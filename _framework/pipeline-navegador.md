# Pipeline Juegos en Navegador (Rust + WASM + WebGPU/WebGL) 🌐

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-14-smaller-models-browser-mmo.md` (video de creador que construyó 2 juegos completos en navegador con modelos pequeños/baratos). Los nombres de productos no entran; las prácticas, con verificación pendiente.
> **Restricción:** "No necesitas modelos state-of-the-art" — GPT-6.1-Sol + Haiku 5.5 son suficientes.

---

## Stack Tecnológico (Browser-First)

| Capa | Tecnología | Por qué |
| :--- | :--- | :--- |
| **Lenguaje** | Rust | Performance, safety, WASM nativo |
| **Compilación** | `wasm-pack` / `cargo` | WASM nativo, sin runtime pesado |
| **Graphics API** | WebGPU + WebGL fallback | WebGPU = performance; WebGL = compatibilidad universal |
| **Runtime** | Navegador (desktop + mobile) | Zero install, zero deploy friction |
| **Multiplayer** | Colyseus (WebSocket) + Railway (self-host) | WebSocket nativo, autoritativo, escalable |
| **Sprite Pipeline** | Spriterrific (custom tool) + alpha maps | 2D en 3D, batching, InstancedMesh |

---

## Pipeline Browser (end-to-end)

| Fase | Qué hace | Herramientas | Tiempo aprox |
| :--- | :--- | :--- | :--- |
| **1. Template base** | Rust + WASM + WebGPU/WebGL boilerplate | Cargo template propio | ~30 min |
| **2. Mockups + Floor plans** | GPT-Image / Codex image gen → 4 mockups + floor plans | GPT-Image, Codex | ~1-2h |
| **3. Assets 3D (Blender)** | Props, entorno, baking → GLTF/GLB | Blender + pipeline-assets.md | ~2-4h |
| **4. Sprites 2D (Spriterrific)** | Character sheets + animaciones (walk, run, idle, interact) | Spriterrific + agente | ~1-2h |
| **6. Ensamblaje en motor** | Three.js + GLTF load + scene setup | Three.js + agente | ~2-4h |
| **7. Multiplayer (Colyseus)** | Autoritativo, WebSocket, client-side prediction | Colyseus + Railway self-host | ~4-8h |
| **7. Polish + Mobile** | Touch controls (analog stick virtual), portrait mode, PWA | CSS + JS + Service Worker | ~2h |
| **7. Deploy** | Railway / Vercel / Netlify / GitHub Pages | CI/CD | ~15 min |

> **Total real:** ~1 semana para juego completo (farming sim) o ~3 días para MMO demo.

---

## 2D Sprites en 3D (Estilo Octopath Traveler / FFT)

| Técnica | Qué hace | Por qué |
| :--- | :--- | :--- |
| **Alpha maps en planos** | Plano 3D + textura con canal alpha = "sprite 3D" | 100x más barato que modelo 3D animado |
| **Billboard / Y-billboard** | Sprite siempre mira a cámara / rota solo en Y | Look 2D en mundo 3D |
| **Atlas de texturas** | Un atlas por personaje = 1 draw call | Performance móvil |
| **InstancedMesh** | Miles de sprites = 1 draw call | Escalable a 1000+ NPCs |
| **Blend shapes en sprites** | Morph targets para expresiones faciales | Emociones baratas |

---

## Spriterrific (Pipeline de Sprites 2D)

> **Herramienta propia del creador** — no entra al catálogo; documentamos el *patrón*.

| Feature | Qué hace |
| :--- | :--- |
| **Prompt → Character sheet** | Genera walk, run, idle, attack, interact, etc. |
| **Prompt → Fix animaciones** | "He faces wrong way / three hands" → re-genera |
| **Blend shapes support** | Muscle size, face variation, equipment swap |
| **Export** | PNG sequences / atlas JSON listo para Three.js |
| **API key en env var** | Cero config, prompt en agente |

**Regla:** *Dogfooding obligatorio.* El creador usa su propia herramienta → encuentra bugs (3 manos, dirección errónea) → fixea la herramienta.

---

## Multiplayer Browser (Colyseus + WebSocket)

| Técnica | Qué resuelve |
| :--- | :--- |
| **Client-side prediction** | Input inmediato → predicción local → corrección servidor → 0 lag percibido |
| **Server reconciliation** | Servidor autoritativo corrige posición cada N ticks |
| **Entity interpolation** | Suavizado visual de otras entidades (lerp entre snapshots) |
| **Single seed para NPCs** | Mismo seed = misma simulación determinista en todos clientes (0 bandwidth para IA) |
| **Position compression** | Enviar solo `uint16` (x, y) + `uint8` (dir) en vez de `float32` × 3 |
| **Interest management** | Solo enviar entidades en viewport + margin (interest area) |
| **Snapshot interpolation** | Buffer de 2-3 snapshots → interpolación suave |

---

## Optimizaciones Móvil (PWA)

| Técnica | Qué hace |
| :--- | :--- |
| **Virtual analog stick** | Touch → vector normalizado → input vector |
| **Portrait mode lock** | `screen.orientation.lock('portrait')` |
| **PWA + Service Worker** | Offline cache, install prompt, background sync |
| **Touch events → pointer events** | Unifica mouse + touch |
| **Viewport meta** | `width=device-width, initial-scale=1, user-scalable=no` |
| **Wake lock** | `navigator.wakeLock.request('screen')` evita sleep |

---

## Costos Reales (Transparencia)

| Juego | Modelo | Costo API | Tiempo |
| :--- | :--- | :--- | :--- |
| **Cozy Farm** (farming sim) | GPT-6.1-Sol | **$89** (~$90 gameplay puro) | ~1 semana |
| **Haiku Harbour** (MMO) | Claude Haiku 5.5 | **$93** (sub-$100) | ~3 días |

> **Regla:** *Siempre reportar costo real (USD / créditos), no "es gratis". Registrar en `00-estado-produccion.md`.*

---

## Dead-ends / Limitaciones (fecha: tanda-14)

| Tarea | Estado |
| :--- | :--- |
| Haiku 5.5 no acierta a la primera | Requiere más iteraciones que Sol; "doesn't get things as right first time" |
| Spriterrific walk cycles | Aún falla a veces (3 manos, dirección errónea) → dogfooding fixea |
| Multiplayer > 1000 concurrentes | No probado; "might make game very busy" |
| Self-hosted Colyseus en Railway | Funciona pero requiere config de WebSocket + SSL |
| Mobile Safari WebGPU | Parcial; WebGL fallback obligatorio |

---

## Dónde Encaja en el Framework

| Documento | Relación |
| :--- | :--- |
| `pipeline-navegador.md` | **Este documento** — pipeline completo browser |
| `pipeline-assets.md` | Perfil `personaje-3d-stylized` (2D en 3D), `vegetacion-shader`, `entorno-procedural-infinito` |
| `pipeline-nivel.md` | Perfil `procedural-asistido` + `arena-sandbox` (chunk loading) |
| `produccion-vfx.md` | Alpha maps, grass shader, day/night, cartoon shader |
| `herramientas-y-apis.md` | Matriz: Rust/WASM, Three.js, Colyseus, Spriterrific |
| `ruta-produccion.md` | Fila: "Juego navegador (Rust/WASM/Three.js + Colyseus)" |
| `escalas-aceptacion.md` | Multiplayer = gate más difícil (sync, lag, prediction) |
| `conocimiento/` | Lecciones: modelos pequeños sirven, dogfooding, cost tracking |

---

## Verificación Pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real (Three.js + Colyseus), y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
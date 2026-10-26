# Pipeline Unity CLI + Agente (Kimi K3) ⚡

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-15-unity-cli-kimi.md` (video de creador que compara Unity CLI + Kimi K3 vs Unreal Engine MCP). **Evidencia alta**: 10+ tests completos mostrados en pantalla, costos reales documentados. **Contra**: vende curso de Unity + IA.

---

## Pipeline Unity CLI + Agente (Kimi K3 / Opus / Opus 5.5 / etc.)

> **Restricción declarada:** Unity 6000+ requerido (solo esta versión soporta el pipeline). **MCP deprecado** → Unity CLI es el puente oficial.

| Fase | Qué hace | Herramientas | Tiempo aprox |
| :--- | :--- | :--- | :--- |
| **1. Setup Unity CLI + MCP** | `unity pipeline install` → instala `com.unity.pipeline` | Unity CLI + MCP config | ~15 min |
| **2. Mockups + Floor plans** | GPT-Image / Codex image gen → mockups + floor plans | GPT-Image, Codex | ~1-2h |
| **3. Assets 3D** | Generador 3D (vía agente) → importar a Unity | Generador 3D + Unity | ~2-4h |
| **4. Sprites 2D (opcional)** | Character sheets + animaciones | Herramienta de sprites 2D | ~1-2h |
| **5. Agente itera en Unity** | Agente usa Unity CLI (MCP) para crear/editar/build/testear en runtime | Unity CLI + Agente (Kimi K3 / Opus / etc.) | ~2-8h por test |
| **6. Multiplayer (opcional)** | Librería networking (Colyseus / Nakama / Mirror / Netcode) | Librería networking + self-host | ~4-8h |
| **7. Polish + Deploy** | Build, optimización, deploy | Unity Build + CI/CD | ~1h |

> **Total real:** 2-8h por test jugable completo (incluye iteraciones visuales).

---

## Hallazgos Clave (Unity CLI vs Unreal Engine MCP)

| Aspecto | Unity CLI + Agente | Unreal Engine MCP |
| :--- | :--- | :--- |
| **Velocidad de iteración** | 2 prompts = 1.5-2h | 3-7 prompts = 3-7h |
| **Facilidad de uso** | Code-first, CLI nativo, MCP nativo | Blueprint-heavy, MCP menos maduro |
| **Debugging** | Agente ve runtime, screenshots, logs | Logs difíciles, crashes frecuentes |
| **Rendimiento** | 120 FPS en tests (WebGPU/WASM) | Laggy, crashes de editor (Niagara) |
| **Costo API** | $8-23 por test completo | $14-23+ por test (más iteraciones) |
| **MCP** | **Nativo, oficial, vía CLI** | Existe pero menos maduro |
| **Debugging visual** | Screenshots + runtime values | Difícil, crashes de editor |

---

## Regla Central: **Engine Code-First > Blueprint-Heavy**

| Criterio | Code-First (Unity CLI, Godot, Rust/WASM) | Blueprint-Heavy (Unreal) |
| :--- | :--- | :--- |
| **Agente controla** | Código C# directo, API completa | Blueprint visual limitado |
| **Iteración** | Prompt → código → build → test (minutos) | Prompt → Blueprint → compile → test (horas) |
| **Debugging** | Logs, breakpoints, runtime values | Breakpoints visuales limitados |
| **Control de versiones** | Git diff en código | Binarios/difícil diff |
| **Escalabilidad** | Código modular, tests automatizados | Blueprints difíciles de escalar |

---

## Regla: **Unity 6000+ + CLI + MCP = Pipeline Oficial**

| Componente | Qué hace |
| :--- | :--- |
| **Unity 6000+** | Versión mínima con soporte Pipeline |
| **Unity CLI** | Binario standalone: `unity pipeline install`, `unity open`, `unity build`, `unity editors running` |
| **`com.unity.pipeline`** | Paquete UPM que expone Pipeline server al CLI |
| **Modo MCP del CLI** | Expone comandos (built-in, custom, `eval`) a agentes vía MCP |
| **`unity-agent-plugin`** | Skills oficiales para Claude Code, Codex, Grok |

---

## Dead-ends / Limitaciones (fecha: tanda-15)

| Tarea | Estado |
| :--- | :--- |
| Unity MCP in-editor | **DEPRECADO** — usar Unity CLI |
| Unreal Engine MCP | Funciona pero **lento, buggy, crashes** (Niagara, memoria) |
| Agente generando shaders complejos | Funciona pero requiere iteraciones visuales |
| NavMesh / NavMesh agents | Funciona pero requiere iteraciones de balance |
| Physics + Niagara (Unreal) | Crashes de memoria, inestable |
| Agente creando NavMesh desde cero | Funciona (NavMeshComponents) pero requiere validación |

---

## Dónde Encaja en el Framework

| Documento | Relación |
| :--- | :--- |
| `herramientas-y-apis.md` | Sección **Unity CLI** (actualizada: MCP deprecado, CLI oficial) |
| `pipeline-assets.md` | Perfil `personaje-3d-secondary` (Unity CLI + generador 3D) |
| `pipeline-nivel.md` | Perfil `modular-asistido` (Unity CLI + agente) |
| `pipeline-navegador.md` | Contraste: **Unity CLI (code-first)** vs **Pure LLM prompting (Three.js)** |
| `herramientas-y-apis.md` | Sección **Unity CLI** actualizada (MCP deprecado, CLI oficial) |
| `ruta-produccion.md` | Fila: "Unity CLI + agente (Kimi K3 / Opus / etc.)" |
| `pipeline-assets.md` | Perfil `personaje-3d-secondary` (Unity CLI + generador 3D) |

---

## Verificación Pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real (Unity 6000+ + CLI + agente), y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
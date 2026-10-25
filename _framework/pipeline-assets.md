# Pipeline de Assets Genérico 🎨

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Consolidación de `pipeline-assets.md` (perfil `personaje-3d-hero` / `personaje-3d-secondary` / `personaje-3d-stylized`), `pipeline-assets.md` (perfil `entorno-unique` + `pipeline-nivel.md` perfil `modular-manual`), `pipeline-assets.md` (perfil `prototipo-rapido`), `produccion-assets.md` y `produccion-vfx.md`. Los nombres de productos no entran; las prácticas, con verificación pendiente.
> **Principio:** un solo pipeline con **perfiles configurables** según el tipo de asset y el objetivo de calidad/velocidad del proyecto.

---

## Perfiles de Asset (se declara en `00-estado-produccion.md` del juego)

| Perfil | Qué cubre | Objetivo de calidad | Pipeline recomendado |
| :--- | :--- | :--- | :--- |
| **personaje-3d-hero** | Protagonista, jefes, NPCs importantes | Alta (hero quality) | High-poly sculpt → retopo → bake completo (color+normal+AO) → texturizado low-poly |
| **personaje-3d-secondary** | NPCs, enemigos genéricos | Media (game-ready) | Smart mesh + UV → mapas desde color map → retopo opcional |
| **personaje-3d-stylized** | RTS, top-down, low-poly | Velocidad > detalle | Smart mesh + color map → normal/roughness/metallic desde color → decimate |
| **entorno-procedural-infinito** | MMO browser, mundos infinitos | Perlin noise + chunk loading + InstancedMesh | Perlin noise 3D/2D, chunk system, distance culling, InstancedMesh |
| **vegetacion-shader** | Grama, árboles, bushes | Shader-based (GPU) | Alpha maps, vertex shader wind, InstancedMesh, distance culling |
| **agent-sandbox-artist** | Agente artista con sandbox propio (modelado, texturizado, rigging, anim, VFX) | Sandbox aislado, herramientas propias, experiencia acumulada, self-healing, blend shapes, decoupling |
| **entorno-procedural-infinito** | MMO browser, mundos infinitos | Perlin noise + chunk loading + InstancedMesh | Perlin noise 3D/2D, chunk system, distance culling, InstancedMesh |
| **vegetacion-shader** | Grama, árboles, bushes | Shader-based (GPU) | Alpha maps, vertex shader wind, InstancedMesh, distance culling |
| **entorno-procedural-infinito** | MMO browser, mundos infinitos | Perlin noise + chunk loading + InstancedMesh | Perlin noise 3D/2D, chunk system, distance culling, InstancedMesh |
| **entorno-tileable** | Suelos, muros, arena, arena, rocas grandes | Tileable PBR | Patina AI / seamless texture AI → tileable + displacement |
| **entorno-modular** | Muros, cercas, postes, props repetibles | Modular + cohesivo | Piezas base + array/curve modifiers en Blender/UE |
| **entorno-unique** | Hero props, landmark, cueva, jefe | Alta (hero) | High-poly sculpt → retopo → bake completo |
| **vfx-simple** | Partículas, trails, impactos simples | Funcional | Código en motor + texturas generadas |
| **vfx-complex** | Habilidades, boss effects, cinemáticos | Alto impacto visual | Concepting 2D → VFX concept → implementación en motor |
| **audio-simple** | SFX, UI sounds | Funcional | Generador API + agente orquestador |
| **audio-complex** | Música adaptativa, voz, foley | Inmersivo | Generador especializado + post-producción |

---

## Pipeline Base (común a todos los perfiles)

| Paso | Qué hace | Quién | Herramientas genéricas |
| :--- | :--- | :--- | :--- |
| **1. Concepto + Referencias** | Imágenes, moodboard, planos, blueprints | Humano | Generador imágenes, moodboard, investigación |
| **2. Separación de partes** | Divide asset en componentes lógicos (cabeza/cuerpo/accesorios; base/accesorios/foliage) | Humano decide, Agente ejecuta | — |
| **3. Generación geometría** | Según perfil: high-poly sculpt / smart mesh / primitivas | Agente | Sculpt tool / Tripo / generador 3D / primitivas motor |
| **4. UV + Retopo** | Según perfil: xatlas / Smart UV / UV Packer / decimate / retopo manual | Agente + Humano | xatlas / Smart UV Project / UV Packer / decimate / retopo tool |
| **5. Bake / Mapas** | Según perfil: high-poly bake (color+normal+AO) / mapas desde color map / tileable PBR | Agente | Cycles bake / color-map generation / Patina AI |
| **6. Texturizado final** | Roughness/metallic/emissive + retoque humano | Agente + Humano | Texture paint / Moondiff / generador PBR |
| **7. Ensamblaje / Rigging** | Según perfil: single armature / partes separadas / primitivas | Humano + Agente | Blender / AccuRig / Mixamo / agente rigging |
| **8. Validación en motor** | Import, LOD, materiales, colisiones, performance | Humano + Agente | Motor (UE/Unity/Godot) + agente validación |

---

## Perfiles en Detalle

### 1. personaje-3d-hero (protagonista, jefes)

| Paso | Específico |
| :--- | :--- |
| Geometría | High-poly sculpt en Blender (elastic grab, pinceles) → combina partes en high-poly único |
| Retopo | Tripo (quads) o Blender (retopo manual donde falle adherence) |
| UV | xatlas interno o Smart UV Project + UV Packer addon |
| Bake | **Normal + AO + Color + roughness/metallic opcional** en Cycles |
| Color bake | Si high-poly está bien → **no retexturizar low-poly** |
| Flexibilidad | Ajustar roughness/metallic on-the-fly en low-poly sin rebakear |
| Rigging | Híbrido: Mixamo/AccuRig (cuerpo) + Agente (partes custom: alas, cola, cabello) → **single armature** |
| Animación | Referencias video → Agente genera → feedback visual (plugin "set pose") |
| VFX | Concepting 2D → VFX concept (HTML viz + timing) → implementación en motor |

### 2. personaje-3d-secondary (NPCs, enemigos)

| Paso | Específico |
| :--- | :--- |
| Geometría | Smart mesh (Tripo P2, 4 variantes poly count) + multi-view (back/side obligatorio) |
| UV | Smart UV (prerequisito) |
| Mapas | Normal/roughness/metallic **desde color map** (minutos vs horas baking) |
| Rigging | AccuRig (gratis) → export UE5 skeleton → retarget en motor |
| Animación | Retarget de plantilla UE (15 min/personaje) |

### 3. personaje-3d-stylized (RTS, top-down, low-poly)

| Paso | Específico |
| :--- | :--- |
| Geometría | Smart mesh (20k polys max) + multi-view (back/side obligatorio) |
| UV | Smart UV |
| Mapas | Normal/roughness/metallic **desde color map** |
| Retopo | Decimate en Blender (target poly count por propósito) |
| Rigging | AccuRig (cuerpo) + Agente (partes custom: alas, cola) → single armature |
| Animación | Retarget de plantilla UE (15 min/personaje) |

### 4. entorno-tileable (suelos, muros, arena, rocas grandes)

| Paso | Específico |
| :--- | :--- |
| Generación | **Patina AI / Seamless Texture AI** (pay-per-use, ~8¢/gen) → base color + normal + roughness + AO + height/displacement |
| Aplicación | UV tileable + displacement map en motor |
| Variación | Área circular repetida en UV → "no es solo un área, van en círculos" |
| Proyección | Imagen 2D → UV cilíndrica (ej. área circular jefe) |

### 5. entorno-modular (muros, cercas, props repetibles)

| Paso | Específico |
| :--- | :--- |
| Piezas base | Generar piezas base (muro, poste, roca) |
| Ensamblaje | **Array + Curve modifier** en Blender/UE (muros circulares, círculos de rocas, anillos) |
| Control | Control total, optimización nativa |
| Reutilización | Mismo material = optimización gratis (menos draw calls) |

### 6. entorno-unique (hero props, landmarks, cueva, jefe)

| Paso | Específico |
| :--- | :--- |
| Geometría | High-poly sculpt → retopo → bake completo (igual que personaje-3d-hero) |
| Texturas | Bake color + normal + AO + roughness/metallic |
| Flexibilidad | Ajustar roughness/metallic on-the-fly sin rebakear |

### 7. vfx-simple / vfx-complex

Ver `produccion-vfx.md` para pipeline completo. Resumen:

| Perfil | Enfoque |
| :--- | :--- |
| **vfx-simple** | Código en motor + texturas generadas; iteración verbal |
| **vfx-complex** | Concepting 2D obligatorio → VFX concept (ref + timing + capas + trigger + bordes) → implementación en motor con playground + iteración verbal |

### 8. audio-simple / audio-complex

| Perfil | Enfoque |
| :--- | :--- |
| **audio-simple** | Agente orquesta APIs de generación especializada (SFX, UI) |
| **audio-complex** | Generador especializado + post-producción humana |

---

## Reglas Transversales (aplican a todos los perfiles)

| Regla | Origen |
| :--- | :--- |
| **Separación de partes antes de generar** | Control posterior de animación, LOD, materiales, reemplazo |
| **Smart UV es prerequisito** | UV legible = agente entiende islas → mapas desde color map funcionan |
| **Generar variantes poly count y elegir** | 4 variantes poly count por parte → elegir por wireframe + uso final (LOD implícito) |
| **Mapas desde color map = ahorro masivo** | Horas baking → minutos; requiere buen UV |
| **Emissive/glow via mask en motor** | No se pinta en textura; se hace en motor |
| **Rigging híbrido: estándar + agente** | Estándar automático (Mixamo/AccuRig) + Agente para custom → single armature |
| **Ajustes finos: nativo > agente** | Sculpt grab / knife / boolean en Blender (5 seg) vs horas agente |
| **Animación: video ref → agente → corrección por pose** | Feedback visual (plugin "set pose") > descripción verbal |
| **VFX concept = HTML viz + timing** | Valida idea antes de código |
| **Agentes especializados por etapa** | Animation agent → Unity/UE agent (no un agente único) |
| **Tileables + displacement > geometría** | Superficies grandes = textura + displacement, no geometría generada |
| **Ensamblaje: primitivas + modificadores** | Array + Curve modifier > IA placement (control > slop) |
| **Referencia de escala exportada del motor ANTES de modelar** | Evita rehacer por escala |
| **Wireframe perfecto no necesario para estáticos** | "Suficientemente bueno" > perfección técnica |
| **Decimate en Blender para low-poly rápido** | "Quedó perfecto; no necesité retopo manual" |
| **Foliage/agua dinámicos: comprar, no generar** | "Mejor comprar hoy; IA generará procedural más adelante" |
| **Assets generados en un estilo = cohesión gratis** | "Generados en un estilo → encajan sin horas de matching" |
| **Prototipo jugable > perfección** | "Punto de partida para iterar" |

---

## Dead-ends / Limitaciones Actuales (consolidado)

| Tarea | Estado |
| :--- | :--- |
| Generar foliage/grass/agua procedural con IA | "Mejor comprar hoy; IA lo hará procedural más adelante" |
| Rigging perfecto sin retoque humano | Siempre hay fix de pesos (hombros, dedos, ropa) |
| Exportar materiales Blender → UE con misma config | "No descubrí cómo... normalmente reconstruyes el shader en UE" |
| Animaciones complejas (quadrupeds, cloth) sin fix manual | Requiere paint weights, colliders, retargeting |
| Acceso a modelos frontera (Fable 5, Opus 5) desde fuera de US | Geo-blocking |
| Video AI para run/complex animations | Sirve de referencia bruta; GPT lo limpia mejor |
| Generar todo el ensamblaje con agente | "1-2 horas + tokens + igual necesitas fixear" → humano 12 min |
| Generar todo el personaje en una sola llamada | Falla: topología, UV, animación, LOD incontrolables |
| Video AI para run/complex animations | Sirve de referencia bruta; GPT lo limpia mejor |

---

## Dónde Encaja en el Framework

| Documento | Relación |
| :--- | :--- |
| `pipeline-nivel.md` | Consume assets; define placement strategies |
| `produccion-vfx.md` | Perfil vfx-simple/complex |
| `montaje-de-niveles.md` | Ensambla assets en nivel |
| `dimensiones-juego.md` #3, #4, #6 | Assets, mapas, combate/VFX |
| `herramientas-y-apis.md` | Criterios de selección de herramientas |
| `ruta-produccion.md` | Router según perfil de asset |
| `ciclo-produccion.md` | Fases Prototipo / Producción / QA |
| `escalas-aceptacion.md` | Estados de aceptación por asset |
| `conocimiento/` | Lecciones aprendidas por perfil |
| `agentes-especializados.md` | Patrones de agentes especializados: artist agent sandbox, self-healing, blend shapes, decoupling |

---

## Verificación Pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real, y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
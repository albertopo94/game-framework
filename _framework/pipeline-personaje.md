# Pipeline Completo de Personaje con Agentes 🧙

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-08-personaje-completo-pipeline.md` (mismo canal que tandas 5-7: demo completa en pantalla de personaje volador con animaciones, VFX y integración en Unity — **evidencia media-alta**: pipeline end-to-end visible funcionando; contra: **vende su curso 3D AI** y usa su "workspace" propio Mr. Mak — incentivo de mostrar fluidez y destacar sus herramientas). Los nombres de productos no entran; las prácticas, con verificación pendiente.
> **Enfoque del creador:** "character ready in one day" — pipeline optimizado por velocidad, no por calidad AAA. El creador admite atajos (no high-poly bake, normal maps desde color map).

## Pipeline end-to-end (resumen del flujo)

| Etapa | Herramienta/agent | Qué hace el humano | Qué hace el agente |
| :--- | :--- | :--- | :--- |
| 1. Separación de partes + Smart UV | Humano (decisión) / Agente (ejecución) | Define partes (cabeza, cuerpo, piernas, armadura, accesorios, cabello, alas), pone en A-pose | Genera 3D desde imágenes (Tripo P2), hace Smart UV |
| 2. Texturizado | Agente (color map) + Humano (retoque) | Revisa, guía iteraciones | Genera normal/roughness/metallic desde color map |
| 3. Ensamblaje en Blender | Humano (12 min) | Coloca, recorta, ajusta escala, organiza colecciones | — |
| 4. Rigging | Mixamo (cuerpo) + GPT (alas) | Decide qué partes, pone markers | Rigging de alas custom |
| 4.5 Fixes de textura | Moondiff (paint over) | Retoque puntual de artefactos | — |
| 5. Animación | GPT-6 Astra (Overlord workspace) | Da conceptos, referencias video, feedback de poses (plugin "set pose") | Genera animaciones, corrige por feedback, itera |
| 6. VFX | Agente (HTML viz + timing) + Motor | Conceptos, referencias, feedback verbal | Implementa en motor (Unity), itera verbal |
| 7. Integración final | Overlord Unity agent | Feedback visual en juego | Integra animaciones + VFX + lógica en motor |

## Reglas operativas transferibles

| Regla | Por qué |
| :--- | :--- |
| **Separación de partes antes de generar** | Cada parte (cabeza, cuerpo, piernas, armadura, cabello, alas) se genera y texturiza independiente → control posterior de animación, LOD, materiales, reemplazo |
| **Smart UV es prerequisito, no opcional** | UV legible = agente entiende qué isla es qué → normal/roughness/metallic desde color map funcionan; UV malo = agente falla en detectar partes |
| **Generar 4 variantes de poly count por parte y elegir** | No se sabe de antemano qué densidad encaja; se genera rango y se elige por wireframe + uso final (LOD implícito) |
| **Normal/roughness/metallic desde color map = ahorro masivo** | Horas de baking → minutos de agente; "si el UV está bien, el agente lo entiende y lo hace" — validado por el creador en producción real |
| **Emissive/glow via mask + agent** | Partes que brillan (ascuas) → pedir al agente "mask this area and make it glow" en integración; no se pinta en textura, se hace en motor |
| **Rigging híbrido: Mixamo (estándar) + Agente (custom)** | Cuerpo humanoide → Mixamo (automático, probado); partes custom (alas, cola, cabello) → GPT escribe rig script; **single armature al exportar** |
| **Blend shapes / shape keys para correcciones** | El creador usa "sculpt mode elastic grab" en Blender para ajustes finos (5 seg) vs esperar horas al agente — **herramienta nativa > agente para ajustes finos** |
| **Animación: referencias → agente → corrección por pose** | Referencias video (Mixamo, Kling, video propio) → GPT genera → feedback via plugin "set pose" (click en frame, guarda pose, agente corrige) — **feedback visual > descripción verbal** |
| **VFX concept = HTML viz + timing** | Antes de motor, agente genera visualización HTML simple con timing (anim time = VFX time) → valida idea antes de código |
| **Pipeline de agente especializado por etapa** | Overlord Animation agent (solo animaciones) → Overlord Unity agent (integración final) — **agentes especializados, no un agente único** |

## Hacks y atajos declarados (no son "best practices", son tradeoffs de velocidad)

| Atajo | Qué ahorra | Qué arriesga |
| :--- | :--- | :--- |
| **Normal/roughness/metallic desde color map (no high-poly bake)** | 4-6 horas de baking | Detalle fino en superficies metálicas/complejas; "para RTS es más que suficiente" |
| **Wings: generar imagen menos detallada → modelo → textura sobre ella** | Geometría de plumas = problema de topología; textura da detalle visual sin geometría | Menos detalle geométrico real; solo válido si el ala se ve a distancia media |
| **Mixamo solo cuerpo, GPT para alas** | Mixamo no hace alas; GPT hace rig custom rápido | Rig de alas puede requerir iteraciones de pesos |
| **Moondiff para fix de texturas en vez de regenerar** | Segundos vs minutos de regeneración + re-UV | Requiere saber pintar en Moondiff; no arregla geometría |
| **Blender para ensamblaje (12 min) vs Agente (1-2 horas + tokens)** | Tiempo y tokens masivos | Requiere saber Blender básico (hotkeys, knife, boolean, UV packer) |
| **Rigging: Mixamo cuerpo + GPT alas → single armature** | Mixamo no hace custom; GPT sí | Pesos de alas pueden necesitar iteración |
| **Plugin "set pose" para feedback de animación** | Feedback visual exacto vs describir en palabras | Requiere desarrollar/mantener el plugin |

## Dead-ends / limitaciones actuales (fecha: tanda-08)

| Tarea | Estado |
| :--- | :--- |
| Generar todo el ensamblaje con agente (posición, escala, cortes) | "Capaz, pero 1-2 horas + tokens + igual necesitas fixear" → humano 12 min |
| Video AI para run/complex animations | Sirve de referencia bruta; GPT lo limpia mejor |
| Generar todo el personaje en una sola llamada (sin separar partes) | Falla: topología, UV, animación, LOD incontrolables |
| Baking high-poly → low-poly para estilo RTS | Innecesario para este estilo; "overkill" declarado por el creador |

## Dónde encaja en el framework

| Documento | Relación |
| `prototipo-fin-de-semana.md` | Rigging AccuRig + retarget UE (vs Mixamo+GPT); animaciones via retarget de plantilla |
| :--- | :--- |
| `produccion-assets.md` | Partes + Smart UV + texturizado agente + ensamblaje = pipeline de asset de personaje |
| `produccion-vfx.md` | Emissive mask + VFX en motor; hojas/partículas separadas para VFX |
| `produccion-vfx.md` / `rigging` | Rigging híbrido documentado aquí; wings = custom rig |
| `herramientas-y-apis.md` | Matriz: character generation pipeline = pendiente (2 fuentes: tanda-05 y tanda-08) |
| `dimensiones-juego.md` #3 | Assets de personaje (partes, UV, texturas, rig) |
| `dimensiones-juego.md` #5 | Animaciones + rigging = bucle y controles |
| `dimensiones-juego.md` #6 | VFX de habilidades, feedback visual |
| `ruta-produccion.md` | Nueva fila: "Pipeline completo de personaje" → este doc (o sección en produccion-assets) |

## Productos nombrados (excluidos deliberadamente)

Tripo P2 (4 variantes poly), GPT-6 Astra / Opus 5.5, Mixamo, Moondiff, "Overlord workspace" (su CLI + skills en GitHub), plugin "set pose" (addon propio). **No entran al catálogo**: el video promociona su curso y su workspace propio. Si un juego necesita la capacidad, la herramienta se evalúa contra `herramientas-y-apis.md` con nombre verificado en fuente.

## Verificación pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real, y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.

## Nota sobre la calidad de la evidencia

- **Media-alta**: personaje completo funcionando en motor (Unity) con animaciones, VFX y lógica de vuelo visible en pantalla.
- **Sesgo fuerte**: el creador vende su **curso 3D AI** y su **workspace Mr. Mak** (skills en GitHub, "Overlord" agents). El video está estructurado para demostrar que "su workflow + sus tools + su curso = resultado rápido". Los tiempos (12 min assembly, 2h animaciones) son de **él con su setup experto**, no de un novato.
- **Lo que sí es estructural y durable**: separación de partes, smart UV, mapas desde color map, rigging híbrido, feedback visual via plugin, agentes especializados por etapa. Esas prácticas se portan al framework; los tiempos y productos no.
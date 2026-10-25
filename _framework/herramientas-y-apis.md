# Herramientas y APIs 🛠️

> **Origen:** construido con el conocimiento del creador a medida que se incorpora. No se inventan herramientas aquí sin respaldo.
> **Estado:** 🚧 en construcción. Cada entrada tiene un estado de validación en el entorno local.

## Principio rector

Las herramientas son **ejemplos, no dependencias obligatorias** (heredado del YouTube Creator Hub):

- El framework enseña **métodos**; el producto concreto se decide según cada juego y las herramientas del creador.
- **Partir de lo que el creador tiene:** el agente parte de las herramientas disponibles y preferidas.
- **Recomendación debatible:** el agente puede proponer otra herramienta si existe una ventaja real, pero debe explicar qué mejora, qué pierde, qué costa y qué limitaciones tiene. El agente **no cambia de herramienta unilateralmente**.
- **Comprobar la capacidad antes de proponer:** antes de proponer un flujo dependiente de una función específica, el agente debe comprobar si la herramienta elegida la ofrece o existe un procedimiento equivalente.
- **Nunca asumir gratuidad:** ningún modo «Draft», «Preview» o «Borrador» es gratuito por definición; el costo real se registra en el registro de recursos del juego (`04-registro-recursos.md`, plantilla pendiente de pipeline) antes de escalar a la versión definitiva.

## Criterios para elegir herramienta en un flujo con agentes

La agnosticidad no significa elegir a ciegas. Criterios estructurales, verificables por inspección antes de adoptar nada:

| Criterio | Por qué importa con agentes |
| :--- | :--- |
| **Archivos de proyecto legibles como texto (code-first)** | Un agente puede leer, interpretar y editar el estado del proyecto directamente. Un formato binario opaco lo deja ciego y obliga a intermediarios. La evidencia de la práctica indica que el trabajo con agentes es sensiblemente más fluido en motores code-first; no es una prohibición de los demás, es un criterio de costo de fricción. *(Origen: tanda-05; verificar en nuestro entorno.)* |
| **Editor controlable por script o puente (CLI/MCP)** | El agente puede abrir, modificar y verificar en el motor real, no solo proponer código. Sin esto, la verificación en motor (estado 4 de `escalas-aceptacion.md`) queda fuera de su alcance. |
| **Salida exportable al formato del motor** | Un asset generado que no importa limpio al motor no es un asset; es una imagen simpática. |
| **Costo y límites de uso conocidos** | El presupuesto de agente es un recurso del proyecto, no infinito. |
| **Licencia compatible con publicar** | Especialmente con assets: la trazabilidad legal sigue vigente. |

Estos criterios son **agnósticos**: describen capacidades, no nombran productos como obligatorios. Cuando se evalúa una herramienta concreta, se la puntúa contra esta tabla y se registra el resultado.

## Matriz de capacidad del agente (hipótesis a verificar en práctica)

Registrada como hipótesis de terceros (`_framework/referencias/notas-creador/tanda-04-agente-y-steam.md`), **no como regla**. Se confirma o descarta con práctica en juegos reales y entonces se mueve a `conocimiento/`.

| Área | Ipótesis inicial | Verificado en |
| :--- | :--- | :--- |
| Código, controles, sistemas | El agente rinde bien | pendiente |
| Diseño de niveles | Rinde mal: la disposición espacial pide criterio humano. **Dos fuentes de terceros coinciden en que el placement suelto produce *slop*** (ver `montaje-de-niveles.md`) | pendiente |
| Ensamblado de ambientes (kit → nivel) | El agente prepara y procesa el kit; el montaje con intención es humano o propuesta etiquetada estado 2 | pendiente |
| VFX (partículas, shaders, timelines, triggers) | El agente escribe código del motor a partir de VFX concept + asset preparado; iteración visual en playground | pendiente |
| VFX concepting (2D) | El agente genera conceptos 2D + timing + capas antes de implementar; validado por creador | pendiente |
| Pipeline completo de personaje (partes → UV → textura → rig → anim → VFX → motor) | Agente genera partes + UV + mapas; humano ensambla en Blender (12 min) + rigging híbrido Mixamo+GPT; animaciones y VFX por agente especializado; integra en motor | pendiente (2 fuentes: tanda-05 + tanda-08) |
| Arte y música | Rinde mal o inconsistente **hecho por el LLM**; el camino es generar assets con generadores especializados + remate humano. Ver `produccion-assets.md` | pendiente |
| VFX/partículas en motores code-first | Vía código funciona bien en juegos chicos; con puente al sistema de partículas del motor, da base sólida que el humano retoca | pendiente |
| Audio (SFX/música) | El agente **orquesta APIs de generación especializada** y elige el modelo; no genera audio "con el LLM" | pendiente |
| ¿Es divertido? | **Nunca**: solo jugadores reales (**esta sí está confirmada**: es la regla de estado 5 de `escalas-aceptacion.md`) | confirmado |

**Dato de entrada, no decisión:** si la hipótesis se confirma, el efecto práctico es que arte y audio se resuelven con producción propia o assets comprados con licencia registrada, y el agente se concentra en código y sistemas.

## Categorías de herramientas

| Categoría | Herramienta | Estado | Notas |
| :--- | :--- | :--- | :--- |
| **Engine** | Godot | ✅ Candidata privilegiada | Open source, ligero, 2D/3D |
| **Engine** | Unity | ✅ Candidata privilegiada | Ecosistema amplio |
| **Art / Modelado 3D** | **Blender MCP oficial** | ✅ **Herramienta principal de creación de assets** | MCP oficial de Blender. Para crear assets (modelado, texturas, iluminación, exportación) cuando el tipo de juego lo amerite. |
| **Audio** | _pendiente del creador_ | ⏳ | |

## Blender MCP oficial — creación de assets

### Cuándo se usa

- **Siempre que el tipo de juego lo amerite.** No es un estándar universal: un juego de pixel art 2D puro puede no necesitarlo; un juego 3D, un 2.5D pixel art con iluminación dinámica, o cualquier juego que requiera modelado/texturas sí.
- La decisión la toma el **rol 01 (Concepto)** en conjunto con el **prompt maestro**: la dimensión 3 (Recursos/assets) y la dimensión 4 (Mapas) declaran si se requiere Blender MCP.
- El agente **nunca asume** que un juego 2D no necesita Blender MCP. Consulta al creador o registra la decisión con justificación.

### Capabilidades esperidas (a verificar en el entorno local)

Antes de proponer un flujo concreto, el agente debe comprobar si la herramienta elegida lo ofrece. No se asumen capacidades por nombre.

### Protocolo de traspaso cuando el agente no tiene acceso

**No es exclusivo de Blender: aplica a cualquier herramienta que el agente no pueda ejecutar** (UI manual, login, editor de escritorio, web, compra). Regla y ficha completa en `AGENTS.md` regla 7 y `plantillas/ficha-recurso-manual.md`. Resumen:

1. El agente **no delega la tarea: entrega el paquete listo para un clic** — una ficha por recurso con tipo, herramienta, parámetros ya resueltos, contenido listo para pegar, pasos de interfaz, ruta de guardado y costo.
2. Prohibido entregar instrucciones abstractas o listas de prompts sin clasificar.
3. Al recibir el resultado, el agente lo verifica contra la ficha y lo registra en el registro de recursos del juego (`04-registro-recursos.md`, plantilla pendiente de pipeline) con licencia, origen y trazabilidad.

## Agregado por capability (pendiente del conocimiento del creador)

| Capability | Herramientas | Estado |
| :--- | :--- | :--- |
| Busca assets de stock | Coverr, Pexels, Pixabay, Openverse | ⏳ Pendiente |
| Generación visual IA | _pendiente_ | ⏳ |
| Audio / música | _pendiente_ | ⏳ |
| Testing / QA | _pendiente_ | ⏳ |
| Build / distribución | _pendiente_ | ⏳ |

## Proactividad de herramientas

Si el agente identifica una herramienta, biblioteca, CLI o recurso que resolvería un cuello de botella y no figura aquí, **la propone con justificación**. Pero **nunca la incorpora al catálogo de forma automática**: debe presentar la sugerencia al creador y, solo si el creador otorga su **visto bueno explícito**, registrarla aquí indicando su estado de validación en el entorno local.

## Relación con otros documentos

- `roles/01-concepto-y-mercado.md` §4: las herramientas se declaran por juego en Concepto.
- `plantillas/prompt-maestro-creacion.md` §4: el prompt maestro lista las herramientas.
- `00-estado-produccion.md`: cada juego declara su engine/art/audio ahí; eso es lo único que fija herramientas.
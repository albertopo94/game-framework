# _framework — Núcleo metodológico

**⚠️ Estado: en construcción.**

A diferencia del YouTube Creator Hub (donde roles y plantillas ya estaban estudiados), aquí los roles, plantillas y reglas **se construyen con el conocimiento que el creador va incorporando**, no se inventan de una vez.

## Qué vive acá

| Archivo | Propósito | Estado |
| :--- | :--- | :--- |
| `reglas-sistema.md` | Reglas operativas para agentes | ✅ Inicial |
| `escalas-aceptacion.md` | Los 5 estados de "está listo" + qué prueba cada evidencia + comparación justa | ✅ Canónico |
| `ruta-produccion.md` | Router: qué documento leer según el resultado necesario | ✅ Canónico |
| `higiene-de-trabajo.md` | Cómo se registran hallazgos, fixes y commits para que sean trazables | ✅ Canónico |
| `produccion-assets.md` | Cómo producir assets con agentes: descomponer por piezas, remate humano presupuestado, dead-ends | 🟡 Hipótesis de terceros a verificar |
| `montaje-de-niveles.md` | Kit + ensamblado de niveles: ancla de escala, grandes-primero, slop como fracaso, pasada de presentación | 🟡 Hipótesis de terceros a verificar |
| `produccion-vfx.md` | Concepting 2D, VFX library, pipeline asset-optimizado, rigging híbrido, implementación en motor | 🟡 Hipótesis de terceros a verificar |
| `pipeline-assets.md` (perfil `personaje-3d-hero` / `personaje-3d-secondary` / `personaje-3d-stylized`) | Pipeline end-to-end de personaje: partes + smart UV → mapas desde color → rig híbrido → anim + VFX → motor | 🟡 Hipótesis de terceros a verificar |
| `pipeline-assets.md` (perfil `entorno-unique` + `pipeline-nivel.md` perfil `modular-manual`) | Nivel Souls-like jugable en 72h: high-poly bake → tileables → modular level → plantilla UE + MCP + agente navegador | 🟡 Hipótesis de terceros a verificar |
| `prompting-puro-browser.md` | 7 pasos: prompt + target + loop + play + score/revise + skills + ship; solo LLM + framework WebGL | 🟡 Hipótesis de terceros a verificar |
| `pipeline-unity-cli.md` | Pipeline Unity 6000+ CLI + agente (Kimi K3 / Opus / etc.); code-first, MCP nativo | 🟡 Hipótesis de terceros a verificar |
| `pipeline-navegador.md` | Pipeline completo navegador: Rust/WASM + framework WebGL + librería networking + herramienta de sprites 2D | 🟡 Hipótesis de terceros a verificar |
| `agentes-especializados.md` | Patrones de agentes especializados: artist agent sandbox, self-healing, blend shapes, decoupling | 🟡 Hipótesis de terceros a verificar |
| `pipeline-assets.md` (perfil `prototipo-rapido`) | Prototipo jugable 2 días: plantilla UE + herramienta de auto-rigging + retarget + generador de texturas PBR tileables + foliage/agua comprados | 🟡 Hipótesis de terceros a verificar |
| `ciclo-produccion.md` | Ciclo macro de producción de un juego | 🚧 Borrador |
| `roles/` | Roles que intervienen según tamaño/tipo de juego | 🚧 `roles/01-concepto-y-mercado.md`, `roles/02-diseno-juego.md`, `roles/05-release-distribucion.md` (01-02: tandas 1-3 + Mass Flux; 05: patrón de sus releases) |
| `plantillas/` | Plantillas de pipeline por juego | 🚧 `plantillas/prompt-maestro-creacion.md` (arranque) + `plantillas/sub-sistema-juego.md` (una por mecánica) + `plantillas/handoff-sesion.md` (traspaso) + `plantillas/propuesta-cambio.md` (scoping) + `plantillas/ficha-recurso-manual.md` (traspaso sin acceso)  + `plantillas/agente-artista.md` (pendiente) + `plantillas/spriterrific.md` (pendiente)
| `dimensiones-juego.md` | Las 7 dimensiones de un juego (concepto, arte, assets, mapas, bucle, combate, entrega) — checklist transversal de gates | ✅ `tanda-03` |
| `referencias/` | Material externo conservado + ficha de análisis | ✅ `notas-creador/` (tandas verbatim) + `README.md` (análisis de Mass Flux GDD, mr-mak-workspace, las 16 tandas del creador y documentación externa de herramientas) |
| `herramientas-y-apis.md` | Directorio de herramientas por capability | ✅ Inicial (MCP de modelado 3D como principal de assets) |

## Modos de trabajo

El framework tiene **dos modos** que no se mezclan:

1. **Modo Creación (Prompt Maestro):** arranca un proyecto desde cero con un único prompt que define el contrato (referencia visual, restricciones duras, assets, herramientas, scope, referentes). Plantilla: `_framework/plantillas/prompt-maestro-creacion.md`.
2. **Modo Producción (Checkpoints):** una vez el proyecto existe, se desarrolla con checkpoints humanos (concepto aprobado, diseño aprobado, etc.). El prompt maestro **no sustituye los checkpoints**: define el contrato inicial; el desarrollo sigue las puertas de calidad de `AGENTS.md`.

## Sesiones (1 feature = 1 sesión)

- **`00-estado-produccion.md`** = instantánea de verdad (fase, siguiente acción, decisiones).
- **`bitacora-sesiones.md`** = historial (quién, cuándo, qué feature, qué evidencia, qué pendiente).

La bitácora **resume** el traspaso; el estado lo **contiene** completo. Si hay conflicto, el estado manda y la bitácora se corrige en la próxima sesión. Ver `AGENTS.md` §Protocolo de Sesión.

## Qué este framework NO es (límites declarados)

Siguiendo nuestra propia regla de declarar límites (`higiene-de-trabajo.md` §7):

| Fuerte hoy | Débil / en borrador hoy | Explícitamente afuera por ahora |
| :--- | :--- | :--- |
| Gobernanza y autonomía de agentes; disciplina de aceptación y evidencia; estructura de sesiones y traspaso; conceptualización y diseño por subsistemas | Roles 03 (producción), 04 (QA) y 06 (post-release) aún no existen; pipeline numerado por juego sin plantillas; conocimiento de plataformas de distribución | Automatización de pipeline o herramientas propias antes del primer juego piloto; cualquier motor, proveedor o modelo como dependencia |

Nada de lo “débil” se rellena inventando: espera conocimiento del creador o práctica en un juego real.

## Regla fundamental

Nada se agrega a `roles/` o `plantillas/` sin que respalde conocimiento del creador o evidencia de la práctica real. Menos estructura real y probada > más estructura inventada.

## Referencia o procedimiento (no las dos cosas mezcladas)

Todo documento operativo declara a cuál de los dos tipos pertenece. Un doc que mezcla los dos es un doc mal archivado.

| Tipo | Qué contiene | Cómo lo usa el agente |
| :--- | :--- | :--- |
| **Referencia** | Hechos, criterios, definiciones, límites. Responde *qué es verdad*. | Lee y decide. **No hay orden**: se saltean secciones sin daño. |
| **Procedimiento** | Pasos con **orden fijo** y **una salida nombrada por paso**. Responde *cómo se hace*. | Ejecuta en orden. Omitir un paso es un defecto, no una optimización. |

**Diagnóstico de deterioro.** Un documento de referencia que se fue llenando de pasos ejecutables, o una plantilla que en vez de campos para completar empezó a tener checklist, está avisando que adentro hay un procedimiento mal archivado. Se separa: la información queda en referencia, los pasos salen a un procedimiento explícito.

> Señal inequívoca: si ante una tarea el agente **vuelve a derivar el orden de los pasos** leyendo prosa, eso es un procedimiento que nadie fijó. La prosa deja reconstruir el orden en cada sesión; un procedimiento lo congela.

**Cómo se crea un procedimiento** — el disparador de **frecuencia**, hermano del de evidencia:

| Disparador | Qué promueve | Dónde |
| :--- | :--- | :--- |
| Evidencia repetida de un **hallazgo** | Que algo **es verdad** → regla | `conocimiento/`: `observación` → `comprobado` → `regla-candidata` |
| Un **resultado** que destacó | Que algo **salió bien** → reutilizable | `higiene-de-trabajo.md` §6 |
| Un **procedimiento que se re-escribe a mano** (misma secuencia de instrucciones en más de una sesión) | Que algo **se está reconstruyendo** → procedimiento con orden fijo | Este apartado |

Un procedimiento se escribe en el documento del juego si es específico del juego, o en `_framework/` si es transversal. **No se automatiza**: sigue siendo un documento que el agente lee y ejecuta en orden, no un script. El límite sigue vigente: **nada de automatización ni herramientas propias antes del primer juego piloto** (ver §Qué este framework NO es).

*(Origen del criterio de clasificación: análisis de la documentación de un asistente comercial para motores; ver la ficha en `_framework/referencias/README.md` §Documentación externa. Solo se adopta el criterio conceptual: la herramienta y su sistema de skills no se adoptan.)*

## Dónde vive cada tipo de contenido

| Si es... | Va en |
| :--- | :--- |
| El método de trabajo | `_framework/` |
| Un procedimiento reutilizable transversal | `_framework/`, como documento de tipo **procedimiento** |
| Un procedimiento específico de un juego | Su carpeta en `mis-juegos/` |
| Una lección aprendida haciendo un juego | `conocimiento/` |
| Material externo que se conserva tal cual | `_framework/referencias/` |
| El estado o la historia de un juego concreto | Su carpeta en `mis-juegos/` |
| Una decisión de herramienta de ESTE juego | Su `00-estado-produccion.md` |

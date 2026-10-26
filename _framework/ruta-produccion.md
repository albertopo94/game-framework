# Ruta de Producción 🧭 (Router)

> **Uso:** antes de ejecutar cualquier trabajo, el agente identifica **qué resultado se necesita ahora** y lee los documentos correspondientes. Esto no es un índice decorativo: es el primer paso de toda tarea.
> **Origen:** patrón destilado del router de `mr-mak-workspace` (skill `3d-production-routing`).

## ¿Qué resultado se necesita ahora?

| Necesidad | Leer |
| :--- | :--- |
| Arrancar un proyecto de cero (contrato inicial) | `plantillas/prompt-maestro-creacion.md` |
| Validar o matar una idea de juego | `roles/01-concepto-y-mercado.md` |
| Diseñar mecánicas, sistemas, tema interpretado | `roles/02-diseno-juego.md` + `plantillas/sub-sistema-juego.md` |
| Fijar o revisar estética | `banco-visual.md` + `reglas-sistema.md` (referencia visual) |
| Decidir motor, art o audio | `herramientas-y-apis.md` |
| Producir assets (personajes, ambientes, props, audio) con agentes | `produccion-assets.md` |
| Ensamblar un nivel/ambiente a partir de assets | `montaje-de-niveles.md` |
| Diseñar e implementar VFX (concepting → motor) | `produccion-vfx.md` |
| Pipeline completo de personaje (partes → UV → textura → rig → anim → VFX → motor) | `pipeline-assets.md` (perfil `personaje-3d-hero` / `personaje-3d-secondary` / `personaje-3d-stylized`) |
| Proyecto completo bajo restricción de tiempo con plantilla + MCP + agente navegador | `pipeline-assets.md` (perfil `entorno-unique` + `pipeline-nivel.md` perfil `modular-manual`) |
| Desarrollo browser-game solo con prompting (Three.js, sin motor) | `prompting-puro-browser.md` |
| Juego navegador/móvil (Rust/WASM/Three.js + Colyseus + Spriterrific) | `pipeline-navegador.md` |
| Pipeline personaje con agente artista especializado | `agentes-especializados.md` |
| Pipeline personaje con agente artista especializado | `agentes-especializados.md` |
| Pipeline personaje con agente artista especializado | `agentes-especializados.md` |
| Prototipo jugable en fin de semana (plantilla + retarget + assets comprados) | `pipeline-assets.md` (perfil `prototipo-rapido`) |
| Saber en qué fase estoy y qué sigue | `00-estado-produccion.md` del juego + `ciclo-produccion.md` |
| Documentar una mecánica concreta | `plantillas/sub-sistema-juego.md` |
| Verificar que algo se ve o se comporta bien | `escalas-aceptacion.md` (protocolo de comparación justa) |
| Decir si algo "está listo" | `escalas-aceptacion.md` (los 5 estados) |
| Cerrar una sesión / pasarle el trabajo a otra | `plantillas/handoff-sesion.md` + `bitacora-sesiones.md` |
| Ver a qué dimensión apunta un trabajo | `dimensiones-juego.md` |
| Publicar un build, demo o parche | `roles/05-release-distribucion.md` |
| Escribir las notas de una entrega | `roles/05-release-distribucion.md` §2 |
| Registrar una lección aprendida | `conocimiento/README.md` |
| Proponer un cambio al framework o a una decisión de diseño aprobada | `plantillas/propuesta-cambio.md` |
| Entregar trabajo que requiere una herramienta que el agente no puede usar | `plantillas/ficha-recurso-manual.md` |
| Registrar un bug, una auditoría o un hallazgo | `higiene-de-trabajo.md` §1 y §2 |
| Escribir un commit o integrar trabajo de otro agente | `higiene-de-trabajo.md` §3 |
| Planificar trabajo amplio en tajadas chicas | `roles/` correspondiente + `00-estado-produccion.md` hitos |

## Reglas del router

1. **Existir no significa estar disponible.** Que un documento, skill, motor o herramienta exista en el repo **no significa que esté instalado, con cuenta activa o editor conectado**. Antes de proponer un flujo, el agente inspecciona la capacidad real en el entorno.
2. **Empezar por el entregable, no por la herramienta.** Primero: "¿qué resultado necesita el creador ahora?". Después: "¿con qué lo hago?".
3. **Un trabajo puede cruzar varios documentos.** Diseñar una mecánica usa rol 02 + plantilla de subsistema + banco-visual + dimensiones. Se leen todos los que aplican, no el primero que aparece.
4. **Si no hay documento para la necesidad, se registra el hueco** en `ciclo-produccion.md` §Qué falta definir. No se improvisa una estructura nueva en silencio.

## Planificar: entregables, no llamadas a herramientas

Cuando hay que planificar trabajo amplio:

- **Un resultado pedido = una frase.** Si no se puede escribir en una frase, el resultado no está definido.
- El plan se escribe **alrededor de entregables**, no de pasos de herramienta: para cada etapa, nombrar su **salida** y **la observación que demostrará que funciona**.
- **Separar lo obligatorio de lo opcional** (MVP vs. Beyond, como en `00-estado-produccion.md`).
- Respetar scope, presupuesto, choices de herramienta y restricciones de reinicio del creador.
- **Solo se pide información que cambie materialmente el trabajo.** Si falta un dato pero hay trabajo independiente preparable, se prepara mientras se espera.
- **Gate de compresión antes de ejecutar:** antes de construir, el agente **repite el plan en sus propias palabras** y espera señal de OK. Cuesta dos líneas y detecta el malentendido antes de gastar una sesión construyendo la cosa equivocada. *(Refuerzo del hallazgo de tanda-04: pedir el juego entero en un solo prompt produce menús rotos y objetos volando.)*
- El plan vive en el juego (`00-estado-produccion.md`), no en el chat. Se actualiza cuando la evidencia cambia el enfoque.

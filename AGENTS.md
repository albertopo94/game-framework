# AGENTS.md — Gobernanza de agentes de IA

Protocolo para agentes de IA que trabajan en este repositorio.

## Niveles de autonomía

1. **Autonomía Normal (Ejecución Fluida):** Tareas reversibles — investigación, análisis de referentes, borradores de diseño, documentación, exploración de herramientas — se ejecutan sin pedir confirmación en cada micro-paso.
2. **Aprobación Creativa (Checkpoints):** Validación humana explícita antes de:
   - El concepto/pitch de un juego nuevo.
   - Decisiones de diseño estructurales (mecánicas núcleo, género, target).
   - Cambios de alcance o de herramientas de un juego en producción.
3. **Confirmación Obligatoria de Operaciones Sensibles:** Detención obligatoria antes de:
   - Publicar un juego o demo en cualquier plataforma.
   - Consumir créditos, comprar assets o incurrir en costos.
   - Ejecutar operaciones destructivas (borrar trabajo, reescribir historial).
4. **Regla de N Alternativas:** Para decisiones creativas clave (nombres, conceptos, mecánicas núcleo, dirección de arte), presentar opciones fundamentadas antes de decidir.
5. **Cambio de estructura = propuesta primero:** tocar `_framework/` (reglas, roles, plantillas, dimensiones) o revertir una decisión de diseño aprobada requiere antes una **propuesta de cambio** (`_framework/plantillas/propuesta-cambio.md`) con su bloque de “qué dejo afuera a propósito”.
6. **Nunca se pide el proyecto entero en un solo paso:** el agente ejecuta **una tarea chica, la verifica, y sigue**. Un entregable que no cabe en una tarea verificable está mal cortado (ver Protocolo de Sesión). El prompt maestro define el contrato; no es una orden de construir todo.
7. **Traspaso de herramientas sin acceso (paquete listo, nunca instrucciones abstractas):** cuando una acción requiere una herramienta que el agente no puede ejecutar (UI manual, login, software de escritorio, interfaz web), el agente **no delega la tarea: entrega el paquete terminado para un clic**. Ficha obligatoria por recurso en `_framework/plantillas/ficha-recurso-manual.md`. Prohibido arrojar listas de prompts sin clasificar o instrucciones del tipo "hacé unos prompts bonitos".

## Agnosticidad

- Ningún agente debe asumir engine, middleware o herramientas: cada juego las declara en su estado de producción.
- Godot, Unity y Blender son candidatas privilegiadas, no un estándar impuesto.

## Disciplina transversal (heredada de las tandas del creador)

- **Referencia declarada antes de evaluar:** todo juego declara en su estado de producción 1-3 juegos reales como referencia de calidad/balance/feel. Ningún "se ve AAA" o "está pulido" es un criterio: el criterio es el comparado explícito contra la referencia.
- **Crítico independiente y estricto:** la validación de calidad visual/gameplay la hace un agente (o persona) distinto del que produjo, con mandato explícito de ser duro, usando comparativa side-by-side contra la referencia declarada. Si no supera la referencia, se itera; no se "aproxima".
- **Descomposición por subsistema:** builds grandes se dividen en subsistemas independientes (movimiento, tiro, armas, audio, UI...) con dueño propio; se integra y se valida por subsistema, no todo de una vez.
- **No automatizar prematuramente:** no desarrollar herramientas de orquestación complejas, bots de pipeline ni scripts de automatización de agentes antes de completar manualmente con éxito un **primer juego piloto completo**. El foco actual es validar el flujo y las capacidades reales del entorno.
- **Scope es ley:** el scope se fija en Diseño. No se expande en Producción. Si surge algo que merece, se registra como idea en cola y se decide en el siguiente ciclo de planificación.
- **Commits pequeños y jugables:** el repo de cada juego debe estar siempre en estado ejecutable.
- **Nunca binarios al repo** de trabajo (ver .gitignore).

## Estado persistente

- Todo juego en `mis-juegos/` mantiene su archivo de estado de producción actualizado; es la primera lectura al retomar cualquier trabajo.
- **Todo el contexto vive en el proyecto, no en la memoria del chat:** imágenes de referencia, prompts aceptados, decisiones y estados se guardan en las carpetas del juego. Cada iteración es más barata porque la anterior está en disco; una memoria de chat que no se puede versionar no existe.
- **Sin bloqueos silenciosos:** si el agente queda esperando una aprobación o una acción del creador, lo dice al momento y sigue preparando lo que pueda en paralelo. Esperar sin avisar gasta tiempo del proyecto.
- Los hallazgos (bugs, auditorías, deudas) se registran como tracker padre + un ítem por fix, y solo se arreglan hallazgos **confirmados** por revisión independiente: ver `_framework/higiene-de-trabajo.md`.
- Este framework está en construcción: los roles y plantillas se definen con el conocimiento del creador, no se inventan.

## Protocolo de Sesión (1 feature = 1 sesión)

> **Origen:** idea del creador. Destilada de la práctica: a más largo un chat, más se degrada el contexto (el agente pierde detalles, mezcla decisiones viejas con nuevas). Un chat fresco + un buen estado persistente recupera más de lo que se pierde al cambiar.

### Regla principal

**Una sesión = una feature.** Feature = una tajada verificable del juego: se completa en una sesión, tiene evidencia concreta (gate superado, commit jugable) y mapea a 1-N dimensiones/subsistemas. Si no cabe en una sesión, está mal cortada: se divide, no se alarga el chat.

### Disparador de cierre por degradación de contexto

**Si antes de terminar la feature el contexto del chat se degrada**, la sesión se cierra con handoff aunque la feature no haya llegado al gate.

Señales de degradación (cualquiera basta para cerrar):

- El agente **repite preguntas** que ya respondió en la misma sesión
- El agente **mezcla decisiones viejas** con la tarea actual (usa referencias de una feature anterior como si fueran de la actual)
- El agente **no recuerda** un entregable que acaba de validar en el chat
- El medidor interno del agente (si lo tiene) indica que el thread está impactando calidad
- El creador nota que el agente **responde más lento, más vago o más genérico**

**La regla:** cerrar antes que alargar. Un handoff limpio recupera; un chat degradado contamina lo que viene. *(Origen: changelog de asistente comercial para motores — 07/29/2025 "threads largos no son recomendados; empezar thread nuevo al cambiar de tarea" + 01/06/2026 medidor de impacto del tamaño del thread en calidad de respuesta)*

### Obligatoriedades del agente

1. **Al terminar o pausar una feature** (incluido a mitad de camino), el agente **debe avisar** al creador: *"feature X completada/pausada; recomendá una nueva sesión para Y (o para lo que quieras)"*. Es una recomendación, no una obligación: el creador puede hacer un follow-up chico en la misma sesión si lo desea.
2. **Antes de avisar**, el agente deja el traspaso completo en los tres lugares de abajo y **nunca** depende del chat para que la próxima sesión sepa qué hacer.
3. **Al iniciar una sesión en un juego**, el agente lee en este orden: handoff abierto (si existe) → `00-estado-produccion.md` → última línea de `bitacora-sesiones.md` → verifica físicamente los entregables (completar casillas no equivale a haber demostrado el resultado).

### Traspaso entre sesiones (dos archivos + handoff)

- **`00-estado-produccion.md` = instantánea de verdad.** Fase actual, hitos con su estado en la escalera de aceptación, siguiente acción permitida, decisiones registradas, bloqueantes. Lo que hay que leer para continuar ahora.
- **`bitacora-sesiones.md` = historial.** Quién (sesión), cuándo, qué feature, qué se hizo, con qué evidencia, y qué se deja pendiente. Lo que hay que leer para entender cómo se llegó hasta acá.
- **Handoff (plantilla `plantillas/handoff-sesion.md`)**: el traspaso detallado, obligatorio cuando la sesión deja trabajo abierto. Contiene los 5 estados de `escalas-aceptacion.md` por separado, propiedad de archivos compartidos y la siguiente acción exacta. Las sesiones cerradas limpian; las abiertas dejan handoff.

La bitácora **resume** el traspaso; el estado lo **contiene** completo; el handoff lo **detalla**. Si hay conflicto entre ambos, el estado manda y la bitácora se corrige en la próxima sesión.

### Formato de la bitácora de sesiones

Una línea por sesión (no notas largas):

```markdown
| Fecha | Sesión | Feature | Resultado | Evidencia | Pendiente para la próxima sesión |
```

- **Sesión (id):** lo genera **Pi**, es el identificador estable que permite retomar esa sesión concretamente si se desea en otro momento (ej. `2026-10-25-a`). No lo inventa el agente de IA: lo genera el runtime.
- **Feature:** la tajada de esa sesión, con la dimensión/subsistema que mapea (ej. "5 — bucle y controles: dash").
- **Resultado:** `completado` / `pausado` / `en curso` / `abandonado`.
- **Evidencia:** commit, gate superado, archivo creado, comparativa contra referente.
- **Pendiente:** la siguiente acción exacta, para que la próxima sesión no tenga que deducirla.


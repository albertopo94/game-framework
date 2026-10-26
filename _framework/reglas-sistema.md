# Reglas del Sistema

Reglas operativas para agentes. Se expanden con el conocimiento del creador.

> **Este documento tiene un tope y las reglas mueren.** Leer §Cómo se escribe, cuánto mide y cómo muere una regla antes de agregar nada.

## Reglas heredadas del YouTube Creator Hub (aplican igual)

1. **Regla de N Alternativas** para decisiones creativas clave: nombre, concepto, mecánicas núcleo, dirección de arte, dirección de marketing.
2. **Autonomía proporcional al riesgo**: reversible = fluido; irreversible o con costo = confirmar.
3. **Trazabilidad legal**: todo asset (música, modelos, fuentes, code de terceros) registra licencia exacta y atribución.
4. **Puerta de originalidad**: no clonar; referentes inspiran, el producto aporta valor propio.

## Reglas propias de desarrollo de juegos (borrador, a confirmar con el creador)

- **Playtest antes de polish**: ningún sistema se pule antes de ser jugable y jugado.
- **Enfoque antes que herramienta:** un mal resultado se atribuye primero al enfoque (descomposición incorrecta, flujo equivocado, herramienta mal configurada) y solo después a la herramienta. Antes de descartar un generador, se prueba con el flujo correcto: evaluar una herramienta con un flujo torpe da falsos negativos. *(Origen: `_framework/referencias/notas-creador/tanda-05-workflow-3d-ai.md`; ver `produccion-assets.md`)*
- **Preguntar la práctica antes de pedir la tarea:** además de qué se quiere, el agente consulta cómo se hace usualmente eso, cuáles son las buenas prácticas y qué enfoque usar. La experiencia del creador y del proyecto **multiplica** la eficacia del agente; el agente también la invoca en vez de asumirla.
- **Greybox antes de arte**: la mecánica se prueba con cubos y geometría provisoria **antes** de producir arte definitivo. Si no es interesante con cubos, no lo va a ser con arte bonito. El arte no salva una mecánica débil. *(Origen: `_framework/referencias/notas-creador/tanda-04-agente-y-steam.md`, corroborado por la práctica de greybox común en la industria)*
- **Scope es ley**: el scope se define en diseño y solo el humano lo expande.
- **Commits pequeños y jugables**: el repo de cada juego debe estar siempre en estado ejecutable.
- **No automatizar prematuramente**: no desarrollar herramientas de orquestación complejas, bots de pipeline ni scripts de automatización de agentes antes de completar manualmente con éxito un **primer juego piloto completo**. El foco actual es validar el flujo y las capacidades reales del entorno. *(Origen: adaptación de la regla homónima del YouTube Creator Hub)*
- **Nunca binarios al repo** de trabajo (ver .gitignore).
- **Referencia declarada antes de evaluar:** todo juego declara en su estado de producción 1-3 juegos reales como referencia de calidad/balance/feel. Ningún "se ve AAA" o "está pulido" es un criterio: el criterio es el comparado explícito contra la referencia.
- **Critic independiente y estricto:** la validación de calidad visual/gameplay la hace un agente (o persona) distinto del que produjo, con mandato explícito de ser duro, usando comparativa side-by-side contra la referencia declarada. Si no supera la referencia, se itera; no se "aproxima".
- **Descomposición por subsistema:** builds grandes se dividen en subsistemas independientes (movimiento, tiro, armas, audio, UI...) con dueño propio; se integra y se valida por subsistema, no todo de una vez. *(Origen: destilación de `referencias/notas-creador/tanda-01-fps-aaa.md`)*
- **Estética fijada por referencia visual, no por adjetivos:** para fijar la identidad visual de un juego, la referencia es un **vídeo, imagen o juego real** que se muestra al agente. "Bonito", "retro" o "pixel art" por sí solos no son especificaciones: son adjetivos. La referencia visual es la fuente primaria. *(Origen: destilación de `referencias/notas-creador/tanda-02-prompt-creacion.md`)*
- **Preferencia por assets handcrafted sobre procedural:** por defecto, los assets (sprites, efectos, modelados) se hacen **a mano / handcrafted**, no procedurales. Lo procedural solo se usa cuando se pide explícitamente o cuando no existe alternativa handcrafted que resuelva la misma necesidad. "Hecho en Canvas" y "juego genérico" son resultados prohibidos por defecto. *(Origen: destilación de `referencias/notas-creador/tanda-02-prompt-creacion.md`)*
- **Mapas/niveles no procedurales por defecto:** mismo criterio que los assets — un mapa generado proceduralmente sin pedido explícito es resultado prohibido. La excepción se declara y justifica en el estado de producción. *(Origen: destilación de `referencias/notas-creador/tanda-03-dimensiones-juego.md`; ver `dimensiones-juego.md` #4)*
- **Dimensiones como unidad de validación:** todo juego declara qué dimensiones de `dimensiones-juego.md` aplican; los gates de fase y las comparativas contra referentes se hacen por dimensión activa, no globalmente. *(Origen: tanda 3)*
- **Corrección dirigida:** ante un resultado defectuoso, se identifica primero el defecto principal y su origen (referencia, prompt, parámetros o método) y se corrige ese elemento antes de reevaluar. **Prohibido reiniciar el diseño entero sin motivo**; la revisión debe ser la más pequeña útil. *(Origen: destilación de `mr-mak-workspace`; hermana de la regla del mismo nombre del YouTube Creator Hub)*
- **No inventar preferencias del creador:** si falta una preferencia, gusto o decisión del creador, se pregunta; no se inventa una biografía ni un gusto por defecto. Lo que no está en `conocimiento/`, en el juego o en sus notas no existe. *(Origen: destilación de `mr-mak-workspace`)*
- **El handoff es el input de arranque:** una sesión nueva empieza leyendo el handoff de la sesión anterior (si quedó trabajo abierto), además de `00-estado-produccion.md` y `bitacora-sesiones.md`. El traspaso vive en disco, nunca en la memoria del chat. *(Origen: destilación de `mr-mak-workspace`; ver `plantillas/handoff-sesion.md`)*
- **Separar ejecución de aceptación:** "el job se envió", "el build se preparó", "el agente lo verificó" son frases incompletas. Cada resultado se declara con su estado en la escalera de aceptación (`escalas-aceptacion.md`); ninguna de esas tres frases equivale a "entregado" ni a "aprobado". *(Origen: destilación de `mr-mak-workspace`)*

## Cómo se escribe, cuánto mide y cómo muere una regla

Una lista de reglas que solo crece deja de ser una lista y pasa a ser decorado. Este documento tiene tres controles: redacción, presupuesto y retiro.

### 1. Redacción

Una regla se escribe como instrucción a un miembro nuevo del equipo, no como valor declarado.

| Requisito | Regla que cumple | Regla que NO cumple |
| :--- | :--- | :--- |
| **Verbo decisivo + objeto concreto** | "Ningún binario al repo de trabajo." | "Escribí buen código." |
| **La violación es observable** | "Ningún gate de fase cierra sin comparativa side-by-side contra la referencia declarada." | "Poné esfuerzo en la calidad." |
| **Afirmativa, con el caso bueno descripto** | "Por defecto los assets son handcrafted; lo procedural se pide explícito." | "Evitá assets feos o genéricos." |
| **Con ejemplo real cuando el criterio es de forma** | "Referencia visual = vídeo, imagen o juego real mostrado." | "Tené buen gusto visual." |

- **Test mínimo:** si no se puede escribir una frase que describa cómo se ve **violar** la regla, eso no es una regla: es una preferencia. Va a `conocimiento/` o se pregunta.
- **Sin contraejemplos sueltos.** Describir el patrón incorrecto le da algo concreto para imitar; se describe el patrón correcto.
- **La condición no vive en la regla.** Si una regla empieza con "si…", la mayoría de las veces la condición pertenece al router (`ruta-produccion.md`) o al juego (`00-estado-produccion.md`), y la regla queda incondicional. Excepción legítima: la regla cuyo objeto **es** la condición (ej. autonomía proporcional al riesgo).
- **Sin contradicciones.** Ante dos reglas que chocan, se resuelve **ahora** y se deja escrito cuál manda; no se deja que el agente elija en cada sesión.
- **Toda regla cita su origen** (tanda, `conocimiento/`, práctica propia). Una regla sin origen no se agrega.

### 2. Presupuesto

- **El tope lo pone la atención del agente, no la paciencia del creador.** Cada regla compite con las otras 22 por el mismo contexto: cuanto más larga la lista, más reglas se cumplen por suerte.
- **Agregar una regla es una decisión del creador** (idéntico a promocionar una `regla-candidata`), y al proponerla **se nombra qué otra se revisa**: se retira, se fusiona, o se explica por qué ninguna.
- **Fusionar antes que acumular.** Varias reglas del mismo origen y el mismo objeto se escriben como una con incisos. *(Ejemplo real de este archivo: "assets handcrafted por defecto" y "niveles no procedurales por defecto" son una regla con dos objetos.)*
- **Lo específico del juego no sube acá.** Una restricción de un juego va en su `00-estado-produccion.md`; si se repite en tres juegos, recién ahí es candidata a regla del sistema.

### 3. Retiro

**Una regla puede estar equivocada y hay que poder decirlo.** La evidencia de retiro es una regla que se violó **por seguirla**, no una que molestó.

| Señal de retiro | Qué se hace |
| :--- | :--- |
| La práctica de un juego la contradice | Se pasa a `RETIRO` con fecha, evidencia y qué la reemplaza |
| Está fusionada en otra | Se marca `RETIRO` apuntando a la regla que la absorbió |
| Depende de algo que ya no existe (herramienta, motor, límite del piloto) | Se marca `RETIRO` con el motivo |
| Nadie la viola porque nadie la lee | Candidata a fusión o a bajar de categoría |

- **No se borra: se marca.** El texto retirado queda visible con `~~tachado~~` + `RETIRO (fecha, motivo)` — la trazabilidad manda sobre la limpieza (ver `higiene-de-trabajo.md`).
- **Retirar también es decisión del creador.** Un agente propone el retiro con la evidencia; no auto-retira.
- **Revisión obligatoria tras el primer piloto.** Hoy el documento tiene **23 reglas** y ninguna violada todavía: sin juego real, ninguna fue tensada. Al cerrar el piloto se revisa la lista completa: qué reglas se cumplieron solas, cuáles se violaron, cuáles nadie usó. Eso, no la intuición, decide qué se va.

### 4. Cómo se promueve (recap)

`conocimiento/` (`regla-candidata`) → **el creador aprueba** → entra acá con origen, redacción según §1 y **hueco nombrado** según §2. Al subir, se parte la entrada: **el hecho** queda como referencia y **el procedimiento** va a su documento (ver `_framework/README.md` §Referencia o procedimiento). La promoción no borra la entrada original: queda como historial enlazado.

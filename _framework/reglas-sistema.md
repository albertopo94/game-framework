# Reglas del Sistema

Reglas operativas para agentes. Se expanden con el conocimiento del creador.

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

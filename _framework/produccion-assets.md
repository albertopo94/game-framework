# Producción de Assets con Agentes 🧱

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-05-workflow-3d-ai.md` (video de un artista 3D profesional que sí construyó su demo, **pero patrocinado**: recomienda plataformas concretas; los nombres de productos llegaron deformados por la transcripción). Las prácticas estructurales se portan; **ningún producto nombrado entra como herramienta del framework**.
> **Verificación:** cada afirmación de capacidad se confirma o descarta practicando en un juego real, y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.

## Regla central: descomponer el asset como se descompone el código

La descomposición por subsistemas (`AGENTS.md`) aplica igual a un asset:

- **Un personaje o un escenario se genera por piezas y se combina**: un árbol = tronco + base + ramas + hojas (estas como planos con textura alpha). Un personaje = cuerpo + accesorios separados.
- El generador que recibe la pieza completa rinde mejor que el que recibe el objeto entero, y las piezas separadas conservan control posterior: animación, lógica, accesorios que se ponen y sacan.
- **"Generar todo junto y quejarse del resultado" es un error de enfoque, no del modelo.** Antes de juzgar una herramienta, se evalúa con el flujo correcto.

## Regla: la representación más simple que cumple el propósito visual

No toda superficie necesita geometría. Una pared o un piso de piedra puede ser **una textura tileable** con mapa de desplazamiento, no una generación de malla por bloque. La pregunta en Producción de assets es siempre: *¿qué representa esto mismo con menos peso de runtime y menos trabajo?* (coherente con el presupuesto de rendimiento de `dimensiones-juego.md`).

## Regla: el remate humano es trabajo planificado, no fracaso

- La generación llega lejos (el patrón observado: ~80-90 % del resultado) y **el último tramo es edición humana**: arreglar topología, pesos de rig, texturas finales. Eso es agenda de producción, se presupuesta.
- **La tasa de fallo es parte del plan**: una fracción de generaciones (orden 10-20 % incluso con las mejores herramientas) va a fallar y se rehace a mano. Un pipeline que no presupuesta ese retrabajo está mal planificado.
- Corolario de capacidad: **saber ~10 % de la herramienta de arte rematadora** (ajustar forma, loops, pesos, textura puntual) multiplica el rendimiento del flujo generado. El framework no reemplaza ese criterio: el creador lo ejerce o lo delega con ojos de supervisor.

## Regla: el agente como orquestador de generadores especializados

Para audio (y análogo para otras familias de assets), el patrón que se propone es: **el agente no "crea" el asset con el LLM; invoca generadores especializados vía API y elige el modelo adecuado**, itera y presenta opciones. La calidad del resultado depende del generador correcto, no del modelo de lenguaje que lo pide.

- Cada generador especializado que se incorpore entra al catálogo con visto bueno del creador (`herramientas-y-apis.md`).
- El agente **no genera música/arte directamente con el LLM** cuando existe un generador especializado disponible: ese es el pattern repetido del video con resultado "sorprendentemente ajustado".

## Dead-ends declarados (hipótesis al momento de la fuente; re-verificar)

| Tarea | Estado declarado por la fuente |
| :--- | :--- |
| Cabello realista por tipo "hair cards" generado | Callejón sin salida: base comprada/licenciada + edición encima |
| Rigging de animales y props dinámicos | Prácticamente sin solución útil; rig custom a mano |
| Huesos físicos de cabello, ajustes finos de pesos | Requiere revisión humana, inevitable |
| Activos "entidad de juego" (agua, lo que tiene lógica/partículas) | No son props: son sistemas con lógica; se tratan como código, no como asset generado |
| Materiales PBR finales | Lo generado es "promedio"; remate humano encima o no es professional-grade |

**Regla de lectura:** esta tabla es una foto de un momento. Una dead-end de hoy puede no serlo en seis meses: se re-verifica cuando un juego lo necesite, y el resultado va a `conocimiento/` con fecha.

## Donde encaja con el resto del framework

- `reglas-sistema.md`: corrección dirigida (arreglar la pieza defectuosa, no reiniciar el asset), referencia visual primero.
- `escalas-aceptacion.md`: un asset generado está en estado 3 cuando corre en el motor; el remate humano y la aceptación del creador son los estados 4 y 5.
- `herramientas-y-apis.md`: los generadores concretos entran por ahí, evaluados contra los criterios de selección, nunca desde este documento.
- `dimensiones-juego.md` #3: este documento es el "cómo" de la dimensión de assets.
- `montaje-de-niveles.md`: consume las piezas que este documento produce; comparte "pregunta de camino" y presupuesto de rendimiento.

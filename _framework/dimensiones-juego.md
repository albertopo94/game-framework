# Dimensiones de un Juego 🎯

> **Origen:** destilación de `referencias/notas-creador/tanda-03-dimensiones-juego.md`.
> **Uso:** checklist transversal. Todo juego declara en su `00-estado-produccion.md` qué dimensiones aplican y cuál es el target de calidad de cada una contra sus referentes. Ningún gate de fase cierra sin revisar las dimensiones activas.

## Las 7 dimensiones

| # | Dimensión | Qué cubre | Fase donde se fija | Fase donde se valida |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Concepto original** | Idea núcleo, promesa de gameplay, diferenciador vs. referentes | Concepto | Concepto (gate), Prototipo |
| 2 | **Dirección de arte** | Estilo visual, paleta, tipografía, coherencia estética; fijada por referencia visual (ver `reglas-sistema.md`) | Diseño | Vertical Slice, QA |
| 3 | **Recursos (assets) y sprites** | Sprites, modelos, texturas, efectos, audio — handcrafted por defecto, procedural solo si se pide explícitamente. Cómo producirlos con agentes (descomponer por piezas, remate humano presupuestado, dead-ends): `produccion-assets.md` | Producción | QA |
| 4 | **Mapas / niveles** | Layout, progresión, densidad de contenido. **No procedurales por defecto** salvo pedido explícito | Diseño + Producción | Playtest, QA |
| 5 | **Bucle (loop) y controles** | Core loop, respuesta al input, feel de movimiento, ergonomía de controles. Incluye el **juice** (sacudida de pantalla, destello de impacto, números de daño, retroalimentación sensorial): es parte del feel, no decoración | Prototipo (greybox, sin juice) | Prototipo (gate "¿es divertido?"), QA |
| 6 | **Combate y profundidad** | Sistemas de conflicto, balance, curva de dificultad, capas de maestría | Diseño | Vertical Slice, playtests |
| 7 | **Entrega al usuario** | Build final, store page, onboarding, UX de menús/settings, documentación, compliance de plataforma. Método: `roles/05-release-distribucion.md` | Release | Release (gate) |

## Reglas de uso

- **Greybox primero, juice después:** la dimensión 5 se valida **sin** arte ni juice (ver `reglas-sistema.md`). El juice se agrega una vez que el bucle funciona con cubos; así se sabe que lo divertido viene de la mecánica y no del efecto.
- **Presupuesto de rendimiento por asset:** la dimensión 3 declara límites medibles (polígonos por mesh, resolución de textura, costo de draw) y la QA los verifica en el motor. Un mesh que llega 10 veces sobre su presupuesto es un bug de asset, no un detalle estético. *(Origen del patrón: `_framework/referencias/notas-creador/tanda-04-agente-y-steam.md`.)*
- **Aplicabilidad variable:** no todas las dimensiones existen en todos los juegos. Un puzzle game puede no tener combate; un visual novel puede fusionar dirección de arte y narrativa. El juego declara cuáles aplican y cuáles se saltan, con justificación de una línea.
- **Target por dimensión, no global:** "se ve AAA" no es criterio (ver `reglas-sistema.md`). Cada dimensión activa tiene su referente y su comparativa side-by-side.
- **Una dimensión puede bloquear el gate de una fase:** si la dimensión 5 (bucle/controles) falla en Prototipo, el gate no pasa aunque las demás estén bien. La dimensión crítica depende del género y se declara en Concepto.
- **Descomposición por subsistema (tanda 1):** estas dimensiones son la unidad lógica de descomposición cuando se fan-outean subagentes. Una dimensión = un dueño = una validación independiente.

## Relación con otros documentos

- `ciclo-produccion.md`: los gates de cada fase revisan las dimensiones activas.
- `reglas-sistema.md`: referencia declarada, crítico independiente, handcrafted-first, mapas no procedurales por defecto.
- `plantillas/prompt-maestro-creacion.md`: el prompt maestro debe listar las dimensiones activas del proyecto.
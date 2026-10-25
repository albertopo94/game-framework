# Dimensiones de un Juego 🎯

> **Origen:** destilación de `referencias/notas-creador/tanda-03-dimensiones-juego.md`.
> **Uso:** checklist transversal. Todo juego declara en su `00-estado-produccion.md` qué dimensiones aplican y cuál es el target de calidad de cada una contra sus referentes. Ningún gate de fase cierra sin revisar las dimensiones activas.

## Las 7 dimensiones

| # | Dimensión | Qué cubre | Fase donde se fija | Fase donde se valida |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Concepto original** | Idea núcleo, promesa de gameplay, diferenciador vs. referentes | Concepto | Concepto (gate), Prototipo |
| 2 | **Dirección de arte** | Estilo visual, paleta, tipografía, coherencia estética; fijada por referencia visual (ver `reglas-sistema.md`) | Diseño | Vertical Slice, QA |
| 3 | **Recursos (assets) y sprites** | Sprites, modelos, texturas, efectos, audio — handcrafted por defecto, procedural solo si se pide explícitamente | Producción | QA |
| 4 | **Mapas / niveles** | Layout, progresión, densidad de contenido. **No procedurales por defecto** salvo pedido explícito | Diseño + Producción | Playtest, QA |
| 5 | **Bucle (loop) y controles** | Core loop, respuesta al input, feel de movimiento, ergonomía de controles | Prototipo | Prototipo (gate "¿es divertido?"), QA |
| 6 | **Combate y profundidad** | Sistemas de conflicto, balance, curva de dificultad, capas de maestría | Diseño | Vertical Slice, playtests |
| 7 | **Entrega al usuario** | Build final, store page, onboarding, UX de menús/settings, documentación, compliance de plataforma. Método: `roles/05-release-distribucion.md` | Release | Release (gate) |

## Reglas de uso

- **Aplicabilidad variable:** no todas las dimensiones existen en todos los juegos. Un puzzle game puede no tener combate; un visual novel puede fusionar dirección de arte y narrativa. El juego declara cuáles aplican y cuáles se saltan, con justificación de una línea.
- **Target por dimensión, no global:** "se ve AAA" no es criterio (ver `reglas-sistema.md`). Cada dimensión activa tiene su referente y su comparativa side-by-side.
- **Una dimensión puede bloquear el gate de una fase:** si la dimensión 5 (bucle/controles) falla en Prototipo, el gate no pasa aunque las demás estén bien. La dimensión crítica depende del género y se declara en Concepto.
- **Descomposición por subsistema (tanda 1):** estas dimensiones son la unidad lógica de descomposición cuando se fan-outean subagentes. Una dimensión = un dueño = una validación independiente.

## Relación con otros documentos

- `ciclo-produccion.md`: los gates de cada fase revisan las dimensiones activas.
- `reglas-sistema.md`: referencia declarada, crítico independiente, handcrafted-first, mapas no procedurales por defecto.
- `plantillas/prompt-maestro-creacion.md`: el prompt maestro debe listar las dimensiones activas del proyecto.
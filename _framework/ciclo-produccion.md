# Ciclo de Producción (Borrador)

Análogo al ciclo de producción de un video, aplicado a un juego. **Borrador — se ajusta con el conocimiento del creador.**

## Fases macro

1. **Concepto** — idea + mercado + referentes + pitch. Checkpoint humano: aprobar/derivar a estudio.
2. **Diseño** — GDD, mecánicas, sistemas, target, scope. Checkpoint humano: aprobar diseño.
3. **Prototipo** — jugable feo pero real. Gate: ¿es divertido? Si no, volver a Diseño o matar.
4. **Vertical Slice** — quality bar completa en miniatura. Gate: decide si sigue a producción.
5. **Producción** — construcción por hitos con estado persistente.
6. **QA / Cierre** — bugs, balance, performance, licencias, compliance de plataforma.
7. **Release** — store page, builds, distribución, lanzamiento.
8. **Post-release** — métricas, reviews, parches, contenido, live ops.

## Disciplina de alcance (Scope)

- El scope se fija en **Diseño** (fase 2). No se expande en Producción.
- Si una idea surge en Producción que merece, se registra como **idea en cola** en `ideas.md` o en el backlog del juego (plantilla pendiente) y se evalúa en el siguiente ciclo de planificación.
- "Scope creep" es la causa número 1 de muerte de juegos indie. No se negocia en silencio: se registra y se decide.

## Gates y dimensiones

Cada gate revisa las **dimensiones activas** del juego (ver `dimensiones-juego.md`), no el juego en bloque:

| Fase / Gate | Dimensiones que cierran el gate |
| :--- | :--- |
| Concepto (checkpoint) | 1 Concepto original |
| Prototipo ("¿es divertido?") | 5 Bucle y controles (crítica en este gate) |
| Vertical Slice ("¿sigue a producción?") | 2 Dirección de arte, 6 Combate y profundidad, y las activas restantes |
| QA / Cierre | 3 Assets, 4 Mapas, 5 Bucle, 6 Combate — todas las activas, comparadas side-by-side contra sus referentes |
| Release (gate) | 7 Entrega al usuario |

Una dimensión activa que falla bloquea el gate, aunque el resto esté bien.

**Ningún gate cierra en estado 4 (verificado por el agente).** Todo gate exige estado 5: aceptación explícita del creador (ver `escalas-aceptacion.md`). Un gate cerrado en 4 es un gate mal cerrado.

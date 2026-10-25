# Ciclo de Producción (Borrador)

Análogo al ciclo de producción de un video, aplicado a un juego. **Borrador — se ajusta con el conocimiento del creador.**

## Fases macro

1. **Concepto** — idea + mercado + referentes + pitch. Checkpoint humano: aprobar/derivar a estudio.
2. **Diseño** — GDD, mecánicas, sistemas, target, scope. Checkpoint humano: aprobar diseño.
3. **Prototipo (greybox)** — jugable feo pero real: cubos, sin arte definitivo. Gate: ¿es divertido? Si no, volver a Diseño o matar. **Prohibido producir arte definitivo antes de pasar este gate.**
4. **Vertical Slice** — quality bar completa en miniatura. Gate: decide si sigue a producción.
5. **Producción** — construcción por hitos con estado persistente.
6. **QA / Cierre** — bugs, balance, performance contra el presupuesto declarado, licencias, compliance de plataforma (política leída en la fuente oficial ese día: ver `roles/05-release-distribucion.md` §5).
7. **Release** — store page, builds, distribución, lanzamiento.
8. **Post-release** — métricas, reviews, parches, contenido, live ops.

## Lead times no técnicos (arrancan antes de lo que parece)

La publicación tiene trámites con tiempos de espera que **no dependen de que el juego esté listo**. Descubrirlos en la fase Release cuesta semanas de calendario perdidas. En cada juego se listan en su `00-estado-produccion.md` con su duración aproximada y cuándo hay que iniciarlos:

- Cuentas de tienda/distribución, verificación de identidad y datos fiscales/bancarios (los procesos de verificación de terceros pueden tardar semanas).
- Períodos de espera obligatorios tras el pago o tras la creación de la cuenta antes del primer lanzamiento.
- Ventanán de página de tienda visible tipo “próximamente” para acumular deseo antes del lanzamiento.
- Revisión de la plataforma del build y de la página antes de publicar.

**Regla:** se planifican en Diseño (fase 2), no en Release. Son camino crítico de calendario aunque no lo sean de producción. Los valores concretos de cada tienda se **verifican en la fuente oficial al momento de usarlos** (cambian; ver `conocimiento/README.md`: los datos de terceros sin verificación no son reglas).

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

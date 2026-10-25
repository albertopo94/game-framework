# Plantilla: Mecánica por Subsistema

> **Uso:** cada subsistema/mecánica del juego se documenta con este formato. No es un GDD monolítico: cada subsistema es un archivo independiente que se actualiza con el conocimiento real.
> **Origen:** formato destilado del Mass Flux GDD (ficha en `referencias/README.md`) — cada mecánica allí (Walls, Spikes, Holes, Fruit) tiene nombre, tipo, mockup y descripción.

## Formato

```markdown
# Mecánica: <nombre>

## Tipo
- Primaria / Secundaria / Opcional
- ¿Qué dimensión del juego mapea? (ver `_framework/dimensiones-juego.md`)

## Descripción
Una frase sobre qué hace esta mecánica. Concreta, sin adjetivos.

## Regla del juego
- ¿Cómo interactúa con el jugador?
- ¿Qué le pasa al jugador / al estado del juego?
- ¿Cuáles son las condiciones de éxito, fracaso y empate?

## Dependencias
- ¿Qué otras mecánicas o subsistemas requiere?
- ¿Con qué interactúa?

## Mockup / Referencia visual
- ¿Hay un mockup, captura o juego de referencia que muestre esta mecánica?
- Si no hay, se marca como `pendiente` y se pide al creador o se busca.

## Equilibrio / Edge cases
- ¿Qué rompe esta mecánica?
- ¿Qué situaciones de borde hay que considerar?

## Estado
- [ ] No diseñada
- [ ] Diseñada (documentada, sin prototipo)
- [ ] Prototipada (jugable, no balanceada)
- [ ] Balanceada (playtest, ajustada)
- [ ] Integrada (en el juego, validada)
```

## Ejemplo (Mass Flux — no es un juego nuestro, solo muestra el formato)

```markdown
# Mecánica: Fruit

## Tipo
- Primaria
- Mapea a dimensión 6 (Combate y profundidad) — en este caso, profundidad de rompecabezas

## Descripción
El jugador come una fruta y genera una nueva celda en el lado opuesto de la masa.

## Regla del juego
- Si una celda del jugador camina sobre una fruta, la fruta se consume.
- Se crea una nueva celda en el lado opuesto de la masa respecto a la celda que comió.
- La nueva celda hereda el estado de la celda origen.

## Dependencias
- Mecánica de movimiento colectivo
- Mecánica de independencia (si la masa se separa)

## Mockup / Referencia visual
- Mockup animado en el GDD original (pendiente en nuestro framework)

## Equilibrio / Edge cases
- ¿Qué pasa si la fruta se come desde un extremo y la masa tiene solo una celda?
- ¿Qué pasa si la nueva celda se genera sobre un spike o un agujero?

## Estado
- [ ] No diseñada
```

## Relación con la escalera de aceptación

El estado de arriba (No diseñada → Integrada) mide **madurez de la mecánica**. La escalera de `escalas-aceptacion.md` mide **quién la validó**. Son ortogonales: una mecánica `Integrada` puede seguir en estado 3 de la escalera (funciona, pero nadie la aceptó). La mecánica no está terminada hasta estado 5.

## Reglas de uso

- **Una mecánica = un archivo.** No se amontonan en un GDD monolítico.
- **Una mecánica puede bloquear un gate.** Si falla en Prototipo, el gate no pasa aunque las demás estén bien.
- **Cada mecánica tiene su own dueño** (subagente o persona) y se valida independientemente contra su referente.
- **El estado de cada mecánica se refleja en `00-estado-produccion.md`.**
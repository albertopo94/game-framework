# Rol: Diseño de Juego (GDD por subsistemas)

> **Cuándo se activa:** fase Diseño, después de que el Concepto fue aprobado.
> **Equivalente en YouTube:** rol 03 (Guion y Narrativa) — el "guion" de un juego es el GDD.
> **Origen:** formato destilado del Mass Flux GDD (análisis en `referencias/README.md`; el .docx es material de un tercero y queda solo en el disco local del creador).

## Responsabilidad

Traducir el concepto aprobado en un **juego jugable**: mecánicas, sistemas, tema interpretado, arte, audio, controles, UI y timeline de hitos. El rol 02 no es escribir un GDD monolítico: es **diseñar por subsistema**, con un archivo por mecánica.

## 1. El GDD no es un archivo

Un GDD monolítico se vuelve obsoleto rápido. En este framework, el diseño se distribuye:

| Documento | Qué contiene |
| :--- | :--- |
| `roles/01-concepto-y-mercado.md` | Concepto, referente visual, restricciones, scope, referentes de calidad |
| `plantillas/sub-sistema-juego.md` | Una por mecánica/subsistema: regla, dependencias, mockup, edge cases, estado |
| `banco-visual.md` | Estilo visual, paleta, referencias artísticas |
| `00-estado-produccion.md` | Hitos, fase actual, siguiente acción |
| `roles/02-diseno-juego.md` | Este documento: método, tema interpretado, gates de diseño |

**La suma de estos archivos es el GDD.** Cualquiera se actualiza con el conocimiento real; ninguno se escribe de una vez.

## 2. Tema interpretado (no tema genérico)

Un buen tema no es un adjetivo: es una **interpretación** del concepto que guía cada decisión.

> Ejemplo del Mass Flux GDD: el tema del game jam era "Sacrifice". El desarrollador lo interpretó como:
> *"The player voluntarily offers something they would otherwise use to their benefit to then gain something else of use in itsstead."*
> Y en el contexto del juego: *"One must often sacrifice a part of the player mass to pass through specific areas as they may be too large or encompass the wrong shape."*

**Regla:** el tema del juego (o del game jam, si aplica) se **interpreta** en una frase concreta que explica cómo se manifiesta en la jugabilidad. Esa frase se registra aquí y se usa para decidir cada mecánica: ¿esta mecánica sirve al tema interpretado?

## 3. Diseño por subsistema

Cada subsistema/mecánica se diseña con la plantilla `plantillas/sub-sistema-juego.md`:

- Una mecánica = un archivo.
- Cada mecánica tiene su **mockup o referencia visual** (no "art not necessarily final").
- Cada mecánica tiene su **dueño** (subagente o persona) y se valida independientemente contra su referente.
- Cada mecánica tiene su **estado**: No diseñada → Diseñada → Prototipada → Balanceada → Integrada.

**Las dimensiones activas** (ver `dimensiones-juego.md`) determinan qué subsistemas existen. No todas las dimensiones se traducen en una mecánica; la dimensión 2 (dirección de arte) se diseña en `banco-visual.md`, la dimensión 7 (entrega) en el pipeline de release.

## 4. Equilibrio y edge cases

Cada mecánica debe responder:

- ¿Qué **rompe** esta mecánica?
- ¿Qué situaciones de **borde** hay que considerar?
- ¿Cómo se **balancea** (dificultad, recompensa, frustración)?

Un juego con edge cases sin responder es un juego que va a romperse en playtest.

## 5. Salida verificables (Definition of Done)

Para que el Diseño se considere `APROBADO`:

- [ ] Tema interpretado escrito (frase concreta, no adjetivo)
- [ ] Cada dimensión activa tiene su subsistema documentado (o se justifica por qué no aplica)
- [ ] Cada mecánica tiene: regla, dependencias, mockup o referencia, edge cases, estado
- [ ] Scope acotado y escrito (el scope se fija aquí; no se expande en Producción)
- [ ] Timeline de hitos en `00-estado-produccion.md` (MVP + Beyond, como el Mass Flux)
- [ ] Checkpoint humano: el creador aprueba el diseño completo

## 6. Relación con otros documentos

- `roles/01-concepto-y-mercado.md`: el concepto aprobado es la entrada.
- `plantillas/sub-sistema-juego.md`: formato de cada subsistema.
- `dimensiones-juego.md`: qué dimensiones activas hay.
- `ciclo-produccion.md`: los gates de Prototipo y Vertical Slice validan los subsistemas.
- `referencias/README.md`: ficha del Mass Flux GDD, ejemplo de GDD por subsistema (no es un juego nuestro).
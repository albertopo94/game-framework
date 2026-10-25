# Escalera de Aceptación 🪜

> **Documento canónico.** Define qué significa "está listo" y en qué punto está cada cosa.
> **Origen:** destilación del flujo de trabajo de `mr-mak-workspace` (ver `referencias/README.md`).
> **Regla madre:** una cosa es que algo exista, otra que el agente lo haya verificado, y otra muy distinta que el creador lo haya aceptado. **Confundir estos estados es la principal fuente de autoengaño en trabajo con agentes.**

## Los 5 estados

| # | Estado | Qué significa exactamente | Quién lo declara |
| :--- | :--- | :--- | :--- |
| 1 | **Baseline** | El punto de partida real: commit, escena, asset original, spec vigente. | Verificable en disco/git |
| 2 | **Propuesta** | Un boceto, mockup, concept o plan **seleccionado**. Todavía no es producto. | Agente + creador |
| 3 | **Implementado** | Existe en el juego, en el código o en el asset final. Corre. | Agente (verificable) |
| 4 | **Verificado** | El agente comprobó el comportamiento con evidencia del tipo correcto (ver abajo). | Agente (con evidencia) |
| 5 | **Aceptado** | El creador lo vio, lo jugó o lo revisó, y dice que sí. | **Solo el creador** |

## Reglas duras

- **Un mockup seleccionado no es una feature entregada.** (2 ≠ 3)
- **Una verificación del agente no implica aceptación del creador.** (4 ≠ 5)
- **Un job enviado no es un asset revisado; un build preparado no es una actualización instalada.**
- **La aceptación de un concept es separable de la aceptación del asset final.** Aceptar el dibujo no acepta el modelo.
- **Un trabajo incompleto no se declara terminado.** Si falta una comprobación, se dice qué falta.
- **El estado 5 solo lo pone el humano.** Ningún agente puede auto-aceptar. Si el agente cree que está listo, pasa a `PENDIENTE_APROBACION` y pide.

## Conexión con prompting puro (browser games)

El proceso de 7 pasos de `prompting-puro-browser.md` usa **score 1-10 + meta numérica** como criterio de avance entre estados:

- Estado 3 (Implementado): el agente entrega build que corre.
- Estado 4 (Verificado): el creador juega, da score 1-10, lista 2-4 problemas, fija meta (ej. 3/10 → 9/10) y tiempo (ej. 2h).
- Estado 5 (Aceptado): el build revisado alcanza la meta y el creador lo aprueba.

Los 6 tipos de pase de revisión (polish, specific issue, lock&focus, praise&gap, quick fix, prefilming) son **operacionalizaciones del tránsito 3→4→5**.

## Qué prueba cada tipo de evidencia

Cada evidencia prueba **una cosa específica**. No se extrapola.

| Evidencia | Prueba | NO prueba |
| :--- | :--- | :--- |
| Un mockup / concept art | La dirección visual elegida | Que sea realizable, que rinda, que sea un asset |
| Un render aislado | La apariencia de un objeto | Que se vea así dentro del juego |
| Una captura de pantalla | Un instante | Una transición en el tiempo, animación, rendimiento |
| Un vídeo en slow-motion | Un detalle de diagnóstico | El feel a velocidad de juego normal |
| Hashes, contadores, valores guardados | Cableado e inputs sin cambios | Calidad visual ni diversión |
| Un prototipo feo | Que la mecánica funciona | Que la calidad sea la objetivo |
| Una prueba en navegador | El comportamiento en navegador | El costo de render nativo |
| **El juego real, corriendo** | Timing, limpieza, costo, feel | La aceptación estética del creador |

**Doctrina:** un diagrama puede proponer apariencia; **solo el motor prueba timing de eventos, limpieza y costo de render.** Ninguna prueba de agente reemplaza la aceptación humana, y ninguna aceptación humana reemplaza la prueba en el motor.

## Toda entrega declara qué NO se validó

Al entregar un build, un asset o una feature, la declaración de validación tiene **tres** partes, no una:

1. **Qué se validó** y con qué método.
2. **Qué NO se validó**: plataformas, casos, dispositivos, saves previos, condiciones no probadas.
3. **Qué queda abierto**, nombrado con su id o ubicación.

Sin el punto 2 la entrega no está descripta: está vendida. Ejemplo del formato objetivo: *"playtest de 3 personas en el build final; no se probó en Steam Deck ni con saves de la versión anterior; queda abierto #12 (texturas en pantalla de carga)"*.

## Protocolo de comparación justa (para llegar a estado 4)

Cuando la verificación es "¿esto se ve/comporta mejor que antes?", el side-by-side debe ser **justo**:

- Misma **cámara, iluminación, materiales** del juego real (no una escena de demostración).
- Misma **semilla, sujeto, ruta/acción y encuadre** entre el ON y el OFF.
- **Velocidad de juego normal.** El slow-motion es diagnóstico, no reemplaza el zoom de gameplay.
- Registrar por escrito toda diferencia **inevitable** entre las dos capturas.
- **Prohibido "arreglar" una comparación con una implementación de demostración separada.** Si hace falta un laboratorio de revisión, aísla la feature pero **conserva el code path de producción**.
- Si se inyecta input sintético, separarlo del input físico y restaurar la configuración al terminar.
- La comparación no debe cambiar el gameplay subyacente: se comprueba que no lo cambió.

## Evidencia que se deja registrada

Para cada verificación: **revisión de origen (commit), configuración exacta, escenario usado, tipo de captura, observaciones y problemas restantes.** Un video corto para movimiento, una imagen para detalle. Se conserva la captura original más una copia ligera de revisión, con procedencia; no se recomprime una y otra vez una entrega ya comprimida.

## Dónde se refleja

- `00-estado-produccion.md`: la tabla de hitos usa los estados 1-5 por ítem.
- `plantillas/maquina-subsistema.md`: el estado de la mecánica (diseñada/prototipada/...) es **ortogonal** a la escalera. Una mecánica puede estar `Integrada` (estado 3) y `PENDIENTE_APROBACION` (todavía no llegó a 5).
- `ciclo-produccion.md`: ningún gate cierra en estado 4; el gate exige estado 5 del creador.
- `AGENTS.md`: los checkpoints humanos son exactamente la transición 4 → 5.

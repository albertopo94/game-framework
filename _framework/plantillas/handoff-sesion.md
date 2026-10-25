# Plantilla: Handoff de Sesión

> **Cuándo se usa:** al cerrar o pausar una sesión, y al pasarle trabajo a otro agente o a otra sesión.
> **Regla de arranque:** la sesión siguiente **empieza leyendo este handoff**, además de `00-estado-produccion.md` y la última línea de `bitacora-sesiones.md`.
> **Origen:** destilación del skill `feature-handoff` de `mr-mak-workspace` (ver `_framework/referencias/README.md`).

## Reglas de contenido

- **Evidencia en disco, no en el chat.** Se leen los archivos actuales antes de escribir el handoff. Un mensaje de progreso previo no es evidencia.
- **Separar los 5 estados** (`escalas-aceptacion.md`): baseline / propuesta seleccionada / implementado / verificado por el agente / aceptado por el creador. Nunca mezclarlos en una misma frase.
- **No dejar valores inventados.** Si un dato falta, se deja explícitamente como `pendiente`. Un timing de ejemplo, un nombre de proyecto o un gusto estético de muestra **no se convierten en requisito**.
- **No asignarle al creador trabajo que el agente receptor puede hacer solo.**
- **Propiedad de archivos compartidos:** nombrar qué archivos no se pueden sobreescribir y quién los posee. Releer el estado compartido antes de aplicar; **reconciliar, no pisar**.
- Sin credenciales ni material de login.
- **Un handoff de feature completada empieza por el resultado práctico**, después el cambio y la verificación, y enlaza la evidencia.
- **Especificación vigente vs. log cronológico:** la spec del juego se mantiene al día; los detalles cronológicos de implementación van al log (`bitacora-sesiones.md`), no dentro de la spec.

## Plantilla

```markdown
# Handoff — <feature> — <fecha> · <sesión>

## Resultado práctico (una línea)
Qué puede hacer el juego ahora, en términos jugables. O "todavía nada jugable: X".

## Estado en la escalera (ver escalas-aceptacion.md)
- **Baseline:** <commit / escena / asset original>
- **Propuesta seleccionada:** <cuál, y si fue aprobada>
- **Implementado:** <sí/no, dónde>
- **Verificado por el agente:** <sí/no, con qué evidencia>
- **Aceptado por el creador:** <sí / no / pendiente>

## Qué se hizo
## Qué queda
## Siguiente acción exacta
La acción concreta, sin que la próxima sesión tenga que deducirla.

## Archivos y propiedad
| Archivo | Estado | Dueño / no tocar |
| :--- | :--- | :--- |

## Evidencia
Commits, capturas ON/OFF (misma cámara y acción), playtests, gates superados.

## Fichas de recurso manual pendientes de entregar o recibir
(acciones que requieren herramientas que el agente no puede usar; plantilla `ficha-recurso-manual.md`; la sesión que recibe no debe reconstruirlas del chat)

## Decisiones aceptadas (no re-litigar)
## Preguntas abiertas
## Procesos corriendo que no se pueden interrumpir
```

## Qué hace un buen handoff

- **Nombras rutas exactas** de documentos del framework que el receptor debe leer (ej. `_framework/roles/02-diseno-juego.md`).
- **Comportamiento esperado, archivos afectados, punto de partida útil, restricciones conocidas y checks de aceptación.**
- Para una continuación: qué está implementado, qué falta, resultados de tests actuales y procesos vivos que no se pueden matar.
- Para assets: IDs estables, hashes, rutas de dependencias locales y marcadores de eventos reales. Nombrar la escena o sistema donde se ve, y cómo revisarlo a **velocidad normal de juego**.
- **Rechazar revisiones viejas:** si el baseline cambió desde que se escribió el handoff, se reconcilian los inputs antes de aplicar.

## Relación con la bitácora

La **bitácora** es la línea de una fila (historial compacto). El **handoff** es el detalle de traspaso de esa sesión. Se guardan los handoffs de las sesiones que dejaron trabajo abierto; las cerradas pueden resumirse solo en la bitácora.

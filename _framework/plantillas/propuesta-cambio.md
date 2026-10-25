# Plantilla: Propuesta de Cambio

> **Cuándo se usa:** antes de implementar un cambio que toca el framework, un rol, una plantilla, o el diseño estructural de un juego. Para trabajo chico y reversible dentro de una sesión no hace falta propuesta: se ejecuta.
> **Regla madre:** **una propuesta registra intención, no reserva el trabajo ni garantiza que se acepte.** Nadie "se queda" una feature por proponerla.
> **Origen:** patrón destilado de issues de propuesta reales (formato "Proposal" + "Contribution intent") observados en `mr-mak-workspace`; ver `_framework/referencias/README.md`.

## Cuándo hace falta propuesta

- Cambiar `_framework/` (reglas, roles, plantillas, dimensiones).
- Cambiar una mecánica núcleo o una decisión de diseño ya aprobada.
- Añadir una herramienta al catálogo.
- Cualquier cambio cuyo alcance no cabe en una sessión.

No hace falta para: fixes acotados, trabajo de documentación, tareas reversibles dentro del scope ya aprobado.

## Plantilla

```markdown
# Propuesta: <una frase que describe el resultado, no la tarea>

## Problema
Qué está mal o falta hoy, con evidencia concreta (no "sería bueno").

## Propuesta
El mecanismo, en términos de comportamiento observable.

## Qué dejo afuera a propósito        <-- OBLIGATORIO
Lo que esta propuesta NO resuelve y por qué se deja para después.
Sin este bloque, la propuesta está incompleta.

## Compatibilidad
Qué sigue funcionando igual que hoy si se adopta. Un cambio que rompe
flujo existente lo dice explícitamente acá, no en el código.

## Criterios de aceptación y plan de validación
Cómo se va a poder decir que el cambio está completo: qué test,
qué comparativa, qué evidencia visual o de playtest.

## Reglón / capacidad
Contexto de tiempo disponible. No implica compromiso de respuesta.
```

## Reglas duras

- **El bloque "qué dejo afuera a propósito" es obligatorio.** Un alcance que no declara exclusiones no es un alcance: es un deseo.
- **Título en forma de resultado**, no de tarea: *"Permitir elegir el esfuerzo de razonamiento por defecto"*, no *"fix settings"*.
- **Después de la propuesta aprobada viene una unidad de implementación** que incluye su validación y su documentación. Una propuesta sin PR/trabajo asociado no avanza.
- **Sin re-litigar decisiones aceptadas.** Si la propuesta contradice una decisión previa registrada, lo dice en la primera línea y nombra la decisión que quiere revisar.
- **Una propuesta = un cambio.** No se agrupan tres ideas en una propuesta porque "están relacionadas".

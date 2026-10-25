# Bitácora de Sesiones — <nombre del juego>

> **Uso:** historial de sesiones de este juego. No es el estado: el estado vive en `00-estado-produccion.md`.
> **Regla:** una línea por sesión. No notas largas — el detalle vive en el estado y en los commits.

## Formato

| Fecha | Sesión | Feature | Resultado | Evidencia | Pendiente para la próxima |
| :--- | :--- | :--- | :--- | :--- | :--- |

- **Sesión (id):** lo genera **Pi**. Es el identificador estable que permite retomar esa sesión concretamente si se desea en otro momento (ej. `2026-10-25-a`, `2026-10-25-b`). No lo inventa el agente de IA: lo genera el runtime.
- **Feature (nombre):** un nombre humano para la feature en cuestión. Lo sugiere la IA o lo da el creador. No es el id: es el "qué" (ej. `dash feel`, `store page`).
- **Resultado:** `completado` / `pausado` / `en curso` / `abandonado`.
- **Evidencia:** commit, gate superado, archivo creado, comparativa contra referente.
- **Pendiente:** la siguiente acción exacta, para que la próxima sesión no tenga que deducirla.

## Ejemplo

| Fecha | Sesión | Feature | Resultado | Evidencia | Pendiente para la próxima |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 2026-10-25 | `2026-10-25-a` — dash feel | 5 — bucle y controles: dash | en curso | commit `abc1234` | Validar feel del dash contra el referente; gate de Prototipo |

## Sesiones

| Fecha | Sesión | Feature | Resultado | Evidencia | Pendiente para la próxima |
| :--- | :--- | :--- | :--- | :--- | :--- |
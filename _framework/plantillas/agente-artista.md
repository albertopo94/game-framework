# Plantilla: Agente Artista Especializado (Pendiente)

> **Estado: PENDIENTE** — Plantilla por definir cuando se implemente el primer agente artista especializado.
> **Origen:** Patrón observado en tanda-13 (`_framework/agentes-especializados.md`).

---

## Qué debe cubrir esta plantilla

Cuando se implemente, debe definir la configuración y handoff para un agente artista especializado:

| Campo | Qué registrar |
| :--- | :--- |
| **Nombre del agente** | Identificador único (ej. `artist-agent-v1`) |
| **Dominio** | Qué cubre: modelado, texturizado, rigging, animación, VFX, UI |
| **Sandbox** | Herramientas, configuración, APIs, credenciales aisladas |
| **Habilidades** | Lista de skills disponibles (Blender, generador 3D, herramienta de sprites 2D, servicio de auto-rigging, etc.) |
| **Formato de handoff** | Ficha técnica por recurso (ver `plantillas/ficha-recurso-manual.md`) |
| **Criterios de aceptación** | Qué valida el humano antes de aceptar (estado 5 de `escalas-aceptacion.md`) |
| **Costo estimado** | Créditos/USD estimados por asset tipo |
| **Límites** | Qué NO hace (ej. no codea gameplay, no diseña niveles) |

## Flujo de trabajo

1. **Humano** define requerimientos + referencias visuales
2. **Agente** ejecuta en su sandbox (herramientas propias, sandbox aislado)
3. **Agente** entrega paquete listo (fichas por recurso, paths, costo)
4. **Humano** valida contra criterios de aceptación (estado 5)
5. **Registro** en `00-estado-produccion.md` + `conocimiento/`

---

> **Nota:** Esta plantilla no existe aún. Se creará cuando el primer juego real necesite un agente artista dedicado.
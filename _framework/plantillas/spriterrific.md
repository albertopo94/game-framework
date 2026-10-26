# Plantilla: Spriterrific — Pipeline de Sprites 2D (Pendiente)

> **Estado: PENDIENTE** — Herramienta propia del creador (tanda-13). No entra al catálogo general; documentamos el *patrón* para referencia.
> **Origen:** `tanda-13-agent-driven-character.md` \u00a7Spriterrific.

---

## Qué es Spriterrific

Herramienta **propia del creador** para generar sprites 2D game-ready desde prompts de texto. No es un producto comercial; es una herramienta interna que el creador dogfoodea.

| Feature | Qué hace |
| :--- | :--- |
| **Prompt → Character sheet** | Genera walk, run, idle, attack, interact, etc. |
| **Prompt → Fix animaciones** | "He faces wrong way / three hands" → re-genera |
| **Blend shapes support** | Muscle size, face variation, equipment swap |
| **Export** | PNG sequences / atlas JSON listo para framework WebGL / Unity / Godot |
| **API key en env var** | Cero config, prompt en agente |

---

## Prompt canónico (patrón)

```text
Generate a character sprite sheet for [description].
Include: walk, run, idle, attack, interact, death animations.
Use blend shapes for: muscle size, face variation, equipment slots.
Export as PNG atlas + JSON metadata.
Style reference: [imagen/url].
```

## Reglas de uso

1. **Dogfooding obligatorio**: El creador usa la herramienta primero → fixea bugs (3 manos, dirección errónea) antes de liberar.
2. **Feedback visual > texto**: Plugin "set pose" en agente → click en frame → guarda pose → agente corrige.
3. **Blend shapes obligatorios**: Muscle size, face variation, equipment slots.
4. **Separación body/equipment**: Body base + equipment toggleable/swappable.
4. **Export**: Atlas PNG + JSON metadata (frame data, blend shape drivers).

---

## Dead-ends conocidos

| Tarea | Estado |
| :--- | :--- |
| Walk cycles en Unreal | No probado; Magica Cloth 2 en Unity funciona |
| Rigging perfecto sin retoque | Siempre hay fix de pesos (hombros, dedos) |
| Walk cycles perfectos primera vez | Fallan a veces (3 manos, dirección errónea) → dogfooding fixea |

---

> **Nota:** Esta plantilla no existe aún. Se creará cuando el primer juego real necesite documentar el uso de Spriterrific en producción.
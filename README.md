[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

**Licencia:** [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) — podés usar, adaptar y vender derivados, pero con **atribución** y liberando el derivado **con esta misma licencia**. Ver `LICENSE` y `NOTICE.md` (que incluye lo que la licencia **no** cubre).

---

# Game Framework 🎮 (Oficina de Producción de Juegos)

Espacio de trabajo modular y pipeline de ingeniería de contenidos para la conceptualización, diseño, producción, QA, publicación y operación de videojuegos con agentes de IA.

## 🏛️ Filosofía

Producción de videojuegos como ciclo de vida de software (SDLC) llevado al extremo: el producto final **es** software. La misma analogía del [YouTube Creator Hub](https://github.com/albertopo94/youtube) aplicada a juegos:

| Fase de producción | Rol en la oficina | Responsabilidad principal |
| :--- | :--- | :--- |
| **Concepto / Pitch** | Diseñador & Investigador | Idea validada: mercado, referentes, promesa de gameplay |
| **Diseño** | Arquitecto de Diseño | Mecánicas, sistemas, GDD, prototipo jugable |
| **Producción** | Implementadores (code/art/audio) | Construcción del juego, assets, contenido |
| **QA / Linter** | Auditor de Calidad | Bugs, balance, performance, legal/licencias |
| **Release / DevOps** | Publisher | Store pages, builds, distribución (Steam, itch.io, consolas) |
| **Telemetría / Live Ops** | Analista de Datos | Métricas de jugadores, reviews, actualizaciones |

> ⚠️ **Roles en construcción**: a diferencia del repo de YouTube (dominio ya estudiado), los roles y plantillas de la producción de juegos se definen **con el conocimiento del creador** a medida que se incorpora. No son dogma: se adaptan al tamaño y tipo de cada juego.

## ⚡ Agnosticidad de herramientas

El framework **no asume engine ni herramientas**. Se usa con lo que elija cada juego.

**Herramientas con las que se ve con buen ojo trabajar** (candidatas por defecto, no obligación):

| Herramienta | Rol habitual |
| :--- | :--- |
| **Godot** | Engine (2D/3D, open source, ligero) |
| **Unity** | Engine (2D/3D, ecosistema amplio) |
| **Blender** | Art (modelado, texturas, animación) |

Cada juego declara sus herramientas en su `00-estado-produccion.md`; nada más que eso.

## 📂 Estructura

```text
game-framework/
├── README.md              # Este manual
├── AGENTS.md              # Protocolo de gobernanza para agentes de IA
├── ideas.md               # Banco vivo de ideas, mecánicas, géneros
├── referentes.md          # Catálogo de juegos de referencia
├── banco-visual.md        # Estilos visuales y referencias artísticas
├── _framework/            # Núcleo metodológico
│   ├── ruta-produccion.md       # Router: qué leer según lo que se necesita
│   ├── escalas-aceptacion.md    # Los 5 estados de "está listo"
│   ├── dimensiones-juego.md     # Las 7 dimensiones: checklist de gates
│   ├── reglas-sistema.md
│   ├── ciclo-produccion.md
│   ├── herramientas-y-apis.md
│   ├── roles/           # 01-concepto-y-mercado, 02-diseno-juego
│   ├── plantillas/      # prompt-maestro, sub-sistema-juego, handoff-sesion
│   └── referencias/     # Material externo + ficha de análisis
├── conocimiento/          # Lecciones de la práctica (no teoría previa)
├── juegos-en-estudio/     # Incubadora: conceptos en validación
│   └── _plantilla-juego/
└── mis-juegos/            # Juegos aprobados en producción
    └── _plantilla-juego/
```

## 🔄 Flujo operativo (borrador, en construcción)

1. **Concepto** — idea validada en `ideas.md` → estudio de mercado y referentes → pitch.
2. **Diseño** — mecánicas y sistemas → GDD → prototipo jugable / vertical slice.
3. **Producción** — desarrollo iterativo por hitos, con estado persistente por juego.
4. **QA** — bugs, balance, performance, licencias y legal.
5. **Release** — store page, builds, distribución.
6. **Post-release** — métricas, reviews, actualizaciones y live ops.

El pipeline detallado (roles, plantillas, puertas de calidad) se va construyendo a medida que se incorpora conocimiento. Ver `_framework/README.md`.

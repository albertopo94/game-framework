# Referencias 📁

> Material externo conservado para análisis. **No se edita el material; se analiza y se ficha qué se tomó y qué se descartó.**
>
> **Regla de redistribución:** el análisis y la ficha viven en el repo; **el archivo original de un tercero no se redistribuye acá** (ver `.gitignore`). Si hace falta volver a consultarlo, se busca en su fuente original. Las `notas-creador/` sí se versionan: son material propio del creador.

## Mass Flux — Game Design Document (2022)

- **Archivo:** `mass-flux-gdd-2022.docx` — **solo en el disco local del creador; no se publica** por ser material de un tercero. Este repo conserva el análisis, no el documento.
- **Fuente original:** pendiente de enlazar (agregar el enlace público del autor si se localiza)
- **Origen:** Aizin, Pirate Software Game Jam 2022
- **Tipo:** GDD de game jam, desarrollado en solitario en 8 días
- **Herramientas del original:** GameMaker Studio 2.3, Aseprite, FL Studio 12
- **Qué es:** puzzle de celdas tile-based, 15 niveles, sobre reducir/manipular la forma de una masa de celdas para llegar a la meta
- **Por qué se conserva:** ejemplo de GDD por subsistema (no monolítico). Cada mecánica (Walls, Spikes, Holes, Fruit, Independence, Set Spikes) tiene nombre, tipo, mockup y descripción. Eso es el formato que inspiró `plantillas/maquina-subsistema.md`.

### Lo que tomamos de él

| Sección | Va a |
| :--- | :--- |
| Primary/Secondary Mechanics | `plantillas/maquina-subsistema.md` (una por mecánica) |
| Theme Interpretation (Sacrifice Is Strength) | `roles/02-diseno-juego.md` §2 (tema interpretado, no genérico) |
| Development Timeline (MVP + Beyond) | `00-estado-produccion.md` hitos |
| Platform / Dev Software / Genre / Target Audience | `00-estado-produccion.md` ficha + `roles/01` §4 |
| Inspiration (Snakebird, Baba Is You) | `referentes.md` + `juegos-en-estudio/_plantilla-juego/estudio-concepto.md` |

### Lo que NO tomamos

- El formato .docx y la tabla de timeline de Word: nuestro framework es agnóstico de herramientas; los hitos van en `00-estado-produccion.md`.
- "Art not necessarily final" / "Not an actual puzzle/level": aclaraciones de game jam, no del framework.
- "2-bit graphical prompt": restricción del game jam, no del juego ni del framework.
- El tono en primera persona del desarrollador: nuestros specs para agentes son concisos y estructurados.

### Conclusión del análisis

**No generamos un solo archivo GDD como el Mass Flux.** Un GDD de game jam es un snapshot de una semana; nuestros proyectos son largos y el framework está diseñado para evolucionar con el conocimiento. Nuestro framework ya cubre todo lo que cubre ese GDD, pero distribuido en documentos más pequeños con responsabilidades claras.

---

## mr-mak-workspace — flujo de trabajo de producción con agentes

- **Origen externo:** https://github.com/witnesstodark/mr-mak-workspace (no se copia el repo; se conserva solo esta ficha)
- **Qué es:** un **producto** — app de escritorio que envuelve CLI agents (Chats) más un Workspace visual, con su propio stack de skills de producción de juegos (`.agents/skills/`: 20 skills de VFX, animación, niveles, UI, audio, review visual, handoffs, asset generation).
- **Por qué se analiza:** es la oficina de producción con agentes **destilada de práctica real** en el dominio que nosotros estamos construyendo. No es un GDD ni una idea: es flujo de trabajo probado.

### Lo que tomamos (4 piezas, pocas pero de peso)

| Su práctica | Nuestro destino |
| :--- | :--- |
| **Escalera de aceptación** ("a selected mockup is not a shipped feature", "a successful agent check does not imply the user accepted the result") + tabla de qué prueba cada evidencia + protocolo de comparación justa ON/OFF | `_framework/escalas-aceptacion.md` |
| **Router de producción** (elegir skill según el entregable necesitado; "la existencia de un skill no significa que el MCP/editor esté conectado") + planificación por entregables | `_framework/ruta-produccion.md` |
| **`feature-handoff`** (separar baseline/propuesta/implementado/verificado/aceptado, propiedad de archivos compartidos, no inventar valores, no asignar al humano trabajo del agente, spec vigente vs. log cronológico) | `_framework/plantillas/handoff-sesion.md` |
| **"Summarize and continue"**: handoff guardado en disco y la nueva sesión arranca leyéndolo | Refuerza nuestro Protocolo de Sesión (`AGENTS.md`) |
| **`knowledge/`** (lecciones) y **`context/`** (preferencias del dueño, "don't invent a biography") como destinos separados | `conocimiento/` |
| **"Make the smallest useful revision instead of restarting the entire design without a reason"** | Corrección dirigida (esta vez sí portada a `reglas-sistema.md`) |
| **Issue tracker como árbol** (tracker padre de auditoría con evaluación general + “one issue per fix” + severidades) y **hallazgos confirmados por dos revisores independientes** | `higiene-de-trabajo.md` §1-§2 |
| **Commits de integración que nombran lo que integran** (`Integrate PR #57 for the community update`) y unidad revisable por commit | `higiene-de-trabajo.md` §3 |
| **Honestidad de green-run** (“without it they skip, so a green run has not proven the emitted code compiles”) | `higiene-de-trabajo.md` §4 |
| **Modos asistidos explícitos, opt-in y aislados** (prohibido descargar assets en silencio; dependencias aisladas del núcleo; se saltea si no se cumple la condición) | `higiene-de-trabajo.md` §5 |
| **Límites declarados** (Strong / Stylized-only / Out of scope today, con análisis del porqué) | `higiene-de-trabajo.md` §6 + sección de límites del `_framework/README.md` |
| **Propuestas de cambio con scope explícito de exclusiones** (“what you will intentionally leave out”, “does not assign, reserve, or guarantee acceptance”) | `plantillas/propuesta-cambio.md` |
| **Títulos de issue/PR como resultado** (“Let the user choose...”, “Show native context usage...”) | `plantillas/propuesta-cambio.md` |
| **Disciplina de releases** (14 releases observados): línea de validación explícita, **evidencia negativa** ("no se probó X", "not interactively validated", "notarization not included"), ítems abiertos declarados, "qué NO incluye el paquete", checksums de artefactos, enlaces pinneados al tag, CHANGELOG ≠ release notes | `roles/05-release-distribucion.md` + sección de evidencia negativa en `escalas-aceptacion.md` |

### Lo que NO tomamos (y por qué)

- **La app** (Tauri, workspace visual, acceso por teléfono, temas): choca de frente con nuestra regla *No automatizar prematuramente*. Este repo es exactamente la tentación que esa regla previene.
- **Skills atados a proveedores:** `fal-ai-generation`, `higgsfield-workflow`, `img2threejs` (un proyecto entero adentro), `materials-to-game`, `character-sheet-pipeline`. Agnosticidad: no adoptamos skills de producto; si un día hacen falta, entran como capability en `herramientas-y-apis.md` con visto bueno del creador.
- **`workspace-authoring`** (su formato de reportes HTML/JSON), temas, `video-watch`, `voice-dictation`: fontanería de su producto.

### Conclusión del análisis

Su valor no es el contenido de ningún juego (el "My Dream Game" es un ejemplo empaquetado), sino **la disciplina con la que separan "lo hice" de "lo verifiqué" de "el dueño lo aceptó"**. Eso es lo que un framework de agentes necesita más que ninguna lista de herramientas, y es lo que adoptamos como documento canónico.

> ⚠️ Nota: este repo es un **producto de terceros**. No se forkéa ni se copia su código ni sus skills. Se documenta aquí solo el análisis de su flujo, igual que con Mass Flux.

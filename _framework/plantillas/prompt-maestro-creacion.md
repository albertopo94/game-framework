# Plantilla: Prompt Maestro de Creación de Proyecto

> **Cuándo se usa:** arranque de un nuevo proyecto desde cero (fase Concepto → Diseño). No es el flujo de producción: una vez el proyecto existe, se usa el pipeline de `mis-juegos/[juego]/` con checkpoints humanos.
> **Origen:** destilación de `referencias/notas-creador/tanda-02-prompt-creacion.md`.

## Reglas fijas del prompt maestro

Un prompt maestro de creación debe contener, en este orden:

1. **Referencia visual primaria** (vídeo, imagen o juego real). La estética se fija aquí, no por adjetivos.
2. **Restricciones duras de resultado prohibido:** "nada de juegos genéricos", "nada hecho en Canvas", "muy pocas cosas procedurales" (si aplica).
3. **Lista de assets requeridos:** sprites, efectos, sonido, modelados — lo que el juego necesita, no lo que el agente elija.
4. **Herramientas permitidas:** engine, art, audio. Si no se especifican, el agente elige y registra en `00-estado-produccion.md`.
5. **Ámbito del prompt:** "proyecto completo" significa que el prompt define el *contrato* (qué se va a construir), no que genera todo en un solo paso. El agente descompone por subsistema y ejecuta con checkpoints.

## Plantilla

```text
# Prompt Maestro — <nombre del proyecto>

## 1. Referencia visual
- Vídeo/imagen/juego de referencia: <enlace o descripción>
- Qué se copia de la referencia (estética, paleta, tipografía, ritmo, feel de movimiento):
- Qué NO se copia:

## 2. Restricciones duras
- [ ] Nada de juegos genéricos / templates
- [ ] Nada hecho en Canvas (o la herramienta prohibida)
- [ ] Assets handcrafted por defecto; procedural solo cuando se pida explícitamente
- [ ] Mapas no procedurales por defecto (ver `dimensiones-juego.md` #4)
- [ ] <otra restricción del creador>

## 3. Assets requeridos
- Sprites: <lista>
- Efectos visuales: <lista>
- Sonido / música: <lista>
- Modelados 3D: <lista>

## 4. Herramientas
- Engine: <Godot / Unity / otro / "el agente elige">
- Art: <Blender / otro>
- Audio: <otro>

## 5. Contrato del proyecto
- Género:
- Mecánicas núcleo:
- Target / plataforma:
- Scope (lo que se va a entregar, no lo que se va a soñar):
- Referentes de calidad (1-3 juegos reales contra los que se va a comparar):

## 6. Dimensiones activas (ver `_framework/dimensiones-juego.md`)
Marcar las que aplican a este juego y, para cada una, el target de calidad:
- [ ] 1 Concepto original
- [ ] 2 Dirección de arte
- [ ] 3 Recursos (assets) y sprites
- [ ] 4 Mapas / niveles
- [ ] 5 Bucle (loop) y controles
- [ ] 6 Combate y profundidad
- [ ] 7 Entrega al usuario

## 7. Descomposición por subsistema
Listar los subsistemas (por dimensión) que se van a construir con dueño propio:
- <subsistema> — dueño:
```

## Relación con prompting puro (browser games)

El proceso de 7 pasos de `prompting-puro-browser.md` (prompt + target + loop + play + score + skills + ship) **es una implementación concreta del modo Creación** para juegos browser/framework WebGL. Donde el prompt maestro define el contrato estático, el proceso de 7 pasos lo ejecuta dinámicamente con loop, scoring y skill library.

## Advertencia

El proceso de 7 pasos de `prompting-puro-browser.md` (prompt + target + loop + play + score + skills + ship) **es una implementación concreta del modo Creación** para juegos browser/framework WebGL. Donde el prompt maestro define el contrato estático, el proceso de 7 pasos lo ejecuta dinámicamente con loop, scoring y skill library.

## Advertencia

Un prompt maestro **no sustituye los checkpoints**. Define el contrato inicial; el desarrollo que viene después sigue las puertas de calidad de `AGENTS.md` (concepto aprobado, diseño aprobado, etc.). "Un único prompt que lo crea todo" es un modo de arranque, no un modo de producción.
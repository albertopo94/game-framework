# Rol: Concepto y Estudio de Viabilidad

> **Cuándo se activa:** arranque de un nuevo juego (fase Concepto). Se salta si el juego viene de `juegos-en-estudio/` con un estudio de concepto ya hecho.
> **Equivalente en YouTube:** rol 01 (Investigación e Ideas).
> **Origen de este rol:** destilación de `_framework/referencias/notas-creador/tanda-01-fps-aaa.md` y `_framework/referencias/notas-creador/tanda-02-prompt-creacion.md`.

## Responsabilidad

Validar que la idea vale la pena antes de invertir tiempo en código. El rol 01 no es "generar ideas bonitas": es **matar ideas malas rápido**.

## 1. Referencia visual primaria

La estética del juego se fija por **referencia visual** (vídeo, imagen o juego real), no por adjetivos.

- "Bonito", "retro", "pixel art", "AAA" por sí solos **no son especificaciones**: son adjetivos.
- El agente pide o recibe la referencia real. Si no hay, lo pregunta honestamente: *"¿qué estilo visual tenés en mente o prefieres que te proponga 5 alternativas?"*
- De la referencia se extraen: paleta, tipografía, ritmo de movimiento, feel de gameplay, qué elementos son invariantes y qué se puede cambiar.

## 2. Restricciones duras de resultado prohibido

Cada juego declara explícitamente lo que **no** puede ser. Ejemplos comunes:

- Nada de juegos genéricos / templates
- Nada hecho en Canvas (si aplica)
- Assets handcrafted por defecto; procedural solo cuando se pida explícitamente
- <otra restricción del creador>

Estas restricciones son **contrato**: no se negocián en silencio.

## 3. Assets requeridos

Lista concreta de lo que el juego necesita, no lo que el agente elija:

- Sprites
- Efectos visuales
- Sonido / música
- Modelados 3D

## 4. Herramientas

- Engine, art, audio. Cada juego las declara en su `00-estado-produccion.md`.
- Godot, Unity y Blender son candidatas privilegiadas, no estándar impuesto.
- **Blender MCP oficial** es la herramienta principal de creación de assets (modelado, texturas, iluminación, exportación). Se usa **siempre que el tipo de juego lo amerite** — no es un estándar universal: un pixel art 2D puro puede no necesitarlo, pero un 3D, un 2.5D pixel art con iluminación dinámica o cualquier juego que requiera modelado/texturas sí. La decisión la toma el rol 01 junto con el prompt maestro (dimensión 3 y 4); el agente **nunca asume** que un juego 2D no necesita Blender MCP.
- Antes de proponer un flujo concreto con Blender MCP, el agente debe **comprobar si la herramienta elegida ofrece esa capacidad** en el entorno local. No se asumen capacidades por nombre.
- Catálogo completo: `_framework/herramientas-y-apis.md`.

## 5. Scope (fija aquí, no en producción)

El scope se define en Concepto/Diseño y **no se expande en Producción**. Si surge algo que merece, se registra como idea en cola y se decide en el siguiente ciclo de planificación.

> "Scope creep" es la causa número 1 de muerte de juegos indie.

## 6. Referentes de calidad

1-3 juegos reales contra los que se va a comparar el proyecto. No son inspiración: son **punto de referencia medible**. Ningún "se ve bien" es un criterio; el criterio es el comparado explícito contra la referencia.

## 7. Salida verificables (Definition of Done)

Para que el Concepto se considere `APROBADO`:

- [ ] Referencia visual primaria registrada (enlace o descripción concreta)
- [ ] Restricciones duras escritas
- [ ] Lista de assets requeridos
- [ ] Herramientas declaradas por juego
- [ ] Scope acotado y escrito
- [ ] 1-3 referentes de calidad declarados
- [ ] Checkpoint humano: el creador aprueba o mata la idea

## 8. Ficha del estudio de concepto

Plantilla en `juegos-en-estudio/_plantilla-juego/estudio-concepto.md`.
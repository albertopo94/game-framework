# Un script de edición en lote vació un archivo versionado

**Type:** bugfix
**Fecha:** 2026-10-25
**Juego / contexto:** el propio framework, incorporando la tanda 05.
**Evidencia:** `git status` mostró `M _framework/README.md` con el archivo en **0 bytes** (`find . -name "*.md" -size 0`). Recuperado con `git checkout -- _framework/README.md` desde el commit `04673f6`, y verificado después con `git diff` (solo las 2 filas nuevas, nada perdido del commit anterior).

## Qué

Un script Python que escribía un archivo después de un `find`/`replace` falló con `UnicodeEncodeError: surrogates not allowed` (una secuencia de emoji escrita mal en la fuente del script). El `open(p,'w')` **ya había truncado el archivo a 0 bytes** antes de que el `write()` lanzara la excepción.

## Por qué

Modo `"w"` trunca al abrir, no al escribir. Cualquier excepción entre el abrir y el escribir deja el archivo vacío. El script además reescribía el archivo entero en vez de hacer reemplazos puntuales.

## Consecuencia práctica

1. **Trabajar sobre estado commiteado.** Antes de una edición por lotes con script, el estado previo tiene que estar en un commit. Aquí salvó la vida el commit inicial: la recuperación fue un comando.
2. **Escribir en un archivo temporal y renombrar** (`write` + `os.replace`), o escribir en memoria y abrir en `"w"` solo al final con el contenido ya validado. Nunca `open(p,'w')` con contenido que todavía puede fallar.
3. **Verificar tamaño después de ediciones masivas:** `find . -name "*.md" -size 0` es un check de 1 segundo que atrapa el daño antes del commit. Va en la verificación de cualquier tanda.

## Límites

- Comprobado una vez, en este repo, con pérdida cero gracias a git. La mecánica (truncar en open, no en write) es comportamiento documentado de Python: no es especulación.
- Aplica a cualquier batch edit con script sobre archivos versionados, no solo a Markdown.

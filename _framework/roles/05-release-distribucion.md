# Rol: Release y Distribución

> **Cuándo se activa:** fase Release (ver `ciclo-produccion.md`), y en cada parche post-release.
> **Equivalente en YouTube:** DevOps / Release (Publisher & Growth).
> **Origen del método de release notes:** patrón observado en 14 releases reales de `mr-mak-workspace` (ver `_framework/referencias/README.md`). Lo específico de plataformas de juegos (Steam, itch.io, consolas) está marcado como **pendiente del conocimiento del creador**: no se inventa.

## Responsabilidad

Que el juego llegue al jugador **en condiciones de ser jugado** y que lo publicado describa con honestidad qué contiene, qué se probó y qué no.

## 1. Regla madre: la entrega declara su validación

Ninguna publicación termina con "listo" o "quedó bien". Toda entrega incluye una **línea de validación** con tres partes:

1. **Qué se validó**, con el método y la cantidad: *"playtest de 3 personas en el build final, 2 horas de sesión, sin crashes"*, *"60 fps medidos en la escena X en la plataforma objetivo"*.
2. **Qué NO se validó** (evidencia negativa, obligatoria): *"no se probó en Steam Deck"*, *"el audio en la plataforma Y no se verificó con auriculares"*, *"no se testearon saves de la versión anterior"*.
3. **Qué queda abierto** nombrado, con su id o ubicación: *"queda abierto el bug #12 (texturas en pantalla de carga)"*.

**Una entrega sin evidencia negativa no está descripta: está vendida.** Y nosotros no vendemos, informamos.

## 2. Anatomía de las notas de release

En este orden:

| Bloque | Contenido |
| :--- | :--- |
| **Resumen en términos del jugador** | Una frase: qué puede hacer/jugar ahora quien lo instale. No dice "se refactorizó X". |
| **Cambios agrupados** | Features / fixes / contenido, por área jugable. Cada fix que corresponde a un reporte enlaza su id. |
| **Qué NO incluye este paquete** | Contenido no terminado, plataformas no incluidas, features de las que se habla pero no están. |
| **Validación** | Los 3 puntos de §1. |
| **Cómo actualizar y qué se conserva** | Qué hay que hacer, y qué no se pierde (saves, configuración, logros). Si los saves se rompen, se dice en la primera línea. |
| **Checksums de los builds** | Archivo de hashes junto a los artefactos. |

## 3. Versionado honesto

- Un release es una **unidad de valor jugable**, no un commit. No hay release por cada microcorrección.
- Los cambios que rompen saves, mods o compatibilidad con builds previos se anuncian con **letra visible**, no enterrados en la lista.
- `CHANGELOG` (completo, cronológico, para mantener historial) y **notas de release** (resumen legible, para el jugador) son **dos artefactos distintos** con públicos distintos. No se copia uno dentro del otro sin filtrar.

## 4. Builds y artefactos

- Cada entrega declara para qué plataforma fue **construida** y para cuál fue **jugada**. Que compile no es que se pueda jugar.
- Se conserva el build exacto que se publicó, con su commit y su configuración, para poder reproducirlo.
- Los builds del repo de trabajo no van al repo (ver `.gitignore`); viven en la ruta de artefactos del juego.

## 5. Qué está pendiente del conocimiento del creador

No se documenta acá lo que no se sabe. Falta, para completar este rol con evidencia real:

- [ ] Tienda elegida por juego y su compliance (Steam / itch.io / consolas / itch-only primero).
- [ ] Página de tienda: capturas, tráiler, textos, categorías, tags, wishlist.
- [ ] Demo: si aplica, cómo se corta y qué se sacrifica de la demo.
- [ ] Ventana de lanzamiento: horarios,.timezone, visibilidad previa, price point.
- [ ] Processos de certificación de consola (si alguna vez aplica).

Hasta que eso esté, el rol cubre **la disciplina de la entrega** (§1-4), que es agnóstica de tienda.

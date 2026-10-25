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

## 5. Compliance de plataforma y declaración de contenido

Las plataformas de distribución tienen políticas que **cambian en el tiempo y se verifican**. Dos reglas permanentes, independientes del texto de la política vigente:

1. **Leí la política en su fuente oficial el día que publicás**, no la que recordás de hace tres meses. Los requisitos de declaración de contenido generado, revisión de página y contenido prohibido se actualizan; citar la fecha de lectura en el registro del juego.
2. **Declarar con honestidad específica, no con frases vacías.** Si corresponde declarar uso de herramientas generativas: decir qué parte, y que hubo revisión humana. Una declaración genérica o evasiva es peor que una precisa: las plataformas revisan, y una omisión detectada cuesta más que la declaración original.

Para el marco general de por qué esto es una puerta y no una sugerencia, ver `reglas-sistema.md` (trazabilidad legal) y `escalas-aceptacion.md` (evidencia negativa).

## 6. Visibilidad previa al lanzamiento

La página de tienda **antes** del juego es trabajo de Release, no un extra. Se planifica en Diseño (por los lead times de `ciclo-produccion.md`) y se ejecuta acá:

- Página visible con anticipación suficiente para acumular deseo de compra medible.
- Registrable: cuánto se acumuló, para poder decidir la fecha con datos.
- Demo en eventos de la plataforma, si aplica al juego.
- Construir en público: mostrar el progreso durante la producción es canal de descubrimiento que no cuesta producción.

## 7. Qué está pendiente del conocimiento del creador

No se documenta acá lo que no se sabe. Falta, para completar este rol con evidencia real:

- [ ] Tienda elegida por juego y su compliance vigente (leído en fuente oficial al momento de publicar).
- [ ] Costos de publicación por plataforma y condiciones de recuperación, verificados al momento.
- [ ] Página de tienda: capturas, tráiler, textos, categorías, tags, wishlist.
- [ ] Demo: si aplica, cómo se corta y qué se sacrifica de la demo.
- [ ] Ventana de lanzamiento: horarios,.timezone, visibilidad previa, price point.
- [ ] Processos de certificación de consola (si alguna vez aplica).

Hasta que eso esté, el rol cubre **la disciplina de la entrega** (§1-4), que es agnóstica de tienda.

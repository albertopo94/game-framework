# Montaje de Niveles y Ambientes 🗺️

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-06-ensamblado-de-niveles.md` (mismo canal que tanda-05: construyó la demo completa en pantalla — evidencia mejor — pero **vende un curso del workflow**, incentivo de hacerlo ver fluido y de destacar herramientas concretas). Los nombres de productos no entran; las prácticas, con verificación pendiente.
> **Problema que aborda:** cómo pasar de "pila de assets generados" a un nivel que parece **dirigido** y no **regado**.

## Regla central: generar piezas es producción; ensamblar es diseño

La colocación de assets es una decisión de diseño leída por el jugador: contar el espacio con formas, no llenarlo. El fracaso nomeado por la fuente es directo: **dejar que la IA "reparta" los assets produce *slop*** — una escena genérica, uniformemente poblada, sin intención legible.

- Piezas: se pueden generar con agentes (ver `produccion-assets.md`).
- Montaje: es criterio dirigido. Si un agente coloca, lo hace **contra una intención explícita declarada** (este bloque es el refugio, esta ruta invita, este objeto es el hito visible), y la escena pasa la revisión visual de `escalas-aceptacion.md`; "quedó lleno" no es un criterio de paso.

## El kit, no el todo

El nivel se produce como un **starter kit de piezas** + ensamblado, no como una generación de la escena completa:

1. Concepto → **dividir en partes** (cada roca, tablas, redes, texturas de apoyo: papel, red de pesca) → generarlas en 2D, seleccionar, convertir en 3D, procesar.
2. **No hace falta predecir todas las piezas antes de empezar**: el kit es iterativo — falta algo en el ensamblado, se vuelve y se genera. Esto conecta con scope: el kit no es una promesa cerrada, es inventario vivo.
3. Agrupar piezas similares en una sola generación (varias piedras juntas) ahorra tiempo y tokens cuando son del mismo estilo.

## Reglas de ensamblado (mecanicas, verificables)

| Regla | Por qué |
| :--- | :--- |
| **Anclar la escala primero**: arrancar el montaje por el elemento cuyas dimensiones reales ya se conocen (el muelle, la escalera, la cabaña) — no por el elemento más grande e indefinido (la cueva) | El primer bloque puesto es la **regla de escala** del resto; un elemento grande sin escala conocida contamina todo lo que se apoye en él |
| **Grandes primero, accesorios al final** ("la última milla") | Los objetos grandes definen lectura y composición; los accesorios decoran una composición que ya existe. Al revés, se decora el caos |
| **Reutilizar antes que generar** | Un stalactita = una roca existente cortada y escalada; una soga = curva Bézier, no una generación — **cinco veces más rápido**. Reutilizar además ya trae la textura puesta: reuso = optimización gratis (misma textura, menos material, menos memoria) |
| **Antes de generar, la pregunta de camino**: ¿generar, modificar un asset existente, primitiva del software, o asset comprado/licenciado? | Gana el camino **más barato que cumpla el propósito** (hermano del "la representación más simple" de `produccion-assets.md`). "Se puede generar" no es razón para generar |
| **Recortar lo que el jugador nunca ve** | La base de una roca grande que apoya en el suelo se corta; polígonos invisibles son rendimiento regalado. Es el presupuesto de rendimiento de `dimensiones-juego.md` aplicado al montaje |
| **Consolidar materiales al ensamblar** | Varias piezas que comparten material → un atlas: menos materiales = menos draw calls. Decidir el tamaño de atlas por cómo se van a usar (distancia de visionado), no por defecto |
| **Referencia fijada en la superficie de trabajo** | La imagen de referencia se deja visible dentro de la herramienta de montaje, no en otra ventana: reduce el ida-y-vuelta de comparar y mantiene el "apuntamos al mismo target" (versión práctica de la referencia visual de `reglas-sistema.md`) |
| **Organizar en agrupaciones desde el día uno** (kit / muelle / cueva...) | Esconder o aislar un área con un clic cambia la velocidad de trabajo; el desorden en la escena se paga en decisiones más lentas |

## La pasada de presentación es parte de la calidad

La escena "se vende" con luz, atmósfera y clima, y la fuente lo trata como **pasada planificada del montaje** (en su ejemplo: 1-2 horas de opciones de iluminación sobre un nivel ya ensamblado), no como filtro posterior. En nuestro framework es parte de la dimensión de dirección de arte y entra en el gate visual: una comparación side-by-side contra el referente sin la iluminación puesta compara dos cosas distintas (`escalas-aceptacion.md`).

## Reparto agente ↔ humano en este flujo (propuesta inicial)

| Lo hace el agente | Lo hace el humano (o dirección humana explícita) |
| :--- | :--- |
| Preparar el kit: generar piezas, procesar, corregir texturas, decimar, hornear mapas, consolidar atlases, organizar agrupaciones, exportar al motor | La composición y el placement con intención; leer si la escena "cuenta" lo que el diseño pide; la pasada de presentación final |

Si el agente hace un placement de borrador, se etiqueta como **propuesta (estado 2 de la escalera)**: la escena resultante no es "el nivel", es un mockup espacial para corregir.

## Dónde encaja

- `dimensiones-juego.md` #4 (mapas no procedurales): este documento es el "cómo" del armado manual asistido.
- `produccion-assets.md`: genera las piezas que este documento ensambla; ambas comparten "camino más barato" y "presupuesto de rendimiento".
- Matriz de capacidad (`herramientas-y-apis.md`): el diseño de niveles queda con **dos fuentes de terceros** marcando placement/ensamblado como punto débil del agente — sigue `pendiente`, pero la hipótesis se está densificando.

## Dónde encaja (actualizado)

| Documento | Relación |
| :--- | :--- |
| `pipeline-soulslike-72h.md` | Modular level design con primitivas + modificadores (array/curve); referencia de escala exportada del motor; tileables para grandes superficies |

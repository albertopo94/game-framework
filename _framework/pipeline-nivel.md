# Pipeline de Nivel Genérico 🗺️

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Consolidación de `montaje-de-niveles.md` (sección nivel) → **`pipeline-assets.md` + `pipeline-nivel.md`**. Un solo pipeline con **estrategias de placement configurables** según el tipo de nivel y el control deseado.
> **Principio:** generar piezas es producción; ensamblar es diseño. El nivel se produce como **kit de piezas + ensamblado dirigido**, no como generación completa por IA.

---

## Perfiles de Nivel (se declara en `00-estado-produccion.md` del juego)

| Perfil | Tipo de juego | Estrategia de placement | Control vs Velocidad |
| :--- | :--- | :--- | :--- |
| **modular-manual** | Souls-like, Metroidvania, FPS, RPG | Primitivas + Array/Curve modifiers + colocación manual | Control total > velocidad |
| **modular-asistido** | Top-down, RTS, City builder | Primitivas + Array/Curve + agente coloca bajo supervisión | Balance |
| **tilemap-2d** | 2D platformer, RPG, roguelike | Tilemap + autotiling + reglas de adyacencia | Velocidad > control fino |
| **procedural-asistido** | Roguelike, survival, infinite runner | Reglas procedurales + semilla + validación humana | Velocidad > control |
| **navegador-pwa** | Juegos browser/móvil (PWA) | Rust/WASM + framework WebGL + librería networking + herramienta de sprites 2D | Mobile-first, touch-first |
| **arena-sandbox** | Battle royale, MMO, open world | Terreno procedural + zones + POIs colocados manualmente | Control en POIs, velocidad en relleno |

---

## Pipeline Base (común a todos los perfiles)

| Paso | Qué hace | Quién | Herramientas genéricas |
| :--- | :--- | :--- | :--- |
| **1. Concepto + Layout en papel** | Sketch, flow, pacing, pacing, spawn points, boss arena, critical path | Humano | Papel / Figma / Miro / papel |
| **2. Referencia de escala** | Exportar esqueleto/cápsula del personaje desde motor → usar como unidad de medida | Humano + Agente | Motor (UE/Unity/Godot) → export reference |
| **3. Kit de piezas (assets)** | Generar/proveer piezas base según `pipeline-assets.md` | Humano + Agente | `pipeline-assets.md` perfiles |
| **4. Estructura base (blockout)** | Primitivas + modificadores para formas grandes (suelo, muros, paths) | Humano | Primitivas + Array/Curve modifier / Terrain tools |
| **5. Placement dirigido (kit → nivel)** | Colocación con intención: ancla de escala → grandes → medianos → accesorios | Humano (dirige) + Agente (prepara) | Editor motor / Blender |
| **6. Detalle y cohesión** | Recortar invisible, consolidar atlases, organizar colecciones, referencia visible | Humano | Editor motor / Blender |
| **7. Iluminación / Atmósfera / VFX** | Luz, niebla, clima, post-process, VFX ambientales | Humano + Agente | Motor + VFX tools |
| **8. Playtest + Iteración** | Jugar, medir pacing, flow, readability, performance | Humano | Motor + telemetría |

---

## Estrategias de Placement (configurables por perfil)

| Estrategia | Qué es | Cuándo usar | Ejemplo |
| :--- | :--- | :--- | :--- |
| **Ancla de escala** | Arrancar por elemento de tamaño conocido (muelle, escalera, cabaña) | Siempre, primero | Muelle → define escala de cueva |
| **Grandes primero, accesorios al final** | Objetos grandes definen lectura; accesorios decoran composición | Siempre | Muros → rocas → accesorios |
| **Reutilizar antes que generar** | Stalactita = roca cortada/escalada; soga = curva Bézier | Siempre | 5x más rápido + hereda material |
| **Pregunta de camino antes de generar** | ¿Generar / Modificar / Primitiva / Comprar? Gana el más barato que cumple | Siempre | Soga = curva Bézier (5x más rápido) |
| **Recortar lo invisible** | Base de roca que toca suelo → knife/boolean cut | Siempre | Polígonos invisibles = rendimiento regalado |
| **Consolidar materiales al ensamblar** | Varias piezas mismo material → atlas único | Cuando >3 piezas mismo material | Menos draw calls |
| **Referencia visible en superficie de trabajo** | Imagen referencia en viewport, no en otra ventana | Siempre | Reduce ida-y-vuelta |
| **Organizar en colecciones desde día 1** | Kit / Zona A / Zona B / Foliage / Lights | Desde día 1 | Esconder/aislar con 1 clic |
| **Primitivas + Modificadores > IA Placement** | Array + Curve modifier > IA "repartiendo" assets | Siempre | Control > slop |
| **Referencia de escala exportada del motor** | Exportar esqueleto/cápsula UE → usar como unidad | Antes de modelar | Evita rehacer por escala |
| **Pasada de luz/atmósfera = gate visual** | Luz, niebla, clima, post-process = parte de la calidad | Tras ensamblado | "Mitad del look" |

---

## Reglas Transversales (aplican a todos los perfiles)

| Regla | Origen |
| :--- | :--- |
| **Generar piezas es producción; ensamblar es diseño** | tanda-06, tanda-09, tanda-11 |
| **Slop = IA "repartiendo" assets sin intención** | tanda-06 |
| **Ancla de escala: arrancar por elemento conocido** | tanda-09, tanda-11 |
| **Grandes primero, accesorios en última milla** | tanda-09, tanda-11 |
| **Reutilizar > generar** (cortar roca, Bézier rope) | tanda-11 |
| **Pregunta de camino antes de generar** (generar/modificar/primitiva/comprar) | tanda-11 |
| **Recortar lo invisible** (knife/boolean) | tanda-11 |
| **Consolidar materiales al ensamblar** | tanda-11 |
| **Referencia fijada en superficie de trabajo** | tanda-06, tanda-11 |
| **Organizar en colecciones desde día 1** | tanda-11 |
| **Primitivas + Modificadores > IA Placement** | tanda-09, tanda-11 |
| **Referencia de escala exportada del motor ANTES** | tanda-09, tanda-11 |
| **Pasada de luz/atmósfera = gate visual** | tanda-09 |
| **Foliage/agua dinámicos: comprar, no generar** | tanda-11 |
| **Wireframe perfecto no necesario para estáticos** | tanda-11 |
| **Decimate en Blender para low-poly rápido** | tanda-11 |
| **Prototipo jugable > perfección** | tanda-11 |
| **Assets generados en un estilo = cohesión gratis** | tanda-11 |

---

## Estrategias por Perfil (detalle)

### modular-manual (Souls-like, Metroidvania, FPS, RPG)
- **Control total** sobre cada placement
- **Array + Curve modifier** para repeticiones geométricas (muros circulares, círculos de rocas)
- **Primitivas + scale/rotate** para formas base (núcleo arena, caminos, paredes)
- **Pinceles terreno / herramientas nativas UE** para detalles (piedras, arena)
- **Referencia escala exportada** del motor ANTES de modelar
- **Luz/niebla/clima** como "mitad del look" (pasada planificada)

### modular-asistido (Top-down, RTS, City builder)
- **Array + Curve** para estructura base
- **Agente coloca bajo supervisión** (da opciones, humano elige)
- **Reglas de placement** codificadas (distancia mínima, alineación a grid, no overlap)
- **Validación visual humana** cada N piezas

### tilemap-2d (2D platformer, RPG, roguelike)
- **Tilemap + autotiling** + reglas de adyacencia
- **Reglas de placement** codificadas (suelo, paredes, decoración)
- **Herramientas nativas** del motor (Tilemap Editor, Rule Tiles)

### procedural-asistido (Roguelike, survival, infinite runner)
- **Reglas procedurales** (rooms + corridors + locks + keys)
- **Semilla + validación humana** (jugar 3-5 runs, marcar roturas)
- **POIs colocados manualmente** (boss room, shop, spawn)
- **Validación de pacing** (tiempo medio, dificultad, flow)

### arena-sandbox (Battle royale, MMO, open world)
- **Terreno procedural** (heightmap + biomas + erosion)
- **Zonas + POIs** colocados manualmente (pueblos, dungeons, landmarks)
- **Relleno procedural** entre POIs (foliage, rocks, debris)
- **Validación de navegación** (navmesh, cover, sightlines)

---

## Reglas Transversales (aplican a todos los perfiles)

| Regla | Origen |
| :--- | :--- |
| **Generar piezas es producción; ensamblar es diseño** | tanda-06, tanda-09, tanda-11 |
| **Slop = IA "repartiendo" assets sin intención** | tanda-06 |
| **Ancla de escala: arrancar por elemento conocido** | tanda-09, tanda-11 |
| **Grandes primero, accesorios en última milla** | tanda-09, tanda-11 |
| **Reutilizar > generar** (cortar roca, Bézier rope) | tanda-11 |
| **Pregunta de camino antes de generar** (generar/modificar/primitiva/comprar) | tanda-11 |
| **Recortar lo invisible** (knife/boolean) | tanda-11 |
| **Consolidar materiales al ensamblar** | tanda-11 |
| **Referencia fijada en superficie de trabajo** | tanda-06, tanda-11 |
| **Organizar en colecciones desde día 1** | tanda-11 |
| **Primitivas + Modificadores > IA Placement** | tanda-09, tanda-11 |
| **Referencia de escala exportada del motor ANTES** | tanda-09, tanda-11 |
| **Pasada de luz/atmósfera = gate visual** | tanda-09 |
| **Foliage/agua dinámicos: comprar, no generar** | tanda-11 |
| **Wireframe perfecto no necesario para estáticos** | tanda-11 |
| **Decimate en Blender para low-poly rápido** | tanda-11 |
| **Prototipo jugable > perfección** | tanda-11 |
| **Assets generados en un estilo = cohesión gratis** | tanda-11 |

---

## Dead-ends / Limitaciones Actuales

| Tarea | Estado |
| :--- | :--- |
| IA placement que produzca nivel dirigido (no slop) | No resuelto; "menos controlable" |
| Generar geometría compleja (cuevas, interiores) con IA | "Menos controlable" → primitivas + modificadores |
| Foliage/agua procedural con IA | "Mejor comprar hoy; IA lo hará procedural más adelante" |
| Exportar nivel Blender → UE con materiales exactos | "No descubrí cómo... normalmente reconstruyes el shader en UE" |
| Navegación procedural validada sin playtest | Requiere playtest humano |

---

## Dónde Encaja en el Framework

| Documento | Relación |
| :--- | :--- |
| `pipeline-assets.md` | Proveedor de piezas (kit) |
| `produccion-vfx.md` | Iluminación, niebla, atmósfera, VFX ambientales |
| `dimensiones-juego.md` #4 | Mapas/niveles (layout, progresión, densidad) |
| `herramientas-y-apis.md` | Criterios de selección (motor, editor, terrain tools) |
| `ruta-produccion.md` | Router según perfil de nivel |
| `ciclo-produccion.md` | Fases Prototipo / Producción / QA |
| `escalas-aceptacion.md` | Estados de aceptación por nivel |
| `conocimiento/` | Lecciones aprendidas por perfil |
| `pipeline-navegador.md` | Pipeline completo navegador: Rust/WASM + framework WebGL + librería networking + herramienta de sprites 2D |
| `agentes-especializados.md` | Agente artista especializado: sandbox isolation, self-healing, blend shapes, decoupling |

---

## Verificación Pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real, y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
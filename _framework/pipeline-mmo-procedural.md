# Pipeline MMO Procedural en Navegador (Three.js) 🌐

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-12-mmo-gamejam.md` (Game Jam 30 días, 90% IA, MMO en Three.js con mundo infinito — **evidencia alta**: juego jugable funcionando en navegador, 1º en votación comunitaria 4.6/5; contra: **vende curso** — incentivo de fluidez). Los nombres de productos no entran; las prácticas, con verificación pendiente.
> **Restricción clave:** 30 días, 90% código por IA, sin motor tradicional (Three.js puro en navegador).

---

## Pipeline "MMO Procedural Browser" (30 días, 1 persona)

| Fase | Tiempo aprox | Qué hace |
| :--- | :--- | :--- |
| Concepto + research (tutoriales engine tradicionales) | ~3 días | Perlin noise, shaders, chunk loading, alpha maps, IK |
| Terreno infinito (Perlin noise + chunk loading) | ~5 días | Ruido coherente, solo render cerca del jugador |
| Vegetación (grass shader + alpha map trees) | ~4 días | Grass shader con Perlin wind, alpha map trees, verticalidad |
| Personaje + animaciones + IK | ~5 días | Generado por IA, rigging, escalar con IK (pie only) |
| Sistemas gameplay (supervivencia, building, recursos) | ~6 días | Hambre, construcción, recursos, vaquitas, enemigos (cortados) |
| Multiplayer (Colyseus + Node.js) | ~7 días | Sincronización, lag, hacks, servidor, inventario compartido |
| Polish (día/noche, post-process, cartoon shader) | ~3 días | Ciclo día/noche, post-process, shader cartoon |
| Bug fixing / corte de features | ~7 días | Enemigos, combate avanzado, skills, ropa/armadura cortados |
| **Total** | **~30 días** | MMO jugable en navegador |

> **Restricción declarada:** 30 días ejecución pura; ideación no contada.

---

## Reglas Operativas Transferibles

| Regla | Por qué |
| :--- | :--- |
| **Debuggers/parameter UIs para la IA** | "Siempre pedí a la IA crear un debugger donde pudiera ajustar todos los parámetros... es un proceso similar a una engine de juegos" — evita el "aceptar o pedir ajustes con texto, que es muy impreciso" |
| **Perlin noise = navaja suiza** | Terreno, grama (wind), árboles (alpha maps), humo, agua, movimiento, nubes — una técnica, mil usos |
| **Chunk loading + distance culling = mundo infinito viable** | "El mundo es infinito, pero no se procesa todo... la grama solo renderiza cerca del personaje" — obligatorio en navegador |
| **Alpha maps > geometría para foliage** | "Árboles = plano + alpha map... blanco = render, negro = excluye... gira hojas, vegetación" — 100x más barato que geometría |
| **Verticalidad = interés visual + gameplay** | "Puntos altos (montañas, rocas) hacen que el jugador quiera ir allí" + escalar con IK |
| **Day/night + post-process + shader stylized = "mitad del look"** | Ciclo día/noche + post-process + cartoon shader = atmósfera vendible |
| **Inverse Kinematics (IK) solo donde impacta** | Pie = sí (evita pie flotando en pendiente); mano escalando = "difícil, perdí mucho tiempo, dejé solo pie" |
| **Multiplayer = dolor de cabeza exponencial** | "Sincronización, lag, ping, hacks, scripts que tiran servidor... valió video solo" — Coliseus ayuda pero no magia |
| **IA degrada con codebase grande** | "Cuanto más código, más contexto, más dificultad para la IA... al final es caos" — contexto pequeño = IA perfecta; grande = caos |
| **Debuggers propios > prompts de texto** | "Crear debugger donde ajusto parámetros... similar a engine... ajusto altura grasa, fuerza viento, etc." — UI > texto |
| **Game Jam evaluation: fun vs polish** | "2 personas sin exp dev cortaron 900 juegos... juzgar solo por 'diversión' desbalancea" — métrica única = sesgo |
| **Comunidad vs jurados** | 1º en votación comunitaria (4.6/5, 310 reviews) vs no top 30 en jurados — "un jurado dijo top 10/top 3" |
| **Cortar features sin piedad** | "Corté enemigos, combate avanzado, skills, ropa/armadura... lo único que no podía faltar era multiplayer" |
| **IA degrada con codebase grande** | "Cuanto más código, más contexto, más dificultad... al final es caos. Código base pequeño = IA perfecta; grande = caos" |
| **UI/debugger propio > prompts** | "Crear debugger donde ajusto parámetros... similar a engine... ajusto altura grama, fuerza viento" — UI > texto |

---

## Pipeline Técnico Específico (Three.js Browser)

### Terreno Infinito Procedural
| Técnica | Implementación |
| :--- | :--- |
| **Perlin noise 3D/2D** | Terreno, grama (wind), árboles (alpha), humo, agua, nubes |
| **Chunk system** | Solo chunks cerca del jugador existen en memoria |
| **Distance culling** | Grama/terreno/objetos solo renderizan cerca del jugador |
| **Mesh instancing** | InstancedMesh para grama/árboles/rocas = 1 draw call |

### Vegetación
| Elemento | Técnica |
| :--- | :--- |
| **Grass** | InstancedMesh triángulos + vertex shader (Perlin wind) + distance culling |
| **Trees** | Alpha map en plano (blanco=render, negro=transparent) + múltiples planos paralelos |
| **Bushes** | Reutilizar hojas de árboles (misma textura, distinto material) |
| **Rocks/Verticalidad** | 2 modelos roca + dispersión aleatoria + escalado = "quiero ir allí" |

### Atmosphere & Rendering
| Feature | Técnica |
| :--- | :--- |
| **Day/Night cycle** | Shader skybox + light direction + color temperature lerp |
| **Post-processing** | Bloom, color grading, vignette, cartoon outline (shader) |
| **Cartoon shader** | Cel shading + outline (sobel/fresnel) |
| **Fog/Atmosphere** | Exponential fog + height fog + volumetric clouds (shader) |

### Personaje & Animación
| Feature | Técnica |
| :--- | :--- |
| **Generación** | IA genera modelo (rig-ready) |
| **Rigging** | AccuRig/Mixamo + fix pesos manuales |
| **Animations** | Referencias video → IA genera keys → feedback visual (set pose) |
| **IK (Inverse Kinematics)** | Solo pie (evita pie flotante en pendientes); mano escalando = descartado por tiempo |
| **Climbing** | Raycast + IK pie + animación trepar + estado "climbing" |

### Gameplay Systems
| Sistema | Estado |
| :--- | :--- |
| **Survival (hambre, sed, vida)** | Implementado |
| **Building (paredes, rampas, pisos, techos, puertas, baúles, fogata)** | Implementado |
| **Recursos (vaquitas, recolección)** | Implementado |
| **Enemigos / Combate avanzado** | **Cortado** por tiempo |
| **Habilidades especiales / Ropa / Armadura** | **Cortado** por tiempo |

### Multiplayer (Colyseus + Node.js)
| Aspecto | Detalle |
| :--- | :--- |
| **Library** | Colyseus (autor brasileño Wendel) |
| **Servidor** | Node.js + Colyseus |
| **Sincronización** | Posición, rotación, animación, inventario, construcciones, vacas |
| **Desafíos** | Lag, ping alto, hacks, scripts que caen servidor, sincronización perfecta |
| **Arquitectura** | Authoritative server + client prediction + reconciliation |

### Optimización Navegador (Claves)
| Técnica | Por qué |
| :--- | :--- |
| **InstancedMesh** | 1 draw call para miles de instancias (grass, trees, rocks) |
| **Distance culling** | Solo render cerca del jugador (frustum + distance) |
| **Chunk loading/unloading** | Chunks lejos se descargan de memoria |
| **Shader-based animation** | Grass wind, tree sway en GPU (vertex shader) |
| **Texture atlasing** | Menos draw calls, menos texture binds |
| **Compression** | Draco/GLTF compression para modelos |

---

## Reglas Operativas Transferibles (Consolidado)

| Regla | Origen |
| :--- | :--- |
| **Debuggers/parameter UIs para la IA** | tanda-12 |
| **Perlin noise = navaja suiza (terreno, grass, trees, wind, smoke, water)** | tanda-12 |
| **Chunk loading + distance culling = mundo infinito viable en browser** | tanda-12 |
| **Alpha maps > geometría para foliage** | tanda-12 |
| **Verticalidad = interés visual + gameplay (escalar)** | tanda-12 |
| **Day/night + post-process + stylized shader = "mitad del look"** | tanda-12, tanda-09 |
| **IK solo donde impacta (pie sí, mano no)** | tanda-12 |
| **Multiplayer = complejidad exponencial (Colyseus ayuda pero no magia)** | tanda-12 |
| **IA degrada con codebase grande (contexto)** | tanda-12 |
| **Debuggers/parameter UIs propios > prompts de texto** | tanda-12 |
| **Evaluación Game Jam: fun vs polish = sesgo si métrica única** | tanda-12 |
| **Comunidad vs jurados expertos = resultados divergentes** | tanda-12 |
| **Cortar features sin piedad para cumplir deadline** | tanda-11, tanda-12 |
| **IA degrada con codebase grande (contexto window)** | tanda-12 |
| **UI/debugger propio > prompts de texto** | tanda-12 |
| **Evaluación: fun vs polish = sesgo si métrica única** | tanda-12 |
| **Comunidad vs jurados = resultados divergentes** | tanda-12 |
| **Cortar features sin piedad** | tanda-11, tanda-12 |

---

## Dead-ends / Limitaciones Actuales (fecha: tanda-12)

| Tarea | Estado |
| :--- | :--- |
| Multiplayer complejo (combate, inventario compartido, lag, hacks) en < 1 semana | **Muy difícil**; valió video solo; Coliseus ayuda pero no magia |
| IA manteniendo coherencia en codebase > 10k líneas | **Degrada severamente**; contexto window overflow |
| IK mano para escalar (preciso) | **Descartado**; "perdí mucho tiempo, dejé solo pie" |
| Combate avanzado + skills + inventario compartido multiplayer | **Cortado** por tiempo |
| Ropa/armadura dinámica con física | **Cortado** por tiempo |
| Acceso a modelos frontera (Opus 5, Fable 5) desde fuera de US | Geo-blocking |
| IA manteniendo coherencia en codebase grande | Contexto window overflow → caos |
| Evaluación Game Jam: 2 personas no-dev cortan 900 juegos | Sesgo masivo; "juzgar solo diversión desbalancea" |
| Jurados expertos vs votación comunitaria | Resultados divergentes; "un jurado dijo top 10/top 3" |

---

## Dónde Encaja en el Framework

| Documento | Relación |
| :--- | :--- |
| `pipeline-assets.md` | Perfil `entorno-procedural-infinito`, `vegetacion-shader`, `personaje-3d-stylized` |
| `pipeline-nivel.md` | Perfil `procedural-asistido` + `arena-sandbox` (chunk loading, POIs) |
| `pipeline-mmo-procedural.md` | **Este documento** — pipeline completo MMO browser |
| `pipeline-assets.md` | Perfiles `entorno-procedural-infinito`, `vegetacion-shader`, `personaje-3d-stylized` |
| `produccion-vfx.md` | Grass shader, alpha maps, day/night, post-process, cartoon shader |
| `pipeline-nivel.md` | Perfil `procedural-asistido` + `arena-sandbox` (chunk loading, POIs, infinite terrain) |
| `produccion-vfx.md` | Grass shader (Perlin wind), alpha map trees, day/night, post-process, cartoon shader, IK foot |
| `pipeline-mmo-procedural.md` | **Este documento** — pipeline completo MMO browser |
| `herramientas-y-apis.md` | Matriz: Three.js/WebGL, Colyseus, Perlin noise libs, shader debugging |
| `ruta-produccion.md` | Fila: "MMO procedural browser (Three.js, infinite world, multiplayer)" |
| `ciclo-produccion.md` | Fases comprimidas en 30 días (Game Jam constraints) |
| `escalas-aceptacion.md` | Estados de aceptación por feature (multiplayer = hardest gate) |
| `conocimiento/` | Lecciones: IA degrada con codebase grande, debuggers > prompts, multiplayer hard |

---

## Verificación Pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real (Three.js browser), y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
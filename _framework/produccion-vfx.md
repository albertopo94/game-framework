# Producción de VFX con Agentes ⚡

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-07-vfx-workflow.md` (mismo canal que tandas 5-6: construyó la demo completa en pantalla — evidencia buena — pero **vende un curso de 3D AI**; incentivo de hacerlo ver fluido y de destacar herramientas concretas). Los nombres de productos no entran; las prácticas, con verificación pendiente.
> **Origen del creador:** "no soy artista de VFX en absoluto" — el workflow es desde la perspectiva de un no-especialista que usa agentes.

## Regla central: concepting antes que implementación

El patrón que se repite: **ningún VFX entra al motor sin haber pasado por una fase de concepting 2D**.

- Para cada VFX significativo (ataque, escudo, level up, captura, status effects), se genera primero una **lista de conceptos 2D** con el agente (GPT/Claude recientes).
- El concepting permite **iterar en segundos** lo que en el motor serían horas. El agente entrega variaciones; el creador selecciona o pide corrección ("más lento", "más partículas", "diferente color").
- Solo **tras validar el concepto** se pasa a implementación en motor.
- Excepción: VFX "directos" (una flecha con sangre) donde no hay ambigüedad — allí se salta el concepting y se describe una vez al agente de implementación.

> **Regla transferible:** *el coste de corregir un concepto en 2D es casi cero; el coste de corregir un VFX ya implementado en motor es alto.* Por tanto, todo VFX con ambigüedad visual entra al pipeline de concepting primero.

## VFX Library: catálogo vivo del juego

El creador construye una **biblioteca de VFX del juego** (VFX library):

- Catálogo de todos los efectos que el juego necesita (ataques, escudos, stun, heal, level up, captura, auras, etc.).
- Cada entrada: nombre, referencia visual (concepto aprobado), timing, capas, trigger en motor, estado.
- Sirve para: no duplicar, mantener coherencia visual, saber qué falta, reusar efectos base.

> **En nuestro framework:** esto es un archivo del juego (ej. `mis-juegos/<juego>/vfx-library.md`) que vive junto a `00-estado-produccion.md` y se actualiza en cada sesión que toque VFX.

## Referencias antes de describir: el atajo del no-especialista

El creador admite: *"para la mayoría de efectos, ni sé cómo describirlos"*. Su solución:

1. Usa **bibliotecas de referencia** (ej. *Cartoon Effects* de Jean Moreno) — páginas con cientos de VFX clasificados.
2. Busca en la librería algo parecido a lo que quiere, **envía el enlace/imagen al agente** con instrucción: *"algo como esto, pero color X, más extruido"*.
3. El agente ya tiene la semántica visual del referente y produce lo pedido.

> **Regla:** *no intentes describir un efecto visual con palabras si existe una imagen que lo define.* La referencia es el contrato; la descripción es el delta.

## VFX Concept = referencia + timing + capas

Un VFX concept aprobado para implementación incluye:

| Campo | Qué es |
| :--- | :--- |
| Referencia visual | Imagen/concepto 2D aprobado (o enlace a librería + delta) |
| Timing | Duración, frames clave, *channeling time*, *release*, *impact frame* |
| Capas | Separación explícita: 3D mesh en armadura + partículas + shader + post-proceso |
| Trigger | Qué evento del juego lo lanza (input, proximidad, HP, channeling) |
| Comportamiento de borde | Qué pasa si se cancela, se interrumpe, se solapa con otro |

> **En la tanda:** el concept del *Roots* incluye "boom roots link release", "roots separate", "falling leaves", "drifting leaves", "channeling link" — cada uno con su frame.

## Personaje optimizado = agente feliz

El VFX del personaje (Dread) funciona porque el asset está **preparado para ser procesado por agentes**:

- Mesh separado en partes lógicas (cuerpo, cabeza, ramas, hojas).
- UVs inteligentes (smart UV) y mapas de color limpias → permiten color correction, metallic/roughness por agente.
- Hojas como **objetos/materiales separados** (no unidos al cuerpo) → animables por viento, cambio de color, transparencia, exportables para VFX de partículas.
- Rig en partes: Mixamo/AccuRig para lo humanoide; GPT para lo custom (ramas, raíces) — partes separadas, **un solo armature al exportar**.
- Mesh optimizado (decimate a ~1k polys por roca) + normal map bakeado desde high poly.

> **Regla:** *un asset que el agente no puede leer/editar limpiamente es un bloqueo de VFX.* La preparación del asset (UV, separación, naming, optimización) es **trabajo previo al VFX**, no parte del VFX.

## Pipeline de textura: AI + retoque humano = calidad

- Color base generado por AI (Gemini/Nano Banana) → retoque puntual en **Moondiff** (paint over áreas rotas, detalles, logos) → **bake** de color correction (gamma, contraste, RGB curves) a textura final.
- PBR: roughness/metallic pintados a mano en *texture paint* (fill brush con valores) → para control fino que AI no da.
- Seamless textures para superficies grandes: **Patina AI** / *seamless texture AI* → preview 3D + mapas (base, normal, roughness, metallic, height/displacement).

## Rigging híbrido: estándar + agente

- Parte humanoide: **Mixamo / AccuRig** (automático, probado).
- Partes custom (ramas, raíces, hojas): **GPT** escribe el script de rigging (huesos, pesos, constraints) → se revisa en Blender.
- **Un armature único al exportar** (todo bajo el mismo root) aunque el rig se haya hecho en partes.

## Animación: referencias → agente → corrección

- Recolecta **referencias de video** (Mixamo, clips de juegos, video AI generados con Kling/Runway/Hunyuan).
- Para lo custom: **video AI como referencia de movimiento** (aunque falla en cosas complejas como movimiento de raíces) → se entrega a GPT como "mira este video, haz la animación" → GPT escribe el código/keys y **lo hace mejor que el video AI**.
- Herramienta de apoyo: **plugin casero** (click "set pose" en timeline) para dar feedback preciso al agente ("en frame 12 la rama está muy baja").

## Implementación en motor: iteración visual, no código ciego

El agente (GPT) recibe el VFX concept + asset preparado + animaciones y **escribe el código del motor** (Unreal/Unity/Godot):

- Partículas (Niagara/Cascade/Particles2D), shaders, materials, timelines, blueprints/scripts.
- Iteración: *"muy rápido"*, *"añade más partículas en el impacto"*, *"el escudo debe pulsar al recibir daño"*.
- La **playground de VFX** (escena de test aislada) permite ver el efecto en contexto sin recompilar el juego entero.

## Reglas operativas duras (transferibles al framework)

| Regla | Por qué |
| :--- | :--- |
| **Concepting 2D obligatorio para VFX ambiguos** | Ahorra iteraciones en motor; el concepto es el contrato |
| **VFX library viva por juego** | Evita duplicados, mantiene coherencia, visibiliza gaps |
| **Referencia visual antes que descripción** | El agente entiende la semántica visual del referente; el delta es barato |
| **VFX concept = referencia + timing + capas + trigger + bordes** | Sin esto, la implementación es adivinanza |
| **Asset listo para agente = UV limpio, partes separadas, naming, optimizado** | Un asset sucio bloquea al agente y produce VFX rotos |
| **Textura: AI base + retoque puntual humano + bake final** | AI no da PBR profesional; el humano cierra lo que AI no resuelve |
| **Rigging híbrido: estándar automático + agente para lo custom** | Lo estándar no necesita agente; lo custom sí, y el agente lo hace bien si el mesh está limpio |
| **Animación: referencias de video → agente corrige lo que el video AI falla** | Video AI genera movimiento; agente entiende la intención y la limpia en código/keys |
| **Implementación en motor: playground de test + iteración verbal** | Ver en contexto real antes de integrar; el agente itera rápido si el feedback es visual |

## Dead-ends / limitaciones actuales (fecha: tanda-07)

| Tarea | Estado |
| :--- | :--- |
| Video AI (Kling/Runway/Hunyuan) para movimiento complejo (raíces, tela) | Falla; sirve solo como referencia bruta para el agente |
| Generar hojas/distribución procedural por agente | "Todavía tricky"; se hace manual (planos + texturas) |
| Video AI para run animation compleja | Falla; GPT lo hizo mejor a partir de la referencia bruta |
| VFX que requieren lógica de juego (guard al estar rodeada) | El agente implementa la lógica si se le da el trigger claro |

## Dónde encaja en el framework

| Documento | Relación |
| `produccion-assets.md` | Asset del personaje listo para VFX (UV, separación, naming, optimización) |
| :--- | :--- |
| `produccion-assets.md` | Asset del personaje listo para VFX (UV, separación, naming, optimización) |
| `montaje-de-niveles.md` | VFX de ambiente (aura de edificios, clima) se ensamblan igual que props |
| `herramientas-y-apis.md` | Matriz de capacidad: VFX-by-code en motores code-first = pendiente (ver fila añadida en tanda-06) |
| `escalas-aceptacion.md` | VFX concept = estado 2 (propuesta); implementación en motor = estado 3; comparación side-by-side en motor = estado 4; aprobación creador = estado 5 |
| `dimensiones-juego.md` #3 y #6 | Assets de VFX y profundidad de combate |
| `ruta-produccion.md` | Nueva fila: "Diseñar e implementar VFX" → `produccion-vfx.md` (este doc) |

## Productos nombrados (excluidos deliberadamente)

Tripo P2, Nano Banana Pro, Moondiff, Mixamo, AccuRig, Astra (plugin rigging), Kling/Runway/Hunyuan (video AI), Jean Moreno's Cartoon Effects, Patina AI, Motive, 3DI Studio, Houdini, Ultra Dynamic Sky/Weather. **No entran al catálogo**: el video vende un curso y tiene sponsors. Si un juego necesita la capacidad, la herramienta se evalúa contra `herramientas-y-apis.md` con nombre verificado en fuente.

## Verificación pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real, y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
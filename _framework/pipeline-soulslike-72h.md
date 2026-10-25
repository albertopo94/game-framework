# Producción de Nivel y Juego "Souls-like" en Restricción de Tiempo 🏰

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-09-soulslike-72h.md` (mismo canal que tandas 5-8: demo completa de nivel jugable en 72h visible en pantalla — **evidencia alta**: nivel Souls-like con jefe, personaje, ubicación, iluminación, niebla, VFX, todo funcionando en Unreal 5.8; contra: **vende curso 3D AI + workspace Mr. Mak** — incentivo de mostrar fluidez). Los nombres de productos no entran; las prácticas, con verificación pendiente.
> **Restricción declarada:** 72 horas (3 días) de ejecución pura; **ideación explícitamente excluida** ("dos o tres días más").

## Pipeline "High-Poly → Bake → Low-Poly" para Personajes y Entorno

El creador declara flujo distinto para personajes/entorno vs. tanda-08 (donde usaba normal maps desde color map). Aquí **sí hace high-poly → retopo → bake completo** porque busca calidad "realista estilizada" y control total.

| Paso | Qué hace | Herramienta | Decisión clave |
| :--- | :--- | :--- | :--- |
| 1. Sculpt high-poly | ZBrush / Blender sculpt mode (elastic grab, pinceles) | Blender | Combina todas las partes del personaje en un solo high-poly |
| 2. Retopología | Tripo (pestaña retopo, quads/triángulos) o Blender (decimate/retopo manual) | Tripo / Blender | Tripo da topología limpia; puede necesitar refinamiento manual de adherence |
| 3. UV | xatlas (interno) o Smart UV Project + UV Packer addon | Blender / Hunyuan (descarta: "largo y aleatorio") | xatlas interno o Smart UV + UV Packer |
| 4. Bake (Cycles) | Normal + AO + **Color** + roughness/metallic opcional | Blender Cycles | **Bakea color** → no necesita volver a texturizar si la forma high-poly está bien |
| 5. Low-poly texturing | Tripo (texturiza low-poly) o pintura manual | Tripo / Blender | Si bakea color, solo normal+AO en low-poly; flexibilidad para ajustar roughness/metallic on-the-fly |

**Regla del creador:** "Para recursos estáticos, personalmente no veo la necesidad de hacer un wireframe perfecto ni un UV perfecto... no afecta al rendimiento." → **Calidad " suficientemente buena" > perfección técnica**, salvo recursos reutilizables o trabajo en equipo.

## Texturas Tileables para Grandes Superficies (Patina / Seamless Texture AI)

| Necesidad | Solución | Por qué |
| :--- | :--- | :--- |
| Arena, muros, suelos grandes | **Patina AI** (fold.ai / plataformas) → genera base color + normal + roughness + AO + height/displacement desde imagen o texto | Tileables reales, calidad PBR superior a generadores de hace 10 años |
| Área circular del jefe | Textura proyectada en cilindro (imagen 2D → UV cilíndrica) | No hace falta geometría 3D; "definitivamente más barato" |
| Suelo con patrón radial | Área circular repetida en UV → "no es solo un área, van en círculos" | Evita repetición visible, usa UV para variar |
| Paths/caminos | Textura tileable + distribución con ruido/máscaras | Variación natural sin geometría extra |

**Regla:** *generar geometría para superficies planas grandes es desperdicio; textura tileable + displacement/normal hace el trabajo a fracción del costo.*

## Diseño Modular de Nivel: Primitivas + Modificadores (no generación IA)

| Técnica | Aplicación | Por qué no IA |
| :--- | :--- | :--- |
| **Array + Curve modifier** | Muros circulares, círculos de rocas, anillos de muros | "Generar eso a la vez no te llevará muy lejos... menos controlable" |
| Primitivas (cajas, cilindros) + scale/rotate | Núcleo de la arena, caminos, paredes, formas base | Control total, optimización nativa |
| Pinceles de terreno / herramientas nativas UE | Detalles pequeños (piedras que caen, arena) | Herramientas nativas diseñadas para eso |
| **Referencia de escala**: exportar esqueleto de UE como referencia de tamaño | Saber "qué hacer" sin adivinar escala | Evita rehacer por escala errónea |

**Regla central (reforzada de tanda-06):** *generar piezas es producción; ensamblar es diseño. Dejar que la IA "reparta" assets produce slop.*

## Personajes y Jefe: High-Poly Sculpt + Bake (no atajos de color-map)

Diferencia clave con tanda-08: **aquí sí hace high-poly → retopo → bake completo** para jefe y personaje principal.

- Sculpt en Blender (elastic grab, pinceles) → combina partes → high-poly único
- Retopo en Tripo (quads) o Blender (decimate manual donde Tripo falla adherence)
- UV: xatlas interno o Smart UV + UV Packer addon
- Bake en Cycles: **Normal + AO + Color + roughness/metallic opcional**
- Color bake → "no es necesario volver a la textura" si la forma high-poly está bien
- Flexibilidad post-bake: ajustar roughness/metallic on-the-fly en low-poly sin rebakear

**Regla:** *high-poly para calidad y control; low-poly para rendimiento. El bake transfiere el detalle; el low-poly es lo que corre en motor.*

## Integración Motor: Plantilla + MCP + Agente como Navegador (no Constructor)

| Componente | Qué usa | Qué hace el agente (Claude Code + Opus 5) |
| :--- | :--- | :--- |
| **Plantilla base** | "Souls-like team plate" de UE (Lyra-ish) | No la construye; la usa como **base sólida** |
| **MCP** | UE MCP nativo 5.8 + Vibe UE (mejor probado) | Conexión agente ↔ motor |
| **Claude Code + Opus 5** | Agente principal | **No construye el juego**; explora escena, dice "qué hacer" y "cómo está configurado", itera rápido |
| **Costo** | Opus 5 API = "una fortuna" si se usa fuera de suscripción | 72h = límite duro; no abusar de Opus 5 por API |

**Rol del agente:** *navegador de código + sugeridor de "qué hacer / cómo está configurado" → el humano ejecuta.* El creador aclara: *"no hice todo con Claude Code de esa manera que lo hizo por mí... le pedí que explorara mi escena y me dijera qué debía hacer."*

**Regla:** *usar plantilla + MCP + agente como navegador acelera 10x vs empezar de cero; pero el agente no sustituye la toma de decisiones de diseño.*

## Flujo de Ropa y Física (UE 5.8)

- Exportar con esqueleto correcto → retargeting → cloth assets → paint weights → colliders en huesos
- UE 5.8 actualizó el sistema: "más fácil / más rápido"
- Si hay problemas: hay videos dedicados (ropa / física general)

## Cinemáticas y Cámara via Agente

- **Caso de uso sorpresa:** movimiento de cámara / cinemáticas in-game
- Agente (Opus 5) escribe secuencias de cámara → "sorprendentemente buen trabajo"
- Con ayuda extra → "mucho mejor"
- Ejemplo: cámara de aparición del jefe al entrar por la puerta

## Costos y Realidad Económica

- **Opus 5 por API = "te va a costar una fortuna"** fuera de suscripción
- Comparativa: Opus 5 vs Kimi K3 vs GPT → Opus 5 gana en calidad, pierde en costo
- 72h = límite duro; no abusar de Opus 5 por API
- **Conclusión del creador:** "la IA es una gran herramienta... si la usas bien. Si aprendes sobre lo que estás haciendo. Si esperas simplemente eliminar algo de un solo golpe con la IA, será muy decepcionante."

## Reglas Operativas Transferibles

| Regla | Origen |
| :--- | :--- |
| **High-poly sculpt + bake completo para héroes/jefes; low-poly + tileables para entorno** | Decisión de calidad por rol del asset |
| **Texturas tileables + displacement para superficies grandes; no geometría** | Costo/rendimiento |
| **Ensamblaje modular con primitivas + modificadores (array/curve); no IA placement** | Control > velocidad ciega |
| **Referencia de escala exportada del motor antes de modelar** | Evita rehacer por escala |
| **Claude Code como navegador de código base + MCP; no constructor autónomo** | Acelera 10x vs cero, pero humano decide |
| **72h ejecución ≠ 72h totales** (ideación = 2-3 días extra) | Honestidad de alcance |
| **UV perfecto no necesario para estáticos; "suficientemente bueno" > perfección** | Tradeoff declarado |
| **Bake color en high-poly → no retexturizar low-poly** | Ahorro masivo si high-poly está bien |
| **Probar enfoques distintos (bake color vs no; retopo Tripo vs Blender) → mismo punto** | Flexibilidad de pipeline |

## Qué NO tomamos

- Nombres de productos (Tripo, Patina, xatlas, Opus 5, Vibe UE, Ultra Dynamic Sky/Weather, Aqua Rig, nano banana pro, etc.) — agenda de herramientas sigue criterios de `herramientas-y-apis.md`
- Cifras de tiempo ("1.5 días assets", "72h totales") — datos de flujo experto con time-lapse; útiles como orden de magnitud, no presupuesto propio
- "Join my course" / "like and subscribe" — marketing
- Wireframe perfecto como requisito — explícitamente descartado para estáticos

## Dónde encaja en el framework

| Documento | Relación |
| :--- | :--- |
| `pipeline-personaje.md` | Enfoque high-poly bake para héroes/jefes (vs. atajos tanda-08) |
| `produccion-assets.md` | Sculpt high-poly → retopo → bake workflow |
| `montaje-de-niveles.md` | Modular level design con primitivas + modificadores |
| `produccion-vfx.md` | Iluminación, niebla, atmósfera como "mitad del look" |
| `herramientas-y-apis.md` | Matriz: character pipeline (high-poly bake) + environment pipeline (tileables) |
| `ruta-produccion.md` | Fila: "Proyecto completo bajo restricción de tiempo con plantilla + MCP" |
| `ruta-produccion.md` | Fila: "Explorar escena y navegar código base con agente" |

## Verificación pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real, y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
# Estrategia de Prompting Puro para Juegos en Navegador 🎮

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-10-prompting-strategy.md` (video de un creador que construye juegos completos en Three.js/HTML **solo con prompting estratégico** — sin motores, sin MCPs, sin herramientas externas. Evidencia: arcade jugable público con decenas de builds; contra: **vende sus skills por $9** — incentivo de mostrar fluidez). Los nombres de productos no entran; las prácticas, con verificación pendiente.
> **Diferencia clave con tandas 5-9:** aquí **no hay motor, no hay Blender, no hay MCP** — el LLM *es* el motor de desarrollo. El framework agnóstico debe contemplar este modo "prompt-only".

## El Proceso de 7 Pasos (núcleo del método)

| Paso | Qué hace | Clave |
| :--- | :--- | :--- |
| **1. Escribir el prompt inicial** | Prompt corto (promedio 44 palabras), lenguaje simple, 6 tipos según objetivo | No sobre-ingeniar; breve y claro |
| **2. Dar un target (referencia)** | 4 tipos: screen recording > imagen objetivo > mockup generado > investigación/planos reales | "Imágenes vencen a párrafos; grabaciones vencen a ambas" |
| **3. Dejarlo correr (loop)** | Ejecutar en bucle hasta meta numérica (ej. "9/10") o tiempo; los modelos paran solos si no se les dice que sigan | "Run until 9/10" o "run X horas" |
| **4. Jugar el build** | Entrar, probar, sentir; llamar lo bueno y lo malo en tiempo real | Feedback humano = señal de verdad |
| **5. Puntuar y revisar** | Score 1-10 + 2-4 problemas específicos + meta numérica + tiempo acotado | "3/10 → 9/10 en 2h; problemas: X, Y, Z" |
| **6. Convertir victorias en skills** | Extraer lo que funcionó bien a skill reutilizable; apilar skills entre builds | Biblioteca de skills compuestos |
| **7. Shippear** | Showcase mode + playability pass + trailer 30s + página arcade pública | "No abrir en pantalla negra" |

---

## 1. Los 6 Tipos de Prompt Inicial

| Tipo | Cuándo | Estructura |
| :--- | :--- | :--- |
| **Oneliner** | Test rápido de modelo nuevo | "Build me a game like Star Wars Rogue Squadron" |
| **Oneshot** | Comparar modelos al salir uno nuevo | 3 párrafos: "one shot, best foot forward" + expectativas + "showcase your capabilities" |
| **Clone** | Replicar juego existente (Wii Rule, etc.) | Link Wikipedia/Steam + "loop 6h, 9/10 closeness, do not stop early, no mobile optimize" |
| **Vision con lista** | Juegos robustos con alcance definido | Visión narrativa + lista explícita de modelos/ubicaciones + "mindblowing detail" |
| **Overnight** | Maximizar uso de tokens nocturnos | "Run until midnight / until token reset / X hours" + expectativas |
| **Upgrade pass** | Juego existente que necesita pulido | "3 additional hours of upgrades" sobre build existente |

**Regla de oro:** *promedio 44 palabras en prompt inicial*. No sobre-ingeniar. Lenguaje simple como brief a persona normal.

---

## 2. Las 4 Referencias para el Target (Calidad)

| Tipo | Qué es | Cuándo |
| :--- | :--- | :--- |
| **Screen recording** | Grabación de gameplay de referencia | Siempre que sea posible; "hace el mejor trabajo mostrando exactamente qué quieres" |
| **Imagen objetivo** | Screenshot del problema exacto (ej. pierna fusionada a escoba) | Bug visual específico |
| **Mockup generado** | GPT image gen crea mockup de calidad objetivo ("highest quality this model can hit") | Estilo gráfico, atmósfera, "nail the style" |
| **Investigación/planos reales** | Blueprints, charts, layouts reales (Hogwarts, NYC, Dunder Mifflin) | Lugares reales, escala exacta |

**Jerarquía:** *screen recording > imagen > mockup > investigación*. "Palabras como gorgeous/mindblowing ponen el mood, pero no ponen la barra de calidad."

---

## 3. El Loop: "Run Until Goal"

- **Por defecto los modelos paran** en cuanto tienen algo que corre. Esa primera versión casi nunca es buena.
- **Framing:** "run for X hours" o "loop until 9/10" o "do not stop early".
- **Nocturno:** "run until midnight" o "until token reset" para maximizar plan.
- **Anti-parada prematura:** prompt explícito "do not stop early / do not stop until 9/10 / minimum X hours".
- **Costo:** planes 20x ok; planes 5x "no super feasible". Reservar para builds serios (Hogwarts, Opus Ring, Darth Maul).

---

## 5 Puntuar y Revisar: 5 Principios

1. **Decir qué funciona** (empezar por lo bueno).
2. **Dar score numérico** (1-10).
3. **Decir dónde debe aterrizar** (meta numérica: "3/10 → 9/10").
2. **Listar 2-4 problemas específicos** (tamaño de ronda: ni vago ni exhaustivo).
5. **Dar tiempo acotado** ("next 2 hours exclusively on this").

**6 tipos de notas de revisión:**
| Tipo | Qué hace |
| :--- | :--- |
| **Polish pass** | Pulido general de feel/visuales |
| **Specific issue pass** | Arreglar bug/problema concreto |
| **Lock and focus pass** | "Solo trabajá en X, ignorá lo demás" |
| **Praise and set the gap** | "Esto está genial; ahora el gap a cerrar es X" |
| **Quick fix pass** | Arreglos rápidos de alto impacto |
| **Prefilming sweep** | Barrido final antes de grabar/publicar |

---

## 6. Convertir Victorias en Skills (Biblioteca Compuesta)

| Principio | Práctica |
| :--- | :--- |
| **Si algo salió espectacular, no lo rehagas** | Conviértelo en skill reutilizable |
| **Skills se apilan** | Voxel world skill + character kit + dark crawler kit = builds más rápidos |
| **Skills compuestos** | Stackear skill sobre skill sobre skill = builds exponencialmente más rápidos |
| **Ejemplos del creador:** | Voxel world skill (Port Solace, Rowanir, ancient Egypt) + Character kit (Darth Maul, Opus Ring, Night's Watch) + Dark crawler kit (Grimhold, Night's Watch, Opus Ring) |

**Regla:** *no volver a resolver lo ya resuelto*. Skill = calidad garantizada + tiempo cero.

---

## 7. Shippear: Del Build al Mundo

| Paso | Qué hace |
| :--- | :--- |
| **Showcase mode** | Todos capítulos seleccionables, tracks desbloqueados, fast travel unlock — fácil para jugador y para filmar |
| **Playability pass** | Agente juega toda la partida como jugador; nada roto |
| **Trailer 30s** | Agente captura trailer desde el archivo ("never open on black screen") |
| **Página arcade** | Pública, jugable gratis |

**Regla:** *nunca abrir en pantalla negra (primeros 1-1.5s negros = pierde viewer)*.

---

## Palabras que Pesan / Palabras que Sobran

| Incluir (peso) | Evitar (ruido) |
| :--- | :--- |
| "It should be able to" → lista de cosas que **tienen que funcionar** 1:1 indistinguibles | "How to build it" — no le digas cómo, confía en el modelo |
| "Carbon copy / 9/10 minimum / indistinguishable" | "May I go for hard / it should / it should not" — direcciones negativas débiles |
| "A fan should say: 'Holy cow, I can't believe AI built this'" | Design document completo (modelos nuevos no lo necesitan tanto) |
| "Showcase what you can do / first impression / best foot forward" | Invertir controles por defecto (fix QOL personal) |
| Calidad de vida: "do not invert controls" | Sobre-especificar implementación |

---

## Andamiaje Técnico (lo que el creador usa pero no enseña a fondo)

- **Modelos:** Opus 5.5, GPT-6, Astra, Kimi K3, Sonnet, etc.
- **Entorno:** Three.js / HTML / browser arcade (sin motor, sin MCP)
- **Skills:** biblioteca propia ($9 bundle) — Voxel world, Character kit, Dark crawler kit, etc.
- **Arcade propio:** página web donde publica y deja jugar gratis

---

## Dónde Encaja en Nuestro Framework

| Documento | Relación |
| :--- | :--- |
| `prompt-maestro-creacion.md` | Este proceso **es** un prompt maestro extendido y iterativo; valida que "prompt corto + loop + score" > "prompt gigante once" |
| `prompt-maestro-creacion.md` §6 | Los 6 tipos de prompt inicial mapean a la sección 6 (dimensiones activas) |
| `escalas-aceptacion.md` | Score 1-10 + meta numérica = implementación del estado 4 (verificado por agente) → 5 (aceptado por humano) |
| `higiene-de-trabajo.md` §6 | Skills = lecciones comprobadas que se promueven de `conocimiento/` a reutilizables |
| `produccion-assets.md` / `produccion-vfx.md` | Enfoque opuesto: aquí **no hay assets previos**, el LLM genera todo en runtime |
| `ciclo-produccion.md` | Este es un **ciclo alternativo** para juegos browser/Three.js; fases: Prompt → Target → Loop → Play → Score → Skill → Ship |
| `herramientas-y-apis.md` | Nueva categoría: "Pure LLM prompting for browser games" (Three.js, HTML Canvas, WebGL) |

---

## Qué NO Tomamos

- **Precio del bundle ($9)** — marketing.
- **Nombres de modelos específicos** (Opus 5.5, GPT-6, Astra, Kimi K3) — agnósticos; el patrón funciona con el "modelo frontera actual".
- **Cifras de tiempo de builds específicos** — datos de su flujo, no presupuesto propio.
- **Arcade propia** — infraestructura propia, no método.

---

## Verificación Pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real (browser/Three.js), y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
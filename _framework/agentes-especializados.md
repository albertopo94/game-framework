# Agentes Especializados: Patrones de Workflow 🎭

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-13-agent-driven-character.md` (mismo canal que tandas 5-12: pipeline de personaje con agente artista especializado — **evidencia media-alta**: personaje completo con animaciones, cloth, weapon, blend shapes, mag boots funcionando en motor; contra: **vende curso 3D AI** — incentivo de fluidez). Los nombres de productos no entran; las prácticas, con verificación pendiente.

---

## Patrón Central: Agente Artista Especializado con Sandbox Propio

> **Hallazgo central:** El creador delega **todo el arte** a un "artist agent" que tiene:
> - Su propio **sandbox/entorno** (herramientas, configuración, experiencia)
> - **Responsabilidad total** sobre su dominio (modelado, texturizado, rigging, animación, VFX)
> - **Autonomía** para decidir cómo ejecutar dentro de su dominio
> - **Experiencia acumulada** ("has experience doing lots of art and building up these processes")

> **Regla:** *No micromanagees el arte. Dale al agente su sandbox, sus herramientas, y déjalo trabajar. El humano dirige el "qué", el agente resuelve el "cómo".*

---

## Patrón: Prompting Iterativo con Separación de Responsabilidades

El flujo usa **6 prompts secuenciales**, cada uno con **alcance acotado y objetivo claro**:

| Prompt | Objetivo | Separación clave |
| :--- | :--- | :--- |
| **1. Concepto + Documentación** | 10 conceptos → elegir 1 + documentar proceso | Exploración vs compromiso |
| **2. Separar equipment** | Body limpio + equipment toggleable/swappable | **Body ≠ Equipment** (decoupling) |
| **3. Cloth & Motion** | Tela (Magica Cloth 2) + motion | Simulación vs geometría |
| **4. Weapon functional** | Staff Teal'c-style (pull, aim, blast) + shield | Funcionalidad > estética |
| **5. Variaciones + Blend Shapes** | Múltiples armaduras, blend shapes (músculo, cara) | **Variation system** (blend shapes = customizer) |
| **6. Mag Boots + Alien variants** | Magnetic boots (walk walls/ceilings) + variants | Feature específica + variantes |

**Regla:** *Un prompt = una responsabilidad. No pidas "haz el personaje completo". Pide "haz X, luego Y, luego Z".*

---

## Patrón: Agente Auto-Curativo (Self-Healing)

> **Observación:** El agente **detecta y corrige errores por sí mismo** sin instrucción humana:
> - Detectó "eye issue" → diagnosticó → corrigió automáticamente
> - "Wasn't something I had to really tell it to do, just kind of found that on its own"

> **Regla:** *Diseña prompts que permitan al agente validar su propio output. Pide "checkea tu trabajo y fixea lo que encuentres".*

**Implementación práctica:**
- Incluye en el prompt: "Después de generar, revisa tu trabajo por issues comunes (geometry, UVs, rigging, collisions) y fixea lo que encuentres antes de entregarme."
- El agente usa herramientas de diagnóstico propias (ej. "diagnosing-bugs skill")

---

## Patrón: Blend Shapes = Sistema de Variación de Bajo Costo

| Feature | Beneficio |
| :--- | :--- |
| **Muscle size, body, face variation** | NPCs únicos sin modelar desde cero |
| **Equipment variation** | Diferentes rangos/tiers de dificultad |
| **Character customizer ready** | Sliders automáticos → character creator instantáneo |
| **Costo** | "Muy bajo costo" vs modelar variantes separadas |

**Regla:** *Siempre pide blend shapes para body/face/equipment en personajes. Costo marginal ≈ 0, valor enorme para customization y variety.*

---

## Patrón: Separación Body / Equipment (Decoupling)

| Antes (acoplado) | Después (desacoplado) |
| :--- | :--- |
| Character = mesh único con equipment baked | Body limpio (base) + Equipment toggleable/swappable |
| Cambiar arma = rehacer personaje | Swap equipment en runtime |
| Variaciones = re-modelar | Blend shapes + equipment swap = combinaciones infinitas |

**Regla:** *Siempre separa body limpio de equipment. El agente genera body base + equipment como assets separados, toggleables en motor.*

---

## Patrón: Agente "Se Ejecuta Mejor Solo"

> **Cita textual:** *"Let the AI run it. It seems to do a drastically better job of running it than I do."*

> **Interpretación:** Cuando el humano micromanagea (da instrucciones paso a paso), el resultado es peor que cuando deja al agente **correr en loop con objetivo claro** (score, meta, tiempo).

**Regla:** *Define objetivo + constraints + meta de calidad → deja al agente correr en loop. Interviene solo para corregir rumbo, no para dar instrucciones paso a paso.*

---

## Costos Reales (Transparencia)

| Item | Costo |
| :--- | :--- |
| **Opus 5.5** (setting 2nd highest, no Ultracode) | ~55 créditos total (1 generación completa) |
| **generador 3D** | Free tier suficiente (créditos gratis) |
| **Tiempo** | "Couple hours running in background while other stuff is going on" |

**Regla:** *Siempre reporta costo real (créditos/USD/tiempo), no "es gratis". Registra en `00-estado-produccion.md`.*

---

## Dead-ends / Limitaciones (fecha: tanda-13)

| Tarea | Estado |
| :--- | :--- |
| Cloth en Unreal Engine | No probado; Magica Cloth 2 en Unity funciona bien |
| Rigging perfecto sin retoque humano | Siempre hay fix de pesos (hombros, dedos) |
| Weapon hold "two-handed vs one-handed" | Aún indeciso; agente lo hizo pero humano duda |
| Shield + weapon simultáneo | Aún por decidir cómo integrar |
| Blend shapes en motor (Unreal/Unity) | Funciona pero requiere setup correcto de drivers |

---

## Dónde Encaja en el Framework

| Documento | Relación |
| :--- | :--- |
| `pipeline-assets.md` | Perfil `personaje-3d-*`: blend shapes, equipment decoupling, cloth, rigging |
| `produccion-vfx.md` | Cloth (Magica Cloth 2), weapon VFX, mag boots |
| `pipeline-assets.md` | Perfil `personaje-3d-*`: blend shapes para variation/customizer |
| `herramientas-y-apis.md` | Matriz: Magica Cloth 2, blend shapes, agent sandbox |
| `reglas-sistema.md` | Agente auto-curativo, "deja correr al agente", sandbox isolation |
| `higiene-de-trabajo.md` | Specialized agent sandbox isolation |
| `ruta-produccion.md` | Fila: "Pipeline personaje con agente artista especializado" |
| `produccion-assets.md` | Blend shapes, cloth, rigging, weapon |

---

## Verificación Pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real, y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
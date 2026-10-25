# Prototipo Jugable en Fin de Semana (2 Días) 🎮

> **Estado: hipótesis de terceros, a verificar en nuestro entorno.** Destilado de `_framework/referencias/notas-creador/tanda-11-weekend-prototype.md` (mismo canal que tandas 5-10: demo completa de shooter top-down en 2 días visible en Unreal — **evidencia alta**: build jugable mostrado funcionando; contra: **vende curso 3D AI** — incentivo de fluidez). Los nombres de productos no entran; las prácticas, con verificación pendiente.

## Pipeline "Weekend Prototype" (2 días, 1 persona)

| Fase | Tiempo | Qué hace |
| :--- | :--- | :--- |
| Concepto + referencias visuales | ~1h | Imágenes generadas (GPT-4o), layout del mapa en papel |
| Generación personajes (Tripo, smart mesh, 20k polys) | ~30 min | Multi-view, smart UV, texturizado en Tripo |
| Rigging (AccuRig → Unreal skeleton → retarget) | ~20 min | AccuRig gratis, export UE5, retarget en motor |
| Animaciones | Retarget de plantilla | Usa plantilla UE ($50) + retarget |
| Assets entorno (Tripo, smart mesh, poly counts variables) | ~2h | Polys por tamaño (2k-12k), sin ediciones manuales |
| Materiales PBR (Patina AI, 8¢/generación) | ~30 min | Tileables para superficies grandes |
| Ensamblado nivel en Unreal (primitivas + assets) | ~4h | Primitivas + modifiers (array/curve) + assets |
| Foliage/agua comprados (paquete bosque $20, agua $50) | — | "Mejor comprar que generar con IA hoy" |
| Integración personajes + armas + retarget | ~30 min | 15 min por personaje |
| Polish (post-process, luces, niebla, VFX gratuitos) | ~2h | Ultra Dynamic Sky/Weather, VFX gratuitos |
| **Total** | **~2 días** | Build jugable funcional |

---

## Reglas Operativas Transferibles

| Regla | Por qué |
| :--- | :--- |
| **Plantilla base + iterar > empezar de cero** | "Team plate $50 con todo lo básico; itera encima" — acelera 10x vs cero |
| **Retarget > animar desde cero** | Plantilla UE trae animaciones; retarget en 15 min por personaje vs días animando |
| **AccuRig (gratis) + retarget en UE > rigging manual** | Marcadores → export UE5 skeleton → retarget en motor; 20 min por personaje |
| **Poly count por propósito** | 2-5k props pequeños, 10-12k grandes; "evalúa cuánto necesitas realmente" |
| **Smart mesh + multi-view (back/side obligatorio)** | Reduce fallos en back/side; retry gratis si falla |
| **Patina AI para tileables (8¢/generación, pay-per-use)** | PBR completo (base, normal, roughness, AO, height) para superficies grandes |
| **Foliage/agua dinámicos: comprar, no generar** | "Mejor comprar hoy; IA generará procedural más adelante" —草/árboles/agua animados comprados ($20 bosque, $50 agua) |
| **Assets generados en un estilo = cohesión visual gratis** | "Generados en un estilo → encajan sin horas de matching" |
| **Wireframe perfecto no necesario** | "Para estáticos, personalmente no veo necesidad... no afecta rendimiento" |
| **Decimate en Blender para low-poly rápido** | "Hice decimate y quedó perfecto; no necesité retopo manual en todo" |
| **Prototipo jugable > perfección** | "No es 100% listo; es prototipo jugable. Punto de partida para iterar" |

---

## División de Trabajo Agente ↔ Humano (esta tanda)

| Lo hace el agente/IA | Lo hace el humano |
| :--- | :--- |
| Generar modelos 3D (Tripo, smart mesh, multi-view) | Decidir poly count, elegir mejores generaciones |
| Generar texturas PBR tileables (Patina) | Elegir qué superficies necesitan tileables, pintar en landscape |
| Generar conceptos visuales (GPT-4o) | Curar, elegir dirección, iterar |
| Rigging automático (AccuRig) | Fix de pesos (pintar azul = peso 0), exportar UE skeleton |
| Retarget de animaciones (UE nativo) | Configurar retarget, fix pesos de ropa/capa |
| Generar texturas tileables PBR (Patina) | Pintar en landscape mode, ajustar escala |
| Colocación primitivas + array/curve modifiers | Decidir layout, composición, escala (referencia exportada de UE) |
| Foliage/agua/VFX comprados | Colocar, configurar, integrar |
| Cinemáticas/cámara | Dirigir, decidir qué mostrar |

---

## Dead-ends / Limitaciones Actuales (fecha: tanda-11)

| Tarea | Estado |
| :--- | :--- |
| Generar foliage/grass/agua procedural con IA | "Mejor comprar hoy; IA lo hará procedural más adelante" |
| Rigging perfecto sin retoque humano | Siempre hay fix de pesos (hombros, dedos, ropa) |
| Exportar materiales Blender → UE con misma config | "No descubrí cómo... normalmente reconstruyes el shader en UE" |
| Animaciones complejas (quadrupeds, cloth) sin fix manual | Requiere paint weights, colliders, retargeting |
| Acceso a modelos frontera (Fable 5, Opus 5) desde fuera de US | "No soy US residential... no tengo acceso a Fable 5" |

---

## Dónde Encaja en el Framework

| Documento | Relación |
| :--- | :--- |
| `pipeline-personaje.md` | Rigging AccuRig + retarget UE (vs. Mixamo+GPT tanda-08) |
| `pipeline-soulslike-72h.md` | Plantilla UE + retarget + foliage comprado (vs. high-poly bake) |
| `montaje-de-niveles.md` | Primitivas + array/curve para layout; foliage comprado |
| `produccion-assets.md` | Smart mesh + multi-view + poly count por propósito |
| `produccion-vfx.md` | VFX gratuitos + Ultra Dynamic Sky/Weather para atmósfera |
| `herramientas-y-apis.md` | Matriz: character pipeline (AccuRig + retarget), environment (tileables Patina) |
| `ruta-produccion.md` | Fila: "Prototipo rápido con plantilla + retarget + assets comprados" |
| `ciclo-produccion.md` | Prototipo (fase 3) en 2 días vs 72h tanda-09 |

---

## Productos Nombrados (Excluidos Deliberadamente)

Tripo (smart mesh, segmentación V2), GPT-4o (imágenes), Nanobanana Pro, AccuRig (gratis), Patina AI (fold.ai, pay-per-use), Unreal Engine 5.x, plantilla "Roguelike Top-Down Shooter" ($50), Ultra Dynamic Sky/Weather, styled forest pack ($20), styled water ($50), Fable 5 (acceso perdido por geo-blocking). **No entran al catálogo**: el video promociona su curso. Si un juego necesita la capacidad, la herramienta se evalúa contra `herramientas-y-apis.md` con nombre verificado en fuente.

---

## Verificación Pendiente

Cada afirmación de capacidad se confirma o descarta practicando en un juego real, y se registra en `conocimiento/`. Mientras tanto, esto planifica, no manda.
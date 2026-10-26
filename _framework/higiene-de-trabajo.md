# Higiene de Trabajo 🧹

> **Para qué sirve:** cómo se registran hallazgos, fixes y commits para que el trabajo sea trazable meses después. Aplica al framework, a los juegos y a los bugs por igual.
> **Origen:** patrones destilados del tracker de issues, los commits y la práctica de auditoría de `mr-mak-workspace` (ver `_framework/referencias/README.md`).

## 1. Un problema grande es un tracker, no un issue

Cuando se detecta una clase de problema (una auditoría, un sistema roto, una deuda estructural), se abre **un issue/registro padre** que:

- **Ancla la evidencia de origen**: commit exacto auditado, fecha, alcance cubierto ("`desktop`,`src`,`src-tauri`, workflows y skills").
- **Da la evaluación general primero**, incluso si es positiva. Decir qué está bien hecho hace creíble lo que está mal.
- **Se subdivide en un fix por ítem**, cada uno con su severidad: *"Sub-issues (one per fix)"*. Un fix por issue = un fix por PR = una unidad revisable.
- Marca qué ítems se trataron por vía privada y dónde vive ese detalle.

**Un tracker padre no se cierra mientras quede un ítem abierto.** Y un fix chico que se arregla "de paso" sin su ítem es trabajo invisible.

## 2. Hallazgo confirmado ≠ hallazgo observado

Un hallazgo de auditoría o review se marca como **confirmado** solo si pasó un control independiente. El patrón de referencia: *"eight areas, and each finding was checked by two independent reviewers. This PR fixes the confirmed findings."*

- Un agente (o persona) levanta el hallazgo; otro lo confirma o lo descarta.
- El fix se hace sobre los **confirmados**. Los descartados se registran igual, con su descarte y el porqué: evitan re-auditar lo mismo.
- Nuestro rol de crítico independiente (`reglas-sistema.md`) es la versión de un solo revisor; para temas de riesgo (datos, seguridad, economía del juego) se piden dos.

## 3. Un fix se referencia a sí mismo

- El trabajo de implementación **cita el issue/ítem que resuelve** en el mensaje de commit o PR. Sin referencia, el tracker no se puede cerrar.
- Un commit de integración nombra lo que integra: `Integrate PR #57 for the community update`, no `updates`.
- **Un commit = una unidad revisable.** Código y docs del mismo cambio van juntos; el trabajo de otra área no se mezcla "porque estaba abierto".

## 4. Verde no significa probado

Un check que **se salteó** casos no probó esos casos. Referencia explícita de su propia doc: *"without it they skip, so a green run has not proven the emitted framework WebGL compiles."*

- Cuando una verificación no cubrió algo, se dice. Un "pasó" que saltó el 80 % de los casos es más peligroso que un "falló".
- En `escalas-aceptacion.md` esto es evidencia negativa obligatoria; acá es disciplina de commit y de tracker.

## 5. Los modos asistidos son explícitos, opt-in y aislados

Nada que traiga descargas, dependencias o comportamientos ocultos entra al framework o a un juego en silencio. El patrón que se copia:

- **Prohibido código que descarga assets o meshes sin que se pida.** La promesa del proyecto se rompe en silencio.
- Un camino asistido (generación, proyección, integración externa) entra **marcado, opt-in y aislado** del núcleo: dependencias propias, activación propia, desactivable sin tocar el resto.
- Se ejecuta **solo cuando la condición real se cumple**; si no hay referencia que medir, se saltea por completo.

## 6. Convertir victorias en skills (biblioteca compuesta)

Cuando una parte de un build destaca y se cree reusable, **se convierte en skill** y se guarda en la biblioteca del proyecto (o del creador). Reglas:

- **No volver a resolver lo ya resuelto.** Skill = calidad garantizada + tiempo cero.
- **Skills se apilan**: Voxel world + Character kit + Dark crawler = builds exponencialmente más rápidos.
- **Skill = lección comprobada** que se promociona de `conocimiento/` (estado `comprobado`) a reutilizable.
- **Un disparador distinto, la frecuencia:** si la misma secuencia de pasos se reescribe a mano en más de una sesión, eso solo basta para fijarla como **procedimiento con orden fijo**, aunque no haya evidencia de que "salió bien". Ver `_framework/README.md` §Referencia o procedimiento.

*(Origen: `prompting-puro-browser.md` §6; ver `conocimiento/`.)*

## 7. Edición por lotes: commitear antes, verificar después

Un script que reescribe archivos puede dejarlos **vacíos** si falla a mitad (`open(p,'w')` trunca al abrir, no al escribir). Regla barata:

- **El estado previo tiene que estar commiteado** antes de una edición por lotes con script. La recuperación pasa a ser un comando en vez de reconstruir a mano.
- Construir el contenido en memoria (o en un temporal + rename) y escribir al final, nunca abrir en modo escritura con contenido que todavía puede fallar.
- **Verificar después:** `find . -name "*.md" -size 0` antes de commitear. Un segundo de check evita un archivo vacío versionado.

*(Origen: incidente propio documentado en `conocimiento/truncado-por-script-de-edicion.md`.)*

## 8. Límites declarados, no prometidos

Todo documento que describe una capacidad del framework o del juego declara **dónde es fuerte, dónde es flojo y qué está explícitamente afuera**. El patrón de referencia divide en tres: *Strong / Stylized-only / Out of scope today*, con el análisis de por qué.

Esto vale igual para nosotros: declarar límites es requisito de cualquier descripción de capacidad, incluida la de este framework (ver `_framework/README.md`). Una capacidad sin límites declarados es marketing, no documentación.

## 8. Dogfooding (comer tu propio perro)

**Usa tus propias herramientas para construir tus propios juegos.** Cuando construyes una herramienta (ej. herramienta de sprites 2D), **úsala tú primero** en un juego real. Los bugs que encuentres (3 manos, dirección errónea, walk cycles rotos) son los mismos que tendrán tus usuarios. Fixearlos en la herramienta beneficia a todos.

*(Origen: `pipeline-navegador.md` §herramienta de sprites 2D; tanda-13 §Patrón: Agente Auto-Curativo)*

## 10. Búsqueda antes de abrir

## 11. Mobile-first por defecto (si aplica)

Si el juego corre en navegador/móvil: **diseña para touch primero** (virtual analog stick, portrait mode, PWA, wake lock). El desktop es superset; lo que funciona en móvil funciona en desktop, no al revés.

*(Origen: `pipeline-navegador.md` §Optimizaciones Móvil)*

## 11. Búsqueda antes de abrir

Antes de registrar un bug o una propuesta: **buscar si ya existe**. Un duplicado cuesta dos veces: una para cerrarlo y otra para la conversación que genera.

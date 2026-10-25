# Conocimiento 📚

> **Qué vive acá:** las **lecciones de la práctica** — lo que se aprendió haciendo un juego o probando una herramienta, no lo que se estudió antes de empezar.
> **Origen:** patrón `knowledge/` destilado de `mr-mak-workspace`.

## Por qué es una carpeta separada

| | `_framework/` | `conocimiento/` | `referencias/` |
| :--- | :--- | :--- | :--- |
| **Qué es** | El método: cómo se trabaja | Lo que se aprendió haciendo | Material externo que se conserva verbatim |
| **Cambia cuando** | Se decide cambiar el método | La evidencia muestra algo | Nunca (se agregan archivos, no se editan) |
| **Ejemplo** | "toda mecánica se documenta con X plantilla" | "el export de Blender a Godot pierde la animación X si no se hace Y" | El GDD de Mass Flux, las tandas del creador |

Mezclar los tres contamina el método con anécdotas. Por eso van separados.

## Regla de origen (innegociable)

Una entrada de conocimiento **solo entra si hay práctica detrás**: un juego producido, una herramienta probada, un error observado, una comparación medida.

- **No entra** conocimiento preventivo copiado de documentación o tutoriales. Eso va a `herramientas-y-apis.md` como capability, o se espera a comprobarlo.
- **No entra** una observación de un solo flujo presentada como regla universal. Si es una observación, se etiqueta como tal.

## Formato de una entrada

Un archivo por lección, nombre kebab-case. Estructura:

```markdown
# <Verbo + qué se aprendió>

**Type:** bugfix | decision | discovery | pattern | tooling | preference
**Fecha:** YYYY-MM-DD
**Juego / contexto:** <de dónde salió>
**Evidencia:** <commit, captura, medición, playtest>

## Qué
Una frase de la lección.

## Por qué
Qué la motivó o qué la provocó.

## Consecuencia práctica
Qué hay que hacer distinto la próxima vez. Si esto es vacío, la entrada no sirve.

## Límites
Cuándo NO aplica. Qué es hipótesis y qué está comprobado.
```

## Cuándo se escribe

- Después de un bug que costó encontrar.
- Después de descubrir que una herramienta no hace lo que se asumía.
- Después de un playtest que contradice el diseño.
- Después de una decisión de diseño que se tomó con duda y salió bien o mal.
- Cuando el creador corrige al agente: la corrección **es** la lección.

## Estados de una entrada

| Estado | Significado |
| :--- | :--- |
| `observacion` | Pasó una vez, en un flujo concreto. **No es regla.** |
| `comprobado` | Verificado más de una vez o con medición explícita. |
| `regla-candidata` | Merece subir a `reglas-sistema.md`. Espera decisión del creador. |

**Las lecciones no se convierten en reglas del framework automáticamente.** El creador decide si una `regla-candidata` sube. Si sube, se mueve y la entrada original queda como referencia histórica con un enlace.

## Índice

| Entrada | Type | Estado |
| :--- | :--- | :--- |
| `entrada-pendiente-verificacion-mercado-steam.md` | discovery | `observacion` — **sin verificar**: no usar en decisiones |

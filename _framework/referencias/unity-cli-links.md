# Referencias Unity CLI — Documentación Oficial 📚

> **Curada el 2026-10-28** contra docs oficiales de Unity. Solo enlaces con utilidad práctica para nuestro framework (agentes + CLI + Pipeline).

---

## Imprescindibles (agregar a `herramientas-y-apis.md`)

| Enlace | Qué resuelve | Por qué importa para nuestro framework |
| :--- | :--- | :--- |
| **https://docs.unity.com/en-us/unity-cli** | Landing oficial | Punto de entrada único; versiones, instalación, requisitos |
| **https://docs.unity.com/en-us/unity-cli/use-unity-cli** | Guía de uso | Instalación, autenticación, workflows típicos (CI, agents) |
| **https://docs.unity.com/en-us/unity-cli/unity-cli-reference** | Referencia de comandos | Tabla completa: `open`, `build`, `pipeline`, `eval`, `projects`, `templates`, `assets` |
| **https://docs.unity.com/en-us/unity-cli/replace-mcp-server-unity-cli** | Migración MCP → CLI | **Crítico**: explica por qué el MCP in-editor está deprecado y cómo migrar al CLI |

---

## Referencia profunda (para `conocimiento/` o `herramientas-y-apis.md`)

| Enlace | Qué resuelve |
| :--- | :--- |
| **https://docs.unity.com/en-us/unity-cli/unity-pipeline/unity-pipeline-package** | Qué hace `com.unity.pipeline`, cómo se conecta al Editor, qué expone |
| **https://learn.unity.com/tutorial/6a7e194752fbca26e9ebccbe** | Tutorial oficial (puede ser útil para onboarding) |
| **https://docs.unity.com/en-us/unity-cli/release-notes** | Changelog para version pinning (qué cambió en cada versión) |

---

## Qué NO documentar (ruido)

| Enlace | Por qué |
| :--- | :--- |
| `https://docs.unity.com/en-us/unity-cli` (duplicado de la landing) | Redundante |
| Tutoriales de "cómo hacer un juego" | Fuera de scope (no es nuestro dominio) |
| Docs del Editor en general | Fuera de scope (nos interesa solo CLI + Pipeline) |

---

## Regla de mantenimiento

> **Actualizar estos enlaces cuando:**
> - Salga nueva major version de Unity (ej. 6 → 7)
> - Cambie el estado del MCP (deprecado → removed)
> - Salga nueva versión del CLI con breaking changes
>
> Verificar en: **release notes** + **replace-mcp-server-unity-cli** cada 3 meses.

---

## Qué agregar a `herramientas-y-apis.md` (sección Unity CLI)

```markdown
## Referencias oficiales (Unity CLI)

| Enlace | Qué es | Cuándo consultar |
| :--- | :--- | :--- |
| [Unity CLI Overview](https://docs.unity.com/en-us/unity-cli) | Landing oficial | Primera vez |
| [Use Unity CLI](https://docs.unity.com/en-us/unity-cli/use-unity-cli) | Guía de uso | Primera vez / onboarding |
| [CLI Reference](https://docs.unity.com/en-us/unity-cli/unity-cli-reference) | Tabla completa de comandos | Buscar comando/flags |
| [Replace MCP Server](https://docs.unity.com/en-us/unity-cli/replace-mcp-server-unity-cli) | Migración MCP → CLI | Si usabas el MCP in-editor |
| [Pipeline Package](https://docs.unity.com/en-us/unity-cli/unity-pipeline/unity-pipeline-package) | Qué expone `com.unity.pipeline` | Integrar agente |
| [Release Notes](https://docs.unity.com/en-us/unity-cli/release-notes) | Changelog | Version pinning |
```

> **Regla:** Estos son enlaces de **referencia**, no tutoriales. El framework enseña *métodos*; la doc oficial enseña *sintaxis*.

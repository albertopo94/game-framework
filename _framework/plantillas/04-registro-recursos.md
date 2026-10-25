# Plantilla: Registro de Recursos del Juego (Pendiente)

> **Estado: PENDIENTE** — Plantilla de pipeline no implementada aún.
> **Origen:** Referenciada desde `herramientas-y-apis.md` como destino para registrar costo real, licencia, origen y trazabilidad de recursos.

## Qué debe cubrir esta plantilla

Cuando se implemente, debe permitir registrar por cada recurso:

| Campo | Qué registrar |
| :--- | :--- |
| **Nombre del recurso** | Nombre interno único |
| **Tipo** | Modelo 3D / Textura / Audio / Shader / Código / Otro |
| **Origen** | Generado por IA (qué modelo) / Comprado (dónde) / Hecho a mano / Dominio público |
| **Licencia** | Texto completo o enlace a licencia (CC0, MIT, Royalty-free, Propietaria, etc.) |
| **Costo real** | USD / créditos / tiempo humano — verificado en factura/panel proveedor |
| **Versión/Fecha** | Versión del recurso y fecha de adquisición/creación |
| **Hash/Checksum** | SHA256 del archivo para verificación de integridad |
| **Ubicación en proyecto** | Ruta relativa en repo / asset bundle |
| **Trazabilidad** | Prompt usado (si IA), URL de descarga, factura, commit que lo introdujo |

## Cuándo se usa

- Al recibir/generar un asset nuevo (pipeline `produccion-assets.md`)
- Al integrar asset en motor (`pipeline-nivel.md`)
- Al hacer build final (checklist legal)
- Al publicar (compliance store)

## Estado

**PENDIENTE DE IMPLEMENTAR** — Se creará cuando el primer juego real necesite trazabilidad legal completa. Mientras tanto, se registra info mínima en `00-estado-produccion.md` del juego.

---

> **Nota:** Esta plantilla no existe aún en el pipeline. Las referencias en `herramientas-y-apis.md` marcan su necesidad futura.
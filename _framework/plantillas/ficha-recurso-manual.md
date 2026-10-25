# Plantilla: Ficha de Recurso Manual (traspaso agente → creador)

> **Cuándo se usa:** cada vez que una acción requiere una herramienta que el agente **no puede ejecutar** (UI manual, login, software de escritorio, interfaz web, compra). Es la unidad mínima del traspaso: un recurso = una ficha.
> **Regla madre (heredada del YouTube Creator Hub, §08.2):** el agente **no delega la tarea, entrega el paquete terminado para un clic**. Prohibido entregar instrucciones abstractas o listas de prompts sin clasificar. El creador ejecuta; el agente preparó todo lo ejecutable.
> **Origen:** `AGENTS.md` §Niveles de autonomía regla 7; protocolo general en `_framework/herramientas-y-apis.md`.

## Campos obligatorios

```markdown
## Ficha: <nombre corto del recurso>  (del handoff/feature <X>)

1. **Tipo de resultado:** <asset visual / modelo 3D / audio / captura de build /
   publicacion en plataforma / accion en editor / compra o pago>
2. **Herramienta y como abrirla:** <app o URL exacta; si es local, como llegar>
3. **Parametros listos:** <resolucion, formato, engine target, duracion, lo que
   la herramienta pida, ya rellenado — no "configuralo vos">
4. **Contenido listo para pegar:** <prompt completo / texto / valores, en bloque
   de codigo copiable, calibrado y sin edicion pendiente>
5. **Accion sugerida en la interfaz, paso a paso:** <"pega esto, clic en X,
   exportar como Y a la carpeta Z">
6. **Donde guardar el resultado:** <ruta exacta dentro del juego; nombre de
   archivo; con que lo verifica el agente al recibirlo>
7. **Costo conocido:** <creditos / precio / "gratis"> — si hay costo, este traspaso
   ya paso por la confirmacion obligatoria de AGENTS.md
8. **Registro posterior:** al recibir el resultado, el agente lo anota en el
   registro de recursos del juego (licencia, origen, version)
```

## Reglas de uso

- **Una ficha por recurso**, con nombre estable: el creador puede procesarlas en el orden que quiera y el agente rastrear cuál falta.
- **Sin relleno:** los campos 3 y 4 van **ya resueltos**. Si el agente no puede resolverlos, dice exactamente qué decisión del creador necesitan ("necesito que elijas entre pixel-art y vectorial antes de escribir el prompt").
- **Verificacion al recibir:** cuando el resultado vuelve, el agente lo revisa contra la ficha (formato, resolucion, ruta) y lo sube por la escalera de aceptacion; no asume que "llego algo" es "llego lo correcto".
- **Capa de decision, no de fontaneria:** se habla en terminos del recurso ("el sprite del dash, 8 frames, listo para importar"), no de la fontaneria interna de la herramienta salvo que el creador pregunte.
- **Las plataformas cambian:** nombres de botones y pestañas se describen como intencion ("el boton de exportar a GLB") mas que como verdad literal de la version actual.

## Ejemplo minimo

```markdown
## Ficha: sonido de dash (feature "dash feel")

1. Tipo: SFX
2. Herramienta: <generador de SFX que el juego declaro>, proyecto del juego
3. Parametros: WAV 48kHz mono, 0.4s, loop off
4. Pegar: `whoosh ascendente corto, energia alta, sin reverb larga, estilo arcade limpio`
5. Interfaz: pegar el prompt, generar 3 variantes, bajar las tres
6. Guardar en: mis-juegos/<juego>/assets/audio/sfx/dash_v1.wav (y _v2/_v3)
7. Costo: 3 generaciones del plan actual del creador
8. Registro: al recibir, anotar generator/version en el registro de recursos
```

# Plantilla · Estructura de carpetas

Crea las carpetas tal cual, pon [`CLAUDE.md`](CLAUDE.md) en la raíz y pégalo también como instrucciones de carpeta en la app de Claude.

```
mi-negocio/
├── CLAUDE.md            ← las reglas de la casa
├── 00-contexto/
│   ├── quien-soy.md
│   ├── precios.md
│   └── servicios.md
├── 01-clientes/
│   └── [cliente]/
│       ├── brief.md     ← una página: vendido, cotizado, pendiente
│       ├── cotizaciones/
│       └── entregas/
├── 02-plantillas/
│   ├── cotizacion.md
│   ├── propuesta.md
│   └── correo-seguimiento.md
├── 03-entradas/         ← lo que llega sin clasificar
├── _revisar/            ← lo dudoso · aquí nunca se borra
└── RESUMEN.md           ← qué hizo la última tarea

nombres:  AAAA-MM-DD-[cliente]-[tipo].[ext]
ejemplo:  2026-11-05-acme-cotizacion.pdf
```

En tu carpeta de negocio no hay nada oculto (ninguna carpeta que empiece con punto). Eso es de Claude Code.

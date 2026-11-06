# Claude, de 0 a 1000

Todo lo de la masterclass **«Claude para TODOs»** de John Olven, listo para copiar: la escalera completa, plantillas, skills, conectores MCP recomendados con el permiso de cada uno, y lo importante de Claude Code.

> Claude ya no es un chat. Es una escalera: el mismo cerebro, con más alcance en cada escalón.

| Escalón | Qué es | Dónde vive | Guía |
|---|---|---|---|
| **0 · Chat** | Le pegas texto, te devuelve texto. Tú eres las manos. | Claude | [Pedir bien](guias/0-pedir-bien.md) |
| **100 · Proyecto** | Instrucciones y archivos que lee en cada conversación. | Claude → Proyectos | [El Proyecto](guias/1-proyecto.md) |
| **300 · Carpeta** | Una carpeta de tu computadora con estructura y un `CLAUDE.md`. Claude tiene manos. | Claude para escritorio | [La carpeta](guias/2-carpeta-y-claude-md.md) |
| **500 · Conectores** | Tu correo, calendario y hoja, por MCP, con permisos leídos. | Claude → Conectores | [Conectores MCP](guias/3-conectores-mcp.md) |
| **700 · Agente** | Disparador, reglas, herramientas, freno y bitácora. Trabaja cuando tú no. | Tareas programadas | [Agentes](guias/4-agentes.md) |
| **1000 · Claude Code** | Construye software. Las mismas piezas, en un proyecto con su `.claude/`. | Terminal o app de escritorio | [Claude Code](guias/6-claude-code.md) |

Y transversal a todos: [Skills](guias/5-skills.md) · [Seguridad: permisos, no promesas](guias/7-seguridad.md).

## Qué hay aquí

```
guias/        una guía por escalón, en el orden de la masterclass
plantillas/   para copiar tal cual: petición, Proyecto, CLAUDE.md, estructura de carpetas, agente
ejemplos/     mi-negocio/ (la carpeta con su CLAUDE.md) y mi-proyecto/ (un proyecto de Claude Code con su .claude/)
plugins/      un plugin de Claude Code con 4 skills de ejemplo (cotizar, clasificar, resumen semanal, revisar permisos)
```

## Las tres reglas de la noche

1. **Pide con 4 partes:** objetivo, contexto, criterio de listo y límites. Y la línea que más vale: *«si te falta un dato, pregúntamelo antes de suponer»*.
2. **Permisos, no promesas:** lee la pantalla de permisos antes de aceptar, da el mínimo y sabe dónde se quita. Leer → escribir → enviar: lo último lo firmas tú.
3. **Los tres nunca de la primera semana:** borrar, pagar y hablar con terceros en tu nombre. El agente propone, el humano firma.

## Instalar las skills en Claude Code

```
/plugin marketplace add hiveflowai/claude-de-0-a-1000
/plugin install de-0-a-1000@claude-de-0-a-1000
```

En la app de Claude (sin terminal): descarga la carpeta de una skill (`plugins/de-0-a-1000/skills/<skill>/`), comprímela en .zip y súbela en **Personalizar → Skills**.

> Un plugin puede ejecutar código en tu máquina. Instala solo de fuentes que confíes y lee lo que trae antes. Estas skills son solo texto (Markdown): no ejecutan nada.

## ¿Y cuando el agente tiene que correr solo, con tu equipo?

Todo lo de aquí vive en tu computadora. Cuando un agente debe correr solo (en WhatsApp, a una hora, cuando llega un correo), con aprobación humana, bitácora y permisos por herramienta para todo un equipo, eso es [Hiveflow](https://hiveflow.ai). Su MCP se conecta igual que cualquier otro: `https://mcp.hiveflow.ai`.

---

Hecho por [John Olven](https://www.treebu.ai/johnolven) · [Hiveflow](https://hiveflow.ai) · Licencia MIT. Verifica los nombres de menús en tu versión de Claude: la app cambia seguido.

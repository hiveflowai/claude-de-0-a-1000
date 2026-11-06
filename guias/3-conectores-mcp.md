# Escalón 500 · Conectores por MCP

## Qué es MCP

**MCP (Model Context Protocol)** es el estándar abierto que Anthropic publicó a finales de 2024 para conectar IA con herramientas. Es el USB-C de la IA: una herramienta que «habla MCP» la puede usar Claude, Claude Code o un agente de otra plataforma con **la misma conexión**.

Un servidor MCP ofrece:

- **Herramientas:** acciones (buscar correos, crear un evento, leer una hoja).
- **Recursos:** datos para leer.
- **Prompts:** plantillas.

Por dentro es JSON-RPC: Claude pregunta `tools/list`, lee la descripción de cada herramienta (con eso decide cuándo usarla) y llama `tools/call`.

## Cómo se conecta

- **En Claude:** Personalizar / Configuración → **Conectores** → elige uno del directorio o agrega uno personalizado con su URL.
- **En Claude Code:**

```bash
claude mcp add --transport http hiveflow https://mcp.hiveflow.ai   # un MCP remoto
claude mcp add clima -- node ./server.js                             # uno local, por stdio
claude mcp list                                                      # los que tienes
```

Dentro de la sesión, `/mcp` muestra cuáles están conectados y autentica los que lo piden. Con `--scope project` se guarda en `.mcp.json` del repo para todo el equipo. **Las llaves van en variables de entorno, nunca en el código.**

## La regla: leer la pantalla de permisos

Antes de aceptar, lee qué pide. Si dice «ver, editar y eliminar» y la tarea solo necesita leer, busca la opción de solo lectura o no conectes. Se quita desde tu cuenta de Google (Seguridad → apps de terceros con acceso) y desde los conectores de Claude.

## 10 conectores recomendados, con el permiso de la primera semana

Sube un escalón de permiso cuando lleve dos semanas sin fallar, y solo si la tarea lo necesita. Comprueba que existan en tu directorio de conectores: cambian seguido.

| # | Conector | Permiso semana 1 | Para qué | Nunca la primera semana |
|---|---|---|---|---|
| 1 | **Gmail** | leer | bandeja sin responder, resumen del día, clasificar | enviar (los borradores los mandas tú) |
| 2 | **Google Calendar** | leer y crear eventos | huecos, agendar con tu ok | eliminar |
| 3 | **Google Sheets / Drive** | leer | números con su celda de origen, resúmenes | escribir (después: solo en una pestaña `_claude`) |
| 4 | **Google Drive** | leer una carpeta concreta | encontrar y resumir documentos | todo el Drive |
| 5 | **Notion** | leer | procesos, clientes, tareas | escribir fuera de una página «Bandeja de Claude» |
| 6 | **Slack** (o el chat del equipo) | leer canales concretos | resumen del día, pendientes | publicar en nombre de nadie |
| 7 | **Firecrawl** (web → datos) | leer páginas públicas | precios de proveedores, directorios | iniciar sesión en sitios |
| 8 | **GitHub** | leer un repositorio | para quien construye | escribir en la rama principal |
| 9 | **Stripe** (o tu pasarela) | reportes, solo lectura | ventas, cobros del mes | crear cobros, reembolsos o cambiar precios |
| 10 | **Hiveflow** (`mcp.hiveflow.ai`) | leer y crear borradores | CRM, tableros, conversaciones, agentes | aprobar o publicar: eso lo firma una persona |

## Pruebas que sirven

- Gmail: «Revisa mi correo de los últimos 7 días. ¿Qué mensajes de clientes siguen sin respuesta mía? Remitente, asunto, fecha y qué piden. No redactes todavía.»
- Calendar: «Propón tres huecos de 45 minutos la semana que viene, espera a que elija y solo entonces crea el evento, sin invitados.» (Tu primera acción con firma.)
- Sheets: «Total de [columna] por mes y filas con celdas vacías; para cada número, de qué celdas lo sacaste.» Debe decir «no se puede» en vez de estimar.

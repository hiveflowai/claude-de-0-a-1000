# Escalón 1000 · Claude Code

**Claude Code** es la otra app: la que construye software. Vive en la terminal (y en apps de escritorio e IDE), lee un proyecto completo, cambia archivos, corre pruebas y te enseña lo que hizo para que apruebes.

- **Es** un agente con las manos dentro de un proyecto de código.
- **No es** para negocios sin software propio: si tu negocio corre en Sheets, WhatsApp y una tienda hecha por alguien más, lo tuyo es la carpeta (escalón 300). Si alguien te mantiene la web o la app, Claude Code le toca a esa persona, y ya sabes qué pedirle.

## La petición lleva el freno dentro

```
Objetivo: [qué cambia, desde el punto de vista del usuario].
Está listo cuando: [qué se ve, qué prueba pasa].
Límites: no toques [archivos], no instales nada nuevo, no cambies [lo que no se cambia].
Antes de editar, dime en tres líneas qué vas a hacer y espera mi ok.
```

## Las mismas piezas, con el mismo nombre

- **CLAUDE.md:** las reglas del proyecto. Lo lee solo al entrar. `/init` crea uno.
- **Skills:** `.claude/skills/<nombre>/SKILL.md`. Se cargan cuando la tarea lo pide.
- **Subagentes:** `.claude/agents/<nombre>.md`. Uno investiga, otro revisa; el principal ve el resumen.
- **Plugins:** skills, agentes, hooks y servidores MCP empaquetados. Tu equipo los instala con `/plugin`.
- **MCP:** `claude mcp add …` (ver [conectores](3-conectores-mcp.md)).
- **Hooks:** comandos que corren en momentos fijos (antes de usar una herramienta, al terminar). Sirven de freno de verdad.

## La carpeta de un proyecto

```
mi-proyecto/
├── CLAUDE.md            ← reglas del proyecto · se lee al entrar
├── CLAUDE.local.md      ← tus notas · no se comparte
├── .mcp.json            ← los MCP del equipo (con --scope project)
├── .claude/             ← OCULTA: empieza con punto (⌘ ⇧ . en el Finder)
│   ├── settings.json    ← permisos y hooks
│   ├── skills/cotizar/SKILL.md
│   └── agents/revisor.md
└── src/ …

~/.claude/               ← tu usuario: vale para todos tus proyectos
├── CLAUDE.md
└── skills/
```

## Tres alcances

| Dónde | Alcance | Quién lo comparte |
|---|---|---|
| `CLAUDE.md` del proyecto | este proyecto, toda sesión | el equipo, por git |
| `.claude/` del proyecto | skills, agentes, permisos de este proyecto | el equipo, por git |
| `~/.claude/` | todos tus proyectos | solo tú |

Si una regla de usuario contradice una del proyecto, Claude puede elegir cualquiera. No te contradigas.

## Permisos: lista de permitidos y prohibidos

`.claude/settings.json`:

```json
{
  "permissions": {
    "allow": ["Bash(npm test)", "Bash(git status)", "Bash(git diff:*)"],
    "deny": ["Bash(rm -rf:*)", "Bash(git push:*)", "Read(./.env)", "Read(./secrets/**)"]
  }
}
```

Lo que no está permitido, Claude Code lo pregunta antes de hacerlo. Lo prohibido no lo hace.

## Comandos que vale la pena saber

| Comando | Para qué |
|---|---|
| `claude` | abrir una sesión en la carpeta actual |
| `/init` | crear el CLAUDE.md leyendo el proyecto |
| `/mcp` | ver y autenticar los MCP |
| `/plugin` | instalar plugins y marketplaces |
| `/agents` | crear y ver subagentes |
| `/permissions` | revisar qué puede hacer sin preguntar |
| `claude -p "…"` | modo sin interfaz: para scripts y tareas programadas |

## Claude y Claude Code, lado a lado

| | Claude (0 → 700) | Claude Code (1000) |
|---|---|---|
| Reglas | instrucciones de carpeta (pegas tu CLAUDE.md) | CLAUDE.md en la raíz |
| Skills | Personalizar → Skills | `.claude/skills/` |
| Carpeta oculta | ninguna | `.claude/` |
| Quién lo comparte | tú | tu equipo, por git |
| **Lo que no cambia** | el .md: mismo formato, mismas reglas | ← lo de hoy lo pegas mañana en un proyecto |

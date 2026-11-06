# Skills

Una **skill** es una carpeta con un archivo `SKILL.md` (y, si hace falta, plantillas o scripts) que le enseña a Claude **un procedimiento**: cómo cotizamos, cómo revisamos una entrega. Convierte al generalista en un especialista de tu flujo.

## Cómo funciona

1. Claude ve solo el **nombre y la descripción** de cada skill instalada (barato en contexto).
2. Cuando tu petición coincide con la descripción, **carga el SKILL.md completo** y lo sigue.
3. Si la skill trae archivos extra (una plantilla, un script), los abre solo cuando los necesita.

Por eso **la descripción es lo más importante**: escribe ahí las palabras que usaría tu usuario («cotización», «presupuesto», «cuánto cuesta»).

## Anatomía

```markdown
---
name: cotizar
description: Arma cotizaciones con la lista de precios vigente. Úsala cuando pidan una cotización,
  un presupuesto o «cuánto cuesta» un servicio para un cliente.
---
# Cotizar
1. Pide lo que falte: cliente, servicio, cantidad.
2. Toma precios SOLO de 00-contexto/precios.md (el de fecha más reciente).
3. Llena 02-plantillas/cotizacion.md.
## Reglas
- No inventes precios ni descuentos.
## Formato de salida
Una página: alcance, precio con IVA, vigencia, forma de pago.
```

## Una buena skill

- **description** con las palabras del usuario y cuándo usarla.
- **Pasos** numerados y verificables.
- **Reglas** de lo que no debe hacer.
- **Formato** exacto de la respuesta.
- Corta: lo largo, en archivos aparte que la skill menciona.

## Dónde se instalan

- **Claude (app):** Personalizar → Skills → sube la carpeta en .zip, o pídele a Claude que la cree contigo.
- **Claude Code:** `.claude/skills/<nombre>/SKILL.md` en el proyecto (todo el equipo, por git) o `~/.claude/skills/` (solo tú, en todos tus proyectos). O como plugin: ver el [README](../README.md).

## Las 4 de este repo

| Skill | Qué hace |
|---|---|
| [`cotizar`](../plugins/de-0-a-1000/skills/cotizar/SKILL.md) | Cotización de una página con tu lista de precios, sin inventar |
| [`clasificar-entradas`](../plugins/de-0-a-1000/skills/clasificar-entradas/SKILL.md) | Ordena y renombra `03-entradas` según tu CLAUDE.md |
| [`resumen-semanal`](../plugins/de-0-a-1000/skills/resumen-semanal/SKILL.md) | El `semana-fecha.md` de cada lunes: qué entró, qué falta, qué mirar primero |
| [`revisar-permisos`](../plugins/de-0-a-1000/skills/revisar-permisos/SKILL.md) | Antes de conectar algo o soltar un agente: revisa sus 5 piezas y sus permisos |

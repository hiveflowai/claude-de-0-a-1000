# Escalón 700 · Agentes

## Un agente son 5 piezas, ninguna es magia

1. **Disparador:** cuándo arranca. Cada lunes 8:00, o cuando llega un correo.
2. **Reglas:** el `CLAUDE.md` de tu carpeta y las instrucciones de la tarea.
3. **Herramientas:** la carpeta, Gmail en lectura, el calendario. Cada una con su permiso.
4. **Freno:** lo que nunca hace sin ti: enviar, borrar, pagar. Y dónde se pausa.
5. **Bitácora:** el `RESUMEN.md` o `semana-fecha.md` que te deja para revisar.

**Sin freno y sin bitácora no es un agente: es un riesgo.** Plantilla: [`plantillas/agente.md`](../plantillas/agente.md).

## Cómo trabaja

Un chat da una vuelta. Un agente da las que necesite: objetivo → piensa → usa una herramienta → observa → ¿terminé? Si no, otra vuelta; si sí, entrega.

**Subagentes:** cuando el trabajo es grande, el agente principal lanza otros en paralelo, cada uno con su contexto y sus permisos (uno investiga, otro redacta, otro revisa) y solo ve el resumen de cada uno.

## Tu primer agente: una tarea programada

```
Cada lunes a las 8:00: revisa qué archivos nuevos entraron a 03-entradas la semana pasada,
clasifícalos según CLAUDE.md (renombra sin borrar) y escribe «semana-[fecha].md» con: qué entró,
qué quedó en _revisar, qué debería mirar yo primero. No envíes nada a nadie.
No toques nada fuera de esta carpeta.
```

- En Claude: describe la tarea y la frecuencia; Claude propone nombre, horario e instrucciones; revisa y programa. Se pausan y se borran en la sección de tareas programadas: búscala hoy, no el día que haga algo raro.
- Si la tarea toca tu carpeta local, **la app de escritorio tiene que estar abierta a esa hora**.
- En Claude Code: `/schedule` o, hecho en casa, `claude -p "…" --allowedTools … --output-format json` en un cron.

Con Gmail en lectura del escalón 500, esa tarea **ya es un agente**.

---
name: revisar-permisos
description: Revisa un agente, una tarea programada, un conector MCP o un plugin antes de soltarlo, con las 5 piezas del agente y la regla de permisos mínimos. Úsala cuando vayan a conectar una herramienta, instalar un plugin, programar una tarea o pregunten si algo es seguro o qué permisos dar.
---

# Revisar permisos

## Pasos
1. Pregunta qué se va a soltar: agente o tarea programada, conector MCP, o plugin.
2. Para un **agente o tarea**, revisa las 5 piezas y marca la que falte:
   - Disparador: ¿cuándo arranca exactamente?
   - Reglas: ¿hay CLAUDE.md o instrucciones claras?
   - Herramientas: ¿cada una con el permiso mínimo (leer antes que escribir, escribir antes que enviar)?
   - Freno: ¿qué nunca hace sin una persona? ¿dónde se pausa?
   - Bitácora: ¿qué archivo deja y quién lo revisa, cuándo?
3. Para un **conector**, pide que te lean (o peguen) la pantalla de permisos y compara con lo que la tarea necesita. Recomienda el mínimo y dónde se quita.
4. Para un **plugin**, revisa quién lo publica, qué trae (skills, MCP, hooks) y si ejecuta código en la máquina.

## Reglas
- Los tres nunca de la primera semana: borrar, pagar y hablar con terceros en nombre del usuario. Si la tarea los necesita, debe pasar por una persona.
- Nunca pidas ni muestres contraseñas, llaves de API o tokens.
- Si algo no se puede verificar, dilo; no lo des por seguro.

## Formato de salida
- Semáforo: 🟢 listo · 🟡 listo con cambios · 🔴 no lo sueltes.
- Tabla de las 5 piezas (o de los permisos) con «tiene / falta / cambiar a».
- Los cambios concretos, en orden.

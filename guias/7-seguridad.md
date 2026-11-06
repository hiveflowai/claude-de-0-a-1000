# Seguridad · Permisos, no promesas

Con una carpeta o un conector, Claude puede hacer lo que tú puedes hacer. **El freno son los permisos, no la confianza.**

## Leer → escribir → enviar

Que lea y escriba en tu carpeta, sí. Que envíe a terceros, no: eso lo firmas tú.

## Lo que no le das

- **Una carpeta, no el disco.** Nunca la raíz, el escritorio ni Documentos entero.
- **Nada con claves.** Ninguna carpeta con contraseñas, accesos bancarios, llaves de API o tarjetas. Si una tarea necesita eso, está mal diseñada.
- **Navegador:** la primera semana, solo lo público y de lectura. Nada de iniciar sesión, comprar, pagar ni publicar.
- **Conectores:** el permiso mínimo, leído en pantalla. Sabes dónde se quita.

## Los tres nunca de la primera semana

1. **Borrar.**
2. **Pagar.**
3. **Hablar con terceros en tu nombre.**

Si una tarea los necesita, pasa por una persona. Se sube un escalón de permiso cuando lleve dos semanas sin fallar, y solo si la tarea lo necesita.

## Antes de instalar un plugin o un MCP de terceros

- ¿Quién lo publica? ¿Tiene repositorio y lo puedes leer?
- ¿Qué permisos pide y qué herramientas expone?
- ¿Ejecuta código en tu máquina? (Un plugin con MCP local, sí.)
- ¿Dónde se desinstala?

La skill [`revisar-permisos`](../plugins/de-0-a-1000/skills/revisar-permisos/SKILL.md) hace esta revisión contigo.

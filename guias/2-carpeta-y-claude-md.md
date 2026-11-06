# Escalón 300 · La carpeta y su CLAUDE.md

En la app de **escritorio** le das a Claude una carpeta de tu computadora y trabaja en ella: lee, ordena, renombra, escribe, y lo hace cada semana si se lo pides. La parte que nadie enseña: **la carpeta tiene estructura y un archivo de reglas.**

## 1 · Dale una carpeta, solo una

- Una carpeta con **copias** (nunca los originales irremplazables).
- Nunca Documentos entero, el escritorio ni la raíz del disco.
- Primera petición: «Dime qué hay en esta carpeta y qué tipo de archivos son». Debe listar sin tocar nada.

## 2 · La estructura

Ver [`plantillas/estructura-carpetas.md`](../plantillas/estructura-carpetas.md). Cuatro ideas:

1. **Un .md en la raíz:** `CLAUDE.md` con las reglas de la casa.
2. **Números para el orden:** 00, 01, 02, 03.
3. **Una entrada y un `_revisar`:** todo lo nuevo cae en `03-entradas`; lo dudoso va a `_revisar`. Nada se borra.
4. **Nombres con fecha:** `AAAA-MM-DD-cliente-tipo.ext`.

## 3 · El CLAUDE.md

No dice qué tarea hacer: dice **cómo se trabaja aquí**. La tarea cambia cada día; las reglas, no. Plantilla: [`plantillas/CLAUDE.md`](../plantillas/CLAUDE.md).

Cómo se escribe para que lo siga:

- **Menos de 200 líneas.** Se carga siempre y gasta contexto. Lo largo va a una skill.
- **Encabezados y viñetas.** Claude recorre la estructura igual que un lector.
- **Concreto y verificable.** «Nombra AAAA-MM-DD-cliente-tipo», no «ordena bien».
- **La prueba de cada línea:** ¿si la quito, se equivoca? Si no, fuera.
- **Agrega una regla** cuando comete el mismo error dos veces.
- **Sin contradicciones.** Si dos reglas chocan, puede elegir cualquiera.

> **Regla, procedimiento o freno.** Reglas → `CLAUDE.md`. Procedimiento de varios pasos → una skill (`SKILL.md`). Lo que debe pasar siempre, sin excepción → no es una regla: es un permiso que no das. Claude trata el .md como contexto, no como candado.

## 4 · Una tarea de verdad

```
Clasifica lo que hay en 03-entradas dentro de la estructura de esta carpeta, siguiendo CLAUDE.md.
Renombra cada archivo con la regla de nombres (fecha, cliente, tipo), leyendo el contenido cuando
el nombre no lo diga. Lo de cada cliente va a 01-clientes/[cliente]/. No borres nada; lo que no
sepas clasificar va a _revisar. Al terminar, RESUMEN.md con la tabla «nombre anterior → nombre nuevo».
```

Revisa el `RESUMEN.md`. Si algo salió mal, **corrige el CLAUDE.md, no la tarea**.

## Qué lee

PDF, DOCX, TXT, MD, CSV, JSON, HTML, XLSX e imágenes (PNG, JPEG, GIF, WebP). No lee bien un PDF escaneado sin capa de texto ni una foto borrosa.

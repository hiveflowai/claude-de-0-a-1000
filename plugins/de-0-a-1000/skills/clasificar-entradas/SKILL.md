---
name: clasificar-entradas
description: Ordena y renombra los archivos nuevos de la carpeta de entradas según las reglas del CLAUDE.md, sin borrar nada, y deja un RESUMEN.md. Úsala cuando pidan clasificar, ordenar, acomodar o renombrar archivos, o limpiar la carpeta de entradas.
---

# Clasificar entradas

## Pasos
1. Lee el `CLAUDE.md` de la carpeta: estructura, regla de nombres y lo que no se toca. Si no hay CLAUDE.md, pregunta antes de mover algo.
2. Lista lo que hay en la carpeta de entradas (por ejemplo `03-entradas/`). Si son más de 10 archivos, resume el plan y espera un ok.
3. Para cada archivo, lee el contenido (no solo el nombre) para sacar fecha, cliente y tipo.
4. Renombra con la regla del CLAUDE.md (por defecto `AAAA-MM-DD-[cliente]-[tipo].[ext]`) y muévelo a su lugar (`01-clientes/[cliente]/…`).
5. Lo que no sepas clasificar con seguridad va a `_revisar/`, con una línea de por qué.

## Reglas
- Nunca borres. Nunca sobrescribas: si el nombre existe, agrega «-v2».
- No abras archivos con «claves», «passwords» o «accesos» en el nombre: avisa.
- No toques nada fuera de la carpeta.

## Formato de salida
`RESUMEN.md` con:
- Una tabla «nombre anterior → nombre nuevo → carpeta».
- Lo que quedó en `_revisar/` y por qué.
- Lo que no pudiste leer (PDF escaneado, imagen borrosa).

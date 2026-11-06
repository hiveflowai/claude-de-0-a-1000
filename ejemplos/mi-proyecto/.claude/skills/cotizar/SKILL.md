---
name: cotizar
description: Arma una cotización de una página con la lista de precios vigente del negocio, sin inventar precios ni condiciones. Úsala cuando pidan una cotización, un presupuesto, una propuesta de precio o «cuánto cuesta» un servicio o producto para un cliente.
---

# Cotizar

## Pasos
1. Confirma lo que falte antes de empezar: cliente, servicio o producto, cantidad y para cuándo. Si falta algo, pregúntalo; no lo supongas.
2. Toma los precios SOLO del archivo de precios del negocio (por ejemplo `00-contexto/precios.md`; si hay varios, el de fecha más reciente). Di de qué archivo salió cada precio.
3. Si existe `02-plantillas/cotizacion.md`, úsala. Si no, usa el formato de abajo.
4. Calcula subtotal, IVA y total. Muestra la operación.
5. Si hay carpeta del cliente (`01-clientes/[cliente]/cotizaciones/`), guarda ahí la cotización con el nombre `AAAA-MM-DD-[cliente]-cotizacion.md`. Nunca sobrescribas una anterior.

## Reglas
- Si un concepto no está en la lista de precios, dilo y deja el renglón «por confirmar». No inventes precios.
- No ofrezcas descuentos, fechas de entrega ni condiciones que no estén escritas.
- Es un BORRADOR: no la envíes a nadie.

## Formato de salida
- Encabezado: cliente, fecha, vigencia (la de la política del negocio o «30 días» marcado como por confirmar).
- Tabla: concepto · cantidad · precio unitario · importe.
- Subtotal, IVA, total.
- Alcance en 3 a 5 viñetas y forma de pago.
- Una línea al final: «Precios tomados de [archivo]».

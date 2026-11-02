# Backlog ágil – Historias de usuario

Formato: **Como** [usuario], **quiero** [funcionalidad], **para** [beneficio].
Tablero: GitHub Projects (Por Hacer → En Progreso → Listo). Cada historia es un *issue* y sus tareas son sub-issues.

> Nota: las historias se alinean con las metas M1–M6 (Entrega 2), el diccionario de datos (Entrega 3) y los Sprints 2, 3 y 4 del cronograma. Prioridad y plazos son supuestos de planeación a validar con Fadel S.A.

## HU-1 · Alerta automática de falla (Prioridad: Alta · Sprint 2)
**Como** técnico de mantenimiento, **quiero** recibir una alerta automática cuando un equipo crítico sale de su umbral, **para** intervenir antes de que se detenga la línea o se corte la cadena de frío.

Criterios de aceptación:
- Si `valor_medido` supera `umbral_maximo` (o baja de `umbral_minimo`), se crea una ALERTA con `nivel_criticidad`.
- La notificación llega al técnico en 30 s o menos (meta M1).
- Si el equipo es crítico (`es_critico`), se avisa también a la Jefatura de Mantenimiento.
- Se registran `fecha_hora_generacion` y `fecha_hora_notificacion`.

Vinculación: BPMN (S2, S4, S5, G1, G2) · Gantt 3.2 · Entidades EQUIPO, LECTURA, ALERTA, USUARIO.

## HU-2 · Orden de mantenimiento correctivo (Prioridad: Alta · Sprint 3)
**Como** jefe de mantenimiento, **quiero** que cada alerta atendida genere una orden con su fecha de apertura y de cierre, **para** medir y reducir el tiempo medio de reparación (MTTR).

Criterios de aceptación:
- El técnico confirma la alerta y se abre una ORDEN con `fecha_hora_apertura`.
- Al cerrar la orden se registran la descripción de la falla y `fecha_hora_cierre`.
- El sistema calcula el MTTR y lo muestra en un tablero (meta M6: −20 %).
- Los estados siguen la secuencia Abierta → En curso → Cerrada.

Vinculación: BPMN (T1, T2, T4, T5, S7) · Gantt 3.3 · Entidades ALERTA, ORDEN_MANTENIMIENTO.

## HU-3 · Control de repuestos y reposición (Prioridad: Media · Sprint 4)
**Como** responsable del pañol, **quiero** que el sistema descuente el repuesto usado al cerrar una orden y genere una solicitud de compra interna cuando el stock baje del mínimo, **para** evitar faltantes y errores de inventario.

Criterios de aceptación:
- El 100 % de las órdenes cerradas con repuesto descuenta `cantidad_repuesto` de `stock_actual`.
- Si `stock_actual` < `stock_minimo`, se genera la solicitud de compra interna.
- Si no hay stock al diagnosticar, se inicia el pedido al proveedor y se avisa a la Jefatura si pasan 48 h sin entrega.

Vinculación: BPMN (S6, G4, C1–C4, G5) · Gantt 3.5 · Entidad REPUESTO.

## Tarjetas sugeridas para el tablero (evidencian los tres estados)

| Tarjeta | Historia | Estado |
|---|---|---|
| Definir criterios de aceptación de HU-1/2/3 | HU-1,2,3 | Listo |
| Modelar el flujo de alerta y orden en BPMN | HU-1, HU-2 | Listo |
| Diseñar reglas de alerta y de stock (Gantt 2.3) | HU-1, HU-3 | En Progreso |
| Implementar motor de alertas (Sprint 2) | HU-1 | Por Hacer |
| Implementar órdenes de mantenimiento (Sprint 3) | HU-2 | Por Hacer |
| Implementar descuento de stock y compras (Sprint 4) | HU-3 | Por Hacer |

*(Actualizar los estados según el tablero real el día de la entrega.)*

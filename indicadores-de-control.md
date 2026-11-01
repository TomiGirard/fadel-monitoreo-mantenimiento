# Indicadores de control y estándares de desempeño

Se aplica el ciclo de control de la Unidad 4:**establecer estándares → medir → comparar → corregir y retroalimentar**.
Los estándares provienen de las metas M1–M6 (Entrega 2); KI-8 y KI-9 son estándares internos del equipo.

| ID | Indicador y fórmula | Estándar | Medición (fuente · frecuencia · responsable) | Acción correctiva |
|---|---|---|---|---|
| KI-1 | Tiempo de notificación = `fecha_hora_notificacion` − `fecha_hora_generacion` (ALERTA) | ≤ 30 s (M1) | Pruebas de rendimiento y registros · cada sprint desde el 2 · QA | Optimizar cola de eventos y canal de envío; reabrir la historia HU-1 |
| KI-2 | Tiempo de respuesta de interfaz = % de consultas ≤ 2 s con 50 usuarios concurrentes | ≥ 95 % (M2) | Pruebas de carga (tarea 4.2) · semana 18 · QA/BE | Índices, paginación, caché; repetir la prueba |
| KI-3 | Escalabilidad = degradación de tiempos con 100 equipos y 10.000.000 de LECTURA | ≤ 10 % (M3) | Prueba con datos sintéticos · semana 18 · BE | Particionar tablas, archivar históricos |
| KI-4 | Calidad = defectos críticos abiertos y % de casos de prueba aprobados | 0 críticos y ≥ 90 % (M4) | Gestor de pruebas e issues · antes del go-live · QA | Posponer el go-live y asignar corrección (tarea 4.3) |
| KI-5 | Avance = historias de prioridad alta en *Listo* ÷ historias de prioridad alta | 100 % en semana 21 (M5) | Tablero ágil · fin de cada sprint · LP | Reordenar backlog, recortar alcance no crítico |
| KI-6 | MTTR = Σ(`fecha_hora_cierre` − `fecha_hora_apertura`) ÷ n.º de órdenes cerradas | −20 % vs. línea base, 3 meses (M6) | ORDEN_MANTENIMIENTO · mensual post go-live · LP/Mantenimiento | Revisar causas de demora (repuestos, diagnóstico) y reentrenar |
| KI-7 | Descuento automático = órdenes con repuesto que descontaron stock ÷ órdenes con repuesto | 100 % (M6) | REPUESTO y ORDEN · semanal · BE | Corregir regla de cierre; conciliar stock manualmente |
| KI-8 | Integración controlada = cambios a `main` mediante PR con ≥ 1 revisión ÷ cambios a `main` | 100 % | Historial de GitHub · cada sprint · LP | Activar protección de rama; revisar el incidente en la retrospectiva |
| KI-9 | Commits descriptivos = commits con formato `tipo(ámbito): descripción` ÷ total | ≥ 90 % | `git log` · cada sprint · LP | Recordar la convención; reescribir mensajes pendientes antes del merge |

## Auditoría técnica por sprint (lista de control)
1. ¿Se midieron los indicadores aplicables y se compararon con el estándar?
2. ¿Hay desvíos? ¿Se abrió un issue con responsable y fecha?
3. ¿Los cambios llegaron a `main` por PR revisado?
4. ¿El tablero refleja el estado real de cada historia?
5. ¿Se actualizó la documentación (README, BPMN, diccionario de datos)?

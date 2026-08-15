---
name: rastreador-proyectos
description: "Construye un sistema de rastreo de proyectos con hitos, asignaciones de tareas y seguimiento de progreso para mantener proyectos en cronograma."
allowed-tools: Read Write Glob
metadata:
  author: Imperio Digital
  version: "1.0"
---

# Rastreador de Proyectos

## Cuándo Usar Este Skill

Usa este skill cuando necesites:
- Rastrear múltiples proyectos simultáneamente
- Definir hitos y fechas de entrega
- Asignar tareas al equipo
- Identificar cuellos de botella

---

## Principio Fundamental

UN PROYECTO SIN SEGUIMIENTO ES SOLO ESPERANZA Y SUERTE — UN PROYECTO CON SEGUIMIENTO ES PREDICTIBLE.

---

## Estructura de Proyecto

### Plantilla de Proyecto

```
## Proyecto: [Nombre]

**Propósito:** [Por qué existe este proyecto]
**Propietario:** [Persona responsable]
**Fecha de inicio:** [Fecha]
**Fecha de vencimiento:** [Fecha]
**Estado:** [En progreso/Completado/En riesgo]
**Presupuesto:** $[X]

### Hitos

| Hito | Descripción | Fecha | Estado |
|------|-----------|-------|--------|
| [Hito] | [Descripción] | [Fecha] | [Completado/En progreso/En riesgo] |

### Tareas

| Tarea | Asignado | Plazo | Estado | Bloqueador |
|------|----------|-------|--------|-----------|
| [Tarea] | [Persona] | [Fecha] | [Completado/En progreso/En riesgo] | [Sí/No] |
```

---

## Fase 2: Seguimiento Regular

Crea ritmo de revisión.

### Cadencia de Seguimiento

- Semanal: Revisión de avance de tareas
- Mensual: Revisión de hitos y presupuesto
- Según sea necesario: Gestión de bloqueadores

---

## Anti-Patrones

- **Demasiadas tareas sin prioridad** — confusión sobre qué importa
- **Sin propietario claro** — responsabilidad compartida es sin responsabilidad
- **Fechas poco realistas** — constantemente en riesgo
- **Sin comunicación de bloqueadores** — problemas no identificados hasta muy tarde

---

## Recuperación

- **Proyecto constantemente en riesgo:** Revisa fechas, descope si es necesario
- **Tareas no se completaban:** Reduce tamaño de tarea, asigna personas más fuertes
- **Equipo no actualiza estado:** Hazlo obligatorio en reunión semanal

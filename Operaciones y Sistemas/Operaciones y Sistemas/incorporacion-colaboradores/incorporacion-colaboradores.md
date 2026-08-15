---
name: incorporacion-colaboradores
description: "Crea un proceso de onboarding estandarizado para nuevos colaboradores que los lleva de cero a productivos operando cuentas de clientes, con hitos por días, accesos, capacitación y criterios de evaluación."
allowed-tools: Read Write Glob
metadata:
  author: Imperio Digital
  version: "1.0"
---

# Incorporación de Colaboradores

## Cuándo Usar Este Skill

Usa este skill cuando necesites:
- Incorporar a un nuevo miembro del equipo que operará procesos o cuentas de clientes
- Estandarizar cómo se entrena a la gente para que no dependa de quién los recibe
- Reducir el tiempo de "cero a productivo" de semanas a días
- Definir qué debe saber y poder hacer alguien antes de tocar la cuenta de un cliente real

**NO** uses este skill para onboarding de proveedores (usa otro skill), ni para delegar una tarea puntual a alguien que ya está dentro (usa `marco-delegacion`). Este es específicamente para integrar a una persona nueva al equipo.

---

## Principio Fundamental

UN COLABORADOR SIN ONBOARDING ESTRUCTURADO TARDA EL TRIPLE EN SER PRODUCTIVO Y COMETE EL TRIPLE DE ERRORES EN CUENTAS DE CLIENTE. EL ONBOARDING NO ES UN FAVOR — ES CONTROL DE CALIDAD Y PROTECCIÓN DE LA RELACIÓN CON EL CLIENTE.

---

## Fase 1: Definir el Rol y el "Listo para Operar"

Antes del día 1, define a qué se incorpora la persona.

### Ficha del Rol

- **Puesto y a quién reporta:** [Rol] → [Responsable directo]
- **Cuentas/clientes que tocará:** [Cuáles, y en qué orden de entrada]
- **Procesos que debe dominar:** [Lista de SOPs aplicables]
- **Herramientas que usará:** [CRM, Notion, Meta Ads, reportería, etc.]
- **Definición de "Listo para Operar":** [Qué debe poder hacer SOLO antes de quedar a cargo]

**PUNTO DE CONTROL: Confirma la ficha del rol y la definición de "Listo para Operar" antes de seguir.**

---

## Fase 2: Plan de Onboarding por Hitos

Estructura la incorporación en bloques de tiempo con resultados claros, no por "ir viendo".

### Día 1 — Contexto y Accesos
- [ ] Bienvenida: qué hace la empresa, modelo de negocio, quiénes son los clientes
- [ ] Entrega de accesos (correo, CRM, Notion, herramientas, carpetas)
- [ ] Lectura de la base de conocimiento y SOPs clave
- [ ] Presentación al equipo y a su responsable directo

### Días 2-5 — Capacitación en Procesos
- [ ] Recorrido de cada SOP que usará, con el responsable
- [ ] Observación: ve cómo alguien con experiencia ejecuta el proceso real
- [ ] Primeras tareas en ambiente controlado (sin impacto directo al cliente)
- [ ] Checklist de calidad explicado (qué significa "bien hecho" aquí)

### Semana 2 — Ejecución Supervisada
- [ ] Ejecuta procesos reales con revisión previa antes de enviar al cliente
- [ ] Shadowing inverso: el responsable observa y corrige
- [ ] Acceso gradual a más cuentas según desempeño

### Semana 3-4 — Autonomía Progresiva
- [ ] Opera cuentas con revisión solo por muestreo
- [ ] Maneja su primer caso de escalada con apoyo
- [ ] Evaluación de "Listo para Operar"

**PUNTO DE CONTROL: Presenta el plan por hitos para revisión antes de arrancar el día 1.**

---

## Fase 3: Plantilla de Seguimiento del Onboarding

Documenta el avance de cada persona para que el proceso sea medible y repetible.

```
## Onboarding: [Nombre del Colaborador]

**Rol:** [Puesto]    **Responsable:** [Quién lo entrena]
**Fecha inicio:** [Fecha]    **Fecha objetivo "Listo para Operar":** [Fecha]
**Cuentas asignadas:** [Lista]

### Estado por Hito
- [ ] Día 1 — Contexto y accesos
- [ ] Días 2-5 — Capacitación en procesos
- [ ] Semana 2 — Ejecución supervisada
- [ ] Semana 3-4 — Autonomía progresiva

### Evaluación "Listo para Operar"
| Competencia | ¿La domina solo? | Notas |
|-------------|------------------|-------|
| [SOP / herramienta / proceso] | Sí/No | [Observación] |

### Decisión final
- [ ] Aprobado para operar de forma autónoma
- [ ] Requiere extensión de onboarding: [razón y plan]
```

---

## Fase 4: Cierre y Mejora Continua

- A los 30 días: checkin con el colaborador — ¿qué le faltó del onboarding?
- Usa esa retroalimentación para mejorar el siguiente onboarding
- Cada vez que un colaborador nuevo tropieza con lo mismo, agrégalo al onboarding o a la base de conocimiento

---

## Anti-Patrones

- **"Aprende sobre la marcha" en cuenta real** — los errores los paga el cliente
- **Onboarding que depende de quién recibe** — sin checklist, cada quien entrena distinto
- **Dar todos los accesos y cuentas el día 1** — autonomía sin base = caos
- **No definir "Listo para Operar"** — sin criterio, nunca sabes si está listo o solo "lleva tiempo"
- **No documentar el avance** — no puedes mejorar lo que no mides

---

## Recuperación

- **El colaborador no avanza al ritmo esperado:** Revisa si el cuello es capacitación, herramientas o claridad del rol; ajusta el plan, no la fecha a ciegas
- **Comete errores en cuenta real:** Regresa a ejecución supervisada en ese proceso; refuerza el checklist de calidad
- **El responsable no tiene tiempo de entrenar:** Apóyate en SOPs y base de conocimiento; el onboarding no debe vivir solo en la cabeza de una persona
- **Rota gente y se pierde el conocimiento:** Asegura que todo lo aprendido quede en SOPs y base de conocimiento, no en la persona

---
name: automatizacion-reportes
description: "Automatiza la generación y distribución de reportes para ahorrar tiempo y asegurar reportes consistentes y a tiempo."
allowed-tools: Read Write Glob
metadata:
  author: Imperio Digital
  version: "1.0"
---

# Automatización de Reportes

## Cuándo Usar Este Skill

Usa este skill cuando necesites:
- Crear reportes regularmente (semanal, mensual, trimestral)
- Reunir datos de múltiples fuentes
- Distribuir reportes automáticamente
- Garantizar reportes consistentes

---

## Principio Fundamental

UN REPORTE MANUAL TOMA HORAS Y SALE TARDE. UN REPORTE AUTOMATIZADO TOMA MINUTOS Y SIEMPRE ESTÁ A TIEMPO.

---

## Fase 1: Definir Reportes

¿Qué reportes necesitas realmente?

### Matriz de Reportes

| Reporte | Audiencia | Frecuencia | Datos Necesarios | Acción Requerida |
|---------|----------|-----------|------------------|-----------------|
| [Reporte] | [Quién] | [Cuándo] | [Fuentes] | [Qué hacen con él] |

---

## Fase 2: Automatizar Recolección

Recopila datos automáticamente.

### Fuentes de Datos

- CRM, Analytics, Spreadsheets, Databases
- Herramientas: Zapier, Make, Integromat

---

## Fase 3: Automatizar Distribución

Envía reportes automáticamente.

### Plantilla de Flujo de Automatización de Reportes

```
**Trigger:** Cada lunes a las 9am
**Acción 1:** Extraer datos de [fuente]
**Acción 2:** Generar reporte en [herramienta]
**Acción 3:** Enviar email a [audiencia]
**Resultado:** Reporte llega automáticamente
```

---

## Anti-Patrones

- **Reporte demasiado largo** — nadie lo lee
- **Datos inconsistentes** — fuente de datos cambia
- **Sin contexto** — números sin interpretación
- **Demasiados reportes** — sobrecarga de datos

---

## Recuperación

- **Automatización falla a veces:** Agrega fallback manual, notificación de error
- **Datos inexactos:** Verifica fuente de datos, formula
- **Nadie actúa sobre reporte:** Tal vez el reporte no es necesario, o demasiado complejo

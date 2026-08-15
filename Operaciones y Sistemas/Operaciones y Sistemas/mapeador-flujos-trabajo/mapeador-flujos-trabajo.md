---
name: mapeador-flujos-trabajo
description: "Mapea visualmente workflows para entender cómo se mueve el trabajo a través de los sistemas, identificar cuellos de botella y mejorar procesos."
allowed-tools: Read Write Glob
metadata:
  author: Imperio Digital
  version: "1.0"
---

# Mapeador de Workflows

## Cuándo Usar Este Skill

Usa este skill cuando necesites:
- Visualizar cómo fluye el trabajo en tu negocio
- Identificar dónde se está atrapando el trabajo
- Mostrar al equipo cómo se conectan los procesos
- Comunicar mejoras de proceso

---

## Principio Fundamental

LOS FLUJOS DE TRABAJO NO SE ENTIENDEN HASTA QUE SE VISUALIZAN — UNA IMAGEN DE UN FLUJO VALE MÁS QUE 1000 PALABRAS DE DESCRIPCIÓN.

---

## Elementos del Mapeo de Flujos

### Símbolos Estándar

- **Rectángulo** = Paso/Proceso
- **Rombo** = Decisión (Sí/No)
- **Óvalo** = Inicio/Fin
- **Flecha** = Dirección del flujo
- **Cilindro** = Datos/Base de datos

---

## Plantilla de Mapeo de Flujo

```
INICIO
  ↓
[Recibir Entrada]
  ↓
¿Válida?  ─→ No ─→ [Rechazar] ─→ FIN
  ↓
  Sí
  ↓
[Procesar]
  ↓
¿Completado? ─→ No ─→ [Revisar] ─→ [Procesar] (loop)
  ↓
  Sí
  ↓
[Entregar]
  ↓
FIN
```

---

## Fase 1: Documentar Flujo Actual

Entrevista al equipo:
- ¿Por dónde viene el trabajo?
- ¿Qué pasos ocurren?
- ¿Dónde están los cuellos de botella?
- ¿Dónde están los puntos de espera?

---

## Fase 2: Visualizar

Dibuja el flujo con símbolos estándar:
- Usa papel o herramienta digital (Lucidchart, Draw.io, Miro)
- Dibuja flujo actual, no ideal
- Etiqueta cada paso claramente
- Muestra puntos de decisión

---

## Fase 3: Analizar

Busca problemas:
- **Cuellos de botella** — dónde se atrapa el trabajo
- **Loops innecesarios** — trabajo que regresa múltiples veces
- **Esperas largas** — pasos que esperan entrada
- **Pasos redundantes** — trabajo duplicado

---

## Fase 4: Mejorar

Para cada problema:
- ¿Se puede automatizar este paso?
- ¿Se puede eliminar este paso?
- ¿Se puede reordenar para eficiencia?
- ¿Se puede paralelizar?

---

## Anti-Patrones

- **Flujo demasiado detallado** — pierde la imagen general
- **Dibuja el flujo ideal en lugar del actual** — no es realista
- **Sin etiquetas claras** — confuso para otros
- **Mapeo una vez y nunca actualizado** — los procesos cambian

---

## Recuperación

- **Equipo no entiende cómo entra el trabajo:** Comienza con un ejemplo específico
- **Flujo es demasiado complejo:** Divide en sub-flujos
- **Análisis no genera mejoras:** Involucra al equipo en sesión de mejora

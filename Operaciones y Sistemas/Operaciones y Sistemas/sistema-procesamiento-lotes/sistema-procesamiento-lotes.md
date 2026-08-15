---
name: sistema-procesamiento-lotes
description: "Diseña workflows de procesamiento por lotes para tareas repetitivas como facturación, publicación de contenido e informes para ahorrar horas cada semana."
allowed-tools: Read Write Glob
metadata:
  author: Imperio Digital
  version: "1.0"
---

# Sistema de Procesamiento por Lotes

## Cuándo Usar Este Skill

Usa este skill cuando necesites:
- Agrupar tareas repetitivas en lotes eficientes en lugar de hacerlas una por una
- Diseñar workflows por lotes para facturación, publicación de contenido, correo electrónico o informes
- Ahorrar tiempo eliminando cambios de contexto en tareas similares
- Crear un cronograma de lotes recurrente que se ajuste al ritmo semanal

**NO** uses este skill para procesos en tiempo real, proyectos únicos o tareas que requieren respuesta inmediata. Este es para agrupar tareas recurrentes en bloques de tiempo eficientes.

---

## Principio Fundamental

LOS CAMBIOS DE CONTEXTO SON EL IMPUESTO OCULTO PARA LOS EMPRENDEDORES SOLITARIOS — AGRUPAR TAREAS SIMILARES EN BLOQUES DE TIEMPO DEDICADOS ELIMINA EL COSTO DE CAMBIO Y PUEDE AHORRAR 5-10 HORAS POR SEMANA.

---

## Fase 1: Identificar Tareas Agrupables

Audita las tareas actuales para encontrar oportunidades de agrupación.

### Información Requerida

| Información | Qué Preguntar | Valor Por Defecto |
|-------|------------|---------|
| **Auditoría de tareas** | "Lista todas las tareas recurrentes que haces semanalmente — todo, incluso las pequeñas." | Sin valor por defecto |
| **Mayores pérdidas de tiempo** | "¿Qué tareas haces varias veces al día que podrían agruparse?" | Sin valor por defecto |
| **Cronograma actual** | "¿Tienes días específicos para ciertas tareas, o todo es ad hoc?" | Ad hoc |
| **Herramientas utilizadas** | "¿Qué herramientas usas para tareas recurrentes?" | Sin valor por defecto |
| **Horas punta** | "¿Cuándo eres más productivo?" | Mañana |

### Puntuación de Candidatos de Lote

Evalúa cada tarea para potencial de agrupación:

```
## Evaluación de Candidatos de Lote

| Tarea | Frecuencia | Tiempo Cada Una | Total Semanal | ¿Tareas Similares? | Puntuación de Lote |
|------|-----------|-----------|-------------|---------------|-------------|
| Responder correos electrónicos | 10x/día | 5 min | 4+ horas | Sí — todos los correos | ALTA |
| Publicar contenido social | Diario | 15 min | 1.5 horas | Sí — todo contenido | ALTA |
| Enviar facturas | 4x/mes | 20 min | 1.3 horas | Sí — toda facturación | MEDIA |
| Llamadas con clientes | 5x/semana | 30 min | 2.5 horas | Sí — todas llamadas | MEDIA |
```

**Criterios de agrupación:** La tarea es similar cada vez, no requiere acción inmediata, puede agruparse sin consecuencias negativas.

**PUNTO DE CONTROL: Confirma qué tareas agrupar antes de diseñar workflows.**

---

## Fase 2: Diseñar Workflows por Lotes

Crea workflows específicos para cada lote.

### Plantilla de Workflow por Lote

Para cada lote, define:

```
## Lote: [Nombre de Categoría]

**Tareas incluidas:** [Lista de tareas específicas agrupadas]
**Frecuencia:** [Diario / 2x semana / Semanal / Quincenal / Mensual]
**Duración:** [Duración del bloque de tiempo]
**Mejor momento:** [Cuándo en el día/semana]
**Herramientas necesarias:** [Herramientas abiertas durante este lote]

### Configuración Previa al Lote (2 min)
1. [Cierra todas las pestañas y herramientas no relacionadas]
2. [Abre [herramientas específicas] necesarias para este lote]
3. [Extrae la cola/lista de elementos a procesar]

### Proceso de Lote
1. [Paso 1 — haz esto para TODOS los elementos antes de pasar al paso 2]
2. [Paso 2 — haz esto para TODOS los elementos antes de pasar al paso 3]
3. [Paso 3 — haz esto para TODOS los elementos]

### Post-Lote (2 min)
1. [Marca el lote como completado]
2. [Anota cualquier elemento que necesite seguimiento]
3. [Cierra herramientas de lote, vuelve al workflow normal]
```

### Lotes Comunes de Emprendedores Solitarios

**Lote de Contenido (semanal, 2-3 horas):**
- Escribe todos los posts de redes sociales de la semana
- Programa todos los posts en la herramienta de programación
- Redacta boletín de correo electrónico
- Pone en cola contenido de blog

**Lote de Admin (semanal, 1-2 horas):**
- Procesa todas las facturas
- Reconcilia gastos
- Responde correos electrónicos no urgentes
- Actualiza estados del proyecto

**Lote de Comunicación (diario, 30-60 min):**
- Todas las respuestas de correo electrónico en un bloque
- Todas las respuestas de Slack/mensaje
- Todos los correos de voz y devoluciones de llamadas

**Lote de Clientes (2x/semana):**
- Agrupa todas las llamadas de clientes en los mismos días
- Procesa toda la feedback del cliente
- Envía todas las actualizaciones del cliente

**PUNTO DE CONTROL: Presenta workflows por lotes para revisión.**

---

## Fase 3: Cronograma Semanal

Mapea lotes a un calendario semanal.

### Plantilla de Cronograma de Lote

```
## Cronograma de Lote Semanal

| Día | Mañana (Punta) | Mediodía | Tarde |
|-----|---------------|--------|-----------|
| Lun | Trabajo profundo | Lote de comunicación | Llamadas de clientes |
| Mar | Trabajo profundo | Lote de comunicación | Lote de contenido |
| Mié | Trabajo profundo | Lote de comunicación | Llamadas de clientes |
| Jue | Trabajo profundo | Lote de comunicación | Lote de admin |
| Vie | Trabajo profundo | Lote de comunicación | Planificación + revisión |
```

### Reglas de Programación

- Agrupa tareas creativas durante las horas de energía máxima
- Agrupa tareas administrativas y de comunicación durante períodos de baja energía
- Nunca programes más de 3 bloques de lote por día
- Deja espacio en blanco — la sobre-agrupación crea un cronograma rígido que se rompe en la primera interrupción
- Protege un día "sin lote" para trabajo flexible o inesperado

---

## Fase 4: Optimizar

Refina lotes con el tiempo para máxima eficiencia.

### Rastreador de Eficiencia de Lote

```
## Registro de Eficiencia de Lote

| Semana | Lote | Tiempo Planeado | Tiempo Real | Elementos Procesados | Notas |
|------|-------|-------------|-------------|-----------------|-------|
| [#] | [Nombre] | [X min] | [X min] | [#] | [¿Qué lo ralentizó?] |
```

### Tácticas de Optimización

- Si un lote constantemente toma más tiempo del planeado, divídelo en dos lotes más pequeños
- Si un lote toma menos de 15 minutos, combínalo con otro lote similar
- Crea listas de verificación o plantillas para cada paso del lote para reducir el tiempo de reflexión
- Automatiza el trabajo previo (pre-ordena correos electrónicos, auto-genera borradores de facturas)

### Revisión Mensual de Lote

1. ¿Qué lotes ahorraron más tiempo?
2. ¿Qué lotes me molestan? (Rediseña o delega)
3. ¿Hay nuevas tareas que deberían agruparse?
4. ¿Todavía estoy haciendo cosas una por una que pertenecen a un lote?

---

## Anti-Patrones

- **Agrupar todo** — algunas tareas necesitan respuesta en tiempo real (problemas urgentes de clientes, decisiones urgentes). No agrupes eso.
- **Lotes demasiado largos** — un lote de 4 horas causa fatiga. Limita a 2 horas, toma un descanso, luego reanuda.
- **Cronograma rígido sin flexibilidad** — si el cronograma de lotes no tiene buffer, una interrupción rompe toda la semana.
- **Agrupación sin cola** — necesitas un lugar para recopilar elementos entre lotes (carpeta de bandeja de entrada, lista de tareas, cola de borradores).
- **Actualmente no agrupar** — hacer "lote de correo electrónico" pero revisar el correo 10 otras veces durante el día derrota el propósito.

---

## Recuperación

- **El usuario sigue interrumpiendo lotes por elementos "urgentes":** Define qué realmente requiere respuesta inmediata vs. qué puede esperar el siguiente lote. La mayoría de elementos "urgentes" pueden esperar 2-4 horas.
- **Los lotes toman demasiado tiempo:** El lote incluye demasiados elementos o demasiados tipos de tareas. Divide en sub-lotes.
- **El usuario no puede mantener el cronograma:** Comienza con UN lote (el de mayor impacto). Agrega más solo después de que el primero se convierta en un hábito.
- **Algunas tareas no encajan en ningún lote:** Crea un lote semanal "misceláneo" para tareas pequeñas únicas que se acumulan.
- **El usuario trabaja de forma reactiva y rechaza la programación:** Enmarca la agrupación como "tú eliges cuándo reaccionar" en lugar de "dejas de reaccionar". Es responsabilidad controlada, no rigidez.

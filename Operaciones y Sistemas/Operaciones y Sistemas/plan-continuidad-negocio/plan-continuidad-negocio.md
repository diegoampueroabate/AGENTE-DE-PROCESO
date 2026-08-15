---
name: plan-continuidad-negocio
description: "Desarrolla planes de continuidad empresarial con evaluación de riesgos, procedimientos de recuperación y protocolos de comunicación para mantener las operaciones durante crisis."
allowed-tools: Read Write Glob
metadata:
  author: Imperio Digital
  version: "1.0"
---

# Plan de Continuidad del Negocio

## Cuándo Usar Este Skill

Usa este skill cuando necesites:
- Crear un plan para mantener las operaciones comerciales en funcionamiento durante interrupciones
- Identificar funciones críticas del negocio y sus procedimientos de recuperación
- Construir protocolos de comunicación para emergencias y crisis
- Prepararte para escenarios como fallas tecnológicas, emergencias de salud, desastres naturales o falta de disponibilidad de personas clave

**NO** uses este skill para respuesta a incidentes de ciberseguridad, planificación de seguros o evaluaciones de responsabilidad legal. Este es para planificación de continuidad operacional.

---

## Principio Fundamental

UN PLAN DE CONTINUIDAD DEL NEGOCIO ES SEGURO QUE TE ESCRIBES A TI MISMO — EL MOMENTO PARA CONSTRUIRLO ES CUANDO NO LO NECESITAS, PORQUE CUANDO LO NECESITES, NO TENDRÁS TIEMPO PARA CONSTRUIRLO.

---

## Fase 1: Evaluación de Riesgos

Identifica qué podría interrumpir el negocio y cuán severamente.

### Información Requerida

| Información | Qué Preguntar | Valor Por Defecto |
|-------|------------|---------|
| **Tipo de negocio** | "¿Qué hace tu negocio y cómo entregas valor?" | Sin valor por defecto — debe proporcionarse |
| **Flujos de ingresos** | "¿Cuáles son tus principales fuentes de ingresos?" | Sin valor por defecto |
| **Herramientas/plataformas clave** | "¿Qué herramientas son críticas para las operaciones diarias?" | Sin valor por defecto |
| **Estructura del equipo** | "¿Eres solo tú o tienes miembros del equipo/contratistas?" | Emprendedor solo |
| **Mayor temor** | "¿Qué escenario te mantiene despierto de noche en el negocio?" | Sin valor por defecto |

### Identificación de Riesgos

Puntúa cada riesgo en probabilidad (1-5) e impacto (1-5):

```
## Matriz de Evaluación de Riesgos

| Escenario de Riesgo | Probabilidad | Impacto | Puntuación de Riesgo | Prioridad |
|--------------|-----------|--------|-----------|----------|
| Herramienta/plataforma principal se cae | 3 | 5 | 15 | ALTA |
| Enfermedad de persona clave (2+ semanas) | 3 | 4 | 12 | ALTA |
| Pérdida de datos / brecha | 2 | 5 | 10 | MEDIA |
| Falla del proveedor | 2 | 3 | 6 | MEDIA |
| Desastre natural | 1 | 4 | 4 | BAJA |
```

**PUNTO DE CONTROL: Confirma la evaluación de riesgos antes de construir procedimientos de recuperación.**

---

## Fase 2: Procedimientos de Recuperación

Construye planes de recuperación específicos para cada riesgo de prioridad alta y media.

### Mapa de Funciones Críticas

```
## Funciones Críticas del Negocio

| Función | Herramientas Requeridas | Objetivo de Tiempo de Recuperación | Responsable | Persona de Respaldo |
|----------|---------------|----------------------|-------------|---------------|
| Entrega al cliente | [herramientas] | 24 horas | [Nombre] | [Nombre/Ninguno] |
| Procesamiento de pagos | [herramientas] | 4 horas | [Nombre] | [Nombre/Ninguno] |
| Comunicación | [herramientas] | 1 hora | [Nombre] | [Nombre/Ninguno] |
```

### Plantilla de Procedimiento de Recuperación

Para cada riesgo de alta prioridad, documenta:

```
## Plan de Recuperación: [Escenario de Riesgo]

**Desencadenante:** [Qué indica que este escenario está sucediendo]
**Severidad:** [Crítica / Mayor / Menor]
**Objetivo de Tiempo de Recuperación:** [Qué tan rápido debe recuperarse]

### Acciones Inmediatas (primeras 1-2 horas)
1. [Paso de acción con instrucciones específicas]
2. [Paso de acción]
3. [Paso de acción]

### Recuperación a Corto Plazo (24-72 horas)
1. [Paso de acción]
2. [Paso de acción]

### Retorno a la Normalidad
1. [Paso de acción]
2. [Revisión post-incidente]

### Recursos Necesarios
- [Herramienta, contacto, documento o acceso necesario]
```

**PUNTO DE CONTROL: Presenta procedimientos de recuperación para revisión.**

---

## Fase 3: Protocolo de Comunicación

Define quién debe ser informado de qué, cuándo y cómo durante una interrupción.

### Plan de Comunicación de Crisis

```
## Plan de Comunicación de Crisis

| Parte Interesada | Notificar Dentro de | Método | Plantilla de Mensaje | Responsable |
|-------------|--------------|--------|-----------------|-------------|
| Clientes activos | 4 horas | Correo electrónico | Aviso de interrupción del servicio | [Nombre] |
| Equipo/contratistas | 1 hora | Slack/texto | Actualización operacional | [Nombre] |
| Proveedores clave | 24 horas | Correo electrónico | Evaluación de impacto | [Nombre] |
| Seguidores en redes sociales | 24 horas | Post de plataforma | Actualización de estado | [Nombre] |
```

### Plantillas de Mensaje

Proporciona plantillas pre-escritas para cada grupo de stakeholders:

```
**Notificación al cliente:**
Asunto: Actualización de Servicio de [Nombre del Negocio]

Hola [Nombre],

Quiero informarte sobre [descripción breve de la situación]. Aquí está lo que significa para ti:
- [Impacto en su proyecto/servicio]
- [Lo que estamos haciendo al respecto]
- [Línea de tiempo de resolución esperada]

Enviaré otra actualización antes de [fecha/hora]. Si tienes preguntas urgentes, [método de contacto].

[Nombre]
```

---

## Fase 4: Mantenimiento

Asegura que el plan se mantenga actualizado y accesible.

### Almacenamiento y Acceso del Plan

- Almacena el plan en al menos 2 ubicaciones (nube + copia de seguridad local)
- Comparte el acceso con cualquier persona de respaldo o asistente virtual
- Incluye credenciales de inicio de sesión en un gestor de contraseñas seguro con acceso de emergencia

### Cronograma de Revisión

- **Trimestral:** Revisa la información de contacto y el acceso a herramientas
- **Semestralmente:** Prueba un procedimiento de recuperación de principio a fin
- **Anualmente:** Revisión y actualización completa del plan
- **Después de cualquier incidente:** Actualiza el plan con lecciones aprendidas

### Hoja de Contactos de Emergencia

```
## Contactos de Emergencia

| Contacto | Rol | Teléfono | Correo Electrónico | Cuándo Contactar |
|---------|------|-------|-------|----------------|
| [Nombre] | Operador de respaldo | [#] | [email] | Cualquier interrupción importante |
| [Nombre] | Soporte del proveedor de hosting | [#] | [email] | El sitio se cae |
| [Nombre] | Contador | [#] | [email] | Problemas financieros |
```

---

## Anti-Patrones

- **Plan existe pero nadie puede encontrarlo** — un plan bloqueado en una herramienta que está caída durante la crisis es inútil. Almacénalo de forma accesible.
- **Demasiado detallado para ser útil** — un plan de 50 páginas no se leerá durante una emergencia. Mantén los pasos de recuperación a 5-7 acciones por escenario.
- **Punto único de falla ignorado** — si solo tú tienes la contraseña, el inicio de sesión o el conocimiento, ESO ES el riesgo.
- **Nunca probado** — un plan que nunca ha sido probado es una teoría, no un plan. Ejecuta un ejercicio de mesa anualmente.
- **Escrito una vez y olvidado** — los cambios empresariales hacen que los planes antiguos sean irrelevantes. Revisa regularmente.

---

## Recuperación

- **El usuario no tiene una persona de respaldo:** Identifica la información mínima que un asistente virtual de emergencia contratado necesitaría para mantener las funciones críticas en funcionamiento durante 48 horas. Documenta eso.
- **El usuario tiene demasiados riesgos para planificar:** Enfócate en los 3 principales por puntuación de riesgo. Un plan para 3 riesgos es mejor que no hay plan para 20.
- **El usuario piensa que es demasiado pequeño para necesitar esto:** Pregunta "¿Qué sucede con tus clientes si estás en el hospital durante una semana?" Ese es el iniciador de la conversación.
- **El usuario ya experimentó una interrupción:** Usa el incidente como el primer caso de estudio. Documenta qué sucedió, qué funcionó, qué falló, y construye el plan a partir de ahí.
- **El usuario no tiene equipo al que delegar:** Construye un documento "romper vidrio" — instrucciones mínimas para que una persona de confianza mantenga el negocio vivo durante 72 horas.

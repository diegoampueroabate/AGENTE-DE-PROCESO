---
name: matriz-decisiones
description: "Crea matrices de decisión ponderadas para opciones empresariales con criterios, puntuación y lógica de recomendación para eliminar la emoción de las decisiones."
allowed-tools: Read Write Glob
metadata:
  author: Imperio Digital
  version: "1.0"
---

# Matriz de Decisiones

## Cuándo Usar Este Skill

Usa este skill cuando necesites:
- Comparar múltiples opciones empresariales usando criterios ponderados y objetivos
- Tomar una decisión de contratación, proveedor, herramienta o estrategia con un razonamiento claro
- Eliminar sesgo emocional de una opción empresarial puntuando opciones sistemáticamente
- Documentar la razón de la decisión para stakeholders o referencia futura

**NO** uses este skill para decisiones simples sí/no, opciones de vida personal o decisiones donde una opción ya es claramente superior. Esto es para decisiones empresariales complejas y multi-criterios.

---

## Principio Fundamental

UNA MATRIZ DE DECISIONES NO TOMA LA DECISIÓN POR TI — HACE TU PENSAMIENTO VISIBLE PARA QUE PUEDAS VER DÓNDE LA INTUICIÓN Y LOS DATOS ESTÁN DE ACUERDO O EN CONFLICTO.

---

## Fase 1: Enmarcar la Decisión

Define la decisión claramente antes de construir la matriz.

### Información Requerida

| Información | Qué Preguntar | Valor Por Defecto |
|-------|------------|---------|
| **Declaración de decisión** | "¿Qué decisión específica estás tomando? Enúnciala como una pregunta." | Sin valor por defecto — debe proporcionarse |
| **Opciones** | "¿Cuáles son tus opciones 2-5?" | Sin valor por defecto — mínimo 2 requerido |
| **Criterios** | "¿Qué factores importan más en esta decisión? (costo, velocidad, calidad, riesgo, etc.)" | Sugiere 5-7 según tipo de decisión |
| **Stakeholders** | "¿Quién está afectado o necesita aprobar esta decisión?" | Emprendedor solo (tú mismo) |
| **Cronograma** | "¿Cuándo necesita tomarse esta decisión?" | Esta semana |

### Tipos de Decisión y Criterios Sugeridos

| Tipo de Decisión | Criterios Sugeridos |
|--------------|-------------------|
| **Herramienta/Software** | Costo, facilidad de uso, características, integraciones, escalabilidad, soporte |
| **Proveedor/Socio** | Precio, calidad, confiabilidad, comunicación, experiencia, términos |
| **Contratación** | Coincidencia de habilidades, ajuste cultural, disponibilidad, tarifa, calidad de cartera |
| **Estrategia** | Impacto en ingresos, esfuerzo, riesgo, tiempo para resultados, alineación con objetivos |
| **Mercado/Producto** | Tamaño del mercado, competencia, potencial de margen, dificultad de ejecución |

**PUNTO DE CONTROL: Confirma la declaración de decisión, opciones y criterios antes de construir la matriz.**

---

## Fase 2: Pesar y Puntuar

Construye la matriz con criterios ponderados y puntúa cada opción.

### Ponderación de Criterios

Asigna pesos que totalicen 100% en todos los criterios:

```
## Pesos de Criterios

| Criterio | Peso | Razón |
|----------|--------|-----------|
| Impacto en ingresos | 30% | Directamente vinculado al objetivo empresarial |
| Esfuerzo de implementación | 25% | Recursos limitados como emprendedor solo |
| Nivel de riesgo | 20% | No puedo permitirme grandes reveses |
| Tiempo para resultados | 15% | Necesito ganancias en 90 días |
| Escalabilidad | 10% | Importante pero no urgente |
| **Total** | **100%** | |
```

### Puntuación de Opciones

Puntúa cada opción 1-5 en cada criterio con justificación breve:

```
## Matriz de Decisiones: [Declaración de Decisión]

| Criterio | Peso | Opción A | Puntuación | Opción B | Puntuación | Opción C | Puntuación |
|----------|--------|----------|-------|----------|-------|----------|-------|
| Impacto en ingresos | 30% | [razón] | 4 | [razón] | 3 | [razón] | 5 |
| Esfuerzo | 25% | [razón] | 3 | [razón] | 5 | [razón] | 2 |
| Riesgo | 20% | [razón] | 4 | [razón] | 4 | [razón] | 3 |
| Tiempo para resultados | 15% | [razón] | 5 | [razón] | 3 | [razón] | 2 |
| Escalabilidad | 10% | [razón] | 3 | [razón] | 4 | [razón] | 5 |

## Puntuaciones Ponderadas

| Opción | Puntuación Ponderada | Rango |
|--------|---------------|------|
| Opción A | 3.80 | 1 |
| Opción C | 3.40 | 2 |
| Opción B | 3.85 | 1 |
```

**PUNTO DE CONTROL: Presenta la matriz puntuada y obtén validación del usuario en puntuaciones antes de entregar la recomendación.**

---

## Fase 3: Recomendar

Entrega una recomendación clara con razonamiento.

### Formato de Recomendación

```
## Recomendación

**Ganador:** [Opción] con una puntuación ponderada de [X.XX]

**Por qué gana:** [2-3 oraciones explicando los diferenciadores clave]

**Compensación clave:** [Lo que sacrificas al elegir esta opción vs. el subcampeón]

**Verificación de instinto:** ¿Esto coincide con tu intuición? Si la matriz dice Opción A pero tu instinto dice Opción B, examina qué criterios podrían estar sub-ponderados.
```

### Análisis de Sensibilidad

Prueba si el resultado se mantiene si los pesos cambian:
- "Si aumentas el peso de [criterio] en 10%, [Opción X] adelantaría a [Opción Y]"
- Marca cualquier decisión donde las dos opciones principales están dentro de 0.3 puntos — esto significa que la decisión es cerrada y factores adicionales pueden importar

### Banderas de Riesgo

Anota cualquier opción que puntúe por debajo de 2 en un criterio de peso alto, incluso si la puntuación total es alta. Una única debilidad crítica puede hundiruna opción por lo demás fuerte.

---

## Fase 4: Documentar

Proporciona un registro de decisión para referencia futura.

### Plantilla de Registro de Decisión

```
## Registro de Decisión

**Decisión:** [Declaración]
**Fecha:** [Fecha]
**Tomador de decisión:** [Nombre]
**Opción elegida:** [Opción]
**Puntuación ponderada:** [X.XX]
**Razones clave:** [3 puntos de bala]
**Riesgos clave:** [Riesgos conocidos de la opción elegida]
**Fecha de revisión:** [Cuándo evaluar si fue la decisión correcta]
```

---

## Anti-Patrones

- **Demasiados criterios** — más de 7 criterios diluye la señal. Fuerza-clasifica y mantén los 5-7 principales.
- **Pesos iguales** — dar a cada criterio 20% significa que no has pensado en qué importa más.
- **Puntuación sin justificación** — una puntuación de 4 no significa nada sin una razón de una línea.
- **Ignorar desacuerdo de instinto** — si la matriz dice una cosa y tu instinto dice otra, los pesos probablemente son incorrectos.
- **Usar una matriz para decisiones obvias** — si ya sabes la respuesta, no construyas una matriz para justificarla.

---

## Recuperación

- **El usuario no puede identificar criterios:** Sugiere 5 basados en el tipo de decisión (ver tabla anterior) y pídele que elimine cualquiera que no aplique.
- **Las opciones son demasiado similares:** Agrega criterios diferenciadores o aumenta la granularidad de puntuación a 1-10 en lugar de 1-5.
- **Las puntuaciones son todas 3s:** Desafía al usuario — "Un 3 significa promedio. ¿Esta opción es verdaderamente promedio en [criterio], o es realmente un 2 o un 4?" Presiona por diferenciación honesta.
- **El usuario no está de acuerdo con el resultado:** Pregunta qué puntuación cambiaría. A menudo, un criterio re-puntuado invierte el resultado, revelando lo que realmente valoran.
- **Las stakeholders no están de acuerdo en los pesos:** Que cada parte interesada asigne pesos independientemente, luego promedia. Discute cualquier criterio donde los pesos difieren en más del 15%.

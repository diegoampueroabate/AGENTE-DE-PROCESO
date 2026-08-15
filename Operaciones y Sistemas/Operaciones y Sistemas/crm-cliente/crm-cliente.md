---
name: crm-cliente
description: "Crea un sistema completo de gestión de relaciones con clientes en Notion con etapas de pipeline, registros de contactos, valores de trato y seguimiento de seguimientos. Úsalo cuando un usuario quiera reemplazar el seguimiento de clientes basado en hojas de cálculo, configurar un CRM sin software pagado o construir un pipeline de ventas desde cero."
allowed-tools: Read Write Glob mcp__claude_ai_Notion__notion-create-database mcp__claude_ai_Notion__notion-create-pages mcp__claude_ai_Notion__notion-search mcp__claude_ai_Notion__notion-fetch
metadata:
  author: Imperio Digital
  version: "1.0"
---

# CRM de Cliente

## Cuándo Usar Este Skill

Usa este skill cuando necesites:
- Construir un pipeline de ventas y base de datos de clientes en Notion desde cero
- Reemplazar un sistema de seguimiento de clientes basado en hojas de cálculo, notas adhesivas o memoria
- Configurar recordatorios de seguimiento para que los tratos no caigan por las grietas
- Importar una lista de contactos existente en una base de datos CRM estructurada
- Crear vistas filtradas para etapas de pipeline, seguimientos vencidos y tratos cerrados

**NO** uses este skill para:
- Migración de CRM empresarial desde Salesforce, HubSpot o Pipedrive (demasiado complejo para una base de datos Notion)
- Gestión de catálogo de productos de comercio electrónico (esquema diferente necesario)
- Gestión de proyectos o seguimiento de tareas (usa un skill de rastreador de proyectos en su lugar)
- Automatización de correo electrónico o secuencias de goteo (esto rastrea contactos, no envía correos electrónicos)

---

## Referencia Rápida: Características del CRM

| Característica | Detalles |
|---------|---------|
| Propiedades | 11 campos por registro de contacto |
| Etapas de pipeline | 6 por defecto (Prospecto a Cerrado Ganado/Perdido) |
| Vistas de base de datos | 4 vistas filtradas pre-construidas |
| Seeding | Importación en lote desde lista de contactos proporcionada por usuario |
| Guía de uso | Operaciones diarias/semanales documentadas para el usuario |

## Referencia Rápida: Esquema de Base de Datos

| Propiedad | Tipo | Propósito | Valor Por Defecto |
|----------|------|---------|---------|
| Nombre | Título | Nombre completo del contacto | Requerido |
| Empresa | Texto enriquecido | Nombre de organización o negocio | Vacío |
| Correo Electrónico | Correo Electrónico | Dirección de correo electrónico principal | Vacío |
| Teléfono | Número de Teléfono | Número de teléfono principal | Vacío |
| Etapa de Pipeline | Seleccionar | Posición actual en pipeline de ventas | Prospecto |
| Valor del Trato | Número (USD) | Cantidad de trato estimada o real | 0 |
| Próximo Seguimiento | Fecha | Cuándo contactar a continuación | Vacío |
| Último Contacto | Fecha | Cuándo hablaste o enviaste correo por última vez | Vacío |
| Fuente | Seleccionar | Cómo encontraste este contacto | Otro |
| Notas | Texto enriquecido | Historial de conversación, contexto, preferencias | Vacío |
| Etiquetas | Multi-seleccionar | Categorías para filtrar y agrupar | Vacío |

### Etapas de Pipeline

```
Prospecto --> Calificado --> Propuesta Enviada --> Negociación --> Cerrado Ganado --> Cerrado Perdido
```

| Etapa | Significado | Acción Requerida |
|-------|---------|-----------------|
| Prospecto | Contacto nuevo, aún no evaluado | Investiga y califica dentro de 48 horas |
| Calificado | Ajuste, presupuesto e interés confirmados | Programa discovery call o envía presentación |
| Propuesta Enviada | Propuesta o cotización entregada | Seguimiento dentro de 5 días hábiles |
| Negociación | Negociación activa de términos | Responde dentro de 24 horas |
| Cerrado Ganado | Trato firmado, pago recibido o acordado | Incorpora y entrega |
| Cerrado Perdido | El trato no se cerró | Registra razón en Notas, revisita en 90 días |

### Opciones de Fuente

Referencia, Sitio Web, Redes Sociales, Contacto Frío, Evento, Entrada, Otro

### Etiquetas Por Defecto

`prospecto-caliente`, `vip`, `cliente-anterior`, `necesita-seguimiento`, `socio-referencia`, `no-contactar`, `alto-valor`, `retainer`, `proyecto-único`

---

## Workflow Principal

CADA CONSTRUCCIÓN DE CRM COMIENZA CREANDO LA BASE DE DATOS CON EL ESQUEMA COMPLETO ANTES DE AGREGAR CUALQUIER CONTACTO -- NUNCA AGREGUES PÁGINAS A UNA BASE DE DATOS QUE FALTEN PROPIEDADES.

### Fase 1: Recopilar Requisitos del CRM

Recopila estos detalles del usuario antes de construir nada:

1. **Página padre Notion** -- dónde debe vivir la base de datos CRM
2. **Lista de contactos** -- contactos existentes a importar (hoja de cálculo, lista o dictados)
3. **Etapas de pipeline personalizadas** -- cualquier modificación a las 6 etapas por defecto
4. **Etiquetas personalizadas** -- etiquetas adicionales más allá de las por defecto
5. **Moneda** -- USD es el valor por defecto para Valor del Trato; confirma o cambia

Si el usuario proporciona solo el elemento 1, procede con todos los valores por defecto.

**Plantilla breve para solicitudes vagas:**

```
Voy a construir tu CRM en Notion. Necesito respuestas rápidas:

1. ¿Cuál página Notion debería usar para crear la base de datos del CRM?
2. ¿Tienes contactos existentes para importar?
3. ¿Algún cambio al pipeline por defecto: Prospecto > Calificado > Propuesta Enviada > Negociación > Cerrado Ganado > Cerrado Perdido?
4. ¿Alguna etiqueta personalizada para agregar?
5. ¿Moneda para valores de trato? (por defecto: USD)
```

### Fase 2: Localizar la Página Padre en Notion

1. Llama a `notion-search` con el nombre de página o palabras clave que el usuario proporcionó
2. Identifica la página padre correcta de los resultados de búsqueda
3. Confirma el ID de página con el usuario si existen múltiples coincidencias

```
Página Notion encontrada: "Business Hub"
ID de Página: abc12345-def6-7890-ghij-klmnopqrstuv

Voy a crear la base de datos del CRM bajo esta página. ¿Correcto?
```

**SI LA PÁGINA NO SE ENCUENTRA:**
- Pide al usuario el título exacto de la página o una URL
- Intenta `notion-search` de nuevo con el término corregido
- **Después de 3 búsquedas fallidas, detente y explica:** "No puedo encontrar esa página. Por favor, verifica que la página exista y que la integración de Notion tenga acceso. Verifica Configuración > Conexiones en Notion."

### Fase 3: Crear la Base de Datos del CRM

1. Llama a `notion-create-database` con el ID de página padre y esquema completo:

**Título de Base de Datos:** `CRM de Cliente`

**Propiedades a crear:**

```
Nombre           -> título
Empresa        -> texto_enriquecido
Correo Electrónico          -> correo_electrónico
Teléfono          -> numero_telefono
Etapa de Pipeline -> seleccionar
  opciones: Prospecto (gris), Calificado (azul), Propuesta Enviada (púrpura),
           Negociación (naranja), Cerrado Ganado (verde), Cerrado Perdido (rojo)
Valor del Trato     -> número (formato: dólar)
Próximo Seguimiento -> fecha
Último Contacto   -> fecha
Fuente          -> seleccionar
  opciones: Referencia (verde), Sitio Web (azul), Redes Sociales (rosa),
           Contacto Frío (amarillo), Evento (naranja), Entrada (púrpura), Otro (gris)
Notas          -> texto_enriquecido
Etiquetas           -> multi_seleccionar
  opciones: prospecto-caliente (rojo), vip (amarillo), cliente-anterior (marrón),
           necesita-seguimiento (naranja), socio-referencia (verde),
           no-contactar (gris), alto-valor (azul), retainer (púrpura),
           proyecto-único (rosa)
```

2. Verifica la creación llamando a `notion-fetch` con el ID de base de datos devuelto
3. Confirma con el usuario con un resumen de todas las propiedades configuradas

**SI LA CREACIÓN DE BASE DE DATOS FALLA:**
- Verifica el ID de página padre llamando a `notion-fetch` en él
- Reintenta una vez con los mismos parámetros
- **Si falla de nuevo:** "La creación de base de datos falló. Por favor, verifica que la integración de Notion tenga acceso de 'Puede editar' en esa página. Ve a la página > menú de tres puntos > Conexiones."

### Fase 4: Semilla con Contactos Existentes

**OMITE ESTA FASE si el usuario no tiene contactos existentes para importar.**

1. Analiza la lista de contactos del usuario. Acepta estos formatos:
   - CSV (nombre, empresa, correo electrónico, teléfono, etapa, valor trato)
   - Lista de puntos con detalles
   - Lenguaje natural ("John en Acme, conocido en la conferencia, proyecto potencial de $5K")
   - Pegada de hoja de cálculo separada por pestañas

2. Para cada contacto, mapea datos al esquema:
   - **Nombre** -- requerido, extrae de los datos
   - **Empresa** -- extrae si se menciona, sino deja vacío
   - **Correo Electrónico/Teléfono** -- extrae si se proporciona; **NUNCA adivines o fabriques**
   - **Etapa de Pipeline** -- infiere del contexto, por defecto "Prospecto"
   - **Valor del Trato** -- extrae si se menciona, por defecto 0
   - **Próximo Seguimiento** -- establece a 3 días hábiles desde hoy para etapas Prospecto/Calificado
   - **Último Contacto** -- establece a hoy si se menciona recientemente
   - **Fuente** -- infiere del contexto (p.ej., "conocido en conferencia" = Evento), por defecto "Otro"
   - **Notas** -- captura cualquier contexto extra proporcionado
   - **Etiquetas** -- infiere del contexto (p.ej., "gran oportunidad" = prospecto-caliente, alto-valor)

3. Llama a `notion-create-pages` para agregar contactos en lotes
4. Reporta resultados de seeding con nombres, etapas y valores de trato

**SI EL ANÁLISIS DE CONTACTO ES AMBIGUO:**
- Presenta tu interpretación al usuario antes de crear páginas
- Ejemplo: "Interpreté 'John, Acme, trato de 5K' como: Nombre: John, Empresa: Acme, Valor del Trato: $5,000, Etapa: Prospecto. ¿Correcto?"

**SI LA CREACIÓN EN LOTE FALLA PARCIALMENTE:**
- Reporta qué contactos tuvieron éxito y cuáles fallaron
- Reintenta contactos fallidos individualmente
- Si los reintentos fallan, proporciona detalles para entrada manual

### Fase 5: Crear Vistas de Base de Datos

**Notion MCP no soporta crear vistas programáticamente.** Proporciona instrucciones exactas para estas 4 vistas:

```
VISTAS RECOMENDADAS (crea estas en Notion):

1. TODOS LOS CONTACTOS (Vista de tabla)
   - Ordenar: Último Contacto (descendente)
   - Sin filtro
   - Propósito: Lista completa de contactos, más recientemente contactados primero

2. PIPELINE ACTIVO (Vista de dashboard)
   - Agrupar por: Etapa de Pipeline
   - Filtro: Etapa de Pipeline no es "Cerrado Ganado" Y no es "Cerrado Perdido"
   - Ordenar: Valor del Trato (descendente)
   - Propósito: Dashboard Kanban de tratos activos

3. SEGUIMIENTOS VENCIDOS (Vista de tabla)
   - Filtro: Próximo Seguimiento es en o antes de hoy
   - Ordenar: Próximo Seguimiento (ascendente)
   - Propósito: Lista de acción diaria de quién necesita contacto

4. TRATOS GANADOS (Vista de tabla)
   - Filtro: Etapa de Pipeline es "Cerrado Ganado"
   - Ordenar: Valor del Trato (descendente)
   - Propósito: Seguimiento de ingresos y referencia de cliente anterior
```

### Fase 6: Entregar Guía de Uso

Presenta esta guía de operaciones después de que se construya el CRM:

```
CRM DE CLIENTE — GUÍA DE USO

RUTINA DIARIA (5 minutos):
1. Abre vista "Seguimientos Vencidos"
2. Trabaja a través de cada contacto vencido
3. Después de cada punto de contacto, actualiza:
   - Último Contacto -> fecha de hoy
   - Próximo Seguimiento -> próxima fecha de contacto planeada
   - Notas -> lo que discutiste
   - Etapa de Pipeline -> avanza si es apropiado

AGREGAR UN NUEVO CONTACTO:
1. Haz clic en "+ Nuevo" en vista "Todos los Contactos"
2. Rellena Nombre (requerido) y detalles conocidos
3. Establece Etapa de Pipeline a "Prospecto"
4. Establece Próximo Seguimiento a 3 días hábiles desde ahora
5. Etiqueta con etiquetas relevantes

MOVER UN TRATO ADELANTE:
1. Abre vista de dashboard "Pipeline Activo"
2. Arrastra la tarjeta de contacto a la siguiente etapa
3. Actualiza Notas con lo que sucedió
4. Ajusta Valor del Trato si el alcance cambió
5. Establece Próximo Seguimiento:
   - Calificado: 3-5 días
   - Propuesta Enviada: 5 días hábiles
   - Negociación: 1-2 días

CERRAR UN TRATO:
- Ganado: Mueve a "Cerrado Ganado", actualiza Valor del Trato, agrega Notas
- Perdido: Mueve a "Cerrado Perdido", registra razón en Notas,
  establece Próximo Seguimiento a 90 días para re-engagement

REVISIÓN SEMANAL (15 minutos):
1. Verifica si hay tratos estancados (sin actividad en 7+ días)
2. Revisa contactos no contactados en 30+ días
3. Cuenta tratos por etapa — un pipeline saludable tiene contactos en cada etapa
```

---

## Lista de Verificación Pre-Entrega

Ejecuta esta lista de verificación antes de entregar el CRM. **NO OMITAS NINGÚN ELEMENTO.**

| Verificación | Qué Verificar | Cómo |
|-------|----------------|-----|
| Base de datos existe | Creada y accesible | `notion-fetch` con ID de base de datos |
| 11 propiedades | Cada propiedad de esquema configurada | Verifica en respuesta `notion-fetch` |
| Etapas de pipeline | Todas las etapas existen como opciones de selección | Verifica opciones de selección |
| Opciones de fuente | Todas las fuentes existen como opciones de selección | Verifica opciones de selección |
| Etiquetas configuradas | Todas las etiquetas existen como opciones multi-seleccionar | Verifica opciones multi-seleccionar |
| Formato Valor del Trato | Número formateado como dólar/moneda | Verifica formato de número |
| Fechas configuradas | Seguimiento y Último Contacto son tipo fecha | Verifica tipos de propiedad |
| Contactos sembrados | Todos los contactos proporcionados creados | Cuenta páginas vs. esperado |
| Sin duplicados | El mismo contacto no fue agregado dos veces | Verifica nombres duplicados |
| Seguimientos establecidos | Prospecto/Calificado tienen fechas de Próximo Seguimiento | Verifica fechas en páginas |
| Instrucciones de vistas | El usuario recibió todas las 4 configs de vistas | Confirma en entrega |
| Guía de uso | El usuario recibió guía de operaciones | Confirma en entrega |
| Página padre correcta | Base de datos bajo página solicitada | Verifica padre en fetch |

```
Lista de Verificación Pre-Entrega:
  [x] Base de datos creada y accesible
  [x] 11 propiedades configuradas
  [x] Etapas de pipeline correctas
  [x] Opciones de fuente presentes
  [x] Etiquetas configuradas
  [x] Valor del Trato formateado correctamente
  [x] Propiedades de fecha configuradas
  [x] Todos los contactos sembrados con éxito
  [x] Sin contactos duplicados
  [x] Fechas de seguimiento establecidas para Prospecto/Calificado
  [x] Instrucciones de setup de vistas entregadas
  [x] Guía de uso entregada
  [x] Base de datos bajo página padre correcta
```

---

## Recuperación y Solución de Problemas

### La Búsqueda de Notion No Devuelve Resultados

1. Pide al usuario el título exacto de la página
2. Intenta buscar con una palabra clave más corta (p.ej., "Ventas" en lugar de "Panel de Ventas y Ingresos")
3. Pide al usuario que confirme que la página está compartida con la integración de Notion
4. **Después de 3 búsquedas fallidas:** "No puedo ubicar esa página. Verifica Configuración > Conexiones en Notion y confirma que la integración tiene acceso."

### La Creación de Base de Datos Falla

1. Verifica el ID de página padre con `notion-fetch`
2. Verifica si hay errores de permiso en la respuesta
3. Reintenta una vez con los mismos parámetros
4. **Si falla de nuevo:** "Por favor, ve a la página padre > menú de tres puntos > Conexiones y asegúrate de que la integración tenga acceso de 'Puede editar'."

### La Siembra de Contacto Falla Parcialmente

1. Reporta qué contactos tuvieron éxito y cuáles fallaron
2. Reintenta contactos fallidos individualmente con `notion-create-pages`
3. Si los reintentos individuales fallan, proporciona detalles de contacto formateados para entrada manual

### Límites de Tasa de la API de Notion

1. Pausa durante 10 segundos entre lotes
2. Reduce el tamaño de lote a 5 contactos por llamada
3. **NO omitas contactos debido a límites de tasa** -- desacelera y reintenta

### Modificación de Esquema Después de Construcción

**Notion MCP no soporta modificar esquemas de bases de datos existentes.** Instruye al usuario:
- Agregar propiedad: Haz clic en "+" en la fila de encabezado, elige tipo, nómbralo
- Modificar propiedad: Haz clic en encabezado de columna > "Editar propiedad" > cambia tipo/nombre/opciones

### Detección de Duplicados

Marca posibles duplicados antes de crear páginas:
```
Posibles duplicados detectados:
  "John Smith" y "John Smith Jr." — ¿la misma persona?
  "Acme Corp" aparece dos veces con correos electrónicos diferentes
Por favor, confirma qué entradas mantener antes de que importe.
```
**NUNCA crees registros de contactos duplicados** -- siempre confirma con el usuario primero.

---

## Anti-Patrones

- **NO** crees la base de datos sin el esquema de propiedad completo -- agregar propiedades después de que las páginas existan causa problemas de alineación
- **NO** adivines o fabriques direcciones de correo electrónico, números de teléfono o valores de trato
- **NO** omitas la confirmación de página padre -- crear bajo la página incorrecta es difícil de deshacer
- **NO** siembres contactos sin confirmación de análisis para datos ambiguos
- **NO** entregues sin la guía de uso -- el CRM solo es valioso si el usuario sabe cómo operarlo
- **NO** prometas características que Notion no puede entregar -- esto es una base de datos, no un CRM con correos electrónicos automatizados o recordatorios
- **NO** crees vistas programáticamente -- Notion MCP no soporta esto; proporciona instrucciones manuales

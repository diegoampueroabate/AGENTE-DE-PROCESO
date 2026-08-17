---
tipo: informe-direccion
fecha: 2026-08-17
periodo: últimos 30 días
fuente: API de Meta, consultada 02:0x del 17-ago
---

# Informe de Dirección — 17 de agosto de 2026

Primer informe del sistema. Datos traídos de la API de Meta esta madrugada, no de documentos.

## 1 · El número primero

**La cuenta principal de Óptica Ferreira pasó de `IN_GRACE_PERIOD` a `UNSETTLED` y ya no se puede consultar.**

`UNSETTLED` significa que el período de gracia terminó y hay saldo impago con Meta. La cuenta `1946094894848` tiene medio de pago registrado, pero el cobro no está pasando. Es la cuenta que concentra el 58% de toda la inversión que AGC administra.

Esto no es lo mismo que ayer. Ayer era una advertencia; hoy es una deuda vencida.

## 2 · Los números que importan · últimos 30 días

| Cuenta | Gasto 30d | Impresiones | CTR | CPM | Costo por clic | Frecuencia |
|---|---:|---:|---:|---:|---:|---:|
| Ópticas Ferreira Spa | $13.635.429 | 9.517.255 | 1,59% | $1.433 | **$90** | **5,25** |
| Sweet Mayorista | $1.273.585 | 789.159 | 6,04% | $1.614 | $27 | 3,30 |
| MQFJOYAS | $691.514 | 267.255 | 5,31% | $2.587 | $49 | 2,61 |
| Ferreira · web | — | — | — | — | — | — |
| **Ferreira · principal** | **no consultable** | | | | | |

**Total visible: $15.600.528 en 30 días.** Y falta la cuenta principal, que es la más grande.

Concentración sobre lo visible: **Ferreira Spa es el 87%**.

## 3 · Qué dicen esos números

**Ferreira tiene fatiga creativa, y es medible.** Frecuencia de **5,25** en 30 días —cada persona vio los anuncios más de cinco veces— con un CTR de **1,59%** contra el 6,04% de Sweet y el 5,31% de MQF. El costo por clic de Ferreira es **3,4 veces** el de Sweet.

No es un problema de audiencia ni de presupuesto: es que la misma gente está viendo las mismas piezas demasiadas veces. Sweet corre a frecuencia 3,30 y le va casi cuatro veces mejor en CTR con un CPM más alto.

**Recomendación:** rotación de creativos en Ferreira, no reasignación de presupuesto. Es una acción de nivel *Dirección aprueba* — la propuesta se puede armar sin tocar nada, pero ejecutar espera tu confirmación.

> ### Lo que este informe NO puede decir
>
> **No hay dato de venta real de ningún cliente este mes.** Por lo tanto este informe **no emite recomendación de distribución de presupuesto** entre cuentas.
>
> No es prudencia excesiva: en la propia cuenta de Ferreira, cruzar gasto contra venta por comuna invirtió el ranking completo que daba el costo por conversación — Petorca 18,93× y Peumo 17,54× contra Buin 2,27× y Talca 3,59×. Recomendar plata mirando solo el costo de la métrica intermedia es recomendar al revés.
>
> **Para el próximo informe hace falta la venta real de los 4 clientes que pagan.**

## 4 · Qué no funcionó

El seguimiento del estado de pago de Ferreira. La cuenta llevaba días en período de gracia, se documentó como riesgo, y aun así **se dejó pasar hasta que venció**. Un riesgo escrito que nadie mira no es distinto de un riesgo que no se escribió.

Se corrige con este informe: el estado de las cuentas se consulta contra la API en cada revisión, no se lee de un documento de ayer.

## 5 · Decisiones del mes

| Decisión | Nivel | Responsable |
|---|---|---|
| Regularizar el pago de `1946094894848` | **Dirección decide** | Diego · hoy |
| Rotar credenciales expuestas (Meta, Google, GHL) + 3 PDF de Ferreira en Descargas | **Dirección decide** | Diego · hoy |
| Confirmar tratamiento tributario con el contador | **Dirección decide** | Diego · esta semana |
| Rotación de creativos en Ferreira por fatiga | **Dirección aprueba** | propuesta lista, espera confirmación |
| Instalar el informe mensual en los 4 clientes que pagan | **Dirección aprueba** | plantilla lista |
| Reclutamiento: 3 o 1 proceso por trimestre | **Dirección decide** | Diego |

## 6 · Qué se necesita del cliente

De los 4 que pagan: **venta real del mes**, ticket promedio y tasa de cierre. Sin eso, todo informe siguiente vuelve a topar con el mismo muro.

## 7 · Correcciones a lo documentado

- **Kristus** (`1742661176389545`): el conector no está bloqueado por Meta. El motivo real es *"Ads MCP is gradually being rolled out"* — es un despliegue gradual, no una restricción de la cuenta. Puede habilitarse solo más adelante.
- **Ferreira · web** (`1228089025451973`): activa y con medio de pago, pero **sin gasto en 30 días**. Está corriendo vacía.
- **Decohogar** (`2001305703797220`) y **Fernando Saavedra (Read-Only)**: activas y **sin medio de pago**. No son clientes; conviene soltar los accesos.

---

*Generado por `/informe-direccion` · Dirección Comercial Externa · by AGC Partners*

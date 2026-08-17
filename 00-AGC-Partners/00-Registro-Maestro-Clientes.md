---
tipo: registro-maestro
ultima_actualizacion: 2026-08-16
fuente_cuentas: API de Meta (ads_get_ad_accounts + gasto 90d), validado por Dirección
clientes_pagados: 4
clientes_sin_cobro: 2
---

# Registro Maestro de Clientes — AGC Partners

> **Este es el documento más importante de toda la operación.** Es la única fuente de la identidad de cada cliente. El mismo *nombre canónico* se usa en las carpetas, en AGENTE ADS MANAGER y en finanzacrm. Si un cliente cambia de estado, responsable o servicio, se actualiza AQUÍ primero.

Reconciliado el 2026-08-16 contra la API de Meta. Ver [[00-Reconciliacion-Cuentas]] para el detalle del cruce.

## Clientes que pagan — 4

| # | Nombre canónico | Cuentas Meta | Portafolio | Gasto 90d | Carpeta | Responsable | Estado |
|---|---|---|---|---|---|---|---|
| 02 | Óptica Ferreira | `1946094894848` (principal) · `1049367834100232` · `1228089025451973` (web) | Opticas Administrador · Optica ferreira | **$44.031.244 CLP** | [[Cliente-02-Optica-Ferreira]] | `[FALTA][[` | Activo |
| 03 | Sweet Mayorista | `3268702886644262` | Sweet Mayorista CLP | $1.875.333 CLP | [[Cliente-03-Sweet-Mayorista]] | `[FALTA][[` | Activo |
| 01 | MQFJOYAS | `540299303050126` (principal) · `1084379184156268` (RO) | Joyas Bañadas | $1.595.160 CLP | [[Cliente-01-MQFJOYAS]] | `[FALTA][[` | Activo |
| 05 | Kristus | `1742661176389545` | Kristus | conector deshabilitado | [[Cliente-05-Kristus]] | `[FALTA][[` | Activo |

## Clientes sin cobro — 2

Se atienden como clientes pero no facturan. La distinción es operativa: define cadencia, alcance y prioridad ante conflicto de recursos.

| # | Nombre canónico | Cuenta Meta | Gasto 90d | Carpeta | Relación |
|---|---|---|---|---|---|
| 08 | Pelucas Antonella Avatte | `1046688890037024` | $24.596 CLP | [[Cliente-08-Pelucas-Antonella]] | Madre de Diego |
| 09 | MASAIFIT Calama | `2050074379205397` | sin gasto | [[Cliente-09-MASAIFIT-Calama]] | Hermana de Kristus · posible cobro futuro |

## Cerrados

No operar. Los accesos de Meta siguen activos por decisión de Dirección.

| Nombre | Cuentas Meta | Valor documental | Nota |
|---|---|---|---|
| Grupal Corp | `1105772127681155` | — | Terminó el 2026-08-16. US$22.620 en los 90 días previos. Competencia en consultoría |
| Importadora Carlitos | `1729894761760673` | **alto** | Ciclo completo documentado · $339.965 CLP en 90d |
| Distribuidora Odawe | `1167311576461422` · `982114147515866` (RO) | **alto** | Caso de cuenta de bajo volumen · $37.282 CLP en 90d |
| Fernando Saavedra | `4790014717936362` · `25323494634007589` (RO) | — | Sin trabajo en curso |
| Luis y Nicol (Luis Piña) | `1439936280849728` | — | Nunca fue cliente; solo acceso publicitario |
| Decohogar Textil | `2001305703797220` | — | Nunca fue cliente. Sin método de pago |
| graduado.cl | `770685053487560` | `[FALTA]` | Sin gasto en 90 días. Confirmar estado |
| Método Starter | — | — | El ID que usaba ADS MANAGER (`1599064547837452`) **no existe** en Meta |

## Cuentas propias de AGC

| Nombre | Cuenta Meta | Uso |
|---|---|---|
| Diego Ampuero Legal Tech | `1197364611603619` | Adquisición propia · $220.293 CLP en 90d |
| Diego Enrique Ampuero Abate | `1201545757671148` | Personal · sin gasto |

---

## Riesgos abiertos

**Concentración del 93%.** La cartera que paga suma ≈ $47,5 M CLP en 90 días y Óptica Ferreira aporta $44,0 M. Sweet Mayorista y MQFJOYAS juntos no llegan al 8%. Kristus no es medible por conector.

**`1946094894848` pasó a `UNSETTLED` el 2026-08-17 y ya no se puede consultar.** Es la cuenta principal de Óptica Ferreira y concentra el 58% de toda la inversión administrada. El período de gracia terminó: hay saldo impago con Meta. Tiene medio de pago registrado, pero el cobro no está pasando.

Ayer era una advertencia; hoy es una deuda vencida. Regularizarlo tiene prioridad sobre cualquier optimización de la cartera.

**La cartera se redujo a la mitad en un día.** Grupal Corp, Importadora Carlitos y Distribuidora Odawe salieron. Los prospectos que entran el lunes 17 no son crecimiento opcional: son reposición.

---

## Los clientes cerrados son materia prima

Un cliente cerrado tiene la historia completa y ya no cambia, lo que lo hace mejor fuente para documentar el método que uno activo. Carlitos y Odawe están marcados con `valor_documental: alto` y alimentan:

- `01-SOPs-Maestros/` — el procedimiento tal como se ejecuta, no como se imagina
- `02-Base-Conocimiento/` — decisiones y sus consecuencias
- Ángulos y guiones probados, reutilizables en los prospectos nuevos

---

## Reglas de uso

1. **Un solo nombre por cliente.** No "MQF", "Joyas", "Marcela" — siempre "MQFJOYAS".
2. **Un cliente puede tener varias cuentas publicitarias.** Se listan todas y una se marca como principal.
3. Cualquier alta, baja o cambio se hace primero aquí y luego se propaga a los sistemas.
4. Cada `Cliente-0X/00-Ficha-Cliente.md` debe coincidir exactamente con su fila.
5. Estados válidos: `Activo` · `En pausa` · `Onboarding` · `Cerrado`.
6. Modalidades válidas: `paga` · `sin cobro` · `cerrado`.
7. Los `account_id` se verifican contra la API de Meta, nunca se copian de memoria ni de documentos antiguos. Dos IDs estuvieron meses en uso sin existir.

---
tipo: registro-historico
estado: cerrado
fecha: 2026-08-16
validado_por: Dirección
---

# Reconciliación de cuentas publicitarias — cerrada

> Registro de cómo se resolvió el desfase entre las tres versiones de la cartera que existían hasta el 2026-08-16.
> **La fuente de verdad vigente es [[00-Registro-Maestro-Clientes]].** Este documento se conserva por trazabilidad, no para consulta operativa.

## El problema

Había tres versiones de la verdad y ninguna coincidía:

| Fuente | Decía |
|---|---|
| `00-Registro-Maestro-Clientes.md` | 7 clientes, casi todos los `account_id` en `_reconciliar_` |
| `AGENTE ADS MANAGER/CLAUDE.md` | 11 negocios, con dos IDs inexistentes y una atribución equivocada |
| API de Meta | **20 cuentas reales** |

Operar campañas sobre la tabla de ADS MANAGER significaba tocar la cuenta equivocada, y dos de sus IDs fallaban en silencio porque no existen.

## Método

Se consultó `ads_get_ad_accounts` para obtener el universo real, y `ads_get_ad_entities` a nivel de cuenta con `date_preset: last_90d` para separar operación viva de archivo. El cruce se hizo contra los nombres de portafolio y las carpetas de `Clientes/`. Dirección validó cada fila el mismo día.

## Errores corregidos

| Decía | Realidad |
|---|---|
| Óptica Ferreira = una sola cuenta, `1946094894848` | Son tres cuentas en dos portafolios |
| Graduados = `1909525409411405` | ID inexistente. El real es `770685053487560` (graduado.cl) |
| Método Starter = `1599064547837452` | ID inexistente. No hay tal cuenta |
| MQF Joyas · Importadora Carlitos · Distribuidora Odawe = "PENDIENTE" | Las tres existen; Odawe además estaba marcada como pausada y está activa |
| `540299303050126` = cuenta huérfana sin dueño | Es "Marcela Quezada Ferrada" — MQF Joyas |

## Hallazgos que sobrevivieron al cierre

**Concentración del 92%.** La cartera activa suma ≈ $47,9 M CLP en 90 días y Óptica Ferreira aporta $44,0 M.

**`1946094894848` en `IN_GRACE_PERIOD`.** Cuenta principal de Óptica Ferreira, 58% de la inversión total administrada, con un problema de pago sin resolver.

**Tres negocios facturaban sin figurar en ningún registro:** Luis y Nicol, Pelucas Antonella y Fernando Saavedra. Dos resultaron no ser clientes; Antonella se incorporó como cliente sin cobro.

**No existía procedimiento de cierre de accesos.** Cuentas de relaciones terminadas siguen accesibles desde el usuario de Meta de Dirección. Dirección decidió no gestionarlo por ahora; queda registrado como riesgo conocido.

## Lección para el sistema

Los `account_id` se verifican siempre contra la API, nunca se copian de memoria ni de documentos antiguos. Dos IDs estuvieron meses en uso sin corresponder a ninguna cuenta real, y nadie lo notó porque las consultas fallaban sin ruido.

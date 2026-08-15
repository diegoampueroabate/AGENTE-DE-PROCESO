# Registro Maestro de Clientes — AGC Partners

> **Este es el documento más importante de toda la operación.** Es la única fuente de la identidad de cada cliente. El mismo *nombre canónico* se usa en las carpetas, en AGENTE ADS MANAGER y en finanzacrm. Si un cliente cambia de estado, responsable o servicio, se actualiza AQUÍ primero.

Última actualización: 2026-06-16

## Tabla maestra

| # | Nombre canónico | Servicio(s) | Meta account_id (ADS) | ID finanzacrm | Board Monday | Carpeta Drive | Responsable | Estado |
|---|---|---|---|---|---|---|---|---|
| 01 | MQFJOYAS | _por confirmar_ | _reconciliar_ | _pend_ | _pend_ | Clientes/Cliente-01-MQFJOYAS | _pend_ | Activo |
| 02 | Óptica Ferreira | _por confirmar_ | act_1946094894848 | _pend_ | _pend_ | Clientes/Cliente-02-Optica-Ferreira | _pend_ | Activo |
| 03 | Sweet Mayorista | _por confirmar_ | _reconciliar_ | _pend_ | _pend_ | Clientes/Cliente-03-Sweet-Mayorista | _pend_ | Activo |
| 04 | Importadora Carlitos | _por confirmar_ | _reconciliar_ | _pend_ | _pend_ | Clientes/Cliente-04-Importadora-Carlitos | _pend_ | Activo |
| 05 | Kristus | _por confirmar_ | _reconciliar_ | _pend_ | _pend_ | Clientes/Cliente-05-Kristus | _pend_ | Activo |
| 06 | Distribuidora Odawe | _por confirmar_ | _reconciliar_ | _pend_ | _pend_ | Clientes/Cliente-06-Distribuidora-Odawe | _pend_ | Activo |
| 07 | Grupal Corp | _por confirmar_ | act_1105772127681155 | _pend_ | _pend_ | Clientes/Cliente-07-Grupal-Corp | _pend_ | Activo |

## ⚠️ Reconciliación pendiente con ADS MANAGER

AGENTE ADS MANAGER lista estos "Negocios Activos" que **no mapean 1:1** con los 7 clientes actuales. Hay que verificar cuáles siguen activos, cuáles son cuentas viejas y cuál account_id pertenece a cada cliente real:

| Negocio en ADS MANAGER | account_id | ¿Es cliente actual? |
|---|---|---|
| Graduados | act_1909525409411405 | _verificar_ |
| Grupal Corp | act_1105772127681155 | Sí → Cliente-07 |
| Óptica Ferreira | act_1946094894848 | Sí → Cliente-02 |
| Método Starter | act_1599064547837452 | _verificar_ |
| Fernando Saavedra | act_4790014717936362 | _verificar_ |

## Reglas de uso
1. **Un solo nombre por cliente.** No "MQF", "Joyas", "Marcela" — siempre "MQFJOYAS".
2. Cualquier alta/baja/cambio se hace primero aquí y luego se propaga a los sistemas.
3. Cada `Cliente-0X/00-Ficha-Cliente.md` debe coincidir exactamente con su fila de esta tabla.
4. "Estado" válido: Activo · En pausa · Onboarding · Cerrado.

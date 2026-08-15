# SOP — Fuente de Verdad (qué vive en cada sistema)

> Regla de oro: **cada dato vive en UN solo sistema.** Si no sabes dónde registrar algo, esta es la respuesta. Duplicar = caos.

## Mapa de sistemas

| Sistema | Es la fuente de verdad de... | Identidad del cliente |
|---|---|---|
| **Registro Maestro de Clientes** (este repo) | Quién es cada cliente y dónde está en cada sistema | Nombre canónico |
| **AGENTE ADS MANAGER** | Campañas, métricas Meta, creativos, gasto, ROAS | `account_id` Meta |
| **finanzacrm** (app) | Facturación, cobranza, ingresos, márgenes | ID en BD |
| **Monday** | Estado de la operación: tareas, etapas, responsables, entregas | Item del board "Clientes" |
| **Google Drive** | Documentos y activos (espejo de estas carpetas) | Carpeta del cliente |
| **GoHighLevel (GHL)** | Conversaciones con cliente, leads/CRM puntual | Contacto/pipeline |

## Reglas
1. **Estado del trabajo** → Monday. Nunca en chats sueltos.
2. **Plata** (lo que se factura/cobra/gana) → finanzacrm. El markdown de finanzas es solo resumen.
3. **Rendimiento de ads** → ADS MANAGER. No se copian métricas a mano a otros lados salvo para el reporte al cliente.
4. **Documentos** (SOW, contratos, reportes, activos) → Drive (espejo de estas carpetas).
5. **Identidad** → Registro Maestro. Un cambio de nombre/responsable/estado se hace ahí primero.

## Antipatrón a eliminar
- Mismo cliente con 3 nombres distintos en 3 sistemas → lo arregla el Registro Maestro.
- Estado de la cuenta "en la cabeza" de una persona → va a Monday.
- Métricas pegadas a mano en WhatsApp → salen del reporte estándar.

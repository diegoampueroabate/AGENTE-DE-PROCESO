---
tipo: sop-maestro
creado: 2026-08-17
decision: quedarse con GoHighLevel y explotarlo, no reemplazarlo
costo_actual: USD 427/mes (297 plan Unlimited + ~130 consumo WhatsApp)
---

# SOP — Sacarle el máximo a GoHighLevel

Decisión de Dirección del 17-ago-2026: **no se reemplaza GHL, se explota.**

Es la decisión correcta por una razón que conviene tener escrita.

## GoHighLevel no es un costo. Es el producto.

La Propuesta de agosto promete instalar, por $1.190.000 CLP al mes:

| Lo que promete el programa | Lo que hace GHL |
|---|---|
| "CRM: cada cliente, pedido y conversación queda registrado" | Contacts · Conversations · Custom Fields |
| "Empleado digital 24/7: responde, toma pedidos, filtra y deriva" | Workflows + Conversations AI |
| "Seguimiento automático que no deja plata en la mesa" | Workflows con triggers |
| "Dashboard con tus números clave" | Reporting por location |
| Agendamiento de operativos y citas | Calendars · Slots · Appointments |

**GHL *es* la "plataforma comercial" que AGC vende.** Se paga USD 427 al mes por la herramienta con la que se factura mucho más que eso. Mirado así, el plan Unlimited a $297 fijos —sin importar cuántos clientes— se abarata solo a medida que la cartera crece: hoy son $74 por cliente, con 10 clientes serían $30.

Lo que sí hay que atacar es el margen del intermediario en WhatsApp. Ver `06-Planeacion-y-Finanzas/Stack-y-presupuesto-de-herramientas.md`.

---

## Lo primero: el setup está desactualizado

`AGENTE GHL/subcuentas/` tiene **una sola subcuenta configurada: `grupal-corp`** — el cliente que terminó la relación en agosto.

**Ninguno de los cuatro clientes que pagan tiene configuración documentada.** Óptica Ferreira, Sweet Mayorista, MQFJOYAS y Kristus no aparecen. Y el `CLAUDE.md` del repo dice que el proyecto está en "Bootstrap (Fase 0) — recién creado".

Eso significa que, muy probablemente, **cada cliente se está armando a mano desde cero.** Que es exactamente el cuello de botella de 5-7 días que el diagnóstico ya nombró.

---

## La palanca número uno: Snapshots

GHL tiene, a nivel de agencia, **Snapshots**: plantillas clonables que se empujan a una location completa. Pipelines, workflows, calendarios, formularios, embudos, campos personalizados — todo, de una vez.

**Construir un snapshot bueno una vez, y cada cliente nuevo queda instalado en minutos en lugar de días.**

Es la función con mejor retorno de toda la plataforma y es la que se pierde cuando cada cuenta se arma a mano. Ataca directamente el hallazgo 02 del diagnóstico.

### El snapshot base de AGC — qué debe traer

Sale de lo que el programa promete y de lo que ya se sabe que funciona:

**Pipeline comercial** (para el negocio del cliente, no para AGC):
1. Conversación iniciada
2. Calificado
3. Agendado
4. Asistió / Compró
5. Perdido — con motivo obligatorio

**Workflows mínimos:**
- *Respuesta inmediata*: el paso 4 del recorrido —esperar respuesta— es donde se cae la venta en Sweet, Odawe y Ferreira por igual. Ver `SOP-Atencion-por-WhatsApp.md`.
- *Seguimiento al que no responde*: 24 h, 72 h, 7 días. Es la sección que casi nadie escribe y la que sostiene el resultado.
- *Confirmación de asistencia* el día previo, para los operativos de Ferreira.
- *Solicitud de reseña* después de la compra.
- *Reactivación de cartera dormida* a los 60 días.

**Campos personalizados** que hacen posible el informe mensual:
`origen_del_lead` · `comuna` · `monto_venta` · `producto` · `motivo_de_perdida`

Ese último grupo es el más importante y explico por qué abajo.

**Calendario** con los slots de operativo por comuna.

---

## Lo que resuelve el problema más grande de la operación

Tres clientes tienen escrito en su propio 360 que **las ventas del live no se registran en ningún sistema**: Sweet dice "el 90%+ de las ventas no existe en el sistema", Odawe que "las 300+ ventas por live NO se ingresan". Ver `02-Base-Conocimiento/El-dato-de-venta-no-existe.md`.

Por eso ningún informe puede cruzar gasto contra venta.

**GHL es la respuesta a eso, y ya está pagado.** Si el campo `monto_venta` se llena en la oportunidad al cerrar, el dato existe por primera vez — y con él se puede calcular ROAS real, rentabilidad y todo lo que hoy es imposible.

**No es un proyecto nuevo: es usar un campo de una plataforma que ya se está pagando.**

---

## Auditoría — hacer esto antes que nada

Media hora, en las cuatro subcuentas. Sin este dato cualquier decisión sobre GHL es una corazonada de USD 5.000 al año.

| Pregunta | Por qué importa |
|---|---|
| ¿Cuántos workflows activos hay por cliente? | Si son 0-1, se está pagando una plataforma de automatización sin automatizar |
| ¿Existe un pipeline con etapas reales? | Sin pipeline no hay embudo que diagnosticar |
| ¿Se usan calendarios? | Ferreira agenda operativos: debería ser el uso más intenso |
| ¿Hay campos personalizados de venta? | Es lo que desbloquea el informe mensual |
| ¿Se usan formularios o embudos? | Función cara si no se usa |
| ¿Cuántos contactos hay por subcuenta? | Mide si el CRM está vivo o vacío |
| **Factura de WhatsApp desglosada** | Cuánto cobró Meta contra cuánto cobró GHL |

Resultado esperable: si en la práctica se usan dos o tres funciones, el trabajo no es migrar — **es empezar a usar las otras diez que ya se pagan.**

---

## Conectar GHL al ecosistema

El plan Unlimited **incluye acceso a API**. Eso permite tres cosas concretas, en orden de valor:

1. **Leer el pipeline desde el CRM de AGC.** La ficha de cliente muestra su embudo real sin entrar a GHL.
2. **Traer `monto_venta` al informe mensual.** Cierra el círculo de "el dato de venta no existe".
3. **Crear la subcuenta desde `/onboarding-cliente`.** El comando ya da de alta al cliente en la bóveda; que además cree la location con el snapshot aplicado.

**Reglas duras que el repo `AGENTE GHL` ya documenta y hay que respetar:** distinguir siempre agency de location, cumplir los rate limits, y fijar la versión de API. Están en su `CLAUDE.md`.

Y una advertencia: los tokens de GHL están entre las 17 credenciales expuestas. **Rotarlos antes de construir sobre ellos** — `SOP-Rotacion-de-Credenciales.md`, paso 5. Es el único paso de esa guía que puede cortar una automatización de un cliente en vivo.

---

## Orden de trabajo

1. **Auditar** las cuatro subcuentas · 30 min · Diego
2. **Rotar** los 3 tokens de GHL, con cuidado · Diego
3. **Documentar** la subcuenta que mejor esté armada, como línea base
4. **Construir el snapshot base de AGC** a partir de ella
5. **Aplicarlo** a los clientes que estén incompletos
6. **Instalar `monto_venta`** como campo obligatorio al cerrar una oportunidad
7. **Conectar la API** al CRM de AGC — etapa 4 o posterior del plan

Los pasos 1 y 2 son de Diego. Del 3 en adelante se puede delegar a `direccion-ventas`.

## Lo que queda fuera

Reemplazar GHL, autohospedar Chatwoot, o construir un clon. Evaluado y descartado el 17-ago: Chatwoot autohospedado cuesta USD 8.000-24.000 al año en infraestructura y mantención, y un clon de GHL son años de trabajo que no se están vendiendo.

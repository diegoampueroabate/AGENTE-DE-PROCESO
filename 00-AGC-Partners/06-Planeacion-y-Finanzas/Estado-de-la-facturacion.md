---
tipo: hallazgo-financiero
fecha: 2026-08-17
fuente: conector WASABIL (consultado 04:2x) + rendiciones mensuales de Óptica Ferreira
estado: requiere decisión de Dirección y confirmación del contador
---

# Estado real de la facturación de AGC

## La entidad

| | |
|---|---|
| Razón social | **AMPUERO ABATE CONSULTING GROUP LIMITADA** |
| RUT | 78.468.795-3 |
| Empresa en WASABIL | id 2885 |

Es una **Limitada**. Ese dato es el centro de la pregunta tributaria pendiente: la Marca v2.0 decidió "valores netos, boleta exenta de IVA", y esa exención depende de calificar como **sociedad de profesionales** del Art. 42 N°2. Una Limitada puede serlo, pero no lo es por defecto — requiere estar constituida solo por profesionales de igual o complementaria profesión y haber optado por ese régimen.

**Es exactamente la pregunta que el contador tiene que responder por escrito.**

## Lo que dice el conector, verificado

| Campo | Valor |
|---|---|
| `can_issue` | **false** |
| `configured` | **false** |
| `method` | null |
| Certificado digital | no disponible |
| Folios cargados | ninguno |
| Documentos emitidos (histórico completo) | **0** |

**AGC no tiene habilitada la emisión de documentos electrónicos en WASABIL.** Sin certificado, sin folios, sin un solo documento en el historial.

Esto **no** prueba que AGC no esté facturando: puede estar emitiendo por el portal gratuito del SII o por otro proveedor. Lo que sí establece es que WASABIL —el conector que el ecosistema tiene enchufado para facturación— **no sirve hoy para nada**. Cualquier skill que asuma que puede consultar o emitir por ahí va a fallar en silencio.

**Pregunta para Diego:** ¿por dónde se está facturando realmente? Según la respuesta, o se configura WASABIL (certificado + folios) o se cambia el conector por el que corresponda.

## Lo que muestran las rendiciones de Óptica Ferreira

Corrección de un dato que reporté mal antes: el fee de Ferreira **no** es $710.000. Leí solo las primeras filas de la planilla. El total real es **$1.180.000** — $1.000.000 de servicios más $180.000 de edición de video. Está en línea con los $1.190.000 de la Fase 1 del programa, así que no hay discrepancia de precio.

Lo que sí aparece son dos cosas.

### 1 · Una línea de $180.000 mensuales rotulada "SIN BOLETA"

La sección se titula literalmente **"PRODUCCIÓN Y EDICIÓN DE VIDEO (SIN BOLETA)"**, y ahí van los $180.000 de edición. Aparece igual en la rendición de enero y en la del 19-ene al 19-feb.

Son **$2.160.000 al año sin documento tributario**, en un solo cliente. Con la pregunta del régimen de IVA todavía abierta, esto es exposición acumulándose mes a mes.

### 2 · Ferreira recibe 119 videos al mes; el programa incluye 8

La rendición detalla 52 videos en la tanda 1 y 67 en la tanda 2. La edición se cobra a costo variable, **USD 2 por video**, y la propia planilla anota que la edición completa va como *"servicio bonificado"* con un **valor comercial referencial de $12.000 por video**.

| | |
|---|---:|
| Videos incluidos en el programa (Fase 1) | 8 / mes |
| Videos que recibe Ferreira | **119 / mes** |
| Cobrado por edición | $180.000 |
| Valor referencial declarado (119 × $12.000) | **$1.428.000** |
| A tarifario `VID-001` (111 extra × $9.500) | $1.054.500 |

**AGC está regalando entre $1,0 y $1,4 millones de trabajo al mes en un solo cliente.** Casi tanto como el fee completo.

Esto no es un error de cálculo: está escrito y asumido como "bonificado". Es una decisión comercial que nadie tomó explícitamente — se acumuló.

### 3 · La factura se arma hacia atrás, no desde el tarifario

En enero la rendición tiene 4 líneas que suman exactamente $1.000.000. En febrero tiene 11 líneas que suman exactamente $1.000.000. Mismo total, distinto desglose, con montos como $80.000, $70.000, $60.000, $50.000 asignados a conceptos nuevos.

El total se fija primero y las líneas se acomodan después. Es lo contrario de lo que la Marca v2.0 exige del tarifario: *"un tarifario que se negocia deja de ser tarifario"*. Con `11-Tarifario-v2.md` vigente, el desglose debería salir de los códigos.

## Qué hay que decidir

| Punto | Nivel | Quién |
|---|---|---|
| ¿Por dónde se factura realmente? Configurar WASABIL o cambiar de conector | **Dirección decide** | Diego |
| Régimen tributario de la Limitada: ¿sociedad de profesionales o no? | **Dirección decide** | contador, por escrito |
| Los $180.000/mes "sin boleta": regularizar o dejar de facturarlos así | **Dirección decide** | Diego + contador |
| Los 119 videos: subir el fee, bajar el volumen, o dejarlo consciente | **Dirección decide** | Diego |
| Armar el desglose de la rendición desde los códigos del tarifario | **Dirección aprueba** | propuesta lista |

Los dos primeros bloquean corregir el precio de la propuesta. El tercero acumula riesgo cada mes que pasa.

---
tipo: planeacion
creado: 2026-08-17
presupuesto_objetivo: USD 500 / mes
estado: propuesta — requiere confirmar qué se paga hoy
---

# Stack de herramientas y presupuesto

Objetivo declarado: sostener el ecosistema con **USD 500 al mes** o menos.

Precios verificados el 17-ago-2026. Los de video con IA cambian varias veces al año — están marcados.

## Lo que ya se paga

| Herramienta | Plan | USD/mes | Para qué |
|---|---|---:|---|
| **Claude** | Max 5x | **100** | Los agentes. Es el motor de todo esto |
| **GoHighLevel** | Unlimited | **297** | CRM de cliente, automatizaciones, subcuentas ilimitadas + API |
| | | **397** | **ya comprometido** |

**Quedan USD 103.** Ese es el presupuesto real disponible, no 500.

### Sobre el plan de GoHighLevel

$297 es el plan **Unlimited**: subcuentas ilimitadas y acceso a API. El de abajo ($97) permite **3 subcuentas** — con 4 clientes que pagan más 2 sin cobro, no alcanza. El de arriba ($497) sirve para revender la plataforma con marca propia; no aplica hoy.

**Está en el plan correcto.** Con una advertencia: SMS, llamadas, correos y las funciones de IA **se cobran aparte por consumo**, típicamente entre $20 y $150 al mes según volumen. Ese gasto no aparece en la mensualidad y conviene medirlo antes de dar el presupuesto por cerrado.

Bajar a $97 solo tendría sentido si la cartera cayera a 3 clientes — que es exactamente lo contrario del objetivo.

---

## Lo que el CRM va a necesitar

| Herramienta | Plan | USD/mes | Necesario |
|---|---|---:|---|
| **Supabase** | Pro | **25** | **Sí** |
| **Vercel** | Hobby (gratis) | 0 | Sí, y alcanza |
| Dominio propio | — | ~1,25 | Opcional |

**Supabase Pro, y no el gratuito, por una razón concreta:** el plan free **pausa los proyectos tras ~7 días sin actividad**. Es exactamente lo que pasó — cuatro de sus cinco proyectos están pausados ahora mismo, y el esquema del CRM quedó inaccesible dentro de uno de ellos. Pro elimina la pausa y agrega respaldos diarios. Para una base que va a tener datos de clientes, el respaldo no es opcional.

**Vercel Hobby alcanza de sobra.** Es una app interna de un usuario. Pro son $20 que hoy no compran nada.

**Total con el CRM: USD 422.** Quedan **78**.

---

## Lo que ya tienes gratis y conviene no duplicar

| Herramienta | Plan | Para qué |
|---|---|---|
| Meta Ads API | gratis | Campañas, insights, creativos, audiencias |
| Google Drive · Gmail · Calendar | incluido en Workspace | Documentos y correo |
| Canva | conector | Diseño |
| Gamma | conector | Presentaciones |
| Resend | 3.000 correos/mes gratis | Correo transaccional del CRM |
| WASABIL | según plan actual | Facturación SII |
| Obsidian | gratis | La bóveda. **No necesita plugins ni Sync** |
| GitHub | gratis en privado | Los 8 repos |

**Obsidian Sync son $4/mes y no hace falta:** la bóveda ya está en OneDrive y versionada en git. Dos mecanismos de sincronización sobre la misma carpeta es cómo se corrompen los archivos.

---

## Video con IA — dónde está la pregunta de verdad

Aquí es donde conviene detenerse, porque el gasto grande de AGC no es software.

**Se entregan 119 videos al mes solo a Óptica Ferreira.** Se cobran $180.000 CLP de edición y la propia planilla declara un valor referencial de **$1.428.000**. Ese es el costo real que hay que atacar — no los $20 de Vercel.

| Herramienta | Plan | USD/mes | Nota |
|---|---|---:|---|
| **Higgsfield** | Basic | **9** | 120 créditos. Para probar |
| Higgsfield | Pro | 29 | 600-900 créditos |
| Higgsfield | Max | 79 | 1.800-5.400 créditos |
| ElevenLabs | Creator | 22 | Voz clonada |
| MuAPI / Runway | por uso | variable | API de generación |

⚠️ **Higgsfield cambió de planes más de una vez en 2026** y los precios anunciados suelen ser con compromiso anual. Verificar en su página antes de contratar.

### La recomendación, que no es la que esperas

**No contratar nada de video todavía.** Dos razones:

1. **No se sabe cuánto cuesta hoy editar un video.** Sin ese número no hay forma de saber si una herramienta de IA ahorra o suma. Es el mismo dato que falta para calcular rentabilidad por cliente.
2. **Los 119 videos de Ferreira son videos de un negocio real** — el cliente graba con indicaciones y AGC edita. Higgsfield genera video sintético. **No reemplaza lo que se está entregando**; sería otro producto. Y la Marca v2.0 §14 es explícita: *"Fotografía SIEMPRE real: negocios reales, bodegas, mesones, locales. PROHIBIDO stock genérico"*.

Si algo de esto se prueba, que sea **$9 al mes en Higgsfield Basic durante un mes**, con un objetivo escrito antes de partir: *"¿puede producir 10 piezas usables que pasen el Test Final de la marca?"*. Si la respuesta es no, se cancela y no se vuelve a mirar por seis meses.

---

## Resumen

| Concepto | USD/mes |
|---|---:|
| Claude Max 5x | 100 |
| GoHighLevel Unlimited | 297 |
| Supabase Pro | 25 |
| Vercel · Resend · Canva · Gamma · GitHub · Obsidian | 0 |
| **Base operativa** | **422** |
| Prueba de video (opcional, 1 mes) | 9 |
| **Total** | **431** |
| Margen dentro de los 500 | **69** |

Más el consumo variable de GoHighLevel ($20-150), que es la única cifra que puede romper el presupuesto y hoy nadie ha medido.

## Dónde se puede bajar de verdad

**No en las suscripciones.** El 94% del gasto son Claude y GoHighLevel, y los dos son el núcleo: uno son los agentes, el otro es el CRM de cliente y las automatizaciones.

Donde sí hay plata:

1. **Medir el consumo variable de GHL.** Puede ser $20 o $150. Es la mayor incógnita del presupuesto y se resuelve mirando una factura.
2. **Los $1,4 millones mensuales de edición regalados a Ferreira.** Eso es ~USD 1.400 al mes de trabajo entregado sin cobrar — **tres veces todo el presupuesto de software.** Cualquier optimización de herramientas es ruido al lado de esa cifra.
3. **Cancelar lo que no se usa.** Antes de sumar herramientas, revisar qué se está pagando y no se ocupa. Los cuatro proyectos pausados de Supabase sugieren que hay servicios contratados sin uso.

## La regla al evaluar una herramienta nueva

Antes de contratar cualquier cosa, tres preguntas:

- **¿Qué entregable del catálogo produce o acelera?** Si no aparece en `01-SOPs-Maestros/Catalogo-de-Entregables.md`, no hay caso de uso.
- **¿Cuánto cuesta hoy hacer eso a mano?** Sin ese número no se puede saber si ahorra.
- **¿Tiene conector o API?** Una herramienta que no se puede automatizar suma trabajo manual, aunque sea barata.

Y una advertencia que sale de anoche: **el cuello de botella de AGC no son las herramientas.** Es que ningún cliente registra sus ventas, así que no se puede demostrar que el trabajo funciona. Ninguna suscripción arregla eso. Ver `02-Base-Conocimiento/El-dato-de-venta-no-existe.md`.

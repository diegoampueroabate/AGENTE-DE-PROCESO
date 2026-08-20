---
tipo: sop-maestro
creado: 2026-08-17
estado: pendiente de ejecución por Dirección
alcance: las 17 credenciales únicas que están en el historial de git
---

# SOP — Rotación de credenciales expuestas

## Corrección al número: son 17, no 26

El primer conteo (26) contaba **apariciones**, no credenciales distintas. Cinco tokens de Meta y dos de GoHighLevel están repetidos en dos o tres archivos.

| Tipo | Únicas | Dónde |
|---|:-:|---|
| Meta — tokens de sistema y acceso | **12** | `AccessMD/meta_tokens.md` + `.claude/settings.json` |
| Meta — **App Secret** | **1** | `AccessMD/meta_tokens.md`, línea 14 |
| Google / Gemini | **1** | `AccessMD/gemini_api.md` y `CLAUDE.md` línea 217 — *es la misma key en dos lugares* |
| GoHighLevel | **3** | `KEYS.md` + los dos `settings.json` |
| **En el historial de git** | **17** | |
| Supabase (solo en disco, nunca versionado) | 1 | `finanzacrm/.mcp.json` |

## Y el hallazgo que reduce el trabajo a la mitad

**7 de los 12 tokens de Meta pertenecen a clientes que ya no existen.** Esos no se rotan: **se revocan.** Revocar es más rápido y más seguro — rotar deja el camino de acceso abierto con una llave nueva; revocar lo cierra.

| Cliente | Tokens | Estado | Acción |
|---|:-:|---|---|
| **Óptica Ferreira** | 2 | Activo · 93% de la inversión | **Rotar** |
| **Kristus Joyería** | 2 | Activo | **Rotar** |
| **Sweet Mayorista** | 1 | Activo | **Rotar** |
| Grupal Corp | 4 | Cerrado · **es competencia** | **Revocar** |
| Método Starter | 1 | Nunca fue cliente | **Revocar** + borrar la app |
| Fernando Saavedra | 1 | Cerrado | **Revocar** |
| Graduados | 1 | Cerrado | **Revocar** |

**Solo 5 tokens de Meta hay que rotar de verdad.** Los otros 7 se revocan, y con eso desaparece el riesgo sin tocar ninguna campaña viva.

Nota: MQFJOYAS no tiene token propio en el archivo (figura `PENDIENTE`). Se opera por el conector, que es lo correcto.

---

## Hallazgo del 20-ago: los tokens estaban en seis lugares más

Al preparar los repos para compartir aparecieron **seis scripts `.py` versionados** con el token escrito literal (`TOKEN = "EAA..."`):

- `proyectos/grupal_corp/Anuncios/ADS JUNIO/_build/` — 3 archivos
- `proyectos/metodo_starter/anuncios/_upload_ascii/` — 3 archivos

Ya salieron del control de versiones y el `.gitignore` cubre esos patrones.

**No suman credenciales nuevas:** son los mismos dos tokens que el inventario ya contaba, de Grupal Corp y Método Starter. El total de 17 no cambia.

Lo que sí confirma es por qué el paso 2 va antes que cualquier rotación: **revocar el usuario de sistema invalida el token en todos los lugares a la vez**, incluidos los que nadie había encontrado. Perseguir archivo por archivo es cómo se queda uno afuera.

## Orden de ejecución

Ordenado por daño posible, no por comodidad.

### 1 · El App Secret · primero, sin excepción

`AccessMD/meta_tokens.md` línea 14, de la app **STARTER APP**.

Un App Secret no es un token: **es la llave que fabrica tokens.** Quien lo tenga, junto con el App ID —que está en el mismo archivo— puede generar credenciales nuevas aunque rotes todas las demás. Rotar tokens dejando el secret expuesto es cambiar la cerradura dejando puesta la máquina de hacer llaves.

Método Starter nunca fue cliente. **No rotes el secret: borra la aplicación completa** en `developers.facebook.com` → la app → Configuración → Eliminar aplicación. Eso invalida el secret, sus tokens y cualquier cosa derivada, de una sola vez.

*Qué se rompe:* nada. No hay campañas de Método Starter.

### 2 · Revocar los 7 tokens de clientes cerrados

En **Business Manager** de cada portafolio → Configuración del negocio → Usuarios → **Usuarios del sistema** → seleccionar el usuario → **Eliminar**.

Eliminar el usuario del sistema invalida todos sus tokens de golpe. No hay que borrarlos uno por uno.

- **Grupal Corp** (4 tokens) — prioridad dentro de este grupo: terminaron la relación y son competencia directa en consultoría.
- **Método Starter** (1) — queda cubierto por el paso 1 si borras la app.
- **Fernando Saavedra** (1)
- **Graduados** (1)

*Qué se rompe:* nada de la operación actual. Si algún día vuelven, se emiten credenciales nuevas.

Al terminar, borra esas secciones de `AccessMD/meta_tokens.md`.

### 3 · Rotar los 5 tokens de clientes activos

Uno a la vez, verificando entre cada uno. **No los rotes todos juntos**: si algo se cae, no vas a saber cuál fue.

| Orden | Cliente | Tokens | Por qué en ese orden |
|:-:|---|:-:|---|
| 3.1 | Sweet Mayorista | 1 | El más simple. Sirve de ensayo |
| 3.2 | Kristus Joyería | 2 | Su conector no responde igual; si se rompe, no detiene campañas grandes |
| 3.3 | **Óptica Ferreira** | 2 | **El último.** Es el 93% de la inversión y su cuenta ya está en `UNSETTLED` |

**Procedimiento por cliente:**

1. Business Manager → Configuración del negocio → Usuarios del sistema → el usuario → **Generar nuevo token**.
2. Marcar los mismos permisos que tenía. Para Grupal Corp quedaron documentados y sirven de referencia: `ads_management`, `pages_read_engagement`, `pages_manage_ads`, `leads_retrieval`, `instagram_basic`, `instagram_manage_insights`, `business_management`.
3. **No pegues el token nuevo en `AccessMD/`.** Ese patrón queda prohibido — es la causa raíz de todo esto. Si un script lo necesita, va en variable de entorno.
4. Verificar de inmediato: `ads_get_ad_accounts` debe seguir devolviendo la cuenta del cliente.
5. Recién entonces, invalidar el anterior.

**Qué se rompe si sale mal:** las consultas del conector a esa cuenta. Las campañas **siguen corriendo** — un token caído no apaga anuncios, solo impide leerlos y modificarlos. Es recuperable.

**Sobre Ferreira, con cuidado:** su cuenta principal está en `UNSETTLED`. Resuelve el pago **antes** de tocar sus tokens. Si rotas primero y algo falla, vas a tener dos problemas encima del cliente que concentra casi toda tu inversión, y no vas a saber cuál causó qué.

### 4 · La key de Google / Gemini

Es **una sola key** que aparece en dos archivos. La consume el skill `cc-nano-banana-main`, que genera creativos de anuncios.

1. `aistudio.google.com` → API keys → crear una nueva → **eliminar la anterior**.
2. Guardarla como variable de entorno: `setx GEMINI_API_KEY "…"` en PowerShell.
3. En `AGENTE ADS MANAGER/CLAUDE.md` ya quedó `export GEMINI_API_KEY="$GEMINI_API_KEY"`. No la vuelvas a escribir literal.

*Qué se rompe:* la generación de imágenes con NanoBanana, hasta que exportes la nueva. Nada más.

### 5 · Los 3 tokens de GoHighLevel

Panel de GHL → Configuración → **Private Integrations**. Revocar los tres y emitir los que hagan falta.

Antes de revocar, revisa **qué subcuenta usa cada uno** — `AGENTE GHL/subcuentas/` tiene el mapa. Si alguno alimenta una automatización viva de un cliente, esa automatización se detiene al revocarlo.

*Qué se rompe:* los flujos de GHL que usen esos tokens. **Es el único paso de esta lista que puede afectar a un cliente en tiempo real.** Hazlo cuando puedas mirarlo, no un viernes a las siete.

### 6 · El token de Supabase

`finanzacrm/.mcp.json`. **No está en git** — el `.gitignore` lo cubre. Riesgo mucho menor.

Rótalo igual cuando reactives el proyecto, en Supabase → Account → Access Tokens. Y como el CRM va a usar una service key propia, este queda solo para el MCP.

---

## Lo que esto NO resuelve

Las 17 credenciales **siguen en el historial de git** aunque las rotes. Rotarlas las vuelve inútiles, que es lo que importa. Pero el historial las conserva, y un amigo de Diego ya clonó los repos.

Borrarlas del historial exige `git filter-repo` y forzar push sobre repos ya clonados — se romperían las copias existentes. **Es una decisión de Dirección, no se ejecuta sola.** Y si todas están rotadas, es en gran medida cosmético.

## La regla que evita la próxima vez

Está en `CARPETA SUPER AGENTES/CLAUDE.md`: las credenciales van por **conector autenticado** o por **variable de entorno**. Nunca literales en archivo.

El conector `mcp__claude_ai_FACEBOOK__*` cubre insights, campañas, conjuntos, creativos, audiencias y catálogos sin un solo token local. Ese es el reemplazo de `AccessMD/`, no un complemento.

Y el escaneo antes de cada commit es parte del procedimiento: en la noche del 16 al 17 detectó un token del pixel de Sweet que se había importado por error a la bóveda desde un `.docx`.

## Verificación al terminar

- [ ] `developers.facebook.com` — la app STARTER APP ya no existe
- [ ] Business Manager — sin usuarios del sistema en Grupal Corp, Fernando Saavedra ni Graduados
- [ ] `ads_get_ad_accounts` devuelve las cuentas de Ferreira, Sweet y Kristus con los tokens nuevos
- [ ] `AccessMD/meta_tokens.md` sin secciones de clientes cerrados y sin ningún token literal
- [ ] `GEMINI_API_KEY` responde desde la variable de entorno
- [ ] Las automatizaciones de GHL de clientes activos siguen corriendo

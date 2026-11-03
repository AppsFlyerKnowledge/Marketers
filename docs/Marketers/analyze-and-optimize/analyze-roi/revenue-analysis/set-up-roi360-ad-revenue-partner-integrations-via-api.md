---
title: >-
  Configura mediante API las integraciones de Partners de ingresos por anuncios
  de ROI360
metadata:
  keywords:
    - ad revenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-10-16T14:53:47Z'
  edited_at: '2026-08-12T11:49:12Z'
  id: 9901416616465
  locale: es
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/es/articles/9901416616465
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo:** Configura integraciones de Partners de ingresos por anuncios para tu cuenta de AppsFlyer o para apps individuales mediante API.

## API de integración de Partners de ingresos por anuncios

La API de integración de Partners de ingresos por anuncios se utiliza para:

* Configura las configuraciones de Partners de ingresos por anuncios a nivel de aplicación para toda tu cuenta.
* Obtén una lista de las configuraciones actuales de partners de ingresos por anuncios para toda tu cuenta.

<div id="set-api" />

<Accordion title="Configurar API">

**Para establecer (configurar) integraciones de partners de ingresos por anuncios mediante API**:

1. <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">Obtén tu token de API V2</Anchor> desde el Dashboard de AppsFlyer. Obligatorio para la autorización de la API. **Nota**: Esto debe hacerlo el administrador de la cuenta.
2. Prepara los parámetros que debes incluir en la solicitud de API, como se describe en la tabla siguiente.
3. Proporciona a tu desarrollador los valores de los parámetros y dile que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">instrucciones de la API de configuración de integraciones</Anchor> en el centro para desarrolladores.  
   La integración entra en vigor a las 00:00 UTC del día siguiente.

#### Parámetros de la solicitud

| Parámetro | Nota |
| --- | --- |
| integraciones | <ul><li>Objeto de nivel superior que debe incluir app\_id, network y products (indicados más abajo).</li><li>Otros campos pueden incluir credentials, event\_name y source\_event.</li></ul> |
| id\_aplicación | El ID de la aplicación que quieres integrar. |
| network | <ul><li>El partner que quieres integrar.</li><li>Para ver una lista de las redes compatibles, consulta la columna network de la <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">tabla de parámetros de la API de partners de ingresos por anuncios</Anchor>.</li></ul> |
| credenciales | <ul><li>Se requieren 1 o más credenciales para la integración de la red.</li><li>Para ver la lista de credenciales, consulta las columnas cred de la <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">tabla de parámetros de la API de partners de ingresos por anuncios</Anchor>.</li></ul> |
| nombre\_del\_evento | <ul><li>Valor predeterminado: af\_ad\_revenue</li><li>También puede ser un nombre de evento personalizado [beta]</li><li>event\_name no es obligatorio si enabled se establece en false.</li></ul> |
| productos | <ul><li>Lista de todos los productos habilitados en una integración, incluidos los parámetros name, enabled y, si corresponde, source\_event (que se indica a continuación).</li><li>Para ver una lista de los productos compatibles por red, consulta la columna de productos de la API masiva de la <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">tabla de parámetros de la API de Partners de ingresos por anuncios</Anchor>.</li></ul> |
| conjunto de anuncios | <ul><li>El nombre del tipo de integración.</li><li>Para ver una lista de nombres de tipos de integración, consulta la columna de productos de la API masiva de la <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">tabla de parámetros de la API de Partners de ingresos por anuncios</Anchor>.</li></ul> |
| habilitada | <ul><li>Posibles valores:<ul><li>Verdadero</li><li>false</li></ul></li><li>Para los tipos de integración a nivel de app, se requiere un evento de origen.</li><li>Si el valor es false, no se requiere ni source\_event ni event\_name.</li></ul> |
| source\_event | <ul><li>Solo es relevante para las integraciones de partners de la API S2S a nivel agregado.</li><li>Para los tipos de integración a nivel de app, si enabled se establece en true, se requiere source\_event.</li></ul> |

</Accordion>

<div id="get-api" />

<Accordion title="API de obtención">

**Para obtener una lista de tus integraciones de partners de ingresos por anuncios a través de la API**:

1. <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">Obtén tu token de API V2</Anchor> desde el Dashboard de AppsFlyer. Obligatorio para la autorización de la API.
2. Dile a tu desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">instrucciones de la API de lista de integraciones</Anchor> en el centro de desarrolladores.

</Accordion>

### Especificaciones y limitaciones

| **Especificación** | **Nota** |
| --- | --- |
| Límite de llamadas | Hasta 1.000 integraciones en una sola llamada. |
| OAuth | No se admiten los partners integrados mediante OAuth (como Google y Facebook). |

<div data-zendesk-anchors="ad-revenue-partner-integration-api=api-de-integraci%C3%B3n-de-partners-de-ingresos-por-anuncios h_01HYD2M7E1PH0ARZRF0P17K80J=api-de-integraci%C3%B3n-de-partners-de-ingresos-por-anuncios h_01HYD2M7E1DX9FAJ0MGN500NZV=set-api request-parameters=par%C3%A1metros-de-la-solicitud h_01HYD2M7E1FYY96HNM6DSHXPQ5=par%C3%A1metros-de-la-solicitud h_01HYD2M7E19XCCFF1NT40VBWH7=get-api specs-and-limitations=especificaciones-y-limitaciones h_01HYD2M7E1X2PEQ616PWMTWCH7=especificaciones-y-limitaciones" />

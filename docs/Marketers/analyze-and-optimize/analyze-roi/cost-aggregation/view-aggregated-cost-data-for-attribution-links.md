---
title: Ver datos de costo agregados de los enlaces de atribución
metadata:
  keywords:
    - eCPI
    - clicks
    - ROI
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-20T10:50:58Z'
  edited_at: '2026-08-12T11:48:20Z'
  id: 360008981698
  locale: es
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/es/articles/360008981698
---
> **En resumen:** Visualización de los datos de costos agregados de cada clic en el anuncio según lo informado por las redes publicitarias.

<div id="basic-cost-reporting" />

## Reportes básicos de costos

Los datos de costos se reportan a AppsFlyer de la siguiente manera:

* Redes publicitarias: cada vez que un usuario hace clic en un anuncio. Ver el costo de la campaña en AppsFlyer ayuda a los anunciantes a medir el ROI y tomar decisiones presupuestarias adecuadas.
  * El costo se informa en el <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">enlace de atribución</Anchor> mediante el modelo de costo por instalación (CPI).
  * Al enviar el enlace de atribución a la red publicitaria, asegúrate de que la red publicitaria <Anchor target="_blank" href="/partners/es/docs/cost-reporting-on-the-attribution-link-for-ad-networks">agregue los parámetros de reportes de costos</Anchor>.
* <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">Opciones avanzadas para la agregación de costos</Anchor>, incluso por API e importación de costos (upload de archivos CSV).

  * Los métodos de agregación de costos admiten los modelos de costos utilizados por el partner además del CPI, incluidos también CPA, CPC y CPM.

<div id="viewing-ad-cost-by-click" />

<Accordion title="Visualización del costo del anuncio por clic">

Los datos de costo por clic se agregan y están disponibles para su visualización en tiempo real (máximo hasta 2 horas después del clic) en los dashboards de AppsFlyer, los reportes de rendimiento y los reportes de raw data.

En el ***dashboard general,** el reporte de rendimiento agregado* contiene datos de costos, clics, impresiones, ROI y eCPI medio.

[![CostReporting.jpg](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)](https://files.readme.io/5d4dbe5dc74fd0915924518f76c63e379f0b072b5d5dbb7a7f92455b83e33a12-17313191631633.jpg)

Los reportes de rendimiento y raw data también están disponibles para <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">descargar</Anchor>.

</Accordion>

<div id="ad-networks-providing-cost-by-click-data" />

<Accordion title="Redes publicitarias que proporcionan datos de costo por clic">

En el caso de las redes publicitarias que reportan el costo por clic, las dimensiones admitidas son las que figuran en el clic.

**Entre las redes publicitarias que reportan sobre el costo por clic se incluyen las siguientes:**

* AdAction
* Aura de Unity
* Blind Ferret
* Chartboost
* Cross Install
* Digital Turbine
* Fyber
* HangMyAds
* ironSource
* Criteo DSP (Manage)
* Mintegral
* TikTok para empresas
* Vungle
* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTMPZ9anfZoFBelK2bsBUoHG9n4YE3WxpXOayDF_wI8vyYClM6_6yXelFCZ3khwhd9Z_5Louxd4VVgx/pub?gid=0&single=true&output=csv">Consulta la lista completa de redes publicitarias que admiten el costo por clic</Anchor>

</Accordion>

<div id="limitations" />

<Accordion title="Limitaciones">

Limitaciones del costo por clic:

* El costo solo se notifica mediante el modelo de costo por instalación (CPI). No se admiten otros modelos, incluyendo CPA, CPC y CPM.
* <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">Las redes de autoreporte</Anchor> (SRN) no reportan el costo por clic.
* Los datos de clics son inmutables. Por lo tanto, una vez que se inicia sesión en AppsFlyer, no se puede cambiar, incluso si hay errores en el reporte de datos.

</Accordion>

<div data-zendesk-anchors="basic-cost-reporting=reportes-b%C3%A1sicos-de-costos h_01HX954Y5X7ZP2VMB5W2XAMCR0=reportes-b%C3%A1sicos-de-costos h_01HX954Y5XTRRQV4JHA5XX1AQ0=viewing-ad-cost-by-click h_01HX954Y5XV8M2R2VDAV34641R=ad-networks-providing-cost-by-click-data h_01HX954Y5X84BM7F8TGQRDPBTS=limitations" />

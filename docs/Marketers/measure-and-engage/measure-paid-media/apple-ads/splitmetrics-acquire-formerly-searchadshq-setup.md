---
title: Configuración de SplitMetrics Acquire (antes SearchAdsHQ)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-15T08:21:04Z'
  edited_at: '2026-09-17T00:25:52Z'
  id: 360002249257
  locale: es
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/es/articles/360002249257
---
> **De un vistazo:** Optimiza las campañas de Apple Ads usando SplitMetrics Acquire. Cuando se configura, AppsFlyer envía postbacks a SplitMetrics Acquire.

<div id="enabling-apple-ads-attribution" />

## Activación de la atribución de Apple Ads

Tanto los anunciantes como las agencias pueden activar la atribución para Apple Ads.

<div id="note" />

> 📘 **Nota:**
>
> Si el anunciante o la agencia desactiva la atribución para Apple Ads, se detiene la atribución de esta aplicación, incluido el envío de postbacks a los partners de marketing de Apple Ads.

* **Anunciantes**: sigan las instrucciones que aparecen a continuación para activar la atribución para Apple Ads.
* **Agencias**: <Anchor target="_blank" href="/marketers/es/docs/apple-ads-integration-setup#agency-setup">sigan estas instrucciones</Anchor> para activar la atribución para Apple Ads.

<div id="setting-up-splitmetrics-acquire-on-appsflyer" />

## Configuración de SplitMetrics Acquire en AppsFlyer

<div id="getting-required-information-from-splitmetrics-acquire" />

### Obtención de la información necesaria de SplitMetrics Acquire

Antes de empezar a configurar SplitMetrics Acquire en AppsFlyer, obtén tu **client\_id** y tu **Apple Ads campaign group ID**.

* Para client\_id, ve al Dashboard de SplitMetrics Acquire y haz clic en **Integrations** > **AppsFlyer**. En la ventana emergente que se abre, copia el ID.
* Para el Apple  Ads Campaign Group ID: **en tu dashboard de Apple Ads,** obtén el parámetro Apple Ads Campaign Group ID relacionado con SplitMetrics Acquire. Utiliza la captura de pantalla a seguie como guía para localizar el ID.  ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)

<div id="setting-up-campaigns-on-appsflyer" />

### Configuración de campañas en AppsFlyer

**Para configurar SplitMetrics Acquire:**

1. **En AppsFlyer, configura SplitMetrics Acquire:**
   1. En AppsFlyer, en el menú lateral, selecciona **Collaboration** > **Partner Integrations** > **Active Integrations.**
   2. Busca SplitMetrics Acquire.  
      Aparece la lista de partners de marketing.
   3. Selecciona SplitMetrics Acquire.
   4. Activa **Activar partner.**
   5. Introduce el ID de cliente en el campo **client\_id**.
   6. Introduce el **Apple Ads Campaign ID** de SplitMetrics Acquire que recuperaste en el paso anterior. Ingresa solo los dígitos (números).
   7. Haga clic en **Guardar**.
2. Si quieres registrar atribuciones para Apple Ads, activa también la **integración de Apple Ads:**
   1. En AppsFlyer, en el menú lateral, selecciona **Collaboration** > **Partner Integrations** > **Partner Marketplace**.
   2. Busca y selecciona al partner. Serás dirigido a la página de configuración del partner.
   3. En la pestaña **Integración**, selecciona **Activar partner**.
   4. Haz clic en **Guardar integración**.

<div id="configuring-in-app-event-postbacks" />

#### Configuración de postbacks de eventos in-app

**Para configurar el postback que se debe enviar a SplitMetrics Acquire cuando se produzcan eventos in-app:**

1. Introduce el client\_id.
2. Activa **postback de eventos in-app**.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

   

| Nombre de parámetro | Nota |
| --- | --- |
| Nombre de evento del SDK | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor. **Consejo:** Si no encuentras el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| Enviar ingresos | Selecciona una de las siguientes opciones: Sin valores y sin ingresos, Valores & sin ingresos o Valores & ingresos. |

5. Haz clic en **Guardar integración**.

<div data-zendesk-anchors="enabling-apple-search-ads-attribution=activaci%C3%B3n-de-la-atribuci%C3%B3n-de-apple-ads h_01HBB5JWBAZMD5BHPGQYHYQY0Q=activaci%C3%B3n-de-la-atribuci%C3%B3n-de-apple-ads h_01HBB5JWBA612TQV90K56H319J=nota setting-up-searchadshq-on-appsflyer=configuraci%C3%B3n-de-splitmetrics-acquire-en-appsflyer h_01HBB5JWBA6QPV3ZN0FCBK0BHR=configuraci%C3%B3n-de-splitmetrics-acquire-en-appsflyer getting-required-information-from-searchadshq=obtenci%C3%B3n-de-la-informaci%C3%B3n-necesaria-de-splitmetrics-acquire h_01HBB5JWBA6CGAAQAA9DZ4XMNS=obtenci%C3%B3n-de-la-informaci%C3%B3n-necesaria-de-splitmetrics-acquire setting-up-campaigns-on-appsflyer=configuraci%C3%B3n-de-campa%C3%B1as-en-appsflyer h_01HBB5JWBAMHKBAMQD4TTQSZ0H=configuraci%C3%B3n-de-campa%C3%B1as-en-appsflyer configuring-inapp-event-postbacks=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HBB5JWBBHMKT3Z9JKEQJAZZ7=configuraci%C3%B3n-de-postbacks-de-eventos-in-app" />

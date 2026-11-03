---
title: 'Partner de marketing de Apple Ads: configuración de la campaña'
metadata:
  keywords:
    - Apple Search Ads
    - Advertisers
    - Bidalgo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-26T10:33:54Z'
  edited_at: '2026-09-17T00:25:47Z'
  id: 360001340429
  locale: es
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/es/articles/360001340429
---
> **En resumen:** Optimiza las campañas de Apple Ads con Bidalgo. Una vez configurado, AppsFlyer envía postbacks a Bidalgo.

## Habilitación del envío de postbacks a Bidalgo (partner de marketing de Apple Ads)

> 📘 **Nota:**
>
> Si el anunciante o la agencia desactiva la atribución de Apple Ads, se detiene la atribución de esta app, incluido el envío de postbacks a partners de marketing de Apple Ads.

Tanto los anunciantes como las agencias pueden habilitar la atribución de Apple Ads.

* **Anunciantes:** sigan las instrucciones que aparecen a continuación para habilitar la atribución de Apple Ads.
* **Agencias:** <Anchor target="_blank" href="/marketers/es/docs/apple-ads-integration-setup#agency-setup">sigan estas instrucciones</Anchor> para habilitar la atribución de Apple Ads.

### Configuración de Bidalgo

**Para configurar Bidalgo:**

1. Si es necesario, activa la **integración de Apple Search Ads:**
   1. En AppsFlyer, desde el menú lateral, selecciona la pestaña **Collaboration** > **Partner Integrations > Partner Marketplace** .
   2. Busca y selecciona al partner. Serás dirigido a la página de configuración del partner.
   3. En la pestaña **Integración**, selecciona **Activar partner**.
   4. Haz clic en **Guardar integración**.
2. **En tu dashboard de Apple Ads**: obtén el parámetro Apple Ads Campaign Group ID relacionado con Bidalgo. Utiliza la captura de pantalla a seguie como guía para localizar el ID.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **En AppsFlyer, configura Bidalgo:**
   1. En AppsFlyer, desde el menú lateral, selecciona **Colaboración** > **Integración activa**.
   2. Busca Bidalgo - Apple Ads partner de marketing.  
      Aparece la lista de partners de marketing.
   3. Selecciona Bidalgo - Apple Ads partner de marketing.
   4. Activa **Activar partner.**
   5. Introduce el **Apple Ads Campaign ID** de Bidalgo que obtuviste en el paso anterior. Ingresa solo los dígitos (números).
   6. Haga clic en **Guardar**.

### Postbacks predeterminados

Las instalaciones y los re-engagements se envían automáticamente cuando se activa el partner.

### Configuración de postbacks de eventos in-app

**Para configurar postbacks de eventos in-app:**

1. Activa **In-app events postback**.
2. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
3. Completa los siguientes parámetros:

   

| Nombre de parámetro | Nota |
| --- | --- |
| Nombre de evento del SDK | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor. **Consejo:** Si no encuentras el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| Enviar ingresos | Selecciona una de las siguientes opciones: Sin valores y sin ingresos, Valores y sin ingresos, o Valores e ingresos. |

4. Haz clic en **Guardar integración**.

<div data-zendesk-anchors="enabling-sending-postbacks-to-bidalgo-apple-search-ads-marketing-partner=habilitaci%C3%B3n-del-env%C3%ADo-de-postbacks-a-bidalgo-partner-de-marketing-de-apple-ads h_01HKW0AZ05126SWNF374821AAH=habilitaci%C3%B3n-del-env%C3%ADo-de-postbacks-a-bidalgo-partner-de-marketing-de-apple-ads h_01HKW0AZ05SXCVY0M3M7R07KG6=nota configuring-bidalgo=configuraci%C3%B3n-de-bidalgo h_01HKW0AZ06QFMYPJF95XQRAK99=configuraci%C3%B3n-de-bidalgo default-postbacks=postbacks-predeterminados h_01HKW0AZ06SPXE8K9JQN60B8T2=postbacks-predeterminados configuring-inapp-events-postbacks=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HKW0AZ06F0169D59AWKQJN87=configuraci%C3%B3n-de-postbacks-de-eventos-in-app" />

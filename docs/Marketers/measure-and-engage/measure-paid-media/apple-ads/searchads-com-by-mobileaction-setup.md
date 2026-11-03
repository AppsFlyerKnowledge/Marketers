---
title: Configuración de SearchAds.com (de MobileAction)
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-06-20T13:34:38Z'
  edited_at: '2026-09-17T00:25:49Z'
  id: 4402846897041
  locale: es
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/es/articles/4402846897041
---
> **En resumen:** Optimiza las campañas de Apple Ads usando SearchAds.com de MobileAction. Una vez configurado, AppsFlyer envía los postbacks a SearchAds.com.

## Activación de la atribución de Apple Ads

Para poder enviar postbacks a SearchAds.com, primero debes activar la atribución de Apple Ads. Esto puede hacerlo un anunciante o una agencia.

> 📘 **Nota:**
>
> Si el anunciante o la agencia desactiva la atribución de Apple Ads, se detienen los postbacks de SearchAds.com y de otros Apple Ads Marketing Partners.

* **Anunciantes**: sigue las instrucciones que aparecen abajo para activar la atribución de Apple Ads.
* **Agencias**: <Anchor target="_blank" href="/marketers/es/docs/apple-ads-integration-setup#agency-setup">sigue estas instrucciones</Anchor> para activar la atribución de Apple Ads.

## Configuración de SearchAds.com en AppsFlyer

### Obtención de la información necesaria de SearchAds.com

Antes de empezar a configurar SearchAds.com en AppsFlyer, obtén tu **api\_key** y el **ID del grupo de campañas de Apple Ads**.

* Para obtener la api\_key, ve a tu dashboard de SearchAds.com y haz clic en **Integrations** > **AppsFlyer**. En la ventana emergente que se abre, copia el ID. [![Clave API de SearchAds.com](https://files.readme.io/1acc061c44fe616a4485b576251d1ad64cb05607f4727bbd21b0bf6871720b40-4402869972241.png)](https://files.readme.io/1acc061c44fe616a4485b576251d1ad64cb05607f4727bbd21b0bf6871720b40-4402869972241.png)
* Para el ID del grupo de campañas de Apple Ads: en tu **dashboard de Apple Ads,** obtén el ID del grupo de campañas de Apple Ads correspondiente:

  ![apple-search-ads-campaign-group-id.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)

### Configuración de campañas en AppsFlyer

**Para configurar SearchAds.com:**

1. Si es necesario, activa la **integración de Apple Search Ads:**
   1. En AppsFlyer, en el menú lateral, selecciona **Collaborate** > **Partner Integrations** > **Partner Marketplace**.
   2. Busca y selecciona al partner. Serás dirigido a la página de configuración del partner.
   3. En la pestaña **Integración**, selecciona **Activar partner**.
   4. Haz clic en **Guardar integración**.
2. **En AppsFlyer, configura SearchAds.com:**
   1. En AppsFlyer, en el menú lateral, selecciona **Collaborate** > **Partner Integrations** > **Active Integrations**.
   2. Busca SearchAds.com (de MobileAction).  
      Aparece la lista de partners de marketing.
   3. Selecciona SearchAds.com (de MobileAction).
   4. Activa **Activar partner.**
   5. Introduce la clave API en el campo **api\_key**.
   6. Introduce el **ID de campaña de Apple Ads** de SearchAds.com. Ingresa solo los dígitos (números).
   7. Haga clic en **Guardar**.

#### Configuración de postbacks de eventos in-app

**Para configurar el postback que debe enviarse a SearchAds.com cuando se produzcan eventos in-app:**

1. Introduce el **api\_key**.
2. Activa el **postback de eventos in-app**.
3. Selecciona **Enviar todos los eventos**.
4. En **Enviar ingresos**, selecciona **Valores&Ingresos**.
5. Haz clic en **Guardar integración**.

<div data-zendesk-anchors="enabling-apple-search-ads-attribution=activaci%C3%B3n-de-la-atribuci%C3%B3n-de-apple-ads h_01HKW0B2AZ40F0N9A7YYGTHCE0=activaci%C3%B3n-de-la-atribuci%C3%B3n-de-apple-ads h_01HKW0B2AZ411647BAS75M5BG6=nota setting-up-searchadscom-in-appsflyer=configuraci%C3%B3n-de-searchadscom-en-appsflyer h_01HKW0B2AZWC9AQBAYDWFPAKQN=configuraci%C3%B3n-de-searchadscom-en-appsflyer getting-required-information-from-searchadscom=obtenci%C3%B3n-de-la-informaci%C3%B3n-necesaria-de-searchadscom h_01HKW0B2AZ49R66CMJ747M485M=obtenci%C3%B3n-de-la-informaci%C3%B3n-necesaria-de-searchadscom setting-up-campaigns-in-appsflyer=configuraci%C3%B3n-de-campa%C3%B1as-en-appsflyer h_01HKW0B2AZ419YS071HNXHPZXY=configuraci%C3%B3n-de-campa%C3%B1as-en-appsflyer configuring-inapp-event-postbacks=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HKW0B2AZ4GHJE5SQHB3ZSZ8D=configuraci%C3%B3n-de-postbacks-de-eventos-in-app" />

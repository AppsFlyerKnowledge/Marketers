---
title: 'Google Ads (AdWords): re-engagement'
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
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2026-07-16T10:19:47Z'
  id: 4417296925073
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/4417296925073
---
> **En resumen:** Mide las campañas de retargeting de Google Ads.

## Campañas de retargeting de Google Ads

Con AppsFlyer, puedes medir los resultados de las **campañas de aplicaciones para interacción de Google Ads**.  
En AppsFlyer, estas campañas se denominan campañas de <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">retargeting</Anchor>. AppsFlyer admite la obtención de datos de costos, clics e impresiones para campañas de retargeting. Esta integración te permite ver y medir tu gasto publicitario en Google Ads, y luego calcular el eCPI y el ROI de tus campañas de Google Ads.

Las campañas de retargeting están dirigidas a usuarios que instalaron tu app anteriormente.

* Las interacciones de retargeting realizadas por usuarios que todavía tienen instalada tu app se denominan **re-engagements**. Normalmente, esto da lugar al deep linking de los usuarios.
* Las interacciones de retargeting realizadas por usuarios que ya no tienen instalada tu app se denominan **reinstalaciones** o **reatribuciones**.

Para más información, consulta la <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">documentación de soporte de Google Ads para engagement</Anchor>.

## Configuración de las campañas de aplicaciones para engagement de Google Ads

Antes de comenzar, revisa las <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">instrucciones de Google sobre cómo compartir un enlace con otras cuentas de Google Ads</Anchor> para asegurarte de que tus campañas de engagement se midan correctamente mediante el ID de enlace existente.

Para medir las campañas de aplicaciones para engagement de Google Ads, sigue estos tres pasos:

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="Activar el retargeting en la configuración de la app">

Para habilitar las campañas de retargeting de cualquier fuente de medios, debes activarlo a nivel de app. Si esta es la primera campaña de retargeting de tu app, haz lo siguiente:

1. En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Configuración de la app**.
2. Desplázate hasta la parte inferior.
3. Activa la **atribución de re-engagement**.

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="Activa el retargeting de Google Ads en AppsFlyer">

* Sigue las <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">instrucciones</Anchor> para configurar Google Ads en AppsFlyer.

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="Importar conversiones de session_start en Google Ads">

Para registrar las conversiones de las campañas de re-engagement en **Google Ads**, debes importar el evento session\_start en Google Ads.

Este evento aparece en Google Ads si al menos un usuario abre la app después de activar el retargeting en AppsFlyer para Google Ads. Para asegurarte de que todo funciona correctamente, abre la app tú mismo después de activar el retargeting.

Para más información sobre cómo importar conversiones en Google Ads, consulta <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aquí</Anchor>.

> 📘 **Nota**
>
> A diferencia de los demás eventos, session\_start puede ser reclamado por la API de Google Ads, aunque no importes session\_start desde AppsFlyer a Google Ads.
> Sin embargo, en ese caso, estas conversiones seguirán atribuyéndose en AppsFlyer. Esto **genera una diferencia significativa entre tus datos en AppsFlyer y en Google Ads**. Además, esto **impide que Google Ads optimice** la segmentación de usuarios de tu campaña.

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="Configuración de deep linking para las campañas de aplicaciones para engagement">

Las campañas de aplicaciones para engagement de Google Ads requieren que <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">utilices deep links para las campañas de re-engagement</Anchor>. No se pueden utilizar soluciones de deep linking de terceros debido a una incompatibilidad de dominios. Esto incluye OneLink de AppsFlyer. Utiliza tus propios <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">App Links, Universal Links o esquemas URI personalizados desarrollados internamente</Anchor>.

No es necesario añadir parámetros adicionales al deep link (is\_retargeting=true y pid=adwords no son obligatorios).

</Accordion>

## Campañas de remarketing dinámico y compras

AppsFlyer admite el remarketing dinámico para apps y las campañas de compras. La plataforma de AppsFlyer las trata como cualquier otra campaña de re-engagement.

* Para más información sobre el remarketing dinámico para apps, haz clic <Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">aquí</Anchor>.
* Para más información sobre las campañas de compras, haz clic <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">aquí</Anchor>.
* Para más información sobre Google Ads para engagement, haz clic <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">aquí</Anchor>.

### Compatibilidad con campañas que no son de apps (Demand Gen y SEM)

AppsFlyer solo admite la medición de re-engagement para las campañas de Google que no son de apps, entre ellas:

* Campañas de Demand Gen
* Campañas de Search Engine Marketing (SEM)

Estas campañas funcionan **desde el primer momento** con AppsFlyer y no requieren:

* Tracking paralelo
* implementación de Smart Script

**Limitaciones:**

* Las **instalaciones** procedentes de campañas de Demand Gen o SEM no se atribuyen en ninguna plataforma.

**Opt-out:** Actualmente, Google no admite activar ni desactivar la medición de campañas que no son de apps (a diferencia de plataformas como TikTok o Meta).

> 📄 **Consulta también**
>
> * Para consultar las consideraciones relacionadas con iOS 14, consulta <Anchor target="_blank" href="/marketers/es/docs/get-skan-postback-data-from-google-ads">la interoperabilidad de Google Ads SKAdNetwork con AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-retargeting-campaigns=campa%C3%B1as-de-retargeting-de-google-ads h_01HDP34BWZFG09ABN5NQB6EY32=campa%C3%B1as-de-retargeting-de-google-ads setting-up-google-ads-app-campaigns-for-engagement=configuraci%C3%B3n-de-las-campa%C3%B1as-de-aplicaciones-para-engagement-de-google-ads h_01HDP34BWZXXNZDE0SR4MXBC9V=configuraci%C3%B3n-de-las-campa%C3%B1as-de-aplicaciones-para-engagement-de-google-ads h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=nota h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement dynamic-remarketing-and-shopping-campaigns=campa%C3%B1as-de-remarketing-din%C3%A1mico-y-compras h_01HDP34BWZ990SD3B1C5DZRESK=campa%C3%B1as-de-remarketing-din%C3%A1mico-y-compras h_google-non-app-campaign-support=compatibilidad-con-campa%C3%B1as-que-no-son-de-apps-demand-gen-y-sem support-for-nonapp-campaigns-demand-gen-and-sem=compatibilidad-con-campa%C3%B1as-que-no-son-de-apps-demand-gen-y-sem h_01HDP2XBSEJVQ5G0MD0V5R05CM=consulta-tambi%C3%A9n" />

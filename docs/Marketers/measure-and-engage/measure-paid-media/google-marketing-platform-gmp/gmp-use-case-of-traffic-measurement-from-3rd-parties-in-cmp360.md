---
title: Caso de uso de GMP de medición de tráfico de terceros en CMP360
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
  created_at: '2021-03-03T12:42:31Z'
  edited_at: '2026-10-08T00:14:48Z'
  id: 360018228758
  locale: es
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/es/articles/360018228758
---
> **En resumen:** Compra tráfico de fuentes de medios de terceros en CM360 y mide las conversiones de aplicaciones móviles originadas en esta fuente tanto en AppsFlyer (atribuida a la fuente de medios de terceros) como en CM360.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

<div id="measurement-of-cm360-with-non-dv360-third-party-media-sources" />

## Medición de CM360 con fuentes de medios de terceros que no son DV360

Google Marketing Platform (GMP) reúne tu publicidad y análisis para ayudarte a establecer conexiones de calidad con los clientes, obtener insights más completos y obtener mejores resultados de marketing.

En el contexto de AppsFlyer, la integración SRN estándar de DV360 (dv360\_int) con GMP permite la fácil atribución de campañas DV360 **administradas en CM360**, sin necesidad de enlaces de atribución. AppsFlyer atribuye instalaciones y re-engagements a DV360 a través de las reclamaciones de SRN de DV360 mediante la integración.

<div id="note" />

> 📘 **Nota**
>
> * AppsFlyer atribuye las campañas de DV360 administradas en CM360 a través de la integración SRN estándar de DV360, sin necesidad de enlaces de atribución. Las instalaciones y los re-engagements se atribuyen a DV360 a través de reclamos SRN de DV360 mediante la integración. Si ejecutas campañas de DV360 a través de CM360, consulta la <Anchor target="_blank" href="/marketers/es/docs/google-marketing-platform-display-video-360-dv360-integration">guía de integración</Anchor>.
> * Si la fuente de medios de terceros es una SRN, AppsFlyer recomienda no usar la integración descrita en este artículo para evitar conflictos cuando las conversiones del mismo partner se reportan a través de dos integraciones diferentes. Por ejemplo, si la <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup">integración SRN de Meta Ads</Anchor> está habilitada en AppsFlyer, pero CM360 también se utiliza para reportar sobre el tráfico de Meta Ads (facebook\_int) utilizando el método descrito en este artículo, tanto Meta Ads como CM360 pueden reportar las conversiones, y CM360 captura algunas de las conversiones que habrían sido reclamadas por la integración principal de Meta Ads.

<div id="measuring-third-party-traffic-running-via-cm360" />

### Medición del tráfico de terceros que se ejecuta a través de CM360

Se recomiendan los siguientes pasos para medir las fuentes de medios de terceros administradas a través de CM360, tanto en AppsFlyer como en CM360:

<div id="step-1-integrate-the-third-party-media-source-and-gmp-with-appsflyer" />

#### Paso 1: Integra la fuente de medios de terceros y GMP con AppsFlyer

Para garantizar la atribución por parte de AppsFlyer:

* Asegúrate de que la fuente de medios de terceros esté integrada y activada, ya que recibe atribución en lugar de CM360. La activación de GMP (dv360\_int) solo es necesaria para garantizar que los datos se envíen a CM360.
* Si la fuente de medios de terceros no está integrada con AppsFlyer, debe manejarse como una fuente de medios personalizada o propia. En este caso, implementa un enlace de atribución con cualquier valor de PID (fuente de medios).

<div id="note-1" />

> 📘 **Nota**
>
> Para la atribución de agencia: AppsFlyer requiere el nombre de la agencia para la atribución de instalaciones. Inclúyelo utilizando el parámetro `af_prt` en el enlace de atribución o a través del referente en la URL.

<div id="step-2-create-the-required-attribution-links" />

#### Paso 2: Crea los enlaces de atribución necesarios

1. <Anchor target="_blank" href="https://support.google.com/campaignmanager/answer/3040965?hl=en&ref_topic=2826011">Crear un "anuncio de seguimiento" de CM360</Anchor>
2. Crea un enlace de atribución en AppsFlyer:
   * El enlace de atribución debe contener la fuente real de medios que pretendes reportar, la cual debe ser una fuente de medios de terceros, no GMP. Por ejemplo, si la fuente de medios de terceros es Rocketfuel, usa `pid=rocketfuel_int` y no `pid=dv360_int`. <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">Saber más</Anchor>.
   * Si tu objetivo es **volver a interactuar con los usuarios existentes abriendo la aplicación** cuando hacen clic en el enlace del anuncio (en lugar de redirigirlos a la tienda de aplicaciones), **usa el método del esquema URI** para el Deep Linking. Para ello, debes configurar el enlace de CM360 con lo siguiente:
     * El parámetro `af_dp` configurado con el esquema URI de tu aplicación.
     * El parámetro `af_force_deeplink=true` para forzar explícitamente el comportamiento de deep linking.
3. Agrega el enlace de atribución de AppsFlyer al enlace de CM360:

   <Tabs>
   <Tab title="Android">

   ```http
   https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
   dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
   ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
   &c=campaign_name&advertising_id=13******-****-****-****-54**********
   ```

   </Tab>

   <Tab title="iOS">

   ```http
   https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
   dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
   ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
   &c=campaign_name&idfa=13******-****-****-****-54**********
   ```

   </Tab>
   </Tabs>

   * Consulta más información sobre la <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters?">estructura y los parámetros de los enlaces de Atribución para iOS y Android</Anchor>
   * Consulta más información sobre la <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">estructura y los parámetros de los enlaces de Atribución de CTV, consolas y PC</Anchor>

<div id="step-3-set-in-app-event-postbacks" />

#### Paso 3: Postbacks de eventos in-app

Para garantizar que CM360 reciba postbacks de eventos originados en estas campañas, se recomienda configurar postbacks de eventos in-app en dv360\_int como "Todas las fuentes de medios, incluidas las orgánicas".

<div id="using-the-attribution-link" />

### Cómo usar el enlace de atribución

Una vez que tengas el enlace de atribución, asegúrate de que se utilice mientras publicas anuncios en tu fuente de medios de terceros prevista. Cuando se produce una instalación, AppsFlyer atribuye la instalación a la fuente de medios de terceros seleccionada y notifica al partner mediante postbacks. AppsFlyer informa a CM360 sobre la instalación o cualquier evento in-app posterior a través de la integración de DV360, siempre que esté activo.

El resultado final es una instalación o evento in-app que se atribuye a la fuente de medios y también se registra en DCM360.

<div data-zendesk-anchors="google-marketing-platform-cm360-nondv360-thirdparty-media-source-for-click-and-impression-measurement=medici%C3%B3n-de-cm360-con-fuentes-de-medios-de-terceros-que-no-son-dv360 h_01HN0GE07NDVK8MWQEYMKDFAE6=medici%C3%B3n-de-cm360-con-fuentes-de-medios-de-terceros-que-no-son-dv360 h_01HVXSGQZP305D7EF1SY56F26B=nota measuring-thirdparty-traffic-running-via-cm360=medici%C3%B3n-del-tr%C3%A1fico-de-terceros-que-se-ejecuta-a-trav%C3%A9s-de-cm360 h_01HVK04VANY30B8EX94F9WPBGB=medici%C3%B3n-del-tr%C3%A1fico-de-terceros-que-se-ejecuta-a-trav%C3%A9s-de-cm360 step-1-integrate-the-thirdparty-media-source-and-gmp-with-appsflyer=paso-1-integra-la-fuente-de-medios-de-terceros-y-gmp-con-appsflyer h_01HYBRGBH10N9H0WT45NQ65C6R=paso-1-integra-la-fuente-de-medios-de-terceros-y-gmp-con-appsflyer h_01HYBB2SJEYE0WV2PRY5SK51GB=nota-1 step-2-create-the-required-attribution-links=paso-2-crea-los-enlaces-de-atribuci%C3%B3n-necesarios h_01HYBA8YS1CWHN3APE5SV506TC=paso-2-crea-los-enlaces-de-atribuci%C3%B3n-necesarios 01JXQGQPDB66E3HWWEVPXXB8BZ=paso-3-postbacks-de-eventos-in-app using-the-attribution-link=c%C3%B3mo-usar-el-enlace-de-atribuci%C3%B3n h_01HN0GE07N10T92EKR5B2482KB=c%C3%B3mo-usar-el-enlace-de-atribuci%C3%B3n" />

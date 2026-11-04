---
title: >-
  Aplicar la solución de la Ley de Protección de la Información Personal (PIPL)
  de China
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-05-10T08:59:00Z'
  edited_at: '2026-08-12T12:18:37Z'
  id: 6031419375377
  locale: es
  section: China market
  section_id: 6552042145425
  url: https://support.appsflyer.com/hc/es/articles/6031419375377
---
> **De un vistazo:** Mejora la flexibilidad al medir con AppsFlyer y cumplir con la PIPL.

<div id="background" />

## Antecedentes

A finales de 2021, China aprobó la Ley de Protección de la Información Personal (PIPL), que regula la recopilación, el uso y la transferencia de los datos personales de los usuarios. Para ofrecer a los clientes más flexibilidad al usar AppsFlyer y dar soporte al cumplimiento de la PIPL, sigue las instrucciones paso a paso que se describen en este artículo.  
La solución PIPL de AppsFlyer se basa en 3 principios:

* Evita que el SDK recopile los ID de dispositivo.
* Enmascara y aplica hash a las IP de los eventos del SDK, los eventos S2S y los clics e impresiones.
* Permite auditar todos los eventos de la app en un servidor de retransmisión en China.

<div id="apply-pipl-solution-in-appsflyer" />

## Aplicar la solución PIPL en AppsFlyer

En la siguiente sección se describen las acciones que debes realizar para aplicar la solución PIPL de AppsFlyer.

**Para aplicar la solución PIPL:**

1. Deja de recopilar ID de dispositivos mediante el SDK. Asegúrate de no enviar a AppsFlyer los ID de dispositivo ni para los engagements ni para los eventos.
   * Para Android:
     * Configura `setDisableAdvertisingIdentifiers` en true
     * Configura <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">`setCollectIMEI`</Anchor> en false
     * Configura <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">`setCollectAndroidID`</Anchor> en false
   * Para iOS:
     * Configura <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier">`disableAdvertisingIdentifier`</Anchor> en true
     * Configura <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableidfvcollection">`disableIDFVCollection`</Anchor> en true

   Ten en cuenta que configurar estos métodos afecta a la recopilación de identificadores no solo en China. Para desactivar los identificadores específicamente para el mercado chino, debes implementar una lógica personalizada.
2. Enmascara y aplica hash a los clics y las impresiones usando dominios chinos específicos para pasar estos eventos a AppsFlyer.
   * Usa los siguientes dominios chinos para OneLink y los enlaces de atribución:
     * Para clics de una sola plataforma: **hclicks.aflink.com**; no uses la firma de clics. Asegúrate de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/click-signing-config-excluded-apps-add">excluir la app de la firma de clics</Anchor>.
     * Para impresiones de una sola plataforma: **himpressions.aflink.com**
     * Para clics de OneLink: **`{subdomain}`.onelnk.com**
   * Envía a tu CSM una lista de los ID de aplicaciones relevantes y los subdominios de OneLink.
   * Si usas banners inteligentes:
     * <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">Envía a AppsFlyer la clave del sitio web.</Anchor>
     * Usa solo `{subdomain}`.onelnk.com.
     * ¡Atención! Como PIPL exige el enmascaramiento y el hashing de las direcciones IP, los banners inteligentes basados en reglas de geolocalización no funcionarán como se espera.
3. Enmascara y aplica hashing a los eventos de SDK y S2S, y transfiérelos a través de un servidor de retransmisión en China
   * **Eventos de SDK:**  
     Configura el dominio de los eventos de SDK en **hevents.appsflyer-cn.com**. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">Instrucciones para Android</Anchor>. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost">instrucciones para iOS</Anchor>.  
     El uso de este dominio garantiza que la IP de todos los eventos de SDK se enmascare y se aplique hashing.
   * **Eventos S2S:**  
     Para los eventos S2S, usa el dominio `api2.hevents.appsflyer-cn.com` para enmascarar y aplicar hashing a los eventos de IP de la siguiente manera:
     * La IP debe convertirse en binario y, a continuación, deben enmascararse los 2 últimos dígitos.
     * La IP binaria enmascarada debe convertirse en texto y, después, aplicarse hashing con el algoritmo sha256.

<div id="solution-limitations" />

## Limitaciones de la solución

En esta sección se describen determinadas limitaciones que impone la solución PIPL.

* La solución S2S para la API de OneLink para la creación de enlaces cortos no es compatible.
* Todos los ID de dispositivo, para todos los engagement, deben someterse a hashing.

<div data-zendesk-anchors="background=antecedentes h_01HQ5Y1W7M46BBJGEZZ5VEYW3K=antecedentes apply-pipl-solution-in-appsflyer=aplicar-la-soluci%C3%B3n-pipl-en-appsflyer h_01HQ5Y1W7MRYYGJWJNWY7ZSY9S=aplicar-la-soluci%C3%B3n-pipl-en-appsflyer solution-limitations=limitaciones-de-la-soluci%C3%B3n h_01HQ5Y1W7M39XRY607H4G7X0X4=limitaciones-de-la-soluci%C3%B3n" />

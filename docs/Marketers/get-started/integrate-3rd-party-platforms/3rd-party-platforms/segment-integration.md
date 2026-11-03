---
title: Integración de Segment
metadata:
  keywords:
    - Integration
    - segment IO
    - Advertisers
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
  created_at: '2016-06-30T07:54:38Z'
  edited_at: '2026-08-12T11:59:33Z'
  id: 210041606
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/210041606
---
> **En resumen:** Envía tus datos de análisis de Segment a AppsFlyer.

## Introducción

Segment facilita el envío de tus datos a AppsFlyer. Una vez que hayas registrado tus datos a través de las bibliotecas de código abierto de Segment, los datos se traducen y se envían a AppsFlyer en el formato adecuado. AppsFlyer ayuda a los marketers a identificar el targeting, optimizar la inversión publicitaria y aumentar el ROI.

## Integración de Segment con AppsFlyer

Seguir <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/">esta guía de Segment</Anchor> para aprender a integrar Segment con AppsFlyer.

## Preguntas Frecuentes

<div id="how-can-i-integrate-segment-with-appsflyer" />

<Accordion title="¿Cómo puedo integrar Segment con AppsFlyer?">

Para integrar Segment con AppsFlyer, sigue estos pasos:

* <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">Configurar el panel de control de Segment</Anchor> para conectarse a AppsFlyer
* Implementa [el wrapper del SDK de Segment](/docs/segment-integration#how-does-the-sdk-wrapper-work) en tu aplicación:
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-swift-appsflyer">Native iOS</Anchor>
  * <Anchor target="_blank" href="https://github.com/segment-integrations/analytics-kotlin-appsflyer">Native Android</Anchor>

</Accordion>

<div id="what-sdks-do-i-need-to-add-to-my-app" />

<Accordion title="¿Qué SDK debo agregar a mi aplicación?">

Solo tienes que agregar el wrapper del SDK de Segment. Cuando agregas la dependencia wrapper del SDK de Segment, el proceso de creación de apps agrega automáticamente el SDK de Segment y el SDK de AppsFlyer a tu app.

</Accordion>

<div id="how-does-the-sdk-wrapper-work" />

<Accordion title="¿Cómo funciona el wrapper del SDK?">

El wrapper del SDK de Segment conecta el SDK de Segment y el SDK de AppsFlyer.

Cuando usas el wraper del SDK de Segment para llamar a los métodos de Segment y así registrar instalaciones y eventos in-app, el wrapper del SDK llama a los métodos de Segment y AppsFlyer.

Esto te ahorra tiempo y esfuerzo y requiere menos codificación.

> ❗️ **Advertencia**
>
> Advertencia- **NO UTILIZAR** métodos tanto del wrapper del SDK de Segment como del SDK de AppsFlyer. Si lo hace, podría producirse errores y discrepancias en los datos.
>
> **Utiliza solo los métodos del wrapper del SDK de Segment.**

</Accordion>

<div id="is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk" />

<Accordion title="¿Hay alguna diferencia en la funcionalidad entre el wrapper del SDK de Segment y el SDK de AppsFlyer?">

No, no hay cambios en la funcionalidad. Todas las funciones del SDK de AppsFlyer están disponibles en el wrapper del SDK de Segment.

</Accordion>

<div id="i-dont-see-inapp-event-data-in-the-appsflyer-dashboard" />

<Accordion title="No veo los datos de eventos in-app en el panel de control de AppsFlyer">

* Asegúrate de seguir las instrucciones para implementar el método track en el wrapper del SDK de Segment:
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyer-Segment-Integration#adding_events">Android</Anchor>
  * <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/segment-appsflyer-ios/blob/master/examples/SwiftPodsSample/SwiftPodsSample/ViewController.swift">apps de iOS,</Anchor>
* Asegúrate de <Anchor target="_blank" href="https://segment.com/docs/destinations/appsflyer/#getting-started">especificar la clave de desarrollo</Anchor> al integrar AppsFlyer en el panel de control de Segment.

</Accordion>

<div id="install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match" />

<Accordion title="Los datos de instalación y eventos in-app en Segment y AppsFlyer no coinciden">

Asegúrate de usar solo el wrapper de SDK de Segment. No combines el wrapper de SDK de Segment con el SDK de AppsFlyer. Ver [aquí](/docs/segment-integration#how-does-the-sdk-wrapper-work) para más información.

[Las preguntas frecuentes anteriores](/docs/segment-integration#i-dont-see-inapp-event-data-in-the-appsflyer-dashboard) también especifica las razones por las que los datos podrían no coincidir entre Segment y AppsFlyer.

</Accordion>

<div id="im-getting-a-validation-error-when-testing-events-in-segment" />

<Accordion title="Recibo un error de validación al probar eventos en Segment">

Al probar eventos con el método ***Probador de eventos*** en ***Destino***, es posible que recibas un error: ***Error de validación ID de dispositivo de AppsFlyer ('integrations.AppsFlyer.appsFlyerId') para enviar eventos de servidor a servidor***.

Este error no significa que haya un problema con la integración entre Segment y AppsFlyer. El Probador de Eventos te permite probar el envío de servidor a servidor de Segment a AppsFlyer. Cualquier evento que se envíe mediante servidor a servidor requiere el AppsFlyerID, por lo que el probador de eventos lanza el error.

Sin embargo, esto solo es relevante para eventos de servidor a servidor. Cuando usas la API del SDK de Segment para registrar eventos, los eventos se envían desde el SDK tanto a Segment como a AppsFlyer. Para la llamada a la API de AppsFlyer, se incluye el ID de dispositivo de AppsFlyer.

</Accordion>

<div id="im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

<Accordion title="Estoy usando una herramienta de análisis de terceros. ¿Debería integrarlo tanto con AppsFlyer como con Segment?">

No, solo debes usar el panel de control de Segment para habilitar las herramientas de análisis de terceros.

</Accordion>

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01JZMD855TA62KQ4AWJ5F6WSDP=introducci%C3%B3n integrating-segment-with-appsflyer=integraci%C3%B3n-de-segment-con-appsflyer h_01JZMD855TNEYZG1MDZY7FWV8S=integraci%C3%B3n-de-segment-con-appsflyer faqs=preguntas-frecuentes h_01JZMD855TAEBDPAMEAEH66F27=preguntas-frecuentes h_01JZMD855T2BXFR1AKRNAA7M51=how-can-i-integrate-segment-with-appsflyer h_01JZMD855TG3WEKQH21JJ1PT43=what-sdks-do-i-need-to-add-to-my-app h_01JZMD855TW07PGDA6QHFWPN67=how-does-the-sdk-wrapper-work h_01JZMD855TNZGKVY2G98FPM22Z=advertencia h_01JZMD855T0BEENPF0BMQDBFS8=is-there-any-difference-in-functionality-between-the-segment-sdk-wrapper-and-the-appsflyer-sdk h_01JZMD855TV6J44PAV1A7JCKT5=i-dont-see-inapp-event-data-in-the-appsflyer-dashboard h_01JZMD855TH07JNZBT8CN4026W=install-and-inapp-events-data-in-segment-and-appsflyer-doesnt-match h_01JZMD855TY8X2PV1HB8Y0QT6Z=im-getting-a-validation-error-when-testing-events-in-segment h_01JZMD855TCE97QW8TSBEN1DYY=im-using-a-thirdparty-analytics-tool-should-i-integrate-it-with-both-appsflyer-and-segment" />

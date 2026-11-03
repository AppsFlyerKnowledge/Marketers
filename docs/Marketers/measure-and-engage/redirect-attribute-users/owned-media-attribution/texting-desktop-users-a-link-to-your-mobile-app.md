---
title: >-
  Mensajes de texto a los usuarios de escritorio con un enlace a tu aplicación
  móvil
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2019-11-21T09:13:52Z'
  edited_at: '2026-08-12T12:25:09Z'
  id: 360003799658
  locale: es
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/es/articles/360003799658
---
> **En resumen:** Convierte usuarios de web de desktop en usuarios de aplicación móvil mediante proveedores de SMS y OneLink.

![text-me-the-app-web-form.png](https://files.readme.io/d28b843ab7528138b4d85b147b8d613efde740d354238227b0f123030fa3a1de-360004940018.png)

## Introducción

Si tu marca tiene tanto una aplicación web como una aplicación móvil, es posible que los usuarios de la web de desktop decidan en algún momento que quieren instalar la aplicación móvil.

Para ayudarles a hacerlo y ofrecer una mejor experiencia de usuario, puedes enviarles un enlace directo a la aplicación por SMS. Esta es la forma más rápida de ayudarles con la instalación de la aplicación.

Así, no tienen que abrir la tienda de aplicaciones en su móvil, buscar tu aplicación e instalarla. Cuando ahorras tiempo y esfuerzo a los usuarios, es más probable que conviertan e instalen tu aplicación móvil.

> 📘 **Nota:**
>
> Ofrecemos otra solución para la <Anchor target="_blank" href="/marketers/es/docs/qr-to-app-conversion">conversión de desktop a web</Anchor> que solo requiere publicar un código QR (generado a partir de tu OneLink) en tu sitio de desktop.

## Requisitos

Para enviar un enlace a tu aplicación móvil por SMS a usuarios de escritorio, necesitas lo siguiente:

1. Una cuenta con un proveedor de SMS como Twilio, AWS SNS o bandwidth.com.
2. Un entorno de backend donde puedas gestionar la lógica para enviar enlaces a los usuarios por SMS.
3. Un enlace personalizado multiplataforma como <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.

## Configuración

La siguiente sección ofrece una visión general de alto nivel de los requisitos tratados anteriormente.

### Cuenta con un proveedor de SMS para enviar un enlace a la aplicación

Crea una cuenta con cualquier proveedor de SMS. Después, podrás enviar enlaces a tu aplicación móvil a un gran número de usuarios en cualquier momento.

Consulta la siguiente lista para ver algunos proveedores populares que ofrecen soporte para varios lenguajes de programación y tienen API completas para distintos casos de uso:

* <Anchor target="_blank" href="https://www.twilio.com/docs/sms/send-messages">Twilio</Anchor>
* <Anchor target="_blank" href="https://dev.bandwidth.com/messaging/about.html">bandwidth</Anchor>
* <Anchor target="_blank" href="https://docs.aws.amazon.com/sns/latest/dg/sns-mobile-phone-number-as-subscriber.html">AWS SNS</Anchor>
* <Anchor target="_blank" href="https://www.braze.com/docs/user_guide/message_building_by_channel/sms/create/">Braze</Anchor>
* <Anchor target="_blank" href="https://www.airship.com/platform/channels/sms/">Airship</Anchor>
* [Swrve](https://docs.swrve.com/user-documentation/campaigns/campaign-channels/intro-to-sms/)
* <Anchor target="_blank" href="https://help.mixpanel.com/hc/en-us/articles/115004730066-Send-SMS-Messages-From-Mixpanel">Mixpanel</Anchor>

### Un entorno de backend para comunicarte con el proveedor de SMS

Los proveedores de SMS requieren tokens de autenticación para usar sus servicios. Además, los números de teléfono de los usuarios son datos sensibles. Por estos motivos, lo mejor es gestionar todo desde tu backend.

### Un enlace personalizado multiplataforma

Un enlace personalizado multiplataforma redirige al usuario a la tienda de aplicaciones o al destino correctos según el dispositivo que tenga. De este modo, puedes enviar el mismo enlace a cualquier usuario, independientemente del dispositivo que tenga.

## Enviar la aplicación a los usuarios por SMS

En esta sección se describe el flujo para enviar a los usuarios un enlace a la aplicación por SMS. También se explica cómo hacer el seguimiento del número de usuarios que instalan la aplicación desde el enlace.

### Crear un OneLink multiplataforma

Crea un OneLink multiplataforma para incluirlo en el SMS. Al crear el enlace, tienes la opción de definir la fuente de medios y la campaña. Te sugerimos que configures la fuente de medios y la campaña de la siguiente manera:

* fuente de medios: sitio web
* campaña: text-me-the-app

Al enviar OneLink por SMS, lo mejor es usar la versión de enlace corto de OneLink.

Para obtener información sobre cómo crear el enlace, consulta <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">aquí</Anchor>.

### Configura un tema de SMS en la cuenta de tu proveedor de SMS

En este paso, creas un tema o mensaje de SMS que contiene el OneLink a la aplicación. Este SMS se envía cuando los usuarios rellenan y envían un formulario con su número de teléfono. Cuando los usuarios envían el formulario, tu backend recibe la solicitud y se comunica con la API del proveedor de SMS para enviar el enlace.

### Configura un formulario web para recopilar números de teléfono

En tu sitio web, en las páginas que elijas, configura una llamada a la acción para animar a los usuarios a instalar tu aplicación. La llamada a la acción debe abrir un formulario web a través del cual los usuarios puedan enviar sus números de teléfono.

### Aplica la lógica en tu backend

Al enviar el formulario, el sitio web debe enviar una solicitud a tu backend. El backend recibe el número de teléfono y envía una solicitud al proveedor de SMS para enviar por SMS un enlace a la aplicación al teléfono del usuario.

Consulta la API y la documentación de tu proveedor de SMS para saber cómo crear la lógica en tu backend.

## Cómo funciona la atribución al enviar un enlace a la App

 No hay ninguna forma de incluir el ID de publicidad al enviar por mensaje de texto a los usuarios de escritorio un enlace a la aplicación. Por lo tanto, AppsFlyer recurre a la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">atribución mediante modelado probabilístico</Anchor>.

AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows#ventana-de-lookback-de-modelado-probabilístico">limita la ventana de lookback</Anchor> para los clics de Modelado probabilístico, a fin de mantener la precisión. Los límites son:

* iOS: hasta 24 horas
* Android (Google Play): hasta una hora
* Android (fuera de la tienda): hasta 24 horas

Anima a tus usuarios a instalar lo más cerca posible del clic para que AppsFlyer pueda atribuir con precisión la instalación al enlace enviado por mensaje de texto. Puedes hacerlo ofreciendo cupones, descuentos o créditos del juego.

## Atribución basada en las personas.

Hay más formas, además de enviar por mensaje de texto un enlace a la aplicación, en las que los usuarios convierten de la web a la aplicación. No siempre está claro de dónde proceden estos usuarios ni qué fuentes de medios y campañas contribuyen a su conversión.

Para obtener más insights sobre cuántos usuarios web se convierten en usuarios de aplicaciones móviles, y qué fuentes de medios y campañas intervienen en el proceso, usa la atribución basada en personas.

La atribución basada en personas (PBA) reúne datos tanto de campañas web como de campañas de aplicaciones móviles. Los datos consolidados te ayudan a analizar los viajes del usuario entre plataformas y la transición del usuario de la web a las aplicaciones móviles.

Para saber más, haz clic <Anchor target="_blank" href="/marketers/es/docs/people-based-attribution-pba-overview">aquí</Anchor>.

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01KQS4E94MVN7NEEDR7ESA17K9=introducci%C3%B3n h_01KQS4E94MSP2PQ0RVAHS2JY8R=nota requirements=requisitos h_01KQS4E94MVYA0EZ7Y0FCMZEBC=requisitos setting-up=configuraci%C3%B3n h_01KQS4E94MF2BZZ5AXP67R7YRW=configuraci%C3%B3n sms-provider-account-to-text-a-link-to-the-app=cuenta-con-un-proveedor-de-sms-para-enviar-un-enlace-a-la-aplicaci%C3%B3n h_01KQS4E94MYPEBKN80CNHCV1DG=cuenta-con-un-proveedor-de-sms-para-enviar-un-enlace-a-la-aplicaci%C3%B3n a-backend-environment-to-communicate-with-the-sms-provider=un-entorno-de-backend-para-comunicarte-con-el-proveedor-de-sms h_01KQS4E94MW7DWRGPNX8D98W46=un-entorno-de-backend-para-comunicarte-con-el-proveedor-de-sms a-multiplatform-custom-link=un-enlace-personalizado-multiplataforma h_01KQS4E94MP2Q29S7892GGT0QM=un-enlace-personalizado-multiplataforma texting-the-app-to-users=enviar-la-aplicaci%C3%B3n-a-los-usuarios-por-sms h_01KQS4E94MGBCX0TM5AGHXPX0Z=enviar-la-aplicaci%C3%B3n-a-los-usuarios-por-sms create-a-multiplatform-onelink=crear-un-onelink-multiplataforma h_01KQS4E94MQSWQ9S0CHNJG8B77=crear-un-onelink-multiplataforma set-up-an-sms-topic-in-your-sms-provider-account=configura-un-tema-de-sms-en-la-cuenta-de-tu-proveedor-de-sms h_01KQS4E94MG7KGB8HQVT11717J=configura-un-tema-de-sms-en-la-cuenta-de-tu-proveedor-de-sms set-up-a-web-form-to-collect-phone-numbers=configura-un-formulario-web-para-recopilar-n%C3%BAmeros-de-tel%C3%A9fono h_01KQS4E94MNPRC5AJ9EJD4GPG3=configura-un-formulario-web-para-recopilar-n%C3%BAmeros-de-tel%C3%A9fono apply-logic-in-your-backend=aplica-la-l%C3%B3gica-en-tu-backend h_01KQS4E94MA810B0QRSMDQ0FQM=aplica-la-l%C3%B3gica-en-tu-backend how-attribution-works-when-sending-a-link-to-the-app=c%C3%B3mo-funciona-la-atribuci%C3%B3n-al-enviar-un-enlace-a-la-app h_01KQS4E94MC8C19RCCPV52G7N1=c%C3%B3mo-funciona-la-atribuci%C3%B3n-al-enviar-un-enlace-a-la-app peoplebased-attribution=atribuci%C3%B3n-basada-en-las-personas h_01KQS4E94MJ0C6Q82H67R22S2W=atribuci%C3%B3n-basada-en-las-personas" />

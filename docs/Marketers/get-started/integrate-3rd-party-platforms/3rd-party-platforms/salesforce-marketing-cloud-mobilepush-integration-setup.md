---
title: Salesforce Marketing Cloud Configuración de la integración de MobilePush
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-14T06:37:05Z'
  edited_at: '2026-08-12T11:59:30Z'
  id: 10590769196817
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/10590769196817
---
> **De un vistazo:** Salesforce Marketing Cloud MobilePush, un partner integrado de AppsFlyer, es una plataforma de engagement de usuario para equipos de marketing, crecimiento y engagement.

## Visión general

Salesforce Marketing Cloud MobilePush te permite crear y enviar mensajes push dirigidos basados en datos de consumidores multicanal. Esto ayuda a fomentar el uso de las aplicaciones y a ofrecer un mayor retorno de la inversión. Con MobilePush, puedes ver cómo los usuarios navegan a través de tu aplicación, desde los productos que ven hasta el tiempo que pasan en cada página. La integración de MobilePush te permite:

* Impulsar el engagement y el mCommerce
* Obtener insights valiosos del usuario
* Crear campañas multicanal fácilmente
* Segmentar y programar mensajes

> 🚧 **¡Importante!**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Configuración de Salesforce Marketing Cloud MobilePush

La mayor parte de la configuración se realiza en Salesforce (pasos 1-4). El paso 5 se realiza en AppsFlyer.

### Paso 1: Configurar el SDK de MobilePush

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_get_started.htm&type=5">Implementa la configuración del SDK de MobilePush.</Anchor>

### Paso 2: Aprovisionamiento para notificaciones push

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-provision.html">Crea un certificado `.p12` .</Anchor>

### Paso 3: Habilitar las notificaciones push de la aplicación

* <Anchor target="_blank" href="https://salesforce-marketingcloud.github.io/MarketingCloudSDK-iOS/get-started/get-started-configureforpush.html">Implementa las notificaciones push.</Anchor>

### Paso 4: Configurar las notificaciones push de la aplicación

* <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_outbound_message.htm&type=5">Crea y envía mensajes push a dispositivos móviles.</Anchor>

> 📘 **Nota**
>
> Al crear una notificación push en Salesforce Marketing Cloud, se debe agregar una <Anchor target="_blank" href="https://help.salesforce.com/s/articleView?id=sf.mc_mp_custom_keys.htm&type=5">clave personalizada</Anchor> para que AppsFlyer pueda atribuir correctamente los atributos PID y de campaña correctos. Utiliza `AF_xxxxxxxxx` como clave personalizada.

### Paso 5: Configurar las notificaciones push en AppsFlyer

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications-ios#addpushnotificationdeeplinkpath-recommended">Configura el SDK de iOS usando OneLink (paso 3 en este enlace).</Anchor>

> 📘 **Nota**
>
> Asegúrate de que la clave personalizada `AF_xxxxxxxxx` que introdujiste en el [paso 4](/docs/salesforce-marketing-cloud-mobilepush-integration-setup#paso-4-configurar-las-notificaciones-push-de-la-aplicación) tenga el mismo valor que la introducida en la función `ddPushNotificationDeepLinkPath`.

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01H9HWK3F5TQZ8YQZBHGBZACPG=visi%C3%B3n-general h_01H9HWK5DM87JTDVFND0KB965G=importante setting-up-salesforce-marketing-cloud-mobilepush=configuraci%C3%B3n-de-salesforce-marketing-cloud-mobilepush h_01H9HWK3F52YGQPX4B82N40PPD=configuraci%C3%B3n-de-salesforce-marketing-cloud-mobilepush step-1-set-up-mobilepush-sdk=paso-1-configurar-el-sdk-de-mobilepush h_01H9HWK3F5HCVZ0225MFRYRW5Q=paso-1-configurar-el-sdk-de-mobilepush step-2-provision-for-push-notifications=paso-2-aprovisionamiento-para-notificaciones-push h_01H9HWK3F5RNCZG340E0CT5XJC=paso-2-aprovisionamiento-para-notificaciones-push step-3-enable-app-push-notifications=paso-3-habilitar-las-notificaciones-push-de-la-aplicaci%C3%B3n h_01H9HWK3F5E4W8FG35V4JTFN7F=paso-3-habilitar-las-notificaciones-push-de-la-aplicaci%C3%B3n step-4-set-up-app-push-notifications=paso-4-configurar-las-notificaciones-push-de-la-aplicaci%C3%B3n h_01H9HWK3F5K8V8AVADXNNG25GY=paso-4-configurar-las-notificaciones-push-de-la-aplicaci%C3%B3n h_01H9HWK3F5VG2GBCE93B69AADH=nota step-5-set-up-push-notifications-in-appsflyer=paso-5-configurar-las-notificaciones-push-en-appsflyer h_01H9HWK3F5YJ71YCWHV4B02VYP=paso-5-configurar-las-notificaciones-push-en-appsflyer h_01H9HWK3F5T67NSPE9CVPS1KTA=nota-1" />

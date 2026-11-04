---
title: Integración de Bloomreach con AppsFlyer
metadata:
  keywords:
    - marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2026-03-29T13:30:32Z'
  edited_at: '2026-08-12T12:24:28Z'
  id: 45235709425553
  locale: es
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/es/articles/45235709425553
---
> **De un vistazo:** Configura una integración con Bloomreach para habilitar Deep Linking sin interrupciones desde campañas de correo electrónico, medir el tráfico tanto en Bloomreach como en AppsFlyer y crear experiencias de usuario que impulsen la conversión.

<Image alt="Bloomreach + AppsFlyer.png" src="https://files.readme.io/842523ac61d5f702a451b361d435e794f8dedad0f54eecffdf27f596c2cab262-45298084947473.png" width="645px" />

<div id="about-the-integration" />

## Sobre la integración

Bloomreach es una plataforma de automatización del marketing por correo electrónico y un proveedor de servicios de correo electrónico (ESP) que ayuda a las marcas a crear experiencias personalizadas en todos los canales.

La integración entre AppsFlyer y Bloomreach permite un Deep Linking sin interrupciones desde campañas de correo electrónico, da soporte a una medición precisa del tráfico tanto en Bloomreach como en AppsFlyer y ayuda a crear experiencias de usuario fluidas que impulsan la conversión.

<div id="set-up-the-integration" />

## Configura la integración

Configurar la integración requiere acciones tanto en AppsFlyer como en Bloomreach. Para configurar la integración, sigue estos pasos:

<div id="step-1-in-appsflyer-create-and-configure-onelink" />

<Accordion title="Paso 1: En AppsFlyer, crea y configura OneLink">

Primero, configura OneLink en AppsFlyer y confirma que la configuración necesaria de alojamiento y dominio esté implementada.

<div id="when-your-app-is-installed" />

#### Cuando la aplicación está instalada

Define el comportamiento de redirección para los usuarios que ya tienen tu app instalada.

**Para definir el comportamiento de redireccionamiento:**

1. <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Crea una plantilla de OneLink</Anchor> y configura Universal Links/App Links. Esta plantilla se utilizará más tarde para crear enlaces de OneLink para tus campañas de correo electrónico.
2. Si ya tienes una plantilla de OneLink existente configurada que habilita Universal Links/App Links, puedes usarla.

<div id="hosting-and-ssl" />

#### Hosting y SSL

* Los enlaces de OneLink están protegidos con SSL y alojados por AppsFlyer.
* El archivo AASA y los archivos de App Link también están alojados por AppsFlyer.

Consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-your-esp-integration-with-appsflyer#configura-tu-aplicación-para-soportar-deep-linking">información e instrucciones adicionales.</Anchor>

<div id="app-domain-definition" />

#### Definición del dominio de la aplicación

Ejemplo: para iOS, define el dominio asociado de la siguiente manera:

```text
applinks:<your-onelink-subdomain>.onelink.me
```

Consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">información e instrucciones adicionales.</Anchor>

</Accordion>

<div id="step-2-in-bloomreach-define-a-universal-link-domain" />

<Accordion title="Paso 2: En Bloomreach, define un dominio de Universal Link">

A continuación, define un dominio de Universal Link en Bloomreach para que los enlaces puedan dar soporte a Deep Linking sin dejar de medirse.

Los dominios definidos en Bloomreach no se envuelven en un enlace de tracking de clics de CDN cuando se usan en una campaña de correo electrónico, lo que habilita Deep Linking.

Se añade automáticamente un parámetro adicional al Universal Link original para habilitar la medición a través de los SDK web y móviles de Bloomreach.

Consulta <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/universal-link">información adicional e instrucciones.</Anchor>

<Image alt="2026-03-31_09-28-18.png" src="https://files.readme.io/4058ab59e2622f26327d9a4a62fa8afdc5965210acba9d9c5bb7a62d53a05503-45298084948753.png" width="73.36%" />

<div id="example" />

> 📄 **Ejemplo**
>
> A continuación se muestra un ejemplo de un enlace Universal sin encapsular, con los parámetros de tracking de Bloomreach añadidos:
>
> ```text
> https://engmntqa.onelink.me/LtRd?pid=ESP_Bloomreach&c=esp-campaign&is_retargeting=true&utm_source=bloomreach&utm_medium=email&utm_campaign=Test-severla-link-yossi-26-10&xnpe_cmp=.eJwzPNrmPEXT6ZZjVKC-flJ-SqV-SWJSTqp-CYRdpF-SQrxItHEslJuSWaafmMWTsWTZufIm9r61XAs2AABFBChI.jF6UMukHXiw5lw
> ```

</Accordion>

<div id="step-3-in-bloomreach-implement-mobile-and-web-sdks" />

<Accordion title="Paso 3: Implementa los SDK móviles y web de Bloomreach">

Por último, implementa los SDK de Bloomreach correspondientes para garantizar que la medición de clics funcione correctamente en las aplicaciones móviles y en la web.

<div id="ios" />

#### apps de iOS,

Implementa el <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">SDK móvil</Anchor> de Bloomreach para iOS y asegúrate de que la medición de enlaces Universal esté configurada correctamente. El SDK de Bloomreach admite la medición de enlaces Universal para capturar las interacciones de los usuarios iniciadas a través de campañas de correo electrónico.

Consulta información adicional e instrucciones sobre <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/ios-sdk-universal-links#track-universal-links">los enlaces Universal</Anchor> y los <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">SDK móviles.</Anchor>

#### Android

Implementa el <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">SDK móvil</Anchor> de Bloomreach para Android y configura los App Links de forma similar a los enlaces Universal de iOS para garantizar la atribución de clics y la coherencia de la medición.

Consulta información adicional e instrucciones sobre <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/android-sdk-app-links#track-android-app-links">Android App Links</Anchor> y los <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">SDK móviles.</Anchor>

#### Web

Implementa el <Anchor target="_blank" href="https://Mobile%20SDKs">SDK web de JavaScript</Anchor> de Bloomreach para garantizar que los clics de los enlaces Universal también se midan en tu sitio web. La medición de clics de los enlaces Universal en tu sitio web funcionará sin necesidad de configuración adicional.

Consulta <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/js-sdk">información adicional e instrucciones.</Anchor>

</Accordion>

<div id="step-4-test-the-integration-by-sending-a-test-email" />

<Accordion title="Paso 4: Prueba la integración">

Cuando completes la configuración, envía un correo electrónico de prueba para validar la integración y confirmar que el Deep Linking y la medición de clics funcionan como se espera.

1. **Inserta el enlace OneLink en un correo electrónico de prueba y envíatelo.**

   Con el editor de correo electrónico de tu ESP, añade el enlace OneLink a un correo electrónico de prueba y envíatelo. Asegúrate de que se use el dominio configurado en el paso 2 y de que el enlace no esté encapsulado.
2. **Valida la estructura del enlace.**

   Abre el correo electrónico de prueba y confirma que Bloomreach no encapsula el OneLink. Además, verifica que el parámetro `xnpe_cmp` se añada al enlace.
3. **Verifica la medición de clics y el comportamiento de OneLink.**

   Desde tu dispositivo móvil, abre el correo electrónico y haz clic en el enlace. Confirma que:

   * Si la aplicación está instalada, se abre y hace Deep Linking al contenido esperado dentro de la aplicación.
   * El clic aparece en el panel de analíticas de Bloomreach.

Cuando se completen todas las validaciones, la configuración de la integración estará completa.

<div id="note" />

> 📘 **Advertencia**
>
> Si los clics no aparecen en la plataforma Bloomreach, ponte en contacto con el equipo de soporte de Bloomreach.

</Accordion>

<div id="important-notes" />

> 📘 **Notas importantes**
>
> * AppsFlyer aloja y protege todos los archivos de asociación y OneLink pertinentes, incluidos los archivos AASA y App Link.
> * Los SDK de Bloomreach para iOS, Android y JavaScript deben implementarse correctamente para que funcione la medición de enlaces.
> * Universal Links y App Links deben permanecer sin encapsular, con los parámetros de Bloomreach añadidos automáticamente.
> * Esta integración permite una atribución precisa de los clics de correo electrónico a app y de correo electrónico a web, así como la medición del engagement entre canales.

<div data-zendesk-anchors="about-the-integration=sobre-la-integraci%C3%B3n h_01KMWVJR5AQRY8YRAD6ZV6H1VV=sobre-la-integraci%C3%B3n set-up-the-integration=configura-la-integraci%C3%B3n h_01KMWVJR5ACS7Q1GKP1GGGBRYK=configura-la-integraci%C3%B3n h_01KMWVJR5ABTK766X4G0B9J92E=step-1-in-appsflyer-create-and-configure-onelink when-your-app-is-installed=cuando-la-aplicaci%C3%B3n-est%C3%A1-instalada h_01KMWVJR5AY8WRV4Y6GTWHDE5D=cuando-la-aplicaci%C3%B3n-est%C3%A1-instalada hosting-and-ssl=hosting-y-ssl h_01KMWVJR5A40099PC91YW2QR1D=hosting-y-ssl app-domain-definition=definici%C3%B3n-del-dominio-de-la-aplicaci%C3%B3n h_01KMWVJR5A7JV0FHC5W1EP9502=definici%C3%B3n-del-dominio-de-la-aplicaci%C3%B3n h_01KMWVJR5A57Y1ZPAYBC5321DX=step-2-in-bloomreach-define-a-universal-link-domain h_01KMWVJR5BER86B8YV3H60PGF6=ejemplo h_01KMWVJR5B6K6EG49VJM7JSEK2=step-3-in-bloomreach-implement-mobile-and-web-sdks ios=apps-de-ios h_01KMWVJR5B3505FSJSXRC9NQ4A=apps-de-ios h_01KMWVJR5BE703X877C40DZ5MX=android h_01KMWVJR5BVTXS8W2WGTYEGP0D=web h_01KMWVJR5BPA0N2YTK2983DHMT=step-4-test-the-integration-by-sending-a-test-email h_01KMWVJR5B6PHSEK7NA5W8ZGNF=advertencia h_01KN1TCDE27DNPJJ8HRHZ4FPA0=notas-importantes" />

---
title: Integración de Tealium con AppsFlyer
metadata:
  keywords:
    - Marketers
    - TEST ID LOC
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-22T16:09:24Z'
  edited_at: '2026-08-12T11:59:44Z'
  id: 10820404821393
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/10820404821393
---
> **De un vistazo:** Tealium, una plataforma de datos del cliente (CDP), conecta los datos del cliente a través de Internet, móvil, IoT y fuera de línea. Aprende cómo compartir automáticamente los datos de conversión con Tealium.

<Image alt="Tealium_icon.png" src="https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png" width="276px" />

<div id="overview" />

## Visión general

Al integrar Tealium con AppsFlyer, los clientes móviles pueden aprovechar el SDK de atribución móvil de AppsFlyer y enviar datos de conversión de la atribución directamente a su perfil de Tealium AudienceStream.

<div id="important" />

> 🚧 **¡Importante!**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-tealium" />

## Configuración de Tealium

Puedes elegir una de las siguientes formas de integrar Tealium con AppsFlyer:

* Integración del lado del cliente
* Integración del lado del servidor

<div id="client-side-integration" />

### Integración del lado del cliente

Usa comandos remotos para bibliotecas de iOS y Android, lo que permite activar el código nativo en el SDK de AppsFlyer.

**Para integrar Tealium mediante la integración del lado del cliente:**

* Sigue la <Anchor target="_blank" href="https://docs.tealium.com/platforms/remote-commands/integrations/appsflyer/">guía de integración de comandos remotos</Anchor>

<div id="server-side-integration" />

### Integración del lado del servidor

Configura el conector de eventos de aplicación de AppsFlyer en tu cuenta de Customer Data Hub para transmitir datos entre Tealium y AppsFlyer en tiempo real.

**Para integrar Tealium mediante la integración del lado del servidor:**

* Sigue la <Anchor target="_blank" href="https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/">guía del conector de eventos de aplicación de AppsFlyer</Anchor>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01H9HWK1ACY09ZVD7WHEQR4MR3=visi%C3%B3n-general h_01H9HWK1ACA6A743PDY3Q1Y0KV=importante setting-up-tealium=configuraci%C3%B3n-de-tealium h_01H9HWK1AC27GPZPZR13SFC3GM=configuraci%C3%B3n-de-tealium clientside-integration=integraci%C3%B3n-del-lado-del-cliente h_01H9HWK1ACH6K0FDTVCHAPSKME=integraci%C3%B3n-del-lado-del-cliente serverside-integration=integraci%C3%B3n-del-lado-del-servidor h_01H9HWK1ACDZQEYVRZ7QWQ4KY3=integraci%C3%B3n-del-lado-del-servidor" />

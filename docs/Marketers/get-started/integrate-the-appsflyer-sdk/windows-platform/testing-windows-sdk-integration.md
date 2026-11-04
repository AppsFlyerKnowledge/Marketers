---
title: Prueba de integración del SDK de Windows
metadata:
  keywords:
    - Testing
    - Windows
    - SDK
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2016-11-15T12:35:48Z'
  edited_at: '2026-08-12T12:03:11Z'
  id: 217924503
  locale: es
  section: Windows platform
  section_id: 6551223206417
  url: https://support.appsflyer.com/hc/es/articles/217924503
---
> **En resumen:** Prueba la integración de tu aplicación de Windows con AppsFlyer.

* Actualmente, no hay forma de hacer pruebas con Windows Referrer salvo subir la aplicación a la tienda de aplicaciones de Windows.
* Al hacer pruebas con Windows Referrer, debes tener en cuenta las siguientes restricciones:
  * Debes haber iniciado sesión en la tienda.
  * Tu dispositivo no debe tener la actualización Windows 10 Anniversary Update.
  * Tu dispositivo no debe haber tenido nunca la aplicación (el referrer de Windows es vitalicio; incluso si estás en la lista de permitidos o has esperado más de 90 días, no recibirás atribución del referrer).

<div id="test-sdk-integration" />

## Probar la integración del SDK

1. Es necesario probar la integración del SDK en un dispositivo de prueba registrado. Para registrar tu dispositivo de prueba, sigue los pasos <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">aquí</Anchor>.
2. Abre el Dashboard de AppsFlyer y elige la aplicación que estás probando.
3. Desde el menú de navegación, selecciona Pruebas de integración de SDK.
4. Aparecerán tres opciones de prueba:

* Instalación no orgánica
* Eventos dentro de la aplicación
* Enlaces profundos

[![](https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png)](https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png)

<div id="testing-non-organic-install" />

## Prueba de instalación no orgánica

1. Desde la lista desplegable, selecciona uno de tus dispositivos registrados
2. Selecciona desde dónde estás instalando la aplicación (Windows Store u Otro)
3. Escanea el código QR generado con tu dispositivo de prueba registrado y sigue las instrucciones que aparecen en el dispositivo.
4. Espera hasta que la instalación no orgánica se registre en la página de Prueba de integración, lo que indica que la prueba se realizó correctamente. Esto puede tardar hasta dos minutos. Si para entonces la aplicación no ha registrado una instalación no orgánica, consulta la guía de resolución de problemas que aparece en la página de Prueba de integración.

<div id="testing-in-app-events" />

## Probando eventos in-app

1. Desde el menú desplegable, selecciona uno de tus dispositivos de prueba registrados y haz clic en Siguiente.
2. Abre tu aplicación y comienza a generar eventos in-app.
3. Verás un registro de estos eventos a medida que se van registrando en tiempo real.

<div id="testing-deep-linking" />

## Pruebas de Deep Linking

1. Debes definir OneLink para tu aplicación para poder probar Deep Linking. Consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">la guía de OneLink</Anchor>
2. Desde el menú desplegable, selecciona uno de tus dispositivos de prueba registrados y haz clic en Siguiente.
3. Escanea el código QR con tu dispositivo de prueba registrado y sigue las instrucciones de tu dispositivo.
4. Espera hasta que el Deep Linking se registre correctamente en la página Prueba de integración.

<div data-zendesk-anchors="test-sdk-integration=probar-la-integraci%C3%B3n-del-sdk testing-nonorganic-install=prueba-de-instalaci%C3%B3n-no-org%C3%A1nica testing-inapp-events=probando-eventos-in-app testing-deep-linking=pruebas-de-deep-linking" />

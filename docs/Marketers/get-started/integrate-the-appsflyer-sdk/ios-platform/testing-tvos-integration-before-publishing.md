---
title: Cómo probar la integración de tvOS antes de publicar
metadata:
  keywords:
    - Testing
    - tvos
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
  created_at: '2016-07-12T09:49:14Z'
  edited_at: '2026-08-12T12:02:07Z'
  id: 211758923
  locale: es
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/es/articles/211758923
---
> **En resumen:** Simula una instalación no orgánica desde tu dispositivo AppleTV con la app de prueba de tvOS.

<div id="overview" />

## Visión general

AppleTV no tiene navegador. Por lo tanto, no puedes probar clics ni instalaciones en el dispositivo para una **aplicación** no publicada. (Para las **apps** publicadas, puedes <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers#pruebas-mediante-enlaces-de-atribución">hacer pruebas con enlaces de atribución</Anchor>).

Para probar la atribución en apps no publicadas, puedes usar la **app de prueba de tvOS.**

<div id="how-does-the-tvos-test-app-work" />

### ¿Cómo funciona la App de prueba de tvOS?

La app de prueba de tvOS te permite simular un clic en un enlace de atribución desde tu dispositivo AppleTV, para que luego puedas instalar la app y recibir una atribución no orgánica.

**Para probar la atribución con la App de prueba de tvOS:**

1. Descarga el proyecto desde <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyerFramework">aquí</Anchor>.
2. En XCode, compila el proyecto para tu dispositivo AppleTV de prueba.

   Se mostrará la siguiente ventana:

   ![](https://files.readme.io/7ed3c5e8165e6d27c9d87db8b026c0898536b145def6bfedd0dc5f78c7804669-205289963.png)
3. <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">Registra</Anchor> tu dispositivo AppleTV como dispositivo de prueba con el **IDFA** que aparece en la parte inferior de la pantalla de la aplicación.
4. En la app de prueba, introduce tu AppID tal como aparece en el Dashboard de tu app.

   Asegúrate de que la aplicación que estás probando **no esté instalada** en el dispositivo. Para obtener una atribución no orgánica, debes simular un escenario real en el que se haga clic en el enlace de atribución antes de que la aplicación se abra en el **primer** **inicio**.
5. Haz clic en el botón **Click Simulation** y espera una respuesta.

   Si todo es válido, se mostrará el siguiente mensaje:

   ![](https://files.readme.io/27b8b5acfe9691d3704ae36b04e28ecaa643e1b68eb5e0a6f8be70f657b2c0d3-205275743.png)
6. **Instala** tu app integrada en tu dispositivo.

   Si la integración es correcta, se mostrará una atribución no orgánica en tu dashboard, en la fuente de medios **AppsFlyer\_Test**.

   ![](https://files.readme.io/4c6ab66ebd13556bd764d4e93adbb639be208b8955dd1fe1d3dd60ecd5c01a3b-205275823.png)

<div data-zendesk-anchors="overview=visi%C3%B3n-general how-does-the-tvos-test-app-work=c%C3%B3mo-funciona-la-app-de-prueba-de-tvos" />

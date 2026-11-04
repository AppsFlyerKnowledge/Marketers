---
title: Atribución de banners de apps de Safari en iOS
metadata:
  keywords:
    - iOS Safari
    - Smart App Banner
    - Advertisers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-01-02T15:08:07Z'
  edited_at: '2026-11-02T01:16:59Z'
  id: 115000171743
  locale: es
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/es/articles/115000171743
---
> **En resumen:** Safari implementa una función de <Anchor target="_blank" href="http://developer.apple.com/library/ios/#documentation/AppleApplications/Reference/SafariWebContent/PromotingAppswithAppBanners/PromotingAppswithAppBanners.html">banner de app</Anchor> que proporciona una forma estandarizada de promocionar apps en la tienda de aplicaciones de Apple. **Esto no está relacionado con la solución** <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">**Smart Banner**</Anchor> **recomendada de AppsFlyer.**

<div id="note" />

> 📘 **Nota**
>
> Te recomendamos usar AppsFlyer Smart Banners para convertir a los visitantes de tu sitio web en usuarios de la aplicación.
>
> AppsFlyer Smart Banners:
>
> * Compatible con todos los navegadores
> * Son personalizables
> * Funciona en todos los dispositivos Android e iOS

<div id="ios-app-banner" />

## Banner de la App para iOS

Con iOS 6.0 y versiones posteriores, puedes implementar banners de apps en Safari para promocionar apps disponibles en la tienda de aplicaciones.

**Ejemplo de banner en Safari**

<Image alt="AppleBanner_en-us.jpg" src="https://files.readme.io/7cfd7fb6890cbe0151a8edfaf3bfe9e2609cf746c2a2d43c574e6744caa0fde8-360007210818.jpg" width="278px" />

Antes de implementar banners de aplicaciones de iOS, ten en cuenta lo siguiente:

* No implementes a la vez el banner de aplicación de iOS y AppsFlyer Smart Banners. Si lo haces, puede haber problemas de visualización en tu sitio web móvil.
* La solución de banner de aplicación es específica de iOS, lo que significa que no funciona en OS X.
* El banner de app solo funciona en Safari.

<div id="setting-a-web-page-with-an-app-banner-and-click-attribution-link" />

### Configurar una página web con un banner de aplicación y un enlace de atribución de clics

1. Inserta lo siguiente en el elemento de encabezado del HTML de la página web.

   ```html Markup
   <meta name="apple-itunes-app" content="app-id=123456789">Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
   ```
2. Genera un enlace de atribución para la aplicación móvil que estás promocionando en el banner de la aplicación. Puedes usar <Anchor target="_blank" href="/marketers/es/docs/onelink-smart-script-overview">AppsFlyer SmartScript</Anchor> para este propósito; generará dinámicamente un enlace de atribución en función de los parámetros UTM entrantes. A continuación se muestra un ejemplo de un enlace de atribución para la aplicación móvil que se está promocionando en el banner de aplicación. También puedes usar <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">enlaces de atribución personalizados abreviados</Anchor>.

   ```http
   https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign
   ```
3. Inserta el enlace de atribución generado dentro de un píxel de imagen. El píxel de imagen con la URL de medición tiene el formato que se muestra en la ilustración.

   ```html Markup
   <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
   ```

   La página HTML final con el píxel de imagen debe aparecer como se muestra en el siguiente ejemplo de HTML.

   ```html Markup
   <html>
     <head>
       <meta name="apple-itunes-app" content="app-id=123456789">

     </head>
     <body>
       <p>Este es mi sitio web</p>
       <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />
     </body>
   </html>
   ```

**¡Atención!** Este código carga y ejecuta un clic tanto en dispositivos iOS como Android. Para desactivar el código en dispositivos Android, añade la lógica necesaria en tu código.

<div data-zendesk-anchors="h_01M63G1712D0HXWH688309CDQB=nota ios-app-banner=banner-de-la-app-para-ios h_01M63G1713KMRCGZFNPB7CDRVX=banner-de-la-app-para-ios setting-a-web-page-with-an-app-banner-and-click-attribution-link=configurar-una-p%C3%A1gina-web-con-un-banner-de-aplicaci%C3%B3n-y-un-enlace-de-atribuci%C3%B3n-de-clics h_01M63G1713H59N0GGD2R82DPT8=configurar-una-p%C3%A1gina-web-con-un-banner-de-aplicaci%C3%B3n-y-un-enlace-de-atribuci%C3%B3n-de-clics" />

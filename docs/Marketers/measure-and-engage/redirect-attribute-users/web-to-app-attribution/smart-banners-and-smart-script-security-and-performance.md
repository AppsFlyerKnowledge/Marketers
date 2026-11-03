---
title: Seguridad y rendimiento de Smart Banners y Smart Script
metadata:
  keywords:
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-01-30T14:54:37Z'
  edited_at: '2026-08-12T12:25:29Z'
  id: 22082177372561
  locale: es
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/es/articles/22082177372561
---
> **En resumen:** Descubre cómo AppsFlyer aborda de forma proactiva tus preocupaciones de seguridad relacionadas con Smart Banners y Smart Script.

En estas preguntas y respuestas, abordamos consultas habituales sobre Smart Banners & la integración de Smart Script, con especial atención a su impacto en la seguridad y la velocidad del sitio.

## Seguridad de la API de Smart Banners

<div id="what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it" />

<Accordion title="¿Qué datos captura el smart banner cuando alguien hace clic en él o lo visualiza?">

| Tus datos | Nota |
| --- | --- |
| IP del cliente | La IP se utiliza para calcular la ubicación (país, región y estado) |
| gp\_referrer (Google Play Referrer string) |  |
| Agente de usuario |  |
| Página del sitio web | La URL desde la que se originó la llamada al SDK web |
| Protocolo HTTP | HTTP/HTTPS |
| Encabezados | Host, Content-type, Origin, Content-length, Encoding |
| Parámetros de OneLink |  |
| Parámetros del banner | Ajustes de configuración del banner:<ul><li><Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#dismissal-behaviour">Comportamiento al descartar</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#param-table">Parámetros entrantes</Anchor></li><li>Parámetros UTM</li><li>Parámetros de AppsFlyer</li><li>Parámetros predeterminados</li><li>Otros parámetros</li></ul> |

</Accordion>

<div id="what-api-calls-are-needed-to-show-a-smart-banner" />

<Accordion title="¿Qué llamadas a la API son necesarias para mostrar un smart banner?">

* Una API para obtener el SDK desde una CDN ubicada en `https://websdk.appsflyersdk.com`.
* Una API para generar el enlace detrás de la CTA, ubicada en `banner.appsflyer.com`. Esta API se activa mediante el método del SDK [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner).
* Una API para obtener el recurso creativo del banner desde una CDN ubicada en `creatives-cdn-appsflyer.com`.

</Accordion>

<div id="do-these-api-calls-include-an-identifier" />

<Accordion title="¿Estas llamadas a la API incluyen un identificador?">

Sí. La clave web única del cliente actúa como identificador en las llamadas a la API, lo que permite recuperar los datos necesarios para mostrar el banner y generar la URL de OneLink para la CTA del banner.

</Accordion>

<div id="is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key" />

<Accordion title="¿Es posible que una entidad maliciosa cambie la URL o altere la clave web de la API?">

N.º No es posible acceder al código que determina la clave web utilizada en la llamada a la API del banner ni modificarlo. Esto significa que las entidades maliciosas no pueden manipular el cálculo del banner ni la URL de OneLink generada para la CTA del banner.

</Accordion>

## Seguridad del alojamiento del script de Smart Banners

<div id="can-clients-host-a-copy-of-the-smart-banner-script-on-their-server" />

<Accordion title="¿Pueden los clientes alojar una copia del script de Smart Banner en su servidor?">

Los clientes no pueden alojar el script de Smart Banners en sus servidores. Sin embargo, pueden usar <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor> para generar la URL de OneLink e implementar sus propios creativos de banner.

Usar Smart Script junto con tus propios banners te permite diseñar creativos personalizados y asignar y personalizar aún más los enlaces generados, lo que elimina la necesidad de implementar el SDK del banner en tu sitio web y realizar llamadas externas a la API.

</Accordion>

<div id="can-clients-host-their-own-code-and-still-use-banners" />

<Accordion title="¿Pueden los clientes alojar su propio código y seguir usando banners?">

Los clientes pueden desarrollar sus propios banners, incluido el diseño, el desarrollo y la integración en el sitio, y utilizar <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor> para generar los enlaces para la llamada a la acción (CTA) de su banner.

</Accordion>

<div id="can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page" />

<Accordion title="¿Se pueden admitir los Smart Banners sin insertar su fragmento de código en la página?">

* Los clientes tienen la opción de usar gestores de etiquetas para invocar las API de Smart Banner, como alternativa a integrar directamente el fragmento de código. Para saber más sobre los gestores de etiquetas, consulta <Anchor target="_blank" href="/marketers/es/docs/smart-banners-website-code-implementation-for-marketers#implementación-del-código-del-sitio-web">aquí.</Anchor>
* No se admite ejecutar el script en un iFrame.

</Accordion>

<div id="how-does-appsflyer-protect-your-banners-from-postsave-tampering" />

<Accordion title="Cómo protege AppsFlyer tus banners frente a manipulaciones posteriores al guardado">

Al editar y guardar un creativo de banner en el editor de creativos de AppsFlyer, un atacante podría intentar interceptar la solicitud, tomar el control e inyectar código JavaScript malicioso.

Implementamos múltiples medidas para garantizar que Smart Banners esté protegido frente a posibles ataques y evitar ediciones no autorizadas por parte de usuarios ajenos a su propia cuenta.

* Nuestro equipo de seguridad ejecuta pruebas y comprobaciones para asegurarse de que todos nuestros servicios (incluidos Smart Banners) estén protegidos y libres de vulnerabilidades.
* Realizamos pruebas de penetración periódicas, independientes e imparciales para garantizar la protección y la seguridad de AppsFlyer.
* A nivel interno, validamos las etiquetas HTML y Script y saneamos cualquier script malicioso.

</Accordion>

<div id="do-smart-banners-use-cookies" />

<Accordion title="¿Los Smart Banners usan cookies?">

De forma predeterminada, Smart Banners no usan cookies. Sin embargo, ofrecemos una configuración opcional para usar cookies propias a los clientes que prefieran una mayor persistencia (por ejemplo, para abordar la volatilidad del almacenamiento en Safari en iOS 26).

El propietario del sitio web debe <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#set-storage-mode-optional">activar esta opción</Anchor> explícitamente. Si está activada, el propietario del sitio web también es responsable de actualizar su gestión del consentimiento de cookies y sus avisos de privacidad, según lo exija la normativa aplicable.

</Accordion>

## Rendimiento de Smart Banners

<div id="does-the-smart-banner-web-sdk-impact-website-load-speed" />

<Accordion title="¿El SDK web de Smart Banner afecta a la velocidad de carga del sitio web?">

Aunque añadir código adicional a un sitio web podría afectar a los tiempos de carga, la mayor parte del trabajo del banner inteligente se realiza en el servidor, de forma asíncrona y sin bloquear la carga de la página.

Además, usamos CDN para acelerar la carga de las páginas y los banners.

</Accordion>

<div id="can-you-share-some-metrics-regarding-banner-speed-performance" />

<Accordion title="¿Puedes compartir algunas métricas sobre el rendimiento de velocidad del banner?">

La velocidad de carga del banner varía y depende de varios factores, entre ellos:

* Velocidad de Internet
* Conectividad y tipo de conexión
* Rendimiento del sitio y más.

Estos factores, sumados al tiempo mínimo de respuesta de los servidores de AppsFlyer a los navegadores, contribuyen al cálculo de los tiempos de carga del banner.

Como las variables anteriores no están relacionadas con AppsFlyer, no podemos especificar plazos exactos para el proceso integral completo.

</Accordion>

<div id="how-can-i-actively-improve-the-banner-loading-time" />

<Accordion title="¿Cómo puedo minimizar activamente el tiempo de carga del banner?">

El tiempo de carga del banner se ve afectado por el Largest Contentful Paint (LCP), que se refiere principalmente a la imagen del banner. Para mejorar el rendimiento de carga del LCP, puedes::

* Elige una plantilla de banner más pequeña.
* Reduce el tamaño de las imágenes del logotipo y del fondo
  * Considera sustituir la imagen de fondo por un color sólido para reducir los tiempos de carga de los recursos.
  * Usa una CDN para alojar las imágenes de tu banner y acelerar los tiempos de carga.

* Usa el mismo grosor de fuente en todo el banner.

</Accordion>

## Seguridad y rendimiento de Smart Script

<div id="does-smart-script-use-cookies" />

<Accordion title="¿Smart Script usa cookies?">

No, no usamos cookies en nuestra solución Smart Script.

</Accordion>

<div id="does-smart-script-make-any-external-calls-to-generate-links" />

<Accordion title="¿Smart Script hace llamadas externas para generar enlaces?">

No, el script se ejecuta localmente en el sitio web del cliente, por lo que no depende de llamadas externas, lo que hace que su uso sea muy seguro.

</Accordion>

<div id="is-there-a-download-time-associated-with-smart-script" />

<Accordion title="¿Hay algún tiempo de descarga asociado a Smart Script?">

Puedes insertar el script directamente en tu sitio web, lo que garantiza que no haya tiempo de descarga. El script se carga rápidamente porque no requiere llamadas al servidor.

</Accordion>

<div data-zendesk-anchors="smart-banners-api-security=seguridad-de-la-api-de-smart-banners h_01HNDDT0XHK5Y5NYTQMSXYSCZ4=seguridad-de-la-api-de-smart-banners h_01HNDDT0XHY7BZNXA2CRT1W46F=what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it h_01HNDDT0XJGFJE3XBAXTE0C2K5=what-api-calls-are-needed-to-show-a-smart-banner h_01HNDDT0XJVX8KXSZC10GTJMCS=do-these-api-calls-include-an-identifier h_01HNDDT0XJ7MGPFSZKJ7YRZ2HJ=is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key smart-banners-script-hosting-security=seguridad-del-alojamiento-del-script-de-smart-banners h_01HNDDT0XJSS77BFVVT2QQV5HP=seguridad-del-alojamiento-del-script-de-smart-banners h_01HNDDT0XJYW3Y0MQZWW1C1ETJ=can-clients-host-a-copy-of-the-smart-banner-script-on-their-server h_01HNDDT0XJG1SKBMA14KBGKZGD=can-clients-host-their-own-code-and-still-use-banners h_01HNDDT0XJDEGBK5WTBJ52ZVST=can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page h_01HNDDT0XJC7FT514HEGN68T68=how-does-appsflyer-protect-your-banners-from-postsave-tampering h_01HNDDT0XJR4BQPN20FNGJPARY=do-smart-banners-use-cookies smart-banner-performance=rendimiento-de-smart-banners h_01HNDDT0XJNJXY52BZJS9T1G72=rendimiento-de-smart-banners h_01HNDDT0XJ456B4DG38BMMP98W=does-the-smart-banner-web-sdk-impact-website-load-speed h_01HNDDT0XJSEXVNRT8H27EMCNS=can-you-share-some-metrics-regarding-banner-speed-performance h_01HNDDT0XJK99RH6MAJFGQ7FPX=how-can-i-actively-improve-the-banner-loading-time smart-script-security-and-performance=seguridad-y-rendimiento-de-smart-script h_01HNDDT0XJSGVRA6SB2YYYAE0P=seguridad-y-rendimiento-de-smart-script h_01HNDDT0XJW9B4GJ3J4RMJDG6V=does-smart-script-use-cookies h_01HNDDT0XJNZXGPZN2NDHQ34KF=does-smart-script-make-any-external-calls-to-generate-links h_01HNDDT0XJXV12C5P1CD32FZW3=is-there-a-download-time-associated-with-smart-script" />

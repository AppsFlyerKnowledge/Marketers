---
title: Conversión de código QR a aplicación
metadata:
  keywords:
    - OneLink
    - Advertisers
    - owned media
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2020-11-04T09:49:23Z'
  edited_at: '2026-08-12T12:25:02Z'
  id: 360015119718
  locale: es
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/es/articles/360015119718
---
> **En resumen:** Convierte usuarios de desktop, TV, CTV u offline, en usuarios de aplicaciones móviles mediante el uso de códigos QR generados con OneLink.

![6005_QR_code_4.jpg](https://files.readme.io/6db45d7e82bc33ba8af8c6e7d096011d71b06766da9df348dccfa1b3e4aa380d-12368835107601.jpg)

## Conversión del tráfico móvil, no móvil y offline en usuarios de aplicaciones móviles

Publicar códigos QR generados por OneLink en anuncios para desktop, TV, CTV u offline, como en pantallas de tiendas, folletos y empaques, brinda los siguientes beneficios:

* Los usuarios pueden escanear rápida y fácilmente el código con su dispositivo móvil para descargar e instalar tu aplicación.
* Los usuarios ahorran el tiempo y el esfuerzo necesarios para ir a la tienda de aplicaciones y buscar tu aplicación, lo que aumenta enormemente las tasas de conversión de instalación de QR a App.
* La privacidad está protegida, ya que este método de conversión no pasa por SMS y los usuarios no necesitan proporcionar información privada, como un número de teléfono para enviar mensajes de texto.
* Puedes atribuir fácilmente las instalaciones y medir la eficacia de tus anuncios.

Los códigos QR se pueden crear de una de las siguientes opciones:

* [Manualmente, en la interfaz de usuario de AppsFlyer](/docs/qr-to-app-conversion#configuración-manual-del-código-qr)
* [Dinámicamente, usando OneLink Smart Script](/docs/qr-to-app-conversion#dynamic-qr-code-setup) (diseñado específicamente para flujos web-to-app)

<div id="qr-to-app-conversion" />

<Accordion title="Configura la conversión de QR a aplicación">

#### Configuración manual del código QR

**Requisitos previos:**

* Una cuenta de AppsFlyer con una aplicación como mínimo.
* Para atribución: <Anchor target="_blank" href="/marketers/es/docs/integrate-the-appsflyer-sdk">El SDK de AppsFlyer ya está integrado</Anchor> en cada una detus aplicaciones móviles.
  * Si el SDK aún no está instalado en tus aplicaciones, aún es posible crear un enlace de redirección que funcione, pero no será posible establecer un deep link, un deep link diferido o medir las instalaciones en tu dashboard.

* Una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor> configurada.

**Para configurar un código QR para la conversión de desktop web a aplicación**:

1. **Para probar tu código QR**:
   * <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">Crea una sola imagen de QR code</Anchor>
     1. [Recomendado] Crea un nuevo vínculo y establece el origen de medios personalizado. Por ejemplo: **desktop\_web**.  
         El uso de un código QR de un enlace existente funciona. Sin embargo, para fines de reportes, recomendamos no compartir fuentes de medios con otro enlace. En su lugar, utiliza un enlace separado con la fuente de medios dedicada.
     2. Después de hacer clic en **Generar enlace**, se muestra el código QR.
     3. Haz clic en el código QR para descargarlo en resolución completa, ya sea en formato SVG o PNG.
   * <Anchor target="_blank" href="/marketers/es/docs/perform-onelink-bulk-actions-via-csv#downloading-a-collection-of-qr-codes">Crea un enlace personalizado de OneLink.</Anchor>
     1. En la página **Bulk Links**, crea una colección de enlaces.
     2. Descarga las imágenes QR de los enlaces de la colección.
2. Agrega el código QR a tu anuncio, de la misma manera que agregarías cualquier otra imagen/contenido.
   * Consulta las [mejores prácticas](/docs/qr-to-app-conversion#best-practices).
   * Es posible que se requiera asistencia para desarrolladores.

</Accordion>

<div id="customize-qr-code" />

<Accordion title="Personalizar código QR">

![OnelinkQRFinal__1_.gif](https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif)

Puedes personalizar los códigos QR generados a través de OneLink de la siguiente manera:

* Agregar tu logotipo al código QR.
* Cambiar el color del código QR.

**Nota**:

* **Nota**: La personalización del código QR se realiza a nivel de plantilla, no a nivel de enlace individual. Por lo tanto, las personalizaciones afectan a todos los códigos QR basados en la plantilla editada.
* **Nota**: Los códigos QR creados a través de Smart Script no se pueden personalizar.

**Para personalizar tu código QR**:

1. En el dashboard de AppsFlyer, ve a  **Experiencias y deep linking** > **Administración de OneLink**.
2. Selecciona la plantilla que deseas editar y haz clic en **Personalizar código QR**.  
   Se abre el editor de códigos QR.
3. Enter the URL where your logo is hosted. For example: https://yourbrand.com/logo.png.

   Requisitos del logo:

   * Formato PNG o JPG
   * Cuadrado o circular con fondo transparente
   * Dimensiones mínimas: 400 x 400 px
   * Para imprimir, usa la máxima resolución de imagen
4. Configura el color del código QR.
5. Haz clic en **Guardar**.

</Accordion>

<div id="measure-qrtoapp-conversions" />

<Accordion title="Mide las conversiones de QR a aplicaciones">

Puedes medir el rendimiento de tu código QR y su ubicación en diferentes fuentes de publicidad/medios, comparando impresiones (para páginas vistas desde desktops), clics (para escaneos de código QR) e instalaciones de aplicaciones.

Para medir las conversiones de QR a la aplicación:

1. En AppsFlyer, consulta el dashboard general u otras herramientas de análisis de AppsFlyer y registra el total de **clics** e **instalaciones** con tu fuente de medios de código QR (como **desktop\_web**).
2. Registra el total de vistas de páginas de desktop (impresiones) utilizando tu software de análisis web.
3. Mide el rendimiento:
   * <Anchor target="_blank" href="/marketers/es/docs/about-conversion-rates#etapas-del-embudo-de-marketing-y-tasas-de-conversión-1">Tasa de clics</Anchor>
   * <Anchor target="_blank" href="/marketers/es/docs/about-conversion-rates#etapas-del-embudo-de-marketing-y-tasas-de-conversión-1">Tasa de clic-instalación</Anchor>

</Accordion>

<div id="best-practices" />

<Accordion title="Mejores prácticas">

Los siguientes son consejos para maximizar las conversiones de QR a la aplicación.

* Para desktop, si estás utilizando la configuración manual del código QR, crea una página separada en tu sitio web para colocar el código QR.
  * Elige un slug de URL para la página como **/app, /download-app** o **/mobile-app**.
  * Haz que la página sea visible solo para el ancho de desktop/pantalla grande.
* Para todos los anuncios:
  * Haz que el código QR de tus anuncios sea grande y de alta resolución, para que sea fácilmente escaneable.
  * Agrega las insignias **Descargar de la App Store** y **Descargar de Google Play** como activadores visuales (no como enlaces).
  * Considera agregar instrucciones sobre cómo escanear el código QR.
* ¿Ya usas OneLink? En tus *otros* OneLinks personalizados siendo utilizado en correos electrónicos, etc., agrega un parámetro **af\_web\_dp** con el valor siendo la URL a la página que contiene el código QR. Esto envía a los usuarios de desktop a hacer clic en el enlace a una página web en lugar de a la tienda de aplicaciones.

  [![](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)

</Accordion>

## Preguntas frecuentes

En esta sección, puedes encontrar una lista de preguntas frecuentes sobre QR codes.

<div id="qr-with-long-links-vs-short-links---is-there-any-difference" />

<Accordion title="Creación de QR code con enlaces largos vs. enlaces cortos: ¿hay alguna diferencia?">

Tu QR code funcionará tanto con una URL larga como con una corta. Sin embargo, si usas una URL corta, podrás actualizar los parámetros y el comportamiento del enlace desde el Dashboard de OneLink (en la sección Link Management o Bulk Links) sin necesidad de sustituir el QR code publicado, ya que la propia URL corta no cambia.

* **URL cortas:** Si cambias los parámetros en la configuración de la URL corta, el QR code sigue siendo el mismo. No necesitas volver a publicarlo.
* **URL largas (p. ej., Smart Script):** Si cambias los parámetros de una URL larga, el QR code también cambia. Una vez que lo hayas publicado, no podrás actualizar el contenido de la URL de forma remota; tendrás que generar y distribuir un nuevo QR code.

**Consejo:** Crear un QR code con una URL corta te permite modificar más adelante los parámetros y el comportamiento del enlace sin tener que regenerar el QR code.

</Accordion>

<div id="can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example" />

<Accordion title="¿Puedes crear un QR code y cambiar después el comportamiento asociado, por ejemplo tras imprimir el QR?">

Sí, puedes hacerlo si el QR code se basa en una URL corta de OneLink que puedes editar (por ejemplo, una creada mediante la IU de OneLink). Un **QR code es una representación visual de la URL que hay detrás**.  Si cambias la propia URL, se creará un nuevo QR code correspondiente (p. ej., el QR code de mike.onelink.me/123A/shorturl es distinto del QR code de mike.onelink.me/123A/example).

Sin embargo, como una URL corta de OneLink es una URL con hash, sus parámetros y reglas de redirección se configuran en el backend y no son visibles en la URL. Esto significa que puedes mantener la misma URL visible y el mismo QR code mientras editas su configuración en el backend.

</Accordion>

<div id="what-appsflyer-options-are-available-for-generating-qr-codes" />

<Accordion title="¿Qué opciones de AppsFlyer están disponibles para generar QR codes?">

Tienes las siguientes opciones:

* **A través del Dashboard de AppsFlyer → IU de OneLink:**
  * Genera automáticamente un QR code al crear un enlace
  * Configuración dinámica del código QR
  * Se puede exportar como SVG o PNG
  * Basado en una URL corta
* **QR code de OneLink API v2:**
  * Siga las <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#qr-codes">instrucciones del código QR de Smart Script</Anchor>.
* **Creación masiva de códigos QR (a través de la página Enlaces masivos):**
  * Para configurar un código QR para la conversión de QR a aplicación:
  * Se puede exportar como SVG o PNG
  * Admite un nombrado de archivos contextual
  * Basado en URL cortas
* **Integración con Smart Script V2.1+**
  * Basado en URL largas generadas dinámicamente
  * Los códigos QR se crean en consecuencia
  * Ir al anuncio con el código QR.

</Accordion>

<div id="can-you-bulk-create-qr-codes" />

<Accordion title="¿Se pueden crear códigos QR de forma masiva?">

Sí. Podrás hacer lo siguiente:

* Una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor> configurada.
* Para atribución: <Anchor target="_blank" href="/marketers/es/docs/integrate-the-appsflyer-sdk">El SDK de AppsFlyer ya está integrado</Anchor> en cada una detus aplicaciones móviles.

</Accordion>

<div data-zendesk-anchors="converting-mobile-nonmobile-and-offline-traffic-into-mobile-app-users=conversi%C3%B3n-del-tr%C3%A1fico-m%C3%B3vil-no-m%C3%B3vil-y-offline-en-usuarios-de-aplicaciones-m%C3%B3viles h_01HKWVMKP3QT59EXPHQEPHW8K9=conversi%C3%B3n-del-tr%C3%A1fico-m%C3%B3vil-no-m%C3%B3vil-y-offline-en-usuarios-de-aplicaciones-m%C3%B3viles h_01HKWWQXVC11E8M3NV3A03SWYD=qr-to-app-conversion manual-qr-code-setup=configuraci%C3%B3n-manual-del-c%C3%B3digo-qr h_01HKWWQXVCB96WDMBSE9WH9ZC5=configuraci%C3%B3n-manual-del-c%C3%B3digo-qr h_01HKWVMKP3R5C5FPH010ZJZAHS=customize-qr-code h_01HKWVMKP3XTF6NNPNM8J00NWD=measure-qrtoapp-conversions h_01HKWVMKP3P6FNRPP1X7ZTNH10=best-practices qr-code-%E2%80%93-faq=preguntas-frecuentes h_01K42Q4QQVNQ4579CCM7QF7MQS=preguntas-frecuentes qr-with-long-links-vs-short-links-%E2%80%93-is-there-any-difference=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVKGQZKAS1PZ3B9H20=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVTV0KP280D15JF7NB=can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example h_01K42Q4QQVV1RZZXZK2Y9W8R58=what-appsflyer-options-are-available-for-generating-qr-codes h_01K42Q4QQVZF4H8FYZCTJPR0RX=can-you-bulk-create-qr-codes" />

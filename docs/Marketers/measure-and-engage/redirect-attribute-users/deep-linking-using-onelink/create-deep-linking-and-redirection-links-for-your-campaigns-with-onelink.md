---
title: Crea un enlace de OneLink para tus campañas
metadata:
  keywords:
    - Marketers
    - onelink
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2016-05-22T10:03:37Z'
  edited_at: '2026-11-03T13:55:20Z'
  id: 208874366
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/208874366
---
> **En resumen:** Crea enlaces de OneLink que brinden a los usuarios exactamente la experiencia que deseas que tengan. Los usuarios que hacen clic en el enlace se redirigen a la tienda de aplicaciones, a la URL web o a la aplicación correctas, y se atribuyen a la fuente de medios.

<div id="onelink-links-and-experiences" />

## Enlaces y experiencias de OneLink

<Embed title="Crea un enlace de OneLink para tus campañas" typeOfEmbed="youtube" url="https://www.youtube.com/embed/KZBrxGEjVUE" providerUrl="https://www.youtube.com" />

Tus clientes interactúan con tu marca a través de diferentes puntos de contacto online y offline. No importa de dónde procedan tus usuarios, puedes crear un enlace que les proporcione la experiencia perfecta, desde el clic hasta la instalación de la aplicación, pasando por deep linking hasta deferred deep linking.

Los pasos necesarios para configurar un enlace se describen en detalle en la sección a seguir, pero básicamente incluyen lo siguiente:

* Selección de una experiencia de usuario
* Configuración general
* Configuración específica de la experiencia
* Configuración de deep linking y redireccionamientos
* Configuración de parámetros adicionales

<div id="create-onelink-links-in-onelink-management" />

<div id="create-onelink-links-from-your-ai-tool" />

<div id="create-a-onelink-link" />

## Crear un enlace de OneLink

| **¿Quién está involucrado?**<ul><li>Solo se requiere un marketer para crear enlaces de OneLink con una experiencia que redirecciona a los usuarios a las tiendas de aplicaciones, la URL web o, una vez configurada la plantilla para abrir la aplicación con Android App Links e iOS Universal Links, a la página de inicio de la aplicación.</li><li>Para agregar deep linking y la funcionalidad de deferred deep linking a los enlaces, se requiere tanto un marketer como un desarrollador de Android/iOS.</li></ul> |
| --- |
| **Prerrequisitos**<ul><li>Una cuenta de AppsFlyer con una aplicación como mínimo.</li><li>Una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">plantilla de OneLink</Anchor> en la que basar tus enlaces.</li><li>Para la atribución: <Anchor target="_blank" href="/marketers/es/docs/integrate-the-appsflyer-sdk">El SDK de AppsFlyer ya debe estar instalado</Anchor> en cada una de tus aplicaciones móviles.<ul><li>Si el SDK aún no está instalado en tus aplicaciones, aún se puede crear un enlace de redireccionamiento que funcione, pero no se podrá medir las instalaciones en tu dashboard, deep link o deferred deep linking.</li></ul></li></ul> |
| **Tiempo requerido**<br /><br />30 minutos para la mayoría de los enlaces, pero aproximadamente 3 horas para los enlaces que requieren la función de deep linking o deferred deep linking. |
| **Resultado**<ul><li>Un enlace que envía a los usuarios a la tienda de aplicaciones, página web o aplicación correctas en función de su dispositivo, y les da exactamente la experiencia que deseas que tengan.</li></ul> |

> 👍 **Tip**
>
> **Crea enlaces de OneLink con tu herramienta de IA**
>
> También puedes crear enlaces de OneLink describiéndolos en lenguaje natural en una herramienta de IA conectada al <Anchor target="_blank" href="/marketers/es/docs/beta-appsflyer-mcp">MCP de AppsFlyer</Anchor><Anchor target="_blank" href="/marketers/es/docs/beta-appsflyer-mcp">.</Anchor> Por ejemplo: «Crea un enlace para nuestro boletín por correo electrónico del Black Friday que abra la página de ofertas en la aplicación». La IA asigna tu solicitud a los parámetros correctos, te muestra los detalles del enlace y solo crea el enlace cuando lo apruebas. Los enlaces se crean a partir de una plantilla de OneLink existente. <Anchor target="_blank" href="/marketers/es/docs/beta-appsflyer-mcp#onelink-management">Saber más</Anchor>

**Para crear un enlace de OneLink con una experiencia de usuario específica:**

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Administración de OneLink**.
2. Selecciona la opción **Plantilla de OneLink** para agregar un enlace personalizado.
3. Haz clic en **Añadir enlace**.
4. Selecciona la [experiencia](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#experiences) que quieres crear para tus usuarios.
5. Selecciona una fuente de medios o introduce una fuente de medios personalizada. Esta es la fuente de medios en la que se muestran los datos en AppsFlyer. La fuente del medio está incluida en tu enlace con el valor del parámetro `pid`.

   <div id="note" />

   > 📘 **Nota:**
   >
   > AppsFlyer bloquea los enlaces de atribución que usan nombres de <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#srns-integradas-con-appsflyer">SRN</Anchor> reservados como valores de PID en fuentes de medios de medios propios, como el correo electrónico y los SMS. Esta restricción no se aplica a las ASRNs.

6. Haz clic en **Siguiente**.
7. Completa la [configuración general](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings).
8. Haz clic en **Siguiente**.
9. [Opcional] Completa los procedimientos pertinentes a la experiencia de usuario que estás creando:

   

| Experiencia | Opciones de procedimiento |
| --- | --- |
| <ul><li>Social-to-app</li><li>Texto a aplicación</li><li>Referencia a aplicación</li><li>Enlace personalizado</li></ul> | <ul><li>[Vista previa de redes sociales](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Landing page de redes sociales](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li></ul> |
| Correo electrónico a aplicación | Si utilizas un ESP, sigue las <Anchor target="_blank" href="/marketers/es/docs/email-service-provider-esp-integration-guide">instrucciones de integración ESP</Anchor>. |
| Aplicación a aplicación | Puedes crear enlaces dinámicos que funcionen en varias aplicaciones a través de <Anchor target="_blank" href="/marketers/es/docs/cross-promotion-attribution-for-marketers">cross-promotion</Anchor>. |
| Referencia a aplicación | <ul><li>[Vista previa de redes sociales](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Landing page de redes sociales](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li><li>Puedes crear dinámicamente enlaces de referral-to-app a través del SDK en tu aplicación mediante la <Anchor target="_blank" href="/marketers/es/docs/user-invite-attribution">integración de la invitación de usuarios</Anchor>.</li></ul> |

10. Haz clic en **Siguiente**.
11. [Opcional] En **Deep linking and redirection**, completa la [configuración de Deep Linking/Deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking). Omite esta sección si este enlace no está destinado a deep linking.
12. [Opcional] En **Deep linking and redirection**, cambia la [configuración de la redirección](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection). Omite esta sección si la configuración de redireccionamiento de la plantilla de OneLink es correcta.
13. Haz clic en **Siguiente**.
14. En **Additional parameters**, [añade parámetros predefinidos o personalizados](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#additional-parameters) a tu enlace para un análisis más granular. <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre los parámetros de atribución</Anchor>
15. Haz clic en **Generar enlace**.
16. Asegúrate de que tu <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">Lista de permitidos de redireccionamiento de dominio</Anchor> se actualiza con todos los dominios a los que deseas redireccionar a los usuarios.

<div id="experiences" />

<Accordion title="Experiencias">

Puedes crear enlaces para las siguientes experiencias de usuario:

* **Social-to-app**: Envuelve a tus usuarios en las redes sociales y envíalos desde las publicaciones de las redes sociales a tu aplicación.
* **App-to-app**: Envía a los usuarios a tu aplicación a través de anuncios que ven en otras aplicaciones.
* **QR-to-app**: Utiliza los QR codes para impulsar las instalaciones de aplicaciones haciendo que los usuarios escaneen un código QR en puntos clave durante su experiencia de cliente offline. También puedes colocar QR codes en tu sitio web de ordenador o en anuncios de TV y CTV para dirigir a los usuarios a tu aplicación.
* **Email-to-app**: Utiliza los proveedores de servicios de correo electrónico (ESP) para interactuar con los usuarios por correo electrónico y enviarlos desde su bandeja de entrada a tu aplicación.
* **Text-to-app**: Crea enlaces para tus campañas de SMS y mensajería e interactúa con los usuarios a través de mensajes de texto.
* **Referral-to-app**: Crea enlaces de invitación de usuario que permitan a los usuarios o personas influyentes invitar a otras personas a tu aplicación o compartir contenido específico en la aplicación, por ejemplo, un artículo.
* **Enlace personalizado**: Para los viajes de usuario que no se ajustan a una de las experiencias mencionadas anteriormente, puedes crear un enlace personalizado de OneLink. Entonces, no importa de dónde provengan tus usuarios, ya sea a través de ordenadores o dispositivos móviles, online u offline, medios propios o pagados, puedes enviarlos fácilmente al lugar correcto.

</Accordion>

<div id="general-settings" />

<Accordion title="Configuración general">

La configuración general es una sección del proceso de creación de enlaces de OneLink que se aplica a todas las experiencias.

**Para completar la configuración general**:

1. [Opcional] Cambia el nombre de la fuente de medios.
2. [Opcional] Cambia el nombre de la campaña.
3. [Opcional] Activa el **Retargeting** si planeas utilizar este enlace para dirigirte a los usuarios existentes.

   Esto te permite ver los re-engagements que ocurrieron cuando los usuarios hicieron clic en tu enlace personalizado.

   Los usuarios existentes que hacen clic en los enlaces que no son de retargeting (UA) también inician la aplicación, y tienen la misma experiencia de usuario. Sin embargo, sus re-engagements se registran como sesiones habituales, lo que significa que es imposible medir el éxito de la campaña de medios.

   <div id="important" />

   > 🚧 **¡Importante!**
   >
   > Para que el retargeting funcione, también debes habilitar el retargeting para la aplicación.

4. [Opcional] Activa **Ignorar usuarios activos para el retargeting** y selecciona la ventana de inactividad.  
   Esto agrega el parámetro af\_inactivity\_window=[número de días] a tu enlace, y todos los usuarios activos durante el período se ignoran para el retargeting.
5. Establece la ventana de re-engagement para determinar el período de tiempo posterior al re-engagement, donde los eventos in-app del usuario se atribuyen a la fuente de medios de retargeting.
   * Puede establecer el valor en días (1-90), horas (hasta 23) o incluso durante toda la vida.
   * La ventana de reengagement se agrega al enlace en el parámetro af\_reengagement\_window.
6. [Opcional] En la subsección **Marca del enlace**:
   * Selecciona un dominio diferente para reflejar tu marca. <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">Saber más</Anchor>
   * <span id="url-id"></span>Edita el ID de URL para resaltar la oferta de la campaña. El ID de URL debe tener un máximo de 50 caracteres y puede ser una combinación de letras y números. Por defecto, tiene 8 caracteres.

<div id="enable-retargeting-for-the-app" />

#### Habilitar el retargeting para la aplicación

Si nunca se habilitó el retargeting para la aplicación, debes hacerlo una vez. <Anchor target="_blank" href="/marketers/es/docs/app-settings#configuración-de-atribución">Saber más</Anchor>

**Para configurar el retargeting a nivel aplicación:**

1. En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Configuración de la aplicación**.
2. En la sección **Atribución**, habilita **Atribución de re-engagement**.
3. Haz clic en **Guardar configuración.**

</Accordion>

<div id="social-media-preview-og-tags" />

<Accordion title="Vista previa de redes sociales: etiquetas OG">

Cuando se comparte un enlace, las etiquetas de gráfico abierto (OG) se utilizan para generar una vista previa con un título, una descripción y una imagen.

Estas etiquetas OG se pueden tomar automáticamente de la URL web o de la tienda de aplicaciones a la que estás redirigiendo. Sin embargo, a veces este método de generar una vista previa falla. Por lo tanto, te recomendamos que configures las vistas previas de tus redes sociales en OneLink, ya sea usando la interfaz de usuario de OneLink o, para los enlaces no creados en la interfaz de usuario de OneLink, agregando parámetros de etiqueta OG a tu enlace.

**Para crear tu propia vista previa de redes sociales en la interfaz de usuario de OneLink:**

1. En tu editor de enlaces personalizados de OneLink, ve a la sección **Compartir en las redes sociales**.
2. En la sección **Social media preview** , selecciona **Default preview (from website/store)** para usar las etiquetas OG de tu URL de destino, o **Custom preview (image and tags)** para configurar las tuyas.
3. Si has seleccionado **Custom preview (image and tags)**, introduce:
   * Título
   * Descripción
   * URL de la imagen
4. [Opcional] Revisa el campo **Template favicon**.
   * Aquí se muestra el favicon configurado en la <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#h_favicon">configuración de la plantilla</Anchor> de OneLink. Se muestra automáticamente en las vistas previas de enlaces en las plataformas compatibles.
   * Para cambiar el favicon, ve a la <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#h_favicon">configuración de tu plantilla</Anchor>.
   * Si no se muestra ningún favicon, es que aún no se ha configurado ninguno en la plantilla. Aun así, puedes usar Custom preview sin un favicon.

**Para agregar parámetros de etiqueta OG a tu enlace** (si no se creó en la interfaz de usuario de OneLink):

* Agrega los siguientes parámetros obligatorios:
  * af\_og\_title (hasta 40 caracteres)
  * af\_og\_description (hasta 300 caracteres)
  * af\_og\_image

<div id="note-1" />

> 📘 **Nota**
>
> * Puedes agregar los parámetros de etiqueta OG a tu enlace fuera de la interfaz de usuario de AppsFlyer.
> * Si agregas etiquetas OG separadas para X (anteriormente Twitter), anularán la vista previa normal de AppsFlyer.

</Accordion>

<div id="social-app-landing-page" />

<Accordion title="Landing page de redes sociales">

<div id="important-1" />

> 🚧 **¡Importante!**
>
> Los iOS Universal Links ahora son compatibles con Meta Ads.
>
> * Como Meta ahora <Anchor target="_blank" href="/marketers/es/docs/meta-ads-faq#are-ios-universal-links-and-android-app-links-supported-in-meta-ads">admite universal links</Anchor>, ya no se requiere una landing page de redes sociales para los anuncios de pago de Meta que admiten enlaces universales.
> * Se necesita una landing page de aplicaciones de redes sociales para las publicaciones propias (anuncios no pagados).

Las aplicaciones de redes sociales pueden romper la experiencia de los usuarios existentes que utilizan Universal Links. Esto puede superarse de la siguiente manera:

* [**Recomendado**] Crear una landing page de redes sociales.  
  Al crear una landing pages de aplicaciones de redes sociales, recomendamos que te asegures de tener configurado un esquema URI.**Nota:** X (antes Twitter) no es compatible con esquemas de URI para iOS. Se debe usar una página de destino de una aplicación social con enlaces universales para evitar problemas al abrir la aplicación.
* [Alternativa] <Anchor target="_blank" href="/marketers/es/docs/onelink-troubleshooting-and-faq#deep-linking-forzado">Forzar la apertura de la aplicación</Anchor> usando el parámetro `af_force_deeplink=true`.  
  **Nota**: Este parámetro se habilita automáticamente para Kakaotalk, Naver, Naver-Blog, Chrome, Weibo y X.

Con una landing page de redes sociales, los usuarios que hacen clic en anuncios en aplicaciones de redes sociales son redireccionados a una página de aterrizaje generada por AppsFlyer. A partir de ahí, pueden tener deep links o continuar instalando la aplicación.

AppsFlyer proporciona una variedad de plantillas de landing pages de aplicaciones de redes sociales. Las posiciones de los elementos en las plantillas son fijas, pero los elementos en sí se pueden personalizar, incluida la imagen de fondo o el color, los títulos, textos, imágenes, botones, etiquetas y más.

La landing page se puede utilizar con las siguientes aplicaciones de redes sociales:

* Instagram
* Facebook/Facebook Messenger (**Nota**: Para Facebook y Facebook Messenger, si se configuran tanto el esquema URI como la landing page, la landing page de la aplicación social no se muestra).
* LinkedIn
* Pinterest para iOS
* Snapchat
* X (antiguo Twitter)
* WeChat

**Experiencia de usuario**

Cuando el usuario interactúa con el CTA en la landing page:

* **Si la aplicación está instalada**: cuando el usuario hace clic se inicia la aplicación.
* **Si la aplicación NO está instalada**: se lleva al usuario a la tienda de aplicaciones correspondiente. Tras la instalación, es posible diferir el Deep Linking del usuario (se explica en [Deep Linking y Deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)).

<div id="note-2" />

> 📘 **Nota**
>
> Las landing pages de las aplicaciones de redes sociales solo admiten la URL corta de OneLink.

<div id="to-use-the-social-app-landing-page" />

#### **Para usar la landing page:**

1. Configura la landing page como se describe en la siguiente sección.
2. Registra la URL **corta** de OneLink generada.  
   La landing page de la aplicación de redes sociales no funciona con URL largas de OneLink.
3. Publica la URL corta de OneLink en la aplicación de red social.

La atribución se determina en función de tus ajustes de atribución.

<div id="to-set-up-the-social-apps-landing-page" />

#### **Para configurar la landing page, debes hacer lo siguiente:**

1. En la configuración de enlaces personalizados, ve a la sección **social-to-app**.
2. En la sección **Landing page de la aplicación de red social**, haz clic en **Crear landing page**.  
   Se abre una ventana para elegir una plantilla de landing page.  
   <Image align="center" alt="" src="https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg" />
3. Para elegir una plantilla, desplaza el cursor sobre la plantilla seleccionada y haz clic en **Crear**. **Consejo**: Coloca el cursor sobre el icono 🛈 de una plantilla para ver en qué casos se debe usar. Para Instagram, se recomiendan Clustered Poster y ShowAndTell.
4. Personaliza todos los elementos en la creatividad de la landing page. Para hacerlo, selecciona los elementos por nombre o haz clic en ellos en la imagen de vista previa.    
   **Consejo**: Guarda tus textos en caso de que reemplaces la plantilla creativa.
5. Reemplaza todas las imágenes de la plantilla con tus propias imágenes.  
   1. Ingresa las URLs de las imágenes, incluida la extensión, por ejemplo, `https://example.com/image.png`.
   2. Utiliza uno de los siguientes tipos de archivos: jpeg, jpg, png.   
      **Nota**: el formato webp no es compatible.
   3. Las recomendaciones para las imágenes son:

| Tipo de imagen de la plantilla | Tamaño máximo del archivo de imagen | Proporción de imagen |
| --- | --- | --- |
| Colección | 300 KB | 16:9 (horizontal) |
| <ul><li>Trapecio</li><li>Carousel</li><li>ShowAndTell</li></ul> | 300 KB | 1:1 |
| <ul><li>Flyer</li><li>Póster</li><li>Blurry poster</li><li>Póster agrupado</li></ul> | 300 KB | 9:16 (vertical) |

   4. Si una o más imágenes no son una URL exacta, se mostrará un error y no podrás revisar la creatividad.  

      <Image align="center" alt="" src="https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png" />
6. Para revisar la creatividad de la landing page, haz clic en **Revisar**.  
   Si es necesario realizar cambios, haz clic en**Volver al editor**.  

   <Image align="center" alt="" src="https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png" />
7. Para guardar tu landing page, haz clic en **Listo**.  
   **Importante**: Las creatividades de landing pages nuevas/actualizadas solo se aplican después de generar/actualizar el enlace personalizado.
8. [Opcional] Para editar tu landing page, haz clic en **Editar landing page de la aplicación de redes sociales**.

</Accordion>

<div id="deep-linking-and-deferred-deep-linking" />

<Accordion title="Deep Linking y Deferred Deep Linking">

Deep linking significan que vuelves a redireccionar a los usuarios de tu aplicación existente y los envías directamente a una experiencia específica (por ejemplo, una página específica) dentro de tu aplicación, sin ser enviado primero a la tienda de aplicaciones o a la página de inicio de la aplicación. Estos usuarios se atribuyen mediante la atribución de retargeting.

Deferred Deep Linking significa que ofreces a los nuevos usuarios una experiencia de deep linking similar a la de los usuarios existentes. Pero su flujo de usuario consiste en que, en primer lugar, los nuevos usuarios se envían a la tienda de aplicaciones y, después de descargar e iniciar la aplicación, se envían a la experiencia o página específicas.

<div id="note-3" />

> 📘 **Nota**
>
> La configuración de deep linking y deferred deep linking requiere a tus desarrolladores de Android e iOS.

**Para configurar deep linking y deferred deep linking para dirigir a los usuarios a una experiencia específica en la aplicación:**

1. Contacta a tus desarrolladores de iOS y Android para planificar el **deep\_link\_value** para tus enlaces.
   * **Deep\_link\_value** es el nombre del valor del contenido in-app específico al que se dirigirá a los usuarios. Los desarrolladores implementan el comportamiento deseado de deep\_link\_value en el código.
   * Los desarrolladores implementan el comportamiento deseado en el código. Comparte la guía para que comprendan el flujo técnico y vean ejemplos:
     * Para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Deep Linking Y Deferred deep linking</Anchor> de usuarios nuevos o existentes, con o sin tu aplicación.  
       **Consideraciones para UDL:**
       * Requiere el SDK V6.1 o posterior.
       * La ventana retrospectiva de clics puede tardar hasta 15 minutos.
     * **Nota**: Los clientes que ya usan OneLink para deep linking pueden estar usando los métodos antiguos para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_gcd_legacy">iOS</Anchor>, en lugar de UDL.

       <div id="tips" />

       > 📄 **Consejos**
       >
       > El **deep\_link\_value** se puede basar en el SKU de un producto, el ID de publicación de redes sociales, la ruta URL o cualquier otro valor.
       >
       > Es importante trabajar con tus desarrolladores para llegar al mejor sistema a largo plazo para el **deep\_link\_value** y cualquier otro parámetro o valor. Esto minimizará las actualizaciones adicionales de la aplicación. Habla con tu desarrollador sobre el uso de valores dinámicos, para generar muchos deep links diferentes que van a diferentes contenidos dentro de la aplicación, **sin necesidad de cambiar el código de la aplicación cada vez.**
       >
       > Por ejemplo, se eligió el **deep\_link\_value** de un tipo de fruta y los desarrolladores hicieron que los valores fueran dinámicos. Esto significa que puedes introducir cualquier fruta sin necesidad de más trabajo por parte de tu equipo de desarrollo.
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=apples...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=bananas...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month&deep_link_value=peaches...`

2. Después de recibir la confirmación de los desarrolladores de que la aplicación se comporta según los parámetros y valores seleccionados, en la sección **Deep linking y redireccionamiento** de la página de configuración del enlace, introduce el **Valor de deep linking** según lo acordado con los desarrolladores.
3. [Opcional] Si tus deep links requieren más de una experiencia en la aplicación (por ejemplo, si quieres dirigir a los usuarios a un producto y ofrecerles un descuento por separado), puedes agregar un **Valor adicional de deep linking** (que utiliza el parámetro deep\_link\_sub1) a la carga útil de datos de deep linking. Puedes agregar más parámetros de deep linking (deep\_link\_sub2-10) en la sección **Parámetros adicionales** .
   1. Contacta a tus desarrolladores de iOS y Android para definir los valores.
   2. Los desarrolladores implementan el comportamiento deseado en el código. Comparte las guías de OneLink con tus desarrolladores para que comprendan el flujo técnico y vean ejemplos.

      <Tabs>
      <Tab title="Android">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_overview">Instrucciones para desarrolladores de Android</Anchor>

      </Tab>

      <Tab title="iOSUnity">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_overview">Instrucciones para desarrolladores de iOS</Anchor>

      </Tab>
      </Tabs>

   3. En **Parámetros adicionales**, agrega parámetros personalizados **deep\_link\_sub2-10** y valores según se requiera, de acuerdo con lo que has decidido con los desarrolladores.

<div id="note-4" />

> 📘 **Nota**
>
> Cuando los desarrolladores implementan los parámetros y valores dinámicos, el marketer puede usar la API de OneLink para generar automáticamente miles de enlaces personalizados. <Anchor target="_blank" href="/marketers/es/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">Saber más</Anchor>

</Accordion>

<div id="redirection" />

<Accordion title="Redireccionamiento">

**Para enviar a los nuevos usuarios a una landing page, en lugar de a la tienda de aplicaciones**:

1. En la sección **Deep linking y redireccionamiento** de la página de configuración del enlace, en «Cuándo la aplicación no está instalada», selecciona enviar a los usuarios a una URL diferente.  
   Las URL personalizadas de Android e iOS redireccionan a los usuarios nuevos a la landing page que especifiques.   
   **¡Nota!** Si tu plantilla de OneLink ya tiene un valor establecido para una URL personalizada, estas URLs de enlaces personalizados la anulan.
2. También puedes enviar a los nuevos usuarios a las <Anchor target="_blank" href="/marketers/es/docs/redirect-users-to-custom-app-store-product-pages">páginas de productos personalizadas de la tienda</Anchor>.

</Accordion>

<div id="additional-parameters" />

<Accordion title="Parámetros adicionales">

Es posible que desees agregar parámetros adicionales a tu enlace, como Campaña, Nombre del conjunto de anuncios, Nombre del anuncio, Canal, tus propios parámetros personalizados o <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">Parámetros del suscriptor</Anchor> 1-5. Esto permite un análisis más granular de los esfuerzos de marketing. Leer más sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">los parámetros de atribución adicionales</Anchor>.

También puedes agregar parámetros de deep linking adicionales (deep\_link\_sub2-10).

**Para agregar parámetros**:

1. En la sección **Parámetros adicionales** de la configuración del enlace, haz clic en **Agregar parámetro**.
2. Selecciona el parámetro que deseas agregar o introduce un parámetro personalizado.

</Accordion>

<div id="testing" />

<Accordion title="Pruebas">

Puedes probar si tu enlace funciona para redirigir a:

* Nuevos usuarios sin tu aplicación instalada
* Usuarios existentes con tu aplicación instalada

<div id="new-users-without-your-app-installed" />

#### Nuevos usuarios sin tu aplicación instalada

**Requisitos previos**: Un <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">dispositivo de prueba registrado</Anchor> sin la aplicación.

**Para probar tu enlace**:

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Gestión de OneLink**.
2. Desplaza el puntero sobre el icono **Acciones** del enlace que quieres probar y haz clic en **Obtener URL**.
3. Envía la URL corta o larga a tu teléfono. Puedes elegir cualquiera de las siguientes opciones:
   * Escanear el código QR con la cámara de tu teléfono o con la aplicación de escáner de QR.
   * Envia el enlace por correo electrónico o WhatsApp y abrirlo en tu móvil.  
     **Nota:** No lo pegues en las notas de iOS ni directamente en un navegador móvil. Muchas veces, el sistema operativo del dispositivo móvil no abrirá la aplicación en este contexto de manera intencional.
4. Haz clic en el enlace en tu dispositivo móvil.  
   Dependiendo de tu plataforma, deberías llevarlo a la tienda de aplicaciones o a la landing page.  
   **Nota**: Es necesario un clic real en un dispositivo móvil. Los redireccionamientos de Javascript o 301/302 no pueden activar los Universal Links ni los Android App Links. Incluso los redireccionamientos básicos fallan con estos métodos en algunos navegadores.
5. Descargar e iniciar la aplicación.
   * La aplicación debería abrirse en su pantalla de inicio.
   * Si has implementado deferred deep linking, la aplicación debe abrirse en el contenido específico en los parámetros del enlace.
6. En el **dashboard general** de AppsFlyer, búsca una nueva instalación.  
   Busca un clic y una instalación nuevos en la fuente de medios (p. ej., prueba) y el nombre de la campaña que indica en la URL.

¿El enlace no funciona como se esperaba? Echa un vistazo a las <Anchor target="_blank" href="/marketers/es/docs/onelink-troubleshooting-and-faq">preguntas frecuentes y la guía de resolución de problemas de OneLink.</Anchor>

<div id="existing-users-with-your-app-installed" />

#### Usuarios existentes con tu aplicación instalada

**Requisitos previos**: Un dispositivo Android y/o iOS con la aplicación instalada. Asegúrate de que sea la fuente y la versión de la aplicación en la que el desarrollador hizo cambios (e implementó los Universal Links, Android App Links o esquemas URI).

**Para probar tu enlace:**

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Gestión de OneLink**.
2. Haz clic en la **Plantilla de OneLink** seleccionada.
3. En la lista, selecciona el Enlace personalizado.
4. Desplaza el puntero sobre el icono **Acciones** del enlace que quieres probar y haz clic en **Obtener URL**.
5. Envía la URL corta o larga a tu teléfono. Puedes elegir cualquiera de las siguientes opciones:
   * Escanear el código QR con la cámara de tu teléfono o con la aplicación de escáner de QR.
   * Envia el enlace por correo electrónico o WhatsApp y abrirlo en tu móvil.  
     **Nota:** No lo pegues en las notas de iOS ni directamente en un navegador móvil. Muchas veces, el sistema operativo del dispositivo móvil no abrirá la aplicación en este contexto de manera intencional.
6. Haz clic en el enlace en tu dispositivo móvil.
   * La aplicación debería abrirse en su pantalla de inicio.
   * Si has implementado deep linking, la aplicación debería abrir el contenido especificado en los parámetros del enlace.
7. Ve al dashboard **general** de AppsFlyer (**Tipo de vista: Retargeting**).  
   Busca un nuevo clic/re-engagement (aplicación abierta) bajo la fuente de medios de tu enlace (por ejemplo, prueba) y el nombre de la campaña que pusiste en la URL.

¿El enlace no funciona como se esperaba? Echa un vistazo a las <Anchor target="_blank" href="/marketers/es/docs/onelink-troubleshooting-and-faq">preguntas frecuentes y la guía de resolución de problemas de OneLink.</Anchor>

</Accordion>

<div id="additional-procedures" />

## Procedimientos adicionales

<div id="create-a-custom-impression-url" />

<Accordion title="Crear una URL de impresión personalizada">

Los enlaces de impresiones personalizados te permiten lo siguiente:

* Mide las <Anchor target="_blank" href="/marketers/es/docs/about-conversion-rates#etapas-del-embudo-de-marketing-y-tasas-de-conversión-1">tasas de conversión de impresiones a clics</Anchor> de los anuncios que muestras.
* Recibir atribución por impresiones.

**Requisitos previos:** Una URL larga de OneLink que funcione. No se admiten URLs cortas.

**Quién debe participar:**

Marketers y desarrolladores web

**Para crear URLs de impresiones solo para la medición de impresiones:**

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **OneLink Management.**
2. Pasa el cursor sobre el menú Opciones, del enlace que deseas probar y haz clic en **Obtener URL**.
3. Copia la URL larga de OneLink para editarla.  
   Ejemplo: `https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
4. Reemplaza el subdominio (o todo el dominio de marca, si estás usando uno) con "impresiones".    
   Ejemplo: si estás usando un OneLink de marca con este aspecto: `https://app.alltrails.com/Waim?` cámbialo por un enlace de impresiones `https://impressions.onelink.me/Waim?`.
5. Copia la URL de impresiones y envíasela a tu desarrollador.
6. Indica a tu desarrollador web que implemente la URL de impresión en la lógica del sitio web.

Ahora tienes una URL de impresiones, que puede usarse para contar impresiones en las páginas de tu sitio web **pero no puede atribuir instalaciones nuevas**. Para ver la atribución por impresiones, sigue los siguientes pasos.

**Para usar las URLs de impresiones para la atribución:**

1. Prepara la URL de impresiones tal como se describe en los pasos anteriores.
2. Asegúrate de que la <Anchor target="_blank" href="/marketers/es/docs/measure-view-through-engagements">atribución por impresiones esté activada</Anchor>.
3. [Opcional] Si deseas cambiar el valor predeterminado de la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback</Anchor> del Día 1, agrega el parámetro `af_viewthrough_lookback` con el nuevo valor. Por ejemplo, `af_viewthrough_lookback=1d`.
4. Copia la URL de impresiones y envíasela a tu desarrollador.
5. Dile a tu desarrollador web que implemente la URL de impresión en la lógica del sitio web.

Ejemplo de URL de impresiones completa:

```http
https://impressions.onelink.me/j7rN?pid=email&c=Spring&af_viewthrough_lookback=1d
```

</Accordion>

<div id="deep-linking-post-event" />

<Accordion title="Deep linking posterior al evento">

Es posible que desees enlazar a los usuarios a actividades o páginas específicas solo después de un evento, por ejemplo:

* Iniciar sesión
* Visualizar una pantalla de inicio
* Aceptar los términos y condiciones
* Y más

**Para enlazar a los usuarios después de un evento**:

Pide a tus desarrolladores que sigan sus instrucciones para hacer deep linking a los usuarios después del evento en <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_dl_post_event">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_dl_post_event">iOS</Anchor>.

</Accordion>

<div id="deferred-deep-linking-with-ios-private-relay" />

<Accordion title="Deferred Deep Linking con iOS Private Relay">

Con el lanzamiento de iOS 15, Apple ofrece a los usuarios de iCloud+ una función llamada <Anchor target="_blank" href="https://www.macworld.com/article/348965/icloud-plus-private-relay-safari-vpn-ip-address-encryption-privacy.html">Private Relay</Anchor>, que les da la opción de cifrar su tráfico de navegación web y ocultar su ubicación exacta, su dirección IP y el contenido de su tráfico de navegación. Si los usuarios optan por Private Relay, esto podría interferir con la atribución y los deferred deep linking. Es decir, una vez que un nuevo usuario sin la aplicación va a la App Store e instala e inicia la aplicación, Private Relay podría evitar que se le envíe a una página específica de la aplicación.

Para asegurarte de que el Deferred deep linking (DDL) siga funcionando como se espera, debes implementar una de las siguientes soluciones de AppsFlyer:

* **[Recomendado] Solución basada en App Clip**: crea un App Clip que te proporcione datos de atribución de usuarios y dirija a los usuarios a una experiencia de App Clip personalizada, similar a la que quieres que el DDL consiga. El clip de aplicación también puede incluir un flujo para dirigir a los usuarios desde tu App Clip a tu aplicación completa.
* **Solución basada en clipboard**: Crea una landing page que copie los datos de deferred deep linking de la URL y envíe correctamente al usuario a la aplicación. **Nota**: Esta solución no ayuda con la atribución.

<div id="app-clipbased-solution" />

<Accordion title="Solución basada en App Clip">

Esta solución combina URLs cortas de OneLink con la tecnología App Clips disponible en iOS y te permite enviar usuarios a flujos específicos en tu producto sin la necesidad de instalar la aplicación completa. La URL corta de OneLink te brinda datos de atribución de usuario y dirige a los usuarios a una experiencia de App Clip personalizada similar a la que deseas que logre el DDL. App clip también puede incluir un flujo para enviar a los usuarios desde tu App Clip a tu aplicación completa. **Nota**: Si los usuarios reinstalan la aplicación completa desde la solución basada en App Clip, es posible que AppsFlyer la reporte como una instalación orgánica. 

<div id="flow" />

#### **Flujo**

El flujo de la solución DDL basada en App Clip es el siguiente:

1. El anunciante crea un App Clip y lo agrega a una plantilla de OneLink para usuarios con Private Relay activado.
2. El usuario toca la URL de OneLink.
3. El controlador web de AppsFlyer comprueba si:
   * El dispositivo está usando iOS 15+
   * El navegador es Safari
   * El usuario tiene activado Private Relay.
4. Una vez que AppsFlyer confirme lo anterior, se le pedirá al usuario que haga clic en **Reproducir App Clip** o en **Ver en Safari**.
   * Si el usuario hace clic en **Reproducir App Clip**, se muestra una tarjeta de App Clip al usuario.
   * Si el usuario hace clic en Ver en Safari, se abre una landing page que le solicita que abra el App Clip.
5. El usuario abre el App Clip.
6. El App Clip se abre y proporciona al usuario la experiencia que han decidido el marketer y el desarrollador de la aplicación.
7. Si el App Clip incluye un flujo para dirigir a los usuarios a la aplicación completa, los usuarios se envían a la App Store para descargar la aplicación completa. Tras el inicio de la aplicación, obtienen la experiencia de usuario definida por el desarrollador.

**Requisitos previos:** AppsFlyer SDK V6.4.0+

**Para configurar la solución DDL basada en App Clip**:

1. Dile al desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#app-clip-based-solution">Instrucciones del Dev Hub de soluciones basadas en App Clip</Anchor> y crea un App Clip que proporcione la experiencia de usuario deseada. y crea un App Clip que proporcione la experiencia de usuario deseada. Esto también puede incluir un flujo para enviar a los usuarios desde tu App Clip a tu aplicación completa.
2. Crea o edita una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">plantilla de OneLink</Anchor> con <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">enlaces universales</Anchor> y [Deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking).
3. En la plantilla de OneLink, activa **Mostrar App Clip si el usuario tiene Private Relay**. No actives esto a menos que tengas un App Clip.  
   **Nota**: Al realizar cambios en una plantilla de OneLink con Universal Links, como agregar (o eliminar) la capacidad de App Clip, es posible que el archivo AASA tarde varias horas en actualizarse. Por lo tanto, es posible que los enlaces que crees basándote en la plantilla no tengan la funcionalidad actualizada de inmediato.
4. Crea un enlace personalizado basado en la plantilla de OneLink.
5. En App Store Connect, ve a la sección **App Clip Experience**, desplázate hacia abajo hasta las **URLs de la aplicación** e introduce la URL de tu plantilla de OneLink (dominio + ID de plantilla. Por ejemplo: `yourbrand.onelink.me/GrbZ`), o una URL corta de enlace personalizado específico de OneLink.  
   **Nota**: Si ingresa un enlace personalizado de OneLink, la solución basada en App Clip solo funcionará para los usuarios que toquen ese enlace específico; otros enlaces creados basados en la plantilla de OneLink no funcionarán.

</Accordion>

<div id="clipboardbased-solution" />

<Accordion title="Solución basada en el clipboard">

<div id="flow-1" />

#### **Flujo**

El flujo de la solución DDL basada en clipboard es el siguiente:

1. El anunciante crea un deferred deep link que contiene el parámetro `af_cp_lp=true`.
2. El usuario toca el deferred deep link.
3. AppsFlyer comprueba si:
   * El dispositivo está usando iOS 15+
   * El navegador es Safari
   * El usuario tiene activado Private Relay.
   * El enlace contiene el parámetro. `af_cp_lp=true`.
4. Una vez que AppsFlyer confirma lo anterior, se carga la landing page web, que contiene el ícono de la aplicación, la imagen y un CTA para obtener la aplicación de la App Store. El usuario también ve un mensaje que explica el proceso: que la URL se copia para garantizar la mejor experiencia de usuario y que se le enviará a la página específica en la aplicación.  
   <Image align="center" alt="ios_15_ip_masking__1_.png" src="https://files.readme.io/c130314c98ebd42f50feaafd752c0cea954f42c5bfd99a6dbd94daf9e48c2ff4-30151216595345.png" />
5. El usuario hace clic en **Obtener la aplicación**.
6. Se envía al usuario a la App Store para instalar la aplicación. Luego, en la primera apertura, se envía a la página de la aplicación específica.

<div id="requirements" />

#### **Requisitos**

La solución de DDL de landing pages de copiar/pegar requiere:

* El usuario que navegará por la web en Safari.
* El deferred deep link para incluir el `af_cp_lp=true`parámetro.
* AppsFlyer iOS SDK V6+.
* Tu desarrollador de aplicaciones iOS implementará un código que pegue los datos del deferred deep link en la URL desde el clipboard. Esto no forma parte del SDK de AppsFlyer.
* El usuario final debe mantener la casilla marcada (predeterminado). Si está desactivada, la URL no se copia y los deferred deep link no funcionan.

<div id="setup" />

#### **Configuración**

**Para configurar la solución DDL basada en clipboard**:

1. Dile a tu desarrollador de iOS que:
   1. Sigua las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#clipboard-based-solution">instrucciones del Dev Hub</Anchor> e integra el código requerido en el SDK de AppsFlyer.
   2. Implementa un código que pegue los datos del deferred deep link en la URL del clipboard. Esto no forma parte del SDK de AppsFlyer.
2. Agrega el parámetro `af_cp_lp=true` a tus enlaces.   
   Puedes hacerlo agregando un parámetro personalizado en la interfaz de usuario de enlaces personalizados de OneLink de AppsFlyer o simplemente agregando el parámetro a cualquiera de tus enlaces.

</Accordion>

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="examples" />

<Accordion title="Ejemplos">

**Ejemplo básico**

Mark es el marketer de un exitoso servicio de entrega de comida llamado "Feed Me". Mark apunta a los números de teléfono de sus usuarios para que descarguen las aplicaciones móviles nuevas de Feed Me en iOS y Android. Se ha planificado una campaña por SMS. Sin embargo, Mark no sabe qué usuarios tienen dispositivos Android o iOS. Tampoco sabe si tienen instalada la aplicación.

Para resolver esto, Mark envía a los usuarios un SMS que contiene una URL corta impulsada por OneLink. Cuando los usuarios reciben el SMS y hacen clic en el enlace:

* Si aún no tienen la aplicación, se les dirige automáticamente a la tienda de aplicaciones o a la página de destino correspondiente, donde les resulta fácil instalar la aplicación.
* Si ya tienen instalada la aplicación, esta se abre para ellos.

Las nuevas instalaciones y los re-engagements se atribuyen a la campaña de SMS, lo que permite a Mark comprobar el éxito de la campaña de SMS en AppsFlyer. 

**Ejemplo de deep linking**

El SMS del marketer (del ejemplo anterior) tuvo un éxito leve a la hora de lograr que los usuarios descargaran y abrieran la aplicación. Sin embargo, no muchos usuarios que hicieron clic en el enlace y abrieron la aplicación se convirtieron para realizar un pedido.

Mark decide aumentar la conversión ofreciendo una bolsa de melocotones, manzanas o aguacates gratis con cada compra. Para ello, Mark crea una experiencia fluida de deep linking para los usuarios existentes. Envía a su base de usuarios un correo electrónico detallado destacando los beneficios de estas 3 frutas saludables. 

Para cada fruta mencionada en el correo electrónico, Mark incluye un enlace con un valor de deep link con tecnología OneLink, configurado (con la ayuda de desarrolladores móviles) para:

Para resolver esto, Mark envía a los usuarios un SMS que contiene una URL corta impulsada por OneLink. Cuando los usuarios reciben el SMS y hacen clic en el enlace:

* Si ya tienen instalada la aplicación, se los dirigirá directamente a la página de la fruta correspondiente.
* Si aún no tienen la aplicación, se les dirige a la tienda de aplicaciones o a la página de destino correspondiente, según su dispositivo. Y luego, una vez que descargan y abren la aplicación, se les dirige directamente a la página de frutas.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| <span id="onelink-characters"></span>Caracteres de OneLink | <ul><li>La longitud total de la URL no debe superar los 2.000 caracteres.</li><li>Nombre del enlace y fuente de medios: no deben superar los 150 caracteres</li><li>El ID de URL corta no debe superar los 50 caracteres.</li><li>Ver <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#special-characters">características y limitaciones</Anchor> adicionales del parámetro de redirección.</li></ul> |
| <span id="maximum-links"></span>Máximo de enlaces | El número máximo de enlaces de OneLink que puedes crear en AppsFlyer es de 120.000 por cuenta. |
| <span id="posting-onelink-urls-in-web-pages"></span>Publicar URL de OneLink en páginas web | Usando`target="_blank"`  en la etiqueta href HTML no da lugar a una redirección a Google Play o App Store. Si la URL de OneLink se coloca dentro de una etiqueta html **a** con el atributo **target="\_blank"**, se abre una página en blanco en Chrome en Android e iOS. Esto afecta la funcionalidad de OneLink. Asegúrate de que la etiqueta **a** no incluya el atributo de destino. |
| <span id="agencies"></span>Agencias | Las agencias no pueden usar plantillas o enlaces de OneLink. Son solo para fuentes de medios personalizadas/propias. |
| <span id="ad-networks"></span>Redes publicitarias | Las agencias no pueden usar plantillas o enlaces de OneLink. Son solo para fuentes de medios personalizadas/propias. |
| <span id="social-media-preview-image"></span>Imagen de vista previa de redes sociales | <ul><li>Si el tipo de imagen no es compatible con la plataforma de redes sociales, no se muestra.</li><li>Para WhatsApp, la imagen no puede superar los 300 KB.</li></ul> |
| <span id="desktop"></span>Ordenador | Cuando configuras la URL o la plantilla de OneLink para redireccionar a los usuarios de ordenador a una URL diferente, la URL web se agrega al enlace del parámetro `af_web_dp`. Cuando el enlace contiene `af_web_dp`, AppsFlyer no registra ningún clic cuando proviene de un ordenador. |
| <span id="af_enc_data"></span>af\_enc\_data | No se admite en las URLs de impresiones. |
| <span id="android-social-apps-webview-deep-linking-redirection"></span>Aplicaciones de redes sociales de WebView | Debido a cambios recientes en varias aplicaciones sociales de Android, algunos flujos de deep linking y redirección a la tienda en la vista del navegador interno (WebView) se rompieron.<br /><br />**App Links de Android**<br /><br />Los App Links de Android actualmente no son compatibles cuando se hacen clic desde dentro del navegador de la aplicación de Facebook. Usar un esquema URI en los enlaces de este flujo funciona como antes.<br /><br />**Redirección de la tienda**<br /><br />Para acomodar los cambios y volver a habilitar la redirección de la tienda, tuvimos que introducir una interacción adicional con el usuario para las siguientes aplicaciones de redes sociales de Android:<ul><li>Versiones de Facebook superiores a v420</li><li>Instagram</li><li>Facebook Messenger</li><li>Snapchat</li></ul>El nuevo flujo del usuario requiere que los usuarios de las aplicaciones anteriores hagan clic en un botón de la landing page adicional para activar la redirección a Google Play Store y otras tiendas de third-party.<br /><br />Este botón se agrega automáticamente, sin requerir ninguna acción.<br /><br />**Notas:**<ul><li>Las versiones 420 y anteriores de Facebook funcionan como antes, sin interacción adicional del usuario.</li><li>Los App Links de Facebook (usando el esquema URI) en las publicaciones de Facebook funcionan como antes, sin necesidad de interacción adicional del usuario.</li><li>Los App Links en el chat de Instagram funcionan como antes, sin interacción adicional del usuario.</li><li>En el flujo de deep linking, cuando la aplicación no está instalada, existe una limitación conocida: un mensaje pop-up de error. Este mensaje no afecta el flujo; el usuario sigue siendo enviado a la tienda como se esperaba.</li></ul> |
| <span id="onelink-link-previews-sometimes-fail-to-display-correctly-on-facebook-and-linkedin"></span>Vistas previas de enlaces de OneLink | **Descripción**  <br />Las vistas previas de enlaces de OneLink a veces no se muestran correctamente en Facebook y LinkedIn. El problema surge cuando el sitio web de destino no reconoce el `AppsFlyerBot-Previewer/1.0` user-agent en la solicitud de vista previa como procedente de un robot (o rastreador). En tales casos, el sitio web no responde con el contenido de vista previa con el etiquetado OG apropiado.<br /><br />**Solución**  <br />Puedes configurar tu landing page para tratar las páginas con el atributo `AppsFlyerBot-Previewer/1.0` user-agent como procedente de un robot por <Anchor target="_blank" href="https://moz.com/learn/seo/robotstxt">Actualización del archivo robot.txt de tu sitio web</Anchor>.<br /><br />El robot de vista previa también comprueba los parámetros de redirección de cada enlace con la lista de permitidos de redirección. Cuando un parámetro apunta a un dominio que no está en la lista, el robot ignora la URL, por lo que la vista previa permanece en blanco o genérica. Asegúrate de añadir a tu lista de permitidos de redirección todos los dominios de páginas de destino cuya vista previa esperas ver. |
| <span id="deep-linking-is-not-supported-on-android-naver-blog-app"></span>Aplicación Android Naver Blog | Los deep linking no son compatibles con la aplicación Android Naver Blog. Los usuarios serán enviados a Google Play o a la redirección web definida en el enlace. |
| <span id="chrome-browser-on-ios"></span>Navegador Chrome en iOS | Debido a un cambio en Chrome iOS, cada vez que un usuario hace clic en un enlace de esquema URI en Chrome en iOS, se muestra un pop-up que solicita a los usuarios que confirmen la apertura de la aplicación o la redirección a la App Store. |
| <span id="telegram-webview"></span>Telegram WebView | La atribución de modelado probabilístico no funciona para el engagement de usuarios en Telegram WebView (navegador de Telegram). La razón es que WebView no incluye modelos de dispositivos ni versiones de SO en sus solicitudes de engagement. |
| <span id="xiaomi-browser"></span>Navegador Xiaomi | La atribución de modelado probabilístico no funciona para el engagement de los usuarios en Xiaomi Browser. |

</Accordion>

<div data-zendesk-anchors="onelink-links-and-experiences=enlaces-y-experiencias-de-onelink h_01H8Y6DDT4M8XGAEJJVTHKHPKV=enlaces-y-experiencias-de-onelink create-a-onelink-link=crear-un-enlace-de-onelink h_01H8Y6DDT41C6JYKXET0NDRB1G=crear-un-enlace-de-onelink h_01JRX3VWTVE77QVNG37BKPKHWW=nota h_01H8Y6DDT4C543RS2BXAGS487M=experiences h_01H8Y6DDT4WZ5FKZYBX2H08MFD=general-settings h_01KY2AWC72SCQKY3XEQGW2J269=importante enable-retargeting-for-the-app=habilitar-el-retargeting-para-la-aplicaci%C3%B3n h_01H8Y6DDT4R7785X5DRES66BKJ=habilitar-el-retargeting-para-la-aplicaci%C3%B3n h_01H8Y6DDT4JT9H0R13ZNGHJ79S=social-media-preview-og-tags h_01KY2AWC72V1JR1BBGKHPDQ7AF=nota-1 h_01H8Y6DDT4PHY2F5E3GK582P51=social-app-landing-page h_01H8Y6DDT463F5569B28DD17SV=importante-1 h_01H8Y6DDT4MMD1AW6D1PNGNX5X=nota-2 to-use-the-social-app-landing-page=para-usar-la-landing-page h_01H8Y6DDT4JB4RT438MAGNNX2S=para-usar-la-landing-page to-set-up-the-social-apps-landing-page=para-configurar-la-landing-page-debes-hacer-lo-siguiente h_01H8Y6DDT4G34S3RV3ZH64XT19=para-configurar-la-landing-page-debes-hacer-lo-siguiente h_01H8Y6DDT5XNJVYW2Y8F6JWPK2=deep-linking-and-deferred-deep-linking h_01KY2AWC73CNKHAF4HV26F132E=nota-3 h_01H8Y6DDT5JR3B3DMR87JCBZ69=consejos h_01H8Y6DDT5KSBE00WWDGQ5R1AQ=nota-4 h_01H8Y6DDT58FC3HMSRZBMGZZRJ=redirection h_01H8Y6DDT5AAQ3BZD8QB9H19QB=additional-parameters h_01H8Y6DDT5B6M7CETQRD9NKX8R=testing new-users-without-your-app-installed=nuevos-usuarios-sin-tu-aplicaci%C3%B3n-instalada h_01H8Y6DDT50DH5TGVVPJPJC4MG=nuevos-usuarios-sin-tu-aplicaci%C3%B3n-instalada existing-users-with-your-app-installed=usuarios-existentes-con-tu-aplicaci%C3%B3n-instalada h_01H8Y6DDT5KDEWS40XPYGYC8HK=usuarios-existentes-con-tu-aplicaci%C3%B3n-instalada additional-procedures=procedimientos-adicionales h_01H8Y6DDT5YR8JA5YMZFPMCC2X=procedimientos-adicionales h_01H8Y6DDT58EFS8S46D1AVP3T1=create-a-custom-impression-url h_01H8Y6DDT5S4NEJMNJR4K3QMNH=deep-linking-post-event h_01H8Y6DDT58Y6CS27M2W3MHYAD=deferred-deep-linking-with-ios-private-relay h_01H8Y6DDT5A7J07KNNRWCXCBH2=app-clipbased-solution flow=flujo h_01H8Y6DDT5VDKAR89B8N6D7YMB=flujo h_01H8Y6DDT62H71A8DPG00A3ZTN=clipboardbased-solution flow::21baf6ac=flujo-1 h_01H8Y6DDT638T7C9HQHZ1CJ726=flujo-1 requirements=requisitos h_01H8Y6DDT6JGP33AWFQV6Z8FF0=requisitos setup=configuraci%C3%B3n h_01H8Y6DDT61ENGJFZ1XS28GS1T=configuraci%C3%B3n additional-information=informaci%C3%B3n-adicional h_01H8Y6DDT679SGBTSM669F9FHV=informaci%C3%B3n-adicional h_01H8Y6DDT6TX4WTP2HYRF11DZ3=examples h_01H8Y6DDT6TQYRS81BMHARB62S=traits-and-limitations" />

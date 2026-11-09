---
title: Crear una plantilla de OneLink
metadata:
  keywords:
    - template
    - Marketers
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2014-11-03T12:35:49Z'
  edited_at: '2026-09-02T00:32:43Z'
  id: 207032246
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/207032246
---
> **De un vistazo:** Crea una plantilla para sentar las bases de la lógica de redireccionamiento de todos los enlaces de OneLink que crees para tus distintas campañas de marketing. Se necesita una plantilla para crear enlaces y experiencias de usuario final.

<div id="onelink-templates" />

## Plantillas de OneLink

<Embed title="Crear una plantilla de OneLink" typeOfEmbed="youtube" url="https://www.youtube.com/embed/d4AtCJ9122Q" providerUrl="https://www.youtube.com" />

Plantilla de OneLink:

* No es un enlace en el que se pueda hacer clic para los usuarios finales; es la base para generar muchos enlaces personalizados. Por lo general, solo necesitas una plantilla por aplicación (fuera de las pruebas) para generar tantos enlaces como desees para todas tus diferentes campañas publicitarias.
* Aquí es donde registras tus decisiones sobre cómo redirigir a los usuarios en función de la plataforma de su dispositivo y si tienen instalada o no tu aplicación.
* Representa la lógica de enrutamiento en el núcleo de todos los enlaces de OneLink que creas para tus diversas campañas de marketing. Esto incluye la configuración del redireccionamiento para:
  * **Nuevos usuarios sin la aplicación instalada**: A la tienda de aplicaciones o a la URL web correcta
  * **Usuarios existentes que ya tienen tu aplicación instalada**: Abrir la aplicación mediante Android App Links, iOS Universal Links o esquemas URI. Esto implica algún trabajo de desarrollador para configurar.
  * **Nota**: La configuración de redireccionamiento para el sitio web o la tienda de aplicaciones se puede anular en el nivel de enlace.

<div id="create-a-onelink-template" />

## Crear una plantilla de OneLink

| ¿Quiénes están involucrados? | Requisitos previos | Tiempo requerido | Característica |
| --- | --- | --- | --- |
| <ul><li>Solo es necesario que un marketer configure la lógica de redireccionamiento para los nuevos usuarios que no tienen tu aplicación instalada (por ejemplo, a la tienda de aplicaciones o a la página web correctas).</li><li>Para agregar la lógica de redireccionamiento para los usuarios de aplicaciones existentes que ya tienen instalada tu aplicación (por ejemplo, para abrir la aplicación), se requieren tanto un marketer como un desarrollador de Android/iOS.</li></ul> | <ul><li>Una cuenta de AppsFlyer con una aplicación como mínimo.</li><li>El marketer debe ser un usuario administrador de AppsFlyer o tener permiso para agregar/editar plantillas de OneLink.</li></ul> | Aproximadamente 1,5 horas, trabajando junto con tus desarrolladores de Android/iOS. | Una plantilla a partir de la cual puedas crear enlaces que envíen a los usuarios a la tienda de aplicaciones, página web o aplicación correctas en función de su dispositivo. |

<div id="create-a-onelink-template-with-redirection-logic-for-new-app-users" />

<Accordion title="Crear una plantilla de OneLink con lógica de redireccionamiento para los nuevos usuarios de la aplicación">

**Para crear una plantilla de OneLink:**

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Administración de OneLink**.  
   El paquete de OneLink es una función a nivel de cuenta que te permite crear plantillas de OneLink y sus enlaces personalizados para todas tus aplicaciones.  
   [![](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png) **Nota**: Si no has creado ninguna plantilla, se abre un asistente de onboarding. Sigue las instrucciones del asistente e ignora el resto de este procedimiento.
2. Haz clic en el icono del menú > **Agregar plantilla de OneLink**.  
   Se abre la página de configuración de la plantilla de OneLink.  
   <Image align="center" alt="OneLink_template_page_en-us.png" src="https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png" />
3. En el campo **Nombre de la plantilla de OneLink**, introduce un nombre.

   <div id="note" />

   > 📘 **Nota**
   >
   > * Un buen nombre de plantilla de OneLink incluye el **nombre de la aplicación (por ejemplo, feed\_me) o el** caso de uso o la experiencia representados por OneLink (por ejemplo, pre\_launch\_landing\_page).
   > * El nombre no debe incluir el nombre de la campaña o del canal ni la fuente de medios (ya que no es el enlace del usuario final, sino la plantilla subyacente para crear muchos enlaces), o el nombre de la plataforma (Android, iOS, ya que las multiplicidad de plataformas suele ser el motivo para usar una plantilla de OneLink).
   > * Este nombre de plantilla solo se usa internamente. No afecta a tus datos de atribución de marketing y los usuarios no lo ven.

4. En el campo **Subdominio** , introduce el nombre de tu <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#subdominio">subdominio</Anchor>.
   * Elige un subdominio que coincida con tu marca. Por ejemplo, si tu sitio web es www.abcd.com, elige abcd como subdominio.
   * Los usuarios verán este subdominio como parte de la URL del enlace. Por ejemplo: `https://abcd.onelink.me/RPsv/37e5cd36`.
   * El subdominio no se puede cambiar una vez que se creen enlaces personalizados basados en esta plantilla.
   * Solo usa letras minúsculas, números o guiones (-).
   * OneLink también admite dominios totalmente personalizados, que pueden ayudarte a mejorar el rendimiento de la campaña y aumentar la exposición de la marca. <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">Saber más</Anchor>
5. Selecciona tu aplicación para Android, iOS o ambas.
6. (Opcional) Activa los enlaces cortos seguros si quieres evitar que se secuestren tus enlaces con parámetros adicionales. **Para activar los enlaces cortos seguros:**

   En **Secure Shortlinks**, activa **Don't attribute clicks with added parameters**.

   Esto significa lo siguiente: una vez activada, si alguien añade un parámetro a un enlace corto creado a partir de esta plantilla, ese clic no se atribuirá. El usuario se redirige según la configuración de redirección de la plantilla; solo se ve afectada la atribución.  

   **Ejemplo:**

| Link | Resultado |
| --- | --- |
| `[subdomain].onelink.me/[template_id]/[shortlink_id]` | Se atribuye como de costumbre. |
| `[subdomain].onelink.me/[template_id]/[shortlink_id]?param=value` | Se añadió un parámetro, así que ese clic no se atribuye. |

   **Notas:**

   * Esta configuración se aplica a nivel de plantilla. No puedes activarla ni desactivarla para enlaces individuales.
   * En las plantillas creadas antes del lanzamiento de esta función, la opción está desactivada. Actívala si lo deseas. En las plantillas creadas después del lanzamiento, está activada de forma predeterminada; desactívala si no lo deseas.
7. Define dónde enviar a los usuarios **cuando la aplicación no está instalada**.  
   * Si has seleccionado una aplicación para Android y una aplicación para iOS, la plantilla está configurada de forma predeterminada para enviar nuevos usuarios de la aplicación a la tienda de aplicaciones correcta.
   * Si seleccionas solo una aplicación, Android o iOS, la plantilla estará configurada para enviar a TODOS los usuarios (iOS y Android, nuevos y existentes) al único destino definido.
   * Si seleccionas una aplicación de Android que no está en Google Play, debes introducir una URL a la que se redirige a los usuarios de Android.
   * [Opcional] **Envía a tiendas de aplicaciones de third-party** si la aplicación está en otras tiendas además de Google Play. Asegúrate de que la aplicación de las demás tiendas tenga el mismo nombre de paquete que la aplicación de Android seleccionada en tu plantilla de OneLink. /span>
   * [Opcional] **Cambiar a una URL diferente**: En algunos casos, es posible que prefieras llevar a los nuevos usuarios a una experiencia web móvil en lugar de llevarlos directamente a la tienda de aplicaciones (o es posible que tu aplicación no aparezca en la tienda). Para implementar, introduce esa URL en el  campo  URL. **Nota**: Si configuras una redirección de third-party y una URL diferente, la redirección predeterminada es a la tienda de aplicaciones de terceros.
   * [Opcional] Activa **Display App Clip para los usuarios con Private Relay** (disponible en iOS 14 o versiones posteriores). <Anchor target="_blank" href="/marketers/es/docs/apple-app-clips-integration-guide">Saber más sobre App Clips</Anchor>.
8. Omitir **cuando la aplicación esté instalada**. Esto se discutirá en el [procedimiento siguiente](/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users).
9. [Opcional] Cambiar el destino para **cuando se hace clic en el enlace en el ordenador.**  
   * En algunos casos, es posible que se haga clic en el enlace desde una computadora de ordenador, especialmente si se envía por correo electrónico o redes sociales. Si esperas que tu enlace reciba mucho tráfico de ordenador, es posible que desees enviar a esos usuarios a una página de destino o a la página principal del sitio web, o a una página en la que puedan solicitar un enlace por SMS en su teléfono, en lugar de a la tienda de aplicaciones correcta.
   * Por defecto, los usuarios de ordenadores son redireccionados a una versión web de la App Store o de la tienda Google Play, dependiendo de las aplicaciones configuradas en la plantilla.
     * Para cambiar la opción de tienda predeterminada, selecciona "URL web de ordenador" y agrega la URL de la tienda web correspondiente. Asegúrate de agregar el dominio de la tienda a la lista de permitidos para redirecciones.
10. **Seleccionar aplicaciones de otras plataformas**  
    Si tienes una versión de aplicación dedicada para lo siguiente:
    * **Windows phone**: Activa el botón y selecciona aplicación o **Cambiar a una URL diferente**.
    * **iPad**: Activa la palanca y selecciona la aplicación para iPad
    * **Amazon Kindle Fire**: Activa el botón y añade el ASIN de la tienda Amazon o la URL de la página de la aplicación.
11. Haz clic en **Guardar plantilla de OneLink (Actualizar plantilla** de OneLink para plantillas editadas).   
    La plantilla de OneLink ya está creada y se puede usar para crear muchos enlaces diferentes en los que se puede hacer clic (consulta Enlaces y experiencias de <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink</Anchor>).

</Accordion>

<div id="add-redirection-logic-for-existing-app-users" />

<Accordion title="Agrega una lógica de redireccionamiento para los usuarios existentes de la aplicación">

Los usuarios de aplicaciones existentes suelen esperar que se les envíe directamente a la aplicación, no a una tienda de aplicaciones o página web. Hay tres tecnologías disponibles para abrir la aplicación directamente después de un clic:

* **iOS Universal Links**: Funciona con iOS 9 y versiones posteriores, y ofrece una experiencia fluida y segura al abrir tu app.
* **Enlaces de aplicaciones de Android**: funciona con Android 6 y versiones posteriores, y ofrece una experiencia fluida y segura al abrir tu aplicación. **Nota**: El sistema operativo Samsung no puede abrir aplicaciones mediante App Links de Android.
* **Esquema URI**:  
  * Método fallback:
    * Android: El esquema URI es un método fallback eficaz cuando los App Links de Android no pueden abrir la aplicación porque no funcionan o no están configurados
    * iOS: Capacidades de fallback limitadas para cuando los Universal Links no pueden abrir la aplicación porque no funcionan o no están configurados. <Anchor target="_blank" href="/marketers/es/docs/uri-scheme-fallback-for-ios">Saber más</Anchor>
  * Método principal para abrir aplicaciones en dispositivos Samsung.
  * Es una dirección que, cuando se accede a ella, abre la aplicación si está instalada. Son similares a los enlaces de sitios web, pero abren aplicaciones en lugar de sitios web.
  * Debe ser igual para iOS y Android.

Para obtener la mejor experiencia de usuario, seguridad y cobertura de dispositivos, recomendamos habilitar tantas tecnologías como sea posible. Si habilitas todas las tecnologías de enlace, OneLink aplicará automáticamente el mejor método para cada usuario.

**Para agregar la lógica de redireccionamiento para los usuarios existentes de la aplicación a tu plantilla de OneLink:**

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Administración de OneLink**.
2. Selecciona la plantilla de OneLink que deseas editar.
3. Haz clic en el icono de menú (⋮) y, luego, haz clic en **Editar plantilla de OneLink**.
4. Desplázate hacia abajo hasta **Cuando la aplicación está instalada**. [![](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)
5. Sigue las instrucciones para iOS, Android y la configuración alternativa:

   <Tabs>
   <Tab title="Enlaces universales de iOS">

   Los Universal Links tienen el formato de los enlaces web habituales (p. ej., https://yourbrand.onelink.me o https://www.yourbrand.com) y, por lo tanto, requieren configurar un subdominio (como se explica en la [guía anterior](/docs/create-a-onelink-template#crear-una-plantilla-de-onelink)). OneLink también es totalmente compatible con <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">dominios de marca</Anchor>, pero eso no es necesario para completar esta guía.

   **Para iniciar la aplicación con Universal Links**:

   1. Contacta con tu desarrollador de iOS:
      * Dale el subdominio de esta plantilla de OneLink.
      * Dile que siga <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">estas instrucciones</Anchor>.
      * El desarrollador te dará el ID de equipo (también denominado prefijo de ID de aplicación de Apple, por ejemplo, PF23MIWNTW).
      * Si la aplicación aún no se publicó, el desarrollador también debe brindarte el identificador de paquete (por ejemplo, com.myapp.something).  
        <Image align="center" alt="" src="https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png" />
   2. En la página de la plantilla de OneLink, haz clic en **Cambiar para iniciar la app con Universal Links**.
   3. En la ventana nueva, selecciona **Iniciar la aplicación con Universal Links**.
   4. En el campo **ID de equipo**, ingresa el ID de equipo que te proporcionó el desarrollador.
   5. Si la aplicación no está publicada, también debes ingresar el **Identificador de paquete**.
   6. Haz clic en **Guardar cambios**.

   </Tab>

   <Tab title="Enlaces de aplicaciones de Android">

   Los App Links tienen el formato de los enlaces web habituales (p. ej., https://yourbrand.onelink.me o https://www.yourbrand.com) y, por lo tanto, requieren configurar un subdominio (como se explica en la [guía anterior](/docs/create-a-onelink-template#crear-una-plantilla-de-onelink)). OneLink también es totalmente compatible con <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">dominios de marca</Anchor>, pero eso no es necesario para completar esta guía.

   **Antes de comenzar**:

   Registra el subdominio que has elegido para esta plantilla de OneLink.

   **Para iniciar la aplicación con los App Links de Android**:

   1. Ponte en contacto con tu desarrollador de Android:   
      Dile que genere una huella digital SHA256 siguiendo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">estas instrucciones</Anchor>.  
      El desarrollador te dará el SHA256 fingerprint. Por ejemplo: `DC:65:43:67:F3:BD:02:52:AC:B4:50:F1:74:54: 23:49:4D:49:6C:E6:DF:56:BD:CB:53:06:11:5B:C9:4E:5D:0C`
   2. En la página de la plantilla de OneLink, haz clic en **Cambiar para iniciar la aplicación con los App Links**.
   3. En la nueva ventana, selecciona **Iniciar la aplicación con App Links**.
   4. En el campo de **fingerprint SHA256**, introduce la fingerprint SHA256 proporcionada por el desarrollador.  
      Aparecerá un código de filtro de intención generado automáticamente.
   5. Ponte en contacto con tu desarrollador de Android:   
      Dale el código intent-filter generado automáticamente.  
      Dile que siga <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">estas instrucciones</Anchor> y que confirme que se ha completado.

   </Tab>

   <Tab title="Esquema URI">

   El esquema URI sirve principalmente como opción alternativa para los usuarios de iOS y Android y, por lo tanto, debe ser el mismo en ambos.

   **Para configurar la opción fallback de URI para Android e iOS:**

   1. Contacta con tus desarrolladores de iOS y Android y elige un esquema URI. Por ejemplo: `feedmeapp://`

      <div id="h_01H9Q4E7VR4CAK0PJY269GQ9XJ" />

      <div id="tip" />

      > 👍 **Consejo**
      >
      > * Ni Apple ni Google exigen nombres exclusivos para los esquemas de aplicaciones. **Elige un nombre de esquema exclusivo para tu marca** para evitar conflictos entre esquemas de distintas aplicaciones. Un buen nombre de esquema podría ser el ID del paquete de la app, por ejemplo, **com.company.app**
      > * Para que OneLink funcione tanto en iOS como en Android, es importante que **se defina el mismo esquema para ambas plataformas**. Aquí tienes las instrucciones para <Anchor target="_blank" href="https://help.contrast.co/hc/en-us/articles/200865293-URL-Scheme-Intro-for-App-Developers">iOS</Anchor> y <Anchor target="_blank" href="https://developer.android.com/training/app-links/deep-linking.html">Android</Anchor>.
      > * El esquema URI no debe comenzar con http o https.

   2. Pídele al desarrollador de iOS que implemente el esquema URI en su aplicación <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-uri-scheme">siguiendo estas instrucciones</Anchor>.  
      **Y**  
      Pídele al desarrollador de Android que implemente el esquema URI en su aplicación siguiendo estas instrucciones.
   3. Una vez hecho esto, el desarrollador confirma el valor del esquema URI implementado. Espera ver algo así: `exampleapp://` o `exampleapp://home` o `exampleapp://main`, etc.
   4. En la página de plantilla de OneLink, haz clic en **Agregar esquema URI para iniciar la aplicación**.
   5. Selecciona **Iniciar la aplicación con el esquema URI**.
   6. Ingresa el valor del esquema URI.
   7. Haz clic en **Guardar cambios**.
   8. Prueba el esquema URI (esto lo puedes hacer tú O tus desarrolladores):
      1. Ve a <Anchor target="_blank" href="https://halgatewood.com/deeplink/">esta herramienta de prueba pública y gratuita</Anchor> tanto en un dispositivo iOS como en uno Android que tenga instalada tu app.
      2. Toca el enlace generado por la herramienta.  
         Si el esquema URI es correcto, la aplicación se abre.

   </Tab>
   </Tabs>

6. Haz clic en **Actualizar la plantilla de OneLink**.

<div id="note-1" />

> 📘 **Nota**
>
> * Cuando guardas o actualizas tu plantilla de OneLink, AppsFlyer genera automáticamente el archivo AASA y/o Digital Asset Links JSON para verificar el dominio de tu aplicación, y lo aloja por ti. Esto es fundamental para que tus Universal Links y App Links funcionen correctamente.
> * Las actualizaciones de la plantilla de OneLink pueden tardar hasta 1 hora en surtir efecto.

</Accordion>

<div id="customize-qr-codes" />

<Accordion title="Personalizar QR code">

<Image align="center" alt="OnelinkQRFinal__1_.gif" src="https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif" />

Puedes personalizar los QR codes generados a través de OneLink de la siguiente manera:

* Agregar tu logotipo al QR code.
* Cambiar el color del código QR.

**Nota**: La personalización del QR code se realiza a nivel de plantilla, no a nivel de enlace individual. Por lo tanto, las personalizaciones afectan a todos los QR codes basados en la plantilla editada.

**Para personalizar tu QR code**:

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **OneLink Custom Links.**
2. Coloca el cursor sobre el icono **Acciones** de la plantilla que deseas editar y haz clic en **Personalizar QR code**.  
   Se abre el editor de QR code.
3. Introduce la URL en la que está alojado tu logotipo. Por ejemplo: https://yourbrand.com/logo.png.  
   Requisitos del logo:

   * Formato PNG o JPG
   * Cuadrado o circular con fondo transparente
   * Dimensiones mínimas: 400 x 400 px
   * Para imprimir, usa la máxima resolución de imagen
4. Configura el color del QR code.
5. Haz clic en **Guardar**.

</Accordion>

<div id="h_favicon" />

<Accordion title="Configura un favicon para las vistas previas de enlaces">

Un favicon es el pequeño icono que aparece junto al título de tu enlace cuando se comparte en redes sociales o en aplicaciones de mensajería. Personaliza su aspecto añadiendo aquí tu propio icono. Se aplica a todos los enlaces basados en esta plantilla y se muestra en las plataformas compatibles cuando se comparte un enlace con una vista previa personalizada de redes sociales configurada.

<div id="note-2" />

> 📘 **Nota:**
>
> Este favicon solo aparece en las vistas previas de enlaces en las plataformas compatibles, y solo cuando se configura **Custom preview (image and tags)** a nivel de enlace. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags">Saber más</Anchor>

**Para configurar un favicon para tu plantilla de OneLink:**

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **OneLink management**.
2. Selecciona la plantilla de OneLink que deseas editar.
3. Haz clic en el icono de menú (⋮) y, a continuación, haz clic en **Editar plantilla de OneLink**.
4. Desplázate hacia abajo hasta la sección **Favicon**.
5. En el campo **URL de la imagen del favicon**, introduce la URL de tu imagen de favicon.
   * Formato compatible: ICO
   * Tamaño de icono recomendado: 32×32 o 64×64 píxeles
   * El tamaño del archivo no debe superar los 100 KB.
   * La URL debe ser accesible públicamente
6. Comprueba la **vista previa** para confirmar que el icono se muestra correctamente.
7. Haz clic en **Actualizar la plantilla de OneLink**.

</Accordion>

<div id="traits-and-limitations" />

## Características y limitaciones

<div id="key-traits-and-limitations" />

<Accordion title="Características y limitaciones clave">

| Caducado | Observaciones |
| --- | --- |
| Agencias | Las agencias no pueden crear plantillas y enlaces de OneLink. |
| Agregar/editar plantillas de OneLink | Los usuarios de la cuenta requieren <Anchor target="_blank" href="/marketers/es/docs/user-management">permiso</Anchor> para agregar y editar plantillas de OneLink. |
| Plantillas de OneLink | Hasta 600 plantillas de OneLink por cuenta. |
| Ordenador | Cuando configuras la URL o la plantilla de OneLink para redireccionar a los usuarios de ordenador a una URL diferente, la URL web se agrega al enlace del parámetro `af_web_dp`. Cuando el enlace contiene `af_web_dp`, AppsFlyer no registra un clic si proviene de un ordenador. |
| Redireccionar a tiendas de aplicaciones de terceros | Se pueden configurar varias tiendas de aplicaciones en la plantilla de OneLink solo si el nombre del paquete de aplicaciones es el mismo para todas las tiendas de aplicaciones. Para más información sobre la redirección de OneLink a tiendas de aplicaciones de Android de terceros, haz clic <Anchor target="_blank" href="/marketers/es/docs/bulletin-onelink-redirection-to-third-party-android-app-stores?query=3rd%20party%20store">aquí</Anchor>.<br /><br />**Nota**:<ul><li>Huawei y otras tiendas de terceros a veces requieren nombres de paquetes diferentes. Cuando este es el caso, la misma plantilla de OneLink no se puede usar en varias tiendas de aplicaciones.</li><li>Algunos dispositivos Xiaomi tienen la tienda GetApps, que utiliza el mismo esquema URI que Google Play. Esto significa que si tu intención es redireccionar a estos usuarios de dispositivos a Google Play, pero tu aplicación no existe en Xiaomi, el enlace enviará a GetApps.</li><li>Si el nombre del paquete es el mismo, pero el canal es diferente, la redirección funciona, pero la atribución no.</li><li><Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">Aprender más</Anchor> sobre la atribución y los datos de las tiendas de aplicaciones de terceros.</li></ul> |
| Actualizar una plantilla | <ul><li>Los cambios en la configuración de una plantilla de OneLink tardan hasta 1 hora en aplicarse.</li><li>Las plantillas de Onelink no se pueden editar si una aplicación asociada fue eliminada de la cuenta. En este caso, puedes:<ul><li>Crea una nueva plantilla.</li><li>Contacta a tu Customer Success Manager de AppsFlyer o escribe a hello@appsflyer.com para restaurar la aplicación eliminada.</li></ul></li></ul> |
| Esquema URI | Consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#chrome-browser-on-ios">aquí</Anchor>. |

</Accordion>

¿Tienes alguna pregunta sobre las plantillas de OneLink? ¡Consulta nuestras <Anchor target="_blank" href="/marketers/es/docs/onelink-troubleshooting-and-faq#preguntas-frecuentes-sobre-las-plantillas-de-onelink">Preguntas frecuentes</Anchor>!

<div id="next-step" />

## Paso siguiente

Sigue las instrucciones para <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">crear enlaces de OneLink</Anchor> basados en tu plantilla.

<div data-zendesk-anchors="onelink-templates=plantillas-de-onelink h_01H9Q4E7VQ0GKZ9HFF88190TYN=plantillas-de-onelink procedures=crear-una-plantilla-de-onelink h_01H9Q4E7VQYGZ1MH5SS3ZYZF1K=crear-una-plantilla-de-onelink h_01H9Q4E7VQ648CQ1VJTB1TC571=create-a-onelink-template-with-redirection-logic-for-new-app-users h_01H9Q4E7VQ15AAR1VXNKWR1XGT=nota h_01H9Q4E7VQ4NEWYAD6AMR9YKGY=add-redirection-logic-for-existing-app-users h_01H9Q4E7VR8164HR6MD0EAV2SN=nota-1 h_01H9Q4E7VR0F4B7CTF08YTG715=customize-qr-codes set-a-favicon-for-link-previews=h_favicon h_01KT6GG94CRBYFDWZ28BA8HEYY=nota-2 traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KZX85DYWA1TJ0AS3QV27VPA4=caracter%C3%ADsticas-y-limitaciones h_01H9Q4E7VR2B50EQE31DDG8GNZ=key-traits-and-limitations next-step=paso-siguiente h_01H9Q4E7VRJK31P9CSGJFCKQQF=paso-siguiente" />

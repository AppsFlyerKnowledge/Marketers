---
title: Preguntas frecuentes y resolución de problemas de OneLink
metadata:
  keywords:
    - faq
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2020-10-27T11:26:30Z'
  edited_at: '2026-09-16T00:32:24Z'
  id: 360014821438
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/360014821438
---
> **At a glance:** Encuentra rápidamente soluciones para probar y depurar problemas de redireccionamiento/comportamiento de enlaces personalizados de OneLink.

<div id="onelink-troubleshooting-guide" />

## Guía de resolución de problemas de OneLink

<div id="onelink-frequently-asked-questions" />

## Preguntas frecuentes sobre OneLink

<div id="onelink-template-faq" />

### Preguntas frecuentes sobre las plantillas de OneLink

<Accordion title="¿Qué método debo usar para abrir aplicaciones: Universal Links, App Links o esquemas URI?">

**Enlaces universales:** necesarios para más del 98% de los usuarios de iOS

**Enlaces de aplicaciones:** para usuarios de Android con la versión 6.0+. **Nota**: El sistema operativo Samsung no puede abrir aplicaciones mediante los enlaces de aplicaciones de Android.

> 📘 **Note**
>
> Tanto los Universal Links como los App Links requieren una prueba de que el dominio en la URL en la que se hizo clic (en otras palabras, el dominio de marca o el dominio de enlace personalizado de OneLink) es de propiedad y está asociado con la aplicación específica que intenta abrir. Esta asociación de dominio se realiza a través del **archivo Apple App Site Association (AASA)** para iOS y del archivo **Assetlinks** para Android.
>
> A estos archivos los aloja AppsFlyer o el anunciante en su sitio web. De forma predeterminada, cuando creas plantillas de OneLink y configuras enlaces universales y enlaces de aplicaciones, AppsFlyer genera y aloja estos archivos.

**Esquemas de URI:** el método principal para abrir aplicaciones en dispositivos Samsung. De lo contrario, es un método heredado y alternativo para abrir aplicaciones. Se puede usar:

* Para usuarios de Android con versiones anteriores a la 6.0 (menos del 15 % de los usuarios de Android)
* Como alternativa cuando los Universal Links y App Links no abren la aplicación, ya sea porque no funcionan o no están configurados. **Nota:** El uso de esquemas URI como opción alternativa para enlaces universales está sujeto a limitaciones basadas en iOS. <Anchor target="_blank" href="/marketers/es/docs/uri-scheme-fallback-for-ios">Saber más</Anchor>.

<div id="deep-linking" />

#### Enlaces profundos

Los Universal Links, App Links y los esquemas URI son métodos seguros para **abrir** una aplicación. Para usar enlaces profundos y redirigir a los usuarios a actividades o páginas específicas en la aplicación, sigue las <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">instrucciones de Deep Linking de OneLink</Anchor>.

</Accordion>

<Accordion title="¿Qué sistemas operativos permiten que los esquemas URI abran la aplicación?">

| Sistema Operativo | ¿Funcionan los esquemas URI para abrir la aplicación? |
| --- | --- |
| apps de iOS, | **Sí.** Se usan como opción alternativa cuando los Universal Links fallan.<br /><br />**Notas importantes:**<ul><li>El uso de esquemas URI como opción alternativa está sujeto a limitaciones basadas en iOS.</li><li>Para muchos navegadores, incluido Safari, debes agregar el parámetro `af_force_deeplink=true` a la URL para usar los esquemas URI como opción alternativa. <Anchor target="_blank" href="/marketers/es/docs/uri-scheme-fallback-for-ios">Saber más</Anchor>.</li><li>Si aparece un mensaje de error que dice: "Something went wrong. «The application couldn’t be opened.» Por lo general, esto significa que la aplicación no está instalada o que se ha utilizado un esquema de URI incorrecto.</li></ul> |
| Android | **Sí.** Se utilizan para dispositivos Samsung, versiones de Android anteriores a la 6.0 y como opción alternativa para cuando los App Links fallan en versiones posteriores de Android. |
| Amazon | **No** |
| Windows Mobile | **No** |

</Accordion>

<Accordion title="¿Debo actualizar la aplicación después de configurar los enlaces universales de iOS y los enlaces de aplicaciones de Android?">

**Sí.** Siempre que se implementen Universal Links o App Links para abrir la aplicación para los usuarios existentes, se actualizarán los dominios asociados de iOS o AndroidManifest.xml. Esto significa que debes cargar una versión nueva de la aplicación en la tienda de aplicaciones correspondiente. **Consejo:** Para minimizar la necesidad de actualizar la aplicación, realiza de una sola vez todos los cambios de desarrollo necesarios para <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">abrir la aplicación</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">Deep Linking</Anchor> al mismo tiempo.

</Accordion>

<Accordion title="¿Puedo enviar a los usuarios existentes a una página web en lugar de a la aplicación?">

**Sí.** Sin embargo, configurar la plantilla para hacerlo afecta a todos los usuarios (nuevos y existentes) y envía a todos a la página de destino/URL web. Es decir, los nuevos usuarios no se envían a la tienda de aplicaciones.

Para enviar usuarios a una página web:

1. En tu plantilla, no configures enlaces universales, enlaces de aplicaciones ni esquema URI.
2. Configura los redireccionamientos a la URL web/landing page para cuando la aplicación no esté instalada.
   * Las URL web/landing pages se agregan como valores para los parámetros af\_android\_url y af\_ios\_url.
   * Asegúrate de que todas las URL a las que rediriges a los usuarios se hayan añadido a tu <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">lista de permitidos de redireccionamiento de dominio</Anchor>.
   * Los redireccionamientos también se aplican automáticamente cuando se instala la aplicación (para los usuarios existentes).

**Nota**: Si quieres redirigir a los usuarios existentes a una página web móvil solo después de iniciar la aplicación, el desarrollador de apps debe configurar ese comportamiento.

</Accordion>

<Accordion title="¿Puedo enviar a los usuarios de tablets a una aplicación o URL diferente a la de los usuarios de aplicaciones móviles?">

Puedes establecer redirecciones específicas para:

* Windows Phones
* iPads
* Amazon Kindle Fire.

Actualmente, no se admiten otras tabletas para redireccionamientos separados.

</Accordion>

<Accordion title="¿Puedo asignar una aplicación a varias plantillas de OneLink?">

**Sí.** Si bien puedes usar una sola plantilla de OneLink para crear una cantidad ilimitada de URL de OneLink, en algunos casos tal vez debas asignar una aplicación a más de una plantilla de OneLink. Por ejemplo, si tienes varias versiones de una aplicación de Android para mercados fuera de la tienda, es posible que necesites una plantilla de OneLink separada por versión de Android, y aun así puedes tener la misma aplicación de iOS asignada a todas ellas.

**Importante**:

En las plantillas que usan enlaces universales de iOS y enlaces de aplicaciones de Android para abrir la aplicación, **si tus plantillas tienen subdominios diferentes**, debes configurar y actualizar tus aplicaciones de iOS y Android para cada uno de ellos:

* **Enlaces universales de iOS:** Después de crear la nueva plantilla de OneLink y actualizar el dominio asociado en la aplicación, envía una nueva versión a la tienda de aplicaciones. Solo los usuarios de iOS que actualizaron a la nueva versión pueden activar una URL de OneLink incorporada en la plantilla nueva.
* **App Links de Android:**
  1. Después de crear la nueva plantilla de OneLink, copia el fragmento de XML al final de la sección App Link y añádelo al archivo **AndroidManifest.xml** dentro del intent al que quieras dirigir el Deep Linking, además de cualquier intent anterior.
  2. Lanza la nueva versión en la tienda. Solo los usuarios de Android que hayan actualizado a la nueva versión podrán activar una URL de OneLink incorporada en la plantilla nueva.

</Accordion>

<Accordion title="¿Puedo eliminar una plantilla de OneLink?">

Sí.

**Para eliminar una plantilla:**

1. En AppsFlyer, ve a la página de Gestión de OneLink.
2. Selecciona la plantilla OneLink.
3. Haz clic en la opción 'Editar plantilla' del menú de tres puntos.

   <Image align="center" alt="delete template.png" src="https://files.readme.io/72b68cb979e2360f4e3065f99fbb547a91713a40dcc9adee59028ed2945f794a-31094482204945.png" width="1204px" />
4. Haz clic en el icono de la papelera.

**Nota:** Si tienes URLs de OneLink existentes basadas en la plantilla eliminada, **no funcionarán ni siquiera para llevar a los usuarios a la tienda de aplicaciones.** Por este motivo, es particularmente importante que no elimines una plantilla sin asegurarte primero de que no haya ninguna URL de OneLink que la utilice. Alternativamente, considera si es posible lograr los resultados que necesitas cambiando la configuración de la plantilla actual en lugar de eliminarla.

</Accordion>

<Accordion title="¿Puedo cambiar el subdominio en una plantilla de OneLink?">

**Sí, siempre y cuando no haya enlaces personalizados existentes en AppsFlyer basados en la plantilla.**

Si ya hay enlaces personalizados en AppsFlyer basados en la plantilla de OneLink, el subdominio no se puede cambiar. Esta limitación está diseñada para evitar romper el comportamiento de redirección/deep linking de los enlaces activos.

Si necesitas cambiar el subdominio en una plantilla con enlaces personalizados existentes, puedes:

* Crear una plantilla nueva de OneLink con el subdominio nuevo y crear enlaces basados en esta.
* Eliminar todos los enlaces personalizados existentes en función de la plantilla para la que se debe cambiar el subdominio. Una vez que se hayan eliminado todos los enlaces basados en la plantilla, el subdominio se podrá editar.

</Accordion>

<Accordion title="¿Se puede aplicar el dominio/subdominio de una plantilla de OneLink al ID de plantilla de otra plantilla?">

**No.** Tomar el subdominio/dominio configurado para una plantilla e ID de plantilla específicos y concatenarlos manualmente con un ID de plantilla diferente rompe la funcionalidad de los Universal Links y App Links y supone una amenaza para la seguridad.

**Ejemplo:**

* La plantilla 1ABC está configurada con el subdominio **bank.onelink.me**.
* La plantilla D123 está configurada con el subdominio **game.onelink.me**.
* El enlace **bank.onelink.me/1ABC/shorturl** se crea en base a la plantilla 1ABC y funciona.
* El enlace **game.onelink.me/D123/exampleurl** se crea en base a la plantilla D123 y funciona.
* El enlace **game.onelink.me/1ABC/shorturl** no funciona
* El **enlace bank.onelink.me/D123/exampleurl** no funciona

</Accordion>

<Accordion title="¿Puedo usar el mismo subdominio para más de una plantilla?">

**Sí.** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

</Accordion>

<Accordion title="¿Cómo puedo redireccionar a los usuarios de ordenadores?">

Los usuarios de ordenador pueden involucrarse con tus enlaces personalizados de OneLink, por ejemplo, a través de una campaña de correo electrónico. Sin embargo, cuando estos usuarios hacen clic en los enlaces, no pueden ser enviados a un sitio móvil, tienda de aplicaciones o aplicación. De forma predeterminada, los usuarios de ordenador son redirigidos a una versión web de la App Store o Google Play Store.

**Entonces, ¿cómo puedo ofrecer a los usuarios de ordenador una buena experiencia de usuario y convertirlos en usuarios móviles?**

En la URL o plantilla de OneLink, puedes redirigirlos (Windows o Mac) a una URL diferente. Esta URL web se agrega al enlace en el parámetro `af_web_dp`. Asegúrate de que todas las URL a las que rediriges a los usuarios se hayan añadido a la <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">lista de permitidos de redireccionamiento</Anchor> de tu dominio. De lo contrario, la redirección no funcionará.

**Nota:** Si tu enlace contiene `af_web_dp`, AppsFlyer no registra un clic cuando proviene de un ordenador.

> 👍 **Tip**
>
> Intenta redireccionar a los usuarios de ordenador a una URL web que contenga un formulario web exclusivo que envíe una URL de OneLink al dispositivo móvil del usuario por SMS o correo electrónico. Obtén más información sobre esta opción como parte de la solución OneLink Smart Script.

</Accordion>

<Accordion title="¿Cómo puedo redirigir a los usuarios de Chrome OS?">

Las aplicaciones en Chromebooks se consideran aplicaciones de Android.

Para Chromebook, para redirigir a nuevos usuarios sin tu aplicación instalada a una URL web diferente:

1. En la configuración de la plantilla de OneLink, en **Establecer el comportamiento del enlace** > **Cuando la aplicación no está instalada** > **Android**, haz clic en **Cambiar a una URL diferente**.  
   O  
   En la configuración del enlace de OneLink, en **Deep linking & redirection** > **Redirigir** > **Cuando la aplicación no está instalada** > **Android**, selecciona **URL web**.
2. Introduce la URL.  
   Cuando se añade a través de la configuración del enlace, la URL se agrega al enlace en el parámetro `af_android_url`.

</Accordion>

<Accordion title="¿Para qué aplicación se registra un clic de OneLink desde un escritorio?">

Una plantilla de OneLink se puede asociar con dos aplicaciones: una de iOS y una de Android. Cuando se hace clic en un enlace de OneLink desde un dispositivo móvil, el clic se registra para la aplicación que coincide con la plataforma del dispositivo. Un clic en un dispositivo iOS se registra para la aplicación de iOS, y un clic en un dispositivo Android se registra para la aplicación de Android.

Cuando se hace clic en un enlace de OneLink desde un escritorio, no hay ninguna plataforma de dispositivo con la que hacer la coincidencia. En este caso, el clic se registra de la siguiente manera:

* Si tanto una aplicación de iOS como una de Android están asociadas con la plantilla, el clic se registra para la aplicación de iOS.
* Si solo una aplicación está asociada a la plantilla, el clic se registra para esa aplicación.

</Accordion>

<div id="onelink-link-faq" />

### Preguntas frecuentes sobre los enlaces de OneLink

<Accordion title="¿OneLink funciona sin el SDK de AppsFlyer?">

**Sí, pero solo en parte.**

Si necesitas convertir rápidamente a los visitantes de la web móvil en usuarios móviles y no se puede integrar el SDK de AppsFlyer, es posible hacerlo.

La redirección básica de usuarios y el lanzamiento de aplicaciones funcionan incluso si el SDK de AppsFlyer no está aún integrado en la aplicación. Los Smart Banners tampoco requieren el SDK y funcionan perfectamente sin él.

Sin embargo, la ausencia del SDK significa que:

* Los usuarios que hacen clic no se pueden vincular con deep links más allá del primer inicio de la aplicación.
* No se registran datos de atribución.
* Los eventos in-app no se registran.

</Accordion>

<Accordion title="¿Qué métodos están disponibles para crear enlaces personalizados de OneLink?">

La siguiente tabla compara los diferentes métodos disponibles para crear enlaces personalizados de OneLink.

| Método de creación de enlaces | Usos | URL cortas y largas | Característica Premium | ¿Visible en la interfaz de usuario? | TTL de atribución (tiempo de vida) máximo y predeterminado |
| --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">UI de AppsFlyer</Anchor> | Crea enlaces personalizados y una plantilla de OneLink | Ambos | -- | ✓ | Sin TTL |
| <Anchor target="_blank" href="/marketers/es/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API de OneLink</Anchor> | Crea miles de OneLinks rápidamente | Corto | ✓ | -- | 31 días |
| <Anchor target="_blank" href="/marketers/es/docs/perform-onelink-bulk-actions-via-csv">Creación masiva de enlaces de OneLink</Anchor> | Crea miles de URLs cortas de OneLinks rápidamente usando los parámetros definidos en un CSV | Corto | -- | -- | 365 días |
| <Anchor target="_blank" href="/marketers/es/docs/user-invite-attribution">SDK</Anchor> | Campañas de invitaciones de usuarios (referencias) | Corto | -- | -- | 60 días |
| <Anchor target="_blank" href="/marketers/es/docs/onelink-smart-script-overview">Smart Script de OneLink</Anchor> | Campañas móviles web-to-app | Largo | -- | -- | Sin TTL |
| <Anchor target="_blank" href="/marketers/es/docs/understand-onelink-short-vs-long-urls">Hoja de cálculo</Anchor> | Crea miles de enlaces personalizados de OneLink aplicando tus propias fórmulas | Largo | -- | -- | Sin TTL |

</Accordion>

<Accordion title="¿Qué ocurre cuando elimino una URL de OneLink de la página de gestión de OneLink?">

A partir de noviembre de 2025,

* Una vez que se elimina un enlace de la sección de gestión de OneLink, el enlace se elimina de la tabla y de la base de datos. Esto significa que, si un usuario final encuentra el enlace y hace clic en él, se le redirigirá en función de la configuración de la plantilla de OneLink. Los parámetros de atribución, los parámetros de deep linking y la configuración de redirección a nivel de enlace no se aplicarán.
* El enlace dejará de funcionar en un plazo de 2 minutos tras su eliminación.
* Los enlaces eliminados a través de la interfaz de usuario después del 5 de noviembre de 2025 se pueden restaurar desde la tabla **Enlaces eliminados**, accesible en la gestión de OneLink.

  <Image align="center" alt="deleted links.png" src="https://files.readme.io/d5a2cc7047fda06ba8249cc00b2830c309ec6137f10306cdabca61bcfe3d4d15-small-41829768141713.png" width="2768px" />
* Los enlaces se pueden restaurar hasta 90 días después de la fecha de eliminación. Si han pasado más de 90 días desde la fecha de eliminación del enlace, el enlace no se puede restaurar.

</Accordion>

<Accordion title="¿Los enlaces personalizados de OneLink pueden abrir la aplicación desde un navegador?">

**Sí**, pero ten en cuenta que los Universal Links y los App Links solo funcionan cuando se hace clic en él (por ejemplo, al hacer clic en un enlace en una página web o correo electrónico). **Pegar el enlace en la barra de direcciones del navegador no inicia la aplicación.** Prueba tus enlaces haciendo clics en las URLs; no pegándolas en la barra de URLs del navegador.

</Accordion>

<Accordion title="¿Por qué la URL de OneLink no abre la aplicación ni establece deep links para los usuarios existentes?">

A pesar de las mejores intenciones, en algunos casos, tus URLs de OneLink pueden no realizar el deep linking previsto. Cuando esto sucede, en lugar de abrir la aplicación o acceder a un deep linking en una actividad específica dentro de la aplicación, los usuarios son redireccionado a la tienda de aplicaciones o a un error de la página.

Hay varias razones posibles para esto:

* **Aplicaciones del host:** Las apps en las que se comparten tus enlaces de atribución (por ejemplo, WhatsApp, Gmail, WeChat) utilizan diferentes métodos para activar los enlaces clicados, como navegadores internos propios. Se sabe que algunos de estos bloquean todos los enlaces de atribución.
* **Navegadores:** Ciertos navegadores y plataformas de sistema operativo se comportan de manera diferente con los enlaces. En ciertos navegadores, por ejemplo, pegar un enlace no funciona. En realidad, se debe hacer clic en el enlace.
* **Actualizaciones del sistema operativo:** Las nuevas actualizaciones del sistema operativo (tanto iOS como Android) pueden introducir errores inesperados que obstaculizan el deep link.
* **Dispositivos:** Diferentes smartphones, tablets, computadoras portátiles, y otros dispositivos que ejecutan diferentes versiones de iOS, Android, Windows Mobile y otros sistemas operativos pueden variar mucho en su manejo de enlaces de atribución.
* **Configuración incorrecta:** El uso de <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">caracteres especiales</Anchor> en el valor del deep linking rompe el enlace.

Dos soluciones para mejorar la experiencia del usuario son las URLs Fallback y el deep linking forzado.

<div id="fallback-urls" />

#### URL alternativas

Las URLs Fullback envían a los usuarios a páginas web específicas si se abre la aplicación o el deep link falla por cualquier motivo. **¡Importante!** Ellos también envían a los usuarios que no tienen tu aplicación instalada a la URL de Fallback en lugar de la tienda de aplicaciones correspondiente. Así que asegúrate de usar solo esta opción si estás volviendo a dirigir a usuarios que ya tienen tu aplicación instalada.

Para implementar una URL Fallback, en la plantilla OneLink o en la configuracíon del enlace personalizado, define el comportamiento del enlace para que, cuando la app no esté instalada, redireccione a una URL diferente.

<Image align="center" alt="different_url.png" src="https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png" />

Usar esta configuración añade `af_ios_url` y `af_android_url` como parámetros de destino para la recuperación, lo que hará que los usuarios de iOS sean enviados a la página especificada por `af_ios_url` y los usuarios de Android para ser redireccionados a la página especificada por `af_android_url`.

> 👍 **Tip**
>
> Mira, por ejemplo, la siguiente URL de OneLink:
>
> Tanto los usuarios de iOS como los de Android que hagan clic en este enlace deberían estar enlazados por deep linking a la aplicación. Sin embargo, cuando el deep link falla, los usuarios se redireccionan de la siguiente manera:
>
> * iOS: www.yoursite.com/ios-bonus
> * Android: www.yoursite.com/android-bonus

> 📘 **Note**
>
> Cuando se produce la redirección, los parámetros de URL de OneLink pasan a la página de destino especificada por af\_ios\_url o af\_android\_url. Para evitar este comportamiento, agrega el parámetro af\_param\_forwarding=false a OneLink.

<div id="forced-deep-linking" />

#### Deep linking forzado

El deep linking forzados te permiten usar un esquema URI como fallback para abrir la aplicación y hacer deep link a los usuarios.

Esta solución funciona bien para la mayoría de los usuarios que tienen la aplicación instalada. Sin embargo, para iOS, el uso del esquema URI para abrir la aplicación tiene limitaciones y es posible que necesites agregar `af_force_deeplink=true` a la URL de OneLink para forzar deep linking a la actividad especificada en el esquema URI (el parámetro `af_dp`). Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/uri-scheme-fallback-for-ios">Esquema URI alternativo para iOS</Anchor>

</Accordion>

<Accordion title="¿OneLink admite eventos de App Store Connect?">

Sí. Sin embargo, en Android, cuando un usuario hace clic en un enlace de OneLink en el navegador Brave, el deferred deep linking no funciona. Y en iOS, después que el usuario hace clic, ve una pantalla en blanco y el deferred deep linking solo funciona si luego hacen algo en la pantalla en blanco, por ejemplo, desplazar o tocar.

</Accordion>

<Accordion title="¿Por qué mi URL de OneLink abre una página en blanco en Chrome?">

Asegúrate de no estar utilizando una etiqueta HTML  que incluya el atributo `target`. Si la URL de OneLink se colocada dentro de una etiqueta  con el atributo `target="_blank"`, se abre una página en blanco en Chrome (tanto en iOS como en Android), y el usuario no es redireccionado a la App Store o a Google Play.

</Accordion>

<Accordion title="¿Puedo utilizar OneLink para la redirección en Brave?">

Sí. Sin embargo, en Android, cuando un usuario hace clic en un enlace de OneLink en un navegador Brave, deferred deep linking no funciona. Y en iOS, después de que el usuario hace clic, ve una pantalla en blanco y el deferred deep linking solo funciona si después hace algo en la pantalla en blanco, por ejemplo, desplazarse o tocar.

</Accordion>

<Accordion title="¿Los enlaces personalizados de OneLink tardan más en cargarse que otros enlaces?">

**No.** Los enlaces personalizados de OneLink no agregan ningún procesamiento adicional ni tiempo de carga para funcionar correctamente y envían a los usuarios según sea necesario. Son tan rápidos como cualquier otro enlace de AppsFlyer.

</Accordion>

<Accordion title="¿Cómo puedo registrar el costo por instalación cuando uso OneLink?">

Activar el **costo por instalación** (bajo **parámetros avanzados**) te permite aplicar un valor de CPI específico por cada instalación proveniente del enlace.

Selecciona la moneda de costo y luego un **valor SOLO numérico** (con hasta 4 dígitos después del punto decimal) que representa el CPI. Esto agrega los parámetros af\_cost\_currency y af\_cost\_value al enlace.

> 👍 **Tip**
>
> Una campaña de SMS cuesta 20 dólares por cada 1000 mensajes (CPM). La experiencia ha que tus campañas alcanzan una tasa de conversión del 5%, lo que significa un CPI derivado de $0.40. Establecer el costo por instalación en $0.40 USD te permite medir el eventual ROI de la campaña de SMS.

Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">medición de costos y ROI</Anchor>.

</Accordion>

<Accordion title="¿Cómo puedo evitar el reenvío de parámetros en redireccionamiento?">

Cuando ocurre la redirección, los parámetros de la URL de OneLink pasan a través. de la página de destino especificada por `af_ios_url` o `af_android_url`. Para prevenir este comportamiento, agrega el parámetro `af_param_forwarding=false` a OneLink.

</Accordion>

<Accordion title="¿Cómo puedo eliminar los parámetros PID y C de AppsFlyer al reenviar mientras? mantengo todos los demás parámetros en las URLs de redirección?">

En algunos casos, es posible que tengas URLs con múltiples PIDs. Esto sucede porque AppsFlyer agrega PID y parámetros C a una URL de redirección y el cliente también puede agregar sus propios parámetros PID. Por ejemplo, el 'ID de producto' podría ser 'pid' en la URL del sitio web del cliente.

Normalmente, agregar `af_param_forwarding=false` al enlace de atribución elimina todos los parámetros.

Sin embargo, si se hace clic en el enlace desde un ordenador, el cliente puede querer que los parámetros esenciales de CRM permanezcan. Para eliminar solo el parámetro PID y C de AppsFlyer y mantener todos los demás parámetros, agrega `af_base_params_forward=false` al enlace de atribución.

</Accordion>

<Accordion title="¿Continúan estando disponibles los enlaces personalizados de plataforma única?">

Sin embargo, si tienes enlaces personalizados heredados de plataforma única, siguen funcionando como siempre.

</Accordion>

<Accordion title="¿Puedo cambiar el ID de URL corta después de guardar un enlace?">

**No,** el ID de la URL corta solo se puede establecer en el momento en que el enlace está creado.

</Accordion>

<Accordion title="¿Puedo encapsular y acortar los enlaces personalizados de OneLink?">

**Los acortadores de enlaces externos o el encapsulado de los enlaces personalizados de OneLink romperán la funcionalidad de apertura de aplicaciones de los Universal Links y App Links.**

Para activar los Universal Links o App Links, el sistema operativo necesita reconocer el dominio de la URL asociada con la aplicación, y cualquier tipo de envoltura externa, acortamiento o redirección al enlace visible para el usuario lo hace imposible. Esto incluye el uso de bit.ly, enlaces no marcados con la marca de AppsFlyer, o Proveedores de Servicios de Correo Electrónico (ESPs) con el registro de clics habilitado.

**Para encapsular o acortar un enlace de forma que permita que la redirección funcione correctamente:**

* Utiliza las URL cortas generadas por AppsFlyer cuando crees enlaces personalizados de OneLink (en lugar de acortadores externos como bit.ly).**¡Consejo!** **Consejo**: Haz la URL aún más corta creando un dominio de marca corto en tu enlace. Y si estás creando el enlaces en la interfaz de usuario de AppsFlyer, puedes editar el ID de la URL para que sea lo más corto posible. Ejemplo: https://brand.com/a1b2/a (donde **brand.com** es tu dominio de marca, **a1b2** es el ID de plantilla que siempre tiene 4 caracteres, y **a** es el ID de URL, que se puede editar a 1 carácter.   
   Beneficios:
  * Este método funciona porque utiliza el subdominio de OneLink configurado en la plantilla OneLink.
  * Te permite cambiar parámetros sobre la marcha, incluyendo cualquier configuración de deep linking, incluso después de distribuir el enlaces de atribución a tus prospectos.
  * Cuenta todos los clics desde dispositivos móviles en el dashboard de AppsFlyer, así que no necesitas revisar otro servicio.
  * La última parte de la URL corta se puede personalizar para convertirla en un <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">dominio de marca</Anchor>.
* Utiliza el <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">esquema URI</Anchor> como una alternativa para abrir la aplicación cuando los Universal Links y los App Links fallan, y añade el siguiente parámetro al enlace: `af_force_deeplink=true`.
* Ver opciones para [trabajando con ESPs](/docs/onelink-troubleshooting-and-faq#can-i-use-onelink-custom-links-in-emails).

</Accordion>

<Accordion title="¿Puedo usar enlaces personalizados de OneLink en correos electrónicos?">

**Sí,** pero requiere una consideración especial cuando estás trabajando con Proveedores de Servicios de Correo Electrónico (ESPs). Para contar los clics, los ESPs envuelven todos los enlaces colocados dentro de los correos electrónicos. Esto rompe el flujo de deep linking/apertura de la aplicación para los usuarios que hacen clic en la URL

Para evitarlo, usa una de las siguientes soluciones opcionales:

* Deshabilita el registro de clics en la configuración de tu ESP.  
  **(Consejo: Esta suele ser la solución más fácil).**
* Forzar la apertura de la aplicación con el esquema URI especificado en el parámetro `af_dp` añadiendo la bandera `af_esp=true` en el enlace de atribución. Esta solución funciona bien para los usuarios que tienen la aplicación instalada.
* Utiliza ESPs que soporten la solución de AppsFlyer para la apertura de aplicaciones y deep linking con Universal Links. <Anchor target="_blank" href="/marketers/es/docs/email-service-provider-esp-integration-guide">Saber más</Anchor>.

</Accordion>

<Accordion title="¿Cómo se redirecciona a los usuarios a su tienda de aplicaciones regional?">

OneLink envía a los usuarios a la tienda de aplicaciones regional correcta según su dirección IP.

</Accordion>

<Accordion title="¿Por qué mi URL de OneLink no redirecciona a los usuarios al dominio especificado?">

Comprueba si has activado las listas de redireccionamientos permitidos en AppsFlyer. Si las tienes activadas, el dominio o subdominio de la URL web deseada debe estar listado. <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">Aprender más sobre las listas de redireccionamientos permitidos</Anchor>

</Accordion>

<Accordion title="¿Por qué aparece el error «La aplicación que estás buscando no está disponible»?">

El error 'La aplicación que estás buscando no está disponible' puede surgir en lugar de redireccionar a Google Play debido a:

* Tu aplicación se encuentra actualmente en estado «Pendiente» en Google Play. Para evitar el mensaje de error mencionado anteriormente, establece la redirección del enlace para apuntar a una URL web en lugar de Google Play. Una vez que la aplicación esté aprobada, la redirección se puede cambiar de nuevo a Google Play. Estos cambios de configuración se realizan en la <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">página de plantilla del enlace</Anchor>.
* Si tu aplicación está disponible exclusivamente a través de una tienda de terceros, el problema puede deberse a que se te esté asignando un estado incorrecto de Google Play en AppsFlyer. Para resolver esto, <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">debe establecer tu estado de Google Play en Published fuera de la tienda</Anchor> en la página Configuración de Mis Aplicaciones.

</Accordion>

<Accordion title="¿Por qué mi enlace corto de m.onelink.me no funciona?">

A partir de junio de 2024, la versión anterior del enlace corto **m.onelink.me** fue eliminado. Enlaces que aún utilizan este subdominio ya no redirecciona al destino previsto, potencialmente interrumpiendo la experiencia de usuario planificada.

</Accordion>

<Accordion title="¿Puedo cambiar manualmente entre el dominio de marca y el subdominio de OneLink en un enlace existente?">

Sí - Si el dominio de marca y el subdominio de OneLink están correctamente mapeados. Consulta: <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer">Configurar un dominio de marca en AppsFlyer</Anchor>

**Ejemplo**:  
 Subdominio de OneLink: **demo.onelink.me**  
 ID de plantilla: **A1r4**  
 Los dominios de marca mapeados a subdominios [**demo.onelink.me**](http://demo.onelink.me) son:

* **app.simulatorapp.com**
* **click.simulatorapp.com**

Has creado el siguiente enlace de marca en la interfaz de usuario de OneLink:  
 **app.simulatorapp.com/A1r4/simulationlink**  
 Puedes reemplazar el enlace de marca anterior con el otro dominio de marca o el enlace de subdominio OneLink.  
Los siguientes enlaces son funcionalmente idénticos y funcionan igual en todas partes

* app.simulatorapp.com/A1r4/simulationlink
* demo.onelink.me/A1r4/simulationlink
* click.simulatorapp.com/A1r4/simulationlink

</Accordion>

<div id="onelink-parameter-faq" />

### Preguntas frecuentes sobre los parámetros de OneLink

<Accordion title="¿Qué parámetros son obligatorios para los enlaces personalizados de OneLink?">

Solo el parámetro de la fuente de medios (**pid**) es obligatorio.

</Accordion>

<Accordion title="¿Se pueden agregar parámetros a la URL corta?">

**Sí,** se puede agregar cualquier parámetro a la URL corta.

**¡Importante!** Los parámetros incorporados a la URL corta no invalidan los parámetros dentro del enlace.

> 👍 **Tip**
>
> * Puedes crear un enlace personalizado de OneLink con el siguiente resultado:
>   * **URL larga:** https://onelink-sim.onelink.me/Il2C?pid=training&c=peaches
>   * **URL corta:** https://onelink-sim.onelink.me/Il2C/70e6d165
> * Añade los siguientes parámetros a la URL corta: https://onelink-sim.onelink.me/Il2C/70e6d165?c=bananas&af_adset=fruits
> * El parámetro **af\_adset=frutas** anexado a la URL corta es efectivo para la atribución. Sin embargo, el parámetro **c=bananas** **no es efectivo** porque ya hay un parámetro **c** en la URL larga.

</Accordion>

<Accordion title="¿Qué nombres de fuentes de medios personalizados puedo usar?">

Para los medios propios, el nombre de la fuente de medios personalizada (valor PID) puede ser cualquier cosa, siempre que no esté reservado por un partner integrado. Para evitar conflictos, no utilices el sufijo \_int (por ejemplo, googleadwords\_int) para fuentes de medios personalizadas. Sin embargo, se recomienda no utilizar *organic* como nombre de fuente de medios personalizado, ya que esto podría afectar a la integridad de los datos de atribución.

Si estás utilizando OneLink para medios de pago:

* Usa los valores **PID** integrados reservados por el partner (aquellos que terminan con **\_int**), como valores de fuente de medios en enlaces personalizados de OneLink. No utilices fuentes de medios SRN como *googleadwords* o *facebook* como nombres de fuentes de medios personalizados. Esto podría afectar la integridad de los datos de atribución.
* Asegúrate de que el partner esté integrado con AppsFlyer y activo (el selector **Activar partner** está activado) para todas las aplicaciones que están configuradas en la plantilla de OneLink.

</Accordion>

<Accordion title="¿Qué parámetros de atribución se pueden agregar a un OneLink?">

Aquí puedes agregar varios parámetros de atribución que te permitan realizar un análisis en profundidad más adelante.

| **Parámetro de atribución** | **Descripción** | **Nombre del enlace del parámetro** |
| --- | --- | --- |
| **Campaña** | Configura nombres de campaña para comparar distintas campañas que se estén realizando con la fuente de medios propios. | C |
| **Conjunto de anuncios** | Configura nombres de grupos de anuncios para comparar distintos grupos de anuncios dentro de campañas específicas de la fuente de medios propia. | af\_conjunto de anuncios |
| **Nombre de anuncio** | Define nombres de anuncios para comparar distintos recursos creativos dentro de grupos de anuncios específicos/campañas específicos de la fuente de medios propios. | af\_anuncio |
| **Canal** | Configura nombres de los canales si deseas comparar más de un canal de distribución para tus medios propios.<br /><br />Ejemplo: Si divides los mensajes SMS entre dos proveedores de servicios SMS, especifica el proveedor mediante el parámetro de canal. Más adelante, podrás comparar las tasas de conversión de los dos proveedores. | af\_canal |
| **Parámetros de suscriptor** | Utiliza cualquiera de los 5 parámetros de suscriptor disponibles para insertar valores que sean útiles para tu análisis.<br /><br />**Nota:** Estos parámetros se analizan y aparecen en los reportes de raw data, por lo que son muy prácticos para agregar o filtrar datos. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |
| **Parámetros personalizados** | De manera similar a los parámetros de suscriptor, puedes especificar campos con cualquier nombre de parámetro, valor y nombre. y nombre.<br /><br />A diferencia de los parámetros de suscriptor, los parámetros personalizados no se analizan en raw data; aparecen en los reportes de raw data solo en la columna **URL original**. | Personalizado  <br />(como especifiques) |

Obtén más información sobre los <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">parámetros y la estructura de los enlaces de atribución de AppsFlyer</Anchor>.

</Accordion>

<Accordion title="¿Se agregan parámetros personalizados a los enlaces personalizados de OneLink disponibles en raw data?">

**Sí.** Los parámetros personalizados se transfieren a la columna **URL original** en el raw data y se pueden ver allí. No tienen sus propias columnas en raw data.

Para los datos analizados, usa los parámetros de suscriptor `af_sub1-5`, cada uno de los cuales tiene una columna separada en los reportes de raw data.

</Accordion>

<Accordion title="¿Los parámetros distinguen entre mayúsculas y minúsculas?">

**Sí.** Asegúrate de usar solo letras minúsculas para tus parámetros y valores. Las letras mayúsculas o un uso incoherente de mayúsculas de nombres y valores de parámetros podrían causar errores o discrepancias de datos, tanto en el dashboard como en los raw data.

</Accordion>

<div id="integrated-partner-faq" />

### Preguntas frecuentes sobre los partners integrados

<Accordion title="¿Puedo usar OneLink en aplicaciones de redes sociales (no pagado)?">

Es posible que quieras utilizar OneLink con publicaciones no pagadas en aplicaciones de redes sociales, ya que no es posible dirigirse de antemano a los usuarios potenciales que están expuestos a tales publicaciones de acuerdo con sus dispositivos.

Lamentablemente, las limitaciones y restricciones de los Universal Links de iOS que establecen algunas aplicaciones de redes sociales complican el uso de OneLink para el reconocimiento básico de dispositivos, redireccionamiento y atribución, y deep linking. En algunos casos, quizás sea necesario configurar un esquema URI o una landing page para la aplicación de redes sociales para redirigir a los usuarios o establecer deep links con ellos.

La siguiente tabla resume cuándo se pueden utilizar OneLinks en las aplicaciones sociales más populares de la actualidad:

<table><tbody><tr><td>Aplicación de red social</td><td>Usuarios de Android sin la aplicación instalada</td><td>Deep linking en Android</td><td>Usuarios de iOS sin la aplicación instalada</td><td>Deep linking en iOS</td></tr><tr><td> <strong>Facebook</strong> (incluidas las publicaciones impulsadas)</td><td><span>✓\*\*†† </span></td><td><span>✓\*\*††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Facebook Messenger</strong></td><td><span>✓\*\*†† </span></td><td> <span>✓\*\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Snapchat</strong></td><td><span>✓†† </span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Instagram</strong></td><td><span>✓†† </span></td><td><span>✓††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>LinkedIn</strong></td><td><span>✓</span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td><strong>Reddit</strong></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td><strong>Slack</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>X (antiguo Twitter)</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>WeChat</strong></td><td><span>✓† </span></td><td><span>✓† </span></td><td><span>✓\*</span></td><td><span>✓\*† </span></td></tr><tr><td><strong>WhatsApp</strong></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="5"><p>\*Si se configura un <a href="./onelink-troubleshooting-and-faq#which-operating-systems-allow-uri-schemes-to-open-the-app">esquema URI</a> o una <a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page" target="_blank">landing page de la aplicación de red social</a>. <strong>Nota</strong>: Para Facebook y Facebook Messenger, si se configuran tanto el esquema URI como la landing page de una aplicación social, la landing page de la aplicación social no se muestra.</p><p>\*\* Debe tener un esquema URI.</p><p>^ Debes tener una página de destino de la app social con Universal Links configurados.</p><p><span>†</span> Es posible que se le pida al usuario que abra el enlace en un navegador externo.</p><p><span>††Aplicaciones sociales de Android, limitación de redireccionamiento de deep linking WebView. Ver más detalles </span><a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection" target="_blank"><span>aquí</span></a><span>.</span></p></td></tr></tbody></table>

</Accordion>

<Accordion title="¿Puedo usar OneLink con ad networks (pagado)?">

**Sí**, pero ten en cuenta que OneLink se usa principalmente con medios propios y no con ad networks. Esto se debe a que las ad networks generalmente se anuncian en aplicaciones (lo que significa que conocen lo suficiente la plataforma del usuario, el ID del dispositivo, etc.), los enlaces de atribución específicos de la plataforma y la aplicación son suficientes, por lo que no es necesario usar OneLink. Sin embargo, en los casos en que las ad networks no conocen la plataforma del usuario de antemano, por ejemplo, cuando ellas mismas ejecutan campañas por correo electrónico o SMS, OneLink puede ser la solución.

> 🚧 **Important**
>
> Cuando usas OneLink con ad networks, debes usar la URL larga de OneLink.

**Para establecer OneLink para ad networks de partners:**

* Sigue las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">instrucciones para el enlace de atribución de ad network</Anchor> y selecciona **Usar OneLink** cuando se te indique.

Una vez que todos los parámetros para Android e iOS se hayan agregado correctamente, cuando se hace clic en el enlace personalizado de OneLink y se redirecciona a la plataforma correcta, los parámetros necesarios se envían a la red en un postback después de la instalación por parte del usuario.

> 👍 **Tip**
>
> La red emplea cualquiera de los parámetros IDFA o GAID según la plataforma del dispositivo del cliente y omite el otro parámetro.

</Accordion>

<Accordion title="¿Qué solución hay para el tema del inicio de aplicaciones de iOS desde las aplicaciones de redes sociales?">

En ocasiones, Facebook y otras aplicaciones de redes sociales bloquean los Universal Links de iOS para que no abran aplicaciones. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Landing pages de aplicaciones sociales</Anchor> son la solución recomendada para estos problemas de inicio de aplicaciones.

Si no deseas usar landing pages de aplicaciones de redes sociales, puedes usar los esquemas URI como método alternativo. Sin embargo, ten en cuenta lo siguiente:

* El uso de esquemas URI como opción alternativa está sujeto a limitaciones basadas en iOS.
* Para muchos navegadores, incluido Safari, debes agregar el atributo `af_force_deeplink=true` a la dirección URL para usar esquemas URI como reserva. <Anchor target="_blank" href="/marketers/es/docs/uri-scheme-fallback-for-ios">Saber más</Anchor>.
* X (antes Twitter) no admite esquemas de URI. Debes usar una página de destino de una aplicación social para evitar problemas al iniciar la aplicación.

</Accordion>

<Accordion title="¿Puedo usar OneLink en Instagram?">

**Sí,** pero ten en cuenta las siguientes limitaciones:

* Debido a la forma en que Instagram presenta el texto de una publicación de la página, no es posible hacer clic en los enlaces cuando se los ingresa en una leyenda de la publicación.
* La apertura de aplicaciones y deep linking en aplicaciones de Android son compatibles sin ninguna consideración especial. Sin embargo, Instagram no admite la apertura de aplicaciones y deep linking en aplicaciones de iOS. Para superar este problema, puedes adoptar uno de estos dos enfoques:
  * **Recomendado:** Configura una <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">landing page de aplicación de redes sociales</Anchor>. Las plantillas Clustered Poster y ShowAndTell funcionan mejor. Además de la landing page de aplicación de redes sociales, recomendamos configurar un esquema URI en tu plantilla de OneLink.
  * Usa un esquema URI y [deep linking forzados](/docs/onelink-troubleshooting-and-faq#deep-linking-forzado) cuando uses OneLinks en Instagram. Asegúrate de tener en cuenta las siguientes consideraciones cuando uses `af_force_deeplink=true` con OneLink en Instagram:

| ¿Aplicación instalada? | ¿El clic tiene af\_force\_deeplink=true? | Resultado |
| --- | --- | --- |
| No | Sí | Al hacer clic se abre la tienda de aplicaciones |
| No | No | Al hacer clic se abre la tienda de aplicaciones |
| Sí | Sí | Al hacer clic se abre la aplicación |
| Sí | No | Al hacer clic se abre la tienda de aplicaciones |

</Accordion>

<Accordion title="¿Puedo usar OneLink en X (antes, Twitter)?">

Sí. Puedes usar OneLink en X, pero se **recomienda encarecidamente configurarlo con una Social App Landing Page (SALP) y Universal Links.**

Esto se debe a que el navegador in-app de iOS de X bloquea la redirección a la tienda de aplicaciones y la apertura de aplicaciones mediante esquemas URI, por lo que las configuraciones de OneLink que están configuradas solo con un esquema URI no abrirán la aplicación para los usuarios existentes. El uso de SALP con Universal Links garantiza que los usuarios se enruten correctamente: se abre la app si está instalada o se envía a los usuarios nuevos a la tienda de aplicaciones cuando es necesario.

</Accordion>

<Accordion title="¿Puedo usar OneLink para redireccionar en WeChat?">

WeChat anula los deep links de Android e iOS y envía a los usuarios a una página web. Desde esta página web, el usuario debe hacer clic en el botón **Opciones** y optar por abrir la página en el navegador. Como resultado, los usuarios se encuentran con una experiencia interrumpida que aumenta las posibilidades de que caigan en el funnel de conversión.

Para solucionar esto, OneLink puede reconocer clics en WeChat y cargar una landing page exclusiva que le indica al usuario que haga clic en el botón de opciones y luego en la opción **Abrir en el navegador**. Esto, a su vez, abre la URL de redireccionamiento definida en la configuración de plantilla de OneLink.

<Image align="center" alt="WeChat_a.jpg" src="https://files.readme.io/49c03a10d458f6ce71fd6448e922294682ac9239775534c6264c29151ec1ea6d-30192900489105.jpg" />

Si el idioma registrado del usuario de WeChat es el chino, OneLink genera una versión localizada de la landing page:

<Image align="center" alt="WeChat_b.jpg" src="https://files.readme.io/502ef821a122459ab991f2a507c720f25fcac7129eb647a01290e8cabfa7a34e-30192887085841.jpg" />

</Accordion>

<Accordion title="¿Por qué los usuarios de Android con la aplicación instalada se redirigen a una URL web y no a la aplicación cuando hacen clic en un enlace en la vista web de Facebook?">

Por lo general, es posible abrir la aplicación y crear deep links desde un anuncio en Facebook. Sin embargo, si se cumplen las siguientes condiciones, Facebook no podrá abrir la aplicación para los usuarios actuales de la aplicación desde la URL de OneLink. En su lugar, todos los usuarios, incluidos los que tienen la aplicación, se envían a la URL definida en la plantilla de OneLink, o en el valor del parámetro **af\_android\_url**, **af\_r** o **af\_custom\_android\_url**:

* El usuario tiene un dispositivo móvil Android.
* Se hace clic en el enlace en la aplicación de Facebook.
* El enlace conduce a una página HTML que se abre en la vista web de Facebook (ya sea un sitio o una landing page de una aplicación social).
* La página HTML contiene un enlace con un **af\_dp** (con un esquema URI) y una configuración de redireccionamiento de URL en la plantilla de OneLink o en un parámetro (uno de los siguientes): **af\_android\_url**, **af\_r** o **af\_custom\_android\_url**).

</Accordion>

<Accordion title="¿Por qué al hacer clic en el vídeo en una campaña pagada de anuncios web de Meta se abre una página en blanco en iOS?">

Cuando se inserta un enlace personalizado de OneLink detrás del vídeo en una campaña pagada de anuncios web de Meta, al hacer clic en el vídeo en iOS desde la aplicación de Facebook se requiere una página de destino de aplicación social (SALP) para redirigir al usuario a la tienda de aplicaciones. Si no hay ninguna SALP configurada, al hacer clic en el vídeo el resultado es una página en blanco.

</Accordion>

<div id="testing-faq" />

### Preguntas frecuentes sobre las pruebas

<Accordion title="¿Cómo puedo realizar pruebas A/B para la landing page de aplicaciones de redes sociales?">

La <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">landing page de aplicaciones de redes sociales</Anchor> ofrece a los usuarios una experiencia de inicio de aplicación perfecta al utilizar OneLink en aplicaciones de redes sociales. Quizás te preocupe que, al agregar un paso al funnel, las tasas de conversión disminuyan. Pero la verdad es que sin la landing page, las trayectorias de los usuarios generalmente se interrumpen, lo cual da como resultado tasas de conversión muy bajas.

Si aún no estás totalmente convencido, ¿por qué no pruebas?

Realiza una <Anchor target="_blank" href="/marketers/es/docs/create-a-b-tests">prueba A/B</Anchor> de tu enlace personalizado en aplicaciones de redes sociales, con la landing page de aplicaciones de redes sociales y sin ella.

**Para realizar la prueba A/B de la landing page de aplicaciones de redes sociales, debes hacer lo siguiente:**

1. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Crea un enlace de OneLink</Anchor> (llamado Link1) para usar con aplicaciones de redes sociales. No configures la landing page de aplicaciones de redes sociales para este enlace.
2. Agrega el parámetro de atribución **af\_adset**.
3. Agrega el parámetro de atribución **af\_ad** con el valor "no lp".
4. Prueba el Link1 fuera de las aplicaciones de redes sociales y verifica que el enlace funciona y que inicia tu aplicación correctamente.
5. Duplica el Link1 y denomínalo Link2.
6. Cambia el valor del parámetro de atribución **af\_ad** a "using lp".
7. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Crea la landing page de aplicaciones de redes sociales</Anchor> solo para Link2.
8. Publica 2 entradas diferentes en la **misma** aplicación de redes sociales, usando Link1 y Link2.  
   No te preocupes porque cada enlace produce una cantidad de clics diferente. El KPI que importa es la tasa de conversión final de cada enlace.
9. **Revisa los resultados de la prueba A/B después de que se haya creado suficiente tráfico.**
   1. Ve al dashboard general de AppsFlyer y desplázate hacia abajo hasta la tabla **Reporte de rendimiento agregado**.
   2. Link1 y Link2 tienen la misma fuente de medios, campaña y nombre de anuncio. Baja hasta el conjunto de anuncios específico.
   3. Compara las tasas de conversión (y otros KPIs) de los usuarios que hicieron clic en Link1 o Link2.

</Accordion>

<Accordion title="¿Cómo puedo omitir la ventana de diálogo de selección de aplicaciones?">

Si ves la ventana de diálogo de selección de aplicaciones cuando pruebes tus enlaces OneLink, asegúrate de <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing">firmar tu aplicación</Anchor>, incluso si es una <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing#debug-mode">aplicación de debug.</Anchor> El certificado que usas para firmar la aplicación es el mismo que usas para <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-for-deep-linking-and-deferred-deep-linking#generating-a-sha256-fingerprint">generar el fingerprint SHA256</Anchor> cuando configuras OneLink para App Links.

</Accordion>

<div id="deep-linking-faq" />

### Preguntas frecuentes sobre deep linking

<Accordion title="¿Qué métodos de deep linking deben implementarse?">

Tus desarrolladores deberían implementar el método de deep linking unificados (UDL) para deep linking. Consulta nuestras <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">instrucciones completas para deep linking</Anchor>.

Los Universal Links de iOS y App Links de Android son **métodos de inicio de aplicaciones, que en realidad no crean deep links para los usuarios** (enviándolos a contenido específico dentro de la aplicación). El método de esquema URI puede iniciar la aplicación y la conexión de los usuarios a través de deep links (a través del parámetro de enlace personalizado **af\_dp**), pero solo debe configurarse para el inicio de la aplicación. Su uso principal es como un método alternativo para los Universal Links y App Links, y para iniciar aplicaciones para usuarios con versiones del sistema operativo Android anteriores a la 6.0.

Una vez que se inicia la aplicación utilizando cualquiera de estos métodos, el SDK de AppsFlyer suministra el valor **deep\_link\_value** especificado en el enlace de atribución personalizado. Este valor debe entregarse a través del método UDL implementado por tus desarrolladores.

</Accordion>

<Accordion title="¿Se puede usar el esquema URI (parámetro af_dp) para deep linking?">

**Sí,** pero no se recomienda. Idealmente, deberías usar **deep\_link\_value** para los deep links y el esquema URI como método alternativo para iniciar la aplicación sin deep links (a través del parámetro **af\_dp**). Sin embargo, si ya tienes el esquema URI configurado para deep linking, con parámetros adicionales concatenados como parte de la ruta de acceso del URI (por ejemplo, greatapp://param1/param2), no es necesario cambiar la configuración o el código existentes; el esquema URI seguirá funcionando.

**La práctica recomendada para agregar parámetros personalizados es a través de la página de configuración de enlaces personalizados**.

</Accordion>

<div id="ios-14-faq" />

### Preguntas frecuentes sobre iOS 14

<Accordion title="¿Los deep linking de OneLink funcionan para iOS 14?">

No hay ningún impacto en la experiencia del usuario para los usuarios de iOS 14 que tengan deep links desde campañas en ad networks y medios propios mediante el método UDL. El método heredado puede impedir deep linking.

A efectos de atribución/reportes, AppsFlyer usa el IDFA o el IDFV cuando están disponibles. Si no hay IDFA o IDFV, se puede utilizar un modelado probabilístico. A partir de iOS 14.5+, el modelo probabilístico se limita al contexto de los medios propios, la promoción cruzada y los flujos acordados de web-to-app.

</Accordion>

<Accordion title="¿Los deferred deep linking de OneLink funcionan para iOS 14?">

No hay ningún impacto en la experiencia del usuario para los usuarios de iOS 14 que tienen deferred deep linking de campañas en ad networks y medios propios mediante el método UDL. El método heredado puede impedir el deferred deep linking.

A efectos de atribución/reportes, AppsFlyer usa el IDFA o el IDFV cuando están disponibles. Si no hay IDFA o IDFV, se puede utilizar un modelado probabilístico. A partir de iOS 14.5+, el modelo probabilístico se limita al contexto de los medios propios, la promoción cruzada y los flujos acordados de web-to-app. Recomendamos a los clientes que desean implementar deferred deep linking de ad networks y medios propios que utilicen el SDK V6.1.0+ de AppsFlyer para iOS que aceptaron la ATT (si es necesario), mitiguen cualquier impacto en la atribución y se beneficien de tiempos de respuesta más rápidos.

</Accordion>

<div data-zendesk-anchors="onelink-troubleshooting-guide=gu%C3%ADa-de-resoluci%C3%B3n-de-problemas-de-onelink 01H7WPYJV9CQ1J6J3PFCEQFGB0=gu%C3%ADa-de-resoluci%C3%B3n-de-problemas-de-onelink onelink-frequently-asked-questions=preguntas-frecuentes-sobre-onelink 01H7WPYJV9H52P659N8JPRX2TY=preguntas-frecuentes-sobre-onelink onelink-template-faq=preguntas-frecuentes-sobre-las-plantillas-de-onelink 01H7WPYJV9TJRKHFZ77DFMKDDG=preguntas-frecuentes-sobre-las-plantillas-de-onelink deep-linking=enlaces-profundos 01H7WPYJV9JSQ5FV73YCE3H5AF=enlaces-profundos onelink-link-faq=preguntas-frecuentes-sobre-los-enlaces-de-onelink 01H7WPYJVAPNYAQ1SH4FBX4Z9F=preguntas-frecuentes-sobre-los-enlaces-de-onelink fallback-urls=url-alternativas 01H7WPYJVACCGVJD1Z7ZPVG2SQ=url-alternativas forced-deep-linking=deep-linking-forzado 01H7WPYJVA1W3HYYJJFQM01136=deep-linking-forzado onelink-parameter-faq=preguntas-frecuentes-sobre-los-par%C3%A1metros-de-onelink 01H7WPYJVAGRVWHRVMZVQG1ZVE=preguntas-frecuentes-sobre-los-par%C3%A1metros-de-onelink integrated-partner-faq=preguntas-frecuentes-sobre-los-partners-integrados 01H7WPYJVB8ZZSKFT1V01EN6QF=preguntas-frecuentes-sobre-los-partners-integrados testing-faq=preguntas-frecuentes-sobre-las-pruebas 01H7WPYJVC1PJJDA0GGT1DVVCF=preguntas-frecuentes-sobre-las-pruebas deep-linking-faq=preguntas-frecuentes-sobre-deep-linking 01H7WPYJVCTM39HKCG9JN03BN6=preguntas-frecuentes-sobre-deep-linking ios-14-faq=preguntas-frecuentes-sobre-ios-14 01H7WPYJVCVCVWHJW4RH85KC40=preguntas-frecuentes-sobre-ios-14" />

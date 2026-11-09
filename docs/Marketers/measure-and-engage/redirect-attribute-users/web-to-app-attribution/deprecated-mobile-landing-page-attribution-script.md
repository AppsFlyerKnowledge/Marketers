---
title: '[Obsoleto] script de atribución de la página de destino móvil'
deprecated: true
metadata:
  keywords:
    - Landing Page
    - Facebook
    - Adwords
    - Advertisers
    - Agencies
    - GCLID
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - Smart Banners and Scripts
  created_at: '2020-12-16T17:28:55Z'
  edited_at: '2026-08-12T12:25:15Z'
  id: 360016643258
  locale: es
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/es/articles/360016643258
---
> **En resumen:** Este script dejó de estar en desuso el 17 de diciembre de 2020 y se reemplazó por el <Anchor target="_blank" href="/marketers/es/docs/onelink-smart-script-overview">Smart Script de OneLink</Anchor>. Esta versión sigue funcionando, pero no se actualizará ni cambiará. El script genera URL que se incrustan detrás de un botón en tu sitio web móvil y redirige a los visitantes para que descarguen tu aplicación. Las URL también admiten la atribución de instalaciones y los enlaces profundos.

<Image align="center" alt="5648_Sunset_and_deprecation-01.png" src="https://files.readme.io/f2a154145e26577b698d00c4c3719be3eea7298576e6883bd47e6fb42897c71a-360015062398.png" />

**<Anchor target="_blank" href="/marketers/es/docs/onelink-smart-script-overview">Migrar a Smart Script de OneLink</Anchor>**

Las páginas de destino son una técnica muy común entre los marketers digital. Permiten a los marketers capturar los detalles de sus clientes potenciales para el remarketing, incluso si estos usuarios no generan conversiones al principio.

Sin embargo, para la adquisición de usuarios móviles, la estrategia de la página de destino tiene ventajas y desventajas.

<div id="the-upsides" />

#### Ventajas:

* Los clientes potenciales, que eventualmente puedan instalarla, deberían estar más comprometidos con la aplicación.
* Los servicios más complicados (por ejemplo, los servicios financieros) requieren más explicaciones para convertir sus clientes potenciales, lo que se habilita en las páginas de destino.

<div id="the-downsides" />

#### Desventajas:

* El embudo más largo reduce el número final de clientes potenciales convertidos.
* Es más difícil atribuirlo desde el punto de vista técnico.

<div id="the-challenges-of-mobile-attribution-on-landing-pages" />

## Desafíos de la atribución móvil en las páginas de destino

* **Las diferentes fuentes de medios requieren diferentes métodos** para completar el escenario de la página de destino con los datos de atribución correctos.
* **El modelo de atribución del último clic puede provocar la pérdida de la atribución correcta** si la página de destino tiene sus propios enlaces de atribución.
* **Los visitantes directos del sitio web se registran como orgánicos**, a menos que la página de destino tenga sus propios enlaces de atribución.
* **Los visitantes de escritorio se registran como orgánicos**, a menos que la página de destino tenga un método para registrar sus conversiones en usuarios móviles.

<div id="the-solution" />

## La solución

Para resolver los problemas de atribución de la página de destino mencionados, debes implementar un flujo de JavaScript en tu página de destino. Ofrecemos una implementación de script de muestra que puedes usar. Asegúrate de ajustar el script para que se ajuste a tus necesidades.

En algunos casos, también tendrás que hacer algunos ajustes en tus campañas.

Los siguientes escenarios cubren los requisitos para todos los casos posibles de fuentes de medios.

<div id="landing-page-scenarios" />

## Escenarios de páginas de destino

Sigue las instrucciones de implementación que aparecen a continuación **para todas las fuentes de medios** que envían clientes potenciales a tus páginas de destino.

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="Anuncios de Meta: atribución multiplataforma">

<div id="description" />

#### Descripción:

Los Anuncios de Meta son un SRN, que no utiliza enlaces de atribución externos.

Cuando se lanza la primera aplicación, AppsFlyer consulta los Anuncios de Meta para ver si el usuario ha interactuado anteriormente (en los últimos 28 días) con un anuncio publicado por un anunciante en la aplicación de Facebook. Si lo han hecho, los Anuncios de Meta se autoatribuyen.

Los Anuncios de Meta también se atribuyen a la multiplataforma, lo que significa que el usuario puede interactuar con cualquier tipo de campaña, móvil o no, en cualquier plataforma, para que los Anuncios de Meta lo atribuyan a sí mismo.

<div id="conclusion" />

#### Conclusión:

Un cliente potencial con el ID de dispositivo disponible, que proviene de la aplicación de Facebook y va a una página de destino, se atribuye correctamente a los Anuncios de Meta. Esto ocurre independientemente del nuevo clic registrado en la página de destino.  
Sin embargo, cuando los usuarios optan por no compartir su ID de dispositivo, como se espera con los usuarios de iOS 14 durante 2021, es posible que la atribución multiplataforma de Anuncios de Meta deje de funcionar.

**Cuando el uso compartido de ID de dispositivo pase a ser opcional, utiliza el [método Otros SRN](/docs/deprecated-mobile-landing-page-attribution-script#other-srns-add-parameter) para los Anuncios Meta.**

* Los usuarios nuevos que compartan la ID de su dispositivo se atribuirán correctamente a los Anuncios de Meta.
* Los usuarios nuevos que no compartan su ID de dispositivo se atribuirán a «Facebook\_LP».

<div id="instructions" />

#### Instrucciones:

1. En tu cuenta de Anuncios de Meta, crea una **campaña de «Tráfico» o «Conversiones» con la atribución móvil habilitada** para enviar clientes potenciales a tu página de destino.
2. Botón de descarga de Android de la página de destino: enlace directo a Google Play.
3. Botón de descarga de la página de destino para iOS: enlace directo a iTunes (O enlace de atribución **sin el ID del dispositivo**).

<div id="what-the-script-does" />

#### ¿Qué hace el script?

El script de la página de destino no realiza cambios. El script está diseñado para detectar a un usuario que proviene de la aplicación de Facebook. Si lo hace, no hace nada. Deja los enlaces directos de la página de destino a las tiendas de aplicaciones tal como están. Esto evita que se grabe otro clic que podría afectar al CTR.

En el script, busca un método llamado ***isFacebook ()*** para aprender más sobre lo que hace el script cuando un usuario proviene de la aplicación de Facebook.

</Accordion>

<div id="google-ads-gclid-offline-conversion-upload" />

<Accordion title="Google Ads: Carga de conversiones sin conexión a GCLID +">

<div id="description-1" />

#### Descripción:

El proceso habitual para instalar la atribución de las campañas de Google Ads requiere que los clientes potenciales que hacen clic se redirijan a la URL de la página de la tienda de la aplicación.

Por lo tanto, cuando redirijas clientes potenciales de Google Ads a una página de destino, utiliza un mediador para establecer la conexión entre la instalación móvil y el clic original en la campaña de Google Ads para dispositivos no móviles.

<div id="conclusion-1" />

#### Conclusión:

La solución para Google Ads consta de dos partes.

La primera parte se ocupa de **atribuir en AppsFlyer** a los usuarios móviles que llegan a la página de destino desde Google e instalar la aplicación desde allí. Requiere etiquetar las URL en las que se hace clic desde Google, identificarlas en la página de destino y crear un OneLink dinámico con los datos de la URL.

La segunda parte se ocupa de **notificar a Google Ads** sobre estas instalaciones móviles mediante el método de subida de conversiones offline de Google.

<div id="note" />

> 📘 **Nota:**
>
> Esta solución GCLID no es oficialmente compatible ni recomendada por Google.
> En caso de que Google deje de utilizar el parámetro GCLID, cambiaremos el script para admitir los cambios.
> Recomendamos seguir este artículo haciendo clic en el botón ***Seguir*** en el encabezado del artículo para estar informado cuando haya una actualización del artículo o del script adjunto.

<div id="instructions-1" />

#### Instrucciones:

Parte 1: Atribuir a Google Ads en AppsFlyer

En el panel de control de Google: **habilita el etiquetado automático** (<Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">aquí verás cómo se hace</Anchor>).

Con el etiquetado automático activado, **la URL de la página de destino contiene el parámetro *GCLID***.

Ejemplo de URL: `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}`

Al cargar tu página de destino -

1. Activar la función ***GenerateURL*** de Javascript
2. La función (ver más abajo) busca el parámetro ***GCLID*** y crea una URL larga de OneLink que contiene su valor en el parámetro af\_sub1 (puedes usar cualquiera de los <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">parámetros de suscriptor</Anchor> af\_sub1 - af\_sub5).
3. El botón de descarga de la página de destino utiliza la URL de OneLink generada.  
   Ejemplo de URL de OneLink: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}`
4. Los nuevos usuarios de dispositivos móviles se atribuyen a la fuente de medios **google\_lp** y a la campaña CAMPAIGN\_NAME (opcional).
5. No se envía ningún postback a la fuente de medios.

En este momento, las instalaciones se registran en AppsFlyer en la fuente de medios ***google\_lp***, con el GCLID, pero no en Google Ads.

Parte 2: Subir las instalaciones a Google como conversiones offline

**Este paso solo es necesario si quieres que las conversiones se registren en la plataforma de Google Ads.**

Para los usuarios atribuidos a google\_lp, los raw data de AppsFlyer ahora muestran el valor de GCLID en la columna **af\_sub1.** El GCLID es necesario para subir conversiones sin conexión a Google Ads (puedes encontrar más información sobre el proceso <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">aquí</Anchor>).

Las conversiones se pueden subir manualmente o mediante una API de Adwords (más información sobre la API <Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">aquí</Anchor>).

Puedes exportar los CSV con esta información desde tu cuenta de AppsFlyer o puedes obtener estos datos de la Push API en tiempo real para cada instalación.

<div id="tip" />

> 👍 **Consejo**
>
> También puedes ver las palabras clave que tus usuarios buscaron en el raw data de AppsFlyer de forma similar a como obtuviste el GCLID:
>
> 1. Para el registro de palabras clave, debes incluir el <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2375447">parámetro ValueTrack</Anchor> de palabras clave en la URL final de Google Ads a la página de destino
>    Ejemplo de URL: `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}&keyword={USER_KEYWORD}`
> 2. La función Javascript (ver más abajo) busca el parámetro de ***palabra clave***
> 3. El valor se añade a la URL de OneLink generada en af\_keywords
>    Ejemplo de URL de OneLink: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}&af_keywords={USER_PARSED_KEYWORD}`
>
> La siguiente función JS ya contiene el código para analizar también el parámetro de la palabra clave.

<div id="what-the-script-does-1" />

#### ¿Qué hace el script?

Google Ads lleva consigo un parámetro gclid. El script busca este parámetro en la URL de la página de destino. Si lo ve, crea el OneLink de forma que refleje que el usuario proviene de Google Ads. A continuación, el script coloca el OneLink como enlace detrás de los botones de descarga en la página de destino.

En el script, busca **gclidValue** para saber cómo el script detecta los usuarios que vienen de Google Ads y crea el OneLink en consecuencia.

</Accordion>

<div id="other-srns-add-parameter" />

<Accordion title="Otros SRN: agregar parámetro">

<div id="description-2" />

#### Descripción:

Otras <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#srns-integradas-con-appsflyer">SRN</Anchor>, por ejemplo, Snapchat o Twitter, no son multiplataforma como los Anuncios de Meta y requieren un poco de trabajo para que se les atribuya a los usuarios móviles.

Tus campañas con otras SRN llevan a tus usuarios a la página de destino y se le factura en función de los clientes potenciales que hacen clic, sin relación con ningún usuario móvil derivado.

<div id="conclusion-2" />

#### Conclusión:

Al definir la URL de la página de destino de una campaña en SRN (además de los Anuncios de Meta y Google Ads), añade un parámetro de ID de partner a la URL, que indique el SRN original.  
La página de destino lanza un código JavaScript (ver más abajo) que analiza ese parámetro y crea una URL de OneLink, que tiene el valor de ID de partner. Cuando los usuarios de dispositivos móviles hacen clic en ese OneLink y lo instalan, se les atribuye a la fuente de medios indicada.

<div id="instructions-2" />

#### Instrucciones:

En tu cuenta SRN:

1. Crea una campaña que no sea móvil.
2. Al definir la URL de la página de destino, añade un parámetro Partner ID + de página de destino a la URL (que no es un enlace de atribución de AF). El formato es "***&af\_pid=srn\_lp***». (ver el ejemplo siguiente)

Al cargar tu página de destino -

1. Activar la función ***GenerateURL*** de Javascript
2. La función busca el parámetro ***af\_pid*** y crea una URL de OneLink que contiene su valor en el parámetro ***pid***
3. El botón de descarga de la página de destino utiliza la URL de OneLink generada.
4. Los nuevos usuarios móviles se atribuyen a la fuente de medios personalizada «Partner ID + landing page»
5. No se envía ningún postback a la fuente de medios.

Si especificas el nombre real del SRN, por ejemplo, twitter\_int, es posible que se envíe postback a esta SRN. Esto podría resultar en cargos dobles. Consulta la nota siguiente para ver los nombres alternativos.

El script en sí contiene lógica para evitar que utilices estos nombres. Búscalo `var SRNs` en el script. Deberías ver una lista de nombres de SRN y una condición que comprueba si `pidValue` es alguno de estos nombres. Elimina esta lógica cuando hayas terminado de probar el script.

<div id="note-1" />

> 📘 **Nota:**
>
> Si vas a enviar usuarios a tu página de destino, te recomendamos que incluyas el siguiente parámetro en la URL de la página de destino:
>
> * Para Twitter: usa "***&af\_pid=twitter\_lp***"
> * Para Snapchat: usa "***&af\_pid=snapchat\_lp***»
> * Para Doubleclick: usa "***&af\_pid=doubleclick\_lp***"
> * Para publicaciones de Anuncios de Meta (no pagadas): usa "***&af\_pid=fbpost\_lp***»
> * Para Oath (anteriormente Yahoo Gemini): usa "***&af\_pid=oath\_lp***»

<div id="what-the-script-does-2" />

#### ¿Qué hace el script?

El script ve el parámetro af\_pid en la URL de la página de destino y concluye que el usuario proviene de un SRN o de alguna otra red personalizada. El script crea un OneLink en consecuencia y lo establece como el enlace detrás del botón de descarga en la página de destino.

Para obtener más información sobre lo que hace el script, busca **pidValue** en el script.

</Accordion>

<div id="attribution-links-redirect-with-af_r" />

<Accordion title="Enlaces de atribución: redirigir con af_r">

<div id="description-3" />

#### Descripción:

Los enlaces de atribución se utilizan para cualquier fuente de medios que no sea una SRN. Esto incluye miles de partners integrados y cualquier medio propio al que desee atribuir.

Por suerte, la solución para la atribución de páginas de destino cuando se utilizan los enlaces de atribución de AppsFlyer es sencilla (y similar a la solución para los Anuncios de Meta).

<div id="conclusion-3" />

#### Conclusión:

el enlace de atribución redirige al cliente potencial a una página de destino y, de este modo, también se encarga de la atribución correcta (si sigue una instalación móvil).

Todo lo que queda por hacer es NO impedir la atribución correcta con otro último clic.

<div id="instructions-3" />

#### Instrucciones:

1. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">Crea el enlace de atribución</Anchor> para la fuente de medios.
2. Añade el <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection">parámetro de página de destino</Anchor> que lleva a tu página de destino al enlace de atribución.
3. Añádelo `&af_redirect=true` al valor de la página de destino en **cualquier parámetro de redirección** (es decir, af\_r, af\_ios\_url y af\_android\_url) del enlace de atribución.  
   Ejemplo: `https://yourapp.onelink.me/abcd?pid=email&c={CAMPAIGN_NAME}&af_r=http://www.yoursite.com/yourlandingpage?af_redirect=true`
4. **Opcional**: agrega el ID del dispositivo (GAID o IDFA) al enlace de atribución para permitir la atribución mediante la coincidencia de ID en lugar del modelado probabilístico
5. Botón de descarga de Android de la página de destino: enlace directo a Google Play.
6. Botón de descarga de iOS de la página de destino: enlace directo a iTunes  

   <div id="note-2" />

   > 📘 **Nota:**
   >
   > El script y la página de muestra HTML ofrecen la opción de configurar un botón de descarga que sirva tanto para Android como para iOS. Lea los comentarios del script para obtener información sobre cómo implementarlo.


<div id="what-the-script-does-3" />

#### ¿Qué hace el script?

El script busca el parámetro **af\_redirect** en la URL de la página de destino. Si lo ve, no hace ningún cambio en los botones de descarga de la página de destino. Esto se debe a que el parámetro af\_redirect indica que el usuario llega a la página de destino después de hacer clic. Por lo tanto, no hay necesidad de enlaces de atribución adicionales.

Para obtener más información sobre lo que hace el script para gestionar los casos en los que los usuarios llegan a la página de destino después de hacer clic en un enlace de atribución, consulta el método **isAFlink ()** en el script.

</Accordion>

<div id="links-with-utm-parameters-dynamic-onelink" />

<Accordion title="Enlaces con parámetros utm: OneLink dinámico">

<div id="description-4" />

#### Descripción

Es posible que tengas fuentes de tráfico que redirijan a los usuarios a tu página de destino mediante enlaces con parámetros UTM.

<div id="conclusion-4" />

#### Conclusión:

ISi la URL original NO es un enlace de atribución de AppsFlyer, el script busca los parámetros ***utm\_source*** y ***utm\_campaign*** en el enlace. Si existen, el script prepara una URL de OneLink, que los tiene como nombre de la fuente de medios (pid) y nombre de la campaña (c), respectivamente.

Ten en cuenta que con los enlaces de atribución de AppsFlyer, que también contienen parámetros UTM, se utilizan los parámetros de AppsFlyer, en lugar de los UTM.

<div id="instructions-4" />

#### Instrucciones:

En la fuente de los medios:

1. Asegúrate de que el código ***utm\_source*** existe en el enlace.
2. El parámetro ***utm\_campaign*** es opcional pero muy recomendable.

Al cargar tu página de destino -

1. Activar la función ***GenerateURL*** de Javascript
2. La función busca los parámetros ***utm\_source*** y ***utm\_campaign*** y crea una URL de OneLink que contiene sus valores
3. El botón de descarga de la página de destino utiliza la URL de OneLink generada.
4. Los nuevos usuarios móviles se atribuyen al valor de ***utm\_source*** como fuente de medios.
5. No se envía ningún postback a la fuente de medios.

<div id="what-the-script-does-4" />

#### ¿Qué hace el script?

El script busca los parámetros UTM en la URL de la página de destino. Si encuentra alguno, lo convierte en parámetros de OneLink. De esta forma, la información de la campaña se transfiere a la atribución final.

</Accordion>

<div id="mobile-organic-visitors-onelink-with-pidwebsite" />

<Accordion title="Visitantes orgánicos móviles: OneLink con pid=website">

<div id="description-5" />

#### Descripción

Los visitantes orgánicos móviles son, por definición, clientes potenciales directos de la web móvil de fuentes desconocidas. Rara vez visitan páginas de destino dedicadas, pero es posible que la gran mayoría de las instalaciones móviles provengan del sitio web del anunciante.

<div id="conclusion-5" />

#### Conclusión:

Si tienes una cantidad significativa de tráfico orgánico móvil desde tu sitio web, es muy recomendable registrar los datos de atribución de tu propio tráfico.

<div id="instructions-5" />

#### Instrucciones:

Para atribuir a los visitantes orgánicos móviles, el sitio web debe tener botones de ***descarga*** o ***instalación***, con un enlace de atribución de OneLink detrás de ellos. OneLink permite diagnosticar el tipo de dispositivo y redirigir el lead a la tienda de aplicaciones correcta en función de este.

Para obtener información sobre cómo configurar y crear las URL de OneLink, haz clic <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">aquí.</Anchor>

<div id="tip-1" />

> 👍 **Consejo**
>
> Añade «&pid=website» a tu enlace de atribución para atribuir a todos estos visitantes a tu sitio web.
> En cada página de tu sitio web, que tenga un botón de descarga/instalación con un enlace de atribución, añade «&c= `{PAGE NAME}`». Esto puede ayudarte a encontrar las páginas con mayor y menor conversión en tu sitio web.

<div id="what-the-script-does-5" />

#### ¿Qué hace el script?

Al agotar todas las demás opciones, el script determina que el usuario es un usuario orgánico que no proviene de ninguna campaña. El script crea un OneLink que refleja eso y lo coloca como enlace detrás del botón de descarga en la página de destino.

</Accordion>

<div id="desktop-visitors-telephoneemail-form" />

<Accordion title="Visitantes de escritorio: formulario de teléfono/correo electrónico">

<div id="description-6" />

#### Descripción

Todas las opciones mencionadas anteriormente suponen que los usuarios utilizan dispositivos móviles cuando interactúan con la campaña y la página de destino.

Pero, ¿qué pasa con los usuarios de escritorio?

Los usuarios de escritorio pueden llegar a tu página de destino o sitio web y, después, visitar «de forma independiente» la tienda de aplicaciones con sus dispositivos móviles e instalar la aplicación móvil. Sin el compromiso anterior con los dispositivos móviles, es imposible atribuir a estos usuarios y, por lo tanto, se los etiqueta como «orgánicos».

<div id="conclusion-6" />

#### Conclusión:

Una excelente solución a este problema de atribución es usar un **formulario de texto para descargar en la página de destino**, solo para usuarios de escritorio. A continuación, se enviará al dispositivo móvil un SMS/correo electrónico con la URL de OneLink.

<div id="instructions-6" />

#### Instrucciones:

1. Identificar que un visitante es un usuario de escritorio
2. Cuando el usuario escriba su número de teléfono, envíale un mensaje de texto con un enlace a tu aplicación, con una URL corta de OneLink. También puedes pedirles su dirección de correo electrónico para enviarles mensajes de descarga de aplicaciones.
3. El uso de OneLink es crucial en este caso, ya que no se conoce la plataforma del dispositivo móvil cuando se envía el mensaje a los usuarios. Las funciones de diagnóstico y redirección de OneLink se encargan de ello por ti.
4. Añade «&pid=desktop\_website» a la URL de OneLink para identificar esta fuente.
5. Añade «&c= `{PAGE NAME}`» para ayudarte a encontrar las páginas con mayor y menor conversión en tu sitio web para usuarios de escritorio.

<div id="what-the-script-does-6" />

#### ¿Qué hace el script?

El script detecta el dispositivo o la plataforma en la que se encuentra el usuario. Si es de escritorio, el script devuelve un enlace a la URL de un formulario web y lo coloca detrás de los botones de descarga. Cuando el usuario hace clic en descargar, se le envía a un formulario web donde rellena sus datos para recibir un SMS o un correo electrónico con un enlace para descargar la aplicación.

Eres tú quien debes crear el formulario web y proporcionar la URL del mismo en el script. Para obtener más información, busca **isMobileDevice () en el script**.

</Accordion>

<div id="landing-page-javascript" />

## Javascript de página de destino

A continuación, puedes encontrar la implementación de código del javascript que realiza todo el alcance de la atribución de fuentes de medios y campañas en escenarios de páginas de destino. **Si quieres disponer de datos adicionales, como conjuntos de anuncios e identificadores de anuncios, debes realizar los ajustes necesarios en el script**.

Para tu comodidad, también puedes descargar el ejemplo de página de destino adjunto.

Debajo del código, encontrarás las instrucciones para adaptarlo a las necesidades de tu página de destino.

<div id="the-script" />

<Accordion title="El script">

Ten en cuenta lo siguiente antes de implementar el script:

* El script se ofrece solo como ejemplo. Abarca desde la página de destino común hasta el flujo de atribución. Adapta el script para que se ajuste a tus necesidades.
* El script busca parámetros específicos en la URL de la página de destino, como la fuente de medios, la campaña, las palabras clave, etc. Si quieres añadir más parámetros, como el identificador del sitio y los conjuntos de anuncios, para ello debes modificar el script.

```javascript
//Devuelve el valor de un parámetro existente en la URL de la página o ' ' si no existe.
function getParameterFromURL(name, url) {
  if (!url) url = window.location.href;
  name = name.replace(/[\[\]]/g, '\\$&');
  var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
    results = regex.exec(url);
  if (!results) return null;
  if (!results[2]) return '';
  return decodeURIComponent(results[2].replace(/\+/g, ' '));
}

function isMobileDevice() {
  return (typeof window.orientation !== "undefined") || (navigator.userAgent.indexOf('IEMobile') !== -1);
}

function getMobileOperatingSystem() {
  var userAgent = navigator.userAgent || navigator.vendor || window.opera;
  if (userAgent) {
    if (/android/i.test(userAgent)) {
      return "Android";
    }

    // Detección de iOS de: http://stackoverflow.com/a/9039885/177710
    if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
      return "iOS";
    }
  }
  return "unknown";
}

function isAFLink() {
  return getParameterFromURL('af_redirect');
}

// Nota: cuando el uso compartido del ID de dispositivo pase a ser opcional, deja de llamar a este método (o haz que siempre devuelva false)
function isFacebook() {
  if (document.referrer && document.referrer != "") {
    return document.referrer.toLowerCase().includes('facebook');
  } else {
    return false;
  }
}

// generateUrl devuelve la URL que se debe usar detrás de los botones de "Descarga" de iOS y Android en una página de destino, en función de la fuente del visitante de la página.
// De forma predeterminada, estos botones deberían dirigir a las páginas de las apps en iTunes y Google Play.
// Si estos enlaces deben mantenerse sin cambios, generateUrl devuelve ' '.
// De lo contrario, generateUrl devuelve la URL que se debe usar en AMBOS botones (en este caso, también se podría usar un único botón de descarga de la aplicación).
// Parámetros: isDebug; si es true, se muestran alertas en cada uno de los casos; de lo contrario, no.  	 
function generateUrl(isDebug) {
  var oneLinkURL = 'https://yourapp.onelink.me/abcd';   // **** Sustituye esta URL base de OneLink por la tuya ****
  var webFormURL = 'https://yoursite.com/webform.html'; // **** Sustituye esta URL de formulario web por la tuya para obtener el correo electrónico o el SMS del usuario ****
  var finalURL = "";
  var partnerIDParam = '?pid=';

  var campaignValue;
  if (getParameterFromURL('c')) {
    campaignValue = getParameterFromURL('c');
  } else if (getParameterFromURL('utm_campaign')) {
    campaignValue = getParameterFromURL('utm_campaign');
  } else if (document.getElementsByTagName('title')[0]) {
    campaignValue = document.getElementsByTagName('title')[0].innerText;
  } else {
    campaignValue = 'unknown';
  }
  var campaignParam = '&c=';
  var gclidParam = '&af_sub1=';
  var gclidValue = getParameterFromURL('gclid');
  var kwParam = '&af_keywords=';
  var pidValue;
  var kwValue = getParameterFromURL('keyword');

  if (getParameterFromURL('af_pid')) {
    pidValue = getParameterFromURL('af_pid');
  } else if (getParameterFromURL('utm_source')) {
    pidValue = getParameterFromURL('utm_source');
  }

  // Evita el uso de nombres reales de SRN. Elimina esta parte cuando hayas terminado de probar el script.
    var SRNs = [
    'twitter_int',
    'facebook_int',
    'snapchat_int',
    'doubleclick_int',
    'yahoogemini_int',
    'yahoojapan_int',
  ];

  if (SRNs.includes(pidValue)) {
  	alert("NO USES NOMBRES DE SRN EN af_pid o utm_source: usa los nombres indicados en la sección Other SRNs: Add Parameter del artículo sobre la página de destino\nhttps://support.appsflyer.com/hc/en-us/articles/360000677217#other-srns-add-parameter");
    return;
  }

  // Usuario de escritorio
  if (!isMobileDevice()) {
    return webFormURL;
  }

  // El usuario fue redirigido mediante el parámetro af_r en un enlace de atribución de AppsFlyer
  if (isAFLink()) {
    if (isDebug) {
      alert("Este usuario procede de AppsFlyer por redirección y está listo para atribuirse. \nMantén los enlaces directos a la tienda de aplicaciones.");
    }
    return; // en este caso, los enlaces originales a la tienda en los botones de instalación se mantienen igual

    /*
    Si quieres un botón de instalación en la página de destino que sirva tanto para iOS como para Android, descomenta el código de abajo
    El código identifica el sistema operativo y devuelve el enlace directo correspondiente a Google Play o iTunes

    if (getMobileOperatingSystem() === 'Android') {
      return 'direct link to Google Play';
    } 

    if (getMobileOperatingSystem() === 'iOS') {
      return 'direct link to iTunes';
    }
    */
  }

  // Google Ads
  if (gclidValue) {
    partnerIDParam += 'google_lp';
    campaignParam += campaignValue;
    gclidParam += gclidValue
    if (!kwValue) {
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam;
      if (isDebug) {
        alert("Este usuario procede de Google AdWords\n " + finalURL);
      }
      return finalURL;

    } else { // Google Ads con KW
      kwParam += kwValue;
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam + kwParam;
      if (isDebug) {
        alert("Este usuario procede de Google AdWords: hay una palabra clave asociada al anuncio\n " + finalURL);
      }
      return finalURL;
    }

  // Otras SRN y redes personalizadas  
  } else if (pidValue) {
    campaignParam += campaignValue;
    partnerIDParam += pidValue;
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("Este usuario procede de la SRN o red personalizada " + pidValue + "\n" + finalURL);
    }
    return finalURL;
  } else if (isFacebook()) {
    if (isDebug) {
      alert("Este usuario procede de un anuncio pagado de Facebook; no hagas nada. \nMantén los enlaces directos a la tienda de aplicaciones.");
    }
    return ' ';

  } else { // usuario móvil orgánico
    campaignParam += campaignValue;
    partnerIDParam += 'website'; //**** Sustituye el valor si quieres que los usuarios orgánicos se atribuyan a una fuente de medios distinta de 'website' ****
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("Este usuario procede de una fuente móvil desconocida.\n El usuario se atribuiría a la fuente de medios 'website' y a la campaña " + campaignParam + "\n" + finalURL);
    }
    return finalURL;
  }
}
```

</Accordion>

<div id="html-sample-for-landing-page" />

<Accordion title="Ejemplo de HTML para la página de destino">

```html Markup
<html>
<head>
  <title>Landing Page</title>
</head>
<body>
  <h1>Landing Page</h1>
  <!-- De forma predeterminada, los botones de instalación deben tener enlaces directos a las tiendas -->
  <div>
    <a id="andrd_link" href="https://play.google.com/store/apps/details?id=com.appsflyer.sampleapp"><img src="/images/andrd.png"alt=""></a>
  </div>
  <div>
    <a id="ios_link" href="https://itunes.apple.com/us/app/id3********"><img src="/images/ios.png" alt=""></a>
  </div>
  <!-- Si quieres que un único botón sirva tanto para Android como para iOS, usa en su lugar el código de abajo
  <a id="store_link" href=""><img src="download.png" alt=""></a>
  -->
  <script type="text/javascript" src="/landing-page-test.js"></script>
  <script type="text/javascript">
    window.onload = function () {
      var url = generateUrl(true);

      // se genera OneLink
      if (url) {
        document.getElementById('andrd_link').setAttribute('href', url);
        document.getElementById('ios_link').setAttribute('href', url);
      }

      // de lo contrario, si no se genera OneLink, significa que el usuario es redirigido
      // y los enlaces a la tienda en los botones se mantienen igual

      /* para la solución de un botón para Android y iOS, usa en su lugar el código de abajo

      document.getElementById('store_link').setAttribute('href', url);

      */

    };
  </script>
</body>

</html>
```

</Accordion>

<div id="tip-2" />

> 👍 **Consejo**
>
> Puedes implementar el fragmento de código javascript con Google Tag Manager. Google Tag Manager te facilita el control de cuándo y dónde se debe usar el javascript de la página de destino.

<div id="instructions-7" />

### Instrucciones

1. Activa el script ***GenerateURL*** al cargar cualquier página de su sitio web, a la que los visitantes puedan acceder directamente y que tenga botones de ***descarga*** para tus aplicaciones móviles.  

   <div id="important" />

   > 🚧 **Importante:**
   >
   > **De forma predeterminada, los botones de *descarga* deberían dirigir a las páginas de las aplicaciones en iTunes y Google Play**. Si estos enlaces se mantienen sin cambios (por ejemplo, el visitante proviene del enlace de atribución de AF o de los Anuncios de Meta), ***generateURL*** devuelve ' '. De lo contrario, devuelve la URL que se utilizará con AMBOS botones de descarga (en este caso también se podría usar un solo botón de ***descarga*** para cubrir ambas aplicaciones con OneLink).

2. Sustituye el valor del parámetro ***OneLinkURL*** por tu propia URL básica de OneLink en el formato exacto del marcador de posición.`https://yourapp.onelink.me/abcd`  
   OBLIGATORIO para atribuir los visitantes de todas las SRN (excepto los anuncios de pago de Anuncios de Meta) y para los visitantes orgánicos móviles.
3. Sustituye el valor del parámetro ***webFormURL*** por el enlace de tu propio formulario web. El formulario web debe poder recibir el correo electrónico o el SMS del usuario y enviar al dispositivo móvil del usuario un mensaje con una URL de OneLink para descargar la aplicación.  
   OBLIGATORIO para atribuir a los visitantes de escritorio.
4. Sustituye el valor del parámetro ***PartnerIDParam*** si deseas que los usuarios orgánicos móviles se atribuyan a una fuente de medios distinta a «sitio web».
5. De forma predeterminada, los usuarios se atribuyen a la página web en la que se encuentran cuando hacen clic en el botón ***Descargar***, a menos que se especifique otro nombre de campaña en la URL de la página de destino (`&c={CAMPAIGN_NAME}`). Para cambiarlo, sustituye el valor del parámetro ***campaignParam.***  
   Opcional para TODOS los escenarios, excepto los anuncios de pago de Anuncios de Meta.

<div id="viewing-the-results" />

## Visualización de los resultados

<Image align="center" alt="dashboard_landing_page_results.png" src="https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png" />

Al igual que con cualquier fuente de medios, puedes ver los resultados de tu página de destino en el panel de control de tu aplicación, en los raw data o mediante las API de AppsFlyer.

Si tu embudo de marketing móvil siempre lleva a tu página de destino, estas fuentes de medios representan lo siguiente:

| **Fuente** | **Descripción** |
| --- | --- |
| **orgánica** | Usuarios que no accedieron a la página de destino o que no interactuaron con ella. Como alternativa, los usuarios que sí interactuaron pero no fueron atribuidos por varios motivos, por ejemplo, pasaron la ventana retrospectiva de atribución antes de lanzar la aplicación. |
| **sitio web** | Usuarios móviles orgánicos que visitan tu página de destino o sitio web e instalan después |
| **Anuncios de Meta** | Usuarios de Anuncios de Meta de pago |
| **fbpost\_lp** | Usuarios de publicaciones virales de Anuncios de Meta no pagas |
| **google\_lp** | Usuarios de Google Ads |
| **[SRN]\_lp** | Usuarios de otras SRN, es decir,. Usuarios de otras SRN, como Twitter (twitter\_lp), Snapchat (snapchat\_lp), Doubleclick (doubleclick\_lp) u Oath (oath\_lp) |
| **ID de partner integrado** | Usuarios que provienen del anuncio de un partner integrado, que usa el enlace de atribución de AppsFlyer. Por ejemplo, inmobi\_int, tapjoy\_int |
| **Escritorio** | Los usuarios de escritorio rellenan el formulario web y completan una instalación después de hacer clic en el SMS o correo electrónico enviado a sus dispositivos móviles |
| **Otras fuentes** | Usuarios que provienen de fuentes de medios propios, que utilizan los enlaces de atribución de AppsFlyer. Por ejemplo, correo electrónico, sms, blog\_post, etc. |

<div id="onelink-for-landing-page-solution" />

## Solución OneLink para páginas de destino

OneLink™ es un enlace de atribución exclusivo de AppsFlyer, que se usa para la detección y redirección de dispositivos, o para la creación de enlaces profundos.

La solución de <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">página de destino de las aplicaciones sociales</Anchor> requiere que el anunciante tenga una URL básica de OneLink. Los usuarios que hacen clic en anuncios en las aplicaciones de redes sociales son redirigidos a una página de destino generada por AppsFlyer. A partir de ahí, pueden tener enlaces profundos o continuar instalando la aplicación.

AppsFlyer ofrece una variedad de plantillas de página de destino para aplicaciones de redes sociales. Las posiciones de los elementos en las plantillas son fijas, pero los elementos en sí se pueden personalizar, incluida la imagen de fondo o el color, los títulos, textos, imágenes, botones, etiquetas y más.

Si no has implementado OneLink para tu aplicación:

1. Configura <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">la plantilla de OneLink</Anchor>.
2. Crea una <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">URL de OneLink</Anchor> basada en la plantilla.
3. En el script, reemplaza https://yourapp.onelink.me/abcd por tu URL de OneLink.

<div data-zendesk-anchors="the-upsides=ventajas the-downsides=desventajas the-challenges-of-mobile-attribution-on-landing-pages=desaf%C3%ADos-de-la-atribuci%C3%B3n-m%C3%B3vil-en-las-p%C3%A1ginas-de-destino the-solution=la-soluci%C3%B3n landing-page-scenarios=escenarios-de-p%C3%A1ginas-de-destino description=descripci%C3%B3n conclusion=conclusi%C3%B3n instructions=instrucciones what-the-script-does=qu%C3%A9-hace-el-script description::7888dd9d=descripci%C3%B3n-1 conclusion::11bed45=conclusi%C3%B3n-1 instructions::5aa3290f=instrucciones-1 what-the-script-does::2a675257=qu%C3%A9-hace-el-script-1 description::650e3f28=descripci%C3%B3n-2 conclusion::a982e4bd=conclusi%C3%B3n-2 instructions::afffc83f=instrucciones-2 what-the-script-does::3fd4ce35=qu%C3%A9-hace-el-script-2 description::9c3fcdaa=descripci%C3%B3n-3 conclusion::bf993a93=conclusi%C3%B3n-3 instructions::350b4cb1=instrucciones-3 what-the-script-does::3dda504d=qu%C3%A9-hace-el-script-3 description::5150e1b5=descripci%C3%B3n-4 conclusion::d51c1aec=conclusi%C3%B3n-4 instructions::e083609=instrucciones-4 what-the-script-does::85ffec6c=qu%C3%A9-hace-el-script-4 description::f5a2038b=descripci%C3%B3n-5 conclusion::4593a93c=conclusi%C3%B3n-5 instructions::2e4dd2ee=instrucciones-5 what-the-script-does::d6370587=qu%C3%A9-hace-el-script-5 description::e20640cf=descripci%C3%B3n-6 conclusion::c818491=conclusi%C3%B3n-6 instructions::ba61ae3e=instrucciones-6 what-the-script-does::3668d917=qu%C3%A9-hace-el-script-6 landing-page-javascript=javascript-de-p%C3%A1gina-de-destino instructions::10da52a9=instrucciones-7 viewing-the-results=visualizaci%C3%B3n-de-los-resultados onelink-for-landing-page-solution=soluci%C3%B3n-onelink-para-p%C3%A1ginas-de-destino" />

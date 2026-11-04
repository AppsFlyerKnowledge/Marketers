---
title: Configura Smart Script para convertir a los visitantes de la web
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2021-12-13T09:57:23Z'
  edited_at: '2026-09-04T00:33:41Z'
  id: 4413588932241
  locale: es
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/es/articles/4413588932241
---
> **A simple vista:** **De un vistazo:** Configura el Smart Script de OneLink para convertir y atribuir a los visitantes de tu sitio web móvil, provenientes de cualquier fuente, en usuarios de la aplicación móvil.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

<div id="setup" />

## Configuración

Hay dos versiones de Smart Script de OneLink:

**OneLink Smart Script V2 (recomendado)**: Si está configurando OneLink Smart Script por primera vez, esta es la versión recomendada para utilizar. Se puede generar en la interfaz de usuario de AppsFlyer sin asistencia del desarrollador. Si por alguna razón se necesita un desarrollador, su parte laboral es más fácil. También se puede configurar mediante Google Tag Manager. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2">Ver instrucciones para desarrolladores</Anchor>

<Anchor target="_blank" href="/marketers/es/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1 (heredado)**</Anchor>: Si ya tiene configurado Onelink Smart Script, utilice la documentación de esta versión para mantener y editar este script. **Nota**: <Anchor target="_blank" href="/marketers/es/docs/legacy-onelink-smart-script-v1-setup">Nota</Anchor>: Aunque no es obligatorio, considera migrar a V2 para obtener correctamente las atribuciones por impresiones **usando el Smart Script de OneLink.**

<div id="set-up-onelink-smart-script" />

### Configuración de Smart Script de OneLink

Para configurar Smart Script, puedes:

* Insertar el script en tu sitio web.
* Utilizar Google Tag Manager.

<div id="scope-of-work" />

#### Alcance del trabajo

**¿Quién está involucrado?**

* **Anunciante**:
  * Decide qué debe contener la URL saliente basándose en los argumentos en el script que procesa la URL entrante. Esto determina la atribución y los datos de enlaces profundos que se incorporan a la URL saliente, ya sea manipulando la URL entrante o forzando ciertos valores.
  * Genera el Smart Script en la UI de AppsFlyer.
  * Se asegura de que todas las campañas que llevan al sitio web móvil tengan direcciones URL entrantes con parámetros para los que funciona el script.
  * <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Prueba el Smart Script</Anchor>.
* **Desarrollador web**:
  * Verifica que el script se ejecuta en el sitio/páginas móviles en las que quieres que funcione.
  * Utiliza el valor del resultado según sea necesario, por ejemplo, para colocarlo como un enlace bajo una CTA en tu sitio web.
  * Puede ser necesario para crear códigos QR utilizando el script.
  * Puede ser necesario para agregar manualmente argumentos avanzados al script.

**Requisitos previos**

* Una cuenta de AppsFlyer con una aplicación como mínimo.
* Una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor> que sirve como valor del [parámetro OneLinkURL](/docs/set-up-smart-script-to-convert-web-visitors#arguments).

<div id="how-to-create-a-onelink-smart-script" />

<Accordion title="Cómo crear un Smart Script de OneLink">

**Cómo crear un Smart Script de OneLink:**

1. En AppsFlyer, desde el menú lateral, seleccione **Engage** > **Web-to-app** > **Smart Script**.
2. ***Para nuevos usuarios***
   1. *Haz clic en el botón **Comenzar**.*
   2. *Sigue los pasos 4 y siguientes.*
3. Haz clic en el **botón + Nuevo Smart Script** en la parte superior de la página.
4. Sigue las instrucciones que aparecen en pantalla para nombrar tu Smart Script.
5. Selecciona una plantilla de OneLink en la que basar el script. La plantilla contiene la configuración básica de redireccionamiento.
6. Asigna los parámetros que debe contener la URL saliente. Estos parámetros se basan en los parámetros de la URL entrante. **Nota**: El parámetro de la fuentes de medios (pid) es obligatorio.
   1. Seleccione el parámetro/dimensión de salida que desea mapear.  
      A menudo, este es un nombre de parámetro de AppsFlyer que no se puede cambiar, pero en algunos casos es necesario ingresar el nombre de su parámetro.
   2. Decide y configura cuál debe ser el valor del parámetro de salida en función de uno u otro:
      * Parámetros de URL entrante: Enumere uno o más posibles parámetros de URL entrantes que desea que se reemplacen por el parámetro de URL saliente. Los valores de los parámetros de la URL entrante serán los valores de su parámetro de URL saliente.
        * Ejemplo: any\_param\_name, utm\_param\_name. Si se encuentra utm\_param\_name en la URL entrante, su valor se utilizará como el valor del parámetro de URL saliente seleccionado.
        * La secuencia de comandos inteligente busca en la lista de parámetros de izquierda a derecha y asigna la primera coincidencia a la URL del parámetro saliente.
        * Los desarrolladores hacen referencia a esta lista de parámetros como claves.
      * Valor predeterminado: Ingrese el valor predeterminado deseado para el valor del parámetro saliente para cuando no se encuentra un parámetro de URL entrante o si no incluye ningún parámetro de URL entrante.
        * Ejemplo: Ejemplo: para el parámetro saliente, si el parámetro URL entrante enumera any\_paramname, utm\_paramname, cuando no se encuentra ningún parámetro en la lista, el valor predeterminado se utilizará como el valor del parámetro saliente.
      * URL saliente:
        * Ejemplo: Ejemplo: Para el parámetro de campaña, si el valor en la URL entrante es campaign\_name, el valor en la URL saliente puede cambiarse a new\_campaign\_name.
   3. [Opcional] Haz clic en + Nuevo parámetro para asignar parámetros adicionales. Consulta todos los argumentos adicionales (configuraciones de parámetros) que puedes utilizar.
7. [Opcional] Activa la **Fuente de medios para instalaciones de búsqueda orgánica**, en la sección de **mapeo de referentes** de **Web**, para establecer automáticamente la fuente de medios del tráfico de búsqueda orgánica cuando aún no se haya resuelto en la sección de mapeo de parámetros de URL. [Saber más](#seo-referrer-mapping)
8. Selecciona cómo implementar el Smart Script en tu sitio web:
   * **Insertar el script en tu sitio web.**
   * **Utilizar Google Tag Manager.**
9. Haz clic en **Probar** para probar el script en la <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">página de prueba de Smart Script</Anchor>. Asegúrate de que se genere la URL saliente correcta.
10. Clic
    1. **Guardar** para guardar tus cambios.
    2. **Guardar y generar** para guardar y generar el script.
       1. Haz clic en **Descargar script**.
11. Dile a tu desarrollador web qué hacer con la URL saliente generada. Por ejemplo, colocarla bajo un botón CTA en tu sitio móvil o presentar un código QR en tu sitio de escritorio. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#embed-the-script-in-your-website">Instrucciones para el desarrollador</Anchor>
12. Si seleccionaste usar Google Tag Manager:
    1. En Google Tag Manager, crea una nueva etiqueta, nombra la etiqueta, haz clic en **Tag Configuration (Configuración de etiquetas)** y selecciona **Custom HTML (HTML personalizado)**.
    2. En el cuadro HTML, pega el código de Smart Script generado.
    3. Haz clic en **Triggering (Activación)**, crea un nuevo activador, nómbralo y elige una **Trigger Configuration (Configuración de activador)** (por ejemplo, todas las vistas de página). <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">Consulta la documentación de GTM para aprender más</Anchor>
    4. Haz clic en **Save**
    5. Envíe el script a su desarrollador web para que lo implemente y dígale qué hacer con la URL saliente generada. Por ejemplo, colocarla bajo un botón CTA en tu sitio móvil o presentar un código QR en tu sitio de escritorio. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#embed-the-script-in-your-website">Instrucciones para el desarrollador</Anchor>
13. Los scripts guardados se pueden ver en el [menú desplegable](/docs/set-up-smart-script-to-convert-web-visitors#how-to-edit-or-delete-a-script).

<div id="important" />

> 🚧 **¡Importante!**
>
> Cada vez que actualices el script, deberás implementarlo de nuevo.

</Accordion>

<div id="how-to-edit-or-delete-a-script" />

<Accordion title="Cómo editar o eliminar un script">

**Cómo editar o eliminar un script:**

1. Haga clic en la flecha desplegable <Image alt="Flecha_abajo.jpg" src="https://files.readme.io/a82023665721be681f985548857c4c329f626435780bb1bff7a3821b32b69078-42045468433041.jpg" width="28px" /> junto al nombre del Smart Script.  
   Aquí puedes ver todos tus scripts guardados.  

   <Image alt="Script_steps.jpg" src="https://files.readme.io/824c042dc23acaa14b360ce8cd792cfc2e85ee3c9c95e3fa694f96badfeb1fc2-42045468432657.jpg" width="1732px" />
2. Haz clic en el icono del lápiz junto al script que quieres editar.
   1. Sigue los pasos de [Cómo crear un Smart Script de OneLink](/docs/set-up-smart-script-to-convert-web-visitors#configuración-de-smart-script-de-onelink).
3. Haz clic en el icono de la papelera para eliminar el Smart Script.

<div id="important-1" />

> 🚧 **¡Importante!**
>
> Cada vez que actualices el script, deberás implementarlo de nuevo.

</Accordion>

<div id="how-to-duplicate-a-script" />

<Accordion title="Cómo duplicar un script">

**Cómo duplicar un script:**

1. Ve al Smart Script que deseas duplicar.
2. Haga clic en el botón duplicar <Image alt="SmartScript_duplicate.jpg" src="https://files.readme.io/ec05ea217331b588dc7033984287d46b61a37e41510546b67a0046ea281e0979-42045454920721.jpg" width="21px" /> en el banner superior
3. Sigue los pasos de [Cómo crear un Smart Script de OneLink](/docs/set-up-smart-script-to-convert-web-visitors#configuración-de-smart-script-de-onelink).

</Accordion>

<div id="argument-structure" />

<Accordion title="Estructura de los argumentos">

El Smart Script de OneLink utiliza argumentos para generar una URL saliente basada en los parámetros de la URL entrante y los argumentos definidos en el script. El argumento afParameters tiene una estructura compuesta por otros argumentos (parámetros) utilizados para la atribución y los enlaces profundos, cada uno de los cuales contiene una estructura (a la que los desarrolladores se refieren como objeto de configuración) que tiene claves, valores de invalidación y un valor predeterminado, como se describe en la tabla siguiente.

| Argumento | Descripción | Ejemplo |
| --- | --- | --- |
| Parámetros de URL entrantes (a los que los desarrolladores se refieren como claves) | <ul><li>Lista de cadenas</li><li>Lista de posibles parámetros en la URL entrante que busca el script, cuyo valor se coloca como valor en la URL saliente.</li><li>El script busca de izquierda a derecha y se detiene en la primera coincidencia.</li></ul> | <ul><li>Ejemplo: ['in\_channel', 'utm\_channel']</li><li>Para el parámetro de canal en el script, el script busca en el enlace entrante para in\_channel y utiliza el valor como valor para el canal.</li></ul> |
| Valor predeterminado | <ul><li>Cadena</li><li>Indica cuál quieres que sea el valor de tu "fallback".</li><li>Si no se encuentra un parámetro en tu lista de claves, se utiliza el valor defaultValue en la URL saliente.</li><li>Puedes forzar un valor predeterminado pasando una lista de claves vacía.</li></ul> | Ejemplo: ['web\_video']<br /><br />Para el parámetro de canal en el script, si no se encuentra el parámetro in\_channel, web\_video se utiliza como valor de canal. |
| Valores de anulación | <ul><li>Diccionario \{string:string\}</li><li>Para los valores que deseas cambiar en el enlace saliente, enumera los valores en la URL entrante, junto con lo que deseas que se reemplace.</li><li>El script sustituye los valores de los parámetros de la URL entrante por los valores que definas.</li></ul> | Ejemplo: \{'video': 'video\_new'\}<br /><br />Para el parámetro del canal en el script, siempre que el valor entrante sea video, el script lo cambia a video\_new en el enlace saliente. |

</Accordion>

<div id="arguments" />

<Accordion title="Argumentos (parámetros y valores)">

El Smart Script de OneLink utiliza argumentos para generar una URL saliente basada en los parámetros de la URL entrante y los argumentos definidos en el script.

<div id="arguments-parameters-and-values-to-implement-the-smart-script" />

#### Argumentos (parámetros y valores) para implementar el Smart Script

<table><thead><tr><th colspan="2">Argumento</th><th>Observaciones</th><th>Registra tus respuestas (para que las utilices tú o tu desarrollador)</th></tr></thead><tbody><tr><td colspan="2">oneLinkURL (obligatorio)</td><td><ul><li>Proporciona el dominio de la plantilla OneLink + el ID de la plantilla. <strong>Nota:</strong> ¡No es una URL de enlace personalizada de OneLink!</li><li>Ejemplo: <strong>yourbrand.onelink.me/A1b2</strong> </li><li>Ejemplo de dominio de marca: <strong>click.yourbrand.com/A1b2</strong> </li></ul></td><td> </td></tr><tr><td rowspan="9"><p>afParameters</p><p>(obligatorio)</p></td><td><p>Fuente demedios</p><p>(obligatorio)</p></td><td><ul><li>Objeto de configuración de la fuente de medios.</li><li>Ejemplo:<ul><li>Claves: ['incoming_mediasource’' 'utm_source']</li><li>Valor por defecto: ['any_source']</li><li>Sobrescribir valores: `{twitter: 'twitter_int', orig_src: 'new_src',  seo:'false'}</li></ul></li></ul></td><td><p>Claves:</p><p>Valor predeterminado:</p><p>Valores de anulación:</p></td></tr><tr><td>campaña</td><td><ul><li>Objeto de configuración de la campaña.</li><li>Ejemplo:<ul><li>Claves: ['incoming_campaign', 'utm_campaign']</li><li>Valor predeterminado: ['any_campaign_name']</li><li>Anular valores: {campaign_name: 'new_campaign_name'}</li></ul></li></ul></td><td><p>Claves:</p><p>Valor predeterminado:</p><p>Valores de anulación:</p></td></tr><tr><td>canal</td><td><ul><li>Objeto de configuración del canal.</li><li>Ejemplo:<ul><li>Claves: ['incoming_channel', 'utm_channel']</li><li>Valor predeterminado: ['any_video']</li><li>Anular valores: {video: 'new_video'}</li></ul></li></ul></td><td><p>Claves:</p><p>Valor predeterminado:</p><p>Valores de anulación:</p></td></tr><tr><td>anuncio</td><td><ul><li>Objeto de configuración del anuncio.</li><li>Ejemplo:<ul><li>Claves: ['incoming_ad', 'utm_ad']</li><li>Valor predeterminado: ['any_ad_name']</li><li>Anular valores: {ad_name: 'new_ad_name'}</li></ul></li></ul></td><td><p>Claves:</p><p>Valor predeterminado:</p><p>Valores de anulación:</p></td></tr><tr><td>adSet</td><td><ul><li>Objeto de configuración del conjunto de anuncios.</li><li>Ejemplo:<ul><li>Claves: ['incoming_adset', 'utm_adset']</li><li>Valor predeterminado: ['any_ad_name']</li><li>Anular valores: {adset_name: 'new_adset_name'}</li></ul></li></ul></td><td><p>Claves:</p><p>Valor predeterminado:</p><p>Valores de anulación:</p></td></tr><tr><td>deepLinkValue</td><td><ul><li>Objeto de configuración de <strong>deep_link_value</strong>.</li><li>Ejemplo:<ul><li>Claves: ['product_id', 'page_name']</li><li>Valor predeterminado: 'new_offers_page'</li><li>Anular valores: {twenty_percent_off: 'thirty_percent_off'}</li></ul></li></ul></td><td><p>Claves:</p><p>Valor predeterminado:</p><p>Valores de anulación:</p></td></tr><tr><td>afSub1-5</td><td>Objeto de configuración de <strong>af_sub[1-5]</strong>.</td><td><p>Claves:</p><p>Valor predeterminado:</p><p>Valores de anulación:</p></td></tr><tr><td>googleClickIdKey</td><td>Selecciona un parámetro en la URL saliente para que contenga el GCLID.`<br />`<span>[Práctica recomendada]: Seleccione <strong>af_sub[1-5]</strong>para que los datos se muestren en los informes de datos sin procesar de AppsFlyer.</span> </td><td> </td></tr><tr><td> <span>Otros parámetros de consulta (personalizados)</span>`<br />` </td><td><ul><li>Enumera cualquier otro parámetro que desees incluir en la URL saliente de OneLink para la atribución o los enlaces profundos, junto con sus objetos de configuración.</li><li>El nombre del parámetro personalizado es identificado por el desarrollador como paramKey en el objeto de configuración.<span></span> </li><li>Ejemplo:<ul><li>paramKey: 'deep_link_sub1'</li><li>Claves: ['page_id']</li><li>Valor predeterminado: 'page1'</li><li>Anular valores: {page12: 'new_page12'}`</li></ul></li></ul></td><td><p>Clave de parámetro:</p><p>Claves:</p><p>Valor predeterminado:</p><p>Valores de anulación:</p></td></tr></tbody></table>

</Accordion>

<div id="advanced-arguments" />

<Accordion title="Argumentos avanzados">

La siguiente tabla describe los argumentos que los marketers o desarrolladores con conocimientos técnicos pueden implementar en el Smart Script.

<div id="advanced-arguments-parameters-and-values-to-implement-in-the-smart-script" />

#### Argumentos avanzados (parámetros y valores) para implementar en el Smart Script

<table><thead><tr><th colspan="2">Argumento</th><th>Observaciones</th><th>Registra tus respuestas (para que las utilices tú o tu desarrollador)</th></tr></thead><tbody><tr><td colspan="2"> <br/> referrerSkipList</td><td><ul><li> <span>Lista de cadenas en el referente HTTP para un clic en particular (por ejemplo, Twitter o Facebook) que, si se encuentran, hacen que el Smart Script regrese</span><code>null</code><span>. Esto puede ser útil para SRN como X Ads y Meta Ads, para los cuales ya se informan los clics.</span> </li><li>La implementación de este argumento da como resultado que el script NO genere una URL de OneLink.</li></ul></td><td> </td></tr><tr><td colspan="2">urlSkipList</td><td><ul><li>Lista de cadenas en la URL para un clic determinado (por ejemplo, af_r) que, si se encuentran, hacen que el Smart Script devuelva <span>null</span>. Esto puede ser útil si utilizas un enlace de atribución de AppsFlyer con af_r para redirigir a los usuarios a tu sitio web móvil, y no quieres que se pierdan los datos del clic original.</li><li>La implementación de este argumento da como resultado que el script NO genere una URL de OneLink.</li></ul></td><td> </td></tr><tr><td colspan="2">SEO</td><td><ul><li>Cuando esta opción está habilitada y la fuente de medios no se resuelve desde la sección <strong>Mapeo de parámetros de URL</strong>, comprobamos si los usuarios llegaron desde un motor de búsqueda en función de la URL de referencia web y configuramos la fuente de medios en consecuencia. (Disponible a partir de la versión 2.10.3)</li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<div id="use-cases" />

## Casos de uso

Las siguientes secciones proporcionan casos de uso de Smart Script para algunos escenarios comunes de campañas/fuentes de medios.

<div id="utm-parameters" />

<Accordion title="Parámetros UTM">

**Para configurar el script para los parámetros UTM**:

1. Haz una lista de los parámetros UTM de la URL entrante (por ejemplo: **utm\_source** y **utm\_campaign**) y hazlos coincidir con los parámetros de la URL saliente (por ejemplo: **media\_source** y **campaign**).
2. Proporciona estos en la lista de argumentos    al desarrollador web.

Resultado: **Resultado**: Los valores de los parámetros entrantes (utm\_source/span> y **utm\_campaign**) se utilizan para rellenar los valores de los parámetros (**media\_source** y **campaign**) en el enlace saliente.

</Accordion>

<div id="google-ads-gclid" />

<Accordion title="Google Ads GCLID">

El proceso habitual para la atribución de instalaciones de campañas de Google Ads (que contienen un parámetro GCLID) requiere que los usuarios que hacen clic en tu anuncio sean redireccionados a la URL de la página de la tienda de aplicaciones.

Dado que en este caso estás redireccionando clientes potenciales desde Google Ads a una página web o landing page, el script toma el parámetro GCLID de la URL de la campaña de instalación de Google Ads y lo coloca en la URL de salida. A partir de la versión 2.9.0 de Smart Script, los parámetros GCLID, WBRAID y GBRAID, cuando están disponibles, se reenvían automáticamente "tal cual" en las URLs de salida generadas por Smart Script.

También puedes asignar los IDs de clic a otros parámetros de salida (**af\_sub[1-5]**) para que estén disponibles en los reportes de raw data de AppsFlyer.

**¡Nota!**

* Esto se aplica a las campañas de instalación. En el caso de las campañas de búsqueda que no son de ACI, es decir, las campañas de re-engagement, se puede atribuir a Google como fuente de medios, a pesar del resultado del Smart Script.
* Si se encuentra un GCLID, el script busca la palabra clave del parámetro entrante. Si se encuentra, coloca el valor de la palabra clave en la URL saliente como el valor de af\_keywords.

**Requisito previo**: En el panel de Google, <Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">habilite el etiquetado automático</Anchor>.   
Con el etiquetado automático habilitado,la URL contiene el parámetro*GCLID*.

**Para configurar el script para asignar el GCLID de Google Ads a otros parámetros**:

1. Indica cómo llamar al parámetro que lleva el <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">GCLID</Anchor>.  
   **¡Nota**! Para que se muestre en los reportes de raw data de AppsFlyer, el parámetro debe ser uno de **af\_sub[1-5]**.
2. Proporciona esto en la [lista de argumentos](/docs/set-up-smart-script-to-convert-web-visitors#arguments) al desarrollador web. El resultado será que en la URL saliente, el GCLID será el valor del parámetro **af\_sub[1-5]** .

**Para notificar a Google Ads sobre estas instalaciones:**

**Recomendado:** Configura la <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-based-campaigns">integración web de Google</Anchor>. Esta integración admite postbacks automáticos para instalaciones.

**Si no tienes la integración:**

1. Obtén los datos GCLID del parámetro af\_sub[1-5] a través de CSV o Push API en tiempo real para cada instalación.
2. Sube los datos de GCLID a Google, ya sea manualmente o a través de <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">Google Ads API</Anchor>.

<div id="note" />

> 📘 **Nota**
>
> Esta solución GCLID no es oficialmente compatible ni recomendada por Google. En caso de que Google deje de utilizar el parámetro GCLID, cambiaremos el script para admitir los cambios. Sigue este artículo, haciendo clic en el botón **Seguir** en la cabecera del artículo, para recibir notificaciones cuando haya una actualización del artículo o del script adjunto.

</Accordion>

<div id="facebook-click-id" />

<Accordion title="Facebook FBCLID">

Los meta anuncios llevan identificadores de clic, llamados Identificador único. A partir de la versión 2.8.1 de Smart Script, cuando esté disponible, FBCLID se reenviará automáticamente "tal cual" en las URL salientes generadas por Smart Script. También puede asignar ID de clic a otros parámetros salientes para que estén disponibles en los informes de datos sin procesar de AppsFlyer.

**Para configurar el script para asignar FBCLID a otros parámetros:**

1. Selecciona un parámetro en la URL saliente para que contenga el GCLID.  
    [Práctica recomendada]: Seleccione **af\_sub[1-5]** para que los datos se muestren en los informes de datos sin procesar de AppsFlyer.
2. Proporciona esto en la [lista de argumentos](/docs/set-up-smart-script-to-convert-web-visitors#arguments) al desarrollador web. El resultado será que en la URL saliente, el FBCLID será el valor del parámetro **af\_sub[1-5]** .

</Accordion>

<div id="tiktok-ttclid-x-twclid-and-snapsccid" />

<Accordion title="TikTok (ttclid), X (twclid) y Snap (ScCid)">

La atribución de instalaciones para las campañas de anuncios de TikTok, X (antes Twitter) y Snap se basa en parámetros de Click ID específicos de cada red, que se añaden a los clics en anuncios y se usan para asociar las instalaciones y los eventos posteriores a la instalación con el anuncio de origen.

Cuando el tráfico se redirige por primera vez a una página web o una landing page, el Click ID debe conservarse y reenviarse para garantizar una atribución correcta. En este caso, el Smart Script captura el parámetro entrante de Click ID y lo añade a la URL de salida que genera.

El Click ID se capturará en la instalación y se usará en futuros eventos asociados a la instalación.

A partir de la versión 2.10.0 de Smart Script, los siguientes parámetros de Click ID, cuando están disponibles, se reenvían automáticamente «tal cual» en las URLs de salida generadas por Smart Script:

* TikTok: ttclid
* X (antes Twitter): twclid
* Snap: ScCid

También puedes asignar estos ID de clic a otros parámetros de salida, como af\_sub1-af\_sub5, para que estén disponibles en los reportes de raw data de AppsFlyer.

Consulta los siguientes artículos relevantes sobre integración web:

* <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-create-web-based-campaigns">TikTok</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/snapchat-create-web-based-campaigns">Snap</Anchor>

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="SRN, medios propios y otros enlaces de fuentes de medios">

<Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#srns-integradas-con-appsflyer">SRN</Anchor> como Snapchat o Twitter, funcionan de manera diferente que Google Ads o una plataforma cruzada como Anuncios de Meta. Las campañas de estas SRN llevan a tus usuarios a la página web/de aterrizaje, y se te factura de acuerdo con los clics que les han conducido, no relacionados con ningún usuario móvil derivado.

Para estas SRN, la configuración del script es la misma que para los enlaces de medios propios u otras fuentes de medios que puedas utilizar.

**Para configurar el script**:

1. Crea una lista de los nombres de los parámetros de fuente de medios y campaña que están en los enlaces entrantes.
2. Proporciona estos en la lista de argumentos   [al desarrollador web.](/docs/set-up-smart-script-to-convert-web-visitors#arguments)  
   yoEl tipo de fuente SRN/media debe ser el valor de la fuente multimedia en la URL entrante, y el script lo encuentra y lo usa como el valor **media\_source** en la URL OneLink saliente detrás del botón de descarga en la página web/de destino. Si deseas cambiar la **media\_source** saliente, proporciona el valor de la fuente de medios entrante y el valor de la fuente de medios de anulación en la [lista de argumentos](/docs/set-up-smart-script-to-convert-web-visitors#arguments) que le das al desarrollador web.

**Resultado:** **Resultado**: Para estas SRN/fuentes de medios, los valores de los parámetros de fuente de medios y campaña en el enlace entrante se utilizan para rellenar los valores de los parámetros **media\_source** y **campaign** en el enlace saliente.

<div id="example" />

> 📄 **Ejemplo**
>
> **URL entrante**: https://hotel.me/incoming_mediasource=twitter&incoming_campaign=big_social
>
> **URL saliente**: https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="Enlaces de atribución de AppsFlyer">

Los enlaces de atribución de AppsFlyer pueden utilizarse cuando la fuente de medios es una red de publicidad de clic. Cuando configuras dicho enlace en AppsFlyer, tienes la opción de agregar un parámetro de **ruta URL de redireccionamiento (af\_r)** con la ruta de URL deseada a tu sitio web móvil para la atribución de campaña web a aplicación. Es posible que no desees que el Script cree una URL de OneLink saliente, ya que, en ese caso, podrían perderse algunos de los datos del clic original.

Acción Utilice el argumento **urlSkipList** para enumerar el parámetro **af\_r** .

Resultado: Resultado: cuando el Smart Script encuentra el parámetro **af\_r** en el enlace entrante, el Smart Script no produce una URL saliente y el desarrollador debe decidir qué enlace colocar como URL saliente e implementarlo.

<div id="example-1" />

> 📄 **Ejemplo**
>
> Haz clic en el botón *Comenzar*.
>
> **URL saliente**: No hay URL saliente.

</Accordion>

<div id="web-referrer-mapping" />

<Accordion title="Asignación del referente web">

La asignación del referente web te muestra desde qué página llegaron los usuarios a tu sitio web (por ejemplo, desde resultados de búsqueda orgánicos), lo que enriquece los datos de los que dispones para analizar las instalaciones y los re-engagements procedentes de tu flujo Web-to-app de Smart Script.

Puedes configurar el Smart Script para recopilar esta información de tu página de aterrizaje o del campo `Referer`Referer del encabezado HTTP del sitio web. Este campo contiene la URL base de la página desde la que los usuarios hicieron clic en un enlace que los envió a tu página web.

**Para configurar el script para recopilar el referente web**

1. Abre la página **Smart Script**.
2. En la sección del área de **asignación del referente web**, selecciona la clave de parámetro de URL saliente para el valor de referente web:
   * af\_channel: el parámetro está disponible en los paneles de control y en el raw data
   * af\_sub1-5: el parámetro está disponible en el raw data, bajo las columnas **af\_sub1-5** y **URL original**.
   * Parámetro personalizado: este se compone del nombre y valor del parámetro. El parámetro se muestra en el raw data, en la columna **URL original**.

Para aprender sobre la atribución de búsquedas orgánicas para re-engagements usando enlaces universales y enlaces de aplicaciones, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">aquí</Anchor>.

</Accordion>

<div id="seo-referrer-mapping" />

<Accordion title="Asignación del referente SEO">

Puedes activar **Fuente de medios para instalaciones de búsqueda orgánica** para configurar automáticamente la fuente de medios del tráfico de búsqueda orgánica cuando aún no se haya resuelto en la sección de **asignación de parámetros de URL**.

* Si el referente web del usuario coincide con un motor de búsqueda compatible (por ejemplo, google.com o bing.com), la Fuente de medios se configura con el canal correspondiente (por ejemplo, google\_organic\_seo).
* Si no hay coincidencia, se usa el **valor predeterminado** configurado en la asignación de parámetros de URL.

</Accordion>

<div id="desktop" />

<Accordion title="Escritorio">

La mayoría de los casos de uso en este artículo Son de usuarios que provienen de dispositivos móviles. Por lo tanto, cuando se les dirige desde el sitio web móvil a una tienda de aplicaciones, pueden descargar inmediatamente su aplicación.

Sin embargo, los usuarios de escritorio no deben ser enviados inmediatamente a una tienda de aplicaciones, ya que su dispositivo (una computadora de sobremesa o portátil) no es compatible con las descargas de aplicaciones móviles.

**Para configurar el script para los usuarios de escritorio**:

* En tu <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor>, establece una URL de destino para **Cuando se hace clic en el enlace en el escritorio**. La URL debe redirigir a una página web/de aterrizaje dedicada. La página de aterrizaje puede contener un formulario web en el que se rellenan los datos para recibir un SMS o un correo electrónico con un enlace para descargar la aplicación. Eres tú quien debes crear el formulario web y proporcionar la URL del mismo en el script.

**Resultado:** El script detecta el dispositivo o la plataforma en la que se encuentra el usuario. Si es de escritorio, el script genera una URL saliente de OneLink que redirige al usuario a tu página web/de aterrizaje dedicada.

Consulta también <Anchor target="_blank" href="/marketers/es/docs/qr-to-app-conversion">Conversión de escritorio a aplicación</Anchor>.

</Accordion>

<div id="qr-codes" />

<Accordion title="Códigos QR">

El Smart Script muestra un código QR en tu página web, en lugar de un botón con un enlace detrás. 

**Para mostrar un código QR:**

1. Asegúrate de usar el Smart Script 2.6+ cuando configures tu Smart Script.
2. Dile a tu desarrollador que siga sus instrucciones para crear un código QR con el resultado del Smart Script.
3. [Práctica recomendada] Dile al desarrollador que:
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#create-a-qr-code-with-the-smart-script-result">Personalice el código QR</Anchor> agregando el logo de tu aplicación al centro de códigos QR y personalizando el color.
   * Muestre el código QR cuando los usuarios estén en el escritorio y muestre el botón con el enlace cuando los usuarios estén en el móvil.

**Resultado:** El script muestra un código QR en lugar de un botón con una URL detrás.

<div id="example-2" />

> 📄 **Ejemplo**
>
> **URL entrante**:
>
> https://hotel.me/qr_code.html?incmp=gogo&inmedia=email
>
>
>  referrerSkipList
>
> https://hotel.onelink.me/LtRd/?af_js_web=true&af_ss_ver=2_1_0&pid=email&c=gogo
>
> **Código QR saliente**:
>
> <Image alt="" src="https://files.readme.io/2f06149c901d8a97c2a544b8196e9afecbe3b3748ed8419a39c2dc5e3afa61ba-42045454923153.png" width="48.07%" />

</Accordion>

<div id="impressions" />

<Accordion title="Impresiones">

El script inteligente OneLink se puede utilizar para contar impresiones en su sitio web. Para ello, el desarrollador debe: Llamar a la función de impresión. Luego, las instalaciones se atribuyen a las impresiones mediante <Anchor target="_blank" href="/marketers/es/docs/measure-view-through-engagements">la atribución de visualización</Anchor>.

**Nota**:

* El recuento de impresiones se suma a la URL normal producida por el Smart Script que cuenta los clics. El Smart Script puede utilizarse para contar los clics, las impresiones o ambos.
* La atribución por impresiones a través de Smart Script solo funciona en dispositivos móviles; no en los de escritorio.

**Para atribuir nuevas instalaciones a estas impresiones (atribución por impresiones):**

1. Asegúrate de usar Smart Script 2.3+ al configurar tu Smart Script.
2. Dile a tu desarrollador que llame la función de impresión en el Smart Script.
3. Asegúrate de que la <Anchor target="_blank" href="/marketers/es/docs/measure-view-through-engagements">atribución por impresiones esté activada</Anchor>.

<div id="important-2" />

> 🚧 **¡Importante!**
>
> A partir del 1 de febrero de 2023 (lanzamiento estable de Chrome 110), Google ha realizado algunos cambios para reducir los datos de usuario-agente. Para obtener correctamente las las atribuciones por impresiones usando el Smart Script de OneLink, debes usar el OneLink Smart Script versión 2.3 y superior.

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="faq" />

<Accordion title="Preguntas frecuentes">

<div id="will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website" />

#### ¿La URL entrante para la generación de enlaces de OneLink funcionará si el usuario navega a una página diferente en el sitio web?

Sí. Los parámetros de URL entrantes se almacenan durante la sesión de navegación y se aplican a los parámetros salientes del enlace de OneLink generado por Smart Script. Para obtener más información sobre la implementación, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#preserve-incoming-url-parameters-across-pages">consulta nuestro centro de desarrollo</Anchor>.

<div id="why-do-i-get-an-error-when-implementing-smart-script-via-google-tag-manager" />

#### **¿Por qué obtengo un error al implementar Smart Script a través de Google Tag Manager?**

A veces, cuando generas el Smart Script en AppsFlyer e intentas insertarlo en Google Tag Manager (GTM), aparece un error de "JavaScript demasiado largo". Si esto ocurre, elimina la etiqueta GTM y crea una nueva.

<div id="can-i-add-parameters-that-are-not-listed" />

#### **¿Puedo agregar parámetros que no aparecen en la lista?**

Sí. En tu página OneLink Smart Script, haz clic en + **Nuevo parámetro** para asignar parámetros adicionales.

* Los nuevos parámetros pueden ser parámetros personalizados o parámetros reservados de AppsFlyer que no están listados en el menú desplegable.
  * Consulta todos los [argumentos adicionales](/docs/set-up-smart-script-to-convert-web-visitors#arguments) (configuraciones de parámetros) que puedes utilizar.
* Utiliza la opción Personalizado del menú desplegable y tu parámetro en el campo **Parámetros de URL saliente**.

Por ejemplo, para agregar is\_retargeting como parámetro, se seleccionaría el parámetro Personalizado en el campo **asignar para** , y luego nuestro parámetro is\_retargeting en el campo **Parámetros de URL saliente**.

![Smart_Script_Custom.jpg](https://files.readme.io/5a09d18b01ece93bbb47667b676039c98742ebc3b88c5235ad92c7e44d5316b9-small-42045454926609.jpg)

<div id="adset-and-other-parameters-are-not-showing-in-the-dropdown" />

#### **El conjunto de anuncios y otros parámetros no se muestran en el menú desplegable**

Te recomendamos desactivar cualquier bloqueador de anuncios que tengas en tu navegador al crear o agregar nuevos parámetros. A veces los bloqueadores de anuncios eliminarán una opción si tiene la palabra 'Anuncio' en ella.

<div id="what-browsers-does-smart-script-work-on" />

#### **¿En qué navegadores funciona Smart Script?**

Smart Script usa Javascript y debería funcionar en todos los navegadores.

</Accordion>

<div id="specs-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| **Especificación** | **Nota** |
| --- | --- |
| Esquema URI | Incluso si se establece un esquema URI en la plantilla de OneLink para abrir la aplicación para los usuarios existentes, para los enlaces creados con Smart Script, el desarrollador debe agregar el parámetro af\_dp con el esquema URI a las URL como un <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#set-additional-custom-parameters">parámetro personalizado</Anchor>. |
| **en la dirección URL entrante**| Smart Script encuentra problemas al manejar direcciones URL entrantes que incluyen un símbolo hash ('#') que precede a los parámetros de consulta (indicado por un '?' signo). En tales casos, Smart Script revierte a los valores predeterminados. |

</Accordion>

<div data-zendesk-anchors="setup=configuraci%C3%B3n h_01H95PGMNWR12KQ2P0KT8BBGEC=configuraci%C3%B3n set-up-onelink-smart-script=configuraci%C3%B3n-de-smart-script-de-onelink h_01H95PGMNW6N63XQ1EQSQSHHB2=configuraci%C3%B3n-de-smart-script-de-onelink scope-of-work=alcance-del-trabajo h_01H95PGMNWPBRHSZBPMKNJ2PS6=alcance-del-trabajo h_01H95PGMNWWYRRNVNTK31XYRN3=how-to-create-a-onelink-smart-script h_01H95PGMNW5HA4FWBFW7AR89AV=importante h_01H95PGMNXZAES8DPJ1B4E1QV8=how-to-edit-or-delete-a-script h_01H95PGMNX5ZT7DPV2WBG0CTKB=importante-1 h_01H95PGMNXNT9C07B0YTS1KK82=how-to-duplicate-a-script h_01H95PGMNXWJ9V5JW9JEAHF81S=argument-structure h_01H95PGMNXR2HTV1EF07QVQB6W=arguments arguments-parameters-and-values-to-implement-the-smart-script::d4f6bf94=argumentos-par%C3%A1metros-y-valores-para-implementar-el-smart-script h_01H95PGMNXPMCM73XT3GTDVAXJ=argumentos-par%C3%A1metros-y-valores-para-implementar-el-smart-script h_01H95PGMNX4B8W84DHJR9T4CR2=advanced-arguments arguments-parameters-and-values-to-implement-the-smart-script=argumentos-avanzados-par%C3%A1metros-y-valores-para-implementar-en-el-smart-script h_01H95PGMNXCAHTTJATG75Y3TRN=argumentos-avanzados-par%C3%A1metros-y-valores-para-implementar-en-el-smart-script use-cases=casos-de-uso h_01H95PGMNXBPFFNE44YGGECBPR=casos-de-uso h_01H95PGMNX3W95JW47YQGSEYQ6=utm-parameters h_01H95PGMNXGZZEMZ6PMAB4XFQQ=google-ads-gclid h_01H95PGMNXZT08G8RTMMG6BQCJ=nota h_01H95PGMNXHJXGB2QXH0YTB6Z0=facebook-click-id h_01KD5EZQFF23MYGXGJF1CF6VPT=tiktok-ttclid-x-twclid-and-snapsccid h_01H95PGMNXBKXFG9M169WG89TK=srns-owned-media-and-other-media-source-links h_01H95PGMNXZPB6CT3ZKJ2KMQ1J=ejemplo h_01H95PGMNX8Q0BASSESVD06MXE=appsflyer-attribution-links h_01H95PGMNX741EJGPF9G2DS67N=ejemplo-1 h_01HAS199KS0C0V3G41WGXTK4PF=web-referrer-mapping h_01M1BK4M22YAQ6YX4RZXRKZF7C=seo-referrer-mapping h_01H95PGMNY0P2354ZFVC92TMVC=desktop h_01H95PGMNYDSFP6GJDWC9AE0J2=qr-codes h_01H95PGMNYGJ9BJ86YCP7FYH6G=ejemplo-2 h_01H95PGMNYZBGZWNFESDTE9GY9=impressions h_01H95PGMNYX1FDT1KK9PQAMX5N=importante-2 additional-information=informaci%C3%B3n-adicional h_01H95PGMNYB6A8VKEAH8Z8TDPE=informaci%C3%B3n-adicional h_01H95PGMNYKQ8TNM3KKK9EXANV=faq will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website=la-url-entrante-para-la-generaci%C3%B3n-de-enlaces-de-onelink-funcionar%C3%A1-si-el-usuario-navega-a-una-p%C3%A1gina-diferente-en-el-sitio-web h_01H95PGMNYM5X2K9J0WZW6PZ8A=la-url-entrante-para-la-generaci%C3%B3n-de-enlaces-de-onelink-funcionar%C3%A1-si-el-usuario-navega-a-una-p%C3%A1gina-diferente-en-el-sitio-web why-do-i-get-an-error-when-implemeting-smart-script-via-google-tag-manager=por-qu%C3%A9-obtengo-un-error-al-implementar-smart-script-a-trav%C3%A9s-de-google-tag-manager h_01H95PGMNYSQX6BJCN56D4XZZF=por-qu%C3%A9-obtengo-un-error-al-implementar-smart-script-a-trav%C3%A9s-de-google-tag-manager can-i-add-parameters-that-are-not-listed=puedo-agregar-par%C3%A1metros-que-no-aparecen-en-la-lista h_01H95PGMNY2AVJ0CYDAM62Q9PA=puedo-agregar-par%C3%A1metros-que-no-aparecen-en-la-lista adset-and-other-parameters-are-not-showing-in-the-dropdown=el-conjunto-de-anuncios-y-otros-par%C3%A1metros-no-se-muestran-en-el-men%C3%BA-desplegable h_01H95PGMNY97BY6BCPPMYHBF0Q=el-conjunto-de-anuncios-y-otros-par%C3%A1metros-no-se-muestran-en-el-men%C3%BA-desplegable what-browsers-does-smart-script-work-on=en-qu%C3%A9-navegadores-funciona-smart-script h_01H95PGMNY5AV0DTX51X0DJMTK=en-qu%C3%A9-navegadores-funciona-smart-script h_01H95PGMNY4W9X51KV6GM4BSPG=specs-and-limitations" />

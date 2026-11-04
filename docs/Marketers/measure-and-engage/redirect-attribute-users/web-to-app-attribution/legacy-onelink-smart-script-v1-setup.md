---
title: '[Legacy] Configuración de OneLink Smart Script V1'
deprecated: true
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
  created_at: '2022-01-02T17:00:19Z'
  edited_at: '2026-08-12T12:25:18Z'
  id: 4415354290321
  locale: es
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/es/articles/4415354290321
---
> **A simple vista:** **De un vistazo:** Configura el Smart Script de OneLink para convertir y atribuir a los visitantes de tu sitio web móvil, provenientes de cualquier fuente, en usuarios de la aplicación móvil. **Nota**: Aunque no es obligatorio, considera la posibilidad de migrar a <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor>.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/89302407b5a7fb98299ce5255393651cc147ed963b0b17a6f74effbc0f7e16e0-4723094404753.png)

<div id="setup" />

## instalación

Hay dos versiones de Smart Script de OneLink:

<Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2 (recomendado)**</Anchor>: Si estás configurando OneLink Smart Script por primera vez, esta es la versión preferida. La parte de trabajo del desarrollador es más fácil y también se puede configurar con Google Tag Manager. **Nota**: Aunque no es obligatorio, considera la posibilidad de migrar a la V2. 

**OneLink Smart Script V1 (heredado)**: Si ya tienes configurado Onelink Smart Script, utiliza la documentación de esta versión para mantener y editar este script. 

<div id="responsibilities" />

<Accordion title="Responsabilidades">

| **¿Quién participa?**<ul><li>**Anunciante**:<ul><li>Decide qué debe contener la URL saliente. Esto incluye qué datos de atribución se añadirán al enlace y los datos necesarios para el Deep Linking. Ya sea manipulando la URL entrante o forzando ciertos valores.</li><li>Se asegura de que todas las campañas que llevan al sitio web móvil tengan direcciones URL entrantes con parámetros para los que funciona el script.</li></ul></li><li>**Desarrollador web**:<ul><li>Configura los datos para inicializar el script.</li><li>Introduce los setters necesarios para generar las URL salientes de OneLink en función de los parámetros de URL entrantes proporcionados por el responsable de marketing. Esto incluye parámetros obligatorios y opcionales.</li><li>Inserta el script en el sitio web o en páginas específicas.</li></ul></li></ul> |
| --- |
| **Prerrequisitos**<ul><li>Una cuenta de AppsFlyer con una aplicación como mínimo.</li><li>Una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor> que sirve como valor del [parámetro OneLinkURL](/docs/legacy-onelink-smart-script-v1-setup#parameters).</li></ul> |

**Para implementar el script en la página web**:

1. Decide qué parámetros/valores debe contener la URL saliente de OneLink generada automáticamente. Consulta la [lista de parámetros](/docs/legacy-onelink-smart-script-v1-setup#parameters) que puedes usar.
   * Asegúrate de que todas las campañas con URL entrantes tengan parámetros para los que funcione el script (y que pueda colocarlos como parámetros **pid** y **c**).
2. Proporciona la [lista de parámetros](/docs/legacy-onelink-smart-script-v1-setup#parameters) al desarrollador web.
3. Dile al desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script">instrucciones para desarrolladores</Anchor> e implemente el script para que se genere el enlace saliente correcto.

</Accordion>

<div id="parameters" />

<Accordion title="Parámetros">

<div id="parametersvalues-provided-to-the-developer-to-implement-the-smart-script" />

#### Parámetros/valores proporcionados al desarrollador para implementar el Smart Script

| Parámetro/valor | Nota | Registra tus respuestas (para que el desarrollador las utilice) |
| --- | --- | --- |
| oneLinkURL (obligatorio) | <ul><li>Proporciona el dominio de la plantilla OneLink + el ID de la plantilla. **Nota:** ¡No es una URL de enlace personalizada de OneLink!</li><li>Ejemplo: **yourbrand.onelink.me/A1b2**</li><li>Ejemplo de dominio de marca: **click.yourbrand.com/A1b2**</li></ul> |  |
| pidKeysList (fuentes de medios) | <ul><li>Enumera todos los parámetros de fuente de medios de la URL entrante que se colocarán como parámetro de fuente de medios (pid) en la URL saliente.</li><li>Ejemplo: ['af\_pid', 'utm\_source']</li></ul> |  |
| pidOverrideList | <ul><li>Para las fuentes de medios que quieras cambiar en el enlace saliente, enumera los valores de fuente de medios en la URL entrante junto con aquello por lo que quieras reemplazarlos.</li><li>Ejemplo: `{`<br />`'twitter': 'twitter_int',`<br />`'snapchat': 'snapchat_int',`<br />`'some_social_net': 'some_social_net_int'`<br />`}`</li></ul> |  |
| pidStaticValue | <ul><li>Indica cuál quieres que sea tu fuente de medios de "fallback".</li><li>Si no se encuentra un parámetro de fuente de medios en tu pidKeysList, se usa pidStaticValue como fuente de medios (pid) en la URL saliente.</li><li>Ejemplo: 'website' o 'landing\_page'</li></ul> |  |
| campaignKeysList (campañas) | <ul><li>Enumera todos los parámetros de campaña de la URL entrante que se colocarán como parámetro de campaña (c) en la URL saliente.</li><li>Ejemplo: ['af\_campaign', 'utm\_campaign']</li></ul> |  |
| campaignStaticValue | <ul><li>Indica cuál quieres que sea tu campaña de "fallback".</li><li>Si no se encuentra un parámetro de campaña en tu campaignKeysList, se usa campaignStaticValue como la campaña (c) en la URL saliente.</li><li>Ejemplo: 'website' o 'landing\_page'</li></ul> |  |
| gclIdParam | <ul><li>Indica cómo llamar al parámetro que contiene el <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">GCLID</Anchor>.</li></ul>[Práctica recomendada]: Seleccione **af\_sub[1-5]** para que los datos se muestren en los informes de datos sin procesar de AppsFlyer. |  |
| skipList | <ul><li>Enumera las cadenas del referente HTTP que deshabilitan Smart Script para un clic específico (por ejemplo, Twitter o Facebook). Si se encuentran esas cadenas, el Smart Script no se ejecuta. Esto puede ser útil para SRN como X Ads y Meta Ads, para los cuales ya se informan los clics.</li><li>Si quieres que Smart Script se ejecute siempre, incluso para las SRN, dile al desarrollador que pase una lista de omisión vacía.</li></ul> |  |
| Otros parámetros de consulta | <ul><li>Enumera cualquier otro parámetro que quieras incluir en la URL saliente de OneLink para Atribución o Deep Linking.</li><li>Añade un **deep\_link\_value** para Deep Linking.<ul><li>Además de añadir el parámetro, tú y tu desarrollador tenéis que implementar la lógica de Deep Linking. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">Saber más</Anchor></li></ul></li><li>Puedes usar parámetros de la URL entrante o forzar un valor estático.</li></ul> |  |

</Accordion>

<div id="use-cases" />

## CASOS DE USO

Las siguientes secciones proporcionan casos de uso de Smart Script para algunos escenarios comunes de campañas/fuentes de medios.

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="Anuncios de Meta — atribución multiplataforma">

Los anuncios de Meta son una SRN que no usa enlaces de atribución externos.

Cuando se abre la app por primera vez, AppsFlyer consulta a los anuncios de Meta si el usuario ha interactuado previamente (en los últimos <Anchor target="_blank" href="/marketers/es/docs/meta-ads-discrepancies#atribución-por-clics-y-por-impresiones">7 días</Anchor>) con un anuncio de la app. Si el usuario ha interactuado con un anuncio de Facebook del anunciante, los anuncios de Meta se autoatribuyen. Los Anuncios de Meta también se atribuyen a la multiplataforma, lo que significa que el usuario puede interactuar con cualquier tipo de campaña, móvil o no, en cualquier plataforma, para que los Anuncios de Meta lo atribuyan a sí mismo.

**Acción**: Indica a tu desarrollador que use el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script#skip-clicks-from-twitter-or-facebook">método skipList</Anchor> para desactivar Smart Script para los anuncios de Meta (o cualquier otra cadena que quieras). Si los anuncios de Meta o cualquiera de las cadenas de la lista de omisión aparecen en el referente HTTP del clic, Smart Script devuelve `null`.

**Nota**: La atribución multiplataforma de los anuncios de Meta puede verse afectada cuando los usuarios optan por no compartir su ID de dispositivo, como se espera de los usuarios de iOS 14 durante 2021.

</Accordion>

<div id="google-ads-gclid-and-utm-parameters" />

<Accordion title="Google Ads — GCLID y parámetros UTM">

El proceso habitual para la atribución de instalaciones de campañas de Google Ads (que contienen un parámetro GCLID) requiere que los usuarios que hacen clic en tu anuncio sean redirigidos a la URL de la página de la tienda de la aplicación.

Como en este caso estás redirigiendo leads desde Google Ads a una página web/de destino, el script toma el parámetro GCLID de la URL de la campaña de instalación de Google Ads y lo coloca en la URL saliente en el parámetro de salida que elijas **af\_sub[1-5]. ¡Nota!** Esto se aplica a las campañas de instalación. En el caso de las campañas de búsqueda que no son de ACI, es decir, las campañas de re-engagement, se puede atribuir a Google como fuente de medios, a pesar del resultado del Smart Script.

**Requisito previo**: En el Dashboard de Google, <Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">habilita el etiquetado automático</Anchor>.   
Con el etiquetado automático habilitado, la URL contiene el *GCLID* parámetro.

**Para configurar el script para Google Ads**:

1. Haz una lista de los nombres de los parámetros de fuente de medios y campaña que están en los enlaces entrantes.  
   Por ejemplo: **utm\_source** y **utm\_campaign**.
2. Indica cómo llamar al parámetro que lleva el <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">GCLID</Anchor>.  
   **¡Nota**! Para que se muestre en los reportes de raw data de AppsFlyer, el parámetro debe ser uno de **af\_sub[1-5]**.
3. Proporciona estos en la [lista de parámetros](/docs/legacy-onelink-smart-script-v1-setup#parameters) al desarrollador web.

**Resultado**:

* Los valores de los parámetros de fuente de medios y campaña (**utm\_source** y **utm\_campaign**) del enlace entrante se utilizan para rellenar los valores de los parámetros **pid** y **c** en el enlace saliente.
* En la URL saliente, el GCLID es el valor del parámetro **af\_sub[1-5]** .

**Para notificar a Google Ads sobre estas instalaciones:**

1. Obtén los datos GCLID del parámetro af\_sub[1-5] a través de CSV o Push API en tiempo real para cada instalación.
2. Sube los datos de GCLID a Google, ya sea <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">manualmente</Anchor> o mediante una <Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">API de Adwords</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Esta solución GCLID no es oficialmente compatible ni recomendada por Google. En caso de que Google deje de utilizar el parámetro GCLID, cambiaremos el script para admitir los cambios. Sigue este artículo, haciendo clic en el botón **Seguir** en la cabecera del artículo, para recibir notificaciones cuando haya una actualización del artículo o del script adjunto.

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="SRN, medios propios y otros enlaces de fuentes de medios">

<Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#srns-integradas-con-appsflyer">SRNs</Anchor> como Snapchat o X Ads funcionan de forma diferente a Google Ads o a una multiplataforma como los anuncios de Meta. Las campañas de estas SRN llevan a tus usuarios a la página web/de aterrizaje, y se te factura de acuerdo con los clics que les han conducido, no relacionados con ningún usuario móvil derivado.

Para estas SRN, la configuración del script es la misma que para los enlaces de medios propios u otras fuentes de medios que puedas utilizar.

**Para configurar el script**:

1. Crea una lista de los nombres de los parámetros de fuente de medios y campaña que están en los enlaces entrantes.
2. Proporciona estos en la [lista de parámetros](/docs/legacy-onelink-smart-script-v1-setup#parameters) al desarrollador web.  
   Tel tipo de SRN/fuente de medios debe ser el valor de la fuente de medios en la URL entrante, y el script lo encuentra y lo usa como el valor de **pid** en la URL saliente de OneLink detrás del botón de descarga en la página web/de destino. Si quieres cambiar el **pid** saliente, proporciona el valor de fuente de medios entrante y el valor de reemplazo de **pid** en la lista de sustitución de pid.

**Resultado**: Para estas SRN/fuentes de medios, los valores de los parámetros de fuente de medios y campaña del enlace entrante se utilizan para rellenar los valores de los parámetros **pid** y **c** en el enlace saliente.

<div id="example" />

> 📄 **Ejemplo**
>
> **URL entrante**: https://hotel.me/af_pid=twitter&af_c=big_social
>
> **URL saliente**: https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="Enlaces de atribución de AppsFlyer">

Los enlaces de atribución de AppsFlyer pueden utilizarse cuando la fuente de medios es una red de publicidad de clic. Cuando configuras un enlace de este tipo en AppsFlyer, tienes la opción de añadir un parámetro de ***ruta URL de redirección (af\_r)*** con la ruta URL deseada a tu sitio web móvil para la atribución de campaña web a aplicación. 

**Resultado**: Si los parámetros **af\_r** y **af\_redirect=true** están en el enlace entrante, el script de la página de destino no realiza cambios. Deja los enlaces directos de la página web/de destino a las tiendas de aplicaciones tal como están. 

<div id="example-1" />

> 📄 **Ejemplo**
>
> **URL entrante**: https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_redirect=true&af_r=hotel.me
>
> **URL saliente**: Igual

</Accordion>

<div id="desktop" />

<Accordion title="Ordenador">

La mayoría de los casos de uso en este artículo Son de usuarios que provienen de dispositivos móviles. Por lo tanto, cuando se les dirige desde el sitio web móvil a una tienda de aplicaciones, pueden descargar inmediatamente su aplicación.

Sin embargo, los usuarios de escritorio no deben ser enviados inmediatamente a una tienda de aplicaciones, ya que su dispositivo (una computadora de sobremesa o portátil) no es compatible con las descargas de aplicaciones móviles.

**Para configurar el script para los usuarios de escritorio**:

* En tu <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor>, establece una URL de destino para **Cuando se hace clic en el enlace en el escritorio**. La URL debe redirigir a una página web/de aterrizaje dedicada. La página de aterrizaje puede contener un formulario web en el que se rellenan los datos para recibir un SMS o un correo electrónico con un enlace para descargar la aplicación. Eres tú quien debes crear el formulario web y proporcionar la URL del mismo en el script.

**Resultado:** El script detecta el dispositivo o la plataforma en la que se encuentra el usuario. Si es de escritorio, el script genera una URL saliente de OneLink que redirige al usuario a tu página web/de aterrizaje dedicada.

Consulta también <Anchor target="_blank" href="/marketers/es/docs/qr-to-app-conversion">Conversión de escritorio a app</Anchor>.

</Accordion>

<div id="limitations" />

<Accordion title="Limitaciones">

| Limitación | Nota |
| --- | --- |
| Administrador de etiquetas | Smart Script no se puede implementar mediante un administrador de etiquetas. Consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor> como solución alternativa de atribución Web-to-app. |

</Accordion>

<div data-zendesk-anchors="setup=instalaci%C3%B3n h_01HDNWHSY8HM30HV1PAF5C3M4E=instalaci%C3%B3n h_01HDNWHSY8J65EB1RZCFP1606H=responsibilities h_01HDNWHSY8CH29FQ2V5DCG2XSP=parameters parametersvalues-provided-to-the-developer-to-implement-the-smart-script=par%C3%A1metrosvalores-proporcionados-al-desarrollador-para-implementar-el-smart-script h_01HDNWHSY8WSPX47VB43MC516Q=par%C3%A1metrosvalores-proporcionados-al-desarrollador-para-implementar-el-smart-script use-cases=casos-de-uso h_01HDNWHSY8N77ZH4CK49ZQ2KZB=casos-de-uso facebook-ads%E2%80%94crossplatform-attribution=facebook-ads-crossplatform-attribution h_01HDNWHSY85QFABA6FAX1XTEPE=facebook-ads-crossplatform-attribution google-ads%E2%80%94gclid-and-utm-parameters=google-ads-gclid-and-utm-parameters h_01HDNWHSY878JTPZSN719KF1Y5=google-ads-gclid-and-utm-parameters h_01HDNWHSY8BJH39TAN46W7HE4G=nota h_01HDNWHSY8NER2M8X4DGHCWYPJ=srns-owned-media-and-other-media-source-links h_01HDNWHSY828Q587S28GYB85VR=ejemplo h_01HDNWHSY8K1AFSEA1RY04KXJ9=appsflyer-attribution-links h_01HDNWHSY8DDTA6VATN0XXBEY5=ejemplo-1 h_01HDNWHSY821DADGKATKH12PSJ=desktop h_01HDNWHSY80QA9CC4S2BPBTJYG=limitations" />

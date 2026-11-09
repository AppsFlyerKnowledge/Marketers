---
title: Configuración de campañas de anuncios de Sina Weibo
metadata:
  keywords:
    - Advertisers
    - Sina Weibo Ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-08-15T08:37:03Z'
  edited_at: '2026-09-17T00:26:19Z'
  id: 115004134086
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/115004134086
---
> **De un vistazo:** Sina Weibo Ads, un partner integrado de la ad network de AppsFlyer, es una de las plataformas de redes sociales más populares en China.

<div id="setting-up-sina-weibo-ads" />

## Configuración de Sina Weibo Ads

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partner</Anchor>.

La ventana de configuración de Sina Weibo Ads incluye 3 pestañas activas: integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

Esta sección se usa para conectar al socio con AppsFlyer. Aquí también aparecen los mensajes de interés para el anunciante con respecto al socio específico.

<div id="activate-partners" />

### Activar los partners

En la **primera visita** aquí, tendrás que activar el botón ***Activar Partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Postbacks predeterminados

Si la atribución/integración está habilitada para el partner, AppsFlyer puede enviarle postbacks automáticos tras instalaciones de usuarios, inicios, re-engagements e instalaciones rechazadas. Utiliza esta sección para definir la **fuente de los usuarios** para los que se envían los postbacks.

<Image align="center" alt="Sina_Weibo_msc_new_2.png" src="https://files.readme.io/0f71568fd13ce9357f07282636e0b86fdbb9e9b1f6ef9db8ba673bb2066881aa-360002277585.png" />

La opción "**Solo eventos atribuidos a este partner**", solo para usuarios atribuidos a este partner, está seleccionada de forma predeterminada.

Haga clic en **Guardar**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que deseas enviar a Sina Weibo Ads para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Sina Weibo Ads. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas en funcionamiento con Sina Weibo Ads.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Sina Weibo Ads.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos, dentro de campañas específicas de Sina Weibo Ads.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** y **ID de subsitio**: configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="" src="https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png" />

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configuraciones de retargeting

Puedes agregar cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en una casilla de parámetro nueva. Aquí puedes encontrar todos los parámetros de URL disponibles de AppsFlyer: <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**Estructura y parámetros de los enlaces de atribución de AppsFlyer**</Anchor>

Cuando está habilitada, AppsFlyer reconoce un enlace como un enlace de atribución de <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">retargeting</Anchor>, en lugar de un enlace de adquisición de usuarios, al añadir `&is_retargeting=true` al enlace de registro de clics. Tenga en cuenta que actualmente solo se admite el redireccionamiento para la atribución por clics y no por impresiones.

**Parámetro del enlace de atribución**: `is_retargeting`

Cuando el retargeting está habilitado, se muestra la siguiente configuración.

<Image align="center" alt="retargeting_settings.png" src="https://files.readme.io/b90bbd6e3bea9dd862808343896b005071b7d9e564d31039c188c3ebf8e81077-360002254489.png" />

***Enlace estándar*** **vs.** ***OneLink***

Selecciona la opción ***enlace de atribución estándar*** si:

* No necesitas un enlace profundo con la URL o
* Tienes previsto usar solo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para Deep Linking

Selecciona ***Use OneLink*** para:

* Utilizar un solo enlace para aplicaciones de Android y iOS, o
* Establecer enlaces profundos empleando enlaces universales o de aplicaciones.

Ten en cuenta que, si seleccionas OneLink, esto cambia el enlace de registro de clics de una URL específica de aplicación a una <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">URL de OneLink</Anchor>.

***URL de deep link***

Utiliza este campo si el enlace está pensado para dirigir mediante Deep Linking a los usuarios a cualquier actividad específica dentro de tu aplicación.  
**Parámetro del enlace de atribución**: `af_dp`  
Puedes encontrar más información sobre la <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">solución de Deep Linking de AppsFlyer en esta guía.</Anchor>

***Ventana de recaptación***

Defina el plazo posterior al re-engagement, durante el cual los eventos in-app del usuario se atribuyen a la fuente de medios de redireccionamiento. Puede establecer el valor en días (1-90), horas (hasta 23) o incluso durante toda la vida.

**Parámetro del enlace de atribución**: `af_reengagement_window`

Consulta aquí [cómo configurar el retargeting](/docs/sina-weibo-ads-campaign-configuration#crear-campañas-de-retargeting-en-el-panel-de-control-de-anuncios-de-weibo) en el dashboard de Sina Weibo.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Sina Weibo Ads.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

<Image align="center" alt="configuración de clics de Sina Weibo" src="https://files.readme.io/2c6cba9eba0b01cba638707df6bdb94c1a78b4d2b98f65d5210538311458b763-360002715417.png" />

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Sina Weibo Ads para que se active cuando los clientes potenciales hagan clic en un anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para Sina Weibo Ads.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Este partner no admite ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle al partner, ya sea que el partner actúe como una red de publicidad, agencia o ambas. Tenga en cuenta que, incluso si la atribución estuviera deshabilitada para el socio, la pestaña Permisos se encontraría activa y podría darle el control al socio.

<Image align="center" alt="sina-weibo-permissions.png" src="https://files.readme.io/a22be58687921e80108fe4b2cbd2863d9277a938a751ed5c666f147d78041c05-360002799478.png" />

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div id="setting-appsflyer-attribution-on-weibo-ads-dashboard" />

## Configurar la atribución de AppsFlyer en el panel de control de anuncios de Weibo

Inicia sesión en Sina Weibo Ads con este enlace: [https://ad.weibo.com/](https://ad.weibo.com)

Ve a la página **Tools** para subir tus aplicaciones en la sección Apps Management:

<Image align="center" alt="" src="https://files.readme.io/56d413ce75a2a3b4ca78a6928f60b9898bbd892d43d370197189da66ef9b078b-360000449769.png" />

Haz clic para añadir nuevas aplicaciones:

<Image align="center" alt="" src="https://files.readme.io/2c372745a5fe9b05325731e29e24f0b5097a43664e9a28e288d0b9300aecee8e-360000441885.png" />

Android: Introduce la página de descarga del APK (debe terminar en .apk) o sube el archivo APK.

iOS: introduce el enlace de iTunes.

<div id="setting-the-attribution-link" />

### Configurar el enlace de atribución

Ve a la página **Promociones** y crea una nueva serie de anuncios

<Image align="center" alt="" src="https://files.readme.io/eaf980c1adc0b134265162c114f66b1bf049a80336116db76d353ee5113a9ae5-360000449909.png" />

Si quieres adquirir nuevos usuarios para tu aplicación, selecciona el tipo de anuncio **Aumentar instalaciones de la app**, como se muestra a continuación:

<Image align="center" alt="" src="https://files.readme.io/b9e75ac4c9681cebfa06ba6965032b1ff0dc11b2da6e8c2b11cc9219555fa4e7-360000442105.png" />

<div id="setup-ad-series" />

### Configurar la serie de anuncios

Selecciona la aplicación que deseas promocionar:

<Image align="center" alt="" src="https://files.readme.io/cf9697b09d8d8b5416b8029cb20c2137eda24d9616bf2db2e1e45a3ec150fcf3-360000450049.png" />

Establece las funciones de la audiencia, el presupuesto y los períodos de promoción:

<Image align="center" alt="" src="https://files.readme.io/709297bb78cbd48218ee5438a40a5a12e78eeeecf4e35414ec36de89420791b6-360000442205.png" />

<div id="uploading-ad-creatives-and-set-the-attribution-link" />

### Cargar creatividades de anuncios y configurar el enlace de atribución

Weibo ofrece cuatro formatos de anuncio para promocionar instalaciones de la app:

* Publicación de Weibo
* Tarjetas grandes
* Tarjeta de app
* App con 9 imágenes

Todos los formatos de anuncio son compatibles con AppsFlyer Attribution.

<Image align="center" alt="" src="https://files.readme.io/5404349a21a783509e6de074826ace0db0d66248853f229ad444fabec95b8311-360000450369.png" />

Introduce el enlace de atribución de AppsFlyer

<div id="example" />

> 📄 **Ejemplo**
>
> ```http
> https://app.appsflyer.com/com.king.candycrushsaga?pid=sinaweibo_int&c=creative1
> 	&clickid={IMP}&md5_idfa={idfa_MD5}&md5_imei={imei_MD5}&redirect=false
> ```

<Image align="center" alt="" src="https://files.readme.io/27113a1303fea22bde74527c7103bfbda8e8fd7755c44a52508a02368e0a6407-360000442725.png" />

Completa cualquier configuración adicional y publica el anuncio.

<div id="note" />

> 📘 **Nota:**
>
> * Puedes previsualizar el formato del anuncio en la parte superior derecha de la página de configuración de la creatividad del anuncio.
> * Si no estás usando deep linking en la campaña del anuncio, deja vacío el campo de deep link.

<div id="creating-retargeting-campaigns-on-weibo-ads-dashboard" />

## Crear campañas de retargeting en el panel de control de anuncios de Weibo

En el nivel de la campaña publicitaria, configura el targeting, el presupuesto y el tiempo de la campaña:

<Image align="center" alt="sina-weibo-retargeting.png" src="https://files.readme.io/8225fbfd74d16bb1a3e2e816933cb22d5f581a219ee35dd7f9d5285bacd49d2d-360002715577.png" />

En el nivel del anuncio, configura el deep link y el enlace de atribución de AppsFlyer:

1. Elige ***deeplink+app*** y pega el deep link en el campo correspondiente:

   <Image align="center" alt="sina-weibo-retargeting-deeplink.png" src="https://files.readme.io/dc5666893ff99dcb808a15aa2e41396b359617e2f6271f246a10893d4b05eebe-360002715557.png" />

   <div id="example-1" />

   > 📄 **Ejemplo**
   >
   > ```http
   > myapp://products/page1&pid=sinaweibo_int&is_retargeting=true
   > ```

2. Copia el enlace de atribución del dashboard de AppsFlyer con todos los parámetros necesarios y pégalo en el campo del enlace de atribución:

   <Image align="center" alt="sina-weibo-retargeting-links.png" src="https://files.readme.io/edd0861728e19a0bc0e23641161c2365cf5c41eeccaa801bd4e8c3392215fe83-360002799598.png" />

   <div id="example-2" />

   > 📄 **Ejemplo**
   >
   > ```http
   > https://app.appsflyer.com/com.mycompany.myapp?pid=sinaweibo_int&c=test&clickid={IMP}
   > &md5_idfa={idfa_MD5}&md5_imei={imei_MD5}&redirect=false&is_retargeting=true
   > ```


   <div id="note-1" />

   > 📘 **Nota:**
   >
   > Ten en cuenta que todos los parámetros siguientes deben incluirse tanto en el deep link como en el enlace de atribución y ser idénticos en ambos enlaces:
   >
   > * `&pid=sinaweibo_int` — parámetro de ID de partner que identifica a Sina Weibo como fuente de medios
   > * `&c=campaign_name` — parámetro que identifica una campaña específica
   > * `&is_retargeting=true` — parámetro que identifica un anuncio como parte de una campaña de retargeting
   >
   > Si usas Deferred deep linking, incluye también los siguientes parámetros:
   >
   > * `&af_adset=adset_name`
   > * `&af_ad=ad_name`
   >
   > Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">estructura y los parámetros del enlace de atribución de AppsFlyer</Anchor> y los [enlaces de atribución](#attribution-link-tab) de Sina Weibo.

<div data-zendesk-anchors="setting-up-sina-weibo-ads=configuraci%C3%B3n-de-sina-weibo-ads h_01HKW6X6G9WGKHT7MXM3BKYX40=configuraci%C3%B3n-de-sina-weibo-ads h_01HKW6X6G9865NFC261ZCPC4AM=integration-tab activate-partners=activar-los-partners h_01HKW6X6G98F7ERDGKN7K5PDVE=activar-los-partners h_01HKW6X6GAR48FSFX7DVEWAMX8=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6X6GA0FPN5EMR68FH2HSR=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n retargeting-settings=configuraciones-de-retargeting h_01HKW6X6GA287ZKAWG69497WRN=configuraciones-de-retargeting clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW6X6GABBB9ZP8GP87JYZAE=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6X6GAY9GP9P57RFPSFTVN=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6X6GADFS59WJT2GHYQ317=cost-tab h_01HKW6X6GAG7TM4WFNJFHGY9QN=ad-revenue-tab h_01HKW6X6GAK8PN5PBFPZTGC0ES=permissions-tab setting-appsflyer-attribution-on-weibo-ads-dashboard=configurar-la-atribuci%C3%B3n-de-appsflyer-en-el-panel-de-control-de-anuncios-de-weibo h_01HKW6X6GA96QHGJY220JF5DF4=configurar-la-atribuci%C3%B3n-de-appsflyer-en-el-panel-de-control-de-anuncios-de-weibo setting-the-attribution-link=configurar-el-enlace-de-atribuci%C3%B3n h_01HKW6X6GA6XJSV02NTNDSRZ19=configurar-el-enlace-de-atribuci%C3%B3n setup-ad-series=configurar-la-serie-de-anuncios h_01HKW6X6GAJBYM89RYH65BAVNH=configurar-la-serie-de-anuncios uploading-ad-creatives-and-set-the-attribution-link=cargar-creatividades-de-anuncios-y-configurar-el-enlace-de-atribuci%C3%B3n h_01HKW6X6GC2RHPJXWZAX8S758B=cargar-creatividades-de-anuncios-y-configurar-el-enlace-de-atribuci%C3%B3n h_01HKW6X6GCNS88DFZTMM7BXMKT=ejemplo h_01HKW6X6GCBQNG4Q2RHJPCRCKS=nota creating-retargeting-campaigns-on-weibo-ads-dashboard=crear-campa%C3%B1as-de-retargeting-en-el-panel-de-control-de-anuncios-de-weibo h_01HKW6X6GE2RVQGSN9JM63SZYA=crear-campa%C3%B1as-de-retargeting-en-el-panel-de-control-de-anuncios-de-weibo h_01HKW6X6GEKZWAPZ6V2EXGY9SA=ejemplo-1 h_01HKW6X6GFQQSY19CRREVR8GRY=ejemplo-2 h_01HKW6X6GF815M1XE9HF631F1W=nota-1" />

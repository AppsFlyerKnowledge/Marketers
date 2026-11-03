---
title: Preguntas frecuentes sobre Meta Ads
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-09T10:04:49Z'
  edited_at: '2026-08-12T12:20:09Z'
  id: 4410472805649
  locale: es
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/es/articles/4410472805649
---
> **En resumen:** Encuentra respuestas a las preguntas frecuentes sobre el uso de Meta Ads en AppsFlyer.

## Preguntas frecuentes sobre Meta Ads

<div id="i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard" />

<Accordion title="No veo los clics de campaña de Meta Ads en el dashboard de AppsFlyer">

Por defecto, Meta Ads envía solo los datos de conversión y de engagement. Sin embargo, también puedes comenzar a obtener fácilmente <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#cost-clicks-and-impressions">clics, impresiones y datos de costos para tus campañas de Meta Ads</Anchor>.

</Accordion>

<div id="can-appsflyer-show-the-campaign-level-and-ad-groups" />

<Accordion title="¿Se pueden ver en AppsFlyer los niveles de campaña y los grupos de anuncios?">

Sí. De hecho, en AppsFlyer también se puede ver el nivel de anuncio individual, por lo que se dispone de tres niveles de desglose con Meta Ads: campañas >> grupos de anuncios >> anuncios.

</Accordion>

<div id="is-facebook-data-shown-in-realtime" />

<Accordion title="¿Los datos de Meta Ads se muestran en tiempo real?">

Sí, todas las instalaciones y los eventos in-app subsiguientes se muestran en tiempo real. Sin embargo, los datos de clics, impresiones y costos que AppsFlyer obtiene en forma agregada de Meta Ads los obtiene periódicamente cada pocas horas.

</Accordion>

<div id="when-can-i-see-a-new-campaigns-data-on-appsflyer" />

<Accordion title="¿Cuándo puedo ver los datos de una campaña nueva en AppsFlyer?">

Para ver los datos de nuevos anuncios, conjuntos de anuncios y campañas en Meta Ads, estos deben generar al menos una instalación.

Por ejemplo, un anuncio nuevo ha generado 100 clics y ninguna instalación, y no se muestra en el dashboard de AppsFlyer ni en los datos. Otro anuncio tiene solo un clic y una instalación, pero se muestra en AppsFlyer.

</Accordion>

<div id="how-can-i-get-more-installs-from-facebook" />

<Accordion title="¿Cómo puedo obtener más instalaciones de Meta Ads?">

Si has activado la función de retargeting para Meta Ads, puedes obtener hasta un 100% más de instalaciones en tus campañas de adquisición de usuarios, de manera gratuita.  
¿Cómo? ¿Cómo? Descúbrelo <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#what-is-srn-mistargeting">aquí</Anchor>.

</Accordion>

<div id="how-can-i-get-device-level" />

<Accordion title="¿Cómo puedo obtener datos de instalación de Android a nivel de dispositivo usando Google Play y Meta Install Referrer?">

#### Google Play Install Referrer API

La API Google Play Install Referrer permite a los anunciantes recuperar datos de atribución, como información de campaña, de las instalaciones que se originaron en la tienda Google Play. Esta API debe <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">integrarse en tu aplicación</Anchor> y funciona al pasar datos de la Referencia de la instalación cuando la aplicación se abre por primera vez después de la instalación. Los campos de atribución estarán disponibles en los reportes de raw data de AppsFlyer con el tipo de coincidencia `gp_referrer` una vez que se envíe la clave de descifrado obligatoria.

#### Meta Install Referrer

La Referencia de la instalación de Meta proporciona metadatos de campaña adicionales almacenados localmente en el dispositivo. Puedes acceder a esto a través del [SDK de AppsFlyer](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer). Complementa Google Play Install Referrer al habilitar datos más enriquecidos, incluidos datos de clic e impresiones, y puede abarcar varias sesiones. La atribución mediante la Referencia de la instalación de Meta utiliza tipos de coincidencia como `fb_referrer` (Facebook) y `ig_referrer` (Instagram).

#### Campos de atribución de campaña

* ID de anuncio
* Nota
* ID del adset
* Nota
* Cadena
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.
* ID de cuenta
* Canal

#### Notas sobre el SDK y la configuración

* Se requiere la versión 5.4.0+ del SDK de AppsFlyer para los datos del referrer de Google Play.
* El soporte del referrer de Meta depende de una configuración correcta del SDK. Consulta <Anchor target="_blank" href="/marketers/es/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">este boletín</Anchor> para ver los detalles de implementación.

#### Envío de la clave de descifrado

Ambos tipos de referrer requieren una clave de descifrado de tu cuenta de desarrollador de Meta. Solo tienes que proporcionar esta clave una vez por aplicación. Los pasos son los siguientes:

1. Inicia sesión en tu portal de desarrollador de Meta.
2. Ve a **My Apps** y selecciona la aplicación correspondiente.
3. Ve a **Settings > Basic** y localiza la «Install Referrer decryption key».
4. En AppsFlyer, ve a **Collaborate > Active Integrations > Meta ads**.
5. Pega la clave en el campo **Install Referrer Decryption Key** y guarda los cambios.

</Accordion>

<div id="do-you-make-facebook-raw-data-available-to-agencies" />

<Accordion title="¿El raw data de Meta Ads está disponible para las agencias?">

N.º No se nos permite proporcionar raw data de Meta Ads a las agencias. Esto se debe a que las agencias se consideran terceros según los términos del servicio de Meta.

</Accordion>

<div id="i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports" />

<Accordion title="No veo raw data de Meta Ads en los reportes de instalación y eventos in-app">

Por defecto, Meta Ads no permite la distribución de datos a nivel de usuario. Sin embargo, si aceptas las condiciones de Meta Advanced Mobile Measurement (AMM), podrás acceder sin restricciones a los datos de atribución a nivel de dispositivo para los anuncios de Meta. Consulta <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">Habilita los datos a nivel de dispositivo de Meta ads.</Anchor>

</Accordion>

<div id="any-specific-columns-for-facebook-in-appsflyers-performance-reports" />

<Accordion title="¿Hay alguna columna específica para Meta Ads en los reportes de rendimiento de AppsFlyer?">

Sí. Los reportes de rendimiento tienen estructuras de columnas estáticas en cualquier combinación de fuentes de medios seleccionadas, que presentan información detallada a nivel de campaña.  
No obstante, cuando descargas reportes de rendimiento SOLO para Meta Ads, AppsFlyer les agrega cuatro columnas que presentan información detallada a nivel de anuncio individual. Las columnas agregadas son Nombre del adset, ID del adset, Nombre de grupo de anuncios (anuncio único) e ID de grupo de anuncios.

[![](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)

</Accordion>

<div id="can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer" />

<Accordion title="¿Puedo trabajar con partners de administración de campañas de Meta y medir el rendimiento con AppsFlyer?">

Sí. AppsFlyer está integrado con docenas de partners de administración de campañas de Meta. Estos partners se pueden configurar para la atribución desde la página de integraciones activas en el dashboard.

Para conocer más detalles sobre cómo configurar la atribución con los partners de administración de campañas de Meta, haz clic <Anchor target="_blank" href="/marketers/es/docs/configuring-meta-campaign-management-partners">aquí</Anchor>.

</Accordion>

<div id="what-should-i-do-when-i-receive-the-following-warning" />

<Accordion title="¿Qué debo hacer cuando recibo la siguiente advertencia?">

[![](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)

* Verifica el ID de aplicación de Facebook y verifica si tienes alguna restricción de geolocalización o edad en tu ID de aplicación de Facebook.
* Si la atribución ya está funcionando, esto quiere decir que la aplicación ya está disponible públicamente en el portal para desarrolladores de Meta y que puedes ignorar este mensaje de error con tranquilidad.

</Accordion>

<div id="what-happens-with-different-lookback-windows-than-on-facebook" />

<Accordion title="¿Qué sucede con las ventanas de lookback que son distintas a las de Meta Ads?">

7 días para clics y 1 día para impresiones son los tiempos máximos y predeterminados para las ventanas de lookback de Meta Ads.

La configuración de ventanas más cortas en AppsFlyer disminuye la atribución de Meta Ads en AppsFlyer. Por el contrario, la configuración de ventanas más largas en AppsFlyer da como resultado más atribución del lado de AppsFlyer que de Meta.

Por lo tanto, para minimizar las discrepancias, se recomienda configurar las ventanas de lookback de Meta Ads en AppsFlyer en 7 días para los clics y 1 día para las impresiones.

</Accordion>

<div id="what-are-the-facebook-api-parameters" />

<Accordion title="¿Cuáles son los parámetros de la API de Meta?">

En algunas APIs de AppsFlyer, los parámetros de Meta tienen nombres diferentes a los que se muestran en el dashboard, por motivos de compatibilidad con versiones anteriores. Consulta la tabla a continuación:

| Datos de conversión | Raw data de AppsFlyer | Meta |
| --- | --- | --- |
| campaña | campaña | campaign\_group\_name |
| id\_campaña | ID de campaña | campaign\_group\_id |
| adgroup | Anuncio | adgroup\_name |
| adgroup\_id | Retargeting: Primer inicio después del re-engagement o la reatribución. | adgroup\_id |
| conjunto de anuncios | Conjunto de anuncios | campaign\_name |
| id\_anuncio | ID de adset | id\_campaña |
| agencia | Fuente de medios | N/D |
| is\_fb | Fuente de medios | is\_fb |
| af\_canal | Ejemplo | publisher\_platform |
| af\_siteid | Parámetros de seguimiento adicionales utilizados para la atribución. | publisher\_platform cuando el valor de `publisher_platform` no es igual a `facebook`; de lo contrario, `null`. |

</Accordion>

<div id="how-long-do-you-keep-facebook-s-userlevel-data" />

<Accordion title="¿Cuánto tiempo conservan los datos de nivel de usuario de Meta Ads?">

Meta Ads exige que los proveedores de atribución eliminen sus datos a nivel de usuario 6 meses después de la instalación. Esto significa que los eventos efectuados por estos usuarios 6 meses después de que hayan instalado la aplicación se cuentan como orgánicos.  
Los datos agregados anteriores permanecen iguales.  
Esto es pertinente para todos los canales de Meta Ads (aplicación de Facebook, Instagram, Messenger y AudienceNetwork).

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-meta-ads" />

<Accordion title="¿Los Universal Links de iOS y los App Links de Android son compatibles con Meta Ads?">

Los Universal Links de iOS y los App Links de Android son compatibles y se pueden usar en Meta Ads. Para más información, consulta el <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">centro de ayuda de Meta</Anchor>.

* Para los anuncios estáticos (no catalogados), los Universal Links de iOS y App Links de Android solo se admiten en campañas en las que se selecciona **App** como destino.
* Para los anuncios dinámicos, los Universal Links de iOS, los App Links de Android y los esquemas URI se pueden usar como se indica [aquí](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).

**Nota:** Los Universal Links de iOS y los App Links de Android solo se admiten en anuncios de pago.

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content" />

<Accordion title="¿Los Universal Links de iOS y los App Links de Android son compatibles con el contenido no pago de Meta?">

Los Universal Links de iOS y los App Links de Android solo se admiten en anuncios de pago. En el contenido de apps sociales no pagadas, quizás sea necesario configurar un esquema URI o una landing page para la aplicación de redes sociales para redireccionar a los usuarios o establecer deep links con ellos.

</Accordion>

<div id="aem-attribution-is-not-working" />

<Accordion title="La atribución de AEM no funciona">

Si la opción de **Intercambio avanzado de datos** está activada y no recibes atribución con Meta, verifica si los eventos compartidos cumplen con los criterios de elegibilidad de Meta. Consulta la [documentación de Meta](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

</Accordion>

<div id="can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads" />

<Accordion title="¿Se pueden usar los enlaces de OneLink para la apertura de aplicaciones y los deep linking en los anuncios dinámicos de productos?">

Sí. Los enlaces de OneLink con App Links, Universal Links o esquemas URI configurados son compatibles con los anuncios dinámicos de productos. Puedes usar enlaces de OneLink en tu feed de datos para catálogos usados en anuncios dinámicos en los campos **applink.ios\_url** y **applink.android\_url.**

</Accordion>

<div id="conversion-events-are-not-sent-to-meta-ads" />

<Accordion title="Los eventos de conversión no se envían a Meta Ads">

Puede que tengas un paquete Zero que no incluya Atribución.

</Accordion>

<div id="can-i-use-get" />

<Accordion title="¿Puedo usar Get Conversion Data (GCD) para recuperar datos de conversión de Meta?">

**Sí.** Puedes seguir usando **GCD** para recuperar datos de conversión de Meta, según la configuración de tu aplicación y el estado del acuerdo AMM:

* **Si el SDK de Facebook está integrado en tu aplicación:**

  Como se explica en <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#deferred-deep-linking">la documentación de Deferred deep linking (DDL)</Anchor>, puedes recuperar los datos de DDL y usarlos mediante GCD.
* **Si el SDK de Facebook no está integrado en tu aplicación:**

  Aun así, puedes recuperar los **nombres de campaña, conjunto de anuncios y anuncio** mediante GCD, siempre que <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#meta-ads">se haya firmado Advanced Mobile Measurement (AMM)</Anchor>. En este caso, puedes usar estos valores para aplicar tu propia **lógica personalizada de Deep Linking**.

> 📘 **Nota:**
>
> Las políticas de intercambio de datos de Meta pueden afectar al nivel de detalle disponible a través de GCD. Asegúrate de que AMM esté firmado para maximizar los datos disponibles a nivel de campaña.

</Accordion>

## Preguntas frecuentes sobre el costo de Meta Ads

<div id="getting-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="Obtener datos de costos de Meta Ads en el dashboard de AppsFlyer">

AppsFlyer obtiene datos de gastos (incluidos clics e impresiones) de las campañas de Meta Ads, si se produjeron una o más instalaciones durante los 7 días anteriores.

Si una campaña de Meta Ads se involucra con múltiples plataformas (Android, iOS, desktop, etc.), el costo en el dashboard es específico de la plataforma y Meta Ads lo calcula.

<Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Obtener el costo de Meta Ads con clics e impresiones incluidos</Anchor>.

</Accordion>

<div id="facebook-cost-example" />

<Accordion title="Ejemplo de costo de Meta Ads">

Un anunciante ejecuta campañas con Meta Ads. En AppsFlyer, el anunciante ve lo siguiente:

![mceclip2.png](https://files.readme.io/a1aa5847db5c0b873b34b1d4de43ade7d4109608371e05a84342122e56d0ce08-4411031032081.png)

Meta Ads proporciona a AppsFlyer la información de costos. AppsFlyer calcula la cantidad de **instalaciones** mediante las reglas de atribución de AppsFlyer. Como resultado, el eCPI que calcula Meta Ads y el que calcula AppsFlyer generalmente difieren.

</Accordion>

<div id="i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="No puedo ver el historial de costos de Meta Ads en el dashboard de AppsFlyer">

Tras el primer inicio de sesión como administrador en Meta Ads, tal como se describiera anteriormente, AppsFlyer comenzará a recibir datos de costos de Meta Ads con carácter retroactivo de hasta 7 días anteriores para las campañas existentes. Los datos de costos no están disponibles de antemano.

En sincronizaciones posteriores, AppsFlyer recibe los datos de los últimos 7 días. Esto significa que los datos de costos, clics e impresiones se recopilan para todas las campañas que tengan al menos 1 conversión durante los últimos 7 días.

</Accordion>

<div id="can-i-stop-cost-data-sync" />

<Accordion title="¿Puedo detener la sincronización de datos de costos?">

Para detener la sincronización de datos de costos con Meta Ads, <Anchor target="_blank" href="https://www.facebook.com/help/405094243235242">elimina AppsFlyer de tu integración empresarial en tu cuenta de Meta Ads</Anchor>.

</Accordion>

<div id="cost-data-was-fine-for-a-few-months-but-it-stopped-displaying" />

<Accordion title="Por unos meses no hubo problema con la visualización de los datos de costos, pero ya no se muestran.">

Meta Ads puede restablecer este permiso para obtener los datos de costos cada pocos meses. Si notas que los datos de costos dejaron de aparecer en el dashboard, repite los pasos de inicio de sesión como administrador de Meta Ads.

Si el usuario administrador de Meta Ads cambiara su contraseña de Meta Ads, también deberían repetirse los pasos de inicio de sesión.

</Accordion>

<div id="i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer" />

<Accordion title="Hice clic en mi anuncio de Facebook, hace apenas 5 minutos. ¿Por qué no veo el clic en AppsFlyer?">

AppsFlyer obtiene datos totales de clics, impresiones y costos de Meta Ads periódicamente con intervalos de pocas horas. Por lo tanto, es posible que transcurran horas sin que estas acciones se muestren en el dashboard de AppsFlyer.

</Accordion>

<div id="can-i-get-raw-data-on-clicks-and-impressions-from-facebook" />

<Accordion title="¿Puedo obtener raw data sobre clics e impresiones de Meta Ads?">

Como AppsFlyer obtiene solo datos agregados de clics e impresiones de Meta Ads, el conjunto entero de raw data de clics e impresiones no está disponible. El único raw data de clics e impresiones disponible en los reportes de raw data es aquel que derivó en instalaciones.

</Accordion>

<div id="are-there-limitations-of-facebook-cost-data-by-geo" />

<Accordion title="¿Existen limitaciones de los datos de costos de Meta Ads por geolocalización?">

Si filtras por geolocalización en el dashboard de AppsFlyer, podrás ver el resumen y desglose de los datos de costos de Meta Ads.

Estos datos solo están disponibles para "Campañas de instalación de aplicaciones móviles" en Meta Ads.

Además, los datos de costos por geolocalización solo están disponibles para campañas de plataforma única. Esto significa que las campañas que tienen un conjunto de anuncios para Android, y otro para iOS, no pueden tener datos de costos específicos por geolocalización. **Para obtener los datos de costos completos, dedica una campaña a cada plataforma**.

</Accordion>

<div id="what-are-the-limitations-of-facebook-cost-data-in-master-api" />

<Accordion title="¿Cuáles son las limitaciones de los datos de costos de Meta Ads en la API maestra?">

Meta Ads no admite la agrupación de datos de costos por geolocalización y canal simultáneamente en los <Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api">reportes de la API maestra</Anchor>.

Para crear un reporte con datos de costos completos, agrúpalos por una sola de estas dimensiones.

</Accordion>

<div id="the-total-cost-doesnt-match" />

<Accordion title="¿Por qué el costo total que se muestra en Meta y AppsFlyer no coincide?">

Existen diferencias entre los modelos de atribución de Meta Ads y AppsFlyer. Estas diferencias pueden producir discrepancias en los datos de costos de Meta Ads:

* **Atribución de dispositivos cruzados de Meta Ads**: A veces puede causar problemas cuando una campaña para una plataforma (iOS/Android) muestra una instalación con su costo para otra plataforma.
* **Campañas de Meta Ads que no son para móviles:** En este tipo de campañas, como las campañas de clic de enlace de Meta Ads, los usuarios de ordenadores pueden instalar aplicaciones móviles en algún momento. Para estas campañas de dispositivos cruzados, AppsFlyer no muestra el costo. Sin embargo, si el clic de enlace se ejecuta en el mismo dispositivo en el que se instaló la aplicación, sí se reciben datos de costos.  
  Por ejemplo, un usuario de Facebook hace clic en un anuncio que conduce a la landing page del anunciante en un ordenador. Una semana después, el mismo usuario de Facebook instala la aplicación iOS del anunciante en un dispositivo iPhone. Si bien la instalación es atribuida y aparece en el dashboard de AppsFlyer, el costo de esta instalación multiplataforma no aparece.
* **Campañas con 0 resultados en los últimos 7 días**: AppsFlyer sincroniza el costo solo para campañas con instalaciones/conversiones en los últimos 7 días. Si recién se establece el costo de Meta Ads para las campañas que estuvieron inactivas por más de 7 días de antelación no se mostrarán los costos.
* **Anuncios eliminados y archivados**: Meta no informa a AppsFlyer el costo de los anuncios eliminados y archivados, pero este costo se refleja en el dashboard de Meta. Esto puede causar una discrepancia entre los reportes de Meta y AppsFlyer al comparar los datos a nivel de campaña.

</Accordion>

<div id="why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical" />

<Accordion title="¿Por qué el cálculo de AppsFlyer del eCPI es diferente del costo calculado por Meta Ads, mientras que el costo total es idéntico?">

El costo por instalación se calcula dividiendo el costo total por el número de instalaciones. Dado que <Anchor target="_blank" href="/marketers/es/docs/meta-ads-discrepancies">AppsFlyer cuenta las instalaciones de manera diferente que Meta Ads</Anchor>, el eCPI puede ser diferente.

</Accordion>

<div id="why-doesnt-cost-data-include-data-from-all-campaigns" />

<Accordion title="¿Por qué los datos de costos no incluyen datos de todas las campañas?">

Cuando el usuario que realiza el inicio de sesión de Meta Ads (descrito anteriormente) no tiene acceso a algunas de las campañas en ejecución, el resultado son campañas que se muestran en el dashboard de AppsFlyer, pero carecen de algunos datos sobre costos, clics e impresiones.

**Nota:** Aunque varios usuarios de Meta Ads pueden tener permiso para ejecutar campañas en Meta Business Manager, solo se requiere uno para iniciar sesión en Meta Ads.

</Accordion>

<div id="is-facebook-cost-data-displayed-for-retargeting-campaigns" />

<Accordion title="¿Se muestran los datos de costos de Meta Ads para las campañas de retargeting?">

Los datos de costo y ROI para campañas de retargeting se pueden encontrar en la vista **unificada** de los <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">reportes de cohortes</Anchor>.

</Accordion>

<div id="why-does-the-facebook-cost-configuration-window-close-before-login" />

<Accordion title="¿Por qué se cierra la ventana de configuración de costos de Meta Ads antes de iniciar sesión?">

Si has iniciado sesión en Meta Ads en el mismo navegador en el que estás realizando la configuración, la ventana se conecta automáticamente a Meta Ads usando esas credenciales. Si ya se ha otorgado acceso a AppsFlyer, entonces no hay nada que hacer y se cierra la ventana.

</Accordion>

<div id="why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store" />

<Accordion title="¿Por qué hay una discrepancia en los datos de costos para las aplicaciones en la tienda de aplicaciones de Amazon?">

Contrariamente a los datos de AppsFlyer, Meta Ads no distingue entre los datos de costos de las aplicaciones de Android en lugar de las aplicaciones de Amazon, que están basadas en Android. Por lo tanto, los datos de costos de los usuarios de Amazon pueden atribuirse a las campañas dirigidas a otros usuarios de Android y no a las campañas originales de Amazon.

</Accordion>

<div id="how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked" />

<Accordion title="¿Cómo conectar los datos de costos de una nueva cuenta de Meta Ads mientras mi cuenta anterior está vinculada?">

Si deseas cambiar a una nueva cuenta de anuncios, pero tu costo de Meta Ads ya está vinculado a través de AppsFlyer con tu antigua cuenta de anuncios, debes desconectar la cuenta de anuncios a través de Meta Ads y conectar la nueva cuenta de anuncios en AppsFlyer.

1. En Meta Ads, ve a **Configuración** > **Integración empresarial**.
2. En la pestaña **Activar**, elimina la integración con AppsFlyer.  

   [![](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)
3. Ve al dashboard de AppsFlyer y conecta el costo con la nueva cuenta de anuncios.

</Accordion>

## Preguntas frecuentes sobre el SDK de Facebook

<div id="who-needs-facebooks-sdk" />

<Accordion title="¿Quién necesita el SDK de Facebook?">

Es posible que la aplicación ya tenga el SDK de Facebook integrado en ella, antes del SDK de AppsFlyer. Incluso si no es así, tal vez te preguntes si realmente necesitas el SDK de Facebook además del SDK de AppsFlyer. Y si es así, ¿pueden coexistir los dos sin reportes duplicados?

Tu aplicación no requiere el SDK de Facebook para lo siguiente:

* **Adquisición de usuarios**: En general, el SDK de AppsFlyer se encarga de todos los fines de atribución de adquisición de usuarios móviles de tus usuarios de Meta Ads, incluidos los engagements, las instalaciones, las sesiones y los eventos post-instalación.
* **Deep linking**: Para abrir la aplicación cuando se hace clic en el enlace y enlazar a los usuarios a una página o actividad específica en la aplicación, puedes usar OneLink sin el SDK de Facebook. Puedes usar los Universal Links de iOS, los App Links de Android y los esquemas URI para hacerlo. Para más información, consulta el <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">centro de ayuda de Meta</Anchor>.  

  **Nota:**   
  Para los anuncios estáticos (no catalogados), los Universal Links de iOS y los App Links de Android solo se admiten en campañas en las que se selecciona **Aplicación** como destino.  
  Por ejemplo, si configuras una campaña de concientización en Meta, ya que esta campaña no permite seleccionar la **aplicación** como destino, no se admiten los Universal Links de iOS ni los App Links de Android.  

  Para los anuncios dinámicos, los Universal Links de iOS, los App Links de Android y los esquemas URI se pueden usar como se indica [aquí](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).  

  Meta Ads obtiene la URL de OneLink y la usa para crear un enlace de aplicación de Meta Ads que abre la aplicación y enlaza al usuario.

Tu aplicación requiere el SDK de Facebook además del SDK de AppsFlyer para lo siguiente:

* **Deferred Deep Linking**:  
  Actualmente, solo es posible acceder a los datos DDL de Meta Ads a través del <Anchor target="_blank" href="/marketers/es/docs/get-conversion-data-using-appsflyer-sdk-overview">método antíguo de datos de conversión</Anchor>. Los clientes deben coordinarse con Meta y, por lo general, se requiere el SDK de Facebook para acceder a estos datos.
* **Datos de campañas de anuncios dinámicos de productos**: Solo puedes obtener datos de anuncios dinámicos de productos del SDK de Facebook.
* **Otras características de Meta Ads**: Es posible que necesites el SDK de Facebook por razones no relacionadas con la atribución, como la autenticación, la monetización de anuncios, el uso compartido de redes sociales, las invitaciones de usuarios, etc.

> 📘 **Nota:**
>
> La información y las recomendaciones anteriores sobre deep linking y deferred deep linking se basan en las pruebas exhaustivas que realizamos utilizando las herramientas de demostración/vista previa disponibles de Meta Ads, que utilizan un mecanismo diferente al de los anuncios en directo.

</Accordion>

<div id="avoiding-duplicates-with-facebook-sdk" />

<Accordion title="Cómo evitar duplicados con el SDK de Facebook">

Si tienes <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#faq_593792547454717">ambos SDKs de AppsFlyer y Facebook en tu aplicación</Anchor>, los eventos in-app y de instalación se reportan vía el SDK de Facebook y, a continuación, vía postbacks a los servidores de Meta Ads a través de AppsFlyer. ¿Cómo evitar estos reportes duplicados?

* **Para las instalaciones**, Meta deduplica las instalaciones. Esto significa que **no hay duplicación** y cada instalación se cuenta solo una vez.
* **En el caso** de los eventos in-app, los Meta Ads no desduplican los eventos in-app, lo que puede generar un recuento doble y reportes inexactos de eventos in-app. Para evitar tal duplicación en Meta Ads, considera cualquiera de las siguientes opciones:
  * No configures eventos en el SDK de Facebook.
  * Para Android: desactiva la <Anchor target="_blank" href="/marketers/es/docs/meta-ads-in-app-event-mapping">asignación de eventos in-app de Meta Ads</Anchor> desde AppsFlyer.  
    Ten en cuenta que, para habilitar la atribución SKAN para iOS 14.5+, deberás <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-interoperation-with-meta-ads#in-app-event-mapping">asignar eventos in-app a Meta Ads</Anchor>.

</Accordion>

## Preguntas frecuentes sobre la atribución de Meta Ads

<div id="attributing-agencies-with-facebook" />

<Accordion title="Atribución de agencias con Meta Ads">

Las agencias y los partners de administración de campañas de Meta pueden ejecutar y atribuir campañas de Meta Ads en nombre de los anunciantes en AppsFlyer, o incluso junto con las propias campañas de Meta Ads de los anunciantes. Para que las campañas de la agencia puedan atribuirse a la agencia, el nombre de la campaña DEBE comenzar con el nombre de la agencia.

Ten en cuenta que para los usuarios de iOS 14, solo **una** agencia puede ejecutar campañas para una cuenta de anuncios específica. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-interoperation-with-meta-ads#interoperabilidad-skan-appsflyer---meta-ads">interoperabilidad de SKAdNetwork de AppsFlyer y Meta Ads</Anchor>.

Más información sobre la atribución de instalaciones de agencias y Meta Ads <Anchor target="_blank" href="/partners/es/docs/about-agency-accounts#configuraciones-de-srn">aquí</Anchor>.

Además, las **agencias no pueden modificar las ventanas de lookback de Meta Ads ni el control de retargeting**. De ser necesario, deben solicitar al anunciante que realice los cambios requeridos.

Además, las agencias no pueden modificar los postbacks de eventos in-app enviados a Meta Ads. Esto se debe a que Meta Ads exige recibir información sobre todas las instalaciones, incluidas las no atribuidas a Meta Ads (y, por lo tanto, no podrán ser aportadas por la agencia).

La siguiente imagen muestra todos los parámetros que deberá configurar el anunciante para que la agencia pueda administrar sus campañas de Meta Ads:

[![advertiser-vs-agency-facebook-int-new.png](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)

</Accordion>

<div id="attribution-for-facebook-for-outofstore-android-apps" />

<Accordion title="Atribución de aplicaciones Android out-of-store para Meta Ads">

Meta Ads no permite crear campañas de instalación de aplicaciones móviles para aplicaciones Android de mercados fuera de la tienda; por ejemplo, Baidu.

Sin embargo, puedes anunciar y registrar instalaciones para aplicaciones out-of-store en Meta Ads siguiendo estas instrucciones:

1. El desarrollador debe preparar un APK independiente para cada mercado fuera de la tienda que utilices para anunciar tu aplicación. Obtén más <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">detalles aquí</Anchor>.
2. Crea una campaña de **Tráfico** o de **Conversiones** en Meta Ads, con la atribución móvil habilitada, que envía clientes potenciales a una landing page.
3. La landing page debe incluir un botón **Descargar aplicación**, que enlaza directamente al mercado fuera de la tienda donde existe el APK.
4. El cliente potencial hace clic en el botón y es redireccionado al mercado out-of-store. Después de completar la instalación, AppsFlyer atribuye al usuario a Meta Ads, a través de la API MMP.

> 📘 **Nota:**
>
> La misma solución se aplica a las aplicaciones en Google Play y App Store, los cuales <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">requieren una landing page</Anchor> antes de la redirección al mercado.

Para obtener instrucciones específicas de atribución para aplicaciones de Amazon, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#driving-users-to-the-amazon-app-store-from-facebook">aquí</Anchor>.

</Accordion>

<div id="what-is-facebook-android-and-ios-crossattribution" />

<Accordion title="¿Qué es una atribución cruzada de Meta Ads para Android e iOS?">

Meta Ads identifica a los usuarios en función de su cuenta de Meta Ads. Algunos usuarios tienen dispositivos iOS y Android asociados a la misma cuenta de Meta Ads.

Si dicho usuario hace clic o ve un anuncio de tu aplicación en su dispositivo Android, pero instala la aplicación en su dispositivo iOS, Meta Ads considera que ha generado la instalación. Como resultado, aparece un nombre de campaña de Android en tu dashboard de iOS.

> 📄 **Ejemplo**
>
> Andrew Josef está ocupado con su dispositivo Android. Mientras lo utiliza, hace clic en un anuncio de campaña de Meta para Android para una aplicación llamada **Bubbles**. No descarga la aplicación.
>
> Un día después, Andrew Josef decide descargar la aplicación **Bubbles** orgánicamente en su dispositivo iOS y la abre.
>
> Ante esta situación, la atribución de AppsFlyer toma la campaña de Meta Ads para Android y la presenta en el dashboard de iOS donde Andrew Josef la descargó y abrió.

</Accordion>

<div id="what-are-facebook-ads-channels" />

<Accordion title="¿Qué son los canales de Meta Ads?">

Con Meta Ads se pueden ver datos desglosados no solo por campañas, conjuntos de anuncios y anuncios, sino también por canales de Meta Ads (llamados ubicaciones):

* **Facebook**: Usuarios de la aplicación de Facebook
* **Instagram**: Usuarios de la aplicación de Instagram
* **Messenger**: Usuarios de la aplicación Messenger de Facebook
* **AudienceNetwork**: Usuarios de otras aplicaciones que pertenecen o están afiliados a Meta Ads
* **Threads**: usuarios de la aplicación de Threads
* **WhatsApp**: usuarios de la aplicación de WhatsApp

Utiliza estos datos para comparar la calidad de los usuarios que obtienes de los diferentes canales.

![Facebook_channels.png](https://files.readme.io/f6b51baf3056f42ee32ac9709b1e4b3661580ce6148acfa36fc2bad102e7bfd8-4411036713745.png)

</Accordion>

<div data-zendesk-anchors="facebook-ads-faq=preguntas-frecuentes-sobre-meta-ads h_01HD1JTW2EP1MY3DD9136E9CHC=preguntas-frecuentes-sobre-meta-ads h_01HD1JTW2EN36V9SHH11283Y3A=i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard h_01HD1JTW2EJE0K034KSV8B3WZQ=can-appsflyer-show-the-campaign-level-and-ad-groups h_01HD1JTW2EFKCJMNBXBK2C55DN=is-facebook-data-shown-in-realtime h_01HD1JTW2E4SVC1Z9C3K6XJB2G=when-can-i-see-a-new-campaigns-data-on-appsflyer h_01HD1JTW2ECWSXFKQC1YBP1592=how-can-i-get-more-installs-from-facebook h_01K8B4YFDKKYP25V6NR12CE9RF=how-can-i-get-device-level h_google_play_referrer=google-play-install-referrer-api h_meta_install_referrer=meta-install-referrer h_attribution_fields=campos-de-atribuci%C3%B3n-de-campa%C3%B1a campaign-attribution-fields=campos-de-atribuci%C3%B3n-de-campa%C3%B1a h_sdk_requirements=notas-sobre-el-sdk-y-la-configuraci%C3%B3n sdk-requirements=notas-sobre-el-sdk-y-la-configuraci%C3%B3n h_decryption=env%C3%ADo-de-la-clave-de-descifrado decryption-key=env%C3%ADo-de-la-clave-de-descifrado h_01HD1JTW2ED762B3K1QS6QC38M=do-you-make-facebook-raw-data-available-to-agencies h_01HD1JTW2EWQGK4QA9W8DFZTMH=i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports h_01HD1JTW2EYSBJ38WNS1HP5MCE=any-specific-columns-for-facebook-in-appsflyers-performance-reports h_01HD1JTW2ETTXQAP7ZSTMVGA8K=can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer h_01HD1JTW2EPY8W5Z84PBWSM86G=what-should-i-do-when-i-receive-the-following-warning h_01HD1JTW2ED2DNPTXAFYJTTGV3=what-happens-with-different-lookback-windows-than-on-facebook h_01HD1JTW2EXF1R0MA91ZSW7QG4=what-are-the-facebook-api-parameters how-long-do-you-keep-facebook%E2%80%99s-userlevel-data=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EPDNSY30J45JB443A=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EN8THFCRNZ0EBQ2M3=are-ios-universal-links-and-android-app-links-supported-in-meta-ads h_01JJVVX9NCSTVQKG2ENTGDRDK9=are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content 01H7YJVNMVBRVTT9HH7KM8P33B=aem-attribution-is-not-working h_01HD1JTW2ETG739TWQVTKPCM2R=can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads h_01JTG2474VHWAD8EK8ASPWZY0W=conversion-events-are-not-sent-to-meta-ads h_01K8B4AKSHSMP18MM0GAAZEQMF=can-i-use-get h_01K8B4AKSH7E8TBEG024NAV1A5=nota facebook-ads-cost-faq=preguntas-frecuentes-sobre-el-costo-de-meta-ads h_01HD1JTW2EEVD1PDPFW15K45CE=preguntas-frecuentes-sobre-el-costo-de-meta-ads h_01HD1JTW2EE0WQ90J431Z8NQ8Q=getting-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2ESVMMPK32W34PA54T=facebook-cost-example h_01HD1JTW2EVFXAET26WK2KSHTV=i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2EJQHKVJF4XHWGVASJ=can-i-stop-cost-data-sync h_01HD1JTW2EYJTA2TRY7EE75KXA=cost-data-was-fine-for-a-few-months-but-it-stopped-displaying h_01HD1JTW2EYXZW2QCMQH5CRFSK=i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer h_01HD1JTW2EYE2ZDNVRT5BCRXZJ=can-i-get-raw-data-on-clicks-and-impressions-from-facebook h_01HD1JTW2EG11RRBYHJ5BMJM5M=are-there-limitations-of-facebook-cost-data-by-geo h_01HD1JTW2E3RMV2TMPNZZ86HG5=what-are-the-limitations-of-facebook-cost-data-in-master-api h_01HD1JTW2EKVSAQ3706NC8JV9M=the-total-cost-doesnt-match h_01HD1JTW2EMJQJHBBB9SRJ6MZN=why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical h_01HD1JTW2E2S79FC9VAHA12X93=why-doesnt-cost-data-include-data-from-all-campaigns h_01HD1JTW2ET6Y2EHG29AQS09NA=is-facebook-cost-data-displayed-for-retargeting-campaigns h_01HD1JTW2EXTS1GDZHN8PAMV8C=why-does-the-facebook-cost-configuration-window-close-before-login h_01HD1JTW2FC0NJK00HZ76SFH30=why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store how-to-connect-cost-data-of%C2%A0a-new-facebook-ad-account-while-my-old-account-is-linked=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked h_01HD1JTW2F401DA2NHBSPTKATB=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked facebook-ads-sdk-faq=preguntas-frecuentes-sobre-el-sdk-de-facebook h_01HD1JTW2FPRCVGBF7CG7ZMKXF=preguntas-frecuentes-sobre-el-sdk-de-facebook h_01HD1JTW2F03XQSEVTFBW8JCX3=who-needs-facebooks-sdk h_01HD1JTW2FB09HM2CC83GMT901=nota-1 h_01HD1JTW2FNNHPZQARZNCCP7ER=avoiding-duplicates-with-facebook-sdk facebook-ads-attribution-faq=preguntas-frecuentes-sobre-la-atribuci%C3%B3n-de-meta-ads h_01HD1JTW2F2JV2BMDS40HFG6K0=preguntas-frecuentes-sobre-la-atribuci%C3%B3n-de-meta-ads h_01HD1JTW2FK1ZTPTA8B8A4N64Z=attributing-agencies-with-facebook h_01HD1JTW2F63AT1NGBY96Y6CCE=attribution-for-facebook-for-outofstore-android-apps h_01HD1JTW2FMKYDHNSM7G182EY0=nota-2 h_01HD1JTW2F8JT69CSN04GCZ91V=what-is-facebook-android-and-ios-crossattribution h_01HD1JTW2F5PY7A8T5NMHBZ87B=ejemplo h_01HD1JTW2FX3QWC9BKWQ65E5B8=what-are-facebook-ads-channels" />

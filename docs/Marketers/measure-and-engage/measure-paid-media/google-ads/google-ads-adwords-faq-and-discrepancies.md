---
title: 'Google Ads (AdWords): preguntas frecuentes y discrepancias'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T10:06:31Z'
  edited_at: '2026-08-12T12:19:01Z'
  id: 4417303339921
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/4417303339921
---
> En resumen: Soluciona problemas y discrepancias comunes relacionados con Google Ads.

<div id="google-ads-faq" />

## Preguntas frecuentes sobre Google Ads

<div id="why-am-i-not-seeing-clicks-from-google-ads" />

<Accordion title="¿Por qué no veo clics de Google Ads?">

Los datos agregados de clics e impresiones de Google Ads se recopilan una vez que hayas <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">autenticado la recopilación de costos, clics e impresiones</Anchor> en la pestaña **Costo**.

Los datos de clics e impresiones de Google Ads se pusieron a disposición durante agosto de 2018, primero para aplicaciones Android y, más tarde, para aplicaciones iOS. Por lo tanto, al analizar los datos de clics de 2018 o anteriores, algunos datos de clics de Google Ads pueden no estar o estar incompletos.

</Accordion>

<div id="why-am-i-not-seeing-first_open-conversions-on-google-ads" />

<Accordion title="¿Por qué no veo conversiones first_open en Google Ads?">

Si no estás viendo conversiones first\_open en Google Ads tal como se muestra en la captura de pantalla a continuación:

<Image align="center" alt="AW_13.png" src="https://files.readme.io/082f79266fced9fc012cdb373321a836129205992adbe29f7509321516e8f5ab-33743114088849.png" />

Significa que debes importar conversiones en Google Ads. Sigue las instrucciones sobre <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">cómo importar conversiones</Anchor>.

</Accordion>

<div id="why-don-t-i-see-installs-from-google-ads" />

<Accordion title="¿Por qué no puedo ver eventos in-app en Google Ads?">

Sigue esta lista de verificación para solucionar problemas de instalaciones faltantes:

<div id="quick-fix" />

#### Solución rápida

1. **Activa Google Ads en AppsFlyer**  
   En AppsFlyer, en la barra lateral, abre **Collaborate > Active integrations**, busca **Google Ads** y confirma que la integración esté activa.
2. **Importa la conversión** `first_open` **en Google Ads**  
   En Google Ads, ve a la página <Anchor target="_blank" href="https://ads.google.com/aw/conversions">Resumen de conversiones</Anchor> y asegúrate de que el evento de conversión `first_open` esté importado. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">Importa las conversiones de tu aplicación</Anchor>.

<div id="still-not-working" />

#### ¿Sigue sin funcionar?

1. **Comprueba qué cuenta de Google Ads importa las conversiones**  
   Determina si la **cuenta MCC o subcuenta de Google Ads** es la responsable de importar las conversiones:

   * **Si usas una MCC (cuenta de administrador):** La MCC debe importar la conversión `first_open` en nombre de todas las subcuentas enlazadas.
   * **Si usas una subcuenta:**
     * La MCC debe **compartir el ID de enlace** con la subcuenta.
     * La subcuenta también debe **importar la conversión** `first_open` directamente.

   Para obtener más información sobre las cuentas MCC de Google Ads, consulta: <Anchor target="_blank" href="/marketers/es/docs/recording-multiple-agency-mcc-google-ads-accounts#mcc">MCC</Anchor>.
2. **Comprueba si se han eliminado conversiones de** `first_open`  
   En la página <Anchor target="_blank" href="https://ads.google.com/aw/conversions">Resumen de conversiones</Anchor>, comprueba si se eliminó el evento de conversión `first_open`. Si se ha eliminado, ponte en contacto con el **soporte de Google** para obtener ayuda.
3. **Confirma el ID de enlace**  
   Asegúrate de que el ID de enlace de AppsFlyer coincida con el ID de enlace de Google Ads.

</Accordion>

<div id="why-dont-i-see-inapp-events-in-the-google-ads-dashboard" />

<Accordion title="Los eventos pueden tardar hasta 6 horas en aparecer en el dashboard de Google Ads.">

Usa esta lista de verificación para asegurarte de que tus eventos in-app estén configurados correctamente y sincronizados entre AppsFlyer y Google Ads.

<div id="quick-fix-checklist" />

#### Lista de verificación de solución rápida

Sigue estos pasos para resolver rápidamente los problemas más habituales:

1. **Verifica los postbacks de eventos en AppsFlyer** (para ver las instrucciones paso a paso, consulta <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">Configura Google Ads en AppsFlyer.</Anchor>)
   1. <span class="af-ol-a"></span>Ve a la **pestaña de integración de Google Ads** en AppsFlyer.
   2. Asegúrate de que los postbacks estén configurados correctamente para cada evento in-app que quieras medir.
   3. En **For users from**, selecciona *All media sources, including organic,* para asegurarte de que Google Ads reciba los datos de eventos.
   4. (Opcional) Después de la configuración inicial, ajusta esta selección para eventos concretos si es necesario.
2. **Activa un evento in-app de prueba**
   1. <span class="af-ol-a"></span>Abre tu aplicación.
   2. En aplicaciones iOS, asegúrate de que la recopilación de IDFA esté habilitada permitiendo que la aplicación haga track.
   3. Realiza manualmente los eventos in-app asignados (por ejemplo, una compra o un registro).
3. **Importar eventos en Google Ads**
   1. <span class="af-ol-a"></span>En Google Ads, haz clic en **Tools Conversions**.
   2. Comprueba el **Conversion Action Summary**.
   3. Importa los eventos in-app relevantes. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">Importa las conversiones de tu aplicación</Anchor>.

      <div id="note" />

      > 📘 **Nota:**
      >
      > Las conversiones pueden tardar hasta 6 horas en aparecer después de realizar el evento.


<div id="still-not-working-1" />

#### ¿Sigue sin funcionar?

Si has modificado el identificador del evento de partner en Google Ads (por ejemplo, si aparece etiquetado como `CUSTOM`) y has cambiado el nombre del evento correspondiente en AppsFlyer, tendrás que volver a importar los eventos en Google Ads.

</Accordion>

<div id="can-i-stop-google-cost-sync" />

<Accordion title="¿Puedo detener la sincronización de costos con Google?">

Para detener la sincronización de costos de Google debes hacer lo siguiente:

1. Ve a los <Anchor target="_blank" href="https://myaccount.google.com/permissions">permisos de tu cuenta de Google</Anchor>.
2. Haz clic en “Eliminar” junto a “Costos de Google para AppsFlyer”.  
   <Image align="center" alt="remove_appsflyer_cost.png" src="https://files.readme.io/56840e708c98875c8db176c642dd324150a76aef9697fcc2756f524b2a6c0a16-33743128661137.png" />

</Accordion>

<div id="do-i-need-to-create-and-then-import-session_start" />

<Accordion title="¿Debo crear y luego importar el evento session_start?">

Depende del tipo de campaña que estés ejecutando. Si estás ejecutando una campaña de re-engagement, se recomienda crear e importar el evento `session_start` para medir las instancias de engagement.

En el caso de una campaña de adquisición de usuarios, no es necesario hacerlo.

</Accordion>

<div id="can-i-send-uninstall-information-to-google-ads" />

<Accordion title="¿Puedo enviar información de desinstalación a Google Ads?">

Sí.  
**Para comenzar a enviar eventos de desinstalación a Google:**

1. Asigna el evento af\_uninstall como un evento personalizado en la ventana de configuración de Google Ads.
2. Importa esa conversión en Google.
3. Google reconoce los eventos si se reciben dentro de la ventana de atribución de Google (comienza con el engagement del anuncio y tiene una duración de 30 a 90 días). Los eventos recibidos por Google una vez finalizada esa ventana no se registran en Google.

</Accordion>

<div id="what-google-ads-data-does-appsflyer-display" />

<Accordion title="¿Qué datos de Google Ads muestra AppsFlyer?">

Puedes ver datos en los siguientes niveles: campaña, canal, conjunto de anuncios y geolocalización.

</Accordion>

<div id="do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data" />

<Accordion title="¿Debo configurar algo para crear listas de audiencias en Google Ads en función de los datos de AppsFlyer?">

N.º En la API de Google, esta información ya está configurada y se basa en tu configuración de eventos in-app.

</Accordion>

<div id="im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard" />

<Accordion title="¿Ves esta pantalla en Google Ads después de asignar tus eventos in-app preferidos en el dashboard de AppsFlyer ( Paso 3 de la configuración )?">

Es muy probable que aún no haya importado los eventos. Para obtener información detallada sobre cómo importar eventos, haz clic <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aquí</Anchor>.

</Accordion>

<div id="what-do-i-do-if-there-are-multiple-accounts" />

<Accordion title="¿Qué hago si hay varias cuentas?">

No hay ningún problema con usar varias cuentas en Google Ads con AppsFlyer. AppsFlyer funciona con un ID de enlace único. Por lo tanto, solo se debe generar un ID de enlace en Google Ads, que puede compartirse entre varias cuentas. Para más información, haz clic <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3030657">aquí</Anchor>.

</Accordion>

<div id="what-happens-with-link-ids-created-at-mcc-level-vs-account-level" />

<Accordion title="¿Qué ocurre con los IDs de enlace creados a nivel de MCC, en comparación con los creados a nivel de cuenta?">

AppsFlyer admite ID de enlace tanto a nivel de MCC como a nivel de cuenta. Se recomienda trabajar en estrecha colaboración con un representante de Google Ads para garantizar que la cuenta esté estructurada correctamente. Para más información, haz clic <Anchor target="_blank" href="/marketers/es/docs/recording-multiple-agency-mcc-google-ads-accounts">aquí</Anchor>.

</Accordion>

<div id="what-is-parallel-tracking" />

<Accordion title="¿Qué es el rastreo paralelo?">

El rastreo paralelo de Google Ads permite que tu landing page se cargue más rápido, lo que reduce el problema de las visitas perdidas. Esto hace que aumenten las conversiones y mejore el rendimiento de los anuncios. Con el rastreo paralelo, los usuarios se envían a la URL final, directamente desde el anuncio, antes de enviarlos a los enlaces de atribución, mientras que la medición de clics tiene lugar en segundo plano.

Para obtener una explicación detallada del rastreo paralelo, haz clic <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">aquí</Anchor>.

<div id="what-is-needed" />

#### ¿Qué se necesita?

Para que el seguimiento paralelo funcione según lo previsto, la URL final debe coincidir con lo que hay en la URL de la campaña e incluirse en el <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en">parámetro `{lpurl}` ValueTrack de Google.</Anchor>

Puedes hacerlo de las siguientes maneras:

* Mediante un enlace de atribución de plataforma única (no recomendado):
  * Se debe usar el parámetro af\_r en la URL.
* Mediante un <Anchor target="_blank" href="/marketers/es/docs/understand-onelink-short-vs-long-urls">enlace largo de OneLink</Anchor> (recomendado):
  * Incluye los siguientes parámetros de URL en la URL de la campaña:
    * af\_android\_url
    * af\_ios\_url
    * af\_web\_dp
  * No se debe usar af\_dp.
  * Agrega tu URL final (URL de destino) al parámetro ValueTrack de Google. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en#urlinsertion&zippy=%2Ctracking-template-only">Saber más</Anchor>

Por ejemplo,

```
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}  
&af_android_url={lpurl}&af_web_dp={lpurl}
```

Nota: Para ver todos los parámetros compatibles, consulta este [artículo](https://support.google.com/google-ads/answer/6305348?hl=en&sjid=12409212435602417786-AP#zippy=%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cfinal-url-tracking-template-or-custom-parameter).

Haz clic aquí para ver cómo configurar las campañas web de anuncios de Google con tracking paralelo.

</Accordion>

<div id="how-do-you-configure-a-campaign-with-android-or-ios-configuration" />

<Accordion title="¿Cómo se configura una campaña con la configuración de Android o iOS?">

<div id="important" />

> 🚧 **¡Importante!**
>
> AppsFlyer admite todas las campañas de aplicaciones habilitadas por Google Ads.
>
> Google es una SRN (Self Reporting Network). Para más información sobre el flujo de atribución para estas redes, haz clic <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">aquí</Anchor>.
>
> AppsFlyer puede presentar cualquier información de campaña proporcionada por Google. Google determina el tipo de campaña (búsqueda, video, visualización y re-engagement) y la información asociada. Se recomienda configurar campañas de aplicaciones. Para recibir orientación sobre otros tipos de campañas, ponte en contacto con un representante de Google. Para más detalles sobre estas campañas, haz clic <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">aquí</Anchor>.

<div id="android-configuration-for-google-ads" />

<Accordion title="Configuración de Android para Google Ads">

Para permitir la atribución en Android, asegúrate de que tu aplicación admita la recopilación del GAID (ID de Publicidad de Google) y de que se transfiera a AppsFlyer a través de nuestro SDK.

<div id="creating-conversion-recording-installs" />

#### Cómo generar el registro de conversiones (instalaciones)

Para obtener información detallada sobre cómo generar el registro de conversiones, haz clic <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">aquí</Anchor>.

<span id="inapp_events"></span>Configuración de Android para Google Ads: Envío de eventos in-app

Si deseas continuar midiendo el éxito de tus campañas de instalación de aplicaciones móviles en Google, puedes enviar eventos in-app a tu cuenta de Google Ads desde tu cuenta de AppsFlyer.

<div id="create-a-conversion-in-app-events" />

#### Cómo crear una conversión (eventos in-app)

Para más información sobre cómo medir las conversiones de tus aplicaciones, haz clic <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aquí</Anchor>.

</Accordion>

<div id="ios-configuration-for-google-ads" />

<Accordion title="Configuración de iOS para Google Ads">

<div id="google-ads---ios-configuration-app-campaigns" />

#### Configuración de iOS para Google Ads: campañas de aplicaciones

Las campañas de aplicaciones te permiten promocionar tu aplicación de iOS a través de Google Search, YouTube y la visualización en un solo lugar de configuración.

Por lo general, Google Ads en sí no puede autoatribuirse las instalaciones de iOS de las campañas de búsqueda, ya que los clics provienen de fuentes de la web móvil, lo que impide que Google extraiga el IDFA de los dispositivos y haga coincidir el ID.

En cambio, **Google Ads sí puede atribuir la búsqueda de iOS en las campañas de aplicaciones** en el caso de los anuncios que se presentan en la **aplicación Google Search**.

<div id="creating-conversion-recording-installs-1" />

#### Cómo generar el registro de conversiones (instalaciones)

Para obtener información detallada sobre cómo generar el registro de conversiones, haz clic <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">aquí</Anchor>.

<div id="google-ads---ios-configuration---sending-in-app-events" />

#### Configuración de iOS para Google Ads: envío de eventos in-app

Si deseas continuar midiendo el éxito de tus campañas de instalación de aplicaciones móviles en Google, puedes enviar eventos in-app a tu cuenta de Google Ads desde tu cuenta de AppsFlyer.

<div id="creating-a-conversion-in-app-events" />

#### Cómo crear una conversión (eventos in-app)

Para más información sobre cómo medir las conversiones de tus aplicaciones, haz clic <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aquí</Anchor>.

</Accordion>

</Accordion>

<div id="for-how-long-do-you-keep-google-ads--userlevel-data" />

<Accordion title="¿Cuánto tiempo conservan los datos de Google Ads de nivel de usuario?">

Google Ads exige que los proveedores de atribución eliminen sus datos a nivel de usuario 6 meses después de la instalación. Esto significa que los eventos efectuados por estos usuarios 6 meses después de que hayan instalado la aplicación se cuentan como orgánicos.

Los datos agregados anteriores permanecen iguales.

Esto es pertinente para todos los canales de Google Ads.

</Accordion>

<div id="google-ads-discrepancies" />

## Discrepancias de Google Ads

A veces hay discrepancias entre el dashboard de Google Ads y el de AppsFlyer.

Si bien trabajamos en estrecha colaboración con Google para minimizar estas discrepancias, es importante que los anunciantes observen las siguientes cuestiones:

<div id="both-ios-and-android" />

#### Tanto en iOS como en Android

| **Causa** | **Anuncios de Google** | **AppsFlyer** |
| --- | --- | --- |
| **Conversiones modeladas y conversiones de ICM** | Google Ads muestra instalaciones modeladas generadas por el modelado interno de Google y no muestra instalaciones modeladas basadas en ICM. | AppsFlyer muestra instalaciones modeladas generadas por Google ICM (reclamaciones probabilísticas) y no muestra las instalaciones modeladas internamente por Google. |
| **Instalaciones asistidas (también conocidas como atribución multi toque)** | Por tratarse de una SRN, Google Ads atribuye todas las instalaciones después de las instancias de engagement con Google Ads, dentro de su ventana de atribuciones. | AppsFlyer atribuye el último clic en la trayectoria de un usuario y trata los engagements anteriores como <Anchor target="_blank" href="/marketers/es/docs/measure-assisted-installs">asistencias</Anchor>. |
| **Tiempo de registro de instalación** | Google Ads atribuye la conversión al tiempo del clic. | AppsFlyer atribuye la conversión al tiempo de inicio (cuando se abre la aplicación). |
| **Zonas horarias** | Varía según la ubicación. | Varía según la ubicación. |
| **Ventana de atribución** | 30 días | La integración de Google está configurada para 30 días de forma predeterminada (se puede modificar). |
| **Conversiones por impresiones** | Las conversiones VT solo se muestran en la columna **Todas las conversiones** y no en la columna **Conversiones**, a menos que se configure lo contrario en Google Ads. | AppsFlyer muestra el número total de instalaciones, instalaciones por clics e instalaciones VT. |
| **Reinstalaciones** | Google Ads muestra las reinstalaciones como una conversión session\_start. | AppsFlyer atribuye y muestra las reinstalaciones (también conocidas como reatribuciones) como parte de sus datos de retargeting. |
| **Eventos in-app** | Google Ads atribuye el evento in-app al tiempo del clic. | En el dashboard de AppsFlyer, los eventos in-app se atribuyen según el tiempo de instalación. En los reportes de raw data, AppsFlyer atribuye los eventos in-app según el tiempo del evento. |
| **Reglas de validación** | Google recibe toda la información de AppsFlyer independientemente de las reglas de validación. | AppsFlyer podría deducir algunas instalaciones en base a sus reglas de validación. |
| **Costo: canales de campaña de Google Ads** | Google informa el costo para todos los canales de una campaña determinada: YouTube, visualización y búsqueda. | AppsFlyer obtiene datos de costos de Google para todos los canales de una campaña, pero solo atribuye conversiones de YouTube y canales de visualización en AC para iOS. Como resultado, el costo por instalación (CPI) general en AppsFlyer es mayor. |
| **Instalaciones de SKAN** | Desde la API V10+ de Google Ads, el dashboard de Google Ads no diferencia entre las instalaciones con did\_win=TRUE y did\_win=NULL. Solo se diferencian en el raw data. | Desde la API V10+ de Google Ads, AppsFlyer solo muestra las instalaciones de postbacks con did\_win=TRUE. Como resultado, el número de instalaciones en AppsFlyer puede ser menor. |
| **Eventos de first\_open** | Google Ads obtiene eventos de Firebase donde DMA se implementa correctamente y posteriormente se reclaman los eventos consentidos de DMA. | Google Ads obtiene los mismos eventos también de AppsFlyer donde DMA se implementa incorrectamente, lo que provoca que todos los eventos se reporten como no consentidos por DMA y Google no los reclame.<ul><li>Para verificar si DMA está implementado correctamente <Anchor target="_blank" href="/marketers/es/docs/raw-data-export-page#download-report">descarga el reporte de raw data</Anchor> y concéntrate en los campos especificados en <Anchor target="_blank" href="/marketers/es/docs/bulletin-dma-support-in-raw-data-reports">este boletín</Anchor>.</li><li>Consulta el [Dev Hub](https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance) para aprender cómo implementar DMA en el SDK</li></ul> |
| **Eventos de retargeting** | Google Ads puede reclamar un re-engagement con `ad_type=ClickToDownload` en la respuesta. | AppsFlyer cuenta `ad_type=ClickToDownload` como un evento de conversión de UA en lugar de como un re-engagement. Como resultado, el número de re-engagement en AppsFlyer puede ser menor. |

<div id="notes" />

> 📘 **Notas**
>
> * Mientras que Google Ads muestra todas las instalaciones de una campaña de retargeting en el mismo lugar, en el dashboard general de AppsFlyer, la vista de UA muestra las nuevas instalaciones, la vista de retargeting muestra las reatribuciones y la vista unificada muestra ambas.
> * Cuando se comparan los datos del dashboard de Google Ads con los de AppsFlyer, hay que asegurarse de que los datos del dashboard de Google Ads sean datos importados de análisis de terceros (AppsFlyer). Los datos importados de Firebase o Google Play se estructuran de manera diferente y no son del todo equiparables a los datos de AppsFlyer. Para saber cómo importar datos de AppsFlyer al dashboard de Google Ads, haz clic <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aquí</Anchor>.
> * Para comparar eventos de instalación (first\_open en Google Ads), asegúrate de explorar en profundidad hasta llegar a los eventos de instalación del reporte de conversiones de Google Ads. Es posible que Google Ads muestre todas las conversiones (podrían ser instalaciones, compras, suscripciones). Por eso es importante seleccionar solo los eventos de instalación de entre todos los eventos de conversión.

<div id="see-also" />

> 📄 **Consulta también**
>
> * Para más información sobre consideraciones relacionadas con iOS 14, consulta <Anchor target="_blank" href="/marketers/es/docs/get-skan-postback-data-from-google-ads">Interoperabilidad de Google Ads SKAdNetwork con AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-faq=preguntas-frecuentes-sobre-google-ads h_01HA1SM7D91QPG17WH752FBAFT=preguntas-frecuentes-sobre-google-ads h_01HA1SM7D9JWBEPNE0E8FE665E=why-am-i-not-seeing-clicks-from-google-ads h_01HA1SM7DAW984PPRGHXA5BYSX=why-am-i-not-seeing-first_open-conversions-on-google-ads why-don%E2%80%99t-i-see-installs-from-google-ads=why-don-t-i-see-installs-from-google-ads h_01K5DZBDMS0D2S5XYDC22WQ19H=why-don-t-i-see-installs-from-google-ads quick-fix=soluci%C3%B3n-r%C3%A1pida h_01K5DZBDMSBDKAFHVVPYD6YKRK=soluci%C3%B3n-r%C3%A1pida still-not-working=sigue-sin-funcionar h_01K5DZBDMSVTE6M2J235ST85DE=sigue-sin-funcionar h_01K7NT8FVC3K3861WN9VKRZ2HB=why-dont-i-see-inapp-events-in-the-google-ads-dashboard quick-fix-checklist=lista-de-verificaci%C3%B3n-de-soluci%C3%B3n-r%C3%A1pida h_01K7NT8FVC1T557GPG7ZCYX33J=lista-de-verificaci%C3%B3n-de-soluci%C3%B3n-r%C3%A1pida h_01K7PAH7VDS7NGW6R6HERGXK9H=nota still-not-working::77f3165b=sigue-sin-funcionar-1 h_01K7NT8FVCD4DNFKP3DS75ZKR0=sigue-sin-funcionar-1 h_01HA1SM7DACQDVGWGKV5MZ63D6=can-i-stop-google-cost-sync h_01HA1SM7DA415FQP3MFC09AE3Y=do-i-need-to-create-and-then-import-session_start h_01HA1SM7DAEKGVPDTX77RJ9Y37=can-i-send-uninstall-information-to-google-ads h_01HA1SM7DAKKVZ82WF6RVEDHE9=what-google-ads-data-does-appsflyer-display h_01HA1SM7DANYQ0DAY54CH4HPV4=do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data h_01HA1SM7DA3XF8NBGYGZ0XTB69=im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard h_01HA1SM7DAY7JNTFSG86A1QGKC=what-do-i-do-if-there-are-multiple-accounts h_01HA1SM7DAYSVMENT91T2BE26Z=what-happens-with-link-ids-created-at-mcc-level-vs-account-level h_01HA1SM7DAK186BRZN970PKPRM=what-is-parallel-tracking additional-information=qu%C3%A9-se-necesita h_01HA1SM7DAMNG8X22VNWMKBJ8R=qu%C3%A9-se-necesita h_01HA1SM7DBNAS6DP8G9D8KFHPW=how-do-you-configure-a-campaign-with-android-or-ios-configuration h_01HA1SM7DB16T3RGBVGT5Z9REW=importante h_01HA1SM7DBC38CY8AN3EPMMJFW=android-configuration-for-google-ads creating-conversion-recording-installs=c%C3%B3mo-generar-el-registro-de-conversiones-instalaciones h_01HA1SM7DBF9KDRNEV25KJHGHN=c%C3%B3mo-generar-el-registro-de-conversiones-instalaciones create-a-conversion-inapp-events=c%C3%B3mo-crear-una-conversi%C3%B3n-eventos-in-app h_01HA1SM7DBDQVNDQ5GG7X2PJ8K=c%C3%B3mo-crear-una-conversi%C3%B3n-eventos-in-app h_01HA1SM7DBKKQ9R8MQMQT9GRXV=ios-configuration-for-google-ads google-ads-ios-configuration-app-campaigns=configuraci%C3%B3n-de-ios-para-google-ads-campa%C3%B1as-de-aplicaciones h_01HA1SM7DBNSDFCJA5BP59MMQ2=configuraci%C3%B3n-de-ios-para-google-ads-campa%C3%B1as-de-aplicaciones creating-conversion-recording-installs::6a56eb4b=c%C3%B3mo-generar-el-registro-de-conversiones-instalaciones-1 h_01HA1SM7DBXCT0NS4W50D4ZGEK=c%C3%B3mo-generar-el-registro-de-conversiones-instalaciones-1 google-ads-ios-configuration-sending-inapp-events=configuraci%C3%B3n-de-ios-para-google-ads-env%C3%ADo-de-eventos-in-app h_01HA1SM7DBEV9CJTAB5YHRJHYK=configuraci%C3%B3n-de-ios-para-google-ads-env%C3%ADo-de-eventos-in-app creating-a-conversion-inapp-events=c%C3%B3mo-crear-una-conversi%C3%B3n-eventos-in-app-1 h_01HA1SM7DBCQYSJ3R67F0856QK=c%C3%B3mo-crear-una-conversi%C3%B3n-eventos-in-app-1 for-how-long-do-you-keep-google-ads%E2%80%99-userlevel-data=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBFAAV7C4ENA34B7JP=for-how-long-do-you-keep-google-ads--userlevel-data google-ads-discrepancies=discrepancias-de-google-ads h_01HA1SM7DBA7KK1DXFCE2G0QTP=discrepancias-de-google-ads both-ios-and-android=tanto-en-ios-como-en-android h_01HA1SM7DB18BTDKK5BK4949HX=tanto-en-ios-como-en-android h_01HA1SM7DBSTAREA36YWRRRG82=notas h_01HDP2XBSEJVQ5G0MD0V5R05CM=consulta-tambi%C3%A9n" />

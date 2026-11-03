---
title: Información sobre las restricciones de los identificadores de raw data
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2026-11-03T01:59:24Z'
  id: 360006868017
  locale: es
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/es/articles/360006868017
---
> **Resumen:** Algunos socios exigen que AppsFlyer restrinja ciertos campos en informes específicos de datos en bruto. En otros casos, los socios pueden solicitar la restricción de la fuente de medios al compartir postbacks con plataformas de terceros. Este artículo describe estas restricciones y sus implicaciones.

## Restricción de datos en bruto

AppsFlyer restringe el acceso a ciertos campos del Reporte de raw data según la configuración de <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">AAP (Aggregated Advanced Privacy)</Anchor> del anunciante o las políticas de intercambio de datos de las ad network que proporcionan los datos. Estas restricciones varían dependiendo del tipo de informe y el motivo de la restricción.

### Restricciones de fuente de medios

La siguiente tabla enumera las restricciones por fuente de medios para conversiones, clics e impresiones.

> 📘 **Nota:**
>
> Los datos de atribución y análisis agregados están disponibles sin limitaciones. No obstante, todos los postbacks y los informes a nivel de dispositivo están sujetos a las limitaciones que se describen a continuación.
>
> <Anchor target="_blank" href="/marketers/es/docs/discrepancies-between-appsflyer-and-third-party-platforms#restricciones-de-postbacks-en-plataformas-de-terceros">Restricciones de postback en plataformas de terceros</Anchor>:
>
> * Las restricciones descritas en la tabla a continuación se aplican a los eventos incluidos en los postbacks enviados a plataformas de terceros, como las de análisis y marketing.
> * Se pueden aplicar otras restricciones de postback para otros eventos.

| Fuente de medios | Restricción del tipo de atribución |
| --- | --- |
| <span id="amazon-ads"></span>Anuncios de Amazon | Los datos en bruto de Amazon Ads están restringidos en la plataforma AppsFlyer. Como resultado, la fuente de medios se reporta como «restringida» y los detalles de la campaña son nulos.<br /><br />Como ocurre con cualquier SRN (Self-Reporting Network), los clics y las impresiones de Amazon no se incluyen en los Reportes de raw data. |
| <span id="discord"></span>Discord | Los raw data de Discord están restringidos en la plataforma AppsFlyer.<br /><br />Se aplican las siguientes restricciones a la atribución view-through y click-through:<ul><li>original\_url: restringido</li><li>click\_id: restringido</li></ul>Los clics y las impresiones de Discord no se incluyen en los reportes de raw data. |
| <span id="meta-ads"></span>Anuncios de Meta | Se aplican las siguientes restricciones a los raw data de Meta Ads:<ul><li>Por defecto, Meta Ads no permite la distribución de datos a nivel de dispositivo con información de atribución sin restricciones. Sin embargo, si aceptas los Términos de Meta Advanced Mobile Measurement (AMM), puedes acceder a los datos de atribución a nivel de dispositivo de Meta Ads sin restricciones. Consulta <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">Habilitar los datos a nivel de dispositivo de Meta Ads</Anchor>.</li><li>Los datos de la solución de Deep Linking de AEM (iOS), así como los datos de Google Play Install Referrer y Meta Install Referrer (Android), están disponibles en los reportes a nivel de dispositivo.</li><li>Los datos de Google Play Install Referrer y Meta Install Referrer solo pueden aparecer en los reportes de instalación.</li><li>Los datos de la solución de Deep Linking de AEM (iOS) solo pueden aparecer en los reportes de re-engagement.</li></ul>Los clics y las impresiones de Meta Ads no se incluyen en los reportes de raw data. |
| <span id="pinterest"></span>Pinterest | Pinterest gestiona la lógica de restricción de raw data para cada evento y la comunica a AppsFlyer a través de la integración. Esta lógica puede aplicarse tanto a los datos de atribución click-through como a los de atribución view-through.<br /><br />Cuando un evento tiene restricciones de raw data, no puedes acceder a sus datos de atribución click-through y view-through, incluidos todos los campos de atribución, como fuente de medios, campaña, adset, anuncio, tipo de toque, tipo de engagement y hora del toque.<br /><br />En todos los casos, los reportes de raw data no incluyen los clics ni las impresiones de Pinterest. |
| <span id="reddit"></span>Reddit | Los clics e impresiones de Reddit no se incluyen en los informes de datos sin procesar.<br /><br />**Recordatorio:** Los datos recibidos sobre una campaña de Reddit están sujetos a las <Anchor target="_blank" href="https://business.reddithelp.com/s/article/Reddit-Business-Tool-Terms">Reddit Business Tool Terms</Anchor> e incluyen, entre otras restricciones, la prohibición de usar datos de Reddit para crear perfiles de cualquier usuario. |
| <span id="samsung-dsp"></span>Samsung DSP | A partir del 17 de octubre de 2023:<br /><br />La atribución view-through y click-through de Samsung es limitada. Se incluyen los siguientes datos en las herramientas de entrega de raw data:<ul><li>Fuente de medios (samsungdsp\_int)</li><li>Tipo de toque atribuido (impresión/clic)</li><li>La hora del toque atribuido está disponible</li><li>Los detalles de la campaña están disponibles</li></ul>Los clics y las impresiones de Samsung no se incluyen en los reportes de raw data.<br /><br />A partir del 30 de agosto de 2025:<br /><br />La atribución view-through y click-through de Samsung EMEA es limitada para los engagement recibidos con `af_data_restriction=attribution` en la URL. Los siguientes se incluyen en las herramientas de entrega de raw data:<ul><li>Fuente de medios: se reporta como restringida</li><li>Tipo de toque atribuido (impresión/clic)</li><li>La fecha y hora del toque atribuido están disponibles</li><li>Los detalles de la campaña están disponibles</li></ul>Los clics y las impresiones de Samsung no se incluyen en los reportes de raw data. |
| <span id="snapchat"></span>Snapchat | Se aplican las siguientes restricciones al raw data de Snapchat:<ul><li>Desde el 1 de marzo de 2023, las desinstalaciones de Snapchat no se incluyen en los reportes de raw data.</li><li>Los datos a nivel de dispositivo de la atribución view-through son limitados en algunos casos. La lógica de las restricciones de raw data se gestiona del lado de Snapchat, por evento, y se comunica a AppsFlyer mediante la integración.</li><li>Cuando el evento tiene restricciones de raw data, lo siguiente **no** está restringido en las herramientas de entrega de raw data:</li></ul><ul><li>Fuente de medios (snapchat\_int)</li><li>Channel</li><li>Tipo de toque atribuido (impresión)</li><li>Hora del toque atribuido (se reporta solo como fecha, "dd/mm/yyyy")</li><li>Nombre e ID de la campaña (a partir del 15 de diciembre de 2025)</li><li>Nombre e ID del conjunto de anuncios (a partir del 15 de diciembre de 2025)</li></ul><ul><li>Las restricciones anteriores no se aplican a las visualizaciones comprometidas.</li></ul>Los clics y las impresiones de Snapchat no se incluyen en los reportes de raw data. |
| <span id="tiktok-for-business"></span>TikTok for Business | Hasta el 19 de mayo de 2026, se aplicaban las siguientes restricciones a la atribución view-through:<ul><li>La fuente de medios se reportaba como `tiktokglobal_int`</li><li>El canal se reportaba como TikTok / Pangle</li><li>El tipo de toque atribuido se reportaba como impresión</li><li>La hora del toque atribuido se reportaba solo como fecha ("dd/mm/yyyy")</li><li>La información de la campaña, el conjunto de anuncios y el anuncio se reportaba como "restringida"</li></ul>A partir del 19 de mayo de 2026, se actualizaron las siguientes herramientas de raw data: Pull API, Data Locker y la página de Raw Data Export.<br /><br />A partir del 25 de junio de 2026, se actualizaron las siguientes herramientas de raw data: Push API y la API Get conversion data (GCD).<br /><br />Los cambios son:<ul><li>Solo está restringido (vacío) el campo `original_url`</li><li>Todos los demás campos de atribución son totalmente compatibles</li></ul>Las restricciones anteriores no se aplican a las visualizaciones comprometidas.<br /><br />Los reportes de raw data de clics e impresiones a través de Data Locker de `tiktokglobal_int` están restringidos. |
| <span id="uber"></span>Uber | Las siguientes restricciones se aplican a la atribución view-through y click-through:<ul><li>Fuente de medios (uber\_int): disponible</li><li>Detalles de la campaña: disponibles</li></ul>Los clics e impresiones de Uber no se incluyen en los reportes de raw data. |
| <span id="x-ads-formerly-twitter"></span>X Ads (antes Twitter) | En algunos casos, según las elecciones de los usuarios en X Ads, el raw data puede estar restringido en la plataforma AppsFlyer.<br /><br />**Hasta el 15 de julio de 2025:** Los eventos atribuidos de X Ads no aparecían en absoluto en los reportes de raw data.<br /><br />**A partir del 15 de julio de 2025:** Los eventos atribuidos se incluyen en los reportes de raw data, con las siguientes restricciones:<ul><li>Fuente de medios (twitter): disponible</li><li>Detalles de la campaña: se reportan como *restringidos*</li><li>Canal (Twitter): disponible</li><li>Tipo de toque atribuido: disponible</li><li>Hora del toque atribuido: se reporta solo como fecha (`dd/mm/yyyy`)</li></ul>Los clics e impresiones de X Ads no se incluyen en los reportes de raw data.<br /><br />El acceso al raw data sin restricciones depende de la participación en el **programa Advanced Mobile Measurement (AMM)** de X Ads y de la configuración de privacidad del usuario final:<ul><li>AMM no habilitado: todos los clics e impresiones se envían con `af_data_restriction=attribution`. Todos los eventos resultantes están restringidos.</li><li>AMM habilitado:<ul><li>Usuarios de la UE: los eventos están restringidos si no se autoriza el uso compartido de datos con partners empresariales.</li><li>Usuarios que no aceptaron compartir datos: los eventos están restringidos (`af_data_restriction=attribution`).</li><li>Usuarios que aceptaron compartir datos con partners comerciales: los eventos no están restringidos (`af_data_restriction=none`).</li></ul></li></ul>Para obtener más información, consulta la <Anchor target="_blank" href="/marketers/es/docs/x-ads-formerly-twitter-ads-setup-guide-overview#privacidad-del-usuario-de-x-ads">guía de configuración de X Ads, sección de privacidad del usuario</Anchor>. |
| Walmart | Las siguientes restricciones se aplican a la atribución view-through y click-through:<ul><li>`original_url` : restringido</li></ul>Los clics e impresiones de Walmart no se incluyen en los reportes de raw data. |

### Contexto de datos sin procesar

La restricción a nivel de campo de los datos sin procesar depende del contexto de los datos, como se indica en la siguiente tabla.

| Tipo de restricción | Informes afectados |
| --- | --- |
| [Fuente de medios restringida](/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios): De dónde proviene el usuario | <ul><li>Atribución: instalaciones, conversiones de retargeting y desinstalaciones</li><li>Eventos y sesiones dentro de la aplicación</li><li>Informes de Protect360</li></ul> |
| Totalmente restringido | <ul><li>Clics</li><li>Impresiones</li><li>Clics bloqueados (Protect360)</li></ul> |

### Entrega de datos sin procesar

Los datos de atribución a nivel de usuario en AppsFlyer están disponibles mediante las siguientes herramientas de entrega de datos sin procesar:

* Casillero de datos
* API de datos sin procesar (extracción)
* API push
* Página de exportación del panel de control
* Postbacks a redes
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">API para obtener datos de conversión (GCD)</Anchor> en el contexto de la API de datos del lado del cliente a nivel de usuario

<div id="unavailable-attribution-fields" />

<Accordion title="Campos de atribución no disponibles">

Los siguientes campos no están disponibles cuando la fuente de medios está restringida:

| Nombre para mostrar | Nombre de la API |
| --- | --- |
| Anuncio | af\_anuncio |
| ID del anuncio | id\_del\_anuncio\_af |
| Tipo de anuncio | af\_ad\_type |
| Conjunto de anuncios | af\_conjunto de anuncios |
| ID del conjunto de anuncios | af\_adset\_id |
| Ventana de retroceso de atribución | af\_attribution\_lookback |
| ID de campaña | af\_c\_id |
| Canal | af\_canal |
| Moneda del costo | af\_cost\_currency |
| Modelo de coste | af\_modelo\_de\_coste |
| Valor del coste | af\_valor\_de\_coste |
| Palabras clave | af\_palabras\_clave |
| Fuente de medios | af\_prt |
| ID del sitio | af\_siteid |
| ID del subsitio | af\_sub\_siteid |
| Subparámetro [n] (n=1-5) | af\_sub[n] (n=1-5) |
| Tiempo del toque atribuido | Se establece como TRUE o FALSE. |
| Tipo de toque atribuido | tipo\_táctil\_atribuido |
| Campaña | campaña |
| URL de enlace directo | URL de enlace profundo |
| Referente HTTP | http\_referrer |
| Instalación desde la tienda de aplicaciones | instalar\_tienda\_aplicaciones |
| ID de la palabra clave | keyword\_id |
| Tipo de coincidencia de palabras clave | keyword\_match\_type |
| Tipo de coincidencia | match\_type |
| ID de cuenta de la red | network\_account\_id |
| URL original | original\_url |
| Ventana de reengagement | af\_ventana\_de\_reengagement |
| Página del producto en la tienda | store\_product\_page |

</Accordion>

<div id="identifier-restriction" />

<Accordion title="Restricción de identificador">

Cuando se aplica la restricción de identificadores, los únicos campos disponibles en los informes de datos en bruto son los listados en la tabla que sigue.

| Nombre de la API |
| --- |
| <span id="event_time"></span>event\_time |
| <span id="event_name"></span>nombre\_del\_evento |
| <span id="event_revenue"></span>ingresos\_evento |
| <span id="event_revenue_currency"></span>moneda\_ingresos\_evento |
| <span id="event_revenue_usd"></span>ingresos\_evento\_usd |
| <span id="af_cost_model"></span>af\_modelo\_de\_coste |
| <span id="af_cost_value"></span>af\_valor\_de\_coste |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>fuente\_del\_evento |
| <span id="media_source"></span>fuente\_de\_medios |
| <span id="af_channel"></span>af\_canal |
| <span id="campaign"></span>campaña |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_conjunto de anuncios |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_anuncio |
| <span id="af_ad_id"></span>id\_del\_anuncio\_af |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>id\_aplicación |
| <span id="app_name"></span>nombre\_aplicación |
| <span id="bundle_id"></span>id\_paquete |
| <span id="is_retargeting"></span>es\_retargeting |
| <span id="retargeting_conversion_type"></span>tipo\_conversion\_retargeting |
| <span id="is_primary_attribution"></span>es\_atribución\_primaria |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_ventana\_de\_reengagement |
| <span id="country_code"></span>código\_de\_país |
| <span id="blocked_reason"></span>razón\_bloqueo |
| <span id="blocked_reason_value"></span>valor\_del\_motivo\_bloqueado |
| <span id="blocked_reason_rule"></span>regla\_del\_motivo\_bloqueado |
| <span id="blocked_sub_reason"></span>submotivo\_bloqueado |
| <span id="platform"></span>plataforma |
| <span id="is_paid_media"></span>es\_medio\_pagado |

</Accordion>

## Preguntas frecuentes

<div id="what-events-are-restricted" />

<Accordion title="¿Qué eventos están restringidos?">

Los eventos restringidos, como se detalla en la [tabla anterior](/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios), pueden incluir conversiones (instalaciones y reengagements) y eventos dentro de la aplicación asociados a los que se atribuye la red publicitaria restrictiva.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="¿Cómo afecta la fuente de medios restringida a los informes de datos sin procesar?">

* El campo *fuente de medios* se rellena con *restringido*.
* Los campos de atribución enumerados en este artículo están vacíos o se completan con *nulo*.

**Ejemplo de informe:** Instalaciones de <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">datos sin procesar restringidos</Anchor> en un archivo CSV. Otros informes de datos sin procesar se completan de manera similar.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-postbacks-sent-to-partners" />

<Accordion title="¿Cómo afecta la fuente de medios restringida a los postbacks enviados a los socios?">

Los postbacks enviados a los socios no incluyen campos de atribución.

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="¿Cómo afectan los eventos restringidos a los postbacks a plataformas de terceros?">

Los postbacks de las redes publicitarias atribuidas enumeradas en la [tabla anterior](#restricciones-de-fuente-de-medios) no se envían a plataformas de terceros.

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="¿Los eventos no restringidos afectan los postbacks a plataformas de terceros?">

Para los eventos enviados a plataformas de terceros, como plataformas de analítica y marketing, consulta las <Anchor target="_blank" href="/marketers/es/docs/discrepancies-between-appsflyer-and-third-party-platforms#restricciones-de-postbacks-en-plataformas-de-terceros">restricciones de postback en plataformas de terceros</Anchor>. En algunos casos, los postbacks de eventos no restringidos no incluyen la fuente de medios. Esto significa que la atribución se acredita como orgánica.

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="¿Qué pasa con los datos de asistencias que forman parte de la atribución?">

Los datos relacionados con las asistencias se consideran datos de atribución y no están disponibles.

</Accordion>

> 📄 **Ver también**
>
> <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention">Retención de datos a nivel de usuario</Anchor>

<div data-zendesk-anchors="raw-data-restriction=restricci%C3%B3n-de-datos-en-bruto 01H7WQHTV9RM2JF2BV45XF626H=restricci%C3%B3n-de-datos-en-bruto media-source-restrictions=restricciones-de-fuente-de-medios 01H7WQHTV9HJEHHH1N8VN6APX6=restricciones-de-fuente-de-medios 01H7WQHTV90YFRP3Z9AEP7ACRD=nota raw-data-context=contexto-de-datos-sin-procesar 01H7WQHTVA8H9FTBJ1FB6BJQ2A=contexto-de-datos-sin-procesar delivery-of-raw-data=entrega-de-datos-sin-procesar 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction faq=preguntas-frecuentes 01H7WQHTVA5439QPE6GNXNKJ63=preguntas-frecuentes h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=how-does-the-restricted-media-source-impact-postbacks-sent-to-partners h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=ver-tambi%C3%A9n" />

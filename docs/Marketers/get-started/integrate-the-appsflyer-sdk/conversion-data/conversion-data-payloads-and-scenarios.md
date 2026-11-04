---
title: Cargas útiles y escenarios de datos de conversión
metadata:
  keywords:
    - Conversion
    - Retargeting
    - Installs
    - Re-attribution
    - Re-engagement
    - Developers
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-31T13:05:33Z'
  edited_at: '2026-08-22T00:13:00Z'
  id: 360000726098
  locale: es
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/es/articles/360000726098
---
> **At a glance:** Usa los datos de conversión para identificar varios escenarios de conversión, personalizar la experiencia del usuario y mucho más.

<div id="overview" />

## Información general

La siguiente guía contiene varios escenarios de conversión de usuarios y sus correspondientes cargas útiles de datos de conversión:

* [Adquisición de usuarios (UA)](#datos-de-conversión-de-ua-con-srn)
* [Reorientación](#datos-de-conversión-de-retargeting)

Los datos de conversión se ponen a disposición en la plataforma utilizando cualquiera de los siguientes:

* <Anchor target="_blank" href="/marketers/es/docs/raw-data-export-page">Reportes de raw data</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">API push</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">El SDK de AppsFlyer</Anchor>

Debido a la compensación de la precisión/latencia, los datos de conversión para los mismos ID de dispositivo pueden diferir entre las API.

<div id="non-organic-conversion-data-payload-fields" />

### Campos de carga útil de datos de conversión no orgánicos

<div id="fields-always-available" />

#### Campos siempre disponibles

En la tabla que sigue, se enumeran los campos que siempre existen para las conversiones **no orgánicas**, independientemente de la `media_source` de conversión.

| Nombre del campo de carga útil | Nombre del campo de raw data | Observaciones |
| --- | --- | --- |
| `fuente_de_medios` | Fuente de medios | Publisher atribuido. Equivalente al parámetro `pid` en los enlaces de atribución |
| `hora_de_instalación` | Horario de instalación |  |
| `click_time` | Tiempo de toque atribuido | La hora en que ocurrió un clic o impresión en UTC |
| `is_first_launch` | N/D | `true`, `false` |
| `af_status` | El raw data se divide en reportes separados: orgánicos, no orgánicos | `"No orgánicas"` |
| `af_siteid` | ID de sitio |  |
| `adgroup_id` | ID de anuncio |  |
| `conjunto de anuncios` | Conjunto de anuncios |  |
| `id_anuncio` | ID de conjunto de anuncios |  |
| `agencia` | Fuente de medios | `null`, o nombre de agencia (para campañas dirigidas por agencias) |
| `campaña única` | Campaña |  |
| `id_campaña` | ID de campaña |  |
| `http_referrer` | Referente de HTTP |  |
| `tipo_conversion_retargeting` | Tipo de conversión de retargeting | "none", o retargeting\_conversion\_type |
| `af_sub[n] (n=1—5)` | Sub Param [n] (n=1–5) |  |

<div id="fields-available-in-some-cases" />

#### Campos disponibles en algunos casos

Los campos de la tabla que sigue están disponibles en algunos casos, dependiendo de cómo la SRN rellena el evento individual.

<table><thead><tr><th>Nombre de los campos de carga útil</th><th>Nombre del campo de raw data</th><th>Observaciones</th><th> </th></tr></thead><tbody><tr><td><code>af_canal</code></td><td>Canal</td><td><p>SRN que rellenan este parámetro:</p><ul><li>AppLovin</li><li>Anuncios de Google</li><li>Meta Ads</li><li>Snapchat</li><li>TikTok para empresas</li><li>Anuncios X</li></ul><p>Ejemplo: Facebook—Instagram, Google—YouTube </p></td><td> </td></tr><tr><td><code>orig_cost</code></td><td> </td><td>Nota (1)</td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td> </td><td>Nota (1)</td><td> </td></tr><tr><td><code>af_cpi</code></td><td> </td><td>Nota (1)</td><td> </td></tr><tr><td colspan="4"><p><strong>Nota</strong></p><p>(1) Los campos de costo se rellenan con valores compartidos por la red de publicidad. Para que la red de publicidad comparta el costo con AppsFlyer, debes habilitar la integración de costos en la página <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank"><strong>Integraciones activas</strong></a>. Algunas SRN admiten costos compartidos de forma masiva. En este caso, los campos de costo a nivel de evento se devuelven como 0. </p></td></tr></tbody></table>

<div id="additional-fields" />

### Campos adicionales

* <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#parámetros-del-enlace-de-atribución">Lista de parámetros de AppsFlyer</Anchor>
* Puedes agregar parámetros al enlace de atribución; estarán disponibles en la carga útil

Consulta el <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#data-fields-dictionary">diccionario de campos de raw data</Anchor> para obtener más información.

<div id="limitations" />

### Limitaciones

<div id="custom-parameter-names" />

<Accordion title="Nombres de parámetros personalizados">

Los parámetros personalizados no se pueden llamar `name` ("n" en minúscula. `Name` es válido).

Si un parámetro se llama `name`, se elimina de la carga útil.

</Accordion>

---

<div id="ua-conversion-data-with-srns" />

## Datos de conversión de UA con SRN

Las <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">redes de autorreporte</Anchor> (SRN) son ad networks que implementan sus propios mecanismos de atribución, por ejemplo, anuncios de Meta y Google.

Las SRN no utilizan enlaces de atribución. Es decir que:

* Los campos de carga útil están predefinidos
* No se pueden agregar campos a la carga útil agregando parámetros a un enlace de atribución.

Las SRN reportan las conversiones a AppsFlyer. Los datos de conversión están disponibles en la aplicación. Los campos disponibles varían según la SRN y se detallan en las pestañas de las SRN individuales que siguen.

<div id="a-note-about-meta-ads" />

#### Una nota sobre Anuncios de Meta

Si ejecutas campañas en Anuncios de Meta y no firmas los términos de servicio de Meta, AppsFlyer atribuye la instalación. La disponibilidad del reporte se limita de la siguiente manera:

* **Disponible:** paneles de control y reportes de datos agregados y analíticos:
* **No disponible:** raw data

<Tabs>
<Tab title="Anuncios Meta">

<div id="meta-ads-conversion-data" />

### Datos de conversión de Anuncios de Meta

| Nombre de campo | Comentarios | Fuente de datos |
| --- | --- | --- |
| `match_type` | `srn`, `gp_referrer`, `probabilistic` | AF |
| `fuente_de_medios` | Siempre `Facebook Ads` | AF |
| `agencia` | `null` o contiene el nombre de la agencia cuando se ejecutan <Anchor target="_blank" href="/partners/es/docs/about-agency-accounts#configuraciones-de-srn">campañas de anuncios de Meta</Anchor> | Anuncios Meta |
| `http_referrer` | Siempre `null` | Anuncios Meta |
| `retargeting_conversion_type` |  | AF |
| `af_canal` |  | Anuncios de Meta (publisher\_platform) |
| `af_status` | Siempre `no orgánico` | AF |
| `ad_id` | Solo para uso interno de Anuncios de Meta. | Anuncios de Meta (ad\_id) |
| `click_time` |  | AF |
| `hora_de_instalación` |  | AF |
| `is_first_launch` | `true`, `false` | Dispositivo |
| `adset_id` | Disponible en el raw data: ID de conjunto de anuncios | Anuncios de Meta (campaign\_id) |
| `is_fb` | Siempre `true` | AF |
| `campaña única` | Disponible en el raw data: Nombre de la campaña | Anuncios de Meta (campaign\_group\_name) |
| `campaign_id` | Disponible en el raw data: ID de campaña | Anuncios de Meta (campaign\_group\_id) |
| `is_paid` | Siempre `true` | Anuncios Meta |
| `adgroup` | Disponible en el raw data: Anuncio | Anuncios de Meta (adgroup\_name) |
| `adgroup_id` | Disponible en el raw data: ID de anuncio | Anuncios de Meta (adgroup\_id) |
| `conjunto de anuncios` | Disponible en el raw data: Conjunto de anuncios | Anuncios de Meta (campaign\_name) |
| `af_siteid` | **Asignación de af\_siteid:**  <br />  <br />***publisher\_platform*** → ***af\_siteid***  <br />Facebook → ""  <br />Instagram → Instagram  <br />AudienceNetwork → AudienceNetwork  <br />Messenger → Messenger  <br />unknown → unknown  <br />"" + is\_instagram=true → Instagram  <br />"" + is\_external=true → AudienceNetwork | Anuncios Meta |
| `af_sub[1-5]` | Siempre `null` | Anunciante |

**Nota:** Los campos relacionados con los costos no están disponibles porque los anuncios de Meta no comparten datos de costos en el momento de la conversión. Si se habilita el <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#cost-clicks-and-impressions">costo compartido</Anchor>, los anuncios de Meta comparten datos de costos con AppsFlyer varias veces al día.

</Tab>

<Tab title="Anuncios de Google">

<div id="google-ads-conversion-data" />

### Datos de conversión de Google Ads

<table><thead><tr><th>Nombre de campo</th><th>Observaciones</th></tr></thead><tbody><tr><td><code>match_type</code></td><td> Siempre <code>"srn"</code> </td></tr><tr><td><code>fuente_de_medios</code></td><td>Siempre <code>"googleadwords_int"</code> </td></tr><tr><td><code>agencia</code></td><td> <code>none</code> o el valor de <code>af_prt</code> </td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>tipo_conversion_retargeting</code></td><td> </td></tr><tr><td><code>af_canal</code></td><td>Nota (1)</td></tr><tr><td><code>af_status</code></td><td>Siempre <code>null</code> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>hora_de_instalación</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>adgroup_name</code></td><td> </td></tr><tr><td><code>id_anuncio</code></td><td>Siempre <code>null</code> </td></tr><tr><td><code>campaña única</code></td><td>Nota (3)</td></tr><tr><td><code>id_campaña</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>conjunto de anuncios</code></td><td>Nota (3)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>ad_event_id</code></td><td> </td></tr><tr><td><code>af_anuncio</code></td><td>Cadena vacía</td></tr><tr><td><code>id_del_anuncio_af</code></td><td>Disponible en raw data cuando Google devuelve el valor <code>creative_id</code>.</td></tr><tr><td><code>af_ad_type</code></td><td><span>Tipo de anuncio de AdWords</span></td></tr><tr><td><code>af_conjunto de anuncios</code></td><td>Disponible en el raw data: Conjunto de anuncios</td></tr><tr><td><code>af_adset_id</code></td><td>Disponible en el raw data: ID de conjunto de anuncios</td></tr><tr><td><code>af_c_id</code></td><td>Disponible en el raw data: ID de campaña</td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Nota (2)</td></tr><tr><td><code>af_dp</code></td><td>Solo relevante para las <a href="./google-ads-adwords-integration-setup-for-advertisers#utilizar-deferred-deep-linking-en-campañas-de-aplicaciones" target="_blank">campañas de Google App en Feeds</a>.</td></tr><tr><td><code>af_palabras_clave</code></td><td>Disponible en el raw data: Palabras clave</td></tr><tr><td><code>af_prt</code></td><td> <code>none</code> o el valor de <code>af_prt</code> </td></tr><tr><td><code>af_ventana_de_reengagement</code></td><td>Disponible en el raw data: Ventana de re-engagement </td></tr><tr><td><code>af_viewthrough_lookback</code></td><td>Disponible en el raw data: Ventana retrospectiva para atribución por impresiones</td></tr><tr><td><code>click_url</code></td><td>Disponible en el raw data: Referente HTTP</td></tr><tr><td><code>click-timestamp</code></td><td>Fuente: AppsFlyer</td></tr><tr><td><code>cost_cents_USD</code></td><td>Nota (2)</td></tr><tr><td><code>external_account_id</code></td><td>ID de cuenta de AdWords</td></tr><tr><td><code>gclid</code></td><td> </td></tr><tr><td><code>lat</code></td><td> </td></tr><tr><td><code>network</code></td><td>Nota (1)</td></tr><tr><td><code>orig_cost</code></td><td>Nota (2)</td></tr><tr><td><code>video_id</code></td><td>Siempre <code>null</code> </td></tr><tr><td colspan="2"> <strong>Notas</strong><br/>(1) Google hace uso de múltiples redes de publicidad. Utiliza <code>af_channel</code> junto con <code>network</code> para determinar la fuente de instalación.<br/>(2) Estos campos se devuelven como 0. Si el anunciante permite compartir los costos, Google envía datos de costos de AppsFlyer varias veces al día.(3) Utiliza <code>campaign</code> y <code>af_adset</code> para personalizar el contenido del usuario.(3) Utiliza <code>campaign</code> y <code>af_adset</code> para personalizar el contenido del usuario.</td></tr></tbody></table>

</Tab>

<Tab title="ASA">

<div id="apple-search-ads-conversion-data" />

### Datos de conversión de Apple Search Ads

<table><thead><tr><th>Nombre de campo</th><th>Observaciones</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Siempre <code>"srn"</code> </td></tr><tr><td><code>fuente_de_medios</code></td><td>Siempre <code>"Apple Search Ads"</code> </td></tr><tr><td><del><code>adset</code></del></td><td>Nota (2)</td></tr><tr><td><code>id_anuncio</code></td><td> </td></tr><tr><td><del><code>af_adset</code></del></td><td>Nota (2)</td></tr><tr><td><code>af_adset_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Nota (1)</td></tr><tr><td><del><code>af_keywords</code></del></td><td>Nota (2)—Usar ID de palabras clave</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Siempre <code>"Non-organic"</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agencia</code></td><td> <code>null</code> o valor de <code>af_prt</code> </td></tr><tr><td><del><code>campaign</code></del></td><td>Nota (2)</td></tr><tr><td><code>id_campaña</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Nota (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>hora_de_instalación</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Nota (1)</td></tr><tr><td><code>tipo_conversion_retargeting</code></td><td> </td></tr><tr><td colspan="3"> <strong>Notas</strong><br/>(1) Apple Search Ads admite costo compartido de forma masiva, no en los datos de conversión.<br/>(2) En desuso a partir del 15 de febrero de 2021, debido a la adopción por parte de Apple Search Ads de la API AdServices. </td></tr></tbody></table>

</Tab>

<Tab title="Snapchat">

<div id="snapchat-conversion-data" />

### Datos de conversión de Snapchat

| AppsFlyer | Anunciante |
| --- | --- |
| `match_type` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`   <br />Como SRN avanzada, admite todos los tipos de coincidencia. |
| `fuente_de_medios` | `"snapchat_int"` |
| `conjunto de anuncios` |  |
| `id_anuncio` |  |
| `af_anuncio` |  |
| `id_del_anuncio_af` |  |
| `af_conjunto de anuncios` |  |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_canal` |  |
| `af_cpi` |  |
| `af_siteid` |  |
| `af_status` | Siempre `"Non-organic"` |
| `af_sub[1-5]` |  |
| `af_viewthrough_lookback` |  |
| `agencia` |  |
| `campaña única` |  |
| `id_campaña` |  |
| `click_time` |  |
| `cost_cents_USD` |  |
| `http_referrer` |  |
| `hora_de_instalación` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` |  |
| `tipo_conversion_retargeting` |  |

</Tab>

<Tab title="Anuncios X">

<div id="twitter-conversion-data" />

<div id="x-ads-conversion-data" />

### Datos de conversión de Anuncios de X

| Nombre de campo | Observaciones |
| --- | --- |
| `match_type` | Siempre `"srn"` |
| `fuente_de_medios` | Siempre `"Twitter"` |
| `af_anuncio` |  |
| `id_del_anuncio_af` |  |
| `af_conjunto de anuncios` |  |
| `af_adset_id` |  |
| `af_canal` |  |
| `af_siteid` |  |
| `af_status` | Siempre `"Non-organic"` |
| `af_sub[1-5]` |  |
| `agencia` | Siempre `null` |
| `campaña única` |  |
| `id_campaña` | `null` o ID de campaña |
| `click_time` |  |
| `http_referrer` |  |
| `hora_de_instalación` |  |
| `is_first_launch` | `true`, `false` |
| `adgroup` |  |
| `adgroup_id` |  |
| `tipo_conversion_retargeting` | Siempre `"none"` |

**Nota:** Los campos de costos no aparecen en la carga útil porque Twitter no admite el uso compartido de datos de costos.

</Tab>

<Tab title="TikTok">

<div id="tiktok-conversion-data" />

<div id="tiktok-for-business-conversion-data" />

### Datos de conversión de TikTok for Business

| Nombre de campo | Observaciones |
| --- | --- |
| `match_type` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`   <br />Como SRN avanzada, admite todos los tipos de coincidencia. |
| `fuente_de_medios` | `tiktokglobal_int` |
| `af_anuncio` |  |
| `id_del_anuncio_af` |  |
| `af_conjunto de anuncios` |  |
| `af_adset_id` |  |
| `af_canal` | Siempre `"srn"` |
| `af_siteid` |  |
| `af_status` | Siempre `"Non-organic"` |
| `af_sub[1-5]` |  |
| `agencia` |  |
| `campaña única` |  |
| `id_campaña` |  |
| `click_time` |  |
| `http_referrer` |  |
| `hora_de_instalación` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `tipo_conversion_retargeting` |  |

**Nota:** Los campos de costo no aparecen en la carga útil porque TikTok no ofrece soporte para el uso compartido de datos de costo.

</Tab>

<Tab title="Oath">

<div id="oath-ad-platforms-conversion-data" />

### Datos de conversión de plataformas publicitarias de Oath

<table><thead><tr><th>Nombre de campo</th><th>Observaciones</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Siempre <code>"srn"</code> </td></tr><tr><td><code>fuente_de_medios</code></td><td>Siempre <code>"yahoogemini_int"</code> </td></tr><tr><td><code>conjunto de anuncios</code></td><td> </td></tr><tr><td><code>id_anuncio</code></td><td> </td></tr><tr><td><code>af_anuncio</code></td><td> </td></tr><tr><td><code>id_del_anuncio_af</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Nota (1)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Siempre <code>"Non-organic"</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agencia</code></td><td> </td></tr><tr><td><code>campaña única</code></td><td> </td></tr><tr><td><code>id_campaña</code></td><td> </td></tr><tr><td><code>tipo_campaña</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Nota (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>hora_de_instalación</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Nota (1)</td></tr><tr><td><code>tipo_conversion_retargeting</code></td><td> </td></tr><tr><td colspan="2"> <strong>Nota</strong><br/>(1) Oath admite costos compartidos pero envía los datos relacionados con los costos en masa, no en los datos de conversión.</td></tr></tbody></table>

</Tab>
</Tabs>

<div id="ua-conversion-with-other-ad-networks" />

## Conversión de UA con otras redes de publicidad

Para otras redes de publicidad, los datos de la carga útil se ven directamente afectados por los <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">parámetros en el enlace de atribución</Anchor>.

Examina las siguientes cargas útiles de JSON.

**¡Atención!** Nota: **Los datos de conversión se devuelven como una estructura de datos similar a un mapa. El desarrollador** no **interactúa con el raw JSON.**

<div id="applovin" />

<Accordion title="Applovin">

<div id="attribution-link" />

#### Enlace de atribución:

```http HTTPS
https://app.appsflyer.com/com.company.app?af_ad=ad_name&af_ad_type=INTER
  &af_channel=video&af_siteid=123_site_id&af_c_id=b8******************************&
  af_adset=_DEFAULT&pid=applovin_int&c=campaign_name
  &af_click_lookback=7d&clickid=10****************
  &advertising_id=50********************************&af_ip=
```

<div id="payload" />

#### Carga útil:

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "applovin_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:49:54.186",
      "adgroup_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-24 14:29:33.738",
      "agency": null,
      "cost_cents_USD": "0",
      "af_ad_type": "INTER",
      "af_c_id": "b8******************************",
      "adset": null,
      "advertising_id": "50********************************",
      "af_sub1": null,
      "clickid": "10****************",
      "af_click_lookback": "7d",
      "af_siteid": "123_site_id",
      "af_ad": "ad_name",
      "http_referrer": null,
      "af_channel": "video",
      "af_adset": "_DEFAULT",
      "af_sub5": null,
      "af_sub4": null,
      "af_cpi": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Los parámetros en el enlace de atribución aparecen como campos en la carga útil.
* Los demás campos en la carga útil que **no están en el enlace de atribución** aparecen con un valor nulo.
* AppLovin admite costos compartidos de anuncios, pero envía los datos de costos a AppsFlyer de forma masiva. Los campos relacionados con el costo se devuelven como 0.

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

<div id="attribution-link-1" />

#### Enlace de atribución:

```http HTTPS
https://app.appsflyer.com/id123456789?
  af_ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &clickid=ab***************&redirect=false
  &ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &af_lang=pt&imei=&af_sub1=&advertising_id=&af_ip=192.168.0.1&pid=ironsource_int
  &device_ip=192.168.0.1&c=campaign_name
  &idfa=01**********************************&af_siteid=123_site_id&
  af_enc_data=cN*********************************************************************
```

<div id="payload-1" />

#### Carga útil:

```json
{
      "adgroup": null,
      "af_enc_data": "cN*************************************************************************************",
      "campaign": "campaign_name",
      "media_source": "ironsource_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:59:32.194",
      "adgroup_id": null,
      "redirect": "false",
      "orig_cost": "0.75",
      "click_time": "2018-12-30 23:58:54.517",
     "agency": null,
      "cost_cents_USD": "75",
      "adset": null,
      "advertising_id": "35****************************",
      "af_sub1": null,
      "af_ip": "192.168.0.1",
      "clickid": "ab*******************",
      "af_sub3": null,
      "af_cost_value": "0.75",
      "af_ref": "ironsource_5f******************************************",
      "af_siteid": "123_site_id",
      "http_referrer": null,
      "af_cost_model": "cpi",
      "af_ua": "Mozilla/5.0 (Linux; Android 8.0.0; SM-N950F Build/R16NW; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/71.0.3578.99 Mobile Safari/537.36",
      "af_cost_currency": "USD",
      "af_sub5": null,
      "af_sub4": null,
      "af_lang": "en",
      "af_cpi": null,
      "af_click_lookback": "7d",
      "af_sub2": null,
      "af_status": "no orgánico"
  }
```

ironSource comparte con AppsFlyer los datos relacionados con el costo al producirse la conversión mediante los campos `orig_cost`, `cost_cents_USD` y `af_cost_value`.

Sin embargo, los datos relacionados con los costos **no aparecen en el enlace de atribución**. ironSource cifra los datos de costos y los almacena en el campo `af_enc_data`.

</Accordion>

<div id="retargeting-conversion-data" />

## Datos de conversión de retargeting

El retargeting incluye dos tipos de conversiones, reatribución o re-engagement.

> 👍 **Tip**
>
> **Consejo**
>
> Los datos de conversión para retargeting no siempre dan una indicación clara del tipo de conversión. Ver las [fuentes de datos de conversión alternativas](#fuentes-de-datos-de-conversión-alternativas).

<div id="re-attribution-with-srns" />

### Reatribución con SRN

Cuando un usuario es reatribuido a través de una SRN, la carga útil de los datos de conversión no indica que se trata de una campaña de retargeting. Dado que las SRN no utilizan enlaces de atribución, no hay forma de establecer un parámetro `is_retargeting=true` en el enlace de atribución. Para las **SRN que sí admiten retargeting**, AppsFlyer determina si el usuario debe ser reatribuido o no.

Lo que esto significa es que no hay forma de determinar, a nivel de SDK, si una instalación proviene de una campaña de retargeting. La única manera es establecer el nombre de la campaña de tal manera que indique una campaña de retargeting.

> 📘 **Note**
>
> **Nota**
>
> Establecer el nombre de la campaña de tal manera que indique el retargeting **no es un método infalible**. Ver [ejemplos para aprender más](#ejemplos-de-adquisición-y-reatribución-de-usuarios-mixtos).

<div id="re-attribution-with-regular-ad-networks" />

### Reatribución con redes de publicidad regulares

La atribución a redes de publicidad se basa en enlaces de atribución. Ya sean enlaces de atribución regulares o OneLink, con el retargeting, el enlace de atribución siempre tiene el parámetro `is_retargeting=true` establecido.

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Campaña de retargeting con Criteo">

<div id="attribution-link-2" />

#### Enlace de atribución

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

<div id="conversion-data-payload" />

#### Carga útil de los datos de conversión

```json
{
      "adgroup": null,
      "campaign": "campaign_name",
      "media_source": "criteo_int",
      "retargeting_conversion_type": "re-attribution",
      "adset_id": null,
      "campaign_id": null,
      "af_reengagement_window": "30d",
      "install_time": "2018-12-01 23:13:03.126",
      "adgroup_id": null,
      "redirect": "false",
      "af_sub5": null,
      "click_time": "2018-11-18 20:02:31.559",
      "agency": null,
      "cost_cents_USD": "0",
      "is_retargeting": "true",
      "af_cpi": null,
      "af_click_lookback": "30d",
      "af_siteid": null,
      "idfa": "68**********************************",
      "http_referrer": null,
      "orig_cost": "0.0",
      "af_sub4": null,
      "adset": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

* Parámetro `retargeting_conversion_type`: este parámetro indica el tipo de retargeting. Puede ser reatribución, re-engagement o ninguno.
* Parámetro `is_retargeting: true`: este parámetro indica que la instalación es una instalación reatribuida.
* `af_reengagement_window`: la ventana de atribución de re-engagement es el número de días en los que un evento puede atribuirse a un **usuario recaptado**. Dado que se trata de una conversión de reatribución, este parámetro es redundante.

</Accordion>

<div id="re-attribution-with-deferred-deep-linking" />

### Reatribución con enlaces profundos diferidos

A menudo, quieres enlazar profundamente a los usuarios reatribuidos que, por definición, no tienen la aplicación instalada. Por ejemplo, tú estableces una campaña que tiene como objetivo traer de vuelta a los usuarios que desinstalaron la aplicación. La campaña promueve un producto o servicio y quieres servir a los usuarios contenido relacionado con el producto o servicio que anuncias.

Esto se conoce como enlaces profundos diferidos. La carga útil de los datos de conversión para los enlaces profundos diferidos proviene del método `onConversionDataSuccess`.

<div id="deferred-deep-linking-with-srns" />

<Accordion title="Enlaces profundos diferidos con SRN">

Los parámetros de enlaces profundos definidos en las campañas de SRN no están disponibles fuera de las SRN. Esto incluye el parámetro `af_dp`, que contiene la ruta de acceso del esquema en la aplicación. La única excepción a esto es cuando se utilizan <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#utilizar-deferred-deep-linking-en-campañas-de-aplicaciones">campañas de Google App en Feeds</Anchor>. A fin de implementar enlaces profundos diferidos, se debe aplicar una lógica adicional para las campañas de SRN. Usa los datos de la respuesta `onConversionSuccess`, como la campaña, el conjunto de anuncios, el grupo de anuncios, para redirigir programáticamente a tus usuarios.

<div id="conversion-data-for-deferred-deep-linking-with-meta-ads" />

#### Datos de conversión para enlace profundo diferido con Anuncios de Meta

<Tabs>
<Tab title="Android">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="apps de iOS,">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,  
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

Puedes usar los datos en la respuesta de getConversionData, como la campaña, conjunto de anuncios, etc. para redirigir programáticamente a tus usuarios y servirles contenido relevante.

> 📘 **Note**
>
> **Ejemplo**
>
> La aplicación es una aplicación de comercio electrónico que se especializa en ropa deportiva. Un usuario que no tiene la aplicación instalada se involucra con un anuncio e instala la aplicación. Una vez que se inicia la aplicación, el SDK devuelve los datos de conversión. El desarrollador hace que la aplicación abra la actividad de la **colección de zapatillas de correr de verano** (campaña) en la tienda y sirve la categoría de **zapatillas para correr para mujer** (conjunto de anuncios).

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="Enlaces profundos diferidos con enlaces de atribución">

Hay tres formas de enlazar profundamente a los usuarios:

<div id="uri-schemes" />

#### Esquemas URI

Al usar esquemas URI, tanto para los enlaces de atribución como para OneLink, el enlace de atribución y la carga útil son los siguientes:

**Enlace de atribución**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```http
// OneLink corto
  https://dhba.onelink.me/2rAD/71ba577e

  // OneLink largo
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**Carga útil**

```json
{
      "af_deeplink": true,
      "campaign": "campaign_name",
      "media_source": "media_source_name",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "orig_cost": "0.0",
      "click_time": "2018-12-30 23:59:09",
      "install_time": "2018-12-30 23:59:39.330",
      "agency": null,
      "cost_cents_USD": "0",
      "adset": "AD_SET_NAME",
      "ad_id": "AD_ID",
      "af_siteid": null,
      "http_referrer": null,
      "af_cpi": null,
      "af_sub5": null,
      "af_sub4": null,
      "af_sub1": null,
      "af_sub3": null,
      "af_sub2": null,
      "af_status": "No orgánico",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true` - cuando este parámetro aparece y está configurado como true, busca los campos `scheme` y `host`
* `scheme` y `host` - estos campos provienen del parámetro `af_dp` en el enlace de atribución e indican el esquema y la actividad a la que debe aplicarse el Deep Linking del usuario

<div id="ios-universal-links-and-android-app-links" />

#### Enlaces universales de iOS y enlaces de aplicaciones de Android

Estas son las otras dos de las tres formas de realizar enlaces profundos.

Cuando se utilizan enlaces universales o enlaces de aplicaciones, el OneLink y la carga útil son los siguientes:

**OneLink**

```http
// OneLink corto
  https://dhba.onelink.me/2rAD/71ba577e

  // OneLink largo
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**Carga útil**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "No orgánico",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* Campo `shortlink`: este campo indica el OneLink específico del que proviene el usuario. Ayuda al desarrollador a saber cómo proceder para ejecutar una actividad y servir contenido. Otros campos, como `campaign`, también pueden utilizarse para este propósito.

  > 🚧 **Important**
  >
  > **Importante:**
  >
  > El campo `shortlink` no aparece en la carga útil cuando se usa el OneLink largo.
  >
  > En ambos casos (OneLink corto o largo) recomendamos agregar un parámetro personalizado que indique la actividad. Por ejemplo `&deep_link_activity=shoes_cateogry`


> 📘 **Note**
>
> **Nota**
>
> El uso de enlaces universales y enlaces de aplicaciones solo es posible con OneLink.

</Accordion>

<div id="re-engagement-with-srns" />

### Re-engagement con SRN

Al igual que con las campañas de reatribución, cuando se recapta un usuario a través de una SRN, los datos de conversión no indican que se trata de una campaña de re-engagement. Se puede establecer el nombre de la campaña de manera que indique una campaña de re-engagement.

<div id="re-engagement-with-regular-ad-networks" />

### Re-engagement con redes de publicidad regulares

Aquí también, la carga útil de los datos de conversión no indica que el usuario proviene de una campaña de re-engagement. Para superar esta limitación, puedes establecer el nombre de la campaña para indicar un re-engagement.

<div id="re-engagement-with-deep-linking" />

### Re-engagement con enlaces profundos

Una parte importante del re-engagement es enviar al usuario a una actividad específica. Por ejemplo, si anuncias algún producto u oferta. En tales casos, deseas enviar a los usuarios que hacen clic en el anuncio directamente a la actividad de la aplicación para este producto u oferta.

Para ello, se utilizan enlaces profundos. Los datos de conversión en los enlaces profundos son realmente importantes. Contienen la información necesaria para que el desarrollador personalice la experiencia del usuario y lo envíe a la actividad correcta.

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="Re-engagement: enlaces profundos con SRN">

Los datos de conversión no están disponibles cuando un usuario recaptado proviene de una SRN. El desarrollador debe usar los métodos de las SRN para obtenerlo al lanzar la aplicación.

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="Re-engagement: enlaces profundos con redes de publicidad">

Cuando se recapta a un usuario y se inicia la aplicación, los siguientes datos de conversión están disponibles en el método `onAppPenAttribution`:

Tanto para iOS como para Android, cuando se usa la versión corta de OneLink, los datos de conversión constituyen un mapa estructurado de todos los parámetros incluidos en el enlace:

Ejemplo:

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* El desarrollador de la aplicación puede utilizar dichos parámetros, como `af_dp` y el nombre de la campaña, para enviar al usuario a una actividad específica y servir el contenido relevante.

> 🚧 **Important**
>
> **Importante:**
>
> Recomendamos usar la versión corta de OneLink. Haz clic <Anchor target="_blank" href="/marketers/es/docs/understand-onelink-short-vs-long-urls">aquí</Anchor> para obtener más información.

Otra razón para utilizar la versión corta de OneLink es la estructura de los datos de conversión que devuelve la versión larga. Cuando se usa la versión larga, los datos de conversión son un mapa con un solo campo llamado `link` que contiene todo el OneLink largo.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

<div id="alternative-conversion-data-sources" />

### Fuentes de datos de conversión alternativas

* La Push API ofrece una carga útil de conversión detallada que indica una reatribución o un re-engagement. Las cargas útiles de la Push API incluyen un campo llamado `re_targeting_conversion_type`. Este campo indica el tipo de conversión, ya sea reatribución o re-engagement. Para obtener más información, consulta nuestra <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">guía de Push API</Anchor>.
* Los reportes de raw data también contienen indicadores del tipo de conversión. En el reporte de raw data de conversiones de retargeting, hay una columna llamada ***Nombre del evento***. El valor en esta columna es ***re-engagement*** o ***reatribución***, según el tipo de conversión.

<div id="examples-of-mixed-user-acquisition-and-re-attribution" />

### Ejemplos de adquisición y reatribución de usuarios mixtos

> 📘 **Note**
>
> **Ejemplo**
>
> 1. Un usuario instala tu aplicación y luego la desinstala. La acción de instalación pone al usuario en una <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor>. Configuras una campaña de adquisición de usuarios (no de retargeting) con anuncios de Meta. También estableces la integración de AppsFlyer con Anuncios de Meta para permitir el retargeting.
>
>    Mientras aún está en la ventana de reatribución, el usuario ve el anuncio, hace clic en él y reinstala la aplicación. Desde el punto de vista de AppsFlyer, el usuario es un usuario reatribuido.
>
>    Esto se debe a dos factores:
>
>    1. La configuración con Anuncios de Meta permite el retargeting.
>    2. El usuario se encuentra dentro de la ventana de reatribución.
>
>    En este caso, el nombre de la campaña no indica reatribución.
> 2. Tomemos el mismo ejemplo, solo que esta vez el usuario se encuentra fuera de la ventana de reatribución. En este caso, la instalación es una nueva instalación no orgánica.
> 3. Veamos otro ejemplo. Estableces una campaña de retargeting en Anuncios de Meta. Algunos usuarios se cruzan con la campaña e instalan la aplicación. Sin embargo, estos usuarios instalan la aplicación por primera vez. Dichos usuarios no se consideran usuarios reatribuidos. En cambio, AppsFlyer los considera como usuarios que provienen de una campaña de adquisición de usuarios.

<div data-zendesk-anchors="overview=informaci%C3%B3n-general h_01HCY86CKDJK9TNHPAZB0QX2ZX=informaci%C3%B3n-general nonorganic-conversion-data-payload-fields=campos-de-carga-%C3%BAtil-de-datos-de-conversi%C3%B3n-no-org%C3%A1nicos h_01HCY86CKDEMB3428YHCNJQA5R=campos-de-carga-%C3%BAtil-de-datos-de-conversi%C3%B3n-no-org%C3%A1nicos fields-always-available=campos-siempre-disponibles h_01HCY86CKDBQRGAY7GHNBJE4WK=campos-siempre-disponibles fields-available-in-some-cases=campos-disponibles-en-algunos-casos h_01HCY86CKDYQMYB9BQ4MXWP8A5=campos-disponibles-en-algunos-casos additional-fields=campos-adicionales h_01HCY86CKD47M85AZVEA5C4JH7=campos-adicionales limitations=limitaciones h_01HCY86CKEFX646H9BSKSFGZ36=limitaciones h_01HCY86CKEZ2483XB461M2C9EC=custom-parameter-names ua-conversion-data-with-srns=datos-de-conversi%C3%B3n-de-ua-con-srn h_01EGKTQN6XDYHA60P2WKHBBVFT=datos-de-conversi%C3%B3n-de-ua-con-srn a-note-about-facebook=una-nota-sobre-anuncios-de-meta h_01HCY86CKENFEGX53G9G4SGPSK=una-nota-sobre-anuncios-de-meta facebook-conversion-data=datos-de-conversi%C3%B3n-de-anuncios-de-meta h_01HCY86CKE658H36F3VJQMATQK=datos-de-conversi%C3%B3n-de-anuncios-de-meta h_01HCY86CKF6FY96PAWB5Y7YXSQ=google-ads-conversion-data h_01HCY86CKFMNNNJZTPGK4870YN=apple-search-ads-conversion-data h_01HCY86CKF26JRT64JR9JZEAKJ=snapchat-conversion-data h_01HCY86CKFM94SQWYARCM0GEJ9=twitter-conversion-data h_01HSQRQSK8W9K6871K0EWHDF76=tiktok-conversion-data h_01HCY86CKFS5SJBECSY42VRJWP=oath-ad-platforms-conversion-data ua-conversion-with-other-ad-networks=conversi%C3%B3n-de-ua-con-otras-redes-de-publicidad h_01HCY86CKFB0GEJRTYSXN9YZ08=conversi%C3%B3n-de-ua-con-otras-redes-de-publicidad h_01HCY86CKFY787RD4BHQDVEVFV=applovin attribution-link=enlace-de-atribuci%C3%B3n h_01HCY86CKFXM5XXJZSPXPB6397=enlace-de-atribuci%C3%B3n payload=carga-%C3%BAtil h_01HCY86CKFDDXWT2KKFTKKBGHM=carga-%C3%BAtil h_01HCY86CKFV55GYY7C51D7F72S=ironsource attribution-link::a45a1b4a=enlace-de-atribuci%C3%B3n-1 h_01HCY86CKFYGEYR2TRPSD87KDA=enlace-de-atribuci%C3%B3n-1 payload::81867f5c=carga-%C3%BAtil-1 h_01HCY86CKFKKFQDG1P42R1FSDJ=carga-%C3%BAtil-1 retargeting-conversion-data=datos-de-conversi%C3%B3n-de-retargeting h_01EHQ74JS84509GT6M93SZA4HX=datos-de-conversi%C3%B3n-de-retargeting reattribution-with-srns=reatribuci%C3%B3n-con-srn h_01HCY86CKFAVWP1W0ZNEN5P30A=reatribuci%C3%B3n-con-srn reattribution-with-regular-ad-networks=reatribuci%C3%B3n-con-redes-de-publicidad-regulares h_01HCY86CKF1PV8MRR902RAHQGW=reatribuci%C3%B3n-con-redes-de-publicidad-regulares h_01HCY86CKF1RGK01VTV3EEHQVM=retargeting-campaign-with-criteo attribution-link::c16e96bb=enlace-de-atribuci%C3%B3n-2 h_01HCY86CKFSKBBMFKA8NN8XTPC=enlace-de-atribuci%C3%B3n-2 conversion-data-payload=carga-%C3%BAtil-de-los-datos-de-conversi%C3%B3n h_01HCY86CKG2YQQC629SC3RAFKE=carga-%C3%BAtil-de-los-datos-de-conversi%C3%B3n reattribution-with-deferred-deep-linking=reatribuci%C3%B3n-con-enlaces-profundos-diferidos h_01HCY86CKGXV50H79R0YH1GB2C=reatribuci%C3%B3n-con-enlaces-profundos-diferidos h_01HCY86CKG12YRGFEEJ27DQART=deferred-deep-linking-with-srns conversion-data-for-deferred-deep-linking-with-facebook=datos-de-conversi%C3%B3n-para-enlace-profundo-diferido-con-anuncios-de-meta h_01HCY86CKGX9VHSV3ASKXMFM0X=datos-de-conversi%C3%B3n-para-enlace-profundo-diferido-con-anuncios-de-meta h_01HCY86CKG3XWM4X0YH7WYCEH4=deferred-deep-linking-with-attribution-links uri-schemes=esquemas-uri h_01HCY86CKGDM2NE1FCRC92K8R0=esquemas-uri ios-universal-links-and-android-app-links=enlaces-universales-de-ios-y-enlaces-de-aplicaciones-de-android h_01HCY86CKGY1NE4214DES0Y2AV=enlaces-universales-de-ios-y-enlaces-de-aplicaciones-de-android reengagement-with-srns=re-engagement-con-srn h_01HCY86CKG4TRYR6TWYYVB0FJE=re-engagement-con-srn reengagement-with-regular-ad-networks=re-engagement-con-redes-de-publicidad-regulares h_01HCY86CKGM2JS7C9T71R6GPH1=re-engagement-con-redes-de-publicidad-regulares reengagement-with-deep-linking=re-engagement-con-enlaces-profundos h_01HCY86CKG0NPQAA2ZRWWNKGQD=re-engagement-con-enlaces-profundos h_01HCY86CKGEBHQVFRGJH96KDFJ=reengagement-deep-linking-with-srns h_01HCY86CKGJ9HG7AGB5MFP33RK=reengagement-deep-linking-with-ad-networks alternative-conversion-data-sources=fuentes-de-datos-de-conversi%C3%B3n-alternativas h_01HCY86CKG3N6ZXV70G4VMZ0X5=fuentes-de-datos-de-conversi%C3%B3n-alternativas examples-of-mixed-user-acquisition-and-reattribution=ejemplos-de-adquisici%C3%B3n-y-reatribuci%C3%B3n-de-usuarios-mixtos h_01HCY86CKGK9DVVB7T6CVNB8ZN=ejemplos-de-adquisici%C3%B3n-y-reatribuci%C3%B3n-de-usuarios-mixtos" />

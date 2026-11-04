---
title: 'Obtén datos de conversión con el SDK de AppsFlyer: Retargeting'
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:17:47Z'
  edited_at: '2026-09-28T00:06:07Z'
  id: 4410481260817
  locale: es
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/es/articles/4410481260817
---
> **At a glance:** Descubre cómo las reatribuciones y los re-engagements se reflejan en los datos de conversión de los viajes de los usuarios SRN y no SRN.

<div id="retargeting-conversion" />

## Conversión de retargeting

El retargeting incluye dos tipos de conversiones, reatribución o re-engagement.

> 👍 **Tip**
>
> Los datos de conversión para retargeting no siempre dan una indicación clara del tipo de conversión. Ver [fuentes alternativas de datos de conversión](#fuentes-de-datos-de-conversión-alternativas).

<div id="re-attribution-with-srns" />

## Reatribución con SRNs

Cuando un usuario es reatribuido a través de una SRN, el payload de los datos de conversión no indica que se trata de una campaña de retargeting. Dado que las SRNs no utilizan enlaces de atribución, no hay forma de establecer un parámetro `is_retargeting=true` en el enlace de atribución. Para las **SRNs que sí admiten retargeting**, AppsFlyer determina si el usuario debe ser reatribuido o no.

Lo que esto significa es que no hay forma de determinar, a nivel de SDK, si una instalación proviene de una campaña de retargeting.

> 📘 **Note**
>
> Establecer el nombre de la campaña de tal manera que indique el retargeting **no es un método infalible**. Ver [ejemplos para saber más](#ejemplos-de-adquisición-y-reatribución-de-usuarios-mixtos).

<div id="re-attribution-with-regular-ad-networks" />

## Reatribución con ad networks regulares

La atribución a ad networks se basa en enlaces de atribución. Ya sean enlaces de atribución regulares o de OneLink, con el retargeting, el enlace de atribución siempre tiene el parámetro `is_retargeting=true` establecido.

<Accordion title="Campaña de retargeting con Criteo">

<div id="attribution-link" />

#### Enlace de atribución

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

<div id="conversion-data-payload" />

#### Payload de los datos de conversión

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
* Parámetro `is_retargeting: true`: este parámetro indica que la instalación es una instalación reatribuida
* `af_reengagement_window`: la ventana de atribución de re-engagement es el número de días en los que un evento puede atribuirse a un **usuario que ha interactuado de nuevo**. Dado que se trata de una conversión de reatribución, este parámetro es redundante.

</Accordion>

<div id="re-attribution-with-deferred-deep-linking" />

## Reatribución con deferred deep linking

Muchas veces, quieres realizar deep linking a los usuarios reatribuidos que, por definición, no tienen la aplicación instalada. Por ejemplo, si estableces una campaña que tiene como objetivo traer de vuelta a los usuarios que desinstalaron la aplicación. La campaña promueve un producto o servicio y quieres servir a los usuarios contenido relacionado con el producto o servicio que anuncias.

Esto se conoce como deferred deep linking. La carga útil de los datos de conversión para los enlaces profundos diferidos proviene del método `onConversionDataSuccess`.

<Accordion title="Deferred deep linking con SRNs">

Para implementar Deferred deep linking con SRN, se debe aplicar una lógica adicional a las campañas de SRN. Usa los datos de la respuesta de `onConversionSuccess`, como campaign, adset y adgroup, para redirigir programáticamente a tus usuarios.

<div id="conversion-data-for-deferred-deep-linking-with-meta-ads" />

#### Datos de conversión para deferred deep linking con Meta Ads

<Tabs>
<Tab title="Android">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"no orgánico",
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
     "media_source":"Meta anuncios",
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

Puedes usar los datos de la respuesta de getConversionData, como campaign, adset, etc., para redirigir programáticamente a tus usuarios y mostrarles contenido relevante.

> 📘 **Note**
>
> La aplicación es una aplicación de eCommerce que se especializa en ropa deportiva. Un usuario que no tiene la app instalada interactúa con un anuncio e instala la app. Una vez que se inicia la aplicación, el SDK devuelve los datos de conversión. El desarrollador hace que la aplicación abra la actividad de la **colección de zapatillas de running de verano** (campaign) en la tienda y muestre la categoría de **zapatillas de running para mujer** (adset).

</Accordion>

<Accordion title="Deferred deep linking con enlaces de atribución">

Hay tres formas de enlazar a los usuarios:

<div id="uri-schemes" />

#### Esquemas URI

Al usar esquemas URI, tanto para los enlaces de atribución como para OneLink, el enlace de atribución y el payload son los siguientes:

**Enlace de atribución**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
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
      "af_status": "no orgánico",
      "scheme": "superapp",
      "host": "deeplink_activity"
  }
```

* `af_deeplink: true` - cuando este parámetro aparece y está establecido en true, busca los campos `scheme` y `host`
* `scheme` y `host` - estos campos provienen del parámetro `af_dp` en el enlace de atribución e indican el esquema y la actividad a la que se debe dirigir al usuario mediante deep linking

<div id="ios-universal-links-and-android-app-links" />

#### Universal Links de iOS y App Links de Android

Estas son las otras dos de las tres formas de realizar deep linking.

Al usar Universal Links o App Links, OneLink y el payload son los siguientes:

**OneLink**

```http
// short OneLink
  https://dhba.onelink.me/2rAD/71ba577e

  //long OneLink
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
      "af_status": "no orgánico",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* Campo `shortlink` - es el campo que indica el OneLink específico del que proviene el usuario. Ayuda al desarrollador a saber cómo proceder para iniciar una actividad y mostrar contenido. Otros campos, como `campaign`, también se pueden usar con este fin.

> 🚧 **Important**
>
> El campo `shortlink` no aparece en el payload cuando se usa el OneLink largo.
>
> En ambos casos (OneLink corto o largo), recomendamos añadir un parámetro personalizado que indique la actividad. Por ejemplo `&deep_link_activity=shoes_cateogry`

> 📘 **Note**
>
> Usar Universal Links y App Links solo es posible con OneLink.

</Accordion>

<div id="re-engagement-with-srns" />

## Re-engagement con SRN

Al igual que con las campañas de reatribución, cuando se vuelve a captar a un usuario a través de una SRN, los datos de conversión no indican que se trata de una campaña de re-engagement.

<div id="re-engagement-with-regular-ad-networks" />

## Re-engagement con ad networks regulares

Aquí también, la carga útil de los datos de conversión no indica que el usuario proviene de una campaña de re-engagement. Para superar esta limitación, puedes establecer el nombre de la campaña para indicar un re-engagement.

<div id="re-engagement-with-deep-linking" />

## Re-engagement con deep linking

Una parte importante del re-engagement es enviar al usuario a una actividad específica. Por ejemplo, si anuncias algún producto u oferta. En tales casos, deseas enviar a los usuarios que hacen clic en el anuncio directamente a la actividad de la aplicación para este producto u oferta.

Para ello, se utiliza Deep Linking. Los datos de conversión en Deep Linking son realmente importantes. Contienen la información necesaria para que el desarrollador personalice la experiencia del usuario y lo envíe a la actividad correcta.

<Accordion title="Re-engagement: deep linking con SRNs">

Los datos de conversión no están disponibles cuando un usuario re-engaged proviene de una SRN. El desarrollador debe usar los métodos de las SRNs para obtenerlo al abrir la aplicación.

</Accordion>

<Accordion title="Re-engagement: deep linking con ad networks">

Cuando se vuelve a captar a un usuario y se inicia la aplicación, los siguientes datos de conversión están disponibles en el método `onAppOpenAttribution`:

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
> Recomendamos usar la versión corta de OneLink. Haz clic <Anchor target="_blank" href="/marketers/es/docs/understand-onelink-short-vs-long-urls">aquí</Anchor> para obtener más información.

Otra razón para utilizar la versión corta de OneLink es la estructura de los datos de conversión que devuelve la versión larga. Cuando se usa la versión larga, los datos de conversión son un mapa con un solo campo llamado `link` que contiene todo el OneLink largo.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

<div id="alternative-conversion-data-sources" />

## Fuentes de datos de conversión alternativas

* La Push API ofrece un payload de conversión detallado que indica una reatribución o un re-engagement. Los payloads de Push API incluyen un campo llamado `re_targeting_conversion_type`. Este campo indica el tipo de conversión, ya sea reatribución o re-engagement. Para más información, consulta nuestra <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">guía de Push API</Anchor>.
* Los reportes de raw data también contienen indicadores del tipo de conversión. En el reporte de raw data de conversiones de retargeting, hay una columna llamada ***Nombre del evento***. El valor en esta columna es ***re-engagemen*t** o ***reatribución***, según el tipo de conversión.

<div id="examples-of-mixed-user-acquisition-and-re-attribution" />

## Ejemplos de adquisición y reatribución de usuarios mixtos

> 📘 **Note**
>
> 1. Un usuario instala tu aplicación y luego la desinstala. La acción de instalación pone al usuario en una <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor>. Configuras una campaña de adquisición de usuarios (sin retargeting) con Meta anuncios. También configuras la integración de AppsFlyer con Meta Ads para permitir el retargeting. Mientras el usuario siga dentro de la ventana de reatribución, ve el anuncio, hace clic en él y vuelve a instalar la aplicación. Desde el punto de vista de AppsFlyer, el usuario es un usuario reatribuido. Esto se debe a dos factores:
>
>    1. La configuración con Meta Ads permite el retargeting.
>    2. El usuario se encuentra dentro de la ventana de reatribución.
>
>    En este caso, el nombre de la campaña no indica reatribución.
> 2. Tomemos el mismo ejemplo, solo que esta vez el usuario se encuentra fuera de la ventana de reatribución. En este caso, la instalación es una nueva instalación no orgánica.
> 3. Veamos otro ejemplo. Estableces una campaña de retargeting en Meta Ads. Algunos usuarios se cruzan con la campaña e instalan la aplicación. Sin embargo, estos usuarios instalan la aplicación por primera vez. Dichos usuarios no se consideran usuarios reatribuidos. En cambio, AppsFlyer los considera como usuarios que provienen de una campaña de adquisición de usuarios.

<div data-zendesk-anchors="retargeting-conversion=conversi%C3%B3n-de-retargeting h_01EHQ74JS84509GT6M93SZA4HX=conversi%C3%B3n-de-retargeting reattribution-with-srns=reatribuci%C3%B3n-con-srns h_01JNBRN0TBCVKBP6X6GCK3ADG9=reatribuci%C3%B3n-con-srns reattribution-with-regular-ad-networks=reatribuci%C3%B3n-con-ad-networks-regulares h_01JNBRN0TCF7YC76661XNS78AD=reatribuci%C3%B3n-con-ad-networks-regulares attribution-link=enlace-de-atribuci%C3%B3n h_01JNBRN0TCP9CAHV3X4QD0AVRS=enlace-de-atribuci%C3%B3n conversion-data-payload=payload-de-los-datos-de-conversi%C3%B3n h_01JNBRN0TCXAZKYVYY56Q4GVHN=payload-de-los-datos-de-conversi%C3%B3n reattribution-with-deferred-deep-linking=reatribuci%C3%B3n-con-deferred-deep-linking h_01JNBRN0TCECNRZ5ZBH2WWAWHV=reatribuci%C3%B3n-con-deferred-deep-linking conversion-data-for-deferred-deep-linking-with-facebook=datos-de-conversi%C3%B3n-para-deferred-deep-linking-con-meta-ads h_01JNBRN0TC3NAE862BG274DRWW=datos-de-conversi%C3%B3n-para-deferred-deep-linking-con-meta-ads uri-schemes=esquemas-uri h_01JNBRN0TC909V4TNCEK4ZP83H=esquemas-uri ios-universal-links-and-android-app-links=universal-links-de-ios-y-app-links-de-android h_01JNBRN0TCH7HYZ4BCZTNS89SS=universal-links-de-ios-y-app-links-de-android reengagement-with-srns=re-engagement-con-srn h_01JNBRN0TCT2F11CQ4H8208JCB=re-engagement-con-srn reengagement-with-regular-ad-networks=re-engagement-con-ad-networks-regulares h_01JNBRN0TCNTAAD47ZTTK3NWYJ=re-engagement-con-ad-networks-regulares reengagement-with-deep-linking=re-engagement-con-deep-linking h_01JNBRN0TCGN9Y8ZHSEC4HMKPM=re-engagement-con-deep-linking alternative-conversion-data-sources=fuentes-de-datos-de-conversi%C3%B3n-alternativas h_01JNBRN0TCZ8T35W3AAA4HVD9M=fuentes-de-datos-de-conversi%C3%B3n-alternativas examples-of-mixed-user-acquisition-and-reattribution=ejemplos-de-adquisici%C3%B3n-y-reatribuci%C3%B3n-de-usuarios-mixtos h_01JNBRN0TC13RAZ73AFV6G92VB=ejemplos-de-adquisici%C3%B3n-y-reatribuci%C3%B3n-de-usuarios-mixtos" />

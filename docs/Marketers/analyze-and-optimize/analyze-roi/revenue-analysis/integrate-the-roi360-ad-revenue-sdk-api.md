---
title: >-
  Guía de integración de la API del SDK de ingresos publicitarios a nivel de
  impresiones de ROI360
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2026-08-12T11:48:58Z'
  id: 4416353506833
  locale: es
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/es/articles/4416353506833
---
> **Resumen:** La API del SDK de AppsFlyer trabaja con redes publicitarias para informar sobre los ingresos publicitarios con un nivel de precisión de impresión.

![mceclip1__1_.png](https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png)

## Informe de ingresos publicitarios a nivel de impresiones mediante la API del SDK

**Opciones de informe de ingresos publicitarios**

Los ingresos publicitarios se informan a AppsFlyer con granularidad agregada (vía API) o con granularidad a nivel de impresión (vía SDK). Datos a nivel de impresiones mediante el SDK:

* Ofrece una actualización de datos más rápida y disponibilidad anticipada en AppsFlyer.
* Admite SKAN.
* Está destinado para AppsFlyer SDK V6.15+. Para versiones anteriores del SDK, se utiliza un conector SDK en vez de la API. Esta documentación incluye enlaces para desarrolladores cuando son pertinentes.

**Nota:**

* Las impresiones de ingresos publicitarios se recopilan y procesan en AppsFlyer, pero no se contabilizan en su paquete de aplicaciones.
* Hay un <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-unity">complemento de ingresos publicitarios de AppsFlyer para Unity</Anchor>.

### Informe de ingresos publicitarios mediante la API del SDK

**Principios de funcionamiento del SDK**

La API del SDK de ingresos publicitarios envía datos de ingresos por impresiones al SDK de AppsFlyer. Estos eventos de impresión se recopilan y procesan en AppsFlyer, y el evento de ingresos publicitarios,  , se genera en la plataforma con los ingresos atribuidos a la fuente de UA original.

**Visualización de datos**

El evento `af_ad_revenue` se utiliza para identificar los ingresos por anuncios. Este evento se emplea en toda la plataforma, incluidos los paneles de control y otras herramientas de entrega de datos.

**Redes compatibles**

La lista de redes de mediación y monetización de ingresos publicitarios compatibles que pueden enviarnos datos a través de la API del SDK de ingresos por publicidad es la siguiente:

* <Anchor target="_blank" href="/marketers/es/docs/ironsource-campaign-configuration#ad-revenue-tab">Mediación de Unity LevelPlay</Anchor> (anteriormente ironSource)
* <Anchor target="_blank" href="/marketers/es/docs/applovin-max-ad-revenue-configuration">Applovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Topon Pte.
* Tradplusad
* <Anchor target="_blank" href="/marketers/es/docs/yandex-direct-campaign-configuration">Yandex</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation (cuando la solución de mediación no está en la lista de socios de mediación compatibles)
* directMonetizationNetwork (cuando la aplicación se integra directamente con redes de monetización sin mediación)

**Actualización de datos**

La API del SDK **envía los datos de ingresos a la plataforma en el momento en que se muestra el anuncio. Para clientes premium de ROI360, los datos están disponibles en:**

* **El tema del nivel de impresión de DataLocker a la 1 a. m. y cada hora desde entonces,**
* **Los informes de actividad y cohorte de AppsFlyer se generan a las 5 a. m. UTC, y cada 4 horas desde entonces.**

## Implementación de la API del SDK de ingresos publicitarios de AppsFlyer

**Para implementar la API del SDK de ingresos publicitarios de AppsFlyer**:

1. <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Habilite los ingresos por publicidad a nivel de SDK en AppsFlyer</Anchor> para el socio con el que desea conectar. **Nota**: Esto debe hacerse para cada aplicación de forma individual.
2. Indique a su desarrollador que integre la API del SDK de ingresos publicitarios de AppsFlyer usando <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">estas instrucciones</Anchor>.
3. Para registrar los ingresos por publicidad en su panel de SKAdNetwork, siga las <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">instrucciones de ingresos publicitarios de SKAN</Anchor>.
4. Prueba tu integración: una vez integrada, verifica que los eventos de ingresos por anuncios se estén recibiendo con uno de los siguientes métodos:
   * En el <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers#view-live-events">visor de eventos en vivo</Anchor>, comprueba que los eventos de ingresos por anuncios aparezcan en tiempo real. Ten en cuenta que el visor de eventos en vivo solo muestra eventos enviados desde dispositivos de prueba registrados.
   * En la página **Revenue Settings**, edita la integración de ingresos por anuncios correspondiente y haz clic en **Test Connection** para comprobar si se ha procesado recientemente algún evento válido de ingresos por anuncios. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Conéctate con partners integrados en los ingresos por anuncios</Anchor>.

## Características y limitaciones

| Caducado | Observaciones |
| --- | --- |
| Admob | <ul><li>Para activar iLTV para Admob, siga <Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">este enlace</Anchor></li><li>Para Android y Unity, el SDK iLTV de Admob reporta los ingresos por impresiones en <Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">microunidades</Anchor>. Para que el monto correcto de ingresos publicitarios en USD se muestre en AppsFlyer, antes de enviar el monto a AppsFlyer, divida la cantidad obtenida del controlador de eventos iLTV por 1 millón.</li></ul> |
| Valor de los ingresos por publicidad | La API del SDK no procesa los eventos de impresión con valores de ingresos superiores a 10 $ (o el equivalente en otras monedas). |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-API=informe-de-ingresos-publicitarios-a-nivel-de-impresiones-mediante-la-api-del-sdk 01H8HHAQHK6CDK8X2Y6N4GANNC=informe-de-ingresos-publicitarios-a-nivel-de-impresiones-mediante-la-api-del-sdk reporting-ad-revenue-using-the-sdk-API=informe-de-ingresos-publicitarios-mediante-la-api-del-sdk 01H8HHAQHKQ3H3R21Z1JYNJ2EE=informe-de-ingresos-publicitarios-mediante-la-api-del-sdk implementing-generic-appsflyer-ad-revenue-sdk-API=implementaci%C3%B3n-de-la-api-del-sdk-de-ingresos-publicitarios-de-appsflyer 01H8HHAQHKCXKPJJE8EDT1J9CR=implementaci%C3%B3n-de-la-api-del-sdk-de-ingresos-publicitarios-de-appsflyer traits-and-limitations=caracter%C3%ADsticas-y-limitaciones 01H8HHAQHMCSVQ2ZAT3G7XJKAN=caracter%C3%ADsticas-y-limitaciones" />

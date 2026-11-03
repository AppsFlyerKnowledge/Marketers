---
title: Uso de Firebase y Google Tag Manager con AppsFlyer–Descripción general
metadata:
  keywords:
    - GTM
    - Google Tag Manager
    - firebase
    - Advertisers
    - datalayer
    - data layer
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-05-13T19:42:23Z'
  edited_at: '2026-08-12T11:59:57Z'
  id: 210353513
  locale: es
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/es/articles/210353513
---
> **De un vistazo:** Sobre el envío de eventos reportados a través del SDK de Firebase a AppsFlyer usando Google Tag Manager.

<Image alt="gtm.png" src="https://files.readme.io/fbb4e0f83baf6f5f7f8dc83e02986ca011f5cb919b9870768da1606798211dcc-360002517245.png" width="289px" />

La integración de AppsFlyer con Google Tag Manager (GTM) y Firebase permite al desarrollador enviar eventos in-app a Firebase utilizando el SDK de Firebase, y hacer que los eventos se envíen a AppsFlyer a través del SDK mediante Google Tag Manager. Esto evita tener que enviar el mismo evento dos veces.

Los eventos enviados con GTM se modelan en eventos in-app de AppsFlyer. El nombre del evento, los parámetros y la estructura son los mismos. Si ya tienes GTM en tu aplicación, utilizarlo para enviar eventos a AppsFlyer es sencillo.

Sigue los pasos y las instrucciones de esta guía para enviar eventos. 

### consideraciones

* **Fuente del evento en el raw data:** los eventos generados por GTM tienen la fuente establecida como S2S en los reportes de raw data. Esto puede llevar a cierta confusión ya que los eventos son reportados por el SDK.
* **Actualización del valor de conversión de SKAdNetwork**: los eventos generados por GTM y reportados al SDK como se describe en esta guía hacen que el SDK actualice el valor de conversión de forma similar a los eventos regulares del SDK. Solo tienes que activarlo y establecer tu <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">configuración de medición de SKAdNetwork</Anchor>.

> 📘 **Nota**
>
> * Actualmente, la integración de Google Tag Manager no admite el envío de los siguientes parámetros a AppsFlyer:
>   * <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">ID de usuario del cliente</Anchor>
>   * `att`
>   * `os`Ten en cuenta que:
>   * Cuando se envían postbacks de eventos in-app a SRN, se requiere el parámetro `att`.
>   * Cuando se envían postbacks de eventos in-app a Anuncios de Meta, se requieren los parámetros `att` y `os`.

### Requisitos previos

Antes de empezar a enviar eventos a AppsFlyer utilizando GTM, debes implementar el SDK de GTM en tu aplicación. Necesitas:

1. Necesitas una cuenta de [GTM.](https://www.google.com/analytics/tag-manager/)
2. Debes tener la configuración de la integración de GTM + Firebase para tu aplicación (instrucciones para [Android](https://developers.google.com/tag-manager/android) e [iOS](https://developers.google.com/tag-manager/ios/)).
3. <Anchor target="_blank" href="/marketers/es/docs/integrate-the-appsflyer-sdk">Integrar el SDK de AppsFlyer</Anchor> si no lo has hecho.

Una vez que lo tengas todo listo, continúa a la <Anchor target="_blank" href="/marketers/es/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup">configuración de GTM</Anchor>.

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/migrate-from-firebase-dynamic-links-to-appsflyer">Migrar de Firebase Dynamic Links a AppsFlyer</Anchor>

<div data-zendesk-anchors="considerations=consideraciones h_01HE7SKSCBH47YYFTKBWY3JVSV=consideraciones h_01HE7SKSCBBTTWATRZ87BYRW6G=nota prerequisites=requisitos-previos h_01HE7SKSCB9QHA4WEERVSWMF0P=requisitos-previos h_01HE7SQQG2VJW9179Q77PTZFPH=consulta-tambi%C3%A9n" />

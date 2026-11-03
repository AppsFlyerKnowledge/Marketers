---
title: Medición de campañas que preserva la privacidad
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2023-11-28T07:10:15Z'
  edited_at: '2026-08-12T11:57:45Z'
  id: 20489739742609
  locale: es
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/es/articles/20489739742609
---
> **De un vistazo:** Obtén respuestas a las preguntas frecuentes más comunes sobre los métodos de medición de campañas que preservan la privacidad, las redes implicadas y sus efectos en el retargeting, el view-through y las limitaciones de las aplicaciones dirigidas a menores.

## Visión general

En la actual era centrada en la privacidad, las plataformas y las tecnologías limitan cada vez más el uso de los ID de anunciante, lo que impulsa a la industria hacia métodos de medición que cumplen los requisitos de privacidad y, al mismo tiempo, permiten una medición eficaz de las campañas. Para estos casos, AppsFlyer admite varios métodos de medición de campañas que preservan la privacidad tanto para ad networks SRN como para ad networks no SRN, como se describe a continuación.

<div id="what-methods-of-attribution-dont-require-collecting-device-ids" />

<Accordion title="¿Cómo mide AppsFlyer el rendimiento de las campañas cuando los ID de anunciante no están disponibles?">

AppsFlyer proporciona los siguientes métodos de medición:

* <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#install-referrer-android-only">Coincidencia de referencia de la instalación</Anchor> (solo para Android)
* <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">Modelado probabilístico</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#deep-link">Deep Linking</Anchor> (solo para retargeting)

</Accordion>

<div id="what-networks-can-be-attributed-without-using-a-device-id" />

<Accordion title="¿Qué métodos de atribución admiten las ad networks?">

Las **ad networks no SRN** se pueden medir con los métodos de atribución adicionales que preservan la privacidad descritos en las [preguntas frecuentes anteriores](#what-methods-of-attribution-dont-require-collecting-device-ids).

**La mayoría de las** <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">**SRN**</Anchor> requieren un ID publicitario para la medición; sin embargo, algunas, como se especifica a continuación, admiten otros métodos de medición de campañas que preservan la privacidad.

| nombres de SRN reservados | Emitido |
| --- | --- |
| SRN avanzadas (como Tiktok y Snapchat) | En función de los clics y las impresiones de la SRN avanzada |
| Meta Ads | <ul><li><Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#medición-de-eventos-agregados-aem-para-ios">Uso de AEM para dispositivos iOS</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#getting-userlevel-data-for-android-installs">Uso de los siguientes parámetros para dispositivos Android:</Anchor><ul><li>`gp_referrer`</li><li>`fb_referrer`</li><li>`ig_referrer`</li></ul></li></ul> |
| Anuncios de Google | Uso del parámetro `gbraid` para dispositivos iOS |
| Apple Search Ads | Uso de la <Anchor target="_blank" href="/marketers/es/docs/apple-ads-integration-setup#asa-attribution">atribución de ASA</Anchor> |
| <ul><li>Anuncios de Google</li><li>Anuncios de Meta</li><li>Snapchat</li><li>TikTok</li><li>Anuncios X</li><li>Yahoo! Japan Japan</li></ul> | <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">SKÁN</Anchor> |

</Accordion>

<div id="can-i-measure-retargeting-without-using-the-device-id" />

<Accordion title="¿Qué opciones de medición de retargeting admite AppsFlyer?">

La atribución de retargeting se puede usar con los métodos mencionados [anteriormente](#what-methods-of-attribution-dont-require-collecting-device-ids).   
**Nota:** La atribución de referencia de la instalación (para Android) es solo para reatribuciones, no para re-engagements.

</Accordion>

<div id="can-i-measure-viewthrough" />

<Accordion title="¿La medición de view-through es compatible con los métodos anteriores?">

View-through es compatible mediante <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">Modelado probabilístico</Anchor>. Otros métodos, como el referente y el Deep Linking, permiten la medición de clics, pero no la de view-through.

Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#viewthrough-attribution">atribución por visualización</Anchor>.

</Accordion>

<div id="can-deep-linking-be-done-without-a-device-id" />

<Accordion title="¿El Deep Linking requiere un ID de publicidad?">

El Deep Linking de usuarios desde una campaña a una actividad específica de tu aplicación puede producirse en distintos escenarios, según si la aplicación ya está instalada.

La disponibilidad de un ID de publicidad puede afectar al comportamiento del Deep Linking en función de los siguientes escenarios:

* **Deep Linking directo:** **sin impacto**.   
  El deep link envía a los usuarios existentes directamente a una actividad específica de tu aplicación. Como se especifica en la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#métodos-de-atribución">tabla de métodos de atribución</Anchor>, la atribución se realiza mediante los datos de la URL del enlace profundo, que se envía directamente al SDK.
* **Deep Linking indirecto:** **solo funciona si la atribución se realiza correctamente**.   
  El deep link envía a los usuarios existentes a una actividad específica de tu aplicación, pero la aplicación no se abre directamente. Cuando el usuario vuelve a abrir la aplicación más tarde, se registra un re-engagement y **se realiza el Deep Linking indirecto. Sin embargo, esto ocurre solo si la atribución se realiza correctamente** (mediante los métodos de atribución [descritos arriba](#what-methods-of-attribution-dont-require-collecting-device-ids)). Por lo tanto, si la atribución se realiza correctamente, el Deep Linking también funcionará.
* **Deferred deep linking:** **solo funciona si la atribución se realiza correctamente**.  
  El deep link envía a los nuevos usuarios a la tienda de aplicaciones. Después de la instalación, la aplicación se abre en una actividad específica. **Esto ocurre solo si la atribución se realiza correctamente** (mediante los métodos de atribución [descritos arriba](#what-methods-of-attribution-dont-require-collecting-device-ids)). Por lo tanto, si la ausencia de un ID de anunciante sigue permitiendo la atribución, el Deep Linking también funcionará.

</Accordion>

<div id="what-are-the-implications-of-childdirected-app-limitations-on-attribution" />

<Accordion title="¿En qué se diferencia la medición cuando no hay disponible un ID de publicidad?">

En determinados escenarios con restricciones de privacidad, la cobertura de la medición puede ser más limitada. AppsFlyer sigue proporcionando una medición significativa de campañas al tiempo que preserva la privacidad del usuario.

</Accordion>

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/preserve-user-privacy">Preservar la privacidad del usuario</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#privacidad-del-usuario">Privacidad del usuario en el nivel del SDK</Anchor>

<div data-zendesk-anchors="eeee=visi%C3%B3n-general h_01HMBEZD0P31S8N9ZERB17ZHPT=visi%C3%B3n-general h_01HGAC6QR6XJ20K92DE8KQ02P3=what-methods-of-attribution-dont-require-collecting-device-ids 01HMEBCTBWJX03WEHY3QTR3RAS=what-networks-can-be-attributed-without-using-a-device-id h_01HGAC6QR7VXFNPENAXTAV97Y7=can-i-measure-retargeting-without-using-the-device-id h_01HGAC6QR7E298ZTH8G4TTD7EC=can-i-measure-viewthrough h_01HMRHWVEQCHS7QBJHPZS3B8KZ=can-deep-linking-be-done-without-a-device-id h_01HGAC6QR752QPT4MSDQ7TWAXT=what-are-the-implications-of-childdirected-app-limitations-on-attribution h_01HGAC6QR7R4ZTWJEMSKHACNPF=v%C3%A9ase-tambi%C3%A9n" />

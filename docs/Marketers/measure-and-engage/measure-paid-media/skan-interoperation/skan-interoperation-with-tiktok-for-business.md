---
title: Interoperabilidad de SKAN con TikTok for Business
metadata:
  keywords:
    - Advertisers
    - ios14
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-03-14T12:05:58Z'
  edited_at: '2026-08-12T12:21:06Z'
  id: 360018499098
  locale: es
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/es/articles/360018499098
---
> **En resumen:** La interoperabilidad de SKAN permite a TikTok compartir postbacks de SKAN con AppsFlyer y permite a AppsFlyer compartir tu mapeo de medición de valor de conversión con TikTok.

## Interoperabilidad de SKAN: AppsFlyer &lt;-> TikTok

Si trabajas con varios partners de ad networks, es mejor configurarlo en AppsFlyer. Al hacerlo, las métricas de rendimiento de SKAN, enriquecidas con otras métricas como el costo, están disponibles a través de la plataforma de AppsFlyer.

### Alcance de la interoperabilidad de SKAN con TikTok

La interoperabilidad permite que AppsFlyer y TikTok compartan el mapeo del valor de conversión de SKAN (establecido en AppsFlyer). Esto permite a ambas partes proporcionar métricas de rendimiento. Al habilitar la integración de TikTok for Business (ya sea la integración antigua o la <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup">integración avanzada de SRN</Anchor> ), AppsFlyer proporciona eventos de TikTok con fines de optimización. Consulta la <Anchor target="_blank" href="/marketers/es/docs/skan-integrated-partners-list">lista de campos de enriquecimiento</Anchor> admitidos por TikTok.

### Orientación de TikTok for Business

Al configurar tus campañas de TikTok for Business, lee el Impacto y la guía de iOS 14 <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10000858">de TikTok y ten en cuenta lo siguiente:</Anchor>

* Asegúrate de que el SDK de AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">esté actualizado.</Anchor>
* [Configura un ID de app de TikTok](https://ads.tiktok.com/help/article?aid=10001060) para cada aplicación que anuncies en TikTok for Business.
  * El ID de aplicación de TikTok es un código único generado en el administrador de TikTok Ads y TikTok lo utiliza para confirmar la propiedad del anunciante de sus aplicaciones.
  * Aunque no es obligatorio, se recomienda introducir el ID de aplicación de todas las aplicaciones.  
    Esto te ayuda a controlar mejor tus datos de TikTok For Business y a desbloquear productos adicionales.
  * **Para agregar más de un ID de aplicación de TikTok:**
    1. Ingresa tu primer ID de aplicación de TikTok.
    2. Presiona **Entrar.**
    3. Introduce tu siguiente ID de aplicación de TikTok.
  * La configuración de un ID de aplicación de TikTok no afecta tus datos en AppsFlyer.
  * [Aprende más sobre los requisitos de ID de aplicación de TikTok para iOS 14](https://ads.tiktok.com/help/article?aid=10001070).
* [Mapeo completo de eventos de conversión](/docs/skan-interoperation-with-tiktok-for-business#3) para bytedanceglobal\_int y tiktokglobal\_int.
* Consulta la guía sobre la limitación de campañas y la consolidación de cuentas o campañas.

Trabaja directamente con tu gestor de cuentas de TikTok for Business en la configuración y estrategia de SKAN.

TikTok es compatible con SKAN de la siguiente manera:

* Medición y optimización a través de la API de medición de conversiones.
* Reportes de campañas dedicadas de iOS 14 en TikTok for Business.

### Límites de campaña para campañas dedicadas de iOS 14

Debido a las limitaciones de la API de SKAN, TikTok for Business admite lo siguiente al crear campañas dedicadas de iOS 14 (aplicables a los anuncios de instalación de aplicaciones y a los anuncios dinámicos de productos para la prospección de aplicaciones):

* ​Las aplicaciones de iOS están limitadas a 15 campañas con 5 grupos de anuncios por campaña.
* Campañas dedicadas de iOS 14:
  * Se puede crear a partir de varias cuentas publicitarias, pero el número total de campañas activas está limitado a 15.
  * En todos los objetivos relevantes, se tiene en cuenta el límite (15) y, después de alcanzarlo, los anunciantes deben esperar al menos 72 horas después de que una campaña se haya pausado, desactivado o eliminado para liberar un espacio de campaña antes de comenzar una nueva.

### Habilitación de la interoperabilidad

La interoperabilidad se logra a través de la configuración en los dashboards de AppsFlyer y TikTok for Business. No se requiere interoperabilidad ni cambios en la propia aplicación.

**Para habilitar la interoperabilidad de SKAN de AppsFlyer con** **TikTok for Business:**

| Paso | Acción | Detalles |
| --- | --- | --- |
| <span id="1"></span>1 | Requisitos previos de la aplicación | <ul><li>Integra la última versión del SDK de AppsFlyer en tu aplicación.</li></ul> |
| <span id="2"></span>2 | Revisión de la configuración de SKAN | Configura y activa la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Solución SKAN</Anchor> de AppsFlyer<br /><br />**Para ver los ajustes de SKAN**:<ol><li>En AppsFlyer, ve a **Configuración** > **SKAN Conversion Studio**.</li><li>Haz clic en opciones (⋮), y revisa que la **Medición de SKAN** esté encendida.<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>Selecciona el modo de medición que prefieras.<br />Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Toma nota de los nombres exactos de los eventos configurados. Los necesitarás en el siguiente paso.</li></ol> |
| <span id="3"></span>3 | Mapeo de eventos in-app | Revisa y, si es necesario, realiza cambios en tus asignaciones de eventos in-app de TikTok for Business.<br /><br />**Para ver y configurar asignaciones de eventos in-app**:<ol><li>En AppsFlyer, ve a **Configuración** > **Integraciones activas**.</li><li>Busca y selecciona **TikTok for Business**.</li><li>En la pestaña **Integración** asegúrate de que la integración con TikTok for Business esté activada y configurada.</li><li>En la sección **Postback de eventos in app:**<ol><li>[Obligatorio] Si no está activado, activa **Postback de eventos in-app**.</li><li>Verifica que los eventos in-app que establezcas en <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor> estén asignados a los nombres de los eventos de TikTok for Business o a los eventos de tu <Anchor target="_blank" href="/marketers/es/docs/skan-cv-decode-map-your-cv-to-events">mapa de conversión personalizado</Anchor>.<br />**Nota:** Solo mapea `af_skad_revenue` al evento `Purchase` de TikTok cuando tu esquema de conversión SKAN mide los ingresos generales.<br />[![](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)</li></ol></li><li>Haz clic en **Guardar integración**.</li></ol> |

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Guía de soluciones SKAN de AppsFlyer</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-tiktok=interoperabilidad-de-skan-appsflyer---tiktok h_01HDNYZ0CT1MGCRSSP3MXTJK5V=interoperabilidad-de-skan-appsflyer---tiktok scope-of-skan-interoperability-with-tiktok=alcance-de-la-interoperabilidad-de-skan-con-tiktok h_01HDNYZ0CT5NZHDHDBDSCFG911=alcance-de-la-interoperabilidad-de-skan-con-tiktok tiktok-for-business-guidance=orientaci%C3%B3n-de-tiktok-for-business 01HR1TPFCSXRGYC610AR7KMTS5=orientaci%C3%B3n-de-tiktok-for-business campaign-limits-for-dedicated-ios-14-campaigns=l%C3%ADmites-de-campa%C3%B1a-para-campa%C3%B1as-dedicadas-de-ios-14 h_01HDNYZ0CT7RNDAEWYKBHS6PET=l%C3%ADmites-de-campa%C3%B1a-para-campa%C3%B1as-dedicadas-de-ios-14 enabling-interoperation=habilitaci%C3%B3n-de-la-interoperabilidad h_01HDNYZ0CTJGY3GPC9F907NEPT=habilitaci%C3%B3n-de-la-interoperabilidad h_01HDNZ1BW5EBP0JCX84MTYPQ6K=consulta-tambi%C3%A9n" />

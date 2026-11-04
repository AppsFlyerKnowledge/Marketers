---
title: '[Beta] Interoperabilidad de SKAN con Amazon'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2024-08-15T09:36:46Z'
  edited_at: '2026-09-10T00:29:39Z'
  id: 27548444974353
  locale: es
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/es/articles/27548444974353
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **En resumen:** La interoperabilidad de SKAN permite a Amazon compartir postbacks de SKAN con AppsFlyer y permite a AppsFlyer compartir tu mapeo de medición del valor de conversión con Amazon.

<div id="note" />

> 📘 **Advertencia**
>
> Para participar en esta beta cerrada, notifícalo a tu representante de Amazon.

<div id="skan-interoperability-appsflyer---amazon" />

## Interoperabilidad de SKAN: AppsFlyer &lt;-> Amazon

Si trabajas con varios partners de ad networks, es mejor configurarlo en AppsFlyer. Al hacerlo, las métricas de rendimiento de SKAN, enriquecidas con otras métricas como costo, estarán disponibles a través de la plataforma de AppsFlyer.

<div id="scope-of-skan-interoperability-with-amazon" />

### Alcance de la interoperabilidad de SKAN con Amazon

La interoperabilidad permite que AppsFlyer y Amazon compartan el mapeo del valor de conversión de SKAN (establecido en AppsFlyer). Esto permite a ambas partes proporcionar métricas de rendimiento. Consulta la <Anchor target="_blank" href="/marketers/es/docs/skan-integrated-partners-list">lista de campos de enriquecimiento</Anchor> admitidos por Amazon.

<div id="amazon-dsp-app-install-ads-guidance" />

### Guía de anuncios de instalación de la aplicación en Amazon DSP

El programa iOS Alpha de Amazon DSP permite a los usuarios de AppsFlyer ejecutar campañas de descarga de apps para iOS, aprovechando la plataforma de Amazon y SKAdNetwork de Apple para una medición del rendimiento centrada en la privacidad. Este programa está diseñado para anunciantes que buscan adquirir y fidelizar eficazmente a los usuarios de apps iOS. Para configurarlo:

**Prerrequisitos**

* Asegúrate de que el SDK de AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">esté actualizado.</Anchor>
* Configura SKAdNetwork en AppsFlyer
  * Integra el SDK de AppsFlyer en tu aplicación.
  * Configura tu esquema de valor de conversión de SKAdNetwork en Conversion Studio de AppsFlyer.
  * Verifica que SKAdNetwork esté habilitado y que tu esquema de conversión esté configurado correctamente.
* Acepta los Términos y condiciones para anunciantes de Amazon

  * **Clientes de servicio gestionado:** Tu representante de Amazon te ayudará a aceptar el Acuerdo de audiencias para anunciantes.
  * **Clientes de autoservicio:**
    * Inicia sesión en tu cuenta de Amazon Ads.
    * Ve a Amazon DSP > Campaign Manager > Events Manager > pestaña Conversiones.
    * Si se te solicita, acepta los Términos para continuar.

  **Pasos de incorporación**
* Registra tu aplicación en Amazon Ads
  * **Clientes de servicio gestionado:** Proporciona a tu representante de Amazon el ID de aplicación de iTunes y el nombre de tu aplicación.
  * **Clientes de autoservicio:**
    * Inicia sesión en advertising.amazon.com.
    * Ve a Amazon DSP > Campaign Manager > Events Manager > pestaña Aplicaciones.
    * Haz clic en **Add App**, selecciona **AppsFlyer** como tu partner de medición móvil y proporciona los siguientes detalles:
      * Plataforma: iOS
      * Nombre de la aplicación: el nombre de tu aplicación
      * iTunes App ID: Se encuentra en la URL de la aplicación en la tienda de aplicaciones de Apple (p. ej., 123456789).
  * Activa la **medición de SKAdNetwork** y guarda.
  * Consulta la pestaña Conversions para confirmar que Amazon reconoce tu esquema de conversión. Si falta algún evento, ponte en contacto con tu representante de Amazon.

**Siguientes pasos**

* Clientes gestionados: notifica a tu representante de Amazon una vez que se complete el onboarding.
* Clientes self-service: sigue la guía de configuración de campañas de Amazon para empezar a crear campañas

**Funciones clave del programa**

* Tipo de campaña: campañas de adquisición de usuarios de apps para iOS.
* Marco de medición: SKAdNetwork 2.0–4.0.
* Entorno de anuncios: anuncios in-app en las propiedades de Amazon y en determinados intercambios de terceros.
* Informes: insights de campaña en tiempo real a través de AppsFlyer.

<div id="enabling-interoperation" />

### Habilitación de la interoperabilidad

La interoperabilidad se logra a través de la configuración en los dashboards de AppsFlyer y Amazon. No se requiere interoperabilidad ni cambios en la propia aplicación.

**Para habilitar la interoperabilidad de SKAN de AppsFlyer con** **Amazon:**

| Paso | Acción | Detalles |
| --- | --- | --- |
| <span id="1"></span>1 | Requisitos previos de la aplicación | <ul><li>Integra la última versión del SDK de AppsFlyer en tu aplicación.</li></ul> |
| <span id="2"></span>2 | Revisión de la configuración de SKAN | Configura y activa la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Solución SKAN</Anchor> de AppsFlyer<br /><br />**Para ver los ajustes de SKAN**:<ol><li>En AppsFlyer, ve a **Configuración** > **SKAN Conversion Studio**.</li><li>Haz clic en opciones (⋮), y revisa que la **Medición de SKAN** esté encendida.<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>Selecciona el modo de medición que prefieras.<br />Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Toma nota de los nombres exactos de los eventos configurados. Los necesitarás en el siguiente paso.</li></ol> |
| <span id="3"></span>3 | Mapeo de eventos in-app | Revisa y, si es necesario, realiza cambios en las asignaciones de eventos in-app de Amazon. **Al menos un evento in-app debe asignarse a Amazon** para que Amazon recupere el esquema y complete la integración.<br /><br />**Para ver y configurar asignaciones de eventos in-app**:<ol><li>En AppsFlyer, ve a **Configuración** > **Integraciones activas**.</li><li>Busca y selecciona **Amazon Ads**.</li><li>En la sección **Postback de eventos in app:**<ol><li>[Obligatorio] Si no está activado, activa **Postback de eventos in-app**.</li><li>Verifica que los eventos in-app que configures en <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor> estén asignados a los nombres de eventos de Amazon o a los eventos de tu <Anchor target="_blank" href="/marketers/es/docs/skan-cv-decode-map-your-cv-to-events">mapa de conversión personalizado</Anchor>.<br />**Nota:** Asigna `af_skad_revenue` al nombre de evento de Amazon `OFF_AMAZON_purchases`</li></ol></li><li>Haz clic en **Guardar integración**.</li></ol> |

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Guía de la solución SKAN de AppsFlyer</Anchor>

<div data-zendesk-anchors="01JEBXBFKGN066TY78WKH0VEXC=advertencia skan-interoperability-appsflyer-tiktok=interoperabilidad-de-skan-appsflyer---amazon h_01HDNYZ0CT1MGCRSSP3MXTJK5V=interoperabilidad-de-skan-appsflyer---amazon scope-of-skan-interoperability-with-tiktok=alcance-de-la-interoperabilidad-de-skan-con-amazon h_01HDNYZ0CT5NZHDHDBDSCFG911=alcance-de-la-interoperabilidad-de-skan-con-amazon tiktok-for-business-guidance=gu%C3%ADa-de-anuncios-de-instalaci%C3%B3n-de-la-aplicaci%C3%B3n-en-amazon-dsp 01HR1TPFCSXRGYC610AR7KMTS5=gu%C3%ADa-de-anuncios-de-instalaci%C3%B3n-de-la-aplicaci%C3%B3n-en-amazon-dsp enabling-interoperation=habilitaci%C3%B3n-de-la-interoperabilidad h_01HDNYZ0CTJGY3GPC9F907NEPT=habilitaci%C3%B3n-de-la-interoperabilidad h_01HDNZ1BW5EBP0JCX84MTYPQ6K=consulta-tambi%C3%A9n" />

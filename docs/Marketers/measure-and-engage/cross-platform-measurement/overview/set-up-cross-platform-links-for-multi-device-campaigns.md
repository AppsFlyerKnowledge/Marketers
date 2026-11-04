---
title: Configura enlaces multiplataforma para campañas en múltiples dispositivos
metadata:
  keywords:
    - Attribution
    - Advertisers
    - CTV
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-06-19T07:02:43Z'
  edited_at: '2026-09-17T00:20:23Z'
  id: 6966260647185
  locale: es
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/es/articles/6966260647185
---
> **En resumen:** Cómo promover, atribuir y medir las instalaciones de aplicaciones en plataformas a vistas de anuncios en otras plataformas. Por ejemplo, las instalaciones de aplicaciones móviles a partir de anuncios vistos en dispositivos CTV, las instalaciones de aplicaciones de consolas de videojuegos a partir de anuncios vistos en dispositivos móviles o de ordenador (web) y las instalaciones de aplicaciones CTV de anuncios vistos en dispositivos móviles o de ordenador (web).

<div id="overview" />

## Descripción general

Con los enlaces multiplataforma de OneLink de AppsFlyer (URLs de impresión), puedes atribuir las aplicaciones de una plataforma a las vistas de anuncios que se muestran en otra plataforma. Varias instalaciones dentro del mismo hogar se pueden atribuir a la misma impresión de anuncios multiplataforma.

<div id="how-does-the-attribution-logic-work" />

### ¿Cómo funciona la lógica de atribución?

* Las impresiones se identifican en AppsFlyer por el ID de su plantilla OneLink y se asignan a cada plataforma configurada en la plantilla.
* Las instalaciones se identifican por su app y plataforma.
* Lógica de coincidencia: las impresiones a nivel de plantilla se asignan al inicio específico de la aplicación mediante atribución probabilística. Se puede asociar cualquier variante de la app del grupo.

<div id="create-a-onelink-templatefor-cross-platform-attribution" />

## Crea o edita una plantilla de OneLink para la atribución multiplataforma.

Una sola plantilla admite tu aplicación en múltiples plataformas (lo que significa que una plantilla funciona en todas las plataformas). En la plantilla, configuras juntas todas las variantes de plataforma de tu aplicación (móvil, CTV, escritorio, consola).

1. Crea o edita una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">plantilla de OneLink</Anchor> para la atribución multiplataforma.
2. En la sección **atribución multiplataforma**, haz clic en el **botón de editar ->** **Habilitar atribución multiplataforma**
3. Desde los menús desplegables de la plataforma relevante, selecciona la aplicación correspondiente. **Nota**: Cada aplicación solo puede añadirse a una plantilla de OneLink con la atribución multiplataforma habilitada. [<Image alt="Atribución multiplataforma.png" src="https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png" width="476px" />](https://files.readme.io/181eae8e98b26321c8aa46bab296f492ba543d645b4659af21e91fe976c08feb-24170762165521.png)

<div id="set-up-cross-platform-partner-integration" />

## Configura la integración de partners multiplataforma

Para configurar la atribución multiplataforma utilizando URLs de impresión multiplataforma, configura la integración de partners para cada aplicación objetivo.

<div id="important" />

> 🚧 **¡Importante!**
>
> Asegúrate de habilitar la integración de partners realizando los pasos a continuación para todas las aplicaciones objetivo que seleccionaste en la plantilla de OneLink (ver la [sección anterior](#crea-o-edita-una-plantilla-de-onelink-para-la-atribución-multiplataforma)). Si la integración está deshabilitada para una de las aplicaciones objetivo, la atribución multiplataforma no ocurrirá.

<div id="h_01K2HBXDWSG3R1WZXT5RB0W48D" />

<Accordion title="Paso 1: Selecciona la aplicación objetivo de la integración de partner">

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de Partners** > **Integraciones activas**
2. Selecciona el partner integrado.
3. En la pestaña **Integración**, desde el cuadro desplegable **Aplicación**, selecciona la aplicación objetivo.

</Accordion>

<div id="step-2-enable-viewthrough-attribution" />

<Accordion title="Paso 2: Habilitar la atribución view-through">

Para que los enlaces sean utilizados por los partners integrados, habilita la atribución view-through.

1. En la pestaña **Integración**, activa **Atribución de instalaciones view-through**.
2. Haz clic en **Guardar integración**.

</Accordion>

<div id="step-4-create-an-attribution-link-crossplatform-impression-url" />

<Accordion title="Paso 3: Crea un enlace de atribución (URL de impresiones multiplataforma).">

Para crear un <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">enlace de atribución</Anchor> (URL de impresión multiplataforma) para redes integradas

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de Partners** > **Integraciones activas** y elige el partner integrado.
2. En la pestaña **Enlace de atribución**, al crear un <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">enlace de OneLink</Anchor>, selecciona Usar OneLink.
3. Selecciona la plantilla de OneLink que has creado para la atribución multiplataformas.
4. Desplázate hacia abajo hasta **Atribución view-through**.[![](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)](https://files.readme.io/0db03066a7f7c14c68d36a019d9791dfea44e6df3e8f5bdb6f5e4b71d5e78a08-12602245845649.png)
5. Activa la **Atribución multiplataformas**. Esto añade el parámetro `af_xplatform=true` al enlace de atribución de impresión y le da al enlace capacidades de atribución multiplataforma. Sin este parámetro, la URL funciona como una URL de impresión normal que no puede atribuir varias instalaciones a la misma impresión.
6. Configura la **ventana de lookback de atribución view-through multiplataforma**. Esto agrega el parámetro `af_xplatform_vt_lookback` al enlace de atribución de impresiones e indica la cantidad de horas (hasta 72) después de la impresión durante la cual la instalación de la aplicación se puede atribuir a la impresión.
7. Agrega cualquier parámetro de atribución adicional según sea necesario. Utiliza convenciones de nomenclatura que identifiquen tu campaña de aplicación multiplataforma. <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más</Anchor> sobre los parámetros que puedes agregar para obtener datos y métricas adicionales. Enlace de muestra:

   ```http
   https://impressions.onelink.me/{template_id}?pid=__media_source__&af_xplatform=true&af_xplatform_vt_lookback=24h&af_siteid=__CSITE__&c=__ctv_to_mobile__&af_channel=__PLACEMENT__&af_c_id=__CAMPAIGN_ID__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_source_platform=__source_platform__&af_source_device_category=__device_category__&af_ad_type=__CTYPE__&redirect=false
   ```
8. Proporciona el enlace a la ad network para colocarlo detrás del anuncio que se muestra en plataformas CTV, PC o consola.

<div id="important-1" />

> 🚧 **¡Importante!**
>
> Para medios propios y partners no integrados, añade parámetros según sea necesario.  <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más</Anchor> sobre los parámetros que puedes agregar para obtener datos y métricas adicionales.

</Accordion>

<div id="equal-priority-advanced-setting" />

<Accordion title="Avanzado: Configuración de prioridad igual (opcional)">

Opcionalmente, puedes asignar la **misma prioridad** a los clics e impresiones en la atribución multiplataforma. Esta configuración avanzada permite a AppsFlyer tratar las impresiones (por ejemplo, en CTV o consolas) como si tuvieran la misma prioridad de atribución que los clics. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#prioridades-de-los-métodos-de-atribución-cascada-de-atribución">Prioridades del método de atribución</Anchor>.

**Para habilitar la prioridad igual:**

1. En la sección de configuración multiplataforma, selecciona la casilla **Misma prioridad**.
2. Haz clic en **Guardar**.

<div id="note" />

> 📘 **Nota**
>
> Habilitar la prioridad igual puede hacer que AppsFlyer priorice su propia atribución sobre otras fuentes. Utiliza esta configuración con precaución y solo si se alinea con tu estrategia general de atribución.

</Accordion>

<div id="traits-and-limitations" />

## Características y limitaciones

| Caducado | Observaciones |
| --- | --- |
| <span id="attribution-window"></span>Ventana de atribución | Entre 1 y 72 horas, dependiendo del parámetro de ventana de lookback `af_xplatform_vt_lookback` (el valor predeterminado es de 24 horas). |
| <span id="retargeting"></span>Reorientación | <ul><li>Reatribución: Compatible con cross-platform-to-mobile. No para otras plataformas.</li><li>Reengagement: No compatible</li></ul> |
| <span id="attribution-method"></span>Método de atribución | Atribución por impresiones mediante el modelado probabilístico |
| <span id="household-attribution"></span>Atribución por hogar | Compatible. Lo que significa que varias instalaciones dentro del mismo hogar se pueden atribuir a la misma impresión de anuncios multiplataforma. |
| <span id="reporting"></span>Reportes | <ul><li>Las instalaciones multiplataforma están disponibles en los dashboards y reportes regulares de AppsFlyer:<ul><li>Datos agregados, <Anchor target="_blank" href="/marketers/es/docs/getting-started-with-appsflyer-dashboards">dashboards</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview">reportes</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">Reportes</Anchor> de raw data</li></ul></li><li>Las impresiones multiplataforma no se muestran en los dashboards a nivel de aplicación. Sin embargo, están disponibles en el <Anchor target="_blank" href="/marketers/es/docs/data-locker-advertiser-reports#user-journey">reporte de engagements multiplataforma</Anchor> a través de Data Locker.</li><li>Asegúrate de usar convenciones de nomenclatura de parámetros que identifiquen fácilmente tu campaña multiplataforma.</li></ul> |
| <span id="ip-masking"></span>Enmascaramiento de IP | No se admite el enmascaramiento de IP para engagements multiplataforma, ya que es una característica a nivel de aplicación. Si `ip_masking` está configurado, la instalación no se atribuirá al engagement multiplataforma. |
| <span id="ctvto-mobile"></span>CTV-to-mobile | Los flujos de atribución de CTV-to-mobile están disponibles solo para [partners integrados](/docs/set-up-cross-platform-links-for-multi-device-campaigns#list-of-ad-networks) que tienen la autorización para realizar campañas multiplataforma. |
| <span id="cross-platform-attribution-links-in-mobile-devices"></span>Enlaces de atribución multiplataforma en dispositivos móviles | Cuando se visualiza un enlace de atribución multiplataforma en un dispositivo móvil, la atribución se determina por la lógica estándar de modelado probabilístico móvil, no por el flujo de atribución multiplataforma diseñado para <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#tv-screens">CTV</Anchor>, PC y consolas. En consecuencia, las impresiones móviles no serán elegibles para la [misma prioridad](#step-3-enable-equal-priority-for-crossplatform-impressions), [ventana de lookback extendida](#attribution-window) o [atribución por hogar](#household-attribution) que está disponible para impresiones genuinas multiplataforma. |
| <span id="agency-permissions"></span>Permisos de la agencia | Las agencias no pueden activar ni desactivar la "Misma prioridad de atribución multiplataforma" desde su lado. Esta configuración se copia directamente de la configuración del anunciante para la ad network específica. |

<div id="discrepancies" />

## Discrepancias

AppsFlyer y tvScientific difieren en sus modelos de atribución. Esto puede hacer que surjan discrepancias entre los dashboards de tvScientific y de AppsFlyer. Consulta las razones de las discrepancias en la siguiente tabla:

| Causa | tvScientific | AppsFlyer |
| --- | --- | --- |
| Modelo de referencia | Modelo de atribución de crédito compartido | Modelo de atribución de último toque |
| Ventana de lookback | Hasta 30 días | Hasta 72 horas |
| Reorientación | Atribución tanto de nuevos usuarios (instalaciones) como de usuarios que regresan (re-engagements) | Atribución solo de nuevos usuarios (instalaciones) |
| Asignación de costos | El costo se asigna a la impresión independientemente del sistema operativo | El costo se asigna a la impresión en sistemas separados para iOS y Android |

<div id="faq" />

## Preguntas frecuentes

<div id="does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on" />

<Accordion title="¿Es necesario habilitar la atribución por impresiones a través del modelado probabilístico?">

N.º La opción de habilitar la atribución por impresiones a través del modelado probabilístico de la configuración de tu aplicación no necesita estar activada para que funcione la atribución por impresiones multiplataforma.

</Accordion>

<div id="why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />

<Accordion title="¿Por qué no veo impresiones para mis campañas multiplataforma en el dashboard?">

Las impresiones multiplataforma no se muestran en los dashboards a nivel de aplicación. Esto se debe a que una impresión de CTV puede llevar a múltiples conversiones en diferentes aplicaciones, y no hay una forma precisa de asignar impresiones a cada aplicación. Puede acceder a los datos de impresiones en el <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-data-via-data-locker#tipos-de-reportes-y-disponibilidad">Reporte de engagements multiplataforma en Data Locker</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=descripci%C3%B3n-general 01H8V0RV7X8JEVEJ36TJB1X43D=descripci%C3%B3n-general app-group-vs-individual-app-%E2%80%93-attribution-logic=c%C3%B3mo-funciona-la-l%C3%B3gica-de-atribuci%C3%B3n h_01KANVNVCY6JFTJ1SVK3DGM54C=c%C3%B3mo-funciona-la-l%C3%B3gica-de-atribuci%C3%B3n step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution=crea-o-edita-una-plantilla-de-onelink-para-la-atribuci%C3%B3n-multiplataforma h_01HVECG1TZ8B5GH28CZM2186BF=crea-o-edita-una-plantilla-de-onelink-para-la-atribuci%C3%B3n-multiplataforma set-up-crossplatform-attribution=configura-la-integraci%C3%B3n-de-partners-multiplataforma h_01HVECG1TZSDTP0WBG7XYM509G=configura-la-integraci%C3%B3n-de-partners-multiplataforma 01JEKG3V0C75G782RC7CE9DAV2=importante h_01HVECG1TZKNG17STSN5XJAF9C=step-2-enable-viewthrough-attribution step-4-create-an%C2%A0attribution-link%C2%A0crossplatform-impression-url=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ6WP257R9D8A105FR=step-4-create-an-attribution-link-crossplatform-impression-url h_01HVECG1TZ3K1EFA22716K2B9X=importante-1 h_01K2HBZKX0EJHSVCXJJ97NMVXZ=equal-priority-advanced-setting equal-priority-impact-note=nota h_01K2HBZKX0ECJPTQMPPXC3JBVC=nota traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01HVED5DJPFR5XCWYDSYCHMCR6=caracter%C3%ADsticas-y-limitaciones discrepancies=discrepancias h_01HVED5DJPMP3AQDTN3GM77T2F=discrepancias faq=preguntas-frecuentes h_01HVED5DJPBPDSZ0AAY1RG8NEZ=preguntas-frecuentes h_01K4AC2J63B4MBTDGZHH7ACRCG=does-enable-viewthrough-attribution-via-probabilistic-modeling-need-to-be-turned-on why-don%E2%80%99t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard h_01K4AC2J63KBF8X20DMNPW1GTK=why-don-t-i-see-impressions-for-my-crossplatform-campaigns-in-the-dashboard" />

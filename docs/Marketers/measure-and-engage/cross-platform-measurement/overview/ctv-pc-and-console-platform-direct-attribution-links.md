---
title: Enlaces de atribución directa de plataforma CTV, PC y consola
metadata:
  keywords:
    - Advertiser
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2023-05-10T10:21:14Z'
  edited_at: '2026-10-20T03:44:24Z'
  id: 15199908310801
  locale: es
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/es/articles/15199908310801
---
> **En resumen:**  Aprende sobre la estructura y los parámetros del enlace de atribución de AppsFlyer para las plataformas de CTV, PC y consola. **Nota**: Para aplicaciones de Android e iOS, incluidos los juegos de PC Android, sigue las <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">instrucciones del enlace de atribución móvil</Anchor>.

## General

Los enlaces de atribución directa de plataformas CTV, PC y consola permiten a los anunciantes redireccionar a los usuarios y recopilar datos después de los clics. Estos enlaces de atribución directa son enlaces de AppsFlyer que admiten la redirección y la atribución **de una sola aplicación de destino en una sola plataforma a la vez**. El destino de la redirección es el valor del parámetro af\_r incluido en el enlace.

**Nota**: Para aplicaciones de Android e iOS, incluidos los juegos de PC Android, sigue las <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">instrucciones del enlace de atribución móvil</Anchor>.

Puedes crear enlaces de atribución directamente y colocarlos detrás de los anuncios. Para crear dichos enlaces, sigue las instrucciones de este artículo.

Alternativamente, se pueden crear enlaces a través de S2S utilizando la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_click-app-platform-app-id">API de Engagements</Anchor>. Esto requiere algo de trabajo de desarrollo. **Nota**: Los enlaces creados a través de S2S también pueden recopilar datos de impresiones.

### Enlace de atribución

| Propiedad | Valores |
| --- | --- |
| URL base | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Parámetros de ruta obligatorios | <ul><li>platform<br />Ejemplo: steam</li><li>app\_id<br />Ejemplo: 123456</li></ul> |
| Parámetros obligatorios de la consulta | <ul><li>media\_source</li><li>af\_campaign\_id</li></ul> |
| Otros parámetros | [Ver todos los parámetros](/docs/ctv-pc-and-console-platform-direct-attribution-links#parámetros) |
| Estructura de URL | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |
| URL de muestra | `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=aloha&af_campaign_id=1234&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello` |

### Parámetros

| Parámetro | Nombre para mostrar en exportación de raw data y en API Pull | Descripción | Tipo de dato |
| --- | --- | --- | --- |
| Identificador de origen | Plataforma | <ul><li>Parámetro de ruta que especifica la plataforma de la aplicación.</li><li>Posibles valores:<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>steam</li><li>quest</li><li>battlenet</li><li>epic</li><li>switch</li><li>xbox</li><li>nativepc</li></ul></li></ul> | Cadena |
| id\_aplicación | ID de aplicación | <ul><li>Parámetro de ruta que especifica el ID de la aplicación para la que estás publicando.</li><li>Ejemplo: `ap123456`</li><li>No agregues un prefijo de plataforma al valor de ID de aplicación. Por ejemplo, si el ID de aplicación es `ap123456` y la plataforma es `platformX`, no uses `platformX_ap123456` como valor de `app_id`.</li></ul> | Cadena |
| media\_source | Fuente de medios | Este es el identificador de parter único según se define en la plataforma de AppsFlyer.  <br />No se permiten los siguientes caracteres especiales: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %. | Cadena |
| af\_campaign | Campaña | Nombre de la campaña | Cadena |
| af\_campaign\_id | ID de campaña | ID de campaña | Cadena |
| af\_request\_id | N/D | Identificador que identifica de forma única una solicitud de un socio. | Cadena |
| af\_conjunto de anuncios | Conjunto de anuncios | Nombre del conjunto de anuncios | Cadena |
| af\_adset\_id | ID del conjunto de anuncios | ID del conjunto de anuncios | Cadena |
| af\_anuncio | Anuncio | Nombre del anuncio | Cadena |
| id\_del\_anuncio\_af | ID del anuncio | ID del anuncio | Cadena |
| af\_campaign\_type | Tipo de campaña | Elige entre:<ul><li>user\_acquisition</li><li>redireccionamiento</li></ul> | Cadena |
| af\_prt | Fuente de medios | <ul><li>Nombre de la cuenta de la agencia que permite atribuir instalaciones a la agencia</li><li>**¡Importante!** No uses este parámetro antes de asegurarte de que los **permisos de la agencia** estén habilitados.</li></ul> | Cadena |
| af\_siteid | ID del sitio | <span id="query-getImpressionAppPlatformApp_id_af_siteid__description"></span>ID único que identifica al publisher que muestra el anuncio. | Cadena |
| af\_sub\_siteid | ID del subsitio | <span id="query-getImpressionAppPlatformApp_id_af_sub_siteid__description"></span>ID de anunciante/subred de publicidad. | Cadena |
| af\_click\_id | N/D | <span id="query-getImpressionAppPlatformApp_id_af_click_id__description"></span>Identificador de transacción único de la red publicitaria | Cadena |
| af\_lookback\_window | N/D | <ul><li>Número configurable de días/horas para el período de atribución de la ventana de lookback. Valores de parámetro disponibles:<ul><li>Clics: 1d-7d (días).</li><li>Impresiones: 1d-7d (días) O 1h-23h (horas).</li></ul></li><li>Validación: 3 caracteres como máximo, utilizando el esquema anterior.</li><li>Validación: 3 caracteres como máximo, utilizando el esquema anterior.</li></ul> | Cadena |
| af\_ad\_placement | N/D | <span id="query-getImpressionAppPlatformApp_id_af_ad_placement__description"></span>Identificador de transacción único de la red publicitaria | Cadena |
| af\_ad\_type | Tipo de anuncio | <ul><li>Tipo de anuncio. Usa la siguiente convención de nomenclatura:<ul><li>**text:** una unidad de anuncio que contiene solo texto, por ejemplo, un resultado de búsqueda.</li><li>**banner:** un formato básico que aparece en la parte superior o inferior de la pantalla del dispositivo.</li><li>**interstitial:** un anuncio de página completa que aparece durante los descansos en la experiencia actual.</li><li>**video:** un video estándar, es decir, no recompensado.</li><li>**rewarded\_video:** una unidad de anuncio que ofrece recompensas in-app a cambio de ver un video.</li><li>**playable:** una unidad de anuncio que contiene una vista previa interactiva de la experiencia de la aplicación.</li><li>**audio:** un anuncio de audio.</li></ul></li><li>Distingue entre mayúsculas y minúsculas.</li></ul> | Cadena |
| af\_canal | Canal | <span id="query-getImpressionAppPlatformApp_id_af_channel__description"></span>El canal de origen de medios a través del cual se distribuyen los anuncios, por ejemplo, UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | Cadena |
| af\_model | Modelo del dispositivo | Modelo del dispositivo | Cadena 64 |
| af\_os\_version | N/D | <ul><li>Versión del sistema operativo del dispositivo</li><li>Solo se permiten dígitos y puntos</li><li>Ejemplo: 8.1.0</li></ul> | Cadena |
| af\_device\_id\_type | N/D | <span id="query-getImpressionAppPlatformApp_id_af_device_id_type__description"></span>Tipo de identificador de dispositivo. Elige entre:<ul><li>VIDA</li><li>TIFA</li><li>rida</li><li>lgudid</li><li>fire</li><li>advertising\_id</li><li>fire</li><li>custom</li></ul> | Cadena |
| af\_device\_id\_value | N/D | <span id="query-getImpressionAppPlatformApp_id_af_device_id_value__description"></span>Tipo de identificador de dispositivo | Cadena |
| af\_r | N/D | <ul><li>Contiene el enlace a la tienda de aplicaciones o landing page correcta.</li><li>Todo dentro del parámetro af\_r debe estar codificado. Esto incluye cualquier valor de parámetro UTM, si se adjunta.</li></ul>**Nota:** Asegúrate de que el dominio URL de af\_r esté incluido en tu <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">lista de redireccionamientos permitidos</Anchor>. | Cadena |

## Rasgos y limitaciones

| Rasgo | Comentarios |
| --- | --- |
| Atribución de agencia | <ul><li>Flujo de CTV-PC-consola a móvil: se admite la atribución de agencia.</li><li>Flujo de móvil a CTV-PC-consola: no se admite la atribución de agencia.</li></ul> |

<div data-zendesk-anchors="overview=general 01H7Z1003GTTMRY072BXWDFNP0=general attribution-link=enlace-de-atribuci%C3%B3n 01H7Z1003G0WYBCK3530064WM1=enlace-de-atribuci%C3%B3n attribution-link-parameters=par%C3%A1metros 01H7Z1003GNC551PDCKKFQMPVN=par%C3%A1metros traits-and-limitations=rasgos-y-limitaciones h_01HVED5DJPFR5XCWYDSYCHMCR6=rasgos-y-limitaciones" />

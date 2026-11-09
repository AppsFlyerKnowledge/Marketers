---
title: Discrepancias de atribución entre AppsFlyer y las tiendas de aplicaciones
metadata:
  keywords:
    - Google Play
    - AppsFlyer
    - iTunes
    - installs
    - Discrepancies
    - App Stre
    - Compare
    - Account
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T12:52:53Z'
  edited_at: '2026-08-12T11:57:14Z'
  id: 207040726
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/207040726
---
> **De un vistazo**: Encuentra las principales causas de las discrepancias de atribución entre AppsFlyer y las tiendas de aplicaciones, así como consejos para minimizar dichas discrepancias.

<div id="attribution-discrepancies" />

## Discrepancias de atribución

Existen diferencias inherentes en los modelos de atribución utilizados por todos los actores del ecosistema de la atribución móvil. Lo mismo aplica a AppsFlyer y a las principales tiendas de aplicaciones: App Store (iOS) y Google Play (Android). **Nota**: En este artículo, las dos tiendas se denominan "tienda de aplicaciones" o "tiendas de aplicaciones".

Debido a las diferencias en los modelos de atribución, en algunos casos, la tienda de aplicaciones registra más instalaciones que AppsFlyer. En otros casos, AppsFlyer registra más instalaciones que la tienda de aplicaciones.

<Image align="center" alt="AF_vs_app_stores.png" src="https://files.readme.io/6f81aac30cdf1ab2331cd08e7a221c154e1f7104c15d47c47690baabaace856a-34114275895825.png" width="605px" />

<div id="note" />

> 📘 **Nota**
>
> Las discrepancias no afectan la precisión del recuento de instalaciones **no orgánicas** porque el modelo de atribución de AppsFlyer acredita una instalación por cada clic en el anuncio. Esto es cierto incluso para un usuario específico con más de un dispositivo registrado en la tienda de aplicaciones.

<div id="why-appsflyer-attributes-less" />

### Por qué AppsFlyer atribuye menos

Los siguientes son motivos para la subatribución por parte de AppsFlyer:

| Causa | Tiendas de aplicaciones | AppsFlyer | Consejo de AppsFlyer |
| --- | --- | --- | --- |
| **Definiciones de la instalación** | Las tiendas de aplicaciones registran las instalaciones después de que el usuario descarga e instala la aplicación, ya sea que el usuario la inicie más tarde o no. | AppsFlyer registra instalaciones nuevas solo después del primer inicio.<br /><br />**AppsFlyer no cuenta los usuarios que nunca iniciaron la aplicación**, aunque la descarguen e instalen (según la definición de la tienda de aplicaciones). | Alrededor del 90 % de las descargas de aplicaciones móviles resultan en al menos un inicio, pero esto puede variar significativamente en diferentes geolocalizaciones y verticales. |
| **Fecha de registro de la instalación** | Las tiendas de aplicaciones registran la fecha de la descarga como el día de la instalación. | AppsFlyer registra la fecha del primer inicio como el día de la instalación. | En AppsFlyer, utiliza periodos de tiempo más largos como tu rango de fechas consultadas para minimizar esta discrepancia. |
| **Zonas horarias** | Los datos se muestran según la zona horaria local del anunciante. | De forma predeterminada, los datos se muestran usando la zona horaria UTC±00:00. | Puedes configurar la zona horaria preferida de la aplicación para reducir esta discrepancia <Anchor target="_blank" href="/marketers/es/docs/changing-app-time-zone-settings">(encuentra detalles aquí</Anchor>). |
| **El usuario de Android desinstala y vuelve a instalar dentro de la ventana de reatribución definida** | En algunas vistas, Google Play muestra **dos** **instalaciones únicas** para el mismo usuario, independientemente del tiempo transcurrido desde la primera instalación. Otras vistas muestran los **usuarios únicos** y, por lo tanto, están más alineadas con AppsFlyer. | Dentro de la ventana de reatribución (por defecto 3 meses) desde el momento de la instalación original, el usuario no se considera como nuevo en AppsFlyer cuando vuelve a instalar. | Puedes <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">establecer la ventana de reatribución</Anchor> de 1 a 24 meses. |
| **El usuario de iOS desinstala y vuelve a instalar dentro de la ventana de reatribución definida** | iTunes cuenta una instalación nueva cada vez que el usuario desinstala y vuelve a instalar. | Dentro de la ventana de reatribución (por defecto 3 meses) desde el momento de la instalación original, el usuario no se considera como nuevo en AppsFlyer cuando vuelve a instalar. | Puedes <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">establecer la ventana de reatribución</Anchor> de 1 a 24 meses. |

<div id="why-appsflyer-attributes-more" />

### Por qué AppsFlyer atribuye más

Los siguientes son motivos para la sobreatribución por parte de AppsFlyer:

| Causa | Tiendas de aplicaciones | AppsFlyer | Consejo de AppsFlyer |
| --- | --- | --- | --- |
| **Actualizar una instalación de aplicación existente de una versión que no contenía el SDK de AppsFlyer a una versión que contiene el SDK de AppsFlyer** | Las tiendas de aplicaciones consideran esto como el mismo usuario; no como una instalación nueva. | AppsFlyer muestra la actualización como instalaciones orgánicas. | <ul><li>Este pico suele caer después de unos días, ya que la mayoría de los usuarios terminan de actualizar la aplicación.</li><li>Las cuentas nuevas pueden desear <Anchor target="_blank" href="/marketers/es/docs/migration-to-appsflyer-from-other-vendors#migración-de-dispositivosopcional">migrar sus usuarios actuales</Anchor> a AppsFlyer para evitar este pico.</li></ul> |
| **Restablecer el ID del dispositivo y fraude de rastreo de anuncios limitado** | Las tiendas de aplicaciones consideran esto como el mismo usuario; no como una instalación nueva. | AppsFlyer lo ve como una instalación nueva en un dispositivo nuevo. | La <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide">solución contra el fraude Protect360</Anchor> de AppsFlyer detecta si tu aplicación sufre este tipo de fraude. |
| **Instalaciones que provienen de <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">mercados fuera de la tienda</Anchor> e <Anchor target="_blank" href="/marketers/es/docs/appsflyer-factory-preinstall-using-manifest-android">instalaciones previas</Anchor>** | Google Play no registra estas instalaciones. | AppsFlyer cuenta estas instalaciones. | Si publicitas en un <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">mercado Android fuera de la tienda</Anchor>, consulta la documentación para la configuración correcta. |
| **El usuario de Android desinstala y vuelve a instalar después de que venza la ventana de reatribución definida** | En algunas vistas, Google Play muestra usuarios únicos (independientemente del tiempo transcurrido desde la primera instalación), mientras que otras vistas muestran dos instalaciones únicas para el mismo usuario y, por lo tanto, están más alineadas con AppsFlyer. | Una vez que expira la ventana de reatribución (3 meses de forma predeterminada), la reinstalación se considera una nueva instalación normal en AppsFlyer. Esto significa que el mismo usuario se contabiliza dos veces. | Puedes <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">establecer la ventana de reatribución</Anchor> de 1 a 24 meses. |

<div data-zendesk-anchors="attribution-discrepancies=discrepancias-de-atribuci%C3%B3n h_01HNWP7A6GQC5ZX6WKBW411DVG=discrepancias-de-atribuci%C3%B3n h_01HNWP7A6GZJS246548Q5AFPZR=nota why-appsflyer-attributes-less=por-qu%C3%A9-appsflyer-atribuye-menos h_01HNWP7A6G85PR1R66Q3KCRPNW=por-qu%C3%A9-appsflyer-atribuye-menos why-appsflyer-attributes-more=por-qu%C3%A9-appsflyer-atribuye-m%C3%A1s h_01HNWP7A6GVVWMV6HECXQFTJT6=por-qu%C3%A9-appsflyer-atribuye-m%C3%A1s" />

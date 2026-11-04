---
title: Atribución de referencias de precarga de AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2022-03-02T09:54:10Z'
  edited_at: '2026-09-17T00:09:40Z'
  id: 4543811207313
  locale: es
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/es/articles/4543811207313
---
> **A simple vista:** AppsFlyer utiliza la referencia de precarga para atribuir las instalaciones a las campañas de precarga, donde los marketers contratan a fabricantes de equipos originales (OEM), operadores móviles y partners de descubrimiento de aplicaciones para precargar su aplicación en la fábrica o en el momento en que el usuario enciende el dispositivo por primera vez.

<div id="overview" />

## Visión general

En las campañas de precarga, los fabricantes de dispositivos originales (OEM), los operadores móviles y los partners de descubrimiento de aplicaciones precargan las aplicaciones en los dispositivos antes de que lleguen al usuario. Esto puede ser realizado por el OEM en la fábrica o por los proveedores al momento de la activación del primer dispositivo.

Las campañas de precarga permiten a los anunciantes llegar a una audiencia potencialmente grande sin ejecutar campañas en línea.

La atribución de referencia de precarga (1 de 3 <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#preload-campaigns">métodos de atribución de precarga</Anchor>) brinda a los marketers un mecanismo preciso y que preserva la privacidad para medir el rendimiento de las campañas de precarga. Este método proporciona a los marketers resultados de atribución deterministas, garantizando al mismo tiempo que se mantenga la privacidad del usuario, ya que la atribución se realiza a través de la coincidencia de referencia con una referencia generada independientemente del dispositivo y los identificadores de usuario.

La solución proporciona:

* Soporte transparente para las actualizaciones de las aplicaciones y las redescargas de las mismas.
* Capacidades de visibilidad y medición entre la primera activación del dispositivo y el primer inicio de la aplicación. Esto te permite ver cuántos dispositivos fueron activados con la aplicación precargada por un partner específico y luego observar cuándo se lanza la aplicación por primera vez.

<div id="partners-supporting-preload-referrer-campaigns" />

## Partners que soportan las campañas de referencia de precarga

La información en este artículo es relevante para los anunciantes que están integrados con los partners especificados en la siguiente tabla:

<table><thead><tr><th rowspan="2">Fuente de medios</th><th rowspan="2">PID no integrados.</th><th colspan="2">Opciones de campaña de referencia de precarga <a href="./set-up-appsflyer-preload-referrer-attribution#opciones-de-referencia-de-precarga"><span>Saber más</span></a> </th></tr><tr><th>Precarga</th><th>Click-to-download</th></tr></thead><tbody><tr><td><a href="#referencia-de-precarga-de-samsung">Samsung</a></td><td>samsung_int</td><td><span>✓</span></td><td> </td></tr><tr><td>Digital Turbine On Device</td><td>digitalturbine_int</td><td><span>✓</span></td><td>En breve</td></tr><tr><td>Aura de Unity</td><td>aura_int</td><td><span>✓</span></td><td>En breve</td></tr><tr><td>Appnext</td><td>appnext_int</td><td><span>✓</span></td><td>En breve</td></tr><tr><td>Glance<br/> </td><td>glance_int</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

<div id="preload-referrer-options" />

## Opciones de referencia de precarga

Las referencias se pueden utilizar para atribuir las instalaciones por precarga o por click-to-download. Consulta la siguiente tabla para obtener más información.

AppsFlyer da la mayor prioridad a la atribución de precarga. Esto significa que si un usuario participa en otras campañas antes de abrir la aplicación por primera vez, la campaña de precarga recibe la atribución. Otros engagements se consideran instalaciones asistidas. **Nota**: Puedes habilitarla prioridad igual para los engagements de precarga. Esto da a los engagements de precarga la misma prioridad de atribución que los clicsdeterministas para toda la ventana de lookback de precarga, por lo que la atribución a la campaña de precarga no puede ser reemplazada por otro engagement publicitario.

| Opción de referencia | Descripción | Tipo de coincidencia del raw data de instalaciones de UA |
| --- | --- | --- |
| Precarga | <ul><li>La aplicación se precargó en la fábrica o se precargó la primera vez que se activó el dispositivo. Alternativamente, un asistente pide a los usuarios que descarguen la aplicación cuando el dispositivo se activa por primera vez.</li><li>Un evento de precarga, equivalente a un clic, se comunica a AppsFlyer cuando el dispositivo se enciende por primera vez.</li><li>La atribución se produce cuando el usuario abre la aplicación por primera vez.</li><li>El evento de precarga tiene la prioridad de atribución más alta (a menos que se haya activado la misma prioridad de atribución).</li></ul> | `preload_rfr` |
| Click-to-download | <ul><li>La instalación de la aplicación se llevará a cabo más tarde en el ciclo de vida del dispositivo a través de push notifications, tiendas alternativas de partners, etc.</li><li>Cuando el usuario interactúa con un anuncio o con un mensaje push notification, la aplicación se descarga e instala automáticamente en el dispositivo sin redireccionar a la tienda.</li><li>La atribución se otorga utilizando las reglas de último clic de AppsFlyer.</li></ul> | `af_referrer` |

<div id="view-preload-attribution-data" />

## Ver datos de atribución de precarga

La precarga/clic para descargar los datos de rendimiento de la campaña de engagement está disponible de la siguiente manera:

* **Dashboard general:** Los engagements cuentan como clics en los reportes y dashboards agregados. Se agregan a nivel de partner de precarga (fuente de medios) y campaña.
* **Raw data:** Las interacciones están disponibles en los reportes de clics disponibles solo a través de Data Locker. Se encuentran en el campo de URL original y se pueden identificar en el parámetro af\_engagement\_type como precarga o click\_to\_download. Para las instalaciones, consulta la tabla en la sección anterior para ver cómo se muestra el tipo de coincidencia en raw data.

<div id="set-up-preload-referrer-attribution" />

## Configurar la atribución de referencias de precarga

**Requisitos previos:**

* Integra el <Anchor target="_blank" href="/marketers/es/docs/appsflyer-android-sdk-release-notes">SDK de AppsFlyer para Android 6.10.1+</Anchor>.
* Contrata a un partner de precarga de AppsFlyer.

**Para configurar la atribución del remitente de precarga**:

1. En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > **Integraciones activas**.
2. Selecciona el partner de precarga.
3. En la pestaña **Integración**, activa **Atribución de precarga**.  
   [<Image alt="" src="https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png" width="538px" />](https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png)
4. **Establece la duración de la ventana de lookback de precarga**. Intervalo: 1-180 días
5. [Opcional] Activa **Igual prioridad de atribución de precarga.**.  
    Esto le da a los clics deterministas la misma prioridad de atribución que a la atribución de precarga, lo que significa que si se registra un clic determinista entre el engagement de la referencia de precarga y la instalación, el clic obtiene la atribución bajo la lógica de atribución estándar de último toque, en lugar de ser reemplazado por la referencia de precarga.
6. Haz clic en **Guardar integración**.
7. Informa al partner de precarga de que estás listo para atribuir sus campañas.

<div id="samsung-preload-referrer" />

## Referencia de precarga de Samsung

La integración de referencia de precarga de Samsung con AppsFlyer te proporciona una visibilidad detallada desde la descarga inicial de la aplicación hasta el primer lanzamiento, lo que permite una comprensión más clara del comportamiento del usuario.

<div id="set-up-samsung-preload-referrer-attribution" />

### Configurar la atribución de referencias de precarga de Samsung

Para configurar la atribución de referencia de precarga de Samsung, consulta las [instrucciones generales para las referencias de precarga](#configurar-la-atribución-de-referencias-de-precarga).

<div id="traits-and-limitations" />

### Rasgos y limitaciones

Los rasgos específicos de la referencia de precarga de Samsung son los siguientes:

| Caducado | Observaciones |
| --- | --- |
| Nombre de la integración | samsung\_int |
| Versión del SDK | v6.16.0 |
| Tipo de coincidencia | `preload_rfr` |
| Dashboard general | Los engagements cuentan como clics en los reportes agregados y dashboards. Se agregan a nivel de partner de precarga (fuente de medios) y campaña. |
| Reportes de raw data | <ul><li>Los engagements están disponibles en los reportes de clics solo a través de Data Locker.</li><li>En los reportes de instalación, los eventos de precarga NO se encuentran en la URL original debido a las restricciones de privacidad de Samsung.</li><li>Pueden identificarse en el parámetro `af_engagement_type` como `preload`.</li></ul> |

<div data-zendesk-anchors="appsflyer-preload-referrer-attribution=visi%C3%B3n-general h_01HEKAF7K41PH189PSCKBRF070=visi%C3%B3n-general partners-supporting-preload-referrer-campaigns=partners-que-soportan-las-campa%C3%B1as-de-referencia-de-precarga h_01HEKAF7K5CWX2P9TY8M0MTQAM=partners-que-soportan-las-campa%C3%B1as-de-referencia-de-precarga preload-referrer-options=opciones-de-referencia-de-precarga h_01HEKAF7K4H3HNAMEYM6C58Y29=opciones-de-referencia-de-precarga view-preload-attribution-data=ver-datos-de-atribuci%C3%B3n-de-precarga h_01HEKAF7K4GJDDPHCFTTC75YBS=ver-datos-de-atribuci%C3%B3n-de-precarga set-up-preload-referrer-attribution=configurar-la-atribuci%C3%B3n-de-referencias-de-precarga h_01HEKAF7K41RBRVXC6GF6PCN3Y=configurar-la-atribuci%C3%B3n-de-referencias-de-precarga samsung-preload-referrer=referencia-de-precarga-de-samsung h_01JCB6K81QRK2NM983SJBYD9M3=referencia-de-precarga-de-samsung set-up-samsung-preload-referrer-attribution=configurar-la-atribuci%C3%B3n-de-referencias-de-precarga-de-samsung h_01M2JCPMNY1ZACWQTDDGZCF2X9=configurar-la-atribuci%C3%B3n-de-referencias-de-precarga-de-samsung traits-and-limitation=rasgos-y-limitaciones h_01JDPYAV86PT14C91ZQ2D9XTZ2=rasgos-y-limitaciones" />

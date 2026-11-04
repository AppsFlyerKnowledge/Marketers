---
title: 'Google Ads (AdWords): crea campañas web para aplicaciones web'
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2026-04-07T12:46:10Z'
  edited_at: '2026-10-20T03:47:54Z'
  id: 45498975339537
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/45498975339537
---
> **At a glance:** Configura una integración de Google Ads para tu aplicación web a fin de enviar señales de conversión web a Google mediante la API de Conversiones Offline (OCI).

<div id="overview" />

## Descripción general

AppsFlyer admite la integración con Google Ads (`googleads_int`) para campañas de aplicaciones en sitios web y reporta datos de conversión mediante la API de Conversiones Offline de Google (OCI).

En este artículo aprenderás a configurar campañas web en AppsFlyer y Google Ads, segmentadas a usuarios que interactúan con Google Ads y realizan conversiones en tu sitio web.

El flujo de la campaña comienza cuando un usuario hace clic en un anuncio de Google y llega a tu sitio web. Cuando el usuario completa un evento en el sitio web (por ejemplo, una compra o un registro), AppsFlyer envía la señal de conversión a Google Ads mediante OCI. Google utiliza estos datos para optimizar la segmentación de anuncios y medir el rendimiento de las campañas.

<div id="prerequisites" />

### Requisitos previos

Antes de activar la integración de Google Ads para campañas de aplicaciones web, asegúrate de tener lo siguiente:

* Una aplicación web configurada en AppsFlyer
* El SDK web de AppsFlyer implementado en tu sitio web, o una integración totalmente del lado del servidor mediante la API Server-to-Server (S2S). Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/server-to-server-s2s-api-for-web-performance-measurement#configurar-una-integración-completamente-del-lado-del-servidor">Configura una integración totalmente del lado del servidor</Anchor>
* Una cuenta de AppsFlyer con los roles o permisos adecuados.

<div id="how-to-set-up-a-google-ads-web-campaign" />

### Cómo configurar una campaña web de Google Ads

La configuración consta de dos partes:

1. Configura la integración de Google Ads en AppsFlyer (obligatorio)
2. Configura la campaña en Google Ads (obligatorio)

<div id="set-up-the-google-ads-integration-in-appsflyer" />

## Configura la integración de Google Ads en AppsFlyer

Para empezar, activa la integración de Google Ads para campañas web y configura los postbacks que AppsFlyer envía a OCI.

<div id="step-1-activate-the-integration" />

<Accordion title="Paso 1: Para activar la integración">

1. En AppsFlyer, en el menú lateral, ve a **Colaborar > Partner Marketplace**.
2. Busca **Google Ads Web** y selecciónalo.
3. Haz clic en **Configurar integración**. Se te redirigirá a la página de configuración de **Integraciones activas**.
4. En el menú desplegable de la app, selecciona la aplicación web.
5. En la pestaña **Integración**, selecciona **Activar partner**.

   <div id="note" />

   > 📘 **Nota**
   >
   > El interruptor debe permanecer (activado) mientras trabajes con el partner.

6. Ingresa tu **Customer ID**. Puedes recuperarlo desde tu Google Ads Manager:
   1. <span class="af-ol-a"></span>Inicia sesión en tu cuenta de Google Ads.
   2. En la esquina superior derecha, haz clic en el icono de la cuenta de Google y desplázate hacia abajo hasta donde se muestra el Customer ID.
   3. Realiza una de las siguientes acciones:
      * Si tienes varias cuentas de Google Ads que ejecutan campañas para tu aplicación, debes usar el Customer ID de un administrador (MCC) para el seguimiento de conversiones de varias cuentas. Pega el ID de MCC (y no el Customer ID de una cuenta específica) en el campo Customer ID y también en el cuadro de texto MCC Customer ID (el mismo ID en ambos campos).  Para más información, consulta <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">las instrucciones de Google sobre cómo configurar una cuenta MCC</Anchor>.
      * Si solo utilizas una cuenta de Google Ads para publicar anuncios, pega el ID de la cuenta en el cuadro de texto "Customer ID". Deja vacío el cuadro de texto MCC Customer ID.
7. Para permitir que AppsFlyer suba conversiones a Google Ads, haz clic en **Iniciar sesión con Google**.
8. Selecciona la cuenta de administrador de la cuenta MCC de la que recuperaste el Customer ID en el paso 7.
9. Haz clic en **Permitir**.

   <div id="note-1" />

   > 📘 **Nota**
   >
   > El mensaje de error **Missing token** dejará de aparecer una vez que inicies sesión con Google y permitas que AppsFlyer obtenga el token. Si el error persiste después de iniciar sesión, *verifica que tu token tenga los permisos requeridos*.


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="Paso 2: Configurar postbacks de eventos in-app">

Asocia los eventos de tu sitio web con las acciones de conversión de Google Ads. AppsFlyer envía estos eventos a Google a través de OCI para impulsar la optimización basada en conversiones.

<div id="note-2" />

> 📘 **Nota**
>
> En las aplicaciones web, todos los eventos son eventos web. No hay eventos de instalación. Cada evento para el que quieras que Google optimice debe asociarse a un ID de acción de conversión correspondiente de Google Ads.

1. Activa **Postbacks de eventos in-app**.
2. Configura la **Ventana de postback de eventos in-app**, si es necesario. La ventana se abre cuando se produce el primer evento de conversión del usuario en el sitio web (el equivalente web de la fecha de instalación en dispositivos móviles).
3. Haz clic en **Agregar evento**.
4. En la columna **Evento de AppsFlyer**, selecciona el evento del sitio web que quieres enviar (por ejemplo, `purchase`, `sign_up`).

   <div id="note-3" />

   > 📘 **Nota**
   >
   > Los eventos de visita están excluidos. En este menú desplegable solo están disponibles los eventos web personalizados.

5. En la columna **Asignado al evento de partner**, introduce el **ID de la acción de conversión** de Google Ads. Antes de hacerlo, debes crear la acción de conversión en Google Ads (consulta el [paso 2: Crear acciones de conversión](#step-2-create-conversion-actions)). Para encontrar el ID de la acción de conversión:
   * En Google Ads, abre la página de la acción de conversión.
   * Abre la pestaña **Detalles**.
   * En la URL de la página, copia el valor del parámetro de consulta `ctid=*`. Por ejemplo, si `ctid=123456789`, introduce `123456789`.
6. En la columna **Para usuarios de**, selecciona **Solo este partner** para enviar únicamente los eventos atribuidos a Google Ads.
7. En la columna **Incluir**, selecciona si quieres incluir los valores de ingresos en el postback.
8. Haz clic en **Guardar integración**.

<div id="note-4" />

> 📘 **Nota**
>
> Si envías eventos S2S y quieres que AppsFlyer envíe postbacks de esos eventos a Google Ads, asegúrate de que cada evento tenga al menos un Google click ID: `gclid`, `gbraid` o `wbraid`. Si un evento no tiene ninguno, AppsFlyer no envía el postback. Para consultar todos los campos de evento compatibles, consulta <Anchor target="_blank" href="/marketers/es/docs/server-to-server-s2s-api-for-web-performance-measurement#medir-un-evento">Server-to-Server (S2S) API for Web Performance Measurement</Anchor>.

</Accordion>

<div id="set-up-a-web-conversion-campaign-in-google-ads" />

## Configura una campaña de conversión web en Google Ads

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="Paso 1: Configura el tipo de campaña, el objetivo y las metas">

1. Inicia sesión en Google Ads y crea una campaña.
2. Selecciona el **objetivo de la campaña**:
   * Todos los objetivos son compatibles excepto **Promoción de aplicaciones**, que solo se utiliza para campañas de aplicaciones móviles.
   * Recomendamos **Ventas** o **Clientes potenciales** para optimizar campañas en función de eventos de conversión específicos del sitio web.
3. Selecciona tus **objetivos de conversión**. De forma predeterminada, verás los objetivos a nivel de cuenta. Puedes mantenerlos o eliminar los que no sean relevantes.
   * Si el objetivo para el que quieres optimizar no aparece en la lista, crea una acción de conversión personalizada (consulta el [paso 2: Crear acciones de conversión](#step-2-create-conversion-actions)).
4. Selecciona el **tipo de campaña**:
   * Todos los tipos son compatibles excepto **Compras**, que requiere un catálogo de productos y un dominio verificado.

</Accordion>

<div id="step-2-create-conversion-actions" />

<Accordion title="Paso 2: Crea acciones de conversión">

Para cada evento del sitio web que hayas asociado en AppsFlyer, crea la acción de conversión correspondiente en Google Ads. Después de crearla, copia el ID de la acción de conversión y pégalo en la asignación de eventos de AppsFlyer de la sección anterior.

1. En Google Ads, en el menú lateral, ve a **Objetivos > Conversiones > Resumen**.
2. Haz clic en **+ Nueva acción de conversión**.
3. Selecciona **Importar** como fuente de datos de conversión y, a continuación, elige una de las siguientes opciones:
   * **Importación manual mediante API o cargas > Seguimiento de conversiones a partir de clics**, O
   * **CRM, archivos u otras fuentes de datos > Seguimiento de conversiones a partir de clics** y, en Fuente de datos, selecciona **Omitir este paso y configurar la fuente de datos más adelante**.
4. Haz clic en **Continuar**.
5. En **Objetivo de conversión**, selecciona una categoría de acción de conversión.
6. Introduce un **Nombre de la conversión** y haz clic en **Agregar**.

   <div id="important" />

   > 🚧 **¡Importante!**
   >
   > Para usar la API de Conversiones Offline con GBRAID/WBRAID (además de GCLID), asegúrate de que el campo **Count** en la acción de conversión esté configurado en **Every** (predeterminado) y no en **One**.


   <div id="note-5" />

   > 📘 **Nota**
   >
   > Si quieres que tus campañas se optimicen únicamente para una acción, incluye solo esa acción en esta categoría. Por ejemplo, si quieres que tu campaña se optimice para una acción de conversión de compra, asegúrate de que sea la única dentro de su categoría. Después podrás seleccionar esta categoría como objetivo de conversión para optimizar el rendimiento al crear la campaña.

7. Haz clic en **Guardar y continuar** y, a continuación, en **Listo**, sin configurar fuentes de datos. Es posible que tu nueva acción de conversión aparezca inicialmente como **Inactive**. Cambiará a **Activo** una vez que se envíen datos reales.
8. Para asociar la nueva acción de conversión al evento de postback de AppsFlyer, obtén el ID de la acción de conversión: En la página **Resumen** de objetivos de conversión, haz clic en la acción de conversión que creaste y copia el valor del parámetro de consulta `ctid=*` de la URL de la página.
9. En AppsFlyer, pega el valor `ctid` en la columna **Asignado al evento de partner** del evento de postback para el que quieres que Google optimice. Consulta [Paso 2: Configurar postbacks de eventos in-app](#step-2-set-inapp-event-postbacks).

</Accordion>

<div id="step-3-set-the-campaigns-final-url" />

<Accordion title="Paso 3: Configura la URL final de la campaña">

Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">define la URL final</Anchor> como "la dirección URL de la página de tu sitio web a la que llegan los usuarios después de hacer clic en tu anuncio, también conocida como 'landing page'".

1. En Google Ads, abre la página **Campañas > Anuncios**.
2. En la fila del anuncio, haz clic en el icono de edición.
3. En el **campo URL final**, introduce la URL de tu landing page.

   <div id="important-1" />

   > 🚧 **¡Importante!**
   >
   > La URL final no puede ser una URL de AppsFlyer (OneLink o una URL de atribución de una sola plataforma), ya que esto podría provocar que tu campaña fuera rechazada. Utiliza únicamente una dirección web directa, sin redirecciones.
   >
   > Puedes añadir parámetros de atribución de AF a la URL final y asociarlos a los parámetros ValueTrack de Google; por ejemplo, `af_c_id={campaignid}`. Una vez que el usuario hace clic en el anuncio de Google y se carga la landing page, estos parámetros están disponibles en la página. Para más información sobre los parámetros ValueTrack disponibles, consulta la <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348">documentación de Google</Anchor>.
   >
   > Por ejemplo:
   >
   > ```http
   > https://example.com?product=1234&af_c_id={campaignid}
   > ```


<div id="note-6" />

> 📘 **Nota**
>
> Las campañas de Google Web Ads pueden utilizar dos URL por engagement: la URL final y la URL de la plantilla de seguimiento. Sin embargo, la URL de la plantilla de seguimiento no es necesaria para las campañas de aplicaciones web cuyo destino del anuncio es un sitio web. Puede que solo necesites una URL de plantilla de tracking cuando el objetivo de la campaña sea web-to-mobile. Para más información, consulta el <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-based-campaigns">artículo sobre campañas web-to-app de Google Ads</Anchor>.

</Accordion>

<div id="view-web-performance-measurement-data" />

## Ver datos de Medición del performance web

Los datos de atribución web de las campañas de Google Ads están disponibles en el dashboard multiplataforma y en las exportaciones de raw data:

* **Dashboard:** En el <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#crossplatform-dashboard">dashboard multiplataforma</Anchor>, los datos web y de la app se muestran uno al lado del otro, lo que te ofrece una vista unificada del rendimiento de las campañas en todas las plataformas.
* **Exportaciones de raw data:** Los datos de atribución web también están disponibles en la página <Anchor target="_blank" href="/marketers/es/docs/raw-data-export-page">Exportaciones de raw data</Anchor>.
  * El campo `media_source` muestra `googleadwords_int` para los eventos web atribuidos a Google Ads.

<div id="note-7" />

> 📘 **Nota:**
>
> Esta vista unificada de reportes te permite analizar el rendimiento de las campañas web y de apps en un solo lugar, incluidos los reportes completos de costos web y móviles.

<div id="measure-web-performance-data-with-web-cost" />

## Mide los datos de rendimiento web con el costo web

En el dashboard y en los <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">reportes de Cost ETL</Anchor>, puedes obtener una vista completa del rendimiento de los datos de atribución web y los datos de costo web de Google Ads. Para hacerlo, asegúrate de tener <Anchor target="_blank" href="/marketers/es/docs/roi360-onboarding-guide#sobre-roi360">el paquete ROI360</Anchor> y completa la siguiente configuración:

1. Conecta el costo a tu aplicación web mediante `googleadwords_int` (no mediante `googleads_int`) desde la pestaña **Costo** o la página **Configuración de costos**. Para más información sobre cómo conectar el costo, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">Configurar la API de costos de ROI360 para medir los datos de costos</Anchor>.
2. Incluye el ID de la campaña (`af_c_id`) en la URL de la landing page. Asegúrate de que la URL incluya la jerarquía completa de la campaña para ver los costos, clics e impresiones asociados a la atribución web con el mayor nivel de detalle posible.

<div id="troubleshooting-in-app-event-postbacks" />

## Solución de problemas de postbacks de eventos in-app

Si los datos de los eventos no aparecen en Google Ads, comprueba lo siguiente antes de ponerte en contacto con el equipo de soporte.

<div id="set-token-permissions" />

<Accordion title="Configurar los permisos del token">

En Google Ads, asegúrate de que tu token de acceso tenga los permisos necesarios para subir conversiones offline:

1. Ve a Google Developers Console.
2. Asegúrate de que `uploadClickConversions` tenga el siguiente alcance de OAuth: `https://www.googleapis.com/auth/adwords`.
3. En AppsFlyer, en la pestaña Integración, haz clic en **Iniciar sesión con Google**.
4. Selecciona la cuenta de administrador de la cuenta MCC.
5. Haz clic en **Permitir**.

</Accordion>

<div id="mcc-customer-id" />

<Accordion title="ID de cliente de MCC">

Si tienes varias cuentas de Google Ads ejecutando campañas para tu app, debes utilizar el Customer ID de una cuenta MCC. Consulta las <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186">instrucciones de Google para configurar una cuenta MCC</Anchor>.

</Accordion>

<div id="conversion-action-id" />

<Accordion title="ID de la acción de conversión">

Asegúrate de que los postbacks de eventos in-app estén asociados al ID de acción de conversión correcto. Para encontrar el ID de la acción de conversión en Google Ads, consulta el [Paso 2:](#step-2-create-conversion-actions) Crear acciones de conversión.

</Accordion>

<div id="traits-and-limitations" />

## Características y limitaciones

| Caducado | Observaciones |
| --- | --- |
| Clics e impresiones | Los clics y las impresiones de las campañas web requieren una <Anchor target="_blank" href="/marketers/es/docs/roi360-onboarding-guide">suscripción a ROI360</Anchor>. |

<div id="see-also" />

> 📄 **Ver también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/web-performance-measurement-overview">Medición del rendimiento web: descripción general</Anchor>

<div data-zendesk-anchors="overview=descripci%C3%B3n-general h_01KNM00RR7V9BAA2BSPDECHC9F=descripci%C3%B3n-general prerequisites=requisitos-previos h_01KNM00RR7H7A9CE06APEZSXKR=requisitos-previos how-to-set-up-a-google-ads-web-campaign=c%C3%B3mo-configurar-una-campa%C3%B1a-web-de-google-ads h_01KNM00RR77P8VD2YJ2R7DZBVX=c%C3%B3mo-configurar-una-campa%C3%B1a-web-de-google-ads set-up-the-google-ads-integration-in-appsflyer=configura-la-integraci%C3%B3n-de-google-ads-en-appsflyer h_01KNM00RR7E8MFSTGYKFEJDS1C=configura-la-integraci%C3%B3n-de-google-ads-en-appsflyer h_01KNM00RR71ZXB72H8X1YXWKED=step-1-activate-the-integration h_01KNM00RR84CCGBR3T5WG7C5VW=nota h_01KNM00RR86C5VKBVTA9X6QRAS=nota-1 h_01KNM00RR8BCJTMPZ29C841BY1=step-2-set-inapp-event-postbacks h_01KNM00RR8PSJ7FEAP7MMEJ1XG=nota-2 h_01KNM00RR89XJ0BZKFDXVC4860=nota-3 h_01M520ZTQ1QT2F03TMY9TZBPSY=nota-4 set-up-a-web-conversion-campaign-in-google-ads=configura-una-campa%C3%B1a-de-conversi%C3%B3n-web-en-google-ads h_01KNM00RR8SAS3TM1NG5DC58TF=configura-una-campa%C3%B1a-de-conversi%C3%B3n-web-en-google-ads h_01KNM00RR8S24AG7FMN6067PZ2=step-1-set-the-campaign-type-objective-and-goals h_01KNM00RR8H1ZFSHFT0DVB11GN=step-2-create-conversion-actions h_01KNM00RR8EV8XY02YJFV5XSX8=importante h_01KNM00RR8N96SNP1YK0CTN6YZ=nota-5 h_01KNM00RR82NZSKB7K06HCP1VE=step-3-set-the-campaigns-final-url h_01KNM00RR8EP6J43G29Q8VVA5B=importante-1 h_01KNM00RR8A704MKGVVC6MQ2KN=nota-6 view-web-attribution-data=ver-datos-de-medici%C3%B3n-del-performance-web h_01KNM00RR8EYJAX2KRGCM65E9M=ver-datos-de-medici%C3%B3n-del-performance-web h_01KNM00RR86Q2GTHVNC505KCXZ=nota-7 measure-web-attribution-data-with-web-cost=mide-los-datos-de-rendimiento-web-con-el-costo-web h_01KNM00RR9TF8JRTJXWN23MF1S=mide-los-datos-de-rendimiento-web-con-el-costo-web troubleshooting-in-app-event-postbacks=soluci%C3%B3n-de-problemas-de-postbacks-de-eventos-in-app h_01KNM00RR9Z0BM5EE62M17EE0F=soluci%C3%B3n-de-problemas-de-postbacks-de-eventos-in-app h_01KNM00RR9CJJQAP4GAXZ9KK8N=set-token-permissions h_01KNM00RR9215H3KB024BBFZX2=mcc-customer-id h_01KNM00RR9DBR5979GA0FVD5AK=conversion-action-id traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KQAE3JKMQ6ZEATDAEXBC4PT6=caracter%C3%ADsticas-y-limitaciones h_01KQC2B644Y44631ZQKC1HPEF4=ver-tambi%C3%A9n" />

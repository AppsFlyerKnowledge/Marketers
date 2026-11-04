---
title: Google Ads (AdWords)—crea campañas web para aplicaciones móviles
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-05-16T09:12:15Z'
  edited_at: '2026-10-14T03:09:29Z'
  id: 25096718837137
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/25096718837137
---
> **At a glance:** Crea campañas web para atribuir las conversiones de la web a la aplicación de Google Ads

> 📘 **Note**
>
> Este artículo se centra en campañas web que promueven aplicaciones móviles. Si deseas crear campañas que promuevan aplicaciones para PC o consola, consulta Google Ads Web—Integración para aplicaciones de PC y consola.

<div id="overview" />

## Descripción general

AppsFlyer admite la integración con Google Ads (`googleads_int`) para campañas basadas en la web e informa de los datos de atribución y de conversión de las campañas a través de la API de conversiones offline de Google (OCI).

En este artículo, aprenderás cómo configurar campañas web móviles en AppsFlyer y Google Ads, dirigidas a los usuarios web que interactúan con los anuncios de Google.

Las campañas se basan en una trayectoria del usuario que comienza cuando un usuario hace clic en un anuncio y es redirigido a una landing page. Esta página incluye Smart Script o Smart Banners de AppsFlyer, que crean enlaces de atribución.

Una vez que se hace clic, estos enlaces llevan al usuario a la tienda de aplicaciones para descargar e instalar la aplicación. La instalación y los eventos in-app posteriores se registran en AppsFlyer y se reportan a Google Ads a través de OCI.

Google utiliza estos datos para optimizar la segmentación de anuncios, medir el rendimiento y crear audiencias personalizadas.

<div id="prerequisite" />

### Requisito previo

Antes de activar la integración de Google Ads para campañas web, asegúrate de tener lo siguiente:

* Una aplicación móvil
* Una cuenta de AppsFlyer
* Usuarios de AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/user-management">con roles o permisos adecuados</Anchor> y acceso a las aplicaciones correspondientes

<div id="create-a-google-ads-web-campaign" />

### Cómo crear una campaña web de Google Ads

Este artículo contiene información y pasos para configurar una campaña web en Google Ads para aplicaciones móviles, de PC y consolas con AppsFlyer. La configuración implica definir la integración entre Google Ads y AppsFlyer, y establecer los enlaces de atribución de la campaña.

* [Configurar la integración de Google Ads en AppsFlyer](#crear-una-integración-de-google-ads-en-appsflyer) (obligatorio)
* [Configurar la integración de Google Ads en Google Ads](#crear-una-campaña-web-en-google-ads) (obligatorio)

Después de configurar los enlaces de atribución en el paso uno a través de la integración de Google Ads y AppsFlyer, el paso dos se centra en la creación de la landing page. Aquí, los Smart Script o Smart Banners de OneLink utilizarán los enlaces de atribución para generar botones de llamada a la acción, dirigiendo a los usuarios a las tiendas de aplicaciones.

* [Crear una página de destino con OneLink Smart Script](#crear-una-landing-page-con-smart-script-de-onelink) (opcional)
* [Crear una página de destino con OneLink Smart Banners](#crea-una-landing-page-con-smart-banners-de-onelink) (opcional)

<div id="create-a-google-ads-integration-in-appsflyer" />

## Crear una integración de Google Ads en AppsFlyer

Empieza por activar la integración con Google Ads para campañas web y configurar los postbacks que AppsFlyer envía a OCI.

<Accordion title="1. Activar la integración de Google Ads para campañas web">

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Partner Marketplace**.
2. Busca **Google Ads Web** y selecciónalo.
3. Haz clic en **Configurar integración**. Se te redirigirá a la página de configuración de **Integraciones activas** .
4. En la pestaña **Integración** , activa **Activate Partner**. **Nota:** El selector debe permanecer activado (<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activated</Anchor>) mientras trabajes con tu partner.
5. Desactiva **Privacidad avanzada** (si estás configurando una integración de una app de iOS).

> 📘 **Note**
>
> El mensaje de error **Missing token** dejará de aparecer cuando inicies sesión con Google y permitas que AppsFlyer obtenga el token en el paso siguiente. Si el error persiste después de iniciar sesión, verifica que tu token tenga los permisos requeridos.

1. En **ID de conversión de primera apertura**, introduce el ID de la acción de conversión `First open` que configuraste en Google Ads. Para encontrar el ID, ve a Google Ads y abre la **pestaña Details** de la página de la acción de conversión **First open**. A continuación, copia el valor del parámetro de consulta `ctid=*` de la URL de la página. Por ejemplo, si `ctid=123456789`, inserta `123456789` en el campo **ID de la acción de conversión de primera apertura**.

   ![](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)

> 👍 **Tip**
>
> Si aún necesitas establecer la acción "Primer acceso" en Google Ads, puedes introducir un valor de marcador de posición temporalmente hasta que la acción esté completamente configurada.

1. Introduce tu **ID de cliente**. Puedes recuperarlo desde tu Administrador de Google Ads:
   1. Inicia sesión en tu cuenta de Google Ads.
   2. En la esquina superior derecha, haz clic en el icono de la cuenta de Google y desplázate hacia abajo hasta donde se muestra el ID de cliente.
2. Si tienes varias cuentas de Google Ads que ejecutan campañas para tu aplicación, debes usar el ID de cliente de un administrador (MCC) para el seguimiento de conversiones de varias cuentas. Pega el **ID de MCC** (y no el ID de cliente de una cuenta específica) en el cuadro de texto **Customer ID** y también en el cuadro de texto **MCC Customer ID** text box (el mismo ID en ambos cuadros).   
   Si solo utilizas una cuenta de Google Ads para publicar anuncios, pega el ID de la cuenta en el cuadro de texto **Customer ID** y deja vacío el cuadro de texto **MCC Customer ID**. Consulta las <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">instrucciones de Google sobre cómo configurar una cuenta MCC</Anchor>.
3. Haz clic en **Permitir**.

</Accordion>

<Accordion title="2. Habilitar la atribución por impresiones">

AppsFlyer admite la atribución view-through para campañas web de Google mediante una página de destino habilitada para [Smart Script](#set-up-a-smart-script-crossplatform-landing-page) o [Smart Banner](#set-up-a-smart-banners-landing-page). Esto permite la atribución de instalaciones de aplicaciones mediante modelado probabilístico (PMOD) desencadenadas por impresiones de anuncios, incluso cuando los usuarios no hacen clic directamente en el anuncio.

Cuando un usuario ve un anuncio de Google y llega a una página de destino habilitada para [Smart Script](#set-up-a-smart-script-crossplatform-landing-page) o [Smart Banner](#set-up-a-smart-banners-landing-page), AppsFlyer puede atribuir la instalación de la app resultante, incluida la multiplataforma, a la impresión web original.

Cuando está disponible, AppsFlyer incluye el `gclid` en el postback a Google.

**Habilitar la atribución view-through:**

1. En AppsFlyer, en la barra lateral, abre **Colaborar** > **Integraciones de partners > Integraciones activas** > **Google Ads Web**
2. En la pestaña **Integración**, desplázate hasta la sección **Atribución de instalaciones**.
3. Activa la **atribución view-through de instalación**.
4. **[opcional]** Activa **Prioridad de atribución equitativa entre plataformas** y configura su ventana de lookback. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Habilitar igual prioridad para impresiones multiplataforma</Anchor>.
5. Abre la pestaña **Atribución**.
6. Desplázate hasta la sección **atribución view-through** y configura la **ventana de lookback view-through** que prefieras (hasta 24 horas).
7. Haz clic en **Guardar integración** para aplicar los cambios.

</Accordion>

<Accordion title="3. Activa el uso compartido de datos de coincidencia avanzada">

El uso compartido de datos de Advanced Matching se controla por partner y por app, y debe activarse por separado para Google Ads Web.

Cuando está activado, los identificadores con hash, como una dirección de correo electrónico con hash o un número de teléfono con hash, se comparten con Google OCI si estos campos se incluyen en los datos del evento que envías. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.

Para activar el uso compartido de datos de Advanced Matching:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Integraciones de partners** > **Integraciones activas**.
2. Busca **Google Ads Web** y selecciónalo.
3. En la pestaña **Integración**, activa **Uso compartido de datos de coincidencia avanzada**.
4. Haz clic en **Guardar integración**.

</Accordion>

<Accordion title="4. Configurar postbacks de eventos in-app">

Actualmente, las instalaciones son los únicos eventos que activan postbacks automáticos predeterminados a Google Ads para Web a través de la API OCI. Para otros tipos de eventos, puedes crear postbacks personalizados asignando los eventos de AppsFlyer a los ID de acción de conversión de Google Ads («Conversion action» es el término que Google Ads utiliza para los eventos de atribución) Consulta Google Ads Manager para obtener información sobre el evento de Google Ads Web que debes asignar a los eventos de AppsFlyer.

1. Activa **Postbacks de eventos in-app**.
2. Si es necesario, configura la ventana de postback de eventos in-app (obtén más información sobre la configuración general de la ventana de postback de eventos in-app en <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">este artículo</Anchor>).
3. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista.
4. En la **columna Evento de AppsFlyer** , selecciona el nombre del evento en el cuadro desplegable. AppsFlyer recibe el nombre del evento del SDK integrado en tu aplicación o de los eventos de servidor a servidor.
5. En la **columna Asignado al evento de partner** , debes asignar el evento de AppsFlyer a un ID de acción de conversión de Google correspondiente. Antes de poder hacerlo, debes configurar las acciones de conversión de Google necesarias en Google Ads. Para obtener información sobre cómo configurar acciones de conversión en Google Ads, consulta [crear acciones de conversión personalizadas.](#h_01J1MPPMW4KMSXAR903P534X65)

   **Para encontrar el ID de acción de conversión en Google Ads:**

   1. Ve a Google Ads.
   2. Abre la página de la acción de conversión que deseas mapear.
   3. Abre la pestaña **Detalles**.
   4. En la URL de la página, copia el valor del parámetro de consulta `ctid=*`.
   5. Volver a AppsFlyer
   6. Pégalo en la columna **asignado al evento de partner**. Por ejemplo, si `ctid=123456789`, pega `123456789`.
6. En la columna **Para usuarios de**, selecciona **Solo este partner** o **Todas las fuentes de medios, incluida la orgánica**. **Nota:** los eventos sin atribuir se enviarán solo si <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Advanced Matching Data Sharing</Anchor> está activado e incluyen un correo electrónico o un número de teléfono con hash.
7. En la columna **Incluido** , selecciona si todos los parámetros del evento, incluido el valor de los ingresos (si existe en el evento), se envían en el postback.
8. [Opcional] Haz clic en el **icono Añadir condición** para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.
9. Haz clic **Guardar integración**.
10. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
    1. En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
    2. Selecciona una aplicación diferente del desplegable.
    3. Repite los pasos de integración para la aplicación seleccionada.

</Accordion>

<Accordion title="5. Configurar la plantilla de OneLink">

Antes de crear un enlace de atribución de OneLink para tu campaña de Google Ads, debes configurar su plantilla. A continuación, puedes crear una URL de atribución de OneLink basada en la plantilla y utilizarla como URL de la plantilla de seguimiento de Google.

> 📘 **Note**
>
> Las instrucciones a continuación se centran en la creación de una plantilla de OneLink para campañas web de Google con Smart Script. Para obtener una guía completa sobre cómo configurar plantillas de OneLink, consulta la sección Cómo crear plantillas de OneLink del artículo Plantillas de OneLink.

1. En la sección **Redireccionamiento** de la página **Nueva plantilla** o **Editar plantilla** página, configura los siguientes ajustes:
   * **Cuando la aplicación no está instalada** > **Redirigir a**: Selecciona la opción que prefieras. El valor de redireccionamiento que configures aquí se reemplaza por el valor de `{lpurl}` de los parámetros de redireccionamiento (<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_android_url">`af_android_url`</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_ios_url">`af_ios_url`</Anchor>) que incluyas en la Tracking Template de Google; consulta [Configurar la URL de la Tracking Template](#establecer-la-url-de-la-plantilla-de-seguimiento).
   * **Cuando la aplicación está instalada**: Asegúrate **de no** configurar Universal Links, el esquema de URI o All Links para abrir la aplicación, ya que Google no permite ningún redireccionamiento aparte del redireccionamiento a la URL final.
   * **Cuando se hace clic en el enlace en una página web de desktop** > **Redirigir a**: Selecciona la opción que prefieras. El valor de redireccionamiento que establezcas aquí se reemplaza por el valor de `{lpurl}` de los parámetros de redireccionamiento (<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_web_dp">`af_web_dp`</Anchor>) que incluyas en la plantilla de seguimiento de Google; consulta [Configurar la URL de la plantilla de seguimiento](#establecer-la-url-de-la-plantilla-de-seguimiento).
2. Haz clic **Crear plantilla**.

</Accordion>

<div id="create-a-web-campaign-in-google-ads" />

## Crear una campaña web en Google Ads

Realiza los siguientes pasos en Google Ads.

<Accordion title="1. Establece el tipo de campaña, el objetivo y las metas">

Google Ads utiliza el tipo de campaña, el objetivo y las metas que selecciones aquí para establecer la estrategia de oferta adecuada y optimizar el rendimiento de la campaña.

1. Inicia sesión en Google Ads y crea una campaña.
2. Selecciona un objetivo de campaña.

   ![](https://files.readme.io/90063f7fe5a363ed498271148c4165969cc63c708a73ab25363d2263a79b0828-26324053661201.png)
   * Todos los objetivos son aplicables, excepto "Promoción de aplicaciones" (que solo se puede utilizar para campañas de aplicaciones móviles).
   * Recomendamos establecer el objetivo de la campaña "Ventas" para la optimización en función de eventos in-app específicos.
3. Selecciona los objetivos de conversión.

   ![](https://files.readme.io/5ca0a0425af24d5926dc0a7a3529632e22bd140423e87c026ff1527e7a0341b3-26324096257169.png)
   * De forma predeterminada, verás los objetivos de campaña predefinidos a nivel de cuenta. Puedes conservarlas o eliminar las que no sean relevantes para tu campaña.
   * Si no ves el objetivo que deseas que Google optimice,

     <Anchor target="_blank" href="/marketers/es/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals">crea una acción de conversión y un objetivo personalizados</Anchor>.
   * También puedes editar tus metas predefinidas en la página Conversiones.
4. Selecciona el tipo de campaña.

   ![](https://files.readme.io/14daea1c1edf92854e21d0a4c5d34372a4e062d68a4613967bb4f40d0d1e720f-26324053659281.png)
   * Todos los tipos de campaña son aplicables, excepto "Compras", que requiere un catálogo de productos y está limitada a dominios verificados.

</Accordion>

<Accordion title="2. Crear acciones de conversión personalizadas">

A continuación, para cada [evento in-app que configuraste en AppsFlyer](#h_01J1MPPMW34GG0EPDWYXA7383C), debes crear una acción de conversión correspondiente en Google Ads. Una vez que completes la creación de la acción de conversión, deberás copiar el ID de la acción recién creada y asignarlo al evento in-app de AppsFlyer.

Para crear acciones y metas de conversión personalizadas de Google Ads, sigue estos pasos:

1. En la página de vista general de tu cuenta de Google Ads, en el menú lateral, selecciona **Objetivos > Conversiones > Resumen**.
2. Haz clic en **+ Nueva acción de conversión**.
3. Selecciona **Conversiones offline** como fuente de datos de las acciones de conversión.
4. Selecciona **Import** en la lista de tipos de conversión y, a continuación, selecciona una de las siguientes opciones:

   * **Importación manual mediante API o subidas > Track conversiones desde clics**.

   O

   * **CRM, archivos u otras fuentes de datos > Track conversions from clicks,** y, en **Fuente de datos,** selecciona **Omitir este paso y configurar la fuente de datos más adelante**.
5. Haz clic en **Continuar**.
6. En **Objetivo de conversión**, selecciona una categoría de acción de conversión.
7. En **Introducir un nombre de conversión**, escribe el nombre de la acción de conversión.

> ❗️ **Warning**
>
> Para usar la API de Conversiones offline con GBRAID/WBRAID (además de GCLID), asegúrate de que el campo **Count** de la acción de conversión esté configurado en **Every** (predeterminado) y NO en **One.**

1. Introduce un **Nombre de conversión** y, a continuación, haz clic en **Agregar**. **Nota**: Si solo quieres que tus campañas se optimicen para una sola acción, incluye solo esa acción en esta categoría. Por ejemplo, si quieres que tu campaña se optimice para la acción de conversión **Primer acceso**, asegúrate de que sea la única de su categoría. A continuación, podrás seleccionar esta categoría como meta de conversión para la optimización del rendimiento al crear la campaña.
2. Haz clic en **Guardar y continuar,** y luego en **Listo** sin configurar fuentes de datos. Tu nueva acción de conversión puede aparecer inicialmente como "Inactiva", pero cambiará a "Activa" una vez que se envíen datos reales.
3. Para asignar la nueva acción de conversión al evento de postback de AppsFlyer, recupera el ID de la nueva acción de conversión. En la página **Resumen,** de objetivos de conversión, haz clic en la acción de conversión que has creado y copia el valor del parámetro de consulta `ctid=*` de la URL de la página de la acción de conversión.

   ![](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)
4. En AppsFlyer, pega el valor `ctid` en la **columna Asignado al evento de partner** del evento de postback para el que quieres que Google optimice; consulta: [Configurar postbacks de eventos in-app](#h_01J1MPPMW34GG0EPDWYXA7383C).

</Accordion>

<Accordion title="3. Establecer las URL de campaña">

Las campañas de Google Web Ads utilizan dos URL para cada engagement: la URL final y la URL de la plantilla de tracking. Estas URL se activan simultáneamente cuando se hace clic en el anuncio, una función a la que Google se refiere como seguimiento en paralelo. Más información sobre el seguimiento en paralelo está disponible en la <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">documentación de Google</Anchor>.

<div id="set-the-final-url" />

#### Establecer la URL final

Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">define la URL final</Anchor> como «la dirección URL de la página web de tu sitio web a la que llegan los usuarios después de hacer clic en tu anuncio». También se conoce como la 'landing page'".

**Para establecer la URL final**

1. En Google Ads, abre la página **Campañas** > **Anuncios**.
2. En la fila del anuncio, haz clic en el icono de edición.

   ![](https://files.readme.io/e6b834a0e105324c5b9e4105a5ce7e1f47fa7c00fcf2aee29b6b0e96763150f1-26324098055057.png)
3. En **URL final,** introduce la URL de la página web de destino.

> ❗️ **Warning**
>
> La URL final no puede ser una URL de AppsFlyer (OneLink o una URL de atribución de una sola plataforma), ya que esto podría hacer que rechazaran tu campaña. Utiliza únicamente una dirección web directa sin redireccionamientos, como la URL de una página web, la URL de Google Play Store o la URL del App Store.

1. Esta debe ser la ubicación web final a la que deseas redirigir a los usuarios. Puede ser:
   * **Una URL de página de destino** que apunte a una página que invite al usuario a hacer clic en un botón de CTA para descargar la aplicación desde Google Play, App Store o cualquier otra tienda de aplicaciones. La landing page incluye Smart Script o Smart Banners, que generan automáticamente las URL de los botones de llamada a la acción. Para saber [cómo crear la página de destino con Smart Script](#crear-una-landing-page-con-smart-script-de-onelink) o [Smart Banners](#crea-una-landing-page-con-smart-banners-de-onelink).

     Puedes añadir parámetros de atribución de AF a la URL final y asignarlos a los parámetros ValueTrack de Google; por ejemplo, `af_c_id={campaignid}`. Una vez que se hace clic en el anuncio de Google y se carga la landing page, el Smart Script o los Smart Banners pueden copiar los parámetros en la URL saliente de la landing page. Para más información sobre los parámetros ValueTrack disponibles, consulta la [documentación de Google](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter).

     Por ejemplo:

     ```
     https://example.com?product=1234&af_c_id={campaignid}
     ```
   * **Una URL de una tienda**, como App Store o Google Play.

> ❗️ **Warning**
>
> Supongamos que utilizas la URL de la tienda como URL final. La única forma de enviar información de parámetros personalizados y de atribución a AppsFlyer es insertar y asignar parámetros de AF a la URL de la plantilla de seguimiento.

*
  ```
  https://play.google.com/store/apps/details?id=.com.app.id&hl=en&gl=US&referrer={gclid}&gclid={gclid}&campaignid={campaignid}
  ```
* **Un enlace de descarga directa al archivo APK de la aplicación** si quieres que los usuarios descarguen la aplicación directamente sin ser redirigidos a una tienda.

<div id="set-the-tracking-template-url" />

#### Establecer la URL de la plantilla de seguimiento

Dado que Google Ads, de forma predeterminada, utiliza el seguimiento en paralelo, la URL de la plantilla de seguimiento (un enlace de atribución de AppsFlyer en este caso) se carga en segundo plano y el clic se registra en AppsFlyer. No es obligatorio usar URLs de plantilla de tracking, especialmente al usar Smart Banners o Smart Script. Consulta [Uso de la URL de la plantilla de tracking con Smart Script o Smart Banners](#uso-de-la-url-de-plantilla-de-seguimiento-con-smart-script-o-smart-banners) en este artículo.

1. En Google Ads, abre la página **Campañas** > **Campañas**. En la fila de la campaña, haz clic en el icono de configuración

   ![](https://files.readme.io/ec6503cfb3ff185448f13897240e0eadd7f10fc3678ffa85b4d52d2393b01ca4-26324098054033.png)
2. Despliega **Configuración** > **Ajustes adicionales** > **Opciones de URL de campaña**

   ![](https://files.readme.io/4959b4129749ff282ee3818c3b5724ac2ed3b1d033d06f8557329cafa812720f-26324053658641.png)
3. En **Plantilla de seguimiento,** usa lo siguiente (BaseURL + parámetros de redirección):
   * **URL base**: establece la URL base según el destino del clic en el anuncio:
     * **Enlace de atribución de plataforma única** si el destino del clic en el anuncio es Google Play o la tienda de aplicaciones (consulta el ejemplo a continuación).
     * **Un enlace de atribución de OneLink** si el destino del clic del anuncio es una página web (consulta el ejemplo a continuación).

> ❗️ **Warning**
>
> Si tu URL final apunta directamente a la tienda de Google Play o a la tienda de aplicaciones (se conoce la plataforma del usuario), usa un enlace de atribución de plataforma única en la URL de la plantilla de tracking. Usar una URL de OneLink en este caso da como resultado un error de «Tracking call unsuccessful» de Google.

* **El parámetro PID:** Añade el parámetro obligatorio <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#pid">`pid`</Anchor>`=googleads_int`.

> 👍 **Tip**
>
> Para simplificar el análisis de la campaña, incluye el tipo de campaña, web o móvil, como prefijo o sufijo en el nombre de la campaña, por ejemplo, campaign-name\_web

* **El parámetro de ID del sitio  :** Añade el parámetro obligatorio <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor>. Puedes asignarle manualmente cualquier valor.
* **El parámetro del nombre de la campaña:** Añade el parámetro obligatorio <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#c">c</Anchor> y asigna manualmente su valor (no hay ningún parámetro ValueTrack para este parámetro).
* **El parámetro force transparent**: Añade el parámetro obligatorio `af_force_transparent=true`. Este parámetro está diseñado para mejorar la seguridad en el comportamiento de redirección y garantizar que tu configuración cumpla con los requisitos de Google. Ten en cuenta que si no agregas el parámetro requerido, Google puede desaprobar tu anuncio.
* **Parámetros de redirección para un enlace de atribución de OneLink:** Para que el seguimiento en paralelo funcione como se espera, establece los parámetros de redirección AF en una de las siguientes combinaciones:
  * Los parámetros `af_android_url`, `af_ios_url` y `af_web_dp` deben establecerse en el parámetro Google ValueTrack `{lpurl}`. **Importante:** Asegúrate de que los tres estén rellenos para garantizar que el enlace de atribución funcione en todos los casos.  
    **O**
  * El parámetro `af_r` debe establecerse en el `{lpurl}` parámetro de Google ValueTrack.
* **Parámetro de redirección para un enlace de atribución de plataforma única:** Para que el seguimiento en paralelo funcione como se espera, establece el parámetro `af_r` en el `{lpurl}` parámetro de Google ValueTrack.

> ❗️ **Warning**
>
> Para cumplir con los requisitos de Google, asegúrate de que el valor `{lpurl}` sea una URL de redirección válida:
>
> * Utiliza el protocolo HTTPS.
> * Debe estar codificado.
> * El dominio de la URL está incluido en tu lista de permitidos para redirecciones.

* **Parámetros de atribución de AppsFlyer asignados a parámetros ValueTrack de Google**, por ejemplo, <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor>`={campaignid}`. Para más información sobre los parámetros ValueTrack disponibles, consulta la [documentación de Google](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter).
* No incluyas ninguno de los siguientes parámetros. Las solicitudes que contienen estos parámetros no son compatibles con el flujo de tracking paralelo y se rechazarán:
  * `af_dp`
  * `af_android_store_csl`
  * `af_ios_store_cpp`
  * `af_og_title`
  * `af_og_description`
  * `af_og_image`
* No incluya ningún parámetro que altere el valor del parámetro de redirección `{lpurl}`. Esto incluye `af_base_params_forward` y `af_param_forwarding`.

> 📘 **Note**
>
> Para limitaciones adicionales relacionadas con la URL de la plantilla de seguimiento, consulta la sección Rasgos y limitaciones en este documento.

<div id="google-tracking-template-url-examples" />

#### Ejemplos de URL de plantilla de seguimiento de Google

Ejemplo de **un** **OneLink** en una URL de plantilla de seguimiento de Google:

```
https://subdomain.onelink.me/aAB1?pid=googleads_int&af_force_transparent=true&af_android_url={lpurl}&af_ios_url={lpurl}&af_web_dp={lpurl}&c=summer_sale24&af_siteid=123456&af_c_id={campaignid}&af_adset=sum24A&af_adset_id={adgroupid}&af_sub1={gclid}&af_sub2={gbraid}
```

Ejemplo de **un enlace de plataforma única** en una URL de plantilla de seguimiento de Google:

```
https://app.appsflyer.com/id1510557250?pid=googleads_int&af_force_transparent=true&c=examplecamp&af_siteid=123456&af_adset=exampleadset&af_adset_id={adgroupid}&af_c_id={campaignid}&af_ad_id={creative}&af_click_lookback=7d&af_r={lpurl}
```

<div id="using-the-tracking-template-url-with-smart-script-or-smart-banners" />

#### Uso de la URL de plantilla de seguimiento con Smart Script o Smart Banners

No es necesario que rellenes la URL de la plantilla de seguimiento con un enlace de atribución de AppsFlyer cuando el anuncio redirige a una página de destino que utiliza un Smart Script o Smart Banners. Esto se debe a que estas herramientas crean automáticamente un enlace de atribución que se registra en AppsFlyer cuando el usuario hace clic en el botón de llamada a la acción de la landing page. Sin embargo, hay consideraciones a favor y en contra de dejar vacío el campo de la URL de la plantilla de seguimiento:

* Si **no rellenas** la URL de la plantilla de seguimiento con un enlace de atribución, corres el riesgo de perder instalaciones que se producen cuando el usuario hace clic en el anuncio, pero no hace clic en ninguno de los botones de llamada a la acción de la página de destino. Si el usuario va directamente a la tienda de aplicaciones para descargar la aplicación dentro de la ventana retrospectiva, la instalación posterior no será atribuible.
* Si **rellenas** la URL de la plantilla de seguimiento con un enlace de atribución y el usuario hace clic en el anuncio y, posteriormente, hace clic en los botones de llamada a la acción de la página de destino, se registrarán dos clics en lugar de uno, lo que puede afectar a los datos de la tasa de conversión.

</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## Crear una landing page con Smart Script de OneLink

**Recorrido del usuario:** El usuario hace clic en un anuncio de Google y es dirigido a tu sitio web móvil. Llegan a una página con botones de llamada a la acción que los instan a descargar tu aplicación. Al hacer clic en el botón, se redirigirá al usuario a la tienda.

<Accordion title="Flujo de datos end-to-end">

El caso de uso de Smart Script W2A se compone de las siguientes fases:

![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. El usuario hace clic en un anuncio de Google, Google automáticamente agrega a la URL final lo siguiente:
   * un `gclid` parámetro para dispositivos Android y para usuarios que den su consentimiento en dispositivos iOS.
   * `gbraid` y `wbraid` para usuarios de dispositivos iOS que no dan su consentimiento.
   * todos los parámetros de consulta establecidos en la URL de plantilla de seguimiento de Google, excepto los parámetros de redirección.
2. La URL final redirecciona al usuario a la landing page.
3. Simultáneamente, la URL de la plantilla de seguimiento de Google del anuncio, que también contiene los parámetros añadidos automáticamente `gclid`, `gbraid`, `wbraid` y `pid=googleads_int` , se activa en segundo plano y el clic se registra en AppsFlyer.
4. Cuando se carga la página de destino, el Smart Script activa un evento de impresión en AppsFlyer, que incluye los parámetros de URL entrante. Esta impresión habilita la atribución view-through para la landing page. Para obtener más información sobre impresiones y atribución view-through, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">Crear una URL de impresión personalizada</Anchor>.
5. Smart Script genera las URL salientes para los botones de llamada a la acción de la página en función de los parámetros de la URL entrante, incluidos los `gclid`, `gbraid` y `wbraid` parámetros. Los botones pueden llevar a:
   * Google Play y App Store mediante un link de atribución OneLink.
   * Tiendas de múltiples plataformas (por ejemplo, CTV, Epic y Steam). En este caso de uso, Smart Script genera un enlace de atribución de plataforma única saliente para cada plataforma, que conduce a la tienda de la plataforma especificada.
   * Descargar un archivo APK en el dispositivo del usuario.
6. Cuando el usuario hace clic en el botón de llamada a la acción, el clic se activa y se registra en AppsFlyer.
7. El usuario es redirigido a la tienda y descarga la app.
8. El evento de instalación se registra en AppsFlyer cuando el usuario abre la aplicación.
9. AppsFlyer atribuye la instalación en función de un modelo probabilístico o de forma determinista si hay disponible un [referente de instalación](https://www.appsflyer.com/glossary/install-referrer/) .
10. Se genera un postback que contiene el `gclid` o el `gbraid` y `wbraid` y parámetros de evento adicionales y se envía a Google Ads a través de la API OCI. Google Ads utiliza el `gclid` o `gbraid` y `wbraid` parámetro para identificar el clic específico, mientras que los demás parámetros ayudan a optimizar la campaña.

</Accordion>

<Accordion title="Configurar una landing page con Smart Script">

Para configurar tu Smart Script para campañas web de Google, sigue estos pasos:

1. Crea un Smart Script.

> 📘 **Note**
>
> Las instrucciones a continuación se centran en los pasos necesarios para configurar una campaña web de Google con Smart Script. Para obtener una guía completa sobre cómo configurar campañas de Smart Script, consulta la sección Cómo crear un Smart Script de OneLink del artículo Configuración de OneLink Smart Script V2.

1. Asegúrate de que todos los parámetros de URL relevantes (que luego son capturados por Smart Script) se anexen a la URL entrante. Para consultar los parámetros añadidos a la URL entrante, abre Google Ads y comprueba los parámetros de URL configurados al crear la URL final o la URL de la plantilla de seguimiento; consulta: [Configurar las URL de la campaña](#h_01J1MPPMW44NGXN55SFD16Z4HE).
2. Asigna los parámetros de URL de entrada necesarios para la campaña a los parámetros de URL de salida que se enviarán a AppsFlyer cuando el usuario haga clic en el CTA:
   * **PID**: Asegúrate de que Smart Script tome el valor del parámetro `pid=googleads_int` de la URL entrante y lo asigne a los parámetros correspondientes en la URL de salida.
   * **GCLID**: El parámetro `gclid` es esencial para enviar correctamente postbacks de eventos in-app a Google Ads. El mapeo del parámetro de URL GCLID de salida depende de tu versión de Smart Script:
     * Versión 2.8.1 y posteriores: El parámetro `gclid` se reenvía automáticamente al parámetro de URL de salida cuando está presente en la URL entrante, lo que elimina la necesidad de una asignación manual.
     * Versión 2.8.0 y anteriores: El parámetro `gclid` debe asignarse manualmente en la sección **Asignación de parámetros de URL** de la página **Smart Script**:
       1. En **Asignación para**, selecciona **Parámetro personalizado**.
       2. En **Parámetro URL de salida** y **Parámetros URL de entrada** introduce **gclid**.
   * **GBRAID** y **WBRAID**: Los parámetros `gbraid` y `wbraid` son esenciales para enviar correctamente postbacks de eventos in-app a Google Ads para usuarios de dispositivos iOS que no dan su consentimiento. La asignación de los parámetros `gbraid` y `wbraid` en la URL de salida depende de la versión de tu Smart Script:
     * Versión 2.9.0 y posteriores: Los parámetros `wbraid` y `gbraid` se reenvían automáticamente a los parámetros de la URL de salida cuando están presentes en la URL de entrada, eliminando la necesidad de asignarlos manualmente.
     * Versión 2.8.1 y anteriores: Los parámetros `wbraid` y `gbraid` deben asignarse manualmente en la sección **Asignación de parámetros de URL** de la página **Smart Script**:
       1. En **Asignación para**, selecciona **Parámetro personalizado**.
       2. En **Parámetro de URL de salida** y **Parámetros de URL de entrada** introduce **wbraid**.
       3. Repite los pasos anteriores para el parámetro `gbraid`.

> 📘 **Note**
>
> Para que se muestren en los Reportes de raw data de AppsFlyer, los parámetros gclid, gbraid y wbraid de la URL de entrada deben asignarse individualmente a un parámetro af\_sub[1-5] de salida específico (además de los parámetros gclid, gbraid y wbraid de la URL de salida).

</Accordion>

<Accordion title="Configurar una página de destino multiplataforma de Smart Script">

En el caso de las landing pages no multiplataforma, el marketer suele ser responsable de generar automáticamente el Smart Script a través de la página de Smart Script de AppsFlyer. Sin embargo, cuando se trata de landing pages multiplataforma, el desarrollador crea el script en función de los parámetros enviados por el marketer.

Para configurar tu Smart Script para campañas web de Google, sigue estos pasos:

1. Activa tu plantilla de OneLink para la atribución multiplataforma; consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#crea-o-edita-una-plantilla-de-onelink-para-la-atribución-multiplataforma">Crear o editar una plantilla de OneLink para la atribución multiplataforma</Anchor>.
2. Asegúrate de que todos los parámetros de URL relevantes estén anexados a la URL entrante. Para revisar los parámetros añadidos a la URL de entrada, abre Google Ads y comprueba los parámetros de URL configurados al crear la URL final o la URL de la plantilla de tracking; consulta: [Configura las URL de la campaña](#h_01J1MPPMW44NGXN55SFD16Z4HE).
3. Decide para cada parámetro entrante el parámetro de salida al que se asignará. Por ejemplo, `af_site_id` en la URL de entrada se asignará a `af_site_id` en la URL de salida.
4. Decide el valor predeterminado para los parámetros de salida obligatorios que no pueden estar vacíos.
5. Envía a tu desarrollador la siguiente información:
   * El mapeo de parámetros de entrada y salida. El desarrollador creará un script que genere una URL directa saliente basada en el mapeo de parámetros entrantes y salientes.
   * Los valores predeterminados de los parámetros. El script rellenará los parámetros de la URL saliente con los valores predeterminados siempre que no haya valores de parámetros de URL entrantes correspondientes.
   * Si utilizas un enlace de atribución de OneLink, envía a tu desarrollador el ID del dominio y de la plantilla. El desarrollador utiliza esto para crear la URL saliente de OneLink. Por ejemplo: `your_brand.onelink.me/A1b2` o ejemplo de dominio de marca: `click.yourbrand.com/A1b2`
   * Envía a tu desarrollador los siguientes enlaces de Dev Hub:
     * [Instrucciones y ejemplos de código](https://dev.appsflyer.com/hc/docs/create-direct-click-url) sobre cómo crear las URL directas salientes a plataformas no móviles.
     * [Una demostración e instrucciones](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) para crear una landing page multiplataforma.
   * Cuando está presente en la URL entrante, el parámetro `gclid` se reenvía automáticamente al parámetro de la URL saliente, eliminando la necesidad de asignación manual (a partir de la versión 2.8.1 de Smart Script). Tu desarrollador todavía tiene la opción de asignar el `gclid` a uno de los parámetros `af_sub`, para que esté disponible en los Reportes de raw data; consulta Google Ads GCLID.

</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## Crea una landing page con Smart Banners de OneLink

**Recorrido del usuario:** El usuario hace clic en un anuncio de Google y es dirigido a tu sitio web móvil. Llega a una página y se muestra un Smart Banner con una llamada a la acción para descargar la aplicación de la tienda de aplicaciones.

<Accordion title="Flujo de datos end-to-end">

1. El usuario hace clic en un anuncio de Google, Google automáticamente agrega a la URL final lo siguiente:
   * un parámetro `gclid` para dispositivos Android y para usuarios que consienten en dispositivos iOS.
   * un `gbraid` y un `wbraid` para usuarios de dispositivos iOS que no consienten.
   * todos los parámetros de consulta establecidos en la URL de plantilla de seguimiento de Google, excepto los parámetros de redirección.
2. Al mismo tiempo, la URL de la plantilla de seguimiento de Google detrás del anuncio, que contiene el parámetro `gclid` agregado automáticamente y el parámetro `pid=googleads_int` , se activa en segundo plano y el clic se registra con AppsFlyer.
3. Cuando se carga la landing page, el Smart Banner envía un evento de <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impresión</Anchor> a AppsFlyer, que incluye los parámetros de la URL entrante. Esta impresión habilita la atribución view-through para la landing page. Para obtener más información sobre impresiones y atribución view-through, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">Crear una URL de impresión personalizada</Anchor>.
4. El Smart Banner genera la URL de salida para el botón de llamada a la acción en el banner en función de los parámetros entrantes, incluido el parámetro `gclid`. El Smart Banner solo puede generar enlaces basados en OneLink.
5. Cuando el usuario hace clic en el botón de llamada a la acción del Smart Banner, el clic se activa y se registra en AppsFlyer.
6. El usuario es redirigido a la tienda y descarga la app.
7. El evento de instalación se registra en AppsFlyer cuando el usuario abre la aplicación.
8. AppsFlyer atribuye la instalación en función del Modelado probabilístico o de forma determinista si hay disponible una [Referencia de instalación](https://www.appsflyer.com/glossary/install-referrer/).
9. Se genera un postback que contiene el `gclid` y los parámetros de eventos adicionales y se envía a Google Ads a través de la API OCI. Google utiliza el parámetro `gclid` para identificar el clic específico, mientras que los demás parámetros ayudan a optimizar la campaña.

</Accordion>

<Accordion title="Configurar una landing page de Smart Banners">

> 📘 **Note**
>
> Las instrucciones a continuación se centran en los pasos necesarios para configurar una campaña web de Google con Smart Banners. Para obtener una guía completa sobre cómo configurar campañas de Smart Banners, consulta la sección de configuración en el artículo Smart Banners: de la web móvil a la aplicación (para marketers).

Para configurar tus Smart Banners para campañas web de Google, haz lo siguiente:

1. Crea un Smart Banner. Para obtener instrucciones, consulta la <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#configuración">sección de configuración</Anchor> del artículo <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners: de la web móvil a la aplicación (para marketers)</Anchor>.
2. Asegúrate de que la URL de entrada incluya lo siguiente:
   * El `pid=googleads_int` está disponible en la URL entrante.
   * El parámetro `gclid` está disponible en la URL entrante. Smart Banners reenvía automáticamente el parámetro `gclid` a la URL de salida del banner. El parámetro `gclid` es necesario para que los postback in-app se entreguen correctamente a Google OCI.
   * Los parámetros `gbraid` y `wbraid` están disponibles en la URL entrante al enviar postbacks para usuarios de dispositivos iOS que no consienten. Los Smart Banners reenvían automáticamente estos parámetros a la URL del banner de salida. En este caso, los parámetros `gbraid` y `wbraid` permiten que Google obtenga datos de eventos agregados en ausencia del parámetro `gclid`.
   * Asegúrate de que todos los parámetros de URL relevantes estén anexados a la URL entrante. Para revisar los parámetros anexados a la URL entrante, abre Google Ads y comprueba los parámetros de la URL establecidos al crear la URL final o la URL de la plantilla de tracking; consulta: [Configura las URL de la campaña.](#h_01J1MPPMW44NGXN55SFD16Z4HE)
3. (Opcional) En la página de configuración del grupo de banners bajo la sección de **parámetros de atribución dinámica**, selecciona la primera casilla de verificación. Esta configuración garantiza que todos los parámetros del enlace entrante se añadan al enlace del Smart Banner.

</Accordion>

<div id="view-web-to-app-attribution-data" />

## Ver datos de atribución web-to-app

Aunque los eventos de conversión basados en web se envían a Google con el PID original `googleads_int`, se reportan en el Dashboard de AppsFlyer y en los Reportes de raw data con el PID `googleadwords_int`. Esto aplica tanto para eventos de conversión primaria como para eventos de asistencia de conversión.

Esta vista unificada de reportes te permite analizar el rendimiento de las campañas web y de apps en un solo lugar, incluidos los reportes completos de costos web y móviles.

<div id="view-in-the-dashboard" />

### Ver en el dashboard

Todas las atribuciones Web-to-app de Google aparecen en `googleadwords_int` en los dashboards Vista general y Actividad. Esto proporciona una vista única y consolidada de los resultados de campañas en todas las plataformas. Utiliza filtros y desgloses estándar para comparar el tráfico de aplicaciones y web en tus datos de Google Ads.

<div id="view-in-raw-data-and-api-reports" />

### Ver en reportes raw data y API

* **Las exportaciones de raw data y las respuestas de la API** incluyen el PID `googleadwords_int` en el campo `media_source` para la actividad web de Google. Para verificar los detalles de configuración de la campaña web, consulta el campo `original_url`, que muestra `googleads_int` como el PID utilizado durante la creación de campañas web.
* **Los reportes de postback** muestran `googleads_int` como la fuente de medios original a la que se envió el postback.

<div id="troubleshooting-in-app-events-postbacks" />

## Solución de problemas de postbacks de eventos in-app

Si los datos de eventos in-app no se muestran en Google Ads o Google Analytics, o si recibes el error de token faltante, asegúrate de que la siguiente configuración sea correcta antes de contactar al soporte:

<Accordion title="Configurar los permisos del token">

En Google Ads, asegúrate de que tu token de acceso tenga los permisos necesarios para subir conversiones offline:

1. Ve a Google Developers Console.
2. Asegúrate de que `uploadClickConversions` tenga el siguiente ámbito de OAuth: [`https://www.googleapis.com/auth/adwords`](https://www.googleapis.com/auth/adwords)
3. En AppsFlyer, en la pestaña de integración, haz clic en **Iniciar sesión con Google**.
4. Selecciona la cuenta de administrador de la cuenta MCC.
5. Haz clic en **Permitir**.

</Accordion>

<Accordion title="Customer ID de MCC">

Si tienes varias cuentas de Google Ads ejecutando campañas para tu app, debes utilizar el Customer ID de una cuenta MCC. Consulta las [instrucciones de Google sobre cómo configurar una cuenta MCC](https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC).

</Accordion>

<Accordion title="ID de la acción de conversión">

Asegúrate de que los postbacks de eventos in-app estén asociados al ID de acción de conversión correcto. Para encontrar el ID de la acción de conversión en Google Ads, consulta [Encontrar el ID de la acción de conversión en Google Ads](#to-find-the-conversion-action-id-in-google-ads).

</Accordion>

<Accordion title="Parámetros GCLID, GBRAID, WBRAID">

La URL de salida de Smart Script o Smart Banners debe incluir `gclid`, `wbraid` o `gbraid` para que el postback a Google OCI se registre correctamente en Google Ads.

</Accordion>

<div id="traits-and-limitations" />

## Rasgos y limitaciones

| Caducado | Nota |
| --- | --- |
| <span id="dashboard"></span>Panel de Control | Los datos de atribución para campañas basadas en la web de Google en iOS se ven y analizan en el Dashboard Clásico de AppsFlyer. En la mayoría de los casos, el Dashboard de SKAN no es relevante para campañas web-to-app. |
| <span id="reengagement-attribution"></span>Atribución de re-engagement | Los usuarios pueden observar instalaciones atribuidas a `googleads_int` y re-engagement atribuidos a `googleadwords_int`, aunque ambos son impulsados por la misma campaña. Este comportamiento es esperado y no indica un problema técnico.   <br />  <br />Generalmente ocurre cuando una`googleadwords_int` integración SRN está activa, permitiendo que reclame el re-engagement de la misma campaña web2app de Google Ads. |
| <span id="cost-data"></span>Datos de impresiones, clics y costos | Los datos de costo para la red web de Google Ads (`pid=googleads_int`) no se recuperan automáticamente.<ul><li>Para obtener los datos, asegúrate de conectar la cuenta de la ad network al PID principal (`googleadwords_int`):<ul><li>Suscriptores del ROI360: en la página **Configuración de costos**,</li><li>ROI360 no suscriptores: en la página **Integración activa** (pestaña **Costo**).</li></ul></li><li>Para ver los datos de costo, clics e impresiones de las campañas web de Google Ads, asegúrate de que el ID de la campaña (<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>) esté incluido en el enlace de atribución.</li><li>El enlace de atribución debe incluir la jerarquía completa de la campaña para ver los datos de costo,  clics e impresiones vinculados a la atribución al nivel más granular.</li></ul> |
| <span id="tracking-template-urls"></span>URLs de plantilla de seguimiento | Las URLs de plantilla de seguimiento deben cumplir con las limitaciones a continuación. No hacerlo resultará en un enlace roto.<ul><li>Los enlaces no deben contener parámetros duplicados.</li><li>Los enlaces no deben incluir parámetros inválidos como:<ul><li>Parámetros sin valores, parámetros rotos o parámetros que no se pueden analizar. Esto incluye parámetros sin valores como `key=` o `key`. Por ejemplo: `pid=googleads_int&key&c=campaign` o `pid=googleads_int&key=&c=campaign`</li><li>Faltan valores en uno de los parámetros de ValueTrack, por ejemplo `{placement}`. Para evitar valores faltantes, asegúrate de que Google Ads los complete definiendo correctamente la plantilla de seguimiento en Google Ads.</li></ul></li><li>Si has ingresado valores para cualquier parámetro bajo la opción **URL de campaña** en la configuración de tu campaña de Google Ads, estos deben coincidir con los valores de los parámetros en la plantilla de seguimiento. Si no coinciden, elimínalos de la plantilla de seguimiento para garantizar el cumplimiento con la actualización de la política.</li></ul> |
| <span id="unexpected-srn-attribution"></span>Atribución SRN inesperada | En algunos casos, las instalaciones de campañas basadas en la web de Google Ads pueden atribuirse a `googleadwords_int` a través de SRN (red de autoreporte), incluso en campañas basadas en la web. Esto ocurre cuando Google reclama la instalación. AppsFlyer atribuye la instalación en consecuencia cuando Google hace la reclamación. Este comportamiento es esperado y puede volverse más común a medida que Google expande el soporte para la atribución de instalaciones de campañas web. |
| <span id="agency-managed-campaigns"></span>Campañas gestionadas por agencias | Si la campaña web la gestiona exclusivamente una agencia, las integraciones de `googleads_int` tanto del anunciante como de la agencia deben estar activas para que los postbacks lleguen a Google Ads. La agencia también debe completar [Iniciar sesión con Google](#h_01J1MPPMW3G9B1G116B18CRYJB) para aprovisionar un token de OAuth. Si omites este paso, la llamada de postback falla y no se envía a Google. |
| <span id="plan-availability"></span>Disponibilidad del plan | La integración `googleads_int` solo está disponible para los planes Growth y Enterprise. Los clientes en los planes Zero y Welcome no pueden usar esta integración. |

<div data-zendesk-anchors="overview=descripci%C3%B3n-general h_01J1MPPMW38A7EG2W8TJ8F6YQ3=descripci%C3%B3n-general prerequisite=requisito-previo h_01J1MPPMW3GWQKZVG2HAQA9H46=requisito-previo how-to-create-a-google-ad-web-campaign=c%C3%B3mo-crear-una-campa%C3%B1a-web-de-google-ads h_01J1MPPMW3ZYSPQHT4D2YAJ038=c%C3%B3mo-crear-una-campa%C3%B1a-web-de-google-ads create-a-google-ad-for-web-integration-in-appsflyer=crear-una-integraci%C3%B3n-de-google-ads-en-appsflyer h_01J1MPPMW3WTD63M686BHZNKDX=crear-una-integraci%C3%B3n-de-google-ads-en-appsflyer create-a-web-campaign-in-google-ads=crear-una-campa%C3%B1a-web-en-google-ads h_01J1MPPMW4AQNQEKBN1VSPM4X7=crear-una-campa%C3%B1a-web-en-google-ads set-the-final-url=establecer-la-url-final h_01J1MPPMW48F7X2NYEA735BG51=establecer-la-url-final set-the-tracking-template-url=establecer-la-url-de-la-plantilla-de-seguimiento h_01J1MPPMW44596CZVKF9MGDTMP=establecer-la-url-de-la-plantilla-de-seguimiento google-tracking-template-url-examples=ejemplos-de-url-de-plantilla-de-seguimiento-de-google 01JCZQR9RJAZF4SJVVKYZNJNPY=ejemplos-de-url-de-plantilla-de-seguimiento-de-google using-the-tracking-template-url-with-smart-script-or-smart-banners=uso-de-la-url-de-plantilla-de-seguimiento-con-smart-script-o-smart-banners 01JCZQR9RMAW9YP3T3679JAX45=uso-de-la-url-de-plantilla-de-seguimiento-con-smart-script-o-smart-banners create-a-landing-page-with-onelink-smart-script=crear-una-landing-page-con-smart-script-de-onelink h_01J1MPPMW4P7Q18JN7JS9ZXR23=crear-una-landing-page-con-smart-script-de-onelink create-a-landing-page-with-onelink-smart-banners=crea-una-landing-page-con-smart-banners-de-onelink h_01J1MPPMW4CW8JMJK26PTEY74W=crea-una-landing-page-con-smart-banners-de-onelink google-view-web-to-app=ver-datos-de-atribuci%C3%B3n-web-to-app view-webtoapp-attribution-data-from-november-2-2025=ver-datos-de-atribuci%C3%B3n-web-to-app h_01K88H6ETM23EV0PTR8GS13KRN=ver-datos-de-atribuci%C3%B3n-web-to-app view-in-the-dashboard=ver-en-el-dashboard h_01K88H6ETMG7007CJ0ADD8VQH4=ver-en-el-dashboard view-in-raw-data-and-api-reports=ver-en-reportes-raw-data-y-api h_01K88H6ETM502Z2XDC63602FGD=ver-en-reportes-raw-data-y-api troubleshooting-inapp-events-postbacks=soluci%C3%B3n-de-problemas-de-postbacks-de-eventos-in-app h_01J52V5G2DSF9PW9Z5GJHAD376=soluci%C3%B3n-de-problemas-de-postbacks-de-eventos-in-app traits-and-limitations=rasgos-y-limitaciones 01JDW5XHD92VFJ93671YP4JMFQ=rasgos-y-limitaciones" />

---
title: Configura Google Ads Web en AppsFlyer
metadata:
  keywords:
    - google ads configuration
    - google ads
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2024-01-18T11:04:33Z'
  edited_at: '2026-09-17T00:27:24Z'
  id: 21768823915665
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/21768823915665
---
> **En resumen:** Utiliza campañas web de Google Ads para promocionar tus aplicaciones en plataformas de PC y consolas y habilita la atribución. AppsFlyer admite campañas web de Google que utilizan landing pages multiplataforma o enlaces de atribución directa.

<div id="note" />

> 📘 **Nota:**
>
> Este artículo se centra en campañas web que promueven aplicaciones de PC o consola. Si deseas crear campañas web que promuevan aplicaciones móviles, consulta <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-based-campaigns">Google Ads (AdWords): Crea campañas basadas en la web</Anchor>.

<div id="overview" />

## Nota

Este artículo contiene información y pasos sobre cómo configurar y utilizar Google Ads Web para aplicaciones de PC y consola con AppsFlyer. Esto incluye:

* [Activación de la integración del partner en AppsFlyer](/docs/google-ads-web-integration-for-pc-and-console-apps#activar-partners-en-appsflyer).
* /docs/google-ads-web-integration-for-pc-and-console-apps#setting-up-Googleadsweb-in-appsflyer
* [Configuración de campañas en Google Ads para aplicaciones de PC y consola](/docs/google-ads-web-integration-for-pc-and-console-apps#configura-campañas-en-google-ads-web-para-aplicaciones-de-pc-y-consola).

<div id="prerequisites" />

### Requisitos previos

Antes de activar la integración de Google Ads Web, asegúrate de tener:

* Una aplicación para PC o consola
* Una cuenta de AppsFlyer
* Un token de acceso de Google con el <Anchor target="_blank" href="https://www.googleapis.com/auth/adwords">alcance OAuth requerido</Anchor>. Poder verificar los alcances asociados con tu token de acceso en Google Developer Console.
* <Anchor target="_blank" href="/marketers/es/docs/user-management">Usuarios de AppsFlyer con roles/permisos apropiados</Anchor> y acceso a las aplicaciones relevantes

<div id="activate-partner-in-appsflyer" />

## Activar partners en AppsFlyer

**Para activar la integración de partners:**

1. En AppsFlyer, en el menú lateral, ve a la pestaña **Collaborate** > **Partner Integrations > Marketplace**.
2. Busca **Google Ads Web** y selecciónalo o haz clic en **Integrate**.
3. Se te redirige a la página de configuración.
4. En la pestaña **Integración**, activa **Activar partner**.  
   **Nota: <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">El conmutador debe permanecer activado (</Anchor><Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor>) mientras trabajes con el partner.**
5. Completa la configuración usando las pestañas relevantes, como se describe en la siguiente sección.

<div id="set-up-google-ads-web-in-appsflyer" />

## Configura Google Ads Web en AppsFlyer

En esta parte de la configuración, también puedes configurar postbacks para Google Ads. La integración web de Google Ads (googleads\_int) utiliza una herramienta de API proporcionada por Google Ads para que los anunciantes envíen datos desde sus **aplicaciones de PC y consola** directamente a los servidores de Google. Dichos datos pueden incluir acciones del usuario, como compras, registros y otros tipos de conversiones realizadas en plataformas no móviles (sitios web o aplicaciones). Luego, Google Ads utiliza los datos para optimizar el targeting de los anuncios, medir el rendimiento de los mismos y crear audiencias personalizadas para el retargeting.

La integración con Google Ads Web solo admite el envío de postbacks para instalaciones y eventos in-app.

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

La pestaña **Integración** incluye una serie de secciones, como se describe a continuación.

<div id="activate-partner" />

#### Activar partner

Para configurar la integración, primero debes activar el selector **Activar partner**.

<div id="general-settings" />

#### Configuración general

<div id="note-1" />

> 📘 **Nota:**
>
> El mensaje de error de token faltante dejará de aparecer una vez que inicies sesión con Google y permitas que AppsFlyer obtenga el token en el paso siguiente. Si el error persiste después de iniciar sesión, <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-based-campaigns#access-token-permissions">verifica que tu token tenga los permisos requeridos</Anchor>.

1. **Primero abre el ID de conversión**: Ingresa el ID de la acción de conversión configurado en Google Ads. Para encontrar el ID:
   1. Ve a la plataforma de Google Ads y abre la pestaña **Detalles** de la página de la acción de conversión de **Primera apertura**.
   2. Copia el valor del parámetro de consulta `ctid=*` de la URL de la página. Por ejemplo, si `ctid=123456789`, inserta `123456789` en el cuadro de **ID de acción de conversión de primera apertura**.
2. Ingresa tu **ID de cliente**. Puedes recuperarlo desde tu Google Ads Manager:
   1. Inicia sesión en tu cuenta de Google Ads.
   2. En la esquina superior derecha, haz clic en el icono de la cuenta de Google y desplázate hacia abajo hasta donde se muestra el ID de cliente.
   3. Si tienes varias cuentas de Google Ads que ejecutan campañas para tu aplicación, debes usar el ID de cliente de un administrador (MCC) para el seguimiento de conversiones de varias cuentas. Pega el **MCC ID** (y no el Customer ID de una cuenta específica) en el cuadro de texto **Customer ID** y también en el cuadro de texto **MCC Customer ID** (el mismo ID en ambos cuadros).   
      Si solo utilizas una cuenta de Google Ads para publicar anuncios, pega el ID de la cuenta en el cuadro de texto **Customer ID** y deja vacío el cuadro de texto **MCC Customer ID**. Consulta las <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">Instrucciones de Google sobre cómo configurar una cuenta MCC</Anchor>.
3. Para permitir que AppsFlyer suba conversiones a Google Ads, haz clic en **Iniciar sesión con Google**.
4. Selecciona la cuenta de administrador de la cuenta MCC de la que recuperaste el ID de cliente en el paso 7.
5. Haz clic en **Permitir**.

<div id="enable-view-through-attribution" />

#### Habilitar la atribución view-through

AppsFlyer admite la atribución view-through a través de campañas web de Google utilizando un <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-based-campaigns#crear-una-landing-page-con-smart-script-de-onelink">Smart Script</Anchor> o una landing page habilitada para <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-based-campaigns#crea-una-landing-page-con-smart-banners-de-onelink">Smart Banner</Anchor>. Esto permite la atribución de instalaciones de aplicaciones mediante modelado probabilístico (PMOD) desencadenadas por impresiones de anuncios, incluso cuando los usuarios no hacen clic directamente en el anuncio.

Cuando un usuario ve un anuncio de Google y aterriza en una página de destino habilitada para <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-based-campaigns#crear-una-landing-page-con-smart-script-de-onelink">Smart Script</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-based-campaigns#set-up-a-smart-banners-landing-page">Smart Banner</Anchor>, AppsFlyer puede atribuir la instalación de la aplicación resultante, incluyendo la multiplataforma, de vuelta a la impresión web original.

Cuando está disponible, AppsFlyer incluye `gclid` en el postback a Google.

**Habilitar la atribución view-through:**

1. En AppsFlyer, desde la barra lateral, abre **Integraciones activas** > **Google Ads Web**.
2. En la pestaña **Integración**, desplázate a la sección **Atribución de instalación**.
3. Activa **Atribución de instalaciones por view-through**.
4. **[opcional]** Activa la opción **prioridad de atribución equitativa entre plataformas** y establece su ventana de lookback. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Habilitar prioridad equitativa para impresiones entre plataformas</Anchor>.
5. Abre la pestaña **Atribución**.
6. Desplázate a la sección **Atribución view-through** y establece la **ventana de lookback view-through** preferida (hasta 24 horas).
7. Haz clic en **Guardar integración** para aplicar los cambios.

<div id="default-postbacks" />

#### Postbacks predeterminados

Los postbacks de instalaciones se envían automáticamente solo a Google Ads Web.

<div id="in-app-event-postbacks" />

#### Postbacks de eventos in-app

Configura la asignación de postbacks de eventos in-app enviados a Google Ads Web. Estos eventos se pueden ver en el Google Ads Manager:

1. Activa **postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. La siguiente tabla describe los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<ul><li>Haz clic en **Agregar elemento**, ingresa el nombre del evento y haz clic en ![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png).</li></ul> |
| **Asignado al evento de partner** | El ID de acción de conversión de cada evento, tal como se define del lado del partner.<ol><li>En la página de **Objetivos de conversión** de Google Ads, haz clic en la acción de conversión que has creado.</li><li>En la página de **Detalles** de la acción de conversión, copia el **ID de acción de conversión** del parámetro de URL `ctId=`.</li><li>Regresa a AppsFlyer y pégala. Por ejemplo, si `ctid=123456789`, pega `123456789`.</li></ol> |
| **para usuarios de** | **Sólo este partner:** Los postbacks de eventos in-app se envían solo para eventos atribuidos a este partner, es decir, el usuario que los realizó proviene de este partner. |
| **incluyendo** | **Valores e ingresos:** Todos los parámetros del evento, incluyendo el valor de los ingresos (si existe en el evento), se envían en el postback. |

3. [Opcional] Haz clic en el ícono **Agregar condiciónaltconditional-iae-postbacks-icon.pngalt para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.**
4. Establece la **ventana de postbacks de eventos in-app**, si es necesario (lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">configuración de la ventana de postbacks de eventos in-app</Anchor>).
5. Haz clic en **Guardar integración**.
6. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repita los pasos de integración para la aplicación seleccionada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

La generación de un enlace de atribución en la interfaz de usuario de AppsFlyer no está disponible actualmente. Sin embargo, puedes usar una landing page multiplataforma con SmartScript o crear un enlace de atribución directa para tu aplicación (consulta la tabla a continuación).

| Opción | Acciones | ¿Quiénes están involucrados? |
| --- | --- | --- |
| Landing page multiplataforma | **Recomendado**: Para cuando tu campaña promociona una aplicación que también está disponible en múltiples plataformas, como Epic y Steam.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Más información sobre las landing pages multiplataforma</Anchor><br /><br /><Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Más información sobre cómo configurar una landing page multiplataforma</Anchor><ul><li>Asegúrate de que todos los parámetros de URL relevantes (que luego son capturados por Smart Script) se anexen a la URL del anuncio.</li><li>Asegúrate de que el script tome el GCLID de la URL de entrada y lo agregue al enlace generado. Es decir, asignar el parámetro de URL GCLID de salida `gclid` al parámetro de URL de entrada `gclid`.<br />[Práctica recomendada]: ¡**Importante**! Para mostrarlo en los reportes de raw data de AppsFlyer, el parámetro de entrada `gclid` también debe asignarse a uno de los parámetros de salida `af_sub[1-5]`.</li></ul> | Marketer (puede requerir la asistencia del desarrollador) |
| Enlace de atribución directa | Si no utilizas una landing page multiplataforma porque solo tienes 1 aplicación en 1 plataforma, puedes crear enlaces de atribución directa para colocarlos detrás de los anuncios.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor><ul><li>Asegúrate de que los siguientes parámetros estén incluidos en tu enlace:<ul><li>media\_source</li><li>af\_campaign\_id</li><li>af\_r<br />**Nota**: El <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">identificador de clic de Google (GCLID)</Anchor> se añade automáticamente por Google Ads a cualquier clic de salida si estás utilizando el <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3095550?hl=en">etiquetado automático</Anchor>. Si el etiquetado automático está desactivado en tu cuenta de Google Ads, añade `gclid={gclid}` a la URL de la plantilla de seguimiento de Google Ads.</li></ul></li><li>Para los parámetros af\_camapign\_id, af\_adset\_id y af\_ad\_id, puedes utilizar las macros de [parámetros de seguimiento de valor](https://support.google.com/google-ads/answer/6305348) de Google (parámetro de URL dinámica). Todos los demás parámetros deben configurarse manualmente.</li><li>No incluyas el parámetro af\_dp.</li></ul>**Plantilla para usar en la mayoría de las plataformas (Epic, Steam, Xbox, PlayStation, etc.)**:<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}? af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Enlace de muestra que conduce a Steam**: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Plantilla para usar SÓLO con las aplicaciones de Google para PC y Mac**:<br /><br />`https://app.appsflyer.com/{app_id}?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Enlace de muestra que conduce a Google PC**: `https://app.appsflyer.com/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}` | Comercializador |

<div id="tip" />

> 👍 **Consejo**
>
> Para simplificar el análisis de campañas, incluye el tipo de campaña, web o móvil, como prefijo o sufijo en el nombre de la campaña (por ejemplo, campaign-name\_web)

</Accordion>

<div id="set-up-campaigns-in-google-ads-web-for-pc-and-console-apps" />

## Configura campañas en Google Ads Web para aplicaciones de PC y consola

Cuando configuras una nueva campaña, puedes dirigir a los usuarios a:

* `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?` af\_media\_source=googleads\_int&af\_campaign\_id=`{campaignid}&af_campaign={campaignname}&af_adset={adgroupname}&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`
* Tienda única: Esto utiliza un enlace de atribución directa y debe usarse cuando solo tienes 1 aplicación en 1 plataforma.

Las instrucciones para configurar campañas para redireccionar a los usuarios a cualquiera de estas opciones se detallan en las secciones siguientes.

**Nota**: Durante la configuración de la campaña, es posible que desees configurar tus propias acciones y objetivos de conversión. Las instrucciones sobre cómo hacer esto también se detallan en las secciones siguientes.

<div id="campaigns-that-redirect-to-a-crossplatform-landing-page" />

<Accordion title="Campañas que redireccionan a una landing page multiplataforma">

**Para configurar una campaña que redirecciona a los usuarios a una landing page multiplataforma**:

1. Configura una landing page multiplataforma como se describe en la [sección de enlaces de atribución](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab).
2. Inicia sesión en Google Ads y crea una nueva campaña.
3. Selecciona un objetivo de campaña.  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * Todos los objetivos son aplicables, excepto "Promoción de aplicaciones" (que solo se puede utilizar para campañas de aplicaciones móviles).
   * Recomendamos establecer el objetivo de la campaña "Ventas" para la optimización en función de eventos in-app específicos.
4. Selecciona los objetivos de conversión.  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * De forma predeterminada, verás los objetivos de campaña predefinidos a nivel de cuenta. Puedes conservarlos o eliminar los que no sean relevantes para tu campaña.
   * Si no ves el objetivo que deseas,[agrega la acción de conversión y el objetivo de conversión](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals).
   * También puedes editar tus objetivos predefinidos en la página de conversiones.
5. Selecciona el tipo de campaña.  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * Todos los tipos de campaña son aplicables, excepto "Compras", que requiere un catálogo de productos y está limitada a dominios verificados.
6. Ingresa la URL de la landing page multiplataforma como URL final de Google.

</Accordion>

<div id="campaigns-that-redirect-to-a-single-app-store" />

<Accordion title="Campañas que redireccionan a una única tienda de aplicaciones">

**Para configurar una campaña que redirecciona a los usuarios a una única plataforma y tienda de aplicaciones**:

1. Configura un enlace de atribución directa como se describe en la sección [Enlace de atribución](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab).
2. Inicia sesión en Google Ads y crea una nueva campaña.
3. Selecciona un objetivo de campaña.  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * Todos los objetivos son aplicables, excepto "Promoción de aplicaciones" (que solo se puede utilizar para campañas de aplicaciones móviles).
   * Recomendamos establecer el objetivo de la campaña "Ventas" para la optimización en función de eventos in-app específicos.
4. Selecciona los objetivos de conversión.  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * De forma predeterminada, verás los objetivos de campaña predefinidos a nivel de cuenta. Puedes conservarlos o eliminar los que no sean relevantes para tu campaña.
   * Si no ves el objetivo que deseas,[agrega la acción de conversión y el objetivo de conversión](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals).
   * También puedes editar tus objetivos predefinidos en la página de conversiones.
5. Selecciona el tipo de campaña.  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * Todos los tipos de campaña son aplicables, excepto "Compras", que requiere un catálogo de productos y está limitada a dominios verificados.
6. Ingresa el enlace que se utilizará como URL final de Google.
   * Esta debe ser la ubicación web final a la que deseas redireccionar a tus usuarios. Puede ser cualquier URL web, incluyendo una landing page web o una URL de tienda. Por ejemplo: `https://store.steampowered.com/app/{appid}/{myapp}/`.
   * La URL final no puede ser una URL de AppsFlyer, ya que esto puede provocar que se rechace tu campaña. Utiliza únicamente una dirección web directa que no tenga redireccionamientos.
7. Ingresa tu enlace de atribución directa de AppsFlyer como URL de la Plantilla de Seguimiento de Google.
   * Para que el seguimiento paralelo funcione según lo previsto, la URL final debe colocarse en el parámetro `{lpurl}` ValueTrack en la URL de la Plantilla de Seguimiento de Google, según lo especificado por Google.
   * No incluyas el parámetro af\_dp.

</Accordion>

<div id="creating-conversion-actions-and-goals" />

<Accordion title="Crea acciones de conversión y objetivos">

En Google Ads, puedes seleccionar de la lista predefinida de acciones y objetivos de conversión o crear los tuyos propios.

**¡Importante!** Para que AppsFlyer envíe un postback del evento "Primera apertura", debes crear una acción de conversión y llamarla "Primera apertura".

**Para crear tus propias acciones y objetivos de conversión de Google Ads**:

1. En la página de descripción general de tu cuenta de Google Ads, en el menú lateral, selecciona **Objetivos** > **Conversiones** > **Resumen**.
2. Haz clic en **+ Nueva acción de conversión**.
3. Nota
4. Selecciona **Importar** en la lista de tipos de conversión y luego selecciona **Importación manual mediante API o cargas** > **Seguimiento de conversiones a partir de clics**.

   <div id="note-2" />

   > 📘 **Nota:**
   >
   > Si la **importación manual usando API o cargas** no está disponible:
   >
   > 1. Selecciona **CRM, archivos u otras fuentes de datos** > **Rastrear conversiones de clics**.
   > 2. En **Fuente de datos** selecciona **Omitir este paso y configurar la fuente de datos más tarde**.

5. Haz clic en **Continuar**.  
   Se muestra un formulario.
6. Completa el formulario y haz clic en **Crear y continuar** para terminar de crear tu rastreador de conversiones.
7. Para **Optimización de objetivos y acciones**, selecciona una categoría para asignar tu acción de conversión.  
   **Nota**: La optimización de la campaña de Google Ads es por categoría; no por acción específica). Si solo deseas que tus campañas se optimicen para una sola acción, asegúrate de asignar solo esa acción a esta categoría. Por ejemplo, si deseas que tu campaña se optimice hacia la acción "instalar", asegúrate de asignar la acción "instalar" a su propia categoría, por ejemplo, "Otro". Luego podrás seleccionar esta categoría como objetivo de la campaña al crear la campaña.
8. Copia el ID de acción de conversión de Google Ads y pégalo en el campo mapeado al evento del partner. El ID de acción de conversión se utiliza como el ID de evento del partner al mapear el nombre del evento de AppsFlyer al ID de evento del partner en la configuración de postbacks de eventos in-app. Para copiar el ID de acción de conversión de Google Ads, realiza lo siguiente:
   1. En la página de **Objetivos de conversión** de Google Ads, haz clic en la acción de conversión creada.
   2. En la página de **Detalles** de acción de conversión, copia el **ID de acción de conversión** del parámetro `ctId=` de la URL y pégalo.
9. Haz clic en **Finalizar**.
10. Haz clic en **Crear y continuar**.

</Accordion>

<div id="view-web-to-app-attribution-data-from-november-2-2025" />

## Ver datos de atribución web-to-app (a partir del 2 de noviembre de 2025)

Aunque los eventos de conversión basados en web se envían a Google con el PID `googleads_int` original, se reportan en el dashboard de AppsFlyer y en los reportes de raw data con el PID `googleadwords_int`. Esto aplica tanto para eventos de conversión primaria como para eventos de asistencia de conversión.

Esta vista unificada de reportes te permite analizar el rendimiento de las campañas web y de apps en un solo lugar, incluidos los reportes completos de costos web y móviles.

<div id="view-in-the-dashboard" />

### Ver en el dashboard

Todas las atribuciones web-to-app de Google aparecen en `googleadwords_int` en los dashboards Resumen y Actividad. Esto proporciona una vista única y consolidada de los resultados de campañas en todas las plataformas. Utiliza filtros y desgloses estándar para comparar el tráfico de la app y de la web dentro de tus datos de Google Ads.

<div id="view-in-raw-data-and-api-reports" />

### Ver en reportes raw data y API

* **Las exportaciones de raw data y las respuestas de la API** incluyen el PID `googleadwords_int` en el campo `media_source` para la actividad web de Google. Para verificar los detalles de configuración de la campaña web, consulta el campo `original_url` que muestra `googleads_int` como el PID utilizado durante la creación de campañas web.
* **Los reportes de postbacks** muestran `googleads_int` como la fuente de medios original a la que se envió el postback.

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Clics e impresiones (limitación temporal) | Los clics y las impresiones de las campañas orientadas a aplicaciones para PC & consola no están disponibles temporalmente en Google SRN (`googleadwords_int`). |

<div data-zendesk-anchors="h_01JP7SMGEPTQGHRYYCBWECH46X=nota overview=nota-1 h_01HK4QHRJG6WTN9P6ZG83XQ6AY=nota-1 prerequisites=requisitos-previos h_01HFXV8HPGCRGYPEW0NPJ0NR0S=requisitos-previos activate-partner=activar-partners-en-appsflyer h_01HFXV8HPH3N4DBKKTQE6DK7FK=activar-partners-en-appsflyer setting-up-metaweb-in-appsflyer=configura-google-ads-web-en-appsflyer 01H88VAJH3VENKYVRQY5RXN63P=configura-google-ads-web-en-appsflyer 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=activar-partner h_01HFXV8HPH6X92YETNAGZ910AV=activar-partner transaction-id=configuraci%C3%B3n-general h_01HARQDVEDA206D0BBXBC6WEHH=configuraci%C3%B3n-general h_01JK8XJJWQK5MEJF7GTC5C1707=nota-2 enable-viewthrough-attribution=habilitar-la-atribuci%C3%B3n-view-through h_01ZXVWB0GZKWB53KTBWJ51RMBM=habilitar-la-atribuci%C3%B3n-view-through default-postbacks=postbacks-predeterminados 01H88VAJH3WE9Z0971WMBRBJRS=postbacks-predeterminados inapp-event-postbacks=postbacks-de-eventos-in-app 01H88VAJH3AS37MVF75GANWX4B=postbacks-de-eventos-in-app 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab h_01K88M617Q7SVMDEKP5HTKANJM=consejo setting-up-campaigns-in-meta-web-for-pc-and-console-apps=configura-campa%C3%B1as-en-google-ads-web-para-aplicaciones-de-pc-y-consola h_01HK4S03KVAN99YKXTHAKCT420=configura-campa%C3%B1as-en-google-ads-web-para-aplicaciones-de-pc-y-consola h_01HMR6HVJF4QT1EZKYZKRVTWEE=campaigns-that-redirect-to-a-crossplatform-landing-page h_01HMR6HVJFMN1V7VM58ZMQFEXF=campaigns-that-redirect-to-a-single-app-store h_01HMTXEZB3W19TKK8ZR6JK2TPG=creating-conversion-actions-and-goals h_01HV6FR2TFYT11H9EVT9Y9TZ3S=nota-3 google%20view-web-to-app=ver-datos-de-atribuci%C3%B3n-web-to-app-a-partir-del-2-de-noviembre-de-2025 view-webtoapp-attribution-data-from-november-2-2025=ver-datos-de-atribuci%C3%B3n-web-to-app-a-partir-del-2-de-noviembre-de-2025 h_01K88H6ETM23EV0PTR8GS13KRN=ver-datos-de-atribuci%C3%B3n-web-to-app-a-partir-del-2-de-noviembre-de-2025 view-in-the-dashboard=ver-en-el-dashboard h_01K88H6ETMG7007CJ0ADD8VQH4=ver-en-el-dashboard view-in-raw-data-and-api-reports=ver-en-reportes-raw-data-y-api h_01K88H6ETM502Z2XDC63602FGD=ver-en-reportes-raw-data-y-api traits-and-limitations=especificaciones-y-limitaciones h_01KB5085FX7G6Y5E200KVH0ABJ=especificaciones-y-limitaciones" />

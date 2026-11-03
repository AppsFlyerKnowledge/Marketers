---
title: Configuración de integración de Apple Ads (Search Ads)
metadata:
  keywords:
    - cost
    - Advertisers
    - apple search ads
    - asa
    - apple ads
    - apple search advanced
    - apple search ads campaign group
    - apple keywords
    - apple searchads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-31T09:04:38Z'
  edited_at: '2026-10-29T01:21:03Z'
  id: 213747963
  locale: es
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/es/articles/213747963
---
> **At a glance:** Apple Ads, un partner de red de autorreporte (SRN) de AppsFlyer, ayuda a los usuarios a encontrar tu aplicación en la tienda de aplicaciones mediante palabras clave.

<Image alt="medium_originaljpeg_apple_ads_logo_blk_highres_720 (1) (1).jpg" src="https://files.readme.io/f89d1a5ec1a1de2ec2dfdec7465465fc2be73e0cf41ddd6be8b2e3f62de3c9e8-47598828154001.jpg" width="719px" />

La relevancia de la aplicación determina si tu anuncio es el que se muestra en respuesta a una query de búsqueda en la App Store. La respuesta del usuario a un anuncio es una señal de la relevancia del mismo. Apple Ads utiliza las respuestas de los usuarios como una señal para decidir qué anuncios mostrar con más frecuencia.

> 📘 **Note**
>
> * AppsFlyer ofrece soporte para la atribución móvil basada en clics de Apple Ads, el retargeting de usuarios y los datos de costo a través de la API (con una suscripción a ROI360).
> * A partir del 27 de marzo de 2025, AppsFlyer también admitirá la atribución móvil basada en impresiones de Apple Ads.
> * A partir del 1 de septiembre de 2026, Apple Ads añade un timestamp exacto a todas las reclamaciones de atribución de iOS.

## Configurar la integración de Apple Ads

<Accordion title="Comienza">

**Requisito previo:**

* Tener adoptada la versión más reciente del SDK de AppsFlyer para iOS

**Configura Apple Ads en AppsFlyer:**

La configuración se realiza desde la página **Integraciones activas**, pero para encontrar nuevos partners primero debes ir a <Anchor target="_blank" href="/marketers/es/docs/partner-integrations">Marketplace de partners</Anchor>. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación.

> 📘 **Note**
>
> Antes de configurar una integración, asegúrate de contactar al partner y abrir una cuenta con este.

</Accordion>

<Accordion title="Pestaña de Integración">

Apple Ads, una SRN, se integra con AppsFlyer a través de API. Como tal, no hay ninguna configuración de postback. Completa las siguientes secciones de acuerdo con tus metas de atribución.

<table><thead><tr><th>Sección. </th><th>Detalles</th></tr></thead><tbody><tr><td>Activación de la integración</td><td><p><strong>Para configurar una nueva integración:</strong></p><ol><li>En AppsFlyer, ve a la pestaña <strong>Colaborar &gt; Integraciones de partners &gt; Marketplace</strong>.</li><li>Selecciona la aplicación correspondiente. </li><li>Busca el partner y selecciona <strong>Integrar</strong>.</li><li>En la pestaña <strong>Integración</strong>, activa el selector <strong>Activar partner</strong>. Mantenlo activado mientras trabajes con el partner.</li><li>Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación.</li></ol><p><strong>Para editar una integración existente:</strong></p><p>En AppsFlyer, ve a la pestaña <strong>Colaborar &gt; Integraciones de partners &gt; Integraciones activas</strong>, busca el partner y haz los cambios que necesites.</p></td></tr><tr><td>Atribución click-through en la instalación</td><td><ol><li><p><strong>Configura la ventana de lookback de clics de instalación</strong><br/>Define el tiempo máximo entre el clic en el anuncio y la instalación. Esto permite que AppsFlyer atribuya a Apple Ads las instalaciones (primeras aperturas) que tienen lugar dentro de la ventana de lookback.</p><ul><li> <strong>Rango:</strong> 1–30 días</li><li> <strong>Valor predeterminado:</strong> 30 días</li></ul><p>Para más información, consulta <a href="./set-up-lookback-windows" target="_blank">Explicación de las ventanas de lookback</a>.</p></li></ol><ol><li> <strong>Medición de campañas de preregistro (pedido anticipado)</strong><br/>Si ejecutas campañas de preregistro para aplicaciones de iOS, configura la ventana de lookback de la campaña de preregistro. <br/>Este control deslizante determina la ventana de lookback utilizada para atribuir instalaciones a campañas de preregistro.<br/>La ventana de lookback de preregistro permite atribuir las instalaciones que se producen cuando se lanzan las aplicaciones preregistradas (pedidas por adelantado), vinculándolas a la interacción original con el anuncio. <ul><li> <strong>Rango:</strong> 1–90 días</li><li> <strong>Valor predeterminado:</strong>  90 días</li></ul></li></ol></td></tr><tr><td>Atribución view-through en la instalación</td><td><ol><li><p><span><strong>Configura la ventana de lookback view-through de instalación</strong></span><br/>Configura el tiempo máximo desde la visualización del anuncio hasta la instalación. AppsFlyer atribuye a Apple Ads las instalaciones (primeros inicios) que se producen dentro de esta ventana. <strong>Nota:</strong> El control deslizante de la ventana de lookback view-through de la instalación solo admite horas (máx.: 24 h; valor predeterminado: 24 h). </p><ul><li> <strong>Rango:</strong> 1–24 horas</li><li> <strong>Valor predeterminado:</strong>  24 horas</li></ul><p>Para obtener más información, consulta <a href="./set-up-lookback-windows" target="_blank">Ventanas de lookback: explicación</a>.</p></li><li> <strong>Medición de campañas de preregistro (pedido anticipado)</strong><br/>Si ejecutas campañas de preregistro para aplicaciones de iOS, configura la ventana de lookback de la campaña de preregistro.<br/>Este control deslizante determina la ventana de lookback utilizada para atribuir instalaciones a campañas de preregistro.<br/>La ventana de lookback de preregistro permite atribuir instalaciones que se producen cuando se lanzan aplicaciones preregistradas (pedidas por anticipado), vinculándolas con el engagement original del anuncio.<ul><li> <strong>Rango:</strong> 1–61 días</li><li> <strong>Valor predeterminado:</strong> 61 días</li></ul></li></ol></td></tr><tr><td rowspan="2">Reinstalaciones </td><td><p><strong>Atribución de reinstalaciones</strong></p><p>Si <strong>la atribución de reinstalaciones está</strong> activada, AppsFlyer puede atribuir las reinstalaciones a Apple Ads.</p><p>La configuración de la ventana de lookback de la atribución de reinstalaciones se realiza de acuerdo con la configuración de la atribución de instalaciones.</p><p>Si el usuario se encuentra dentro de la <a href="./set-up-re-attribution-window" target="_blank">ventana de reatribución</a> (establecida en el momento de la instalación original), la instalación se atribuye a Apple Ads como una reinstalación.</p><p>La reinstalación se puede ver en la vista de retargeting del panel de control general.</p><p>El campo raw data <strong>Store reinstall</strong> se establece en true. </p><p>Actualmente, el retargeting de Apple Ads no admite re-engagements.</p></td></tr><tr><td><p><strong>Ventana de inactividad</strong></p><p>Configura el <a href="./set-retargeting-inactivity-window" target="_blank">umbral de inactividad</a> del usuario (en días) para controlar el impacto de las campañas de retargeting. </p></td></tr><tr><td>Devoluciones de mensajes</td><td>Actualmente, la integración de Apple Ads no admite postbacks.  </td></tr></tbody></table>

</Accordion>

<Accordion title="Pestaña de costo">

La integración de costos proporciona los siguientes datos agregados:

* Datos de costo de tus campañas, conjuntos de anuncios, geos/países y palabras clave. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad networks</Anchor> para obtener todos los detalles sobre las dimensiones, métricas y funciones compatibles.  
  **Nota:** Los datos de costo requieren una suscripción a ROI360.
* Datos sobre clics, impresiones y datos enriquecidos: palabras clave, nombres de campañas y conjuntos de anuncios.

> 📘 **Note**
>
> * Se admite el uso de varias cuentas de Apple Ads. En otras palabras, si ejecutas campañas para la misma aplicación con diferentes cuentas de Apple Ads, AppsFlyer puede recibir estos datos de todas las cuentas.
> * Varios usuarios de la misma cuenta de Apple Ads pueden conectar cada uno su propia integración de costos de Apple Ads. AppsFlyer mantiene cada integración de costos por separado. Cuando otro usuario de tu cuenta de Apple crea una nueva integración de costos con Apple, tu conexión se mantiene tal como está y no se sobrescribe. Cada integración de costos extrae datos de costo según los permisos de Apple Ads del usuario que ha iniciado sesión.
> * Los datos de costes de los "grupos de campañas" no son compatibles con la API de reportes de Apple Ads, por lo que los datos del "grupo de campañas" no están disponibles en AppsFlyer.
> * Para iniciar sesión con Apple, necesitas permisos de **gestión de grupos de campañas** de Apple Ads (ya sean de solo lectura o de lectura y escritura en la cuenta).
> * Cuando inicias sesión con Apple, la autorización de los grupos de campañas de Apple Ads no es acumulativa. Esto significa que, al integrar una nueva aplicación, la autorización de los grupos de campaña seleccionados en aplicaciones anteriores se revoca, a menos que se vuelvan a seleccionar.
> * Cuando inicias sesión con Apple, no puedes usar un inicio de sesión federado.

**Para habilitar los datos de costos, clics, impresiones y enriquecidos:**

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Consulta el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer datos de costo coincidentes, ya sea en el Dashboard de estado de la integración de costos (e ingresos por publicidad) o en el Dashboard individual de la ad network.

</Accordion>

<Accordion title="Pestaña de permisos">

<Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">Configurar permisos de ad network y agencia.</Anchor>

</Accordion>

## Configurar agencias y partners de marketing de Apple Ads

<Accordion title="Principios">

**Apple Search Ads: Partner de marketing vs Agencia**

Los anunciantes y las agencias pueden optar por trabajar con partners de marketing de Apple Ads para reportar y optimizar campañas en Apple Ads.

Las diferencias entre las agencias y los partners de marketing se describen en la tabla siguiente.

#### Agencia vs partner de marketing

|  | Agencia | Partner de marketing |
| --- | --- | --- |
| AppsFlyer envía postbacks | No | Sí |
| Tecnología | Ejecutar campañas por tu cuenta. | Disponer de una solución tecnológica de valor añadido para optimizar campañas |

#### Configuración de agencias y partners de marketing

Usa la siguiente lista de verificación para asegurarte de completar todos los pasos del proceso de configuración. En las secciones siguientes se proporcionan instrucciones detalladas para cada tipo de partner.

#### Lista de verificación de pasos de configuración

| Configurado por | Integración con una agencia | Integración con un partner de marketing |
| --- | --- | --- |
| AppsFlyer | <ol><li>En AppsFlyer, en la pestaña de integración de Apple Ads, activa **Activar partner.**</li><li>Selecciona la agencia; en la pestaña de permisos de la agencia, activa **Agency Permission.**</li></ol> | <ol><li>En la pestaña de integración de Apple Ads, activa **Activar partner.**</li><li>En el dashboard de Apple Ads, obtén el **ID del grupo de campaña** del partner de marketing.</li><li>En la pestaña integración del partner de marketing:<ol><li>Activa **Activar partner.**</li><li>Configura el grupo de campañas.</li><li>Configura los postbacks de eventos in-app.</li></ol></li></ol> |
| Agencia | En la pestaña de integración de Apple Ads, configura **Grupo de campaña de Apple Ads.** | <ol><li>En la pestaña de integración de Apple Ads, activa **Activar partner.**</li><li>En el dashboard de Apple Ads, obtén el **ID del grupo de campaña** del partner de marketing.</li><li>En la pestaña integración del partner de marketing:<ol><li>Activa **Activar partner.**</li><li>Configura el grupo de campañas.</li><li>Configura los postbacks de eventos in-app.</li></ol></li></ol> |

</Accordion>

<Accordion title="Configuración de partners de marketing">

**Para configurar un partner de marketing:**

1. Si es necesario, activa la **integración de Apple Search Ads:**
   1. En AppsFlyer, ve a **Configuración** > **Partners de integración activos** > **Apple Ads**.
   2. Activa **Activar partner.**
   3. Haz clic en **Guardar**.
2. **En tu dashboard de Apple Ads,** obtén el parámetro ID del grupo de campaña de Apple Ads relacionado con el partner de marketing. Utiliza la captura de pantalla a seguie como guía para localizar el ID.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **En AppsFlyer, configura el partner de marketing de Apple Ads:**
   1. En **AppsFlyer**, desde el menú lateral, selecciona **Colaboración** > **Integraciones activas.**
   2. Busca el ***partner de marketing de*** **Apple Search Ads**.  

      Se muestra la lista de partners de marketing.
   3. Selecciona un partner de marketing.
   4. Activa **Activar partner.**
   5. Introduce el **pple Search Ads Campaign Group ID** del partner que has conseguido en el paso anterior. Ingresa solo los dígitos (números).
   6. Haz clic en **Guardar**.
4. [Opcional] Configura los postbacks de eventos in-app:
   1. Activa **Postback de evento in-app.**
   2. Haz clic en **Añadir evento** para agregar un evento de SDK a la lista.
   3. Completa los siguientes parámetros:
      1. **Nombre del evento del SDK**: el nombre del evento tal como lo recibe AppsFlyer, ya sea desde el SDK integrado en tu aplicación o desde eventos de servidor a servidor. **Consejo:** Si no encuentras el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.
      2. **Enviar ingresos:** Selecciona uno de los siguientes: Sin valores y sin ingresos, Con valores y sin ingresos o Con valores e ingresos.
5. **Haz clic en Guardar integración**.

</Accordion>

<Accordion title="Configuración de agencias">

Los anunciantes permiten que las agencias realicen campañas en su nombre utilizando Apple Search Ads. Tanto los anunciantes como las agencias realizan acciones de configuración en AppsFlyer como se describe en esta sección.

**Requisitos previos**

Antes de configurar una agencia en AppsFlyer, tanto la agencia como el anunciante deben seguir estos pasos en la plataforma Apple Ads:

* **Agencia:**
  1. Crea grupos de campaña separados dentro de la cuenta de la agencia.
  2. Invita al anunciante como Campaign Group Manager o a través del rol de Link Accounts para conectar su cuenta de App Store Connect.
* **Anunciante:** Después de recibir la invitación para vincular cuentas, el anunciante debe vincular los grupos de campaña a su cuenta de App Store Connect.

Consulta la documentación de Apple Ads sobre <Anchor target="_blank" href="https://searchads.apple.com/help/get-started/0012-link-app-store-connect-accounts">Cómo vincular la cuenta de App Store Connect de un cliente a una cuenta de agencia.</Anchor>

**Grupo de campañas de Apple Search Ads**

* Las campañas de agencia y las campañas de anunciantes deben ser IDs de grupos de campaña de Apple Search Ads separados.
* No uses caracteres especiales ni espacios para el nombre del grupo.
* Cuando inicias sesión con Apple, la autorización de los grupos de campaña de Apple Ads no es acumulativa. Esto significa que al integrar una nueva aplicación, la autorización para los grupos de campaña elegidos para las aplicaciones anteriores se revoca a menos que se vuelva a elegir. Necesitarás seleccionar **Acceso limitado** y cada uno de los grupos de campaña relevantes (relacionados con las aplicaciones que deseas conectar para el anunciante).

#### **Acciones del anunciante**

**Requisito previo**:

<Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">Conceder permiso a una agencia</Anchor>

**Para habilitar la Atribución de Apple Ads, el anunciante:**

1. En **AppsFlyer**, desde el menú lateral, selecciona **Colaboración** > **Integraciones activas.**
2. Selecciona **Apple Search Ads.**
3. Ve a la pestaña **Integración**, activa **Activar partner**.
4. [Opcional] Si deseas atribuir a los usuarios que reinstalan la aplicación durante la ventana de reatribución, activa **Atribución de reinstalaciones**
5. Haz clic en **Guardar**.

#### **Acciones de la agencia**

1. **En tu dashboard de Apple Ads,** obtén tu ID de grupo de campaña. Utiliza la captura de pantalla a seguie como guía para localizar el ID. Obtén solo los dígitos.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
2. En AppsFlyer, selecciona una aplicación.
3. Desde el menú lateral, selecciona **Colaboración** > **Integraciones activas**.
4. Selecciona **Apple Search Ads.**
5. Ingresa el parámetro del **ID de campaña de Apple Search Ads**. ¡Atención! ¡Nota! Ingresa solo dígitos (solo números)
6. Haz clic en **Guardar**.

> 📘 **Note**
>
> Cuando una agencia trabaja con un partner de marketing de Apple Ads, debe configurar el mismo ID de grupo de campaña tanto en la página de configuración de Apple Ads como en la página de configuración del partner de marketing.

### Datos de impresiones, clics y costos

Si habilitas la API de costos, AppsFlyer recibe datos de costo, clics e impresiones de Apple Ads a través de la API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de la ad network</Anchor> para obtener detalles completos sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360. Sin ROI360, solo se reciben datos de clics e impresiones.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>. Asegúrate de que, cuando se te pida iniciar sesión en tu cuenta de Apple Ads en **Select permissions**, selecciones una de las siguientes opciones:
  * **Lectura y escritura de la cuenta**
  * **Cuenta Solo Lectura**  
     **Nota**: Si eliges Acceso Limitado y un grupo de campaña específico, puedes encontrar errores de datos.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Consulta el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer datos de costo coincidentes, ya sea en el Dashboard de estado de la integración de costos (e ingresos por publicidad) o en el Dashboard individual de la ad network.

> 📘 **Note**
>
> Los datos de costo de Apple Ads no están disponibles en el Dashboard de SKAdNetwork (SKAN) ni en la Pull API de SKAN porque los postbacks de SKAN no incluyen datos a nivel de campaña. Sin embargo, los datos de costos están disponibles en los reportes de SSOT, que combinan los datos de instalación de SKAN con la información de costos recuperada a través de nuestra integración clásica de Apple Search Ads.

</Accordion>

<Accordion title="Desactivación de agencias y partners de marketing">

**Para dejar de registrar la atribución de las instalaciones de Apple Search Ads generadas por agencias o partners de marketing:**

1. En **AppsFlyer**, desde el menú lateral, selecciona **Colaboración** > **Integraciones activas.**
2. Selecciona la agencia o el partner de marketing según sea el caso.
3. Elimina el contenido del **campo Apple Search Ads Campaign Group ID.**
4. Haz clic en **Guardar integración.** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

</Accordion>

## Información adicional

<Accordion title="Atribución de Apple Ads">

Apple Ads funciona independientemente de SKAdNetwork y atribuye a los usuarios de forma determinística, independientemente del consentimiento de ATT (App Tracking Transparency). Esto significa que, para los usuarios atribuidos a Apple Ads, tienes toda la gama de funciones y mediciones que proporciona nuestro <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">modelo de atribución de LTV.</Anchor>

La atribución de Apple Ads no depende del IDFA; la atribución se realiza mediante un token del dispositivo (atribución determinista).

#### Después del 1 de septiembre de 2026

La hora del clic y de la impresión está disponible independientemente del estado de ATT. La ventana de lookback la define el anunciante y AppsFlyer aplica sus reglas de atribución de último toque al engagement.

#### Antes del 1 de septiembre de 2026

La disponibilidad de la hora del clic y de la impresión, así como la ventana de lookback, varían según el consentimiento de ATT:

| **Consentimiento de la ATT** | **Tiempo de clic/impresión disponible** | **Ventana de lookback de clics/impresiones** | **Observaciones** |
| --- | --- | --- | --- |
| Sí | Sí | Establecido por el anunciante | Reglas de atribución de último toque de AppsFlyer utilizadas |
| No | No | Clics: 30 días (definidos por Apple Ads), Impresiones: 24 h | No se proporciona tiempo de clic o impresión. Se da prioridad a los candidatos deterministas |

</Accordion>

<Accordion title="Discrepancias">

AppsFlyer y Apple Ads usan una lógica de atribución diferente, lo que genera discrepancias entre las plataformas. <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#atribución">Apple Search Ads</Anchor>, una SRN, reporta las instalaciones nuevas por API.

**Apple Ads reporta a AppsFlyer por API**

* Las campañas se agregan por geolocalización.
* Lo siguiente no se informa: Impresiones, toques o costo de geos con menos de 100 impresiones para una campaña dada.
* Al agrupar por geolocalización en AppsFlyer, las geolocalizaciones con datos no disponibles no se muestran y el total de datos no disponibles aparece como N/A.

### Discrepancias relacionadas con el retargeting

El mecanismo de atribución de retargeting de AppsFlyer permite a los anunciantes medir y analizar campañas de retargeting, además de las campañas de adquisición de usuarios.

Las cifras que aparecen a continuación muestran cómo pueden producirse discrepancias en relación con las campañas de retargeting (independientemente de la configuración de los controles de retargeting) que se ejecutan en Apple Ads.

**Retargeting activado**

 ![ASA R Enabled2.jpg](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg) 

**Retargeting desactivado**

 ![ASA_R_Disabled.png](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png) 

### Razones adicionales para discrepancias

En la siguiente tabla se enumeran las principales razones.

| Discrepancia | Apple Search Ads | AppsFlyer |
| --- | --- | --- |
| <span id="differences-related-to-appsflyer-sdk-versions"></span>Diferencias relacionadas con las versiones del SDK de AppsFlyer. | Cuenta las conversiones independientemente de la versión del SDK de AppsFlyer. | Para AdsServices, se requiere el SDK V6.1.3+ para atribuir correctamente. |
| <span id="limit-ad-tracking-lat-and-att"></span>Limit ad tracking (LAT) y ATT. | Siempre cuenta la conversión.<br /><br />Si tu campaña está limitada por la edad y el sexo, los usuarios de LAT quedan excluidos.<br /><br />Los usuarios de Apple menores de 18 años son siempre LAT. | Las conversiones de LAT se atribuyen a orgánico.<br /><br />Si AdServices está implementado e iOS 14.3+ está instalado, los usuarios sin consentimiento se atribuyen correctamente. |
| <span id="counting-users"></span>Recuento de usuarios | Cuenta los usuarios en función de las descargas. | Cuenta los usuarios en función de la primera apertura de la aplicación. |
| <span id="reinstall-a-user-after-installing-the-app-deletes-it-clicks-on-a-search-ad-then-installs-the-app-again"></span>Reinstalación: Un usuario después de instalar la aplicación, la elimina, hace clic en un anuncio de Apple Search Ads y vuelve a instalar la aplicación. | Cuenta como conversión (instalación). | <ul><li>With IDFA: AppsFlyer identifica la reinstalación y no la contabiliza a efectos de UA. Consejo: ¡Consejo! Habilita el retargeting y la reinstalación se registrará como una instalación de retargeting (es decir, una reatribución).</li><li>Sin IDFA: AppsFlyer puede confiar en el IDFV para determinar si se trata de una reinstalación o de una nueva instalación:<ol><li>Si una o varias aplicaciones de otro proveedor están instaladas en el dispositivo, AppsFlyer atribuye Apple Ads como una reatribución.</li><li>De lo contrario (si no existe ninguna otra aplicación), AppsFlyer atribuye la instalación a Apple Ads.</li></ol></li></ul> |
| <span id="click-lookback-window"></span>Ventana de lookback de clics | Ventana fija de 30 días | Para las respuestas de AdServices que no tienen tiempo de clic, la ventana de lookback de clics se fija en una ventana de 30 días. |
| <span id="impression-lookback-window"></span>Ventana de lookback de impresiones | Ventana fija de 24 horas | Para las respuestas de AdServices que no tienen un tiempo de impresión, la ventana de lookback de impresiones se fija a una ventana de 24 horas. |
| <span id="preregistration-click-and-impression-lookback-window-discrepancy"></span>Discrepancia entre las ventanas de lookback de clics e impresiones de preinscripción |  | Para las respuestas de AdServices que no tienen hora de clic ni de impresión, la ventana de lookback de clics o impresiones es fija.<ul><li>**Clic**: 90 días</li><li>**Impresión**: 61 días</li></ul> |
| <span id="winning-click"></span>Clic ganador | Siempre se atribuye a sí mismo si el usuario se involucró y descargó la aplicación. | Tiene visibilidad en varias redes y atribuye según la metodología del último clic |
| <span id="install-time"></span>Hora de instalación | Tiempo de descarga de la aplicación | Primera apertura de la aplicación |
| <span id="time-zone"></span>Zona horaria | Zona horaria local de la App Store | Zona horaria UTC o según lo ajustado en la configuración de AppsFlyer |
| <span id="conversion-data"></span>Datos de conversión | Puede tomar más de 5 segundos hasta que se actualiza a AppsFlyer de que Search Ads trajo la instalación. | Se atribuye dentro de los 5 segundos después de que la API de datos de conversión responde. Si no se ha recibido ningún dato, la respuesta es orgánica. |
| <span id="cost-data"></span>Datos de costo | Reporta el costo para todas las palabras clave | No reporta los datos de costos de las palabras clave que contienen letras mayúsculas en el dashboard de cohorte o la API de cohorte. |
| <span id="geo-locations"></span>Geolocalizaciones | Apple Search Ads permite a los anunciantes apuntar a los usuarios según su país y región. Apple Ads admite un número limitado de [**países**](https://searchads.apple.com/storefronts/). | AppsFlyer reconoce la ubicación geográfica exacta del usuario en función de la dirección IP, por lo que reporta sobre geolocalizaciones no disponibles en Apple Search Ads.<br /><br />Consejo: ¡Consejo! Los usuarios que instalan mientras se encuentran en el país de la tienda de aplicaciones tienen los mismos datos de geolocalización en AppsFlyer y Apple Search Ads. |
| <span id="missing-conversion-payload-for-gender-and-age-targeted-users"></span>Falta la carga útil de conversión para usuarios segmentados por sexo o edad (se aplica a partir del 1 de septiembre de 2026) | Apple Ads puede contabilizar estas conversiones en el reporte de Apple Ads, aunque Apple no proporciona una reclamación de atribución para esta cohorte. | Los grupos de anuncios con targeting por edad o sexo devuelven una carga útil de atribución con valor false, por lo que estos usuarios no se atribuyen a Apple Ads en AppsFlyer. Esto puede hacer que Apple Ads reporte más conversiones que AppsFlyer en los grupos de anuncios afectados. |

</Accordion>

<Accordion title="Consejos">

Trabajar con Apple Search Ads te permite recopilar valiosos datos de marketing, que pueden afectar tus esfuerzos de adquisición de usuarios con todas las fuentes de medios para tus aplicaciones iOS.

Consejos para ayudarte a maximizar los beneficios de usar Apple Search Ads:

| Consejo | Detalles |
| --- | --- |
| <span id="get-keyword-data"></span>Obtener datos de palabras clave | Apple Search Ads comparte datos de palabras clave con AppsFlyer. Puedes ver los datos de palabras clave en las herramientas de raw data y de análisis como las de Pivot, Retención y Cohorte.<br /><br />**Nota:**<ul><li>Obtener datos de palabras clave puede retrasarse entre 8 y 12 horas y, en algunos casos, pueden incluir solo el ID de palabra clave sin el término de la palabra clave.</li><li>Para obtener datos de palabras clave, el selector de costo debe estar activado. Los datos de palabras clave se proporcionan como parte de la [integración de costos](/docs/apple-ads-integration-setup#cost-tab), sin la necesidad de una suscripción a ROI360.</li></ul>Si faltan datos de palabras clave en AppsFlyer, esto puede deberse a lo siguiente:<ul><li>**Tipo de paquete:** Apple Ads comparte los datos de palabras clave con los anunciantes que tienen el paquete [avanzado](https://searchads.apple.com/advanced/) de Apple Ads.</li><li>**Tipo de campaña** Puedes configurar diferentes tipos de coincidencia de palabras clave de campaña en Apple Search Ads. Según el tipo de coincidencia, Apple Search Ads comparte las palabras clave de la siguiente manera:<ul><li>**Coincidencia exacta**: Las palabras clave exactas buscadas por el usuario</li><li>**Amplia coincidencia**: Las palabras clave que Apple utilizó para realizar la búsqueda. Estas son similares a los términos de búsqueda reales del usuario.</li><li>**Coincidencia de búsqueda**: Apple **no** comparte estas palabras clave con los anunciantes.</li></ul></li></ul>Usa solo campañas de búsqueda de **coincidencias exactas o amplias** para recibir datos completos de palabras clave. |
| <span id="compare-the-quality-of-users-based-on-keyword-data"></span>Comparar la calidad de los usuarios en función de los datos de palabras clave | No todas las palabras clave son iguales, lo que significa que, aunque diferentes palabras clave puedan costar lo mismo, la calidad de los usuarios atraídos podría ser distinta. Utiliza los reportes de retención o <Anchor target="_blank" href="/marketers/es/docs/pivot-table-user-metrics">pivot</Anchor> para identificar las palabras clave que maximizan tu ROI. |
| <span id="analyze-keyword-cost"></span>Analizar el costo de las palabra clave | La plataforma contiene datos agregados de costos de palabras clave cuando las campañas de palabras clave de Apple Ads se configuran como una [coincidencia exacta o una coincidencia amplia](/docs/apple-ads-integration-setup#get-keyword-data). Los datos de costos de palabras clave tienen las siguientes características:<ul><li>Los datos históricos están disponibles desde el 13 de octubre de 2019.</li><li>Dimensiones:<ul><li>Fecha</li><li>Campaña</li><li>Conjunto de anuncios</li></ul></li><li>Herramientas de análisis:<ul><li><Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">Cohorte</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/pivot-table-user-metrics">Pivot</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api">API maestra</Anchor></li></ul></li></ul>**Limitaciones**<ul><li>Usa solo las dimensiones indicadas para filtrar y agrupar consultas de datos de costos. Por ejemplo, no filtres ni agrupes usando la geolocalización.</li></ul>**<span id="h_01M0YZYCC5S0E3HA296KAA0SDZ"></span>Ejemplos**<br /><br />**<span id="cohort-example"></span>Ejemplo de cohorte**<br /><br />El siguiente ejemplo muestra cómo configurar la Cohorte para ver los costos y la información de ROI.<br /><br />**Configuración de cohorte**<br /><br /><Image alt="CohortRequest.png" src="https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png" width="327px" /><br /><br />**Tabla de resultados de cohorte**<br /><br />En la tabla a seguir, se muestra el costo total y el ROI de la cohorte:<br /><br /><Image alt="CohortTable.png" src="https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png" width="429px" /><br /><br />**<span id="pivot-example"></span>Ejemplo de pivot**<br /><br />**Configuración de pivot**<br /><br /><Image alt="Pivot_define.png" src="https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png" width="413px" /><br /><br />**Tabla de resultados de pivote**<br /><br /><Image alt="Pivot.png" src="https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png" width="439px" /> |
| <span id="find-the-best-performing-creative-set"></span>Encontrar el conjunto creativo de mejor rendimiento | ![creative_sets.png](https://files.readme.io/ef8e38d67121283742dcbd1faef11d94a8ea1c612dc258611e72cbf826d7ef8f-31197524112785.png)<br /><br />Es una buena práctica probar cómo responden los usuarios potenciales a los diferentes conjuntos creativos que usas. Los conjuntos creativos de mejor rendimiento tienen las tasas de conversión más altas. Además, los mejores conjuntos creativos convierten a los usuarios con un mayor nivel de engagement.<br /><br />Esto afecta a todos tus usuarios potenciales de iOS, no solo a los de Apple Ads, ya que todos llegan a la página de tu aplicación en la tienda de aplicaciones. Sin embargo, con las instalaciones de Apple Ads, AppsFlyer indica el ID del conjunto creativo en el <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">raw data</Anchor> parámetro **Ad ID**, lo que te permite comparar el rendimiento de diferentes conjuntos creativos. |
| <span id="target-redownloaders"></span>Apunta a los que han vuelto a descargar la app | Tus usuarios anteriores son posiblemente la mejor audiencia a la que puedes dirigirte con Apple Ads.<br /><br />Un usuario que desinstaló tu aplicación y, como resultado de tu campaña de retargeting de Apple Ads, la instala de nuevo, se denomina «re-downloader» en Apple Ads. Si la reinstalación se realiza durante la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor>, AppsFlyer lo denomina una reatribución. En todos los demás casos, se trata como una instalación nueva.<br /><br />![ASACGroupID.png](https://files.readme.io/ebdc380f2abc3e9a3b134cd258d90ae32f75b3ee4d9eadde39adbc728daae523-31197514645265.png) |

</Accordion>

<Accordion title="Registro de cambios de Apple Ads">

| Fecha de vigencia | Actualización/modificación |
| --- | --- |
| <span id="20260901"></span>2026-09-01 | A partir del 1 de septiembre de 2026:<ul><li>La API AdServices de Apple añade una marca de tiempo de engagement a todas las atribuciones de iOS, independientemente del estado de ATT. AppsFlyer usa esta marca de tiempo para aplicar la ventana de lookback configurada por el anunciante y las reglas de atribución de último toque a estas atribuciones.</li><li>En los grupos de anuncios con targeting por edad o sexo, Apple devolverá una carga útil de atribución con valor false, lo que significa que no se puede aplicar ninguna medición de SRN a esa cohorte segmentada.</li></ul>Consulta la documentación para desarrolladores de AdServices de Apple para conocer más detalles. |
| <span id="20230207"></span>07-02-2023 | Los parámetros de atribución enriquecidos `Nombre de la campaña`, `Nombre del conjunto de anuncios` y `Palabras clave` están disponibles solo cuando la pestaña de Costo está habilitada, independientemente de tu plan de suscripción.  <br />**Esto significa que para que tus dashboards y reportes de raw data muestren nombres de campañas, nombres de conjuntos de anuncios o palabras clave, debes tener habilitada la pestaña de Costo.** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla. |
| <span id="20220216"></span>16-02-2022 | Las palabras clave están disponibles a través de la API de costos. Debes habilitar la API de costos en la página de integración de Apple Search Ads. ¡Atención! ¡Nota! La API está disponible para todos los anunciantes independientemente de tu plan de suscripción. |
| <span id="20210407"></span>07-04-2021 | Integración de Apple Ads: Apple Ads funciona independientemente de SKAdNetwork y atribuye a los usuarios de forma determinista. Esto significa que, para los usuarios atribuidos a Apple Ads, tienes la gama completa de funciones y mediciones que proporciona nuestro <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">modelo de atribución de LTV.</Anchor> |
| <span id="20210307"></span>07-03-2021 | Apple Search Ads está implementando la API V4.0 de gestión de campañas. La API se relaciona con el costo y otros datos relacionados con las campañas. No tiene impacto en la atribución. Estamos en el proceso de adoptar la API actualizada. No se requiere ninguna acción de tu parte. |
| <span id="20210215"></span>15-02-2021 | A partir de esta fecha, los campos de nombre de campaña y nombre de conjunto de anuncios se pueden completar si habilitas la API de [Costo](/docs/apple-ads-integration-setup#cost-tab) de Apple Ads. La API está disponible para todos los anunciantes independientemente del plan de suscripción. |

Actualizaciones y cambios de Apple Ads

</Accordion>

<Accordion title="Disponibilidad de los parámetros de las campañas de Apple Search Ads">

La siguiente tabla muestra la disponibilidad de los parámetros de atribución en los reportes de raw data o en el dashboard.

| Parámetro del reporte de raw data | Disponibilidad |
| --- | --- |
| Nombre de la campaña | Para que este parámetro esté disponible, debes habilitar la API de [Costo](/docs/apple-ads-integration-setup#cost-tab) en la página de integración de Apple Ads. La API está disponible para todos los anunciantes, independientemente de su plan de suscripción. |
| ID de campaña | Siempre disponible |
| Nombre del conjunto de anuncios | Para que este parámetro esté disponible, debes habilitar la API de [Costo](/docs/apple-ads-integration-setup#cost-tab) en la página de integración de Apple Ads. La API está disponible para todos los anunciantes, independientemente de su plan de suscripción. |
| ID del conjunto de anuncios | Siempre disponible |
| Anuncio | Actualmente no disponible |
| ID del anuncio | Este parámetro solo está disponible cuando se cumplen las dos condiciones a seguir:<ul><li>Los usuarios tienen iOS 15.2 o versiones posteriores</li><li>El anuncio usa</li></ul><Anchor target="_blank" href="https://developer.apple.com/app-store/product-page/">Páginas de productos personalizadas</Anchor> para campañas asociadas con cualquiera de las siguientes ubicaciones de anuncios:<ul><li>`Pestaña Hoy`</li><li>`Resultados de búsqueda`</li></ul> |
| Palabras clave | Para que este parámetro esté disponible, debes habilitar la API de [Costo](/docs/apple-ads-integration-setup#cost-tab) en la página de integración de Apple Ads. La API está disponible para todos los anunciantes, independientemente de su plan de suscripción. |
| ID de palabra clave | Este parámetro está disponible a través de los reportes de raw data. Sin embargo, debe seleccionarse explícitamente en Data Locker, Push API y Datos exportados. En el caso de la Pull API, agrega `keyword_id` al parámetro `&additional_fields` <Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data#additional-fields">en la llamada de la Pull API</Anchor>. |
| Tipo de coincidencia de palabras clave | Actualmente no disponible |

</Accordion>

<Accordion title="Impacto de la privacidad avanzada agregada">

A partir de iOS 14, [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) (ATT) regula la disponibilidad del IDFA, y Apple Ads controla los datos de atribución a nivel de usuario de las instalaciones generadas por Apple Ads. Por tanto, la disponibilidad de datos a nivel de usuario de las instalaciones generadas por Apple Ads no se ve afectada por <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad Avanzada Agregada</Anchor>.

#### Después del 1 de septiembre de 2026

| **Consentimiento de la ATT** | **Tiempo de clic/impresión disponible** | **Ventana de lookback de clics/impresiones** | **Observaciones** | **Disponibilidad de datos** | **IDFA disponible** |
| --- | --- | --- | --- | --- | --- |
| Con consentimiento y sin consentimiento | Sí | Establecido por el anunciante | Reglas de atribución de último toque de AppsFlyer utilizadas | Datos de atribución a nivel usuario | Sí para quienes dan su consentimiento, no para quienes no lo dan |

#### Antes del 1 de septiembre de 2026

La disponibilidad del momento del clic/impresión, la ventana de lookback y la disponibilidad de datos variaban según el consentimiento de ATT:

| **Consentimiento de la ATT** | **Tiempo de clic/impresión disponible** | **Ventana de lookback de clics/impresiones** | **Comentarios** | **Disponibilidad de datos** | **IDFA disponible** |
| --- | --- | --- | --- | --- | --- |
| Anunciante | Sí | Establecido por el anunciante | Reglas de atribución de último toque de AppsFlyer utilizadas | Datos de atribución a nivel usuario | Sí |
| Sin consentimiento | No | Clics: 30 días (establecido por Apple Ads), impresiones: 24 horas | Se da prioridad a los candidatos deterministas. | Datos de atribución a nivel de usuario sin el tiempo de clic/impresión. | No |

</Accordion>

#### Consulta también

* <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Framework de Privacidad Avanzada Agregada</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">Ventanas de lookback explicadas</Anchor>

<div data-zendesk-anchors="set-up-asa-integration=configurar-la-integraci%C3%B3n-de-apple-ads h_01HDPCGMP2CY4B37VM3AT2P114=configurar-la-integraci%C3%B3n-de-apple-ads set-up-agencies-and-asa-marketing-partners=configurar-agencias-y-partners-de-marketing-de-apple-ads h_01HDPCGMP3D96BG496G7H97YWP=configurar-agencias-y-partners-de-marketing-de-apple-ads agency-vs-marketing-partner=agencia-vs-partner-de-marketing h_01HDPCGMP3YGJEA942DF2YC9P1=agencia-vs-partner-de-marketing configuring-agencies-and-marketing-partners=configuraci%C3%B3n-de-agencias-y-partners-de-marketing h_01HDPCGMP3NQQ76SC32SEC8TS4=configuraci%C3%B3n-de-agencias-y-partners-de-marketing configuration-steps-checklist=lista-de-verificaci%C3%B3n-de-pasos-de-configuraci%C3%B3n h_01HDPCGMP39HE117X4MP25M77W=lista-de-verificaci%C3%B3n-de-pasos-de-configuraci%C3%B3n advertiser-actions=acciones-del-anunciante h_01HDPCGMP3S3PHHH3F6KZE3SEV=acciones-del-anunciante agency-actions=acciones-de-la-agencia h_01HDPCGMP3MK61YRMCQA2KA5X2=acciones-de-la-agencia cost-clicks-and-impressions-data=datos-de-impresiones-clics-y-costos h_01HDPCGMP3AVYYK2X03RF057FN=datos-de-impresiones-clics-y-costos additional-information=informaci%C3%B3n-adicional h_01HDPCGMP3BXVASH2YJ9G8AS2C=informaci%C3%B3n-adicional h_01M0YZYCC477D5MMBC6D5BD3MG=despu%C3%A9s-del-1-de-septiembre-de-2026 h_01M0YZYCC4RRSRWBDAKN6ECV7N=antes-del-1-de-septiembre-de-2026 retargeting-related-discrepancies=discrepancias-relacionadas-con-el-retargeting h_01HDPCGMP4Z9M3QR6QGRR7A8BM=discrepancias-relacionadas-con-el-retargeting additional-reasons-for-discrepancies=razones-adicionales-para-discrepancias h_01HDPCGMP4QJ3HYEP7EAYMHRQQ=razones-adicionales-para-discrepancias h_01HDPCGMP4MF9FBP4WDRHVZ4BR=cohort-example h_01HDPCGMP4EFMZ4FHZ8WBWW9R2=pivot-example h_01M0YZYCC5H6FBKYNEHZA91BSZ=despu%C3%A9s-del-1-de-septiembre-de-2026-1 h_01M0YZYCC5QK9A6T9KV2XDSK8P=antes-del-1-de-septiembre-de-2026-1 h_01M0YZYCC5V5N4Z3M3327W2XFT=consulta-tambi%C3%A9n" />

---
title: Configuración de integración de Meta Ads
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Facebook
    - App Install
    - View-Through
    - integrated partner
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2013-01-24T20:13:58Z'
  edited_at: '2026-09-11T00:28:44Z'
  id: 207033826
  locale: es
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/es/articles/207033826
---
> **Resumen:** Descubre cómo integrar los Meta Ads con AppsFlyer.

## Guía para configurar Meta Ads

¿Cuánto se tarda en comenzar a atribuir los anuncios de tu aplicación móvil de Meta con AppsFlyer?

Si ya tienes el <Anchor target="_blank" href="/marketers/es/docs/integrate-the-appsflyer-sdk">SDK de AppsFlyer integrado en tu aplicación</Anchor>, y ya has definido tu aplicación en Meta Ads, la respuesta es: ¡menos de un minuto!

No necesitas implementar el inicio de sesión de Facebook ni integrar tu app con el SDK de Facebook para la atribución móvil. Simplemente sigue las [instrucciones básicas de configuración paso a paso](#configuración-básica-de-atribución-de-meta-ads) a continuación. Después, echa un vistazo a las [opciones de configuración avanzada](#configuración-de-atribución-avanzada-para-meta-ads) para Meta Ads.

## Configuración básica de atribución de Meta Ads

<div id="create-and-retreive-facebook-app-id" />

<Accordion title="Crea y recupera un ID de aplicación de Facebook">

Para integrar los anuncios de Meta con AppsFlyer, primero crea un <Anchor target="_blank" href="https://developers.facebook.com/docs/apps/register">ID de aplicación de Facebook</Anchor> y luego recupéralo.

**Cómo crear un ID de aplicación de Facebook**:

1. En **Meta Ads**, ve al <Anchor target="_blank" href="https://developers.facebook.com/apps">Dashboard de la aplicación</Anchor>.
2. En **Aplicaciones**, haz clic en **Crear nueva aplicación.**
3. Completa el nombre de tu aplicación e introduce un espacio de nombres único. Asegúrate de añadir la plataforma correcta para tu aplicación; de lo contrario, es posible que las instalaciones no sean atribuidas correctamente.

**Para recuperar el ID de la aplicación de Facebook**:

1. En **Meta Ads**, ve al <Anchor target="_blank" href="https://developers.facebook.com/apps">Dashboard de tu aplicación.</Anchor>
2. Haz clic en la aplicación requerida.
3. Haz clic en el ID de la aplicación, ubicado en la parte superior izquierda de la pantalla, para copiarlo.

   [![](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)

AppsFlyer atribuye los datos por ID de aplicación. El mismo ID de aplicación de Facebook se puede usar para [tus aplicaciones de Android e iOS](https://developers.facebook.com/docs/app-ads/app-setup/). Ten en cuenta que para iOS 14+, Meta Ads limita las cuentas de anuncios a nueve cuentas por aplicación.

</Accordion>

<div id="enable-meta-ads-device-level-data" />

<Accordion title="Habilita los datos a nivel de dispositivo de Meta Ads">

A partir del 17 de junio de 2025, Meta ha reactivado el reporte de **Medición Móvil Avanzada (AMM)**. Una vez que aceptes, recibirás:

* Análisis móvil a nivel de dispositivo
* Métricas de atribución a nivel de evento para campañas de Meta
* Integración completa con tus dashboards y exportaciones de AppsFlyer existentes

**Para habilitar AMM, sigue estos pasos:**

1. Visita <Anchor target="_blank" href="https://business.facebook.com/business/loginpage/?next=https%3A%2F%2Fdevelopers.facebook.com%2Fadvanced_mobile_measurement%2Fterms">Meta Ads</Anchor>.
2. Selecciona la aplicación correspondiente.
3. Acepta los términos de Medición Móvil Avanzada de Meta.

> 🚧 **¡Importante!**
>
> * Se requiere que un administrador de tu aplicación de desarrollador de Meta acepte los términos de AMM de Meta.
> * Los datos a nivel de dispositivo con visibilidad completa de atribución solo están disponibles para nuevos dispositivos atribuidos después de que se hayan aceptado los términos de AMM.
> * Los eventos in-app heredan el estado de restricción de sus conversiones atribuidas. Esto significa:
>   * Si el evento in-app está atribuido a una conversión que ocurrió antes de firmar el acuerdo de Medición Móvil Avanzada (AMM), el evento permanece restringido.
>   * Si el evento in-app está atribuido a una conversión que ocurrió después de firmar el acuerdo de AMM, el evento está disponible en reportes de raw data.

</Accordion>

<div id="set-the-meta-ads-active-integration" />

<Accordion title="Configura la integración activa de Meta Ads">

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.
2. Busca Meta Ads y luego selecciónalo.
3. Haz clic en **Integrate**. Serás enviado a la página de configuración de integración.
4. En la pestaña **Integración**, haz clic en **Activar partner**.  
   **Nota: <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">El conmutador debe permanecer encendido (</Anchor><Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor>) mientras trabajes con el partner.**
5. En **Configuración general**:

   [![](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)

   * Pega tu [ID de aplicación de Facebook](#create-and-retreive-facebook-app-id) en el campo **ID de aplicación de Facebook**.
   * Pega la clave de descifrado del referente de instalación de [Meta Ads](/docs/meta-ads-integration-setup#datos-cifrados-de-la-api-de-referencia-de-google-play-o-el-referente-de-instalación-de-meta).
6. Activa o desactiva la **Compartición avanzada de datos**; consulta [Compartición avanzada de datos](#advanced_data_sharing) a continuación. (Disponible progresivamente para todas las cuentas hasta el 14 de octubre de 2024.)
7. Activa o desactiva el **uso compartido de datos de Advanced Matching**; consulta [Uso compartido de datos de Advanced Matching](#advanced_matching_data_sharing) a continuación.
8. Haz clic en **Guardar integración**.

</Accordion>

<div id="optional--configure-recommended-settings" />

<Accordion title="[Opcional] Configura los ajustes recomendados:">

[![](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)

* Para que coincida con la ventana de lookback por click-through de Meta Ads, configúrala en 7 días.  
  (Ten en cuenta que [hay algunos casos específicos en los que el valor predeterminado es diferente](https://www.facebook.com/business/help/395050428485124?id=428636648170202)).
* Para que coincida con la ventana de lookback por view-through de Meta Ads, configúrala en un día.
* Para habilitar la atribución de reinstalación, activa el interruptor de **Atribución de reinstalación**. La atribución de reinstalaciones te permite medir a los usuarios que reinstalan tu app durante su ventana de reatribución. No es necesario activar la atribución por impresiones o configurar ventanas de lookback para la atribución de reinstalaciones, ya que toma la configuración de la atribución de instalaciones. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls">Medir reinstalaciones</Anchor>.

</Accordion>

## Configuración de atribución avanzada para Meta Ads

Con la atribución básica ya configurada para los Meta Ads, es momento de una rápida configuración avanzada de atribución.

<div id="getting-userlevel-data-for-android-installs" />

<Accordion title="Obteniendo datos a nivel de dispositivo para instalaciones de Android">

#### Google Play Install Referrer API

Los Meta Ads comparten metadatos de campaña con anunciantes para anuncios de aplicaciones de Android que dirigen a los usuarios a Google Play Store. En este caso, los campos de atribución están disponibles para los anunciantes en la Google Play Install Referrer API, que debe <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">integrarse en tu aplicación.</Anchor> Los campos proporcionados a través de la Google Play install referrer API rellenan los reportes de raw data de AppsFlyer con el tipo de coincidencia `gp_referrer`. Esto solo está disponible una vez que se envía la clave de descifrado y se atribuye una instalación a los Meta Ads. Esto permite a AppsFlyer atribuir a los usuarios que no tienen un ID de publicidad (habilitado para LAT).

#### **Meta install referrer**

> 📘 **Nota:**
>
> El Meta install referrer permite a AppsFlyer recibir metadatos de campañas publicitarias del almacenamiento local de un dispositivo. Consulta el [Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer) para aprender cómo habilitar el SDK para acceder al Meta install referrer.

Además de la API de referente de instalación de Google Play, el referente de instalación de Meta permite a AppsFlyer recibir metadatos de campañas publicitarias del almacenamiento local de un dispositivo. Estos datos se utilizan para medir la atribución. Las principales diferencias entre la Google Play Install Referrer API y el Meta install referrer son:

* El Meta install referrer puede incluir datos de impresiones y clics, mientras que la Google Play Install Referrer API se limita a los datos de clics.
* Meta install referrer puede incluir datos de varias sesiones, mientras que la Google Play Install Referrer API se limita a los datos de la última sesión (el dispositivo debe instalar la aplicación en la misma sesión en la que se hizo clic).

Como resultado, es posible que veas un aumento de las instalaciones atribuidas a Meta en los reportes de raw data. Cuando una instalación se atribuye a través de la Google Play Install Referrer API o Meta install referrer, los datos están disponibles en los reportes de raw data. Los campos que pueden estar disponibles para la atribución a través del Meta install referrer rellenan los reportes de raw data de AppsFlyer con el tipo de coincidencia `fb_referrer` para la atribución desde la aplicación de Facebook y `ig_referrer` para la atribución desde la aplicación de Instagram. Esto solo está disponible en una vez que se envía la clave de descifrado y se atribuye una instalación a Meta Ads. La clave de descifrado del Meta install referrer es la misma clave `fb_referrer`utilizada para Google Play Install Referrerfb\_referrer y no es necesario proporcionarla a AppsFlyer una segunda vez.

#### **Campos de atribución de campaña disponibles a través del referente:**

* ID del anuncio
* Nombre del anuncio
* ID del conjunto de anuncios
* Nombre del conjunto de anuncios
* ID de campaña
* Nombre de la campaña
* ID de cuenta
* Canal

> 📘 **Nota:**
>
> * **Para Google Play Install Referrer API:**
>   * El SDK de AppsFlyer debe ser **V5.4.0+** para que los datos del referente se transmitan correctamente. Los datos del referente tienen prioridad sobre los datos proporcionados por la API y no están restringidos. Esta solución se aplica a la atribución por clics y no a la atribución por impresiones.
>   * El campo Canal está determinado por el valor del canal recibido de la API de referente de Google Play (enviado a Google Play por Meta). Si se recibe una cadena vacía, el campo Canal mostrará "None".
>
> * **Para el referente de instalación de Meta:** Consulta los <Anchor target="_blank" href="/marketers/es/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">requisitos previos y las acciones requeridas</Anchor> descritas en el boletín.

#### Meta install referrer — Preguntas frecuentes

**¿En qué casos se aplica Meta install referrer para la atribución?**

* Para atribución de instalaciones:
  * Atribución por clics para todas las campañas
  * La atribución por impresiones es compatible con todas las campañas de aplicaciones Advantage+ y las campañas manuales de promoción de aplicaciones con targeting amplio (por ejemplo, cuando la edad y el sexo se establecen en Predeterminado).

* Compatibilidad: Google Play Store y tiendas de aplicaciones Android ajenas a Google Play
* Exclusiones: Esto no incluye las campañas que redireccionan a landing pages

**¿Para qué sirve el "targeting amplio" en Meta Ads?**

Para recibir los datos de instalaciones por impresiones se requiere un targeting amplio. La configuración de campaña admitida incluye:

* Edad: Se aplica la configuración predeterminada (18-65+)
* Género: Se aplica la configuración predeterminada (todos los géneros)
* Ubicación: Se admiten grupos de países y países. **Nota:** Para ubicaciones más específicas (como ciudades o códigos postales), las campañas que utilicen el targeting por inclusión deben configurarse como relajadas.
* Targeting detallado: Los segmentos de interés, los comportamientos y los datos demográficos avanzados se establecen de forma relajada.
* Audiencias personalizadas: Configurar como relajado.
* Para la opción "relajada", debe seleccionarse la casilla "Targeting detallado Advantage" para las campañas publicitarias: [![](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)

#### Datos cifrados de la API de referencia de Google Play o el referente de instalación de Meta

Tanto la API de referencia de Google Play como el referente de instalación de Meta cifran los datos. Estos datos se pueden descifrar usando una clave disponible en tu cuenta de desarrollador de Meta. Debes proporcionarnos la clave de descifrado indicada en la fila de acciones requeridas. La clave de descifrado debe enviarse solo una vez por aplicación.

Ten en cuenta que si la clave no se proporciona o se eliminó, hay algunos casos en los que aún se atribuye a Meta Ads la instalación en función del referente, incluso sin los campos de atribución de la campaña (mencionados en la lista anterior). Esto sucede cuando:

* Los anuncios de Meta no reclamaron la instalación
* Los datos recibidos de la API de referencia de instalación de Google Play se recibieron pero no se decodificaron
* Y fue el último clic

**Para obtener tu clave de descifrado de Meta:**

1. Inicia sesión en tu portal de desarrollador de Meta.
2. Dirígete a **Mis Aplicaciones** en la esquina superior derecha.
3. Selecciona la aplicación para la que deseas acceder a tu clave de descifrado.
4. Ve a **Configuración** > **Básico** en el lado izquierdo de la página. [![](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
5. Desplázate hacia abajo hasta la sección Android y verás tu clave de descifrado con la etiqueta clave de descifrado de referente de instalación debajo del campo “Nombres de paquete”. Nota: Esta es la misma sección en la que configuraste el nombre de tu paquete y Google Play Store.

**Para configurar la clave de descifrado en AppsFlyer:**

1. [Obligatorio] Verifica que AppsFlyer SDK V5.4+ esté adoptado en tu aplicación. No confíes en versiones anteriores.
2. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
3. Selecciona **Meta Ads**. [![](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)
4. En la pestaña **Integración**, pega la clave en **Install Referrer Decryption Key**. Esto debe hacerse solo una vez por aplicación.
5. Haz clic en **Guardar integración**.

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Costos, clics e impresiones">

[![meta_cost_tab.png](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)

Esta integración proporciona datos agregados sobre costos, clics e impresiones de tus campañas, anuncios y geolocalizaciones/países. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad networks</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas.

**Nota:** Los datos sobre clics e impresiones se incluyen en la integración. Sin embargo, los datos de costos requieren **requieren una** suscripción **a** <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview?query=xpend">**ROI360**</Anchor> .

**Para habilitar la API de costos**:

1. Asegúrate de haber iniciado sesión en la cuenta de usuario de Meta Ads habilitada para administrar las campañas de la cuenta de Meta Ads. El usuario que se haya registrado debe tener permiso para ejecutar todas las campañas en Meta Business Manager.
2. Ve a la pestaña **Costo**.
3. Activa **Obtener datos de costo, clics e impresiones**.
4. Haz clic en el botón **f de inicio de sesión**. Puedes iniciar sesión con una cuenta de negocio o administrador de Meta ads.
5. Cuando se te indique, habilita el acceso a los datos de tu campaña de Meta Ads para AppsFlyer.  
   **Nota**: En la primera sincronización de datos después de la integración, así como en las sincronizaciones posteriores, AppsFlyer recibe los datos de costos de Meta Ads hasta los últimos 7 días de manera retroactiva.

**Para eliminar una cuenta de Meta Ads conectada:** En la columna acciones, desplaza el cursor sobre una cuenta y haz clic en **Eliminar conexión.**

> 📘 **Notas**
>
> * Si ya iniciaste sesión en Meta Ads, al hacer clic en el botón **f de inicio de sesión de Facebook**, la ventana se abrirá y se cerrará inmediatamente. Este es el comportamiento normal.
> * Si tienes varios usuarios con permisos para Meta Ads, lo mejor es iniciar sesión con todos ellos, para <Anchor target="_blank" href="/marketers/es/docs/meta-ads-faq#why-doesnt-cost-data-include-data-from-all-campaigns">evitar obtener datos parciales</Anchor>.

#### Estado de sincronismo de datos de costos

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer datos de costos coincidentes, ya sea en el Dashboard de estado de la integración de costos (e ingresos por anuncios) o en el Dashboard de la ad network individual. 

Puedes sincronizar varias cuentas para extraer datos de costos. Para cada cuenta sincronizada, AppsFlyer muestra el estado de integración de costos y la última vez que AppsFlyer pudo extraer datos de costos coincidentes.

Aprende más sobre cómo enriquecer tus datos con datos de <Anchor target="_blank" href="/marketers/es/docs/meta-ads-faq#preguntas-frecuentes-sobre-el-costo-de-meta-ads">costos, clics e impresiones</Anchor>.

</Accordion>

<div id="inapp-event-mapping" />

<Accordion title="Mapeo de eventos in-app">

[![meta_iae_postbacks.png](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)

**Para mapear eventos in-app:**

1. Activa **Postbacks de eventos in-app.**  
   Al habilitar la asignación de eventos in-app de Meta Ads para una aplicación **por primera vez**, **af\_app\_open** se asigna automáticamente a **fb\_mobile\_activate\_app**.
2. Completa los siguientes parámetros:

| Nombre del parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos servidor a servidor.<br />**Consejo**: ¿No encuentras el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor>.</li></ul> |
| **Asignado al evento de partner** | El ID o nombre único de cada evento, tal y como se defina en Meta Ads. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** Obtén el ID de evento correspondiente de Meta Ads</li><li>**Cuadro desplegable:** Selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Tal como está**: Envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuya a Meta Ads.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envían postbacks de eventos atribuidos a cualquier partner y eventos orgánicos.</li></ul> |
| **incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin el valor del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

3. Para agregar un evento de SDK o de servidor a servidor a la lista, haz clic en **Agregar evento**.

**Limitaciones con respecto a los nombres de eventos:**

* Restricción de longitud para los nombres de eventos: 2-40 caracteres
* Los caracteres siguientes no están permitidos:
  * Dos puntos (:)
  * Punto (.)
  * Juegos de caracteres no latinos (inglés): A partir del 12 de enero de 2020, Meta Ads rechaza los caracteres chinos. AppsFlyer no ha probado otros conjuntos de caracteres y debes usarlos solo después de verificar con Meta Ads si estos son compatibles en los postbacks.
* Los nombres de eventos distinguen entre mayúsculas y minúsculas. Para evitar discrepancias, asegúrate de usar las mayúsculas y minúsculas correctas en los nombres de eventos para todas las fuentes de medios y versiones de la aplicación.

> 📘 **Nota:**
>
> Los Meta Ads pueden optimizar tus campañas en función de los datos de ingresos de tus anuncios al mapear el evento af\_ad\_revenue al evento adecuado de Meta Ads.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Atribución de retargeting">

La atribución de retargeting de AppsFlyer para Meta Ads permite a los anunciantes atribuir un engagement de un usuario existente con un anuncio de Meta, y medir la calidad del usuario con posterioridad al engagement, usando los reportes de AppsFlyer. Debe usarse solo si estás ejecutando activamente campañas dirigidas a tus propios usuarios en Facebook.

1. <Anchor target="_blank" href="/marketers/es/docs/app-settings#reengagement-attribution">Activa el retargeting en la página Configuración de la aplicación</Anchor>.
2. En la página de partner de Meta Ads, activa la **Atribución de re-engagement**.
3. Configura la **ventana de lookback de re-engagement por click-through**.  
   La ventana de lookback de re-engagement es el período de tiempo, a partir del clic en el anuncio, durante el cual debe iniciarse la aplicación para que el clic se registre como un re-engagement.  
   Selecciona una ventana de lookback (en horas o días) y configura el control deslizante en el valor deseado.  
   [![](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)
4. Habilita **la atribución de re-engagement view-through**.
5. Establece el **control deslizante de la ventana de lookback de re-engagement por view-through** al valor deseado (hasta 24 horas). Este es el período de tiempo a partir de una impresión de un anuncio, durante el cual se debe iniciar la aplicación para que la impresión se registre como un re-engagement.[![](https://files.readme.io/82028408b7475e6ad5bcd35f2d597b7f5344b9eca432157559265cf73bdb952c-30354145625873.png)](https://files.readme.io/82028408b7475e6ad5bcd35f2d597b7f5344b9eca432157559265cf73bdb952c-30354145625873.png)
6. Configura la **Ventana de re-engagement**.  
   Ese es el período en el que los eventos in-app del usuario se atribuyen a la fuente de medios de retargeting como fuente principal.  
   Puedes configurar el valor en días (1-90), horas (hasta 23) o incluso de por vida. El valor predeterminado es de 30 días.  
   [![](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)

Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">atribución de retargeting de AppsFlyer</Anchor>.

Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#deep-linking-con-srns">los usuarios de deep linking a partir de SRNs como Meta Ads</Anchor>.

#### Atribución de campañas de retargeting de WhatsApp

AppsFlyer admite la medición de campañas de mensajes de WhatsApp Marketing que se usan para re-engagement mediante atribución por deep link tanto en iOS como en Android.

Cuando el conmutador de **re-engagement** está activado tanto en el **nivel de integración** como en el **nivel de la aplicación**, estas campañas se miden automáticamente, sin necesidad de configuración adicional.

Selecciona el tipo de datos agregados de ingresos por publicidad que deseas recibir. **Ingresos atribuidos** y/o **ingresos de monetización agregados**:

</Accordion>

<div id="advanced_data_sharing" />

<Accordion title="Intercambio avanzado de datos">

Cuando se activa el intercambio avanzado de datos, Meta recibe postbacks y eventos con identificadores a nivel de dispositivo para todos los dispositivos, incluidos los dispositivos que no han disponibilizado su ID de publicidad (IDFA).

Además, cuando se activa el **intercambio avanzado de datos**, AppsFlyer atribuye estos eventos. Cuando está apagado, solo se envían y atribuyen los postbacks y eventos de dispositivos con un IDFA.

Este método atribuye instalaciones de click-through y view-through de iOS, así como re-engagement de deep link de iOS, para dispositivos de exclusión simple y dual. La atribución se basa en la atribución de último toque con una ventana de atribución máxima de 24 horas.

> 📘 **Nota:**
>
> Si la opción de **Intercambio avanzado de datos** está activada y no recibes atribución con Meta, verifica si los eventos compartidos cumplen con los criterios de elegibilidad de Meta. Consulta la <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">documentación de Meta</Anchor>.

</Accordion>

<div id="advanced_matching_data_sharing" />

<Accordion title="Uso compartido de datos de Advanced Matching">

Cuando el **uso compartido de datos de Advanced Matching** está activado, los campos de Advanced Matching, como el correo electrónico con hash, el número de teléfono con hash, el nombre con hash, el apellido con hash y el ID de login de Facebook, se comparten con Meta si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.

</Accordion>

<div id="use-deep-links-in-meta-ads-campaigns" />

<Accordion title="Usa deep links en campañas de Meta Ads">

Cuando ejecutas campañas de Meta Ads, puedes usar deep links para enviar a los usuarios directamente a una página o experiencia específica dentro de la aplicación. En las secciones siguientes se describe cómo configurar el Deep Linking de AppsFlyer en Meta Ads

Antes de seleccionar un objetivo de campaña, asegúrate de que tu aplicación use uno de los siguientes formatos de deep link (DL) compatibles:

* OneLink de AppsFlyer, si la aplicación tiene integración de Universal Links o Android App Links
* Apple Universal Links
* Enlaces de aplicaciones de Android
* Esquemas URI personalizados
* Facebook App Links

La tabla siguiente describe qué objetivos de campaña de Meta Ads admiten deep links directos y deep links diferidos (DDL), junto con las instrucciones de configuración y las limitaciones de cada uno.

| Propiedades de la campaña | Direct deep link | Deep link diferido (DDL) | instalación | Limitaciones y requisitos previos |
| --- | --- | --- | --- | --- |
| Promoción de app / Instalación | Compatible | Compatible | Introduce la URL de DDL en el campo **Deferred Deep Link** en el nivel del anuncio, en la sección **Destination**. | <ul><li>En iOS, DDL solo es compatible en <Anchor target="_blank" href="/marketers/es/docs/meta-ads-aggregate-event-measurement-aem-for-ios">aplicaciones con AEM habilitado</Anchor> o aplicaciones con consentimiento doble (Meta + App)</li><li>DDL requiere el SDK de Facebook para iOS y Android.</li></ul> |
| Ventas | Compatible | No compatible | Configúralo en el nivel del conjunto de anuncios, en **Conversion**, o usa la configuración del catálogo. Si es necesario, puedes sustituir los deep links del catálogo por una URL de sitio web. | <ul><li>Requiere que **Enable Install Tracking** esté activo.</li><li>El destino debe ser una aplicación móvil.</li></ul> |
| Tráfico | Compatible | No compatible | Configúralo en el nivel del conjunto de anuncios, en **Conversion**. Admite alternativas de respaldo a la App Store o a un sitio web. | <ul><li>Requiere que **Habilitar el tracking de instalaciones** esté activo.</li></ul> |
| Awareness | Compatible | No compatible | Configúralo en el nivel de anuncio, en la sección **Destino**. | <ul><li>Requiere que **Habilitar el tracking de instalaciones** esté activo.</li></ul> |
| Leads | Compatible | No compatible | Configúralo en el nivel de conjunto de anuncios, en **Conversión**. | <ul><li>Requiere que **Habilitar el tracking de instalaciones** esté activo.</li></ul> |

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">Guía de OneLink</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Crea un enlace de OneLink para tus campañas</Anchor>

</Accordion>

<div id="comply-with-california-consumer-privacy-act-ccpa" />

<Accordion title="Cumplimiento de la Ley de Privacidad del Consumidor de California (CCPA)">

Cumplir con las regulaciones de privacidad de la CCPA limita los datos provenientes de los usuarios de Meta Ads que residen en California, EE.UU.

**Para permitir el cumplimiento de la CCPA:** Activa la opción **Limitar el uso de la información personal de los usuarios por parte de Meta Ads (CCPA)** en la pestaña **Integración**.

Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">leyes de protección de datos</Anchor>.

</Accordion>

<div id="ad-revenue-recording" />

<Accordion title="Registro de ingresos por publicidad">

[![](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)

Si tu aplicación utiliza la función de Ingresos por publicidad de Meta Audience Network para la monetización de anuncios, puedes registrar tus ingresos derivados de Meta Ads en AppsFlyer. Esto, con o sin datos de ingresos por compras in-app, te proporciona un **panorama general de los ingresos por usuario**.

#### Registrar los ingresos por publicidad de Meta Audience Network

1. En la pestaña **Ingresos por publicidad**, activa **Obtener datos de ingresos por publicidad**.
2. <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el dashboard de estado de la integración de costos (e ingresos por publicidad) o en el dashboard de la ad network individual.
   * **Ingresos atribuidos**: ingresos basados en la fuente de adquisición de usuarios.  
     Configura la **fuente del evento**, que es el evento que representa tu modelo de ingresos por publicidad de la mejor manera posible. Por ejemplo, si tus ingresos se basan en impresiones, se recomienda enviar a AppsFlyer un evento ad\_viewed. Se puede configurar por separado el mejor evento para cada plataforma de monetización. Sin embargo, también es posible utilizar el evento `af_app_opened`. En este caso, los ingresos por anuncios son atribuidos para cada apertura de aplicación realizada por el usuario.
   * **Ingresos de monetización agregados**: Ingresos basados en la fuente de la publicidad.
3. Se muestra el **evento de ingresos publicitarios**. Se trata de un campo de solo lectura que presenta el evento de ingresos por publicidad nuevo, llamado [source event]\_monetized (por ejemplo, Ad\_Watched\_Monetized, como se muestra anteriormente). El evento de ingresos por anuncios se presenta en el dashboard como evento adicional.
4. Haz clic en **Conectar a Meta Ads** para habilitar la recaudación de ingresos publicitarios de Meta Audience Network en Meta Ads. Inicia sesión con tus credenciales de Meta Ads para autorizar los Ingresos por Publicidad de Meta Audience Network.
5. Introduce el **ID de aplicación de ad network (**[**ID de aplicación Facebook**](/docs/meta-ads-integration-setup#facebook-app-id)). Obtén esto de Meta Audience Network.
   * Obtén el [ID de aplicación de Facebook](/docs/meta-ads-integration-setup#facebook-app-id).
   * Copia el ID en el campo **Audience Network APP ID** en AppsFlyer.
6. Haz clic en **Guardar ingresos publicitarios**.

</Accordion>

<div id="permissions" />

<Accordion title="Permisos">

Permite que Meta Ads realice varias acciones y acceda a tus datos de acuerdo con los permisos disponibles.

Obtén más información sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">cómo conceder permisos a partners integrados</Anchor>.

</Accordion>

## Medición de eventos agregados (AEM) para iOS

AppsFlyer admite la <Anchor target="_blank" href="/marketers/es/docs/meta-ads-aggregate-event-measurement-aem-for-ios">Medición de eventos agregados de Meta Ads (AEM)</Anchor>. Esta solución optimiza las conversiones en iOS y eventos in-app, atribuyendo también los re-engagements de iOS en Meta Ads.

## Solución de problemas de integración de Meta Ads

Si ya has completado la integración básica y aún no ves resultados de los Meta Ads en el dashboard de AppsFlyer, primero verifica que haya nuevas instalaciones desde los anuncios de Meta tras la integración.

Si es así, revisa las principales causas a continuación para resolver este problema:

<div id="no-idfa-collection" />

<Accordion title="Sin recopilación del IDFA">

Como se especifica en la Guía de Integración del SDK - iOS, debes agregar el AdSupport.framework a tu proyecto para permitir la recopilación del IDFA. Consulta el reporte de raw data de instalación para verificar si la columna de IDFA está realmente vacía o no. Se recomienda que tu aplicación esté habilitada para recopilar el IDFA en apps iOS y GAID en apps Android.  
A partir de iOS 14.5, tendrás que mostrar el mensaje de la ATT de Apple y obtener el consentimiento del usuario antes de poder recopilar IDFA.

**Nota:** La atribución de SKAdNetwork no se ve afectada por la disponibilidad del IDFA. Sin embargo, asegúrate de habilitar la opción de Campaña iOS 14 en Meta Ads al configurar campañas de iOS 14.

</Accordion>

<div id="wrong-facebook-app-id" />

<Accordion title="ID de aplicación de Facebook incorrecto">

El ID de la aplicación de Facebook se configuró incorrectamente en AppsFlyer.  
Verifica que el ID de la aplicación sea correcto y coincida con el valor en el dashboard de Meta Ads.  

Nota: también puedes usar la <Anchor target="_blank" href="https://developers.facebook.com/tools/explorer/?method=GET&path=&version=v6.0">API Graph de Facebook</Anchor> para validar tu ID de aplicación de Facebook.

</Accordion>

<div id="app-status-on-meta-ads" />

<Accordion title="Estado de la aplicación en Meta Ads">

La aplicación debe definirse en Meta Ads como **Live** en lugar de **In development** para que la atribución funcione.

[![](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)

</Accordion>

<div id="wrong-type-of-meta-ads-campaign" />

<Accordion title="Tipo de campaña equivocado en Meta Ads">

Asegúrate de que la campaña de Meta Ads sea **Anuncios de instalación de aplicaciones móviles** o **Interacción con aplicaciones móviles**. Para otros objetivos de campaña, para medir las instalaciones móviles, el anunciante debe <Anchor target="_blank" href="/marketers/es/docs/attributing-app-installs-to-non-mobile-ads-from-meta-ads">verificar la **grabación de eventos in-app** opción</Anchor> al definir la campaña de Meta Ads.

<div id="aem-attribution-is-not-working" />

<Accordion title="La atribución de AEM no funciona">

Si la opción de **Intercambio avanzado de datos** está activada y no recibes atribución con Meta, verifica si los eventos compartidos cumplen con los criterios de elegibilidad de Meta. Consulta la [documentación de Meta](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

</Accordion>

</Accordion>

<div id="meta-ads-app-install" />

<Accordion title="Instalación de la aplicación mediante Meta Ads">

Al configurar la campaña de instalación de aplicaciones en Meta Ads, puedes seleccionar la aplicación de un menú desplegable o pegar la URL completa de la tienda. Aunque ambos métodos funcionan con Meta Ads, el segundo método no permite la atribución en AppsFlyer.

Configuración correcta: la atribución se realiza correctamente.

[![](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)

Configuración incorrecta: no se logra la atribución.

[![](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)

</Accordion>

### Actualizaciones de iOS 14 relacionadas con Meta Ads

AppsFlyer confirma que nuestra integración MMP con Meta Ads siempre implementa la bandera *Seguimiento de Anunciantes Activado*. Esto significa que no necesita realizar ninguna acción en AppsFlyer. Esta información se proporciona siguiendo la lista de verificación de la guía de Meta Ads para iOS 14, de febrero de 2021.

> 📄 **Consulta también**
>
> * Para consideraciones relacionadas con iOS 14, <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-interoperation-with-meta-ads">Interoperabilidad de Meta Ads SKAN</Anchor>.
> * <Anchor target="_blank" href="/marketers/es/docs/configuring-meta-campaign-management-partners">Configuración de partners de gestión de campañas de Meta</Anchor> (<Anchor target="_blank" href="/marketers/es/docs/bidalgo-meta-campaign-management-partner-configuration">Bidalgo</Anchor> / <Anchor target="_blank" href="/marketers/es/docs/kenshoo-meta-campaign-management-partner-configuration">Kenshoo</Anchor> / <Anchor target="_blank" href="/marketers/es/docs/adquant-meta-campaign-management-partner-configuration">Adquant</Anchor> / <Anchor target="_blank" href="/marketers/es/docs/webpals-mobile-meta-campaign-management-partner-configuration">Webpals</Anchor>)

<div data-zendesk-anchors="facebook-ads-setup-guide=gu%C3%ADa-para-configurar-meta-ads 01H7YJVNMSZ4WG4HWBZF648HZN=gu%C3%ADa-para-configurar-meta-ads basic-facebook-attribution-setup=configuraci%C3%B3n-b%C3%A1sica-de-atribuci%C3%B3n-de-meta-ads 01H7YJVNMTFW076FAJZGJWT4R9=configuraci%C3%B3n-b%C3%A1sica-de-atribuci%C3%B3n-de-meta-ads h_01JXYJW7AFB53PY7WHGM05HDMH=create-and-retreive-facebook-app-id h_01JKX03GC8ZSMGCSX84381QW0A=enable-meta-ads-device-level-data h_01JYPKG2RH3R08604V7B3NC5WQ=importante h_01JXYHEFW19DJXXXRNN186E07B=set-the-meta-ads-active-integration %5Boptional%5D-configure-recommended-settings=optional--configure-recommended-settings h_01JXYHEFW15E6K39JY2VBCN79E=optional--configure-recommended-settings advanced-facebook-attribution-setup=configuraci%C3%B3n-de-atribuci%C3%B3n-avanzada-para-meta-ads 01H7YJVNMTHF800PD5CEWPFS49=configuraci%C3%B3n-de-atribuci%C3%B3n-avanzada-para-meta-ads h_01JKX03GC8B4VKC6KJT4CZ9VT8=getting-userlevel-data-for-android-installs h_01JKX2BE00WYHMJ3RX1FK8DQV5=google-play-install-referrer-api h_01JKX2BNRDHHNJCN257H3QBZ65=meta-install-referrer h_01JKX03GC8JRZSD13TVDDM1MWE=nota campaign-attribution-fields-available-via-the-referrer=campos-de-atribuci%C3%B3n-de-campa%C3%B1a-disponibles-a-trav%C3%A9s-del-referente h_01JKX2CF8RE4T5R3V83FS1PBQR=campos-de-atribuci%C3%B3n-de-campa%C3%B1a-disponibles-a-trav%C3%A9s-del-referente h_01JKX03GC9BG4GFDKR7JHG31BQ=nota-1 meta-install-referrer%E2%80%94faq=meta-install-referrer--preguntas-frecuentes h_01JKX2DSY85X6570AHYKHM34KS=meta-install-referrer--preguntas-frecuentes encrypted-data-from-google-play-referrer-api-or-meta-install-referrer=datos-cifrados-de-la-api-de-referencia-de-google-play-o-el-referente-de-instalaci%C3%B3n-de-meta h_01JKX2E4A44QHKADG4S8ZM9KC5=datos-cifrados-de-la-api-de-referencia-de-google-play-o-el-referente-de-instalaci%C3%B3n-de-meta 01H7YJVNMTBN9RJ6Q7TJ1AJ0XX=cost-clicks-and-impressions 01H7YJVNMTGRBQG54DVMJDHDKS=notas cost-data-sync-status=estado-de-sincronismo-de-datos-de-costos 01H7YJVNMTRQAYG7TY29AX4MZS=estado-de-sincronismo-de-datos-de-costos 01H7YJVNMTNRREKWY96CK9JJKV=inapp-event-mapping 01H7YJVNMT2DRVR26F8CDDTWHP=nota-2 01H7YJVNMV5AZ9G2KCKEFF1CSV=retargeting-attribution whatsapp-retargeting-campaign-attribution=atribuci%C3%B3n-de-campa%C3%B1as-de-retargeting-de-whatsapp h_01KBZ2CAGX18ZZPXQGMPTEPSCP=atribuci%C3%B3n-de-campa%C3%B1as-de-retargeting-de-whatsapp 01H7YJVNMVSA4Y33MW6Q8Y777Y=advanced_data_sharing 01JDH9Y65409Y5E162NWJA25E3=nota-3 h_01KPK96J1G0BY3PPEBN9RB005V=use-deep-links-in-meta-ads-campaigns h_01KPK96J1GZE9ZHQB5NHFCVAG6=v%C3%A9ase-tambi%C3%A9n h_01JKTYRMD70ZGN31FSQ7BXF1HB=comply-with-california-consumer-privacy-act-ccpa 01H7YJVNMVWRG10SZY1B33H5EA=ad-revenue-recording record-meta-audience-network-ad-revenue=registrar-los-ingresos-por-publicidad-de-meta-audience-network 01H7YJVNMV1TTHKMMX4TFB2BF3=registrar-los-ingresos-por-publicidad-de-meta-audience-network 01H7YJVNMVMW5BXWEP8BPX4D7E=permissions aggregate-event-measurement-aem-for-ios=medici%C3%B3n-de-eventos-agregados-aem-para-ios 01H7YJVNMVGFYMHE5FACTD9NS0=medici%C3%B3n-de-eventos-agregados-aem-para-ios meta-ads-integration-troubleshooting=soluci%C3%B3n-de-problemas-de-integraci%C3%B3n-de-meta-ads 01H7YJVNMVCAQ6ETKBGCAM31B9=soluci%C3%B3n-de-problemas-de-integraci%C3%B3n-de-meta-ads 01H7YJVNMV3YRF59RX87TJCT8D=no-idfa-collection 01H7YJVNMVHCYVWKDW5WWPX1A5=wrong-facebook-app-id 01H7YJVNMVE9QJAXQBD4P14C88=app-status-on-meta-ads 01H7YJVNMVBRVTT9HH7KM8P33B=wrong-type-of-meta-ads-campaign h_01JKTYRMD7YPGJRZXR4Y66BAHG=aem-attribution-is-not-working 01H7YJVNMV4G3VP40E6VFD7SJD=meta-ads-app-install ios-14-updates-relating-to-facebook=actualizaciones-de-ios-14-relacionadas-con-meta-ads 01H7YJVNMVQP5PR6XDHTCPXVDC=actualizaciones-de-ios-14-relacionadas-con-meta-ads h_01HDP0Y4CZBZEK5VZ6FG3T31JB=consulta-tambi%C3%A9n" />

---
title: Guía de atribución de ingresos por publicidad
metadata:
  keywords:
    - ad revenue
    - ad monetization
    - monetization
    - Advertisers
    - adrevenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2016-12-12T10:53:27Z'
  edited_at: '2026-10-27T03:34:38Z'
  id: 217490046
  locale: es
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/es/articles/217490046
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Atribuye los ingresos por publicidad para completar la vista de rendimiento del LTV (Lifetime value).

<Image align="center" alt="Attributes_ad_revenue.png" src="https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png" />

<div id="ad-revenue-attribution" />

## Atribución de ingresos por publicidad

* Los anuncios se muestran en la aplicación en banners, muros de ofertas, intersticiales, etc., y generan ingresos por publicidad.
* Los ingresos por publicidad, combinados con las compras in-app y los ingresos por suscripción, te proporcionan la imagen completa del LTV del usuario. Al vincular el LTV del usuario con la campaña de gasto en medios, puedes determinar el ROI y analizarlo en la plataforma.

**Datos de ingresos por publicidad atribuidos**:

* Se adquiere de las plataformas de mediación o de las redes de monetización de anuncios a través de las API del servidor o mediante el SDK de reportes integrado en la aplicación (incluido iOS 14).
* Se atribuye a la fuente de medios que originalmente trajo al usuario, por ejemplo:
  * El usuario ve un anuncio de la red A y descarga tu aplicación.
  * El anuncio se muestra dentro de la aplicación.
  * Los ingresos por publicidad se atribuyen a la Red A (responsable de la adquisición de usuarios), independientemente de quién haya publicado el anuncio.
* La granularidad de los reportes depende de la integración de la red de monetización y del tipo de atribución de los ingresos por publicidad.

<Accordion title="Tipos de integración para la atribución de ingresos por publicidad">

La precisión y la actualización de los datos dependen del tipo de integración de atribución de ingresos por publicidad, como se muestra en la siguiente tabla.

**Nota**: los tipos de integración del SDK requieren la ayuda de desarrolladores para implementarse. Los tipos de integración S2S requieren que tengas las credenciales de red adecuadas.

| Tipo de integración para la atribución de ingresos por publicidad | Descripción |
| --- | --- |
| [Nivel agregado](#h_01JYRKB8Q3D3W0FM75VH78XQTS) a través de la API S2S | <ul><li>AppsFlyer recibe los ingresos diarios desglosados por geolocalización.</li><li>Los ingresos efectivos por acción (eRPA) se obtienen dividiendo los ingresos por la cantidad de instancias de un evento desencadenante.</li><li>Los eventos de activación son eventos in-app abiertos o específicos configurados en la aplicación.</li><li>Si estás utilizando una plataforma de mediación, asegúrate de desactivar las integraciones de ingresos por publicidad para los partners de monetización mediados a través de la plataforma antes de habilitar la integración de ingresos por publicidad con la plataforma. Si no lo haces, se duplicarán los datos.</li><li>Los datos no están disponibles en los reportes de raw data y no se pueden compartir con ad network mediante postbacks ni señales de UA.</li></ul> |
| [Nivel de dispositivo](#01ECF1PZ36R9W7A0X4WBR95JDS) por API S2S | <ul><li>La red de mediación o monetización reporta los ingresos por usuario a nivel de dispositivo. No todas las redes admiten granularidad a nivel de dispositivo.</li><li>Estos ingresos se atribuyen a la fuente de medios que trajo al usuario. Es decir, la atribución de ingresos por publicidad de AppsFlyer se adhiere a las reglas de atribución que se encuentran en la plataforma, incluidas las reglas de atribución por retargeting.</li><li>Si estás utilizando una plataforma de mediación, asegúrate de desactivar las integraciones de ingresos por publicidad para los partners de monetización mediados a través de la plataforma antes de habilitar la integración de ingresos por publicidad con la plataforma. Si no lo haces, se duplicarán los datos.</li><li>El nivel de dispositivo por API S2S incluye el 100% de los ingresos por publicidad y ofrece la mayor precisión de datos entre los tipos de integración de ingresos por publicidad.</li><li>Los datos están disponibles en los reportes de raw data y solo se pueden compartir con ad network mediante <Anchor target="_blank" href="/marketers/es/docs/share-ad-revenue-data-with-partners">señales de UA.</Anchor></li><li>Para Android: asegúrate de que los desarrolladores hayan habilitado la recopilación de AppSet\_id, ya que algunas mediaciones pueden proporcionar solo este identificador. Consulta las instrucciones para desarrolladores sobre [la recopilación del ID de AppSet](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |
| Nivel de impresión (por SDK) | <ul><li>El nivel de impresión se refiere a cómo AppsFlyer recibe los datos. Los datos pueden acabar reportándose con otros niveles de granularidad (como el nivel de dispositivo).</li><li>La red de mediación o monetización reporta los ingresos por usuario a nivel de impresión. No todas las redes admiten la granularidad a nivel de impresión.</li><li>Estos ingresos se atribuyen a la fuente de medios que trajo al usuario. Es decir, la atribución de ingresos por publicidad de AppsFlyer se adhiere a las reglas de atribución que se encuentran en la plataforma, incluidas las reglas de atribución por retargeting.</li><li>Si estás utilizando una plataforma de mediación, asegúrate de desactivar las integraciones de ingresos por publicidad para los partners de monetización mediados a través de la plataforma antes de habilitar la integración de ingresos por publicidad con la plataforma. Si no lo haces, se duplicarán los datos.</li><li>El nivel de impresión por SDK tiene la mejor actualización de datos de todos los tipos de integración de ingresos por publicidad.</li><li>Admite SKAN (SKAdNetwork).</li><li>El nivel de impresión mediante SDK es el tipo de integración que debes usar cuando utilizas una plataforma de mediación que no está incluida en la lista de Partners integrados de AppsFlyer. En el SDK de ingresos por anuncios, para mediation\_network, el desarrollador debe elegir customMediation.</li><li>Los datos solo se pueden compartir con ad network mediante <Anchor target="_blank" href="/marketers/es/docs/share-ad-revenue-data-with-partners">postbacks</Anchor>.</li></ul> |
| Nivel de impresión (por SDK) con nivel de dispositivo (por API S2S) | <ul><li>Permite atribuir y reportar los datos a nivel de impresión que llegan a través del SDK el día X, y sustituirlos por datos a nivel de dispositivo que llegan por API a partir del día 1 y en adelante. **Nota**: Para Android, los datos reportados a través del SDK desde dispositivos desconocidos (sin ID de dispositivo disponibles) no se reemplazan por datos que llegan a través de API.</li><li>Permite la actualización de los datos para la precisión. Lo que significa que puedes disfrutar de una actualización de los datos del Día X con la precisión de los datos de los Días X+1 y siguientes.</li><li>Admite SKAN.</li><li>Lista de partners de mediación que pueden enviar señales de UA a las redes de publicidad de UA:</li><li>Para Android: asegúrate de que los desarrolladores hayan habilitado la recopilación de AppSet\_id, ya que algunas mediaciones pueden proporcionar solo este identificador. Consulta las instrucciones para desarrolladores sobre [la recopilación del ID de AppSet](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |

</Accordion>

<div id="implementation" />

## Implementación

Las siguientes secciones describen los tipos de atribución de ingresos por publicidad disponibles, así como los flujos de trabajo y los pasos necesarios para la implementación y el mantenimiento.

<Accordion title="Si bien puedes enviar postbacks de ingresos por publicidad a partners específicos, debes asegurarte de validar cómo los partners utilizan los datos antes de comenzar la integración.">

**Antes de comenzar**:

* Solicita que el partner integrado de ingresos por publicidad te proporcione las credenciales de la API.

**Para habilitar la integración de los ingresos por publicidad con la red de ingresos por publicidad**:

1. En AppsFlyer, ve a **ROI360** > **Configuración de ingresos** > **Ingresos por publicidad**.
2. En Integración de ingresos por publicidad, haz clic en **Nueva integración de ingresos por publicidad**.
3. Selecciona un partner de ingresos por publicidad y haz clic en **Siguiente**.

   <Image align="center" alt="ingresos por anuncios 3.6(2).png" src="https://files.readme.io/8ccba7d0909c15e92507bc55c7bf2bf003e1a9431fb6bd1d32a0f41959f7a904-47792643579153.png" />

   <div id="note" />

   > 📘 **Advertencia**
   >
   > Si tu solución de mediación no aparece en la lista de partners compatibles, selecciona **Mediación personalizada** e intégrala mediante la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/gs-ad-revenue">API del SDK de ingresos por anuncios de AppsFlyer</Anchor>.

4. Selecciona el tipo de datos de ingresos por publicidad que deseas recibir. **Nota**: No todas las redes de publicidad proporcionan todas las opciones que se enumeran a continuación.
   * Ingresos atribuidos. Significa ingresos basados en la fuente de adquisición de usuarios. Los reportes de ingresos atribuidos pueden ser:
     * [Nivel agregado](#h_01JYRKB8Q3D3W0FM75VH78XQTS) por API S2S.
       * Selecciona el evento en el que basar los ingresos por publicidad. Por ejemplo, si eliges el evento af\_app\_opened, los ingresos por publicidad totales se dividen entre todos los eventos de apertura de la app, lo que te da los ingresos por publicidad por cada apertura de la app.
     * Nivel de dispositivo por API S2S.
       * **Para Android:** Asegúrate de que los desarrolladores habiliten la recopilación de`app_set_id`, ya que algunas mediaciones pueden proporcionar solo este identificador. Consulta las instrucciones para desarrolladores sobre [la recopilación del ID de AppSet](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).
       * **Nota**: Si habilitas la API de ingresos por publicidad a nivel de dispositivo para una plataforma de mediación, debes desactivar las integraciones de ingresos por publicidad de las redes de monetización que media. Si no lo haces, se duplicarán los datos.
     * Nivel de impresión por SDK.
       * Dile a tus desarrolladores de aplicaciones que integren el conector del SDK de ingresos por publicidad de AppsFlyer. Hay opciones disponibles para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-2">iOS</Anchor> y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad_revenue_unity_connector">Unity</Anchor>.
     * Nivel de impresión (por SDK) con nivel de dispositivo (por API S2S).
       * Dile a tus desarrolladores de aplicaciones que integren el conector del SDK de ingresos por publicidad de AppsFlyer.
     * **Para Android:** Asegúrate de que los desarrolladores habiliten la recopilación de`app_set_id`, ya que algunas mediaciones pueden proporcionar solo este identificador. Consulta las instrucciones para desarrolladores sobre [la recopilación del ID de AppSet](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).
     * **Nota**: Si estás utilizando una plataforma de mediación, asegúrate de desactivar las integraciones de ingresos por publicidad para los partners de monetización mediados a través de la plataforma antes de habilitar la integración de ingresos por publicidad con la plataforma. Si no lo haces, se duplicarán los datos.
5. Completa las credenciales de la API o inicia sesión, según lo requiera el partner integrado. Esto no es relevante para las integraciones de SDK.
6. Haz clic en **Guardar**.
7. Haz clic en **Guardar configuración.**
   * Si se muestra un mensaje de éxito, has completado el procedimiento.
   * Si aparece cualquier otro mensaje, consulta la tabla [Estado y pruebas de la integración de ingresos por publicidad](#01ECF1PZ32Z4C20NADJ2SF3EPC) y sigue la acción correctiva recomendada; después, repite el procedimiento.
8. AppsFlyer recopila datos del partner varias veces al día. Para más información, consulta [Actualización de datos](#01H8V10BKK6N5XJ6GHKC201E3Y).
9. [Opcional] Haz el QA y compara los datos de ingresos por publicidad que ves en AppsFlyer con los datos de ingresos por publicidad que ves en tus paneles de control de partners de mediación y partners de UA. <Anchor target="_blank" href="/marketers/es/docs/compare-roi360-ad-revenue-data-with-partner-data">Aprender más</Anchor>
10. [Opcional] Comparte los datos de ingresos por publicidad con tus partners a través de <Anchor target="_blank" href="/marketers/es/docs/compare-roi360-ad-revenue-data-with-partner-data">señales de UA</Anchor> y [postbacks de eventos de ingresos por publicidad](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks).

**Nota**: Si cambias de un tipo de integración a otro, el cambio entra en vigor a las 12 am UTC del día siguiente.

</Accordion>

<Accordion title="Ver, editar y eliminar partners integrados de ingresos por publicidad">

<Image align="center" alt="delete_edit_adi.png" src="https://files.readme.io/2d2153ec3248061dab4072e1d981e237f553e32824a68e392ae239778b307610-47792653636113.png" />

**Para ver, editar o eliminar integraciones de redes de ingresos por publicidad**:

1. En AppsFlyer, ve a **ROI360** > **Configuración de ingresos** > **Ingresos por publicidad** y selecciona tu aplicación.  
   Se muestra una lista de todas las integraciones de tus partners, junto con información sobre el producto y el tipo de integración, el estado de la integración y los nombres de los eventos de ingresos por publicidad.
2. Pasa el cursor sobre la integración y haz clic en **Editar** o **Eliminar** según sea necesario.

</Accordion>

<Accordion title="Desduplicar los ingresos por publicidad con referencias cruzadas.">

Cuando una aplicación utiliza dos <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#plataforma-de-mediación">plataformas de mediación</Anchor> con tipos de integración por API (nivel agregado o nivel de dispositivo), ambas asociadas a la misma <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#attributed_touch-_time">red de monetización</Anchor>, puede producirse una duplicación parcial de los datos de ingresos por publicidad. En tales casos, cada plataforma de mediación reporta todos los ingresos por anuncios generados por su red de monetización asociada, independientemente de si esos ingresos se generaron mientras solo una de las plataformas los mediaba.

**Para evitar la duplicación parcial de los datos de ingresos cuando hay referencias cruzadas entre dos plataformas de mediación**:

* Nivel de impresión (por SDK) Los datos reportados a nivel de impresión de esta manera no se deduplican. El SDK reporta cada impresión una sola vez, por lo que no hay solapamiento que eliminar.
* Para las integraciones **mediante API**, deduplica los ingresos por anuncios:
  1. En AppsFlyer, ve a **ROI360** > **Configuración de ingresos** > **Ingresos por publicidad**.
  2. En **Configuración general**, haz clic en **Desduplicar los ingresos por publicidad cuando hay referencias cruzadas entre dos partners de mediación**. **Nota**: No marques la casilla si las 2 plataformas de mediación median formatos de anuncios diferentes. Por ejemplo, cuando la plataforma 1 muestra Banner e Interstitial, y la plataforma 2 muestra anuncios de AppOpen y Native.

     <div id="note-1" />

     > 📘 **Nota:**
     >
     > Este ajuste siempre se ignora para:
     >
     > * **Integraciones a nivel de impresión (SDK)** — todos los partners.
     > * **Integraciones a nivel de dispositivo (API)** - para AppLovin MAX o ironSource (Unity LevelPlay)
     >
     > Estas no contienen datos duplicados en primer lugar, así que no hay nada que deduplicar.


<Image align="center" alt="dedup.png" src="https://files.readme.io/a739bc7e3557913bf6a67afa74a71dd72673d5b4e4d6bbe1d3ef872e46609422-47792653637265.png" />

</Accordion>

<Accordion title="Selecciona el evento AppsFlyer af_ad_revenue.">

La granularidad agregada para los ingresos por publicidad funciona de la siguiente manera:

* La red integrada reporta los ingresos diarios totales, desglosados por geolocalización.
* AppsFlyer deriva los ingresos efectivos por acción (eRPA) dividiendo los ingresos por la cantidad de instancias de un evento desencadenante.
* AppsFlyer crea un evento \_monetized que incluye el eRPA total para cada dispositivo atribuido. Por ejemplo, ad\_matched\_monetized.
* El uso de los ingresos de eRPA se atribuye a las fuentes de medios.
* Puedes usar uno de los siguientes tipos de eventos:
  * El **evento in-app de monetización única** requiere modificaciones en la aplicación.
  * Evento **af\_app\_opened** , que está disponible de forma predeterminada.
* No reportes los montos de ingresos por publicidad en eventos in-app en paralelo a una integración de ingresos por publicidad. Si lo haces, los ingresos por publicidad se duplicarán en el dashboard porque AppsFlyer obtiene los datos de ingresos de la red de monetización mediante la integración.

<div id="aggregate-ad-revenue-using-events" />

#### Ingresos por publicidad agregados mediante eventos

| Método de evento | ¿Cómo se implementa? | consideraciones |
| --- | --- | --- |
| Evento in-app único de monetización | <ul><li>Un evento in-app se establece en el momento de la visualización del anuncio.</li><li>Esto proporciona un recuento distinto de las acciones de los usuarios, lo que permite cálculos de eRPA superiores</li><li>Esto se puede perfeccionar aún más si se usa un evento in-app distinto para cada red de monetización. Esto te permite desglosar los ingresos por red de monetización<br />Consulta la tabla siguiente para ver un análisis completo.</li></ul> | <ul><li>Requiere que el desarrollador modifique la aplicación.</li><li>Los ingresos se pueden desglosar por red de monetización en el panel de control.</li></ul> |
| evento af\_app\_opened | <ul><li>El SDK de Appsflyer envía el evento af\_app\_opened de forma predeterminada</li><li>Se activa por cada sesión de usuario</li></ul> | <ul><li>No se requiere modificación de la aplicación.</li><li>Rápido de implementar.</li><li>eRPA values are significantly distorted unless you show only one ad per session</li><li>Sin desglose de los ingresos por red de monetización.</li><li>El evento corresponde a todos los usuarios que abren la aplicación, y no tienes ninguna indicación de la disposición del usuario a ver anuncios</li></ul> |

<div id="comparison-of-in-app-event-methods" />

#### Comparación de métodos de eventos in-app

| Método | Ventajas | Desventajas | Consideraciones |
| --- | --- | --- | --- |
| Utiliza el mismo evento para todas las redes. Por ejemplo, ad\_watched. Esto genera automáticamente el evento ad\_watched\_monetized que contiene los detalles de monetización. | Más simple de implementar. | Sin información de calidad, como el número de clics y los ingresos por publicidad por red. | <ul><li>Es la mejor opción si el objetivo principal es encontrar fuentes/campañas que atraigan a usuarios con mayor tendencia a hacer clic en los anuncios.</li><li>No es adecuado para comparar el rendimiento de las redes de monetización.</li></ul> |
| **(Mejores prácticas)** A cada red se le asigna un evento único para ver anuncios. Ejemplo: ad\_watch\_admob,<br /><br /> ad\_watch\_vungle. | Visibilidad completa y capacidad para comparar las redes de monetización en el panel de control, además del raw data. | Los ingresos por publicidad no se acumulan en un solo evento. El número de eventos es equivalente al número de redes. | Permite comparar redes monetizadas en el panel de control. Los ingresos por publicidad se separan por red mediante un evento in-app por red. |

</Accordion>

<Accordion title="Estado y pruebas de la integración de ingresos por publicidad">

El estado operativo de la integración de ingresos por publicidad está disponible de la siguiente manera:

* <Anchor target="_blank" href="/marketers/es/docs/dashboard-cost-and-ad-revenue-status">Dashboard del estado de integración de costes e ingresos por publicidad</Anchor>: lista centralizada de partners para los que está habilitada la integración de ingresos por publicidad en una o varias aplicaciones de tu cuenta.
* **Botón Probar conexión:** Está disponible al añadir o editar una integración de ingresos por publicidad. Úsalo para comprobar si la integración está operativa.

Para verificar que la integración esté operativa:

1. Haz clic en **Probar conexión**.
2. Se muestra un mensaje de éxito: **Clave de API verificada** (para integraciones basadas en API) o **La autenticación se realizó correctamente** (para integraciones basadas en SDK). Si aparece cualquier otro mensaje, sigue la guía de acciones correctivas en la tabla siguiente.

| Estado | Significado | Observaciones/acción requerida |
| --- | --- | --- |
| Clave verificada de la API | La conexión está activa y puede extraer datos. AppsFlyer recopila datos varias veces al día. Para más información, consulta [Data Freshness](#01H8V10BKK6N5XJ6GHKC201E3Y). | None |
| La autenticación se realizó correctamente | Se recibieron del SDK eventos válidos de ingresos por anuncios. | None |
| Credenciales no válidas | Una o varias de las credenciales proporcionadas son incorrectas. | Obtén las credenciales correctas de los partners de ingresos por publicidad |
| Faltan detalles de configuración | Uno o más de los campos de credenciales están incompletos | Recupera las credenciales en el panel de control del partner de ingresos por publicidad o comunícate con el partner y solicita las credenciales. |
| No se encontraron eventos | No se han recibido recientemente del SDK eventos válidos de ingresos por anuncios. | Confirma que la integración del SDK está completa y que se están enviando eventos de prueba. Puedes verificar la entrega de eventos en tiempo real usando el <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers#view-live-events">visor de eventos en vivo</Anchor>. |

<div id="note-2" />

> 📘 **Advertencia**
>
> En las integraciones de SDK, también puedes verificar que los eventos de ingresos por anuncios se registran en tiempo real con el <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers#view-live-events">visor de eventos en vivo</Anchor>. Ten en cuenta que solo muestra eventos enviados desde dispositivos de prueba registrados.

</Accordion>

<div id="ad-revenue-data" />

## Datos de ingresos por publicidad

Los datos de ingresos por publicidad están disponibles a través de los paneles de control de AppsFlyer y los reportes de raw data.

<Accordion title="Datos agregados de ingresos por publicidad">

Los ingresos por publicidad muestran la calidad de los usuarios de diferentes fuentes a lo largo del tiempo. A medida que los usuarios siguen abriendo la aplicación e interactuando con anuncios, su LTV aumenta.

**Nota**: Puede haber discrepancias entre los datos de ingresos por anuncios en distintos dashboards y reportes.

La atribución de ingresos por publicidad está disponible de la siguiente manera:

* Basada en LTV:
  * Paneles de control: general, eventos
  * Reportes de LTV
  * Panel de control y reportes de cohorte
  * API maestra
* Basada en actividades:
  * Panel de control: Actividad
  * Raw data de ingresos por publicidad

<div id="overview-dashboard---aggregated-performance-report" />

#### **Panel de información general - Reporte de estadísticas agregadas de rendimiento**

<Image align="center" alt="" src="https://files.readme.io/f3ea2c79ed42c59d26f6f82d7f68e20b319a005e6a3131239b99f13db59b3cff-47792643589393.png" />

En el panel de control de información general:

* Los valores, incluidos los ingresos, son LTV. Consulta <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Valor de vida útil (LTV) vs. actividad</Anchor>.
* La columna **Ingresos** incluye todos los ingresos, incluidos los ingresos por publicidad y las compras in-app.
* Profundiza en la jerarquía publicitaria (fuente de medios, campaña, conjunto de anuncios, geolocalización) para ver los eventos **monetizados** en el reporte.

**Dashboard de eventos**

<Image align="center" alt="" src="https://files.readme.io/c7c8fddb68f705a7be694afdde6faf387cf34b79abfbc68c39e53823549a385d-47792643591057.png" />

En el panel de control de actividad:

* Los valores, incluidos los ingresos, se basan en la fecha de actividad. Consulta <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Valor de vida útil (LTV) vs. actividad</Anchor>.
* El 0**Promedio de acciones por usuario** indica la tendencia de los usuarios a interactuar con los anuncios presentados en la aplicación.

<div id="examples" />

#### Ejemplos

Tres usuarios instalan una aplicación el 31 de diciembre de 2017. Se atribuyen de la siguiente manera:

* Usuario A:
* Usuario B:
* Usuario C: orgánico

La aplicación está integrada con cinco plataformas de monetización diferentes. Cada plataforma utiliza un evento in-app único utilizando el SDK de AppsFlyer de la siguiente manera:

* Red de audiencia de Meta: fb\_ad\_view
* Chartboost: chartboost\_ad\_view
* Admob: admob\_ad\_view
* Applovin: applovin\_ad\_view
* IronSource: is\_ad\_view

Después de la instalación, durante un período de cuatro días, se muestran anuncios a los usuarios de la siguiente manera:

| Usuario | Red de publicidad de UA | fb\_  <br />ad\_view | chartboost\_  <br />ad\_view | admob\_  <br />ad\_view | applovin\_  <br />ad\_view | is\_ad\_view | Total |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | Red A<br /><br />2017-12-31 | 2018-01-01<br /><br />$1 | 2018-01-02<br /><br />$1 | 2018-01-03<br /><br />$1 | 2018-01-04<br /><br />$1 |  | $4 |
| B | Red B<br /><br />2017-12-31 | 2018-01-02<br /><br />$1 |  | 2018-01-04<br /><br />$1 |  |  | $2 |
| C | Orgánico<br /><br />2017-12-31 | 2018-01-01<br /><br />$1 |  |  |  | 2018-01-02<br /><br />$1 | $2 |

Observando los datos, ahora podemos resumir los ingresos recaudados por usuario, por día (y por evento in-app):

| Usuario | 2018-01-01 | 2018-01-02 | 2018-01-03 | 2018-01-04 | Valor del tiempo de vida (LTV) total |
| --- | --- | --- | --- | --- | --- |
| A | $1 | $1 | $1 | $1 | $4 |
| B |  | $1 |  | $1 | $2 |
| C | $1 | $1 |  |  | $2 |
| Total | $2 | $3 | $1 | $2 | $8 |

**Comprender los reportes:**

Como se mencionó, los ingresos por publicidad están vinculados al LTV del usuario. Por lo tanto, el período de tiempo seleccionado en el panel de control representa la cohorte de instalaciones para las que se suman los ingresos hasta la hora y el día actuales. Examinemos un reporte con dos selecciones de fechas diferentes:

Reporte agregado: fechas seleccionadas: 2017-12-31-2018-01-05

| Ecomonline | Ingresos de LTV |
| --- | --- |
| Orgánico | $2 |
| Red A | $4 |
| Red B | $2 |
| Red C | $2 |

En este caso, la cohorte está formada por los usuarios que instalaron la aplicación entre 2017-12-31 y el día actual, 2018-01-05. Todos los ingresos generados por esos usuarios se atribuyen a la fuente de adquisición y se reflejan en el LTV del usuario.

</Accordion>

<Accordion title="Raw data de ingresos por publicidad">

<Image align="center" alt="PremiumFeature.jpg" src="https://files.readme.io/674e5d0c9efde9d12008bd705b3ba95f04e133fec3f39d4278612675123d4de4-360007173877.jpg" width="78px" />

Los reportes de raw data de ingresos por anuncios contienen datos de redes de monetización con integración a nivel de dispositivo o de impresión con AppsFlyer.

**Principios del raw data de los ingresos por publicidad**

* Los datos se agregan por número de impresiones únicas por usuario. Las impresiones únicas se derivan de la combinación de la red de monetización de anuncios, el bloque de anuncios y la ubicación.
* El raw data a nivel de impresiones es:
  * Agregado a nivel de dispositivo y disponible en los reportes a nivel de dispositivo.
  * Disponible como reportes a nivel de impresión en Data Locker.

<table><thead><tr><th>Reporte</th><th>Página de datos exportados</th><th>API Pull </th><th>Casillero de datos</th></tr></thead><tbody><tr><td>Ingresos por publicidad atribuidos (no orgánicos)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Ingresos por publicidad orgánicos</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Ingresos por publicidad por retargeting </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Raw data a nivel de impresiones</td><td><span>-</span></td><td><span>-</span></td><td><span>✓ </span></td></tr><tr><td colspan="4"><p>\* El reporte versionado también está disponible, actualizado varias veces al día, con datos agregados a nivel de dispositivo. Los reportes de Data Locker no versionados son diarios. Para más información, consulta <a href="#01H8V10BKK6N5XJ6GHKC201E3Y">Frescura de los datos</a>.</p><p>\*\* Esto se refiere a los reportes con impression-level en el nombre, no a la integración de ingresos por anuncios a nivel de impresión.</p></td></tr></tbody></table>

**Características y campos de datos**

Los campos de los reportes de ingresos por publicidad se rellenan:

* Por el propio evento de ingresos por anuncios, y se indica en la tabla siguiente. Estos campos se dividen en:
  * **Específico:** campos específicos de los ingresos por publicidad. Por ejemplo, impresiones y colocación. **Requisitos previos**: **Nota**: Los campos rellenados difieren según el partner de monetización, como se muestra en la tabla Campos por red de esta sección.
  * **Contexto:** campos que tienen un significado similar en otros reportes de raw data. Por ejemplo, el nombre del evento, el valor del evento y la moneda.
* Como resultado de la atribución del evento a la fuente de medios que trajo al usuario. Es decir, estos campos se copian del evento de conversión que trajo al usuario. Por ejemplo, la fuente de medios y una campaña. Estos campos no se enumeran en la siguiente tabla.

<div id="fields-populated-by-ad-revenue" />

#### Campos rellenados por ingresos por publicidad

| api\_name | Nombre de campo | Tipo de campo | Descripción |
| --- | --- | --- | --- |
| <span id="event_time"></span>event\_time | Hora del evento | Contexto | La fecha a la que se atribuyen los ingresos |
| <span id="event_name"></span>nombre\_del\_evento | Nombre del evento | Contexto | Evento para asignar af\_ad\_revenue a |
| <span id="event_revenue"></span>ingresos\_evento | Divisa de ingresos del evento | Contexto | <ul><li>Cantidad de ingresos utilizando la moneda de ingresos del evento</li><li>Un valor cero indica impresiones sin ingresos.</li></ul> |
| <span id="event_revenue_currency"></span>moneda\_ingresos\_evento | Moneda del evento | Contexto | Divisa de ingresos del evento |
| <span id="event_revenue_xxx"></span>event\_revenue\_XXX | Ingresos del evento XXX | Contexto | <ul><li>En la página de exportación: ingresos convertidos a la moneda específica de la aplicación</li><li>En Data Locker, siempre en USD</li><li>En Pull API, según la moneda del Pull.</li></ul> |
| <span id="country"></span>País | País | Contexto | País de instalación de la conversión |
| <span id="ad_unit"></span>ad\_unit | Para SKAN 3, el valor es nulo. | Específico | El valor de este campo es específico de la red publicitaria. Para integraciones de servidor a servidor (S2S):<ul><li>**MAX:** Usa el ID de la unidad de anuncio (por ejemplo, f53328a3c).</li><li>**IronSource:** Usa el tipo de unidad de anuncio, como banner, rewarded\_video o interstitial.</li></ul>Para otras redes, consulta la guía de integración del partner correspondiente o ponte en contacto con el representante de tu red para confirmar el formato requerido. |
| <span id="segment"></span>segment | Segmento | Específico | Nombre de ubicación del anuncio |
| <span id="monetization_network"></span>monetization\_network | Monetization network | Específico | Red que envía el anuncio |
| <span id="impressions"></span>Impresiones | Impresiones | Específico | Número de veces que el usuario vio el anuncio |
| <span id="mediation_network"></span>mediation\_network | Mediation network | Específico | Red de mediación que informa el evento a AppsFlyer |
| <span id="customer_user_id"></span>ID de usuario | ID de usuario | Motive | Se completa si está disponible por parte del anunciante:<ul><li>Para las integraciones a nivel de impresión (SDK): se recopila mediante `setCustomerUserId()` en el SDK de AppsFlyer.</li><li>Para las integraciones de nivel de dispositivo (API): Se recopila desde la API de mediación (ID de usuario o ID de usuario del publisher configurado mediante el SDK de mediación).</li><li>Odeeo y Appodeal no lo admiten.</li></ul> |

<div id="fields-by-network" />

#### Campos por red

<table><thead><tr><th>Nombre para mostrar</th><th>Admob</th><th>Mediación de Unity LevelPlay (anteriormente ironSource)</th><th>AppLovin MAX</th><th>Appodeal</th><th>Fyber</th></tr></thead><tbody><tr><td>Para SKAN 3, el valor es nulo.</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Segmento</td><td>-</td><td>(1)</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Ubicación</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Monetization network</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Impresiones</td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td>Mediation network</td><td><span>-</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) El anunciante debe configurar esto en ironSource</td></tr></tbody></table>

[Reporte de muestra de raw data de ingresos por publicidad](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm_1tevWFdzdj6JgdxYawLBtYAJj-ubDeY4g1QfbdSkd2-Adi18oemPMdd7m7cM2e3fzm7VH0w6lhD/pub?output=xlsx)

</Accordion>

<Accordion title="Actualización de los datos">

La actualización de los datos depende del tipo de integración y del método de reporte.

Para las **integraciones de la API S2S**, el momento más temprano en que los datos pasan a estar disponibles es:

* Paneles de control y reportes (vía Data Locker) a partir del Día X+1, 8 AM UTC, aproximadamente 4 veces al día, cada 6 horas. Y, para los suscriptores de ROI360, los Días 2, 3, 7 y 14, una vez al día.

Para las **integraciones del SDK a nivel de impresión**, el momento más temprano en que los datos pasan a estar disponibles es:

* Dashboards (métricas de actividad y de cohorte): Continuo (15–60 minutos después de que ocurra el evento)
* Paneles de control y reportes (vía Data Locker) de mejor escenario, a partir del Día X desde las 5 AM UTC, actualizados aproximadamente 6 veces al día, cada 4 horas.
* Los reportes de raw data a nivel de impresiones (a través de Data Locker) son del Día X a partir de la 1 AM UTC, actualizados cada hora.

Para **el nivel de impresión (vía SDK) con el nivel de dispositivo (vía API S2S)**, obtienes la frescura de los datos para el día X con la precisión de los datos para los días X+1, de la siguiente manera:

* Para los datos de nivel de impresión que llegan a través del SDK:

  * Dashboards (métricas de actividad y de cohortes): continuo (15–60 minutos después de que ocurra el evento)
  * Paneles de control y reportes (vía Data Locker) de mejor escenario, a partir del Día X desde las 5 AM UTC, actualizados aproximadamente 6 veces al día, cada 4 horas.
  * Los reportes de raw data a nivel de impresiones (a través de Data Locker) son del Día X a partir de la 1 AM UTC, actualizados cada hora.
* Para los datos de nivel de dispositivo que llegan a través de la API S2S:

  * Paneles de control y reportes (vía Data Locker) a partir del Día X+1, 8 AM UTC, aproximadamente 4 veces al día, cada 6 horas. Y, para los suscriptores de ROI360, los Días 2, 3, 7 y 14, una vez al día.

Para **Raw Data Export and Pull API**, independientemente del tipo de integración o del paquete ROI360 (Advanced o Standard), los datos de un día determinado están disponibles al día siguiente, a las 6 PM UTC del día X+1. Los datos no se actualizan después de esta hora en estas herramientas.

**Nota:** La disponibilidad de datos intradía en dashboards requiere una suscripción a ROI360 Advanced.

</Accordion>

<Accordion title="Reportes de ingresos por anuncios de Data Locker">

| Nombre | Actualización | Secciones de los reportes |
| --- | --- | --- |
| ***Ingresos por publicidad diarios (agregados a nivel de dispositivo)*** | Los ingresos por publicidad para un día determinado (día X) se reportan al día siguiente (X+1), a las 8 PM UTC.<br /><br />Por ejemplo, los ingresos por publicidad del 1 de mayo se reportarán el 2 de mayo. | El reporte incluye las secciones de ingresos por anuncios atribuidos, orgánicos y de retargeting. |
| \*\*Reporte de ingresos por publicidad de versiones diarias\*\** \*\**(agregado a nivel de dispositivo) | El reporte diario consta de:<ul><li>Las versiones intradía se crean cada 4 horas durante el día de ingresos (día X). Los datos intradía se recopilan a través de la API del SDK.</li><li>Versiones de día completo creadas los días 1, 2, 3, 7 y 14, basadas en datos procedentes de reportes de la API S2S.</li></ul>Es decir, el conjunto de versiones de un reporte diario incluye las siguientes versiones:<ul><li>00:00 — 04:00 del día X.</li><li>00:00 — 08:00 del día X [conector ROI de SDK]</li><li>00:00 — 12:00 del día X [conector ROI de SDK]</li><li>00:00 — 24:00 del día X [conector ROI de SDK]</li><li>00:00 — 24:00 del día x+1 [S2S]</li><li>00:00 — 24:00 del día x+2 [S2S]</li><li>00:00 a 24:00 del día x+13 [S2S]</li><li>00:00 — 24:00 del día x+6 [S2S]</li><li>Para integraciones heredadas (anteriores a ROI360), la actualización de los datos es el Día X+1, a las 5 PM UTC como muy temprano.</li></ul> | Cada versión del reporte incluye las secciones de ingresos por anuncios atribuidos, orgánicos y de retargeting. |
| ***Reporte de ingresos por anuncios a nivel de impresión (a nivel de impresión)*** | Los registros de ingresos por publicidad de nivel de impresiones se escriben en un archivo separado cada hora. |  |

<span id="h_01KRKHJN2G5SER73D3EZB14GDS"></span>**Consulta también:**

* <Anchor target="_blank" href="/marketers/es/docs/revenue-etl-reports">Clave de reporte</Anchor>

</Accordion>

<div id="additional-information" />

## Información adicional

<Accordion title="Migrar de la granularidad agregada a la de nivel de dispositivo">

Recuerda lo siguiente al migrar de la granularidad agregada a la de nivel de dispositivo:

* La migración no afecta los datos históricos de ingresos por publicidad. Estos datos permanecen sin cambios.
* Los datos de ingresos por anuncios se extraen varias veces al día, a partir de las 03:00 UTC, con las opciones de granularidad seleccionadas en ese momento.
* La granularidad a nivel dispositivo no requiere que definas eventos in-app (como lo haces para los reportes de nivel agregado). Puedes seguir enviando estos eventos, ya que no afectan los reportes de granularidad a nivel dispositivo en AppsFlyer.

</Accordion>

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Limitaciones | Los eventos de ingresos por publicidad no están disponibles para:<ul><li>API push</li><li>Panel de Control de Retargeting</li></ul>Limitaciones de granularidad a nivel de dispositivo:<ul><li>El evento af\_ad\_revenue no está disponible para cohortes en Pivot y Master API.</li><li>El evento está disponible en análisis de cohortes.</li><li><Anchor target="_blank" href="/marketers/es/docs/applovin-max-ad-revenue-configuration#práctica-recomendada">Pueden producirse discrepancias al implementar los ingresos por pujas **in-app** de Anuncios de Meta.</Anchor></li></ul>No se admite el recuento de usuarios únicos que activan un evento af\_ad\_revenue en los dashboards de AppsFlyer. |
| IDs de dispositivo compatibles | Los siguientes ID de dispositivo son compatibles para la atribución de ingresos de anuncios:<ul><li>ID de aplicación</li><li>Identificador de anunciante (IDFA)</li><li>IDFV</li><li>GNA Company</li><li>ID de aplicación</li><li>ID de aplicación</li><li>IMEI</li></ul><ul><li>AppSet ID solo es compatible con las mediaciones de AppLovin MAX e ironSource LevelPlay. Consulta las instrucciones para desarrolladores para [recopilar AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |
| Acceso a la red de publicidad | No se puede acceder a los reportes de cohorte. |
| Acceso de agencias | Agencias:<ul><li>No pueden acceder a las configuraciones de ingresos por publicidad.</li><li>Pueden ver todos los paneles de control y los datos relevantes para ellos.</li></ul> |
| Transparencia de Agencias | No se admite |
| Zona horaria | Los ingresos por anuncios se muestran solo en los dashboards y reportes de AppsFlyer en la zona horaria UTC. Es decir, si los datos se reportan a las 2 PM UTC+2, en AppsFlyer se muestran como 2 PM UTC. Se procesan diariamente.<br /><br />Esto se debe a que AppsFlyer necesita normalizar los datos recopilados de múltiples fuentes y partners, la mayoría de los cuales reportan sus datos en UTC. |
| Truemoney | En AppsFlyer:<ul><li>El panel de control muestra la divisa específica de la aplicación del anunciante.</li><li>Los reportes de raw data muestran la divisa original y también la convierten a la divisa específica de la aplicación del anunciante.</li></ul> |
| Tipo de datos | Se admiten tanto los datos orgánicos como los no orgánicos |
| Granularidad de datos | [Ingresos por anuncios](#01H8V10BKK6N5XJ6GHKC201E3Y) |
| Datos históricos/retroactivos | <ul><li>Los datos se extraen y están disponibles desde el día de la integración. Esto significa que los datos históricos no están disponibles antes de la fecha de integración (día 0).</li><li>Los datos de ingresos por publicidad recibidos a través de la API S2S para un día específico se actualizan los días 1, 2, 3, 7 y 14.</li><li>Los datos de ingresos por anuncios en los dashboards de Overview, Cohort y Activity, así como los datos a través de la Master API y la Cohort API, se actualizan retroactivamente; a través de la exportación de raw data y la Pull API, no. Si tienes el paquete de ingresos avanzado, los datos también se actualizan en Data Locker.</li></ul> |
| Acceso de usuario a la cuenta | Compatible |
| SKÁN | Compatible con conectores SDK de ingresos por publicidad a nivel de impresión. |
| Geolocalización/país | En el dashboard de Cohort, cuando la geolocalización es desconocida (N/A), los datos N/A no se muestran al agregar por geolocalización. |
| Postbacks de eventos in-app | <ul><li>Los postbacks a partners pueden ser para «solo este partner» o «todas las fuentes de medios, incluidas las orgánicas». <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#opciones-para-enviar-postbacks">Más información</Anchor></li><li>Para dar señales a las redes de publicidad y UA, los partners mediadores deben tener una integración a nivel de impresión o a nivel de dispositivo.</li></ul> |
| Aplicaciones de CTV, PC y consola | <ul><li>Solo se admiten aplicaciones de Android e iOS.</li><li>La plataforma Windows (UWP) cuenta con soporte de Vungle.</li><li>No se admite ninguna otra plataforma.</li></ul> |
| ID de cliente | Compatible tanto con integraciones de SDK como de nivel de dispositivo. |
| Conteo de eventos en dashboard | Se espera que el conteo de eventos sea mayor en los datos intradía (del día actual) que en los periodos históricos. Los datos históricos se agregan en impresiones únicas de ingresos de anuncios (mismo dispositivo × red × unidad de anuncio × placement), lo que da como resultado un conteo de eventos menor. |

</Accordion>

<Accordion title="Lista de Partners integrados de ingresos por anuncios">

<table><thead><tr><th rowspan="2">Fuente de medios</th><th colspan="3">Tipo de integración disponible</th></tr><tr><th>Nivel de dispositivo</th><th>Nivel de dispositivo</th><th>ImpressionLevelAdRevenue</th></tr></thead><tbody><tr><td>Admost</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./applovin-campaign-configuration#ad-revenue-tab" target="_blank">AppLovin</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./applovin-max-ad-revenue-configuration" target="_blank">Applovin Max</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./appodeal-campaign-configuration" target="_blank">Appodeal</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./bytedance-ads-china-campaign-configuration" target="_blank">Anuncios de Bytedance: tráfico de China</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>TikTok for Business</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./chartboost-campaign-configuration#ad-revenue-tab" target="_blank">Chartboost</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td>Mediación a medida</td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td>Google Ads</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./meta-ads-integration-setup" target="_blank">Meta Ads</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./fyber-campaign-configuration#ad-revenue-tab" target="_blank">Fyber</a></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./google-admob-ad-revenue-attribution-configuration" target="_blank">Google Admob</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td> <a href="./ironsource-campaign-configuration#ad-revenue-tab" target="_blank">ironSource</a> (LevelPlay)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Odeeo</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tapjoy</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Topon</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>TopOn</td><td>-</td><td>-</td><td> <span>✓</span><br/> </td></tr><tr><td>Tradplusad</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./unity-ads-campaign-configuration" target="_blank">Unity Ads</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Unidad de anuncio</td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td>Voodoo Ads</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./vungle-campaign-configuration" target="_blank">Vungle</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Yandex</td><td>-</td><td>-</td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div data-zendesk-anchors="ad-revenue-attribution=atribuci%C3%B3n-de-ingresos-por-publicidad 01ECF1PZ2XNCHR4QPATTBV0VMV=atribuci%C3%B3n-de-ingresos-por-publicidad implementation=implementaci%C3%B3n 01ECF1PZ2Y9ERT5C50ZD4CDJET=implementaci%C3%B3n h_01_custom_mediation_note=advertencia h_01M1TXMH5P53PNVW56GHZEXKKK=nota aggregate-ad-revenue-using-events=ingresos-por-publicidad-agregados-mediante-eventos 01H8V10BKK06Z3E823G6GNTPKH=ingresos-por-publicidad-agregados-mediante-eventos comparison-of-inapp-event-methods=comparaci%C3%B3n-de-m%C3%A9todos-de-eventos-in-app 01H8V10BKKMG2A704NZC2VFSJM=comparaci%C3%B3n-de-m%C3%A9todos-de-eventos-in-app h_01_sdk_live_events_note=advertencia-1 ad-revenue-data=datos-de-ingresos-por-publicidad 01ECF1PZ3315R242DC78HV60YC=datos-de-ingresos-por-publicidad overview-dashboard-aggregated-performance-report=panel-de-informaci%C3%B3n-general---reporte-de-estad%C3%ADsticas-agregadas-de-rendimiento 01ECF1PZ348365STFGE3136WEJ=panel-de-informaci%C3%B3n-general---reporte-de-estad%C3%ADsticas-agregadas-de-rendimiento 01ECF1PZ348P0JCBASS4QBD56W=ejemplos fields-populated-by-ad-revenue=campos-rellenados-por-ingresos-por-publicidad 01H8V10BKK7BHC31W27G22D23K=campos-rellenados-por-ingresos-por-publicidad fields-by-network=campos-por-red 01H8V10BKKW6NERRYCRD6BVZ54=campos-por-red additional-information=informaci%C3%B3n-adicional 01H8V10BKMX7H9H04ZBF3HRJVY=informaci%C3%B3n-adicional" />

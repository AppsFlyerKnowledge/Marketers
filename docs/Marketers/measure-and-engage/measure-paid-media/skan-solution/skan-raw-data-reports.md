---
title: Reportes de raw data de SKAN
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2026-10-20T03:49:10Z'
  id: 360014261518
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/360014261518
---
> **En resumen:** Los reportes de raw data de SKAN contienen datos a nivel de fila, generados después de traducir y decodificar los postbacks recibidos por AppsFlyer desde iOS, así como los postbacks de raw data de SKAN. Los datos están disponibles a través de <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Data Locker</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">Push API</Anchor>. Si tu plan de suscripción incluye raw daya, no es necesario tener una suscripción a Data Locker.

## Reportes de raw data de SKAN

Principios:

* **Los datos son proporcionados por:**
  * **Casillero de datos**
    * [Práctica recomendada]: ¡**Importante**! Disponible para cuentas que tengan una suscripción de raw data. Es decir, no hay necesidad de una suscripción a Data Locker. Si actualmente no estás usando Data Locker, un usuario administrador debe configurar Data Locker y habilitar los reportes de SKAN. Para ello, ve a **Reportes** > **Data Locker**. Selecciona los reportes de SKAN.
    * **Tasa de actualización de los datos**: Diariamente. Los datos se incluyen en la carpeta h=23 de la fecha en que AppsFlyer recibe el postback.
  * **API Push**
    * Ver <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">Push API para datos de SKAN</Anchor>.
* **Fecha de instalación**: La calcula AppsFlyer a partir de la hora de llegada del postback, de la siguiente manera:
  * Si los postbacks son SKAN V4, la fórmula de la fecha de instalación es: Fecha de instalación = hora de llegada del postback - [duración acumulada de la ventana] - [retraso medio del postback].
    * Postback 1: fecha de instalación = hora de llegada del postback - 48h - 36h
    * Postback 2: fecha de instalación = hora de llegada del postback - 168h - 84h
    * Postback 3: fecha de instalación = hora de llegada del postback - 840h - 84h
  * Si los postbacks son SKAN V3, la fórmula de la fecha de instalación es: Fecha de instalación = hora de llegada después del postback: 36 horas (promedio del último intervalo activo). 
    * El [promedio del último rango activo] predeterminado es de 12 horas.
    * Para un valor de conversión de 0, el rango promedio de última actividad se establece en 0.
  * Google estima la hora de instalación por su cuenta y AppsFlyer utiliza esa hora de instalación. **Nota**: Google puede tardar hasta 45 días en reportar las instalaciones. <Anchor target="_blank" href="/marketers/es/docs/get-skan-postback-data-from-google-ads#obtener-datos-de-postbacks-de-skan-de-google-ads">Saber más</Anchor>

Los tipos de reportes disponibles son:

* **Postbacks del dispositivo**: 1 postback de dispositivo por cada instalación o redescarga recibida desde el dispositivo iOS.
* **Raw data de SKAN**:
  * AppsFlyer decodifica y traduce el postback del dispositivo en registros de raw data.
  * Cada postback genera un registro de instalación o redescarga y registros de eventos in-app.
  * El número de registros de eventos in-app depende del valor de conversión (CV), de la siguiente manera:
    * CV = 0, blank, o null: No se generan registros en la aplicación.
    * Rango de CV:
      * 1-63: Para SKAN 3, y el valor preciso de la ventana 1 de SKAN 4, este es el número de registros in-app, en función de tus ajustes de medición.
      * Bajo, medio o alto: Para los valores aproximados de SKAN 4, este es el número de registros in-app, en función de tus ajustes de medición.

**¿Por qué algunos campos están vacíos?** Esto ocurre por cualquiera de las siguientes razones:

* Campos de enriquecimiento no obligatorios como campaign\_name, ad\_network\_campaign\_id, ip que la red de publicidad no proporcionó.
* Apple retuvo los datos debido a las políticas de umbral de Apple. Campos como source\_app\_id, skad\_campaign\_id, skad\_conversion\_value.

## Formato y contenido de los reportes de raw data de SKAN

<div id="raw-data-report-types" />

<Accordion title="Tipos de reportes de raw data">

<Table>
  <thead>
    <tr>
      <th>
        Tipo de reporte
      </th>
      <th>
        Nombre del informe
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="postback"></span>
        Postback
      </td>
      <td>
        Devoluciones de mensajes
      </td>
      <td>
        Postbacks enviados por iOS a la red de publicidad. El postback, después del enriquecimiento por parte de la red de publicidad, se reenvía a AppsFlyer. [Descargar ejemplo de postbacks](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv) (CSV).

        Nota: Nota: Los postbacks no se incluyen cuando did\_win=false.

        **Nombre del tema en Data Locker**: skad\_postbacks
      </td>
    </tr>
    <tr>
      <td><span id="postback::315d5a62"></span>
        Postback
      </td>
      <td>
        Copia de postbacks (directa de Apple)
      </td>
      <td>
        Postbacks enviados directamente por iOS a AppsFlyer.

        Está disponible a partir de iOS 15+ y requiere que el anunciante configure la aplicación para <Anchor target="_blank" href="/marketers/es/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">enviar el postback ganador</Anchor> a AppsFlyer. [Descargar ejemplo de copia de postbacks](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv) (CSV).

        Nota: Este tema contiene solo postbacks ganadores.

        **Nombre del tema en Data Locker**: skad\_postbacks\_copy
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event"></span>
        Evento decodificado
      </td>
      <td>
        Instalaciones
      </td>
      <td>
        **Primeras instalaciones de aplicaciones**

        SKAN reportó *redownload=false*. Es decir que esta es la primera vez que el usuario, representado por el ID de Apple, descargó la aplicación.  
        [Descargar ejemplo de instalaciones](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv) (CSV).

        **Nombre del tema en Data Locker**: skad\_installs
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5c7e459f"></span>
        Evento decodificado
      </td>
      <td>
        Re-descargas
      </td>
      <td>
        **Instalaciones de aplicaciones que no son primeras instalaciones**

        SKAN reportó *redownload=true*. Es decir que esta no es la primera vez que el usuario, representado por el ID de Apple, descargó la aplicación. Este reporte tiene la misma estructura que las instalaciones.

        **Nombre del tema en Data Locker**: skad\_redownloads
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::b8f2b4a4"></span>
        Evento decodificado
      </td>
      <td>
        Eventos dentro de la aplicación
      </td>
      <td>
        **Eventos dentro de la aplicación**

        A partir del 21 de julio de 2021, habrán cambios en la forma en que proporcionamos el raw data de los eventos in-app, como se detalla en las tablas.

        El número de registros de eventos in-app depende de tu configuración de la medición.

        [Descargar ejemplo de eventos in-app](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv) (CSV).

        **Nombre del tema en Data Locker**: skad\_inapps

        Válido para postbacks de iOS recibidos a partir del 21 de julio de 2021:

        | Tipo de medición | Descripción |
        | --- | --- |
        | Ingresos | * Ingresos de un usuario determinado. Si los ingresos son > 0, un registro contiene los campos skad\_revenue y event\_name.<br />* Los campos min\_revenue y max\_revenue se rellenan con tus valores de rango de conversión personalizados. |
        | Eventos de conversión in-app y de funnel | * Un registro para cada evento de conversión único realizado. El campo event\_name se rellena en consecuencia. Si no se realizan eventos, no hay ningún registro.<br />* Los eventos de conversión tienen min\_event\_counter = 0 y max\_event\_counter = 1. |
        | Engagement in-app | Para determinar el número de veces que un usuario realizó un evento en la aplicación, utiliza la fórmula`[round up (min_event_counter + max_event_counter) / 2]` |

        Válido para postbacks de iOS recibidos hasta el 20 de julio de 2021:

        | Tipo de medición | Número de registros | Descripción |
        | --- | --- | --- |
        | Ingresos | 0-1 | Si los ingresos son > 0, un registro contiene los campos skad\_revenue y event\_name. |
        | Conversión | 0-6 | Un registro para cada evento de conversión único realizado. El campo event\_name se rellena en consecuencia. Si no se realizan eventos, no hay ningún registro. |
        | Participación | 0-63 | El número de registros representa el número de veces que el usuario realizó el evento de engagement. Si el usuario no se involucra, no hay registros de engagement. |
        | Personalizado | 0-ilimitado | De acuerdo con tu esquema de conversión personalizado. |
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5dac9cbb"></span>
        Evento decodificado
      </td>
      <td>
        Dimensiones publicitarias de SRN
      </td>
      <td>
        * El reporte contiene eventos de Meta Ads con granularidad de campaña, conjunto de anuncios y anuncio. Cada fila del reporte puede ser una instalación o un evento in-app.
        * La granularidad de adset y anuncio no está incluida en los postbacks de SKAN de los Meta Ads. Estos datos son únicos para este reporte y no se muestran en el dashboard de SKAN, la API de rendimiento y otros reportes de SKAN Data Locker.
        * El reporte es sin esquema. Las opciones de selección de campo de Data Locker no se aplican.
        * Mejores prácticas: No combines ni compares los datos de este reporte con otros reportes de SKAN, ya que puede haber discrepancias entre este, que utiliza datos decodificados por el SRN, y otros, que utilizan datos decodificados por AppsFlyer. Estas discrepancias pueden deberse a diferencias de zona horaria, diferencias en el esquema de SRN o eventos in-app mapeados incorrectamente a CV en la integración de SRN.
        * <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx">Descargar ejemplo de dimensiones publicitarias de SRN</Anchor> (CSV).

        **Nombre del tema en Data Locker**: skad\_srn\_advertising\_dimensions
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-field-format-types" />

<Accordion title="Tipos de formato de los campos de raw data">

#### Formatos de campo

| Nombre del formato | Descripción |
| --- | --- |
| Cadena [n] | La longitud máxima de la cadena. Por lo general, no aplicamos limitaciones de longitud de campo al recibir los datos, pero los datos pueden truncarse como consecuencia de ello. |
| Cadena temporal | Cadena con el formato, `yyyy-mm-dd hh:mm:ss`. Por ejemplo, `2019-09-17 00:09:25` |
| Enumeración [n] | Los campos de enumeración solo pueden contener valores específicos. Por ejemplo, la divisa de costo tiene 3 caracteres y puede contener solo códigos de divisa según lo especificado. |
| Marca de tiempo | Marca de tiempo UNIX de 10 dígitos. Ejemplo:<br /><br />4 de agosto de 2020 a las 07:25 UTC se traduce como `"timestamp": "1596525944"` |
| Booleano | El valor del campo puede ser `TRUE` o `FALSE` |
| Entero | Entero |
| Flotante | Número flotante real que puede tener un punto decimal y valores después del punto decimal. |

</Accordion>

<div id="fields-available-in-postback-and-postback-copy-reports" />

<Accordion title="Campos disponibles en reportes de postback y de copia de postback">

<table><thead><tr><th>Nombre del campo</th><th>Fuente o versión inicial de SKAN de iOS</th><th>Descripción</th><th>Formato</th><th>Disponible en copia de postbacks </th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>Red de anuncios</td><td>ID de campaña informado por la red publicitaria a AppsFlyer</td><td>Cadena</td><td>No</td></tr><tr><td><p>ad_network_campaign</p><p>_nombre</p></td><td>Red de anuncios</td><td><p>Nombre de la campaña reportado por la red de publicidad a AppsFlyer.</p></td><td>Cadena</td><td>No</td></tr><tr><td>ad_network_timestamp</td><td>Red de anuncios</td><td><p>Hora en que la red de publicidad recibió el postback.</p><p>En el caso de Google Ads, la hora se deriva del último clic reportado por Google.</p></td><td>Marca de tiempo</td><td>No</td></tr><tr><td>id_aplicación</td><td>AppsFlyer</td><td>ID de aplicación (aplicación del anunciante) con ID de prefijo.</td><td>Cadena</td><td>Sí</td></tr><tr><td>ciudad</td><td>AppsFlyer</td><td>A partir del 30 de agosto de 2021, siempre nulo </td><td>Cadena</td><td>No</td></tr><tr><td>código_de_país</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>dma</td><td> </td><td>A partir del 30 de agosto de 2021, siempre nulo </td><td>Cadena</td><td>No</td></tr><tr><td>postal_code</td><td> </td><td>A partir del 30 de agosto de 2021, siempre nulo  </td><td>Cadena</td><td>No</td></tr><tr><td>región</td><td>AppsFlyer</td><td>Según el country_code reportado</td><td>Cadena</td><td>No</td></tr><tr><td>skad_ad_network_id</td><td>1.0 </td><td>Algunas SRN no comparten su ID y el campo se deja en blanco. Por ejemplo, X Ads. </td><td>Cadena</td><td>Sí </td></tr><tr><td>skad_attribution_signature</td><td>1.0</td><td> </td><td>Cadena</td><td>Sí</td></tr><tr><td>skad_campaign_id</td><td>1.0</td><td>ID de campaña usada para publicar el anuncio. Intervalo 0-100</td><td>Cadena</td><td>Sí</td></tr><tr><td>skad_conversion_value</td><td>2.0 </td><td><p>Valor de conversión reportado por iOS. Rango 0-63.</p><p>Si es nulo, iOS no rellenó el campo.\*\* </p></td><td>Entero</td><td>Sí</td></tr><tr><td>skad_redownload</td><td>2.0</td><td>Si es true, la aplicación se volvió a descargar</td><td>Booleano</td><td>Sí</td></tr><tr><td>skad_source_app_id</td><td>2.0</td><td><p>ID del sitio. La aplicación que publica el anuncio. Este campo es idéntico a source_app_id.</p><p>El relleno del campo depende de los umbrales de privacidad\*\*</p></td><td>Cadena</td><td>Sí</td></tr><tr><td>skad_transaction_id</td><td>1.0</td><td> </td><td>Cadena</td><td>Sí</td></tr><tr><td>versión_skad</td><td>2.0</td><td> </td><td>Cadena</td><td>Sí</td></tr><tr><td>timestamp</td><td>Red de anuncios</td><td>Hora en que AppsFlyer recibió el postback de SKAN. </td><td>Cadena de tiempo</td><td>Sí</td></tr><tr><td>ad_network_name</td><td>Red de anuncios</td><td><p>Nombre de la red de publicidad reportado por la red de publicidad a AppsFlyer. </p><ul><li>Si este campo está vacío, la red publicitaria no lo ha completado.</li><li>Puede resolver el nombre de la red publicitaria usando skad_ad_network_id. Utiliza <a href="./skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks" target="_blank">esta tabla</a> para hacerlo. </li></ul></td><td>Cadena</td><td>No</td></tr><tr><td>ip</td><td> </td><td><p>Dirección IP en el mensaje HTTP del dispositivo iOS que envía el postback.</p><p>Este campo se rellena si la red de publicidad nos proporciona la dirección.</p><p>¡Atención! ¡Nota! El SDK no está involucrado en la obtención de la dirección.</p></td><td>Cadena</td><td>No</td></tr><tr><td>skad_app_id</td><td>1.0</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>ID de la aplicación de origen</td><td>AppsFlyer</td><td>ID del sitio. La aplicación que publica el anuncio. Este campo es idéntico a skad_source_app_id</td><td>Cadena</td><td>No</td></tr><tr><td>ad_network_adset_id</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>ad_network_adset_name</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>ad_network_ad_name</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>ad_network_ad_id</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>did_win</td><td>3.0 (iOS 14.6)</td><td><p>Se utiliza para distinguir entre campañas <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">que contribuyen a la instalación o a las que se les atribuye la instalación</a>. </p><ul><li>Si es verdadero, la campaña se atribuye por haber realizado la instalación.</li><li>Si es falso, se reconoce que la campaña ha contribuido a la instalación, pero no se incluye en ningún panel ni informe de SKAN.</li><li>Si es nulo, iOS no rellenó el campo debido a una <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">versión heredada de iOS o SKADNetwork</a>.</li></ul></td><td>Booleano</td><td>Sí</td></tr><tr><td>fidelity_type</td><td>2.2 (iOS 14.5)</td><td><p>Permite diferenciar entre las opciones de <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">presentación de anuncios</a> que afectan a la atribución. Se indica utilizando los valores 0 y 1 de la siguiente manera: </p><ul><li>Anuncios de visualización (0)</li><li>Anuncios renderizados por StoreKit (1)</li></ul><p>Ignore el valor del campo si la versión de SKAN es anterior a la 2.2.</p></td><td>Entero</td><td>Sí</td></tr><tr><td>id_app_fuente_red_publicitaria</td><td>Red de anuncios</td><td><span>ID de la aplicación del editor informado por la red publicitaria. Úselo para ayudar en la conciliación de costes; informado por la red publicitaria. La base de estos datos la proporciona la aplicación del publisher. </span></td><td>Cadena</td><td>No</td></tr><tr><td>ad_network_channel</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>af_prt</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0 (iOS 16.2)</td><td><ul><li>El valor representa la ventana SKAN <code>0</code>, <code>1</code> o <code>2</code>.</li><li>Para SKAN 3, el valor es <code>0</code> </li></ul></td><td>Entero</td><td>Sí</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li>El valor puede ser <code>low</code>, <code>medium</code>, o <code>high</code>.</li><li>Para SKAN 3, el valor es <code>null</code>.</li></ul></td><td>Cadena</td><td>Sí</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>El valor puede tener hasta 4 dígitos.</li><li>Para SKAN 3, el valor es <code>null</code>. </li></ul></td><td>Cadena</td><td>Sí</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>El valor representa la fuente de anuncios web atribuibles.</li><li>Para SKAN 3, el valor es <code>null</code>.</li></ul></td><td>Cadena</td><td>Sí</td></tr><tr><td>ad_network_creative</td><td>Red de anuncios</td><td><ul><li>El valor se basa en el enriquecimiento de datos recibido de la red de anuncios.</li><li>Para SKAN 3, el valor es <code>null</code>.</li></ul></td><td>Cadena</td><td>No</td></tr><tr><td colspan="4">\*\* Apple determina si el campo se rellena, mediante un mecanismo de umbral de privacidad. </td><td> </td></tr></tbody></table>

</Accordion>

<div id="fields-available-in-decoded-event-reports" />

<Accordion title="Campos disponibles en los reportes de eventos decodificados">

<table><thead><tr><th>Nombre del campo</th><th>Fuente</th><th>Descripción</th><th>Formato</th><th>Incluido en el reporte de dimensiones publicitarias de SRN</th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>Red de anuncios</td><td>ID de campaña informado por la red publicitaria a AppsFlyer</td><td>Cadena</td><td>Sí</td></tr><tr><td>ad_network_campaign<br/>_nombre</td><td>Red de anuncios</td><td>Nombre de la campaña informado por la red publicitaria a AppsFlyer</td><td>Cadena</td><td>Sí</td></tr><tr><td>ad_network_timestamp</td><td>Red de anuncios</td><td>Momento en que la ad network recibió el postback. En Google Ads, este campo se rellena, pero el valor es una hora estimada de instalación, no la hora real de recepción del postback. Consulta <a href="./get-skan-postback-data-from-google-ads" target="_blank">Obtener datos de postback de SKAN desde Google Ads</a> para obtener más información.</td><td><p>Marca de tiempo</p><p>(cadena de tiempo para el reporte de dimensiones publicitarias SRN)</p></td><td>Sí</td></tr><tr><td>id_aplicación</td><td>apps de iOS,</td><td>El ID de aplicación (aplicación del anunciante).</td><td>Cadena</td><td>Sí</td></tr><tr><td>ciudad</td><td> </td><td>A partir del 30 de agosto de 2021, siempre nulo </td><td>Cadena</td><td>No</td></tr><tr><td>código_de_país</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>dma</td><td> </td><td>A partir del 30 de agosto de 2021, siempre nulo </td><td>Cadena</td><td>No</td></tr><tr><td>nombre_del_evento</td><td>AppsFlyer</td><td><p>Nombre del evento in-app configurado en AppsFlyer.</p><p>Para SRN ___report, es el nombre del evento in-app configurado en Anuncios de Meta.</p></td><td>Cadena</td><td>Sí</td></tr><tr><td>UUID del evento</td><td>AppsFlyer</td><td>Un identificador único y aleatorio que permite a los socios identificar postbacks duplicados</td><td>Cadena</td><td>No</td></tr><tr><td>fecha_de_instalación</td><td>apps de iOS,</td><td>Estimado por AppsFlyer basándose en el momento de llegada del postback.</td><td>Cadena temporal</td><td>No</td></tr><tr><td>tipo_de_instalación</td><td>apps de iOS,</td><td>Nuevas instalaciones</td><td>Cadena</td><td>No</td></tr><tr><td>ip</td><td>apps de iOS,</td><td><p>La dirección IP en el mensaje HTTP del dispositivo iOS que envía el postback.</p><p>Este campo se rellena si la red de publicidad nos proporciona la dirección.</p><p>¡Atención! ¡Nota! El SDK no está involucrado en la obtención de la dirección. </p></td><td>Cadena</td><td>No</td></tr><tr><td>fuente_medios</td><td>apps de iOS,</td><td>Red de publicidad atribuida utilizando nombres de red de AppsFlyer</td><td>Cadena</td><td>Sí</td></tr><tr><td>postal_code</td><td> </td><td>A partir del 30 de agosto de 2021, siempre nulo </td><td>Cadena</td><td>No</td></tr><tr><td>región</td><td>AppsFlyer</td><td>Determinada según el código del país</td><td>Cadena</td><td>No</td></tr><tr><td>skad_ad_network_id</td><td>apps de iOS,</td><td>ID de la red publicitaria a la que se envió el postback.</td><td>Cadena</td><td>No</td></tr><tr><td>skad_ambiguous_event (obsoleto con SKAN 4+)</td><td>AppsFlyer</td><td><p>Si es verdadero, el postback de iOS se recibió en las primeras 72 horas después de que un anunciante cambió la configuración de SKAN en el panel. Debido a los diferentes temporizadores que utiliza SKAN, AppsFlyer no puede mapear el evento con precisión.</p><ul><li>No disponible en SKAN 4 y posteriores</li></ul></td><td>Booleano</td><td>No</td></tr><tr><td>skad_attribution_signature</td><td>apps de iOS,</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>skad_campaign_id</td><td>apps de iOS,</td><td>ID de campaña usada para publicar el anuncio. Intervalo 0-100</td><td>Entero</td><td>No</td></tr><tr><td>skad_conversion_value</td><td>apps de iOS,</td><td><p>Valor de conversión reportado por iOS. Rango 0-63.</p><p>Si es nulo, iOS no rellenó el campo.\*\*</p></td><td>Entero</td><td>No</td></tr><tr><td>modo_skad</td><td>AppsFlyer</td><td><p>El modo de medición de conversión usado para decodificar el postback de iOS. Opciones:</p><ul><li>decodificación_personalizada</li><li>ingresos</li><li>eventos</li><li>skan4</li><li>codificación_personalizada</li><li>participación</li></ul></td><td>Cadena</td><td>No</td></tr><tr><td>skad_redownload</td><td>apps de iOS,</td><td>Si es verdadero, la aplicación se descargó de nuevo.</td><td>Booleano</td><td>No</td></tr><tr><td>ingresos_skad</td><td>apps de iOS,</td><td>Monto de ingresos del evento en USD.</td><td>Flotante</td><td>No</td></tr><tr><td>skad_source_app_id</td><td>apps de iOS,</td><td><p>ID del sitio: la aplicación que publica el anuncio.</p><p>El relleno del campo depende de los umbrales de privacidad\*\*</p></td><td>Cadena</td><td>No</td></tr><tr><td>skad_transaction_id</td><td>apps de iOS,</td><td>-</td><td>Cadena</td><td>No</td></tr><tr><td>versión_skad</td><td>apps de iOS,</td><td>-</td><td>Cadena</td><td>No</td></tr><tr><td>timestamp</td><td>apps de iOS,</td><td><p>Hora en que AppsFlyer recibió el postback de SKAN.</p><p>Para los anuncios de Google y Meta, este es el momento en que AppsFlyer recibe los datos de la API de anuncios de Google y Meta, respectivamente.</p></td><td><p>Marca de tiempo</p><p>(cadena de tiempo para el reporte de dimensiones publicitarias SRN)</p></td><td>Sí</td></tr><tr><td>event_value</td><td>S2S</td><td><p>Valor predeterminado: nulo</p><p>Contiene una cadena establecida por aplicaciones que implementan decodificación personalizada.</p><p>Este valor es utilizado por los anunciantes en sus sistemas. AppsFlyer no lo emplea. </p></td><td>Cadena (JSON)</td><td>No</td></tr><tr><td>ad_network_adset_id</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>Sí</td></tr><tr><td>ad_network_adset_name</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>Sí</td></tr><tr><td>ad_network_ad_name</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>Sí</td></tr><tr><td>ad_network_ad_id</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>Sí</td></tr><tr><td>skad_did_win (1)</td><td>3.0 (iOS 14.6)</td><td><p>Se utiliza para distinguir entre campañas que <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">contribuyen o se les atribuye</a> una instalación. </p><ul><li>Si es verdadero, la campaña se atribuye por haber realizado la instalación.</li><li>Si es false, se reconoce que la campaña contribuye a la instalación, pero no se incluye en ningún panel de control o reporte de SKAN.</li><li>Si es nulo, iOS no rellenó el campo debido a una <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">versión heredada de iOS o SKADNetwork</a>.</li></ul></td><td>Booleano</td><td>No</td></tr><tr><td>skad_fidelity_type (1)</td><td>2.2 (iOS 14.5)</td><td><p>Permite diferenciar entre las opciones de <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">presentación de anuncios</a> que afectan a la atribución. Se indica utilizando los valores 0 y 1 de la siguiente manera: </p><ul><li>Anuncios de visualización (0)</li><li>Anuncios renderizados por StoreKit (1)</li></ul><p>Ignore el valor del campo si la versión de SKAN es anterior a la 2.2.</p></td><td>Entero</td><td>Sí</td></tr><tr><td>ad_network_source_app_id (1)</td><td>Red de anuncios</td><td><span>ID de la aplicación del editor informado por la red publicitaria. Úselo para ayudar en la conciliación de costes; informado por la red publicitaria. La aplicación del editor proporciona la base para estos datos.</span></td><td>Cadena</td><td>No</td></tr><tr><td>ad_network_channel (1)</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>af_prt (1)</td><td>Red de anuncios</td><td> </td><td>Cadena</td><td>No</td></tr><tr><td>min_revenue </td><td>AppsFlyer</td><td>Ver nota (4)</td><td>Número real</td><td>No</td></tr><tr><td>max_revenue </td><td>AppsFlyer</td><td>Ver nota (4)</td><td>Número real</td><td>No</td></tr><tr><td>ingresos_evento</td><td>AppsFlyer</td><td>Fórmula: [suma de valores para el evento específico en dólares americanos]/[el número de eventos que ocurrieron en un día específico]</td><td>Flotante</td><td>Sí</td></tr><tr><td>contador_de_eventos_min</td><td>AppsFlyer</td><td>Se utiliza para calcular cuántas veces realiza un usuario un evento. Ver nota (3)</td><td>Entero</td><td>No</td></tr><tr><td>contador_máximo_de_eventos</td><td>AppsFlyer</td><td>Ver nota (3)</td><td>Entero</td><td>No</td></tr><tr><td>tiempo mín. post-instalación</td><td>AppsFlyer</td><td>Ver nota (5)</td><td>Entero</td><td>No</td></tr><tr><td>tiempo máx. post-instalación</td><td>AppsFlyer</td><td>Ver nota (5)</td><td>Entero</td><td>No</td></tr><tr><td>af_attribution_flag</td><td>AppsFlyer</td><td>Cuando el mecanismo de Single Source of Truth (SSOT) está activado: Si es verdadero, la instalación fue atribuida tanto por AppsFlyer como por SKAN. Si es falso, la instalación no fue atribuida por AppsFlyer. Si skad_conversion_value es nulo, el indicador es verdadero o falso (basado en el <a href="./skan-modeled-data#null-conversion-values" target="_blank">modelado</a>).</td><td>Booleano</td><td>No</td></tr><tr><td>measurement_window</td><td>AppsFlyer</td><td>Duración de la ventana de actividad. Predeterminado: 24h. </td><td>Entero</td><td>No</td></tr><tr><td>intervalo</td><td>AppsFlyer</td><td>Intervalos de ventanas de actividad. </td><td>Entero</td><td>No</td></tr><tr><td>agente_usuario</td><td>AppsFlyer</td><td>Agente de usuario del dispositivo</td><td>Cadena</td><td>No</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0 (iOS 16.2)</td><td><ul><li>El valor representa la ventana SKAN <code>0</code>, <code>1</code> o <code>2</code>.</li><li>Para SKAN 3, el valor es <code>0</code> </li></ul></td><td>Entero</td><td>Sí</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li>El valor puede ser <code>low</code>, <code>medium</code>, o <code>high</code>.</li><li>Para SKAN 3, el valor es <code>null</code>.</li></ul></td><td>Cadena</td><td>Sí</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>El valor puede tener hasta 4 dígitos.</li><li>Para SKAN 3, el valor es <code>null</code>. </li></ul></td><td>Cadena</td><td>Sí</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>El valor representa la fuente de anuncios web atribuibles.</li><li>Para SKAN 3, el valor es <code>null</code>.</li></ul></td><td>Cadena</td><td>Sí</td></tr><tr><td>ad_network_creative</td><td>Red de anuncios</td><td><ul><li>El valor se basa en el enriquecimiento de datos recibido de la red de anuncios.</li><li>Para SKAN 3, el valor es <code>null</code>.</li></ul></td><td>Cadena</td><td>No</td></tr><tr><td colspan="4"><p>\*\* Apple determina si el campo se rellena, mediante un mecanismo de umbral de privacidad.</p><p>(1) A partir del 2 de junio de 2021, el campo se agrega a los reportes, pero no necesariamente se rellenará.</p><p>Para determinar el número de veces que un usuario realizó un evento in-app, utiliza la fórmula: <code>[round up (min_event_counter + max_event_counter) / 2]</code>. ¡Atención! ¡Nota! <mark>Debes redondear al número entero más cercano.</mark><br/>Ejemplo:<br/>A. Si min = 0 y max = 1, el promedio es 0,5; al redondear hacia arriba, el resultado es 1.<br/>D. Si min = 5 y max = 10, el promedio es 7,5; al redondear hacia arriba, el resultado es 8.</p><p>(4) Los ingresos siempre se proporcionan en el campo <code>skad_revenue</code>. Si utilizas SKAN 4 o el <a href="./skan-conversion-studio" target="_blank">modo personalizado</a>, el rango asociado con el evento para calcular skad_revenue se describe mediante min_revenue y max_revenue.</p><p>(5)</p><ul><li>En conversión personalizada: AppsFlyer calcula el tiempo de instalación como el tiempo de llegada del postback menos 36 horas menos el promedio de (min_time_post_install + max_time_post_install). Sin embargo, si CV=0, el promedio (min_time_post_install + max_time_post_install) se considera 0. </li><li>En la conversión Decode: El min_time_post_install es una hora menos que el max_time_post_install, que es igual a hours_from_install definido en tu asignación de conversión Decode. </li></ul></td><td> </td></tr></tbody></table>

</Accordion>

## Información adicional

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Acceso a la red publicitaria | Las redes publicitarias reciben postbacks |
| Acceso a la agencia | No disponible |
| Transparencia de agencia | N/D |
| Zona horaria | UTC |
| Truemoney | USD (Dólar estadounidense) |
| Datos orgánicos | Basado en datos de eventos del SDK. Por ejemplo, las métricas de instalación orgánica se calculan de la siguiente manera: Datos de todas las instalaciones reportadas por el SDK menos las instalaciones no orgánicas reportadas por SKAdNetworks. |
| Datos no orgánicos | Basado en postbacks de SKAN |
| Actualización de los datos | Diariamente. La sincronización de SKAN significa que iOS informa sobre una instalación 24-48 horas después del cierre de la ventana. |
| Datos históricos | Limitado a la ventana de disponibilidad de Data Locker. |
| Acceso de usuario a la cuenta | Disponible. Según los permisos de la cuenta. |

</Accordion>

> 📄 **Consulte también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#reporting-options">Reportes de SKAN disponibles (guía de soluciones SKAN)</Anchor>

<div data-zendesk-anchors="skan-raw-data-reports=reportes-de-raw-data-de-skan 01H8XHATZB2G6YZ9AJNPRZS59Y=reportes-de-raw-data-de-skan skan-raw-data-report-format-and-content=formato-y-contenido-de-los-reportes-de-raw-data-de-skan 01H8XHATZCJQZTZF0Y5P18XMEA=formato-y-contenido-de-los-reportes-de-raw-data-de-skan 01H8XHATZCR5BC2P5TSQTMDY5Q=raw-data-report-types 01H8XHATZC0MST5ASGWDGGK2R8=raw-data-field-format-types field-formats=formatos-de-campo 01H8XHATZCZMNGK72DDE5HS6E9=formatos-de-campo 01H8XHATZC24DH4AYB2C523JDH=fields-available-in-postback-and-postback-copy-reports 01H8XHATZCNXVG0E3MZ9H68AA1=fields-available-in-decoded-event-reports additional-information=informaci%C3%B3n-adicional 01H8XHATZD9D7JBHTFZ095EBD5=informaci%C3%B3n-adicional 01H8XHATZDMV0VN4BDTECGF91K=traits-and-limitations h_01HDNYQBVZP0A6SQASGDRFVFGP=consulte-tambi%C3%A9n" />

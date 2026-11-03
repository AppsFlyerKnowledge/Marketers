---
title: Resumen de los reportes de raw data
metadata:
  keywords:
    - LTV
    - raw data
    - uninstalls
    - AFI
    - Advertisers
    - Agencies
    - Premium Feature
    - Gray
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2016-03-21T08:32:06Z'
  edited_at: '2026-08-17T11:45:55Z'
  id: 209680773
  locale: es
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/es/articles/209680773
---
> **En resumen:** Los datos a nivel de fila (también denominados raw data) describen eventos relacionados con los usuarios, como instalaciones, eventos in-app, visitas a sitios web, instalaciones bloqueadas por Protect360, ingresos publicitarios generados y postbacks asociados al usuario enviados a partners. Los reportes de raw data se pueden obtener mediante descarga, API y Data Locker.

## Reportes de raw data: herramientas y reportes

Los reportes de raw data te permiten analizar el comportamiento y los viajes de los usuarios, conciliar cuentas de ad networks y enriquecer tus sistemas CRM y BI. Usar raw data incrementa tu capacidad para analizar, optimizar y mejorar el rendimiento de la aplicación.

Los reportes están disponibles usando herramientas de generación de reportes. Las herramientas cuentan con diferentes características que se adaptan a distintos casos de uso. Por ejemplo, para conciliar una cuenta de ad network, descarga el reporte necesario a través de la página Exportar datos. Para obtener datos de rendimiento del usuario que se van a cargar en tus sistemas de BI, obtén los datos programáticamente usando Data Locker o Pull API.

> 👍 **Consejo**
>
> ¿Quieres entender más sobre tu raw data? Consulta este curso breve e informativo en el <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7806/play/18629/viewing-and-understanding-your-raw-data">Portal de Aprendizaje de AppsFlyer</Anchor>.

<div id="reporting-tools-characteristics-and-features" />

<Accordion title="Herramientas de reportes: características y funciones">

Los reportes están accesibles mediante las herramientas de reportes mencionadas en esta sección.

Consideraciones:

* El rango de fechas del reporte se refiere a la fecha de la actividad (real) en la que ocurrió el evento. Esto es diferente de los reportes agregados donde el rango de fechas está <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">basado en LTV</Anchor>.
* Descripciones de campos: consulta el <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">diccionario de campos de datos</Anchor>.

#### Herramientas de reportes

<table><thead><tr><th>Herramienta</th><th>Descripción</th><th>Aplicaciones múltiples/única (1)</th><th>Capacidad de actualización de datos (2)</th><th>Incorporar en scripts</th><th>Zona horaria</th><th>Truemoney</th></tr></thead><tbody><tr><td><a href="./raw-data-export-page" target="_blank">Página de exportación de raw data</a></td><td><ul><li>Descarga el reporte mediante la interfaz de usuario</li><li>Formato: Archivo CSV</li></ul></td><td>Único</td><td>Revisado continuamente</td><td><span>.</span></td><td>Específico para la aplicación</td><td>Específico para la aplicación</td></tr><tr><td><a href="./pull-api-raw-data" target="_blank">Pull API\*</a></td><td><ul><li>Descargar reporte usando llamadas API.</li><li>Formato: Archivos CSV</li></ul></td><td>Único</td><td>Revisado continuamente</td><td><span>✓</span></td><td><ul><li>Seleccionable</li><li>Predeterminado: UTC</li></ul></td><td><ul><li>Seleccionable</li><li>Predeterminado: USD</li></ul></td></tr><tr><td> <a href="./data-locker-for-marketers" target="_blank">Data Locker</a> <span><strong>P</strong></span> </td><td><ul><li>Datos transmitidos a un <a href="./data-locker-cloud-service-setup" target="_blank">almacenamiento en la nube</a> </li><li>Sin límites de volumen</li><li>Ventana de disponibilidad de datos: 14 días.</li><li>Formato: CSV o parquet</li></ul></td><td>Múltiples</td><td>Se actualiza continuamente con un retraso de varias horas</td><td><span>✓</span></td><td>UTC</td><td>USD (Dólar estadounidense) </td></tr><tr><td> <a href="./push-api-streaming-raw-data" target="_blank">Push API<span></span></a> <span><strong>P</strong></span> </td><td><ul><li>Los datos del viaje del usuario (instalaciones, in-app, retargeting, SKAN) son enviados a sus servidores en tiempo real.</li><li>Formato: JSON o parámetros de consulta</li></ul></td><td>Puede usar el mismo punto de conexión</td><td>Minutos después de que el evento se registre en AppsFlyer</td><td><span>✓</span></td><td>UTC + específico de la app</td><td>USD + específico de la app</td></tr><tr><td> <a href="./conversion-data-payloads-and-scenarios" target="_blank">Datos de conversión del SDK</a> (3)</td><td><ul><li>Obtén datos de conversión de atribución dentro de la aplicación.</li><li>Formato: JSON</li></ul></td><td>N/D</td><td>Los datos de conversión del SDK recuperan los datos de atribución del Usuario en hasta 8 segundos desde el primer lanzamiento de la App (hasta 5 segundos en los Servidores de AppsFlyer, más el retraso de red de extremo a extremo).</td><td><span>✓</span></td><td>UTC</td><td>N/D</td></tr><tr><td colspan="7"> <strong>Notas y abreviaturas:</strong><br/>(1) Soporte para múltiples aplicaciones<br/>(2) La frescura real de los datos depende del reporte en sí, ya que algunos son diarios.<br/>(3) Los datos de conversión del SDK recuperan los datos de atribución del Usuario en hasta 8 segundos desde el primer lanzamiento de la App (hasta 5 segundos en los Servidores de AppsFlyer, más el retraso de red de extremo a extremo) y, por lo tanto, es el método menos preciso.<br/><span><strong>(P)</strong> </span><span>Función premium</span><br/><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Se aplican cuotas para la generación de reportes</a> </td></tr></tbody></table>

#### Limitaciones de la herramienta

<table><thead><tr><th>Limitación </th><th>Pull API (\*)</th><th>API Push</th><th>Casillero de datos</th><th>SDK<br/>Datos de conversión</th></tr></thead><tbody><tr><td>Límite de datos</td><td>1 millón de filas por llamada</td><td>N/D</td><td>N/D</td><td>N/D</td></tr><tr><td>Opciones de selección de datos</td><td>Selecciona tipos de datos. Opciones limitadas de selección de campos</td><td>Selecciona tipos de datos, campos y análisis in-app</td><td>Selecciona tipos de datos, campos y análisis in-app</td><td>No</td></tr><tr><td>Ventana de disponibilidad de datos</td><td>90 días</td><td>N/D</td><td>14 días </td><td>Para siempre (disponible en el SDK)</td></tr><tr><td colspan="5"><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Se aplican cuotas para la generación de reportes</a></td></tr></tbody></table>

#### Consideraciones para la integración

| Consideración | API Pull | API Push | Casillero de datos | SDK  <br />Datos de conversión |
| --- | --- | --- | --- | --- |
| Desarrollo del lado del servidor | Opcional | Obligatorio | Opcional | Opcional |
| Requiere procesamiento de datos | Opcional | Obligatorio | Opcional | Opcional |
| Riesgo de pérdida de datos | No | Sí, si los servidores de recepción están fuera de línea | No | Pequeño, si hay retrasos en la respuesta de la ad network |
| Costos de procesamiento cliente-servidor | Ninguno | Altos | Bajos | Ninguno (a menos que se envíen los datos a los servidores) |
| Mantenimiento cliente-servidor | Ninguno | Altos | Bajos | Ninguno (a menos que se envíen los datos a los servidores) |
| Formato de datos | Archivo CSV | JSON o parámetros de consulta | CSV o parquet | JSON |

</Accordion>

Los registros de raw data que ocurren en un contexto determinado se agrupan en reportes. Por ejemplo, instalaciones no orgánicas, eventos orgánicos in-app. Para facilitar la explicación, los reportes se agrupan de la siguiente manera:

* **Viajes del usuario:** Utilizalo para seguir el viaje y la interacción de un usuario con la aplicación.  
  Por ejemplo: clic > instalación > evento in-app > desinstalación.
* **Característica:** Están relacionadas con una función de AppsFlyer específica, pero no forman parte del viaje principal del usuario. Por ejemplo, postbacks a ad networks, reportes de fraude y Reglas de Validación, y reportes de ingresos por publicidad por usuario.

<div id="report-fields" />

<Accordion title="Campos del reporte">

El diccionario de campos de <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">raw data</Anchor> contiene campos relevantes para los reportes del viaje del usuario y algunos campos de reportes de funciones. Los principios son los siguientes:

* **Viajes del usuario:**
  * Contar con un conjunto común de campos.
  * La inclusión de campos depende del contexto del viaje. Por ejemplo, los reportes no orgánicos incluyen la fuente de medios atribuida a traer al usuario. Los campos de atribución en los reportes orgánicos no se completan porque no hay fuente de medios.
* **Función**: Contar con un conjunto único de campos o incluir campos del viaje del usuario junto con campos adicionales relevantes para la función. Por ejemplo, los reportes de SKAdNetwork tienen una lista única de campos, mientras que los reportes de postback contienen los campos del viaje del usuario y campos adicionales relacionados con el envío de postbacks a los partners.

**¡Consejo!** ¡**Consejo**! La mejor manera de familiarizarse con los reportes es revisarlos. Puedes descargar tus reportes desde la página <Anchor target="_blank" href="/marketers/es/docs/raw-data-export-page">Exportación de datos</Anchor>.

Para facilitar la comprensión, los campos del viaje del usuario se agrupan según el contexto.

#### Grupos de campos de raw data del viaje del usuario

| Grupo de campos | Relevante para usuarios orgánicos | Campos de ejemplo |
| --- | --- | --- |
| Aplicación | Sí | ID de aplicación, nombre de la aplicación, versión de la aplicación, versión del SDK, ATT |
| Atribución | No, excepto la hora de instalación. | Hora de instalación, hora del toque atribuido, fuente de medios, campaña, adset, anuncio, partner, tipo de conversión de retargeting |
| Atribución de colaboradores | No | Partner colaborador, tipo de coincidencia |
| Información del dispositivo | Sí | ID de publicidad, GAID, OAID, tipo de dispositivo, ID de usuario del cliente |
| Ubicación del dispositivo | Sí | Dirección IP, ciudad, país |
| Evento | Sí | Se completa en los reportes de in-app events:<br /><br />Nombre del evento, valor del evento, ingresos del evento |

</Accordion>

## Reportes del viaje del usuario

![Raw_data_-_User_acquisition_.png](https://files.readme.io/319da2a6a5567d6cfe4a74337279e67e0bdcdb063e62ecacde5eb4293a98a1a2-36317497158033.png)

<div id="user-journey-basics" />

<Accordion title="Conceptos básicos del viaje del usuario">

Los reportes del viaje del usuario contienen datos recopilados sobre eventos que ocurren durante toda la vida de un usuario. Los datos se dividen en reportes según:

* Fuente de usuario: orgánica o no orgánica
* Contexto del viaje:
  * Engagement con anuncios antes de la instalación de la app (visualizaciones y clics)
  * Adquisición
  * Reorientación

**Los reportes de adquisición de usuarios (UA) incluyen:**

* Las impresiones y los clics que ocurren antes de la instalación por parte de cualquier usuario *potencial* que interactúe con un anuncio.
* Evento de instalación.
* Eventos posteriores in-app realizados por el usuario.

**Los reportes de retargeting incluyen:**

* Las impresiones y los clics que se producen al redireccionar al usuario.
* Eventos de conversión: Ya sea reengagement o reatribución.
* Eventos posteriores in-app realizados durante el reengagement. Considere:
  * Los datos de retargeting siempre son no orgánicos.
  * Los eventos de retargeting in-app se incluyen tanto en los reportes de UA como en los de retargeting de eventos in-app. Consulta la metodología de <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">doble atribución de retargeting</Anchor>.

    ![Raw_data_-_Retargeting.png](https://files.readme.io/717f6e43ca3b224ead9e3e1c5f9b277d2f21dbc1fe3b4c217ebf4bdbc539bab7-36317470735249.png)

Para seguir el viaje de un usuario, combina los reportes relacionados con la parte que te interesa, por ejemplo, instalaciones y eventos en la app. Luego, ordena el reporte usando el ID de AppsFlyer, la hora del evento y el tipo de reporte. El resultado es el conjunto de eventos de un usuario a lo largo del tiempo, es decir, su recorrido.

</Accordion>

<div id="user-journey-report-availability" />

<Accordion title="Disponibilidad de reportes del viaje del usuario">

* La disponibilidad de los reportes depende de tu plan de suscripción.
* Los reportes pueden incluir usuarios orgánicos, no orgánicos o ambos, según se indique.
* Las políticas de retención se aplican a los reportes de raw data históricos según la herramienta de reportes y el origen de los datos. En general, los datos están disponibles para los últimos 90 días.   
  [Práctica recomendada]: **¡Nota**! Las políticas de retención no se aplican a los datos agregados.

#### Reportes del viaje del usuario

<table><thead><tr><th>Categoría</th><th>Exclusivo para Data Locker</th><th>Tema del reporte</th><th>Orgánico</th><th>No orgánico</th></tr></thead><tbody><tr><td>Adquisición de usuarios</td><td><span>✓</span></td><td>Clics</td><td colspan="2">N/D</td></tr><tr><td>Reorientación</td><td><span>✓</span></td><td>Clics de campañas de retargeting </td><td colspan="2">El retargeting es siempre no orgánico</td></tr><tr><td>Adquisición de usuarios</td><td><span>✓</span></td><td>Impresiones</td><td colspan="2">N/D</td></tr><tr><td>Reorientación</td><td><span>✓</span></td><td>Impresiones de campañas de retargeting</td><td colspan="2">El retargeting es siempre no orgánico</td></tr><tr><td>Adquisición de usuarios</td><td>-</td><td>Instalaciones </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Adquisición de usuarios</td><td>-</td><td>Eventos dentro de la app </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Adquisición de usuarios</td><td>-</td><td>Ingresos por publicidad atribuida</td><td>-</td><td><span>✓</span></td></tr><tr><td>Adquisición de usuarios</td><td>-</td><td>Ingresos por publicidad orgánica</td><td><span>✓</span></td><td>-</td></tr><tr><td>Reorientación</td><td>-</td><td>Ingresos por publicidad de retargeting</td><td colspan="2">El retargeting es siempre no orgánico</td></tr><tr><td>Reorientación</td><td>-</td><td>Conversiones de retargeting (re-engagement y re-atribución)</td><td colspan="2">El retargeting es siempre no orgánico</td></tr><tr><td>Reorientación</td><td>-</td><td>Eventos de retargeting en la app (re-engagement y re-atribución)</td><td colspan="2">El retargeting es siempre no orgánico</td></tr><tr><td>Reorientación</td><td><span>✓</span></td><td>Sesiones de retargeting (re-engagement y re-atribución)</td><td colspan="2">El retargeting es siempre no orgánico</td></tr><tr><td>Adquisición de usuarios</td><td><span>✓</span></td><td>Sesiones</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Adquisición de usuarios</td><td>-</td><td>Desinstalaciones no orgánicas </td><td>-</td><td><span>✓</span></td></tr><tr><td>Adquisición de usuarios</td><td>-</td><td>Desinstalaciones orgánicas</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adquisición de usuarios</td><td><span>✓</span></td><td>Interacciones en múltiples plataformas</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div id="user-journey-report-descriptions" />

<Accordion title="Descripciones de reportes del viaje del usuario">

#### Clics e impresiones

| Reporte | Características |
| --- | --- |
| Contexto | Un usuario interactúa con una campaña y hace clic o visualiza un anuncio. |
| Características | Los reportes contienen un registro del enlace de atribución y de los encabezados HTTP presentes cuando un usuario hace clic en un anuncio o lo <Anchor target="_blank" href="/marketers/es/docs/measure-view-through-engagements#set-impression-links">visualiza</Anchor>. |
| Caso de uso | <ul><li>Optimiza las campañas que no conducen a la apertura de una aplicación (instalación, reatribución, reengagement).</li><li>Vuelve a involucrar a estos usuarios usando diferentes campañas.</li></ul> |
| Ejemplo de reporte | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1036692270&single=true&output=csv">Clics</Anchor> |
| Observaciones | Datos de SRN no disponibles. |
| Usuarios restringidos | En algunos casos, debido a las reglas de privacidad, los datos de impresiones y clics están restringidos (no disponen de identificadores de usuario) o no están disponibles en absoluto. La disponibilidad depende de la fuente del medio y de la plataforma. |

#### Instalaciones y conversiones de retargeting

<table><thead><tr><th rowspan="2">Nombre del reporte </th><th rowspan="2"><p>Adquisición de usuarios: Instalaciones</p></th><th rowspan="2">Retargeting: Conversiones</th></tr></thead><tbody><tr><td>Contexto</td><td><p>Cuando un usuario abre una aplicación por primera vez.</p></td><td><p>Después de que un usuario interactúa con un anuncio de retargeting y luego abre la aplicación. Una conversión de retargeting es una nueva interacción o reengagement.</p> Consulta la <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">Guía de atribución de retargeting.</a>  </td></tr><tr><td>Casos de uso</td><td><ul><li>Genera reportes agregados utilizando campos que no están disponibles a través de las herramientas de análisis de AppsFlyer.</li><li>Combínalo con otros reportes para un análisis avanzado en secciones cruzadas.</li><li>Analizar el rendimiento entre diferentes dimensiones como ciudades, áreas metropolitanas, etc. </li><li>Segmentar a los usuarios según el país, ciudad e idioma para fines de orientación.</li><li>Obtener los ID de los dispositivos de los usuarios para objetivos de redireccionamiento.</li></ul></td><td>Similar a las instalaciones.</td></tr><tr><td>Orgánico vs. no orgánico</td><td><ul><li> <strong>No orgánico:</strong> Los grupos de campos de atribución y de contribuciones se llenan</li><li> <strong>Orgánico:</strong> El campo de fuente de medios está en blanco, nulo o es orgánico. Considérelo al cargar datos en sus sistemas. </li></ul></td><td>No aplicable</td></tr><tr><td>Ejemplo de reporte</td><td><a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR2yvNGmZp8ataHBj89CFq856PmDixnyjKK75O8fQcS9TjT8J2jBAnJoTn3350NV-7pCSlaT0oh8ebs/pub?output=csv" target="_blank">Instalaciones</a></td><td>El reporte de conversiones de retargeting tiene la misma estructura que el reporte de instalaciones. Algunos campos se completan en el contexto del retargeting. Consulta <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">raw data de retargeting</a>. </td></tr></tbody></table>

#### Eventos dentro de la app

<Table>
  <thead>
    <tr>
      <th>
        Reporte
      </th>
      <th>
        Características
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-context"></span>
        Contexto del reporte
      </td>
      <td>
        Lista cronológica de acciones realizadas por los usuarios después de la atribución (instalación, reatribución o reengagement)
      </td>
    </tr>
    <tr>
      <td><span id="characteristics"></span>
        Características
      </td>
      <td>
        * La estructura y campos del reporte son similares a los reportes de instalación.
        * Campos dedicados describen el evento. Estos datos incluyen el nombre, valor, ingresos y momento del evento.
      </td>
    </tr>
    <tr>
      <td><span id="use-case"></span>
        Caso de uso
      </td>
      <td>
        Utiliza el reporte para:

        * Obtener información al analizar el viaje del usuario durante toda su interacción.
        * Combina los raw data de instalaciones y eventos in-app para seguir el viaje completo del usuario.
      </td>
    </tr>
    <tr>
      <td><span id="event-values"></span>
        Valores de los eventos
      </td>
      <td>
        **Campo de valor del evento**

        El campo de valor del evento contiene todos los datos del evento en formato JSON. Puedes cargar esto en tu sistema BI para un análisis más detallado.

        **¡Consejo!** ¡Consejo! **Puedes usar <Anchor target="_blank" href="https://docs.microsoft.com/en-us/power-query/parse-json-xml">Power Query en Microsoft Excel</Anchor> para analizar los parámetros de los eventos a partir de las cadenas de texto JSON.**

        ```json
        {"af_level":"10","af_user_journey":"3387","arena":"7","char_type":"paladin"}
        ```

        **Reporte de ingresos**

        Los datos de ingresos y ROI en AppsFlyer se derivan del af\_revenue enviado en eventos.

        Cuando se envía el parámetro af\_revenue en un evento dentro de la aplicación, AppsFlyer lo utiliza para completar el campo de ingresos del evento. AppsFlyer usa este campo para actualizar el panel de control y los reportes agregados.

        ¡Atención! ¡Nota! Usa solo el parámetro af\_revenue en eventos que describan **los ingresos reales generados.** Para otros eventos relacionados con ingresos, pero que no son definitivos, como add\_to\_cart, utiliza otros parámetros como af\_price.
      </td>
    </tr>
    <tr>
      <td><span id="example-report"></span>
        Ejemplo de reporte
      </td>
      <td>
        <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQhOF-g3HeqZt3rXx7WZVQnB54p7ALW_IEpnJ9xtAkrcb9XzZwweiNCZzEmuX7q0i1g6yYMxYtuuX1c/pub?output=csv">Eventos in-app</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="remarks"></span>
        Observaciones
      </td>
      <td>
        * Los eventos in-app de retargeting se <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">registran por duplicado</Anchor> tanto en los reportes de raw data de UA como en los de eventos in-app de retargeting.
        * Los eventos in-app no incluyen el evento de inicio (af\_app\_opened). Esta información está disponible en el reporte de raw data de sesiones.
        * Geolocalización: Se obtiene a partir de la dirección IP del usuario en el momento en que se realiza el evento.
      </td>
    </tr>
  </tbody>
</Table>

#### Sesiones

| Reporte | Características |
| --- | --- |
| Contexto | Cuando el usuario abre la aplicación, se envía un evento de sesión a AppsFlyer. El evento se registra si se supera el umbral del tiempo <Anchor target="_blank" href="/marketers/es/docs/measure-sessions">mínimo entre sesiones</Anchor>. |
| Características | La estructura del reporte es la misma que la de los reportes de eventos dentro de la aplicación. Las sesiones (eventos de sesión) se enumeran en un reporte separado debido al gran número existente. |
| Caso de uso | Entiende el engagement del usuario con la aplicación. |
| Ejemplo de reporte | El reporte de sesiones es similar al de eventos in-app. Nota: En los raw datao, las sesiones incluyen el nombre del evento *launch*. |

#### Desinstalaciones

| Reporte | Características |
| --- | --- |
| Contexto | Registro de usuarios que desinstalan la aplicación. |
| Características | <ul><li>Este reporte se actualiza diariamente y no continuamente, como ocurre con otros reportes del viaje del usuario.</li><li>En el reporte, el tiempo del evento representa el momento en que AppsFlyer determina que la app fue desinstalada, y no el momento exacto de la desinstalación. Consulta la Medición de desinstalaciones.</li></ul> |
| Campos disponibles | <ul><li>Si el usuario procede de una fuente de medios no orgánica, los campos de fuente de medios se completan.</li><li>Considera que el evento de desinstalación lo generan los servidores de AppsFlyer después de determinar que el usuario desinstaló. Por consiguiente, muchos campos no están completados.</li><li>Los identificadores de usuario disponibles son los registrados en el momento de la instalación. El CUID nunca está disponible.</li><li>Los campos geográficos se completan con la ubicación del usuario al interactuar con la fuente de medios (clic o impresión). Si no se dispone de la ubicación del engagement, se utiliza la ubicación asociada al evento de instalación.</li></ul> |
| Ejemplo de reporte | ¡Nota de <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1558773473&single=true&output=csv">desinstalaciones</Anchor>! En el ejemplo, por claridad, la fila 2 indica qué campos se completan si hay datos relevantes disponibles. En el ejemplo, por claridad, la fila 2 indica qué campos se completan si hay datos relevantes disponibles. |
| Casos de uso | <ul><li>Analizar el evento de desinstalación, el dispositivo y las características del usuario.</li><li>Construir una audiencia de eventos de desinstalación para el retargeting.</li></ul> |

</Accordion>

<div id="user-journey-report-availability-per-tool" />

<Accordion title="Disponibilidad del reporte de viaje del usuario por herramienta">

#### Reporte de engagement con anuncios por herramienta

<table><thead><tr><th>Reporte</th><th>Exportar datos</th><th>API Pull</th><th>Casillero de datos</th><th>API Push</th><th>SDK<br/>Datos de conversión</th></tr></thead><tbody><tr><td>Impresiones (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Clics (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td colspan="6">(1) Los datos de clics e impresiones están disponibles gracias a fuentes que no son SRN. Las SRN no ponen estos datos a disposición.</td></tr></tbody></table>

#### Reportes de adquisición de usuarios por herramienta

| Reporte | Exportar datos | API Pull | Casillero de datos | API Push | Datos de conversión del SDK |
| --- | --- | --- | --- | --- | --- |
| Instalaciones | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sesiones | - | - | ✓ | - | - |
| Eventos in-app | ✓ | ✓ | ✓ | ✓ | - |
| Desinstalaciones | ✓ | ✓ | ✓ | - | - |

#### Reportes de raw data de retargeting por herramienta

<table><thead><tr><th>Reporte</th><th>Exportar datos</th><th>API Pull</th><th>Casillero de datos</th><th>API Push</th><th>SDK<br/>Datos de conversión</th></tr></thead><tbody><tr><td>Clics (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Conversiones (reatribuciones + reengagements)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Impresiones (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Sesiones</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Eventos in-app</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) Los datos de clics e impresiones están disponibles gracias a fuentes que no son SRN. Los SRNs no ponen estos datos a disposición.</td></tr></tbody></table>

</Accordion>

<div id="faq" />

<Accordion title="Preguntas frecuentes">

| Detalles |
| --- |
| **¿Cuál es la diferencia entre las marcas de tiempo?**<br /><br />Las marcas de tiempo son comunes a todos los reportes. Esto permite combinar diferentes reportes.<br /><br />Las siguientes marcas de tiempo son relevantes:<ul><li>**Hora de contacto atribuido**: La hora en que el usuario interactuó con un anuncio.</li><li>**Hora de instalación** : La hora en que se inicia la aplicación por primera vez.</li><li>**Hora del evento**: La hora en que ocurre el evento.</li></ul>Considera:<ul><li>En los reportes de instalación, las horas de instalación y de eventos coinciden.</li><li>En los reportes de eventos in-app, las horas de instalación y de eventos son distintas. Esta diferencia puede mostrar el tiempo que pasa entre el inicio de la aplicación y el engagement del usuario con ella.</li></ul> |
| **¿Cuál es el propósito del campo colaborador?**<br /><br />El campo colaborador lista las fuentes de medios del colaborador. A veces se les dice <Anchor target="_blank" href="/marketers/es/docs/measure-assisted-installs#reportes-de-instalaciones-asistidas">Instalaciones asistidas</Anchor>. En Protect360, también se utiliza para la <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#corrección-de-atribución-de-instalaciones-secuestradas">corrección de la atribución de instalaciones secuestradas</Anchor>. |
| **¿Qué es el campo de palabras clave y por qué no está disponible en todas las instalaciones no orgánicas?**<br /><br />Las instalaciones atribuidas a Google Ads o Apple Ads pueden contener las palabras clave o el ID de la palabra clave asociados al anuncio que generó la instalación. |

</Accordion>

<div id="install-report-tips" />

<Accordion title="Consejos para los reportes de instalación">

**Entendiendo el viaje del usuario**

El viaje del usuario es una serie de pasos que este realiza antes de alcanzar un objetivo, como comprar un producto o reservar un vuelo. El propósito de analizar un viaje del usuario es observar qué hace el usuario en la aplicación, cuán activo es y qué valor aporta en un periodo determinado.

Puedes identificar y destacar los viajes de usuario con la ayuda del ID de AppsFlyer. El ID se genera para cada instalación de la aplicación por dispositivo. El ID permanece sin cambios durante todo el ciclo de vida del usuario (desde la instalación hasta la desinstalación). El ID persiste si el usuario restablece el ID de su dispositivo.

Dado que los reportes de eventos de instalación e in-app tienen la misma estructura, se pueden fusionar en un único reporte. En el reporte combinado, puedes agregar y filtrar por ID de AppsFlyer e ID de usuario del cliente (si está disponible) para analizar las rutas de los usuarios.

> 📄 **Usuario involucrado—fuerte**
>
> * Un usuario instaló la aplicación el 20 de agosto a las 09:31.
> * El reporte fusionado muestra que realizó compras el 20 de agosto a las 10:31, el 22 de agosto a las 15:22 y el 25 de agosto a las 16:47.
> * De esto concluimos que el usuario está involucrado. Hizo una compra una hora después de abrir la aplicación y continuó comprando los días siguientes a la instalación.
>
> #### Usuario involucrado—débil
>
> * Un usuario instaló la aplicación el 30 de julio. El reporte fusionado muestra que añadió un artículo a su carrito el 15 de agosto, pero no hubo eventos de compra posteriores.
> * Puedes suponer que el usuario está indeciso para realizar una compra y decidir volver a dirigirlo con el artículo que añadió al carrito.
>
> #### Análisis del viaje del usuario para la optimización de campañas
>
> * El responsable por la adquisición de usuarios (UA) de una app de viajes descarga los reportes de instalaciones y eventos in-app y los combina.
> * Luego, para ver los viajes de los usuarios en la app, filtra o agrupa los datos por ID de AppsFlyer.
> * Observa que un usuario en particular, identificado por su ID de AppsFlyer, descargó la app hace 12 meses y reservó un vuelo varios días después.
> * Posteriormente, el usuario visualizó algunas ofertas de vuelos pero no hizo ninguna reserva. Al profundizar más, el gerente de UA descubre más usuarios con el mismo patrón y decide investigar aún más.
> * Descubren que la mayoría de estos usuarios provienen del **Anuncio A** de la **Campaña B** ejecutada en la **Fuente de medios C.** Se descubre que este anuncio y campaña estaban dirigidos a usuarios interesados en viajar a un destino específico.
> * Al analizar el viaje del usuario, el gestor de UA podría deducir que la campaña estaba demasiado centrada y que los usuarios no estaban suficientemente involucrados con la aplicación.

</Accordion>

## Reportes de funciones

Reportes sobre funciones adicionales disponibles en la plataforma

* <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">Ingresos por publicidad</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview#reportes-de-raw-data">Incrementalidad</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">SKAdNetwork</Anchor>

<div id="postbacks" />

<Accordion title="Devoluciones de mensajes">

Utiliza los reportes de postback para revisar copias de los datos enviados a una ad network. Por ejemplo, utilízalo para investigar discrepancias. Estos reportes son únicamente informativos y no son obligatorios para la integración con ad networks.

* El reporte incluye:
  * Copias de postbacks enviados a la fuente de medios atribuida.
  * <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">Campos de datos en crudo</Anchor> y campos adicionales tal como se detalla en esta sección.
* El reporte no incluye:
  * Instalaciones de SRN.
  * Eventos in-app relacionados con Meta Ads, X y Apple Search Ads.
  * Postbacks de partners no atribuidos. Consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">eventos atribuidos a cualquier partner o de origen orgánico</Anchor>.
  * Usuarios orgánicos. Lee <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">sobre instalaciones orgánicas.</Anchor>
* A partir de marzo de 2021, los campos se rellenan conforme a la configuración de Privacidad Avanzada de una red. Es decir, si la Privacidad Avanzada está activa, algunos campos, como los identificadores de usuario, no están incluidos. Consulta la <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification">especificación de postbacks de privacidad avanzada para ad networks.</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5">Obtén reportes de postback a través de la PULL API</Anchor>

#### Reportes de postback (disponibles a través de la página de Exportación de Datos y la API Pull)

| Tema del reporte | Eventos enviados a la fuente de medios atribuida |
| --- | --- |
| Instalaciones | Instalaciones no orgánicas (UA) |
| Eventos in-app | Eventos no orgánicos in-app |
| Postbacks de conversión de retargeting | Retargeting (reengagement y reatribución) |
| Eventos de retargeting en la aplicación | Eventos de retargeting en la aplicación |

#### Campos adicionales en los reportes de postback

| Campo | Observaciones |
| --- | --- |
| URL de postback | Es posible que algunos valores, como los ingresos, no aparezcan en el campo adecuado, pero aun así podrás consultar estos datos en la URL del **Postback**. |
| Método de postback |  |
| Código de respuesta HTTP del postback | 200: Confirma que la ad network ha recibido el postback |
| Mensaje de error de postback |  |

</Accordion>

<div id="protect360-fraud-and-validation-rules" />

<Accordion title="Normativas de validación y protección contra fraudes de Protect360">

* Consulta los reportes de raw data de <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">Protect360</Anchor> y los de las <Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud#outcomes">reglas de validación</Anchor> raw data
* Las ad networks y las agencias necesitan el <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#access-protect360-dashboard-raw-data">permiso</Anchor> del anunciante para acceder a los reportes de Protect360 y reglas de validación.

**Para conceder a un partner integrado permiso para acceder a Protect360:**

1. Accede a **Colaborar** > **Integraciones activas**.
2. Selecciona el partner integrado.
3. En la pestaña **Permisos**, activa **Acceder a tu dashboard de Protect360 y a los raw data a través de la API**.
4. Para otorgar acceso al dashboard de eventos in-app (CPA), activa **Acceder a los datos agregados de in-app**.

</Accordion>

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview">Reportes agregados y análisis</Anchor>

<div data-zendesk-anchors="raw-data-reporting%E2%80%94tools-and-reports=reportes-de-raw-data-herramientas-y-reportes h_01HE7SRDXQ9TR0CRB2JC9XCQE2=reportes-de-raw-data-herramientas-y-reportes h_01HE7SRDXQQJFMV9EJKPY34D00=consejo reporting-tools%E2%80%94characteristics-and-features=reporting-tools-characteristics-and-features h_01HE7SRDXQFJGMY05K1SV4TF63=reporting-tools-characteristics-and-features reporting-tools=herramientas-de-reportes h_01HE7SRDXQ647XRQ8QVMPGH43B=herramientas-de-reportes tool-limitations=limitaciones-de-la-herramienta h_01HE7SRDXQWQAKR0G6CNKC5AMT=limitaciones-de-la-herramienta integration-considerations=consideraciones-para-la-integraci%C3%B3n h_01HE7SRDXQN3HSMGAPBAX9S3MB=consideraciones-para-la-integraci%C3%B3n h_01HE7SRDXQRPD8MHC8M5916HTQ=report-fields user-journey-raw-data-field-groups=grupos-de-campos-de-raw-data-del-viaje-del-usuario h_01HE7SRDXQMGQEG1QWGWEESQER=grupos-de-campos-de-raw-data-del-viaje-del-usuario user-journey-reports=reportes-del-viaje-del-usuario h_01HE7SRDXQZ50WMKCMYHZM7D92=reportes-del-viaje-del-usuario h_01HE7SRDXQFN0P9QK8SKAZKVKP=user-journey-basics h_01HE7SRDXRS2B12Z67MYMH0QN9=user-journey-report-availability user-journey-reports::d286e1f5=reportes-del-viaje-del-usuario-1 h_01HE7SRDXR7YQGWN4FNDXMNMX8=reportes-del-viaje-del-usuario-1 h_01HE7SRDXRK6G27SDFK3CGDCRC=user-journey-report-descriptions clicks-and-impressions=clics-e-impresiones h_01HE7SRDXRC9YKZ0P9ED0218SJ=clics-e-impresiones installs-and-retargeting-conversions=instalaciones-y-conversiones-de-retargeting h_01HE7SRDXRN60XE5BSDQY28N71=instalaciones-y-conversiones-de-retargeting inapp-events=eventos-dentro-de-la-app h_01HE7SRDXR3ZT39EDNW4MVZZTX=eventos-dentro-de-la-app sessions=sesiones h_01HE7SRDXRY05XQCMZE6YPXGWQ=sesiones uninstalls=desinstalaciones h_01HE7SRDXRA7ESDD4ME51WWBPR=desinstalaciones h_01HE7SRDXRZYNFGK4CNP4VPAE0=user-journey-report-availability-per-tool ad-engagement-report-by-tool=reporte-de-engagement-con-anuncios-por-herramienta h_01HE7SRDXR171M74HMQBZJ2E8R=reporte-de-engagement-con-anuncios-por-herramienta user-acquisition-reports-by-tool=reportes-de-adquisici%C3%B3n-de-usuarios-por-herramienta h_01HE7SRDXRMGEP5QB452ZKQ8X7=reportes-de-adquisici%C3%B3n-de-usuarios-por-herramienta retargeting-raw-data-reports-by-tool=reportes-de-raw-data-de-retargeting-por-herramienta h_01HE7SRDXRXR4J3HTMYW2P233Y=reportes-de-raw-data-de-retargeting-por-herramienta h_01HE7SRDXRWW3JKNESSN2QA4DV=faq h_01HE7SRDXR61K28JGA8944D6HV=install-report-tips h_01HE7SRDXRKFR2WYGNF317CTRX=reportes-de-raw-data-de-retargeting-por-herramienta engaged-user%E2%80%94strong=usuario-involucradofuerte h_01HE7SRDXRW0CWHGQV75VF66DC=usuario-involucradofuerte engaged-user%E2%80%94weak=usuario-involucradod%C3%A9bil h_01HE7SRDXRNMDZEJQ32665T14F=usuario-involucradod%C3%A9bil analyzing-the-user-journey-for-campaign-optimization=an%C3%A1lisis-del-viaje-del-usuario-para-la-optimizaci%C3%B3n-de-campa%C3%B1as h_01HE7SRDXRRET0YN4Q8WYMENSR=an%C3%A1lisis-del-viaje-del-usuario-para-la-optimizaci%C3%B3n-de-campa%C3%B1as feature-reports=reportes-de-funciones h_01HE7SRDXSVAHKBYQK0C71K6AR=reportes-de-funciones h_01HE7SRDXSFWMVY61NBYFQ4XSM=postbacks postback-reports-available-via-the-export-data-page-and-pull-api=reportes-de-postback-disponibles-a-trav%C3%A9s-de-la-p%C3%A1gina-de-exportaci%C3%B3n-de-datos-y-la-api-pull h_01HE7SRDXS6T4M4CRQN0ZTJETR=reportes-de-postback-disponibles-a-trav%C3%A9s-de-la-p%C3%A1gina-de-exportaci%C3%B3n-de-datos-y-la-api-pull additional-fields-in-postback-reports=campos-adicionales-en-los-reportes-de-postback h_01HE7SRDXSYBDG0H2QEYBFWSRH=campos-adicionales-en-los-reportes-de-postback h_01HE7SRDXS8K4MB76WVBCBHASQ=protect360-fraud-and-validation-rules h_01HE7ST20N8ZBFNY2QXW5G44A1=consulta-tambi%C3%A9n" />

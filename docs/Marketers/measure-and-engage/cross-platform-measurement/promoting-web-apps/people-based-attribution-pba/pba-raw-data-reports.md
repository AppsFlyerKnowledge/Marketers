---
title: Reportes de raw data de PBA
metadata:
  keywords:
    - Data Locker
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-07-01T07:53:57Z'
  edited_at: '2026-08-12T12:11:27Z'
  id: 360001917778
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360001917778
---
> **De un vistazo**: Los reportes de raw data de PBA están disponibles a través de Data Locker.

<div id="pba-raw-data-reports" />

## Reportes de raw data de PBA

Utiliza reportes de raw data de PBA para analizar las trayectorias y acciones de los usuarios.

<div id="report-descriptions" />

### Descripciones de reportes

Temas del reporte de raw data de PBA

| Tema del reporte de raw data | Descripción |
| --- | --- |
| <span id="website-visits"></span>[Visitas al sitio web](#visitas-al-sitio-web-y-eventos-del-sitio-web) | <ul><li>Visitas al sitio web.</li><li>Mide la exposición y el engagement de los usuarios con las campañas de tráfico web.</li></ul> |
| <span id="website-events"></span><Anchor target="_blank" href="/marketers/es/docs/pba-website-attribution-dashboard">Eventos del sitio web</Anchor> | <ul><li>Contienen las acciones realizadas por los visitantes del sitio web, como suscribirse o comprar.</li><li>Los eventos se atribuyen a la última visita web no directa que ocurrió en los últimos 30 días.</li><li>Los parámetros de atribución asociados con el evento pueden incluir la fuente de medios, canal de medios, campaña, etc.</li><li>Utiliza estos parámetros para optimizar tus esfuerzos de marketing.</li><li>Analiza el comportamiento de los usuarios por fuente de medios.</li><li>Los valores de estos campos se determinan a través de la visita atribuida mediante las <Anchor target="_blank" href="/marketers/es/docs/pba-media-source-attribution-rules">reglas de atribución de fuentes de medios de PBA.</Anchor></li><li>La intención es asociar eventos con una visita a un sitio web específico y no con una vista de página específica.</li><li>Utiliza esta opción para averiguar qué fuentes y campañas impulsan a los usuarios y qué acciones realizan estos.</li></ul> |

<div id="raw-data-report-fields" />

## Campos de los reportes de raw data

<div id="website-visits-and-website-events" />

<Accordion title="Visitas al sitio web y eventos del sitio web">

<div id="sample-reports" />

#### Ejemplos de reportes

* Eventos del sitio web: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=1096347999&single=true&output=csv">CSV</Anchor>
* Visitas al sitio web: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=432734495&single=true&output=csv)

Los campos de raw data se completan en parte a partir de los datos que se originan en el enlace de atribución del usuario de la aplicación móvil y en el evento de instalación de la aplicación.

[Descargar lista de campos como CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmRBeUQS-xeiv069vIgnfBoJW8Wfl1ojv0rAK-pcOlAzNveG1lqvExVdhWfgCKIpJxczWksUiHjSa3/pub?gid=0&single=true&output=csv)

<div id="field-list-website-visits-and-website-events-report" />

#### Lista de campos del reporte de visitas y eventos del sitio web:

| Nombre de campo | Descripción | Formato | Ejemplo |
| --- | --- | --- | --- |
| advertising\_id | ID de publicidad (GAID) | Cadena | 7fzzz3fa-8bad-46c9-bb03-fffffffffffffffffffffffff |
| af\_web\_id | ID de cookie enviado desde el SDK web | Cadena | 68972980-58f9-4ca6-8743-c0d633364b6d |
| amazon\_aid | ID de publicidad de Amazon Fire TV | Cadena | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| android\_id | ID de dispositivo de Android | Cadena | 68999980-58f9-4ca6-8743-c0d633364b6d |
| id\_aplicación | El ID de aplicación más reciente instalado | Cadena | id123456789 |
| nombre\_aplicación | El nombre de la aplicación más reciente | Cadena | Mi aplicación |
| version\_app | La versión más reciente de la aplicación | Cadena | 6.32 |
| appsflyer\_id | ID de AppsFlyer (instalación) | Cadena | 1594825729709-5655157112349378588 |
| Se establece como TRUE o FALSE. | En las visitas web, la marca de tiempo de la visita web. En eventos web, la marca de tiempo de la visita web atribuida | aaaa-mm-dd hh:mm:ss | 17/9/2020 0:09:25 |
| tipo\_táctil\_atribuido | El tipo de punto de contacto. Actualmente, siempre está configurado como visita al sitio web. | Cadena | Visita web |
| id\_paquete | ID de paquete de PBA | Cadena | 048db9bf-97r7-4m2f-919b-607b7kk806d0 |
| campaña única | Atribuido a la visita al sitio web | Cadena | Campaña de verano |
| id\_campaña | Atribuido a la visita al sitio web | Cadena | 12343425 |
| Ingresos por eventos en USD | Resuelto utilizando la dirección IP | Cadena | Spring Valley |
| código\_de\_país | Resuelto utilizando la dirección IP | Cadena | Estados Unidos |
| id\_usuario\_cliente | Identificador de usuario del cliente (CUID) | Cadena | 5a8771ecbb986ABC |
| tipo\_de\_dispositivo | El tipo de dispositivo | Cadena | Escritorio |
| dma | Resuelto utilizando la dirección IP | Cadena | 501 |
| nombre\_del\_evento | En el reporte de visitas al sitio web: siempre visita al sitio web. En el reporte de eventos del sitio web: eventName enviado por el SDK web. | Cadena | compra |
| ingresos\_evento | Importe de ingresos en la divisa del evento | Cadena | 199.99 |
| moneda\_ingresos\_evento | Código de divisa de 3 dígitos del event\_revenue | Cadena | USD, ZAR, EUR |
| ingresos\_evento\_usd | event\_revenue convertido a USD | Cadena | 57.46 |
| fuente\_del\_evento | SDK web o servidor a servidor | Cadena | SDK web, S2S |
| event\_time | Visitas al sitio web: hora de la visita Evento del sitio web: hora del evento | aaaa-mm-dd hh:mm:ss | 17/9/2020 0:09:25 |
| tipo\_de\_evento | Lo siguiente: evento estándar, evento de conversión, visita al sitio web | Cadena | Evento de conversión |
| event\_url | URL de la página web donde ocurrió el evento (Igual a la URL original en las visitas al sitio web) | Cadena | http://www.brandpit.com/checkout |
| event\_value | Eventos del sitio web: detalles del valor de evento contenidos en un JSON. Visitas al sitio web: siempre nulas | JSON | `{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}` |
| idfa | Identificador de publicidad | Cadena | A56B9887-FEBA-458C-BEFC-C891F9DF7681 |
| idfv | Identificador de publicidad | Cadena | EBC2F523-B1E5-4484-A4C8-ADC32DC7C23D |
| imei | Identificador de dispositivo | Cadena | 3532211234 |
| hora\_de\_instalación | La hora de instalación de la aplicación más reciente | aaaa-mm-dd hh:mm:ss | 17/9/2020 0:09:25 |
| ip | Dirección IP del visitante | Cadena | 24.7.104.115 |
| Indicador de atribución AF | Reportado por agente de usuario | Cadena | English |
| media\_channel | Atribuido a la visita al sitio web | Cadena | Anuncio |
| fuente\_de\_medios | Atribuido a la visita al sitio web | Cadena | googleadwords\_int |
| media\_type | Atribuido a la visita al sitio web | Cadena | Paga |
| oaid | Identificador de publicidad | Cadena | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| original\_url | Dirección URL que redirige al usuario al sitio web en la visita al sitio web atribuida | Cadena | https://www.brandpitt.com/signin?utm_source=Googleg&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld |
| Identificador de origen | La plataforma | Cadena | macOS |
| postal\_code | Resuelto utilizando la dirección IP | Cadena | 10977 |
| query\_params | Parámetros de consulta en la URL de redireccionamiento (después de ?). Parámetros de consulta en la URL de redireccionamiento (después de ?) Ejemplo: https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes Si la URL no tiene parámetros de consulta, el valor será nulo | JSON | `{"c":"summer",af_siteid":"publisher",af_sub1":helloworld",af_keywords":"shoes","utm_source":"Google","utm_campaign":"cool","utm_term":"shoes"}` |
| referrer | Referente de documentos HTTP de la visita al sitio web atribuida | Cadena | https://www.google.com/ |
| Información del dispositivo | Resuelto utilizando la dirección IP | Cadena | Estados Unidos y Canadá |
| state | Resuelto utilizando la dirección IP | Cadena | NY |

</Accordion>

<div id="field-release-notes" />

<Accordion title="Notas de la versión de campo">

| Fecha | Reporte | Cambio |
| --- | --- | --- |
| 18-11-2020 | Eventos del sitio web<br /><br />Visitas al sitio web | Los nombres y la estructura del reporte se modifican:<ul><li>Puntos de contacto web reemplazados por **visitas al sitio web**</li><li>Eventos web reemplazados por **eventos** del sitio web</li></ul> |
| 04-10-2020 | De la web a la aplicación | Campos agregados:<ul><li>mobile\_campaign\_id</li><li>web\_campaign\_id</li></ul> |

</Accordion>

<div id="procedures" />

### Procedimientos

<div id="setting-up-pba-reports-in-data-locker" />

<Accordion title="Configuración de reportes de PBA en Data Locker">

* Los reportes de PBA se escriben diariamente en el Data Locker en la carpeta h=23 para los eventos que ocurren en un día determinado.
* Los datos no se pueden escribir de forma retroactiva.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Para habilitar los reportes de PBA, el administrador de la cuenta debe configurar Data Locker:**

1. Ve a **Integración** > **Data Locker**.
2. Selecciona todos los reportes en la sección Atribución basada en personas.
3. Haz clic en **Guardar configuración**.

Para descargar reportes, consulta cómo <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">acceder a los reportes de Data Locker</Anchor>.

**Data Locker** Los reportes de raw data de PBA están disponibles en la carpeta h=23.

Ejemplo: t=website\_events/dt=2020-11-26/h=23

</Accordion>

<div id="combining-pba-and-mobile-data" />

<Accordion title="Combinación de PBA y datos móviles">

Los datos reflejan a los usuarios que tienen más probabilidades de interactuar tanto con tu aplicación móvil como con tu sitio web.

Combina los datos de la aplicación móvil y del sitio web.

**Solución**:

* Combinar reportes utilizando el <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">ID de usuario de cliente</Anchor> (CUID)
  * Utiliza el mismo CUID tanto para móviles como para <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">web</Anchor> y combina reportes utilizando el CUID como clave.
  * Luego, combina reportes usando el campo CUID
* Identificación de usuario multiplataforma de PBA:
  * La PBA puede determinar que un usuario web y uno móvil son la misma persona.
  * De ser así, los reportes web con PBA incluyen un ID de publicidad móvil: ID de publicidad de Android, identificador de anunciante (IDFA) de iOS, OAID o ID de publicidad de Amazon.
  * A continuación, combina reportes móviles y web basados en el ID de publicidad móvil.

<div id="use-cases-for-pba-and-mobile" />

#### **Casos prácticos para PBA y dispositivos móviles**

Combina datos móviles y web para ver la actividad del usuario en todas las plataformas y dispositivos. Los datos combinados te permiten:

* Seguir la trayectoria del usuario a través de las propiedades digitales de tu marca
* Analizar el comportamiento de los usuarios en cada plataforma
* Considerar qué plataforma muestra más engagement de usuario
* Ver qué plataforma produce más conversiones
* Medir tus esfuerzos para cambiar a los usuarios del entorno web al móvil

</Accordion>

<div id="application-note-downloading-and-combining-data-locker-files" />

<Accordion title="Nota de la aplicación: descarga y combinación de archivos de Data Locker">

El raw data de PBA está disponible en Data Locker. Para un reporte determinado, los datos están contenidos en la carpeta h=23 del tipo de reporte y constan de varios archivos comprimidos.

Utiliza este procedimiento para:

* Copiar los archivos de Data Locker utilizando Cyber-Duck o cualquier otra herramienta para copiar archivos S3.
* Combinar los archivos en un único archivo CSV usando [Q.](http://harelba.github.io/q/)

**Copia de datos de PBA de Data Locker**

**Antes de comenzar**:

* <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#cyberduck">Instala y configura Cyber-Duck.</Anchor>

**Para copiar datos utilizando Cyber Duck:**

1. Abre Cyberduck.  
    Aparecerá la lista de tipos de datos disponibles.

   ![Duck_us-en.jpg](https://files.readme.io/b8e93ad9423605b3247531d276b9c2d45abd4ea044dde29ee177f4d71b738e9d-360008254377.jpg)
2. **Haz doble clic** en un tipo de reporte de PBA y elige entre web\_events, web\_to\_app o web\_touch\_points.  
   Aparecerá la lista de fechas de reportes disponibles.
3. **Haz clic con el botón derecho** en una fecha determinada.
4. Selecciona **Descargar en una ubicación específica y completa la ubicación.**   
   Los archivos se descargan.
5. Repite los pasos anteriores para copiar datos de otros tipos de reportes. Cada tipo de reporte y fecha deben almacenarse en un directorio diferente en tu equipo.

**Crear un archivo CSV combinado:**

**Antes de comenzar:**

Instala <Anchor target="_blank" href="http://harelba.github.io/q/">Q</Anchor> en tu computadora.

**Para combinar los datos en un archivo CSV usando Q**:

1. Usando la línea de comando/terminal maс, ve al directorio que contiene los datos.
2. Utiliza el comando siguiente para combinar los archivos comprimidos en un único archivo con el nombre pbadata.csv.  
   Nota: El símbolo ~ representa la ruta/carpeta de inicio donde se encuentra el comando Q en tu computadora. Es posible que debas incluir la ruta completa para invocar el comando.

   ```
   ~q "SELECT * from part*.gz" -d , -H -z -O >pbadata.csv
   ```
3. Abre el archivo usando Excel o cualquier otra herramienta

</Accordion>

<div data-zendesk-anchors="pba-raw-data-reports=reportes-de-raw-data-de-pba h_01HKW341NVTCP4FY5G4TC94MZY=reportes-de-raw-data-de-pba report-descriptions=descripciones-de-reportes h_01HKW341NVC83ZC3HCH86QBJYG=descripciones-de-reportes rawdata-report-fields=campos-de-los-reportes-de-raw-data h_01HKW341NVNYM1AGFC8GHV7VR2=campos-de-los-reportes-de-raw-data h_01EQD0FBKE0J71MA9MNETEZAMA=website-visits-and-website-events sample-reports=ejemplos-de-reportes h_01HKW341NVX51NQFAA79BD7MF3=ejemplos-de-reportes website-visits-events=lista-de-campos-del-reporte-de-visitas-y-eventos-del-sitio-web field-list-website-visits-and-website-events-report=lista-de-campos-del-reporte-de-visitas-y-eventos-del-sitio-web h_01J53BGNDSQCCFV1VQA8EV50GR=lista-de-campos-del-reporte-de-visitas-y-eventos-del-sitio-web h_01HKW341NW43C07KYAN3WCV0WY=field-release-notes procedures=procedimientos h_01HKW341NWXQ19ZB5QXZK84VMQ=procedimientos h_01HKW341NXR3MP2T99AAHNH3SG=setting-up-pba-reports-in-data-locker h_01HKW341NX2S093V1Y8YVY45VP=combining-pba-and-mobile-data use-cases-for-pba-and-mobile=casos-pr%C3%A1cticos-para-pba-y-dispositivos-m%C3%B3viles h_01HKW341NXTXX4FJ2ZZQFZ2V85=casos-pr%C3%A1cticos-para-pba-y-dispositivos-m%C3%B3viles h_01HKW341NX95YBGHZZG8KZC3KX=application-note-downloading-and-combining-data-locker-files" />

---
title: Política de identificador de usuario de Audiencias
metadata:
  keywords:
    - IDFA
    - Audiences
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-12-23T15:39:55Z'
  edited_at: '2026-08-12T12:26:18Z'
  id: 360016791118
  locale: es
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/es/articles/360016791118
---
> **Resumen:** Configure su política de identificador de usuario para ejercer control a **nivel de cuenta** sobre los datos que Audiences comparte con socios.

<div id="about" />

## Acerca de

Una vez que defina una audiencia, AppsFlyer Audiences envía identificadores de los miembros de esa audiencia a sus <Anchor target="_blank" href="/marketers/es/docs/audiences-partner-connections">socios publicitarios</Anchor> seleccionados. Esto les permite mostrar anuncios solo a estos usuarios.

Para cumplir con los requisitos de privacidad de iOS 14.5 y otras consideraciones sobre la privacidad del usuario, Audiences le permite controlar completamente qué identificadores se comparten con socios:

* a nivel de cuenta
* a nivel de conexión de socios

Este artículo explica el proceso para gestionar su política de identificador de usuario a nivel de cuenta. Para más información sobre cómo gestionar los identificadores compartidos a nivel de conexión de socios, consulte la sección <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#manage-connections">Gestionar conexiones</Anchor> de la guía de Audiencias.

<div id="user-identifiers" />

## Identificadores de usuario

Esta sección describe los identificadores que se pueden compartir con los socios.

<div id="shared-identifiers" />

<Accordion title="Configuración predeterminada de identificadores">

Por defecto, Audiences comparte los siguientes identificadores con socios:

* **iOS:** IDFA (en iOS 14.5 y posteriores, disponible solo si el usuario permite su compartición)
* Android: GAID

También puedes configurar audiencias para enviar los siguientes identificadores a los Partners que los admitan:

* Correo electrónico (encriptado)
* Número de teléfono (encriptado)
* OAID y IMEI (ambos relevantes solo para tiendas Android no Google Play)

Algunos otros identificadores adicionales pueden ser útiles para sus procesos internos (como CRM o análisis):

* CUID
* IDFV (solo relevante para iOS)

Para más información (incluidos los requisitos para usar identificadores específicos en AppsFlyer), consulte la tabla de identificadores más abajo.

</Accordion>

<div id="identifiers-table" />

<Accordion title="Tabla de identificadores">

<table><thead><tr><th>Identificador</th><th>Sistema Operativo</th><th>¿Se comparte por defecto?</th><th>Requisitos de uso/<br/>Notas<br/><br/> </th></tr></thead><tbody><tr><td>Identificador de anunciante (IDFA)</td><td>apps de iOS,</td><td>Ver nota<br/>(derecha)</td><td>Por defecto, solo se comparte para usuarios con <a href="./audiences-user-identifier-policy#ios">estado ATT: autorizado o no determinado</a> </td></tr><tr><td>GNA Company</td><td>Android</td><td>Sí</td><td>Ninguno</td></tr><tr><td>OAID</td><td>Android<br/>(no Google Play)</td><td>N/A</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">Debe configurarse</a> en el SDK de AppsFlyer</td></tr><tr><td>IMEI</td><td>Android<br/>(no Google Play)</td><td>N/A</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">Debe configurarse</a> en el SDK de AppsFlyer</td></tr><tr><td>CUID</td><td>iOS<br/>Android</td><td>N/A</td><td><ul><li>Generado por el anunciante y <a href="./customer-user-id-field-cuid" target="_blank">reportado a AppsFlyer</a> usando las API o SDK de AppsFlyer</li><li>No se comparte con socios publicitarios, pero puede ser útil para tus propósitos internos</li><li>Sujeto a los <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Términos de uso de identificadores adicionales</a> </li></ul></td></tr><tr><td>IDFV</td><td>apps de iOS,</td><td>N/A</td><td><ul><li>No se comparte con socios publicitarios, pero puede ser útil para tus propósitos internos</li><li>Sujeto a los <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Términos de uso de identificadores adicionales</a> </li></ul></td></tr><tr><td>Correo electrónico (con hash)</td><td>iOS<br/>Android</td><td>N/A</td><td rowspan="2"><ul><li> <a href="./audiences-configure-additional-identifiers-for-partner-audience-creation" target="_blank">Se debe configurar</a> a través del <span>SDK de AppsFlyer o la API S2S-mobile</span> </li><li>Debe cifrarse con el algoritmo de hash SHA256</li><li>Sujeto a los <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Términos de uso de identificadores adicionales</a> </li></ul></td></tr><tr><td>Número de teléfono (con hash)</td><td>iOS<br/>Android</td><td>N/A</td></tr></tbody></table>

</Accordion>

<div id="setting-account-level-user-identifier-policy" />

## Configuración de la política de identificador de usuario a nivel de cuenta

La política de identificador de usuario solo puede ser establecida por un usuario administrador.

**Para establecer o modificar tu política, sigue estos pasos:**

1. En AppsFlyer, desde el menú lateral, selecciona **Interactuar** > **Audiencias**.
2. Haz clic en el icono de configuración (engranaje) en la esquina superior derecha.
3. En la ventana **Política de identificador de usuario**, selecciona las configuraciones que cumplan con las políticas de privacidad de tu organización.
   * Si eliges permitir la compartición de identificadores distintos de IDFA, GAID, OAID e IMEI, primero debes revisar y aceptar los [Términos de uso de identificadores adicionales.](https://support.appsflyer.com/hc/article_attachments/360017900558)
   * Si decides no permitir los identificadores que son cargados por conexiones de socios existentes, se te pedirá que confirmes que deseas dejar de cargar estos identificadores.
4. Haz clic en **Guardar**.

<div id="privacy-regulations" />

## Regulaciones de privacidad

Esta sección describe las regulaciones de privacidad que afectan cómo se pueden compartir los identificadores de usuario.

<div id="ios" />

<Accordion title="apps de iOS,">

A partir de la versión 14.5, iOS requiere que cada aplicación ofrezca al usuario la opción de permitir o no compartir su identificador de dispositivo IDFA con fines publicitarios (Transparencia de seguimiento de aplicaciones). El hecho de que un usuario haya visto y respondido a esta opción (el "diálogo de consentimiento de ATT") determina el <Anchor target="_blank" href="/marketers/es/docs/att-implications-ios-14-and-deprecation-of-lat">estado de ATT</Anchor> del usuario.

Las opciones de política de audiencias para compartir identificadores en iOS se basan en el estado de ATT más reciente de un usuario. Sus opciones para compartir son las siguientes:

| Opción de política de usuario | Estado ATT correspondiente |
| --- | --- |
| Nunca subir | Este identificador no se envía a los socios |
| Estado de ATT: sólo autorizado | El identificador se envía si el estado ATT más reciente es **autorizado** o **af\_authorized** |
| Estado de ATT: autorizado o no determinado | El identificador se envía si el estado ATT más reciente es **autorizado**, **af\_autorizado**, **no\_determinado**, o **af\_no\_disponible***Opción predeterminada para IDFA, a partir del lanzamiento de iOS 14.5 de Apple* |
| Siempre subir | El identificador se envía independientemente del estado de ATT. Asegúrese de cumplir con los términos de uso de su aplicación.  <br />  <br />*Opción no disponible para IDFA* |

**Nota:** Audiences considera el estado ATT de un nuevo usuario como **no determinado** hasta que haya visto y respondido al cuadro de diálogo de consentimiento de ATT.

Para definiciones detalladas del estado de ATT, consulte:

* <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">Definiciones del estado ATT de Apple</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/att-implications-ios-14-and-deprecation-of-lat#valor-att">Definiciones del estado ATT de AppsFlyer</Anchor> (af\_authorized, af\_unavailable)

Además, todos los usuarios del Espacio Económico Europeo (EEE) están sujetos a la aplicación de Google de la [Ley de Mercados Digitales (DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act).

</Accordion>

<div id="android" />

<Accordion title="Android">

Los usuarios de Android del Espacio Económico Europeo (EEE) están sujetos a la aplicación de Google de la [Ley de Mercados Digitales (DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act).

</Accordion>

<div id="eu-digital-markets-act" />

<Accordion title="Ley de Mercados Digitales de la UE">

Como parte de la aplicación de la Ley de Mercados Digitales (DMA) por parte de Google a partir del 6 de marzo de 2024, Google actualiza su política de consentimiento de usuarios de la UE. Como socio de atribución de aplicaciones de Google, AppsFlyer está haciendo los cambios necesarios para apoyar los requisitos de sus políticas asegurándose de que los anunciantes maximicen el valor de sus canales de marketing de Google Ads. <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">Más información</Anchor>

**Así es como los cambios afectarán a las audiencias:**

* **Nuevo SDK de AppsFlyer**  
  El último SDK de AppsFlyer recopilará el consentimiento de los usuarios de los propietarios de apps para el <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">Espacio Económico Europeo (EEE)</Anchor> y así poder compartir sus datos con Google. Para las audiencias creadas en AppsFlyer (como las audiencias personalizadas y sugeridas), la información de consentimiento recogida del SDK se compartirá automáticamente con Audiences, y luego con Google. Una vez que actualices al último SDK, este proceso se realizará automáticamente.
* **Audiencias conectadas a Google**
  * **Consentimiento otorgado** - AppsFlyer enviará los dispositivos de los usuarios del EEE que hayan dado su consentimiento para compartir su información con Google.
  * **Consentimiento denegado** - AppsFlyer no enviará los dispositivos de los usuarios del EEE que hayan rechazado el consentimiento para compartir su información con Google.
  * **Consentimiento desconocido** - AppsFlyer enviará los dispositivos de los usuarios del EEE que no hayan dado ni negado su consentimiento como “No especificado”. Es poco probable que Google los acepte para incluirlos en su audiencia.  

    Para más detalles, consulta las <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">Preguntas Frecuentes</Anchor> de Google.
* **Audiencias existentes**  
  Todos los dispositivos que ya formaban parte de una audiencia en Google antes del 6 de marzo de 2024 no se verán afectados y seguirán siendo parte de la audiencia. Solo las nuevas audiencias o los nuevos dispositivos del EEE añadidos a una audiencia existente se cargarán en Google con consentimiento.
* **Tamaño de carga de la audiencia**  
  El tamaño estimado y real de la carga de audiencia puede verse afectado dependiendo del número de usuarios que otorguen o nieguen su consentimiento.
* #### <span id="importing-audiences"></span>**Importación de audiencias**

  * **Importar audiencia estándar** - AppsFlyer agregará los datos de consentimiento que recopile del SDK y eliminará los dispositivos no especificados o sin consentimiento de la audiencia antes de enviarlos a Google.
  * **Importar audiencia “tal cual”** - Al importar una audiencia “tal cual” a través de <Anchor target="_blank" href="/marketers/es/docs/audiences-import-audience-segments-from-internal-systems#import-a-csv-file">CSV</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/audiences-import-audience-segments-from-internal-systems#use-the-import-audience-api">API</Anchor>, dos campos de consentimiento adicionales deberán ser añadidos. Estos campos son:

| Campo de AppsFlyer (1) | Campo de Google (2) | Valores | Campo explicado |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>personalización de anuncios habilitada | personalización de anuncios | verdadero/falso | ¿El usuario dio su consentimiento a Google para usar sus datos en publicidad personalizada? |
| <span id="ad_user_data"></span>datos de usuario de anuncios habilitados | datos\_de\_usuario\_de\_anuncios | verdadero/falso | ¿El usuario dio su consentimiento para enviar sus datos a Google? |

Si los campos de consentimiento no se rellenan con valores, se enviarán a Google como “No especificado”.

<div id="note" />

> 📘 **Nota**
>
> La aplicación de la Ley de Mercados Digitales por parte de Google se aplica a plataformas tanto de Android como de iOS.

</Accordion>

<div data-zendesk-anchors="background=acerca-de h_01HKA2FS9VBCSV8FP8FH79H4R0=acerca-de user-identifiers=identificadores-de-usuario h_01HKA2FS9VSVJD54R14GC7G0P4=identificadores-de-usuario h_01HNZH99Z8NA9607VHSYH5XVW0=shared-identifiers h_01HKA2FS9V1KBK9BJAJ63FP6CV=identifiers-table setting-accountlevel-user-identifier-policy=configuraci%C3%B3n-de-la-pol%C3%ADtica-de-identificador-de-usuario-a-nivel-de-cuenta h_01HKA2FS9WNGGRP3NX5NKV15SK=configuraci%C3%B3n-de-la-pol%C3%ADtica-de-identificador-de-usuario-a-nivel-de-cuenta user-identifier-policy-options=regulaciones-de-privacidad h_01HKA2FS9W5NSKKRK2VCZARG15=regulaciones-de-privacidad h_01HNZJ1ET6F87AHHVQK17QHZDD=ios h_01HNZJ1ET67JQQCPYSM3H6Y9VW=android h_01HNZN8MWETDCMGWKJ0MMM8JK4=eu-digital-markets-act importing-audiences=importaci%C3%B3n-de-audiencias h_01HPGV1GYT8DW0GYWTC031TNVH=importaci%C3%B3n-de-audiencias h_01HNZEAJT00KKEBDPR7FD0TJNR=nota" />

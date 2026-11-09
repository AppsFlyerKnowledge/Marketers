---
title: Configurar un partner integrado
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
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-08T08:02:46Z'
  edited_at: '2026-09-02T00:28:44Z'
  id: 4410395957521
  locale: es
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/es/articles/4410395957521
---
> **Resumen:** Habilita la medición de atribución, envía postbacks a partners y activa otras funciones de integración estableciendo la conexión con los partners en AppsFlyer.

<div id="overview" />

## Visión general

Los partners, fuentes de medios y plataformas de terceros se integran con AppsFlyer por API. Este artículo contiene las instrucciones genéricas para activar y configurar la integración, incluida la generación de enlaces de atribución para ad networks que no sean SRN.

* Esta guía no se aplica a las SRNs. Utiliza el artículo específico para <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">SRN</Anchor>.
* Algunas ad networks cuentan con artículos específicos.
* Antes de configurar, contacta al partner y abre una cuenta con ellos.

<div id="partner-types-in-the-ecosystem" />

<Accordion title="Tipos de partners en el ecosistema">

La imagen a continuación muestra los diferentes tipos de partners que componen el ecosistema de atribución.

<Image align="center" alt="Ecosystem.jpg" src="https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg" />

**Lectura relacionada**: El <Anchor target="_blank" href="https://www.appsflyer.com/performance-index/">Performance Index de AppsFlyer</Anchor> clasifica las fuentes de medios móviles por categoría y región.

| Tipo de partner | Descripción |
| --- | --- |
| Redes publicitarias | Ejecutar campañas por ti. |
| Agencias | Utilizan su experiencia para conseguir usuarios de alta calidad gestionando campañas en tu nombre. Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/view-agency-data">datos de agencia</Anchor>. |
| Partners de marketing | Estos partners se especializan en trabajar con ad networks específicas. Ejemplos: Partners de gestión de campañas en Meta, partners de marketing de Apple Search Ads, partners de marketing de X. |
| Redes de retargeting | Ad networks centradas en ejecutar campañas de retargeting. |
| Plataformas de terceros | Proveen servicios relacionados con BI, como plataformas de análisis y automatización de marketing. |
| Detección del fraude | Sistemas externos de detección de fraude que no forman parte de la solución antifraude Protect360 de AppsFlyer. |

</Accordion>

<div id="partners-in-the-marketplace" />

<Accordion title="Partners en integraciones de partners">

Todos los partners, fuentes de medios y otras plataformas integradas con AppsFlyer se encuentran en la página de integraciones de partners. Puedes localizar a tus partners <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activos e inactivos</Anchor> y buscar nuevos partners con los que conectartar.

**Para buscar y filtrar todos los partners, fuentes de medios u otras plataformas en integraciones de partners:**

* En AppsFlyer, desde el menú lateral, selecciona **Colaboración** > **Integración de** **partner**. Puedes usar los distintos **filtros** de búsqueda.

<div id="invite-new-partners-to-appsflyer" />

#### Invita a nuevos partners a AppsFlyer

Si el partner con el que trabajas aún no está integrado con AppsFlyer, puedes <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#invitar-nuevos-partners-a-appsflyer">enviarle un enlace de invitación</Anchor>.

</Accordion>

<div id="your-integrated-partners" />

<Accordion title="Tus partners activos integrados">

La pestaña “Integraciones activas” en “Integraciones con partners” muestra todos tus partners integrados <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activos</Anchor> . Desde esta página, puedes obtener información del partner y gestionar la integración.

<div id="note" />

> 📘 **Nota**
>
> La lista de partners que se muestra en la pestaña **Integraciones activas** varía según la aplicación seleccionada. Puedes ver qué partners están conectados a otras aplicaciones haciendo clic en la aplicación en la esquina superior izquierda y seleccionando una aplicación diferente.

**Para ver todos tus partners activos:**

* En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > la pestaña **Integraciones activas**.

</Accordion>

<div id="about-the-integrated-partner-page" />

<Accordion title="Acerca de la página de configuración del partner">

La página está estructurada de la siguiente manera:

* **Encabezado**, que contiene:
  * Nombre del partner
  * Enlace a un artículo dedicado al partner. Si no existe un artículo dedicado, se muestra este artículo.
  * Estado de la integración
  * Aplicación seleccionada
* **Pestañas de configuración**: Las pestañas disponibles dependen del tipo de partner y de las funciones admitidas.
* **Pie de página**:
  * **Volver a la lista**: Regresa a la lista de Integraciones Activas usando las opciones de filtrado seleccionadas previamente.
  * **Mensaje de estado:** Estado actual de los datos de la pestaña (por ejemplo, guardando, guardado, error, hay cambios sin guardar).
  * **Descartar cambios:** Deshacer los últimos cambios sin guardar.
  * **Guardar:** Guarda solo la configuración de la pestaña actual.

<div id="applicable-settings-tabs-per-partner-type" />

#### Pestañas de configuración aplicables por tipo de partner

<table><thead><tr><th> </th><th colspan="2">Pestaña de configuración</th><th> </th></tr><tr><th>Tipo de partner</th><th>Integración </th><th>Permisos</th><th>Observaciones</th></tr></thead><tbody><tr><td>Fuente de medios</td><td>Sí</td><td>Sí</td><td><p><strong>Pestañas adicionales disponibles</strong>: Costo, ingresos por publicidad, enlace de atribución</p><p>Incluye ad networks, redes de afiliados, editores directos, publicidad programática, ad networks nacionales de China y redes de retargeting.<br/>Para las SRNs, la pestaña de enlace de atribución no es aplicable.</p></td></tr><tr><td>Agencia </td><td>N/A</td><td>Sí</td><td>Agencias independientes que no funcionan como ad networks</td></tr><tr><td>Plataforma de terceros</td><td>Sí</td><td>N/A</td><td>Plataformas de análisis o automatización de marketing</td></tr><tr><td>Partner de marketing </td><td>Sí</td><td>N/A</td><td> </td></tr></tbody></table>

</Accordion>

<div id="set-up-a-partner-non-srn" />

## Configurar un partner (no SRN)

<div id="important" />

> 🚧 **¡Importante!**
>
> Al habilitar la integración de un partner, de forma predeterminada, compartes ciertos datos, incluida la información personal (por ejemplo, ID de publicidad, dirección IP). Asegúrate de tener la base legal y los derechos adecuados para compartir estos datos. Puedes limitar el intercambio de datos con un partner siguiendo las instrucciones proporcionadas en el <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">framework de privacidad avanzada agregada</Anchor> y los métodos de <Anchor target="_blank" href="/marketers/es/docs/apply-privacy-preserving-sdk-methods">preservación de privacidad</Anchor> de los artículos del SDK.

**Para acceder a la configuración y configurar tus campañas con el partner:**

Busca y selecciona a tu partner en [Integraciones con partners.](/docs/set-up-an-integrated-partner#partners-in-the-marketplace)

<div id="note-1" />

> 📘 **Nota**
>
> El paso [Configuración general](#d-general-settings) en la pestaña **Integración** es obligatorio para todos los partners. También debes completar la pestaña **Enlace de atribución** para ad networks no SRN. Las pestañas restantes son opcionales.

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

Las integraciones de partners varían en sus requisitos y pueden contener un subconjunto de todas las opciones posibles descritas en esta sección. Hay ciertas diferencias entre las configuraciones de iOS y Android.

<Image align="center" alt="set_up_an_integrated_partner.png" src="https://files.readme.io/441ddfcd784a000099ae75acdb234d32bfe75ab598a34a88c7f9ed651fe8f7ec-15520850610449.png" />

Completa las secciones requeridas.

<div id="integration-sections" />

#### Secciones de integración

La tabla siguiente incluye diferentes secciones de la página de integración. Algunas secciones están disponibles para todos, mientras que otras son específicas para cada integración.

<Table>
  <thead>
    <tr>
      <th>
        Sección
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="a-activate-partner"></span>
        Activar partner
      </td>
      <td>
        Antes de compartir enlaces de atribución con un partner, debes habilitar **Activar partner** y completar las secciones restantes de la pestaña Integración.

        * No utilices **Activar partner** para pausar o desactivar la atribución de campañas
        * Desactivar la integración de partners **puede causar daños irreversibles a las campañas activas**.
        * Infórmate más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor> y el impacto de desactivar a un partner.

        **Para activar un partner integrado**:

        1. En AppsFlyer, desde el menú lateral, selecciona **Colaboración** > **Integración de partners**.
        2. Busca y selecciona al partner. Serás dirigido a la página de configuración del partner.
        3. Activa <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">**Activar partner**</Anchor>.
        4. Haz clic en **Guardar integración.**
        5. [Opcional] Para permitir que el partner <Anchor target="_blank" href="/marketers/es/docs/manage-data-access-permissions">vea los datos atribuidos a él</Anchor>, asegúrate de activar los [Permisos de ad network](/docs/set-up-an-integrated-partner#permisos-de-ad-network) en la pestaña [Permisos](/docs/set-up-an-integrated-partner#permissions-tab).
      </td>
    </tr>
    <tr>
      <td><span id="b-advanced-privacy"></span>
        Privacidad avanzada
      </td>
      <td>
        Solo para aplicaciones iOS:  
        Cuando la **Privacidad Avanzada (para iOS 14.5+ y posteriores)** está activada, puedes <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">controlar qué datos compartir</Anchor> con el partner a través de postbacks y reportes. Esto limita el intercambio de identificadores de usuario con el partner. Ten en cuenta que cuando la opción <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad Avanzada Agregada</Anchor> está activada en la configuración de la aplicación, la **Privacidad Avanzada (para iOS 14.5+ y posteriores)** se activa y queda bloqueada.
      </td>
    </tr>
    <tr>
      <td><span id="c-transaction-id"></span>
        ID de la transacción
      </td>
      <td>
        Solo para aplicaciones iOS:  
        Cuando la opción **Compartir ID de transacción de SKAN** está activada, estás <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">compartiendo el ID de transacción de los postbacks de SKAdNetwork</Anchor> con el partner. Al hacer esto, el partner podría decodificar tus valores de conversión de SKAdNetwork.
      </td>
    </tr>
    <tr>
      <td><span id="d-general-settings"></span>
        Configuración general
      </td>
      <td>
        **ID de partner: credenciales**  
        Algunos partners requieren credenciales para que AppsFlyer se integre con ellos. Los partners se refieren a este ID como ID de aplicación, ID de cuenta, ID de usuario o ID de red. Si aparece este campo, obtén el ID del dashboard del partner e introdúcelo en el campo.
      </td>
    </tr>
    <tr>
      <td><span id="non-eu-users"></span>
        Usuarios no pertenecientes a la UE
      </td>
      <td>
        Decide si deseas activar o no la opción <Anchor target="_blank" href="/marketers/es/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**Usuarios no pertenecientes a la UE**</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="e-install-attribution"></span>
        Atribución de instalación
      </td>
      <td>
        Configura las ventanas de atribución para asignar nuevas instalaciones (primeros lanzamientos) de usuarios que vieron o hicieron clic en tu anuncio. La ventana de atribución de lookback es el tiempo máximo desde un clic o una vista de tu anuncio hasta la instalación, durante el cual las instalaciones pueden ser atribuidas al partner.

        * **Ventana de lookback click-through para instalaciones:** Establece el tiempo máximo después de un clic en la aplicación durante el cual una instalación puede ser atribuida a ese clic.

        **Atribución view-through para instalaciones: Actívala para comenzar a atribuir nuevas instalaciones a usuarios que vieron tu anuncio pero no hicieron clic en él.**

        * **Ventana de lookback de visualización para instalación:** Establece el tiempo máximo después de una vista a la aplicación durante el cual una instalación puede ser atribuida a esa vista.

        <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">Infórmate más sobre las ventanas de lookbacks</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="e-re-engagement-attribution"></span>
        Atribución de re-engagement
      </td>
      <td>
        Activa y configura las ventanas de lookbacks para empezar a atribuir reengagements de tus usuarios existentes. Para aquellos que no son SRNs, esta configuración está disponible en la pestaña de Integración o en la pestaña [Enlace de atribución](/docs/set-up-an-integrated-partner#configuración-de-retargeting).

        * **Ventana de lookback click-through para reengagement:** Establece el tiempo máximo después de un clic en la aplicación durante el cual el lanzamiento de la aplicación puede ser atribuido al clic como un reengagement.

        **Atribución de visualización para reengagement:** Actívala para comenzar a atribuir reengagements de tus usuarios existentes que vieron tu anuncio pero no hicieron clic en él.

        * **Ventana de lookback view-through para reengagement:** Establece el tiempo máximo después de una vista a la aplicación durante el cual el lanzamiento de una aplicación puede ser atribuido a la vista como un reengagement.

        <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">Infórmate más sobre las ventanas de lookbacks</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="reengagement-window"></span>
        Ventana de reengagement
      </td>
      <td>
        Establece el periodo de tiempo durante el cual los eventos in-app se atribuyen principalmente a la conversión de reengagement. <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#setup-reengagement-window">Saber más</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="ignore-active-users"></span>
        Ignorar usuarios activos para retargeting
      </td>
      <td>
        Configura un periodo de inactividad para evitar registrar conversiones de retargeting en usuarios activos durante el periodo especificado. Más información sobre el <Anchor target="_blank" href="/marketers/es/docs/set-retargeting-inactivity-window">Período de inactividad para retargeting</Anchor>.

        **Para** <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">**SRNs**</Anchor>:

        1. En la pestaña de Integración, activa la **atribución de reengagement**.
        2. Activa **Ignorar usuarios activos para retargeting**.
        3. Configura la **ventana de inactividad**.

        **Para los que no son SRNs:**

        1. En la pestaña de enlace de atribución, activa la **configuración de retargeting**.
        2. Activa **Ignorar usuarios activos para retargeting**.
        3. Configura la **ventana de inactividad**.
      </td>
    </tr>
    <tr>
      <td><span id="e-cross-platform-attribution"></span>
        Atribución multiplataforma
      </td>
      <td>
        Cuando la **Prioridad de atribución igual entre plataformas** está activada, las impresiones multiplataforma durante el periodo seleccionado tienen la misma prioridad para la atribución.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-attribution"></span>
        Atribución de precarga
      </td>
      <td>
        Cuando la **Atribución de precarga** está activada, las <Anchor target="_blank" href="/marketers/es/docs/measure-preload-campaigns-with-google-play-install">instalaciones se atribuyen a las **campañas de precarga**</Anchor>. Establece la **ventana de lookback de precarga** para determinar cuánto tiempo <Anchor target="_blank" href="/marketers/es/docs/measure-preload-campaigns-with-google-play-install">después de la activación del dispositivo se puede atribuir una instalación de precarga al partner.</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-equal-attribution-priority"></span>
        Prioridad de atribución igualitaria de precargas
      </td>
      <td>
        Cuando la **Prioridad de atribución igualitaria de precarga** está activada, la interacción de precarga durante la ventana de lookback seleccionada tiene la misma <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#métodos-de-atribución">prioridad de atribución</Anchor> que los clics deterministas.
      </td>
    </tr>
    <tr>
      <td><span id="advanced-data-sharing"></span>
        Compartición avanzada de datos
      </td>
      <td>
        Cuando **Compartición Avanzada de Datos** está activado, se comparten datos adicionales con el partner a través del enlace de atribución.  
        **Nota:** Esta opción de compartición difiere de <Anchor target="_blank" href="/marketers/es/docs/meta-ads-aggregate-event-measurement-aem-for-ios#compartición-de-datos-de-aem">Compartición Avanzada de Meta Ads AEM</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="default-postbacks"></span>
        Postbacks predeterminados
      </td>
      <td>
        Cuando la integración del partner está activada, se envían postbacks predeterminados a los partners relacionados con acciones de usuario que ocurren antes del lanzamiento de la aplicación, como instalaciones, instalaciones rechazadas y reengagements.

        <div id="01H80XGTBQ4MPGGKSZW0D9GG9H" />

        > 📘 **Nota**
        >
        > * Los eventos rechazados son aquellos eventos in-app bloqueados por <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide">Protect360</Anchor> o que la validación de destino ha encontrado que no corresponden. En el caso de eventos rechazados, confirma con el partner que haya habilitado la integración de eventos rechazados con AppsFlyer.
        > * Los partners tecnológicos pueden recibir postbacks predeterminados para instalaciones y reengagements. En algunos casos, también pueden recibir postbacks de eventos in-app.

        **Para configurar postbacks predeterminados para el partner**, define la fuente de usuarios para enviar los postbacks:

        * **Solo este partner**: Envía postbacks solo cuando el evento se atribuya a este partner, es decir, el usuario que lo realizó provino de este partner.  
          **Nota:** En los siguientes casos, los postbacks predeterminados siempre se establecen como **Solo este partner**:
          * Instalaciones rechazadas
          * Agencias (con [permisos](/docs/set-up-an-integrated-partner#permisos-de-la-agencia))
        * **Todas las fuentes de medios, incluidas las orgánicas**: Envía postbacks de eventos atribuidos a cualquier partner y eventos orgánicos, es decir, el usuario que los realizó provino de cualquier fuente de medios.
        * **Desactivado** No enviar postbacks predeterminados a este partner.
      </td>
    </tr>
    <tr>
      <td><span id="g-in-app-event-postback-configuration"></span>
        <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">Postbacks de eventos in-app</Anchor>
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#mapeo-de-eventos">Mapea</Anchor> los eventos de AppsFlyer con los eventos del partner mediante postbacks. Si el envío de postbacks está habilitado, esto incluye eventos in-app rechazados (eventos bloqueados por Protect360 o eventos que no cumplen con las reglas de validación de destino).

        **Para configurar postbacks de eventos in-app:**

        1. Establece el **ID de partner** (si es necesario).
        2. Habilite los **postbacks de eventos in-app**.
        3. Establezca la **ventana de postbacks de eventos in-app**, si es necesario (lea más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">configuración de la ventana de postbacks de eventos in-app</Anchor>).
        4. Haga clic en **Agregar evento** para añadir un evento SDK o de servidor a servidor a la lista.
        5. Complete los parámetros necesarios de acuerdo con el <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#métodos-de-mapeo">método de mapeo</Anchor>.
        6. [Opcional] Haz clic en <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para enviar ciertos eventos in-app al partner.

        | Nombre del parámetro | Descripción |
        | --- | --- |
        | <span id="appsflyer-event"></span>**Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos servidor a servidor.  <br />**Consejo**: ¿No ves el evento que buscas?<br /><br />* Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.<br />* Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados.</Anchor> |
        | <span id="mapped-to-partner-event"></span>**Asignado al evento de partner** | El nombre o ID único de cada evento, tal como lo define el partner. <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#métodos-de-mapeo">Las posibles configuraciones de mapeo</Anchor> son:<br /><br />* **Campo de texto:** Obtén el ID del evento correspondiente del partner.<br />* **Cuadro desplegable:** Selecciona el evento de partner predefinido más adecuado.<br />* **Tal cual**: Envía los eventos tal como son, sin mapear el nombre del evento. |
        | <span id="for-users-from"></span>**para usuarios de** | Selecciona la opción de envío para el evento:<br /><br />* **Solo este partner**: Envía postbacks solo cuando el evento se atribuya a este partner, es decir, el usuario que lo realizó provino de este partner.<br />* **Todas las fuentes de medios, incluidas las orgánicas**: Envía postbacks de eventos atribuidos a cualquier partner y de eventos orgánicos, es decir, cuando el usuario que los realizó proviene de cualquier fuente de medios. |
        | <span id="including"></span>**incluyendo** | Selecciona <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">qué datos del evento</Anchor> deseas compartir con el partner en el postback:<br /><br />* **Sin valores ni ingresos**: Envía solo el evento en sí, sin ningún parámetro (valores o ingresos).<br />* **Valores y sin ingresos**: envía todos los parámetros **excluyendo** el valor de los ingresos.<br />* **Valores e ingresos**: Envía todos los parámetros del evento, **incluyendo** el valor de los ingresos (si existe en el evento). |

         Observaciones:

        * Los eventos asignados en la pestaña de Integración para un partner específico son aplicables tanto para postbacks estándar como para <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">SKAN</Anchor>.
        * Los postbacks se envían a los partners en tiempo real.
        * El nombre del evento de AppsFlyer puede seleccionarse o escribirse.  
          Se permite que los valores escritos incluyan guiones bajos antes o después del nombre del evento. Utilice guiones bajos solo si el nombre del evento que se envía desde AppsFlyer tiene exactamente los mismos guiones bajos.
        * **Importante:** Los nombres de los eventos son sensibles a mayúsculas y minúsculas. Para evitar discrepancias, asegúrese de usar el nombre de evento correcto para todas las fuentes de medios y versiones de la aplicación.
        * Si la sección **Postbacks de eventos in-app** no está presente en la pestaña **Integración**, significa que el partner no ha configurado aún el registro de eventos in-app con AppsFlyer en su configuración preliminar. El partner puede ponerse en contacto con AppsFlyer mediante el <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">widget del asistente para partners</Anchor> para completar la integración.
        * Para evitar que los anunciantes compartan demasiada información accidentalmente con plataformas de terceros, hemos eliminado la opción **Enviar todos los eventos (excluyendo desinstalaciones, sesiones y af\_ad\_revenue)** para plataformas de terceros, desde marzo de 2019. Las plataformas de terceros configuradas antes de esta fecha aún conservan esta opción de configuración.

        Lectura relacionada:

        * Configuración del <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">postback de eventos in-app</Anchor>
        * Configuración del <Anchor target="_blank" href="/marketers/es/docs/share-ad-revenue-data-with-partners#ad-revenue-event-postbacks-for-ad-networks">postback de eventos de ingresos publicitarios</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="h"></span>
        Guardar integración
      </td>
      <td>
        Haga clic en **Guardar integración** después de realizar los cambios.
      </td>
    </tr>
    <tr>
      <td><span id="i-connect-more-apps-optional"></span>
        Conectar más aplicaciones (opcional)
      </td>
      <td>
        Después de guardar la integración, mientras permanece en la página de configuración, puedes integrar más de tus aplicaciones con el partner.

        1. Desde la esquina superior izquierda, bajo el nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
        2. Selecciona una aplicación diferente en la lista desplegable.
        3. Repita los pasos de integración para la aplicación seleccionada.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Genera y guarda enlaces de atribución para el uso de ad networks de clic (no SRN), y envía el enlace de atribución al partner para atribuir campañas específicas, conjuntos de anuncios o anuncios individuales.

**Nota:** Las SRN no implementan enlaces de atribución generados por el anunciante, por lo que esta pestaña no es relevante para las campañas de SRN.

Para generar un enlace de atribución:

1. Seleccione **Usar un enlace de plataforma única** o **Usar OneLink**.

   Seleccione **Usar un enlace de plataforma única** si se aplica alguna de las siguientes condiciones:

   * Planea utilizar solo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">esquemas URI</Anchor> para abrir la aplicación.
   * No necesita realizar un enlace profundo con la URL.

   Seleccione **Usar OneLink** si se aplica alguna de las siguientes condiciones:

   * Desea un único enlace para aplicaciones tanto de Android como de iOS.
   * Desea utilizar enlaces de aplicaciones de Android o enlaces universales de iOS para abrir la aplicación.
   * Quiere capacidades de enlaces profundos.

   **Nota**: Al seleccionar OneLink, el enlace de grabación de clic se cambia de una aplicación específica a una <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">URL de OneLink</Anchor>.
2. Si seleccionó **Usar OneLink**:
   1. Seleccione qué plantilla de OneLink desea usar para abrir la aplicación (y potencialmente realizar el enlace profundo).
   2. [Opcional] Ingrese el **valor del enlace profundo**.
   3. [Opcional] Introduce el **valor adicional del enlace profundo**.
3. Agrega parámetros para <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#parámetros-específicos-de-android">Android</Anchor> e <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#parámetros-específicos-de-ios">iOS</Anchor>, según sea necesario.
4. [Opcional] Selecciona parámetros de atribución adicionales.

<div id="attribution-link-parameters" />

#### Parámetros del enlace de atribución

<Image align="center" alt="attribution-link-parameters-en_us.png" src="https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png" />

Agregar parámetros al enlace de atribución te permitirá realizar análisis detallados. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí. Al guardar el enlace de atribución, se guardan todos los parámetros configurados en esta pestaña.

Selecciona qué parámetros deseas agregar al enlace de atribución.

<div id="attribution-link-parameters-1" />

#### Parámetros del enlace de atribución

| Nombre | Descripción | Parámetro del enlace de atribución |
| --- | --- | --- |
| Campaña | **Parámetro requerido.**  <br />Compara diferentes campañas que se ejecutan con la fuente de medios. | C |
| Conjunto de anuncios | Compara distintos conjuntos de anuncios dentro de campañas específicas de la fuente de medios. | af\_conjunto\_de\_anuncios |
| Nombre del anuncio | Compara diferentes creatividades dentro de conjuntos de anuncios específicos dentro de campañas específicas de la fuente de medios. | af\_anuncio |
| ID del sitio y ID del subsitio | **Parámetro requerido.**<br /><br />Establece el ID del sitio para atribuir instalaciones a editores específicos.<br /><br />El ID del sitio debe pasarse a AppsFlyer en el enlace de atribución porque:<ul><li>Proporciona claridad y transparencia sobre el editor.</li><li>AppsFlyer lo utiliza para identificar y eliminar editores fraudulentos y otros grupos de tráfico.</li></ul>Ten en cuenta que la falta de un ID del sitio no afectará la atribución. Aprende más sobre el <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#site-id-parameter">parámetro de ID del sitio</Anchor>.<br /><br />Si hay muchos editores, aconsejamos limitar la cantidad de ID del sitio utilizadas y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">sobrepasar las limitaciones de ID del sitio</Anchor>. | af\_siteid y af\_sub\_siteid |
| Parámetros del suscriptor | Usa cualquiera de los 5 parámetros del suscriptor para introducir valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de datos sin procesar, lo que los hace muy útiles para realizar la agregación o el filtrado de datos. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |

Puede añadir otros parámetros al enlace de atribución escribiéndolos en un nuevo cuadro de parámetros. Puede utilizar todos los <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">parámetros de URL disponibles de AppsFlyer.</Anchor> Tenga en cuenta que solo el esquema URI y los parámetros de OneLink están codificados en el enlace de atribución.

<div id="retargeting-settings" />

#### Configuración de retargeting

**Cuando el retargeting está activado**: AppsFlyer reconoce un enlace como un enlace de atribución de <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">retargeting</Anchor>, en lugar de uno de adquisición de usuarios, al añadir al enlace de atribución.  
**Parámetro del enlace de atribución:** is\_retargeting

Para utilizar su enlace para retargeting:

1. Activa la **Configuración de retargeting**.
2. [Opcional] Ingresa un esquema URI si deseas que se utilice para abrir la aplicación.  
   **Nota**:
   * Se recomiendan los esquemas URI como método alternativo para abrir la app si fallan los Universal Links o App Links.
   * Si añade un esquema URI aquí, se anulará cualquier otro esquema URI que ya esté configurado en su plantilla OneLink.
   * El esquema URI se añade al enlace en el parámetro af\_dp.
3. [Opcional] Active **Ignorar usuarios activos para retargeting**.
4. Configure la ventana de inactividad para determinar qué usuarios se consideran activos o inactivos.
5. Establezca la ventana de reenganche para definir el período durante el cual los eventos en la app del usuario se atribuyen a la fuente de medios de retargeting.
   * Puede establecer el valor en días (1-90), horas (hasta 23) o incluso durante toda la vida.
   * La ventana de reenganche se añade al enlace en el parámetro af\_reengagement\_window.

<div id="click-through-attribution" />

#### Atribución por clic

Utilice la configuración para establecer el **tiempo máximo desde el clic hasta la instalación**. Solo se atribuyen las instalaciones (primeros inicios) que ocurren dentro de la ventana de lookback.

Rango permitido: 1-23 horas o 1-30 días.

**Parámetro del enlace de atribución:** af\_click\_lookback

Obtenga más información sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana retrospectiva de clics</Anchor>.

**Haz clic en el enlace de atribución**

<Image align="center" alt="click-through-attribution-link_en-us.png" src="https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png" />

Este es el enlace de atribución que contiene toda la información de configuración que has establecido. Puedes guardar el enlace para futuras referencias haciendo clic en **Guardar enlace de atribución**.

**Para copiar el enlace de atribución de clics:**

1. Haz clic en **Guardar enlace de atribución.**
2. Copia el enlace generado.

Envía el enlace al partner para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

#### Ventana retrospectiva de atribución por visualización

Configura el **tiempo máximo desde la impresión hasta la instalación**. Solo las instalaciones (primeras aperturas) que ocurren dentro de esta ventana, después de una impresión de anuncio, se atribuyen al partner, siempre que no haya otro clic relevante en un anuncio.

Puedes personalizar este valor entre 1 y 24 horas.

**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por visualización</Anchor>.

**Enlace de atribución de impresiones**

<Image align="center" alt="impressions-attribution-link_en-us.png" src="https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png" />

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Puedes guardar el enlace para futuras referencias haciendo clic en **Guardar enlace de atribución**.

Haz clic en Guardar enlace de atribución y luego copia el enlace generado.

**Para copiar el enlace de atribución de impresiones:**

1. Haz clic en **Guardar enlace de atribución.**
2. Copia el enlace generado.

Envíalo al partner para que se active cuando se vea un anuncio correspondiente, generalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

* Los datos de costos son reportados por tus partners integrados al hacer clic o a través de la API de costos.
* La mejor práctica es implementar la API de costos (se requiere una suscripción a ROI360)
* La API de costos incluye reportes de clics e impresiones. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad networks</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas.

<div id="note-2" />

> 📘 **Nota**
>
> Si un anunciante utiliza una agencia para gestionar sus campañas, es la agencia, y no el anunciante, quien debe integrarse con los partners pertinentes. De lo contrario, si tanto el anunciante como la agencia se integran con un partner utilizando las mismas credenciales para la misma aplicación, los datos de costos se duplican.

<div id="enabling-cost-data-by-api" />

#### Habilitación de datos de costos mediante API

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<div id="cost-data-sync-status" />

#### Estado de sincronismo de datos de costos

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Si actúa como editor mostrando anuncios en su aplicación, la función de ingresos por publicidad le permite atribuir esos ingresos a la fuente de medios que atrajo al usuario. <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution">Acerca de la atribución de ingresos por publicidad.</Anchor>

<div id="enable-ad-revenue-attribution" />

#### Activar la atribución de ingresos por publicidad

1. Comprueba qué método, <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#list-of-ad-revenue-integrated-partners">atribución agregada o a nivel de usuario</Anchor>, es compatible con el partner.
2. Siga el método adecuado en la <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#implementación">guía de integración de ingresos por publicidad.</Anchor>

<div id="ad-revenue-api-status-messages" />

#### Mensajes de estado de la API de ingresos por publicidad

| Estado | Observaciones/acción requerida |
| --- | --- |
| Activo | La conexión está activa y extrayendo datos. |
| No se encontraron datos para extraer. | La conexión fue exitosa. El partner no tenía datos relacionados con esta aplicación. |
| La API del partner no responde. Póngase en contacto con el soporte de AppsFlyer. | El servidor del partner no responde a AppsFlyer. |
| Credenciales no válidas. Introduzca credenciales actualizadas. |  |
| Algo ha ido mal. Póngase en contacto con el soporte de AppsFlyer. | Hay un problema técnico. |
| Los datos del partner aún no están listos. Si el problema persiste, ponte en contacto con el soporte de AppsFlyer. |  |
| Los datos se están procesando y estarán disponibles pronto. | Actualmente estamos procesando los datos recibidos del partner. Los datos estarán disponibles en los dashboards e informes. |
| Nunca se extrajeron los datos con éxito | Si este estado persiste durante una hora más, póngase en contacto con el soporte de AppsFlyer. |

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Otorga a las ad networks y agencias permisos específicos para acceder a tus datos y realizar diversas acciones.

* No es necesario que la integración con un partner esté activada para otorgarle permisos.
* **Ad network configurada por una agencia:** Cuando una agencia realiza la configuración del partner, el anunciante no puede ver el estado de activación de la ad network ni los permisos otorgados.
* Si tu asociación con el partner es únicamente como agencia, utiliza los **permisos de agencia** en lugar de los **permisos de ad network**. Al activar la opción "Permisos de la agencia", permites que la agencia controle los permisos de la ad network. Para más información, consulta la nota en <Anchor target="_blank" href="/partners/es/docs/getting-started-agency-onboarding#qué-significa-obtener-el-permiso-de-un-marketer">¿Qué significa obtener el permiso de un marketer</Anchor>?
* Se otorgan permisos para la aplicación actualmente seleccionada.

<div id="ad-network-permissions" />

#### Permisos de ad network

Al activar los **permisos de ad network**, la ad network puede acceder a tu dashboard y gestionar permisos adicionales, como se detalla en la tabla siguiente.

<div id="note-3" />

> 📘 **Nota**
>
> Cualquier permiso de acceso se restringe a los datos que pertenecen a la ad network.

**Para otorgar permisos a una ad network y a sus miembros de equipo:**

1. Activa los **permisos de ad network**.

   * Tu aplicación aparece en el dashboard de la ad network.
   * El administrador de la ad network tiene permisos para <Anchor target="_blank" href="/marketers/es/docs/manage-data-access-permissions">ver datos básicos sobre la aplicación.</Anchor>

   **Nota:** Los miembros del equipo de la ad network ahora son gestionados directamente por la ad network. Si deseas que un miembro específico del equipo tenga acceso, ponte en contacto con tu ad network. <Anchor target="_blank" href="/partners/es/docs/user-management-for-ad-networks#crear-un-usuario">Saber más</Anchor>
2. Selecciona permisos adicionales para otorgar a la ad network:

| **Permiso** | **Capacidad otorgada** |
| --- | --- |
| <span id="configure-integration"></span>Configurar integración | La ad network puede modificar parámetros en la pestaña de integración, excepto para configurar los postbacks de eventos in-app. |
| <span id="configure-inapp-event-postbacks"></span>Configura los postbacks de eventos in-app | La ad network puede configurar postbacks de eventos in-app. Esto implica que pueden crear, definir (mapear) y modificar configuraciones de postback.<br /><br />**¡Precaución**! **¡Importante**! Cuando este permiso y **Configurar integración** están habilitados a la vez, la ad network tiene acceso a todos los eventos. Esto incluye tráfico orgánico y tráfico no orgánico de todas las fuentes de medios. |
| <span id="access-retention-report"></span>Acceso a reportes de retención y cohorte | La ad network solo puede acceder a los datos de retención/cohorte creados por los usuarios que haya traído la ad network. |
| <span id="access-aggregate-loyal-users-data"></span>Acceso a datos agregados de usuarios leales | <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el dashboard de estado de la integración de costos (e ingresos por publicidad) o en el dashboard de la ad network individual. |
| <span id="access-aggregate-conversions-data"></span>Acceso a datos de conversiones agregadas | La ad network puede acceder a sus reportes de métricas de eventos de conversión agregados. Esto incluye instalaciones, re-engagements, reinstalaciones y reatribuciones. Ejemplo: <Anchor target="_blank" href="/partners/es/docs/aggregated-campaign-performance-report-for-ad-networks">Reporte sobre el rendimiento agregado de las campañas para las ad networks</Anchor>. |
| <span id="access-aggregate-inapp-events-data"></span>Acceso a datos agregados de eventos in-app | La ad network puede:<ul><li>Acceso a reportes agregados de datos de eventos in-app. El acceso incluye todos los datos de eventos in-app seleccionada, incluidos los datos de eventos in-app Protect360. Esto significa que pueden acceder no solo a los eventos mapeados en la configuración del postback.</li><li>Acceder a reportes agregados de datos de monetización de anuncios, que pueden incluir eventos de monetización de anuncios de otras fuentes de medios.</li></ul> |
| <span id="view-validation-rules"></span>Ver reglas de validación | La ad network puede ver <Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud">los detalles de las reglas de validación</Anchor>. |
| <span id="access-aggregate-revenue-data"></span>Acceder a los datos de ingresos agregados | La ad network puede acceder a reportes agregados de datos de ingresos, tanto publicitarios como in-app, atribuidos a los usuarios traídos por la ad network. **Nota:** Este permiso no identifica directamente al partner de ingresos publicitarios. Sin embargo, si has configurado el nombre del evento de monetización para incluir el nombre del partner, podrías revelar inadvertidamente la identidad de la red de monetización. |
| <span id="use-ad-spend-ingestion"></span>Utilizar la ingestión de gasto publicitario | La ad network puede:<ul><li>Acceder a la ventana de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Ingestión de Gasto Publicitario</Anchor>. Esta ventana muestra únicamente las aplicaciones para las que tienen permisos.</li><li>Enviar archivos de gasto publicitario para su ingestión.</li></ul> |
| <span id="access-protect360-dashboard-raw-data"></span>Accede a la consola Protect360 y raw data | La ad network puede:<ul><li>Acceder a su dashboard de Protect360 (incluyendo <Anchor target="_blank" href="/marketers/es/docs/basic-fraud-detection-and-insights-with-protectlite-dashboard-and-reporting">ProtectLITE</Anchor>).</li><li>Accede a Protect360, Reglas de Validación, y raw data si forman parte del plan de suscripción. ProtectLITE no incluye acceso a raw data.</li></ul>**Nota:** Cuando tienes una suscripción a <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide">Protect360</Anchor>, la ad network puede ver el dashboard completo. Sin una suscripción a Protect360, solo pueden ver el dashboard Lite. |
| <span id="access-ad-revenue-raw-data"></span>Acceder a los raw data de los ingresos por publicidad | La ad network puede acceder a sus <Anchor target="_blank" href="/partners/es/docs/ad-revenue-signals-for-ua-ad-networks">datos de ingresos publicitarios para utilizarlos en la optimización de UA</Anchor>.   <br />**Nota:** Este permiso solo está disponible para aplicaciones con una suscripción a <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>. |

<div id="agency-permissions" />

#### Permisos de la agencia

Lee todo sobre <Anchor target="_blank" href="/partners/es/docs/getting-started-agency-onboarding#qué-significa-obtener-el-permiso-de-un-marketer">lo que pueden hacer las agencias</Anchor> cuando se les conceden permisos.

<div id="important-1" />

> 🚧 **¡Importante!**
>
> Al trabajar con agencias, desactivar un partner integrado no desactiva automáticamente ciertas capacidades de atribución para las agencias vinculadas a ese partner:
>
> Para desactivar completamente estas funcionalidades para las agencias, el anunciante debe desactivar manualmente las siguientes configuraciones antes de desactivar al partner:
>
> 1. Atribución view-through en la instalación
> 2. Igual prioridad de atribución multiplataforma
>
> Solo después de desactivar estas opciones, el anunciante deberá proceder a desactivar al partner.
>
> **Nota:** Si el anunciante desactiva al partner sin antes desactivar estas configuraciones, las agencias podrán seguir utilizando estas capacidades de atribución.

**Precaución:** Las instalaciones realizadas por la agencia mientras el control está desactivado no se atribuyen a la agencia y no aparecen en el dashboard de la agencia ni en sus datos. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#permisos-de-la-agencia">activación de agencias</Anchor>.

**Para otorgar permisos a una agencia:**

1. Activa los **permisos de agencia**.
2. Selecciona los permisos que quieres otorgar a la agencia:

| **Permiso** | **Capacidad otorgada** |
| --- | --- |
| <span id="change-advanced-privacy-configuration"></span>Cambiar la configuración de privacidad avanzada | La agencia puede cambiar la configuración de <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">compartición de datos de privacidad avanzada de una ad network</Anchor>.   <br />**Nota:** Este permiso no es aplicable a TikTok for Business ni a Snapchat. Para estas integraciones, la configuración de Privacidad Avanzada aparece deshabilitada, reflejando la configuración del anunciante. |
| <span id="access-retention-and-cohort-reports"></span>Acceso a reportes de retención y cohorte | La agencia puede acceder a los datos de retención y cohorte creados solo por los usuarios que lleve la agencia. |
| <span id="access-aggregate-organic-data"></span>Accede a datos orgánicos agregados | La agencia puede acceder a datos orgánicos agregados |
| <span id="view-validation-rules::6872643b"></span>Ver reglas de validación | La agencia puede ver los detalles de las reglas de validación. |
| <span id="add-validation-rules"></span>Agregar reglas de validación | La agencia puede agregar y editar reglas de validación. Disponible cuando **Ver reglas de validación** está activado.   <br />**Nota**: Las agencias no pueden editar las reglas creadas por los anunciantes. |
| <span id="access-rawdata-reports"></span>Accede a reportes de datos originales | La agencia puede acceder a los reportes de raw data para el tráfico atribuido a la agencia. Los anunciantes no pueden limitar los eventos que una agencia puede ver en los reportes. |
| <span id="access-protect360-dashboard-raw-data::dd9829fd"></span>Accede a la consola Protect360 y raw data | La agencia puede:<ul><li>Acceder a tu dashboard agregado de Protect360</li><li>Acceder a Protect360, las reglas de validación y el raw data si forman parte del plan de suscripción.</li></ul>**Nota:** Para que los anunciantes que colaboran con ad networks a través de una agencia, para que tanto la ad network como la agencia puedan acceder a los datos, el anunciante debe integrar tanto la agencia como la ad network en AppsFlyer y concederles a ambas permiso para acceder a los datos. Si solo la agencia está integrada y se le otorga el permiso, la ad network no tiene acceso a los datos. |
| <span id="configure-inapp-event-postbacks::8743ba60"></span>Configura los postbacks de eventos in-app | La agencia puede configurar el envío de postbacks de eventos específicos in-app que puedes seleccionar:<ul><li>**Añadir evento:** En el menú desplegable, seleccione los eventos para los que aprueba otorgar permiso a la agencia.</li></ul>Las siguientes opciones se aplican a los eventos seleccionados:<ul><li>**Enviar ingresos generados por eventos:** Cuando está activado, la agencia puede configurar el envío de eventos, incluyendo su valor monetario.</li><li>**Opción de envío:**<ul><li>**Sólo este partner:** Cuando se selecciona, la agencia puede configurar el envío de postbacks solo para eventos atribuidos a su propio tráfico traído.</li><li>**Todas las fuentes de medios, incluidas las orgánicas:** Cuando se selecciona, la agencia puede configurar el envío de postbacks para eventos atribuidos a todas las demás fuentes de medios, agencias y usuarios orgánicos.</li></ul></li></ul> |

Aprenda más sobre <Anchor target="_blank" href="/partners/es/docs/about-agency-accounts#acceso-de-la-agencia-a-los-datos-de-los-comercializadores">cómo trabajar con agencias</Anchor>.

</Accordion>

<div id="test-the-integration" />

## Pruebe la integración

Después de completar la integración con el partner, y antes de iniciar campañas con el nuevo partner agregado, es importante probar la integración. Es más probable que se produzcan errores durante la configuración inicial. Probar con anticipación evita el riesgo de gastar recursos considerables, solo para descubrir que los datos de atribución faltan o son incorrectos. 

<div id="note-4" />

> 📘 **Nota**
>
> Antes de probar la integración, asegúrate de primero <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers">probar la aplicación para la integración básica del SDK,</Anchor> incluyendo las instalaciones orgánicas y no orgánicas.

<div id="test-the-attribution-link-for-nonsrns" />

<Accordion title="Pruebe el enlace de atribución para redes no SRN">

Las ad networks no SRN, que constituyen el 99,5% de las ad networks integradas, utilizan enlaces de atribución de AppsFlyer. De manera similar, la atribución de medios propios se realiza mediante los enlaces <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink</Anchor> de AppsFlyer.

Dado que la atribución correcta depende de los parámetros de los enlaces, prueba estos enlaces antes de iniciar una campaña con una ad network que no sea SRN o un enlace de atribución personalizado.

**Para probar los enlaces de atribución:**

1. Cree un [enlace de atribución](/docs/set-up-an-integrated-partner#attribution-link-tab).
2. Envíe el nuevo enlace de atribución a su dispositivo de prueba <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">registrado</Anchor> (por correo electrónico o código QR).
3. Haga clic en el enlace y asegúrese de ser redirigido a la tienda de aplicaciones.
4. Instale la aplicación.
5. Inicie la aplicación.
6. Comprueba si la instalación aparece en el dashboard de AppsFlyer bajo el nombre de la fuente de medios del partner. Permite hasta 30 minutos para que la instalación se muestre en el dashboard.
7. Desglosa hasta el nivel de campaña (seleccionando al partner en el **filtro de fuente de medios** en la parte superior de la página de resumen) para asegurarte de que la instalación aparece bajo el nombre correcto de la campaña.
8. Si es necesario, continúa desglosando y revisa también los niveles de conjunto de anuncios y de anuncios individuales.

</Accordion>

<div id="test-the-srn-integration" />

<Accordion title="Prueba la integración de SRN">

Las SRNs, como Meta Ads, Apple Search Ads y Google Ads, no dependen de enlaces de atribución externos para efectos de atribución. En su lugar, las SRN reciben consultas de AppsFlyer, se atribuyen a sí mismas y devuelven la respuesta. Por ello, no es viable probar la integración separadamente del sistema de la red, como se hace con las ad networks normales. Debes probar la integración con cada SRN con el que trabajes de forma independiente.

**Para probar la integración de SRN**[:](/docs/set-up-an-integrated-partner)

1. Realiza la configuración completa de SRN en AppsFlyer según la <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#srns-integradas-con-appsflyer">guía específica de configuración de SRN</Anchor>.
2. Lanza una nueva campaña de bajo presupuesto con el partner SRN.
3. Cuando el dashboard del partner muestre nuevas instalaciones, verifica si aparecen en el dashboard de AppsFlyer bajo el nombre de la fuente de medios del partner.
4. En el dashboard de resumen, desglosa hasta el nivel de campaña seleccionando al partner en el **filtro de fuente de medios**, para comprobar que la instalación se muestra bajo el nombre correcto de la campaña. Permite hasta 30 minutos para que la instalación se muestre en el dashboard.
5. Si es necesario, continúa desglosando para verificar los niveles de conjunto de anuncios y de anuncios individuales.

Si todo está en orden, puedes comenzar a ejecutar nuevas campañas de alto presupuesto con el partner. Es suficiente probar la integración una vez por cada partner SRN. Es decir, no es necesario probar en cada campaña.

</Accordion>

<div id="test-the-raw-data" />

<Accordion title="Prueba los datos en bruto">

Si tu plan de suscripción con AppsFlyer incluye acceso a datos en bruto, deberías probarlos.

**Para probar datos en bruto**:

1. Después de realizar la prueba mencionada anteriormente, ve a **reportes** > <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">**Exportar datos**</Anchor>.
2. Selecciona la fuente de medios probada.
3. Espere hasta 15 minutos después de la instalación y luego descargue el reporte de instalaciones.
4. Verifica que existan registros de instalación del partner y que incluyan parámetros como la fuente de medios, el nombre de la campaña, el momento y tipo de contacto, el ID del dispositivo (si aplica), el nombre de la agencia (denominada "partner" en el reporte) y otros.

<div id="important-2" />

> 🚧 **¡Importante!**
>
> Algunas ad networks requieren acciones específicas para habilitar la recopilación de raw data a nivel de usuario.
>
> Si observas una nueva instalación en el dashboard pero no la ves en los raw-data, consulta la guía específica del Centro de Ayuda para la ad network, por ejemplo: <Anchor target="_blank" href="/marketers/es/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#do-you-make-twitters-raw-data-available-to-agencies">X Ads</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general 01H80XGTBQ6MAK3VG0X6QMAYMP=visi%C3%B3n-general 01H80XGTBQPPZV7WR5JBHQFB0B=partner-types-in-the-ecosystem 01H80XGTBQ4CPMBRVSMM7TD4VD=partners-in-the-marketplace invite-new-partners-to-appsflyer=invita-a-nuevos-partners-a-appsflyer 01H80XGTBQRJ78XCGNZBTJVYEQ=invita-a-nuevos-partners-a-appsflyer 01H80XGTBQ8VF6V9WARZRECWVR=your-integrated-partners 01H80XGTBQJQYD3R46H95WVVM0=nota 01H80XGTBQ5BE24X219BVZBMDG=about-the-integrated-partner-page applicable-settings-tabs-per-partner-type=pesta%C3%B1as-de-configuraci%C3%B3n-aplicables-por-tipo-de-partner 01H80XGTBQPP74G38YNNYVXWP2=pesta%C3%B1as-de-configuraci%C3%B3n-aplicables-por-tipo-de-partner set-up-a-partner-nonsrn=configurar-un-partner-no-srn 01H80XGTBQXNQ7SFXZ5PBQGS1V=configurar-un-partner-no-srn 01JDM949M75Q3BAG6M65DYMHZT=importante 01H80XGTBQZXZARZCM61CMG0K3=nota-1 01H80XGTBQB9T22GQ7CSHS2S1X=integration-tab integration-tab-sections=secciones-de-integraci%C3%B3n 01H80XGTBQ0531M2RS3DH7E4Z0=secciones-de-integraci%C3%B3n d-general%20settings=d-general-settings default%20postbacks=default-postbacks 01H80XGTBQ4MPGGKSZW0D9GG9H=nota-2 01H80XGTBRT41FGP5107G96TWC=attribution-link-tab attribution-link-parameters=par%C3%A1metros-del-enlace-de-atribuci%C3%B3n 01H80XGTBRPENCTCRK8PPYSCGX=par%C3%A1metros-del-enlace-de-atribuci%C3%B3n attribution-link-parameters::3874dfb8=par%C3%A1metros-del-enlace-de-atribuci%C3%B3n-1 01H80XGTBR8630SEV80K9RD6V9=par%C3%A1metros-del-enlace-de-atribuci%C3%B3n-1 retargeting-settings=configuraci%C3%B3n-de-retargeting 01H80XGTBRT57QMPRENYSS81Z3=configuraci%C3%B3n-de-retargeting clickthrough-attribution=atribuci%C3%B3n-por-clic 01H80XGTBREZTJ6B0Y08JCKN1E=atribuci%C3%B3n-por-clic viewthrough-attribution-lookback-window=ventana-retrospectiva-de-atribuci%C3%B3n-por-visualizaci%C3%B3n 01H80XGTBRXC1YYX4FW94NDR2Z=ventana-retrospectiva-de-atribuci%C3%B3n-por-visualizaci%C3%B3n 01H80XGTBRERTJ9XHGDV416T7V=cost-tab 01H80XGTBR54TQ0DNY1JR36GXN=nota-3 enabling-cost-data-by-api=habilitaci%C3%B3n-de-datos-de-costos-mediante-api 01H80XGTBRV6BHWS76HWHK933M=habilitaci%C3%B3n-de-datos-de-costos-mediante-api cost-data-sync-status=estado-de-sincronismo-de-datos-de-costos 01H80XGTBRPWREFYFXA0A6VD47=estado-de-sincronismo-de-datos-de-costos 01H80XGTBRJ1AKX2Q7WPXFVA49=ad-revenue-tab enable-ad-revenue-attribution=activar-la-atribuci%C3%B3n-de-ingresos-por-publicidad 01H80XGTBRHE9PPRA9X46M4TGZ=activar-la-atribuci%C3%B3n-de-ingresos-por-publicidad ad-revenue-api-status-messages=mensajes-de-estado-de-la-api-de-ingresos-por-publicidad 01H80XGTBRNT4K4ZNPKVV25ESJ=mensajes-de-estado-de-la-api-de-ingresos-por-publicidad 01H80XGTBRGXS97JMG45QR4BEQ=permissions-tab ad-network-permissions=permisos-de-ad-network 01H80XGTBRS9BTT2F8F95BCE9Z=permisos-de-ad-network h_01HGFD78GRX9P2G58W21QZN4X7=nota-4 agency-permissions=permisos-de-la-agencia 01H80XGTBRTVP407AAA77N090E=permisos-de-la-agencia h_01KC9MDDRPTB05PV6NCGZVFRMJ=importante-1 test-the-integration=pruebe-la-integraci%C3%B3n 01H80XGTBSEWPHCPQF29XD6Y4W=pruebe-la-integraci%C3%B3n 01H80XGTBSTHG2FC2M31F83RGK=nota-5 01H80XGTBS4P06757QXHDKYAHT=test-the-attribution-link-for-nonsrns 01H80XGTBS2K9SPQ1MTAV7GP2H=test-the-srn-integration 01H80XGTBSTBV4RC3V279WNNB1=test-the-raw-data 01H80XGTBSN0VAX76XW9Y77T04=importante-2" />

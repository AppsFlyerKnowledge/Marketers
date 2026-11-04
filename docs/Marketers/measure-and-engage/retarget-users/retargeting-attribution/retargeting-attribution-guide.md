---
title: Guía de atribución para retargeting
metadata:
  keywords:
    - Attribution
    - Re-targeting
    - retargeting
    - Advertisers
    - reatribution
    - re-atribution
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-30T13:18:26Z'
  edited_at: '2026-08-12T12:26:34Z'
  id: 207033786
  locale: es
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/es/articles/207033786
---
> **Resumen:** Las campañas de retargeting (remarketing) alientan a los usuarios a abrir nuevamente e interactuar con la aplicación o a reinstalarla si la eliminaron.

<div id="retargeting-fundamentals" />

## Fundamentos del retargeting

La atribución de retargeting se produce cuando un usuario interactúa con una campaña haciendo clic en un [enlace de atribución de retargeting](/docs/retargeting-attribution-guide#retargeting-attribution-links) o en un <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">deep link</Anchor>. Esto genera uno de los siguientes eventos de atribución:

* **Re-engagement:** Si la aplicación está en el dispositivo, se acredita a la fuente de medios que motiva al usuario a abrir la aplicación como responsable del nuevo re-engagement.
* **Re-atribución (también conocida como reinstalación por retargeting)**: Si la aplicación no está en el dispositivo del usuario (lo que indica que el usuario la desinstaló), interactuar con la campaña de retargeting provoca que el usuario la reinstale y abra. Si esto ocurre durante una <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución,</Anchor> se acredita la reatribución a la fuente de medios de retargeting. Lectura complementaria: <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#reinstalls">Reinstalaciones.</Anchor>

![](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

Antes de comenzar con las campañas de retargeting, revisa las reglas de re-engagement y los casos de ejemplo en las secciones siguientes, luego configura el retargeting según las instrucciones en la sección de procedimientos de retargeting. Para una mejor comprensión, debes familiarizarte con el <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">modelo de atribución</Anchor> de AppsFlyer y las ventanas de atribución asociadas.

<div id="tip" />

> 👍 **Consejo**
>
> ¿Quieres saber más sobre el retargeting? Consulta este breve e informativo <Anchor target="_blank" href="https://elevate.appsflyer.com/pages/142/remarketing">curso en el Portal de Aprendizaje de AppsFlyer</Anchor>.

<div id="reengagement-rules-and-windows" />

<Accordion title="Reglas y ventanas de re-engagement">

* Las reglas de atribución de retargeting determinan si un evento es de retargeting y se acredita a la fuente de medios correspondiente.
* Similar a las campañas de atribución de adquisición de usuarios, los re-engagements de retargeting en SRNs se reportan por API y las de no SRNs, por enlace de atribución.
* Las reglas, basadas en el viaje del usuario, incluyen:
  * [Ventanas de inclusión,](/docs/retargeting-attribution-guide#ventanas-de-inclusión) un periodo de tiempo durante el cual puede tener lugar un re-engagement.
  * [Ventanas de exclusión,](/docs/retargeting-attribution-guide#ventanas-de-exclusión) un periodo de tiempo durante el cual no puede ocurrir un re-engagement.
* Si se acredita un re-engagement, los eventos in-app durante la ventana de re-engagement se <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">atribuyen doblemente.</Anchor> Esto implica que se atribuye tanto a la fuente de medios de retargeting como a la fuente de medios original de UA, si se conoce.

El diagrama a continuación presenta el conjunto de reglas de re-engagement. Utilízalo como referencia para determinar si una interacción con una campaña de retargeting se considerará un re-engagement.

**Reglas de re-engagement**

![](https://files.readme.io/e6643112f3e9969242c0dd394f6401406fbc837a9494cc4bb3825cff6365f36d-33563511578513.png) **Referencia: ventanas de inclusión y exclusión**

Las tablas a continuación contienen información de referencia relacionada con las ventanas vinculadas a la atribución de retargeting.

<div id="inclusion-windows" />

#### Ventanas de inclusión

| Tipo de ventana | Descripción |
| --- | --- |
| Impresiones | La duración máxima desde que el usuario ve un anuncio hasta que abre una aplicación.<br /><br />**Dónde se configura:** Enlace de atribución<br /><br />**Duración**:<ul><li>Por defecto: 1 día</li><li>Rango: 1-23 horas/1-7 días</li></ul> |
| Lookback del clic | La duración máxima desde que un usuario hace clic en un anuncio hasta que abre una aplicación.<br /><br />**Dónde se configura:** Enlace de atribución<br /><br />**Duración** :<ul><li>Por defecto: 7 días</li><li>Rango: 1-23 horas/1-30 días</li></ul>**Comentarios de la SRN:** Consulta con la SRN cuál es su política específica de ventana de lookback. |
| Reengagement | Considera lo siguiente respecto a la ventana de re-engagement:<ul><li>La ventana comienza cuando el usuario abre la aplicación por primera vez después de interactuar con la fuente de medios de retargeting.</li><li>Los eventos in-app se <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">atribuyen doblemente</Anchor> tanto a las fuentes de medios de adquisición de usuarios como de retargeting durante la ventana.</li><li>La duración de la ventana se determina por la configuración de la aplicación o por la SRN.</li><li>Si el usuario interactúa con otra campaña de retargeting durante la ventana de re-engagement que no está bloqueada por una ventana de exclusión, la ventana de re-engagement actual finaliza inmediatamente y comienza una nueva.</li><li>En el contexto de una reatribución: La **ventana de atribución** tiene una duración ilimitada en tiempo (similar a las instalaciones). Sin embargo, esta ventana finaliza en el caso de una nueva instalación, reinstalación o debido a limitaciones de retención de datos.</li></ul>**Dónde se establece:** Enlace de atribución<ul><li>Por defecto: 30 días</li><li>Rango: 1-23 horas/1-90 días/vida útil</li></ul>**Comentarios de la SRN**: Configurable para SRNs<br /><br />Si cambias la configuración de la ventana, el cambio afectará los re-engagements futuros. No tiene impacto en los re-engagements existentes. |

<div id="exclusion-windows" />

#### Ventanas de exclusión

| Tipo de ventana | Descripción |
| --- | --- |
| Tiempo mínimo entre conversiones de re-engagement | No registres un re-engagement durante la ventana de exclusión.<br /><br />**Tiempo mínimo entre conversiones de re-engagement**<ul><li>Durante un re-engagement, se abre una ventana en la que los eventos in-app se atribuyen tanto a las campañas de retargeting (primaria) como a las de UA (no primaria).</li><li>Esto permite medir el rendimiento de la campaña de retargeting.</li><li>Si otra red o campaña trae un re-engagement durante esta ventana:<ul><li>[Por defecto] se cierra la ventana de re-engagement existente, se registra otro re-engagement y los eventos posteriores en la aplicación se atribuyen al re-engagement más reciente.</li><li>Para impedir esto, establece el Tiempo mínimo entre conversiones de re-engagement. En este caso, solo después del tiempo mínimo transcurrido se puede registrar un nuevo re-engagement.</li></ul></li><li>Esta configuración no tiene impacto en los casos donde la ventana de re-engagement es más corta que la duración de esta configuración. Ejemplo: Si la ventana de re-engagement es de 1 día, y esta configuración es de 4 días, entonces esta configuración no tiene impacto alguno.</li><li>Estas configuraciones no afectan la duración entre la instalación y el re-engagement.</li></ul>**Dónde se establece**: Página de configuración de la aplicación<br /><br />**Duración**:<ul><li>Por defecto: Ninguno</li><li>Rango: 1-23 horas/1-30 días</li></ul> |
| <Anchor target="_blank" href="/marketers/es/docs/set-retargeting-inactivity-window">Período mínimo de inactividad</Anchor> | No registres un re-engagement o una reatribución durante la ventana de exclusión.<br /><br />**Dónde se establece:** Página de configuración de partners integrados en la pestaña de Integración.<br /><br />**Duración**:<ul><li>Por defecto: Ninguno</li><li>0-30 días</li></ul>**Comentarios de la SRN**: Considera que las SRNs suelen tener sus propias reglas de período de inactividad. Si tu configuración difiere de la del SRN, esto puede causar discrepancias. |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">Reatribución</Anchor> | La ventana de reatribución afecta las reatribuciones pero no los re-engagements.<br /><br />Los usuarios que reinstalan durante la ventana de reatribución después de interactuar con una campaña de retargeting se atribuyen a las fuentes de medios de retargeting. Lectura complementaria: <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#reinstalls">Reinstalaciones</Anchor><br /><br />**Dónde se establece:** Configuración de la aplicación |

<div id="example-flow-implementing-the-rules" />

#### Ejemplo de flujo que implementa las reglas

![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)

Lista de comprobación de reglas de re-engagement para click-through y view-through:

| Regla | Regla |
| --- | --- |
| A | El usuario interactuó con una campaña de retargeting, lo que significa que vio o hizo clic en un anuncio definido como de retargeting. |
| B | La interacción ocurrió **durante** una ventana de lookback o view-through. |
| C | El usuario estuvo inactivo más tiempo del periodo mínimo de inactividad. |
| D | En el caso de eventos in-app, ocurren durante la ventana de re-engagement. |
| E | El tiempo entre el re-engagement anterior es mayor que el tiempo mínimo entre re-engagements. |

</Accordion>

<div id="example-retargeting-scenarios" />

<Accordion title="Ejemplos de escenarios de retargeting">

| **Escenario 1: Compras antes, durante y después de la ventana de re-engagement**<br /><br />Viaje del usuario:<ul><li>Interactúa con un anuncio de la red Z, instala la app y realiza una compra (A).</li><li>Interactúa con un anuncio de retargeting de la red Y, abre la app y realiza una compra (B).</li><li>Realiza una compra (C).</li></ul>![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)<br /><br />Columna P/S: Primario o secundario como se describe en <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">doble atribución de eventos de retargeting</Anchor> |
| --- |
| Escenario 2: Múltiples conversiones durante la ventana de atribución de re-engagement<br /><br />Viaje del usuario:<ul><li>Interactúa con un anuncio de la red Z, instala la app y realiza una compra (A).</li><li>Interactúa con un anuncio de retargeting de la red Y, abre la app y realiza una compra (B).</li><li>Realiza una compra (C).</li></ul>![](https://files.readme.io/bf57f8a9597bd56a89bb3f1be3700195e1b153b548cb11ee3d37c65d5382e711-33563474530321.png)<br /><br />Columna P/S: Primario o secundario como se describe en <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">doble atribución de eventos de retargeting</Anchor> |

</Accordion>

<div id="retargeting-operations" />

## Operaciones de retargeting

<div id="retargeting-settings" />

<Accordion title="Configuraciones de retargeting">

Las siguientes configuraciones son necesarias según el escenario.

| Tipo de conversión | nombres de SRN reservados | No-SRN |
| --- | --- | --- |
| Reengagement | <ol><li>En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Configuración de la aplicación**.</li><li>Verifica que la **Atribución de re-engagement** esté activada.</li><li>Para SRN:</li><li>En el menú lateral, selecciona **Colaborar** > **Integraciones activas** y selecciona el SRN.</li><li>Activa la **Atribución de re-engagement**.</li></ol> | <ol><li>En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Configuración de la aplicación**.</li><li>Verifica que la **atribución** de **Re-engagement** esté activada.</li><li>Para no-SRN: Añade el parámetro de retargeting a los enlaces de atribución como se detalla en esta sección</li></ol> |
| Re-atribución | <ol><li>Desde el menú lateral, selecciona **Colaborar** > **Integraciones activas** y</li><li>Activa **Reinstalar atribución**.</li></ol> | <ol><li>No se requieren configuraciones explícitas.</li><li>Añade el parámetro de retargeting a los enlaces de atribución como se detalla en esta sección.</li></ol> |

<div id="non-srn-settings" />

#### **Configuraciones para no-SRN**

**Para configurar un partner de retargeting de ad network (no SRN)**:

1. En el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
2. Selecciona la ad network.
3. Activa las **configuraciones de habilitación** **para el retargeting**. Esto modifica el enlace de atribución a una URL de retargeting, añadiendo `is_retargeting=true` al enlace.

   [![](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)
4. Selecciona una de las siguientes opciones:
   * **Utiliza un enlace de atribución estándar** para enlaces de una sola plataforma (específicos de la aplicación).
   * **Utiliza OneLink**.
     * Introduce una **URL de deep linking**, si es necesario (consulta la guía de <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Deep Linking</Anchor>).
5. Copia la URL generada y entrégasela a la ad network para usarla en tu campaña de retargeting.  
   Nota : La URL no se conserva ni se puede guardar.

</Accordion>

<div id="retargeting-dashboard" />

<Accordion title="Dashboard de retargeting">

El dashboard general incluye métricas tanto de retargeting como de adquisición de usuarios. Estas métricas están basadas en LTV y se refieren a los usuarios que interactúan con una campaña de retargeting.

**Para consultar los datos de retargeting**:

1. En el menú lateral, selecciona **Analizar** > **Descripción general**.
2. Haz clic en **Tipo de vista** y elige **Retargeting**.  
   Se muestran los datos de retargeting.  
   Nota : También puedes revisar los datos de retargeting en la vista unificada. Consulta Tipos de vistas del dashboard.

</Accordion>

<div id="retargeting-attribution-links" />

<Accordion title="Enlaces de atribución de retargeting">

* Los enlaces de retargeting son similares a los de adquisición normal de usuarios.
* Créalos para:
  * No SRN que admiten retargeting.
  * Medios propios, usando la página de <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">gestión de enlaces</Anchor>.

Parámetros de enlaces de atribución de retargeting

| Parámetro | Descripciones | Obligatorio |
| --- | --- | --- |
| `es_retargeting` | Establecer en: `is_retargeting=true` | Sí |
| Identificación de publicidad | Cuando sea posible, envía un ID de publicidad como IDFA, OAID, IDFV, etc. <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">Limitaciones del modelado probabilístico para apps de iOS.</Anchor> | No |
| Ventana de lookback de clics de retargeting | <ul><li>La <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor> de retargeting funciona como la de las campañas de adquisición de usuarios.</li><li>Define el período máximo que puede pasar desde que un usuario hace clic en un anuncio hasta que se le atribuya.</li><li>La ventana de lookback se configura usando el parámetro `&af_click_lookback`.</li><li>La configuración predeterminada es de 7 días.</li></ul>**<span id="01ECF12NKTFH6Q2NH4B1WKSYF9"></span>Ejemplo**<br />Para establecer una ventana de lookback de clic-through de 14 días, añade lo siguiente al enlace de atribución de la campaña de retargeting: `&af_click_lookback=14d` | No |
| Temporizador de lookback de view-through de retargeting | <ul><li>La <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de view-through</Anchor> de retargeting funciona como la de las campañas de adquisición de usuarios.</li><li>Define el período máximo que puede pasar desde que un usuario ve un anuncio hasta que se le atribuya.</li><li>El valor predeterminado es de 1 día.</li><li>La ventana de lookback se configura mediante</li></ul>`af_viewthrough_lookback={time}`<br /><br /><br /><br />**<span id="01ECF12NKTE8W4K72VATN9RM2X"></span>Ejemplo**<br />Para configurar una ventana de lookback de view-through de 5 horas, añade lo siguiente al enlace de atribución de la campaña de retargeting: `&af_viewthrough_lookback=5h` | No |
| Ventana de re-engagement | <ul><li>La **ventana de re-engagement** se puede establecer en la interfaz de usuario del enlace de atribución. Esto configura el parámetro **af\_reengagement\_window** en el enlace de atribución. El parámetro se puede añadir manualmente.</li><li>El valor por defecto es de 30 días.</li><li>Los siguientes valores de ventana de re-engagement están disponibles:</li><li>Horas: 1-23 horas</li><li>Días: 1-90 días</li><li>De por vida: Persiste hasta que el usuario desinstale la aplicación o realice otra reactivación, por ejemplo, af\_reengagement\_window=lifetime</li></ul>Por ejemplo, **af\_reengagement\_window=60d** significa que los eventos reportados dentro de los 60 días desde la reactivación se atribuyen a la fuente de medios de retargeting. | No |

<div id="retargeting-view-through-lookback-period" />

#### Periodo de lookback de view-through de retargeting

```http
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

</Accordion>

<div id="retargeting-reports-and-raw-data" />

<Accordion title="Reportes de retargeting y raw data">

* Los reportes de retargeting, al igual que los reportes <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview">agregados</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">raw data</Anchor> de UA, están disponibles mediante las herramientas de reportes.
* Los eventos y sesiones in-app de retargeting se <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">atribuyen doblemente.</Anchor>

**Reporte de conversiones de retargeting**

* El reporte de conversiones de retargeting contiene raw data sobre re-engagements y re-atribuciones.
* Algunos campos tienen un significado distinto en el contexto del retargeting en comparación con los utilizados en los reportes de adquisición de usuarios.

Interpretación de reportes de raw data en el contexto de retargeting

| Columna | **Descripción** |
| --- | --- |
| Nombre del evento | <ul><li>La población del campo depende del tipo de reporte.</li><li>reportes de eventos in-app: El nombre del evento in-app.</li><li>Reportes de conversión de retargeting: re-engagement o reatribución.<br />[Práctica recomendada]: **¡Nota**! En el caso de Data Locker, los valores son los siguientes:<ul><li>Instalar significa reatribución</li><li>Retargeting significa re-engagement</li></ul></li></ul> |
| Tipo de toque atribuido | Tipo de engagement:<ul><li>Clic</li><li>Impresión</li></ul> |
| Tiempo de toque atribuido | Tiempo de interacción en retargeting |
| Tiempo de instalación | La primera apertura de la aplicación tras el re-engagement o la reatribución. |
| Hora del evento | La hora en que ocurrió el evento |
| ID de AppsFlyer | <ul><li>Re-atribuciones: Una nueva ID de AppsFlyer</li><li>Re-engagement: Permanece sin cambios</li></ul> |
| ¿Es retargeting? | VERDADERO para conversiones y eventos de retargeting |
| ¿Es atribución primaria? | VERDADERO para conversiones y eventos de retargeting |
| Tipo de conversión de retargeting | <ul><li>Reengagement</li><li>Re-atribución</li></ul> |
| Tipo de conversión | El tipo de conversión:<ul><li>Instalación</li><li>Reinstalación (1)</li><li>Reengagement</li><li>Desconocido (2)</li></ul>(1) Si conversion\_type=reinstall y campaign\_type=retargeting, equivale a retargeting\_conversion\_type=re-attribution<br /><br />(2) Eventos in-app/sesiones que no están atribuidos a ninguna fuente de medios. |
| Tipo de campaña | La fuente que atrae al usuario:<ul><li>Ucrania</li><li>Orgánico</li><li>Reorientación</li><li>Desconocido</li></ul> |
| Lookback de atribución | Ventana de lookback de click-through para retargeting |
| URL original | Contiene uno de los siguientes:<ul><li>Enlace de retargeting</li><li>Datos de deep linking</li><li>Vacío para SRNs</li></ul> |
| Campos de contribuyentes | No disponible para re-engagements |

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="app-requirements" />

<Accordion title="Requisitos de la aplicación">

Para ejecutar campañas de retargeting, la aplicación debe cumplir con los siguientes requisitos mínimos.

* apps de iOS,
  * Además de la integración estándar del SDK de AppsFlyer, se debe agregar código adicional al delegado de la aplicación; consulta el artículo <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#deep-linking-con-onelink">Integración del SDK</Anchor> (en la sección de enlaces de atribución).
  * Para iOS 9, se debe implementar el código para abrir aplicaciones con Universal Links. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Universal Links con iOS 9</Anchor>.
* Android:
  * Si el deep link abre una actividad distinta a la actividad principal, consulta el artículo <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#deep-linking">Integración del SDK</Anchor> (en la sección de enlaces de atribución).

</Accordion>

<div id="retargeting-limitations" />

<Accordion title="Limitaciones del retargeting">

* Desde el 17 de febrero de 2021, el retargeting admite el modelado probabilístico.
* Los datos de costos de campaña para el retargeting están disponibles en los Dashboards General y de Cohorte, así como en los reportes en la vista unificada.

</Accordion>

<div id="faq" />

<Accordion title="Preguntas frecuentes">

| **Clics de retargeting:**<ul><li>Los clics de retargeting incluyen usuarios de retargeting que interactúan con un enlace de atribución de AppsFlyer.</li><li>Los clics provenientes de SRNs o de <Anchor target="_blank" href="/marketers/es/docs/measuring-push-notification-re-engagement-campaigns">push notifications</Anchor> no se incluyen en el recuento.</li><li>Algunos clics resultan en nuevas instalaciones que se atribuyen como adquisición de usuarios. Esto ocurre cuando personas que no son usuarios, o usuarios anteriores después de haber expirado la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor>, interactúan con un enlace de retargeting e instalan la app.</li><li>Si un clic de retargeting lleva a una apertura de app a través de Universal Links o Android App Links, pero el re-engagement no se contabiliza por motivos como las ventanas de inactividad, el clic no se medirá.</li></ul> |
| --- |
| **¿Cuándo es el tiempo de toque atribuido idéntico al tiempo de instalación?**<ul><li>Cuando los usuarios de Universal Links o Android App Links realizan un deep linking, son dirigidos directamente a la aplicación, sin pasar antes por AppsFlyer.</li><li>Cuando la app se inicia y el SDK reporta un nuevo re-engagement, AppsFlyer reproduce los datos del clic utilizando la misma marca de tiempo del lanzamiento. Esto hace que el tiempo de interacción y el de lanzamiento sean idénticos.</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">Modelo de atribución de AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/audiences-guide">Guía de Audiences</Anchor>

<div data-zendesk-anchors="retargeting-fundamentals=fundamentos-del-retargeting h_01HCFJHC85VK0A05X5F69E2WKT=fundamentos-del-retargeting h_01HCFJHC851PV0VR42H07VQAXF=consejo h_01HCFJHC85EW8MBQ8MBXBVPF03=reengagement-rules-and-windows inclusion-windows=ventanas-de-inclusi%C3%B3n h_01HCFJHC85FRFJ531Y08DW03Y2=ventanas-de-inclusi%C3%B3n exclusion-windows=ventanas-de-exclusi%C3%B3n h_01HCFJHC85ECS3PJV80D943TVY=ventanas-de-exclusi%C3%B3n example-flow-implementing-the-rules=ejemplo-de-flujo-que-implementa-las-reglas h_01HCFJHC8529NW0ABMQ0RB3E8R=ejemplo-de-flujo-que-implementa-las-reglas h_01HCFJHC85E1SWGYN0BH603BV9=example-retargeting-scenarios retargeting-operations=operaciones-de-retargeting h_01HCFJHC863XPHNWRHJ60JPSRF=operaciones-de-retargeting h_01HCFJHC86XNCT5AQP48R9ZDC4=retargeting-settings nonsrn-settings=configuraciones-para-no-srn h_01HCFJHC865V36R3H58D5PWXYY=configuraciones-para-no-srn h_01HCFJHC860BS9YJM99G437G24=retargeting-dashboard h_01HCFJHC860Y5HZN66DRNN2Q89=retargeting-attribution-links retargeting-viewthrough-lookback-period=periodo-de-lookback-de-view-through-de-retargeting h_01HCFJHC863CSP03AYBXFSNC37=periodo-de-lookback-de-view-through-de-retargeting h_01HCFJHC86MNFRGYMN776FYHJV=retargeting-reports-and-raw-data additional-information=informaci%C3%B3n-adicional h_01HCFJHC86RKKPPMBYEZV4Q3X9=informaci%C3%B3n-adicional h_01HCFJHC862E6C46Q7645VJ6CZ=app-requirements h_01HCFJHC86SMKZ1HT5KHQNQS1N=retargeting-limitations h_01HCFJHC86BVSVRNAGJEKZFCJP=faq h_01HE7TPR7928SF2W8ZJS55Y5BG=v%C3%A9ase-tambi%C3%A9n" />

---
title: Configuración de la campaña de Yahoo Japan Search Ads
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-12-02T10:07:00Z'
  edited_at: '2026-09-17T00:25:15Z'
  id: 4412602890641
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/4412602890641
---
> **De un vistazo:** Yahoo Japan Search Ads, un partner de red de autorreporte (SRN) que combina publicidad y análisis.
>
> * El 15 de diciembre de 2021, la integración heredada con Yahoo Japan Search Ads, *yahoojapansearch\_int,* se reemplazó por una nueva integración, *yjsearch\_int*. Descubre cómo [empezar a trabajar con la nueva API](/docs/yahoo-japan-search-ads-campaign-configuration#integrating-with-the-new-api).

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yjsearch.png" width="121px" />

<div id="yahoo-japan-search-ads-integration-principles" />

## Principios de la integración de Yahoo Japan Search Ads

La integración de AppsFlyer con Yahoo Japan Search Ads solo es relevante para aplicaciones Android. 

La integración aprovecha un ID de enlace para la medición de conversiones y se basa en eventos de conversión predefinidos en Yahoo Japan Search Ads. Puedes asignar eventos in-app, como suscripciones y compras, a estos eventos. Esto permite la medición y el reporte de conversiones entre AppsFlyer y Yahoo Japan Search Ads.

<div id="comparing-the-legacy-and-new-integration" />

<Accordion title="Comparación entre la integración heredada y la nueva">

Compatibilidad de funciones de la API de Yahoo Japan Search Ads:

| Función | Heredada (yahoojapansearch\_int) | Nuevo<br /><br />(yjsearch\_int) |
| --- | --- | --- |
| Conversión de instalación (solo clic) | Sí | Sí |
| Conversión in-app | No | Sí |

</Accordion>

<div id="integrating-with-the-new-api" />

<Accordion title="Integración con la nueva API">

**Para habilitar la integración con la nueva API:**

1. En el dashboard de anuncios de Yahoo Japan Search Ads, <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">genera un ID de enlace</Anchor>. Debes seleccionar AppsFlyer como tu MMP.
2. En AppsFlyer, [configura la integración con Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).
3. [Asigna los eventos in-app](/docs/yahoo-japan-search-ads-campaign-configuration#2) que quieras medir y <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">crea nuevas analíticas de conversión en la herramienta Campaign Management Tool</Anchor> de Yahoo Japan Search Ads.

</Accordion>

<div id="data-sharing-between-appsflyer-and-yahoo-japan-search-ads" />

<Accordion title="Intercambio de datos entre AppsFlyer y Yahoo Japan Search Ads">

Envía postbacks a Yahoo Japan Search Ads relacionados con conversiones y eventos in-app. Los eventos in-app se asignan a eventos de conversión predefinidos que Yahoo Japan Search Ads usa para optimizar y actualizar los reportes de rendimiento. Realizas la asignación como parte de la configuración de la integración.

Consulta la siguiente tabla de asignación en el contexto de los eventos in-app de AppsFlyer (tu aplicación) y la asignación de eventos predefinidos de Yahoo Japan Search Ads.

| Evento in-app de AppsFlyer | Tipo de evento de la aplicación de Yahoo Japan Search Ads |
| --- | --- |
| af\_compra | in\_app\_purchase |
| af\_app\_opened | session\_start |
| af\_search | view\_search\_results |
| af\_content\_view | view\_item |
| af\_list\_view | view\_item\_list |
| af\_add\_to\_cart | añadir\_al\_carrito |
| af\_travel\_booking | ecommerce\_purchase |
| Cualquier evento in-app | Si tienes eventos adicionales, asígnalos al evento personalizado. |

**Datos proporcionados a AppsFlyer por Yahoo Japan Search Ads**

Cuando Yahoo Japan Search Ads atribuye una conversión, nos proporciona los parámetros de la fuente de medios que se enumeran en la tabla. Estos parámetros completan los reportes de análisis y raw data. La tabla siguiente contiene la asignación entre los parámetros de Yahoo Japan Search Ads y AppsFlyer.

<div id="yahoo-japan-search-ads-appsflyer-media-source-mapping" />

#### Asignación de la fuente de medios de Yahoo Japan Search Ads a AppsFlyer

| Yahoo Japan Search Ads | AppsFlyer |
| --- | --- |
| timestamp | Se establece como TRUE o FALSE. |
| campaign\_tracking\_id | id\_campaña |
| ad\_group\_tracking\_id | id\_anuncio |
| ad\_tracking\_id | id\_adset |
| palabra clave | palabras clave |
| match\_type | keyword\_match\_type |
| account\_id | network\_account\_id |

</Accordion>

<div id="integration-procedures" />

## Procedimientos de integración

Puedes integrar Yahoo Japan Search Ads mediante una única entidad: directamente como anunciante o a través de una agencia.  
Completa las secciones de la siguiente manera:

* [Completar una vez: obligatorio] [Integración del anunciante de Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).
* [Opcional por agencia] [Integración de la agencia](/docs/yahoo-japan-search-ads-campaign-configuration#agency-integration).

<div id="yahoo-japan-search-ads-integration-tab-sections" />

<Accordion title="Yahoo Japan Search Ads: secciones de la pestaña de integración">

<Table>
  <thead>
    <tr>
      <th>
        Paso
      </th>
      <th>
        Sección.
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="1"></span>
        1
      </td>
      <td>
        Activar socio
      </td>
      <td>
        **Pré-requisitos:**

        Obtén el <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">ID de enlace</Anchor> de Yahoo Japan Search Ads.

        **Para activar la integración de atribución de aplicaciones de Yahoo Japan Search Ads:**

        1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > **Marketplace de partners**.
        2. Busca **Yahoo! Anuncios de búsqueda (Yahoo! JAPAN Sponsored Search) - New API**, y selecciónalo.
        3. Verifica que **yjsearch\_int** aparezca en la URL. Si no es así, has seleccionado el partner integrado equivocado.
        4. En la pestaña **Integración**, selecciona **Activar partner**.  
           **Nota:** El conmutador debe estar activado <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado)</Anchor> mientras trabajes con el partner.
        5. En el campo ID de enlace, pega el ID del enlace mencionado en los requisitos previos.
        6. [Opcional] Cambios en la configuración predeterminada de la ventana de instalación <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">lookback de clics</Anchor>. El valor predeterminado de Yahoo Japan Search Ads es de 7 días. Para minimizar las discrepancias [mejor práctica], ajústalo al valor predeterminado de Yahoo Japan Search Ads.
        7. Haz clic en **Guardar integración**.
        8. En **Yahoo Japan Search Ads**, configura los nuevos ajustes de conversión como "app\_first\_open". Obtén más información sobre la configuración en Yahoo Japan Search Ads.
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        Asigna eventos in-app de AppsFlyer a eventos de Yahoo Japan Search Ads
      </td>
      <td>
        **Para asignar los eventos predefinidos de Yahoo Japan Search Ads a eventos in-app de AppsFlyer:**

        1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > **Integraciones activas**.
        2. ¡Selecciona **Yahoo! ¡Anuncios de búsqueda (Yahoo! JAPAN Sponsored Search) - Nueva API**.
        3. Activa **Postback de evento in-app.**
        4. Haz clic **Añadir evento** para añadir un evento de la aplicación a la lista.
        5. Completa los parámetros según sea necesario.
        6. Haz clic en **Guardar integración**.
        7. En **Yahoo Japan Search Ads**, configura los nuevos ajustes de conversión para que coincidan con los eventos in-app configurados. Obtén más información sobre la configuración en Yahoo Japan Search Ads.

        | Nombre del parámetro | Nota |
        | --- | --- |
        | <span id="sdk-event-name"></span>Nombre de evento SDK | El nombre del evento, tal como lo recibe AppsFlyer ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor. |
        | <span id="partner-event-identifier"></span>Identificador de evento de partner | Los eventos predefinidos de Yahoo Japan Search Ads. Las configuraciones de asignación predeterminadas sugeridas aparecen en la tabla de la sección anterior. |
        | <span id="sending-option"></span>Opción de envío | Selecciona la opción de envío para el evento:<br /><br />* **Solo este partner:** para eventos que proceden solo de usuarios atribuidos a Yahoo Japan Search Ads.<br />* **Todas las fuentes de medios, incluidas las orgánicas:** permite que toda tu base de usuarios esté disponible para reportarla a Yahoo Japan Search Ads. |
        | <span id="send-revenue"></span>Enviar ingresos | * **Sin valores & sin ingresos:** envía solo el evento en sí sin el valor del evento.<br />* **Valores & sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.<br />* **Valores & ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento). |

        Observaciones:

        * Los nombres de eventos distinguen entre mayúsculas y minúsculas. Para evitar discrepancias, asegúrese de usar el nombre de evento correcto para todas las fuentes de medios y versiones de la aplicación.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="agency-integration" />

<Accordion title="Integración de agencia">

Las agencias pueden ejecutar campañas con Yahoo Japan Search Ads en tu nombre.

<div id="agency-setup" />

#### Configuración de agencias

| Procedimiento realizado por | Procedimiento |
| --- | --- |
| AppsFlyer | <ol><li>Comprueba que has completado la [integración del anunciante de Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).</li><li>En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > **Integraciones activas**.</li><li>Selecciona una agencia.</li><li>Ve a la pestaña **Permisos** y activa **Permisos de agencia**.</li></ol> |
| El código de moneda de los ingresos del evento reportado al SDK. | <ol><li>En AppsFlyer, ve a **Colaborar** > **Integraciones de partners** > **Integraciones activas**.</li><li>Selecciona **Yahoo! Search Ads (Yahoo! JAPÓN Búsqueda patrocinada) - API nueva.**</li><li>Ve a la pestaña **Integración**.</li><li>Verifica que **Activar Partner** esté **encendido.** Si no es así, el anunciante debe completar la [integración de Yahoo Japan Search Ads del anunciante](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections)</li><li>Comprueba que el resto de la configuración, como las ventanas de lookback y la asignación de eventos in-app, sea correcta. Si es necesario, pídele al anunciante que haga cambios.</li><li>Introduce tu **ID de cliente de Yahoo Japan Search Ads**. El ID está disponible en la <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=36745&o=default#:~:text=How%20to%20check%20Account%20ID">herramienta de gestión de campañas</Anchor>. Ten en cuenta que solo se puede conectar un ID de cliente.</li><li>Haga clic en **Guardar**.</li></ol> |

</Accordion>

<div id="subsidiary-procedures" />

## Procedimientos adicionales

<div id="get-the-app-link-id" />

<Accordion title="Obtén el ID del enlace de la app">

**Para obtener el ID del enlace de Campaign Manager,** <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">consulta la documentación de Yahoo Japan Search Ads.</Anchor>

</Accordion>

<div id="create-a-new-yahoo-japan-search-ads-predefined-event" />

<Accordion title="Crea un nuevo evento predefinido de Yahoo Japan Search Ads">

**Para crear un nuevo evento predefinido,** consulta <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">las instrucciones de Yahoo Japan Search Ads</Anchor>.

</Accordion>

<div id="yahoo-japan-search-ads-discrepancies" />

<Accordion title="Discrepancias de Yahoo Japan Search Ads">

Consulta la tabla siguiente para conocer las discrepancias y cómo minimizarlas.

**Diferencias en los modelos de atribución**

| Causa | Nota | Consejo de AppsFlyer |
| --- | --- | --- |
| Asignación incorrecta de eventos in-app | La asignación entre AppsFlyer y Yahoo Japan Search Ads no es correcta. | <ul><li>Verifica el ID del enlace,</li><li>Comprueba que los eventos in-app de AppsFlyer estén asignados correctamente a los eventos de Yahoo Japan Search Ads.</li></ul> |

</Accordion>

<div data-zendesk-anchors="yahoo-japan-search-ads-integration-principles=principios-de-la-integraci%C3%B3n-de-yahoo-japan-search-ads h_01HH1RS8ZJSWTCDY5QBN3E041D=principios-de-la-integraci%C3%B3n-de-yahoo-japan-search-ads h_01HH1RS8ZJATXC84X8C74B95C8=comparing-the-legacy-and-new-integration h_01HH1RS8ZJWESR21H0BE7S3HV5=integrating-with-the-new-api h_01HH1RS8ZJM3EHGMKJF409QPTX=data-sharing-between-appsflyer-and-yahoo-japan-search-ads yahoo-japan-search-adsappsflyer-media-source-mapping=asignaci%C3%B3n-de-la-fuente-de-medios-de-yahoo-japan-search-ads-a-appsflyer h_01HH1RS8ZM0ZEPJ7ZJYY286J2F=asignaci%C3%B3n-de-la-fuente-de-medios-de-yahoo-japan-search-ads-a-appsflyer integration-procedures=procedimientos-de-integraci%C3%B3n h_01HH1RS8ZMAFNAGWAZDWX5PJT4=procedimientos-de-integraci%C3%B3n yahoo-japan-search-ads%E2%80%94integration-tab-sections=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMS287YR3K9CW7HN37=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMGTJQB3ANAJB8MY52=agency-integration agency-setup=configuraci%C3%B3n-de-agencias h_01HH1RS8ZMCBT0NJ5Z23ZAK6TV=configuraci%C3%B3n-de-agencias subsidiary-procedures=procedimientos-adicionales h_01HH1RS8ZMKHBA000CEX6KHQJK=procedimientos-adicionales h_01HH1RS8ZMWPS69ASK452QAXAK=get-the-app-link-id h_01HH1RS8ZMXVXH745DP5Q8SZ3D=create-a-new-yahoo-japan-search-ads-predefined-event h_01HH1RS8ZM5SXTQDPJ5E9YEKPS=yahoo-japan-search-ads-discrepancies" />

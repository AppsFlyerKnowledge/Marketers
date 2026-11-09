---
title: Configuración de la integración de Yahoo
metadata:
  keywords:
    - Advertisers
    - yahoo
    - gemini
    - Oath
    - verizon media
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-25T13:09:48Z'
  edited_at: '2026-09-11T00:25:29Z'
  id: 212067546
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/212067546
---
> **De un vistazo:** Yahoo, un partner integrado de ad network de AppsFlyer, ofrece publicidad de búsqueda y nativa en una sola plataforma publicitaria. Además de la atribución móvil basada en clics, Yahoo ofrece atribución de costos y view-through, que se pueden registrar en AppsFlyer.

<div id="setting-up-yahoo" />

## Configuración de Yahoo

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>

<div id="tip" />

> 👍 **Consejo**
>
> El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña Integración es **obligatorio**. Todos los demás pasos son descriptivos u **opcional**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="advertiser-configuration" />

### Configuración del anunciante

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En tu **primera visita** aquí, tendrás que activar el selector ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña integración. El interruptor DEBE estar ENCENDIDO mientras trabajes con el partner.

Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

Sigue estos pasos para la configuración general de Yahoo.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Yahoo.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-30 días. Te recomendamos configurar la ventana de lookback por clics en 7 días para que coincida con Yahoo.

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback por clic aquí</Anchor>.

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir las instalaciones view-through de Yahoo. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días. Te recomendamos configurar la ventana de lookback view-through en 1 día para alinearla con Yahoo.

<div id="agency-configuration" />

### Configuración de agencia

Antes de empezar a trabajar con Yahoo, el anunciante debe activar la integración por su parte; de lo contrario, las conversiones no se podrán atribuir a ti.

Para tu cuenta de Yahoo, introduce el ID de tu cuenta de Yahoo. Para Yahoo DSP, introduce el ID del anunciante.

**Note:**

* Si el anunciante y la agencia promocionan la aplicación en Yahoo, deben trabajar con cuentas de Yahoo independientes.
* La agencia solo puede usar una cuenta en Yahoo.

Para encontrar tu ID de cuenta, inicia sesión en el dashboard de Yahoo, haz clic en el icono de engranaje para abrir el menú de ***Configuración*** y selecciona ***Facturación***:

<Image align="center" alt="gemini-account-number.png" src="https://files.readme.io/77f464c6dadefc54acb3a84d97ab0d0751610b253d2da90523bc117f1f26683c-50705625726865.png" />

Las ventanas de lookback por clics y view-through están en modo de solo lectura y las debe configurar el anunciante.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Yahoo mediante postbacks.

1. Introduce el ID de Dot Tag proporcionado por Yahoo.  
   Para encontrarlo en el Dashboard de Yahoo, haz clic en el icono de engranaje para abrir el menú **Settings** y selecciona **View Dot tag code**. Copia el código del dashboard:

   <Image align="center" alt="yahoo-dot-tag.png" src="https://files.readme.io/6ceaea7447d1c3a81451dac3aa7c3c3063a5cf2c0051b4dfad6cf7aeba40ab24-small-50705593680401.png" />
2. Activa los postbacks de eventos in-app
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos server-to-server.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Yahoo.  <br />Obtén el ID de evento correspondiente de Yahoo e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

**Note:**

Para las agencias, la ***opción de envío*** y la lista de eventos disponibles para la asignación dependen de los permisos que el anunciante haya concedido a la agencia.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Esta pestaña no aplica a Yahoo.

<div id="note" />

> 📘 **Nota:**
>
> Para todas las SRN, como anuncios de Meta, Apple Search Ads, Adwords, Snapchat, etc., esta pestaña no es funcional, ya que no utilizan enlaces de atribución externos.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

<div id="enabling-and-testing-yahoo-cost-integration" />

### Habilitar y probar la integración de costos de Yahoo

La integración de costos proporciona los siguientes datos agregados:

* Datos de costos para tus campañas, conjuntos de anuncios, anuncios y geos/países. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad network</Anchor> para obtener todos los detalles sobre las dimensiones, métricas y funciones compatibles.  
  **Nota:** Los datos de costos requieren una <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview?query=xpend">suscripción a ROI360</Anchor> .
* Datos sobre clics, impresiones y datos enriquecidos (palabras clave, nombres de campañas y conjunto de anuncios).

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer datos de costos coincidentes, ya sea en el dashboard de estado de la integración de costos (y de ingresos por anuncios) o en el dashboard de la ad network individual.

<div id="warning" />

> ❗️ **Advertencia**
>
> Una vez definido el costo de Yahoo, no cambies el nombre de ninguna campaña, conjunto de anuncios o anuncio individual en funcionamiento, ya que puede provocar discrepancias graves o la ausencia de datos de costos.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Este partner no admite ingresos publicitarios.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Yahoo. Ten en cuenta que, incluso si la atribución está deshabilitada para Yahoo, la pestaña de permisos está activa y puedes otorgar control a Yahoo.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div id="marking-events-as-conversions-in-yahoo" />

## Marcar eventos como conversiones en Yahoo

Puedes marcar como conversiones los eventos que AppsFlyer envía a Yahoo mediante postbacks de eventos in-app:

<Image align="center" alt="yahoo-conversion-rules.png" src="https://files.readme.io/17a3fdd1619d4e4d0bfcca35e4fd51e7f270ce7446f9e70fb6f7787291e2e022-50705625729297.png" />

<div id="yahoo-raw-report" />

## Reporte raw Yahoo

AppsFlyer recibe los siguientes parámetros de Yahoo y los asigna a los siguientes campos en los reportes raw.

| Parámetros de Yahoo | Parámetros del reporte raw de AppsFlyer |
| --- | --- |
| Creative ID | Retargeting: Primer inicio después del re-engagement o la reatribución. |
| Nombre de la creatividad | El valor puede tener hasta 4 dígitos. |
| ID de grupo de anuncios | ID del adset |
| Nombre de grupo de anuncios | Conjunto de anuncios |
| Cadena | Cadena |
| Nombre de la campaña | Apps asociadas que pertenecen a una plantilla OneLink relacionada para atribución multiplataforma |
| Parámetros de seguimiento adicionales utilizados para la atribución. | Parámetros de seguimiento adicionales utilizados para la atribución. |

<div id="limitations" />

## Limitaciones

* Cuando habilitas la atribución por primera vez, pueden pasar hasta 4 horas antes de que se refleje en la interfaz de usuario de Yahoo.

<div id="skadnetwork-support" />

## Soporte SKAdNetwork

La interoperabilidad de SKAdNetwork con Yahoo está disponible.

<div data-zendesk-anchors="setting-up-yahoo=configuraci%C3%B3n-de-yahoo h_01HJR1D3NZJPKDK3DJ7DT3VZ44=configuraci%C3%B3n-de-yahoo h_01HJR1D3P0RS08SJZJYF2487MM=consejo h_01HJR1D3P0TMSSJBKDG130RV2E=integration-tab advertiser-configuration=configuraci%C3%B3n-del-anunciante h_01HJR1D3P05WQGP8SFZ5H5AD6A=configuraci%C3%B3n-del-anunciante activate-partner=activar-socio h_01HJR1D3P0WC1W6H8MKHKR9MX9=activar-socio general-settings=configuraci%C3%B3n-general h_01HJR1D3P0C5TNMHRGWG8JR2TQ=configuraci%C3%B3n-general clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HJR1D3P0V155S0QFVP2RDPP8=atribuci%C3%B3n-por-clic agency-configuration=configuraci%C3%B3n-de-agencia h_01HJR1D3P02HSHKFR45HRQWGCE=configuraci%C3%B3n-de-agencia inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJR1D3P0PAT8B60P5313GMQQ=configuraci%C3%B3n-de-eventos-in-app h_01HJR1D3P0G9P4FQ5QZWXD9PW8=attribution-link-tab h_01HJR1D3P03WM14AYT4TKXVX0X=nota h_01HJR1D3P0YHSB6QDQJ77WFR45=cost-tab enabling-and-testing-yahoo-cost-integration=habilitar-y-probar-la-integraci%C3%B3n-de-costos-de-yahoo h_01HJR1D3P10YRNVR68AAJNMY6K=habilitar-y-probar-la-integraci%C3%B3n-de-costos-de-yahoo h_01HJR1D3P10EF6X40X3YPKRTF0=advertencia h_01HJR1D3P18KB4AXKN31ZKCHRC=ad-revenue-tab h_01HJR1D3P10GR6AZ7MNS0Q7NWZ=permissions-tab marking-events-as-conversions-in-yahoo=marcar-eventos-como-conversiones-en-yahoo h_01HJR1D3P1D817ABQ7D92KJ1QK=marcar-eventos-como-conversiones-en-yahoo yahoo-raw-report=reporte-raw-yahoo h_01HJR1D3P19SM0JFZ7Q2XND911=reporte-raw-yahoo limitations=limitaciones h_01HJR1D3P1YAJJMCC6TX2NSCTG=limitaciones skadnetwork-support=soporte-skadnetwork h_01HJR1D3P1HBBBCVMRGZ96DC1E=soporte-skadnetwork" />

---
title: Configuración de la campaña de Hotstar
metadata:
  keywords:
    - Campaign
    - configuration
    - integrated partner
    - Advertisers
    - hotstar
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-12-19T09:52:42Z'
  edited_at: '2026-09-11T00:23:45Z'
  id: 360004428658
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/360004428658
---
> **En resumen:** Hotstar, un partner integrado de AppsFlyer, es un importante servicio de streaming con anuncios en India.

![](https://cdn.appsflyer.com/marketplace/static/logo/hotstar.png)

## Integración de Hotstar en AppsFlyer

**Requisito previo:** Una cuenta con el partner. Si no tienes\n una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña\n **Colaborar > Integraciones de Partners > Marketplace** .  
    (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el\n interruptor **Activar partner**.   
   \n **Nota:** El interruptor\n **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber\n más sobre\n <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

Conéctate a Hotstar activando y configurando los parámetros en la pestaña de integración.

**Para configurar la integración**:

1. Activa **Activar partner.**
2. **En** **Configuración general, activa o desactiva** **la atribución view-through:**
   * [Predeterminado] **Habilitar**: Actívalo para atribuir instalaciones post-impresión a Hotstar. La duración de la ventana de lookback se configura en la pestaña Enlace de atribución.
   * **Desactivar**: las instalaciones view-through del partner no se atribuyen.
3. **Postbacks predeterminados**: envía postbacks a Hotstar después de que el usuario instale la aplicación. Solo se reportan los usuarios atribuidos a Hotstar.
4. **Configuración de eventos in-app**: para enviar postbacks, asigna los ID de tus eventos in-app a los ID in-app de Hotstar. Configura los parámetros de la siguiente manera:
   * Habilita **los postbacks de eventos in-app**.
   * Opción de envío: **Solo los eventos atribuidos a este partner** se pueden enviar a Hotstar.
   * Haz clic en **Añadir evento** para agregar un evento de SDK a la lista. Completa los parámetros como se describe en la siguiente tabla.

| Nombre del ajuste | Description |
| --- | --- |
| Nombre de evento SDK | Nombre del evento que AppsFlyer recibe de:<ul><li>SDK integrado en la aplicación</li><li>Eventos server-to-server (servidor a servidor)</li></ul>**Consejo:** Si el evento que necesitas no está en la lista, realiza una instalación no orgánica en un dispositivo y vuelve a comprobarlo. |
| Identificador de evento de partner | Nombre o ID únicos del evento, tal como los define Hotstar. Obtén de Hotstar el ID del evento correspondiente a tu evento del SDK e introdúcelo en el campo de texto. |
| Enviar ingresos | [Predeterminado] **No habilitado:** Envía todos los parámetros in-app a Hotstar, excepto el parámetro de ingresos (`af_revenue`).<br /><br />**Habilitado**: Envía todos los parámetros in-app, incluido, cuando esté disponible, el importe de ingresos. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera enlaces de atribución de clic e impresión para que Hotstar los utilice. La siguiente tabla explica la diferencia entre el enlace de clic y el enlace de impresión, así como la relevancia de las ventanas de lookback.

| Tipo de enlace de atribución | Activación del enlace | Lookback window |
| --- | --- | --- |
| Clic | Un lead hace clic en un anuncio publicado por Hotstar | La **ventana de lookback de clics** es el **tiempo máximo desde el clic hasta la instalación**.<br /><br />Hotstar recibe una atribución si un lead hace clic e instala una app antes de que venza la ventana de lookback.<br /><br />**Nombre del parámetro**: `af_click_lookback`  <br />**Valor predeterminado**: 7 días  <br />**Rango:** 1-23 horas o 1-30 días |
| Impresión | Un lead ve un anuncio (durante al menos 1 segundo) servido por Hotstar | La ventana de lookback de **view-through** es el **tiempo máximo desde la impresión hasta la instalación**.<br /><br />Hotstar recibe una atribución si un lead ve un anuncio (impresión) publicado por Hotstar y luego instala una app antes de que venza la ventana de lookback. Esto se aplica si no hay otros clics en anuncios relevantes.<br /><br />**Nombre del parámetro**: `af_viewthrough_lookback`  <br />**Valor predeterminado**: 1 día  <br />**Rango:** 1-23 horas o 1-7 días |

Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">estructura del enlace y los parámetros</Anchor>.

**Parámetros típicos del enlace:**

| Parámetro | Nombre del parámetro | Description |
| --- | --- | --- |
| Campaña | C | Nombre de la campaña |
| Conjunto de anuncios | af\_conjunto de anuncios | Nombre del conjunto de anuncios. Se usa para diferenciar entre conjuntos de anuncios dentro de una campaña |
| Nombre de anuncio | af\_anuncio | Nombre del anuncio específico. Se usa para diferenciar entre creativos dentro de un conjunto de anuncios |
| ID de sitio | af\_siteid  <br />af\_sub\_siteid | ID de publisher utilizado para atribuir instalaciones a publishers específicos.<br /><br />**¡Buena práctica!** Si hay muchos publishers,<ul><li>Limita el número de ID de sitio en uso.</li><li>Usa el parámetro de ID de subsite para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar el límite de ID de sitio</Anchor>.</li></ul> |
| Parámetros del suscriptor | af\_sub1 hasta af\_sub5 | Úsalo para insertar valores:<ul><li>Los parámetros se analizan y se incluyen en el reporte de raw data.</li><li>Úsalos para realizar la agregación o el filtrado de datos.</li></ul> |

**Para generar los enlaces de atribución**:

1. Selecciona un nombre en la lista desplegable **Nombre del parámetro** y, a continuación, establece el valor del parámetro.
2. Para añadir más parámetros, haz clic en **Añadir parámetro** y repite el paso anterior.
3. Establece la duración de la ventana retrospectiva por clics.
4. Establece la duración de la ventana retrospectiva por impresiones.
5. Copia los enlaces de atribución de clic e impresión para usarlos en tus campañas de Hotstar.  
   **Nota**: AppsFlyer no guarda enlaces de Partners.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La atribución de costos no está disponible para este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La atribución de ingresos por publicidad no está disponible para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Puedes dar permiso a Hotstar para ver información o configurar cambios en la integración. El tipo de permiso varía en función de la relación comercial (ad network/agencia de publicidad) que tengas con Hotstar.

**Nota**: Puedes dar permisos a Hotstar aunque no haya una integración activa con ellos.

#### Permisos de ad network

**Para habilitar los permisos de ad network**:

1. Activa los **permisos de ad network**.
2. Da a los miembros del equipo de Hotstar acceso a una o varias de las siguientes opciones:
   * **Permitir la configuración de la integración**: permite que el partner configure la pestaña integración (con excepción de postbacks de eventos in-app).
   * **Permitir configurar postbacks de eventos in-app** - permite que el partner asigne postbacks de eventos in-app a sí mismo en la pestaña de integración
   * **Permitir el acceso a tu reporte de retención**: solo para los datos propios de retención del partner.
   * **Permitir acceso a tus datos agregados de usuarios fieles** - solo a los datos de usuarios fieles propios del partner
   * **Permitir acceso a tus datos agregados de eventos in-app** - solo a los datos de eventos in-app propios del partner
   * **Permitir acceso a tus datos agregados de ingresos**: solo para los datos de ingresos atribuidos al partner.
   * **Permitir la ingesta de gasto** - es a nivel de la aplicación.
   * **Permitir el acceso a tu dashboard de Protect360** - solo a los datos propios de Protect360 del partner, siempre que la función esté habilitada para el anunciante.

</Accordion>

<div data-zendesk-anchors="hotstar-integration-in-appsflyer=integraci%C3%B3n-de-hotstar-en-appsflyer h_01HKA2884DABDCZ8DGY7456A4X=integraci%C3%B3n-de-hotstar-en-appsflyer h_01HKA2884DMN9DT8KJQNMJ7P73=integration-tab h_01HKA2884D16FT48173A5TQ44G=attribution-link-tab h_01HKA2884EPHWNNT5MGNNPC5G2=cost-tab h_01HKA2884EPQCRQBX9RRV5YEDK=ad-revenue-tab h_01HKA2884E57SB3X86W6QVB80Y=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKA2884EECK51Z5NQKSGWE96=permisos-de-ad-network" />

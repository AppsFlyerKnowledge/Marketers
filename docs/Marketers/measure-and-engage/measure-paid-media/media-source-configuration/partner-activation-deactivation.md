---
title: Activación/desactivación de partners
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2019-01-29T08:53:31Z'
  edited_at: '2026-09-11T00:28:03Z'
  id: 360000844778
  locale: es
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/es/articles/360000844778
---
> **En resumen:** Activa o desactiva las integraciones de partners para permitir o denegarles el acceso a tus datos y la realización de acciones.

## Resumen general de la activación

Las integraciones de partners pueden estar activas o inactivas. Se activa una integración encendiendo primero el interruptor **Activar partner** en la página principal de integración. Existen varios tipos de integración. Una integración también se considera activa si cualquier otro [tipo de integración](#id) (ver la tabla a continuación) está activado, incluso si el interruptor **Activar partner** está desactivado.

> 🚧 **¡Importante!**
>
> Al habilitar la integración de un partner, de forma predeterminada, compartes ciertos datos, incluida la información personal (por ejemplo, ID de publicidad, dirección IP). Asegúrate de tener la base legal y los derechos adecuados para compartir estos datos. Puedes limitar el intercambio de datos con un partner siguiendo las instrucciones proporcionadas en el <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">framework de privacidad avanzada agregada</Anchor> y los métodos de <Anchor target="_blank" href="/marketers/es/docs/apply-privacy-preserving-sdk-methods">preservación de privacidad</Anchor> de los artículos del SDK.

**Para acceder a la página de integración de partners de la aplicación actualmente seleccionada:**

* En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas** y elige el partner.

Las secciones a continuación describen los diversos tipos de integración y el impacto de la configuración de activación de partner en las integraciones:

<div id="id" />

<Accordion title="Tipos de integración">

La integración principal (**Activar partner**) se activa en la primera pestaña de integración. Los tipos de integración adicionales (ver tabla a continuación) se activan desde las pestañas siguientes. **Cada integración funciona individualmente**. Para que una integración se considere activa, al menos un tipo de integración debe estar activado, sin importar el estado del interruptor Activar partner.

| Tipo de integración | Descripción |
| --- | --- |
| **Integración principal (**<Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#a-activate-partner">**Activar partner**</Anchor>) | Permite la atribución de conversiones y enviar notificaciones a los partners. |
| <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">**Costo**</Anchor> (cuando aplica) | Permite obtener datos sobre costos, clics e impresiones de tus campañas, conjuntos de anuncios, anuncios y regiones/países. |
| <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution">**Ingresos por publicidad**</Anchor> (cuando aplica) | Permite obtener datos sobre ingresos provenientes de tus anuncios |
| <Anchor target="_blank" href="/marketers/es/docs/skan-integrated-partners-list">**SKAN**</Anchor> (cuando aplica) | Permite recibir notificaciones SKAN de los partners. |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">**Permisos**</Anchor> | Permite otorgar permisos a ad networks y agencias para acceder a tus datos y realizar acciones en tu integración. |

</Accordion>

<div id="effect-of-the-partner-activation-setting" />

<Accordion title="Efecto de la configuración de activación del partner">

La siguiente tabla presenta el impacto de las configuraciones de activación de partners en la atribución y los postbacks en diversos escenarios.

<table><thead><tr><th>Escenario</th><th>Activar partner:<br/>Activado</th><th>Activar partner: Desactivado</th></tr></thead><tbody><tr><td>Atribución y postbacks para nuevas instalaciones, <span>reatribuciones y re-engagements</span> </td><td><p><strong>Atribución:</strong> Sí</p><p><strong>Postbacks:</strong> Sí</p></td><td><p><strong>Atribución:</strong> No</p><p><strong>Postbacks:</strong> No</p></td></tr><tr><td><span>El engagement (clic) sucede antes de la desactivación; la instalación/reatribución/re-engagement se produce después de la desactivación</span></td><td><p><span>No aplicable</span></p></td><td><span>El partner desactivado no se atribuye.</span></td></tr><tr><td>Clics e impresiones</td><td>Los engagements se pueden atribuir y mostrar en el dashboard.</td><td><ul><li>El clic redirecciona a una página 403 prohibida.</li><li>Los engagements no se pueden atribuir ni se muestran en el dashboard.</li></ul></td></tr><tr><td>Atribución SKAN</td><td colspan="2"><p>No aplica.</p><p>Cuando se configura la atribución SKAN, los datos de SKAN se registran independientemente de si <strong>Activar partner</strong> está activado o no. </p></td></tr></tbody></table>

</Accordion>

## Activar la integración de un partner

**Para activar o editar la integración principal (pestaña Integración) de la aplicación seleccionada actualmente:**

1. **Para activar:** En AppsFlyer, en el menú lateral, selecciona la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   **Para editar:** En AppsFlyer, en el menú lateral, selecciona la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.
2. Busca al partner y selecciónalo. Serás enviado a la página de configuración de integración.
3. Desde la pestaña **Integración**, activa **Activar partner**.
4. Haz clic en **Guardar integración**.

Consulta [otros tipos de integración](#id).

> ❗️ **Precaución**
>
> Asegúrate de no utilizar la configuración **Activar partner** para pausar o finalizar campañas. Hacerlo podría causar daños irreversibles a la medición de campañas que están en curso.

#### ¿Quién puede activar una integración?

Las integraciones con partners pueden ser activadas por marketers y agencias según lo establecido en la tabla siguiente.

| Activado por | nombres de SRN reservados | No SRN |
| --- | --- | --- |
| Comercializador | Se activa para uso propio y en nombre de las agencias. | Se activa para uso personal |
| Agencia | No se puede activar | Activa los no SRN designados por la agencia |

## Desactivar la integración de un partner

Puede desactivar la integración de un partner en tu aplicación desactivando el botón **Activar partner**. Esto significa que los partners no reciben la atribución de conversiones ni se les envían los postbacks. Sin embargo, si alguno de los otros [tipos de integración](#id) aún está activo, seguirán operando aunque el botón **Activar partner** esté desactivado. Esto implica que la **integración todavía está activa** y se podrían seguir recopilando datos.

<span id="deactivating-a-partner"></span>**Para desactivar una integración de partner:**

1. En AppsFlyer, en el menú lateral, selecciona la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.
2. Busca al partner y selecciónalo. Serás enviado a la página de configuración de integración.
3. Desde la pestaña **Integración**, desactiva **Activar partner**.
4. Haz clic en **Guardar integración**.
5. Para desactivar completamente al partner de todos los [otros tipos de integración](#id), revisa cada pestaña en la página de integración y desactívalas.  
   **Nota:** Para Google y Meta Ads, para dejar de registrar datos de SKAN, ve a la pestaña SKAN y elimina la conexión.
6. Haz clic en **Guardar integración**.
7. [Opcional] Después de guardar la integración, mientras todavía estés en la página de configuración, puedes **desactivar el partner de otras aplicaciones:**
   1. Desde la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente de la lista desplegable.
   3. Repite los pasos 2 a 4.

## Acceso de partner y agencias a los dashboards

Los partners y las agencias tienen diferentes vistas del dashboard y opciones de configuración, de acuerdo con sus permisos.

### Visibilidad de los partners

* Los partners ven la configuración de **Activar partners** en modo de solo lectura. Esto ocurre incluso si el partner tiene permiso para configurar la integración.
* La visibilidad de la configuración del partner depende de si fue el marketer o la agencia quien configuró la integración, como se detalla en la siguiente tabla:

| Integración configurada por | Configuración visible para el partner |
| --- | --- |
| Comercializador | Sí |
| Agencia | No |

### Permisos de la agencia

Puede otorgar permiso a las agencias para trabajar con tu aplicación y generar tráfico en tu nombre.

**Para conceder permisos a una agencia en una aplicación:**

1. En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
2. Localiza la agencia y selecciónala.
3. Ve a la pestaña **Permisos** y activa los **Permisos de agencia.**
4. [Opcional] Concede a la agencia <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos</Anchor> adicionales.

> 📘 **Nota:**
>
> * Una **agencia** puede activar o desactivar la opción **Activar partner** para **partners no SRN**.
> * Un **marketer** puede activar o desactivar la opción **Activar partner** para las **SRNs**. Al hacerlo, las instalaciones de ese SRN **no se atribuyen a la agencia**.

#### Permisos de agencia desactivados

Cuando los permisos están desactivados para las agencias:

* La agencia no tiene acceso a la aplicación en el dashboard de AppsFlyer.
* Las nuevas instalaciones y eventos no se atribuyen a la agencia.
* No se envían postbacks a las fuentes de medios utilizadas por la agencia.
* Los nuevos eventos de conversiones previas a la desactivación de la agencia se atribuyen y muestran en el dashboard del marketer, pero los postbacks no se envían a las fuentes de medios.

**Nota:** Si el marketer desactiva los permisos de la agencia, los datos históricos de la agencia (como instalaciones y costos) dejan de ser visibles.

Los siguientes ejemplos describen lo que ocurre con el tráfico que continúa siendo enviado después de que un marketer retire los permisos de la agencia:

> 📄 **Ejemplo 1**
>
> **Campaña de agencia con un no SRN (partner de enlace de atribución)**
>
> El tráfico se atribuye como orgánico o a un engagement previo si aún está dentro de su ventana de lookback. La agencia no se atribuye.
>
> Este ejemplo también se aplica a escenarios en los que AppsFlyer recibe enlaces de atribución de clics y consulta la API del partner.

> 📄 **Ejemplo 2**
>
> **Campaña de agencia con un SRN (partner de enlace de atribución)**
>
> El tráfico se atribuye al SRN en el dashboard del marketer, pero no a la agencia.

<div data-zendesk-anchors="overview=resumen-general-de-la-activaci%C3%B3n h_01HRA982WC3519NMGXV5WEY1AZ=resumen-general-de-la-activaci%C3%B3n 01JDM949M75Q3BAG6M65DYMHZT=importante %20id%3D=id integration-types=id h_01HRAERWRJ2SBRY9XQG983WP5M=effect-of-the-partner-activation-setting activating-a-partner=activar-la-integraci%C3%B3n-de-un-partner h_01HJR1D6THJ9TNGZZV78SEVBZN=activar-la-integraci%C3%B3n-de-un-partner h_01HJR1D6THSEA65CY71VWJYX1P=precauci%C3%B3n who-can-activate-partners=qui%C3%A9n-puede-activar-una-integraci%C3%B3n h_01HJR1D6THRMF854SCSFVZFWM9=qui%C3%A9n-puede-activar-una-integraci%C3%B3n deactivated-partners=desactivar-la-integraci%C3%B3n-de-un-partner h_01HJR1D6THE2QWSF971VQFXCBX=desactivar-la-integraci%C3%B3n-de-un-partner h_01HJR1D6THS60X7VTDN2X6FT0K=deactivating-a-partner partner-and-agency-dashboards=acceso-de-partner-y-agencias-a-los-dashboards h_01HJR1D6THB0N1C8XCC5YAMQQ3=acceso-de-partner-y-agencias-a-los-dashboards partner-visibility=visibilidad-de-los-partners h_01HJR1D6TJ6D3TV2PCFWP4SEAR=visibilidad-de-los-partners agency-permissions=permisos-de-la-agencia h_01HJR1D6TJ9PHVG6GGQ2Z1KJRQ=permisos-de-la-agencia h_01HJR1D6TJ9T55PSPBRNW1XXS7=nota disabled-agency-permissions=permisos-de-agencia-desactivados h_01HJR1D6TJ1ABQM6HCPK277R0Z=permisos-de-agencia-desactivados h_01HJR1D6TJBT0D3G2KWKFKEW5S=ejemplo-1 h_01HJR1D6TJTXF49JP3VJE6ZYC9=ejemplo-2" />

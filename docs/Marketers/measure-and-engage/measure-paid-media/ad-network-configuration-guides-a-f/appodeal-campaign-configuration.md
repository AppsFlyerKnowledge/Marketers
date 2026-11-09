---
title: Configuración de la campaña de Appodeal
metadata:
  keywords:
    - ad revenue
    - cost
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
  created_at: '2019-12-17T19:36:02Z'
  edited_at: '2026-08-12T12:13:05Z'
  id: 360004404977
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/360004404977
---
> **De un vistazo:** Appodeal, partner integrado de AppsFlyer, ofrece a los propietarios de aplicaciones atribución de clics y una solución integral de monetización de anuncios. Los ingresos por anuncios se reportan con granularidad a nivel de usuario.

<div id="setting-up-appodeal-integration" />

## Configurar la integración con Appodeal

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/appodeal.png" />

La integración de AppsFlyer con Appodeal admite la atribución de clics y la <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">atribución de ingresos publicitarios a nivel de usuario.</Anchor>

**Requisito previo:** Antes de configurar la integración, asegúrate de [ponerte en contacto con el partner](#) y abrir una cuenta con ellos. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación:

<div id="integration" />

<Accordion title="Integración">

Configura esta sección si Appodeal proporciona servicios publicitarios de ad network.

**Para habilitar la integración**:

1. Activa **Activar partner.**
2. Haz clic en **Guardar integración**.

</Accordion>

<div id="attribution-link" />

<Accordion title="Enlace de atribución">

Genera enlaces de atribución de clics (para que los use Appodeal) desde esta pestaña. <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Más información sobre la estructura y los parámetros del enlace</Anchor>.

Para generar un enlace de atribución:

1. Selecciona un parámetro en la lista desplegable Nombre del parámetro y establece un valor.
2. Haz clic en **Agregar parámetro** y repite el paso anterior para agregar más parámetros.
3. Establece la duración de la **ventana de lookback de clic-through.**
4. Copia el enlace de atribución de clics y envíalo a la ad network.  
   Nota: AppsFlyer no guarda los enlaces.

**Enlace de atribución y ventana de lookback**

| Tipo de enlace de atribución | Activación del enlace | Ventana retrospectiva |
| --- | --- | --- |
| Clic | Un usuario hace clic en un anuncio publicado por la ad network | **La ventana de lookback de clic-through** está predefinida; es el **tiempo máximo permitido desde el clic hasta la instalación**.<br /><br />Ejemplo: una instalación (primer inicio) realizada después del clic—pero antes de que venza la ventana de lookback—se atribuye a Appodeal.<br /><br />**Nombre del parámetro**: `af_click_lookback`  <br />**Valor predeterminado**: 7 días  <br />**Rango:** de 1 a 23 horas o de 1 a 30 días |

**Parámetros típicos del enlace**

| Parámetro | Nombre del parámetro | Nota |
| --- | --- | --- |
| Apps asociadas que pertenecen a una plantilla OneLink relacionada para atribución multiplataforma | C | Nombre de la campaña |
| Conjunto de anuncios | af\_conjunto de anuncios | Se usa para diferenciar conjuntos de anuncios. |
| Nota | af\_anuncio | Se usa para diferenciar entre creatividades dentro del conjunto de anuncios. |
| Parámetros de seguimiento adicionales utilizados para la atribución. | af\_siteid  <br />af\_subsiteid | Se usa para atribuir instalaciones a publishers específicos.<br /><br />**¡Buena práctica!** Si hay varios publishers,<ul><li>Limita el número de ID de sitio en uso</li><li>Usa el parámetro de ID de subsite para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder el límite de ID de sitio</Anchor></li></ul> |
| Parámetros de suscriptor | af\_sub1, af\_sub2, af\_sub3, af\_sub4, and af\_sub5 | Se usa para insertar valores.<ul><li>Los parámetros se analizan y se incluyen en el Reporte de raw data.</li><li>Úsalos para realizar agregación o filtrado de datos</li></ul> |

</Accordion>

<div id="cost" />

<Accordion title="Coste">

Appodeal envía datos de costos de CPI a través del enlace de atribución.

</Accordion>

<div id="ad-revenue" />

<Accordion title="Cadena">

* Appodeal ofrece mediación de ingresos publicitarios con <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">granularidad a nivel de usuario</Anchor>
* Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution">atribución de ingresos publicitarios de AppsFlyer</Anchor>

**Para habilitar la API de ingresos por publicidad**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instrucciones de integración</Anchor>.

</Accordion>

<div id="permissions" />

<Accordion title="Permisos">

No es necesario configurar permisos para Appodeal.

</Accordion>

<div data-zendesk-anchors="setting-up-appodeal-integration=configurar-la-integraci%C3%B3n-con-appodeal h_01HKW9BK4ZAR4Q22Z9WBVFPPT7=configurar-la-integraci%C3%B3n-con-appodeal h_01HKW9BK4ZDFDX9X7P2HW4QR1P=integration h_01HKW9BK4ZM4JMQKT4Y8ZC050V=attribution-link h_01HKW9BK4ZV8DWSZQ55332NQWY=cost h_01HKW9BK4ZS3GYMZ6E9T64PPGC=ad-revenue h_01HKW9BK4ZJ1F1Z099NJHRZRNE=permissions" />

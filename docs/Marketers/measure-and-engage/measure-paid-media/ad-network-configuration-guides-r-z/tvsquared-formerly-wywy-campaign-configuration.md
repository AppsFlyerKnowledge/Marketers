---
title: Configuración de la campaña de TVSquared (anteriormente WyWy)
metadata:
  keywords:
    - Advertisers
    - TV Squareed
    - Wywy
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-09-06T08:58:47Z'
  edited_at: '2026-08-12T12:16:24Z'
  id: 213836263
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/213836263
---
> **En resumen:** TVSquared (anteriormente WyWy), partner integrado de ad network de AppsFlyer, permite a toda la organización digital —especialistas en marketing, responsables de producto y científicos de datos— ejecutar el negocio basándose en datos. TVSquared crea una vista integrada de los consumidores en todos los dispositivos y proporciona herramientas para optimizar la experiencia del usuario en tiempo real.

## Configuración de TVSquared

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

**Nota:** Para TVSquared, debes completar la pestaña Integración. Las demás pestañas no se aplican a TVSquared.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

1. Activa ***Activate Partner***.  
   Se muestran los parámetros de integración.  
   Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
2. Completa los campos de Configuración general:
   * ***SITEID***: Introduce el SITEID que obtuviste de TVSquared.
   * ***COLLECTORID***: Introduce el COLLECTORID que obtuviste de TVSquared.
3. **Postbacks predeterminados**: AppsFlyer envía postbacks a TVSquared después de la instalación o el re-engagement del usuario. Selecciona la opción de envío para la que el partner recibirá postbacks:
   * **Eventos atribuidos a cualquier partner u orgánico**: Todas las instalaciones, independientemente de la fuente, se reportan a TVSquared
   * **Desactivado**
4. Completa los campos de configuración de los eventos in-app:

* ***SITEID***: Introduce el SITEID que obtuviste de TVSquared.
* ***COLLECTORID***: Introduce el COLLECTORID que obtuviste de TVSquared.
* **customerid:** (opcional) Puedes dejar este campo en blanco.
* (opcional) Activa ***Postback de eventos in-app***: asigna tus eventos in-app a TVSquared mediante postbacks. Configura los parámetros de la siguiente manera:
  * Haz clic en Agregar evento para añadir un evento del SDK a la lista y completa los parámetros.
* Haz clic en **Guardar integración**.

> 📘 **Nota:**
>
> De acuerdo con los términos y condiciones de los anuncios de Meta y X Ads, AppsFlyer no puede compartir datos a nivel de usuario con ninguna 3rd party. Por lo tanto, todas las instalaciones de los anuncios de Meta y X Ads se envían a TVSquared como orgánicas.
>
> Para obtener más información sobre cómo compartir datos con 3rd parties, haz clic <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention">aquí</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para TVSquared.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para TVSquared.

</Accordion>

<div data-zendesk-anchors="setting-up-tvsquared=configuraci%C3%B3n-de-tvsquared h_01HF9R4JZ504QNYCQQ8TFDM6FV=configuraci%C3%B3n-de-tvsquared h_01HF9R4JZ5VXT1P5T3RVRXN522=integration-tab activate-partner=activar-socio h_01HF9R4JZ55HMSRD3TNFF05PKZ=activar-socio h_01HF9R4JZ5KWKPCN3ESQ9K27S7=nota h_01HF9R4JZ596NM643Z662BGY0M=attribution-link-tab h_01HF9R4JZ50XY445ABGAPDY962=cost-tab h_01HF9R4JZ5BA74FKFRKY4FPTAS=ad-revenue-tab h_01HF9R4JZ5BV6C6H6V6W53BXXK=permissions-tab" />

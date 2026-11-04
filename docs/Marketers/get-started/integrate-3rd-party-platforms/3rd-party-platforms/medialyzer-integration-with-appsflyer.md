---
title: Integración de Medialyzer con AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2026-08-12T11:59:15Z'
  id: 14963611180689
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/14963611180689
---
> **De un vistazo:** Medialyzer, un partner integrado de AppsFlyer, desarrolla y comercializa el software como una solución de servicio. La solución permite a los planificadores de medios optimizar sus campañas de TV para negocios en línea, en función de las visitas y conversiones generadas inmediatamente por la emisión del anuncio de televisión.

<div id="important" />

> 🚧 **¡Importante!**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-medialyzer" />

## Configuración de Medialyzer

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar la integración:**

1. En la pestaña **Integración**, selecciona la aplicación para la integración y activa **Activar partner**.  
   **Nota:** El selector debe permanecer <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor> mientras trabajes con el partner.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la primera visita, tendrás que activar el selector **Activar partner** para configurar la integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

Para ver una descripción detallada del Encabezado de la Ventana de Configuración de Partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

<div id="activate-partner" />

#### Activar el partner

La configuración se realiza desde la página **Integraciones activas**, pero para encontrar al partner primero debes ir al <Anchor target="_blank" href="/marketers/es/docs/partner-integrations">marketplace</Anchor>. El selector debe estar activado mientras trabajes con Medialyzer. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación del partner</Anchor>.

<div id="advanced-privacy" />

#### Privacidad avanzada

Para las aplicaciones de iOS, aparece el selector de <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad avanzada</Anchor>. Cuando se activa, limita el intercambio de identificadores de usuario con el partner. Ten en cuenta que cuando el selector <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad avanzada agregada</Anchor> está activado en la Configuración de la aplicación, la **Privacidad avanzada (para iOS 14.5+ y versiones posteriores)** está activada y bloqueada de forma predeterminada.

<div id="default-postbacks" />

#### Postbacks predeterminados

AppsFlyer envía postbacks predeterminados a Medialyzer después de las instalaciones de los usuarios. Usa esta sección para <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#f">definir estos postbacks</Anchor>.

* **Off**: los postbacks de instalaciones no se envían a Medialyzer.
* **Todas las fuentes de medios, incluidas las orgánicas**: los postbacks de instalaciones se envían para los eventos atribuidos a cualquier partner y para los eventos orgánicos.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

<div id="in-app-event-postbacks" />

#### Postbacks de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer con tus partners a través de postbacks.

[![app_event_postbacks.JPG](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)

1. Activa **Postbacks de eventos in-app.**
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista.
3. Completa los siguientes parámetros:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrese de activar el evento en un dispositivo con una instalación no orgánica y vuelva a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados.</Anchor></li></ul> |
| **asignado al evento de partner** | Introduce el nombre o ID de evento correspondiente de cada evento, como se define en BPM, o envía los eventos tal como están, sin asignación de nombres. |
| **para usuarios de** | Selecciona **Todas las fuentes de medios, incluidas las orgánicas** para enviar postbacks de los eventos atribuidos a cualquier partner y los eventos orgánicos. |
| **Incluyendo** | <ul><li>**Sin valores y sin ingresos**: envía solo el evento en sí sin parámetros (valores o ingresos).</li><li>**Valores y sin ingresos**: envía todos los parámetros **excluyendo** el valor de los ingresos.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li></ul> |

4. Haz clic en **Guardar integración**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Medialyzer.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña Costo">

Los datos de costos no se admiten en la integración con Medialyzer.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña Ingresos por publicidad">

Los datos de ingresos por publicidad no se admiten en la integración con Medialyzer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Medialyzer.

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=importante setting-up-spoteffects=configuraci%C3%B3n-de-medialyzer h_01H9FKEAV37AT3VTZ5WV1YMWC2=configuraci%C3%B3n-de-medialyzer h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab activate-partner=activar-el-partner h_01H9FKEAV3DW2A6RQ1NS44FT5F=activar-el-partner advanced-privacy=privacidad-avanzada h_01H9FKEAV3T3YCPBYW70QVF540=privacidad-avanzada default-postbacks=postbacks-predeterminados h_01H9FKEAV3Z1Y09P6E18J8AVX2=postbacks-predeterminados inapp-event-postbacks=postbacks-de-eventos-in-app h_01H9FKEAV3GG6X17X3NCCSWJAS=postbacks-de-eventos-in-app h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />

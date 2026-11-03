---
title: Integración de Appcharge con AppsFlyer
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
  created_at: '2025-06-17T13:21:47Z'
  edited_at: '2026-08-12T11:58:30Z'
  id: 36292113943825
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/36292113943825
---
> **En resumen:** Appcharge, partner integrado de AppsFlyer, es un proveedor de tecnología de comercio para juegos especializado en procesar pagos fuera de los ecosistemas tradicionales de tiendas de aplicaciones. A través de su integración con AppsFlyer, Appcharge puede enviar automáticamente a AppsFlyer datos de compras y reembolsos de la tienda web, lo que permite obtener una visión más completa del retorno de la inversión publicitaria (ROAS) y del valor del ciclo de vida (LTV).

## Acerca de Appcharge

<Anchor target="_blank" href="https://appcharge.com/">Appcharge</Anchor>, partner integrado de AppsFlyer, es una plataforma direct-to-consumer (D2C) creada para publishers de juegos para móviles. La integración ayuda a los publishers a monitorizar las compras de su tienda web, un canal de ingresos crítico fuera de las tiendas de aplicaciones tradicionales. Al enviar datos de compras y reembolsos directamente a AppsFlyer, Appcharge permite calcular con precisión el retorno de la inversión publicitaria (ROAS) basándose en los ingresos netos, lo que ofrece mejores insights sobre el rendimiento de la campaña y el valor del ciclo de vida del jugador (LTV).

La integración de Appcharge te ayuda a:

* Atribuir y medir el rendimiento del e-commerce
* Garantizar que se reporta el LTV de las compras de la tienda web
* Atribuir las compras de la tienda web a campañas de marketing
* Mantener la coherencia con los datos de tu campaña móvil

Esta guía te explica cómo configurar la integración de Appcharge.

## Configura la integración

**Requisitos previos:**

* Tienes una cuenta de Appcharge activa. Si no es así, ponte en contacto con el partner (Appcharge) y abre una cuenta con ellos antes de configurar la integración.
* Tu cuenta de AppsFlyer incluye los permisos necesarios para configurar integraciones de partners.

**Configurar la integración de ASA**

1. En la pestaña de **Integración** selecciona la aplicación para la integración y haz clic en **Activar partner**  
   **Nota:** El selector debe estar encendido <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado) mientras</Anchor> trabajes con el partner.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. Mantenlo activado mientras trabajes con el partner.
5. Completa la configuración en la pestaña **Integración**, como se describe a continuación.

**Para activar o editar la integración:**

Busca al partner y selecciónalo.

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

#### Activar partner

En tu primera visita, tendrás que activar el conmutador **Activar partner** para configurar la integración. El conmutador debe estar activado mientras trabajes con Appcharge. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación del partner</Anchor>.

#### Privacidad avanzada

Para las aplicaciones de iOS, aparece el selector de <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad avanzada</Anchor>. Cuando se activa, limita el intercambio de identificadores de usuario con el partner. Ten en cuenta que cuando el conmutador <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad avanzada agregada</Anchor> toggle se activa en la Configuración de la aplicación, **Privacidad avanzada (para iOS 14.5+ y versiones posteriores)** se activa y se bloquea de forma predeterminada.

#### Postbacks predeterminados

AppsFlyer envía postbacks predeterminados a Appcharge después de las instalaciones de los usuarios. Usa esta sección para <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">definir estos postbacks</Anchor>.

* **Desactivado:** Los postbacks de instalación no se envían a Appcharge.  
   **Nota:** La integración de Appcharge con AppsFlyer no requiere el envío de postbacks de instalación. Por lo tanto, se recomienda configurarlo como Desactivado.
* **Todas las fuentes de medios, incluidas las orgánicas:** Los postbacks de instalación se envían para los eventos atribuidos a cualquier partner y para eventos orgánicos.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

#### Postbacks de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a tus partners mediante postbacks.

![xsolla-af-login-3.jpg](https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg)

1. Activa los **postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para añadir un evento de SDK o un evento de servidor a servidor a la lista.
3. Completa los siguientes parámetros:
4. Haz clic en **Guardar integración**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Los enlaces de atribución no están disponibles para Appcharge.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

Los datos de costos no se admiten en la integración con Appcharge.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos publicitarios">

Los datos de ingresos publicitarios no se admiten en la integración con Appcharge.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Appcharge.

</Accordion>

## Identificar eventos de Appcharge en AppsFlyer

Appcharge envía a AppsFlyer dos tipos de eventos in-app móviles:

* `ac_af_purchase` - Cuando un usuario completa una compra correctamente
* `ac_af_refund` - Cuando se completa un reembolso

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

Soporte para PC/consolas: la integración de AppsFlyer con Appcharge no admite aplicaciones para PC/consolas.

</Accordion>

Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>.

<div data-zendesk-anchors="integration-types=acerca-de-appcharge h_01J3DB8MCNQKKKCV1M39KN7Q0H=acerca-de-appcharge setting-up-appcharge=configura-la-integraci%C3%B3n h_01HST42K52JKQ70F7Y5PHDZAZ5=configura-la-integraci%C3%B3n h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=activar-partner h_01HST42K52RCTSGRNRCJ1C70NP=activar-partner advanced-privacy=privacidad-avanzada h_01HST42K52BBJ6JS5KM0WCN6CF=privacidad-avanzada default-postbacks=postbacks-predeterminados h_01HST47F5BXWV5W8BNHS9M2MTN=postbacks-predeterminados inapp-event-postbacks=postbacks-de-eventos-in-app h_01H9FKEAV3GG6X17X3NCCSWJAS=postbacks-de-eventos-in-app h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab identifying-appcharge-events-in-appsflyer=identificar-eventos-de-appcharge-en-appsflyer h_01JMHXRGB60RVZ399FNHS18ZHZ=identificar-eventos-de-appcharge-en-appsflyer h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations" />

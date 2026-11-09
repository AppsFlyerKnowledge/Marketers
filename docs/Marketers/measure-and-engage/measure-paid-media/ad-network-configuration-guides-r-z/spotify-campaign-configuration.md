---
title: Configuración de la campaña de Spotify
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
  created_at: '2020-11-05T07:36:01Z'
  edited_at: '2026-08-12T12:16:04Z'
  id: 360015074677
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/360015074677
---
> **De un vistazo:** Spotify, un partner integrado de ad network de AppsFlyer, utiliza su solución mejorada de publicidad móvil para cultivar campañas estratégicas, escalables e inteligentes que satisfacen las necesidades de los usuarios móviles. En Spotify, los clics se generan cuando un usuario hace clic en un botón de CTA mientras ve o escucha un anuncio.

<Image align="center" alt="Spotify_Full_Logo_RGB_Black.png" src="https://files.readme.io/e3908e19ec71c506c2ff135652cea6529f128743d8284c02c1a481f24485b3a6-small-37818004235409.png" width="53.91%" />

<div id="setting-up-spotify" />

## Configuración de Spotify

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

Saber más sobre el <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">encabezado de la ventana de configuración del partner</Anchor>.

Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">reglas de activación del partner</Anchor>.

<div id="important" />

> 🚧 **Importante**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">configuración general</Anchor> en la pestaña Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales.**

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución view-through**

Si quieres atribuir instalaciones view-through de Spotify, activa este interruptor. Para configurar la ventana de lookback view-through, ve a la pestaña del enlace de atribución (se describe a continuación).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Spotify tiene una integración de servidor a servidor con AppsFlyer, por lo que no se utilizan enlaces de atribución para la medición de campañas. Cuando seleccionas tu aplicación como fuente de medición de conversiones durante la configuración de la campaña de Spotify, la integración de AppsFlyer se activará automáticamente y Spotify enviará a AppsFlyer datos de impresiones y clics con los identificadores necesarios para la atribución.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos no está disponible para Spotify.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no están disponibles para Spotify.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Spotify, tanto si el partner actúa como ad network, como agencia o incluso como ambas. Ten en cuenta que, aunque la atribución esté deshabilitada para Spotify, la pestaña de permisos está activa y puedes otorgar el control a Spotify.

Después de habilitar la concesión de permisos a Spotify, puedes agregar miembros del equipo para otorgarles acceso a los datos según los permisos seleccionados.  
Los permisos solo se pueden otorgar a empleados de Spotify que tengan una cuenta de miembro del equipo de ad network en AppsFlyer.  
**Para otorgar permisos a miembros del equipo de ad network:**

1. Haz clic en **Añadir miembro del equipo.**
2. Ingresa el correo electrónico del miembro del equipo de la ad network.
3. Haz clic en **Añadir**.

<div id="important-1" />

> 🚧 **Importante:**
>
> * Cuando otorgas a Spotify permisos para configurar la integración y cambiar los postbacks de eventos in-app, permites que pueda acceder potencialmente a todos los eventos de atribución, incluido el tráfico orgánico y no orgánico de todas las fuentes de medios.
> * Los cambios que realiza Spotify anulan la configuración actual, aunque la haya establecido el anunciante.

Estos son los tipos de permisos que los anunciantes pueden otorgar a Spotify:

* **Permitir configurar la integración**: permite que el partner configure la pestaña Integración (excepto los postbacks de eventos in-app).
* **Permitir configurar los postbacks de eventos in-app** - permite que el partner configure la asignación de postbacks de eventos in-app para sí mismo en la pestaña de integración.
* **Permitir el acceso a tu reporte de retención** - solo a los datos de retención del propio partner.
* **Permitir el acceso a tus datos agregados de usuarios fieles** - solo a los datos de usuarios fieles del propio partner.
* **Permitir el acceso a tus datos agregados de eventos in-app** - solo a los datos de eventos in-app del propio partner.
* **Permitir el acceso a tus datos agregados de ingresos** - solo a los datos de ingresos atribuidos al partner.
* **Permitir el acceso a tu dashboard de Protect360 & raw data mediante API** - solo a los datos de Protect360 del propio partner, siempre que la función esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-spotify=configuraci%C3%B3n-de-spotify h_01HJS1DB7YV8T6RNXH1JRNTGDN=configuraci%C3%B3n-de-spotify h_01HJS1DB7YKBY0Q7GY7QT9DHKZ=importante h_01HJS1DB7YQKM7DRR0MJGHX95G=integration-tab general-settings=configuraci%C3%B3n-general h_01HJS1DB7YEQZ7JQ0T2NWFBQBM=configuraci%C3%B3n-general h_01HJS1DB7YHN0PCMFWQ9SZKE27=attribution-link-tab h_01HJS1DB7ZVSQCYJZENWJ9G77H=cost-tab h_01HJS1DB7Z03PTQSQB0JVJEFY0=ad-revenue-tab h_01HJS1DB7Z6CBDQFVNC75X2Z6Z=permissions-tab h_01HJS1DB7ZPZET71JAZ8E4CZ7S=importante-1" />

---
title: Integración de Google Analytics—Discrepancias
metadata:
  keywords:
    - Analytics
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
  created_at: '2021-12-07T13:38:17Z'
  edited_at: '2026-08-12T12:00:09Z'
  id: 4413026674833
  locale: es
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/es/articles/4413026674833
---
> **De un vistazo:** Comprende las discrepancias que pueden producirse entre AppsFlyer y Google Analytics.

## Discrepancias en los datos entre AppsFlyer y Google Analytics

A continuación se indican los motivos de las discrepancias entre AppsFlyer y Google Analytics.

<div id="high-volume-of-nonconsenting-ios-145-users" />

<Accordion title="Alto volumen de usuarios de iOS 14.5+ que no dan su consentimiento">

Cuando <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">AAP está habilitado para tu aplicación</Anchor>, AppsFlyer no envía postbacks a Google Analytics de usuarios de iOS 14.5+ que no dan su consentimiento. Si tu aplicación tiene un gran número de estos usuarios, habrá una discrepancia entre los dashboards de AppsFlyer y Google Analytics.

</Accordion>

<div id="customer-user-id" />

<Accordion title="ID de usuario del cliente">

Google Analytics asocia los eventos por ID de usuario del cliente. El ID de usuario del cliente que AppsFlyer envía de forma predeterminada es el GAID o el IDFA.

Por lo tanto, Google Analytics considera que los usuarios que vuelven a instalar la aplicación (usuarios que la instalan, la desinstalan y luego la vuelven a instalar) son los mismos usuarios.

> 📄 **Ejemplo**
>
> Un usuario instala tu aplicación y luego la desinstala. A continuación, el usuario vuelve a instalar la aplicación a través de una campaña de retargeting dentro de la ventana de reatribución.
>
> Google Analytics considera a este usuario como el mismo usuario. En User Explorer de Google Analytics, este usuario tiene todo lo siguiente listado:
>
> * instalación normal
> * evento in-app normal
> * instalación reatribuida
> * evento in-app reatribuido
>
> AppsFlyer, por otro lado, considera a este usuario como dos usuarios diferentes:
>
> * Un usuario que proviene de una campaña de UA
> * Un usuario que proviene de una campaña de retargeting

Además, pueden surgir discrepancias si implementas tanto el SDK de GA como el SDK de AppsFlyer.

</Accordion>

<div id="time-zone-differences" />

<Accordion title="Diferencias en la zona horaria">

Si la zona horaria de tu dashboard de GA es distinta de la zona horaria de tu aplicación en AppsFlyer, es posible que los datos no coincidan.

> 📄 **Ejemplo**
>
> El dashboard de tu aplicación está configurado en GMT +13 y tu dashboard de GA está configurado en GMT. Esto significa que el dashboard de tu aplicación va un día por delante del dashboard de GA.
>
> Por lo tanto, los datos que aparecen en el dashboard de GA para el 2 de marzo solo aparecen en el dashboard de tu aplicación si eliges el 3 de marzo en el filtro de intervalo de fechas.

</Accordion>

<div id="duplicate-events" />

<Accordion title="Eventos duplicados">

Si los eventos se producen con poca diferencia entre sí, tanto AppsFlyer como Google Analytics podrían descartarlos como eventos duplicados. El <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#how-does-appsflyer-handle-event-deduplication">mecanismo de deduplicación de eventos</Anchor> de AppsFlyer es diferente del que utiliza Google Analytics.

Como AppsFlyer y Google Analytics deduplican los eventos de forma distinta, pueden producirse discrepancias en los datos de eventos.

</Accordion>

<div id="session-count" />

<Accordion title="Recuento de sesiones">

AppsFlyer contabiliza una sesión cada vez que se inicia la app o vuelve al primer plano. Google Analytics contabiliza las sesiones según el CID (ID de usuario del cliente) y la actividad.

> 📄 **Ejemplo**
>
> Un usuario inicia tu app, realiza algunas acciones y luego envía la app a segundo plano. Después, el usuario repite el proceso 4 veces, cada vez con un intervalo de unos 5 minutos.
>
> Para AppsFlyer, esto cuenta como 5 sesiones diferentes. Sin embargo, para Google Analytics esto cuenta como una sola sesión.

Para saber más sobre cómo AppsFlyer y Google Analytics calculan las sesiones, consulta los recursos que aparecen a continuación.

1. <Anchor target="_blank" href="/marketers/es/docs/measure-sessions">Cómo contabiliza AppsFlyer las sesiones</Anchor>
2. <Anchor target="_blank" href="https://support.google.com/analytics/answer/2731565?hl=en">Sesiones de Google Analytics</Anchor>

</Accordion>

<div id="google-analytics-views-and-filters" />

<Accordion title="Vistas y filtros de Google Analytics">

Google Analytics te permite crear distintas vistas y aplicarles diferentes filtros. Cuando compares datos de AppsFlyer y Google Analytics, asegúrate de verlos en la vista ***All Web Site Data*** de Google Analytics.

</Accordion>

<div data-zendesk-anchors="discrepancies-in-data-between-appsflyer-and-google-analytics=discrepancias-en-los-datos-entre-appsflyer-y-google-analytics h_01HDP3G48R2XXEQDEAAJYGR9V9=discrepancias-en-los-datos-entre-appsflyer-y-google-analytics h_01HDP3G48RQD3EW0DTRE2252JF=high-volume-of-nonconsenting-ios-145-users h_01HDP3G48RPWDY7ZRG9HM1F5AR=customer-user-id h_01HDP3G48RMGSJSWQDSKW5DXD9=ejemplo h_01HDP3G48R2JWF3Y23011NDCAN=time-zone-differences h_01HDP3G48RXFWZX4FQ0V2ZE44D=ejemplo-1 h_01HDP3G48RHT7PWSWZZAG27CP0=duplicate-events h_01HDP3G48R1044364MF96QX41E=session-count h_01HDP3G48RHQ3VG6N4HTT1KJFS=ejemplo-2 h_01HDP3G48R9571AS0WH7TWQWJP=google-analytics-views-and-filters" />

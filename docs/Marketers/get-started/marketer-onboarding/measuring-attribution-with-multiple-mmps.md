---
title: Medición de la atribución con múltiples MMPs
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-07-27T08:29:19Z'
  edited_at: '2026-08-12T12:05:24Z'
  id: 17316973509393
  locale: es
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/es/articles/17316973509393
---
> **En resumen:** Descubre qué fuentes de medios son capaces de medir la atribución cuando se trabaja con múltiples MMPs simultáneamente para que puedas comparar los resultados de atribución entre AppsFlyer y tu otro MMP.

<div id="overview" />

## Visión general

Al buscar migrar de otro MMP a AppsFlyer, los anunciantes pueden querer comparar simultáneamente ambas mediciones de MMP con las mismas fuentes de medios y campañas. Para ello, se deben cumplir los siguientes requisitos:

* La aplicación probada debe tener **ambos SDK MMP integrados**
* Las fuentes de medios deben **configurarse para soportar la atribución con dos MMPs**

Sin embargo, no todas las fuentes de medios soportan la medición con más de un MMP.  

<div id="details-and-limitations-of-media-source-measurement" />

## Detalles y limitaciones de la medición de fuentes de medios

A continuación se muestran los detalles y las limitaciones de la medición de fuentes de medios cuando se trabaja con múltiples MMPs simultáneamente.

<div id="self-reporting-networks" />

### Redes de autorreporte

| nombres de SRN reservados | Detalles y limitaciones | Soporta medición |
| --- | --- | --- |
| Anuncios en la búsqueda de Apple | ASA soporta múltiples mediciones de MMPs sin limitación. Cuando hay una solicitud de llamada a la API de múltiples MMPs, los datos se envían a los MMPs correspondientes. | ✓ |
| DV360 (GMP) | Son posibles múltiples MMPs, pero la configuración de la campaña debe tener elementos de línea separados para cada seguimiento de foco (Link ID). | ✓ |
| Anuncios de Google | Google Ads admite múltiples mediciones de MMP:<ul><li>Los anunciantes pueden vincular varios Link IDs de MMP a una sola cuenta de Google Ads y recibir postbacks de cada MMP</li><li>Google Ads puede recibir postbacks de múltiples MMPs</li><li>Se pueden medir rendimientos de múltiples MMP</li></ul>**Nota:** Una vez que los datos fluyen en el nuevo MMP, Google Ads recomienda detener la integración existente. | ✓ |
| Anuncios de Meta | Los Meta Ads reciben solicitudes de datos de múltiples MMPs. Sin embargo, recomiendan **no** tener más de un MMP por las siguientes razones:<ul><li>Los Meta Ads solo pueden manejar la deduplicación en instalaciones, no para eventos. Por lo tanto, los eventos deben enviarse solo desde un MMP</li><li>Al insertar varios SDKs desde MMPs, existe una probabilidad muy alta de problemas y errores secundarios durante el proceso de deduplicación.</li><li>Cuando se envía una gran cantidad de datos a los Meta Ads, se pueden introducir datos duplicados en sus sistemas de optimización y medición.</li></ul>Por lo tanto, la atribución múltiple de MMP puede ser soportada sólo por un corto plazo. | Con limitación |
| Snapchat | Es posible transferir datos entre Snapchat y múltiples MMPs. Sin embargo, se recomienda minimizar el período de migración superpuesto. Al recibir múltiples datos de MMP, no hay opción para optimizar seleccionando un MMP específico. Esto significa que la optimización se realiza para ambos MMPs y que es muy probable que los datos se dupliquen. | Con limitación |
| TikTok para empresas | El envío de postbacks a TikTok for Business solo es compatible con un MMP. Al migrar desde otro MMP, para permitir que AppsFlyer atribuya conversiones a TikTok for Business, primero tendrás que desactivar los postbacks del otro MMP y luego configurar AppsFlyer. | X |
| Anuncios X | X Ads no admite la integración múltiple de MMP | X |

<div id="skan" />

### SKÁN

El envío de <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#aspectos-básicos-del-skan-conversion-studio">postbacks de conversión SKAN</Anchor> **no es compatible con múltiples MMPs**. Sólo un SDK puede activar el envío de postbacks SKAN a los partners. Esto significa que cuando se integra más de un SDK en tu aplicación, los postbacks de SKAN solo se envían a un SDK.

<div id="non-srn-ad-networks" />

### Redes de publicidad no SRN

Los enlaces de atribución MMP registran las contrataciones de los usuarios en redes publicitarias que no son SRN y, posteriormente, se utilizan para atribuir las contrataciones que se convierten en instalaciones reales. Para habilitar la atribución de múltiples MMPs simultáneamente, la red de anuncios debe asegurarse de que se cumplan los siguientes requisitos:

| Requerimiento de red de anuncios | Detalles |
| --- | --- |
| Los datos para una única contratación deben enviarse a ambos MMPs | <ul><li>**Clics:** Como los enlaces de atribución redirigen a los usuarios a la tienda de aplicaciones, solo se puede usar un enlace de atribución. Recomendamos continuar usando el enlace de atribución del MMP existente mientras <Anchor target="_blank" href="/partners/es/docs/redirecting-users-to-the-app-store#descripción-general">envía datos de atribución de clics a AppsFlyer</Anchor>.</li><li>**Impresiones:** Como las impresiones no redireccionan a los usuarios a la tienda de aplicaciones, la red de anuncios debe enviar datos de impresión a ambos MMPs.</li></ul> |
| Los postbacks de instalación recibidos deben ser deduplicados | Las redes publicitarias reciben postbacks de instalación de ambos MMPs. Para evitar cargos dobles, la red de anuncios debe deduplicar uno de estos postbacks. |
| Los postbacks de eventos in-app recibidos deben deduplirse | Cuando cada uno de los MMPs está configurado para enviar postbacks de eventos in-app, las redes publicitarias reciben postbacks de eventos in-app de ambos MMPs. Para evitar una doble atribución que resulte en cargos dobles, la red de anuncios debe deduplicar uno de estos postbacks. Si la red de anuncios no puede deduplicar las postbacks dobles de eventos in-app, asegúrate de que los postbacks de eventos in-app estén configurados en un solo MMP. |

<div id="owned-media" />

### Medios propios

Al igual que con las redes publicitarias no SRN, la atribución de instalaciones desde medios propios requiere el uso de enlaces de atribución MMP. Sin embargo, para algunos tipos de medios propios, como listas de correo electrónico, SMS o códigos QR, los MMPs pueden enviar datos en una sola contratación una sola vez. La solución de <Anchor target="_blank" href="/marketers/es/docs/convert-your-mobile-web-visitors-to-app-users">atribución móvil web-to-app</Anchor> de AppsFlyer permite medir las **instalaciones provenientes de un sitio web o una landing page**. La ventaja de utilizar medios propios para comparar la atribución de MMP es el hecho de que no se necesita ninguna instalación o deduplicación de eventos.

<div id="avoiding-attribution-discrepancies" />

## Evita discrepancias de atribución

Cuando los MMPs utilizan diferentes modelos de atribución para medir el tráfico, puede dar lugar a discrepancias. Puedes minimizarlas con estos pasos:

* Asegúrate de que ambos MMPs utilicen la misma zona horaria para la aplicación. Aquí te mostramos cómo <Anchor target="_blank" href="/marketers/es/docs/changing-app-time-zone-settings">configurar la zona horaria de la aplicación en AppsFlyer</Anchor>.
* Para no SRN y medios propios: Asegúrate de configurar el enlace de atribución utilizando los mismos valores de parámetro. Por ejemplo, establece la misma ventana lookback en ambos MMPs.
* Al comparar los datos en los dashboards o reportes de MMPs, asegúrate de comparar los mismos criterios, como el tráfico del mismo rango de fechas y la posición geográfica.

<div data-zendesk-anchors="ability-to-measure-with-multiple-mmps=visi%C3%B3n-general 01H7TP9P86DE0J04VHXJYKE3PA=visi%C3%B3n-general details-and-limitations-of-media-source-measurement=detalles-y-limitaciones-de-la-medici%C3%B3n-de-fuentes-de-medios 01H81ANMGMEKCZCS2FNBY67321=detalles-y-limitaciones-de-la-medici%C3%B3n-de-fuentes-de-medios selfreporting-networks=redes-de-autorreporte 01H81APGNBGCMREZVFXJW9KN6H=redes-de-autorreporte skan=sk%C3%A1n 01H7TP9P86YQ75N0XFY7EW2JHQ=sk%C3%A1n nonsrn-ad-networks=redes-de-publicidad-no-srn 01H7TP9P86TEWC47MZZVQ1965K=redes-de-publicidad-no-srn owned-media=medios-propios 01H7W2YTXYMAEN403WCHYH8G7W=medios-propios avoiding-attribution-discrepancies=evita-discrepancias-de-atribuci%C3%B3n 01H7YVHVW3YY8XY8GHQX1B0WZN=evita-discrepancias-de-atribuci%C3%B3n" />

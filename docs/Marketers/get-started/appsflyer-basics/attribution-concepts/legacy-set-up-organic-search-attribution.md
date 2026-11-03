---
title: '[Legacy] Configura la atribución de búsqueda orgánica'
deprecated: true
metadata:
  keywords:
    - Android
    - organic
    - keyword
    - search
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-28T06:35:08Z'
  edited_at: '2026-08-12T11:56:22Z'
  id: 210195193
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/210195193
---
> **En resumen:** Obtén datos detallados de atribución de búsqueda orgánica para que puedas optimizar las conversiones orgánicas. <Anchor target="_blank" href="/marketers/es/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Consulta nuestro método actualizado de atribución de búsqueda orgánica</Anchor>.

> 🚧 **Importante:**
>
> Te recomendamos implementar nuestro <Anchor target="_blank" href="/marketers/es/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">método actualizado de atribución de búsqueda orgánica</Anchor>.

## Atribución de búsqueda orgánica

La atribución de búsqueda orgánica es una innovadora solución de atribución que permite a los clientes de AppsFlyer atribuir las aperturas de aplicaciones móviles de usuarios que ya tienen tu aplicación instalada a la búsqueda orgánica.

Usa la atribución de búsqueda orgánica para atribuir a estos usuarios existentes que vuelven a interactuar con tu aplicación después de una búsqueda web orgánica.

#### FLUJO

![Organic_SEO_attribution_flow.png](https://files.readme.io/1772808df9d9e521204153d9f0689b3f9f156dd8c0ab8555673b1d321f28aece-15320495862545.png)

1. Un usuario busca un término (por ejemplo, «zapatos de hombre») en el motor de búsqueda de su navegador móvil (Google, Bing, etc.). El motor de búsqueda muestra varios resultados en los que se puede hacer clic.
2. Tu desarrollador web asigna algunos de estos resultados de búsqueda para que abran tu aplicación móvil mediante Android App Links y iOS Universal Links. Si un usuario tiene la aplicación instalada, cuando hace clic en el resultado de la búsqueda, la aplicación se abre (sin redireccionar primero a una tienda de aplicaciones).
3. Al iniciar la aplicación, AppsFlyer recopila la información requerida y puede atribuir la apertura de la aplicación a la fuente de medios que hayas configurado (por ejemplo, search\_engine).
4. Si el usuario no tiene la aplicación instalada, se envía a una landing page web, donde puedes usar cualquiera de varias soluciones de la web a la aplicación de AppsFlyer (como Smart Banners, Smart Script o códigos QR) para redireccionarlo y atribuirlo.

**Para configurar la atribución**:

1. Indica a los desarrolladores de apps de Android e iOS de tu aplicación cuál es el dominio asociado a tu aplicación. En Android, esto significa el dominio con App Links de Android configurados para abrir la aplicación a los usuarios existentes. Y en iOS, esto significa que el dominio con Universal Links está configurado para abrir la aplicación a los usuarios existentes.
2. Indica a los desarrolladores qué valor deben usar para el parámetro de fuente de medios (`pid`). Por ejemplo: search\_engine.
3. Indica a tus desarrolladores que sigan las instrucciones de atribución de búsqueda orgánica para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_organic_search_attr">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_organic_search_attr">iOS</Anchor>.  
   Las instalaciones procedentes de búsquedas orgánicas se mostrarán con el valor de fuente de medios que hayas elegido. Por ejemplo: search\_engine.

**Consejo!** Más información sobre el <Anchor target="_blank" href="https://gs.statcounter.com/search-engine-market-share">desglose del uso de motores de búsqueda por geolocalización</Anchor>

<div data-zendesk-anchors="organic-search-attribution=atribuci%C3%B3n-de-b%C3%BAsqueda-org%C3%A1nica flow=flujo" />

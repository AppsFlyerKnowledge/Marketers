---
title: >-
  Configura la atribución de re-engagement de búsqueda orgánica (SEO) y
  respuestas orgánicas de IA (AEO)
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-07T13:34:36Z'
  edited_at: '2026-09-16T00:09:20Z'
  id: 15123194526353
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/15123194526353
---
> **At a glance:** Obtén datos de atribución detallados sobre los re-engagements (usuarios que ya tienen tu app instalada) procedentes de motores de búsqueda orgánicos y motores de respuestas de IA, para que puedas optimizar tus conversiones de búsqueda orgánica y las impulsadas por IA.

## Descripción

La atribución de re-engagement de búsqueda orgánica (SEO) y respuestas orgánicas de IA (AEO) es una solución de atribución que permite a los clientes de AppsFlyer atribuir los re-engagements (es decir, las aperturas de aplicaciones móviles por parte de usuarios que ya tienen tu app instalada) a varios motores de búsqueda orgánica y motores de respuestas de IA.

Tener acceso a estos datos únicos es muy útil para los equipos de SEO (optimización para motores de búsqueda) y AEO (optimización para motores de respuestas), y proporciona información muy valiosa sobre sus esfuerzos de SEO y AEO.

### Flujo

![Diagrama que muestra el flujo de atribución de búsqueda orgánica, desde que un usuario hace clic en un resultado de búsqueda hasta que se abre la aplicación o el usuario llega a una página web](https://files.readme.io/4b33060cfa30a4e2786c4a3a213ca41223ae276d63c97ab7c2cb5a997a4b010c-16540659217809.png)

El flujo de atribución de búsqueda orgánica funciona de la siguiente manera:

1. Un usuario busca un término en el motor de búsqueda de su navegador móvil (Google, Bing, etc.). El motor de búsqueda muestra varios resultados en los que se puede hacer clic.
2. Tu desarrollador web asigna algunos de estos resultados de búsqueda para que abran tu aplicación móvil mediante Android App Links y iOS Universal Links. Si un usuario tiene la aplicación instalada, cuando hace clic en el resultado de la búsqueda, la aplicación se abre (sin redireccionar primero a una tienda de aplicaciones).
3. Al iniciar la aplicación, AppsFlyer recopila la información requerida y puede atribuir la apertura de la aplicación al motor de búsqueda del usuario.
4. Si el usuario no tiene la app instalada, se le envía a una página de destino web, donde puedes usar cualquiera de las soluciones Web-to-app de AppsFlyer (como Smart Banners, Smart Script o QR code) para redirigirlo y atribuirlo.

## Configuración

**Requisitos previos**:

* SDK de AppsFlyer para Android V6.12.1
* SDK de AppsFlyer para iOS V6.12.1

**Para configurar la atribución de búsqueda orgánica**:

1. Pide a tus desarrolladores que habiliten la apertura de la aplicación siguiendo las instrucciones de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android App Links</Anchor> y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#app-opening-methods">iOS Universal Links</Anchor> (usando el dominio de nivel superior de la aplicación).
2. En AppsFlyer, en el menú lateral, selecciona **Configuración** > <Anchor target="_blank" href="/marketers/es/docs/app-settings">Configuración de la aplicación</Anchor> y activa:
   * **Atribución de re-engagement para aplicación móvil de SEO (búsqueda orgánica) y AEO.**
   * **la atribución de re-engagement**.

> 📘 **Note**
>
> **Nota para tu desarrollador**
>
> performOnDeepLinking consume y resuelve de forma forzada la URL de Deep Linking cuando se invoca. Esto evitará que la función de atribución SEO funcione correctamente y hará que la atribución no se reporte a la fuente de medios SEO correcta.

## Disponibilidad de datos

Los datos están disponibles de la siguiente manera:

* En los datos agregados de dashboards y reportes, el campo `media_source` indica desde qué motor de búsqueda llegó el usuario. Ejemplo: `google_organic_seo`.
* En reportes de raw data.
  * El campo `media_source` indica desde qué motor de búsqueda llegó el usuario. Ejemplo: `google_organic_seo`.
  * El campo `http_referrer` incluye la URL completa de la página de resultados de la búsqueda, desde la cual el usuario fue enviado a la app o landing page móvil.
  * El campo `channel` tiene el valor `seo` para el tráfico orgánico de motores de búsqueda, o `aeo` para el tráfico de motores de respuestas de IA.

## Información adicional

<Accordion title="Lista de motores de búsqueda compatibles">

La atribución de búsqueda orgánica admite los siguientes motores de búsqueda:

* Google
* Bing
* Yahoo
* Preguntar
* DuckDuckGo
* Yandex
* Naver
* Daum
* Baidu
* Ecosia
* Coccoc
* Sogou
* Yahoo Japón

> 📘 **Note**
>
> Para otros motores de búsqueda, usa la solución de atribución de búsqueda orgánica heredada (requiere la entrada del desarrollador).
>
> En los dashboards y los reportes de datos, los motores de búsqueda se muestran como `<search engine>`\_organic\_seo. Por ejemplo: google\_organic\_seo.

</Accordion>

<Accordion title="Lista de motores de respuestas de IA compatibles">

La atribución de búsqueda orgánica también es compatible con los siguientes motores de respuestas de IA:

* ChatGPT
* Claude
* Perplexity
* Manus
* Copilot
* Géminis
* Grok
* Deepseek

> 📘 **Note**
>
> En los dashboards y los reportes de datos, los motores de respuestas de IA se muestran como `<motor de IA>`\_organic\_aeo. Por ejemplo: chatgpt\_organic\_aeo.

</Accordion>

<Accordion title="PREGUNTAS FRECUENTES">

<Accordion title="¿La atribución de SEO orgánica incurre en alguna tarifa adicional?">

No, esta función está incluida en tu suscripción.

</Accordion>

<Accordion title="¿Las conversiones de SEO orgánicas cuentan como parte de mi paquete?">

Sí, igual que las conversiones no orgánicas.

</Accordion>

<Accordion title="¿Puedo personalizar el nombre de la fuente de medios de SEO?">

N.º AppsFlyer determina el nombre de la fuente de medios SEO orgánica y no se puede personalizar por el momento.

</Accordion>

<Accordion title="Si el motor de búsqueda muestra un botón de instalación junto a los resultados de búsqueda orgánica y el usuario hace clic en él y navega a la tienda de aplicaciones, ¿AppsFlyer atribuye la instalación al motor de búsqueda?">

N.º En este caso, AppsFlyer no puede recopilar la información requerida para la atribución. La atribución de búsqueda orgánica requiere que la aplicación ya esté instalada.

</Accordion>

<Accordion title="¿Están disponibles los datos de palabras clave?">

Los datos de palabras clave no están disponibles a través de esta solución de atribución de búsqueda orgánica. Sin embargo, hay raros casos en los que los datos de palabras clave están disponibles para Android. Consulta <Anchor target="_blank" href="/marketers/es/docs/evaluate-keyword-data#palabras-clave-de-android">la disponibilidad de los datos de palabras clave de Android</Anchor>.

</Accordion>

<Accordion title="¿Se admite la atribución de búsquedas orgánicas en un flujo de instalación?">

Sí, puedes ver desde qué página llegaron a tu sitio web los usuarios que instalaron tu aplicación.

Smart Script lo hace de la siguiente manera:

* Recopila el dominio de la URL de la página, denominado referente web
* Crea un `pid` relevante (que después se muestra como la fuente de medios) en función del origen específico del usuario
* Lo asigna a una clave de parámetro que elijas, como `af_sub1`, en la URL saliente

Para saber cómo configurar Smart Script para recopilar el referente web, consulta la <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#seo-referrer-mapping">guía de configuración de OneLink Smart Script V2</Anchor>.

</Accordion>

</Accordion>

<Accordion title="Características y limitaciones">

| Rasgo | Description |
| --- | --- |
| Navegadores | La atribución de búsqueda orgánica no es compatible con:<ul><li>Firefox en Android</li><li>Cualquier navegador excepto Safari en iOS.</li></ul> |
| Aplicaciones SwiftUI (iOS) | La atribución de búsqueda orgánica no es compatible con las aplicaciones de iOS creadas con SwiftUI. |
| Ventana de reenganche | La búsqueda orgánica tiene una ventana fija de re-engagement de 30 días. El tamaño de la ventana no se puede modificar. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#ventanas-de-inclusión">la guía de atribución de retargeting</Anchor>. |

</Accordion>

<div data-zendesk-anchors="organic-search-attribution=descripci%C3%B3n h_01H9G0W21SRDC6ZSR1E8AQFZFC=descripci%C3%B3n flow=flujo h_01H9G0W21S4RB56PNV9DAYZPB2=flujo setup=configuraci%C3%B3n h_01H9G0W21S6Z0A5QXC52KSYVQS=configuraci%C3%B3n data-availability=disponibilidad-de-datos h_01H9G0W21S7KVJ2Z5DRPCHZF4Z=disponibilidad-de-datos additional-information=informaci%C3%B3n-adicional h_01H9G0W21SERW2HC44KD77FNCG=informaci%C3%B3n-adicional" />

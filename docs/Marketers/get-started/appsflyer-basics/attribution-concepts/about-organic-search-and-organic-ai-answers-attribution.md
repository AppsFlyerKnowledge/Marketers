---
title: >-
  [WIP] Acerca de la atribución de la búsqueda orgánica y de las respuestas
  orgánicas de IA
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
  created_at: '2026-11-01T17:06:19Z'
  edited_at: '2026-11-02T13:24:18Z'
  id: 52556274395537
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/52556274395537
---
> **At a glance:** Usa la atribución de la búsqueda orgánica (SEO) y de las respuestas orgánicas de IA (AEO) para ver qué motores de búsqueda y motores de respuestas de IA envían tráfico no pagado a tu sitio web y aplicación. Atribuye a ellos las conversiones web, las instalaciones de la app y los re-engagements de la app.

## Acerca de la atribución de SEO y AEO

Un usuario busca en Google o le hace una pregunta a ChatGPT y, después, hace clic en un resultado que lo lleva a tu sitio web. AppsFlyer atribuye al motor de búsqueda o al motor de respuestas de IA las visitas y conversiones en tu sitio web, las instalaciones de la app y las aperturas de la app.

## Recorridos compatibles

Cada recorrido empieza cuando un usuario busca en un motor de búsqueda compatible o le hace una pregunta a un motor de respuestas de IA compatible. Si la respuesta incluye un enlace no pagado y el usuario hace clic en él, se da uno de estos tres recorridos:

| Trayectoria | Qué mide AppsFlyer | Implementación necesaria |
| --- | --- | --- |
| El usuario llega a tu sitio web | Visitas web y conversiones web, como registros y compras | SDK de atribución web de AppsFlyer o integración de servidor a servidor (S2S) |
| El usuario llega a tu sitio web y luego toca un botón de descarga que lo lleva a la tienda de aplicaciones | Instalaciones de aplicaciones | SDK móvil de AppsFlyer y Smart Script versión 2.10.3 o posterior, con **la fuente de medios para instalaciones de búsqueda orgánica** activada |
| La persona usuaria llega a tu sitio web y va directamente a la app que ya tiene instalada | Re-engagement de la app (aperturas de la app) | SDK de AppsFlyer para Android e iOS versión 6.12.1 o posterior, además de Android App Links e iOS Universal Links |

## Caso de uso 1: medición web

Atribuye las visitas al sitio web y las conversiones al motor de búsqueda o motor de respuestas con IA del que procede la persona usuaria.

**Pré-requisitos:**

* SDK de atribución web de AppsFlyer o integración server-to-server (S2S). Saber más en <Anchor target="_blank" href="/marketers/es/docs/web-performance-measurement-overview">Medición del performance web - Vista general</Anchor>.

**Cómo funciona:**

1. Una persona usuaria hace clic en un resultado de búsqueda no pagado o en un enlace de respuesta con IA y llega a tu sitio web.
2. El SDK de atribución web o la integración S2S leen el referente web, el campo que muestra de dónde proviene la persona usuaria. AppsFlyer atribuye la visita web a la fuente de medios de SEO o AEO correspondiente.
3. Si más tarde la persona usuaria completa una acción relevante, como registrarse o hacer una compra, AppsFlyer atribuye el evento a ese motor de búsqueda o motor de respuestas con IA.

<Image alt="Google Chrome 2026-11-01 19.17.00.png" src="https://files.readme.io/aa441d266e07d4ad69277455e6f36b19b5127f1748cd94bb4b35bca6a912555b-52588329956753.png" width="2266px" />

Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/about-traffic-source-resolution#paso-2-resolución-de-la-fuente-de-medios">resolución de la fuente de tráfico</Anchor>.

## Caso de uso 2: medición de la instalación de la app

Atribuye las instalaciones de la app al motor de búsqueda o motor de respuestas con IA que envió a la persona usuaria a tu sitio web.

**Pré-requisitos:**

* SDK móvil de AppsFlyer
* Smart Script de AppsFlyer versión 2.10.3 o posterior, con la **fuente de medios para instalaciones de búsqueda orgánica** activada

**Cómo funciona:**

1. Una persona usuaria hace clic en un resultado de búsqueda no pagado o en un enlace de respuesta con IA y llega a tu sitio web.
2. La página muestra un botón de descarga con Smart Script detrás. La persona usuaria no tiene tu app instalada, así que el botón la envía a la tienda de aplicaciones.
3. Smart Script crea un enlace de atribución de AppsFlyer. Su fuente de medios (`pid`) se basa en el referente web, es decir, la página de la que procede la persona usuaria. Por ejemplo, una persona usuaria llega desde google.com y la visita no tiene indicadores de pago (`pid`, parámetros UTM, `gclid`, `gbraid` o `wbraid`). Smart Script puede definir entonces `pid=google_organic_seo`.
4. El usuario instala la aplicación y la abre por primera vez. AppsFlyer puede atribuir la instalación a ese clic y asignar el mérito al motor de búsqueda o motor de respuestas de IA que envió al usuario a tu sitio web.

<Image alt="Google Chrome 2026-11-01 19.18.06.png" src="https://files.readme.io/5032ea848a80a61233e20a1ff710f148e42f478dc9ecfaf2be45b9b5d990ea31-52588329958673.png" width="2250px" />

Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#seo-referrer-mapping">configurar Smart Script para convertir a los visitantes web</Anchor>.

## Caso de uso 3: medición del re-engagement de la aplicación

Atribuye aperturas de la aplicación de usuarios que ya tienen tu aplicación instalada.

**Pré-requisitos:**

* Versión 6.12.1 o posterior del SDK de AppsFlyer para Android e iOS
* Contenido del sitio web asignado al contenido de la app mediante Android App Links e iOS Universal Links

**Cómo funciona:**

1. Un usuario hace clic en un resultado de búsqueda no pagado o en un enlace de respuesta de IA.
2. El contenido de tu sitio web está asignado a tu app y el usuario tiene la app instalada. El enlace abre la app directamente en el contenido correspondiente.
3. La aplicación se abre mediante el enlace profundo. El referente web, la página de la que procede el usuario, se envía a AppsFlyer. AppsFlyer lo usa para atribuir la apertura de la aplicación al motor de búsqueda o motor de respuestas de IA correspondiente.

<Image alt="Google Chrome 2026-11-01 19.18.53.png" src="https://files.readme.io/2e78034afb5f276391e6ca9971bc8cf018c234b22c928a19b595cdc69beb0d5d-52588346452753.png" width="2227px" />

Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">cómo configurar la atribución de re-engagement de la búsqueda orgánica (SEO) y de las respuestas orgánicas de IA (AEO)</Anchor>.

## Disponibilidad de datos

El tráfico de SEO y AEO aparece en AppsFlyer de la siguiente manera:

* **Dashboards y reportes:** Los motores de búsqueda aparecen como `<search engine>_organic_seo`, por ejemplo `google_organic_seo`. Los motores de respuestas de IA aparecen como `<AI engine>_organic_aeo`, por ejemplo `chatgpt_organic_aeo`.
* **Reportes de raw data:** El campo `channel` es `seo` para el tráfico de motores de búsqueda y `aeo` para el tráfico de motores de respuestas de IA.

## Motores de búsqueda y motores de respuestas de IA compatibles

AppsFlyer atribuye tráfico de los siguientes motores.

**Motores de búsqueda:** Google, Bing, Yahoo, Ask, DuckDuckGo, Yandex, Naver, Daum, Baidu, Ecosia, Coccoc, Sogou y Yahoo Japón.

**Motores de respuestas de IA:** ChatGPT, Claude, Perplexity, Manus, Copilot, Gemini, Grok y DeepSeek.

## PREGUNTAS FRECUENTES

### ¿Hay alguna tarifa adicional por la atribución de SEO y AEO?

N.º Está incluida en tu suscripción. Las conversiones orgánicas cuentan para tu paquete de la misma manera que las conversiones no orgánicas.

### ¿Puedo personalizar el nombre de la fuente de medios de SEO o AEO?

N.º AppsFlyer establece el nombre de la fuente de medios.

### ¿AppsFlyer atribuye una instalación cuando el usuario toca un botón de instalación que aparece en los resultados de búsqueda?

N.º En ese flujo, AppsFlyer no puede recopilar la información necesaria para la atribución.

### ¿Hay datos disponibles de palabras clave, términos de búsqueda o indicaciones?

N.º El referente web no incluye esta información.

## Consulte también

* <Anchor target="_blank" href="/marketers/es/docs/about-traffic-source-resolution">Información sobre la resolución de la fuente de tráfico</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors">Configura Smart Script para convertir a los visitantes de la web</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Configurar la atribución de re-engagement para la búsqueda orgánica (SEO) y las respuestas orgánicas de IA (AEO)</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">Modelo de atribución de AppsFlyer</Anchor>

<div data-zendesk-anchors="h_01M6C15DBDG1JVJ11WZ2ZB5A0R=acerca-de-la-atribuci%C3%B3n-de-seo-y-aeo h_01M6C15DBDFD0H52Y2V2X9J89K=recorridos-compatibles h_01M6C15DBDKJH8NN771ED3ZWVX=caso-de-uso-1-medici%C3%B3n-web h_01M6C15DBDY5Y4KM23NBYN12RH=caso-de-uso-2-medici%C3%B3n-de-la-instalaci%C3%B3n-de-la-app h_01M6C15DBDK3HC4SD9X9V7BGWD=caso-de-uso-3-medici%C3%B3n-del-re-engagement-de-la-aplicaci%C3%B3n h_01M6C15DBDSSBM7JK28KT01EA9=disponibilidad-de-datos h_01M6C15DBDQSE84ZGBJ7EBHR99=motores-de-b%C3%BAsqueda-y-motores-de-respuestas-de-ia-compatibles h_01M6C15DBDFQ4R4CE8021ANQ8Z=preguntas-frecuentes h_01M6C15DBDP74VR7JTPMMDP91H=hay-alguna-tarifa-adicional-por-la-atribuci%C3%B3n-de-seo-y-aeo h_01M6C15DBDSVC2E5HTRPJ27PM2=puedo-personalizar-el-nombre-de-la-fuente-de-medios-de-seo-o-aeo h_01M6C15DBD6Q000S8S8VZ2PEK9=appsflyer-atribuye-una-instalaci%C3%B3n-cuando-el-usuario-toca-un-bot%C3%B3n-de-instalaci%C3%B3n-que-aparece-en-los-resultados-de-b%C3%BAsqueda h_01M6C15DBDQ2JPM01NX82N110A=hay-datos-disponibles-de-palabras-clave-t%C3%A9rminos-de-b%C3%BAsqueda-o-indicaciones h_01M6C15DBD6442ATGZVZNZKGJ9=consulte-tambi%C3%A9n" />

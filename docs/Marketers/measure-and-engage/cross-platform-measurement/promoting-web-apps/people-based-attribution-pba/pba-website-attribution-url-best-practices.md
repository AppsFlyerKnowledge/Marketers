---
title: Mejores prácticas de atribución de URL de sitios web de PBA
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-05-23T05:29:27Z'
  edited_at: '2026-08-12T12:11:39Z'
  id: 6313062676497
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/6313062676497
---
> **En resumen:** Prácticas recomendadas para atribuir a las campañas de atribución de tu sitio web la mejor granularidad de campaña disponible.

## URL de atribución de sitios web de PBA

Para obtener los mejores resultados de granularidad de la campaña combinados con la atribución más precisa en los datos de atribución de tu sitio web, rellena las URL (enlaces) y lleva a los usuarios a tu sitio web mediante las prácticas que se detallan en este artículo.

### Parámetros de URL: grupo y prioridad

La solución de atribución de sitios web de AppsFlyer admite varias clases de parámetros de campaña. Las clases se organizan por prioridad de la siguiente manera:

* [Prioridad más alta] PID
* ID de clic de canales específicos, como Google, DoubleClick y Microsoft
* [Prioridad más baja] UTM

Las <Anchor target="_blank" href="/marketers/es/docs/pba-media-source-attribution-rules">reglas de atribución de fuentes de medios de la PBA</Anchor> determinan cómo se atribuye a un usuario determinado. Las clases de parámetros se clasifican por prioridad. Si se encuentra más de una clase de parámetros en un enlace, la clase que tenga la prioridad más alta recibe la atribución.

#### Parámetros compatibles

| # | Parámetro | Usado para | Clase de parámetros | Disponible en el panel de control | Campo de raw data de PBA |
| --- | --- | --- | --- | --- | --- |
| 1 | PID | Fuente de medios | PID no integrados. | Sí | fuente\_de\_medios |
| 2 | C | Nombre de la campaña | PID no integrados. | Sí | campaña única |
| 3 | af\_c\_id | ID de campaña | PID no integrados. | Sí | id\_campaña |
| 4 | af\_conjunto de anuncios | Nombre del conjunto de anuncios | PID no integrados. | Sí | Extraer de query\_params |
| 5 | af\_adset\_id | ID de conjunto de anuncios | PID no integrados. | Sí | Extraer de query\_params |
| 6 | af\_anuncio | Nombre de anuncio | PID no integrados. | Sí | Extraer de query\_params |
| 7 | id\_del\_anuncio\_af | ID de anuncio | PID no integrados. | Sí | Extraer de query\_params |
| 8 | utm\_source | Fuente de medios | UTM | Sí | fuente\_de\_medios |
| 9 | utm\_medium | Media Type | UTM | Sí | media\_type |
| 10 | utm\_campagin | Campaña | UTM | Sí | campaña única |

## Mejores prácticas para los parámetros de URL

### Selección de parámetros de URL

Cada clase de parámetros funciona en el contexto de un silo. Por lo tanto, si necesitas URL con varias clases, la URL debe tener los parámetros relevantes de cada clase. De este modo, se optimiza la granularidad de tus reportes.

El uso de parámetros de varias clases se ilustra en el contexto de los anuncios de Meta de la siguiente manera:

* **Grupo PID**:  `www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}`
* **Grupo UTM**: `www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}`
* Si combinas clases pero incluyes solo algunos de los parámetros obligatorios, es posible que AppsFlyer no proporcione la granularidad completa. Por ejemplo, si utilizas `www.website.com?utm_source=facebook&c={{campaign.name}}`, ocurre lo siguiente:
  * AppsFlyer usa la clase UTM porque no hay ninguna clase PID y determina la fuente multimedia mediante utm\_source.
  * Sin embargo, la campaña no se puede determinar porque *c=* forma parte de la clase PID, pero pid no está incluido.
  * Para resolver esto, asumiendo que necesitas el utm\_source para otros fines, considera esta opción: `www.website.com?pid=facebook_int&c={{campaign.name}}&utm_source=facebook` Con esta estructura, AppsFlyer usa la clase PID para identificar la fuente de medios. Con esta estructura, AppsFlyer usa la clase PID para identificar la fuente de medios. Se pueden incluir otros parámetros PID, como c=, y no se tiene en cuenta el utm\_source porque tiene una prioridad más baja.

### Implementa URL dinámicas mediante macros de redes de publicidad

Usa macros de red (también conocidas como parámetros de valuetrack) para ahorrar tiempo al crear plantillas y aplicar parámetros de URL a las campañas de pago.

Las redes utilizan diferentes macros para rellenar los parámetros de la URL. Por lo tanto, debes consultar la documentación de la red de publicidad para comprobar que utilizas las macros correctamente. Por ejemplo, si quieres pasar el ID de la campaña a af\_c\_id, puedes evitar codificar de forma rígida el ID de la campaña real para cada URL y simplemente usar las macros:

* Google Adwords: `www.website.com?af_c_id={campaignid}`
* Anuncios de Meta: `www.website.com?af_c_id={{campaign.id}}`
* Anuncios de Pinterest: `www.website.com?af_c_id={campaignid}`
* Anuncios de Snapchat: `www.website.com?af_c_id={{campaign.id}}`
* Anuncios de Microsoft (Bing): `www.website.com?af_c_id={campaignid}`

### Mayúsculas y minúsculas dentro de los parámetros

Los valores de los parámetros distinguen mayúsculas de minúsculas. Por ejemplo, utm\_source=channel1 y utm\_source=CHANNEL1 se consideran fuentes de medios diferentes. Por lo tanto, verifica que es coherente con respecto a la mayúscula.

### Usa la integración de Google Ads para automatizar la granularidad

En el caso de las campañas de Google Ads, puedes obtener la granularidad de la campaña integrando PBA con tu cuenta de <Anchor target="_blank" href="/marketers/es/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Ads</Anchor>. Esto garantiza que tus datos se rellenen con todos los datos de la jerarquía de la campaña sin necesidad de parámetros PID o UTM en la URL.

## Errores comunes en los parámetros de URL que se deben evitar

### Signos de interrogación

* Utiliza solo un signo de interrogación entre la página de destino de la URL y los parámetros
* No debe haber otros signos de interrogación en la URL

Por ejemplo, `www.website.com?parameters`

Ejemplo de usos **incorrectos**: 

`www.website.com??parameters`

`www.website.com?parameter1?parameter2`

### Señales de anclaje

Los signos de anclaje (#) no deben usarse en la URL. El uso de un signo de anclaje en una URL puede provocar que los parámetros que aparecen después del formulario de firma no se carguen y nuestro SDK web no los recopile.

<div data-zendesk-anchors="pba-website-attribuiton-urls=url-de-atribuci%C3%B3n-de-sitios-web-de-pba h_01KQS4QK4Z70GC9VVFQCFHK4SQ=url-de-atribuci%C3%B3n-de-sitios-web-de-pba url-parameters%E2%80%94group-and-priority=par%C3%A1metros-de-url-grupo-y-prioridad h_01KQS4QK4Z3YTXHGQMYNZ36DZ1=par%C3%A1metros-de-url-grupo-y-prioridad supported-parameters=par%C3%A1metros-compatibles h_01KQS4QK4Z1RVQKZX94MJJQSQW=par%C3%A1metros-compatibles url-parameter-best-practices=mejores-pr%C3%A1cticas-para-los-par%C3%A1metros-de-url h_01KQS4QK4Z3V5Y9RSM20VTESDP=mejores-pr%C3%A1cticas-para-los-par%C3%A1metros-de-url selecting-url-parameters=selecci%C3%B3n-de-par%C3%A1metros-de-url h_01KQS4QK4ZP6WCWEG4FH9R1N8Q=selecci%C3%B3n-de-par%C3%A1metros-de-url implement-dynamic-urls-using-ad-network-macros=implementa-url-din%C3%A1micas-mediante-macros-de-redes-de-publicidad h_01KQS4QK50MTKRPPNYNWZKPMSD=implementa-url-din%C3%A1micas-mediante-macros-de-redes-de-publicidad consistent-case-within-parameters=may%C3%BAsculas-y-min%C3%BAsculas-dentro-de-los-par%C3%A1metros h_01KQS4QK50K5Q5NV2VQTASHDGD=may%C3%BAsculas-y-min%C3%BAsculas-dentro-de-los-par%C3%A1metros use-google-ads-integration-to-automate-granularity=usa-la-integraci%C3%B3n-de-google-ads-para-automatizar-la-granularidad h_01KQS4QK505R1Y4TED19FWCY6M=usa-la-integraci%C3%B3n-de-google-ads-para-automatizar-la-granularidad common-url-parameter-mistakes-to-avoid=errores-comunes-en-los-par%C3%A1metros-de-url-que-se-deben-evitar h_01KQS4QK50XDC8216WBJJ6DJJ7=errores-comunes-en-los-par%C3%A1metros-de-url-que-se-deben-evitar question-marks=signos-de-interrogaci%C3%B3n h_01KQS4QK50KAS1DVXASYB81PGJ=signos-de-interrogaci%C3%B3n anchor-signs=se%C3%B1ales-de-anclaje h_01KQS4QK507423MN3RWN94CWEY=se%C3%B1ales-de-anclaje" />

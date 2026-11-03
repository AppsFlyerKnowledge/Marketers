---
title: Guía de pruebas A/B de AppsFlyer
metadata:
  keywords:
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
  created_at: '2019-05-07T09:17:43Z'
  edited_at: '2026-08-12T11:56:55Z'
  id: 360001523657
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/360001523657
---
> **En resumen:** Utiliza AppsFlyer para realizar pruebas A/B de fuentes de medios, campañas, creatividades, targeting y ubicación de anuncios.

![AB_TESTING.jpg](https://files.readme.io/259277a96d044e85cbac39de0f636bad531706e53e2ad5a21475277ea9dbd3a6-360002822018.jpg)

## ¿Qué son las pruebas A/B?

Las pruebas A/B son un método utilizado por los marketers para probar diferentes elementos de sus anuncios y campañas. Cada anuncio contiene elementos (targeting, visuales, textos) que pueden afectar las tasas de conversión de los usuarios potenciales. Encontrar las variantes de mejor rendimiento de tus elementos publicitarios puede tener un impacto significativo en el resultado final de tus esfuerzos de marketing móvil.

Este artículo explica **cómo los anunciantes pueden realizar pruebas A/B utilizando AppsFlyer para encontrar los elementos publicitarios con mejor rendimiento**.

## Cómo realizar pruebas A/B en campañas móviles

Para realizar una prueba A/B de un elemento, divide tu tráfico móvil 50/50 entre dos fuentes que muestren la oferta idéntica. A continuación, crea dos variantes del elemento que quieres probar. Una vez que haya transcurrido suficiente tráfico, puedes comparar los resultados de tu versión existente (control) con la nueva versión (variante).

Los siguientes pasos se aplican a una prueba A/B que ejecutes utilizando AppsFlyer.

**Configuración**:

1. Selecciona el elemento a probar.  
   En este artículo, explicamos cómo realizar pruebas A/B de [creatividades](/docs/create-a-b-tests#pruebas-ab-de-creatividades-y-targeting), ubicaciones de anuncios, fuentes de medios y campañas.
2. Crea dos campañas (o anuncios) idénticas y luego varía un solo elemento dentro del anuncio. Por ejemplo, el texto del botón de llamada a la acción.
   * Para probar el impacto de la variante en las **tasas de conversión de instalaciones**, divide el tráfico equitativamente entre las dos campañas.   
     Si hay datos de impresiones completos disponibles para ambas fuentes, divide las instalaciones por las impresiones para calcular las tasas de conversión de instalaciones.
   * Para probar el impacto de la variante en la calidad de los usuarios, **después de la instalación**, puedes enviar diferentes cantidades de tráfico a las dos campañas.
3. Dirige suficiente tráfico a cada campaña para alcanzar significancia estadística, es decir, al menos 50 instalaciones por campaña. Utiliza la <Anchor target="_blank" href="https://neilpatel.com/ab-testing-calculator/">calculadora de significancia de pruebas A/B</Anchor>.

**Análisis:**

1. Utiliza el panel de control y los datos de AppsFlyer para comparar el rendimiento de los KPI clave entre las dos campañas.
2. Selecciona la variante ganadora y úsala en tus campañas online.

## Pruebas A/B de creatividades y targeting

Las creatividades contienen muchos elementos con un impacto variable en las tasas de conversión de los usuarios, incluidos el texto, las imágenes, los colores, las fuentes, los botones, etc. Los parámetros de targeting, como el país, la edad o el género, también pueden tener un impacto importante en las tasas de conversión. Y para iOS 15+, también puedes tener hasta 35 páginas de productos personalizadas. **Realizar pruebas A/B de estos elementos puede ayudarte a encontrar qué factores tienen el mayor impacto en la mejora de las tasas de conversión de los usuarios**.

A continuación explicamos dos métodos de pruebas A/B utilizando:

* Una única fuente de medios
* Varias fuentes de medios

| Método | Ventajas | Contras |
| --- | --- | --- |
| Pruebas A/B con una única fuente de medios | <ul><li>Configuración rápida</li><li>La tasa de conversión de instalaciones es fácil de probar</li></ul> | <ul><li>Los resultados solo pueden aplicarse a los usuarios de la fuente de medios específica</li><li>La prueba puede tardar más tiempo</li></ul> |
| Pruebas A/B en varias fuentes de medios | <ul><li>Resultados rápidos</li><li>Los resultados se aplican a los usuarios de todas las fuentes de medios</li></ul> | <ul><li>Es necesario actualizar los enlaces de atribución en varios lugares</li></ul> |

<div id="method-1-ab-testing-with-a-single-media-source" />

<Accordion title="Método 1: Pruebas A/B con una única fuente de medios">

**Configuración**:

1. Selecciona una fuente de medios confiable con suficiente tráfico.
2. Crea dos campañas o <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup">banners inteligentes</Anchor> en AppsFlyer utilizando uno de los siguientes métodos:
   * Varía la campaña que tiene como nombre el parámetro "**c**" en el enlace de atribución.
   * Alternativamente, puedes crear dos conjuntos de anuncios ("**af\_adset**=") dentro de una campaña o anuncios individuales ("**af\_ad=**") dentro de un conjunto de anuncios. **Nota**: En los banners inteligentes, también puedes <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers#ab-testing-banner-performance">realizar pruebas A/B colocando diferentes parámetros para cada banner</Anchor> dentro del mismo grupo de banners.
   * Para iOS 15+, también puedes probar la eficacia de diferentes páginas de productos personalizadas enviando diferentes URL de OneLink a diferentes páginas de productos. <Anchor target="_blank" href="/marketers/es/docs/redirect-users-to-custom-app-store-product-pages">Saber más</Anchor>
3. Utiliza la misma creatividad en ambas campañas, excepto la variante probada.
4. Envía la misma cantidad de tráfico a ambas campañas.

**Análisis:**

* Compara los KPI (por ejemplo, tasa de conversión de instalaciones, ROI, ARPU, tasa de usuarios leales) de las campañas en la página del panel de control general.

</Accordion>

<div id="method-2-ab-testing-across-multiple-media-sources" />

<Accordion title="Método 2: Pruebas A/B en varias fuentes de medios">

**Configuración**:

1. Selecciona un parámetro de suscriptor para guardar el valor de variante.  
   Por ejemplo, para probar 2 variantes del texto de CTA, puedes utilizar af\_sub1="instalar ahora" o af\_sub1="instalar por favor". Puedes leer más sobre los parámetros de suscriptores y ver un ejemplo de prueba de creatividad <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">aquí</Anchor>.
2. Agrega el parámetro de suscriptor con el valor correspondiente a cada enlace de atribución online.
3. Se recomienda utilizar las mismas creatividades en todas las campañas, excepto la variante probada.

**Análisis:**

1. Descarga los reportes de raw data de instalaciones o eventos in-app. Utiliza la columna de parámetros de suscriptor seleccionada para filtrar y ordenar tus datos.
2. Compara el rendimiento de las creatividades con cualquiera de los 2 valores almacenados.

</Accordion>

## Pruebas A/B de la ubicación de anuncios en la web móvil

![ad_placement.png](https://files.readme.io/6d64eed1a7a16c6daae9c93429d5bd46625dc4de12728e42b49a91ae69765f24-360002747977.png)

La ubicación de los banners de tus aplicaciones en sitios web móviles puede afectar significativamente las tasas de conversión de usuarios. En la mayoría de los casos, los anunciantes utilizan sus propios sitios web móviles para convertir a los visitantes en usuarios móviles.

Con la <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">función Banners inteligentes</Anchor> de AppsFlyer, puedes configurar banners web móviles de forma rápida y sencilla. Además, esta función también te permite ejecutar fácilmente pruebas A/B para **determinar la mejor ubicación para convertir a los visitantes del sitio web en usuarios móviles**.

**Configuración**:

1. Implementa <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Banners Inteligentes</Anchor> en tu sitio web móvil.
2. Para cada nuevo visitante, determina si deseas mostrar el banner en la parte superior o inferior de la página. Asegúrate de dividir el tráfico 50/50 entre los dos.  
   Consejo para desarrolladores: un método simple para dividir el tráfico de tu sitio web es utilizar un contador de visitantes y luego verificar si el valor del contador es impar (opción A) o par (opción B) para cada visitante nuevo.
3. Establece la ubicación del banner y el enlace de atribución de acuerdo con la ubicación determinada utilizando la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">API ShowBanner del SDK</Anchor> de Banners inteligentes.  
   Ejemplo:

   ```javascript
   showBanner({ bannerContainerQuery: "#document.body", additionalParams:{ af_sub5: "top"}})
   ```

**Análisis:**

1. Descarga los reportes de raw data de instalaciones o eventos in-app. Utiliza la columna del parámetro de suscriptor seleccionado (por ejemplo, af\_sub5) para filtrar y ordenar tus datos.
2. Compara el rendimiento de las dos ubicaciones de anuncios, es decir, qué ubicación obtuvo más instalaciones o eventos post-instalación.

## Pruebas A/B de fuentes de medios

Ayudar a los anunciantes a identificar las fuentes de medios con mejor (y peor) rendimiento para sus aplicaciones es el propósito de AppsFlyer. Sin embargo, **si los anunciantes no comparan correctamente las fuentes de medios, corren el riesgo de llegar a conclusiones erróneas sobre la calidad del tráfico**.

**Configuración:**

1. Crea una única creatividad de anuncio para AMBAS fuentes de medios.
2. Define un anuncio para cada fuente de medios, con exactamente los mismos parámetros de targeting.
3. Puedes enviar diferentes cantidades de tráfico a las 2 fuentes de medios.

**Análisis:**

1. Si los anuncios que se están probando son los únicos que se ejecutan en ambas fuentes de medios, usa el panel de control y los datos de AppsFlyer para comparar fácilmente tu KPI clave entre las dos fuentes.  
     
   De lo contrario:
2. Ve al Reporte de retención, <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">Reporte de cohortes</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api">API maestra</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/pivot-table-user-metrics">Tabla dinámica</Anchor> de AppsFlyer.
3. Agrupa por Fuente de medios -> Campaña -> Conjunto de anuncios -> Anuncio.
4. Compara los KPI para identificar la fuente de medios con mejor rendimiento.

> 📄 **Ejemplo**
>
> [![](https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png)](https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png)
>
> * 1 y 2 son anuncios diferentes en la misma fuente de medios. Compara un único KPI para ellos, por ejemplo, la tasa de retención del día 4, con las creatividades de prueba A/B, el targeting o la ubicación de los anuncios.
> * 2 y 3 son anuncios en diferentes fuentes de medios. Si las creatividades y el targeting de los anuncios son idénticos, comparar un único KPI permite realizar pruebas A/B de la fuente de medios.

### Uso de la división de audiencias para facilitar las pruebas A/B de fuentes de medios

Si estableces los mismos parámetros de targeting para cada fuente de medios, la prueba incluye las capacidades de targeting de las redes. Al realizar pruebas A/B, es mejor probar una sola variante cada vez. Por lo tanto, es aconsejable eliminar las diferencias en las capacidades de targeting cuando se realizan pruebas A/B de otros factores del rendimiento de las redes.

Para lograr esto, recomendamos dividir una audiencia aleatoriamente y apuntar a ambas audiencias con la misma creatividad, en cada red probada. AppsFlyer ofrece un **método sencillo para definir, dividir y distribuir automáticamente audiencias entre diferentes fuentes de medios**. Puedes leer más <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#pruebas-de-incrementalidad-y-división-de-audiencia">aquí</Anchor>.

<div data-zendesk-anchors="what-is-ab-testing=qu%C3%A9-son-las-pruebas-ab h_01HN5CNKKBHV52ENXJXCBV2CES=qu%C3%A9-son-las-pruebas-ab how-to-ab-test-mobile-campaigns=c%C3%B3mo-realizar-pruebas-ab-en-campa%C3%B1as-m%C3%B3viles h_01HN5CNKKC02NKW4330QB6E01T=c%C3%B3mo-realizar-pruebas-ab-en-campa%C3%B1as-m%C3%B3viles ab-testing-creatives-and-targeting=pruebas-ab-de-creatividades-y-targeting h_01HN5CNKKCJPZSEEF1RAHC0HXD=pruebas-ab-de-creatividades-y-targeting h_01HN5CNKKCMVE9YH379RP1S19W=method-1-ab-testing-with-a-single-media-source h_01HN5CNKKC53RTV61K08T9AVRA=method-2-ab-testing-across-multiple-media-sources ab-testing-ad-placement-on-mobile-web=pruebas-ab-de-la-ubicaci%C3%B3n-de-anuncios-en-la-web-m%C3%B3vil h_01HN5CNKKCVPSSZZTJ8QGJHY1B=pruebas-ab-de-la-ubicaci%C3%B3n-de-anuncios-en-la-web-m%C3%B3vil ab-testing-media-sources=pruebas-ab-de-fuentes-de-medios h_01HN5CNKKC03ZAFCQZ0KJ0RHCE=pruebas-ab-de-fuentes-de-medios h_01HN5CNKKC4M6YMPHTQCFHFDMD=ejemplo using-audiences-split-for-easy-ab-testing-of-media-sources=uso-de-la-divisi%C3%B3n-de-audiencias-para-facilitar-las-pruebas-ab-de-fuentes-de-medios h_01HN5CNKKC551X3HQFNKHW1JBY=uso-de-la-divisi%C3%B3n-de-audiencias-para-facilitar-las-pruebas-ab-de-fuentes-de-medios" />

---
title: Dimensiones personalizadas
metadata:
  keywords:
    - dashboard
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2023-06-06T09:28:20Z'
  edited_at: '2026-08-12T11:50:37Z'
  id: 15920604187921
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/15920604187921
---
> **De un vistazo:** Define tus propias dimensiones y úsalas para agrupar y ver datos en el panel de control de resumen general.

<Embed title="Dimensiones personalizadas" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/tvcdofnwjo" providerUrl="https://fast.wistia.com" />

## Resumen general

Las dimensiones personalizadas te permiten usar las dimensiones existentes para crear tus propias dimensiones para el análisis de datos relevantes para tus propósitos comerciales. Estas dimensiones se pueden usar en todos los widgets del panel de control de resumen general para agrupar datos y ayudarte a obtener insights más profundos y tomar decisiones basadas en datos que se alineen con tus objetivos comerciales.

Las dimensiones personalizadas que creas están a nivel de cuenta, lo que significa que diferentes aplicaciones en la misma cuenta de AppsFlyer pueden usar las mismas dimensiones personalizadas.

### Ventajas

* Insights personalizados: define y recopila datos específicos para las necesidades de tu negocio. Al capturar información adicional más allá de las dimensiones estándar, puedes obtener insights más profundos y una comprensión más completa de tus datos.
* Análisis segmentado: agrupa y analiza tus datos en función de atributos o características específicas relevantes para obtener una visión más detallada del comportamiento de los usuarios, los segmentos de clientes o el rendimiento del producto.
* Reportes mejorados: crea paneles de control y reportes personalizados que se alineen con tus requisitos de reportes únicos.
* Mejora en la toma de decisiones: al capturar dimensiones personalizadas que se alinean con tus objetivos comerciales, puedes tomar decisiones más informadas. Las dimensiones personalizadas proporcionan el contexto necesario para evaluar el impacto de diferentes variables y factores en tus indicadores claves de rendimiento (KPI), lo que te ayuda a identificar tendencias, patrones y oportunidades de optimización.

### Ejemplos de casos de uso

| Ejemplo de caso de uso | Descripción |
| --- | --- |
| Intención de campaña | <ul><li>Basado en los nombres de tu campaña.</li><li>Selecciona nombres de valor para diferenciar tus diferentes objetivos de campaña. Por ejemplo: etiqueta una concientización de marca como "brd" y una campaña de adquisición de usuarios como "new" o "ua".</li><li>Incluye los nombres de valor en los nombres de tu campaña. Por ejemplo: "US\_Facebook\_BRD" o "UK\_Google\_new".</li><li>AppsFlyer realiza un análisis del nombre de la campaña y agrupa los datos en función de tus etiquetas.</li></ul> |
| Regiones | <ul><li>Basado en geolocalización.</li><li>Agrupa varias geolocalizaciones/países en regiones. Por ejemplo: agrupa Estados Unidos, Canadá y México en "Norteamérica", o usa diferentes geolocalizaciones para crear agrupaciones para Europa, APAC, etc.</li><li>AppsFlyer agrupa los datos en función de los valores de tu región (Norteamérica, Europa, APAC, etc.).</li></ul> |
| Medios propios vs. medios pagados | <ul><li>Basado en fuentes de medios.</li><li>Agrupa diferentes fuentes de medios en "propios" y "pagados". Por ejemplo: agrupa SMS y publicaciones de Facebook en el valor "propios", y Facebook y Google en el valor de "pagados".</li><li>AppsFlyer agrupa los datos de estas fuentes de medios en los valores "propios" y "pagados", respectivamente.</li></ul> |
| Ciudades | <ul><li>Basado en los nombres de tu campaña.</li><li>Los valores incluyen las ciudades para las que tienes campañas específicas en los nombres de tus campañas. Por ejemplo: "US\_Facebook\_NY" para Nueva York y "US\_Google\_SF" para San Francisco.</li><li>AppsFlyer realiza un análisis del nombre de la campaña y agrupa los datos en función de las ciudades.</li></ul> |
| Gerente de UA | <ul><li>Basado en fuentes de medios.</li><li>Agrupa diferentes fuentes de medios de acuerdo con miembros específicos del equipo. Por ejemplo: agrupa las campañas de Google y Facebook en el valor "Kevin" y TikTok e las campañas de Instagram en el valor "Natasha".</li><li>AppsFlyer agrupa los datos de estas fuentes de medios en los valores "Kevin" y "Natasha", respectivamente.</li></ul> |

## Procedimientos

<div id="create-a-custom-dimension" />

<Accordion title="Crear una dimensión personalizada">

**Para crear una dimensión personalizada**:

1. En el panel de control de Resumen general:
   * Haz clic en el **icono Menú (⋮)** > **Dimensiones personalizadas**.  
     [![](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)
   * O bien, en cualquier gráfico o tabla, en el menú desplegable **Mostrar principales** o **Agrupar por**, haz clic en **+ Crear dimensión personalizada**.
2. Si es la primera vez que creas una dimensión personalizada, haz clic en **+ Nueva dimensión**.  
   Se abre la pestaña **Crear**.
3. Ingresa un nombre y una descripción para tu dimensión. Elige el nombre y la descripción que te ayudarán a identificar esta dimensión personalizada en las opciones de agrupación del panel de control.
4. Define los posibles valores de dimensión. Puede haber hasta 10 valores por dimensión. Por cada valor:
   1. Introduce un nombre de valor.
      * Ejemplo: para una dimensión personalizada llamada "intención de campaña", los valores pueden ser "branding" y "ua". Consulta más ejemplos de casos de uso.
   2. Define las reglas para cuándo se debe usar el nombre del valor. Puede haber hasta 10 reglas por valor.
      * Cada regla incluye la dimensión existente en la que se basa el valor, los operadores y los valores de operador.
      * Ejemplo: si el nombre de la campaña incluye "brd" o "brnd", el nombre del valor será "branding". Consulta más ejemplos de casos de uso.
      * En la siguiente tabla se muestran los diferentes componentes utilizados en la definición de una dimensión.

<table><thead><tr><th>Nombre del valor</th><th>Dimensión (en la que basar el valor)</th><th>Operador</th><th>Valor del operador</th></tr></thead><tbody><tr><td rowspan="3">Tú decides los posibles nombres de valor para tu dimensión personalizada.</td><td>Fuente de medios</td><td rowspan="2">Selecciona: <ul><li>Es</li><li>Contiene</li><li>Comienza con</li><li>Termina con</li></ul></td><td><ul><li>Cadena</li><li>Selección desplegable (si el operador es "es")</li></ul></td></tr><tr><td>Nombre de la campaña</td><td>Cadena</td></tr><tr><td>Geolocalización</td><td>Es </td><td>Selección desplegable</td></tr></tbody></table>

5. Haz clic en **Guardar**.

</Accordion>

<div id="delete-or-edit-a-custom-dimension" />

<Accordion title="Eliminar o editar una dimensión personalizada">

**Para eliminar o editar una dimensión personalizada**:

1. En el panel de control de Resumen general:
   * Haz clic en el **icono Menú** > **Dimensión personalizada**.  
     [![](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)](https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png)
   * O bien, en cualquier gráfico o tabla, en el menú desplegable **Mostrar principales** o **Agrupar por**, haz clic en **+ Crear dimensión personalizada**.
2. Haz clic en la pestaña **Editar**.
3. Selecciona o busca una dimensión personalizada.
4. Para eliminar la dimensión, haz clic en el icono **Eliminar** junto a la dimensión seleccionada.
5. Para editar la dimensión, realiza los cambios que desees en la configuración de dimensión personalizada y haz clic en **Guardar**.

</Accordion>

<div id="view-custom-dimension-data" />

<Accordion title="Ver datos de dimensiones personalizadas">

Las dimensiones personalizadas se pueden usar para agrupar y ver datos en todos los widgets en el panel de control de Resumen general.

**Para ver datos de dimensiones personalizadas**:

1. En el panel de control de Resumen general, ve a cualquier widget de gráfico o panel de control.
2. En el menú desplegable **Mostrar principales** o **Agrupar por**, busca en Dimensiones personalizadas la dimensión personalizada que deseas usar.  
   [![](https://files.readme.io/e34bcb2ca34546347b391f0ad921319f296a21c41c3783e59a7d808b44d0b6a9-17082706166929.png)](https://files.readme.io/e34bcb2ca34546347b391f0ad921319f296a21c41c3783e59a7d808b44d0b6a9-17082706166929.png)
3. Los datos del gráfico o tabla se muestran en una agrupación utilizando tu dimensión personalizada

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Espec | Observaciones |
| --- | --- |
| Dimensiones personalizadas | Se pueden crear hasta 10 dimensiones personalizadas. |
| Anunciante | No pueden ver ni editar las dimensiones personalizadas hechas por agencias. |
| Agencias | <ul><li>Pueden crear y editar sus propias dimensiones personalizadas y verlas en su panel de control.</li><li>No pueden editar ni ver las dimensiones personalizadas hechas por el anunciante.</li></ul> |
| Redes de publicidad | No pueden ver, crear o editar las dimensiones personalizadas. |
| Métricas de SKAN | Cuando SSOT está desactivado y los datos se agrupan por una dimensión personalizada, las métricas de SKAN no se muestran. |
| Métricas orgánicas del día 7 | Cuando SSOT está activado y los datos se agrupan por una dimensión personalizada basada en la geolocalización, los datos no se muestran. |
| Permisos | Cualquier miembro del equipo puede crear nuevas dimensiones y editar las dimensiones existentes, incluso si fueron creadas por otro miembro del equipo. |
| Distinción entre mayúsculas y minúsculas | N.º Las mayúsculas y minúsculas se tratan igual. |
| Valores de dimensión | <ul><li>Puede haber hasta 10 valores de dimensión personalizados.</li><li>Al conectar los datos con valores de dimensión personalizados, se da prioridad a los valores de dimensión de mayor rango. Ejemplo:<ul><li>Distinción entre mayúsculas y minúsculas</li><li>Facebook se puede agrupar en medios pagados o propios según tu configuración, pero AppsFlyer da prioridad al Valor 1 (pagados).</li></ul></li></ul> |
| Operadores | El operador "no contiene" aún no está disponible. |
| Reglas de dimensión | Puedes tener hasta 10 reglas para un valor de dimensión. Estas se conectan mediante "o". El conector "y" aún no está disponible. |

</Accordion>

<div data-zendesk-anchors="organic-search-attribution=resumen-general h_01H8XWQHPERAEDQVD275TFVC5B=resumen-general benefits=ventajas h_01H8XWQHPE85376WV1Q9SPQ2NM=ventajas example-use-cases=ejemplos-de-casos-de-uso h_01H8XWQHPETE03XG9GGV9EBA2H=ejemplos-de-casos-de-uso procedures=procedimientos h_01H8XWQHPESY4DDDJSTR0JDHNB=procedimientos h_01H8XWQHPEDYVDQQV3P8EDARAY=create-a-custom-dimension h_01H8XWQHPE22WZ46RTNCYKX96F=delete-or-edit-a-custom-dimension h_01H8XWQHPED4PFPJP2044FT1H8=view-custom-dimension-data h_01H8XWQHPF7WZ7B5Q7T9CHADRK=specifications-and-limitations" />

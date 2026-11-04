---
title: Data Clean Room—consulta dinámica
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2023-09-20T10:05:34Z'
  edited_at: '2026-08-12T11:52:40Z'
  id: 18704719821329
  locale: es
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/es/articles/18704719821329
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo:** Ejecuta consultas DCR personalizadas en tiempo real sobre tus datos de atribución en el sistema AppsFlyer, tus fuentes personalizadas o una combinación de ambos. Previsualiza los resultados de tus consultas o descarga los resultados completos.

<div id="overview" />

## Visión general

<div id="why-use-dynamic-query" />

### ¿Por qué usar la consulta dinámica?

La consulta dinámica te permite ejecutar consultas ad hoc y personalizadas sobre tus datos de DCR en tiempo real para responder a tus preguntas específicas de marketing de forma rápida y eficiente.

* Al incorporar la potencia y la flexibilidad de SQL, te permite realizar investigaciones avanzadas y cálculos complejos que no pueden lograrse de ninguna otra forma. Con la consulta dinámica, puedes aplicar tu lógica de negocio a datos que, de otro modo, serían inaccesibles.
* Además, la consulta dinámica permite obtener respuestas eficientes a preguntas puntuales u ocasionales sin necesidad de configurar reportes. (Por supuesto, los <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-reports">reportes DCR tradicionales</Anchor> siguen siendo la solución adecuada para la recuperación y la ingesta continuas de datos)

La consulta dinámica está disponible para **todos los clientes de DCR** y te permite ejecutar consultas y previsualizar los resultados sin usar créditos de tu paquete de DCR. Solo se te cobrarán créditos si decides descargar los resultados completos. De este modo, puedes asegurarte de que has configurado tus consultas correctamente y de que obtendrás las respuestas que necesitas antes de que se te aplique ningún cargo.

<div id="query-language-and-dialect" />

### Lenguaje y dialecto de consulta

La consulta dinámica utiliza SQL **(dialecto Spark SQL)** y admite:

* <Anchor target="_blank" href="https://spark.apache.org/docs/3.2.1/sql-ref-syntax-qry-select.html">Sentencias SELECT</Anchor>
* <Anchor target="_blank" href="https://spark.apache.org/docs/3.2.1/api/sql/">Funciones SQL estándar</Anchor>
* Funciones definidas por el usuario (UDF), a petición del cliente
  * Si necesitas una función SQL no estándar, ponte en contacto con tu CSM o con [hello@appsflyer.com](mailto:hello@appsflyer.com,) y haremos todo lo posible por añadirla.

<div id="available-sources" />

### Fuentes disponibles

La consulta dinámica te permite realizar consultas personalizadas sobre las siguientes fuentes de datos:

* Tus datos de atribución en el sistema AppsFlyer
  * [Más información](#querying-attribution-data) sobre las tablas de datos de atribución y cómo consultarlas
* <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources">Fuentes personalizadas</Anchor> que has configurado en el DCR

Puedes consultar estas fuentes por separado o [combinar 2 o más](#combining-sources) mediante sentencias **JOIN** o **UNION**. Esta flexibilidad hace que la consulta dinámica sea útil en diversos escenarios, por ejemplo:

* Consultar solo datos de atribución para [obtener insights entre apps](#obtain-crossapp-insights), [explorar la integridad de los datos](#explore-data-integrity) o [calcular métricas de atribución personalizadas](#calculate-custom-attribution-metrics)
* Consultar tus fuentes personalizadas en combinación con datos de atribución para [enriquecer tus datos](#enrich-your-custom-data-with-attribution-insights) con insights de atribución

En función de los tipos de fuentes utilizados en una consulta, [se aplican reglas](#protección-de-la-privacidad) para garantizar la estricta protección de la privacidad del usuario.

<div id="note" />

> 📘 **Advertencia**
>
> Actualmente, Dynamic Query no consulta datos de atribución ni devuelve resultados de Meta (Facebook, Instagram, etc.) Para consultar estos datos, configura <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-reports">reportes de DCR</Anchor>.

<div id="preserving-privacy" />

### Protección de la privacidad

Para garantizar que Dynamic Query mantenga un cumplimiento estricto de los estándares de privacidad de DCR, los siguientes requisitos se aplican a todas las consultas:

1. Cualquier consulta que utilice **datos de atribución** debe incluir una instrucción **GROUP BY** para que los resultados se agreguen.
2. Las instrucciones **UNION** **no pueden** usarse para combinar fuentes personalizadas con datos de atribución.
3. No se permite agrupar por los siguientes campos **no está permitido:**
   * **Campos de Datos de atribución:**
     * appsflyer\_id
     * idfa
     * idfv
     * advertising\_id
     * android\_id
     * id\_usuario\_cliente
     * ip
   * **Campos de fuentes personalizadas** que se unan a cualquiera de los campos de datos de atribución anteriores.
4. Las siguientes funciones **no están permitidas** cuando se ejecutan sobre **datos de atribución no agregados.** **Están permitidas** cuando se ejecutan sobre **datos de atribución agregados** o **datos de fuentes personalizadas:**
   * collect\_list
   * collect\_set
   * último
   * last\_value
   * first
   * first\_value
   * máx.
   * mín.

Para saber qué *debes* y qué *no debes* hacer al construir consultas, consulta ejemplos y explicaciones de consultas [válidas](#queries-de-muestra) y [no válidas](#consultas-no-válidas).

<div id="accessing-dynamic-query" />

### Acceso a Dynamic Query

1. En AppsFlyer, desde el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En el menú superior, selecciona la pestaña **Dynamic Query**.

<div id="reference" />

## Referencia

<div id="query-reference" />

### Referencia de consulta

Las siguientes pestañas proporcionan información adicional sobre cómo crear consultas en el entorno de Dynamic Query.

<div id="combining-sources" />

<Accordion title="Combinación de fuentes: JOIN y UNION">

Las instrucciones **JOIN** combinan fuentes al hacer coincidir un campo común:

* Se pueden usar para combinar cualquier tipo de fuentes: tablas de datos de atribución y/o fuentes personalizadas
* Se puede usar para combinar un número ilimitado de fuentes
* **Suele usarse para enriquecer datos de fuentes personalizadas con Datos de atribución**

Las instrucciones **UNION** agregan tablas con un esquema coincidente (que contienen las mismas columnas y tipos de datos):

* **Se puede** usar para combinar tablas de datos de atribución ***o*** fuentes personalizadas; **no se puede** usar para combinar tablas de datos de atribución ***con*** fuentes personalizadas
* Se puede usar para combinar un número ilimitado de fuentes
* **Suele usarse para realizar consultas en** [**varias tablas de datos de atribución**](#querying-attribution-data)

</Accordion>

<div id="querying-attribution-data" />

<Accordion title="Consulta de tablas de datos de atribución">

Los datos de atribución del sistema AppsFlyer existen en 8 tablas diferentes:

* Cada tabla incluye distintos tipos de eventos de atribución.
* El período durante el cual los datos de consulta están disponibles varía según la tabla.
  * Al crear tu consulta en la consola de Dynamic Query, coloca el cursor sobre el nombre de una tabla en el panel de selección para ver las fechas exactas de disponibilidad de los datos de esa tabla.
* Las tablas de cada uno de los grupos siguientes tienen un esquema coincidente, lo que significa que puedes usar instrucciones **UNION** para consultar fácilmente varias tablas a la vez.

**Grupo 1: instalaciones de apps y eventos de retargeting**

| Nombre de la tabla | Nota | Fechas de disponibilidad de los datos |
| --- | --- | --- |
| Cadena | Un usuario descarga, instala e inicia una aplicación móvil | 180 días anteriores  <br />(sin incluir el día actual) |
| re\_installs | Un usuario instala una aplicación, luego la desinstala y la vuelve a instalar durante la ventana de reatribución | 180 días anteriores  <br />(sin incluir el día actual) |
| re\_engagements | Un usuario inactivo de una aplicación específica participa en una campaña de retargeting de la aplicación y posteriormente la inicia | 180 días anteriores  <br />(sin incluir el día actual) |
| re\_attribution | Un antiguo usuario de una aplicación específica (que la había desinstalado) participa en una campaña de retargeting de la aplicación y posteriormente la vuelve a instalar | 180 días anteriores  <br />(sin incluir el día actual) |
| organic\_installs | Instalación no atribuida a una fuente de medios específica | 180 días anteriores  <br />(sin incluir el día actual) |

**Grupo 2: Eventos in-app**

| Nombre de la tabla | Descripción | Fechas de disponibilidad de los datos |
| --- | --- | --- |
| eventos\_in\_app | Eventos posteriores a la instalación configurados para su medición en el SDK de la aplicación | Día anterior + día actual |
| instalaciones\_orgánicas\_in\_app | Eventos in-app posteriores a una instalación orgánica | Día anterior + día actual |

**Grupo 3: Impresiones**

| Nombre de la tabla | Nota | Fechas de disponibilidad de los datos |
| --- | --- | --- |
| Validación de compra de AppsFlyer | Un anuncio es visualizado por un usuario de la aplicación o un visitante del sitio web<ul><li>Datos disponibles solo para ad networks que no sean SRN</li></ul> | 5 días anteriores + día actual |

</Accordion>

<div id="sample-queries" />

### Queries de muestra

Estas consultas muestran solo algunas de las posibilidades de lo que puedes hacer con Dynamic Query. Puedes utilizarlas simplemente para inspirarte o usarlas como punto de partida para tus propias consultas.

**Para usar las consultas de ejemplo como base para tus consultas:**

1. Copiar y pegar: copia los ejemplos de SQL que quieras y pégalos en una hoja de trabajo de la pestaña **Dynamic Query**.
2. Sustituir parámetros: modifica el código SQL sustituyendo los parámetros por las fuentes y los campos concretos que quieras consultar.
3. Ejecutar: haz clic en el botón **Run** para ejecutar una consulta y obtener una vista previa de los resultados.  
   * Ejecutar una consulta y previsualizar los resultados no consume créditos.
   * Los créditos de tu paquete DCR solo se consumen si descargas los resultados completos.

<div id="obtain-crossapp-insights" />

<Accordion title="Obtén insights entre aplicaciones">

Esta consulta recupera información sobre las 3 aplicaciones con más reinstalaciones de Snapchat durante los últimos 3 días.

```sql
SELECT app_id, COUNT(*) AS reinstall_count
FROM re_installs
WHERE media_source = 'snapchat_int' AND dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY app_id
ORDER BY reinstall_count DESC
LIMIT 3;
```

</Accordion>

<div id="explore-data-integrity" />

<Accordion title="Explora la integridad de datos">

Para ayudarte a evaluar la integridad de los datos, esta consulta calcula la tasa de valores IDFA nulos de las 10 fuentes de medios con el mayor número de instalaciones durante los últimos 7 días.

```sql
SELECT media_source, COUNT(*) AS total_installs, ROUND((SUM(CASE WHEN idfa IS NULL THEN 1 ELSE 0 END) / COUNT(*)) * 100, 2) AS null_idfa_rate
FROM installs
WHERE dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY media_source
ORDER BY total_installs DESC
LIMIT 10;
```

</Accordion>

<div id="calculate-custom-attribution-metrics" />

<Accordion title="Calcula métricas de atribución personalizadas">

Al calcular la media geométrica de la diferencia de tiempo (en segundos) entre la hora de instalación y la hora del toque atribuido para cada fuente de medios y campaña, los datos resultantes proporcionan información sobre la eficiencia de varias fuentes de medios con respecto a las conversiones de usuarios y los plazos de atribución.

```sql
SELECT media_source,campaign,geo_mean(GREATEST(1, unix_timestamp(install_time, "yyyy-MM-dd HH:mm:ss") - unix_timestamp(attributed_touch_time, "yyyy-MM-dd HH:mm:ss.SSS")))
FROM installs
GROUP BY 1,2
```

</Accordion>

<div id="enrich-your-custom-data-with-attribution-insights" />

<Accordion title="Enriquece tus datos personalizados con insights de atribución">

Esta consulta utiliza datos de atribución para agrupar una puntuación de la fuente personalizada C (c.score) por fuente de medios, lo que te permite usar tu métrica personalizada para evaluar el rendimiento relativo de varias fuentes de medios.

```sql
SELECT media_source, sum(c.score)
FROM client_input c JOIN install i on i.appsflyer_id = c.appsflyer_id
GROUP BY media_source;
```

</Accordion>

<div id="complex-attribution-and-firstparty-data-join" />

<Accordion title="Unión compleja de atribución y datos propios">

Esta consulta utiliza un proceso de unión de datos más complejo, lo que permite generar insights avanzados. Primero, recupera y unifica datos de 2 tablas de atribución distintas ("instalación" y "installRetarget"). A continuación, combina estos datos con 2 fuentes personalizadas propias para proporcionar insights sobre varios tipos de conversión, incluida una métrica personalizada de rendimiento agregada (score) y la antigüedad máxima de cada una.

```sql
SELECT conversion_type, SUM(sum_score), MAX(max_age)
FROM (SELECT media_source, conversion_type, SUM(score) as sum_score, MAX(age) as max_age
FROM (SELECT * from install union all select * FROM installRetarget) af
JOIN client_input c on c.appsflyer_id = af.appsflyer_id
JOIN client_age ca on ca.appsflyer_id = c.appsflyer_id
GROUP BY media_source, conversion_type)
GROUP BY conversion_type
```

</Accordion>

<div id="invalid-queries" />

### Consultas no válidas

Estas consultas ilustran algunas de las reglas que Dynamic Query utiliza para garantizar el cumplimiento de los requisitos de privacidad del usuario. Úsalas para comprender mejor lo que se *debe* y lo que *no se debe* hacer al crear consultas para el DCR.

<div id="no-group-by-statement" />

<Accordion title="Sin instrucción GROUP BY">

Cada una de las siguientes consultas no es válida porque utiliza datos de atribución, pero no incluye una instrucción **GROUP BY**:

```sql
SELECT *
FROM install;
```

-----------------------------------------------------

```sql
SELECT media_source, appId
FROM client_input c
JOIN install af on af.appsflyer_id = c.appsflyer_id;
```

</Accordion>

<div id="grouped-by-nonpermitted-attribution-data-field" />

<Accordion title="Agrupada por un campo no permitido de datos de atribución">

La siguiente consulta no es válida porque agrupa por un campo no permitido de datos de atribución (appsflyer\_id):

```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY appsflyer_id
```

-----------------------------------------------------

La siguiente consulta no es válida porque agrupa por un campo no permitido de datos de atribución (appsflyer\_id). Esto no está permitido, incluso cuando el campo está dentro de una función:

```sql
SELECT substr(appsflyer_id, 0, 5), count(*)
FROM install
GROUP BY substr(appsflyer_id, 0, 5)
```

-----------------------------------------------------

La siguiente consulta no es válida porque agrupa por un campo no permitido de datos de atribución (appsflyer\_id). Esto no está permitido, incluso cuando el campo está dentro de un índice:

```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY 1
```

</Accordion>

<div id="grouped-by-nonpermitted-custom-data-field" />

<Accordion title="Agrupada por un campo de fuente personalizada unido a un campo no permitido de datos de atribución">

La siguiente consulta no es válida porque agrupa por un campo de fuente personalizada (my\_id) que está unido a un campo no permitido de datos de atribución (appsflyer\_id); por lo tanto, la misma restricción de agrupación también se aplica a my\_id.

```sql
SELECT my_id, count(*)
FROM installs
JOIN my_source on my_source.my_id = installs.appsflyer_id
GROUP BY my_id
```

</Accordion>

<div id="restricted-function" />

<Accordion title="Función restringida">

La siguiente consulta es **no válida** porque intenta ejecutar la función collect\_list en datos de atribución **no agregados**:

```sql
SELECT App_id, collect_list(appsflyer_id)
FROM install
GROUP BY app_id
```

-----------------------------------------------------

Compáralo con la siguiente consulta **válida**, que ejecuta la función collect\_list en **datos de atribución agregados**:

```sql
SELECT app_id, collect_list(campaign)
FROM (select app_id, campaign
  FROM Install
  GROUP BY 1, 2)
GROUP BY app_id
```

-----------------------------------------------------

Compárala con la siguiente consulta **válida**, que ejecuta la función collect\_list en **datos de fuente personalizados:**

```sql
SELECT app_id, collect_list(c.score)
FROM client_input c
GROUP BY app_id
```

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HAS0VY179VDWWV6N5YY2578E=visi%C3%B3n-general why-use-dynamic-query=por-qu%C3%A9-usar-la-consulta-din%C3%A1mica h_01HF9G8TXGTAJDFZFVT8WS3QJE=por-qu%C3%A9-usar-la-consulta-din%C3%A1mica query-language-and-syntax=lenguaje-y-dialecto-de-consulta h_01HF3KZXC2VHNG92YX25K9HX7Q=lenguaje-y-dialecto-de-consulta h_01HASGQZ5ATBPQ0HF28ETAGPMJ=fuentes-disponibles h_01HF45KMZNF95SC0K6DE7P4K1R=advertencia preserving-privacy=protecci%C3%B3n-de-la-privacidad 01HF3EJEN2KSRR56F9XF0VSPQF=protecci%C3%B3n-de-la-privacidad accessing-the-dynamic-query=acceso-a-dynamic-query h_01J3FBVTVW2NCNESK3SYR0G9Q8=acceso-a-dynamic-query reference=referencia h_01HAS0X3NDFM136YMYSAG88JD7=referencia query-reference=referencia-de-consulta h_01HFKFTBD7BCVP8PT0FDNGVHXS=referencia-de-consulta h_01HFM169F3W9FDZZ3A4SG7WW58=combining-sources h_01HFM169F3WECT4M32H1CVCMKS=querying-attribution-data sample-queries=queries-de-muestra h_01HF3TDC0A8N9ZXGJHY4MZE3Y6=queries-de-muestra h_01HF40PRZV7DBMYQRS6YJK2RM4=obtain-crossapp-insights h_01HF40PRZVFHY7B0R1G5S5PRTG=explore-data-integrity h_01HF40PRZVB5N2B14VEYW2CB3N=calculate-custom-attribution-metrics h_01HF40PRZVDXPZBDT25B9JK2EE=enrich-your-custom-data-with-attribution-insights h_01HF40PRZVM2HGQMX9TCK8WF7Y=complex-attribution-and-firstparty-data-join invalid-queries=consultas-no-v%C3%A1lidas h_01HF3V03EFAVYR6M4WX0BHSVDK=consultas-no-v%C3%A1lidas h_01HF40PRZVZWTSK4BJ6BQ1D7S0=no-group-by-statement h_01HF40PRZVY13XM4RVETNK7E6K=grouped-by-nonpermitted-attribution-data-field h_01HF40PRZVJ9G4BAXKGW5VZMJX=grouped-by-nonpermitted-custom-data-field h_01HF42A4B20727TQGPPMP20629=restricted-function" />

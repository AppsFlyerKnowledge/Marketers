---
title: 'API maestra: métricas de adquisición de usuarios a través de API'
metadata:
  keywords:
    - Master API
    - Customizable
    - Aggregated Data
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-09-27T15:10:38Z'
  edited_at: '2026-08-12T11:49:48Z'
  id: 213223166
  locale: es
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/es/articles/213223166
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo:** Obtén KPI seleccionados de LTV, actividad, retención, cohorte y rendimiento de campañas de Protect360 por API, en formato CSV o JSON. Selecciona 1 o más aplicaciones.

## API maestra: métricas de adquisición de usuarios a través de API

API maestra:

* Te permite obtener KPI seleccionados de LTV, actividad, retención, cohorte y rendimiento de campañas de Protect360. Los KPI disponibles son los KPI equivalentes a los que se encuentran en el panel de control, Resumen general, Activity, Retención, Cohorte y Protect360.
* Se calcula diariamente. Los datos actualizados están disponibles para ti dentro de las 24 a 48 horas, dependiendo de la zona horaria específica de tu aplicación.
* Es la infraestructura sobre la que se construye la <Anchor target="_blank" href="/marketers/es/docs/pivot-table-user-metrics">tabla de pivote</Anchor> de AppsFlyer.

Para usar la API maestra, define los datos que deseas ver (similar a la implementación de la <Anchor target="_blank" href="/marketers/es/docs/pull-api-aggregate-data">Pull API</Anchor>). El resultado se devuelve como un archivo CSV o JSON.

**Para usar la API maestra**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Obtén el <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">token de API</Anchor>. Un administrador deberá recuperar el token.
2. Dale a tu desarrollador el token de API que se utilizará en el encabezado de autenticación.
3. Proporciona a tus desarrolladores los parámetros que deben introducir cuando realicen la llamada a la API, como se describe en las secciones que siguen. Los parámetros determinan en qué se enfoca el reporte, cómo se organiza, y proporcionan un marco de tiempo para la presentación de reportes.
4. Dile a tu desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-9">instrucciones de la API maestra</Anchor> en el centro de desarrolladores.
5.
   <div id="api-parameters" />

   <Accordion title="Parámetros de API">

   | Parámetro | Valor | Obligatorio |
   | --- | --- | --- |
   | id\_aplicación | * Identificador de la aplicación como se encuentra en AppsFlyer.<br />* Inserta el ID de aplicación tal como se encuentra en AppsFlyer.<br />* Agrega el prefijo **ID** a las aplicaciones iOS.<br />* Usa **todos los ID de aplicaciones** para consultar todas tus aplicaciones. | Sí |
   | desde | Límite inferior del rango de fechas de atribución de LTV.<br /><br />* Formato: cadena aaaa-mm-dd<br />* Ejemplo: `from: 2020-01-02` | Sí |
   | a | Límite superior del rango de fechas de atribución de LTV.<br /><br />* Número de días en el rango: 1 a 31 días<br />* Para un solo día: los valores `from` y `to` son idénticos.<br />* Formato: aaaa-mm-dd<br />* Ejemplo: `from: 2021-01-01, to: 2021-01-31` es 31 días. | Sí |
   | [Agrupaciones](/docs/master-api-user-acquisition-metrics-via-api#groupings) | Agrupar por parámetros, separados por una coma. Consulta la tabla Agrupaciones para ver la lista disponible. <br /><br />Ejemplo: `groupings=pid,geo` | Sí |
   | [KPIs](/docs/master-api-user-acquisition-metrics-via-api#kpis) | Lista de KPIs a incluir, cada uno separado por una coma. Consulta la tabla de KPIs a seguir para obtener una lista de KPIs.<br /><br />Ejemplo: `kpis=installs,clicks, impressions,sessions,retention_day_7` | Sí |
   | [Filtros](/docs/master-api-user-acquisition-metrics-via-api#filters-optional) | Los datos se pueden filtrar usando una o más opciones de filtro. | No |
   | [Truemoney](/docs/master-api-user-acquisition-metrics-via-api#localization) | Para devolver datos usando el conjunto de divisas específico de la aplicación, establece currency=preferred. | No |
   | [Zona horaria](/docs/master-api-user-acquisition-metrics-via-api#localization) | Para devolver datos usando la zona horaria específica de la aplicación, establece timezone=preferred.  Consulta las [reglas de localización](/docs/master-api-user-acquisition-metrics-via-api#localization) | No |
   | Formato | Por defecto, los datos de respuesta se reciben en formato de archivo CSV. Si prefieres obtener los datos en formato JSON, selecciona `format=json`. | No |

   </Accordion>

   <div id="groupings" />

   <Accordion title="Agrupaciones">

   Estas dimensiones se utilizan para recopilar los datos en grupos para permitir un análisis más fácil y preciso de la información. Puedes encontrar descripciones de estos campos <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">aquí</Anchor>.

   <table><thead><tr><th>Agrupar por<br/>nombre de API</th><th>Agrupar por nombre visible</th><th>KPIs de LTV</th><th>KPIs de retención</th><th>KPIs de actividad</th><th>Las alertas de Protect360 se actualizan a la hora UTC diaria.</th><th>cohort_<span>[x]</span>_days_total_sessions_per_user</th></tr></thead><tbody><tr><td>id_aplicación</td><td>ID de aplicación</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td>PID</td><td>Fuente de medios</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td>af_prt</td><td>Agencia</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td><td>No</td></tr><tr><td>C</td><td>Campaña</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td>af_conjunto de anuncios</td><td>Conjunto de anuncios</td><td>Sí</td><td>Sí</td><td>Sí</td><td>No</td><td>No</td></tr><tr><td>af_anuncio</td><td>Anuncio</td><td>Sí</td><td>Sí</td><td>Sí</td><td>No</td><td>No</td></tr><tr><td>af_canal</td><td>Canal</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td><td>No</td></tr><tr><td>af_siteid</td><td>ID de anunciante</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td>af_palabras_clave</td><td>Palabras clave</td><td>Sí</td><td>Sí</td><td>Sí</td><td>No</td><td>No</td></tr><tr><td>es_primario</td><td>Atribución primaria</td><td>Sí</td><td>No</td><td>Sí</td><td>Sí</td><td>No</td></tr><tr><td>af_c_id</td><td>ID de campaña</td><td>Sí</td><td>No</td><td>Sí</td><td>Sí</td><td>No</td></tr><tr><td>af_adset_id</td><td>ID de adset</td><td>Sí</td><td>No</td><td>Sí</td><td>No</td><td>No</td></tr><tr><td>id_del_anuncio_af</td><td>ID de anuncio</td><td>Sí</td><td>No</td><td>Sí</td><td>No</td><td>No</td></tr><tr><td>hora_de_instalación</td><td>Hora de la Instalación</td><td>Sí</td><td>Sí</td><td>Sí\*</td><td>Sí</td><td>Sí</td></tr><tr><td>tipo_táctil_atribuido</td><td>Tipo de Toque</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td><td>No</td></tr><tr><td>geolocalización</td><td>Geolocalización</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td colspan="7">\* En el contexto de los KPI de actividad, considera el tiempo de instalación como tiempo de evento. </td></tr></tbody></table>

   </Accordion>

   <div id="kpis" />

   <Accordion title="KPIs">

   Los KPI son las métricas utilizadas para obtener insights sobre el comportamiento de tu aplicación. Los KPI se agrupan por tipo en las pestañas que siguen.

   <div id="ltv" />

   <Accordion title="Característica">

   Valor de duración: eventos agregados segmentados por día de instalación y hasta hoy.

   | KPI del nombre de la API | Descripción |
   | --- | --- |
   | Impresiones | Número de impresiones en el periodo de tiempo seleccionado |
   | clics | Número de clics en el periodo de tiempo seleccionado |
   | instalaciones | Número de instalaciones en el periodo de tiempo seleccionado |
   | cr | Tasa de Conversión |
   | sesiones | Número de sesiones creadas por los usuarios que instalaron la app en el periodo seleccionado |
   | loyal\_users | Número de usuarios leales que instalaron la app en el periodo seleccionado |
   | loyal\_users\_rate | Usuarios leales / Instalaciones |
   | costo | Costo total en el período seleccionado. [Ver limitaciones](/docs/master-api-user-acquisition-metrics-via-api#limitations). |
   | ingresos | Ingresos de por vida generados por los usuarios que instalaron la app en el periodo seleccionado |
   | roi | Retorno de la inversión en un tiempo determinado |
   | arpu\_ltv | Ingresos medios por usuario, para los usuarios que instalaron la app en el periodo seleccionado |
   | average\_ecpi | Costo efectivo por instalación (eCPI) a lo largo de un cierto período de tiempo. Disponible solo si el costo y las instalaciones están incluidas en la llamada. |
   | desinstalaciones | Desinstalación de usuarios que instalaron la app en el periodo seleccionado |
   | uninstalls\_rate | Tasa de desinstalación |
   | event\_counter\_[event\_name] | Cantidad de ocurrencias de eventos |
   | unique\_users\_[event\_name] | Cantidad de usuarios únicos que realizaron el evento |
   | sales\_in\_usd\_[event\_name] | Ingresos declarados como parte de los hechos declarados |

   </Accordion>

   <div id="retention" />

   <Accordion title="Retención">

   Retención es una medida de cuántos usuarios existentes son activos en tu app

   **Nota:**

   * El número máximo de días de retención es de 30 días post-instalación, donde el día 0 es el día de la instalación. Esto significa que el valor [x] no puede superar 30.
   * Si solicitas retention\_day\_1, antes de que los datos de ese día estén disponibles, entonces la métrica que se devuelve se refiere a los usuarios que instalaron el día anterior. Por ejemplo, el 2 de enero, solicitas retention\_day\_1 para los usuarios que instalaron el 1 de enero. Debido a que la métrica aún no está disponible, la métrica que se devuelve se refiere a los usuarios que instalaron el 31 de diciembre.

   | KPI | Descripción |
   | --- | --- |
   | retention\_day\_[x] | Número de usuarios retenidos en el día X |
   | retention\_rate\_day\_[x] | Número de usuarios retenidos en el día X de los usuarios que instalaron la app |

   </Accordion>

   <div id="activity" />

   <Accordion title="Actividad de la app durante un intervalo de fechas seleccionado">

   Actividad de la app durante un intervalo de fechas seleccionado **Nota**: Los KPI de actividad incluyen datos unificados (UA y retargeting combinados).

   | KPI | Descripción |
   | --- | --- |
   | activity\_average\_dau | Promedio de usuarios diarios activos (DAU) en el periodo seleccionado |
   | activity\_average\_mau | Promedio de usuarios mensuales activos en el periodo seleccionado (un día MAU representa los usuarios únicos en los 30 días anteriores) |
   | activity\_average\_dau\_mau\_rate | Tasa promedio de DAU/MAU |
   | activity\_average\_arpdau | Ingresos medios por usuario diario activo: Los ingresos medios de un día determinado de todos los usuarios únicos |
   | activity\_sessions | Número de sesiones realizadas en el periodo determinado |
   | activity\_revenue | Ingresos declarados en el plazo seleccionado |
   | activity\_event\_counter\_[event\_name] | Número de eventos generados por los usuarios en el periodo de tiempo seleccionado |
   | activity\_sales\_in\_usd\_[event\_name] | Ingresos declarados como parte de los eventos declarados dentro del plazo seleccionado |
   | activity\_average\_unique\_users\_[event\_name] | Media de usuarios únicos que realizan un evento determinado en el periodo de tiempo seleccionado |

   </Accordion>

   <div id="cohort" />

   <Accordion title="Cohorte">

   Las cohortes de AppsFlyer brindan a los anunciantes la capacidad de ver y comparar diferentes métricas para múltiples cohortes en diferentes períodos.

   **Nota:**

   * **Errores de redondeo:** los KPI de cohorte por usuario se calculan utilizando cuatro decimales. Esto significa que si el valor calculado por usuario es &lt; 0,0001, entonces esto se muestra como 0. Por ejemplo, el número de usuarios es de 100 000, y los ingresos totales son de 9 USD. Los ingresos por usuario serán de 9/100 000=0,00009. Como 0,00009 &lt; 0,0001, el valor mostrado será 0.
   * **Días de cohorte**: el número máximo de días de cohorte es de 90 días post-instalación, donde el día 0 es el día de la instalación. El valor del día de cohorte [x] debe estar en el rango de 1-90.  **Nota**: cohort\_day\_0 no es compatible con la API maestra, aunque se admite en el panel de control de cohorte.
   * **API maestra frente a API de cohorte y <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">panel de control de cohorte:</Anchor>** los resultados pueden diferir debido a diferentes problemas con el manejo de las reinstalaciones y el tiempo.

   **Sesiones**

   | KPI | Descripción |
   | --- | --- |
   | cohort\_day\_[x]\_total\_sessions\_per\_user | Cohorte del día x - Sesiones acumuladas por usuario hasta el día x (incluido el día x) |
   | cohort\_day\_[x]\_sessions\_per\_user | Cohorte del día x - Sesiones del día x sólo de la cohorte |
   | cohort\_day\_[x]\_total\_sessions\_per\_user | Sustituye la especificación de los KPIs de Cohort\_day\_1\_total\_sessions\_per\_user a Cohort\_day\_x\_total\_sessions\_per\_user en la URL.<br /><br />Por ejemplo: cohort\_3\_days\_total\_sessions\_per\_user en la URL produce 3 columnas de reporte:  <br />Cohort\_day\_1\_total\_sessions\_per\_user+ Cohort\_day\_2\_total\_sessions\_per\_user+Cohort\_day\_3\_total\_sessions\_per\_user |

   **Ingresos**

   | KPI | Descripción |
   | --- | --- |
   | cohort\_day\_[x]\_total\_revenue\_per\_user | Cohorte del día X - Ingresos acumulados por usuario hasta el día x (incluido el día x) |
   | cohort\_day\_[x]\_revenue\_per\_user | Cohorte del día x - ARPU recibido el día x sólo de la cohorte |
   | cohort\_[x]\_days\_total\_revenue\_per\_user | Reemplaza especificando los KPI Cohort\_day\_1\_Total\_Revenue\_per\_user a Cohort\_day\_x\_total\_revenue\_per\_user.<br /><br />Por ejemplo: cohort\_3\_days\_total\_revenue\_per\_user en la URL produce 3 columnas de reporte:  <br />Cohort\_day\_1\_total\_revenue\_per\_user+ Cohort\_day\_2\_total\_revenue\_per\_user+Cohort\_day\_3\_total\_revenue\_per\_user |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_revenue\_per\_user | Día de cohorte x ingresos acumulativos por usuario según evento específico in-app. |
   | cohort\_day\_[x]\_event\_[eventname]\_revenue\_per\_user | Día de cohorte x ingresos por usuario según evento específico in-app. |

   **Eventos**

   | KPI | Descripción |
   | --- | --- |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_per\_user | Cohorte del día x - Eventos acumulados por usuario hasta el día x (incluido el día x) |
   | cohort\_day\_[x]\_event\_[eventname]\_per\_user | Cohorte del día x - Eventos recibidos el día x sólo de la cohorte |
   | cohort\_[x]\_days\_total\_event\_[eventname]\_per\_user | Reemplaza la especificación de los eventos de KPI a Cohort\_day\_x\_total\_events\_per\_user.<br /><br />Por ejemplo: cohort\_3\_days\_total\_events\_per\_user en la URL produce 3 columnas de reporte:  <br />Cohort\_day\_1\_total\_events\_per\_user+ Cohort\_day\_2\_total\_events\_per\_user+Cohort\_day\_3\_total\_events\_per\_user |

   </Accordion>

   <div id="protect360" />

   <Accordion title="Las alertas de Protect360 se actualizan a la hora UTC diaria.">

   **KPI de Protect360**

   | Descripción | KPI |
   | --- | --- |
   | **Instalaciones** |  |
   | Total | protect360\_total\_installs |
   | Bloqueos | blocked\_installs |
   | % de bloqueos | blocked\_installs\_rate |
   | Después de la atribución | post\_attribution\_installs |
   | % posterior a la atribución | post\_attribution\_installs\_rate |
   | Total de instalaciones fraudulentas | total\_fraudulent\_installs |
   | % de instalaciones fraudulentas | fraudulent\_installs\_rate |
   | **Instalaciones falsas** |  |
   | Bloqueo en tiempo real | real\_time\_fake\_installs |
   | Fraude posterior a la atribución | post\_attribution\_fake\_installs |
   | **Instalaciones secuestradas (Hijacked installs)** |  |
   | Bloqueo en tiempo real | real\_time\_hijacked\_installs |
   | Fraude posterior a la atribución | post\_attribution\_installs\_hijacked\_installs |
   | **Reglas de validación** |  |
   | Instalaciones bloqueadas | validation\_rules\_blocked\_installs |
   | Atribución bloqueada | validation\_rules\_blocked\_attribution |
   | **Desglose de instalaciones falsas bloqueadas** |  |
   | Lista negra de ID de sitios bloqueados | blocked\_installs\_siteid\_blacklist |
   | Lista negra de ID de sitios posteriores a la atribución | post\_attribution\_installs\_siteid\_blacklist |
   | Bots bloqueados | blocked\_installs\_bots |
   | Bots posteriores a la atribución | post\_attribution\_installs\_bots |
   | Bloqueos por anomalías de comportamiento | blocked\_installs\_behavioral\_anomalies |
   | Anomalías de comportamiento posterior a la atribución | post\_attribution\_installs\_behavioral\_anomalies |
   | Validación de instalación bloqueada | blocked\_installs\_install\_validation |
   | **Desglose de instalaciones secuestradas bloqueadas** |  |
   | Secuestro de instalaciones bloqueados | blocked\_installs\_install\_hijacking |
   | Secuestro de instalaciones posteriores de la atribución | atribución posterior a la instalación: secuestro de instalaciones |
   | Anomalías en el CTIT bloqueadas | blocked\_installs\_ctit\_anomalies |
   | Anomalías en el CTIT posteriores a la atribución | atribución posterior a la instalación: anomalías de CTIT |
   | Inundación de clics bloqueados | blocked\_installs\_click\_flood |
   | Inundación de clics posteriores de la atribución | atribución posterior a la instalación: inundación de clics |
   | **Clics** |  |
   | Total | protect360\_total\_clicks |
   | Bloqueos | blocked\_clicks |
   | % | blocked\_clicks\_rate |
   | **Eventos in-app** |  |
   | Total | protect360\_total\_in\_apps |
   | Bloqueos | blocked\_in-app-events |
   | % | blocked\_in-app-events\_rate |
   | Indicadores de granjas de dispositivos (device farm): nuevos dispositivos |  |
   | Instalaciones | fraude de instalación: total de dispositivos nuevos |
   | % de instalaciones | install\_fraud\_new\_devices\_total\_installs\_rate |
   | % de usuarios leales | install\_fraud\_new\_devices\_total\_loyal\_user\_rate |
   | **Indicadores de granjas de dispositivos: dispositivos con LAT** |  |
   | Instalaciones | fraude de instalación: total de dispositivos con LAT |
   | % de instalaciones | fraude de instalación: tasa total de instalaciones en dispositivos con LAT |
   | % de usuarios leales | fraude de instalación: tasa total de usuarios fieles en dispositivos con LAT |
   | **Indicadores de inundación de clics** |  |
   | Tasa de conversión | conversion\_rate |
   | **Indicadores de inundación de clics: CTIT** |  |
   | Más de 60 minutos | tasa de inundación de clics de más de una hora |
   | Más de 5 horas | tasa de inundación de clics de más de cinco horas |

   </Accordion>

   #### KPIs calculados

   Ademas de los KPIs descritos anteriormente, puedes añadir KPIs calculados a tus reportes de master API. Esto te permite tener tus propios reportes calculados incluidos en tus tus reportes de master API.

   Puedes insertar cualquier número de objetos de KPI integrados en las fórmulas KPI calculadas. Cada objeto de KPI de cálculo incluye una clave y un valor. La clave es el nombre que le das al KPI y el valor es la fórmula del KPI.

   Se admiten los operadores aritméticos estándar: suma (+) codificada como %2b, resta (-), multiplicación (*), división (/) codificada como %2f.

   Las claves de campo KPI calculadas **deben** comenzar con "calculated\_kpi\_", seguido de cualquier cadena válida, como, "calculated\_kpi\_purchaserate".

   > 📄 **Ejemplo**
   >
   > **Retención combinada de los primeros tres días**
   >
   > ```http
   > kpis=installs,loyal_users_rate&calculated_kpi_3days_retention=
   > retention_day_1%2Bretention_day_2%2Bretention_day_3
   > ```
   >
   > **Ingresos medios por impresión**
   >
   > ```http
   > kpis=installs&calculated_kpi_rev_per_impression=revenue%2Fimpression
   > ```
   >
   > **Cohort del ROI del día 7**
   >
   > ```http
   > kpis=installs,roi,arpu_ltv,cost,revenue&calculated_kpi_roi_day_7=
   > (cohort_day_7_total_revenue_per_user-average_ecpi)%2Faverage_ecpi
   > ```

   </Accordion>

   <div id="filters-optional" />

   <Accordion title="Filtros (opcional)">

   | Parámetro | Descripción | Ejemplo | Obligatorio? |
   | --- | --- | --- | --- |
   | PID | * Se utiliza para seleccionar las filas, en las que se muestran las fuentes de medios especificadas.<br />* Se admite la selección múltiple separada por comas. | pid=organic,applovin\_int | No |
   | C | * Se utiliza para filtrar por nombre de campaña.<br />* Se admite la selección múltiple separada por comas. | c=my\_sample\_campaign | No |
   | af\_prt | * Se utiliza para filtrar por nombre de agencia.<br />* Se admite la selección múltiple separada por comas. | af\_prt=moburst | No |
   | af\_canal | * Se utiliza para filtrar por nombre de canal.<br />* Se admite la selección múltiple separada por comas. | af\_channel=Instagram | No |
   | af\_siteid | * Se utiliza para filtrar por ID de anunciante.<br />* Se admite la selección múltiple separada por comas. | af\_siteid=12345678 | No |
   | geolocalización | * Se utiliza para filtrar por país.<br />* Se admite la selección múltiple separada por comas. | geo=US,DE | No |

   </Accordion>

   <div id="localization" />

   <Accordion title="Localización">

   La divisa local y la zona horaria específica de la aplicación se establecen en la <Anchor target="_blank" href="/marketers/es/docs/app-settings">página de configuración de la aplicación</Anchor>. Los datos de la API maestra pueden extraer los datos utilizando la divisa y la zona horaria predeterminadas del sistema o usando la región y la divisa específicas de la aplicación.

   Se aplica lo siguiente:

   * El uso de la zona horaria/divisa específica de la aplicación solo se admite si todas las aplicaciones tienen la misma zona horaria/divisa. De lo contrario, se utilizan UTC y USD. La zona horaria y la divisa son independientes. Eso significa que, si la divisa de todas las aplicaciones es la misma pero las zonas horarias no lo son, entonces puedes usar la divisa específica de la aplicación, pero no la zona horaria específica de la aplicación.
   * Si la zona horaria preferida se cambió en el panel de control del período solicitado, el reporte generado contiene valores a partir del cambio de zona horaria más reciente.

   Utiliza los siguientes parámetros para seleccionar la configuración específica de la aplicación. **Nota**: Si no usas los parámetros preferidos, obtienes la configuración predeterminada, que es USD para la divisa y UTC para la zona horaria.

   | Parámetro | Descripción | Ejemplo | Obligatorio? |
   | --- | --- | --- | --- |
   | divisa | Los valores monetarios están en la divisa específica de la app | divisa=preferida | No |
   | huso horario | La zona horaria utilizada coincide con la zona horaria específica de la aplicación. | huso horario=preferido | No |

   </Accordion>

## Información adicional

<div id="limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Datos de costos | <ul><li>La disponibilidad de diferentes dimensiones de costo, es decir, conjunto de anuncios, anuncio, geolocalización, canal e ID de sitio, <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">dependen de la red de publicidad</Anchor>.</li><li>Para obtener el eCPI: si los datos de costos están disponibles, incluye tanto las instalaciones como el costo en la llamada.</li><li>En general, todas las fuentes, incluidos los medios propios, que utilizan enlaces de AppsFlyer y tienen el parámetro de costo en los enlaces, soportan completamente los datos de costos, independientemente de las dimensiones solicitadas. Las redes de autorreporte, con API propia, suelen soportar datos de costos con solo algunas de las dimensiones disponibles. Por ejemplo, <Anchor target="_blank" href="/marketers/es/docs/meta-ads-faq#what-are-the-limitations-of-facebook-cost-data-in-master-api">Anuncios de Meta</Anchor> no admite la agrupación por geolocalización y canal en la misma llamada. Se admite la agrupación por cualquiera de ellos por separado.</li><li>Las campañas que tienen datos de costos, pero no datos de instalaciones en el pasado reciente (aprox. 7 días), no están disponibles a través de la API maestra.</li></ul> |
| Agrupaciones | Las agrupaciones específicas solo están disponibles para los KPI de LTV, KPI de actividad o retención. La API devuelve N/A cuando los datos de un KPI específico no están disponibles. Por ejemplo, al solicitar retention\_rate\_day\_7 agrupado por af\_channel, devuelve N/A. |
| Dimensiones | Para los datos de cohortes, si una agencia participa en la atribución, la fuente de medios devuelta es el nombre de la agencia |
| Máximo de filas por reporte | 200 000 |
| Nombres de los eventos | Actualmente, la API maestra no admite nombres de eventos que incluyan una barra inclinada `/` . Para superar esta limitación, evita el uso de `/` en nombres de eventos. |
| Tiempo de procesamiento | Seleccionar más de una aplicación aumenta el tiempo de procesamiento y la respuesta puede tardar más tiempo. |
| Rango de fechas | La granularidad del período es diaria. |
| Agencias | API maestra no disponible |
| Redes de publicidad | API maestra no disponible |
| Historial de datos | <ul><li>Datos de LTV: 5 años</li><li>Datos de cohortes (cohorte diaria): 2 años</li><li>Datos de actividad: 3 años</li></ul> |
| Reorientación | <ul><li>No está soportado.</li><li>Excepción: Los KPI de actividad para el tráfico posterior al 1 de febrero de 2025 incluyen datos unificados (UA y retargeting juntos).</li></ul> |

</Accordion>

<div data-zendesk-anchors="master-api%E2%80%94user-acquisition-metrics-via-api=api-maestra-m%C3%A9tricas-de-adquisici%C3%B3n-de-usuarios-a-trav%C3%A9s-de-api h_01JJVMXKACJ2V4YZFGYXVB8FQF=api-maestra-m%C3%A9tricas-de-adquisici%C3%B3n-de-usuarios-a-trav%C3%A9s-de-api h_01JJVMXKACZDXPQG4271HFYWCE=api-parameters h_01JJVMXKAEXMKQQRT0RT6N8P74=groupings h_01JJVMXKAEHM0871GBQHZENRXA=kpis h_01JK2ZEH32Y92Y553540XDYZFA=ltv h_01JK2ZEH32A08EEDZEWFSX3ZFS=retention h_01JK2ZEH3219694E4PFPZ8ZXZF=activity h_01JK2ZEH32NCWZWKTDS0J6DFS2=cohort h_01JK2ZEH32Q7B6RCQYXNHM8KGK=protect360 calculated-kpis=kpis-calculados h_01JJVMXKAFW1TEE35GK9B20TRP=kpis-calculados h_01JJVMXKAFZDPNXKAZCBQ27DBD=ejemplo h_01JJVMXKAFWA4D47MH7VSXKN14=filters-optional h_01JJVMXKAFSBXJ9EJJ16BF8H7Q=localization additional-information=informaci%C3%B3n-adicional h_01JJVMXKAFFW2G3N7188DHYCB8=informaci%C3%B3n-adicional h_01JJVMXKAF25YX092NE9DV9862=limitations" />

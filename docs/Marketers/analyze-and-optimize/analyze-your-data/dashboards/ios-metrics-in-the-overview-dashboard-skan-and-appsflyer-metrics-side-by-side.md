---
title: >-
  Métricas de iOS en el panel de control de resumen general (métricas de SKAN y
  AppsFlyer una al lado de la otra)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-08-02T07:18:18Z'
  edited_at: '2026-08-12T11:50:45Z'
  id: 4404976682257
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/4404976682257
---
> **En resumen:** Consulta las métricas de los marcos de atribución de SKAdNetwork (SKAN) y AppsFlyer una al lado de la otra en el panel de control de resumen general. Identifica el marco con la mejor métrica de rendimiento de la campaña para ti y, a continuación, aprovéchalo para obtener información y optimizar las campañas.

**Las métricas de atribución se muestran una al lado de la otra en el panel de control de resumen general de la versión 2.0**

![SBSDB.png](https://files.readme.io/550c465c329eac484d2b2e5a65c8f48831c350c3c4b967315e3b2059ab95a36d-4409263804049.png)

<div id="finding-the-best-ios-14-campaign-performance-metrics" />

## Cómo encontrar las mejores métricas de rendimiento de las campañas de iOS 14+

A partir de iOS 14+, los marcos de atribución de SKAN y de atribución de <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">AppsFlyer</Anchor> generan métricas de rendimiento de la campaña. Se atribuyen de manera diferente, tienen rasgos y limitaciones diferentes y, a menudo, se producen discrepancias entre ellos. Por ejemplo, SKAN no contiene métricas de las campañas de Apple Search Ads ni de los medios propios. Por el contrario, las métricas de AppsFlyer de las SRN no incluyen las instalaciones de usuarios que no han dado su consentimiento. <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">Además, SKAN mide el rendimiento durante un período inicial posterior a la instalación de 1 a 3 días, mientras que AppsFlyer mide el valor de vida útil (LTV).</Anchor>

En paralelo, puedes ver el rendimiento de la campaña utilizando los datos proporcionados por ambos marcos. Compara las métricas de cada marco y decide qué métrica representa mejor el rendimiento real de la campaña.

**Limitación del intercambio de datos**: Las métricas de SKAN del panel de control de resumen general no están disponibles para las agencias y redes de publicidad.

<mark>Si las métricas de SKAN no aparecen en el panel de control, debes actualizar la [configuración de la tabla](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#display-skan-metrics-in-the-table).</mark>

La vista en paralelo proporciona información sobre las métricas de la campaña. Utilízalo para evaluar las métricas de rendimiento de la campaña en términos de:

* [Precisión](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-precision):
  * ¿Cuántas descargas generó una campaña?
  * ¿Por qué son diferentes las métricas de SKAN y AppsFlyer?
* [Efectividad:](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-effectiveness) ¿Cuántos usuarios se convirtieron y cuál es el ROI?
* [Eficiencia](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-efficiency): ¿Qué es la campaña eCPI?

Este artículo contiene una guía basada en nuestro conocimiento del mercado y en nuestras observaciones sobre cómo interpretar los datos y obtener información útil a partir de ellos. Ten en cuenta que el panorama de marketing de cada aplicación es diferente y valida nuestras directrices en el contexto de tu aplicación.

**Terminología**

* **Instalación**:
  * AppsFlyer Nuevas instalaciones y reatribuciones
  * SKAN: Nuevas instalaciones y descargas
* **Real:** Actual significa la métrica que mejor representa los datos, aunque es posible que no incluya todos los datos.
* **Usuarios que dan su consentimiento** Un usuario de iOS 14+ que concede la <Anchor target="_blank" href="/marketers/es/docs/about-att-and-skan#att-principles">autorización de AT&T</Anchor> tanto en el editor como en la aplicación anunciada.

<div id="campaign-precision" />

<Accordion title="Precisión de la campaña">

| Pregunta | ¿Cuántas instalaciones reales se atribuyen a una campaña? |
| --- | --- |
| Síntoma | Las métricas de instalación difieren entre los marcos. Cada marco cuenta algunas de las instalaciones y puede haber superposiciones y discrepancias entre los marcos. |
| Remedio | <ul><li>Compara las métricas de instalación de los marcos a nivel de campaña.</li><li>Se considera que el marco que informa del mayor número de instalaciones tiene la métrica más precisa, aunque es posible que esta métrica no incluya el 100 % de las atribuciones.</li></ul> |
| Ejemplo | ![S2Sinstalls.png](https://files.readme.io/9599ef8ac37aa1bc0da46112c1a7d6b4c42f3ff82efda0d0e4b47b8bddc6b52a-4406110225425.png)<br /><br />En la tabla, se resalta el marco que genera el mayor número de instalaciones. Este es el número real de instalaciones que ha generado la campaña. |
| Consejo | Puedes automatizar el proceso de establecer qué métrica es más alta importando la tabla a una hoja de cálculo. Utiliza la función @max y el formato condicional para identificar el marco que informa de la mayor cantidad de instalaciones. |

| Pregunta | ¿Por qué son diferentes las métricas de SKAN y AppsFlyer? |
| --- | --- |
| Síntoma | Las métricas de instalación son diferentes. |
| Explicación | <ul><li>El marco de AppsFlyer determina las instalaciones de acuerdo con el <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">modelo de atribución</Anchor> de AppsFlyer, que abarca diferentes tipos de campañas y métodos de atribución, mientras que SKAN mide las instalaciones en el contexto de las campañas pagas de aplicación a aplicación.</li><li>Por lo general, las métricas SKAN de las instalaciones de campañas de SRN son más altas que las de AppsFlyer, porque AppsFlyer solo registra a los usuarios que dan su consentimiento.</li><li>En el caso de redes que no son SRN (redes de clics), a menudo hay una alineación mucho más estrecha entre las métricas por marco.</li></ul> |

</Accordion>

<div id="campaign-effectiveness" />

<Accordion title="Efectividad de la campaña">

| Pregunta | ¿Cuántos usuarios se convirtieron y cuál es el ROI? |
| --- | --- |
| Consideraciones | <ul><li>La determinación de las métricas de ingresos y tasas de conversión requiere que el rendimiento de los usuarios se mida a lo largo del tiempo.</li><li>SKAN limita la medición a 12 a 72 horas después de la instalación, mientras que la medición de AppsFlyer es ilimitada (LTV).</li><li>La atribución de AppsFlyer solo contiene métricas de usuarios que han dado su consentimiento.</li></ul> |
| Remedio | Considera si las métricas de atribución de AppsFlyer representan con precisión a toda la población de usuarios (incluidos los usuarios reportados a través de SKAN). Si es así, úsalas para extrapolar las métricas de eficacia de la campaña, como las métricas de ROI y tasa de conversión.<br /><br />**Para calcular el número de usuarios que han realizado la conversión:**<ol><li>Usa la métrica de tasa de conversión de AppsFlyer (por evento).</li><li>Multiplica la tasa de conversión por el número real de usuarios, obtenido tal y como se describe en la sección de precisión de la campaña.</li></ol>**Para calcular los ingresos y el ROI de la campaña:**<ol><li>Derive el número real de usuarios (a) tal y como se describe en la sección de precisión de la campaña.</li><li>Usa la métrica ARPU (b) proporcionada por la atribución de AppsFlyer.</li><li>Calcula los ingresos de la campaña con la fórmula: a * b</li><li>Usa el costo de la campaña tal y como se muestra en el panel de control.</li><li>ROI = (ingresos de la campaña - coste de la campaña)/(coste de la campaña * 100)</li></ol> |
| Ejemplo | **Calcular el ROI**<br /><br />![SBSCost.png](https://files.readme.io/052c862e0a93c4e938f84b22e04e8b088bf50acbf047b821ca6cd20f5b9eae57-4409270882577.png)<br /><br />**Ejemplo de cálculo del ROI para la campaña a:**<ol><li>Número supuesto de usuarios 2000</li><li>Métrica de ARPU en el panel de control: 0,76 USD</li><li>Ingresos de la campaña = 0,76 USD = 1.520,00 USD</li><li>Costo de campaña : 905,88 USD</li><li>ROI= (1.520,00 USD - 905,88 USD) / (905,88 USD * 100) = 68 %</li></ol> |
| Consejo | Utiliza tu herramienta de análisis de productos de BI para comparar el rendimiento de los usuarios que dan su consentimiento con el de toda la población de usuarios de la aplicación. Si los resultados son diferentes, debes ajustar el cálculo de la reparación para tener en cuenta este hecho. |

</Accordion>

<div id="campaign-efficiency" />

<Accordion title="Eficiencia de campañas">

| Pregunta | ¿Qué es el eCPI real de la campaña? |
| --- | --- |
| Síntoma | Las métricas relacionadas con los costos de las campañas, como el eCPI, son engañosas porque se basan en un número preciso de usuarios. |
| Remedio | <ol><li>Derive el número real de usuarios (a) tal y como se describe en la sección de precisión de la campaña.</li><li>Calcule el eCPI mediante la siguiente fórmula: eCPi = coste/(a)</li></ol> |
| Ejemplo | ![mceclip1.png](https://files.readme.io/98fc80d1e995ba8ef0cce267fa12f22d48a77d7e25db4add1108144c6de7136d-4406111715217.png)<ul><li>Las instalaciones reales se determinan utilizando el marco que tiene el mayor número de instalaciones.</li><li>El eCPI se calcula mediante la fórmula: costo/número de instalaciones.</li></ul> |

</Accordion>

<div id="using-side-by-side" />

## Uso en paralelo

<div id="principles" />

<Accordion title="Principios">

* Contiene las instalaciones informadas por ambos marcos de atribución
* Usa la vista unificada, en Resumen general V2.0, para asegurarte de que todos los datos disponibles en el contexto de una campaña se muestren y no se oculten inadvertidamente mediante el filtrado
* Los datos de SKAN son los mismos que los disponibles en el panel de control de SKAN
* Para reducir las discrepancias debidas a las diferencias de tiempo entre los marcos, establece un intervalo de fechas en el panel de control de la siguiente manera:
  * Duración: Mínimo 7 días
  * Fecha más reciente:
    * De 3 a 5 días antes de la fecha actual. El rango depende de tu ventana de actividad
    * Si publicas campañas de Google Ads, la fecha más temprana debe ser 8 días antes de la fecha actual

</Accordion>

<div id="display-skan-metrics-in-the-table" />

<Accordion title="Mostrar las métricas de SKAN en la tabla">

**Para mostrar las métricas de SKAN en la tabla**:

1. Haz clic en ⚙ (configuración de la tabla).   
   Se abre la ventana de selección de métricas.

   ![SelectSkan.png](https://files.readme.io/6b60fa8e2d10a1b61b1bfb4b7a968adb5ee16086d80c9cc8bc097b8e8ed77b51-4408473842833.png)
2. Haz clic en **Atribución de SKAN**.
3. Haz clic en **Instalaciones de SKAN**.
4. Haz clic en **Ingresos de SKAN.**
5. [Opcional] Para añadir o eliminar un evento in-app:
   1. Selecciona Eventos In-App.
   2. Agrega o elimina los eventos in-app necesarios.
6. Haz clic en**Aplicar**.   
   Se muestran las métricas y los eventos in-app seleccionados.

</Accordion>

<div id="timerelated-differences" />

<Accordion title="Diferencias relacionadas con el tiempo">

<table><thead><tr><th>Diferencia</th><th>AppsFlyer</th><th>SKÁN</th></tr></thead><tbody><tr><td>Historial de datos</td><td><p>Disponible; sin limitación</p></td><td><p>Disponible; sin limitación. </p></td></tr><tr><td>Zona horaria</td><td><p>Zona horaria específica de la aplicación</p></td><td>UTC </td></tr><tr><td>Actualización de datos </td><td>Se actualiza de forma continua con una latencia de hasta 60 minutos</td><td><p>Las actualizaciones se hacen todos los días antes de las 08:00 UTC. </p><p><span>La latencia depende de la duración de la ventana de actividad. Valor predeterminado: De 2 a 5 días; en el caso de las campañas publicadas por la campaña de Google Ads, hasta 13 días.</span></p></td></tr><tr><td>Fecha de instalación</td><td>Fecha en que se produjo la instalación </td><td>Derivado de la hora de llegada del postback. (1) </td></tr><tr><td>Duración de la medición</td><td>Ilimitado; basado en LTV</td><td><p>Limitado a la duración de la ventana de actividad de 12 a 72 horas. Predeterminado: 24 horas</p></td></tr><tr><td>Ventana de atribución retrospectiva</td><td><ul><li>Determinado por el anunciante o el SRN</li><li>Haz clic para abrir: 7 días</li></ul></td><td><ul><li>Determinado por Apple</li><li>Clic para descargar 30 días.</li><li>Descargar para abrir: 60 días</li></ul></td></tr><tr><td colspan="3"><p>Notas</p><p>(1) Actualizaciones de datos de Google Ads con un retraso de hasta 13 días.</p></td></tr></tbody></table>

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Costo, clics e impresiones">

Las redes de publicidad proporcionan métricas de costos, clics e impresiones a AppsFlyer que son comunes a ambos marcos. No hay segregación de estas métricas por marco.

En el caso de las métricas de costos, se aplica lo siguiente:

* Se actualiza 6 veces al día, en promedio cada 4 horas.
* AppsFlyer registra la primera interacción (clic o impresión) asociada a una campaña; después, se muestra el costo de la campaña asociado a la interacción.
* Dado que las instalaciones de SKAN se notifican entre 72 y 120 horas después de la apertura de la primera aplicación, espera ver las métricas de costos algunos días antes de que se asocien a las instalaciones.
* En el caso de las instalaciones desde Google Ads, el retraso puede ser de hasta 13 días.

</Accordion>

<div id="data-scope-differences" />

<Accordion title="Diferencias del alcance de los datos">

| Diferencia | AppsFlyer | SKÁN |
| --- | --- | --- |
| Plataforma | Todos | apps de iOS, |
| Tipos de atribución | <ul><li>Instalaciones</li><li>Reenganches</li><li>Re-Atribuciones</li></ul> | <ul><li>Instalaciones</li><li>Redescargas</li></ul> |
| Ingresos por publicidad | Disponible | <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">Limitado; depende del partner de mediación</Anchor>. |
| Apple Search Ads | Disponible | No se aplica a la atribución de SKAN |
| Medios propios | Disponible | No se aplica a la atribución de SKAN |
| De la web a la aplicación | Disponible | Disponible para la atribución SKAN 4 |
| Truemoney | Divisa específica de la aplicación | USD (Dólar estadounidense) |

</Accordion>

<div id="matching-considerations" />

<Accordion title="Consideraciones sobre la correspondencia">

<table><thead><tr><th>Consideraciones</th><th>AppsFlyer</th><th>SKÁN</th></tr></thead><tbody><tr><td>Transparencia de agencias</td><td>Compatible</td><td><p>Atribuido a la fuente multimedia que trajo la instalación. Las agencias pueden indicar a las fuentes de medios que pongan su <em><a href="/partners/es/docs/getting-started-agency-onboarding" target="_blank">prt</a>,</em> como prefijo a los nombres de las campañas, en cuyo caso puedes identificar el tráfico dirigido por las agencias.</p></td></tr><tr><td>Cambios del nombre de campaña</td><td><ul><li>Compatible</li><li>El nombre más reciente publicado por la red de publicidad determina el nombre de la campaña utilizado para todas las instalaciones asociadas a un identificador de campaña determinado. Esto incluye las instalaciones grabadas anteriormente. </li></ul></td><td><ul><li>No compatible</li><li>Se utiliza el nombre de la campaña que aparece cuando el usuario instala la aplicación. Esto no cambia con el tiempo. En consecuencia, se pueden asociar varios nombres con un ID de campaña determinado. </li></ul></td></tr><tr><td>Dimensiones admitidas</td><td>Ninguna limitación</td><td><p><strong>Disponible</strong>: Geolocalización, anuncio, ID de anuncio, canal, conjunto de anuncios, ID de sitio.</p><p><strong>Agencia:</strong> No en este momento.</p><p>Si seleccionas una dimensión que no es compatible, los datos de SKAN se muestran como ninguno.</p></td></tr><tr><td>Métricas de instalación de SRN</td><td>Limitado a los usuarios que dan su consentimiento; por lo tanto, se espera que las métricas informadas por AppsFlyer sean inferiores a las métricas informadas por SKAN y a las métricas proporcionadas por el propio SRN. </td><td>Todas las instalaciones atribuidas a SKAN. Suele ser superior a la métrica de AppsFlyer. </td></tr><tr><td>Campañas SKAN ocultas</td><td colspan="2"><p>La tabla del panel de control contiene un número limitado de filas. Las filas restantes se combinan en la fila designada como <em>otras</em>.</p><p>Para ver un desglose de esta fila, exporta toda la tabla a una hoja de cálculo. </p></td></tr></tbody></table>

</Accordion>

<div id="dimensions-available" />

<Accordion title="Dimensiones disponibles:">

Las siguientes dimensiones están disponibles en la vista en paralelo:

* Fuente de medios
* Nombre de la campaña
* ID de campaña
* Fecha
* Tipo de atribución

</Accordion>

<div data-zendesk-anchors="finding-the-best-ios-14-campaign-performance-metrics=c%C3%B3mo-encontrar-las-mejores-m%C3%A9tricas-de-rendimiento-de-las-campa%C3%B1as-de-ios-14 h_01HYAQAR84BP9MRRXP7BPPDJ4N=c%C3%B3mo-encontrar-las-mejores-m%C3%A9tricas-de-rendimiento-de-las-campa%C3%B1as-de-ios-14 h_01HYAQAR856G6VARSH746SJB5Z=campaign-precision h_01HYAQAR856JT2JX28SE3QY7VZ=campaign-effectiveness h_01HYAQAR85GZN1RZYNV2MV7DAP=campaign-efficiency using-sidebyside=uso-en-paralelo h_01HYAQAR85FY6K8R574GWFQW91=uso-en-paralelo h_01HYAQAR85Z09SXSE8JGTG5AMF=principles h_01HYAQAR85V6CD29T9AY9XYX0Z=display-skan-metrics-in-the-table h_01HYAQAR85QSTB8QZPGMEV6MR9=timerelated-differences h_01HYAQAR85A03KNAHC5TEAZAZK=cost-clicks-and-impressions h_01HYAQAR85SPYQKDFP3CRGW5FN=data-scope-differences h_01HYAQAR85FSAXQ25X16N6XQEW=matching-considerations h_01HYAQAR85XF7CEG6F7PC44F1C=dimensions-available" />

---
title: >-
  Boletín: reporte de costos completos para las campañas no móviles de Meta en
  ROI360
deprecated: false
hidden: false
metadata:
  keywords:
    - Cost
    - ROI360
    - Meta
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
  created_at: '2026-11-01T08:56:35Z'
  edited_at: '2026-11-03T02:05:06Z'
  id: 52545079276561
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/52545079276561
---
| **Sección.** | **Detalles** |
| --- | --- |
| **¿Qué hay de nuevo?** | Después de esta actualización, ROI360 ahora reporta el costo completo de las campañas no móviles de Meta en los reportes de canal y geolocalización, y el número de clics reportados de Meta ha aumentado. Este cambio resuelve la discrepancia conocida entre el dashboard de Meta y los reportes de geolocalización y canal.<br /><br />Meta reporta el costo de las campañas no móviles sin App ID. ROI360 atribuye este costo a las aplicaciones que tienen atribución en AppsFlyer y lo reparte entre esas aplicaciones en proporción a las conversiones de cada una. Este enfoque se aplica tanto al reporte de geolocalización como al de canal. Después de la actualización:<ul><li>El costo a nivel de campaña es el mismo en los reportes de geolocalización y canal porque ambos reportes incluyen todos los costos que Meta reporta.</li><li>El costo a nivel de aplicación puede diferir entre los reportes de geolocalización y canal. ROI360 reparte el costo entre aplicaciones haciendo coincidir el desglose del costo con el desglose de conversiones. Como los dos reportes usan una granularidad distinta (geolocalización y canal), el desglose de conversiones por aplicación también difiere, por lo que el costo asignado a cada aplicación también es diferente.</li></ul> |
| **Fecha de entrada en vigor** | 9 de noviembre de 2026<br /><br />Los cambios se implementan gradualmente. Se aplican a los datos nuevos en adelante y completan los datos históricos de los últimos 7 días. |
| **Lo que debes hacer** | Si aplicas una lógica interna para completar el costo de Meta en los reportes de canal y geolocalización, elimina esta lógica cuando la actualización se ponga en marcha para evitar reportar el costo de más. |
| **Lo que debes saber** | **Reporte de canal**<ul><li>Cambio: Hoy, ROI360 solo mide el costo que se asigna claramente a una aplicación móvil (iOS o Android). Después de esta actualización, ROI360 reporta el costo total de las campañas no móviles de Meta y resuelve las aplicaciones mediante datos de atribución y lógica de división de costos. Esto cierra la discrepancia conocida con Meta.</li><li>Impacto: el costo total en el reporte de canal aumenta en los niveles de campaña y aplicación para coincidir con tu gasto real en Meta.</li></ul>Para ver un ejemplo, consulta el [ejemplo de reporte de canal](#REPLACE_CHANNEL_EXAMPLE_ID).<br /><br />**Reporte de geolocalización**<ul><li>Cambio: Hoy, el costo a nivel de geolocalización para las campañas no móviles de Meta solo está disponible para clientes beta. Después de esta actualización, el costo a nivel de geolocalización está disponible para todos los clientes en el dashboard y en el reporte de geolocalización de Cost ETL. ROI360 asigna los costos entre geolocalizaciones y aplicaciones atribuidas mediante lógica de división de costos.</li><li>Impacto: el costo total medido de Meta con granularidad de geolocalización aumenta en los niveles de campaña y aplicación.</li></ul>Para ver un ejemplo, consulta el [ejemplo de reporte de geolocalización](#REPLACE_GEO_EXAMPLE_ID).<br /><br />**Métrica de clics**<ul><li>Cambio: **después de esta actualización, ROI360 usa una métrica de clics de Meta diferente.** Hoy, ROI360 usa la métrica de clics en línea de Meta, que mide solo el número de clics en enlaces a destinos o experiencias seleccionados, dentro o fuera de las propiedades de Meta. Después de esta actualización, ROI360 usa la métrica de clics de Meta, que mide el número total de clics en anuncios. Esto puede incluir clics en enlaces en línea, Me gusta en la página, comentarios en publicaciones y respuestas a eventos.</li><li>Impacto: aumentan los clics que reporta Meta.</li></ul> |

<div id="examples" />

## Ejemplos

<div id="channel-report-example" />

### Ejemplo de informe de canal

**Cuando el dashboard de Meta muestra el costo por dispositivo de impresión:**

| **Dispositivo de impresión** | **Coste** |
| --- | --- |
| iPhone | $100 |
| Android | $200 |
| Ordenador | $El 50 |
| **Total** | **$350** |

**Antes de la actualización, ROI360 reporta un costo parcial:**

| **Identificación de la aplicación** | **Coste** |
| --- | --- |
| id12345 | $100 |
| android.com | $200 |
| **Total** | **$300** |

ROI360 reporta solo el costo que se asigna claramente a las aplicaciones móviles. No reporta el resto. En este ejemplo, se trata de los $50 que Meta devolvió con dispositivo de impresión = ordenador.

**Después de la actualización, ROI360 reporta todos los costos:**

| **Identificación de la aplicación** | **Relación** | **Coste** |
| --- | --- | --- |
| id12345 | 0.3 | $105 |
| android.com | 0.6 | $210 |
| www.test.com | 0.1 | $35 |
| **Total** |  | **$350** |

ROI360 reporta todo el costo a nivel de campaña, en línea con los reportes de Meta. Divide el costo entre las aplicaciones atribuidas (móviles y no móviles).

<div id="geo-report-example" />

### Ejemplo de reporte por geolocalización

**Cuando el dashboard de Meta muestra el costo por geolocalización:**

| **Geolocalización** | **Coste** |
| --- | --- |
| Reino Unido | $200 |
| BE | $150 |
| **Total** | **$350** |

**Después de la actualización, ROI360 reporta el costo por geolocalización y aplicación:**

| **Geolocalización** | **Identificación de la aplicación** | **Coste** |
| --- | --- | --- |
| Reino Unido | id12345 | $El 50 |
| Reino Unido | android.com | $150 |
| BE | id12345 | $El 50 |
| BE | android.com | $100 |
| **Total** |  | **$350** |

<div data-zendesk-anchors="h_01M6BT1WAPZBCJQMGSFEYNX4D4=ejemplos h_01M6BT1WAPJHDGF5N5SACGDWAX=ejemplo-de-informe-de-canal h_01M6BT1WAP2PW79ZZPM4WD7SKK=ejemplo-de-reporte-por-geolocalizaci%C3%B3n" />

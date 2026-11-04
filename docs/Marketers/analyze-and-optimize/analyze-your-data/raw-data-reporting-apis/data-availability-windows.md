---
title: Períodos de disponibilidad de los datos
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2022-01-04T03:33:13Z'
  edited_at: '2026-08-12T11:51:58Z'
  id: 4415473374865
  locale: es
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/es/articles/4415473374865
---
> **En resumen:** La disponibilidad de los datos depende del tipo de reporte y del período de disponibilidad definido.

<div id="data-availability-windows" />

## Períodos de disponibilidad de los datos

* Los términos **período de disponibilidad** y **retención de datos** tienen significados diferentes. La <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">retención de datos</Anchor> corresponde al período durante el que conservamos los raw data en nuestros servidores y tiene una duración mayor que el período de disponibilidad.
* La duración del período depende de tu paquete de suscripción.
* Este artículo no se aplica a <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Data Locker</Anchor>.

<div id="raw-data-availability-window" />

### Período de disponibilidad de los raw data

El período de disponibilidad limita los raw data proporcionados por Pull API y la página de exportación de raw data. La duración del período depende del tipo de reporte, como se detalla en la siguiente tabla.

| Tipo de evento del reporte | Ejemplos de tipos de reportes | Período de disponibilidad predeterminado |
| --- | --- | --- |
| Atribuciones | Instalaciones orgánicas, instalaciones no orgánicas, conversiones de retargeting y desinstalaciones | 60 de los últimos 90 días |
| Eventos in-app | Eventos orgánicos in-app, eventos no orgánicos in-app y eventos in-app de retargeting | 31 de los últimos 90 días |

<div id="aggregated-data-availability-window" />

### Período de disponibilidad de los datos agregados

Un período de disponibilidad limita los datos proporcionados por Pull API y la página de exportación de datos agregados. La duración del período depende del tipo de reporte, como se detalla en la siguiente tabla.

| Reporte | Ventana de disponibilidad |
| --- | --- |
| Reportes agregados | 25 meses (2 años + 1 mes), <Anchor target="_blank" href="/marketers/es/docs/bulletin-aggregated-ltv-data-availability">a partir de la primera instalación de la app</Anchor> |

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/report-generation-quotas-rate-limitations">Cuotas de generación de reportes</Anchor>

<div data-zendesk-anchors="data-availability-windows=per%C3%ADodos-de-disponibilidad-de-los-datos h_01HE0FT9CNECNKYMVX9ZJJ9DNV=per%C3%ADodos-de-disponibilidad-de-los-datos raw-data-availability-window=per%C3%ADodo-de-disponibilidad-de-los-raw-data h_01HE0FT9CNS4N1GD1AYRBSRWPF=per%C3%ADodo-de-disponibilidad-de-los-raw-data aggregated-data-availability-window=per%C3%ADodo-de-disponibilidad-de-los-datos-agregados h_01HE0FT9CPW91ASDH9MEW083ZH=per%C3%ADodo-de-disponibilidad-de-los-datos-agregados h_01HE7S7VH4PC6FQAYKP6A0G4YY=consulta-tambi%C3%A9n" />

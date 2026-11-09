---
title: Datos modelados SKAN
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T12:02:02Z'
  edited_at: '2026-08-12T12:21:41Z'
  id: 7086372479505
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/7086372479505
---
> **De un vistazo**: Los modelos de AppsFlyer agregan datos que los reportes básicos de SKAdNetwork no pueden proporcionar.

<div id="overview" />

## Visión general

Los reportes de SKAdNetwork (SKAN) pueden ser limitados porque:

* SKAN se basa en valores de conversión (CV) que están limitados a 6 bits, lo que da lugar a 64 valores posibles (0-63).
* En ocasiones, Apple retiene el CV real (y devuelve los datos como "null") para preservar la privacidad del usuario.
* Los datos solo están disponibles dentro de una ventana de actividad de entre 12 y 72 horas y no se conoce el valor total de la vida útil (LTV).

Los datos modelados SKAN resuelven estos problemas:

* AppsFlyer utiliza el aprendizaje de máquina, la estadística bayesiana, los datos reportados por AppsFlyer y los datos de SKAN para modelar puntos de datos ocultos.
* Los anunciantes obtienen una imagen más completa del rendimiento del LTV de la aplicación y la campaña.

**Nota**: Cuando cambias tu esquema de valores de conversión, los datos modelados tardan 2 días en estar disponibles.

<div id="modeled-data-types-and-availability" />

## Tipos de datos modelados y disponibilidad

| Tipo de datos | Disponibilidad | Observaciones |
| --- | --- | --- |
| Valores de conversión nulos | <ul><li>Vista general del panel de control de Única fuente de verdad</li><li>Panel de control de SKAN</li><li>API del reporte de estadísticas agregadas de rendimiento SKAN</li><li>API de la fecha de llegada del postback agregado de SKAN</li></ul> |  |
| LTV de ingresos | Vista general del panel de control de Única fuente de verdad | Hasta 30 días en el reporte de SSOT Data Locker (D7 sigue mostrándose en el dashboard) |
| LTV del evento in-app | Vista general del panel de control de Única fuente de verdad | El modelado de LTV de ingresos está actualmente limitado a 7 días |
| Geolocalización | Vista general del panel de control de Única fuente de verdad |  |

<div id="null-conversion-values" />

<Accordion title="Valores de conversión nulos">

A veces, el valor de conversión (CV) tiene un valor nulo porque Apple retiene el CV real para preservar la privacidad del usuario. En AppsFlyer, un CV nulo se cuenta como una instalación. Ten en cuenta lo siguiente:

* Nulo y cero tienen significados diferentes:
  * Cero: el usuario instaló la aplicación pero no realizó ninguna acción medible durante la ventana de actividad. En consecuencia, la métrica es precisa y no está modelada.
  * Nulo: no sabemos qué hizo el usuario; Apple retuvo el CV.
* Los CV nulos pueden distorsionar tus métricas de rendimiento. Para resolver la distorsión y proporcionar una medición más real del rendimiento de la aplicación, los valores de conversión nulos se modelan según los valores de conversión entre 0 y 63.
  * El modelado nulo requiere un mínimo de dos días de datos de los últimos 14 días.

Valores de conversión modelados:

* Utiliza la distribución de instalaciones SKAN con valores de conversión para modelar instalaciones nulas. El algoritmo utilizado para modelar datos es dinámico y tiene en cuenta varias variables. Mira el siguiente ejemplo de cómo podría funcionar:
  * Hay 100 instalaciones, 60 nulas, 10 con CV=1, 5 con CV=3 y 25 con CV=5.
  * Esto significa que de las 40 instalaciones con valores de conversión, el 25 % tienen CV=1, el 12,5 % tienen CV=3 y el 62,5 % tienen CV=5.
  * Las 60 instalaciones nulas obtienen la misma distribución modelada: 15 obtienen CV=1, 7 obtienen CV=3 y 38 obtienen CV=5.
* Se incluyen en el panel de control de SKAN y en las métricas de API. Las métricas originales e inalteradas, que no incluyen datos modelados, están disponibles junto con estas métricas y están marcadas como *unmodeled*.
* Utiliza los datos de los siguientes niveles de granularidad: aplicación, fuente de medios, campaña y conjunto de anuncios. Si los datos modelados que utilizan esos niveles no están disponibles, se muestra el valor N/A.

Métricas modeladas disponibles en función del valor de conversión:

* Ingresos
* Eventos ocurridos
* Costo Efectivo por Adquisición (eCPA)
* OPCIONAL
* ROI (Retorno de la Inversión)
* ROAS (Retorno de la Inversión Publicitaria)

</Accordion>

<div id="revenue-ltv" />

<Accordion title="LTV de ingresos">

<Image align="center" alt="modeled_d7.png" src="https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png" />

Los reportes de SKAN por sí solos solo pueden proporcionar ingresos basados en la ventana de medición de SKAN y la configuración de CV para los ingresos en Conversion Studio. El modelado SKAN es capaz de modelar los ingresos hasta 7 días (168 horas) post-instalación.

**Beneficios**:

Para SKAN versión 3 y anteriores, los datos modelados se extienden más allá del marco de tiempo de la ventana de actividad.

Para SKAN versión 4+:

* Actualización de datos: el LTV de los ingresos está disponible antes de que llegue el segundo postback de SKAN (el retraso del postback es de entre 24 y 144 horas).
* Mide más: puedes usar la configuración de valor aproximado del segundo y tercer postbacks para otras métricas, como eventos y retención, y aún así obtener datos del LTV de los ingresos mediante el modelado.
* Enriquecimiento de datos: si usas el segundo postback para medir los ingresos, los datos del postback se utilizan para mejorar los datos del LTV de los ingresos modelados y proporcionar datos de ingresos a un nivel más granular que los 3 niveles proporcionados por el postback.

**Consideraciones**:

* Las métricas de LTV de ingresos se muestran para las aplicaciones con la configuración de ingresos en SKAN Conversion Studio, para los ingresos que provienen de las compras in-app y los ingresos por publicidad.
* El LTV de ingresos requiere al menos 14 días de datos de ingresos. Es decir, si configuras Ingresos generales el 1 de noviembre de 2022, la primera fecha de instalación para la que están disponibles los datos modelados es el 14 de noviembre de 2022. Los datos se muestran 8 días después de eso (22 de noviembre de 2022).
* El LTV de ingresos (actualmente limitado a 7 días) y otras métricas derivadas están disponibles en el panel de control de SSOT (en los widgets, gráficos y tabla) el día 8 post-instalación, de la siguiente manera:
  * Ingresos D[X]
  * ARPU D[X]
  * Beneficio bruto D[X]
  * ROI D[X]
  * ROAS D[X]

</Accordion>

<div id="inapp-event-ltv" />

<Accordion title="LTV del evento in-app">

El framework de SKAN por sí solo ofrece insights limitados sobre los eventos in-app posteriores a la instalación. El modelado de SKAN amplía el análisis de eventos in-app y proporciona métricas de eventos in-app hasta 7 días posteriores a la instalación.

**Beneficios**:

Para SKAN versión 3 y anteriores, los datos modelados se extienden más allá del marco de tiempo de la ventana de actividad.

Para SKAN versión 4+:

* Actualización de datos: el LTV de eventos in-app está disponible antes de que llegue el segundo postback de SKAN (el retraso del postback es de entre 24 y 144 horas).
* Mide más: puedes usar la configuración de valor aproximado del segundo y tercer postback para medir ingresos, tasas de retención, etc., y aun así obtener métricas de LTV del evento in-app mediante el modelado.
* Enriquecimiento de datos: si usas el segundo postback para medir eventos in-app, los datos del postback se utilizan para mejorar la precisión de las métricas de eventos in-app modeladas, lo que ofrece una medición más detallada que la que proporciona por sí solo el postback aproximado de SKAN.

**Consideraciones**:

* Las métricas están disponibles desde el 7 de marzo de 2024.
* Los eventos in-app (como dimensiones) y sus métricas están disponibles solo para:
  * Eventos configurados en SKAN Conversion Studio.
  * Eventos que ocurrieron durante el período de la Ventana 1 de SKAN.
* Las métricas D7 de evento in-app requieren al menos 14 días de datos de eventos in-app. Por ejemplo, si configuras un evento in-app en SKAN Conversion Studio el 1 de enero de 2024, la primera fecha de instalación para la que hay datos modelados disponibles es el 14 de enero de 2024. Los datos se muestran 8 días después de eso (22 de enero de 2024).
* Las métricas de LTV del evento in-app (actualmente limitadas a 7 días) y otras métricas derivadas están disponibles en el dashboard de SSOT (en los widgets, gráficos y tabla) el día 8 posterior a la instalación, de la siguiente manera:
  * Usuarios únicos del evento D7
  * Conversión del evento D7
  * Event eCPA D7
  * Ingresos d7
* El recuento de usuarios únicos del evento D2 puede ser mayor que el recuento de D7 si no todas las fechas dentro del intervalo seleccionado han alcanzado el día 7, lo que restringe las métricas D7 a los datos de AppsFlyer. La jerarquía de «fuente» o «método de atribución» se puede añadir a las tablas con fines de visualización.

</Accordion>

<div id="geo" />

<Accordion title="Geolocalización">

Los postbacks de SKAN no incluyen una dimensión de geolocalización. Por lo tanto, los datos de SKAN no se pueden agrupar por geolocalización usando solo postbacks de SKAN. Sin embargo, AppsFlyer es capaz de modelar geolocalizaciones de instalación de SKAN para proporcionar la dimensión y agrupación por geolocalización para los datos de SKAN.

Cuando no hay datos de atribución de AppsFlyer Classic disponibles a nivel de campaña, el modelado de geolocalización no calcula ninguna estimación de distribución geográfica en la vista SSOT.

Geolocalizaciones modeladas:

* Utilizan herramientas de aprendizaje de máquina que tienen en cuenta la geodistribución para las instalaciones de las campañas atribuidas a través de otros métodos de AppsFlyer.
* Están disponibles a través de la dimensión de geolocalización en el panel de control SSOT.  
  **Nota**: Si agrupas los datos por el método de geolocalización y el de atribución, puedes ver los datos de cada geolocalización divididos entre los modelados por AF y los exclusivos de SKAN. Se modelan los exclusivos de SKAN.

Consideraciones:

* La precisión del modelado de geolocalización de AppsFlyer es de aproximadamente el 90 %. Si no se puede modelar la geolocalización, la instalación de SKAN se agrupa en Ninguna. Ninguna significa que se desconoce la geolocalización.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general 01H8TZR38AC6P264CGF4PX4SJ5=visi%C3%B3n-general modeled-data-types-and-availability=tipos-de-datos-modelados-y-disponibilidad 01H8TZR38A2V9ZSSGKHF3XCX0P=tipos-de-datos-modelados-y-disponibilidad 01H8TZR38A4RDX42B7J5X9SPMQ=null-conversion-values 01H8TZR38BG9XEM2FTJADJ27VK=revenue-ltv h_01HTW0XNB2W7JMD9ECZHSN91GZ=inapp-event-ltv 01H8TZR38BSFVDSQCH915ACSYH=geo" />

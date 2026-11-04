---
title: Cuotas de generación de reportes (limitaciones de la tarifa)
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2014-05-01T12:55:30Z'
  edited_at: '2026-10-20T03:41:35Z'
  id: 207034366
  locale: es
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/es/articles/207034366
---
> **At a glance:** Un mecanismo de cuota (limitación de tasa) limita el número de reportes que puedes generar al día, tanto a través de Pull API como de las páginas de exportación de datos.

<div id="rate-limits-for-reports" />

## Límites de frecuencia para reportes

La cuota limita el número de reportes que puedes generar al día por tipo de reporte. La cuota varía según tu plan de suscripción.

**Principios:**

* **Agencias:** Las agencias y los anunciantes tienen cuotas de Pull API separadas. La cuota se aplica por reporte, por día y por aplicación, de la misma manera para ambos. Para los reportes de la página de datos exportados, las agencias y los anunciantes tienen cuotas separadas. Si a menudo alcanzas el límite de cuota, contacta con tu Ejecutivo de cuenta.
* **Ad networks:** Los reportes que generan las ad network no cuentan para la cuota del anunciante.
* **Día:** Las cuotas se aplican por día natural, a partir de las 00:00 UTC.

<div id="aggregated-and-analytics-reports" />

### Reportes agregados y análisis

| Herramienta de entrega de datos | Cuota |
| --- | --- |
| Pull API agregada | <ul><li>Hasta 2 días en el rango de fechas:<ul><li>Máximo de 1 llamada por minuto por aplicación por reporte</li></ul></li><li>Intervalo de fechas de 3 días o más: se aplican los siguientes límites:<ul><li>Máximo de 120 llamadas por día, por cuenta</li><li>24 llamadas por día por aplicación</li></ul></li></ul> |
| Página de datos exportados agregados | Ilimitado |
| API maestra | Ilimitado |
| API de cohorte | 60 llamadas por minuto por cuenta |
| Reportes agregados de SKAN | 10 llamadas por minuto por cuenta |

<div id="raw-data" />

### Datos sin procesar

* Se aplica una cuota independiente a cada herramienta de reportes, es decir, Pull API y la página de exportación de raw data.
* Las agencias y los anunciantes tienen cuotas de Pull API separadas. Es posible que los reportes generados por la agencia cuenten para la cuota del anunciante. La única excepción es cuando una agencia utiliza el token API del anunciante en lugar del suyo propio, en cuyo caso las solicitudes no se distinguen de las solicitudes del anunciante y cuentan para la cuota del anunciante. Para los reportes de la página de datos exportados, las agencias y los anunciantes tienen cuotas separadas.
* Las cuotas de extracción de API se aplican por:
  * Reporte
  * Día
  * Nivel de aplicación
  * Nivel de cuenta
* Para los anunciantes, las cuotas dependen de tu suscripción a AppsFlyer. Las cuotas también se aplican a los reportes que requieran una suscripción premium.
* Las cuotas diarias de los reportes de raw data de Pull API y de los reportes de postback de ad network son las que se indican en las tablas siguientes.

Para ver ejemplos, consulta las Preguntas frecuentes a continuación.

<div id="pull-api-raw-data-daily-quota" />

#### Cuota diaria de raw data de Pull API

Los reportes de raw data de Pull API tienen las siguientes cuotas diarias:

| Tipo de reporte | Cuota diaria a nivel de aplicación (reportes) | Cuota diaria a nivel de cuenta (reportes) |
| --- | --- | --- |
| Instalaciones | 24 | 120 |
| Eventos in-app | 12 | 60 |

<div id="note" />

> 📘 **Nota:**
>
> Las cuotas se aplican por tipo de reporte, por lo que cada tipo de reporte tiene una cuota independiente.

<div id="ad-network-postback-reports-daily-quota" />

#### El postback de la ad network reporta la cuota diaria

Las ad networks pueden extraer los siguientes tipos de reportes de postback:

| Grupo de postback | Tipo de reporte  <br />(cada tipo de reporte tiene una cuota independiente) | Cuota diaria a nivel de aplicación | Cuota diaria a nivel de cuenta |
| --- | --- | --- | --- |
| Postbacks para atribución | <ul><li>Instalaciones</li><li>Conversiones de retargeting</li></ul> | 24 | 120 |
| Postbacks para eventos in-app | <ul><li>Eventos dentro de la app</li><li>Retargeting de eventos in-app</li></ul> | 12 | 60 |

<div id="faq" />

## Preguntas frecuentes

* P: Para una aplicación determinada, ¿puedo generar 24 reportes de instalaciones orgánicas utilizando la Pull API y otros 24 reportes utilizando la página de exportación de raw data?  
  R: Sí. La cuota por cada herramienta de reportes es independiente.
* P: Para una aplicación determinada, al utilizar la página de exportación de raw data, ¿puedo generar 24 reportes de instalaciones orgánicas, 24 reportes de instalaciones no orgánicas y 24 reportes de conversiones de retargeting?  
  R: Sí. La cuota por cada tipo de reporte es independiente.
* P: Tengo 25 aplicaciones en mi cuenta. ¿Puedo generar 10 reportes de instalaciones orgánicas para cada aplicación?  
  R: No. Esto da como resultado un total de 250 reportes, lo que supera la cuota a nivel de cuenta de 120.
* P: ¿Los reportes de Pull API generados por la agencia cuentan para la cuota del anunciante?  
  R: No. Las agencias y los anunciantes tienen cuotas de Pull API separadas. Es posible que los reportes generados por la agencia cuenten para la cuota del anunciante. La única excepción es cuando una agencia utiliza el token de API del anunciante en lugar del suyo propio, en cuyo caso esas solicitudes se cuentan como solicitudes del anunciante.

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/data-availability-windows">Ventanas de disponibilidad de datos</Anchor>

<div data-zendesk-anchors="rate-limits-for-reports=l%C3%ADmites-de-frecuencia-para-reportes h_01H9JNZFPSVXPKMEVR1ZR6PSYG=l%C3%ADmites-de-frecuencia-para-reportes aggregated-and-analytics-reports=reportes-agregados-y-an%C3%A1lisis h_01H9JNZFPS62A5CFWSXVPN8XM5=reportes-agregados-y-an%C3%A1lisis raw-data=datos-sin-procesar h_01H9JNZFPSPYWBB2MCZV2R2KX1=datos-sin-procesar h_01M4WW4PAZ64FXVR1QPKE53DS7=cuota-diaria-de-raw-data-de-pull-api h_01M4WW4PAZFMX9X0DFX1E6F9M0=nota ad-network-postback-reports-daily-quota=el-postback-de-la-ad-network-reporta-la-cuota-diaria h_01H9JNZFPSYXZNW81BZTRDS576=el-postback-de-la-ad-network-reporta-la-cuota-diaria h_01H9JNZFPT76RAV8JBTY2K75V4=preguntas-frecuentes h_01HE7SW3VWRNVY1WFB4YCSAVY6=consulta-tambi%C3%A9n" />

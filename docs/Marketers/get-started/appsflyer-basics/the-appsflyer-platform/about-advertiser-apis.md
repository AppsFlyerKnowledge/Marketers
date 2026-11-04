---
title: Acerca de las APIs de anunciantes
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-05-24T15:14:53Z'
  edited_at: '2026-08-12T11:57:54Z'
  id: 360009122638
  locale: es
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/es/articles/360009122638
---
> **En resumen:** APIs disponibles para que los anunciantes accedan o actualicen datos.

<div id="advertiser-api-list-and-interfaces" />

## Lista e interfaces de la API de anunciante

<span id="01EEQJERAWW3HY59HVPY3YWA0B"></span>Información específica sobre los reportes, las herramientas de reportes y las APIs de reportes:

* <span id="01EEQJERAW2ZTBWBQKBCDSC76Z"></span><span id="01EEQJERAWQ2WCPV0207XM6FR4"></span><Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview"><span id="01EEQJERAX0W7RCYQWVM2M5S13"></span>APIs/Herramientas de reportes de raw data</Anchor>
* <span id="01EEQJERAWA09P200SGR985846"></span><span id="01EEQJERAW6AC6WR7E46T5DMHW"></span><Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview">APIs/Herramientas de reportes agregados y de análisis</Anchor>

<div id="interfaces-for-advertisers" />

#### Interfaces para anunciantes

| Campo | Nombre de la API | ![af_premium.png](https://files.readme.io/ad0c279c48242ea25529f1bc386ee2c747bcd332f5fb1eb2fc26dd378a257f6e-4403570953105.png)<br /><br />Función premium | Descripción | Autenticación  <br />token/key | Tipo de interfaz |
| --- | --- | --- | --- | --- | --- |
| Atribución móvil | <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">Eventos server-to-server (servidor a servidor)</Anchor> | No | Registra eventos in-app que ocurran fuera de una aplicación móvil | <Anchor target="_blank" href="/marketers/es/docs/app-settings#sdk-authentication-dev-key">Clave de desarrollador de SDK</Anchor> | REST API |
| Atribución People-Based (PBA) | <Anchor target="_blank" href="/marketers/es/docs/web-server-to-server-events-api-for-pba-web-s2s">Web server-to-server</Anchor> | No | Reportar eventos de PBA que ocurren en el Backend | <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings#gestión-de-paquetes-de-marca">PBA key</Anchor> | REST API |
| Participación | <Anchor target="_blank" href="/marketers/es/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink</Anchor> | Sí | Administrar OneLinks: crear, actualizar, recuperar, eliminar | <Anchor target="_blank" href="/marketers/es/docs/app-settings#sdk-authentication-dev-key">Clave de desarrollador de SDK</Anchor> | REST API |
| Remarketing | <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#import-an-audience">Audiencias</Anchor> | Sí | Sube listas de usuarios a Audiences | <Anchor target="_blank" href="/marketers/es/docs/audiences-import-audience-segments-from-internal-systems">Importar key</Anchor> | REST API |
| Privacidad | <Anchor target="_blank" href="/marketers/es/docs/send-opendsr-api-requests">Solicitudes openDSR</Anchor> | No | Solicitudes y estado de eliminación de datos | <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reportes | <Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api">Domina los KPIs de rendimiento</Anchor> | Sí | Métricas de rendimiento de campañas de múltiples aplicaciones en archivos CSV | <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reportes | <Anchor target="_blank" href="/marketers/es/docs/pull-api-aggregate-data">Obtener reportes agregados</Anchor> | No | Reportes agregados en archivos CSV | <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reportes | <Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data">Extraer raw data</Anchor> | Sí | Reportes de raw data en archivos CSV | <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reportes | <Anchor target="_blank" href="/marketers/es/docs/cohort-api">Análisis de cohortes</Anchor> | Sí | Métricas de cohorte en archivos JSON o CSV | <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reportes | <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Casillero de datos</Anchor> | Sí | Reportes de raw data y agregados | N/D | Almacenamiento en la nube |
| Atribución móvil | <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">Push</Anchor> | Sí | Instalaciones en tiempo real y eventos in-app enviados a los servidores de los anunciantes. | N/D | REST API |
| Costo de la campaña | <Anchor target="_blank" href="/partners/es/docs/cost-import-for-ad-networks">Importación de costos</Anchor> | No | Reportar del costo de la campaña | N/D | Subir archivo |
| Cuenta | <Anchor target="_blank" href="/marketers/es/docs/app-list-api-for-app-owners">Obtener lista de aplicaciones</Anchor> | No | Obtén una lista de aplicaciones en tu cuenta | <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">V2.0</Anchor> | REST API |
| Reportes | <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">ETL Cost</Anchor> | Sí | Costo de la campaña granular Cost ETL | N/D | Almacenamiento en la nube |
| Reportes | <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#reporting-options">Reportes SKAN</Anchor> | No | Reportes agregados de SKAN | V2.0 | REST API |
| Partners integrados | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-copy">Copiar la configuración de integración de partners</Anchor> | No | Copia los parámetros de configuración de integración de una aplicación a otra | V2.0 | REST API |
| Partners integrados | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Establecer la clave de descifrado del referente de instalación</Anchor> | No | Establecer la clave de descifrado de referencia de instalación recibida de Meta Ads | V2.0 | REST API |

<div data-zendesk-anchors="advertiser-api-list-and-interfaces=lista-e-interfaces-de-la-api-de-anunciante h_01HX9638DX6EHR4ETMSH10K68F=lista-e-interfaces-de-la-api-de-anunciante interfaces-for-advertisers=interfaces-para-anunciantes h_01HX9638DXNJM3A968A2PSRRKS=interfaces-para-anunciantes" />

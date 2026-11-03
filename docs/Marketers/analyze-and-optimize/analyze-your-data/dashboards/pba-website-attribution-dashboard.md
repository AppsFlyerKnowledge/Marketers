---
title: Panel de control de atribución de sitio web de la PBA
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2018-12-09T07:49:24Z'
  edited_at: '2026-08-12T11:50:59Z'
  id: 360000654377
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/360000654377
---
> **De un vistazo:** Mide el impacto de los esfuerzos de marketing para impulsar el tráfico efectivo del sitio web. Qué fuentes de medios, tipos y canales son responsables de las visitas, eventos de conversión y métricas de nivel de anuncio disponibles.

[![Website_Atribución.jpg](https://files.readme.io/59cda285cb1f2b88c6992f3d303ee87e33176f82f0cf7afedb4711ee363e3a73-360015253418.jpg)](https://files.readme.io/59cda285cb1f2b88c6992f3d303ee87e33176f82f0cf7afedb4711ee363e3a73-360015253418.jpg)

## Atribución de sitios web de la PBA

Usando el panel de control de atribución del sitio web, los anunciantes obtienen una visión de las fuentes de medios que impulsan a los visitantes y las conversiones.

* Usa el gráfico de tendencias para ver la tendencia general y el desglose de las contribuciones por fuente y canal de medios.
* Obtén detalles granulares hasta el nivel de anuncio/conjunto de anuncios, y visualiza las métricas de rendimiento para cada evento de conversión.

**Los marketers usan el panel de control para responder preguntas como:**

| ![icon2.png](https://files.readme.io/77fda01229f4b1b50755bc94f35cc021928ba7af1e3b5b45e61606ab18e8fd7a-360013383917.png) | **Rendimiento**<br /><br />¿Qué fuentes de medios y campañas impulsan más visitas, conversiones y valor en mi sitio web? |
| --- | --- |
| ![Icon1.png](https://files.readme.io/b20da70a56d881dd2fe31b18df8919db43b47e3e2338b89da7ef5ef6467590d6-360013383937.png) | **Efectividad**<br /><br />¿Qué canales de adquisición ofrecen los KPI de mejor rendimiento, como la tasa de conversión o los ingresos promedio por usuario (ARPU)? |
| ![s4.png](https://files.readme.io/9a426232668022a9b4d006e685d2384d61efe4814c377aa9295e9b7887f14fef-360013383957.png) | **Análisis comparativo**<br /><br />¿Cómo se comparan mis campañas pagas con mis canales propios y el tráfico ganado? ¿En qué tipos de dispositivos y plataformas mis usuarios web se convierten? |

## Referencia del panel de control

**Para ir a los paneles de control de la PBA, realiza una de las siguientes acciones:**

* En AppsFlyer, en el menú lateral, **Analyze** > **Atribución basada en personas.**
* Ve a **Mis Aplicaciones >** **Ver paquetes de marca**. Haz clic en los **paneles de control de la PBA.** Ve a la pestaña **Atribución de sitio web**.

<Table>
  <thead>
    <tr>
      <th>
        Componente
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Selector de fechas y filtros
      </td>
      <td>
        ![WebsiteAttributionFilterPaner_us-en.jpg](https://files.readme.io/1d4cb6145bd0a297d9d358b904968cdffadc4235499ba661048983de8dbc348c-360013057737.jpg)

        * Selecciona el intervalo de fechas, el <Anchor target="_blank" href="/marketers/es/docs/using-pba-dashboards">filtro y las opciones de agrupación de la atribución</Anchor>.
        * **Filtra por**: fuente de medios, tipo de medios, canal de medios, geolocalización, evento de conversión.
        * **Agrupa por:** fuente/campaña de medios, tipo de medios, canal de medios, tipo de dispositivo, plataforma.
      </td>
    </tr>
    <tr>
      <td>
        Gráfico
      </td>
      <td>
        **Actividad del sitio web a lo largo del tiempo**

        ![WebsiteAttribution_us-en__1_.jpg](https://files.readme.io/cfa214a82b39db1fdbed128029dd28fdf4b623f2c0c7d7f51e067d5e182431ca-360013057717.jpg)

        * Muestra las fuentes de las visitas y las conversiones para un período determinado.
        * Visualiza por opciones: canal de medios, fuente de medios
      </td>
    </tr>
    <tr>
      <td>
        Tabla
      </td>
      <td>
        **Tabla de atribución**

        [![WebsiteAttributionTable](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)

        * Las métricas están disponibles para el sitio web en su conjunto con un desglose por evento de conversión.
        * Baja de nivel desde la fuente de medios hasta el nivel de anuncio para descubrir fuentes de medios y anuncios específicos que impulsan el tráfico al sitio web.
        * Compara el rendimiento de los anuncios en relación con el impulso del tráfico y la generación de conversiones.

        | Métricas totales | Descripción |
        | --- | --- |
        | <span id="visits"></span>Visitas | Sesiones de usuarios que visitan el sitio web |
        | <span id="unique-visitors"></span>Visitantes únicos | Visitantes únicos del sitio. Los usuarios únicos son determinados por la PBA utilizando el gráfico de usuarios privados de PBA. Para mantener la integridad del gráfico, debes implementar el <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">CUID</Anchor>. El mismo usuario que llega al sitio utilizando diferentes navegadores se cuenta una sola vez. |
        | <span id="conversions"></span>Conversiones | Cantidad de eventos de conversión realizados |
        | <span id="conversion-rate"></span>tasa de conversión | Fórmula: Conversiones / Visitas * 100 |
        | <span id="acpu"></span>ACPU | La cantidad promedio de conversiones por visitante único. Fórmula: Conversiones / Visitantes únicos |
        | <span id="revenue"></span>Ingresos | Ingresos de todos los eventos combinados |
        | <span id="arpu"></span>OPCIONAL | Ingresos promedio por usuario. Fórmula: Ingresos / Usuarios únicos |

        | Métricas de eventos de conversión | Descripción |
        | --- | --- |
        | <span id="event-count"></span>Recuento de eventos | Cantidad de veces que se realizó el evento |
        | <span id="unique-users"></span>Usuarios únicos | Usuarios únicos que realizan el evento de conversión |
        | <span id="revenue::58195989"></span>Ingresos | Ingresos asociados a este evento de conversión |
        | <span id="arpe"></span>ARPE | Ingreso promedio por evento de conversión. Fórmula: Ingresos / Recuento de eventos |
      </td>
    </tr>
    <tr>
      <td>
        Exportar CSV
      </td>
      <td>
        Haz clic en **Exportar CSV** para exportar la tabla.
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="pba-website-attribution=atribuci%C3%B3n-de-sitios-web-de-la-pba h_01HJR6ZPF5VWPX9020G0W7NX4X=atribuci%C3%B3n-de-sitios-web-de-la-pba dashboard-reference=referencia-del-panel-de-control h_01HJR6ZPF58VWA51QWY4BGZN8E=referencia-del-panel-de-control" />

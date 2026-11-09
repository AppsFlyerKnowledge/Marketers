---
title: Dashboard de Atribuição do Site PBA
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
  edited_at: '2026-08-18T00:04:14Z'
  id: 360000654377
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/360000654377
---
> **Visão geral:** mensure o impacto dos seus esforços de marketing para impulsionar o tráfego ativo do site. Quais fontes, tipos e canais de mídia são responsáveis por visitas, eventos de conversão e métricas em nível de anúncio que estão disponíveis.

<Image align="center" alt="Website_Atribuição.jpg" src="https://files.readme.io/59cda285cb1f2b88c6992f3d303ee87e33176f82f0cf7afedb4711ee363e3a73-360015253418.jpg" />

<div id="pba-website-attribution" />

## Atribuição do site PBA

Usando o dashboard de Atribuição do Site, os anunciantes obtêm insight sobre as fontes de mídia que impulsionam visitantes e conversões.

* Use o gráfico de tendências para visualizar a tendência geral e o detalhamento da contribuição por fonte de mídia e canal de mídia.
* Obtenha detalhes granulares a nível de anúncio/conjunto de anúncios e visualize as métricas de desempenho para cada evento de conversão.

**Os profissionais de marketing usam o dashboard para responder a perguntas como:**

| ![icon2.png](https://files.readme.io/77fda01229f4b1b50755bc94f35cc021928ba7af1e3b5b45e61606ab18e8fd7a-360013383917.png) | **Desempenho**<br /><br />Quais fontes de mídia e campanhas geram mais visitas, conversões e valor no meu site? |
| --- | --- |
| ![Icon1.png](https://files.readme.io/b20da70a56d881dd2fe31b18df8919db43b47e3e2338b89da7ef5ef6467590d6-360013383937.png) | **Eficácia**<br /><br />Quais canais de aquisição oferecem os melhores KPIs de desempenho, como taxa de conversão ou ARPU? |
| ![s4.png](https://files.readme.io/9a426232668022a9b4d006e685d2384d61efe4814c377aa9295e9b7887f14fef-360013383957.png) | **Análise comparativa**<br /><br />Como minhas campanhas pagas se comparam aos meus canais próprios e ao tráfego orgânico? Em quais tipos de dispositivos e plataformas os meus usuários da web convertem? |

<div id="dashboard-reference" />

## Referência do dashboard

**Para acessar os dashboards de PBA, siga um dos procedimentos abaixo:**

* No AppsFlyer, no menu lateral, selecione **Analyze** > **People-Based Attribution.**
* **Vá para Meus aplicativos >** **Ver pacotes de marca**. Clique em **Dashboards de PBA.** Acesse a aba **Atribuição de Site** .

<Table>
  <thead>
    <tr>
      <th>
        Componente
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Selecionador de data e filtros
      </td>
      <td>
        ![WebsiteAttributionFilterPaner_us-en.jpg](https://files.readme.io/1d4cb6145bd0a297d9d358b904968cdffadc4235499ba661048983de8dbc348c-360013057737.jpg)

        * Selecione o intervalo de datas de atribuição, <Anchor target="_blank" href="/marketers/pt/docs/using-pba-dashboards">filtro e opções de agrupamento</Anchor>.
        * **Filtrar por**: fonte de mídia, tipo de mídia, canal de mídia, geolocalização, evento de conversão
        * **Agrupar por:** fonte de mídia/campanha, tipo de mídia, canal de mídia, tipo de dispositivo, plataforma.
      </td>
    </tr>
    <tr>
      <td>
        Gráfico
      </td>
      <td>
        **Atividade do site ao longo do tempo**

        ![WebsiteAttribution_us-en__1_.jpg](https://files.readme.io/cfa214a82b39db1fdbed128029dd28fdf4b623f2c0c7d7f51e067d5e182431ca-360013057717.jpg)

        * Faça a exibição das fontes de visitas e conversões para um determinado período.
        * Veja por opções: canal de mídia, fonte de mídia
      </td>
    </tr>
    <tr>
      <td>
        Tabela
      </td>
      <td>
        **Tabela de atribuição**

        [![WebsiteAttributionTable](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)](https://files.readme.io/46f03ee216dc23f3f184663aeef7d6b64ae6fb9a64e7a161ff0482e4d2eab204-360013057757.jpg)

        * As métricas estão disponíveis para o site como um todo com uma análise por evento de conversão.
        * Analise da fonte de mídia até o nível do anúncio para descobrir fontes de mídia específicas e anúncios que estão direcionando tráfego para o site.
        * Compare a performance dos anúncios para impulsionar o tráfego e gerar conversões.

        | Métricas totais | Descrição |
        | --- | --- |
        | <span id="visits"></span>Visitas | Sessões de usuários que visitam o site |
        | <span id="unique-visitors"></span>Visitantes únicos | Visitantes exclusivos do site. Usuários exclusivos são determinados pelo PBA usando o gráfico de usuários privados do PBA . Para manter a integridade do gráfico, você deve implementar o <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">CUID</Anchor>. O mesmo usuário que chega ao site usando navegadores diferentes é contado uma vez. |
        | <span id="conversions"></span>Conversões | Número de eventos de conversão realizados |
        | <span id="conversion-rate"></span>Taxa de conversão | Fórmula: Conversões / Visitas x 100 |
        | <span id="acpu"></span>ACPU | Número médio de conversões por visitante único. Fórmula:  Conversões / Visitantes únicos |
        | <span id="revenue"></span>Resultados | Receita de todos os eventos combinados |
        | <span id="arpu"></span>OPCIONAL | Receita média por usuário. Fórmula: Receita / Usuários únicos |

        | Métricas de eventos de conversão | Descrição |
        | --- | --- |
        | <span id="event-count"></span>Contagem de eventos | Número de vezes que o evento foi executado |
        | <span id="unique-users"></span>Usuários únicos | Usuários únicos que executam o evento de conversão |
        | <span id="revenue::58195989"></span>Resultados | Receita associada a esse evento de conversão |
        | <span id="arpe"></span>ARPE | Receita média por evento de conversão. Fórmula: Receita / Contagem de evento |
      </td>
    </tr>
    <tr>
      <td>
        Exportar CSV
      </td>
      <td>
        Clique em **Exportar CSV** para exportar a tabela.
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="pba-website-attribution=atribui%C3%A7%C3%A3o-do-site-pba h_01HJR6ZPF5VWPX9020G0W7NX4X=atribui%C3%A7%C3%A3o-do-site-pba dashboard-reference=refer%C3%AAncia-do-dashboard h_01HJR6ZPF58VWA51QWY4BGZN8E=refer%C3%AAncia-do-dashboard" />

---
title: Métricas de atividade no My Dashboards
metadata:
  keywords:
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maya-kahane
    - Marketers
    - Marketing Analytics
    - Ad Networks
  created_at: '2025-09-09T10:46:09Z'
  edited_at: '2026-08-18T00:03:38Z'
  id: 38874924986001
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/38874924986001
---
> **Resumo:** Use as métricas de atividade no <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards">My Dashboards</Anchor> para avaliar rapidamente a performance do seu aplicativo, identificar tendências de engajamento, analisar receitas e detectar problemas o quanto antes. Tudo isso em qualquer intervalo de datas e com maior precisão e flexibilidade.

> 📘 **Atenção**
>
> As métricas de receita líquida serão implementadas gradualmente para os clientes ao longo dos meses de julho e agosto de 2026. Se você ainda não as vê, nenhuma ação é necessária; elas ficarão disponíveis para a sua conta durante esse período. Consulte <Anchor target="_blank" href="/marketers/pt/docs/bulletin-cohort-and-activity-metrics-update-in-my-dashboards">Boletim: atualização das métricas de cohort e atividade no My Dashboards</Anchor>.

## Sobre as métricas de atividade

As métricas de atividade no My Dashboards permitem que os usuários analisem dados de atividade, LTV e cohort em um só local. Assim, você consegue monitorar a performance do seu negócio e acessar insights mais detalhados:

* Analise a **atividade do usuário e o stickiness** com relevância em tempo real.
* Mensure **a performance, receita e tendências de sessões.**  
  Acesse uma visão unificada no período **atual ou nos intervalos de LTV ou cohort**, tudo em um único dashboard.
* Personalize relatórios usando a análise **diária ou mensal** (usuários ativos).

Atenção: No My Dashboards, o termo **atividade** foi renomeado para **atual**. Essa alteração esclarece que essas métricas refletem ações reais dos usuários durante o intervalo de datas selecionado e não estão conectadas à agregação de LTV. A opção "atual" também é o período padrão para Sessões, Lucro Bruto e Receita Total.

## Informações sobre o dashboard

**Activity View:**

O template de **Activity view** ajuda os profissionais de marketing a avaliar rapidamente a performance do aplicativo, identificar tendências de engajamento, analisar receitas e detectar problemas o quanto antes, permitindo decisões mais rápidas e baseadas em dados em campanhas e plataformas.

**Adicionar widgets ao dashboard**

Você pode adicionar widgets ao seu dashboard clicando no botão **+ Criar novo** no canto superior direito e selecionando o tipo de widget que pretende criar: Tabela, KPI, gráfico, tabela de eventos in-app, gráfico de eventos in-app, texto ou métrica personalizada. Instruções detalhadas podem ser acessadas <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#add-widget">aqui</Anchor>.

**Adicionar métricas ao seu gráfico ou tabela**

Em configurações do gráfico ou configurações da tabela, clique no sinal de mais + em métricas.

Feito isso, você pode adicionar uma dimensão de "agrupar por" e selecionar seus filtros.

Instruções detalhadas podem ser acessadas <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#add-metric">aqui</Anchor>.

## Métricas de atividade disponíveis

* Todas as métricas (com a exceção das métricas de usuários ativos, usuários ativos nos últimos 31 dias, e DAU/MAU) também são compatíveis com períodos de cohort e LTV.

| **Métrica** | **Descrição** |
| --- | --- |
| Usuários ativos | <ul><li>Número de usuários ativos que abriram o aplicativo pelo menos uma vez durante o período selecionado, com base nas sessões, conforme a definição de análise temporal selecionada.</li><li>Se o período "diário" estiver selecionado, é mostrado como DAU.</li><li>Se o período "mensal" estiver selecionado, é mostrado como MAU.</li><li>Quando visualizado em gráficos de linhas, quadros de colunas ou em uma tabela agrupada por data, é mostrado como DAU.</li><li>Para informações sobre o query de relatórios de dados brutos para DAU e MAU, veja: <Anchor target="_blank" href="/marketers/pt/docs/calculate-daily-and-monthly-active-users-dau-and-mau">Calcular daily e monthly active users (DAU e MAU)</Anchor></li></ul> |
| Usuários ativos nos últimos 31 dias | Número de usuários únicos (contados apenas uma vez) que abriram o aplicativo pelo menos uma vez durante os 31 dias anteriores. |
| DAU/MAU | A taxa de usuários que retornam ao aplicativo (stickiness).<br /><br />Uma taxa DAU/MAU de 50% significa que o usuário médio abriu o aplicativo em 15 dos 31 dias anteriores.<br /><br />A taxa DAU/MAU é uma medida de aderência do usuário e fornece um instantâneo da retenção do usuário.<br /><br />Fórmula: Usuários ativos diários / Usuários ativos nos últimos 31 dias. |
| Sessões | Sessões durante o intervalo de datas selecionado. |
| Receita total | Receita gerada durante o período selecionado. A receita consiste em compras in-app e receita de anúncios. |
| Net revenue | Receita líquida do período selecionado, agregada a partir do parâmetro de evento af\_net\_revenue. Para aplicativos que utilizam a receita da loja do ROI360, é a receita bruta menos as taxas e impostos da loja de aplicativos (líquida = bruta - taxas da loja - impostos); os aplicativos que enviam af\_net\_revenue definem o próprio cálculo. |
| Primeiras visitas | Número de primeiras visitas a um aplicativo web. Contou como linhas onde conversion\_name = first\_visit. Disponível apenas para aplicativos web. |
| Re-visitas | Número de visitas não-orgânicas que retornam a um aplicativo web. Contado como linhas onde conversion\_name = revisit. Disponível apenas para aplicativos web. |
| Aquisições de usuários | Disponível para atribuição cross-platform ou aplicativos web. Para aplicativos web, as aquisições de usuários refletem as primeiras visitas, a menos que um evento de aquisição de usuário esteja configurado. Para aplicativos mobile, as aquisições de usuários correspondem às instalações. Ao visualizar vários aplicativos juntos: aquisições de usuários = instalações + primeiras visitas (ou o evento na web personalizado e configurado pelo cliente). |

## Métricas disponíveis no aplicativo

| **Métrica** | **Descrição** |
| --- | --- |
| Taxa de conversão | Percentagem de usuários únicos (atribuições) que realizam o evento. Fórmula: Usuários únicos do evento / Atribuições x 100 |
| Usuários únicos | Número de usuários únicos (atribuições) que realizam o evento |
| Contagem média | Número médio de vezes que este evento foi realizado por atribuição.<br /><br />Fórmula: Contagem de eventos / Atribuições |
| eCPA | Custo efetivo por ação (evento).<br /><br />Fórmula: Custo / Usuários únicos do evento |
| Contagem | Número de vezes que este evento foi realizado |
| Resultados | Receitas geradas por este evento específico |
| OPCIONAL | Receita média por usuário.<br /><br />Fórmula: Receita / Usuários específicos (usuários = atribuições) |
| Lucro bruto | Receita - Custo |
| ROAS | Retorno do investimento em anúncios.<br /><br />Fórmula: Receita / custo x 100 |
| ROI | Retorno do investimento.<br /><br />Fórmula: (Receita - Custo) / Custo x 100 |
| Net revenue | Receita líquida gerada por esse evento específico (após taxas e impostos da loja de aplicativos). |
| ARPU líquido | Receita líquida média por usuário.<br /><br />Fórmula: Receita líquida / Usuários únicos (usuários = atribuições) |
| Lucro bruto/líquido | Receita líquida - Custo |
| ROAS líquido | Retorno do gasto com anúncios com base na receita líquida.<br /><br />Fórmula: Receita líquida / Custo x 100 |
| ROI líquido | Retorno do investimento com base na receita líquida.<br /><br />Fórmula: (Receita líquida - Custo) / Custo x 100 |

**Métricas de receita líquida**

As métricas líquidas (receita líquida, ROI líquido, ROAS líquido, ARPU líquido e lucro líquido) mostram a receita líquida em vez da receita bruta. A receita líquida é qualquer valor enviado em af\_net\_revenue, e o anunciante define o cálculo (por exemplo, receita após taxas da loja e/ou impostos, margem bruta ou receita após taxas de serviço). Para aplicativos que usam a receita da loja do ROI360, a AppsFlyer a calcula como o bruto menos as taxas e os impostos da loja de aplicativos (Líquido = Bruto - taxas da loja - impostos).

O valor vem do parâmetro af\_net\_revenue dos seus eventos in-app, da mesma forma que as métricas regulares de receita usam af\_revenue. O valor está na moeda da transação, expressa por af\_currency (USD por padrão).

Como o valor é preenchido:

* Se a **receita da loja do ROI360** estiver habilitada para o aplicativo, a AppsFlyer preencherá af\_net\_revenue automaticamente nos eventos de compra in-app e assinatura que registrar.
* Caso contrário, o valor vem do parâmetro af\_net\_revenue que você envia no evento in-app.
* Se a receita líquida não for fornecida por nenhum dos dois, a métrica mostrará N/A.

Consulte <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue">Sobre a receita da loja do ROI360</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure">Eventos in-app - Estrutura do evento</Anchor>.

## Dimensões de "filtro" e "agrupar por" disponíveis

Você pode agrupar e filtrar métricas de atividade usando:

* Análise diária
  * As ad
  * ID do anúncio
  * Conjunto de anúncios
  * Adset ID
  * Aplicação
  * Tipo de atribuição
  * Tipo de toque atribuído
  * Campaign
  * ID da campanha
  * Canal
  * Geografia
  * Data
  * Palavras-chave
  * Canal de mídia
  * Acesso para
  * ID do site
  * Platform
  * Sub param 1
  * Fonte:
  * Campanha
  * Destino do engajamento
  * Loja de aplicativos na instalação
* Análise mental
  * Aplicação
  * Campaign
  * ID da campanha
  * Geografia
  * Mês
  * Canal de mídia
  * Acesso para

## Especificações e limitações

| **Especificações** | **Observação** |
| --- | --- |
| Atualização dos dados | O tempo real não tem suporte para aplicativos web, CTV ou PC e console nas métricas de cohort e atividade.<br /><br />**Observação:** as métricas de LTV para aplicativos CTV e PC e console estão disponíveis em tempo real — essa limitação se aplica apenas aos dados de atividade e cohort. |
| Granularidade de tempo | Para aplicativos web, CTV e PC e console, os dados de cohort e atividade estão disponíveis apenas com granularidade diária. Detalhamentos semanais e mensais não têm suporte nessas plataformas. |
| Receita de anúncios | Dados em tempo real não possuem suporte. |
| Métricas de receita líquida - períodos | Com suporte para métricas de atividade e cohort. Não tem suporte para LTV. |
| Métricas de receita líquida - atualização dos dados | A análise em tempo real não está disponível. Os dados ficam disponíveis a partir do dia seguinte. |
| Métricas de receita líquida - receita de anúncios | Os eventos de receita de anúncios não estão incluídos nas métricas de receita líquida.<br /><br />**Dica:** Para ver a receita líquida que inclui a receita de anúncios, crie uma métrica personalizada que adicione a receita de anúncios à receita líquida, por exemplo: Receita líquida + Receita (evento: af\_ad\_revenue). Consulte <Anchor target="_blank" href="/marketers/pt/docs/beta-set-up-custom-metrics-in-my-dashboards">Configure métricas personalizadas no My Dashboards</Anchor>. |
| Métricas de receita líquida - fonte de atribuição | Não tem suporte para SKAN e SSOT. |
| Métricas de receita líquida - plataformas | Somente Android e iOS (mobile). |
| Fusos horários | Todas as métricas estão disponíveis nos fusos horários locais, exceto aquelas que são apenas UTC:<ul><li>Usuários ativos nos últimos 31 dias</li><li>DAU/MAU</li><li>Usuários ativos com agrupamento mensal (MAU)</li></ul> |
| Gráficos | Atualmente, apenas o **DAU** está disponível em formato de linha ou coluna |
| Widgets | KPI e widgets de tabela estão disponíveis para todas as métricas de atividade. |
| Intervalo de dados diário | Limitado a 62 dias por visualização |
| Eventos de desinstalação | Não incluído nos dados de atividade |
| Histórico de dados | Até 3 anos (diários) |
| Agrupamento geográfico | Com base na geolocalização no momento da instalação; limitado a 62 geos |
| Métricas de sessão | <ul><li>Os dados de atividade passaram a ser unificados para UA e retargeting a partir de 1 de fevereiro de 2025</li><li>Você pode visualizar o retargeting filtrando os valores de**tipo de atribuição** por **reengajamentos** e **reatribuições**.</li></ul> |
| Métricas de visualização unificada | Todas as métricas estão disponíveis apenas na visualização unificada |
| Utilizadores únicos em eventos in-app e usuários ativos | As métricas de **usuários únicos em eventos in-app** e **usuários ativos** no My Dashboards se baseiam em um algoritmo de estimativa estatística que reduz duplicatas e oferece uma visão consistente da atividade do usuário. |
| A análise em tempo real não está disponível. | Se o intervalo de datas selecionado incluir hoje e dias anteriores, e o widget não estiver agrupado por data, os dados de hoje não serão exibidos. |

<div data-zendesk-anchors="h_01KXNJ1RB3ZWVG9SASCRNSS9N1=aten%C3%A7%C3%A3o about-activity-metrics=sobre-as-m%C3%A9tricas-de-atividade h_01K4Q11V7F3KCHT69SC90J54Q6=sobre-as-m%C3%A9tricas-de-atividade dashboard-information=informa%C3%A7%C3%B5es-sobre-o-dashboard h_01K4Q11V7MV95K09VC3D0190V3=informa%C3%A7%C3%B5es-sobre-o-dashboard available-activity-metrics=m%C3%A9tricas-de-atividade-dispon%C3%ADveis h_01K4Q11V7QY8DB1FNRG3AJBDWR=m%C3%A9tricas-de-atividade-dispon%C3%ADveis available-inapp-metrics=m%C3%A9tricas-dispon%C3%ADveis-no-aplicativo h_01K4Q11V7Z4Y4TWT5E2J0354JA=m%C3%A9tricas-dispon%C3%ADveis-no-aplicativo supported-filter-and-group-by-dimensions=dimens%C3%B5es-de-filtro-e-agrupar-por-dispon%C3%ADveis h_01K4Q11V86S336QH6ZG5XS5AWG=dimens%C3%B5es-de-filtro-e-agrupar-por-dispon%C3%ADveis specifications-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01K4Q11V8DCBT4CY5MJZ44X7SX=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />

---
title: >-
  Detecção básica de fraude e insights com o dashboard e o relatório do
  ProtectLITE
metadata:
  keywords:
    - Advertisers
    - Protect360
    - Marketers
    - Protect360 / Fraud protection
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360 / Fraud protection
  created_at: '2021-01-25T09:47:02Z'
  edited_at: '2026-08-18T00:07:47Z'
  id: 360017223058
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/360017223058
---
> **Visão geral:** O ProtectLITE fornece insights sobre instalações fraudulentas bloqueadas pelo nosso mecanismo de proteção básico e gratuito, bem como instalações bloqueadas devido à aplicação de regras de validação.

## ProtectLITE

O ProtectLITE oferece proteção básica e gratuita contra fraude de atribuição de instalação. Proteção e detecção avançadas contra fraude estão disponíveis com o <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide">Protect360</Anchor>.

Quando a AppsFlyer identifica fraude, ela é bloqueada nos dados de tráfego (disponíveis nos dashboards da AppsFlyer e nos relatórios de dados brutos), mas não impacta a experiência do usuário final no aplicativo. Isso significa que o usuário do aplicativo ainda pode usá-lo e gerar receita para o anunciante.

O dashboard do ProtectLITE:

* Exibe dados agregados de todos os seus aplicativos para instalações bloqueadas em tempo real, seja devido a instalações fraudulentas, instalações sequestradas ou às suas <Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud">Regras de validação</Anchor>.
* Permite que você se aprofunde na análise das instalações identificadas usando as opções de filtragem e agrupamento.
* Mostra recursos adicionais antifraude que podem ser acessados somente com uma assinatura do Protect360, incluindo: fraude avançada em tempo real, fraude pós-atribuição, fraude em eventos in-app, Regras de validação para eventos in-app e ferramentas de análise de anomalias.

Dados brutos do ProtectLITE <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">dados brutos</Anchor>:

* Está disponível no relatório de instalações do Protect360 pela página Export Data e pela Pull API.

<div id="dashboard" />

## Painel

Para visualizar o dashboard do ProtectLITE, na AppsFlyer, acesse **Protect360**.

Os recursos do painel estão descritos nas seções a seguir.

<div id="filters-and-groupings" />

<Accordion title="Filtros e agrupamentos">

**Janela de filtro e agrupamentos**

As seguintes opções de filtros e agrupamento estão disponíveis:

* Filtros básicos:
  * Nome da aplicação
  * Tipo de fonte: Orgânica e não orgânica
  * Canal de mídia
  * Geografia
  * Intervalo de datas (<Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#protect360-dashboard">consulte compatibilidade com fuso horário</Anchor>)
* Filtros expandidos - clique na seta azul, à direita do seletor de datas:
  * Agências
  * Canais
  * Tamanho mínimo de cohort
* Opções de agrupamento - escolha diferentes dimensões para agrupar os dados de fraudes e obter os insights específicos necessários:
  * **Aplicativo:** compare a quantidade total de fraude em cada um dos seus aplicativos.
  * **Canal de mídia** (padrão): compare a fraude tratada de cada um dos canais de mídia usados pelos seus aplicativos.
  * **Canal de mídia + Campanha**: compare a fraude tratada de todas as suas campanhas em todos os canais de mídia usados pelos seus aplicativos.
  * **Canal de mídia + ID do site**: compare a fraude tratada de todos os publishers (IDs do site) em todos os canais de mídia usados pelos seus aplicativos.
  * **Canal de mídia + ID do site + Campanha**: compare a fraude tratada de todos os publishers (IDs do site) em todos os canais de mídia usados pelos seus aplicativos, associada aos nomes de campanha relevantes.
  * **Geolocalização**: compare a fraude tratada de todos os países.
  * **Canal de mídia + Geolocalização** (disponível no dashboard de eventos in-app): compare a fraude tratada de cada um dos canais de mídia usados pelos seus aplicativos associados aos países relevantes.

</Accordion>

<div id="installs-headline-metrics" />

<Accordion title="Instalações—métricas do título">

As métricas do título permitem que você veja:

* Economia estimada
* Instalações identificadas
* Suspeita de ameaça geral de fraude

As métricas são relevantes para o período selecionado no filtro de data.

Para os KPIs de Economia estimada e Instalações identificadas, há um valor percentual. Este valor mostra a relação do KPI apresentado com o intervalo de datas paralelo anterior. Por exemplo, esta semana comparada com a anterior, ou quaisquer dias selecionados no intervalo de datas comparados ao mesmo número de dias anteriores: se houver um aumento de X% nas economias estimadas, significa que o intervalo de datas paralelo anterior teve menos X% de instalações fraudulentas.

<div id="estimated-savings" />

#### Economia estimada

<Image align="center" alt="" src="https://files.readme.io/f53d6245eb8bb81fb652a05869fe71102ed50ab304d2fc8faf1cc17198794470-360019038197.jpg" />

Métricas de economia estimada:

* Exibe o valor da fraude identificada e bloqueada em tempo real pelo ProtectLITE e pelas Regras de validação, a ser acertado por você com as ad networks.
* Usa a fórmula: economias estimadas = número de instalações bloqueadas X eCPI médio de aplicativos
* Não são relevantes para orgânico tráfego.

Para mais detalhes sobre como esse valor é calculado, leia este <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide#faq">FAQ</Anchor>.

<div id="identified-installs" />

#### Instalações identificadas

<Image align="center" alt="" src="https://files.readme.io/2bc38a1ee19b4a13c18ed7571d97efd0f855d27142e8a6cd9a761cac276d3bd0-360019090998.jpg" />

As métricas de instalações identificadas exibem o número de instalações identificadas e bloqueadas em tempo real pelo ProtectLITE e pelas Regras de Validação.

<div id="suspected-overall-fraud-threat" />

#### Suspeita de ameaça geral de fraude

<Image align="center" alt="" src="https://files.readme.io/bb6a33cfea1dbff695d46a4b2f6547b756740cf35b750db25097d7ec772cc3d8-360019091058.jpg" />

O nível geral de ameaça suspeito:

* É uma estimativa da fraude que seria bloqueada pelo Protect360, se você tivesse uma assinatura.
* Dá uma boa ideia de se você deve fazer upgrade para o Protect360 para receber uma proteção antifraude mais avançada.

</Accordion>

<div id="installs-chart" />

<Accordion title="Instalações—gráfico">

<div id="fraud-trend-over-time-chart" />

#### Gráfico de tendência de fraudes ao longo do tempo

O gráfico exibe o número de instalações por dia bloqueadas pelo ProtectLITE e pelas Regras de Validação, para o período selecionado no filtro de data.

</Accordion>

<div id="installs-table" />

<Accordion title="Instalações—tabela">

<div id="identified-fraud-breakdown" />

#### Análise de fraudes identificadas

A tabela exibe o número de instalações bloqueadas pelo ProtectLITE e pelas Regras de Validação para o período selecionado no filtro de data.

Clique em **Exportar CSV** para fazer o download da tabela para a área de trabalho no formato CSV.

A tabela é apresentada em um formato de visão geral, conforme a imagem abaixo:

<Image align="center" alt="plite_fraud_table.jpg" src="https://files.readme.io/81246675ce8f0e1243e0c0d64e1cf347246bb403894718ad9e23c56fc594eb84-360019038257.jpg" />

A estrutura dinâmica da tabela permite que você:

* Clique no botão de configurações da tabela para adicionar ou remover colunas da tabela.  
  Se você fizer alguma alteração, certifique-se de clicar no botão Salvar em seguida para que suas personalizações sejam salvas para visitas futuras.
* Altere a ordem das colunas arrastando as seções de colunas nas configurações de colunas.

<Image align="center" alt="plite_edit_columns.jpg" src="https://files.readme.io/52fc1378d4c758d80ed2a89b24f5b7fa949c9ccccae7ff5edf4af307538e805a-360019038297.jpg" />

<div id="content-of-the-identified-fraud-breakdown-table" />

#### Conteúdo da tabela detalhada de fraudes identificadas

| Coluna da tabela | A descrição |
| --- | --- |
| Agrupamentos | <ul><li>[Padrão] A tabela e o painel são agrupados por canal de mídia.</li><li>Ao selecionar uma fonte de mídia específica, o agrupamento é feito automaticamente tanto por Canal de mídia quanto por ID do site.</li><li>Agrupamentos opcionais incluem Campanha, Geolocalização, Canal, agência e suas combinações.</li><li>Se você selecionar um agrupamento com dimensões que se aplicam somente ao tráfego não-orgânico , a tabela exibirá N/A para a orgânico fonte de mídia.</li></ul> |
| **de instalações** | **Detalhamento principal das instalações bloqueadas devido a fraude e às Regras de Validação** |
| Total (A) | <ul><li>Total de instalações = Todas as instalações do aplicativo, incluindo instalações fraudulentas e instalações identificadas por meio das Regras de Validação.</li><li>Instalações regulares estão disponíveis por canal de mídia (não-orgânica) no painel de Visão geral.</li></ul> |
| Instalações identificadas (B) | <ul><li>Número total de instalações identificadas e bloqueadas em tempo real</li><li>As instalações orgânicas bloqueadas não são exibidas no dashboard. Para ver instalações orgânicas bloqueadas, use os relatórios de dados brutos.</li><li>[Padrão] A tabela é classificada em ordem decrescente usando este KPI.</li></ul> |
| **% de instalações identificadas** (B/A) | Instalações identificadas / Total de instalações |
| **Identificados pós-atribuição (C)** | Requer o Protect360 |
| **% de identificados pós-atribuição (C/A)** | Requer o Protect360 |
| **Instalações falsas** | **Instalações fraudulentas que simulam a atividade real do usuário.** |
| Bloqueio em tempo real | Instalações falsas bloqueadas em tempo real. |
| Identificados pós-atribuição | Requer o Protect360 |
| **Hijacking de instalações** | **Últimos cliques fraudulentos roubando a atribuição de instalações de usuários reais.** |
| Bloqueio em tempo real | Hijacking de instalações bloqueadas em tempo real. |
| Identificados pós-atribuição | Requer o Protect360 |
| **Regras de validação** | **Instalações consideradas inválidas devido às condições das regras de validação.** |
| Instalações bloqueadas | Instalações bloqueadas por regras de validação. |
| Atribuição bloqueada | Instalações com atribuição corrigida devido às regras de validação. |
| **Cliques** | **Cliques legítimos na fonte.**<br /><br />**Observação:** Todos os tipos de atribuição devem ser selecionados na barra de filtro para que os dados de clique sejam exibidos na tabela (caso contrário, serão exibidos como N/A). Certifique-se de ajustar suas seleções de filtro de forma correspondente. |
| Total (E) | Número total de cliques legítimos recebidos da fonte. |
| Bloqueado | Cliques bloqueados por conta do limite de cliques |
| **Impressions** | **Impressões da fonte.**<br /><br />**Observação:** Todos os tipos de atribuição devem ser selecionados na barra de filtro para que os dados de impressões sejam exibidos na tabela (caso contrário, serão exibidos como N/A). Certifique-se de ajustar suas seleções de filtro de forma correspondente. |
| Total | Número total de impressões legítimas e fraudulentas recebidas da fonte |
| Bloqueado | Impressões bloqueadas por conta da fraude (incluindo impressões limitadas) |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificações e limitações">

| Caraterística | Observações |
| --- | --- |
| Acesso do anunciante | Todos os usuários da conta. |
| Acesso à rede de anúncios | <ul><li>O dashboard do ProtectLITE e o acesso a dados brutos exigem <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-ad-network">permissão do anunciante.</Anchor></li><li>O anunciante deve ter a ad network como um parceiro integrado.</li></ul> |
| Acesso à agência | O dashboard do ProtectLITE e o acesso a dados brutos exigem <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-ad-network">permissão do anunciante.</Anchor> |
| Transparência das agências | Agência transparente: pode acessar fontes de mídia específicas<br /><br />Agências não transparentes: não acessam fontes de mídia específicas |

</Accordion>

<div data-zendesk-anchors="01JDHEKR6W19WD6HXFFMRNXKFF=protectlite dashboard=painel 01JDHEKR6YGEKRB23M19F5ZGQ5=painel 01JDHEKR6YPNDQAK3ATDRDDZTC=filters-and-groupings installs%E2%80%94headline-metrics=installs-headline-metrics 01JDHEKR75TF5RHJTFM91XPYPY=installs-headline-metrics estimated-savings=economia-estimada 01JDHEKR76MMVSJSWFTZS5PRBK=economia-estimada identified-installs=instala%C3%A7%C3%B5es-identificadas 01JDHEKR77VGHR1BWQFPYSWW2E=instala%C3%A7%C3%B5es-identificadas suspected-overall-fraud-threat=suspeita-de-amea%C3%A7a-geral-de-fraude 01JDHEKR78BBFEZS98VG0VTERN=suspeita-de-amea%C3%A7a-geral-de-fraude installs%E2%80%94chart=installs-chart 01JDHEKR795RK8KP9BZ0WECQW8=installs-chart fraud-trend-over-time-chart=gr%C3%A1fico-de-tend%C3%AAncia-de-fraudes-ao-longo-do-tempo 01JDHEKR79YM7VWE6NH2FJ70NS=gr%C3%A1fico-de-tend%C3%AAncia-de-fraudes-ao-longo-do-tempo installs%E2%80%94table=installs-table 01JDHEKR79ZBQVSTT4GA162J94=installs-table identified-fraud-breakdown=an%C3%A1lise-de-fraudes-identificadas 01JDHEKR79H7PQFEJGWAY4RMJC=an%C3%A1lise-de-fraudes-identificadas content-of-the-identified-fraud-breakdown-table=conte%C3%BAdo-da-tabela-detalhada-de-fraudes-identificadas 01JDHEKR7BR6ESS9DX03NMHPT0=conte%C3%BAdo-da-tabela-detalhada-de-fraudes-identificadas 01JDHEKR9JCAR22V33B7TFZSPV=traits-and-limitations" />

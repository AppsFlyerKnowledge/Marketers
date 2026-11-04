---
title: Painel do Protect360
metadata:
  keywords:
    - dashboard
    - Advertisers
    - Protect360
    - protect 360
    - '360'
    - P360
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-08-11T09:58:07Z'
  edited_at: '2026-08-19T00:07:46Z'
  id: 360011793077
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/360011793077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral:** O painel do Protect360 oferece insights sobre tráfego fraudulento e instalações bloqueadas em razão da aplicação de regras de validação.

<div id="about-protect360-dashboard" />

## Sobre o painel do Protect360

O painel do Protect360:

* Exibe dados agregados de fraude no nível da conta.
* Tem duas visualizações de painel:
  * Instalações (CPI)
  * Eventos in-app (CPA)
* Organiza fraudes com base em categorias, incluindo:
  * Instalações falsas versus instalações com hijacking
  * Fraude bloqueada em tempo real versus fraude identificada após a atribuição
  * Fraude de UA versus campanhas de retargeting
* Permite que você se aprofunde na análise dos eventos de fraude usando as opções de filtragem e agrupamento.

Para visualizar o painel do Protect360, na AppsFlyer, acesse **otimizar** > **Protect360.** 

<div id="filters-and-groupings" />

<Accordion title="Filtros e agrupamentos">

**Janela de filtro e agrupamentos**

[![p360_filters_2.png](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)

As seguintes opções de filtros e agrupamento estão disponíveis:

* Filtros básicos:
  * Nome do aplicativo
  * Tipo de fonte: Orgânica e não orgânica
  * Canal de mídia
  * Geolocalização
  * Intervalo de datas (<Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#protect360-dashboard">consulte compatibilidade com fuso horário</Anchor>)
  * Tipo de atribuição Instalações, reatribuições e reengajamentos.
  * [Eventos a pagar](/docs/protect360-dashboard#payable-events) (disponíveis no painel de eventos in-app)
* Filtros expandidos - clique na seta azul, à direita do seletor de datas:
  * Agências
  * Campanhas
  * Canais
* Opções de agrupamento - escolha diferentes dimensões para agrupar os dados de fraudes e obter os insights específicos necessários:
  * **Aplicação:** Compare a quantidade total de fraudes para cada um de seus aplicativos.
  * **Fonte de mídia**(padrão): Compare a fraude identificada de cada uma das fontes de mídia usadas por seus aplicativos
  * **Fonte de mídia + campanha**: Compare a fraude identificada em todas as suas campanhas entre todas as fontes de mídia usadas por seus aplicativos
  * **Fonte de mídia + ID do site**: Compare a fraude identificada em todos os publishers (IDs de site) entre todas as fontes de mídia usadas por seus aplicativos
  * **Fonte de mídia + ID do site + campanha**: Compare a fraude identificada em todos os publishers (IDs de site) entre todas as fontes de mídia usadas por seus aplicativos, associadas aos nomes de campanha relevantes
  * **Fonte de mídia + Geo**: (disponível no dashboard de eventos in-app): compare a fraude identificada em cada uma das fontes de mídia usadas por seus aplicativos associados aos países relevantes
  * **Fonte de mídia + Tipo de atribuição**: Compare a fraude identificada em cada uma das suas fontes de mídia, associada ao tipo de atribuição selecionado (instalações, reatribuições e/ou reengajamentos)
  * **Geolocalização**: compare a fraude identificada em todos os países

</Accordion>

<div id="installs-dashboard" />

## Dashboard de instalação

O painel de instalação exibe dados baseados em LTV, ou seja, dados relacionados a instalações, reatribuições e reengajamentos que ocorreram durante o intervalo de datas selecionado.

Os recursos do painel estão descritos nas seções a seguir.

<div id="installs-headline-metrics" />

<Accordion title="Instalações—métricas do título">

As métricas do título permitem que você veja:

* **Atribuições fraudulentas identificadas** - Número total de instalações fraudulentas
* Número de eventos fraudulentos (in-app)
* **Total de atribuições marcadas** - Total de atribuições marcadas
* Na seção Filtrar por **do painel de Atividades in-app, ative Eventos a pagar.**
* **Instalações comprometidas identificadas** - Número de instalações detectadas com engajamentos não autênticos
* **Média de engajamentos por instalação** - Número médio de  engajamentos associados à instalação

Para cada KPI, há um valor percentual. Esse valor mostra qual é o status do KPI exibido em relação ao mesmo intervalo de datas anterior a ele. Por exemplo, a semana atual em comparação com a semana passada, ou quaisquer dias selecionados no intervalo de datas em comparação com o mesmo número de dias anteriores: se mostrar um aumento de X% na economia estimada, significa que o intervalo de datas paralelo anterior teve X% menos instalações fraudulentas, reatribuições e reengajamentos.

**Atribuições fraudulentas identificadas**

[<Image alt="" src="https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png" width="100%" />](https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png)

A métrica de total de fraudes identificadas exibe as quantidades de:

* Instalações, reatribuições e reengajamentos fraudulentos bloqueados em tempo real por vários motivos para um bloqueio de fraude.
* Instalações, reatribuições e reengajamentos identificados como fraude pós-atribuição.

**Eventos in-app bloqueados**

[<Image alt="" src="https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png" width="100%" />](https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png)

As métricas de eventos in-app bloqueados exibem a quantidade de eventos in-app bloqueados pela AppsFlyer. Os eventos podem ter sido bloqueados por pertencerem a instalações bloqueadas ou por serem sinalizados como eventos de pós-atribuição suspeitos.

**Total de atribuições marcadas**

[<Image alt="" src="https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png" width="100%" />](https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png)

As métricas de atribuições marcadas mostram o número total de instalações reconhecidas como fraude, mas que foram marcadas pelo usuário como marcadas e não bloqueadas. isso não inclui eventos in-app.

**Número de eventos fraudulentos (in-app)**

[<Image alt="" src="https://files.readme.io/79650837a722efdc3bea39664f0d5eb774ac6acbfb15e5f64d9a56f7c03b21fe-32637238112145.png" width="100%" />](https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png)

As métricas de eventos in-app marcados mostram o número total de instalações reconhecidas como fraude, mas que foram marcadas pelo usuário como marcadas e não bloqueadas.

**Impressões bloqueadas por conta do limite de impressões**

<Image alt="" src="https://files.readme.io/60fdba97e9eb920e26ac2667431b760a7dee62b53396196403d68326bff6c3cc-41459847283729.png" width="624px" />

Instalações em que a lógica de atribuição da AppsFlyer detectou que o dispositivo recebeu um alto volume de engajamentos não autênticos.

**Usa a fórmula: Economias estimadas = número de instalações bloqueadas X eCPI médio de aplicativos**

<Image alt="" src="https://files.readme.io/edb695ad30e16e403d953fd0fad274d5733ca4e2dc411baad7bbe4179cfcd0b0-41459862819857.png" width="624px" />

 A média de engajamentos por instalação mostra o número médio de engajamentos associados à instalação.

</Accordion>

<div id="installs-charts" />

<Accordion title="Instalações—gráficos">

<div id="identified-fraud-trend-chart" />

#### Gráfico de tendências de fraude identificadas

O gráfico de tendências de fraude identificadas exibe o número de instalações fraudulentas, reatribuições e reengajamentos por dia, detalhado por:

* **Tipo de detecção**: Instalações bloqueadas em tempo real e instalações identificadas como fraude pós-atribuição.
* **Tipo de atribuição**: Instalações, reatribuições e reengajamentos.
* **Tipo de fonte**: Não orgânica e orgânica
* **Status de detecção**: comparação entre dados marcados, não marcados e bloqueados.
* **Taxa de comprometimento**: total de atribuições sinalizadas como comprometidas em relação ao total de atribuições.

A exibição pode ser feita em um gráfico de linhas ou um gráfico de barras.

<div id="hijacked-installs-attribution-correction-chart" />

#### Gráfico de correção de atribuição de hijacking de instalações

O gráfico de correção de atribuição de instalações com hijacking exibe fontes de mídia que tentaram receber crédito por instalações, reatribuições e reengajamentos, assim como as últimas fontes válidas que auxiliaram a instalação.

Você pode:

* Filtrar por atribuições com hijacking identificadas em tempo real, pós-atribuição ou atribuições identificadas por meio de regras de validação.
* Defina qual atribuição de fontes válidas é corrigida ou a partir de quais fontes de hijacking a atribuição foi corrigida.
* Altere a visualização do gráfico para um formato de tabela e baixe os dados como CSV.

**Observação:**

* Este gráfico só pode ser acessado pelos anunciantes. Agências e ad networks não têm acesso.
* Quando os hijackings são bloqueados em tempo real, as atribuições corretas são exibidas nos dashboards e relatórios da AppsFlyer (não apenas no Protect360). Quando os hijackings são identificados após a atribuição, as atribuições corretas são exibidas apenas nos dados brutos do Protect360.
* Esse gráfico pode exibir a correção **para** orgânica, mas não **de** orgânica.

<div id="identified-fraud-chart" />

#### Gráfico de fraude identificada

O gráfico de fraude identificada exibe os tipos de fraude que ocorrem, por porcentagem. A análise de fraudes pode ser feita por:

* Razão do bloqueio
* <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#nível-de-instalação-razões-secundárias-para-bloqueio-de-instalações-falsas">Sub-razão do bloqueio</Anchor>
* Tipo de tag
* Motivo da tag
* Submotivo da tag
* Canal de mídia
* Campanha
* Geolocalização
* Aplicativo

<div id="affiliate-attribution-model" />

#### Modelo de atribuição de afiliados

O novo **Modelo de Atribuição de Afiliados** da AppsFlyer resolve diretamente o problema de inundação de cliques. No centro dele está um algoritmo de atribuição dedicado que detecta ativamente dispositivos inundados e valida o engajamento usando métodos de autenticação e análise comportamental de IA em tempo real. O resultado é uma atribuição imparcial, resiliente à fraude e baseada na intenção real do usuário.

* **Taxa de comprometimento:** total de atribuições sinalizadas como comprometidas em relação ao total de atribuições
* **Reflexão do candidato:**
  * Candidatos por comprometida - número médio de candidatos do total de atribuições **sinalizadas** como comprometidas
  * Candidatos por não comprometida - número médio de candidatos do total de atribuições **não** **sinalizadas** como comprometidas
* Essas métricas também se refletem no gráfico de tendências ao longo do tempo:
  * O número total de instalações fraudulentas
  * Candidatos por comprometida
  * Candidatos por não comprometida

Instalações comprometidas são instalações em que a lógica de atribuição da AppsFlyer detectou que o dispositivo recebeu um alto volume de engajamentos não autênticos. Isso indica que o dispositivo estava sob intensa manipulação por flooding, referindo-se especificamente a casos em que as instalações são manipuladas

</Accordion>

<div id="installs-table" />

<Accordion title="Instalações—tabela">

<div id="identified-fraud-breakdown" />

#### Análise de fraudes identificadas

A tabela de **análise de fraudes identificadas** exibe os seguintes dados:

* Fraude bloqueada em tempo real
* Fraude identificada e marcada após a atribuição
* Outras indicações de fraude por canal de mídia

A tabela é apresentada em um formato de visão geral, conforme a imagem abaixo:

[![p360_main_table.png](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)

A estrutura dinâmica da tabela:

* Permite clicar no botão de configurações da tabela para adicionar ou remover colunas à tabela.  
  Se você fizer alterações na tabela, certifique-se de clicar no botão **Salvar** depois.
* É por usuário, de modo que cada usuário da conta com acesso ao Protect360 possa personalizar a estrutura da sua própria tabela. Veja [mais opções de tabelas](/docs/protect360-dashboard#opções-adicionais-de-tabela).

[![edit_table.jpg](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)

<div id="content-of-the-identified-fraud-breakdown-table" />

#### Conteúdo da tabela detalhada de fraudes identificadas

| Coluna da tabela | Descrição |
| --- | --- |
| Agrupamentos | <ul><li>[Padrão] A tabela e o painel são agrupados por canal de mídia.</li><li>Ao selecionar uma fonte de mídia específica, o agrupamento é feito automaticamente tanto por Canal de mídia quanto por ID do site.</li><li>Os agrupamentos opcionais incluem Campanha, GEO, Canal, Agência, Agência + Canal de mídia e suas combinações.</li><li>Se você selecionar um agrupamento com dimensões que se aplicam somente ao tráfego não orgânico, a tabela exibirá N/A para a fonte de mídia orgânica.</li></ul> |
| **Atribuições** | **Detalhamento do título de instalações fraudulentas bloqueadas e pós-atribuição.** |
| Total (A) | <ul><li>Total de instalações = instalações regulares (não-fraudulentas) + instalações bloqueadas</li><li>Instalações regulares estão disponíveis por canal de mídia (não-orgânica) no painel de Visão geral.</li></ul> |
| Bloqueadas (B) | <ul><li>Número total de instalações bloqueadas.</li><li>[Padrão] A tabela é classificada em ordem decrescente usando este KPI.</li></ul> |
| % Bloqueadas (B/A) | Instalações bloqueadas / Total de instalações |
| Pós-atribuição (C) | Instalações identificadas como fraude pós-atribuição. |
| % Pós-atribuição (C/A) | Instalações pós-atribuição / Número total de instalações |
| Total de instalações fraudulentas (D) | Instalações fraudulentas, bloqueadas em tempo real ou identificadas como pós-atribuição fraudulenta. |
| % Instalações fraudulentas (D/A) | Instalações fraudulentas / Número total de instalações |
| **Análise detalhada do tipo de atribuição de fraude** | **Os tipos de atribuição das instalações fraudulentas, divididos em instalações, reatribuições e reengajamentos.** |
| Instalações | A fraude se originou de uma campanha de UA. |
| Reatribuições | A fraude se originou de uma campanha de retargeting que levou a uma instalação. |
| Reengajamentos | A fraude se originou de uma campanha de retargeting que levou a um reengajamento. |
| **Falso** | **Instalações ou reatribuições fraudulentas que simulam a atividade real do usuário - divididas por blocos entre fraude em tempo real e pós-atribuição.** |
| Bloqueio em tempo real | Instalações falsas bloqueadas em tempo real. |
| Fraude pós-atribuição | Instalações falsas identificadas como fraude pós-atribuição. |
| **Sequestrado** | **Últimos cliques fraudulentos que roubam a atribuição de instalações de usuários reais - divididos por blocos em tempo real e pós-atribuição.** |
| Bloqueio em tempo real | Hijacking de instalações bloqueadas em tempo real. |
| Fraude pós-atribuição | Hijacking de instalações identificadas como fraude pós-atribuição. |
| **Regras de validação** | **Instalações que atendem às condições das regras de validação.** |
| Instalações bloqueadas | Instalações bloqueadas por regras de validação. |
| Atribuição bloqueada | Alterações na atribuição de instalações devido a regras de validação. |
| **Detalhes do bloqueio de instalações falsas** | **Detalhamento de instalações falsas fraudulentas pós-atribuição e bloqueadas, geralmente realizadas programaticamente** |
| Denylist de IDs de sites bloqueados | Instalações bloqueadas devido à inclusão do ID do site à denylist do Protect360. |
| Denylist da ID do site pós atribuição. | Instalações marcadas como fraudulentas devido à inclusão do ID do site na denylist pós-atribuição do Protect360. |
| Bots bloqueados | Bloqueio de tentativas de instalação feitas por bots automáticos. |
| Bots pós-atribuição | Instalações marcadas como fraude devido a atividades de bots automáticos identificados após a atribuição |
| Anomalias comportamentais bloqueadas | Instalações bloqueadas devido a anomalias comportamentais, ou seja, sessão anormal e desempenho de eventos in-app dos usuários. |
| Anomalias comportamentais pós-atribuição | Instalações marcadas como fraudulentas devido a anomalias comportamentais pós-atribuição. |
| Validação de instalações bloqueadas | Total de instalações bloqueadas devido à validação negativa da loja. |
| **Detalhes do bloqueio de hijackings de instalação** | **Detalhes dos últimos cliques fraudulentos destinados a roubar a atribuição de instalações do aplicativo feitas por usuário reais.** |
| Hijacking de instalações bloqueados | Hijacking de instalação bloqueada da fonte. |
| Hijacking de instalação pós-atribuição | Hijacking de instalação marcada como fraude na pós-atribuição. |
| Anomalias de CTIT bloqueadas | Instalações bloqueadas devido a anomalias do CTIT. |
| Anomalias de CTIT pós-atribuição | Anomalias CTIT marcadas como fraude na pós-atribuição. |
| Flooding de cliques bloqueados | Instalações bloqueadas devido a flooding de cliques (tentativas de fraude para enviar uma grande quantidade de cliques com o objetivo de ser responsável pelos últimos cliques antes de instalações aleatórias.) |
| Flooding de cliques pós-atribuição | Instalações de flooding de cliques marcados como fraude na pós-atribuição |
| **Cliques** | **Cliques da fonte**<br /><br />**Observação:** Todos os tipos de atribuição devem ser selecionados na barra de filtro para que os dados de clique sejam exibidos na tabela (caso contrário, serão exibidos como N/A). Certifique-se de ajustar suas seleções de filtro de forma correspondente. |
| Total (E) | Número total de cliques legítimos e fraudulentos recebidos da fonte |
| Bloqueadas | Cliques bloqueados por conta do limite de cliques |
| **Impressões** | **Impressões da fonte**<br /><br />**Observação:** Todos os tipos de atribuição devem ser selecionados na barra de filtro para que os dados de impressões sejam exibidos na tabela (caso contrário, serão exibidos como N/A). Certifique-se de ajustar suas seleções de filtro de forma correspondente. |
| Total | Número total de impressões legítimas e fraudulentas recebidas da fonte |
| Bloqueadas | Impressões bloqueadas por conta da fraude (incluindo impressões limitadas) |
| **Eventos in-app** | **Eventos in-app da fonte**<br /><br />**Observação:** Isso inclui eventos in-app de instalações; não inclui reatribuições ou reengajamentos. |
| Total (G) | Total de eventos in-app |
| Bloqueados (H) | Eventos in-app bloqueados |
| % (H/G) | Eventos in-app bloqueados / total de eventos in-app |
| **Indicadores de device farm** | **Indicadores de atividade fraudulenta de device farm, usando o reset de ID do dispositivo e fraude de limite de rastreamento de anúncios (LAT).**<br /><br />**Observação:** Inclui instalações e reatribuições; não inclui reengajamentos. |
| Instalações (I) | Instalações com um nov ID de dispositivo desconhecido para a AppsFlyer. |
| % instalações (I/A) | Novas instalações de dispositivos / Número total de instalações |
| % usuários fidelizados | KPI geral que indica se os usuários são reais ou falsos |
| **Indicadores de flooding de cliques** | **Indicações de fraude de flooding de cliques com base em taxas anormais de conversão ou assistência, ou tempo de CTIT.** |
| Taxa de conversão (%) | Uma baixa porcentagem em comparação com a taxa geral de conversão do aplicativo indica fraude por flooding de cliques.<br /><br />**Observação**: Todos os tipos de atribuição devem ser selecionados na barra de filtro para que os dados de taxa de conversão sejam exibidos na tabela (caso contrário, serão exibidos como N/A). Certifique-se de ajustar suas seleções de filtro de forma correspondente. |
| % Assistências | Uma alta porcentagem em comparação com outros canais de mídia (no widget de Assistências na página de visão geral) indica fraude por flooding de cliques. |
| CTIT > Mais de 60 minutos | Instalações, reatribuições e reengajamentos em que o tempo entre o clique e a primeira inicialização do aplicativo seja superior a 60 minutos. O cálculo inclui apenas instalações cujo CTIT seja inferior a 25 horas (e não todas as instalações). Normalmente, cerca de 30% das primeiras inicializações de aplicativos ocorrem mais de 60 minutos após o download. |
| CTIT > Mais de 5 horas | Instalações, reatribuições e reengajamentos em que o tempo entre o clique e a primeira inicialização do aplicativo seja superior a cinco horas. O cálculo inclui apenas instalações cujo CTIT seja inferior a 25 horas (e não todas as instalações). Normalmente, cerca de 20% das primeiras inicializações de aplicativos ocorrem mais de 5 horas após o download. |

<div id="additional-table-options" />

#### Opções adicionais de tabela

* Clique em **Exportar CSV** para fazer o download da tabela para a área de trabalho no formato CSV
* Clique no ícone de engrenagem para:
  * Alterar a ordem das colunas da tabela
  * Adicionar ou remover as colunas descritas acima
  * Adicionar ou remover qualquer um dos **eventos in-app bloqueados recentemente**. Para cada evento in-app adicionado, as seguintes colunas são exibidas:

| Coluna da tabela | Descrição |
| --- | --- |
| Contador de eventos (total) | Número de ocorrências bloqueadas do evento específico |
| Usuários únicos | Número de usuários únicos que obtêm o evento específico bloqueado |

Observe que taxas incomuns de um desses KPIs não indicam necessariamente fraude, pois muitos eventos são bloqueados devido a instalações fraudulentas pós-atribuição.

Os dados de eventos in-app no dashboard de CPI se baseiam em LTV, ou seja, são todos os eventos in-app associados às instalações que ocorreram durante o intervalo de datas especificado.

</Accordion>

<div id="in-app-events-dashboard" />

## Painel de eventos in-app

O painel de eventos in-app exibe dados baseados em atividades, ou seja, dados relacionados a eventos in-app que ocorreram durante o período selecionado, incluindo  eventos de instalações que ocorreram antes desse período.

Os recursos do painel estão descritos nas seções a seguir.

<div id="inapp-events-headline-metrics" />

<Accordion title="Eventos in-app — métricas do título">

[![](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)

As métricas do título permitem que você veja:

* Economia estimada
  * Disponível somente se os [**Eventos a pagar**](/docs/protect360-dashboard#payable-events) estiverem ativados.
  * Com base nos eventos a pagar que você configurou.
* Número total de IAEs fraudulentas identificadas

</Accordion>

<div id="inapp-events-charts" />

<Accordion title="Eventos in-app — gráficos">

<div id="fraud-trend-over-time-chart" />

#### **Gráfico de tendência de fraudes ao longo do tempo**

O gráfico de tendência de fraude ao longo do tempo exibe o número de eventos por dia, divididos em:

* **Em tempo real**: Eventos fraudulentos no aplicativo bloqueados em tempo real
* **Pós-atribuição**: Eventos fraudulentos identificados após a atribuição
* **Não fraude**

<div id="top-iae-fraud-by-media-source-chart" />

#### **Gráfico das principais fraudes IAE por canal de mídia**

A lista das principais fraudes de eventos in-app (IAE) por canal de mídia contém: 

* As 5 fontes de mídia com o maior número de eventos in-app fraudulentos em ordem decrescente.
* Um gráfico de barras para cada barra da fonte de mídia que exibe os seguintes tipos de eventos in-app como uma porcentagem do total de eventos in-app:
  * **Em tempo real**: Eventos fraudulentos no aplicativo bloqueados em tempo real
  * **Pós-atribuição**: Eventos fraudulentos identificados após a atribuição
  * **Não fraude**

</Accordion>

<div id="inapp-events-table" />

<Accordion title="Eventos in-app — tabela">

A tabela de **análise de fraudes de eventos in-app** exibe os seguintes dados:

* Fraude bloqueada em tempo real
* Fraude identificada e marcada após a atribuição
* Outras indicações de fraude por canal de mídia

A tabela é apresentada em um formato de visão geral, conforme a imagem abaixo:

[![IAE_fraud_table.jpg](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)

A estrutura dinâmica da tabela:

* Permite clicar no botão de configurações da tabela para adicionar ou remover colunas à tabela.  
  Se você fizer alterações na tabela, certifique-se de clicar no botão **Salvar** depois.
* É por usuário, de modo que cada usuário da conta com acesso ao Protect360 possa personalizar a estrutura da sua própria tabela. Veja [mais opções de tabelas](/docs/protect360-dashboard#installs-table).

[![iae_table_structure.jpg](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)

<div id="content-of-the-in-app-event-fraud-breakdown-table" />

#### Conteúdo da tabela de análise de fraudes de eventos in-app

| Coluna da tabela | Descrição |
| --- | --- |
| Agrupamentos | <ul><li>[Padrão] A tabela e o painel são agrupados por canal de mídia.</li><li>Ao selecionar uma fonte de mídia específica, o agrupamento é feito automaticamente tanto por Canal de mídia quanto por ID do site.</li><li>Os agrupamentos opcionais incluem Campanha, GEO, Canal, Agência, Agência + Canal de mídia e suas combinações.</li></ul> |
| **Eventos in-app** | **Detalhes do título de IAEs fraudulentos bloqueados e pós-atribuição.** |
| Total de IAE (A) | <ul><li>Total de IAE = IAEs regulares (não fraudulentos) + IAEs bloqueados + IAEs identificados como fraude pós-atribuição.</li><li>IAEs regulares estão disponíveis por fonte de mídia (não-orgânicas) no painel de Visão geral.</li></ul> |
| Total de IAEs fraudulentos (B) | <ul><li>Número total de IAEs bloqueados + IAEs identificados como fraude pós-atribuição.</li><li>[Padrão] A tabela é classificada em ordem decrescente usando este KPI.</li></ul> |
| % eventos fraudulentos (B/A) | IAEs fraudulentos/Total de IAEs |
| **Bloqueios em tempo real de IAE falso** | **IAEs fraudulentos bloqueados em tempo real.** |
| IAE falso | IAE falso identificado como fraude e bloqueado em tempo real. |
| Instalações falsas | A instalação original foi identificada como fraude e bloqueada em tempo real. |
| Instalações falsas pós-atribuição | A instalação original foi identificada como fraude pós-atribuição, antes do IAE. |
| **Salvo de hijacking em tempo real** | **IAEs com a instalação original que passaram por hijacking feito por uma fonte fraudulenta, que a AppsFlyer atribui corretamente à última fonte não fraudulenta.** |
| Corrigida para orgânica | Instalações que sofreram hijacking com a última fonte não fraudulenta sendo orgânica. |
| Corrigida para fonte não-orgânica | Instalações que sofreram hijacking com a última fonte não fraudulenta sendo uma fonte de mídia não-orgânica. |
| **Fraude de IAE pós-atribuição** | **Eventos in-app identificados como fraude pós-atribuição.** |
| Instalações falsas | IAE ocorreu antes da instalação ser identificada como fraude pós-atribuição. |
| Instalações com hijacking | IAE ocorreu antes da instalação ser identificada como hijacked, e não pode ser corretamente atribuída após a atribuição. |
| **Regras de validação** | **IAEs bloqueados por cumprir com as condições das regras de validação.** |
| Instalações bloqueadas | IAEs de instalações bloqueadas por regras de validação. |
| IAE bloqueado | IAEs bloqueados por regras de validação. |
| Corrigida para orgânica | Instalações que sofreram hijacking com a última fonte não fraudulenta sendo orgânica. |
| Corrigida para fonte não-orgânica | Instalações que sofreram hijacking com a última fonte não fraudulenta sendo uma fonte de mídia não-orgânica. |

<div id="additional-table-options-1" />

#### Opções adicionais de tabela

* Clique em **Exportar CSV** para fazer o download da tabela para a área de trabalho no formato CSV
* Clique no ícone de engrenagem para:
  * Alterar a ordem das colunas da tabela
  * Adicionar ou remover as colunas descritas acima

A quantidade de eventos mostrados é baseada em atividades, não em LTV, ou seja, é o número exato de bloqueios de eventos durante o intervalo de datas especificado.

</Accordion>

<div id="payable-events" />

<Accordion title="Eventos a pagar">

Eventos a pagar são IAEs que têm um custo. Uma vez ativado e configurado, o dashboard de atividades in-app exibe apenas dados relacionados a eventos a pagar.

Para ativar eventos a pagar no painel de atividades in-app:

* Na seção Filtrar por **do painel de Atividades in-app, ative Eventos a pagar.**   
  [![](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)

**Para configurar eventos a pagar**:

1. No painel de Atividades in-app, clique em **Configurar eventos a pagar**.

   [![](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)

   O pop-up Configurar eventos a pagar é exibido.

   [![](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)
2. [Opcional] Se você configurar um novo evento a pagar, clique em **Adicionar novo**.
3. Com base nos IAEs a pagar que você deseja exibir no painel, selecione os seguintes itens nos menus suspensos:
   * Aplicativos
   * Eventos in-app
   * Canais de mídia
   * Campanhas
4. Insira o CPA do IAE.
5. Clique em **Salvar.**
6. Clique em **Fechar.**

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Redirecionamento | <ul><li>O painel de controle das instalações (CPI) pode exibir a divisão por toque atribuída entre parcelas, reatribuições e reengajamentos.</li><li>O painel de eventos in-app (CPA) exibe eventos fraudulentos de instalação da UA, mas não do retargeting. **Observação**: Eventos fraudulentos de reatribuições que são identificados em tempo real podem ser vistos em relatórios de dados brutos.</li></ul> |
| Dados históricos | Os dados estão disponíveis desde o início da assinatura do Protect360 |
| Atualização dos dados | Atualizados diariamente.<ul><li>Instalações (CPI) às 16:00 UTC</li><li>Eventos in-app (CPA) às 21:00 UTC</li></ul> |
| Canal de mídia indisponível | Se um canal de mídia não estiver disponível no filtro, isso pode ser devido ao bloqueio de todo o tráfego dele.<br /><br />Para filtrar com base no canal de mídia, você pode usar o link dele na tabela de detalhamento de fraude identificada |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide">Visão geral do Protect360</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">Relatórios de dados brutos</Anchor>

<div data-zendesk-anchors="about-protect360-dashboard=sobre-o-painel-do-protect360 01H8H9GQ17C4PBHCAMXE879BX7=sobre-o-painel-do-protect360 01H8H9GQ173SQ8P29C4DETJRTD=filters-and-groupings installs-dashboard=dashboard-de-instala%C3%A7%C3%A3o 01H8H9GQ173H3QH1Y5KZ26XMCW=dashboard-de-instala%C3%A7%C3%A3o installs%E2%80%94headline-metrics=installs-headline-metrics 01H8H9GQ17FJKWE3M2YSZFTQCS=installs-headline-metrics installs%E2%80%94charts=installs-charts 01H8H9GQ18VHMK7FFV3RY409VB=installs-charts identified-fraud-trend-chart=gr%C3%A1fico-de-tend%C3%AAncias-de-fraude-identificadas 01H8H9GQ18JDSZ2H8BKZVWGBPV=gr%C3%A1fico-de-tend%C3%AAncias-de-fraude-identificadas hijacked-installs-attribution-correction-chart=gr%C3%A1fico-de-corre%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-de-hijacking-de-instala%C3%A7%C3%B5es 01H8H9GQ18VXBPQRN55WHM3GG0=gr%C3%A1fico-de-corre%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-de-hijacking-de-instala%C3%A7%C3%B5es identified-fraud-chart=gr%C3%A1fico-de-fraude-identificada 01H8H9GQ18FW87TXQZCYERHNDE=gr%C3%A1fico-de-fraude-identificada affiliate-attribution-model=modelo-de-atribui%C3%A7%C3%A3o-de-afiliados h_01KQY7ARA2Z1WJ1V84X5GH832C=modelo-de-atribui%C3%A7%C3%A3o-de-afiliados installs%E2%80%94table=installs-table 01H8H9GQ18FYXJA7TXQ4RNQGX2=installs-table identified-fraud-breakdown=an%C3%A1lise-de-fraudes-identificadas 01H8H9GQ18540JJ8X833E6WF44=an%C3%A1lise-de-fraudes-identificadas content-of-the-identified-fraud-breakdown-table=conte%C3%BAdo-da-tabela-detalhada-de-fraudes-identificadas 01H8H9GQ18DMPD7YTPTN2XJMSH=conte%C3%BAdo-da-tabela-detalhada-de-fraudes-identificadas additional-table-options=op%C3%A7%C3%B5es-adicionais-de-tabela 01H8H9GQ18PZ8ABG3D51M7J91R=op%C3%A7%C3%B5es-adicionais-de-tabela inapp-events-dashboard=painel-de-eventos-in-app 01H8H9GQ19CQZV00XA62MGVJ86=painel-de-eventos-in-app inapp-events%E2%80%94headline-metrics=inapp-events-headline-metrics 01H8H9GQ19B95MDK2WEHVNEFS5=inapp-events-headline-metrics inapp-events%E2%80%94charts=inapp-events-charts 01H8H9GQ19XEJ0HNY2Y8BMX7A5=inapp-events-charts fraud-trend-over-time-chart=gr%C3%A1fico-de-tend%C3%AAncia-de-fraudes-ao-longo-do-tempo 01H8H9GQ1969AB4KK4ENP8AVQJ=gr%C3%A1fico-de-tend%C3%AAncia-de-fraudes-ao-longo-do-tempo top-iae-fraud-by-media-source-chart=gr%C3%A1fico-das-principais-fraudes-iae-por-canal-de-m%C3%ADdia 01H8H9GQ19Z078PK1HR7VEZHXG=gr%C3%A1fico-das-principais-fraudes-iae-por-canal-de-m%C3%ADdia inapp-events%E2%80%94table=inapp-events-table 01H8H9GQ19PTNWGJV6YDWR7SH6=inapp-events-table content-of-the-inapp-event-fraud-breakdown-table=conte%C3%BAdo-da-tabela-de-an%C3%A1lise-de-fraudes-de-eventos-in-app 01H8H9GQ19773CS8TGS2QXBRG5=conte%C3%BAdo-da-tabela-de-an%C3%A1lise-de-fraudes-de-eventos-in-app additional-table-options::44e54bfa=op%C3%A7%C3%B5es-adicionais-de-tabela-1 01H8H9GQ192WA6XFNW7CKGBQ03=op%C3%A7%C3%B5es-adicionais-de-tabela-1 01H8H9GQ1AVAVQ31ZZA1K024RF=payable-events 01H8H9GQ1BJX0K01NX8VCC0690=traits-and-limitations h_01HE7S2JKX3VMRCF6913S4MCAR=veja-tamb%C3%A9m" />

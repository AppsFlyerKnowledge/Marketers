---
title: Sobre dimensões excedidas e limites de cardinalidade
metadata:
  keywords:
    - performance reports
    - Advertisers
    - exceeded
    - reports
    - faq
    - Agencies
    - Exceeded_Events_Limit
    - Exceeded Events Limit
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
  created_at: '2017-10-08T15:20:55Z'
  edited_at: '2026-08-18T00:03:02Z'
  id: 115005099063
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/115005099063
---
> **Visão geral:** Por que algumas dimensões de dados agregados são exibidas como *Excedidas*e como evitar atingir os limites de cardinalidade.

## O que são dimensões excedidas?

A AppsFlyer coleta seus dados de instalação e eventos e os agrega. Os dados são agregados usando valores exclusivos que preenchem uma determinada dimensão. O número de valores exclusivos em uma dimensão é chamado de cardinalidade. A maioria das ferramentas de análise e relatórios agregados tem limites de cardinalidade por dimensão. Quando o número de valores exclusivos em uma dimensão excede o limite de cardinalidade, os dados restantes são agrupados em um grupo *Excedidos*. E quando o número de valores exclusivos na dimensão da fonte de mídia excede o limite de cardinalidade, os dados restantes do canal de mídia **bem como todas as dimensões com base nas fontes de mídia restantes** são agrupados nos grupos *Excedidos*.

Os exemplos a seguir ilustram a cardinalidade e como ela afeta seus relatórios.

> 📄 **Exemplo**
>
> **Exemplo A: Limite de cardinalidade do ID da campanha**
>
> O limite de cardinalidade da ID da campanha é 3000. Se o número de IDs de campanha informados em um determinado dia exceder 3000, todos os IDs de campanha restantes serão agrupados no Exceeded\_CampaignID\_Limit.
>
> **Exemplo B: Limite de cardinalidade de eventos**
>
> * Suponha que o limite de cardinalidade de Eventos é 3.
> * Em um determinado dia, 7 eventos únicos são relatados: A, B, C, D, E, F e G. Em outras palavras, a cardinalidade de eventos é 7.
> * Nos relatórios agregados, os eventos A, B, C são listados separadamente. Os eventos D, E, F e G são agrupados em Exceeded\_Events\_Limit.

As dimensões excedidas e os limites de cardinalidade afetam os dados agregados da seguinte maneira:

* Dahsboard de Visão Geral
* Exportação de dados agregados e relatórios da Pull API
* Relatórios da API mestre
* Dados de cliques e impressões nos painéis de atividades e personalizados
* Painel do Protect360

Os dados brutos não são afetados pelos limites de cardinalidade.

Se uma grande parte dos seus dados estiver agrupada em agrupamentos *Excedidos*, esses dados não são divididos. Isso pode levar a resultados imprecisos em relatórios de análise. Se necessário, use dados brutos para criar agrupamentos sem limites de cardinalidade.

A tabela a seguir lista os limites de cardinalidade por dia, por aplicativo.

<table><tbody><tr><th>Dimensão</th><th>Nome do grupo excedido</th><th>Tipo de limite por...</th><th>Limite de cardinalidade por dia </th><th>Cardinalidade para Protect360 por dia</th></tr><tr><td>Anúncio</td><td>Limite de anúncios excedido</td><td>Canal de mídia</td><td>1000</td><td>-</td></tr><tr><td>ID do anúncio</td><td>Limite de IDs de anúncio excedido</td><td>Canal de mídia</td><td>1000</td><td>-</td></tr><tr><td>Conjunto de anúncios</td><td>Limite de conjuntos de anúncios excedido</td><td>Canal de mídia</td><td>1000</td><td>-</td></tr><tr><td>ID do conjunto de anúncios</td><td>Limite de IDs de conjuntos de anúncios excedido</td><td>Canal de mídia</td><td>1000</td><td>-</td></tr><tr><td>Campanha</td><td>Exceeded_Campaign_Limit</td><td>Canal de mídia</td><td>3000</td><td><ul><li>Instalações/eventos in-app 3000</li><li>Impressões/cliques: 100 </li></ul></td></tr><tr><td>ID da campanha</td><td>Limite de IDs de campanha excedido</td><td>Canal de mídia</td><td>3000</td><td><ul><li>Instalações/eventos in-app 3000</li><li>Impressões/cliques: 100 </li></ul></td></tr><tr><td>Canal</td><td>Exceeded_Channels_Limit</td><td>Canal de mídia</td><td>20</td><td>20</td></tr><tr><td>ID do site</td><td>Limite de IDs de site excedido</td><td>Canal de mídia</td><td>1000\*\*</td><td><ul><li>Instalações/eventos in-app 1000</li></ul></td></tr><tr><td>Eventos</td><td>Exceeded_Events_Limit</td><td>Aplicativo </td><td>300</td><td>Instalações/eventos in-app 300</td></tr><tr><td>Palavras-chave</td><td>Limite de palavras-chave excedido</td><td>Canal de mídia</td><td>1000</td><td>-</td></tr><tr><td>Nomes dos canais de mídia\*</td><td>Limite da fonte de mídia excedido</td><td>Aplicativo</td><td>1000</td><td><ul><li>Instalações/eventos in-app 1000</li><li>Impressões/cliques: 100 </li></ul></td></tr><tr><td colspan="5"><p>E <span>quando o número de valores exclusivos na dimensão da fonte de mídia excede o limite de cardinalidade, os dados restantes do canal de mídia </span> <strong>bem como todas as dimensões com base nas fontes de mídia restantes</strong><span> são agrupados nos grupos </span><em>Excedidos</em><span>.</span></p><p><span>\*\* Consulte <a href="./measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">Exceeded_SiteID_Limit</a> para mais detalhes e limites.</span></p></td></tr></tbody></table>

## Limites de cardinalidade por dimensão

<div id="exceeded_adset_limit-and-exceeded_ad_limit" />

<Accordion title="Exceeded_AdSet_Limit e Exceeded_Ad_Limit">

* Estão disponíveis até 1000 nomes de conjuntos de anúncios exclusivos e 1000 nomes de anúncios exclusivos por canal de mídia.
  * Em um determinado dia, as informações do conjunto de anúncios do 1001º conjunto de anúncios e acima são agrupadas na fonte **Exceeded\_AdSet\_Limit** . O mesmo se aplica à fonte **Exceeded\_Ad\_Limit** .

> 👍 **Observação**
>
> "Divida e conquiste" novamente. Defina um pequeno número de nomes gerais de conjuntos de anúncios (de preferência até 50) e atribua todos os nomes de conjuntos de anúncios anteriores como anúncios únicos. Você também pode usar o **af\_sub** nos links de atribuição da AppsFlyer. Isso permite que você:
> 1. Impeça a visualiazação de **Exceeded\_AdSet\_Limit** ou **Exceeded\_Ad\_Limit.** 2. Otimize com eficiência de acordo com conjuntos de anúncios significativos e tráfego de anúncios.
> 3. Realize uma análise profunda com base no conjunto de anúncios e nos nomes dos anúncios nos dados brutos.

</Accordion>

<div id="exceeded_adsetid_limit-and-exceeded_adid_limit" />

<Accordion title="Exceeded_AdSetID_Limit e Exceeded_AdID_Limit">

* Estão disponíveis até 1000 IDs de conjuntos de anúncios exclusivos e 1000 IDs de anúncios exclusivos por fonte de mídia.
  * Em um determinado dia, as informações do ID do conjunto de anúncios do ID do 1001º conjunto de anúncios e acima são agrupadas na fonte **Exceeded\_AdSet\_Limit** . O mesmo se aplica à fonte **Exceeded\_AdID\_Limit** .

</Accordion>

<div id="exceeded_campaign_limit" />

<Accordion title="Exceeded_Campaign_Limit">

**[![](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)**

* Até 3000 nomes de campanha exclusivos por dia estão disponíveis.
  * Em um dia, as informações da campanha 3001ª e acima são agrupadas na fonte **Exceeded\_Campaign\_Limit** .

> 👍 **Observação**
>
> Defina um pequeno número de nomes gerais de campanhas (de preferência até 300) e atribua todos os nomes de campanhas anteriores como conjuntos de anúncios. Nos links de atribuição da AppsFlyer, o parâmetro é **af\_adset**. Isso permite que você:
> 1. Impeça a visualização de **Exceeded\_Campaign\_Limit**.
> 2. Otimize com eficiência de acordo com conjuntos de tráfego de conjuntos de anúncios significativos.
> 3. Realize uma análise profunda com base nos nomes das campanhas e conjunto de dados nos dados brutos.

</Accordion>

<div id="exceeded_campaignid_limit" />

<Accordion title="Limite de IDs de campanha excedido">

* Até 3000 IDs de campanha exclusivos por dia estão disponíveis.
  * Durante um único dia, todas as informações da campanha do ID da campanha 3001 e superior são atribuídas à fonte **Exceeded\_CampaignID\_Limit** .

</Accordion>

<div id="exceeded_channels_limit" />

<Accordion title="Exceeded_Channels_Limit">

* Estão disponíveis até 20 nomes de canais exclusivos por dia por canal de mídia. Para o Protect360, o limite é 1000.
  * Em um dia, todas as informações do canal do 21º canal e acima são atribuídas à fonte **Exceeded\_Channel\_Limit** .

</Accordion>

<div id="exceeded_events_limit" />

<Accordion title="Exceeded_Events_Limit">

* Até 300 nomes de eventos exclusivos por dia estão disponíveis.
  * Em um dia, todas as informações do evento do 301º evento e acima são atribuídas ao nome do evento chamado **Exceeded\_Events\_Limit**.

> 👍 **Observação**
>
> Para parar de ver **Exceeded\_Events\_Limit**, considere usar:
>
> * <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">Eventos avançados in-app</Anchor>. Em vez de reportar centenas de eventos diferentes, defina um pequeno número de nomes gerais de eventos (de preferência até 20). Use valores de eventos dinâmicos para diferenciar esses eventos. Isso permite otimizar de acordo com os parâmetros de valor e executar análises com base nos valores do evento, que estão disponíveis por meio do <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Relatório de dados brutos de eventos in-app.</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud">Regras de validação</Anchor> para remover eventos in-app desnecessários da plataforma da AppsFlyer.

> 📄 **Exemplo**
>
> Seu aplicativo com.greatapp envia um evento de compra no aplicativo para cada cor de meias que vende, por exemplo, buy\_red\_socks, buy\_blue\_socks, buy\_white\_socks, etc. Para evitar essa inflação de eventos diferentes, restrinja-os a um único evento, buy\_socks, e insira a cor como um <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">parâmetro de evento</Anchor>. Para evitar essa inflação de eventos diferentes, restrinja-os a um único evento, buy\_socks, e insira a cor como um <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">parâmetro de evento</Anchor>.

</Accordion>

<div id="exceeded_keywords_limit" />

<Accordion title="Limite de palavras-chave excedido">

* Até 1000 palavras-chave exclusivas por dia por canal de mídia de mídia estão disponíveis.
  * Em um dia, as informações da palavra-chave 1001 e acima é agrupada na fonte **Exceeded\_Keywords\_Limit**.

</Accordion>

<div id="exceeded_mediasource_limit" />

<Accordion title="Limite da fonte de mídia excedido">

* Até 1000 nomes de canal de mídia por dia estão disponíveis.
  * Em um dia, as informações da campanha do nome da fonte de mídia 1001 e acima são agrupadas na fonte **Exceeded\_MediasSource\_Limit**.

</Accordion>

<div id="exceeded_siteid_limit" />

<Accordion title="Limite de IDs de site excedido">

O ID do site (por cliques, impressões, instalações e eventos in-app) tem 2 limites: 1.000 e 5.000.

* Até 1000 IDs de site exclusivos por dia por mídia estão disponíveis.
  * Em um dia, as informações de ID do site do ID do site 1001 e acima por canal de mídia são agrupadas em um ID de site exclusivo chamado **Exceeded\_SiteID\_Limit.** Portanto, se você vir o ID do site **Exceeded\_SiteID\_Limit**, isso significa que há muitos IDs de site usados de acordo com o canal de mídia em questão, e tentar otimizar o tráfego da fonte de acordo com os IDs do site se torna menos preciso e menos eficaz.
* A partir de 19 de agosto de 2024, se houver mais de 5.000 IDs de site por dia por canal de mídia, apenas 10 IDs de site serão exibidos. Todos os outros IDs de site são agrupados em um único ID de site chamado **Exceeded\_SiteID\_Limit**.

> 👍 **Observação**
>
> "Divida e conquiste". Em vez de usar milhares de IDs de site por canal de mídia, o que distorce seus dados agregados, use um segundo parâmetro em seus links de atribuição chamado **af\_sub\_siteid.** Defina um pequeno número de IDs de site gerais (de preferência até 50) e atribua todas os IDs de site anteriores como IDs de subsite nesses IDs de site gerais. Isso permite que você:
> 1. Impeça a visualização de **Exceeded\_SiteID\_Limit**2. Otimize com eficiência de acordo com o tráfego de IDs de sites significativos
> 3. Realize uma análise profunda com base nos IDs de site e IDs de sub-site nos dados brutos

> 📘 **Observação**
>
> No Relatório de retenção, você não vê um Exceeded\_SiteID\_Limit mas nem todos os IDs de site são mostrados. As IDs de site são mostradas aleatoriamente, mas é uma limitação da interface do usuário mostrar tudo (quando elas excederam o limite). Para contornar esse problema, recupere os dados de retenção da API mestre.

</Accordion>

## Como evitar fontes excedidas?

### A solução a longo prazo

A maioria dos anunciantes não encontrará fontes de **Excedido**, pois normalmente não definem 3000 campanhas manualmente.

Se você encontrar fontes de **Excedido** provavelmente é porque uma ou mais fontes de mídia estão usando valores dinâmicos para nomes de campanhas, IDs de sites, conjuntos de anúncios ou anúncios. Eventos dinâmicos in-app dentro do código do aplicativo podem fazer com que a fonte de dados **Exceeded\_Events\_Limit** apareça.

> 👍 **Observação**
>
> Use apenas valores estáticos para nomes de eventos in-app, campanhas, IDs de sites, conjuntos de anúncios e anúncios para evitar receber fontes de **Excedido**.
>
> Além disso, verifique dicas específicas para qualquer fonte de **Excedido** acima.

### A solução de curto prazo

A solução de longo prazo pode levar de alguns dias a algumas semanas para ser totalmente implementada.

Mas e se você quiser ver seus dados agora?

Conforme explicado, uma fonte de **Excedido** ocorre quando a AppsFlyer recebe a origem de N+1 clique (ou evento) durante um único dia. É possível que os canais de mídia mais proeminentes que você usa cheguem no final do dia e, portanto, sejam combinados com os dados de uma fonte de **Excedido**. Aqui está um truque simples para minimizar o efeito de qualquer fonte de **Excedido** que você vir:

> 👍 **Observação**
>
> Esqueça o hoje e olhe apenas para os dados de ontem e de antemão. Todos os dias, um processo de agregação recalcula os dados do último dia e, em retrospecto, atribui apenas as fontes menores (não as mais atrasadas) a qualquer fonte de **Excedido**. Isso garante que a distorção causada pelo excesso de cliques seja mínima!

<div data-zendesk-anchors="what-are-exceeded-dimensions=o-que-s%C3%A3o-dimens%C3%B5es-excedidas h_01J1VY82KFVMRW99RK0SXWSEZ4=o-que-s%C3%A3o-dimens%C3%B5es-excedidas h_01J1VY82KFXYA0XCA1XFVTJ2DZ=exemplo cardinality-limits-per-dimension=limites-de-cardinalidade-por-dimens%C3%A3o h_01J1VY82KF5WP6PJQ1MKYPP7YY=limites-de-cardinalidade-por-dimens%C3%A3o h_01J1VY82KF9XQ08EQ2BH89B6QK=exceeded_adset_limit-and-exceeded_ad_limit h_01J1VY82KFM4VAD4FG5CEKTQK6=observa%C3%A7%C3%A3o h_01J1VY82KFWMF6DN3XNFSWBFHH=exceeded_adsetid_limit-and-exceeded_adid_limit h_01J1VY82KFF7AWBCB54KRPJNS4=exceeded_campaign_limit h_01J1VY82KFBPK2PAHSSMCER6TW=observa%C3%A7%C3%A3o-1 h_01J1VY82KF4TFVTGQ31RCE3QK7=exceeded_campaignid_limit h_01J1VY82KFXPX63XKKKTZ9AWN1=exceeded_channels_limit h_01J1VY82KFRDRVNEAG6S72Q1T4=exceeded_events_limit h_01J1VY82KFYXAXTJ613VAN1PXX=observa%C3%A7%C3%A3o-2 h_01J1VY82KF48N1M8DZ89XQBJTD=exemplo-1 h_01J1VY82KFAFK03F3SDJBA5ZNX=exceeded_keywords_limit h_01J1VY82KFV85460FCZB77EY1A=exceeded_mediasource_limit h_01J1VY82KFQG2ZGF91F80X2AAK=exceeded_siteid_limit h_01J1VY82KFMD2DJWDYXF8528CY=observa%C3%A7%C3%A3o-3 h_01J1VY82KFQRVCAW82ZSNJ96G7=observa%C3%A7%C3%A3o-4 how-to-avoid-getting-exceeded-sources=como-evitar-fontes-excedidas h_01J1VY82KFE9E2DNRNPBRQSW22=como-evitar-fontes-excedidas the-long-term-solution=a-solu%C3%A7%C3%A3o-a-longo-prazo h_01J1VY82KFDBASKPRK2GJ16FDZ=a-solu%C3%A7%C3%A3o-a-longo-prazo h_01J1VY82KFSWQ2Y4WSSASYDFWR=observa%C3%A7%C3%A3o-5 the-short-term-solution=a-solu%C3%A7%C3%A3o-de-curto-prazo h_01J1VY82KFR7Z8422MYFK71ET8=a-solu%C3%A7%C3%A3o-de-curto-prazo h_01J1VY82KF83SADWJCESRNSJCJ=observa%C3%A7%C3%A3o-6" />

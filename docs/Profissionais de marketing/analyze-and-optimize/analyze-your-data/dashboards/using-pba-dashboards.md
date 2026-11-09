---
title: Usando dashboards PBA
metadata:
  keywords:
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-04-21T04:53:54Z'
  edited_at: '2026-08-19T00:04:16Z'
  id: 360007630318
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/360007630318
---
> **Em resumo:** Aproveite ao máximo os recursos dos nossos dashboards PBA.

<Image align="center" alt="Atribuição baseada em pessoas da AppsFlyer" src="https://files.readme.io/d2178dfedb2f67420e66626adbd72dd96ba9edc39fcb0be08648b01656fd2d4b-360010094118.png" />

<div id="pba-dashboards" />

## Os painéis de PBA

As seções a seguir se referem aos dashboards de <Anchor target="_blank" href="/marketers/pt/docs/pba-website-attribution-dashboard">Atribuição de website</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/pba-web-assisted-installs">instalações assistidas pela web</Anchor> dashboards.

<div id="settings" />

## Configurações

<div id="filtering-options" />

<Accordion title="Opções de filtro">

Refine os resultados do dashboard PBA usando o seletor de datas (A), os filtros principais (B) e os filtros adicionais (C) para adaptar a análise às suas necessidades.

<div id="filter-panel-in-pba-dashboards" />

#### Painel de filtros nos dashboards PBA

<Image align="center" alt="Cabeçalho do PBA" src="https://files.readme.io/aaa4040b69082c8507c604b530086404080d542b614fd20fcb0d5302221d7586-360019762657.png" />

**Legenda**:

(1) Seletor de datas

(2) Filtros padrão

(3) Filtros adicionais: clique em + para selecionar um filtro adicional.

**Princípios**

* O design do painel de filtros é comum a todos os dashboards PBA.
* Os filtros disponíveis em cada dashboard diferem, conforme indicado na tabela a seguir.
* Filtros com contexto: alguns filtros, conforme indicado na tabela, exigem associação com um contexto. Por exemplo, no dashboard de instalações assistidas pela web, o filtro de geolocalização exige um contexto que pode ser o canal de mídia da web ou o canal de mídia mobile. Você pode definir um filtro de geolocalização para cada um deles configurando dois filtros de geolocalização, um para cada contexto.

<div id="available-filter-dimensions-per-dashboard" />

#### Dimensões de filtro disponíveis por dashboard

<table><tbody><tr><th>Filtro</th><th>Descrição/valores</th><th>Atribuição do site </th><th>Instalações Auxiliadas pela Web</th><th>Caminhos de<br/>conversão</th></tr><tr><td>Seletor de datas</td><td><p>A data em que ocorreu um dos seguintes eventos de conversão do PBA: </p><ul><li>Instalação de aplicativos</li><li>Conversão da web</li><li>Conversão mobile</li></ul></td><td><p>S</p></td><td><p>S</p></td><td><p>S</p></td></tr><tr><td>Geografia </td><td><p>Lista de países/territórios </p></td><td>S</td><td><span>S (1)</span></td><td><p><span>S (2)</span></p></td></tr><tr><td>Tipo de instalação</td><td>Orgânico, banner inteligente, link personalizado, pago</td><td>--</td><td><span>S</span></td><td><span>--</span></td></tr><tr><td>Canal de mídia</td><td>Anúncio, direto, e-mail, referência, pesquisa orgânica, social</td><td>S</td><td><span>S</span></td><td><span>S (2)</span></td></tr><tr><td>Mobile platform</td><td>Android, iOS</td><td>--</td><td><span>S</span></td><td><span>--</span></td></tr><tr><td>Canal de mídia </td><td><p>Canal de mídia ao qual o evento é atribuído<span></span></p></td><td><p>S</p></td><td><span>S(1)</span></td><td><span> <font>S (2)</font> </span></td></tr><tr><td><p>Tipo de mídia</p></td><td><p>Inclui pago, <a href="./owned-media-attribution" target="_blank">próprio</a>, ganho</p></td><td><p>S</p></td><td>S</td><td>S (2)</td></tr><tr><td><p>Eventos de conversão</p></td><td><p>Mostra caminhos que levam ao evento de conversão para o caminho de conversão</p></td><td><p>S</p></td><td><p>--</p></td><td><p><span>S</span></p></td></tr><tr><td><p>Duração do caminho (etapas) </p></td><td><p>Número de etapas na visualização atual do caminho de conversão: canal de mídia, canal, tipo de mídia</p></td><td><p>--</p></td><td><p>--</p></td><td><p>S</p></td></tr><tr><td><p>Duração do caminho (dias)</p></td><td>Duração da conversão a partir do primeiro touchpoint</td><td>--</td><td>--</td><td>S</td></tr><tr><td colspan="5"><p><strong>(1)</strong> No dashboard de instalações assistidas pela web, você associa o filtro ao canal de mídia da web ou ao canal de mídia mobile. Você pode definir várias instâncias do filtro. Caso de exemplo</p></td></tr></tbody></table>

</Accordion>

<div id="grouping-options" />

<Accordion title="Opções de agrupamento">

As opções de Agrupar por estão disponíveis nos dashboards **Instalações assistidas pela web** e **Atribuição do site**.

Os dados do dashboard são agrupados por, por exemplo, canal de mídia, dispositivo ou país. Quando um grupo é selecionado, uma coluna de dados é adicionada à tabela de resultados. A ordem em que os grupos são escolhidos afeta como os dados são exibidos.

* Grupo padrão: **Canal de mídia/Campanha**
* No menu suspenso, selecione 1 ou mais opções.

<div id="example" />

> 📄 **Exemplo**
>
> **Cenário:** A mesma campanha de segmentação é veiculada tanto na Net\_A quanto na Net\_B.
>
> **Objetivo:** Ver qual canal de mídia tem mais sucesso.
>
> **Como?** Agrupe por *canal de mídia* e, em seguida, analise uma campanha direcionada ao mesmo público-alvo.

| Grupo | A descrição | Instalações Auxiliadas pela Web | Atribuição do site |
| --- | --- | --- | --- |
| Tipo do dispositivo | Inclui smartphone, tablet, desktop, TV e outros (dispositivos não reconhecidos) | S | S |
| Ambiente | <ul><li>Use para diferenciar KPIs da web e do mobile</li><li>Dashboard de Atribuição do site: combina sistema operacional e plataforma. Por exemplo, Android/web, iOS/web, Windows/web, Linux/web</li><li>Instalações assistidas pela web: iOS, Android, Windows</li></ul> | S | Não |
| Geografia | <ul><li>Veja tendências de tráfego e engajamento por país</li><li>Os resultados podem ter impacto direto nas decisões de investimento por país</li></ul> | S | S |
| Fonte de mídia / campanha | **Canal de mídia**<br /><br />Canal de mídia atribuído a uma conversão<ul><li>Para visualizar dados detalhados da campanha, clique na hierarquia da campanha: campanha > conjunto de anúncios > anúncio</li><li>Os níveis de hierarquia disponíveis variam entre os diferentes canais de mídia</li></ul>**Nomes de campanha**<ul><li>Nomes de campanhas disponíveis com base nos parâmetros da URL.</li><li>Os nomes de campanhas não estão disponíveis em todos os casos.</li></ul> | S | S |
| Canal de mídia | Anúncio, direto, e-mail, referência, pesquisa orgânica, social | Não | S |
| Tipo de mídia | Inclui mídia paga, <Anchor target="_blank" href="/marketers/pt/docs/owned-media-attribution">própria</Anchor> e conquistada | Não | S |
| Platform |  | Não | S |

</Accordion>

<div id="other-settings" />

<Accordion title="Outras configurações">

| Configuração | A descrição |
| --- | --- |
| Agrupamento da marca (EN: Brand bundle) | Os dashboards do PBA têm dados no nível do agrupamento de marca. Os agrupamentos consistem em um site, 1 aplicativo Android e 1 aplicativo iOS.<ul><li>Você pode selecionar agrupamentos se suas <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings#perguntas-frequentes">permissões</Anchor> permitirem visualizar/editar os aplicativos que formam o agrupamento.</li><li>Use o seletor para alternar entre os agrupamentos.</li><li><Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings">Criar e editar agrupamentos.</Anchor></li></ul> |
| Configurações de PBA | <ul><li>Definir eventos de conversão</li><li>Alterar configurações do agrupamento</li></ul> |

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="traits-and-limitations" />

<Accordion title="Especificações e limitações">

Os dashboards e relatórios do PBA são atualizados <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#eod">diariamente</Anchor> de acordo com o fuso horário UTC.

* O processamento diário inclui eventos recebidos durante o dia anterior.
* Finalização dos dados:
  * No caso de instalações assistidas pela web, a atribuição de site do PBA identifica eventos relacionados adicionais durante os primeiros 7 dias após a conversão. Isso pode alterar o canal de mídia identificado como o responsável final por impulsionar a conversão.
  * Nos relatórios de dados brutos relacionados, o campo *final\_data* é false durante o período inicial de 7 dias.

Os dashboards do PBA não oferecem suporte a moeda local e os dados serão exibidos em USD.

</Accordion>

<div data-zendesk-anchors="pba-dashboards=os-pain%C3%A9is-de-pba h_01HNJGN4BYRH14QXS4SWQAHR8D=os-pain%C3%A9is-de-pba settings=configura%C3%A7%C3%B5es h_01HNJGN4BYF8NFYYWHG30RHEJH=configura%C3%A7%C3%B5es h_01HNJGN4BYSHM9PFYQQ86ZR84X=filtering-options filter-panel-in-pba-dashboards=painel-de-filtros-nos-dashboards-pba h_01HNJGN4BYVYY2MKK5G3RCS07W=painel-de-filtros-nos-dashboards-pba filters-and-date-picker=dimens%C3%B5es-de-filtro-dispon%C3%ADveis-por-dashboard h_01HNJGN4BZ2KZAK120ZGT3B23W=dimens%C3%B5es-de-filtro-dispon%C3%ADveis-por-dashboard h_01HNJGN4BZV94W8W2GBXCZF563=grouping-options 01EDDQYQ8RWQZZTEZY9AVT1M64=exemplo 01EDDQYQ8R5JPZE30ETV70FJVN=other-settings additional-information=informa%C3%A7%C3%B5es-adicionais h_01HNJGN4BZ9BMV7BQRQCKGYSSP=informa%C3%A7%C3%B5es-adicionais h_01HNJGN4BZFMG73SPZ1J4Z7TT5=traits-and-limitations" />

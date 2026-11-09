---
title: Painel de visão geral da SKAdNetwork (SKAN) por AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-07-25T21:27:38Z'
  edited_at: '2026-10-20T03:36:14Z'
  id: 360011307357
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/360011307357
---
> **Visão geral:** o dashboard da SKAdNetwork (SKAN) exibe métricas de campanha relatadas por meio de postbacks da SKAN e pontos de dados adicionais durante as janelas iniciais de mensuração do usuário. Métricas modeladas que consideram conversões nulas também estão disponíveis. Exibição de dados usando a data de instalação ou de chegada do postback.

<Image align="center" alt="SKAdHeadling8_us-en.png" src="https://files.readme.io/72c2eb452741cbd77c5828197f827f238c71c5097b8703528fa180dcafe2364c-360011831017.png" />

<div id="dashboard-principles" />

## Princípios do painel

O painel contém dados de desempenho da campanha SKAN e adere aos seguintes princípios:

* Considere que a Apple, devido a um <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork">mecanismo de limite de privacidade</Anchor>, nem sempre preenche o valor de conversão (CV). Estes são chamados de CVs nulos. No caso de CVs nulos, apenas uma instalação é registrada.
* As métricas são calculadas da seguinte forma:
  * Métricas não orgânicas no painel são calculadas usando os dados postback de SKAN recebidos pela AppsFlyer. Algumas métricas, como redownloads, ID do aplicativo de origem e métricas do tipo fidelidade, exigem que você configure seu aplicativo para <Anchor target="_blank" href="/marketers/pt/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">enviar cópias de postback diretamente para a AppsFlyer</Anchor>.
  * As métricas orgânicas são calculadas como dados de atribuição da AppsFlyer menos os dados de atribuição não orgânica da SKAN. **Observação**: as métricas orgânicas nem sempre estão disponíveis. [Saiba mais](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations).
    * Certifique-se de filtrar por **Novas instalações** no campo tipo de instalação.
  * Algumas métricas, como receita e ROAS, têm tanto o valor original derivado de postbacks quanto um [valor modelado](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) que considera a taxa CV nula.
* O tráfego conduzido pela agência é tratado como vindo de uma agência transparente.
* Atualização dos dados:
  * Diariamente.
  * Postbacks recebidos em um determinado dia são processados no final do dia UTC. Os dados ficam disponíveis até às 08:00 UTC do dia seguinte. Significa que os postbacks recebidos na segunda-feira estão disponíveis no painel na manhã de terça-feira.
  * Ver <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">tempo esperado de atualização do painel.</Anchor>

<div id="skan-dashboard-view-options" />

## Opções de visualização do painel do SKAN

Mostrar dados usando a data de instalação [ou a data de chegada do postback](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#filter-options).

**Para selecionar uma opção de exibição de data**, na AppsFlyer, vá para **Painel** > **Visão geral do SKAN.** Na barra do filtro, selecione uma opção de data em **Exibir por**.

Filtros adicionais e opções de exibição são descritos nas seções a seguir.

<div id="dashboard-use" />

## Uso do painel

<div id="dashboard-settings" />

<Accordion title="Configurações do dashboard">

As configurações do painel estão disponíveis quando seu aplicativo usa o <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#fixed-modes">modo fixo da métrica de conversão</Anchor> legado para selecionar o evento de conversão.

**Para selecionar o evento de conversão**:

1. No lado superior direito do painel, clique em **Configurações do painel**.
2. Selecionar evento de conversão
3. Clique em Aplicar.  
   As métricas de conversão são calculadas utilizando este evento.  
   Atenção! Este ajuste está relacionado à exibição no painel e não afeta o ajuste do CV no aplicativo.

</Accordion>

<div id="filter-options" />

<Accordion title="Opções de filtro">

Use filtros para refinar as informações exibidas.

| **Filtro** | **Observações** |
| --- | --- |
| Exibir por | <ul><li>**Data de instalação**: é derivada da hora de chegada do postback da seguinte forma:<ul><li>Se os postbacks do SKAN forem SKAN V4, a fórmula da data de instalação será: Data de instalação = hora de chegada do postback - [tamanho da janela acumulada] - [atraso médio do postback].<ul><li>Postback 1: data de instalação = hora de chegada do postback - 48h - 36h</li><li>Postback 2: data de instalação = hora de chegada do postback - 168h - 84h</li><li>Postback 3: data de instalação = hora de chegada do postback - 840h - 84h</li></ul></li><li>Se os postbacks do SKAN forem SKAN V3 ou anterior, a fórmula da data de instalação será: Data de instalação = horário de chegada do postback - 36 horas - [intervalo médio do último ativo].<ul><li>O padrão [faixa média da última atividade] é de 12 horas.</li><li>Para um valor de conversão de 0, o último intervalo ativo médio é definido como 0.</li></ul></li></ul></li><li>**Data de chegada do postback**:<ul><li>A data no campo ad\_network\_timestamp dos Relatórios de dados brutos do SKAN. O timestamp depende da ad network:<ul><li>Google Ads: o timestamp estimado do clique.</li><li>Meta Ads: o timestamp retornado pela API da Meta.</li><li>Todas as outras ad networks: o timestamp de quando a ad network recebeu o postback do SKAN da Apple.</li></ul></li><li>Quando você compara as métricas no painel SKAN da AppsFlyer com as fornecidas pelas ad networks, considere que as ad networks normalmente disponibilizam os dados utilizando a data de chegada do postback.</li><li>As métricas orgânicas não estão disponíveis ao selecionar esta opção.</li><li>No caso do Google Ads, as datas de chegada e instalação não diferem.</li></ul></li></ul> |
| Date range | <ul><li>A data de instalação atribuída. Esta data é derivada utilizando a hora de chegada do postback.</li><li>Se houver um grande número de instalações, a imprecisão devido a questões de tempo é insignificante.</li><li>As instalações incluem redownloads.</li><li>O intervalo de datas é limitado a 90 dias.</li></ul> |
| Canal de mídia | <ul><li>A ad network atribuída com a instalação</li><li>Tráfego dirigido pela agência: a fonte real da mídia exibe independentemente do status de transparência da agência. Consequentemente, você pode ver fontes de mídia com as quais não está familiarizado.</li></ul> |
| Campanha | <ul><li>Nome e identificação da campanha, conforme definido pela ad network.</li><li>A AppsFlyer traduz a identificação da campanha pós-campanha para a da ad network.</li><li>Se um determinado ID de campanha tem vários nomes de campanha associados a ele, então todos os nomes são exibidos no painel. Atenção! A ad network fornece a identificação da campanha e o nome por postback. Tanto o ID quanto o nome da campanha estão disponíveis nos relatórios SKAN de dados brutos e agregados.</li></ul> |
| ID do site | <ul><li>Aplicativo de origem exibindo seu anúncio.</li><li>Use para analisar os aplicativos mais benéficos para você.</li></ul> |
| Geografia | <ul><li>Território ou país</li><li>A geolocalização é derivada usando dados fornecidos pela ad network ou usando o endereço IP do dispositivo.</li><li>A partir do iOS 14.6 o endereço IP do dispositivo é mascarado por um servidor proxy da Apple. Isso significa que a geolocalização do servidor Apple é refletida e não o dispositivo em si.</li></ul> |
| Tipo de instalação | <ul><li>Instalações</li><li>Redownloads relatados pela loja de aplicativos</li></ul> |
| Conjunto de anúncios | Disponível se a ad network fornecer este ponto de dados |
| Anúncio | Disponível se a ad network fornecer este ponto de dados |
| Versão | A versão do SKAN |

</Accordion>

<div id="headline-metrics" />

<Accordion title="Principais métricas">

| Métrica | Observações |
| --- | --- |
| Instalações | O SKU não relatará instalações se o usuário não tiver se engajado com um anúncio antes da instalação. A AppsFlyer calcula a métrica orgânica usando as instalações atribuídas à AppsFlyer (painel de LTV).<ul><li>Não orgânico: instalações atribuídas a uma fonte de mídia no contexto de uma campanha app-to-app paga e relatada por SKAN.</li><li>Orgânico calculado pela AppsFlyer inclui o seguinte:<ul><li>Instalações não atribuídas pelo SKAN ou para as quais nenhum postback foi recebido de uma ad network.</li><li>App clips</li></ul></li></ul>Apple Ads (media-source iossearchads\_int) agora aparece no tráfego SKAN não orgânico. |
| Pontos de contato | As ad networks relatam impressões e cliques por clique ou API. |
| Receita total | <ul><li>Disponível quando o modo de receita está ativo.</li><li>Exibe em USD ou na moeda local específica do aplicativo, conforme definido na <Anchor target="_blank" href="/marketers/pt/docs/app-settings">página de configurações do aplicativo</Anchor>.</li><li>Dividido entre receitas orgânicas e não orgânicas.</li><li>A receita orgânica é calculada como a receita de todas as fontes menos a receita não orgânica.</li><li>Para permitir uma comparação semelhante, a duração da janela de postback de instalações orgânicas e não orgânicas é a mesma.</li><li>Inclui <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#null-conversion-values">dados modelados</Anchor></li></ul>**Observação**: as métricas orgânicas nem sempre estão disponíveis. [Saiba mais](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). |
| Custo | <ul><li>Custo informado pela ad network. Os dados de custo são relatados à AppsFlyer usando ROI360/API de custo. O custo é exibido em USD ou na moeda local específica do aplicativo, conforme definido na <Anchor target="_blank" href="/marketers/pt/docs/app-settings">página de configurações do aplicativo</Anchor>.</li><li>Se o nome da campanha mudar, os custos serão exibidos sob o nome da campanha mais recente utilizada. (Se houver vários nomes de campanha)</li><li>As métricas de custo estão disponíveis apenas para o filtro Install type=All que inclui tanto instalações quanto redownloads.</li></ul> |
| Taxa de click-to-install | Taxa de click-to-install |
| Tendência para o período adjacente | Os valores de tendência em % indicam a mudança da métrica atual em relação à métrica do período equivalente anterior. Por exemplo, se o período atual é de 1 a 10 de maio, o período anterior é de 21 a 30 de abril. |

</Accordion>

<div id="charts" />

<Accordion title="Gráficos">

Os gráficos disponíveis dependem do tipo de métrica selecionado.

<Table>
  <thead>
    <tr>
      <th>
        Métrica do gráfico
      </th>
      <th>
        Observações
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Tendência de Aquisição de Usuários
      </td>
      <td>
        Dimensões disponíveis:

        * Orgânica
        * Não orgânica

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer2_us-en.png" src="https://files.readme.io/5c46dc05b4df07f3f60ff6015f115b4bc89106a6eb594f43d777af2100fdf460-360010368477.png" width="201px" />](https://support.appsflyer.com/hc/article_attachments/49929170406161)
      </td>
    </tr>
    <tr>
      <td>
        Toque para conversão
      </td>
      <td>
        Visualizações disponíveis:

        * Dimensões do ponto de contato:
          * Impressões
          * Cliques
        * Taxa de click-to-install

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer3_us-en.png" src="https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png" width="223px" />](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png)
      </td>
    </tr>
    <tr>
      <td>
        Instalações por dia agrupadas por elemento de hierarquia de publicidade
      </td>
      <td>
        Elementos disponíveis: Fonte de mídia, Campanha, ID do site, Conjunto de anúncios, Anúncio [<Image alt="SKAdNetwork_Dashboard_AppsFlyer4_us-en.png" src="https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png" width="206px" />](https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png)
      </td>
    </tr>
    <tr>
      <td>
        Detalhamento da métrica por elementos da hierarquia de publicidade
      </td>
      <td>
        Elementos disponíveis: Fonte de mídia, Campanha, ID do site, Conjunto de anúncios, Anúncio

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer5_us-en.png" src="https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png" width="198px" />](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png)
      </td>
    </tr>
    <tr>
      <td>
        Top eventos
      </td>
      <td>
        Os principais eventos contêm tanto usuários orgânicos quanto não-orgânicos. Use o filtro da fonte de mídia, no topo da página, para distinguir entre usuários orgânicos e não orgânicos ou por fontes de mídia selecionadas.

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer6_us-en.png" src="https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png" width="245px" />](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png)
      </td>
    </tr>
    <tr>
      <td>
        Principais países
      </td>
      <td>
        [<Image alt="mceclip1.png" src="https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png" width="181px" />](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)

        Observação: este quadro está disponível para as agências e não para os anunciantes.
      </td>
    </tr>
    <tr>
      <td>
        Cópia do postback
      </td>
      <td>
        Este gráfico está disponível depois que você configurar o aplicativo para enviar <Anchor target="_blank" href="/marketers/pt/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">cópias do postback</Anchor> do iOS 15+ para a AppsFlyer. Se nenhum gráfico for exibido, considere isso:

        * Não estamos recebendo os postbacks do aplicativo ou ainda não os recebemos. Verifique com seu desenvolvedor de aplicativos se o endpoint AppsFlyer foi definido no aplicativo e se a versão atualizada do aplicativo está na App Store.
        * Os postbacks não foram recebidos (o que significa que não há instalações na SKAN) para a data selecionada ou você selecionou uma data anterior a 1 de janeiro de 2022.

        Observações:

        * Todas as outras métricas no painel são calculadas usando postbacks iOS encaminhados por ad networks para a AppsFlyer ou a partir de dados fornecidos diretamente por SRNs. Esperar discrepâncias entre as métricas de cópia postback e as outras métricas.
        * O quadro de cópias de postback não está disponível para as agências.

        [<Image alt="PostbackCopy.png" src="https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png" width="207px" />](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png)

        | Dimensão | Observações |
        | --- | --- |
        | Canal de mídia | A fonte de mídia atribuída à instalação. <br /><br />* Métricas:<br />  * **Taxa de redownload:** as métricas se referem a postbacks usando SKAdNetwork V2.0+.<br />  * **Taxa atribuída por tipo de toque:** engajamento, visualização ou clique, que leva à instalação. As métricas se referem a postbacks usando SKAdNetwork V2.2+<br />* Observação: se a identificação da fonte de mídia for exibida, não temos atualmente um nome associado a essa identificação. Peça à fonte de mídia para atualizar seu ID do SKAdNetwork na AppsFlyer. |
        | Aplicativo de origem | O nome do editor do anúncio, ou seja, o nome do aplicativo em que o usuário se engajou com seu anúncio.<br /><br />* Métrica:<br />  * **Contagem de instalação**: o número de instalações trazidas pelo aplicativo do editor.<br />* Observações:<br />  * Se a Apple retiver a ID do aplicativo de origem, devido aos limites de privacidade, o aplicativo de origem será exibido como *desconhecido*.<br />  * Se o nome do aplicativo não puder ser encontrado, a ID do aplicativo aparece. |
        | ID do aplicativo de origem | O ID do editor do anúncio, ou seja, o ID do aplicativo no qual o usuário se engajou com seu anúncio.<br /><br />* Métrica:<br />  * **Contagem de instalações**: o número de instalações trazido pela ID do aplicativo da editora. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="metrics" />

<Accordion title="Métricas">

* Selecione as métricas dentre as disponíveis. [Métricas modeladas](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) considera a taxa de CV nulo.
* Definir os grupos primários e secundários por dimensões para detalhar em métricas de desempenho.

<Image align="center" alt="SKAdNetwork_Dashboard_AppsFlyer7_us-en.png" src="https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png" />

Sobre a tabela de métricas:

* Use a tabela para comparar o desempenho das campanhas e das fontes de mídia.
* Inicialmente, as 20 principais fontes de mídia são exibidas, ordenadas pelo número de instalações em ordem decrescente.
* Para ordenar a tabela, clique no cabeçalho de uma coluna. Clique novamente para reverter a ordem de classificação.
* As métricas de custo (custo, impressões e cliques) estão disponíveis se pelo menos 1 instalação estiver associada a uma determinada campanha. Observação:
  * Campanhas com 0 instalações não são exibidas de forma alguma.
  * Algumas ad networks relatam as métricas de custo relacionadas ao conjunto de anúncios e ao nível do anúncio, mas relatam a instalação no nível da campanha. Neste caso, o conjunto de anúncios e a métrica de custos são exibidos com uma métrica de instalação de 0.
* Atribuição de limitação de dimensão por toque: as métricas de custo não podem ser decompostas e exibidas como **Desconhecido**.

Métricas da tabela:

<table><thead><tr><th>Métrica</th><th>Fórmula/observações</th></tr></thead><tbody><tr><td>Instalações</td><td><ul><li>Instalações totais</li><li>Cliques (click-throughs)<ul><li>Usuários trazidos através da atribuição por clique</li><li>Disponível para instalações gravadas a partir de 22 de dezembro de 2021</li></ul></li><li>Exibições (view-throughs)<ul><li>Disponível para instalações gravadas a partir de 22 de dezembro de 2021</li><li>Aplica-se a ad networks que implementam a SKAdNetwork V2.2+</li></ul></li></ul><p>Estes dados são derivados do campo do tipo fidelidade_ no postback</p></td></tr><tr><td>Taxa de valor de conversão nula</td><td>Postbacks com um valor de conversão nulo/Instalações \* 100 </td></tr><tr><td>Impressões</td><td> </td></tr><tr><td>Cliques</td><td> </td></tr><tr><td>Taxa de click-to-install</td><td>Instalações/Cliques \* 100</td></tr><tr><td>Usuários convertidos</td><td><p>Contagem de usuários que realizam um evento de mensuração específico.</p><ul><li>Modo personalizado: sempre af_skad_revenue (se qualquer outra coisa for selecionada, os usuários convertidos permanecerão vazios)</li><li>Modo SKAN 4: sempre af_skad_revenue (se qualquer outra coisa for selecionada, os usuários convertidos permanecerão vazios)</li><li>Modo de receita: sempre af_skad_revenue</li><li>Modo de conversão: evento in-app selecionado nas configurações do dashboard</li><li> <span>Modo de engajamento: evento in-app conforme definido no Conversion Studio</span><br/><br/> </li></ul><p>O tráfego de usuários convertidos <strong>orgânicos</strong> não é exibido no dashboard do SKAN</p></td></tr><tr><td>Usuários convertidos/Instalações</td><td> </td></tr><tr><td>Receita</td><td>Receita, incluindo dados modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Saiba mais</a> </td></tr><tr><td>Receita total (não modelado)</td><td>Receita informada por meio dos valores de conversão. Dados modelados não incluídos.</td></tr><tr><td>Receita D1-D2</td><td>Receita para a janela da SKAN 1 (dias 1-2, a menos que modificado), incluindo dados modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Saiba mais</a> </td></tr><tr><td>Receita D1-D2 (não modelado)</td><td>Receita recebida na 1ª da janela SKAN (dias 1-2, a menos que modificado). Dados modelados não incluídos.</td></tr><tr><td>Receita D3-D7</td><td>Receita para a janela 2 do SKAN (dias 3 a 7, a menos que modificado)</td></tr><tr><td>Receita D8-D35</td><td>Receita para a janela 3 do SKAN (dias 8 a 35, a menos que modificado)</td></tr><tr><td>Custo</td><td><ul><li>Custo informado pela ad network.</li><li>Se o nome da campanha mudar, os custos serão exibidos sob o nome da campanha mais recente utilizada. (Se houver vários nomes de campanha)</li></ul></td></tr><tr><td>OPCIONAL</td><td><ul><li>Receita média por usuário, incluindo dados modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Saiba mais</a> </li><li>Fórmula: receita (US$) (modelada) / instalações</li></ul></td></tr><tr><td>ARPU (não modelado)</td><td>Receita média por usuário, dados modelados não incluídos</td></tr><tr><td>ROI</td><td><ul><li>Retorno sobre o investimento, incluindo dados modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Saiba mais</a> </li><li>Fórmula: (receita (US$) (modelada) - custo) / custo x 100</li></ul></td></tr><tr><td>ROI (não modelado)</td><td>Retorno sobre o investimento, dados modelados não incluídos</td></tr><tr><td>ROAS</td><td><ul><li>Retorno sobre o gasto com anúncios, incluindo dados modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Saiba mais</a> </li><li>Receita</li></ul></td></tr><tr><td>ROAS (não modelado)</td><td>Retorno sobre o gasto com anúncios, dados modelados não incluídos</td></tr><tr><td>eCPI</td><td> </td></tr><tr><td colspan="2"><strong>Métricas de eventos in-app</strong></td></tr><tr><td>Nome do evento in-app</td><td> </td></tr><tr><td>eCPA</td><td><ul><li>Custo efetivo por ação, incluindo dados modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Saiba mais</a> </li><li>Fórmula: custo / usuários únicos realizando os eventos (modelado)</li></ul></td></tr><tr><td>eCPA (não modelado)</td><td>Custo efetivo por ação, dados modelados não incluídos</td></tr><tr><td>Contagem total de eventos</td><td>Total de ocorrências de eventos em todas as janelas, incluindo dados modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Saiba mais</a> </td></tr><tr><td>Contagem total de eventos (não modelado)</td><td>Total de ocorrências de eventos em todas as janelas, dados modelados não incluídos</td></tr><tr><td>Contagem de eventos <span>D1-D2</span> </td><td>Ocorrências de eventos para a 1ª janela (dias 1-2, a menos que modificados), incluindo dados modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Saiba mais</a> </td></tr><tr><td>Contagem de eventos <span>D1-D2 (não modelado)</span> </td><td>Ocorrências de eventos para a 1ª janela (dias 1-2, a menos que modificados), dados modelados não incluídos</td></tr><tr><td>Contagem de eventos <span>D3-D7</span> </td><td>Para <a href="./skan-conversion-studio#fixed-modes" target="_blank">modos fixos</a>, dados orgânicos estão disponíveis tanto para eventos de instalação como para eventos in-app.</td></tr><tr><td>Contagem de eventos <span>D8-D35</span> </td><td>Característica</td></tr><tr><td>Usuários únicos para o evento em D1-D2</td><td>Número de usuários únicos que realizaram o evento na janela 1 (dias 1 a 2)</td></tr><tr><td>Período</td><td>Número de usuários únicos que realizaram o evento na janela 1 (dias 1 a 2, a menos que seja alterado). Dados modelados não incluídos.</td></tr><tr><td>Usuários únicos para o evento em D3-D7 (não modelado)</td><td>Número de usuários únicos que realizaram o evento na janela 2 (dias 3 a 7, a menos que seja alterado). Dados modelados não incluídos.</td></tr><tr><td>Usuários únicos para o evento em D8-D35 (não modelado)</td><td>Número de usuários únicos que realizaram o evento na janela 3 (dias 8 a 35, a menos que seja alterado). Dados modelados não incluídos.</td></tr></tbody></table>

</Accordion>

<div id="modeled-metrics-and-null-cv" />

<Accordion title="Métricas modeladas e CV nulo">

Os relatórios da SKAdNetwork (SKAN) podem ser limitados, pois:

* A SKAN se baseia em valores de conversão (CVs) limitados a 6 bits, que resultam em 64 valores possíveis (0-63).
* A Apple às vezes retém o CV real (e retorna dados como "null") para preservar a privacidade do usuário.
* Os dados só estão disponíveis dentro de uma janela de mensuração e o lifetime value total (LTV) não é conhecido.

Os dados modelados da SKAN resolvem esses problemas, oferecendo:

* Valores de conversão modelados em vez de valores nulos.
* Receita modelada e ocorrências de eventos.
* Uma imagem mais completa da performance do LTV do aplicativo e da campanha.

As métricas modeladas disponíveis incluem:

* Resultados
* Contagem de eventos
* eCPA
* OPCIONAL
* ROI
* ROAS

<Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data">Saiba mais sobre os dados modelados da SKAN</Anchor>

</Accordion>

<div id="appsflyer-attribution-vs-skan-attribution" />

<Accordion title="Atribuição da AppsFlyer vs. Atribuição do SKAN">

As métricas do SKAN diferem daquelas disponíveis utilizando o modelo de atribuição da AppsFlyer. A tabela que segue enumera as principais causas.

Definições:

* **Horários:** considere a janela de atividade padrão de 24 horas (48 horas depois de atualizar para a SKAN 4).
* **SDK:** SDK da AppsFlyer incorporado no aplicativo.
* **Regras**: <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">modelo de atribuição da AppsFlyer</Anchor>

<div id="attribution-framework-differences" />

#### Diferenças na estrutura de atribuição

| Conceito | SKAN | A AppsFlyer |
| --- | --- | --- |
| Metodologia de atribuição compatível | Apple SKAN para atribuição por clique e exibição. Contém tráfego de campanhas app-to-app de ad networks e SRNs de apoio ao SKAN. | <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">O modelo de atribuição da AppsFlyer</Anchor> suporta múltiplos métodos e cenários de atribuição:<ul><li>Web mobile</li><li>Exibição (view-through)</li><li>Cliques (click-through)</li><li>App clips</li><li>Atribuição da web</li><li>Anúncios de Busca da Apple</li><li>Mídias próprias</li><li>Tráfego SRN (usuários com consentimento)</li><li>E mais</li></ul> |
| Fonte de dados primária | <ul><li>Postbacks do SKAN</li><li>SDK</li></ul> | SDK e soluções associadas.  Exemplo: eventos servidor para servidor. |
| Atualização de dados | <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#skan">Atualização de dados da SKAN.</Anchor> | Em tempo real, quando o usuário inicializa e utiliza o aplicativo. |
| Fuso horário | UTC | Fuso horário específico do aplicativo |
| Hora da instalação | Derivado da hora de chegada do postback do iOS. | Reportado pelo SDK. |
| Janela de atividades | Atividade do usuário durante uma janela de mensuração fixa, começando com a abertura do aplicativo. | Contém dados de LTV desde a data de instalação até o presente.<br /><br />Use a Coorte para visualizar dados limitados ao dia 0 ou dia 1 de coorte, ou ambos juntos para visualizar um período de métrica comparável.<br /><br />Considere que o dia 0 de coorte consiste de menos de 24 horas de atividade. Por exemplo, um usuário que instala às 18:00 em um determinado dia tem 6 horas de atividade no dia de coorte 0. |
| Instalações relatadas por | <ul><li>**SKAN**: limitado a instalações não orgânicas e re-downloads não orgânicos.</li><li>**SDK**: todas as instalações são relatadas. Somente as primeiras instalações são contadas para fins de métrica. Significa que as reatribuições são desconsideradas.</li></ul> | O SDK reporta todas as instalações categorizadas usando Regras em instalações de primeira vez e reinstalações (reatribuições). |
| Nível de granularidade publicitária | Campanha, conjunto de anúncios, ID do conjunto de anúncios, anúncio e ID do anúncio. | Hierarquia completa: Campanha, ID da campanha, conjunto de anúncios, parâmetros adicionais como canal e parceiro. |
| Redownloads vs. reinstalações | Redownloads relacionam-se às ações de um determinado usuário Apple ID. Elas não são paralelas a reatribuições. | O retargeting (reatribuições de reengajamento) reflete no painel Retargeting. Eles não são paralelos aos redownloads. |

<div id="metric-differences" />

#### Diferenças de métrica

| Métrica | SKAN | Atribuição tradicional |
| --- | --- | --- |
| Instalações não-orgânicas | Contagem de postbacks de iOS recebidos pela AppsFlyer.<br /><br />Considere que a AppsFlyer não recebe os postbacks das ad networks que não completaram a integração do SKAN com a AppsFlyer.<br /><br />Isso pode levar à subcontagem de instalações não orgânicas e ao aumento das instalações orgânicas. | <ul><li>Reportado pelo SDK.</li><li>Atribuído a uma fonte de mídia.</li><li>Contado usando Regras.</li></ul> |
| Instalações orgânicas | Instalações do SDK menos instalações do SKAN | <ul><li>Reportado pelo SDK.</li><li>Não atribuído a nenhuma fonte de mídia.</li><li>Contado usando Regras.</li></ul> |
| Resultados | **Não orgânico**: receita relatada pelos postbacks do SKAN.<br /><br />**Orgânico:** receita relatada por eventos in-app do SDK, menos receita não orgânica. **Observação**: as métricas orgânicas nem sempre estão disponíveis. [Saiba mais](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). | <ul><li>Reportado por SDK e API servidor para servidor.</li></ul> |
| Receita de anúncios | <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">Disponível</Anchor> | A receita publicitária a nível de usuário é atribuída com base no IDFV |
| ROI/ROAS | Receita durante a janela de mensuração. | <ul><li>Dados de LTV: 5 anos</li><li>Métricas de UA e campanhas de retargeting.</li></ul> |

</Accordion>

<div id="faq-skan-discrepancies" />

<Accordion title="Perguntas frequentes — discrepâncias do SKAN">

| Motivo | Discrepâncias—QA |
| --- | --- |
| E | **P: Por que os números de conversão no painel da AppsFlyer diferem dos números do painel da ad network?**<br /><br />**A**: Razões das discrepâncias<ul><li>**Data de instalação vs. data de chegada do postback:**<ul><li>AppsFlyer: a data de instalação é derivada usando uma fórmula que leva em consideração o tempo de chegada do postback do iOS, a duração da janela e o tempo de atraso do postback.</li><li>Ad network: normalmente, usa apenas o horário de chegada do postback do iOS como a data de instalação, sem ajuste.</li><li>Use a opção **exibir por data de chegada do postback** no painel para eliminar esta diferença.</li></ul></li><li>**Validação do postback:** a AppsFlyer valida os postbacks do iOS recebidos e assegura que a assinatura da Apple seja válida. A ad network pode enviar postbacks inválidos desconsiderados pela AppsFlyer.</li><li>**Postbacks desaparecidos**: postbacks do iOS devem ser enviados pela ad network para AppsFlyer. A AppsFlyer não recebe o postback diretamente do dispositivo. Se faltam postbacks, a AppsFlyer não tem como saber disso.</li></ul> |
| B | **P**: **Quais são as diferenças entre a <Anchor target="_blank" href="/marketers/pt/docs/skan-aggregated-performance-report-api">API de desempenho do SKU</Anchor> e o painel versus a <Anchor target="_blank" href="/marketers/pt/docs/skan-aggregated-postback-arrival-date-api">API de postback agregada do SKU?</Anchor>**<br /><br />**R**: O intervalo de datas da API de postback está relacionado à data em que a AppsFlyer recebeu o postback. O intervalo de datas da API de desempenho está relacionada à data de instalação derivada como descrito no motivo A. |
| C | **P: Todas as ad networks relatam a geolocalização?**<br /><br />**A:** Não. |
| J | **P: Por que existem diferenças entre o painel de visão geral e o painel do SKAN?**<br /><br />**A:** Consulte a seção anterior para uma visão geral sobre os motivos das discrepâncias. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Ocorrências de eventos modelados | <ul><li>Os eventos modelados se baseiam na fórmula descrita em [Métricas modeladas e CV nulo](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv).</li><li>A fórmula é aplicada por linha de dados. Isto pode causar discrepâncias entre a contagem de eventos modelados para uma determinada fonte de mídia e a soma da contagem de eventos modelados de suas campanhas.</li></ul> |
| Data de chegada do postback | A data final em um intervalo de datas é limitada ao dia em que a última instalação foi registrada. |
| Dados orgânicos | <ul><li>A **receita orgânica** está disponível apenas para receita no modo <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#fixed-modes">fixo</Anchor> ou legado.</li><li>Para <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#skan-4">SKAN 4</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#custom">modos personalizados</Anchor>, os dados orgânicos estão disponíveis para instalações, não para eventos in-app e receita geral.</li><li>Para os **modos não legados** (<Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#skan-4">SKAN 4</Anchor>, personalizado e encode), os dados orgânicos estão disponíveis apenas para instalações.</li><li>Considere o uso do SSOT para visualizar dados orgânicos, já que o SSOT deduplica os eventos atribuídos pelo modelo SKAN e pelo modelo AppsFlyer.</li><li>Se os dados de atribuição da AppsFlyer (novas instalações orgânicas e não orgânicas) menos os dados de atribuição SKAN (instalações não orgânicas) forem iguais a um número negativo, o painel SKAN exibirá 0 em instalações orgânicas.</li></ul> |
| Dados históricos | Dados de conversão mais antigos suportados: 1º de novembro de 2020 |
| Moeda | Exibe em USD ou na moeda local específica do aplicativo, conforme definido na <Anchor target="_blank" href="/marketers/pt/docs/app-settings">página de configurações do aplicativo</Anchor>. |
| Fuso horário | Para dados informados pelo SKAN, instalações e eventos são exibidos usando UTC, com exceção dos dados Meta e Google SKAN, para os quais o fuso horário é baseado no fuso horário configurado em suas contas Meta e Google, respectivamente. |
| Filtrar por versão do SKAN | Para alguns parceiros de mídia, **desconhecido** é exibido. Isso acontece porque eles não fornecem esse campo no momento.<ul><li>Google</li><li>Meta<br />Outros - você verá esse campo, pois o dashboard do SKAN oferece suporte a métricas de pré-atribuição, como custo, cliques e impressões, e não podemos detalhar essas métricas por versão, então uma nova linha terá essas métricas.</li></ul> |
| Anúncios de Busca da Apple | Apple Search Ads não compartilha dados no nível da campanha. As campanhas de agência que exigem um prefixo não aparecerão na visualização da agência. |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Guia de soluções do SKAN da AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/about-att-and-skan">O que há de diferente—Atualizações da AppsFlyer relacionadas ao iOS 14</Anchor>

<div data-zendesk-anchors="dashboard-principles=princ%C3%ADpios-do-painel 01H81P8JPZM24J0536GKBPNFMJ=princ%C3%ADpios-do-painel skan-dashboard-view-options=op%C3%A7%C3%B5es-de-visualiza%C3%A7%C3%A3o-do-painel-do-skan 01H81P8JPZC5K0KZR64P084N4W=op%C3%A7%C3%B5es-de-visualiza%C3%A7%C3%A3o-do-painel-do-skan dashboard-use=uso-do-painel 01H81P8JPZGSHQVMG27YEJPARH=uso-do-painel 01H81P8JPZ93G4EQY343SV2B1Q=dashboard-settings 01H81P8JPZV5F4VCZHR537HREH=filter-options 01H81P8JQ0KRGXWCVT82YW30CS=headline-metrics 01H81P8JQ0ETB0W3SGS56CBCX8=charts 01H81P8JQ0KK1NMRGFR0GBX4EK=metrics 01H81P8JQ0ZKGTRWNW95D015Z7=modeled-metrics-and-null-cv 01H81P8JQ18NGP8Z74D02DMQ7P=appsflyer-attribution-vs-skan-attribution attribution-framework-differences=diferen%C3%A7as-na-estrutura-de-atribui%C3%A7%C3%A3o 01H81P8JQ1VTYX3382WDXDMVT3=diferen%C3%A7as-na-estrutura-de-atribui%C3%A7%C3%A3o metric-differences=diferen%C3%A7as-de-m%C3%A9trica 01H81P8JQ1M8M9TSHF0C12Z2QE=diferen%C3%A7as-de-m%C3%A9trica faq%E2%80%94skan-discrepancies=faq-skan-discrepancies 01H81P8JQ157YYNX9C527ES4C8=faq-skan-discrepancies 01H81P8JQ1T3DE29Y14VARKASK=traits-and-limitations h_01HE7SWGPWNWG26CEN40VSTA9J=veja-tamb%C3%A9m" />

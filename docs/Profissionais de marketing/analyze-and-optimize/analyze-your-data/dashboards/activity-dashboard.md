---
title: Dashboard de atividades
metadata:
  keywords:
    - activity report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-01-12T15:50:15Z'
  edited_at: '2026-08-19T00:03:28Z'
  id: 207602503
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/207602503
---
> **Resumo:** Veja a atividade da app, o engajamento e as métricas internas durante um determinado período. As métricas do dia atual são atualizadas em tempo real.

<Image align="center" alt="ActivityDB.png" src="https://files.readme.io/8150eafc018c83ae2b1030702129bda12419dfac60eb8664187c2acd66136df3-4420170646289.png" />

<div id="activity-dashboard" />

## Dashboard de atividades

* Contém tráfego orgânico e não orgânico.
* O intervalo de datas refere-se à data do evento e não é <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">baseado em LTV.</Anchor>
* Atualização de dados:
  * **Dia atual**: <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Contínuo</Anchor>. Exemplo: DAU, sessões, receita
  * **Média:** Diária. Exemplo: MAU, DAU médio, MAU médio
* O filtro de geolocalização se relaciona com a localização do usuário no momento da instalação

<div id="tip" />

> 👍 **Dica**
>
> Quer saber mais sobre o dashboard de atividades? Confira o  <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7802/play/18621/the-activity-dashboard">curso rápido e informativo no portal de aprendizado da AppsFlyer</Anchor>.

<div id="dashboard-features-and-layout" />

## Funcionalidades e layout do dashboard

<div id="metric-definitions" />

<Accordion title="Definições de métricas">

<Table>
  <thead>
    <tr>
      <th>
        Métrica
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="dau"></span>
        DAU
      </td>
      <td>
        * Usuários ativos diários o número de usuários únicos que abriram o aplicativo pelo menos uma vez durante o dia.
        * O DAU se baseia em sessões.
        * <Anchor target="_blank" href="/marketers/pt/docs/unique-users">Saiba mais sobre usuários únicos</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="average-dau"></span>
        DAU médio
      </td>
      <td>
        Número médio de usuários ativos diariamente, por dia, durante o período selecionado.

        Exemplo: Cálculo do DAU médio

        > 📄
        >
        > |  | Domingo | Segunda-feira | Terça-feira |
        > | --- | --- | --- | --- |
        > | <span id="daily-active-unique-users"></span>Usuários únicos ativos diariamente | 10 | 12 | 8 |
        >
        >
        >
        > **DAU médio**= (10+12+8)\/3 = 10.
      </td>
    </tr>
    <tr>
      <td><span id="mau"></span>
        MAU
      </td>
      <td>
        Usuários ativos mensais:

        * **Detalhado:** número de usuários únicos (contados apenas uma vez) que abriram o aplicativo pelo menos uma vez durante os 31 dias anteriores.
        * Alto nível: número de usuários únicos (contados apenas uma vez) que abriram o aplicativo pelo menos uma vez durante o mês.
      </td>
    </tr>
    <tr>
      <td><span id="daumau-rate"></span>
        Taxa DAU/MAU
      </td>
      <td>
        * Esta métrica apresenta uma visão da taxa de retorno dos usuários. Uma taxa DAU/MAU de 50% significa que o usuário médio abriu o aplicativo em 15 dos 31 dias anteriores.
        * A taxa DAU/MAU é uma medida de aderência do usuário e fornece um instantâneo da retenção do usuário.
      </td>
    </tr>
    <tr>
      <td><span id="revenue"></span>
        Resultados
      </td>
      <td>
        Receita gerada durante o período selecionado. A receita consiste em compras in-app (se informadas) e receita de anúncios.
      </td>
    </tr>
    <tr>
      <td><span id="arpdau"></span>
        ARPDAU
      </td>
      <td>
        Receita média por usuário ativo diário.  
        Receita média por usuário ativo diário  
        Fórmula: soma de (receita no dia [n] / DAU no dia [n])]/Número de dias.

        <div id="h_01HHYHP1HFZBRTWB8MJ1F6XKZS" />

        > 📄 **Exemplo: Cálculo do ARPDAU**
        >
        > | Dia | Receita no dia ($) | DAU | Receita média diária do usuário ($) |
        > | --- | --- | --- | --- |
        > | <span id="day-1"></span>Dia 1 | 10 | 5 | 2 |
        > | <span id="day-2"></span>Dia 2 | 16 | 4 | 4 |
        > | <span id="day-3"></span>Dia 3 | 30 | 5 | 6 |
        > |  |  | Total: | 12 |
        > |  <span id="::4eb0b020"></span>|  | Número de dias | 3 |
        > |  <span id="::b35cc38c"></span>|  | **ARPDAU** | 4 |
      </td>
    </tr>
    <tr>
      <td><span id="sessions"></span>
        Sessões
      </td>
      <td>
        Sessões durante o período selecionado (se relatado pelo aplicativo)
      </td>
    </tr>
    <tr>
      <td><span id="installs"></span>
        Instalações
      </td>
      <td>
        Número de instalações durante o período especificado
      </td>
    </tr>
    <tr>
      <td><span id="average-ecpi"></span>
        eCPI médio
      </td>
      <td>
        Custo médio por instalação. Atenção: As instalações são instalações de aquisição de usuários (UA) e o custo é unificado (UA e retargeting).
      </td>
    </tr>
    <tr>
      <td><span id="conversion-rate"></span>
        Taxa de conversão
      </td>
      <td>
        Taxa de instalações a partir de cliques. **Atenção:** As instalações são instalações de aquisição de usuários (UA) e os cliques são unificados (UA e retargeting).
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="detailed-tab" />

<Accordion title="Separador detalhado">

A aba de análise detalhada está dividida em seções: métricas principais, tendência da atividade e resumo da atividade.

<table><tbody><tr><td colspan="2"><h4><strong><span id="headline-metrics"></span>Métricas principais</strong></h4></td></tr><tr><td> </td><td><img alt="ActivityHeadLines_us-en__1_.png" src="https://files.readme.io/a4f1a5316eeacf0f635bbeadf52d490dd0276bb8a1fe9c0e32db7008d11d044b-360012584838.png"/></td></tr><tr><td> </td><td><p><strong>Média de usuários ativos</strong></p><ul><li>DAU médio: o número médio de usuários ativos diariamente no intervalo de tempo especificado.</li><li>MAU médio: o número médio de usuários ativos mensais no intervalo de tempo especificado. Ele é calculado como uma média móvel dos dias no intervalo de datas selecionado, em que cada dia inclui os 31 dias anteriores. Nota: Para ver o valor MAU de um mês específico, como março, defina o período de datas para o primeiro dia após esse mês (por exemplo, 1 de abril) e verifique o valor MAU médio.</li></ul></td></tr><tr><td> </td><td> <strong>Total de instalações:</strong> Número de instalações divididas em orgânicas e não orgânicas.</td></tr><tr><td> </td><td> <strong>Total de sessões</strong>: Número de sessões divididas por usuários orgânicos e não orgânicos.</td></tr><tr><td> </td><td> <strong>Receita total</strong>: Receita dividida em atribuível a usuários orgânicos e não orgânicos.</td></tr><tr><td colspan="2"><h4> <br/><strong><span id="activity-trends"></span>Tendências de atividade</strong><br/> </h4></td></tr><tr><td> </td><td><p> <strong>Linha de tendência com comparação</strong></p><p><img alt="TrendLinWithComp_us-en.png" src="https://files.readme.io/b9edb3e409dc13bc72aebdccdc499fa2dcd9abf4549fb0170bf0cdc7036eee15-360012507997.png"/></p><ul><li>O gráfico de tendências exibe os KPIs ou mensurações relacionadas a eventos in-app.</li><li>Uma linha de tendência de comparação opcional pode ser adicionada, ativando <strong>Comparar com o período de tempo anterior</strong> (dia, semana, mês, trimestre, ano).</li><li>Por exemplo, se você selecionar "mês", isso significa que para um determinado dia no gráfico, a comparação é para o mesmo dia do mês anterior. </li></ul><p>Os KPIs disponíveis são:</p><ul><li><span>DAU</span></li><li><span>MAU</span></li><li><span>Resultados</span></li><li><span>ARPDAU</span></li><li><span>Sessões</span></li><li><span>Taxa DAU/MAU</span></li></ul><p><span>As mensurações disponíveis para eventos in-app são: </span></p><ul><li><span>Contagem</span></li><li><span>Usuários únicos</span></li><li><span>Resultados</span></li></ul></td></tr><tr><td colspan="2"><h4> <br/><strong><span id="activity-summary-table"></span>Tabela de resumo das atividades</strong> </h4></td></tr><tr><td> </td><td><p>A tabela de resumo das atividades:</p><ul><li>exibe até 50 fontes de mídia com dados relacionados a impressões, cliques, instalações, etc. (para obter todos os dados, use a <a href="./master-api-user-acquisition-metrics-via-api" target="_blank">Master API</a> ou o <a href="./pivot-table-user-metrics" target="_blank">Pivot.)</a> </li><li>É classificada pelo número de sessões.</li><li>Permite detalhar até o nível da campanha (não podendo ir além desse nível).</li><li>É uma boa maneira de ver quantos DAUs são novos e quantos são usuários existentes (DAUs menos instalações).</li></ul><p><span>Para usar a tabela de resumo:</span></p><ul><li><span>Refine os dados exibidos usando os campos Filtrar por e Agrupar por.</span></li><li><span>As colunas da tabela podem ser ordenadas clicando no header de uma coluna.</span></li><li>Filtrar por <strong>eventos in-app</strong> para limitar a exibição a eventos in-app específicos.</li><li>Alternar entre diferentes tipos de visualização:<ul><li> Resumo: o total para todos os eventos in-app selecionados</li><li> <strong>Eventos</strong> <strong>in-app</strong> divididos por evento in-app</li></ul></li></ul></td></tr></tbody></table>

</Accordion>

<div id="highlevel-tab-previous-twelvemonths" />

<Accordion title="Aba de alto nível: últimos doze meses">

<Image align="center" alt="ActivityHiLevel.png" src="https://files.readme.io/42636f5b13dca3a2209ea295c02e784175dfc92a2523c861220b87baed859541-4420194466065.png" />

A aba contém um histórico de visão geral de doze meses da performance da atividade do aplicativo e tem os seguintes gráficos: 

* Usuários ativos e receita
* Lucro bruto mensal: receita, custo, lucro bruto

</Accordion>

<div id="specifications-and-limitations" />

## Especificações e limitações

| Especificações | Observações |
| --- | --- |
| Atualidade dos dados | <ul><li>**Métricas:** Em tempo real. Veja a imagem a seguir.</li><li>**Métricas médias**: Diária. Veja a imagem a seguir. **Atenção:** As métricas médias não são calculadas em tempo real para evitar distorções com dados de dias incompletos. Se o intervalo de datas incluir o dia atual, então ocorre o seguinte:<ul><li>Se o intervalo de datas for apenas para o dia atual: os resultados médios não são exibidos.</li><li>Se o intervalo de datas for para um período que inclui o dia atual: a média é calculada sem incluir os dados do dia atual.</li></ul></li><li>**Processamento de dados do dia anterior:** O processamento de dados começa à meia-noite UTC para os dados do dia anterior. Para aplicativos que operam em fusos horários atrasados em relação ao UTC (UTC-), isso significa que o dia local deles ainda pode estar em andamento quando o processamento começa, o que pode levar a dados inicialmente incompletos. Os dados restantes são processados e incorporados no dia seguinte.</li><li>**Receita de anúncios:** <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#data-freshness">registrada com um atraso</Anchor> e relatada na seguinte data:<ul><li>Dados de nível agregado: no Dia 1 (o dia em que os dados são extraídos).</li><li>Dados em nível de usuário: no Dia 0 (o dia em que o anúncio é exibido).</li></ul></li></ul>[![Whats_realtime.png](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png)](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png) |
| Desinstalações | Sem suporte |
| Redirecionamento | A partir de 1 de fevereiro de 2025, todas as métricas de atividade são dados unificados (UA e retargeting juntos). No entanto, antes de 1 de fevereiro de 2025, as seguintes métricas incluem apenas dados de tráfego de UA:<ul><li>Total de sessões</li><li>DAU</li><li>MAU</li><li>DAU/MAU</li><li>ARPDAU</li><li>Custo</li><li>Cliques</li><li>Impressões</li><li>Taxa de conversão</li><li>eCPI</li></ul>A visão unificada é a única disponível; os usuários não conseguem trocar para visualizar apenas UA ou retargeting. |
| ARPDAU | Pode haver discrepâncias entre o ARPDAU no dashboard de atividades e no dashboard Pivot. |
| Histórico de dados | <ul><li>3 anos</li><li>Aba de alto nível: 1 ano</li></ul> |
| Intervalo de exibição | <ul><li>Máximo de 2 meses. Se um período mais longo for especificado, o intervalo é reduzido para dois meses e uma mensagem é apresentada.</li></ul> |
| Agrupar por geolocalização | <ul><li>A agregação por geolocalização se baseia na geolocalização onde a instalação ocorreu.</li><li>Exibe até 62 geolocalizações (classificadas pelas principais sessões de atividade).</li></ul> |
| Agrupar por campanha | Esse agrupamento só está disponível após a seleção de fontes de mídia específicas. |
| Valores de dimensão | Os valores de dimensões como fonte de mídia, nome da campanha e nome do recurso são sensíveis a maiúsculas e minúsculas. Por exemplo, isto significa que "Facebook" e "facebook" serão tratados como entidades distintas ao filtrar os resultados. Para ver os resultados sem considerar a distinção entre maiúsculas e minúsculas, use o <Anchor target="_blank" href="/marketers/pt/docs/pivot-table-user-metrics">Pivot table</Anchor>. |
| Agências | As agências não têm acesso ao dashboard de Atividades. <Anchor target="_blank" href="/marketers/pt/docs/manage-data-access-permissions">Saiba mais</Anchor> |
| DAU médio e MAU médio | As métricas de DAU médio e MAU médio podem contabilizar o mesmo usuário em vários agrupamentos. Por exemplo, se um usuário fizer a instalação de um Aplicativo pela Network A e depois interagir com ele pela Network B, ele aparecerá em ambas as network ao agrupar por canal de mídia ou campanha. Como resultado, somar esses valores diretamente pode gerar duplicação. Para obter o total preciso de DAU médio ou MAU médio, consulte a métrica de KPI em vez de agregar os valores da tabela. |
| Redes de anúncios | Para determinadas ad networks, a tabela de atividade pode exibir duas linhas em vez de uma. Nesses casos:<ul><li>Impressões, cliques, custo e conversões devem ser calculados como a soma de ambas as linhas.</li><li>Sessões de atividade, receita de atividade, DAU médio, MAU médio, taxa média de DAU/MAU e ARPDAU devem ser considerados de apenas uma das linhas.</li></ul> |
| Modo legado: eventos in-apps orgânicos não atribuídos | Se o seu aplicativo usa o modo legado **eventos in-apps orgânicos não atribuídos**, a quantidade de **usuários orgânicos ativos** obtidos em tempo real pode parecer menor do que o esperado. Valores corrigidos automaticamente após o dia atual terminar. Para uma visualização mais precisa em tempo real, recomendamos que você mude para o modo de **primeira instalação**.  <br />Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#unattributed-organic-inapps">modo de eventos in-apps orgânicos não atribuídos</Anchor> e o <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#attributed-to-the-first-install">modo de primeira instalação</Anchor>. |

<div data-zendesk-anchors="activity-dashboard=dashboard-de-atividades h_01HHYHP1HE8G5VA6GSAVTQDDDN=dashboard-de-atividades h_01HHYHP1HEJHKQKCNC5R26ZE3J=dica dashboard-features-and-layout=funcionalidades-e-layout-do-dashboard h_01HHYHP1HEBTACW6Q3MJ3QJJ95=funcionalidades-e-layout-do-dashboard h_01HHYHP1HESQBPYJWK81ZHQDVH=metric-definitions h_01HHYHP1HFZBRTWB8MJ1F6XKZS=exemplo-c%C3%A1lculo-do-arpdau h_01HHYHP1HFF92WQMQAFKWWNDJK=detailed-tab h_01HHYHP1HFNDXC2E55Q7PDE9WY=headline-metrics h_01HHYHP1HFZR9JN2H0RNAG1QTK=activity-trends h_01HHYHP1HFV8AZ2FYKJ300488A=activity-summary-table h_01HHYHP1HF6FCXPS2SHTH0RBXC=highlevel-tab-previous-twelvemonths specifications-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01HHYHP1HFNJF4JJZY4CSVZ3GY=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />

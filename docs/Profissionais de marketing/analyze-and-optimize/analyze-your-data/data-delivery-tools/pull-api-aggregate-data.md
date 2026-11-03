---
title: Dados agregados da Pull API
metadata:
  keywords:
    - Performance
    - raw data
    - Pull API
    - Reports
    - API
    - Parameters
    - API Policy
    - Advertisers
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2026-08-19T00:04:21Z'
  id: 207034346
  locale: pt
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/pt/articles/207034346
---
> **Visão geral:** use esta Pull API para obter seus relatórios agregados da AppsFlyer em arquivos CSV.

[![PullAPIAverage_us-en.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

> 👍 **Procurando por dados brutos da Pull API?**
>
> Aprenda tudo <Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data">aqui</Anchor>.

## Dados agregados da Pull API

* A Pull API permite obter relatórios de dados agregados para aquisição de usuários (UA) e redirecionamento em arquivos CSV.
* As <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support">taxas de atualização dos dados</Anchor> são iguais às do relatório equivalente na página de Exportar Dados e na página de Visão Geral do dashboard. Considere que o custo pode ser atualizado com um atraso de várias horas, dependendo do parceiro que fornece os dados de custo.
* Filtrar por opções disponíveis: fonte de mídia e intervalo de datas.
* Os recursos adicionais da Pull API são:
  * Adicionar tipo de toque de atribuição
  * Selecione o fuso horário

#### Relatórios de desempenho agregados disponíveis na Pull API

<table><thead><tr><th>Categoria</th><th> UA</th><th>Remarketing\*</th></tr></thead><tbody><tr><td>Parceiros (fonte de mídia)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Parceiros por data</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Diariamente</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Geolocalização</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Relatório de geolocalização por data</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="3">\* Para relatórios de redirecionamento, adicione <code><span>&amp;reattr=true</span></code> ao URI. </td></tr></tbody></table>

<div id="using-pull-api-aggregate-data" />

<Accordion title="Usando dados agregados da Pull API">

**Para usar os dados agregados da Pull API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Obtenha o token da API. Um administrador precisa recuperar o token.
2. Forneça ao seu desenvolvedor o token de API a ser usado no cabeçalho de autenticação.
3. Forneça a seus desenvolvedores os [parâmetros](/docs/pull-api-aggregate-data#parameters) a serem inseridos quando eles fizerem a chamada de API, conforme descrito na seção a seguir. Os parâmetros determinam o foco do relatório, como ele é organizado e fornecem um cronograma de relatório.
4. Diga ao seu desenvolvedor para seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">instruções de dados agregados da Pull API</Anchor> no hub de desenvolvedores.

</Accordion>

<div id="parameters" />

<Accordion title="Parâmetros">

| Parâmetro | Descrição |
| --- | --- |
| ativado | ID do aplicativo |
| from (a partir de) | <ul><li>O intervalo de datas consiste em um parâmetro `from`e `to`. O intervalo é o período de LTV (instalação).</li><li>Formato: `yyyy-mm-dd`,</li><li>Exemplo: 01-01-2010</li></ul> |
| to (até) | Data final. Quanto a `from` |
| fonte\_de\_mídia | Use para limitar (filtrar) uma fonte de mídia específica.<ul><li>Exemplo:`media_source=facebook`</li></ul> |
| tipo\_de\_toque\_de\_atribuição | Defina este parâmetro como mostrado no exemplo para obter KPIs de [atribuição de visualização](/docs/pull-api-aggregate-data) (VTA).<br /><br />Exemplo: `attribution_touch_type=impression`<br /><br />Alguns KPIs de VTA, como cliques, impressões e APIs de custo, não têm valores associados a eles e exibem o valor N/A. |
| símbolos monetários | Moeda de receita e custo.<br /><br />Relatórios agregados de Pull API sempre usam a moeda específica do aplicativo. |
| reattr | Obtenha dados de conversões de retargeting.<ul><li>[Padrão] Se falso, as campanhas de dados de aquisição de usuários (UA) serão retornadas.</li><li>Se verdadeiro, a conversão de retargeting irá retornar.</li><li>**Exemplo**:`reattr=true`</li></ul> |
| Fuso horário | [Padrão] Os dados retornam usando UTC.<ul><li>Os templates de URIs são preenchidos com o parâmetro de fuso horário definido para o fuso horário específico do aplicativo.</li><li>[Padrão] Se o parâmetro não for enviado, os dados retornarão usando UTC.</li><li>Se você enviar `timezone=[Joda-Time]`, os dados serão retornados usando o fuso horário específico do aplicativo.</li></ul>Observações sobre a seleção de fusos horários<ul><li>O formato de fuso horário Joda-Time considera o horário de verão.</li><li>O valor de Joda-Time deve ser idêntico ao valor definido na página de definições do aplicativo. Por exemplo, se o fuso horário definido é o de Paris, o valor do fuso horário na URL da Pull API deve ser `timezone=Europe%2fParis`.</li><li>Extrair dados no fuso horário selecionado está disponível somente a partir da data em que a configuração do fuso horário foi feita. Qualquer dado anterior à data da mudança usa UTC como fuso horário.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Comentários |
| --- | --- |
| Tipo de token de API necessário | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">Token V2.0</Anchor> |
| Acesso da ad network | Não |
| Acesso das agências | S |
| Transparência da agência | S |
| Moeda específica do aplicativo | S |
| Fuso horário específico do aplicativo | S |
| Custo | Os dados de custo são apenas para campanhas de UA; não para retargeting ou campanhas inativas (campanhas sem instalações). |
| Atualização de dados | <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Contínuo</Anchor> |
| Dados históricos | Os dados agregados de LTV ficam disponíveis por até 25 meses (2 anos + 1 mês) |
| Dados não orgânicos | S |
| Dados orgânicos | S |
| Limitações de taxa | <Anchor target="_blank" href="/marketers/pt/docs/report-generation-quotas-rate-limitations">Limitação</Anchor> |
| Limitações de tamanho | <ul><li>A Pull API para **dados brutos** oferece suporte a até 1 milhão de linhas. A Pull API para dados brutos aceita 1 milhão de linhas.</li><li>As chamadas de API retornam no máximo 200 mil linhas.<ul><li>Se um relatório tiver exatamente 200 mil linhas, assuma que estão faltando linhas.</li><li>Faça múltiplas chamadas de API usando os parâmetros from/to que incluem a hora do dia.</li></ul></li></ul> |
| Alterações de nome da campanha | Os relatórios de Pull API não são compatíveis com alterações no nome da campanha |

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview">Descrições e exemplos de relatórios agregados</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview">Selecionando a ferramenta de entrega de dados correta para dados agregados</Anchor>

<div data-zendesk-anchors="h_01HE0YP82966QHRAEW979ABCTP=procurando-por-dados-brutos-da-pull-api pull-api-aggregate-data=dados-agregados-da-pull-api h_01HE0YP829WD5TDFHTPYAV30QN=dados-agregados-da-pull-api aggregate-performance-reports-available-via-pull-api=relat%C3%B3rios-de-desempenho-agregados-dispon%C3%ADveis-na-pull-api h_01HE0YP829EQ7N6CST352X917H=relat%C3%B3rios-de-desempenho-agregados-dispon%C3%ADveis-na-pull-api h_01HE0YP82954F1ACVR2K4AFD5W=using-pull-api-aggregate-data h_01HE0YP8292131Q2561A4E1GYZ=parameters h_01HE0YP829ZPJAPHPDR9H4HMRT=traits-and-limitations h_01HE0Y2KTXS06WHN57MQ91AD09=veja-tamb%C3%A9m" />

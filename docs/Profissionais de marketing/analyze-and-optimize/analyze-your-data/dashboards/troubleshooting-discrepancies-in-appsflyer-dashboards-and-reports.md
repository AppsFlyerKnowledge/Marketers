---
title: Resolvendo discrepâncias nos dashboards e relatórios da AppsFlyer
metadata:
  keywords:
    - dashboard
    - activity
    - Advertisers
    - ltv
    - life time value
    - lifetime value
    - lifetime
    - Agencies
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
  created_at: '2017-11-07T12:42:27Z'
  edited_at: '2026-08-18T00:04:23Z'
  id: 115005600889
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/115005600889
---
> **Resumo:** Entenda por que podem haver diferenças e discrepâncias na comparação de dados de diferentes dashboards e relatórios. Frequentemente, isso pode acontecer porque os dados em um local são dados de lifetime value (LTV) e em outro são dados de atividade. Os dados de LTV estão relacionados a instalações que ocorreram durante um intervalo de datas específico. Os dados de atividade são eventos que ocorreram durante um intervalo de datas específico.

## Sobre diferenças e discrepâncias de dados

Ao comparar dados de diferentes dashboards e relatórios, o motivo comum para discrepâncias é o fato de que você pode não estar comparando os mesmos dados. Veja a checklist abaixo para garantir que você está comparando dados equivalentes:

* As plataformas de aplicativo são as mesmas (Android, iOS, CTV, etc.)?
* Os app IDs são os mesmos?
* Os filtros do dashboard/dados são os mesmos?
* As moedas são as mesmas?
* Os fusos horários são os mesmos?
* A <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support">atualização dos dados</Anchor> é a mesma?
* Os dados são <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">dados agregados</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">dados brutos</Anchor>?
* Os dados são de LTV ou de atividade?

Um dos motivos mais comuns para diferenças nos dados é a comparação de um dashboard ou relatório de LTV com um dashboard ou relatório de atividade. Veja as seções a seguir para saber mais sobre as diferenças entre LTV e atividade.

## LTV vs. atividade

Há duas formas de analisar dados de eventos do usuário. Dados de evento se relacionam às ações executadas pelos usuários pós-instalação, como compras in-app, cadastros e níveis concluídos. Na AppsFlyer os dados de evento estão disponíveis agrupados pela data de aquisição de usuário ou pela data do evento em si.

* Dados de eventos pós-instalação agrupados por data de aquisição de usuário são considerados como lifetime value (LTV).
* Dados de eventos pós-instalação agrupados por data de evento são considerados como atividade.

**Atenção:** As instalações não são consideradas nem dados de LTV nem atividade.

Ambos os dados são úteis, mas para diferentes propósitos. Por isso, ambos estão disponíveis.

### Dados de LTV

* Dados de LTV são eventos executados durante o tempo de vida de um usuário que instalou o aplicativo/converteu em um intervalo de datas específico. O intervalo de datas refere-se a usuários que instalaram durante o período e mostra quão valiosos eles são durante seu tempo como clientes. Se um usuário converteu/instalou o aplicativo antes da data especificada, então mesmo que eventos ocorram durante o intervalo de datas especificado, eles não aparecem nos dashboards e relatórios de LTV.
* Dados de LTV são uma ferramenta que mostra a qualidade dos usuários/span> a partir de diferentes fontes de mídia. A otimização de campanhas depende dos dados de LTV.

### Dados de atividade

* Os dados de atividade mostram o que os usuários fizeram durante um intervalo de datas específico. Os dados de atividade mostram o que os usuários fizeram durante um intervalo de datas específico, ou seja, quais eventos foram realizados por usuários ativos do aplicativo durante um intervalo de datas especificado. Não importa se os usuários converteram/instalaram o aplicativo fora do intervalo de datas.
* Como os dados de atividade exibem uma análise precisa dos eventos cronológicos, eles são úteis para mensurar a performance geral dos canais de mídia durante um intervalo de datas específico. Por exemplo, use os dados de atividade para ver quantos eventos de compra foram realizados por todos os usuários do aplicativo durante um mês específico.
* Use os dados da atividade para comparar o comportamento do usuário no mês atual em relação a um mês anterior.

> 📄 **Analogia do trem**
>
> Essa analogia ajudará você a entender a diferença entre LTV e dados de atividade.
>
> **Atividade:** imagine que você está vendo um trem passar. À medida que o trem passa, você vê apenas as ações realizadas pelos passageiros no momento em que o trem passa. Isso são os dados de atividade.
>
> <Image alt="activity_data.jpg" src="https://files.readme.io/70a37d5dc16f0817d137f9011be9af5360bd7c4d2469a8abf9430fe69b2671c3-360002436957.jpg" width="400px" />
>
> **LTV**: Agora imagine que você embarca no trem como um observador. O trem é dividido em vagões.
>
> * Você embarca no vagão com outros passageiros na estação. Isso é a instalação.
> * Durante a viagem, você observa todas as ações executadas pelos passageiros no vagão. Você pode ver as ações de todos os passageiros no vagão até que um passageiro desembarque do trem; isso é uma desinstalação.
> * Você não consegue ver as ações dos passageiros em outros vagões porque eles embarcaram no trem antes ou depois de você. Isso é o LTV.
>
> <Image alt="ltv_data.jpg" src="https://files.readme.io/78925644f263b6d5ea5630a09e0b2155d153ce2c4b3060be5c8d7cb9ba0ce4e6-360002436977.jpg" width="400px" />

### Dashboards e relatórios da AppsFlyer—LTV ou atividade?

O dashboard permite que os profissionais de marketing otimizem seu tráfego não orgânico. A maioria dos dashboards se baseia em LTV, pois os profissionais de marketing normalmente avaliam a performance com base em LTV. Todos os relatórios de dados agregados se baseiam em LTV e todos os relatórios de dados brutos se baseiam em atividade.

A tabela a seguir mostra quais dashboards e relatórios são de LTV e quais são de atividade.

| Fonte de dados | Tipo de dados |
| --- | --- |
| Dashboard de Visão Geral | Dados de LTV: 5 anos |
| Meus dashboards | Dados de LTV: 5 anos |
| Visão geral da SKAN | Dados de LTV: 5 anos |
| Instalações do Protect360 | Dados de LTV: 5 anos |
| Eventos in-app do Protect360 | atividade |
| Dashboard de atividades | atividade |
| Dashboard de eventos | Dados de LTV: 5 anos |
| Painel Personalizado | Dados de LTV: 5 anos |
| Retenção | Dados de LTV: 5 anos |
| Coorte | Dados de LTV: 5 anos |
| Relatórios de dados brutos | Dados de LTV: 5 anos |
| Relatório Retargeting | Atividade |
| Relatório Retargeting | Dados de LTV: 5 anos |
| Relatórios de prevenção de fraudes Protect360 | Atividade |
| Master API - KPIs de performance da campanha | Ambos |
| Tabela dinâmica | Ambos |

## Compare dados entre diferentes dashboards e relatórios

As seções a seguir explicam como você pode comparar dados entre diferentes dashboards e relatórios enquanto reduz e soluciona diferenças e discrepâncias nos dados.

<div id="compare-ltv-and-activity-data-in-appsflyer" />

<Accordion title="Comparar dados de LTV e de atividade na AppsFlyer">

Ao comparar dados da AppsFlyer, considere que há 2 diferenças a serem consideradas:

1. Os dados da atividade incluem eventos de **instalações que ocorreram antes** do intervalo de datas.
2. Os dados de LTV incluem **eventos que ocorreram após** o intervalo de datas.

Para comparar os dois tipos de dados corretamente, precisamos neutralizar as diferenças. Isso pode ser obtido recuperando dados de LTV dos dados da atividade ou vice-versa. **Atenção:** pequenas diferenças entre fontes semelhantes ainda podem ser observadas devido a diferenças no tempo de geração de relatórios.

#### Para recuperar dados de LTV a partir de dados brutos de atividade:

1. Na AppsFlyer, no menu lateral, selecione relatório > exportar dados brutos.
2. Defina o **dia atual como o último dia** do intervalo de datas (problema 2 resolvido)
3. Faça download do relatório de eventos in-app brutos.
4. Use a coluna **Install Time** (Tempo de instalação) para filtrar as instalações anteriores ao primeiro dia do intervalo de datas (problema 1 resolvido)

#### Para recuperar dados de atividade a partir de dados de LTV:

1. **Selecione fontes que começaram a enviar instalações dentro do intervalo de datas especificado na AppsFlyer** (problema 1 resolvido).  
   Isso garante que os dados da atividade não incluam eventos executados no intervalo de datas que pertence às instalações que ocorreram antes do intervalo de datas.
2. **Defina o dia atual como o último dia do intervalo de datas** (problema 2 resolvido).  
   Defina o **dia atual como o último dia** do intervalo de datas (problema 2 resolvido)  
   Isso garante que os dados LTV não incluam eventos executados após o intervalo de datas que pertence às instalações que ocorreram no intervalo de datas.

</Accordion>

<div id="compare-different-appsflyer-aggregated-data-dashboards-and-reports" />

<Accordion title="Compare diferentes dashboards e relatórios de dados agregados da AppsFlyer">

Ao comparar dados entre diferentes dashboards e relatórios de dados agregados da AppsFlyer, a diferença entre os dados de LTV vs. atividade pode ser um motivo para discrepâncias.

Se você estiver agregando dados por geo: nos dashboards da AppsFlyer, agregar por geo significa a geo onde a instalação ocorreu, enquanto nos relatórios de dados brutos, significa a geo onde o evento ocorreu.

No entanto, é importante destacar que podem haver outras razões para esse problema. <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">Para mais informações, veja a comparação dos métodos de relatórios agregados.</Anchor>

</Accordion>

<div id="compare-appsflyer-data-with-external-data" />

<Accordion title="Compare os dados da AppsFlyer com dados externos">

A grande maioria das fontes de dados, incluindo Google e Apple, exibe dados de atividade, que não são dados de LTV. Portanto, para comparar os dados de fontes externas com os dados da AppsFlyer, você normalmente usaria os dados de atividade da AppsFlyer, disponíveis nos relatórios de dados brutos.

Considere que o Meta ads oferece dados de LTV parciais, limitados a 28 dias após a instalação.

Podem haver outros motivos para discrepâncias entre os dados da AppsFlyer e dados externos. Veja também:

* <Anchor target="_blank" href="/marketers/pt/docs/google-analytics-integration-discrepancies">Discrepâncias do Google Analytics</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-discrepancies">Discrepâncias do Meta Ads</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/snapchat-integration-discrepancies">Discrepâncias do Snapchat</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-faq-and-discrepancies">Discrepâncias do Google Ads</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies">Discrepâncias do X Ads</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/attribution-discrepancies-between-tiktok-for-business-and-appsflyer">Discrepâncias do TikTok</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/resolve-appsflyer-app-stores-discrepancies">Discrepâncias da loja de aplicativos</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/discrepancies-between-appsflyer-and-third-party-platforms">Discrepâncias de plataformas de terceiros</Anchor>

</Accordion>

<div id="compare-inapp-event-raw-data-with-the-activity-view" />

<Accordion title="Compare os dados brutos de eventos in-app com a visualização de atividade">

Os eventos in-app aparecem tanto no LTV quanto na visualização de atividade no dashboard. No entanto, cada um usa uma lógica de contagem diferente.  
Ao reconciliar contagens de eventos com dados brutos, compare-as sempre com o dashboard de atividade ou com a visualização de atividade em My Dashboards, pois essas visualizações representam as ocorrências de eventos no dia em que ocorreram.

As diferenças geralmente surgem quando os dados brutos não são filtrados corretamente, especialmente para eventos de retargeting.

#### **Reconciliar dados brutos com métricas de eventos de atividade**

Para comparar os totais de eventos in-app:

1. **Extraia os relatórios de dados brutos necessários:**

* Eventos in-app não orgânicos
* Eventos in-app relacionados ao retargeting
* Eventos orgânicos in-app

2. **Filtre eventos de retargeting para evitar contagem dupla.**  
   Em cenários de retargeting, ocorre atribuição dupla. Um evento in-app será atribuído a ambos:

* O canal de mídia de retargeting (**atribuição primária**)
* O canal de mídia que impulsionou a instalação original (**atribuição secundária**)

Para evitar contar o mesmo evento duas vezes nos seus relatórios, filtre o campo **Is primary attribution = True** nos seus dados brutos.  
Aplique esse filtro antes de agregar os relatórios de UA para que apenas a instância de atribuição primária seja incluída. Isso evita que eventos duplicados de retargeting inflem os totais.

3. **Agregue os totais de eventos.**  
   Some os eventos entre os conjuntos filtrados.
4. **Compare o total agregado** com a contagem de eventos exibida no **dashboard de atividade**.

</Accordion>

<div data-zendesk-anchors="ltv-vs-activity=sobre-diferen%C3%A7as-e-discrep%C3%A2ncias-de-dados h_01HKA0R42YZMAM5Y20B7T2JCDZ=sobre-diferen%C3%A7as-e-discrep%C3%A2ncias-de-dados h_01J5WGZ13WPMNSB1NA0SMA77WJ=ltv-vs-atividade ltv-data=dados-de-ltv h_01HKA0R42YQ2CJS67MDQSJHKEW=dados-de-ltv activity-data=dados-de-atividade h_01HKA0R42Y987PJRM70M7DFJ98=dados-de-atividade h_01J5WGZ13W5W8NJ1CRZQPHY939=analogia-do-trem appsflyer-dashboards%E2%80%94ltv-or-activity=dashboards-e-relat%C3%B3rios-da-appsflyerltv-ou-atividade h_01HKA0R42Y558BQ45Y9MFZHZM0=dashboards-e-relat%C3%B3rios-da-appsflyerltv-ou-atividade compare-data-between-different-dashboards-and-reports=compare-dados-entre-diferentes-dashboards-e-relat%C3%B3rios h_01J5WKA06A7XYFN07V60VQ4FY5=compare-dados-entre-diferentes-dashboards-e-relat%C3%B3rios h_01J5WHVQSNEA2WK83RBRDM1GT3=compare-ltv-and-activity-data-in-appsflyer retrieving-ltv-data-out-of-raw-activity-data=para-recuperar-dados-de-ltv-a-partir-de-dados-brutos-de-atividade h_01HKA0R42Z3ZSMEM7T5F0V3VM7=para-recuperar-dados-de-ltv-a-partir-de-dados-brutos-de-atividade retrieving-activity-data-out-of-ltv-data=para-recuperar-dados-de-atividade-a-partir-de-dados-de-ltv h_01HKA0R42ZHFM4RHG78GE51XK3=para-recuperar-dados-de-atividade-a-partir-de-dados-de-ltv h_01J5WK0AEN2N6J4P06CC3DMWPJ=compare-different-appsflyer-aggregated-data-dashboards-and-reports h_01J5WHVQSNZW66CQ4VGQGAKZB1=compare-appsflyer-data-with-external-data h_01KCNZWKFAWQ3KBJPCXP4BP8RM=compare-inapp-event-raw-data-with-the-activity-view reconcile-raw-data-with-activity-event-metrics=reconciliar-dados-brutos-com-m%C3%A9tricas-de-eventos-de-atividade h_01KCNZXRJKTGPH104H5Y1QNTM9=reconciliar-dados-brutos-com-m%C3%A9tricas-de-eventos-de-atividade" />

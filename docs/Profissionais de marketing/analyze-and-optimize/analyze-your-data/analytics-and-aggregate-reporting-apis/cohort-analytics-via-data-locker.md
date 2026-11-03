---
title: Cohort analytics no Data Locker
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2021-10-14T08:46:00Z'
  edited_at: '2026-08-19T00:02:46Z'
  id: 4408945472529
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/4408945472529
---
> **Em resumo**: a análise de coortes no Data Locker contém Dados agregados de todos os elementos da hierarquia de publicidade. Os relatórios incluem dados de usuários atribuídos nos últimos 365 dias. Eles estão disponível para anunciantes que têm dados brutos, a Cohort API, ou ambos, como parte da sua assinatura. Ou seja, não é necessária uma assinatura do Data Locker para acessar os relatórios.

## Cohort analytics no Data Locker

Em alguns casos, os dados brutos de atribuição na AppsFlyer são <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">restritos</Anchor> por conta das políticas de compartilhamento de dados de fontes de mídia ou por conta das suas <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">políticas de proteção à privacidade.</Anchor> As restrições afetam campos relacionados à atribuição, como campanha e adset. Os relatórios de cohort oferecem dados agregados que podem ser usados como alternativa aos dados brutos.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ8q_4xv83wHkl4fs6jndEffRu-RHsPobBRfxDG-bUNXb0pOnvJH4QT0nXKdWvi3JPtVUBegTFbxIEe/pub?output=xlsx">Baixar relatório de exemplo</Anchor>

<div id="enable-data-locker" />

<Accordion title="Ativar Data Locker">

O relatório está disponível para assinantes do Data Locker, Cohort API e dados brutos. Para ativar o relatório no <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker,</Anchor> use um dos procedimentos abaixo.

| Atualmente, você recebe dados através do Data Locker? | Procedimento |
| --- | --- |
| Sim | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Para adicionar relatórios de cohort ao Data Locker:<ol><li>Na AppsFlyer, a partir do menu lateral, selecione **Relatório > Data Locker**.</li><li>Selecione todos os relatórios na seção **Análise de cohort.**</li><li>Clique em **Salvar configuração**.<br />Os relatórios estarão disponíveis no dia seguinte, às 10:00 UTC.</li></ol> |
| Não | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**Para configurar o Data Locker**:<ol><li>Conclua a configuração inicial do Data Locker (<Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#set-up-data-locker">anunciante</Anchor> \| <Anchor target="_blank" href="/partners/pt/docs/data-locker-for-partners">parceiro</Anchor>).</li><li>Adicione os relatórios de cohort ao Data Locker:<ol><li>Na AppsFlyer, a partir do menu lateral, selecione **Relatório > Data Locker**.</li><li>Selecione todos os relatórios na secção **Análise de cohort**.</li><li>Clique em **Salvar configuração**.<br />Os relatórios estarão disponíveis no dia seguinte, às 10:00 UTC.</li></ol></li></ol> |

</Accordion>

Você pode carregar os dados em seus sistemas de BI e usá-los como parte de seus processos de otimização de campanhas e performance.

**Métricas disponíveis**

As métricas disponíveis são a receita, os usuários que executam um evento e o número de ocorrências do evento. Para calcular métricas relacionadas a custos, como ROI e ROAS, são necessárias métricas de receita e custo. As métricas de receita estão em Cohort e as métricas de custo são fornecidas pelo <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL.</Anchor>

<div id="facts" />

<Accordion title="Informações sobre cohort analytics">

| Relatórios disponíveis | Os relatórios a seguir estão disponíveis para download. Os tipos de relatório estão descritos com mais detalhes no <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard#cohort-principles">dashboard Cohort</Anchor>.<ul><li>**Aquisição de usuários:** atribuída a uma fonte de mídia de aquisição de usuários, incluindo dados LTV, sendo que a aquisição ocorre durante as janelas de reengajamento.</li><li>**Retargeting:** atribuído a uma fonte de mídia de retargeting para eventos que ocorrem:<ul><li>Durante uma janela de reengajamento</li><li>Como resultado de reatribuições</li></ul></li><li>**Unificado:** exibe dados sob o canal de mídia que recebeu o último toque e que trouxe o usuário de acordo com as regras de <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">atribuição dupla</Anchor> da AppsFlyer. Isso significa que o LTV que ocorre durante os reengajamentos é exibido sob o canal de mídia de retargeting e não sob o canal de mídia da aquisição de usuários (UA).</li></ul> |
| --- | --- |
| Período coberto pelo relatório | Usuários que converteram nos últimos 365 dias. Ou seja, a cada dia, os relatórios incluem eventos de usuários que converteram nos últimos 365. |
| Estrutura do relatório | O esquema de cada relatório (as dimensões e métricas incluídas) é fixo e não pode ser alterado. Consulte a [estrutura do relatório](/docs/cohort-analytics-via-data-locker#report-structure). |
| Entrega do relatório | Consulte [Ativar relatórios de cohort no Data Locker](/docs/cohort-analytics-via-data-locker#enable-data-locker). |
| Atualização dos dados | <ul><li>Diariamente.</li><li>As métricas são calculadas usando os dados disponíveis à meia-noite UTC. Ou seja, no final do dia.</li><li>Os relatórios estão disponíveis no Data Locker na pasta date-time (dt) às 10:00 UTC. Por exemplo, os dados de segunda-feira estão disponíveis na terça-feira às 10:00 UTC na pasta de Monday.</li></ul> |
| Impacto das políticas de retenção de parceiros | Alguns parceiros possuem uma política de retenção de dados. Nesse caso, os eventos que ocorrem após o término do período de retenção não são considerados nos relatórios de cohort.<br /><br />Exemplo: A SRN A tem uma política de retenção de dados de 180 dias. Eventos de usuário até o dia 180 são atribuídos à SRN A. Eventos que ocorrem após 180 dias são desconsiderados. |

</Accordion>

<div id="report-structure" />

<Accordion title="Estrutura do relatório">

O relatório é composto por dimensões e métricas.

O formato dos campos é o seguinte:

* **Dimensões**: String. O comprimento máximo da string é dinâmico e, na maioria dos casos, depende de como se preenchem os elementos da hierarquia publicitária.
* **Métricas**: Número. **Atenção:** O formato do campo selected\_currency é uma string.

#### Dimensões

<Table>
  <thead>
    <tr>
      <th>
        Nome do campo
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        conjunto\_de\_anúncios
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        fonte\_de\_mídia
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        tipo\_de\_conversão
      </td>
      <td>
        Valores possíveis: install, install\_unified (representando instalações no relatório unificado), re-engagement, re-attribution
      </td>
    </tr>
    <tr>
      <td>
        tipo\_de\_toque\_atribuído
      </td>
      <td>
        Valores possíveis: click, impressions, pre-install, unknown, tv, null
      </td>
    </tr>
    <tr>
      <td>
        dias\_após\_atribuição
      </td>
      <td>
        * O número de dias decorridos desde a data da conversão (não o carimbo de data/hora específico da conversão).
        * Dica! Use isso para calcular os dias de retenção e de KPI.
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * A data em que um usuário executa um determinado evento.
        * Formato: aaaa-mm-dd
        * Exemplo: A data em que um usuário executou um determinado evento no aplicativo. No caso de uma conversão.
        * Atenção! Se o event\_name for af\_conversion, a data do evento e a data de conversão serão as mesmas.
      </td>
    </tr>
    <tr>
      <td>
        data\_da\_conversão
      </td>
      <td>
        * A data em que a conversão ocorreu.
        * Formato: aaaa-mm-dd
        * Exemplo: A data de instalação.
      </td>
    </tr>
    <tr>
      <td>
        nome\_do\_evento
      </td>
      <td>
        Identifica o evento. Alguns nomes de eventos têm um significado específico, enquanto outros se relacionam com eventos in-app definidos pelo anunciante no aplicativo. 

        | nome\_do\_evento | O que o usuário fez |
        | --- | --- |
        | af\_conversion | Usuário convertido. Use conversion\_type para identificar se é uma instalação, reengajamento ou reatribuição. |
        | af\_sessão | Abriu o aplicativo |
        | coorte\_desinstalações | Desinstalou o aplicativo |
        | Anunciante definiu evento in-app | Realizou um evento in-app. |
      </td>
    </tr>
    <tr>
      <td>
        Twitter
      </td>
      <td>
        Hierarquia da campanha

        Lembre-se: Não é possível alterar o nome da campanha. Consequentemente, vários nomes podem ser associados a um determinado ID de campanha.
      </td>
    </tr>
    <tr>
      <td>
        id\_da\_campanha
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        conjunto\_de\_anúncios
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        id\_conjunto\_de\_anúncios
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        Anúncio
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        id\_anúncio
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        Canal
      </td>
      <td>
        Hierarquia da campanha.

        [Atualizado em 27 de outubro de 2021] No momento, o Meta ads não preenche o canal através de dados fornecidos por meio do mecanismo Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        id\_do\_site
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        é\_atribuição\_primária
      </td>
      <td>
        Use para identificar e desduplicar dados de retargeting
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        O código de país ISO derivado do endereço IP do usuário.
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        * Transparência da agência suportada.
        * No caso de agências não transparentes, podem existir várias linhas com o mesmo nome de campanha se o anunciante e a agência executarem campanhas com o mesmo nome. Não se preocupe. As linhas não são duplicadas.
      </td>
    </tr>
    <tr>
      <td>
        instalar\_app\_store
      </td>
      <td>
        Somente aplicativos Android: A loja Android de onde o aplicativo foi baixado. Preenchido por anunciantes implementando a <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">multi-store attribution do Android</Anchor>. Se estiver em branco, significa que é a Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        keywords
      </td>
      <td>
        Palavra(s) usada(s) na pesquisa online do usuário. Conforme relatado pela ad network
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        [Disponível a partir de 27 de abril de 2022] Keyword ID retornado pela ad network.
      </td>
    </tr>
  </tbody>
</Table>

#### Métricas

| Nome do campo | Descrição | Formato |
| --- | --- | --- |
| utilizadores\_únicos | Número de usuários que executam o evento. | Número |
| receita\_usd | <ul><li>Valor da receita em USD. Por exemplo, US$100,56 são refletidos como 100,56.</li><li>Máximo de 2 dígitos após a vírgula decimal.</li></ul> | Número |
| contagem\_de\_eventos | Número de ocorrências de eventos. | Número |
| moeda\_selecionada | Código de moeda de 3 letras (USD, EUR) definido por você nas configurações do aplicativo. Formato <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. Essa é a mesma moeda usada para exibir a receita no dashboard de Cohort, na interface do usuário. | Sequência de caracteres |
| receita\_moeda\_selecionada | <ul><li>Valor da receita na moeda selecionada. Por exemplo, se a moeda selecionada for EUR, então €1234,56 é refletido como 1234,56</li><li>Máximo de 2 dígitos após a vírgula decimal.</li></ul> | Número |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="Considerações para desenvolvedores de BI">

**Escopo dos dados no relatório**

Os relatórios contêm instalações de aquisição de usuários, reatribuições de retargeting e reengajamentos, além dos seus eventos in-app relacionados.

Você pode carregar relatórios unificados, de aquisição de usuários e de retargeting separadamente ou de uma só vez em seu sistema de BI. Se você carregá-los juntos e quiser filtrar as exibições por conta própria:

* Para dados unificados, is\_primary\_attribution=true ou null field.
* Para aquisição de usuários, use conversion\_type=Install
* Para retargeting, use conversion\_type=re-engagement ou re-attribution.

Se você usar apenas a exibição unificada em seu processo de carregamento de dados, poderá dividir os dados entre os tipos de campanha, ou seja, atribuição de usuário (instalações) e retargeting (reengajamentos). Para fazer isso, use o conversion\_type=install, install-unified, re-engagement ou re-attribution. Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">atribuição dupla de eventos de retargeting.</Anchor>

**Considerações a nível de campo**

* Use dias pós-atribuição para permitir o cálculo fácil das métricas de retenção.
* Cálculo de usuários únicos usando as dimensões de nome de campanha e ID de campanha: Se puder desconsiderar a granularidade do nome da campanha, você pode somar a contagem única no ID da campanha, e as métricas estarão corretas.
* Você pode agregar os dados usando os campos de hierarquia da campanha.
* A receita está em USD e é calculada usando a taxa de câmbio no dia do evento.
* Eventos de receita de anúncios são incluídos quando disponíveis, mas são atualizados com um atraso de até 3 dias.

**Considerações gerais**

Todos os dados do aplicativo são fornecidos em um único arquivo. Use o campo App ID para separar dados por aplicativo ou defina o Data Locker para segregar por aplicativo.

</Accordion>

<div id="use-cases" />

<Accordion title="Casos de uso">

A seguir estão exemplos de alguns usos práticos dos dados via Data Locker. Cada exemplo é ilustrado por uma instrução SQL e um exemplo visual em Excel.

#### **1. Calculando a retenção**

No exemplo seguinte, realizamos as seguintes ações:

* Calculamos a retenção do Dia 1 e do Dia 7, bem como o número total de instalações por campanha e anúncio.
* Somamos a contagem de eventos por evento de conversão filtrando `event_name`para que seja `af_conversion`.
* Mais especificamente, analisamos as campanhas de aquisição de usuários no relatório Unificado, filtrando os dados para que `conversion_type IN (install, install_unified)`.

**Instrução SQL**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and app_id = YOUR_APP
group by 1,2
```

**Exemplo Excel**

| ID da campanha | ID do anúncio | Instalações | Retenção Dia 1 | Retenção Dia 7 |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | 15% |
| 07315466 | 613770 | 300 | 20% | 12% |

#### **2. Calculando o ARPU de múltiplos eventos in-app**

No exemplo a seguir, nós:

* Calculamos o ARPU de múltiplos eventos in-app por campanha.
* Analisamos especificamente as campanhas de retargeting, filtrando os dados de modo que `conversion_type=re-engagement` e `conversion_type=re-attribution`.
* Somamos a contagem de eventos por evento de conversão filtrando `event_name`para que seja `af_conversion`.
* Somamos a receita de múltiplos eventos, nesse caso `af_purchase`e `af_coins`.
* Configuramos `days_post_attribution` como o mínimo necessário (nesse caso, 7) para reduzir a carga de processamento de dados.

**SQL**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Exemplo Excel**

| ID da campanha | Tipo de conversão | OPCIONAL<br /><br />Dia 1 | OPCIONAL<br /><br />Dia 3 | OPCIONAL<br /><br />Dia 7 |
| --- | --- | --- | --- | --- |
| 12345678 | re-engajamento | 6.23 | 5.11 | 2.34 |
| 98765432 | re-engajamento | 3.57 | 1.34 | 4.86 |
| 07315466 | reatribuição | 7.41 | 6.79 | 5.29 |

#### **3. Calculando a taxa de conversão de eventos in-app para um dia de cohort específico**

No exemplo a seguir, nós:

* Calculamos a taxa de conversão de eventos in-app no Dia 0 para várias dimensões (nesse caso, data de conversão, localização geográfica, campanha, anúncio e site ID).
* Analisamos dados unificados (campanhas de UA e de retargeting) filtrando-os para que `is_primary_attribution=true`.
* Somamos a contagem de eventos por evento de conversão filtrando `event_name`para que seja `af_conversion`.
* Configuramos `days_post_attribution` como o mínimo necessário (nesse caso, 7) para minimizar a carga de processamento de dados.

**SQL**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary_attribution = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Exemplo Excel**

| Data de conversão | Geolocalização/país | ID da campanha | ID do anúncio | ID do site | Dia 0 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | EUA | 12345678 | 123456 | site\_123 | 45% |
| 2022-11-05 | Reino Unido | 98765432 | nulo | site\_654 | 70% |
| 2022-10-31 | KR | 07315466 | nulo | nulo | 63% |

#### **4. Calculando instalações diárias**

No exemplo a seguir, nós:

* Calculamos o número de instalações por App ID, data de conversão, fonte de mídia, nome do evento e tipo de conversão.
* No relatório unificado, filtre os dados para mostrar instalações de UA (não retargeting) configurando `conversion_type` para `install` ou `install_unified`.
* Some as instalações, configurando `event_name`para que seja `af_conversion`.

**SQL**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // Se você estiver consultando dados de relatórios unificados, edite a linha abaixo para: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Exemplo Excel**

| ID da aplicação | Data de conversão | Fonte de mídia | Nome do evento | Total |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

#### **5. Calculando a receita de anúncios do Facebook Ads**

No exemplo seguinte, realizamos as seguintes ações:

* Calculamos a receita do Dia 3 do Facebook Ads, com base na data de conversão e app ID.
* Analisamos os dados do Facebook filtrando os dados para que `media_source='Facebook Ads'`.
* Configuramos `days_post_attribution` como o mínimo necessário (nesse caso, 3) para minimizar a carga de processamento de dados.

**SQL**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
group by 1,2,3
group by 1,2,3
```

**Exemplo Excel**

| Data de conversão | ID da aplicação | Fonte de mídia | Resultados<br /><br />Dia 3 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400.45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99.23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13.34 |

#### **6. Calculando o ARPU por ASA keyword ID até 365 dias de cohort**

No exemplo seguinte, realizamos as seguintes ações:

* Calculamos o ARPU do Apple Search Ads por keyword ID até o dia 365 do cohort.
* Analisamos os dados do Apple Search Ads filtrando-os de modo que `media_source='Apple Search Ads'`.
* Somamos a contagem de eventos por evento de conversão filtrando `event_name`para que seja `af_conversion`.

**SQL**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Exemplo Excel**

| Fonte de mídia | ID da palavra-chave | OPCIONAL<br /><br />Dia 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57.019,93 |
| adnet2\_int | 987654 | 64.867,84 |
| adnet3\_int | 666854 | 48.160,02 |

#### **7. Cálculo do ARPU Dia 7 por tempo de atribuição para cada área geográfica**

O exemplo seguinte ilustra como usar <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">KPIs por tempo de atribuição</Anchor>. Nesse exemplo, nós:

* Calculamos o ARPU D7 por data de atribuição para cada área geográfica.
* Os resultados foram classificados pelo número de conversões, exibindo as 20 principais regiões geográficas.
* Os dados foram filtrados de maneira que `conversion_type='install'`.
* A primeira coluna mostra a área geográfica. A segunda coluna mostra o total de conversões. As colunas seguintes mostram a receita dos 7 dias para cada dia especificado como uma linha na consulta.

**SQL**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    // Se você estiver consultando dados de relatórios unificados, edite a linha abaixo para: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Exemplo Excel**

| Geolocalização/país | Total de conversões | ARPU Dia 7 para 2023-07-11 | ARPU Dia 7 para 2023-07-12 | ARPU Dia 7 para 2023-07-13 | ARPU Dia 7 para 2023-07-14 | ARPU Dia 7 para 2023-07-15 | ARPU Dia 7 para 2023-07-16 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Coreia do Sul | 120.660 | US$ 7.798,89 | US$ 6.997,37 | US$ 8.258,95 | US$ 9.050,21 | US$ 10.018,04 | US$ 13.765,73 |
| Canadá | 35.099 | US$ 64.867,84 | US$ 7.050,19 | US$ 5.656,33 | US$ 9.553,75 | US$ 8.632,41 | US$ 11.308,06 |
| Chile | 26.750 | US$ 48.160,02 | US$ 21.249,55 | US$ 22.584,57 | US$ 24.033,07 | US$ 31.118,91 | US$ 41.145,22 |

</Accordion>

## Informações adicionais

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística |  |
| --- | --- |
| Dados de custo | <ul><li>Indisponível. <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">Use o Cost ETL</Anchor>.</li><li>Veja também <Anchor target="_blank" href="/marketers/pt/docs/combine-cost-etl-and-cohort-reports-via-data-locker">combinar o Cost ETL com relatórios de cohort</Anchor>.</li></ul> |
| Mudanças no nome da campanha | Sem suporte. |
| Atualização dos dados | Diário UTC. Os relatórios estão na pasta de date-time (dt) do Data Locker do dia de extração do relatório até as 10:00 UTC do dia seguinte. |
| Receita de anúncios | <ul><li>Disponível.</li><li>Para eventos af\_ad\_revenue, a métrica de usuários únicos não está disponível para as datas entre 5 de outubro de 2022 e 16 de fevereiro de 2023.</li></ul> |
| Moeda | USD e moeda específica do aplicativo estão disponíveis por linha. |
| Fuso horário | <ul><li>UTC</li><li>O fuso horário específico do aplicativo está disponível no <Anchor target="_blank" href="/marketers/pt/docs/advanced-aggregated-reports-in-data-locker">Relatório avançado versionado por fuso horário de cohort agregado</Anchor>.</li></ul> |
| Dados orgânicos | Disponível. |
| Dias após conversão (instalação, reatribuição, reengajamento) | <ul><li>365 dias de dados pós-instalação estão disponíveis.</li><li>Estão disponíveis 1.095 dias com <Anchor target="_blank" href="/marketers/pt/docs/advanced-aggregated-reports-in-data-locker">relatórios avançados agregados</Anchor>.</li></ul> |
| Transparência das agências | <ul><li>Com suporte.</li><li>Os dados do X Ads e Meta Ads são sempre transparentes.</li></ul> |
| Segregação de aplicativos | Com suporte. |
| Dados SKAN | Não incluído. Ou seja, os dados fornecidos pelos postbacks do iOS não estão incluídos. |
| Reinstalações | <ul><li>Se os eventos pós-reinstalação forem considerados orgânicos não atribuídos:<ul><li>Eles estão incluídos somente a partir de 26 de maio de 2024. <Anchor target="_blank" href="/marketers/pt/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Saiba mais</Anchor></li><li>O tempo de instalação se baseia no campo <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>Não são contabilizados para mensurações de usuários únicos e de retenção.</li></ul></li><li>Se os eventos pós-reinstalação forem atribuídos na primeira instalação, os dados sempre são incluídos. <Anchor target="_blank" href="/marketers/pt/docs/unique-users">Saiba mais</Anchor></li></ul> |

</Accordion>

> 📄 **Ver também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Combinar Cost ETL e relatórios de cohort</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">Dashboard de cohort</Anchor>

<div data-zendesk-anchors="cohort-analytics-in-data-locker=cohort-analytics-no-data-locker 01H7WG3CA1DDAN79D1PBPE0RJ3=cohort-analytics-no-data-locker 01H7WG3CA1ZMNTGZ5B8FNXNC4A=enable-data-locker 01H7WG3CA179D6VCWYPCJ1G49M=facts 01H7WG3CA1R3PZCKSGWC90E7RC=report-structure dimensions=dimens%C3%B5es 01H7WG3CA14PQ2PJ58FX8TE6ZH=dimens%C3%B5es metrics=m%C3%A9tricas 01H7WG3CA24VQKFVP99S82GCXZ=m%C3%A9tricas 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-calculating-retention=1-calculando-a-reten%C3%A7%C3%A3o h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-calculando-a-reten%C3%A7%C3%A3o 2-calculating-arpu-of-multiple-inapp-events=2-calculando-o-arpu-de-m%C3%BAltiplos-eventos-in-app h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-calculando-o-arpu-de-m%C3%BAltiplos-eventos-in-app 3-calculating-inapp-event-conversion-rate-for-a-specific-cohort-day=3-calculando-a-taxa-de-convers%C3%A3o-de-eventos-in-app-para-um-dia-de-cohort-espec%C3%ADfico h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-calculando-a-taxa-de-convers%C3%A3o-de-eventos-in-app-para-um-dia-de-cohort-espec%C3%ADfico 4-calculating-daily-installs=4-calculando-instala%C3%A7%C3%B5es-di%C3%A1rias h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-calculando-instala%C3%A7%C3%B5es-di%C3%A1rias 5-calculating-revenue-from-facebook-ads=5-calculando-a-receita-de-an%C3%BAncios-do-facebook-ads h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-calculando-a-receita-de-an%C3%BAncios-do-facebook-ads 6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-calculando-o-arpu-por-asa-keyword-id-at%C3%A9-365-dias-de-cohort h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-calculando-o-arpu-por-asa-keyword-id-at%C3%A9-365-dias-de-cohort calculating-arpu-days-0-7-by-attribution-time-per-geo=7-c%C3%A1lculo-do-arpu-dia-7-por-tempo-de-atribui%C3%A7%C3%A3o-para-cada-%C3%A1rea-geogr%C3%A1fica 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-c%C3%A1lculo-do-arpu-dia-7-por-tempo-de-atribui%C3%A7%C3%A3o-para-cada-%C3%A1rea-geogr%C3%A1fica additional-information=informa%C3%A7%C3%B5es-adicionais 01H7WG3CA255TG9HW150RW1QTX=informa%C3%A7%C3%B5es-adicionais 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=ver-tamb%C3%A9m" />

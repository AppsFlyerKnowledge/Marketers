---
title: Como alterar as configurações de fuso horário do aplicativo
metadata:
  keywords:
    - Time Zone
    - Existing Apps
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2017-01-12T15:33:00Z'
  edited_at: '2026-08-19T00:17:09Z'
  id: 115000306786
  locale: pt
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/pt/articles/115000306786
---
> **Visão geral:** defina ou altere um fuso horário específico do aplicativo para visualizar os dados do aplicativo mais alinhados com seu fuso horário ou com o de seus parceiros de publicidade. Entenda o efeito das mudanças de fuso horário nos relatórios de dados na plataforma da AppsFlyer.

<div id="why-change-the-time-zone" />

## Por que alterar o fuso horário?

O fuso horário padrão para novos aplicativos é UTC (UTC +0). Se o fuso horário do aplicativo for alterado, isso afetará a forma como os dados aparecem na plataforma.

* **Cenário:** você trabalha em um fuso horário que não é UTC. However, you want app data aligned to your time zone or to the time zone you selected with other partners like Facebook and Google.
* **Objetivo:** simplificar as comparações de dados entre a AppsFlyer e outras networks.
* **Solução:** alinhe o fuso horário na plataforma da AppsFlyer com o dos outros provedores de serviços que você usa. O horário de verão é ajustado automaticamente por padrão (não configurável).

**Agências e ad networks**:

* Agências: visualize os dados usando o fuso horário definido pelo proprietário do aplicativo. As agências não podem definir o fuso horário.
* Ad networks: visualize dados usando UTC em todos os momentos, independentemente do fuso horário definido pelo anunciante.

<div id="changing-the-time-zone" />

## Alterando o fuso horário

The account admin can make time-zone changes. As alterações podem ser feitas uma vez a cada 48 horas. As configurações de alteração de fuso horário ficam indisponíveis nas 48 horas após uma alteração anterior.

**Para alterar o fuso horário do aplicativo:**

1. In AppsFlyer, go to **Configuration** > **App settings**.
2. In **Localization** > **Time Zone**, select **UTC**.
3. Clique em **Salvar configurações** e aguarde 48 horas.
4. Go to **Configuration** > **App settings**.
5. Em **Localização** > **Fuso horário** > selecione um fuso horário (por cidade/país).
6. Clique em **Salvar configurações**.  
   A mudança entra em vigor no início do dia seguinte às 00:00 UTC.

<div id="example" />

> 📄 **Exemplo**
>
> * October 24 at 22:00, the time zone is changed.
> * Em 25 de outubro às 00:00 UTC, a alteração entra em vigor.

Depois de alterar o fuso horário:

* O fuso horário usado na apresentação dos dados depende do período e do método do relatório, conforme detalhado nas tabelas a seguir.
* Os relatórios agregados terão algumas anomalias no dia e no dia seguinte à alteração do fuso horário.
  * Cost data is duplicated on the day of the change.

<div id="aggregate-data" />

#### Dados agregados

<table><thead><tr><th rowspan="2">Método de relatório </th><th colspan="3">Intervalo de datas do relatório</th></tr><tr><th>Começa e termina <span>antes</span> da alteração </th><th>Começa e termina <span>após</span> a alteração </th><th>Começa antes e termina após a alteração</th></tr></thead><tbody><tr><td>Meus dashboards</td><td><p>Não compatível Não compatível Os dados ficam disponíveis somente em UTC quando o fuso horário do dashboard é alterado.</p></td><td>Fuso horário atual</td><td>Os dados são apresentados somente para datas após a alteração.</td></tr><tr><td>Painel de Visão geral</td><td>Fuso horário anterior</td><td>Fuso horário atual</td><td><p>Divisão:</p><ul><li>Antes da alteração: UTC</li><li>Após a alteração: fuso horário atual</li></ul></td></tr><tr><td>Eventos e painéis personalizados</td><td>UTC</td><td>Fuso horário atual</td><td><p>Divisão:</p><ul><li>Antes da alteração: UTC</li><li>Após a alteração: fuso horário atual</li></ul></td></tr><tr><td>Painel de atividades</td><td>Fuso horário anterior</td><td>Fuso horário atual</td><td>UTC</td></tr><tr><td>Coorte, retenção, tabela dinâmica</td><td>UTC</td><td>Fuso horário atual (1)</td><td>UTC</td></tr><tr><td>Master API</td><td colspan="3"><ul><li>Predefinição: UTC</li><li>Option: <a href="./pull-api-aggregate-data#aggregate-report-uri-and-parameters" target="_blank">Select the time zone when you pull data</a> </li></ul></td></tr><tr><td colspan="4">Observações:<br/>(1) Todos os aplicativos devem usar o mesmo fuso horário específico do aplicativo em um determinado período de relatórios. Caso contrário, o fuso horário será revertido para UTC.</td></tr></tbody></table>

<div id="raw-data-reports" />

#### Relatórios de dados brutos

<table><thead><tr><th rowspan="2">Método de relatório </th><th colspan="3">Intervalo de datas do relatório</th></tr><tr><th>Começa e termina <span>antes</span> da alteração </th><th>Começa e termina <span>após</span> a alteração </th><th>Começa antes e termina após a alteração</th></tr></thead><tbody><tr><td>Página de exportação de dados brutos</td><td>Fuso horário atual</td><td>Fuso horário atual</td><td>Fuso horário atual</td></tr><tr><td>API de push</td><td colspan="3">Campos separados para UTC e o fuso horário específico do aplicativo calculado usando o fuso horário selecionado no momento do evento.</td></tr><tr><td>Extrair API</td><td colspan="3"><ul><li>Predefinição: UTC</li><li>Option: <a href="./pull-api-aggregate-data#aggregate-report-uri-and-parameters" target="_blank">Select the time zone when you pull the data</a> </li></ul></td></tr><tr><td>Relatório do Data Locker</td><td colspan="3">Not impacted - date fields are in UTC</td></tr></tbody></table>

<div data-zendesk-anchors="why-change-the-time-zone=por-que-alterar-o-fuso-hor%C3%A1rio h_01HJR69P6Z44SZA5A684H82PNV=por-que-alterar-o-fuso-hor%C3%A1rio changing-the-time-zone=alterando-o-fuso-hor%C3%A1rio h_01HJR69P6ZWJQ47FQY2HATAAE3=alterando-o-fuso-hor%C3%A1rio h_01HJR69P6Z6B0Q6E6996WXVZ0N=exemplo aggregate-data=dados-agregados h_01HJR69P6ZY8JJBCBSDZKN75N6=dados-agregados raw-data-reports=relat%C3%B3rios-de-dados-brutos h_01HJR69P6ZDXXK8ZTKK3E774VJ=relat%C3%B3rios-de-dados-brutos" />

---
title: Relatório de conversões multiplataforma
metadata:
  keywords:
    - Marketers
    - Data Locker
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Data Locker
    - Cross-Platform Measurement
  created_at: '2026-09-02T07:11:54Z'
  edited_at: '2026-10-20T03:53:57Z'
  id: 50451304393617
  locale: pt
  section: Cross platform reports
  section_id: 50467263168657
  url: https://support.appsflyer.com/hc/pt/articles/50451304393617
---
> **At a glance:** O relatório de conversões multiplataforma mostra a jornada completa do usuário por trás de cada conversão multiplataforma, incluindo toda a cadeia completa de engajamento de assistência e o contexto de receita — não apenas o último touchpoint.

<div id="about-the-report" />

## Sobre o relatório

O relatório de conversões multiplataforma é um relatório de dados brutos que fornece registros de conversão no nível do usuário, vinculados entre plataformas usando seu <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/set-customer-user-id">Customer User ID (CUID)</Anchor>. Isso permite analisar a jornada completa do usuário que levou a uma conversão, não apenas o último touchpoint.

Para mais informações sobre o fluxo e a configuração da atribuição baseada em usuário, acesse <Anchor target="_blank" href="/marketers/pt/docs/beta-user-based-cross-platform-attribution">atribuição cross-platform baseada em usuário</Anchor>.

<div id="report-fields" />

## Campos do relatório

Para saber quais campos estão contidos no relatório, faça o <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRTFg6HXtHNYwegAjMysjybPbRk4IO8uflwvbGvR_xb11BcCrCWQ7i3xZD_Y2iiYSsx_MjTPN0E_Bmk/pub?gid=670907846&single=true&output=csv">download de um exemplo de relatório</Anchor>.

Ele inclui todos os campos do relatório e seus valores. Para as definições dos campos, acesse <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">o dicionário de campos</Anchor>.

O relatório contém três grupos de campos:

* **Campos de conversão multiplataforma:** canal de mídia, campanha, anúncio, geolocalização, dispositivo, CUID, tipo de conversão, receita, timestamp da conversão multiplataforma e identificadores relacionados.
* **Campos de assistência (1, 2 e 3):** para cada uma das três posições de assistência, o canal de mídia, a campanha, o conjunto de anúncios, o anúncio, a agência, o canal, o tipo e o subtipo de engajamento, o ID do site e o horário do evento correspondentes. Esses campos usam a convenção de nomenclatura `<field>__assist_1`, `<field>__assist_2` e `<field>__assist_3`.
* **Campos de enriquecimento:** oferecem suporte à análise de lifetime value (LTV) no nível do usuário e à análise no nível do evento. Por exemplo, combine esses campos com os registros de conversão de um usuário para criar uma visualização de LTV por usuário entre plataformas.

<div id="report-data-freshness" />

## Atualização dos dados do relatório

O relatório executa um lote a cada 4 horas. Cada execução de lote processa eventos que entraram no banco de dados durante as últimas 4 horas. Por exemplo, a execução do lote das 8:00 AM processa eventos que entraram no banco de dados entre 3:00 AM e 7:00 AM.

O processo em lote aloca eventos para suas versões por hora correspondentes. Por exemplo, eventos que entraram no banco de dados entre 3:00 e 4:00 AM aparecem na versão das 3:00 AM.

> 📘 **Note**
>
> Normalmente, há um pequeno atraso entre o momento em que um evento ocorre e sua entrada no banco de dados. O relatório usa o horário de entrada no banco de dados para manter o agrupamento por hora preciso e consistente.

<div id="example-the-8-am-batch-run" />

### Exemplo: a execução do lote das 8h

| Date | Versão do relatório | Disponível em | Inclui eventos que ocorreram entre | Inclui eventos que entraram no banco de dados entre |
| --- | --- | --- | --- | --- |
| 01/10/2025 | 3:00 | 9:00 | 2:00-4:00 | 3:00-4:00 |
| 01/10/2025 | 4:00 | 9:00 | 3:00-5:00 | 4:00-5:00 |
| 01/10/2025 | 5:00 | 9:00 | 4:00-6:00 | 5:00-6:00 |
| 01/10/2025 | 6:00 | 9:00 | 5:00-7:00 | 6:00-7:00 |

Algumas observações sobre este exemplo:

* O lote não processa eventos da última hora antes da execução, para deixar tempo suficiente para enriquecer os eventos com o CUID relacionado. No exemplo acima, o lote das 8:00 AM processa eventos que entraram no banco de dados entre 3:00 e 7:00. Eventos que entraram no banco de dados entre 7:00 e 8:00 não são processados nessa execução.
* O relatório fica disponível uma hora após a execução em lote, pois um processo interno atualiza o lote durante essa hora. No exemplo acima, o lote das 8:00h está disponível às 9:00h.

<div id="subscribe-to-the-report" />

## Inscreva-se no relatório

Para se inscrever no relatório:

1. Na AppsFlyer, no menu lateral, selecione **Exportar** > **Data Locker**.
2. No painel de conteúdo do **Data Locker**, role para baixo até a seção **Relatórios avançados**.
3. Selecione **Conversões cross-platform**.

<div id="access-the-report-data-in-your-cloud-bucket" />

## Acesse os dados do relatório no seu cloud bucket

O caminho (path) para o relatório consiste na seguinte hierarquia de pastas:

```text
<bucket-name>/<DataLocker connection name>/t=conversions_user_level_cross_platform/dt=<yyyy-mm-dd>/h=<hour>/
```

<div id="business-intelligence-bi-developer-considerations" />

## Considerações para desenvolvedores de business intelligence (BI)

Lembre-se do seguinte ao conectar seu banco de dados ou dashboard a este relatório:

* A versão horária de cada relatório contém registros de conversão únicos. Certifique-se de extrair todos os relatórios por hora ou por dia.
* Os campos de assistência (`__assist_1`, `__assist_2`, `__assist_3`) refletem os engajamentos assistidos por trás de cada conversão, com base nos dados de conversão subjacentes. Use-os para reconstruir a sequência de touchpoints que levou a cada conversão.
* O relatório fornece receita em três moedas: `revenue_usd` (normalizada), `revenue_value_original` (a moeda do evento reportado; consulte `revenue_currency_original`) e `revenue_value_customer` (sua moeda preferida; consulte `currency_customer`). Use a que melhor atende às suas necessidades de relatório.
* Este relatório não inclui campos de custo (custo, cliques, impressões). Em vez disso, extraia-os do <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">relatório de custo ETL</Anchor>.
* O relatório fornece todos os dados do aplicativo em um único arquivo. Use o campo App ID para separar dados por aplicativo ou defina o Data Locker para segregar por aplicativo. Recomendamos usar o <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#app-segregation">tipo de segregação unificada</Anchor>.

<div data-zendesk-anchors="h_01=sobre-o-relat%C3%B3rio about-the-report=sobre-o-relat%C3%B3rio h_02=campos-do-relat%C3%B3rio report-fields=campos-do-relat%C3%B3rio h_03=atualiza%C3%A7%C3%A3o-dos-dados-do-relat%C3%B3rio report-data-freshness=atualiza%C3%A7%C3%A3o-dos-dados-do-relat%C3%B3rio h_07=exemplo-a-execu%C3%A7%C3%A3o-do-lote-das-8h example-8am-batch-run=exemplo-a-execu%C3%A7%C3%A3o-do-lote-das-8h h_04=inscreva-se-no-relat%C3%B3rio subscribe-to-the-report=inscreva-se-no-relat%C3%B3rio h_05=acesse-os-dados-do-relat%C3%B3rio-no-seu-cloud-bucket access-report-data-cloud-bucket=acesse-os-dados-do-relat%C3%B3rio-no-seu-cloud-bucket h_06=considera%C3%A7%C3%B5es-para-desenvolvedores-de-business-intelligence-bi bi-developer-considerations=considera%C3%A7%C3%B5es-para-desenvolvedores-de-business-intelligence-bi" />

---
title: Atribuição duplicada de eventos de retargeting
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-12-13T07:35:18Z'
  edited_at: '2026-08-18T00:37:15Z'
  id: 360016371077
  locale: pt
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/pt/articles/360016371077
---
> **Visão geral:** para avaliar a performance durante a janela de reengajamento de uma campanha de retargeting, os eventos e sessões in-app são atribuídos de forma duplicada aos canais de mídia responsáveis pela aquisição de usuários (UA) e retargeting.

![](https://files.readme.io/fce514999471aa7bfced06fa0e1c7d6fa7363a8d30119bd20d0b5d7e56eb1f7d-9479192551825.png)

## Visão geral

No modelo de atribuição da AppsFlyer, eventos que ocorrem como resultado de um engajamento com uma campanha de retargeting são atribuídos tanto ao canal de mídia que impulsionou a instalação quanto ao canal de mídia que gerou um reengajamento.

A aplicação de atribuições duplas é diferente entre reengajamentos e reatribuições:

* **Reengajamentos:** A atribuição dupla é aplicada a todos os reengajamentos.
* **Reatribuições:** A atribuição dupla é aplicada a aplicativos que estão no modo de primeira instalação. Para aplicativos que não estão no modo de primeira instalação, a atribuição dupla não é aplicada. (O modo de primeira instalação significa que todos os eventos in-app gerados a partir de reinstalações são atribuídos à instalação original. Para mais informações sobre o modo de primeira instalação, consulte <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#attributed-to-the-first-install">Atribuído à primeira instalação</Anchor>). Recomendamos entrar em contato com a AppsFlyer para migrar seus aplicativos existentes para o modo de primeira instalação.

Na imagem acima, o evento de UA é atribuído à green\_network. Um evento é gerado. Em contraste, quando o usuário se engaja com um anúncio de retargeting exibido pela blue\_network, dois eventos são gerados. Os eventos creditam:

* blue\_network como fonte primária que motivou o reengajamento.
* green\_network como fonte secundária que impulsionou a instalação original.

A tabela abaixo mostra um cenário que explica como os eventos in-app são atribuídos antes, durante e após uma janela de reengajamento. As informações da tabela se referem aos campos de dados brutos usados para identificar eventos duplamente atribuídos:

* is\_primary (is\_primary\_attribution): quando true, o canal de mídia é a fonte primária
* context: use um dos campos abaixo:
  * [Prática recomendada] **conversion\_type**: instalação ou reengajamento.
  * is\_retargeting: quando true, os dados se referem à campanha de retargeting.

#### Atribuição na janela de reengajamento

| Canal de mídia | Antes do reengajamento | Durante o reengajamento | Após o reengajamento |
| --- | --- | --- | --- |
| Aquisição de usuários | Primário<br /><br />is\_primary: True<br /><br />conversion\_type: install<br /><br />(is\_retargeting: False) | Secundário<br /><br />is\_primary: False<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: False) | Primário<br /><br />is\_primary: True<br /><br />conversion\_type: install<br /><br />(is\_retargeting: False) |
| Redirecionamento | N/D | Primário<br /><br />is\_primary: True<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: True) | N/D |

## Tipos de visualização compatíveis

Alguns dashboards e relatórios de cohort possuem diversas opções de visualização, como a visão unificada, de aquisição de usuários e retargeting. Essas opções seguem uma lógica semelhante à dos dados brutos.

![](https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png)

#### Filtragem de dados por tipo de visualização usando o campo conversion\_type

<table><thead><tr><th>Tipo de visualização</th><th>tipo_de_conversão</th><th>is_primary</th><th>Atribuição</th></tr></thead><tbody><tr><td rowspan="2">Aquisição de usuários</td><td>instalação</td><td>True ou False</td><td>Eventos de UA atribuídos ao canal de mídia responsável pela aquisição de usuários</td></tr><tr><td>re-engajamento</td><td>Falso</td><td>Eventos de retargeting atribuídos ao canal de mídia responsável pela aquisição de usuários</td></tr><tr><td>Redirecionamento</td><td>reengajamento ou reatribuição</td><td>True</td><td>Eventos de retargeting atribuídos ao canal de mídia responsável pelo retargeting</td></tr><tr><td>Unificada</td><td>instalação ou reengajamento</td><td>True</td><td>Todos os eventos atribuídos ao canal de mídia que recebeu o último toque</td></tr></tbody></table>

## Como identifico eventos de retargeting com atribuição duplicada nos relatórios de aquisição de usuários in-app?

Nos **relatórios de eventos de aquisição de usuários in-app,** isso é identificado da seguinte forma:

* O campo is\_primary\_attribution identifica fontes primárias e secundárias; quando false, significa que a atribuição ocorre como resultado de uma campanha de retargeting e o canal de mídia responsável pela aquisição do usuário (UA) é uma fonte secundária.
* O campo is\_retargeting é sempre true.

O registro correspondente nos relatórios de eventos de retargeting durante a janela de reengajamento é preenchido da seguinte forma:

* O campo is\_primary\_attribution é sempre true.
* O campo is\_retargeting é sempre false.
* Para esclarecer, nenhum registro é feito se o evento não ocorrer durante a janela de reengajamento.

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01J8FJW0TE4DV5BFHGARS4ERT6=vis%C3%A3o-geral attribution-relative-to-the-reengagement-window=atribui%C3%A7%C3%A3o-na-janela-de-reengajamento h_01J8FJW0TEJH716NXMM2RDN4J1=atribui%C3%A7%C3%A3o-na-janela-de-reengajamento support-for-dashboard-view-types=tipos-de-visualiza%C3%A7%C3%A3o-compat%C3%ADveis h_01J8FJW0TEDFGFPPYZEAREKY4Q=tipos-de-visualiza%C3%A7%C3%A3o-compat%C3%ADveis data-filtering-by-view-type-using-the-conversion_type-field=filtragem-de-dados-por-tipo-de-visualiza%C3%A7%C3%A3o-usando-o-campo-conversion_type h_01J8FJW0TETSV5X6D7NJ4EQHGC=filtragem-de-dados-por-tipo-de-visualiza%C3%A7%C3%A3o-usando-o-campo-conversion_type how-do-i-identify-doubleattributed-retargeting-events-in-user-acquisition-inapp-reports=como-identifico-eventos-de-retargeting-com-atribui%C3%A7%C3%A3o-duplicada-nos-relat%C3%B3rios-de-aquisi%C3%A7%C3%A3o-de-usu%C3%A1rios-in-app h_01J8FJW0TED4T9JN89PCRA3M9R=como-identifico-eventos-de-retargeting-com-atribui%C3%A7%C3%A3o-duplicada-nos-relat%C3%B3rios-de-aquisi%C3%A7%C3%A3o-de-usu%C3%A1rios-in-app" />

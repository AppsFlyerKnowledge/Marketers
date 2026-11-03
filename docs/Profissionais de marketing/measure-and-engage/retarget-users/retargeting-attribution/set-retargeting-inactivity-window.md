---
title: Período de inatividade de retargeting
metadata:
  keywords:
    - Agencies
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
  created_at: '2020-05-31T13:56:38Z'
  edited_at: '2026-09-16T00:34:39Z'
  id: 360009305817
  locale: pt
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/pt/articles/360009305817
---
> **Visão geral:** Expanda o aumento incremental redirecionando usuários inativos. Defina janelas de inatividade por fonte de mídia.

## Período de inatividade

Os anunciantes recuperam usuários inativos redirecionando-os. Essas campanhas costumam ter uma boa taxa de conversão e geram ROAS significativo. Muitas campanhas de retargeting têm um baixo desempenho porque elas não filtram usuários ativos. Para impulsionar o aumento incremental das campanhas de retargeting, implemente **um tempo mínimo de inatividade** para filtrar usuários ativos.

Ao definir um tempo mínimo de inatividade, os anunciantes não atribuem usuários ativos. Por exemplo, se o limite mínimo de inatividade for de três dias, então os usuários ativos nos últimos 0-3 dias não serão atribuídos. Usuários inativos durante quatro ou mais dias são atribuídos. O período de inatividade se aplicava tanto a cenários de reatribuição como de reengajamento. No caso de reatribuição, a última atividade é a última sessão antes de executar a desinstalação.

**Regras de inatividade**

* **Atribuído** Usuários inativos que não usam o aplicativo há mais tempo do que o período de inatividade definido. Retargeting, reengajamentos e reinstalações são atribuídos.
* **Não atribuídos**: Os usuários ativos que abrem o aplicativo e não excedem o período mínimo de inatividade são desconsiderados e não atribuídos à campanha de retargeting.

### Retargeting da terminologia de inatividade

| Termo | Definição |
| --- | --- |
| Valor máximo | 30 dias |
| Valor padrão | 0 (nenhum)  <br />O **Período de inatividade** O recurso não está ativo por padrão para canais de mídia. |
| Atividade do usuário | Instalações ou sessões reportadas pelo SDK ou via S2S. |
| Dispositivos migrados | O tempo de migração é o último tempo de atividade. |

## Cenário

Nos cenários de retargeting a seguir, o período de inatividade é definido para o canal de mídia.

<div id="reattribution" />

<Accordion title="Reatribuição">

O cenário do usuário é representado na figura a seguir. O usuário:

* desinstala o aplicativo e está inativo
* engaja com uma campanha de retargeting executada por um canal de mídia
* reinstala o aplicativo

[![re-attribution_1_en-us.png](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)](https://files.readme.io/7d9fa957758b19a7bd61a9f92428118009f0380d703e1641a15f0e531ce08a8a-10298371408017.png)

| Cenário | Limite de inatividade | Período de inatividade do usuário | Resultado |
| --- | --- | --- | --- |
| E | 7 dias | 8 dias.<br /><br />**O usuário estava inativo** por um período superior ao limiar de inatividade | <ul><li>**Reatribuição** (reinstalação de retargeting)</li><li>Atribuído ao retargeting da fonte de mídia A</li></ul> |
| B | 14 dias | 5 dias<br /><br />O usuário estava ativo. | <ul><li>**Reinstalação orgânica**</li><li>**Reinstalação não orgânica:** se o usuário engajou com um canal de mídia de UA.</li><li>A fonte de mídia de redirecionamento A não pode ser atribuída devido ao limite de inatividade do usuário.</li></ul> |

</Accordion>

<div id="reengagement" />

<Accordion title="Reengajamento">

O cenário do usuário é representado na figura a seguir. O usuário:

* instala o aplicativo
* fica inativo por vários dias
* posteriormente, engaja-se com uma campanha de retargeting. executado por um canal de mídia e inicia o aplicativo

[![Re-engagement_scenarios_en-us.png](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)](https://files.readme.io/dd527f12caa8b197fe0d1145ff0175a92d48ab4e7e4851e15f56faa617fe9e2e-10124778806929.png)

| Cenário | Canal de mídia Um limite de inatividade | Período de inatividade do usuário | Resultado |
| --- | --- | --- | --- |
| E | 7 dias | 8 dias<br /><br />**O usuário estava inativo** por um período superior ao limiar de inatividade | <ul><li>**Reengajamento** atribuído à fonte de mídia A</li></ul> |
| B | 7 dias | 4 dias<br /><br />**O usuário usou o aplicativo** dentro do período de inatividade definido. | <ul><li>**Sessão comum**</li><li>O canal de mídia de retargeting A não é atribuído</li></ul> |

</Accordion>

## Configuração de parceiro

<div id="zd-srn" />

<Accordion title="SRN">

Os SRNs compatíveis com períodos de inatividade têm esse recurso configurado na aba Integração.

**Para definir um período de inatividade para Redes de Self-Reporting (SRN) compatíveis com retargeting:**

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas.**
2. Selecione um SRN.
3. Na aba **Integração**, role para baixo. Ative **Ignorar usuário ativo para retargeting**
4. Conifugure **Janela de inatividade.** (1-30 dias.)
5. Clique em **Salvar integração.**

[![Inactivity_window_SRN.png](https://files.readme.io/a3a6dfb2270790a28b71581264c924ba1e4146d4975f64d3cee43a9e0ff3f172-36539146170897.png)](https://files.readme.io/a3a6dfb2270790a28b71581264c924ba1e4146d4975f64d3cee43a9e0ff3f172-36539146170897.png)

</Accordion>

<div id="nonsrn-click-ad-networks" />

<Accordion title="Não-SRN (clique em ad networks)">

**Para definir um período de inatividade para não-SRNs compatíveis com retargeting:**

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas.**
2. Selecione uma ad network.
3. Vá para a aba **Link de atribuição**, role para baixo e ative **Ignorar usuário ativo para retargeting**.
4. Conifugure **Janela de inatividade.** (1-30 dias.)  
   O parâmetro **Período de inatividade** `af_inactivity_window`é adicionado ao link de atribuição, por exemplo, "&af\_inactivity\_window=7d". Se o recurso estiver desativado, ele não estará no link de atribuição.

[![](https://files.readme.io/cec66a07874832ecd93d26a7275b81cd4cae2842b34d04c93427bb6344edd651-36538331525521.png)](https://files.readme.io/cec66a07874832ecd93d26a7275b81cd4cae2842b34d04c93427bb6344edd651-36538331525521.png)

</Accordion>

<div id="agencies" />

<Accordion title="Agências">

#### SRN

Agência (permissão concedida pelo anunciante)

**Para acessar a configuração do período de inatividade:**

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas.**
2. Selecione um SRN.
3. Na **Integração**, faça as configurações conforme mostrado na tabela a seguir.

| SRN | Agência |
| --- | --- |
| DoubleClick | <ul><li>Ativar/desativar o retargeting</li><li>Configurar um período de inatividade</li></ul> |
| Google Ads | <ul><li>Não é possível ativar/desativar o retargeting</li><li>Se uma agência tiver permissões, ela poderá configurar um período de inatividade</li></ul> |
| Meta ads/X Ads/Snapchat | não podem acessar configuração de retargeting e **Período de inatividade** |

#### Não-SRN

Parceiro (compatível com retargeting)

**Para definir um período de inatividade para não-SRNs compatíveis com retargeting:**

1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas.**
2. Selecione uma Ad network não SRN > aba **Link de atribuição**.

</Accordion>

## Especificações e limitações

| Caraterística | Observações |
| --- | --- |
| /docs/testing-the-sdk-integration-for-marketers#test-reengagement | Ao usar um dispositivo de teste registado, certifique-se de remover o parâmetro `af_inactivity_window` do link de teste. Caso contrário, a instalação pode ser atribuída incorretamente como *orgânica*, em vez de ser atribuída ao link de teste. |

<div data-zendesk-anchors="inactivity-period=per%C3%ADodo-de-inatividade h_01H9JS3QKW5S7VP9YW05CB6STR=per%C3%ADodo-de-inatividade retargeting-inactivity-terminology=retargeting-da-terminologia-de-inatividade h_01H9JS3QKXMBS95RG06A9JXGT0=retargeting-da-terminologia-de-inatividade scenarios=cen%C3%A1rio h_01H9JS3QKXWDX8Y58GX1G5HNYY=cen%C3%A1rio h_01H9JS3QKXN0E0MGD35173C9FR=reattribution h_01H9JS3QKXNS77EFYBZP94YQMT=reengagement partner-setup=configura%C3%A7%C3%A3o-de-parceiro h_01H9JS3QKXGNFM8499G52458B2=configura%C3%A7%C3%A3o-de-parceiro srn=zd-srn h_01H9JS3QKXCAHG91VS6VSVJTTT=zd-srn h_01H9JS3QKX8R8AXHQWKX7FR9GZ=nonsrn-click-ad-networks h_01H9JS3QKXSDXA5Z7TWN2A7S5K=agencies srn::bd853114=srn h_01H9JS3QKX88HQYJ5881W7VXF2=srn nonsrn=n%C3%A3o-srn h_01H9JS3QKXRJ8W9H89JBVSZ3R3=n%C3%A3o-srn traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01J6S6HS0H0M6GQ81WGZ3XT0P9=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />

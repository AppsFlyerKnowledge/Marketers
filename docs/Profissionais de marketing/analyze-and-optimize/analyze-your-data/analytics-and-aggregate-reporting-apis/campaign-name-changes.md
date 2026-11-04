---
title: Alterações no nome da campanha
metadata:
  keywords:
    - Aggregated Data
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2023-03-26T10:56:19Z'
  edited_at: '2026-08-18T00:02:46Z'
  id: 14038324952465
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/14038324952465
---
> **Visão geral:** Altere os nomes das campanhas sem criar exibições de dados duplicadas.

<div id="campaign-name-changes" />

## Alterações no nome da campanha

Alterar os nomes das campanhas afeta a exibição de **dados agregados** em painéis e relatórios. A AppsFlyer exibe campanhas usando o ID da campanha como chave. Se houver mais de um nome associado ao mesmo ID de campanha, o nome informado mais recentemente será usado para exibir dados.

* Embora façamos referência às mudanças no nome da **campanha** neste artigo, as mesmas regras se aplicam às mudanças no conjunto de anúncios e no nome do anúncio.
* A mudança de nome afeta a exibição de todos os dados conectados à campanha, incluindo instalações, eventos in-app, custo e receita.
* A maioria das ad networks é compatível com alterações de nome de campanha, mas algumas não. Nelas, você pode ver linhas duplicadas com os mesmos dados.
* Os dados brutos não são afetados pelas alterações de nome.

A tabela a seguir mostra quais painéis e relatórios são compatíveis com alterações no nome da campanha.

| Painel/relatório | Compatível com alterações no nome da campanha |
| --- | --- |
| Painel de Visão Geral | Sim, exceto para visualização de CTV |
| Painel de atividades | Sim |
| Painel de coorte | Sim |
| API de Coorte | Sim |
| Extrair API | Não compatível com a Pull API V5 e versões anteriores |
| Painel Pivot | Não |
| Painel personalizado | Não |
| Painel de retenção | Não |
| Painel de eventos | Não |
| Painel do Protect360 | Não |
| ETL de custos | Sim |
| Painel de visão geral do SKAN | Não |

<div id="example" />

> 📄 **Exemplo**
>
> * Em 1º de janeiro, a campanha **example\_a1** começou a ser veiculada.
> * Em 2 de janeiro, o nome da campanha foi alterado de **example\_a1** para **example\_a2**.
>
> #### <span id="example-campaign-data"></span>Exemplos de dados de campanha
>
>
>
> | Data | Nome da campanha | ID da campanha | Instalações | Gasto com anúncios |
> | --- | --- | --- | --- | --- |
> | 1º de janeiro | example\_a1 | 123 | 100 | $100 |
> | 2 de janeiro | example\_a2 | 123 | 200 | US$ 200 |
>
>
>
> #### <span id="overview-dashboard-display"></span>Visualização do painel de visão geral
>
>
>
> <table><tbody><tr><th><p><span>Campanha</span></p></th><th><p><span>ID da campanha</span></p></th><th><p><span>Instalações</span></p></th><th><p><span>Gasto com anúncios</span></p></th></tr><tr><td><p><span>example_a2</span></p></td><td><p><span>123</span></p></td><td><p><span>300</span></p></td><td><p><span>US$ 300</span></p></td></tr><tr><td colspan="4"><p>Resultado: Os dados são exibidos sob o nome da campanha mais recente.</p></td></tr></tbody></table>

<div id="best-practice" />

### Prática recomendada:

* A maioria das ad networks é compatível com alterações de nome de campanha, mas algumas não. Nelas, você pode ver linhas duplicadas com os mesmos dados. Para evitar essas anomalias de exibição, certifique-se de que as campanhas tenham um ID de campanha exclusivo atribuído a elas.
* Você não usa o mesmo nome de campanha com IDs diferentes.
* Não use o mesmo nome de anúncio com IDs de anúncio diferentes.

<div data-zendesk-anchors="rollout-details=altera%C3%A7%C3%B5es-no-nome-da-campanha h_01HW896QQ2T4J0N5PDY6YFTJ49=altera%C3%A7%C3%B5es-no-nome-da-campanha h_01HW896QQ34YVGF6P212ZHAQHG=exemplo example-campaign-data=exemplos-de-dados-de-campanha h_01HW896QQ3G07XM06HR2CRXA3G=exemplos-de-dados-de-campanha overview-dashboard-display-before-the-behavior-change=visualiza%C3%A7%C3%A3o-do-painel-de-vis%C3%A3o-geral h_01HW896QQ3J9NE9GZRKKAPX46B=visualiza%C3%A7%C3%A3o-do-painel-de-vis%C3%A3o-geral best-practice=pr%C3%A1tica-recomendada h_01HW896QQ4RAQ51GPD17YYZBJF=pr%C3%A1tica-recomendada" />

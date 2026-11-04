---
title: Configure integrações de parceiros de receita de anúncios do ROI360 via API
metadata:
  keywords:
    - ad revenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-10-16T14:53:47Z'
  edited_at: '2026-08-19T00:02:15Z'
  id: 9901416616465
  locale: pt
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/pt/articles/9901416616465
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Em resumo:** Configure integrações de parceiros de receita de anúncios para sua conta da AppsFlyer ou aplicativos individuais via API.

<div id="ad-revenue-partner-integration-api" />

## API de integração de parceiros de receita de anúncios

A API de integração de parceiros de receita de anúncios é usada para:

* Definir configurações de parceiros de receita de anúncios no nível do aplicativo para toda a sua conta.
* Obter uma lista das configurações atuais de parceiros de receita de anúncios para toda a sua conta.

<div id="set-api" />

<Accordion title="Definir API">

**Para definir (configurar) integrações de parceiros de receita de anúncios via API**:

1. <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">Obtenha seu token da API V2</Anchor> no Dashboard da AppsFlyer. Necessário para a autorização da API. **Observação**: isso deve ser feito pelo administrador da conta.
2. Prepare os parâmetros para incluir na solicitação da API, conforme descrito na tabela a seguir.
3. Forneça os valores dos parâmetros ao seu desenvolvedor e diga a ele para seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">instruções da API de definição de integrações</Anchor> no hub de desenvolvimento.  
   A integração entra em vigor às 00:00 UTC do dia seguinte.

<div id="request-parameters" />

#### Parâmetros da solicitação

| Parâmetro | A descrição |
| --- | --- |
| integrações | <ul><li>Objeto de nível superior que deve incluir app\_id, network e products (listados abaixo).</li><li>Outros campos podem incluir credentials, event\_name e source\_event.</li></ul> |
| ativado | O ID do aplicativo que você deseja integrar. |
| network | <ul><li>O parceiro que você deseja integrar.</li><li>Para ver uma lista das networks compatíveis, consulte a coluna network da <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">tabela de parâmetros da API de parceiros de receita de anúncios</Anchor>.</li></ul> |
| credenciais | <ul><li>1 ou mais credenciais necessárias para a integração da network.</li><li>Para ver a lista de credenciais, consulte as colunas cred da <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">tabela de parâmetros da API de parceiros de receita de anúncios</Anchor>.</li></ul> |
| nome\_do\_evento | <ul><li>Valor padrão: af\_ad\_revenue</li><li>Também pode ser um nome de evento personalizado [beta]</li><li>event\_name não é obrigatório se enabled estiver definido como false.</li></ul> |
| produtos | <ul><li>Lista de todos os produtos habilitados em uma integração, incluindo os parâmetros name, enabled e, se relevante, source\_event (listado abaixo).</li><li>Para ver uma lista de nomes de tipos de integração, consulte a coluna de produtos da API em massa na <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">tabela de parâmetros da API de Parceiros de receita de anúncios</Anchor>.</li></ul> |
| coluna | <ul><li>O nome do tipo de integração.</li><li>Para ver uma lista de Produtos compatíveis por network, consulte a coluna de produtos da API em massa na <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">tabela de parâmetros da API de Parceiros de receita de anúncios</Anchor>.</li></ul> |
| ativado | <ul><li>Valores possíveis:<ul><li>verdadeiro</li><li>false</li></ul></li><li>Para tipos de integração em nível de Aplicativo, um source-event é obrigatório.</li><li>Se o valor for false, nem source\_event nem event\_name serão obrigatórios.</li></ul> |
| source\_event | <ul><li>Relevante apenas para integrações de parceiros da API S2S em nível agregado.</li><li>Para tipos de integração em nível de Aplicativo, se enabled estiver definido como true, source\_event é obrigatório.</li></ul> |

</Accordion>

<div id="get-api" />

<Accordion title="Obter a API">

**Para obter via API uma lista das suas integrações de parceiros de receita de anúncios**:

1. <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">Obtenha seu token da API V2</Anchor> no dashboard da AppsFlyer. Obrigatório para autorização da API.
2. Diga ao seu desenvolvedor para seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">instruções da API List integrations</Anchor> no hub de desenvolvedores.

</Accordion>

<div id="specs-and-limitations" />

### Especificações e limitações

| **Especificação** | **Considerações** |
| --- | --- |
| Limite de chamadas | Até 1.000 integrações em uma única chamada. |
| OAuth | Parceiros integrados via OAuth (como Google e Facebook) não são compatíveis. |

<div data-zendesk-anchors="ad-revenue-partner-integration-api=api-de-integra%C3%A7%C3%A3o-de-parceiros-de-receita-de-an%C3%BAncios h_01HYD2M7E1PH0ARZRF0P17K80J=api-de-integra%C3%A7%C3%A3o-de-parceiros-de-receita-de-an%C3%BAncios h_01HYD2M7E1DX9FAJ0MGN500NZV=set-api request-parameters=par%C3%A2metros-da-solicita%C3%A7%C3%A3o h_01HYD2M7E1FYY96HNM6DSHXPQ5=par%C3%A2metros-da-solicita%C3%A7%C3%A3o h_01HYD2M7E19XCCFF1NT40VBWH7=get-api specs-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01HYD2M7E1X2PEQ616PWMTWCH7=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />

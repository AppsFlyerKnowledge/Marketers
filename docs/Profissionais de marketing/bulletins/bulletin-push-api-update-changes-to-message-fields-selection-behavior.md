---
title: >-
  Boletim: atualização da Push API - alterações no comportamento de seleção para
  "campos de mensagem"
metadata:
  keywords:
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2025-12-10T11:38:33Z'
  edited_at: '2026-08-18T00:20:49Z'
  id: 41785747996689
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/41785747996689
---
| Seção | Detalhes |
| --- | --- |
| **Novidades** | O comportamento da configuração `selected_fields = "ALL FIELDS"` da Push API mudou. Essa configuração deixará de atuar como um seletor que identifica alterações futuras. Ela será aplicada apenas aos campos de mensagem já existentes no momento em que a configuração for salva. Quaisquer novos campos adicionados posteriormente não serão incluídos automaticamente.<br /><br />Essa mudança aumenta a transparência da solução, fornecendo aos clientes melhor controle sobre seus pipelines de dados e evitando a inclusão não planejada de novos campos. |
| **Data de início** | 30 de dezembro de 2025 |
| **O que você precisa saber** | <ul><li>A configuração da Push API pode ser aplicada das seguintes maneiras:<ul><li>[Atualizar a configuração da REST API na Push API](https://dev.appsflyer.com/hc/reference/put_app-app-id):<ul><li>Definir a propriedade `select_fields` como ALL Fields</li></ul></li><li><Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">Na AppsFlyer, vá para Exportar-> Acesso à API -> Push API ou Push API (SKAN)</Anchor>:<ul><li>Selecione o campo **Selecionar todos**.</li></ul></li></ul></li><li>Ao chamar <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-app-id">Get Push API configuration REST API</Anchor> quando `selected_fields = "ALL FIELDS"` está configurado, a chamada retornará a lista de campos selecionados em vez do resultado genérico "todos".</li></ul> |
| **O que você precisa fazer** | <ul><li>A maioria dos clientes não precisa fazer nada.</li><li>Não é necessária nenhuma alteração nos nomes ou na semântica dos campos.</li><li>Os clientes devem atualizar manualmente sua seleção na AppsFlyer ou via REST API para receber os novos campos adicionados.</li><li>Clientes que utilizam "ALL FIELDS" devem revisar periodicamente sua configuração para garantir que novos campos sejam incluídos conforme necessário.</li></ul> |
---
title: >-
  Boletim: parâmetros adicionais disponíveis para deep linking de usuários
  existentes
metadata:
  keywords:
    - SDK
    - deep link
    - deep linking
    - Developers
    - Marketers
    - OneLink
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2022-04-27T09:49:22Z'
  edited_at: '2026-10-20T03:56:43Z'
  id: 5733303620113
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/5733303620113
---
> **Resumo:** Retorno de parâmetros adicionais para deep linking de usuários existentes pelo método UDL.

| **Novidades** | O SDK da AppsFlyer V6.6+ permite que o método UDL retorne parâmetros adicionais para deep linking de usuários existentes (com o aplicativo instalado). |
| --- | --- |
| **Data de início** | 27º de abril de 2022 |
| **Onde** | Método UDL para deep linking de usuários existentes com o aplicativo instalado |
| **O que** | **Antes da mudança:** o método UDL retornava apenas os parâmetros `deep_link_value` e `deep_link_sub1-10` para deep linking de usuários existentes.<br /><br />**Depois da mudança:** o método UDL retorna todos os parâmetros que aparecem no parâmetro do link, incluindo:<ul><li>`c`</li><li>`pid`</li><li>`path`</li><li>`esquema`</li><li>`host`</li><li>`af_c_id`</li><li>`af_adset`</li><li>`af_adset_id`</li><li>`af_ad`</li><li>`af_ad_id`</li><li>`af_ad_type`</li><li>`af_channel`</li><li>`af_dp`</li><li>`esp_name`</li><li>`link`</li></ul> |
| **O que você precisa saber** | **Práticas recomendadas**: embora esses parâmetros estejam disponíveis para deep linking de usuários existentes, recomendamos que você crie novos links usando apenas os parâmetros `deep_link_value` e `deep_link_sub1-10`, conforme documentado em nosso <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">guia de deep linking</Anchor>.<ul><li>Essa mudança se destina apenas a clientes com links existentes que usam métodos legados de deep linking. Agora, esses clientes podem implementar o método UDL para deep linking e usar esses parâmetros adicionais para fazer deep linking de usuários existentes, enquanto continuam usando os mesmos links. Não é necessário criar novos links.</li><li>AppsFlyer SDK V6.6+ obrigatório</li></ul> |
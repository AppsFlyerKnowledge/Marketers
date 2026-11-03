---
title: >-
  Boletim: Smart Banners são compatíveis com múltiplos canais de mídia para
  atribuição
metadata:
  keywords:
    - OneLink
    - Advertisers
    - smart banners
    - Marketers
    - Smart Banners and Scripts
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2021-08-24T07:01:05Z'
  edited_at: '2026-10-20T03:56:50Z'
  id: 4406100924689
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/4406100924689
---
| **Novidades** | As configurações de Smart Banner permitem que você escolha vários tipos de canal de mídia para atribuição. Eles já não estão mais limitados a um tipo de URL web-to-app. |
| --- | --- |
| **Data de início** | 25 de agosto de 2021 |
| **Onde:** | Smart Banners - configuração do grupo de banners |
| **O que** | **Antes da mudança:** Era compatível com um tipo de canal de mídia por grupo de banners. Os usuários precisavam escolher entre usar parâmetros de atribuição de links recebidos, **OU** links recebidos com parâmetros UTM, **OU** os parâmetros de atribuição padrão (que também eram usados como fallback). Isso significava que a AppsFlyer procurava por "pid" ou “utm\_source” na URL recebida.<br /><br />**Depois da mudança:** Os grupos de banners não estão limitados a um tipo de canal de mídia. Eles podem ser configurados para ser compatíveis com um ou mais dos canais de mídia acima. Ou seja, os usuários podem escolher entre parâmetros de atribuição de links recebidos **E/OU** parâmetros UTM de links recebidos **E/OU** os parâmetros de atribuição padrão. Isso oferece mais flexibilidade para personalizar o link por trás do banner e proporcionar a melhor experiência web-to-app para o usuário final. |
| **O que você precisa saber** | <ul><li>Se você já tem Smart Banners e grupos de banners, suas configurações permanecem as mesmas.</li><li>Para novos grupos de banners, a interface mudou para permitir que você escolha mais de uma opção de canal de mídia.</li><li>Você precisa ter o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#smart-banners-only">SDK web do Smart Banners</Anchor> atual integrado; esse recurso não é compatível com o SDK web antigo (descontinuado).</li></ul>[![](https://files.readme.io/35d3888899ee7d95cb81152ab5a72de5bfcf1df40568b7f2fea00c947658fd42-4406108511633.png)](https://files.readme.io/35d3888899ee7d95cb81152ab5a72de5bfcf1df40568b7f2fea00c947658fd42-4406108511633.png) |
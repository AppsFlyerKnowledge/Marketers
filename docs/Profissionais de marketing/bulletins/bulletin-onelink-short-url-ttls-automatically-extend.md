---
title: 'Boletim: os TTLs das URLs curtas do OneLink são estendidos automaticamente'
metadata:
  keywords:
    - OneLink
    - User invite
    - OneLink API
    - Developers
    - Marketers
    - bulk upload
    - Link Management
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2022-03-10T11:17:11Z'
  edited_at: '2026-10-20T03:56:41Z'
  id: 4667188714001
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/4667188714001
---
| **Novidades** | O tempo de vida (TTL) padrão das URLs curtas do OneLink criadas via upload em massa, SDK (convite de usuário) e API do OneLink é estendido sempre que se clica no link:<ul><li>Upload em massa: 365 dias</li><li>Convite de usuário via SDK: 60 dias</li><li>API do OneLink: 31 dias</li></ul> |
| --- | --- |
| **Data de início** | 14 de janeiro de 2024 |
| **Onde:** | <ul><li>Upload em massa do OneLink</li><li>Links de convite de usuário (URLs do OneLink criadas via SDK)</li><li>API OneLink</li></ul> |
| **O que vai mudar?** | **Antes da mudança**: as URLs curtas do OneLink criadas via upload em massa, SDK (convite de usuário) e API do OneLink tinham um tempo de vida (TTL). Depois que o TTL expirava, os links deixavam de funcionar como esperado e não forneciam dados de atribuição.<br /><br />**Depois da mudança**: as URLs curtas do OneLink criadas via upload em massa, SDK (user invite) e API do OneLink ainda têm um TTL. No entanto, sempre que o link é clicado, o TTL é estendido:<ul><li>Upload em massa: 365 dias</li><li>Convite de usuário via SDK: 60 dias</li><li>API do OneLink: 31 dias</li></ul> |
| **O que você precisa saber** | <ul><li>A mudança afeta URLs curtas do OneLink novas e já existentes com TTLs.</li><li>Para a API do OneLink:<ul><li>Você pode alterar o TTL padrão adicionando o parâmetro `ttl={value}` e especificando quantos dias, horas ou minutos. Por exemplo, `ttl=7d`, `ttl=12h` ou `ttl=10m`.</li></ul></li><li>Para a API do OneLink e upload em massa:<ul><li>Se você não quiser que os TTLs dos links sejam estendidos automaticamente, adicione o parâmetro `renew_ttl=false` aos seus links.<br />**Nota**:<ul><li>O parâmetro `renew_ttl` não é exibido na URL real.</li><li>Para a API do OneLink, o valor é do tipo boolean: true (padrão) ou false.</li></ul></li></ul></li></ul> |
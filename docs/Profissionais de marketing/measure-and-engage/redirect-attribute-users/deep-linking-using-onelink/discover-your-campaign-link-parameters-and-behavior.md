---
title: Descubra os parâmetros e o comportamento do seu link de campanha
metadata:
  keywords:
    - Marketers
    - discover
    - Social-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Social-to-App
  created_at: '2023-07-03T11:56:14Z'
  edited_at: '2026-08-18T00:34:49Z'
  id: 16678138044689
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/16678138044689
---
> **Resumo:** Descubra os parâmetros incluídos em seus links de campanha do AppsFlyer e entenda a experiência e o comportamento esperados do link.

## Sobre o Link Discovery

O recurso de descoberta de links fornece informações sobre seus links de campanha da AppsFlyer, incluindo parâmetros de link e a experiência do usuário esperada que os links criam.

### Vantagens

O Link Discovery ajuda os anunciantes a:

* Ter uma compreensão mais profunda do significado e comportamento do link.
* Comunicar-se com as equipes responsáveis pela criação de links.
* Confirmar os detalhes do link antes de publicá-lo em uma campanha
* Solucionar problemas de comportamento inesperado.
* Consultar os parâmetros de atribuição para saber o que procurar nos painéis.

### Informações disponíveis via Link Discovery

O Link Discovery mostra as seguintes informações sobre uma URL:

* **Detalhes gerais**: informações sobre para quais aplicativos o link se destina, fonte de criação (por exemplo, página de gerenciamento ou API do OneLink), o template do OneLink no qual o link se baseia e a data de expiração e o período de renovação do link.   
  **Observação:** Se a fonte de criação for 'Unknown', é provável que isso aconteça porque se trata de um link legado criado pela IU (Gerenciamento do OneLink) ou de um link mais antigo criado de outras formas (em massa/API/SDK) antes do armazenamento da fonte do chamador.
* **Parâmetros**: todos os diferentes parâmetros incluídos no link e seus valores, exibidos por categoria.   
  **Atenção:** se houver redirecionamento para um domínio que não está na sua <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">redirect allowlist</Anchor>, um alerta deve aparecer.
* **Recursos**: as diferentes capacidades habilitadas para o link. Por exemplo: retargeting, deep linking, pré-visualização de mídia social e página inicial de mídia social.
* **Redirecionamento**: um resumo de como o link é criado para redirecionar os usuários com base em seu dispositivo, plataforma e se eles já têm o aplicativo instalado.

## Usando o Link Discovery

**Para usar o Link Discovery e obter informações sobre uma URL**:

1. No AppsFlyer, no menu lateral, selecione **Engajar** > **Link Discovery**.
2. Insira a sua URL e clique em **descobrir.**

## Especificações e limitações

| Especificação | Observações |
| --- | --- |
| Links compatíveis com o Link Discovery | <ul><li>URLs curtos ou longos criados via AppsFlyer, sejam links de plataforma única ou multiplataforma criados via OneLink.</li><li>Links criados na IU da AppsFlyer e via API, SDK e criação em massa.</li><li>Links com domínios de marca.</li></ul> |
| Agências | Sem suporte |
| Redes de anúncios | Não suportado |
| URLs de impressão | Não suportado |
| Links entre plataformas | Não suportado |

<div data-zendesk-anchors="what-is-app-attribution=sobre-o-link-discovery h_01HKW0CMGXXFKEY7W0NCN1SH76=sobre-o-link-discovery benefits=vantagens h_01HKW0CMGXEAYPDFMR4QCS9F52=vantagens information-available-via-link-discovery=informa%C3%A7%C3%B5es-dispon%C3%ADveis-via-link-discovery h_01HKW0CMGXHZ2NYP6YVPW6QNX3=informa%C3%A7%C3%B5es-dispon%C3%ADveis-via-link-discovery using-link-discovery=usando-o-link-discovery h_01HKW0CMGXD4Z0J7CCKJFZNVCG=usando-o-link-discovery specifications-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01HKW0CMGXX4VXBHFGG3TGGPRV=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />

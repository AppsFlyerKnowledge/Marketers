---
title: Redirecionar usuários do aplicativo para um site web
metadata:
  keywords:
    - OneLink
    - Marketers
    - Social-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Social-to-App
  created_at: '2022-02-22T11:45:43Z'
  edited_at: '2026-08-18T00:35:48Z'
  id: 4460838224273
  locale: pt
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/pt/articles/4460838224273
---
> **Em resumo:** Redirecione usuários do aplicativo para uma URL web ou uma página de rede social usando uma URL gerada com o OneLink.

## Redirecionar usuários do aplicativo para uma URL web

Os anunciantes podem publicar URLs do OneLink que direcionam para páginas externas da web ou sites de rede social. A AppsFlyer mensura os cliques no link dentro do aplicativo, o que permite determinar a eficácia do anúncio.

**Pré-requisitos**: Uma conta no AppsFlyer com pelo menos um aplicativo.

**Para configurar o redirecionamento do aplicativo para a web**:

1. Configure um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor>.
   * Na seção **When app is installed**, verifique se você não configurou um método de abertura do aplicativo (Universal Links, App Links ou esquema de URI).
2. Crie um <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">link personalizado do OneLink</Anchor>.
   * Na seção **When app isn’t installed**, verifique se as configurações de redirecionamento estão definidas para a URL da web desejada.
   * Não adicione um parâmetro `af_dp` com um esquema de URI.
3. Verifique se o domínio para o qual você está redirecionando os usuários aparece na sua <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">redirect allowlist</Anchor>.   
   **Observação:** Configurar uma redirect allowlist de domínio é necessário para garantir que os usuários sejam redirecionados para domínios verificados e confiáveis.

Para testar seu link:

**Pré-requisitos**: Um dispositivo mobile com o aplicativo instalado.

1. Envie a URL curta ou longa para o seu telefone e clique nela.  
   **Observação**: Envie o link para você mesmo por e-mail ou WhatsApp e abra-o no seu telefone. Não paste nas notas do iOS nem diretamente em um navegador mobile.
2. Você deverá ser redirecionado para a URL da web.

<div data-zendesk-anchors="redirect-app-users-to-a-web-url=redirecionar-usu%C3%A1rios-do-aplicativo-para-uma-url-web 01JENAXDEE8C81DN0JGPWPZQSY=redirecionar-usu%C3%A1rios-do-aplicativo-para-uma-url-web" />

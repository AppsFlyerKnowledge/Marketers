---
title: Integração Tapcart
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-24T09:21:54Z'
  edited_at: '2025-05-29T14:37:32Z'
  id: 4411720533905
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/4411720533905
---
> **Resumo:** use o Tapcart para aproveitar os recursos da AppsFlyer no seu aplicativo.

## Introdução

O Tapcart facilita o envio de dados para a AppsFlyer e agiliza o uso dos seus recursos. Ao desenvolver seu aplicativo com o Tapcart, o SDK da AppsFlyer é implementado no aplicativo como padrão. Uma vez que você registra seus dados através do Tapcart, os dados, incluindo instalações orgânicas e não orgânicas, são exibidos na AppsFlyer.

## Integrando o Tapcart com a AppsFlyer

O SDK da AppsFlyer permite que você mensure instalações, desinstalações, referrals, engajamentos com notificações push, realize deep linking, gerencie cenários de privacidade do usuário e mais.

Veja <Anchor target="_blank" href="https://tapcart.com/integrations/appsflyer">essa página do Tapcart</Anchor> para aprender a integrar o Tapcart com a AppsFlyer.

## Eventos in-app padrão configurados no SDK da AppsFlyer

Assim que o Tapcart integrar o SDK da AppsFlyer em seu aplicativo, os seguintes eventos são registrados sempre que um usuário os realiza:

* Concluir cadastro
* Login
* Pesquisa
* Visualização de conteúdo
* Visualização de lista
* Adicionar à lista de desejos
* Adicionar ao carrinho
* Checkout iniciado
* Compra
* Compra concluída
* Remover do carrinho
* Primeira compra

## Ative o deep linking com a AppsFlyer

**Para ativar o deep linking com a AppsFlyer, você precisa fornecer ao Tapcart os seguintes parâmetros:**

1. **Dev key:** identificador exclusivo e token de autenticação usados para configurar um SDK, criptografar suas mensagens e autenticar uma conta de cliente ou chamar um programa em uma API.  
   Aplicativos na mesma conta geralmente têm a mesma dev key. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/app-settings#sdk-authentication-dev-key">dev key</Anchor>.
2. **OneLink template ID:** esse é o ID do template do OneLink usado para gerar URLs do OneLink. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">como criar um template do OneLink</Anchor>.  
   **Para obter o ID de um template específico:**  
   1. **Na AppsFlyer, acesse** **Experiências e deep linking** > Links personalizados do OneLink.
   2. No menu **template do OneLink**, selecione o template desejado.
   3. Copie o ID exibido no lado direito.  
       [![OneLink-template-id.png](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)
3. **URL do OneLink:** uma URL gerada na AppsFlyer para uma campanha específica. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">como gerar um OneLink</Anchor>.

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01JQ6D9NCM8K3E6GS12V2CR1CH=introdu%C3%A7%C3%A3o integrating-tapcart-with-appsflyer=integrando-o-tapcart-com-a-appsflyer h_01JQ6D9NCM95VJB19G2F7SDRG1=integrando-o-tapcart-com-a-appsflyer default-inapp-events-configured-in-the-appsflyer-sdk=eventos-in-app-padr%C3%A3o-configurados-no-sdk-da-appsflyer h_01JQ6D9NCMYBNJ6WJ09R1EHXH4=eventos-in-app-padr%C3%A3o-configurados-no-sdk-da-appsflyer enable-deep-linking-with-appsflyer=ative-o-deep-linking-com-a-appsflyer h_01JQ6D9NCMC97JQ759B44M9TDJ=ative-o-deep-linking-com-a-appsflyer" />

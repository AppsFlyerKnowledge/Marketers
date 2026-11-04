---
title: Testando a integração do tvOS antes de publicar
metadata:
  keywords:
    - Testing
    - tvos
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2016-07-12T09:49:14Z'
  edited_at: '2026-08-18T00:14:55Z'
  id: 211758923
  locale: pt
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/pt/articles/211758923
---
> **Resumo:** Simule uma Instalação não orgânica no seu dispositivo AppleTV usando o Aplicativo de teste do tvOS.

<div id="overview" />

## Escritórios

O AppleTV não tem navegador. Portanto, você não pode testar cliques nem instalações no dispositivo para um **aplicativo não publicado** app. (Para **aplicativos publicados**, você pode <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers#testar-usando-links-de-atribuição">testar usando links de atribuição</Anchor>).

Para testar a atribuição em aplicativos não publicados, você pode usar o **Aplicativo de Teste do tvOS.**

<div id="how-does-the-tvos-test-app-work" />

### Como o Aplicativo de teste do tvOS funciona?

O Aplicativo de teste do tvOS permite simular um clique em um link de atribuição dentro do seu dispositivo AppleTV, para que você possa instalá-lo e receber uma atribuição não orgânica.

**Para testar a atribuição usando o Aplicativo de Teste do tvOS:**

1. Faça o download do projeto <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyerFramework">aqui</Anchor>.
2. No XCode, compile o projeto no seu dispositivo AppleTV de teste.

   A seguinte janela é exibida:

   ![](https://files.readme.io/7ed3c5e8165e6d27c9d87db8b026c0898536b145def6bfedd0dc5f78c7804669-205289963.png)
3. <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">Registre</Anchor> seu dispositivo AppleTV como um dispositivo de teste usando o **IDFA** exibido na parte inferior da tela do Aplicativo.
4. No Aplicativo de Teste, insira seu AppID como ele aparece no dashboard do seu aplicativo.

   Verifique se o aplicativo que você está testando **não está instalado** no dispositivo. Para receber uma atribuição não orgânica, você deve simular um cenário real em que o link de atribuição recebe um clique antes de o Aplicativo ser aberto na **primeira** **execução**.
5. Clique no botão **Click Simulation** e aguarde uma resposta.

   Se tudo estiver válido, a seguinte mensagem será exibida:

   ![](https://files.readme.io/27b8b5acfe9691d3704ae36b04e28ecaa643e1b68eb5e0a6f8be70f657b2c0d3-205275743.png)
6. **Instale** o aplicativo integrado no seu dispositivo.

   Uma atribuição não orgânica é mostrada no seu dashboard, no canal de mídia **AppsFlyer\_Test**, se a sua integração estiver correta.

   ![](https://files.readme.io/4c6ab66ebd13556bd764d4e93adbb639be208b8955dd1fe1d3dd60ecd5c01a3b-205275823.png)

<div data-zendesk-anchors="overview=escrit%C3%B3rios how-does-the-tvos-test-app-work=como-o-aplicativo-de-teste-do-tvos-funciona" />

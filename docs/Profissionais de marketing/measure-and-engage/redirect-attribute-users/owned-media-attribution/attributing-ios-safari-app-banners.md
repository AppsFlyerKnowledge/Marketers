---
title: Atribuição de Banners de Aplicativo do Safari no iOS
metadata:
  keywords:
    - iOS Safari
    - Smart App Banner
    - Advertisers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-01-02T15:08:07Z'
  edited_at: '2026-11-02T01:16:58Z'
  id: 115000171743
  locale: pt
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/pt/articles/115000171743
---
> **Em resumo:** o Safari implementa o recurso <Anchor target="_blank" href="http://developer.apple.com/library/ios/#documentation/AppleApplications/Reference/SafariWebContent/PromotingAppswithAppBanners/PromotingAppswithAppBanners.html">Banner de Aplicativo</Anchor> que fornece uma maneira padronizada de promover aplicativos na Apple App Store. **Isso não está relacionado à solução recomendada de** <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">**Smart Banner**</Anchor> **da AppsFlyer.**

> 📘 **Atenção**
>
> Recomendamos usar os Smart Banners da AppsFlyer para converter visitantes da web em usuários do aplicativo.
>
> AppsFlyer Smart Banners:
>
> * Compatível com todos os navegadores
> * São personalizáveis
> * Funciona em todos os dispositivos Android e iOS

## Banner de Aplicativo para iOS

Usando o iOS 6 e versões posteriores, você pode implementar Banners de Aplicativo no Safari para promover aplicativos disponíveis na App Store.

**Exemplo de banner no Safari**

<Image alt="AppleBanner_en-us.jpg" src="https://support.appsflyer.com/hc/article_attachments/49929553421073" width="278px" />

Antes de implementar Banners de Aplicativo no iOS, considere o seguinte:

* Não implemente simultaneamente o Banner de Aplicativo no iOS e os Smart Banners da AppsFlyer. Isso pode resultar em problemas de exibição no seu site web mobile.
* A solução de banner de aplicativo é específica para iOS, o que significa que não funciona no OS X.
* O banner de aplicativo funciona apenas no Safari.

### Configurar uma página web com um banner de aplicativo e um link de atribuição de clique

1. Insira o seguinte no elemento de cabeçalho do HTML da página web.

   ```
   Etapa 1<meta name="apple-itunes-app" content="app-id=123456789">:
   ```
2. Gere um link de atribuição para o app mobile que você está promovendo no App Banner. Você pode usar o <Anchor target="_blank" href="/marketers/pt/docs/onelink-smart-script-overview">AppsFlyer SmartScript</Anchor> para essa finalidade; ele gerará dinamicamente um link de atribuição com base nos parâmetros UTM recebidos. Veja a seguir um exemplo que mostra um link de atribuição para o app mobile promovido no banner de aplicativo. Você também pode usar <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">links de atribuição personalizados encurtados</Anchor>.

   ```http
   https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign
   ```
3. Insira o link de atribuição gerado em um pixel de imagem. Seu pixel de imagem com a URL de mensuração é formatado conforme ilustrado.

   ```
   Etapa 1<img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />:
   ```

   A página HTML final com o pixel de imagem deve aparecer como mostrado no exemplo de HTML a seguir.

   ```html Markup
   <html>
     <head>
       <meta name="apple-itunes-app" content="app-id=123456789">

     </head>
     <body>
       <p>Este é o meu site</p>
       <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />
     </body>
   </html>
   ```

**Nota!** Este código carrega e executa um clique em dispositivos iOS e Android. Para desativar o código em dispositivos Android, adicione a lógica necessária ao seu código.

<div data-zendesk-anchors="h_01M63G1712D0HXWH688309CDQB=aten%C3%A7%C3%A3o ios-app-banner=banner-de-aplicativo-para-ios h_01M63G1713KMRCGZFNPB7CDRVX=banner-de-aplicativo-para-ios setting-a-web-page-with-an-app-banner-and-click-attribution-link=configurar-uma-p%C3%A1gina-web-com-um-banner-de-aplicativo-e-um-link-de-atribui%C3%A7%C3%A3o-de-clique h_01M63G1713H59N0GGD2R82DPT8=configurar-uma-p%C3%A1gina-web-com-um-banner-de-aplicativo-e-um-link-de-atribui%C3%A7%C3%A3o-de-clique" />

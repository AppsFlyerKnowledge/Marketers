---
title: Configuração de anúncios de instalação mobile do Instagram
metadata:
  keywords:
    - Facebook
    - Instagram
    - install ads
    - integrated partner
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-09T01:10:44Z'
  edited_at: '2026-08-18T00:30:51Z'
  id: 207034066
  locale: pt
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/pt/articles/207034066
---
> **Resumo:** Adicione anúncios de instalação mobile do Instagram à sua conta do Meta Ads.

<Image alt="instagram_logo.jpg" src="https://files.readme.io/55ab80e2b1ba9d164d978116f3aaaacb9fe7e4571f71e0130a40e1ded16679db-360000492725.jpg" width="101px" />

## Configurando o Instagram

A configuração do Instagram está na lista do Meta Ads na seção “Integrações ativas” da AppsFlyer.

Você pode conferir a documentação da Meta <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/guides/instagramads/">neste link</Anchor> e <Anchor target="_blank" href="https://www.facebook.com/business/help/1634705703469129">neste outro link</Anchor>.

1. Vincule sua conta do Instagram ao Gerenciador de Negócios da Meta  

   ![vincular-inst-com-conta_fb.png](https://files.readme.io/c6c7fe17274f0b9af008c4452b4b7ea2233cc5bca8773307fef6afaeb7d06015-11212956311441.png)
2. Depois de adicionar no Business Manager, atribua uma conta de anúncios à sua conta do Instagram  

   <Image alt="atribuir-anuncio-inst-ao-fb.png" src="https://files.readme.io/658dc57d0056a2217a9f0f5c785b87e24c297158b75c5815eddb64930d00ea17-11213052873745.png" width="550px" />
3. Configure o Meta Ads em “Integrações ativas” ao adicionar seu App ID do Facebook.
4. Se você não tiver um App ID do Facebook, crie um <Anchor target="_blank" href="https://developers.facebook.com/apps">aqui</Anchor>.  
   [![id_app_facebook.png](https://files.readme.io/2e497e1e00c22d0006aebd540b24c47ba4f2907ee9de061dc04ab50bbbe2cc67-14069602144273.png)](https://support.appsflyer.com/hc/article_attachments/49722356592913)

## Landing page do Instagram para deep linking

Atualmente, o <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Instagram é compatível com deep linking em aplicativos iOS através de Universal Links</Anchor> para anúncios estáticos (fora do catálogo). Os Universal Links do iOS e os App Links do Android só funcionam em campanhas onde o **app** é selecionado como destino.

Se você precisa usar links personalizados com deep linking no Instagram em campanhas onde o **app** não pode ser selecionado. Por exemplo, se você configurar uma campanha de awareness na Meta (que não permite que o **app** seja selecionado como destino), os Universal Links e os App Links não funcionam. Você pode <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">configurar uma landing page do Instagram</Anchor>. Isso permite que você use o OneLink com Universal Links para deep linking no Instagram, melhorando a experiência dos usuários.

Para anúncios dinâmicos, Universal Links, App Links e esquemas de URI podem ser usados conforme descrito <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads">neste link</Anchor>.

<div data-zendesk-anchors="setting-up-instagram=configurando-o-instagram instagram-landing-page-for-deep-linking=landing-page-do-instagram-para-deep-linking" />

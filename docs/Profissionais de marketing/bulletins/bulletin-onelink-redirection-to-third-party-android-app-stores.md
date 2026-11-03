---
title: 'Boletim: redirecionamento do OneLink para app stores do Android de terceiros'
metadata:
  keywords:
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
  created_at: '2021-04-08T08:39:22Z'
  edited_at: '2026-10-20T03:57:02Z'
  id: 360019130678
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/360019130678
---
| Novidades | Os templates do OneLink oferecem uma opção para redirecionar usuários que não possuem o seu aplicativo para app stores terceiras do Android. |
| --- | --- |
| Data de início | 19 de maio de 2021 |
| Onde | <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">Configuração de modelo do OneLink</Anchor> |
| O que | **Antes da alteração:** os templates do OneLink ofereceram opções para que usuários que não possuem o seu aplicativo fossem redirecionados para a Apple App Store, Google Play ou uma URL da web.<br /><br />**Após a alteração:** os templates do OneLink também oferecem opções para que usuários que não possuem o seu aplicativo sejam redirecionados para as seguintes app stores terceiras ao Android:<ul><li>Huawei AppGallery</li><li>Xiaomi Market</li><li>Samsung Galaxy Store</li><li>Oppo App Market</li><li>Loja de aplicativos Vivo</li></ul> |
| O que você deve saber | <ul><li>O redirecionamento para app stores terceiras do Android exige que seu aplicativo nas outras stores tenha o mesmo nome de pacote que o aplicativo Android selecionado no template do OneLink.</li><li>O nome do pacote APK (por exemplo: com.shop.app) é usado para o redirecionamento, então verifique se o nome do pacote APK existe na app store terceira antes de selecioná-lo.</li><li>Somente o nome do pacote é extraído do aplicativo Android para redirecionar os usuários. Por exemplo, se o nome da AppsFlyer também incluir um canal, como com.shop.app-store, somente com.shop.app é extraído. Nesse caso, o redirecionamento funciona, mas a atribuição não.</li><li>Se você selecionar um aplicativo do Android que não esteja no Google Play, é necessário inserir uma URL para a qual todos os usuários do Android serão redirecionados.</li></ul>[![](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)<ul><li>Se o seu aplicativo Android estiver disponível exclusivamente por meio de uma loja de terceiros, <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">você deve definir o status no Google Play como “Published out of store” ao adicionar o aplicativo.</Anchor> Escolher qualquer outro status impedirá o redirecionamento para a loja terceirizada e resultará em uma mensagem de erro.</li></ul> |
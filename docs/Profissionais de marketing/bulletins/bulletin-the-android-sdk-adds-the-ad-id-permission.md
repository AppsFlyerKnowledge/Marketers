---
title: 'Boletim: O SDK do Android adiciona a permissão AD_ID'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-12T08:57:45Z'
  edited_at: '2026-08-18T00:21:11Z'
  id: 7569900844689
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/7569900844689
---
> **Visão geral:** A partir do Android SDK V6.8.0 da AppsFlyer, a permissão AD\_ID é declarada no AndroidManifest.xml do SDK.

| **CONTEXTO** | No início de 2022, o Google anunciou uma alteração no comportamento do Google Play Services e na obtenção do ID de publicidade do Android.<br /><br />De acordo com o <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6048248?hl=en">anúncio</Anchor>os aplicativos destinados ao Android 13 (API 33) e superior terão de declarar uma permissão normal do Google Play Services no seu arquivo de manifesto para terem acesso ao Advertising ID do dispositivo.<br /><br />A permissão é concedida ao aplicativo no momento da instalação e não aciona qualquer interação do usuário. |
| --- | --- |
| **O que vai mudar?** | A partir do Android SDK V6.8.0 da AppsFlyer, a permissão AD\_ID é declarada no AndroidManifest.xml do SDK. Quando o aplicativo é criado, o manifesto do SDK funde-se com o manifesto do seu aplicativo por predefinição e a permissão é adicionado mesmo que o aplicativo não declare explicitamente a permissão. Se a permissão existir tanto no aplicativo como no SDK, isso funciona bem, não haverá colisão. |
| **O que você precisa saber** | <ul><li>Se você estiver usando o SDK V6.8.0 e tiver a permissão AD\_ID no Manifesto do seu aplicativo, você pode opcionalmente removê-la do manifesto e deixar que o SDK a adicione para você.</li><li>Se você estiver usando uma versão do SDK **anterior** à V6.8.0 e o seu aplicativo segmentar o Android 13 (API 33) e superior, você deve adicionar a permissão AD\_ID ao seu aplicativo para permitir que o SDK tenha acesso ao Advertising ID.</li><li>**Aplicativos dirigidos a crianças:** De acordo com a <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/11043825?hl=en">Política do Google</Anchor>, os aplicativos dirigidos a crianças não devem transmitir o Advertising ID. Se você estiver criando um aplicativo para crianças e estiver usando o SDK V6.8.0 e superior, você deve revogar a permissão AD\_ID. Consulte as instruções do desenvolvedor <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission">aqui</Anchor>.</li></ul> |
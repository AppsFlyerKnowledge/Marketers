---
title: 'Bulletin : Le SDK Android ajoute l''autorisation AD_ID'
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
  edited_at: '2024-10-28T12:29:49Z'
  id: 7569900844689
  locale: fr
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/fr/articles/7569900844689
---
> **En bref :** Depuis la version V6.8.0 du SDK Android AppsFlyer, l'autorisation AD\_ID est déclarée dans le fichier AndroidManifest.xml du SDK.

| **Préambule** | Au début de 2022, Google a annoncé une modification dans le comportement des services Google Play et la récupération de l'ID publicitaire Android.<br /><br />Cette <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6048248?hl=en">annonce</Anchor> stipule que les applications ciblant Android 13 (API 33) et + devront déclarer une autorisation normale des services Google Play dans leur fichier manifeste afin d'avoir accès à l'ID publicitaire de l'appareil.<br /><br />L'autorisation est accordée à l'app au moment de l'installation, elle ne demande aucune interaction de la part de l'utilisateur. |
| --- | --- |
| **Ce qui change** | Depuis la version V6.8.0 du SDK Android AppsFlyer, l'autorisation AD\_ID est déclarée dans le fichier AndroidManifest.xml du SDK. Lorsque l'app est créée, le manifeste du SDK fusionne par défaut avec le manifeste de votre application, et l’autorisation est ajoutée même si l'app ne la déclare pas explicitement. Si l'autorisation est présente à la fois dans l'app et dans le SDK, tout fonctionne parfaitement : il n'y a pas de conflit. |
| **Ce que vous devez savoir** | <ul><li>Si vous utilisez le SDK V6.8.0 et que vous avez l'autorisation AD\_ID dans le manifeste de votre app, vous pouvez éventuellement la supprimer du manifeste et laisser le SDK l'ajouter pour vous.</li><li>Si vous utilisez une version du SDK **antérieure** à la V6.8.0 et que votre application vise Android 13 (API 33) et +, vous devez ajouter l'autorisation AD\_ID à votre app afin de permettre au SDK d'accéder à l'ID publicitaire.</li><li>**Applications pour le jeune public :** Selon le <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/11043825?hl=en">Règlement de Google</Anchor>, les applications destinées au jeune public ne doivent pas transmettre d’ID publicitaire. Si vous créez une application pour le jeune public et que vous utilisez le SDK V6.8.0 et +, vous devez révoquer l'autorisation AD\_ID. Les instructions à l’attention des développeurs se trouvent <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission">ici.</Anchor></li></ul> |
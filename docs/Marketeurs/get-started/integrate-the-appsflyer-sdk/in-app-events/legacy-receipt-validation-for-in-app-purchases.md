---
title: Validation de Reçu pour iOS
deprecated: true
metadata:
  keywords:
    - iOS
    - Android
    - Receipt
    - Validation
    - Receipt Validation
    - SDK
    - Advertisers
    - Developers
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
  created_at: '2015-02-26T10:30:58Z'
  edited_at: '2022-01-25T17:18:00Z'
  id: 207032106
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/207032106
---
A partir de la version 2.5.3.12 du SDK d’AppsFlyer, vous pouvez procéder à la validation des achats dans l’App Store.

Le flow de validation est le suivant :

1. Un utilisateur procède à un achat in-app.

2. Apple Store répond par succès ou échec (authentification)

3. Le développeur appelle la fonction de validation dans le SDK (validateAndTrackInAppPurchase) avec réception des données.

4. Le SDK appelle le service de validation d’AppsFlyer avec réception des données.

5. Le service de validation d’AppsFlyer valide la transaction avec les serveurs d’Apple.

6. Les serveurs d’Apple répondent par succès ou échec.

7. Le service de validation d’AppsFlyer transfère la réponse au SDK.

8. Le SDK transfère le reçu de validation à l’app.

Ci-dessous, un extrait de réponse du validation du reçu:

<Image align="center" alt="Screen Shot 2015-02-26 at 12.26.45.png" src="/attachments/token/l41yw5RpWECWHtGnSdx3SsUbU/?name=Screen+Shot+2015-02-26+at+12.26.45.png" />
---
title: 'Bulletin : prise en charge de SKAN 4 dans AppsFlyer'
metadata:
  keywords:
    - iOS
    - Marketers
    - SKAN
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2023-08-28T09:08:31Z'
  id: 11938810583825
  locale: fr
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/fr/articles/11938810583825
---
| **Sujet** | La solution SKAdNetwork d'AppsFlyer prend désormais en charge SKAN 4. Cela inclut des modifications majeures dans le Studio de conversion SKAN, ainsi que dans les tableaux de bord et les rapports SKAN. |
| --- | --- |
| **Date d'entrée en vigueur** | <ul><li>15 février 2023 : avec le SDK iOS natif V6.10+.</li><li>Nous recommandons la mise à jour vers la version la plus récente (V6.12+), même si vous utilisez la version V6.10 depuis février.<ul><li>Vous pouvez consulter la liste des changements <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-ios-sdk-release-notes">ici</Anchor></li></ul></li><li>Prochainement : prise en charge d'autres SDK et plugins AppsFlyer</li></ul> |
| **Conditions préalables** | Pour que les données de SKAN 4 iOS soient correctement enregistrées, les éléments suivants sont nécessaires :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/appsflyer-ios-sdk-release-notes">AppsFlyer SDK version V6.12.1+.</Anchor></li><li>Le réseau publicitaire doit générer une signature publicitaire pour SKAdNetwork V4.</li><li>Pour les publicités qui s'affichent dans une application, l'app doit être créée avec le SDK iOS 16.1 ou -+.</li><li>Pour les publicités sur le web, la publicité nécessite Safari 16.1 ou +.</li><li>L'application annoncée doit être signée par l'App Store et fonctionner sur un appareil équipé d'iOS 16.1 ou +.</li></ul> |
| **Actions requises** | <ul><li>Mettez à jour votre <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-ios-sdk-release-notes">SDK AppsFlyer vers la version V6.12.1+.</Anchor></li><li>Dans AppsFlyer SKAN Conversion Studio, passez au <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#skan-4">mode de mesure SKAN 4</Anchor> et configurez les CV pour les 3 fenêtres SKAN (ou conservez les paramètres par défaut).</li></ul>**Remarque :** Une fois que vous aurez effectué la mise à niveau vers SKAN 4 :<ul><li>Le délai d'activité pour les installations pré-SKAN 4 est de 48 heures.</li><li>Vous ne pouvez pas revenir à une version antérieure de SKAN.</li></ul> |
| **Modifications dans <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#skan-4">SKAN Conversion Studio</Anchor>** | Nouveau mode de mesure SKAN 4 pour configurer les 3 fenêtres SKAN |
| **Changements dans les <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">tableaux de bord</Anchor>** | <ul><li>Le tableau de bord SKAN comprend de nouveaux champs (disponibles dans les paramètres du tableau) pour le nombre d'événements et les revenus au cours des 3 fenêtres SKAN :<ul><li>Nombre d'événements J0-J2</li><li>Nombre d'événements J0-J2 (modélisé)</li><li>Nombre d'événements J3-J7</li><li>Nombre d'événements J8-J35</li><li>Revenus J0-J2 ($)</li><li>Revenus J0-J2 ($) (modélisé)</li><li>Revenus J3-J7 ($)</li><li>Revenus D8-D35 ($)</li></ul></li><li>Le tableau de bord SSOT affiche les champs de données J2, au lieu de la fenêtre d'activité (AW). Pour les données SKAN 3, ce champ affiche toutes les données de la fenêtre d'activité, même si la fenêtre est plus large ou plus courte que 2 jours.</li></ul> |
| **Modifications dans les <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">rapports</Anchor>** | <ul><li>Les rapports SKAdNetwork incluent les nouveaux champs suivants pour prendre en charge SKAN 4 :<ul><li>**skad\_postback\_sequence\_index**: la valeur est un nombre entier qui représente la fenêtre SKAN, soit0`,`1 , soit 2. Pour SKAN 3, la valeur est `0`.</li><li>**skad\_coarse\_conversion\_value**:lavaleur peut être`inférieure`,`moyenne` ou`élevée`. Pour SKAN 3, la valeur`est nulle`.</li><li>**skad\_source\_identifier**: la valeur est une chaîne de 4 chiffres maximum. Pour SKAN 3, la valeur est`nulle`.</li><li>**skad\_source\_domain**: la valeur est une chaîne de caractères qui représente la source des publicités web attribuables. Pour SKAN 3, la valeur est `nulle`.</li><li>**ad\_network\_creative**: la valeur est une chaîne basée sur l'enrichissement des données reçues du réseau publicitaire. Pour SKAN 3, la valeur est vide.</li></ul></li><li>Les rapports Data Locker et Push API suivants sont concernés :</li></ul><ul><li>**skad\_installs** (via Data Locker et Push API)</li><li>**skad\_redownloads** (via Data Locker et Push API)</li><li>**skad\_inapps** (via Data Locker et Push API)</li><li>**skad\_postbacks** (via Data Locker)</li><li>**skad\_postbacks\_copy** (ne comprend pas le champ ad\_network\_creative) (via Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">Voir les exemples de schémas de rapport</Anchor></li></ul><ul><li>L'API de la date d'arrivée du postback agrégé SKAN et l'API du rapport de performance agrégé SKAN contiennent des champs SKAN 4. **Remarque** : Vous devez utiliser le chemin d'accès au jeton API V2 pour SKAN 4.</li></ul> |
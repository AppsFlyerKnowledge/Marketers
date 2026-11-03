---
title: Attribution Android pour les Apps Préinstallées
metadata:
  keywords:
    - Android
    - Pre-Install
    - Attribution
    - Metrics
    - Advertisers
    - Agencies
    - af_pre_install_name
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
    - Agencies
  created_at: '2014-10-13T11:14:04Z'
  edited_at: '2022-01-25T17:20:02Z'
  id: 207032166
  locale: fr
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/fr/articles/207032166
---
AppsFlyer permet aux annonceurs de traquer les métriques des apps pré-installées sur les appareils Android au moment de leur achat.

Quand une app est lancée, elle est listée dans le tableau de bord d’AppsFlyer sous une source média custom (comme indique dans l’exemple ci-dessous) avec le nom de campagne ‘preinstall’.

**Note** : si un utilisateur met à jour l’app depuis la boutique avant d’ouvrir l’application pour la première fois, cela sera enregistré comme une installation organique (pas en tant que pré-installée).

**Configuration du tracking pre-install** :

Pour configurer un APK pour pre-install, ajoutez l’entrée suivante dans l’AndroidManifest.xml avant de fermer la section ‘application’ (au-dessus du tag &lt;/application>).

**Exemple**:

`<meta-data android:name="AF_PRE_INSTALL_NAME" android:value="VODAFONE"/>`

Dans cet exemple, la valeur ‘VODAFONE’ sera liste en tant que ‘mediao source’ d’AppsFlyer.
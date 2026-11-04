---
title: Soutenir la politique de consentement de Google pour l'UE
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2024-02-07T07:28:17Z'
  edited_at: '2024-09-18T17:37:30Z'
  id: 22310731147153
  locale: fr
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/fr/articles/22310731147153
---
> **En bref :** AppsFlyer aide les annonceurs à se conformer à la Loi sur les marchés numériques (DMA) et à améliorer la valeur de leurs publicités sur Google. Trouvez des réponses aux questions fréquemment posées sur la conformité avec la DMA et l'optimisation de la valeur des publicités.

<div id="overview" />

## Présentation

Google met à jour sa <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">politique de consentement des utilisateurs dans l'UE</Anchor> en préparation de l'application de la <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">Loi sur les marchés numériques</Anchor> (DMA). En tant que <Anchor target="_blank" href="https://ads.google.com/lp/appcampaigns/attribution/">partenaire de</Anchor> Google <Anchor target="_blank" href="https://ads.google.com/lp/appcampaigns/attribution/">Attribution</Anchor>, AppsFlyer s'adapte aux changements de politique tout en permettant aux annonceurs de tirer le meilleur parti de leurs publicités sur Google. La politique actualisée est en vigueur depuis le 6 mars 2024.

<div id="relevant-integrations-and-continued-use-of-google-features" />

## Intégrations pertinentes et utilisation continue des fonctionnalités de Google

<div id="which-integrations-are-involved" />

<Accordion title="Quelles sont les intégrations concernées ?">

Les intégrations suivantes sont liées à la nouvelle politique de consentement de Google pour l'UE :

* Google Ads (`googleadwords_int`)
* GMP DV360 (`dv360_int`)

Si les utilisateurs finaux de vos applications provenant de ces intégrations se trouvent dans l'Espace économique européen (EEE), veillez à prendre les mesures nécessaires pour respecter les exigences de la nouvelle politique de consentement de Google pour l'UE.

<div id="note" />

> 📘 **Remarque**
>
> L'intégration [ancienne] de Google Marketing Platform DV360/CM (`doubleclick_int`) sera obsolète et ne sera plus prise en charge selon la nouvelle politique de consentement de Google pour l’UE. Si vous utilisez cette intégration, nous vous recommandons de <Anchor target="_blank" href="/marketers/fr/docs/bulletin-google-marketing-platform-gmp-integration-transition">passer à la nouvelle intégration DV360 (dv360\_int).</Anchor>

</Accordion>

<div id="what-must-i-do-to-continue-using-googles-features" />

<Accordion title="Comment continuer à utiliser les fonctionnalités de Google ?">

Les marketeurs doivent obtenir le consentement des utilisateurs finaux dans l'EEE pour l'utilisation de leurs données personnelles afin de continuer à utiliser les fonctionnalités de mesure, de personnalisation des publicités et de remarketing de Google Ads et GMP DV360.

</Accordion>

<div id="updating-the-appsflyer-sdk" />

## Mise à jour du SDK AppsFlyer

<div id="what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk" />

<Accordion title="Étapes nécessaires à la mise en œuvre des données de consentement via le SDK AppsFlyer">

Le SDK AppsFlyer (v6.13.1+) peut envoyer les données de consentement nécessaires avec chaque événement pour répondre aux exigences de Google.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">Mettez à jour votre SDK</Anchor> vers la dernière version (v6.13.1+), applicable aux applications Android ou iOS.
* Une fois le SDK mis à jour, <Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">voir ici</Anchor> les instructions d'implémentation pour la conformité avec la DMA.

</Accordion>

<div id="sending-consent-data" />

## Envoi des données de consentement

<div id="how-do-i-send-consent-data-to-appsflyer" />

<Accordion title="Comment envoyer les données de consentement à AppsFlyer ?">

Les marketeurs ont deux options pour envoyer les données de consentement requises à AppsFlyer :

* **[Directement via le SDK](#mise-à-jour-du-sdk-appsflyer) ou une API S2S :** Les marketeurs peuvent envoyer les données de consentement directement à AppsFlyer en utilisant le SDK. Applicable aux applications Android ou iOS.
* **Via TCF Strings :** Les marketeurs qui utilisent ou prévoient d’utiliser une plateforme de gestion du consentement (CMP) peuvent transmettre les champs de données via les chaînes standard IAB TCF (TCF V2.2). Veillez à inclure l'identifiant du fournisseur Google (755) dans la liste des fournisseurs autorisés.

AppsFlyer permet ensuite aux clients de transmettre les signaux de consentement à Google. Cependant, il est important de noter qu'AppsFlyer ne recueille pas, ne modifie pas et ne contrôle pas le consentement de l'utilisateur final. Les marketeurs qui travaillent avec Google sont responsables de la collecte des champs de consentement nécessaires.

Voir <Anchor target="_blank" href="https://appsflyer.wistia.com/medias/0tnlyre8ai">cette vidéo</Anchor> sur la façon d'envoyer des données de consentement à AppsFlyer.

</Accordion>

<div id="which-consent-values-does-appsflyer-send-to-google" />

<Accordion title="Valeurs de consentement qu'AppsFlyer envoie à Google">

Les valeurs de consentement de l'utilisateur final sont envoyées à Google pour les intégrations AppsFlyer concernées (`googleadwords_int`et `dv360_int`) en utilisant les champs suivants :

| Champ AppsFlyer | Champ Google (1) | Valeurs | Le champ expliqué |
| --- | --- | --- | --- |
| <span id="gdpr_applies"></span>gdpr\_applies | eea | true/false (2) | La DMA s'applique-t-elle à cet utilisateur ? |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true/false | L'utilisateur a-t-il donné son accord à Google pour que ses données soient utilisées à des fins de publicité personnalisée ? |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true/false | L'utilisateur a-t-il donné son accord pour que ses données soient transmises à Google ? |

1. Voir <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">la définition de Google pour chaque champ.</Anchor>
2. Lorsque la DMA ne s'applique pas à l'utilisateur, AppsFlyer suggère de s'abstenir d'envoyer des champs de consentement autres que `gdpr_applies=false`

</Accordion>

<div id="sending-consent-datafaq" />

### Envoi des données de consentement - FAQ

<div id="do-i-have-control-over-consent-data-for-nonue-users" />

<Accordion title="Existe-t-il une option permettant de ne pas envoyer les données de consentement à Google ?">

AppsFlyer permet aux annonceurs, lorsqu'ils estiment que les exigences de la DMA ne s'appliquent pas à leurs utilisateurs finaux (par exemple lorsqu'ils ne sont pas ressortissants de l'UE), d'empêcher l'envoi de données de consentement à Google. Pour ce faire, il suffit d'activer une option dans les pages d'intégration concernées.

<div id="important" />

> 🚧 **Attention !**
>
> Avant d'utiliser cette option, il est recommandé d'obtenir l'approbation des équipes chargées des questions juridiques et de la protection de la vie privée afin de s'assurer qu'elle est conforme à leurs politiques. Voir l'<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">article du mode de consentement</Anchor>  de Google pour les définitions de référence.

**S'abstenir de partager les données de consentement avec Google :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégration active**.
2. Recherchez le partenaire et cliquez sur **Gérer l'intégration**.
3. Dans l'onglet Configuration de l'intégration, activez l'option **Utilisateurs non-UE**.

<Image alt="non eu usrs.png" src="https://files.readme.io/6e86882f209773d7e8ca0ff801c23fd70ab0e3511c69b1a47c0ea48e0dd710db-22361665421713.png" width="595px" />

</Accordion>

<div id="is-consent-needed-for-mobile-web-events" />

<Accordion title="Le consentement est-il nécessaire pour les événements web mobiles ?">

À ce stade, seuls les événements liés aux applications mobiles sont partagés avec Google. Il n'est donc pas nécessaire d'obtenir le consentement d'AppsFlyer pour les événements web. Si les utilisateurs passent du web à votre application, leur consentement sera recueilli ultérieurement dans l'application.

</Accordion>

<div id="which-countries-does-googles-eu-consent-policy-cover" />

<Accordion title="À quels pays s'applique le consentement Google DMA ?">

Selon la <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">Commission européenne</Anchor>, la Loi sur les marchés numériques (DMA) s'applique aux utilisateurs de l'UE et de l'EEE (Espace économique européen), ce qui a <Anchor target="_blank" href="https://www.gov.uk/eu-eea">un impact sur ces pays.</Anchor> Sur la base de ces informations, il convient de noter que **la DMA ne s'étend pas au Royaume-Uni et à la Suisse.**

</Accordion>

<div id="whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way" />

<Accordion title="Quelle est la méthode recommandée pour demander le consentement de l'utilisateur dans le respect des règles ?">

AppsFlyer recommande de consulter votre équipe juridique afin d'obtenir le consentement d'une manière conforme à la DMA. Bien que <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14009343?hl=en&sjid=3762335249108620505-NC#app-consent">Google fournisse des instructions générales</Anchor>, il ne propose pas de texte spécifique pour les invites.

</Accordion>

<div id="how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags" />

<Accordion title="Comment AppsFlyer traduit-il les chaînes TCF en indicateurs de consentement Google DMA ?">

Après qu’AppsFlyer reçoit les chaînes TCF de ta CMP (soit via le SDK AppsFlyer, soit par S2S), elles sont traitées et traduites sur les serveurs d’AppsFlyer. La traduction suivante est mappée et envoyée à Google, comme le recommande Google :

| AppsFlyer a collecté des chaînes de caractères | Indicateurs de consentement de Google | Description |
| --- | --- | --- |
| `gdpr_applies=1/0` | `eea=1/0` | Identifie si la DMA est applicable ou non pour l'utilisateur concerné. |
| `ad_user_data` | `ad_user_data=1` | Lorsque le consentement est donné à Google pour l'objectif 1 et que le consentement/l'intérêt légitime est donné à Google pour l'objectif 7 |
| `ad_user_data` | `ad_user_data=0` | Lorsque le consentement n'est pas donné à Google pour l'objectif 1 **et/ou que** le consentement/l'intérêt légitime n'est pas donné à Google pour l'objectif 7 |
| `ad_personalization` | `ad_personalization=1` `ad_personalization=0` | Lorsque le consentement est donné à Google aux fins des objectifs 3 et 4 Lorsque le consentement n'est pas donné à Google aux fins des objectifs 3 et 4 |

</Accordion>

<div id="if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk" />

<Accordion title="Dois-je mettre à jour les SDK AppsFlyer et Firebase pour envoyer les données de consentement ?">

Oui. Google exige que les données de consentement soient incluses dans chaque événement envoyé par AppsFlyer, car Google ne fusionne pas les données de consentement des utilisateurs provenant de Firebase avec celles envoyées par AppsFlyer. Par conséquent, les données relatives au consentement doivent être envoyées à AppsFlyer, qui les transmet à Google. De même, le partage des données de consentement avec AppsFlyer ne suffit pas à répondre aux exigences du SDK Firebase. Cela signifie que vous devez envoyer les données à la fois à AppsFlyer et à Firebase.

</Accordion>

<div id="preparing-for-the-upcoming-changes" />

## Se préparer aux changements à venir

<div id="how-can-i-prepare-for-the-upcoming-changes" />

<Accordion title="Étapes préparatoires">

<div id="address-user-consent-in-the-european-economic-area-eea" />

#### Traiter le consentement des utilisateurs dans l'Espace économique européen (EEE)

Collaborez avec le conseiller juridique de votre entreprise. Il peut fournir des informations sur les implications des politiques de consentement des utilisateurs européens concernant les données que vous partagez avec des partenaires comme Google. Si nécessaire, mettez en place des invites de confidentialité telles que « Paramètres de confidentialité » ou « Choix de confidentialité » pour recueillir les signaux de consentement des utilisateurs de votre application en ce qui concerne le marketing et la publicité.

<div id="verify-cmp-compliance-and-tcf-2223-support" />

#### Vérifier la conformité de la CMP et le support du TCF 2.2

Assurez-vous que votre plate-forme de gestion du consentement (CMP) prend en charge le TCF 2.2, qui est la version la plus récente du Transparency and Consent Framework (TCF). Votre TCF doit également être bien informé des nouvelles exigences de consentement de Google pour l'UE et peut vous conseiller sur la manière de les soutenir via le TCF.

<div id="implement-the-newest-sdkserver-to-server-s2s-apis" />

#### Mettre en œuvre les dernières versions des API SDK/Serveur-à-Serveur (S2S)

Envisagez les options suivantes pour envoyer les nouveaux champs de consentement, soit en utilisant le SDK, soit par des appels API S2S :

* **Utilisation du SDK :**
  * Mettre en œuvre la dernière version du SDK AppsFlyer (v6.13.1+) pour les applications iOS et Android
  * Choisir le mode d'<Anchor target="_blank" href="/marketers/fr/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">envoi des données de consentement</Anchor>
* **Utilisation des appels de l'API <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile?">S2S :</Anchor>**
  * Avant d'envoyer des événements in-app à AppsFlyer, mettez à jour vos appels API pour inclure l'objet `consent_data` pour chaque événement. Voir <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">comment procéder</Anchor>.

<div id="transition-from-the-legacy-gmp-integration-doubleclick" />

#### Transition depuis l'ancienne intégration GMP (DoubleClick)

Si vous utilisez encore l'intégration AppsFlyer GMP héritée (doubleclick\_int), prévoyez de terminer la transition vers la version plus récente (dv360\_int) d'ici le premier trimestre 2024. L'intégration de l'ancienne version **n**'est **pas compatible avec le consentement de l'UE** et sera bientôt abandonnée. Plus de détails <Anchor target="_blank" href="/marketers/fr/docs/bulletin-google-marketing-platform-gmp-integration-transition">ici.</Anchor>

</Accordion>

<div id="impact-on-advertising-activityfaq" />

## Impact sur l'activité publicitaire-FAQ

<div id="how-will-the-upcoming-change-impact-my-remarketing-campaigns" />

<Accordion title="Quel sera l'impact de ce changement sur l'attribution de mes campagnes ?">

Les utilisateurs de l'UE qui refusent que leurs données soient utilisées par Google à des fins publicitaires (`ad_user_data=0`) ne seront pas pris en compte par Google Ads et DV360. Cela signifie qu'AppsFlyer ne pourra pas les attribuer.

</Accordion>

<div id="how-will-the-upcoming-change-affect-my-audiences" />

<Accordion title="Comment le changement à venir affectera-t-il les audiences ?">

Cette modification peut avoir une incidence sur le nombre d'utilisateurs de l'EEE apparaissant dans vos audiences et exposés aux campagnes de remarketing de Google. Les utilisateurs basés dans l'EEE devront donner leur accord avant que leurs informations ne soient communiquées à Google. Les personnes qui n'ont pas donné leur accord seront exclues des audiences de Google et ne verront pas vos campagnes. Cela soulève la question de savoir comment obtenir le consentement de vos utilisateurs et quelles peuvent être les répercussions pour votre entreprise et vos efforts publicitaires. <Anchor target="_blank" href="/marketers/fr/docs/audiences-user-identifier-policy#eu-digital-markets-act">En savoir plus sur les changements apportés aux audiences</Anchor>.

</Accordion>

<div id="see-also" />

<div id="further-information-and-contact-details" />

## Informations complémentaires et coordonnées

Si vous avez d'autres questions ou des incertitudes, vous pouvez contacter les personnes suivantes :

* Pour connaître les exigences de Google ou savoir comment ces mises à jour peuvent avoir un impact sur vos données Google, veuillez consulter les <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy-help/">articles d'aide de Google</Anchor> ou contacter directement votre représentant Google.
* Pour toute question concernant la prise en charge par AppsFlyer des champs de consentement de l'utilisateur final dans l'UE, contactez votre CSM AppsFlyer ou écrivez à [hello@appsflyer.com.](mailto:hello@appsflyer.com)
* Voir l'<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">article de</Anchor> Google <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">sur</Anchor> le <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">mode de consentement pour</Anchor> les définitions de référence.

<div data-zendesk-anchors="overview=pr%C3%A9sentation h_01HP195KV35FD6X67WTMXJWWSZ=pr%C3%A9sentation relevant-integrations-and-continued-use-of-google-features=int%C3%A9grations-pertinentes-et-utilisation-continue-des-fonctionnalit%C3%A9s-de-google h_01HP1M37V1CYW5T5E4K1ES3NQA=int%C3%A9grations-pertinentes-et-utilisation-continue-des-fonctionnalit%C3%A9s-de-google 01HP1KN2H7NTS2V1S2PGF0C41N=which-integrations-are-involved h_01HP2HRPJR72Z0R5VEG5N36CN2=remarque h_01HP1K1088SJK60QRSTQF4WF6S=what-must-i-do-to-continue-using-googles-features updating-the-appsflyer-sdk=mise-%C3%A0-jour-du-sdk-appsflyer h_01HP1Z2G2M56DDQS9T47GMCFHJ=mise-%C3%A0-jour-du-sdk-appsflyer h_01HP1ZASRQGABCEFV67P961XAV=what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk how-consent-data-is-sent=envoi-des-donn%C3%A9es-de-consentement h_01HP1KPSMCH3EG373BWVQZM4ZT=envoi-des-donn%C3%A9es-de-consentement h_01HP1JJ2AYHYJET9GYMXA93E86=how-do-i-send-consent-data-to-appsflyer h_01HP1JJ2AYWRBREW5GD0KPDF1R=which-consent-values-does-appsflyer-send-to-google sending-consent-data%E2%80%94faq=envoi-des-donn%C3%A9es-de-consentement---faq h_01HR1X08VZ5MEAV01E9X54KAQS=envoi-des-donn%C3%A9es-de-consentement---faq h_01HP1JJ2AYZ57G0GMR8QRDTEZ7=do-i-have-control-over-consent-data-for-nonue-users h_01HP2MRPFA2ECJGAZ93NQHVD2J=attention- 01HVE9TVZWTRW3VQ8TSXWA13QM=is-consent-needed-for-mobile-web-events h_01HRXZYZJBDTP8CHJDHQ187CTN=whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way 01HR6SD3PBWN5X9AHT66ZADQ3R=how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags 01J2V4XRKRSEPA6KPJFMSTHE1F=if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk what-i-can-do-on-my-side=se-pr%C3%A9parer-aux-changements-%C3%A0-venir 01HR1XYXRDVEW6H9Q3WP17E2N3=se-pr%C3%A9parer-aux-changements-%C3%A0-venir h_01HP1JJ2AYFHRRDYZS8YFYE6WP=how-can-i-prepare-for-the-upcoming-changes address-user-consent-in-the-european-economic-area-eea-and-in-the-uk=traiter-le-consentement-des-utilisateurs-dans-lespace-%C3%A9conomique-europ%C3%A9en-eee h_01HPGNBQCTJFVZR99BY6E5J2JF=traiter-le-consentement-des-utilisateurs-dans-lespace-%C3%A9conomique-europ%C3%A9en-eee verify-cmp-compliance-and-tcf-22-support=v%C3%A9rifier-la-conformit%C3%A9-de-la-cmp-et-le-support-du-tcf-22 h_01HPGNC0HAMA7Z0B4DNV2QSFYG=v%C3%A9rifier-la-conformit%C3%A9-de-la-cmp-et-le-support-du-tcf-22 implement-the-newest-sdkservertoserver-s2s-apis=mettre-en-%C5%93uvre-les-derni%C3%A8res-versions-des-api-sdkserveur-%C3%A0-serveur-s2s h_01HPGNCAG3M9XPHDTP03WHQQ9F=mettre-en-%C5%93uvre-les-derni%C3%A8res-versions-des-api-sdkserveur-%C3%A0-serveur-s2s transition-from-the-legacy-gmp-integration-doubleclick=transition-depuis-lancienne-int%C3%A9gration-gmp-doubleclick h_01HPGNCHP6SSFCVZ3P4AG0N1FB=transition-depuis-lancienne-int%C3%A9gration-gmp-doubleclick impact-on-my-advertising-activity=impact-sur-lactivit%C3%A9-publicitaire-faq h_01HP1PKNZN32TQYHGJNNM3JFVZ=impact-sur-lactivit%C3%A9-publicitaire-faq h_01HP1PKNZN0VJGYAPFHR5JVV5H=how-will-the-upcoming-change-impact-my-remarketing-campaigns h_01HP4K2ZJW11BFSKNPRH7FA092=how-will-the-upcoming-change-affect-my-audiences further-information-and-contact-details=informations-compl%C3%A9mentaires-et-coordonn%C3%A9es h_01HQ2VJES04CYF4J8YBB4GQS73=informations-compl%C3%A9mentaires-et-coordonn%C3%A9es" />

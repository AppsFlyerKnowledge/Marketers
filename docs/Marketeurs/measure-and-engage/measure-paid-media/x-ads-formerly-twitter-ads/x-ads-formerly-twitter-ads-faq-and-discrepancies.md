---
title: >-
  Guide d'installation X Ads (anciennement Twitter Ads) - FAQ et problèmes de
  résultats
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:34:59Z'
  edited_at: '2023-11-24T14:22:07Z'
  id: 4410464352017
  locale: fr
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/fr/articles/4410464352017
---
> **En bref :** FAQ sur les écarts de résultats rencontrés avec X Ads.

<div id="x-ads-faq-and-discrepancies" />

## FAQ et écarts de résultats X Ads

<div id="who-can-perform-the-twitter-setup-on-appsflyer" />

<Accordion title="Qui peut réaliser la configuration sur AppsFlyer ?">

L'utilisateur qui autorise l'intégration entre AppsFlyer et Twitter doit posséder un accès d'administrateur de compte Twitter.

</Accordion>

<div id="what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer" />

<Accordion title="Que se passe-t-il si aucun compte Twitter n'est sélectionné pour l'attribution sur AppsFlyer ?">

Toutes les attributions sont pour les campagnes du compte sélectionné. Si aucun compte n'est sélectionné, aucun événement in-app ou attribution n'est envoyé à Twitter, même si le mappage de l'événement in-app est encore visible sur la fenêtre Configuration de Twitter.

</Accordion>

<div id="do-the-account-owner-and-the-team-members-see-the-same-twitter-data" />

<Accordion title="Le propriétaire du compte et les membres de l'équipe voient-ils les mêmes données Twitter ?">

Non. Le propriétaire du compte voit tous les comptes Twitter connectés. Les membres d'équipe voient uniquement leurs comptes Twitter connectés.

</Accordion>

<div id="how-do-i-disconnect-twitter-from-appsflyer" />

<Accordion title="Comment déconnecter Twitter d'AppsFlyer ?">

Il est possible de déconnecter AppsFlyer de votre compte Twitter. Les instructions suivantes sont valides si vous êtes connecté à votre compte Twitter via un navigateur d'ordinateur :

1. Connectez-vous à Twitter.
2. Dans le menu de gauche, cliquez sur **Autre** > **Paramètres et confidentialité**.
3. Rendez-vous dans **Sécurité et accès au compte** > **Apps et sessions** > **Apps connectées**.
4. Cliquez sur AppsFlyer.
5. Cliquez sur **Révoquer l'accès**.

Vous pouvez maintenant revenir à votre compte AppsFlyer et <Anchor target="_blank" href="/marketers/fr/docs/x-ads-formerly-twitter-ads-integration-setup">vous connecter un autre compte Twitter</Anchor> si vous le souhaitez.

</Accordion>

<div id="is-it-possible-to-attribute-installs-to-multiple-twitter-accounts" />

<Accordion title="Est-il possible d'attribuer des installations à plusieurs comptes Twitter ?">

Oui, mais des actions doivent être effectuées depuis Twitter. Une procédure doit d'abord être suivie :

Vous pouvez associer **un seul identifiant** (utilisateur X Ads) à votre compte AppsFlyer. Lorsque vous associez cet identifiant, votre compte X Ads s'affiche dans la configuration X Ads de votre tableau de bord AppsFlyer.

Si l'un de vos membres d'équipe possède également un compte X Ads, son identifiant est différent et il ne peut donc pas l'associer à AppsFlyer. En effet, **votre identifiant est le seul qui a déjà été associé à votre compte AppsFlyer**. Afin que son compte X Ads s'affiche également dans AppsFlyer, il doit **configurer votre identifiant comme administrateur du compte sur son compte X Ads**.

Imaginons que votre membre d'équipe s'appelle Jenny et que son identifiant soit @jenny. Votre identifiant est @nivi et est l'identifiant connecté à AppsFlyer. Afin que son compte X Ads s'affiche dans le compte AppsFlyer, **elle doit configurer votre identifiant comme admin du compte sur son compte X Ads**. Jenny doit donner accès à Nivi à son compte X Ads et non l'inverse. Une fois cette action effectuée, AppsFlyer examine l'identifiant de Nivi et voit tous les comptes publicitaires associés, y compris celui de Jenny.

1. Jenny se connecte à <Anchor target="_blank" href="http://ads.twitter.com/">ads.twitter.com</Anchor>
2. Elle clique sur **Compte** puis sélectionne **Modifier l'accès au compte**  

   <Image align="center" alt="twitter_assign_account2.PNG" src="https://support.appsflyer.com/hc/article_attachments/4416810336785" />
3. Jenny octroie ensuite à @nivi l'accès à son compte X Ads en tant qu'admin du compte  

    <Image align="center" alt="twitter_edit_access_to_account.png" src="https://support.appsflyer.com/hc/article_attachments/4416810307601/twitter_edit_access_to_account.png" />
4. Jenny se connecte à son compte AppsFlyer et va dans Integrations actives >> option Twitter
5. Elle peut alors voir que son compte X Ads est également listé.
6. Elle peut maintenant choisir son compte X Ads et configurer l'intégration. L'admin du compte peut voir tous les comptes X Ads connectés.  

   Ce que voit Jenny :

   <Image align="center" alt="jennys_ads_account.png" src="https://support.appsflyer.com/hc/article_attachments/4416824257041" />

   Ce que voit l'administrateur :

   <Image align="center" alt="jennys_ads_account__1_.png" src="https://support.appsflyer.com/hc/article_attachments/4416833416337" />

</Accordion>

<div id="any-special-instructions-for-agencies" />

<Accordion title="Des instructions particulières pour les agences ?">

Oui.   
Lorsqu'une agence crée une nouvelle campagne Twitter, le nom de la campagne doit commencer par le nom de l'agence et un trait de soulignement (Exemple : « AgencyName\_Campaign1 »).

> 📘 **Note**
>
> Pour établir la connexion entre AppsFlyer et Twitter, l'annonceur DOIT configurer Twitter afin de permettre aux agences d'exécuter le trafic de Twitter.

Pour plus de détails, allez <Anchor target="_blank" href="/partners/fr/docs/about-agency-accounts#configurations-srn">ici</Anchor>.

</Accordion>

<div id="do-you-make-twitters-raw-data-available-to-agencies" />

<Accordion title="Les données brutes de Twitter sont-elles accessibles aux agences ?">

Nous ne fournissons pas les données brutes de Twitter aux agences car, dans les conditions d'utilisation de Twitter, les agences sont considérées comme des tiers.

</Accordion>

<div id="im-clicking-save-close-but-twitters-configuration-is-not-saved-help" />

<Accordion title="Je clique sur Enregistrer et fermer mais la configuration de Twitter n'est pas enregistrée ! Que faire ?">

Si votre app était abonnée à un autre prestataire d'attribution dans le passé, utilisé pour attribuer les installations de Twitter, les erreurs suivantes apparaissent lors de la configuration de Twitter sur le tableau de bord d'AppsFlyer :

**Erreur : L'app est associée à un prestataire d'attribution différent. Veuillez l'associer à AppsFlyer.**

L'erreur suivante peut également apparaître :  

 <Image align="center" alt="" src="https://support.appsflyer.com/hc/article_attachments/360001502209/X%20Ads_error_2.png" />

**Erreur : Une erreur s'est produite lors de l'enregistrement de la configuration de Twitter. Certains comptes n'ont pas été mis à jour : XX Plusieurs ID de prestataire sont identiques (appid, conversionType) pour l'événement appid2872.**

Si la sélection de compte ne s'enregistre pas, il se peut que le compte Twitter en question ait été précédemment associé à un différent prestataire du côté de Twitter. Pour résoudre ce problème :

* Contactez Twitter pour supprimer l'autre prestataire de votre côté
* Sélectionnez le nom du compte actif
* Cliquez sur **Enregistrer et fermer**.
* Si cela ne résout toujours pas le problème, vous devrez contacter votre prestataire de mesures précédent et lui demander de supprimer les anciennes balises Twitter associées à votre compte.

</Accordion>

<div id="how-can-i-set-up-retargeting-campaigns-with-twitter" />

<Accordion title="Comment puis-je configurer des campagnes de retargeting avec Twitter ?">

Pour plus de détails sur la façon de configurer une campagne de retargeting Twitter, cliquez ici.

</Accordion>

<div id="does-retargeting-affect-inapp-events-sending-to-twitter" />

<Accordion title="Le retargeting affecte-t-il les envois d'événements in-app à Twitter ?">

Oui. Si le retargeting est activé, AppsFlyer n'envoie pas les postbacks d'événements af\_app\_opened à Twitter, à sa demande.   
Notez que même si la fenêtre de configuration de Twitter permet ce choix, les postbacks af\_app\_opened ne sont pas envoyés avec le retargeting.

</Accordion>

<div id="how-can-i-stop-measuring-twitter-attributions" />

<Accordion title="Comment puis-je arrêter la mesure des attributions de Twitter ?">

Pour désactiver l'intégration à Twitter, décochez tous les comptes et cliquez sur **Enregistrer et fermer**.

</Accordion>

<div id="can-an-agency-measure-twitter-attributions-for-advertisers" />

<Accordion title="Une agence peut-elle mesurer les attributions de Twitter pour les annonceurs ?">

Oui !  
Pour établir la connexion entre AppsFlyer et Twitter, l'annonceur DOIT sélectionner un compte actif sur la page des partenaires de Twitter dans le tableau de bord d'AppsFlyer, de sorte qu'au moins un compte Twitter soit coché.  
Par la suite, l'agence doit connecter son compte Twitter directement à partir de son propre tableau de bord d'agence.

</Accordion>

<div id="can-an-agency-configure-inapp-events-for-twitter" />

<Accordion title="Une agence peut-elle configurer les événements in-app pour Twitter ?">

Les agences ne peuvent pas configurer les événements in-app pour Twitter.  Comme dans Meta Ads, ils doivent être configurés par l'annonceur.

</Accordion>

<div id="for-how-long-do-you-keep-twitter-s-userlevel-data" />

<Accordion title="Combien de temps conservez-vous les données de niveau utilisateur de Twitter ?">

Twitter demande aux prestataires d'attribution de supprimer ses données de niveau utilisateur 3 mois après l'installation. Cela signifie que les évènements effectués par ces utilisateurs 3 mois après l'installation de l'app sont considérés comme organiques.

Les données agrégées passées restent les mêmes.

</Accordion>

<div id="why-do-i-see-duplicated-cost-data" />

<Accordion title="Pourquoi les données de coût sont-elles dupliquées ?">

Lorsque vous mettez en place une campagne sur Twitter, vous pouvez ajouter plusieurs apps à une même campagne. Lorsque Twitter rapporte les coûts, les données de coût total de la campagne s'affichent sous chaque app dans AppsFlyer, et ne sont pas divisées par application.

Par exemple, si vous lancez une campagne qui coûte 1 000  $ pour une app Android et une app iOS, alors un coût de 1 000 $ s'affiche dans le tableau de bord AppsFlyer pour les deux apps Android et iOS. Le coût n'apparait pas fractionné, ici ce serait 500  $ chacune.

Pour éviter de multiplier les coûts, il est recommandé de ne définir qu'une seule app par élément/campagne.

</Accordion>

<div id="im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message" />

<Accordion title="J'essaie d'associer mon compte Twitter à AppsFlyer, mais je reçois un message d'erreur">

Pour recevoir les données d'attribution d'AppsFlyer, votre compte Twitter doit être un compte publicitaire actif.

**Pour résoudre ce problème :**

1. Déconnectez-vous de Twitter.
2. Allez dans **Intégrations actives**.
3. Dans le **champ de recherche,** tapez «Twitter».
4. Cliquez sur l'icône Twitter,  
    la fenêtre de configuration du partenaire s'ouvre.
5. Dans l'onglet **Intégration**, cliquez sur **Activer le partenaire**.
6. Cliquez sur **Se connecter avec Twitter**, une fenêtre de connexion Twitter s'ouvre.
7. Connectez-vous avec votre compte X Ads.

</Accordion>

<div id="discrepancies-between-x-ads-and-appsflyer" />

## Différences entre Twitter et AppsFlyer

Bien que nous travaillions en étroite collaboration avec Twitter, des différences peuvent apparaître entre le tableau de bord Twitter et le tableau de bord/les rapports AppsFlyer.

Les annonceurs doivent être conscients des raisons courantes de telles différences :

| Cause | Twitter | AppsFlyer |
| --- | --- | --- |
| **Fenêtres d'attribution** | Twitter permet à ses utilisateurs de configurer la fenêtre d'attribution et prend en charge les attributions post clic et post vue. Par défaut : post clic de 14 jours et post vue de 1 jour. | Si vous n'avez pas configuré la fenêtre rétrospective d'attribution AppsFlyer pour Twitter avec les mêmes valeurs que dans Twitter, des différences peuvent survenir. |
| \*\*Attribution  <br />de sources multi-canaux\*\* | L'attribution de Twitter fonctionne comme spécifié ci-dessus, indépendamment des autres sources. | AppsFlyer utilise l'attribution du dernier clic (vous trouverez plus d'informations sur l'attribution AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">ici</Anchor>). |
| **Différences de fuseau horaire** | Le fuseau horaire de Twitter est défini par le fuseau horaire configuré pour l'application de l'annonceur. | Le fuseau horaire par défaut d'AppsFlyer est UTC±00:00, mais il peut être défini sur n'importe quel fuseau horaire par l'annonceur. |
| **Différences de temps d'installation** | Twitter affiche les installations en fonction de l'heure du clic (appelée « heure d'engagement »). | AppsFlyer affiche l'heure de la première app ouverte. |
| **Type de touch d'attribution** | L'attribution de Twitter est basée sur ses propres clics et impressions. | AppsFlyer donne la priorité à l'attribution post clic sur l'attribution post vue. Si Twitter compte une impression et si AppsFlyer est informé d'un clic supplémentaire dans la fenêtre d'attribution post clic, le clic provenant d'une autre source est attribué sur le tableau de bord d'AppsFlyer. Sur Twitter, l'impression est attribuée et est présentée sur son tableau de bord. |
| **Paramètres de partage de données Twitter** | Twitter permet à ses utilisateurs de ne PAS <Anchor target="_blank" href="https://twitter.com/settings/account/personalization">partager leurs données personnelles avec des tiers</Anchor>. Ces données incluent les publicités avec lesquelles ils interagissent.<br /><br />Les statistiques sur le tableau de bord Twitter reflètent tous les engagements, y compris les utilisateurs qui ont choisi de ne pas partager leurs données. | AppsFlyer affiche les données agrégées de ces utilisateurs Twitter, mais ne rapporte pas leurs données brutes au niveau de l'utilisateur (plus d'infos <Anchor target="_blank" href="/marketers/fr/docs/x-ads-formerly-twitter-ads-setup-guide-overview#confidentialité-des-utilisateurs-sur-x-ads">ici</Anchor>). |
| **Logique de réengagement de Twitter** | Twitter compte les utilisateurs uniques. Si un utilisateur se réengage plus d'une fois à la suite d'une même campagne, Twitter fait apparaitre ces engagements comme une seule et même conversion. | AppsFlyer comptabilise chaque instance de réengagement, ainsi dans ce cas, ces engagements apparaissent comme des conversions multiples. |

> 📘 **Note**
>
> En raison des <Anchor target="_blank" href="/marketers/fr/docs/implement-validation-rules-to-prevent-fraud">règles de validation d'AppsFlyer</Anchor>, les résultats peuvent être différents sur les tableaux de bord car certaines installations sont affichées sur Twitter, mais ne le sont pas sur le tableau de bord AppsFlyer.

<div data-zendesk-anchors="twitter-ads-faq-and-discrepancies=faq-et-%C3%A9carts-de-r%C3%A9sultats-x-ads h_01HE7S15F9YR28FBA1TYCE3N0X=faq-et-%C3%A9carts-de-r%C3%A9sultats-x-ads h_01HE7S15F9NSQJSP268B0WF0JP=who-can-perform-the-twitter-setup-on-appsflyer h_01HE7S15F9PFZ8CATJC5YWC6QP=what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer h_01HE7S15F989Y94YFJ7TGK7QN5=do-the-account-owner-and-the-team-members-see-the-same-twitter-data h_01HE7S15F9GNWTK2N50GAHN52Q=how-do-i-disconnect-twitter-from-appsflyer h_01HE7S15F9CE4F29R97EVCG791=is-it-possible-to-attribute-installs-to-multiple-twitter-accounts h_01HE7S15F9G4M44CB2Q1KQMJPJ=any-special-instructions-for-agencies h_01HE7S15F9VG8XMJE7YSNN245P=note h_01HE7S15F9A7BBAW8BNN6H4AKQ=do-you-make-twitters-raw-data-available-to-agencies h_01HE7S15F9MM26SGKMAPGDH9F8=im-clicking-save-close-but-twitters-configuration-is-not-saved-help h_01HE7S15F923NKTTCS3Z1C40B5=how-can-i-set-up-retargeting-campaigns-with-twitter h_01HE7S15F931EWS48QVCQYPBCH=does-retargeting-affect-inapp-events-sending-to-twitter h_01HE7S15F98VN1TS99751S34C5=how-can-i-stop-measuring-twitter-attributions h_01HE7S15F9MEKBKAQ3NA76TFKY=can-an-agency-measure-twitter-attributions-for-advertisers h_01HE7S15F921V3T885F39VSPCQ=can-an-agency-configure-inapp-events-for-twitter for-how-long-do-you-keep-twitter%E2%80%99s-userlevel-data=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F90RXSWJ7HV3GSJB65=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F9B39KV628NSD29P6P=why-do-i-see-duplicated-cost-data h_01HE7S15F9N3CCJEMAD2QB38F9=im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message discrepancies-between-twitter-and-appsflyer=diff%C3%A9rences-entre-twitter-et-appsflyer h_01HE7S15F9YWCY883DP9TEGQXK=diff%C3%A9rences-entre-twitter-et-appsflyer h_01HE7S15FAPS2696J3KQG3P3ME=note-1" />

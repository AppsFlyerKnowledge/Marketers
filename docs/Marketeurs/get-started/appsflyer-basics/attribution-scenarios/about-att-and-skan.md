---
title: Guide de démarrage rapide et FAQ pour iOS 14, ATT et SKAN
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2024-09-09T12:30:03Z'
  id: 360011890298
  locale: fr
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/fr/articles/360011890298
---
> **En bref :** Depuis iOS 14.5, Apple exige que vous implémentiez et respectiez les conditions <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">d’AppTrackingTransparency</Anchor> (ATT). ATT signifie que *si votre app collecte des données sur les utilisateurs finaux et les partage avec d’autres sociétés à des fins de suivi entre les apps et les sites web,* vous devez utiliser la boîte de dialogue de consentement ATT et obtenir le consentement de l’utilisateur dans l’app de l’éditeur et de l’annonceur. En l’absence de suivi, il n’est pas nécessaire d’afficher la boîte de dialogue pour le consentement.

<Image align="center" alt="iOS14-consent-pre-ATT-enforcement-6522_Cover-image_917x480.jpg" src="https://files.readme.io/622b57cf6b6b7ad9472b3d072f44d9b451e82fec6b0c918427e39e9e6700602e-360019478118.jpg" />

<div id="attribution-measurement-in-an-att-environment" />

## Mesure de l’attribution dans un environnement ATT

AppsFlyer vous fournit plusieurs méthodes d'attribution vous offrant une gamme complète de solutions d'attribution. L’exigence de consentement [ATT](/docs/about-att-and-skan#att-principles) impacte l’attribution dans le contexte des campagnes payantes d’application à application. Les annonceurs doivent donc utiliser une combinaison de solutions d’attribution et de reporting. 

Dans le cas des campagnes payantes d’application à application, [SKAN](/docs/about-att-and-skan#skan-solution-principles) fournit des résultats d’attribution déterministes. D’autres types de campagnes, tels que les médias propriétaires, les applications web et les annonces Apple Search Ads, utilisent les outils d’attribution traditionnels d’AppsFlyer. Ces derniers fournissent une mesure LTV à long terme, tandis que SKAN mesure les performances de l’utilisateur lors d’une courte post-installation. 

En résumé, pour obtenir une vue d’ensemble complète, utilisez à la fois les solutions traditionnelles SKAN et AppsFlyer car elles se complètent.

Cet article présente SKAN et ATT aux annonceurs. Il est destiné aux annonceurs déjà familiers avec la plateforme AppsFlyer.

<div id="skan-solution-principles" />

<Accordion title="Principes de la solution SKAN">

AppsFlyer fournit des résultats agrégés d'attribution iOS en utilisant les postbacks SKAN d'iOS. Ces postbacks sont envoyés par iOS aux réseaux publicitaires qui les transmettent ensuite à AppsFlyer. Les postbacks contiennent des enregistrements d'attribution anonymes auxquels s'ajoutent une valeur de conversion (CV) définie par l'annonceur. La CV correspond à la mesure de la qualité de l'utilisateur au cours d'une fenêtre initiale de post-installation.

La <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">solution SKAN AppsFlyer</Anchor> offre aux annonceurs :

* Des tableaux de bord avec les données SKAN ainsi que des rapports obtenus en agrégeant les postbacks de tous les réseaux publicitaires enrichis de différents types de données, comme le coût.
* La possibilité de contrôler (via le studio de conversion AppsFlyer) ce que la VC mesure sans avoir à modifier le code de l'application. La VC peut être utilisée pour mesurer les revenus, les engagements ou les événements de conversion.

**Les limites de SKAN**

* **Campagnes :** Ne prend pas en charge Apple Search Ads, les campagnes de promotion croisée et les installations web mobiles.
* **Période de mesure :** La période de mesure effective est limitée à quelques jours.

**Flux SKAN**

<Image align="center" alt="SKAN_flow_-_Affinity_diagram_2.png" src="https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png" />

1. L'annonceur définit les paramètres de mesure SKAN dans le Studio de conversion AppsFlyer.
2. L'utilisateur ouvre l'app pour la première fois.
3. Pendant chaque fenêtre, AppsFlyer définit la CV selon les actions de l'utilisateur et le schéma de CV qui a été défini.
4. Après la fermeture de la fenêtre, iOS envoie le postback au réseau publicitaire ainsi qu'une copie du postback à AppsFlyer. Le postback arrive après un certain délai :
   * Fenêtre de mesure 1 de SKAN 4 : 24-48 heures
   * Fenêtre de mesure 2-3 de SKAN 4 : 24-144 heures
   * Pour SKAN 3 : Pour SKAN 24 : 48-48 heures après la dernière augmentation de la valeur de la VC.
5. Les copies des postbacks envoyées directement de l'appareil iOS à AppsFlyer sont transmises au point de terminaison défini par l'annonceur. Voir Envoyer des copies de postbacks SKAN à AppsFlyer.
6. Le réseau publicitaire transmet les postbacks enrichis à AppsFlyer, ou bien le SRN communique les données de postback via API.
7. AppsFlyer valide et décode la VC. Les données décodées sont enregistrées et attribuées avant d’être mises à disposition dans AppsFlyer via les tableaux de bord, les rapports et les API.

</Accordion>

<div id="att-principles" />

<Accordion title="Principes ATT">

La fenêtre ATT permet aux annonceurs d’obtenir le consentement explicite de l’utilisateur afin de collecter et de partager leurs données. Depuis iOS 14.5, l'IDFA est disponible uniquement si l'utilisateur donne son consentement via l’invitation ATT.

Les applications de l’éditeur et de l’annonceur affichent l’invitation. Si l’utilisateur donne son consentement dans les deux apps, cela signifie qu’il accepte le *suivi* et que les annonceurs sont autorisés par Apple à suivre l’utilisateur entre les apps appartenant à différentes sociétés.

**Réglage de l’ATT**

L’ATT est défini sur l’une des valeurs répertoriées dans le tableau ci-dessous. Initialement, iOS définit ATT sur non déterminé ou restreint.

Considérez que l’utilisation de la demande de consentement pour convertir un utilisateur *non déterminé* à *autorisé* est facultative. Toutefois, si vous n’affichez pas l’invitation, vous ne pouvez pas obtenir *d’autorisation.*

| Valeur ATT | Consentement  <br />(IDFA disponible) | Remarques |
| --- | --- | --- |
| Restreint | Non | <ul><li>Déterminé par Apple en fonction de l’âge de l’utilisateur et d’autres critères. Ne peut pas être modifié par l’utilisateur de l’appareil.</li><li>L’invitation ne peut pas être affichée pour ces utilisateurs.</li></ul> |
| Non déterminé (jusqu’à iOS 14.4) | Oui | Valeur par défaut |
| Non déterminé<br /><br />(à partir d’iOS 14.5) | Non | Valeur par défaut |
| Refusé | Non | Se produit si l’une des conditions suivantes s’applique :<ul><li>Définir après l’affichage de l’invitation</li><li>L’utilisateur a désactivé l’option *Autoriser les applications à demander le suivi* (commutateur principal au niveau de l’appareil)</li><li>Avant l’installation d’iOS 14 sur l’appareil, le LAT était activé</li></ul> |
| Autorisé(e) | Oui | Définir après l’affichage de l’invitation |

**Conséquences de l’ATT**

En raison de l'ATT, de nombreux utilisateurs ne donneront pas leur consentement, l'IDFA ne sera pas disponible et le suivi ne sera pas autorisé. En conséquence, les annonceurs qui, jusqu'à iOS 14.5, se fiaient aux rapports d'attribution au niveau de l'utilisateur, doivent transférer une partie de leur analyse vers des méthodes et des rapports d'attribution agrégée. <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">Modèle d'attribution AppsFlyer</Anchor>.

Les données relatives à l’attribution d’une application proviennent de plusieurs sources. L’identifiant disponible et utilisé par chacune diffère. La plupart des données s’affichent à l’aide des outils d’attribution traditionnels. Toutefois, pour les installations attribuées à l’aide de SKAN, les rapports se font via le tableau de bord SKAN.

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="Quel tableau de bord a l’installation ?">

Dans iOS 14, une installation peut être attribuée à la fois aux tableaux de bord traditionnels et SKAN. De plus, selon le contexte de la source média, il peut être attribué comme organique dans un tableau de bord et comme non organique dans l’autre.

</Accordion>

<div id="ios-attribution-and-privacy-important-knowledge" />

## Connaissances importantes sur iOS 14

<div id="ios-attribution-skan-and-privacy-articles-and-links" />

#### Articles et liens iOS 14 et SKAN

| Secteur | Article | Intérêt particulier : FAQ, divergences, comparaisons |
| --- | --- | --- |
| SKAN | <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">Champs de données brutes SKAN</Anchor> | Données brutes supplémentaires, champs SKAN prenant en charge did\_win et SKAN 3.0 |
| SKAN | <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">Solution SKAN</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Délai entre l’installation de l’application et la mise à jour du tableau de bord</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#organic-metrics-in-the-context-of-skadnetwork">Métriques organiques dans le contexte de SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#appsflyer-attribution-vs-skan-attribution">Attribution AppsFlyer et attribution SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#faq-skan-discrepancies">FAQ Divergences SKAN</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/fr/docs/skan-interoperation">Interopérabilité avec les partenaires SKAN</Anchor> (section article) | <Anchor target="_blank" href="/marketers/fr/docs/skan-integrated-partners-list">Liste des partenaires SKAN intégrés</Anchor> |
| SKAN | <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-interoperation-with-meta-ads">Intégration des publicités Meta et d’AppsFlyer SKAN</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq">Dépannage et écarts</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook">Différences de mesure et de synchronisation</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/fr/docs/skan-interoperation-with-snapchat">Interopérabilité Snapchat et AppsFlyer SKAN</Anchor> | <Anchor target="_blank" href="/marketers/fr/docs/skan-interoperation-with-snapchat#discrepancies-guide">Guide des écarts</Anchor> |
| Confidentialité | <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Confidentialité avancée agrégée (CAA)</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework#fonctionnalités-affectées-par-la-caa">Fonctionnalités affectées par la CAA</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework#aap-central-switch">Désactivation et désactivation la CAA</Anchor></li></ul> |
| Confidentialité | <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">Sources média restreintes</Anchor> | <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">Champs de données brutes restreints</Anchor> |
| iOS 14 | <Anchor target="_blank" href="/marketers/fr/docs/preparing-for-the-app-store-review-nutrition-labels">Étiquettes nutritionnelles : préparez-vous à l’examen de l’App Store</Anchor> |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Configuration ATT dans l’application</Anchor> (aide aux développeurs du SDK) |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">À propos des réseaux d’auto-reporting (SRN) tels que Google, Meta ads, etc</Anchor> | <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#ios-145-srn-attribution">Où les installations SRN sont-elles signalées ?</Anchor> |
| Facturation | <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/billing/">Facturation pour les apps iOS</Anchor> |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="Impact d’iOS 14 sur l’attribution et la mesure">

<div id="metrics" />

#### **Métriques**

Considérez qu’en raison de l’ATT, les mesures relatives aux utilisateurs non consentants de l’ATT peuvent être affectées comme suit :

| Métriques | Augmenter | Diminuer | Remarques |
| --- | --- | --- | --- |
| Non organique vs organique | Organique | Non organique |  |
| Réinstallations et installations | Installations | Réinstallations |  |
| Retargeting | Installations organiques et événements in-app | Réengagements, réattributions |  |
| Apple Search Ads | -- | -- | Inchangé. Les utilisateurs consentants et non consentants sont attribués correctement. |

#### **Deep Linking**

Le deep linking différé utilisant <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-legacy-apis#deferred-deep-linking">l’ancienne méthode onConversionDataSuccess</Anchor> peut ne pas fonctionner pour iOS 14.5+, car il nécessite des données d’attribution qui peuvent ne pas être disponibles en raison de la protection de la confidentialité.

Nous vous recommandons d’utiliser <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">le deep linking unifié (DLU).</Anchor> La DLU est conforme aux normes de confidentialité iOS 14.5+ et ne renvoie que les paramètres pertinents pour le deep linking et le deep linking différé : `deep_link_value` et `deep_link_sub1`. Les paramètres d’attribution tels que `media_source`, `campaign`et `af_sub1-5` renvoient null et ne peuvent pas être utilisés à des fins de deep linking. <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/deep-linking-deferred-deep-linking/">En savoir plus</Anchor>

</Accordion>

<div id="faqios-attribution-and-att" />

## FAQ – iOS 14+

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="Qu’advient-il d’une app utilisant une version du SDK antérieure à la V6+ ?">

Si vous utilisez une version du SDK antérieure à la V6.0 :

* Les publicités SKAdNetwork et Apple Search ne fonctionneront pas.
* Si vous soumettez l’app à l’App Store, attendez-vous à ce qu’elle soit rejetée.

Pour les applications utilisant un SDK antérieur à la V6.10 : SKAN 4 ne fonctionnera pas.

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="Est-il obligatoire d’afficher l’invitation ATT ?">

Non. Vous n’avez besoin de demander le consentement ATT que si vous souhaitez *suivre* un utilisateur, collecter l’IDFA ou les deux.

</Accordion>

## FAQ—SKAN

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="Comment puis-je savoir quand je recevrai des postbacks et s’ils seront SKAN 3 ou SKAN 4 ?">

Le type de publication SKAN que vous recevez est déterminé par divers facteurs, notamment le mode que vous utilisez dans Conversion Studio, le réseau publicitaire que vous utilisez et la version iOS de vos utilisateurs.

Ces facteurs ont un impact sur :

* Version de postback : SKAN 3 ou SKAN 4. <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#principles-and-flow">En savoir plus</Anchor>
* Fenêtre 1 (AW) : Pour SKAN 4, c’est 48 heures. Pour SKAN 3, cela est basé sur la fenêtre d’activité. Remarque : Si Conversion Studio n’est pas SKAN 4, mais que la signature du réseau publicitaire l’est, la fenêtre est basée sur la fenêtre d’activité ou sur 48 heures, selon la valeur la plus basse.
* Délai du postback : Heures après l’installation, lorsque le postback SKAN arrive. Cela dépend du moment où la fenêtre est fermée. <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update">En savoir plus</Anchor>
* Minuterie roulante : Pour SKAN 3, la fenêtre d’activité peut être prolongée jusqu’à 63 jours ; Le postback n’arrive qu’après la fermeture de la fenêtre.

L’organigramme suivant explique cela plus en détail.

<Image align="center" alt="SKAN_4_matrix_-_Page_8__1_.png" src="https://files.readme.io/0dbd4cae34d9f9fed80dbe835485789dab75d46dbb38de055f454d01efb97350-13756140934545.png" />

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="Dans SKAN, suis-je limité à un certain nombre d’identifiants de source/ID de campagne par réseau publicitaire ?">

Oui. Auparavant, la limite était de 100 identifiants de campagne. Cependant, à partir de SKAN 4, les ID de campagne sont appelés identifiants de source hiérarchiques et la limite est de 10 000. L’identificateur de source est un entier à 4 chiffres.

Les réseaux publicitaires associent l’identifiant de source SKAN à leur ID de campagne.

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="Quel est le cas d’utilisation des données brutes SKAN ?">

* Utilisez des données brutes pour agréger des dimensions qui ne sont pas disponibles via des API agrégées.
* Ajustez facilement les processus d’importation de données brutes existants pour consommer les données brutes SPAN.

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="Pourquoi les valeurs de conversion que je reçois ne correspondent-elles pas à ma configuration dans AppsFlyer Conversion Studio ?">

Cela est généralement dû à un autre SDK dans votre app qui a la capacité de définir des valeurs de conversion, ce qui entre en conflit avec votre SDK AppsFlyer et les valeurs de conversion que vous avez configurées dans AppsFlyer. Assurez-vous de ne pas avoir un autre SDK intégré dans votre app qui définit des valeurs de conversion.

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="Pourquoi les données agrégées de mon tableau de bord SKAN ne correspondent-elles pas aux chiffres de données brutes de mes rapports SKAN Data Locker ?">

Cette divergence est due au fait que les rapports de Data Locker sont consultés au mauvais moment. La réception des données de Google peut prendre jusqu’à 13 jours. Et dans les rapports de données brutes, les données sont écrites le jour de leur réception, et non de manière cumulative. Par conséquent, pour obtenir des mesures correctes pour les installations relatives à une date spécifique, vous devez également consulter tous les rapports 13 jours après cette date.

Exemple : Dans le rapport du 12 juin, il affiche 100 installations de Google qui ont eu lieu le 11 juin. Dans le rapport du 24 juin, il est indiqué que 100 installations DE PLUS ont eu lieu le 11 juin. Vous devrez examiner tous les rapports des 13 derniers jours (du 12 au 24 juin) et les agréger en fonction de l’heure d’installation ou de l’horodatage du réseau publicitaire pour obtenir une lecture précise des 200 installations totales qui ont eu lieu le 11 juin.

</Accordion>

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/getting-started-onboarding-for-marketers#étape-4-configuration-de-lattribution">AppsFlyer : démarrer étape par étape</Anchor>

<div data-zendesk-anchors="attribution-measurement-in-an-att-environment=mesure-de-lattribution-dans-un-environnement-att h_01HE0C8YXSXSX003X0671Z97KZ=mesure-de-lattribution-dans-un-environnement-att h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=connaissances-importantes-sur-ios-14 h_01HE0C8YXS3BH109DF1Y1KNK5P=connaissances-importantes-sur-ios-14 ios-14-and-skan-articles-and-links=articles-et-liens-ios-14-et-skan h_01HE0C8YXSPZKBWXC51Z2636R0=articles-et-liens-ios-14-et-skan h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement metrics=m%C3%A9triques h_01HE0C8YXSJMYN81FKPCA8ATK7=m%C3%A9triques h_01HE0C8YXS6ADG1SQCMVP0W69B=deep-linking faq%E2%80%94ios-14=faq--ios-14 h_01HE0C8YXSV9VSK1NPG9RCTQW1=faq--ios-14 h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=faqskan h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=faqskan how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=articles-connexes" />

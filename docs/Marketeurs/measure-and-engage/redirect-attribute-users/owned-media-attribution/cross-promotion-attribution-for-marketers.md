---
title: Attribution des promotions croisées pour les marketeurs
metadata:
  keywords:
    - tracking
    - Advertisers
    - Cross Promotion
    - cross-promotion
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2017-08-30T13:26:03Z'
  edited_at: '2024-08-04T09:18:52Z'
  id: 115004481946
  locale: fr
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/fr/articles/115004481946
---
> **En bref :** Attribuez les installations des campagnes de promotion croisée qui font la publicité de vos apps sur les différentes apps dont vous êtes propriétaire.

![CrossPromo_userJourney](https://files.readme.io/4ecc5b536021355247c51f1a19b23d71623da9f9578387622d6c6f0a57d4801b-4404615401489.png)

<div id="about-cross-promotion" />

## À propos de la promotion croisée

La campagne de promotion croisée est ce qu’il y a de mieux pour promouvoir vos apps, ou diriger les utilisateurs vers les nouvelles apps produites par votre entreprise. Ces types de campagnes donnent souvent des taux de conversion et de rétention plus élevés que la plupart des autres sources de trafic. Comme la promotion croisée fait de la publicité sur des médias propriétaire, vous pouvez utiliser la [correspondance des ID d’appareil](/docs/cross-promotion-attribution-for-marketers#attribuer-une-promotion-croisée) pour attribuer de manière déterministe les nouvelles installations. L'attribution des promotions croisées est disponible dans tous les comptes, quel que soit votre forfait AppsFlyer.

L'image suivante montre le tableau de bord de l'app mise en avant, avec la répartition des résultats des campagnes lancées sur les médias propriétaire (**af\_cross\_promotion**) ainsi que les autres sources média. Vous pouvez voir que le nombre d'installations et le taux de conversion de la campagne de promotion croisée sont bien plus importants que chez les autres sources média.

[![CrossPromo_mediaSource](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)

<div id="how-does-cross-promotion-work" />

### Comment se passe la promotion croisée ?

1. L'utilisateur reçoit une publicité de promotion croisée sur une des apps appartenant à votre entreprise. La publicité met en avant une application qui appartient également à votre entreprise. La création publicitaire peut être une bannière, une vidéo ou tout autre objet cliquable.
2. [facultatif] Le <Anchor target="_blank" href="/marketers/fr/docs/cross-promotion-attribution-for-developers">SDK enregistre et envoie</Anchor> une impression de promotion croisée à AppsFlyer.
3. L'utilisateur clique sur la publicité.
4. Le SDK enregistre le clic et redirige l'utilisateur vers l'App Store, sur la page de l’app dont vous faites la publicité. Le clic enregistré par le SDK inclut déjà l'ID publicitaire de l'appareil.
5. **Une fois l'app dont vous faites la publicité installée et lancée, le tableau de [bord AppsFlyer](/docs/cross-promotion-attribution-for-marketers#tableau-de-bord-de-lapp-mise-en-avant) fait apparaître l'utilisateur nouvellement acquis au niveau de la source média af\_cross\_promotion.**
   * Pour modifier la valeur de la source média, votre développeur doit ajouter un paramètre personnalisé qui sera appelé `pid` avec la valeur que vous souhaitez. **Remarque** : sous Android, cela ne fonctionne qu’avec le SDK V6.4.2 et +.
   * L'app qui supporte l'installation ( l'application source), apparaît en tant qu'**ID de site** de cette source média.
6. Le SDK génère automatiquement un événement in-app.  
   Le nom de l’événement sous Android est `af_cross_promotion`, et sous IOS le nom est `af_cross_promotion_clicked`.

<div id="attributing-cross-promotion" />

## Attribuer une promotion croisée

AppsFlyer vous permet d'utiliser la correspondance des ID d’appareils comme méthode d'attribution pour enregistrer et attribuer les installations issues de vos campagnes de promotion croisée. Vous pouvez attribuer à la fois les impressions et les clics, ce qui vous permet de calculer le <Anchor target="_blank" href="/marketers/fr/docs/about-conversion-rates#les-étapes-du-tunnel-marketing-et-les-taux-de-conversion-1">taux post-clic</Anchor> ou le ratio installations/impressions.

L’ID d'appareil utilisé pour la correspondance dépend des éléments suivants :

* L'appareil et la version du système d'exploitation de l'utilisateur
* La version du SDK AppsFlyer dans l'app source

| Correspondance d’ID d'appareil pour une promotion croisée | Version de l'appareil/OS | Version du SDK | Remarques |
| --- | --- | --- | --- |
| IDFA | iOS 9 – 14.4 | V5.0.0+ |  |
| IDFV | iOS 14.5+ | V6.0.2+ | L'IDFV est collecté automatiquement, sans aucune autre action de la part du développeur. |
| GAID | Appareils Android dotés des services Google Play |  |  |
| OAID, ID Android, IMEI, ID Fire | Appareils Android non dotés des services Google Play |  |  |

<div id="setting-up-cross-promotion" />

## Mettre en place une promotion croisée

Pour configurer une attribution des promotions croisées, le marketeur et le développeur doivent collaborer pour implémenter un code supplémentaire dans le SDK AppsFlyer.

Le marketeur et le développeur doivent suivre les étapes suivantes :

| Étape | Role | Tâche | Détails |
| --- | --- | --- | --- |
| 1 | Marketeur | Choisissez les apps dans lesquelles vous souhaitez lancer la campagne de promotion croisée. | L'app source attribuée à l'installation apparaîtra en tant qu'**ID de site** dans le tableau de bord de l'app dont vous faites la publicité. |
| 2 | Marketeur | Décidez si vous souhaitez ajouter <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">des paramètres supplémentaires</Anchor>, comme la fenêtre rétrospective, le nom d’adset ou les paramètres de l'abonné. Transmettez ces noms et valeurs de paramètres supplémentaires au développeur. |  |
| 3 | Développeur | Implémentez le code dans le SDK. | La documentation destinée aux développeurs est disponible <Anchor target="_blank" href="/marketers/fr/docs/cross-promotion-attribution-for-developers">ici</Anchor>. |
| 4 | Marketeur | Dans le [tableau de bord de l'application mise en avant](/docs/cross-promotion-attribution-for-marketers#tableau-de-bord-de-lapp-mise-en-avant), consultez le trafic issu de la campagne de promotion croisée et optimisez vos campagnes en fonction des résultats. |  |
| 5 [Facultatif] | Marketeur | Créez un [tableau de bord personnalisé](/docs/cross-promotion-attribution-for-marketers#tableau-de-bord-personnalisé) pour comparer le trafic des promotions croisées et partager les données avec les utilisateurs du compte. |  |

<div id="viewing-cross-promotion-data" />

## Consulter les données des promotions croisées

<div id="promoted-app-dashboard" />

### Tableau de bord de l’app mise en avant

Le tableau de bord de l'application mise en avant vous permet de déterminer quelles apps sources génèrent le plus de trafic vers l'application au cœur de la publicité.

**Pour comparer le trafic provenant des apps sources, procédez comme suit :**

1. Accédez à la **vue d'ensemble**.
2. Sélectionnez la source média **af\_cross\_promotion** (ou votre source média personnalisée).
3. Regroupez par **ID de site** pour afficher la liste des apps sources. [![CrossPromo_SiteID](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)

<div id="analysis" />

#### Analyse

En consultant les données des installations, clics, impressions et taux de conversion des différentes applications qui font de la publicité pour une même application, vous pouvez obtenir des chiffres sur leur degré d’association. Les apps sources (ID de site) avec les meilleurs taux de conversion sont les plus associées à l'app mise en avant, leurs utilisateurs sont donc plus susceptibles de l'installer. Sur la base de ces informations, vous pouvez optimiser vos campagnes de promotion croisée.

<div id="example" />

> 📄 **Exemple**
>
> Vous êtes un marketeur spécialisé dans les apps de gaming pour PlayIt Gaming International. Vous disposez d'un certain nombre d'applications populaires, dont Bowling (com.playit.bowling) et Golf (com.playit.golf). Vous venez de lancer une nouvelle application nommée Billard. Vous décidez de lancer des tests en promotion croisée pour voir combien d'utilisateurs précis cliquent sur la publicité Billard dans l'une des autres apps. La campagne fonctionne bien sur Bowling, avec un taux de conversion de 7,92 %. Vous décidez donc de faire de la publicité également sur Golf.
>
> Lorsque vous consultez le tableau de bord, vous constatez que le taux de conversion pour Golf (18,22 %) est beaucoup plus élevé que le taux avec Bowling, vous en déduisez donc que Golf est plus associée à Billard, l’app au cœur de la publicité.
>
> [![CrossPromo_conversionRate](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)
>
> Sur la base de ces informations, vous pourriez optimiser votre campagne comme ceci :
>
> * Lancez une campagne de promotion croisée à grande échelle autour de Golf.
> * Commencez à <Anchor target="_blank" href="/marketers/fr/docs/measure-view-through-engagements#processus-dattribution-post-vue">attribuer les impressions</Anchor> en plus des clics. Comme vous avez initialement configuré votre campagne pour ne mesurer que les clics, les installations des utilisateurs qui voient la publicité sans cliquer, mais qui l'installent plus tard, sont considérées comme des installations organiques (et non comme des installations non organiques). Ce qui signifie que vous n’avez pas encore tous les éléments sur les performances des campagnes dans chaque application source.

<div id="custom-dashboard" />

### Tableau de bord personnalisé

Le tableau de bord de l'app mise en avant est idéal pour comprendre quelles apps sources génèrent le plus de trafic. Mais qu'en est-il si vous souhaitez évaluer les performances d'une application unique utilisée pour faire la publicité de plusieurs apps ? C'est là que le tableau de bord personnalisé entre en jeu.

Un <Anchor target="_blank" href="/marketers/fr/docs/custom-dashboards">tableau de bord personnalisé</Anchor> vous permet de centraliser les informations de plusieurs applications dont vous faites la publicité, ce qui inclut le trafic lié aux promotions croisées. De plus, avec le tableau de bord personnalisé vous pouvez rapidement partager les données avec les utilisateurs du compte.

<div id="example-1" />

> 📄 **Exemple**
>
> Vous êtes un marketeur pour eCommerce Apps, Ltd., et vous avez une application très populaire appelée Chaussures. Vous lancez maintenant 3 nouvelles applications, Accessoires, Vestes et manteaux, et Chaussures de sport. Vous décidez de lancer une campagne de promotion croisée dans l'application Chaussures pour voir laquelle de vos nouvelles apps aurait la meilleure pub.
>
> Vous divisez votre base d'utilisateurs en 3 segments. Chaque fois qu'un utilisateur lance l'application Chaussures, 1 des 3 publicité possibles s'affiche : 1 pour Accessoires, 1 pour Vestes et manteaux et 1 pour Chaussures de sport.
>
> Pour centraliser les résultats des 3 applications mises en avant, vous créez un tableau de bord personnalisé. Dans l'image suivante, vous pouvez voir que Chaussures de sport a un taux de conversion de 20,23 %, ce qui signifie que Chaussures est plus associée à Chaussures de sport qu'aux 2 autres applications dont elle fait la publicité.
>
> ![CrossPromo_customWidget](https://files.readme.io/9363a68994956bc19115f6f9babb9acb0c7d4fe75478683b2a45720987486956-4404613319953.png)

<div data-zendesk-anchors="about-crosspromotion=%C3%A0-propos-de-la-promotion-crois%C3%A9e h_01HE7RXZ2CZCYENE4K40W5YSHF=%C3%A0-propos-de-la-promotion-crois%C3%A9e how-does-crosspromotion-work=comment-se-passe-la-promotion-crois%C3%A9e h_01HE7RXZ2CE5EQV42Y4B9SK4FN=comment-se-passe-la-promotion-crois%C3%A9e attributing-crosspromotion=attribuer-une-promotion-crois%C3%A9e h_01HE7RXZ2CWB2GZ8HV6447RVV1=attribuer-une-promotion-crois%C3%A9e setting-up-crosspromotion=mettre-en-place-une-promotion-crois%C3%A9e h_01HE7RXZ2C9JGFYV8K8FECFFJN=mettre-en-place-une-promotion-crois%C3%A9e viewing-crosspromotion-data=consulter-les-donn%C3%A9es-des-promotions-crois%C3%A9es h_01HE7RXZ2CE9NWMQ1PT3G98QVN=consulter-les-donn%C3%A9es-des-promotions-crois%C3%A9es promoted-app-dashboard=tableau-de-bord-de-lapp-mise-en-avant h_01HE7RXZ2CQG9M35Y2FJNPZWDA=tableau-de-bord-de-lapp-mise-en-avant analysis=analyse h_01HE7RXZ2CVQD8H0J6EVRJM5T7=analyse h_01HE7RXZ2CW1P0QNA8FFXP5KBS=exemple custom-dashboard=tableau-de-bord-personnalis%C3%A9 h_01HE7RXZ2C7N3DKNPF898WM4AD=tableau-de-bord-personnalis%C3%A9 h_01HE7RXZ2C51KJMP795QYS26YK=exemple-1" />

---
title: 'Google Ads (AdWords) : coûts et revenus publicitaires'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-20T10:01:42Z'
  edited_at: '2023-10-27T11:12:46Z'
  id: 4417309205521
  locale: fr
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/fr/articles/4417309205521
---
> **En bref :** activer les données sur les coûts et les revenus publicitaires Google Ads dans AppsFlyer.

<div id="cost-data-sync-status" />

## État de synchronisation des données de coût

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Affichez le statut de votre API de coûts</Anchor> ainsi que la dernière fois où AppsFlyer a pu extraire les données de coûts correspondantes, soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), soit dans le tableau de bord du réseau publicitaire individuel.

Google Adwords vous permet de synchroniser plusieurs comptes pour extraire les données de coût. Pour chaque compte synchronisé, AppsFlyer indique l'état de l'intégration de coût ainsi que la dernière fois où AppsFlyer est parvenu à extraire les données de coût correspondantes.

<div id="stopping-google-cost-sync" />

### Arrêt de Google Cost Sync

**Pour arrêter la synchronisation des coûts Google, supprimez la connexion au compte Google :**

* <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Rendez-vous dans l'onglet Coût, dans la colonne Actions, survolez un compte, cliquez sur Supprimer la connexion.</Anchor> Une fois supprimée, AppsFlyer cesse de recevoir les coûts.Le fait de supprimer la connexion ne supprime pas les données historiques.

<div id="cost-clicks-and-impressions" />

## Coûts, clics et impressions

L'intégration des coûts fournit les données agrégées suivantes :

* Données sur les coûts pour vos campagnes, vos adsets, vos zones géographiques/pays et vos niveaux de canaux.Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts du réseau publicitaire</Anchor> pour obtenir plus d'infos sur les dimensions, les métriques et les fonctionnalités prises en charge.**Remarque :** Les données de coût nécessitent un abonnement <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Données sur les clics, les impressions et les données enrichies (mots-clés, noms de campagne et adsets).

> 📘 **Note**
>
> * Les comptes MCC sont pris en charge.
> * Les données relatives aux coûts, aux clics et aux impressions ne sont actuellement pas disponibles pour les campagnes de préinscription en raison des limitations de l'API Google Ads.

Pour afficher les données sur le coût, les clics et les impressions de Google Ads dans le tableau de bord AppsFlyer, connectez-vous via votre page de configuration Google Ads. Une fois la connexion établie, AppsFlyer interroge les montants de vos coûts, clics et impressions Google Ads pour toutes vos campagnes existantes.

En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">paramétrage des coûts dans Google Ads</Anchor>.

En savoir plus sur la façon dont Google définit les clics et les vues.

En savoir plus sur les <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6163740">limitations de Google Ads</Anchor>.

**Les données devraient arriver sous quelques heures une fois la configuration effectuée**.

> 👍
>
> <span id="h_01HDP2SMHJF86QK9CJTVABKTYW"></span>Les utilisateurs peuvent confirmer qu'ils sont connectés avec le compte Google Ads correct en vérifiant l'adresse e-mail qui apparaît dans le coin supérieur droit du tableau de bord Google Ads.
>
> ![short.png](https://support.appsflyer.com/hc/article_attachments/4417297915537)
> Si le compte Google Ads est un sous-compte d'un compte MCC, l'ID en haut à droite est l'ID du compte MCC, et l'ID du sous-compte se trouve dans le coin supérieur gauche.
>
> Si le compte n'est pas correct, déconnectez-vous du compte et connectez-vous à nouveau à l'aide de l'adresse e-mail d'un autre compte Google.

<div id="recording-ad-revenue-with-google-ads" />

## Enregistrement des revenus publicitaires avec Google Ads

L'intégration des revenus de Google Ads (AdWords) est obsolète depuis le 30 novembre 2020. Concernant les données relatives aux revenus publicitaires, les clients d'AdWords doivent migrer vers <Anchor target="_blank" href="/marketers/fr/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>.

<div id="faq" />

<Accordion title="FAQ">

| **Pourquoi ne puis-je pas voir mes données de coûts ?**<br /><br />Il y a peut y avoir plusieurs explications au fait que vous ne voyez pas les données :<ul><li>Lors de la connexion, il est important de vérifier que le bon compte Google est utilisé.<br />Si vous vous connectez avec le mauvais compte Google, aucun coût n'est extrait ou affiché. Dans ce cas, vous devez supprimer l'accès de l'application aux applications Google et vous connecter avec le compte approprié. Pour ce faire, suivez ces étapes :<ol><li>Cliquez sur l'URL suivante : <Anchor target="_blank" href="https://myaccount.google.com/permissions">https://myaccount.google.com/permissions</Anchor></li><li>Supprimez AppsFlyer Cost sur Google et reconnectez-vous.</li></ol></li><li>Dans certains cas, l'intégration des coûts de l'agence est activée mais ne génère pas de coûts parce que l'utilisateur de l'agence qui s'est connecté n'a pas accès au bon ID de client Google Ads. L'annonceur obtient donc des données incomplètes sur les coûts.</li></ul>Assurez-vous que l'utilisateur de l'agence qui se connecte à l'onglet Coût a accès à l'ID client Google Ads défini dans l'onglet Intégration.<br /><br />[<Image alt="" src="https://support.appsflyer.com/hc/article_attachments/5991137319441" width="457px" />](https://support.appsflyer.com/hc/article_attachments/5991137319441)<ul><li>L'utilisation d'espaces ou de caractères spéciaux dans les campagnes de recherche iOS ou de page de renvoi Android peut entraîner des problèmes de correspondance entre les données de coûts et les données de clics, se traduisant par l'absence de rapport sur les coûts.</li><li>Lorsqu'une agence désactive une intégration de coûts après que les coûts ont déjà été collectés, mais que l'annonceur a toujours une intégration de coûts active, les données sont associées à l'annonceur à partir du jour où l'agence désactive l'intégration.</li></ul> |
| --- |
| **Où se trouvent les données de clics selon la zone géographique ?**<br /><br />Dans certains cas, AppsFlyer ne reçoit pas la totalité des données de clics selon la zone géographique de Google. Dans ce cas, AppsFlyer complète les informations manquantes sur les clics depuis d'autres sources Google, dépourvues des données géographiques. Par conséquent, lors du regroupement par géo (zone géographique), le nombre total de clics générés par les campagnes de Google peut ne pas correspondre au même nombre que celui défini dans une autre dimension de regroupement. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| Campagnes actives et inactives | L'intégration Google prend en charge les rapports de coûts pour les **campagnes inactives** dans les cas suivants :<ul><li>Campagnes d'installation d'applications (type campagne ACI)</li><li>Campagnes d'applications pour les engagements (type campagne ACE)</li></ul>Les campagnes inactives sont des campagnes pour lesquelles aucune installation ou conversion n'a été enregistrée dans AppsFlyer.<br /><br />Pour les campagnes non-ACI et non-ACE, AppsFlyer rapporte les coûts pour les **campagnes actives** uniquement, ce qui signifie qu'au moins une conversion ou installation est enregistrée dans AppsFlyer. Les coûts sont rapportés pour la fenêtre de 7 jours de la conversion/l'installation. |

</Accordion>

> 📄 **À consulter également**
>
> * Pour iOS 14, voir l'<Anchor target="_blank" href="/marketers/fr/docs/get-skan-postback-data-from-google-ads">interopérabilité entre Google Ads SKAdNetwork et AppsFlyer</Anchor>.

<div data-zendesk-anchors="cost-data-sync-status=%C3%A9tat-de-synchronisation-des-donn%C3%A9es-de-co%C3%BBt h_01HDP2SMHJT8Z6DP7BHC0Y5RRN=%C3%A9tat-de-synchronisation-des-donn%C3%A9es-de-co%C3%BBt stopping-google-cost-sync=arr%C3%AAt-de-google-cost-sync h_01HDP2SMHJPEDKKZF9SBXW56KG=arr%C3%AAt-de-google-cost-sync cost-clicks-and-impressions=co%C3%BBts-clics-et-impressions h_01HDP2SMHJ26S1BCER3KKZ8H14=co%C3%BBts-clics-et-impressions h_01HDP2SMHJB5YE5PCWVJVBAKHD=note recording-ad-revenue-with-google-ads=enregistrement-des-revenus-publicitaires-avec-google-ads h_01HDP2SMHKC9TSZZZPFFNK8TPH=enregistrement-des-revenus-publicitaires-avec-google-ads h_01HDP2SMHK8NH6M4T1A2Y79P55=faq h_01HDP2SMHKPDEE07H8WAP212TZ=traits-and-limitations h_01HDP2XBSEJVQ5G0MD0V5R05CM=%C3%A0-consulter-%C3%A9galement" />

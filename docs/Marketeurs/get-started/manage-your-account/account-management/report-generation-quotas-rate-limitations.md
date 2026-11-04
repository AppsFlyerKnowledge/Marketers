---
title: Quotas de production des rapports (limitations)
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2014-05-01T12:55:30Z'
  edited_at: '2023-11-12T12:52:18Z'
  id: 207034366
  locale: fr
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/fr/articles/207034366
---
> **En bref :** un principe de quota (seuil limite) limite le nombre de rapports qui peuvent être générés chaque jour via l'API Pull, et par la page d'exportation des données.

<div id="rate-limits-for-reports" />

## Seuils limite pour les rapports

Le nombre maximum de rapports pouvant être générés par jour et par type de rapport. Le quota varie en fonction de votre forfait d'abonnement.

**Les principes :**

* **Agences** : les rapports API Pull générés par les agences sont comptabilisés dans le quota d'annonceurs pour les rapports API Pull. Si vous atteignez souvent le seuil limite, contactez votre responsable de compte. Pour les rapports issus de la page des données d'exportation, les agences et les annonceurs ont un quota chacun.
* **Réseaux publicitaires** : les rapports générés par les réseaux publicitaires ne sont pas comptabilisés dans le quota des annonceurs.
* **Jour**: les chiffres sont calculés chaque jour à 00:00 UTC.

<div id="aggregated-and-analytics-reports" />

### Rapports agrégés et analytiques

| Outil de fourniture des données | Quota |
| --- | --- |
| API Pull agrégée | <ul><li>Jusqu'à 2 jours sur la période :<ul><li>1 appel maximum par minute, par app et par rapport</li></ul></li><li>Plage de dates de + de 3 jours, les appels sont limités comme suit :<ul><li>Maximum 120 appels par jour et par compte</li><li>24 appels par jour et par app</li></ul></li></ul> |
| Page des données d'exportation agrégées | Illimité |
| Master API | Illimité |
| API de cohorte | 60 appels par minute et par compte |
| Rapports agrégés SKAN | 60 appels par minute et par compte |

<div id="note" />

<div id="pull-api-raw-data-daily-quota" />

<div id="raw-data" />

### Données Brutes

* Un seuil différent s'applique à chaque outil de rapport, c'est à dire l'API Pull et la page d'exportation des données brutes.
* Pour l'API Pull, les rapports générés par les agences sont comptabilisés dans le quota des annonceurs. Pour les rapports issus de la page des données d'exportation, les agences et les annonceurs ont un quota chacun.
* Les quotas de l'API PULL s'appliquent par :
  * Rapport
  * Jour
  * Au niveau de l'application
  * Au niveau du compte
* Pour les annonceurs, les quotas dépendent de votre abonnement à AppsFlyer. **Remarque** : Les quotas s'appliquent également aux rapports qui nécéessitent un abonnement premium.
* Les rapports générés par les agences peuvent être comptabilisés dans le quota des annonceurs.
* Les quotas journaliers des réseaux publicitaires sont indiqués dans le tableau suivant.

Pour plus d'infos, consultez la FAQ qui suit le tableau.

<div id="ad-network-postback-reports-daily-quota" />

#### Quota quotidien de données brutes pour les réseaux publicitaires

| Groupe | Type de rapport  <br />(chaque type de rapport a un quota propre) | Quota au niveau de l'app | Quota au niveau du compte |
| --- | --- | --- | --- |
| Attribution | <ul><li>Installations organiques</li><li>installations non organiques</li><li>Les conversions par retargeting</li><li>Désinstallations</li><li>Revenus publicitaires attribués</li><li>Revenus publicitaires organiques</li><li>Revenus publicitaires de retargeting</li></ul> | 24 | Ne s'applique pas |
| Évènement in-app | <ul><li>Installations organiques</li><li>installations non organiques</li><li>Les conversions par retargeting</li><li>Désinstallations</li></ul> | 12 | Ne s'applique pas |

#### **FAQ**

* Q : Pour une application donnée, est-il possible de générer 24 rapports d'installation organiques via l'API Pull, et 24 rapports supplémentaires via la page d'exportation des données brutes ?  
  R : Oui. Chaque outil de reporting a un quota propre.
* Q : Pour une application donnée, est-il possible de générer 24 rapports d'installation organiques, plus 24 rapports d'installation non organiques, plus 24 rapports de conversion de retargeting ?R : Oui Chaque type de rapport a un quota propre.
* Q: Mon compte contient 25 apps. Est-il possible de générer 10 rapports d'installations organiques pour chaque application ?  
  R : Non. Cela fait un total de 250 rapports, qui dépasse le seuil maxi au niveau du compte qui est de 120.

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/data-availability-windows">Fenêtre de disponibilité des données</Anchor>

<div data-zendesk-anchors="rate-limits-for-reports=seuils-limite-pour-les-rapports h_01H9JNZFPSVXPKMEVR1ZR6PSYG=seuils-limite-pour-les-rapports aggregated-and-analytics-reports=rapports-agr%C3%A9g%C3%A9s-et-analytiques h_01H9JNZFPS62A5CFWSXVPN8XM5=rapports-agr%C3%A9g%C3%A9s-et-analytiques raw-data=donn%C3%A9es-brutes h_01H9JNZFPSPYWBB2MCZV2R2KX1=donn%C3%A9es-brutes ad-network-raw-data-daily-quota=quota-quotidien-de-donn%C3%A9es-brutes-pour-les-r%C3%A9seaux-publicitaires h_01H9JNZFPSYXZNW81BZTRDS576=quota-quotidien-de-donn%C3%A9es-brutes-pour-les-r%C3%A9seaux-publicitaires h_01H9JNZFPT76RAV8JBTY2K75V4=faq h_01HE7SW3VWRNVY1WFB4YCSAVY6=%C3%A0-consulter-%C3%A9galement" />

---
title: Mappage des événements in-app des Meta Ads
metadata:
  keywords:
    - Facebook
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
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2023-08-07T11:17:05Z'
  id: 4410480904081
  locale: fr
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/fr/articles/4410480904081
---
> **En bref :** envoyez les événements in-app riches de votre app depuis AppsFlyer vers Meta ads.

<div id="meta-in-app-events-mapping" />

## Mappage des événements in-app dans Meta.

Les annonceurs mappent leurs événements in-app, SDK ou Server-to-server, aux événements prédéfinis de Meta. Les annonceurs peuvent également envoyer à Meta des postbacks pour chaque <Anchor target="_blank" href="/marketers/fr/docs/measure-sessions">lancement d'app</Anchor> ou toute <Anchor target="_blank" href="/marketers/fr/docs/measure-uninstalls#mappage-de-lévènement-de-désinstallation">désinstallation d'app</Anchor> connue.

Les annonceurs pourront ainsi utiliser les capacités d'optimisation avancées de Meta, et créer des segments d'audience personnalisés ou Lookalike.

<div id="availability-limitations" />

<div id="mapping-ad-revenue-data-for-campaign-optimization" />

<div id="predefined-event-mapping" />

### Mappage des événements prédéfinis

Meta offre un <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names">large éventail d'événements</Anchor> qui sont déjà prédéfinis et peuvent être mappés.

Vous trouverez <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure">ici</Anchor> la liste des **événements in-app riches** qui peuvent être envoyés à Meta avec des paramètres supplémentaires fournissant **des informations sur la qualité des événements**.

Plus d'infos sur les <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup#inapp-event-mapping">événements de mappage dans Meta</Anchor>.

<Image align="center" alt="In-app_event_postbacks_en-us.png" src="https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png" />

Notez qu'il n'y a pas d'événement prédéfini pour envoyer les désinstallations à Meta ads. Pour envoyer des désinstallations, utilisez un [événement personnalisé](/docs/meta-ads-in-app-event-mapping#mappage-des-événements-in-app-personnalisés).

Vous trouverez ci-dessous la liste d'autres événements Meta prédéfinis qui n'ont pas de paramètres supplémentaires :

| Identifiant d'événement Meta | Description | Nom du SDK AppsFlyer recommandé |
| --- | --- | --- |
| Faire un don | Les fonds transmis à votre organisation ou cause. | af\_donate |
| Planifier | Prise de rendez-vous pour visiter l'un de vos sites. | af\_schedule |
| Envoyer candidature | La soumission d'une demande pour un produit, service ou programme que vous offrez, comme une carte de crédit, un programme éducatif ou un emploi. | af\_submit\_application |
| Trouver lieu | Lorsqu'une personne trouve l'un de vos emplacements via le Web ou l'application, avec l'intention de s'y rendre. Par exemple, rechercher un produit et le trouver dans l'un de vos magasins locaux. | af\_find\_location |
| Contact | Appel, SMS, e-mail, chat ou tout autre type de contact entre un client et votre entreprise. | af\_contact |
| Produit personnalisé | Personnalisation des produits via un outil de configuration ou une autre application dont votre entreprise est propriétaire. | af\_customize\_product |

<div id="custom-in-app-events-mapping" />

### Mappage des événements in-app personnalisés

AppsFlyer vous permet de mapper tous les événements in-app personnalisés à envoyer à Meta en utilisant l'option ID d’événement Meta PERSONNALISÉ.

Le nom et la valeur de l'événement (avec les paramètres de l'événement) configurés dans le SDK sont transmis tels quels à Meta et affichés sous le nom original de l'événement AppsFlyer SDK, et non comme personnalisés.

Veuillez noter que vous pouvez <Anchor target="_blank" href="https://www.facebook.com/business/help/2308889442692949?id=1716638325041491">utiliser ces événements pour optimiser vos campagnes</Anchor>.

<Image align="center" alt="" src="https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png" />

<div id="automatic-parameter-mapping-with-the-custom-event" />

### Mappage automatique des paramètres avec l'événement CUSTOM

Grâce à l'intégration étendue d'AppsFlyer avec Meta, la majorité des paramètres d'événement du SDK de base AppsFlyer sont automatiquement mappés sur les paramètres prédéfinis de Meta. Par exemple, le paramètre **af\_revenue** est converti en paramètre **valueToSum** dans Meta, ce qui vous permet d'envoyer un revenu par événement qui sera mesuré et optimisé pour Meta.

<div id="important" />

<div id="example-unified-format-compatible-with-meta-and-tiktok" />

<div id="note-1" />

<div id="send-complex-in-app-events-to-meta-ads" />

<div id="predefined-events-automatic-mapping-to-the-_valuetosum-parameter" />

> 📘 **Note**
>
> Le mappage automatique des paramètres peut différer entre l'évènement CUSTOM et les évènements prédéfinis.
>
> Pour les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure">évènements prédéfinis</Anchor>, **af\_price** est mappé à **\_valueToSum** dans certains cas (par exemple, `fb_mobile_add_to_cart`). Dans d'autres cas, **af\_revenue** est mappé à **\_valueToSum** (par exemple, dans `fb_mobile_purchase`).
>
> Pour les évènements mappés CUSTOM, **af\_price** est toujours mappé à **fb\_price**, et **af\_revenue** à **\_valueToSum**.

Le tableau suivant répertorie les paramètres d'événement AppsFlyer qui, lorsque mappés pour Meta via l'événement CUSTOM, sont automatiquement mappés sur les paramètres de Meta.

| Paramètre AppsFlyer | Paramètre Meta |
| --- | --- |
| af\_city | fb\_city |
| af\_class | fb\_travel\_class |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_content\_type | fb\_content\_type |
| af\_country | fb\_country |
| af\_currency | fb\_currency |
| af\_date\_a | fb\_checkin\_date |
| af\_date\_b | fb\_checkout\_date |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_description | fb\_description |
| af\_destination\_a | fb\_origin\_airport |
| af\_destination\_b | fb\_destination\_airport |
| af\_destination\_list | fb\_destination\_ids |
| af\_hotel\_score | fb\_hotel\_score |
| af\_level | fb\_level |
| af\_max\_rating\_value | fb\_max\_rating\_value |
| af\_num\_adults | fb\_num\_adults |
| af\_num\_children | fb\_num\_children |
| af\_num\_infants | fb\_num\_infants |
| af\_order\_id | fb\_order\_id |
| af\_payment\_info\_available | fb\_payment\_info\_available |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops |
| af\_preferred\_price\_range | fb\_preferred\_price\_range |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings |
| af\_price | fb\_price |
| af\_quantity | fb\_num\_items |
| af\_region | fb\_region |
| af\_registration\_method | fb\_registration\_method |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date |
| af\_returning\_departure\_date | fb\_returning\_departure\_date |
| af\_revenue | \_valueToSum |
| af\_search\_string | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | fb\_suggested\_destinations |
| af\_suggested\_hotels | fb\_suggested\_hotels |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |

<div id="important-1" />

<div id="event-and-parameter-limitations" />

## Limitations des événements et des paramètres

Les restrictions suivantes s'appliquent aux [événements que vous envoyez à Meta Ads](https://developers.facebook.com/docs/app-events/faq#limits) :

* Les caractères suivants ne sont pas autorisés :
  * Deux points (:)
  * Point (.)
  * Caractères non latins (anglais) : depuis le 12 janvier 2020, Meta ads rejette les caractères de l'alphabet chinois. AppsFlyer n'a pas encore testé les autres alphabets. Vous ne devez les utiliser qu'après avoir vérifié auprès de Meta ads s'il prend en charge ce type de caractères dans les postbacks.
* Les noms d'événements sont sensibles à la casse. Pour éviter les incohérences, assurez-vous d'utiliser le bon nom d'événement pour toutes les sources média et versions d'app.
* Nombre maximal de paramètres : 25.
* Longueur des noms et des paramètres d'événement : 2 à 40.
* Longueur maximale du paramètre : 100 caractères.
* Caractères autorisés : caractères alphanumériques, tirets du bas, traits d'union et espaces. N'utilisez pas de caractères non latins (hors anglais). L'utilisation de caractères non latins entraîne des incohérences dans les résultats.

Éléments à prendre en compte pour nommer un événement in-app :

* Les noms d'événements dans AppsFlyer peuvent refléter les noms d'événements Meta (par exemple fb\_price), cependant, ils ne doivent pas être envoyés en tant qu'événements CUSTOM à Meta.  
  **Par mesure de sécurité, évitez de donner aux événements des noms d'événements Meta.**
* Pour effectuer le mappage des postbacks d'évènement in-app avec Meta, vous devez obtenir les données d'évènement de toutes les sources, y compris organiques.

> 🚧 **Important !**
>
> À l'exception des paramètres ci-dessus, AppsFlyer envoie les données d'événements CUSTOM **telles quelles** à Meta. Il incombe au propriétaire de l'application de vérifier que les données relatives à l'événement sont conformes aux exigences de Meta et utilisent des paramètres Meta valides (voir le tableau ci-dessus). Sinon, ces paramètres ne seront pas envoyés à Meta.

<div data-zendesk-anchors="facebook-iae-mapping=mappage-des-%C3%A9v%C3%A9nements-in-app-dans-meta predefined-event-mapping=mappage-des-%C3%A9v%C3%A9nements-pr%C3%A9d%C3%A9finis custom-inapp-events-mapping=mappage-des-%C3%A9v%C3%A9nements-in-app-personnalis%C3%A9s automatic-parameter-mapping-with-the-custom-event=mappage-automatique-des-param%C3%A8tres-avec-l%C3%A9v%C3%A9nement-custom event-and-parameter-limitations=limitations-des-%C3%A9v%C3%A9nements-et-des-param%C3%A8tres" />

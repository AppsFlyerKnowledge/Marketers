---
title: API d'événements de serveur à serveur pour mobile (S2S mobile)
metadata:
  keywords:
    - iOS
    - Android
    - API
    - In-App
    - S2S
    - HTTP API
    - appsflyer_id
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-05-21T17:47:21Z'
  edited_at: '2024-05-06T08:41:10Z'
  id: 207034486
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/207034486
---
> **En bref :** envoyez les événements de vos serveurs à AppsFlyer pour mesurer les événements mobiles qui se produisent en dehors de l'app.

<Image align="center" alt="S2S_us-en.png" src="https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png" />

<div id="server-to-server-events-api-for-mobile" />

## API pour mobile d'événements de serveur à serveur

Pour les apps iOS, à partir d'iOS 14 vous devez envoyer le paramètre de système d'exploitation (OS).

La plateforme AppsFlyer attribue et enregistre les événements d'apps mobile qui sont envoyés par le SDK AppsFlyer et par les API. Utilisez l'API S2S pour signaler les événements qui ont lieu hors de l'app, par exemple pour un utilisateur qui renouvellerait son abonnement en utilisant votre interface web. Une fois enregistrés, les événements S2S sont disponibles sur toute la plateforme, y compris les tableaux de bord, les données brutes et les analyses. Pour les événements web de PBA, consultez <Anchor target="_blank" href="/marketers/fr/docs/web-server-to-server-events-api-for-pba-web-s2s">Le S2S mobile pour la PBA</Anchor>.

AppsFlyer remplit les événements S2S en se basant sur :

* Les valeurs envoyées dans le message S2S
* Certaines AppsFlyer valeurs d'attribution d'installation AppsFlyer, comme l'heure ou la source du média.

Pour envoyer des événements via l'API, dites à votre développeur de suivre les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">instructions sur l'API pour les événements de serveur à serveur.</Anchor>

<div id="populating-parameters" />

## Paramètres de remplissage

<div id="difference-between-organic-and-nonorganic" />

<Accordion title="Différence entre organique et non organique">

Lorsque AppsFlyer traite des événements in-app S2S, les champs d'attribution sont remplis en se basant sur l'ID AppsFlyer afin d'identifier l'événement d'installation qui a précédé les événements in-app.

Cela signifie que certaines données qu'AppsFlyer associe à des événements in-app S2S non organiques ne sont pas associées à des événements in-app S2S organiques.

<div id="h_01_including-user-agent-and-ip-address-in-s2s-events" />

<div id="increasing-the-volume-of-data-transactions" />

<div id="note-1" />

<div id="note" />

> 📄 **Exemple**
>
> Par exemple, si vous comparez les rapports de données brutes d'événements in-app S2S non organiques et organiques, les événements non organiques contiennent des données que les événements in-app organiques ne contiennent pas.
>
> Les événements in-app non organiques incluent les données concernant la source média, la campagne, le type de touch attribué et l'heure du touch attribué.
>
> Les événements in-app organiques quant à eux suivent une installation organique. Les installations organiques ne disposent pas de données relatives à la campagne ou source média, ni au type ou à l'heure de touch attribué.

</Accordion>

<div id="mapping-appsflyer-id-with-customer-user-id-cuid" />

<Accordion title="Mappage de l'ID AppsFlyer avec l'ID utilisateur du client (CUID)">

Une démarche en arrière-plan est requise pour obtenir les valeurs permettant de renseigner les paramètres. Vous trouverez ci-dessous comment obtenir l'ID AppsFlyer :

* L'ID AppsFlyer est obligatoire et sert à attribuer les événements.
* Il est généré dès qu'un utilisateur installe une app mobile pour la première fois.
* Pour pouvoir mapper votre CUID à l'ID AppsFlyer, vous devez définir le CUID dans l'app.

Pour connaître plus facilement l'utilisateur à l'origine de chaque évènement, procédez comme suit :

* <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">Définissez l'ID utilisateur du client</Anchor> lorsque l'utilisateur installe l'app.
* Les rapports de données brutes AppsFlyer contiennent le CUID et l'ID AppsFlyer. Pour l'obtenir, utilisez l'un des outils de livraison de données ou bien l'API Push AppsFlyer.
* Utilisez les rapports de données brutes pour comparer le CUID et l'ID AppsFlyer.
* L'ID AppsFlyer est disponible dans le SDK intégré à votre app (Android/iOS).
* Mappez l'ID AppsFlyer avec l'ID utilisateur du client dans vos systèmes internes (très important pour les futures utilisations).

Après avoir mappé l'ID AppsFlyer à votre CUID, vous pourrez facilement associer chaque utilisateur avec les événements qu'il a exécutés. Vous pourrez ensuite obtenir d'autres valeurs (valeur d'évènement, devise d'évènement, heure de l'évènement, etc.), puis envoyer l'évènement in-app de serveur à serveur.

</Accordion>

<div id="fetching-the-appsflyer-id" />

<Accordion title="Récupérer l'ID AppsFlyer">

`appsflyer_id` est un paramètre obligatoire dans les messages d’événement de serveur à serveur. AppsFlyer utilise ce paramètre pour attribuer l’événement à l’appareil d’origine et à la source média attribuée. Vous pouvez définir l’ID utilisateur en appliquant l'une des méthodes suivantes :

* Depuis un appareil mobile en appelant l'API SDK AppsFlyer :

  <Tabs>
  <Tab title="Android natif">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="iOS natif">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#getappsflyerid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="UnityReact natif">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>
  </Tabs>

* Depuis la plate-forme AppsFlyer à l'aide de l'un des éléments suivants : <Anchor target="_blank" href="/marketers/fr/docs/pull-api-raw-data?query=pull">API Pull,</Anchor> <Anchor target="_blank" href="/marketers/fr/docs/push-api-streaming-raw-data">API Push,</Anchor> Exportation <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">installation des données brutes.</Anchor>

> 👍 **Astuce**
>
> Lorsque vous testez les messages S2S, si vous utilisez des données brutes recherchez l'enregistrement dont la source média est signalée par « s2s\_test ». Il s’agit de votre appareil de test et son ID d'appareil AppsFlyer est l’identifiant dont vous avez besoin.

</Accordion>

<div id="time-stamping-s2s-events" />

<Accordion title="Horodatage des Événements S2S">

<Image align="center" alt="diagramme de logique d'horodatage" src="https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png" />

Lorsque les événements S2S arrivent en groupe sur AppsFlyer, ils sont horodatés en fonction des valeurs de la propriété `eventTime` et de leur heure d'arrivée. La propriété `eventTime` indique l'heure à laquelle l'événement s'est produit dans l'application.

À leur arrivée, les événements sont horodatés comme suit :

* Si le paramètre `eventTime` n'est pas inclus dans l'enregistrement de l'événement, l'heure de l'événement correspond à l'heure d'arrivée du message HTTP.
* Les événements qui arrivent avant 02:00 UTC sont datés avec la valeur `eventTime`. En d'autres termes, pour que les événements soient marqués de `eventTime`, ils doivent être signalés soit le jour de l'événement, soit le jour suivant jusqu'à 02:00 UTC.
* Les événements qui ont eu lieu la veille ou encore plus tôt, mais qui arrivent après 02:00 UTC, sont datés à l'heure d'arrivée (l'heure de l'appel d'API).
* Les événements qui arrivent avec une heure `eventTime` future (eventTime est postérieure à l'heure d'arrivée) :
  * Si l'heure de l'événement `eventTime` et l'heure d'arrivée ont lieu le même jour, l'événement est daté à l'heure de `eventTime`.
  * Si la date `eventTime` transmise a lieu le jour suivant, l'événement est daté à l'heure d'arrivée.
* Les événements dont la valeur `eventTime` n'est pas valide sont marqués par l'heure d'arrivée du message HTTP.

**Exemple**

* Un événement est envoyé avec l'`eventTime` = Lundi 21h00.

| Arrivée sur AppsFlyer | Horodatage AppsFlyer | Remarque |
| --- | --- | --- |
| Mardi 01h00 | Lundi 21h00 | Arrivée avant l'heure de fermeture. L'heure est fixée d'après la valeur `eventTime`. |
| Mercredi 09h00 | Mercredi 09h00 | Arrivée après l'heure de fermeture. L'heure est définie sur l'heure d'arrivée. |

</Accordion>

<div id="sending-negative-revenue" />

<Accordion title="Envoi de revenus négatifs">

Les événements qui ont une valeur négative de revenus peuvent être envoyés. Par exemple, dans le cas où un achat a été annulé. Le paramètre `af_revenue` peut avoir des valeurs négatives pour permettre l'enregistrement.

Lorsque vous remplissez `af_quantity`, vous pouvez avoir besoin de renseigner une valeur négative en fonction du fonctionnement de votre système. AppsFlyer n'utilise pas `af_quantity`.

</Accordion>

<div id="S2S_in-app_events_are_wrongly_attributed_as_organic" />

<div id="troubleshooting" />

## Dépannage

<div id="events-arent-displaying-in-the-dashboard" />

<Accordion title="Les événements ne s'affichent pas dans le tableau de bord">

* Point de terminaison : vérifiez que le point de terminaison est utilisé proprement.
* Vérifiez que la charge utile contient bien les paramètres obligatoires. Plus d'infos [ici](/docs/server-to-server-events-api-for-mobile-s2s-mobile#mapping-appsflyer-id-with-customer-user-id-cuid).
* Vérifiez que l'ID AppsFlyer que vous utilisez pour amorcer l'événement est un véritable appsflyer\_id, et qu'il est bien installé sur l'app concernée. Plus d'infos [ici](/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id).
* Les événements S2S ne prennent pas en charge l'envoi d'événements multiples sur une seule requête S2S. Chaque événement doit obligatoirement être envoyé séparément.
  * Les événements peuvent être envoyés en désynchronisé pour réduire le temps de réponse.
* Dans le tableau de bord général, la plage de dates se rapporte au jour d'installation de l'app (LTV), et non au jour de l'événement.
  * Veillez à sélectionner la bonne période.
  * Assurez-vous que la plage de dates du tableau de bord correspond bien à la date d'installation de l'appareil (appsflyer\_id), et non à la date de l'événement.
* Rapports de données brutes d'événements : la plage de dates se rapporte au jour de l'événement et non au jour d'installation.

</Accordion>

<div id="events-dont-contain-revenue" />

<Accordion title="Les événements ne contiennent pas de revenu">

Si vous envoyez des événements S2S dont les revenus ne sont pas enregistrés : veillez à ce que le JSON que vous envoyez soit converti en chaîne. La section la plus importante est celle du paramètre de valeur d'événement dans le JSON. Elle doit être convertie en chaîne comme stipulé dans l'exemple suivant.

```json
"{\"af_revenue\":\"6\" ,\"af_content_type\":\"wallets\"}"
```

Dans le cas contraire, la valeur de l'événement ne sera pas traitée correctement et ne pourra pas être enregistrée.

Les valeurs de revenus ne doivent en aucun cas être formatées. Elles peuvent contenir une virgule décimale. N'y ajoutez aucun caractère, code de devise, séparateur ou `,` (virgule). Les revenus peuvent être précédés d'un `-` (tiret du milieu)

* Exemples de valeurs valides : `123`, `-123.45`, `123.456`
* Exemples de valeurs invalides : `1,234.56`, `1,234`

</Accordion>

<div id="not-all-fields-are-populated-in-s2s-events" />

<Accordion title="Dans les événements S2S, tous les champs ne sont pas remplis">

Les champs de données brutes sont renseignés à l'aide de la valeur transmise dans l'appel S2S, tandis que d'autres champs sont remplis à l'aide de l'événement d'installation.  On observe la même chose, à quelques exceptions près, pour les événements in-app signalés à l'aide du SDK AppsFlyer. Il existe quelques différences entre les deux, notamment, les champs suivants ne sont pas renseignés pour les événements S2S :

* wifi
* operator
* langue
* Modèle d'appareil
* Catégorie d'appareil
* Version de l'app : vous pouvez utiliser `app_version_name`
* Nom de l'app
* Agent utilisateur

</Accordion>

<div data-zendesk-anchors="servertoserver-events-api-for-mobile=api-pour-mobile-d%C3%A9v%C3%A9nements-de-serveur-%C3%A0-serveur h_01H9Q8KBYGXAA8H4AKKXP8T8DY=api-pour-mobile-d%C3%A9v%C3%A9nements-de-serveur-%C3%A0-serveur populating-parameters=param%C3%A8tres-de-remplissage h_01H9Q8KBYGHY1SDSMSFZRT2JXZ=param%C3%A8tres-de-remplissage h_01H9Q8KBYG6W4TERWHARZZZASZ=difference-between-organic-and-nonorganic h_01H9Q8KBYG0JCCGTEJW3GXZMF1=exemple h_01H9Q8KBYG6EBKPS5Y2KC1QT7G=mapping-appsflyer-id-with-customer-user-id-cuid h_01H9Q8KBYGR26VMQR9Y0CK85F6=fetching-the-appsflyer-id h_01H9Q8KBYGNC8PJE2GS8MHG0KQ=astuce h_01H9Q8KBYG8ASB1WB9X4XM3CYZ=time-stamping-s2s-events h_01H9Q8KBYG63SZWNM4GWSJG605=sending-negative-revenue troubleshooting=d%C3%A9pannage h_01H9Q8KBYGYR9Y7DPCNWSB4QY0=d%C3%A9pannage h_01H9Q8KBYGYHCWAPPNMG9WB8QN=events-arent-displaying-in-the-dashboard h_01H9Q8KBYGDC68637RH4DE2FZX=events-dont-contain-revenue h_01H9Q8KBYGDQKZF90EJAXRTMF3=not-all-fields-are-populated-in-s2s-events" />

---
title: Détermination de la position de l’utilisateur à l’aide de l’adresse IP
metadata:
  keywords:
    - IPs
    - Advertisers
    - Agencies
    - Ad Networks
    - ip
    - digital element
    - zip
    - dim
    - zip code
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2019-01-29T12:52:11Z'
  edited_at: '2024-08-26T13:32:40Z'
  id: 360000847378
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/360000847378
---
> **En bref :** La localisation de l’utilisateur est déterminée à l’aide de l’adresse IP de l’appareil qui est mappée à son emplacement général (ville, état, pays, etc.). La position de l’utilisateur a un impact sur la sélection des créations, le coût de la campagne, l’engagement et la qualité de l’utilisateur.

![5888ResolveIpAddress_us-en.png](https://files.readme.io/166e48fb0bb90b627bc51e29b53a556b71939749ab3e5eadff7d6edf0f0dfd25-360011758517.png)

## Détermination de l’emplacement de l’utilisateur

Les actions de l’utilisateur sur l’appareil sont signalées à AppsFlyer. Les actions (événements) contiennent divers champs de données, y compris l’adresse IP de l’appareil.

Dans certains cas, la véritable adresse IP de l’appareil est masquée par un VPN, un mécanisme tel que iOS 15 Private Relay ou des serveurs proxy postback SKAN. Par conséquent, la conversion de l’adresse IP en géolocalisation décrite dans cet article peut être incorrecte ou trompeuse. AppsFlyer n’a aucun contrôle sur cela.

L’adresse IP est convertie par AppsFlyer en informations de géolocalisation à l’aide des données fournies par <Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor>, le leader mondial de la localisation IP.

* Les informations de géolocalisation peuvent inclure :
  * Territoire (pays) : codes ISO 3166 (alpha-2), ou UE (Europe) ou AS (Asie) si aucune information spécifique au territoire n’est disponible.
  * Ville : cela peut être corrélé à un quartier ou à un quartier de la ville sans être directement lié aux limites réelles de la ville.
  * DMA (zone de marché, régions ou zones géographiques désignées pour l’écoute de la télévision, mesurées par le <Anchor target="_blank" href="https://www.nielsen.com/us/en/solutions/nielsen-global-connect/">Nielsen</Anchor> compagnie. <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012539677">Codes de métro dans le fichier CSV.</Anchor>
  * Région : La région géographique ou le continent.
  * État ou province : Voir le tableau des <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012615238">noms d’état localisés dans le fichier CSV</Anchor>. Nous utilisons le champ de la région dans cette table. Il se compose d’un maximum de 3 lettres ou chiffres.
  * Code postal.
* Les tables d’adresses IP et de géolocalisation sont mises à jour à intervalles réguliers, généralement toutes les semaines.

**Exemple : Conversion de l’adresse IP en géolocalisation**![IPTables_us-en.png](https://files.readme.io/0d7d4d4190face77e18476bdb9e47fdd26ed62ab91cd641f76f728d9a7c8d005-360011787798.png)

> 📘 **Note concernant le Royaume-Uni (UK)**
>
> <Image alt="blobid0.png" src="https://files.readme.io/33ed45ea49e3308e17a237400ea6c6e9d33c495a9c83197041fdae282f9c65a4-360006637538.png" width="62px" />
>
> * Dans la plateforme, le Royaume-Uni est désigné par le code UK.
> * Le code ISO 3166 pour le Royaume-Uni est GB. Le Royaume-Uni est réservé, mais n’a pas été attribué par l’ISO au Royaume-Uni.

### Écarts de localisation

Dans certains cas, il peut y avoir des différences dans la localisation dérivée des utilisateurs entre AppsFlyer et d’autres plateformes, même si d’autres plateformes utilisent Digital Element pour résoudre les adresses IP. Les raisons possibles de la divergence d’emplacement sont les suivantes :

* **Mises à jour de la base de données :** pour permettre une attribution rapide, AppsFlyer résout les adresses IP en données de localisation en interne. AppsFlyer récupère la carte globale à partir de Digital Element périodiquement et non en temps réel. Si AppsFlyer et l’autre plate-forme récupèrent les données Digital Element à des moments différents, cela peut expliquer les différences.
* **Changements de FAI :** Les bases de données Digital Element évoluent rapidement à mesure que les fournisseurs de services (FAI) modifient leurs mappages IP.
* **Différents plans/méthodes :** Digital Element propose différents forfaits en fonction du niveau de granularité requis. D’autres plates-formes utilisant des packages Digital Element différents ou des méthodes différentes pour définir l’ID d’un appareil peuvent fournir des résultats différents.
* **Proxy, ou VPN :** Si un utilisateur met en œuvre un VPN ou un proxy, nous ne connaîtrons pas sa véritable adresse IP. La résolution géographique sera basée sur l’adresse VPN/proxy.
* **Pour en savoir plus :** <Anchor target="_blank" href="https://www.digitalelement.com/wp-content/uploads/2018/07/IP-Geolocation-Myths-Facts.pdf">Les mythes de la géolocalisation IP par Digital Element.</Anchor>

<div data-zendesk-anchors="determining-user-location=d%C3%A9termination-de-lemplacement-de-lutilisateur h_01HDP1SA5YV96YMPPFGN9H6RGE=d%C3%A9termination-de-lemplacement-de-lutilisateur h_01HDP1SA5YR7JWDHX2BNXXTKT9=note-concernant-le-royaume-uni-uk location-discrepancies=%C3%A9carts-de-localisation h_01HDP1SA5YNA9N4P9AD4RHWS0J=%C3%A9carts-de-localisation" />

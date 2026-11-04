---
title: Exporter les URL OneLink
metadata:
  keywords:
    - export
    - Marketers
    - download
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2022-01-09T11:58:46Z'
  edited_at: '2024-08-26T13:39:21Z'
  id: 4416027813905
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/4416027813905
---
> **En bref :** téléchargez toutes les URL OneLink créées dans l'interface utilisateur AppsFlyer.

<div id="export-onelink-urls" />

## Exporter les URL OneLink

Téléchargez un fichier CSV contenant toutes les URL OneLink créées par template OneLink, et via la configuration OneLink de l’IU AppsFlyer. (Les URL OneLink créées via SDK, API OneLink ou téléchargement de groupe ne sont pas exportées).

Le fichier CSV contient des informations sur chaque lien, comme indiqué ci-dessous :

* Nom du lien
* Source média
* Nom de la campagne
* URL courte
* URL longue
* Date de la dernière modification/création (MM:DD:YY HH:MM)
* Modifié par (e-mail)

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR02eohAyUA2fsr9iGEb0UiZI8v45wH58KGo-45wajF4KNGuk_2S_cY1WW3UV8LwPRg-wm9bkMjvWyZ/pub?output=csv">Exemple de CSV</Anchor>

**Remarque** : Si un lien est créé dans l’IU AppsFlyer, mais que les paramètres sont ensuite mis à jour en dehors de l'IU (via API OneLink, une feuille de calcul, etc.), les paramètres mis à jour ne seront pas contenus dans le fichier CSV téléchargé.

**Pour télécharger le fichier CSV** :

1. Dans AppsFlyer, allez dans Expériences et Deep Linking > **Liens personnalisés OneLink.**
2. Sélectionnez le template OneLink pour lequel vous souhaitez obtenir une liste de liens.
3. Cliquez sur **Exporter**.  
   Le fichier CSV est téléchargé.

<div id="traits-and-limitations" />

### Caractéristiques et limitations

| **Caractéristique** | **Remarques** |
| --- | --- |
| Agences | Ne peuvent obtenir que les liens qu'elles ont créés sur la base du template OneLink. |
| Annonceurs | Ne peuvent obtenir que les liens qu'ils ont créés sur la base du template OneLink. |

<div data-zendesk-anchors="export-onelink-urls=exporter-les-url-onelink traits-and-limitations=caract%C3%A9ristiques-et-limitations" />

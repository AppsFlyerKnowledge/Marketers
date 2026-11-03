---
title: URL longs de OneLink
metadata:
  keywords:
    - Marketers
    - parameters
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2021-01-26T09:39:19Z'
  edited_at: '2024-08-15T14:37:53Z'
  id: 360017132597
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/360017132597
---
> **En bref :** Comprendre la différence entre les URL courtes et longues de OneLink, et comment créer des URL longues en dehors d'AppsFlyer.

## URL longs de OneLink

Liens personnalisés OneLink :

* Travailler sur tous les canaux de marketing média pour rediriger les utilisateurs vers : 
  * l'URL/l’app store correct.
  * Ouvrez l'application, puis créez un deep link vers une activité spécifique de l'app.
* Peut prendre en charge la personnalisation de la marque. Cela signifie que l'URL contient le domaine de votre <Anchor target="_blank" href="/marketers/fr/docs/brand-onelink-with-your-domain">domaine de la marque</Anchor> au lieu du sous-domaine OneLink.
* Il peut s'agir d'URL courtes ou longues :
  * Les URL courtes sont créées dans AppsFlyer (soit <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">dans l'interface utilisateur</Anchor>, soit via l'<Anchor target="_blank" href="/marketers/fr/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API</Anchor> ou le <Anchor target="_blank" href="/marketers/fr/docs/user-invite-attribution">SDK</Anchor>).
  * URL longues :
    * Peuvent être créées dans l'interface utilisateur d'AppsFlyer ou en dehors d'AppsFlyer.
    * Contiennent tous les paramètres que vous souhaitez.
    * Peuvent être utilisées pour générer un grand nombre de liens personnalisés OneLink en appliquant vos propres formules simples dans une feuille de calcul. **Remarque** : Les liens créés dans une feuille de calcul ne sont pas visibles (et ne peuvent pas être modifiés) dans l'interface utilisateur d'AppsFlyer.
    * N'expirent pas, ce qui signifie qu'il n'y a pas de limitation de durée de vie (TTL).

**Attention**

* Les URL longues sont transparentes, ce qui signifie que tous les paramètres du lien sont visibles par l’audience et peuvent potentiellement être manipulés.
* Les URL longues risquent de ne pas être adaptés aux navigateurs, aux SMS ou lorsque le nombre de caractères des URL est limité.

### Procédures

**Pour créer une URL longue OneLink en dehors de l'interface utilisateur d'AppsFlyer :**

1. Créez un <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">template OneLink</Anchor>.
2. Enregistrez l'URL de base OneLink, c'est-à-dire le domaine du modèle OneLink + l'ID du modèle.  
   Exemple : 
   * Domaine du modèle OneLink : `yourbrand.onelink.me`
   * ID du template :`1a6f`
   * URL de base OneLink : `yourbrand.onelink.me/1a6f`
   * Exemple de domaine de marque : `yourbrand.com/1a6f`
3. Ajoutez une adresse `?` à l'URL, suivie de tous les paramètres que vous souhaitez ajouter.
   * Voir la <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">liste des paramètres d'AppsFlyer</Anchor>.
   * Pour ajouter plus d'un paramètre, utilisez `&`.  
     Exemple : `yourbrand.onelink.me/1a6f?pid=email&c=freestuff`

**Pour obtenir les URL longues des liens personnalisés OneLink que vous créez dans l'interface utilisateur d'AppsFlyer :**

1. Dans AppsFlyer, allez dans les **liens personnalisés OneLink.**  
   La liste des OneLinks s'affiche.  

   [![](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)
2. Allez sur le lien pour lequel vous souhaitez obtenir l'URL longue, et dans la colonne **Actions** cliquez sur **Obtenir l'URL**.  
   L'URL longue s'affiche.

<div data-zendesk-anchors="onelink-long-urls=url-longs-de-onelink procedures=proc%C3%A9dures" />

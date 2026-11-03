---
title: Configuration du Smart Script pour convertir les visiteurs du site web
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2021-12-13T09:57:23Z'
  edited_at: '2024-11-13T10:46:47Z'
  id: 4413588932241
  locale: fr
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/fr/articles/4413588932241
---
> **En bref :** Utilisez Smart Script OneLink pour convertir et attribuer les visiteurs de votre site web mobile (qu’elle que soit la source) en utilisateurs d'app mobile.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

## Configuration

Il existe deux versions du Smart Script OneLink :

**Smart Script OneLink V2 (recommandé)**: Si vous configurez Smart Script OneLink pour la première fois, vous devez utiliser cette version en priorité. Smart Script OneLink peut être généré dans l'interface utilisateur d'AppsFlyer sans l'aide d'un développeur. Nous avons fait en sorte de faciliter la configuration. Votre développeur en sera ravi ! Smart Script OneLink peut également être configuré à l'aide du Google Tag Manager. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2">A l'attention des développeurs : accéder aux instructions</Anchor>

<Anchor target="_blank" href="/marketers/fr/docs/legacy-onelink-smart-script-v1-setup">**Smart Script OneLink V1 (version héritée)**</Anchor>: Si vous avez déjà configuré Smart Script OneLink vous devez suivre les instructions propres à cette version pour configurer et modifier le script. **Remarque** : Vous n’êtes évidemment pas obligés de passer à la V2. En revanche, vous profiterez pleinement des <Anchor target="_blank" href="https://www.appsflyer.com/glossary/view-through-attribution/">attributions post-vue</Anchor>  via Smart Script OneLink.

### Configurer Smart Script OneLink

Pour configurer le Smart Script, vous pouvez :

* Intégrer le script à votre site web ;
* Utiliser Google Tag Manager.

#### Mise en oeuvre

| **Personne en charge**<ul><li>**L’annonceur** :<ul><li>Décide de ce que l'URL sortante doit contenir en fonction des [arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) du script qui traitent l'URL entrante. Cette méthode détermine les données d’attribution et de deep linking qui sont ajoutées à l’URL sortant, soit en manipulant l’URL entrant, soit en forçant certaines valeurs.</li><li>Génère le Smart Script dans l’interface utilisateur AppsFlyer.</li><li>S'assure que toutes les campagnes menant au site web mobile ont des URL entrantes avec des paramètres pour lesquels le script fonctionne.</li><li><Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Teste le Smart Script</Anchor>.</li></ul></li><li>**Le développeur web** :<ul><li>Vérifie que le script s'exécute correctement sur le site ou les pages mobiles où il est installé.</li><li>Utilise la valeur du résultat, par exemple pour la placer en tant que lien sur un CTA de votre site web.</li><li>Peut être nécessaire pour créer des QR codes à l'aide du script.</li><li>Peut être nécessaire pour ajouter manuellement des arguments avancés au script.</li></ul></li></ul> |
| --- |
| **Conditions préalables**<ul><li>Avoir un compte AppsFlyer avec au moins une app.</li><li>Avoir un <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">template OneLink</Anchor> qui sert de valeur au [paramètre OneLinkURL](/docs/set-up-smart-script-to-convert-web-visitors#arguments).</li></ul> |

<div id="how-to-create-a-onelink-smart-script" />

<Accordion title="Comment créer un Smart Script OneLink ?">

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Engage** > **Web-to-app** > **Smart Script.**
2. ***Pour les nouveaux utilisateurs***
   1. *Cliquez sur le bouton **Démarrer***.
   2. *Validez les étapes 4 et suivantes.*
3. Cliquez sur le bouton **+ Nouveau Smart Script** en haut de la page.
4. Donnez un nom à votre Smart Script en suivant les instructions.
5. Sélectionnez un template OneLink sur lequel baser le script. Le template contient les paramètres basiques de redirection.
6. Mappez les paramètres que l'URL sortant doit contenir. Ces paramètres sont basés sur les paramètres de l’URL entrant. **Remarque** : Le paramètre (pid) de la source média est obligatoire.
   1. Sélectionnez le paramètre/dimension sortant à mapper.  
      Il s'agit souvent d'un nom de paramètre AppsFlyer qui ne peut pas être modifié, mais dans certains cas, vous devez saisir votre nom de paramètre.
   2. Définissez et configurez la valeur du paramètre sortant en fonction des éléments suivants :
      * Paramètres de l'URL entrante : Listez un ou plusieurs paramètres d'URL entrants possibles que vous souhaitez remplacer par le paramètre d'URL sortant. Les valeurs des paramètres de l'URL entrant seront les valeurs des paramètres de l'URL sortant.
        * Exemple : any\_param\_name, utm\_param\_name. Si utm\_param\_name se trouve dans l'URL entrante, sa valeur sera utilisée comme valeur du paramètre de l'URL sortant sélectionné.
        * Smart Script recherche la liste des paramètres en allant de gauche à droite, puis mappe la première correspondance trouvée avec l'URL du paramètre sortant.
        * Les développeurs appellent cette liste de paramètres «les clés».
      * Valeur par défaut : Entrez la valeur par défaut souhaitée pour la valeur du paramètre sortant lorsqu’un paramètre d’URL entrant est introuvable, ou si vous ne renseignez aucun paramètre d’URL entrant.
        * Exemple : Pour le paramètre sortant, si le paramètre d’URL entrant répertorie any\_paramname ou utm\_paramname dans le cas où aucun paramètre de la liste n’est trouvé, la valeur par défaut sera utilisée comme valeur du paramètre sortant.
      * Remplacer les valeurs : Configurez une ou plusieursvaleurs de l'URL entrant avec les valeurs de l'URL sortant par lesquelles vous souhaitez qu'elles soient remplacées.
        * Exemple : Pour le paramètre Campaign (campagne), si la valeur de l'URL entrant est campaignn\_name, la valeur de l'URL sortant peut être changée en new\_campaign\_name.
   3. [Facultatif] Cliquez sur **+ Nouveau paramètre** pour mapper des paramètres supplémentaires. Consultez tous les [arguments supplémentaires](/docs/set-up-smart-script-to-convert-web-visitors#arguments) (configurations des paramètres) que vous pouvez utiliser.
7. Sélectionnez comment implémenter le Smart Script sur votre site web :
   * **Intégrer le script à votre site web ;**
   * **Utiliser Google Tag Manager.**
8. Cliquez sur **Tester** pour tester le script sur <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">la page de test Smart Script</Anchor>. Assurez-vous que le bon URL sortant soit généré.
9. Clic
   1. **Enregistrer** pour enregistrer vos modifications
   2. **Enregistrer et Générer** pour enregistrer et générer le script
      1. Cliquez sur **Télécharger le script**
10. Si vous avez choisi d'intégrer le script dans votre site web : Envoyez le script à votre développeur web pour qu'il l’intègre. Vous pouvez lui communiquer les instructions afin qu’il puisse gérer l’URL sortant généré. Par exemple, placez l’URL sortant sur un bouton de CTA sur votre site mobile ou affichez un QR code sur la version desktop de votre site. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#embed-the-script-in-your-website">Instructions pour les développeurs</Anchor>
11. Si vous avez choisi d’utiliser Google Tag Manager :
    1. Dans Google Tag Manager, créez une nouvelle balise, nommez-la, cliquez sur **Configuration des balises**, puis sélectionnez **HTML personnalisé.**
    2. Dans la zone HTML, collez le code Smart Script généré.
    3. Cliquez sur **Déclenchement**, créez un nouveau déclencheur, nommez-le et choisissez une **Configuration de déclencheur** (ex : toutes les pages vues). <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">Consultez la documentation GTM pour en savoir plus</Anchor>
    4. Cliquez sur **Enregistrer**.
    5. Communiquez les instructions au développeur web au sujet de la gestion de l’URL sortant généré. Par exemple, placez l’URL sortant sur un bouton de CTA sur votre site mobile ou affichez un QR code sur la version desktop de votre site. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#use-google-tag-manager">Instructions pour les développeurs</Anchor>
12. Les scripts qui ont été enregistrés se trouvent dans le [menu déroulant](/docs/set-up-smart-script-to-convert-web-visitors#how-to-edit-or-delete-a-script).

> 🚧 **Important !**
>
> A chaque fois que le script est mis à jour, il doit être ré-implémenté.

</Accordion>

<div id="how-to-edit-or-delete-a-script" />

<Accordion title="Comment modifier ou supprimer un script ?">

![Script_steps.jpg](https://files.readme.io/824c042dc23acaa14b360ce8cd792cfc2e85ee3c9c95e3fa694f96badfeb1fc2-42045468432657.jpg)

1. Cliquez sur la flèche déroulante <Image alt="Down_arrow.jpg" src="https://files.readme.io/a82023665721be681f985548857c4c329f626435780bb1bff7a3821b32b69078-42045468433041.jpg" width="28px" /> à côté du titre du Smart Script.  
   Vous verrez s'afficher ici tous vos scripts sauvegardés.
2. Cliquez sur l'icône «Stylo» à côté du script que vous souhaitez modifier.
   1. Suivez les différentes étapes dans [Comment créer un Smart Script OneLink](/docs/set-up-smart-script-to-convert-web-visitors#configurer-smart-script-onelink)
3. Cliquez sur l'icône Corbeille pour supprimer le Smart Script.

> 🚧 **Important !**
>
> A chaque fois que le script est mis à jour, il doit être ré-implémenté.

</Accordion>

<div id="how-to-duplicate-a-script" />

<Accordion title="Comment dupliquer un script ?">

1. Accédez au Smart Script que vous souhaitez dupliquer
2. Cliquez sur le bouton dupliquer <Image alt="SmartScript_duplicate.jpg" src="https://files.readme.io/ec05ea217331b588dc7033984287d46b61a37e41510546b67a0046ea281e0979-42045454920721.jpg" width="21px" /> sur la bannière supérieure
3. Suivez les différentes étapes dans [Comment créer un Smart Script OneLink](/docs/set-up-smart-script-to-convert-web-visitors#configurer-smart-script-onelink)

</Accordion>

<div id="argument-structure" />

<Accordion title="Structure des arguments">

Le Smart Script OneLink utilise des arguments pour générer un URL sortant en fonction des paramètres de l’URL entrant et des arguments définis dans le script. L’argument afParameters a une structure composée de plusieurs autres arguments (paramètres) utilisés pour l’attribution et le deep linking, chacun contenant une structure (appelée par les développeurs en tant qu'objet de configuration) dotée de clés, de valeurs de remplacement et d’une valeur par défaut, comme décrit dans le tableau qui suit.

| Argument | Description | Exemple |
| --- | --- | --- |
| Paramètres d'URL entrants (appelés «clés» par les développeurs) | <ul><li>Liste des chaînes</li><li>Liste des paramètres possibles dans l’URL entrant recherché par le script, dont la valeur est placée comme valeur dans l’URL sortant.</li><li>Le script recherche de gauche à droite et s'arrête à la première correspondance.</li></ul> | <ul><li>Exemple : ['in\_channel', 'utm\_channel']</li><li>Pour le paramètre de canal dans le script, le script recherche le lien entrant in\_channel et utilise la valeur comme valeur de canal.</li></ul> |
| Valeur par défaut | <ul><li>String</li><li>Indiquez la valeur de secours (fallback) que vous souhaitez.</li><li>Si aucun paramètre n'est trouvé dans votre liste de clés, la valeur defaultValue est utilisée dans l'URL sortant.</li><li>Vous pouvez forcer une valeur par défaut en transmettant une liste de clés vides.</li></ul> | Exemple : ['web\_video']<br /><br />Pour le paramètre de canal dans le script, si vous ne trouvez pas le paramètre in\_channel, web\_video est utilisé comme valeur de canal. |
| Remplacer les valeurs | <ul><li>Dictionnaire \{string : string\}</li><li>Répertoriez les valeurs que vous souhaitez modifier dans le lien sortant dans l’URL entrant. Indiquez aussi les valeurs que vous souhaitez intégrer à la place.</li><li>Le script remplace les valeurs de paramètre de l'URL entrant par les valeurs que vous définissez.</li></ul> | Exemple : \{'video' : 'video\_new'\}<br /><br />Pour le paramètre de canal dans le script, chaque fois que la valeur entrante est « video », le script la remplace par « video\_new » dans le lien sortant. |

</Accordion>

<div id="arguments" />

<Accordion title="Arguments">

Le Smart Script OneLink utilise des arguments pour générer un URL sortant en fonction des paramètres de l’URL entrant et des arguments définis dans le script.

#### Arguments (paramètres et valeurs) pour implémenter le Smart Script

<table><thead><tr><th colspan="2">Argument</th><th>Remarques</th><th>Enregistrez vos réponses (pour votre développeur, ou pour vous)</th></tr></thead><tbody><tr><td colspan="2">oneLinkURL (obligatoire)</td><td><ul><li>Indiquez le domaine du template OneLink + l’ID du template. <strong>Remarque :</strong> Pas un URL de lien personnalisé OneLink !</li><li>Exemple : <strong>yourbrand.onelink.me/A1b2</strong> </li><li>Exemple de domaine de marque : <strong>click.yourbrand.com/A1b2</strong> </li></ul></td><td> </td></tr><tr><td rowspan="9"><p>afParameters</p><p>(obligatoire)</p><span><br/></span> </td><td><p>mediaSource</p><p>(obligatoire)</p></td><td><ul><li>Objet de configuration pour la source média.</li><li>Exemple :<br/><ul><li>Clés : ['incoming_mediasource'' 'utm_source']</li><li>Valeur par défaut : ['any_source']</li><li>Remplacer les valeurs : `{twitter : 'twitter_int', orig_src : 'new_src'}</li></ul></li></ul></td><td><p>Clés :</p><p>Valeur par défaut :</p><p>Remplacer les valeurs :</p></td></tr><tr><td><p>campaign</p></td><td><ul><li>Objet de configuration pour la campagne.</li><li>Exemple :<br/><ul><li>Clés : ['incoming_campaign', 'utm_campaign']</li><li>Valeur par défaut : ['any_campaign_name']</li><li>Remplacer les valeurs : {campaign_name : 'new_campaign_name'}</li></ul></li></ul></td><td><p>Clés :</p><p>Valeur par défaut :</p><p>Remplacer les valeurs :</p></td></tr><tr><td><p>channel</p></td><td><ul><li>Objet de configuration pour le canal.</li><li>Exemple :<br/><ul><li>Clés : ['incoming_channel', 'utm_channel']</li><li>Valeur par défaut : ['any_video']</li><li>Remplacer les valeurs : {video : 'new_video'}</li></ul></li></ul></td><td><p>Clés :</p><p>Valeur par défaut :</p><p>Remplacer les valeurs :</p></td></tr><tr><td><p>ad</p></td><td><ul><li>Objet de configuration pour la publicité.</li><li>Exemple :<br/><ul><li>Clés : ['incoming_ad', 'utm_ad']</li><li>Valeur par défaut : ['any_ad_name']</li><li>Remplacer les valeurs : {ad_name : 'new_ad_name'}</li></ul></li></ul></td><td><p>Clés :</p><p>Valeur par défaut :</p><p>Remplacer les valeurs :</p></td></tr><tr><td>adSet</td><td><ul><li>Objet de configuration pour l'adset.</li><li>Exemple :<br/><ul><li>Clés : ['incoming_adset', 'utm_adset']</li><li>Valeur par défaut : ['any_ad_name']</li><li>Remplacer les valeurs : {adset_name : 'new_adset_name'}</li></ul></li></ul></td><td><p>Clés :</p><p>Valeur par défaut :</p><p>Remplacer les valeurs :</p></td></tr><tr><td>deepLinkValue</td><td><ul><li>Objet de configuration pour <strong>deep_link_value</strong>.</li><li>Exemple :<br/><ul><li>Clés : ['product_id', 'page_name']</li><li>Valeur par défaut : 'new_offers_page'</li><li>Remplacer les valeurs : {twenty_percent_off : 'thirty_percent_off'}</li></ul></li></ul></td><td><p>Clés :</p><p>Valeur par défaut :</p><p>Remplacer les valeurs :</p></td></tr><tr><td>afSub1-5</td><td><p>Objet de configuration pour <strong>af_sub[1-5]</strong>.</p></td><td><p>Clés :</p><p>Valeur par défaut :</p><p>Remplacer les valeurs :</p></td></tr><tr><td>googleClickIdKey</td><td><p>Indiquez comment appeler le paramètre qui transporte la <a href="https://support.google.com/google-ads/answer/9744275?hl=en" target="_blank">GCLID</a>.<br/><strong>Remarque</strong>  ! <span>Pour s'afficher dans les rapports de données brutes AppsFlyer, le paramètre doit être l'un de <strong>af_sub[1-5]</strong>.</span></p></td><td> </td></tr><tr><td> <span>Autres paramètres de requête (personnalisés)</span><span><br/></span> </td><td><ul><li>Répertoriez tous les autres paramètres que vous souhaitez inclure dans l’URL OneLink sortant pour l’attribution ou le deep linking, ainsi que leurs objets de configuration.</li><li>Le nom du paramètre personnalisé est inscrit par le développeur en tant que paramKey dans l’objet de configuration.<span></span> </li><li>Exemple : <ul><li>paramKey : 'deep_link_sub1'</li><li>Clés : ['page_id']</li><li>Valeur par défaut : 'page1'</li><li>Remplacer les valeurs : {page12 : 'new_page12'}`</li></ul></li></ul></td><td><p>Clé Param :</p><p>Clés :</p><p>Valeur par défaut :</p><p>Remplacer les valeurs :</p></td></tr></tbody></table>

</Accordion>

<div id="advanced-arguments" />

<Accordion title="Arguments avancés">

Le tableau suivant décrit les arguments que les tech-savvy marketeurs ou les développeurs peuvent intégrer dans le Smart Script.

#### Arguments avancés (paramètres et valeurs) pour implémenter le Smart Script

<table><thead><tr><th colspan="2">Argument</th><th>Remarques</th><th>Enregistrez vos réponses (pour votre développeur, ou pour vous)</th></tr></thead><tbody><tr><td colspan="2"> <span> </span><br/><span>referrerSkipList</span> </td><td><ul><li> <span>Liste des chaînes de caractères du référent HTTP pour un clic particulier (par exemple Twitter ou Facebook) qui, si elles sont trouvées, amènent le Smart Script à renvoyer un signal</span><code>null</code><span>. Cela peut être utile pour les SRN tels que les annonces X et Meta, pour lesquelles les clics sont déjà signalés.</span> </li><li><span>L'implémentation de cet argument entraîne la génération d'un URL OneLink dans le script.</span></li></ul></td><td><p><span> </span></p></td></tr><tr><td colspan="2"><span>urlSkipList</span></td><td><ul><li><span>Liste des chaînes dans l’URL pour clic particulier (par exemple af_r) qui, si elles sont trouvées, amènent le Smart Script à renvoyer un signal «<code>null</code>». Cela peut être utile si vous utilisez un lien d’attribution AppsFlyer avec af_r pour rediriger les utilisateurs vers votre site web mobile, et que vous ne souhaitez pas que les données du clic d’origine soient perdues. </span></li><li><span>L'implémentation de cet argument entraîne la génération d'un URL OneLink dans le script.</span></li></ul></td><td><p><span> </span></p></td></tr></tbody></table>

</Accordion>

## Cas d’utilisation

Les sections suivantes fournissent des cas d’utilisation Smart Script pour certains scénari courants de campagne / source média.

<div id="utm-parameters" />

<Accordion title="Paramètres UTM">

**Pour configurer le script des paramètres UTM** :

1. Faites une liste des paramètres UTM pour l'URL entrant (par exemple : **utm\_source** et **utm\_campaign**) et faites-les correspondre aux paramètres de l'URL sortant (par exemple : **media\_source** et **campaign**).
2. Indiquez ces paramètres dans la [liste des arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) du développeur web.

**Résultat**: Les valeurs des paramètres entrants (**utm\_source** et **utm\_campaign**) sont utilisées pour renseigner les valeurs des paramètres (**media\_source** et **campaign**) dans le lien sortant.

</Accordion>

<div id="google-ads-gclid" />

<Accordion title="Le GCLID sur Google Ads">

Le processus habituel d'attribution des installations des campagnes Google Ads (qui comportent un paramètre GCLID) nécessite que les utilisateurs qui cliquent sur votre publicité soient redirigés vers l'URL de la page de l'app store.

Dans ce cas, le script récupère le paramètre GCLID de l'URL de la campagne Google Ads pour le réinsérer dans l'URL de destination, lorsque vous redirigez les clients potentiels vers une page web ou une landing page. À partir de la version 2.9.0 de Smart Script, les paramètres GCLID, WBRAID et GBRAID, lorsqu'ils sont disponibles, sont automatiquement transmis "tels quels" dans les URL sortantes générées par Smart Script.

Vous pouvez également associer les identifiants de clics à d'autres paramètres sortants (**af\_sub[1-5]**) afin qu'ils soient disponibles dans les rapports de données brutes d'AppsFlyer.

**Remarque!**

* Cela s'applique aux campagnes d'installation. Pour les campagnes de recherche non ACI, c'est-à-dire les campagnes de réengagement, Google peut être attribué comme source média, malgré la sortie Smart Script.
* Si un GCLID est trouvé, le script recherche le mot-clé de paramètre entrant. Si ce paramètre est identifié, il place la valeur du mot-clé dans l’URL sortant comme valeur de af\_keywords.

**Conditions préalables** : Dans le tableau de bord Google, <Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">activez le tag automatique</Anchor>.   
Lorsque le tag automatique est activé, l'URL contient le paramètre *GCLID*.

**Pour configurer le script afin de faire correspondre le GCLID de Google Ads à d'autres paramètres :**

1. Sélectionnez un paramètre de l’URL sortant qui contiendra le GCLID.  
   Bonne pratique : Sélectionnez **af\_sub[1-5]**, pour que les données s'affichent dans les rapports de données brutes d'AppsFlyer.
2. Indiquez ces éléments dans la [liste des arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) du développeur web. Le résultat sera que dans l'URL sortant, le GCLID sera la valeur du paramètre **af\_sub[1-5].**

**Pour informer Google Ads de ces installations :**

1. Obtenez les données GCLID du param **af\_sub[1-5]** via le CSV ou l'API Push en temps réel pour chaque installation.
2. Téléchargez les données GCLID vers Google <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">manuellement</Anchor> ou via l'<Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/start">API Google Ads</Anchor>.

> 📘 **Remarque**
>
> Cette solution GCLID n’est pas officiellement prise en compte ou recommandée par Google. Si jamais Google déprécie le paramètre GCLID, nous modifierons le script pour prendre en compte les modifications. Suivez cet article, en cliquant sur le bouton **Suivre** dans l’en-tête, pour être informé lors d'une mise à jour de l’article ou du script.

</Accordion>

<div id="facebook-click-id" />

<Accordion title="Facebook FBCLID">

Les métapublicités comportent des identifiants de clics, appelés FBCLID. À partir de la version 2.8.1 de Smart Script, lorsqu'elle sera disponible, FBCLID sera automatiquement transmis "tel quel" sur les URL sortants générés par Smart Script. Vous pouvez également associer les identifiants de Clics à d'autres paramètres sortants afin de les rendre disponibles dans les rapports de données brutes d'AppsFlyer.

**Pour configurer le script afin de faire correspondre FBCLID à d'autres paramètres :**

1. Sélectionnez un paramètre dans l'URL sortant qui contiendra le FBCLID.   
   Bonne pratique : Sélectionnez **af\_sub[1-5]**, pour que les données s'affichent dans les rapports de données brutes d'AppsFlyer.
2. Indiquez ces éléments dans la [liste des arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) du développeur web. Le résultat sera que dans l'URL sortant, le FBCLID sera la valeur du paramètre **af\_sub[1-5].**

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="SRN, médias propres et autres liens vers des sources média">

<Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#srn-intégrés-à-appsflyer">Les SRN</Anchor> comme les ads Snapchat ou X (Twitter) fonctionnent différemment de Google Ads ou d'une cross-platform comme Meta Ads. Les campagnes de ces SRN dirigent vos utilisateurs vers la page web/landing page, et vous êtes facturé en fonction des clics générés, sans lien avec les utilisateurs mobiles associés.

Pour ces SRN, la configuration du script est la même que pour les liens provenant de médias propriétaires ou d’autres sources média que vous utilisez.

**Pour configurer le script** :

1. Dressez une liste des noms des sources média et des paramètres de campagne qui se trouvent dans les liens entrants.
2. Indiquez ces paramètres dans la  [liste des arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments)  du développeur web.  
   Le type de SRN/source média doit être la valeur de la source média dans l'URL entrante, et le script la trouve et l'utilise comme valeur **media\_source** dans l'URL OneLink sortant derrière le bouton de téléchargement sur la page web/landing page. Si vous souhaitez modifier le paramètre **media\_source** sortant, indiquez la valeur de la source média entrante et la valeur media\_source de remplacement dans la [liste des arguments](/docs/set-up-smart-script-to-convert-web-visitors#arguments) que vous donnez au développeur web.

**Résultat :** Pour ces SRN / sources média, les valeurs de la source média et les paramètres de campagne du lien entrant sont utilisés pour renseigner les valeurs des paramètres de **media\_source** et de **campagne** dans le lien sortant.

> 📄 **Exemple**
>
> **URL entrant** : https://hotel.me/incoming_mediasource=twitter&incoming_campaign=big_social
>
> **URL sortant** : https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="Lien d'attribution de base d'AppsFlyer">

Les liens d'attribution AppsFlyer peuvent être utilisés lorsque la source média est un réseau publicitaire de clics. Lorsque vous configurez un tel lien dans AppsFlyer, vous avez la possibilité d’ajouter un paramètre **de redirection d’URL (af\_r)** avec le chemin d’URL souhaité vers votre site web mobile pour l’attribution de campaign-to-app web. Évitez que le script ne crée un URL OneLink sortant, car certaines des données du clic d’origine pourraient être perdues.

**Action** Utilisez l’argument **urlSkipList** pour répertorier le paramètre **af\_r**.

**Résultat**: Lorsque le Smart Script trouve le paramètre **af\_r** dans le lien entrant, il ne produit pas d'URL sortant et le développeur doit décider quel lien placer en tant qu'URL sortant, puis l'intégrer.

> 📄 **Exemple**
>
> **URL entrante :** https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_r=hotel.me
>
> **URL sortant** : Pas d'URL sortant.

</Accordion>

<div id="web-referrer-mapping" />

<Accordion title="Mapping des référents web">

Le mapping des référents web vous permet de connaître la page par où les utilisateurs sont entrés sur votre site web (ex : depuis une recherche organique), et donc d'enrichir les données pour mieux analyser les installations et réengagements issus de votre flux Smart Script web-to-app.

Vous pouvez configurer le Smart Script pour qu'il collecte ces informations à partir du champ de l'en-tête HTTP `Referer` de votre page d'accueil ou site web. Ce champ indique l'URL de la page qui contient le lien sur lequel les utilisateurs ont cliqué avant d'être orientés vers votre page web.

**Configurer le script qui permet de récupérer le référent web**

1. Ouvrez la page **Smart Script**
2. Dans la section **Web Referrer Mapping**, sélectionnez la clé de paramètre de l'URL sortant pour la valeur du référent web :
   * af\_channel - Paramètre disponible dans les tableaux de bord et les données brutes
   * af\_sub1-5 - Le paramètre est disponible dans les données brutes, dans les colonnes **af\_sub1-5** et dans la colonne **URL d’origine**.
   * Paramètre personnalisé - Il est constitué du nom et de la valeur du paramètre. Le paramètre s'affiche dans la colonne **URL d’origine** des données brutes.

Pour en savoir plus sur l'attribution des recherches organiques pour les réengagements qui utilisent les Liens Universels et les Liens d'App, rendez-vous <Anchor target="_blank" href="/marketers/fr/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">ici</Anchor>.

</Accordion>

<div id="desktop" />

<Accordion title="Desktop">

La plupart des cas d'utilisation présentés dans cet article concernent des utilisateurs provenant d'appareils mobiles. Ainsi, lorsqu'ils sont dirigés du site web mobile vers un app store, ils peuvent immédiatement télécharger votre application.

Toutefois, les utilisateurs desktop ne doivent pas être immédiatement redirigés vers un app store, car leur appareil (PC ou portable) n'est pas compatible avec les téléchargements d'apps mobile.

**Pour configurer le script des utilisateurs desktop** :

* Dans votre <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">template OneLink</Anchor>, définissez un URL de destination **lorsqu'un clic est effectué sur le lien depuis un ordinateur.** L'URL doit rediriger vers une page web / landing page dédiée. La landing page peut contenir un formulaire web permettant d'indiquer ses coordonnées pour obtenir un SMS ou un e-mail avec un lien pour télécharger l'app. Vous pouvez créer le formulaire web et le fournir à l'URL dans le script.

**Résultat :** Le script détecte l'appareil ou la plateforme sur lequel l'utilisateur se trouve. S’il s’agit d’un appareil desktop, le script génère un URL OneLink sortant qui redirige l’utilisateur vers votre page web / landing page dédiée.

Voir aussi <Anchor target="_blank" href="/marketers/fr/docs/qr-to-app-conversion">Conversion desktop-to-app</Anchor>.

</Accordion>

<div id="qr-codes" />

<Accordion title="QR Codes">

Smart Script affiche un QR code sur votre page web, au lieu d'un bouton contenant un lien. 

**Pour afficher un QR code :**

1. Assurez-vous d’utiliser Smart Script 2.1 (et version au delà) lorsque vous configurez votre Smart Script.
2. Demandez à votre développeur de suivre <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#create-a-qr-code-with-the-smart-script-result">les instructions disponibles</Anchor> pour créer un QR code avec le résultat Smart Script.
3. [Recommandé] Demandez au développeur de :
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#create-a-qr-code-with-the-smart-script-result">Personnaliser le QR code</Anchor> en ajoutant le logo de votre app au centre du code et en choisissant une couleur.
   * Afficher le QR code lorsque les utilisateurs sont sur desktop, et afficher le bouton avec un lien lorsque les utilisateurs sont sur mobile.

**Résultat :** Le script affiche un QR code au lieu d'un bouton avec un URL derrière.

> 📄 **Exemple**
>
> **URL entrant** :
>
> https://hotel.me/qr_code.html?incmp=gogo&inmedia=email
>
> **URL sortant**:
>
> https://hotel.onelink.me/LtRd/?af_js_web=true&af_ss_ver=2_1_0&pid=email&c=gogo
>
> **QR Code sortant** :
>
> ![](https://files.readme.io/2f06149c901d8a97c2a544b8196e9afecbe3b3748ed8419a39c2dc5e3afa61ba-42045454923153.png)

</Accordion>

<div id="impressions" />

<Accordion title="Impressions">

Le Smart Script OneLink peut être utilisé pour compter les impressions sur votre site web. Pour ce faire, le développeur doit appeler la fonction d'impression. Les installations sont ensuite attribuées aux impressions par le biais de l'<Anchor target="_blank" href="/marketers/fr/docs/measure-view-through-engagements">attribution des vues.</Anchor>

**Remarque** :

* La comptabilisation des impressions s’ajoute au nombre de clics produits par l’URL issue de Smart Script. Smart Script peut être utilisé pour compter soit les clics, soit les impressions, soit les deux.
* L’attribution view-through par Smart Script ne fonctionne que sur les appareils de type mobile et non sur les desktop.

**Pour attribuer de nouvelles installations à ces impressions (c'est-à-dire l'attribution view-through):**

1. Assurez-vous d’utiliser Smart Script 2.3+ lorsque vous configurez votre Smart Script.
2. Demandez à votre développeur <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#fire-an-impression">d’appeler la fonction d’impression</Anchor> dans Smart Script.
3. Vérifiez que <Anchor target="_blank" href="/marketers/fr/docs/measure-view-through-engagements">l'attribution view-through soit bien activée</Anchor>.

> 🚧 **Important !**
>
> À compter du 1er février 2023 (version stable de Chrome 110), les modifications de Google pour <Anchor target="_blank" href="https://developer.chrome.com/en/docs/privacy-sandbox/user-agent/">réduire les données relatives aux User-Agent</Anchor> seront effectives. Pour obtenir des <Anchor target="_blank" href="https://www.appsflyer.com/glossary/view-through-attribution/">attributions view-thorough</Anchor> via Smart Script OneLink pleinement fonctionnelles, vous devez utiliser la version 2.3 (et au-delà) du Smart Script OneLink.

</Accordion>

## Informations supplémentaires

<div id="faq" />

<Accordion title="FAQ">

#### **Est-ce que l’URL entrant, qui sert à générer les liens OneLink, peut-il fonctionner** **si l'utilisateur navigue vers une autre page du site web ?**

Oui. Oui. Les paramètres de l'URL entrant sont stockés pour la durée de la session de navigation et ils sont appliqués aux paramètres sortants du lien OneLink généré par Smart Script. Pour plus d'informations sur l'implémentation, consultez notre <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#preserve-incoming-url-parameters-across-pages">dev hub.</Anchor>

#### **Pourquoi j'obtiens une erreur lorsque j'implémente Smart Script via Google Tag Manager  ?**

Une erreur « JavaScript too long » s'affiche parfois lorsque vous générez le Smart Script dans AppsFlyer et que vous essayez de l'insérer dans Google Tag Manager (GTM). Si cela se produit, supprimez la balise GTM et créez-en une nouvelle.

#### **Est-il possible d'ajouter un paramètre qui ne figure pas dans la liste ?**

Oui. Sur votre page Smart Script OneLink, cliquez sur + **Nouveau paramètre** pour mapper des paramètres supplémentaires.

* Les nouveaux paramètres peuvent être des paramètres personnalisés, ou des paramètres propres à AppsFlyer qui n'apparaissent pas dans le menu déroulant.
  * Consultez tous les [arguments supplémentaires](/docs/set-up-smart-script-to-convert-web-visitors#arguments) (configurations des paramètres) que vous pouvez utiliser.
* Dans l'option Custom du menu déroulant renseignez votre paramètre dans le champ **Paramètres de l'URL sortant**.

Exemple : pour ajouter is\_retargeting comme paramètre, le paramètre Custom sera sélectionné dans le champ **mapping pour**, puis notre paramètre is\_retargeting sera appliqué dans le champ **Paramètres de l'URL sortant**.

![Smart_Script_Custom.jpg](https://files.readme.io/5a09d18b01ece93bbb47667b676039c98742ebc3b88c5235ad92c7e44d5316b9-small-42045454926609.jpg)

#### **L'adset et les autres paramètres ne s'affichent pas dans la liste déroulante**

Nous vous recommandons de désactiver les bloqueurs de publicité installés sur votre navigateur pour créer ou ajouter de nouveaux paramètres. Les bloqueurs de publicité suppriment parfois les options qui contiennent le mot « publicité » ( ad).

#### **Quels navigateurs sont compatibles avec Smart Script ?**

Smart Script utilise Javascript et fonctionne sur tous les navigateurs.

</Accordion>

<div id="specs-and-limitations" />

<Accordion title="Cahier des charges et limitations">

| **Spécifications** | **Remarques** |
| --- | --- |
| Schéma d'URI | Même si un schéma d’URI est défini dans le template OneLink pour ouvrir l’app aux utilisateurs existants, en ce qui concerne les liens créés à l’aide de Smart Script, le développeur doit ajouter aux URL le paramètre af\_dp avec le schéma d’URI en tant que <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#set-additional-custom-parameters">paramètre personnalisé</Anchor>. |
| **dans l'URL entrant**| Smart Script rencontre des problèmes lors de la gestion des URL entrants qui incluent un symbole de hachage ('#') précédant les paramètres de la requête (indiqué par un signe '?'). Dans ce cas, Smart Script reprend les valeurs par défaut. |

</Accordion>

<div data-zendesk-anchors="setup=configuration h_01H95PGMNWR12KQ2P0KT8BBGEC=configuration set-up-onelink-smart-script=configurer-smart-script-onelink h_01H95PGMNW6N63XQ1EQSQSHHB2=configurer-smart-script-onelink scope-of-work=mise-en-oeuvre h_01H95PGMNWPBRHSZBPMKNJ2PS6=mise-en-oeuvre h_01H95PGMNWWYRRNVNTK31XYRN3=how-to-create-a-onelink-smart-script h_01H95PGMNW5HA4FWBFW7AR89AV=important- h_01H95PGMNXZAES8DPJ1B4E1QV8=how-to-edit-or-delete-a-script h_01H95PGMNX5ZT7DPV2WBG0CTKB=important--1 h_01H95PGMNXNT9C07B0YTS1KK82=how-to-duplicate-a-script h_01H95PGMNXWJ9V5JW9JEAHF81S=argument-structure h_01H95PGMNXR2HTV1EF07QVQB6W=arguments arguments-parameters-and-values-to-implement-the-smart-script::d4f6bf94=arguments-param%C3%A8tres-et-valeurs-pour-impl%C3%A9menter-le-smart-script h_01H95PGMNXPMCM73XT3GTDVAXJ=arguments-param%C3%A8tres-et-valeurs-pour-impl%C3%A9menter-le-smart-script h_01H95PGMNX4B8W84DHJR9T4CR2=advanced-arguments arguments-parameters-and-values-to-implement-the-smart-script=arguments-avanc%C3%A9s-param%C3%A8tres-et-valeurs-pour-impl%C3%A9menter-le-smart-script h_01H95PGMNXCAHTTJATG75Y3TRN=arguments-avanc%C3%A9s-param%C3%A8tres-et-valeurs-pour-impl%C3%A9menter-le-smart-script use-cases=cas-dutilisation h_01H95PGMNXBPFFNE44YGGECBPR=cas-dutilisation h_01H95PGMNX3W95JW47YQGSEYQ6=utm-parameters h_01H95PGMNXGZZEMZ6PMAB4XFQQ=google-ads-gclid h_01H95PGMNXZT08G8RTMMG6BQCJ=remarque h_01H95PGMNXHJXGB2QXH0YTB6Z0=facebook-click-id h_01H95PGMNXBKXFG9M169WG89TK=srns-owned-media-and-other-media-source-links h_01H95PGMNXZPB6CT3ZKJ2KMQ1J=exemple h_01H95PGMNX8Q0BASSESVD06MXE=appsflyer-attribution-links h_01H95PGMNX741EJGPF9G2DS67N=exemple-1 h_01HAS199KS0C0V3G41WGXTK4PF=web-referrer-mapping h_01H95PGMNY0P2354ZFVC92TMVC=desktop h_01H95PGMNYDSFP6GJDWC9AE0J2=qr-codes h_01H95PGMNYGJ9BJ86YCP7FYH6G=exemple-2 h_01H95PGMNYZBGZWNFESDTE9GY9=impressions h_01H95PGMNYX1FDT1KK9PQAMX5N=important--2 additional-information=informations-suppl%C3%A9mentaires h_01H95PGMNYB6A8VKEAH8Z8TDPE=informations-suppl%C3%A9mentaires h_01H95PGMNYKQ8TNM3KKK9EXANV=faq will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website=est-ce-que-lurl-entrant-qui-sert-%C3%A0-g%C3%A9n%C3%A9rer-les-liens-onelink-peut-il-fonctionner-si-lutilisateur-navigue-vers-une-autre-page-du-site-web h_01H95PGMNYM5X2K9J0WZW6PZ8A=est-ce-que-lurl-entrant-qui-sert-%C3%A0-g%C3%A9n%C3%A9rer-les-liens-onelink-peut-il-fonctionner-si-lutilisateur-navigue-vers-une-autre-page-du-site-web why-do-i-get-an-error-when-implemeting-smart-script-via-google-tag-manager=pourquoi-jobtiens-une-erreur-lorsque-jimpl%C3%A9mente-smart-script-via-google-tag-manager- h_01H95PGMNYSQX6BJCN56D4XZZF=pourquoi-jobtiens-une-erreur-lorsque-jimpl%C3%A9mente-smart-script-via-google-tag-manager- can-i-add-parameters-that-are-not-listed=est-il-possible-dajouter-un-param%C3%A8tre-qui-ne-figure-pas-dans-la-liste h_01H95PGMNY2AVJ0CYDAM62Q9PA=est-il-possible-dajouter-un-param%C3%A8tre-qui-ne-figure-pas-dans-la-liste adset-and-other-parameters-are-not-showing-in-the-dropdown=ladset-et-les-autres-param%C3%A8tres-ne-saffichent-pas-dans-la-liste-d%C3%A9roulante h_01H95PGMNY97BY6BCPPMYHBF0Q=ladset-et-les-autres-param%C3%A8tres-ne-saffichent-pas-dans-la-liste-d%C3%A9roulante what-browsers-does-smart-script-work-on=quels-navigateurs-sont-compatibles-avec-smart-script h_01H95PGMNY5AV0DTX51X0DJMTK=quels-navigateurs-sont-compatibles-avec-smart-script h_01H95PGMNY4W9X51KV6GM4BSPG=specs-and-limitations" />

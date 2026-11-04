---
title: Guide d'intégration des clics d’app d’Apple
metadata:
  keywords:
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
  created_at: '2020-10-09T00:42:10Z'
  edited_at: '2024-08-22T08:56:01Z'
  id: 360014262358
  locale: fr
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/fr/articles/360014262358
---
> **En bref :** Les clips d’app permettent aux utilisateurs d'iOS 14 ou d'une version ultérieure d'accéder rapidement à votre app. AppsFlyer permet l'attribution des clips d’app et redirige les utilisateurs qui ne peuvent pas les utiliser (par exemple, les utilisateurs d'Android) si nécessaire.

![app_clip_flow_3.png](https://files.readme.io/1a5ec7a6b8a061955742d8e79ba78fa0262c0609e1e801decc92300d6c24a774-360012832058.png)

<div id="app-clip-integration" />

## Intégration des clips d’app

* Les clips d'app permettent aux utilisateurs d'iOS 14 d'accéder rapidement et facilement à l'expérience d'une app, sans avoir à la télécharger entièrement.
* Les clips d’app sont installés et lancés à partir d'une invocation (par exemple, un QR code ou une étiquette NFC). **Remarque** : Les bannières Safari Smart App et les liens dans les messages ne sont pas pris en charge.
* Le SDK AppsFlyer est nécessaire pour l'attribution des clics, des installations, des événements in-app et des installations de l'application complète à partir des clips d’app.
* Indépendamment du SDK, OneLink redirige les utilisateurs si nécessaire :
  * Utilisateurs n'ayant pas installé l'app :
    * Avec iOS 14 ou une version plus récente, redirection vers le clip d’app.
    * Avec iOS 13 ou une version antérieure, ou Android, redirection en fonction de vos paramètres dans OneLink (vers l’app store, etc.).
  * Les utilisateurs qui ont installé l'app sont dirigés vers cette dernière en fonction du lien universel ou du lien d’app configuré dans OneLink.

<div id="considerations" />

### Attention

* Les clips d'app peuvent avoir une taille maximale de 10 Mo. Le SDK d'AppsFlyer fait ~1,5 Mo.
* Aucun identifiant publicitaire n'est disponible.
* Les clips d’app sont supprimés automatiquement par le système d'exploitation après une période d'inactivité de 30 jours.

<div id="example" />

> 📄 **Exemple**
>
> Mark est le responsable marketing d'une chaîne de cafés. Il fait appel à son développeur iOS pour créer un clip d’app qui permet aux clients de sauter la file d'attente et de commander en quelques secondes. Il leur suffit de s'identifier à l'aide d’<Anchor target="_blank" href="https://developer.apple.com/sign-in-with-apple/">Apple Sign-in</Anchor>, de commander un café et de payer à l'aide d'<Anchor target="_blank" href="https://developer.apple.com/apple-pay/">Apple Pay.</Anchor> Le développeur ajoute le SDK AppsFlyer et s'assure qu'il fonctionne à la fois dans l'app et dans le clip d’app.
>
> Mark crée un OneLink et affiche le QR code dans le café, avec le slogan « N’attendez pas ! »
>
> Le client scanne le QR code et :
>
> * S'il dispose d'un appareil équipé d'iOS 14 ou d'une version ultérieure, le clip d’app s'ouvre (avec la bonne succursale de café et un coupon de réduction).
> * S'il a déjà installé l'app complète, celle-ci s'ouvre sur la page du café de la commande.
> * S'il n’a pas l'app et qu'il dispose d'un appareil équipé d'iOS 13 ou d'une version antérieure, ou d'Android, la page de l'app du café dans l’app store s’ouvre.
>
> Mark utilise le tableau de bord et les rapports d'AppsFlyer pour connaître le nombre de clics et d'installations que reçoit le clip d’app - et le nombre d'utilisateurs qui finissent par télécharger l'app complète.

<div id="metrics-and-reporting" />

## Mesures et rapports

Les données analytiques et brutes des clips d’app sont disponibles sur la plate-forme en fonction de l'activité de l'utilisateur décrite dans le tableau suivant.

| Action de l'utilisateur | Événement AppsFlyer | Aperçu du tableau de bord et des outils d'analyse | Données Brutes |
| --- | --- | --- | --- |
| Invocation (exemple : QR Code) | Pas d'événement | Pas d'événement | Pas d'événement |
| Cliquez sur App Card pour ouvrir les clips d’app | Cliquez et installez les attributs à la source d'invocation | <ul><li>Clics</li><li>Installations</li></ul> | <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor> |
| Utilise un clip d’app | <ul><li>[Facultatif] Le développeur envoie un événement in-app</li><li>Après le premier lancement du clip d’app, les lancements suivants sont comptabilisés comme des sessions.</li></ul> | <ul><li>Évènement in-app</li><li>Session</li></ul> | <ul><li>Événement in-app envoyé par le développeur</li><li><Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor></li></ul> |
| Téléchargement et lancement de l'app complète | Évènement in-app | Événement in-app nommé af\_app\_clip\_to\_full\_app | <ul><li>Événement in-app nommé af\_app\_clip\_to\_full\_app</li><li><Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |
| Utilisation continue de l'app complète | [Facultatif] Le développeur envoie un événement in-app | Évènement in-app | <ul><li>Événement in-app envoyé par le développeur</li><li><Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |

**Tableau de bord des cohortes**

Visualisez les performances du clip d’app dans le <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard#trend-type-user-lifetime-performance">tableau de bord des cohortes</Anchor>, où vous pouvez :

* Voyez combien de temps il faut aux utilisateurs pour passer du clip d’app à l'installation complète.
* Utilisez l'indicateur de conversion in-app pour comparer les performances de différentes campagnes d'invocation.

<div id="app-clip-implementation" />

## Mise en œuvre du clip d’app

La procédure suivante détaille ce que vous et le développeur iOS devez faire pour développer et intégrer des clips d’app.

<div id="scope-of-work" />

#### Mise en application

| **Personnes concernées**<ul><li>**Annonceur** :<ul><li>Configure les clips d’app Apple dans les modèles OneLink.</li><li>Place les liens OneLink dans le portail Apple App Store Connect.</li><li>Affiche les mesures dans le tableau de bord et les rapports d'AppsFlyer.</li></ul></li><li>**Développeur iOS** :<ul><li>Crée le clip d'app</li><li>Intègre le SDK AppsFlyer dans le clip d’app.</li></ul></li></ul> |
| --- |
| **Conditions techniques**<ul><li>Un compte AppsFlyer avec au moins une app.</li><li>Un modèle OneLink avec des liens universels et un lien OneLink pour diriger les utilisateurs de l'app complète.<br />**Recommandation** : Le modèle et le lien que vous utilisez pour le clip d'app envoient tous les utilisateurs qui n'ont pas votre app complète vers le clip d'app. Par conséquent, envisagez de disposer d'un modèle et d'un lien personnalisé distincts pour les cas où vous souhaitez envoyer ces utilisateurs vers l'App Store, au lieu du clip d’app.</li></ul> |

<div id="develop-app-clip" />

<Accordion title="Développer un clip d'app">

Pour des instructions complètes sur la façon dont les développeurs créent un clip d’app, voir le <Anchor target="_blank" href="https://developer.apple.com/app-clips/">Guide des clips d’app Apple pour les développeurs</Anchor>.

Pour un exemple d'app simplifiée qui démontre l'utilisation des clips d’app et leur intégration dans une app complète, voir le <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips/">Guide des clips d’app Apple.</Anchor>

</Accordion>

<div id="integrate-sdk" />

<Accordion title="Intégrer le SDK">

* Le SDK est nécessaire pour l'attribution par AppsFlyer des clics, des installations, des événements in-app et des installations via le clip d’app par rapport aux installations complètes.
* OneLink redirige les utilisateurs indépendamment de l'intégration du SDK.

**Pour installer le SDK et configurer le SDK d’app complet**:

Envoyez les liens suivants à votre développeur iOS et dites-lui de suivre les instructions pour les points suivants :

* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-sdk-integration">Intégration du SDK aux clips d’app</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-to-full-app-install">Configuration de l'attribution des installations à partir des clips d’app</Anchor>
* [Facultatif] <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events">Configurez les événements in-app</Anchor>, si vous n'avez pas encore d'événements in-app mesurés pour votre app complète, ou si vous souhaitez utiliser des événements in-app différents pour le clip d’app.

</Accordion>

<div id="configure-onelink" />

<Accordion title="Configuration OneLink">

**Conditions préalables** :

* <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">Modèle OneLink</Anchor> pour votre app complète avec les liens universels iOS configurés.
* <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">Lien OneLink</Anchor>.
* **Recommandation** : Le modèle et le lien que vous utilisez pour le clip d'app envoient tous les utilisateurs qui n'ont pas votre app complète vers le clip d'app. Par conséquent, envisagez de disposer d'un modèle et d'un lien personnalisé distincts pour les cas où vous souhaitez envoyer ces utilisateurs vers l'App Store, au lieu du clip d’app.

**Pour configurer le modèle OneLink pour votre clip d’app** :

1. Dans le tableau de bord d'AppsFlyer, allez dans **Engagement** > **Gestion OneLink**.
2. Sélectionnez le **modèle OneLink** que vous utilisez pour diriger les utilisateurs vers votre app complète.
3. Assurez-vous que les liens universels sont configurés dans le modèle OneLink. (Voir les <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">instructions</Anchor> pour l'ajout de liens universels).
4. Cliquez sur **Enregistrer**.  
   Le fichier AASA est mis à jour pour prendre en charge les clips d’app.
5. Dans le tableau de bord d'AppsFlyer, allez dans **Engagement** > **Gestion OneLink**.
6. Sélectionnez le **lien personnalisé OneLink** basé sur le modèle que vous avez configuré aux étapes 1 à 4 et que vous utilisez pour diriger les utilisateurs via votre clip d’app.
7. Assurez-vous d’avoir indiqué une source média (pid).  
   La source média doit être spécifiée dans l'URL (par exemple : **pid=chartboost\_int**) ou contenue dans le lien.

**Pour vérifier que les clips d’app sont activés sur AppsFlyer OneLink :**

1. Créez une URL pour obtenir votre fichier d'association. L'URL est créée en prenant le domaine de votre modèle OneLink et en ajoutant `/.well-known/apple-app-site-association`.   
   Exemple : `coffee.onelink.me/.well-known/apple-app-site-association`.
2. Allez à l'URL de votre fichier d'association.  
   Le fichier apple-app-site-association est automatiquement téléchargé.
3. Ouvrez le fichier apple-app-site-association avec un éditeur de texte (par exemple, Notepad).
4. Assurez-vous que le fichier contient le mot "**appclips**" et que l'ID du bundle se termine par **".Clip**". Exemple :  

   ```java
   "appclips": {
       "apps": [
         "ABCD1234.id.your.app.Clip",
         ...
       ]
   ...
   }
   ```

   Si c'est le cas, vous avez réussi à mettre en place des clips d’app du côté d'AppsFlyer, et le clip d’app est mis en œuvre sur n'importe quel modèle OneLink avec le même sous-domaine.

</Accordion>

<div id="configure-app-store-connect" />

<Accordion title="Configurer App Store Connect">

**Conditions préalables** : Achèvement de la [configuration du modèle OneLink pour les clips d'app](/docs/apple-app-clips-integration-guide#configure-onelink)

**Pour configurer votre clip d’app afin qu'il fonctionne avec OneLink** :

1. Sur la page de votre app dans App Store Connect, allez dans **Build** > **Statut de domaine**.
2. Assurez-vous que votre domaine OneLink s'affiche sous **Build domains** et que les **statuts Cache** et **Debug** sont tous deux validés.
3. Dans le tableau de bord d'AppsFlyer, allez dans **Engagement** > **Gestion OneLink**.
4. Survolez l'icône **Actions** du lien que vous souhaitez utiliser et cliquez sur **Obtenir l'URL**.
5. Enregistrez l'URL courte (ou le préfixe de l'URL longue).
6. Sur la page de votre app dans App Store Connect, allez dans **Clip d’app** > **Modifier les expériences avancées** > **+Ajouter** > **Suivant.**
7. Dans **URL expérience clip d’app**, collez l'URL personnalisée OneLink que vous avez enregistrée à l'étape 5.  
   **Remarque** : Vous pouvez ajouter des paramètres de requête après l'URL personnalisée principale, mais vous ne pouvez pas modifier le chemin d'accès.
8. Cliquez sur **Suivant**.  
   Votre clip d’app est maintenant configuré pour fonctionner avec OneLink. Des instructions supplémentaires concernant les paramètres App Store Connect sont disponibles dans le <Anchor target="_blank" href="https://developer.apple.com/documentation/app_clips/configuring_your_app_clip_s_launch_experience">guide du développeur Apple.</Anchor>

</Accordion>

<div id="testing" />

<Accordion title="Test">

**Conditions préalables** : Un <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">appareil de test enregistré</Anchor> avec iOS 14 sans votre app complète installée.

**Pour tester votre intégration OneLink/clip d’app :**

1. Dans le tableau de bord d'AppsFlyer, allez dans **Engagement** > **Gestion OneLink**.
2. Survolez l'icône **Actions** du lien que vous souhaitez tester et cliquez sur **Obtenir l'URL**.
3. Scannez le QR code avec votre appareil.  
   La carte clip d’app s'affiche sur votre appareil, indiquant que l'intégration OneLink/clip d’app est correctement configurée.

</Accordion>

<div id="traits-and-limitations" />

## Caractéristiques et limitations

<div id="traits-and-limitations::26141033" />

<Accordion title="Caractéristiques et limitations">

| Trait/Limitation | Description |
| --- | --- |
| Méthodes d'invocation | <ul><li>Les QR codes et les étiquettes NFC sont pris en charge.</li><li>Les bannières Safari Smart App et les liens dans les messages ne sont pas pris en charge.</li></ul> |
| SKAdNetwork | La fonctionnalité SKAdNetwork n'est pas disponible. Par conséquent, les installations via les clips d’app s'affichent dans le tableau de bord de SKAdNetwork comme étant organiques. |
| OneLink | Une seule expérience de clip d’app avancée est autorisée par lien personnalisé OneLink. Cela signifie que vous ne pouvez pas ajouter de chemins supplémentaires à OneLink dans App Store Connect. |
| Protect360 | Protect360 ne prend pas en charge les clips d’app. |

</Accordion>

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/guides/ios-14-app-clips/">Solution d'attribution pour les clips d’app Apple par AppsFlyer</Anchor>

<div data-zendesk-anchors="app-clip-integration=int%C3%A9gration-des-clips-dapp h_01HDNZQTCBXY0Y3QYCBNVH7EAW=int%C3%A9gration-des-clips-dapp considerations=attention h_01HDNZQTCBPJWY6H2M452QH644=attention h_01HDNZQTCB7NB682YTSMNCJSDP=exemple metrics-and-reporting=mesures-et-rapports h_01HDNZQTCBNG3TYRAA7GVPF39P=mesures-et-rapports app-clip-implementation=mise-en-%C5%93uvre-du-clip-dapp h_01HDNZQTCBJK7SB96G8A4DHR34=mise-en-%C5%93uvre-du-clip-dapp scope-of-work=mise-en-application h_01HDNZQTCB1AKW9QFRRM9VVN4D=mise-en-application h_01HDNZQTCBN04J3GA8H64V70YY=develop-app-clip h_01HDNZQTCBHHENFYJK7MFJTZ14=integrate-sdk h_01HDNZQTCBN9QV4MZAAWMV164Y=configure-onelink h_01HDNZQTCC6F8TTM2FRQK6DB2E=configure-app-store-connect h_01HDNZQTCCN2BX9NZ4027ZCEFB=testing traits-and-limitations=caract%C3%A9ristiques-et-limitations h_01HDNZQTCCMW2YNK1G34EBM7DM=caract%C3%A9ristiques-et-limitations h_01HDNZQTCCV0S78NRK00PK4S0J=traits-and-limitations::26141033 h_01HDNZS83EKJNZGG1QEVS9RMCA=articles-connexes" />

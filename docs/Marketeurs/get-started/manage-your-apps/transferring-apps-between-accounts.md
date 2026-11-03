---
title: Transférer des apps entre deux comptes
metadata:
  keywords:
    - Account
    - Advertisers
    - Agencies
    - moving apps
    - move app
    - app transfer
    - transferring apps
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2018-07-24T07:56:37Z'
  edited_at: '2024-05-26T12:05:42Z'
  id: 360001336005
  locale: fr
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/fr/articles/360001336005
---
> **En bref :** Vous pouvez transférer des apps entre des comptes AppsFlyer en suivant les étapes décrites dans cet article (réservé aux admins des comptes expéditeur et destinataire).

![5638-Transfering-an-app-NEW1.gif](https://files.readme.io/f4288a79bbd96e8cf828cf0ca9ae9ef994400f702cd66108d2861e3a405c4d79-360010967257.gif)

## Transfert d'app entre les comptes

Pour transférer une app entre deux comptes AppsFlyer, les propriétaires d'apps côté expéditeur et destinataire (tels que représentés par leur admin de compte AppsFlyer) doivent remplir les conditions préalables nécessaires au transfert et accepter le transfert.

### Conditions techniques

* Assurez-vous de posséder les e-mails des comptes de l'expéditeur et du destinataire (admin).
* Les deux comptes sont actifs. Les comptes suspendus ne peuvent ni envoyer ni recevoir d'applications.
* Aucun compte n'a de factures impayées

### Procédure de transfert d'app

Voici un aperçu de la procédure de transfert d'une application :

1. L'expéditeur demande à AppsFlyer de transférer les apps sélectionnées puis saisit l'e-mail de l'admin destinataire.
2. Le destinataire est informé et accepte de recevoir les apps.
3. Les admins côté expéditeur et destinataire reçoivent un avis de transfert en attente (par e-mail ainsi que sur la page **Mes apps**).   
   **Remarque :** Lorsque le transfert est en attente, chacun des admins peut choisir de supprimer la demande de transfert de l'application (c'est à dire d’annuler le transfert).
4. AppsFlyer transfère les applications. Si une des conditions préalables est incomplète, AppsFlyer contacte la partie concernée pour demander à ce qu'elle soit remplie.

<div id="app-transfer-scope" />

<Accordion title="Cadre du transfert de l'app">

Le tableau suivant détaille les fonctionnalités et paramètres de l'app qui sont transférés. Notez que l'expéditeur peut choisir, à sa discrétion, de supprimer certains paramètres et éléments de configuration avant le transfert.

<table><thead><tr><th>Élément</th><th>Transféré /<br/>non transféré</th><th>Détails / pouvoirs discrétionnaires</th></tr></thead><tbody><tr><td>Paramètres d'application </td><td><p>Transféré</p></td><td><p><strong>Discrétion :</strong> L'expéditeur peut supprimer la clé du serveur Firebase/GCM avant le transfert. </p></td></tr><tr><td rowspan="2">Partenaires intégrés</td><td>Transféré</td><td><p><span>Configuration de l'intégration, des coûts et des revenus (y compris les données relatives aux coûts et aux revenus)</span></p><p><strong>Discrétion :</strong> Si le destinataire n'a pas besoin que les partenaires intégrés soient transférés, l'expéditeur doit les désactiver et supprimer leurs configurations et identifiants (y compris les configurations de coût et de revenus publicitaires).</p></td></tr><tr><td>Non transféré</td><td><p>Autorisations du réseau publicitaire et de l'agence</p><p>Configurations et identifiants Twitter</p></td></tr><tr><td>Gestion des liens</td><td>Non transféré</td><td><p>Les modèles et les liens OneLink ne sont pas transférés automatiquement mais peuvent l'être par votre CSM.</p><strong>Discrétion :</strong> <ul><li>Pour transférer des modèles et des liens, contactez votre CSM ou envoyez un message à <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a>.</li><li>L'expéditeur peut supprimer les liens obsolètes avant le transfert.</li></ul></td></tr><tr><td>API Push</td><td>Transféré</td><td><p><strong>Discrétion :</strong></p><ul><li>Si le destinataire ne souhaite pas que les configurations de l'API Push (points de terminaison) soient transférées, l'expéditeur doit supprimer les paramètres. S'il ne le fait pas, les données continueront d'être envoyées aux points de terminaison définis par l'expéditeur.</li><li>Le destinataire peut également modifier les paramètres à réception pour s'assurer que l'expéditeur ne reçoive aucune données de niveau utilisateur. </li></ul></td></tr><tr><td>Smart Banners</td><td>Non transféré</td><td><p>Les bannières, les groupes de bannières, les créations et les sites web ne sont pas transférés. </p></td></tr><tr><td>Script intelligent</td><td>Non transféré</td><td><p><span>Les Smart Scrips créés dans l'interface utilisateur d'AppsFlyer ne seront pas disponibles dans le nouveau compte. </span></p></td></tr><tr><td>Agences</td><td>Non transféré</td><td>Les agences perdent l'accès à l'application.</td></tr><tr><td>Audiences</td><td>Non transféré</td><td>Les audiences sont supprimées.</td></tr><tr><td>Importation des coûts</td><td>N/A</td><td>Les fichiers d'importation des coûts historiques ne sont pas accessibles au destinataire. Ceci ne concerne pas l'historique des coûts. </td></tr><tr><td>Data Locker</td><td>Non transféré</td><td>L'app est supprimée de la configuration Data Locker et le compte de l'expéditeur ne reçoit plus les données de l'app. </td></tr><tr><td>Données historiques</td><td>Transféré</td><td> </td></tr><tr><td>Bundles de marque en PBA</td><td>Non transféré</td><td><p>Le bundle ne sera plus proposé à l'expéditeur si l'une des apps qu'il contient est transférée. Le destinataire ne peut pas accéder aux données PBA.</p><p>Cela signifie que si le client a besoin de continuer à utiliser PBA dans son nouveau compte, il doit supprimer son Bundle web avant que le transfert d'application ne soit terminé, sinon il ne pourra pas créer le même Bundle web dans son nouveau compte.</p></td></tr><tr><td>Données Protect 360</td><td>Transféré</td><td> </td></tr><tr><td>Données agrégées et brutes</td><td>Transféré</td><td> </td></tr><tr><td>Clé dev du SDK</td><td>Transféré</td><td> </td></tr><tr><td>Règles de validation</td><td>Transféré</td><td> </td></tr></tbody></table>

</Accordion>

## Procédures de transfert

Pour demander le transfert d'une ou plusieurs apps vers un autre compte AppsFlyer, lancez la procédure et vous serez guidé par l'assistant d'interface utilisateur.

<div id="sender" />

<Accordion title="Expéditeur">

**Pour soumettre une demande de transfert** :

1. Contactez l'admin du destinataire :
   1. Déterminez et acceptez le [cadre du transfert de l'application](/docs/transferring-apps-between-accounts#app-transfer-scope). Assurez-vous de bien comprendre ce qui est et n'est pas transféré et que vous êtes tous les deux correctement préparés.
   2. Demandez au destinataire de vous fournir l'e-mail d'admin qu'il utilise dans AppsFlyer.
2. Effectuez l'une des opérations suivantes : *** Pour transférer une application : Dans la barre de menu supérieure > **Mes Apps** > Ouvrir le menu d'action de l'application (...) > Sélectionnez l'**Transfer app**
   * Pour transférer 2 ou plusieurs applications: Dans la barre de menu supérieure > <strong>Mes Apps</strong> > Ouvrir le menu d'action de l'application (...) > Sélectionnez l'<strong>Transfer app</strong>
3. Choisissez l'application ou les applications à transférer.
4. Cliquez sur **Suivant**.
5. Saisissez l'e-mail de l'admin destinataire
6. Cliquez sur **Suivant**.
7. Lisez et signez les conditions générales.
   * Le destinataire et vous-même êtes informés (par e-mail) que la demande a bien été envoyée.
   * Vous serez notifié (par pop-up) si la demande nécessite l'intervention d'AppsFlyer.
   * Les apps s'affichent dans votre page **Mes apps** avec le statut «en attente de transfert vers `<receiver email>`. A ce stade, il est encore possible de supprimer la demande.[![App_transfer_sender_side.JPG](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)

</Accordion>

<div id="receiver" />

<Accordion title="Destinataire">

1. Contactez l'admin de l'expéditeur pour vérifier et accepter le [cadre du transfert de l'app](/docs/transferring-apps-between-accounts#app-transfer-scope). Assurez-vous de bien comprendre ce qui est et n'est pas transféré et que vous êtes tous les deux correctement préparés.
2. Vous recevrez une notification par e-mail vous indiquant que l'expéditeur a lancé la demande de transfert.
3. Sur la page **Mes apps**, cliquez sur **Vérifier la demande**. Une demande peut concerner une app, ou plusieurs.  
   [![App_transfer_receiver_side.JPG](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)
4. Vérifiez puis et acceptez ou rejeter chaque demande.
5. Lisez les conditions et, si vous les acceptez, apposez votre signature.
6. L'expéditeur et vous-même êtes informés par e-mail que la demande a été acceptée.
7. Les apps transférées apparaissent sur votre page **Mes Apps**.

<div id="delete-transfer-request" />

<Accordion title="Annuler la demande de transfert">

Avant la finalisation du transfert, la procédure de transfert d'app peut être supprimée (annulée) par l'expéditeur ou le destinataire.

**Pour annuler une demande de transfert d'app :**

* **Expéditeur admin :** Dans la barre de menu supérieure > **Mes Apps** > Section **Transfert en attente vers [email]** > Cliquez sur **Supprimer la demande**.  
  Les admins coté expéditeur et destinataire sont informés (par e-mail).
* **Administrateur du récepteur**:
* Dans la barre de menu supérieure > **Mes Apps** > Section des **applications en attente de transfert** > Cliquez sur **Rejeter**.  
  Les admins coté expéditeur et destinataire sont informés (par e-mail).

</Accordion>

</Accordion>

## Restrictions

Les limitations suivantes s'appliquent au processus de transfert de l'application :

* Les applications CTV ne peuvent pas être transférées.

<div data-zendesk-anchors="app-transfer-between-accounts=transfert-dapp-entre-les-comptes h_01HJR1G7Q71H5DAH1G9QFSYK35=transfert-dapp-entre-les-comptes prerequisites=conditions-techniques h_01HJR1G7Q7T1Q768MTTR3Y542X=conditions-techniques app-transfer-process=proc%C3%A9dure-de-transfert-dapp h_01HJR1G7Q7EDJZ4E1T17GWYGTP=proc%C3%A9dure-de-transfert-dapp h_01HJR1G7Q7AWF07RG2J4Q3V2KN=app-transfer-scope transfer-procedures=proc%C3%A9dures-de-transfert h_01HJR1G7Q7JB0XD3NGT0MWYJZ5=proc%C3%A9dures-de-transfert h_01HJR1G7Q7ERYXGB83D475AEPN=sender h_01EDBXVWAB5VBWT3XFK21KPV6W=receiver h_01HJR1G7Q8NEF5P5N95C6CGSF9=delete-transfer-request limitations=restrictions h_01HJR1G7Q82DBFJ9XPW53KXBZD=restrictions" />

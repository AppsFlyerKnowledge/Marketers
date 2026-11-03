---
title: Guide d'importation des coûts
metadata:
  keywords:
    - Ad Network
    - Agency
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Xpend
    - Marketers
    - ROI360
    - Ad Networks
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
    - Ad Networks
  created_at: '2019-09-15T15:53:44Z'
  edited_at: '2024-06-05T11:25:19Z'
  id: 360002516838
  locale: fr
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/fr/articles/360002516838
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** Cost Import, qui fait partie d'AppsFlyer ROI360, permet aux annonceurs de couvrir 100 % de leurs besoins en matière de rapports sur les coûts de leurs campagnes. Les annonceurs et les réseaux publicitaires peuvent enregistrer le coût de la campagne à partir de sources médiatiques qui ne signalent pas les dépenses par API ou par clic.

## Importation des coûts

![Adspendimport.jpg](https://files.readme.io/e870005c5f20531a2d06cc78b47a82a8a1f730f2c04728f5d0a5674c1c70129a-24507313816337.jpg)

## Données complètes sur les coûts des campagnes

Utilisez Cost Import pour agréger les coûts des campagnes provenant de sources médiatiques qui n'indiquent pas le coût par clic ou par API. Cela vous permet d'avoir une image complète des coûts et du retour sur investissement de vos campagnes dans le tableau de bord.

Le coût doit être enregistré au niveau de la campagne, les autres dimensions de la hiérarchie publicitaire étant facultatives. Les dépenses (coûts) sont déclarées à l'aide de fichiers CSV chargés sur le tableau de bord pour importation. Les données de coûts agrégées mises à jour sont disponibles dans le tableau de bord dans les 4 heures suivant l'importation.

Les annonceurs et les réseaux publicitaires peuvent envoyer et gérer des fichiers de dépenses. Les agences peuvent préparer des fichiers pour l'importation, mais l'annonceur doit télécharger les fichiers correspondants. 

Les données sur les dépenses publicitaires précédemment importées peuvent être remplacées si nécessaire.

Exemple de cas d'utilisation

* Enregistrez les coûts occasionnés par les réseaux qui n'envoient pas de données de coûts par API ou lien d'attribution
* Chaînes hors ligne, comme les campagnes radio et les panneaux d'affichage
* Influenceurs

Pour gérer l'importation des coûts, allez dans **Paramètres** > **Importation des coûts.** **Remarque :** La page d'importation des dépenses publicitaires est une page au niveau du compte. Cela signifie que les annonceurs gèrent les importations de toutes les applications du compte sur la même page.

## Préparation, téléchargement et importation de fichiers de dépenses publicitaires

Il existe deux flux de travail que vous pouvez utiliser pour préparer, charger et importer des fichiers de dépenses publicitaires :

* Téléchargez le fichier dans l'interface utilisateur.  
  **Remarque** :
  * Nous vous recommandons d'essayer d'abord cette méthode. En effet, les messages d'erreur dus à des problèmes de format et de contenu de fichier s'affichent immédiatement, ce qui vous permet de résoudre plus facilement les problèmes.
  * Cette méthode n'est pas disponible pour les applications sur les plateformes CTV, PC et console.
* Téléchargez le fichier par e-mail.
  * Pour les applications sur les plateformes CTV, PC et console, utilisez uniquement cette méthode.

Les deux flux de travail sont expliqués dans les sections qui suivent.

### Workflows de téléchargement

#### Flux de travail : Télécharger le fichier dans l'interface utilisateur

| Étape | Description | Lien |
| --- | --- | --- |
| 1 | Étape pour les réseaux publicitaires uniquement : Avant qu'un réseau publicitaire puisse envoyer des fichiers, l'annonceur doit accorder l'autorisation au réseau publicitaire | [Accorder l'autorisation d'importer des dépenses](/docs/import-cost-data#granting-an-ad-network-import-permission) |
| 2 | Préparez le fichier CSV<br /><br />**Remarque** : Les agences peuvent également préparer des fichiers pour leurs données. [En savoir plus](/docs/import-cost-data#preparing-a-csv-with-agency-data) | [Format de fichier CSV et schéma](/docs/import-cost-data#csv-file-format-and-schema) |
| 3 | Téléchargez et importez le fichier dans l'interface utilisateur | [Téléchargement de fichiers de dépenses publicitaires](/docs/import-cost-data#uploading-ad-spend-files) |
| 4 | Une fois l'importation terminée, utilisez l'interface pour surveiller l'importation :<ul><li>Statut</li><li>[Lignes correspondantes](/docs/import-cost-data#row-matching-and-the-unmatched-report) (dans de nombreux cas, un faible pourcentage de lignes correspondantes signifie que vous avez des erreurs dans les données)</li></ul> | [Actions d'importation de coûts](/docs/import-cost-data#ad-spend-import-actions) |
|  | Procédure supplémentaire : Remplacer l'importation précédente | [Remplacer les dépenses précédemment importées](/docs/import-cost-data#overwrite-correct-previously-imported-ad-spend) |

#### Flux de travail : Télécharger le fichier par e-mail

| Étape | Description | Lien |
| --- | --- | --- |
| 1 | Étape préalable pour les réseaux publicitaires : Avant qu'un réseau publicitaire puisse envoyer des fichiers, l'annonceur doit leur accorder une autorisation. | [Accorder l'autorisation d'importer des dépenses](/docs/import-cost-data#granting-an-ad-network-import-permission) |
| 2 | Conditions préalables : Obtenez un jeton de dépenses publicitaires | Afficher le jeton de dépense publicitaire |
| 3 | Préparez le fichier CSV<br /><br />**Remarque** : Les agences peuvent également préparer des fichiers pour leurs données. [En savoir plus](/docs/import-cost-data#preparing-a-csv-with-agency-data) | [Format de fichier CSV et schéma](/docs/import-cost-data#csv-file-format-and-schema) |
| 4 | Envoyer le fichier par e-mail | [E-mail](/docs/import-cost-data#sending-ad-spend-files-by-email) |
| 5 | AppsFlyer envoie un rapport d'état par e-mail ; il indique si l'importation a réussi ou si des problèmes ont été détectés. |  |
| 6 | Utilisez l'interface pour surveiller l'importation :<ul><li>Statut</li><li>[Lignes correspondantes](/docs/import-cost-data#row-matching-and-the-unmatched-report) (dans de nombreux cas, un faible pourcentage de lignes correspondantes signifie que vous avez des erreurs dans les données)</li></ul> | [Actions d'importation de coûts](/docs/import-cost-data#ad-spend-import-actions) |
|  | Procédure supplémentaire : Remplacer l'importation précédente | [Remplacer les dépenses précédemment importées](/docs/import-cost-data#overwrite-correct-previously-imported-ad-spend) |

### Procédures

<div id="csv-file-format-and-schema" />

<Accordion title="Format de fichier CSV et schéma">

Le format de fichier CSV, le schéma et les règles de validation des dépenses publicitaires sont détaillés ici. Si vous utilisez Excel ou Google Sheets pour créer le fichier, vous devez consulter les instructions de [mise en forme d'Excel](/docs/import-cost-data#using-excel-to-format-date-and-spend-fields-of-csv-files).

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv">Voir le fichier d'exemple</Anchor>.

Avant de poursuivre la lecture, prenez note des erreurs les plus courantes commises lors de la préparation du fichier CSV, comme illustré dans la capture d'écran suivante.

![importfile_en-us.png](https://support.appsflyer.com/hc/article_attachments/360007902297)

Le format de fichier CSV, le schéma et les règles de validation des dépenses publicitaires sont décrits en détail dans les sections suivantes. Si vous utilisez Excel ou Google Sheets pour créer le fichier, vous devez consulter les instructions de [mise en forme d'Excel](/docs/import-cost-data#using-excel-to-format-date-and-spend-fields-of-csv-files).

> 📘 **Remarque**
>
> N'utilisez pas Excel ou Google Sheets pour afficher ou vérifier que le fichier CSV est correctement formaté. Utilisez plutôt un [éditeur](/docs/import-cost-data#visual-inspection-of-the-csv-file-without-excel)

#### Règles de contenu et schéma des fichiers CSV relatifs aux dépenses publicitaires

| Élément | Exigence |
| --- | --- |
| Personnages interdits | Les champs au format chaîne ne peuvent pas avoir `=` `+``-`,, ou `@` comme premier caractère. Par exemple, `@example_campign` ou `=123` sont interdits. |
| Source média | <ul><li>Une source multimédia par fichier</li><li>Plusieurs applications pour la même source multimédia sont autorisées</li><li>Limites :<ul><li>N'envoyez pas de données de coûts depuis une source multimédia qui possède déjà une intégration de l'API Cost avec AppsFlyer. L'importation n'est pas autorisée depuis ces sources. Cela inclut les Meta Ads, Apple Search Ads et Snapchat.</li></ul></li></ul> |
| Propriétaire d'app | Un annonceur (propriétaire de l'application) par fichier est autorisé. Cela signifie que plusieurs applications du même annonceur sont autorisées. |
| Extension de nom de fichier | Exemple de fichier CSV : abc123.csv |
| Structure des fichiers | <ul><li>Format Les fichiers sont au format CSV, ce qui signifie que chaque colonne est séparée par une virgule. Notez que c'est ainsi qu'Excel formate les fichiers CSV par défaut. Si Excel met en forme le fichier avec un point-virgule (;), cela est lié au réglage régional de votre ordinateur.</li><li>**Ligne d'en-tête** : La première ligne est une ligne d'en-tête qui correspond au schéma</li><li>**Lignes de données** : Contient les colonnes obligatoires. **Remarque** : Assurez-vous qu'il n'y a aucun espace à la fin de vos données. Par exemple, [USD] (un espace après le **D**) doit être remplacé par [USD].</li><li>**Lignes vides** : Non autorisé</li><li>**Lignes dupliquées** ayant la même clé : Non autorisé. La clé est dérivée de l'utilisation des champs obligatoires.</li><li>**Cellules vides :** Les valeurs vides ne sont pas autorisées dans le fichier. Si vous ne souhaitez pas charger certains champs, ils ne doivent pas figurer dans le fichier.</li></ul> |
| Hiérarchie publicitaire | Toutes les données partielles téléchargées à un niveau hiérarchique inférieur remplaceront toutes les données depuis le niveau inférieur de la campagne.<br /><br />Exemple,  Si vous importez un fichier avec le coût de la campagne pour l'ensemble d'annonces 1 et que vous importez séparément un autre fichier pour l'ensemble d'annonces 2 de la même campagne, le coût total de la campagne sera remplacé et seules les données de l'ensemble d'annonces 2 seront affichées. Pour le coût total de la campagne, le fichier que vous importez doit inclure les ensembles d'annonces 1 et 2. |

#### Schéma CSV des dépenses publicitaires

<table><tbody><tr><th><p>Nom de la colonne</p><p><span>(sensible aux majuscules et minuscules)</span></p></th><th><p><span>Format/remarque</span></p></th><th><p><span>Exemple</span></p></th><th><p><span>Obligatoire</span></p></th></tr><tr><td><p><span>date</span></p></td><td><ul><li><span>La date à laquelle la dépense a été engagée</span></li><li>Format chaîne<br/>(Meilleure pratique) YYYY-MM-DD <br/>AAAA-MM-JJ <br/>MM-JD-AAAA <br/>MM/JJ/AAAA <br/> </li><li>Les dates futures ne sont pas autorisées</li><li> <strong>Bonnes pratiques</strong>  Utilisez le même fuseau horaire que celui défini pour votre application dans AppsFlyer.</li><li> <strong>Remarque</strong> : Utilisez-vous Excel/Google Sheets pour préparer le fichier ? <a href="./import-cost-data#using-excel-to-format-date-and-spend-fields-of-csv-files">Lisez ceci</a>. </li></ul></td><td><p><span>2019-05-30<br/>30/05/2019<br/>2019/30/5 <br/>2019/30/5<br/>05-30-2019<br/>2019/30/05</span></p></td><td><p><span>✓</span></p></td></tr><tr><td><p>app_id<span></span></p></td><td><ul><li>Format chaîne</li><li> <span>ID de l'application tel qu'il apparaît dans le tableau de bord</span>.</li><li>Plusieurs applications sont autorisées dans un seul fichier</li><li>Toutes les applications doivent appartenir au même annonceur</li></ul></td><td><ul><li><span>com.app.name </span></li><li><span> id12356789</span></li></ul></td><td><p><span>✓</span></p></td></tr><tr><td><p>Source média</p></td><td><ul><li>Format chaîne</li><li><span>Nom de la source <strong>multimédia</strong> tel qu'il apparaît dans le tableau de bord. <strong>Remarque :</strong> Incluez le suffixe _int s'il s'affiche dans le tableau de bord.</span></li><li> <span>Une seule source multimédia par fichier est autorisée.</span><span></span> </li></ul></td><td><p><span>network_x_int</span></p></td><td><p><span>✓</span></p></td></tr><tr><td><p><span>campagne</span></p></td><td><ul><li> Format chaîne </li><li> <span>Nom de la campagne</span> Si le nom de la campagne apparaît sur le réseau publicitaire, il doit correspondre (distinction majuscules/minuscules) au nom tel qu'il apparaît sur le réseau publicitaire.</li><li>N'utilisez pas le même nom de campagne pour plusieurs applications.</li></ul></td><td><p>campaign_a</p></td><td><p><span>✓</span></p><p><span><strong>Remarque</strong> : S'il existe des données d'attribution comportant à la fois un nom et un identifiant, le CSV doit contenir les deux pour qu'il y ait correspondance.</span></p></td></tr><tr><td><p><span>dépense</span></p></td><td><ul><li><span>Dépenses monétaires</span></li><li><span>Cinq chiffres autorisés après la virgule </span></li><li><span>La valeur 0 (zéro) est autorisée</span></li><li> <span>Remarque</span> : <ul><li><span>Le format « 2 874,12 » n'est pas autorisé.</span></li><li>Utilisez-vous Excel/Google Sheets pour préparer le fichier ? <a href="./import-cost-data#using-excel-to-format-date-and-spend-fields-of-csv-files">Lisez ceci</a>.</li></ul></li></ul></td><td><p><span>2874.12345</span></p></td><td><p><span><span>✓</span></span></p></td></tr><tr><td><p><span>geo</span></p></td><td><p>Format chaîne</p><p><span>Code de pays à deux lettres conforme à la <a href="https://www.iso.org/iso-3166-country-codes.html">norme ISO 3166</a>.  </span></p><p><span>Pour le Royaume-Uni, utilisez UK et <span></span> non GB.<br/><strong>Remarque</strong> : Assurez-vous d'envoyer deux caractères sans espaces.</span></p></td><td><p><span>US, CN, AU</span></p></td><td><p><span>Non</span></p></td></tr><tr><td><p><span>devise</span></p></td><td><ul><li>Format chaîne</li><li>Code de devise à trois lettres conforme à la norme ISO 4217. <strong>Remarque</strong> : Assurez-vous d'envoyer trois caractères sans espaces de début ou de fin.</li><li> <span>Un code de devise par application dans le fichier est autorisé. Les </span> <span>différentes applications peuvent avoir des codes de devise différents</span>. </li></ul></td><td><p><span>DOLLAR AMÉRICAIN, LIVRE STERLING, EURO, JPY</span></p></td><td><p><span>Non.</span></p><p><span>La valeur par défaut sera USD si ce champ est laissé vide.</span></p></td></tr><tr><td><p><span>ID de campagne</span></p></td><td>Format : Chaîne</td><td><p>abc1234def</p></td><td rowspan="5"><p>Non.</p><p><strong>Remarque</strong> : S'il existe des données d'attribution comportant à la fois un nom et un identifiant, le CSV doit contenir les deux pour qu'il y ait correspondance.</p></td></tr><tr><td><p><span>adset</span></p></td><td>Format : Chaîne </td><td>my_adset_1</td></tr><tr><td><p><span>adset-id</span></p></td><td>Format : Chaîne</td><td>id5678ghi</td></tr><tr><td><p><span>ad</span></p></td><td>Format : Chaîne </td><td>my_ad_name</td></tr><tr><td><p><span>ID publicitaire</span></p></td><td>Format : Chaîne </td><td>id91011jkl</td></tr><tr><td><p>site_id</p></td><td>Format : Chaîne </td><td>id1213mno</td><td>Non</td></tr><tr><td><p><span>canal</span></p></td><td>Format : Chaîne </td><td> Vidéo</td><td>Non</td></tr><tr><td><p><span>Mots-clés</span></p></td><td><p>Format : Chaîne</p></td><td><ul><li>mieux</li><li>application Better You</li><li>mieux vous en ligne</li></ul></td><td>Non</td></tr><tr><td><p><span>agency</span></p></td><td><ul><li>Le nom de l'agence. La valeur du paramètre af_prt)</li><li>Format : Chaîne</li></ul></td><td>AgencyName</td><td>Non</td></tr><tr><td colspan="4"><p><span><strong>Remarque :</strong> Les noms contenant des caractères autres que l'anglais doivent être codés en UTF-8.</span></p></td></tr></tbody></table>

</Accordion>

<div id="getting-an-ad-spend-token" />

<Accordion title="Obtenir un jeton de dépenses publicitaires">

Le jeton Ad Spend est utilisé pour vérifier que l'expéditeur de l'e-mail est autorisé à soumettre le fichier d'importation des coûts. Les jetons d'annonceur et de réseau publicitaire sont différents. 

> ❗️ **Attention !**
>
> * Les annonceurs ne partagent pas votre jeton avec les réseaux publicitaires.
> * Le réseau publicitaire possède son propre jeton unique.

* **Jeton de l'annonceur** :
  * Le même jeton est utilisé pour l'ensemble des apps du compte.
  * Tout utilisateur de compte peut récupérer le jeton Ad Spend
* **Jeton de réseau publicitaire** :
  * Le même jeton est utilisé pour **tous les annonceurs**.
  * En outre, l'annonceur doit autoriser [le réseau publicitaire](/docs/import-cost-data#granting-an-ad-network-import-permission) à soumettre des fichiers d'importation.

**Pour récupérer le jeton de dépenses publicitaires, procédez comme suit :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Paramètres** > Importation des **coûts**.
2. En haut à droite de la page, cliquez sur **Afficher le jeton des dépenses publicitaires**.  
   Le jeton Ad Spend s'affiche.
3. Copiez et enregistrez le jeton Ad Spend.

</Accordion>

<div id="granting-an-ad-network-import-permission" />

<Accordion title="Octroi d'une autorisation d'importation sur un réseau publicitaire">

**Pour accorder l'autorisation d'importation des coûts au réseau publicitaire, procédez comme suit :**

1. Dans AppsFlyer, l'**annonceur** doit accéder au menu latéral et sélectionner **Collaborate** > **Active Integrations.   
   À propos de la page partenaire intégré**
2. Sélectionnez le partenaire intégré.
3. Allez dans l'onglet **Autorisations**.    
    [<Image alt="PermissionAdNetwork.png" src="https://support.appsflyer.com/hc/article_attachments/360004994898" width="221px" />](https://support.appsflyer.com/hc/article_attachments/360004994898)
4. Activez **les autorisations du réseau publicitaire** si ce n'est pas déjà fait.
5. (facultatif) Ajoutez des utilisateurs au compte.
6. Activez **Autoriser l'importation des dépenses.**

</Accordion>

<div id="sending-ad-spend-files-by-email" />

<Accordion title="Envoi de fichiers de dépenses publicitaires par e-mail">

**Prérequis en matière de courrier électronique** :

* Annonceurs
  * Le jeton Ad Spend est requis.
  * L'adresse e-mail de l'expéditeur doit être celle d'un utilisateur enregistré d'AppsFlyer.
* Réseaux publicitaires  
  * Le jeton Ad Spend est requis.
  * L'adresse e-mail de l'expéditeur doit être celle d'un utilisateur enregistré d'AppsFlyer.
  * L'annonceur doit autoriser l'importation des coûts au partenaire (réseau publicitaire).

**Pour envoyer le fichier des dépenses publicitaires par e-mail** :

1. Complétez les champs d'adresse e-mail :
   * À :
   * CC : Utilisateurs qui devraient recevoir une copie du feedback automatique
   * Objet : Collez le jeton Ad Spend dans le champ objet.
   * attachment\_1292637 Fichier CSV contenant les données.
2. Envoyez l'e-mail.
   * À la fin du traitement, un e-mail de statut est envoyé qui résume le téléchargement et détaille les problèmes ou les erreurs détectés lors du traitement. L'e-mail est envoyé à toutes les parties sur l'e-mail de soumission et à l'administrateur de l'annonceur. Lorsque des erreurs sont identifiées, vous devez prendre des mesures correctives. Remarque : Si le message de statut n'a pas été reçu,  [cliquez ici.](/docs/import-cost-data#after-emailing-the-ad-spend-files-no-status-email-is-received)
   * Vous pouvez consulter l'état des fichiers soumis sur la [page d'importation des coûts](/docs/import-cost-data#ad-spend-import-actions)

</Accordion>

<div id="uploading-ad-spend-files" />

<Accordion title="Téléchargement de fichiers de dépenses publicitaires">

**Pour télécharger le fichier des dépenses publicitaires, procédez comme suit** :

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Paramètres** > Importation des **coûts.** La page d'importation des coûts s'affiche.
2. Cliquez sur **+ importer le fichier de dépenses publicitaires**La fenêtre d'importation des dépenses publicitaires s'ouvre.
3. Faites glisser le fichier CSV vers la fenêtre **d'importation du fichier de dépenses publicitaires**.  
   Le message Traitement du fichier s'affiche.
4. Si un message d'erreur s'affiche pendant le téléchargement : rectifiez l'erreur et répétez les étapes correspondantes.
5. La fenêtre **Importation des coûts : résumé du fichier** s'ouvre.

   ![AdspendInestionFileSummary.png](https://support.appsflyer.com/hc/article_attachments/360005116138)
6. Effectuez l'une des opérations suivantes :
   * Abandonnez le téléchargement, cliquez sur **Annuler l'importation**.
   * Terminez le processus d'importation, cliquez sur **Importer le fichier.**  
     Le message : « Tout est prêt ! écrans.
7. Cliquez sur **Importer un autre fichier** ou sur **OK**.

</Accordion>

## Gestion des importations de coûts

Sur la page Importation des coûts, vous pouvez effectuer les actions suivantes.

* Surveillez l'état des fichiers importés : Identifier les fichiers d'importation qui nécessitent votre attention car les données n'ont peut-être pas été importées ou ont été importées partiellement. Il se peut que vous deviez soumettre à nouveau ces fichiers.
* Surveillez l'indicateur de lignes sans correspondance : Si le pourcentage de lignes correspondantes est faible, cela peut être le symptôme d'erreurs dans les données.
* Téléchargez des copies des fichiers CSV soumis
* Rétablir (annuler) l'importation

**Autorisation de consulter les fichiers téléchargés et les rapports non correspondants :**

* Tous les utilisateurs du compte peuvent accéder à la page d'importation des dépenses publicitaires
* L'accès aux informations détaillées est réservé aux utilisateurs du compte autorisés à utiliser l'application.
* Si un fichier contient les données de plusieurs applications, l'utilisateur du compte r doit accéder à toutes les applications référencées dans le fichier.

<div id="ad-spend-import-actions" />

<Accordion title="Actions d'importation de coûts">

**Pour consulter l'état de l'importation au niveau du fichier :**

* Dans AppsFlyer, dans le menu latéral, sélectionnez **Paramètres** > Importation des **coûts.** La page Cost Import affiche la liste des fichiers chargés. [![](https://support.appsflyer.com/hc/article_attachments/360005029737)](https://support.appsflyer.com/hc/article_attachments/360005029737)
* Si vous êtes autorisé à accéder à toutes les applications contenues dans le fichier, utilisez la commande **Action** pour :  
  * Télécharger le fichier CSV Il s'agit d'une copie du fichier CSV qui a été chargé.
  * **Téléchargez un rapport inégalé** pour toutes les applications du fichier.

**Pour consulter l'état de l'importation au niveau de l'application, procédez comme suit :**

* Sélectionnez le fichier.  
  La page au niveau de l'application s'affiche. La liste des applications figurant dans le fichier des dépenses publicitaires s'affiche.

  ![Adspendimports2.png](https://support.appsflyer.com/hc/article_attachments/360005029797)
* Effectuez des actions au niveau du fichier ou de l'application comme décrit ici.
* **Au niveau du fichier :** Si vous êtes autorisé à accéder à toutes les applications contenues dans le fichier, vous pouvez utiliser les commandes situées en haut à droite de la page pour :
  * **Annulez** (annulez) l'importation des coûts pour toutes les applications du fichier.
  * **Téléchargez** une copie du fichier CSV qui a été envoyé.
* Au niveau de l'application Si vous êtes autorisé à accéder à une application spécifique, vous pouvez le faire à l'aide de la commande **Action** :
  * Télécharger les données de l'app
  * **Téléchargez un rapport inégalé** pour l'application
  * **Annulez** (annulez) l'importation des coûts pour l'application sélectionnée.

</Accordion>

<div id="status-indicators" />

<Accordion title="Indicateurs d'état">

| Statut | Remarques |
| --- | --- |
| Appliqué | L'action s'est terminée avec succès |
| Rétabli | L'action s'est terminée avec succès |
| Erreur de traitement des données | Problème système AppsFlyer. Patientez 10 minutes et réessayez. S'il échoue à nouveau, contactez le support d'AppsFlyer. |
| Aucune autorisation | Le jeton n'est pas approuvé pour cette application.<ul><li>Annonceurs : vérifiez que l'identifiant de l'application est correct.</li><li>Partenaire : vérifiez auprès de l'annonceur qu'il a activé l'option **Autoriser l'importation des dépenses** dans l'onglet **Autorisations** de l'intégration.</li></ul> |
| Erreur de validation |  |

</Accordion>

<div id="row-matching-and-the-unmatched-report" />

<Accordion title="Correspondance des lignes et rapport non apparié">

La correspondance des lignes est le processus par lequel le mécanisme d'importation associe les lignes de dépenses publicitaires signalées par importation aux données d'attribution enregistrées dans le tableau de bord. Cela se fait en utilisant toutes les dimensions disponibles dans le schéma du fichier, telles que la source multimédia, la campagne, l'ensemble publicitaire, la publicité, etc. Si elles correspondent toutes, les lignes sont désignées comme IS-Matching=True.

#### Noms et pièces d'identité

Cost Import identifie une dimension, telle qu'une campagne, un ensemble de publicités ou une annonce par son nom, sans son identifiant. Actuellement, Cost Import ne prend pas en charge les rapports de dépenses utilisant uniquement des identifiants.

**Remarque** : Quel que soit le statut de correspondance, les dépenses sont enregistrées.

> 📄 **Exemple : Lignes correspondantes et non appariées**
>
> | Date | Source média | Campagne | Impressions | Clics | Coût | État correspondant |
> | --- | --- | --- | --- | --- | --- | --- |
> | 2019-01-01 | Exemple | abc | 5000 | 100 | 25/01/1000 | est correspondant = VRAI  <br />Informations sur les performances trouvées |
> | 2019-01-02 | Exemple | abc |  |  |  | correspond = FAUX  <br />Aucune information sur les performances le 02/01/2019 |
> | 2019-01-02 | Exemple | influenceur |  |  | 25/01/2500 | correspond = FAUX  <br />Aucune information sur les performances le 02/01/2019 |

Le pourcentage de lignes correspondantes s'affiche sur la page d'importation.

Si des lignes sans correspondance sont inattendues, téléchargez le [rapport sans correspondance](/docs/import-cost-data#ad-spend-import-actions) pour en rechercher la cause. Si nécessaire, annulez l'importation en l'annulant.

Le rapport Unmatched contient une colonne, is matching, qui peut avoir une valeur de lignes TRUE (correspondant) ou FALSE (non apparié).

**Page d'importation des coûts affichant le pourcentage de lignes correspondantes**

![Adpsendmatching.png](https://support.appsflyer.com/hc/article_attachments/360004979278)

</Accordion>

<div id="overwrite-correct-previously-imported-ad-spend" />

<Accordion title="Remplacer (corriger) les dépenses publicitaires précédemment importées">

Les dépenses publicitaires importées précédemment peuvent être remplacées à l'aide de fichiers CSV contenant des données dont la clé est identique à celle des données précédemment importées.

La clé est formée à partir de la date, de la source multimédia et des champs de campagne. Si les clés correspondent, les données importées en dernier remplacent les données précédemment importées.

Les exemples suivants illustrent le remplacement des dépenses publicitaires.

> 📄 **Exemple : Remplacer les dépenses publicitaires**
>
> + indique les champs obligatoires
>
> #### Exemple A
>
> Spend1.csv importé le lundi
>
>
>
> | date | app\_id | Source média | Campagne | Dépense |
> | --- | --- | --- | --- | --- |
> | 2019-06-01 | com.my.app | network\_x | campaign\_a | 100 |
>
>
>
> Spend2.csv importé le mardi
>
>
>
> <table><tbody><tr><th>date</th><th>app_id</th><th>Source média</th><th>Campagne</th><th>Dépense</th></tr><tr><td>2019-06-01</td><td>com.my.app</td><td>network_x</td><td>campaign_a</td><td>200</td></tr><tr><td colspan="5">Les données de dépenses du fichier spend1.csv ont été remplacées par celles du fichier spend2.csv. Cela est dû au fait que spend2.csv a été importé en dernier et que les champs obligatoires qui constituent la clé sont les mêmes. </td></tr></tbody></table>
>
>
>
> #### Exemple B
>
> Spend3.csv importé le lundi
>
>
>
> | date | app\_id | Source média | Campagne | Dépense | Géo |
> | --- | --- | --- | --- | --- | --- |
> | 2019-05-01 | com.my.app | network\_x | campaign\_a | 100 | États-Unis |
> | 2019-05-01 | com.my.app | network\_x | campaign\_a | 200 | CN |
>
>
>
> Spend4.csv importé le mardi
>
>
>
> <table><tbody><tr><th>date</th><th>app_id</th><th>Source média</th><th>Campagne</th><th>Dépense</th></tr><tr><td>2019-05-01</td><td>com.my.app</td><td>network_x</td><td>campaign_a</td><td>50</td></tr><tr><td colspan="5">Les données de dépenses du fichier spend3.csv ont été remplacées par celles du fichier spend4.csv. Cela est dû au fait que spend4.csv a été importé en dernier et que les champs obligatoires qui constituent la clé sont les mêmes. <strong>Remarque</strong> : Les deux lignes du fichier spend3.csv sont remplacées. </td></tr></tbody></table>

</Accordion>

## Dépannage

<div id="error-messages-and-solutions" />

<Accordion title="Messages d'erreur et solutions">

Le tableau suivant répertorie tous les messages d'erreur possibles liés à l'importation des coûts et les solutions correspondantes.

| Message d'erreur | Description | SOLUTION |
| --- | --- | --- |
| Aucun des identifiants d'application fournis dans le fichier n'existe dans AppsFlyer. Vérifiez l'exactitude des identifiants de l'application. | L'identifiant de l'application n'existe pas dans le compte. | Modifiez l'identifiant de l'application et soumettez-la à nouveau. |
| La ligne [nom de la ligne] ne contient pas le bon nombre de colonnes. [nombre] colonnes attendues, [nombre] colonnes reçues. | Toutes les colonnes du fichier doivent avoir une valeur. | Modifiez les valeurs renseignées dans le fichier en fonction des en-têtes que vous avez définis. |
| « Source du média » manquante dans l'en-tête du fichier. | <ul><li>L'en-tête du fichier ne contient pas de source multimédia.</li><li>Le nom de la colonne doit être exactement tel qu'il figure dans le schéma.</li></ul> | Ajoutez media-source comme nom d'en-tête. |
| Le fichier ne peut contenir qu'une seule source multimédia. Plusieurs sources multimédia rencontrées dans le fichier : [nombre de sources multimédia]. | Impossible de télécharger un fichier contenant plus d'une source multimédia. | Divisez le téléchargement en un seul fichier pour chaque source multimédia. |
| La valeur fournie [valeur] pour [champ] n'est pas une valeur valide pour cette colonne. | Le format des données dans la colonne est incorrect. Par exemple, la date est jj-mm-aa au lieu de aaaa-mm-dd. | Corrigez le format et soumettez-le de nouveau. |
| Plusieurs devises ont été identifiées pour l'application. Veuillez utiliser une devise unique pour chaque application du fichier. Devises rencontrées : %nombre de devises%. | Une seule devise peut être utilisée pour une application. | Utilisez une devise lors du téléchargement et soumettez-le à nouveau. |
| Les colonnes suivantes de l'en-tête de fichier ne sont pas prises en charge : [en-têtes de fichier] | L'en-tête du fichier ne correspond pas au schéma. Cela signifie que le nom de la colonne doit être exactement tel qu'il est dans le schéma. | Supprimez les colonnes non prises en charge et soumettez-les à nouveau. |
| Colonnes obligatoires manquantes dans l'en-tête du fichier : [en-têtes de fichier] | Il manque une colonne obligatoire dans l'en-tête du fichier. | Ajoutez la colonne manquante et ses valeurs, puis soumettez-la de nouveau. |
| L'application contient une date future : [date] | Les dates futures ne sont pas autorisées. | Corrigez la date à la date d'aujourd'hui ou à une date antérieure, puis soumettez-la de nouveau. |
| Le fichier est vide. Il n'y a aucune donnée à traiter. | Le fichier est vide. | Renseignez les données dans le fichier et soumettez-les de nouveau. |
| Les deux lignes suivantes sont en conflit en raison de dimensions identiques. Veuillez fournir une seule ligne de dépenses par ensemble de dimensions. [lignes contradictoires] | Il existe plusieurs lignes contenant les mêmes champs clés (obligatoires). | Supprimez les lignes dupliquées et soumettez-les de nouveau. |
| Le fichier ne peut contenir que des données provenant d'un seul compte annonceur. Différents annonceurs rencontrés dans le fichier : [noms des annonceurs] | Pour les partenaires, une mise en ligne ne peut pas concerner plus d'un annonceur. | Divisez le téléchargement en un seul fichier par annonceur. |
| L'application [ID de l'application] n'existe pas dans le compte. Vérifiez l'identifiant de l'application. | L'identifiant de l'application n'existe pas. | Corrigez l'ID de l'application et soumettez-la à nouveau. |
| Le code géographique (pays) n'a pas été trouvé pour l'application [ID de l'application]. Utilisez un code à 2 lettres ISO 3166 | Geo n'existe pas. | Corrigez la géolocalisation et soumettez-la de nouveau. |
| Le code de devise n'a pas été trouvé pour l'application [ID de l'application]. Utilisez un code à 3 lettres ISO 4217. | La devise n'existe pas | Remplacez la devise par une devise valide et soumettez-la à nouveau. |
| Des erreurs de validation se sont produites pour une ou plusieurs applications du fichier. Veuillez consulter les informations du fichier pour plus de détails. | Le fichier contient plusieurs erreurs. | Téléchargez le fichier et vérifiez s'il n'y a pas d'erreurs. |
| Une erreur interne s'est produite lors du traitement du fichier, veuillez réessayer de le charger. | <ul><li>Problème de backend lors du traitement du fichier.</li><li>Il s'agit généralement d'un problème temporaire.</li></ul> | Patientez 1 heure, puis chargez à nouveau. |

</Accordion>

<div id="imported-cost-data-does-not-display-or-displays-in-a-separate-row" />

<Accordion title="les données de coûts importées ne s'affichent pas ou s'affichent dans une ligne séparée">

Symptôme  Les données de coûts ne s'affichent pas après une importation réussie

1. Dans le tableau de bord, vérifiez si le nom de la campagne s'affiche plusieurs fois.
2. Si c'est le cas, localisez la ligne où l'identifiant de campagne est vide.  
   La ligne contenant l'identifiant de campagne vide contient le coût.

Symptôme  Le coût importé s'affiche dans une ligne distincte (ligne supplémentaire) sans les données **de performance (installations).** L'identifiant de campagne sur la ligne est vide.

Cause Lorsque l'identifiant et le nom de la campagne figurent à la fois dans les données d'attribution, le fichier CSV doit contenir les deux pour qu'AppsFlyer corresponde correctement aux données de coûts et évite des rubriques distinctes.

</Accordion>

<div id="using-excel-to-format-date-and-spend-fields-of-csv-files" />

<Accordion title="Utilisation d'Excel pour mettre en forme les champs de date et de dépenses des fichiers CSV">

Lorsque vous utilisez Excel/Google Sheets pour créer un fichier CSV, les colonnes de date et de dépenses doivent être correctement mises en forme avant d'enregistrer le fichier au format CSV. Utilisez les procédures suivantes pour mettre en forme correctement les champs de date et de dépenses.

Après avoir enregistré le fichier CSV, vérifiez que le contenu est correctement formaté. **Remarque** : N'utilisez pas Excel pour effectuer la vérification, utilisez plutôt un [éditeur](/docs/import-cost-data#visual-inspection-of-the-csv-file-without-excel).

#### Formatage des cellules de date dans Excel

**Pour mettre en forme des cellules de date dans Excel au format YYYY-MM-DD** :

1. Sélectionnez les cellules à mettre en forme.
2. Cliquez avec le bouton droit, sélectionnez **Formater les cellules**.  
   La fenêtre Formater les cellules s'ouvre.  

   <Image alt="Formatdate..png" src="https://files.readme.io/43d0f370f299d73b8ce93fec1c912cb7525d0071db779a64a58f5917df2a5531-360004042458.png" width="379px" />
3. Sélectionnez **Personnalisé**.
4. Dans le champ Type, saisissez **YYYY-MM-DD**
5. Cliquez sur **OK**.  
   La date est formatée.

#### Formatage des cellules de dépenses dans Excel

Excel met généralement en forme les cellules de valeur par une virgule pour séparer les milliers, comme indiqué dans la figure. Ce format n'est pas adapté aux fichiers d'importation d'Ad Spend.

<Image alt="mceclip1.png" src="https://files.readme.io/d54e21ddd937dfe25a33bb96193761a5a724c22a35a55bb7d71eb03a6433d7ed-360003949177.png" width="291px" />

Vous pouvez corriger cela en formatant les cellules dans Excel.

**Pour formater les montants des dépenses sans séparateur de 1 000, procédez comme suit** :

1. Sélectionnez les cellules à mettre en forme.
2. Cliquez avec le bouton droit, sélectionnez **Formater les cellules**.  
   La fenêtre Formater les cellules s'ouvre.
3. Sélectionnez **Numéro**.  

   <Image alt="Formatnumbers.png" src="https://files.readme.io/d2bfeec87d24739e9d1cea8467d7ce23b56aa9414a96202379f6e774991bf387-360004075458.png" width="381px" />

1. **Décochez Utiliser le séparateur 1000 (,).**
2. (Facultatif) Définissez le nombre de **décimales**. La valeur par défaut est 2. Le maximum autorisé est de 5.
3. Cliquez sur **OK**.  
   Les cellules sont correctement mises en forme.

</Accordion>

<div id="visual-inspection-of-the-csv-file-without-excel" />

<Accordion title="Inspection visuelle du fichier CSV sans Excel">

Pour examiner le contenu du fichier CSV, utilisez un éditeur pour afficher le fichier.

* Windows Bloc-notes, Bloc-notes ++
* MacOS TextEdit

Ce qui suit contient une capture d'écran de l'[exemple de fichier CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv) affiché dans un éditeur.

**Vue de l'éditeur**

<Image alt="mceclip1.png" src="https://files.readme.io/1398c5e9bad7a46b697e3b21030e64d656162e33a4a63f39475c64993bbe7a72-360003996197.png" width="672px" />

À l'aide d'un éditeur, examinez le fichier CSV. Portez une attention particulière aux points suivants :

* **Espaces vides :** Assurez-vous qu'il n'y a aucun espace vide en début ou en fin de champ avant ou après les virgules qui séparent les champs. Dans Excel, utilisez la commande @trim pour supprimer les espaces vides.
* **Date :** Assurez-vous que le champ de date est au format YYYY-MM-DD.
* Dépense Assurez-vous qu'il n'y a pas de virgule dans le champ des dépenses.  

  <Image alt="mceclip1.png" src="https://files.readme.io/d54e21ddd937dfe25a33bb96193761a5a724c22a35a55bb7d71eb03a6433d7ed-360003949177.png" width="150px" />

</Accordion>

<div id="csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

<Accordion title="Les fichiers CSV générés par Excel n'ont pas de virgules comme délimiteurs">

Si Excel crée un fichier CSV avec un point-virgule « ; » ou un autre caractère comme séparateur mais pas une virgule :

* Cela se produit lorsque les paramètres régionaux de votre ordinateur sont définis sur une langue/région autre que l'anglais.
* Ce problème est particulièrement fréquent lorsque l'allemand est sélectionné dans les paramètres régionaux.
* La solution varie en fonction du système d'exploitation de votre ordinateur (macOS ou Windows).
* Pour résoudre ce problème, recherchez les derniers conseils de <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> ou d'autres forums dédiés à Revolve. Utilisez les termes de recherche suivants : Système d'exploitation (macOS ou Windows) Excel modifie le délimiteur pour les fichiers CSV.

</Accordion>

<div id="after-emailing-the-ad-spend-files-no-status-email-is-received" />

<Accordion title="Après l'envoi par e-mail des fichiers de dépenses publicitaires, aucun e-mail de statut n'est reçu">

Cela signifie probablement que le fichier des dépenses publicitaires n'a pas été traité. Cela peut se produire pour diverses raisons :

#### Type de contenu incorrect

AppsFlyer traite uniquement les messages dont le type de contenu est `multipart/mixed` défini. Les autres types ne sont pas traités et, par conséquent, aucun e-mail de statut n'est généré et renvoyé. Dans le cas normal, les e-mails avec pièce jointe sont automatiquement configurés `multipart/mixed` par le client de messagerie.

Pour vous assurer que le type de contenu du message électronique est bien défini, `multipart/mixed` consultez la valeur du type de contenu dans l'en-tête de l'e-mail.

* Pour afficher l'en-tête du message électronique dans Gmail, consultez <Anchor target="_blank" href="https://support.google.com/mail/answer/29436?hl=en#zippy=%2Cgmail">la documentation Gmail</Anchor>.
* Pour afficher l'en-tête du message électronique dans Outlook, consultez <Anchor target="_blank" href="https://support.microsoft.com/en-us/office/view-internet-message-headers-in-outlook-cd039382-dc6e-4264-ac74-c048563d212c">la documentation Outlook</Anchor>.

#### Le code HTML du message électronique n'est pas correctement formaté

Les erreurs HTML peuvent empêcher le traitement correct de l'e-mail. Par exemple, la balise est vide ou manquante. Vérifiez que votre script ne contient pas d'erreurs HTML.

</Accordion>

## Informations supplémentaires

<div id="preparing-a-csv-with-agency-data" />

<Accordion title="Préparation d'un fichier CSV avec les données de l'agence">

Les annonceurs et les agences peuvent préparer des fichiers CSV pour télécharger et importer des données sur les coûts. Pour ce faire, les fichiers CSV doivent contenir une colonne Agence avec le nom de l'agence (le nom de l'agence est la valeur du paramètre af\_prt). [Voir le schéma CSV](/docs/import-cost-data#schéma-csv-des-dépenses-publicitaires)

N'oubliez pas :

* Une seule agence peut être incluse dans un dossier. Et seules les campagnes gérées par cette agence peuvent être incluses dans le fichier.
* Le nom de l'agence est obligatoire par ligne. Aucune cellule vide n'est autorisée dans la colonne de l'agence.
* L'agence doit être autorisée à accéder à toutes les applications incluses dans le fichier.
* Seuls les annonceurs peuvent télécharger le fichier. Les agences ne peuvent pas télécharger de données. Ils peuvent préparer leurs fichiers et les envoyer à l'annonceur pour qu'il les télécharge.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Supports d'importation des coûts | Remarques |
| --- | --- | --- |
| Réseaux publicitaires | ✓ |  |
| Agences | ✓ | Les agences ne peuvent pas télécharger de données. Ils peuvent préparer leurs fichiers et les envoyer à l'annonceur pour qu'il les télécharge. |
| Transparence de l'agence | **x** |  |
| Fuseau horaire spécifique à l'app | ✓ |  |
| Devise spécifique à l'app | ✓ | Les coûts des campagnes sont convertis dans la devise spécifique à l'application. |
| Nom de la campagne | N/A | Le même nom de campagne ne peut pas être utilisé pour plusieurs applications, sinon le coût d'une seule application s'appliquera aux deux. |
| Noms des champs | N/A | Si les noms des champs dans la hiérarchie des campagnes ne correspondent pas aux noms des champs tels qu'ils apparaissent dans les données d'attribution, ils seront comptabilisés séparément. <br /><br />Par exemple, si les noms des campagnes ne correspondent pas, même si les identifiants de campagne sont identiques, elles seront considérées comme des campagnes différentes. |
| Taille du fichier | N/A | Lorsque vous chargez un fichier d'importation des coûts au format CSV, la taille limite est la suivante :<ul><li>Via le tableau de bord AppsFlyer : (2 MO)</li><li>Par e-mail : (5 MO)</li></ul> |
| Données organiques | ✓ |  |
| Données non organiques | ✓ |  |
| Actualisation des données | <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#ad-revenue">dépenses publicitaires</Anchor> |  |
| Données historiques | ✓ | Les coûts déclarés peuvent être annulés et les données corrigées peuvent être soumises pendant 90 jours. |
| Retargeting | **x** |  |
| Accès utilisateur du compte | ✓ | Non disponible pour les utilisateurs soumis à des restrictions liées à la géolocalisation ou à la source multimédia. |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/partners/fr/docs/cost-import-for-ad-networks">Importation des coûts pour les réseaux publicitaires</Anchor>

<div data-zendesk-anchors="ad-spend-import=importation-des-co%C3%BBts 01H7VYHJ2BN3EFDC4J3YN3P4WM=importation-des-co%C3%BBts full-campaign-cost-data=donn%C3%A9es-compl%C3%A8tes-sur-les-co%C3%BBts-des-campagnes 01H7VYHJ2B8176E3PSXCTD3XB4=donn%C3%A9es-compl%C3%A8tes-sur-les-co%C3%BBts-des-campagnes preparing-uploading-and-importing-ad-spend-files=pr%C3%A9paration-t%C3%A9l%C3%A9chargement-et-importation-de-fichiers-de-d%C3%A9penses-publicitaires 01H7VYHJ2CW152JZW55VX6CPRC=pr%C3%A9paration-t%C3%A9l%C3%A9chargement-et-importation-de-fichiers-de-d%C3%A9penses-publicitaires upload-workflows=workflows-de-t%C3%A9l%C3%A9chargement 01H7VYHJ2C4Y8APWKP8H5QASQG=workflows-de-t%C3%A9l%C3%A9chargement workflow-upload-file-in-the-user-interface=flux-de-travail-t%C3%A9l%C3%A9charger-le-fichier-dans-linterface-utilisateur 01H7VYHJ2CRT6DBH5XS1FTQZYY=flux-de-travail-t%C3%A9l%C3%A9charger-le-fichier-dans-linterface-utilisateur workflow-upload-file-by-email=flux-de-travail-t%C3%A9l%C3%A9charger-le-fichier-par-e-mail 01H7VYHJ2CD5142SAZ2QPF32ZY=flux-de-travail-t%C3%A9l%C3%A9charger-le-fichier-par-e-mail procedures=proc%C3%A9dures 01H7VYHJ2CFMP3FEAFWMHG1HA1=proc%C3%A9dures 01H7VYHJ2CW7M5VX6REXNANSEH=csv-file-format-and-schema 01H7VYHJ2CTCT652G0AEKXJKM5=remarque content-rules-and-schema-of-ad-spend-csv-files=r%C3%A8gles-de-contenu-et-sch%C3%A9ma-des-fichiers-csv-relatifs-aux-d%C3%A9penses-publicitaires 01H7VYHJ2CND8ZE42A4MSTWCKJ=r%C3%A8gles-de-contenu-et-sch%C3%A9ma-des-fichiers-csv-relatifs-aux-d%C3%A9penses-publicitaires ad-spend-csv-schema=sch%C3%A9ma-csv-des-d%C3%A9penses-publicitaires 01H7VYHJ2CWF2HWHCTZDEZHT29=sch%C3%A9ma-csv-des-d%C3%A9penses-publicitaires 01H7VYHJ2CW6Z94N2ZX320P6E3=getting-an-ad-spend-token 01H7VYHJ2CTSS6WCPJBEFNNQCK=attention- 01H7VYHJ2CT2DMTGEP4MXTCER3=granting-an-ad-network-import-permission 01H7VYHJ2CEEVQH6ZKQAHE924A=sending-ad-spend-files-by-email 01H7VYHJ2CPHZQTG26289JH24B=uploading-ad-spend-files managing-ad-spend-imports=gestion-des-importations-de-co%C3%BBts 01H7VYHJ2DXQTFV3P0FJD40D41=gestion-des-importations-de-co%C3%BBts 01H7VYHJ2DC6HYNJ9W2WPR8KCH=ad-spend-import-actions 01H7VYHJ2DFEMD429F7QYHMS4M=status-indicators 01H7VYHJ2DWGSWWRPMCG1KCEX5=row-matching-and-the-unmatched-report names-vs-ids=noms-et-pi%C3%A8ces-didentit%C3%A9 01H7VYHJ2D9CZMZMY6J8Z2N7CG=noms-et-pi%C3%A8ces-didentit%C3%A9 01H7VYHJ2D1GPD5Y0QGTADXGMS=exemple--lignes-correspondantes-et-non-appari%C3%A9es 01H7VYHJ2DKFERS1674ZR7BR8H=overwrite-correct-previously-imported-ad-spend 01H7VYHJ2DAZRM8HGFQCFBKRYZ=exemple--remplacer-les-d%C3%A9penses-publicitaires example-a=exemple-a 01H7VYHJ2D4FRA4MCDABAKYDS8=exemple-a example-b=exemple-b 01H7VYHJ2DTX7GHPRGZYA16PGX=exemple-b troubleshooting=d%C3%A9pannage 01H7VYHJ2DGB0M01ZAWP4SCFF4=d%C3%A9pannage 01H7VYHJ2D1C10NBAXTFDRAVF4=error-messages-and-solutions 01H7VYHJ2DGH32HBSVF5XQAVC0=imported-cost-data-does-not-display-or-displays-in-a-separate-row 01H7VYHJ2D6C26HTRP7KWF6136=using-excel-to-format-date-and-spend-fields-of-csv-files formatting-date-cells-in-excel=formatage-des-cellules-de-date-dans-excel 01H7VYHJ2DSWC2J1NY04Q9Q620=formatage-des-cellules-de-date-dans-excel formatting-spend-cells-in-excel=formatage-des-cellules-de-d%C3%A9penses-dans-excel 01H7VYHJ2DA9JM4Q33V2TF7BD3=formatage-des-cellules-de-d%C3%A9penses-dans-excel 01H7VYHJ2DG01EF165K5C6NDD5=visual-inspection-of-the-csv-file-without-excel 01H7VYHJ2DXJGANNBTNK3EF1XB=csv-files-generated-by-excel-dont-have-commas-as-delimiters 01H7VYHJ2DDR5PPFJ402GZGNT8=after-emailing-the-ad-spend-files-no-status-email-is-received wrong-contenttype=type-de-contenu-incorrect 01H7VYHJ2DXECF8W20ZPFCJNWH=type-de-contenu-incorrect the-email-message-html-is-not-properly-formatted=le-code-html-du-message-%C3%A9lectronique-nest-pas-correctement-format%C3%A9 01H7VYHJ2D8MTJ6ZBMQ26GT6GF=le-code-html-du-message-%C3%A9lectronique-nest-pas-correctement-format%C3%A9 additional-information=informations-suppl%C3%A9mentaires 01H7VZGXDDE64TKB59VXFJ42N6=informations-suppl%C3%A9mentaires 01H7VYHJ2D40E91CJS0PC3VPWC=preparing-a-csv-with-agency-data h_01HE7TC49KRRX1RVGX1FY7C52T=%C3%A0-consulter-%C3%A9galement" />

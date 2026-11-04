---
title: Décodage de la VC SKAN (associez votre VC aux événements)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-26T20:31:40Z'
  edited_at: '2024-08-28T14:43:35Z'
  id: 360014696297
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/360014696297
---
> **En bref :** AppsFlyer décode et transforme la valeur de conversion que vous avez définie en événements. Les événements sont utilisés pour remplir le tableau de bord SKAN, les données brutes et les postbacks pour les partenaires.

![SKAdNetwork_-_Custom__1_.png](https://files.readme.io/74f0d3836ee6a73f6746afa2d6d6a468c09cba696561c5a2075149ca360b78bf-34255690318097.png)

<div id="decode-skan-conversion-value" />

## Décoder la valeur de conversion SKAN

Les annonceurs utilisent le décodage de la valeur de conversion comme alternative aux options disponibles dans <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">Conversion Studio</Anchor>. Si vous utilisez Decode, cela signifie que vous êtes responsable de la définition <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/4097267-updatepostbackconversionvalue">de updatePostbackConversionValue</Anchor> en fonction de la logique de votre app.

Outre la définition de la valeur de conversion (VC) dans l'app, le reste du flux, les fonctionnalités et les options de rapport sont les mêmes que ceux décrits dans le <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">guide de solution SKAN</Anchor>. Cela signifie qu'à l'expiration de la fenêtre d'activité (contrôlée par vous), iOS envoie le postback au réseau publicitaire, qui le transmet à AppsFlyer. AppsFlyer décode la VC en fonction de votre mappage dans des événements traités comme les VC décodées définies par le SDK.

<div id="custom-conversion-valuedecode" />

## Valeur de conversion personnalisée — Décoder

La mise en œuvre du décodage de VC personnalisé nécessite le téléchargement d'un fichier CSV contenant votre mappage de VC sur la plateforme AppsFlyer.

**Principes de cartographie du décodage**

* Fournit un mappage de décodage pour les valeurs de conversion précises (1 à 63) et les valeurs de conversion grossières (faible, moyenne et élevée) pour les fenêtres 1 à 3. Il n’est pas obligatoire de mapper toute la plage de valeurs. Par exemple, vous pouvez mapper les valeurs 1, 2, 10 et 43.
* La VC 0 est toujours mappée sur l'installation. Vous ne pouvez pas la régler.
* La table de mappage est téléchargée sur AppsFlyer dans un fichier CSV. Vous pouvez télécharger une table de mappage mise à jour selon vos besoins.
* Lors de la réception d'un postback d'iOS, la VC est décodée en événements, tel qu’illustré dans les exemples.
* L'heure d'installation est dérivée à l'aide de l'heure d'arrivée du postback.
* Les événements ont la même durée que le temps d'installation.
* Pour mieux comprendre comment préparer le schéma, examinez les scénarios de mappage qui suivent.
* Les noms <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">d'événements personnalisés dans l'app</Anchor> sont autorisés.
  * Cela signifie que vous envoyez de nouveaux noms d'événements, même s'ils n'ont jamais été envoyés par le SDK.
  * Vous pouvez mapper les événements in-app aux événements intégrés au réseau publicitaire.
  * Ceci est également vrai pour l'intégration des annonces Meta, sous réserve des règles spécifiques à Meta détaillées dans la section suivante.

<div id="decode-mapping-scenario-rules" />

<Accordion title="Décoder les règles du scénario de cartographie">

N'oubliez pas :

* Plage de valeurs de conversion précise : 1-63
* Plage de valeurs de conversion grossière : Faible, moyen et élevé
* Une valeur de conversion donnée correspond à un ou plusieurs événements in-app que vous avez spécifiés. Les événements in-app ont des paramètres facultatifs.
* Pour les exemples : Supposons que la date d'installation soit le 1er février à 08h00.
* Le tableau suivant est un exemple de table de mappage de décodage. Sa structure est similaire à celle du fichier CSV requis. Le tableau suivant présente les événements générés à la suite du processus de décodage.
* Un événement d'installation est toujours généré, quel que soit votre mappage.
* Mesure des revenus :
  * Les revenus sont en USD.
  * Une valeur de conversion donnée a une plage de revenus délimitée par min\_revenue et max\_revenue.
  * Dans les rapports et tableaux de bord agrégés, les revenus sont calculés comme la moyenne de la plage. Exemple : min\_revenue=4 et max\_revenue=10. Le revenu calculé est de 7.
  * Les rapports de données brutes incluent les revenus calculés (skad\_revenue), min\_revenue et max\_revenue.

<div id="meta-specific-rules" />

#### **Règles méta-spécifiques**

Si vous intégrez des annonces Meta, respectez les règles suivantes :

* Les valeurs de revenus minimales et maximales pour une valeur de conversion donnée doivent être différentes. Signifie pas égal.
* Les valeurs ne doivent pas se chevaucher et doivent être dans un ordre consécutif comme illustré pour conversion\_value 1-2 et 62 dans le tableau suivant.
* event\_counter : Les méta-annonces ne prennent pas en compte cette valeur. [Bonne pratique] Renseignez-la avec une valeur de 1.

<div id="example-decode-mapping" />

### Ex. : Cartographie de décodage

| conversion\_  <br />valeur | event\_  <br />name | event\_  <br />valeur | min\_revenue<br /><br />(non inclusif) | max\_revenue (inclusif) | event\_  <br />compteur | hours\_from\_  <br />install |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | af\_purchase | `{abc}` | 0 | 3 | 1 | 24 |
| 2 | af\_purchase | `{def}` | 3 | 10 | 3 | 36 |
| 21 | event\_a |  |  |  | 1 | 24 |
| 21 | event\_b |  |  |  | 3 | 24 |
| 21 | event\_c | `{xyz}` |  |  | 2 | 24 |
| 21 | event\_d |  |  |  | 1 | 24 |
| 21 | event\_e |  |  |  | 1 | 24 |
| 21 | event\_f |  |  |  | 1 | 24 |
| 21 | event\_g |  |  |  | 1 | 24 |
| 62 | af\_purchase | \{fgh) | 10 | 17 | 2 | 72 |
| 62 | event\_a | `{klm}` |  |  | 3 | 72 |

<div id="example-a-fine-conversion-value-1" />

### Exemple A : Valeur de conversion précise 1

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 1,5 | 0 | 3 | `{abc}` |

<div id="example-b-fine-conversion-value-2" />

### Exemple B  : Valeur de conversion précise 2

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 6,5 | 3 | 10 | `{def}` |
| af\_purchase | 6,5 | 3 | 10 | `{def}` |
| af\_purchase | 6,5 | 3 | 10 | `{def}` |

<div id="example-c-fine-conversion-value-21" />

### Exemple C : Valeur de conversion précise 21

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| event\_a |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_c |  |  |  | `{xyz}` |
| event\_c |  |  |  | `{xyz}` |
| event\_d |  |  |  |  |
| event\_e |  |  |  |  |
| event\_f |  |  |  |  |
| event\_g |  |  |  |  |

<div id="ssot-support-for-decode-mode" />

<div id="faq" />

<div id="how-to-enable-ssot-for-decode-mode" />

<div id="key-benefits" />

<div id="overview" />

<div id="example-d-fine-conversion-value-62" />

### Exemple D : Valeur de conversion précise 62

| event\_name | skad\_revenue | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| install |  |  |  |  |
| af\_purchase | 13.5 | 10 | 17 | `{fgh}` |
| af\_purchase | 13.5 | 10 | 17 | `{fgh}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |

</Accordion>

<div id="zd-decode-csv-file-specification" />

<div id="decode-csv-file-specification" />

<Accordion title="Décoder les spécifications du fichier csv">

Les valeurs de conversion sont mappées à un ou plusieurs événements in-app.

**Règles de fichier**

* Format : Fichier CSV
* Nombre maximal de lignes : 640 + ligne d'en-tête ; total 641.
* La ligne d'en-tête  <mark>doit inclure tous les noms de colonnes exactement tels qu'ils s'affichent ici.</mark> Recommandation : utilisez le fichier d’exemple ci-joint comme modèle. Voir des exemples de fichiers CSV décodés pour <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=0&single=true&output=csv">SKAN 3</Anchor> et <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=1187444449&single=true&output=csv">SKAN 4</Anchor>.
* N'utilisez pas les caractères suivants comme premier caractère d'une colonne :`=`,`+`,`-`, et`@` (édité).

### Décoder les spécifications du fichier csv

| Colonne | Valeur obligatoire | Contenu | Détails |
| --- | --- | --- | --- |
| conversion\_value | Oui, pour :<ul><li>SKAN 3 et moins</li><li>SKAN 4 où postback\_sequence\_index est 0</li></ul> | Valeur entière 1–63 | La même valeur de conversion précise peut être répertoriée plusieurs fois. Voir les exemples pour plus d'explications. |
| coarse\_conversion\_value | Uniquement valable pour SKAN 4 | Chaîne :<ul><li>faible</li><li>moyen</li><li>haut</li></ul> | La même valeur de conversion grossière peut être répertoriée plusieurs fois. |
| event\_name | Oui | Chaîne | Évènement in-app. Il n’est pas nécessaire que l’événement existe déjà dans AppsFlyer.<br /><br />Attention ! Les noms des événements in-app sont <mark>sensibles à la casse.</mark><br /><br />[Recommandation] : Nom de l'événement pour les revenus af\_skad\_revenue. |
| event\_value | Non | Chaîne | Chaîne définie par le développeur contenant les données à décoder par l'annonceur dans ses systèmes. Il s'agit généralement d'un format JSON. |
| min\_revenue | Non | Entier ou flottant | Utilisez min\_revenue et max\_revenue pour définir une plage de revenus en USD.<ul><li>Si vous ne souhaitez pas associer les revenus à une valeur de conversion, définissez min\_revenue et max\_revenue sur vide.</li><li>La valeur définie dans min\_revenue n'est pas inclusive. Signifiant supérieur à 0. Similaire à 0,0001</li><li>La valeur définie dans max\_value est inclusive.</li><li>Ex. : Si min\_revenue est 0 et max\_revenue est 4, cela signifie que la plage est de 0,0001 à 4</li><li>max\_revenue doit être supérieur à min\_revenue</li></ul>**Attention !** Si vous générez le fichier à l'aide d'Excel, avant de l'enregistrer, modifiez le format de colonne en virgule et non en devise pour éviter qu'Excel n'intègre un symbole $ dans le fichier CSV. |
| max\_revenue | Non |  | Si vous renseignez min\_revenue : max\_revenue doit avoir une valeur supérieure à 0.<br /><br />Voir min\_revenue pour l'explication. |
| ~~event\_revenue\_usd~~ | Non |  | Obsolète depuis le 7 juillet 2021. Utilisez min\_revenue et max\_revenue |
| event\_counter | Oui | Integer | <ul><li>Nombre de fois où l'événement est dupliqué lors du décodage. En général, il s'agit du nombre de fois que l'utilisateur a effectué une action donnée.</li><li>Valeur minimale 1.</li></ul>Ex. : si l'utilisateur a effectué un événement donné 5 fois, alors 5 événements sont générés.<br /><br />Attention : Si vous envoyez des revenus, le montant total en USD indiqué est multiplié par la valeur dans event\_counter. Cela signifie que si min\_revenue = 0, max\_revenue = 3 et event\_counter = 4, le revenu total déclaré est de 1,5 X 4 = 6.<br /><br />Voir les exemples. |
| hours\_from\_install | Oui | Integer | <ul><li>Heures écoulées depuis l'installation</li><li>Valeur minimale : 1</li><li>Valeur maximale : 1512 (63 jours)</li><li>La valeur de toutes les lignes d’un élément conversion\_value donné doit être identique. Cela signifie que des valeurs différentes pour différentes valeurs de conversion sont autorisées.</li></ul>AppsFlyer l'utilise pour dériver et définir la date d'installation comme suit :<ul><li>Si les postbacks sont SKAN V4, la formule de la date d'installation est : Date d'installation = heure d'arrivée du postback - [durée de la fenêtre accumulée] - [délai moyen du postback].<ul><li>Postback 1 : date d'installation = heure d'arrivée du postback - 48h - 36h</li></ul></li><li>Si les postbacks sont SKAN V3, la formule de la date d'installation est : Date d'installation = heure d'arrivée du postback - 36 heures - [plage moyenne de la dernière activité].<ul><li>La valeur par défaut [moyenne de la dernière plage active] est de 12 heures.</li><li>Pour une valeur de conversion de 0, la moyenne de la dernière plage active est fixée à 0.</li></ul></li></ul> |
| postback\_sequence\_index | Oui, mais uniquement pertinent pour SKAN 4 | Integer :<ul><li>0</li><li>1</li><li>2</li></ul> | Pour une valeur précise, seule la valeur 0 peut être reçue. |

</Accordion>

<div id="upload-conversion-value-schema-file" />

<Accordion title="Télécharger le fichier de schéma de valeur de conversion">

**Avant de commencer** :

* Préparez le fichier CSV du schéma de valeur de conversion.
* Si vous intégrez des annonces Meta et mesurez les revenus, vérifiez que votre schéma est conforme aux [règles relatives à Meta.](/docs/skan-cv-decode-map-your-cv-to-events#règles-méta-spécifiques) Si vous ne le faites pas, les annonces Meta ne peuvent pas interpréter le schéma.

**Pour activer la mesure SKAN à l’aide de la mesure de décodage :**

1. Dans AppsFlyer, rendez-vous dans **Paramètres** > **Studio de Conversion SKAN.**
2. Cliquez sur Options (⋮), sélectionnez **Télécharger le fichier de mappage de décodage**.
3. Si vous n'avez pas encore effectué la mise à niveau vers SKAN 4, choisissez de télécharger un fichier pour SKAN 4 ou pré-SKAN 4. Une fois que vous avez effectué la mise à niveau vers SKAN 4, le choix d'autres versions n'est plus disponible.
4. Effectuez l'une des opérations suivantes :
   * **Cliquez pour glisser-déposer le fichier.**
   * **Téléchargez le fichier de mappage mis à jour.**
5. Suivez les instructions de l'interface utilisateur pour télécharger le fichier.
6. Activer la **mesure SKAN.**
7. Cliquez sur **Enregistrer les modifications**.   
   Remarque : Pour les 48 à 72 prochaines heures, les données du tableau de bord sont ambiguës. En raison de problèmes de minuterie iOS, nous ne pouvons pas être sûrs que le mappage de décodage correspond au mappage d'encodage que vous utilisez.
8. Assurez-vous d'avoir mappé vos événements intégrés à ceux utilisés par les partenaires afin qu'ils puissent consommer correctement les postbacks.

</Accordion>

<div id="troubleshooting-the-csv-upload-errors-file" />

## Dépannage du fichier d'erreurs de téléchargement CSV

<div id="upload-error-messages" />

<Accordion title="Télécharger les messages d'erreur">

Une ou plusieurs valeurs dans le fichier ne correspondent pas au format requis : Le format du fichier a été modifié à compter du 7 juin 2021. Vérifiez que le format de votre fichier correspond à l’exemple de cet article.

</Accordion>

<div id="using-excel-to-format-the-event_revenue_usd-column" />

<Accordion title="Utilisation d'Excel pour formater la colonne event_revenue_usd">

Lorsque vous utilisez des feuilles Excel/Google pour créer un fichier CSV, la colonne event\_revenue\_usd doit être formatée correctement avant d'enregistrer le fichier en tant que fichier CSV.

Après avoir enregistré le fichier CSV, vérifiez que le contenu est correctement formaté. **Remarque** : N'utilisez pas Excel pour effectuer la vérification ; utilisez plutôt un [éditeur](/docs/skan-cv-decode-map-your-cv-to-events#visual-inspection-of-the-csv-file-without-excel).

<div id="formatting-event_revenue_usd-cells-in-excel" />

#### Formatage des cellules event\_revenue\_usd dans Excel

Excel formate généralement les cellules de valeur avec une virgule pour séparer les milliers, comme indiqué dans la figure. Ce format ne convient pas au téléchargement de fichiers CSV. Vous devez également supprimer le symbole $.

![mceclip0.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

Vous pouvez corriger cela en formatant les cellules dans Excel.

**Pour formater les montants dépensés sans virgule 1000 ni symbole $ :**

1. Sélectionnez les cellules à formater.
2. Faites un clic droit, sélectionnez **Formater les cellules**.  
   La fenêtre de formatage des cellules s'ouvre.
3. Sélectionnez **Number**.  

   <Image alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />

1. Désélectionnez**Use 1000 separator (,).**
2. (Facultatif) Définissez le nombre de **décimales**. La valeur par défaut est 2. Le maximum autorisé est 5.
3. Cliquez sur**OK**.  
   Les cellules sont correctement formatées.

</Accordion>

<div id="visual-inspection-of-the-csv-file-without-excel" />

<Accordion title="Inspection visuelle du fichier CSV sans Excel">

Pour examiner le contenu du fichier CSV, utilisez un éditeur.

* Windows : Bloc-notes, Notepad++
* MacOS : TextEdit

Ce qui suit contient une capture d’écran de l’<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?output=csv">exemple de fichier CSV</Anchor> affiché dans un éditeur.

**Vue de l'éditeur**

![SKCustomeEditor.png](https://files.readme.io/d8677e9967a70db32e8d04c4ee835bd477b18c1cb464a9cd0e593f72ce3f3c15-34255690323217.png)

Examinez le fichier CSV dans un éditeur. Portez une attention particulière aux points suivants :

* **Espaces vides :** Assurez-vous qu'il n'y a pas d'espaces vides au début ou à la fin, avant ou après les virgules qui séparent les champs. Dans Excel, utilisez la commande @trim pour supprimer les espaces vides.
* **event\_revenue\_usd :** Assurez-vous qu'il n'y a ni virgule ni symbole $ dans la colonne event\_revenue\_usd.  

  ![mceclip1.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

</Accordion>

<div id="csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

<Accordion title="Les fichiers CSV générés par Excel n'ont pas de virgules comme délimiteurs">

Si Excel crée un fichier CSV avec un point-virgule « ; » ou d'autres caractères comme délimiteur mais pas de virgule :

* Cela se produit lorsque les paramètres régionaux de votre ordinateur sont définis sur une langue/région autre que l'anglais.
* Ce problème est particulièrement répandu lorsque l’allemand est sélectionné dans les paramètres régionaux.
* La solution diffère selon le système d'exploitation de votre ordinateur (macOS ou Windows).
* Pour résoudre ce problème, recherchez les derniers conseils de <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> ou d’autres forums. Utilisez les termes de recherche suivants : *Système d'exploitation (macOS ou Windows) Excel modifie le délimiteur pour les fichiers CSV.*

</Accordion>

<div data-zendesk-anchors="decode-skan-conversion-value=d%C3%A9coder-la-valeur-de-conversion-skan h_01HAMKKCKJEGCDPN5P8J6X0E8E=d%C3%A9coder-la-valeur-de-conversion-skan custom-conversion-value%E2%80%94decode=valeur-de-conversion-personnalis%C3%A9e--d%C3%A9coder h_01HAMKKCKJ5K6J6NNPF394ZK61=valeur-de-conversion-personnalis%C3%A9e--d%C3%A9coder h_01HAMKKCKJT7MA03SHT4X3MH4W=decode-mapping-scenario-rules facebookspecific-rules=r%C3%A8gles-m%C3%A9ta-sp%C3%A9cifiques h_01HAMKKCKJDCEKCNZFSF0V6KH8=r%C3%A8gles-m%C3%A9ta-sp%C3%A9cifiques example-decode-mapping=ex-cartographie-de-d%C3%A9codage h_01HAMKKCKJ5B7W8FGK01QCKN7Y=ex-cartographie-de-d%C3%A9codage example-b-conversion-value-1=exemple-a-valeur-de-conversion-pr%C3%A9cise-1 h_01HAMKKCKJ1ZRH00A7Q4HZ4BBK=exemple-a-valeur-de-conversion-pr%C3%A9cise-1 example-b-conversion-value-2=exemple-b-valeur-de-conversion-pr%C3%A9cise-2 h_01HAMKKCKJZBASWWM1VD0VXWBX=exemple-b-valeur-de-conversion-pr%C3%A9cise-2 example-c-conversion-value-21=exemple-c-valeur-de-conversion-pr%C3%A9cise-21 h_01HAMKKCKJ4YHMQENKNVPMV4KC=exemple-c-valeur-de-conversion-pr%C3%A9cise-21 example-d-conversion-value-62=exemple-d-valeur-de-conversion-pr%C3%A9cise-62 h_01HAMKKCKJP7V7D26MGM1WVDTE=exemple-d-valeur-de-conversion-pr%C3%A9cise-62 h_01HAMKKCKKJFRTXYJNWZNGF97V=decode-csv-file-specification decode-csv-file-specification::d6a1f3f1=d%C3%A9coder-les-sp%C3%A9cifications-du-fichier-csv h_01HAMKKCKK7G7VP6SDEHBH6383=d%C3%A9coder-les-sp%C3%A9cifications-du-fichier-csv h_01HAMKKCKKN7WDP6F5E4W91HQJ=upload-conversion-value-schema-file troubleshooting-the-csv-upload-errors-file=d%C3%A9pannage-du-fichier-derreurs-de-t%C3%A9l%C3%A9chargement-csv h_01HAMKKCKK0QQ8AS8FZ83MZ8FH=d%C3%A9pannage-du-fichier-derreurs-de-t%C3%A9l%C3%A9chargement-csv h_01HAMKKCKK3B2T9VSTYCVE0017=upload-error-messages h_01HAMKKCKKFJAE4B88QV00HYPW=using-excel-to-format-the-event_revenue_usd-column formatting-event_revenue_usd-cells-in-excel=formatage-des-cellules-event_revenue_usd-dans-excel h_01HAMKKCKKKVYCWCQCAEMSBMF7=formatage-des-cellules-event_revenue_usd-dans-excel h_01HAMKKCKK39C9SP7K86ER3HZK=visual-inspection-of-the-csv-file-without-excel h_01HAMKKCKK9GEBC64JE4DSDAMQ=csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

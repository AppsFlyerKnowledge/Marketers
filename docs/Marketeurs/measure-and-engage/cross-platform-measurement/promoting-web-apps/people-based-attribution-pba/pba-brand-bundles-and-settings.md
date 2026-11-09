---
title: Bundles de marque de PBA et paramètres
metadata:
  keywords:
    - Advertisers
    - Bundles
    - Web Attribution
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2018-12-09T11:42:52Z'
  edited_at: '2025-05-08T09:17:30Z'
  id: 360000646498
  locale: fr
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/fr/articles/360000646498
---
> **En bref** : les bundles de marque réunissent l'attribution, l'activité, les visites et les revenus des apps et sites web liés à une marque. Utilisez la page des paramètres des bundles de marques pour marquer les événements de conversion, intégrer dans Google Ads, etc.

<Image align="center" alt="BrandBundles.png" src="https://files.readme.io/eab9447f0bdd225ab7915724f996555057fa7f2840ec6e69a89465a90af6181e-360017356617.png" />

<div id="about-brand-bundles" />

## À propos des bundles de marques

Les marques opèrent dans un écosystème qui englobe les propriétés web et mobile. En tant qu'annonceur, vous aurez besoin d'avoir une vision des performances globales de la marque sur l'ensemble des plateformes (web et mobile). Dans la PBA, les bundles de marques réunissent les données des propriétés mobile et web afin de générer des analyses et des données brutes.

<div id="what-is-a-web-app" />

> 📘 **Qu'est-ce qu'une application web ?**
>
> Une application web est une <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">entité que vous avez créée dans AppsFlyer</Anchor> et qui est liée à un site web pour lequel vous souhaitez mesurer la performance.
>
> * L'entité d'app web a été ajoutée à AppsFlyer le 9 février 2022. Avant cette date, vous deviez saisir le domaine de l'ensemble de marques en tant que paramètre distinct lors de la création d'un bundle de marques. Maintenant, vous créez d'abord une app web qui définit le domaine, puis vous incluez cette application web lors de la création du bundle.
> * Si vous aviez des bundles de marques au 9 février 2022, vous avez désormais sur la page **Mes apps** une app web correspondant à chaque bundle. **Rassurez-vous !** L'attribution de votre trafic web n'est pas impactée, et il n'y a pas eu d'autres changements dans les tableaux de bord de la PBA ou dans les rapports de données brutes.

**Les bases des bundles de marques :**

* Un bundle de marques contient 1 app web *(obligatoire* ) et 1 ou plusieurs apps mobile *(facultatives)*.
* Une app (web ou mobile) peut appartenir à un seul bundle.
* Les apps ne peuvent pas être supprimées transférées d'un bundle à l'autre sans devoir [supprimer le bundle d'origine.](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle)
  * Lors de la suppression d'un lot, AppsFlyer cesse d'attribuer des données PBA pour le bundle et l'accès aux données historiques n'est plus disponible.

<div id="accessing-brand-bundles" />

## Accéder aux bundles de marques

Accédez à la page **Bundles de marques** pour gérer les bundles de marques et leurs paramètres :

* Allez dans **Mes apps** > **Voir les bundles de marques**.  
                           - ou -
* Dans l'arborescence de navigation à gauche du tableau de bord, allez dans **Configuration** > **Bundles de marques**.

<div id="managing-brand-bundles" />

## Gérer les bundles de marque

Pour ajouter, supprimer ou gérer des bundles de marques, sélectionnez l'une de ces options dans la page **Bundles de marques**:

| Option | Détails |
| --- | --- |
| Ajouter un bundle de marques | Ouvre la page **Créer une un bundle**   <br />Suivez les [instructions ci-dessous](/docs/pba-brand-bundles-and-settings#add-brand-bundle) pour créer une nouveau bundle. |
| Tableau de bord de la PBA | Ouvre le tableau de bord de la marque |
| ID de bundle de marques | Copie de l'ID du bundle de marques dans le presse-papiers |
| Clé dev web | Copie la clé web dev dans le presse-papiers |
| Sélectionnez un bundle existant pour mettre à jour les paramètres et les options du bundle de marques. | Options disponibles :<ul><li>Marquer les événements comme des événements de conversion :<ul><li>[Paramètres des événements web](/docs/pba-brand-bundles-and-settings#web-event-settings)</li><li>[Paramètres des événements in-app](/docs/pba-brand-bundles-and-settings#inapp-event-settings)</li></ul></li><li>[Exclusion de domaine](/docs/pba-brand-bundles-and-settings#domain-exclusion)</li><li><Anchor target="_blank" href="/marketers/fr/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Intégration de Google Ads</Anchor></li></ul> |
| Icône de suppression | [Supprime le bundle de marques sélectionné](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) (après confirmation de votre décision) |

<div id="add-brand-bundle" />

<Accordion title="Ajoutez un bundle de marques">

Avant de procéder, assurez-vous que toutes les apps que vous souhaitez inclure dans le bundle ont été ajoutées à votre compte. Une fois qu'un bundle a été créé, les apps qu'il comprend ne peuvent pas être modifiées sans [supprimer le bundle](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) et le recréer.

**Pour ajouter un bundle :**

1. Dans la page [Bundles](/docs/pba-brand-bundles-and-settings#accéder-aux-bundles-de-marques), cliquez sur **Ajouter un bundle**.
2. Saisissez le **nom du bundle** (le nom de votre choix pour identifier le bundle).
3. Sélectionnez les apps à inclure dans l'offre groupée.

   **Remarque :** Les apps incluses dans d'autres bundles ne sont pas disponibles pour la sélection.

   * App web *[obligatoire]*: sélectionnez une app web disponible.
   * Apps mobile *[facultatif] :* sélectionnez les apps mobile disponibles que vous souhaitez inclure dans le bundle.
     * Les apps mobile ne sont pas nécessaires pour créer un bundle.
     * Il n'y a pas de limite au nombre d'apps mobile que vous pouvez inclure dans un bundle.
4. Cliquez sur Créer un bundle.

<div id="important" />

> 🚧 **Important !**
>
> Il est impossible de créer des bundles dans les cas suivants :
>
> * L'app web sélectionnée ne pointe pas vers une URL valide.
> * L'app web et l'app mobile Android sélectionnées ont le même ID d'app.

</Accordion>

<div id="web-event-settings" />

<Accordion title="Paramètres des événements web">

Il existe deux types d'événements web : **classique** ou de **conversion**. Pour plus d'efficacité, définissez certains événements comme des événements de conversion.

* La PBA attribue de la même manière les événements de conversion et les événements standards.
* <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">Les rapports de données brutes</Anchor> incluent des événements classiques et des événements de conversion.
* Les tableaux de bord de la PBA n'incluent que les événements de conversion.
* Les types d'événement peuvent être modifiés à tout moment, mais le changement n'est pas rétroactif.

**Pour définir les événements de conversion :**

1. Sur la page [Bundles de marques](/docs/pba-brand-bundles-and-settings#accéder-aux-bundles-de-marques), sélectionnez Bundle de marques.  
   La page **Mise à jour des bundles de marques** s'ouvre.
2. Ouvrez l'onglet **Paramètres de l'événement web**.
3. Activez **Marquer comme événement de conversion**.
4. Cliquez sur **Mettre à jour le bundle**.

</Accordion>

<div id="inapp-event-settings" />

<Accordion title="Paramètres des événements in-app">

Les chemins de conversion prennent en compte les événements in-app qui ont été marqués ainsi que les événements web qui ont été marqués comme des événements de conversion. Tout comme pour les événements web, les marketeurs définissent certains événements in-app comme des événements de conversion.

[Par défaut] Les événements in-app qui ont des revenus sont marqués comme des événements de conversion. **Important** ! Si vous modifiez les événements par défaut, vous devez marquer manuellement les événements de revenus in-app.

**Pour marquer les événements in-app comme des événements de conversion :**

1. Sur la page [Bundles de marques](/docs/pba-brand-bundles-and-settings#accéder-aux-bundles-de-marques), sélectionnez Bundle de marques.  
   La page **Mise à jour des bundles de marques** s'ouvre.
2. Ouvrez l'onglet **Paramètres de l'événement in-app**.
3. Activez **Marquer comme événement de conversion**.
4. Cliquez sur **Mettre à jour le bundle**.

</Accordion>

<div id="domain-exclusion" />

<Accordion title="Exclusion de domaine">

Un principe d'exclusion de domaine (qui fait partie des règles de source média de la PBA) <Anchor target="_blank" href="/marketers/fr/docs/pba-media-source-attribution-rules">,</Anchor> est appliqué pour empêcher :

* Auto-attribution : AppsFlyer n'attribuera pas les événements au site web défini dans l'app web en elle-même ou aux domaines associés au site web de votre marque.
* L'attribution ou l'enregistrement d'événements associés à des domaines qui ne font pas partie de votre marque, mais qui participent au flux utilisateur (par exemple les passerelles de paiement).

| Type de domaine | Description | Effets de l'exclusion |
| --- | --- | --- |
| Primaire | Le domaine de l'**app web** incluse dans le bundle de marques. Il inclut les sous-domaines.<br /><br />Exemple : si votre domaine est mydomain.co.za alors les sous-domaines comme a.mydomain.co.za, b.mydomain.co.za seront exclus automatiquement. <br /><br />Le domaine d'une app web ne peut être modifié sans devoir [supprimer](/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle) et recréer l'app web (cela signifie qu'il faut supprimer aussi le bundle dans lequel l'app web est incluse). | Pas d'auto-attribution |
| Interne | Liste les autres domaines qui font partie de votre marque, exemple : mydomain.com, mydomain.in, mydomain.co.ng, abc.com | Pas d'auto-attribution |
| Externes (que vous avez listés) | Domaines utilisés directement par votre site web, mais pas par la marque. Ils incluent les passerelles de paiement, les sites de traitement des paiements, etc. | <Anchor target="_blank" href="/marketers/fr/docs/pba-media-source-attribution-rules#visit-recognition-rules">Les visites ne sont pas prises en compte</Anchor> |
| Externes (que AppsFlyer a listés) | Domaines listés par AppsFlyer et qui seront toujours exclus.<ul><li>Paypal</li><li>Stripe</li><li>Adyen</li></ul>La liste des domaines automatiques ne peut pas être modifiée. | <Anchor target="_blank" href="/marketers/fr/docs/pba-media-source-attribution-rules#visit-recognition-rules">Les visites ne sont pas prises en compte</Anchor> |

**Pour exclure des domaines internes ou externes :**

1. Dans la page [Bundles de marques](/docs/pba-brand-bundles-and-settings#accéder-aux-bundles-de-marques), cliquez sur Ajouter un bundle.  
   La page **Mise à jour des bundles de marques** s'ouvre.
2. Allez dans l'onglet Exclusion de domaine.
3. Cliquez sur **Ajouter un domaine**.
4. Saisissez un nom de domaine.
5. Sélectionnez un type de domaine : **Interne** ou **Externe**.
6. Cliquez sur **Ajouter un domaine**.  
   Il faut compter une heure pour que l'exclusion prenne effet.

</Accordion>

## FAQ

<div id="can-i-include-the-same-app-in-more-than-one-bundle" />

<Accordion title="Est-il possible d'inclure une même app dans différents bundles ?">

**Non**. Une fois qu'une app a été ajoutée à un bundle, elle ne peut pas être ajoutée à un bundle différent.

</Accordion>

<div id="can-i-add-or-remove-apps-after-creating-a-bundle" />

<Accordion title="est-il possible d'ajouter ou supprimer des applications après avoir créé un bundle de marques ?">

**Non**. Une fois qu'un bundle est créé, les apps qui lui sont associées ne peuvent pas modifiées.

**Pourquoi ?** La raison en est que chaque app possède ses propres données et qu'AppsFlyer utilise précisément ces données pour analyser le parcours utilisateur sur les plateformes (web et app). Si une app venait à être modifiée, cela produirait un ensemble de données différent qui ne serait plus compatible avec les données précédentes.

</Accordion>

<div id="how-do-i-add-or-remove-delete-apps-from-a-bundle" />

<Accordion title="Comment faire pour ajouter ou supprimer des apps à un bundle ?">

Pour modifier le bundle dans lequel une app est incluse, supprimez le bundle initial et créez-en un nouveau qui contient l'app.

</Accordion>

<div id="what-happens-if-i-delete-a-bundle" />

<Accordion title="Si je supprime un bundle, que se passe-t-il ?">

<div id="page-404" />

<div id="faqs-what-happens-if-i-delete-a-bundle" />

#### FAQ Que se passe-t-il si je supprime un bundle ?

Si vous supprimez un bundle :

* AppsFlyer cesse d'attribuer le bundle.
* Les données du bundle sont conservées (elles ne sont pas définitivement supprimées), mais le bundle en lui-même ne peut pas être restauré pour accéder aux données.

  **Pourquoi ?** Chaque nouveau bundle utilise une nouvelle clé dev web. Ainsi, même s'il contient les mêmes apps, le bundle d'origine n'est pas restauré.

</Accordion>

<div id="why-are-certain-apps-not-available-for-me-to-add-to-a-bundle" />

<Accordion title="Pourquoi est-il impossible d'ajouter certaines apps à un bundle ?">

* **Admins :** si vous ne pouvez pas sélectionner une app lors de la création d'un bundle, assurez-vous que l'app a été ajoutée à votre compte AppsFlyer et qu'elle n'est pas incluse dans un autre bundle.
* **Autres utilisateurs du compte :** vérifiez auprès d'un admin de compte que vous avez le rôle et les autorisations nécessaires pour accéder aux apps que vous essayez d'ajouter.

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/onboarding-guide-to-people-based-attribution">Guide de démarrage pour la PBA</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/people-based-attribution-pba-overview">Démarrer avec la PBA</Anchor>

<div data-zendesk-anchors="about-brand-bundles=%C3%A0-propos-des-bundles-de-marques h_01HE0Y2A3A5W86YY44RWCTKM1Y=%C3%A0-propos-des-bundles-de-marques h_01HE0Y2A3AYAFFSPRSH2BQ00Z3=quest-ce-quune-application-web- accessing-brand-bundles=acc%C3%A9der-aux-bundles-de-marques h_01HE0Y2A3A7265NYM7GVBZVXEN=acc%C3%A9der-aux-bundles-de-marques managing-brand-bundles=g%C3%A9rer-les-bundles-de-marque h_01HE0Y2A3A272QJ4ZQH7VXJWCC=g%C3%A9rer-les-bundles-de-marque h_01HE0Y2A3ATX4ZDYZSRQGSJ4G7=add-brand-bundle h_01HE0Y2A3AQC5MMNQA0AV34MZ3=important- h_01HE0Y2A3ATN6DEQ2KHCGT6VPQ=web-event-settings h_01HE0Y2A3A76VBZ17W4P1D0K2A=inapp-event-settings h_01HE0Y2A3A7F2YEW2SK0PSXXE4=domain-exclusion h_01HE0Y2A3AB24NCNPAYFC0J4YH=faq h_01HE0Y2A3A5E816CYG2TMZ37DA=can-i-include-the-same-app-in-more-than-one-bundle h_01HE0Y2A3BENKY1AM51VM76TVS=can-i-add-or-remove-apps-after-creating-a-bundle h_01HE0Y2A3BK4JKMTND0JFCB179=how-do-i-add-or-remove-delete-apps-from-a-bundle h_01HE0Y2A3BKJTQZJXV49X32N1E=what-happens-if-i-delete-a-bundle faqs-what-happens-if-i-delete-a-bundle=faq-que-se-passe-t-il-si-je-supprime-un-bundle h_01HE0Y2A3B276FV92EYBCZRA6C=faq-que-se-passe-t-il-si-je-supprime-un-bundle h_01HE0Y2A3BEB2JG8CPSX3DA1V9=why-are-certain-apps-not-available-for-me-to-add-to-a-bundle h_01HE0Y2KTXS06WHN57MQ91AD09=%C3%A0-consulter-%C3%A9galement" />

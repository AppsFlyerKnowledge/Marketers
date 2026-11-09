---
title: Dépannage et FAQ OneLink
metadata:
  keywords:
    - faq
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2020-10-27T11:26:30Z'
  edited_at: '2024-03-11T12:36:26Z'
  id: 360014821438
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/360014821438
---
> **En bref :** trouvez rapidement des solutions pour tester et déboguer les problèmes de redirection/comportement des liens personnalisés OneLink.

<div id="onelink-troubleshooting-guide" />

## Guide de dépannage OneLink

<div id="onelink-frequently-asked-questions" />

## Questions fréquentes sur OneLink

<div id="onelink-template-faq" />

### FAQ sur les templates OneLink

<div id="which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes" />

<Accordion title="Quelle méthode utiliser pour ouvrir des apps : liens universels, liens d'app ou schémas d'URI ?">

**Liens universels :** requis pour plus de 98 % des utilisateurs iOS

**Liens d’app :** pour les utilisateurs Android 6.0 et +. **Remarque** : un système d’exploitation Samsung ne pourra pas ouvrir les apps avec des liens d’app Android.

<div id="note" />

> 📘 **Remarque**
>
> Les liens universels et les liens d'app nécessitent de prouver que le domaine figurant dans l'URL cliquée (c’est-à-dire le domaine du lien personnalisé OneLink ou le domaine de marque) est détenu par et associé à l'app qu'il cherche à ouvrir. Cette association de domaine se fait via le **fichier AASA (Apple App Site Association)** **pour iOS et via le fichier Assetlinks pour Android.**
>
> Ces fichiers sont hébergés soit par AppsFlyer soit par l'annonceur sur son site web. Lorsque vous créez des templates OneLink et configurez des liens universels et des liens d'app, par défaut ces fichiers sont générés et hébergés par AppsFlyer.

**Schémas d’URI :** principale méthode d'ouverture des apps sur les appareils Samsung. C’est également il une méthode héritée et de secours pour ouvrir les apps. Ils peuvent être utilisés :

* Pour les utilisateurs Android version 6.0 ou - (moins de 15 % des utilisateurs Android)
* Comme solution de secours lorsque les liens universels et liens d’app n’ouvrent pas l’app, soit parce qu’ils ne fonctionnent pas, soit parce qu’ils n’ont pas été configurés.

  **Remarque :** l'utilisation de schémas d'URI comme solutions de secours pour les liens universels est soumise à des restrictions posées par iOS. <Anchor target="_blank" href="/marketers/fr/docs/uri-scheme-fallback-for-ios">En savoir plus</Anchor>.

#### Deep Linking

Les liens universels, les liens d'app et les schémas d'URI sont des méthodes qui permettent d'**ouvrir** une app de manière sécurisée. Pour créer un deep link et rediriger les utilisateurs vers certaines activités ou pages de l'app, veuillez suivre les <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">instructions relatives au deep linking OneLink</Anchor>.

</Accordion>

<div id="which-operating-systems-allow-uri-schemes-to-open-the-app" />

<Accordion title="Quels systèmes d'exploitation autorisent les schémas d'URI pour ouvrir l'app ?">

| OS | Les schémas d'URI fonctionnent-ils pour l’ouverture d’une app ? |
| --- | --- |
| iOS | **Oui.** À utiliser comme solution de secours en cas d’échec des liens universels.<br /><br />**Remarques importantes :**<ul><li>l'utilisation de schémas d'URI comme solutions de secours est soumise à des restrictions posées par iOS.</li><li>Pour de nombreux navigateurs, y compris Safari, vous devez ajouter le `af_force_deeplink=true` paramètre à l’URL pour utiliser les schémas d’URI comme solution de secours. <Anchor target="_blank" href="/marketers/fr/docs/uri-scheme-fallback-for-ios">En savoir plus</Anchor>.</li></ul> |
| Android | **Oui.** À utiliser sur les appareils Samsung, avec les versions Android 6.0 et -, et comme solution de secours lorsque les liens d’application ne fonctionnent pas sur les versions Android plus récentes. |
| Amazon | **Non** |
| Windows Mobile | **Non** |

</Accordion>

<div id="do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup" />

<Accordion title="Dois-je mettre à jour l'app après la configuration des liens universels iOS et des liens d'app Android ?">

**Oui.** À chaque fois que vous implémentez des liens universels ou des liens d'application pour que les utilisateurs habituels ouvrent l’app, les domaines iOS associés ou AndroidManifest.xml sont mis à jour. Cela signifie que vous devez importer une nouvelle version de l'app dans l'app store concerné. **Astuce :** pour réduire le nombre de mises à jour de l'app, effectuez en une seule fois toutes les modifications de développement liées à **l'ouverture d'app** et au <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">deep linking.</Anchor>

</Accordion>

<div id="can-i-redirect-existing-users-to-a-web-page-instead-of-the-app" />

<Accordion title="Est-il possible de rediriger les utilisateurs existants vers une page web plutôt que vers l'application ?">

**Oui.** Cependant, si votre template est configuré de cette manière, tous les utilisateurs (nouveaux et existants) seront concernés et chacun d'eux sera dirigé vers la page d'accueil/l'URL web. Les nouveaux utilisateurs ne seront donc pas envoyés sur l'app store.

Pour envoyer les utilisateurs vers une page web :

1. Dans votre template, ne configurez aucun lien universel, lien d'application ou schéma d'URI.
2. Configurez les redirections vers la page de d'accueil/l'URL qui correspondent au cas où l'app n'est pas installée.
   * Les URL de la page d'accueil/web sont ajoutées en tant que valeurs dans les paramètres af\_android\_url et af\_ios\_url.
   * Les redirections sont alors automatiquement appliquées dans le cas où l'application est installée (pour les utilisateurs existants).

**Remarque** : si vous souhaitez rediriger les utilisateurs existants vers une page web mobile uniquement après le lancement de l'app, c'est au développeur de votre application de configurer ce comportement.

</Accordion>

<div id="can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users" />

<Accordion title="Puis-je rediriger les utilisateurs de tablette vers une autre app ou URL que celle des utilisateurs d'app mobile ?">

Vous pouvez définir des redirections spécifiques pour les appareils suivants :

* Windows phone
* iPad
* Amazon Kindle Fire.

Les autres tablettes ne sont actuellement pas prises en charge pour une redirection séparée.

</Accordion>

<div id="can-i-assign-an-app-to-multiple-onelink-templates" />

<Accordion title="Puis-je attribuer une app à plusieurs templates OneLink ?">

**Oui.** Même si vous pouvez utiliser un même template OneLink pour créer un nombre infini d'URL OneLink, dans certains cas de figure vous pourrez être amené à devoir affecter une app à plusieurs templates OneLink. Si vous avez par exemple plusieurs versions d'une app Android pour les marchés hors-store, il vous faudra peut-être utiliser un template OneLink pour chacune des versions Android, tout en ayant une même app iOS affectée à l'ensemble des versions.

**Important** :

Pour les templates qui utilisent les liens universels iOS et les liens d'application Android pour l'ouverture d'app, **si vos templates possèdent plusieurs sous-domaines**, vous devez configurer et mettre à jour vos apps iOS et Android pour chacun d'eux :

* **Liens universels iOS :** après avoir créé le nouveau template OneLink et mis à jour le domaine associé au sein de l'app, envoyez une nouvelle version à l'App Store. Seuls les utilisateurs iOS qui ont auront mis à jour la nouvelle version pourront activer une URL OneLink construite sur le nouveau template.
* **Liens d'app Android**
  1. Une fois le template créé, copiez le snippet XML en bas de la section App Link et ajoutez-le à votre fichier **AndroidManifest.xml**, dans l'intention vers laquelle vous souhaitez deep linker l'utilisateur (en plus de la ou des intentions existantes).
  2. Publiez la nouvelle version dans l'app store. Seuls les utilisateurs Android qui ont effectué la mise à jour vers la nouvelle version peuvent activer une URL OneLink conçue à partir du nouveau template.

</Accordion>

<div id="can-i-delete-a-onelink-template" />

<Accordion title="Puis-je supprimer un template OneLink ?">

**Oui,** mais uniquement en contactant votre CSM ou en envoyant un e-mail à notre équipe en charge de l'engagement client à [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Remarque :** Si vous avez des URL OneLink existantes basées sur le template supprimé, **elles ne permettront pas de diriger les utilisateurs vers l'app store.** C'est pourquoi il est important de ne pas supprimer un template sans vous être assuré qu'il n'est pas utilisé par une URL OneLink. Vous pouvez également obtenir les résultats souhaités en modifiant la configuration du template existant, plutôt qu'en le supprimant.

</Accordion>

<div id="can-i-change-the-subdomain-in-a-onelink-template" />

<Accordion title="Puis-je modifier le sous-domaine dans un template OneLink ?">

**Oui, tant qu'il n'y a pas de liens personnalisés dans AppsFlyer basés sur le template.**

Si vous avez déjà créé des liens personnalisés dans AppsFlyer sur la base du template OneLink, alors la modification du sous-domaine n'est pas possible. Cette restriction évite de briser le comportement de redirection/deep linking des liens directs.

Si vous devez changer le sous-domaine dans un modèle avec des liens personnalisés existants, vous pouvez soit :

* Créer un nouveau template OneLink avec le nouveau sous-domaine, et créer des liens basés sur celui-ci.
* Supprimer tous les liens personnalisés existants basés sur le template pour lequel le sous-domaine doit être modifié. Une fois que tous les liens basés sur le template ont été supprimés, le sous-domaine peut être modifié.

</Accordion>

<div id="can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template" />

<Accordion title="Le domaine/sous-domaine d'un template OneLink peut-il être appliqué à l'ID de template d'un autre template ?">

**Non.** Le fait de prendre le sous-domaine/domaine configuré sur un template et un ID de template et de le connecter manuellement à un ID de template différent rompt la fonctionnalité des liens universels et des liens d’application, et constitue une menace pour la sécurité.

**Exemple :**

* Le template 1ABC est configuré avec des **bank.onelink.me** de sous-domaine.
* Le template D123 est configuré avec des **game.onelink.me** de sous-domaine.
* Le lien **bank.onelink.me/1ABC/shorturl** est créé sur la base du template 1ABC et fonctionne.
* Le lien **game.onelink.me/D123/exampleurl** est créé à partir du template D123 et fonctionne.
* Le lien **bank.onelink.me/1ABC/shorturl** ne fonctionne pas
* Le fichier **link bank.onelink.me/D123/exampleurl** ne fonctionne pas

</Accordion>

<div id="can-i-use-the-same-subdomain-for-more-than-one-template" />

<Accordion title="Puis-je utiliser le même sous-domaine pour plusieurs templates ?">

**Oui.** Veillez à créer des templates distincts du sous-domaine : ne vous contentez pas d'ajouter le sous-domaine à un ID de template.

</Accordion>

<div id="how-can-i-redirect-desktop-users" />

<Accordion title="Comment rediriger les utilisateurs d'ordinateurs de bureau ?">

Les utilisateurs de ordinateur de bureau peuvent interagir avec vos liens personnalisés OneLink, par exemple, via une campagne e-mail. Cependant, lorsque les utilisateurs d’ordinateur de bureau cliquent sur ces liens, ils ne peuvent pas être redirigés vers un site mobile, un app store ou une app.

**Alors comment offrir aux utilisateurs d’ordinateur de bureau une bonne expérience utilisateur et les convertir en utilisateurs de mobile ?**

Dans l'URL ou le template OneLink, vous pouvez rediriger les utilisateurs d’ordinateur de bureau (Windows ou Mac) vers une autre URL. Cette URL est ajoutée au lien dans le `af_web_dp` paramètre. **Remarque :** `af_web_dp`si votre lien contient `af_web_dp`, AppsFlyer n'enregistre pas les clics provenant d'un ordinateur de bureau.

<div id="tip" />

> 👍 **Astuce**
>
> Redirigez les utilisateurs d’ordinateur de bureau vers une URL qui contient un formulaire web spécifique qui permettra d'envoyer une URL OneLink (via SMS ou e-mail) sur l'appareil mobile de l'utilisateur de l’ordinateur. En savoir plus sur cette option dans le cadre de la solution <Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors#desktop">OneLink Smart Script</Anchor>.

</Accordion>

<div id="how-can-i-redirect-chrome-os-users" />

<Accordion title="Comment rediriger les utilisateurs de Chrome OS ?">

Les apps sur Chromebooks sont considérées comme des apps Android.

Sous Chromebook, pour rediriger les nouveaux utilisateurs sans que votre app soit installée sur une URL web différente :

1. Dans les paramètres du template OneLink, dans **Définir le comportement du lien** > **Lorsque l’application n’est pas installée** > **Android**, cliquez sur **Remplacer par une autre URL**.  
   OU  
   Dans les paramètres de lien OneLink, dans **Deep Linking et redirection** > **Rediriger** > **Lorsque l’application n’est pas installée** > **Android**, sélectionnez **URL Web**.
2. Saisissez l'URL.  
   Lorsqu'elle est ajoutée via les paramètres du lien, l'URL est ajoutée à votre lien dans le paramètre `af_android_url`.

</Accordion>

<div id="onelink-link-faq" />

### FAQ sur les liens OneLink

<div id="does-onelink-work-without-the-appsflyer-sdk" />

<Accordion title="OneLink peut-il fonctionner sans le SDK AppsFlyer ?">

**Oui, mais seulement en partie.**

Si vous avez besoin de convertir rapidement des visiteurs web mobile en utilisateurs mobile et que vous ne pouvez pas intégrer le SDK AppsFlyer, c'est possible.

La redirection basique de l'utilisateur et le lancement de l'app fonctionnent même si le SDK AppsFlyer n'est pas encore intégré à l'app. Les Smart Banners n'ont pas besoin du SDK non plus, et fonctionnent très bien sans lui.

Cependant, l'absence de SDK induit que :

* Les utilisateurs ne seront pas deep linkés après le lancement initial de l'app.
* Aucune donnée d'attribution ne sera enregistrée.
* Les événements in-app ne seront pas enregistrés.

</Accordion>

<div id="what-methods-are-available-for-creating-onelink-custom-links" />

<Accordion title="Quelles sont les méthodes disponibles pour créer des liens personnalisés OneLink ?">

Le tableau suivant compare les différentes méthodes disponibles pour créer des liens personnalisés OneLink.

| Méthode de création de liens | Utilisations | URL courte ou longue | Fonctionnalité Premium | Visible dans l'interface utilisateur ? | TTL d'attribution (Time to Live) max et par défaut |
| --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Interface utilisateur APPSFLYER</Anchor> | Créer un template OneLink et des liens personnalisés | Les deux | -- | ✓ | Pas de TTL |
| <Anchor target="_blank" href="/marketers/fr/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> | Créez rapidement des milliers de OneLink | Courte | ✓ | -- | 31 jours |
| Création de groupes de liens OneLink | Créez rapidement des milliers d’URL courtes OneLink à l’aide de paramètres inscrits dans un fichier CSV | Courte | -- | -- | 365 jours |
| <Anchor target="_blank" href="/marketers/fr/docs/user-invite-attribution">SDK</Anchor> | Campagnes d'invitation (parrainage) d'utilisateur | Courte | -- | -- | 60 jours |
| <Anchor target="_blank" href="/marketers/fr/docs/onelink-smart-script-overview">Script intelligent OneLink</Anchor> | Campagnes web-to-app mobile | Longue | -- | -- | Pas de TTL |
| <Anchor target="_blank" href="/marketers/fr/docs/understand-onelink-short-vs-long-urls">Feuille de calcul</Anchor> | Créer des milliers de liens personnalisés OneLink avec vos propres formules | Longue | -- | -- | Pas de TTL |

</Accordion>

<div id="can-onelink-custom-links-open-the-app-from-a-browser" />

<Accordion title="Les liens personnalisés OneLink peuvent-ils ouvrir l'app à partir d'un navigateur ?">

**Oui,** mais sachez que les liens universels et les liens d'app ne fonctionnent que lorsque l'on clique dessus (par exemple, lorsque l'on clique sur un lien dans une page web ou un e-mail). **Le fait de coller le lien dans la barre d'adresse du navigateur ne permet pas de lancer l'app.** Effectuez votre test en cliquant sur les URL, et non en les copiant-collant dans la zone URL du navigateur.

</Accordion>

<div id="why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users" />

<Accordion title="Pourquoi l'URL OneLink n'ouvre-t-elle pas l'app, ou n'établit-elle pas de deep linking avec les utilisateurs existants ?">

Parfois, et même en suivant tout à la lettre, vos URL OneLink ne produisent pas le deep linking que vous aviez prévu. Le résultat, c'est que plutôt que d'ouvrir l'app ou d'être deep linké vers une certaine activité de l'app, l'utilisateur est redirigé vers l'app store, voire sur une page d'erreur.

Il y a plusieurs explications possibles :

* **Applications hôtes :** les apps dans lesquelles vos liens d'attribution sont partagés (ex. WhatsApp, Gmail, WeChat) utilisent différentes méthodes pour activer les liens cliqués, notamment les navigateurs internes propriétaires. Certains d'entre eux sont connus pour bloquer tous les liens d'attribution.
* **Navigateurs :** certains navigateurs et certaines plateformes OS réagissent différemment aux liens. Certains navigateurs, par exemple, ne permettent pas de copier-coller un lien. Il est nécessaire de cliquer sur le lien.
* **Mises à jour du système d’exploitation : les nouvelles mises à jour du système d'exploitation (iOS et Android) peuvent introduire des bugs qui affectent le fonctionnement du deep linking.**
* **Appareils :** la gestion des liens d'attribution peut varier de manière significative selon les smartphones, tablettes, ordinateurs portables et autres appareils, et selon les différentes versions d'iOS, Android, de Windows Mobile ou autres systèmes d'exploitation qu’ils utilisent.
* **Erreur de configuration :** l'utilisation de <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">caractères spéciaux</Anchor> dans la valeur du deep linking brise le lien.

Les URL de secours et le deep linking forcé sont deux solutions qui permettent d'améliorer l'expérience utilisateur.

<div id="fallback-urls" />

#### URL de secours

Les URL de secours vous permettent de rediriger les utilisateurs vers des pages web spécifiques, dans le cas où l'ouverture de l'app ou le deep linking échoue pour une raison quelconque. **Attention !** Les utilisateurs qui n'ont pas installé votre app seront dirigés vers l'URL de secours et non vers l'app store approprié. Par conséquent, vous ne devez utiliser cette option que si vous redirigez des utilisateurs qui ont déjà installé votre app.

Pour implémenter une URL de secours, dans les paramètres du template OneLink ou du lien personnalisé, définissez le comportement du lien lorsque l'app n'est pas installée pour rediriger vers une autre URL.

<Image align="center" alt="different_url.png" src="https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png" />

L’utilisation de ce paramètre ajoute `af_ios_url` et `af_android_url` comme paramètres de destination pour la solution de secours, ce qui entraîne la redirection des utilisateurs iOS vers la page définie par `af_ios_url`, et la redirection des utilisateurs Android vers la page définie par `af_android_url`.

<div id="tip-1" />

> 📄 **Exemple**
>
> Prenons par exemple l'URL OneLink suivante :
>
> ```http
> https://go.onelink.ly/qwerty?pid=source&af_dp=greatapp%3A%2F%2F&af_ios_url=www.yoursite.com/ios-bonus
> &af_android_url=www.yoursite.com/android-bonus
> ```
>
> Les utilisateurs iOS et Android qui cliquent sur ce lien sont censés être deep linkés dans l'app. Lorsque le deep link ne fonctionne pas, les utilisateurs sont redirigés comme suit :
>
> * iOS: www.yoursite.com/ios-bonus
> * Android : www.yoursite.com/android-bonus

<div id="note-1" />

> 📘 **Remarque**
>
> * Si vous incluez un symbole de hachage (#) dans une valeur de paramètre dans l'URL, vous devez l'encoder.
> * En cas de redirection, les paramètres URL de OneLink passent sur la page de destination définie par `af_ios_url` ou `af_android_url`. Pour éviter ce comportement, ajoutez le paramètre `af_param_forwarding=false` à OneLink.

<div id="forced-deep-linking" />

#### Deep linking forcé

Le deep link forcé vous permet d'utiliser un schéma d'URI comme solution de secours pour l'ouverture de l'app, et de deep linker les utilisateurs.

Cette solution est efficace sur la majorité des utilisateurs qui ont installé l'application. Toutefois, pour iOS, l’utilisation d’un schéma d’URI pour ouvrir l’application présente des limites, et vous devrez peut-être ajouter `af_force_deeplink=true` à l’URL OneLink pour forcer le deep linking vers l’activité spécifiée dans le schéma d’URI (le paramètre`af_dp`). En savoir plus <Anchor target="_blank" href="/marketers/fr/docs/uri-scheme-fallback-for-ios">sur les schémas d'URI de secours sous iOS.</Anchor>

</Accordion>

<div id="why-does-my-onelink-url-open-a-blank-page-in-chrome" />

<Accordion title="Pourquoi mon URL OneLink ouvre-t-elle une page vierge dans Chrome ?">

Assurez-vous que vous n'utilisez pas une balise HTML  qui inclut l'attribut `target`. Si l'URL OneLink est placée à l'intérieur d'une balise  avec l'attribut `target="_blank"`, elle ouvre une page vierge dans Chrome (sur iOS et Android) et l'utilisateur n'est pas redirigé vers l'App Store ou vers Google Play.

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-brave" />

<Accordion title="Est-il possible d'utiliser OneLink pour rediriger sur Brave ?">

Oui. Cependant, sous Android, lorsqu’un utilisateur clique sur un lien OneLink dans un navigateur Brave, le deep linking différé ne fonctionne pas. Sous iOS, après avoir cliqué, l'utilisateur voit s'afficher un écran vide. Le deep linking différé ne fonctionnera qu'une fois qu'il aura réalisé une action sur cet écran vide (cliquer ou faire défiler l'écran par exemple).

</Accordion>

<div id="do-onelink-custom-links-take-longer-to-load-than-other-links" />

<Accordion title="Les liens personnalisés OneLink sont-ils plus longs à charger que les autres liens ?">

**Non.** Les liens personnalisés OneLink n'impliquent aucun temps de chargement ou de traitement supplémentaire pour fonctionner correctement et rediriger les utilisateurs comme prévu. Ils sont aussi rapides que les autres liens AppsFlyer.

</Accordion>

<div id="how-can-i-record-the-cost-per-install-when-using-onelink" />

<Accordion title="Comment enregistrer le coût par installation lorsque j'utilise OneLink ?">

L'activation du bouton **Coût par installation** (dans **Paramètres avancés**) vous permet d'appliquer une valeur CPI spécifique pour chaque installation provenant du lien.

Sélectionnez le coût de la devise et une **valeur numérique UNIQUEMENT** (jusqu'à 4 chiffres après la virgule) représentant le CPI. Cela ajoute les paramètres af\_cost\_currency et af\_cost\_value au lien.

<div id="tip-2" />

> 📄 **Exemple**
>
> Une campagne SMS coûte 20 $ par tranche de 1 000 messages (CPM). D'après votre expérience, ces campagnes atteignent un taux de conversion de 5 %, c'est-à-dire que le CPI dérivé est de 0,40 $. La définition du coût par installation à 0,40 $ permet de mesurer facilement le ROI éventuel de la campagne SMS.

En savoir plus sur la <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview">mesure du coût et du ROI</Anchor>.

</Accordion>

<div id="how-can-i-prevent-parameter-forwarding-on-redirections" />

<Accordion title="Comment puis-je empêcher la transmission de paramètres sur les redirections ?">

Reportez les paramètres `af_r`, `af_ios_url`, `af_android_url`, et `af_web_dp` du lien d’attribution ou de OneLink vers la page redirigée. Pour éviter ce comportement, ajoutez `af_param_forwarding=false` au lien d’attribution.

</Accordion>

<div id="how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls" />

<Accordion title="Comment supprimer les paramètres PID et C d'AppsFlyer lors de la redirection, tout en conservant les autres paramètres des URL de redirection ?">

Dans certains cas, vous pouvez avoir des URL avec plusieurs PID. Cela se produit quand AppsFlyer ajoute les paramètres PID et C à une URL de redirection et que le client peut également ajouter ses propres paramètres PID. Par exemple, l'ID du produit peut être « pid » dans l'URL du site web du client.

Normalement, l’ajout de `af_param_forwarding=false` au lien d’attribution supprime tous les paramètres.

Toutefois, si l'utilisateur clique sur le lien depuis un ordinateur de bureau, le client peut souhaiter que les paramètres CRM essentiels soient conservés. Pour supprimer uniquement les paramètres PID et C d'AppsFlyer et conserver tous les autres paramètres, ajoutez `af_base_params_forward=false` au lien d'attribution.

</Accordion>

<div id="are-singleplatform-custom-links-still-available" />

<Accordion title="Les liens personnalisés pour plateforme unique sont-ils toujours disponibles ?">

OneLink est désormais la seule méthode prise en charge pour créer des liens d'attribution personnalisés pour les médias propres.

Auparavant, les propriétaires d'apps pouvaient également utiliser des liens personnalisés (spécifiques aux apps) sans utiliser OneLink. Cette méthode est obsolète et les nouveaux liens personnalisés peuvent être créés uniquement à partir d'un template OneLink.

Toutefois, si vous avez des liens personnalisés liés à une plateforme unique, ils sont toujours opérationnels. Vous pouvez également consulter et modifier vos anciens liens en cliquant sur **Afficher les anciens liens uniques pour la plateforme** en haut à droite de la page des liens personnalisés OneLink.

</Accordion>

<div id="can-i-change-the-short-url-id-after-saving-a-link" />

<Accordion title="Puis-je modifier l'ID de l'URL courte après avoir enregistré un lien ?">

**Non,** l'ID d'URL courte ne peut être défini qu'au moment de la création du lien.

</Accordion>

<div id="can-i-wrap-and-shorten-onelink-custom-links" />

<Accordion title="Puis-je encapsuler et raccourcir les liens personnalisés OneLink ?">

**Non, les raccourcisseurs de liens externes ou l'encapsulage de vos liens personnalisés OneLink risquent de bloquer la fonctionnalité d'ouverture d'app des liens universels et des App Links.**

Pour pouvoir activer les liens universels ou les App Links, l'OS doit reconnaître le domaine de l'URL qui est associée à l'app, or tout type d'encapsulage externe, de raccourcissement ou de redirection vers le lien utilisateur rend cette action impossible. Cela inclut l’utilisation de liens bit.ly, de liens ne portant pas la marque AppsFlyer ou de fournisseurs de services de messagerie (ESP) avec l’enregistrement des clics activé.

**Pour encapsuler ou raccourcir un lien sans perturber le fonctionnement de la redirection :**

* Utilisez les URL courtes générées par AppsFlyer lorsque vous créez des liens personnalisés OneLink (plutôt qu'un raccourcisseur externe de type bit.ly).  
  **Conseil** ! Créez une URL encore plus courte en inscrivant un domaine de marque court dans votre lien. Et si vous créez les liens dans l'interface utilisateur AppsFlyer, vous pouvez modifier l'ID de l'URL pour la raccourcir au maximum. Exemple : https://brand.com/a1b2/a (où **brand.com** est votre domaine de marque, **a1b2** est l’ID du template qui est toujours de 4 caractères, et **a** est l’ID de l’URL, qui peut être réduit à 1 caractère).   
  Avantages :
  * Cette méthode fonctionne car elle utilise le sous-domaine OneLink configuré dans le template OneLink.
  * Cela vous permet de modifier les paramètres à n'importe quel moment, y compris les paramètres de deep linking, et ce même après avoir transmis les liens d'attribution à vos prospects.
  * Tous les clics issus d'appareils mobile sont comptabilisés dans le tableau de bord AppsFlyer, vous n'avez donc pas besoin de vérifier sur un autre service.
  * La dernière partie de l'URL courte peut être personnalisée pour la transformer en <Anchor target="_blank" href="/marketers/fr/docs/brand-onelink-with-your-domain">lien de marque.</Anchor>
* Utilisez le <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-2#procedures-for-uri-scheme">schéma URI</Anchor> comme solution de secours pour ouvrir l'app lorsque les liens universels et les liens d'app échouent, et ajoutez le paramètre suivant au lien : `af_force_deeplink=true`.
* Voir les options pour [utiliser les ESP](/docs/onelink-troubleshooting-and-faq#can-i-use-onelink-custom-links-in-emails).

</Accordion>

<div id="can-i-use-onelink-custom-links-in-emails" />

<Accordion title="Puis-je utiliser des liens personnalisés OneLink dans des e-mails ?">

**Oui,** mais cela nécessite une attention particulière lorsque vous travaillez avec des fournisseurs de services de messagerie (ESP). Pour comptabiliser les clics effectués, les ESP englobent tous les liens placés dans les e-mails. Cela interrompt le flux d'ouverture de l'app et de deep linking pour les utilisateurs qui cliquent sur l'URL.

Pour éviter cela, utilisez l'une des solutions facultatives suivantes :

* Désactivez l'enregistrement des clics dans votre configuration ESP.  
  **(Notre avis :** c'est généralement la solution la plus simple).
* Forcez l'ouverture de l'app avec le schéma d'URI spécifié dans le paramètre `af_dp` en ajoutant l'indicateur `af_esp=true` au lien d'attribution. Cette solution est efficace pour les utilisateurs qui ont installé l'app.
* Utilisez des ESP qui prennent en charge la solution AppsFlyer  pour l'ouverture d'app et le deep linking de liens universels. <Anchor target="_blank" href="/marketers/fr/docs/email-service-provider-esp-integration-guide">En savoir plus</Anchor>.

</Accordion>

<div id="how-do-users-get-redirected-to-their-regional-app-store" />

<Accordion title="Comment les utilisateurs sont-ils redirigés vers leur app store régional ?">

OneLink redirige les utilisateurs vers l'app store régional qui correspond à leur adresse IP.

</Accordion>

<div id="why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain" />

<Accordion title="Pourquoi mon URL OneLink ne redirige pas les utilisateurs vers le domaine spécifié ?">

Vérifiez que vous avez activé les listes de redirection autorisées dans AppsFlyer. Si vous les avez activées, le domaine ou le sous-domaine de l'URL web choisi doit y apparaître. <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-api-allowlist#redirect-allowlists">En savoir plus sur les listes de redirection autorisées</Anchor>

</Accordion>

<Accordion title="Pourquoi est-ce que je reçois l’erreur « L’application que vous recherchez n’est pas disponible » ?">

L’erreur « L’application que vous recherchez n’est pas disponible » peut se produire au lieu d’une redirection vers Google Play pour les raisons suivantes :

* Votre application a le statut « En attente » sur Google Play. Pour éviter le message d’erreur mentionné ci-dessus, configurez la redirection du lien afin de pointer vers une URL Web au lieu de Google Play. Une fois l’application approuvée, la redirection peut être modifiée vers Google Play. Ces modifications de configuration sont effectuées sur la <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">page de template du lien</Anchor>.
* Si votre application est disponible exclusivement via un app store tiers, le problème peut provenir de son statut Google Play incorrect dans AppsFlyer. Pour résoudre ce problème, vous <Anchor target="_blank" href="/marketers/fr/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">devez définir son statut Google Play sur Publié hors store</Anchor> sur la page Paramètres, Mes applications.

</Accordion>

<div id="can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link" />

<Accordion title="Est-il possible de passer manuellement du domaine de marque au sous-domaine OneLink dans un lien déjà existant ?">

Oui - Si le domaine de marque et le sous-domaine OneLink sont correctement mappés. Voir : <Anchor target="_blank" href="/marketers/fr/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer">Configurer un domaine de marque dans AppsFlyer</Anchor>

**Exemple :**  
Sous-domaine OneLink : **demo.onelink.me**  
ID du template : **A1r4**  
Les domaines de marque mappés au sous-domaine [**demo.onelink.me**](http://demo.onelink.me) sont les suivants :

* **app.simulatorapp.com**
* **click.simulatorapp.com**

Vous avez créé le lien de marque suivant dans l’interface utilisateur OneLink :  
**app.simulatorapp.com/A1r4/simulationlink**  
Vous pouvez remplacer le lien de marque ci-dessus par le lien de l'autre domaine de marque, ou par le lien du sous-domaine OneLink.  
Les liens suivants sont identiques dans le principe et fonctionnent partout de la même manière :

* app.simulatorapp.com/A1r4/simulationlink
* demo.onelink.me/A1r4/simulationlink
* click.simulatorapp.com/A1r4/simulationlink

</Accordion>

<div id="onelink-parameter-faq" />

### FAQ sur les paramètres OneLink

<div id="what-parameters-are-mandatory-for-onelink-custom-links" />

<Accordion title="Quels paramètres sont obligatoires pour les liens personnalisés OneLink ?">

Seul le paramètre de la source média (**pid**) est obligatoire.

</Accordion>

<div id="can-parameters-be-appended-to-the-short-url" />

<Accordion title="Les paramètres peuvent-ils être ajoutés à l'URL courte ?">

**Oui,** n'importe quel paramètre peut être ajouté à l'URL courte.

**Important !** Les paramètres ajoutés à l'URL courte ne remplacent pas les paramètres à l'intérieur du lien.

<div id="tip-3" />

> 📄 **Exemple**
>
> * Vous créez un lien personnalisé OneLink avec la sortie suivante :
>   * **URL longue :** https://onelink-sim.onelink.me/Il2C?pid=training&c=peaches
>   * **URL courte :** https://onelink-sim.onelink.me/Il2C/70e6d165
> * Vous ajoutez les paramètres suivants à l'URL courte : https://onelink-sim.onelink.me/Il2C/70e6d165?c=bananas&af_adset=fruits
> * Le paramètre **af\_adset=fruits** ajouté à l’URL courte est effectif pour l’attribution. Cependant, le paramètre **c=bananas** **n’est pas effectif** car il y a déjà un paramètre **c** dans l’URL longue.

</Accordion>

<div id="what-custom-media-source-names-can-i-use" />

<Accordion title="Quels noms de sources média personnalisés puis-je utiliser ?">

Pour les médias propres, les noms de sources média personnalisées sont libres. Toutefois, il est recommandé de ne pas utiliser *« organique »* comme nom de source média personnalisé, car cela pourrait affecter l’intégrité des données d’attribution.

Si vous utilisez OneLink pour les médias payants :

* Utilisez les valeurs **PID** réservées (finissant par **\_int**) des partenaires intégrés comme valeurs de source média dans les liens personnalisés OneLink. N’utilisez pas de sources média SRN telles que *googleadwords* ou *facebook* comme noms de sources média personnalisés. Cela pourrait affecter l’intégrité des données d’attribution.
* Assurez-vous que le partenaire est intégré dans AppsFlyer et actif (avec l’option « **Activer le partenaire** » activée) pour toutes les applications configurées dans le template OneLink.

</Accordion>

<div id="what-attribution-parameters-can-be-added-to-a-onelink" />

<Accordion title="Quels paramètres d'attribution peuvent être ajoutés à un OneLink ?">

Vous pouvez ajouter de nombreux paramètres d'attribution pour vous permettre d'effectuer ensuite des analyses plus approfondies.

| **Paramètre d'attribution** | **Description** | **Nom du lien du paramètre** |
| --- | --- | --- |
| **Campagne** | Définissez des noms de campagnes pour comparer différentes campagnes au sein de la source média propre | C |
| **Adset** | Définissez des noms d'adset pour comparer différents adsets au sein de certaines campagnes de la source média propre | af\_adset |
| **Nom de la publicité** | Définissez des noms d'adset pour comparer différentes créations au sein d'adsets/de campagnes de la source média propre | af\_ad |
| **Canal** | Définissez les noms des canaux si vous souhaitez comparer plus d'un canal de distribution pour vos médias propres.<br /><br />Exemple : Par exemple, si vous divisez vos messages SMS entre deux fournisseurs de services SMS, précisez quel fournisseur utilise le paramètre de canal. Par la suite, vous pourrez comparer les taux de conversion des deux fournisseurs. | af\_channel |
| **Paramètres abonné** | Utilisez l'un des 5 paramètres d'abonné disponibles pour insérer des valeurs qui serviront vos analyses.<br /><br />**Remarque :** ces paramètres sont analysés et apparaissent dans les rapports de données brutes, ce qui les rend très utiles pour l'agrégation de données ou le filtrage. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |
| **Paramètres personnalisés** | Comme pour les paramètres d'abonné, vous pouvez spécifier des champs avec n'importe quels noms et valeurs de paramètres, et n'importe quel nom.<br /><br />Contrairement aux paramètres abonnés, les paramètres personnalisés ne sont pas analysés dans les données brutes ; ils apparaissent dans les rapports de données brutes dans la colonne **URL d'origine**. | Personnalisation  <br />(selon vos spécifications) |

Obtenir plus d'informations sur <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">les paramètres et la structure des liens d'attribution AppsFlyer</Anchor>.

</Accordion>

<div id="are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data" />

<Accordion title="Les paramètres personnalisés sont-ils ajoutés aux liens personnalisés OneLink disponibles dans les données brutes ?">

**Oui.** Les paramètres personnalisés sont transmis à la colonne **URL d'origine** dans les données brutes où ils peuvent être consultés. Ils n'ont pas leurs propres colonnes dans les données brutes.

Pour les données analysées, utilisez les paramètres d'abonné `af_sub1-5`, chacun d'entre eux ayant une colonne distincte dans les rapports de données brutes.

</Accordion>

<div id="are-parameter-names-case-sensitive" />

<Accordion title="Les noms de paramètre sont-ils sensibles à la casse ?">

**Oui.** Faites en sorte de n'utiliser que des lettres minuscules pour vos paramètres et valeurs. Utiliser des lettres majuscules dans les noms et valeurs des paramètres peut créer des erreurs ou des incohérences dans les données, tant sur le tableau de bord que dans les données brutes.

</Accordion>

<div id="integrated-partner-faq" />

### FAQ sur les partenaires intégrés

<div id="can-i-use-onelink-in-social-apps-unpaid" />

<Accordion title="Puis-je utiliser OneLink dans les apps sociales (non payantes) ?">

Il est parfois utile d'utiliser OneLink avec les publications gratuites sur les apps sociales, car les utilisateurs potentiels exposés à ce type de posts ne peuvent pas être ciblés à l'avance selon leur appareil.

Malheureusement, les limitations établies par les Universal Links d'Apple, associées aux restrictions de certaines apps sociales, empêchent l'utilisation de OneLink pour la reconnaissance, la redirection, l'attribution des appareils de base et le deep linking. Dans certains cas, il peut s'avérer nécessaire de mettre en place une page de destination de l'app sociale, ou un schéma d'URI, afin de rediriger ou de deep linker les utilisateurs.

Le tableau suivant indique comment les OneLinks peuvent être utilisés avec les apps sociales les plus répandues :

<table><thead><tr><th>App sociale</th><th>Utilisateurs Android qui n'ont pas installé l'app</th><th>Deep Linking Android</th><th>Utilisateurs IOS qui n'ont pas installé l'app</th><th>Deep Linking iOS</th></tr></thead><tbody><tr><td> <strong>Facebook</strong> (y compris les publications boostées)</td><td><span>✓\*\*<span>†</span><span>† </span></span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Facebook Messenger</strong></td><td><span>✓\*\*<span>†</span><span>† </span></span></td><td> <span>✓\*\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Snapchat</strong></td><td><span>✓<span>†</span><span>† </span></span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Instagram</strong></td><td><span>✓<span>†</span><span>† </span></span></td><td><span>✓</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>LinkedIn</strong></td><td><span>✓</span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td><strong>Reddit</strong></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td><strong>Slack</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>X (anciennement Twitter)</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>WeChat</strong></td><td><span>✓<span>† </span></span></td><td><span>✓<span>† </span> </span></td><td><span>✓\*</span></td><td><span>✓\*<span>† </span></span></td></tr><tr><td><strong>WhatsApp</strong></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="5"><p>\* Si un <a href="./onelink-troubleshooting-and-faq#which-operating-systems-allow-uri-schemes-to-open-the-app">schéma d'URI</a> ou une page d'accueil de réseau social a été définie. <strong>Remarque</strong> : pour Facebook et Facebook Messenger, si à la fois un schéma d'URI et une page d'accueil d'app sociale sont configurés, alors la page d'accueil de l'app sociale ne s'affiche pas.</p><p>\*\* Doit forcément contenir un schéma d'URI.</p><p><span>†</span> L'utilisateur peut être invité à ouvrir le lien dans un navigateur externe.</p><p><span>†</span><span>† </span><span><span>Limitation de la redirection via le deeplinking des apps sociales Android WebView. Voir les détails <a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection" target="_blank">ici</a>.</span></span></p></td></tr></tbody></table>

</Accordion>

<div id="can-i-use-onelink-with-ad-networks-paid" />

<Accordion title="Puis-je utiliser OneLink avec un réseau publicitaire (payant) ?">

**Oui,** mais notez que OneLink est principalement utilisé avec les médias propres, pas avec les réseaux publicitaires. En effet, comme les réseaux publicitaires font généralement de la publicité in-app (ce qui induit qu’ils connaissent la plateforme de l’utilisateur, l’ID de l’appareil, etc.), les liens d’attribution spécifiques aux apps et aux plateformes sont suffisants, il n’est donc pas nécessaire d'avoir recours à OneLink. Cependant, lorsque les réseaux publicitaires ne connaissent pas la plateforme utilisateur à l'avance (par exemple lorsqu'ils exécutent eux-mêmes des campagnes par e-mail ou SMS), OneLink peut s'avérer utile.

<div id="important" />

> 🚧 **Important !**
>
> Lorsque vous utilisez OneLink avec des réseaux publicitaires, vous devez utiliser l'URL longue OneLink.

**Pour mettre en place OneLink pour les ad networks partenaires :**

* Suivez les <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">instructions relatives au lien d'attribution d'un réseau publicitaire</Anchor>, et sélectionnez **Utiliser OneLink**.

Une fois tous les paramètres pour Android et iOS bien ajoutés, lorsque l'utilisateur clique sur le lien personnalisé OneLink et qu'il est redirigé vers la plateforme choisie, les paramètres sont envoyés au réseau via postback après l'installation.

<div id="tip-4" />

> 📄 **Exemple**
>
> ```http
> https://greatapp.onelink.me/3287867539?pid=network_int&c=email&
> idfa{$IDFA}&gaid={$GAID}&clickid=$SITEID&
> af_sub1=[pixel_code]&af_sub2=[creative]
> ```
>
> Le réseau utilise les paramètres IDFA ou GAID correspondant à la plateforme de l'appareil du client et ignore l'autre paramètre.

</Accordion>

<div id="how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps" />

<Accordion title="Comment puis-je résoudre le problème de lancement de l'app iOS à partir des apps de médias sociaux ?">

Facebook et d'autres apps de réseaux sociaux bloquent parfois l'ouverture des apps via les liens universels iOS. La solution recommandée pour les problèmes de lancement d'app de réseaux sociaux est la <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">page de destination des apps sociales.</Anchor>

Si vous ne souhaitez pas utiliser les pages de destination des apps sociales, vous pouvez utiliser des schémas d'URI comme méthode de secours. Remarque :

* l'utilisation de schémas d'URI comme solutions de secours est soumise à des restrictions posées par iOS.
* Pour de nombreux navigateurs, y compris Safari, vous devez ajouter le `af_force_deeplink=true` paramètre à l’URL pour utiliser les schémas d’URI comme solution de secours. <Anchor target="_blank" href="/marketers/fr/docs/uri-scheme-fallback-for-ios">En savoir plus</Anchor>.

</Accordion>

<div id="can-i-use-onelink-on-instagram" />

<Accordion title="Puis-je utiliser OneLink sur Instagram ?">

**Oui,** mais les restrictions suivantes s'appliquent :

* La façon dont Instagram affiche le texte d'une page rend les liens des légendes de posts non cliquables.
* L'ouverture d'apps et le deep linking dans les apps Android sont pris en charge sans aucune considération particulière. Cependant, Instagram ne prend pas en charge l'ouverture d'apps et le deep linking dans les apps iOS. Pour surmonter ce problème, vous pouvez adopter l'une des deux approches suivantes :

  * **Recommandé :** configurez une <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">page d'accueil d'app sociale</Anchor>. Les templates Clustered Poster et ShowAndTell sont les mieux adaptés. En plus de la page de destination sociale, nous vous recommandons de définir un schéma d'URI dans votre template OneLink.
  * Utilisez un schéma d'URI et le [deep linking forcé](/docs/onelink-troubleshooting-and-faq#deep-linking-forcé) lorsque vous utilisez OneLink sur Instagram. N'oubliez pas les considérations suivantes lorsque vous utilisez `af_force_deeplink=true`OneLink sur Instagram :`af_force_deeplink=true`  

| App installée ? | Le clic possède-t-il af\_force\_deeplink=true ? | Résultat |
| --- | --- | --- |
| Non | Oui | Le clic ouvre l'app store |
| Non | Non | Le clic ouvre l'app store |
| Oui | Oui | Le clic ouvre l'app |
| Oui | Non | Le clic ouvre l'app store |

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-wechat" />

<Accordion title="Est-il possible d'utiliser OneLink pour rediriger sur WeChat ?">

WeChat ignore les deep links Android et IOS et redirige les utilisateurs vers une page web. À partir de cette page web, l'utilisateur doit alors cliquer sur le bouton **Options** et sélectionner « Ouvrir la page dans le navigateur ». Par conséquent, les utilisateurs rencontrent une expérience utilisateur interrompue, ce qui augmente leurs chances de tomber dans le tunnel de conversion.

Pour résoudre ce problème, OneLink peut reconnaître les clics dans WeChat et charger une page d'accueil dédiée demandant à l'utilisateur de cliquer sur le bouton Options, puis sur **Ouvrir dans le navigateur**. Cette opération ouvre l'URL de redirection définie dans la configuration du template OneLink.

<Image align="center" alt="WeChat_a.jpg" src="https://files.readme.io/49c03a10d458f6ce71fd6448e922294682ac9239775534c6264c29151ec1ea6d-30192900489105.jpg" />

Si la langue WeChat de l'utilisateur est le chinois, OneLink génère une version traduite de la page d'accueil :

<Image align="center" alt="WeChat_b.jpg" src="https://files.readme.io/502ef821a122459ab991f2a507c720f25fcac7129eb647a01290e8cabfa7a34e-30192887085841.jpg" />

</Accordion>

<div id="why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview" />

<Accordion title="Pourquoi les utilisateurs Android qui ont installé l'app sont-ils redirigés vers une URL web, et non vers l’app lorsqu’ils cliquent sur un lien Facebook Webview ?">

Il est généralement possible d’ouvrir l’application et de deep linker à partir d’une publicité sur Facebook. Toutefois, si les conditions suivantes sont réunies, Facebook ne peut pas ouvrir l'application pour les utilisateurs existants à partir de l'URL OneLink. Au lieu de cela, tous les utilisateurs, y compris ceux qui utilisent l’application, sont adressés à l’URL définie dans le template OneLink, ou à la valeur du paramètre **af\_android\_urlaf\_r**, ou **af\_custom\_android\_url:**

* L'utilisateur possède un appareil mobile Android.
* Le clic sur le lien se fait dans l’app Facebook.
* Le lien mène à une page HTML qui s'ouvre en mode web Facebook (c'est à dire un site ou la page d'accueil d'une app sociale).
* La page HTML contient un lien avec un  paramètre **af\_dp** (avec un schéma d’URI) et un paramètre de redirection d’URL dans le template OneLink, ou dans un des paramètres parmi **af\_android\_url**, **af\_r** ou **af\_custom\_android\_url**.

</Accordion>

<div id="testing-faq" />

### FAQ sur les tests

<div id="how-can-i-ab-test-the-social-app-landing-page" />

<Accordion title="Comment procéder au test A/B de la page d'accueil des apps sociales ?">

La page d'accueil des apps sociales offre aux utilisateurs un lancement d'app pratique et rapide dans le cas où <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">OneLink est inclus dans les apps de réseaux sociaux.</Anchor> Vous pensez sans doute que l'ajout d'une étape au tunnel risque de faire baisser les taux de conversion. Mais en vérité, sans la page d'accueil les taux de conversion sont très faibles, car les parcours des utilisateurs sont souvent interrompus.

Si vous n'êtes pas totalement convaincu, pourquoi ne pas le tester ?

<Anchor target="_blank" href="/marketers/fr/docs/create-a-b-tests">Procédez au test A/B</Anchor> de votre lien personnalisé dans les apps de réseaux sociaux, avec et sans la page d'accueil des apps sociales.

**Pour procéder au test A/B de la page d'accueil des apps sociales :**

1. <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Créez un lien OneLink</Anchor> (appelé Link1) à utiliser dans les apps de réseaux sociaux. Ne définissez pas de page d'accueil des apps sociales pour ce lien.
2. Ajoutez le paramètre d'attribution **af\_adset**.
3. Ajoutez le paramètre d'attribution**af\_ad** avec la valeur "no lp".
4. Testez link1 en dehors des apps de réseaux sociaux et vérifiez que le lien fonctionne et lance correctement votre app.
5. Dupliquez Link1 et nommez-le Link2.
6. Modifiez la valeur du paramètre d'attribution **af\_ad** en « using lp ».
7. <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Créez la page de destination des apps sociales</Anchor> pour Link2 uniquement.
8. Publiez 2 posts différents dans **la même** app de réseaux sociaux, à l'aide de Link1 et de Link2.  
   Ne vous souciez pas du nombre différent de clics que chaque lien génère. Le KPI important ici est le taux de conversion final de chaque lien.
9. **Vérifiez les résultats du test A/B après avoir créé suffisamment de trafic.**
   1. Allez dans le tableau de bord AppsFlyer et faites défiler l'écran jusqu'au tableau **Rapport de performances agrégées**.
   2. Link1 et Link2 ont la même source média, la même campagne et le même nom d'adset. Descendez dans la hiérarchie de l'adset.
   3. Comparez les taux de conversion (et autres KPI) des utilisateurs qui ont cliqué sur Link1 ou Link2.

</Accordion>

<div id="how-can-i-bypass-the-app-selection-dialog" />

<Accordion title="Comment puis-je contourner la boîte de dialogue de sélection de l'app ?">

Si vous voyez la boîte de dialogue de sélection d'app lors du test de vos OneLink, assurez-vous de <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing">signer votre app</Anchor> même s'il s'agit d'une <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing#debug-mode">app de débogage.</Anchor> Le certificat que vous utilisez pour signer l'app est le même que celui que vous utilisez pour <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-for-deep-linking-and-deferred-deep-linking#generating-a-sha256-fingerprint">générer le fingerprint SHA256</Anchor> lors de la configuration de OneLink pour les liens d'app.

</Accordion>

<div id="deep-linking-faq" />

### FAQ sur le deep Linking

<div id="what-deep-linking-methods-should-be-implemented" />

<Accordion title="Quelles méthodes de deep linking doivent être implémentées ?">

Vos développeurs doivent implémenter la méthode de deep linking unifié (DLU) pour utiliser le deep linking. Consultez nos <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">instructions complètes sur le deep linking</Anchor>.

Les liens universels iOS et les liens d'app Android sont des **méthodes de lancement d'app qui n'établissent pas de deep link avec les utilisateurs** (cela signifie qu'elles ne les dirigent pas vers un contenu spécifique de l'app). La méthode du schéma d'URI peut lancer l'app et deep linker les utilisateurs (via le paramètre de lien personnalisé **af\_dp**), mais elle ne doit être configurée que pour le lancement de l'app. Elle est principalement utilisée comme solution de secours pour les liens universels et les liens d'app, et pour les utilisateurs qui lancent des apps avec des versions d'Android antérieures à la version 6.0.

Après le lancement de l'app à l'aide de l'une de ces méthodes, le SDK AppsFlyer fournit la valeur **deep\_link\_value** spécifiée dans le lien d'attribution personnalisé. Cette valeur doit être transmise via la méthode de deep linking unifié implémentée par vos développeurs.

</Accordion>

<div id="can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking" />

<Accordion title="Peut-on utiliser le schéma d'URI (paramètre af_dp) pour le deep linking ?">

**Oui**, mais ce n'est pas recommandé. Idéalement, il vaut mieux utiliser **deep\_link\_value** pour le deep linking, et choisir le schéma d’URI comme méthode de secours pour le lancer l'app sans deep linking (via le paramètre **af\_dp**). Cependant, si vous avez déjà configuré le schéma d’URI pour le deep linking, avec des paramètres supplémentaires inclus dans le chemin d'accès de l'URI (par exemple, superapp://param1/param2), vous n'êtes pas obligé de modifier votre configuration ou votre code existant ; le schéma d'URI continuera à fonctionner. 

**Le mieux pour ajouter des paramètres personnalisés est de passer par la page de configuration du lien personnalisé**.

</Accordion>

<div id="ios-14-faq" />

### FAQ sur IOS 14

<div id="does-onelink-deep-linking-work-for-ios-14" />

<Accordion title="Le deep linking OneLink fonctionne-t-il sous iOS 14 ?">

L'expérience des utilisateurs d'iOS 14 acquis via le deep linking de campagnes sur les ad networks et les médias propres via le DLU n'est pas affectée. La méthode héritée peut affecter le deep linking.

À des fins d'attribution/de reporting, AppsFlyer utilise l'IDFA ou l'IDFV lorsqu'il est disponible. En l’absence d'IDFA ou d'IDFV, la modélisation probabiliste peut être utilisée. Depuis IOS 14.5, la modélisation probabiliste peut être utilisée dans le cadre des médias propres, de la promotion croisée et des flux web-to-app consentis.

</Accordion>

<div id="does-onelink-deferred-deep-linking-work-for-ios-14" />

<Accordion title="Le deep linking différé OneLink fonctionne-t-il pour iOS 14 ?">

L'expérience des utilisateurs d'iOS 14 acquis via le deep linking différé de campagnes sur les réseaux publicitaires et les médias propres via le DLU n'est pas affectée. La méthode héritée peut affecter le deep linking différé.

À des fins d'attribution/de reporting, AppsFlyer utilise l'IDFA ou l'IDFV lorsqu'il est disponible. En l’absence d'IDFA ou d'IDFV, la modélisation probabiliste peut être utilisée. Depuis IOS 14.5, la modélisation probabiliste peut être utilisée dans le cadre des médias propres, de la promotion croisée et des flux web-to-app consentis. Nous conseillons aux clients qui souhaitent mettre en place un deep linking différé à partir d'ad networks et de médias propres d'utiliser le SDK AppsFlyer iOS V6.1.0 et +, et d'autoriser le consentement ATT (si nécessaire) afin d'atténuer l'impact sur l'attribution et d'offrir des temps de réponse plus rapides.

</Accordion>

<div data-zendesk-anchors="onelink-troubleshooting-guide=guide-de-d%C3%A9pannage-onelink 01H7WPYJV9CQ1J6J3PFCEQFGB0=guide-de-d%C3%A9pannage-onelink onelink-frequently-asked-questions=questions-fr%C3%A9quentes-sur-onelink 01H7WPYJV9H52P659N8JPRX2TY=questions-fr%C3%A9quentes-sur-onelink onelink-template-faq=faq-sur-les-templates-onelink 01H7WPYJV9TJRKHFZ77DFMKDDG=faq-sur-les-templates-onelink which-method-should-i-use-for-opening-apps%E2%80%94universal-links-app-links-or-uri-schemes=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9JQG66S3K7TRHMFHA=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9TV402AGAAGYARATW=remarque 01H7WPYJV9JSQ5FV73YCE3H5AF=deep-linking 01H7WPYJV9CMQAQZ56P5P2MDBV=which-operating-systems-allow-uri-schemes-to-open-the-app 01H7WPYJV975A2YS61MQM1WX4W=do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup 01H7WPYJV9GPXDP0KSQEPZXJCH=can-i-redirect-existing-users-to-a-web-page-instead-of-the-app 01H7WPYJV9A266QMK2J1K2AQXR=can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users 01H7WPYJV9DCVNRR3NNF7JMR0D=can-i-assign-an-app-to-multiple-onelink-templates 01H7WPYJV90RVHSAWA2YHBNNHA=can-i-delete-a-onelink-template 01H7WPYJV9RPNG3Z94630B789K=can-i-change-the-subdomain-in-a-onelink-template 01H7WPYJV9C0H3ZH6F6F3E43WH=can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template 01H7WPYJV9246X8821B943N9AD=can-i-use-the-same-subdomain-for-more-than-one-template 01H7WPYJVAFBS0Y56NWN8M979B=how-can-i-redirect-desktop-users 01H7WPYJVA6PWA88VD8V0B3M74=astuce 01H7WPYJVAB57R0VQAS7C0D9NK=how-can-i-redirect-chrome-os-users onelink-link-faq=faq-sur-les-liens-onelink 01H7WPYJVAPNYAQ1SH4FBX4Z9F=faq-sur-les-liens-onelink 01H7WPYJVAEQQDSJ298M8JV361=does-onelink-work-without-the-appsflyer-sdk 01H7WPYJVA8XASRX9X3QVAWYS9=what-methods-are-available-for-creating-onelink-custom-links 01H7WPYJVATBVVMEPNAVBW9ZFZ=can-onelink-custom-links-open-the-app-from-a-browser 01H7WPYJVAWJ9BFYBXM6DJ3V22=why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users fallback-urls=url-de-secours 01H7WPYJVACCGVJD1Z7ZPVG2SQ=url-de-secours 01H7WPYJVAHXE4M12X94T9C7A5=exemple 01H7WPYJVAEMX54GZAX166FPS7=remarque-1 forced-deep-linking=deep-linking-forc%C3%A9 01H7WPYJVA1W3HYYJJFQM01136=deep-linking-forc%C3%A9 01H7WPYJVAWSD03E141SZEN2J9=why-does-my-onelink-url-open-a-blank-page-in-chrome 01H7WPYJVAV93G4EGDH2A91XMP=can-i-use-onelink-for-redirection-on-brave 01H7WPYJVAJQ6FKWDK8MNZAZT3=do-onelink-custom-links-take-longer-to-load-than-other-links 01H7WPYJVAX7P2YCBV1K1DCGEJ=how-can-i-record-the-cost-per-install-when-using-onelink 01H7WPYJVAEFX5306YA4GA45FW=exemple-1 01H7WPYJVAQZJQYX3H5V8YTC27=how-can-i-prevent-parameter-forwarding-on-redirections 01H7WPYJVAYVK3A77Q35H1ENKF=how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls 01H7WPYJVA89118V5Y2DSM67Y4=are-singleplatform-custom-links-still-available 01H7WPYJVANDKXGFKYXZ6CKHSF=can-i-change-the-short-url-id-after-saving-a-link 01H7WPYJVAC2WXXY43WEYKVPYP=can-i-wrap-and-shorten-onelink-custom-links 01H7WPYJVANTMSMGZ6VP36DTV1=can-i-use-onelink-custom-links-in-emails 01H7WPYJVAE0TSRPPTD21X9Q4V=how-do-users-get-redirected-to-their-regional-app-store 01H7WPYJVA4W7YFMQD4HEE313P=why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain h_01HAKSWWMSHVW9KFWA34XGXWN2=can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link onelink-parameter-faq=faq-sur-les-param%C3%A8tres-onelink 01H7WPYJVAGRVWHRVMZVQG1ZVE=faq-sur-les-param%C3%A8tres-onelink 01H7WPYJVBCS3JZ98FYMAPY2YT=what-parameters-are-mandatory-for-onelink-custom-links 01H7WPYJVBCD7GG37JZTF919YQ=can-parameters-be-appended-to-the-short-url 01H7WPYJVB15Q3YAVJ8M7EQ1FW=exemple-2 01H7WPYJVBNTKJM3F72ZEZG32Z=what-custom-media-source-names-can-i-use 01H7WPYJVB25VGB37D3DZ2J786=what-attribution-parameters-can-be-added-to-a-onelink 01H7WPYJVBSQBR8E9NY0GJ3APT=are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data 01H7WPYJVB3CCB838A7N6K932G=are-parameter-names-case-sensitive integrated-partner-faq=faq-sur-les-partenaires-int%C3%A9gr%C3%A9s 01H7WPYJVB8ZZSKFT1V01EN6QF=faq-sur-les-partenaires-int%C3%A9gr%C3%A9s 01H7WPYJVBCQNPTEZPM8KFE6YX=can-i-use-onelink-in-social-apps-unpaid 01H7WPYJVBTBQKK50JR179S7MW=can-i-use-onelink-with-ad-networks-paid 01H7WPYJVBJ0DX0MZPGXYF76EP=important- 01H7WPYJVBB9KJRZQTFZDG7NDK=exemple-3 01H7WPYJVB60DFMHN8PCVFC5S9=how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps 01H7WPYJVB94NGD94MW4HYDB5S=can-i-use-onelink-on-instagram 01H7WPYJVBT5PJHVAFD1TY6CDY=can-i-use-onelink-for-redirection-on-wechat 01H7WPYJVB05C8BXKRG0WGBJ8P=why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview testing-faq=faq-sur-les-tests 01H7WPYJVC1PJJDA0GGT1DVVCF=faq-sur-les-tests 01H7WPYJVCQ89S3R4X1111TRGZ=how-can-i-ab-test-the-social-app-landing-page 01H7WPYJVC20TXWKRB89XFTK1N=how-can-i-bypass-the-app-selection-dialog deep-linking-faq=faq-sur-le-deep-linking 01H7WPYJVCTM39HKCG9JN03BN6=faq-sur-le-deep-linking 01H7WPYJVCZMRN53QG5JNSB8MP=what-deep-linking-methods-should-be-implemented 01H7WPYJVC6BXRJGTJBY6KG8JX=can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking ios-14-faq=faq-sur-ios-14 01H7WPYJVCVCVWHJW4RH85KC40=faq-sur-ios-14 01H7WPYJVCFANQQ9T27M2YGGBD=does-onelink-deep-linking-work-for-ios-14 01H7WPYJVCBC9YMBQ6TV1B2SBV=does-onelink-deferred-deep-linking-work-for-ios-14" />

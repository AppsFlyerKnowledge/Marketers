---
title: Domaines de marque
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2023-11-20T14:49:36Z'
  id: 360002329137
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/360002329137
---
> **En bref :** les annonceurs qui utilisent les liens OneLink peuvent les marquer de leur propre domaine. Ceci améliorera les performances des campagnes et augmentera l'exposition de la marque.

![Branded_1__3_.jpg](https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png)

<div id="branded-domains" />

## Domaines de marque

* Les domaines de marque sont utilisés pour estampiller les liens d'attribution avec votre marque et votre domaine. Cf exemple ci-dessous :
  * OneLink : abcdef.onelink.me
  * Marque abcdef.com
  * Sous-domaine : ex. app
  * Implémentez des domaines de marque tout en utilisant votre domaine complet. Le lien d'attribution sera cliquer.abcdef.com.
* Les domaines de marque augmentent les performances des campagnes, car :
  * Ils renforcent la confiance : capitalisez sur votre marque, proposez une identité cohérente, simplifiez les parcours utilisateur et améliorez vos taux CTR.
  * Ils permettent au deep linking d'utiliser votre marque.
  * Ils sont faciles à implémenter et fonctionnent comme les OneLinks.
  * Ils améliorent la visibilité de votre marque : vos liens de campagne portent le nom de votre marque, ils ne sont pas génériques.
  * Autorisez les e-mails pour qu'ils ne soient pas considérés comme des spams à cause du lien qui ne correspond pas à l'e-mail de l'expéditeur.

<div id="principles-of-implementation" />

### Principes de mise en œuvre

Les liens de marque sont implémentés en associant un domaine complet défini dans votre Domain Name System (DNS) à un sous-domaine OneLink (la destination CNAME AppsFlyer). Pour ce faire, vous utilisez les paramètres standard de votre DNS et configurez un domaine de marque dans AppsFlyer. Vous devrez également apporter quelques petites modifications à votre app pour qu'elle prenne en charge les domaines de marque.

Vous devrez faire appel au développeur d'app et à l'admin DNS (généralement un membre de votre équipe informatique ou de votre hébergeur DNS).

Différents domaines complets peuvent être associés à un seul sous-domaine OneLink. Il est donc possible d'avoir plusieurs marques qui utilisent le même sous-domaine OneLink.

<div id="setting-up-branded-domains" />

### Configurer les domaines de marque

Suivez toutes les étapes de la procédure pour configurer un domaine de marque.

|  | Responsable | Action | Remarques |
| --- | --- | --- | --- |
| 1 | Le marketer et l'admin DNS | [Configurer un lien de marque dans AppsFlyer](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | L'admin DNS (généralement un membre de votre équipe informatique ou de votre hébergeur DNS) doit définir le domaine complet (ie l'hôte) puis définir un enregistrement CNAME tel qu'indiqué dans les instructions. |
| 2 | Développeur | [Configurer des domaines de marque dans l'app](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | De petites modifications sont apportées au code de l'app. |
| 3 | Marketeur | [Utiliser et tester des domaines de marque](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| Options | Marketeur | [Modifier et supprimer des domaines de marque](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

<div id="procedures" />

### Procédures

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="Configurer un domaine de marque dans AppsFlyer">

Pour configurer un domaine de marque, vous devez associer un domaine complet de votre DNS à un sous-domaine OneLink de AppsFlyer, comme illustré ci-dessous.

**Domaine de marque pointant vers les serveurs AppsFlyer**

![Branded2__3_.jpg](https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png)

**Avant de commencer :**

* Choisissez un nom de domaine complet, comme app.abcdef.com où abcdef.com est votre marque.
  * Le sous-domaine, par exemple app, peut également être personnalisé.
* Demandez à l'admin DNS de créer le domaine complet (c'est à dire l'hôte).
* Demandez à l'admin DNS de définir un enregistrement CNAME pour que le domaine complet (domaine de marque) pointe vers l'URL spécifiée (soit l'hôte AppsFlyer). Cf schéma ci-dessus qui illustre un domaine de marque pointant vers les serveurs AppsFlyer.

**Pour mapper votre domaine complet à un sous-domaine OneLink :**

1. Allez dans **Experiences et Deep Linking** > **Domaines de marque.**
2. Cliquez sur **+ Nouveau domaine de marque**.
3. Dans le champ **Domaine de marque**, entrez votre domaine complet tel que défini dans votre DNS. Par exemple **cliquer.abcdef.com**  
   N'inscrivez pas de point après le domaine.
4. Sélectionnez le sous-domaine OneLink dans la liste qui s'ouvre.  Si aucune liste ne s’affiche, vous devez créer un template OneLink, celui-ci fournira un sous-domaine par défaut.
5. Cliquez sur **Suivant**.
6. Créez un enregistrement CNAME :
   * Si votre domaine a été correctement dirigé vers la destination CNAME AppsFlyer, le message « AppsFlyer CNAME trouvé » s'affiche.
   * Si le CNAME est introuvable, copiez la destination CNAME AppsFlye, transmettez-la à votre admin DNS et demandez-lui de s’assurer que votre domaine complet pointe bien vers la destination CNAME. Votre domaine complet doit forcément pointer vers une destination CNAME AppsFlyer. Dans le cas contraire, le domaine de marque sera bien créé mais il ne sera pas fonctionnel.  Si vous utilisez votre domaine de marque avec des ESP, sélectionnez **Utiliser le domaine de marque pour une configuration ESP** avant même de copier la destination CNAME..
7. Cliquez sur **Terminer**.  
   Vous pouvez maintenant créer de nouveaux liens avec votre domaine de marque en vous basant sur le template OneLink.

**Remarque** :

* Si vous avez déjà créé des liens sans le domaine de marque à partir de votre template OneLink, ils continueront de fonctionner.
* Cela peut demander jusqu’à 24 heures pour qu’un nouveau domaine de marque entre en activité.
* Si vous ne créez pas d’enregistrement CNAME dans les 7 jours suivants, votre domaine de marque sera expiré. Vous devez actualiser votre domaine de marque avant de pouvoir l'utiliser. Pour l'actualiser : 
  1. Allez dans **Experiences et Deep Linking** > **Domaines de marque.**
  2. Ouvrez le domaine de marque que vous souhaitez actualiser.
  3. Cliquez sur **Actualiser**.
  4. Créez un enregistrement CNAME.

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="Configurer des domaines de marque dans l'app">

* Utilisez les versions suivantes du SDK  :  
  * Android V4.10.1 et +
  * iOS V4.10.1 et +
  * Le référant d'invitation d'un utilisateur (inviter un ami) nécessite le SDK V5.2.0 et + pour iOS et Android

**Recommandations concernant l'implémentation du SDK de domaines de marque**

* Lorsque le deep linking est réalisé à travers un domaine de marque, le SDK AppsFlyer ne peut pas obtenir de données de conversion pour les installations et pour le deep linking.
* Pour contourner ce problème, le développeur doit utiliser l'API de SDK `setOneLinkCustomDomain` pour Android, et `oneLinkCustomDomains` pour IOS.
* Cette API envoie une requête au domaine, elle obtient le domaine de OneLink qui lui est associé, puis finalise le OneLink.

<Tabs>
<Tab title="Android">

Pensez à mettre à jour <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">intent-filter</Anchor> dans le manifeste pour inclure le domaine de votre marque en paramétrant android:host.

Utilisez cette API avant d'initialiser le SDK dans la classe d'applications globale Android <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">.</Anchor>

**Exemple**

```java
public class AFApplication extends Application {

    @Override
    public void onCreate() {
    super.onCreate();

      // Set branded link domain. Don't include https:// as part of the domain. 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

Si vous avez plusieurs domaines de marque, transmettez-les tous à l'API pour être sûr d'obtenir toutes les données de conversion et de pouvoir toujours créer un deep link dans l'application.

**Exemple**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="iOS">

<Tabs>
<Tab title="Objective C">

Utilisez l'API dans AppDelegate.m, au sein de la méthode didFinishLaunchingWithOptions :

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** APPSFLYER INIT **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

Si vous avez plusieurs domaines de marque, transmettez-les tous à l'API pour être sûr d'obtenir toutes les données de conversion et de pouvoir toujours créer un deep link dans l'application.

**Exemple**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

L'API doit être utilisée dans le fichier AppDelegate.swift, au sein de la méthode didFinishLaunchingWithOptions :

```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions 
        launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
          AppsFlyerLib.shared().appsFlyerDevKey = "6CQi4Be6Zs9oNLsCusPbUL"
          AppsFlyerLib.shared().appleAppID = "340954504"
          AppsFlyerLib.shared().oneLinkCustomDomains = ["example.com"]
          //...
          //...
   }
```

Si vous avez plusieurs domaines de marque, vous pouvez les transmettre à l'API sous la forme d'une série de chaînes. Ainsi, quel que soit le domaine de marque utilisé, vous serez assuré d'obtenir toutes les données de conversion et de pouvoir toujours créer un deep link dans l'application.

**Exemple**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="Utiliser et tester des domaines de marque">

**Conditions préalables** :

Avant d'utiliser et de tester les domaines de marque, suivez l'intégralité de la [marche à suivre pour les domaines de marque](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app).

**Pour créer et tester des domaines de marque :**

1. <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">Créez un lien OneLink</Anchor> en utilisant le template OneLink mappé au domaine de marque.
2. Copiez le lien d'attribution personnalisé dans un éditeur de texte.
3. Le lien d'attribution personnalisé est composé d'un sous-domaine OneLink, d'un ID OneLink et d'un ID de lien personnalisé. Remplacez le sous-domaine OneLink par le domaine complet du domaine de marque. Exemple : 

| Lien d'attribution personnalisé | Domaine de marque |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **cliquer.abcdef.com**/A1bc/dc1234ef |

4. Utilisez le lien de marque pour <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">tester les installations ainsi que le deep linking</Anchor>.
5. Si vous utilisez des rapports de données brutes pour le test, le champ «URL d'origine» sera rempli par les liens de marque.

</Accordion>

<div id="editing-and-deleting-branded-domains" />

<Accordion title="Modifier et supprimer des domaines de marque">

La modification vous permet de changer le mappage d'un domaine complet pour qu'il soit associé à un autre sous-domaine OneLink. Il ne sera pas demandé de définir de CNAME.

> ❗️ **Attention**
>
> Modifier le domaine de marque d'une campagne active peut altérer ou interrompre le bon fonctionnement des liens.

**Pour modifier un mappage de domaine de marque :**

1. Allez dans **Experiences et Deep Linking** > **Domaines de marque.**
2. Ouvrez le domaine de marque que vous souhaitez modifier.
3. Cliquez sur **Modifier.**

**Pour supprimer un mappage de domaine de marque :**

* Contactez votre CSM AppsFlyer ou écrivez à <Anchor target="_blank" href="hello@appsflyer.com">hello@appsflyer.com</Anchor>.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## Dépannage, caractéristiques et seuils

<div id="troubleshooting" />

<Accordion title="Dépannage">

| Symptôme | Cause/solution |
| --- | --- |
| Impossible de mapper le domaine de marque avec un template OneLink | <ul><li>**Nom de domaine non valide :** lors du mappage d'un domaine de marque avec un template OneLink, AppsFlyer cherche à vérifier que le lien de marque possède un nom de domaine valide. Un nom de domaine valide aura le format cliquer.abdef.com</li><li>**Le domaine de marque est déjà mappé** : un domaine complet ne peut être mappé qu'une seule fois.</li></ul> |
| Le domaine de marque ne se deep linke pas vers l'app | <ul><li>[Vérifiez que le domaine de marque fonctionne bien](/docs/brand-onelink-with-your-domain#troubleshooting)</li><li>**Vérifiez le CNAME** : un enregistrement CNAME doit forcément partir de votre domaine de marque et pointer vers AppsFlyer.</li><li>**Vérifier les paramètres de deep linking pour le template OneLink** : un problème dans les paramètres de deep linking OneLink est possible. Pensez à bien configurer le deep linking pour OneLink :</li><li>**Modification du mappage OneLink**: vous pouvez modifier le domaine de marque et le mapper vers un autre OneLink. Si le OneLink nouvellement mappé a des paramètres de deep linking différents (ou aucun), le deep linking risque de ne pas fonctionner.</li></ul> |
| Aucune installation n'est mesurée depuis les domaines de marque | <ul><li>**Vérifiez les paramètres du template OneLink** : le sous-domaine OneLink utilisé pour mapper le domaine de marque doit être correctement associé aux différentes apps.</li><li>**Le sous-domaine OneLink a été modifié :** si vous mappez un domaine de marque avec un template OneLink et que le sous-domaine OneLink est modifié, cela peut avoir des effets sur l'attribution.</li><li>**Pensez à implémenter  :** l'API setOneLinkCustomDomain dans l'application.</li></ul> |
| Aucun réengagement n'est enregistré depuis les domaines de marque | Vérifiez que les éléments suivants sont actifs et correctement définis :<ul><li>Configurer le deep linking avec OneLink.</li><li>L'app s'appuie sur l'API SDK dédiée [setOneLinkCustomDomain](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer).</li><li><Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#retargeting-settings">Le retargeting est activé dans les paramètres de l'app</Anchor>.</li></ul> |
| Durant la phase de configuration du domaine de marque, le message **Domaine inexistant** s'affiche | <ol><li>Contactez votre admin DNS pour qu'il lance les vérifications.</li><li>Attendez que l'admin DNS vous confirme que le domaine est bien enregistré.</li><li>Cliquez sur **Vérifier**.</li></ol> |
| Durant la phase de configuration du domaine de marque, le message **CNAME AppsFlyer introuvable** s'affiche | <ol><li>Demandez à l'admin DNS de définir un enregistrement CNAME pour que le domaine complet (domaine de marque) pointe vers l'URL spécifiée (soit l'hôte AppsFlyer). Cf schéma de cette section qui illustre un lien de marque pointant vers les serveurs AppsFlyer.</li><li>Attendez que l'admin DNS vous confirme que le CNAME est bien actif.</li></ol> |
| Erreur **route\_not\_found** lors du chargement d'une page de domaine de marque | Les domaines de marque n'incluent ni le template ni les paramètres. Lorsque vous utilisez un domaine de marque, vous devez ajouter le template ou les paramètres à la fin de l'URL du domaine de marque.<br /><br />Ex : si 'click.abcdef.com' est votre domaine de marque et que vous utilisez '**click.abcdef.com'** tout seul, vous obtiendrez **route\_not\_found\_error**.<br /><br />Vous devez forcément ajouter les paramètres ou templates à la fin. Ex : click.abcdef.com **/A1bc/dc1234ef** |
| Erreur **err\_cert\_authority\_invalid** lors du chargement d'une page de domaine de marque | Cette erreur indique que votre domaine de marque n'a pas de certificat HTTPS valide car l'autorité de certification n'est pas reconnue. Comme AppsFlyer certifie vos domaines de marque avec Let's Encrypt, le problème est certainement dû au fait que Let's Encrypt n'est pas reconnue comme autorité de certification (CA) valide selon les enregistrements DNS CAA (Certification Authority Authorization) de votre domaine.<br /><br />**Solution** Veuillez procéder comme suit :<ol><li>Déterminez si votre domaine reconnaît Let's Encrypt comme CA en passant par un service comme <Anchor target="_blank" href="https://www.entrust.com/resources/certificate-solutions/tools/caa-lookup">celui-ci</Anchor>.</li><li>Demandez à vos admins système de mettre à jour les enregistrements CAA de votre domaine pour inclure Let's Encrypt comme autorité de certification autorisée.</li></ol> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Oui ✓ / Non **x** | Remarques |
| --- | --- | --- |
| Accès du ad network | **X** |  |
| Autorisations de l'agence | **X** | Les agences ne peuvent pas accéder à la section Domaines de marque pour créer des domaines de marque. Elles peuvent cependant créer des liens personnalisés OneLink avec un sous-domaine de domaine de marque. |
| Transparence de l'agence | **X** |  |
| Fuseau horaire spécifique à l'app | S/O |  |
| Devise spécifique à l'app | S/O |  |
| Restrictions liées aux caractères | S/O | Lorsque vous saisissez votre domaine de marque, le dernier caractère ne peut pas être un point ("."). |
| Limitations de taille | S/O |  |
| Limitation de taux | ✓ | Les certificats SSL/HTTP des domaines de marque sont générés par AppsFlyer via <Anchor target="_blank" href="https://letsencrypt.org/">Let's Encrypt</Anchor>, avec un nombre de nouveaux certificats limité à 50 par semaine et par domaine. |
| Données organiques | ✓ |  |
| Données non organiques | ✓ |  |
| Actualisation des données | N/A |  |
| Données historiques | ✓ |  |
| Accès utilisateur du compte | ✓ |  |
| HTTP | **X** | Le protocole HTTP n'est pas pris en charge par les liens de marque. Vous devez utiliser HTTPS. |

</Accordion>

<div data-zendesk-anchors="branded-domains=domaines-de-marque h_01HFM51V4PE53FQAED68V8Q834=domaines-de-marque principles-of-implementation=principes-de-mise-en-%C5%93uvre h_01HFM51V4PPJXMCSV5ZVDPT49M=principes-de-mise-en-%C5%93uvre setting-up-branded-domains=configurer-les-domaines-de-marque h_01HFM51V4PH58ZA4ZXHP5J6K2W=configurer-les-domaines-de-marque procedures=proc%C3%A9dures h_01HFM51V4PWWX7TBCHFMPR3QVB=proc%C3%A9dures h_01HFM51V4PA23K6HR2Y1D6D31Q=set-up-a-branded-domain-in-appsflyer h_01HFM51V4PP0NQHVHTKB86250R=set-up-branded-domains-in-the-app h_01HFM51V4PN0FPEDNAF0Q1QS8P=using-and-testing-branded-domains h_01HFM51V4PFFXZ8RFBZNMZGXXK=editing-and-deleting-branded-domains h_01HFM51V4PVZE7FAFN2EYS7P6E=attention troubleshooting-traits-and-limitations=d%C3%A9pannage-caract%C3%A9ristiques-et-seuils h_01HFM51V4PH4YM13DVXENRWF2E=d%C3%A9pannage-caract%C3%A9ristiques-et-seuils h_01HFM51V4PJNHZTD97X75WPN98=troubleshooting h_01HFM51V4QQ2TZQMJ2ATNDG91F=traits-and-limitations" />

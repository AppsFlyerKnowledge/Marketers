---
title: Configurer l'authentification SSO avec votre prestataire d'identité (IdP)
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - login security
    - SSO
    - SSO verification
    - SSO certificate
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
    - Ad Networks
  created_at: '2020-11-02T10:50:55Z'
  edited_at: '2024-08-21T13:55:24Z'
  id: 360015017198
  locale: fr
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/fr/articles/360015017198
---
> **En bref :** En intégrant AppsFlyer à votre prestataire d'identité (IdP), les utilisateurs du compte AppsFlyer peuvent se connecter à AppsFlyer en utilisant l'authentification unique (SSO). Découvrez l'authentification SSO, comment configurer le SSO avec votre IdP et trouvez les réponses aux questions les plus fréquentes.

> 📘 **Remarque**
>
> **Pour les utilisateurs disposant de plusieurs comptes :**
>
> Lors du passage d'un compte configuré pour la connexion via SSO à un compte configuré pour la connexion via nom d'utilisateur et mot de passe ou via la connexion Google, vous devrez vous connecter en utilisant les identifiants du compte ou via le processus de connexion Google.

## Configurer le SSO avec votre IdP

Le processus de configuration utilisant le protocole SAML2.0 se fait en trois étapes. L'[étape 1](#step-1-configure-the-idp-platform) comprend des procédures détaillées pour les IdP suivants :

* JumpCloud
* Okta
* OneLogin
* Ping Identity

<div id="step-1-configure-the-idp-platform" />

<Accordion title="Étape 1 : Configurer la plateforme IdP">

La première étape consiste à configurer le côté IdP.

#### Procédures de configuration des principaux IdP

Voir les procédures détaillées pour configurer l'authentification SSO dans l'un des IdP suivants :

* <Anchor target="_blank" href="/marketers/fr/docs/configure-appsflyer-sso-in-jumpcloud">JumpCloud</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/configure-appsflyer-sso-in-okta">Okta</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/configure-appsflyer-sso-in-onelogin">OneLogin</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/configure-appsflyer-sso-in-ping-identity">Ping Identity</Anchor>

#### Aperçu de la configuration pour d'autres plate-formes IdP

Aperçu du processus de configuration sur d'autres plate-formes IdP :

* Une application AppsFlyer est créée sur la plateforme IdP, basée sur le protocole SAML 2.0, et le [certificat d'authentification AppsFlyer](#the-authentication-certificate) est implémenté dans la plate-forme IdP.
* Les utilisateurs sont affectés à la nouvelle app AppsFlyer
* Le certificat IdP ou les métadonnées sont récupérés pour être utilisés dans AppsFlyer (à l'[étape 2)](#step-2-complete-the-configuration-at-appsflyer).

> 📘 **Remarque**
>
> * Lors de l'attribution des utilisateurs au prestataire d'identité (IdP), assurez-vous d'utiliser la même adresse e-mail que dans AppsFlyer afin que chaque utilisateur sur les deux plate-formes ait la même adresse e-mail.
> * Les <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">métadonnées d'AppsFlyer</Anchor> contiennent :
>   * Certificats de cryptage et de signature
>   * ID d'entité
>   * URL de rappel

#### Configurer l'URL de rappel

La méthode par défaut pour authentifier les utilisateurs entrant dans AppsFlyer est celle de l'IdP. Cela signifie que les utilisateurs sont dirigés vers AppsFlyer à partir du plugin ou de la page web d'authentification IdP.

**Utilisez le lien suivant pour authentifier les utilisateurs à partir de l'IdP :** `https://hq1.appsflyer.com/auth/sso-callback/`

Exemple d'ID de compte AppsFlyer : `acc-xxxxxx`. Pour obtenir votre ID de compte, contactez votre CSM.

> 📘 **Remarque**
>
> Les utilisateurs peuvent également entrer dans AppsFlyer via la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">page de connexion AppsFlyer SSO</Anchor> en cliquant sur **Connexion avec SSO** et en saisissant leur adresse e-mail. Ils seront dirigés vers l'IdP pour l'authentification, puis redirigés vers la page d'accueil d'AppsFlyer.
>
> <Image alt="AppsFlyer_login_page.png" src="https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png" width="215px" />

</Accordion>

<div id="step-2-complete-the-configuration-at-appsflyer" />

<Accordion title="Étape 2 : Terminer la configuration sur AppsFlyer">

Après avoir configuré la plate-forme IdP, retournez dans AppsFlyer pour terminer la configuration.

1. Dans la barre supérieure, ouvrez le menu du compte (liste déroulante de l’adresse e-mail) > **Centre de sécurité.**
2. Sous **Sécurité de connexion renforcée**, sélectionnez **Configurer la méthode de connexion**.
3. Dans la section **Single sign-on (SSO)**, à côté de **Télécharger le certificat IdP SSO**, cliquez sur **Ajouter.**
4. Ajouter les métadonnées IdP SSO de l'une des manières suivantes :
   * **Adresse URL :** Collez l'URL que vous avez copiée depuis la plate-forme IdP à l'[étape 1.](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-1-configure-the-idp-platform)
   * **Télécharger le fichier :** Télécharger le fichier que vous avez téléchargé de la plateforme IdP à l'[étape 1](#step-1-configure-the-idp-platform)  

     <Image alt="IdP_SSO_certificate__1_.png" src="https://files.readme.io/9830320945234cd4f069356c1ff0c7c29d26b2cb00e422a515d98d2035a5d3f2-17233244732817.png" width="443px" />
5. Cliquez sur **Importer**, puis sur **Enregistrer.**
6. [Facultatif] **Forcer la connexion SSO :** En cochant cette case, vous vous assurez que les utilisateurs se connectent via SSO et non avec leur nom d'utilisateur et leur mot de passe.  
   **Remarque :**
   * Garder l'option**Forcer la connexion SSO** sélectionnée est la méthode recommandée pour assurer une connexion plus sécurisée. Cela signifie que les utilisateurs essayant de se connecter sont authentifiés par le prestataire d'identité (IdP) et ne peuvent pas se connecter uniquement avec leur nom d'utilisateur et leur mot de passe.
   * L'option **Forcer la connexion SSO** est désactivée après l'activation et enregistré le bouton **Authentification unique.** Cela signifie que, que l'option **Forcer la connexion SSO** soit sélectionné ou non, elle ne peut pas être modifiée. [Voir comment revenir à cette option](/docs/set-up-sso-authentication-with-your-identity-provider-idp#how-can-i-unselect-the-force-sso-login-option)
7. Activez l'**authentification unique** et cliquez sur **Enregistrer.**

[![idp](https://files.readme.io/82be48b1657ddb9f11ddb578af013d88354da5ab2d4643906773ae755ccc4595-17233244738705.png)](https://files.readme.io/82be48b1657ddb9f11ddb578af013d88354da5ab2d4643906773ae755ccc4595-17233244738705.png)

</Accordion>

<div id="step-3-test-the-sso-process" />

<Accordion title="Étape 3 : Tester le processus SSO">

Après avoir terminé la configuration du SSO sur les deux plateformes — le fournisseur d'identité (IdP) et AppsFlyer — assurez-vous que les utilisateurs peuvent se connecter à AppsFlyer via l'**une ou l'autre** des [méthodes de rappel d'URL](#configurer-lurl-de-rappel) : votre IdP ou le fournisseur de services (AppsFlyer), mais pas les deux.

#### Tester l'authentification via votre IdP

Si vous avez configuré l'authentification pour vous connecter via votre IdP, vérifiez que les utilisateurs peuvent entrer dans AppsFlyer à partir du plugin IdP ou de la page web :

1. Si vous êtes connecté à AppsFlyer et à l'IdP, déconnectez-vous.
2. Ouvrez une page web en mode incognito.
3. Allez sur la page web de votre IdP. Comme vous n'êtes pas connecté à l'IdP, vous devez passer par un processus d'authentification. Se connecter avec l'utilisateur concerné.
4. Recherchez et sélectionnez AppsFlyer. Vous êtes dirigé vers la page d'accueil d'AppsFlyer. Cela indique que le processus s'est déroulé avec succès.

#### Testez l'authentification via votre fournisseur de services (AppsFlyer)

Si vous avez configuré le flux d'authentification pour vous connecter via votre fournisseur de services (AppsFlyer), vérifiez que les utilisateurs peuvent entrer dans AppsFlyer en utilisant leur e-mail :

<Image alt="log_in_to_af_by_email2.png" src="https://files.readme.io/ae22ff9ba0216f54bee4cea82ed7d35cea656a68e30c0a0e4f549b1855ec7cfd-17233244746257.png" width="245px" />

1. Si vous êtes connecté à AppsFlyer et à l'IdP, déconnectez-vous.
2. Ouvrez une page web en mode incognito.
3. Allez sur la <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">page de connexion AppsFlyer</Anchor> et cliquez sur **Connexion avec SSO.**
4. Saisissez l’e-mail correspondant et cliquez sur **Continuer.** Vous êtes maintenant dirigé vers l'IdP pour l'authentification.
5. Après l'authentification IdP, vous êtes redirigé vers AppsFlyer en tant qu'utilisateur connecté. Cela indique que le processus s'est déroulé avec succès.

</Accordion>

## À propos de l'authentification SSO

Découvrez le processus de connexion à AppsFlyer via l'authentification unique (SSO) avec votre prestataire d'identité (IdP).

<div id="what-is-sso" />

<Accordion title="Qu'est-ce que l'authentification SSO ?">

Le SSO est une méthode d'authentification qui permet aux utilisateurs d'accéder à plusieurs apps, systèmes ou plateformes indépendants en se connectant une seule fois via votre prestataire d'identité (par exemple, Okta, Azure AD ou OneLogin). L'ajout d'AppsFlyer à votre IdP permet à vos utilisateurs de se connecter à AppsFlyer directement à partir de votre IdP par le biais d'un processus d'authentification unique (SSO). Cela permet à vos utilisateurs de se connecter automatiquement avec une **authentification** plus **sûre** en utilisant une seule série d'informations d'identification.

</Accordion>

<div id="how-does-sso-authentication-work" />

<Accordion title="Comment fonctionne l'authentification SSO ?">

La plateforme AppsFlyer prend en charge la vérification SSO en utilisant le protocole SAML2.0. En implémentant le certificat d'authentification d'AppsFlyer dans votre IdP SAML 2.0, votre IdP génère un jeton avec les données de l'utilisateur authentifié. Le même processus est effectué de votre IdP à AppsFlyer — leur jeton est implémenté dans AppsFlyer.

</Accordion>

<div id="the-authentication-certificate" />

<Accordion title="Le certificat d'authentification">

AppsFlyer fournit un certificat de cryptage pour crypter les données et signer la demande SSO. Vous pouvez choisir le certificat à utiliser :

* **Certificat signé par AppsFlyer :** Un certificat AppsFlyer (document .crt). Vous pouvez obtenir ce certificat à partir de l'<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">URL des métadonnées AppsFlyer</Anchor> (voir ci-dessous).
* **Certificat signé par l'autorité de certification :** Un certificat AppsFlyer **signé par Amazon**. Pour obtenir ce certificat, contactez votre CSM.

#### Création du fichier de certificat AppsFlyer

Pour créer un fichier de certificat, vous devez créer un fichier contenant la clé de chiffrement. Cela se fait en deux étapes :

1. Obtenez les données nécessaires.
2. Créez un fichier texte et saisissez les données.

**1. Obtention des données**

Vous pouvez obtenir les données relatives au fichier de certificat soit à partir du centre de sécurité, soit via l'URL des métadonnées :

**Dans le centre de sécurité AppsFlyer :**

1. Dans la barre supérieure, ouvrez le menu du compte (adresse e-mail de l'administrateur) > **Centre de sécurité.**
2. Sous **Sécurité de connexion renforcée**, sélectionnez **Configurer la méthode de connexion**.
3. Dans la section **Single sign-on (SSO)** , près de **Copier le dernier certificat**, cliquez sur **Afficher**.
4. Copiez la clé de cryptage.

**À partir de l'URL des métadonnées :**

1. Ouvrez l'URL <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">des métadonnées d'AppsFlyer</Anchor> et trouvez `use="encryption"`.
2. Copiez les données de l’élement `X509Certificate`, de l’élément `use="encryption"` (voir les données de l'élément surlignées dans l'image ci-dessous).

![appsflyer certificate-signing.jpg](https://files.readme.io/989a2a99c54add8a3879cd2f5b4f20121f97f53b103c1a3f53c37d5eafaaa144-24887540886929.jpg)

<span id="h_01HVK231WJFS9YWNHJJR18RXBF"></span>**2. Création du fichier texte du certificat :**

Après avoir obtenu les données requises, créez un fichier texte contenant les données, comme décrit ci-dessous :

1. Collez les données que vous avez copiées dans un nouveau fichier texte.
2. Insérez "`-----BEGIN CERTIFICATE-----`" au début du fichier.
3. Ajoutez "`-----END CERTIFICATE-----`" à la fin du fichier.
4. Enregistrez le fichier texte avec une extension `.CRT` ou `.PEM.`

> 📘 **Remarque**
>
> Certains sites web en ligne offrent la possibilité de copier et de coller le certificat X.509 pour vérifier que le format est correct.

</Accordion>

<div id="considerations" />

<Accordion title="Attention">

* **Conditions minimum :** Les utilisateurs doivent être configurés dans les deux systèmes (AppsFlyer et l'IdP) en utilisant le même e-mail.
* Seul un administrateur peut activer ou désactiver le SSO
* Si la fonctionnalité est configurée en mode SSO uniquement, tous les utilisateurs doivent se connecter en utilisant uniquement le SSO et des utilisateurs spécifiques ne peuvent pas être exclus.
* Il n'est pas recommandé d'activer à la fois le SSO et une autre méthode d'authentification (comme le nom d'utilisateur et le mot de passe).

</Accordion>

<div id="deactivating-sso-authentication" />

<Accordion title="Désactivation de l'authentification SSO">

En désactivant l'authentification SSO, les utilisateurs pourront se connecter en utilisant d'autres méthodes, telles que leurs noms d'utilisateur et mots de passe AppsFlyer et la méthode <Anchor target="_blank" href="/marketers/fr/docs/implementing-and-using-2fa-login">2FA.</Anchor>

1. Dans la barre supérieure, ouvrez le menu du compte (adresse e-mail de l'administrateur) > **Centre de sécurité.**
2. Sous **Sécurité de connexion renforcée**, sélectionnez **Configurer la méthode de connexion**.
3. Dans la **section SSO (Single Sign-On)**, désactivez la case **Single Sign-On**.

</Accordion>

## FAQ

Trouvez les réponses aux questions fréquemment posées sur la connexion SSO.

<div id="can-users-log-in-using-both-sso-and-2fa-methods" />

<Accordion title="Les utilisateurs peuvent-ils se connecter en utilisant à la fois les méthodes SSO et 2FA ?">

Une seule méthode de connexion de sécurité peut être utilisée à la fois, soit SSO, soit 2FA.

* **Pour activer la méthode 2FA lorsque le SSO est actif :** Désactiver d'abord le SSO, puis activer le 2FA
* **Pour activer la méthode SSO lorsque 2FA est actif :** Désactiver d'abord 2FA, puis activer le SSO

</Accordion>

<div id="why-cant-some-users-connect-using-sso" />

<Accordion title="Pourquoi certains utilisateurs ne peuvent-ils pas se connecter à l'aide du SSO ?">

Assurez-vous que tous les courriels des utilisateurs sont configurés dans les deux systèmes — dans votre IdP et dans la plate-forme AppsFlyer. Si ce n'est pas le cas, contactez votre CSM pour savoir pourquoi et trouver comment résoudre le problème. En attendant, votre CSM peut temporairement désactiver l'option **Force SSO login** afin que les utilisateurs puissent se connecter en utilisant leur e-mail et leur mot de passe.

</Accordion>

<div id="do-i-need-a-test-environment-to-test-setup-before-pushing-to-production" />

<Accordion title="Ai-je besoin d'un environnement de test pour tester l'installation avant de définir la configuration ?">

Un environnement de test n'est pas nécessaire. Suivez [l'étape 3](#step-3-test-the-sso-process) pour tester la connexion SSO, soit du côté de l'IdP, soit du côté du prestataire de services (AppsFlyer).

</Accordion>

<div id="what-should-i-do-before-the-appsflyer-certificate-expires" />

<Accordion title="Que dois-je faire avant que le certificat AppsFlyer n'expire ?">

AppsFlyer vous alertera via la plate-forme lorsque votre certificat SSO AppsFlyer est sur le point d'expirer. Suivez ces étapes pour mettre en œuvre le nouveau certificat AppsFlyer :

1. [Créez un nouveau fichier de certificat avec la clé de chiffrement mise à jour](#création-du-fichier-de-certificat-appsflyer).
2. Accédez à votre IdP et mettez en œuvre le nouveau certificat AppsFlyer.
3. Après l'implémentation, retournez à la section **Single sign-on (SSO)** , cliquez sur **Confirmation de l'implémentation du certificat**, et confirmez que vous avez mis à jour le dernier certificat AppsFlyer.

</Accordion>

<div id="how-can-i-unselect-the-force-sso-login-option" />

<Accordion title="La connexion SSO forcée est désactivée, comment puis-je l'activer ?">

Une fois que l'option **Forcer la connexion SSO** est sélectionnée et que la configuration est enregistrée, cette option est désactivée. Pour revenir en arrière et activer **Forcer la connexion SSO**, vous devrez reconfigurer l' [étape 2](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer) du processus SSO depuis le début [.](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer)

> 📘 **Remarque**
>
> La sélection de l'option **Forcer la connexion SSO** est la méthode recommandée pour renforcer la sécurité de la connexion. Cela signifie que les utilisateurs qui essaient de se connecter sont authentifiés par l'IdP et ne peuvent pas se connecter avec leur nom d'utilisateur et leur mot de passe.

</Accordion>

<div id="is-it-required-to-use-the-appsflyer-certificate-in-my-idp" />

<Accordion title="Est-il nécessaire d'utiliser le certificat AppsFlyer dans mon IdP ?">

La mise en œuvre du certificat AppsFlyer dans votre IdP est **fortement recommandée** mais n'est pas obligatoire. Certains IdP, tels que Google Workspace et Microsoft Entra ID, ne requièrent pas par défaut de certificat de fournisseur de services.

</Accordion>

## À propos de l'authentification SSO

Découvrez le processus de connexion à AppsFlyer via l'authentification unique (SSO) avec votre prestataire d'identité (IdP).

<Accordion title="Qu'est-ce que l'authentification SSO ?">

Le SSO est une méthode d'authentification qui permet aux utilisateurs d'accéder à plusieurs apps, systèmes ou plateformes indépendants en se connectant une seule fois via votre prestataire d'identité (par exemple, Okta, Azure AD ou OneLogin). L'ajout d'AppsFlyer à votre IdP permet à vos utilisateurs de se connecter à AppsFlyer directement à partir de votre IdP par le biais d'un processus d'authentification unique (SSO). Cela permet à vos utilisateurs de se connecter automatiquement avec une **authentification** plus **sûre** en utilisant une seule série d'informations d'identification.

</Accordion>

<Accordion title="Comment fonctionne l'authentification SSO ?">

La plateforme AppsFlyer prend en charge la vérification SSO en utilisant le protocole SAML2.0. En implémentant le certificat d'authentification d'AppsFlyer dans votre IdP SAML 2.0, votre IdP génère un jeton avec les données de l'utilisateur authentifié. Le même processus est effectué de votre IdP à AppsFlyer — leur jeton est implémenté dans AppsFlyer.

</Accordion>

<Accordion title="Le certificat d'authentification">

AppsFlyer fournit un certificat de cryptage pour crypter les données et signer la demande SSO. Vous pouvez choisir le certificat à utiliser :

* **Certificat signé par AppsFlyer :** Un certificat AppsFlyer (document .crt). Vous pouvez obtenir ce certificat à partir de l'<Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">URL des métadonnées AppsFlyer</Anchor> (voir ci-dessous).
* **Certificat signé par l'autorité de certification :** Un certificat AppsFlyer **signé par Amazon**. Pour obtenir ce certificat, contactez votre CSM.

#### Création du fichier de certificat AppsFlyer

Pour créer un fichier de certificat, vous devez créer un fichier contenant la clé de chiffrement. Cela se fait en deux étapes :

1. Obtenez les données nécessaires.
2. Créez un fichier texte et saisissez les données.

**1. Obtention des données**

Vous pouvez obtenir les données relatives au fichier de certificat soit à partir du centre de sécurité, soit via l'URL des métadonnées :

**Dans le centre de sécurité AppsFlyer :**

1. Dans la barre supérieure, ouvrez le menu du compte (adresse e-mail de l'administrateur) > **Centre de sécurité.**
2. Sous **Sécurité de connexion renforcée**, sélectionnez **Configurer la méthode de connexion**.
3. Dans la section **Single sign-on (SSO)** , près de Copier le dernier certificat, cliquez sur Afficher.
4. Copiez la clé de cryptage.

**À partir de l'URL des métadonnées :**

1. Ouvrez l'URL <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">des métadonnées d'AppsFlyer</Anchor> et trouvez `use="encryption"`.
2. Copiez les données de l’élement `X509Certificate`, de l’élément `use="encryption"` (voir les données de l'élément surlignées dans l'image ci-dessous).

![appsflyer certificate-signing.jpg](https://files.readme.io/989a2a99c54add8a3879cd2f5b4f20121f97f53b103c1a3f53c37d5eafaaa144-24887540886929.jpg)

**2. Création du fichier texte du certificat :**

Après avoir obtenu les données requises, créez un fichier texte contenant les données, comme décrit ci-dessous :

1. Collez les données que vous avez copiées dans un nouveau fichier texte.
2. Insérez "`-----BEGIN CERTIFICATE-----`" au début du fichier.
3. Ajoutez "`-----END CERTIFICATE-----`" à la fin du fichier.
4. Enregistrez le fichier texte avec une extension `.CRT` ou `.PEM.`

> 📘 **Remarque**
>
> Certains sites web en ligne offrent la possibilité de copier et de coller le certificat X.509 pour vérifier que le format est correct.

</Accordion>

<Accordion title="Attention">

* **Conditions minimum :** Les utilisateurs doivent être configurés dans les deux systèmes (AppsFlyer et l'IdP) en utilisant le même e-mail.
* Seul un administrateur peut activer ou désactiver le SSO
* Si la fonctionnalité est configurée en mode SSO uniquement, tous les utilisateurs doivent se connecter en utilisant uniquement le SSO et des utilisateurs spécifiques ne peuvent pas être exclus.
* Il n'est pas recommandé d'activer à la fois le SSO et une autre méthode d'authentification (comme le nom d'utilisateur et le mot de passe).

</Accordion>

<Accordion title="Désactivation de l'authentification SSO">

En désactivant l'authentification SSO, les utilisateurs pourront se connecter en utilisant d'autres méthodes, telles que leurs noms d'utilisateur et mots de passe AppsFlyer et la méthode <Anchor target="_blank" href="/marketers/fr/docs/implementing-and-using-2fa-login">2FA.</Anchor>

1. Dans la barre supérieure, ouvrez le menu du compte (adresse e-mail de l'administrateur) > **Centre de sécurité.**
2. Sous **Sécurité de connexion renforcée**, sélectionnez **Configurer la méthode de connexion**.
3. Dans la **section SSO (Single Sign-On)**, désactivez la case **Single Sign-On**.

</Accordion>

## FAQ

Trouvez les réponses aux questions fréquemment posées sur la connexion SSO.

<Accordion title="Les utilisateurs peuvent-ils se connecter en utilisant à la fois les méthodes SSO et 2FA ?">

Une seule méthode de connexion de sécurité peut être utilisée à la fois, soit SSO, soit 2FA.

* **Pour activer la méthode 2FA lorsque le SSO est actif :** Désactiver d'abord le SSO, puis activer le 2FA
* **Pour activer la méthode SSO lorsque 2FA est actif :** Désactiver d'abord 2FA, puis activer le SSO

</Accordion>

<Accordion title="Pourquoi certains utilisateurs ne peuvent-ils pas se connecter à l'aide du SSO ?">

Assurez-vous que tous les courriels des utilisateurs sont configurés dans les deux systèmes — dans votre IdP et dans la plate-forme AppsFlyer. Si ce n'est pas le cas, contactez votre CSM pour savoir pourquoi et trouver comment résoudre le problème. En attendant, votre CSM peut temporairement désactiver l'option **Force SSO login** afin que les utilisateurs puissent se connecter en utilisant leur e-mail et leur mot de passe.

</Accordion>

<Accordion title="Ai-je besoin d'un environnement de test pour tester l'installation avant de définir la configuration ?">

Un environnement de test n'est pas nécessaire. Suivez [l'étape 3](#step-3-test-the-sso-process) pour tester la connexion SSO, soit du côté de l'IdP, soit du côté du prestataire de services (AppsFlyer).

</Accordion>

<Accordion title="Que dois-je faire avant que le certificat AppsFlyer n'expire ?">

AppsFlyer vous alertera via la plate-forme lorsque votre certificat SSO AppsFlyer est sur le point d'expirer. Suivez ces étapes pour mettre en œuvre le nouveau certificat AppsFlyer :

1. [Créez un nouveau fichier de certificat avec la clé de chiffrement mise à jour](#création-du-fichier-de-certificat-appsflyer).
2. Accédez à votre IdP et mettez en œuvre le nouveau certificat AppsFlyer.
3. Après l'implémentation, retournez à la section **Single sign-on (SSO)** , cliquez sur **Confirmation de l'implémentation du certificat**, et confirmez que vous avez mis à jour le dernier certificat AppsFlyer.

</Accordion>

<Accordion title="La connexion SSO forcée est désactivée, comment puis-je l'activer ?">

Une fois que l'option **Forcer la connexion SSO** est sélectionnée et que la configuration est enregistrée, cette option est désactivée. Pour revenir en arrière et activer **Forcer la connexion SSO**, vous devrez reconfigurer l' [étape 2](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer) du processus SSO depuis le début [.](/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer)

> 📘 **Remarque**
>
> La sélection de l'option **Forcer la connexion SSO** est la méthode recommandée pour renforcer la sécurité de la connexion. Cela signifie que les utilisateurs qui essaient de se connecter sont authentifiés par l'IdP et ne peuvent pas se connecter avec leur nom d'utilisateur et leur mot de passe.

</Accordion>

<Accordion title="Est-il nécessaire d'utiliser le certificat AppsFlyer dans mon IdP ?">

La mise en œuvre du certificat AppsFlyer dans votre IdP est **fortement recommandée** mais n'est pas obligatoire. Certains IdP, tels que Google Workspace et Microsoft Entra ID, ne requièrent pas par défaut de certificat de fournisseur de services.

</Accordion>

<div data-zendesk-anchors="h_01J530X1930CMCF7XJM1XKPC74=remarque setting-up-sso-authentication=configurer-le-sso-avec-votre-idp h_01HCHG901V25TSRGRT9244384D=configurer-le-sso-avec-votre-idp h_01HCHG901VVPAQNGAYDW86CVZJ=step-1-configure-the-idp-platform configuration-procedures-for-the-main-idps=proc%C3%A9dures-de-configuration-des-principaux-idp h_01HCHG901VS7P5WS7WEC52CFKV=proc%C3%A9dures-de-configuration-des-principaux-idp configuration-overview-for-other-idp-platforms=aper%C3%A7u-de-la-configuration-pour-dautres-plate-formes-idp h_01HCHG901VPG0ZJ20XJBFPY7CD=aper%C3%A7u-de-la-configuration-pour-dautres-plate-formes-idp h_01HCHG901VH2XZS9Q0KM9D26WX=remarque-1 single-signon-url-configuration=configurer-lurl-de-rappel h_01HCHG901WDMYHFAJDBTRQG9MK=configurer-lurl-de-rappel h_01HFKMD6WPZVENX4SB65N255QR=remarque-2 h_01HCHG901W5D15T5E95FBQKB7E=step-2-complete-the-configuration-at-appsflyer h_01HCHG901WZ5GJ20HMBD6WQVVQ=step-3-test-the-sso-process testing-authentication-via-the-idp=tester-lauthentification-via-votre-idp h_01HCHG901WXSQ2VPCH2NKE63SE=tester-lauthentification-via-votre-idp testing-authentication-via-appsflyer=testez-lauthentification-via-votre-fournisseur-de-services-appsflyer h_01HCHG901W6DJ3GN6E7WFR6RNK=testez-lauthentification-via-votre-fournisseur-de-services-appsflyer about-sso-authentication=%C3%A0-propos-de-lauthentification-sso h_01HCHG901W2EMXXA3PYT1DNNRV=%C3%A0-propos-de-lauthentification-sso h_01HCHG901WD3EVKKPG8NMNWTZN=what-is-sso h_01HCHG901WVRX1MKNB0KF02PSJ=how-does-sso-authentication-work h_01HCHG901WG05TP2NJBJRDRWPN=the-authentication-certificate creating-the-appsflyer-certificate=cr%C3%A9ation-du-fichier-de-certificat-appsflyer h_01HCHG901WQQX70RQHXXXXQZSF=cr%C3%A9ation-du-fichier-de-certificat-appsflyer h_01HXFA35D93TDQQPMTZRQR2GC2=remarque-5 h_01HCHG901XZ2G7SQ0K980J6QTX=considerations h_01HCHG901XGJGY6V78XFWHPJVE=deactivating-sso-authentication h_01HCHG901XSAQ7HSGM0ZVT7B70=faq h_01HCHG901XJ77NQFVX01YZPGT2=can-users-log-in-using-both-sso-and-2fa-methods h_01HCHG901XH0ED40MK2YM1NGRP=why-cant-some-users-connect-using-sso h_01HCHG901X942E0WCBC00KRFSE=do-i-need-a-test-environment-to-test-setup-before-pushing-to-production h_01HCHG901XNNT8GA3TSP5XJC3B=what-should-i-do-before-the-appsflyer-certificate-expires h_01HCHG901XSKPTTRECJPNA09XR=how-can-i-unselect-the-force-sso-login-option h_01HCHG901XPKMP7HSJ04PY9KHW=remarque-6 h_01HYDBV18S924FNRCBSPR56CTR=is-it-required-to-use-the-appsflyer-certificate-in-my-idp" />

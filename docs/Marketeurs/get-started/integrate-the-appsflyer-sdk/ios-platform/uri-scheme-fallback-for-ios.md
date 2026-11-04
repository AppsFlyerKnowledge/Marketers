---
title: Schéma d'URI de secours pour iOS
metadata:
  keywords:
    - Advertisers
    - Redirects
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
  created_at: '2017-05-10T12:50:00Z'
  edited_at: '2024-09-26T13:10:56Z'
  id: 115002366466
  locale: fr
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/fr/articles/115002366466
---
> **En bref :** pour comprendre ce qui se passe lorsqu'un utilisateur équipé d'un appareil iOS clique sur un lien personnalisé OneLink et que Universal Links ne parvient pas à ouvrir l'application.

<div id="note" />

<div id="about-uri-fallback-for-ios" />

## À propos du schéma d'URI de secours pour iOS

* La meilleure façon d'ouvrir une app sur les appareils iOS est d'utiliser les liens universels. Depuis 2016, d’importantes restrictions du système d'exploitation ont réduit l'efficacité des schémas d'URI comme solution de secours lorsqu’un lien universel iOS échoue à ouvrir une app. Ces limitations ne sont pas liées à AppsFlyer et impactent également tout autre lien avec un schéma d’URI que vous pourriez utiliser pour ouvrir l'app.
* Par défaut, les schémas d'URI (portés comme valeur du paramètre af\_dp) ne sont utilisés que comme méthode de secours pour ouvrir l'app sur iOS sur un nombre restreint de navigateurs/plateformes.
* Avec Safari, vous pouvez essayer d'utiliser les schémas d’URI comme secours pour ouvrir les apps sur iOS en définissant les paramètres suivants dans votre URL OneLink : 
  * `af_dp` (qui porte le schéma d’URI comme valeur).
  * `af_force_deeplink=true` (qui force l'app à s'ouvrir en utilisant le schéma d’URI af\_dp). Sans ce paramètre, l'application ne s'ouvre pas en utilisant le schéma d’URI.
* Les schémas d'URI sont assez imprévisibles et ne sont donc pas pris en charge par défaut. Les utilisateurs qui cliquent sur le lien sont susceptibles d'être redirigés vers l'App Store (ou vers l'URL définie dans le paramètre si il existe`af_ios_url`).
* Pour plus de détails, voir les scénarios et cas d'utilisation qui suivent.

<div id="scenarios-flowchart" />

### Les scénarios

![Copy_of_Ios_fall_back_-_scenarios_flowchart__2_.png](https://files.readme.io/4814c80b9622fd33adf32ea649c14e5d9516958cbedb4f1e5dc1a0dcff6682a3-4425164762257.png)

<div id="use-cases" />

## Cas d’utilisation

<div id="browsers-that-can-use-uri-schemes-by-default" />

<Accordion title="Navigateurs pouvant utiliser des schémas d’URI par défaut">

Parfois, les liens universels ne parviennent pas à ouvrir l'application, soit parce que l'app n'existe pas, soit parce que le lien n'est pas configuré pour les liens universels. Dans ce cas, les navigateurs/plateformes suivants peuvent utiliser les schémas d’URI comme méthode de secours pour ouvrir l'app :

* Chrome
* X (anciennement Twitter)  
  **Remarque** : Si l'app n'est pas installée, les utilisateurs voient apparaître un message d'erreur et, après l'avoir refermé, ils sont redirigés vers l'App Store (ou selon le paramètre af\_ios\_url).
* Kakaotalk
* Naver
* Blog naver-blog
* Weibo

<div id="flowchart" />

#### **Scénarios**

![Copy_of_Ios_fall_back_-_browsers_that_can_use_URI_schemes_by_default__2_.png](https://files.readme.io/fae8ea628ff8bbfb343bb8de51af01f596e850a2a24afdc08e15e0a1b981e631-4425166478481.png)

</Accordion>

<div id="safari" />

<Accordion title="Safari">

Les sections suivantes détaillent le parcours suivi par les utilisateurs lorsque les liens universels ne parviennent pas à ouvrir l'app, et que le lien contient `af_dp` (qui porte le schéma d’URI comme valeur).

**Si l'application n'est pas installée :**

1. La boîte du message d'erreur Safari s'affiche.  

   [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
2. L 'utilisateur clique sur **OK** pour fermer la boîte de dialogue, voit brièvement une page d'accueil se charger en arrière-plan, puis, dans la seconde qui suit, est automatiquement redirigé vers l'App Store, ou selon le paramètre af\_ios\_url.

**Si l'application est installée :**

* Si le lien ne contient pas `af_force_deeplink=true`, l'utilisateur est redirigé vers l'App Store, ou selon le paramètre af\_ios\_url.
* Si le lien contient `af_force_deeplink=true` :
  1. La boîte de dialogue Safari s'affiche.  

     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  2. Si l'utilisateur clique sur **Ouvrir**, l'application s'ouvre.
  3. Si l'utilisateur clique sur **Annuler :**
     * Si le paramètre af\_ios\_url est défini, l'utilisateur est redirigé en conséquence.
     * Si le paramètre af\_ios\_url n'est pas défini, la boîte de dialogue du message d'erreur Safari s'affiche en arrière-plan sur une page d'accueil.  

       [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
  4. L'utilisateur clique sur **OK** et voit s’ouvrir une page d'accueil avec un appel à l'action (CTA).
  5. L'utilisateur clique sur le CTA et une boîte de dialogue s'ouvre.  

     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  6. Si l'utilisateur clique sur **Ouvrir**, l'application s'ouvre.
  7. Si l'utilisateur clique sur **Annuler**, une boîte de dialogue s'ouvre.  

     [![](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)
  8. Si l'utilisateur clique sur **OK**, il est redirigé vers l'App Store.
  9. Si l'utilisateur clique sur **Annuler**, il reste sur la page d’accueil.

<div id="flowchart-1" />

#### **Scénarios**

![Copy_of_Ios_fall_back_-_safari.png](https://files.readme.io/5e50eb558b23a849f02e1ffe5df3181ad7c8d9514f5813fbffcfa6160493de81-360016515318.png)

</Accordion>

<div id="facebook-post-unpaid" />

<Accordion title="Post Facebook — non payant">

Les paragraphes suivants décrivent le cheminement des utilisateurs lorsque les liens universels ne parviennent pas à ouvrir l'app, et que le lien contient `af_dp` (qui porte le schéma d’URI comme valeur).

**Si l'application est installée :**

* L'application s'ouvre.

**Si l'application n'est pas installée :**

1. Si aucune application de réseaux sociaux n'est configurée, ou une fois que l'utilisateur a cliqué sur le CTA, une boîte de dialogue s'ouvre sur une page d'accueil en arrière-plan.  

   [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
2. Il clique sur Ouvrir l'app. L'un des événements suivants peut se produire :
   * Si le paramètre `af_ios_url` est défini, l'utilisateur est redirigé en fonction.
   * Si le paramètre `af_ios_url` n'est pas défini et si `af_force_deeplink=true` ne figure pas dans le lien, l'utilisateur est redirigé en fonction.
   * Si le paramètre af\_ios\_url n'est pas défini et si `af_force_deeplink=true` est dans le lien, la boîte de dialogue s'affiche à nouveau sur la page d’accueil en arrière-plan.  

     [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
3. Si l'utilisateur clique sur **Ouvrir**, il est dirigé vers l'App Store.
4. Si l'utilisateur clique sur **Fermer**, la page d’accueil en arrière-plan s'affiche.  

   [![](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)
5. L'utilisateur clique sur le badge App Store et est redirigé vers l'App Store.

<div id="flowchart-2" />

#### **Scénario**

![diagram-X.png](https://files.readme.io/0c8040d27bbf34fdf1374b4b40a8239b6af7b6c7719db9666f36dd2829bc3217-small-17710399441553.png)

</Accordion>

<div data-zendesk-anchors="about-uri-fallback-for-ios=%C3%A0-propos-du-sch%C3%A9ma-duri-de-secours-pour-ios h_01HFV6PXS5401CCW6N2T04HGSM=%C3%A0-propos-du-sch%C3%A9ma-duri-de-secours-pour-ios scenarios-flowchart=les-sc%C3%A9narios h_01HFV6PXS5WWS0B1VYF7RJAV1J=les-sc%C3%A9narios use-cases=cas-dutilisation h_01HFV6PXS51B2W497TADRGBX7Y=cas-dutilisation h_01HFV6PXS5HE462CJEE18CM5ZR=browsers-that-can-use-uri-schemes-by-default flowchart=sc%C3%A9narios h_01HFV6PXS5N98MHJFYPSAB5XKZ=sc%C3%A9narios h_01HFV6PXS521E3MTCHJ5QBQGJ2=safari flowchart::db5f50ee=sc%C3%A9narios-1 h_01HFV6PXS57ZRSX2WAECS69XB4=sc%C3%A9narios-1 facebook-post%E2%80%94unpaid=facebook-post-unpaid h_01HFV6PXS5K8YZPE2B82V3DNTV=facebook-post-unpaid flowchart::df1b7de0=sc%C3%A9nario h_01HFV6PXS504YQRDHZ1S1WS8CV=sc%C3%A9nario" />

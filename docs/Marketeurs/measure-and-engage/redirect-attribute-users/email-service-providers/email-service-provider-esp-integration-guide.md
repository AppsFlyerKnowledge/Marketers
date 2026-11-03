---
title: Guide d'intégration des fournisseurs de services de messagerie (ESP)
metadata:
  keywords:
    - Email
    - Advertisers
    - Developers
    - Premium
    - Email service providers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-12-31T10:43:24Z'
  edited_at: '2024-10-28T12:46:59Z'
  id: 360004556077
  locale: fr
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/fr/articles/360004556077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** pour créer des campagnes d’e-mails avec des ESP intégrés avec des liens de marque OneLink et du deep linking pour améliorer l’expérience utilisateur et encourager sa conversion.

## À propos de l'intégration ESP

Le marketing par e-mail est un moyen simple, puissant et efficace pour interagir avec les clients, réguliers et nouveaux. De nombreux marketeurs font appel à des fournisseurs de services de messagerie (ESP) pour lancer des campagnes d’e-mail à grande échelle en direction de leurs utilisateurs. Vous pourriez penser que c’est un procédé simple et direct, qui offre le parfait parcours utilisateur mobile, mais ce n'est généralement pas le cas.

**Quel est le problème ?**

Les problèmes sont dus à la manière dont les ESP gèrent le plus souvent leurs analyses, qui tend à rompre le deep linking et à alourdir l'expérience des utilisateurs sur mobile. Le deep linking consiste à envoyer les utilisateurs directement à un endroit précis de votre app, ce qui est crucial pour effectuer une conversion. Permettre de créer sans difficulté du deep linking dans les campagnes par e-mail envoyées par les ESP n’est pas si simple, car les ESP « encapsulent » les liens de deep linking à des fins de mesure, ce qui rompt l'association avec le domaine de l'app requise pour les liens universels iOS et les liens d'app Android. Cela produit malheureusement les problèmes suivants :

* Les utilisateurs sont dirigés vers des sites Web mobile au lieu de les deep linker dans l'application
* La méthode de deep linking du schéma d'URI est utilisée, or elle est moins sécurisée et altère l’expérience utilisateur

<Image alt="53242 KB.png" src="https://files.readme.io/53db119f60e3fe2dfaf58b8a87e14595eeb9dde375bf87f7617f36a463ee0ced-30227717940753.png" width="688px" />

**Quelle solution ?**

Pour éviter ces problèmes et offrir aux utilisateurs mobile la meilleure expérience possible, cliquez sur votre ESP dans la section ci-dessous et suivez les instructions d'intégration fournies. Certains ESP sont pris en charge par une solution d'intégration AppsFlyer qui permet à AppsFlyer de servir d'intermédiaire entre le serveur ESP et votre nom de domaine. Son rôle de proxy permet de fournir des fichiers d'association (AASA/liens vers des actifs), ce qui facilite le deep linking.

## Les ESP pris en charge

Les campagnes d’e-mails des FSM pour les utilisateurs d'apps mobile peuvent engendrer des problèmes d'attribution et de deep linking. Pour éviter ces erreurs, cliquez sur votre ESP dans la section ci-dessous et suivez les instructions.

| Liste des ESP pris en charge |
| --- |
| <Image alt="Bluecore-850x480.png" src="https://support.appsflyer.com/hc/article_attachments/10488115966609" width="252px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Blueshift.png" src="https://support.appsflyer.com/hc/article_attachments/27174452398737" width="273px" /></Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="braze.png" src="https://support.appsflyer.com/hc/article_attachments/360005507337" width="175px" /></Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![CleverTap.png](https://support.appsflyer.com/hc/article_attachments/27174461142929)</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![Customer.io.png](https://support.appsflyer.com/hc/article_attachments/27174502908177)</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/emaillabs-integration-with-appsflyer">![email_labs_en-us.png](https://support.appsflyer.com/hc/article_attachments/9296858735121)</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![Emarsys.png](https://support.appsflyer.com/hc/article_attachments/27174515613969)</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![ExpertSender.png](https://support.appsflyer.com/hc/article_attachments/27174576950161)</Anchor> |
| <Image alt="hubspot_logo_en-us.png" src="https://support.appsflyer.com/hc/article_attachments/8610865848849" width="175px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/iterable-integration-with-appsflyer"><Image alt="iterable-logo.png" src="https://support.appsflyer.com/hc/article_attachments/360016192957" width="175px" /></Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="klaviyo.png" src="https://support.appsflyer.com/hc/article_attachments/10577276917521" width="250px" /></Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![MailExpress.png](https://support.appsflyer.com/hc/article_attachments/27174580640657)</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="MailGun.png" src="https://support.appsflyer.com/hc/article_attachments/27174583418129" width="226px" /></Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="MoEngage.png" src="https://support.appsflyer.com/hc/article_attachments/27174612972561" width="228px" /></Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/oracle-responsys-integration-with-appsflyer">![Screen_Shot_2022-09-30_at_22.15.48.png](https://support.appsflyer.com/hc/article_attachments/9523595395089)</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![RD Station.png](https://support.appsflyer.com/hc/article_attachments/27174585202961)</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![Reteno.png](https://support.appsflyer.com/hc/article_attachments/27174637167121)</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![sailthru.png](https://support.appsflyer.com/hc/article_attachments/360008755558)</Anchor> |
| <Image alt="salesforce.png" src="https://support.appsflyer.com/hc/article_attachments/360005590298" width="147px" /> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![Screen_Shot_2022-09-30_at_22.06.29.png](https://support.appsflyer.com/hc/article_attachments/9523487444241)</Anchor> |
| <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-esp-integration-with-appsflyer">![Screen_Shot_2022-09-30_at_22.09.40.png](https://support.appsflyer.com/hc/article_attachments/9523494174481)</Anchor> |

<div data-zendesk-anchors="overview=%C3%A0-propos-de-lint%C3%A9gration-esp h_01J3JHJCCASM6E5QYJB5VHQ8HK=%C3%A0-propos-de-lint%C3%A9gration-esp supported-email-service-providers=les-esp-pris-en-charge h_01H92VH355BQ13SP72VNJEKW1E=les-esp-pris-en-charge" />

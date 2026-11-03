---
title: 'Résolution des problèmes liés aux postbacks pour les annonceurs '
metadata:
  keywords:
    - Postback
    - Partner
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2023-11-14T08:40:11Z'
  id: 14272573202833
  locale: fr
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/fr/articles/14272573202833
---
> **En bref :** trouvez les principales causes et solutions en cas de non réception des postbacks attendus par votre partenaire. Examinez chacun des sujets ci-dessous et voyez s'ils peuvent en être la cause.

## Contrôler l'activation des fonctions d'intégration

Différents boutons permettent de contrôler différentes parties de l'intégration. La désactivation pourrait être la cause de l'échec de l'envoi des postbacks. 

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="Activer le partenaire est désactivé">

Lorsque le bouton <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">**Activer le partenaire**</Anchor> est désactivé, les conversions ne sont pas attribuées et les postbacks ne sont pas envoyés aux partenaires.

![integration_turned_off.png](https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png)

**Pour activer l'intégration :**

1. Dans AppsFlyer, allez dans **Configuration** et ouvrez **Intégrations actives**.
2. Cliquez sur l'icône Gérer l'intégration du partenaire.
3. Dans l'onglet **Integration** , cochez **Activer le partenaire**.

Il est également possible que la fonction <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">**Activer le partenaire**</Anchor> soit activée, mais que ce n'était pas le cas au moment de l'événement. Utilisez le journal d'audit pour vérifier si l'intégration du partenaire était active au moment de l'événement :

* Accédez à votre e-mail utilisateur (en haut à droite) > **Centre de sécurité** > **Journal d'audit**.

</Accordion>

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<Accordion title="L'option Postback d'évènement d'app est désactivée">

Le bouton **<Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration">Postback d'évènement d'in-app</Anchor>** est désactivé ou était désactivé pendant la durée de l'événement. Cela signifie qu'aucun postback n'est envoyé.

**Activez Postbacks d'événement in-app :**

1. Dans AppsFlyer, allez dans **Configuration** et ouvrez **Intégrations actives**.
2. Cliquez sur l'icône Gérer l'intégration du partenaire.
3. Dans l'onglet **Integration**, faites défiler la page jusqu'à **Postback d'évènement d'in-app** et activez la fonction.  

   ![integration-in_app_event_postbacks_toggle.png](https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png)

</Accordion>

## Vérifier la configuration de l'événement

La configuration de l'événement pourrait bloquer l'envoi de certains postbacks.

<div id="the-event-wasnt-configured" />

<Accordion title="L'événement n'est pas configuré">

Vérifiez que l'événement est inclus dans la liste des événements in-app configurés. S'il n'est pas défini, le postback n'est pas envoyé.

[![list_of_in_app_events.png](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)](https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png)

1. Dans AppsFlyer, allez dans **Configuration** et ouvrez **Intégrations actives**.
2. Cliquez sur l'icône Gérer l'intégration du partenaire.
3. Dans l'onglet **Integration**, faites défiler vers le bas jusqu'à **Postbacks d'événements in-app** et voyez si le nom de l'événement apparaît.

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="L'événement n'est pas configuré correctement">

Vérifiez que le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#le-mappage-dévénement">mappage de l'événement</Anchor> est correct. Assurez-vous que **l'événement** **AppsFlyer** (le nom de l'événement tel qu'il est reçu par AppsFlyer depuis votre app mobile ou via S2S) correspond au **nom du partenaire associé** (le nom exact de l'événement utilisé par le partenaire). 

[![in_app_event_postback_mapping_2.png](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)](https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png)

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="L'événement est configuré correctement mais est soumis à une condition">

Si une condition est définie pour l'événement, le postback est envoyé en fonction de la condition. Vérifier s'il existe une condition qui limite l'envoi de postbacks.

[![in_app_event_condition__1_.png](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="L'événement est configuré pour envoyer des postbacks uniquement au partenaire attribué">

Vérifiez si l'événement in-app est configuré pour envoyer des postbacks à <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#options-pour-lenvoi-de-postbacks">**Ce partenaire uniquement** ou à **Toutes les sources média, y compris les sources organiques**</Anchor>. S'il est défini sur **Ce partenaire seulement**, seul le partenaire attribué reçoit le postback.

[![in_app_event_sending_options.png](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)](https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png)

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="L'événement s'est produit en dehors de la fenêtre de configuration">

Les postbacks sont envoyés en fonction <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#fenêtre-des-postbacks-dévénements-in-app">de la fenêtre de postback</Anchor> configurée. Les postbacks pour les événements qui ont lieu après cette période ne sont pas envoyés au partenaire, bien que les événements soient toujours enregistrés dans AppsFlyer.

![in_app_event_postback_window.png](https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png)

Notez que pour les <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">SRN</Anchor>, les postbacks d'événements in-app sont envoyés pendant la durée de rétention <Anchor target="_blank" href="/marketers/fr/docs/user-level-data-retention#périodes-de-conservation-des-données-des-partenaires">des données du partenaire</Anchor>.

</Accordion>

<div id="the-attribution-link-was-configured-not-to-send-postbacks-for-installs" />

<Accordion title="Le lien d'attribution est configuré pour ne pas envoyer de postbacks pour les installations">

Lorsque le lien d'attribution inclut le paramètre `af_installpostback=false`, les installations sont enregistrées mais les postbacks ne sont pas envoyés au partenaire.

**Pour visualiser le lien d'attribution :**

* Dans AppsFlyer, dans **Configuration** > **Intégrations actives**, allez dans l'onglet **Lien d'attribution** et faites défiler vers le bas pour voir votre lien d'attribution.

</Accordion>

## Restrictions de confidentialité

Dans les cas suivants, AppsFlyer n'envoie pas de postbacks en raison de restrictions de confidentialité.

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="Le partenaire ne prend pas en charge le mode Confidentialité avancée, ou ne l'a pas mis en place.">

Lorsque le mode <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">Confidentialité avancée</Anchor> est activé mais que le partenaire ne l'a pas configuré de son côté (ou ne le prend pas en charge), il ne recevra pas <Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks">les postbacks de confidentialité avancée agrégée</Anchor>. 

![partner_not_supporting_ap_postbacks.png](https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png)

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<Accordion title="Restrictions concernant les sources média sur les plateformes tierces">

<Anchor target="_blank" href="/marketers/fr/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">Certaines sources média</Anchor> limitent le partage des données avec les tiers. AppsFlyer n'autorise pas le partage de données d'utilisateurs provenant de ces sources média avec des plateformes ou services tiers.Toute installation issue de ces sources média est donc transmise comme organique. Notez que Meta ads ne partage aucune donnée avec les plateformes tierces.

</Accordion>

## Divers

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="Le postback a été envoyé mais n'apparaît pas sur la plateforme du partenaire">

Dans certains cas, bien qu'AppsFlyer envoie des postbacks à un partenaire, ceux-ci ne s'affichent pas du côté du partenaire. Dans ce cas, vous devez contacter le partenaire.

**Pour savoir si le postback a été envoyé par AppsFlyer :**

1. Dans AppsFlyer, dans **Rapports** allez à **Exportation de données brutes**.
2. Consultez le rapport correspondant dans **Postbacks** (Installations, Événements in-app, Conversions de retargeting, Retargeting d'événements in-app).

[![postback_reports.JPG](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)](https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png)

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="L'événement n'a pas eu lieu ou n'a pas été envoyé à AppsFlyer">

Tous les événements qui se sont produits peuvent être consultés dans le <Anchor target="_blank" href="/marketers/fr/docs/activity-dashboard">**Tableau de bord** des activités</Anchor> et dans <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview?query=raw%20data%20reports">les rapports de données brutes</Anchor>. Si un événement n'apparaît pas, c'est que celui-ci n'a pas eu lieu, ou n'a pas été envoyé à AppsFlyer.

Il se peut que l'événement n'ait pas été défini dans le SDK. Dans ce cas, vous ne le verrez pas sur la plateforme. Vérifiez la configuration  <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#enregistrer-les-événements-in-app">définie dans le SDK</Anchor>.

Si vous pensez que l'événement s'est produit, vérifiez ci-dessous s'il apparaît dans le tableau de bord des activités ou générez un rapport de données brutes et recherchez-le.

**Pour afficher le tableau de bord des activités :**

* Dans AppsFlyer, dans les **tableaux de bord** , allez sur **Activités** et sélectionnez le partenaire et la plage de dates.

**Pour créer un rapport de données brutes :**

1. Dans AppsFlyer, dans  **Rapports,** allez dans **Exportation de données brutes**.
2. Cliquez sur **Créer un rapport**.
3. Sélectionnez le rapport concerné.
4. Sélectionnez la plage de dates et tous les champs nécessaires, puis cliquez sur **Créer**.
5. Téléchargez le rapport et recherchez l'événement.

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="Différences de fuseaux horaires">

Il peut y avoir des divergences dans la réception des postbacks en raison d'un décalage horaire entre la plateforme AppsFlyer et la plateforme du partenaire. Les tableaux de bord et les rapports AppsFlyer s'affichent en fonction du fuseau horaire sélectionné.

**Pour voir le fuseau horaire de l'application dans AppsFlyer :**

1. Dans AppsFlyer, dans **Configuration** allez dans **Paramètres de l'application**.
2. Affichez le fuseau horaire de l'application dans **Localisation**.

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="Identifiants publicitaires manquants pour le SRN (IDFA/GAID)">

Il existe un certain nombre de cas spécifiques <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">aux SRN</Anchor> où AppsFlyer n'envoie pas de postbacks pour les installations, les ouvertures d'app ou les événements in-app.

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<Accordion title="Restrictions concernant les sources média sur les plateformes tierces">

<Anchor target="_blank" href="/marketers/fr/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">Certaines sources média</Anchor> limitent le partage des données avec les tiers. AppsFlyer n'a pas le droit de partager les données d'utilisateurs provenant de ces sources média avec des plateformes ou services tiers.Toute installation issue de ces sources média est donc transmise comme étant organique. Notez que Meta ads ne partage aucune donnée avec des plateformes tierces.

</Accordion>

> 📄 **À consulter également**
>
> <Anchor target="_blank" href="/partners/fr/docs/postback-troubleshooting-for-ad-networks">Résolution des problèmes de postback pour les réseaux publicitaires</Anchor>

<div data-zendesk-anchors="activation-toggles=contr%C3%B4ler-lactivation-des-fonctions-dint%C3%A9gration h_01H9FT385FY1QJC6M2YVMZF2NC=contr%C3%B4ler-lactivation-des-fonctions-dint%C3%A9gration h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=v%C3%A9rifier-la-configuration-de-l%C3%A9v%C3%A9nement h_01H9FT385FW71JV2KKZ22TP6TN=v%C3%A9rifier-la-configuration-de-l%C3%A9v%C3%A9nement h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window h_01H9FT385GDDV1D6X69JQWPN02=the-attribution-link-was-configured-not-to-send-postbacks-for-installs privacy-restrictions=restrictions-de-confidentialit%C3%A9 h_01H9FT385G84E2A1J64VWG8H4Z=restrictions-de-confidentialit%C3%A9 h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms miscellaneous=divers h_01H9FT385GSWRPKEHKJ4HXCX01=divers h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01HE7R6G699RG30ZSSQF02AK5Y=%C3%A0-consulter-%C3%A9galement" />

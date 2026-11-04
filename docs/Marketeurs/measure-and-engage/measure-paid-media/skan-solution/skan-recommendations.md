---
title: Recommandations pour utiliser SKAN
metadata:
  keywords:
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T07:56:50Z'
  edited_at: '2023-05-21T10:13:32Z'
  id: 7078169815057
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/7078169815057
---
> **En bref** : les recommandations de SKAN permettent d'optimiser les paramètres de vos valeurs de conversion et donnent ainsi des mesures d'activité post-installation plus précises.

<div id="overview" />

## Présentation

SKAdNetwork (SKAN), qui fait partie d'Apple iOS, permet aux annonceurs de mesurer les performances des campagnes tout en respectant la vie privée des utilisateurs. Avec SKAdNetwork, l'activité post-installation est mesurée à l'aide de nombres (valeurs de conversion) compris entre 0 et 63.

Le <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">Studio de Conversion</Anchor> AppsFlyer offre une grande flexibilité pour que chaque valeur de conversion (CV) soit mise à profit. Vous déterminez précisément les données de mesure qui doivent être encodées dans la CV, ce qui inclut le choix et la durée des activités post-installation qui doivent être mesurées.

Cependant, étant donné les capacités de mesure restreintes chez SKAN, il n'est pas toujours simple de savoir ce qui vaut d'être mesurer (ex. les revenus, les événements in-app ou la rétention) et comment utiliser au mieux les CV entre 0 et 63. Les choix peuvent reposer sur des estimations, des essais et erreurs, ou des outils de machine learning qui utilisent les données internes aux applications. De plus, les mesures ne sont pas toujours aussi précises que possible.

Recommandations de AppsFlyer pour SKAN :

* Offre des suggestions pour améliorer vos paramètres de CV actuels et booster l'efficacité de votre CV et la précision de vos mesures.
* Résout les difficultés que vous pouvez rencontrer lors du choix de paramètres en matière de CV.
* Se basent sur votre verticalité, votre géo, les données SKAN et non-SKAN de l'app , et le comportement de l'utilisateur.

<div id="recommendations" />

## Recommandations

<div id="revenue" />

<Accordion title="Revenus">

<div id="understanding-revenue-recommendations" />

#### **Comprendre les recommandations sur les revenus**

Avoir le bon schéma de configuration pour les revenus est essentiel pour obtenir des rapports précis.

La configuration de la valeur de conversion (CV) utilisée pour rapporter les revenus n'est pas nécessairement exacte à 100 %, et le revenu rapporté par SKAN peut ne pas correspondre au revenu réel. Par exemple, vous pouvez avoir une ARPPU réelle (rapportée par AF) de 10 $ et une ARPPU SKAN de 7 $ d'après la configuration de votre CV, ce qui signifie que pour chaque utilisateur payant SKAN sous-estime de 3 $ les revenus.

AppsFlyer vérifie quotidiennement vos données de revenus non-SKAN (qui sont exactes à 100 %) et vous envoie des recommandations personnalisées qui vous permettront d'améliorer l'exactitude de vos rapports de revenus SKAN. Les recommandations reposent également sur la configuration de la fenêtre d'activité que vous avez enregistrée dans Conversion Studio, sur votre verticale, votre géo ainsi que sur le comportement des utilisateurs de votre app.

Nos recommandations :

* Vous donnent une vision claire des performances de campagne grâce à des rapports de revenus très précis.
* Économisent les valeurs de conversion en utilisant moins de périodes différentes pour mesurer précisément les revenus.
* Prenez en compte tant les achats in-app que les revenus publicitaires.

<div id="revenue-recommendations-layout" />

#### **Présentation des recommandations sur les revenus**

<table><tbody><tr><td colspan="2"><p><img alt="revenue_recommendions_layout.png" src="https://files.readme.io/1595d3f59b6e30154da560a99430e231d8353d1bd54ebed6192ec0f13cd3f5b3-8976338886801.png"/></p></td></tr><tr><td><p><span>A</span></p></td><td><span>Fenêtre d'activité qui a été enregistrée dans la configuration de votre Conversion Studio, et durant laquelle le revenu SKAN est mesuré.</span></td></tr><tr><td><p><span>B</span></p></td><td><span>Revenu moyen réel par utilisateur payant (ARPPU), basé sur des données précises issues d'utilisateurs organiques et non organiques attribués via les procédés AppsFlyer (AF).</span></td></tr><tr><td><p><span>C</span></p></td><td><p><span>Configuration actuelle ARPPU (SKAN ARPPU), soit l'ARPPU mesurée <span>dans la fenêtre d'activité et la configuration de CV pour le rapport des revenus (d'après votre configuration dans Conversion Studio).</span></span></p></td></tr><tr><td><span>D</span></td><td><p><span>Prévision de l'ARPPU : l'ARPPU attendue sur le nombre de périodes que vous avez sélectionnées. Voir F et G.</span></p></td></tr><tr><td><p><span>E</span></p></td><td><p>Erreur approximative : la d<span>ifférence entre B et C. Il peut s'agir d'une erreur positive si votre SKAN ARPU est surestimée, ou négative si elle est sous-estimée.</span></p><p><span>Exemple : si l'ARPPU réelle est 10 dollars et l'ARPPU SKAN est 7 dollars, l'erreur approximative est sous-estimée à 30 % (- 3 dollars par utilisateur).</span></p></td></tr><tr><td><p><span>F</span></p></td><td><p>Recommandations pour la configuration de votre revenu SKAN. Sélectionnez le nombre de périodes que vous souhaitez inclure dans votre configuration.</p></td></tr><tr><td><p><span>G</span></p></td><td><p><span>La configuration de vos revenus, telle que vous l'avez définie dans Conversion Studio.</span><span></span></p></td></tr></tbody></table>

<div id="note" />

<div id="using-revenue-recommendations" />

#### **Appliquer les recommandations sur les revenus**

**Condition nécessaire :** les recommandations sur les revenus requièrent au minimum 14 jours de données de revenus.

**Pour appliquer les recommandations sur les revenus :**

1. Dans AppsFlyer, selon que vous utilisez SKAN 4 ou le mode personnalisé / fixe, rendez-vous dans l'une des sections suivantes :
   * **Configuration** > **SKAN Conversion Studio** > **SKAN 4**> **Revenu global / Événement in-app**.
   * **Configuration** > **SKAN Conversion Studio** > **Personnalisé** > **Revenu global / Événement in-app**.
   * **Configuration** > **SKAN Conversion Studio** > **Revenus**.
2. Si vous avez déjà configuré une plage de revenus, veuillez ignorez cette étape. Si vous n'avez pas encore configuré de plage de revenus, veuillez le faire avant de poursuivre.  
   Lorsque la plage de revenus est configurée, des informations sur la précision de votre configuration et l'erreur approximative s'affichent.
3. Cliquez sur **Vérifier les recommandations**.  
   Les éléments de votre configuration actuelle s'affichent, ainsi que les recommandations sur la plage de revenus et la précision de l'estimation (erreur approximative) qui pourront s'appliquer. Des recommandations sont proposées pour soit conserver, soit modifier le nombre de plages.
4. Sélectionnez une recommandation de plage.
5. Cliquez sur **Appliquer la recommandation**.
   * Si la configuration de vos revenus est définie en mode personnalisé, la recommandation s'applique.
   * Si votre configuration des revenus est en mode fixe (revenus), vous devez enregistrer la recommandation de plage, puis aller dans **SKAN Conversion Studio** > **Personnalisé** > **Revenu global**, et configurer la plage recommandée.
6. Cliquez sur ***Enregistrer***.  
   * Si vous modifiez par la suite la configuration de vos revenus, vous pourrez vérifier à nouveau votre configuration et afficher les nouvelles recommandations.

</Accordion>

<div data-zendesk-anchors="overview=pr%C3%A9sentation recommendations=recommandations understanding-revenue-recommendations=comprendre-les-recommandations-sur-les-revenus revenue-recommendations-layout=pr%C3%A9sentation-des-recommandations-sur-les-revenus using-revenue-recommendations=appliquer-les-recommandations-sur-les-revenus" />

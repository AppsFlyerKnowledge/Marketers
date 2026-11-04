---
title: Conservation des données de niveau utilisateur
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - SRN
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
    - Ad Networks
  created_at: '2020-02-23T15:35:57Z'
  edited_at: '2024-08-15T14:37:00Z'
  id: 360006091197
  locale: fr
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/fr/articles/360006091197
---
> **En bref :** Les politiques de conservation et d'utilisation au niveau de l'utilisateur (données brutes) sont déterminées par AppsFlyer, la législation applicable, ainsi que les conditions d'utilisation des SRN ("**les partenaires**").

<div id="caution" />

> ❗️ **Attention !**
>
> AppsFlyer fournit dans cet article des explications sur les restrictions des données, et ce à titre d'information uniquement.  Rien de ce qui est inscrit dans cet article ne constitue un avis juridique. Ces indications sont fournies à titre d'information uniquement.

<div id="data-retention-and-deletion-obligations" />

## Obligations concernant la conservation et l'effacement des données

AppsFlyer reçoit des données sur les utilisateurs de la part d'applications, de partenaires et d'autres sources.

<div id="availability-of-user-level-data-to-advertisers" />

### Disponibilité des données de niveau utilisateur pour les annonceurs

En règle générale, les données de niveau utilisateur sont mises à la disposition des annonceurs via des <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">outils de reporting de données brutes</Anchor>, dans le cas où leur abonnement inclue les données brutes au cours d’une fenêtre d'accès de 90 jours<Anchor target="_blank" href="/marketers/fr/docs/report-generation-quotas-rate-limitations">(limitations du taux AppsFlyer</Anchor>). Dans certains cas, il existe des <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">restrictions concernant les données brutes</Anchor>.

<div id="data-retention" />

### Conservation des données

AppsFlyer garde les données de niveau utilisateur pendant une période de conservation limitée. Avant la fin de la période de conservation, les événements de l'utilisateur sont attribués à la source média qui a drainé l'utilisateur. Après la période de conservation, les événements des utilisateurs sont attribués à l'organique.

La période de conservation est déterminée selon les modalités suivantes :

* <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">Politique de confidentialité des services AppsFlyer</Anchor>
* Si la loi l'impose, le prescrit ou l'autorise
* Les conditions d'utilisation des partenaires ainsi que les durées de conservation sont indiquées dans le tableau ci-dessous.

Prenez en compte les éléments suivants :

* La fenêtre d'accès et la période de conservation peuvent différer
* Dans certains cas, AppsFlyer peut prolonger la fenêtre d'accès.
* La période de conservation peut varier selon le partenaire qui a produit l'utilisateur.
* Certaines données de niveau utilisateur sont attribuées à la <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">source média restreinte</Anchor>, ce qui signifie que les données brutes ne contiennent pas les données d'attribution. Cela peut se produire dans les cas suivants :
  * Politique de partage des données des partenaires
  * <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">La confidentialité avancée agrégée</Anchor> est activée.

<div id="partner-data-retention-periods" />

#### Périodes de conservation des données des partenaires

| SRN/partenaire | ID du partenaire (PID) | Après l'installation, supprime les données après [x] mois |
| --- | --- | --- |
| Amazon | amazon\_int | 12 |
| Google Ads | googleadwords\_int (tous les canaux) | 6 |
| Meta Ads | facebook\_int (tous les canaux) | 6 |
| Microsoft | microsoftdisplay\_int and bingsearch\_int | 13 |
| Pinterest | pinterest\_int | 6 |
| Samsung DSP | samsungdsp\_int | 3 |
| Snapchat<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">(TOS</Anchor>) | snapchat\_int | 6 |
| TikTok for Business | tiktokglobal\_int | 6 |
| X Ads (anciennement Twitter) | twitter\_int | 3 |

<div id="note" />

> 📄 **Articles connexes**
>
> <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">Restriction du contenu des données brutes - identifiants utilisateur ou source média</Anchor>

<div data-zendesk-anchors="h_01H95FY07TRAAD3K0A0TSG3RB6=attention- data-retention-and-deletion-obligations=obligations-concernant-la-conservation-et-leffacement-des-donn%C3%A9es h_01H95FY07TABPC769R7TYGY5DD=obligations-concernant-la-conservation-et-leffacement-des-donn%C3%A9es availability-of-userlevel-data-to-advertisers=disponibilit%C3%A9-des-donn%C3%A9es-de-niveau-utilisateur-pour-les-annonceurs h_01H95FY07T2Q9QAGW5A5S6KP6J=disponibilit%C3%A9-des-donn%C3%A9es-de-niveau-utilisateur-pour-les-annonceurs data-retention=conservation-des-donn%C3%A9es h_01H95FY07TXS63FVDJC2NEFXYC=conservation-des-donn%C3%A9es partner-data-retention-periods=p%C3%A9riodes-de-conservation-des-donn%C3%A9es-des-partenaires h_01H95FY07TZ4N0RRJRGJ6FN2EK=p%C3%A9riodes-de-conservation-des-donn%C3%A9es-des-partenaires h_01HE7S5A2Q8GFEKD8M7C2RZ40W=articles-connexes" />

---
title: 複数の代理店／MCCのGoogle Adsアカウントの計測
metadata:
  keywords:
    - Advertisers
    - Multiple Agencies
    - MCC
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-28T11:11:04Z'
  edited_at: '2026-10-28T09:15:42Z'
  id: 115004970386
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/115004970386
---
> **概要：** 複数のGoogle Adsアカウントからのトラフィックを正しく成果に紐づけるための計測設定について説明します。

## はじめに

Google Adsのトラフィックは、Google Adsを専門とする代理店や、アプリ所有者の組織内のさまざまな地域のローカルチームなど、複数のアカウントから発生することがあります。広告成果を正しい運用元に紐づけるために、複数のGoogle Adsアカウントの計測設定を理解しておくことが重要です。

この記事では、代理店の成果計測から、MCCや複数のMCCを統括するMCCの利用まで、これらのケースを説明します。

> 📘 **注意**
>
> 以下は、Google Adsの新しいAPIを使用しているクライアント**のみ**に適用されます。

Google Adsの代理店アカウントの設定については、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-agencies">こちら</Anchor>を参照してください。

## 重要な定義

* **リンクID**：**Google Adsで定義されるモバイルアプリの一意の識別子**です。

> 📘 **注意**
>
> 同じアプリのAndroidとiOSバージョンでは異なるリンクIDが必要です。

* **お客様ID**：**Google Adsアカウントの一意の識別子**です。  
  各アカウントでは、たとえば自社のすべてのアプリなど、複数のリンクIDに対応するアプリの広告を配信できます。 AppsFlyer管理画面で代理店アカウントを既存のアプリにリンクする場合、最大10個のお客様IDを定義できます。
* **MCC**：Google Adsマネージャーアカウント（MCC、旧称My Clients Center）は、**複数のGoogle Adsアカウントを管理するためのツール**です。  
  MCCアカウントでは複数のアカウントをリンクし、1か所で確認できます（<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186?hl=en&ref_topic=7554904">詳細はこちら</Anchor>）。

## Google Adsの計測設定

AppsFlyerで登録できるリンクIDは、アプリごとに1つです。<strong>複数のアカウントが同じアプリを運用する場合、同じリンクIDを使用する必要があります。</strong>計測のために、このリンクIDをAppsFlyer管理画面で設定する必要があります。

### GoogleのリンクIDを別のアカウントと共有する方法

一つのGoogle Adsアカウントを持つアプリ所有者、またはGoogle Adsトラフィックの運用を代理店に依頼する予定のアプリ所有者は、次の方法を使用してください。

以下の画面例のように、アプリ所有者は、お客様IDで識別される別のアカウントと任意のリンクIDを共有できます。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-agencies#代理店向けのgoogle-ads計測設定">リンクIDを代理店と共有する方法</Anchor>を参照してください。

> 🚧 **重要**
>
> * MCCがサブアカウントのコンバージョンアカウント（コンバージョンアカウント）である場合、MCCからサブアカウントにリンクIDを共有する必要はありません。ただし、MCC配下のサブアカウントが自らのコンバージョンを管理する場合、MCCは、そのコンバージョンアカウントとなるサブアカウントにリンクIDを共有する必要があります。
> * コンバージョンのインポート：MCCがコンバージョンアカウントである場合、MCCが配下のサブアカウントのコンバージョンをインポートする必要があります。ただし、MCC配下のサブアカウントが自らのコンバージョンを管理する場合、そのサブアカウントでもコンバージョンをインポートする必要があります。

> 📘 **注意**
>
> * Google Ads管理画面で、3点メニュー>>***リンク済みアカウント***>>***サードパーティのアプリ分析の詳細***の順にクリックします。 [![](https://support.appsflyer.com/hc/article_attachments/52396751401361)](https://support.appsflyer.com/hc/article_attachments/52396751401361)
> * 他のアカウントは「共有」を承認する必要があります。
> * これにより、共有先アカウントに、そのアプリのGoogle Adsキャンペーンを配信する権限が付与されます。

> 👍 **ヒント**
>
> AppsFlyerでは、他のアカウントでリンクIDを直接生成するのではなく、広告主のメインアカウントから他のアカウントにリンクIDを共有することを推奨しています。これは最も手早い方法であり、広告主と代理店の関係が終了した際にアカウントのリンクを容易に解除することができます。

## MCC

複数のGoogle Adsアカウントを管理する代理店や大規模な広告主は、すべてのアカウントを1か所で確認できるMCC（My Client Center）をよく利用します。

MCCの設定中に、MCCとサブアカウントのどちらでコンバージョンを管理するかを設定できます。

[![MCC_1_new.png](https://support.appsflyer.com/hc/article_attachments/52396712542097)](https://support.appsflyer.com/hc/article_attachments/52396712542097)

この設定は、必要に応じて後で変更できます。

![mmc-googleads-settings.png](https://support.appsflyer.com/hc/article_attachments/52396751408529)

## 複数のMCCを統括するMCC

[![](https://support.appsflyer.com/hc/article_attachments/52396712543121)](https://support.appsflyer.com/hc/article_attachments/52396712543121)

複数の代理店と取引する大規模な広告主は、複数のMCCを統括するMCCアカウントを利用する場合があります。これは通常のMCCアカウントに似ています。このとき、MCCアカウントの中で最上位のMCCアカウント、または広告主アカウントがリンクIDを生成することを推奨します。この構造を正しく設定するには、サブアカウント側で、適切な階層のMCC（通常は最上位のMCC）をコンバージョンアカウントとして選択する必要があります。このように設定されている場合は、リンクIDをサブアカウントと共有する必要はなく、最上位のアカウントでコンバージョンのインポートをするだけで十分です。

> 👍 **ヒント**
>
> MCCおよびアカウントの階層の詳細については、以下のリンクを参照してください：
>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7456530">アカウントをMCCアカウントにリンクする方法</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7519925?hl=en&ref_topic=7554359">MCCアカウントの階層の確認</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/topic/7554359?hl=en&ref_topic=6031997">管理対象アカウントの操作</Anchor>
>
> アカウント構成や推奨される設定については、Googleの担当者にお問い合わせください。

## Google Adsキャンペーンの開始

MCCからGoogle Adsキャンペーンを直接作成することはできません。通常のGoogle Adsサブアカウントから作成する必要があります。

コンバージョンの計測には、次の2つの方法があります。

1. **MCCがサブアカウントのコンバージョン計測を管理**  
   社内に複数のチームがあり、たとえば**同じ会社で地域ごとにGoogle Adsアカウントを運用している**場合によく利用されます。  
   MCCが、すべてのサブアカウントの計測設定を保持するコンバージョンアカウントとなります。計測設定の変更はMCCでのみ行い、すべてのサブアカウントに自動的に引き継がれます。  
   MCCはコンバージョンをインポートする必要もあります。1回のインポートですべてのサブアカウントが対象となります。また、サブアカウント用に共有されたリンクIDも取得する必要があります。
2. **サブアカウントが自らのコンバージョン計測を管理**  
   たとえば**1つの代理店が複数の広告主のアカウントを運用する**場合など、同じ運用元を利用していること以外にアカウント間のつながりがない場合によく利用されます。  
   この場合、各サブアカウントで個別にコンバージョンをインポートする必要があります。 AppsFlyerに登録できるリンクIDはアプリごとに1つのため、モバイルアプリを計測するには、MCCまたは広告主がリンクIDをサブアカウントと共有する必要があります。

Google Adsのコンバージョンは、インストール、アプリ内イベントのいずれも、最初のコンバージョンが発生してからインポートできます。

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB important-definitions=%E9%87%8D%E8%A6%81%E3%81%AA%E5%AE%9A%E7%BE%A9 setting-up-google-ads-recording=google-ads%E3%81%AE%E8%A8%88%E6%B8%AC%E8%A8%AD%E5%AE%9A sharing-google-link-id-with-another-account=google%E3%81%AE%E3%83%AA%E3%83%B3%E3%82%AFid%E3%82%92%E5%88%A5%E3%81%AE%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%A8%E5%85%B1%E6%9C%89%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 mcc-of-mccs=%E8%A4%87%E6%95%B0%E3%81%AEmcc%E3%82%92%E7%B5%B1%E6%8B%AC%E3%81%99%E3%82%8Bmcc opening-a-google-ads-campaign=google-ads%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E9%96%8B%E5%A7%8B" />

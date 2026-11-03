---
title: Google Ads（AdWords）｜リエンゲージメント
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2026-10-21T19:11:45Z'
  id: 4417296925073
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/4417296925073
---
> **概要：** Google Adsのリターゲティングキャンペーンを計測しましょう。

## Google Adsのリターゲティングキャンペーン

AppsFlyerでは、**Google Adsのエンゲージメント向けアプリキャンペーン**の成果を計測できます。  
AppsFlyer上では、これらのキャンペーンは「<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide">リターゲティングキャンペーン</Anchor>」と呼ばれます。 AppsFlyerは、リターゲティングキャンペーンにおけるコスト、クリック、インプレッションデータの取得をサポートしています。この連携により、Google Adsの広告費を確認・計測し、Google AdsキャンペーンのeCPIとROIを算出できます。

リターゲティングキャンペーンは、過去にアプリをインストールしたユーザーを対象とします。

* アプリが現在もインストールされているユーザーによるリターゲティング広告へのエンゲージメントを、**リエンゲージメント**と呼びます。通常、これらのユーザーはディープリンクでアプリに誘導されます。
* 一方、アプリをインストールしていないユーザーによるリターゲティングエンゲージメントは「**再インストール**」または「**リアトリビューション**」と呼ばれます。

詳細は、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">Google Adsのエンゲージメント向けアプリキャンペーンのヘルプ</Anchor>を参照してください。

## Google Adsのエンゲージメント向けアプリキャンペーンの設定

既存のリンクIDでエンゲージメントキャンペーンを正しく計測できるよう、開始前に<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">他のGoogle Adsアカウントとリンクを共有する方法に関するGoogleの手順</Anchor>を確認してください。

Google Adsのエンゲージメント向けアプリキャンペーンを計測するには、以下の3つのステップに従ってください。

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="アプリ設定でのリターゲティング有効化">

任意のメディアソースでリターゲティングキャンペーンを有効にするには、アプリレベルで設定を有効化する必要があります。初めてリターゲティングキャンペーンを実施する場合は、以下の手順を実施してください。

1. AppsFlyer管理画面左メニュー **設定** > **アプリ設定**へ移動します。
2. ページ下までスクロールダウンしてください。
3. **リエンゲージメントの計測**をオンにします。

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="AppsFlyerでGoogle Adsのリターゲティングを有効化">

* AppsFlyerでの<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">Google Ads設定手順</Anchor>に従ってください。

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="Google Adsへのsession_startコンバージョンのインポート">

**Google Ads**でリエンゲージメントキャンペーンのコンバージョンを記録するには、「session\_start」のイベントをGoogle Adsにインポートする必要があります。

このイベントは、AppsFlyerでGoogle Adsのリターゲティングを有効化した後、少なくとも1人のユーザーがアプリを起動するとGoogle Ads上に表示されます。確実に表示させるため、有効化後に自身でアプリを起動することを推奨します。

Google Adsでのコンバージョンインポート方法については、<Anchor target="_blank" href="/marketers/ja/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">こちらをご参照ください。</Anchor>

> 📘 **注意**
>
> 他のイベントとは異なり、session\_startはAppsFlyerからGoogle Adsにインポートしていなくても、Google Ads API経由でGoogle Adsが成果を主張できます。
> ただし、その場合でもAppsFlyerではこれらのコンバージョンが成果として計測されます。これにより、**AppsFlyerとGoogle Adsのデータに大きな乖離が生じます**。さらに、キャンペーンのユーザーターゲティングを**Google Adsで最適化できなくなります**。

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="エンゲージメント向けアプリキャンペーンにおけるディープリンク設定">

Googleのエンゲージメント向けアプリキャンペーンでは、<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">リエンゲージメントキャンペーンでディープリンクを使用する</Anchor>必要があります。ドメイン不一致のため、サードパーティのディープリンクソリューションは使用できません。これにはAppsFlyerのOneLinkも含まれます。自社で実装した<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">App Links、ユニバーサルリンク、またはカスタムURIスキーム</Anchor>を使用してください。

ディープリンクに追加パラメータを付与する必要はありません（is\_retargeting=trueやpid=adwordsは不要です）。

</Accordion>

## ダイナミックリマーケティングおよびショッピングキャンペーン

AppsFlyerは、アプリ向けダイナミックリマーケティングおよびショッピングキャンペーンに対応しています。これらは他のリエンゲージメントキャンペーンと同様に扱われます。

* アプリ向けダイナミックリマーケティングについては<Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">こちらをご参照ください。</Anchor>
* ショッピングキャンペーンについては<Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">こちらをご参照ください。</Anchor>
* Google Adsのエンゲージメント向けアプリキャンペーンの詳細は<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">こちらをご参照ください。</Anchor>

### 非アプリキャンペーン（Demand GenおよびSEM）への対応

AppsFlyerでは、以下を含むGoogleの非アプリキャンペーンについて、リエンゲージメントの計測のみに対応しています。

* Demand Genキャンペーン
* 検索エンジンマーケティング（SEM）キャンペーン

これらのキャンペーンは、AppsFlyerで**特別な設定なしに利用可能**であり、以下は不要です。

* 並行トラッキング
* Smart Scriptの実装

**制限事項：**

* Demand GenまたはSEMキャンペーンによる**インストール**は、いかなるプラットフォームでも計測されません。

**オプトアウト：** TikTokやMetaなどのプラットフォームとは異なり、Googleは現在、非アプリキャンペーンの計測のオプトイン／オプトアウトに対応していません。

> 📄 **関連記事**
>
> * iOS14関連の考慮事項については、<Anchor target="_blank" href="/marketers/ja/docs/get-skan-postback-data-from-google-ads">Google AdsにおけるSKAdNetworkとAppsFlyerの相互運用性</Anchor>をご参照ください。

<div data-zendesk-anchors="google-ads-retargeting-campaigns=google-ads%E3%81%AE%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_01HDP34BWZFG09ABN5NQB6EY32=google-ads%E3%81%AE%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 setting-up-google-ads-app-campaigns-for-engagement=google-ads%E3%81%AE%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E5%90%91%E3%81%91%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDP34BWZXXNZDE0SR4MXBC9V=google-ads%E3%81%AE%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E5%90%91%E3%81%91%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=%E6%B3%A8%E6%84%8F h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement dynamic-remarketing-and-shopping-campaigns=%E3%83%80%E3%82%A4%E3%83%8A%E3%83%9F%E3%83%83%E3%82%AF%E3%83%AA%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%8A%E3%82%88%E3%81%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_01HDP34BWZ990SD3B1C5DZRESK=%E3%83%80%E3%82%A4%E3%83%8A%E3%83%9F%E3%83%83%E3%82%AF%E3%83%AA%E3%83%9E%E3%83%BC%E3%82%B1%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%8A%E3%82%88%E3%81%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3 h_google-non-app-campaign-support=%E9%9D%9E%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3demand-gen%E3%81%8A%E3%82%88%E3%81%B3sem%E3%81%B8%E3%81%AE%E5%AF%BE%E5%BF%9C support-for-nonapp-campaigns-demand-gen-and-sem=%E9%9D%9E%E3%82%A2%E3%83%97%E3%83%AA%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3demand-gen%E3%81%8A%E3%82%88%E3%81%B3sem%E3%81%B8%E3%81%AE%E5%AF%BE%E5%BF%9C h_01HDP2XBSEJVQ5G0MD0V5R05CM=%E9%96%A2%E9%80%A3%E8%A8%98%E4%BA%8B" />

---
title: Bidalgo - Google Ads：キャンペーンの設定
metadata:
  keywords:
    - Advertisers
    - Bidalgo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-19T11:46:44Z'
  edited_at: '2026-10-28T09:15:10Z'
  id: 360001325405
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/360001325405
---
> **概要：** AppsFlyerの連携済みパートナーであるBidalgoは、アプリのマーケティング担当者による事業成長の拡大を支援するAIソリューションの主要プロバイダーです。

<div id="set-up-bidalgo-integration" />

## Bidalgo連携の設定

**前提条件：** 連携を設定する前に、パートナーに連絡して、パートナー側でアカウントを開設してください。

**新規連携：**

1. AppsFlyerで、［**コラボレーション>パートナー連携>マーケットプレイス**］タブに移動します。
2. 対象のアプリを選択します。
3. Bidalgoを検索し、［**連携**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効にする**］トグルをオンにします。 Bidalgoとの連携中は、オンのままにしてください。
5. 以下の説明に従い、必要に応じて他のタブを設定します。

**既存の連携の編集：**

AppsFlyerで、［**コラボレーション>パートナー連携>アクティブな連携**］タブに移動し、パートナーを検索して設定を変更します。

<div id="note" />

> 📘 **注意**
>
> Google Adsのお客様IDは、ハイフンを**含めずに**入力する必要があります。

6. **Google Ads**アカウントの左上に表示されるお客様IDをハイフンなしでコピーし、以下の画面例のようにAppsFlyerの［**広告のお客様ID**］パラメータに貼り付けます。

<Image align="center" alt="" src="https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png" />

7. ［**Google Adsのお客様ID**］欄に、その番号を入力します。

<div id="in-app-events" />

### アプリ内イベント

1. Bidalgoにアプリ内イベントのポストバックを送信するには、［アプリ内イベントポストバック］トグルを**オン**にします。

2. Bidalgoに送信するアプリ内イベントを個別に追加し、［**パートナーイベント識別子**］欄にマッピングします。

3. ［**収益を送信**］を選択すると、収益値（イベントに含まれる場合）を含むすべてのパラメータが送信されます。

4. **保存**をクリックします。

<div id="important-note" />

> 📘 **重要な注意事項**
>
> * Google Adsの計測を無効にすると、Google Adsのパートナーにポストバックを送信できなくなります。
> * CIDをカンマで区切ることで、ポストバックの送信対象として複数のGoogle Adsアカウント（CID）を設定できます（ステップ5）。

<div data-zendesk-anchors="set-up-bidalgo-integration=bidalgo%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKA1JNXMRJ8059FAJAEQ6RK5=bidalgo%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKA1JNXM5R15CBVQ2WHT99Z9=%E6%B3%A8%E6%84%8F inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HKA1JNXM59W74725961FZA27=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HKA1JNXMASTQ9X2144JCKKNQ=%E9%87%8D%E8%A6%81%E3%81%AA%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85" />

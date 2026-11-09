---
title: Adquant by Kenshoo - Google Ads：キャンペーンの設定
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Kenshoo
    - Adquant
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2018-12-09T07:43:55Z'
  edited_at: '2026-10-28T09:15:07Z'
  id: 360000654357
  locale: ja
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ja/articles/360000654357
---
> **概要：** Adquant by Kenshooを使用してGoogle AdWordsキャンペーンを最適化します。設定が完了すると、AppsFlyerからAdquantにポストバックが送信されます。

<div id="setting-up-adquant-by-kenshoo" />

## Adquant by Kenshooの設定

**前提条件：** 連携を設定する前に、パートナーに連絡して、パートナー側でアカウントを開設してください。

**新規連携：**

1. AppsFlyerで、［**コラボレーション>パートナー連携>マーケットプレイス**］タブに移動します。
2. 対象のアプリを選択します。
3. Adquant by Kenshooを検索し、［**連携**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効にする**］トグルをオンにします。 Adquant by Kenshooとの連携中は、オンのままにしてください。
5. 以下の説明に従い、必要に応じて他のタブを設定します。

**既存の連携の編集：**

AppsFlyerで、［**コラボレーション>パートナー連携>アクティブな連携**］タブに移動し、パートナーを検索して設定を変更します。

<div id="note" />

> 📘 **注意**
>
> Google Adsのお客様IDは、ハイフンを**含めずに**入力する必要があります。

6. **Google Ads**アカウントの左上に表示されるお客様IDをハイフンなしでコピーし、以下の画面例のようにAppsFlyerの［**広告のお客様ID**］パラメータに貼り付けます。

<Image align="center" alt="" src="https://files.readme.io/0987564b63f58e4091126c0131f93ae38a20bb9998894cadb53965fe7b72e9f4-21414640108689.png" />

7. Adquantから提供された**Action Identifier**と**Disable\_Country\_Sending**、および**Google Adsのお客様ID**をそれぞれの欄に入力します。

<div id="in-app-events" />

### アプリ内イベント

1. Adquant by Kenshooにアプリ内イベントのポストバックを送信するには、［アプリ内イベントポストバック］トグルを**オン**にします。

2. Adquant by Kenshooに送信するアプリ内イベントを個別に追加し、［**パートナーイベント識別子**］欄にマッピングします。

3. ［**収益を送信**］を選択すると、収益値（イベントに含まれる場合）を含むすべてのパラメータが送信されます。

4. ［**保存**］をクリックします。

<div id="important-note" />

> 📘 **重要な注意事項**
>
> * Google Adsの計測を無効にすると、Google Adsのパートナーにポストバックを送信できなくなります。
> * CIDをカンマで区切ることで、ポストバックの送信対象として複数のGoogle Adsアカウント（CID）を設定できます（ステップ5）。

<div data-zendesk-anchors="setting-up-adquant-by-kenshoo=adquant-by-kenshoo%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKA1JQRK5BVGW13P72YEXZT7=adquant-by-kenshoo%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKA1JQRKGDMZHTVSPVDSV463=%E6%B3%A8%E6%84%8F inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HKA1JQRK4YNEXKAHVBYP3EC1=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01HKA1JQRKZJJ4RXCCVSS1BG7Z=%E9%87%8D%E8%A6%81%E3%81%AA%E6%B3%A8%E6%84%8F%E4%BA%8B%E9%A0%85" />

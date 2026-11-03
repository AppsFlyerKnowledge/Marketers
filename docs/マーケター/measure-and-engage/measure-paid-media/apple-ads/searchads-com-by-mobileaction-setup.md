---
title: MobileAction による SearchAds.com の設定
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-06-20T13:34:38Z'
  edited_at: '2026-10-14T09:34:45Z'
  id: 4402846897041
  locale: ja
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/ja/articles/4402846897041
---
> **概要：** 概要： MobileAction の SearchAds.com を使用して、Apple Search Ads キャンペーンを最適化します。設定により、AppsFlyer は SearchAds.com にポストバックを送信します。

## Apple Search Ads のアトリビューションを有効化する

この設定は、広告主、代理店のいずれでも可能です。

> 📘 **注意**
>
> 広告主または広告代理店が Apple Search Ads のアトリビューションを無効化した場合、SearchAds.com およびその他の Apple Search Ads マーケティングパートナーのポストバックは停止されます。

* **広告主**： Apple Search Ads でアトリビューションを有効にする方法については、以下の手順を参照してください。
* **代理店**：Apple Search Ads でアトリビューションを有効にする方法については、<Anchor target="_blank" href="/marketers/ja/docs/apple-ads-integration-setup#agency-setup">以下の手順を参照してください</Anchor>。

## AppsFlyer での SearchAds.com の設定方法

### SearchAds.com から必要な情報を取得する

AppsFlyer で SearchAds.com の設定を開始する前に、**api\_key** と **Apple Search Ads キャンペーングループ ID** を取得します。

* api\_key については、SearchAds.com のダッシュボードで**連携** > **AppsFlyer** をクリックします。
* apple-search-ads-campaign-group-id.png

  ![apple-search-ads-campaign-group-id.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)

### AppsFlyer でのキャンペーンの設定方法

**SearchAds.com を設定するには：**

1. 必要に応じて、**Apple Search Ads連携**を有効にしてください：
   1. **AppsFlyerのサイドメニューから、** コラボレーション  > パートナーマーケットプレイス を選択します。
   2. パートナーを検索して選択します。パートナー構成ページに移動します。
   3. **連携**タブで、**パートナーを有効化**をオンにします。
   4. **連携を保存** をクリックします。
2. **AppsFlyer 内で、SearchAds.com を設定する：**
   1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動します。
   2. MobileAction による SearchAds.com を検索します。  
      マーケティングパートナーの一覧が表示されます。
   3. MobileAction による SearchAds.com を選択します。
   4. **パートナーを有効にする** をオンにしてください。
   5. **api\_key** フィールドに API キーを入力します。
   6. 数値（数字）のみを入力してください。
   7. **保存**をクリックしてください。

#### アプリ内イベントポストバックの設定

**アプリ内イベントの際に SearchAds.com に送信されるポストバックを設定する：**

1. **api\_key** を入力します。
2. **アプリ内イベントポストバック**をオンにする。
3. **すべてのイベントを送信**を選択します。
4. **収益を送信**下で、**値と収益**を選択します。
5. **連携を保存** をクリックします。

<div data-zendesk-anchors="enabling-apple-search-ads-attribution=apple-search-ads-%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96%E3%81%99%E3%82%8B h_01HKW0B2AZ40F0N9A7YYGTHCE0=apple-search-ads-%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96%E3%81%99%E3%82%8B h_01HKW0B2AZ411647BAS75M5BG6=%E6%B3%A8%E6%84%8F setting-up-searchadscom-in-appsflyer=appsflyer-%E3%81%A7%E3%81%AE-searchadscom-%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01HKW0B2AZWC9AQBAYDWFPAKQN=appsflyer-%E3%81%A7%E3%81%AE-searchadscom-%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 getting-required-information-from-searchadscom=searchadscom-%E3%81%8B%E3%82%89%E5%BF%85%E8%A6%81%E3%81%AA%E6%83%85%E5%A0%B1%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B h_01HKW0B2AZ49R66CMJ747M485M=searchadscom-%E3%81%8B%E3%82%89%E5%BF%85%E8%A6%81%E3%81%AA%E6%83%85%E5%A0%B1%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B setting-up-campaigns-in-appsflyer=appsflyer-%E3%81%A7%E3%81%AE%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 h_01HKW0B2AZ419YS071HNXHPZXY=appsflyer-%E3%81%A7%E3%81%AE%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A%E6%96%B9%E6%B3%95 configuring-inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKW0B2AZ4GHJE5SQHB3ZSZ8D=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E8%A8%AD%E5%AE%9A" />

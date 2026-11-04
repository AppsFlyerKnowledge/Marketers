---
title: TikTok for Business—ウェブアプリ用のウェブキャンペーンを作成する
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-29T07:09:07Z'
  edited_at: '2026-10-14T09:22:48Z'
  id: 46191822292113
  locale: ja
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ja/articles/46191822292113
---
> **概要：** ウェブアプリ用のTikTok Web Ads統合を設定して、Events APIを介してTikTokにウェブコンバージョン信号を送信します。

<div id="overview" />

## オーバービュー

AppsFlyerは、ウェブアプリキャンペーンのためのTikTok Web Ads (`tiktokweb_int`)との統合をサポートしており、TikTokのEvents APIを通じてアトリビューションとコンバージョンデータを直接報告できます。このデータを、TikTokは広告ターゲティングの最適化、パフォーマンスの計測、カスタムオーディエンスの作成に活用できます。

仕組みは次のとおりです：ユーザーがTikTok広告をクリックしてウェブサイトにアクセスし、その後ウェブサイトイベント（例えば、購入やサインアップ）を完了すると、AppsFlyerはEvents APIを介してTikTokにコンバージョン信号を送信します。TikTokはこのデータを使用して広告ターゲティングを最適化し、キャンペーンのパフォーマンスを測定します。

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/web-performance-measurement-overview">AppsFlyer Web Attribution - Overview</Anchor>

<div id="important" />

> 🚧 **【重要】**
>
> 現在、統合はEvents APIを介して再エンゲージメントのポストバックを送信することをサポートしていません。

<div id="prerequisites" />

### 事前準備

ウェブアプリ用のTikTok Web Ads統合を有効にする前に、次のことを確認してください：

* AppsFlyerに設定されたウェブアプリ
* <Anchor target="_blank" href="https://getstarted.tiktok.com/grow-your-business-gb">TikTok Ads Manager</Anchor>のビジネスアカウント

<div id="how-to-set-up-tiktok-web-ads-for-your-website-app" />

### ウェブアプリ用のTikTok Web Adsを設定する方法

設定には、TikTok Web AdsとAppsFlyerの間の統合を定義し、TikTok Ads Managerでキャンペーンを構成することが含まれます。以下の部分が含まれます：

* 第1部：AppsFlyer管理画面でTikTok Web広告の連携を設定する（必須）
* 第1部：TikTok AdsでAppsFlyerの連携を設定する(必須)

<div id="part-1-set-up-tiktok-web-ads-integration-in-appsflyer" />

## 第1部：AppsFlyer上でのTikTok Web Adsの連携設定

まず、TikTokのWeb連携を有効にし、AppsFlyerがEvents APIへ送信するポストバックの内容を設定してください。

<div id="1-activate-the-tiktok-ads-integration" />

<Accordion title="1.TikTok Ads Web連携の有効化">

TikTok Ad Web連携を有効にするには：

1. AppsFlyer管理画面 左メニュー **連携** > **Partner Marketplace** へ移動します。
2. **TikTok For Business - Advanced SRN**（または`tiktokweb_int`）を検索して選択します。
3. **連携の設定**をクリックします。連携設定画面へ移動してください。
4. **連携**タブにて、**パートナーを有効にする**をオンにしてください。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。
5. **Pixel ID：Pixel ID を入力してください。それを生成するか、<Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">TikTokのドキュメント</Anchor>の指示に従ってTikTok Ads Managerから取得できます。**
6. **Access Token：Access Tokenを入力してください。生成または取得するには、同じ<Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">TikTokのドキュメント</Anchor>に従ってください。**
7. **ユーザーの個人情報のTikTok Adsでの使用を制限する（CCPA）：このトグルをオンにすると、<Anchor target="_blank" href="/marketers/ja/docs/send-opendsr-api-requests">CCPAに沿ったデータ保護の遵守</Anchor>が可能になります。**

<div id="note" />

> 📘 **注意**
>
> CCPAコンプライアンスを有効にすると、カリフォルニア州や米国の他の敏感な州に拠点を置くTikTok Web Adsユーザーからのデータが制限されます。

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2.アプリ内イベントのポストバック設定">

AppsFlyerがTikTok Adsに送信するウェブコンバージョンイベントを定義するには、AppsFlyerイベントをTikTok Web Adsイベントにマッピングします。これらのポストバックはTikTok Ads Managerで表示でき、TikTokはマッピングされたイベントをキャンペーンの最適化と報告に使用します。

アプリ内イベントのポストバック設定

1. **アプリ内イベントポストバック**を有効にします。
2. 必要に応じて、アプリ内イベントポストバックウィンドウを設定します。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック構成</Anchor>におけるアプリ内イベントポストバックウィンドウの設定について詳しく読む。
3. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
4. **AppsFlyer側のSDKイベント名**の列で、ドロップダウンのリストからイベント名を選択してください。AppsFlyerは、あなたのウェブサイトに統合されたWeb SDKまたはAppsFlyerに送信するサーバー間（S2S）イベントからイベント名を受け取ります。
5. **パートナーイベントにマッピングされた**列で、最も適切な事前定義されたパートナーイベントを選択してください。
6. **ユーザーから**列で、適切なオプションを選択してください：
   * **このパートナーのみ**、TikTok Web Adsに帰属するイベントを送信するため。
   * **すべてのメディアソース、オーガニックを含む**、帰属元に関係なくすべてのイベントを送信するため。
7. **送信データ**の項目で、収益値を送信するかどうかを選択します。詳細：ポストバックに含めるデータ
8. ［任意］**条件を追加**アイコンをクリックして、ポストバックする<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">イベントの条件を設定可能です。</Anchor>
9. **連携を保存**をクリックします。

<div id="note-2" />

<div id="note-1" />

> 📘 **注意**
>
> * 購入イベントを設定する場合は、**送信データ**項目は**イベント値と収益を送信**と設定します。他のオプションを選択した場合はポストバックに失敗します。
> * また、現在収益の値を含めることができるのは購入(Purchase)イベントのみです。

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-tiktok-web-ads" />

## パート2:TikTok Ads上におけるAppsFlyerとの連携設定

TikTok Ads Managerで次の手順を完了してください。

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1.キャンペーンの種類、目的、目標の設定">

AppsFlyerから送信された任意の事前定義されたアプリ内イベントをキャンペーン目標として選択できます。ウェブサイトのコンバージョン目標に合致するキャンペーン目標を選択してください。例えば、ウェブサイトへのトラフィックを促進することや、サイト内コンバージョンの最適化です。

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2.遷移先URLの設定">

1. **宛先**の下、**ウェブサイトURL**フィールドに、広告をクリックした後にユーザーが到達するページのURLを入力してください。

   **ウェブサイトURL**は主要な宛先オプションです。ユーザーは広告をクリックし、コンバージョンイベントを完了するために直接ウェブサイトに到達します。
2. **[代替] AF帰属リンク（OneLink）：** ユーザーをモバイルアプリにリダイレクトし、ウェブサイトにフォールバックする場合は、代わりにAF帰属リンク（OneLink）を宛先URLとして使用できます。
3. **URLパラメータを構築**をクリックして、宛先URLにURLパラメータを追加します。
4. **カスタムパラメータ**の項目で、**パラメータを追加**をクリックしてください。
5. AppsFlyerのパラメータをTikTokの値にマッピングしてください。

| AppsFlyerパラメータ | TikTokのマップする値 |
| --- | --- |
| `pid` | `tiktokweb_int` |
| `c` | `__campaign_name__` |
| `af_c_id` | `__campaign_id__` |
| `af_adset` | `__aid_name__` |
| `af_adset_id` | `__aid__` |
| `af_ad` | `__cid_name__` |
| `af_ad_id` | `__cid__` |

   <div id="note-3" />

   > 📘 **注意**
   >
   > `campaign-name_web`*campaign-name\_web キャンペーン分析を簡素化するために、キャンペーン名の冒頭または末尾に、キャンペーンタイプを示す\_webまたは\_mobileを追加することをオススメします。（例：campaign-name\_web）


   URLパラメータの設定とトラフィックソースの解決に関するベストプラクティスについては、<Anchor target="_blank" href="/marketers/ja/docs/about-traffic-source-resolution">トラフィックソースの解決について</Anchor>を参照してください。

   結果として得られるURLの例：

   ```http
   https://www.example.com?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__
   ```

   <div id="note-4" />

   > 📘 **注意**
   >
   > TikTokは、広告がクリックされたときに宛先URLに`ttclid={{ttclid}}`を自動的に追加します。


</Accordion>

<div id="measure-cost-clicks-and-impressions" />

<div id="view-web-attribution-data" />

## ウェブ帰属データを表示

ウェブコンバージョンイベントは、`tiktokweb_int` PIDの下で`media_source`フィールドに報告されます。ウェブ帰属データを表示するには、生データレポートを使用し、`media_source = tiktokweb_int`でフィルタリングしてTikTokウェブサイトアプリのコンバージョンを特定します。

ウェブサイトアプリキャンペーンのダッシュボードレポートはまだ利用できません。他のチャネルと並行してウェブキャンペーンのパフォーマンスを分析できる統一されたレポートビューが、将来のリリースに向けて計画されています。

<div id="traits-and-limitations" />

## 特徴と制限事項

| 項目 | 備考 |
| --- | --- |
| （コスト連携・収益管理） | TikTok広告（`tiktokglobal_int`）のウェブサイトアプリキャンペーンのコストデータはダッシュボードに表示されず、**すべてのコスト**レポートを除いて、コストETLレポートにも表示されません。   <br />**すべてのコスト**レポートでウェブサイトアプリキャンペーンのTikTokコストデータを取得するには、`tiktokglobal_int`を介してTikTok広告アカウントをTikTokコスト統合に接続してください。**コスト設定**ページまたは**コスト**タブを使用します。 |
| クリック数とインプレッション数 | ウェブサイトアプリキャンペーンのクリック数とインプレッションは現在TikTokから利用できません。 |
| リエンゲージメント | イベントAPIを介した再エンゲージメントポストバックは現在サポートされていません。 |

<div data-zendesk-anchors="overview=%E3%82%AA%E3%83%BC%E3%83%90%E3%83%BC%E3%83%93%E3%83%A5%E3%83%BC h_01KQC152Q49R7P96BPMMZGVZWS=%E3%82%AA%E3%83%BC%E3%83%90%E3%83%BC%E3%83%93%E3%83%A5%E3%83%BC h_01KQC25PY3PPRTQBJ7K8NV3JWQ=%E5%8F%82%E7%85%A7 h_01KQC152Q42VT7XKTGCEJV7V7S=%E9%87%8D%E8%A6%81 prerequisites=%E4%BA%8B%E5%89%8D%E6%BA%96%E5%82%99 h_01KQC152Q4A31VJ1JTXWJG6CN0=%E4%BA%8B%E5%89%8D%E6%BA%96%E5%82%99 how-to-set-up-tiktok-ads-for-your-website-app=%E3%82%A6%E3%82%A7%E3%83%96%E3%82%A2%E3%83%97%E3%83%AA%E7%94%A8%E3%81%AEtiktok-web-ads%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 h_01KQC152Q4S1VTK7BGWPHHD27W=%E3%82%A6%E3%82%A7%E3%83%96%E3%82%A2%E3%83%97%E3%83%AA%E7%94%A8%E3%81%AEtiktok-web-ads%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 part-1-set-up-tiktok-ads-integration-in-appsflyer=%E7%AC%AC1%E9%83%A8appsflyer%E4%B8%8A%E3%81%A7%E3%81%AEtiktok-web-ads%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01KQC152Q4J5ZCSFVM8EZ8ZBTZ=%E7%AC%AC1%E9%83%A8appsflyer%E4%B8%8A%E3%81%A7%E3%81%AEtiktok-web-ads%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01KQC152Q4WDH8W6AVV679JPGS=1-activate-the-tiktok-ads-integration h_01KQC152Q492SBJMJ3J10B1R84=%E6%B3%A8%E6%84%8F h_01KQC152Q4QWF2996MBS0BYCK7=2-set-inapp-event-postbacks h_01KQC152Q4561EWHVKB7A1AWDX=%E6%B3%A8%E6%84%8F-1 part-2-set-up-appsflyer-integration-in-tiktok-ads=%E3%83%91%E3%83%BC%E3%83%882tiktok-ads%E4%B8%8A%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bappsflyer%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01KQC152Q4NKQHF75Y14XCCFNH=%E3%83%91%E3%83%BC%E3%83%882tiktok-ads%E4%B8%8A%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bappsflyer%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01KQC152Q4TMJ0F09Q1PZYV71A=1-set-the-campaign-type-objective-and-goals h_01KQC152Q414XNHHR0Q2B8ZCST=2-set-destination-url h_01KQC152Q4F3WQKETR34WRHACT=%E6%B3%A8%E6%84%8F-2 h_01KQC152Q4BYHRW52BYBJHBGJ4=%E6%B3%A8%E6%84%8F-3 view-web-attribution-data=%E3%82%A6%E3%82%A7%E3%83%96%E5%B8%B0%E5%B1%9E%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E8%A1%A8%E7%A4%BA h_01KQC152Q45QE5M5BGD4RJNFR9=%E3%82%A6%E3%82%A7%E3%83%96%E5%B8%B0%E5%B1%9E%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E8%A1%A8%E7%A4%BA traits-and-limitations=%E7%89%B9%E5%BE%B4%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KQC152Q45WC7HNZ64T98JJ6Y=%E7%89%B9%E5%BE%B4%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />

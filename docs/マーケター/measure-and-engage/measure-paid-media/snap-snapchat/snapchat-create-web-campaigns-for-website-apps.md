---
title: Snapchat—ウェブサイトアプリ向けのウェブキャンペーンを作成する
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
  created_at: '2026-04-29T09:02:24Z'
  edited_at: '2026-10-14T09:22:51Z'
  id: 46196482479249
  locale: ja
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ja/articles/46196482479249
---
> **概要：** ウェブサイトアプリにSnapchatのWeb広告連携を設定し、Conversion APIを通じてウェブコンバージョンシグナルをSnapchatに送信します。

<div id="overview" />

## オーバービュー

AppsFlyerはSnapchat Web Adsとの連携をサポートしています(`snapweb_int`ウェブサイトアプリのキャンペーン用で、SnapchatのConversion APIを通じてアトリビューションやコンバージョンデータを直接報告できます。このデータは、Metaが広告ターゲティングの最適化、パフォーマンスの測定、カスタムオーディエンスの構築に活用できます。

仕組みはこうです:ユーザーがSnapchatの広告をクリックしてあなたのウェブサイトにたどり着き、その後ウェブサイトイベント(例えば購入やサインアップ)を完了すると、AppsFlyerはコンバージョンAPIを通じてそのコンバージョンシグナルをSnapchatに送信します。Snapchatはこのデータを活用して広告ターゲティングの最適化やキャンペーンのパフォーマンス測定を行います。

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/web-performance-measurement-overview">AppsFlyer Web Attribution - Overview</Anchor>

<div id="important" />

> 🚧 **【重要】**
>
> 現時点では、この統合はConversionAPI経由で再関与ポストバックを送信する機能がありません。

<div id="prerequisites" />

### 事前準備

ウェブサイトアプリでSnapchat Web Ads連携を有効にする前に、以下のものを確認してください:

* AppsFlyerで設定したウェブサイトアプリ
* ビジネスアカウント <Anchor target="_blank" href="https://ads.snapchat.com/">Snapchat広告マネージャー</Anchor>

<div id="how-to-set-up-snapchat-ads-for-your-website-app" />

### ウェブサイトアプリでSnapchat Web広告を設定する方法

セットアップには、Snapchat Web AdsとAppsFlyerの連携を定義し、Snapchat Ads Managerでキャンペーンを設定することが含まれます。以下のステップが含まれます:

* 第1部：AppsFlyerでSnapchat Web Adsの連携を設定する(必須)
* 第1部：Snapchat Web AdsでAppsFlyer連携を設定する(必須)

<div id="part-1-set-up-snapchat-ads-integration-in-appsflyer" />

## 第1部：AppsFlyerでSnapchat Web Adsの連携を設定する

まずはSnapchatのウェブ広告連携を有効にしてください。次に、AppsFlyerがConversion APIに送信するポストバックを設定しましょう。

<div id="1-activate-the-snapchat-ads-integration" />

<Accordion title="1.Snapchatのウェブ広告連携を有効化してください">

Snapchatのウェブ広告連携を有効にするには:

1. AppsFlyer管理画面左メニュー **連携** > **パートナーマーケットプレイス**へ移動します。
2. 検索 **Snapchat** そして選択します。
3. **連携の設定**をクリックします。連携設定画面へ移動してください。
4. **連携**タブにて、**パートナーを有効にする**をオンにしてください。このパートナーと連携を続ける限り、トグルをオンにしておく必要があります。
5. **Pixel ID：Pixel ID を入力してください。Snapchat広告マネージャーから生成または取得できるのは、以下の指示に従うことです。 <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">Snapchatウェブ広告のドキュメント</Anchor>.**
6. **Access Token：Access Tokenを入力してください。作成または取得するには、 <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">公式のSnapchatウェブ広告ドキュメントに記載されている指示</Anchor>.**

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2.アプリ内イベントのポストバック設定">

AppsFlyerのイベントをSnapchat Web広告のイベントにマッピングすることで、AppsFlyerがどのウェブコンバージョンイベントをSnapchat広告に送信するかを定義できます。これらのポストバックはSnapchat広告マネージャーで閲覧可能です。Snapchatはマッピングされたイベントをキャンペーンの最適化と報告に活用しています。

アプリ内イベントのポストバック設定

1. **アプリ内イベントポストバック**を有効にします。
2. 必要に応じて、アプリ内のイベントのポストバックウィンドウを設定してください。詳細：<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントのポストバック設定</Anchor>
3. **イベントを追加**をクリックして、SDKイベントをリストに追加してください。
4. **AppsFlyer側のSDKイベント名**の列で、ドロップダウンのリストからイベント名を選択してください。AppsFlyerは、ウェブサイトに統合されたWeb SDKまたはAppsFlyerに送信したサーバー間(S2S)イベントからイベント名を受け取ります。
5. では **パートナーイベントにマッピング** 列から、リストから最も適した事前定義されたパートナーイベントを選択します。
6. では **以下のユーザーへ** 列で、適切なオプションを選択してください:
   * **このパートナーだけ** Snapchatのウェブ広告に起因するイベントを送信します。
   * **有機メディアを含むすべてのメディアソース**は、帰属の出典に関係なくすべてのイベントを送信することを意味します。
7. では **含まれます** カラムで、収益値付きのイベントを送信するかどうかを選択します。詳細：ポストバックに含めるデータ
8. ［任意］**条件を追加**アイコンをクリックして、ポストバックする<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">イベントの条件を設定可能です。</Anchor>
9. **連携を保存**をクリックします。

<div id="note-2" />

<div id="note-1" />

<div id="note" />

> 📘 **注意**
>
> * 購入イベントを設定する場合は、**送信データ**項目は**イベント値と収益を送信**と設定します。他のオプションを選択するとポストバックが失敗します。
> * 現在は、購入イベントのみを収益に含める設定が可能です。

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-snapchat-ads" />

## パート2:Snapchat Web AdsでAppsFlyerの連携を設定する

Snapchat広告マネージャーで以下の手順を実行してください。

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1.キャンペーンの種類、目的、目標の設定">

AppsFlyerから送信される任意の事前定義されたアプリ内イベントをキャンペーン目標として選択できます。ウェブサイトのコンバージョン目標に合ったキャンペーン目標を選択してください。例えば、ウェブサイトへのトラフィック獲得やオンサイトコンバージョンの最適化などです。

</Accordion>

<div id="2-set-the-destination-url" />

<Accordion title="2.宛先URLを設定してください">

1. アンダー **行き先**、 **ウェブサイトのURL** フィールドに、広告をクリックしてユーザーがたどり着くページのURLを入力してください。**ウェブサイトのURL** が主な目的地の選択肢です。ユーザーは広告をクリックすると、直接あなたのウェブサイトにアクセスしてコンバージョンイベントを完了できます。
2. **[代替案]AF帰属リンク(OneLink):** モバイルアプリにリダイレクトし、ウェブサイトへのフォールバックを設けたい場合は、代わりにAFの帰属リンク(OneLink)を宛先URLとして使うことができます。
3. カチッ **URLパラメータを作成する** 宛先URLにURLパラメータを追加するために。
4. **カスタムパラメータ**の項目で、**パラメータを追加**をクリックしてください。
5. AppsFlyerのパラメータをSnapchatの値にマッピングします:

| AppsFlyerパラメータ | マッピングされたSnapchatの価値 |
| --- | --- |
| `pid` | `snapweb_int` |
| `c` * | `{{campaign.name}}` |
| `af_c_id` | `{{campaign.id}}` |
| `af_adset` | `{{adSet.name}}` |
| `af_adset_id` | `{{adSet.id}}` |
| `af_ad` | `{{creative.name}}` |
| `af_ad_id` | `{{ad.id}}` |
| `af_channel` | `{{site_source_name}}` |

   `campaign-name_web`*campaign-name\_web キャンペーン分析を簡素化するために、キャンペーン名の冒頭または末尾に、キャンペーンタイプを示す\_webまたは\_mobileを追加することをオススメします。（例：campaign-name\_web）

   URLパラメータ設定およびトラフィックソース解決のベストプラクティスについては、以下をご覧ください <Anchor target="_blank" href="/marketers/ja/docs/about-traffic-source-resolution">トラフィックソースの解決について</Anchor>.

   その結果得られるURLの例:

   ```http
   https://www.example.com?pid=snapweb_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}
   ```

<div id="note-3" />

> 📘 **注意**
>
> Metaは、広告がクリックされると、`ScCid={{ScCid}}` を宛先URLに自動的に追加します。

</Accordion>

<div id="view-web-attribution-data" />

## ウェブアトリビューションデータの閲覧

設定後にアトリビューションデータを確認する際に期待すべきことは以下の通りです:

* **生データのエクスポートとAPI応答** Snap Webを `media_source` Snapウェブ活動用のフィールドです。
* ウェブキャンペーンの設定の詳細を確認するには、 `original_url` を示すフィールド `snapchat_int` ウェブキャンペーン作成時に使われるPIDとして。

> 📘 **注意**
>
> ウェブサイトアプリのキャンペーンのダッシュボードレポートはまだ利用できません。ウェブキャンペーンのパフォーマンスを他のチャネルと並べて分析できる統合レポートビューが今後リリースされる予定です。

<div id="measure-web-attribution-data-with-web-cost" />

## ウェブコストでウェブ帰属データを測定する

Snapchat広告からウェブアトリビューションデータおよびウェブコストデータの完全なパフォーマンスビューを得るには、ダッシュボードや <Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">コストETLレポート</Anchor>、ちゃんと持ってるか確認して <Anchor target="_blank" href="/marketers/ja/docs/roi360-onboarding-guide#roi360について">ROI360パッケージ</Anchor>、次のセットアップを完了します:

1. 費用をウェブサイトアプリに連携させて`snapchat_int` (経由ではない) `snapweb_int`) **費用** タブまたは **コスト設定** ページ。コストと結びつける方法の詳細については、こちらをご覧ください。 <Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiの有効化">コストデータを測定するためのROI360コストAPIを設定しましょう</Anchor>.
2. キャンペーンIDを含めてください(`af_c_id`ランディングページのURLに記載されています。URLにキャンペーンの階層全体を含め、コスト、クリック、インプレッションをウェブアトリビューションと最も細かくマッチングしたものを確認しましょう。

<div id="traits-and-limitations" />

## 特徴と制限事項

| 項目 | 内容 |
| --- | --- |
| クリック数とインプレッション数 | ウェブキャンペーンのクリック数とインプレッション数には <Anchor target="_blank" href="/marketers/ja/docs/roi360-onboarding-guide">ROI360サブスクリプション</Anchor>. |
| リエンゲージメント | ConversionAPIを使った再エンゲージメントポストバックは現在サポートされていません。 |

<div data-zendesk-anchors="overview=%E3%82%AA%E3%83%BC%E3%83%90%E3%83%BC%E3%83%93%E3%83%A5%E3%83%BC h_01KQC7RA5R1PS69N3015WY4QRY=%E3%82%AA%E3%83%BC%E3%83%90%E3%83%BC%E3%83%93%E3%83%A5%E3%83%BC h_01KQC80MBB1KCVVNDSFSJHG5ZT=%E5%8F%82%E7%85%A7 h_01KQC7RA5RAY6R70GNHCYWAMRC=%E9%87%8D%E8%A6%81 prerequisites=%E4%BA%8B%E5%89%8D%E6%BA%96%E5%82%99 h_01KQC7RA5R02QV60T81NX055DM=%E4%BA%8B%E5%89%8D%E6%BA%96%E5%82%99 how-to-set-up-snapchat-ads-for-your-website-app=%E3%82%A6%E3%82%A7%E3%83%96%E3%82%B5%E3%82%A4%E3%83%88%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A7snapchat-web%E5%BA%83%E5%91%8A%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 h_01KQC7RA5RPWP0X927ENN6KJ9V=%E3%82%A6%E3%82%A7%E3%83%96%E3%82%B5%E3%82%A4%E3%83%88%E3%82%A2%E3%83%97%E3%83%AA%E3%81%A7snapchat-web%E5%BA%83%E5%91%8A%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 part-1-set-up-snapchat-ads-integration-in-appsflyer=%E7%AC%AC1%E9%83%A8appsflyer%E3%81%A7snapchat-web-ads%E3%81%AE%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KQC7RA5RY1HF9VHC332FVBFR=%E7%AC%AC1%E9%83%A8appsflyer%E3%81%A7snapchat-web-ads%E3%81%AE%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KQC7RA5RJXR5N13SYW3QMMDQ=1-activate-the-snapchat-ads-integration h_01KQC7RA5R3TZZ8PPHHC8EXPG1=2-set-inapp-event-postbacks h_01KQC7RA5RZVTM2X3N6WXRTAT8=%E6%B3%A8%E6%84%8F part-2-set-up-appsflyer-integration-in-snapchat-ads=%E3%83%91%E3%83%BC%E3%83%882snapchat-web-ads%E3%81%A7appsflyer%E3%81%AE%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KQC7RA5REPX0WDDHT7YWDHMC=%E3%83%91%E3%83%BC%E3%83%882snapchat-web-ads%E3%81%A7appsflyer%E3%81%AE%E9%80%A3%E6%90%BA%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01KQC7RA5R8MDFAF9R5YH1TFPX=1-set-the-campaign-type-objective-and-goals h_01KQC7RA5SB11HRSQR493PM121=2-set-the-destination-url h_01KQC7RA5S422C22YQX1VQ4R7A=%E6%B3%A8%E6%84%8F-1 view-web-attribution-data=%E3%82%A6%E3%82%A7%E3%83%96%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%96%B2%E8%A6%A7 h_01KQC7RA5SKRWGGCKV71MV8J56=%E3%82%A6%E3%82%A7%E3%83%96%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%96%B2%E8%A6%A7 h_01KQC7RA5S5VWHT4DW2MPSMNY0=%E6%B3%A8%E6%84%8F-2 measure-web-attribution-data-with-web-cost=%E3%82%A6%E3%82%A7%E3%83%96%E3%82%B3%E3%82%B9%E3%83%88%E3%81%A7%E3%82%A6%E3%82%A7%E3%83%96%E5%B8%B0%E5%B1%9E%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E6%B8%AC%E5%AE%9A%E3%81%99%E3%82%8B h_01KQC7XYSWPTHVDY5R3EG8H4K2=%E3%82%A6%E3%82%A7%E3%83%96%E3%82%B3%E3%82%B9%E3%83%88%E3%81%A7%E3%82%A6%E3%82%A7%E3%83%96%E5%B8%B0%E5%B1%9E%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E6%B8%AC%E5%AE%9A%E3%81%99%E3%82%8B traits-and-limitations=%E7%89%B9%E5%BE%B4%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KQC7RA5SSZB8M8G00NTXG71K=%E7%89%B9%E5%BE%B4%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />

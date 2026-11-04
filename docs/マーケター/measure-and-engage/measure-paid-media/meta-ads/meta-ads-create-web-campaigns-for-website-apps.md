---
title: Meta広告｜Webアプリ向けWebキャンペーンの作成
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
  created_at: '2026-04-28T14:18:14Z'
  edited_at: '2026-10-28T09:16:48Z'
  id: 46172666260241
  locale: ja
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ja/articles/46172666260241
---
> **概要：** WebアプリのMeta広告連携を設定し、コンバージョンAPI（CAPI）経由でWebコンバージョンのシグナルをMetaに送信します。これにより、Metaは広告ターゲティングの最適化とキャンペーンのパフォーマンス計測を行えます。

<div id="overview" />

## 概要

AppsFlyerは、Webアプリのキャンペーン向けに、Meta広告（`metaweb_int`）との連携をサポートしています。この連携では、MetaのコンバージョンAPI（CAPI）を通じて、アトリビューションデータとコンバージョンデータを直接報告できます。Metaは、このデータを広告ターゲティングの最適化、パフォーマンスの計測、カスタムオーディエンスの作成に利用します。

ユーザーがMeta広告をクリックしてWebサイトに到達すると、AppsFlyerは、購入や登録など、ユーザーが完了したコンバージョンイベントを取得し、CAPI経由でMetaにシグナルを送信します。 Metaは、このデータをターゲティングの改善とキャンペーン成果の評価に利用します。

<div id="see-also-1" />

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/web-performance-measurement-overview">Web Performance Measurement｜概要</Anchor>

> 📘 **注意**
>
> 現在のMeta Web連携では、CAPIへのリエンゲージメントポストバックの送信はサポートされていません。

<div id="prerequisites" />

### 前提条件

Meta広告連携を有効にする前に、以下を準備してください。

* AppsFlyerで設定済みのWebアプリ。詳細は、以下を参照してください。
  * <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#web">Webアプリの追加</Anchor>
  * <Anchor target="_blank" href="/marketers/ja/docs/configure-web-performance-measurement-settings">Web Performance Measurementの設定</Anchor>
* <Anchor target="_blank" href="https://www.facebook.com/business/help/1710077379203657?id=180505742745347">Metaビジネスマネージャのビジネスアカウント</Anchor>。

<div id="set-up-meta-ads-web-campaigns-for-website-apps" />

## Webアプリ向けMeta広告のWebキャンペーンの設定

設定では、Meta広告とAppsFlyerの連携を定義し、両プラットフォームでキャンペーンを設定します。以下の2つのパートを順番に完了してください。

* [パート1：AppsFlyerでMeta広告連携を設定する](#set-up-meta-ads-integration-in-appsflyer)（必須）
* [パート2：Meta広告でAppsFlyer連携を設定する](#パート2meta広告でのappsflyer連携の設定)（必須）

<div id="part-1-set-up-meta-ads-integration-in-appsflyer" />

## パート1：AppsFlyerでのMeta広告連携の設定

まず、Meta広告連携を有効にし、AppsFlyerからCAPIに送信するポストバックを定義します。

<div id="step-1-activate-the-meta-ads-integration" />

<Accordion title="ステップ1：Meta広告連携の有効化">

Meta広告連携を有効にするには、以下の手順に従ってください。

1. AppsFlyerのサイドメニューから、**［連携］**><strong>［パートナーマーケットプレイス］</strong>に移動します。
2. **Meta広告**を検索し、選択します。
3. <strong>［連携を設定］</strong>をクリックします。<strong>［連携済みパートナー］</strong>の設定ページが表示されます。
4. <strong>［連携］</strong>タブで、<strong>［パートナーを有効にする］</strong>をオンにします。

   <div id="note-1" />

   > 📘 **注意**
   >
   > このパートナーとの連携を継続する間は、トグルをオン（<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">有効</Anchor>）のままにしてください。

5. <strong>［ピクセルID］</strong>欄に入力します。 Meta広告マネージャでピクセルIDを取得するには、以下の手順に従ってください。
   1. <span class="af-ol-a"></span><Anchor target="_blank" href="https://www.facebook.com/ads/manager">広告マネージャ</Anchor>のサイドメニューから、**［すべてのツール］**><strong>［イベントマネージャ］</strong>に移動します。

      <div id="note-2" />

      > 📘 **注意**
      >
      > 右上のドロップダウンで、対象のビジネスが選択されていることを確認してください。

   2. **イベントマネージャ**のサイドメニューで、<strong>［データソース］</strong>を選択します。ピクセルの一覧が表示されます。選択したビジネスのピクセルがない場合は、同じ画面から作成できます。
   3. ピクセル名の下に表示されるピクセルIDをコピーし、AppsFlyerの<strong>［ピクセルID］</strong>欄に貼り付けます。
6. <strong>［アクセストークン］</strong>欄に入力します。アクセストークンの取得方法は、<Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token">こちらの手順</Anchor>を参照してください。
7. <Anchor target="_blank" href="/marketers/ja/docs/send-opendsr-api-requests">データ保護法</Anchor>に対応するには、<strong>［Meta広告によるユーザーの個人情報の利用を制限（CCPA）］</strong>をオンにします。

   <div id="note-3" />

   > 📘 **注意**
   >
   > CCPAのプライバシー規制に対応すると、カリフォルニア州のMeta広告ユーザーから取得するデータが制限されます。


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="ステップ2：アプリ内イベントポストバックの設定">

AppsFlyerのイベントをMeta広告のイベントにマッピングすることで、Meta広告に送信するWebコンバージョンイベントを定義できます。これらのポストバックは、<Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Metaイベントマネージャ</Anchor>で確認できます。 Metaは、マッピングされたイベントをキャンペーンの最適化とレポートに利用します。

アプリ内イベントポストバックを設定するには、以下の手順に従ってください。

1. <strong>［アプリ内イベントポストバック］</strong>をオンにします。
2. 必要に応じて、アプリ内イベントポストバック期間を設定します。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック期間の設定</Anchor>を参照してください。
3. <strong>［イベントを追加］</strong>をクリックし、リストにイベントを追加します。
4. <strong>［AppsFlyerイベント］</strong>列のドロップダウンリストから、イベント名を選択します。 AppsFlyerは、Webサイトに実装したWeb SDK、またはAppsFlyerに送信されたサーバー間（S2S）イベントからイベント名を受信します。
5. <strong>［マッピング先のパートナーイベント］</strong>列のドロップダウンリストから、最適な定義済みパートナーイベントを選択するか、**CUSTOM**を選択します。
6. <strong>［送信対象ユーザー］</strong>列で、イベントの送信対象を選択します。
   * **このパートナーのみ**：このイベントがMeta広告にアトリビューションされた場合にのみ、ポストバックを送信します。
   * **オーガニックを含むすべてのメディアソース**：いずれかのパートナーにアトリビューションされたイベントと、オーガニックのイベントについてポストバックを送信します。
7. <strong>［送信データ］</strong>列で、イベントに収益値を含めて送信するかどうかを選択します。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#ポストバックに含めるデータ">ポストバックに含めるデータ</Anchor>を参照してください。

   <div id="note-5" />

   <div id="note-4" />

   <div id="important" />

   > 🚧 **重要！**
   >
   > 購入イベントを設定する場合は、<strong>［送信データ］</strong>列で<strong>［イベント値と収益］</strong>を選択してください。それ以外の選択肢を選ぶと、ポストバックが失敗します。

8. ［任意］<strong>［条件を追加］</strong>アイコンをクリックして、イベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定します</Anchor>。
9. <strong>［連携を保存］</strong>をクリックします。

> 📘 **Note**
>
> WebサイトでMetaピクセルも使用している場合は、AppsFlyerがイベントの重複を排除できるよう、AppsFlyerとMetaの両方に同じイベントIDを送信してください。
>
> * AppsFlyerに送信するイベントペイロードに`af_customer_event_id`を含めます。Web SDKの場合は`eventValue`内、サーバー間（S2S）APIの場合は`event_value`内に指定します。
> * 対応するピクセルイベントにも、同じ値を送信します。
>
> AppsFlyerは、この値をイベントIDとしてMetaに転送します。 Metaはこの値を使い、AppsFlyerから受信したサーバー側イベントとピクセルイベントの重複を排除します。これにより、AppsFlyerはコンバージョンを1回だけカウントします。
>
> `af_customer_event_id`を送信しない場合、AppsFlyerがイベントIDを自動生成します。このIDは、ピクセルイベントのIDとは一致しません。
>
> 詳細は、<Anchor target="_blank" href="/marketers/ja/docs/integrate-appsflyer-web-sdk">［ベータ版］AppsFlyer Web SDKの実装</Anchor>を参照してください。

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-meta-ads" />

## パート2：Meta広告でのAppsFlyer連携の設定

以下の手順をMeta広告マネージャで行います。

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="ステップ1：キャンペーンの種類、目的、目標の設定">

1. Meta広告にログインし、キャンペーンを作成します。
2. <strong>［キャンペーンの目的］</strong>で、以下のいずれかを選択します。
   * **売上**：特定のイベント（主要なKPI）に向けてMetaが最適化します。
   * **トラフィック**：広告クリックに向けてMetaが最適化します。他にKPIがない場合、または他のKPIイベントの件数が少なすぎる場合にのみ使用してください。
3. ［任意］カスタムの目的を追加する場合は、以下の手順に従ってください。

   1. Meta広告で、キャンペーンの目的に設定するカスタムイベントを選択し、コンバージョンアクションとして指定します。
   2. AppsFlyerの**Meta Web連携**ページで、<strong>［アプリ内イベントポストバック］</strong>の<strong>［マッピング先のパートナーイベント］</strong>列から、AppsFlyerのイベントをカスタムパートナーイベントにマッピングし、Meta広告のコンバージョンアクションと同じ名前を付けます。

   <div id="note-6" />

   > 📘 **注意**
   >
   > Metaのキャンペーン目的の詳細は、<Anchor target="_blank" href="https://www.facebook.com/business/help/175683976191028">Metaのドキュメント</Anchor>を参照してください。

4. <strong>［コンバージョンの場所］</strong>で<strong>［Webサイト］</strong>を選択します。
5. <strong>［ピクセル］</strong>には、AppsFlyerのパートナーマーケットプレイスで`metaweb_int`に入力したものと同じピクセルIDを指定します。 Metaピクセルの詳細は、<Anchor target="_blank" href="https://www.facebook.com/business/help/742478679120153">Metaのドキュメント</Anchor>を参照してください（ログインが必要です）。
6. <strong>［次へ］</strong>をクリックします。

</Accordion>

<div id="step-2-set-destination-url" />

<Accordion title="ステップ2：遷移先URLの設定">

1. <strong>［遷移先］</strong>の<strong>［WebサイトURL］</strong>欄に、広告の遷移先となるURLを入力します。以下のいずれかを選択します。

   * **WebサイトURL**：ユーザーをWebサイトに直接誘導し、購入や登録などのWebコンバージョンイベントを完了してもらいたい場合に使用します。
   * **AF計測リンク（OneLink）**：ユーザーをモバイルアプリにリダイレクトし、アプリがインストールされていない場合はWebサイトに誘導するには、AF計測リンクを使用します。これは、アプリとWebの両方のユーザーを対象とするキャンペーンに適しています。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLinkのリンクとユーザー体験の設定</Anchor>を参照してください。

   <div id="important-1" />

   > 🚧 **重要！**
   >
   > AF計測リンクを使用すると、エラーが発生する場合があります。その場合は、Metaの担当者に解決方法を問い合わせるか、遷移先URLとしてWebサイトのURLを使用してください。

2. <strong>［URLパラメータを作成］</strong>をクリックし、遷移先URLにURLパラメータを追加します。
3. <strong>［カスタムパラメータ］</strong>で、<strong>［パラメータを追加］</strong>をクリックします。
4. 以下の表に従って、AppsFlyerのパラメータを対応するMetaの値にマッピングします。

| AFのパラメータ | マッピングするMetaの値 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

生成されるURLの例：

```http
https://www.example.com?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}
```

<div id="note-7" />

> 📘 **注意**
>
> Metaは、広告がクリックされると、遷移先URLに`fbclid={{fbclid}}`を自動的に追加します。

<div id="tip" />

> 👍 **ヒント**
>
> キャンペーンの分析を容易にするため、キャンペーン名の先頭または末尾に、Webやモバイルなどのキャンペーンの種類を付けてください（例：`campaign-name_web`）。

<div id="see-also" />

> 📄 **関連情報**
>
> * 必要なパラメータをすべて含む広告URLの作成に関するベストプラクティスは、<Anchor target="_blank" href="/marketers/ja/docs/about-traffic-source-resolution">トラフィックソースの判定</Anchor>を参照してください。

</Accordion>

<div id="step-3-select-tracked-events" />

<Accordion title="ステップ3：計測対象イベントの選択">

<strong>［トラッキング］</strong>セクションで、広告で促進するコンバージョンイベントを選択します。イベントは、<Anchor target="_blank" href="https://www.facebook.com/business/help/898185560232180?id=1205376682832142">イベントマネージャ</Anchor>で設定します。

<div id="important-2" />

> 🚧 **重要！**
>
> は選択しないでください。選択すると、MetaがSRN APIを通じてこれらのコンバージョンのアトリビューションを申告するため、レポートと最適化に不整合が生じる可能性があります。

</Accordion>

<div id="view-web-attribution-data" />

## Webアトリビューションデータの確認

設定後にアトリビューションデータを確認する際の表示内容は、以下のとおりです。

* MetaのWeb上のアクティビティについて、**ローデータのエクスポートとAPIレスポンス**では、`media_source`フィールドにMeta Webが表示されます。
* Webキャンペーンの設定内容を確認するには、`original_url`フィールドを確認してください。Webキャンペーンの作成時に使用したPIDとして、`facebook_int`が表示されます。

> 📘 **注意**
>
> Webアプリのキャンペーンについては、ダッシュボードでのレポート表示はまだ利用できません。 Webキャンペーンのパフォーマンスを他のチャネルと併せて分析できる統合レポートビューは、今後のリリースで提供予定です。

<div id="measure-web-attribution-data-with-web-cost" />

## Webのコストデータとアトリビューションデータを組み合わせた計測

ダッシュボードと<Anchor target="_blank" href="/marketers/ja/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Cost ETLレポート</Anchor>で、Meta広告のWebアトリビューションデータとWebコストデータを組み合わせてパフォーマンスを総合的に把握するには、<Anchor target="_blank" href="/marketers/ja/docs/roi360-onboarding-guide#roi360について">ROI360パッケージ</Anchor>を契約し、以下の設定を完了してください。

1. <strong>［コスト］</strong>タブまたは<strong>［コスト設定］</strong>ページから、`metaweb_int`ではなく`facebook_int`を介して、コストデータをWebアプリに連携します。コスト連携の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/set-up-roi360-cost-api-to-measure-cost-data#広告費apiの有効化">コストデータ計測のためのROI360 Cost APIの設定</Anchor>を参照してください。
2. ランディングページURLにキャンペーンID（`af_c_id`）を含めます。 Webアトリビューションに紐づくコスト、クリック、インプレッションのデータを最も細かい単位で表示するには、URLにキャンペーンのすべての階層の情報が含まれていることを確認してください。

<div id="traits-and-limitations" />

## 仕様と制限事項

| 項目 | 補足 |
| --- | --- |
| クリックとインプレッション | Webキャンペーンのクリックとインプレッションを取得するには、<Anchor target="_blank" href="/marketers/ja/docs/roi360-onboarding-guide">ROI360の契約</Anchor>が必要です。 |

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01KQA78RE9FRENQAK31Q641C0N=%E6%A6%82%E8%A6%81 h_01KQC27K5KWP3A6HMM2W7N3MVB=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1 h_01KQA78RE9F82ZBVF4YZHZTEEX=%E6%B3%A8%E6%84%8F prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01KQA78RE93B09A9YH2FRB3XRR=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 set-up-meta-ads-web-campaigns=web%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91meta%E5%BA%83%E5%91%8A%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KQA78RE9J681CJ8DQNWJC37H=web%E3%82%A2%E3%83%97%E3%83%AA%E5%90%91%E3%81%91meta%E5%BA%83%E5%91%8A%E3%81%AEweb%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A part-1-set-up-meta-ads-integration-in-appsflyer=%E3%83%91%E3%83%BC%E3%83%881appsflyer%E3%81%A7%E3%81%AEmeta%E5%BA%83%E5%91%8A%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KQA78RE93JYCV2P0DDZC0A4B=%E3%83%91%E3%83%BC%E3%83%881appsflyer%E3%81%A7%E3%81%AEmeta%E5%BA%83%E5%91%8A%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KQA78RE94B1JSVJFWR1V9QE5=step-1-activate-the-meta-ads-integration h_01KQA78REA5VN1229F2J3QH794=%E6%B3%A8%E6%84%8F-1 h_01KQA78REANHAQ88N4MXWM832D=%E6%B3%A8%E6%84%8F-2 h_01KQA78REA08SNB0BKCJDJZ2R0=%E6%B3%A8%E6%84%8F-3 h_01KQA78REACR7QTMQWJMV6VJSF=step-2-set-inapp-event-postbacks h_01KQA78REA1EB5ZHX4HKJSW7ZD=%E9%87%8D%E8%A6%81 part-2-set-up-appsflyer-integration-in-meta-ads=%E3%83%91%E3%83%BC%E3%83%882meta%E5%BA%83%E5%91%8A%E3%81%A7%E3%81%AEappsflyer%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KQA78REAEZQPDSKZ0GRNKEJJ=%E3%83%91%E3%83%BC%E3%83%882meta%E5%BA%83%E5%91%8A%E3%81%A7%E3%81%AEappsflyer%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01KQA78REASX8JX1H37075WT82=step-1-set-the-campaign-type-objective-and-goals h_01KQA78REA5JZ44C4BE77JCHG8=%E6%B3%A8%E6%84%8F-4 h_01KQA78REAKBGQRC713FZ3J02P=step-2-set-destination-url h_01KQA78REAXZ1BFGC5BR75ZB5X=%E9%87%8D%E8%A6%81-1 h_01KQA78REARWGQDCJ4KN3FM120=%E6%B3%A8%E6%84%8F-5 h_01KQA78REA7MZSG5JZ1XX2C65P=%E3%83%92%E3%83%B3%E3%83%88 h_01KQA78REA3ZW7W9M3VFSQASB6=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1-1 h_01KQA78REASTZH19CM58M5Z43R=step-3-select-tracked-events h_01KQA78REBHCR1AHA254BTFZC6=%E9%87%8D%E8%A6%81-2 view-web-attribution-data=web%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KQA78REBK1PWXNA1PM9118TA=web%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01KQA78REBAW2SM5DRD68DP8W1=%E6%B3%A8%E6%84%8F-6 measure-web-attribution-data-with-web-cost=web%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%B5%84%E3%81%BF%E5%90%88%E3%82%8F%E3%81%9B%E3%81%9F%E8%A8%88%E6%B8%AC h_01KNM00RR9TF8JRTJXWN23MF1S=web%E3%81%AE%E3%82%B3%E3%82%B9%E3%83%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%A8%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%B5%84%E3%81%BF%E5%90%88%E3%82%8F%E3%81%9B%E3%81%9F%E8%A8%88%E6%B8%AC traits-and-limitations=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KQAE3JKMQ6ZEATDAEXBC4PT6=%E4%BB%95%E6%A7%98%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />

---
title: ビュースルーエンゲージメントの計測
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2026-10-21T18:44:01Z'
  id: 210084473
  locale: ja
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ja/articles/210084473
---
> **概要：** 広告を見たユーザーが、その後アプリをインストールした場合、その成果を広告表示に紐づけるビュースルーアトリビューションで計測します。

## 概要

ビュースルーアトリビューションは、広告を見たもののクリックしなかったユーザーのインストール、リアトリビューション、リエンゲージメントを計測します。

### ビュースルーアトリビューションの流れ

### 用語の説明

* **インプレッション：** 広告がユーザーに表示されることを指します。クリックなどのユーザーによる反応の有無は問いません。
* **インストール**：この記事では、インストール、リアトリビューション、リエンゲージメントを総称して「インストール」と表記します。
* **ビュースルーアトリビューション：** ユーザーへの広告表示後に発生したインストールを、その広告のメディアソースに紐づけて計測することを指します。

### ビュースルーアトリビューションの基本ルール

* <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#device-id-matching">デバイスIDマッチング</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#probabilistic-modeling">確率論的モデリング</Anchor>の両方に対応しています。
* [ビュースルーアトリビューション対応パートナー一覧](/docs/measure-view-through-engagements#view-vta-partner-list)に掲載されているパートナーが対応しています。

インプレッションがビュースルーアトリビューションの対象となる際は、次のルールが適用されます。

* 広告表示がビュースルー計測のルックバック期間（デフォルトは24時間）内に発生している必要があります。
* 複数のインプレッションがある場合は、最も直近のインプレッションが対象となります。
* クリックはインプレッションより優先されます。そのため、クリックスルー計測のルックバック期間内にクリックがある場合は、最も直近のクリックが成果の獲得元として計測されます。最も直近のインプレッションは、アシスト（成果への間接的な貢献）として計測されます。

### ビュースルー計測のルックバック期間

* SRN以外のメディアソースでは、広告表示を成果の計測対象とするルックバック期間を1〜24時間に設定できます。セルフレポーティングネットワーク（SRN）では、これより長い期間を設定できる場合があります。
* 期間は次のように設定します。
  * **SRN以外：** インプレッション計測リンクの`af_viewthrough_lookback`パラメータで期間を設定します。パラメータを設定しない場合は、デフォルトの24時間が適用されます。
  * **SRN**：期間はSRN側で決まります。 AppsFlyer側にも、SRN側と同じ値を設定することを推奨します。

### ビュースルーアトリビューションのレポートと指標

* **集計データ：** アドネットワークは、インプレッションの集計データをAPI経由でAppsFlyerに送信するか、インプレッションごとにデータを送信します。インプレッションのカウント方法と報告方法は、パートナーごとに定義されている点に注意してください。 関連する指標は、オーバービューダッシュボードやその他のレポートツールで確認できます。確認できる指標は次のとおりです。
  * インプレッション数：指定した期間内に広告が表示された回数です。
  * ビュースルー数：ビュースルーアトリビューションで計測されたインストール数です。
* **ローデータ**：
  * ビュースルーアトリビューションで計測されたユーザーについても、クリック経由で計測されたユーザーと同様に、ユーザー単位のデータ（ローデータ）を利用できます。ただし、一部のパートナーでは、このデータの提供が制限されています。
  * クリックデータと同様に、インプレッションデータも利用できます。
  * attributed\_touch\_typeフィールドには、*impression*という値が入ります。

## ビュースルー計測の設定と操作

<div id="set-impression-links" />

<Accordion title="インプレッションリンクの設定">

アドネットワークは、クリックスルー計測用の<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">アトリビューションリンク</Anchor>と同様に、キャンペーンなどの情報を含めたインプレッションリンクをAppsFlyerに送信します。

広告表示後のインストールを正しく計測できるよう、リンクはリアルタイムで送信されます。

リンクを作成する際は、次の点に注意してください。

* ベースURLは`https://impression.appsflyer.com`です。
* GETリクエストを使用します。
* 取得可能な場合は、IDFA、GAID、IDFVなどのデバイスIDを含めます。
* <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#probabilistic-modeling-parameters-for-ad-networks">確率論的モデリング</Anchor>用のパラメータを含めます。
* セキュリティを高めるため、SHA1を使用してデバイスIDの値をハッシュ化できます。パラメータ名は「sha1\_」で始め、その後に元のパラメータ名を続け、値にはハッシュ化したデバイスIDを指定します。パラメータ名の例：sha1\_idfa、sha1\_advertising\_id、sha1\_android\_id、sha1\_imei。

> 📄
>
>  例
>
> ```http
> https://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
> &af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
> &af_sub1={free value}&idfa={idfa value}
> ```

</Accordion>

<div id="set-custom-impression-links" />

<Accordion title="カスタムインプレッションリンクの設定">

広告主は、自社Webサイトのバナーなど、独自のメディアソースでインプレッション計測リンクを使用できます。

広告主が<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">カスタムアトリビューションリンクを作成</Anchor>すると、必要な情報を含むインプレッションリンクが生成されます。このリンクは、ユーザーが自社の広告に接触するたびに送信できます。

OneLinkで作成したカスタムインプレッションリンクは、モバイルWebサイトの訪問者を対象としたビュースルーアトリビューションにも使用できます。 詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">カスタムインプレッションURLの作成</Anchor>を参照してください。

</Accordion>

<div id="turn-off-viewthroughattribution" />

<Accordion title="ビュースルーアトリビューションの無効化">

ビュースルーアトリビューションは、デフォルトで有効になっています。 AppsFlyerが有効なインプレッション計測リンクを受信すると、そのインプレッションはアトリビューションの判定対象になります。

ビュースルーアトリビューションはデフォルトで有効なため、広告主は、ビュースルー計測の有効・無効について、アドネットワークと事前に契約上の合意をしておくことが重要です。

ビュースルーアトリビューションは、メディアソースごとに無効化できます。ビュースルーアトリビューションを無効にしている状態でインプレッションを受信した場合は、次のように扱われます。

* インプレッションの指標はダッシュボードで確認できます。
* これらのインプレッションはアトリビューションの判定対象から除外されます。

**ビュースルーアトリビューションを無効にするには、次の手順に従います。**

1. AppsFlyerのサイドメニューで、［**連携**］>［**連携中のパートナー**］を選択します。
2. 連携済みパートナーを選択します。
3. ［連携］タブで、［**インストールのビュースルー計測**］をオフにします。
4. ［**連携設定を保存**］をクリックします。

SRNの場合、AppsFlyer側でビュースルーアトリビューションを無効にしても、SRN側の設定は無効になりません。計測結果の差異を防ぐため、AppsFlyerとSRNの両方でビュースルー計測の設定を揃えてください。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HEMT7T1TB9W7ZBRPQW29SRPF=%E6%A6%82%E8%A6%81 viewthrough-attribution-flow=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%B5%81%E3%82%8C h_01HEMT7T1T6ZK4ZH7DKV3162J1=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E6%B5%81%E3%82%8C terminology=%E7%94%A8%E8%AA%9E%E3%81%AE%E8%AA%AC%E6%98%8E h_01HEMT7T1TY46QXBDS6MBF1DZ5=%E7%94%A8%E8%AA%9E%E3%81%AE%E8%AA%AC%E6%98%8E viewthrough-attribution-principles=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%9F%BA%E6%9C%AC%E3%83%AB%E3%83%BC%E3%83%AB h_01HEMT7T1THD8TVKRRJ168HKY2=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%9F%BA%E6%9C%AC%E3%83%AB%E3%83%BC%E3%83%AB viewthrough-lookback-window=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 h_01HEMT7T1TWHN2AB3Q5X36TKKB=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E3%83%AB%E3%83%83%E3%82%AF%E3%83%90%E3%83%83%E3%82%AF%E6%9C%9F%E9%96%93 viewthrough-attribution-reporting-and-metrics=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A8%E6%8C%87%E6%A8%99 h_01HEMT7T1TQNKM5GABA7VY6KR1=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%A8%E6%8C%87%E6%A8%99 viewthrough-operations=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%A8%E6%93%8D%E4%BD%9C h_01HEMT7T1T13JC75ZYY01N8PS6=%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B9%E3%83%AB%E3%83%BC%E8%A8%88%E6%B8%AC%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%A8%E6%93%8D%E4%BD%9C h_01HEMT7T1TQ3YNQ2Y0CCGPXWDX=set-impression-links h_01HEMT7T1T75MBS64JE837CJ0E=set-custom-impression-links h_01HEMT7T1T253G1CZNS9KVDFCP=turn-off-viewthroughattribution" />

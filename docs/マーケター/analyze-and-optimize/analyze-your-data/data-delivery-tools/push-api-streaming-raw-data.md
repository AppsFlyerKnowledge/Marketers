---
title: Push APIでのローデータストリーミング
metadata:
  keywords:
    - Push API
    - Real-time
    - Installation and Conversion
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:19:42Z'
  edited_at: '2026-10-14T09:39:38Z'
  id: 207034356
  locale: ja
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ja/articles/207034356
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** ローデータ計測イベントを自社サーバーのエンドポイントにストリーミングできます。

![6970_Push_API_image.png](https://files.readme.io/0bb5747a65a6ca6ed8f55f72f189b92e780649d55b766c5d295f5602745f04f5-4405028260241.png)

## Push API

Push APIは、AppsFlyer計測とSKAdNetwork（SKAN）計測により生成されたローデータを、広告主のサーバーにメッセージとしてストリーミングします。メッセージタイプとコンテンツを選択し、送信先のエンドポイントを設定できます。

利用できるメッセージタイプ、データ更新頻度および項目は、次のセクションで説明するとおり、計測を行うフレームワーク（AppsFlyerかSKAN）よって異なります。

<div id="appsflyer-attribution-messages" />

<Accordion title="AppsFlyer計測メッセージ">

メッセージの特性

| 特性 | 詳細 |
| --- | --- |
| メッセージタイプの分離 | <ul><li>メッセージはエンドポイント別（アプリごとに最大6つのエンドポイント）に分けるか、リストされている項目の値を調べてメッセージタイプを判別することができます。<ul><li>event\_name</li><li>conversion\_type</li><li>campaign\_type</li></ul></li><li>メッセージタイプ別の項目の値は、次の表にて示しています。</li></ul>**例：**<br /><br />メッセージには次の項目が含まれています：<ul><li>conversion\_type=install</li><li>campaign\_type=organic</li><li>event\_name=install</li></ul>この表を使用して、このイベントがオーガニックユーザーのインストールイベントであると判断してください。 |
| データ更新頻度 | メッセージは、AppsFlyerプラットフォームにイベントが記録された直後に送信されます。これは通常数分以内に行われます。 |
| メッセージの内容（項目） | <ul><li>メッセージに `key:value` 構造が存在します。</li><li>AppsFlyer計測の<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#field-availability-by-reporting-tool">Push API</Anchor>項目をご参照ください。</li><li>各キーはローデータ項目を表しています。<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#data-fields-dictionary">AppsFlyerのローデータ項目の説明</Anchor>を参照してください。</li><li>空白または null キーは一切送信されません。</li><li>この例には、null フィールドと空のフィールドの両方が含まれています。実際のポストバックには、空白の項目も null も含まれません。提供されている例は JSON 形式です。<ul><li>[iOS](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=0&single=true&output=csv)</li><li>[Android](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=233131974&single=true&output=csv)</li></ul></li></ul> |
| タイムスタンプ項目の形式 | <ul><li>UTCタイムスタンプ：`yyyy-mm-dd hh:mm:ss.sss` 例：`2019-09-17 00:09:00.123` のように表示されます。日本時間の18:00にイベントが発生したとします。イベント時刻は UTCの 09:00 に変換されます。記録された時刻は UTC での時間です。</li><li>選択されたタイムゾーン（アプリ固有）タイムスタンプ：`yyyy-mm-dd hh:mm:ss.sss±th:tm`　（例：`yyyy-mm-dd hh:mm:ss.sss±th:tm`）日本時間の18:00にイベントが発生したとします。表示されるイベント時刻は 18:00+09:00 として記録されます。09:00 は東京のタイムゾーンです。</li></ul> |

#### 使用可能なメッセージタイプ

<table><thead><tr><th>アトリビューションのコンテキスト</th><th>メッセージタイプ</th><th>conversion_type 項目</th><th>campaign_type 項目</th><th>event_name 項目</th><th>event_type 項目</th></tr></thead><tbody><tr><td>新規獲得</td><td>インストール\*</td><td>install</td><td><p>非オーガニック：UA</p><p>オーガニック：organic</p></td><td>install</td><td><ul><li>install</li><li>organic-install</li></ul></td></tr><tr><td>新規獲得 </td><td>新規獲得 - アプリ内イベント</td><td><span>install</span></td><td><p>非オーガニック：UA</p><p>オーガニック：organic</p></td><td>広告主が定義したイベント名</td><td><ul><li>install-in-app-event</li><li>organic-install-in-app-event</li></ul></td></tr><tr><td>リターゲティング</td><td>リエンゲージメント</td><td>re-engagement</td><td>retargeting</td><td>re-engagement</td><td>re-attribution</td></tr><tr><td>リターゲティング </td><td>リエンゲージメント アプリ内イベント</td><td>re-engagement</td><td>retargeting</td><td>広告主が定義したイベント名</td><td>re-engagement-in-app-event</td></tr><tr><td>リターゲティング </td><td>リアトリビューション </td><td>reinstall</td><td>retargeting</td><td>re-attribution</td><td>re-attribution</td></tr><tr><td>新規獲得 </td><td>再インストール</td><td>reinstall</td><td><p>非オーガニック：UA</p><p>オーガニック：organic</p></td><td>reinstall</td><td><ul><li>reinstall</li><li>organic-reinstall</li></ul></td></tr><tr><td>リターゲティング</td><td>リアトリビューションアプリ内イベント</td><td>reinstall</td><td>retargeting</td><td>広告主が定義したイベント名</td><td>re-attribution-in-app-event</td></tr><tr><td colspan="6">\* ビュースルー計測に紐づく一部のインストールは<a href="./about-raw-data-identifier-restrictions" target="_blank">制限されたメディアソース</a>に紐づいています。 </td></tr></tbody></table>

#### 固有の項目

<table><thead><tr><th>項目</th><th>Push APIの名前</th></tr></thead><tbody><tr><td>Selected currency\*</td><td>selected_currency</td></tr><tr><td>Revenue in selected currency</td><td>revenue_in_selected_<br/>currency</td></tr><tr><td>Cost in selected currency</td><td>cost_in_selected_<br/>currency</td></tr><tr><td>Device download time selected timezone</td><td>device_download_time_selected_timezone</td></tr><tr><td>Attributed touch time selected timezone</td><td>attributed_touch_time_selected_timezone</td></tr><tr><td>Install time selected timezone</td><td>install_time_selected_<br/>timezone</td></tr><tr><td>Event time selected timezone</td><td>event_time_selected_<br/>timezone</td></tr><tr><td>Selected timezone(\*)</td><td>selected_timezone</td></tr><tr><td colspan="2">\* これは、APIメッセージが送信される時点で有効なアプリレベルの設定です。</td></tr></tbody></table>

</Accordion>

<div id="skan-attribution-messages" />

<Accordion title="SKANアトリビューションメッセージ">

このセクションでは、SKANで利用できるメッセージ（レポートタイプ）と、メッセージの識別方法について説明します。このセクションを読み、[SKAN計測のエンドポイントを設定](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)してください。

関連記事：<Anchor target="_blank" href="/marketers/ja/docs/skan-raw-data-reports">SKANローデータの項目</Anchor> / Push APIメッセージには、同様の構造と項目が存在します。

メッセージの特性

| 特性 | 詳細 |
| --- | --- |
| メッセージタイプの分離 | <ul><li>全てのメッセージは、設定した1つのエンドポイントに送信されます。</li><li>メッセージタイプを判別するためには、event\_type 項目を使用してください。<br />注：event\_type フィールドを使用すると、event\_name フィールドと skad\_redownload フィールドも判別できます。</li><li>event\_type フィールドの値は、[次の表](/docs/push-api-streaming-raw-data#skanアトリビューションのメッセージタイプ)のとおりです。</li></ul>例：<br /><br />メッセージには次の項目が含まれています：<ul><li>event\_type: skad-re-download</li></ul>このことから、次のことがわかります：<ul><li>これは再ダウンロードイベントです。</li><li>event\_name: install</li><li>skad\_redownload: true</li></ul> |
| データ更新頻度 | <ul><li>インストール、再ダウンロード、アプリ内イベント：<ul><li>毎日処理されます。</li><li>AppsFlyerが iOS ポストバックを受信した翌日にエンドポイントに送信されます。</li><li>05:00–08:00 UTC（正確な時間は変動あり）にイベントメッセージを受け取ると予想されます。</li><li>例：月曜に受信したポストバックは火曜日の08:00 UTC（日本時間17時）以降に送信されます。</li></ul></li><li>iOSからのポストバックとポストバックのコピー：メッセージはAppsFlyerに到着した後すぐに送信されます。</li></ul> |
| メッセージの例 | スプレッドシートには、メッセージの例が含まれています。提供されている例は JSON 形式です。 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vS0CO6W7jgx6zxMeSGIo-hbqLbFh3AO0OT6qp4cWmgdbWVMjLJ-2dermVz49jmAXexewiOGzR1YjGzu/pub?output=xlsx">SKANメッセージの例</Anchor> |

#### SKANアトリビューションのメッセージタイプ

| メッセージタイプ | event\_name 項目 | skad\_redownload 項目 | event\_type 項目 |
| --- | --- | --- | --- |
| インストール | install | <ul><li>含まれる値：false, blank, null</li><li>この項目がメッセージにない場合、値は FALSEであると考えてください。</li></ul> | skad-installs |
| 再インストール | install | True | skad-re-download |
| In-app events | 広告主が設定したイベント名 | 広告主が設定したイベント名 | skad-in-app-event |
| iOSからのポストバック | このメッセージでは利用できません | 場合によって利用できます | skad\_postback |
| <Anchor target="_blank" href="/marketers/ja/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">ポストバックコピー</Anchor> | このメッセージでは利用できません | 場合によって利用できます | skad-postback-copy |

</Accordion>

## Push APIエンドポイントの設定

> ❗️ **注意**
>
> 次の理由から、Push APIを使用して第三者にAppsFlyerの計測データを送信しないでください：
>
> * ユーザーが第三者へのデータ送信をオプトアウトした場合、CCPAなどのプライバシー規制に違反する可能性があります。
> * 一部のメディアソースは、それらによって提供されるユーザーレベルのデータの使用、第三者との共有、またはその両方を制限します。メディアソースの利用規約を遵守していることを確認してください。
>   例：[X Ads](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html) / [Snapchat](https://www.snap.com/en-US/privacy/privacy-policy/) / [Pinterest](https://policy.pinterest.com/en/privacy-policy)
>
> 注記：  この注記はSKANデータには適用されません。Push APIを使用して、SKANデータをサードパーティエンドポイントに送信してください。

Push APIを設定するには、次のアクションリストを完了してください。

#### Push API設定チェックリスト

<table><thead><tr><th>手順No. </th><th>AppsFlyer計測</th><th>SKAdNetwork 計測： </th></tr></thead><tbody><tr><td>1</td><td colspan="2"><p>既にアクティブなPush APIエンドポイントがある場合は、この手順をスキップしてください。 </p><p><a href="./push-api-streaming-raw-data#serverside-requirements-your-server">サーバー側の要件</a>を完了してください。</p></td></tr><tr><td>2</td><td>AppsFlyer計測については、<a href="./push-api-streaming-raw-data#push-api-planning-checklist-for-appsflyer-attribution">Push API計画チェックリスト</a>を使用してエンドポイントの設定を計画してください。 </td><td>不適用</td></tr><tr><td>3</td><td><a href="./push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">AppsFlyer計測エンドポイントの設定</a></td><td><a href="./push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint">SKAdNetwork計測エンドポイントの設定</a></td></tr></tbody></table>

<div id="serverside-requirements-your-server" />

<Accordion title="サーバー要件（お客様のサーバー）">

サーバーが次の要件に準拠していることを確認してください。

#### サーバー要件

| エンドポイント URL | <ul><li>有効なドメイン名</li><li>アプリごとの一意のエンドポイントの最大数：<ul><li>AppsFlyer：6つのエンドポイント</li><li>SKAdNetwork：3つのエンドポイント</li></ul></li></ul> |
| --- | --- |
| エンドポイントのリターンコード | メッセージ受信の際に、御社のエンドポイントは HTTP 200 ステータスコードを返す必要があります。 |
| AppsFlyerサーバーをホワイトリスト登録する | エンドポイントとの通信を確実にするために、自社のファイアウォールとセキュリティシステムにて、AppsFlyerサーバーの<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-server-ip-address-ranges-allowlisting">IPアドレス</Anchor>を許可リストに追加してください。 |
| TLSバージョン | <ul><li>TLS 1.1</li><li>TLS 1.2+ / 参照：<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-https-ssl-encryption-policy-support#送信メッセージappsflyerがクライアントとなる場合">サポートされている暗号</Anchor></li></ul> |
| ポート | ポート：80, 443 |

**注意！** 3秒間の待機時間をもつタイムアウトメカニズムが使用されます。この間にAppsFlyerがOKメッセージを受け取らなかった場合、AppsFlyerはこれをメッセージ送信の失敗と見なします。

</Accordion>

<div id="push-api-planning-checklist-for-appsflyer-attribution" />

<Accordion title="AppsFlyer計測用のPush API計画チェックリスト">

* このチェックリストを使用して、AppsFlyer計測のエンドポイント設定を進めてください。図の数字は、チェックリストの行番号を表しています。
* このセクションはSKAdNetwork計測には関係ありません。[SKAdNetwork計測の設定](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)をご覧ください。

**エンドポイント**

[![PushAPI_us-en.png](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)

#### エンドポイント計画テーブル

| いいえ。 | 設定 | 詳細 | この列を使って計画した設定を記録してください。 |
| --- | --- | --- | --- |
| 1 | メソッド | POST または GET |  |
| 2 | エンドポイント URL | - |  |
| 3 | イベントメッセージタイプ | <ul><li>イベントメッセージタイプを少なくとも1つ選択します。</li><li>アプリ内イベントメッセージを選択するには、アプリ内イベントを記録する必要があります。これが完了するまではアプリ内イベントメッセージは選択できません。</li></ul>[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png) |  |
| 4 | <ul><li>項目</li><li>フィールドのリストはすべてのメッセージタイプにおいて共通です。</li></ul> | **<span id="01H8E8DET2PBGQAKHJY40R1P9Z"></span>要注意**<br />all を選択しても、今後追加されるメッセージフィールドは自動的には含まれません。新しいフィールドを追加するには、選択を手動で更新する必要があります。<br /><br /><br /><br />必要なフィールドを選択します。<ul><li>最も一般的なフィールドは、デフォルトで選択されています。</li><li>空白または null の項目は送信しません</li></ul> |  |
| 5 | アプリ内イベントの種類 | アプリ内イベントでフィルタリングして、エンドポイントに送信されるトラフィックを絞ることができます。<ul><li>1つまたは複数のアプリ内イベントを選択します。注意！イベントが一覧に表示されない場合は、そのイベントを検索します。</li><li>アプリ内イベントは、少なくとも1回記録された後にのみ選択できるようになります。 必要に応じて、<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> を使用してイベントを発生させます。</li><li>[![mceclip1.png](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)</li></ul> |  |

</Accordion>

<div id="set-up-appsflyer-attribution-endpoint" />

<Accordion title="AppsFlyer計測エンドポイントの設定">

APIへのアクセス権限を持つすべてのチームメンバーは、Push APIの設定を変更できます。他のアカウントユーザーは設定の閲覧のみ可能です。

#### AppsFlyer計測のエンドポイントを追加する方法：

1. AppsFlyerのサイドバーから、**エクスポート > APIアクセスを開きます。**Push APIセクションまで下にスクロールします。
2. **エンドポイントを追加**をクリックしてください。
3. HTTPメソッドを選択します： **POST** または **GET**
4. **Endpoint URL**を入力してください。 *このURLは安全ではありません*というメッセージが表示された場合は、AppsFlyerサポートにお問い合わせください。
5. 1つまたは複数のイベントタイプを選択してください。　**注：** アプリ内イベントメッセージが無効になっている場合は、アプリ内イベントは記録されていないことを意味します。
6. Push APIメッセージを設定するフィールドを選択します。注記：
   * 必須項目は常に送信されます：アプリID、イベント名、イベント時間、IDFA（iOS）または広告ID（Android）
   * 次の図に示すコントロールを使用して、オプションのフィールドを選択します。  [![PushAPIFieldSelect1.jpg](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)
     * 最も一般的なフィールドは、デフォルトで選択されています。選択をキャンセルすることができます。
     * 必要に応じて、オプションのフィールドを選択ください。
     * オプションの項目をすべて削除するには、**すべてクリア**を使用してください。
     * nullまたは空の項目と関連するキーは送信しません。インポート/解析プロセスを検討する際には、このことを考慮してください。
7. 1つまたは複数のイベント（最大52イベント）または**すべて**のアプリ内イベントを選択してください。
   * リストには、すでに記録されているイベントタイプが表示されます。イベントが見つからない場合は、テストデバイスを使用して、このタイプのイベントを送信します。
8. **保存**をクリックしてください。  
   Push APIがアクティブになりました。コンバージョンデータはエンドポイントに送信されます。
9. 次の手順を使用して、エンドポイントをテストします。

#### エンドポイントのテスト

1. **コードを送信**をクリックしてください。  
   **テスト送信**ボタンの下にテスト結果のメッセージが表示されます。   
   テストメッセージがエンドポイントに送信されます。テストに失敗した場合、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-server-ip-address-ranges-allowlisting">AppsFlyer IPアドレスを許可リストに追加</Anchor>しているか確認してください。   
   <strong>注意！</strong>タイムアウトメカニズム（2秒間の待機時間）が使用されます。この間にAppsFlyerがOKメッセージを受け取らなかった場合、AppsFlyerはこれをメッセージ送信の失敗と見なします。
2. 御社エンドポイントがテストメッセージを受信したことを確認してください。  
   [送信されたメッセージのコピーを確認してください。](https://docs.google.com/spreadsheets/d/e/2PACX-1vScQf189h3Ry0BU-ejbZYkMZCJRdXXYeOwuNxPEHwY77vCVYWW9P9xCTUSJKmTvVbp_yzLidXD0WGLm/pub?gid=0&single=true&output=csv)

</Accordion>

<div id="set-up-skadnetwork-attribution-endpoint" />

<Accordion title="SKAdNetwork計測エンドポイントの設定">

APIへのアクセス権限を持つすべてのチームメンバーは、Push APIの設定を変更できます。他のアカウントユーザーは設定の閲覧のみ可能です。

**SKAdNetwork Push APIエンドポイントの追加：**

1. AppsFlyerのサイドバーから、**エクスポート > APIアクセスを開きます。**Push APIセクションまで下にスクロールします。
2. 計測エンティティで**SKAdNetwork**を選択してください。
3. **エンドポイントを追加**をクリックしてください。  
   　**注：** アプリごとに1〜3個のSKAdNetworkエンドポイントを定義できます。
4. HTTPメソッドを選択します： **POST** または **GET**
5. **Endpoint** **URL**を入力してください。 *このURLは安全ではありません*というメッセージが表示された場合は、AppsFlyerサポートにお問い合わせください。
6. nullまたは空の項目と関連するキーは送信しません。インポート/解析プロセスを検討する際には、このことを考慮してください。
7. **保存**をクリックしてください。  
   Push APIがアクティブになりました。このエンドポイントにデータが送信されます。

</Accordion>

<div id="configure-authentication-token" />

<Accordion title="認証トークンの設定">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_tokens-app-app-id">Push API認証トークン</Anchor>を使用すると、クライアントは、要求されたトークンを使用してカスタマイズ可能な認証ヘッダーを追加することで、Push APIメッセージをシームレスに統合し、保護できます。  
各アプリIDに紐づくトークン名と値を定義することで、Push APIメッセージと共に送信されるauthorizationヘッダーをカスタマイズできます。これにより、メッセージは安全であるだけでなく、特定の要件に合わせて調整されます。

</Accordion>

## その他の手順—エンドポイントの管理

APIへのアクセス権限を持つすべてのチームメンバーは、Push APIの設定を変更できます。他のアカウントユーザーは設定の閲覧のみ可能です。

<div id="change-an-endpoint" />

<Accordion title="エンドポイントの変更">

**エンドポイント設定の変更：**

1. AppsFlyerのサイドバーから、**エクスポート > APIアクセスを開きます。**Push APIセクションまで下にスクロールします。
2. 変更したいエンドポイントを特定します。
3. 修正を行います。
4. **保存** をクリックしてください。

</Accordion>

<div id="delete-an-endpoint" />

<Accordion title="エンドポイントの削除">

**エンドポイントの削除**：

1. AppsFlyerのサイドバーから、**エクスポート > APIアクセスを開きます。「Push API」セクションまでスクロールします。**
2. **エンドポイントを削除**をクリックしてください。
3. **保存**をクリックしてください。  
   エンドポイントが削除されます。

</Accordion>

## トラブルシューティング、特性、制限事項

<div id="test-message-fails" />

<Accordion title="テストメッセージに失敗する場合：">

テストメッセージが届かず、IPアドレスでサーバーへのアクセスを制限している場合は、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-server-ip-address-ranges-allowlisting">AppsFlyer のすべてのIPアドレスを許可</Anchor>していることを確認してください。

</Accordion>

<div id="duplicate-retargeting-inapp-events" />

<Accordion title="リターゲティングアプリ内イベントの重複">

ユーザー獲得リエンゲージメント期間中に、リターゲティングキャンペーンの一環として購入イベントが発生すると、アプリ内イベントのリターゲティングが重複します。これは、ユーザー獲得メディアソースとリターゲティングメディアソースの両方に収益を計上するために行われます。

両方を有効にしている場合にのみ、重複するイベントが発生します。

* 新規獲得 - アプリ内イベント
* リターゲティングアプリ内イベント

<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">アプリ内イベントを特定し重複を排除してください</Anchor>。

</Accordion>

<div id="inapp-event-message-selection-is-disabled" />

<Accordion title="アプリ内イベントメッセージの選択が無効になっている">

[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)

* アプリ内イベントメッセージは、アプリ内イベントが記録された後にのみ選択できます。
* テストデバイスを使用してアプリ内イベントを生成するか、<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor> を使用して手動で生成します。

</Accordion>

<div id="missing-push-messages-and-cloudfront" />

<Accordion title="プッシュメッセージが見つからない（CloudFront使用の場合）">

エンドポイントとして Amazon CloudFront を使用している場合は、CloudFront が拒否コード 421 でメッセージを拒否しているかどうかを確認してください。この場合には、<Anchor target="_blank" href="https://docs.aws.amazon.com/en_pv/AmazonCloudFront/latest/DeveloperGuide/cnames-https-dedicated-ip-or-sni.html">CloudFront が HTTPS リクエストを処理する方法の選択</Anchor>を参照してください。

</Accordion>

<div id="endpoint-error-messages" />

<Accordion title="エンドポイントのエラーメッセージ">

**症状**：エンドポイントURLを設定すると、*このURLは安全ではありません* というメッセージが表示されます。

**必要なアクション**：AppsFlyerサポートに連絡し、アプリID、エンドポイントURL、およびエラーメッセージのスクリーンショットを送信してください。

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="特性と制限">

| **特性** | 備考 |
| --- | --- |
| <span id="ad-networks"></span>アドネットワーク | 利用不可 |
| <span id="agencies"></span>代理店 | 利用不可 |
| <span id="appspecific-time-zone"></span>アプリ固有のタイムゾーン | サポート対象 |
| <span id="appspecific-currency"></span>アプリ固有の通貨 | サポート対象 |
| <span id="size-limitations"></span>サイズ制限 | 不適用 |
| <span id="organic"></span>オーガニック | はい |
| <span id="nonorganic"></span>非オーガニック | はい |
| <span id="data-freshness"></span>データ更新頻度 | 継続的 |
| <span id="historical-data"></span>過去データ | いいえ：データが見つからない場合は、Pull APIやData Lockerを使用してデータを取得してください。SKANの場合は、Data Locker経由で一部の過去データを取得できます（Data Lockerのデータ可用期間による制限）。 |
| <span id="account-owneruser-access"></span>アカウント所有者 / ユーザーアクセス | Push API設定を変更できるのは、AppsFlyer**アカウント所有者**のみです。<ul><li>各AppsFlyerアカウントのアカウント所有者は **1人のみ**です。これは、最初のAppsFlyerユーザー（アカウントが開設された時点で作成されたユーザー）です。</li></ul>アカウントメンバーはPush APIの設定を閲覧できますが、変更はできません。 |
| <span id="authentication-token-in-test-messages"></span>テストメッセージ内の認証トークン | [テストメッセージ](#エンドポイントのテスト)のヘッダーには、認証トークンが含まれていません。 |

</Accordion>

<div id="can-i-include-custom-headers-with-the-push-api-request" />

<Accordion title="Push APIリクエストにカスタムヘッダーを含めることはできますか？">

いいえ。Push APIでは、認証トークンにのみ `Authorization` ヘッダーを使用できます。追加のカスタム ヘッダー（`consumer-key` など）は**サポートされていません**。

追加のパラメーターを渡す必要がある場合は、URLに含めてください。例：

```
https://your.server.com?consumer_key=abc456
```

</Accordion>

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">ローデータ配信ツールの比較</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_app-app-id">APIを使用したPush APIの設定</Anchor>

<div data-zendesk-anchors="01H89PJFBPXVKJGGH18CJBJ41W=push-api 01H89PJFBP45FQDHT4YGS58NP8=appsflyer-attribution-messages available-message-types=%E4%BD%BF%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%82%BF%E3%82%A4%E3%83%97 01H89PJFBP9DEX520BDGC5PANQ=%E4%BD%BF%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%82%BF%E3%82%A4%E3%83%97 unique-fields=%E5%9B%BA%E6%9C%89%E3%81%AE%E9%A0%85%E7%9B%AE 01H89PJFBPBK09Q7CRPMM4G7PJ=%E5%9B%BA%E6%9C%89%E3%81%AE%E9%A0%85%E7%9B%AE 01H89PJFBQM4NKFSFF8XGMX9XT=skan-attribution-messages message-types-for-skan-attribution=skan%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%82%BF%E3%82%A4%E3%83%97 01H89PJFBQBFCK5QVWW2X09H28=skan%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%83%A1%E3%83%83%E3%82%BB%E3%83%BC%E3%82%B8%E3%82%BF%E3%82%A4%E3%83%97 set-up-push-api-endpoints=push-api%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A 01H89PJFBQZ2FW3ST5V4FW91GS=push-api%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A 01H89PJFBQ6WP7ERP0DJ69QZ1G=%E6%B3%A8%E6%84%8F push-api-setup-checklist=push-api%E8%A8%AD%E5%AE%9A%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 01H89PJFBQ625A7G3QT5HQJXMW=push-api%E8%A8%AD%E5%AE%9A%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 01H89PJFBQGW8ZV76Z0HTNX2AB=serverside-requirements-your-server serverside-requirements=%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E8%A6%81%E4%BB%B6 01H89PJFBQ2BC5GHX403RD2RAT=%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E8%A6%81%E4%BB%B6 01H89PJFBQ4FXB7ABMFVHX326H=push-api-planning-checklist-for-appsflyer-attribution endpoint-planning-table=%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E8%A8%88%E7%94%BB%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB 01H89PJFBQJXWWPQDKZ387VYX3=%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E8%A8%88%E7%94%BB%E3%83%86%E3%83%BC%E3%83%96%E3%83%AB 01H89PJFBQZE6KJDHXRB8GK7TF=set-up-appsflyer-attribution-endpoint add-an-appsflyer-attribution-endpoint=appsflyer%E8%A8%88%E6%B8%AC%E3%81%AE%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 h_01JFSS65G8GTZNMY257QCV922M=appsflyer%E8%A8%88%E6%B8%AC%E3%81%AE%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%82%92%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 test-the-endopoint=%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01JFSS6YVP1WFWXSZ7HP7GTDA2=%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 01H89PJFBQQS31C6AF245SSJ61=set-up-skadnetwork-attribution-endpoint h_01HSDW5XQ28T3SQJTN5PBSBCFT=configure-authentication-token additional-procedures%E2%80%94managing-endpoints=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%89%8B%E9%A0%86%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%81%AE%E7%AE%A1%E7%90%86 01H89PJFBQ7WV3NM7JR5Z9QEFB=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%89%8B%E9%A0%86%E3%82%A8%E3%83%B3%E3%83%89%E3%83%9D%E3%82%A4%E3%83%B3%E3%83%88%E3%81%AE%E7%AE%A1%E7%90%86 01H89PJFBQ9RZXNHGNNYV5MP7P=change-an-endpoint 01H89PJFBQGE1WESD7ZEMBEFNE=delete-an-endpoint troubleshooting-traits-and-limitations=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E7%89%B9%E6%80%A7%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 01H89PJFBQJDGT1FVHKG9DETHJ=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E7%89%B9%E6%80%A7%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 01H89PJFBQAAZYF7YWKC7TP884=test-message-fails 01H89PJFBQHQJSHE09GC599AQ6=duplicate-retargeting-inapp-events 01H89PJFBRDET8T8CTAP1GW0J9=inapp-event-message-selection-is-disabled 01H89PJFBRH58FX1FTH37DP3HC=missing-push-messages-and-cloudfront 01H89PJFBR3CJSR2AEFP3HT5JE=endpoint-error-messages 01H89PJFBRZXXEMPBGBPB35MQ9=specifications-and-limitations h_01JQY6KXYBGXTSVDC18H5CZCWR=can-i-include-custom-headers-with-the-push-api-request h_01HE7SH7XFMPJ13DKCZ04RCJDD=%E5%8F%82%E7%85%A7" />

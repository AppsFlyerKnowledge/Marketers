---
title: SKANローデータレポート
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2026-10-28T09:17:52Z'
  id: 360014261518
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/360014261518
---
> **概要：** SKANローデータレポートには、元のSKANポストバックに加え、AppsFlyerがiOSから受信したポストバックを変換・デコードして生成した、行単位のデータが含まれます。データは、<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers">Data Locker</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">Push API</Anchor>経由で利用できます。契約プランにローデータが含まれている場合、Data Lockerの契約は不要です。

## SKANローデータレポート

原則：

* **データの提供方法：**
  * **Data Locker**
    * **注意**！ローデータを契約しているアカウントで利用できます。 Data Lockerの契約は不要です。現在Data Lockerを使用していない場合は、管理者ユーザーがData Lockerを設定し、SKANレポートを有効にする必要があります。**［レポート］**＞<strong>［Data Locker］</strong>に移動します。 SKANレポートを選択します。
    * **データの更新頻度**：日次。 データは、AppsFlyerがポストバックを受信した日付のh=23フォルダーに格納されます。
  * **Push API**
    * データの更新頻度：<Anchor target="_blank" href="/marketers/ja/docs/push-api-streaming-raw-data">SKANデータ向けPush API</Anchor>を参照してください。
* **インストール日**：AppsFlyerがポストバック到着時刻から、以下のように算出します。
  * SKAN V4のポストバックでは、次の式を使用します。インストール日＝ポストバック到着時刻−［累積ウィンドウ期間］−［平均ポストバック遅延時間］。
    * ポストバック1：インストール日＝ポストバック到着時刻−48時間−36時間
    * ポストバック2：インストール日＝ポストバック到着時刻−168時間−84時間
    * ポストバック3：インストール日＝ポストバック到着時刻−840時間−84時間
  * SKAN V3のポストバックでは、次の式を使用します。インストール日＝ポストバック到着時刻−36時間−［最終アクティブ時間帯の平均値］。 
    * ［最終アクティブ時間帯の平均値］のデフォルトは12時間です。
    * CVが0の場合、最終アクティブ時間帯の平均値は0に設定されます。
  * Googleは独自にインストール時刻を推定し、AppsFlyerはその時刻を使用します。**注意**：Googleによるインストールの報告には、最大45日かかる場合があります。<Anchor target="_blank" href="/marketers/ja/docs/get-skan-postback-data-from-google-ads#google-adsとのskan連携">詳細はこちら</Anchor>

利用できるレポートの種類：

* **デバイスポストバック**：iOSデバイスから、インストールまたは再ダウンロードごとに1件受信するポストバック。
* **SKANローデータ**：
  * AppsFlyerは、デバイスポストバックをデコード・変換し、ローデータのレコードを生成します。
  * 各ポストバックから、インストールまたは再ダウンロードのレコードと、アプリ内イベントのレコードが生成されます。
  * アプリ内イベントのレコード数は、CVによって以下のように異なります。
    * CVが0、空欄、nullの場合：アプリ内イベントのレコードは生成されません。
    * CVの範囲：
      * 1〜63：SKAN 3と、SKAN 4のウィンドウ1の細かいCVでは、計測設定に応じたアプリ内イベントのレコード数になります。
      * low、medium、high：SKAN 4の粗いCVでは、計測設定に応じたアプリ内イベントのレコード数になります。

**一部のフィールドが空欄になる理由**以下のいずれかの理由で、フィールドが空欄になります。

* campaign\_name、ad\_network\_campaign\_id、ipなど、任意の追加情報をアドネットワークが提供していない場合。
* Appleのしきい値ポリシーにより、データが開示されなかった場合。 source\_app\_id、skad\_campaign\_id、skad\_conversion\_valueなどが該当します。

## SKANローデータレポートの形式と内容

<div id="raw-data-report-types" />

<Accordion title="ローデータレポートの種類">

<Table>
  <thead>
    <tr>
      <th>
        レポートの種類
      </th>
      <th>
        レポート名
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="postback"></span>
        ポストバック
      </td>
      <td>
        ポストバック
      </td>
      <td>
        iOSからアドネットワークに送信されたポストバック。アドネットワークが情報を追加した後、AppsFlyerに転送します。[ポストバックのサンプルをダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv)（CSV）。

        注意：did\_win=falseのポストバックは含まれません。

        **Data Lockerのトピック名**：skad\_postbacks
      </td>
    </tr>
    <tr>
      <td><span id="postback::315d5a62"></span>
        ポストバック
      </td>
      <td>
        ポストバックのコピー（Appleから直接受信）
      </td>
      <td>
        iOSからAppsFlyerに直接送信されたポストバック。

        iOS15以降で利用できます。広告主がアプリを設定し、<Anchor target="_blank" href="/marketers/ja/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">帰属先へのポストバックをAppsFlyerにも送信</Anchor>する必要があります。[ポストバックコピーのサンプルをダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv)（CSV）。

        注意：このトピックには、帰属先へのポストバックのみが含まれます。

        **Data Lockerのトピック名**：skad\_postbacks\_copy
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event"></span>
        デコード済みイベント
      </td>
      <td>
        インストール
      </td>
      <td>
        **初回のアプリインストール**

        SKANが*redownload=false*を報告した場合。つまり、そのApple IDのユーザーが、このアプリを初めてダウンロードしたことを意味します。  
        [インストールのサンプルをダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv)（CSV）。

        **Data Lockerのトピック名**：skad\_installs
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5c7e459f"></span>
        デコード済みイベント
      </td>
      <td>
        再ダウンロード
      </td>
      <td>
        **初回ではないアプリインストール**

        SKANが*redownload=true*を報告した場合。つまり、そのApple IDのユーザーが、このアプリを以前にもダウンロードしていることを意味します。レポートの構成は、インストールのレポートと同じです。

        **Data Lockerのトピック名**：skad\_redownloads
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::b8f2b4a4"></span>
        デコード済みイベント
      </td>
      <td>
        アプリ内イベント
      </td>
      <td>
        **アプリ内イベント**

        2021年7月21日以降、アプリ内イベントのローデータの提供方法が、以下の表のとおり変更されています。

        アプリ内イベントのレコード数は、計測設定によって異なります。

        [アプリ内イベントのサンプルをダウンロード](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv)（CSV）。

        **Data Lockerのトピック名**：skad\_inapps

        2021年7月21日以降に受信したiOSポストバックに適用：

        | 計測タイプ | 説明 |
        | --- | --- |
        | 収益 | * 特定のユーザーの収益。収益が0より大きい場合、skad\_revenueとevent\_nameのフィールドを含むレコードが生成されます。<br />* min\_revenueとmax\_revenueには、カスタムコンバージョンで定義した範囲の値が入ります。 |
        | アプリ内コンバージョンとファネルイベント | * 実行されたコンバージョンイベントの種類ごとに1件のレコードが生成されます。 event\_nameフィールドには、対応するイベント名が設定されます。イベントが実行されていない場合、レコードは生成されません。<br />* コンバージョンイベントでは、min\_event\_counter=0、max\_event\_counter=1となります。 |
        | アプリ内エンゲージメント | ユーザーがアプリ内イベントを実行した回数は、次の式で算出します。`[round up (min_event_counter + max_event_counter) / 2]` |

        2021年7月20日までに受信したiOSポストバックに適用：

        | 計測タイプ | レコード数 | 説明 |
        | --- | --- | --- |
        | 収益 | 0-1 | 収益が0より大きい場合、skad\_revenueとevent\_nameのフィールドを含むレコードが生成されます。 |
        | コンバージョン | 0-6 | 実行されたコンバージョンイベントの種類ごとに1件のレコードが生成されます。 event\_nameフィールドには、対応するイベント名が設定されます。イベントが実行されていない場合、レコードは生成されません。 |
        | エンゲージメント | 0-63 | レコード数は、ユーザーがエンゲージメントイベントを実行した回数を表します。ユーザーがイベントを実行しなかった場合、エンゲージメントのレコードはありません。 |
        | カスタム | 0〜上限なし | 独自のコンバージョンスキーマに従います。 |
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5dac9cbb"></span>
        デコード済みイベント
      </td>
      <td>
        SRNの広告ディメンション
      </td>
      <td>
        * Meta広告のイベントを、キャンペーン、広告セット、広告の粒度で提供するレポートです。各行は、インストールまたはアプリ内イベントのいずれかです。
        * Meta広告のSKANポストバックには、広告セットと広告の粒度の情報は含まれません。このデータは、このレポートでのみ確認できます。SKANダッシュボード、Performance API、その他のSKANのData Lockerレポートには表示されません。
        * レポートのスキーマは固定されていません。 Data Lockerのフィールド選択設定は適用されません。
        * 推奨：このレポートのデータを、ほかのSKANレポートと統合・比較しないでください。このレポートではSRNがデコードしたデータを使用しますが、ほかのレポートではAppsFlyerがデコードしたデータを使用するため、差異が生じる場合があります。差異の原因には、タイムゾーンやSRNのスキーマの違い、SRN連携でのアプリ内イベントとCVのマッピングの誤りなどがあります。
        * <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx">SRNの広告ディメンションのサンプルをダウンロード</Anchor>（CSV）。

        **Data Lockerのトピック名**：skad\_srn\_advertising\_dimensions
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-field-format-types" />

<Accordion title="ローデータのフィールド形式">

#### フィールドの形式

| 形式名 | 説明 |
| --- | --- |
| 文字列［n］ | 文字列の最大長。通常、データ受信時にはフィールド長を制限しません。ただし、その後の処理でデータが切り詰められる場合があります。 |
| 日時文字列 | `yyyy-mm-dd hh:mm:ss`形式の文字列。例：`2019-09-17 00:09:25` |
| 列挙型［n］ | 列挙型のフィールドには、指定された値のみを設定できます。たとえば、コストの通貨は3文字で、指定された通貨コードのみを使用できます。 |
| タイムスタンプ | 10桁のUNIXタイムスタンプ。例：<br /><br />2020年8月4日07:25（UTC）は、`"timestamp": "1596525944"`になります。 |
| ブール値 | フィールドの値は、`TRUE`または`FALSE`です。 |
| 整数 | 整数 |
| 浮動小数点数 | 小数点以下の値を含められる実数。 |

</Accordion>

<div id="fields-available-in-postback-and-postback-copy-reports" />

<Accordion title="ポストバック／ポストバックコピーレポートで利用できるフィールド">

<table><thead><tr><th>フィールド名</th><th>データソース、または対応開始のiOS SKANバージョン</th><th>説明</th><th>形式</th><th>ポストバックコピーに含まれる </th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>アドネットワーク</td><td>アドネットワークがAppsFlyerに報告したキャンペーンID</td><td>文字列</td><td>いいえ</td></tr><tr><td><p>ad_network_campaign</p><p>_name</p></td><td>アドネットワーク</td><td><p>アドネットワークがAppsFlyerに報告したキャンペーン名。</p></td><td>文字列</td><td>いいえ</td></tr><tr><td>ad_network_timestamp</td><td>アドネットワーク</td><td><p>アドネットワークがポストバックを受信した時刻。</p><p>Google広告の場合、Googleが報告した最終クリック時刻から算出します。</p></td><td>タイムスタンプ</td><td>いいえ</td></tr><tr><td>app_id</td><td>AppsFlyer</td><td>IDプレフィックス付きのアプリID（広告対象アプリ）。</td><td>文字列</td><td>はい</td></tr><tr><td>city</td><td>AppsFlyer</td><td>2021年8月30日以降、常にnull </td><td>文字列</td><td>いいえ</td></tr><tr><td>country_code</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>dma</td><td> </td><td>2021年8月30日以降、常にnull </td><td>文字列</td><td>いいえ</td></tr><tr><td>postal_code</td><td> </td><td>2021年8月30日以降、常にnull  </td><td>文字列</td><td>いいえ</td></tr><tr><td>region</td><td>AppsFlyer</td><td>報告されたcountry_codeに基づきます。</td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_ad_network_id</td><td>1.0 </td><td>一部のSRNはIDを共有しないため、フィールドは空欄になります。たとえば、X広告が該当します。 </td><td>文字列</td><td>はい </td></tr><tr><td>skad_attribution_signature</td><td>1.0</td><td> </td><td>文字列</td><td>はい</td></tr><tr><td>skad_campaign_id</td><td>1.0</td><td>広告配信に使用されたキャンペーンID。範囲：0〜100</td><td>文字列</td><td>はい</td></tr><tr><td>skad_conversion_value</td><td>2.0 </td><td><p>iOSが報告したCV。範囲：0〜63。</p><p>nullの場合、iOSがこのフィールドに値を設定していません。\*\* </p></td><td>整数</td><td>はい</td></tr><tr><td>skad_redownload</td><td>2.0</td><td>trueの場合、アプリが再ダウンロードされています。</td><td>ブール値</td><td>はい</td></tr><tr><td>skad_source_app_id</td><td>2.0</td><td><p>サイトID。広告を掲載するアプリ。このフィールドは、source_app_idと同じです。</p><p>値が設定されるかどうかは、プライバシーしきい値に基づきます。\*\*</p></td><td>文字列</td><td>はい</td></tr><tr><td>skad_transaction_id</td><td>1.0</td><td> </td><td>文字列</td><td>はい</td></tr><tr><td>skad_version</td><td>2.0</td><td> </td><td>文字列</td><td>はい</td></tr><tr><td>timestamp</td><td>アドネットワーク</td><td>AppsFlyerがSKANポストバックを受信した時刻。 </td><td>日時文字列</td><td>はい</td></tr><tr><td>ad_network_name</td><td>アドネットワーク</td><td>アドネットワークがAppsFlyerに報告したアドネットワーク名。 <ul><li>空欄の場合、アドネットワークが値を設定しなかったか、設定できなかったことを意味します。</li><li>skad_ad_network_idを使用して、アドネットワーク名を特定できます。こちらの<a href="./skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks" target="_blank">表</a>を使用してください。 </li></ul></td><td>文字列</td><td>いいえ</td></tr><tr><td>ip</td><td> </td><td><p>ポストバックを送信したiOSデバイスのHTTPメッセージに含まれるIPアドレス。</p><p>アドネットワークがAppsFlyerにアドレスを提供した場合に設定されます。</p><p>注意！このアドレスの取得に、SDKは関与しません。</p></td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_app_id</td><td>1.0</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>source_app_id</td><td>AppsFlyer</td><td>サイトID。広告を掲載するアプリ。このフィールドは、skad_source_app_idと同じです。</td><td>文字列</td><td>いいえ</td></tr><tr><td>ad_network_adset_id</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>ad_network_adset_name</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>ad_network_ad_name</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>ad_network_ad_id</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>did_win</td><td>3.0 (iOS 14.6)</td><td>インストールに<a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">貢献したキャンペーンと、帰属先となったキャンペーン</a>を区別するために使用します。 <ul><li>trueの場合、インストールはこのキャンペーンに帰属しています。</li><li>falseの場合、インストールに貢献したと見なされますが、SKANダッシュボードやレポートには含まれません。</li><li>nullの場合、<a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">iOSまたはSKAdNetworkが古いバージョン</a>であるため、iOSがこのフィールドに値を設定していません。</li></ul></td><td>ブール値</td><td>はい</td></tr><tr><td>fidelity_type</td><td>2.2 (iOS 14.5)</td><td><p>アトリビューションに影響する<a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">広告の表示方式</a>を区別します。以下のように、0と1で表します。 </p><ul><li>ビュースルー広告（0）</li><li>StoreKitで表示される広告（1）</li></ul><p>SKAN 2.2未満では、このフィールドの値は使用しないでください。</p></td><td>整数</td><td>はい</td></tr><tr><td>ad_network_source_app_id</td><td>アドネットワーク</td><td><span>アドネットワークが報告した広告掲載元アプリのID。アドネットワークが報告する値で、コストの照合に役立ちます。このデータの基になる情報は、広告掲載元アプリが提供します。 </span></td><td>文字列</td><td>いいえ</td></tr><tr><td>ad_network_channel</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>af_prt</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0 (iOS 16.2)</td><td><ul><li>SKANのウィンドウを表す値で、<code>0</code>、<code>1</code>、<code>2</code>のいずれかです。</li><li>SKAN 3では、値は<code>0</code>です。 </li></ul></td><td>整数</td><td>はい</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li>値は<code>low</code>、<code>medium</code>、<code>high</code>のいずれかです。</li><li>SKAN 3では、値は<code>null</code>です。</li></ul></td><td>文字列</td><td>はい</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>最大4桁の値です。</li><li>SKAN 3では、値は<code>null</code>です。 </li></ul></td><td>文字列</td><td>はい</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>アトリビューション対象となるWeb広告の流入元を表します。</li><li>SKAN 3では、値は<code>null</code>です。</li></ul></td><td>文字列</td><td>はい</td></tr><tr><td>ad_network_creative</td><td>アドネットワーク</td><td><ul><li>アドネットワークから受信した追加情報に基づく値です。</li><li>SKAN 3では、値は<code>null</code>です。</li></ul></td><td>文字列</td><td>いいえ</td></tr><tr><td colspan="4">\*\*Appleが、プライバシーしきい値の仕組みに基づいて、フィールドに値を設定するかどうかを決定します。 </td><td> </td></tr></tbody></table>

</Accordion>

<div id="fields-available-in-decoded-event-reports" />

<Accordion title="デコード済みイベントレポートで利用できるフィールド">

<table><thead><tr><th>フィールド名</th><th>ソース</th><th>説明</th><th>形式</th><th>SRNの広告ディメンションレポートに含まれる</th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>アドネットワーク</td><td>アドネットワークがAppsFlyerに報告したキャンペーンID</td><td>文字列</td><td>はい</td></tr><tr><td>ad_network_campaign<br/>_name</td><td>アドネットワーク</td><td>アドネットワークがAppsFlyerに報告したキャンペーン名</td><td>文字列</td><td>はい</td></tr><tr><td>ad_network_timestamp</td><td>アドネットワーク</td><td><p>アドネットワークがポストバックを受信した時刻</p><p>Google広告では、このフィールドに値は設定されません。 </p></td><td><p>タイムスタンプ</p><p>（SRNの広告ディメンションレポートでは日時文字列）</p></td><td>はい</td></tr><tr><td>app_id</td><td>iOS</td><td>アプリID（広告対象アプリ）</td><td>文字列</td><td>はい</td></tr><tr><td>city</td><td> </td><td>2021年8月30日以降、常にnull </td><td>文字列</td><td>いいえ</td></tr><tr><td>country_code</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>dma</td><td> </td><td>2021年8月30日以降、常にnull </td><td>文字列</td><td>いいえ</td></tr><tr><td>event_name</td><td>AppsFlyer</td><td><p>AppsFlyerで設定したアプリ内イベント名。</p><p>SRN ___reportでは、Meta広告で設定したアプリ内イベント名です。</p></td><td>文字列</td><td>はい</td></tr><tr><td>event_uuid</td><td>AppsFlyer</td><td>パートナーがポストバックの重複を識別するための、一意のランダムな識別子</td><td>文字列</td><td>いいえ</td></tr><tr><td>install_date</td><td>iOS</td><td>ポストバック到着時刻に基づいて、AppsFlyerが推定します。</td><td>日時文字列</td><td>いいえ</td></tr><tr><td>install_type</td><td>iOS</td><td>新規インストール</td><td>文字列</td><td>いいえ</td></tr><tr><td>ip</td><td>iOS</td><td><p>ポストバックを送信したiOSデバイスのHTTPメッセージに含まれるIPアドレス。</p><p>アドネットワークがAppsFlyerにアドレスを提供した場合に設定されます。</p><p>注意！このアドレスの取得に、SDKは関与しません。 </p></td><td>文字列</td><td>いいえ</td></tr><tr><td>media_source</td><td>iOS</td><td>帰属先のアドネットワーク。AppsFlyerで使用するアドネットワーク名で表示します。</td><td>文字列</td><td>はい</td></tr><tr><td>postal_code</td><td> </td><td>2021年8月30日以降、常にnull </td><td>文字列</td><td>いいえ</td></tr><tr><td>region</td><td>AppsFlyer</td><td>country_codeに基づいて決定</td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_ad_network_id</td><td>iOS</td><td>ポストバックの送信先アドネットワークのID</td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_ambiguous_event（SKAN 4以降は廃止）</td><td>AppsFlyer</td><td>trueの場合、このiOSポストバックは、広告主がダッシュボードでSKANの設定を変更してから72時間以内に受信したものです。 SKANの各種タイマーの影響により、AppsFlyerはイベントを正確にマッピングできません。<ul><li>SKAN 4以降では利用できません。</li></ul></td><td>ブール値</td><td>いいえ</td></tr><tr><td>skad_attribution_signature</td><td>iOS</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_campaign_id</td><td>iOS</td><td>広告配信に使用されたキャンペーンID。範囲：0〜100</td><td>整数</td><td>いいえ</td></tr><tr><td>skad_conversion_value</td><td>iOS</td><td><p>iOSが報告したCV。範囲：0〜63。</p><p>nullの場合、iOSがこのフィールドに値を設定していません。\*\*</p></td><td>整数</td><td>いいえ</td></tr><tr><td>skad_mode</td><td>AppsFlyer</td><td>iOSポストバックのデコードに使用したコンバージョン計測モード。選択肢：<ul><li>custom_decode</li><li>revenue</li><li>events</li><li>skan4</li><li>custom_encode</li><li>engagement</li></ul></td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_redownload</td><td>iOS</td><td>trueの場合、アプリが再ダウンロードされています。</td><td>ブール値</td><td>いいえ</td></tr><tr><td>skad_revenue</td><td>iOS</td><td>イベント収益額（USD）。</td><td>浮動小数点数</td><td>いいえ</td></tr><tr><td>skad_source_app_id</td><td>iOS</td><td><p>サイトID。広告を掲載するアプリです。</p><p>値が設定されるかどうかは、プライバシーしきい値に基づきます。\*\*</p></td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_transaction_id</td><td>iOS</td><td>-</td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_version</td><td>iOS</td><td>-</td><td>文字列</td><td>いいえ</td></tr><tr><td>timestamp</td><td>iOS</td><td><p>AppsFlyerがSKANポストバックを受信した時刻。</p><p>Google広告とMeta広告では、それぞれのAPIからAppsFlyerがデータを取得した時刻です。</p></td><td><p>タイムスタンプ</p><p>（SRNの広告ディメンションレポートでは日時文字列）</p></td><td>はい</td></tr><tr><td>event_value</td><td>S2S</td><td><p>デフォルト値：null</p><p>カスタムデコードを実装するアプリが設定した文字列を含みます。</p><p>広告主が自社システムで使用します。 AppsFlyerはこの値を使用しません。 </p></td><td>文字列（JSON）</td><td>いいえ</td></tr><tr><td>ad_network_adset_id</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>はい</td></tr><tr><td>ad_network_adset_name</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>はい</td></tr><tr><td>ad_network_ad_name</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>はい</td></tr><tr><td>ad_network_ad_id</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>はい</td></tr><tr><td>skad_did_win (1)</td><td>3.0 (iOS 14.6)</td><td>インストールに<a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">貢献したキャンペーンと、帰属先となったキャンペーン</a>を区別するために使用します。 <ul><li>trueの場合、インストールはこのキャンペーンに帰属しています。</li><li>falseの場合、インストールに貢献したと見なされますが、SKANダッシュボードやレポートには含まれません。</li><li>nullの場合、<a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">iOSまたはSKAdNetworkが古いバージョン</a>であるため、iOSがこのフィールドに値を設定していません。</li></ul></td><td>ブール値</td><td>いいえ</td></tr><tr><td>skad_fidelity_type (1)</td><td>2.2 (iOS 14.5)</td><td><p>アトリビューションに影響する<a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">広告の表示方式</a>を区別します。以下のように、0と1で表します。 </p><ul><li>ビュースルー広告（0）</li><li>StoreKitで表示される広告（1）</li></ul><p>SKAN 2.2未満では、このフィールドの値は使用しないでください。</p></td><td>整数</td><td>はい</td></tr><tr><td>ad_network_source_app_id (1)</td><td>アドネットワーク</td><td><span>アドネットワークが報告した広告掲載元アプリのID。アドネットワークが報告する値で、コストの照合に役立ちます。このデータの基になる情報は、広告掲載元アプリが提供します。</span></td><td>文字列</td><td>いいえ</td></tr><tr><td>ad_network_channel (1)</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>af_prt (1)</td><td>アドネットワーク</td><td> </td><td>文字列</td><td>いいえ</td></tr><tr><td>min_revenue </td><td>AppsFlyer</td><td>注意事項（4）を参照</td><td>実数</td><td>いいえ</td></tr><tr><td>max_revenue </td><td>AppsFlyer</td><td>注意事項（4）を参照</td><td>実数</td><td>いいえ</td></tr><tr><td>event_revenue</td><td>AppsFlyer</td><td>計算式：［該当イベントの値の合計（USD）］÷［特定の日に発生したイベント数］</td><td>浮動小数点数</td><td>はい</td></tr><tr><td>min_event_counter</td><td>AppsFlyer</td><td>ユーザーがイベントを実行した回数の算出に使用します。注意事項（3）を参照</td><td>整数</td><td>いいえ</td></tr><tr><td>max_event_counter</td><td>AppsFlyer</td><td>注意事項（3）を参照</td><td>整数</td><td>いいえ</td></tr><tr><td>min_time_post_install</td><td>AppsFlyer</td><td>注意事項（5）を参照</td><td>整数</td><td>いいえ</td></tr><tr><td>max_time_post_install</td><td>AppsFlyer</td><td>注意事項（5）を参照</td><td>整数</td><td>いいえ</td></tr><tr><td>af_attribution_flag</td><td>AppsFlyer</td><td>SSOT（Single Source of Truth）がオンの場合：trueであれば、AppsFlyerとSKANの両方でインストールがアトリビューションされています。 falseの場合、AppsFlyerではインストールがアトリビューションされていません。 skad_conversion_valueがnullの場合、フラグは<a href="./skan-modeled-data#null-conversion-values" target="_blank">モデリング</a>に基づいてtrueまたはfalseに設定されます。</td><td>ブール値</td><td>いいえ</td></tr><tr><td>measurement_window</td><td>AppsFlyer</td><td>アクティビティ期間の長さ。デフォルトは24時間です。 </td><td>整数</td><td>いいえ</td></tr><tr><td>interval</td><td>AppsFlyer</td><td>アクティビティ期間の間隔。 </td><td>整数</td><td>いいえ</td></tr><tr><td>user_agent</td><td>AppsFlyer</td><td>デバイスのユーザーエージェント</td><td>文字列</td><td>いいえ</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0 (iOS 16.2)</td><td><ul><li>SKANのウィンドウを表す値で、<code>0</code>、<code>1</code>、<code>2</code>のいずれかです。</li><li>SKAN 3では、値は<code>0</code>です。 </li></ul></td><td>整数</td><td>はい</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li>値は<code>low</code>、<code>medium</code>、<code>high</code>のいずれかです。</li><li>SKAN 3では、値は<code>null</code>です。</li></ul></td><td>文字列</td><td>はい</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>最大4桁の値です。</li><li>SKAN 3では、値は<code>null</code>です。 </li></ul></td><td>文字列</td><td>はい</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>アトリビューション対象となるWeb広告の流入元を表します。</li><li>SKAN 3では、値は<code>null</code>です。</li></ul></td><td>文字列</td><td>はい</td></tr><tr><td>ad_network_creative</td><td>アドネットワーク</td><td><ul><li>アドネットワークから受信した追加情報に基づく値です。</li><li>SKAN 3では、値は<code>null</code>です。</li></ul></td><td>文字列</td><td>いいえ</td></tr><tr><td colspan="4"><p>\*\*Appleが、プライバシーしきい値の仕組みに基づいて、フィールドに値を設定するかどうかを決定します。</p><p>（1）2021年6月2日以降、このフィールドはレポートに含まれますが、必ずしも値が設定されるわけではありません。</p><p>（3）ユーザーがアプリ内イベントを実行した回数は、次の式で算出します。<code>[round up (min_event_counter + max_event_counter) / 2]</code>。注意！ <mark>小数点以下を切り上げて、整数にする必要があります。</mark><br/>例：<br/>A. min=0、max=1の場合、平均は0.5となり、切り上げると1になります。<br/>B. min=5、max=10の場合、平均は7.5となり、切り上げると8になります。</p><p>（4）収益は常に<code>skad_revenue</code>フィールドで提供されます。 SKAN 4または<a href="./skan-conversion-studio" target="_blank">カスタムモード</a>では、イベントに対応する収益範囲をmin_revenueとmax_revenueで確認できます。この範囲を使って、skad_revenueを算出します。</p><p>(5)</p><ul><li>カスタムコンバージョン：AppsFlyerは、ポストバック到着時刻−36時間−average (min_time_post_install + max_time_post_install)としてインストール時刻を算出します。ただし、CV=0の場合、average (min_time_post_install + max_time_post_install)は0と見なします。 </li><li>デコードコンバージョン：max_time_post_installは、デコードマッピングで設定した<a href="./skan-cv-decode-map-your-cv-to-events#decode-csv-file-specification" target="_blank">hours_from_install</a>と同じ値です。min_time_post_installは、その1時間前の値になります。 </li></ul></td><td> </td></tr></tbody></table>

</Accordion>

## 補足情報

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| アドネットワークのアクセス | アドネットワークにはポストバックが提供されます。 |
| 代理店のアクセス | 利用不可 |
| 運用媒体の開示設定 | N/A |
| タイムゾーン | UTC |
| 通貨 | USD |
| オーガニックデータ | SDKイベントデータに基づきます。たとえば、オーガニックインストール数は、SDKが報告した全インストール数から、SKANが報告したノンオーガニックインストール数を差し引いて算出します。 |
| ノンオーガニックデータ | SKANポストバックに基づきます。 |
| データの更新頻度 | 日次。 SKANのタイミングにより、iOSはウィンドウ終了から24〜48時間後にインストールを報告します。 |
| 過去のデータ | Data Lockerで取得可能な期間に限られます。 |
| アカウントユーザーのアクセス | 利用できます。アカウントの権限に従います。 |

</Accordion>

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide#reporting-options">利用できるSKANレポート（SKANソリューションガイド）</Anchor>

<div data-zendesk-anchors="skan-raw-data-reports=skan%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 01H8XHATZB2G6YZ9AJNPRZS59Y=skan%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 skan-raw-data-report-format-and-content=skan%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%BD%A2%E5%BC%8F%E3%81%A8%E5%86%85%E5%AE%B9 01H8XHATZCJQZTZF0Y5P18XMEA=skan%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%BD%A2%E5%BC%8F%E3%81%A8%E5%86%85%E5%AE%B9 01H8XHATZCR5BC2P5TSQTMDY5Q=raw-data-report-types 01H8XHATZC0MST5ASGWDGGK2R8=raw-data-field-format-types field-formats=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E5%BD%A2%E5%BC%8F 01H8XHATZCZMNGK72DDE5HS6E9=%E3%83%95%E3%82%A3%E3%83%BC%E3%83%AB%E3%83%89%E3%81%AE%E5%BD%A2%E5%BC%8F 01H8XHATZC24DH4AYB2C523JDH=fields-available-in-postback-and-postback-copy-reports 01H8XHATZCNXVG0E3MZ9H68AA1=fields-available-in-decoded-event-reports additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 01H8XHATZD9D7JBHTFZ095EBD5=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 01H8XHATZDMV0VN4BDTECGF91K=traits-and-limitations h_01HDNYQBVZP0A6SQASGDRFVFGP=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />

---
title: Pull APIローデータ
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2026-10-19T18:38:52Z'
  id: 360007530258
  locale: ja
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ja/articles/360007530258
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** このAPIを使用すると、CSVファイルでローデータレポートを取得できます。

<div id="pull-api-raw-data" />

## Pull APIローデータ

* Pull APIを使用すると、CSVファイルでローデータレポートを取得できます。<Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview">ローデータレポートの詳細はこちら</Anchor>
* 利用可能なオプションでフィルターできます：メディアソース、日付範囲、アプリ内イベント名、地域。
* Pull APIの追加機能は次のとおりです：
  * 通貨を選択
  * タイムゾーンを選択

<div id="raw-data-reports-available-via-pull-api" />

#### Pull APIで利用可能なローデータレポート

<table><thead><tr><th>レポート</th><th>説明</th><th>更新頻度</th></tr></thead><tbody><tr><td colspan="3"><h4><span id="raw-data-reports-non-organic"></span><strong><span id="raw-data-reports-nonorganic"></span>ローデータレポート（非オーガニック）</strong></h4></td></tr><tr><td><a href="" target="_blank">インストール</a></td><td>非オーガニックインストールを記録します。ユーザーが初めてアプリを起動したときに記録が生成されます。<br/> </td><td>リアルタイム</td></tr><tr><td><a href="" target="_blank">アプリ内イベント</a></td><td>ユーザーが実行したイベントを記録します。<br/> </td><td>リアルタイム</td></tr><tr><td><a href="" target="_blank">アンインストール</a></td><td>ユーザーがアプリをアンインストールしたときに記録します。<br/> </td><td>日次</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">再インストール</a><br/> </td><td>アプリをアンインストールした後にUAメディアソースと接触し、リアトリビューション期間中にアプリを再インストールしたユーザーを記録します。</td><td>リアルタイム</td></tr><tr><td colspan="3"><h4><strong><span id="raw-data-reports-organic"></span>ローデータレポート（オーガニック）</strong></h4></td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">オーガニックインストール</a><br/> </td><td>ユーザーが初めてアプリを起動したときに記録します。<br/> </td><td>継続的</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">オーガニックアプリ内イベント</a><br/> </td><td>ユーザーが実行したイベントの詳細を記録します。<br/> </td><td>継続的</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">オーガニックアンインストール</a><br/> </td><td>ユーザーがアプリをアンインストールした記録。<br/> </td><td>日次</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">オーガニック再インストール</a><br/> </td><td>ユーザーがアプリをアンインストールした後、再度インストールしたことを記録します。</td><td>日次<br/> </td></tr><tr><td colspan="3"><h4><strong><span id="retargeting"></span>リターゲティング</strong></h4></td></tr><tr><td><a href="">コンバージョン</a></td><td>リターゲティングキャンペーンに接触した後にアプリを開いたユーザーの記録。</td><td>リアルタイム</td></tr><tr><td><a href="">アプリ内イベント</a></td><td>リエンゲージメント期間中にユーザーが実行したアプリ内イベント。</td><td>リアルタイム</td></tr><tr><td colspan="3"><h4><strong><span id="ad-revenue-raw-data"></span>広告収益のローデータ</strong></h4></td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">帰属広告収益</a><br/> </td><td>メディアソースに帰属するユーザーの広告収益を記録します。</td><td>日次</td></tr><tr><td><a href="" target="_blank">オーガニック広告収益</a></td><td>メディアソースに帰属しないユーザーの広告収益を記録します。</td><td>日次</td></tr><tr><td colspan="3"><h4><strong><span id="protect360-fraud"></span>Protect360の不正防止</strong></h4></td></tr><tr><td><a href="" target="_blank">インストール</a></td><td>不正と識別されたため、どのメディアソースにも帰属されなかったインストールを記録します。</td><td>リアルタイム</td></tr><tr><td><a href="" target="_blank">アトリビューション後のインストール</a></td><td>不正なインストールから発生したため、まったく帰属されなかったアプリ内イベントを記録します。</td><td>日次</td></tr><tr><td><a href="" target="_blank">アプリ内イベント</a></td><td>Protect360によって不正と識別されたアプリ内イベントを記録します。</td><td>リアルタイム</td></tr><tr><td><a href="" target="_blank">アトリビューション後のアプリ内イベント</a></td><td>メディアソースに帰属された後に不正と識別されたインストール、またはインストール自体にかかわらず不正と判定されたインストールに関連するアプリ内イベントを記録します。</td><td>日次</td></tr><tr><td><a href="" target="_blank">クリック</a></td><td>Protect360によってブロックされたユーザーのクリックを記録します。</td><td>リアルタイム</td></tr><tr><td><a href="" target="_blank">ブロック済みインストールポストバック</a></td><td>インストールがブロックされた結果としてメディアソースに送信されたポストバックのコピーを記録します。</td><td>リアルタイム</td></tr><tr><td colspan="3"><strong>ポストバック</strong></td></tr><tr><td><a href="" target="_blank">インストールポストバック</a></td><td>ユーザーが初めてアプリを起動したときに生成されたインストールイベントを記録します。</td><td>日次</td></tr><tr><td><a href="" target="_blank">アプリ内イベントポストバック</a></td><td>メディアソースに送信されたアプリ内イベントポストバックを記録します。</td><td>日次</td></tr><tr><td><a href="" target="_blank">リターゲティングアプリ内イベントポストバック</a></td><td>リエンゲージメント期間中にユーザーが実行したアプリ内イベントを記録します。</td><td>リアルタイム</td></tr><tr><td><a href="" target="_blank">リターゲティングコンバージョンポストバック</a></td><td>リエンゲージメント期間中にユーザーが実行したアプリ内イベントを記録します。</td><td>リアルタイム</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="Pull APIローデータの使用">

**Pull APIローデータを使用するには**：

1. <Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#トークンページを開く">APIトークンを取得します</Anchor>。管理者はトークンを取得する必要があります。
2. 認証ヘッダーで使用するAPIトークンを開発者に渡します。
3. 次のセクションで説明するように、APIコールを行う際に入力するパラメータを開発者に渡してください。パラメータは、レポートの対象と構成、およびレポートの期間を決定します。
4. 開発者に、Developer Hubの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">Pull APIローデータの手順</Anchor>に従うよう伝えてください。

<div id="parameters" />

#### パラメータ

| パラメータ | 説明 |
| --- | --- |
| from | <ul><li>日付範囲は`from`パラメータと`to`パラメータで構成されます。日付はアクティビティ日に基づきます。</li><li>形式：`yyyy-mm-dd`、`yyyy-mm-dd hh:mm`、または`yyyy-mm-dd hh:mm:ss` **注意：** スペースは、次のようにエンコードする必要があります：`from=2020-04-01%2001:00:00`。通常、ブラウザがスペースをエンコードします。</li><li>例：2010-01-01 または 2010-01-01 20:15（ローデータレポートでは時刻と分を指定できます）。</li></ul> |
| to | 終了日。 `from`と同様です。 |
| media\_source | `media_source`：特定のメディアソースに絞り込む（フィルターする）ためのパラメータです。<br /><br />`media_source`と`category`の両方のパラメータを次のように設定します。<ul><li>Meta広告の場合、categoryとmedia sourceを*facebook*に設定します。</li><li>X広告の場合、categoryとmedia sourceを*twitter*に設定します。</li><li>その他のメディアソースの場合は、categoryを*standard*に、media sourceをメディアソース名に設定します。</li></ul><ul><li>例<ul><li>`media_source=facebook&category=facebook`</li><li>`media_source=abc_example&category=standard`</li></ul></li></ul> |
| maximum\_rows | 1回のAPIコールで返される行数の上限です。<ul><li>［デフォルト］値を指定しない場合は最大200K行</li><li>200000：最大200K行が返されます</li><li>1000000：最大1M行が返されます</li><li>例：`maximum_rows=1000000`を指定すると、最大1M行を取得できます。</li></ul> |
| event\_name | 指定したイベントでアプリ内イベントをフィルタリングします。カンマ区切りのリストを使用して、複数のイベントを選択できます。<br /><br />**例：**`event_name=af_purchase,ftd` |
| reattr | リターゲティングのアトリビューションデータを設定します。<ul><li>［デフォルト］falseの場合、ユーザー獲得（UA）キャンペーンのデータが返されます。</li><li>trueの場合、リターゲティングのアトリビューションデータが返されます。</li><li>**例：**`reattr=true`</li></ul> |
| additional\_fields | デフォルトフィールドに加えて、追加フィールドを取得します。<br /><br />**例：**`additional_fields=device_download_time,deeplink_url` |
| currency | 収益とコストの通貨<ul><li>［デフォルト］パラメータを指定しない場合、データはUSDで返されます。つまり、何も設定しない場合、結果はUSDで返されます。</li><li>`currency=preferred`を指定すると、<Anchor target="_blank" href="/marketers/ja/docs/app-settings#localization-time-zone">アプリ固有の</Anchor>通貨が使用されます。 これは、アプリ設定で指定した通貨です。</li></ul>**例：** アプリ固有の通貨がEURの場合、`currency=preferred`を指定すると値はEURで返されます。 |
| timezone | ［デフォルト］データはUTCで返されます。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/app-settings#localization-time-zone">アプリ固有の</Anchor>タイムゾーンでデータを取得するには、このセクションに記載されている方法で、`timezone`をAPIコールに追加します。</li></ul><ul><li>`timezone=[Numerical value]`</li><li>例：タイムゾーンがUTC+10:00の場合は`timezone=+10:00`を使用します。**注意：**`+`、`-`、`:`はエンコードする必要があります。例：+10:00は`%2B10%3A00`にエンコードされます。</li></ul> |
| geo | 国コードでデータをフィルタリングします。<br /><br />制限：1回のAPIコールにつき、国コードのフィルターは1つだけ設定できます。<br /><br />例：`geo=ZA` |
| from\_install time | <ul><li>日付範囲は`from`パラメータと`to`パラメータで構成されます。日付はアクティビティ日に基づきます。</li><li>形式：`yyyy-mm-dd`</li><li>例：2010-01-01</li></ul> |
| to\_install\_time | 終了日。 `from_install time`と同様です。 |
| agency | 特定の代理店に絞り込む（フィルターする）ためのパラメータです。 |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Protect360のフィールド">

Protect360ローデータガイドを参照してください。

</Accordion>

<div id="time-frame-fields" />

<Accordion title="時間枠のフィールド">

APIの結果が上限を超える場合は、時刻と分を指定してレポートを分割します。次の設定を適用します：

* **from**/**to：yyyy-mm-dd hh:mm**
* **from：**
  * 日付のみ = 選択した日の開始時刻（00:00）から
  * 日付と時刻 = 00:00から（00:00を含む）
* パラメータ**to：**
  * 日付のみ = 選択した日の終了時刻（24:00）まで
  * 日付と時刻 = 表示された時刻まで（その時刻は含まない）

**例：** あるアプリ所有者が、すべてのソースから毎日130万件のインストールを受信しているとします。 100万行の上限を超えないように、アプリ所有者は1日を12時間ずつに分けて2回のURIコールを行います。次の表に示す方法を使用できます。

<table><thead><tr><th>APIコール</th><th>From </th><th>To </th></tr></thead><tbody><tr><td><strong>1回目のAPIコール</strong> </td><td><p><strong>from</strong>=yyyy-mm-dd</p><p><strong>例：</strong></p><ul><li> <strong>from</strong>=<code>2019-12-29</code> </li><li>この日の00:00に開始します。</li></ul></td><td><p><strong>to</strong>=yyyy-mm-dd 12:00</p><p><strong>例：</strong></p><ul><li> <strong>to</strong>=<code>2019-12-29 12:00</code> </li><li>12:00ではなく、11:59:59まで続きます。 </li></ul></td></tr><tr><td><p><strong>オプションA：2回目のAPIコール</strong> </p><p><strong>例：</strong> </p><p><code><kbd><strong>&amp;from=2019-12-29 12:00&amp;to=2019-12-29</strong></kbd></code></p><ul><li>2019年12月29日12:00から開始します。</li><li>2019年12月30日00:00に終了します。</li></ul></td><td><p><strong>from</strong>=yyyy-mm-dd 12:00</p><p><strong>例：</strong></p><ul><li> <strong>from</strong>=<code>2019-12-29 12:00</code> </li><li>12:00から開始し、12:00を含みます。</li></ul></td><td><p><strong>to</strong>=yyyy-mm-dd</p><p><strong>例：</strong></p><ul><li> <strong>to</strong>=<code>2019-12-29</code> </li><li>00:00に終了します。</li></ul></td></tr><tr><td><strong>オプションB：2回目のAPIコール</strong></td><td><p><strong>from</strong>=yyyy-mm-dd 12:00</p><p><strong>例：</strong></p><ul><li> <strong>from</strong>=<code>2019-12-29 12:00</code> </li><li>12:00から開始し、12:00を含みます。</li></ul></td><td><p><strong>to</strong>=yyyy-mm-dd+1 00:00</p><p><strong>+1</strong> = 翌日の00:00</p><p><strong>例：</strong></p><ul><li> <strong>to=</strong><code><strong>2019-12-30 00:00</strong></code> </li><li>つまり、12月30日の00:00になる前を意味します。</li></ul></td></tr><tr><td colspan="3"> <strong>注意：</strong>オプションAまたはBを使用してください。どちらも同じ結果になります。 </td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="追加フィールド">

新しいフィールドによって既存のインポートおよび取り込み処理に影響が出ないよう、追加のレポートフィールドはデフォルトのフィールド一覧には追加されません。デフォルト以外のフィールドを取得するには、`additional_fields`パラメータを使用します。

* 各フィールドは1回だけ指定してください。
* <Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">利用可能なフィールドの一覧</Anchor>を参照してください。
* 例：`additional_fields=device_download_time,deeplink_url`

</Accordion>

<div id="default-fields" />

<Accordion title="デフォルトフィールド">

| Pull APIのデフォルトフィールド |
| --- |
| アトリビューションタッチタイプ |
| アトリビューションタッチ時間 |
| インストール時間 |
| イベント時間 |
| イベント名 |
| イベント値 |
| イベント収益 |
| イベント収益通貨 |
| イベント収益（USD） |
| イベントソース |
| レシート検証済み |
| パートナー |
| メディアソース |
| チャネル |
| キーワード |
| キャンペーン |
| キャンペーンID |
| 広告セット |
| 広告セットID |
| 広告 |
| 広告ID |
| 広告タイプ |
| サイトID |
| サブサイトID |
| サブパラメータ1 |
| サブパラメータ2 |
| サブパラメータ3 |
| サブパラメータ4 |
| サブパラメータ5 |
| コストモデル |
| コスト値 |
| コスト通貨 |
| コントリビューター1のパートナー |
| コントリビューター1のメディアソース |
| コントリビューター1のキャンペーン |
| コントリビューター1のタッチタイプ |
| コントリビューター1のタッチ時間 |
| コントリビューター2のパートナー |
| コントリビューター2のメディアソース |
| コントリビューター2のキャンペーン |
| コントリビューター2のタッチタイプ |
| コントリビューター2のタッチ時間 |
| コントリビューター3のパートナー |
| コントリビューター3のメディアソース |
| コントリビューター3のキャンペーン |
| コントリビューター3のタッチタイプ |
| コントリビューター3のタッチ時間 |
| 地域 |
| 国コード |
| 州 |
| 市 |
| 郵便番号 |
| DMA |
| IP |
| WIFI |
| オペレーター |
| キャリア |
| 言語 |
| AppsFlyer ID |
| Advertising ID |
| IDFA |
| Android ID |
| Customer User ID |
| IMEI |
| IDFV |
| プラットフォーム |
| デバイスタイプ |
| OSバージョン |
| アプリバージョン |
| SDKバージョン |
| アプリID |
| アプリ名 |
| バンドルID |
| リターゲティング |
| リターゲティングコンバージョンタイプ |
| アトリビューションルックバック期間 |
| リエンゲージメント期間 |
| プライマリアトリビューション |
| ユーザーエージェント |
| HTTPリファラ |
| 元のURL |

</Accordion>

<div id="additional-information" />

## 追加情報

<div id="traits-and-limitations" />

<Accordion title="特性と制限事項">

| 特性 | 備考 |
| --- | --- |
| 必要なAPIトークンタイプ | <Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">V2.0トークン</Anchor> |
| アドネットワークのアクセス | いいえ |
| 代理店によるデータアクセス | はい |
| 運用媒体の開示設定 | はい。ただし、代理店フィルターとメディアソースフィルターの両方を使用する場合、メディアソースフィルターは非透明な代理店には適用されません。これは、非透明な代理店の場合、フィルタリングしたメディアソースのデータだけでなく、すべてのデータが含まれることを意味します。 |
| アプリ固有の通貨 | はい |
| アプリ固有のタイムゾーン | はい |
| データ更新頻度 | <ul><li>オーバービュー管理画面でのデータの利用可能状況と同等です。</li><li>数時間のタイムラグで更新されるレポート：<ul><li>オーガニックアプリ内イベント</li></ul></li><li>日次で更新されるレポート：<ul><li>アンインストール</li><li>アトリビューション後のアプリ内イベント</li><li>広告収益</li></ul></li></ul> |
| 過去データ | はい。  <Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention">データ保持</Anchor>および<Anchor target="_blank" href="/marketers/ja/docs/report-generation-quotas-rate-limitations">レート制限</Anchor>のポリシーに従います。 |
| 非オーガニックデータ | はい |
| オーガニックデータ | はい |
| レート制限 | <Anchor target="_blank" href="/marketers/ja/docs/report-generation-quotas-rate-limitations">ローデータ</Anchor>に関するAPIの制限です。 |
| サイズ制限 | <ul><li>APIコールでは最大200K行または1M行が返されます。</li><li>レポートの行数が200K行または1M行ちょうどの場合、データが欠落していると考えてください。</li><li>最大行数を指定するには、maximum\_rowsパラメータを使用します。</li><li>時刻を含むfrom/toパラメータを使用して、複数のAPIコールを実行します。</li></ul> |
| install\_date\_fromとinstall\_date\_to | インストール日の日付範囲は、アクティビティの日付範囲より前である必要があります。 |

</Accordion>

<div id="troubleshooting" />

<Accordion title="トラブルシューティング">

| 症状／メッセージ | 解決策 |
| --- | --- |
| 選択した期間に対して期待されるデータがレポートに含まれていない、またはローデータレポートと集計データレポートの間に差異がある場合。 | `timezone`パラメータが設定されていることを確認してください。設定していない場合、データはアプリのタイムゾーンではなくUTCで送信されます。 |

</Accordion>

<div id="see-also" />

> 📄 **関連情報**
>
> * 適切なデータ配信ツール／レポートAPIの選択

<div data-zendesk-anchors="pull-api-raw-data=pull-api%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF h_01HE7S6WDVJD2XFW498P8FPY7W=pull-api%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF aggregate-performance-reports-available-via-pull-api=pull-api%E3%81%A7%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HE7S6WDV59VTP6Z4X790QDRD=pull-api%E3%81%A7%E5%88%A9%E7%94%A8%E5%8F%AF%E8%83%BD%E3%81%AA%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01KEVCHC25BDNS9F1GEPBDAW39=raw-data-reports-nonorganic h_01KEVCHJ8TRRM9BYW6C544PNFR=raw-data-reports-organic h_01KEVCHSNGPX2RW917QX4N03A2=retargeting h_01KEVCHYMHGC6VTVSERH611Q8X=ad-revenue-raw-data h_01KEVCJ3GWBZG8SWHZKTRJ6YAX=protect360-fraud h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data parameters=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HE7S6WDVF8T4719HWDJH8JN1=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HE7S6WDW9V8XC3CJ0F96EHN0=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />

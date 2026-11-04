---
title: Protect360｜ローデータレポート
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - Raw Data
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2026-10-21T18:35:09Z'
  id: 360015179337
  locale: ja
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ja/articles/360015179337
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** ローデータレポートには、Protect360エンジンや手動で追加した検証ルールによってブロックされたインストールとアプリ内イベントが表示されます。

<div id="about-protect360-raw-data-reports" />

## Protect360ローデータレポートについて

ローデータレポートには、次の特徴があります。

* 次のデータを表示します。
  * Protect360エンジンによって不正と判定されたクリック、インストール、アプリ内イベント。
  * 検証ルールによって判定されたインストールとアプリ内イベント。
* クリック、インストール、アプリ内イベントごとに、ブロック理由が含まれます。
* 広告主は、アドネットワークとの広告費の精算、最適化、ポストアトリビューション不正を考慮したアトリビューションダッシュボードの調整に使用できます。
* <Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">AppsFlyer Aggregated Advanced Privacy（AAP）</Anchor>を適用している場合、<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">一部のフィールドが制限されるか、利用できない</Anchor>ことがあります。0>
* レポートの種類と、ダウンロード、API、Data Locker（S3バケット）での利用可否は、以下の各セクションで説明します。
* 過去のローデータレポートの保存期間は、レポート取得ツールとローデータの取得元によって異なり、最大90日です。 0>

<div id="note" />

> 📘 **注意**
>
> プライバシーに関連するローデータの制限により、レポートの一部のフィールドが空欄になる場合があります。例えば、アトリビューションに貢献した流入元のフィールドが該当します。

<div id="report-types" />

<Accordion title="レポートの種類">

<div id="protect360-raw-data-report-types" />

#### Protect360ローデータレポートの種類

| レポート | 説明 |
| --- | --- |
| <span id="installs"></span>インストール | レポートには次のデータが含まれます。<ul><li>**偽のインストール**：Protect360エンジンによって不正と判定されたインストール。 Protect360のダッシュボードとローデータ以外には、AppsFlyerのどのダッシュボードやローデータにも表示されません。</li><li>**ハイジャックされたインストール**：実際のユーザーによるインストールの成果が横取りされたもの。Protect360が[アトリビューションを修正](/docs/protect360-raw-data-reports#ハイジャックされたインストールのアトリビューション修正)します。</li><li>**検証ルール**：インストールまたはアトリビューションをブロックしたもの。Protect360が[アトリビューションを修正](/docs/protect360-raw-data-reports#ハイジャックされたインストールのアトリビューション修正)します。</li></ul> |
| <span id="postattribution-installs"></span>ポストアトリビューションインストール | レポートには、メディアソースに紐づけられた後に不正と判明したインストールが含まれます。 Protect360が[アトリビューションを修正](/docs/protect360-raw-data-reports#ハイジャックされたインストールのアトリビューション修正)します。 |
| <span id="blocked-inapp-events"></span>ブロックされたアプリ内イベント | レポートには、次に該当するアプリ内イベントが含まれます。<ul><li>**偽のインストール**：アプリ内イベントがブロックされます。</li><li>**アプリ内イベント**：元のインストールとは関係なく、不正と判定されたもの。</li><li>**検証ルール**：<ul><li>インストールまたはアトリビューションをブロックしたルールに関連するアプリ内イベント。</li><li>アプリ内イベントをブロックしたルールに関連するアプリ内イベント。</li></ul></li></ul> |
| <span id="postattribution-inapp-events"></span>ポストアトリビューションアプリ内イベント | レポートには、次のアプリ内イベントが含まれます。<ul><li>ポストアトリビューションで判明したもの。</li><li>メディアソースに紐づけられた後に不正と判明したインストールに関連するもの。</li></ul> |
| <span id="clicks"></span>クリック | レポートには、ブロックされたクリックとそのブロック理由が含まれます。 |
| <span id="blocked-install-postbacks"></span>ブロックされたインストールのポストバック | レポートには、ブロックされたインストールの流入元のメディアソースに送信した、拒否ポストバックのコピーが含まれます。 |

</Accordion>

<div id="postattribution-reports" />

<Accordion title="ポストアトリビューションレポート">

* ポストアトリビューション不正のローデータレポートは、ブロックされた不正のレポートと同じ構造です。
* 当月のポストアトリビューションレポート（インストール日基準）は、翌月7日（検知日基準）まで更新されます。
* ポストアトリビューションのローデータレポートは、広告主のみ利用できます。代理店がアクセスするには、<Anchor target="_blank" href="/partners/ja/docs/protect360-for-integrated-partners">権限</Anchor>を付与される必要があります。
* レポートには、Protect360が検知したポストアトリビューション不正のイベントが含まれ、すべてのメディアソースが1つのレポートにまとめられます。**注意**：選択した日付範囲にポストアトリビューション不正のイベントが検知されていない場合、レポートは空になります。
* ポストアトリビューション不正のローデータレポートは、次の方法で利用できます。
  * ダッシュボードの画面：1暦月の1つのメディアソースに限定されます。
  * Pull API：すべてのメディアソースを含みます。（制限：アプリ所有者のみ利用できます。）

<div id="using-post-attribution-reports" />

#### **ポストアトリビューションレポートの利用方法**

* 必要に応じて、インストール／アプリ内イベントの日付範囲と、検知日の日付範囲を組み合わせて指定します。
* Protect360は、インストールが発生した月から翌月7日まで、ポストアトリビューションの不正検知を行う点に注意してください。例えば、11月のインストールは、12月7日まで不正の確認が行われます。
* このPull APIの推奨される利用方法は、次のとおりです。
  * 毎日レポートを取得する場合を想定します。
  * インストール日の範囲は、当日から過去60日間に設定します。
  * detect-from／detect-toの範囲は、当日の前日に設定します。  
    これにより、前日に検知されたポストアトリビューション不正の一覧を取得できます。数日間レポートを取得していなかった場合は、検知日の範囲を調整して取得してください。

<div id="example" />

> 📄 **例**
>
> **例A**：12月（インストール日）に、15件のインストールがexample\_mediaに紐づけられました。 1月3日（検知日）に、Protect360がexample\_mediaを不正な流入元と判定しました。その結果、example\_mediaに紐づいた15件のインストールが、ポストアトリビューション不正レポートに不正として記載され、アプリ所有者が対応を行えます。
>
> **例B**：12月に、15件のインストールがexample\_mediaに紐づけられました。 1月9日に、Protect360がexample\_mediaを不正な流入元と判定しました。この場合、1月7日の月次締め後に不正な流入元が判明したため、Protect360は処理を行いません。

</Accordion>

<div id="raw-data-availability-by-tool-type" />

<Accordion title="取得ツール別のローデータの利用可否">

<div id="protect360-raw-data-availability-by-tool-type" />

#### 取得ツール別のProtect360ローデータの利用可否

<table><thead><tr><th>レポート</th><th>データの更新頻度</th><th>Pull API</th><th>データ出力ページ</th><th>Data Locker</th></tr></thead><tbody><tr><td>インストール</td><td>リアルタイム</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>ブロックされたアプリ内イベント</td><td>リアルタイム</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>クリック</td><td>リアルタイム</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>ブロックされたインストールのポストバック</td><td>リアルタイム</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>ポストアトリビューションインストール</td><td>日次、UTC 15:00</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>ポストアトリビューションアプリ内イベント</td><td>日次、UTC 20:00</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="5"><p>\* Data Lockerで取得するレポートの制限：</p><ul><li>運用媒体の開示設定には対応していません。そのため、代理店経由のトラフィックには、インストールを送信したメディアソースの名前が含まれません。</li><li>他のData Lockerレポートとは異なる、専用のフィールド構成です。このフィールドの一覧は変更できません。</li><li>リターゲティングデータは、インストールレポートでは利用できません。ポストアトリビューションインストールレポートでのみ利用できます。 </li></ul></td></tr></tbody></table>

</Accordion>

<div id="getting-raw-data-reports" />

## ローデータレポートの取得

ローデータレポートは、ダウンロード、Pull API、Data Locker（S3バケット）で利用できます。<Anchor target="_blank" href="/partners/ja/docs/protect360-for-integrated-partners">パートナーにレポートへのアクセス権を付与</Anchor>することもできます。

<div id="download" />

<Accordion title="ダウンロード">

**ダウンロードするには：**

1. Protect360ダッシュボードで、**ローデータレポート** > **ブロック**または**ポストアトリビューション**に移動します。
   * ポストアトリビューションレポートの場合は、メディアソースと月を選択します。
2. ダウンロードする**Protect360と検証ルール**のレポートを選択します。

**OR**

1. AppsFlyerダッシュボードで、**データ出力**に移動します。
2. ダウンロードする**Protect360と検証ルール**のレポートを選択します。

**注意**：データ出力ページからダウンロードしたレポートには、すべてのメディアソースが含まれます。

</Accordion>

<div id="pull-api" />

<Accordion title="Pull API">

**Pull APIで利用できるローデータレポートをダウンロードするには：**

**事前準備：**

Pull APIトークンが必要です。<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">管理者ユーザー</Anchor>からトークンを取得してください。

1. レポート > APIアクセス  
   に移動します。<Anchor target="_blank" href="/marketers/ja/docs/pull-api-raw-data">Pull API</Anchor>ページが開きます。
2. Protect360不正レポートのセクションで、必要なPull APIの呼び出しを選択します。
3. 必要に応じてパラメータを入力します。パラメータは次の表に記載されています。
4. レポートを取得します。

<div id="pull-api-raw-data-report-parameters" />

#### Pull APIローデータレポートのパラメータ

| パラメータ | 説明 | 形式 | 必須 |
| --- | --- | --- | --- |
| app\_id | AppsFlyerに表示されるアプリID | 文字列 | はい |
| api\_token | ダッシュボードからキーを取得します。**レポート** > **APIアクセスに移動します。** APIトークンを取得できるのは、管理者ユーザーのみです。 | 文字列 | はい |
| from | 日付範囲の開始日：<ul><li>インストールの場合は、インストール日です。</li><li>アプリ内イベントの場合は、イベント発生日です。</li></ul> | YYYY-MM-DD | はい |
| to | 日付範囲の終了日：<ul><li>インストールの場合は、インストール日です。</li><li>アプリ内イベントの場合は、イベント発生日です。</li></ul> | YYYY-MM-DD | はい |
| event\_name | ［ポストアトリビューションのアプリ内イベント不正では任意］<br /><br />アプリ内イベントの種類で絞り込みます。レポートを特定のイベントに限定します。  1つ以上のイベントを指定できます。<br /><br />使用例：`&event_name=af_purchase,af_login` | 文字列 | いいえ |
| additional\_fields=rejected\_reason\_value | ［ポストアトリビューションのアプリ内イベント不正では任意］<br /><br />**<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>** には、ハイジャックされたインストールやアプリ内イベントの、有効なアトリビューションに貢献した流入元（メディアソース）が表示されます。 <Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributor[1-3]**</Anchor>または**organic**が入力されます。 | 文字列 | いいえ |
| detect-from | ［ポストアトリビューションインストールでは任意］<br /><br />不正検知日の範囲の開始日。（デフォルトはfromです。）（ポストアトリビューションのインストール不正で使用します。） （ポストアトリビューションのインストール不正で使用します。） | YYYY-MM-DD | いいえ |
| detect-to | ［ポストアトリビューションインストールでは任意］<br /><br />不正検知日の範囲の終了日。（デフォルトはtoです。） | YYYY-MM-DD | いいえ |

</Accordion>

<div id="data-locker" />

<Accordion title="Data Locker">

Data Lockerは、ローデータをAWS S3バケットに書き込みます。

<Anchor target="_blank" href="/marketers/ja/docs/data-locker-advertiser-reports#protect360">利用できるProtect360レポートの一覧</Anchor>をご覧ください。 

<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#aws-cli">Data Lockerの設定手順</Anchor>をご覧ください。

</Accordion>

<div id="protect360-report-structure" />

## Protect360レポートの構造

Protect360レポートの基本的なフィールド構成は、ユーザー獲得レポートと同じです。

通常の<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">ローデータレポートのフィールド</Anchor>に加え、Protect360レポートには、次のリターゲティングとブロック理由のフィールドがあります。

<div id="blocked-reasons" />

### ブロック理由

<div id="click-level-blocked-reasons" />

<Accordion title="クリック単位のブロック理由">

クリック単位では、クリックをブロックし、アトリビューションの判定対象から除外します。

| ブロック理由 | 説明 |
| --- | --- |
| ip\_blacklist | 状況に応じて作成されるリストに基づきます（<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide#ip-denylists">詳細</Anchor>）。 |
| click\_capping | そのアドネットワークで、クリック不正の割合が極めて高いことが検知されています。<Anchor target="_blank" href="/partners/ja/docs/protect360-for-integrated-partners#インプレッションとクリックの上限ブロックcapping">詳しくはこちら</Anchor> |
| click\_signing | クリックの署名を検証できません。<Anchor target="_blank" href="/partners/ja/docs/click-signing-for-ad-networks">詳しくはこちら</Anchor> |
| input\_validation | 無効なメディアソース名 |

</Accordion>

<div id="install-level-blocked-reasons" />

<Accordion title="インストール単位のブロック理由">

インストール単位では、インストール時に十分な情報を収集し、次のいずれかを判定します。

* 偽のインストール：アプリをインストールしたユーザーが実在しない場合。この場合、アトリビューションは完全にブロックされます。
* アトリビューションハイジャック：ユーザーは実在するものの、広告接触が偽装されている場合。この場合、不正な広告接触をブロックし、最初の有効なアトリビューションに貢献したアドネットワークにアトリビューションを付け替えます。

次の表に、インストール単位のブロック理由を示します。

<div id="install-level-fake-install-block-sub-reasons" />

#### インストール単位：偽のインストールのブロック理由の詳細

| ブロック理由 | ブロック理由の詳細 | 説明 |
| --- | --- | --- |
| bots | fake\_device\_parameters | アプリのインストール処理中に、デバイス関連のパラメータで、人間によるものとは考えにくい動作が検知された場合 |
| bots | fake\_install\_parameters | アプリのインストール処理中に、インストール関連のパラメータで、人間によるものとは考えにくい動作が検知された場合 |
| bots | bayesian\_network | ベイジアンネットワーク（確率に基づく分析モデル）によって不正なパターンを特定 |
| bots | user activity anomalies | 行動の異常検知モデルを使い、アプリ内での異常なユーザー行動や不審なユーザー行動を特定します。これらのモデルは、次の処理を行います。<ul><li>個々のユーザーの行動を分析</li><li>想定される行動パターンからのずれを特定</li><li>正常なユーザーの特徴とは異なる、行動のまとまりを検知</li><li>これにより、実際のユーザーを模倣しながら、通常とは異なる方法でアプリ内の操作を行うボットの活動を特定できます。</li></ul> |
| bots | store validation | 各インストールが、正規の想定された流入元から発生したことを検証します。この仕組みは、次の処理を行います。<ul><li>ユーザー獲得チャネルの正当性を検証</li><li>偽装・改ざんされたインストール情報を検知</li><li>正規の配信経路に合致しないインストールを拒否</li><li>インストール単位で正当性を確認することで、オーガニックや広告経由のインストールを偽装しようとするボットをブロックします。</li></ul> |
| bots | App-interaction anomalies | インストール後のアプリ利用時に、アプリ内イベントに基づかないイベントに目印を付けます。インストールから起動までの過程における不審な行動の特定に役立ちます。 |
| validation\_bots | invalid\_device\_parameters | 特定のデバイスフィールドが、お客様の定義した想定値と一致しない場合 |
| validation\_bots | validation\_rules | 手動で定義した検証ルールに基づき、インストールをブロックするルール |
| bots | ai\_layer | AIモデルで膨大なデータを分析し、不正なデバイスの活動やインストールの検知能力を高めます。 |

<div id="install-level-attribution-hijacking-block-sub-reasons" />

#### インストール単位：アトリビューションハイジャックのブロック理由の詳細

| ブロック理由 | ブロック理由の詳細 | 説明 |
| --- | --- | --- |
| ctit\_anomalies | short\_ctit | CTITが短いためにブロックされたインストール：Protect360による定義 |
| install\_hijacking | referrer\_hijack | Google Play APIとAppsFlyer SDKのパラメータに基づき、ブロックされたハイジャックの試み |
| install\_hijacking | integration\_temporarily\_blocked | パートナー（pid）の不正率が極めて高く、トラフィック全体に重大な異常があるためにブロックされたインストール |
| validation\_hijacking | short\_ctit | CTITが短いためにブロックされたインストール：お客様による定義 |
| validation\_hijacking | empty\_site\_id | サイトIDが入力されていないためにブロックされたインストール。ルールは段階的に適用されます。 |
| validation\_hijacking | validation\_rules | 手動で定義した検証ルールに基づき、アトリビューションをブロックするルール |

</Accordion>

<div id="cluster-level-blocked-reasons" />

<Accordion title="不正パターンのまとまりに基づくブロック理由">

不正のパターンが検知されると、その流入元が拒否リストに登録されます。拒否リストに登録された流入元からのインストールは、次のいずれかの理由でブロックされます。

* 偽のインストール：アプリをインストールしたユーザーが実在しない場合。この場合、アトリビューションは完全にブロックされます。
* アトリビューションハイジャック：ユーザーは実在するものの、広告接触が偽装されている場合。この場合、不正な広告接触をブロックし、最初の有効なアトリビューションに貢献したアドネットワークにアトリビューションを付け替えます。

次の表に、不正パターンのまとまりに基づくブロック理由を示します。

<div id="cluster-level-fake-install-block-reasons" />

#### 不正パターンのまとまりに基づく判定：偽のインストールのブロック理由

| ブロック理由 | ブロック理由の詳細 | 説明 |
| --- | --- | --- |
| bots | timestamp\_anomalies | アトリビューションの過程でのクリック時刻や、デバイスから取得したその他のタイムスタンプに関する異常 |
| bots, site\_blacklist | device\_emulators | 仮想環境で動作する自動スクリプトによって大量に生成されたインストール |
| site\_blacklist | device\_farms | 未識別の（新規）デバイスの割合が高い場合 |
| behavioral\_anomalies | behavioral\_anomalies | 一般的なアプリユーザーの行動パターンと比較して、不審なアプリ内の行動 |

<div id="cluster-level-attribution-hijacking-block-reasons" />

#### 不正パターンのまとまりに基づく判定：アトリビューションハイジャックのブロック理由

| ブロック理由 | ブロック理由の詳細 | 説明 |
| --- | --- | --- |
| ctit\_anomalies, install\_hijacking | ctit\_anomalies | そのアプリの基準と比べて異常なCTITのパターン |
| click\_flood | click\_flood | CTITが長い範囲にわたって、クリック数が異常に多い場合 |
| install\_hijacking | click\_clusters | デバイス上のマルウェアによって生成されたクリック |
| Re-engagement Hijacking | Re-engagement Click Clusters | リエンゲージメントのアトリビューションをハイジャックする不正の試みを検知します。こうした操作は、正規のリターゲティングネットワークの成果や、リターゲティング広告を一切見ていないユーザーの成果までも横取りすることを目的としています。<br />検知されると、アトリビューションが修正され、次のいずれかに付け替えられます。<ul><li>有効なリターゲティングネットワーク</li><li>元のユーザー獲得（UA）の流入元</li><li>有効なリターゲティング広告に接触せずにユーザーがアプリをインストールした場合は、オーガニック</li></ul> |

</Accordion>

<div id="inapp-level-blocked-reasons" />

<Accordion title="アプリ内イベント単位のブロック理由">

アプリ内イベントは、次の理由でブロックされる場合があります。

* 元のインストールが偽と判定された場合。
* 設定された検証ルールによる場合。
* AppsFlyerのアルゴリズムが不正を検知した場合。

次の表に、アプリ内イベント単位のブロック理由を示します。

<div id="in-app-level-block-reasons" />

#### アプリ内イベント単位のブロック理由

| ブロック理由 | ブロック理由の詳細 | 説明 |
| --- | --- | --- |
| Inherits from install | Inherits from install | [インストール単位](/docs/protect360-raw-data-reports#install-level-blocked-reasons)または[拒否リストに基づく](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons)理由によって、元のインストールが偽と判定された場合 |
| inapps\_bots | fake\_device\_parameters | AppsFlyerのアルゴリズムが不正を検知 |
| in\_app\_store\_validation | - | アプリ内購入の<Anchor target="_blank" href="/marketers/ja/docs/legacy-receipt-validation-for-in-app-purchases">レシート検証</Anchor>に失敗。 |
| validation\_inapps | validation\_rules | 手動で定義した検証ルールに基づく判定 |

</Accordion>

<div id="retargeting" />

### リターゲティング

Protect360のローデータには、リターゲティングキャンペーンにおける不正なインストールとセッション（それぞれリアトリビューション、リエンゲージメント）が含まれます。データは、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#event">イベント名</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#attribution::e9c68f6c">リターゲティングコンバージョンの種類</Anchor>のフィールドで表示されます。次のいずれかとして表示されます。

* インストール（イベント名には使用されますが、リターゲティングコンバージョンの種類には使用されません）
* リアトリビューション
* リエンゲージメント
* 再インストール

Protect360のリターゲティングローデータは、リアルタイムのブロックと、ポストアトリビューションで検知した不正について、次の方法で利用できます。

<table><thead><tr><th>レポート </th><th>データ出力</th><th>Pull API</th><th>Data Locker</th></tr></thead><tbody><tr><td>インストール</td><td><span>✓\*</span></td><td><span>✓\*</span></td><td>-</td></tr><tr><td>ポストアトリビューションインストール</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="4"> <span>\* リエンゲージメントデータは利用できません。</span><br/> </td></tr></tbody></table>

<div id="hijacked-installs-attribution-correction" />

### ハイジャックされたインストールのアトリビューション修正

ハイジャックされたインストールに対して、AppsFlyerは不正なアドネットワークへのアトリビューションをブロックし、最後の正当なアトリビューションに貢献した流入元に成果を紐づけます。

ハイジャックされたインストールでは、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>フィールドで、有効なアトリビューションに貢献した流入元（メディアソース）を確認してください。これは、本来成果が紐づくべき流入元です。

* **rejected\_reason\_value**には、<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributor[1-3]**</Anchor>または**organic**が入力されます。 **contributor[1-3]** の**メディアソース／パートナー**フィールドで、アトリビューションに貢献した流入元の詳細を確認し、照合してください。
* レポートにアトリビューションに貢献した流入元のフィールドが表示されない場合は、**データ出力**ページから追加できます。

**注意**：ハイジャックされたインストールがリアルタイムでブロックされた場合、修正後のアトリビューションはProtect360だけでなく、AppsFlyerのダッシュボードとレポートにも表示されます。ハイジャックされたインストールがポストアトリビューションで判明した場合、修正後のアトリビューションはProtect360のローデータにのみ表示されます。

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 補足 |
| --- | --- |
| アプリ内イベントレポート | アプリ内イベントレポートには、アトリビューションに貢献した流入元のフィールドは含まれません。アトリビューションに貢献した流入元のフィールドは、インストールレポートでのみ利用できます。 |
| 空欄の値 | プライバシーに関連するローデータの制限により、レポートの一部のフィールドが空欄になる場合があります。例えば、アトリビューションに貢献した流入元のフィールドが該当します。 |

</Accordion>

<div data-zendesk-anchors="about-protect360-raw-data-reports=protect360%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HE7S55TCE60A34T6RCNTCQK8=protect360%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J91EP40Q69KXXF2SR66AM2FQ=%E6%B3%A8%E6%84%8F h_01HE7S55TC4G31R9EANMKCZ7V5=report-types protect360-rawdata-report-types=protect360%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E7%A8%AE%E9%A1%9E h_01HE7S55TCKQYTXPV6J54SHM0D=protect360%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E7%A8%AE%E9%A1%9E h_01HE7S55TC4F5S243BSGN74RDK=postattribution-reports using-postattribution-reports=%E3%83%9D%E3%82%B9%E3%83%88%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%88%A9%E7%94%A8%E6%96%B9%E6%B3%95 h_01HE7S55TC7KCF75KFXHCE3K2K=%E3%83%9D%E3%82%B9%E3%83%88%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%88%A9%E7%94%A8%E6%96%B9%E6%B3%95 h_01HE7S55TCR8BKZ0PQ5B14X3X4=%E4%BE%8B h_01HE7S55TC95YC1BJJ0ZERCQ14=raw-data-availability-by-tool-type protect360-rawdata-availability-by-tool-type=%E5%8F%96%E5%BE%97%E3%83%84%E3%83%BC%E3%83%AB%E5%88%A5%E3%81%AEprotect360%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E5%8F%AF%E5%90%A6 h_01HE7S55TCH4CES29C5J3QXQK4=%E5%8F%96%E5%BE%97%E3%83%84%E3%83%BC%E3%83%AB%E5%88%A5%E3%81%AEprotect360%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%A9%E7%94%A8%E5%8F%AF%E5%90%A6 getting-raw-data-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%8F%96%E5%BE%97 h_01HE7S55TC3MRT6E9QV0J0X6FC=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%8F%96%E5%BE%97 h_01HE7S55TCBVFQ1DH06G53BNEN=download h_01HE7S55TCMT81J4SWBFQFYV2C=pull-api pull-api-raw-data-report-parameters=pull-api%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HE7S55TCRRD95D0QPCXBRF8T=pull-api%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF h_01HE7S55TCMAY86J1HKYB0APZ6=data-locker protect360-report-structure=protect360%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E6%A7%8B%E9%80%A0 h_01HE7S55TCS91ZC9V3K0VDSVXK=protect360%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E6%A7%8B%E9%80%A0 blocked-reasons=%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1 h_01HE7S55TC1ZEDD5ABD21FCPY2=%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1 h_01HE7S55TDMDSVQCVSV5YS3CZN=click-level-blocked-reasons h_01HE7S55TD754T07FWHFK5P71K=install-level-blocked-reasons install-level-fake-install-block-reasons=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E5%8D%98%E4%BD%8D%E5%81%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1%E3%81%AE%E8%A9%B3%E7%B4%B0 h_01HE7S55TDHTE5P47N1CCREGZX=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E5%8D%98%E4%BD%8D%E5%81%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1%E3%81%AE%E8%A9%B3%E7%B4%B0 install-level-attribution-hijacking-block-reasons=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E5%8D%98%E4%BD%8D%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1%E3%81%AE%E8%A9%B3%E7%B4%B0 h_01HE7S55TDFA6WGAHE80ECV8CA=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E5%8D%98%E4%BD%8D%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1%E3%81%AE%E8%A9%B3%E7%B4%B0 h_01HE7S55TDCHG0CVJA3JRSAW3G=cluster-level-blocked-reasons cluster-level-fake-install-block-reasons=%E4%B8%8D%E6%AD%A3%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E3%81%AE%E3%81%BE%E3%81%A8%E3%81%BE%E3%82%8A%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E5%88%A4%E5%AE%9A%E5%81%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1 h_01HE7S55TDBES0BY0FF3WKSSVG=%E4%B8%8D%E6%AD%A3%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E3%81%AE%E3%81%BE%E3%81%A8%E3%81%BE%E3%82%8A%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E5%88%A4%E5%AE%9A%E5%81%BD%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1 cluster-level-attribution-hijacking-block-reasons=%E4%B8%8D%E6%AD%A3%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E3%81%AE%E3%81%BE%E3%81%A8%E3%81%BE%E3%82%8A%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E5%88%A4%E5%AE%9A%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1 h_01HE7S55TD3M45TH4PY2W805W7=%E4%B8%8D%E6%AD%A3%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3%E3%81%AE%E3%81%BE%E3%81%A8%E3%81%BE%E3%82%8A%E3%81%AB%E5%9F%BA%E3%81%A5%E3%81%8F%E5%88%A4%E5%AE%9A%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1 h_01HE7S55TDGB05PEZX8KS3J3QJ=inapp-level-blocked-reasons inapp-level-block-reasons=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E5%8D%98%E4%BD%8D%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1 h_01HE7S55TD661EHCV50S9BW5MS=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E5%8D%98%E4%BD%8D%E3%81%AE%E3%83%96%E3%83%AD%E3%83%83%E3%82%AF%E7%90%86%E7%94%B1 retargeting=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 h_01HE7S55TDSYDC8BWZ8D8DF9JE=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 hijacked-installs-attribution-correction=%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%95%E3%82%8C%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E4%BF%AE%E6%AD%A3 h_01HE7S55TD8SDCQJCCYQC0MNES=%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%95%E3%82%8C%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E4%BF%AE%E6%AD%A3 h_01J91E55BXQ4E01A9R3EB33WYF=traits-and-limitations" />

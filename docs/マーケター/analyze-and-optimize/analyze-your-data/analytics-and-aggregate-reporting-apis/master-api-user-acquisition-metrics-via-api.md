---
title: Master API — APIによるユーザー獲得メトリック
metadata:
  keywords:
    - Master API
    - Customizable
    - Aggregated Data
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-09-27T15:10:38Z'
  edited_at: '2026-10-14T09:39:21Z'
  id: 213223166
  locale: ja
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ja/articles/213223166
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** 選択された LTV、アクティビティ、リテンション、コホート、および Protect360 キャンペーンのパフォーマンス KPI を API別に、CSVまたは JSON形式で指定します。データ対象のアプリは1つ以上選択可能です。

## Master API — APIによるユーザー獲得メトリック

マスターAPI：

* 選択した LTV、アクティビティ、リテンション、コホート、Protect360 キャンペーンのパフォーマンス KPI を取得できます。使用可能な KPI は、概要、アクティビティ、リテンション、コホート、および Protect360 ダッシュボードにある KPI と同等の KPI です。
* デイリーで計算処理されます（リアルタイムではありません）。更新されたデータは、アプリ固有のタイムゾーンに応じて、24 ~ 48 時間以内に利用できます。
* AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/pivot-table-user-metrics">ピボットテーブル</Anchor> で構築されるインフラストラクチャです。

マスターAPI を使用するには、表示するデータを定義します ( <Anchor target="_blank" href="/marketers/ja/docs/pull-api-aggregate-data">Pull API</Anchor>の実装と同様)。結果は CSV ファイルまたは JSON ファイルとして返されます。

**Master APIを使用する**：

1. ![](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) alt<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">AppsFlyerAdmin\_us-en.png</Anchor> APIトークンを取得します。管理者はトークンをダッシュボードで取得する必要があります。
2. 認証ヘッダーで使用するためにAPIトークンをデベロッパーに渡します。
3. 次のセクションで説明するように、APIコールを行うときに入力するパラメーターを開発者へ渡してください。パラメーターは、レポートが何に焦点を当て、どのように編成されるかを決定し、レポートの時間枠を定義します。
4. AppsFlyer公式デベロッパーハブの <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-9">Master APIの手順</Anchor> に従うように開発者に伝えます。
5.
   <div id="api-parameters" />

   <Accordion title="API パラメータ">

   | パラメータ | 値 | 必須 |
   | --- | --- | --- |
   | app\_id | * AppsFlyerに表示されるアプリ識別子<br />* AppsFlyerに表示されているとおりにアプリIDを挿入します。<br />* iOSアプリの先頭に **id** を付けます。<br />* **すべてのアプリ ID** を使用してすべてのアプリを照会する | はい |
   | 開始 | LTVアトリビューション日付期間の下限<br /><br />* 形式：String yyyy-mm-dd<br />* 例： `from: 2020-01-02` | はい |
   | 終了 | LTVアトリビューション期間の上限<br /><br />* 範囲内の日数：1～31日1-180日<br />* 形式： yyyy-mm-dd | はい |
   | [グループ化](/docs/master-api-user-acquisition-metrics-via-api#groupings) | パラメーターでグループ化し、コンマで区切ります。使用可能なリストについては、グループ化の表を参照してください。<br /><br />例：`groupings=pid,geo` | はい |
   | [KPI](/docs/master-api-user-acquisition-metrics-via-api#kpis) | 含めるKPIのリスト（それぞれをコンマで区切って指定）KPIリストについては、以下の KPI表を参照してください。<br /><br />例： `kpis=installs,clicks, impressions,sessions,retention_day_7` | はい |
   | [フィルタ](/docs/master-api-user-acquisition-metrics-via-api#filters-optional) | データは、1つ以上のフィルターオプションを使用してフィルター処理できます。 | いいえ |
   | [通貨設定](/docs/master-api-user-acquisition-metrics-via-api#localization) | アプリ固有の通貨を設定するには currency=preferred とセットしてください。 | いいえ |
   | [タイムゾーン](/docs/master-api-user-acquisition-metrics-via-api#localization) | アプリ固有のタイムゾーンを使用してデータを返すには、timezone=preferred を設定します。   参照：[ローカリゼーションルール](/docs/master-api-user-acquisition-metrics-via-api#localization) | いいえ |
   | 形式 | デフォルト設定で、レスポンスデータはすべてCSVファイル形式となります。 | いいえ |

   </Accordion>

   <div id="groupings" />

   <Accordion title="グループ化">

   これらのディメンションを使うことで、データをグループで表示し、情報をより簡単に、より正確に精査することが可能になります。詳細は<Anchor target="_blank" href="/marketers/ja/docs/raw-data-field-dictionary">こちら</Anchor>をご覧ください。

   <table><thead><tr><th>グループ化<br/>API名</th><th>表示名でグループ化</th><th>LTV KPI</th><th>リテンションKPI</th><th>アクティビティKPI</th><th>Protect360</th><th>コホート</th></tr></thead><tbody><tr><td>app_id</td><td>App ID</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td></tr><tr><td>pid</td><td>Media source</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td></tr><tr><td>af_prt</td><td>代理店</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td><td>いいえ</td></tr><tr><td>c</td><td>Campaign</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td></tr><tr><td>af_adset</td><td>Adset</td><td>はい</td><td>はい</td><td>はい</td><td>いいえ</td><td>いいえ</td></tr><tr><td>af_ad</td><td>Ad</td><td>はい</td><td>はい</td><td>はい</td><td>いいえ</td><td>いいえ</td></tr><tr><td>af_channel</td><td>Channel</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td><td>いいえ</td></tr><tr><td>af_siteid</td><td>パブリッシャーID</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td></tr><tr><td>af_keywords</td><td>Keywords</td><td>はい</td><td>はい</td><td>はい</td><td>いいえ</td><td>いいえ</td></tr><tr><td>is_primary</td><td>プライマリアトリビューション</td><td>はい</td><td>いいえ</td><td>はい</td><td>はい</td><td>いいえ</td></tr><tr><td>af_c_id</td><td>Campaign ID</td><td>はい</td><td>いいえ</td><td>はい</td><td>はい</td><td>いいえ</td></tr><tr><td>af_adset_id</td><td>Adset ID</td><td>はい</td><td>いいえ</td><td>はい</td><td>いいえ</td><td>いいえ</td></tr><tr><td>af_ad_id</td><td>Ad ID</td><td>はい</td><td>いいえ</td><td>はい</td><td>いいえ</td><td>いいえ</td></tr><tr><td>install_time</td><td>インストール時刻</td><td>はい</td><td>はい</td><td>はい\*</td><td>はい</td><td>はい</td></tr><tr><td>attributed_touch_type</td><td>タッチタイプ</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td><td>いいえ</td></tr><tr><td>geo</td><td>地理</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td><td>はい</td></tr><tr><td colspan="7">\* アクティビティKPIのコンテキストでは、インストール時間をイベント時間と見なします。 </td></tr></tbody></table>

   </Accordion>

   <div id="kpis" />

   <Accordion title="KPI">

   KPIはアプリの状況を確認するための指標となります。

   <div id="ltv" />

   <Accordion title="LTV（顧客生涯価値）">

   生涯価値 - インストールされた日から本日までのイベント集計値

   | KPI API名 | 説明 |
   | --- | --- |
   | Impressions | 選択した期間におけるインプレッション数 |
   | clicks | 選択した期間におけるクリック数 |
   | installs | 選択した期間におけるインストール数 |
   | cr | コンバージョン率 |
   | sessions | 選択した期間にインストールしたユーザーのセッション数 |
   | ロイヤルユーザー | 選択した期間にインストールしたロイヤルユーザー数 |
   | loyal\_users\_rate | ロイヤルユーザー率（ロイヤルユーザー数 ÷ インストール数） |
   | cost | 選択した期間の総コスト*制限事項を参照 |
   | revenue | 選択した期間にインストールしたユーザーの生涯収益 |
   | ROI | 選択した期間における投資対効果 |
   | arpu\_ltv | 選択した期間にインストールしたユーザーの１ユーザーあたりの平均収益 |
   | average\_ecpi | 特定の期間におけるeCPIコストとインストールがコールに含まれている場合にのみ使用できます。 |
   | uninstalls | 特定の期間にアンイストールしたユーザー |
   | uninstalls\_rate | アンインストール率 |
   | event\_counter\_[event\_name] | イベントの発生数 |
   | unique\_users\_[event\_name] | イベントが発生したユニークユーザー数 |
   | sales\_in\_usd\_[event\_name] | レポートされたイベントの収益 |

   </Accordion>

   <div id="retention" />

   <Accordion title="リテンション">

   リテンションとは、アクティブなユーザー数を把握する指標です。

   **注記：**

   * 最大リテンション日数はインストール後 30日で、0日はインストール日です。つまり、値 [x] は 30 を超えることはできません。
   * retention\_day\_1 をリクエストすると、その日のデータが利用可能になる前に、返されるメトリックは前日にインストールしたユーザーに関連しています。たとえば、1月2日に、1月1日にインストールしたユーザーの retention\_day\_1 をリクエストします。メトリックはまだ使用できないため、返されるメトリックは 12月31日にインストールしたユーザーに関連しています。

   | KPI | 説明 |
   | --- | --- |
   | retention\_day\_[x] | X日後のアクティブユーザー数 |
   | retention\_rate\_day\_[x] | インストールしたユーザーのうち、X日後のアクティブユーザー数 |

   </Accordion>

   <div id="activity" />

   <Accordion title="アクティビティ">

   選択した期間におけるアプリ内アクティビティ　**注：**

   | KPI | 説明 |
   | --- | --- |
   | activity\_average\_dau | 選択した期間における平均DAU |
   | activity\_average\_mau | 選択した期間における平均MAU（1MAU日：過去30日におけるユニークユーザー数） |
   | activity\_average\_dau\_mau\_rate | 平均DAU/MAU率 |
   | activity\_average\_arpdau | 1DAUあたりの平均収益：その1日のすべてのユニークユーザーあたりの平均収益 |
   | activity\_sessions | 選択した期間におけるセッション数 |
   | activity\_revenue | 選択した期間における収益 |
   | activity\_event\_counter\_[event\_name] | 選択した期間におけるユーザーによるイベント数 |
   | activity\_sales\_in\_usd\_[event\_name] | 選択した期間における収益イベントからの収益 |
   | activity\_average\_unique\_users\_[event\_name] | 選択した期間における特定のイベントを実施した平均ユニークユーザー数 |

   </Accordion>

   <div id="cohort" />

   <Accordion title="コホート">

   AppsFlyerのコホートレポートでは、異なる期間の複数のコホートレポートを異なる指標を使って比較することが可能です。

   **注記：**

   * 1ユーザーあたりの収益は 9 ÷ 100000=0.00009 です。値は0と表示されます。
   * コホート日数：コホート日の最大数は、インストール後 90日で、0日がインストール日です。コホートの日の値 [x] は、1 ~ 90 の範囲である必要があります。  注： cohort\_day\_0 は、コホートダッシュボードでサポートされていますが、Mater API ではサポートされていません。
   * Master API V2

   **セッション**

   | KPI | 説明 |
   | --- | --- |
   | cohort\_day\_[x]\_total\_sessions\_per\_user | コホート X日：X日目までのユーザー毎の累積セッション数（X日目を含む） |
   | cohort\_day\_[x]\_sessions\_per\_user | コホート X日：X日目のみのセッション数 |
   | cohort\_[x]\_days\_total\_sessions\_per\_user | X日目までのセッション数を日別で取得できます。 |

   **収益**

   | KPI | 説明 |
   | --- | --- |
   | cohort\_day\_[x]\_total\_revenue\_per\_user | コホートX日： ユーザーあたりの累積収益 (X日目を含む) |
   | cohort\_day\_[x]\_revenue\_per\_user | コホートX日：X日目のみのARPU |
   | cohort\_[x]\_days\_total\_revenue\_per\_user | 指定した KPI Cohort\_day\_1\_total\_revenue\_per\_user を Cohort\_day\_x\_total\_revenue\_per\_userに置き換えます。 |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_revenue\_per\_user | コホートの Day Xの特定のアプリ内イベントに応じたユーザーあたりの累積収益 |
   | cohort\_day\_[x]\_event\_[eventname]\_revenue\_per\_user | コホートの Day Xの特定のアプリ内イベントに応じたユーザーあたりの収益 |

   **イベント**

   | KPI | 説明 |
   | --- | --- |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_per\_user | コホートX日：X日目までのユーザーあたりの累積イベント数 (X日目を含む) |
   | cohort\_day\_[x]\_event\_[eventname]\_per\_user | コホートX日：X日目のみのイベント数 |
   | cohort\_[x]\_days\_total\_event\_[eventname]\_per\_user | 指定したKPIイベントを Cohort\_day\_x\_total\_events\_per\_user に置き換えます。 |

   </Accordion>

   <div id="protect360" />

   <Accordion title="Protect360">

   **Protect360 KPI**

   | 説明 | KPI |
   | --- | --- |
   | **インストール** |  |
   | 合計 | protect360\_total\_installs |
   | ブロックされます。 | blocked\_installs |
   | ブロック率 | blocked\_installs\_rate |
   | ポストアトリビューション不正 | post\_attribution\_installs |
   | ポストアトリビューション不正率 | post\_attribution\_installs\_rate |
   | 不正インストールの合計 | total\_fraudulent\_installs |
   | 不正インストール | fraudulent\_installs\_rate |
   | **フェイクインストール** |  |
   | リアルタイムブロック | real\_time\_fake\_installs |
   | ポストアトリビューション不正 | post\_attribution\_fake\_installs |
   | **ハイジャックされたインストール** |  |
   | リアルタイムブロック | real\_time\_hijacked\_installs |
   | ポストアトリビューション不正 | post\_attribution\_installs\_hijacked\_installs |
   | **検証ルール** |  |
   | ブロック済みインストール | validation\_rules\_blocked\_installs |
   | ブロック済みアトリビューション | validation\_rules\_blocked\_attribution |
   | **フェイクインストール ブロックの内訳** |  |
   | ブロック済みサイトIDブラックリスト | blocked\_installs\_siteid\_blacklist |
   | ポストアトリビューションサイトIDブラックリスト | post\_attribution\_installs\_siteid\_blacklist |
   | ブロック済みボット | blocked\_installs\_bots |
   | ポストアトリビューションボット | post\_attribution\_installs\_bots |
   | ブロック済み異常行動 | blocked\_installs\_behavioral\_anomalies |
   | ポストアトリビューション行動異常 | post\_attribution\_installs\_behavioral\_anomalies |
   | バリデーションルールによりブロックしたインストール数 | blocked\_installs\_install\_validation |
   | **ハイジャックされたインストールのブロック内訳** |  |
   | ブロック済みインストールハイジャック数 | blocked\_installs\_install\_hijacking |
   | ポストアトリビューション インストールハイジャック | post\_attribution\_installs\_installs\_hijacking |
   | ブロック済みCTIT異常の数 | blocked\_installs\_ctit\_anomalies |
   | ポストアトリビューション CTIT異常 | post\_attribution\_installs\_ctit\_anomalies |
   | ブロック済みクリック洪水 | blocked\_installs\_click\_flood |
   | ポストアトリビューションクリック洪水 | post\_attribution\_installs\_click\_flood |
   | **クリック** |  |
   | 合計 | protect360\_total\_clicks |
   | ブロックされます。 | blocked\_clicks |
   | % | blocked\_clicks\_rate |
   | **アプリ内イベント** |  |
   | 合計 | protect360\_total\_in\_apps |
   | ブロックされます。 | blocked\_in-app-events |
   | % | blocked\_in-app-events\_rate |
   | デバイスファームの指標 - 新規端末 |  |
   | インストール | install\_fraud\_new\_devices\_total |
   | インストール率 | install\_fraud\_new\_devices\_total\_installs\_rate |
   | ロイヤルユーザー率 % | install\_fraud\_new\_devices\_total\_loyal\_user\_rate |
   | **デバイスファームの指標 - LAT端末** |  |
   | インストール | install\_fraud\_lat\_devices\_total |
   | インストール率 | install\_fraud\_lat\_devices\_total\_installs\_rate |
   | ロイヤルユーザー率 % | install\_fraud\_lat\_devices\_total\_loyal\_user\_rate |
   | **クリック洪水の指標** |  |
   | コンバージョン率 | conversion\_rate |
   | **クリック洪水の指標 - CTIT** |  |
   | 60分以上 | click\_flood\_over\_1\_hour\_rate |
   | 5時間以上 | click\_flood\_over\_5\_hours\_rate |

   </Accordion>

   #### 算出KPI

   Master APIレポートでは、上記のKPIに加え、算出KPIを追加することが可能です。これにより、独自の計算レポートをMaster API レポートに含めることができます。

   KPI計算式の中には、いくつでもKPIを挿入いただいても構いません。各計算 KPI オブジェクトには、キーと値が含まれます。キーは KPI に付ける名前で、値は KPI の式です。

   標準の算術演算子がサポートされています：％2bとしてエンコードされた加算（+）、減算（-）、乗算（*）、％2fとしてエンコードされた除算（/）。

   計算式を挿入するKPIは、小目名は**必ず** "calculated\_kpi\_" から始め、そのあとに有用な文字列で続けてください。例："calculated\_kpi\_purchaserate"

   > 📄 **例**
   >
   > 最初の３日間の合算リテンション
   >
   > ```http
   > kpis=installs,loyal_users_rate&calculated_kpi_3days_retention=
   > retention_day_1%2Bretention_day_2%2Bretention_day_3
   > ```
   >
   > インプレッション毎の平均収益
   >
   > ```http
   > kpis=installs&calculated_kpi_rev_per_impression=revenue%2Fimpression
   > ```
   >
   > コホート7日目のROI
   >
   > ```http
   > kpis=installs,roi,arpu_ltv,cost,revenue&calculated_kpi_roi_day_7=
   > (cohort_day_7_total_revenue_per_user-average_ecpi)%2Faverage_ecpi
   > ```

   </Accordion>

   <div id="filters-optional" />

   <Accordion title="フィルター（オプション）">

   | パラメータ | 説明 | 例 | 必須? |
   | --- | --- | --- | --- |
   | pid | * メディアソースの絞り込みに利用します。<br />* カンマ区切りで複数指定可能です。 | pid=organic,applovin\_int | いいえ |
   | c | * キャンペーン名のフィルターに使用されます。<br />* カンマ区切りで複数指定可能です。 | c=my\_sample\_campaign | いいえ |
   | af\_prt | * 代理店名のフィルターに使用されます。<br />* カンマ区切りで複数指定可能です。 | af\_prt=moburst | いいえ |
   | af\_channel | * チャネル名のフィルターに使用されます。<br />* カンマ区切りで複数指定可能です。 | af\_channel=Instagram | いいえ |
   | af\_siteid | * パブリッシャーIDのフィルターに使用されます。<br />* カンマ区切りで複数指定可能です。 | af\_siteid=12345678 | いいえ |
   | geo | * 国ごとのフィルターに使用されます。<br />* カンマ区切りで複数指定可能です。 | geo=US,DE | いいえ |

   </Accordion>

   <div id="localization" />

   <Accordion title="ローカライゼーション">

   現地通貨とアプリ固有のタイムゾーンは、 <Anchor target="_blank" href="/marketers/ja/docs/app-settings">アプリ設定</Anchor>ページから設定します。Master APIのデータは、システムの既定の通貨とタイムゾーン、またはアプリ固有のタイムゾーンと通貨を使用してデータを抽出できます。

   以下が適用されます：

   * アプリ固有のタイムゾーン/通貨の使用は、すべてのアプリが同じタイムゾーン/通貨を持つ場合にのみサポートされます。それ以外の場合は、UTC と USD が使用されます。タイムゾーンと通貨は別々です。つまり、すべてのアプリの通貨が同じでタイムゾーンが同じでない場合は、アプリ固有の通貨を使用できますが、アプリ固有のタイムゾーンは使用できません。
   * リクエストされた時間範囲内にダッシュボードでリクエストされたタイムゾーンが変更された場合、生成されたレポートには、最新のタイムゾーンの変更から始まる値が含まれます。

   次のパラメーターを使用して、アプリ固有の設定を選択します。　**注：** 注意：preferredパラメーターを使用しない場合は、通貨の場合は USD、タイムゾーンの場合は UTCという既定の設定が適用されます。

   | パラメータ | 説明 | 例 | 必須? |
   | --- | --- | --- | --- |
   | currency | 金額はアプリ設定画面で設定された通貨です。 | currency=preferred | いいえ |
   | timezone | 使用されるタイムゾーンは、アプリ設定画面で設定されたタイムゾーンに従います。 | timezone=preferred | いいえ |

   </Accordion>

## 追加情報

<div id="limitations" />

<Accordion title="特性と制限">

| 特性 | 備考 |
| --- | --- |
| コストデータ | <ul><li>さまざまなコストディメンションが利用可能であることから、広告セット、広告、地域、チャンネル、サイトIDは <Anchor target="_blank" href="/marketers/ja/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">広告ネットワークによって異なります</Anchor>。</li><li>eCPIを取得するには：コストデータが利用可能な場合は、インストールとコストの両方をコールに含めます。</li><li>基本的に、オウンドメディアを含むAppsFlyerのURLを使う全てのメディアソースで、リクエストするディメンションに関わらずコストデータが提供可能です。ただし、URLにコストパラメータが存在する必要があります。独自のAPIをもつセルフレポーティングネットワークは一部のディメンションのコストデータのみに対応しています。 たとえば、 <Anchor target="_blank" href="/marketers/ja/docs/meta-ads-faq#what-are-the-limitations-of-facebook-cost-data-in-master-api">Meta広告</Anchor> では、同じコールでの地域とチャネルによるグループ化はサポートされていません。これらのいずれかによる個別のグループ化がサポートされています。</li><li>コストデータはあるが、最近のインストールデータがないキャンペーン（約7日間）はマスターAPIではご利用いただけません。</li></ul> |
| グループ化 | 特定のグルーピングはLTV、アクティビティ、リテンションのKPIでのみ利用可能です。特定のKPIが利用不可の場合、”N/A” とAPIから返答されます。例えば、retention\_rate\_day\_7 を af\_channel でグループするようにリクエストをすると、“N/A” と返します。 |
| レポートあたりの最大行数 | 200K |
| 複数のイベント名 | Master API は現在、スラッシュ `/`// を含むイベント名をサポートしていません。この制限を克服するには、イベント名に含まれる / を避けます。 |
| 処理時間 | 複数のアプリを選択すると、処理時間が長くなり、応答に時間がかかる場合があります。 |
| データ期間 | 時間枠の粒度はデイリー（各日）です。 |
| 代理店 | Master APIではご利用いただけません |
| アドネットワーク | Master APIではご利用いただけません |
| 過去データ | <ul><li>LTVデータ5年</li><li>2年</li><li>アクティビティデータ：3年</li></ul> |
| リターゲティング | <ul><li>いいえ：</li></ul> |

</Accordion>

<div data-zendesk-anchors="master-api%E2%80%94user-acquisition-metrics-via-api=master-api--api%E3%81%AB%E3%82%88%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%83%A1%E3%83%88%E3%83%AA%E3%83%83%E3%82%AF h_01JJVMXKACJ2V4YZFGYXVB8FQF=master-api--api%E3%81%AB%E3%82%88%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%8D%B2%E5%BE%97%E3%83%A1%E3%83%88%E3%83%AA%E3%83%83%E3%82%AF h_01JJVMXKACZDXPQG4271HFYWCE=api-parameters h_01JJVMXKAEXMKQQRT0RT6N8P74=groupings h_01JJVMXKAEHM0871GBQHZENRXA=kpis h_01JK2ZEH32Y92Y553540XDYZFA=ltv h_01JK2ZEH32A08EEDZEWFSX3ZFS=retention h_01JK2ZEH3219694E4PFPZ8ZXZF=activity h_01JK2ZEH32NCWZWKTDS0J6DFS2=cohort h_01JK2ZEH32Q7B6RCQYXNHM8KGK=protect360 calculated-kpis=%E7%AE%97%E5%87%BAkpi h_01JJVMXKAFW1TEE35GK9B20TRP=%E7%AE%97%E5%87%BAkpi h_01JJVMXKAFZDPNXKAZCBQ27DBD=%E4%BE%8B h_01JJVMXKAFWA4D47MH7VSXKN14=filters-optional h_01JJVMXKAFSBXJ9EJJ16BF8H7Q=localization additional-information=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01JJVMXKAFFW2G3N7188DHYCB8=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1 h_01JJVMXKAF25YX092NE9DV9862=limitations" />

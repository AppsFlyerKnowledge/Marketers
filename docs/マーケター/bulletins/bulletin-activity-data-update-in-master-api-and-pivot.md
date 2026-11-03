---
title: お知らせ：Master APIおよびPivotにおけるアクティビティデータの更新
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-17T07:26:26Z'
  edited_at: '2026-10-14T09:22:20Z'
  id: 49896622875537
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/49896622875537
---
| セクション | 詳細 |
| --- | --- |
| 更新情報 | Master APIとPivotでは、マイダッシュボード、AppsFlyer MCPおよびAI Assistant、Agentsですでに使用されているものと同じアクティビティデータへの移行を進めています。これにより、どの機能で確認してもアクティビティ指標の値が一貫するようになります。<br /><br />この変更に伴い、アクティビティデータのフィルタリングやグループ化に使用される一部の内部値が変更されます。詳細については、以下をご確認ください。<br /><br />ほとんどのお客様において、対応は不要です。 |
| 適用日 | 2026年9月14日 |
| 対象となるお客様 | <ul><li>以下のアクティビティ指標を分析している、すべてのMaster APIおよびPivotのお客様が対象です：`activity_average_dau`、`activity_average_dau_mau_rate`、`activity_average_arpdau`、`activity_sessions`、`activity_revenue`、`activity_event_counter_[event_name]`、`activity_sales_in_usd_[event_name]`、`activity_average_unique_users_[event_name]`</li></ul>注意：`activity_average_mau`は今回の変更の影響を受けません。<ul><li>Cohort、LTV、Retention、およびその他のデータタイプに変更はありません。これらのデータとアクティビティデータを同じレポート内で組み合わせて使用している場合、他のデータタイプにも同様の変更が適用されるまでは、一部の値、特にメディアソース／pidの値が一致しない場合があります。</li></ul> |
| 必要な対応 | この変更は自動的に適用されるため、ほとんどのお客様において対応は不要です。<br /><br />ただし、以下に記載されている値を使用してアクティビティレポートのフィルタリングまたはグループ化を行っている場合は、2026年9月14日以降に該当するフィルター設定をご確認ください。従来の値を使用した場合、これまでとは異なる結果が返される、または結果が返されなくなる可能性があります。 |
| ご確認いただきたいポイント | 以下の変更点にご注意ください。<br /><br />* **アップデート後、指標の値に若干の差異が生じる場合があります。** アクティビティデータは新しいデータパイプラインへ移行するため、メトリクスの値がわずかに変動する可能性があります。ユニークユーザー数、DAU、および関連する指標では、最大3%程度の差異が生じる場合があります。これはデータのエラーではなく、データパイプラインの変更に伴う想定内の差異です。<br />* `attributed_touch_type`のグループ化では、**「Pre-install」と「preload」が「download」に統合**されます。 Master APIの`attributed_touch_type`を「pre-install」または「preload」でフィルタリングまたはグループ化しても、今後はそれぞれ個別の結果として返されません。該当するトラフィックは「download」に含まれるようになります。<br />* **null値は空文字列に置き換えられます。** これには、オーガニック／Noneのメディアソースも含まれます。Master APIでは`pid`、PivotではMedia sourceに該当し、今後は空文字列として返されます。<br />* **2つのメディアソース名が変更されます：**`facebook`は`Facebook Ads`に変更され、`twitter`および`twitter_int`は`Twitter`に変更されます。その他のメディアソース名に変更はありません。<br />* **一部の文字はアンダースコア（ \_ ）に置き換えられます：** 制御文字、および`;`、 `{`、 `}`、 `$`、 `<`、 `>`、 `'`、 `\`の各文字は、すべてアンダースコア（ \_ ）に置き換えられます。<br />* **新しいフィールド切り捨て制限が適用されます：**<br />  * `ad_id` （250文字）<br />  * `ad_name` （256文字）<br />  * `event_name` （100文字）<br />  * `app_version` （64文字）<br />  * `agency` （32文字）<br />  * `keywords` （90文字）<br />  * `install_app_store` （50文字）<br />  * `os_version` （20文字）<br /><br />今回の移行により、アクティビティデータは、よりモダンで拡張性の高いインフラストラクチャへ移行します。これにより、信頼性とパフォーマンスが向上するとともに、今後のプロダクト改善を支える基盤が強化されます。 |
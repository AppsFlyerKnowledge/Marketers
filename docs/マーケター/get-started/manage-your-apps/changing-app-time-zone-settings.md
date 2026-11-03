---
title: アプリのタイムゾーン設定の変更
metadata:
  keywords:
    - Time Zone
    - Existing Apps
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2017-01-12T15:33:00Z'
  edited_at: '2026-10-14T09:37:37Z'
  id: 115000306786
  locale: ja
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ja/articles/115000306786
---
> **概要：** 概要：アプリ毎のタイムゾーンを設定または変更することで、アプリのデータをお客様や広告パートナーのタイムゾーンに合った形で表示することが可能になります。このページでは、タイムゾーンの変更がAppsFlyerのプラットフォーム内のデータの計測に与える影響についても正しく理解してください。

## なぜタイムゾーンを変更するのか

新しいアプリを追加した場合、デフォルトのタイムゾーンはUTC(UTC + 0)に設定されます。アプリのタイムゾーンが変更されると、プラットフォーム上でのデータの表示のされ方に影響します。

* **シナリオ：** シナリオ：あなたは、UTCではないタイムゾーンで働いています。そしてアプリのデータを、自分のタイムゾーン、もしくはFacebookやGoogleといった他のパートナーで選択しているタイムゾーンに合わせたいと思っています。
* **ゴール：** ゴール：AppsFlyerと他のパートナーにおけるデータ比較をより容易にすること
* **ソリューション：** 解決策：AppsFlyerのプラットフォーム上のタイムゾーン設定を、利用している他のパートナーの設定に合わせましょう。サマータイムはデフォルトでサポートしています。(設定変更は不可)

**代理店とアドネットワークについて**：

* アドネットワーク：広告主が設定したタイムゾーンに関係なく、常にUTCでデータが表示されます。

## タイムゾーンの変更方法

アドミン（管理者）ユーザーがタイムゾーンを変更できます。

**アプリのタイムゾーンを変更するには：**

1. AppsFlyer管理画面左メニュー **設定** > **アプリ設定へ移動します。**
2. **ローカリゼーション>** **タイムゾーン**にて、**UTC**を選択してください。
3. **設定の保存**をクリックして、まずは48時間待ってください。
4. **設定** > **アプリ設定**へ進んでください。
5. **ローカリゼーション**> **タイムゾーン** にて、任意のタイムゾーン(都市/国単位)を選択してください。
6. [**設定を保存**] をクリックします。

> 📄 **例**
>
> * 10月25日の00:00 (UTC)に、その変更内容が有効になります。

タイムゾーンを変更した後は：

* 各データの表示に適用されるタイムゾーンは、以下の表に記載されているように、レポート期間と方法によって異なります。
* 集計レポートでは、タイムゾーンを変更した当日とその翌日は以下のように一部データが正しく表示されないので注意してください。

#### 集計データ

<table><tbody><tr><th> </th><th colspan="3"><p>レポートの指定期間</p></th></tr><tr><th>レポートの利用機能 </th><th>開始日と終了日が設定変更日より<span>前</span> </th><th><p>開始日と終了日が設定変更日より<span>後</span> </p></th><th>開示日と終了日の間に設定変更日がある場合</th></tr><tr><td>オーバービュー管理画面</td><td>過去のタイムゾーン設定</td><td>現在のタイムゾーン設定</td><td><p>分割されます：</p><ul><li>変更前：UTC</li><li>変更後のデータ：現在のタイムゾーン設定</li></ul></td></tr><tr><td>イベントとカスタムダッシュボード</td><td>UTC</td><td>現在のタイムゾーン設定</td><td><p>分割されます：</p><ul><li>変更前：UTC</li><li>変更後のデータ：現在のタイムゾーン設定</li></ul></td></tr><tr><td><p>アクティビティ管理画面</p></td><td>過去のタイムゾーン設定</td><td>現在のタイムゾーン設定</td><td>UTC</td></tr><tr><td><p>コホート、リテンション、Pivot</p></td><td>UTC</td><td>現在のタイムゾーン設定 (1)</td><td>UTC</td></tr><tr><td>Master API</td><td colspan="3"><ul><li>デフォルトUTC </li><li>任意 オプション： <a href="./pull-api-aggregate-data" target="_blank">データ取得時のタイムゾーンの選択</a>  </li></ul></td></tr><tr><td colspan="4">注：<br/>注意：(1)すべてのアプリで、対象のレポート期間においてアプリ毎のタイムゾーン設定が同じタイムゾーンに設定されている必要があります。そうでない場合、タイムゾーンはUTCが適用されます。</td></tr></tbody></table>

#### ローデータレポート

<table><tbody><tr><th> </th><th colspan="3">レポートの指定期間</th></tr><tr><th>レポートの利用機能 </th><th>開始日と終了日が設定変更日より<span>前</span> </th><th>開始日と終了日が設定変更日より<span>後</span> </th><th>開示日と終了日の間に設定変更日がある場合</th></tr><tr><td>データエクスポート / ローデータ</td><td>現在のタイムゾーン設定</td><td>現在のタイムゾーン設定</td><td>現在のタイムゾーン設定</td></tr><tr><td>Push API</td><td colspan="3"><p>UTCと、イベント発生時点で選択されているアプリ毎のタイムゾーンを使ったフィールドに分割されます。</p></td></tr><tr><td>Pull API</td><td colspan="3"><ul><li>デフォルトUTC </li><li>任意オプション：<a href="./pull-api-aggregate-data" target="_blank">データ取得時のタイムゾーンの選択</a> </li></ul></td></tr><tr><td>Data Locker</td><td colspan="3">影響なし — 日付のデータ項目は UTC時間での表示です。</td></tr></tbody></table>

<div data-zendesk-anchors="why-change-the-time-zone=%E3%81%AA%E3%81%9C%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E3%82%92%E5%A4%89%E6%9B%B4%E3%81%99%E3%82%8B%E3%81%AE%E3%81%8B h_01HJR69P6Z44SZA5A684H82PNV=%E3%81%AA%E3%81%9C%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E3%82%92%E5%A4%89%E6%9B%B4%E3%81%99%E3%82%8B%E3%81%AE%E3%81%8B changing-the-time-zone=%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E3%81%AE%E5%A4%89%E6%9B%B4%E6%96%B9%E6%B3%95 h_01HJR69P6ZWJQ47FQY2HATAAE3=%E3%82%BF%E3%82%A4%E3%83%A0%E3%82%BE%E3%83%BC%E3%83%B3%E3%81%AE%E5%A4%89%E6%9B%B4%E6%96%B9%E6%B3%95 h_01HJR69P6Z6B0Q6E6996WXVZ0N=%E4%BE%8B aggregate-data=%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF h_01HJR69P6ZY8JJBCBSDZKN75N6=%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF raw-data-reports=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HJR69P6ZDXXK8ZTKK3E774VJ=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88" />

---
title: ピープルベースドアトリビューション(PBA)のオンボーディングガイド
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-10-01T08:00:26Z'
  edited_at: '2026-10-14T09:20:26Z'
  id: 360013821097
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360013821097
---
> **概要：**

## PBA の設定

PBAの設定は、ここで説明しているいくつかのアクション項目で構成されています。以下の表もご参照ください。

* AppsFlyer CSMまたは営業担当者に連絡し、PBAを有効にします。
* ブランドのデジタル資産を一つの "ブランドバンドル" にグループ化します。
* WebサイトにWeb SDKを、アプリにはモバイルSDKを実装します。
* AppsFlyerがデータを収集し計測します。
  * データはいくつかの異なるメディアソースから収集されます。
  * 記録されたデータはタッチポイントとイベントに分類されます。
  * イベントは、過去30日間に発生したダイレクト (direct) 以外の最後のWebサイト訪問に紐づきます。
  * 広告主側で一部のイベントをコンバージョンイベントとして設定します。例）購入イベント等。コンバージョンイベントは、管理画面上で分析できます。
  * ローデータは、独自のデータ分析をするために使用できます。
* カスタマージャーニーを分析してキャンペーンを最適化します。

### PBAの設定ステップ

まずAppsFlyer CRMまたは営業担当者に連絡し、PBAを有効にしてから、セットアップを開始します。セットアップに必要なアクション項目について、次の表にて詳しく説明しています。この<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQkYW2k1VUFugYLZ7Xv5esBL4kxfoNXMw0wyfRvoNGHdgiyZS5K5BE4seR2bjocK5HAArj97nlqF4By/pub?output=xlsx">スプレッドシート</Anchor>をダウンロードして、進捗状況を記録します。

**ベストプラクティス：**

<table><thead><tr><th> </th><th>担当者</th><th>アクション</th><th>備考</th></tr></thead><tbody><tr><td><span id="1"></span><p> 1</p></td><td><p>広告主 </p></td><td><ul><li> </li><li> <span><a href="./pba-brand-bundles-and-settings" target="_blank">ブランドバンドルを設定してください</a></span>；ブランドのデジタルプロパティ（モバイルとWebアプリ）をまとめます。 </li><li>追加の<a href="./pba-brand-bundles-and-settings#domain-exclusion" target="_blank">除外ドメイン</a>を指定してください。</li></ul></td><td><ul><li><span>分析とレポートはブランド内で集計されます。</span></li></ul></td></tr><tr><td><span id="2"></span><p> 2</p></td><td>  ウェブマスター  </td><td><ul><li>Webアプリで定義されたWebサイトに<a href="./pba-web-sdk-integration-guide" target="_blank">Web SDK</a>をインストールしてください。 </li><li>Web SDK を次のように設定する：  <ul><li>訪問の計測</li><li>イベントの計測</li><li>CUIDの設定</li><li> <a href="./test-pba-web-sdk-integration" target="_blank">SDKテストツール</a>による実装テスト </li></ul></li></ul></td><td><ul><li><span>SDKが訪問とイベントを計測。</span></li><li><span>実装は、Google Tag Manager (GTM)、Adobe、Tealiumを通じて完全にサポートされています。</span></li><li> <strong>必須</strong> 必須：ユーザー登録またはログインの直後に SetCusotmerUserID() を呼び出してください。CUIDがない場合、代替案について担当CSMまでご相談ください。 </li></ul></td></tr><tr><td><span id="3"></span><p>3</p></td><td><p>広告主</p></td><td><p>ウェブマスターが<a href="./test-pba-web-sdk-integration" target="_blank">SDKテストツール</a>を使用して、SDKが実装されているWebサイトにて以下が設定されていることを確認してください。</p><ul><li>訪問の計測</li><li>イベントの計測</li><li>CUIDの設定</li></ul></td><td><p>広告主</p></td></tr><tr><td><span id="4"></span><p>4 </p></td><td><p>ディベロッパー＆広告主</p></td><td><p>[オプション] <a href="./web-server-to-server-events-api-for-pba-web-s2s" target="_blank">Web server-to-server</a> API</p></td><td>自動サブスクリプション更新などのWebに関するイベントをレポートします。</td></tr><tr><td><span id="5"></span><p>5</p></td><td><p>広告主</p></td><td><ul><li> コンバージョンイベントを<span>定義</span>： <ul><li> <span>Webイベント</span> </li><li> </li></ul></li></ul></td><td><ul><li><span>実行する前に、デイリー\*処理が完了するまでお待ちください。</span></li></ul></td></tr><tr><td><span id="6"></span><p> 6</p></td><td><p>広告主</p></td><td><p>管理画面を使用し始めます</p></td><td><ul><li><a href="./pba-website-attribution-dashboard" target="_blank">Webサイト計測</a></li><li><a href="./pba-web-assisted-installs" target="_blank">Webアシストインストール</a></li></ul></td></tr><tr><td><span id="7"></span><p> 7</p></td><td>広告主</td><td><a href="./pba-raw-data-reports#setting-up-pba-reports-in-data-locker" target="_blank">Data Lockerの設定</a></td><td><p>タッチポイント、標準とコンバージョンイベントを含むPBAローデータレポートとおよびWebアシストインストールとコンバージョン経路を含む専用レポートへのアクセスを提供します</p></td></tr><tr><td><span id="8"></span><p>8</p></td><td><p>広告主</p></td><td><p>オプション<br/></p></td><td><p>データは、デイリー\*処理の後に利用できます。</p></td></tr><tr><td colspan="4"><span id="-due-to-processing-data-is-available-10-hours-after-midnight-utc-on-the-day-of-the-event-meaning-mondays-events-are-available-tuesday-1000-utc"></span>\* 処理のため、データはイベント当日のUTC深夜から10時間後に利用できるようになります。つまり、月曜日のイベントは火曜日のUTC10:00に利用できます。 </td></tr></tbody></table>

## SDK／APIを介したPBAデータ収集

|  | Webプラットフォーム | モバイル(アプリ)プラットフォーム |
| --- | --- | --- |
| SDK | <Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide">Web</Anchor><ul><li>WebサイトにインストールされているJavaScriptタグのSDK</li><li>Webサイト訪問、Webイベントを計測</li></ul> | <Anchor target="_blank" href="/marketers/ja/docs/integrate-the-appsflyer-sdk">モバイル</Anchor><ul><li>iOS、Android、Unity等に実装されたアプリ用SDK</li><li>アプリ内で発生するアプリインストール、ユーザーアクションを計測</li></ul> |
| Server-to-server API | <Anchor target="_blank" href="/marketers/ja/docs/web-server-to-server-events-api-for-pba-web-s2s">Web S2S</Anchor><ul><li>バックエンドサーバー（Webではない）で発生するイベントを計測</li><li>例）サブスクリプション更新</li></ul> | <Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">モバイルS2S</Anchor><ul><li>バックエンドサーバー（アプリではない）で発生するイベントを計測</li><li>例）サブスクリプション更新</li></ul> |

<div data-zendesk-anchors="setting-up-pba=pba-%E3%81%AE%E8%A8%AD%E5%AE%9A 01H8V1XPAHGFVJRKM56S2ZQTBD=pba-%E3%81%AE%E8%A8%AD%E5%AE%9A pba-setup-steps=pba%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%B9%E3%83%86%E3%83%83%E3%83%97 01ECF26CMN668ZZV6XNZA3W692=pba%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%82%B9%E3%83%86%E3%83%83%E3%83%97 pba-dataacquisition-via-sdkapi=sdkapi%E3%82%92%E4%BB%8B%E3%81%97%E3%81%9Fpba%E3%83%87%E3%83%BC%E3%82%BF%E5%8F%8E%E9%9B%86 01H8V1XPAH23BV25ZCMFR7MM9Q=sdkapi%E3%82%92%E4%BB%8B%E3%81%97%E3%81%9Fpba%E3%83%87%E3%83%BC%E3%82%BF%E5%8F%8E%E9%9B%86" />

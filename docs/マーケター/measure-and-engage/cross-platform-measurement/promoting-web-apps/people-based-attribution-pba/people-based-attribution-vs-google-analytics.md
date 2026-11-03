---
title: People-based Attribution (PBA)Google Analytics
metadata:
  keywords:
    - Google Analytics
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-03-28T07:22:04Z'
  edited_at: '2026-10-14T09:25:45Z'
  id: 360001305617
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360001305617
---
> **概要：** 概要 ：ピープルベースドアトリビューション（PBA）とGoogleアナリティクスの違いについて

## Google Analyticsと比較した場合のPBA

PBAはこれに追加した価値を提供しています。

* PBAは、アトリビューション計測に焦点を当てた、独立した、偏りのないツールです。PBAはユーザーをウェブサイトに導いてくれるメディアソースやキャンペーンにコンバージョンや収益の成果を紐づけます。
* Google Analyticsはウェブ分析に重点をおいています。ユーザー行動に関連するデータを収集、分析、集計します。Google Analyticsを使用すると、例えば、ユーザーの行動、ファネル、ウェブイベントを分析することができます。

### Googleアナリティクスと比較時のPBAの利点

Googleアナリティクスと比較した場合のPBAの利点は次のとおりです。

* PBAには以下が含まれます；
  * Web-to-app計測。この指標は、ウェブサイトからアプリに移動したユーザー数を示します。また、どのメディアソースやキャンペーンが Web サイトにユーザーを誘導し、その後アプリをインストールしたかがわかります。
  * <Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports">コンバージョンやイベントのローデータ</Anchor>を活用して、独自のBIツールにデータを取り込むことができます。これにより、柔軟に分析を実行することが可能になります。

### 乖離の理由

PBAとGoogle Analyticsを比較した場合の乖離については、以下をご参照ください。

#### SDKの実装例

PBAとGoogle Analyticsの実装方法は、データ収集に影響を与える可能性があります。

<div id="google-analytics-shows-more-sessions-and-visitors" />

<Accordion title="Google Analyticsの方が、セッションと訪問者が多い">

#### 原因

Google Analyticsが Web SDK よりも前に読み込まれた場合、離脱したユーザー、またはウェブサイトに短期間滞在したユーザーは PBA ではカウントされません。これにより、セッションと訪問者のデータに乖離が生じます。

#### 解決策

Web SDK は、できるだけ早期に読み込まれるように配置することを強くお勧めします。

<Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#web-sdkのwebサイトへの実装">SDKが直接設置されている、またはGoogleタグマネージャを使用して設置されている</Anchor>かに関わらず、SDKのロード遅延によって大きな乖離が生じる可能性があります。

</Accordion>

<div id="google-analytics-shows-more-data-for-sessions-campaign-and-conversions" />

<Accordion title="Google Analyticsの方がセッション、キャンペーン、コンバージョン数が多い">

#### 原因

AppsFlyerのPBA Web SDK は、特定のページにのみ存在します。Googleアナリティクスはすべてのページに存在します。結果として、Google Analyticsはウェブサイト全体のデータ収集をするのに対し、Web SDKは特定のページのデータのみを収集します。これにより、セッション、アクセスユーザー、キャンペーン、コンバージョンに乖離が生じます。

#### 解決策

Web SDKをウェブサイトのすべてのページに実装してください。

</Accordion>

### 管理画面の設定

タイムゾーンやデータフィルタなどの管理画面の設定は、データの表示方法に影響する可能性があります。

<div id="timezone-settings-discrepancies-in-data" />

<Accordion title="タイムゾーンの設定：データの乖離">

#### 原因

Google Analyticsのタイムゾーン設定が PBA ダッシュボードの設定と異なる場合は、乖離が発生する可能性があります。

> 📄 **例**
>
> これは、アプリの管理画面がGAの管理画面より1日進んでいることを意味します。
>
> すなわち、3月2日のAppsFlyer管理画面に表示されるデータは、GA管理画面で3月3日を選択しないと表示されません。

#### 解決策

AppsFlyerとGoogleアナリティクスの両方でタイムゾーン設定が同じであることを確認してください。

</Accordion>

<div id="data-filters--discrepancies-in-data" />

<Accordion title="データフィルタ：データの乖離">

#### 問題

AppsFlyerとGoogle Analyticsの両方とも日付、アトリビューションされたメディアソース、キャンペーン、イベントに応じてデータをフィルタできます。AppsFlyerとGoogle Analyticsでの異なるフィルタ設定は、同じデータに対して異なる見え方を生成することになります。

#### 解決策

2 つの管理画面のデータを比較する場合は、フィルターが適用されていないことを確認してください。

</Accordion>

### コンバージョンとイベント

計測モデルやルックバック期間、イベント送信方法、クッキー設定は全てデータ収集と処理に影響します。

<div id="lookback-window-discrepancies-in-conversion-measurement" />

<Accordion title="ルックバック期間：コンバージョン計測における乖離">

#### 原因

ルックバック期間が、Google AnalyticsとPBAで異なる場合、計測データに乖離が生じる可能性があります。

#### 解決策

PBAのルックバック期間は常に30日です。Google Analyticsにおいて、<Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189">計測モデルを選択する際は</Anchor>、ルックバック期間を30日に設定するようにお願いします。

</Accordion>

<div id="attribution-model--discrepancies-in-conversion-measurement" />

<Accordion title="計測モデル：コンバージョン計測における乖離">

#### 原因

PBAとGoogle Analyticsで異なる計測モデルを設定している場合は、計測データに乖離が生じる可能性があります。

#### 解決策

Google Analyticsでは<Anchor target="_blank" href="https://support.google.com/analytics/answer/1665189?hl=en">デフォルト計測モデル</Anchor>を選択できます。しかし、PBAは、ラスト間接タッチ、30日間ルックバック期間計測モデルとなります。Google アナリティクスでも、ラスト間接タッチ計測モデルを選択してください。

</Accordion>

<div id="sending-events" />

<Accordion title="イベントの送信">

#### 問題

Google Analytics SDKとWebSDKの両方とも、イベントを送信することができます。Google Analyticsへのイベント送信ロジックを実装し、別にPBAへのイベント送信ロジックを実装すると、乖離が発生する可能性があります。

#### 解決策

イベントを送信する場合は、次のことをご確認ください。

* 同じトリガーが両方に適用されているか
* Google Analyticsと PBA の両方にイベントが送信されているか

Web SDK を使用してイベントを送信する方法については、 <Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#イベント記録の原則">ここ</Anchor> をクリックしてください。

</Accordion>

<div id="cookies" />

<Accordion title="クッキー">

PBAとGoogle Analyticsのいづれも、ユーザーを認識するためにクッキーを使用しています。

#### Google Analyticsのクッキー設定

Google Analytics SDKが自動的にクッキーの設定を処理できるようにすることをお勧めしていますが、 <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/cookies-user-id">クッキー設定を変更</Anchor> することは可能です。クッキー設定のいかなる変更も、乖離の生じる要因となります。

#### クッキーの有効期限の設定

Google Analyticsでは、クッキーの有効期限を設定できます。Google Analyticsのクッキー有効期限をWeb SDKの有効期限よりも前に設定した場合は、乖離が発生する可能性がございます。

> 📄 **例**
>
> マークは、あなたのウェブサイトに1年以上頻繁に訪問しているユーザーです。現在、プレミアムコンテンツへの購読を検討しています。
>
> あなたの開発者がGoogle Analyticsのクッキー有効期限を1 年に設定しました。一方で、Web SDKのクッキー有効期限は2年となります。
>
> マークが最終的に購読することを決め、コンバージョンが登録されると、Google Analyticsのクッキー有効期限は切れており、別のものが設定されています。
>
> その結果、Google Analyticsは2人のユーザーを表示しますが、いづれもマークです。そのうち1人のみがコンバージョンに関連づけられています。一方で、PBAではマークを1人のユーザーとして表示され、この同じユーザーにコンバージョンが関連づけられています。
>
> つまり、Google Analyticsのコンバージョン率がPBAのコンバージョン率よりも低くなります。

#### クッキーのサブドメインの設定

Google Analyticsではサブドメインにクッキーを設定できますが、PBAではトップレベルドメインにのみクッキーを設定します。

> 📄 **例**
>
> サブドメイン **store.mywebsite.com** にクッキーを設定したとします。シャロンはあなたのウェブサイトを訪問し、あなたのオンラインストア **store.mywebsite.com** に行きました。Google Analyticsは、彼女を**2 つの異なるユーザー** とみなします。
>
> PBAはトップレベルドメイン **mywebsite.com** にのみクッキーを設定しているため、 **mywebsite.com** と **store.mywebsite.com** を訪問したシャロンを同一ユーザーとみなします。
>
> その結果、Google Analyticsでは 2 人のユーザー、PBA では 1 人のユーザーになります。

</Accordion>

<div data-zendesk-anchors="pba-compared-to-google-analytics=google-analytics%E3%81%A8%E6%AF%94%E8%BC%83%E3%81%97%E3%81%9F%E5%A0%B4%E5%90%88%E3%81%AEpba benefits-of-pba-over-google-analytics=google%E3%82%A2%E3%83%8A%E3%83%AA%E3%83%86%E3%82%A3%E3%82%AF%E3%82%B9%E3%81%A8%E6%AF%94%E8%BC%83%E6%99%82%E3%81%AEpba%E3%81%AE%E5%88%A9%E7%82%B9 reasons-for-differences=%E4%B9%96%E9%9B%A2%E3%81%AE%E7%90%86%E7%94%B1 sdk-implementation=sdk%E3%81%AE%E5%AE%9F%E8%A3%85%E4%BE%8B cause=%E5%8E%9F%E5%9B%A0 solution=%E8%A7%A3%E6%B1%BA%E7%AD%96 cause::49d3e519=%E5%8E%9F%E5%9B%A0-1 solution::447e7ac9=%E8%A7%A3%E6%B1%BA%E7%AD%96-1 dashboard-settings=%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2%E3%81%AE%E8%A8%AD%E5%AE%9A cause::30244d2c=%E5%8E%9F%E5%9B%A0-2 solution::f1a0e066=%E8%A7%A3%E6%B1%BA%E7%AD%96-2 data-filters-%C2%A0discrepancies-in-data=data-filters--discrepancies-in-data issue=%E5%95%8F%E9%A1%8C solution::df8f3921=%E8%A7%A3%E6%B1%BA%E7%AD%96-3 conversions-and-events=%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%B8%E3%83%A7%E3%83%B3%E3%81%A8%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 cause::b346571c=%E5%8E%9F%E5%9B%A0-3 solution::4bb14ac9=%E8%A7%A3%E6%B1%BA%E7%AD%96-4 attribution-model%C2%A0-discrepancies-in-conversion-measurement=attribution-model--discrepancies-in-conversion-measurement cause::2296f6c1=%E5%8E%9F%E5%9B%A0-4 solution::b2be4a33=%E8%A7%A3%E6%B1%BA%E7%AD%96-5 issue::b412f5ba=%E5%95%8F%E9%A1%8C-1 solution::39b4d7d6=%E8%A7%A3%E6%B1%BA%E7%AD%96-6 cookie-settings-in-google-analytics=google-analytics%E3%81%AE%E3%82%AF%E3%83%83%E3%82%AD%E3%83%BC%E8%A8%AD%E5%AE%9A setting-cookie-expiration=%E3%82%AF%E3%83%83%E3%82%AD%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E6%9C%9F%E9%99%90%E3%81%AE%E8%A8%AD%E5%AE%9A setting-cookie-subdomain=%E3%82%AF%E3%83%83%E3%82%AD%E3%83%BC%E3%81%AE%E3%82%B5%E3%83%96%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A" />

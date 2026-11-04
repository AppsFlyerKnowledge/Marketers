---
title: Google Analyticsとの連携｜データの差異
metadata:
  keywords:
    - Analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-12-07T13:38:17Z'
  edited_at: '2026-10-28T09:04:22Z'
  id: 4413026674833
  locale: ja
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/ja/articles/4413026674833
---
> **概要：** AppsFlyerとGoogle Analyticsの間でデータの差異が生じる原因を説明します。

<div id="discrepancies-in-data-between-appsflyer-and-google-analytics" />

## AppsFlyerとGoogle Analyticsのデータの差異

AppsFlyerとGoogle Analyticsでデータに差異が生じる原因を、以下に示します。

<div id="high-volume-of-nonconsenting-ios-145-users" />

<Accordion title="同意していないiOS 14.5以降のユーザーが多い場合">

<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">アプリでAAPを有効にしている</Anchor>場合、AppsFlyerは、同意していないiOS 14.5以降のユーザーのポストバックをGoogle Analyticsに送信しません。該当するユーザーが多いアプリでは、AppsFlyerとGoogle Analyticsの管理画面のデータに差異が生じます。

</Accordion>

<div id="customer-user-id" />

<Accordion title="カスタマーユーザーID">

Google Analyticsは、カスタマーユーザーIDに基づいてイベントを紐付けます。 AppsFlyerがデフォルトで送信するカスタマーユーザーIDは、GAIDまたはIDFAです。

そのため、Google Analyticsは、インストール後にアンインストールし、再インストールしたユーザーを同じユーザーとして扱います。

<div id="example" />

> 📄 **例**
>
> ユーザーがアプリをインストールし、その後アンインストールします。その後、リアトリビューション期間内に、リターゲティングキャンペーン経由でアプリを再インストールします。
>
> Google Analyticsは、このユーザーを同じユーザーとして扱います。 Google Analyticsのユーザーエクスプローラでは、このユーザーのデータとして次のすべてが表示されます。
>
> * regular-install
> * regular-in-app-event
> * reattribution-install
> * reattribution-in-app-event
>
> 一方、AppsFlyerでは、次の2人の異なるユーザーとして扱います。
>
> * ユーザー獲得キャンペーン経由のユーザー
> * リターゲティングキャンペーン経由のユーザー

また、GA SDKとAppsFlyer SDKの両方を実装している場合も、差異が生じることがあります。

</Accordion>

<div id="time-zone-differences" />

<Accordion title="タイムゾーンの違い">

GA管理画面のタイムゾーンと、AppsFlyerに設定したアプリのタイムゾーンが異なる場合、データが一致しないことがあります。

<div id="example-1" />

> 📄 **例**
>
> アプリの管理画面はGMT+13、GA管理画面はGMTに設定されているとします。この場合、アプリの管理画面の日付は、GA管理画面より1日先になります。
>
> そのため、GA管理画面で3月2日に表示されるデータをアプリの管理画面で確認するには、期間フィルターで3月3日を選択する必要があります。

</Accordion>

<div id="duplicate-events" />

<Accordion title="イベントの重複">

短い間隔でイベントが発生した場合、AppsFlyerとGoogle Analyticsのいずれも、重複イベントとして除外することがあります。 AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#how-does-appsflyer-handle-event-deduplication">イベントの重複排除の仕組み</Anchor>は、Google Analyticsとは異なります。

重複排除の方法が異なるため、イベントデータに差異が生じることがあります。

</Accordion>

<div id="session-count" />

<Accordion title="セッション数">

AppsFlyerは、アプリが起動するか、フォアグラウンドに戻るたびにセッションを集計します。 Google Analyticsは、CID（カスタマーユーザーID）とアクティビティに基づいてセッションを集計します。

<div id="example-2" />

> 📄 **例**
>
> ユーザーがアプリを起動していくつか操作した後、バックグラウンドに移します。その後、約5分間隔で同じ操作を4回繰り返します。
>
> AppsFlyerでは、5つの異なるセッションとして集計されます。 Google Analyticsでは、1つのセッションとして集計されます。

AppsFlyerとGoogle Analyticsのセッションの集計方法の詳細は、以下の資料を参照してください。

1. <Anchor target="_blank" href="/marketers/ja/docs/measure-sessions">AppsFlyerでのセッションの集計方法</Anchor>
2. <Anchor target="_blank" href="https://support.google.com/analytics/answer/2731565?hl=en">Google Analyticsのセッション</Anchor>

</Accordion>

<div id="google-analytics-views-and-filters" />

<Accordion title="Google Analyticsのビューとフィルター">

Google Analyticsでは、複数のビューを作成し、それぞれに異なるフィルターを適用できます。 AppsFlyerとGoogle Analyticsのデータを比較する際は、Google Analyticsで***All Web Site Data***ビューを表示していることを確認してください。

</Accordion>

<div data-zendesk-anchors="discrepancies-in-data-between-appsflyer-and-google-analytics=appsflyer%E3%81%A8google-analytics%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%B7%AE%E7%95%B0 h_01HDP3G48R2XXEQDEAAJYGR9V9=appsflyer%E3%81%A8google-analytics%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%B7%AE%E7%95%B0 h_01HDP3G48RQD3EW0DTRE2252JF=high-volume-of-nonconsenting-ios-145-users h_01HDP3G48RPWDY7ZRG9HM1F5AR=customer-user-id h_01HDP3G48RMGSJSWQDSKW5DXD9=%E4%BE%8B h_01HDP3G48R2JWF3Y23011NDCAN=time-zone-differences h_01HDP3G48RXFWZX4FQ0V2ZE44D=%E4%BE%8B-1 h_01HDP3G48RHT7PWSWZZAG27CP0=duplicate-events h_01HDP3G48R1044364MF96QX41E=session-count h_01HDP3G48RHQ3VG6N4HTT1KJFS=%E4%BE%8B-2 h_01HDP3G48R9571AS0WH7TWQWJP=google-analytics-views-and-filters" />

---
title: セッションの計測
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-03-14T12:13:13Z'
  edited_at: '2026-10-28T09:08:02Z'
  id: 360000520785
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/360000520785
---
> **概要**：広告主はセッションの指標を使用して、一定期間内のアプリのユーザーエンゲージメントを計測します。

<Image align="center" alt="DAU_example.jpg" src="https://files.readme.io/97b845b9e04809dc6b670746c81cf1ca59dce11f492194ee7e7895ada01c0b86-360016015278.jpg" width="461px" />

<div id="sessions-counting-principles" />

## セッションの集計の基本

ユーザーによるセッション（起動）の回数は、アプリのユーザーエンゲージメントを計測する重要な指標です。複数のレポートやダッシュボードで確認できます。セッションは、以下の指標の算出に使用します。

* 日次アクティブユーザー数（DAU）
* 月次アクティブユーザー数（MAU）
* リテンション
* デフォルトの「アプリを3回起動」という条件で判定するロイヤルユーザー

**注意**オーガニックのセッション数は、アクティビティとコホートのダッシュボードで確認できますが、Overview dashboardでは確認できません。

<div id="sessions-calculation" />

### セッション数の算出

セッション数は、SDKが報告する*af\_app\_opened*イベントに基づいて算出します。サーバー側では、最初の5セッションは、セッション間の時間間隔に関係なく計上されます。 6回目以降は、セッション間の最小時間を判定する仕組みによって、計上するかどうかが決まります。

*af\_app\_openedイベント*は、Data Lockerで取得できるセッションのローデータでは、*launch*として表示されます。セッションは、他のレポートツールでは取得できません。本記事では、分かりやすくするため*af\_app\_opened*という名称を使用します。

**セッションの報告**

以下のいずれかが発生すると、SDKがセッションを報告します。

* ユーザーがアプリを起動する。
* アプリがバックグラウンドからフォアグラウンドに移る。開発者は、[setMinTimeBetweenSessionsを呼び出して、報告の動作を変更できます。](/docs/measure-sessions#session-reporting-by-the-app-sdk)
* Androidアプリで、開発者が明示的にセッションを報告する。たとえば、常にバックグラウンドで動作するユーティリティアプリなどで使用します。

**セッションの指標**

セッション数は、最初のセッションから集計します。 6回目のセッションから、セッション間の最小時間を判定する仕組みが適用されます。以下の例のとおり、デフォルトの間隔は10分です。

<div id="minimum-time-between-sessions-mechanism" />

## セッション間の最小時間の判定

この仕組みは、セッションの集計数に影響します。**注意**セッション間の最小時間を1時間超などの長い間隔に設定し、ユーザーが1日に何度もアプリを開かない場合は、DAUやリテンションなど、一部のセッション関連の指標に影響する可能性があります。特に、通常1日に1回程度しか起動されないアプリでは注意が必要です。 

<div id="description-and-example" />

<Accordion title="仕組みと例">

この仕組みは、最初の5セッションの集計後に適用されます。 6回目以降は、設定したセッション間の最小時間を経過している場合に、セッションを計上します。

セッションを計上→カウントダウンタイマーを開始→タイマーの動作中に報告されたセッションは計上しない、という流れです。

**例**

前提：セッション間の最小時間は10分に設定され、最初の5セッションはすでに計上されています。

| ケース | セッションの報告時刻（00:00からの経過分） | 計上されるセッション数 | 計上されないセッション |
| --- | --- | --- | --- |
| A | 0, 10, 20, 30 | 4 | なし |
| B | 0, 1, 9, 11 | 2 | 1, 9 |
| C | 0, 10, 15, 21 | 3 | 15 |

</Accordion>

<div id="timer-setting" />

<Accordion title="タイマーの設定">

* デフォルト値：10分
* 以下の値を設定できます。

  * 1～60分
  * 1～24時間

**セッション間の最小時間のタイマーを設定するには、以下の手順を実施します。**

1. AppsFlyerのサイドメニューで、**設定**＞**アプリ設定**を選択します。
2. **セッション間の最小時間**を設定します。
3. ［**設定を保存**］をクリックします。   
   変更は1時間以内に反映されます。

</Accordion>

<div id="sessions-related-topics" />

## セッションに関するその他の情報

<div id="retargeting-sessions" />

<Accordion title="リターゲティングのセッション">

* リターゲティングのセッションは、2020年7月12日以降のデータで利用できます。
* 以下で確認できます。
  * Overview dashboardのリターゲティング表示と統合表示。
  * コホートのリターゲティング表示と統合表示。 
    * 統合表示で、セッションがUAとリターゲティングの両方のメディアソースに紐付く場合は、リターゲティングのメディアソースが優先され、UAのメディアソースは表示されません。
    * データ更新：日次、UTC 13:00。
  * Data Locker：リターゲティングセッションレポートを有効にできます。リエンゲージメントとリアトリビューションの両方のセッションが含まれます。 
    * データ更新：6時間の遅延。
* リエンゲージメント期間中、セッションはUAとリターゲティングの両方のメディアソースに紐付けられます。他のリエンゲージメントのアプリ内イベントも、同様に<Anchor target="_blank" href="/marketers/ja/docs/resolve-retargeting-double-attribution">両方に紐付けられます</Anchor>。
* Google広告とX広告では、ポストバックの重複を防ぐため、*af\_app\_opened*イベントは1回だけ送信されます。

</Accordion>

<div id="sessions-postbacks-to-partners" />

<Accordion title="パートナーへのセッションポストバック">

パートナーにセッションポストバックを設定すると、計上されたセッションごとに<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#マッピング方法">ポストバック</Anchor>が送信されます。

* 送信するには、*af\_app\_opened*をパートナーのイベントに明示的にマッピングします。注意 Data Lockerで取得できるAppsFlyerのローデータレポートでは、このイベントは*launch*として表示されます。
* このイベントは送信量が多く、多くのパートナーが受信を希望しない点に注意してください。

<div id="note" />

> 📘 **注意**
>
> `af_app_opened`のマッピングに対応するのは、**Send Sessions**が有効なパートナーのみです。

</Accordion>

<div id="session-reporting-by-the-app-sdk" />

<Accordion title="アプリ（SDK）によるセッションの報告">

**アプリ側：** SDKは、*setMinTimeBetweenSessions*の設定を考慮したうえで、アプリの起動時やフォアグラウンドへの移行時に*af\_app\_opened* を送信します。

**サーバー側：アプリの初回起動後の最初の5セッションに該当せず**、かつセッション間の最小時間の判定条件を満たす場合に、セッションを計上します。計上されたセッションには、他のアプリ内イベントと同じ<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">アトリビューションルール</Anchor>が適用されます。

<div id="explicit-sessions-reporting-by-the-developer-android-apps-only" />

#### **開発者による明示的なセッションの報告（Androidアプリのみ）**

Androidでは、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#logsession">logSession</Anchor>を使用して、明示的にセッションを報告します。 iOSには、同等の呼び出しはありません。

* 常にバックグラウンドで動作するアプリでは、開発者がセッション報告用のロジックを実装する必要がある場合があります。たとえば、バッテリー節約、ランチャー、画面ロック、ウイルス対策などのユーティリティアプリが該当します。こうしたアプリでは、毎日午前0時、またはアプリに適した別の間隔で、セッションを報告することを検討してください。
* また、［*メモリを解放*］ボタンの押下など、特定のアプリ内アクションを実行した時点でセッションを数える方法もあります。

<div id="setting-minimum-time-between-app-launches" />

#### **アプリ起動間の最小時間の設定**

2つのセッションを別々に報告するために必要な最小の時間間隔を、SDKで設定します。

***setMinTimeBetweenSessions***で、af\_app\_openedイベントをそれぞれ報告するために必要な、セッション間の最小時間を制御します。

* ［デフォルト］5秒。つまり、次のセッションを報告するまでに、少なくとも5秒が経過している必要があります。
* APIで、セッション間に必要な最小時間を設定できます。

**`setMinTimeBetweenSessions`のSDKリファレンス：**

<Tabs>
<Tab title="Android">

Android SDKリファレンスの[`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setmintimebetweensessions)を参照してください。

</Tab>

<Tab title="iOS">

iOS SDKリファレンスの[`minTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#mintimebetweensessions)を参照してください。

</Tab>

<Tab title="Unity">

Unity SDKリファレンスの[`setMinTimeBetweenSessions`](https://dev.appsflyer.com/hc/docs/api#setmintimebetweensessions)を参照してください。

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="sessions-counting-principles=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E9%9B%86%E8%A8%88%E3%81%AE%E5%9F%BA%E6%9C%AC h_01HB8NDPNKERK1RR1Y09V2R2CC=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E9%9B%86%E8%A8%88%E3%81%AE%E5%9F%BA%E6%9C%AC sessions-calculation=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E6%95%B0%E3%81%AE%E7%AE%97%E5%87%BA h_01HB8NDPNKFW6S28A3TC7W5J3C=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E6%95%B0%E3%81%AE%E7%AE%97%E5%87%BA minimum-time-between-sessions-mechanism=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E9%96%93%E3%81%AE%E6%9C%80%E5%B0%8F%E6%99%82%E9%96%93%E3%81%AE%E5%88%A4%E5%AE%9A h_01HB8NDPNKF32E34M3CBJ6GMP8=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E9%96%93%E3%81%AE%E6%9C%80%E5%B0%8F%E6%99%82%E9%96%93%E3%81%AE%E5%88%A4%E5%AE%9A h_01HB8NDPNKERP5YVEXMPKP620B=description-and-example h_01HB8NDPNK6R2P682EPSPQ8MGH=timer-setting sessions-related-topics=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%83%85%E5%A0%B1 h_01HB8NDPNKPTJX56Q2SVAB6V6T=%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E6%83%85%E5%A0%B1 h_01HB8NDPNMX2JTFHVTN14MVCCW=retargeting-sessions h_01HB8NDPNM5Z9ZHADD32EG66BJ=sessions-postbacks-to-partners h_01HYARHNQCWEHAFQ6B3FHZ0KTK=%E6%B3%A8%E6%84%8F h_01HB8NDPNM0Z7D1ZS7G952SSKK=session-reporting-by-the-app-sdk explicit-sessions-reporting-by-the-developer-android-apps-only=%E9%96%8B%E7%99%BA%E8%80%85%E3%81%AB%E3%82%88%E3%82%8B%E6%98%8E%E7%A4%BA%E7%9A%84%E3%81%AA%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%A0%B1%E5%91%8Aandroid%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%81%BF h_01HB8NTFMR3Y9GHFP3EWMAATHY=%E9%96%8B%E7%99%BA%E8%80%85%E3%81%AB%E3%82%88%E3%82%8B%E6%98%8E%E7%A4%BA%E7%9A%84%E3%81%AA%E3%82%BB%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E5%A0%B1%E5%91%8Aandroid%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%81%BF setting-minimum-time-between-app-launches=%E3%82%A2%E3%83%97%E3%83%AA%E8%B5%B7%E5%8B%95%E9%96%93%E3%81%AE%E6%9C%80%E5%B0%8F%E6%99%82%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HB8NTMC1JYPDWYG9YC8RNSEQ=%E3%82%A2%E3%83%97%E3%83%AA%E8%B5%B7%E5%8B%95%E9%96%93%E3%81%AE%E6%9C%80%E5%B0%8F%E6%99%82%E9%96%93%E3%81%AE%E8%A8%AD%E5%AE%9A" />

---
title: 通知設定
metadata:
  keywords:
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
  created_at: '2025-03-24T10:10:37Z'
  edited_at: '2026-10-14T09:22:04Z'
  id: 33732395637905
  locale: ja
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/ja/articles/33732395637905
---
> **概要：** 重要なAppsFlyerの通知における設定を管理します。

アカウントで特定のイベントが発生したときに、AppsFlyerからのメール通知を受け取ることを選択できます。**通知設定**では、これらの通知の受信をオプトインまたはオプトアウトできます。

<div id="accessing-and-configuring-notification-preferences" />

## 通知設定へのアクセスと設定

<div id="to-access-notifications" />

### 通知設定画面へのアクセス：

* 上部のバーから、アカウントメニュー（Eメールアドレス） をクリックし、**通知設定を開きます。**
* もしくは、上部メニューのベルアイコンから > **設定アイコン**をクリックします。

<div id="configuring-notifications" />

### 通知の設定

通知の受信を許可するには、利用可能な通知のリストからその通知をオンにしてください。

受信を停止するには、オフにしてください。

注記：一部の通知はメールのみで利用できます。メール専用の通知タブには、これらの[通知設定](/docs/notifications#メールのみの通知)が含まれています。 

<div id="what-notifications-can-i-receive" />

## どのような通知を受け取ることができますか？

次の通知カテゴリが利用できます：

* アカウントとプランの管理
* 請求または決済の問題
* プライバシー関連のアラート
* インサイトと設定
* コラボレーション機能

注：一部の通知はメール経由でのみ受信できます。詳細は[こちら](/docs/notifications#email-notification)をご覧ください。

特定の通知をオプトインするためには、以下が必要です：

* **AppsFlyerアカウントで利用できる機能のみ -** 特定の通知がご利用のアカウントで利用できない場合、オン／オフのトグルは表示されません。
  * たとえば、Push API機能を利用できないアカウントプランの場合、この機能に関連するスイッチは表示されません。
* **その機能にアクセスするユーザー権限があること -** アクセス権限がない機能に関する通知の場合は、オン／オフを切り替えるスイッチが無効になります。
  * 例えば、連携パートナーを追加または編集する権限がない場合、連携パートナーの設定に関連する通知をオンまたはオフに設定するスイッチが無効になります。

<div id="when-will-i-receive-notifications" />

## 通知はいつ届きますか？

特定の通知の受信をオプトインした場合、その通知に紐づくトリガーイベントが発生した際にメールを受信します。ただし、そのユーザーが**アクセス権限を持つ**アプリやメディアソースに適用される場合に**のみ**、この通知を受信できます。

<div id="example" />

<Accordion title="例">

以下のシナリオを想定します：

* あなたのアカウントには3つのアプリが登録されています：アプリA、アプリB、アプリC。
* 各アプリは2つのメディアソース（連携パートナー）でアクティブな連携があります：Google AdsおよびTikTok
* あなたのAppsFlyerユーザーには、次の権限があります：
  * 連携パートナーを追加・編集する
  * アプリCのデータへのアクセス
  * Google Adsのデータへのアクセス
* 連携パートナーの設定に変更があった場合に通知を受け取ることを選択しました。

結果：

* アプリAとBに関する連携パートナーの設定変更があっても、通知は**届きません**。
* アプリCのTikTokの設定変更があっても通知は**届きません**。
* アプリCのGoogle広告の設定変更があった際に通知が**届きます**。

</Accordion>

<div id="where-will-i-receive-notifications" />

## 通知はどこに届きますか？

通知は、[ベル](/docs/notifications#bell-notification)アイコン、[メール](/docs/notifications#email-notification)、[Slack](/docs/notifications#slack-notification)連携で受信できます。

<div id="bell-notification" />

<Accordion title="ベル通知">

ベルアイコンの通知は、画面右上のアカウントメニュー（メールアドレス）の左側にあります。

歯車アイコンをクリックすると、[通知設定](/docs/notifications#通知設定へのアクセスと設定)に移動します。

</Accordion>

<div id="email-notification" />

<Accordion title="メール通知">

通知は、ユーザーのAppsFlyerアカウントに紐づくメールアドレスにメールで送信されます。

一部の通知はメールのみで利用できます。**メール専用の通知**タブには、これらの通知設定が含まれています。

<div id="note" />

> 📘 **注意**
>
> すべてのAppsFlyer通知メールは[notifications@appsflyer.com](mailto:notifications@appsflyer.com)から送信されます。

<div id="email-only-notifications" />

#### メールのみの通知

次の表は、**メール経由でのみ**利用可能な通知とそのトリガーとなるイベントの一覧です：

| 通知 | トリガーイベント |
| --- | --- |
| 連携済みパートナー設定の変更 | <ul><li>新しい連携パートナー設定が有効になった</li><li>既存の連携パートナー設定が非アクティブになった</li><li>既存の連携パートナーの設定が変更された</li></ul> |
| Push APIの失敗 | 12時間以内にアプリのPush APIメッセージの5%以上が失敗した |
| オーディエンス連携の失敗 | オーディエンスのパートナー連携が失敗したため確認が必要です |
| 広告収益連携の中断 | 広告収益の連携が、警告ステータスが30日以上表示された後、停止されます |
| 広告収益データの失敗 | 広告収益連携でデータが受信されない場合 |
| 連携済みパートナー：コスト連携の変更 | チームメンバーがコスト連携設定を変更した場合 |
| SKAdNetwork接続の失敗 | Google AdsまたはMetaのSKAdNetwork計測連携に問題がある場合現在の連携を削除してから、再度ログインする必要がある場合があります。 |

</Accordion>

<div id="slack-notification" />

<Accordion title="Slack通知">

**Slack通知の設定**

Slack通知を設定するには、まずSlackが接続されている必要があります。

1. 通知設定画面で、ページ右上の **連携**ボタンをクリックします。
2. Slac 通知コネクタで **接続** をクリックします。
3. 権限リクエストを確認して承認します。
   1. **あなたがSlack管理者の場合：**
      1. Slackにて、Slack Workspaceをクリックします。  
         <Image align="center" alt="" src="https://a.slack-edge.com/8e8e4/helpcenter/img/workspace-picker@2x.jpg" width="263px" />
         注記：表示されているSlack Workspaceが接続先の正しいワークスペースであることを確認してください。
      2. **ツールと設定** -> **アプリの管理**へ進みます。
      3. **Adminパネル**で、**Requests**を選択します。
      4. **Needs review**（承認の確認）タブで、AppsFlyerアプリリクエストの横にある3つのドットをクリックします。
      5. **承認** をクリックし、次のポップアップを承認します。
      6. **AppsFlyer連携画面**に戻り、**許可**ボタンをクリックします。
   2. **Slack管理者でない場合：**  
      1. SlackをAppsFlyerに接続するための権限をSlack管理者にリクエストしてください。
      2. Slack管理者は、上記のすべての手順を実行する**必要があります**。それまでの間：
      3. Slackコネクタが保留ステータスになります。
      4. Slack管理者が接続を承認したら、**接続**をクリックして連携を開始し、保留から接続に変わります。

</Accordion>

<div data-zendesk-anchors="accessing-email-notifications=%E9%80%9A%E7%9F%A5%E8%A8%AD%E5%AE%9A%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E3%81%A8%E8%A8%AD%E5%AE%9A h_01HKA254W4XDVNP816N46N59ZV=%E9%80%9A%E7%9F%A5%E8%A8%AD%E5%AE%9A%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E3%81%A8%E8%A8%AD%E5%AE%9A to-access-notifications=%E9%80%9A%E7%9F%A5%E8%A8%AD%E5%AE%9A%E7%94%BB%E9%9D%A2%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01JQ66J4YSCSX7ZGG81XHGJ3MM=%E9%80%9A%E7%9F%A5%E8%A8%AD%E5%AE%9A%E7%94%BB%E9%9D%A2%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 configuring-notifications=%E9%80%9A%E7%9F%A5%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HKA254W497H0SKTZ33CVSA4P=%E9%80%9A%E7%9F%A5%E3%81%AE%E8%A8%AD%E5%AE%9A what-notifications-can-i-receive=%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E9%80%9A%E7%9F%A5%E3%82%92%E5%8F%97%E3%81%91%E5%8F%96%E3%82%8B%E3%81%93%E3%81%A8%E3%81%8C%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01HKA254W47XRG1D3HZ6VBZ2BH=%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E9%80%9A%E7%9F%A5%E3%82%92%E5%8F%97%E3%81%91%E5%8F%96%E3%82%8B%E3%81%93%E3%81%A8%E3%81%8C%E3%81%A7%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B when-will-i-receive-notifications=%E9%80%9A%E7%9F%A5%E3%81%AF%E3%81%84%E3%81%A4%E5%B1%8A%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01JQ66BX52MV5WQ7RXH6SY3QHK=%E9%80%9A%E7%9F%A5%E3%81%AF%E3%81%84%E3%81%A4%E5%B1%8A%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01JQ6EYTZ13FHYERT48K3J25SV=example where-will-i-receive-notifications=%E9%80%9A%E7%9F%A5%E3%81%AF%E3%81%A9%E3%81%93%E3%81%AB%E5%B1%8A%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01HKA254W4Z95M335V7KWAJA6N=%E9%80%9A%E7%9F%A5%E3%81%AF%E3%81%A9%E3%81%93%E3%81%AB%E5%B1%8A%E3%81%8D%E3%81%BE%E3%81%99%E3%81%8B h_01JQ667RAW19658DVMZNFXNAJK=bell-notification h_01JQ667RAWCAVYBZD3J0T8XH2G=email-notification h_01JJGTDQFM1WE9G3XWSN9S7Z02=%E6%B3%A8%E6%84%8F emailonly-notifications=%E3%83%A1%E3%83%BC%E3%83%AB%E3%81%AE%E3%81%BF%E3%81%AE%E9%80%9A%E7%9F%A5 h_01JQ6EQR8JRBZ2ECJ7SHHWDWFC=%E3%83%A1%E3%83%BC%E3%83%AB%E3%81%AE%E3%81%BF%E3%81%AE%E9%80%9A%E7%9F%A5 h_01JQ667RAW48YQ64VXW899EW3X=slack-notification" />

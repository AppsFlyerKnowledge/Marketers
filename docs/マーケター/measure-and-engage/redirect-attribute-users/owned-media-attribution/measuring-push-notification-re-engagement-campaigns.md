---
title: プッシュ通知の測定によるリエンゲージメントキャンペーンの測定
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2026-10-14T09:36:08Z'
  id: 207364076
  locale: ja
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ja/articles/207364076
---
> **概要：** 概要： iOSとAndroidの両方でプッシュ通知キャンペーンを計測します。

## 概要

AppsFlyerは、すべてのプッシュ通知プロバイダーからのプッシュ通知キャンペーンの計測と、Firebase Cloud Messaging または Apple Push Notification Services (APNS) の上に直接実装されたキャンペーンの計測をサポートしています。

連携を実装するには、次の2つの方法があります：

* プッシュ通知のペイロードにキーを持つ `af`afaf JSONオブジェクトを送信する（旧来の方法）

コンバージョンは、オーバービューダッシュボードのリターゲティング、または統合ビューで表示されます。

## 仕組み

この記事の手順を完了すると、アプリは次のように動作します：

2. アプリユーザーはプッシュ通知を受信し、それをクリックします。
3. アプリが読み込まれ、AppsFlyer SDK が起動します。
4. SDKが、アプリを開いたプッシュ通知のペイロードを処理します。
5. SDKが、アトリビューションデータを抽出し、AppsFlyerに送信します。

OneLinkに、アプリ内の特定の画面にユーザーをルーティングするように設定されている場合、ディープリンクフローがトリガーされます。

## 前提条件

続行する前に、アプリに <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide">AppsFlyer SDKが実装</Anchor>されており、<strong>かつ、</strong>プッシュ通知を受信できることを確認してください。

## ステップ

プッシュ通知の計測を設定するには、次の手順を完了する必要があります：

1. OneLinkテンプレートを含むカスタムデータキー、[または、](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification)**af**値として JSON オブジェクトを含むキーを含む`af`プッシュ通知を作成afします。
2. [カスタムキーを解決するようにSDKを構成](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk)します（アプリ開発者が実行）。
3. プッシュ通知をトリガーして[実装テスト](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration)します。
4. ダッシュボードで[プッシュ通知キャンペーンのパフォーマンスを表示](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard)します。

<div id="1-creating-the-push-notification" />

<Accordion title="1.1. プッシュ通知の作成">

まず、次のいずれかの方法を使用して、アトリビューションデータを含むプッシュ通知を作成します。

> 📘 **注意**
>
> 次のデモでは、Firebase をプッシュ通知プロバイダーとして使用しています。この手順は、すべてのプッシュ通知プロバイダーに適用でき、わずかな違い（存在する場合）がある必要があります。以下に記述されているそれぞれのプッシュ通知プロバイダーのドキュメントを参照してください。

<Tabs>
<Tab title="OneLinkの使用（推奨）">

#### **OneLinkの使用（推奨）**

AppsFlyerをプッシュ通知と連携するために推奨される方法です。

1. <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">OneLinkカスタムリンクを作成し、リターゲティング計測用に設定</Anchor>します。  
   　**注：** 注： OneLinkショートURLとロングURLの両方がサポートされています。
2. プッシュ通知のカスタムデータに、AppsFlyerに送信するアトリビューションデータを含む OneLinkを追加します。

> 📄 **Firebaseの例**
>
> Firebase管理画面：
>
> [![appsflyer-push-custom-data-firebase.png](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)

</Tab>

<Tab title="JSONの使用（旧来の方法）">

<div id="using-json-legacy" />

#### **JSONの使用（旧来の方法）**

> 📘 **注意**
>
> 以下は、AppsFlyer をプッシュ通知と連携する従来の方法を文書化したもので、下位互換性の目的で利用できます。[新しいアプリをセットアップする場合は、推奨されるOneLinkベースのソリューションを使用してください。](/docs/measuring-push-notification-re-engagement-campaigns#onelinkの使用推奨)

プッシュ通知のカスタムデータに、JSON形式で AppsFlyerに送信するアトリビューションデータを含むカスタム `af`afaf キーを追加します。次のアトリビューションパラメータは必須です：

* `pid`
* `is_retargeting`
* `c`

> 📄 **Firebaseの例**
>
> Firebase管理画面：
>
> [![appsflyer-push-custom-data-firebase-json.png](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)

</Tab>
</Tabs>

</Accordion>

<div id="2-configuring-the-sdk" />

<Accordion title="2.2. SDK の設定">

このタスクでは、アプリコードを変更する必要があります。SDKの設定方法に関する指示に従ってください：

* [推奨] OneLinkベースのソリューションを実装する場合：
  1. プッシュ通知に追加したカスタムキーの名前をアプリ開発者に知らせます。
  2. 開発担当者にこちらの手順を渡し、開発依頼してください。
* 従来の JSONベースのソリューションを実装する場合は、開発担当者に これらの手順を渡してください。

</Accordion>

<div id="3-testing-the-integration" />

<Accordion title="3.連携のテスト">

プッシュ通知の計測が正しく連携されていることをテストするには、手順 1 で設定したキャンペーンでプッシュ通知をトリガーするだけです。

すべてが正しく構成されている場合、SDKは次のことを行います：

1. プッシュ通知を聞きにいきます。
2. プッシュ通知に埋め込まれたアトリビューションデータを処理し、AppsFlyerに送信します。
3. OneLinkを使用してプッシュ通知の計測が実装されている場合は、通常のディープリンクフローに進みます。

</Accordion>

<div id="4-viewing-push-notification-campaigns-in-the-dashboard" />

<Accordion title="4. 4. ダッシュボードでのプッシュ通知キャンペーンの表示">

プッシュ通知から発信されたデータは、 <Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#retargeting-dashboard">リターゲティングダッシュボード</Anchor>で確認できます。

**注：** 注：AppsFlyer はプッシュ通知データの重複を排除します。つまり、同一のペイロードが複数回受信された場合、カウントされるのは 1つだけです。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01J5XFSEG9DR31DP73KTAGQPFW=%E6%A6%82%E8%A6%81 how-does-it-work=%E4%BB%95%E7%B5%84%E3%81%BF h_01J5XFSEG967HXNT3GFSC2AQYE=%E4%BB%95%E7%B5%84%E3%81%BF prerequisites=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 h_01J5XFSEG91SER3JKB3RKK6B6G=%E5%89%8D%E6%8F%90%E6%9D%A1%E4%BB%B6 steps=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97 h_01J5XFSEG9W3RTP62NW7SV4D0F=%E3%82%B9%E3%83%86%E3%83%83%E3%83%97 h_01J5XFSEG9PXHTD4C9XCDC01DH=1-creating-the-push-notification h_01J5XFSEG9C2C1Z8HK4R1V03H1=%E6%B3%A8%E6%84%8F using-onelink-recommended=onelink%E3%81%AE%E4%BD%BF%E7%94%A8%E6%8E%A8%E5%A5%A8 h_01J5XFSEG9W73JYPHH9VRZSTZ8=onelink%E3%81%AE%E4%BD%BF%E7%94%A8%E6%8E%A8%E5%A5%A8 h_01J5XFSEG97PMRHV20V1VG0SP4=firebase%E3%81%AE%E4%BE%8B h_01J5XFSEG9V46T6XSG31J4AVET=using-json-legacy h_01J5XFSEG9G7QV4N4JATS8W3MX=%E6%B3%A8%E6%84%8F h_01J5XFSEG9XAQ1KMB088GFK4YS=firebase%E3%81%AE%E4%BE%8B h_01J5XFSEG9GYMKAT27AWTN1WZZ=2-configuring-the-sdk h_01J5XFSEG91NH41QMV9K3S4F18=3-testing-the-integration h_01J5XFSEG904NC72K8MWX9YM06=4-viewing-push-notification-campaigns-in-the-dashboard" />

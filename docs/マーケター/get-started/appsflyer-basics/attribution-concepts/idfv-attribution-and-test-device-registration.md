---
title: IDFVによるアトリビューションとテストデバイスの登録
metadata:
  keywords:
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
  created_at: '2023-08-15T13:44:35Z'
  edited_at: '2026-10-28T09:07:53Z'
  id: 17798709514001
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/17798709514001
---
> **At a glance:** IDFVは、同じベンダーのアプリに対してiOSが割り当てる一意の識別子です。クロスプロモーションキャンペーン経由のインストールの計測や、テストデバイスの登録に使用できます。

IDFV（Identifier for Vendor）は、そのベンダーの最初のアプリをインストールした際にiOSが生成する一意の識別子です。同じデバイスに同じベンダーの別のアプリをインストールすると、同じIDFVが割り当てられます。そのベンダーのアプリをデバイスからすべて削除すると、IDFVも削除されます。その後、同じベンダーのアプリを再度インストールすると、異なるIDFVが生成されます。

Appleは、次のように説明しています。「ベンダー向けID（IDFV）は、同じコンテンツプロバイダーのアプリ間での分析に使用できます。この場合、[ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/)フレームワークを使用する必要はありません。 IDFVを他のデータと組み合わせて、他社が所有するアプリやWebサイトを横断してユーザーを追跡することはできません。 IDFVの収集と使用が適用法に準拠していることを確認する責任は、全面的にお客様にあります。」

AppsFlyerでは、IDFVを以下の用途に使用できます。

* [クロスプロモーションのアトリビューション](/docs/idfv-attribution-and-test-device-registration#クロスプロモーションのアトリビューションでのidfvの利用)
* [テストデバイスの登録](/docs/idfv-attribution-and-test-device-registration#テストデバイスの登録でのidfvの利用)

## クロスプロモーションのアトリビューションでのIDFVの利用

クロスプロモーションのアトリビューションでは、IDFVを照合に使用できます。この場合、自社が所有するアプリ内でユーザーに広告を表示します。その広告では、同じく自社が所有する別のアプリを宣伝します。

<div id="how-does-crosspromotion-attribution-using-idfv-work" />

<Accordion title="IDFVを使用したクロスプロモーションのアトリビューションの仕組み">

1. ベンダーのアプリ内に、プロモーション対象アプリの広告が表示されます。 プロモーション対象アプリも、同じベンダーが所有しています。
2. 広告のクリックや閲覧が発生すると、SDKは該当のクリックまたはインプレッションイベントをAppsFlyerに通知します。 SDKは、**広告を掲載する**アプリのIDFVをイベントに紐付けます。このIDFVは、そのアプリの初回起動時にSDKが自動収集したものです。
3. プロモーション対象アプリがインストールされて起動されると、SDKはインストールイベントをAppsFlyerに通知します。このイベントには、**プロモーション対象**アプリのIDFVが含まれます。
4. AppsFlyerはインストールイベントを受信すると、該当するクリックまたはインプレッションとの照合を試みます。両方のイベントのIDFVが一致すれば、インストールイベントをクロスプロモーションキャンペーンに紐付けます。

</Accordion>

<div id="a-few-examples-of-idfv-attribution" />

<Accordion title="IDFVを使用したクロスプロモーションの計測例">

以下のようなケースで、クロスプロモーションのアトリビューションにIDFVの照合を使用します。

* **自社のメール・SMSキャンペーン：** プロモーション対象アプリと同じベンダーが所有する、他のアプリのユーザーにメールやSMSを送信します。メッセージには、元のベンダーアプリのインストールイベントから収集したIDFVを含む計測リンクを設定します。 AppsFlyerは、そのIDFVと、プロモーション対象アプリのインストールイベントに含まれるIDFVを照合します。
* **プッシュ通知キャンペーン：** プロモーション対象アプリと同じベンダーのアプリのSDKが配信するプッシュ通知に、IDFVを含む計測リンクを設定します。 AppsFlyerは、プッシュ通知に含まれるIDFVと、プロモーション対象アプリのインストールイベントのIDFVを照合します。

</Accordion>

## テストデバイスの登録でのIDFVの利用

広告主はAppsFlyerの導入時にテストを実施し、アプリがインストールイベントを正しく記録・送信できることを確認します。 IDFVは、AppsFlyerがテストに使用するデバイスを認識するための一意の識別子として機能します。

<div id="why-identify-devices-as-test-devices" />

<Accordion title="テストデバイスとして識別する理由">

AppsFlyerは、同じアプリを複数回インストールできるように、テストデバイスからのインストールイベントを通常と異なる方法で処理します。連携テストでは、多くの場合、この対応が必要になります。 AppsFlyerがこれらのイベントをテストデバイスからのものと認識できるよう、**ユーザーアカウント**メニューから開く**テストデバイス**ページに、テストデバイスのIDFVを登録します。

</Accordion>

<div id="why-use-idfv-as-an-identifier-in-test-device-registration" />

<Accordion title="テストデバイスの登録にIDFVを使用する理由">

テストデバイスはIDFAでも登録できます。ただし、アプリにApp Tracking Transparency（ATT）を実装していない場合や、ユーザーが個人データの共有に同意していない場合、iOSアプリはIDFAにアクセスできません。この場合、IDFVはATTに依存しないため、IDFVを使用してテストデバイスを識別できます。

</Accordion>

> 📄 **関連情報**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/cross-promotion-attribution-for-marketers">マーケター向けクロスプロモーションのアトリビューション</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices#idfvでデバイスを登録する方法">IDFVを使用したテストデバイスの登録方法</Anchor>

<div data-zendesk-anchors="idfv-in-crosspromotion-attribution=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A7%E3%81%AEidfv%E3%81%AE%E5%88%A9%E7%94%A8 h_01H9041HQ7H18541W83A72B85B=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%A7%E3%81%AEidfv%E3%81%AE%E5%88%A9%E7%94%A8 h_01H9041HQ7JE11FTWTD0XYQWRS=how-does-crosspromotion-attribution-using-idfv-work a-few-examples-of-idfv-attribution%E2%80%A6=a-few-examples-of-idfv-attribution h_01H9041HQ7YDCTJQYBYDVJZPW0=a-few-examples-of-idfv-attribution idfv-for-test-device-registration=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E7%99%BB%E9%8C%B2%E3%81%A7%E3%81%AEidfv%E3%81%AE%E5%88%A9%E7%94%A8 h_01H9041HQ8ZC679PX7HWRMG1YC=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E7%99%BB%E9%8C%B2%E3%81%A7%E3%81%AEidfv%E3%81%AE%E5%88%A9%E7%94%A8 h_01H9041HQ8K76JD72VR4EXCEZB=why-identify-devices-as-test-devices h_01H9041HQ8WS1GEAY6RGV10PF5=why-use-idfv-as-an-identifier-in-test-device-registration h_01HG809S72YC5W61GGN0CE6TP1=%E9%96%A2%E9%80%A3%E6%83%85%E5%A0%B1" />

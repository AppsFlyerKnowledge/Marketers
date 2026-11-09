---
title: お知らせ：iOS ROI360レシート検証におけるApp Store認証情報の更新
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-08-28T09:24:00Z'
  edited_at: '2026-10-14T09:24:50Z'
  id: 27880822483985
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/27880822483985
---
| **更新情報** | 本日以降、AppsFlyerはAppleの新しいアプリ内購入検証APIに移行します。現在のAPIはAppleによって非推奨となっています。  <br />アプリのiOS収益データが正確かつリアルタイムで検証され続けることを保証するために、AppsFlyer管理画面でApp Store Connectの資格情報を更新する必要があります。  <br />アプリでまだApple Server Notificationsバージョン1を使用している場合は、認証情報を更新する前にバージョン2の通知に切り替える必要もあります。 |
| --- | --- |
| **更新日** | 02/04/2025 |
| **更新内容** | この変更は、iOSのアプリ内購入とサブスクリプション収益の検証にROI360を使用しているアプリに影響します。<br />新しいiOS検証フローにアップグレードすることで、次のメリットを得られます：<ul><li>新しいAppleのエンドポイントを使用したApple Storeでのリアルタイム検証の強化。</li><li>アプリ内イベントの構成やパラメーターに変更はありません。</li><li>AppsFlyer Purchase SDK Connectorの検証結果の応答が更新されました。これには、失敗した検証の新しいコード `store_status` も含まれています。</li><li>SDKの実装を変更する必要はありません。</li></ul>**注意：** StoreKit 2に基づくレシート検証は、新しいApp Storeの資格情報でのみサポートされています。アプリがStoreKit 2を使用している場合は、継続的な検証を確保するために更新を完了してください。<br /><br />Appleはいつでも古いAPIを廃止する可能性があるため、潜在的な中断を回避するために、資格情報を更新することを強くお勧めします。 |
| **必要な対応** | 設定を完了するには：<ol><li>App Store Connectから新しいアプリ内購入キーを生成してください。</li><li>AppsFlyerプラットフォームの収益設定セクションに新しいキーをアップロードしてください。</li></ol>アプリで Apple Server Notifications バージョン1を使用している場合は、認証情報を更新する前に バージョン 2 に切り替える必要があります。これが前提条件としてアプリに適用される場合、収益設定画面にメッセージが表示されます。<br /><br />以下の詳細な手順に従ってください：<ul><li>[ROI360 iOSレシート検証におけるApp Store認証情報の更新](#get-ios-credentials)</li><li>[Apple Server Notificationsのバージョン2の設定](#send-app-store-notifications-directly-to-appsflyer)</li></ul> |

<div id="send-app-store-notifications-directly-to-appsflyer" />

<Accordion title="Apple Server Notificationsのバージョン2の設定">

アプリでApple Server Notificationsバージョン1を以前使用していた場合は、検証認証情報を更新する前に、App Store Connectでバージョン2に切り替える必要があります。これが前提条件としてアプリに適用される場合、**収益設定**画面にメッセージが表示されます。

**Apple Server Notificationsのバージョン2の設定：**

1. **App Store Connect**の **App Information** セクションで、**App Store Server Notifications**までスクロールします。

   <Image align="center" alt="image__9_.png" src="https://files.readme.io/8e9c92cdf87303b58a6b604640b4f7adb3cf56c03e57df053e9d486b89345547-33812520143505.png" width="2009px" />
2. **Production Server URL** で、**Edit** をクリックします。
3. **Production Server URL** ボックスのURLは変更しないでください。

   <Image align="center" alt="image__9_.png" src="https://files.readme.io/fc7737793f2e7982e3e92d30dec45d7def98ef8ec6c3186ebbdf32a78f217a3d-33812683240977.png" width="1182px" />
4. **Notification Version** で、**Version 2 Notifications** を選択します。
5. **Save**をクリックしてください。
6. **App Store Server Notifications** セクションで、**Sandbox Server URL** の **Edit** をクリックします。
7. ステップ3&#126;5を繰り返します。

</Accordion>

<div id="get-ios-credentials" />

<Accordion title="ROI360のレシート検証におけるApp Storeの認証情報を更新する">

iOSのアプリ内購入API連携に必要な認証情報は次のとおりです：

* アプリ内購入キー
* キーID
* 発行者ID

**はじめる前に：**

* キーの更新には、App Store ConnectとAppsFlyerの両方で手順を実行する必要があります。設定中は、App Store ConnectとAppsFlyerの両方のタブを開いたままにしてください。
* AppsFlyerでキーを設定するには、管理者権限が必要です。

**iOS認証情報の更新：**

1. App Store Connectで、**Users and Access**へアクセスします。<Image alt="" src="https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png" width="486px" />
2. **Users and Access** > **Integration**を開き、**Keys**リストから**In-App Purchase**を選択します。  
   <Image align="center" alt="" src="https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png" width="532px" />
3. + をクリックして、新しいアプリ内購入キーを生成します。  
   <Image align="center" alt="" src="https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png" width="384px" />
4. APIキーの名前を入力します。
5. **Generate** をクリックします。
6. 先ほど生成したキーの横にある **Download In-App Purchase Key** をクリックして、ダウンロードします。　**注：** キーは一度しかダウンロードできません。
7. AppsFlyer管理画面 左メニュー **設定** > 収益設定 へアクセスします。
8. リストから対象のアプリを選択します。
9. **購入とサブスクリプション**タブで、**キーの更新**をクリックします。<Image alt="" src="https://files.readme.io/edcb9ef1c24f58b911792e924ca69173c487261e2ef35cf1a21270251c50e586-33405937635601.png" width="549px" />
10. **新しいキー** の **In-App Purchase Key**項目で、**アップロードアイコン** <Image alt="upload-2.png" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="15px" /> をクリックして p8ファイルをアップロードします。
11. App Store Connect で、先ほど生成したキーの**キー ID**をコピーし、AppsFlyerの**キーID**のベーシックレシート検証設定に貼り付けます。
12. App Store Connect で、**Issuer ID** をコピーし、AppsFlyer管理画面「購入とサブスクリプション」タブで**Issuer ID**項目に貼り付けます。　**注：Issuer ID**がページ上部に表示されない場合は、App Store Connect APIキーを（任意のアクセスレベルで）作成します。その後、アプリ内購入キーのページ上部にIssue IDが表示されます。 

    <Image align="center" alt="" src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw" width="474px" />
13. AppsFlyerの購入とサブスクリプションの設定で、**キーの検証**をクリックして、入力したキーが正しいことを確認します。
14. **ファイルを更新** をクリックします。キーが更新されると、アプリはAppleの新しいiOS検証フローに完全に移行します。

</Accordion>

<div data-zendesk-anchors="h_01JP2XAKZABDJYB9ZQS4N3ST4Z=send-app-store-notifications-directly-to-appsflyer h_01J14M3C6WNXPJJQHVWVNFB4GS=get-ios-credentials" />

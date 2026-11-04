---
title: Adobe Experience Platform（AEP）とAppsFlyer Data Lockerの統合
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2023-03-19T06:54:23Z'
  edited_at: '2026-10-14T09:36:05Z'
  id: 13856826626321
  locale: ja
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/ja/articles/13856826626321
---
> **概要：** Adobe Experience Platform（AEP）との統合ソリューションを設定して、ローレベルのイベントデータをAdobeデータレイクに送信します。AEPは、顧客ジャーニーをキャプチャする顧客データプラットフォームであるAdobeが提供する、データを集中管理するすべての顧客のためのデータレイヤーであり、分析を行うことができます。

<div id="overview" />

## 概要

Data Locker—AEPとの連携により、Adobe Experience Platform内でAppsFlyerのデータを使用できます。統合には、リアルタイム顧客データプラットフォーム（RTCDP）に裏打ちされた、すぐに利用可能な（OOTB）コンポーネントが使用されます。AppsFlyerのデータをAdobe Experience Platform（AEP）にアップロードするには、まずData Lockerバケット（GCSとAWS）接続を構成し、次にバケットのデータを既存または新規のデータセットユニットにロードするようにAEPを構成する必要があります。

<div id="setting-up-the-integration" />

## 連携の設定

<span id="prerequisites"></span>**前提条件**：

* <Anchor target="_blank" href="/marketers/ja/docs/data-locker">Data Locker</Anchor>のサブスクリプション
* 管理者権限を持つ<Anchor target="_blank" href="https://business.adobe.com/products/experience-platform/adobe-experience-platform.html">エクスペリエンスプラットフォーム</Anchor>アカウント

連携設定方法：

1. <span id="step-1-aws-create-an-aws-iam-user-with-bucket-access"></span>データロッカーの権限を持つバケットを作成します。<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>ストレージの手順に従ってください。
2. Data Lockerの設定<Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#set-up-data-locker">Data Lockerセットアップ手順</Anchor>に従い、GCSバケットまたはAWSバケットを選択する際に 、 ［ **この接続を**Adobe Experience Platformと互換性のあるものにする］が選択されていることを確認します。
3. AEPでデータロッカースキーマを設定します。
   1. 管理者の資格情報を使用してAEPにログインします。
   2. Adobe XDM[体験イベントクラス](https://experienceleague.adobe.com/docs/experience-platform/xdm/classes/experienceevent.html?lang=en#)を作成します。
   3. AppsFlyerフィールドの新しいフィールドグループを追加します。
   4. 最初のフィールドをAppsFlyerというオブジェクトフィールドとして作成します。  
      これが親フィールドです。作成される他のすべてのフィールドは、このオブジェクトフィールドの子です。
   5. その他のデータロッカースキーマフィールドを追加します。Adobe CJAを使用している場合は、customer\_user\_idをビジネス識別子としてマークします。
4. AEPでバケットソースを設定します。
   1. AEPでバケットコネクタを追加します（Data Lockerで使用したのと同じAWSまたはGCSバケット ） 。
   2. 必要な認証の詳細を入力します。
   3. 「**ソースに接続**」をクリックします。
5. AEPでデータフローを設定します。
   1. **AEP Select data**で、バケットフォルダーリストから関連するAppsFlyer Data Lockerレポートを選択します。
   2. 設定
      * Delimitedとしてのデータ形式。
      * 区切り文字を「,」にします。
      * 圧縮形式はGzip。
   3. **次へ**をクリックしてください。
   4. 「**データフローの詳細**」で、データセットとデータフローの詳細を入力します。
   5. **次へ**をクリックしてください。
   6. 「<strong>スケジュール」</strong>で、頻度を60分に設定します。
   7. 必要なデータロッカーレポートごとに繰り返します。

<div id="see-also" />

> 📄 **参照：**
>
> * Adobe Launch SDK 拡張機能
> * <Anchor target="_blank" href="/marketers/ja/docs/adobe-air-plugin?query=adobe">Adobe Airプラグイン</Anchor>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HDNYXDFCQQBNBB6ZQQTJS189=%E6%A6%82%E8%A6%81 setting-up-the-integration=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDNYXDFCEVVDS5RANQMP6K3G=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HDNZ1AS5YTK6N26PD7S7C0XF=%E5%8F%82%E7%85%A7" />

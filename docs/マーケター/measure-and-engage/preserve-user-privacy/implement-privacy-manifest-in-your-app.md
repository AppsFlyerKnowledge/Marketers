---
title: プライバシーマニフェスト
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2024-01-15T10:17:30Z'
  edited_at: '2026-10-14T09:37:29Z'
  id: 21677433322641
  locale: ja
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ja/articles/21677433322641
---
> **概要：** WWDC23 で、Apple は新しいプライバシーマニフェストを導入しました。プライバシーマニフェストを使用すると、アプリ開発者はアプリのプライバシー慣行についてより正確な説明を提供できるようになります。AppsFlyer は、AppsFlyer SDK 用のプライバシーマニフェストを作成しました。詳細は以下で説明します。

<div id="background" />

## 背景

プライバシーマニフェストを使用すると、アプリ開発者は、アプリを通じて個別に収集し、アプリで使用されるサードパーティのSDKなどのサードパーティの依存関係を使用して収集するデータのカテゴリの記録を作成できます。この情報は、アプリ開発者がユーザーに提供するNutrition Labelsなどを通じて、アプリのプライバシー慣行を正確に表現するのに役立ちます。

多くの場合、アプリ開発者は、サードパーティのSDKがどのようなデータを収集しているか、または特定のSDKが何にデータを使用しているかを認識していません。プライバシーマニフェストを使用すると、サードパーティのSDKがこの情報をアプリ開発者に簡単に渡し、正確な情報を作成できるようになります。

<div id="what-are-nutrition-labels" />

### Privacy Nutrition Lablesとは何ですか？

Nutrition Labels は、アプリのプライバシー慣行に関する情報を読みやすく理解しやすい形式で提供します。エンドユーザーは、アプリがどのようなデータを収集し、どのような目的で収集しているかについて、より透明性を高めることができます。Nutrition Labels の詳細については、<Anchor target="_blank" href="/marketers/ja/docs/preparing-for-the-app-store-review-nutrition-labels">こちら</Anchor>をご覧ください。

<div id="what-is-in-the-appsflyer-privacy-manifest" />

## AppsFlyer プライバシー マニフェストには何が含まれていますか?

<div id="important" />

> 🚧 **重要！**
>
> AppsFlyer SDK に加えて、独自のデータ収集、必須理由 API、アプリまたは他の SDK での使用状況を決定し、その情報を Nutrition Labels に報告する必要があります。

AppsFlyer SDK 6.14.0 には、AppsFlyer プライバシーマニフェストが含まれています。これには以下が含まれます：

* [データ使用状況](#データ使用状況)
* [必須理由 API](#必須理由-api)
* [トラッキングドメイン](#トラッキングドメイン)

<div id="data-usage" />

### データ使用状況

Apple は、アプリおよび SDK 開発者に、アプリまたはサードパーティの SDK が収集するデータのカテゴリと理由を記録することを義務付けています。

アプリ開発者は、Xcode を使用して、収集されたデータに関する情報をまとめたプライバシーレポートを作成できます。

以下は、プライバシーマニフェストに含まれる、AppsFlyer SDK によって収集されるデータタイプです。

<div id="note" />

> 📘 **注意**
>
> 次の表は、AppsFlyerソフトウェアのデフォルト実装を前提としています。アプリ開発者は、AppsFlyer SDK の特定の構成と使用状況に応じて、独自のマニフェストを適切に調整する責任があります。

| 名前 | NSPrivacyCollectedDataType | NSPrivacyCollectedDataTypeLinked | NSPrivacyCollectedDataTypeTracking | NSPrivacyCollectedDataTypePurposes |
| --- | --- | --- | --- | --- |
| デバイス ID (IDFA、IDFV) | NSPrivacyCollectedDataTypeDeviceID | はい | はい | NSPrivacyCollectedDataTypePurposeThirdPartyAdvertising |
| 製品のインタラクション（発売） | NSPrivacyCollectedDataTypeProductInteraction | いいえ | いいえ | NSPrivacyCollectedDataTypePurposeAnalytics |

<div id="required-reason-apis" />

### 必須理由 API

Apple は、使用の根拠を示す必要がある API のリストを提供しました。これらの API を使用するアプリと SDK では、プライバシーマニフェストの必須理由 API セクションに詳細を記載する必要があります。これらの API は、<Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api?language=objc">Apple のトピックのリスト</Anchor>に従って、機能と提供される情報に基づいてカテゴリに分類されます。これらは、AppsFlyer SDK バージョン 6.14.0 プライバシーマニフェストに含まれる API です。

* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">File Timestamp APIs</Anchor>
* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">User defaults APIs</Anchor>

Required Reason API の使用方法を明確にするために、アプリ開発者は API カテゴリを宣言し、API を使用する理由を指定する必要があります。以下は、AppsFlyer API とその使用方法です。

<div id="sdk-version-6140-and-above" />

<Accordion title="SDK バージョン 6.14.0 以上">

| API カテゴリ | API カテゴリタイプ | 理由 | 備考 |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">File Timestamp APIs</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | SDK では、 NSFileCreationDate API と<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileModificationDate</Anchor> API を使用して、アプリのインストール日とアプリの更新日を決定します。 |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">User defaults APIs</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | SDK には、その操作に必要なデータが格納されます。例：アプリが起動された回数のメンテナンスなど |

</Accordion>

<div id="sdk-versions-6130-and-earlier" />

<Accordion title="SDK バージョン 6.13.x 以前">

| API カテゴリ | API カテゴリタイプ | 理由 | 備考 |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">File Timestamp APIs</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | SDK では、 NSFileCreationDate API と<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileModificationDate</Anchor> API を使用して、アプリのインストール日とアプリの更新日を決定します。 |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278394">System boot time APIs</Anchor> | NSPrivacyAccessedAPICategorySystemBootTime | 35F9.1 | SDK のパフォーマンス（リクエストの実行にかかった時間など）を測定 |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">User defaults APIs</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | SDK には、その操作に必要なデータが格納されます。例：アプリが起動された回数のメンテナンスなど |

便宜上、上記の必須理由を含む以下のコードスニペットをコピーして、PrivacyInfo.xcprivacy ファイル内に貼り付けることができます。

```xml
<key>NSPrivacyAccessedAPITypes</key>
<array>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>CA92.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryUserDefaults</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>C617.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryFileTimestamp</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>35F9.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategorySystemBootTime</string>
    </dict>
</array>
```

</Accordion>

<div id="tracking-domains" />

### トラッキングドメイン

アプリまたはサードパーティの SDK で使用されるトラッキングドメインはすべて、プライバシーマニフェストに記録する必要があります。ユーザーが App Tracking Transparency (ATT) フレームワークを通じて許可を付与しない (オプトアウトする) 場合、iOS オペレーティングシステムはそのドメインへのすべての送信トラフィックをブロックします。AppsFlyer SDK は、サーバーリクエストの前にユーザーの ATT ステータスを確認し、ユーザーがオプトインしたかどうかに基づいてリクエストを実行します。

<div id="faq" />

## よくある質問

<div id="do-i-have-to-update-my-appsflyer-sdk" />

<Accordion title="AppsFlyer にはプライバシーマニフェストをサポートする SDK がありますか?">

はい、バージョン 6.14.0 以降、SDK はプライバシーマニフェストを完全にサポートしています。

</Accordion>

<div id="do-i-have-to-report-my-own-data-collection" />

<Accordion title="自分でデータ収集内容をレポートする必要がありますか？">

はい、AppsFlyer またはその他の SDK に加えて、独自のデータ収集と使用方法を決定し、デフォルトの AppsFlyer SDK 構成に加えられた構成変更 (アプリ内イベントの計測など) を含め、その情報を Nutrition Labels に報告する必要があります。

</Accordion>

<div data-zendesk-anchors="background=%E8%83%8C%E6%99%AF h_01HCY4D9EKHYB5B3YNWRCB53F4=%E8%83%8C%E6%99%AF what-are-nutrition-labels=privacy-nutrition-lables%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B h_01HCY4ZASEAR69RT3YMHMSE4NP=privacy-nutrition-lables%E3%81%A8%E3%81%AF%E4%BD%95%E3%81%A7%E3%81%99%E3%81%8B what-to-consider-when-getting-your-app-ready-to-ios17=appsflyer-%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC-%E3%83%9E%E3%83%8B%E3%83%95%E3%82%A7%E3%82%B9%E3%83%88%E3%81%AB%E3%81%AF%E4%BD%95%E3%81%8C%E5%90%AB%E3%81%BE%E3%82%8C%E3%81%A6%E3%81%84%E3%81%BE%E3%81%99%E3%81%8B h_01HCY4D9EKTKB50BSZD7RBMMYB=appsflyer-%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC-%E3%83%9E%E3%83%8B%E3%83%95%E3%82%A7%E3%82%B9%E3%83%88%E3%81%AB%E3%81%AF%E4%BD%95%E3%81%8C%E5%90%AB%E3%81%BE%E3%82%8C%E3%81%A6%E3%81%84%E3%81%BE%E3%81%99%E3%81%8B h_01HQ5C9WGW669HBWSG4WQMJTGP=%E9%87%8D%E8%A6%81 data-usage=%E3%83%87%E3%83%BC%E3%82%BF%E4%BD%BF%E7%94%A8%E7%8A%B6%E6%B3%81 h_01HQ03P71BG159MCE3VQY4GTMH=%E3%83%87%E3%83%BC%E3%82%BF%E4%BD%BF%E7%94%A8%E7%8A%B6%E6%B3%81 h_01HT9QHRQSKDQ8GR17N7X5QB8N=%E6%B3%A8%E6%84%8F required-reason-apis=%E5%BF%85%E9%A0%88%E7%90%86%E7%94%B1-api h_01HQ03NV880VHFTXQDE8R6ZRZH=%E5%BF%85%E9%A0%88%E7%90%86%E7%94%B1-api h_01HSZSWW6Y91BTY1GNXMMVJCEQ=sdk-version-6140-and-above h_01HT9QVD9KZVN7RXWP03XCH8JZ=sdk-versions-6130-and-earlier required-reasons-api=%E3%83%88%E3%83%A9%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01HQ03NV88SJPYKBM66S7X6GP8=%E3%83%88%E3%83%A9%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F 01HQQXSN96D4QTTYHG8CBE8695=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HCY5XRA96XAYYGB4XCZ8EXXG=do-i-have-to-update-my-appsflyer-sdk h_01HDDQV25KC9XWF7CJ7QBH4XW2=do-i-have-to-report-my-own-data-collection" />

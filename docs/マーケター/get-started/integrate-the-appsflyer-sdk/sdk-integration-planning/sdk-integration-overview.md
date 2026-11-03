---
title: SDK実装の概要
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2026-10-28T09:09:40Z'
  id: 207032126
  locale: ja
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ja/articles/207032126
---
> **At a glance:** AppsFlyer SDKで利用できる機能を確認し、AndroidまたはiOSアプリに実装するAPIを検討します。

## SDKについて

SDK実装の全体像については、こちらの動画をご覧ください。

<Embed title="SDK実装の概要" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

SDKには、アプリのインストールやイベントを記録する機能があります。インストール、セッション、アプリ内イベントを記録できます。アプリ内イベントには、アプリ内課金やゲームでのレベルアップなどがあります。これらのイベントを記録することで、ROIやユーザーの質を評価できます。

この記事では、SDK V6以降の実装手順を説明し、広告主（アプリ所有者）やプロダクトマネージャーがAndroidまたはiOSアプリへのAppsFlyer SDK実装を計画する際に役立つ情報を紹介します。

関連ドキュメントは以下のとおりです。

<Tabs>
<Tab title="Androidネイティブ">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">開発者向けSDKインストールガイド</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-android-sdk-release-notes">リリースノート</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference">開発者向けSDKリファレンス</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/fill-out-google-safety-section-form">Google Playのデータセーフティセクション</Anchor>

</Tab>

<Tab title="iOSネイティブ">

* <Anchor target="_blank" href="/marketers/ja/docs/updating-to-ios-sdk-v6-and-plugins">iOS SDK V6へのアップデート</Anchor> iOS SDK V5.4.4は、iOS 14でも問題なく動作します。ただし、今後のiOSリリースとの互換性を確保するため、SDK V6.Xの導入を推奨します。
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">開発者向けSDKインストールガイド</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">リリースノート</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">開発者向けSDKリファレンス</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/preparing-for-the-app-store-review-nutrition-labels">App Store審査への準備：プライバシーに関する情報の表示</Anchor>

</Tab>

<Tab title="Unity">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">開発者向けSDKインストールガイド</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">開発者向けSDKリファレンス</Anchor>

</Tab>

<Tab title="React Native">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">開発者向けSDKインストールガイド</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">開発者向けSDKリファレンス</Anchor>

</Tab>
</Tabs>

## SDKの互換性

AppsFlyer SDKは、以下のプラットフォームに対応しています。

<Tabs>
<Tab title="Android">

* Android V4.0以降
* スマートテレビ（Amazon Fire TVを含む）など、モバイル端末以外のAndroidベースのプラットフォーム。 <Anchor target="_blank" href="/marketers/ja/docs/ctv-pc-and-console-platform-attribution-concepts">CTVの概要を見る</Anchor>
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-multi-store-android-attribution">AmazonやBaiduなど、Androidアプリ向けのGoogle Play以外のアプリストア</Anchor>

</Tab>

<Tab title="iOS">

* iOS 9以降（iPhone、iPod、iPad）
* tvOS 9以降（Apple TV）
* Appleの<Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">IPv6 DNS64/NAT64</Anchor>ネットワークに対応

SDKは複数のアトリビューション方式に対応しています。<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model">複数のアトリビューション方式</Anchor>使用するアトリビューション方式は、以下の条件によって異なります。

* ユーザーの端末にインストールされているiOSのバージョン
* アプリに実装されているiOS SDKのバージョン

<table><thead><tr><th>対応するアトリビューション方式</th><th>iOSバージョン</th><th>対応するiOS SDK</th><th>注意事項</th></tr></thead><tbody><tr><td rowspan="2">確率論的モデリング</td><td>8 – 14.4</td><td>5.0.0+</td><td> </td></tr><tr><td>14.5+</td><td>6.0.3+</td><td>確率論的モデリングの利用は、オウンドメディア、クロスプロモーション、ユーザーの同意を得たWeb-to-Appフローに限定されます。</td></tr><tr><td rowspan="2">IDマッチング<br/><br/> </td><td>8 - 13</td><td>5.0.0+</td><td>ユーザーは「追跡型広告を制限」（LAT）でオプトアウトできます。</td></tr><tr><td>14.5+</td><td>6.0.3+</td><td>App Tracking Transparency（ATT）によるユーザーの同意が必要です。詳しくは「<a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">ATTに対応するためのiOS SDKの設定</a>」をご覧ください。</td></tr><tr><td rowspan="2"><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork</a></td><td>11.3 - 13</td><td rowspan="2">6.2.3<br/><br/> </td><td>SKAdNetwork（SKAN）ソリューションは、<a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">SKAN</a>の仕様に従い、インストールのアトリビューションに限定されます。つまり、コンバージョン値は利用できません。</td></tr><tr><td>14+</td><td><ul><li>SKANは、ATTの設定に関係なく、iOSとSDKの両方のレベルで常に利用できます。</li><li>マーケターはAppsFlyer管理画面でSKANを有効にします。</li></ul></td></tr></tbody></table>

SDK V6.0.8以降では、<Anchor target="_blank" href="/marketers/ja/docs/apple-app-clips-integration-guide">Apple App Clipsのアトリビューション</Anchor>を利用できます。 Apple App Clipsについては、こちらの<Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips">ブログ記事</Anchor>もご覧ください。

</Tab>
</Tabs>

## SDK実装

SDKのインストールと実装には、プロダクトマネージャーとモバイルアプリ開発者の連携が必要です。**実装する前に**、実装タスクをすべて確認し、アプリで利用する機能を検討してください。

### SDK実装の計画チェックリスト

計画を進める際に役立つ、<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">ダウンロード可能なチェックリスト</Anchor>を用意しています。各タスクには、マーケター向けおよび開発者向けドキュメントへのリンクがあります。

### SDK実装のタスク

基本SDK実装には、以下のタスクが含まれます。所要時間は一般的な目安です。

| 基本SDK実装のタスク | 計画に必要な時間 |
| --- | --- |
| AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#アプリへのdevキーの組み込み">Dev Key</Anchor>を取得し、インストールと実装の手順とともに開発者へリンクを送ります。 | 15分 |
| <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#アトリビューション">アトリビューションに関する考慮事項</Anchor>を確認し、収集する端末識別子を決定します。 | 30分 |
| 計測する<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#アプリ内イベントの記録">アプリ内イベント</Anchor>を決定し、イベント名とイベントパラメータを開発者に伝えます。 | 1時間 |
| 使用する<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#onelinkによるディープリンク">ディープリンク方式</Anchor>を決定します。 | 30分 |
| <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#アトリビューションデータとディープリンクデータの取得">アトリビューションデータへのアクセス方法</Anchor>を決定します。 | 30分 |
| 基本実装が完了したら、AppsFlyer管理画面へのアクセス権を持つアカウントユーザーは、<Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#sdk実装のテスト">基本的なテスト</Anchor>を実施できます。<br /><br />開発者は、<Anchor target="_blank" href="/marketers/ja/docs/testing-the-sdk-integration-for-marketers#testing-in-the-development-environment">開発環境</Anchor>でデバッグログを利用できます。 | 1時間 |

モバイルアプリ開発者と協力して、SDKに以下の追加APIを実装できます。

| 追加SDK実装のタスク | 計画に必要な時間 |
| --- | --- |
| アプリに<Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#追加のアトリビューション計測方法">追加のアトリビューション設定</Anchor>が必要かどうかを判断します（アンインストール計測やサードパーティのアプリストア経由のインストールアトリビューションなど）。 | 30分 |
| <Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#セッション">ユーザーセッションのレポート方法</Anchor>を決定します。 | 30分 |
| <Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#オウンドメディア">オウンドメディアの流入元</Anchor>に使用するアトリビューション方式を決定します。 | 1時間 |
| アプリがプライバシー規制（GDPR、CCPA）に準拠するよう、<Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#ユーザーのプライバシー">ユーザープライバシー</Anchor>に関するポリシーを管理します。 | 1時間 |

> 📘 **Note**
>
> **関連情報**
>
> * CTV、PC、コンソールプラットフォームの概要

<div data-zendesk-anchors="about-the-sdk=sdk%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01H9FHRVKE6BHGW05G6YMKF737=sdk%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 sdk-compatibility=sdk%E3%81%AE%E4%BA%92%E6%8F%9B%E6%80%A7 h_01H9FHRVKEQ837Q0GFECNPPAN2=sdk%E3%81%AE%E4%BA%92%E6%8F%9B%E6%80%A7 sdk-integration=sdk%E5%AE%9F%E8%A3%85 h_01H9FHRVKEN0MMGTSD362FTWPS=sdk%E5%AE%9F%E8%A3%85 sdk-planning-checklist=sdk%E5%AE%9F%E8%A3%85%E3%81%AE%E8%A8%88%E7%94%BB%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 h_01H9FHRVKE468M1RTMF7VTYV1R=sdk%E5%AE%9F%E8%A3%85%E3%81%AE%E8%A8%88%E7%94%BB%E3%83%81%E3%82%A7%E3%83%83%E3%82%AF%E3%83%AA%E3%82%B9%E3%83%88 sdk-integration-tasks=sdk%E5%AE%9F%E8%A3%85%E3%81%AE%E3%82%BF%E3%82%B9%E3%82%AF h_01H9FHRVKERHXY19R97EN86EGP=sdk%E5%AE%9F%E8%A3%85%E3%81%AE%E3%82%BF%E3%82%B9%E3%82%AF" />

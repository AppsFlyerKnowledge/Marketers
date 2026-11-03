---
title: iOS・Android向け：SDK実装ウィザード
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2024-04-10T12:17:00Z'
  edited_at: '2026-10-20T13:12:40Z'
  id: 24073235369617
  locale: ja
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ja/articles/24073235369617
---
> **At a glance:** SDK実装コードの生成とテストを自動化します。

## SDK実装ウィザードについて

<Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">SDK実装ウィザード</Anchor>を使用すると、アプリ開発者は案内に沿ってSDKの実装を進められます。アプリ開発者が必要な認証情報とカスタマイズ項目を入力するだけで、ウィザードがプロジェクトにコピー＆ペーストできるコードスニペットを生成します。

この記事では、SDK実装ウィザードの各フローで必要となる情報や認証情報を収集し、アプリ開発者に共有する方法を説明します。ウィザードでは、開発者向けに次の2つのフローを用意しています。

* [インストールと実装のフロー](#インストールと実装のフロー)：SDKのインストールから実装のテストが成功するまで、ウィザードが開発者を案内します。
* [アプリ内イベントの追加フロー](#アプリ内イベントの追加フロー)：アプリ内イベントの定義から、AppsFlyerへの送信テストが成功するまで、ウィザードが開発者を案内します。

## インストールと実装のフロー

アプリ開発者が実装ウィザードを使ってインストールと設定を完了すると、AppsFlyer SDKからアトリビューションデータを送信できる状態になります。実装が正常に完了したことを確認するため、このフローには、アプリのインストール時に「インストールイベント」がAppsFlyerへ正しく報告されるかを確認するテストが含まれます。

次の表は、ウィザードの設定時に開発者が回答する必要のある質問をまとめたものです。表の案内に従って必要な情報を収集し、開発者に共有してください。

| 質問 | 詳細 |
| --- | --- |
| アプリIDは何ですか？（必須） | <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#アプリの詳細を入力">各ストアのアプリIDの確認方法</Anchor> |
| AppsFlyerのDev Keyは何ですか？（必須） | <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#devキーの取得">Dev Keyの確認方法</Anchor> |
| どのSDKモードで実装しますか？通常モードと厳格モードのどちらですか？ | <Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#strictmode-sdk">SDKモードについて</Anchor> |
| SDKでコンバージョンデータを取得しますか？ | <Anchor target="_blank" href="/marketers/ja/docs/get-conversion-data-using-appsflyer-sdk-overview">SDKでのコンバージョンデータについて</Anchor> |
| SDKの起動が正常に完了したことを示す確認通知を受け取りますか？ | 完了ハンドラーを使用したSDK起動メソッドについて（[Android](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-with-a-response-listener)、[iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#start-with-completion-handler)） |
| SDKでApp Tracking Transparency（ATT）をサポートしますか？ | <Anchor target="_blank" href="/marketers/ja/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">ATTについて</Anchor> |
| AppsFlyerのv2認証トークンは何ですか？（自動テストのフローを使用する場合のみ必須） | <Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#トークンページを開く">v2トークンの取得方法</Anchor> |

## アプリ内イベントの追加フロー

アプリ開発者がインストールと実装のウィザードを完了すると、AppsFlyer SDKがアプリに正常に実装されます。このフローには、アプリ内イベントのテストが含まれます。原文では、このテストで確認する内容についての記述が不完全です。

次の表は、ウィザードの設定時に開発者が回答する必要のある質問をまとめたものです。表の案内に従って必要な情報を収集し、開発者に共有してください。

| 質問 | 詳細 |
| --- | --- |
| イベント名とイベントパラメータを選択してください。 | <Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#アプリの詳細を入力">利用できる定義済みイベントを確認する</Anchor>各イベントの説明には、一般的なイベントパラメータが記載されています。  <br />また、  <br />[アプリ内イベントジェネレーター](https://evgen.appsflyer.com/)も利用できます。 |
| アプリ内イベントがAppsFlyerに受信されたことを示す確認通知をSDKで受け取りますか？ | AppsFlyerでイベントが正常に受信されたことを確認するコードについて（<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#handling-event-submission-success-and-failure">Android</Anchor>、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#handling-event-submission-success-and-failure">iOS</Anchor>） |
| AppsFlyerのv2認証トークンは何ですか？（自動テストのフローを使用する場合のみ必須） | <Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#トークンページを開く">v2トークンの取得方法</Anchor> |

## 特徴と制限事項

| 項目 | 備考 |
| --- | --- |
| Zeroプラン | SDK実装ウィザードは<Anchor target="_blank" href="/marketers/ja/docs/account-management-plans-payments-and-billing#appsflyer-plans">Zeroプラン</Anchor>では利用できません。 |

<div data-zendesk-anchors="about-the-sdk-integration-wizard=sdk%E5%AE%9F%E8%A3%85%E3%82%A6%E3%82%A3%E3%82%B6%E3%83%BC%E3%83%89%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J6730Y7WE1AJXNXFZ0QX23T8=sdk%E5%AE%9F%E8%A3%85%E3%82%A6%E3%82%A3%E3%82%B6%E3%83%BC%E3%83%89%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 the-installation-and-integration-flow=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E5%AE%9F%E8%A3%85%E3%81%AE%E3%83%95%E3%83%AD%E3%83%BC h_01J5K2A8BZS9CTZA45FB5VX8C0=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%A8%E5%AE%9F%E8%A3%85%E3%81%AE%E3%83%95%E3%83%AD%E3%83%BC the-add-in-app-event-flow=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%BF%BD%E5%8A%A0%E3%83%95%E3%83%AD%E3%83%BC h_01J5K2CG0H1G0BCSWHBJ8DPQWA=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%BF%BD%E5%8A%A0%E3%83%95%E3%83%AD%E3%83%BC traits-and-limitations=%E7%89%B9%E5%BE%B4%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%E7%89%B9%E5%BE%B4%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />

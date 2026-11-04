---
title: Windows SDKの実装テスト
metadata:
  keywords:
    - Testing
    - Windows
    - SDK
    - Advertisers
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
  created_at: '2016-11-15T12:35:48Z'
  edited_at: '2026-10-14T09:30:58Z'
  id: 217924503
  locale: ja
  section: Windows platform
  section_id: 6551223206417
  url: https://support.appsflyer.com/hc/ja/articles/217924503
---
> **概要：** 概要： WindowsアプリのAppsFlyer連携をテストします。

* 現在、Windows App Storeにアプリをアップロードする以外に、Windows Referrerでテストする方法はありません。
* Windowsリファラーを使用してテストする場合は、次の制限事項を理解している必要があります：
  * ストアにログインする必要があります。
  * デバイスに Windows 10 アニバーサリー更新プログラムをインストールしないでください。
  * お使いのデバイスにアプリが搭載されていない必要があります（Windowsのリファラーはライフタイム（永久に有効）です ー 許可リストに登録されているか、90日以上待機している場合でも、リファラーのアトリビューションを受け取ることはできません）。

<div id="test-sdk-integration" />

## SDK連携のテスト

1. SDK実装テストは、ホワイトリストに登録されたテスト端末で行う必要があります。
2. AppsFlyer管理画面を開き、テストするアプリを選択します。
3. 左メニューにある SDK実装テスト を選択してください。
4. テストするための3つの選択肢が表示されます。

* 非オーガニックインストール
* In-app events
* ディープリンク

[![](https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png)](https://files.readme.io/7b2af46dc66530db91c31466b08121673f067ea9188d5bbf7e5f4a4137cbc6e4-115011326025.png)

<div id="testing-non-organic-install" />

## 非オーガニックインストールのテスト

1. ドロップダウンリストから登録済みのデバイスの1つを選択します。
2. アプリをインストールする場所を選択します（Windows ストアまたはその他）
3. ホワイトリスト登録されたテスト端末でQRコードをスキャンし、表示された指示に従ってください。
4. テストが成功したことを示す、SDK実装テストページに非オーガニックインストールが記録されるまで待ちます。これには最大2分程度かかります。この時点までにアプリが非オーガニックインストールを登録しなかった場合は、連携テストページに表示されるトラブルシューティングガイドを参照してください。

<div id="testing-in-app-events" />

## アプリ内イベントのテスト

1. ドロップダウンメニューから予めホワイトリスト登録したテスト端末を選択し、Nextをクリックしてください。
2. アプリを開き、実装したアプリ内イベントを発火させてください。
3. これらのイベントはリアルタイムで記録されるため、イベントログが表示されます。

<div id="testing-deep-linking" />

## ディープリンクのテスト

1. ディープリンクをテストするには、アプリのOneLink設定が完了している必要があります。
2. ドロップダウンメニューから予めホワイトリスト登録したテスト端末を選択し、Nextをクリックしてください。
3. テスト端末に登録した端末でQRコードをスキャンし、表示された指示に従ってください。
4. 連携テストページにディープリンクが正常に登録されるまで待ちます。

<div data-zendesk-anchors="test-sdk-integration=sdk%E9%80%A3%E6%90%BA%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 testing-nonorganic-install=%E9%9D%9E%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 testing-inapp-events=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 testing-deep-linking=%E3%83%87%E3%82%A3%E3%83%BC%E3%83%97%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88" />

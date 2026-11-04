---
title: Apple App Store（itunes）のインストール検証の実装
metadata:
  keywords:
    - Validation
    - iTunes
    - Apple
    - Store Install
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2017-07-02T08:36:31Z'
  edited_at: '2026-10-21T12:37:41Z'
  id: 115003285626
  locale: ja
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ja/articles/115003285626
---
> **概要：** Appleのインストール検証サービスを使用して、オーガニック・非オーガニックを問わず、すべてのiOSインストールを検証し、不正な操作がアトリビューションされるのを防ぎます。

<div id="receipt-validation-flow" />

## レシート検証の流れ

レシート検証は、以下の流れで行われます。

1. AppsFlyer SDKがAppleのインストールレシートデータ（インストールを証明するデータ）を収集し、アプリ起動時の送信データとともにAppsFlyerのサーバーに送信します。
2. AppsFlyerのサーバーは、Appleのインストール検証サービスを通じて、このレシートデータを検証します。
3. Appleのインストール検証サービスから、インストールが無効であることを示すエラーコードが返された場合は、以下の処理が行われます。
   * そのインストールは拒否され、AppsFlyerのダッシュボードには表示されません。
   * 無効と判定されたインストールについては、アドネットワークへのポストバック送信やAPI呼び出しは行われません。
   * そのインストールと、それに関連するすべてのアプリ内イベントは、Protect360のローデータレポート「インストール」と「ブロックされたアプリ内イベント」に記録されます。

<div id="notes" />

> 📘 **注意**
>
> * AppsFlyer iOS SDKは、バージョン6.9.2以降が必要です。
> * インストール検証は、iOS 7以降を搭載したiOSデバイスに対応しています。
> * Appleからインストールのレシートデータが提供されない場合があります。この場合、AppsFlyerは、App Storeのインストール検証ではそのインストールを有効とみなします。ただし、Protect360が他の不正理由に基づいて、そのインストールをブロックすることがあります。

<div data-zendesk-anchors="receipt-validation-flow=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E6%B5%81%E3%82%8C h_01JR7ST09GNZ2NTMP8D2YQ1DCH=%E3%83%AC%E3%82%B7%E3%83%BC%E3%83%88%E6%A4%9C%E8%A8%BC%E3%81%AE%E6%B5%81%E3%82%8C h_01JR7ST09G5QFHFTWK98NCJE97=%E6%B3%A8%E6%84%8F" />

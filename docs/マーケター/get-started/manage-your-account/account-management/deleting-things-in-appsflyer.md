---
title: AppsFlyerでのアプリ・データなどの削除
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
  created_at: '2018-11-21T16:07:58Z'
  edited_at: '2026-10-28T09:13:04Z'
  id: 360000603117
  locale: ja
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/ja/articles/360000603117
---
> **概要：** 広告主が、アプリを削除して計測を停止する方法、メディアソースを削除する方法、ユーザー関連データを削除する方法を説明します。

<Image align="center" alt="shutterstock_699498934.jpg" src="https://files.readme.io/db2cd79f6da6de42042707fb2c8bbfe450a6cdc17a93f7a9dc9ea27d04716ef3-34228068995857.jpg" width="363px" />

<div id="delete-user-history" />

## ユーザーの履歴を削除する

GDPRやCCPAなどのプライバシー規制では、ユーザーに*データの消去を求める権利*が認められています。

**例：** ユーザーから、自分に関連するデータを削除してほしいという依頼がありました。 GDPRでは、30日以内に対応することが求められています。

**必要な対応：** <Anchor target="_blank" href="/marketers/ja/docs/send-opendsr-api-requests">OpenDSR API</Anchor>を使って消去リクエストを送信します。

<div id="stop-attributing-installs-to-a-media-source" />

## メディアソースのインストール計測を停止する

AppsFlyerは、設定されたメディアソースのインストールとイベントの情報を収集します。メディアソースがアトリビューションの対象として設定されている場合、新規インストールが計測されます。

**例：** メディアソースでのキャンペーン配信を停止し、クリック、インプレッション、インストールが発生しなくなると、アトリビューションも停止します。ただし、既存ユーザーのアプリ内イベントは、引き続き記録され、計測元に紐付けられます。

**メディアソースのインストール計測を停止するために必要な対応：**

* **SKAN（iOSアプリの場合）：**
  1. <Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio#disable-skan-measurement">SKAN計測を無効にします</Anchor>。
  2. SKANデータの記録を停止するには、<Anchor target="_blank" href="/marketers/ja/docs/get-skan-postback-data-from-google-ads#turning-off-the-skan-integration">Google広告</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-interoperation-with-meta-ads#turning-off-the-skan-integration">Meta広告</Anchor>では、SKAN連携も解除する必要があります。
* **SRN：** <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#パートナー連携を無効にする">パートナー連携を無効にします</Anchor>。
* **非SRN：**  
  1. <Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#パートナー連携を無効にする">パートナー連携を無効にします</Anchor>。
  2. 広告内のAppsFlyer計測リンク経由のクリックとインストールは、引き続き記録・計測されます。見込みユーザーに表示される広告に、AppsFlyer計測リンクが含まれないようにしてください。
* **自社メディア：**
  * 該当するOneLinkカスタムリンクの使用を停止します。

<div id="remove-or-delete-an-app" />

## アプリの削除

アプリは一時的に削除できます。

<div id="temporarily-removing-an-app" />

#### アプリの一時的な削除

アプリを一時的に削除すると、データの記録が停止してダッシュボードに表示されなくなり、［マイアプリ］ページではグレー表示になります。ただし、アカウントとの紐付けは維持されるため、復元できます。アプリを復元した際には、アプリ設定、承認済み代理店、トークンなどの過去の情報が保持されます。

<div id="note" />

> 📘 **注意**
>
> アプリの削除は、1件ずつ行います。ただし、<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer#api経由でアプリを一括管理">APIを使うと複数のアプリを削除できます</Anchor>。

**アプリを削除するには、次の手順に従います。**

1. 上部のバーで**［マイアプリ］*をクリックします。***
2. アプリの操作メニューを選択します。
3. <strong>［削除］<em>をクリックし、</em></strong>削除を確定します。  
   アプリが削除され、アプリ一覧に表示されなくなります。

**削除したアプリを復元するには、次の手順に従います。**

* 担当CSMに連絡するか、[hello@appsflyer.com](mailto:hello@appsFlyer.com)にメールを送信して、手続きを開始してください。 CSMがアプリを復元すると、アカウントに再追加できます。

<div id="transfer-apps-between-accounts" />

## アカウント間でのアプリの移管

詳細は、<Anchor target="_blank" href="/marketers/ja/docs/transferring-apps-between-accounts">アカウント間でのアプリの移管</Anchor>を参照してください。

<div id="delete-your-account-or-downgrade-your-subscription-plan" />

## アカウントの削除または契約プランのダウングレード

担当CSMに連絡するか、[hello@appsflyer.com](mailto:hello@appsFlyer.com)にメールを送信してください。

<div data-zendesk-anchors="delete-user-history=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E5%B1%A5%E6%AD%B4%E3%82%92%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B h_01HNZ7TNZM4P5APM2B1WQ4X7S5=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E5%B1%A5%E6%AD%B4%E3%82%92%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B stop-attributing-installs-to-a-media-source=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%82%92%E5%81%9C%E6%AD%A2%E3%81%99%E3%82%8B h_01HNZ7VPA16065PGCSZDMQZ3ZC=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC%E3%82%92%E5%81%9C%E6%AD%A2%E3%81%99%E3%82%8B delete-an-app=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E5%89%8A%E9%99%A4 h_01HNZ7XKEFRNEWGQZ58T7H0KDH=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E5%89%8A%E9%99%A4 removing-an-app=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E4%B8%80%E6%99%82%E7%9A%84%E3%81%AA%E5%89%8A%E9%99%A4 h_01J52J31FDKSPNWSD5J2V5BYTW=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E4%B8%80%E6%99%82%E7%9A%84%E3%81%AA%E5%89%8A%E9%99%A4 h_01HYJ5EPX4B1G1SAF6XGZ7ADWZ=%E6%B3%A8%E6%84%8F transfer-apps-between-accounts=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E9%96%93%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E7%A7%BB%E7%AE%A1 h_01HNZ7ZW7ZKDSD2TTEX55PYB91=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E9%96%93%E3%81%A7%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E7%A7%BB%E7%AE%A1 delete-your-account-or-downgrade-your-subscription-plan=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E5%89%8A%E9%99%A4%E3%81%BE%E3%81%9F%E3%81%AF%E5%A5%91%E7%B4%84%E3%83%97%E3%83%A9%E3%83%B3%E3%81%AE%E3%83%80%E3%82%A6%E3%83%B3%E3%82%B0%E3%83%AC%E3%83%BC%E3%83%89 h_01HNZ81GQ8Z6R8DV8Z6SAXYRB9=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E5%89%8A%E9%99%A4%E3%81%BE%E3%81%9F%E3%81%AF%E5%A5%91%E7%B4%84%E3%83%97%E3%83%A9%E3%83%B3%E3%81%AE%E3%83%80%E3%82%A6%E3%83%B3%E3%82%B0%E3%83%AC%E3%83%BC%E3%83%89" />

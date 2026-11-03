---
title: QRコードを使用してアプリインストールを促す
metadata:
  keywords:
    - OneLink
    - Advertisers
    - owned media
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2020-11-04T09:49:23Z'
  edited_at: '2026-10-14T09:31:32Z'
  id: 360015119718
  locale: ja
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ja/articles/360015119718
---
> **概要：** 概要： OneLinkで生成されたQRコードを使用して、デスクトップ、テレビ、CTV、またはオフラインユーザーをストアもしくはモバイルアプリへ誘導します。

![6005_QR_code_4.jpg](https://files.readme.io/6db45d7e82bc33ba8af8c6e7d096011d71b06766da9df348dccfa1b3e4aa380d-12368835107601.jpg)

## モバイル、非モバイル、オフラインのユーザーをモバイルアプリへ誘導する

OneLinkで生成された QRコードを、店舗内のディスプレイ、パンフレット、パッケージなど、デスクトップ、テレビ、CTV、オフラインの広告に投稿することで、次のような利点があります。

* ユーザーは、モバイル端末でQRコードをすばやく簡単にスキャンして、アプリをダウンロードしてインストールできます。
* ユーザーはアプリストアでアプリを検索するのに必要な時間と労力を減らし、デスクトップからアプリインストールへのコンバージョン率を大幅に高めます。
* この転換方法はテキストメッセージなどを送信してユーザーの電話番号などの個人情報を取得する必要がないため、プライバシー保護が可能です。
* インストール数を簡単にアトリビューションし、オウンドメディア施策の効果を測定できます。

QRコードは、次の方法で簡単に作成できます：

* [手動：AppsFlyer管理画面から発行](/docs/qr-to-app-conversion#qrコードの手動設定)
* <Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#qr-codes">OneLink スマートスクリプト</Anchor> Web からアプリへのデスクトップ挙動用に特別に設計されたコードを動的に使用する

<div id="qr-to-app-conversion" />

<Accordion title="QRコードを使用してアプリインストールを促す">

#### QRコードの手動設定

**前提条件：**

* 少なくとも1つのアプリが登録されたAppsFlyerアカウントを持っていること
* アトリビューション計測したい場合： 各モバイルアプリに<Anchor target="_blank" href="/marketers/ja/docs/integrate-the-appsflyer-sdk">AppsFlyer SDKが実装</Anchor>されていること
  * SDKがアプリに実装されていない場合は、リダイレクション用リンクを作成することは可能ですが、ディープリンク、ディファードディープリンク、インストールの計測はできません。

* <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor>が設定されている必要があります。

**QRコードからアプリへのコンバージョン用のQRコードを設定するには**：

1. * 1. [推奨] 新しいリンクを作成し、カスタムメディアソースを設定します。例： **Desktop\_Web**既存リンクからQRコードを取得しても機能します。ただし、レポーティングにおいて、メディアソース名を他のリンクと共有すると計測値が混在してしまうためお勧めしません。＜b代わりに、QRコードもしくはデスクトップ経由のインストールと判別できる、専用のメディアソース名を定義した別のリンクをご利用ください。
     2. **リンクを作成**をクリックすると、QRコードが表示されます。
     3. QRコードをクリックして、SVG または PNG 形式のフル解像度でダウンロードします。
2. 他の画像/コンテンツを追加するのと同じ方法で、QRコードを施策に掲載します。
   * [ベストプラクティス](/docs/qr-to-app-conversion#best-practices)を参照してください。
   * ディベロッパーの作業が必要な場合があります。

</Accordion>

<div id="customize-qr-code" />

<Accordion title="QRコードのカスタマイズ">

OnelinkQRFinal\_\_1\_.gif

OneLink で生成した QR コードを、以下のようにカスタマイズできます。

* QR コードにロゴを追加する
* QR コードの色を変更する。

**注：**

* 注：QRコードのカスタマイズはテンプレートレベルで行われ、個々のリンクレベルでは行われません。そのため、カスタマイズした場合は、編集したテンプレートに基づくすべてのQRコードに影響します。
* スマートスクリプトで作成したQRコードはカスタマイズできません。

**QRコードをカスタマイズする方法**：

1. AppsFlyer管理画面から、**Experience & Deeplinking** > **OneLink**を開きます。
2. QRコードエディターが開きます。
3. ロゴが保存されている URL を入力してください。例：https://yourbrand.com/logo.png  

   ロゴの仕様：

   * PNG または JPG形式
   * 背景が透明な正方形または円形
   * 最小サイズは400 x 400 px
   * 印刷時は最大画像解像度を使用してください
4. QR コードの色を設定してください。
5. **保存**をクリックします。

</Accordion>

<div id="measure-qrtoapp-conversions" />

<Accordion title="QRからアプリへのコンバージョンを計測する">

インプレッション数（デスクトップページビューの場合）、クリック数（QRコードスキャンの場合）、アプリのインストール数を比較することで、QRコードのパフォーマンスとさまざまな広告/メディアソースでのQRコードの配置を測定できます。

**QRからアプリへのコンバージョンを計測するには**：

1. AppsFlyerで、オーバービューダッシュボードまたはその他のAppsFlyer分析ツールを確認し、QRコード用に設定したメディアソース（**Desktop\_Web**など）で合計**クリック**数と**インストール数**を確認します。
2. Webアナリティクスソフトウェアを使用して、デスクトップのページビュー（インプレッション）を記録してください。
3. パフォーマンスを測定してください。
   * <Anchor target="_blank" href="/marketers/ja/docs/about-conversion-rates#マーケティングファネルの各段階とコンバージョン率-1">クリック率（CTR）</Anchor>
   * <Anchor target="_blank" href="/marketers/ja/docs/about-conversion-rates#マーケティングファネルの各段階とコンバージョン率-1">Click-to-install率</Anchor>

</Accordion>

<div id="best-practices" />

<Accordion title="ベストプラクティス">

以下は、QRからアプリへのコンバージョンを最大化するためのヒントです。

* デスクトップの場合、QRコードの手動設定を使用している場合は、Webサイトに別のページを作成してQR コードを配置します。
  * このページのスラッグを選択してください（例：**/app**、**/download-app**、 **/mobile-app** 等）。
  * デスクトップ／大画面の幅でのみページを表示可能にします。
* すべての施策：
  * Webページ上のQRコードは、スキャンしやすいように大きく高解像度で表示してください。
  * **App Storeからダウンロード**と**Google Playからダウンロード**というバナーを視覚的なトリガーとして目立つように（リンクではなく）追加してください。
  * QRコードのスキャン方法の説明を追加するのも良いアイディアです。
* 既にOneLinkを利用していますか？メールキャンペーンなどで使用されている*その他*のカスタムOneLinkで、 **af\_web\_dp** パラメーターを追加し、QRコードを含むページのURLを値に設定してください。これは、リンクをクリックしたデスクトップユーザーをアプリストアの代わりにWebページに送信します。  

  [![](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)](https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg)

</Accordion>

<div data-zendesk-anchors="converting-mobile-nonmobile-and-offline-traffic-into-mobile-app-users=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E9%9D%9E%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%AA%E3%83%95%E3%83%A9%E3%82%A4%E3%83%B3%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E8%AA%98%E5%B0%8E%E3%81%99%E3%82%8B h_01HKWVMKP3QT59EXPHQEPHW8K9=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E9%9D%9E%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%AA%E3%83%95%E3%83%A9%E3%82%A4%E3%83%B3%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E8%AA%98%E5%B0%8E%E3%81%99%E3%82%8B h_01HKWWQXVC11E8M3NV3A03SWYD=qr-to-app-conversion manual-qr-code-setup=qr%E3%82%B3%E3%83%BC%E3%83%89%E3%81%AE%E6%89%8B%E5%8B%95%E8%A8%AD%E5%AE%9A h_01HKWWQXVCB96WDMBSE9WH9ZC5=qr%E3%82%B3%E3%83%BC%E3%83%89%E3%81%AE%E6%89%8B%E5%8B%95%E8%A8%AD%E5%AE%9A h_01HKWVMKP3R5C5FPH010ZJZAHS=customize-qr-code h_01HKWVMKP3XTF6NNPNM8J00NWD=measure-qrtoapp-conversions h_01HKWVMKP3P6FNRPP1X7ZTNH10=best-practices" />

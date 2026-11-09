---
title: OneLink｜導入ガイド
metadata:
  keywords:
    - Marketers
    - set up
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-08-21T11:48:39Z'
  edited_at: '2026-10-28T09:18:39Z'
  id: 27699299657617
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/27699299657617
---
> **概要**：OneLinkを使用すると、ユーザーのデバイス、OS、チャネル、プラットフォームを問わず、キャンペーンからのリダイレクト、ディープリンク、アトリビューションを柔軟に設定し、コンバージョンの最大化を図れます。

<Image align="center" alt="53010_Onelink.jpg" src="https://files.readme.io/c0d24ab87126bf765a89a25077b07d8678159cdb6f1b68eddc14a4cd2759b12a-30192941047185.jpg" />

<div id="about-onelink" />

## OneLinkについて

AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>では、アトリビューション、リダイレクト、ディープリンクの機能を備えたキャンペーン用リンクを作成できます。デバイス、OS、チャネル、プラットフォームを問わず、ユーザーの状況に合ったスムーズな導線を提供し、オウンドメディアのユーザーをアプリユーザーに転換するとともに、既存ユーザーのエンゲージメントを促進します。 OneLinkを使用してユーザーごとの状況に合わせた導線を作成し、アプリへの誘導とコンバージョン率・収益の最大化につなげましょう。次のようなユーザー体験を作成できます。

* **Social-to-app**：ソーシャルメディア上でユーザーの関心を引き、フィードからアプリへ誘導します。
* **App-to-app**：他のアプリ内から自社アプリへユーザーを誘導します。
* <Anchor target="_blank" href="/marketers/ja/docs/convert-your-mobile-web-visitors-to-app-users">**Web-to-app**</Anchor>：Smart BannersとSmart Scriptを使用し、モバイルWebサイトの訪問者を新規モバイルアプリユーザーに転換します。**有料機能を含みます**
* **QR-to-app**：QRコードを活用して、オフラインでの顧客体験の要所でユーザーにコードを読み取ってもらい、アプリのインストールを促進します。また、デスクトップサイトやテレビ・CTV広告にQRコードを掲載して、ユーザーをアプリへ誘導することもできます。
* **Email-to-app**：メール配信サービスプロバイダー（ESP）を利用してメールでユーザーの関心を引き、受信トレイからアプリへ誘導します。**有料機能を含みます**
* **Text-to-app**：SMSやメッセージ配信キャンペーン用のリンクを作成し、テキストメッセージを通じてユーザーのエンゲージメントを促進します。
* **Referral-to-app**：ユーザーやインフルエンサーが他のユーザーをアプリに招待したり、記事などの特定のアプリ内コンテンツを共有したりできるユーザー招待リンクを作成します。**有料機能を含みます**
* **Custom**：豊富なオプションを組み合わせ、ニーズに合わせて柔軟にカスタマイズしたユーザー体験を作成します。 デスクトップ／モバイル、オンライン／オフライン、オウンドメディア／有料メディアを問わず、OneLinkを使って、あらゆる流入元のユーザーを適切な遷移先へ簡単に誘導できます。

**注意：** OneLinkの基本設定は無料プランでも利用できますが、ほとんどの機能にはAppsFlyerの有料<Anchor target="_blank" href="/marketers/ja/docs/account-management-plans-payments-and-billing#appsflyer-plans">サブスクリプションプラン</Anchor>が必要です。 0>

<div id="onelink-onboarding" />

## OneLinkの導入

**OneLinkの利用を開始するには、次の手順に従ってください。**

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**前提条件**

* 自社アプリが少なくとも1つ登録されているAppsFlyer<Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">アカウント</Anchor>。
* ほとんどの機能にはAppsFlyerの有料<Anchor target="_blank" href="/marketers/ja/docs/account-management-plans-payments-and-billing#appsflyer-plans">サブスクリプションプラン</Anchor>が必要です。ご不明な点は、[hello@appsflyer.com](mailto:hello@appslfyer.com)までお問い合わせください。
* OneLinkを設定するには、AppsFlyerの管理者ユーザーであるか、OneLinkテンプレートを追加・編集する<Anchor target="_blank" href="/marketers/ja/docs/user-management">権限</Anchor>が必要です。
* インストールとアプリ内イベントのアトリビューション、およびディープリンクを利用するには、モバイルアプリに<Anchor target="_blank" href="/marketers/ja/docs/integrate-the-appsflyer-sdk">AppsFlyer SDK</Anchor>が実装されている必要があります。
  * SDKがまだ実装されていない場合も、リダイレクトが機能するリンクは作成できますが、アトリビューションは行われません。

| タスク | 目的 | 必要な作業 | 担当者 |
| --- | --- | --- | --- |
| 1. OneLinkテンプレートの作成 | OneLinkテンプレートは、作成するリンクに共通するリダイレクト設定の土台として必要です。 | <ul><li>マーケター／プロダクトマネージャー：AppsFlyerで<Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template">OneLinkテンプレート</Anchor>を設定します。</li><li>Android開発者：既存ユーザー向けにアプリを開く方法（Android App LinksとURIスキーム）を設定します。</li><li>iOS開発者：既存ユーザー向けにアプリを開く方法（iOS Universal LinksとURIスキーム）を設定します。</li></ul><Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">開発者向けの手順</Anchor> | マーケターと開発者 |
| 2. OneLinkリンクの作成 | 新しく作成したテンプレートをもとに、キャンペーンで使用するOneLinkリンクを作成します。 | <ul><li>マーケター／プロダクトマネージャー：AppsFlyerで<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">OneLinkリンク</Anchor>を設定し、ユーザー体験の選択やアトリビューション・ディープリンク用パラメータの追加を行います。</li><li>Android／iOS開発者：<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">ディープリンク</Anchor>を設定します（ディープリンクが必要な場合）。</li></ul> | マーケターと開発者 |
| 3. ドメインのリダイレクト許可リストの設定 | セキュリティ上の理由により、AppsFlyerで作成したリンクは、許可リストに登録されているドメインのWeb URLにのみユーザーをリダイレクトします。 | ユーザーのリダイレクト先とするすべてのドメインを、<Anchor target="_blank" href="/marketers/ja/docs/set-up-your-domain-redirect-allowlist">ドメインのリダイレクト許可リスト</Anchor>に登録します。 | マーケター |
| 4. 新しいリンクのテスト | 次のユーザーがリンクから正常にリダイレクトされることをテストします。<ul><li>アプリをインストールしていない新規ユーザー</li><li>アプリをインストール済みの既存ユーザー</li></ul> | 新しく作成したリンクを<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">テスト</Anchor>できます。 | マーケター |
| 5. テスト済みのリンクをキャンペーンで使用し、結果を計測 |  | <ol><li>新しいリンクをキャンペーンに追加して、対象ユーザーに配信します。</li><li>AppsFlyerのOverview dashboardで、キャンペーンを指定してフィルタリングし、成果を確認します。</li></ol>お疲れさまでした！ OneLinkの導入はこれで完了です。 | マーケター、データアナリスト |
| **オプション機能** |  | 設定が完了したら、以下のようなOneLinkの追加機能もご検討ください。<ul><li>Web-to-app：Webユーザーをアプリユーザーに転換し、Webからアプリへのコンバージョン経路を計測します。</li><li><Anchor target="_blank" href="/marketers/ja/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor>と<Anchor target="_blank" href="/marketers/ja/docs/perform-onelink-bulk-actions-via-csv">リンクの一括作成</Anchor>：複数のキャンペーンを同時に大規模に展開し、数千ものOneLinkリンクをすばやく簡単に作成できます。<br />*OneLink APIの利用にはEnterpriseプランの契約が必要です。</li><li><Anchor target="_blank" href="/marketers/ja/docs/export-onelink-urls">OneLink URLのエクスポート</Anchor>：AppsFlyerで作成したOneLink URLをダウンロードします。</li><li><Anchor target="_blank" href="/marketers/ja/docs/user-invite-attribution">ユーザー招待のアトリビューション</Anchor>：アプリ内で直接作成するユーザー招待リンクを組み込み、エンゲージメントを促進します。</li><li><Anchor target="_blank" href="/marketers/ja/docs/cross-promotion-attribution-for-marketers">クロスプロモーションのアトリビューション</Anchor>：既存のアプリユーザーは、自社の別の新しいアプリをインストールしてくれる可能性が高いユーザーです。 SDKのメソッドを使用してクロスプロモーションキャンペーンを作成し、計測する方法をご確認ください。</li><li><Anchor target="_blank" href="/marketers/ja/docs/understand-onelink-short-vs-long-urls">ロングURL</Anchor>：OneLinkカスタムリンクにパラメータを追加したり、スプレッドシートで独自の簡単な数式を使用して多数のOneLinkカスタムリンクを生成したりできます。</li></ul>**注意：** ほとんどの機能にはAppsFlyerの有料<Anchor target="_blank" href="/marketers/ja/docs/account-management-plans-payments-and-billing#appsflyer-plans">サブスクリプションプラン</Anchor>が必要です。 | マーケターと開発者 |

OneLinkの利用開始にあたってご不明な点がある場合は、営業担当者に連絡するか、[hello@appsflyer.com](mailto:hello@appsflyer.com)までお問い合わせください。

<div id="traits-and-limitations" />

## 特性と制限事項

| 項目 | 説明 |
| --- | --- |
| iPadのSafariにおけるオウンドメディアのアトリビューション | iPadのSafariブラウザでユーザーがオウンドメディアのリンクをクリックすると、ブラウザはiPadのデバイスモデルではなく、**Macintoshに似たユーザーエージェント**を報告する場合があります。その結果、AppsFlyerはクリックをMacからのアクセスとして識別する一方、アプリのインストールはiPadで行われたものとして識別します。確率論的モデリングによるアトリビューションは、クリック時とインストール時のデバイス特性の照合に依存するため、この不一致によってアトリビューションができなくなり、インストールがアトリビューションされない、またはディファードディープリンクが機能しない場合があります。この制限は、Safariを使用するiPadのオウンドメディアトラフィックにのみ適用されます。 |

<div data-zendesk-anchors="overview=onelink%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J2G7RMHSPPXCWJ60W9HZASXX=onelink%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=onelink%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 xyz-onboarding=onelink%E3%81%AE%E5%B0%8E%E5%85%A5 h_01J2RJFH0B4R815CWDQNEB2C1P=onelink%E3%81%AE%E5%B0%8E%E5%85%A5 traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KFAG3N0X0W0RCJXK00KX038E=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85" />

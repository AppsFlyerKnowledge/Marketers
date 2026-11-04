---
title: Eメールサービスプロバイダ（ESP）連携ガイド
metadata:
  keywords:
    - Email
    - Advertisers
    - Developers
    - Premium
    - Email service providers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-12-31T10:43:24Z'
  edited_at: '2026-10-14T09:21:47Z'
  id: 360004556077
  locale: ja
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ja/articles/360004556077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** OneLink ブランドリンクとディープリンクを使用して連携されたESPでメールキャンペーンを作成し、コンバージョンをうながすシームレスなユーザーエクスペリエンスを実現します。

<div id="about-esp-integration" />

## ESP連携について

Eメールマーケティングは、顧客や潜在顧客と関わるためのシンプルで強力かつ効果的な方法です。多くのマーケターは、ユーザーに大規模なメールキャンペーンを送信するために、Eメールサービスプロバイダ（ESP）に依存しています。そして、これは単純明快なプロセスであり、あなたが思い描く完璧なモバイルユーザージャーニーを提供するはずですが、通常はそうではありません。

**課題は何ですか？**

この問題は、一般的なESPのアナリティクスの扱い方に起因しており、ディープリンクを破壊し、モバイルのユーザーエクスペリエンスに悪影響を及ぼす傾向があります。ディープリンクとは、ユーザーをアプリ内の特定の場所に直接誘導することを指し、コンバージョンを効果的にする上で重要な機能です。ESPが送信するメールキャンペーンでスムーズなディープリンク体験を提供することは本当に難しいことです。ESPは計測目的でディープリンクを「ラップ」（短縮化）するため、iOSユニバーサルリンクやAndroidアプリリンクに必要なアプリとドメインの関連付けが壊れてしまいます。そして、残念ながらこのような結果になります：

* ユーザーをアプリにディープリンクさせるのではなく、モバイルウェブサイトに遷移させる。
* 安全性が低く、ユーザーエクスペリエンスが劣るURIスキームのディープリンクを使用する。

<Image alt="53242 KB.png" src="https://files.readme.io/53db119f60e3fe2dfaf58b8a87e14595eeb9dde375bf87f7617f36a463ee0ced-30227717940753.png" width="688px" />

**ソリューションは何ですか？**

これらの問題を回避し、モバイルユーザーに最高の体験を提供するには、以下のセクションでESPをクリックし、特定の連携手順に従ってください。一部のESPは、AppsFlyerがESPサーバーとお客様のドメイン名の仲介を行う、AppsFlyer統合ソリューションによってサポートされています。プロキシとしての役割は、ディープリンクを容易にするアソシエーションファイル（AASA/アセットリンク）の提供を可能にする。

<div id="supported-esps" />

## サポートされているESP

モバイルアプリユーザー向けのESPメールキャンペーンは、アトリビューションやディープリンクの問題を引き起こす可能性があります。これらの問題を回避するには、以下のセクションでESPをクリックし、特定の指示に従ってください。

| サポートされているESPのリスト | AppsFlyerベータ版の連携をサポート |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="acoustic logo.svg" src="https://files.readme.io/b3dac2e0a4f326da76584ed95ee2cd61683edff054c67110c56b95a361444acb-38086051586577.svg" width="211px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB blueshift.png" src="https://files.readme.io/038b29f54fdb4e20775d7c1af0e6543a78351abdfad8b8d7d029a1fdd5b5de7b-32377991388945.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB braze.png" src="https://files.readme.io/41e9614c7a35cd18f1d17d5958d6a7243e53a1af0a3e56935342b90103d7be20-32378022189969.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB CleverTap.png" src="https://files.readme.io/f3190c5c82b380e93d70bbccccf279f78decf6a223bcab3ca62958356202e1a1-32378022192657.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB customer.io.png" src="https://files.readme.io/e893909294e6397226b10dbad55f06644cf7a9e6db0a3020280495a9d17fc53c-32378022194833.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/emaillabs-integration-with-appsflyer"><Image alt="53798 KB EmailLabs (1).png" src="https://files.readme.io/776046677e11500f4cc0eb33f30f0c3a266c85bc386e507aaecedb23bd9e0680-51909446815761.png" width="343px" /></Anchor> | いいえ。独自のリダイレクト方法を使用します。 |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB emarsys.png" src="https://files.readme.io/449120ed88bb0540b758530ca5d8884e2e8210485859b17eb272d61e218566a1-32378022206737.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB expertsender.png" src="https://files.readme.io/25141c53c10b3f2eed600567b04849dda88f6b379bb71ae00bcc2e85fa0171e7-32377991413393.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="Insider (1).svg" src="https://files.readme.io/544b4f408b64e99e037cfca238c578185db66d87d85f7d329e39d62b253ba618-36655909659153.svg" width="145px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/iterable-integration-with-appsflyer"><Image alt="53798 KB ITERABLE (1).png" src="https://files.readme.io/cc443da9715a94c37ba8818ecd80ee6565fcf38d479c3ae6e744e71960accfd7-51909430351505.png" width="343px" /></Anchor> | いいえ。独自のリダイレクト方法を使用します。 |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB klaviyo.png" src="https://files.readme.io/393e2afebbb2d3fcf4d5f42c29f6e082d102f2a0a81edba5c3c602184544f55b-51909430352913.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB MailExpress (2).png" src="https://files.readme.io/7a196f7d2825ea7dbb14a7deda4af907c5056957b63e93c53a7550bd8394a5c4-32377991435921.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB Mailgun.png" src="https://files.readme.io/4a19bb320d3abf176ca3bb2384f4de5a06d8e2f1925df2fc6e082372b711b19a-32377991438865.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB moengage.png" src="https://files.readme.io/d2316501fe1f428d4337a4924a59e93545b50171d173b3371bdd4dd180805509-32377991440913.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB ongage.png" src="https://files.readme.io/d3dd0839abd7ee6fbcf065a815d71a20885b0a09beabd37452c47d0396ee1d6e-32378022240273.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/oracle-responsys-integration-with-appsflyer"><Image alt="53798 KB ORACLE (1).png" src="https://files.readme.io/e3167fe6f110aebbcb7d046f5b5a4439531a1ae1da6658df609ec73f181e5e05-51909430353553.png" width="343px" /></Anchor> | いいえ。独自のリダイレクト方法を使用します。 |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB RD STATION.png" src="https://files.readme.io/91a24e7341c87484a4c06d077a1ee7fd7a04b3817b63ced27cec944421ca58aa-32378022248977.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB Reteno.png" src="https://files.readme.io/4e1d8fab29601c1d3c2015a7253258a9c152cd987ee6c5f0125c6f6e79a370a1-32377991454609.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB SAILTHRU.png" src="https://files.readme.io/61b721936f4f9cc64ee9551a213865eca2bea188599311f79d92d945204a713b-32378022253841.png" width="343px" /></Anchor> | はい |
| <Image alt="salesforce.png" src="https://files.readme.io/c270f99994ecb1a96a4154a815b5f013305795b681bb1bfd404f76c5beeb30af-51909446820625.png" width="147px" /> | いいえ。独自のリダイレクト方法を使用します。 |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB sendgrid.png" src="https://files.readme.io/f4c3217e956db7e922a6150597d596c2c4848e5aa0a43b2347824aacbeb2caa3-32378022256785.png" width="343px" /></Anchor> | はい |
| <Anchor target="_blank" href="/marketers/ja/docs/set-up-your-esp-integration-with-appsflyer"><Image alt="53798 KB SPARKPOST.png" src="https://files.readme.io/bec55e3c96bb80b736777e110d05df9009e015ef2c1cdd8b3d8088880264f593-32377991460369.png" width="343px" /></Anchor> | はい |

<div data-zendesk-anchors="overview=esp%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J3JHJCCASM6E5QYJB5VHQ8HK=esp%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 supported-email-service-providers=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8Besp h_01H92VH355BQ13SP72VNJEKW1E=%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%95%E3%82%8C%E3%81%A6%E3%81%84%E3%82%8Besp" />

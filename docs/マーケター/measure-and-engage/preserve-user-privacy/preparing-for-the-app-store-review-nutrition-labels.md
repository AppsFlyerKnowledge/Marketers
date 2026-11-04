---
title: App Storeの審査に向けた準備
metadata:
  keywords:
    - iOS
    - iTunes
    - Apple
    - IDFA
    - Guidelines
    - IFA
    - Ad Tracking
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-04-12T13:28:26Z'
  edited_at: '2026-10-14T09:38:46Z'
  id: 207032086
  locale: ja
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ja/articles/207032086
---
> **概要**:

弁護士からの一言： ここに記載されていることは、一切法的な助言ではありません。これらは情報提供と便宜上の目的でのみ提供されています。

<div id="nutrition-labels-and-the-app-store-review" />

## プライバシーに関する詳細情報とApp Store審査

* プライバシーラベルを生成するには、アプリデベロッパーはApp Store Connectにアプリを提出する際に、次のセクションを含むいくつかの質問に回答する必要があります。
  * 収集されるデータタイプ
  * [データが収集される目的](/docs/preparing-for-the-app-store-review-nutrition-labels#データの使用目的)
  * [データタイプが個人識別情報に紐づくものかどうか](/docs/preparing-for-the-app-store-review-nutrition-labels#idに紐づくデータ)
  * データがトラッキングに使用されるかどうか（アプリ内に含まれるサードパーティサービスやSDKに関するものを含む）
* アプリデベロッパー：
  * AppsFlyerソフトウェアの実装と設定方法、収集するデータ、およびそのデータの使用方法に関して、完全な決定権を有しています。
  * 各々のAppsFlyerソフトウェアの実装方法と収集するデータポイントに基づいて、アンケートに対する回答が大きく異なる可能性があります。
* Appleのポリシーに関するAppsFlyerの理解では、AppsFlyerはトラッキングを実施しません。そのため、アプリデベロッパーは自身の用途やパートナー連携の方針に基づいて、プライバシーに関する質問に回答する必要があります。
* 収集されたデータをトラッキング目的に使用する場合は、ATTへの同意画面を実装する必要があります。
* 次の表は、AppsFlyerソフトウェアのデフォルト実装を前提としています。アプリ開発者は、それぞれの構成や用途に合わせて、適宜適合させる責任があります。

<div id="data-types-collected" />

#### 収集されるデータタイプ

| **データタイプ** | **AppsFlyerのデータ収集** | **備考** |
| --- | --- | --- |
| **Contact information/連絡先情報**<ul><li>名前</li><li>メールアドレス（ハッシュ化を含む）</li><li>電話番号（ハッシュ化を含む）</li><li>住所</li><li>その他のユーザー連絡先情報</li></ul> | いいえ | 連絡先情報は収集すべきではありません。ただし、アプリでハッシュ化されたメールアドレスや電話番号を通信するよう設定している場合は、それに応じてApp Storeの質問に回答してください。 |
| **フィットネス** | いいえ | 収集しません |
| **Financial info/財務情報**<ul><li>お支払い情報</li><li>クレジット情報</li><li>その他の財務情報</li></ul> | いいえ | 収集しません |
| **Location info/位置情報**<ul><li>正確な位置</li><li>大体の位置</li></ul> | /span>備考を参照 | <ul><li>正確な位置情報いいえ</li><li>大体の位置はい。IPアドレスが収集され大体の地理的位置にマッピングされます。</li></ul> |
| **Sensitive info/機密情報** | いいえ | 収集しません |
| **Contacts/連絡先** | いいえ | 収集しません |
| **User content/ユーザーコンテンツ**<ul><li>メールまたはテキストメッセージ</li><li>写真または動画</li><li>音声データ</li></ul> | いいえ | 収集しません |
| **Browsing history/閲覧履歴** | いいえ | 収集しません |
| **Search history/検索履歴** | いいえ | 収集しません |
| **Identifiers/識別情報**<ul><li>ユーザーID</li><li>デバイスID (IDFA)</li></ul> | オプション | <ul><li>\_ユーザーIDユーザーID: アプリデベロッパーはユーザーID (CUID) を設定および送信できます。</li><li>device\_idデバイスID: 広告ID (IDFA) はアクセス可能な場合にのみ収集されます。</li></ul> |
| **購入**<ul><li>購入履歴</li></ul> | オプション | アプリデベロッパーは特定のアプリ購入イベントを計測するように設定できます。 |
| **Usage data/データ使用状況**<ul><li>製品インタラクション</li><li>広告データ</li><li>その他の使用状況データ</li></ul> | <ul><li>はい</li><li>オプション</li><li>いいえ</li></ul> | <ul><li>製品インタラクション製品インタラクション: アプリ起動や、アプリデベロッパーによって設定されたその他のユーザーインタラクションが計測されます。</li><li>広告データ: アプリデベロッパーがAppsFlyer広告収益モジュールを使用する場合に受信されます。</li></ul> |
| **Diagnostics data/診断データ**<ul><li>クラッシュデータ</li><li>パフォーマンスデータ</li><li>その他の診断データ</li></ul> | <ul><li>いいえ</li><li>はい</li><li>いいえ</li></ul> | 起動時間および/またはバッテリー残量は不正検知のために受信されることがあります。 |
| **その他のデータ**<ul><li>その他のデータタイプ</li><li>IDFV</li></ul> | はい | <ul><li>技術デバイス情報（例：OS、デバイスタイプ、言語、画面サイズなど）または、ネットワーク情報（例：IPアドレス、HTTPユーザーエージェント）はAppsFlyerによって受信されます。</li><li>AppsFlyerは各アプリインストールに対してAF IDというインストールIDを割り当てます。</li><li>IDFVは収集されます。</li></ul> |

<div id="data-use-purposes" />

### データの使用目的

Googleは、アプリ開発者が選択しなければならない目的のリストを次の表のように提供しています。

| データの目的 | AppsFlyerからのデータの使用方法に基づく選択 |
| --- | --- |
| Third-party advertising /サードパーティ広告 | サードパーティの広告をアプリ内で表示するために、データタイプをサードパーティと共有する場合に選択します。 |
| Developer’s advertising or marketing /開発者の広告またはマーケティング | アプリ内でファーストパーティ広告を表示する場合（自社広告を表示するためにサードパーティと共有する場合を含む）または、その他のマーケティング目的で使用する場合に選択します。 |
| アナリティクス | はい |
| Product personalization / 製品のパーソナライズ | 製品のパーソナライゼーションにデータを使用する場合に選択します。 |
| App functionality / アプリの機能 | はい |
| Other purposes / その他の目的 | 記以外の記載されていない目的のためにデータを使用する場合に選択します。 |

<div id="data-linked-to-an-identity" />

### IDに紐づくデータ

AppsFlyerを介して収集されるデータタイプは、大抵の場合、デバイスID（利用可能な場合）などの識別子、もしくは実装されている場合は、顧客が発行したカスタマーIDなどに紐づいています。

したがって、アプリデベロッパーは、データがIDに紐づいているかという質問に対して、Yesを選択し回答すべきです。

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="https://developer.apple.com/app-store/app-privacy-details/">AppleのApp Storeのアプリプライバシーに関する情報</Anchor>

<div data-zendesk-anchors="nutrition-labels-and-the-app-store-review=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E8%A9%B3%E7%B4%B0%E6%83%85%E5%A0%B1%E3%81%A8app-store%E5%AF%A9%E6%9F%BB h_01HE7T7J409620K5KX5XKPEQVZ=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E8%A9%B3%E7%B4%B0%E6%83%85%E5%A0%B1%E3%81%A8app-store%E5%AF%A9%E6%9F%BB data-types-collected=%E5%8F%8E%E9%9B%86%E3%81%95%E3%82%8C%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BF%E3%82%A4%E3%83%97 h_01HE7T7J4004XVJTMF6S964DVB=%E5%8F%8E%E9%9B%86%E3%81%95%E3%82%8C%E3%82%8B%E3%83%87%E3%83%BC%E3%82%BF%E3%82%BF%E3%82%A4%E3%83%97 data-use-purposes=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E4%BD%BF%E7%94%A8%E7%9B%AE%E7%9A%84 h_01HE7T7J4098NNW8D0BCD3EFBJ=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E4%BD%BF%E7%94%A8%E7%9B%AE%E7%9A%84 data-linked-to-an-identity=id%E3%81%AB%E7%B4%90%E3%81%A5%E3%81%8F%E3%83%87%E3%83%BC%E3%82%BF h_01HE7T7J41BJG9GTBWMVKG7031=id%E3%81%AB%E7%B4%90%E3%81%A5%E3%81%8F%E3%83%87%E3%83%BC%E3%82%BF h_01HE7TES34MEF1XR4B6BDEMJW4=%E5%8F%82%E7%85%A7" />

---
title: 詳細マッチングデータの共有
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-06-18T14:23:54Z'
  edited_at: '2026-10-28T09:07:35Z'
  id: 47876839961489
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/47876839961489
---
> **At a glance:** 詳細マッチングデータの共有では、メールアドレスや電話番号などのハッシュ化されたユーザー識別子をAppsFlyerから指定のアドネットワークへ転送します。パートナーはデバイスIDがなくても、イベントを広告接触と紐付けて計測できます。

<div id="about-advanced-matching-data-sharing" />

## 詳細マッチングデータの共有について

利用できるデバイス識別子が減る中、アドネットワークが広告接触の照合にファーストパーティデータを活用する機会が増えています。詳細マッチングデータの共有は、ハッシュ化された識別子を、プライバシー要件に準拠した形式で対応パートナーに転送することで、この課題に対処します。

この機能は任意で利用でき、パートナーごとに設定します。対応するアドネットワークで有効にすると、AppsFlyerはインストール、リエンゲージメント、アプリ内イベントのデータとともに、ハッシュ化された識別子を転送します。

> 🚧 **Important**
>
> すべての識別子は、AppsFlyerに到達する前に、デバイス上のSDKまたはS2S APIを使用するサーバー側の処理で、SHA-256によるハッシュ化を行う必要があります。平文のデータを受信、保存、転送することはなく、検証に失敗した値は受信時に破棄されます。

<div id="supported-partners" />

### 対応パートナー

詳細マッチングデータの共有は、以下のアドネットワークで利用できます。

| パートナー | パートナーID（PID） | 対応する詳細マッチングフィールド |
| --- | --- | --- |
| Google | googleads\_int | ハッシュ化したメールアドレス、電話番号 |
| Meta | facebook\_int | ハッシュ化したメールアドレス、電話番号、名、姓 |
| Meta | metweb\_int | ハッシュ化したメールアドレス、電話番号、名、姓、およびFBログインID |
| Moloco | moloco\_int | ハッシュ化したメールアドレス、電話番号、名、姓 |
| ChatGpt Ads | openai\_int | ハッシュ化したメールアドレス、電話番号、名、姓 |
| Pinterest | pinterest\_int | ハッシュ化したメールアドレス、電話番号、名、姓 |
| Snapchat | snapchat\_int | ハッシュ化したメールアドレス、電話番号 |
| Snapchat | snapweb\_int | ハッシュ化したメールアドレス、電話番号、名、姓 |
| TikTok | tiktokglobal\_int | ハッシュ化したメールアドレス、電話番号、名、姓 |
| TikTok | tiktokweb\_int | ハッシュ化したメールアドレス、電話番号、名、姓 |
| Reddit | reddit\_int | ハッシュ化したメールアドレス、電話番号 |
| Rokt | roktv2\_int | ハッシュ化したメールアドレス、電話番号、名、姓 |
| Roku | rokuads\_int | ハッシュ化したメールアドレス、電話番号 |
| Smadex | smadex\_int | ハッシュ化したメールアドレス、電話番号、名、姓 |

<div id="the-end-to-end-flow" />

## 取得から共有までの流れ

識別子を取得してからパートナーに届くまでの流れは、以下のとおりです。

1. アプリまたはバックエンドが、メールアドレス、電話番号などの対応する識別子を取得します。
2. AppsFlyer SDKが識別子を自動で正規化し、SHA-256でハッシュ化します。S2S APIで送信する場合は、送信前にサーバー側で同じ処理を行います。
3. SDKまたはサーバーが、ハッシュ化した識別子を、イベント（インストール、再インストール、リエンゲージメント、アプリ内イベント）とともにAppsFlyerへ送信します。
4. 対象パートナーで詳細マッチングデータの共有が有効な場合、AppsFlyerはイベントのペイロードとともにハッシュ値を転送します。
5. パートナーはハッシュ値を使用してイベントを既知のユーザーと照合し、アトリビューションの精度と照合の品質を高めます。

> 📘 **Note**
>
> ハッシュ化した識別子は、詳細マッチングデータの共有が有効なパートナーにのみ転送されます。パートナーの設定を無効にすると、イベントに識別子が含まれていても、そのパートナーにはハッシュ化されたデータを共有しません。

<div id="send-hashed-identifiers-with-the-sdk" />

<div id="how-hashed-user-identifiers-reach-appsflyer" />

## ハッシュ化したユーザー識別子をAppsFlyerに送信する方法

ハッシュ化した識別子をAppsFlyerに送信する方法は、SDKとサーバー間（S2S）APIの2つです。どちらの場合も、正しくハッシュ化された値のみ受け付けます。各方法は、以下のタブで説明します。

<Tabs>
<Tab title="SDK">

SDK V7.0.1では、ハッシュ化前の識別子をAppsFlyerのAndroidおよびiOS SDKに渡すメソッドが導入されています。 SDKは入力値を正規化し、ハッシュ化してからAppsFlyerに送信します。

SDKは、以下の手順を順番に実行します。

1. 各パートナーの要件に従って入力値を正規化します。
2. 正規化した値をSHA-256でハッシュ化します。
3. ハッシュ化した値のみをAppsFlyerに送信します。ハッシュ化前の入力値がデバイスの外に送信されることはありません。

無効な値はSDKがエラーとして拒否し、AppsFlyerには送信しません。

<div id="send-hashed-identifiers-with-the-s2s-api" />

> 📘 **Note**
>
> AndroidとiOSでは、SDK V7.0.1以降で利用できます。

実装の詳細は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">Android SDK実装ガイド</Anchor>および<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk">iOS SDK実装ガイド</Anchor>を参照してください。

</Tab>

<Tab title="S2S API">

S2Sアプリ内イベントAPIでイベントを送信する場合は、送信前にサーバー側で識別子の正規化とハッシュ化を行う必要があります。 APIは、以下のフィールドを受け付けます。

| フィールド | 説明 |
| --- | --- |
| `email_hashed` | ハッシュ化したメールアドレス |
| `phone_number_hashed` | ハッシュ化した電話番号（数字のみの形式） |
| `phone_number_e164_hashed` | ハッシュ化した電話番号（E.164形式） |
| `first_name_hashed` | ハッシュ化した名 |
| `last_name_hashed` | ハッシュ化した姓 |
| `fb_login_id` | FacebookログインID（ハッシュ化せず、そのまま送信） |

> 🚧 **Important**
>
> この表のすべてのフィールド（fb\_login\_idを除く）で、SHA-256形式かどうかを検証します。形式が一致しない値は、通知せずに破棄され、どのパートナーにも転送されません。イベントの他のフィールドは通常どおり処理されます。

<div id="why-are-there-two-phone-number-fields" />

<div id="h_why-two-phone-fields" />

#### 電話番号のフィールドが2種類あるのはなぜですか？

アドネットワークは、AppsFlyerから転送されたハッシュ値と、自社が保有するユーザーの電話番号のハッシュ値を比較して、イベントを照合します。同じ電話番号でも正規化の形式が異なるとハッシュ値が変わるため、照合する双方で同じ形式の値をハッシュ化する必要があります。アドネットワークごとに正規化の形式が異なり、AppsFlyerはハッシュ化済みの値を受け取るため、すべての対応パートナーで利用するには、両方の形式を送信する必要があります。

* `phone_number_hashed`：MetaとSnapchat向け。ハッシュ化前の正規化形式：`16501234567`
* `phone_number_e164_hashed`：GoogleとTikTok向け。ハッシュ化前の正規化形式：`+16501234567`

</Tab>
</Tabs>

<div id="facebook-login-id-fbloginid" />

<div id="first-name-firstnamehashed-and-last-name-lastnamehashed" />

<div id="phone-number-e164-phonenumbere164hashed" />

<div id="phone-number-digits-only-phonenumberhashed" />

<div id="email-emailhashed" />

<div id="normalize-and-hash-identifiers" />

## 識別子の正規化とハッシュ化

以下の手順に従って元の値を正規化し、SHA-256でハッシュ化して、小文字の16進数文字列でハッシュ値を送信します。

<Accordion title="メールアドレス（email_hashed）">

メールアドレスを以下の手順で正規化し、ハッシュ化します。

1. すべての空白文字を削除します。
2. 小文字に変換します。
3. SHA-256でハッシュ化します。

**例：**

`User@Example.COM`→`user@example.com`→SHA-256のハッシュ値

</Accordion>

<Accordion title="電話番号・数字のみ（phone_number_hashed）">

Meta、Reddit、Pinterest、Snapchatで使用します。電話番号を以下の手順で正規化し、ハッシュ化します。

1. 先頭に国番号を追加します。
2. 記号、英字、先頭の0をすべて削除します。
3. SHA-256でハッシュ化します。

**例：**

`+1 (650) 123-4567`→`16501234567`→SHA-256のハッシュ値

</Accordion>

<Accordion title="電話番号・E.164形式（phone_number_e164_hashed）">

Google、TikTok、Rokuで使用します。電話番号を以下の手順で正規化し、ハッシュ化します。

1. 先頭に国番号を追加します。
2. 記号、英字、先頭の0をすべて削除します。
3. 先頭に`+`を追加します。
4. SHA-256でハッシュ化します。

**例：**

`+1 (650) 123-4567`→`+16501234567`→SHA-256のハッシュ値

</Accordion>

<Accordion title="名（first_name_hashed）と姓（last_name_hashed）">

氏名を以下の手順で正規化し、ハッシュ化します。

1. すべての空白文字を削除します。
2. 小文字に変換します。
3. SHA-256でハッシュ化します。

</Accordion>

<Accordion title="FacebookログインID（fb_login_id）">

Facebook Login SDKから取得したFacebookログインIDをそのまま送信します。このフィールドはハッシュ化しません。

</Accordion>

<div id="turn-on-advanced-matching-data-sharing" />

## 詳細マッチングデータの共有の有効化

詳細マッチングデータの共有は、パートナーおよびアプリ単位で管理され、アドネットワークごとに明示的に有効にする必要があります。

詳細マッチングデータの共有を有効にするには、以下の手順を実施します。

1. AppsFlyerのサイドメニューで、**連携＞有効な連携**を選択します。
2. パートナーを検索して選択します。
3. **詳細マッチングデータの共有**を有効にします。
4. ［**連携を保存**］をクリックします。

詳細マッチングデータの共有を有効にすると、対応する識別子フィールドを1つ以上含むイベントで、該当フィールドがパートナーに転送されます。

> 📘 **Note**
>
> 詳細マッチングデータの共有を無効にすると、そのパートナーへのハッシュ化されたデータの共有は直ちに停止します。ポストバックやイベントデータなど、他の連携設定には影響しません。

<div id="privacy-and-data-handling" />

## プライバシーとデータの取り扱い

パートナーで詳細マッチングデータの共有を有効にすると、AppsFlyerはイベントデータとともに、ハッシュ化されたユーザー識別子をそのアドネットワークへ転送し始めます。有効にする前に、以下を確認してください。

* 一般データ保護規則（GDPR）やカリフォルニア州消費者プライバシー法（CCPA）など、適用されるプライバシー法に基づき、パートナーとこのデータを共有する法的根拠があること。
* プライバシーポリシーを更新し、必要な場合はユーザーの同意を取得していること。
* データ共有の方法が、パートナーの規約に準拠していること。

> 🚧 **Important**
>
> AppsFlyerは、平文の個人識別情報（PII）を処理または保存しません。すべての識別子フィールドを受信時に検証します。SHA-256形式に準拠していない値は破棄し、どのパートナーにも転送しません。

<div id="does-appsflyer-ever-receive-plaintext-user-identifiers" />

<div id="will-advancedmatching-data-sharing-improve-install-attribution" />

<div id="do-i-need-to-send-all-supported-fields" />

<div id="what-happens-if-i-send-an-invalid-hash-value" />

<div id="is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature" />

<div id="faq" />

## よくある質問

<Accordion title="詳細マッチングデータの共有は、Audiencesのメールアドレスや電話番号のハッシュ値を利用する機能と同じですか？">

いいえ。これらは別々の仕組みです。 Audiencesは、広告ターゲティング用のユーザーリストを作成します。詳細マッチングデータの共有は、個々のイベントとともにハッシュ化された識別子を転送し、パートナー側の照合率を高めます。 AppsFlyerでは、両方の仕組みを統合し、新しいデータ取得方法を詳細マッチングデータの共有とAudiencesの両方で使用する予定です。

</Accordion>

<Accordion title="無効なハッシュ値を送信するとどうなりますか？">

そのフィールドは受信時に破棄され、どのパートナーにも転送されません。イベントの他のフィールドは通常どおり処理されます。

</Accordion>

<Accordion title="対応するフィールドをすべて送信する必要がありますか？">

いいえ。取得可能で、設定したパートナーに関連する識別子のみを含めれば問題ありません。含まれていないフィールドは転送されません。

</Accordion>

<Accordion title="詳細マッチングデータの共有で、インストールのアトリビューションは改善されますか？">

ほとんどのパートナーは、インストール、リエンゲージメント、再インストールの照合に、ハッシュ化したメールアドレスや電話番号を使用していません。これらのフィールドの送信は、主にパートナー側でアプリ内イベントをより正確に照合するために役立ちます。 AppsFlyerのアトリビューションには影響しません。

</Accordion>

<Accordion title="AppsFlyerが平文のユーザー識別子を受信することはありますか？">

いいえ。記事上部の「重要」に記載のとおり、識別子はデバイス上のSDKまたはS2S APIを使用するサーバー側の処理で、AppsFlyerに到達する前に必ずハッシュ化されます。 AppsFlyerは、ハッシュ化された値のみを受け付けます。

</Accordion>

<div data-zendesk-anchors="about-advancedmatching-data-sharing=%E8%A9%B3%E7%B4%B0%E3%83%9E%E3%83%83%E3%83%81%E3%83%B3%E3%82%B0%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%85%B1%E6%9C%89%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KVFJHWK1TYAPPMZDYFAP0RX0=%E8%A9%B3%E7%B4%B0%E3%83%9E%E3%83%83%E3%83%81%E3%83%B3%E3%82%B0%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%85%B1%E6%9C%89%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 supported-partners=%E5%AF%BE%E5%BF%9C%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC h_01KVFJHWK1VTJZH53FKNE8NZ59=%E5%AF%BE%E5%BF%9C%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC the-endtoend-flow=%E5%8F%96%E5%BE%97%E3%81%8B%E3%82%89%E5%85%B1%E6%9C%89%E3%81%BE%E3%81%A7%E3%81%AE%E6%B5%81%E3%82%8C h_01KVFJHWK1JQ7J838YNDTYDD4A=%E5%8F%96%E5%BE%97%E3%81%8B%E3%82%89%E5%85%B1%E6%9C%89%E3%81%BE%E3%81%A7%E3%81%AE%E6%B5%81%E3%82%8C how-hashed-user-identifiers-reach-appsflyer=%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E5%8C%96%E3%81%97%E3%81%9F%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E8%AD%98%E5%88%A5%E5%AD%90%E3%82%92appsflyer%E3%81%AB%E9%80%81%E4%BF%A1%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 h_01KVFJHWK197KW8YBQ1NBD9XT1=%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E5%8C%96%E3%81%97%E3%81%9F%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E8%AD%98%E5%88%A5%E5%AD%90%E3%82%92appsflyer%E3%81%AB%E9%80%81%E4%BF%A1%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 why-are-there-two-phone-number-fields=h_why-two-phone-fields normalize-and-hash-identifiers=%E8%AD%98%E5%88%A5%E5%AD%90%E3%81%AE%E6%AD%A3%E8%A6%8F%E5%8C%96%E3%81%A8%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E5%8C%96 h_01KVFJHWK16KQ1X1WFTTTFFND3=%E8%AD%98%E5%88%A5%E5%AD%90%E3%81%AE%E6%AD%A3%E8%A6%8F%E5%8C%96%E3%81%A8%E3%83%8F%E3%83%83%E3%82%B7%E3%83%A5%E5%8C%96 turn-on-advancedmatching-data-sharing=%E8%A9%B3%E7%B4%B0%E3%83%9E%E3%83%83%E3%83%81%E3%83%B3%E3%82%B0%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%85%B1%E6%9C%89%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01KVFJHWK27C5FA358M526EJED=%E8%A9%B3%E7%B4%B0%E3%83%9E%E3%83%83%E3%83%81%E3%83%B3%E3%82%B0%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%85%B1%E6%9C%89%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 privacy-and-data-handling=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%A8%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E3%82%8A%E6%89%B1%E3%81%84 h_01KVFJHWK2BN2T7BTXANAWAX4B=%E3%83%97%E3%83%A9%E3%82%A4%E3%83%90%E3%82%B7%E3%83%BC%E3%81%A8%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%96%E3%82%8A%E6%89%B1%E3%81%84 faq=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01KVFJHWK2XB5VF8V2KPG62QYV=%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F" />

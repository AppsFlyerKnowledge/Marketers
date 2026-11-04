---
title: 新しいGoogle EU同意ポリシーのサポート
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2024-02-07T07:28:17Z'
  edited_at: '2026-10-14T09:30:19Z'
  id: 22310731147153
  locale: ja
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ja/articles/22310731147153
---
> **概要：** AppsFlyer は、マーケティング担当者がデジタル市場法（DMA）を遵守し、Google での広告の価値を向上できるよう支援しています。DMA への準拠と広告価値の最適化に関するよくある質問への回答をご覧ください。

<div id="overview" />

## 概要

Google は、 <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">デジタル市場法</Anchor>（DMA）の施行に備えて、<Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">EUユーザーの同意ポリシー</Anchor>を更新しています。Googleの公式<Anchor target="_blank" href="https://ads.google.com/lp/appcampaigns/attribution/">アプリアトリビューションパートナー</Anchor>として、AppsFlyerはポリシー変更に適応しながら、広告主がGoogleでの広告を最大限に活用できるように対応しています。更新されたポリシーは、2024年3月6日現在有効です。

<div id="relevant-integrations-and-continued-use-of-google-features" />

## 関連する連携とGoogle機能の継続使用

<div id="which-integrations-are-involved" />

<Accordion title="どの連携が関係していますか？">

次の連携が、Googleの新しいEU同意ポリシーに関連します：

* Google 広告(`googleadwords_int`)
* GMP DV360 (`dv360_int`)

これらの連携によるアプリのエンドユーザーが欧州経済領域（EEA）または英国に拠点を置いている場合は、Googleの新しいEU同意ポリシーの要件に準拠するために必要な措置を必ず講じてください。

<div id="note" />

> 📘 **注**
>
> 従来のGoogleマーケティングプラットフォーム DV360/CMの連携（`doubleclick_int`）は非推奨となり、Googleの新しいEU同意ポリシーではサポートされなくなります。この連携を使用している場合は、 <Anchor target="_blank" href="/marketers/ja/docs/bulletin-google-marketing-platform-gmp-integration-transition">新しいDV360連携 （dv360\_int）に移行</Anchor>してください。

</Accordion>

<div id="what-must-i-do-to-continue-using-googles-features" />

<Accordion title="Googleの機能を引き続き使用するにはどうすればよいですか？">

マーケティング担当者は、計測、広告のパーソナライズ、リマーケティングに関連する Google 広告と GMP DV360 の機能を引き続き使用するために、個人データの使用について EEA および英国のエンドユーザーから同意を得る必要があります。

</Accordion>

<div id="updating-the-appsflyer-sdk" />

## AppsFlyer SDKの更新

<div id="what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk" />

<Accordion title="AppsFlyer SDK経由で同意データ送信を実装する手順">

AppsFlyer SDK（v6.13.1以降）は、Googleの要件を満たすために、各イベントとともに必要な同意データを送信できます。

* AndroidまたはiOSアプリに適用できる最新バージョン（Android v6.13.0+、iOS -v6.13.1+）に、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">SDKをアップデート</Anchor>してください。
* SDKアップデートが完了したら、DMAをサポートするための実装手順を<Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">こちら</Anchor>から参照してください。

</Accordion>

<div id="sending-consent-data" />

## AppsFlyerへの同意データの送信

<div id="how-do-i-send-consent-data-to-appsflyer" />

<Accordion title="同意データをAppsFlyerに送信するには？">

必要な同意データを AppsFlyerに送信するために2つのオプションがあります：

* [**SDKまたはS2S API経由で直接送信：**](#appsflyer-sdkの更新) SDKを使用して同意データをAppsFlyerに直接送信できます。Android または iOS アプリに適用できます。
* **TCF文字列経由：** 同意管理プラットフォーム (CMP) を現在使用している、または使用する予定のマーケティング担当者は、標準の IAB TCF 文字列 (TCF V2.2) を通じてデータ項目を送信できます。同意されたベンダーのリストには、必ず Google ベンダー ID (755) を含めてください。

その後、AppsFlyer は顧客が同意シグナルを Google に送信できるようにします。ただし、AppsFlyer はエンドユーザーの同意を収集、変更、またはコントロールしないことに注意することが重要です。Googleを利用するマーケティング担当者は、必要な同意フィールドを収集する責任があります。

<Anchor target="_blank" href="https://appsflyer.wistia.com/medias/0tnlyre8ai">同意データをAppsFlyerに送信する方法を解説した動画はこちら</Anchor>

</Accordion>

<div id="which-consent-values-does-appsflyer-send-to-google" />

<Accordion title="AppsFlyerはどの同意値をGoogleに送信しますか？">

エンドユーザーの同意値は、関連する AppsFlyer連携（`googleadwords_int` および `dv360_int`）において、以下のフィールドを使用してGoogleに送信されます：

| AppsFlyerのフィールド | Googleのフィールド(1) | 値 | フィールドの説明 |
| --- | --- | --- | --- |
| <span id="gdpr_applies"></span>gdpr\_applies | eea | true/false (2) | このユーザーにGDPR（DMA）が適用されるかどうか |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true/false | ユーザーが自分のデータをパーソナライズ広告に使用することに同意したかどうか |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true\/false | ユーザーがユーザーデータをGoogleに送信することに同意したかどうか |

1. (1) <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">各フィールドについては、Google の定義</Anchor>を参照してください。
2. DMAがユーザーに適用されない場合、AppsFlyerは `gdpr_applies=false` 以外の同意項目の送信を控えるよう提案

</Accordion>

<div id="sending-consent-datafaq" />

### AppsFlyerへの同意データの送信 - よくある質問

<div id="do-i-have-control-over-consent-data-for-nonue-users" />

<Accordion title="同意データをGoogleに送信しないという選択肢はありますか？">

AppsFlyer は、GDPRがエンドユーザーに適用されないと思われる場合（EUまたは英国圏外など）の広告主が、Googleに同意データを送信しないようにすることができます。これは、関連する連携済みパートナー画面で Non EU users トグルをオンに設定することで適用されます。

<div id="important" />

> 🚧 **重要！**
>
> このオプションを使用する前に、広告主は法務部とプライバシー専門家から承認を得て、ポリシーに沿っていることを確認することをおすすめします。参照定義については、Googleの<Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">同意モードに関する記事</Anchor> を参照してください。

**同意データをGoogleと共有しないようにする：**

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**へ移動します。
2. 関連する媒体名を検索し、**連携設定**をクリックします。
3. 連携タブで、**Non EU users**トグルをオンにします。

<Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="595px" />

</Accordion>

<div id="is-consent-needed-for-mobile-web-events" />

<Accordion title="モバイルウェブイベントにも同意は必要ですか？">

現状では、モバイルアプリイベントのみがGoogleと共有され、ウェブイベントの同意データをAppsFlyerと共有する必要はありません。もしユーザーがウェブからアプリに移行した場合、同意はアプリ内で収集されます。

</Accordion>

<div id="which-countries-does-googles-eu-consent-policy-cover" />

<Accordion title="Google DMAの同意はどの国に適用されますか？">

デジタル市場法（DMA）は、EUおよびEEA（欧州経済領域）内のユーザーに適用され、<Anchor target="_blank" href="https://www.gov.uk/eu-eea">影響を与えます</Anchor>。**英国とスイス**はEUの一部ではありませんが、Googleは同意ポリシーを延長し、これらの国も対象にすることを決定しました。

</Accordion>

<div id="whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way" />

<Accordion title="コンプライアンスに準拠した方法でユーザーの同意を求めるには、どのような方法を推奨していますか？">

AppsFlyerでは、DMAに準拠した方法で同意を得るために、自社の法務部に相談することをお勧めします。<Anchor target="_blank" href="https://support.google.com/google-ads/answer/14009343?hl=en&sjid=3762335249108620505-NC#app-consent">Googleは一般的な手順</Anchor>を提示していますが、プロンプトには特定の言語は提示しません。

</Accordion>

<div id="how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags" />

<Accordion title="AppsFlyerはTCF文字列をGoogle DMAの同意フラグにどのように変換していますか？">

AppsFlyerがCMPから（AppsFlyer SDKまたはS2Sを介して）TCF文字列を受信すると、AppsFlyerサーバーで処理および変換されます。Googleが推奨する、次の変換がGoogleにマッピングされて送信されます。

| AppsFlyerが収集した文字列 | Googleの同意フラグ | 説明 |
| --- | --- | --- |
| `gdpr_applies=1/0` | `eea=1/0` | 各ユーザーにDMAが適用できるかどうかを識別 |
| `ad_user_data` | `ad_user_data=1` | Googleが目的1で同意し、目的7で同意／正当な利益がGoogleに与えられた場合 |
| `ad_user_data` | `ad_user_data=0` | 目的1でGoogleに同意が得られず、目的7でGoogleに同意/正当な利害関係が得られない場合 |
| `ad_personalization` | `ad_personalization=1` `ad_personalization=0` | 目的3および4でGoogleに同意する場合、目的3および4でGoogleに同意しない場合 |

</Accordion>

<div id="if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk" />

<Accordion title="同意データを送信するには、AppsFlyerとFirebase SDKの両方を更新する必要がありますか？">

はい。Googleは、Firebaseからのユーザー同意データとAppsFlyerから送信されたデータをマージしないため、AppsFlyerから送信される各イベントに同意データを含める必要があります。そのため、同意データはAppsFlyerに送信する必要があり、AppsFlyerからGoogleに転送されます。同様に、AppsFlyerと同意データを共有するだけでは、Firebase SDKの要件には不十分です。つまり、AppsFlyerとFirebaseの両方にデータを送信する必要があります。

</Accordion>

<div id="preparing-for-the-upcoming-changes" />

## 今後の変更に備える方法

<div id="how-can-i-prepare-for-the-upcoming-changes" />

<Accordion title="次の準備手順を実行します。">

<div id="address-user-consent-in-the-european-economic-area-eea" />

#### 欧州経済領域 (EEA) および英国におけるユーザーの同意に対処する

会社の法律顧問と協力してください。彼らが、Google などのパートナーと共有しているデータに対する欧州のユーザー同意ポリシーの影響についてのインサイトを提供してくれます。必要に応じて、「プライバシー設定」や「プライバシーの選択」などのプライバシープロンプトを実装して、アプリユーザーからマーケティングや広告に関連するユーザーの同意シグナルを収集します。

<div id="verify-cmp-compliance-and-tcf-2223-support" />

#### CMPコンプライアンスとTCF 2.2対応の確認

同意管理プラットフォーム（CMP）が、最新の透明性および同意フレームワーク TCFバージョンであるTCF 2.2をサポートしていることを確認してください。TCF は、Google EU の新しい同意要件についても十分な情報を持っている必要があり、TCF を通じてそれをサポートする方法についてアドバイスできるはずです。

<div id="implement-the-newest-sdkserver-to-server-s2s-apis" />

#### 最新の SDK/サーバー間 (S2S) API を実装する

SDK または S2S APIコールを使用して、新しい同意フィールドを送信するには、次のオプションを検討してください：

* **SDKの使用：**
  * 最新バージョンのiOS および Androidアプリ用のAppsFlyer SDKを実装する（Android v6.13.0以降、iOS v6.13.1以降）
  * <Anchor target="_blank" href="/marketers/ja/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">同意データの送信</Anchor>方法を選択する
* **<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile?">S2SAPI</Anchor>コールの使用：**
  * アプリ内イベントをAppsFlyerに送信する前に、各イベントの `consent_data` オブジェクトを含むように API コールを更新します。 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">実行方法を</Anchor>参照してください。

<div id="transition-from-the-legacy-gmp-integration-doubleclick" />

#### 従来のGMP連携（DoubleClick）からの移行

従来の AppsFlyer GMP 連携（doubleclick\_int）をまだ使用している場合は、2024年第1四半期中に新しいバージョン（dv360\_int）への移行を完了してください。従来の連携は**EUの同意と互換性がなく**、まもなく非推奨になります。詳細は <Anchor target="_blank" href="/marketers/ja/docs/bulletin-google-marketing-platform-gmp-integration-transition">こちら</Anchor>をご覧ください。

</Accordion>

<div id="impact-on-advertising-activityfaq" />

## 広告活動への影響 - よくある質問

<div id="how-will-the-upcoming-change-impact-my-remarketing-campaigns" />

<Accordion title="今後の変更はリマーケティング キャンペーンにどのような影響を及ぼしますか？">

Google が広告目的で自分のデータを使用することに同意しない EU および英国のユーザーは、Google 広告および DV360 によるアトリビューションには含まれません。これは、AppsFlyer がそれらのアトリビューションを特定できないことを意味します。  
GoogleとAppsFlyerは、GoogleのDMA規制の解釈に基づいて、ad\_user\_data=0 でもアトリビューションを実行できるエッジケースがいくつかあります。

</Accordion>

<div id="how-will-the-upcoming-change-affect-my-audiences" />

<Accordion title="今後の変更はオーディエンスにどのような影響を与えますか？">

変更は、オーディエンスに表示され、Google のリマーケティング キャンペーンに表示される EEA および英国のユーザーの数に影響を与える可能性があります。EEA および英国に拠点を置くユーザーは、情報を Google と共有する前に同意する必要があります。同意しないユーザーは Google 側の対象ユーザーから除外され、キャンペーンの対象にはなりません。これにより、ユーザーから同意を得る方法と、ビジネスや広告活動にどのような影響を及ぼす可能性があるかという問題が生じます。<Anchor target="_blank" href="/marketers/ja/docs/audiences-user-identifier-policy#eu-digital-markets-act">オーディエンスへの変更について詳しくは、こちらをご覧ください</Anchor>。

</Accordion>

<div id="further-information-and-contact-details" />

## 追加情報および問い合わせ詳細

さらに質問や不明な点がある場合は、以下までご連絡ください：

* Google の要件や、これらのアップデートが Google データに及ぼす影響についてご不明な点がある場合は、<Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy-help/">Google のヘルプ記事</Anchor> をご覧いただくか、Google の担当者に直接お問い合わせください。
* AppsFlyer の EU エンドユーザー同意フィールドのサポートに関するご質問については、AppsFlyer CSM にお問い合わせいただくか、[hello@appsflyer.com](mailto:hello@appsflyer.com)までお問い合わせください。
* 参照定義については、Google の <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">同意モードに関する記事</Anchor> を参照してください。

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HP195KV35FD6X67WTMXJWWSZ=%E6%A6%82%E8%A6%81 relevant-integrations-and-continued-use-of-google-features=%E9%96%A2%E9%80%A3%E3%81%99%E3%82%8B%E9%80%A3%E6%90%BA%E3%81%A8google%E6%A9%9F%E8%83%BD%E3%81%AE%E7%B6%99%E7%B6%9A%E4%BD%BF%E7%94%A8 h_01HP1M37V1CYW5T5E4K1ES3NQA=%E9%96%A2%E9%80%A3%E3%81%99%E3%82%8B%E9%80%A3%E6%90%BA%E3%81%A8google%E6%A9%9F%E8%83%BD%E3%81%AE%E7%B6%99%E7%B6%9A%E4%BD%BF%E7%94%A8 01HP1KN2H7NTS2V1S2PGF0C41N=which-integrations-are-involved h_01HP2HRPJR72Z0R5VEG5N36CN2=%E6%B3%A8 h_01HP1K1088SJK60QRSTQF4WF6S=what-must-i-do-to-continue-using-googles-features updating-the-appsflyer-sdk=appsflyer-sdk%E3%81%AE%E6%9B%B4%E6%96%B0 h_01HP1Z2G2M56DDQS9T47GMCFHJ=appsflyer-sdk%E3%81%AE%E6%9B%B4%E6%96%B0 h_01HP1ZASRQGABCEFV67P961XAV=what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk how-consent-data-is-sent=appsflyer%E3%81%B8%E3%81%AE%E5%90%8C%E6%84%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%80%81%E4%BF%A1 h_01HP1KPSMCH3EG373BWVQZM4ZT=appsflyer%E3%81%B8%E3%81%AE%E5%90%8C%E6%84%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%80%81%E4%BF%A1 h_01HP1JJ2AYHYJET9GYMXA93E86=how-do-i-send-consent-data-to-appsflyer h_01HP1JJ2AYWRBREW5GD0KPDF1R=which-consent-values-does-appsflyer-send-to-google sending-consent-data%E2%80%94faq=appsflyer%E3%81%B8%E3%81%AE%E5%90%8C%E6%84%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%80%81%E4%BF%A1---%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HR1X08VZ5MEAV01E9X54KAQS=appsflyer%E3%81%B8%E3%81%AE%E5%90%8C%E6%84%8F%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E9%80%81%E4%BF%A1---%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HP1JJ2AYZ57G0GMR8QRDTEZ7=do-i-have-control-over-consent-data-for-nonue-users h_01HP2MRPFA2ECJGAZ93NQHVD2J=%E9%87%8D%E8%A6%81 01HVE9TVZWTRW3VQ8TSXWA13QM=is-consent-needed-for-mobile-web-events h_01JVYS49FCZT3Z91KNACNR6GET=which-countries-does-googles-eu-consent-policy-cover h_01HRXZYZJBDTP8CHJDHQ187CTN=whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way 01HR6SD3PBWN5X9AHT66ZADQ3R=how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags 01J2V4XRKRSEPA6KPJFMSTHE1F=if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk what-i-can-do-on-my-side=%E4%BB%8A%E5%BE%8C%E3%81%AE%E5%A4%89%E6%9B%B4%E3%81%AB%E5%82%99%E3%81%88%E3%82%8B%E6%96%B9%E6%B3%95 01HR1XYXRDVEW6H9Q3WP17E2N3=%E4%BB%8A%E5%BE%8C%E3%81%AE%E5%A4%89%E6%9B%B4%E3%81%AB%E5%82%99%E3%81%88%E3%82%8B%E6%96%B9%E6%B3%95 h_01HP1JJ2AYFHRRDYZS8YFYE6WP=how-can-i-prepare-for-the-upcoming-changes address-user-consent-in-the-european-economic-area-eea-and-in-the-uk=%E6%AC%A7%E5%B7%9E%E7%B5%8C%E6%B8%88%E9%A0%98%E5%9F%9F-eea-%E3%81%8A%E3%82%88%E3%81%B3%E8%8B%B1%E5%9B%BD%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E5%90%8C%E6%84%8F%E3%81%AB%E5%AF%BE%E5%87%A6%E3%81%99%E3%82%8B h_01HPGNBQCTJFVZR99BY6E5J2JF=%E6%AC%A7%E5%B7%9E%E7%B5%8C%E6%B8%88%E9%A0%98%E5%9F%9F-eea-%E3%81%8A%E3%82%88%E3%81%B3%E8%8B%B1%E5%9B%BD%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E5%90%8C%E6%84%8F%E3%81%AB%E5%AF%BE%E5%87%A6%E3%81%99%E3%82%8B verify-cmp-compliance-and-tcf-22-support=cmp%E3%82%B3%E3%83%B3%E3%83%97%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%82%B9%E3%81%A8tcf-22%E5%AF%BE%E5%BF%9C%E3%81%AE%E7%A2%BA%E8%AA%8D h_01HPGNC0HAMA7Z0B4DNV2QSFYG=cmp%E3%82%B3%E3%83%B3%E3%83%97%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%82%B9%E3%81%A8tcf-22%E5%AF%BE%E5%BF%9C%E3%81%AE%E7%A2%BA%E8%AA%8D implement-the-newest-sdkservertoserver-s2s-apis=%E6%9C%80%E6%96%B0%E3%81%AE-sdk%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E9%96%93-s2s-api-%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B h_01HPGNCAG3M9XPHDTP03WHQQ9F=%E6%9C%80%E6%96%B0%E3%81%AE-sdk%E3%82%B5%E3%83%BC%E3%83%90%E3%83%BC%E9%96%93-s2s-api-%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B transition-from-the-legacy-gmp-integration-doubleclick=%E5%BE%93%E6%9D%A5%E3%81%AEgmp%E9%80%A3%E6%90%BAdoubleclick%E3%81%8B%E3%82%89%E3%81%AE%E7%A7%BB%E8%A1%8C h_01HPGNCHP6SSFCVZ3P4AG0N1FB=%E5%BE%93%E6%9D%A5%E3%81%AEgmp%E9%80%A3%E6%90%BAdoubleclick%E3%81%8B%E3%82%89%E3%81%AE%E7%A7%BB%E8%A1%8C impact-on-my-advertising-activity=%E5%BA%83%E5%91%8A%E6%B4%BB%E5%8B%95%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF---%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HP1PKNZN32TQYHGJNNM3JFVZ=%E5%BA%83%E5%91%8A%E6%B4%BB%E5%8B%95%E3%81%B8%E3%81%AE%E5%BD%B1%E9%9F%BF---%E3%82%88%E3%81%8F%E3%81%82%E3%82%8B%E8%B3%AA%E5%95%8F h_01HP1PKNZN0VJGYAPFHR5JVV5H=how-will-the-upcoming-change-impact-my-remarketing-campaigns h_01HP4K2ZJW11BFSKNPRH7FA092=how-will-the-upcoming-change-affect-my-audiences further-information-and-contact-details=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1%E3%81%8A%E3%82%88%E3%81%B3%E5%95%8F%E3%81%84%E5%90%88%E3%82%8F%E3%81%9B%E8%A9%B3%E7%B4%B0 h_01HQ2VJES04CYF4J8YBB4GQS73=%E8%BF%BD%E5%8A%A0%E6%83%85%E5%A0%B1%E3%81%8A%E3%82%88%E3%81%B3%E5%95%8F%E3%81%84%E5%90%88%E3%82%8F%E3%81%9B%E8%A9%B3%E7%B4%B0" />

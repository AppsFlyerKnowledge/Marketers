---
title: ChatGPT 広告（OpenAI）の連携設定
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-07-05T13:42:23Z'
  edited_at: '2026-10-14T09:22:46Z'
  id: 48439655791249
  locale: ja
  section: Measure paid media
  section_id: 6550990672401
  url: https://support.appsflyer.com/hc/ja/articles/48439655791249
---
> **概要：** ChatGPT 広告 は AppsFlyer の連携パートナーであり、OpenAI の広告プラットフォームです。この連携を設定することで、ChatGPT の広告キャンペーンによって獲得したモバイルアプリのインストール、アプリ内イベント、Webサイトのコンバージョンを計測・アトリビューションできます。

<div id="about-the-integration-with-chatgpt-ads" />

## ChatGPT 広告との連携について

AppsFlyer と ChatGPT 広告（OpenAI）の連携により、ChatGPT 広告のキャンペーンによって獲得したアプリのインストール、アプリ内イベント、および Web サイトのコンバージョンを計測・アトリビューションできます。この連携は、モバイルアプリと Web サイトの両方の計測に対応しています。

* **モバイルアプリ** - AppsFlyer は ChatGPT 広告のキャンペーンに対してインストールおよびリエンゲージメントを計測し、アプリ内イベントのポストバックを送信します。
* **Web サイト** - AppsFlyer は、AppsFlyer Web SDK で取得したページビュー、コンテンツ閲覧、購入などの Web イベントを、ChatGPT 広告 の JavaScript ピクセルに加えて（またはその代わりとして）、ChatGPT 広告 の Conversions API（CAPI）へ送信します。

Web サイトで ChatGPT 広告のピクセルも利用している場合、ChatGPT 広告は共通のイベント ID を使用して、サーバーサイド（CAPI）のイベントとピクセルイベントを重複排除します。そのため、両方を並行して利用しても、コンバージョン数が重複して計上されることはありません。

AppsFlyerへ送信するイベントペイロードに、この共通IDを `af_customer_event_id` として含めてください。（詳細：`af_customer_event_id`Webサイトの連携af\_customer\_event\_id）

<div id="set-up-the-integration" />

## 連携設定

計測対象となるモバイルアプリおよび Web サイトごとに、それぞれ個別に連携を設定します。それぞれについて、ChatGPT 広告（OpenAI）の Ads Manager アカウントから取得した Pixel ID と API Key が必要です。

**前提条件：**

* 連携を設定する前に、ChatGPT 広告のアカウントを開設してください。
* モバイルアプリとWebサイトアプリがAppsFlyerに設定されている必要があります。（<Anchor target="_blank" href="/marketers/ja/docs/adding-an-app-to-appsflyer">詳細</Anchor>）

**連携設定方法：**

1. **有効化するには：** AppsFlyer のサイドメニューから、［**Collaborate**］>［**Partner Integrations**］>［**Marketplace**］ タブを選択します。  
   **編集するには：** AppsFlyer のサイドメニューから、［**Collaborate**］>［**Partner Integrations**］>［**Active integrations**］ タブを選択します。
2. 対象に応じて、以下のいずれかの連携を設定します。

* [**モバイルアプリ**](#モバイルアプリの連携) - ChatGPT 広告キャンペーンによるインストール、リエンゲージメント、およびアプリ内イベントをアトリビューションします。
* [**Web サイト**](#webサイトの連携) - Web コンバージョンイベントを ChatGPT 広告の Conversions API に送信し、ChatGPT 広告のピクセルとの重複排除を行います。

<div id="integrate-your-mobile-app" />

## モバイルアプリの連携

以下の手順に従って、モバイルアプリ向けのアトリビューションおよびアプリ内イベントのポストバックを ChatGPT 広告用に設定します。

モバイルアプリを連携するには：

1. AppsFlyer のサイドメニューから、［**Collaborate**］>［**Partner Integrations**］>［**Marketplace**］ タブを選択します。
2. ドロップダウンメニューから対象のモバイルアプリを選択します。  
   **注意：** Android アプリや iOS アプリなど、アプリが対応する各プラットフォームごとに、この手順を繰り返す必要があります。
3. <strong>ChatGPT 広告（OpenAI）</strong>を検索し、［**Integrate**］ をクリックします。
4. 以下で説明する内容に従って、各タブの設定を完了します。

<div id="integration-tab" />

<Accordion title="連携タブ">

<div id="activate-partner" />

#### パートナーの有効化

**連携を有効にするには：**

**パートナーを有効化**のトグルをオンにします。

**重要な注意点：** ChatGPT 広告を利用している間は、このトグルをオンのままにしてください。連携を無効にすると、ChatGPT 広告キャンペーンに対するアトリビューションとポストバックの送信が停止します。  
詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>をご覧ください。

<div id="general-settings" />

#### 一般設定

以下の認証情報を入力します。

* **Pixel ID** - Pixel は ChatGPTの広告マネージャー上で作成されます。広告マネージャーアカウントのコンバージョンタブから取得してください。
* **API key** - Events API の呼び出しを認証するために API Key が必要です。ChatGPTの広告マネージャーアカウントの コンバージョンタブから取得してください。   
  **注意：** 必ずコンバージョンの API Key を使用してください。Ads Management API Key では必要な権限が付与されておらず、CAPI Key が必要です。

**高度なマッチングデータ共有：** AppsFlyerへ送信されるイベント情報に、ハッシュ化されたメールアドレス、電話番号、名、姓などの高度なマッチング用フィールドが含まれている場合、これらの情報をChatGPT広告と共有するには、高度なマッチングデータの共有をオンにします。（詳細：<Anchor target="_blank" href="/marketers/ja/docs/advanced-matching-data-sharing">高度なマッチングデータ共有</Anchor>）

<div id="default-postbacks" />

#### デフォルトのポストバック

ポストバックとは、AppsFlyer が ChatGPT 広告に対して、アトリビューションされたイベント（インストールやアプリ内アクションなど）を通知するサーバー間通信（Server-to-Server）です。このセクションには、設定されているポストバックが表示されます。インストールおよびリエンゲージメントのポストバック設定について<Anchor target="_blank" href="/marketers/ja/docs/set-up-re-attribution-window">詳しくはこちらをご覧ください。</Anchor>

デフォルトのポストバック設定について<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">詳しくはこちらをご覧ください。</Anchor>

<div id="in-app-event-settings" />

#### アプリ内イベントの設定

ChatGPT 広告にアプリ内イベントのポストバックを送信するには、以下の認証情報を入力します。

* Pixel ID
* API key

詳細については、[前述の 一般設定](#一般設定) を参照してください。

<div id="in-app-event-postbacks" />

#### アプリ内イベントのポストバック

ChatGPT Ads に送信するアプリ内イベントのポストバックを設定します。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration">（詳細）</Anchor>

**アプリ内イベントのポストバック**を有効にするには：

**アプリ内イベントのポストバック**のトグルをオンにします。

**アプリ内イベントポストバック期間**

AppsFlyer が ChatGPT 広告にアプリ内イベントのポストバックを送信する期間を設定します。この期間は、インストール、リエンゲージメント、または再アトリビューションを起点として適用されます。詳しくはこちらをご覧ください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration">（詳細）</Anchor>

**イベントのマッピング**

ChatGPT 広告の対応するイベントと一致するように、イベント名をマッピングしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#イベントマッピング">（詳細）</Anchor>

ChatGPT 広告は以下の標準イベントをサポートしています。また、以下に該当しないイベントについては **Custom** をフォールバックとして利用できます。

| ChatGPT 広告のイベント名 | 使用するタイミング |
| --- | --- |
| page\_viewed | ユーザーが重要なページにアクセスまたは閲覧した場合。 |
| contents\_viewed | ユーザーが商品、掲載情報、記事、またはコンテンツを閲覧した場合。 |
| items\_added | ユーザーがカート、セット、または選択リストに 1 つ以上の商品を追加した場合。 |
| checkout\_started | ユーザーが購入手続きを開始した場合。 |
| order\_created | 購入が完了した場合。 |
| registration\_completed | ユーザーがアカウント登録またはイベント登録を完了した場合。 |
| lead\_created | ユーザーがお問い合わせフォームを送信した場合、または連絡を希望した場合。 |
| appointment\_scheduled | ユーザーが商談、デモ、または相談の予約を行った場合。 |
| trial\_started | 無料トライアルを開始した場合。 |
| subscription\_created | 有料サブスクリプションを開始した場合。 |
| app\_opened | モバイルアプリを起動した場合。 |
| custom | 上記の標準イベントに該当しないすべてのイベント。 |

**イベントの重複排除**

WebサイトでもChatGPT広告のピクセルを使用している場合は、AppsFlyerとChatGPT広告の両方に同じイベントIDを送信し、イベントの重複を排除します。

* AppsFlyerへ送信するイベントペイロードに `af_customer_event_id` を含めます。Web SDKの場合は eventValue 内、S2S（サーバー間）APIの場合は event\_value 内に設定します。
* 対応するPixelイベントにも同じ値を送信します。

AppsFlyerは、この値をイベントIDとしてChatGPT広告へ転送します。ChatGPT広告はこのIDを使用して、AppsFlyerから受信したサーバーサイドイベントとPixelイベントの重複を排除します。これにより、AppsFlyerではコンバージョンが1回だけカウントされます。

`af_customer_event_id` を送信しない場合、AppsFlyerがイベントIDを自動的に生成します。ただし、このIDはPixelイベントのIDとは一致しません。

詳細については、 「AppsFlyer Web SDK の実装」を参照してください。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

ChatGPT 広告（OpenAI）は計測リンクをサポートしています。

<div id="choose-your-attribution-type" />

#### アトリビューションの種類を選択する

キャンペーンの要件に応じて、最終ページURLとして単一プラットフォーム向けの計測りリンクまたは<Anchor target="_blank" href="/marketers/ja/docs/onelink-guide">OneLink</Anchor>、もしくはSmart Scriptを実装したランディングページへ遷移させるのかを決定します。

**推奨**：広告の遷移先にはランディングページのURL末尾に&pid=openai\_intを追加したものを使用し、ランディングページ側に予め実装した<Anchor target="_blank" href="/marketers/ja/docs/onelink-smart-script-overview">Smart Script</Anchor>または<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor>を使って、ユーザーをApp StoreまたはGoogle Playへ誘導してください。

<div id="select-parameters" />

#### パラメーターを選択する

計測リンクに含めるパラメーターを選択します。

* **キャンペーン名**や**サイトID**など、 計測リンクに含めるパラメーターを選択し、 **クリックスルールックバック期間**を設定します。 AppsFlyerでは、デフォルトとして 7日間を推奨しています。 AppsFlyerによって、 ChatGPT 広告のキャンペーンで使用する計測リンクが自動的に生成されます。
* 以下の動的URLマクロを使用すると、ChatGPTによって 次のURLパラメーターを 自動的に入力できます。
  * `af_partner_account_id={ad_account_id}`
  * `af_c_id={campaign_id}`
  * `af_adset_id={ad_group_id}`
  * `af_ad_id={ad_id}`
  * `clickid={oppref}`

<strong>【重要】</strong>AppsFlyerがChatGPT広告の クリックIDを取得し、 ChatGPT広告へ送り返せるようにするには、 広告の遷移先がApp StoreまたはGoogle Playの場合、 必ず`clickid={oppref}`を使用してください。広告の遷移先が Smart Scriptを実装した ランディングページの場合は、 受信URLの`oppref`パラメーターを取得し、 送信URLの`clickid`へ マッピング してください。

* なお、キャンペーン名、アドセット名など、名前フィールドのマクロはサポートされていません。

**注意：** 生成されるリンクには、AppsFlyerにおけるChatGPT Adsの連携IDである`openai_int`が含まれます。

計測リンクについて<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#attribution-link-tab">詳しくはこちらをご覧ください。</Anchor>

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

現在、ChatGPT 広告は Cost API 連携に対応していません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

ChatGPT 広告から広告収益データを取得することはできません。キャンペーンの最適化に広告収益データを利用する場合は、ポストバックまたは UA シグナルを使用してデータを共有してください。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

**アドネットワーク権限**をオンにすると、ChatGPT 広告チームのメンバーに対してデータへのアクセス権限を付与できます。有効化後は、連携設定の変更、リテンションレポートおよびコホートレポートへのアクセス、集計済みのコンバージョンデータや収益データの閲覧など、付与する権限を個別に選択できます。なお、ChatGPT 広告のアトリビューションを無効にしている場合でも、権限を付与することは可能です。

詳細は<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#permissions-tab">こちら</Anchor>をご覧ください。

</Accordion>

<div id="integrate-your-website" />

## Webサイトの連携

以下の手順に従って、Web サイト向けに ChatGPT 広告へのサーバーサイドイベント送信を設定します。

**Webサイトを連携するには：**

1. AppsFlyer のサイドメニューから、［**Collaborate**］>［**Partner Integrations**］>［**Marketplace**］ タブを選択します。
2. ドロップダウンメニューからWebサイトアプリを選択します。
3. **ChatGPT 広告（OpenAI）** を検索し、［**Integrate**］ をクリックします。
4. 以下で説明する内容に従って、連携タブの設定を完了します。

<div id="integration-tab::2739744d" />

<Accordion title="連携タブ">

<div id="activate-partner-1" />

#### パートナーの有効化

**連携を有効にするには：**

**パートナーを有効化**のトグルをオンにします。

**重要な注意点：** ChatGPT 広告を利用している間は、このトグルをオンのままにしてください。連携を無効にすると、Web サイトのイベント転送が停止します。  
詳細は、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>をご覧ください。

<div id="in-app-event-settings-1" />

#### アプリ内イベントの設定

ChatGPT 広告にイベントのポストバックを送信するには、以下の認証情報を入力します。

* **Pixel ID** - Pixel は ChatGPTの広告マネージャー上で作成されます。広告マネージャーアカウントのコンバージョンタブから取得してください。
* **API key** - Events API の呼び出しを認証するために API Key が必要です。ChatGPTの広告マネージャーアカウントの コンバージョンタブから取得してください。

**高度なマッチングデータ共有：** AppsFlyerへ送信されるイベント情報に、ハッシュ化されたメールアドレス、電話番号、名、姓などの高度なマッチング用フィールドが含まれている場合、これらの情報をChatGPT広告と共有するには、高度なマッチングデータの共有をオンにします。（詳細：<Anchor target="_blank" href="/marketers/ja/docs/advanced-matching-data-sharing">高度なマッチングデータ共有</Anchor>）

<div id="in-app-event-postbacks-1" />

#### アプリ内イベントのポストバック

ChatGPT 広告に送信するイベントのポストバックを設定します。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration">（詳細）</Anchor>

**イベントポストバックを有効にするには：**

**アプリ内イベントのポストバック**のトグルをオンにします。

**イベントのマッピング**

AppsFlyer のイベントと ChatGPT 広告の対応するイベントを一致させるために、イベント名をマッピングします。ChatGPT 広告がサポートするイベントについては、前述の標準イベント一覧を参照してください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#イベントマッピング">（詳細）</Anchor>

</Accordion>

<div id="h_01KWVSPJ9WATTRLNK" />

<Accordion title="計測リンクタブ">

ChatGPT 広告（OpenAI）は、Web サイト連携では外部の計測リンクを使用しません。AppsFlyer Web SDK が Web イベントを計測し、それらを ChatGPT 広告の Conversions API に直接送信するため、リンクベースのアトリビューション設定は不要です。

</Accordion>

<div id="h_01KWVSPJ9WCOST" />

<Accordion title="コストタブ">

ChatGPT 広告との Web サイト連携では、コストデータは利用できません。

</Accordion>

<div id="h_01KWVSPJ9WADREV" />

<Accordion title="広告収益タブ">

ChatGPT 広告とのWebサイト連携では、広告収益データは利用できません。

</Accordion>

<div id="h_01KWVSPJ9WPERM" />

<Accordion title="権限タブ">

ChatGPT 広告とのWebサイト連携では、権限タブは利用できません。

</Accordion>

<div id="traits-and-limitations" />

## 特徴と制限事項

| 特性 | 説明 |
| --- | --- |
| サポート対象地域 | <Anchor target="_blank" href="https://help.openai.com/en/articles/20001245-ads-manager-availability">ChatGPT広告マネージャーが利用可能な国一覧</Anchor>をご確認ください。 |

<div id="see-also" />

> 📄 **参照：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携</Anchor>

<div data-zendesk-anchors="about-the-integration=chatgpt-%E5%BA%83%E5%91%8A%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KWS8SS8RE2VQ275MFB7CT39J=chatgpt-%E5%BA%83%E5%91%8A%E3%81%A8%E3%81%AE%E9%80%A3%E6%90%BA%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 set-up-the%20integration=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A h_01H95QTA3Z5HXW39AHAF8FMFWH=%E9%80%A3%E6%90%BA%E8%A8%AD%E5%AE%9A integrate-your-mobile-app=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E9%80%A3%E6%90%BA h_01KWVBQG0G85W6QJ8AT2520GTX=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E9%80%A3%E6%90%BA h_01KWVK5J7FBA81238JD4AD0219=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H95QTA3ZGEM34HY1A7NC8NX7=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01KWVKHV36H34XCHYBFRHNF8TB=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01KWVKZJ7AZ8Z4CFM8J0PV071A=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01JTDP2T0BFP5WP03X5EMXVAWA=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01KWVMZC74AQSN7BDQP2QQWBT4=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01KWVK5J7FE0ZF74NGXKSASMBV=attribution-link-tab h_01_choose-your-attribution-type=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E7%A8%AE%E9%A1%9E%E3%82%92%E9%81%B8%E6%8A%9E%E3%81%99%E3%82%8B choose-your-attribution-type=%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E7%A8%AE%E9%A1%9E%E3%82%92%E9%81%B8%E6%8A%9E%E3%81%99%E3%82%8B h_01_select-parameters=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC%E3%82%92%E9%81%B8%E6%8A%9E%E3%81%99%E3%82%8B select-parameters=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC%E3%82%92%E9%81%B8%E6%8A%9E%E3%81%99%E3%82%8B h_01KWVK5J7FK8BAQKEMNA35ABPY=cost-tab h_01KWVK5J7FQRYXQ9FGCWHWY16T=ad-revenue-tab h_01KWVK5J7G3E8NSNDG4CR9FA7N=permissions-tab integrate-your-website=web%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E9%80%A3%E6%90%BA h_01KWVSJRYSQEH12C5RH7BN4CC2=web%E3%82%B5%E3%82%A4%E3%83%88%E3%81%AE%E9%80%A3%E6%90%BA h_01KWVSPJ9WJERF84ZNGTS7P0HZ=integration-tab::2739744d activate-partner::3c5a91e7=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96-1 h_01KWVSPJ9WBQ2AS5JZPTJZPTRG=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96-1 inapp-event-settings::a3adef08=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A-1 h_01KWVSPJ9WV7ZQZD00ZB7T639X=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A-1 inapp-event-postbacks::c3d06354=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF-1 h_01KWVSPJ9WA7Q1M281Q5NBYHV7=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF-1 attribution-link-tab::3e2b1646=h_01KWVSPJ9WATTRLNK cost-tab::c486dc3c=h_01KWVSPJ9WCOST ad-revenue-tab::84884d8a=h_01KWVSPJ9WADREV permissions-tab::6f805250=h_01KWVSPJ9WPERM traits-and-limitations=%E7%89%B9%E5%BE%B4%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KX3DAS0FBTKGKE7CZJTDTY2X=%E7%89%B9%E5%BE%B4%E3%81%A8%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01KWVT1XJ2FKP1CACRV24C1R8E=%E5%8F%82%E7%85%A7" />

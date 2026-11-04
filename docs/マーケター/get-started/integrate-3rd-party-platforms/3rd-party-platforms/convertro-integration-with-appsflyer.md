---
title: ConvertroとAppsFlyerの連携
metadata:
  keywords:
    - Attribution
    - Convertro
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:37:56Z'
  edited_at: '2026-10-28T09:02:57Z'
  id: 207040636
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/207040636
---
> **概要：** AppsFlyerの連携済みパートナーであるConvertroは、広告施策の成果を正確に把握し、分析結果をすばやく施策に反映するための、マーケター向け自動化ツールを提供しています。コンバージョンに至る顧客の行動を詳細に収集するだけでなく、マーケティングミックスを科学的に最適化し、ROIを最大化するための予算配分を自動的に判断する技術を備えています。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-convertro" />

## Convertroの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

Convertroの設定で使用するのは、<strong>［連携］</strong>タブのみです。

パートナー設定画面のヘッダーについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

**初めて設定する場合**は、以下のトグルを操作します。［***パートナーを有効化***］をオンにすると、［連携］タブのパラメータを設定できるようになります。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

<div id="general-settings" />

### 一般設定

**ページURL、サイトID、クライアント名**

ConvertroとAppsFlyerの接続には、固有のページURL、サイトID、クライアント名を使用します。まだ取得していない場合は、連携の設定を進める前にConvertroから取得するか、以下の手順で取得してください。

[![](https://files.readme.io/74a1ea32d0667da1a4fe4797cb83f75639111b24c98f72d2caa721e6911e3015-360002220189.png)](https://files.readme.io/74a1ea32d0667da1a4fe4797cb83f75639111b24c98f72d2caa721e6911e3015-360002220189.png)

<div id="obtaining-the-client-name-page-url--site-id-from-the-convertro-platform" />

### Convertroでクライアント名、ページURL、サイトIDを取得する

クライアント名、ページURL、サイトIDを取得するには、Convertro管理画面にログインします。

**ページURL：**

[![](https://files.readme.io/f20c2e45146f0874d94dc84c4f61658e15274970f348896a40b2806d3fe540c9-204790263.png)](https://files.readme.io/f20c2e45146f0874d94dc84c4f61658e15274970f348896a40b2806d3fe540c9-204790263.png)

**サイトID：**

[![](https://files.readme.io/b60897bea0b640cb393bceecb57c14370b2ba074818160af0a25a53c7a8ce26b-204790283.png)](https://files.readme.io/b60897bea0b640cb393bceecb57c14370b2ba074818160af0a25a53c7a8ce26b-204790283.png)

**クライアント名：**

![](https://files.readme.io/2e5342006bdfff9e3b3c1dffdaed3e9d83ec2fe4c465b7918023a359776cee91-204595606.png)

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にConvertroへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

アプリをダウンロードしたすべてのユーザーのポストバックをConvertroに送信するには、<strong>［すべてのパートナーまたはオーガニックのイベント］</strong>を選択します。送信しない場合は、<strong>［オフ］</strong>を選択します。

［**保存**］をクリックします。

<div id="in-app-event-settings" />

### アプリ内イベントの設定

[![](https://files.readme.io/5c1d6841c7f8397d797964790c1f200d60a6ab81fe67eb2162b2a5e7c73462d3-360002200405.png)](https://files.readme.io/5c1d6841c7f8397d797964790c1f200d60a6ab81fe67eb2162b2a5e7c73462d3-360002200405.png)

このセクションでは、ポストバックを介してAppsFlyerのイベントをConvertroのイベントに対応付けます。

1. クライアント名、サイトID、ページURLを再度入力します。
2. ［アプリ内イベントポストバック］をオンにします。
3. SDKで定義されたすべてのイベントについて、送信対象を選択します。  
   **- このパートナーのイベントのみ**：このパートナーの成果として計測されたユーザーのイベント**のみ**を送信します。  
   **- すべてのパートナーまたはオーガニックのイベント**：すべてのユーザーのデータをパートナーに送信できます。
4. ［**イベントを追加**］をクリックし、SDKイベントをリストに追加します。
5. 以下のパラメータを設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリに実装したSDKまたはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名です。  <br />**ヒント**：リストに目的のイベントがない場合は、非オーガニックでインストールしたデバイスでそのイベントを発生させ、もう一度確認してください。 |
| **パートナーイベント識別子** | Convertro側で定義されている各イベントの一意の名前またはIDです。  <br />Convertroから対応するイベントIDを取得し、テキストフィールドに入力します。 |
| **収益を送信** | **オフの場合**：**af\_revenue**で指定した収益値を除き、リッチアプリ内イベントのすべてのパラメータをパートナーに送信します。  <br />**オンの場合**：収益値を含むすべてのパラメータを送信します（イベントに収益値がある場合）。 |

［**保存**］をクリックします。

この設定を保存すると、AppsFlyerはオーガニックと非オーガニックのすべてのインストールについて、次のデータをConvertroに送信し始めます。

* Converto Parameters
* AndroidおよびiOSのデバイスID
* メディアソース
* キャンペーン名
* クリック時刻
* ユーザーのIPアドレス
* ユーザーエージェント
* カスタマーユーザーID（任意、設定済みの場合）

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Convertroでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

このパートナーとの連携では、コストデータには対応していません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

このパートナーとの連携では、広告収益データには対応していません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

Convertroでは、権限の設定は利用できません。

</Accordion>

<div data-zendesk-anchors="h_01H9FK64HSFKW54BBRVB3W9ZR0=%E9%87%8D%E8%A6%81 setting-up-convertro=convertro%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK64HS75VDP07DGETASAH7=convertro%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK64HSK1B1Y9BRWP7AN96R=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FK64HS7VJWHF1QCWNYVBX8=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FK64HSCAYHB82DZX0JA2ZX=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A obtaining-the-client-name-page-url-site-id-from-the-convertro-platform=convertro%E3%81%A7%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E5%90%8D%E3%83%9A%E3%83%BC%E3%82%B8url%E3%82%B5%E3%82%A4%E3%83%88id%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B h_01H9FK64HSKR8N45RXQQC3VEW1=convertro%E3%81%A7%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E5%90%8D%E3%83%9A%E3%83%BC%E3%82%B8url%E3%82%B5%E3%82%A4%E3%83%88id%E3%82%92%E5%8F%96%E5%BE%97%E3%81%99%E3%82%8B default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FK64HTPK69QQ92DJ55RNVM=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK64HTGKXWW0FMN0T445FG=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FK64HTCM3H0243FVFDY0ET=attribution-link-tab h_01H9FK64HT9JHKBN5W8H16E6CK=cost-tab h_01H9FK64HTSP070RX7ZCYM7KE3=ad-revenue-tab h_01H9FK64HTCXAMY6TR186EE0M9=permissions-tab" />

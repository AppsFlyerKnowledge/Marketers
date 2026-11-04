---
title: OneLink Smart Scriptの概要
metadata:
  keywords:
    - OneLink
    - Adwords
    - Advertisers
    - referral
    - referal
    - landing
    - redirect
    - gclid
    - facebook
    - landing page
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2018-12-12T16:32:47Z'
  edited_at: '2026-10-28T09:20:01Z'
  id: 360000677217
  locale: ja
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ja/articles/360000677217
---
> **概要：** OneLink Smart Scriptを使用すると、流入元を問わず、モバイルWebサイトの訪問者をモバイルアプリへ誘導し、その成果を紐づけられます。

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

<div id="about-onelink-smart-script" />

## OneLink Smart Scriptについて

ユーザーは、自然流入や広告キャンペーンへの接触を通じて、アプリのストアページに到達する前にモバイルWebサイトを訪問します。ただし、この経路では次の2回のクリックが発生します。

* Webページへ移動するクリック
* Webページからアプリストアへ移動するクリック

このような経路では、アトリビューションやディープリンクに課題が生じます。最終的にアプリをダウンロードしたユーザーのインストールが、誤った流入元に紐づいたり、オーガニックとして扱われたりする可能性があります。最初のクリックがアドネットワーク、Google、オウンドメディアからのものであっても、この問題は起こり得ます。

OneLink Smart Scriptは、次の機能でこれらの課題を解決します。

* Webページへの誘導に使われた受信URLを基に、アプリストアへ誘導する固有の送信URL（長い形式のOneLink URL）を動的に生成します。
* アドネットワーク、SRN、Googleのクリック、オウンドメディアを含む、すべてのメディアソースについて、Webからアプリへの成果を正確に紐づけます。
* ディープリンクにも使用できます。
* どのWebページやランディングページでもスムーズに動作します。
* Smart Bannersを使用する必要はありません。   
  **注意**：Smart Bannersは多くの業種でコンバージョン促進に役立ち、開発者の作業なしで設定できますが、ユーザーの導線にバナーという接点が1つ加わります。
* マーケターがGoogleタグマネージャーで設定できます。

OneLink Smart Scriptには、次の2つのバージョンがあります。

<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2（推奨）**</Anchor>：初めてOneLink Smart Scriptを設定する場合は、このバージョンの使用をおすすめします。 AppsFlyerの管理画面で設定でき、開発者の実装作業も簡単になります。Googleタグマネージャーを使った設定にも対応しています。

<Anchor target="_blank" href="/marketers/ja/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1（旧版）**</Anchor>：すでにOneLink Smart Scriptを設定している場合は、このバージョンのドキュメントを参照してスクリプトを保守・編集してください。 **注意**：必須ではありませんが、V2への移行をご検討ください。 

<div id="note" />

> 📘 **注意**
>
> OneLink Smart Scriptが要件に合うか迷っていませんか？ AppsFlyerが提供する他のWeb-to-appソリューションとの<Anchor target="_blank" href="/marketers/ja/docs/convert-your-mobile-web-visitors-to-app-users">比較</Anchor>を参考にしてください。

<div id="examples" />

### 利用例

以下では、OneLink Smart ScriptでOneLinkの送信URLを生成し、正確なアトリビューションやディープリンクを実現する例を紹介します。特定のメディアソースとキャンペーンの組み合わせについては、<Anchor target="_blank" href="/marketers/ja/docs/set-up-smart-script-to-convert-web-visitors#利用ケース">利用ケース</Anchor>を参照してください。

<div id="attribution" />

<Accordion title="アトリビューション">

マークはホテルチェーンのマーケターです。フロリダ州オーランドのホテルでの休暇を案内するメールを送信します。メール内のリンクは次のとおりです：https://hotel.me/pid=email&c=orlando

リンクをクリックすると、ホテルのモバイルWebサイトに移動します。そのページには、ホテルのモバイルアプリのダウンロードを促すボタンが表示されます。 OneLink Smart Scriptは、メール内の元のリンクと同じ**pid**と**c**パラメータを含むURLを自動生成します。生成されるリンクは次のとおりです：https://hotel.onelink.me/Ac4G?pid=email&c=orlando

ユーザーがモバイルサイトのボタンをクリックしてアプリをダウンロードすると、そのインストールはマークのオーランド向けメールキャンペーンに紐づきます。

</Accordion>

<div id="deep-linking" />

<Accordion title="ディープリンク">

エマは、フロリダ州オーランドのホテルでの休暇を案内するメールを受け取ります。

メール内のリンクは次のとおりです：https://hotel.me?type=email&campaign=Florida&city=orlando

リンクをクリックすると、ホテルのモバイルWebサイトに移動します。そのページには、ホテルのモバイルアプリのダウンロードを促すボタンが表示されます。 OneLink Smart Scriptは、メール内の元のリンクと同じ**pid**と**c**パラメータを含むURLを自動生成します。生成されるリンクは次のとおりです：https://hotel.onelink.me/Ac4G?pid=email&c=Florida&deep_link_value=orlando

**エマがモバイルサイトのボタンをクリックすると、アプリストアに移動します。アプリをダウンロードして起動すると、ディープリンクでアプリ内のオーランドの休暇案内ページへ誘導されます。**

<div id="note-1" />

> 📘 **注意**
>
> ディープリンクの動作は、アプリ開発者が実装したアプリの設定に従います。<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">詳細はこちら</Anchor>。

</Accordion>

<div data-zendesk-anchors="about-onelink-smart-script=onelink-smart-script%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HE7RW9G26CNME9TP350GFGS4=onelink-smart-script%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HE7RW9G2BV2NFJ0YZ9QKAA2V=%E6%B3%A8%E6%84%8F examples=%E5%88%A9%E7%94%A8%E4%BE%8B h_01HE7RW9G2WBZ1A0RS66CJ7BNH=%E5%88%A9%E7%94%A8%E4%BE%8B h_01HE7RW9G24Y604NTZFGKJJXSS=attribution h_01HE7RW9G2ZDDWE1M1B2G175ZF=deep-linking h_01HE7RW9G3W5GKQ2CD2BZW8YAW=%E6%B3%A8%E6%84%8F-1" />

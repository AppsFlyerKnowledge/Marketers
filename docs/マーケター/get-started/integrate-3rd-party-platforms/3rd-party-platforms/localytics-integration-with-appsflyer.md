---
title: LocalyticsとAppsFlyerの連携
metadata:
  keywords:
    - Localytics
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
  created_at: '2016-07-27T11:09:25Z'
  edited_at: '2026-10-28T09:03:23Z'
  id: 210748626
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/210748626
---
> **概要：** AppsFlyerの連携済みパートナーであるLocalyticsは、モバイルアプリとWebアプリ向けのマーケティング・分析プラットフォームです。 Localyticsのアプリ分析では、コホート別の継続率分析、ファネル分析、顧客のセグメント分け、リアルタイム分析により、ロイヤルティと顧客生涯価値が最も高いユーザー群を特定できます。 Localyticsのアプリマーケティングは、顧客獲得キャンペーンの長期的な成果を計測し、最も効果的なタイミングで対象の顧客に充実したアプリ内メッセージやプッシュ通知を届けることで、アプリのマーケティングを自動化します。

<div id="important" />

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

<div id="setting-up-localytics" />

## Localyticsの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

Localyticsの設定画面には、**［連携］、［計測リンク］、［データエンリッチメント］**、<strong>［権限］</strong>の4つのタブがあります。以下の項目をクリックすると、各タブの設定方法を確認できます。

パートナー設定画面のヘッダーについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

<div id="activate-partner" />

### パートナーを有効化

**初めてこの画面を開いたとき**は、下にあるトグルをオンにする必要があります。［***パートナーを有効化***］をオンにすると、［連携］タブのパラメータを設定できるようになります。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

<Image align="center" alt="" src="https://files.readme.io/5064c48a0851c34c51b4cfd28e2808a11e6d8d271f1cd735616f6de0d827cea8-360001902809.png" />

<div id="general-settings" />

### 一般設定

**アトリビューションID**

LocalyticsとAppsFlyerの接続には、固有のアトリビューションIDを使用します。まだ取得していない場合は、連携の設定を進める前にLocalyticsから取得するか、以下の手順で取得してください。

<Image align="center" alt="Localytics_msc_new_3.png" src="https://files.readme.io/2a51018b2248a855ed5a86207c18d132addf5ab56449f4c9915df2eb754e39ca-360001902869.png" />

Localyticsからのアプリキーの取得

* Localyticsの管理画面にログインします。
* 左側のパネルで**Attribution**をクリックします。
* **Third Party Attribution**を選択します。
* アトリビューションキーをコピーします。

<Image align="center" alt="" src="https://files.readme.io/dbac1c9beb6d22f4cf8f2ccfbdc0f6a22fec7e6ccad5a52e77c7c32044cab55c-207223506.png" />

AppsFlyerの管理画面でLocalyticsを設定します。

<div id="default-postbacks" />

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にLocalyticsへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

アプリをダウンロードしたすべてのユーザーのポストバックをLocalyticsに送信するには、［**すべてのパートナーまたはオーガニックのイベント**］を選択します。

設定が完了すると、AppsFlyerはオーガニックと非オーガニックのすべてのインストールについて、次のデータをLocalyticsに送信します。

* デバイスID（IDFA／Google広告ID）
* メディアソース
* キャンペーン名

［**保存**］をクリックします。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Localyticsでは、計測リンクは利用できません。

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

Localyticsでは、権限の設定は利用できません。

</Accordion>

<div id="viewing-the-attribution-data-in-the-localytics-console" />

## Localyticsコンソールでアトリビューションデータを確認する

AppsFlyerのデータを表示するには、LocalyticsのAttribution Settings画面でThird Party Attributionを有効にします。

<Image align="center" alt="" src="https://files.readme.io/0c171096b9bfd8a559ba8e1a0ad4296559dc050c7b3b52b8987bd9707e44220a-205662666.png" />

<Image align="center" alt="" src="https://files.readme.io/53524088099556d72e6e7573f3997bbb55b1a89e38a2f7a74eec1a1632125c72-205663286.png" />

<div data-zendesk-anchors="h_01H9FKCBM5W16BYJQ6TH9SSBVC=%E9%87%8D%E8%A6%81 setting-up-localytics=localytics%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKCBM5Z39GPE5772799DB1=localytics%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKCBM5JZ5V4YMB6S24JA6V=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FKCBM5PSZZ5FP1G12M9F63=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FKCBM5N4RB5ZSB61W02368=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKCBM5STZ79NBP3EFYGMB9=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKCBM54S067F1Z51E4FXQD=attribution-link-tab h_01H9FKCBM591RG57Q80JZ7FJWY=cost-tab h_01H9FKCBM5Q8P53V34QRQMS0BS=ad-revenue-tab h_01H9FKCBM5GGXX04JEH3DHNV78=permissions-tab viewing-the-attribution-data-in-the-localytics-console=localytics%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%81%A7%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01H9FKCBM5VBM87C2PHNZVZ4RJ=localytics%E3%82%B3%E3%83%B3%E3%82%BD%E3%83%BC%E3%83%AB%E3%81%A7%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B" />

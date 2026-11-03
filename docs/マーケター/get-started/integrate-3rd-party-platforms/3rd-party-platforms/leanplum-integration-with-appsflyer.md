---
title: LeanplumとAppsFlyerの連携
metadata:
  keywords:
    - Leanplum
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
  created_at: '2016-08-08T13:41:18Z'
  edited_at: '2026-10-28T09:03:18Z'
  id: 211487846
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/211487846
---
> **概要：** AppsFlyerの連携済みパートナーであるLeanplumは、データに基づく的確な施策を実現するモバイルマーケティングプラットフォームです。メッセージ配信とアプリ内体験を統合し、ユーザーエンゲージメントを高めます。 Leanplumは、メッセージ配信、自動化、アプリ編集、パーソナライズ、A/Bテスト、分析の機能を提供しています。

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

## Leanplumの設定

Leanplumをご利用の場合は、パブリッシャー情報を含むポストバックをLeanplumに送信することで、AppsFlyerと連携できます。このデータはLeanplumの分析画面で確認できるほか、ターゲティング・セグメント設定メニューを使って、A/Bテストやマーケティングキャンペーンのターゲティングにも活用できます。

AppsFlyerとの連携を有効にする前に、Leanplumの連携設定でAppsFlyerと同じデバイスIDを使用していることを確認してください。 LeanplumはデバイスIDを使ってユーザーのインストールとポストバックを照合します。IDが一致しないと、データをレポートに表示できません。

デフォルトでは、LeanplumはiOSでIDFV、AndroidでMACアドレスのMD5ハッシュを収集します。コードを1行追加するだけで、iOSではIDFA、AndroidではGAIDに変更できます。 AndroidとiOSでデバイスIDの形式を変更する方法は、<Anchor target="_blank" href="https://docs.leanplum.com/docs/which-device-id-format-should-i-use">こちら</Anchor>を参照してください。

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

Leanplumの設定で使用するのは、<strong>［連携］</strong>タブのみです。

パートナー設定画面のヘッダーについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

### パートナーを有効化

<strong>初めて設定する場合</strong>は、<strong><em>［パートナーを有効化］</em></strong>をオンにすると、［連携］タブのパラメータを設定できます。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">こちら</Anchor>を参照してください。

### 一般設定

**アプリIDとクライアントキー**

LeanplumとAppsFlyerの接続には、固有のアプリIDとクライアントキーを使用します。まだ取得していない場合は、連携の設定を進める前にLeanplumから取得するか、以下の手順で取得してください。

![Leanplum_msc_new_3.png](https://files.readme.io/0ef9adb16568192e922b33688a0525a3e61bc0f18dfc63e3717390adc34a66c4-360001904209.png)

**IDFAまたはIDFVの送信**

この設定が有効な場合、ポストバックでIDFVを送信します。 IDFVを取得できない場合は、代わりにIDFAを送信します。

この設定が無効な場合、ポストバックでIDFAを送信します。 IDFAを取得できない場合は、代わりにIDFVを送信します。

どちらも取得できない場合は、ポストバックを送信しません。

### アプリIDとクライアントキーの取得

画面右上の自分の名前をクリックし、**App Settings**を選択します。

![](https://files.readme.io/fcb9bb4fab1eec1db130904c2c4856529f58582bd8c9c04f08200ed82c0fcb80-206117303.png)

アプリを選択し、**Keys & Settings**をクリックします。

[![](https://files.readme.io/5608bddb2c31b1569e3d2e262946e239f3e637e5ac5d95bc24a03c3ff0d8d763-206117323.png)](https://files.readme.io/5608bddb2c31b1569e3d2e262946e239f3e637e5ac5d95bc24a03c3ff0d8d763-206117323.png)

![](https://files.readme.io/cd638732b197f03c6194b8bae7b8f726a6e4c16661702fdad48054a35ce333e5-206117343.png)

### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にLeanplumへポストバックを自動送信できます。このセクションで、ポストバックの送信を設定します。

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

アプリをダウンロードしたすべてのユーザーのポストバックをLeanplumに送信するには、［**すべてのパートナーまたはオーガニックのイベント**］を選択します。

［**保存**］をクリックします。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Leanplumでは、計測リンクは利用できません。

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

Leanplumでは、権限の設定は利用できません。

</Accordion>

## Leanplumでユーザーのアトリビューションデータを確認する

LeanplumとAppsFlyerの連携を設定すると、Leanplumのターゲティング・セグメント設定メニューからデータにアクセスできます。

[![](https://files.readme.io/5685cfe357930bd57611365d7f47fff1608a8e7c345110070763af26374e01bc-206117523.png)](https://files.readme.io/5685cfe357930bd57611365d7f47fff1608a8e7c345110070763af26374e01bc-206117523.png)

このメニューは、LeanplumのAnalytics、Messages、A/B Tests、Usersの各セクションで利用できます。 Analyticsではデータによる絞り込み、グループ分け、コホート分析、Usersでは絞り込みができます。また、AnalyticsとA/B Testsでは、このデータを使ったターゲティングが可能です。

<div data-zendesk-anchors="h_01H9FKB51R253NAXWEKSYVRZ3P=%E9%87%8D%E8%A6%81 setting-up-leanplum=leanplum%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKB51RA35X0G19ZPN2KAQ7=leanplum%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKB51VVVS5C4WEQ4FKHH4H=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FKB51VY7QASRV8XW8KRZK1=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A h_01H9FKB51VA8A6XZYM3W6AVNMH=%E4%B8%80%E8%88%AC%E8%A8%AD%E5%AE%9A obtaining-the-app-id-and-client-key=%E3%82%A2%E3%83%97%E3%83%AAid%E3%81%A8%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 h_01H9FKB51VFGCW21AG0BYWGFXZ=%E3%82%A2%E3%83%97%E3%83%AAid%E3%81%A8%E3%82%AF%E3%83%A9%E3%82%A4%E3%82%A2%E3%83%B3%E3%83%88%E3%82%AD%E3%83%BC%E3%81%AE%E5%8F%96%E5%BE%97 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKB51V63GPAS3R1GBWNTWR=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKB51VR8160P1RQK994DGZ=attribution-link-tab h_01H9FKB51VEJWHZXKENFASR9NG=cost-tab h_01H9FKB51V7C44MGTWR3RNX4D8=ad-revenue-tab h_01H9FKB51VY9V478W297NB58EM=permissions-tab viewing-user-attribution-data-in-leanplum=leanplum%E3%81%A7%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01H9FKB51VHAYS1STK6GQE4515=leanplum%E3%81%A7%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B" />

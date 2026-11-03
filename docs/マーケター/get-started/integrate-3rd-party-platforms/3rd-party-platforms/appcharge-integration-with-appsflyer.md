---
title: AppchargeとAppsFlyerの連携
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2025-06-17T13:21:47Z'
  edited_at: '2026-10-28T09:02:43Z'
  id: 36292113943825
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/36292113943825
---
> **概要：** AppsFlyerの連携済みパートナーであるAppchargeは、従来のアプリストアを介さない決済処理を専門とする、ゲーム向けコマース技術のプロバイダーです。 AppsFlyerとの連携により、AppchargeからWebストアの購入・返金データをAppsFlyerに自動送信でき、広告費用対効果（ROAS）と顧客生涯価値（LTV）をより包括的に把握できます。

## Appchargeについて

AppsFlyerの連携済みパートナーである<Anchor target="_blank" href="https://appcharge.com/">Appcharge</Anchor>は、モバイルゲームパブリッシャー向けのD2C（消費者への直接販売）プラットフォームです。この連携により、従来のアプリストア以外の重要な収益源であるWebストアでの購入状況を把握できます。購入・返金データをAppsFlyerに直接送信することで、純収益に基づく広告費用対効果（ROAS）を正確に算出し、キャンペーンの成果とプレイヤーの顧客生涯価値（LTV）をより詳しく分析できます。

Appchargeとの連携では、次のことができます。

* Eコマースの成果を計測し、流入元を特定する
* Webストアでの購入をLTVレポートに反映する
* Webストアでの購入をマーケティングキャンペーンに紐付ける
* モバイルキャンペーンのデータとの整合性を保つ

このガイドでは、Appchargeとの連携を設定する手順を説明します。

## 連携の設定

**前提条件：**

* 有効なAppchargeアカウントがあること。アカウントがない場合は、連携の設定を始める前にAppchargeに問い合わせて作成してください。
* AppsFlyerアカウントに、パートナー連携の設定に必要な権限があること。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。パートナーとの連携を利用している間は、オンにしておいてください。
5. 以下の説明に従い、<strong>［連携］</strong>タブで設定を完了します。

**既存の連携を編集するには、以下の手順を実施します。**

AppsFlyerで、［**連携＞パートナー連携＞有効な連携**］タブに移動し、パートナーを検索して設定を変更します。

<div id="integration-tab" />

<Accordion title="連携タブ">

#### パートナーを有効化

初回の設定時は、［**パートナーを有効化**］をオンにして、連携を設定できるようにします。 Appchargeと連携している間は、オンにしておく必要があります。 詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>を参照してください。

#### Advanced Privacy

iOSアプリでは、［<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">Advanced Privacy</Anchor>］のトグルが表示されます。オンにすると、パートナーとのユーザー識別子の共有が制限されます。アプリ設定で［<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor>］がオンの場合、［**Advanced Privacy（iOS 14.5以降）**］はデフォルトでオンになり、変更できなくなります。

#### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にAppchargeへデフォルトポストバックを送信します。 このセクションで、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">ポストバックを設定</Anchor>します。

* **オフ：** インストールポストバックはAppchargeに送信されません。  
   **注意：** AppchargeとAppsFlyerの連携では、インストールポストバックを送信する必要はありません。そのため、オフに設定することを推奨します。
* **オーガニックを含むすべてのメディアソース：** すべてのパートナーの成果として計測されたイベントと、オーガニックのイベントのインストールポストバックを送信します。

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

#### アプリ内イベントポストバック

このセクションでは、ポストバックを介してAppsFlyerのイベントをパートナーのイベントに対応付けます。

![xsolla-af-login-3.jpg](https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg)

1. ［**アプリ内イベントポストバック**］をオンにします。
2. ［**イベントを追加**］をクリックし、SDKまたはサーバー間（S2S）のイベントをリストに追加します。
3. 以下のパラメータを設定します。
4. ［**連携を保存**］をクリックします。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Appchargeでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

Appchargeとの連携では、コストデータには対応していません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

Appchargeとの連携では、広告収益データには対応していません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

Appchargeでは、権限の設定は利用できません。

</Accordion>

## AppsFlyerでAppchargeのイベントを識別する

Appchargeは、次の2種類のモバイルアプリ内イベントをAppsFlyerに送信します。

* `ac_af_purchase`：ユーザーが購入を正常に完了したとき
* `ac_af_refund`：返金が完了したとき

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

PC／コンソールへの対応：AppsFlyerとAppchargeの連携は、PC／コンソールアプリに対応していません。

</Accordion>

詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携</Anchor>を参照してください。

<div data-zendesk-anchors="integration-types=appcharge%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01J3DB8MCNQKKKCV1M39KN7Q0H=appcharge%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 setting-up-appcharge=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HST42K52JKQ70F7Y5PHDZAZ5=%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HST42K52RCTSGRNRCJ1C70NP=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HST42K52BBJ6JS5KM0WCN6CF=advanced-privacy default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HST47F5BXWV5W8BNHS9M2MTN=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKEAV3GG6X17X3NCCSWJAS=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab identifying-appcharge-events-in-appsflyer=appsflyer%E3%81%A7appcharge%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E8%AD%98%E5%88%A5%E3%81%99%E3%82%8B h_01JMHXRGB60RVZ399FNHS18ZHZ=appsflyer%E3%81%A7appcharge%E3%81%AE%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%82%92%E8%AD%98%E5%88%A5%E3%81%99%E3%82%8B h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations" />

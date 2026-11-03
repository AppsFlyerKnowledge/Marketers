---
title: パートナーへの広告収益データの共有
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-04-11T11:04:45Z'
  edited_at: '2026-10-28T08:50:08Z'
  id: 24100803679761
  locale: ja
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ja/articles/24100803679761
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** メディエーションネットワークの広告収益データをパートナーに共有し、ユーザー獲得（UA）キャンペーンの最適化に役立てます。**注意**：ROI360 Advancedの契約が必要です。

## パートナーへの広告収益データの共有について

ユーザー獲得を担うアドネットワークに、メディエーションネットワークの広告収益データへのアクセス権を付与できます。パートナーは、その情報をユーザー獲得キャンペーンの最適化に利用できます。

パートナーは、次のいずれかの方法で広告収益データを受信できます。

* [アドネットワーク向けUAシグナル](#ua-signals-for-ad-networks)
* [アドネットワーク向け広告収益ポストバック](#ad-revenue-event-postbacks-for-ad-networks)

広告収益データを共有する2つの方法を、以下の表で比較します。 

| 広告収益データの共有方法 | データの更新・反映 | 用途 | 必要な連携方式 | 必要な契約プラン |
| --- | --- | --- | --- | --- |
| UAシグナル | 1日1回 | 正確で網羅的なデータ。主にD3・D7の最適化に使用します。 | <ul><li>広告表示単位または端末単位</li><li>両方を設定している場合は、端末単位のデータを送信します。</li></ul> | ROI360 Advanced |
| ポストバック | リアルタイム | 反映の早いデータ。主にD0・D1の最適化に使用します。 | 広告表示単位 | ROI360 Advanced |

## 手順

<div id="ua-signals-for-ad-networks" />

<Accordion title="アドネットワーク向けUAシグナル">

UAシグナルを受信できるアドネットワークとの連携をご検討ください。ユーザー獲得を担うアドネットワークは、メディエーションネットワークの広告収益データを受信し、広告主のユーザー獲得キャンペーンの最適化に活用できます。

**アドネットワークにUAシグナルを送信するには**：

1. AppsFlyerのサイドメニューから<strong>［コラボレーション］</strong>＞**［パートナー連携］**＞<strong>［有効な連携］</strong>を選択します。
2. 連携済みパートナーを選択します。
3. <strong>［連携］</strong>タブを開きます。
4. <strong>［パートナーを有効にする］</strong>がオンになっていることを確認します。オフの場合、データは共有されません。
5. <strong>［権限］</strong>タブを開きます。
6. <strong>［アドネットワークの権限］</strong>をオンにします。
7. <strong>［広告収益のローデータへのアクセス（UAシグナル）］</strong>をオンにします。
8. <strong>［送信オプション］</strong>で、このパートナーが獲得したユーザーの広告収益データだけを送信するか（**［このパートナーのみ］**）、すべての流入元のユーザーの広告収益データを送信するか（**［オーガニックを含むすべてのメディアソース］**）を選択します。**注意**：<strong>［オーガニックを含むすべてのメディアソース］</strong>を選択した場合、他のパートナーが獲得したユーザーのデータには、アトリビューション情報は含まれません。
9. <strong>［設定を保存］</strong>をクリックします。
10. アドネットワークに連絡します。
    1. 権限を付与したことを伝えます。
    2. <Anchor target="_blank" href="/partners/ja/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">パートナー向けの手順</Anchor>に従って、レポートを受信するよう依頼します。

**アドネットワークにUAシグナルを送信できるメディエーションパートナーの一覧：**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Unity LevelPlayメディエーション（旧ironSource）
* Admost
* Tradplusad
* Yandex
* カスタムメディエーション

</Accordion>

<div id="ad-revenue-event-postbacks-for-ad-networks" />

<Accordion title="アドネットワーク向け広告収益イベントのポストバック">

アドネットワークへの広告収益ポストバックを設定できます。ユーザー獲得を担うアドネットワークは、メディエーションネットワークの広告収益データをリアルタイムで受信し、広告主のユーザー獲得キャンペーンの最適化に活用できます。 

> 🚧 **重要**
>
> * アドネットワークへの広告収益イベントのポストバックに対応するのは、SDKによる広告表示単位の<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">連携方式</Anchor>と、広告表示単位（SDK経由）・端末単位（サーバー間［S2S］API経由）の併用のみです。そのため、開発者が<Anchor target="_blank" href="/marketers/ja/docs/integrate-the-roi360-ad-revenue-sdk-api">AppsFlyer広告収益SDK API</Anchor>を実装する必要があります。
> * 特定のパートナーに広告収益ポストバックを送信できますが、連携を始める前に、そのパートナーがデータをどのように利用するか確認することを推奨します。

**広告収益イベントのポストバックを設定するには**：

1. <Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#既存の連携管理">マーケットプレイス</Anchor>、または<strong>［コラボレーション］</strong>＞**［パートナー連携］**＞<strong>［有効な連携］</strong>ページで、パートナーを検索・選択します。
2. <strong>［連携］</strong>タブを下にスクロールし、<strong>［アプリ内イベントのポストバック］</strong>をオンにします。
3. AppsFlyerのイベントaf\_ad\_revenueを選択します。**注意**：一部のアドネットワークの連携には、<strong>［すべてのイベントを選択］</strong>という選択肢があります。この選択肢にはaf\_ad\_revenueイベントが含まれないため、使用しないでください。
4. 次のように、パートナー側のイベント名／IDに対応づけます。

| アドネットワーク | af\_ad\_revenueに対応づけるパートナー側のイベント名／ID | スクリーンショット |
| --- | --- | --- |
| Google広告 | ad\_impression | <Image alt="Google広告のad_impressionイベントへの対応づけ" src="https://files.readme.io/883dd04563027d722e7e8e76a50f813c8a955db827cbb92e94cdc650ab7b234d-50421403523601.png" width="238px" /> |
| Unity Ads | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Moloco | 対応づけは不要 |  |
| Mintegral | 対応づけは不要 |  |
| Smadex | 対応づけは不要 |  |
| Mistplay | 対応づけは不要 |  |
| Meta広告 | iOSアプリではfb\_mobile\_purchase  <br />または  <br />AndroidアプリではAdimpression  <br /><Anchor target="_blank" href="/marketers/ja/docs/meta-ads-in-app-event-mapping#キャンペーン最適化のための広告収益データのマッピング">Meta広告のアプリ内イベントの対応づけガイド</Anchor>。 | [<Image alt="revenue-mapping-meta2.jpg" src="https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg" width="230px" />](https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg) |
| TikTok For Business｜アドバンスSRN | ImpressionLevelAdRevenue | [![](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png)](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png) |
| Aura from Unity | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| SingleTap by Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Persona.ly RTB | ad-revenue | [![](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png)](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png) |
| Bigo | ad\_watch | [![](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png)](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png) |
| Appier | 対応づけは不要 |  |
| Bidease | 対応づけは不要 |  |
| MAF | 対応づけは不要 |  |

5. イベントの<strong>［対象ユーザーの流入元］</strong>で、送信オプションを選択します。
   * **［このパートナーのみ］**：このパートナーに紐づくイベント、つまり、このパートナーが獲得したユーザーのイベントだけをポストバックで送信します。
   * **［オーガニックを含むすべてのメディアソース］**：すべてのパートナーに紐づくイベントとオーガニックイベントのポストバックを送信します。つまり、流入元にかかわらず、すべてのユーザーが対象です。**注意**：［オーガニックを含むすべてのメディアソース］を選択した場合、他のパートナーに紐づくイベントのポストバックには、アトリビューション情報は含まれません。
6. <strong>［連携を保存］</strong>をクリックします。

**アドネットワークに広告表示単位の広告収益イベントを送信できる、メディエーションパートナーの一覧：**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Unity LevelPlayメディエーション（旧ironSource）
* Admost
* Tradplusad
* Yandex
* カスタムメディエーション

</Accordion>

## 補足情報

<div id="list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks" />

<Accordion title="UAシグナルとポストバックを受信できるアドネットワークの一覧">

以下の表は、メディエーションネットワークから広告収益のUAシグナルとポストバックを受信できるアドネットワークの一覧です。

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th rowspan="2">アドネットワーク（パートナー）</th><th colspan="2">対応する受信方式</th></tr><tr><th>UAシグナル</th><th>ポストバック</th></tr></thead><tbody><tr><td>RZR（旧Aarki）</td><td>-</td><td><span>✓</span></td></tr><tr><td>AdAction</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adaction3</td><td>-</td><td><span>✓</span></td></tr><tr><td>Adamobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adikteev (Trademob)</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adjoe</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Adonco</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adshow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Almedia GmbH</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appgrowth</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appier</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Apprainbow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Aura from Unity</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Avow OEM</td><td> </td><td><span>✓</span></td></tr><tr><td>ayeT-Studios</td><td>-</td><td><span>✓</span></td></tr><tr><td>Betop</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidswave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidease</td><td>-</td><td><span>✓</span></td></tr><tr><td>Bigo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Brandscale</td><td><span>✓</span></td><td>-</td></tr><tr><td>Buzzvil</td><td>-</td><td><span>✓</span></td></tr><tr><td>Chameleostudios</td><td><span>✓</span></td><td>-</td></tr><tr><td>Chartboost</td><td><span>✓</span></td><td>-</td></tr><tr><td>Churney</td><td>-</td><td><span>✓</span></td></tr><tr><td>Datawave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>DLab</td><td><span>✓</span></td><td>-</td></tr><tr><td>Ecomonline</td><td><span>✓</span></td><td>-</td></tr><tr><td>Etusdigital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Exmox</td><td>-</td><td><span>✓</span></td></tr><tr><td>Fluent</td><td><span>✓</span></td><td>-</td></tr><tr><td>Foregon</td><td><span>✓</span></td><td>-</td></tr><tr><td>GNA Company</td><td><span>✓</span></td><td>-</td></tr><tr><td>Google広告</td><td> </td><td><span>✓</span></td></tr><tr><td>Greedygame</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Happimobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Hybrid</td><td><span>✓</span></td><td>-</td></tr><tr><td>Inflecto</td><td><span>✓</span></td><td>-</td></tr><tr><td>Irismedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Kashkick</td><td>-</td><td><span>✓</span></td></tr><tr><td>Kwai ads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lacuna</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lambadapp</td><td><span>✓</span></td><td>-</td></tr><tr><td>Leadidadmonster</td><td><span>✓</span></td><td>-</td></tr><tr><td>Lifestreet</td><td><span>✓</span></td><td>-</td></tr><tr><td>Liftoff</td><td><span>✓</span></td><td>-</td></tr><tr><td>MAF</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Melodong</td><td><span>✓</span></td><td>-</td></tr><tr><td>Meta広告</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Miniclip</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mistplay</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Mobrand</td><td><span>✓</span></td><td>-</td></tr><tr><td>Moloco</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Motive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Mpnd</td><td><span>✓</span></td><td>-</td></tr><tr><td>Msla</td><td><span>✓</span></td><td>-</td></tr><tr><td>Muvmobile</td><td><span>✓</span></td><td>-</td></tr><tr><td>NewsBreak</td><td>-</td><td><span>✓</span></td></tr><tr><td>Nexamob</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nftdroper</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nsofmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Performadlive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Persona.ly RTB</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Pitatroas</td><td><span>✓</span></td><td>-</td></tr><tr><td>Playgap</td><td>-</td><td><span>✓</span></td></tr><tr><td>Rebornads</td><td><span>✓</span></td><td>-</td></tr><tr><td>Remerge</td><td><span>✓</span></td><td>-</td></tr><tr><td>RTBhouse</td><td><span>✓</span></td><td>-</td></tr><tr><td>Runfuns</td><td><span>✓</span></td><td>-</td></tr><tr><td>SayGames LTD</td><td>-</td><td><span>✓</span></td></tr><tr><td>Scmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shalltry</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shareit</td><td><span>✓</span></td><td>-</td></tr><tr><td>SingleTap by Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>Smadex</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Surgex</td><td>-</td><td><span>✓</span></td></tr><tr><td>Tapjoy</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Targetmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>TaurusX</td><td>-</td><td><span>✓</span></td></tr><tr><td>Thepurpleline</td><td><span>✓</span></td><td>-</td></tr><tr><td>TikTok for Business</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Trade Desk</td><td> </td><td><span>✓</span></td></tr><tr><td>Transsion</td><td>-</td><td><span>✓</span></td></tr><tr><td>Truemoney</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tyrads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Unity Ads</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Unity CTV</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Vivo Global </td><td> </td><td><span>✓</span></td></tr><tr><td>Voodoo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Vungle</td><td><span>✓</span></td><td>-</td></tr><tr><td>VYBS</td><td>-</td><td><span>✓</span></td></tr><tr><td>Yandex</td><td><span>✓</span></td><td>-</td></tr><tr><td>Yeahmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>YouAppi</td><td>-</td><td><span>✓</span></td></tr><tr><td>Xiaomi Global</td><td>-</td><td><span>✓</span></td></tr><tr><td>YSO Network</td><td>-</td><td><span>✓</span></td></tr><tr><td>Z2A Digital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Zoyo</td><td><span>✓</span></td><td>-</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="仕様と制限事項">

| 項目 | 説明 |
| --- | --- |
| コンバージョンの種類 | UAシグナルと広告収益ポストバックは、インストール、リアトリビューション、リエンゲージメント、再インストールのすべてのコンバージョンのデータに対応しています。 |
| 代理店のポストバック設定権限 | 代理店は、広告収益ポストバックを設定できません。 |

</Accordion>

<div data-zendesk-anchors="about-sharing-ad-revenue-data-with-ua-partners=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%B8%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%85%B1%E6%9C%89%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HV6CW4SAF23TT5XZF1SGPVQH=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%B8%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%85%B1%E6%9C%89%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 procedures=%E6%89%8B%E9%A0%86 h_01HVEEMGMEWDKAXVNHR8C0AHPQ=%E6%89%8B%E9%A0%86 01H8V10BKM7MMM63JHGCF2DYMC=ua-signals-for-ad-networks 01H8V10BKMED8J73G22CFVH6GJ=ad-revenue-event-postbacks-for-ad-networks h_01HFAAC1J9KQ6ZNSCRSRKE9GA3=%E9%87%8D%E8%A6%81 additional-information=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HVE6AREZBPH751WFW70Q7X66=%E8%A3%9C%E8%B6%B3%E6%83%85%E5%A0%B1 h_01HVE6AREZBCAJPVYSF43JWNJZ=list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks h_01HTM0KJA8TB44TSV5N2151N4N=traits-and-limitations" />

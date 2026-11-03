---
title: MedialyzerとAppsFlyerの連携
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
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2026-10-28T09:03:28Z'
  id: 14963611180689
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/14963611180689
---
> **概要：** AppsFlyerの連携済みパートナーであるMedialyzerは、SaaSソリューションを開発・提供しています。メディアプランナーは、テレビ広告の放映直後に発生した訪問数とコンバージョン数に基づいて、オンラインビジネスのテレビ広告キャンペーンを最適化できます。

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

## Medialyzerの設定

**前提条件：** パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。

**新しく連携を設定するには、以下の手順を実施します。**

1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。  
   （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
2. 対象のアプリを選択します。
3. パートナーを検索し、［**連携する**］を選択します。
4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。   
   注意：パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
5. 以下の説明に従い、該当するタブで設定を完了します。

パートナー設定画面のヘッダーについて詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">こちら</Anchor>を参照してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

#### パートナーを有効化

初回の設定時は、［**パートナーを有効化**］をオンにして、連携を設定できるようにします。 Medialyzerと連携している間は、オンにしておく必要があります。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">パートナーの有効化</Anchor>を参照してください。

#### Advanced Privacy

iOSアプリでは、［<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">Advanced Privacy</Anchor>］のトグルが表示されます。オンにすると、パートナーとのユーザー識別子の共有が制限されます。アプリ設定で［<Anchor target="_blank" href="/marketers/ja/docs/apply-aggregated-advanced-privacy-framework">Aggregated Advanced Privacy</Anchor>］がオンの場合、［**Advanced Privacy（iOS 14.5以降）**］はデフォルトでオンになり、変更できなくなります。

#### デフォルトポストバック

AppsFlyerは、ユーザーのインストール後にMedialyzerへデフォルトポストバックを送信します。このセクションで、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#default-postbacks">ポストバックを設定</Anchor>します。

* **オフ**：インストールポストバックはMedialyzerに送信されません。
* **オーガニックを含むすべてのメディアソース**：すべてのパートナーの成果として計測されたイベントと、オーガニックイベントのインストールポストバックを送信します。

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

#### アプリ内イベントポストバック

このセクションでは、ポストバックを介してAppsFlyerのイベントをパートナーのイベントに対応付けます。

[![app_event_postbacks.JPG](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)

1. ［**アプリ内イベントポストバック**］をオンにします。
2. ［**イベントを追加**］をクリックし、SDKまたはサーバー間（S2S）のイベントをリストに追加します。
3. 以下のパラメータを設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | アプリに組み込んだSDK、またはサーバー間イベントからAppsFlyerが受信したイベント名です。<br />**ヒント**：目的のイベントが表示されない場合は、<ul><li>非オーガニックインストールのデバイスで対象イベントを発生させてから、もう一度確認してください。</li><li>［**AppsFlyerイベント**］に名前を入力し、［**カスタムイベントを作成**］をクリックします。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントのマッピング</Anchor>を参照してください。</li></ul> |
| **パートナー側のイベント名／ID** | BPMで定義されている各イベントの対応する名前またはIDを入力します。名前を対応付けずに、そのまま送信することもできます。 |
| **対象ユーザーの流入元** | すべてのパートナーの成果として計測されたイベントとオーガニックのイベントを送信するには、［**オーガニックを含むすべてのメディアソース**］を選択します。 |
| **送信するデータ** | <ul><li>**値も収益も送信しない**：パラメータ（値や収益）を含めず、イベント自体のみを送信します。</li><li>**値のみ送信し、収益は送信しない**：収益値を**除く**すべてのパラメータを送信します。</li><li>**値と収益を送信する**：収益値を**含む**すべてのイベントパラメータを送信します（イベントに収益値がある場合）。</li></ul> |

4. ［**連携を保存**］をクリックします。

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Medialyzerでは、計測リンクは利用できません。

</Accordion>

<div id="cost-tab" />

<Accordion title="コストタブ">

Medialyzerとの連携では、コストデータには対応していません。

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

Medialyzerとの連携では、広告収益データには対応していません。

</Accordion>

<div id="permissions-tab" />

<Accordion title="権限タブ">

Medialyzerでは、権限の設定は利用できません。

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=%E9%87%8D%E8%A6%81 setting-up-spoteffects=medialyzer%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKEAV37AT3VTZ5WV1YMWC2=medialyzer%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FKEAV3DW2A6RQ1NS44FT5F=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9FKEAV3T3YCPBYW70QVF540=advanced-privacy default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKEAV3Z1Y09P6E18J8AVX2=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKEAV3GG6X17X3NCCSWJAS=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />

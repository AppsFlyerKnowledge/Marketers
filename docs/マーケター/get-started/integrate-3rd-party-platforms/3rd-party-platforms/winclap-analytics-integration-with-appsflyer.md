---
title: Winclap AnalyticsとAppsFlyerの連携
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
  created_at: '2019-09-04T11:07:12Z'
  edited_at: '2026-10-28T09:04:03Z'
  id: 360002403537
  locale: ja
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ja/articles/360002403537
---
> **概要：** AppsFlyerの連携済みパートナーであるWinclap Analyticsは、AppsFlyerのアトリビューションデータをBIとポストアトリビューション分析に使用します。

> 🚧 **重要**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions#メディアソースの制限">一部のメディアソース</Anchor>は、第三者へのデータ共有を制限しています。 そのため、制限対象のイベントのポストバックは、送信設定にかかわらず、このパートナーには送信されません。

## Winclapの設定

設定は<strong>［有効な連携］</strong>ページで行いますが、まず<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations">マーケットプレイス</Anchor>でパートナーを探す必要があります。

> 📘 **注意**
>
> パートナーのアカウントが必要です。アカウントがない場合は、連携を設定する前にパートナーに連絡し、アカウントを開設してください。
>
> **新しく連携を設定するには、以下の手順を実施します。**
>
> 1. AppsFlyerで、［**連携＞パートナー連携＞マーケットプレイス**］タブに移動します。
>    （**既存の連携を編集する場合：** ［**連携＞パートナー連携＞有効な連携**］タブに移動します。）
> 2. 対象のアプリを選択します。
> 3. パートナーを検索し、［**連携する**］を選択します。
> 4. ［**連携**］タブで、［**パートナーを有効化**］をオンにします。
>    **注意：** パートナーとの連携を利用している間は、**このトグルをオン（有効）にしておく必要があります**。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">詳しく見る</Anchor>
> 5. 以下の説明に従い、該当するタブで設定を完了します。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner">パートナー連携</Anchor>を参照してください。

Winclap Analyticsの設定で使用するのは、***［連携］***タブのみです。

<div id="integration-tab" />

<Accordion title="連携タブ">

［連携］タブは、以下のセクションで構成されています。

### パートナーを有効化

**初めて設定する場合**は、***［パートナーを有効化］***をオンにすると、［連携］タブのパラメータを設定できます。パートナーとの連携を利用している間は、このトグルをオンにしておく必要があります。  
パートナーの有効化について詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/user-level-data-retention">こちら</Anchor>を参照してください。

### デフォルトポストバック

AppsFlyerは、ユーザーのインストールとリエンゲージメントの発生時に、Winclap Analyticsへポストバックを自動送信できます。このセクションでは、ポストバックを送信する**対象ユーザーの流入元**を指定します。

![Winclap Analytics連携のデフォルトポストバック](https://files.readme.io/a45d8d7ab4687876d8dea4b026580d80f4b34c151b00c3c47a701771d16582aa-50896714399761.png)

**インストール**について、次のいずれかを選択します。

* （デフォルト）***このパートナーのみ***：Winclapの成果として計測されたユーザーのイベントのみが対象です。
* ***オーガニックを含むすべてのメディアソース***：アプリをダウンロードしたすべてのユーザーのポストバックをWinclapに送信します。

**リエンゲージメント**では、***このパートナーのみ***を対象にポストバックを送信できます。

この設定を保存すると、AppsFlyerはオーガニックと非オーガニックの各インストールについて、次のデータをWinclap Analyticsに送信します。

* クリックID
* キャンペーン名
* ユーザーエージェント
* クリック時刻
* IP
* 国
* 市区町村
* サブパブリッシャー
* AndroidおよびiOSのデバイスID
* 通信事業者
* 言語
* アプリID
* アプリバージョン
* アプリ名
* インストール時刻

### アプリ内イベントの設定

このセクションでは、ポストバックでWinclap Analyticsに送信するアプリ内イベントを対応付けます。

[![Winclap Analyticsのアプリ内イベントポストバックの設定](https://files.readme.io/f14f801a50b3c699f71141a387a9d75586bae7b91aad88f29f97778408ee12fb-50896714404369.png)](https://files.readme.io/f14f801a50b3c699f71141a387a9d75586bae7b91aad88f29f97778408ee12fb-50896714404369.png)

1. ***［アプリ内イベントポストバック］***をオンにします。
2. 必要に応じて***［アプリ内イベントポストバック期間］***を設定します（<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#アプリ内イベントポストバック期間">アプリ内イベントポストバック期間の設定</Anchor>の詳細を参照）。
3. ***［イベントを追加］***をクリックし、SDKイベントをリストに追加します。
4. 以下のパラメータを設定します。

| パラメータ名 | 説明 |
| --- | --- |
| **SDKイベント名** | アプリに実装したSDKまたはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名です。  <br />**ヒント**：目的のイベントが表示されない場合は、 SDKイベント名を入力し、<strong>［カスタムイベントを作成］</strong>をクリックして、通常の手順で対応付けます。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントのマッピング</Anchor>の詳細を確認してください。 |
| **パートナーイベント識別子** | Winclap側で定義されている各イベントの一意の名前またはIDです。  <br />レポート対象の各イベントに対応するIDをWinclapから取得し、このフィールドに入力します。 |
| **送信オプション** | イベントの送信対象を選択します。  <br />**このパートナーのみ**：このパートナーの成果として計測されたユーザーのイベント**のみ**を送信します。  <br />**オーガニックを含むすべてのメディアソース**：すべてのユーザーをパートナーへのレポート対象にします。 |
| **イベントデータを送信** | <ul><li>**値も収益も送信しない：** イベント値を含めず、イベント自体のみを送信します。</li><li>**値のみ送信し、収益は送信しない：** 収益値を除くすべてのパラメータを送信します。</li><li>**値と収益を送信する**：収益値を含むすべてのイベントパラメータを送信します（イベントに収益値がある場合）。</li></ul> |

5. ***［保存］*をクリックします。**

この設定を保存すると、AppsFlyerは各非オーガニックイベントについて、次のデータをWinclap Analyticsに送信します。

* クリックID
* イベント名
* イベント値
* イベント収益
* イベント通貨
* イベント収益（USD）
* キャンペーン名
* ユーザーエージェント
* クリック時刻
* IP
* 国
* 市区町村
* サブパブリッシャー
* AndroidおよびiOSのデバイスID
* 通信事業者
* 言語
* アプリID
* アプリバージョン
* アプリ名
* インストール時刻

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

Winclap Analyticsでは、計測リンクは利用できません。

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

Winclap Analyticsでは、権限の設定は利用できません。

</Accordion>

<div data-zendesk-anchors="h_01H9HWQK6JA2194MPE8PVQJ346=%E9%87%8D%E8%A6%81 setting-up-winclap=winclap%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWQK6JAQ2GCHHGQ57PJ570=winclap%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWQK6JRZ1KVDJK00PZR7T9=%E6%B3%A8%E6%84%8F h_01H9HWQK6JX9MAD64MQ1HPK4T0=integration-tab activate-partner=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 h_01H9HWQK6JKRB5MDE43RKV3SEH=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92%E6%9C%89%E5%8A%B9%E5%8C%96 default-postbacks=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01H9HWQK6JP4HQHRFC011KW6XQ=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF inapp-events-settings=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWQK6J1MEK67XDMAMKAQKW=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E8%A8%AD%E5%AE%9A h_01H9HWQK6JBH1M2MZQM12R0SAR=attribution-link-tab h_01H9HWQK6JG46BGNRMR8ZM9W2J=cost-tab h_01H9HWQK6J7HHJWKVB55WE1VW9=ad-revenue-tab h_01H9HWQK6J6BD0ER2M9Z7GYGSM=permissions-tab" />

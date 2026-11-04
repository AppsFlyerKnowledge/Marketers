---
title: Meta広告｜アプリ内イベントのマッピング
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2026-10-28T09:16:39Z'
  id: 4410480904081
  locale: ja
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ja/articles/4410480904081
---
> **概要：** アプリ内イベントを詳細な情報とともにAppsFlyerからMeta広告に送信します。

<div id="meta-in-app-events-mapping" />

## Meta広告へのアプリ内イベントのマッピング

広告主は、SDKまたはサーバー間（S2S）で送信するアプリ内イベントを、Metaの定義済みイベントにマッピングします。また、<Anchor target="_blank" href="/marketers/ja/docs/measure-sessions">アプリの起動</Anchor>ごと、または検知された<Anchor target="_blank" href="/marketers/ja/docs/measure-uninstalls#アンインストールイベントの紐づけ">アプリのアンインストール</Anchor>についても、Metaにポストバックを送信できます。

これにより、Metaの高度な最適化機能を利用し、カスタムオーディエンスや類似オーディエンスのセグメントを作成できます。

<div id="predefined-event-mapping" />

### 定義済みイベントのマッピング

Meta広告には、マッピングに使用できる<Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names">さまざまな定義済みイベント</Anchor>が用意されています。

**詳細なアプリ内イベント**の一覧は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure">こちら</Anchor>を参照してください。追加パラメータとともにMetaに送信することで、**イベントの質に関する詳細情報**を提供できます。

詳細は、<Anchor target="_blank" href="/marketers/ja/docs/meta-ads-integration-setup#inapp-event-mapping">Meta広告へのイベントのマッピング</Anchor>を参照してください。

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

Meta広告には、アンインストール送信用の定義済みイベントはありません。アンインストールを送信するには、[カスタムイベント](/docs/meta-ads-in-app-event-mapping#カスタムアプリ内イベントのマッピング)を使用してください。

以下は、追加パラメータのない、その他のMetaの定義済みイベントの一覧です。

| Metaのイベント識別子 | 説明 | 推奨するAppsFlyer SDKイベント名 |
| --- | --- | --- |
| Donate | 組織や活動への寄付。 | af\_donate |
| Schedule | 事業拠点への訪問予約。 | af\_schedule |
| SubmitApplication | クレジットカード、教育プログラム、求人など、提供する商品、サービス、プログラムへの申し込み。 | af\_submit\_application |
| FindLocation | ユーザーが訪問を目的として、Webまたはアプリで事業拠点を見つけたとき。たとえば、商品を検索して、近隣の店舗で取り扱いがあることを確認した場合です。 | af\_find\_location |
| Contact | 顧客と企業の間で行われる、電話、SMS、メール、チャットなどによる問い合わせや連絡。 | af\_contact |
| CustomizeProduct | 企業が所有する設定ツールやその他のアプリケーションを使用した、商品のカスタマイズ。 | af\_customize\_product |
| `Adimpression`：Android用  <br />`Fb_mobile_purchase`：iOS用 | Meta広告プラットフォームで広告収益を最適化します。[詳細は以下を参照してください](#キャンペーン最適化のための広告収益データのマッピング)。 | af\_ad\_revenue |

<div id="mapping-ad-revenue-data-for-campaign-optimization" />

### キャンペーン最適化のための広告収益データのマッピング

Meta広告では、広告収益データに基づいてキャンペーンを最適化できます。そのためには、af\_ad\_revenueイベントを以下のMeta広告イベントにマッピングします。

<table><colgroup><col/><col/><col/><col/></colgroup><thead><tr><th><strong>AppsFlyerのイベント名</strong></th><th><strong>プラットフォーム</strong> </th><th><strong>マッピング先のパートナーイベント</strong></th><th><strong>Meta広告での最適化の基準</strong></th></tr></thead><tbody><tr><td rowspan="2"> <br/>af_ad_revenue</td><td>Android</td><td>Adimpression</td><td>個々の広告収益</td></tr><tr><td>iOS</td><td>fb_mobile_purchase</td><td>アプリ内購入</td></tr></tbody></table>

<div id="availability-limitations" />

#### 利用上の制限

* 現在、**Adimpression**イベントを使用した最適化は、以下の場合にのみ利用できます。
  * Androidアプリ。 iOSアプリでは、引き続き*fb\_mobile\_purchase*イベントを使用して広告収益データを送信できます。
  * Metaの基準に基づいて選ばれたMeta広告アカウント。グレーアウトしている場合は、[利用要件を満たしていない可能性があります](https://www.facebook.com/business/help/571188993373447?id=561906377587030)。
* *af\_ad\_revenue*イベントは、<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-cost-and-revenue-data">ROI360のアドバンスプラン</Anchor>を契約している場合にのみ利用できます。また、<Anchor target="_blank" href="/marketers/ja/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">SDK経由のインプレッションレベルの広告収益連携</Anchor>が必要です。
  * ROI360以外のプランでは、他のイベント名を使用して広告収益データを送信できます。

<div id="custom-in-app-events-mapping" />

### カスタムアプリ内イベントのマッピング

Metaのイベント識別子としてCUSTOMを選択すると、任意のカスタムアプリ内イベントをマッピングし、Metaに送信できます。

SDKで設定したイベント名とイベント値（イベントパラメータを含む）はそのままMetaに転送され、「custom」ではなく、元のAppsFlyer SDKのイベント名で表示されます。

これらのイベントを<Anchor target="_blank" href="https://www.facebook.com/business/help/2308889442692949?id=1716638325041491">キャンペーンの最適化に利用することもできます</Anchor>。

[![](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)](https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png)

<div id="automatic-parameter-mapping-with-the-custom-event" />

### カスタムイベントでのパラメータの自動マッピング

AppsFlyerとMetaの緊密な連携により、AppsFlyer SDKの標準イベントパラメータの多くは、Metaの定義済みパラメータに自動的にマッピングされます。たとえば、**af\_revenue**パラメータはMetaの **\_valueToSum**パラメータに変換されます。これにより、イベントごとの収益を送信し、Metaで計測や最適化に利用できます。

<div id="note" />

> 📘 **注意**
>
> パラメータの自動マッピングは、CUSTOMイベントと定義済みイベントで異なる場合があります。
>
> <Anchor target="_blank" href="/marketers/ja/docs/in-app-events-event-structure">定義済みイベント</Anchor>では、**af\_price**が **\_valueToSum**にマッピングされる場合があります（例：`fb_mobile_add_to_cart`）。一方、**af\_revenue**が **\_valueToSum**にマッピングされる場合もあります（例：`fb_mobile_purchase`）。
>
> CUSTOMにマッピングしたイベントでは、**af\_price**は常に**fb\_price**に、**af\_revenue**は常に **\_valueToSum**にマッピングされます。

以下の表は、CUSTOMイベントを介してMetaにマッピングした際に、Metaのパラメータに自動的にマッピングされるAppsFlyerのイベントパラメータをすべて示しています。

| AppsFlyerのパラメータ | Metaのパラメータ |
| --- | --- |
| af\_city | fb\_city |
| af\_class | fb\_travel\_class |
| af\_content | fb\_content |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_content\_type | fb\_content\_type |
| af\_country | fb\_country |
| af\_currency | fb\_currency |
| af\_date\_a | fb\_checkin\_date |
| af\_date\_b | fb\_checkout\_date |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_description | fb\_description |
| af\_destination\_a | fb\_origin\_airport |
| af\_destination\_b | fb\_destination\_airport |
| af\_destination\_list | fb\_destination\_ids |
| af\_hotel\_score | fb\_hotel\_score |
| af\_level | fb\_level |
| af\_max\_rating\_value | fb\_max\_rating\_value |
| af\_num\_adults | fb\_num\_adults |
| af\_num\_children | fb\_num\_children |
| af\_num\_infants | fb\_num\_infants |
| af\_order\_id | fb\_order\_id |
| af\_payment\_info\_available | fb\_payment\_info\_available |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops |
| af\_preferred\_price\_range | fb\_preferred\_price\_range |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings |
| af\_price | fb\_price |
| af\_quantity | fb\_num\_items |
| af\_region | fb\_region |
| af\_registration\_method | fb\_registration\_method |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date |
| af\_returning\_departure\_date | fb\_returning\_departure\_date |
| af\_revenue | \_valueToSum |
| af\_search\_string | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | fb\_suggested\_destinations |
| af\_suggested\_hotels | fb\_suggested\_hotels |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |

<div id="predefined-events-automatic-mapping-to-the-_valuetosum-parameter" />

#### 定義済みイベントの`_valueToSum`パラメータへの自動マッピング

定義済みイベントでは、Metaの`_valueToSum`パラメータは`af_price`または`af_revenue`のいずれかにマッピングされます。

以下の表は、`_valueToSum`パラメータを持つすべてのMetaの定義済みイベントについて、マッピングの対応関係を示しています。

| **Metaのイベント** | **\_valueToSumのマッピング先** |
| --- | --- |
| fb\_mobile\_level\_achieved | なし |
| fb\_mobile\_add\_payment\_info | なし |
| fb\_mobile\_add\_to\_cart | af\_price |
| fb\_mobile\_add\_to\_wishlist | af\_price |
| fb\_mobile\_complete\_registration | なし |
| fb\_mobile\_tutorial\_completion | なし |
| fb\_mobile\_initiated\_checkout | af\_price |
| fb\_mobile\_purchase | af\_revenue |
| fb\_mobile\_rate | af\_rating\_value |
| fb\_mobile\_search | af\_revenue |
| fb\_mobile\_spent\_credits | af\_price |
| fb\_mobile\_achievement\_unlocked | なし |
| fb\_mobile\_content\_view | af\_price |
| StartTrial | af\_price |
| Subscribe | af\_revenue |

<div id="send-complex-in-app-events-to-meta-ads" />

### 複数の商品を含むアプリ内イベントのMeta広告への送信

2026年9月時点では、複数の商品を含むアプリ内イベントをMeta広告に送信する際に、新しい`af_order_info`オブジェクトの使用を推奨しています。このオブジェクトを使用すると、広告主は複数の商品を含むアプリ内イベントを、対応する複数のアドネットワークと共有できます。詳細は、<Anchor target="_blank" href="/marketers/ja/docs/item-level-order-data-for-ad-networks-af-order-info">アドネットワーク向けの商品単位の注文データ（af\_order\_info）</Anchor>を参照してください。

`af_order_info`を使用すると、AppsFlyerは商品情報をMetaの`fb_contents`イベントフィールドに送信します。このフィールドは、商品ごとのSKU、数量、収益に対応しています。

代わりに、構造化した`af_content`配列も引き続き使用できます。ポストバックを正しく処理するため、配列内の各オブジェクトには`id`と`quantity`を必ず含めてください。

`af_content_list`は任意です。このパラメータがない場合、Metaは`fb_content`フィールド（`af_content`からマッピング）を使用して商品IDを識別します。 `af_content`のJSON内の各オブジェクトに`id`フィールドが含まれていれば、Metaはその内容を解析してコンテンツIDを抽出できます。

`af_content_list`を含める場合、同じイベントに`af_content_id`を含めないでください。どちらのパラメータも`fb_content_id`にマッピングされるため、競合を防ぐには、いずれか一方のみに値を設定する必要があります。

<div id="note-1" />

> 📘 **注意**
>
> `fb_content_id`は、Advantage+カタログ広告やダイナミック広告でのイベントとカタログ商品の照合、商品単位のパフォーマンスレポート、商品に基づく最適化シグナルなど、商品単位の用途で重要です。イベント数と値に基づく一般的なコンバージョン最適化では、このパラメータがなくてもキャンペーンは機能します。

<div id="example-unified-format-compatible-with-meta-and-tiktok" />

> 📄 **MetaとTikTokの両方に対応した共通形式の例**
>
> ```json
> {
>   "af_revenue": 4.99,
>   "af_currency": "USD",
>   "af_order_id": "12345",
>   "af_content": "[{\"id\":\"ID1\",\"quantity\":\"1\"},{\"id\":\"ID2\",\"quantity\":\"1\"},{\"id\":\"ID3\",\"quantity\":\"2\"}]"
> }
> ```

この形式は、MetaとTikTokの両方で使用できます。 TikTokも`af_content`フィールドから`id`の値を読み取るため、両方のアドネットワークにポストバックする場合も、共通のペイロードを1つ用意するだけで対応できます。

<div id="important" />

> 🚧 **重要！**
>
> `af_content`パラメータが1,000文字を超える場合、AppsFlyerは`fb_content`パラメータを含めずにイベントをMetaに送信することがあります。このとき`af_content_list`も含まれていない場合、Metaは商品を識別するためのデータを受信できません。多くの商品を含むイベントでは、`af_content`を1,000文字未満に抑えてください。

複数の商品を含むアプリ内イベントの構造の詳細は、<Anchor target="_blank" href="/marketers/ja/docs/in-app-events-overview#what-are-complex-inapp-events-and-how-do-i-set-them-up">アプリ内イベント｜概要</Anchor>を参照してください。

<div id="event-and-parameter-limitations" />

## イベントとパラメータの制限

[Meta広告に送信するイベント](https://developers.facebook.com/docs/app-events/faq#limits)には、以下の制限が適用されます。

* 以下の文字は使用できません。
  * コロン（:）
  * ピリオド（.）
  * ラテン文字（英字）以外の文字：2020年1月12日時点で、Metaは中国語の文字を拒否します。 AppsFlyerでは他の文字種をテストしていません。使用する場合は、ポストバックでの対応可否をMetaに確認してください。
* イベント名は大文字と小文字を区別します。乖離を避けるため、すべてのメディアソースとアプリバージョンで、イベント名の大文字と小文字を正しく使い分けてください。
* パラメータ数の上限：25個。
* イベント名とパラメータ名の長さ：2～40文字。
* パラメータ値の長さの上限：100文字。
* af\_contentパラメータ値の長さの上限：1,000文字。
* 使用可能な文字：英数字、アンダースコア、ハイフン、スペース。ラテン文字（英字）以外の文字は使用しないでください。ラテン文字以外の文字を使用すると、処理結果が一貫しなくなります。

アプリ内イベント名に関する注意事項：

* AppsFlyerのイベントにはMetaのイベント名と同じ名前（例：fb\_price）を付けることもできますが、その場合はMetaにCUSTOMイベントとして送信しないでください。  
  **問題を避けるため、Metaのイベント名と同じ名前を付けることは控えてください。**
* Metaへのアプリ内イベントポストバックをマッピングするには、オーガニックを含むすべての流入元のイベントデータを取得してください。

<div id="important-1" />

> 🚧 **重要！**
>
> 上記のパラメータを除き、AppsFlyerはCUSTOMイベントのデータを**そのまま**Metaに送信します。有効なMetaのパラメータ（上の表を参照）を使用し、イベントデータがMetaの要件を満たしていることを確認する責任は、アプリの所有者にあります。要件を満たさない場合、これらのパラメータはMetaに送信されません。

<div data-zendesk-anchors="facebook-iae-mapping=meta%E5%BA%83%E5%91%8A%E3%81%B8%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01J1WCP44CHN0Q73P6DN7H8FKG=meta%E5%BA%83%E5%91%8A%E3%81%B8%E3%81%AE%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 predefined-event-mapping=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01J1WCP44D18WMXCMHJ0FNF6Y0=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 mapping-ad-revenue-data-for-campaign-optimization=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E6%9C%80%E9%81%A9%E5%8C%96%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 01JAPZ6M11HSCE9QNN5NSD61FK=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E6%9C%80%E9%81%A9%E5%8C%96%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E5%BA%83%E5%91%8A%E5%8F%8E%E7%9B%8A%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 availability-limitations=%E5%88%A9%E7%94%A8%E4%B8%8A%E3%81%AE%E5%88%B6%E9%99%90 01JAQ1ECZVR8SZ81KE6CDD08A2=%E5%88%A9%E7%94%A8%E4%B8%8A%E3%81%AE%E5%88%B6%E9%99%90 custom-inapp-events-mapping=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01J1WCP44DK14AC5ZG4KTFFFSC=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 automatic-parameter-mapping-with-the-custom-event=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E8%87%AA%E5%8B%95%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01J1WCP44D645TS6JFGM2BDGM9=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A7%E3%81%AE%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E8%87%AA%E5%8B%95%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01J1WCP44DSZ7G3603W5EBWZEW=%E6%B3%A8%E6%84%8F value-to-sum=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE_valuetosum%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%B8%E3%81%AE%E8%87%AA%E5%8B%95%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 01JATBG1SZRRZ0PCANKQ6S8CX4=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AE_valuetosum%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%B8%E3%81%AE%E8%87%AA%E5%8B%95%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 send-complex-in-app-events-to-meta-ads=%E8%A4%87%E6%95%B0%E3%81%AE%E5%95%86%E5%93%81%E3%82%92%E5%90%AB%E3%82%80%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AEmeta%E5%BA%83%E5%91%8A%E3%81%B8%E3%81%AE%E9%80%81%E4%BF%A1 h_01K1QR0NWMT1WCFWXF2GK9YZYF=%E8%A4%87%E6%95%B0%E3%81%AE%E5%95%86%E5%93%81%E3%82%92%E5%90%AB%E3%82%80%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%AEmeta%E5%BA%83%E5%91%8A%E3%81%B8%E3%81%AE%E9%80%81%E4%BF%A1 h_01KSMX6DZHA1HNQ2WGECZPEQGJ=%E6%B3%A8%E6%84%8F-1 h_01KSMX6DZHF0P97RTJHS065KB1=meta%E3%81%A8tiktok%E3%81%AE%E4%B8%A1%E6%96%B9%E3%81%AB%E5%AF%BE%E5%BF%9C%E3%81%97%E3%81%9F%E5%85%B1%E9%80%9A%E5%BD%A2%E5%BC%8F%E3%81%AE%E4%BE%8B h_01KSMX6DZHWXYRJP5QK5BB730P=%E9%87%8D%E8%A6%81 event-and-parameter-limitations=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A8%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%B6%E9%99%90 h_01J1WCP44DF2QMV10VXF8NQZ7W=%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%81%A8%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E5%88%B6%E9%99%90 h_01J1WCP44D9SNEYZG59KNM822K=%E9%87%8D%E8%A6%81-1" />

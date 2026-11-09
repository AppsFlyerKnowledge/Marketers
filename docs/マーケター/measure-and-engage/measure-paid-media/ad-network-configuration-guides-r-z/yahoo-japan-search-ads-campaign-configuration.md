---
title: Yahoo! Japan検索広告のキャンペーン設定
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-12-02T10:07:00Z'
  edited_at: '2026-10-14T09:33:15Z'
  id: 4412602890641
  locale: ja
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ja/articles/4412602890641
---
> **概要：** セルフレポーティングネットワーク（SRN）である、Yahoo! Japan 検索広告の連携方法について記載しています。
>
> * 202年12月15日、ヤフー検索広告（*yahoojapansearch\_int*） との従来の連携は、新しい連携 *yjsearch\_int*に置き換えられました。この記事では、新しいAPIの使用を開始する方法について説明します。 新APIでの連携方法の詳細については、[こちら](/docs/yahoo-japan-search-ads-campaign-configuration#integrating-with-the-new-api)をご確認ください。

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yjsearch.png" width="121px" />

<div id="yahoo-japan-search-ads-integration-principles" />

## Yahoo! Japan 検索広告の連携仕様

AppsFlyerとYahoo! Japan 検索広告の計測連携は、Androidアプリのみに対応しています。 

この連携は、コンバージョン測定のためにリンクIDを活用し、Yahoo Japan検索広告で事前に定義されたコンバージョンイベントに基づいています。そのコンバージョンイベントには、アプリ課金やサブスクリプションなどのアプリ内イベントを設定できます。これにより、AppsFlyerとYahoo! Japan検索広告との間でコンバージョン計測とレポーティングが可能になります。

<div id="comparing-the-legacy-and-new-integration" />

<Accordion title="新連携と旧連携の比較">

Yahoo! Japan検索広告のAPI対応：

| 機能 | 旧連携（yahoojapansearch\_int） | 新連携<br /><br />（yjsearch\_int） |
| --- | --- | --- |
| インストールコンバージョン（クリックスルーのみ） | はい | はい |
| アプリ内イベントコンバージョン | いいえ | はい |

</Accordion>

<div id="integrating-with-the-new-api" />

<Accordion title="新APIとの連携作業">

**新APIとの連携を有効にするには：**

1. Yahoo! Japan検索広告の管理画面上で、<Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">LinkIDを作成</Anchor>してください。その際、MMPとしてAppsFlyerを選択してください。
2. AppsFlyerの管理画面上で、[Yahoo! Japan検索広告との連携設定を行ってください。](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections)
3. 測定したい[アプリ内イベントをマッピング](/docs/yahoo-japan-search-ads-campaign-configuration#2)し、Yahoo Japan検索広告の<Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">キャンペーン管理ツールで新しいコンバージョン分析を作成</Anchor> します。

</Accordion>

<div id="data-sharing-between-appsflyer-and-yahoo-japan-search-ads" />

<Accordion title="AppsFlyerとYahoo! Japan検索広告のデータ共有について">

Yahoo! Japan 検索広告にコンバージョンとアプリ内イベントに関するポストバックを送信します。アプリ内イベントは、Yahoo! Japan検索広告がパフォーマンスレポートの最適化と更新のために使用するために、事前に定義されているコンバージョンイベントにマッピングされます。広告主は、連携作業の一部としてこのマッピング作業を行います。

AppsFlyerアプリ内イベント（あなたのアプリ）とYahoo検索広告の事前定義イベントマッピングのコンテキストで、次のマッピング表を検討してください。

| AppsFlyerのアプリ内イベント | Yahoo! Japan検索広告のアプリイベントタイプ |
| --- | --- |
| af\_purchase | in\_app\_purchase |
| af\_app\_opened | session\_start |
| af\_search | view\_search\_results |
| af\_content\_view | view\_item |
| af\_list\_view | view\_item\_list |
| af\_add\_to\_cart | add\_to\_cart |
| af\_travel\_booking | ecommerce\_purchase |
| その他のアプリ内イベント | 他にイベントがあれば、customに設定してください。 |

**Yahoo! Japan検索広告からAppsFlyerへの提供データ**

Yahoo! Japan検索広告がコンバージョンの計測を申告した際には、以下の表に記載されている関連パラメータの情報を提供します。これらのパラメータは、管理画面やローデータレポートに適宜反映されます。以下の表は、Yahoo! Japan検索広告とAppsFlyerのパラメータの対応表です。

<div id="yahoo-japan-search-ads-appsflyer-media-source-mapping" />

#### Yahoo! Japan検索広告 - AppsFlyer間のデータマッピング

| Yahoo! Japan検索広告 | AppsFlyer |
| --- | --- |
| timestamp | attributed\_touch\_time |
| campaign\_tracking\_id | campaign\_id |
| ad\_group\_tracking\_id | adset\_id |
| ad\_tracking\_id | ad\_id |
| keyword | Keywords |
| match\_type | keyword\_match\_type |
| account\_id | network\_account\_id |

</Accordion>

<div id="integration-procedures" />

## 実装の手順

Yahoo! Japan検索広告との連携は、広告主として直接、もしくは1社の代理店経由で、一つのアカウントと行うことができます。  
以下のように、必要に応じて各セクションの作業を完了してください：

* ［広告主：必須］[広告主アカウントでのYahoo! Japan検索広告の連携作業](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections)
* [代理店 - オプション］[代理店アカウント側での連携作業](/docs/yahoo-japan-search-ads-campaign-configuration#agency-integration)

<div id="yahoo-japan-search-ads-integration-tab-sections" />

<Accordion title="Yahoo JAPAN 検索広告 — 連携タブ">

<Table>
  <thead>
    <tr>
      <th>
        ステップ
      </th>
      <th>
        セクション
      </th>
      <th>
        説明
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="1"></span>
        1
      </td>
      <td>
        パートナーの有効化
      </td>
      <td>
        **前提条件：**

        Yahoo! Japan検索広告の<Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">LinkID</Anchor>を取得してください。

        **Yahoo! Japan検索広告の計測連携を有効にするには：**

        1. **AppsFlyerのサイドメニューから連携** > Partner Marketplaceを選択します。
        2. **Yahoo!を検索します。Yahoo! 検索広告（Yahoo! JAPANスポンサードサーチ） - 新規APIを検索し、選択します。**
        3. **yjsearch\_int** とブラウザのURL内に記載されていることを確認してください。そうでない場合には、間違ったパートナーを選択している状態なので注意してください。
        4. **連携**タブで、**パートナーを有効にする**トグルをオンにします。  
           **注: パートナーとの作業中はトグルをオン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（アクティブ化）</Anchor>にしておいてください。**
        5. Link IDの欄に、前提条件の部分で記載したLink IDを貼り付けてください。
        6. ［任意］インストールの <Anchor target="_blank" href="/marketers/ja/docs/set-up-lookback-windows">クリックスルールックバック期間</Anchor>を変更してください。Yahoo! Japan検索広告のデフォルト設定は7日間です。(媒体側との乖離を最小限に抑えるために、Yahoo! Japan検索広告側の設定と期間を合わせることをお勧めします。)
        7. **連携を保存**をクリックします。
        8. **Yahoo! Japan 検索広告**の媒体管理画面上で、 <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=365">新しいコンバージョン設定</Anchor>として"app\_first\_open" を設定してください。詳細については<Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default">Yahoo! Japan 検索広告のガイド</Anchor>を参照してください。
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        AppsFlyerのアプリ内イベントのYahoo! Japan検索広告のイベントへのマッピング
      </td>
      <td>
        **Yahoo! Japan検索広告側で定義されているイベントにAppsFlyerのアプリ内イベントをマッピングするには：**

        1. AppsFlyerのサイドメニューから、 **連携** > 連携済みパートナーを選択します。
        2. Yahoo!Yahoo! JAPANスポンサードサーチ） - 新規APIを検索し、選択します。
        3. **アプリ内イベントポストバック**をオンにしてください。
        4. **イベントを追加**をクリックしてアプリ内イベントをリストに追加してください。
        5. 必要なパラメーターを完了してください。
        6. **連携を保存**をクリックします。
        7. **Yahoo Japan検索広告**で、設定したアプリ内イベントに合わせて<Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=365">新しいコンバージョン</Anchor>を設定します。詳細については<Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default">Yahoo! Japan 検索広告のガイド</Anchor>を参照してください。

        | パラメーター名 | 説明 |
        | --- | --- |
        | <span id="sdk-event-name"></span>SDKイベント名 | アプリに実装されている、SDKまたはサーバー間（S2S）イベントからAppsFlyerが受信したイベント名。 |
        | <span id="partner-event-identifier"></span>パートナー側のイベント名 | Yahoo! Japan検索広告側であらかじめ定義されているイベント。推奨されているデフォルトのマッピング設定は、前のセクションで記載されている表を確認してください。 |
        | <span id="sending-option"></span>送信オプション | 最適なイベントの送信オプションを選択します。<br /><br />* **このパートナーのみ**：Yahoo! Japan検索広告に成果が紐づいたユーザーのイベントのみを送信します。<br />* **オーガニックを含む全メディアソース：** 全ユーザーをYahoo Japan検索広告にレポートすることができます。 |
        | <span id="send-revenue"></span>収益を送信 | * **値も収益も送信しない：** イベント値なしでイベント名のみを送信します。<br />* **Values & no revenue（値は送信し、収益は送信しない）：** 収益値以外のすべてのパラメータを送信します。<br />* **Values & revenue（値も収益も送信する）**：収益値（イベントに存在する場合）を含むすべてのイベントパラメータを送信します。 |

        備考：

        * イベント名は大文字小文字を区別します。乖離を避けるため、全てのメディアソースとアプリバージョンで、正しいイベント名を使用していることを確認してください。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="agency-integration" />

<Accordion title="代理店連携">

代理店は、広告主に代わってYahoo! Japan検索広告のキャンペーンを実施することが可能です。

<div id="agency-setup" />

#### 代理店の設定

| 作業担当： | 手順 |
| --- | --- |
| 広告主 | <ol><li>[広告主側で必要なYahoo! Japan検索広告の連携作業](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections)が完了していることを確認してください。</li><li>AppsFlyerのサイドメニューから、 **連携** > 連携済みパートナーを選択します。</li><li>対象の代理店を選択してください。</li><li>権限タブにて、**代理店権限の付与作業**を行ってください。</li></ol> |
| 代理店 | <ol><li>AppsFlyer管理画面 左メニュー **設定** > **連携済みパートナー**に移動します。</li><li>Yahoo!Yahoo! JAPAN Sponsored Search) - 新API</li><li>**連携タブ**を開きます。</li><li>**パートナーを有効にする**が**オン**になっていることを確認してください。ONになっていない場合には、広告主側でのYahoo! Japan検索広告の連携作業をまずは行う必要があります。</li><li>ルックバック期間やアプリ内イベントのマッピングなど、残りの設定が正しいことも確認してください。必要であれば、変更を広告主に依頼してください。</li><li>**Yahoo Japan検索広告のカスタマーID**を入力します。このIDは<Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=36745&o=default#:~:text=How%20to%20check%20Account%20ID">キャンペーン管理ツール</Anchor>から取得可能です。接続できるカスタマーIDは1つだけです。</li><li>**保存**をクリックしてください。</li></ol> |

</Accordion>

<div id="subsidiary-procedures" />

## その他の作業について

<div id="get-the-app-link-id" />

<Accordion title="アプリのリンクIDの取得">

**キャンペーン管理のリンクIDを取得するには、**<Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">Yahoo! Japan検索広告のドキュメントを参照してください。</Anchor>

</Accordion>

<div id="create-a-new-yahoo-japan-search-ads-predefined-event" />

<Accordion title="Yahoo! Japan検索広告側の事前定義イベントを新しく作成">

**新しく事前定義イベントを作成したい場合には、**<Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">Yahoo! Japan検索広告の案内</Anchor>を参照してください。

</Accordion>

<div id="yahoo-japan-search-ads-discrepancies" />

<Accordion title="Yahoo! Japan検索広告の数値乖離">

乖離とそれを最小化する方法については以下を参照してください。

**計測モデルの違い**

| 原因 | 説明 | AppsFlyerからのアドバイス |
| --- | --- | --- |
| アプリ内イベントのマッピングの不備 | AppsFlyerとYahoo! Japan検索広告のアプリ内イベントのマッピングが正しくない状態です。 | <ul><li>リンクIDを確認してください。</li><li>AppsFlyerのアプリ内イベントが、Yahoo! Japan検索広告側のイベントに正しくマッピングされていることを確認してください。</li></ul> |

</Accordion>

<div data-zendesk-anchors="yahoo-japan-search-ads-integration-principles=yahoo-japan-%E6%A4%9C%E7%B4%A2%E5%BA%83%E5%91%8A%E3%81%AE%E9%80%A3%E6%90%BA%E4%BB%95%E6%A7%98 h_01HH1RS8ZJSWTCDY5QBN3E041D=yahoo-japan-%E6%A4%9C%E7%B4%A2%E5%BA%83%E5%91%8A%E3%81%AE%E9%80%A3%E6%90%BA%E4%BB%95%E6%A7%98 h_01HH1RS8ZJATXC84X8C74B95C8=comparing-the-legacy-and-new-integration h_01HH1RS8ZJWESR21H0BE7S3HV5=integrating-with-the-new-api h_01HH1RS8ZJM3EHGMKJF409QPTX=data-sharing-between-appsflyer-and-yahoo-japan-search-ads yahoo-japan-search-adsappsflyer-media-source-mapping=yahoo-japan%E6%A4%9C%E7%B4%A2%E5%BA%83%E5%91%8A---appsflyer%E9%96%93%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01HH1RS8ZM0ZEPJ7ZJYY286J2F=yahoo-japan%E6%A4%9C%E7%B4%A2%E5%BA%83%E5%91%8A---appsflyer%E9%96%93%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 integration-procedures=%E5%AE%9F%E8%A3%85%E3%81%AE%E6%89%8B%E9%A0%86 h_01HH1RS8ZMAFNAGWAZDWX5PJT4=%E5%AE%9F%E8%A3%85%E3%81%AE%E6%89%8B%E9%A0%86 yahoo-japan-search-ads%E2%80%94integration-tab-sections=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMS287YR3K9CW7HN37=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMGTJQB3ANAJB8MY52=agency-integration agency-setup=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HH1RS8ZMCBT0NJ5Z23ZAK6TV=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%AD%E5%AE%9A subsidiary-procedures=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E4%BD%9C%E6%A5%AD%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HH1RS8ZMKHBA000CEX6KHQJK=%E3%81%9D%E3%81%AE%E4%BB%96%E3%81%AE%E4%BD%9C%E6%A5%AD%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HH1RS8ZMWPS69ASK452QAXAK=get-the-app-link-id h_01HH1RS8ZMXVXH745DP5Q8SZ3D=create-a-new-yahoo-japan-search-ads-predefined-event h_01HH1RS8ZM5SXTQDPJ5E9YEKPS=yahoo-japan-search-ads-discrepancies" />

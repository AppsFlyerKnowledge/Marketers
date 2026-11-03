---
title: オーディエンス—ユーザー属性
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-06-11T06:13:55Z'
  edited_at: '2026-10-14T09:33:59Z'
  id: 360009775517
  locale: ja
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ja/articles/360009775517
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **概要：** ユーザーの特性に関するデータをオーディエンスに追加することで、ユーザーを適切なグループに分類する機能を向上させます。

[![UserAttributionNavigationXL3_us-en.png](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)

## ユーザー属性について

ユーザー属性は、イベントベースのデータとは異なり、 ユーザーが共有する一般的な特性です。これには、性別、年齢、誕生日、国のような静的なもの、またはゲーム内のユーザースコアのような動的なものがあります。

ユーザー属性データについて：

* CSVファイルのインポートまたはAPIを通じてJSONで更新されます。
* ハッシュ形式で保存されます。
* あらゆるオーディエンスルールセットで利用可能です。

ユーザー属性データは**広告パートナーに共有されません**。

ユーザー属性はアプリレベルまたはアカウントレベルで設定され、この記事で説明されます。アプリレベルの属性を使用する場合、アカウントユーザーがその属性を管理および利用するための<Anchor target="_blank" href="/marketers/ja/docs/user-management#概要">アプリ権限</Anchor>が必要です。

以下のシナリオでは、ユーザー属性について詳しく説明します。

<div id="scenario-app-marketer-requirements" />

<Accordion title="シナリオ—アプリマーケティング担当者の要件">

あなた、アプリマーケティング担当者は、次のことに忙しいです：

* 2つのゲームアプリ（game\_a と game\_b）の管理。
* game\_cのリリース
* 以下のユーザー属性で現行のアプリユーザーをターゲティングします：
  * 好きなスポーツ：クリケット
  * 現在のゲームスコア：いずれかの現行ゲームで15以上

表にはCRMからのユーザー属性データが含まれています。オーディエンスルールセットはこのデータにアクセスする必要があります。   
![UserAttributuesExample_us-en.png](https://files.readme.io/6f86d8659ef089ac82bb8401b4af650fbc590d2293ac93de30e6f9b4fc2ceb86-33375683035281.png)

**ルールセットでCRMデータを利用する**

オーディエンス内で、ユーザー属性（好きなスポーツとゲームスコア）を作成します。これにより、ルールセットがCRMデータにアクセスできるようになります。

#### シナリオユーザー属性

| 名前 | 形式 | レベル |
| --- | --- | --- |
| <span id="game-score"></span>ゲームスコア | **数値**：「*ScoreGameBが29より大きい*」というルールを設定できます。 | **アプリレベル**：プレイしたゲームごとにユーザーのスコアが記録されます。<br /><br />意味：ScoreGameA、ScoreGameB。 |
| <span id="favorite-sport"></span>好きなスポーツ | **文字列：** 「*好きなスポーツがテニスである*」のようなルールを設定できます。<br /><br />注記！値は大文字小文字を区別します。 | **アカウントレベル**：ユーザーのお気に入りのスポーツはアプリに関係なく同じです。<br /><br />注記！ユーザーはアカウントレベルの属性に1つの値しか紐づけられません。 |

**ルールセット内のユーザー属性**

ユーザー属性は、オーディエンスルールセット内のフィルターとして機能します。この例では、マーケティング担当者が設定した基準（好きなスポーツとゲームスコア）を使用します。

[altUserAttributedExample.jpgalt](https://support.appsflyer.com/hc/article_attachments/30205926953745)

</Accordion>

## ユーザー属性を実装する

ユーザー属性を設定、追加、管理、削除します。

<div id="set-up" />

<Accordion title="設定">

**前提条件：**

アプリレベルの属性を管理するには、それぞれのアプリ権限を持っている必要があります。

**ユーザー属性を設定するには、次の手順に従います：**

1. [ユーザー属性を追加します。](/docs/audiences-create-better-audiences-with-user-attribute-data#add)
2. [次のいずれかを実行します](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)

   * [ユーザー属性データをCSVでインポートします。](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [ユーザー属性データをAPIでインポートします。](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)
3. <Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#user-attributes">ユーザー属性をルールセットに実装します。</Anchor>

</Accordion>

<div id="add" />

<Accordion title="追加">

**ユーザー属性を追加するには：**

1. AppsFlyerのサイドメニューから、**エンゲージメント** > **オーディエンス** を選択します。
2. ユーザー属性タブをクリックします。
3. ユーザー属性を追加**をクリックします。**

   ![UserAttributeAdd.png](https://files.readme.io/6c7f25bb23d47e67aaef34264029daa9ab058f08e218a441ab9dde8240b0b384-33375683046033.png)
4. フィールドに入力します。フィールドの特性は次の表に記載されています。   
   * **属性名**
   * **フォーマット**
   * **レベル**
5. 保存**をクリックします。**

| 項目 | 特性 |
| --- | --- |
| <span id="attribute-name"></span>属性名 | <ul><li>英字のみ</li><li>句読点や特殊文字は使用できません</li><li>アプリレベルとアカウントレベルの両方で同じ名前を使用することはできません</li><li>アプリレベルで同じ名前**を利用する**ことができます。例：上記のシナリオではScoreGameAとScoreGameBを利用します。</li></ul> |
| <span id="format"></span>形式 | <ul><li>テキスト：属性値が指定されたルール値と**等しい**か、**等しくない**かをテストします。例：クリケットであるか、クリケットでないか。</li><li>数値：属性値が指定されたルール値より大きいか、小さいか、または等しいかをテストします。例：スコアが15より大きい</li></ul> |
| <span id="level"></span>レベル | <ul><li>アカウントレベル： 属性はアプリと関連がありません。<br />例：性別、好きなスポーツ</li><li>アプリレベル： 属性はアプリに関連しています。属性に関連するアプリを選択します。</li></ul> |

</Accordion>

<div id="manage" />

<Accordion title="管理">

ユーザー属性を管理するには、**オーディエンス** > **ユーザー属性**タブに移動します。

[altAudiencesUserAttributes\_us-en.pngalt](https://support.appsflyer.com/hc/article_attachments/30205882472721)

| 機能 | 説明 |
| --- | --- |
| <span id="search-and-filter"></span>検索およびフィルター | 属性名、アプリ名、および属性レベルで。 |
| <span id="sort-by"></span>並び替え | 列のヘッダーをクリックすると、表の行が並べ替えられます。 |
| <span id="import-data"></span>データをインポート | <ul><li>[CSVでデータをインポート](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)</li><li>[APIでデータをインポート](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)</li></ul> |
| <span id="change-api-import-key"></span>APIインポートキーの変更 | **APIインポートキーを変更するには：**<ol><li>**データのインポート**をクリックします。</li><li>**API**を選択します。</li><li>**インポートキー**を更新をクリックします。</li></ol><strong>注意！</strong>スクリプトにキーが埋め込まれている場合は、新しいキーで更新してください。 |

</Accordion>

<div id="delete" />

<Accordion title="削除">

![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) 属性を削除できるのは管理者ユーザーのみです。

**ルールセットの一部である属性を削除するには：**

1. ルールセットから属性を削除します。
2. 属性を削除します。

</Accordion>

## データをインポート

<div id="import-field-specifications" />

<Accordion title="インポートフィールドの仕様">

| 項目 | コンテンツ | 形式 | データを追加  <br />CSVで | CSVでデータを削除 |
| --- | --- | --- | --- | --- |
| <span id="device_id"></span>device\_id | 次のユーザーIDのうち1つが含まれます：<ul><li>IDFA</li><li>GAID</li></ul> | テキスト | **device\_id**または**customer\_id**のいずれかが必須です | **device\_id**または**customer\_id**のいずれかが必須です<br /><br />既存データを削除するには、送信しないでください |
| <span id="customer_id"></span>customer\_id | <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">カスタマーユーザーID</Anchor> | テキスト | **device\_id**または**customer\_id**のいずれかが必須です | **device\_id**または**customer\_id**のいずれかが必須です<br /><br />既存データを削除するには、送信しないでください |
| <span id="app_id"></span>app\_id | **アプリレベルの属性：** 管理画面で表示されるアプリIDです。<br /><br />iOSアプリの場合、プレフィックス*ID*を含めます。<br /><br />**アカウントレベルの属性：** 常に*を入力します | テキスト | 必須 | 必須 |
| <span id="attribute_key"></span>属性キー | ユーザー属性名。ユーザー属性タブに表示されるものと同じです。 | テキスト | 必須 | 必須 |
| <span id="attribute_value"></span>属性値 | 割り当てられた値<br /><br />[*制限事項を参照](/docs/audiences-create-better-audiences-with-user-attribute-data#limitations) | テキストまたは数値 | 必須 | 送信しない |

</Accordion>

<div id="import-data-by-csv" />

<Accordion title="CSVでデータをインポート">

ユーザー属性データは、CSVファイルを通じて追加または削除されます。次の図と例のCSVファイルは、この記事で説明されているシナリオと一致しています。

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012423857">ユーザー属性の例.csv</Anchor>

![属性のファイル.png](https://files.readme.io/2a9075ab7f900648aeebe3b5fca807c6b931ba5295f35708ee6c48d345f681b9-33375704847633.png)

**CSVファイルの要件**

* ヘッダー行なし
* 前の表にリストされているすべての列が含まれています。

**CSVファイルをインポートするには：**

1. **オーディエンス** > **ユーザー属性**タブに移動します。
2. **データのインポート**をクリックします。
3. **CSV**を選択します。
4. 次のどちらかを選択します：
   * **データを追加**
   * **データを削除**
5. インポートするCSVファイルを選択してください。
6. [**アップロード**]をクリックすると、アップロードのステータスメッセージが表示されます。

**注：** ユーザー属性をインポートする際、カスタマーIDに関連付けられているすべての既知のデバイスにも属性が割り当てられます。たとえば、ユーザーがカスタマーIDごとに10台のデバイスを「ゲームスコア」にインポートし、そのうち1つのカスタマーIDが2台のデバイス（同じCUIDを持つ2つのGAID）に関連付けられている場合、このインポートには合計で11のユーザー属性レコードが含まれます。

</Accordion>

<div id="import-data-by-api" />

<Accordion title="APIによるデータのインポート">

このインポート方法には、リクエストURLとユーザー属性データを含むJSONが必要です。

1. 管理画面で、準備されたAPIリクエストとJSONテンプレートを取得します。
2. [フィールド仕様](/docs/audiences-create-better-audiences-with-user-attribute-data#import-field-specifications)に従って、JSONテンプレートにデータを入力します。

**APIリクエストURLとJSONテンプレートを生成するには：**

1. [**データのインポート**] をクリックします。
2. **APIを選択します。**
3. アクションを選択します：  
   * ユーザー属性を更新：上書きまたは追加。
   * ユーザー属性を削除。
   * ユーザーデータを削除：特定のユーザーに関するすべてのデータを削除します。ユーザーはAppsFlyer IDによって識別されます。
   * アプリデータを削除:アプリレベルで全データを削除します。
4. 生成されたAPIリクエストURLをコピーします。
5. 生成されたAPIリクエストボディをコピーします。
6. 指定されたJSON形式で、JSON（ユーザー属性データを含む）を準備します。アカウントレベルの属性の場合、「app\_ids: ["*"]」を設定します。
7. URLとリクエストボディに基づいてAPI呼び出しを準備します。
8. プログラムを使ってリクエストを送信します。

**リクエストとJSONの例**  

```json
https://hq1.appsflyer.com/api/user-attributes-import-api/set-user-data
{
  "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
  "attributes_values": [
    {
      "device_id": "",
      "customer_id": "",
      "app_ids": [],
      "attributes": [
        {
          "attribute_key": "",
          "attribute_value": ""
        }
      ]
    }
  ]
}
```

> 📘 **注記**
>
> Authorization Bearer ヘッダーでリクエストを<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens#広告主">API トークン V2.0</Anchor>を使用して認証する必要があります。

**複数のデバイスID、属性キー、属性値の例**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "2222222",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 5
                }
                ,
                {
                    "attribute_key": "favorite_sport",
                    "attribute_value": "cricket"
                }
            ]
        }
        ,
        {
            "device_id": "555555-d1d1-d1d1-555-fffffffff",
            "customer_id": "111111",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "order",
                    "attribute_value": 7
                }
                ,
                {
                    "attribute_key": "number",
                    "attribute_value": 8
                }
            ]
        }]
}
```

**単一のデバイスIDと複数の属性キーと値の例**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "12345678",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 90
                }
                ,
                {
                    "attribute_key": "favorite-sport",
                    "attribute_value": "cricket"
                }
                ,
                {
                    "attribute_key": "orderNumber",
                    "attribute_value": 93
                }
                ,
                {
                    "attribute_key": "netPromoterScore",
                    "attribute_value": 94
                }
            ]
        }
    ]
}
```

**注：** ユーザー属性をインポートする際、カスタマーIDに関連付けられている全ての既知のデバイスにも属性が割り当てられます。たとえば、ユーザーがカスタマーIDごとに10台のデバイスを「ゲームスコア」にインポートし、そのうち1つのカスタマーIDが2台のデバイス（同じCUIDを持つ2つのGAID）に関連付けられている場合、このインポートには合計で11のユーザー属性レコードが含まれます。CSVインポートの制限

</Accordion>

<div id="limitations" />

<Accordion title="制限事項">

#### 一般的な制限

* CSV／APIインポートデータでは整数（完全数）のみがサポートされます。浮動小数点型（小数）の数値はサポートされていません。**例：** 「スコア」属性値は90に設定することができますが、90.5にすることはできません。
* ユーザー属性データは印刷もダウンロードもできません。
* #### 属性値の制限：

  * 属性値にはカンマやドット、その他の特殊文字を使用できません。
  * 文字列属性値には40文字の長さ制限があります。
  * 属性値は0で開始することはできません。

#### APIインポートの制限事項

* 1分あたり最大350件のAPIリクエスト、フラットペイロードでは1つの属性で10,000台のデバイス、2つの属性で5,000台のデバイスなどが対象です。
* `device_id`キーと`customer_id`キーは、すべてのインポート呼び出しに必須です。これらの識別子のいずれか1つだけで属性をインポートする場合、呼び出しには空の文字列を含む他の識別子の「ヘッダー」を含める必要があります。たとえば、`device_id`ごとに属性をインポートし、`customer_id`なしでインポートする場合、呼び出しは次のようになります：

```json
"attributes_values": [
{
"device_id": "39e123.......",
"customer_id": "",
```

#### CSVインポートの制限

* ユーザー属性値を追加する場合、 CSVファイルごとに最大1,000万行が可能です。

</Accordion>

<div data-zendesk-anchors="user-attributes=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%B1%9E%E6%80%A7%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HDNZH1XVX5BYQBPG848M8QZM=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%B1%9E%E6%80%A7%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 scenario%E2%80%94app-marketer-requirements=scenario-app-marketer-requirements h_01HDNZH1XV8AWVVGNYVA9G4PAG=scenario-app-marketer-requirements scenario-user-attributes=%E3%82%B7%E3%83%8A%E3%83%AA%E3%82%AA%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%B1%9E%E6%80%A7 h_01HDNZH1XW32ZJJRSANBQCTBV0=%E3%82%B7%E3%83%8A%E3%83%AA%E3%82%AA%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%B1%9E%E6%80%A7 implement-user-attributes=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%B1%9E%E6%80%A7%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B h_01HDNZH1XWPBVDHJ7AGPT5ZM9W=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E5%B1%9E%E6%80%A7%E3%82%92%E5%AE%9F%E8%A3%85%E3%81%99%E3%82%8B h_01HDNZH1XWYA9TQZ1B342A661R=set-up h_01HDNZH1XW0PPJF78EVFQTW3R7=add h_01HDNZH1XWGZ04TQXD5D50771A=manage h_01HDNZH1XWP8P1ZVJX11AXCS2P=delete import-data::b50dc884=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E3%82%A4%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%88 h_01HDNZH1XWCXV89YJV7EBJXNK5=%E3%83%87%E3%83%BC%E3%82%BF%E3%82%92%E3%82%A4%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%88 h_01HDNZH1XW87W1PV4C3PMY9QD6=import-field-specifications h_01HDNZH1XW3XC893Q8BQZQW2AG=import-data-by-csv h_01HDNZH1XX7PMGNTD683DD2B49=import-data-by-api h_01HDNZH1XXF6DSNKG19ZRZ01AZ=%E6%B3%A8%E8%A8%98 h_01HDNZH1XX61DVGK96C2TDSYW9=limitations general-limitations=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E5%88%B6%E9%99%90 h_01HDNZH1XXZZFA3WHZEE5N24AB=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E5%88%B6%E9%99%90 attribute-value-limitations=%E5%B1%9E%E6%80%A7%E5%80%A4%E3%81%AE%E5%88%B6%E9%99%90 h_01GZTGPK2FTHTV4NQ2HKV1HK00=%E5%B1%9E%E6%80%A7%E5%80%A4%E3%81%AE%E5%88%B6%E9%99%90 api-import-limitations=api%E3%82%A4%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HDNZH1XX4JWSMSF4672ENWNS=api%E3%82%A4%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 csv-import-limitations=csv%E3%82%A4%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%88%B6%E9%99%90 h_01J3APYQ8MXG1SGREVN638R75N=csv%E3%82%A4%E3%83%B3%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E5%88%B6%E9%99%90" />

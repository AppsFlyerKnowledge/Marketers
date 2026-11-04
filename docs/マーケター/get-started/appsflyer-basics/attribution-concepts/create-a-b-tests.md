---
title: A/Bテストの作成
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2019-05-07T09:17:43Z'
  edited_at: '2026-10-28T09:07:45Z'
  id: 360001523657
  locale: ja
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ja/articles/360001523657
---
> **概要：** AppsFlyerを使って、メディアソース、キャンペーン、クリエイティブ、ターゲティング、広告掲載位置のA/Bテストを実施できます。

![AB_TESTING.jpg](https://files.readme.io/259277a96d044e85cbac39de0f636bad531706e53e2ad5a21475277ea9dbd3a6-360002822018.jpg)

<div id="what-is-ab-testing" />

## A/Bテストとは？

A/Bテストとは、広告やキャンペーンのさまざまな要素を比較検証するための手法です。各広告には、ターゲティング、ビジュアル、テキストなど、見込みユーザーのコンバージョン率に影響する要素が含まれています。広告の各要素について、より高い成果につながるバリエーションを見つけることで、モバイルマーケティングの成果を大きく向上させられる可能性があります。

この記事では、**AppsFlyerを使ってA/Bテストを実施し、より高い成果につながる広告要素を見つける方法**を説明します。

<div id="how-to-ab-test-mobile-campaigns" />

## モバイルキャンペーンのA/Bテスト

ある要素をA/Bテストするには、同じオファーを表示する2つのソースにモバイルトラフィックを50/50で分割します。次に、テスト対象の要素について2つのバリエーションを作成します。十分なトラフィックが集まったら、既存バージョン（コントロール）と新しいバージョン（バリエーション）の結果を比較できます。

以下の手順は、AppsFlyerを使ってA/Bテストを実施する場合に適用されます。

**設定**：

1. テストする要素を選択します。  
   この記事では、[クリエイティブ](/docs/create-a-b-tests#クリエイティブとターゲティングのabテスト)、広告掲載位置、メディアソース、キャンペーンのA/Bテストについて説明します。
2. 同一のキャンペーン（または広告）を2つ作成し、それぞれで広告内の1つの要素だけを変えます。例えば、CTAボタンの文言などです。
   * バリエーションが**インストールコンバージョン率**に与える影響をテストするには、2つのキャンペーンにトラフィックを均等に分配します。   
     両方のソースでインプレッションデータを完全に取得できる場合は、インストール数をインプレッション数で割ってインストールコンバージョン率を算出します。
   * バリエーションが**インストール後のユーザーの質**に与える影響をテストする場合は、2つのキャンペーンに異なる量のトラフィックを送ることができます。
3. 統計的有意性を確保できるだけの十分なトラフィックを各キャンペーンに送ります。つまり、各キャンペーンで少なくとも50件のインストールが必要です。 「<Anchor target="_blank" href="https://neilpatel.com/ab-testing-calculator/">A/Bテスト有意性計算ツール</Anchor>」を使用します。

**分析：**

1. AppsFlyerのダッシュボードとデータを使用して、2つのキャンペーンの主要KPIのパフォーマンスを比較します。
2. 成果の高いバリエーションを選択し、実際のキャンペーンで使用します。

<div id="ab-testing-creatives-and-targeting" />

## クリエイティブとターゲティングのA/Bテスト

クリエイティブには、コピー、画像、色、フォント、ボタンなど、ユーザーのコンバージョン率にさまざまな影響を与える多くの要素が含まれています。国、年齢、性別などのターゲティングパラメータも、コンバージョン率に大きな影響を与える可能性があります。また、iOS 15以降では、最大35個のカスタムプロダクトページを利用できます。**これらの要素をA/Bテストすることで、ユーザーのコンバージョン率の改善に最も大きな影響を与える要因を特定できます**。

ここでは、次の2つの方法でA/Bテストを実施する手順を説明します。

* 単一のメディアソース
* 複数のメディアソース

| 方法 | メリット | デメリット |
| --- | --- | --- |
| 単一のメディアソースでA/Bテスト | <ul><li>簡単な設定</li><li>インストールコンバージョン率を簡単にテストできる</li></ul> | <ul><li>特定のメディアソースのユーザーにしか結果を適用できない場合がある</li><li>テストに時間がかかる場合がある</li></ul> |
| 複数のメディアソースでA/Bテスト | <ul><li>迅速に結果を得られる</li><li>すべてのメディアソースのユーザーに結果を適用できる</li></ul> | <ul><li>複数の場所で計測リンクを更新する必要がある</li></ul> |

<div id="method-1-ab-testing-with-a-single-media-source" />

<Accordion title="方法1：単一のメディアソースでA/Bテスト">

**設定**：

1. 十分なトラフィックがある、信頼できるメディアソースを選択します。
2. 次のいずれかの方法で、AppsFlyerに2つのキャンペーンまたは<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup">Smart Banners</Anchor>を作成します。
   * 計測リンクの「**c**」パラメータの値となるキャンペーン名を変えます。
   * または、1つのキャンペーン内に2つの広告セット（「**af\_adset**="」）を作成するか、1つの広告セット内に個別の広告（「**af\_ad=**」）を作成します。**注意**：Smart Bannersでは、同じバナーグループ内で<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers#ab-testing-banner-performance">各バナーに異なるパラメータを設定してA/Bテスト</Anchor>することもできます。
   * iOS 15以降では、異なるOneLink URLでそれぞれ別のカスタムプロダクトページへユーザーを誘導し、ページごとの効果をテストすることもできます。<Anchor target="_blank" href="/marketers/ja/docs/redirect-users-to-custom-app-store-product-pages">詳細を見る</Anchor>
3. テスト対象のバリエーション以外は、両方のキャンペーンで同じクリエイティブを使用します。
4. 両方のキャンペーンに同じ量のトラフィックを送ります。

**分析：**

* Overview dashboardで、キャンペーンのKPI（インストールコンバージョン率、ROI、ARPU、ロイヤルユーザー率など）を比較します。

</Accordion>

<div id="method-2-ab-testing-across-multiple-media-sources" />

<Accordion title="方法2：複数のメディアソースでA/Bテスト">

**設定**：

1. バリエーションの値を格納するサブパラメータを選択します。  
   例えば、CTAの文言を2パターンテストする場合、af\_sub1="install now"またはaf\_sub1="please install"を使用できます。サブパラメータとクリエイティブのテスト例については<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">こちら</Anchor>をご覧ください。
2. すべての有効な計測リンクに、対応する値を設定したサブパラメータを追加します。
3. テスト対象のバリエーション以外は、すべてのキャンペーンで同じクリエイティブを使用することを推奨します。

**分析：**

1. インストールまたはアプリ内イベントのローデータレポートをダウンロードします。選択したサブパラメータの列を使用して、データをフィルタリングおよび並べ替えます。
2. 記録した2種類の値ごとに、クリエイティブのパフォーマンスを比較します。

</Accordion>

<div id="ab-testing-ad-placement-on-mobile-web" />

## モバイルWebで広告掲載位置をA/Bテストする

![ad_placement.png](https://files.readme.io/6d64eed1a7a16c6daae9c93429d5bd46625dc4de12728e42b49a91ae69765f24-360002747977.png)

モバイルWebサイト上でアプリのバナーをどこに表示するかによって、ユーザーのコンバージョン率が大きく変わる可能性があります。多くの場合、広告主は自社のモバイルWebサイトを使って、訪問者をモバイルユーザーへ誘導します。

AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners機能</Anchor>を使うと、モバイルWebバナーをすばやく簡単に設定できます。さらに、この機能を使えば、**Webサイトの訪問者をモバイルユーザーへ転換するうえで最適な掲載位置**を判断するためのA/Bテストも簡単に実施できます。

**設定**：

1. モバイルWebサイトに<Anchor target="_blank" href="/marketers/ja/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>を実装します。
2. 新しい訪問者ごとに、ページの上部と下部のどちらにバナーを表示するかを決定します。両方にトラフィックを50/50で分割してください。  
   開発者向けヒント：Webサイトのトラフィックを分割する簡単な方法として、訪問者カウンターを使用し、新しい訪問者ごとにカウンターの値が奇数（A）か偶数（B）かを確認します。
3. 決定した表示位置に応じて、Smart Bannersの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">SDK API ShowBanner</Anchor>を使用してバナーの表示位置と計測リンクを設定します。  
   例：

   ```javascript
   showBanner({ bannerContainerQuery: "#document.body", additionalParams:{ af_sub5: "top"}})
   ```

**分析：**

1. インストールまたはアプリ内イベントのローデータレポートをダウンロードします。選択したサブパラメータ（例：af\_sub5）の列を使用して、データをフィルタリングおよび並べ替えます。
2. 2つの広告掲載位置のパフォーマンスを比較します。つまり、どちらの掲載位置でより多くのインストールまたはインストール後イベントが発生したかを確認します。

<div id="ab-testing-media-sources" />

## メディアソースのA/Bテスト

広告主がアプリにとって最も成果の高い（または低い）メディアソースを特定できるようにすることは、AppsFlyerが開発された目的の1つです。ただし、**メディアソースを正しく比較しないと、トラフィックの品質について誤った結論に至る可能性があります**。

**設定：**

1. 両方のメディアソースに対して、同じ1つの広告クリエイティブを作成します。
2. 各メディアソースに、まったく同じオーディエンスのターゲティングパラメータを設定した広告を作成します。
3. 2つのメディアソースに異なる量のトラフィックを送ることもできます。

**分析：**

1. 両方のメディアソースでテスト対象の広告のみを配信している場合は、AppsFlyerのダッシュボードとデータを使用して、2つのソースの主要KPIを簡単に比較できます。  
     
   それ以外の場合：
2. AppsFlyerのリテンションレポート、<Anchor target="_blank" href="/marketers/ja/docs/cohort-and-retention-dashboard">コホートレポート</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor>、または<Anchor target="_blank" href="/marketers/ja/docs/pivot-table-user-metrics">ピボットテーブル</Anchor>に移動します。
3. メディアソース → キャンペーン → 広告セット → 広告の順にグループ化します。
4. KPIを比較して、最も成果の高いメディアソースを特定します。

<div id="example" />

> 📄 **例**
>
> [![](https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png)](https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png)
>
> * 1と2は、同じメディアソース上の異なる広告です。クリエイティブ、ターゲティング、広告掲載位置のA/Bテストを行うには、例えば4日目のリテンション率など、1つのKPIを比較します。
> * 2と3は、異なるメディアソース上の広告です。広告のクリエイティブとターゲティングが同一であれば、1つのKPIを比較することでメディアソースのA/Bテストを行えます。

<div id="using-audiences-split-for-easy-ab-testing-of-media-sources" />

### オーディエンスを分割してメディアソースのA/Bテストを簡単に実施

各メディアソースに同じターゲティングパラメータを設定すると、テスト結果には各ネットワークのターゲティング機能の違いも含まれます。 A/Bテストでは、毎回1つのバリエーションだけをテストするのが最適です。そのため、アドネットワークのターゲティング以外の要素をA/Bテストする際は、ターゲティング機能の違いが結果に影響しないようにすることを推奨します。

オーディエンスをランダムに分割し、テストする各アドネットワークで、分割した両オーディエンスに同じクリエイティブを配信することを推奨します。 AppsFlyerでは、**オーディエンスを定義、分割し、異なるメディアソースに自動で振り分けるための簡単な方法**を提供しています。<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#オーディエンス分割とインクリメンタリティのテスト">こちら</Anchor>をご覧ください。

<div data-zendesk-anchors="what-is-ab-testing=ab%E3%83%86%E3%82%B9%E3%83%88%E3%81%A8%E3%81%AF h_01HN5CNKKBHV52ENXJXCBV2CES=ab%E3%83%86%E3%82%B9%E3%83%88%E3%81%A8%E3%81%AF how-to-ab-test-mobile-campaigns=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AEab%E3%83%86%E3%82%B9%E3%83%88 h_01HN5CNKKC02NKW4330QB6E01T=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AEab%E3%83%86%E3%82%B9%E3%83%88 ab-testing-creatives-and-targeting=%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%81%A8%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AEab%E3%83%86%E3%82%B9%E3%83%88 h_01HN5CNKKCJPZSEEF1RAHC0HXD=%E3%82%AF%E3%83%AA%E3%82%A8%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E3%81%A8%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%AEab%E3%83%86%E3%82%B9%E3%83%88 h_01HN5CNKKCMVE9YH379RP1S19W=method-1-ab-testing-with-a-single-media-source h_01HN5CNKKC53RTV61K08T9AVRA=method-2-ab-testing-across-multiple-media-sources ab-testing-ad-placement-on-mobile-web=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%ABweb%E3%81%A7%E5%BA%83%E5%91%8A%E6%8E%B2%E8%BC%89%E4%BD%8D%E7%BD%AE%E3%82%92ab%E3%83%86%E3%82%B9%E3%83%88%E3%81%99%E3%82%8B h_01HN5CNKKCVPSSZZTJ8QGJHY1B=%E3%83%A2%E3%83%90%E3%82%A4%E3%83%ABweb%E3%81%A7%E5%BA%83%E5%91%8A%E6%8E%B2%E8%BC%89%E4%BD%8D%E7%BD%AE%E3%82%92ab%E3%83%86%E3%82%B9%E3%83%88%E3%81%99%E3%82%8B ab-testing-media-sources=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AEab%E3%83%86%E3%82%B9%E3%83%88 h_01HN5CNKKC03ZAFCQZ0KJ0RHCE=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AEab%E3%83%86%E3%82%B9%E3%83%88 h_01HN5CNKKC4M6YMPHTQCFHFDMD=%E4%BE%8B using-audiences-split-for-easy-ab-testing-of-media-sources=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%82%92%E5%88%86%E5%89%B2%E3%81%97%E3%81%A6%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AEab%E3%83%86%E3%82%B9%E3%83%88%E3%82%92%E7%B0%A1%E5%8D%98%E3%81%AB%E5%AE%9F%E6%96%BD h_01HN5CNKKC551X3HQFNKHW1JBY=%E3%82%AA%E3%83%BC%E3%83%87%E3%82%A3%E3%82%A8%E3%83%B3%E3%82%B9%E3%82%92%E5%88%86%E5%89%B2%E3%81%97%E3%81%A6%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AEab%E3%83%86%E3%82%B9%E3%83%88%E3%82%92%E7%B0%A1%E5%8D%98%E3%81%AB%E5%AE%9F%E6%96%BD" />

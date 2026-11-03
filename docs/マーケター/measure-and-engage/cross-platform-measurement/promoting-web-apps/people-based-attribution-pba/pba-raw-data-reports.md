---
title: PBA ローデータレポート
metadata:
  keywords:
    - Data Locker
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-07-01T07:53:57Z'
  edited_at: '2026-10-14T09:32:02Z'
  id: 360001917778
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360001917778
---
> **概要**：ローデータレポートはData Lockerで入手可能です

## PBA ローデータレポート

PBA ローデータレポートを使用してユーザージャーニーとアクションを分析します。

### レポートの説明

PBA ローデータレポートの項目

| ローデータレポート項目 | 説明 |
| --- | --- |
| <span id="website-visits"></span>[Webサイト訪問](#website-visits-and-website-events) | <ul><li>Webサイトへの訪問。</li><li>Webトラフィックキャンペーンでユーザーへの露出とエンゲージメントを測定します。</li></ul> |
| <span id="website-events"></span><Anchor target="_blank" href="/marketers/ja/docs/pba-website-attribution-dashboard">Webサイトイベント</Anchor> | <ul><li>サブスクリプションや購入など、Webサイト訪問者によって実行されるアクションが含まれます。</li><li>イベントは、過去30日間に発生した直接以外の最後のWebサイト訪問に紐づきます。</li><li>イベントに紐づくアトリビューションパラメータは、メディアソース、メディアチャネル、キャンペーン等を含みます。</li><li>これらのパラメータまーを使用してマーケティングの最適化に活用します。</li><li>メディアソース毎のユーザー行動を分析します。</li><li>これらの項目の値は、<Anchor target="_blank" href="/marketers/ja/docs/pba-media-source-attribution-rules">PBA メディアソース計測ルール</Anchor>を使用して、成果が紐づいた訪問から決定されます。</li><li>目的は、イベントを特定のページビューではなく、特定のWebサイト訪問に関連付けることです。</li><li>これを使用してどのメディアとキャンペーンがユーザーをもたらし、ユーザーがどんなアクションを実行したかを明確にできます。</li></ul> |

## ローデータレポートの項目

<div id="website-visits-and-website-events" />

<Accordion title="Webサイト訪問とWebサイトイベント">

#### サンプルレポート

* Webサイトイベント<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=1096347999&single=true&output=csv">CSV</Anchor>
* Webサイト訪問[CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=432734495&single=true&output=csv)

ローデータ項目は、モバイルアプリユーザーの計測リンクとアプリインストールイベントで発生したデータから部分的に入力されます。

[項目の一覧をCSVとしてダウンロードする](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmRBeUQS-xeiv069vIgnfBoJW8Wfl1ojv0rAK-pcOlAzNveG1lqvExVdhWfgCKIpJxczWksUiHjSa3/pub?gid=0&single=true&output=csv)

#### Webサイト訪問とWebサイトイベントレポートの項目一覧

| フィールド名 | 説明 | 形式 | 例 |
| --- | --- | --- | --- |
| advertising\_id | Advertising ID (GAID) | 文字列 | 7fzzz3fa-8bad-46c9-bb03-fffffffffffffffffffffffff |
| af\_web\_id | Web SDKから送信されたCookie ID | 文字列 | 68972980-58f9-4ca6-8743-c0d633364b6d |
| amazon\_aid | Amazon Fire TVの広告ID | 文字列 | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| android\_id | Androidの端末ID | 文字列 | 68999980-58f9-4ca6-8743-c0d633364b6d |
| app\_id | インストールされた最新のアプリID | 文字列 | id123456789 |
| app\_name | 最新のアプリ名 | 文字列 | My App |
| app\_version | 最新のアプリバージョン | 文字列 | 6.32 |
| appsflyer\_id | AppsFlyer (インストール) ID | 文字列 | 1594825729709-5655157112349378588 |
| attributed\_touch\_time | ウェブ訪問の場合は、ウェブ訪問のタイムスタンプ、ウェブイベントの場合は、それに紐づくウェブ訪問のタイムスタンプ | yyyy-mm-dd hh:mm:ss | 9/17/2020 0:09:25 |
| attributed\_touch\_type | タッチポイントのタイプ。現在、常に 'website visit' （Website訪問）となります。 | 文字列 | web visit |
| bundle\_id | PBA バンドルID | 文字列 | 048db9bf-97r7-4m2f-919b-607b7kk806d0 |
| campaign | 'website visit' （Website訪問）にアトリビューション | 文字列 | Summer Campaign |
| campaign\_id | 'website visit' （Website訪問）にアトリビューション | 文字列 | 12343425 |
| city | IPアドレスを使用して解決 | 文字列 | Spring Valley |
| country\_code | IPアドレスを使用して解決 | 文字列 | US |
| customer\_user\_id | 顧客ユーザーID (CUID) | 文字列 | 5a8771ecbb986ABC |
| device\_type | デバイスタイプ | 文字列 | デスクトップ |
| dma | IPアドレスを使用して解決 | 文字列 | 501 |
| event\_name | Websiteイベントレポート：web SDKから送信された eventName | 文字列 | purchase |
| event\_revenue | 購入通貨でのイベント収益額 | 文字列 | 199.99 |
| event\_revenue\_currency | event\_revenueの3桁の通貨コード | 文字列 | USD, ZAR, EUR |
| event\_revenue\_usd | USDに換算されたevent\_revenue | 文字列 | 57.46 |
| event\_source | web SDK または Server-to-server | 文字列 | web SDK, S2S |
| event\_time | Webサイト訪問：訪問時刻。Webサイトイベント：イベント時刻。 | yyyy-mm-dd hh:mm:ss | 9/17/2020 0:09:25 |
| イベントタイプ | 次の手順を実行します： | 文字列 | conversion event |
| イベントURL | イベントが発生したWebページのURL（Webサイト訪問時のオリジナルURLと同じ） | 文字列 | http://www.brandpit.com/checkout |
| event\_value | WebサイトイベントWebサイト訪問常に null | JSON | \{"sku":"ABC123", “color": "blue", "unit\_price":3.99,"currency":USD |
| idfa | 広告識別子 | 文字列 | A56B9887-FEBA-458C-BEFC-C891F9DF7681 |
| idfv | 広告識別子 | 文字列 | EBC2F523-B1E5-4484-A4C8-ADC32DC7C23D |
| imei | Device identifier | 文字列 | 3532211234 |
| install\_time | 最新のアプリインストール時刻 | yyyy-mm-dd hh:mm:ss | 9/17/2020 0:09:25 |
| ip | 訪問者のIPアドレス | 文字列 | 24.7.104.115 |
| 言語 | ユーザーエージェントからレポートされる | 文字列 | English |
| media\_channel | Webサイト訪問に起因 | 文字列 | Ad |
| media\_source | Webサイト訪問に起因 | 文字列 | googleadwords\_int |
| media\_type | Webサイト訪問に起因 | 文字列 | 支払済 |
| oaid | 広告識別子 | 文字列 | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| original\_url | 帰属するWebサイト訪問時に、ユーザーをWebサイトにリダイレクトするURLアドレス | 文字列 | https://www.brandpitt.com/signin?utm_source=Googleg&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld |
| platform | プラットフォーム | 文字列 | macOS |
| postal\_code | IPアドレスを使用して解決 | 文字列 | 10977 |
| query\_params | リダイレクトURLのクエリパラメータ（? の後）リダイレクトURL上のクエリパラメーター (? の後)。例： https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoesURLにクエリパラメーターがない場合、この値は null になります | JSON |  |
| referrer | 成果が紐づくWebサイト訪問のHTTPドキュメントリファラ | 文字列 | https://www.google.com/ |
| region | IPアドレスを使用して解決 | 文字列 | NA |
| 州 | IPアドレスを使用して解決 | 文字列 | NY |

</Accordion>

<div id="field-release-notes" />

<Accordion title="項目のリリースノート">

| 日付 | レポート | 変更 |
| --- | --- | --- |
| 2020-11-18 | Webサイトイベント<br /><br />Webサイト訪問 | レポート名と構成が変更されました：<ul><li>Webタッチポイントが**Website visits**に置き換わりました</li><li>Webイベントが**Website events**に置き換わりました</li></ul> |
| 2020-10-04 | Web-to-app | 追加された項目：<ul><li>mobile\_campaign\_id</li><li>web\_campaign\_id</li></ul> |

</Accordion>

### 手順

<div id="setting-up-pba-reports-in-data-locker" />

<Accordion title="Data LockerでPBAレポートを設定する">

* PBAレポートは、Data Lockerのフォルダ「h=23」にその日に発生したイベントが一日一回記録されます。
* データを遡及的に記録することはできません。

1. AppsFlyerの側面メニューから、**[レポート] > [Data Locker]** を選択します。
2. レポート内のピープル ベースド アトリビューションのセクションを全て選択してください。
3. <strong>Save Configuration（設定を保存）</strong>をクリックします。

レポートをダウンロードするには、「 **Data Locker レポートへのアクセス** 」を参照してください。

**Data locker** PBAローデータレポートは、フォルダ「h=23」で使用できます。

例： t=website\_events/dt=2020-11-26/h=23

</Accordion>

<div id="combining-pba-and-mobile-data" />

<Accordion title="PBAとモバイルデータの組み合わせ">

このデータは、ユーザーがモバイルアプリとWebサイトの両方とエンゲージメントを持つ可能性が高いことを示しています。

モバイルとWebサイトデータを組み合わせます。

**ソリューション：**

* <Anchor target="_blank" href="/marketers/ja/docs/customer-user-id-field-cuid">カスタマーユーザーID</Anchor>（CUID）を使用してレポートを結合する  
  * モバイルと <Anchor target="_blank" href="/marketers/ja/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">Web</Anchor>の両方で同じCUIDを使用し、CUIDをキーとしてレポートを統合します。
  * 次に CUIDの項目を使用してレポートを結合します。
* PBAクロスプラットフォームでのユーザー識別
  * PBAでは、Webとモバイルユーザーが同一人物であることを特定できます。
  * 次に モバイル広告IDに基づいてモバイルとWebレポートを結合します。

#### **PBAとモバイルの使用例**

モバイルとWebデータを組み合わせて、プラットフォームやデバイス全体のユーザーのアクティビティを可視化します。データを結合することで、次のことができるようになります。

* ブランドのデジタルプロパティ全体のユーザージャーニーをたどります。
* 各プラットフォームでのユーザー行動を分析できます。
* どのプラットフォームがより高いエンゲージメントを示すかを分析します。
* どのプラットフォームがより高いコンバージョンを促しているのかを確認できます。
* ユーザーをWebからモバイルに切り替える施策を測定します。

</Accordion>

<div id="application-note-downloading-and-combining-data-locker-files" />

<Accordion title="応用のための留意点 - Data Lockerファイルのダウンロードと統合">

PBAローデータはData Lockerで利用できます。特定のレポートでは、データはレポートタイプ「h=23」フォルダに格納され、複数の圧縮ファイルで構成されます。

この手順を使用して、次の操作を行います。

* Cyber-Duck、またはS3ファイルをコピーするための他のツールを使用して、Data Lockerからファイルをコピーします。
* [Q](http://harelba.github.io/q/) を使用して1つのCSVファイルに複数のファイルを結合します。

**Data LockerからPBAデータをコピーする**

**はじめに：**

* <Anchor target="_blank" href="/marketers/ja/docs/data-locker-for-marketers#cyberduck">Cyber-Duck をインストールしセットアップ</Anchor>します。

**Cyber Duck を使用してデータをコピーする方法：**

1. ![Duck_us-en.jpg](https://files.readme.io/b8e93ad9423605b3247531d276b9c2d45abd4ea044dde29ee177f4d71b738e9d-360008254377.jpg)
2. PBAレポートタイプを**ダブルクリック**し、web\_events、web\_to\_app、web\_touch\_points から選択してください。  
   使用可能なレポート日付のリストが表示されます。
3. 特定の日付を**右クリック**してください。
4. **Download to a specific location and complete the location**（指定の場所にダウンロードし場所を完了する）を選択します。  
   ファイルがダウンロードされます。
5. 上記ステップを繰り返して、他のレポートタイプからデータをコピーします。各レポートタイプと日付は、コンピュータ上の別のディレクトリに保存する必要があります。

**統合されたCSVファイルを作成する：**

**始める前に:**

コンピュータに <Anchor target="_blank" href="http://harelba.github.io/q/">Q</Anchor> をインストールします。

**Q を使用してデータをCVSファイルに統合する方法**：

1. コマンドライン／ターミナルを使用して、データがあるディレクトリに移動します。
2. 次のコマンドを使用して、圧縮ファイルを pbadata.csv という名前の一つのファイルに結合します。  
   注記：注：記号「~」は、コンピュータ上でQコマンドが置かれているパス／ホームフォルダを示しています。コマンドを呼び出すには、完全なパスを使用する必要があります。   

   ```
   ~q "SELECT * from part*.gz" -d , -H -z -O >pbadata.csv
   ```
3. Excel または他のツールを使用してファイルを開きます。

</Accordion>

<div data-zendesk-anchors="pba-raw-data-reports=pba-%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HKW341NVTCP4FY5G4TC94MZY=pba-%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 report-descriptions=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E8%AA%AC%E6%98%8E h_01HKW341NVC83ZC3HCH86QBJYG=%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E8%AA%AC%E6%98%8E rawdata-report-fields=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%A0%85%E7%9B%AE h_01HKW341NVNYM1AGFC8GHV7VR2=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%A0%85%E7%9B%AE h_01EQD0FBKE0J71MA9MNETEZAMA=website-visits-and-website-events sample-reports=%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01HKW341NVX51NQFAA79BD7MF3=%E3%82%B5%E3%83%B3%E3%83%97%E3%83%AB%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 website-visits-events=web%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%AA%E5%95%8F%E3%81%A8web%E3%82%B5%E3%82%A4%E3%83%88%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%A0%85%E7%9B%AE%E4%B8%80%E8%A6%A7 field-list-website-visits-and-website-events-report=web%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%AA%E5%95%8F%E3%81%A8web%E3%82%B5%E3%82%A4%E3%83%88%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%A0%85%E7%9B%AE%E4%B8%80%E8%A6%A7 h_01J53BGNDSQCCFV1VQA8EV50GR=web%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%AA%E5%95%8F%E3%81%A8web%E3%82%B5%E3%82%A4%E3%83%88%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88%E3%81%AE%E9%A0%85%E7%9B%AE%E4%B8%80%E8%A6%A7 h_01HKW341NW43C07KYAN3WCV0WY=field-release-notes procedures=%E6%89%8B%E9%A0%86 h_01HKW341NWXQ19ZB5QXZK84VMQ=%E6%89%8B%E9%A0%86 h_01HKW341NXR3MP2T99AAHNH3SG=setting-up-pba-reports-in-data-locker h_01HKW341NX2S093V1Y8YVY45VP=combining-pba-and-mobile-data use-cases-for-pba-and-mobile=pba%E3%81%A8%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%81%AE%E4%BD%BF%E7%94%A8%E4%BE%8B h_01HKW341NXTXX4FJ2ZZQFZ2V85=pba%E3%81%A8%E3%83%A2%E3%83%90%E3%82%A4%E3%83%AB%E3%81%AE%E4%BD%BF%E7%94%A8%E4%BE%8B h_01HKW341NX95YBGHZZG8KZC3KX=application-note-downloading-and-combining-data-locker-files" />

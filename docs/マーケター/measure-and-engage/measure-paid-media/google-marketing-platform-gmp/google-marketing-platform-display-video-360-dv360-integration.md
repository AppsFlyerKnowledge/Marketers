---
title: Google Marketing Platform - Display & Video 360（DV360）の統合
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-02-02T17:40:13Z'
  edited_at: '2026-10-14T09:34:57Z'
  id: 360017595598
  locale: ja
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/ja/articles/360017595598
---
> **概要：**

<div id="note-5" />

<div id="important-1" />

<div id="important" />

> 🚧 **重要！**
>
> <Anchor target="_blank" href="/marketers/ja/docs/bulletin-supporting-the-new-google-eu-consent-policy">新しいGoogle EU同意ポリシー支援</Anchor>に関するお知らせをご覧ください。

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

<div id="note" />

<div id="overview" />

## 概要

| GMPソリューション | 説明 | 連携に必要なアクション |
| --- | --- | --- |
| DV360 |  |  |
| CM360 & DV360 |  |  |
| CM360 + 非DV360のサードパーティメディアソース (1) | サードパーティメディアソースからトラフィックを購入し、このトラフィックから発生するモバイルアプリコンバージョンをCM360で計測する | <Anchor target="_blank" href="/marketers/ja/docs/gmp-use-case-of-traffic-measurement-from-3rd-parties-in-cmp360">CM360を使用した第三者トラフィックの測定</Anchor> |

<div id="note-1" />

<div id="setting-up-gmp-dv360-for-advertisers" />

<div id="data-sharing-between-appsflyer-and-gmp---dv360" />

### AppsFlyerとGMP間のデータ共有

AppsFlyerは、コンバージョンとアプリ内イベントに関連するポストバックをGMPに送信します。

これらのパラメータは、管理画面やローデータレポートに適宜反映されます。

| GMP | AppsFlyer |
| --- | --- |
| interaction type | attributed\_touch\_type |
| timestamp | attributed\_touch\_time |
| line\_item\_id | campaign\_id |
| line\_item\_name | campaign\_name |
| creative\_id | ad\_id |
| product\_type | af\_channel |
| external\_customer\_id | network\_account\_id |
| site\_id | af\_siteid |


**前提条件**

**連携を有効化または編集する：**

1. **有効化するには:** AppsFlyerのサイドメニューから、**コラボレーション** > **パートナーマーケットプレイス**を選択します。  
   **編集方法**：AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択します。
2. **Google Marketing Platform - Display & Video 360 (DV360)** を検索して選択します。
3. **連携の設定**をクリックします。連携の設定ページに移動します。
4. **連携**タブにて連携したいアプリを選択し、 **パートナーを有効にする**をオンにしてください。  
   **注：** パートナーと作業している間、トグルはオン<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation">（有効）</Anchor>のままにしておく必要があります。
5. 以下の手順に従い、各タブの設定を完了してください。

<div id="integration-tab" />

<Accordion title="連携タブ">

AppsFlyerがGMPを照会すると、レスポンスにてリストされたパラメーターが返されます。これらは、次の表に示すとおり、AppsFlyerパラメーターとローデータにマッピングされます。

|  |  | AppsFlyer のパラメーター | URLパラメーター |
| --- | --- | --- | --- |
| Placement ID | line\_item\_name | キャンペーン名 | c |
| Placement ID | line\_item\_id | Campaign ID | af\_c\_id |
| Site ID | Site ID | Site ID | af\_siteid |
| Creative ID | Creative ID | Ad ID | af\_ad\_id |

<span id="activate-partner::e4f2f638"></span>**連携**タブには、以下で説明するセクションがあります。

<div id="activate-partner" />

#### パートナーの有効化

連携を設定するには、まず[**パートナーの有効化**]トグルをオンにしてください。<Anchor target="_blank" href="/marketers/ja/docs/partner-activation-deactivation#パートナー統合を有効にする">パートナーの有効化と無効化</Anchor>について詳細はこちら。

<div id="general-settings" />

#### 一般的な設定

非EUユーザー非EUユーザー/strong>を有効にするか決定してください。

<Image align="center" alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="536px" />

<div id="install-attribution" />

#### インストール計測

広告を表示またはクリックしたユーザーの新規インストール（初回起動）をアトリビューションするためのアトリビューション期間を設定します。

1. **インストールのクリックルックバック期間**を1-24時間または1-14日に設定します。

<div id="note-2" />

<div id="re-engagement-attribution" />

#### リエンゲージメント計測

さまざまなアトリビューション期間を設定して、広告を表示した、クリックした、または携わっている既存のユーザーのリエンゲージメントをアトリビューションします。ルックバック期間内のリエンゲージメントのみがSnapchatに起因する可能性があることに注意してください。

1. **リエンゲージメントCVのクリックルックバック期間**を1-23時間または1-14日に設定します。

参考：<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#reengagement-rules-and-windows">リエンゲージメント計測の仕様と期間設定について</Anchor>

#### Re-engagement window

アプリ内イベントが主にリエンゲージメントコンバージョンに関連付けられる期間を設定します。<Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#setup-reengagement-window">詳細はこちら</Anchor>を参照してください。

* **リエンゲージメント期間**を1～23時間、1～90日間、または**全期間**に設定します。

<div id="ignore-active-users-for-retargeting" />

#### リターゲティングでアクティブユーザーを無視する

直近アプリを起動したユーザーの、<Anchor target="_blank" href="/marketers/ja/docs/set-retargeting-inactivity-window#休眠期間">リエンゲージメントとリアトリビューションを計測しない</Anchor>期間を設定します。したがって、この期間中のアクティビティはAppsFlyerに記録されません。

<div id="note-3" />

> 📘 **注記：**
>
> 設定された期間中に**休眠状態**だったユーザーのリエンゲージメントと再アトリビューションのコンバージョンは**記録されます**。

1. リターゲティングで**アクティブユーザーを無視する**をオンにします。
2. 非アクティブ期間を設定します。

<div id="in-app-event-postbacks" />

#### アプリ内イベントポストバック

ポストバック経由で送信されるAvow GmbH イベントと一緒にアプリ内イベントのマッピングを設定します。

1. **アプリ内イベントポストバック**を有効にします。
2. **イベントを追加**をクリックして、SDK または サーバー間イベントをリストに追加してください。各項目の説明は以下を参照してください。  

| パラメーター名 | 説明 |
| --- | --- |
| **AppsFlyerイベント** | これは、アプリに連携されたSDKまたはサーバー間イベントからAppsFlyerが受信したイベントの名前です。<br />**ヒント：** お探しのイベントが見つかりませんか？<ul><li>非オーガニックインストールとして計測された端末上で、そのアプリ内イベントが発生しているかを確認し、再度チェックしてください。</li><li>**AppsFlyerイベント**にイベントを入力し、**カスタムイベントを作成**をクリックしてください。<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#カスタムイベント">カスタムイベントマッピングの詳細をお読みください。</Anchor></li></ul> |
| **パートナー側のイベント名** | パートナー側で定義されている各イベントの固有の名前またはID。オプションは以下の通りです：<ul><li>**ドロップダウンボックス：** 最適な事前定義されたAppsFlyerイベントを選択します。</li><li>**カスタム：**</li></ul>**注記：** |
| **送信オプション** | 最適なイベントの送信オプションを選択します。<ul><li>**このパートナーのみ**（デフォルト）:このイベントがGoogle広告に帰属する場合のみポストバックを送信します。</li><li>**オーガニックを含むすべてのメディアソース：** 任意のパートナーに紐づくイベント及びオーガニックイベントのポストバックを送信します。</li></ul> |
| **送信データ** | <ul><li>**値も収益も送信しない**（デフォルト）:イベント値なしでイベント自体のみを送信します。</li><li>**Values & no revenue（値は送信し、収益は送信しない）：** 収益値**以外**のすべてのパラメーターを送信します。</li><li>**Values & revenue（値も収益も送信する）**：収益の額を**含む**（存在する場合）、すべてのイベント値を送信します。</li></ul> |

3. [オプション] ポストバックするイベントの<Anchor target="_blank" href="/marketers/ja/docs/in-app-event-postback-configuration#条件付きアプリ内イベントポストバック">条件を設定</Anchor>するには、　**条件を追加**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> アイコンをクリックします。
4. **連携を保存**をクリックします。
5. ［任意］連携設定を保存したあとに、他のアプリのこのパートナーとの連携設定を編集することも可能です：
   1. 左上のパートナー名の下にある、アプリ名をクリックしてアプリ一覧を開いてください。
   2. ドロップダウンリストから別のアプリを選択してください。
   3. 選択したアプリで、連携ステップを再度実施してください。

<div id="note-4" />

> 📘 **注記：**
>
> iOS アプリの場合のみ:ポストバックや<Anchor target="_blank" href="/marketers/ja/docs/about-raw-data-identifier-restrictions">レポート</Anchor>を介してパートナーと共有されるデータのコントロールは、**高度なプライバシー（ iOS 14.5 以降）**[の切り替え状態](#advanced-privacy)によって異なります。

<div id="u-parameter-mapping" />

#### パラメーター マッピング:

* たとえば、キャリアデータが欠落している場合、AppsFlyerはu5を送信しません。

| パラメータ名 | 名前 | 値の例 |
| --- | --- | --- |
| u1= | af device id | 1540995037437-2811776739500410055 |
| u2= | customer user id | eaf8a5f2.1836.4686 |
| u3= | **Android：**  <br />advertising\_id  <br />**iOS**: idfa | 9d9d03ab-f211-4e17-994e-d0afdf23ac01 |
| u4= | Wi-Fi | true |
| u5= | キャリア | Jio%204G |
| u6= | country code | IN |
| u7= | 地域 | HR |
| u8= | city | Gurgaon |
| u9= | デバイスタイプ | motorola::Moto G (4) |
| u10= | os version | 7 |
| u11= | sdk version | v4.8.18 |
| u12= | app version | 3.31.1 |
| u13= | install timestamp | 1540995041 |
| u14= | click time | 1546441586 |
| u15= | impression time | 1546441586 |
| u16= | campaign name* | Appinstall\_campaign |
| u17= | Campaign ID | 12345ABC |
| u18= | adset name* | Appinstall\_adset |
| u19= | Adset ID | 12345ABC |
| u20= | ad name* | Appinstall\_ad |
| u21= | Ad ID | 1234567ABCDE |
| u22= | site id | site\_id\_123456 |
| u23= | event time | 2019-01-04 12:56:35.707 |
| u24= | eventName | af\_purchase |
| u25= | event value | `{"af_price":459,"af_content_id":"77147","af_revenue":4.59,"af_currency":"EUR"}` |
| u26= | currency | 価格はユーロで表示されます。 |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="計測リンクタブ">

**インプレションやクリック数の記録のみに、DV360でAppsFlyerの計測リンクを使用**することもできます。ただし、これらのリンクはアトリビューションには使用されないため、パラメーターを追加しても、そのパラメータや他のデータは使用できません。

DV360のクリック数をAppsFlyerで計測したい場合、DV360の管理画面にてAppsFlyer計測リンクを追加する必要があります。その際に、計測URL内のキャンペーン名が、GMPの**Placement ID**と一致することを確認してください。こうすることで、AppsFlyerはクリックデータを正しいキャンペーンに追加することができます。

AppsFlyerで**クリック**をカウントする場合は、次のリンクを使用します。

```http
https://app.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=${UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

AppsFlyerで**インプレッション**をカウントする場合は、次のリンクを使用します。

```http
https://impression.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=%24{UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="コストタブ（コスト、クリック数、インプレッション数の取得）">

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="広告収益タブ">

</Accordion>


<span id="setting-up-gmp-dv360-for-agencies"></span>代理店は広告主に代わってGMPでキャンペーンを実行することができます。

<div id="agency-setup" />

#### 代理店の設定

| 作業担当： | 手順 |
| --- | --- |
| 広告主 | <ol><li>AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択します。</li><li>対象の代理店を選択してください。</li><li>[**権限**] タブに移動し、[**代理店権限**] をオンにします。</li><li>[オプション] **連携**タブで**アプリ内イベントのポストバック**をオンにします。これにより、代理店はポストバックをオンまたはオフにすることができます。</li></ol> |
| 代理店 | <ol><li>AppsFlyer管理画面左メニュー **連携** > **連携済みパートナー**を選択します。</li><li>**連携タブ**を開きます。</li><li>**パートナーを有効にする**が**オン**になっていることを確認してください。そうでない場合、広告主側でまず広告主のGMP連携 を完了する必要があります。</li><li>ルックバック期間やアプリ内イベントのマッピングなど、残りの設定が正しいことも確認してください。必要であれば、変更を広告主に依頼してください。</li><li>最低1つ以上の**DBM Advertiser ID**を入力します。IDは <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/11415707?hl=en">GMP管理画面</Anchor>で確認できます。</li><li>**保存**をクリックしてください。</li></ol> |


| <span id="see-also"></span><span id="gmp-dv360-discrepancies"></span><span id="gmp-discrepancies"></span>原因 | 説明 | AppsFlyerからのアドバイス |
| --- | --- | --- |
| ビュースルーアトリビューションウィンドウ | DV360／CM360のビュースルー計測期間は14日ですが、AppsFlyerのデフォルト期間は1日です。 |  |
|  | AppsFlyer と GMP のマッピングが正しくない | <ul><li>リンクIDを確認してください。</li></ul> |

<div data-zendesk-anchors="h_01HMEH8VW3PYCZ6GC4T5BYBS3V=%E9%87%8D%E8%A6%81 overview=%E6%A6%82%E8%A6%81 01H8E4ZJNRMXY183TQCPW15ZQB=%E6%A6%82%E8%A6%81 01H8DYEV7JPV80T3YAJQQHBA6C=%E6%A6%82%E8%A6%81 data-sharing-between-appsflyer-and-gmp=appsflyer%E3%81%A8gmp%E9%96%93%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89 h_01HQ0QJJRMYP3E6B5FVA0V6861=appsflyer%E3%81%A8gmp%E9%96%93%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89 advertiser-gmp-integration=appsflyer%E3%81%A8gmp%E9%96%93%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89 01H8DYEV7KYNB2FJG7N1CTEE86=appsflyer%E3%81%A8gmp%E9%96%93%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E5%85%B1%E6%9C%89 h_01HPYMRJ1WVVKCHKKEA6WD0XZP=integration-tab 01H8VVCC8G0KR4AA2HD9S8QBKD=%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 general-settings=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A 01H8VVCC8GSDPSNN0AJPVZPR8P=%E4%B8%80%E8%88%AC%E7%9A%84%E3%81%AA%E8%A8%AD%E5%AE%9A install-attribution=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC 01H8VVCC8GK8VFPBEPAMVHCAWM=%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC reengagement-attribution=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E8%A8%88%E6%B8%AC 01H8VVCC8HHG5290PYF0BT29QA=%E3%83%AA%E3%82%A8%E3%83%B3%E3%82%B2%E3%83%BC%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88%E8%A8%88%E6%B8%AC reengagement-window=re-engagement-window h_01HQ06JCJZD6AMFR2B6GTMSM9S=re-engagement-window ignore-active-users-for-retargeting=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A7%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E7%84%A1%E8%A6%96%E3%81%99%E3%82%8B h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%E3%83%AA%E3%82%BF%E3%83%BC%E3%82%B2%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E3%81%A7%E3%82%A2%E3%82%AF%E3%83%86%E3%82%A3%E3%83%96%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E7%84%A1%E8%A6%96%E3%81%99%E3%82%8B h_01HMXNJVHK9C3FT8E04RE0TH99=%E6%B3%A8%E8%A8%98 inapp-event-postbacks=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8VVCC8HHZRFQ2T1X478YZMP=%E3%82%A2%E3%83%97%E3%83%AA%E5%86%85%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF 01H8VVCC8HDMTY1P2SG31HD61K=%E6%B3%A8%E8%A8%98-1 parameter-mapping=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC-%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 h_01HBBJQZSTT1HFENXNACMHFC18=%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%83%BC-%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab h_01HBBJQZSW45X3SM92H4FS94HM=%E9%87%8D%E8%A6%81 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab 01H8VVCC8HVNNQ9PJS4ZQCVDNS=setting-up-gmp-dv360-for-agencies agency-setup=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%AD%E5%AE%9A 01H8DYEV7MNFFY9ESFF2S3ETEB=%E4%BB%A3%E7%90%86%E5%BA%97%E3%81%AE%E8%A8%AD%E5%AE%9A 01H8DYEV7MTPJMY12AVHX45YFF=gmp-discrepancies" />

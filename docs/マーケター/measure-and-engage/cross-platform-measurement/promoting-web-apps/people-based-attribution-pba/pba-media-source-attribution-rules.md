---
title: PBAメディアソースのアトリビューションルール
metadata:
  keywords:
    - media source
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
  created_at: '2019-09-03T07:30:08Z'
  edited_at: '2026-10-14T09:26:16Z'
  id: 360002386997
  locale: ja
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ja/articles/360002386997
---
> **概要：** 概要：効果的なWebサイトトラフィックを促進するためのマーケティング施策の成果を測定します。訪問やコンバージョンイベントをもたらしたメディアソース、タイプ、チャネルはどれかを分析します。広告レベルの粒度で指標を確認できます。

![Touchpoints_us-en.png](https://files.readme.io/45c45c9a1b108ea31e450df4c2aaab20482c9829726d9860e55e2c9ca32c401a-360008629017.png)

<div id="website-visits-and-web-events" />

## Webサイト訪問とWebイベント

* **Web訪問の計測**
  * Webサイトにユーザーをもたらしたメディアソースを判断するために、PBAはWeb SDKによって収集されたURL上のクエリパラメーターとHTTPドキュメントリファラを分析します。
  * この記事で詳しく説明されているとおり、ルールに基づいたメディアソースの判断には、収集されたデータが使用されます。同様に、メディアタイプとメディアチャネルが決定されます。
  * 訪問データは、<Anchor target="_blank" href="/marketers/ja/docs/pba-raw-data-reports">PBAローデータ</Anchor>に記録されます。
* **キャンペーン**情報は次から抽出されます：
  * メディアソースを使用したクエリパラメーター
  * <Anchor target="_blank" href="/marketers/ja/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Ads 連携</Anchor>を使用したGCLID（利用可能な場合）
* **Webイベント**
  * Webイベントは、訪問者がWebサイト上でアクションを実行する際に発生します。例えば、商品検索、商品選択、または購入などです。
  * イベントは、30日間のルックバック期間に発生した最新のダイレクト以外のWeb訪問に紐づきます。
  * イベントは、以下のように細分されています：   
    * コンバージョンイベント例：購入や登録など）。
    * スタンダードイベント

PBA管理画面とローデータレポートは、成果が紐づくメディアソース、タイプ、チャネル、キャンペーンを利用します。

![MediaSource_us-en.png](https://files.readme.io/bcb3e471753809b0fdf1a0e1dc9783002004b1988f4701ab30524c1eb7b9fbfc-360008629057.png)

分かりやすいように、次の表には決定されたメディアソースとそのタイプおよびチャネルの例を示しています。

| Media source | メディアタイプ | メディアチャネル |
| --- | --- | --- |
| ダイレクト | Earned | ダイレクト |
| <ul><li>Social Facebook</li></ul> | オウンド | Social media（ソーシャルメディア） |
| <ul><li>Meta ads</li><li>X Ads</li></ul> | 支払済 | Social media（ソーシャルメディア） |
| Google search | Earned | Organic search |
| Email | オウンド | Email |
| googleadwords\_int | 支払済 | Ad |
| usatoday.com | Earned | Referral（紹介） |

<div id="determining-the-media-source" />

## メディアソースの決定

PBAはメディアソース、メディアタイプ、メディアチャネルを階層的に決定します。つまり、関連するメディアソースルールとメディアソースを決定することを意味します。その後、メディアタイプとメディアチャネルが決定されます。

<div id="media-source-rules" />

<Accordion title="メディアソースルール">

次の表に示すメディアソースルールは、優先度の高いものから低いものの順にランク付けされます。

<Table>
  <thead>
    <tr>
      <th>
        メディアソースルール
      </th>
      <th>
        メディアソースの判別
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        セルフアトリビューションの防止
      </td>
      <td>
        イベント成果をWebサイト自体と他の関連ドメインに紐づける（セルフアトリビューション）のを防ぐために、<Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings#domain-exclusion">ドメインの除外</Anchor>リストを使用します。リストには、次の内容で構成されます。

        * プライマリードメイン：ブランドバンドルに含まれるWebアプリのURLで決定されます
        * 外部ドメイン：自身で設定した決済ゲートウェイと決済処理サイトおよび、AppsFlyerにより設定されたPayPalやStripeなどの一部のドメインは自動的に除外されます。
      </td>
    </tr>
    <tr>
      <td>
        pid
      </td>
      <td>
        URLに含まれる pid 値で判断されます。一部のSRNでは、一貫性を保つため、および分かりやすいように、pid を 商用名にします。例えば、pid=facebook\_int は Facebook Ads として、twitter\_int は Twitter として表示されます。
      </td>
    </tr>
    <tr>
      <td>
        クリックID
      </td>
      <td>
        Googleなどの主要なアドネットワークは、クリックIDを使用してキャンペーンに自動タグをつけます。クリックIDは次のように判別されます：

        * **GCLID：**  注意
        * dcliddclid：DoubleClickのクリックIDで、*doubleclick\_int*と判別されます。
        * msclkid msclkid：BingのクリックID/strong>/span>で <Anchor target="_blank" href="http://help.ads.microsoft.com/apex/index/3/en/60000">bingsearch\_int と判別されます。</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        UTMパラメーター
      </td>
      <td>
        **UTMカスタムルール**

        | utm\_source | utm\_medium | Media source |
        | --- | --- | --- |
        | * | * email、mail、e-mail<br />* ご注意くださいutm\_medium にこれらの値が含まれる場合、utm\_source は無視されます。 | Email |
        | google | cpc / ppc / paidsearch / search | googleadwords\_int |
        | google | cpm / display / banner / video / listing | doubleclick\_int |
        | dfa / dbm | cpm | doubleclick\_int |
        | facebook | cpc / ppc / cpm / cpa / paidsocial / paid-social | Facebook広告 |
        | bing | cpc | bingsearch\_int |
        | yahoo / gemini | cpc / display / listing | yahoogemini\_int |
        | twitter | cpc | X Ads |
        | snapchat | swipe | snapchat\_int |
        | pinterest | cpc | pinterest\_int |

        一致するカスタムルールがない場合、メディアソースは、utm\_source パラメーターの値で判別されます。

        UTMパラメーターに関する情報
      </td>
    </tr>
    <tr>
      <td>
        リファラ
      </td>
      <td>
        リファラは、ユーザーをWebサイトに誘導したHTTPソースです。メディアソースは、リファラのドメイン名です。
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="media-source-type" />

<Accordion title="メディアソースタイプ">

マーケティング担当者は、通常Webメディアソースを以下の3つのタイプに分類します。

* **有料広告：** ディスプレイバナー、動画、広告キャンペーンなどの広告キャンペーン。
* **オウンド：** メールマーケティング、ソーシャル投稿、ブログなどの自社メディアからのマーケティングキャンペーン。
* **獲得：** 直接、または検索エンジン、紹介、実際のダイレクトトラフィックなどのオーガニックトラフィック。

メディアタイプは、メディアソースやその他のパラメーターと組み合わせて使用されるメディアソースルールを参照することで判別されます。

<table><thead><tr><th>適用されるメディアソースルール</th><th>Media source</th><th>メディアタイプ</th></tr></thead><tbody><tr><td colspan="1" rowspan="2"><div>pid</div></td><td><p>pid ルールは、メディアソースが次の場合に判別されます： </p><ul><li>Social Facebook</li><li> </li><li>SMS</li><li>ブログ</li><li>Email</li></ul></td><td>オウンド</td></tr><tr><td>その他のメディアソース</td><td>支払済</td></tr><tr><td>クリックID</td><td><p><span>クリックIDを使用して判別：</span></p><ul><li>gclid</li><li>dclid</li><li>msclkid</li></ul></td><td>支払済</td></tr><tr><td colspan="1" rowspan="2"><div>UTM</div></td><td>UTMカスタムルールはメディアソースを決定します</td><td>支払済</td></tr><tr><td>その他のメディアソース</td><td>オウンド</td></tr><tr><td rowspan="2">リファラ</td><td><p><span>リファラのドメインが次のいずれかの場合：</span></p><ul><li>googleads.g.doubleclick.net </li><li>tpc.googlesyndication.com</li></ul></td><td><p>支払済</p></td></tr><tr><td>その他のメディアソース</td><td><p>Earned</p></td></tr></tbody></table>

</Accordion>

<div id="media-source-channel" />

<Accordion title="メディアソースチャネル">

メディアチャネルは、ここに記載されているルールにより判別されます。

<table><thead><tr><th>優先度</th><th>メディアチャネルのルール</th><th>範囲外の値は</th><th>メディアチャネル</th></tr></thead><tbody><tr><td rowspan="4">最優先されます</td><td rowspan="4">メディアソースが次のいずれかの場合</td><td>ダイレクト</td><td>ダイレクト</td></tr><tr><td><ul><li>Google Search</li><li>Yahoo Search</li><li>Bing Search</li></ul></td><td>Organic search</td></tr><tr><td><ul><li>facebook</li><li>twitter</li><li>snapchat</li><li>pinterest</li><li>LinkedIn</li><li>WhatsApp</li></ul></td><td>Social media（ソーシャルメディア）</td></tr><tr><td>Email</td><td>Email</td></tr><tr><td> </td><td>メディアタイプは有料広告です</td><td> </td><td><div>Ad</div></td></tr><tr><td> </td><td>リファラによって判別されるメディアソース</td><td> </td><td>Referral（紹介）</td></tr><tr><td>最も低い優先度です。</td><td>前述のいずれの条件も一致しない場合</td><td> </td><td>その他</td></tr></tbody></table>

</Accordion>

<div id="determine-the-campaign" />

<Accordion title="キャンペーンの判別">

* キャンペーンは、以下を使用して判別されます：
  * メディアソースURLパラメーターごとのキャンペーンURLパラメーター。
  * GclidクリックIDと <Anchor target="_blank" href="/marketers/ja/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Ads</Anchor> 連携。
* 関連するキャンペーンパラメーターがURL上に見つからない場合、キャンペーンは取得されません。

| 使用されるメディアソースパラメーター | 使用されるキャンペーンパラメーター |
| --- | --- |
| pid | URL上で利用可能なAppsFlyerのメディアソースパラメータは、ローデータとWebサイトアトリビューションダッシュボードのデータに使用されます。使用可能なパラメーター：c\_id / af\_adset / af\_adset\_id / af\_ad\_id |
| クリックID—gclid | Google AdsからAPI経由で取得 |
| utm\_source | utm\_campaign |

</Accordion>

<div id="additional-attribution-rules" />

## 追加のアトリビューションルール

<div id="visit-recognition-rules" />

<Accordion title="訪問の認識ルール">

Webサイトへの訪問は、以下のルールを使用し、現在のセッションの状態を考慮して記録されます。アクティブセッションは、30分以下の休眠期間を持つセッションです。

* ユーザーが<Anchor target="_blank" href="/marketers/ja/docs/pba-brand-bundles-and-settings#domain-exclusion">外部の除外</Anchor>ドメインから来た場合、この訪問は記録されません。
* アクティブセッション中：ページロードにメディアソースが含まれている場合は、訪問を記録します。
* アクティブセッションが無い場合：訪問を記録します。
* 最低の滞在時間はありません。

**PBA訪問記録ルール**

![PBA_-_PBA-vist.png](https://files.readme.io/651c3ee4d39832297b7d6dc871aa281f1fa3219264ba264851ad0cc643b8baee-360015532817.png)

</Accordion>

<div id="data-finalization" />

<Accordion title="データのファイナライズ">

* データのファイナライズ：
  * Webアシストインストール、Webサイトアトリビューション、およびコンバージョン経路については、PBAはコンバージョン後7日間、追加の関連イベントを識別します。これにより、コンバージョンをもたらしたと特定されたメディアソースが変更される可能性があります。
  * 関連するローデータレポートでは、最初の7日間は *final\_data* の項目が fales になります。

</Accordion>

<div data-zendesk-anchors="website-visits-and-web-events=web%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%AA%E5%95%8F%E3%81%A8web%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 h_01H936NV7VP8CTE9BZP6D5E7NK=web%E3%82%B5%E3%82%A4%E3%83%88%E8%A8%AA%E5%95%8F%E3%81%A8web%E3%82%A4%E3%83%99%E3%83%B3%E3%83%88 determining-the-media-source=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E6%B1%BA%E5%AE%9A h_01H936NV7VZHWBDPHFJRFFCPSW=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E6%B1%BA%E5%AE%9A h_01H936NV7V6GMWSCHNDMJ205JS=media-source-rules h_01H936NV7W9ZFMET29GY6JTBGN=media-source-type h_01H936NV7W61DB43D3E1MNEJHN=media-source-channel h_01H936NV7WZYE3EKYZ9PX9ZJXW=determine-the-campaign additional-attribution-rules=%E8%BF%BD%E5%8A%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%BC%E3%83%AB h_01H936NV7WA9WZM4RTQZHD22VV=%E8%BF%BD%E5%8A%A0%E3%81%AE%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%AB%E3%83%BC%E3%83%AB h_01H936NV7W323HQMG5E6SQFQEN=visit-recognition-rules h_01H936NV7WSB2FMRBPDN936TWM=data-finalization" />

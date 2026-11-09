---
title: Google Playインストールでプレロードキャンペーンを測定する
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-07-25T11:31:06Z'
  edited_at: '2026-10-14T09:37:51Z'
  id: 4404557237649
  locale: ja
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ja/articles/4404557237649
---
> **概要：** AppsFlyerは、マーケターがモバイルキャリアやアプリ発見パートナーと契約し、ユーザーがデバイスを初めて起動したときにアプリをプレロードするために、Google Play自動インストール（PAI）を使用してインストールを帰属させます。　**注：** 注：この計測方法は、APKによる計測方法とは異なります。

<div id="pai-preload-attribution" />

## プリロードアトリビューション

プレロードキャンペーンでは、オリジナルデバイスメーカー（OEM）、モバイルキャリア、およびアプリ発見パートナーが、デバイスが初めてアクティブ化されたときにダウンロードされるアプリをプレロードします。

プリインストールキャンペーンは、広告主がオンラインキャンペーンを実施することなく、潜在的に多くのオーディエンスにリーチすることができます。

Google Play自動インストール（PAI）（3つのプレロード帰属方法の1つ）は、マーケターにプレロードキャンペーンのパフォーマンスを測定するための正確でプライバシーを保護するメカニズムを提供します。この方法は、マーケターに決定論的なアトリビューション結果を提供すると同時に、デバイスおよびユーザー識別子とは無関係に生成されたリファラーとのリファラーマッチングを介してアトリビューションが実行されるため、ユーザーのプライバシーが保護されることを保証します。

AppsFlyerは、プリロードインストールを最優先にアトリビューションします。つまり、ユーザーがアプリを初めて起動する前に他の広告キャンペーンに接触しても、プリロードキャンペーンにアトリビューションが与えられます。その他のキャンペーン接触は、アシストインストールと見なされます。

<div id="note" />

> 📘 **注意**
>
> プレロード等価帰属優先設定はGoogle PAIには適用されません。

<div id="flow" />

### フロー

1. 新しいデバイスが初めてアクティベートされると、プリインストールパートナーが設定したルールに従って、クラウドから設定済みのアプリが自動的にインストールされます。
2. ユーザーがプレロードされたアプリを初めて起動します。
3. AppsFlyer SDKはGoogle PlayリファラーAPIにクエリを送信します。
4. AppsFlyerの帰属は取得したデータに基づいています。

<Image align="center" alt="PAI-attribution-flow_en-us.png" src="https://files.readme.io/c7f02a0a6637e9c73e9a39f97e71d5d37d8d2712b458735cd87b4b245ad0fccb-small-4404791877649.png" />

<div id="data-availability" />

### データの可用性

Google Play自動インストール（PAI）プレロードパフォーマンスデータは以下で利用可能です：

* 概要ダッシュボードおよびプレロードパートナー（メディアソース）およびキャンペーンレベルで集計された集計レポート。
* ローデータレポート

生データには以下のフィールドが含まれます：

* Media\_source = パートナーID
* Match\_type = preload\_pai
* Campaign\_name = `<preloadpartner ID>` によるキャンペーンのプリロード

<div id="set-up-google-play-auto-install-pai-preload-attribution" />

### Google Play自動インストール（PAI）プレロード帰属を設定する

**PAIプレロード帰属を設定するには：**

1. AppsFlyer管理画面 左メニュー **連携** > **連携済みパートナー**を選択します。
2. プリロードパートナーを選択します。
3. **プリロード計測をオン**にします。
4. **プリロードルックバック期間** を設定します。

   <div id="note-1" />

   > 📘 **注意**
   >
   > Googleはリファラーデータを最大90日間保存します。PAIのルックバックウィンドウを90日以内に設定します。UIでは最大180日まで許可されていますが、90日を超えるデータはGoogleからは利用できません。

5. **連携を保存** をクリックします。
6. プリロードパートナーに、キャンペーン計測を設定する準備ができたことを知らせます。

<div id="partners-supporting-google-play-auto-install-pai-preload-campaigns" />

### Google Play自動インストール（PAI）プレロードキャンペーンをサポートするパートナー

<table><thead><tr><th rowspan="2">Partner</th><th rowspan="2">pid</th></tr></thead><tbody><tr><td><p>Xiaomi</p></td><td><span>xiaomipai_int</span></td></tr><tr><td><p>Transsion</p></td><td><span>shalltrypai_int</span></td></tr><tr><td><p>Oppo</p></td><td><span>oppopaipreinstall_int</span></td></tr><tr><td><p>Vivo</p></td><td><span>vivootapreload_int</span></td></tr><tr><td><p>TCL</p></td><td><span>tclpai_int</span></td></tr><tr><td><p>モトローラ</p></td><td><span>motorola_int</span></td></tr><tr><td><p>MITV</p></td><td><span>mitvpai_int</span></td></tr><tr><td><p>ZTE</p></td><td><span>ztepai_int</span></td></tr><tr><td><p>レノボタブ</p></td><td><span>lenovotabpai4p_int</span></td></tr><tr><td><p>KDDIプレインストール</p></td><td><span>kddipai_int</span></td></tr></tbody></table>

<div id="note-2" />

> 📘 **注意**
>
> ※代理店アカウントからは、クライアントに対してプリロードキャンペーンを有効にすることはできません。

<div id="postbacks-for-preload-partners" />

## プリロードパートナーのポストバック

AppsFlyerとの連携の一環として、プリインストールパートナーはAppsFlyerから送信されるポストバックの内容とエンドポイントの情報を定義する必要があります。

ポストバックに含まれる場合、マクロにはユーザーに関連するデータが含まれます。サポートされているマクロについては以下の表を参照してください。

* **ソース**:データソース：データの取得元がどこかを示しています：
  * **SDK**:SDK＝アプリに実装されているAppsFlyerSDK、もしくはServer-to-ServerのAPI
  * AppsFlyerAF＝AppsFlyer側で処理した情報

| プレロードパートナー用のポストバックマクロ（パラメータ名） | ソース | 説明 |
| --- | --- | --- |
| app\_name | SDK | 広告主が設定したアプリ名 |
| country\_code | AppsFlyer | ISO 3166 (alpha-2)を使用した国コード：US, CN など米国、中国。 |
| install\_time | SDK | インストールのタイムスタンプ |
| 言語 | SDK | 端末OSによって設定され、端末から取得した言語設定(+地域情報) |
| app\_id | SDK | AppsFlyerで使用される一意のアプリ識別子 |
| app\_version | SDK | 開発者によってアプリのコードに設定された、アプリのバージョン |
| device\_type | SDK | デバイスの商用モデル名。例：SM-GM284またはiPhone7 |
| os\_version | SDK | デバイスのOSバージョン |

<div id="postback-example" />

#### ポストバックの例

```http
http://YourCompanyDomain.com?pid=(preinstall_partner)&app_name=(app-name)&app_id=(app-id)&install_time=(install-unix-ts)
```

<div data-zendesk-anchors="pai-preload-attribution=%E3%83%97%E3%83%AA%E3%83%AD%E3%83%BC%E3%83%89%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HEJG4FHSGJDZ77Y281F7SG4R=%E3%83%97%E3%83%AA%E3%83%AD%E3%83%BC%E3%83%89%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01K8XBQ3YKJ8KBMPMAAMBZP25E=%E6%B3%A8%E6%84%8F pai-preload-attribution-flow=%E3%83%95%E3%83%AD%E3%83%BC h_01HEJG4FHSF8X1TEMMNJBYP71Z=%E3%83%95%E3%83%AD%E3%83%BC campaign-performance-data-availability=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E7%94%A8%E6%80%A7 h_01HEJG4FHSCMPJM5TRNSPNDHVN=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E5%8F%AF%E7%94%A8%E6%80%A7 run-preload-referrer-campaigns=google-play%E8%87%AA%E5%8B%95%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%ABpai%E3%83%97%E3%83%AC%E3%83%AD%E3%83%BC%E3%83%89%E5%B8%B0%E5%B1%9E%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01HEJG4FHS7E5JZT2BBYG2BNEK=google-play%E8%87%AA%E5%8B%95%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%ABpai%E3%83%97%E3%83%AC%E3%83%AD%E3%83%BC%E3%83%89%E5%B8%B0%E5%B1%9E%E3%82%92%E8%A8%AD%E5%AE%9A%E3%81%99%E3%82%8B h_01K8XBJ9EJ38ST3KAFF879ZQ1H=%E6%B3%A8%E6%84%8F-1 partners-supporting-preload-referrer-campaigns=google-play%E8%87%AA%E5%8B%95%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%ABpai%E3%83%97%E3%83%AC%E3%83%AD%E3%83%BC%E3%83%89%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC h_01HEJG4FHSNEGR7R9VCSDT9TSZ=google-play%E8%87%AA%E5%8B%95%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%ABpai%E3%83%97%E3%83%AC%E3%83%AD%E3%83%BC%E3%83%89%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%82%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%83%88%E3%81%99%E3%82%8B%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC h_01K8XBVZJGG59K3XJ8R346X9FH=%E6%B3%A8%E6%84%8F-2 postbacks-for-preload-partners=%E3%83%97%E3%83%AA%E3%83%AD%E3%83%BC%E3%83%89%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF h_01HEJG4FHSKD7DY6W7W65YBMGN=%E3%83%97%E3%83%AA%E3%83%AD%E3%83%BC%E3%83%89%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%81%AE%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF preload-postback-example=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E4%BE%8B h_01HEJG4FHSBFB456Z752HFC8KN=%E3%83%9D%E3%82%B9%E3%83%88%E3%83%90%E3%83%83%E3%82%AF%E3%81%AE%E4%BE%8B" />

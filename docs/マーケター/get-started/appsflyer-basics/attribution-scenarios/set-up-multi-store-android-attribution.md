---
title: 複数ストアにおけるAndroidアプリ計測の設定
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2026-10-14T09:38:28Z'
  id: 207447023
  locale: ja
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ja/articles/207447023
---
> **概要：** 概要：複数のAndroidストアで配信しているアプリを計測して、データを単一のアプリ管理画面、またはストアごとのアプリ管理画面で確認しましょう。

<div id="multi-store-android-attribution" />

## 第三者ストアにおけるAndroidアトリビューション

AppsFlyerはアプリストアに関わらず、アプリを計測します。つまり、Google PlayストアとAmazon、Opera、GetJar、Baidu、Huaweiのような第三者Androidアプリストアが計測対象です（別名：外部ストア、代替Androidアプリストア）。複数ストアでアプリを配信しているアプリ所有者は、全てのストアのデータを一箇所で確認できる**単一の管理画面**か、**ストアごとの管理画面**を選択できます。

<div id="note" />

> 📘 **注**
>
> * AppsFlyerのAndroid計測では、GAIDと<Anchor target="_blank" href="/marketers/ja/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>を含む全てのデバイス識別子タイプをサポートしています。
> * 中国で配信されているアプリについては、<Anchor target="_blank" href="/marketers/ja/docs/measure-attribution-in-the-chinese-domestic-market">中国国内市場での Androidアプリのアトリビューション</Anchor>をご覧ください。

![DashboardType_us-en-new.jpg](https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg)

<div id="single-dashboard-vs-dashboard-per-store" />

### 単一管理画面 vs. ストアごとの管理画面

* 単一管理画面
* ストアごとの管理画面つまり、アプリを配信するストアの数だけ管理画面が存在します。

<table><thead><tr><th> </th><th>単一管理画面<br/>[ベストプラクティス]</th><th> ストアごとの管理画面</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>Androidパッケージ名</td><td colspan="2">選択したオプションに関わらず同じパッケージ名を使用してください。 </td></tr><tr><td><span id="channel-name"></span>チャネル名</td><td>設定するものはありません</td><td><ul><li>AppsFlyer管理画面に<span>Android外部ストアAPK</span>を使用してアプリを追加する際に、チャネルを設定してください。</li><li><span>チャネルはストアを識別します。</span></li><li>Androidパッケージ名とチャネルの組み合わせにより、一意に各AppsFlyer管理画面を識別します。 </li><li>例： </li><li>APKにチャネル設定があるが、この設定のアプリが無い場合、トラフィックはデフォルトのアプリに紐づきます。これは、チャネル設定が無いアプリ、つまりGoogle Play Storeのアプリを指します。 </li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>install_app_store の入力</td><td><ul><li>ダウンロードによってアプリを提供するストアを一意に識別します。</li><li>Google Playストアの場合は空白になります。 </li><li>このストア名は <a href="./set-up-multi-store-android-attribution#single-dashboard-apk-preparation">manifest/APK</a> で設定されます。</li></ul></td><td>N/A</td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#onelinkテンプレートの作成" target="_blank">OneLinkテンプレート</a></td><td>OneLinkを使用する場合は、この方法をお勧めします。 </td><td>N/A </td></tr><tr><td><span id="measurementattribution-links"></span>計測／アトリビューションリンク </td><td><ul><li>リンクはストアに関わらず同じです。</li><li>正しいストアへリダイレクトするには、<a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">af_r</a> を使用してリダイレクトURLを設定してください。</li></ul></td><td><ul><li>ストアごとに一意のリンクが必要です。</li><li> </li><li>アプリIDはチャネル名にAndroidパッケージ名を追加したものです。例：com.abc.def-def_store.<br/>したがって計測リンクも異なります。</li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>install_app_store を持つ使用可能なレポーティングオプション</td><td> </td><td>N/A </td></tr><tr><td><span id="considerations"></span>注意事項</td><td><ul><li>アトリビューションの精度 </li><li><span>オーガニックインストールは、全てのストアからのAPKのオーガニックインストールが1つの管理画面上に反映されます。</span></li><li><span>現在、レポートオプションとストアごとの内訳は、オーバービュー、コホート、ローデータのみで表示されます。</span></li></ul></td><td><ul><li>アトリビューションの精度</li><li> <span></span>オーガニックと非オーガニックインストールおよびアプリ内イベントデータを、ストア（チャネル）ごとに、AppsFlyerの別々のアプリ管理画面で表示します。</li><li><span>全てのストアを一箇所で表示するには、コホートレポートを使用してください。</span></li><li> </li></ul></td></tr></tbody></table>

<div id="set-up-tasks" />

## 設定に必要なタスク

次のワークフローでは、目的のオプションを設定するために必要なアクティビティを示します。タスクは、マーケティング担当者とディベロッパーのタスクに分かれています。

ストアごとの管理画面オプションは、ストアごとにこのタスクを繰り返してください。

<div id="before-you-begin" />

### **始める前に**

* チャネルと install\_app\_store パラメーターの命名規則を決定します。
* 次のネーミングテーブルを使用してチャネルとストアをマッピングしてください。
* このテーブルはディベロッパーがAPKを準備する際に使用します。

<table><thead><tr><th>パラメータ</th><th>手順</th><th>単一管理画面<br/>[ベストプラクティス]</th><th>ストアごとの管理画面</th></tr></thead><tbody><tr><td>Androidパッケージ名</td><td>全ての管理画面オプションで同じパッケージ名を使用</td><td colspan="2">既にアプリがGoogle Play Storeに存在する場合は、既存のパッケージ名を使用してください。例：comb.abc.def</td></tr><tr><td>チャネル名</td><td>各ストアで一意の値。</td><td>設定しません。空白のままにしてください。 </td><td><p>ストアごとに一意の値。ストア用に準備された個々のAPKの値と、AppsFlyerでアプリを追加するときの値を設定します。 </p><p>Google PlayストアAPKにはチャネルを設定しないでください。 </p></td></tr><tr><td>インストールアプリストア AF_STORE</td><td>一意のストア識別子</td><td>ストアごとに一意の値。manifestを介してAPKで設定します。各ストアは独自のAPKを持っています。</td><td> 設定されません</td></tr></tbody></table>

<div id="tasks" />

### タスク

| ステップ | 担当者 | 単一管理画面 | ストアごとの管理画面 |
| --- | --- | --- | --- |
| 1 | 開発者 | [APKの準備](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [APKの準備](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | マーケティング担当者 | アクションは必要ありません。前提として、アプリはすでにAppsFlyerでアクティブになっています。 | AppsFlyerに[アプリを追加](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app) |
| 3 | マーケティング担当者 | [計測リンクを準備します。](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | アプリIDとチャネル名を組み合わせた計測リンクを準備してください。 |
| 4 | ディベロッパーとマーケティング担当者 | [テスト](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [テスト](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

<div id="procedures" />

## 手順

<div id="single-dashboard-apk-preparation" />

<Accordion title="単一管理画面—APKの準備">

Androidパッケージ名によってどの管理画面にアトリビューションデータが表示されるかが決まります。単一管理画面の場合は、全てのストアで同じAndroidパッケージ名を使用します。 その場合チャネルパラメーターは使用しません。

ダウンロードされたストアの識別は、このセクションで説明するとおり、AF\_STORE パラメーターによってSDKで設定されます。  AF\_STORE パラメーターは大文字小文字を区別しません。例：ABC、abc、Abc。

**APKを準備する方法：**

1. アプリビルドのコピーを作成してください。　**注：** 注：Androidパッケージ名を変更しないでください。
2. 個々のストアを識別するには、次のいずれかの方法を使用します。
   * ストアを識別するために、AndroidManfest.xml の `<application>` タグ内に、次を追加してください。AF\_STORE パラメーターをアプリストア名に設定してください。

     ```xml
     <application>
        ...
        <meta-data android:name="AF_STORE" android:value="EnterStoreNameHere"/>
        ...
     </application>
     ```

     **--または--**
   * APIメソッドAPIメソッド：代替アプリストアごとに別々のAPKを準備してください。setOutOfStore API を呼び出して、AF\_STORE の値を設定してください。ストアごとに一意の値を設定してください。  

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("EnterStoreNameHere")
     ```

ここで設定した値は、AppsFlyerのローデータの install\_app\_store 項目に表示されます。この項目は次で利用できます：

* オーバービュー管理画面
* コホートダッシュボード
* <Anchor target="_blank" href="/marketers/ja/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">ローデータレポート</Anchor>（ローデータレポートはAppsFlyerのプレミアム機能です）

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="単一管理画面—計測リンク">

1. この値は、計測リンク上の af\_r マクロに入力され、ユーザーを正しいアプリストアのランディングページにリダイレクトします。　例：   
   **注記：** <Anchor target="_blank" href="/marketers/ja/docs/app-settings#outofstore-app-url">詳細はこちら</Anchor>
2. af\_r マクロにストアのランディングページURLを入力します。
3. 追加の<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#計測リンクパラメーター">計測リンクパラメーター</Anchor>を設定してください。
4. 外部ストアメディアソースは、**計測にIDマッチングを使用**し、AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#probabilistic-modeling">確率論的モデリング</Anchor>はフォールバックメソッドとして機能します。
5. リンクURLに1つ以上のユーザーIDプレースホルダを追加してください：
   * `android_id`
   * `advertising_id`
   * `oaid`
6. 計測リンクをコピーし、アドネットワークに渡してください。

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="アプリごとの管理画面—APKの準備">

マニフェストで設定されたチャネルパラメーターとAndroidパッケージ名の組み合わせにより、どのストアに計測データが紐づくかが決定されます。

**ストアごとに別々のAPK／マニフェストを準備する方法：**

* ストアを識別するために、AndroidManfest.xml の `<application>` タグ内に、次を追加してください。アプリストア名に CHANNEL パラメーターを設定してください。

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="EnterStoreNameHere"/>
       ...
  </application>
  ```

  **注：注：パラメーターでは大文字と小文字が区別されます。 ハイフン (-) やアンダースコア (\_) などの他の文字は使用できません。**

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="ストアごとの管理画面—アプリの追加">

APK／マニフェストで設定されたAndroidパッケージ名とチャネルの組み合わせによって識別される管理画面（アプリ）を追加してください。例：例：Androidパッケージ名が com.myapp、チャネル名が abcstoreの場合、一意の管理画面名は com.myapp—abcstore です。

**AppsFlyerのストアごとの管理画面にアプリを追加する方法**：

2. **Android > サードパーティストア**を選択してください。
3. 次の項目を入力してください：
   * **Androidパッケージ名**
   * チャネル名 チャネル名：同じパッケージ名を持つ管理画面を区別するための一意の識別子（ストア名）です。このストア用に用意したAPKの値と同じものを使用していることを確認してください。  
     **注記：** ハイフン (-) やアンダースコア (\_) などの他の文字は使用できません。
   * **アプリURL：**
     * 計測リンクに af\_r マクロを入力するデフォルトのURLダウンロードアドレスを含みます。APKがホストされているURL、またはランディングページURLを入力してください。
     * これは作成時にアトリビューションリンクごとに変更できます。
4. **次へ**をクリックしてください。
5. アプリの追加を完了するには、画面の手順に従ってください。

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="テスト—両方の管理画面オプション向け">

<div id="non-organic-installs" />

#### **非オーガニックインストール**

**非オーガニックインストールのテスト方法：**

1. アプリがインストールされていないAndroidデバイスを使用するか、<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">デバイスを登録</Anchor>してください。
2. <Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink</Anchor>を使用して、テスト用計測リンクを生成します。メディアソース名に ' test' と設定してください ("&pid=test")。
3. GAID、OAIDまたはAndroid IDの広告IDをクリックURLに追加してください。

   ```http
   https://app.appsflyer.com/com.greatapp?pid=test
   &af_r=https://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   計測リンクを自身のメールに送信して、クリックしてください。**リダイレクト後、ストアからインストールしないでください**。代わりに、AppsFlyerの計測SDKが実装されたベータ版の最新アプリをインストールし、起動してください。

| 単一管理画面 | ストアごとの管理画面 |
| --- | --- |
| <ol><li>データエクスポートページのインストールローデータにて、アプリインストールを確認してください。</li><li>test メディアソースに1件のインストールコンバージョンが表示されるはずです。**Install App Store** という名前の列に、manifest.xml ファイル内のものと同じストアの名前が表示されます。</li></ol> | <ol><li>アプリごとの管理画面を開きます。</li><li>データエクスポートページのインストールローデータ、またはアプリのオーバービューページをインストールを確認してください。</li><li>“test” メディアソースにて、1件のインストールコンバージョンが確認できるはずです。</li></ol> |

<div id="organic-installs" />

#### **オーガニックインストール**

**オーガニックインストールのテスト方法：**

1. アプリがインストールされていないAndroidデバイス、または<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">登録されているデバイス</Anchor>をしてください。
2. AppsFlyerの計測SDKが実装されたベータ版の最新アプリをインストールし、起動てください。
3. 結果を確認してください：

<div id="expected-results" />

#### 期待される結果

| 単一管理画面 | ストアごとの管理画面 |
| --- | --- |
| オーバービューページで新しいオーガニックインストール（「Organic」メディアソースの下）を確認してください。現在、単一アプリの方法では、オーガニックインストールの流入元を示す指標はありません。 | <ol><li>テスト対象アプリの管理画面でオーバービューページを開いてください。</li><li>「organic」メディアソースにて、1件のインストールコンバージョンが確認できるはずです。</li></ol> |

</Accordion>

<div id="additional-features" />

## 追加機能

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="FacebookからAmazonアプリストアへユーザーを誘導する">

1. Android**セクションの**Facebookのアプリ設定にて、アプリへのURLリンクを設定してください。
2. アプリ管理者としてFacebookにログインし、<Anchor target="_blank" href="https://developers.facebook.com/apps/">https://developers.facebook.com/apps/</Anchor>を開き、アプリを選択してください。
3. 設定からAndroidの設定を開きます。まだAndroidを設定していない場合は、プラットフォームを追加してください。
4. アプリ固有のAmazonアプリストアのURLを含む、必要な詳細を追加して下さい。   

   [![outofstore_1.png](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)

</Accordion>

* コホート：
  * 複数の管理画面（アプリ）を単一レポートにまとめる
  * install\_app\_store 別に細分化し、管理画面ごとにパフォーマンスを表示


<div id="referrer-implementation-thirdparty-android-app-stores" />

<Accordion title="リファラの実装—サードバーティAndroidアプリストア">

AppsFlyerとリファラ計測を連携しているサードバーティAndroidストア

| サードバーティアプリストア | 開始日 | SDKバージョン |
| --- | --- | --- |
| <span id="huawei-app-store"></span>Huawei App Store | 2020年7月 | 2024-02-26 |
| <span id="samsung-galaxy-store"></span>Samsung Galaxy Store | 2020年12月 | 6.1.1 + |
| <span id="xiaomi-getapps-store"></span>Xiaomi GetApps Store | 2022年9月 | 6.9.0 + |

</Accordion>

サードバーティストアのリファラによる計測は、ローデータレポートに次のように反映されます：

* Match type：計測されたサードバーティストアの名前。　（例：`huawei_referrer`）
* コントリビューターコントリビュータ：ユーザーがアプリをインストールする前に複数のアプリストアにアクセスしていた場合、AppsFlyerはこれらのアクセスをコントリビュータとみなします。このインストールは、ラストクリックのエンゲージメントの成果に紐づきます。例：
  * Googleが配信する広告をユーザーがクリックすると、Play Storeにリダイレクトされます。 ユーザーはアプリをダウンロードしません。
  * このユーザーが別の広告をクリックし、Samsung Galaxyストアにリダイレクトされます。ユーザーはアプリをダウンロードしインストールします。
  * このインストール成果は、ユーザーをSamsung Galaxyストアに誘導したアドネットワークに紐づきます。Googleはコントリビュータと見なされます。


<div id="troubleshooting" />

## トラブルシューティング

<div id="installs-attributed-to-the-default-app" />

### デフォルトアプリへのインストール計測

デフォルトアプリが無い場合は、アプリに関するデータは記録されません。

<div id="traits-and-limitations" />

## 特性と制限

| 特性 | 備考 |
| --- | --- |
| 複数のアプリストアへのOneLinkリダイレクト | アプリパッケージ名がすべてのアプリストアで同じで、1 つのダッシュボードオプションを実装する場合は、 <Anchor target="_blank" href="/marketers/ja/docs/create-a-onelink-template#onelinkテンプレートの作成">OneLinkテンプレート</Anchor> に複数のアプリストアを設定できます。 |
| Install app store |  |
|  |  |
| 広告収益 |  |

<div data-zendesk-anchors="multistore-android-attribution=%E7%AC%AC%E4%B8%89%E8%80%85%E3%82%B9%E3%83%88%E3%82%A2%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bandroid%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HJ369QB8PDKG7QQRV840KRAY=%E7%AC%AC%E4%B8%89%E8%80%85%E3%82%B9%E3%83%88%E3%82%A2%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8Bandroid%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 h_01HJ369QB876GZKQCGJZQDXDRF=%E6%B3%A8 single-dashboard-vs-dashboard-per-store=%E5%8D%98%E4%B8%80%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2-vs-%E3%82%B9%E3%83%88%E3%82%A2%E3%81%94%E3%81%A8%E3%81%AE%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 h_01HJ369QB8SRN61ABBZ51TKFX2=%E5%8D%98%E4%B8%80%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2-vs-%E3%82%B9%E3%83%88%E3%82%A2%E3%81%94%E3%81%A8%E3%81%AE%E7%AE%A1%E7%90%86%E7%94%BB%E9%9D%A2 reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=%E8%A8%AD%E5%AE%9A%E3%81%AB%E5%BF%85%E8%A6%81%E3%81%AA%E3%82%BF%E3%82%B9%E3%82%AF h_01HJ369QB8NPE8FAHR42D2YN0K=%E8%A8%AD%E5%AE%9A%E3%81%AB%E5%BF%85%E8%A6%81%E3%81%AA%E3%82%BF%E3%82%B9%E3%82%AF before-you-begin=%E5%A7%8B%E3%82%81%E3%82%8B%E5%89%8D%E3%81%AB h_01JD2DEXW74MFE44FM3S0JCK5Q=%E5%A7%8B%E3%82%81%E3%82%8B%E5%89%8D%E3%81%AB tasks=%E3%82%BF%E3%82%B9%E3%82%AF h_01JD2DFF2K0APZ98JV1X09ZB33=%E3%82%BF%E3%82%B9%E3%82%AF procedures=%E6%89%8B%E9%A0%86 h_01HJ369QB990HH38TRQESQVFWN=%E6%89%8B%E9%A0%86 single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation h_01HJ369QB9V3W9R3EB6SJSNBED=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links h_01HJ369QB9H3J6E892X4V15AYJ=single-dashboard-attribution-links dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation h_01HJ369QB9SP4DHZM5JB0RKEWG=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app h_01HJ369QB9X58DVBTWVWD0GCAV=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options h_01HJ369QB97FN9BJKD9WRW99YG=testing-both-dashboard-options nonorganic-installs=%E9%9D%9E%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HJ369QB93A3ZZFAF0JAEXFRR=%E9%9D%9E%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB organic-installs=%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB h_01HJ369QB9SA05Y8VES8DD1FY4=%E3%82%AA%E3%83%BC%E3%82%AC%E3%83%8B%E3%83%83%E3%82%AF%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB expected-results=%E6%9C%9F%E5%BE%85%E3%81%95%E3%82%8C%E3%82%8B%E7%B5%90%E6%9E%9C h_01HJ369QBAJADS4SMSDPKK9RHW=%E6%9C%9F%E5%BE%85%E3%81%95%E3%82%8C%E3%82%8B%E7%B5%90%E6%9E%9C additional-features=%E8%BF%BD%E5%8A%A0%E6%A9%9F%E8%83%BD h_01HJ369QBAQ49ACSG3VEGSH7D4=%E8%BF%BD%E5%8A%A0%E6%A9%9F%E8%83%BD h_01HJ369QBA1XVMZD4G019T2S9W=driving-users-to-the-amazon-app-store-from-facebook referrer-implementation%E2%80%94thirdparty-android-app-stores=referrer-implementation-thirdparty-android-app-stores h_01HJ369QBA4D0SG9MQE6MXB0DH=referrer-implementation-thirdparty-android-app-stores troubleshooting=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 01JBKV47A5YJXKYHWA7H8NQAAF=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0 installs-attributed-to-the-default-app=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC h_01HJ369QBANRCTCFKTGK8BTQEC=%E3%83%87%E3%83%95%E3%82%A9%E3%83%AB%E3%83%88%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%88%E6%B8%AC traits-and-limitations=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90 h_01HJ369QBAJA87QJNTYNWYX82N=%E7%89%B9%E6%80%A7%E3%81%A8%E5%88%B6%E9%99%90" />

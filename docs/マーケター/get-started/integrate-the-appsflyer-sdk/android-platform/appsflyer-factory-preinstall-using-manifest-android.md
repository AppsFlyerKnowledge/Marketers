---
title: AppsFlyerによる工場出荷前のプリインストール計測：マニフェストの使用（Android）
metadata:
  keywords:
    - Android
    - Pre-Install
    - Attribution
    - Metrics
    - Advertisers
    - Agencies
    - af_pre_install_name
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2014-10-13T11:14:04Z'
  edited_at: '2026-10-28T09:10:56Z'
  id: 207032166
  locale: ja
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ja/articles/207032166
---
> **概要：** 工場出荷前に端末へインストールされたアプリのインストールを、端末メーカーにアトリビューションします。**注意**：<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#preload-campaigns">その他のプリロードアトリビューション方式</Anchor>も参照してください。

![pre-install-intro-breakdown.png](https://files.readme.io/6f7476f414d3d7ff9428bbf70617f6ac71ffbc27b4c934bcbb6e0c33f870a923-52396539342865.png)

<div id="introduction" />

## はじめに

<div id="what-is-a-pre-install-campaign" />

### プリインストールキャンペーンとは

プリインストールキャンペーンでは、オンラインキャンペーンを実施せずに、多くのユーザーにアプローチできます。

アプリの所有者は、端末メーカーに**工場出荷前の端末へアプリをプリインストールするよう依頼できます**。

アプリの所有者に代わってさまざまなメーカーと連携する、サードパーティのメディアソースと協力して実施することもできます。

<div id="important" />

> 🚧 **重要！**
>
> AppsFlyerは、アプリが初めて起動された時点でインストールをカウントします。そのため、表示されるプリインストール数は、アプリを起動したユーザー数です。アプリがプリインストールされた端末の台数ではありません。

<div id="benefits-of-recording-installs-from-pre-install-campaigns" />

### プリインストールキャンペーンによるインストールを記録するメリット

プリインストールキャンペーンをアトリビューションすると、次の項目を計測できます。

* プリインストールされたアプリを起動したユーザー数
* 各メーカーが獲得したアプリユーザー数
* 各ユーザーのLTV。これにより、価値の高いユーザーを獲得しているメーカーを判断できます。

<div id="how-can-i-measure-pre-install-campaigns" />

### プリインストールキャンペーンの計測方法

プリインストールキャンペーンの計測には、4つの方式があります。詳しくは、この記事の[設定セクション](/docs/appsflyer-factory-preinstall-using-manifest-android#設定)を参照してください。

<div id="viewing-pre-install-data" />

### プリインストールデータの確認

プリインストールは、他のインストールイベントと同様に、アトリビューションされたメディアソースのデータとしてAppsFlyerダッシュボードに表示されます。ただし、キャンペーン名は常に**Pre-install**になります。

<div id="note" />

> 📘 **注意**
>
> [SDK API方式](/docs/appsflyer-factory-preinstall-using-manifest-android#sdk-api-method)では、プリインストールのキャンペーン名を個別に指定できます。

<div id="note-1" />

> 📘 **注意**
>
> 2022年5月24日以降、次のように表示されます。
>
> * 工場出荷前のプリインストールキャンペーンのMatch\_typeは、ローデータレポートで`preload_conf`と表示されます。
> * AppsFlyerのダッシュボードには、プリロードにつながったアドネットワークと、アプリの初回起動に貢献したアドネットワークが表示されます。詳しくは、<Anchor target="_blank" href="/marketers/ja/docs/appsflyer-attribution-model#preload-campaigns">プリロードキャンペーン</Anchor>を参照してください。

<div id="setup" />

## 設定

プリインストールキャンペーンを計測する方式を、以下から選択してください。

| 方式名 | 複数のAPKが必要か | プリインストールへのアトリビューションを保証するか | メディアソースまたはメーカー側での作業が必要か |
| --- | --- | --- | --- |
| システムプロパティ | いいえ | はい | はい |
| SDK API | はい | いいえ | いいえ |
| マニフェストファイルに媒体名を指定 | はい | いいえ | いいえ |
| 設定ファイルのパスを指定 | いいえ | いいえ | はい |

<div id="system-properties-method-recommended" />

<Accordion title="システムプロパティ方式（推奨）">

SDKバージョン`V4.0+`を使用してください。

この方式は最も確実性が高いため、推奨されています。ただし、以後のすべてのアプリインストールは、常にプリインストールのメディアソースにアトリビューションされる点に注意してください。これは、新規インストールか再インストールかを問いません。 0>

システムプロパティ方式では、開発者とメーカーの両方で作業が必要です。

<div id="developer" />

#### 開発者

メーカーまたはメディアソースにAPKを提供します。通常のAPKを提供してください。この方式では、別のAPKを用意する必要はありません。

`pre_install.appsflyer`という名前のファイルを作成します。ファイルに、次のキーと値のペアを追加します。

`<0>=<1>`

例：

`com.appsflyer.sampleapp=huawei`

**プリインストール用のパラメータを追加で指定するには、次のように設定します。**

**pre\_install.appsflyer**ファイルに、追加のパラメータをJSON形式で指定します。例：

```json
com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
```

<div id="important-1" />

> 🚧 **重要！**
>
> このオプションを使用する場合は、次の動作に注意してください。
>
> * ローデータでは、チャネルが「Pre-install」に設定されます。
> * JSONに`pid`パラメータがない場合、ローデータのメディアソースは「None」と表示されます。
> * JSONの設定に`c`パラメータがない場合、キャンペーン名は「Pre-install」に設定されます。
> * JSONの形式が正しくない場合、指定した文字列がメディアソース名として扱われます。

pre\_install.appsflyerファイルを作成したら、APKと一緒にメディアソースまたはメーカーに渡します。

<div id="manufacturer" />

#### メーカー

メーカーは、任意のパスに***pre\_install.appsflyer***ファイルを配置します。 **pre\_install.appsflyer**ファイルのアクセス権限を744に設定してください。

次に、メーカーはシステムプロパティファイルを編集し、***pre\_install.appsflyer***ファイルを参照するように設定します。この設定には、システムプロパティにキーと値のペアを追加する必要があります。

<div id="note-2" />

> 📘 **注意**
>
> この手順にはroot権限が必要です。プリインストール設定のテストにもroot権限が必要です。詳しくは、[テストのセクション](/docs/appsflyer-factory-preinstall-using-manifest-android#プリインストール設定のテスト)を参照してください。

**Androidのシステムプロパティへのキーと値のペアの追加：**

```bash
adb shell su
setprop ro.appsflyer.preinstall.path /data/pre_install.appsflyer
```

別の方法として、Androidのファイルシステムからシステムプロパティファイルを取得し、編集して戻すこともできます。

```bash
adb root
adb remount
adb pull /system/build.prop
echo ro.appsflyer.preinstall.path=/data/pre_install.appsflyer >> build.prop
adb push build.prop /system/build.prop
adb shell chmod 744 /system/build.prop
adb reboot
```

<div id="advantages" />

#### メリット

メディアソースやメーカーごとに、異なるAPKを管理する必要がありません。 Google Playで配信するアプリを変更してパスを追加する必要がありません。メーカーは任意のパスを使用できます。また、異なる端末で動作する複数のプリインストールアプリ間に依存関係はありません。

この方式では、プリインストールキャンペーンとメディアソースへのアトリビューションが保証されます。ユーザーが初回起動前にアプリを更新した場合や、広告をクリックした後にアプリをインストールした場合でも、プリインストールのメディアソースまたはメーカーにアトリビューションされます。

<div id="disadvantages" />

#### デメリット

メディアソースまたはメーカー側が、作業の一部を担う必要があります。開発者は、メーカーまたはメディアソースが必要な手順を実施したことを確認する必要があります。また、アプリ開発者にとっては、この方式のテストがやや難しい場合があります。

</Accordion>

<div id="sdk-api-method" />

<Accordion title="SDK API方式">

SDK API方式では、ネイティブのAPIを使用して、プリインストールのアトリビューション先となるメーカー名またはメディアソース名を指定できます。

この方式を使用するには、SDKを初期化する前に、AFApplicationクラスに次のメソッド呼び出しを追加します。

`setPreinstallAttribution(String mediaSource, String campaign, String siteId)`

<div id="when-working-with-a-media-source" />

#### メディアソースと連携する場合

```java
AppsFlyerLib.getInstance().setPreinstallAttribution("MEDIA_SOURCE_NAME", "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

<div id="when-working-with-a-manufacturer" />

#### メーカーと連携する場合

```java
AppsFlyerLib.getInstance().setPreinstallAttribution(android.os.Build.MANUFACTURER, "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

<div id="note-3" />

> 📘 **注意**
>
> * メディアソースのパラメータは必須です。
> * `android.os.Build.MANUFACTURER`プロパティには、OSで設定されたメーカー名が格納されています。このプロパティを使用しても、同じメーカーのすべての端末で、メーカー名が同じ形式で取得できるとは限りません。このプロパティに、想定どおりのメーカー名が格納されていることを確認してください。
> * `campaign`と`siteId`パラメータの値は任意ですが、`setPreinstallAttribution`メソッドにはこれらの引数を渡す必要があります。 `campaign`と`siteId`を指定しない場合は、両方にnullを渡してください。

<div id="advantages-1" />

#### メリット

SDK API方式では、メーカー名をプログラムで取得できます。メーカーを問わず、SDKのメソッドで端末から直接メーカー名を取得できます。そのため、連携するすべてのメーカーに対して、1つのAPKを管理すれば対応できます。

`setPreinstallAttribution`メソッドでは、キャンペーン名を指定できます。すべてを「Pre-install」キャンペーンとして扱う代わりに、メーカーやメディアソースごとにキャンペーンを分けることができます。

<div id="disadvantages-1" />

#### デメリット

メーカーと直接連携する場合は、メーカー向けとGoogle Play向けの2種類のAPKを管理する必要があります。いずれの場合も、複数のAPKが必要です。

アプリの所有者に代わってメーカーとやり取りする複数のメディアソースと連携する場合は、メディアソースごとに個別のAPKを管理する必要があります。

次の場合、プリインストールのメディアソースにインストールがアトリビューションされないことがあります。

* 新しい端末のユーザーが、プリインストールされたアプリを一度も起動せずにGoogle Playから直接更新した場合、インストールはオーガニックとみなされます。
* 新しい端末のユーザーが、広告をクリックした後にGoogle Playからアプリを更新した場合、インストールは広告を配信したメディアソースにアトリビューションされます。

<div id="tip" />

> 👍 **ヒント**
>
> 上記のケースでもプリインストールとしてカウントされるよう、アプリに判定処理を実装できます。 Google Play向けのAPKとプリインストール向けのAPKの両方に、この処理を実装してください。
>
> **例：**
>
> * 特定のメーカーと機種の端末に、アプリがプリインストールされていることが分かっているとします。これらの端末は、特定のキャリアも使用しています。
> * アプリの起動時に、これらの条件を確認できます。条件を満たしていれば、インストールはプリインストールとして記録されます。 Google Play向けのAPKにもこの処理があるため、ユーザーが初回起動前にアプリを更新した場合でも、プリインストールとして記録されます。

</Accordion>

<div id="name-in-manifest-file-method" />

<Accordion title="マニフェストファイルに媒体名を指定する方式">

この方式では、アプリのマニフェストファイルにメタデータタグを追加します。連携するメディアソースまたはメーカーごとに、この手順を行う必要があります。

applicationの閉じタグの前に、メタデータタグを追加します。

```html Markup
...
    <0/>
  1>
2>
```

アプリの初回起動時に、AppsFlyer SDKがマニフェストファイルのメタデータタグを検出し、その内容に応じてインストールをアトリビューションします。

<div id="advantages-2" />

#### メリット

マニフェストファイルに媒体名を指定する方式は、プリインストールキャンペーンを簡単にアトリビューションできる方式です。マニフェストに追加するタグは1つだけです。また、キャンペーンを計測するために、メディアソースやメーカー側で作業を行う必要はありません。

<div id="disadvantages-2" />

#### デメリット

メタデータタグにメディアソース名またはメーカー名を指定するため、メディアソースやメーカーごとに異なるAPKを管理する必要があります。

次の場合、プリインストールのメディアソースにインストールがアトリビューションされないことがあります。

* 新しい端末のユーザーが、プリインストールされたアプリを一度も起動せずにGoogle Playから直接更新した場合、インストールはオーガニックとみなされます。
* 新しい端末のユーザーが、広告をクリックした後にGoogle Playからアプリをインストールした場合、インストールは広告を配信したメディアソースにアトリビューションされます。

</Accordion>

<div id="pathway-method" />

<Accordion title="設定ファイルのパスを指定する方式">

<div id="note-4" />

> 📘 **注意**
>
> SDKバージョン4.5.0以降でサポートされています。

この方式では、開発者とメーカーの両方で作業が必要です。

<div id="developer-1" />

#### 開発者

この方式では、メディアソース名またはメーカー名が記載されたファイルのパスを指定できます。次の3つの手順を行ってください。

1. キーと値のペアを記載したファイルを作成します。ファイル名は***pre\_install.appsflyer***にします。ファイルに、`<PACKAGE_NAME>`=`<MEDIA_SOURCE>`の形式でキーと値のペアを指定します。例：`com.appsflyer.sampleapp=my_media_source`。  

   <div id="passing-additional-pre-install-parameters" />

   #### プリインストール用の追加パラメータの指定

   ファイル内に、プリインストール用の追加パラメータをJSON形式で指定できます。例えば、**pre\_install.appsflyer**ファイルに次のキーと値のペアを追加できます。

   ```json
   com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
   ```

   <div id="important-2" />

   > 🚧 **重要！**
   >
   > このオプションを使用する場合は、次の動作に注意してください。
   >
   > 1. af\_channelに「Pre-install」が設定されます。
   > 2. JSONにpidがない場合、メディアソースは「None」と表示されます。
   > 3. JSONの設定にcがない場合、キャンペーン名は「Pre-install」に設定されます。
   > 4. JSONの形式が正しくない場合、指定した文字列がメディアソース名として扱われます。


   pre\_install.appsflyerファイルを作成したら、APKと一緒にメディアソースまたはメーカーに渡します。
2. メディアソースまたはメーカーと相談し、ファイルの配置先のパスを決めます。推奨するパスは「/data/local/tmp/pre\_install.appsflyer」です。
3. 配置先が決まったら、そのパスをマニフェストファイルに指定します。 applicationの閉じタグの前に、次のコードを追加します。  

   ```html Markup
   <0/>
   ```

<div id="manufacturer-1" />

#### メーカー

メーカーは、合意したパスにファイルを配置する必要があります。 pre\_install.appsflyerファイルのアクセス権限を744に設定してください。

アプリが起動すると、SDKはマニフェストファイル内の指定パスを確認し、そのパスでファイルを探します。ファイルが見つかると、記載されているメディアソースにインストールをアトリビューションします。

<div id="advantages-3" />

#### メリット

AppsFlyerは、次の2つのデフォルトのパスで**pre\_install.appsflyer**ファイルを探します。

```bash
/data/local/tmp/pre_install.appsflyer
または
/etc/pre_install.appsflyer
```

メーカーによっては、デフォルト以外のパスにファイルを配置したい場合があります。その場合は、マニフェストファイルにデフォルト以外のパスを指定できます。

<div id="important-3" />

> 🚧 **重要！**
>
> デフォルト以外のパスを使用するには、SDKバージョン4.8以降が必要です。
>
> デフォルト以外のパスも使用できますが、代わりに[システムプロパティ方式](/docs/appsflyer-factory-preinstall-using-manifest-android#system-properties-method-recommended)の実装を推奨します。

<div id="disadvantages-3" />

#### デメリット

メディアソースやメーカーごとに、個別の***pre\_install.appsflyer***ファイルを管理する必要があります。

メーカーが***pre\_install.appsflyer***ファイルをデフォルト以外のパスに配置したい場合があります。その場合は、デフォルト以外のパスごとに個別のAPKを管理する必要があります。

**デフォルト以外のパス**を使用すると、次の場合にプリインストールのメディアソースにインストールがアトリビューションされないことがあります。

* 新しい端末のユーザーが、プリインストールされたアプリを一度も起動せずにGoogle Playから直接更新した場合、インストールはオーガニックとみなされます。
* 新しい端末のユーザーが、広告をクリックした後にGoogle Playからアプリをインストールした場合、インストールは広告を配信したメディアソースにアトリビューションされます。

</Accordion>

<div id="testing-pre-install-configuration" />

## プリインストール設定のテスト

このセクションでは、プリインストール設定をテストして確認する方法を説明します。

<div id="important-4" />

> 🚧 **重要！**
>
> テストを開始する前に、<Anchor target="_blank" href="/marketers/ja/docs/registering-test-devices">テストに使用するデバイスを許可リストに登録</Anchor>してください。
> また、AFApplicationクラスでデバッグログをtrueに設定してください。
>
> ```java
> AppsFlyerLib.getInstance().setDebugLog(true);
> ```

<div id="verifying-the-configuration-in-the-app" />

<Accordion title="アプリでの設定の確認">

<div id="tip-1" />

> 👍 **ヒント**
>
> キャッシュに関する問題を避け、適切にテストするため、ビルド前にプロジェクトをクリーンアップすることを推奨します。 Android Studioのコンテキストメニューで<strong><em>［Build］</em></strong>をクリックし、<strong><em>［Clean Project］</em></strong>を選択します。

Android Studioでアプリをビルドし、テストデバイスにインストールします。アプリが起動したら、Android StudioでLogcatを開き、「AppsFlyer」でフィルタリングします。アトリビューションされたインストールの詳細が表示されます。以下のスクリーンショットを参照してください。

![pre_install_logcat.png](https://files.readme.io/bc2186117491c79699e08210fd58460f51ae102b7167735d8017fa08e394fd12-52396508410257.png)

![pre_install_logcat_2.png](https://files.readme.io/08e09b0a71e91840c98640d4da1b26d9e9a0c857c55607442bcdd324a10d3003-52396539348113.png)

</Accordion>

<div id="verifying-the-configuration-in-the-appsflyer-dashboard" />

<Accordion title="AppsFlyerダッシュボードでの設定の確認">

設定が成功すると、メーカーまたはメディアソースにアトリビューションされたノンオーガニックインストールがダッシュボードに表示されます。このインストールイベントは、「Pre-install」キャンペーンにも表示されます。

AppsFlyerアカウントにアクセスし、テスト対象のアプリのダッシュボードを開きます。次の手順に従ってください。

1. オーバービューダッシュボードで、メディアソースのフィルターから対象のメディアソースを選択します。  

   ![choose_media_source.png](https://files.readme.io/f7fc3f24540cdeb8914a64b19fd0c6450827a63eaed5b9eb6c77470e4a129412-52396508413073.png)
2. <strong><em>［キャンペーン別内訳］</em></strong>グラフでは、「my media source」にアトリビューションされたインストールが、Pre-installキャンペーンによるものであることを確認できます。  

    [![](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)  
   ***集計パフォーマンスレポート***でも、インストールが正しくアトリビューションされているか確認できます。このレポートでは、メディアソースとキャンペーンを確認できます。以下のスクリーンショットでは、メディアソースが「My Media Source」、キャンペーンがPre-installになっています。  

    [![](https://files.readme.io/6eee128de5ea268540fd4672b27dd6e6e7b686d77215096184f2570fd641c6f1-52396508413969.png)](https://files.readme.io/6eee128de5ea268540fd4672b27dd6e6e7b686d77215096184f2570fd641c6f1-52396508413969.png)
3. プリインストールキャンペーンで連携するすべてのメーカーまたはメディアソースについて、この手順を繰り返します。

</Accordion>

<div id="special-cases" />

## 特殊なケース

<div id="multiple-preinstall-apps-on-the-same-device" />

<Accordion title="同じ端末に複数のアプリがプリインストールされている場合">

同じ端末にインストールされた複数のアプリでキャンペーンを実施している場合、4つの方式のいずれでもアトリビューションを計測できます。

* マニフェストファイルに媒体名を指定する方式：各アプリのManifest.xmlに、メディアソースまたはメーカーを指定します。
* SDK API方式：各アプリで、プリインストール用のSDK APIメソッドにメディアソースまたはメーカーを指定します。
* システムプロパティ方式または設定ファイルのパスを指定する方式：***pre\_install.appsflyer***ファイルに、各アプリと対応するメディアソースを指定できます。各アプリの情報は、ファイル内で1行ずつ記載してください。例：

  ```bash
  com.appsflyer.tester=<0>market_name0>
  com.newapp.newapp=<0>market_name0>
  com.game.king=<0>market_name0>
  ```

</Accordion>

<div id="sending-install-postbacks" />

<Accordion title="インストールポストバックの送信">

連携するメディアソースまたはメーカーが<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#your-integrated-partners">AppsFlyerパートナー</Anchor>であれば、インストールのポストバックを有効にできます。

その場合は、メディアソース名が、AppsFlyerで設定されているメディアソースのpidと一致していることを確認してください。

例えば、market\_nameと連携している場合、そのpidはmarket\_name\_intです。 pidは、<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#クリックスルー計測">連携済みパートナーのアトリビューションリンク</Anchor>で確認できます。

</Accordion>

<div id="agencies" />

<Accordion title="代理店">

現在、プリインストールを代理店にアトリビューションすることはできません。

プリインストールデータにaf\_prt（代理店名のパラメータ）が含まれ、ユーザーがプリインストールされたアプリを起動した場合：

* ユーザーは、代理店が使用するメディアソース（pid=）にアトリビューションされます。
* 広告主は、ユーザーレベルのすべてのデータにアクセスできます。
* ユーザーは、代理店にはアトリビューションされません。
* 代理店は、ユーザーレベルのデータにアクセスできません。

</Accordion>

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB h_01J421581P06FTM7B3XG2GYB2P=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB what-is-a-preinstall-campaign=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%A8%E3%81%AF h_01J421581P6GYK60D5JQ9PK93N=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%A8%E3%81%AF h_01J421581PBQQ5AS3S4JPX52CF=%E9%87%8D%E8%A6%81 benefits-of-recording-installs-from-preinstall-campaigns=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AB%E3%82%88%E3%82%8B%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%92%E8%A8%98%E9%8C%B2%E3%81%99%E3%82%8B%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01J421581P5MS4X9BHSJ3TTWBF=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AB%E3%82%88%E3%82%8B%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%92%E8%A8%98%E9%8C%B2%E3%81%99%E3%82%8B%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 how-can-i-measure-preinstall-campaigns=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC%E6%96%B9%E6%B3%95 h_01J421581PEZZW2R244ZX9HX0R=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E8%A8%88%E6%B8%AC%E6%96%B9%E6%B3%95 viewing-preinstall-data=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01J421581PS1CEPK3NN7AZ0ZDE=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%A2%BA%E8%AA%8D h_01J421581PDE1CEXRS6BYTDV35=%E6%B3%A8%E6%84%8F h_01J421581PKQTX47GC62K4AB9A=%E6%B3%A8%E6%84%8F-1 setup=%E8%A8%AD%E5%AE%9A h_01J421581P28NEVB44R3XTPY75=%E8%A8%AD%E5%AE%9A h_01J421581QNSQ7W3VYFDVZ1423=system-properties-method-recommended developer=%E9%96%8B%E7%99%BA%E8%80%85 h_01J421581Q8ZAPZS12PEG4VW3N=%E9%96%8B%E7%99%BA%E8%80%85 h_01J421581QYRNXCP16GY8CJTKT=%E9%87%8D%E8%A6%81-1 manufacturer=%E3%83%A1%E3%83%BC%E3%82%AB%E3%83%BC h_01J421581QF6Y6MY28N5MR5BTM=%E3%83%A1%E3%83%BC%E3%82%AB%E3%83%BC h_01J421581QBFMVT3KPCPPFRX42=%E6%B3%A8%E6%84%8F-2 advantages=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01J421581QEPAC0WZK93HH3QYP=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 disadvantages=%E3%83%87%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01J421581QCG3HARVZVECMHQ1K=%E3%83%87%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88 h_01J421581QQ3VJSSQ06DKZQ0BQ=sdk-api-method when-working-with-a-media-source=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A8%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 h_01J421581Q6F1AD0SYXEEJB8FB=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%A8%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 when-working-with-a-manufacturer=%E3%83%A1%E3%83%BC%E3%82%AB%E3%83%BC%E3%81%A8%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 h_01J421581Q3YSNH7KXQXET7FD4=%E3%83%A1%E3%83%BC%E3%82%AB%E3%83%BC%E3%81%A8%E9%80%A3%E6%90%BA%E3%81%99%E3%82%8B%E5%A0%B4%E5%90%88 h_01J421581QRYRWY2WJKCBHQBFG=%E6%B3%A8%E6%84%8F-3 advantages::d999b734=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-1 h_01J421581QWHP73CA7P13WAQ7Q=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-1 disadvantages::92772f7d=%E3%83%87%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-1 h_01J421581QRRFBJWZB5Z6M08BE=%E3%83%87%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-1 h_01J421581QF11R7ZXAXRP2YQYR=%E3%83%92%E3%83%B3%E3%83%88 h_01J421581QJ2J54HJFTXF3G5S0=name-in-manifest-file-method advantages::3f0b06fb=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-2 h_01J421581Q8WFYYFQJ45KPWZWP=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-2 disadvantages::919cb3e3=%E3%83%87%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-2 h_01J421581QYC02EKB5P0FN5G3F=%E3%83%87%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-2 h_01J421581QNFT2E2P3A6MR3BB5=pathway-method h_01J421581QF43JW6A0B48SK9AE=%E6%B3%A8%E6%84%8F-4 developer::7c51f631=%E9%96%8B%E7%99%BA%E8%80%85-1 h_01J421581QB4TH9DMA2ANHG7RD=%E9%96%8B%E7%99%BA%E8%80%85-1 passing-additional-preinstall-parameters=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E7%94%A8%E3%81%AE%E8%BF%BD%E5%8A%A0%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E6%8C%87%E5%AE%9A h_01J421581Q45AEN4GEM5ZKPYRN=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E7%94%A8%E3%81%AE%E8%BF%BD%E5%8A%A0%E3%83%91%E3%83%A9%E3%83%A1%E3%83%BC%E3%82%BF%E3%81%AE%E6%8C%87%E5%AE%9A h_01J421581Q3MMTKPP3E8SZD13F=%E9%87%8D%E8%A6%81-2 manufacturer::56d9649d=%E3%83%A1%E3%83%BC%E3%82%AB%E3%83%BC-1 h_01J421581Q16AVHRCTHME67VHQ=%E3%83%A1%E3%83%BC%E3%82%AB%E3%83%BC-1 advantages::1fb76031=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-3 h_01J421581QTRY13FVNQRMG0H2B=%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-3 h_01J421581Q0P5VQJHQ9X3VRW8N=%E9%87%8D%E8%A6%81-3 disadvantages::c9cae863=%E3%83%87%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-3 h_01J421581QSNNCHPC2VSF48FT3=%E3%83%87%E3%83%A1%E3%83%AA%E3%83%83%E3%83%88-3 testing-preinstall-configuration=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%AD%E5%AE%9A%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01J421581QYHRHF119J4YBZD23=%E3%83%97%E3%83%AA%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E8%A8%AD%E5%AE%9A%E3%81%AE%E3%83%86%E3%82%B9%E3%83%88 h_01J421581QW0XKZ635A194W80J=%E9%87%8D%E8%A6%81-4 h_01J421581QPXQDFX5G11B7GSNA=verifying-the-configuration-in-the-app h_01J421581QSZPZVZ6GGQST5FWS=%E3%83%92%E3%83%B3%E3%83%88-1 h_01J421581Q7PGHJ2HBX1ZDNJS6=verifying-the-configuration-in-the-appsflyer-dashboard special-cases=%E7%89%B9%E6%AE%8A%E3%81%AA%E3%82%B1%E3%83%BC%E3%82%B9 h_01J421581Q624TH08PX24B1P3X=%E7%89%B9%E6%AE%8A%E3%81%AA%E3%82%B1%E3%83%BC%E3%82%B9 h_01J421581QQHB8624SS6FSSA6D=multiple-preinstall-apps-on-the-same-device h_01J421581Q86AB5GTM91ARYJ23=sending-install-postbacks h_01J421581RD2WQ6SPES729GJEP=agencies" />

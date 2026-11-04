---
title: テストデバイスの登録
metadata:
  keywords:
    - whitelisting
    - Testing
    - device
    - Advertisers
    - Agencies
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
  created_at: '2015-03-10T08:19:35Z'
  edited_at: '2026-10-28T09:09:35Z'
  id: 207031996
  locale: ja
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ja/articles/207031996
---
> **At a glance:** アトリビューションをテストする際は、各インストールが新規インストールとして記録されるよう、テストデバイスを登録してください。テストデバイスを登録すると、インストールが再インストールとして記録されるのを防げます。

<div id="why-register-a-test-device" />

## テストデバイスを登録する理由

アトリビューションのテストでは、リアトリビューション期間の制限により、90日間に1回しかインストールのアトリビューションが行われません。そのため、同じデバイスでインストールのアトリビューションを繰り返しテストしても、記録されません。デバイスをテストデバイスとして登録すると、そのデバイスで繰り返し行ったインストールが、再インストールとして記録されるのを防げます。

<div id="methods-for-registering-a-test-device" />

## テストデバイスの登録方法

テストデバイスの登録では、デバイスのOS（Android、iOS、Windows）を選択し、デバイス識別子を追加します。

次のいずれかの方法で登録できます。

* [My Device ID by AppsFlyerアプリをダウンロードしてインストール：](#register-a-device-using-the-appsflyer-device-id-app-admin-only)テストデバイスにアプリをインストールすると、デバイスを自動的に登録し、デバイスIDの詳細をAppsFlyerアカウントに共有できます。デバイスは、<strong>［テストデバイス］</strong>ページの一覧に自動的に表示されます。

> 📘 **Note**
>
> * iOS 14以降のテストデバイスでこの登録方法を利用できるのは、アプリにApp Tracking Transparency（ATT）が実装されており、トラッキングを許可したユーザーとしてテストする場合のみです。それ以外の場合は、手動で登録してください。
> * My Device ID by AppsFlyerアプリは2要素認証（2FA）に対応していないため、AppsFlyerアカウントで2要素認証を有効にしている場合、アプリからテストデバイスを登録することはできません。この場合は、手動でテストデバイスを登録してください。

* [テストデバイスを手動で追加：](#register-a-device-manually)アカウントのすべてのユーザーは、<strong>［テストデバイス］</strong>ページにデバイス識別子を追加して、直接登録できます。

次の点に注意してください。

* 登録済みのテストデバイスは、アカウント内のすべてのアプリで利用できます。
* アドネットワークは、広告主にデバイスの追加を依頼する必要があります。代理店は、自分でデバイスを追加できます。

<Accordion title="対応するデバイス識別子">

対応するデバイス識別子は、次のとおりです。

* **Android：** AID（GAIDまたはOAID）、IMEI、Android ID

> 📘 **Note**
>
> テストデバイスを登録する際、IMEIまたはAndroid IDを追加するのは、アプリがこれらの識別子を取得・使用している場合のみにしてください。

* **iOS：** IDFA、IDFV
* **Windows Phone：** Windows広告ID

</Accordion>

<div id="windows::6c6af14b" />

<div id="ios::80f176b3" />

<div id="android::db8cc168" />

<div id="windows" />

<div id="ios" />

<div id="managing-test-device-registration" />

## テストデバイスの登録管理

<Accordion title="AppsFlyerのデバイスID確認アプリを使った登録">

**AppsFlyerのデバイスID確認アプリをダウンロードする方法：**

1. QRコード（Google Playストア）または以下のリンクを使って、アプリをダウンロードしてインストールします。

   <div id="android" />

   <Accordion title="Android">

   [<Image alt="kb_qr_code.png" src="https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png" width="50%" />](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

   **リンク：** [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en)、[Google Play以外のアプリストア](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

   </Accordion>

   <Accordion title="Details">

   &lt;0>iOS0>

   [<Image alt="kb_qr_code.png" src="https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png" width="50%" />](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

   </Accordion>

   <Accordion title="Details">

   &lt;0>Windows0>

   [<Image alt="" src="https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png" width="50.91%" />](https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png)

   </Accordion>

2. iOS 14.5以降のデバイスでIDFAの取得を許可する場合は、ATTの確認画面で<strong>［許可］</strong>をタップします。 [<Image alt="" src="https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png" width="50%" />](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)
3. Android／iOS／Windowsの画面で<strong>［登録（Register）］</strong>をタップして、デバイスを登録します。

   <Accordion title="Details">

   &lt;0>Android0>

   [<Image alt="" src="https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png" width="50%" />](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)

   </Accordion>

   <Accordion title="Details">

   &lt;0>iOS0>

   [<Image alt="" src="https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png" width="50%" />](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)

   </Accordion>

   <Accordion title="Details">

   &lt;0>Windows0>

   [<Image alt="" src="https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg" width="50%" />](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)

   </Accordion>

4. AppsFlyerのログイン情報を入力します。これでデバイスの登録が完了します。
5. <strong>［共有（Share）］</strong>をタップして、デバイスIDの情報を共有します。

</Accordion>

<Accordion title="デバイスの手動登録">

アカウントのユーザーは、次の手順でデバイスを手動登録できます。

1. AppsFlyerのサイドメニューから、**［設定］**＞<strong>［テストデバイス］</strong>を選択します。
2. <strong>［テストデバイス］</strong>を選択します。
3. <strong>［＋デバイスを追加］</strong>をクリックします。

   [<Image alt="" src="https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png" width="50%" />](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)
4. 次の項目を設定します。
   * **名前（英字のみ）：** デバイスを一意に識別できる名前を入力します。
   * **OS：** OSを選択します。
   * **デバイスIDの種類：** デバイス識別子を選択します。
   * **デバイスID：** OSに応じたデバイスIDを入力します。

     <div id="ios::41efa11e" />

     <Accordion title="iOS">

     IDFAまたはIDFVの取得方法：

     * **IDFA：** IDFAを取得するには、テストデバイスにAppsFlyerのデバイスID確認アプリをインストールします。方法については、前述のAppsFlyerのデバイスID確認アプリを使った[デバイスの追加](#register-a-device-manually)（管理者のみ）を参照してください。
     * **IDFV：** IDFVを取得するには、テストデバイスにIDFVテストツールアプリをインストールするよう、開発者に依頼します。インストール後にツールアプリを起動すると、IDFVが表示されます。**注意：** 開発者がXcodeで事前準備を済ませてからでないと、テストツールはインストールできません。

     IDFAとIDFVの使い分けについては、[iOSテストデバイスの登録](#iosテストデバイスの登録)を参照してください。

     </Accordion>

     <div id="android::7db075c7" />

     <Accordion title="Android">

     AppsFlyerのデバイスID確認アプリを使用するか、デバイスの電話アプリで次のコードを入力して、識別子を取得します。

     | 識別子 | 取得方法 | Google Play | その他 |
     | --- | --- | --- | --- |
     | AID（GAIDまたはOAID） | [AppsFlyerのデバイスID確認アプリ](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid)を使用します。 | 必須 |  |
     | IMEI | *#06#* | 対象外 | 開発者が<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">setCollectImei</Anchor>を使ってIDを取得していることを確認してください。 |
     | Android ID | *#*#8255#*#*（新しいデバイスでは動作しない場合があります） | 対象外 | 開発者が<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">setCollectAndroidID</Anchor>を使ってIDを取得していることを確認してください。 |

     </Accordion>

5. <strong>［保存］</strong>をクリックします。 登録済みデバイスの一覧に、デバイスが表示されます。 **注意**：デバイスはすぐに登録済みデバイスの一覧に表示されますが、システムへの登録が完了し、正しく動作するまでには数分かかる場合があります。

> 📘 **Note**
>
> **複数の識別子の追加**
>
> たとえば、同じデバイスにIDFAとIDFVの両方を登録するなど、テストデバイスに複数の識別子を追加したい場合があります。
>
> **識別子を追加するには、次の手順を実行します。**
>
> 1. <strong>［デバイスを追加］</strong>をクリックします。
> 2. 同じテストデバイス名を使い、2つ目の識別子を追加します。
> 3. <strong>［保存］</strong>をクリックします。

</Accordion>

<Accordion title="デバイスの登録解除">

アカウントごとに、最大200台のデバイスを登録できます。

**一覧からデバイスを削除するには、次の手順を実行します。**

1. AppsFlyerの右上にあるメールアドレスをクリックします。
2. <strong>［テストデバイス］</strong>を選択します。
3. 削除アイコンをクリックして、デバイスを削除します。

</Accordion>

<div id="registering-an-ios-test-device" />

## iOSテストデバイスの登録

以下のフローチャートは、iOSテストデバイスを登録する際の選択肢と手順を示しています。

[![](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)

iOSテストデバイスを登録する際は、次のいずれかを選択します。

<Accordion title="IDFAを使ったテストデバイスの登録">

<div id="when-to-use-idfa-for-test-device-registration" />

#### **IDFAでテストデバイスを登録するのは、どのような場合ですか？**

アプリにApp Tracking Transparency（ATT）が実装されており、トラッキングを許可したユーザーとしてテストする場合は、IDFAで登録できます。テスト対象のアプリを初めて起動する際、ATTの確認画面で必ず<strong>［許可］</strong>を選択してください。

<div id="how-to-register-your-test-device-with-an-idfa" />

#### **IDFAでテストデバイスを登録するには、どうすればよいですか？**

IDFAで登録する場合は、AppsFlyerのデバイスID確認アプリを使ってデバイスを登録します。

</Accordion>

<Accordion title="IDFVを使ったテストデバイスの登録">

<div id="when-to-use-idfv-for-test-device-registration" />

#### **IDFVでテストデバイスを登録するのは、どのような場合ですか？**

IDFAを取得できない場合は、IDFVを使用する必要があります。次の場合は、**IDFVの使用が必須**です。

* **ATTが実装されている**ものの、トラッキングを許可していないユーザーとしてテストしたい場合。アプリを初めて起動する際、ATTの確認画面で必ず<strong>［許可しない］</strong>を選択してください。
* **ATTが実装されていない**場合。

<div id="how-to-register-your-device-with-idfv" />

#### **IDFVでデバイスを登録する方法**

1. IDFVでテストデバイスを登録する前に、開発者がテストデバイスにIDFVテストツールアプリをインストールする必要があります。開発者向けの手順は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app">こちらの記事</Anchor>を案内してください。
2. 開発者がIDFVテストツールアプリをインストールした後、アプリを起動し、表示されたIDFVをコピーします。
3. そのIDFVを使って、[テストデバイスを手動で登録](#register-a-device-manually)します。

> 📘 **Note**
>
> **IDFVテストツールアプリをインストールする理由**
>
> * IDFVテストツールは、テストデバイスの登録に必要なIDFVを取得するために使用します。
> * テストデバイスに、同じ開発者アカウントの他のアプリがインストールされていない場合にも、このツールを使用します。この場合、iOSはアプリを再インストールするたびに、新しいベンダーIDを割り当てます。テストではアプリを再インストールすることが多いため、そのたびにiOSがIDFVをリセットします。**このツールアプリは、同じベンダーのアプリとして動作することで、テストデバイスでアプリを再インストールするたびに、iOSが新しいIDFVを生成するのを防ぎます。**

</Accordion>

<Accordion title="未登録のデバイスを使ったテスト">

IDFAでもIDFVでもテストデバイスを登録できない場合に限り、この方法を使用してください。この場合、アトリビューションには確率論的モデリングを使用します。テストデバイスでの各インストールは、新規インストールとして記録されます。次の条件のいずれかを満たす場合、この方法で、同じデバイスで繰り返し行うテストインストールを記録できます。

* AppsFlyerのiOS SDKがv6.8.0以前である。
* アプリの再インストール検知が無効になっている。公開済みアプリでは推奨しません。
* テスト用のアトリビューションリンクに`is_retargeting="true"`が含まれている。この場合、インストールはリアトリビューションとして記録され、リターゲティングのダッシュボードとローデータレポートで確認できます。
* iOSのみ：Protect360がクリックを不正と判定するのを防ぐため、テスト用のアトリビューションリンクにクエリパラメータ`pid="ios_testing"`を追加してください。

</Accordion>

<div data-zendesk-anchors="why-register-a-testing-device=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E7%90%86%E7%94%B1 01H7W9EA7RQDB69QS339XFHAFZ=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E7%90%86%E7%94%B1 methods-for-registering-a-testing-device=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E7%99%BB%E9%8C%B2%E6%96%B9%E6%B3%95 01H7W9EA7RRRJBFSXW3KY53R9K=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E7%99%BB%E9%8C%B2%E6%96%B9%E6%B3%95 managing-testingdevice-registration=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E7%99%BB%E9%8C%B2%E7%AE%A1%E7%90%86 01H7W9EA7R7SJVVQCST3WA6YBM=%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E7%99%BB%E9%8C%B2%E7%AE%A1%E7%90%86 01JHJKN5Z3562N4W2H543XPC7E=android 01JHJKDZK8084GMZ9QAZPHVBHQ=ios::41efa11e 01JHJKDZK9MTNXANVEHCM18EBM=android::7db075c7 registering-an-ios-testing-device=ios%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E7%99%BB%E9%8C%B2 h_01H6S2AKDH181MBDFGPBP1BQPV=ios%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%AE%E7%99%BB%E9%8C%B2 when-to-use-idfa-for-testing-device-registration=idfa%E3%81%A7%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E3%81%AE%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E5%A0%B4%E5%90%88%E3%81%A7%E3%81%99%E3%81%8B 01H7W9EA7SRD5V5134H2BRZ2AF=idfa%E3%81%A7%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E3%81%AE%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E5%A0%B4%E5%90%88%E3%81%A7%E3%81%99%E3%81%8B how-to-register-your-testing-device-with-an-idfa=idfa%E3%81%A7%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF%E3%81%A9%E3%81%86%E3%81%99%E3%82%8C%E3%81%B0%E3%82%88%E3%81%84%E3%81%A7%E3%81%99%E3%81%8B 01H7W9EA7SBBCAP3Y24FFCCGJW=idfa%E3%81%A7%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E3%81%AB%E3%81%AF%E3%81%A9%E3%81%86%E3%81%99%E3%82%8C%E3%81%B0%E3%82%88%E3%81%84%E3%81%A7%E3%81%99%E3%81%8B when-to-use-idfv-for-testing-device-registration=idfv%E3%81%A7%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E3%81%AE%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E5%A0%B4%E5%90%88%E3%81%A7%E3%81%99%E3%81%8B 01H7W9EA7S3103TSHSH4XHTP1R=idfv%E3%81%A7%E3%83%86%E3%82%B9%E3%83%88%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E3%81%AE%E3%81%AF%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E5%A0%B4%E5%90%88%E3%81%A7%E3%81%99%E3%81%8B how-to-register-your-device-with-idfv=idfv%E3%81%A7%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 01H7W9EA7SGTDQCRVJKKRH0EVT=idfv%E3%81%A7%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%99%BB%E9%8C%B2%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95" />

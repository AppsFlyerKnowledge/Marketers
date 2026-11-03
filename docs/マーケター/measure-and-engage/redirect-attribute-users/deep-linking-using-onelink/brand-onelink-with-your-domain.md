---
title: ブランドドメイン｜OneLinkを自社ドメイン化する方法
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2026-10-28T09:18:22Z'
  id: 360002329137
  locale: ja
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ja/articles/360002329137
---
> **At a glance:** OneLinkリンクを使用する広告主は、自社ドメインを使用してリンクをブランド化できます。これにより、キャンペーンのパフォーマンス向上とブランド露出の拡大が期待できます。

![Branded_1__3_.jpg](https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png)

## ブランドドメイン

* ブランドドメインを使用すると、自社ブランドとドメインを用いてアトリビューションリンクをブランド化できます。たとえば、上の図では以下のように設定されています。
  * OneLink： abcdef.onelink.me
  * ブランドドメイン： abcdef.com
  * サブドメイン例： app
  * ブランドドメインを実装すると、自社の完全修飾ドメインを使用でき、アトリビューションリンクをclick.abcdef.comのような形式にできます。
* ブランドドメインには、以下のようなメリットがあり、キャンペーンのパフォーマンス向上につながります。
  * 信頼性の向上：　自社ブランドを活用し、一貫したブランドアイデンティティを維持することで、ユーザージャーニー上の不安や抵抗を減らし、CTRの向上につなげます。
  * 自社ブランドを活用したディープリンクが可能です。
  * 簡単な実装：　実装が容易で、OneLinkと同じように動作します。
  * ブランド認知度の向上： 一般的な汎用リンクではなく、自社ブランドをキャンペーンに表示できます。
  * リンクのドメインと送信元メールアドレスのドメインが一致しないことによる、メールのスパム判定リスクを軽減できます。
  * ブランドドメインは、AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/account-management-plans-payments-and-billing">有料契約プラン</Anchor>に含まれています。

### 実装の基本原則

ブランドドメインは、DNS（Domain Name System）で定義した完全修飾ドメインを、OneLinkのサブドメイン、すなわちAppsFlyerのCNAME参照先に関連付けることで実装します。実装には、DNSの標準設定を使用するとともに、AppsFlyer上でブランドドメインを設定します。さらに、ブランドドメインに対応するため、アプリにも軽微な変更を加える必要があります。

設定にあたっては、通常、自社のITチームまたはDNSホスティングプロバイダーに所属するDNS管理者と、アプリ開発者の協力が必要です。

1つのOneLinkサブドメインに、複数の完全修飾ドメインを関連付けることもできます。これにより、複数のブランドで同じOneLinkサブドメインを使用できます。

### ブランドドメインの設定

ブランドドメインを設定するには、以下の作業を完了してください。

|  | 担当者 | 作業 | 備考 |
| --- | --- | --- | --- |
| 1 | DNS管理者の支援を受けるマーケティング担当者 | [AppsFlyerでブランドリンクを設定する](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | 通常は自社のITチームまたはDNSホスティングプロバイダーに所属するDNS管理者が、完全修飾ドメイン（ホストとも呼ばれます）を定義し、手順に従ってCNAMEレコードを設定する必要があります。 |
| 2 | 開発者 | [アプリでブランドドメインを設定する](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | アプリのコードに軽微な変更を加えます。 |
| 3 | マーケティング担当者 | [ブランドドメインを使用してテストする](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| 必要に応じて | マーケティング担当者 | [ブランドドメインを編集または削除する](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

### 手順

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="AppsFlyerでブランドドメインを設定する">

ブランドドメインの設定では、以下の図のように、DNSで設定した完全修飾ドメインをAppsFlyerのOneLinkサブドメインに関連付けます。

**AppsFlyerサーバーを参照するブランドドメイン**

![AppsFlyerサーバーを参照するブランドドメインの図](https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png)

**始める前に：**

* 使用する完全修飾ドメイン名を決定します。 たとえば、app.abcdef.comです。   
  abcdef.comは自社ブランドのドメインです。 appなどのサブドメインも任意に設定できます。
* DNS管理者に、完全修飾ドメイン（ホスト）の作成を依頼します。
* DNS管理者に、完全修飾ドメイン、つまりブランドドメインが指定されたURL、  
  すなわちAppsFlyerホストを参照するよう、CNAMEレコードの設定を依頼します。  
  この構成は、上の「AppsFlyerサーバーを参照するブランドドメイン」の図に示されています。

**完全修飾ドメインをOneLinkサブドメインにマッピングする**：

1. AppsFlyerで、**エンゲージメント** > **ブランドドメイン**の順にクリックします。
2. **＋新しいブランドドメイン**をクリックします。
3. **ブランドドメイン**フィールドに、DNSで設定した完全修飾ドメインを入力します。例：click.abcdef.com **注意：** ドメインの末尾にピリオドを付けないでください。
4. 表示された一覧から、OneLinkサブドメインを選択します。一覧が表示されない場合は、  
   OneLinkテンプレートを作成する必要があります。 OneLinkテンプレートを作成すると、  
   デフォルトのサブドメインが提供されます。
5. **次へ**をクリックします。
6. CNAMEレコードを設定します：
   * ドメインがAppsFlyerのCNAME参照先を正しく参照している場合は、  
     「AppsFlyerのCNAMEが見つかりました」と表示されます。
   * CNAMEが見つからない場合は、AppsFlyerのCNAME参照先をコピーしてDNS管理者に共有し、完全修飾ドメインがそのCNAME参照先にマッピングされていることを確認するよう依頼してください。 DNS管理者は、完全修飾ドメインがAppsFlyerのCNAME参照先を指すように設定する必要があります。マッピングされていない場合、ブランドドメイン自体は作成されますが、正常に動作しません。

     > 📘 **Note**
     >
     > **注意**
     >
     > CNAMEレコードは、ブランドドメインの作成日から確認ダイアログに表示される指定日までの7日以内にマッピングする必要があります。  
     > 指定された期日までにCNAMEレコードがマッピングされなかった場合は、  
     > [7日間の設定期間を更新](#cnameレコードのマッピング期限7日間の更新)する必要があります。

7. **完了**をクリックします。これで、ブランドドメインにマッピングされたOneLinkテンプレートを使用して、新しいリンクを作成できます。

   > 📘 **Note**
   >
   > **注意**
   >
   > * ブランドドメインを設定する前に、同じOneLinkテンプレートを使用してリンクをすでに作成している場合でも、それらのリンクは引き続き正常に動作します。
   > * 新しいブランドドメインが利用可能になるまで、最大24時間かかる場合があります。


#### CNAMEレコードのマッピング期限（7日間）の更新

ブランドドメインの作成から7日以内に完全修飾ドメインのCNAMEレコードがAppsFlyerへマッピングされなかった場合、新しいブランドドメインは機能しません。

> 📘 **Note**
>
> **注意**
>
> 7日間の期限が過ぎた後にCNAMEレコードをマッピングした場合でも、新しいブランドドメインを動作させるには、7日間の設定期間を更新する必要があります。

**7日間の設定期間を更新するには、以下の手順を実行します：**

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **ブランドドメイン**へ移動します。
2. 警告アイコン（![alert.png](https://files.readme.io/7df53739ca5c629ec0bda789563f59717da9699986222705228f57e0d947c8de-30192946335761.png)）が表示されている、AppsFlyerにまだマッピングされていないブランドドメインを開きます。
3. 更新アイコン（<Image alt="refresh.png" src="https://files.readme.io/052b47c423612c1b0549f37ed6394373d37f28331e09f4c709601a7e5473bf2b-30192959741585.png" width="18px" />）をクリックして、7日間の設定期間を更新します。

> 📘 **Note**
>
> **注意**
>
> 7日間の設定期間を更新しない場合は、削除アイコン（<Image alt="delete-subdomain.png" src="https://files.readme.io/0029cc63db331d998182d46a63f9da9856de9b2351abd5b2d87fb2b47ae853c2-30192959748241.png" width="16px" />）をクリックしてブランドドメインを削除できます。削除できるのは、AppsFlyerにまだマッピングされていないブランドドメインのみです。

#### カスタムSSL証明書（任意）

AppsFlyerが管理するSSLは、デフォルトかつ多くのお客様に推奨される設定です。 AppsFlyerが証明書の発行と更新を自動的に行うため、追加の対応は必要ありません。特定のセキュリティ要件やコンプライアンス要件がある場合は、AppsFlyer管理のSSLではなく、自社で選択した認証局のSSL証明書、すなわちカスタムSSL証明書を使用できます。このオプションを選択した場合、証明書の発行、アップロード、管理、更新はお客様の責任で行う必要があります。証明書の有効期限が切れ、期限内に更新されなかった場合、サービスが中断する可能性があります。

**カスタムSSL証明書を使用するには：**

1. [ブランドドメインを作成します](/docs/brand-onelink-with-your-domain#ブランドドメインの設定)。
2. AppsFlyerで、**エンゲージメント** > **ブランドドメイン**の順に移動し、対象のドメインにカーソルを合わせて「カスタムSSL証明書」アイコンを選択します。

   <Image alt="SSL certificate icon Newest minimal.png" src="https://files.readme.io/8b22a41fd755a3f36e8eaf4a869b107661894d81504bbfb44e1fc728b9b06751-45231876708497.png" width="1044px" />
3. 証明書情報のフォームに必要事項を入力します。

   <Image alt="fill in form to generate CSR file.png" src="https://files.readme.io/4327a4da0cbcc6243c9bbdbec21fe4f91d7fe701ccbffca99e629a5eadd248e8-45231876709649.png" width="722px" />
4. **CSRをダウンロード**をクリックし、入力した内容に基づくCSRファイルをダウンロードします。 <Image alt="Download CSR file.png" src="https://files.readme.io/9a560d19e38593fbc379efc6bdb1e636e1fa34f894dca4b46a23be30019127dd-45231892701585.png" width="254px" />
5. ダウンロードしたCSRファイルを、選択したSSL認証局に提出します。
6. 認証局から新しいSSL証明書が発行されたら、その証明書をAppsFlyerにアップロードします。

<Image alt="Upload new SSL certificate to AF.png" src="https://files.readme.io/b22525d9f653c3897f39f02a7beded3ad5c42d74a5487458f2ed720a20351e03-45231892701969.png" width="811px" />

> 📘 **Note**
>
> **注意**
>
> SSL証明書には有効期限があります。現在の証明書の有効期限が切れる前に、証明書を更新し、更新後の証明書をAppsFlyerにアップロードする責任はお客様にあります。

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="アプリでブランドドメインを設定する">

* 以下のSDKバージョンを使用してください：
  * Android SDK V4.10.1以降
  * iOS SDK V4.10.1以降
  * ユーザー紹介機能を使用する場合は、iOSとAndroidの両方でSDK V5.2.0以降が必要

**ブランドドメインのSDK実装に関する考慮事項**

* ブランドドメインを使用してディープリンクが行われた場合、AppsFlyer SDKは、インストールおよびディープリンクに関するコンバージョンデータを取得できません。
* この問題に対応するため、開発者はAndroidでは`setOneLinkCustomDomain`、iOSでは`oneLinkCustomDomains`のSDK APIを使用します。
* このAPIはブランドドメインに問い合わせ、マッピングされているOneLinkドメインを取得したうえで、OneLinkの処理を完了します。

<Tabs>
<Tab title="Android">

マニフェストの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">intent-filter</Anchor>を更新し、android:hostにブランドドメインを指定してください。

<Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">AndroidのグローバルApplicationクラス</Anchor>で、SDKを初期化する前にこのAPIを使用してください。

**例**

```java
public class AFApplication extends Application {

    @Override
    public void onCreate() {
    super.onCreate();

      // Set branded link domain. ドメインにはhttps://を含めないでください。 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

ブランドドメインが複数ある場合は、コンバージョンデータを常に取得し、アプリへのディープリンクを正常に行えるよう、すべてのドメインをAPIに渡してください。

**例**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="iOS">

**iOS Universal Links用にドメインを関連付ける方法：**

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#enabling-associated-domains">Xcodeで設定</Anchor>した**OneLinkドメイン／サブドメイン**を、Associated Domainsとして登録します。
* Xcode にて**ブランドドメイン**を <Anchor target="_blank" href="https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains">associated domain</Anchor> と設定します。
* コンバージョンデータを取得できるよう、ブランドリンクを設定します。手順については、以下から該当するプログラミング言語を選択してください。

<Tabs>
<Tab title="Objective-C">

AppDelegate.mのdidFinishLaunchingWithOptionsメソッド内で、以下のAPIを使用します。

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** APPSFLYER INIT **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

ブランドドメインが複数ある場合は、コンバージョンデータを常に取得し、アプリへのディープリンクを正常に行えるよう、すべてのドメインをAPIに渡してください。

**例**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

AppDelegate.swiftのdidFinishLaunchingWithOptionsメソッド内で、以下のAPIを使用します：

```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions 
        launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
          AppsFlyerLib.shared().appsFlyerDevKey = "6CQi4Be6Zs9oNLsCusPbUL"
          AppsFlyerLib.shared().appleAppID = "340954504"
          AppsFlyerLib.shared().oneLinkCustomDomains = ["example.com"]
          //...
          //...
   }
```

ブランドドメインが複数ある場合は、文字列の配列としてAPIに渡すことができます。これにより、どのブランドリンクが使用された場合でも、コンバージョンデータを取得し、アプリへのディープリンクを正常に行えるようになります。

**例**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="ブランドドメインを使用してテストする">

**前提条件**：

ブランドドメインを使用してテストする前に、[ブランドドメインのワークフロー](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app)に記載されている手順をすべて完了してください。

**ブランドドメインの作成とテスト方法：**

1. ブランドドメインにマッピングされたOneLinkテンプレートを使用して<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#onelinkリンクの作成">OneLinkのカスタムリンクを作成</Anchor>してください。
2. カスタム計測リンクをテキストエディタにコピーします。
3. カスタム計測リンクは、OneLinkサブドメイン、OneLink ID、およびカスタムリンクID で構成されています。 OneLinkサブドメインを、ブランドドメインの完全修飾ドメインに置き換えます。例：

| カスタム計測リンク | ブランドドメイン |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **click.abcdef.com**/A1bc/dc1234ef |

4. ブランドリンクを使用して<Anchor target="_blank" href="/marketers/ja/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">インストールとディープリンクをテスト</Anchor>します。
5. テストの一環としてローデータレポートを使用する場合、Original URLのフィールドにはブランドリンクが入力されます。

</Accordion>

<div id="editing-verifying-and-deleting-branded-domains" />

<Accordion title="ブランドドメインを編集、検証、削除する">

#### **ブランドドメインのマッピングを編集する**

既存の完全修飾ドメインのマッピング先を、別のOneLinkサブドメインに変更できます。この場合、CNAMEを再設定する必要はありません。

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **ブランドドメイン**へ移動します。
2. 編集するブランドドメインに移動します。
3. 編集アイコン （<Image alt="edit-subdomain.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="17px" />） をクリックします。
4. 新しいOneLinkサブドメインを選択します。
5. **次へをクリックします。** CNAME を設定する必要はありません。
6. ［**完了**］をクリックします。

> 🚧 **Important**
>
> **要注意**
>
> 配信中のキャンペーンで使用しているブランドドメインを変更すると、リンクの動作が変わったり、リンクが機能しなくなったりする可能性があります。

#### **ブランドドメインのマッピングを検証する**

ブランドドメインにマッピングされているOneLinkサブドメインを変更した後は、ブランドドメインが正しくマッピングされていることを確認してください。

1. AppsFlyer管理画面 左メニュー **エンゲージメント** > **ブランドドメイン**へ移動します。
2. 検証するブランドドメインに移動します。
3. 確認アイコン（<Image alt="verify-2.png" src="https://files.readme.io/4ac94a535e9101b3e727351f67df8917c0870d6ede8ec963de8c5528893b8e2b-30192946342929.png" width="17px" />）をクリックします。

> 📘 **Note**
>
> **注意**
>
> CNAMEレコードがまだマッピングされていないことが原因で検証に失敗した場合は、検証失敗ダイアログに表示される期日まで、最大7日間の設定期間があります。
> 指定された期日までにCNAMEレコードがマッピングされなかった場合は、7日間の設定期間を更新する必要があります。

#### **ドメインのCNAMEレコードがAppsFlyerを参照しなくなった場合：**

CNAMEレコードを変更し、AppsFlyerを参照しない状態にすると、該当するブランドドメインはAppsFlyerから削除されます。

#### **ブランドドメインのマッピングを削除する：**

ブランドドメインを削除するには、AppsFlyerのCSMまたはhello@appsflyer.comまでお問い合わせください。

</Accordion>

## トラブルシューティング、特性、制限事項

<div id="troubleshooting" />

<Accordion title="トラブルシューティング">

| 症状 | 原因／解決方法 |
| --- | --- |
| ブランドドメインをOneLinkテンプレートにマッピングできない | <ul><li>**ドメイン名が無効：** ブランドドメインをOneLinkテンプレートにマッピングする際、AppsFlyerはブランドリンクのドメイン名が有効であることを確認します。有効なドメイン名は、click.abdef.comのような形式です。</li><li>**ブランドドメインがすでにマッピングされている：** 1つの完全修飾ドメインをマッピングできるのは1回のみです。</li></ul> |
| ブランドドメインからアプリへディープリンクされない | <ul><li>[ブランドドメインが機能していることを確認する](#ブランドドメインのマッピングを検証する)</li><li>**CNAMEを確認する：** ブランドドメインからAppsFlyerを参照するCNAMEレコードが設定されていることを確認してください。</li><li>**OneLinkテンプレートのディープリンク設定を確認する：** OneLinkのディープリンク設定に問題がある可能性があります。 OneLinkを使用したディープリンクが正しく設定されていることを確認してください。</li><li>**OneLinkのマッピングが変更された：** ブランドドメインを編集し、別のOneLinkにマッピングできます。新たにマッピングしたOneLinkのディープリンク設定が異なる場合や、ディープリンク設定がない場合は、ディープリンクが機能しない可能性があります。</li></ul> |
| ブランドドメイン経由のインストールが計測されない | <ul><li>**OneLinkテンプレート設定の確認：** ブランドドメインへのマッピングに使用したOneLinkサブドメインが、正しいアプリに関連付けられていることを確認してください。</li><li>**OneLinkサブドメインが変更された：** ブランドドメインをOneLinkテンプレートにマッピングした後でOneLinkサブドメインが変更されると、アトリビューションに影響する可能性があります。</li><li>**実装の確認：** アプリにsetOneLinkCustomDomain APIが実装されていることを確認してください。</li></ul> |
| ブランドドメイン経由のリエンゲージメントが記録されない | 以下が有効であり、正しく設定されていることを確認してください。<ul><li><Anchor target="_blank" href="/marketers/ja/docs/onelink-guide#onelinkの設定">OneLinkにディープリンクが設定</Anchor>されていること</li><li>アプリが、専用の[SDK API setOneLinkCustomDomain](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer)を使用している</li><li><Anchor target="_blank" href="/marketers/ja/docs/retargeting-attribution-guide#retargeting-settings">アプリ設定でリターゲティングが有効</Anchor>に設定されている</li></ul> |
| ブランドドメインの設定中に「**ドメインが存在しません**」と表示される | <ol><li>DNS管理者に連絡し、調査を依頼します。</li><li>DNS管理者からドメインが登録済みであるとの連絡を受けるまで待ちます。</li><li>**再確認**をクリックします。</li></ol> |
| ブランドドメインの設定中に「**AppsFlyerのCNAMEが見つかりません**」と表示される | <ol><li>DNS管理者に、完全修飾ドメイン、つまりブランドドメインが、指定されたURL、すなわちAppsFlyerホストを参照するよう、CNAMEレコードの設定を依頼します。この構成は、本セクションの「AppsFlyerサーバーを参照するブランドリンク」の図に示されています。</li><li>DNS管理者からCNAMEが有効になったとの連絡を受けるまで待ちます。</li></ol> |
| ブランドドメインのページを開いたときに「**ブロックされました**」と表示される | ブランドドメイン単体には、テンプレートやパラメータは含まれていません。ブランドドメインを使用する場合は、ブランドドメインURLの末尾にテンプレートまたはパラメータを追加する必要があります。<br /><br />たとえば、ブランドドメインがclick.abcdef.comの場合、**click.abcdef.com**のみを使用すると、<strong>「ブロックされました」</strong>というメッセージが表示されます。<br /><br />URLの末尾にパラメータまたはテンプレートを追加する必要があります。例：click.abcdef.com **/A1bc/dc1234ef** |
| ブランドドメインのページを開いたときに**err\_cert\_authority\_invalid**エラーが表示される | このエラーは、認証局が認識されていないため、ブランドドメインに有効なHTTPS証明書が設定されていないことを示します。 AppsFlyerはLet's Encryptを使用してブランドドメインの証明書を発行しているため、ドメインのCAA（Certification Authority Authorization）DNSレコードで、Let's Encryptが有効な認証局（CA）として認識されていない可能性があります。<br /><br />**解決策**<br />以下を実行してください：<ol><li><Anchor target="_blank" href="https://www.entrust.com/resources/certificate-solutions/tools/caa-lookup">外部サービス</Anchor>などを使用して、自社ドメインがLet's Encryptを認証局として認識しているかどうかを確認します。</li><li>2. システム管理者に、Let's Encryptを認可済みの認証局として含めるよう、ドメインのCAAレコードの更新を依頼します。</li></ol> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="特性と制限事項">

| 特性 | はい ✓ / いいえ **x** | 備考 |
| --- | --- | --- |
| アカウントユーザーのアクセス権限 | ✓ |  |
| アドネットワークのアクセス権限 | **x** |  |
| 代理店のアクセス権限 | **x** | 代理店は、ブランドドメインまたはOneLinkリンクを作成できません。 |
| 代理店の運用媒体の開示 | **x** |  |
| アプリ固有の通貨設定 | N/A |  |
| アプリ固有のタイムゾーン設定 | N/A |  |
| ブランドドメインの利用可否 | N/A | ブランドドメインは、対象となる有料プランでのみ利用できます。サブスクリプションプランの有効期限が切れた場合や解約された場合は、ブランドドメインを利用できなくなり、既存のブランドドメインを使用したリンクも機能しなくなります。 |
| 文字の制限 | N/A | ブランドドメインを入力する際、末尾の文字にピリオド（.）は使用できません。 |
| データの更新頻度 | N/A |  |
| 過去データ | ✓ |  |
| HTTP | **x** | ブランドリンクではHTTPプロトコルはサポートされていません。 HTTPSを使用する必要があります。 |
| 非オーガニックデータ | ✓ |  |
| オーガニックデータ | ✓ |  |
| レート制限 | ✓ | ブランドドメインのSSL／HTTP証明書は、AppsFlyerが<Anchor target="_blank" href="https://letsencrypt.org/">Let's Encrypt</Anchor>を使用して発行します。 証明書の発行上限は、1つのドメインにつき1週間あたり新規50件です。 |
| サイズ制限 | N/A |  |
| SSL / HTTP証明書の更新 | ✓ | AppsFlyerが管理するブランドドメインのSSL / HTTP証明書は、自動的に更新されます。 |

</Accordion>

<div data-zendesk-anchors="branded-domains=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 h_01HFM51V4PE53FQAED68V8Q834=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3 principles-of-implementation=%E5%AE%9F%E8%A3%85%E3%81%AE%E5%9F%BA%E6%9C%AC%E5%8E%9F%E5%89%87 h_01HFM51V4PPJXMCSV5ZVDPT49M=%E5%AE%9F%E8%A3%85%E3%81%AE%E5%9F%BA%E6%9C%AC%E5%8E%9F%E5%89%87 setting-up-branded-domains=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A h_01HFM51V4PH58ZA4ZXHP5J6K2W=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E8%A8%AD%E5%AE%9A procedures=%E6%89%8B%E9%A0%86 h_01HFM51V4PWWX7TBCHFMPR3QVB=%E6%89%8B%E9%A0%86 h_01HQ5CWGQNRBXQ6QQDADV7XCQP=set-up-a-branded-domain-in-appsflyer renew-the-day=cname%E3%83%AC%E3%82%B3%E3%83%BC%E3%83%89%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E6%9C%9F%E9%99%907%E6%97%A5%E9%96%93%E3%81%AE%E6%9B%B4%E6%96%B0 h_01HQ5CWGQNQJJ1CXDKTGZ8N9ZE=cname%E3%83%AC%E3%82%B3%E3%83%BC%E3%83%89%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E6%9C%9F%E9%99%907%E6%97%A5%E9%96%93%E3%81%AE%E6%9B%B4%E6%96%B0 custom-ssl-certificate=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0ssl%E8%A8%BC%E6%98%8E%E6%9B%B8%E4%BB%BB%E6%84%8F h_01KM0E8VHARA2JRAR2H37QM91Y=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0ssl%E8%A8%BC%E6%98%8E%E6%9B%B8%E4%BB%BB%E6%84%8F h_01HFM51V4PP0NQHVHTKB86250R=set-up-branded-domains-in-the-app h_01HFM51V4PN0FPEDNAF0Q1QS8P=using-and-testing-branded-domains h_01HQ5CWGQPZ6MEFA6MDTHYHCSA=editing-verifying-and-deleting-branded-domains edit-a-branded-domain-mapping=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01HQ5FJZD6QMNFA45Z2C7CA3ST=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%92%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B verify-a-branded-domain-mapping=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%92%E6%A4%9C%E8%A8%BC%E3%81%99%E3%82%8B h_01HQ5FK5XJNZ1EABJA66RMYBCN=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%92%E6%A4%9C%E8%A8%BC%E3%81%99%E3%82%8B domain-cname-record-no-longer-pointing-to-appsflyer=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AEcname%E3%83%AC%E3%82%B3%E3%83%BC%E3%83%89%E3%81%8Cappsflyer%E3%82%92%E5%8F%82%E7%85%A7%E3%81%97%E3%81%AA%E3%81%8F%E3%81%AA%E3%81%A3%E3%81%9F%E5%A0%B4%E5%90%88 h_01JSHFECXS00M6BXH8168ZWJE5=%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AEcname%E3%83%AC%E3%82%B3%E3%83%BC%E3%83%89%E3%81%8Cappsflyer%E3%82%92%E5%8F%82%E7%85%A7%E3%81%97%E3%81%AA%E3%81%8F%E3%81%AA%E3%81%A3%E3%81%9F%E5%A0%B4%E5%90%88 delete-a-branded-domain-mapping=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%92%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B h_01JSHF5RMXXFJTXC246KKAQBSS=%E3%83%96%E3%83%A9%E3%83%B3%E3%83%89%E3%83%89%E3%83%A1%E3%82%A4%E3%83%B3%E3%81%AE%E3%83%9E%E3%83%83%E3%83%94%E3%83%B3%E3%82%B0%E3%82%92%E5%89%8A%E9%99%A4%E3%81%99%E3%82%8B troubleshooting-traits-and-limitations=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E7%89%B9%E6%80%A7%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HFM51V4PH4YM13DVXENRWF2E=%E3%83%88%E3%83%A9%E3%83%96%E3%83%AB%E3%82%B7%E3%83%A5%E3%83%BC%E3%83%86%E3%82%A3%E3%83%B3%E3%82%B0%E7%89%B9%E6%80%A7%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01HFM51V4PJNHZTD97X75WPN98=troubleshooting h_01HFM51V4QQ2TZQMJ2ATNDG91F=traits-and-limitations" />

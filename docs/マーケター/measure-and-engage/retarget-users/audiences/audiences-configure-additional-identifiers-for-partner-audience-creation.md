---
title: オーディエンス - パートナーオーディエンス作成のための追加識別子を設定する
metadata:
  keywords:
    - Audiences
    - Advertisers
    - Developers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-02-14T16:23:45Z'
  edited_at: '2026-10-14T09:37:20Z'
  id: 360017807278
  locale: ja
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ja/articles/360017807278
---
> **概要:** カスタムオーディエンスを広告パートナーに送信するための追加のユーザー識別子を設定します。

## 追加の識別子について

AppsFlyer Audiencesは、カスタムオーディエンスを<Anchor target="_blank" href="/marketers/ja/docs/audiences-partner-connections">広告パートナー</Anchor>に送信するための以下のデバイス識別子を自動的にサポートします。

* **iOS:IDFA**
* **Android (Google Play):** GAID
* **Android（サードパーティのアプリストア）:** <Anchor target="_blank" href="/marketers/ja/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>とIMEI

一部の広告パートナーは、追加のユーザー識別子に基づくカスタムオーディエンスのマッチングもサポートしています。オーディエンスでは、AppsFlyer SDKまたはS2SモバイルAPIを利用してこれらの識別子を特別に設定した場合に、これらを使用する選択肢を提供します。

**これらの追加識別子には電話番号やメールが含まれますが、SHA256ハッシュで暗号化されている場合に限り利用できます。  これらの追加の識別子の使用には、[Additional Identifiers Terms of Use](https://support.appsflyer.com/hc/article_attachments/16567368205201)（追加識別子の利用規約）への同意が必要です。**

## 次のステップ

1. 使用したい追加識別子を[利用可能な識別子の表](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)から選択します。すべての広告パートナーがすべての識別子をサポートするわけではありませんので、ご注意ください。
2. デベロッパー—以下の方法で選択した識別子を設定します。
   * 利用可能な識別子の表[に記載されているパラメーターおよびフォーマット要件](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)
   * [SDK](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#sdk-reference-and-code-samples)および[S2S](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#s2s-reference-and-code-samples)のリファレンスおよびコードサンプル
3. オーディエンス管理画面で:
   * <Anchor target="_blank" href="/marketers/ja/docs/audiences-user-identifier-policy">アカウントレベルのユーザー識別子ポリシー</Anchor>を設定します
   * 各<Anchor target="_blank" href="/marketers/ja/docs/audiences-guide#manage-connections">パートナー接続</Anchor>でアップロードする識別子を選択します

## 利用可能な識別子

以下の表に示されているように、1つ以上の識別子を設定できます。

<Accordion title="追加の識別子 — パラメーターとフォーマット">

<table><thead><tr><th>識別子</th><th>パラメーター名</th><th>形式</th><th>ハッシュ化前の例となる値</th></tr></thead><tbody><tr><td>メールアドレス</td><td>email_sha256</td><td><p><strong>SDK v7.0.0以前：</strong></p><ul><li>小文字</li><li>空白なし</li><li>クライアント側でハッシュ化（SHA256）してから渡します</li></ul><p><strong>SDK v7.0.1以降：</strong>プレーンテキスト。SDKはそれを自動的に正規化およびハッシュ化します。</p></td><td>name@domain.com</td></tr><tr><td>電話番号<br/>（下記注意参照）</td><td><p><strong>v7.0.0以前（またはS2S）：</strong> phone_number_sha256</p><p><strong>v7.0.1 and later:</strong> phone_number_hashed</p></td><td><p><strong>v7.0.0以前（またはS2S）：</strong></p><ul><li>記号、文字、先頭のゼロを含めない</li><li>国コードを含める</li><li>SHA256ハッシュ済み</li></ul><p><strong>バージョン7.0.1以降：</strong>プレーンテキスト。SDKは国コードと国番号を連結し、正規化してハッシュ化を自動的に行います。</p></td><td>442070313000</td></tr><tr><td><p>電話番号 E164</p><p>（下記注意参照）</p></td><td><p><strong>v7.0.0以前（またはS2S）：</strong>電話番号_e164_sha256</p><p><strong>v7.0.1 and later:</strong> phone_number_e164_hashed</p></td><td><p><strong>v7.0.0以前（またはS2S）：</strong></p><ul><li>E164電話番号</li><li>SHA256ハッシュ済み</li></ul><p><strong>バージョン7.0.1以降：</strong>プレーンテキスト。SDKは国コードと国番号を連結し、正規化してハッシュ化を自動的に行います。</p></td><td>+442070313000</td></tr><tr><td colspan="4"><p><br /><br /><strong>注意</strong><br /></p><p>異なる広告パートナーは異なる電話番号形式をサポートしています。したがって、電話番号を利用する場合は、両方の識別子を設定してください。<em>電話番号</em>と<em>電話番号 E164。</em></p></td></tr></tbody></table>

</Accordion>

## SDKリファレンスとコードサンプル

SDKを介してオーディエンスの識別子を送信する場合:

* ハッシュ化された*メールアドレス*や*電話番号*以外の識別子には、`setAdditionalData` 。
* ハッシュ化された*メールアドレス*には*を使用してください。
  * SDK v7.0.1以降:`setUserEmail` 。
  * SDK v7.0.0以前: 使用`setUserEmails`。*
* ハッシュ化された*電話番号*の場合：
  * SDK v7.0.1以降:`setUserPhone` （推奨）。
  * SDK v7.0.0以前: 使用`setAdditionalData`カスタムデータを使用。

> 📘 **注意**
>
> 以下のバージョン依存の変更点にご注意するください。
>
> * **メールアドレス：** SDK v7.0.1以降、`setUserEmails` (iOS/ Android) は完全に削除され、以下に置き換えられました`setUserEmail`。これは互換性を損なう変更であり、廃止ではありません。v7.0.0以前のアプリは引き続き使用する必要があります`setUserEmails`。v7.0.1以降のアプリは`setUserEmail`。どのサンプルに従うかを選択する前に、統合SDKのバージョンを確認してください。
> * PhoneSDK v7.0.1以降、専用の`setUserPhone`APIが利用可能です。これは、高度なマッチングのために電話番号識別子を送信する推奨方法です。これは互換性を損なう変更ではありません。`setAdditionalData`まだ動作します。新規統合の場合、およびv7.0.1以降にアップグレードするお客様には、以下への移行をお勧めします。`setUserPhone` 。v7.0.0以前のアプリは引き続き使用する必要があります`setAdditionalData`、 なぜなら`setUserPhone`これらのSDKバージョンには存在しません。

<Accordion title="iOS SDKの設定">

ハッシュ化された*電話番号*を追加のユーザー識別子として設定するには:

**SDK v7.0.0 and earlier — setAdditionalData**

<Tabs>
<Tab title="Objective-C">

```objectivec
NSDictionary *customData = @{
  @"audiences": @{
    @"phone_number_sha256": @"6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37",
    @"phone_number_e164_sha256":@"F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E"
  }
};
[[AppsFlyerLib shared] setAdditionalData:customData];
```

</Tab>

<Tab title="Swift">

```swift
let customData: Dictionary = [
  "audiences" : [
    "phone_number_sha256":"6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37",
    "phone_number_e164_sha256":"F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E"
  ]
] 
AppsFlyerLib.shared().customData = customData
```

</Tab>
</Tabs>

> 📘 **注意**
>
> 両方の値を渡す前に、必ずハッシュ化（SHA-256）する必要があります。

**SDK v7.0.1以降 — setUserPhone（推奨）**

<Table>
  <tbody>
    <tr>
      <td>
        **メソッドシグネチャ**
      </td>
      <td>
        ```objectivec
        - (void)setUserPhone:(NSString *_Nonnull)countryCode
        phoneNumber:(NSString *_Nonnull)phoneNumber;
        ```
      </td>
    </tr>
    <tr>
      <td>
        **使用例**
      </td>
      <td>
        \`
\`
<Accordion title="Objective-C">


```objectivec
[[AppsFlyerLib shared] setUserPhone:@"1" phoneNumber:@"(650) 555-1212"];
```


</Accordion>
\`
<Accordion title="Swift">


```swift
AppsFlyerLib.shared().setUserPhone(countryCode: "1", phoneNumber: "(650) 555-1212")
```


</Accordion>


      </td>
    </tr>
  </tbody>
</Table>

> 📘 **注意**
>
> 国番号と市内番号をプレーンテキストで渡してください。ローカル番号には記号とスペースを含めることができます。SDKは、両方の値をローカルで連結、正規化、ハッシュ化（SHA-256）します。事前ハッシュ化しないでください。

ハッシュ化された*メールアドレス*を追加のユーザー識別子として設定するには:

**SDK v7.0.0以前**

<Table>
  <tbody>
    <tr>
      <td>
        **メソッドシグネチャ**
      </td>
      <td>
        ```objectivec
        - (void)setUserEmails:(NSArray<NSString *> *_Nullable)userEmails 
        withCryptType:(EmailCryptType)type;
        ```
      </td>
    </tr>
    <tr>
      <td>
        **使用例**
      </td>
      <td>
        \`
\`
<Accordion title="Objective-C">


```objectivec
NSArray *emails = @[@"name@domain.com"];    
        [[AppsFlyerLib shared] setUserEmails:emails withCryptType:EmailCryptTypeSHA256];
```


</Accordion>
\`
<Accordion title="Swift">


```swift
let emails: Array = ["name@domain.com"]
        AppsFlyerLib.shared().setUserEmails(emails, with: EmailCryptTypeSHA256)
```


</Accordion>


      </td>
    </tr>
  </tbody>
</Table>

**SDK v7.0.1以降**

<Table>
  <tbody>
    <tr>
      <td>
        **メソッドシグネチャ**
      </td>
      <td>
        ```objectivec
        - (void)setUserEmail:(NSString *_Nonnull)email;
        ```
      </td>
    </tr>
    <tr>
      <td>
        **使用例**
      </td>
      <td>
        \`
\`
<Accordion title="Objective-C">


```objectivec
[[AppsFlyerLib shared] setUserEmail:@"name@domain.com"];
```


</Accordion>
\`
<Accordion title="Swift">


```swift
AppsFlyerLib.shared().setUserEmail("name@domain.com")
```


</Accordion>


      </td>
    </tr>
  </tbody>
</Table>

> 📘 **注意**
>
> プレーンテキストのメールを渡してください。SDKはそれをローカルで正規化し、ハッシュ化します（SHA-256）。事前ハッシュ化しないでください。通話ごとに受け付けられるメールは1通のみです。`setUserEmail`これは、以前に設定された値に加算するのではなく、それを上書きします。

</Accordion>

<Accordion title="Android SDKの設定">

ハッシュ化された*電話番号*を追加のユーザー識別子として設定するには:

**SDK v7.0.0 and earlier — setAdditionalData**

<Tabs>
<Tab title="Java">

```java
HashMap<String, Object> audiences = new HashMap<>();
audiences.put("phone_number_sha256", "6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37");
audiences.put("phone_number_e164_sha256", "F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E");
HashMap<String, Object> customDataMap = new HashMap<>();
customDataMap.put("audiences", audiences);
AppsFlyerLib.getInstance().setAdditionalData(customDataMap);
```

</Tab>

<Tab title="Kotlin">

```kotlin
val audiences = hashMapOf<String, Any>(
   "phone_number_sha256" to "6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37",
   "phone_number_e164_sha256" to "F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E"
)
val customDataMap = hashMapOf<String, Any>("audiences" to audiences)
AppsFlyerLib.getInstance().setAdditionalData(customDataMap)
```

</Tab>
</Tabs>

> 📘 **注意**
>
> 両方の値を渡す前に、必ずハッシュ化（SHA-256）する必要があります。

**SDK v7.0.1以降 — setUserPhone（推奨）**

<Table>
  <tbody>
    <tr>
      <td>
        **メソッドシグネチャ**
      </td>
      <td>
        ```java
        public abstract void setUserPhone(String countryCode, String phoneNumber);
        ```
      </td>
    </tr>
    <tr>
      <td>
        **使用例**
      </td>
      <td>
        \`
\`
<Accordion title="Java">


```java
AppsFlyerLib.getInstance().setUserPhone("1", "(650) 555-1212");
```


</Accordion>
\`
<Accordion title="Kotlin">


```java
AppsFlyerLib.getInstance().setUserPhone("1", "(650) 555-1212")
```


</Accordion>


      </td>
    </tr>
  </tbody>
</Table>

> 📘 **注意**
>
> 国番号と市内番号をプレーンテキストで渡してください。SDKは、両方の値をローカルで連結、正規化、ハッシュ化（SHA-256）します。事前ハッシュ化しないでください。

ハッシュ化された*メールアドレス*を追加のユーザー識別子として設定するには:

**SDK v7.0.0以前**

<Table>
  <tbody>
    <tr>
      <td>
        **メソッドシグネチャ**
      </td>
      <td>
        ```java
        public abstract void setUserEmails(
          AppsFlyerProperties.EmailsCryptType cryptMethod,
          String... emails
        );
        ```
      </td>
    </tr>
    <tr>
      <td>
        **使用例**
      </td>
      <td>
        \`
\`
<Accordion title="Java">


```java
AppsFlyerLib.getInstance().setUserEmails(
          AppsFlyerProperties.EmailsCryptType.SHA256,
          "name@domain.com",
          "another_name@another_domain.com"
        );
```


</Accordion>
\`
<Accordion title="Kotlin">


```java
AppsFlyerLib.getInstance().setUserEmails(
          AppsFlyerProperties.EmailsCryptType.SHA256,
          "name@domain.com",
          "another_name@another_domain.com"
        );
```


</Accordion>


      </td>
    </tr>
  </tbody>
</Table>

**SDK v7.0.1以降**

<Table>
  <tbody>
    <tr>
      <td>
        **メソッドシグネチャ**
      </td>
      <td>
        ```java
        public abstract void setUserEmail(String email);
        ```
      </td>
    </tr>
    <tr>
      <td>
        **使用例**
      </td>
      <td>
        ```java
        AppsFlyerLib.getInstance().setUserEmail("name@domain.com");
        ```
      </td>
    </tr>
  </tbody>
</Table>

> 📘 **注意**
>
> バージョン7.0.1以降では、1回の呼び出しにつき1通のメールのみが受け付けられます。複数のメールはサポートされていません:`setUserEmail`これは、以前に設定された値に加算するのではなく、それを上書きします。

</Accordion>

## S2Sリファレンスとコードサンプル

<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>を経由してオーディエンスの識別子を送信する場合、**すべての識別子（ハッシュ化されたメールアドレスも含む）には<Anchor target="_blank" href="/marketers/ja/docs/server-to-server-events-api-for-mobile-s2s-mobile">パラメータを使用してください。</Anchor>** 1つ以上の識別子を送信できます。

<Accordion title="S2S経由で識別子を送信する">

形式:

* ネストされたJSON
* キーの値は`audiences`でなければなりません
* すべての値は、以下のコード例に示すように文字列化する必要があります。
* パラメータ名は、上記の[表](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)に記載されている利用可能な識別子と一致する必要があります。

一般的な形式:

```json
"custom_data" : { 
      \"audiences\" : { 
          \"parameter_name_a\" : \"hashed_identifer_a\",
          \"parameter_name_a\" : \"hashed_identifer_b\",
          \"parameter_name_c\" : \"hashed_identifer_c\" 
       }
 }
```

ハッシュ化された*電話番号*とハッシュ化された*メールアドレス*の例:

```json
"custom_data" : {
     \"audiences\" : { 
         \"phone_number_sha256\" : \"6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37\",
         \"phone_number_e164_sha256\" : \"F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E\",
         \"email_sha256\"         : \"34D31BE18022626DE6B311D6A76E791176D2691B6EEF406F524D8F56364C187A\"
     }
}
```

</Accordion>

> 📄 **関連情報：**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/audiences-partner-connections">Audiencesのパートナー連携</Anchor>
> * <Anchor target="_blank" href="/marketers/ja/docs/audiences-user-identifier-policy">オーディエンスのユーザー識別子ポリシー</Anchor>
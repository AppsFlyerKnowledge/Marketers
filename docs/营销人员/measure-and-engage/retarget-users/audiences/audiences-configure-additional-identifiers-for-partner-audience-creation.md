---
title: 受众群体 - 为合作伙伴受众群体创建配置其他标识符
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
  edited_at: '2026-10-14T10:13:48Z'
  id: 360017807278
  locale: zh-cn
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/zh-cn/articles/360017807278
---
> **概要：** 向广告投放渠道发送自定义人群包时，您可以额外配置其他的用户标识符。

## 其他相关标识符简介

AppsFlyer的受众共享产品支持以下设备标识符，用于向<Anchor target="_blank" href="/marketers/zh/docs/audiences-partner-connections">合作渠道</Anchor>发送自定义人群包：

* **iOS**：IDFA
* **安卓（Google Play）：** GAID
* **安卓（第三方应用商店）：** <Anchor target="_blank" href="/marketers/zh/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>和IMEI

部分渠道还支持根据额外配置的用户标识符进行自定义的人群匹配。AppsFlyer的受众共享针对此类标识符提供多种使用方式，但您需要事先通过AppsFlyer SDK或S2S-mobile API对所需的特定标识符进行配置。

**这些额外的标识符还可包括电话号码和邮箱地址，但必须经过SHA256算法加密后才能使用。  使用此类额外标识符时，您还需要遵守额外标识符的使用条款。**

## 下一步

1. 从[可用标识符表格](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)中选择您要使用的额外标识符（若有）。请注意：并非所有渠道都支持全部标识符。
2. 开发人员——使用以下说明配置选定的标识符：
   * 请参考[可用标识表格](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)，了解具体的参数和格式要求
   * [SDK](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#sdk-reference-and-code-samples)和[S2S](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#s2s-reference-and-code-samples)的参考代码示例
3. 在受众共享面板中完成以下操作：
   * 设置<Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy">账户级别的用户标识符共享规则</Anchor>
   * 在各<Anchor target="_blank" href="/marketers/zh/docs/audiences-guide#manage-connections">渠道连接</Anchor>中选择需要上传的标识符

## 可用标识符

您可以配置一个或多个标识符。具体的可用标识符请见下表。

<Accordion title="额外标识符 — 参数和格式">

<table><thead><tr><th>标识符</th><th>参数名称</th><th>格式</th><th>示例值（加密前）</th></tr></thead><tbody><tr><td>邮箱地址</td><td>email_sha256</td><td><p><strong>SDK v7.0.0 及更早版本：</strong></p><ul><li>小写</li><li>无空格</li><li>在传入前进行客户端哈希处理 (SHA256)</li></ul><p><strong>SDK v7.0.1 及更高版本：</strong>纯文本。SDK 会自动对其进行标准化和哈希处理。</p></td><td>name@domain.com</td></tr><tr><td>电话号码<br/>(见表格下方注释）</td><td><p><strong>v7.0.0 及更早版本（或 S2S）：</strong> phone_number_sha256</p><p><strong>v7.0.1 及更高版本：</strong> phone_number_hashed</p></td><td><p><strong>v7.0.0 及更早版本（或 S2S）：</strong></p><ul><li>无符号、字母，不能以零开头</li><li>需包含国家代码</li><li>须经过SHA256加密</li></ul><p><strong>v7.0.1 及更高版本：</strong>纯文本。SDK 会自动拼接国家/地区代码和号码，进行标准化并执行哈希处理。</p></td><td>442070313000</td></tr><tr><td><p>电话号码E164</p><p>(见表格下方注释）</p></td><td><p><strong>v7.0.0 及更早版本（或 S2S）：</strong> phone_number_e164_sha256</p><p><strong>v7.0.1 及更高版本：</strong> phone_number_e164_hashed</p></td><td><p><strong>v7.0.0 及更早版本（或 S2S）：</strong></p><ul><li>E164电话号码</li><li>须经过SHA256加密</li></ul><p><strong>v7.0.1 及更高版本：</strong>纯文本。SDK 会自动拼接国家/地区代码和号码，进行标准化并执行哈希处理。</p></td><td>+442070313000</td></tr><tr><td colspan="4"><p><br /><br /><strong>注释</strong><br /></p><p>各个渠道支持的电话号码格式有所不同。如果您选择电话号码作为额外的标识符，请同时配置<em>电话号码</em>和<em>电话号码E164。</em></p></td></tr></tbody></table>

</Accordion>

## SDK参考说明和代码示例

通过SDK发送标识符用于受众共享时，请注意以下事项：

* 对于哈希处理的 *电子邮件地址* 或 *电话号码* 以外的标识符，请使用 `setAdditionalData`。
* 如需发送加密*邮箱地址*，请使用
  * SDK v7.0.1 及更高版本：请使用 `setUserEmail`。
  * SDK v7.0.0 及更早版本：请使用 `setUserEmails`。
* 对于哈希处理的 *电话号码*：
  * SDK v7.0.1 及更高版本：请使用 `setUserPhone`（推荐）。
  * SDK v7.0.0 及更早版本：请结合自定义数据使用 `setAdditionalData`。

> 📘 **注释**
>
> 请牢记以下版本相关的变更：
>
> * *电子邮箱自 SDK v7.0.1 起，`setUserEmails` (iOS/Android) 已被完全移除并由 `setUserEmail` 取代。这是一个破坏性变更，而非弃用。v7.0.0 及更早版本的应用必须继续使用 `setUserEmails`。v7.0.1 及更高版本的应用必须切换至 `setUserEmail`。在选择参考示例之前，请检查您集成的 SDK 版本。
> * 手机自 SDK v7.0.1 起，已提供专用的 `setUserPhone` API。这是发送用于高级匹配的电话号码标识符的推荐方式。这不是破坏性变更：`setAdditionalData` 仍然有效。对于新的集成，以及升级至 v7.0.1 及更高版本的客户，我们建议迁移至 `setUserPhone`。v7.0.0 及更早版本的应用必须继续使用 `setAdditionalData`，因为 `setUserPhone` 在这些 SDK 版本中不存在。

<Accordion title="iOS的SDK配置">

如需将加密后的*电话号码*设置为额外的用户标识符：

**SDK v7.0.0 及更早版本 — setAdditionalData**

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
> 您必须在传入这两个值之前对其进行预哈希处理 (SHA-256)。

**SDK v7.0.1 及更高版本 — setUserPhone（推荐）**

<Table>
  <tbody>
    <tr>
      <td>
        **方法签名**
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
        **用法示例**
      </td>
      <td>
<Accordion title="Objective-C">


```objectivec
[[AppsFlyerLib shared] setUserPhone:@"1" phoneNumber:@"(650) 555-1212"];
```


</Accordion>
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
> 请以纯文本形式传入国家/地区拨号代码和本地号码。本地号码中允许包含符号和空格。SDK 会在本地对这两个值进行拼接、标准化和哈希处理 (SHA-256)。请勿进行预哈希处理。

如需将加密后的*邮箱地址*设置为额外的用户标识符：

**SDK v7.0.0 及更早版本**

<Table>
  <tbody>
    <tr>
      <td>
        **方法签名**
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
        **用法示例**
      </td>
      <td>
<Accordion title="Objective-C">


```objectivec
NSArray *emails = @[@"name@domain.com"];    
        [[AppsFlyerLib shared] setUserEmails:emails withCryptType:EmailCryptTypeSHA256];
```


</Accordion>
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

**SDK v7.0.1 及更高版本**

<Table>
  <tbody>
    <tr>
      <td>
        **方法签名**
      </td>
      <td>
        ```objectivec
        - (void)setUserEmail:(NSString *_Nonnull)email;
        ```
      </td>
    </tr>
    <tr>
      <td>
        **用法示例**
      </td>
      <td>
<Accordion title="Objective-C">


```objectivec
[[AppsFlyerLib shared] setUserEmail:@"name@domain.com"];
```


</Accordion>
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
> 请传入纯文本格式的电子邮件地址。SDK 会在本地对其进行标准化和哈希处理（SHA-256）。请勿进行预哈希处理。每次调用仅接受一个电子邮件地址：再次调用 `setUserEmail` 会覆盖之前设置的值，而不是进行添加。

</Accordion>

<Accordion title="安卓的SDK配置">

如需将加密后的*电话号码*设置为额外的用户标识符：

**SDK v7.0.0 及更早版本 — setAdditionalData**

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
> 您必须在传入这两个值之前对其进行预哈希处理 (SHA-256)。

**SDK v7.0.1 及更高版本 — setUserPhone（推荐）**

<Table>
  <tbody>
    <tr>
      <td>
        **方法签名**
      </td>
      <td>
        ```java
        public abstract void setUserPhone(String countryCode, String phoneNumber);
        ```
      </td>
    </tr>
    <tr>
      <td>
        **用法示例**
      </td>
      <td>
<Accordion title="Java">


```java
AppsFlyerLib.getInstance().setUserPhone("1", "(650) 555-1212");
```


</Accordion>
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
> 请以纯文本形式传入国家/地区拨号代码和本地号码。SDK 会在本地对这两个值进行拼接、标准化和哈希处理 (SHA-256)。请勿进行预哈希处理。

如需将加密后的*邮箱地址*设置为额外的用户标识符：

**SDK v7.0.0 及更早版本**

<Table>
  <tbody>
    <tr>
      <td>
        **方法签名**
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
        **用法示例**
      </td>
      <td>
<Accordion title="Java">


```java
AppsFlyerLib.getInstance().setUserEmails(
          AppsFlyerProperties.EmailsCryptType.SHA256,
          "name@domain.com",
          "another_name@another_domain.com"
        );
```


</Accordion>
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

**SDK v7.0.1 及更高版本**

<Table>
  <tbody>
    <tr>
      <td>
        **方法签名**
      </td>
      <td>
        ```java
        public abstract void setUserEmail(String email);
        ```
      </td>
    </tr>
    <tr>
      <td>
        **用法示例**
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
> 在 v7.0.1 及更高版本中，每次调用仅接受一个电子邮件地址。不支持多个电子邮件地址：再次调用 `setUserEmail` 会覆盖之前设置的值，而不是进行添加。

</Accordion>

## S2S参考说明和代码示例

通过<Anchor target="_blank" href="/marketers/zh/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>发送用户标识符用于受众共享时，请使用`custom_data`参数。该参数适用于<strong>所有标识符（包括加密的邮箱地址）。</strong>您可以发送一个或多个标识符。

<Accordion title="通过S2S发送标识符">

格式：

* 多层嵌套JSON
* 参数值必须是`audiences`
* 所有参数值都必须转化为字符串，参见下图代码示例。
* 参数名称必须与上文[可用标识符表格](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)中所列的名称一致。

通用格式：

```json
"custom_data" : { 
      \"audiences\" : { 
          \"parameter_name_a\" : \"hashed_identifer_a\",
          \"parameter_name_a\" : \"hashed_identifer_b\",
          \"parameter_name_c\" : \"hashed_identifer_c\" 
       }
 }
```

填充参数值后的加密*电话号码*和*邮箱地址*代码示例：

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

> 📄 **另请参阅**
>
> * <Anchor target="_blank" href="/marketers/zh/docs/audiences-partner-connections">受众共享渠道连接</Anchor>
> * <Anchor target="_blank" href="/marketers/zh/docs/audiences-user-identifier-policy">人群包的用户标识符规定</Anchor>
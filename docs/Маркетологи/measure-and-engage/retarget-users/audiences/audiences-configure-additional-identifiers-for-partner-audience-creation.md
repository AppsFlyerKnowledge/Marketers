---
title: >-
  Аудитории — настройка дополнительных идентификаторов для создания партнерских
  аудиторий
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
  edited_at: '2026-09-02T00:34:28Z'
  id: 360017807278
  locale: ru
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ru/articles/360017807278
---
> **At a glance:** **Краткий обзор:** Настройте дополнительные идентификаторы пользователей для отправки пользовательских аудиторий рекламным Партнерам.

<div id="about-additional-identifiers" />

## О дополнительных идентификаторах

AppsFlyer Аудитории автоматически поддерживает следующие идентификаторы устройств для отправки пользовательских аудиторий <Anchor target="_blank" href="/marketers/ru/docs/audiences-partner-connections">рекламным Партнерам</Anchor>:

* **iOS: IDFA**
* **Android (Google Play):** GAID
* **Android (сторонние магазины приложений):** <Anchor target="_blank" href="/marketers/ru/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor> и IMEI

Некоторые рекламные Партнеры также поддерживают сопоставление пользовательских аудиторий на основе дополнительных идентификаторов пользователей. Аудитории предоставляет вам возможность использовать эти идентификаторы, если вы настроите их через SDK (пакет средств разработки ПО) AppsFlyer или мобильный API S2S.

Такие дополнительные идентификаторы могут включать номера телефонов и адреса электронной почты, но их можно **использовать только, если они зашифрованы с использованием хеширования SHA256**.  Использование таких дополнительных идентификаторов регулируется [Условиями использования дополнительных идентификаторов](https://support.appsflyer.com/hc/article_attachments/16567368205201).

<div id="next-steps" />

## Следующие шаги

1. Выберите дополнительные идентификаторы, которые вы хотите использовать (если таковые имеются), из [таблицы доступных идентификаторов](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting). Заметьте, что не все рекламные Партнеры поддерживают все идентификаторы.
2. Разработчики—Настройте выбранные идентификаторы, используя:
   * Параметры и требования к форматированию, указанные в [таблице доступных идентификаторов](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)
   * Справочные материалы и примеры кода для [SDK (пакет средств разработки ПО)](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#справочник-sdk-пакет-средств-разработки-по-и-образцы-кода) и [S2S](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#справочник-s2s-и-образцы-кода)
3. В дэшборде «Аудитории»:
   * Установите <Anchor target="_blank" href="/marketers/ru/docs/audiences-user-identifier-policy">политику идентификаторов пользователей на уровне учетной записи</Anchor>
   * Выберите идентификаторы, которые будут загружены в каждое из ваших <Anchor target="_blank" href="/marketers/ru/docs/audiences-guide#manage-connections">подключений с Партнерами</Anchor>.

<div id="available-identifiers" />

## Доступные идентификаторы

Вы можете настроить один или несколько идентификаторов, указанных в таблице ниже.

<Accordion title="Дополнительные идентификаторы — параметры и форматирование">

<table><tbody><tr><td>Идентификатор</td><td>Имя параметра</td><td>Формат</td><td>Пример значения (до хеширования)</td></tr><tr><td>Адрес электронной почты</td><td>email_sha256</td><td><p><strong>SDK v7.0.0 и более ранние:</strong></p><ul><li>В нижнем регистре</li><li>Без пробелов</li><li>Хешируется на стороне клиента (SHA256) перед передачей</li></ul><p><strong>SDK v7.0.1 и более поздние версии:</strong> Обычный текст. SDK автоматически нормализует и хеширует его.</p></td><td>name@domain.com</td></tr><tr><td>Номер телефона<br/>(см. примечание ниже)</td><td><p><strong>v7.0.0 и более ранние (или S2S):</strong> phone_number_sha256</p><p><strong>v7.0.1 и более поздние:</strong> phone_number_hashed</p></td><td><p><strong>v7.0.0 и более ранние (или S2S):</strong></p><ul><li>Без символов, букв или ведущих нулей</li><li>Включить код страны</li><li>SHA256 хеширование</li></ul><p><strong>v7.0.1 и более поздние:</strong> Обычный текст. SDK объединяет код страны и номер, нормализует и автоматически хеширует их.</p></td><td>442070313000</td></tr><tr><td><p>Номер телефона E164</p><p>(см. примечание ниже)</p></td><td><p><strong>v7.0.0 и более ранние (или S2S):</strong> phone_number_e164_sha256</p><p><strong>v7.0.1 и более поздние:</strong> phone_number_e164_hashed</p></td><td><p><strong>v7.0.0 и более ранние (или S2S):</strong></p><ul><li>E164 номер телефона</li><li>SHA256 хеширование</li></ul><p><strong>v7.0.1 и более поздние:</strong> Обычный текст. SDK объединяет код страны и номер, нормализует и автоматически хеширует их.</p></td><td>+442070313000</td></tr><tr><td colspan="4"><p><br /><br /><strong>Note</strong><br /></p><p><strong><span id="h_01HNZNWZ9XSY47T58Z5YR7Q65S"></span>номер_телефона_e164_sha256</strong></p><p>Разные рекламные Партнеры поддерживают разные форматы телефонных номеров. Поэтому, если вы решите использовать номер телефона, настройте оба идентификатора: <em>Номер телефона</em> и <em>Номер телефона E164.</em></p></td></tr></tbody></table>

</Accordion>

<div id="sdk-reference-and-code-samples" />

## Справочник SDK (пакет средств разработки ПО) и образцы кода

При отправке идентификаторов для аудиторий через SDK (пакет средств разработки ПО):

* Для идентификаторов, помимо хешированного *адреса электронной почты*, используйте
* Для хешированного *адреса электронной почты* используйте
  * SDK v7.0.1 и более поздние версии: используйте `setUserEmail`.
  * SDK v7.0.0 и более ранние версии: используйте `setUserEmails`.
* В дэшборде «Аудитории»:
  * SDK v7.0.1 и более поздние версии: используйте `setUserPhone` (рекомендуется).
  * SDK v7.0.0 и ранее: используйте`setAdditionalData` с пользовательскими данными.

> 📘 **Note**
>
> **Java Kotlin**
>
> Учитывайте следующие изменения, зависящие от версии:
>
> * **Электронная почта:** Начиная с SDK v7.0.1, метод setUserEmails (iOS/Android) полностью удален и заменен на setUserEmail. Это ломающие изменения, а не устаревание. Приложения на v7.0.0 и более ранних версиях должны продолжать использовать setUserEmails. Приложения на v7.0.1 и более поздних версиях должны перейти на setUserEmail. Проверьте версию интегрированного SDK, прежде чем выбирать пример, которому нужно следовать.
> * **Телефон:** Начиная с SDK v7.0.1, доступен отдельный API setUserPhone. Это рекомендуемый способ отправки идентификаторов номеров телефонов для Advanced Matching. Это не ломающие изменения: setAdditionalData по-прежнему работает. Для новых интеграций, а также для клиентов, обновившихся до версии 7.0.1 или более поздней, мы рекомендуем перейти на setUserPhone. Приложения на v7.0.0 и более ранних версиях должны продолжать использовать setAdditionalData, поскольку setUserPhone не существует в этих версиях SDK.

<div id="ios-sdk-configuration" />

## Настройка iOS SDK (пакет средств разработки ПО)

Чтобы задать хешированный *номер телефона* как дополнительный идентификатор пользователя:

### **SDK v7.0.0 and earlier — setAdditionalData**

<Tabs>
<Tab title="Objective C">

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
Objective-C Swift
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **Строчные буквы**
>
> Перед передачей необходимо предварительно хешировать оба значения (SHA-256).

<div id="sdk-v701-and-later--setuserphone-recommended" />

### **SDK v7.0.1 и более поздние версии — setUserPhone (рекомендуется)**

<div id="method-signature" />

#### SHA256 хеширование

```objectivec
- (void)setUserPhone:(NSString *_Nonnull)countryCode
phoneNumber:(NSString *_Nonnull)phoneNumber;
```

<div id="usage-example" />

#### Пример использования

<Tabs>
<Tab title="Objective C">

```objectivec
[[AppsFlyerLib shared] setUserPhone:@"1" phoneNumber:@"(650) 555-1212"];
```

</Tab>

<Tab title="Swift">

```swift
AppsFlyerLib.shared().setUserPhone(countryCode: "1", phoneNumber: "(650) 555-1212")
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **номер\_телефона\_sha256**
>
> Передавайте код страны и местный номер в виде обычного текста. В локальном номере допускаются символы и пробелы. SDK объединяет, нормализует и хеширует оба значения локально (SHA-256). Без предварительного хеширования.

Чтобы задать хешированный *адрес электронной почты* как дополнительный идентификатор пользователя:

<div id="sdk-v700-and-earlier" />

### **SDK v7.0.0 и более ранние версии**

<div id="method-signature-1" />

#### Сигнатура метода

```objectivec
- (void)setUserEmails:(NSArray<NSString *> *_Nullable)userEmails 
withCryptType:(EmailCryptType)type;
```

<div id="usage-example-1" />

#### Пример использования

<Tabs>
<Tab title="Objective C">

```objectivec
NSArray *emails = @[@"name@domain.com"];    
[[AppsFlyerLib shared] setUserEmails:emails withCryptType:EmailCryptTypeSHA256];
```

</Tab>

<Tab title="Swift">

```swift
let emails: Array = ["name@domain.com"]
AppsFlyerLib.shared().setUserEmails(emails, with: EmailCryptTypeSHA256)
```

</Tab>
</Tabs>

<div id="sdk-v701-and-later" />

### **SDK v7.0.1 и более поздние версии**

<div id="method-signature-2" />

#### Сигнатура метода

```objectivec
- (void)setUserEmail:(NSString *_Nonnull)email;
```

<div id="usage-example-2" />

#### Пример использования

<Tabs>
<Tab title="Objective C">

```objectivec
[[AppsFlyerLib shared] setUserEmail:@"name@domain.com"];
```

</Tab>

<Tab title="Swift">

```swift
AppsFlyerLib.shared().setUserEmail("name@domain.com")
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **JavaKotlin**
>
> Передавайте адрес электронной почты в виде обычного текста. SDK нормализует и хеширует его локально (SHA-256). Без предварительного хеширования. За один вызов принимается только один адрес электронной почты: повторный вызов setUserEmail перезаписывает ранее заданное значение, а не добавляет его.

<div id="android-sdk-configuration" />

## Настройка Android SDK (пакет средств разработки ПО)

Чтобы задать хешированный *номер телефона* как дополнительный идентификатор пользователя:

<div id="sdk-v700-and-earlier--setadditionaldata-1" />

### **SDK v7.0.0 и более ранние — setAdditionalData**

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

> 📘 **Note**
>
> **Objective-C Swift**
>
> Перед передачей необходимо предварительно хешировать оба значения (SHA-256).

<div id="sdk-v701-and-later--setuserphone-recommended-1" />

### **SDK v7.0.1 и более поздние — setUserPhone (рекомендуется)**

<div id="method-signature-3" />

#### Аудитории — дополнительные идентификаторы

```java
public abstract void setUserPhone(String countryCode, String phoneNumber);
```

<div id="usage-example-3" />

#### Пример использования

<Tabs>
<Tab title="Java">

```java
AppsFlyerLib.getInstance().setUserPhone("1", "(650) 555-1212");
```

</Tab>

<Tab title="Kotlin">

```java
AppsFlyerLib.getInstance().setUserPhone("1", "(650) 555-1212")
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **Примечание**
>
> Передавайте код страны и местный номер в виде обычного текста. SDK объединяет, нормализует и выполняет хеширование обоих значений локально (SHA-256). Без предварительного хеширования.

Чтобы задать хешированный *адрес электронной почты* как дополнительный идентификатор пользователя:

<div id="sdk-v700-and-earlier-1" />

### **SDK v7.0.0 и более ранние**

<div id="method-signature-4" />

#### SHA256 хеширование

```java
public abstract void setUserEmails(
  AppsFlyerProperties.EmailsCryptType cryptMethod,
  String... emails
);
```

<div id="usage-example-4" />

#### Пример использования

<Tabs>
<Tab title="Java">

```java
AppsFlyerLib.getInstance().setUserEmails(
  AppsFlyerProperties.EmailsCryptType.SHA256,
  "name@domain.com",
  "another_name@another_domain.com"
);
```

</Tab>

<Tab title="Kotlin">

```java
AppsFlyerLib.getInstance().setUserEmails(
  AppsFlyerProperties.EmailsCryptType.SHA256,
  "name@domain.com",
  "another_name@another_domain.com"
);
```

</Tab>
</Tabs>

<div id="sdk-v701-and-later-1" />

### **SDK v7.0.1 и более поздние**

<div id="method-signature-5" />

#### SHA256 хеширование

```java
public abstract void setUserEmail(String email);
```

<div id="usage-example-5" />

#### Пример использования

```java
AppsFlyerLib.getInstance().setUserEmail("name@domain.com");
```

> 📘 **Note**
>
> **Примечание**
>
> В v7.0.1 и более поздних версиях за один вызов принимается только один email. Несколько адресов электронной почты не поддерживаются: повторный вызов setUserEmail перезаписывает ранее заданное значение, а не добавляет его.

<div id="s2s-reference-and-code-samples" />

## Справочник S2S и образцы кода

При отправке идентификаторов для аудиторий через <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> используйте параметр <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">для **всех идентификаторов (включая хешированный *адрес электронной почты*).** Вы можете отправить один или несколько идентификаторов.</Anchor>

<Accordion title="Отправка идентификаторов через S2S">

Формат:

* Вложенный JSON
* Значение ключа должно быть `audiences`
* Все значения должны быть в формате строки, как показано в примере кода ниже.
* Названия параметров должны совпадать с указанными в [таблице доступных идентификаторов](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting) выше.

Общий формат:

```json
"custom_data" : {   
      \"audiences\" : { 
          \"parameter_name_a\" : \"hashed_identifer_a\",
          \"parameter_name_a\" : \"hashed_identifer_b\",
          \"parameter_name_c\" : \"hashed_identifer_c\" 
       }
 }
```

Пример с заполненными полями для хешированного *номера телефона* и хешированного *адреса электронной почты*:

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

> 📘 **Note**
>
> **Смотрите также**
>
> * Аудитории – подключение партнёров
> * Политика идентификаторов пользователей в аудиториях

<div data-zendesk-anchors="background=%D0%BE-%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0%D1%85 h_01HNZNWZ9WVH11NG94P5YX5CE0=%D0%BE-%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0%D1%85 next-steps=%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D1%8E%D1%89%D0%B8%D0%B5-%D1%88%D0%B0%D0%B3%D0%B8 h_01HNZNWZ9WYWFE1TTS3CWEBS8N=%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D1%8E%D1%89%D0%B8%D0%B5-%D1%88%D0%B0%D0%B3%D0%B8 available-identifiers=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B h_01HNZNWZ9XG5P67Y8P08JGFWFD=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B sdk-reference-and-code-samples=%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D1%87%D0%BD%D0%B8%D0%BA-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B8-%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D1%86%D1%8B-%D0%BA%D0%BE%D0%B4%D0%B0 h_01HNZNWZ9X0N0D3EF9HJ76EVNJ=%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D1%87%D0%BD%D0%B8%D0%BA-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B8-%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D1%86%D1%8B-%D0%BA%D0%BE%D0%B4%D0%B0 ios-sdk-configuration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-ios-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE h_01HNZNWZ9XCZFWA7H8BN6J6485=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-ios-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE sdk-v700-and-earlier-%E2%80%94-setadditionaldata=sdk-v700-and-earlier--setadditionaldata h_01KZXZHJZCZ8XNS5Z5JQFGABEJ=sdk-v700-and-earlier--setadditionaldata sdk-v701-and-later-%E2%80%94-setuserphone-recommended=sdk-v701-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D0%BF%D0%BE%D0%B7%D0%B4%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8--setuserphone-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D1%82%D1%81%D1%8F h_01KZXZHSF8PCN9A4425217F4YP=sdk-v701-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D0%BF%D0%BE%D0%B7%D0%B4%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8--setuserphone-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D1%82%D1%81%D1%8F method-signature=sha256-%D1%85%D0%B5%D1%88%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5 h_01KZXZF3GX0HSY4BFYX4N4BTHD=sha256-%D1%85%D0%B5%D1%88%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5 usage-example=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01KZXZF3GXN55TJ078CJKMJGSY=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F sdk-v700-and-earlier=sdk-v700-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D1%80%D0%B0%D0%BD%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8 h_01KZXZJ3MEQPEJ73798RY3S3R9=sdk-v700-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D1%80%D0%B0%D0%BD%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8 method-signature::a8fd9cf9=%D1%81%D0%B8%D0%B3%D0%BD%D0%B0%D1%82%D1%83%D1%80%D0%B0-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0 h_01KZXZF3GX62EV1TTA689CK59F=%D1%81%D0%B8%D0%B3%D0%BD%D0%B0%D1%82%D1%83%D1%80%D0%B0-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0 usage-example::5a156aca=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-1 h_01KZXZF3GXB5VHHYT3SJ60F94V=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-1 sdk-v701-and-later=sdk-v701-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D0%BF%D0%BE%D0%B7%D0%B4%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8 h_01KZXZJ98R1274HPDM9T4RTYDP=sdk-v701-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D0%BF%D0%BE%D0%B7%D0%B4%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8 method-signature::6246e0dd=%D1%81%D0%B8%D0%B3%D0%BD%D0%B0%D1%82%D1%83%D1%80%D0%B0-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-1 h_01KZXZF3GX9R7J1VF0ZFMJKN4Q=%D1%81%D0%B8%D0%B3%D0%BD%D0%B0%D1%82%D1%83%D1%80%D0%B0-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-1 usage-example::b5bfcf61=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-2 h_01KZXZF3GXQ22XRNRP1H0TX1HG=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-2 android-sdk-configuration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-android-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE h_01HNZNWZ9XAF2K6213ZMMGKQ7T=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-android-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE sdk-v700-and-earlier-%E2%80%94-setadditionaldata::6dbf5d0c=sdk-v700-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D1%80%D0%B0%D0%BD%D0%BD%D0%B8%D0%B5--setadditionaldata h_01KZXZJGMVJQAH5XC1BPJS1DGD=sdk-v700-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D1%80%D0%B0%D0%BD%D0%BD%D0%B8%D0%B5--setadditionaldata sdk-v701-and-later-%E2%80%94-setuserphone-recommended::1b63a185=sdk-v701-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D0%BF%D0%BE%D0%B7%D0%B4%D0%BD%D0%B8%D0%B5--setuserphone-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D1%82%D1%81%D1%8F h_01KZXZJX109FSKCCRPVAA1W2Y2=sdk-v701-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D0%BF%D0%BE%D0%B7%D0%B4%D0%BD%D0%B8%D0%B5--setuserphone-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D1%82%D1%81%D1%8F method-signature::bf39fa28=%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B8--%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B h_01KZXZF3GX3Q6MZX5KXQJSANVK=%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B8--%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B usage-example::1515fa60=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-3 h_01KZXZF3GXSXDP4BBFWM7WZ74M=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-3 sdk-v700-and-earlier::5989d839=sdk-v700-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D1%80%D0%B0%D0%BD%D0%BD%D0%B8%D0%B5 h_01KZXZK2H50HJVZKF65H59XVXY=sdk-v700-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D1%80%D0%B0%D0%BD%D0%BD%D0%B8%D0%B5 method-signature::9b0b0248=sha256-%D1%85%D0%B5%D1%88%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01KZXZF3GXZXD09H3T922TGM7N=sha256-%D1%85%D0%B5%D1%88%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-1 usage-example::2bb38341=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-4 h_01KZXZF3GXB7V1YK1584H0NW1G=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-4 sdk-v701-and-later::16b1fdb1=sdk-v701-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D0%BF%D0%BE%D0%B7%D0%B4%D0%BD%D0%B8%D0%B5 h_01KZXZK8EXXVDY8P4TR2418FXH=sdk-v701-%D0%B8-%D0%B1%D0%BE%D0%BB%D0%B5%D0%B5-%D0%BF%D0%BE%D0%B7%D0%B4%D0%BD%D0%B8%D0%B5 method-signature::852458c4=sha256-%D1%85%D0%B5%D1%88%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-2 h_01KZXZF3GXX4S3P8SE4SBY6WZ2=sha256-%D1%85%D0%B5%D1%88%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-2 usage-example::11baa27a=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-5 h_01KZXZF3GXM9Q0MQNX2ASEZ2BJ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-5 s2s-reference-and-code-samples=%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D1%87%D0%BD%D0%B8%D0%BA-s2s-%D0%B8-%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D1%86%D1%8B-%D0%BA%D0%BE%D0%B4%D0%B0 h_01HNZNWZ9XKM53TJ9Z0FHWGCYC=%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D1%87%D0%BD%D0%B8%D0%BA-s2s-%D0%B8-%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D1%86%D1%8B-%D0%BA%D0%BE%D0%B4%D0%B0" />

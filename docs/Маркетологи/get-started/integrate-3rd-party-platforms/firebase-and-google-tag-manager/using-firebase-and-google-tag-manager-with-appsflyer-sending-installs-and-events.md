---
title: >-
  Использование Firebase и Google Менеджера тегов с AppsFlyer — отправка
  установок и событий
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:31:07Z'
  edited_at: '2026-08-18T00:13:14Z'
  id: 4410481550609
  locale: ru
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/ru/articles/4410481550609
---
> **Краткий обзор.** Инструкции по настройке отправки событий через SDK Firebase в AppsFlyer в вашем приложении.

## Настройка событий в приложении

В этом разделе рассказывается о том, как настроить и создать события в приложении с помощью Google Менеджера тегов (GTM).

Когда событие отправлено, GTM проверяет, есть ли тег, настроенный на обработку этого события с помощью триггера события. Триггер события настроен на срабатывание тега при каждой отправке определенного события. Если отправляется определенное событие и у него есть соответствующий триггер, то тег срабатывает. Когда тег срабатывает, Google Менеджер тегов собирает все данные о событии. Такие данные включают идентификатор AppsFlyer, название события и параметры события. После сбора всех данных Google Менеджер тегов отправляет событие в AppsFlyer.

<div id="creating-event-variables-for-revenue-and-price" />

<Accordion title="Создание переменных событий для дохода и цены">

#### Android;

<Tabs>
<Tab title="Java">

1. В классе MainActivity создайте переменные для хранения идентификатора устройства AppsFlyer:  

   ```java
   public static String appsFlyerID;
   ```
2. В классе MainActivity в методе `onCreate` и после `super.onCreate` передайте идентификатор AppsFlyer в переменную:

   ```java
   appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
   ```

</Tab>

<Tab title="Kotlin">

1. В классе MainActivity создайте переменную для хранения идентификатора устройства AppsFlyer:  

   ```kotlin
   var appsFlyerID: String? = пусто
   ```
2. В классе MainActivity, в методе `onCreate` и после `super.onCreate` передайте значение AppsFlyer ID в переменную:

   ```kotlin
   override fun onCreate(savedInstanceState: Bundle?) {
    ... {
    ...
    appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this)
   }
   ```

</Tab>
</Tabs>

#### https://support.appsflyer.com/hc/article_attachments/360016192917

Для iOS параметры доступны во всем приложении. Вы можете получить их с помощью экземпляра AppsFlyerTracker.

<Tabs>
<Tab title="Objective-C">

1. Идентификатор устройства AppsFlyer —

   ```objectivec
   [AppsFlyerTracker sharedTracker].getAppsFlyerUID
   ```
2. Идентификатор приложения Apple —

   ```objectivec
   [AppsFlyerTracker sharedTracker].appleAppID
   ```

</Tab>

<Tab title="Swift">

1. Идентификатор устройства AppsFlyer —

   ```swift
    AppsFlyerTracker.shared().getAppsFlyerUID()
   ```
2. Идентификатор приложения Apple —

   ```swift
   AppsFlyerTracker.shared().appleAppID
   ```

</Tab>
</Tabs>

</Accordion>

<div id="adding-events-in-the-app" />

<Accordion title="Добавление событий в приложение">

Первым делом нужно настроить событие в приложении. Событие отправляется с помощью Firebase Event Logging. В событии вы указываете идентификатор AppsFlyer, название события и параметры события. Идентификатор AppsFlyer извлекается из переменной, созданной в <Anchor target="_blank" href="/marketers/ru/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup#настройка-google-tag-manager">ходе настройки</Anchor>.

<Anchor target="_blank" href="https://developers.google.com/tag-manager/ios/v5/#log-events-and-variables">Google Менеджер тегов использует аналитику событий Firebase</Anchor> для срабатывания событий тега. Когда событие отправляется в Firebase, Менеджер тегов распознает событие и отправляет его также в AppsFlyer.

#### Android;

<Tabs>
<Tab title="Java">

1. В нужной активности добавьте оператор import для Firebase:  

   ```java
   import com.google.firebase.analytics.FirebaseAnalytics;
   ```
2. Добавьте следующий код, который будет выполняться при каждом возникновении события покупки:

   ```java
   Bundle bundle = new Bundle();
     // обратите внимание на "af_id" — это имя параметра события 
     // для идентификатора AppsFlyer ID, который мы создали на предыдущем шаге
     bundle.putString("af_id", appsFlyerID);
     bundle.putString("af_revenue", "200");
     bundle.putString("af_price", "250");
     mFirebaseAnalytics.logEvent("af_purchase", bundle);
   ```

</Tab>

<Tab title="Kotlin">

1. В нужной активности добавьте оператор import для Firebase:  

   ```kotlin
   import com.google.firebase.analytics.FirebaseAnalytics
   ```
2. Добавьте следующий код, который будет выполняться при каждом возникновении события покупки:

   ```kotlin
   val bundle = Bundle()
     // обратите внимание на "af_id" — это имя параметра события
     // для идентификатора AppsFlyer ID, который мы создали на предыдущем шаге
     bundle.putString("af_id", appsFlyerID)
     bundle.putString("af_revenue", "200")
     bundle.putString("af_price", "250")
     FirebaseAnalytics.getInstance(this).logEvent("af_purchase", bundle)
   ```

</Tab>
</Tabs>

https://support.appsflyer.com/hc/article_attachments/360016192917

<Tabs>
<Tab title="Objective-C">

1. В представление, куда отправляется событие, добавьте `@import Firebase`
2. Добавьте следующий код, который будет выполняться при каждом возникновении события покупки:

   ```objectivec
   NSString *id_prefix = @"id";  
   NSString *apple_app_id = [id_prefix stringByAppendingString:[AppsFlyerTracker sharedTracker].appleAppID];  

   [FIRAnalytics logEventWithName:@"af_purchase"
         parameters:@{
          @"apple_app_id": apple_app_id,
          @"af_id": [AppsFlyerTracker sharedTracker].getAppsFlyerUID,
          @"af_revenue": @250,
          @"af_price": @375
       }];
   ```

</Tab>

<Tab title="Swift">

1. В представление, куда отправляется событие, добавьте `import Firebase`
2. Добавьте следующий код, который будет выполняться при каждом возникновении события покупки:

   ```swift
   Analytics.logEvent("af_purchase", parameters: [
          "apple_app_id": "id" + AppsFlyerTracker.shared().appleAppID,
          "af_id": AppsFlyerTracker.shared().getAppsFlyerUID(),
          "af_revenue": 250,
          "af_price": 375
       ]);
   ```

</Tab>
</Tabs>

</Accordion>

## Отправка событий установки в Firebase

Вы также можете отправлять события установки в Firebase со всеми данными, связанными с установкой.

#### Android;

<Tabs>
<Tab title="Java">

Чтобы отправить события установки в Firebase на Android, вы можете использовать объект `conversionData`.

#### Создание метода отправки события

Добавьте следующий метод в класс `AFApplication` сразу под методом `onCreate`:

```java
public void sendInstallToFirebase(Map<String, String> conversionData){
       mFirebaseAnalytics = FirebaseAnalytics.getInstance(this);
       Bundle bundle = new Bundle();
       bundle.putString("install_time", conversionData.get("install_time") == null ? String.valueOf(new Date().getTime()) : conversionData.get("install_time"));
       bundle.putString("click_time", conversionData.get("click_time"));
       bundle.putString("media_source", conversionData.get("media_source") == null ? "organic": conversionData.get("media_source"));
       bundle.putString("campaign", conversionData.get("campaign") == null ? "organic": conversionData.get("campaign"));
       bundle.putString("install_type", conversionData.get("af_status"));
       mFirebaseAnalytics.logEvent("install", bundle);
    }
```

Этот метод принимает объект `conversionData`. Метод проверяет, есть ли значение NULL для параметров «Время установки», «Медиа-источник» и «Кампания», и если да, то устанавливает для времени установки текущее время, а медиа-источник и кампанию как органические. В противном случае метод берет данные из объекта `conversionData` и отправляет их в Firebase.

#### Отправка события установки

Добавьте следующий код в метод `onConversionDataSuccess`:

```java
if(conversionData.get("is_first_launch").equals("true")){
       sendInstallToFirebase(conversionData);
    }
```

Этот код проверяет, запускается ли приложение впервые. Если это так, он вызывает метод `sendInstallToFirebase`.

</Tab>

<Tab title="Kotlin">

Чтобы отправить события установки в Firebase на Android, вы можете использовать объект `conversionData`.

#### Создание метода отправки события

Добавьте следующий метод в класс `AFApplication` сразу под методом `onCreate`:

```kotlin
fun sendInstallToFirebase(conversionData: Map<String, Any>) {
      val bundle = Bundle()
      bundle.putString("install_time", conversionData["install_time"]?.toString() ?: Date().time.toString())
      bundle.putString("click_time", conversionData["click_time"]?.toString())
      bundle.putString("media_source", conversionData["media_source"]?.toString() ?: "organic")
      bundle.putString("campaign", conversionData["campaign"]?.toString() ?: "organic")
      bundle.putString("install_type", conversionData["af_status"]?.toString())
      FirebaseAnalytics.getInstance(this).logEvent("install", bundle)
  }
```

Этот метод принимает объект `conversionData`. Метод проверяет, есть ли значение NULL для параметров «Время установки», «Медиа-источник» и «Кампания», и если да, то устанавливает для времени установки текущее время, а медиа-источник и кампанию как органические. В противном случае метод берет данные из объекта `conversionData` и отправляет их в Firebase.

#### Отправка события установки

Добавьте следующий код в метод `onConversionDataSuccess`:

```kotlin
if(conversionData?.get("is_first_launch") == true){
      sendInstallToFirebase(conversionData);
  }
```

Этот код проверяет, запускается ли приложение впервые. Если это так, он вызывает метод `sendInstallToFirebase`.

**Примечание:** Начиная с SDK V5, `onConversionDataSuccess` — название метода получения данных о конверсиях. Если вы используете версию SDK ниже 5.0.0, имя метода — `onInstallConversionDataLoaded`. Мы рекомендуем обновить SDK до версии 5.0.0. Подробнее см. <Anchor target="_blank" href="/marketers/ru/docs/links-to-appsflyer-sdk-release-notes">здесь</Anchor>.

</Tab>
</Tabs>

#### https://support.appsflyer.com/hc/article_attachments/360016192917

<Tabs>
<Tab title="Objective-C">

#### Создание метода отправки события

В AppDelegate.m добавьте следующий метод в конец файла:

```objectivec
- (void)sendInstallToFirebase:(NSDictionary *)installData{
      NSDateFormatter *dateFormatter = [[NSDateFormatter alloc] init];
      [dateFormatter setDateFormat:@"dd/MM/yyyy HH:mm:ss"];
      NSDate *date = [NSDate date];
      NSString *newDate = [dateFormatter stringFromDate:date];

      if([[installData objectForKey: @"af_status"] isEqual: @"Organic"]){
        [FIRAnalytics logEventWithName:@"install"
         parameters:@{
          @"install_time": newDate,
          @"media_source": @"organic",
          @"campaign": @"organic"

        }];
      }
      else {
        [FIRAnalytics logEventWithName:@"install"
          parameters:@{
          @"install_time": [installData objectForKey: @"install_time"],
          @"click_time": [installData objectForKey: @"click_time"],
          @"install_type": [installData objectForKey: @"af_status"],
          @"media_source": [installData objectForKey: @"media_source"],
          @"campaign": [installData objectForKey: @"campaign"]
        }];
      }
    }
```

Этот метод получает объект `installData` и проверяет, является ли установка органической или нет. Если она органическая, метод устанавливает время установки на текущее время, а медиа-источник, кампанию и тип установки — на органические.

Если установка является неорганической, метод получает соответствующие данные о неорганических установках.

После установки параметров метод отправляет событие установки в Firebase.

#### Отправка события установки

В AppDelegate.m в методе `didFinishLaunchingWithOptions` добавьте `[FIRApp configure]`

В AppDelegate.m в методе `onConversionDataSuccess` добавьте следующий код в конец метода:

```objectivec
if([installData objectForKey:@"is_first_launch"]){
      [self sendInstallToFirebase: installData];
    }
```

Приведенный выше фрагмент кода проверяет, запускается ли приложение впервые. Если это так, он вызывает метод `sendInstallToFirebase`.

</Tab>

<Tab title="Swift">

В AppDelegate.swift добавьте следующий метод в конец файла:

```swift
func sendInstallToFirebase(_ installData: [AnyHashable : Any]!){

        let date = Date()
        let dateFormatter = DateFormatter()
        dateFormatter.dateFormat = "dd/MM/yyyy hh:mm:ss"
        let _newDate: String = dateFormatter.string(from: date)

        if(installData["af_status"] as? String == "Organic"){
          Analytics.logEvent("install", parameters: [
            "install_time": _newDate,
            "media_source": "organic",
            "campaign": "organic"
          ]);
        } else {
          Analytics.logEvent("install", parameters: [
            "install_time": installData["install_time"],
            "click_time": installData["click_time"],
            "media_source": installData["media_source"],
            "campaign": installData["campaign"],
            "install_type": installData["af_status"]
          ]);
        }

      }
```

**Примечание:** Начиная с SDK V5, `onConversionDataSuccess` — название метода получения данных о конверсиях. Если вы используете версию SDK ниже 5.0.0, имя метода — `onConversionDataReceived`. Мы рекомендуем обновить SDK до версии 5.0.0. Подробнее см. <Anchor target="_blank" href="/marketers/ru/docs/links-to-appsflyer-sdk-release-notes">здесь</Anchor>.

Этот метод принимает объект `installData` и проверяет, является ли установка органической или нет. Если она органическая, метод устанавливает время установки на текущее время, а медиа-источник, кампанию и тип установки — на органические.

Если установка является неорганической, метод получает соответствующие данные о неорганических установках.

После установки параметров метод отправляет событие установки в Firebase.

#### Отправка события установки

В AppDelegate.swift в методе `didFinishLaunchingWithOptions` добавьте `FirebaseApp.configure();`

В AppDelegate.swift в методе `onConversionDataSuccess` добавьте следующий код в конец метода:

```swift
if let is_first_launch = data["is_first_launch"] , let launch_code = is_first_launch as? Int {
      if(launch_code == 1){
        print("Первый запуск")
        sendInstallToFirebase(installData)
      } else {
        print("Не первый запуск")
      }
    }
```

**Примечание:** Начиная с SDK V5, `onConversionDataSuccess` — название метода получения данных о конверсиях. Если вы используете версию SDK ниже 5.0.0, имя метода — `onConversionDataReceived`. Мы рекомендуем обновить SDK до версии 5.0.0. Подробнее см. <Anchor target="_blank" href="/marketers/ru/docs/links-to-appsflyer-sdk-release-notes">здесь</Anchor>.

Приведенный выше фрагмент кода проверяет, запускается ли приложение впервые. Если это так, он вызывает метод `sendInstallToFirebase`.

</Tab>
</Tabs>

> ❗️ **Предупреждение**
>
> Некоторые медиа-источники не разрешают делиться своими данными со сторонними платформами и сервисами. Если вы работаете с такими партнерами, как Meta ads, Twitter, Snap, Pinterest и др., которые устанавливают ограничения на передачу своих данных на сторонние платформы и сервисы, обязательно **следуйте их указаниям и удаляйте данные, которые подпадают под эти ограничения**.
>
> * <Anchor target="_blank" href="https://www.facebook.com/privacy/policy/">Политика данных Meta ads</Anchor>
> * <Anchor target="_blank" href="https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html">Политика данных Twitter</Anchor>
> * <Anchor target="_blank" href="https://www.snap.com/en-US/privacy/privacy-policy/">Политика данных Snapchat</Anchor>
> * <Anchor target="_blank" href="https://policy.pinterest.com/en/privacy-policy">Политика данных Pinterest</Anchor>

<div data-zendesk-anchors="configuring-events-in-the-app=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 01H8H2MH93M1SB9HEQNHDDJZP0=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 01H8H2MH93D36ZH7788XCMHHV6=creating-event-variables-for-revenue-and-price 01H8H2MH93RNWN6N6EWE5T26V1=android ios=httpssupportappsflyercomhcarticle_attachments360016192917 01H8H2MH93CZ5TACG3MWJ8YRFK=httpssupportappsflyercomhcarticle_attachments360016192917 01H8H2MH9340PQCCKB85BQZQEG=adding-events-in-the-app android::eb294e42=android-1 01H8H2MH9357Z5M1DBK4Z9N22P=android-1 sending-install-events-to-firebase=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%B2-firebase 01H8H2MH930VDZH5YSWEPTS8BN=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%B2-firebase android::319436d3=android-2 01H8H2MH938Y980A9KA9BPP44Y=android-2 creating-the-send-event-method=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F 01H8H2MH932WYSS6Z5NZJ3195X=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F sending-the-install-event=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 01H8H2MH93H0WKMV5DAN713EY0=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 creating-the-send-event-method::64b5a305=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F 01H8H2MH93VYXGMM5H6ZQWCFZY=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F sending-the-install-event::aeb9cdb7=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 01H8H2MH93VTPZNF51R05QPK7C=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 ios::95ad6e27=httpssupportappsflyercomhcarticle_attachments360016192917-1 01H8H2MH93AQE7PKVW4QKD2ARN=httpssupportappsflyercomhcarticle_attachments360016192917-1 creating-the-send-event-method::346138b1=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-2 01H8H2MH93NGBRHBDQTX4DKNTY=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-2 sending-the-install-event::aca3c0e3=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-2 01H8H2MH93SWYFF2KTC1HJ06FF=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-2 sending-the-install-event::b6997ad3=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-2 01H8H2MH93Y5J8QH0YBKPQSV5N=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-2 01H8H2MH93JQBAR6ZTW77HHFQR=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5" />

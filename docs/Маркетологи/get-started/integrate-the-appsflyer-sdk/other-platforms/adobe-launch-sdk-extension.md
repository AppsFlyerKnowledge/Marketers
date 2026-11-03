---
title: Расширение для SDK Adobe Launch
metadata:
  keywords:
    - SDK
    - Adobe
    - Advertisers
    - AppsFlyer SDK
    - Adobe Experience Platform
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
  created_at: '2019-02-13T08:03:45Z'
  edited_at: '2026-08-18T00:15:26Z'
  id: 360000939097
  locale: ru
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/ru/articles/360000939097
---
> **At a glance:** Выберите или введите сопоставленные данные о конверсиях AppsFlyer и выберите предпочтительный вариант ***Persistence*** (Хранение данных).

## Обзор

Adobe Launch SDK является неотъемлемой частью платформы Adobe Experience Platform. Adobe Experience Platform помогает компаниям собирать, консолидировать и анализировать данные из различных приложений и платформ. Она позволяет владельцам бизнеса и разработчикам лучше понять поведение клиентов, чтобы оптимизировать опыт и доставку контента. Если ваше приложение использует и Adobe Launch SDK, и AppsFlyer SDK, вы можете отправлять данные на обе платформы с помощью одной реализации **AppsFlyer Adobe Launch SDK Extension**. Это снижает общую сложность процесса разработки и делает кодовую базу более чистой и удобной для обслуживания.

> 📘 **Note**
>
> **Примечание**
>
> Если вы используете расширение Adobe Launch, нет необходимости в стандартной <Anchor target="_blank" href="/marketers/ru/docs/adobe-analytics-integration-with-appsflyer">интеграции Adobe Analytics</Anchor>.

## Необходимые условия

Перед интеграцией расширения AppsFlyer Adobe SDK необходимо выполнить несколько действий.

<Accordion title="Получение ключа разработчика AppsFlyer (dev key)">

![dev_key.png](https://files.readme.io/bf25b5d583f3eaab57c230b68764f08c49806a50401955a511993d8a847e7d42-360006050318.png)

1. На дэшборде вашего приложения нажмите ***Настройки приложения*** в разделе ***Конфигурация*** в левом меню.
2. В разделе ***Установка SDK***скопируйте ***Ключ разработчика***.

</Accordion>

<Accordion title="Получите идентификатор приложения">

* Для Android ID приложения — это имя пакета, например example.com.app.
* Для iOS ID приложения — это ID приложения в iTunes без префикса *id*, например 123456748.

</Accordion>

## Примечание

Для настройки Adobe Launch следуйте приведенным здесь инструкциям.

<Accordion title="1.1 Создание нового свойства в Adobe Launch">

![Примечание](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)

1. Войдите в Adobe Experience Cloud.
2. Выберите ***Launch*** (Запуск).
3. Нажмите ***Go to Launch*** (Перейти к запуску).
4. Нажмите ***New Property*** (Новое свойство).
5. Дайте свойству имя и выберите ***Mobile*** (Мобильный).
6. Нажмите кнопку ***Save*** (Сохранить)

</Accordion>

<Accordion title="1.2 Установка необходимых расширений Adobe Launch">

Установите следующие расширения в Adobe Launch:

![adboe_extensions.png](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)

* Adobe Analytics соединяет записанные данные из SDK с модулем Adobe Analytics.
* AppsFlyer SDK Extension отправляет данные и события в Adobe и AppsFlyer с помощью Adobe Launch SDK.
* Adobe Profile позволяет SDK сохранять данные в профиле на стороне клиента.
* Adobe Mobile Core позволяет настраивать мобильный SDK и предоставляет доступ к событиям и условиям жизненного цикла по умолчанию.

#### Установка расширения Adobe Analytics

1. Войдите в Adobe Analytics.
2. <Anchor target="_blank" href="https://docs.adobe.com/help/en/analytics/admin/admin-console/create-report-suite.html">Создайте набор отчетов</Anchor>.
3. Снова войдите в Adobe Launch.
4. В списке свойств нажмите на свойство, которое вы создали ранее.
5. Нажмите ***Extensions*** (Расширения).
6. Найдите и установите ***Adobe Analytics***.
7. Под ***Наборами отчетов***укажите набор отчетов, который вы создали в шаге 2.
8. Нажмите кнопку ***Save*** (Сохранить)

#### Установка расширения AppsFlyer SDK

1. Выберите ***Расширения*** снова.
2. Найдите и установите ***AppsFlyer SDK Extension***.
3. В разделе ***AppsFlyer iOS App ID*** укажите идентификатор приложения для iOS, который вы получили на этапе предварительных условий.
4. В разделе ***AppsFlyer Dev Key*** укажите ключ разработчика, полученный на этапе предварительных условий.
5. Включите ***Отправка данных об атрибуции в Adobe Analytics***. Обратите внимание, что существуют некоторые <Anchor target="_blank" href="/marketers/ru/docs/user-level-data-retention">ограничения на передачу данных на уровне пользователя сторонним аналитическим платформам</Anchor>.
6. Нажмите кнопку ***Save*** (Сохранить)

#### Установите расширение Profile и Mobile Core

1. Выберите ***Расширения*** снова.
2. Найдите и установите ***Профиль***.
3. Найдите и установите ***Mobile Core***.
   * При установке Mobile Core просто сохраните расширение как есть. Нет необходимости указывать ***Experience Cloud Server*** (Сервер Experience Cloud).

</Accordion>

## Выберите вкладку ***Custom Variables*** (Пользовательские переменные) и настройте переменные для сопоставления данных AppsFlyer SDK с данными системы Adobe.

Следуйте инструкциям в этом разделе, чтобы внедрить расширение Adobe SDK в свое приложение.

<Accordion title="2.1 Добавление SDK в приложение">

![adobe_sdk.png](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)

1. Внутри свойств Adobe выберите ***Environments*** (Среды).
2. Выберите среду, для которой вы хотите развернуть SDK.
3. С правой стороны нажмите на значок коробки.
4. Скопируйте фрагменты кода из открывшегося окна и следуйте инструкциям. Если вы маркетолог, настраивающий Adobe, отправьте эти фрагменты кода своему разработчику приложений.

</Accordion>

<Accordion title="2.2 Публикация среды">

Чтобы завершить реализацию SDK, необходимо опубликовать среду в библиотеке.

![adobe_publishing.png](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)

1. Внутри свойств Adobe выберите ***Publishing*** (Публикация).
2. Нажмите ***Add New Library*** (Добавить новую библиотеку).
3. Дайте ей имя и в разделе "Environment" выберите ***Development*** (Разработка).
4. Нажмите ***Save & Build for Development*** (Сохранить и собрать для разработки).
5. После завершения сборки в разделе ***Development***нажмите на три точки рядом с библиотекой и выберите ***Submit for Approval*** (Отправить на утверждение).
6. В разделе ***Submitted*** (Отправленные) нажмите на три точки рядом с библиотекой и выберите ***Build for Staging*** (Собрать для стейджинга).
7. Когда сборка завершится, нажмите на три точки рядом с библиотекой и выберите ***Approve for Publishing*** (Утвердить для публикации).
8. Под кнопкой ***Утвердить***нажмите на три точки рядом с библиотекой и выберите ***Build & Publish to Production*** (Собрать и опубликовать в продакшн).

</Accordion>

<Accordion title="2.3 Добавление реферера установки для Android к вашему приложению">

Инициатор установки для Android повышает точность атрибуции, защищает от мошеннических установок, а также выполняет другие функции. Его поддержка в SDK AppsFlyer для Android предусмотрена начиная с версии 4.8.6.

> 📘 **Note**
>
> **Примечание**
>
> Google прекратил поддержку [BroadcastReceiver](https://android-developers.googleblog.com/2019/11/still-using-installbroadcast-switch-to.html)в марте 2020 г.
>
> * Это изменение не влияет на приложение.
> * Возможно, вам по-прежнему понадобится BroadcastReceiver для атрибуции приложений, установленных не из магазина. Проверьте это в магазине, в котором зарегистрировано приложение.
> * Внедрение инициатора установки теперь является обязательным.

Добавить инициатор установки в приложение можно двумя способами:

* С помощью системы Gradle (рекомендуется)
* Добавление инициатора установки вручную

<Tabs>
<Tab title="Добавление реферера установки с помощью Gradle">

Добавьте инициатор установки для Android как зависимость. Загрузить последнюю версию можно <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">здесь</Anchor>.

1.
   ```java
   dependencies {
   //убедитесь, что используете последнюю версию SDK: https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk
   	implementation 'com.appsflyer:af-android-sdk:5.+'
   	implementation 'com.android.installreferrer:installreferrer:1.1'
   }
   ```
2. Синхронизируйте проект для получения зависимостей — см. снимок экрана ниже:![android_af_sdk_sync_gradle.png](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)

Разработчикам, которые используют утилиту ProGuard и хотят использовать новый API для реферера от Google, необходимо добавить в ProGuard такое правило:`-dontwarn com.android.installreferrer`

</Tab>

<Tab title="Добавление инициатора установки с помощью Gradle Добавление инициатора установки вручную">

1. <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">Загрузите файл реферера установки в формате aar.</Anchor>
2. <Anchor target="_blank" href="https://stackoverflow.com/questions/16682847/how-to-manually-include-external-aar-package-using-new-gradle-android-build-syst">Добавьте его в проект.</Anchor>
3. Добавьте следующее разрешение в манифест: `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE`

</Tab>
</Tabs>

</Accordion>

<Accordion title="2.4. Настройка необходимых разрешений">

Добавление разрешения повышает показатель <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">атрибуции на основе вероятностного моделирования</Anchor>. Кроме того, это позволяет SDK отправлять больше данных, таких как данные WiFi и сети оператора связи. Эти данные можно получать из <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview">отчетов по сырым данным</Anchor> и использовать для анализа и оптимизации кампаний.

#### Добавление необходимых разрешений

1. Добавьте в файл AndroidManifest.xml эти разрешения:  

   ```html Markup
   <uses-permission android:name="android.permission.INTERNET" />
   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
   <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
   <!-- Необязательно: -->
   <uses-permission android:name="android.permission.READ_PHONE_STATE" />
   ```

</Accordion>

## Использование расширения Adobe SDK

Теперь вы можете начать использовать расширение Adobe SDK для отправки данных в Adobe и AppsFlyer.

> 📘 **Note**
>
> **Примечание**
>
> В настоящее время расширение Adobe Launch SDK поддерживает только получение данных о конверсиях и отправку событий. Однако, когда вы добавляете расширение Adobe Launch SDK в свое приложение, AppsFlyer SDK также добавляется. Таким образом, любая функциональность, отсутствующая в расширении Adobe SDK, может быть реализована с помощью AppsFlyer SDK.

<Accordion title="Отправка событий">

Отслеживая события внутри приложения, можно понять, что в нем происходит. Рекомендуется заранее определить, какие события нужно регистрировать. Регистрация внутренних событий приложения позволит измерять такие KPI, как ROI (окупаемость инвестиций) и LTV (суммарная прибыль от пользователя).

Расширение Adobe Launch SDK позволяет отправлять данные о событиях в приложении как в Adobe, так и в AppsFlyer. Затем вы можете использовать Adobe Analytics для анализа поведения пользователей и AppsFlyer для анализа ROI и LTV.

<Tabs>
<Tab title="Android;">

```java
final Map<String,String> eventMap = new HashMap<>();  
eventMap.put("currency", "USD");  
eventMap.put("revenue", "200");  
eventMap.put("freehand", "param");

MobileCore.trackAction("af_purchase", eventMap);
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

```java
[ACPCore trackAction:@"af_purchase" data:@{@"revenue":@"200",@"currency":@"USD"}];
```

</Tab>
</Tabs>

Отправка событий, как указано в приведенном выше коде, создает на дэшборде AppsFlyer событие af\_purchase с доходом в 200 долларов. Это событие также отправляется и отображается в Adobe Analytics.

Все <Anchor target="_blank" href="https://dev.appsflyer.com/docs/direct-deep-linking-1">данные о конверсиях</Anchor>, отправляемые вместе с событиями, имеют префикс ***appsflyer***. Подробнее см. в таблице ниже.

| Переменные в префиксах данных о конверсиях |
| --- |
| appsflyer.af\_click\_lookback |
| appsflyer.install\_time |
| appsflyer.cost\_cents\_USD |
| appsflyer.media\_source |
| appsflyer.af\_adset |
| appsflyer.click\_time |
| appsflyer.orig\_cost |
| appsflyer.campaign |

Данные конверсии доступны в Analysis Workspace в Adobe Analytics. Дополнительные сведения о переносе правил обработки Adobe Mobile Services в Adobe Analytics см. [в документации Adobe](https://experienceleague.adobe.com/en/docs/analytics/technotes/migrate-mobile).

</Accordion>

<Accordion title="Получение данных для диплинкинга и отложенного диплинкинга.">

Диплинкинг и отложенный диплинкинг позволяют улучшить пользовательский опыт. Они позволяют открывать приложение при определенных действиях и настраивать контент в соответствии с данными кампании.

Чтобы получить данные из диплинка, реализуйте обратные вызовы расширения.

<Tabs>
<Tab title="Android;">

В глобальном классе application выполните следующий код:

```java
AppsFlyerAdobeExtension.registerAppsFlyerExtensionCallbacks(new AppsFlyerExtensionCallbacksListener() {
		@Override
		public void onCallbackReceived(Map<String, String> callback) {
			Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			if(callback.get("callback_type").equals("onConversionDataReceived")){
				// conversion data returned 
				if(callback.get("is_first_launch").equals("true")){
					String af_status = callback.get("af_status");
					if(af_status.equals("Non-organic")){
						Log.d(AppsFlyerLibCore.LOG_TAG, "this is first launch and a non organic install!");
					}
				}
			} else if(callback.get("callback_type").equals("onAppOpenAttribution")){
				// direct deeplink - redirect user
				Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			}
		}
		@Override
		public void onCallbackError(String errorMessage) {
			Log.d("TAG", errorMessage);
		}
	});
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

В файле AppDelegate.m выполните следующий код:

```objectivec
[AppsFlyerAdobeExtension registerCallbacks:^(NSDictionary *dictionary) {
        NSLog(@"[AppsFlyerAdobeExtension] Received callback: %@", dictionary);
        if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onConversionDataReceived"]){
            if([[dictionary objectForKey:@"is_first_launch"] boolValue] == YES){
                NSString* af_status = [dictionary objectForKey:@"af_status"];
                if([af_status isEqualToString:@"Non-organic"]){
                    NSLog(@"this is first launch and a non organic install!");
                }
            }
        } else if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onAppOpenAttribution"]) {
            NSLog(@"onAppOpenAttribution Received");
        }
     }];
    [AppsFlyerAdobeExtension callbacksErrorHandler:^(NSError *error) {
          NSLog(@"[AppsFlyerAdobeExtension] Error receiving callback: %@" , error);
    }];
```

</Tab>
</Tabs>

</Accordion>

## Подключение данных о конверсиях AppsFlyer

Данные о конверсии отправляются вместе с событиями на платформу Adobe. Эти переменные позволяют применять логику и правила к измерениям, метрикам или фильтрам отчетности.

1. Войдите в систему <Anchor target="_blank" href="https://mobilemarketing.adobe.com">Adobe Mobile Services</Anchor>.

   ![adobe_analytics.png](https://files.readme.io/d56f170695893dbbde00c50c838ce8a5c2cfe418a17692f372e208d458ed2d6c-31205379096465.png)
2. Перейдите в **Admin** > **Report Suites**
3. Выберите набор отчетов, настроенный во время внедрения Adobe Analytics.
4. Выберите соответствующее приложение и войдите на страницу ***Manage Variables & Metrics*** (Управление переменными и метриками).
5. Создайте правила обработки, чтобы сопоставить переменные AppsFlyer Context Data с eVars.

См. следующую таблицу для сопоставления переменных контекста AppsFlyer:

| **Рекомендуемое название для сопоставления** | **Данные о конверсиях** |
| --- | --- |
| Окно атрибуции AppsFlyer | appsflyer.af\_click\_lookback |
| Время установки AppsFlyer | appsflyer.install\_time |
| Стоимость в AppsFlyer в центах доллара США | appsflyer.cost\_cents\_USD |
| Медиа-источник AppsFlyer | appsflyer.media\_source |
| Группа объявлений AppsFlyer | appsflyer.af\_adset |
| Время клика AppsFlyer | appsflyer.click\_time |
| Первоначальная стоимость AppsFlyer | appsflyer.orig\_cost |
| Кампания AppsFlyer | appsflyer.campaign |

### Использование данных о конверсии, сопоставленных с AppsFlyer, для аналитики и анализа

Все данные, поступающие из SDK, доступны в пакете отчетов Adobe Analytics, который подключен к приложению.

Вы можете использовать данные и связанные с ними показатели и метрики в созданных отчетах и панелях Adobe Analytics. Эти данные также доступны на дэшборде AppsFlyer для атрибуции и анализа событий в приложении.
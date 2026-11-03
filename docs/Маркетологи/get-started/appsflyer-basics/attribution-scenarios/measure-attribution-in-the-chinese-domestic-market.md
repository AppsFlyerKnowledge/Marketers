---
title: Измерение атрибуции на внутреннем рынке Китая
metadata:
  keywords:
    - Advertisers
    - China
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
  created_at: '2019-07-17T12:33:29Z'
  edited_at: '2026-08-28T00:09:17Z'
  id: 360002049858
  locale: ru
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ru/articles/360002049858
---
> **Кратко:** атрибуция устройств Android без GAID с использованием OAID или IMEI. Практические рекомендации по просмотру данных атрибуции в AppsFlyer.

## Атрибуция приложений Android на внутреннем рынке Китая

В Китае владельцы приложений сталкиваются с рядом проблем:

* Сервисы Google Play (GPS) не активны на большинстве устройств Android, а значит, на них нет GAID.
* Использование сторонних магазинов приложений Android создает возможности для перехвата магазинов производителями устройств.
* Серверы атрибуции недоступны или отвечают медленно.
* Управление данными атрибуции из Google Play и сторонних магазинов приложений Android и их просмотр.

Используя AppsFlyer, эти проблемы можно решить следующим образом:

* Реализация атрибуции на основе <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-knowledge-base-glossary#o">OAID</Anchor>
* Использование IMEI устройства в качестве альтернативы GAID на устройствах с Android версии 28 или более ранней
* Подготовка APK с уникальными идентификаторами для обнаружения перехвата магазинов Android
* Настройка ссылок атрибуции, распознаваемых в Китае

## Подготовка приложения

Интегрируйте SDK в приложение и подготовьте APK одним из способов в зависимости от версии Android на целевых устройствах.

<div id="integrate-the-sdk-in-the-app" />

<Accordion title="Интегрируйте SDK в приложение">

**Используйте IMEI и/или OAID вместо GAID**

Как правило, сервисы Google Play не устанавливаются на устройства Android, поставляемые в Китае. Это означает, что нет GAID, который можно использовать как уникальный идентификатор атрибуции.

Альтернативой использованию GAID могут быть IMEI и/или OAID, если они доступны, для обеспечения записи атрибуции.

**OAID:**

* Это рекламный идентификатор, который пользователь может сбросить, аналогичный GAID и IDFA.
* Требуется AppsFlyer Android SDK версии 5.1.0 или более поздней.
* Начиная с AppsFlyer SDK V5.4.0, SDK по умолчанию будет автоматически пытаться собирать OAID.
* Несколько производителей завершили тестирование совместимости атрибуции OAID с AppsFlyer. <Anchor target="_blank" href="/marketers/ru/docs/android-oaid-implementation-in-the-sdk">В том числе Huawei, Lenovo, OPRO, Vivo, Samsung и Xiaomi,</Anchor>

**IMEI**:

* SDK AppsFlyer блокирует доступ к IMEI, если не настроено иначе. Обычно предполагается, что на устройстве активны сервисы Google Play и IMEI не требуется. В Китае это не так.
* При интеграции SDK AppsFlyer в приложение необходимо включить доступ к IMEI.
* При необходимости OAID и IMEI следует реализовать одновременно, чтобы обеспечить атрибуцию независимо от версии Android.
* Это связано с тем, что доступ к IMEI ограничен начиная с <Anchor target="_blank" href="https://developer.android.com/training/articles/user-data-ids">Android 10 (API level 29)</Anchor>, выпущенного в конце 2019 года. Ни ваше приложение, ни SDK AppsFlyer не могут собирать эти идентификаторы. Если идентификатор недоступен, AppsFlyer использует <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">атрибуцию на основе вероятностного моделирования.</Anchor>

**Прежде чем начать**:

* Требуется AppsFlyer Android SDK версии 5.1.0 или более поздней.

Используйте одну из следующих процедур:

<div id="oaid-starting-from-android-api-level-29" />

<Accordion title="OAID начиная с Android API уровня 29">

Есть два метода сбора OAID:

* setCollectOaid
* setOaidData

<Anchor target="_blank" href="/marketers/ru/docs/android-oaid-implementation-in-the-sdk#msa-sdk">Инструкции по включению методов API</Anchor>

</Accordion>

<div id="imei-android-api-level-2328" />

<Accordion title="IMEI Android API уровня 23–28">

Есть два метода сбора IMEI:

* setImeiData
* setCollectIMEI(true)

Используйте следующий пример кода для интеграции SDK. В этом примере кода используется метод `onConversionDataSuccess`. Это название метода для получения данных конверсии, начиная с SDK V5. Если вы используете версию SDK ниже V5, название метода — `onInstallConversionDataLoaded`. Мы рекомендуем обновить SDK до <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">текущей версии.</Anchor>

**Примечание:** Для доступа к IMEI на Android с уровнем API 23 и выше требуется разрешение пользователя, запрашиваемое через диалоговое окно. В результате этого IMEI может быть получен после активации API StartTracking. Начиная с уровня API 29 доступ к IMEI ограничен.

```java
Public class AFApplication extends Application {
   private static final String AF_DEV_KEY = "";
   private static AFApplication instance;
   @Override
   public void onCreate() {
      //If you want to show debug log.
      AppsFlyerLib.getInstance().setDebugLog(true); //Разработчики собирают IMEI и идентификатор Android, а затем отправляют их в SDK AppsFlyer.
	  AppsFlyerLib.getInstance().setImeiData("customer imei"); \n\t  AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");\n      //Или используйте два API ниже, чтобы SDK AppsFlyer собирал IMEI & android id      //независимо от того, установлены службы Google Play или нет.
      AppsFlyerLib.getInstance().setCollectIMEI(true);\n      AppsFlyerLib.getInstance().setCollectAndroidID(true);\n      //Настройте минимальное время между двумя сессиями; рекомендуется 2 секунды。\n      AppsFlyerLib.getInstance().setMinTimeBetweenSessions(2);\n      final AppsFlyerConversionListener conversionDataListener = new \nAppsFlyerConversionListener() {\n       @Override\n       public void onConversionDataSuccess(Map<String, Object=""> map) {}\n       @Override\n       public void onConversionDataFail(String error) {}\n       @Override\n       public void onAppOpenAttribution(Map<string, string=""> map) {}\n       @Override\n       public void onAttributionFailure(String s) {}\n     }\n     AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionDataListener);\n     AppsFlyerLib.getInstance().startTracking(context, AF_DEV_KEY);\n   }  \n   @Override\n     protected void attachBaseContext(Context base) {\n        instance = this;\n        super.attachBaseContext(base);\n    }\n  public static synchronized AFApplication getAppInstance() {\n        return instance;\n    }\n}
```

При первом запуске приложения пользователю отправляется запрос разрешения READ\_PHONE\_STATE в обратном вызове onResume() в MainActivity.

build.gradle в модуле app****

```java
allprojects {
    repositories {
       ....
       maven { url 'https://jitpack.io'}
    }
}
dependencies {
    implementation 'com.github.tbruyelle:rxpermissions:0.10.2'
}
```

<Tabs>
<Tab title="MainActivity">

```java
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
   @Override
   protected void onCreate(Bundle savedInstanceState) {
       super.onCreate(savedInstanceState);
       startIMEILogic();
   }
   private void startIMEILogic() {
       SharedPreferences permissions_flags = getSharedPreferences("appsflyer-data", MODE_PRIVATE);
       if (!permissions_flags.contains(Manifest.permission.READ_PHONE_STATE)) {
           requestIMEIPermissions();
       }
   }
   private void requestIMEIPermissions() {
       if (ContextCompat.checkSelfPermission(this,
               Manifest.permission.READ_PHONE_STATE)
               != PackageManager.PERMISSION_GRANTED) {
           ActivityCompat.requestPermissions(this,
                   new String[]{Manifest.permission.READ_PHONE_STATE},
                   MY_PERMISSIONS_REQUEST_READ_PHONE_STATE);
       } else {
           //Permission was already granted
           SharedPreferences.Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           permissionsFlagsEditor.putBoolean(Manifest.permission.READ_PHONE_STATE, true);
           permissionsFlagsEditor.apply();
       }
   }
   @Override
   public void onRequestPermissionsResult(int requestCode,
                                          String[] permissions, int[] grantResults) {
       if (requestCode == MY_PERMISSIONS_REQUEST_READ_PHONE_STATE) {
           SharedPreferences.Editor permissionsFlagsEditor = getSharedPreferences("appsflyer-data", MODE_PRIVATE).edit();
           boolean granted;
           // If request is cancelled, the result arrays are empty.
           if (grantResults.length > 0
                   && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
               // разрешение предоставлено!
               granted = true;
               AppsFlyerLib.getInstance().setCollectIMEI(true);
           } else {
               // разрешение отклонено!
               granted = false;
           }
           AppsFlyerLib.getInstance().setMinTimeBetweenSessions(0);
           AppsFlyerLib.getInstance().reportTrackSession(this);
           AppsFlyerLib.getInstance().setMinTimeBetweenSessions(5);
           permissionsFlagsEditor.putBoolean(Manifest.permission.READ_PHONE_STATE, granted);
           permissionsFlagsEditor.apply();
       }
   }
}
```

</Tab>

<Tab title="MainActivity (устаревшая версия)">

```java
public class MainActivity extends AppCompactActivity {
    @Override
    protected void onResume() {
        super.onResume();
        final RxPermissions rxPermissions = new RxPermissions(this);
         if(RxPreference.Instance().getBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, false){
          return;
         }
         if(rxPermissions.isGranted(Manifest.permission.READ_PHONE_STATE)) {
            return;
         }
          RxPreference.Instance().putBoolean(RxPreference.KEY_PERMISSION_DIALOG_HAS_SHOW, true);
        rxPermissions.request(Manifest.permission.READ_PHONE_STATE)
                .subscribe(granted -> {
                    if (granted) {  
AppsFlyerLib.getInstance().setImeiData("customer imei");  
AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");  
//or  
AppsFlyerLib.getInstance().setCollectIMEI(true);  
AppsFlyerLib.getInstance().setCollectAndroidID(true);  
//NOTE: Here the report session API is reportTrackSession() not the startTracking()
                        AppsFlyerLib.getInstance().reportTrackSession(AFApplication.getAppInstance());
                    } else {
                    }
                });
    }
}
```

</Tab>
</Tabs>

</Accordion>

Существует два метода сбора IMEI:

* setImeiData
* setCollectIMEI(true)

Используйте следующий пример кода для интеграции SDK. **Примечание:** В примере кода для получения данных конверсии используется метод `onConversionDataSuccess`. Это название метода, начиная с SDK V5. Если вы используете версию SDK ниже 5.0.0, название метода — `onInstallConversionDataLoaded`. Мы рекомендуем обновить SDK до версии 5.0.0. Подробнее см. <Anchor target="_blank" href="/marketers/ru/docs/links-to-appsflyer-sdk-release-notes">здесь</Anchor>.

```java
 public class AFApplication extends Application {
    private static final String AF_DEV_KEY = "";
    private static AFApplication instance;
    @Override
    public void onCreate() {
      //If you want to show debug log.
      AppsFlyerLib.getInstance().setDebugLog(true);  
 //Разработчик собирает IMEI и идентификатор Android, а затем отправляет их в SDK AppsFlyer.  
 AppsFlyerLib.getInstance().setImeiData("customer imei");  
 AppsFlyerLib.getInstance().setAndroidIdData("customer android_id");
      //Или используйте два API ниже, чтобы SDK AppsFlyer собирал IMEI & android id независимо от того,
      //установлен сервис Google Play или нет.
      AppsFlyerLib.getInstance().setCollectIMEI(true);
      AppsFlyerLib.getInstance().setCollectAndroidID(true);  
      final AppsFlyerConversionListener conversionDataListener = new AppsFlyerConversionListener() {
          @Override
          public void onConversionDataSuccess(Map<String, Object=""> map) {} 
    	  @Override
          public void onConversionDataFail(String error) {}    
    	  @Override
          public void onAppOpenAttribution(Map<string, string=""> map) {}
          @Override
          public void onAttributionFailure(String s) {}
  	};
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionDataListener);
      AppsFlyerLib.getInstance().startTracking(context, AF_DEV_KEY);
  }
    @Override
    protected void attachBaseContext(Context base) {
        instance = this;
        super.attachBaseContext(base);
    }
    public static synchronized AFApplication getAppInstance() {
        return instance;
    }
}
```


</Accordion>

<div id="preparing-the-apk" />

<Accordion title="Подготовка APK">

Выберите, как в AppsFlyer будут отображаться данные атрибуции:

* (лучшие практики) **Одно приложение:** данные атрибуции из всех сторонних магазинов приложений Android (внутренний рынок Китая) отображаются в одном приложении, но отдельно. Это означает, что в AppsFlyer вы видите данные атрибуции из всех китайских магазинов внутреннего рынка в одном приложении. Чтобы использовать этот метод, перейдите к разделу [Добавление приложения в AppsFlyer](/docs/measure-attribution-in-the-chinese-domestic-market#добавление-приложения-в-appsflyer), который приведен ниже.
* **Одно приложение, объединенное с магазином Google Play:** атрибуция как из сторонних магазинов приложений, так и из магазина Google Play отображается как единая сущность. Для этого варианта требуется, чтобы имя пакета в магазине Google Play и в сторонних магазинах было одинаковым. При использовании этого варианта предполагается, что приложение уже определено в AppsFlyer. Чтобы использовать этот метод, перейдите к разделу [Подготовка APK/manifest](/docs/measure-attribution-in-the-chinese-domestic-market#подготовка-apkманифеста), который приведен ниже.
* **Несколько приложений** означает, что данные атрибуции для каждого магазина отображаются в отдельном приложении. Например, отдельно отображаются Google Play Store, сторонний магазин A, сторонний магазин B и т. д. Чтобы использовать этот метод, см. статью <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution">multiple apps</Anchor>. Чтобы использовать этот метод, см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution">множество приложений</Anchor>.

### Добавление приложения в AppsFlyer

**Чтобы добавить приложение в AppsFlyer**:

1. В AppsFlyer нажмите **My Apps**.
2. Нажмите **Добавить приложение**.  
   Откроется окно Add Your App.
3. Выберите **Android out of store APK**.
4. Заполните следующие поля:  
   * **Android package name**: произвольный текст
   * **Channel name**: должно совпадать с именем канала в манифесте, как описано в следующем разделе. В качестве лучшей практики рекомендуется задать для этого поля значение **cn\_market**.
   * **Ссылка на приложение**

**Примечание**: вы можете создать приложение, выбрав вариант **Ожидает одобрения или не опубликовано**, но это не рекомендуется. Перед тем как использовать этот метод, проконсультируйтесь со своим CSM.

### Подготовка APK/манифеста

**Чтобы подготовить отдельный APK/манифест для каждого стороннего магазина приложений:**

1. Добавьте следующее в манифест, чтобы идентифицировать трафик из Китая:

   ```java
   < meta-data android:name="CHANNEL" android:value="cn_market">
   ```

   **Примечание:** Параметры чувствительны к регистру. Мы рекомендуем задать для канала значение **cn\_market**.
2. Выберите один из следующих методов, чтобы идентифицировать магазин:
   * **Метод манифеста:** Добавьте следующую строку в файл AndroidManifest.xml. Значение AF\_STORE должно быть уникальным для каждого магазина.

     ```xml
     <meta-data android:name="AF_STORE" android:value="example_store"/>
     ```

     **--ИЛИ--**
   * **Метод API:** Подготовьте отдельный APK для каждого стороннего магазина приложений. Чтобы установить значение AF\_STORE, вызовите API setOutOfStore. Задайте уникальное значение для каждого магазина.  

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("example_store")
     ```

Описанные методы задают параметр AF\_STORE, который, в свою очередь, задает поле install\_app\_store в данных атрибуции. Это поле доступно:

* когортный анализ
* <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview">Отчеты по необработанным данным</Anchor>

</Accordion>

## Дополнительные аспекты атрибуции

<div id="workaround-for-stores-without-attribution-link-support" />

<Accordion title="Обходной путь для магазинов без поддержки ссылок атрибуции">

Многие сторонние магазины приложений Android в Китае также продают трафик, то есть одновременно являются и рекламными платформами. В некоторых случаях эти магазины не поддерживают использование ссылок атрибуции. В качестве альтернативы можно использовать следующие обходные решения:

* install\_app\_store field: (рекомендуется) Если установка выполняется без ссылки атрибуции, AppsFlyer относит установку к органическим установкам. Используя поле install\_app\_store, вы можете определить фактический источник установки. Примечание: поле install\_app\_store задается с помощью параметра AF\_STORE, описанного в предыдущем разделе.
* <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-factory-preinstall-using-manifest-android">Название предустановки</Anchor> в файле манифеста. Использование названия предустановки, содержащегося в манифесте. Недостаток этого метода в том, что если предустановленный APK попадет на рынок, информация об атрибуции будет некорректной. При использовании этого метода убедитесь, что у вас есть соответствующие коммерческие условия, чтобы защитить APK.

</Accordion>

<div id="china-domestic-attribution-links" />

<Accordion title="Ссылки атрибуции для внутреннего трафика в Китае">

При подготовке ссылок атрибуции учитывайте следующее:

**Ссылки для Китая**

Для медиаисточников, у которых есть только внутренний (китайский) трафик, используйте доменные ссылки, указанные здесь. Эти ссылки распознаются внутри Китая и обеспечивают более удобный пользовательский опыт.

Для обычных ссылок атрибуции используйте: https://app.aflink.com - (aflink.com)

Для ссылок атрибуции OneLink используйте: https://go.onelnk.com (onelnk.com). Примечание: прежде чем использовать домен onelnk.com, обратитесь к своему CSM в AppsFlyer.

Обратите внимание: в weChat в список разрешенных включен только **onelnk.com**, тогда как **onelink.me** заблокирован

**Используйте af\_r**

Используйте af\_r, чтобы пользователи перенаправлялись либо на URL-адрес для загрузки APK, либо в магазин APK, а не в Google Play.

Примечание: часто у интегрированных медиаисточников с внутренним китайским трафиком этот параметр по умолчанию задан как &redirect=false в шаблоне URL-адреса атрибуции. Это означает, что перенаправление выполняют рекламные платформы, а не AppsFlyer.

Подробнее об интегрированных медиаисточниках:  
<Anchor target="_blank" href="/marketers/ru/docs/android-app-promotion-in-china">Продвижение приложения Android в Китае</Anchor>

</Accordion>

<div id="detecting-store-hijacking" />

<Accordion title="Выявление перехвата магазина приложений">

В сценариях со сторонними магазинами приложений пользователь сначала устанавливает приложение из стороннего магазина медиаисточника (рекламной сети). В случае перехвата установки всплывающее предупреждение предлагает пользователю установить или обновить приложение напрямую из магазина приложений производителя устройства (телефона). Если пользователь соглашается, его перенаправляют для загрузки из магазина приложений производителя, после чего APK загружается. Это означает, что производитель устройства перехватил установку.

Следующий пример иллюстрирует как легитимный сценарий, так и сценарий с перехватом:

**Легитимный сценарий**

Пользователь приложения нажимает на рекламу, показанную media-example, и либо сразу загружает приложение, либо перенаправляется в legitimate-app-store для загрузки приложения. В AppsFlyer записывается следующая информация об атрибуции:

* **Медиаисточник**: media-example
* **Магазин приложений для установки**: legitimate-app-store

**Перехваченный поток**

Пользователь приложения кликает по рекламному объявлению, показанному media-example. При запуске загрузки появляется всплывающее предупреждение с предложением скачать приложение из магазина приложений производителя устройства. Если пользователь соглашается, его перенаправляют в магазин производителя, где он скачивает приложение. В AppsFlyer записывается следующая информация об атрибуции:

* **Медиаисточник:** media-example
* **Install-app-store**: manufacturer-store

**Идентификация события перехвата в AppsFlyer**

Чтобы выявить перехваченную установку, сравните поля «медиаисточник» и install-app-store. Несоответствие между ожидаемым значением install-app-store и фактическим значением install-app-store указывает на перехват установки.

</Accordion>

<div data-zendesk-anchors="attribution-android-apps-in-the-chinese-domestic-market=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-android-%D0%BD%D0%B0-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B5%D0%BC-%D1%80%D1%8B%D0%BD%D0%BA%D0%B5-%D0%BA%D0%B8%D1%82%D0%B0%D1%8F preparing-the-app=%D0%BF%D0%BE%D0%B4%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F adding-the-app-in-appsflyer=%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-appsflyer preparing-the-apkmanifest=%D0%BF%D0%BE%D0%B4%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BA%D0%B0-apk%D0%BC%D0%B0%D0%BD%D0%B8%D1%84%D0%B5%D1%81%D1%82%D0%B0 additional-attribution-considerations=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%B0%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D1%8B-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8" />

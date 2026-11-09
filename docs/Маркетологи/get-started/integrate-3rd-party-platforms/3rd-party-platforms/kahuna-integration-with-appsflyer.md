---
title: Интеграция Kahuna с AppsFlyer
metadata:
  keywords:
    - kahuna
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-09-14T11:26:59Z'
  edited_at: '2026-08-28T00:10:45Z'
  id: 212561966
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/212561966
---
> **Кратко:** Kahuna — интегрированный партнер AppsFlyer, который помогает компаниям расти и процветать в эпоху мобильных технологий. Мы обеспечиваем новый уровень подлинной вовлеченности между брендами и их клиентами, где бы они ни находились — в интернете, в электронной почте, на мобильных устройствах, в социальных каналах — благодаря персонализированной коммуникации в масштабе. Используя большие данные и машинное обучение, мы помогаем создавать превосходный опыт для каждого клиента благодаря идеальному сообщению, доставленному по нужному каналу в нужное время.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

Чтобы настроить интеграцию с Kahuna, следуйте инструкциям ниже:

1. Минимальные требования — AppsFlyer SDK:

* Android – версия 2.3.1.18 и выше
* iOS – версия 3.3.3 и выше

2. Для интеграции с Kahuna необходимо, чтобы <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/deviceid/">идентификатор устройства</Anchor> Kahuna (уникальный идентификатор пользователя Kahuna) был указан в SDK AppsFlyer. Этот параметр отправляется с каждым постбэком и позволяет идентифицировать каждого пользователя. Для этого необходимо вставить в код приложения следующие строки:

<div id="important-note" />

> 📘 **Важное замечание**
>
> Убедитесь, что строки кода вставлены в правильное место — после запуска SDK Kahuna и до вызова методов appsflyer.sendtracking (Android) / trackAppLaunch (iOS).

<Tabs>
<Tab title="Для Android">

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId = Kahuna.getInstance().getKahunaDeviceId();
customData .put("customData", deviceId);
AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="Для iOS">

```objectivec
NSString *kahunaDeviceID = [Kahuna getKahunaDeviceId];
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{@"customData" : kahunaDeviceID}];
```

</Tab>
</Tabs>

<div id="setting-up-kahuna" />

## Настройка Kahuna

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. **Примечание. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации/деактивации партнеров</Anchor>.**
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

В окне настройки Kahuna используется только вкладка ***Integration***.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

Вкладка Integration («Интеграция») содержит несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом посещении** нужно переключить переключатель ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="general-settings" />

### Общие настройки

**Секретный ключ Kahuna, Staging и Production**

Kahuna подключается к AppsFlyer с помощью уникального секретного ключа. Если у вас его ещё нет, для продолжения интеграции необходимо получить его у Kahuna или выполнить следующие шаги. [![](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)

<div id="obtaining-the-kahuna-secret-key" />

### Получение секретного ключа Kahuna

1. Войдите в свою учетную запись Kahuna

2. Нажмите на значок пользователя и выберите **Настройки** в правом верхнем углу меню дэшборда

<Image align="center" alt="" src="https://files.readme.io/4962454c4dd428c69e90d4ebcfa20304dc0ea57c7d58a1368c9a9369ba3e563a-207206166.png" />

3. Скопируйте секретный ключ Kahuna:

<Image align="center" alt="" src="https://files.readme.io/73d24826e6c55636dafbc22766910fea12fbe7a58c49079c800d5056be45352a-207229823.png" />

4. Выберите **APIs & Integrations** — на этой странице вы найдете параметры:

* Вставьте Kahuna Master Key, полученный из консоли Kahuna (см. раздел 3)
* Если вы хотите отправлять события в среду Sandbox Kahuna, введите букву S в поле Staging (см. раздел «Тестирование с использованием Kahuna Sandbox»)
* Для рабочей среды введите букву P в поле Production
* Если ввести обе буквы, события будут отправляться в рабочую среду
* Нажмите **Сохранить**.

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки по установкам пользователей Kahuna. В этом разделе можно определить отправку этих постбэков.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Выберите **События, атрибутированные любому партнеру или органические**, чтобы отправлять постбэки в Kahuna для любого пользователя, который скачивает приложение.

Нажмите кнопку **Сохранить.**

После сохранения конфигурации AppsFlyer отправляет в Kahuna следующие данные для каждой органической и неорганической установки:

* Kahuna Dev\_ID
* Источник медиа
* Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>.
* Версия ОС

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Kahuna.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для Kahuna.

</Accordion>

<div id="view-user-attribution-data-in-kahuna" />

## Просмотр данных атрибуции пользователей в Kahuna

События установки можно просматривать как Newbies на основном дэшборде Kahuna.

<Image align="center" alt="" src="https://files.readme.io/ebbb7f265e37ead80dd77a9956b9629ce07eeb2fcc9b283ad7b6cc927fe10758-207230483.png" />

Вы можете найти конкретного пользователя или перейти в раздел «Top People» в меню слева.

<Image align="center" alt="" src="https://files.readme.io/ea6ae8494f600bb8a9b9b0af3e36a976e65d72b64052da3e7399f9a9b0c9458c-207230503.png" />

При выборе одного из пользователей открывается Mini Profile, где в разделе Top Events можно увидеть событие установки «af\_install»:

<Image align="center" alt="" src="https://files.readme.io/3e0a99f178cc1a9ab18886a576b4ba56878fecb6dbd0866926730fb32b65bc59-207230563.png" />

<div id="testing-with-sandbox" />

## Тестирование через sandbox

Если вы еще не выпустили приложение в магазин приложений и хотите протестировать интеграцию из среды Sandbox Kahuna, выполните следующие действия:

1. Убедитесь, что при настройке Kahuna в AppsFlyer вы вводите «s» в поле Staging

<Image align="center" alt="" src="https://files.readme.io/b69fc390ed7f1303ee8ba6dd1345d2c76b5b4c22b4b0b6ec0957a108d709247b-360002217229.png" />

2. Убедитесь, что вы добавили код в свое приложение для интеграции SDK AppsFlyer и Kahuna, как описано в разделах выше

3. Вам нужно получить Advertising ID с тестового устройства (его можно найти, установив приложение на устройство и просмотрев логи)

4. Попросите AppsFlyer добавить ваш Advertising ID в список разрешенных

5. Удалите приложение с устройства

6. Настройте этот URL-адрес, указав свои данные (имя пакета приложения, advertising ID и название кампании... не включайте скобки) - [https://app.appsflyer.com/[APP PACKAGE NAME]?pid=[SOMETHING]&advertising\_id=](https://app.appsflyer.com/com.dailylabs.kahunatest?pid=Testing_Installs&advertising_id=0eea1488-3037-44b2-a944-11f8bfc3e479)[DEVICE’S ADVERTISING ID]

7. Перейдите по этому URL-адресу, вы можете увидеть следующее:

<Image align="center" alt="" src="https://files.readme.io/8b16b6d84f0244db3510e4376bf5fc51b6a737e13df89da82e951e1bda90711a-207230963.png" width="486px" />

8. Установите приложение на свое устройство

9. Перейдите в дэшборд Kahuna и найдите пользователя (можно включить отладку Kahuna и посмотреть логи, чтобы получить уникальный идентификатор устройства Kahuna для этого пользователя.. “dev\_id”... или, если для вашего приложения требуется вход в систему и вы передаете учетные данные в Kahuna, можно также выполнить поиск по этим учетным данным). Когда вы найдете пользователя, вы должны увидеть событие “af\_install” для этого пользователя.

<Image align="center" alt="" src="https://files.readme.io/b365a27e7638a6a87e6a5b46a67d329956f6a678b234bd1fd802acaeeceaaeb2-207207606.png" width="629px" />

<div data-zendesk-anchors="h_01H9FKAF22A3FTGC7CSE5K0CY4=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01H9FKAF22W59PMYJRFW8HKBQ7=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE%D0%B5-%D0%B7%D0%B0%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 setting-up-kahuna=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-kahuna h_01H9FKAF222ES9240V0THQQ5X0=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-kahuna h_01H9FKAF227SZWFTCP9P1B7HEK=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FKAF22EFF1F8D2QR1F38PV=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FKAF221EXQYBJGS8GFRF4S=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 obtaining-the-kahuna-secret-key=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D0%B5%D0%BA%D1%80%D0%B5%D1%82%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-kahuna h_01H9FKAF22XMJW7A89MBD0J276=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D0%B5%D0%BA%D1%80%D0%B5%D1%82%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-kahuna default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKAF2258JVR3XS6P7TT8H3=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKAF22DMF1NNJRY3SJB5XX=attribution-link-tab h_01H9FKAF22KPY1ABFJN63XZ5CM=cost-tab h_01H9FKAF22KRDEFTVBR954JSJT=ad-revenue-tab h_01H9FKAF22HJPHZZM59TQ7RRFM=permissions-tab view-user-attribution-data-in-kahuna=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B2-kahuna h_01H9FKAF22A5910NXRFDGC1JTG=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B2-kahuna testing-with-sandbox=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-sandbox h_01H9FKAF22KW2J6H2B6F9AMDP9=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-sandbox" />

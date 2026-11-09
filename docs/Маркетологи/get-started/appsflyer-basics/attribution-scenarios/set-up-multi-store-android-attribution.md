---
title: Настройте атрибуцию для нескольких магазинов Android
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
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
    - Agencies
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2026-08-18T00:10:40Z'
  id: 207447023
  locale: ru
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ru/articles/207447023
---
> **Краткий обзор:** Атрибутируйте свои приложения в нескольких магазинах Android и просматривайте данные либо в единой панели приложения, либо в отдельных панелях для каждого магазина.

<div id="multi-store-android-attribution" />

## Атрибуция приложений Android для нескольких магазинов

AppsFlyer атрибутирует приложения независимо от магазина приложений. Имеются в виду магазин Google Play и сторонние магазины Android, такие как Amazon, Opera, GetJar, Baidu и Huawei (также известные как независимые (out-of-market) или альтернативные магазины приложений Android). (также известные как независимые (out-of-market) или альтернативные магазины приложений Android). Владельцы приложений, которые продвигают их в нескольких магазинах, могут использовать **единый** **дэшборд,** содержащий данные всех магазинов, или **отдельный дэшборд для каждого магазина.**

<div id="note" />

> 📘 **Примечание**
>
> * Атрибуция AppsFlyer для Android поддерживает все типы идентификаторов устройств, включая GAID и <Anchor target="_blank" href="/marketers/ru/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>.
> * По приложениям, продвигаемым в Китае, см. статью <Anchor target="_blank" href="/marketers/ru/docs/measure-attribution-in-the-chinese-domestic-market">Атрибуция приложений для Android на внутреннем рынке Китая</Anchor>.

<Image align="center" alt="DashboardType_us-en-new.jpg" src="https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg" />

<div id="single-dashboard-vs-dashboard-per-store" />

### Единый дэшборд vs. отдельный дэшборд на магазин

* **Единый дэшборд:** Единый дэшборд, объединяющий данные из всех магазинов, включая Google Play Store.
* **Дэшборд для каждого магазина приложений:** Несколько дэшбордов — у каждого магазина есть свой дэшборд. Это значит, что число дэшбордов соответствует числу магазинов, которые предоставляют ваше приложение.

<table><thead><tr><th> </th><th>Единый дэшборд<br/>[Лучшая практика]</th><th> Дэшборду на каждый магазин</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>Имя пакета Android</td><td colspan="2">Используйте одно и то же (идентичное) название пакета независимо от выбранной опции. </td></tr><tr><td><span id="channel-name"></span>Название канала</td><td>Настройка не требуется</td><td><ul><li><span>При добавлении приложения в панели AppsFlyer, выбрав параметр <strong>«APK вне магазина Android»</strong>, укажите канал.</span></li><li><span>Канал идентифицирует магазин.</span></li><li>Комбинация названия пакета Android и канала становится уникальным идентификатором каждого дэшборда AppsFlyer.</li><li>Пример: Название пакета Android — com.abc.def, а канал — xyzdevicestore. Уникальный идентификатор дэшборда — com.abc.def-xyzdevicestore.</li><li>Если в APK указан канал, но приложения с таким значением нет, трафик будет приписан приложению по умолчанию — тому, у которого настройки канала пустые (Google Play Store). </li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>Заполнение поля install_app_store</td><td><ul><li>Уникально идентифицирует магазин, предоставляющий приложение путем загрузки.</li><li>В случае Google Play Store это поле пустое.</li><li>Название магазина указывается в <a href="./set-up-multi-store-android-attribution#single-dashboard-apk-preparation">манифесте/APK</a>.</li></ul></td><td>Н/Д</td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#создание-шаблонов-onelink" target="_blank">Шаблон OneLink</a></td><td>Этот метод рекомендуется при работе с OneLink. </td><td>Н/Д </td></tr><tr><td><span id="measurementattribution-links"></span>Ссылки измерения/атрибуции </td><td><ul><li>Ссылки те же самые, независимо от магазина.</li><li>Чтобы перенаправлять пользователей в нужный магазин, задайте URL-адрес перенаправления с помощью параметра <a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">af_r</a> </li></ul></td><td><ul><li>Для каждого магазина необходима уникальная ссылка.</li><li>Создайте их на странице <strong>Активные интеграции</strong>.</li><li>Идентификатор приложения — это имя канала, добавленное в конец имени пакета Android. Например: com.abc.def-def_store.<br/>Поэтому ссылки атрибуции будут различными.</li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>Доступные варианты отчетности при наличии поля install_app_store</td><td>Отчеты о сырых данных всегда содержат это поле. Для Обзора и Когорт свяжитесь с вашим менеджером, попросив его добавить необходимую функцию. </td><td>Н/Д </td></tr><tr><td><span id="considerations"></span>Соображения</td><td><ul><li>Точность атрибуции Повторные установки из разных магазинов не приводят к завышенныму количеству установок.</li><li><span>Органические установки будут отражать органические установки APK из всех магазинов, находящихся в одном дэшборде.</span></li><li><span>В настоящий момент разбивка по магазинам доступна только в обзорном и когортном отчетах, а также в отчетах с сырыми данными.</span></li></ul></td><td><ul><li>Точность атрибуции Повторные установки учитываются, что приводит к менее точной атрибуции.</li><li><span>Просматривайте данные об органических и неорганических установках, а также событиях внутри приложения для каждого магазина (канала) на отдельных панелях приложений в AppsFlyer.</span></li><li><span>Чтобы показывать консолидированные отчеты по всем магазинам вместе, нужно использовать когорты.</span></li><li><p>Активируйте партнера (<a href="./partner-activation-deactivation" target="_blank">Активировать партнера</a> включено) в каждом приложении стороннего магазина, где партнер проводит активную кампанию. Это помогает предотвратить расхождения в атрибуции, особенно при работе с сетями с собственной отчётностью (SRN).<br/> </p></li></ul></td></tr></tbody></table>

<div id="set-up-tasks" />

## Настройка

В следующем процессе перечислены действия, которые нужно выполнить для настройки нужного варианта. Действия разделены между маркетологом и разработчиком.

Для опции «Дэшборд на каждый магазин» повторите все операции для каждого магазина.

<div id="before-you-begin" />

### **Прежде чем начать**

* Определите соглашение об именах для канала и параметров install\_app\_store.
* Используйте следующую таблицу имен для сопоставления каналов и магазинов.
* Таблица используется разработчиком для подготовки APK.

<table><thead><tr><th>Параметр</th><th>Инструкции</th><th>Единый дэшборд<br/>[Лучшая практика]</th><th>Дэшборду на каждый магазин</th></tr></thead><tbody><tr><td>Имя пакета Android</td><td>Одно и то же имя пакета для всех вариантов дэшбордов</td><td colspan="2">Если приложение уже присутствует в Google Play Store, используйте существующее имя пакета. Пример: comb.abc.def</td></tr><tr><td>Название канала</td><td>Уникальное значение для каждого магазина.</td><td>Не установлено. Оставьте пустым. </td><td><p>Уникальное для каждого магазина. Задайте его значение в индивидуальном APK, который вы подготовили для магазина. Его также нужно настроить, когда вы добавляете приложение в AppsFlyer. </p><p>Не указывайте канал для пакета APK магазина Google Play. </p></td></tr><tr><td>Магазин установки приложения AF_STORE</td><td>Уникальное значение для идентификации магазина</td><td><span>Уникальное для каждого магазина. Задайте в APK через манифест. У каждого магазина свой APK. </span></td><td> Не установлено</td></tr></tbody></table>

<div id="tasks" />

### Действия

| Шаг | Ответственность | Единый дэшборд | Дэшборду на каждый магазин |
| --- | --- | --- | --- |
| 1 | Разработчик | [Подготовка APK](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [Подготовка APK](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | Маркетолог | действий не требуется. Предполагается, что приложение уже активно в AppsFlyer. | [Добавьте приложение](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app) в AppsFlyer. |
| 3 | Маркетолог | [Подготовьте ссылки атрибуции](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | Подготовьте ссылки атрибуции, используя идентификатор приложения в сочетании с названием канала. |
| 4 | Разработчик и маркетолог | [Тестирование](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [Тестирование](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

<div id="procedures" />

## Процедуры

<div id="single-dashboard-apk-preparation" />

<Accordion title="Единый дэшборд — подготовка APK">

Имя пакета Android определяет, какой дэшборд будет содержать данные атрибуции. При использовании метода единого дэшборда все магазины имеют одинаковые имена пакетов Android. Здесь нет понятия параметра канала.

Магазин для загрузки определяется по параметру AF\_STORE, который задается в SDK, как описано в этом разделе.  Параметр AF\_STORE не чувствителен к регистру. Например: ABC, abc, Abc.

**Чтобы подготовить APK:**

1. Создайте копию сборки приложения. **Примечание**: Не меняйте название пакета Android.
2. Для идентификации конкретного магазина используйте один из следующих методов:
   * **Метод манифеста:** Чтобы идентифицировать магазин, добавьте следующий фрагмент кода внутрь тега `<application>` файла AndroidManifest.xml. Установите параметр AF\_STORE для имени магазина приложений.

     ```xml
     <application>
        ...
        <meta-data android:name="AF_STORE" android:value="EnterStoreNameHere"/>
        ...
     </application>
     ```

     **--ИЛИ--**
   * **Метод API** Подготовьте отдельный APK для каждого альтернативного магазина приложений. Чтобы установить значение AF\_STORE, вызовите API setOutOfStore. Задайте уникальное значение для каждого магазина.

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("EnterStoreNameHere")
     ```

Заданное здесь значение отображается в поле install\_app\_store сырых данных AppsFlyer. Это поле доступно:

* Обзорный дэшборд
* Ретаргетинг
* <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Отчеты о сырых данных</Anchor> (это премиальная опция AppsFlyer)

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="Единый дэшборд — ссылки атрибуции">

Независимо от того, создаете ли вы свою ссылку атрибуции <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">для использования рекламной сетью</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/onelink-onboarding-guide#описание-onelink">для собственных медиа</Anchor>, следуйте этим шагам, чтобы убедиться, что все ваши взаимодействия со ссылкой на атрибуцию отображаются на одном дэшборде.

1. В вашей ссылке атрибуции установите параметр **URL-адрес вне магазина**. Это подставляет `af_r`макрос в атрибуционную ссылку, чтобы перенаправить пользователей на нужный лэндинг приложения в магазине. Например:`&af_r=https://www.destinationurl.com`

   <div id="note-1" />

   > 📘 **Примечание**
   >
   > URL-адрес перенаправления по умолчанию **URL-адрес приложения вне магазина** установлен на странице <Anchor target="_blank" href="/marketers/ru/docs/app-settings">Настройки приложения</Anchor>. Если это было настроено, нет необходимости обновлять ссылку атрибуции, потому что ссылки атрибуции, созданные для приложения, будут автоматически заполнены этим URL-адресом. <Anchor target="_blank" href="/marketers/ru/docs/app-settings#outofstore-app-url">Подробнее</Anchor>

2. Добавьте `af_r` перенаправление в <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-domain-redirect-allowlist">список разрешенных перенаправлений</Anchor>.
3. Заполните `af_r`макрос URL-адресом страницы приложения в магазине.
4. Настройте дополнительные <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#параметры-ссылки-атрибуции">параметры ссылки атрибуции</Anchor>.
5. Источники трафика вне магазинов **используют сопоставление по ID для атрибуции**, а <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">вероятностное моделирование</Anchor> AppsFlyer служит резервным методом.
6. Добавьте один или несколько заполнителей (placeholders) для идентификатора пользователя в URL-адрес ссылки:
   * `android_id`
   * `рекламный_идентификатор`
   * `oaid`
7. Скопируйте ссылку атрибуции и передайте ее партнеру рекламной сети.

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="По дэшборду на магазин — подготовка APK">

Название пакета Android в сочетании с установленным в манифесте параметром канала определяет, дэшборд какого магазина будет содержать данные об атрибуции.

**Чтобы подготовить отдельный APK/манифест для каждого магазина:**

* Чтобы идентифицировать магазин, добавьте следующий фрагмент кода внутрь тега `<application>` файла AndroidManifest.xml. Установите для параметра Канал название магазина приложений.

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="EnterStoreNameHere"/>
       ...
  </application>
  ```

  **Примечание:** Параметры чувствительны к регистру. Для названия канала необходимо использовать буквы только в верхнем или нижнем регистре (a-z или A-Z). Никакие другие символы, такие как дефис (-) или подчеркивание (\_), не допускаются.

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="По дэшборду на магазин — добавление приложения">

Добавьте дэшборд (приложение), который идентифицируется сочетанием имени пакета Android и канала, заданного в APK/манифесте. Пример: Если имя пакета Android – com.myapp, а название канала – abcstore, то уникальным именем для дэшборда будет com.myapp—abcstore.

**Чтобы добавить в AppsFlyer "по дэшборду на каждый магазин"**:

1. В AppsFlyer в боковом меню выберите **Настройки** > **Мои приложения** и нажмите **Добавить приложение**.
2. Выберите **Android > В стороннем магазине.**
3. Завершите:
   * **Название пакета Android** Название пакета точно такое же, как оно отображается в пакете приложения.
   * **Название канала:** Уникальный идентификатор (название магазина), позволяющий различать дэшборды с одинаковым названием пакета. Убедитесь, что в APK используется то же значение, которое было подготовлено для магазина.  
     **Примечание:** Для названия канала необходимо использовать буквы только в верхнем или нижнем регистре (a-z или A-Z). Никакие другие символы, такие как дефис (-) или подчеркивание (\_), не допускаются.
   * **URL-адрес приложения:**
     * Содержит URL-адрес загрузки по умолчанию, который заполняет макрос af\_r в ссылках атрибуции. Укажите URL-адрес места размещения APK или его лендинга.
     * Его можно изменить для конкретной ссылки атрибуции при ее создании.
4. Нажмите **Далее**.
5. Следуйте инструкциям в интерфейсе, чтобы завершить добавление приложения.

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="Тестирование — оба варианта дэшбордов">

<div id="non-organic-installs" />

#### **Неорганические установки**

**Чтобы протестировать неорганические установки:**

1. Используйте устройство Android, на котором ваше приложение не установлено, или <Anchor target="_blank" href="/marketers/ru/docs/registering-test-devices">зарегистрируйте устройство</Anchor>.
2. Создайте тестовую ссылку атрибуции с помощью <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink</Anchor>. Используйте test в качестве названия медиа-источника ("&pid=test").
3. Добавьте идентификатор рекламы (GAID, OAID или Android ID) к кликабельному URL-адресу.

   ```http
   https://app.appsflyer.com/com.greatapp?pid=test
   &af_r=https://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   Отправьте себе ссылку атрибуции по электронной почте и нажмите на нее. **После перенаправления не выполняйте установку из магазина**. Вместо этого установите обновленную бета-версию приложения со встроенным SDK AppsFlyer, предназначенным для атрибуции, и запустите это приложение.

| Единый дэшборд | Дэшборду на каждый магазин |
| --- | --- |
| <ol><li>Посмотрите отчет с сырыми данными по установкам приложения на странице «Экспорт данных».</li><li>Вы должны увидеть одну конверсию установки с медиа-источником test. В столбце **Магазин установки приложения** вы должны увидеть название магазина в том виде, в каком оно указано в файле manifest.xml.</li><li>Вы также можете увидеть параметр "af\_installstore": "STORE\_NAME" в журналах установок.</li></ol> | <ol><li>Перейдите к нужному приложению через магазинный дэшборд.</li><li>Посмотрите отчет о сырых данных по установкам для своего приложения на странице "Экспорт данных" или же посмотрите обзорную страницу приложения.</li><li>Вы должны увидеть одну конверсию установки для медиа-источника test.</li></ol> |

<div id="organic-installs" />

#### **Органические установки**

**Чтобы протестировать органические установки:**

1. Используйте устройство Android, на котором ваше приложение не установлено, или же <Anchor target="_blank" href="/marketers/ru/docs/registering-test-devices">зарегистрированное</Anchor> устройство.
2. Установите обновленную бета-версию приложения со встроенным SDK AppsFlyer, предназначенным для атрибуции, и запустите это приложение.
3. Проверьте результаты:

<div id="expected-results" />

#### Ожидаемые результаты

| Единый дэшборд | Дэшборду на каждый магазин |
| --- | --- |
| Проверьте обзорную страницу Overview для новой органической установки (под медиа-источником "organic"). На данный момент при использовании метода единого приложения источники органических установок не указываются. | <ol><li>Перейдите на дэшборд, а затем на страницу обзора приложения, которые относятся к тестируемому магазину.</li><li>Вы должны увидеть одну конверсию установки для медиа-источника organic (органические).</li></ol> |

</Accordion>

<div id="additional-features" />

## Дополнительные функции

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="Привлечение пользователей из Facebook в магазин приложений Amazon">

1. Настройте URL-адрес ссылки на приложение в настройках вашего приложения для Meta в разделе **Android**.
2. Войдите в Meta как администратор приложения, перейдите по адресу <Anchor target="_blank" href="https://developers.facebook.com/apps/">https://developers.facebook.com/apps/</Anchor> и выберите приложение.
3. Перейдите к настройкам и найдите параметры для Android или добавьте платформу Android, если она еще не настроена.
4. Введите необходимые данные, в том числе URL-адрес своего приложения в магазине приложений Amazon.  

   <Image align="center" alt="outofstore_1.png" src="https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png" />
5. На дэшборде AppsFlyer перейдите на страницу «Активные интеграции» и выберите Meta Ads, а потом введите тот же идентификатор приложения Facebook, который вы используете в Meta Ads при регистрации установок мобильных приложений из магазина с помощью AppsFlyer.

</Accordion>

<div id="getting-the-data-appsflyer-reports" />

<Accordion title="Получение данных — дополнительные отчеты AppsFlyer">

Помимо обзорного дэшборда, вы можете использовать следующие методы отчетности, которые предлагает AppsFlyer.

* Когортный:
  * Консолидируйте данные по нескольким дэшбордам (приложениям) в одном отчете
  * Просматривайте показатели эффективности каждого дэшборда с разбивкой по install\_app\_store
* Pull API (для метода с одним приложением) <Anchor target="_blank" href="/marketers/ru/docs/pull-api-aggregate-data">API для получения</Anchor> сырые данные установок не содержат **Магазин приложений для установки** по умолчанию. Чтобы включить столбец, добавьте следующее в вызов Pull API: `&additional_fields=install_app_store`
* Настраиваемый дэшборд (для метода с несколькими приложениями) Если вы используете подход с несколькими дэшбордами, используйте <Anchor target="_blank" href="/marketers/ru/docs/custom-dashboards">настраиваемый дэшборд</Anchor>, чтобы объединить данные о производительности из нескольких приложений в одном месте.

</Accordion>

<div id="referrer-implementation-thirdparty-android-app-stores" />

<Accordion title="Реализация реферера в сторонних магазинах Android">

Атрибуция рефералов сторонних магазинов поддерживается в SDK следующим образом:

* **Реферал магазина Samsung**: Готовая встроенная поддержка
* **Реферал магазина Huawei**: Зависимость должна быть добавлена вашим разработчиком, для инструкций смотрите [Хаб разработчиков](https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer).
* **Реферал магазина Xiaomi GetApps**: Зависимость должна быть добавлена вашим разработчиком, для инструкций смотрите [Хаб разработчиков](https://dev.appsflyer.com/hc/docs/install-android-sdk#xiaomi-getapps-store-referrer).

Сторонние магазины приложений для Android, у которых есть интеграция атрибуции реферера с AppsFlyer

| Сторонний магазин приложений | Дата начала | Версия SDK |
| --- | --- | --- |
| <span id="huawei-app-store"></span>Магазин приложений Huawei | Июль 2020 | 6.14.0+ |
| <span id="samsung-galaxy-store"></span>Магазин Samsung Galaxy | Декабрь 2020 | 6.1.1 + |
| <span id="xiaomi-getapps-store"></span>Магазин Xiaomi GetApps | Сентябрь 2022 г. | 6.9.0 + |

</Accordion>

<div id="3rd-party-raw-data" />

<Accordion title="Реферал стороннего магазина в отчетах о сырых данных">

Атрибуция реферера стороннего магазина отражается в отчетах с сырыми данными следующим образом:

* Тип соответствия: название стороннего магазина, которому приписана атрибуция. Match type (Тип соответствия): название стороннего магазина, Например: `huawei_referrer`.
* Участники: Если пользователь до установки приложения взаимодействовал с несколькими магазинами приложений, AppsFlyer считает эти взаимодействия участниками. Установка атрибутируется источнику последнего клика. Пример:
  * Пользователь нажимает рекламное объявление, показанное Google, перенаправляется в Play Store,  Пользователь не скачивает приложение. Пользователь не скачивает приложение.
  * Пользователь нажимает другое рекламное объявление и перенаправляется в магазин Samsung Galaxy Store, Пользователь скачивает и устанавливает приложение. Пользователь скачивает и устанавливает приложение.
  * Атрибуция присваивается рекламной сети, перенаправившей пользователя в магазин Samsung Galaxy, а Google признаётся участником.

</Accordion>

<div id="troubleshooting" />

## Устранение неполадок

<div id="installs-attributed-to-the-default-app" />

### Установки, атрибутированные приложению по умолчанию

Если вы создаете APK приложения с настройкой канала, но не создаете панель для него в аккаунте AppsFlyer: Установки атрибутируются приложению по умолчанию, обычно это приложение Google Play Store в вашем аккаунте. Если приложение по умолчанию не задано, данные не регистрируются.

<div id="traits-and-limitations" />

## Характеристики и ограничения

| Специфика | Примечания |
| --- | --- |
| Перенаправление с помощью OneLink в различные магазины приложений | В <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">шаблоне OneLink</Anchor> можно задать несколько магазинов приложений, только если для всех магазинов имя пакета приложения одинаково и вы выбрали единый дэшборд. |
| Установить магазин приложений | Этот параметр недоступен для агентств и рекламных сетей. |
| Перенаправление OneLink в сторонний магазин | Если ваше Android-приложение доступно исключительно через сторонний магазин, [вы должны установить его статус в Google Play на "Опубликовано вне магазина" при добавлении приложения](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app). Выбор любого другого статуса предотвратит перенаправление в сторонний магазин и приведет к сообщению об ошибке. |
| Доход от рекламы | `af_ad_revenue` значения не могут быть сгруппированы по значениям `install_app_store`. |

<div data-zendesk-anchors="multistore-android-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-android-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%B8%D1%85-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%BE%D0%B2 h_01HJ369QB8PDKG7QQRV840KRAY=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-android-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%B8%D1%85-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%BE%D0%B2 h_01HJ369QB876GZKQCGJZQDXDRF=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 single-dashboard-vs-dashboard-per-store=%D0%B5%D0%B4%D0%B8%D0%BD%D1%8B%D0%B9-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4-vs-%D0%BE%D1%82%D0%B4%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4-%D0%BD%D0%B0-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD h_01HJ369QB8SRN61ABBZ51TKFX2=%D0%B5%D0%B4%D0%B8%D0%BD%D1%8B%D0%B9-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4-vs-%D0%BE%D1%82%D0%B4%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4-%D0%BD%D0%B0-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 h_01HJ369QB8NPE8FAHR42D2YN0K=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 before-you-begin=%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5-%D1%87%D0%B5%D0%BC-%D0%BD%D0%B0%D1%87%D0%B0%D1%82%D1%8C h_01JD2DEXW74MFE44FM3S0JCK5Q=%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5-%D1%87%D0%B5%D0%BC-%D0%BD%D0%B0%D1%87%D0%B0%D1%82%D1%8C tasks=%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F h_01JD2DFF2K0APZ98JV1X09ZB33=%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B h_01HJ369QB990HH38TRQESQVFWN=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation h_01HJ369QB9V3W9R3EB6SJSNBED=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links h_01HJ369QB9H3J6E892X4V15AYJ=single-dashboard-attribution-links h_01K5EJP59771926PMZBRC0C2AB=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation h_01HJ369QB9SP4DHZM5JB0RKEWG=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app h_01HJ369QB9X58DVBTWVWD0GCAV=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options h_01HJ369QB97FN9BJKD9WRW99YG=testing-both-dashboard-options nonorganic-installs=%D0%BD%D0%B5%D0%BE%D1%80%D0%B3%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 h_01HJ369QB93A3ZZFAF0JAEXFRR=%D0%BD%D0%B5%D0%BE%D1%80%D0%B3%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 organic-installs=%D0%BE%D1%80%D0%B3%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 h_01HJ369QB9SA05Y8VES8DD1FY4=%D0%BE%D1%80%D0%B3%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 expected-results=%D0%BE%D0%B6%D0%B8%D0%B4%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D1%80%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%D1%8B h_01HJ369QBAJADS4SMSDPKK9RHW=%D0%BE%D0%B6%D0%B8%D0%B4%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D1%80%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%D1%8B additional-features=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8 h_01HJ369QBAQ49ACSG3VEGSH7D4=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8 h_01HJ369QBA1XVMZD4G019T2S9W=driving-users-to-the-amazon-app-store-from-facebook h_01HJ369QBA2WDAZNNPRRWA3MRT=getting-the-data-appsflyer-reports referrer-implementation%E2%80%94thirdparty-android-app-stores=referrer-implementation-thirdparty-android-app-stores h_01HJ369QBA4D0SG9MQE6MXB0DH=referrer-implementation-thirdparty-android-app-stores 01JBKT1E0YA06EKW27VR1DH861=3rd-party-raw-data troubleshooting=%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA 01JBKV47A5YJXKYHWA7H8NQAAF=%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA installs-attributed-to-the-default-app=%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8E-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HJ369QBANRCTCFKTGK8BTQEC=%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8E-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HJ369QBAJA87QJNTYNWYX82N=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

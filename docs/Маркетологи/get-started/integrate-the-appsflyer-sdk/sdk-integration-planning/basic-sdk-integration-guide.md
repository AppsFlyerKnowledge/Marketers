---
title: Базовое руководство по интеграции SDK (пакет средств разработки ПО)
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2026-08-19T00:15:07Z'
  id: 207032066
  locale: ru
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ru/articles/207032066
---
> **At a glance:** **Краткий обзор:** Работайте вместе с разработчиком вашего мобильного или CTV-приложения, чтобы интегрировать и установить SDK (пакет средств разработки ПО) в приложения для Android или iOS. После завершения основных задач интеграции ваше приложение будет готово к атрибуции установок и измерению внутренних событий приложения.

## **Внедрение ключа разработчика в ваше приложение**

AppsFlyer использует ключ разработчика для уникальной идентификации вашей учётной записи. Ключ разработчика обязателен, так как позволяет SDK (пакет средств разработки ПО) безопасно отправлять и получать данные, относящиеся к вашей учётной записи. Ваш разработчик должен установить и интегрировать SDK (пакет средств разработки ПО), а также внедрить ключ разработчика.

#### Получение ключа разработчика

Перед тем как разработчик сможет установить и интегрировать SDK (пакет средств разработки ПО), вам необходимо получить ключ разработчика.

1. В AppsFlyer в боковом меню выберите **Настройки** > **Настройки приложения**.
2. Скопируйте свой ключ разработчика и отправьте его вашему мобильному разработчику.

   ![](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)

#### Предоставьте ключ разработчика вашему разработчику

Предоставьте ключ разработчика, идентификатор приложения и токен API v2 AppsFlyer вашему мобильному разработчику, а также следующие инструкции:

* <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration">Мастер интеграции SDK</Anchor> для автоматической установки и интеграции SDK.
* Пошаговые инструкции для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">установки</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration">интеграции SDK</Anchor>.

## **С чего начать использование SDK?**

При планировании интеграции SDK (пакета средств разработки ПО) AppsFlyer первое, что нужно решить, это где инициализировать и запустить SDK (пакет средств разработки ПО) в процессе запуска вашего приложения.

Главное правило — запускать SDK (пакет средств разработки ПО) как можно раньше после старта приложения, чтобы начать отправку данных. **Это гарантирует, что SDK зафиксирует событие установки и все другие внутренние события, происходящие в сессии.**

Однако для соблюдения правил защиты данных, таких как GDPR и CCPA, часто требуется отсрочить отправку данных в AppsFlyer до получения согласия пользователя на передачу своей информации.

<Tabs>
<Tab title="Android iOS">

### Запуск SDK (пакета средств разработки ПО) в нативной среде Android

#### ВЫБЕРИТЕ КЛАСС, В КОТОРОМ БУДЕТ ЗАПУЩЕН SDK (пакет средств разработки ПО)

Выберите, запускать ли SDK (пакет средств разработки ПО) в глобальном классе `Application` или в классе `Activity`:

* **Запустите SDK (пакет средств разработки ПО) в глобальном классе** **: Обычно инициализация SDK (пакет средств разработки ПО) в глобальном классе или подклассе `Application` считается хорошей практикой, так как класс `Application` загружается и инициализируется до отображения UI Приложения. Это гарантирует, что SDK (пакет средств разработки ПО) может быть запущен в любых условиях, включая диплинкинг.**
* <strong>Запустите SDK (пакет средств разработки ПО) в классе</strong> (отложенный запуск)<strong> , чтобы пользователи могли дать согласие на обмен данными. Это связано с тем, что для получения согласия пользователя требуется UI, который отображается в классе `Activity`.</strong>

#### ИНСТРУКЦИИ ДЛЯ РАЗРАБОТЧИКОВ ANDROID

* Сообщите разработчику о вашем решении по следующим моментам:
  * В каком классе, `Application` или `Activity`, запускать SDK (пакет средств разработки ПО)?
  * Какой сценарий согласия/отказа использовать?
* Отправьте разработчику следующую ссылку:
  * [Как выполнить отложенный запуск](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)

</Tab>

<Tab title="Android native iOS native Unity React Native">

<div id="starting-the-sdk-in-ios" />

### Запуск SDK (пакет средств разработки ПО) в нативной среде iOS

<div id="delay-the-sdk-start-in-ios" />

#### ОТЛОЖИТЬ ЗАПУСК SDK (пакет средств разработки ПО) В IOS

При планировании запуска SDK (пакет средств разработки ПО) важно учесть, стоит ли откладывать `start` до получения согласия пользователя.

SDK (пакет средств разработки ПО) предоставляет метод `waitForATTUserAuthorization`, который позволяет **настроить, сколько времени SDK должен ожидать согласия пользователя перед отправкой данных на сервера AppsFlyer**.

Для получения дополнительной информации о потоке данных метода и его взаимодействии с фреймворком iOS ATT, см. раздел [Настройка поддержки App Tracking Transparency (ATT)](/docs/basic-sdk-integration-guide#обзор-waitforattuserauthorization).

<div id="ios-developer-instructions" />

#### ИНСТРУКЦИИ ДЛЯ РАЗРАБОТЧИКОВ IOS

Сообщите вашему разработчику следующую информацию:

* Сколько секунд должно пройти до отправки данных в AppsFlyer?
* Ссылки для разработчиков:
  * [Запуск iOS SDK (пакет средств разработки ПО)](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk) для руководства разработчика и справочной информации о запуске SDK.
  * [Настройка поддержки App Tracking Transparency (ATT)](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support) для получения информации о том, как поток данных метода [взаимодействует с фреймворком iOS ATT](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support)
  * [Включение поддержки App Tracking Transparency (ATT)](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support) для руководства разработчика и справочной информации по

</Tab>

<Tab title="Unity">

<div id="starting-the-sdk-in-Unity" />

### Запуск SDK (пакет средств разработки ПО) в Unity

Отправьте вашему разработчику <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration">эту статью на Dev Hub</Anchor> о запуске SDK (пакет средств разработки ПО).

</Tab>

<Tab title="iOS native UnityReact Native">

<div id="starting-the-sdk-in-react" />

### Запуск SDK (пакет средств разработки ПО) в React Native

Отправьте вашему разработчику <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#startsdk">эту статью на Dev Hub</Anchor> о запуске SDK (пакет средств разработки ПО).

</Tab>
</Tabs>

## Выберите стратегию сохранения конфиденциальности

Выберите **способ защиты конфиденциальности пользователя.** Например, выберите между остановкой SDK (пакет средств разработки ПО) при установке, предотвращением передачи данных третьим лицам, анонимизацией пользовательских данных или отключением определённых идентификаторов.

Для получения дополнительной информации о различных методах защиты конфиденциальности смотрите <Anchor target="_blank" href="/marketers/ru/docs/apply-privacy-preserving-sdk-methods">Методы защиты конфиденциальности в SDK (пакет средств разработки ПО)</Anchor>.

## **Атрибуция**

SDK (пакет средств разработки ПО) собирает <Anchor target="_blank" href="/marketers/ru/docs/about-device-identifiers">идентификаторы</Anchor> для целей атрибуции. Чтобы установки были зарегистрированы и корректно атрибутированы, изучите и следуйте этим рекомендациям.

**Все платформы**

<Accordion title="Уникальный идентификатор для установок">

Идентификатор AppsFlyer создается автоматически при каждой новой установке приложения. Маркетологу не требуется выполнять никаких действий.

Вы можете использовать этот идентификатор для выполнения следующих действий:

* Отправлять <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">внутренние события от сервера к серверу</Anchor>.
* Свяжите идентификатор AppsFlyer с пользовательскими записями в ваших бэкенд-системах.
* Загружайте <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview">отчет о необработанных данных о событиях в приложении</Anchor> и используйте **appsflyer\_id** для анализа поведения и путей пользователей.

</Accordion>

<Accordion title="Интегрируйте уникальные идентификаторы из системы бизнес-аналитики с AppsFlyer.">

Установите собственный идентификатор пользователя клиента (CUID) в SDK (пакет средств разработки ПО) AppsFlyer, чтобы соотносить уникальный идентификатор из вашей системы бизнес-аналитики с идентификатором AppsFlyer и другими идентификаторами. CUID доступен в отчётах о <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary">необработанных данных</Anchor> AppsFlyer. Вы также можете использовать его в постбэк API для связи с вашими внутренними идентификаторами.

Чтобы узнать больше о CUID, смотрите <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid">эту статью.</Anchor>

</Accordion>

**Только для Android**

В следующих разделах рассматриваются аспекты атрибуции для Google Play Store или сторонних магазинов приложений.

<Accordion title="Атрибуция приложений, опубликованных в Google Play">

#### Реферал установки в GOOGLE PLAY

API [Google Play Install Referrer](https://developer.android.com/google/play/installreferrer) улучшает точность <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#методы-атрибуции">атрибуции</Anchor>, защищает от мошеннических установок и обеспечивает безопасное извлечение данных о переходах из Google Play (например, версию приложения на момент его первой установки).

Рекомендуется предоставить разработчику [указания по добавлению API Google Play Install Referrer](https://developer.android.com/google/play/installreferrer/library).

#### ГАИД

Начиная с версии SDK (пакет средств разработки ПО) 4.8.0, AppsFlyer автоматически собирает этот идентификатор устройства.

</Accordion>

<Accordion title="Атрибуция приложений в сторонних магазинах">

С помощью AppsFlyer вы можете <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution">атрибутировать установки, поступающие из сторонних магазинов приложений</Anchor>, таких как Amazon, Opera, GetJar, Baidu и Huawei. Это позволяет вам продвигать приложения и охватывать большие аудитории на рынках, где Google Play недоступен.

AppsFlyer поддерживает атрибуцию в контексте сторонних магазинов приложений следующим образом:

* **IMEI или идентификатор Android:** SDK (пакет средств разработки ПО) не осуществляет автоматический сбор IMEI или идентификатора Android. Однако, если необходимо собирать эти идентификаторы (например, для <Anchor target="_blank" href="/marketers/ru/docs/measure-attribution-in-the-chinese-domestic-market#атрибуция-приложений-android-на-внутреннем-рынке-китая">приложений на внутреннем рынке Китая</Anchor>), разработчик может реализовать один из следующих способов сбора:
  * Ручной сбор данных: Приложение передает IMEI или идентификатор Android в SDK (пакет средств разработки ПО) с использованием API `setImeiData` или `setAndroidIdData` (см. раздел о функции на вкладках ниже). SDK (пакет средств разработки ПО) отправляет данные на серверы AppsFlyer.

    <Tabs>
    <Tab title="Android iOS">

    См. справочник по Android SDK:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>

    <Tab title="Unity">

    См. справочник по Unity SDK:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>
    </Tabs>

  * Дайте согласие на сбор идентификатора устройства: Принудительно осуществляет сбор IMEI или идентификатора Android с использованием setCollectIMEI и setCollectAndroidID (см. раздел о функции на вкладках ниже).

    <Tabs>
    <Tab title="Android iOS">

    См. справочник по Android SDK:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>

    <Tab title="Unity">

    См. справочник по Unity SDK:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>

    <Tab title="Android native UnityReact Native">

    См. справочник по React Native:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>
    </Tabs>

* **OAID:** Атрибуция установок из сторонних магазинов приложений Android. Для получения дополнительной информации см. <Anchor target="_blank" href="/marketers/ru/docs/android-oaid-implementation-in-the-sdk">руководство по внедрению OAID</Anchor>.
* **Рефереры установки:** SDK (пакет средств разработки ПО) поддерживает получение реферальных данных из Samsung Gallery и Huawei AppGallery.

</Accordion>

**Только для iOS**

Следующие разделы содержат важную информацию о поддержке Устройств iOS 14+.

<Accordion title="Настройка поддержки App Tracking Transparency (ATT)">

**ОБЩИЕ СВЕДЕНИЯ**

Начиная с iOS 14.5, для сбора IDFA требуется согласие пользователя. На практике это означает, что доступ к IDFA регулируется фреймворком [**App Tracking Transparency**](https://developer.apple.com/documentation/apptrackingtransparency) (ATT). На Устройствах iOS 14+ SDK (пакет средств разработки ПО) использует фреймворк ATT для получения доступа к идентификатору устройства IDFA. Для введения в ATT см. <Anchor target="_blank" href="/marketers/ru/docs/about-att-and-skan#att-principles">принципы ATT</Anchor>.

<Tabs>
<Tab title="Android native iOS native Unity React Native">

См. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support">инструкции для разработчиков по внедрению ATT</Anchor> в хабе для разработчиков.

</Tab>

<Tab title="Unity">

См. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager">инструкции для разработчиков по внедрению ATT</Anchor> в хабе для разработчиков.

</Tab>
</Tabs>

Когда Атрибуция осуществляется с использованием IDFA, важно, чтобы IDFA был отправлен при **первом запуске. `waitForATTUserAuthorization`По этой причине SDK (пакет средств разработки ПО) предоставляет метод `waitForATTUserAuthorization`.**

#### Обзор waitForATTUserAuthorization

> 🚧 **Important**
>
> Не вызывайте `waitForATTUserAuthorization`, если вы не собираетесь использовать запрос ATT.

`waitForATTUserAuthorization` позволяет вам настроить, как долго SDK (пакет средств разработки ПО) должен ожидать статус ATT перед передачей данных на серверы AppsFlyer.

![](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)

Когда пользователь запускает Приложение, статус ATT — **не определен.** В течение [тайм-аута SDK (пакет средств разработки ПО) временно сохраняет событие запуска и последующие события в Приложении в памяти, аналогично тому, как записываются](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events) [офлайн-события](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events):

* Если пользователь **дает согласие** на запрос ATT (сбор IDFA):
  * SDK добавляет IDFA к закэшированным событиям.
  * SDK запускается и отправляет события с IDFA без ожидания окончания тайм-аута.
* Если пользователь **отклоняет** запрос ATT: SDK запускается и отправляет события без IDFA без ожидания окончания тайм-аута.
* Если тайм-аут заканчивается, а статус ATT остается **не определен:** SDK запускается и отправляет закэшированные события без IDFA.

**Соображения**

* Вызов  без предварительной настройки [приведет к отправке запусков и событий без IDFA для Устройств на iOS 14 и выше.](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization)
* Если пользователь переводит Приложение в фоновый режим в течение тайм-аута:
  * Таймер приостанавливается, пока Приложение не вернется на передний план.
  * События временно сохраняются в памяти.
* Если пользователь закрывает Приложение и оно завершает работу в течение тайм-аута:
  * Таймер перезапустится при следующем запуске Приложения.
  * Закэшированные события теряются.

</Accordion>

<Accordion title="Настройка окна согласия ATT">

Вы можете настроить запрос ATT. Сообщение, четко объясняющее цель запроса, может помогать увеличить процент согласий пользователей.

При создании сообщения учтите следующее:

* Использовать такую формулировку, которая наилучшим образом объясняет пользователям, почему Приложение запрашивает их согласие.
* Сообщите пользователям, как будут использоваться их данные. [Узнать больше о конфиденциальности пользователей и использовании данных.](https://developer.apple.com/app-store/user-privacy-and-data-use/)

После подготовки вашего сообщения предоставьте его разработчику вместе с инструкциями по его внедрению.

<Tabs>
<Tab title="Android native iOS native Unity React Native">

См. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">инструкции для разработчиков по настройке окна согласия на ATT</Anchor> в хабе для разработчиков.

</Tab>

<Tab title="Unity">

См. [инструкции для разработчиков по настройке окна согласия на ATT](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager) в хабе для разработчиков.

</Tab>
</Tabs>

</Accordion>

<Accordion title="Поддержка атрибуции в SKAN">

> 📘 **Note**
>
> Для полной поддержки атрибуции SKAN обновите iOS SDK (пакет средств разработки ПО) до версии V6.2.3+.

SKAN — это класс, используемый iOS для проверки установок приложений, инициированных рекламодателями. Процесс проверки установки приложения включает в себя приложение-источник и рекламируемое приложение.

Приложение-источник — это приложение, участвующее в рекламных кампаниях и показывающее рекламу из рекламной сети. Настройка вашего приложения для показа рекламы не входит в задачи SDK AppsFlyer. Для настройки следуйте [инструкциям Apple](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app).

Для рекламируемого приложения (приложения с SDK AppsFlyer) решение <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">SKAN</Anchor> от AppsFlyer использует SKAN для предоставления постбэков об атрибуции, при этом AppsFlyer собирает, преобразует и агрегирует данные, сохраняя конфиденциальность пользователя. При первом запуске приложения платформа AppsFlyer, используя конфигурацию, заданную маркетологом, указывает SDK, как установить значение конверсии SKAN.

Чтобы использовать решение SKAN:

* Маркетолог должен настроить измерение SKAN в AppsFlyer. Разработчику не нужно предпринимать никаких действий.
* SDK AppsFlyer автоматически вызывает необходимые API SKAN.
* Обязательно отключите вызовы SKAN в других SDK, если вы полагаетесь на AppsFlyer для атрибуции SKAN.
* Никаких дополнительных действий или процесса регистрации в магазине приложений ни от разработчика, ни от маркетолога не требуется.

Чтобы отключить атрибуцию SKAN, попросите разработчика выключить её в SDK.

<Tabs>
<Tab title="Android native iOS native Unity React Native">

Чтобы отключить атрибуцию SKAN, используйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork">`disableSKAdNetwork`</Anchor>

</Tab>

<Tab title="Unity">

Чтобы отключить атрибуцию SKAN, используйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#disableskadnetwork">`disableSKAdNetwork`</Anchor>

</Tab>

<Tab title="Примечание">

Чтобы отключить атрибуцию SKAN, используйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#disableskad">`disableSKAd`</Anchor>

</Tab>
</Tabs>

</Accordion>

## **Регистрация внутренних событий приложения**

События в приложении (IAE) дают понимание о том, что происходит в вашем приложении. Запись событий в приложении помогает измерять такие KPI, как ROI (окупаемость инвестиций) и LTV. Мы рекомендуем выделить время для определения событий, которые необходимо записывать.

Когда вы определите, какие внутренние события требуется измерять, отправьте своему разработчику имена и параметры этих событий, а также ссылку на:

* [Мастер установки SDK](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration), который формирует специальный путь для внутренних событий приложения.
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">Пошаговые инструкции по реализации внутренних событий приложения в SDK</Anchor>.

Чтобы узнать, как определить события в приложении и отправить их своему разработчику, см. наше <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview">Руководство по насыщенным внутренний событиям</Anchor>.

**Все платформы**

<Accordion title="Запись выручки">

Вы можете отправлять доход с любым внутренним событием. Обязательно используйте параметр **af\_revenue** для включения выручки. Это единственный параметр события, который AppsFlyer считает реальной выручкой на дэшборде и в отчетах о необработанных данных. <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#revenue-events">Подробнее</Anchor>.

<Tabs>
<Tab title="Android iOS">

Инструкции для разработчиков по определению событий дохода см. [здесь](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue).

</Tab>

<Tab title="Android native iOS native Unity React Native">

Инструкции для разработчиков по определению событий дохода см. [здесь](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue).

</Tab>

<Tab title="Unity">

* Общие инструкции для разработчиков по внутренним событиям см. [здесь](https://dev.appsflyer.com/hc/docs/inappevents#send-event).
* Конкретные инструкции по получению выручки в iOS и Android см. на вкладках Android и iOS.

</Tab>
</Tabs>

</Accordion>

<Accordion title="Подтверждение покупок в приложении">

AppsFlyer SDK предоставляет проверку сервера для покупок в приложении. Валидация покупки в приложении автоматически отправляет событие покупки в приложении в AppsFlyer. Самостоятельная отправка этого события создает дублирующую отчетность о событии.

</Accordion>

<Accordion title="Отраслевые вертикали">

Ознакомьтесь с нашим <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#recommended-events-by-business-vertical">списком рекомендуемых событий в приложении для различных отраслей</Anchor>, например, для путешествий, гейминга или электронной коммерции.

</Accordion>

## **Диплинкинг с помощью OneLink**

OneLink — это решение AppsFlyer для многоплатформенной атрибуции, **перенаправления и диплинкинга**.

**Все платформы**

<Accordion title="Определение устройства и перенаправление">

Для пользователей, у которых не установлено ваше приложение, OneLink определяет тип устройства и перенаправляет их на правильный ресурс (например, Google Play, магазин приложений Apple, сторонний магазин приложений или веб-страницу). Это основано на настройках вашего шаблона OneLink. <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template">Узнать больше</Anchor>

</Accordion>

<Accordion title="Диплинкинг">

Если у пользователя установлено ваше приложение, OneLink открывает его. Вы также можете направлять пользователей на определённую активность или страницу в приложении, используя диплинкинг. Для этого вашему разработчику нужно реализовать унифицированный диплинкинг (UDL) с помощью:

* [Мастера установки SDK](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration), который формирует специальный путь для реализации диплинкинга; или
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Пошаговые инструкции по реализации SDK для унифицированного диплинкинга</Anchor>.

**Примечание**:

* Для UDL требуется SDK V6.1 или позже.
* Клиенты, уже использующие OneLink для диплинкинга, могут применять [устаревший метод](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking) вместо UDL.

Смотрите наше руководство по настройке <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">диплинкинга и отложенного диплинкинга</Anchor>.

</Accordion>

<Accordion title="Отложенная глубинная ссылка (диплинкинг)">

Для пользователей, у которых не установлено ваше приложение, OneLink определяет тип устройства и перенаправляет их на нужный ресурс: Google Play, магазин приложений Apple, сторонний магазин приложений или веб-страница. После запуска приложения пользователем вы можете использовать отложенный диплинкинг для перехода к конкретной активности или странице в приложении.

Для этого вашим разработчикам нужно внедрить метод расширенного отложенного диплинкинга с помощью:

* [Мастера установки SDK](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration), который формирует специальный путь для реализации диплинкинга; или
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">Пошаговые инструкции по реализации SDK для отложенного диплинкинга</Anchor>.

**Примечание**:

* Для UDL требуется SDK V6.1 или позже.
* Клиенты, уже использующие OneLink для отложенного диплинкинга, могут применять [устаревший метод](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking) вместо UDL.

Смотрите наше руководство по настройке <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">диплинкинга и отложенного диплинкинга</Anchor>.

</Accordion>

## **Доступ к данным атрибуции и диплинкинга**

В следующей таблице описаны доступные методы для извлечения данных атрибуции и диплинкинга:

| Метод | Кто участвует? | Возврат результатов | Метод извлечения | Данные атрибуции | Данные глубинных ссылок | Доступность |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ru/docs/push-api-streaming-raw-data">**push**</Anchor> | • Маркетолог • Бэкенд-разработчик | Обычно в течение нескольких минут | Обработка на стороне сервера | Д | Н | Категория "Премиум" |
| <Anchor target="_blank" href="/marketers/ru/docs/pull-api-raw-data">**Pull API**</Anchor> | • Маркетолог • Бэкенд-разработчик | • Периодически (не в режиме реального времени). • Вы можете запланировать загрузку отчетов с необработанными данными. | Обработка на стороне сервера | Д | Д | Категория "Премиум" для отчетов по необработанным данным |
| <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers">**Отчет Data Locker**</Anchor> | • Маркетолог • Бэкенд-разработчик | Почасовые отчеты доступны в течение 1–3 часов. | Облачное хранилище через один из следующих вариантов: • Владельческое хранилище AppsFlyer на AWS • Хранилище, принадлежащее вам (AWS или GCS) | Д | Д | Категория "Премиум" |
| <Anchor target="_blank" href="/marketers/ru/docs/conversion-data-payloads-and-scenarios#обзор">**Получение данных о конверсиях (GCD)**</Anchor> | • Маркетолог • Мобильный разработчик <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">См. документацию разработчика</Anchor> | До 5 секунд | SDK (пакет средств разработки ПО) | Д | Д | Все аккаунты |
| <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template">**Унифицированный диплинкинг (UDL)**</Anchor> | • Маркетолог • Мобильный разработчик <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">См. документацию разработчика</Anchor> | До 1 секунды | SDK (пакет средств разработки ПО) | Н | Д | Все аккаунты |

Обратите внимание на следующее для пользователей iOS 14.5+, не давших согласия:

* При использовании UDL для платных и собственных медиа доступны данные о диплинкинге.
* При использовании GCD для платных медиа данные ограничены и не включают информацию об атрибуции и диплинкинге.

> 👍 **Tip**
>
> Мы рекомендуем следующее:
>
> * Использовать push для получения данных атрибуции и отправки их на ваши серверы для дальнейшей обработки. Этот метод ожидает, пока данные не станут доступными, и поэтому обладает высокой точностью и приближен к реальному времени. GCD возвращает данные в реальном времени, но они могут быть неточными, если окончательные решения по атрибуции принимаются более чем через 5 секунд.
> * Использовать Pull API для периодического (например, ежедневного) дополнения данных атрибуции в реальном времени и компенсации возможных ошибок связи.

## **Тестирование интеграции SDK**

После завершения интеграции SDK вы можете перейти в дэшборд AppsFlyer и на странице тестирования интеграции SDK провести тестирование органических и неорганических установок, событий в приложении и диплинкинга (ретаргетинг). Это гарантирует, что установки и события в приложении корректно регистрируются и атрибутируются.

См. тестовые сценарии и инструкции в разделе <Anchor target="_blank" href="/marketers/ru/docs/testing-the-sdk-integration-for-marketers">Тестирование интеграции SDK</Anchor>.

**Примечание:** При выполнении тестов атрибуции <Anchor target="_blank" href="/marketers/ru/docs/registering-test-devices">зарегистрируйте тестовое устройство</Anchor> (Android или iOS), чтобы каждая установка регистрировалась как новая установка. Зарегистрированное тестовое устройство предотвращает регистрацию установок как переустановок.

> 📘 **Note**
>
> **См. также**
>
> * Обзор платформ CTV, ПК и консолей

<div data-zendesk-anchors="retrieving-the-dev-key=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-%D0%B2-%D0%B2%D0%B0%D1%88%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 h_01HAWCK9K4QBRE74JAS8Q7MEXW=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-%D0%B2-%D0%B2%D0%B0%D1%88%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 retrieve-the-dev-key=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0 h_01HHHKTARNPQTBXQ6CQGEHMJRG=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0 embed-the-dev-key=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-%D0%B2%D0%B0%D1%88%D0%B5%D0%BC%D1%83-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D1%83 h_01HHHKXMBGV6EM0CCW842RQQZ6=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-%D0%B2%D0%B0%D1%88%D0%B5%D0%BC%D1%83-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D1%83 where-to-start-the-sdk=%D1%81-%D1%87%D0%B5%D0%B3%D0%BE-%D0%BD%D0%B0%D1%87%D0%B0%D1%82%D1%8C-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-sdk h_01HAWCK9K4MBS0F0HE6QE1W1AN=%D1%81-%D1%87%D0%B5%D0%B3%D0%BE-%D0%BD%D0%B0%D1%87%D0%B0%D1%82%D1%8C-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-sdk starting-the-sdk-in-android=%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%B0-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2-%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B9-%D1%81%D1%80%D0%B5%D0%B4%D0%B5-android h_01HAWCK9K45HCJEDRW761WHKES=%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%B0-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2-%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B9-%D1%81%D1%80%D0%B5%D0%B4%D0%B5-android select-in-what-class-to-start-the-sdk=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D0%BA%D0%BB%D0%B0%D1%81%D1%81-%D0%B2-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D0%BE%D0%BC-%D0%B1%D1%83%D0%B4%D0%B5%D1%82-%D0%B7%D0%B0%D0%BF%D1%83%D1%89%D0%B5%D0%BD-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE h_01HAWCK9K428SDFBFCCSZ15X9J=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D0%BA%D0%BB%D0%B0%D1%81%D1%81-%D0%B2-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D0%BE%D0%BC-%D0%B1%D1%83%D0%B4%D0%B5%D1%82-%D0%B7%D0%B0%D0%BF%D1%83%D1%89%D0%B5%D0%BD-sdk-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82-%D1%81%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B2-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%BF%D0%BE android-developer-instructions=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2-android h_01HAWCK9K4XR1HZHP7Y15Q2Q4N=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2-android h_01HAWCK9K4693729EX1WYFR6XT=starting-the-sdk-in-ios h_01HAWCK9K4QSBP874RX2ZRA7EB=delay-the-sdk-start-in-ios h_01HAWCK9K4VHDFB9CYHC144BZN=ios-developer-instructions h_01JQ73M8DWMVQ98V1DQMPT0316=starting-the-sdk-in-Unity h_01JQ73M8DW350GBH9P52W4516V=starting-the-sdk-in-react select-the-optoutin-scenario::ae4c6e25=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D1%81%D1%82%D1%80%D0%B0%D1%82%D0%B5%D0%B3%D0%B8%D1%8E-%D1%81%D0%BE%D1%85%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HAWCK9K4EXBA2F0BPVBXFAMG=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D1%81%D1%82%D1%80%D0%B0%D1%82%D0%B5%D0%B3%D0%B8%D1%8E-%D1%81%D0%BE%D1%85%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F h_01HAWCK9K41T5GGWDB3ABYGRHW=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F google-play-install-referrer=%D1%80%D0%B5%D1%84%D0%B5%D1%80%D0%B0%D0%BB-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%B2-google-play h_01HAWCK9K4V91MPQHXDZBD0HKR=%D1%80%D0%B5%D1%84%D0%B5%D1%80%D0%B0%D0%BB-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%B2-google-play gaid=%D0%B3%D0%B0%D0%B8%D0%B4 h_01HAWCK9K4YD8CYQDB2YRA8W1F=%D0%B3%D0%B0%D0%B8%D0%B4 waitforattuserauthorization-overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80-waitforattuserauthorization h_01HAWCK9K5JHDWS8KTBTTGSS9G=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80-waitforattuserauthorization recording-inapp-events=%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HAWCK9K5ZZYQR8KPCWANZEA5=%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F deep-linking-with-onelink=%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink h_01HAWCK9K5PK9RE7WZQVCY97KC=%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink accessing-attribution-and-deep-linking-data=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF-%D0%BA-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B8-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0 h_01HAWCK9K5ACPZ2WKBTVR3VVTD=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF-%D0%BA-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B8-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0 testing-your-sdk-integration=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-sdk h_01HAWCK9K6JQ33T32RYKYH20P1=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-sdk" />

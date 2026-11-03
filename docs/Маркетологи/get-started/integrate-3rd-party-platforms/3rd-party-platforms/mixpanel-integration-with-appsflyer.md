---
title: Интеграция Mixpanel с AppsFlyer
metadata:
  keywords:
    - Attribution
    - Mixpanel
    - SDK
    - integrated partner
    - Advertisers
    - Ad Networks
    - facebook mixpabel
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
  created_at: '2015-12-24T11:33:01Z'
  edited_at: '2026-08-19T00:11:29Z'
  id: 207447103
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/207447103
---
> **Необходимые условия:** Перед настройкой интеграции обязательно <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">свяжитесь с партнером</Anchor> и откройте у него аккаунт.

![](https://cdn.appsflyer.com/marketplace/static/logo/mixpanel.png)

Интеграция между AppsFlyer и Mixpanel позволяет импортировать информацию о кампаниях по привлечению из AppsFlyer в Mixpanel.

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиаисточники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.

## Настройка Mixpanel

**Необходимые условия:** Перед настройкой интеграции обязательно [свяжитесь с партнёром](#) и откройте у него аккаунт. Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В AppsFlyer в боковом меню выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.  
    **Примечание.** Этот переключатель должен быть включен <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">(активирован)</Anchor> все время, пока вы работаете с этим партнером.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Для подробного описания заголовка окна для конфигурации партнера, нажмите <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

### Общие настройки

<Image alt="mixpanel-general-settings.png" src="https://files.readme.io/df1b95eb3926aa7e10db338f156a87b88aabda6b97a4d28db2953e9e48a114e6-360017400598.png" width="542px" />

* **Локализация данных в ЕС**: AppsFlyer по умолчанию отправляет данные на американские серверы Mixpanel. Чтобы отправить данные на серверы Mixpanel в ЕС, включите этот переключатель.  
  **\*Токен**: Mixpanel подключается к AppsFlyer с помощью уникального токена. Если у вас его еще нет, вы должны получить его от Mixpanel, чтобы продолжить интеграцию.

  **Чтобы получить токен от Mixpanel:**

  1. Войдите в свой аккаунт Mixpanel по адресу: https://mixpanel.com/login/.
  2. В **Mixpanel** перейдите на панель **анализа** и нажмите на значок шестеренки.

     ![mixpanel-token-1.png](https://files.readme.io/f1fbc76fff621e12a7d91fed5ba49eb20f2b049de65c70b0ab32cadd997287d2-small-360014578477.png)
  3. Скопируйте свой токен из раздела «Ключи доступа» вашего проекта и вставьте его в поле **токена** на вкладке интеграции AppsFlyer с Mixpanel.

     ![mixpanel-token-2.png](https://files.readme.io/e8e633ec87d963244652a53b9b21c495b0a850e234621a44d93b3034c640bff7-360014578757.png)
* **Отправить ID рекламодателя**:
  * Если вы используете параметр AppsFlyer customer\_user\_id, то он будет отправляться в Mixpanel при каждой установке (оставьте опцию **Отправить ID рекламодателя** отключенной).
  * Если вы не используете AppsFlyer customer\_user\_id, включите опцию **Отправить ID рекламодателя**. Идентификатор устройства отправляется в Mixpanel как customer\_user\_id (unique\_id в Mixpanel).  
    Узнайте больше в руководстве по интеграции AppsFlyer SDK для <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">Android</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">iOS</Anchor>.
* **События:** Включите, чтобы отправлять данные об установке на конечную точку Mixpanel Events.
* **Люди:** Включите этот параметр, чтобы отправлять данные об установке на конечную точку Mixpanel People.

  > 📘 **Примечание**
  >
  > Чтобы постбэки по установкам отправлялись в Mixpanel, должна быть включена хотя бы одна из двух конечных точек — **Events** (События) или **People** (Люди).

* **Расширенный обмен данными:** Включите эту опцию, чтобы отправить в Mixpanel дополнительную информацию: c (кампания), network (pid), impression\_based (is-impression).

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки в Mixpanel после установок приложения пользователями, включая события установки и повторного вовлечения. Повторные вовлечения происходят, когда пользователь, у которого уже установлено приложение, открывает его после перехода по ссылке в кампании. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэках по умолчанию</Anchor>.

[![](https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png)](https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png)

### Настройки внутренних событий приложения

![mixpanel-in-app-events-settings.png](https://files.readme.io/db5e4e6d5bbe084a94b90425d49345511c214ddc39380a2b8419659ad752cdb2-360014576637.png)

В этом разделе можно сопоставить события в AppsFlyer с событиями в Mixpanel и настроить отправку постбэков.

> 📘 **Примечание**
>
> Mixpanel фиксирует события в приложении с помощью собственного SDK. Единственное событие, которое можно отправить в Mixpanel и которое не фиксируется ими, — это af\_uninstall.

Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">постбэках по внутренним событиям приложения</Anchor>.

**Чтобы настроить постбэки по событиям внутри приложения:**

1. Введите токен Mixpanel.
2. Включите Постбэки по внутренним событиям.
3. **Чтобы отправить идентификатор рекламодателя при удалении**, включите опцию **Отправить идентификатор рекламодателя**.
4. **Чтобы отправить дополнительную информацию об удалении**, включите функцию **Расширенный обмен данными**.
5. Чтобы добавить в список событие, определенное в SDK, нажмите **Добавить событие**.
6. Выберите **af\_uninstall** из выпадающего меню.
7. Выберите соответствующий **идентификатор события партнера** из выпадающего меню.
8. Выберите нужный вариант в раскрывающемся меню «Отправить доход»:
   * **Нет значений и нет дохода:** отправляет только само событие без значения.
   * **Значения, нет дохода:** отправляет все параметры, кроме значения дохода.
   * **Значения и доход**: отправляет все параметры события, включая значение дохода (если оно есть в событии).
9. Чтобы завершить настройку интеграции, нажмите кнопку **Сохранить интеграцию**.

После сохранения интеграции AppsFlyer отправляет в Mixpanel следующие данные для каждой органической и неорганической установки:

* Параметр токена Mixpanel
* Customer\_user\_id или ID устройства (IDFA / Google Advertising ID)
* Медиа-источник
* Название кампании

**Примечание**: CUID не отправляется в постбэках об удалениях.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для этого партнера.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнером.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнером.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для этого партнера.

</Accordion>

## Интеграция с Mixpanel при использовании механизма входа в систему

Ниже показан пример шагов интеграции:

1. Приложение было запущено (открыто) пользователем.
2. Mixpanel SDK генерирует случайный собственный идентификатор **(distinct\_id**).
3. Получите собственный идентификатор Mixpanel и установите его в качестве идентификатора клиента (CUID) с помощью функции SDK Appsflyer **setCustomerUserId**.
4. Отправьте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#start">**Start**</Anchor>. Этот API дает возможность АppsFlyer отслеживать установки, сеансы и обновления.
5. Когда установка приложения атрибутирована, в Mixpanel отправляется событие **установки** с идентификатором клиента, который включает в себя собственный идентификатор Mixpanel.
6. Когда пользователь регистрируется или входит в систему, вызывается команда Mixpanel identify() с идентификатором пользователя (например, электронной почтой или идентификатором клиента). В результате первоначальный случайный идентификатор будет сопоставлен с идентификатором зарегистрированного пользователя.

   <Tabs>
   <Tab title="Android">

   Mixpanel Android — <Anchor target="_blank" href="https://developer.mixpanel.com/docs/android#section-combining-anonymous-and-identifiable-user-data">объединение анонимных и идентифицируемых пользовательских данных</Anchor>

   ```java
   MixpanelAPI mixpanel = MixpanelAPI.getInstance(context, MIXPANEL_TOKEN);
   mixpanel.identify("user@example.com");

   // Mixpanel v6.2.0 and below should use the following API:
   mixpanel.getPeople().identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Objective C">

   Mixpanel iOS Objective C — <Anchor target="_blank" href="https://developer.mixpanel.com/docs/ios#section-combining-anonymous-and-identifiable-user-data">объединение анонимных и идентифицируемых пользовательских данных</Anchor>

   ```objectivec
   [mixpanel identify:@“user@example.com”];
   ```

   </Tab>

   <Tab title="Swift">

   Mixpanel iOS Swift — [объединение анонимных и идентифицируемых пользовательских данных](https://developer.mixpanel.com/docs/swift#section-combining-anonymous-and-identifiable-user-data)

   ```swift
   mixpanel.identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Unity">

   Mixpanel Unity — [объединение анонимных и идентифицируемых пользовательских данных](https://developer.mixpanel.com/docs/unity#section-combining-anonymous-user-data-with-identifiable-user-data)

   ```csharp
   // set customer user id or device id
   Mixpanel.Identify(“user@example.com”);
   ```

   </Tab>
   </Tabs>

7. Mixpanel получает customer\_user\_id из AppsFlyer с псевдонимом идентификатора пользователя (например, адрес электронной почты).

> 📘 **Примечание**
>
> Если вы не используете процесс регистрации в своем приложении, выполните шаги 1-3, как описано выше.

## Просмотр данных AppsFlyer в Mixpanel

На скриншотах ниже представлен отчет «Воронка», в котором показана конверсия с момента установки до завершения события с разбивкой по медиа-источникам. Кроме того, можно увидеть время до совершения конверсии для каждого медиа-источника.

[![](https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png)](https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png)

[![](https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png)](https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png)

<div data-zendesk-anchors="h_01H9FKEWTEN4F8FM5C9A9ES6HN=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-mixpanel=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-mixpanel h_01H9FKEWTEGMEVH3SK739DD719=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-mixpanel h_01H9FKEWTE90WR75PMNN93JAXE=integration-tab general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FKEWTEMT7VGTTFWFMJHYA8=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FKEWTEV3RWKMWZN0EXFFNP=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKEWTER31RXAH216TRXQPM=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FKEWTERRVKPQFF1B8QQERE=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FKEWTEEMMQ0KKRZXRJRE25=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01H9FKEWTEEQ0GHF87V20TX9W0=attribution-link-tab h_01H9FKEWTEJ61197SN3R6JXYCP=cost-tab h_01H9FKEWTEA7GN2HHK3QD62A3A=ad-revenue-tab h_01H9FKEWTET4QD1RE0HJZM64D4=permissions-tab integrating-with-mixpanel-when-using-a-login-mechanism=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81-mixpanel-%D0%BF%D1%80%D0%B8-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BC%D0%B5%D1%85%D0%B0%D0%BD%D0%B8%D0%B7%D0%BC%D0%B0-%D0%B2%D1%85%D0%BE%D0%B4%D0%B0-%D0%B2-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D1%83 h_01H9FKEWTE9DEANTXKPD286GD2=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81-mixpanel-%D0%BF%D1%80%D0%B8-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BC%D0%B5%D1%85%D0%B0%D0%BD%D0%B8%D0%B7%D0%BC%D0%B0-%D0%B2%D1%85%D0%BE%D0%B4%D0%B0-%D0%B2-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D1%83 h_01H9FKEWTFZ107Y999WEMB3409=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 viewing-appsflyer-data-in-mixpanel=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%B2-mixpanel h_01H9FKEWTF9PFNVHTZGDKBX75Y=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%B2-mixpanel" />

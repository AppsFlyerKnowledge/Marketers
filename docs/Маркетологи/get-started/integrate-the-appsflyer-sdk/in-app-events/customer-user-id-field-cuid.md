---
title: Поле идентификатора пользователя клиента (CUID)
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
    - Advertisers
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
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2026-09-23T00:06:16Z'
  id: 207032016
  locale: ru
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ru/articles/207032016
---
> **At a glance:** CUID позволяет объединять события одного и того же пользователя на различных устройствах, источниках медиа или каналах.

## Что такое CUID?

Идентификатор пользователя клиента (CUID) — это уникальный идентификатор пользователя. Обычно владелец приложения генерирует и задаёт его во время регистрации пользователя. CUID позволяет владельцам приложений отслеживать действия пользователей на различных устройствах.

> 📘 **Например**
>
> У пользователя с двумя или более устройствами один и тот же CUID во всех приложениях. Каждый раз, когда пользователь выполняет событие на мобильном или настольном устройстве, SDK фиксирует событие вместе с CUID. Это позволяет рекламодателю объединить данные устройств в целостное представление о пользователе.
>
> Несколько примеров использования:
>
> * Покупки в приложении, совершённые одним и тем же пользователем в одном и том же приложении на нескольких устройствах (телефон, планшет, ТВ, настольный компьютер), можно объединить в единое представление.
> * Вы можете объединять данные об активности пользователей на разных платформах (компьютерах, мобильных устройствах и телевизорах), чтобы получить целостное представление о пользовательском опыте.

## Установка CUID

Рекомендуется задавать CUID как можно раньше в процессе инициализации SDK, чтобы с CUID можно было связать как можно больше событий.

<Tabs>
<Tab title="Android iOS">

Как только CUID станет доступен, можно установить его, вызвав `setCustomerUserID`. Вы можете связать CUID только с событиями в приложении, которые происходят после его установки. Поэтому событие установки не будет содержать CUID, если вы вызываете `start` до `setCustomerUserID`.

### Связь CUID с событием установки

Если вам нужно связать событие установки с CUID, рекомендуем задать его до вызова `start`.

**Важно:** Помните, что установка CUID перед `start` может заблокировать SDK (пакет средств разработки ПО) от отправки события установки и, таким образом, предотвратить атрибуцию. Это может произойти, например, когда пользователь запускает Приложение впервые и выходит из него до того, как SDK сможет установить CUID.

В Android вы можете запускать `start` и настраивать CUID либо из глобального класса `Application` , либо из класса `Activity` в зависимости от реализации приложения. Для получения дополнительной информации см. <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#выберите-класс-в-котором-будет-запущен-sdk-пакет-средств-разработки-по">Выбор класса для запуска SDK</Anchor>.

#### Если SDK запускается в классе Application

Если вы хотите связать CUID с событием установки при запуске из глобального класса `Приложение`, обязательно отложите отправку события установки с помощью метода `waitForCustomerUserId` . Этот метод переводит SDK в режим ожидания, пока CUID не будет установлен.

Примечание. Если по какой-то причине не удастся задать CUID, SDK останется в режиме ожидания и не будет отправлять никаких событий.

#### Если SDK запускается в классе Activity

Если вы хотите связать CUID с событием установки при запуске из класса `Активность` , отправку события установки откладывать не нужно. Достаточно вызвать `start` перед вызовом `start`.

#### Инструкции для разработчиков

Сообщите разработчикам следующее:

* Используйте `waitForCustomerUserId`, если SDK запускается в глобальном классе `Application`.
* Ссылки для разработчиков:
  * Если вы хотите связать CUID с событием установки, см. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event">здесь</Anchor>.

</Tab>

<Tab title="Android native iOS native Unity React Native">

Используйте метод `customerUserId` для установки CUID. Расположение `customerUserId` по отношению к `start` определяет, какие события можно связать с CUID.

* Если вы вызываете `customerUserId` до вызова `start`, SDK связывает CUID с установкой и следующими событиями в приложении
* Если вы вызываете его после `start`, SDK связывает CUID только с событиями, зарегистрированными после того, как вы его задали.

#### Инструкции для разработчиков

Обратитесь к вашему разработчику по <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id">настройке идентификатора пользователя клиента</Anchor> в Dev Hub.

</Tab>

<Tab title="Unity">

#### Инструкции для разработчиков

Обратитесь к вашему разработчику по <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">настройке идентификатора пользователя клиента</Anchor> в Dev Hub.

</Tab>

<Tab title="iOS native UnityReact Native">

#### Инструкции для разработчиков

Порекомендуйте вашему разработчику ознакомиться с <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid">справочником API setCustomerUserId</Anchor> в Dev Hub.

</Tab>

<Tab title="Веб">

Полное пошаговое руководство по реализации см. в статье <Anchor target="_blank" href="/marketers/ru/docs/integrate-appsflyer-web-sdk#6-установить-идентификатор-пользователя-клиента">Set customer user ID</Anchor> в материале Integrate AppsFlyer Web SDK.

</Tab>
</Tabs>

## CUID и конфиденциальность

AppsFlyer ценит и уважает конфиденциальность ваших пользователей и <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">не допускает сбор или передачу конфиденциальных персональных данных на платформу AppsFlyer.</Anchor>

Чтобы защитить конфиденциальность ваших пользователей, вы не должны создавать CUID так, чтобы он содержал информацию, которая напрямую идентифицирует пользователя. Это включает в себя номера социального страхования или национальные идентификационные номера.

Если CUID содержит адрес электронной почты пользователя или номер телефона, перед отправкой в AppsFlyer его необходимо хешировать. Никогда не отправляйте в AppsFlyer нехешированные CUID, содержащие персональные данные.

> 📘 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview#отчёты-о-пути-пользователя">Отчёты о пути пользователя</Anchor> (подробнее о CUID в отчетах о необработанных данных)
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">Рекомендации Google, чтобы избежать отправки PII</Anchor>

<div data-zendesk-anchors="what-is-cuid=%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-cuid h_01HAJ00DVHRSDBS4FFKM16JFER=%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-cuid h_01HAJ00DVHZ8V8MRAXN2W3T8DS=%D0%BD%D0%B0%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 setting-the-cuid=%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-cuid h_01HAJ00DVHDGM133A72HD5JXER=%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0-cuid associate-the-cuid-with-the-install-event=%D1%81%D0%B2%D1%8F%D0%B7%D1%8C-cuid-%D1%81-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B5%D0%BC-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 h_01HAJ00DVHDE9V2MT6JQF8SAH3=%D1%81%D0%B2%D1%8F%D0%B7%D1%8C-cuid-%D1%81-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B5%D0%BC-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8 if-the-sdk-starts-in-the-application-class=%D0%B5%D1%81%D0%BB%D0%B8-sdk-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0%D0%B5%D1%82%D1%81%D1%8F-%D0%B2-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B5-application h_01HAJ00DVH746B6YJVF70PMZJ8=%D0%B5%D1%81%D0%BB%D0%B8-sdk-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0%D0%B5%D1%82%D1%81%D1%8F-%D0%B2-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B5-application if-the-sdk-starts-in-an-activity-class=%D0%B5%D1%81%D0%BB%D0%B8-sdk-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0%D0%B5%D1%82%D1%81%D1%8F-%D0%B2-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B5-activity h_01HAJ00DVHYZBER40RJH0GM8KF=%D0%B5%D1%81%D0%BB%D0%B8-sdk-%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0%D0%B5%D1%82%D1%81%D1%8F-%D0%B2-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B5-activity developer-instructions-android=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2 h_01HAJ00DVHZBZCRA1VGYJY44VY=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2 developer-instructions::31dbab4b=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2 h_01HAJ00DVH2RV902D6G224A4QY=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2 developer-instructions-unity=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2 h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2 developer-instructions-react=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2 h_01M25Y3EFC7BJAYE9YEJYA4S5A=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%BE%D0%B2 cuid-and-privacy=cuid-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C h_01HAJ00DVH4987JGZZVDA1NB29=cuid-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C h_01HE7RXTEPQAWV03276TDEPG0V=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

---
title: 'Для iOS и Android: мастер интеграции SDK'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2024-04-10T12:17:00Z'
  edited_at: '2026-08-28T00:14:39Z'
  id: 24073235369617
  locale: ru
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ru/articles/24073235369617
---
> **At a glance:** Автоматически создавайте и тестируйте код интеграции SDK.

<div id="about-the-sdk-integration-wizard" />

## О мастере интеграции SDK

Позвольте нашему <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">мастеру интеграции SDK</Anchor> провести разработчика приложений через процесс интеграции SDK. Разработчику приложений достаточно указать некоторые учетные данные и параметры настройки, а мастер сгенерирует фрагменты кода, которые нужно скопировать и вставить в проект.

Эта статья поможет вам собрать все вводимые данные и учетные данные, необходимые для сценариев мастера интеграции, и передать их разработчику приложений. Мастер поддерживает два сценария для разработчиков:

* [Путь разработчика при установке и интеграции](#процесс-установки-и-интеграции): мастер проводит разработчика от установки до успешного тестирования интеграции.
* [Путь разработчика для in-app событий](#процесс-настройки-событий-в-приложении): мастер помогает разработчику пройти путь от определения событий в приложении до успешного тестирования их передачи в AppsFlyer.

<div id="the-installation-and-integration-flow" />

## Процесс установки и интеграции

После того как разработчик приложений успешно завершит установку и настройку с помощью мастера интеграции, SDK AppsFlyer будет готов начать отправку данных атрибуции. Чтобы подтвердить успешную интеграцию, сценарий включает тест, который проверяет, правильно ли в AppsFlyer передается событие установки при установке вашего приложения.

В таблице ниже перечислены вопросы, на которые разработчики должны ответить при настройке мастера. Используйте указанные в таблице инструкции, чтобы собрать необходимую информацию и передать ее разработчикам.

| Остались вопросы | Читать полностью |
| --- | --- |
| Какой у вас идентификатор ID приложения? (Необязательно) | <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer#ввод-данных-приложение">Узнайте, как получить идентификатор ID приложения в каждом магазине.</Anchor> |
| Какой у вас Dev Key AppsFlyer (обязательно) | <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#получение-ключа-разработчика">Узнайте, как получить Dev Key.</Anchor> |
| Какой режим SDK вы хотите внедрить? Стандартный или строгий? | <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#strictmode-sdk">Узнайте о режимах SDK</Anchor>. |
| Должен ли SDK получать данные конверсии? | <Anchor target="_blank" href="/marketers/ru/docs/get-conversion-data-using-appsflyer-sdk-overview">Узнайте о данных конверсии в SDK</Anchor>. |
| Должен ли SDK получать подтверждение о том, что он успешно запущен? | Узнайте о методе запуска SDK с обработчиком завершения ([Android](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-with-a-response-listener), [iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#start-with-completion-handler)). |
| Должен ли SDK поддерживать AppTrackingTransparency (ATT)? | <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Узнайте об ATT</Anchor>. |
| Какой у вас токен аутентификации AppsFlyer v2? (Требуется, только если вы следуете автоматическому тестовому потоку.) | <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens#открытие-страницы-токены">Узнайте, как получить токен v2</Anchor>. |

<div id="the-add-in-app-event-flow" />

## Процесс настройки событий в приложении

После того как разработчик приложений завершит работу мастера установки и интеграции, SDK AppsFlyer будет успешно интегрирован в ваше приложение. Этот процесс включает тест события в приложении, который подтверждает, что AppsFlyer получает событие при установке вашего приложения.

В таблице ниже перечислены вопросы, на которые разработчики должны ответить при настройке мастера. Используйте указания в таблице, чтобы собрать необходимую информацию и передать ее разработчикам.

| Остались вопросы | Читать полностью |
| --- | --- |
| Выберите имя события и его параметры | <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer#ввод-данных-приложение">Узнайте, какие предустановленные события вам доступны.</Anchor> Описание каждого события включает его типичные параметры события.  <br />Кроме того, вы можете использовать наш   <br />[генератор событий в приложении](https://evgen.appsflyer.com/). |
| Должен ли SDK получать подтверждение того, что AppsFlyer получил событие в приложении? | Узнайте о коде, который проверяет, что события были успешно получены в AppsFlyer (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#handling-event-submission-success-and-failure">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#handling-event-submission-success-and-failure">iOS</Anchor>). |
| Какой у вас токен аутентификации AppsFlyer v2? (Требуется только при использовании сценария автоматического тестирования.) | <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens#открытие-страницы-токены">Узнайте, как получить токен v2</Anchor>. |

<div id="traits-and-limitations" />

## Спецификации и ограничения

| Специфика | Специфика |
| --- | --- |
| План Zero | Мастер интеграции SDK не входит в <Anchor target="_blank" href="/marketers/ru/docs/account-management-plans-payments-and-billing#appsflyer-plans">план Zero</Anchor>. |

<div data-zendesk-anchors="about-the-sdk-integration-wizard=%D0%BE-%D0%BC%D0%B0%D1%81%D1%82%D0%B5%D1%80%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-sdk h_01J6730Y7WE1AJXNXFZ0QX23T8=%D0%BE-%D0%BC%D0%B0%D1%81%D1%82%D0%B5%D1%80%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-sdk the-installation-and-integration-flow=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01J5K2A8BZS9CTZA45FB5VX8C0=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 the-add-in-app-event-flow=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01J5K2CG0H1G0BCSWHBJ8DPQWA=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

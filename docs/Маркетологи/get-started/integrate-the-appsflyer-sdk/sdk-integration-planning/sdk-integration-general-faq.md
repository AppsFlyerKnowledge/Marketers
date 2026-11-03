---
title: Общие вопросы по интеграции SDK
metadata:
  keywords:
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
  created_at: '2015-01-18T11:13:24Z'
  edited_at: '2026-08-18T00:16:12Z'
  id: 207033546
  locale: ru
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ru/articles/207033546
---
> **At a glance:** **Краткий обзор:** AppsFlyer SDK позволяет безопасно рекламировать ваше приложение, атрибутировать его, создавать диплинки и собирать информацию о поведении ваших мобильных пользователей. Вы можете настроить и начать работу с любой рекламной сетью и/или платформой за считанные минуты, а не за недели или месяцы!

## Как установить и обновить AppsFlyer SDK?

Чтобы узнать, как установить и обновить SDK AppsFlyer, посетите <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">хаб разработчиков</Anchor>. **Примечание**: Обновление SDK включает выпуск новой версии вашего приложения в магазинах.

## Сложно ли интегрировать AppsFlyer SDK?

Опытный разработчик может подготовить приложение для атрибуции с помощью AppsFlyer менее чем за час. Затем потребуется всего несколько минут на приложение.

См. руководства по интеграции AppsFlyer SDK для <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">Android</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">iOS</Anchor>, Unity и других <Anchor target="_blank" href="/marketers/ru/docs/other-platforms">платформ</Anchor>.

## Влияет ли AppsFlyer SDK на время загрузки приложения?

SDK AppsFlyer разработаны для *минимального* влияния на производительность приложения. Все версии SDK имеют небольшой размер и обычно занимают менее 1% от общего размера приложения. Другими словами, **влияние на время загрузки приложения минимально**.

* **Android SDK:** ~300 КБ
* **iOS SDK:** ~3,4 МБ

## Влияет ли AppsFlyer SDK на производительность Приложения?

API-интерфейсы AppsFlyer SDK в основном являются методами *setter*/ *getter* или быстрыми асинхронными методами веб-сервисов, которые отправляют/получают данные с серверов AppsFlyer. Это означает, что API SDK имеют незначительное влияние на производительность Приложения.

Другими словами, **AppsFlyer SDK** **не влияет на производительность приложения или пользовательский опыт**.

## Могу ли я записывать внутренние события приложения, которые происходят за его пределами?

Вы можете использовать <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">API S2S для отчетов о событиях</Anchor>, которые происходят за пределами приложения; например, когда пользователь продлевает свою подписку через ваш веб-интерфейс. События S2S после их записи доступны на всей платформе, включая дэшборды, сырые данные и аналитику.

<div data-zendesk-anchors="how-to-install-and-update-the-appsflyer-sdk=%D0%BA%D0%B0%D0%BA-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D1%8C-%D0%B8-%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D1%8C-appsflyer-sdk h_01HSXBYM9WMD9CDX03RFHM0JY1=%D0%BA%D0%B0%D0%BA-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D1%8C-%D0%B8-%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D1%8C-appsflyer-sdk is-it-hard-to-integrate-the-appsflyer-sdk=%D1%81%D0%BB%D0%BE%D0%B6%D0%BD%D0%BE-%D0%BB%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-appsflyer-sdk h_01HMTWQHQRGE6Z2BM1BBQY04H1=%D1%81%D0%BB%D0%BE%D0%B6%D0%BD%D0%BE-%D0%BB%D0%B8-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-appsflyer-sdk does-the-appsflyer-sdk-affect-app-download-time=%D0%B2%D0%BB%D0%B8%D1%8F%D0%B5%D1%82-%D0%BB%D0%B8-appsflyer-sdk-%D0%BD%D0%B0-%D0%B2%D1%80%D0%B5%D0%BC%D1%8F-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HMTWQHQRQQ47CAJCA4Y0AASZ=%D0%B2%D0%BB%D0%B8%D1%8F%D0%B5%D1%82-%D0%BB%D0%B8-appsflyer-sdk-%D0%BD%D0%B0-%D0%B2%D1%80%D0%B5%D0%BC%D1%8F-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F does-the-appsflyer-sdk-affect-app-performance=%D0%B2%D0%BB%D0%B8%D1%8F%D0%B5%D1%82-%D0%BB%D0%B8-appsflyer-sdk-%D0%BD%D0%B0-%D0%BF%D1%80%D0%BE%D0%B8%D0%B7%D0%B2%D0%BE%D0%B4%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HMTWQHQRXBPQN75J0KM48AJ2=%D0%B2%D0%BB%D0%B8%D1%8F%D0%B5%D1%82-%D0%BB%D0%B8-appsflyer-sdk-%D0%BD%D0%B0-%D0%BF%D1%80%D0%BE%D0%B8%D0%B7%D0%B2%D0%BE%D0%B4%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F can-i-record-inapp-events-that-occur-outside-my-app=%D0%BC%D0%BE%D0%B3%D1%83-%D0%BB%D0%B8-%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8B%D0%B2%D0%B0%D1%82%D1%8C-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D1%8B%D0%B5-%D0%BF%D1%80%D0%BE%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%82-%D0%B7%D0%B0-%D0%B5%D0%B3%D0%BE-%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B0%D0%BC%D0%B8 h_01HMTWQHQSP646Y8KVZSBA01TF=%D0%BC%D0%BE%D0%B3%D1%83-%D0%BB%D0%B8-%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8B%D0%B2%D0%B0%D1%82%D1%8C-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D1%8B%D0%B5-%D0%BF%D1%80%D0%BE%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%82-%D0%B7%D0%B0-%D0%B5%D0%B3%D0%BE-%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B0%D0%BC%D0%B8" />

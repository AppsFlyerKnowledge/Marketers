---
title: "Руководство по настройке X Ads (ранее Twitter Ads)\_— обзор"
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2026-08-18T00:33:45Z'
  id: 4410464316049
  locale: ru
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/ru/articles/4410464316049
---
> **Краткий обзор:** Узнайте, как функционирует интеграция аккаунта Х Ads с AppsFlyer.

<Image align="center" alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

<div id="mobile-app-promotion-on-x-ads" />

## Продвижение мобильных приложений в X Ads

Функция рекламы мобильных приложений в X Ads — это способ продвигать приложения в X Ads, используя отлично продуманные карточки приложений, чтобы стимулировать установки, взаимодействие с приложением и диплинкинг. используя отлично продуманные карточки приложений, чтобы стимулировать установки, взаимодействие с приложением и диплинкинг. Пользователи могут легко устанавливать приложения и взаимодействовать с ними прямо в ленте X Ads.

<div id="x-ads-user-privacy" />

## Конфиденциальность пользователей X Ads

Пользователи X Ads могут контролировать, какую информацию они предоставляют рекламодателям:

* Если в настройках пользователей указано, что они не предоставляют рекламодателю информацию об интеракциях, то их установки и внутренние события приложения, осуществляемые через X Ads, не учитываются в сырых данных, но по-прежнему атрибутируются к X Ads.
* Сводные данные атрибуции правильно отражаются в AppsFlyer, на них не влияет политика X Ads.
* В результате отчеты по агрегированным и сырым данным X Ads не коррелируют между собой.

С 31 июля 2021 года рекламодатели, не участвующие в программе X Ads Advanced Mobile Measurement (AMM), перестанут получать данные X Ads MACT уровня пользователя.

Через программу AMM рекламодатели могут получать более полные данные уровня пользователя. Для этого потребуется разрешить X Ads проводить аудит с целью проверки, что данные X Ads используются исключительно в целях измерения. Это соответствует действующим законам о защите данных и общепринятой практике в отрасли.  
**Как присоединиться к программе AMM:** Перейдите на ads.twitter.com/help > **Mobile App, Conversion Tracking & Audience Manager** и выберите **Advanced Mobile Measurement Program Agreement Form** (Форма согласия на участие в программе Advance Mobile Measurement).

Обратите внимание, что данные уровня пользователя, полученные до подключения к программе AMM, экспортировать нельзя.

Чтобы узнать больше, обратитесь своему менеджеру в X Ads.

<div id="x-ads-and-appsflyer-skan-interoperation" />

## Взаимодействие X Ads и AppsFlyer SKAN

X Ads отправляет в SKAdNetwork данные постбэков через выделенный API. Данные SKAN из X Ads будут отображаться на <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">дэшборде SKAN</Anchor>.

X Ads добавляет в постбэки SKAN следующие поля данных:

* Название кампании
* Идентификатор кампании
* Название группы объявлений
* Идентификатор группы объявлений

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=%D0%BF%D1%80%D0%BE%D0%B4%D0%B2%D0%B8%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B2-xads h_01H9QR6TH7M0H5YMXRWVVAYRK9=%D0%BF%D1%80%D0%BE%D0%B4%D0%B2%D0%B8%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B2-xads twitter-user-privacy=%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-xads h_01H9QR6TH74R50K00H7FYN61KC=%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-xads twitter-ads-and-appsflyer-skan-interoperation=%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D0%B5-xads-%D0%B8-appsflyer-skan h_01H9QR6TH74PKBGM5RC4M118GE=%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D0%B5-xads-%D0%B8-appsflyer-skan" />

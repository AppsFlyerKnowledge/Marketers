---
title: Интеграция Google Play Games на ПК с AppsFlyer
metadata:
  keywords:
    - Marketers
    - cross-platform
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-09-05T13:06:17Z'
  edited_at: '2026-10-19T14:19:03Z'
  id: 18315431772817
  locale: ru
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ru/articles/18315431772817
---
> **Кратко:** Интегрируйте свою игру или приложение Google Play Games на ПК/Android с AppsFlyer, чтобы измерять эффективность кампаний, продвигающих эти приложения.

## Об атрибуции Google Play Games на ПК

Google Play Games — это приложение для ПК, которое позволяет пользователям просматривать, загружать и запускать выбранные мобильные игры Android на настольном компьютере или ноутбуке с Windows. Google Play Games работает на устройствах с Windows.

Приложения, работающие в Google Play Games, не отличаются от любых других приложений Android. По сути, это мобильные игры Android, доступные на ПК. И, как и любое мобильное приложение Android, они могут интегрироваться с AppsFlyer «из коробки» с помощью Android SDK AppsFlyer, чтобы получать данные атрибуции и измерения эффективности о том, какие источники и кампании приводят к открытию приложения и событиям в приложении. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

AppsFlyer использует для приложений, работающих в Google Play Games, тот же процесс атрибуции, что и для мобильных приложений Android.

## Процедуры интеграции

В следующей таблице перечислены задачи, необходимые для интеграции вашего приложения Google Play Games с AppsFlyer.

| Выручка | Действия | Кто участвует |
| --- | --- | --- |
| Настройка приложения | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Создание аккаунта</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими разрешениями</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте свое приложение Android в AppsFlyer</Anchor></li></ul> | Маркетолог |
| Интеграция SDK с вашим приложением | Интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">AppsFlyer Android SDK</Anchor>. | Разработчик приложения |
| Настройка кросс-платформенной целевой страницы | **Рекомендуется:** Кроссплатформенная целевая страница, на которой запущен смарт-скрипт AppsFlyer, позволяет проводить атрибуцию из веба в приложение. Рекомендуется для случаев, когда ваша кампания продвигает приложение, которое также доступно на нескольких платформах, например Epic и Steam.<br /><br /><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Узнайте о кросс-платформенных целевых страницах</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ru/docs/cross-platform-landing-pages-with-smart-script">Узнайте, как создать кросс-платформенную целевую страницу</Anchor> | Маркетолог (может потребоваться помощь разработчика) |
| Настройка ссылки | Если вы не используете кроссплатформенную целевую страницу, вы можете создать прямые ссылки атрибуции для размещения за рекламой. Для маркетинговых кампаний приложений Google Play Games используются ссылки, аналогичные ссылкам атрибуции, создаваемым в AppsFlyer для мобильных приложений.<br /><br /><Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Узнайте, как создавать ссылки</Anchor> | Маркетолог |
| Настройка отчета / просмотр данных | Дэшборды и отчеты AppsFlyer для приложений Google Play Games аналогичны тем, что доступны для мобильных приложений.<br /><br /><Anchor target="_blank" href="/marketers/ru/docs/analyze-your-data">Узнайте больше о дэшбордах и отчетах AppsFlyer</Anchor> | Маркетолог/инженер по обработке и анализу данных |

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Концепции платформ CTV, ПК и консолей</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/google-ads-web-integration-for-pc-and-console-apps">Веб-интеграция Google Ads для приложений для ПК и консолей</Anchor>

<div data-zendesk-anchors="about-steam-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-google-play-games-%D0%BD%D0%B0-%D0%BF%D0%BA 01H7Z1DJRW1KPJQ4CZ6T85ASRK=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-google-play-games-%D0%BD%D0%B0-%D0%BF%D0%BA integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z1DJRWX54DN2SNS21GPGXB=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01HDP2XBSEJVQ5G0MD0V5R05CM=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

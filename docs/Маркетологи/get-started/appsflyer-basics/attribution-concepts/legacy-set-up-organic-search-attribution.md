---
title: '[Legacy] Настройка атрибуции органического поиска'
deprecated: true
metadata:
  keywords:
    - Android
    - organic
    - keyword
    - search
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-28T06:35:08Z'
  edited_at: '2026-08-28T00:08:08Z'
  id: 210195193
  locale: ru
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ru/articles/210195193
---
> **Краткий обзор:** Получите подробные данные атрибуции органического поиска, чтобы оптимизировать органические конверсии. <Anchor target="_blank" href="/marketers/ru/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Ознакомьтесь с нашим обновленным методом атрибуции органического поиска</Anchor>.

> 🚧 **Важно!**
>
> Мы рекомендуем внедрить наш <Anchor target="_blank" href="/marketers/ru/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">обновленный метод атрибуции органического поиска</Anchor>.

## Атрибуция органического поиска

Атрибуция органического поиска — это инновационное решение для атрибуции, которое позволяет клиентам AppsFlyer атрибутировать открытия мобильного приложения пользователями, у которых уже установлено ваше приложение, органическому поиску.

Используйте атрибуцию органического поиска, чтобы атрибутировать этих существующих пользователей, которые повторно взаимодействуют с вашим приложением после органического веб-поиска.

#### ПОТОК

![Organic_SEO_attribution_flow.png](https://files.readme.io/1772808df9d9e521204153d9f0689b3f9f156dd8c0ab8555673b1d321f28aece-15320495862545.png)

1. Пользователь ищет термин (например, «mens shoes») в поисковой системе мобильного браузера (Google, Bing и т. д.). Поисковая система выводит несколько кликабельных результатов.
2. Некоторые из этих результатов поиска ваш веб-разработчик настроил так, чтобы они открывали ваше мобильное приложение с помощью Android App Links и iOS Universal Links. Если у пользователя установлено приложение, то при нажатии на результат поиска открывается приложение (без перенаправления в магазин приложений).
3. При запуске приложения AppsFlyer собирает необходимую информацию и может атрибутировать открытие приложения к настроенному вами медиаисточнику (например, search\_engine).
4. Если у пользователя не установлено приложение, он попадает на целевую страницу, где можно использовать любое из нескольких решений AppsFlyer для перехода из веб в приложение (например, смарт-баннеры, Smart Script или QR-коды) для перенаправления и атрибуции пользователя.

**Чтобы настроить атрибуцию**:

1. Передайте разработчикам приложений для Android и iOS домен, связанный с вашим приложением. Для Android это означает домен, в котором настроены Android App Links для открытия приложения существующим пользователям. А для iOS это означает, что домен с Universal Links настроен на открытие приложения для существующих пользователей.
2. Сообщите разработчикам, какое значение использовать для параметра медиаисточника (`pid`). Например: search\_engine.
3. Попросите ваших разработчиков следовать инструкциям по атрибуции органического поиска для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_organic_search_attr">Android</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_organic_search_attr">iOS</Anchor>.  
   Все установки из органического поиска будут отображаться со значением выбранного вами медиаисточника. Например: search\_engine.

**Совет.** Узнайте больше о <Anchor target="_blank" href="https://gs.statcounter.com/search-engine-market-share">распределении использования поисковых систем по гео</Anchor>

<div data-zendesk-anchors="organic-search-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BE%D1%80%D0%B3%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B3%D0%BE-%D0%BF%D0%BE%D0%B8%D1%81%D0%BA%D0%B0 flow=%D0%BF%D0%BE%D1%82%D0%BE%D0%BA" />

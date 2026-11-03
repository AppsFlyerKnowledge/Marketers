---
title: Атрибуция баннеров приложений в iOS Safari
metadata:
  keywords:
    - iOS Safari
    - Smart App Banner
    - Advertisers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-01-02T15:08:07Z'
  edited_at: '2026-10-19T14:31:16Z'
  id: 115000171743
  locale: ru
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ru/articles/115000171743
---
> **Кратко:** Safari поддерживает функцию <Anchor target="_blank" href="http://developer.apple.com/library/ios/#documentation/AppleApplications/Reference/SafariWebContent/PromotingAppswithAppBanners/PromotingAppswithAppBanners.html">App Banner</Anchor> предоставляя стандартизированный способ продвижения приложений в магазине приложений Apple. **Это не связано с рекомендуемым решением <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor> от AppsFlyer.**

> 📘 **Примечание:**
>
> Мы рекомендуем использовать AppsFlyer Smart Banners, чтобы конвертировать посетителей сайта в пользователей приложения.
>
> Смарт-баннеры AppsFlyer:
>
> * Поддерживает все браузеры
> * Можно настраивать
> * Работает на всех устройствах Android и iOS

## iOS App Banner

Начиная с iOS 6 и новее вы можете внедрить App Banners в Safari, чтобы продвигать приложения, доступные в магазине приложений.

**Пример баннера в Safari**

<Image alt="AppleBanner_en-us.jpg" src="https://support.appsflyer.com/hc/article_attachments/49929540112017" width="278px" />

Перед внедрением баннеров приложений iOS учтите следующее:

* Не используйте одновременно баннер приложения iOS и AppsFlyer Smart Banners. Это может привести к проблемам с отображением на вашем мобильном сайте.
* Решение с баннером приложения предназначено только для iOS, то есть не работает в OS X.
* Баннер приложения работает только в Safari.

### Настройка веб-страницы с баннером приложения и ссылкой для атрибуции кликов

1. Вставьте следующий код в элемент header HTML веб-страницы.  

   ```html Markup
   <meta name="apple-itunes-app" content="app-id=123456789">:
   ```
2. Сгенерируйте ссылку атрибуции для мобильного приложения, которое вы продвигаете в App Banner. Ниже приведен пример ссылки атрибуции для мобильного приложения, продвигаемого в App Banner. Вы также можете использовать <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">сокращенные пользовательские ссылки атрибуции</Anchor>.   

   ```http
   https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign
   ```
3. Вставьте сгенерированную ссылку атрибуции в пиксель изображения. Пиксель изображения с URL-адресом измерения должен быть оформлен, как показано на иллюстрации.

   ```html Markup
   <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />
   ```

   Итоговая HTML-страница с пикселем изображения должна выглядеть, как в следующем примере HTML.

   ```html Markup
   <html>
     <head>
       <meta name="apple-itunes-app" content="app-id=123456789">

     </head>
     <body>
       <p>Это мой веб-сайт</p>
       <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />
     </body>
   </html>
   ```

**Внимание!** Этот код загружается и выполняет клик на устройствах iOS и Android. Чтобы отключить код на устройствах Android, добавьте в свой код необходимую логику.

<div data-zendesk-anchors="setting-a-web-page-with-an-app-banner-and-click-attribution-link=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B2%D0%B5%D0%B1-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%B1%D0%B0%D0%BD%D0%BD%D0%B5%D1%80%D0%BE%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%BE%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2" />

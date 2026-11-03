---
title: 'Бюллетень: Перенаправление OneLink в сторонние магазины приложений Android'
metadata:
  keywords:
    - Marketers
    - OneLink
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2021-04-08T08:39:22Z'
  edited_at: '2026-08-19T00:19:59Z'
  id: 360019130678
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/360019130678
---
| Что нового | Шаблоны OneLink предоставляют возможность перенаправлять пользователей, у которых нет вашего приложения, в сторонние магазины приложений для Android. |
| --- | --- |
| Дата вступления в силу | 19 мая 2021 года |
| Где | <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template">Настройка шаблона OneLink</Anchor> |
| Что | До изменения До изменения: шаблоны OneLink предоставляли возможность перенаправлять пользователей, у которых нет вашего приложения, в Apple App Store, Google Play или по URL-адресу.<br /><br />После изменения Шаблоны OneLink также предоставляют пользователям без вашего приложения возможность перенаправляться в следующие сторонние магазины приложений Android:<ul><li>Huawei AppGallery</li><li>Xiaomi Market</li><li>Магазин Samsung Galaxy</li><li>Oppo App Market</li><li>Vivo App Store</li></ul> |
| Что вы должны знать | <ul><li>Для перенаправления в сторонние магазины приложений для Android требуется, чтобы ваше приложение в других магазинах имело то же имя пакета, что и приложение для Android, выбранное в шаблоне OneLink.</li><li>Для перенаправления используется имя пакета APK (например: com.shop.app), поэтому убедитесь, что это имя существует в стороннем магазине приложений, прежде чем выбирать его.</li><li>Для перенаправления пользователей из приложения для Android извлекается только имя пакета. Например, если имя AppsFlyer также включает канал, например com.shop.app-store, извлекается только com.shop.app. В этом случае переадресация будет работать, а атрибуция нет.</li><li>Если выбрать приложение для Android вне Google Play, потребуется ввести URL-адрес, на который перенаправляются пользователи Android.</li></ul>[![](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)](https://files.readme.io/5e9df9148e5059160401391ef857ad965d1154e1ee7516bc33804de6badc5cd9-4403341605265.png)<ul><li>Если ваше приложение для Android доступно исключительно через сторонний магазин, <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">При добавлении приложения необходимо установить статус приложения в Google Play на Опубликовано out-of-store.</Anchor> Выбор любого другого статуса предотвратит перенаправление в сторонний магазин и приведет к появлению сообщения об ошибке.</li></ul> |
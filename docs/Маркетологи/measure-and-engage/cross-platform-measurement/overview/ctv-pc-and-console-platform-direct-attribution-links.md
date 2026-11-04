---
title: Прямые ссылки атрибуции для платформ CTV, ПК и консолей
metadata:
  keywords:
    - Advertiser
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2023-05-10T10:21:14Z'
  edited_at: '2026-08-18T00:22:43Z'
  id: 15199908310801
  locale: ru
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ru/articles/15199908310801
---
> **Вкратце:**  Узнайте о структуре и параметрах ссылок атрибуции AppsFlyer для платформ CTV, ПК и консолей. **Примечание**: Для приложений Android и iOS, включая игры Android для ПК, используйте <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">инструкции по созданию мобильных ссылок атрибуции</Anchor>.

<div id="overview" />

## Обзор

Прямые ссылки атрибуции для платформ CTV, ПК и консолей позволяют рекламодателям перенаправлять пользователей и собирать данные после кликов. Эти прямые ссылки атрибуции — это ссылки AppsFlyer, поддерживающие перенаправление и атрибуцию **для одного целевого приложения на одной платформе одновременно**. Цель перенаправления указывается значением параметра af\_r, включенного в ссылку.

**Примечание**: Для приложений Android и iOS, включая игры Android для ПК, используйте <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">инструкции по созданию мобильных ссылок атрибуции</Anchor>.

Ссылки атрибуции можно создать самостоятельно и размещать их в рекламе. Чтобы создать такие ссылки, следуйте инструкциям в этой статье.

Кроме того, ссылки можно создавать через S2S, используя <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_click-app-platform-app-id">API для вовлечения</Anchor>. Это требует работы разработчиков. **Примечание**: Ссылки, созданные через S2S, также могут собирать данные о показах.

<div id="attribution-link" />

### Ссылка атрибуции

| Свойство | Значения |
| --- | --- |
| Базовый URL-адрес | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Обязательные параметры пути | <ul><li>платформа<br />Пример: steam</li><li>app\_id<br />Пример: 123456</li></ul> |
| Обязательные параметры запроса | <ul><li>media\_source (медиа-источник)</li><li>af\_campaign\_id</li></ul> |
| Другие параметры | [См. все параметры](/docs/ctv-pc-and-console-platform-direct-attribution-links#параметры) |
| Структура URL-адреса | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |
| Пример URL-адреса | `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=aloha&af_campaign_id=1234&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello` |

<div id="parameters" />

### Параметры

| Параметр | Отображаемое имя в экспорте необработанных данных и Pull API | Описание | Тип поля |
| --- | --- | --- | --- |
| платформа | платформа | <ul><li>Параметр пути, указывающий платформу приложения.</li><li>Возможные значения:<ul><li>SmartCast</li><li>тизен</li><li>Roku</li><li>webOS</li><li>VIDAA</li><li>PlayStation</li><li>Steam</li><li>Quest</li><li>battlenet</li><li>epic</li><li>switch</li><li>xbox</li><li>Native PC</li></ul></li></ul> | строка |
| app\_id (идентификатор приложения) | Идентификатор приложения | <ul><li>Параметр пути, указывающий идентификатор приложения, для которого вы публикуете.</li><li>Пример: `ap123456`</li><li>Не добавляйте префикс платформы к значению идентификатора приложения. Например, если идентификатор приложения `ap123456`, а платформа `platformX`, не используйте `platformX_ap123456` в качестве значения `app_id`.</li></ul> | строка |
| media\_source (медиа-источник) | Медиа-источник | Уникальный идентификатор партнера, определенный на платформе AppsFlyer.  <br />Следующие специальные символы не допускаются: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %. | строка |
| af\_campaign | Кампания | Название кампании | строка |
| af\_campaign\_id | Идентификатор кампании | Идентификатор кампании | строка |
| af\_request\_id | Не применимо | Идентификатор, который однозначно идентифицирует запрос партнера. | строка |
| af\_adset | Группа объявлений | Название группы объявлений | строка |
| af\_adset\_id | идентификатор группы объявлений | идентификатор группы объявлений | строка |
| af\_ad | Реклама | Название рекламы | строка |
| af\_ad\_id | Идентификатор рекламы | Идентификатор рекламы | строка |
| af\_campaign\_type | Тип кампании | Либо:<ul><li>user\_acquisition</li><li>ретаргетинг</li></ul> | строка |
| af\_prt | Партнер | <ul><li>Имя аккаунта агентства, позволяющее атрибутировать установки к агентству</li><li>**Внимание**: Не используйте этот параметр, пока не проверите, что **разрешения агентства** включены.</li></ul> | строка |
| af\_siteid | идентификатор сайта | <span id="query-getImpressionAppPlatformApp_id_af_siteid__description"></span>Уникальный идентификатор издателя, показывающего рекламу | строка |
| af\_sub\_siteid | идентификатор подсайта | <span id="query-getImpressionAppPlatformApp_id_af_sub_siteid__description"></span>Идентификатор подсети рекламы или издателя | строка |
| af\_click\_id | Не применимо | <span id="query-getImpressionAppPlatformApp_id_af_click_id__description"></span>Уникальный идентификатор транзакции рекламной сети | строка |
| af\_lookback\_window | Не применимо | <ul><li>Конфигурируемое количество дней/часов для периода окна атрибуции по кликам. Доступные ценности, значения параметров:<ul><li>Клики: 1 d–7 d (дней).</li><li>Показы: 1 d–7 d (дней) ИЛИ 1 h–23 h (часов).</li></ul></li><li>Валидация: максимум 3 символа, используя схему выше.</li><li>Валидация: Максимум 3 символа, используя схему выше.</li></ul> | строка |
| af\_ad\_placement | Н/Д | <span id="query-getImpressionAppPlatformApp_id_af_ad_placement__description"></span>Уникальный идентификатор транзакции рекламной сети | строка |
| af\_ad\_type | Тип рекламы | <ul><li>Тип рекламы. Используйте следующее соглашение об именовании:<ul><li>**текст:** рекламный блок, содержащий только текст, например результат поиска</li><li>**баннер:** базовый формат, который отображается в верхней или нижней части экрана устройства</li><li>**межстраничное объявление:** полностраничное объявление, которое появляется во время перерывов в текущем опыте</li><li>**видео:** стандартное видео, без вознаграждения</li><li>**rewarded\_video:** рекламный блок, предлагающий награды в приложении в обмен на просмотр видео</li><li>**playable:** рекламный блок, содержащий интерактивный предварительный просмотр приложения</li><li>**аудио:** аудиореклама</li></ul></li><li>Чувствительность к регистру.</li></ul> | строка |
| af\_channel | Канал | <span id="query-getImpressionAppPlatformApp_id_af_channel__description"></span>Канал медиа-источника, через который распространяется реклама, например UAC\_Search, UAC\_Display, Instagram, Meta Audience Network и т. д. | строка |
| af\_model | Модель устройства | Модель устройства | Строка 64 |
| af\_os\_version | Н/Д | <ul><li>Версия ОС устройства</li><li>Разрешены только цифры и точки</li><li>Пример: 8.1.0</li></ul> | строка |
| af\_device\_id\_type | Н/Д | <span id="query-getImpressionAppPlatformApp_id_af_device_id_type__description"></span>Тип идентификатора устройства. Либо:<ul><li>VIDA</li><li>TIFA</li><li>rida</li><li>lgudid</li><li>fire</li><li>рекламный\_идентификатор</li><li>fire</li><li>пользовательский</li></ul> | строка |
| af\_device\_id\_value | Не применимо | <span id="query-getImpressionAppPlatformApp_id_af_device_id_value__description"></span>Тип идентификатора устройства | строка |
| af\_r | Не применимо | <ul><li>Содержит ссылку на нужный магазин приложений или целевую страницу.</li><li>Все данные внутри параметра af\_r необходимо кодировать. Сюда входят любые значения параметров UTM, если они добавлены.</li></ul>**Примечание:** Проверьте, чтобы домен URL для af\_r был включен в ваш <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-domain-redirect-allowlist">список разрешенных перенаправлений</Anchor>. | строка |

<div id="traits-and-limitations" />

## Характеристики и ограничения

| Атрибуция агентства | <ul><li>Поток CTV-PC-Console на мобильный — поддерживается атрибуция агентства.</li><li>Поток с мобильного на CTV-ПК-консоль — атрибуция агентства не поддерживается.</li></ul> |
| --- | --- |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 01H7Z1003GTTMRY072BXWDFNP0=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H7Z1003G0WYBCK3530064WM1=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B 01H7Z1003GNC551PDCKKFQMPVN=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HVED5DJPFR5XCWYDSYCHMCR6=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

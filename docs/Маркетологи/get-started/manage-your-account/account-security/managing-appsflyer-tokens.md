---
title: Управление токенами AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2020-01-01T09:50:22Z'
  edited_at: '2026-09-28T00:07:48Z'
  id: 360004562377
  locale: ru
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ru/articles/360004562377
---
> **Краткий обзор:** Токены повышают безопасность данных. Они позволяют пользователям получать доступ к данным через API AppsFlyer или получать данные о событиях с помощью вызовов от сервера к серверу. Администраторы могут управлять несколькими токенами, сохраняя непрерывность данных. Это включает в себя создание, переименование и удаление API и токенов для межсерверной аутентификации по мере необходимости.

> 🚧 **Двоеточие (:)**
>
> ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)
>
> * Только администраторы могут просматривать и управлять токенами. Пользователи учетной записи не имеют доступа к странице Токены.
> * Храните токены в безопасности, поскольку они обеспечивают доступ к вашим данным. Не публикуйте токены в открытых репозиториях кода.
> * Рекомендуется заменять токены каждые 180 дней.

## О токенах AppsFlyer

Токены используются для предоставления пользователям доступа к данным через API AppsFlyer и вызовы S2S. Администраторы используют токены для различных целей:

* Меры безопасности
  * Замена токенов для решения конкретных проблем безопасности, таких как компрометация токена или подозрение на несанкционированный доступ
  * Периодическая замена токенов в рамках регулярного обновления политики безопасности
* Управление различными вызовами API
* Цели тестирования
* Для использования с определенными функциями, такими как API OneLink

## Открытие страницы “Токены”

1. На верхней панели откройте меню аккаунта (выпадающий список под адресом электронной почты) > **Центр безопасности**.
2. В разделе **Токены API AppsFlyer** нажмите **Управление токенами API AppsFlyer.** Отобразятся текущие токены.

## Типы токенов

Существуют различные типы токенов для разных целей. По умолчанию для каждой новой учетной записи генерируется токен API (токен API V2). Администраторы могут создать максимум два токена для каждого типа, как показано в таблице ниже.

| Тип токена | Целевое назначение |
| --- | --- |
| <span id="api-token"></span>Токен API: | JWT токен (JSON Web Token), используемый для авторизации вызовов API, таких как Pull API, Cohort API, ROI API и других. |
| <span id="onelink-api-premium"></span><Anchor target="_blank" href="/marketers/ru/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> (премиум) | Уникальный токен, используемый для API OneLink, который генерирует персонализированные ссылки для оптимального вовлечения пользователей в крупномасштабные кампании. |
| <span id="s2s-token"></span>Токен S2S | Используется для отправки данных с помощью вызовов от сервера к серверу. |
| <span id="mcp-token"></span>MCP токен: | Используется для аутентификации сторонних или самостоятельно размещенных систем с помощью AppsFlyer MCP. |

> 📘 **Примечание**
>
> Если вы интегрируете функцию, для которой требуется отдельный токен API V2 (например, <Anchor target="_blank" href="/marketers/ru/docs/beta-advanced-security-protect360-module">модуль расширенной безопасности</Anchor>), и уже достигли лимита в два токена, вы можете перепрофилировать существующий токен API V2 вместо запроса нового — один и тот же токен может использоваться для нескольких кейсов.

## Управляйте своими токенами

В качестве администратора вы можете управлять несколькими токенами: создавать, переименовывать и удалять их. В основном они используются для замены текущих токенов на новые. Для этого нужно сначала [создать](#создайте-токен) новый токен, внедрить его в свои системы, а после того, как он станет доступен, [удалить](#удалить-токен) старый токен.

### Получение токенов

1. На верхней панели откройте меню аккаунта (выпадающий адрес электронной почты) > **Центр безопасности**.
2. В разделе **Токены API AppsFlyer** нажмите **Управление токенами API AppsFlyer**.
3. Отобразятся доступные Токены.
4. Скопируйте необходимый токен.

### Создайте токен

1. На странице [**Токены**](#открытие-страницы-токены) нажмите **+ Новый токен**.
2. Введите имя токена.
3. Выберите тип токена.
4. Нажмите кнопку **Создать токен**.

> 📘 **Примечание:**
>
> * Токены API V2 активируются сразу после создания.
> * Активация токенов S2S, OneLink и других типов может занять до 30 минут.
>   * Пока активация не завершена, статус токена — **Pending**.
>   * Используйте токен только после того, как его статус изменится на **Активный**.
> * Обязательно внедрите новый токен в свои системы

### Удалить токен

> ❗️ **Предупреждение**
>
> * Удаление токена может привести к сбою в работе зависящих от него систем.
> * При удалении токена он удаляется со страницы Токены, и все вызовы от предыдущего токена отклоняются.
> * Если вы хотите заменить токен, сначала создайте новый токен, внедрите его, и только после того, как он станет доступен, то есть не будет находиться в статусе "Ожидание", вы сможете удалить старый токен.

1. На странице [**Токены**](#открытие-страницы-токены) нажмите на значок редактирования токена, который нужно переименовать.
2. Вы должны подтвердить удаление токена, набрав “Удалить токен”.
3. Нажмите **Сохранить**.

## Применение токена API V2

Варианты использования токена API V2 для рекламодателей и рекламных сетей:

### Рекламодатель

| Токен API V2 |
| --- |
| <Anchor target="_blank" href="/marketers/ru/docs/pull-api-raw-data">Сырые данные Pull API</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/pull-api-aggregate-data">Агрегированные данные Pull API</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/app-list-api-for-app-owners">Получение списка приложений</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/cohort-api">Ретаргетинг</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/skan-aggregated-performance-report-api">Агрегированные отчеты SKAdNetwork</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_copy">Копирование настроек интеграции партнеров</Anchor> |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_v1-integration-params">Ключ расшифровки для реферера установки</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-tax-and-store-commission-rates-with-the-net-revenue-api">API чистой выручки</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests">OpenDSR API</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/master-api-user-acquisition-metrics-via-api">Master API.</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/audiences-import-audience-segments-from-internal-systems#imported-audience-management-api">Импортировать API аудитории</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/beta-advanced-security-protect360-module">Интеграция модуля расширенной безопасности (Android)</Anchor> |

### Рекламная сеть

| Токен API V2 |
| --- |
| <Anchor target="_blank" href="/partners/ru/docs/app-list-api-for-ad-networks">Список приложений для рекламных сетей</Anchor> |
| <Anchor target="_blank" href="/partners/ru/docs/access-to-aggregated-analytics-tools-for-api-partners">Интеграция с платформами управления кампаниями</Anchor> |
| <Anchor target="_blank" href="/partners/ru/docs/protect360-for-integrated-partners#api-отчетности-по-protect360-для-рекламных-сетей">Отчеты Protect360 для интегрированных партнеров</Anchor> |
| <Anchor target="_blank" href="/partners/ru/docs/incost-api-for-ad-networks">InCost</Anchor> |

## Применение токена S2S

Пользовательские кейсы для рекламодателей и рекламодателей, использующих токен S2S:

### Рекламодатель

| Токен S2S |
| --- |
| <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">Мобильные события в приложении S2S API</Anchor> |
| <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-s2s-api-for-web-performance-measurement">Веб-события S2S API</Anchor> |

### Рекламная сеть

| Токен S2S |
| --- |
| <Anchor target="_blank" href="/marketers/ru/docs/set-up-appsflyer-preload-referrer-attribution">Атрибуция рефереров предварительной загрузки AppsFlyer</Anchor> |

> 📘 **Примечание**
>
> Для большинства рекламных сетей генерация токена S2S больше не является самостоятельной. В результате администраторы не будут видеть возможность генерации токена S2S в пользовательском интерфейсе. Самостоятельная генерация токенов доступна только для определённых управляемых партнёров.

## Применение токена OneLink

Варианты использования токена API OneLink для рекламодателей:

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">Создавайте</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">получайте</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">обновляйте</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">удаляйте</Anchor> короткие URL-адреса OneLink с настраиваемыми параметрами.

## Заявки на токен MCP

Прочтите <Anchor target="_blank" href="/marketers/ru/docs/beta-appsflyer-mcp">Статью об MCP от AppsFlyer</Anchor>, чтобы узнать о доступных вариантах использования токенов MCP.

<div data-zendesk-anchors="01HFNX0XS4RAB543NKR12B2W50=%D0%B4%D0%B2%D0%BE%D0%B5%D1%82%D0%BE%D1%87%D0%B8%D0%B5- overview=%D0%BE-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0%D1%85-appsflyer h_01HFY5D0E1H66CEB3KMJQEXV4K=%D0%BE-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0%D1%85-appsflyer reaching-the-tokens-page=%D0%BE%D1%82%D0%BA%D1%80%D1%8B%D1%82%D0%B8%D0%B5-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D1%8B h_01HFTT570KF3XM9MBSFYRDYN9S=%D0%BE%D1%82%D0%BA%D1%80%D1%8B%D1%82%D0%B8%D0%B5-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D1%8B token-types=%D1%82%D0%B8%D0%BF%D1%8B-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%BE%D0%B2 h_01HFBR7KP8BZN7KH0BNJ982WK8=%D1%82%D0%B8%D0%BF%D1%8B-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%BE%D0%B2 h_01M36NWJZ03NKZVAC2SCTAWBFX=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 manage-your-tokens=%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D1%8F%D0%B9%D1%82%D0%B5-%D1%81%D0%B2%D0%BE%D0%B8%D0%BC%D0%B8-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0%D0%BC%D0%B8 h_01HFY5D0E1AF4NYPX31W3VJYQC=%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D1%8F%D0%B9%D1%82%D0%B5-%D1%81%D0%B2%D0%BE%D0%B8%D0%BC%D0%B8-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0%D0%BC%D0%B8 retrieving-api-tokens=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%BE%D0%B2 h_01HBQN3T2HKEMNC8MSR0THYW2S=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%BE%D0%B2 create-a-token=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD h_01HFY5D0E1FECQC1HN0EXWMXAV=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD h_01HFY5D0E1HJFKFPRT8WVNPHDG=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 delete-a-token=%D1%83%D0%B4%D0%B0%D0%BB%D0%B8%D1%82%D1%8C-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD h_01HFY5D0E2B1KXGSFZR0AYAER5=%D1%83%D0%B4%D0%B0%D0%BB%D0%B8%D1%82%D1%8C-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD h_01HFY5D0E2KZYG0J2R7GR1R7W5=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 applications-of-the-api-v2-token=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0-api-v2 h_01HG64DMW7PYRXBMZN00EQN991=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0-api-v2 v20-token%E2%80%94advertiser-apis=%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D1%8C h_01HBQN7TBASK192P8D7AEWM9P6=%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D1%8C v20-token%E2%80%94ad-network-apis=%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%B0%D1%8F-%D1%81%D0%B5%D1%82%D1%8C h_01HBQN7TBAWAHEQXMYK9V14G0M=%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%B0%D1%8F-%D1%81%D0%B5%D1%82%D1%8C applications-of-the-s2s-token=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0-s2s h_01HG64M8K1PPY2Z2406MC78EEN=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0-s2s advertiser=%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D1%8C-1 h_01JSKCVT6ACKHECVJGZ0QVD8C6=%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D1%8C-1 h_01JSKD341C1EKE51Z16MMPG3Ckjh=%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%B0%D1%8F-%D1%81%D0%B5%D1%82%D1%8C-1 ad-network=%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%B0%D1%8F-%D1%81%D0%B5%D1%82%D1%8C-1 h_01KKBYBR8M9ZJWVB3MP1QG4FR4=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 applications-for-the-onelink-token=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0-onelink h_01JSKCWS5406YQJP3RR9KAXJC9=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD%D0%B0-onelink applications-for-the-mcp-token=%D0%B7%D0%B0%D1%8F%D0%B2%D0%BA%D0%B8-%D0%BD%D0%B0-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD-mcp h_01K9YD2Y9M1C8QDBS5H048XYYD=%D0%B7%D0%B0%D1%8F%D0%B2%D0%BA%D0%B8-%D0%BD%D0%B0-%D1%82%D0%BE%D0%BA%D0%B5%D0%BD-mcp" />

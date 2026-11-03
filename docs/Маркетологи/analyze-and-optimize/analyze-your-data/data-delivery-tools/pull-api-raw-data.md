---
title: Сырые данные Pull API
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2026-08-27T00:04:00Z'
  id: 360007530258
  locale: ru
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ru/articles/360007530258
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор:** Используйте этот API для получения отчетов с необработанными данными в формате CSV.

[![PullAPIRaw_us-en.png](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)

## Сырые данные Pull API

* Pull API позволяет получать отчеты по сырым данным в виде файлов CSV. <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview">Подробнее об отчетах по необработанным данным</Anchor>
* Фильтры по доступным параметрам: Источник медиа, диапазон дат, название внутреннего события и гео.
* Дополнительные возможности в Pull API:
  * Выберите валюту
  * Выберите часовой пояс

#### Отчеты по сырым данным, доступные через Pull API

<table><thead><tr><th>Отчет</th><th>Описание</th><th>Частота обновления</th></tr></thead><tbody><tr><td colspan="3"><h4><strong><span id="raw-data-reports-nonorganic"></span>Отчеты по необработанным данным (неорганические)</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5" target="_blank">Установки</a></td><td>Регистрирует неорганические установки. Запись создается, когда пользователь впервые открывает приложение.<br/> </td><td>В реальном времени</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5" target="_blank">События внутри приложения</a></td><td>Регистрирует события, совершенные пользователями.<br/> </td><td>В реальном времени</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5" target="_blank">Удаления</a></td><td>Регистрирует, когда пользователь удаляет приложение.<br/> </td><td>Ежедневно</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">Повторные установки</a><br/> </td><td>Регистрирует пользователей, которые после удаления приложения взаимодействуют с UA медиа-источником и переустанавливают приложение в течение окна повторной атрибуции.</td><td>Ежедневно</td></tr><tr><td colspan="3"><h4><strong><span id="raw-data-reports-organic"></span>Отчеты по необработанным данным (органические)</strong></h4></td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">Органические установки</a><br/> </td><td>Регистрирует момент первого открытия приложения пользователем.<br/> </td><td>Непрерывно</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">Органические события в приложении</a><br/> </td><td>Регистрирует сведения о событиях, совершенных пользователями.<br/> </td><td>Непрерывно</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">Органические удаления</a><br/> </td><td>Регистрирует пользователей, удаляющих приложение.<br/> </td><td>Ежедневно</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">Органические повторные установки</a><br/> </td><td>Регистрирует доходы от рекламы от пользователей, атрибутированных ретаргетинговому медиа-источнику в течение окна повторного взаимодействия.</td><td>Ежедневно<br/> </td></tr><tr><td colspan="3"><h4><strong><span id="retargeting"></span>Обязательный</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-retarget-v5">Конверсии</a></td><td>Запись о том, как пользователь открывает приложение после участия в ретаргетинговой кампании.</td><td>В реальном времени</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-retarget-v5">События внутри приложения</a></td><td>События в приложении, выполняемые пользователем в течение окна повторного взаимодействия.</td><td>В реальном времени</td></tr><tr><td colspan="3"><h4><strong><span id="ad-revenue-raw-data"></span>Сырые данные о доходах от рекламы</strong></h4></td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">Атрибутированный доход от рекламы</a><br/> </td><td>Регистрирует доходы от рекламы от пользователей, атрибутированных медиа-источнику.</td><td>Ежедневно</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5" target="_blank">Органический доход от рекламы</a></td><td>Регистрирует доходы от рекламы от пользователей, не атрибутированных медиа-источнику.</td><td>Ежедневно</td></tr><tr><td colspan="3"><h4><strong><span id="protect360-fraud"></span>Protect360 защита от мошенничества</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5" target="_blank">Установки</a></td><td>Регистрирует установки, признанные мошенническими и не атрибутированные какому-либо медиа-источнику.</td><td>В реальном времени</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5" target="_blank">Пост-атрибуционные установки</a></td><td>Регистрирует внутренние события, происходящие из мошеннических установок и поэтому не атрибутированные.</td><td>Ежедневно</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5" target="_blank">События внутри приложения</a></td><td>Регистрирует внутренние события, признанные мошенническими в Protect360.</td><td>В реальном времени</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5" target="_blank">Пост-атрибуционные события в приложении</a></td><td>Регистрирует внутренние события, происходящие из установок, которые признаны мошенническими после их атрибуции медиа-источнику, или считающиеся мошенническими независимо от установки.</td><td>Ежедневно</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5" target="_blank">клики;</a></td><td>Регистрирует клики от пользователей, заблокированных Protect360.</td><td>В реальном времени</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5" target="_blank">Заблокированные постбэки установок</a></td><td>Регистрирует копии постбэков, отправленных в медиа-источник, в результате чего установка была заблокирована.</td><td>В реальном времени</td></tr><tr><td colspan="3"><strong>Постбэки</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5" target="_blank">Постбэки установок</a></td><td>Регистрирует события установки, возникающие, когда пользователь впервые открывает приложение.</td><td>Ежедневно</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5" target="_blank">Постбэки событий в приложении</a></td><td>Регистрирует постбэки по внутренним событиям, отправленные в медиа-источник.</td><td>Ежедневно</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5" target="_blank">Постбэки событий ретаргетинга в приложении</a></td><td>Регистрирует внутренние события приложения, выполненные пользователями во время окна повторного вовлечения.</td><td>В реальном времени</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5" target="_blank">Постбэки конверсий ретаргетинга</a></td><td>Регистрирует внутренние события приложения, выполненные пользователями во время окна повторного вовлечения.</td><td>В реальном времени</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="Использование сырых данных Pull API">

**Для использования необработанных данных Pull API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens#открытие-страницы-токены">Получите токен API</Anchor>. Администратору необходимо получить токен.
2. Передайте вашему разработчику токен API для использования в заголовке аутентификации.
3. Предоставьте разработчикам параметры, которые они должны ввести при вызове API, как описано в следующих разделах. Параметры определяют, что содержится в отчете, как он организован, а также устанавливают временные рамки отчетности.
4. Попросите своего разработчика следовать их <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">инструкциям по Pull API для необработанных данных</Anchor> в центре для разработчиков.

#### Параметры

| Параметр | Описание |
| --- | --- |
| от | <ul><li>Диапазон дат состоит из параметров и . Даты относятся к дате активности.</li><li>Формат: ,  или  **Примечание**: Пробел  необходимо закодировать, как показано здесь `from=2020-04-01%2001:00:00`. Обычно браузеры кодируют пробел.</li><li>Пример: 2010-01-01 или 2010-01-01 20:15 (параметры часов и минут доступны для отчетов по необработанным данным).</li></ul> |
| до | Дата окончания. Что касается `from``from` |
| медиа-источник | `media_source`: Чтобы ограничить вызов конкретным медиа-источником.<br /><br />Установите параметры `media_source` и `category` следующим образом:<ul><li>Для Meta ads установите category и media source на *facebook*</li><li>Для X Ads установите category и media source на *twitter*</li><li>Для всех других медиа-источников установите category как *standard*, а media source — по названию медиа-источника.</li></ul><ul><li>Примеры<ul><li>`media_source=facebook&category=facebook`</li><li>`media_source=abc_example&category=standard`</li></ul></li></ul> |
| maximum\_rows | Максимальное количество строк, возвращаемых за один вызов API.<ul><li>[По умолчанию] если значение не указано, до 200 тыс. строк</li><li>200000: До 200 тыс. строк</li><li>1000000: До 1 млн строк</li><li>Пример:  допускает до 1 млн строк.</li></ul> |
| имя\_события | Фильтрация событий внутри приложения по указанным событиям. Выберите несколько событий, используя список, разделённый запятыми.<br /><br />**Пример**: `event_name=af_purchase,ftd` |
| reattr | Установите данные атрибуции ретаргетинга.<ul><li>[По умолчанию] Если false, возвращаются кампании с данными о привлечении пользователей (UA).</li><li>Если true, возвращаются данные ретаргетинговой атрибуции.</li><li>**Пример:**</li></ul> |
| additional\_fields | Чтобы получить дополнительные поля вдобавок к полям по умолчанию.<br /><br />**Пример**: `additional_fields=device_download_time,deeplink_url` |
| валюта | Валюта доходов и расходов<ul><li>[По умолчанию] Если параметр не указан, данные возвращаются в долларах США. Это означает, что ничего не делайте, и результаты будут предоставлены в USD.</li><li>Если вы отправляете, <Anchor target="_blank" href="/marketers/ru/docs/app-settings#localization-time-zone">используется валюта</Anchor> <Anchor target="_blank" href="/marketers/ru/docs/app-settings#localization-time-zone">, специфичная для приложения</Anchor>.  <Anchor target="_blank" href="/marketers/ru/docs/app-settings#localization-time-zone">Речь идет о валюте, установленной в настройках приложения.</Anchor></li></ul>**Пример**: Если валютой приложения является евро, отправив `currency=preferred`, значения возвращаются в евро. |
| часовой пояс | [По умолчанию] Данные возвращаются, используя UTC.<ul><li>Чтобы получить данные в часовом поясе <Anchor target="_blank" href="/marketers/ru/docs/app-settings#localization-time-zone">, специфичном для приложения</Anchor>, добавьте <Anchor target="_blank" href="/marketers/ru/docs/app-settings#localization-time-zone">, как показано в этом разделе, к вызову:</Anchor></li></ul><ul><li>`timezone=[Numerical value]`</li><li>Пример: Для часового пояса UTC+10:00 используйте Примечание<strong>: Кодированию подлежат ,</strong> и `:`. Пример: +10:00 кодируется как `%2B10%3A00`</li></ul> |
| геоданные | Отфильтруйте данные по коду страны.<br /><br />Ограничение: Вы можете указать только один фильтр кода страны на один вызов API.<br /><br />Пример: `geo=ZA` |
| время установки | <ul><li>Диапазон дат состоит из параметров и . Даты относятся к дате активности.</li><li>Формат: `yyyy-mm-dd`</li><li>Пример: 2010-01-01</li></ul> |
| время установки | Дата окончания. Как для  `from_install time` |
| агентство | Чтобы ограничить вызов конкретным агентством. |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Поля Protect360">

<Anchor target="_blank" href="/marketers/ru/docs/protect360-raw-data-reports#postattribution-reports">См. руководство по необработанным данным Protect360</Anchor>

</Accordion>

<div id="time-frame-fields" />

<Accordion title="Поля временных рамок">

Если результаты API превышают максимум, разделите отчет, используя часы и минуты. Примените следующее:

* **от**/**до:** **гггг-мм-дд чч:мм**
* **от:**
  * Только дата = с начала (00:00) выбранной даты
  * Дата и время = с 00:00 включительно
* Параметр **до:**
  * Только дата = до конца (24:00) выбранного дня
  * Дата и время = до, но не включая указанное время

**Пример:** У владельца приложения 1,3 млн установок в день из всех источников. Чтобы превысить лимит в 1М строк, владелец приложения разбивает день на два вызова URI, каждый по 12 часов. Смотрите следующую таблицу.

<table><thead><tr><th>API вызов</th><th>От </th><th>До </th></tr></thead><tbody><tr><td><strong>Первый вызов API</strong> </td><td><p><strong>до</strong></p><p><strong>Пример:</strong></p><ul><li> <strong><span>Пример</span></strong><span>:</span> </li><li>Начинается в эту дату с начала дня в 00:00</li></ul></td><td><p><strong>от</strong>=гггг-мм-дд 12:00</p><p><strong>Пример:</strong></p><ul><li> <strong>от</strong> </li><li> <span>Продолжается до 11:59:59, но не 12:00</span> </li></ul></td></tr><tr><td><p>Вариант A: <strong><strong>Второй вызов API</strong></strong>  </p><p><strong>Пример:</strong> </p><p><code><strong>от</strong>=гггг-мм-дд</code></p><ul><li>Начало в полдень 29 декабря 2019 года</li><li>Окончается в полночь 29 декабря 2019 года</li></ul></td><td><p><strong>от</strong>=гггг-мм-дд 12:00</p><p><strong>Пример:</strong></p><ul><li> <strong><span>Пример</span></strong><span>:</span> </li><li>Начинается с 12:00 и включает</li></ul></td><td><p><strong>до</strong></p><p><strong>Пример:</strong></p><ul><li> <strong>из</strong> </li><li>Заканчивается в полночь</li></ul></td></tr><tr><td><strong>Вариант Б: Второй вызов API</strong></td><td><p><span><strong>до</strong>=yyy</span><span>y-mm-dd </span></p><p><strong>Пример:</strong></p><ul><li> <span><strong>до</strong>=ггг</span><span>г-мм-дд 12:00</span> </li><li>Начинается с 12:00 и включает</li></ul></td><td><p><strong>до</strong>=гггг-мм-дд+1 00:00</p><p><strong>+1</strong> = следующий день в 00:00</p><p><strong>Пример:</strong></p><ul><li> <span>Формат: </span><span><span>, </span><span><span> или </span></span><span> <strong>Примечание</strong>: Пробел </span><span> необходимо закодировать, как показано здесь <code>from=2020-04-01<var>%20</var>01:00:00</code>. </span></span> </li><li>Означает "до того, как началось 30 декабря".</li></ul></td></tr><tr><td colspan="3"> <strong>Примечание:</strong> Используйте вариант A или B, так как они дают одинаковые результаты. </td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="Дополнительные поля">

Дополнительные поля отчета не добавляются в список полей по умолчанию, поэтому новые поля не влияют на имеющиеся процессы импорта и загрузки данных. Используйте параметр `additional_fields` для получения нестандартных полей.

* Укажите поле только один раз.
* См. <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary">список доступных полей</Anchor>.
* Пример:

</Accordion>

<div id="default-fields" />

<Accordion title="Поля по умолчанию">

| Поля Pull API по умолчанию |
| --- |
| Тип атрибутированного взаимодействия |
| Время атрибутированного взаимодействия |
| Время установки |
| Время события |
| Название события |
| Значение события |
| Выручка от события |
| Валюта выручки от события |
| Выручка от события в USD |
| Источник события |
| Проверено ли получение |
| Партнер |
| Источник медиа |
| Канал |
| Ключевые слова |
| Кампания |
| Идентификатор кампании |
| Блок рекламы |
| идентификатор рекламы |
| Реклама |
| идентификатор адсета |
| Тип рекламы |
| Идентификатор сайта |
| ID подсайта |
| Cубпараметр 1 |
| Cубпараметр 2 |
| Cубпараметр 3 |
| Cубпараметр 4 |
| Cубпараметр 5 |
| Модель затрат |
| Значение стоимости |
| Валюта стоимости |
| Партнер ассистента 1 |
| Исходная точка взаимодействия ассистента 1 |
| Кампания ассистента 1 |
| Тип касания ассистента 1 |
| Время касания ассистента 1 |
| Партнер ассистента 2 |
| Исходная точка взаимодействия ассистента 2 |
| Кампания ассистента 2 |
| Тип касания ассистента 2 |
| Время касания ассистента 2 |
| Партнер ассистента 3 |
| Исходная точка взаимодействия ассистента 3 |
| Кампания ассистента 3 |
| Тип касания ассистента 3 |
| Время касания ассистента 3 |
| Регион |
| Код страны |
| Штат |
| city |
| Почтовый индекс |
| ДМА |
| IP |
| Wi-Fi |
| Оператор |
| carrier |
| Язык |
| Идентификатор AppsFlyer |
| ID рекламы |
| IDFA |
| Android идентификатор |
| Идентификатор клиента |
| imei |
| IDFV |
| Платформа |
| Тип устройства |
| Версия ОС |
| Версия приложения |
| Версия SDK |
| Идентификатор приложения |
| Имя приложения |
| Идентификатор пакета |
| Is Retargeting (Ретаргетинг) |
| Тип конверсии ретаргетинга |
| Attribution Lookback (Ретроспективная атрибуция) |
| Окно повторного вовлечения |
| Is Primary Attribution (Основная атрибуция) |
| user agent |
| Источник ссылки HTTP |
| Исходный URL-адрес |

</Accordion>

## Дополнительные сведения

<div id="traits-and-limitations" />

<Accordion title="Характеристики и ограничения">

| Специфика | Комментарии |
| --- | --- |
| Необходимый тип токена API | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">Токен версии 2.0</Anchor> |
| Доступ к рекламной сети | Нет |
| Доступ агентств | Да |
| Прозрачность агентства | Да. Однако, пожалуйста, обратите внимание, что если вы используете одновременно фильтры агентства и медиа-источника, то фильтры медиа-источника не применяются для непрозрачных агентств. Это значит, что для непрозрачных агентств учитываются все данные, а не только данные из отфильтрованных медиа-источников. |
| Валюта приложения | Да |
| Часовой пояс приложения | Да |
| Обновление данных | <ul><li>Эквивалент доступности данных на обзорном дэшборде.</li><li>Отчеты, которые обновляются с задержкой в несколько часов:<ul><li>Органические события внутри приложения</li></ul></li><li>Отчеты, которые обновляются ежедневно:<ul><li>Удаления</li><li>События в приложении после атрибуции</li><li>Доход от рекламы</li></ul></li></ul> |
| Исторические данные | Да.  В соответствии с <Anchor target="_blank" href="/marketers/ru/docs/user-level-data-retention">политиками хранения данных</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/report-generation-quotas-rate-limitations">ограничениями по скорости передачи</Anchor>. |
| Неорганические данные | Да |
| Органические данные | Да |
| Ограничение предоставления данных | API ограничения для <Anchor target="_blank" href="/marketers/ru/docs/report-generation-quotas-rate-limitations">сырых данных</Anchor>. |
| Ограничения на размер | <ul><li>Вызов API возвращает максимум 200 тысяч / 1 млн строк.</li><li>Если в отчете ровно 200 тысяч / 1 млн строк, стоит предположить, что какие-то строки отсутствуют.</li><li>Используйте параметр maximum\_rows для выбора максимального количества строк.</li><li>Сделайте несколько API-вызовов, используя параметры from/to с указанием времени.</li></ul> |
| Install\_date from и install\_date\_to | Диапазон дат установки должен быть более ранним, чем диапазон дат активности. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Устранение неполадок">

| Симптом/сообщение | Решение |
| --- | --- |
| Отчет не содержит данных, ожидаемых в соответствии с выбранным диапазоном времени, или имеется несоответствие между отчетом по сырым данным и отчетом по агрегированным данным. | Убедитесь, что вы настроили параметр `timezone`. Если вы этого не сделаете, данные будут отправляться с использованием UTC, а не часового пояса вашего приложения. |

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Выбор подходящего инструмента доставки и отчётности данных через API</Anchor>

<div data-zendesk-anchors="pull-api-raw-data=%D1%81%D1%8B%D1%80%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-pull-api h_01HE7S6WDVJD2XFW498P8FPY7W=%D1%81%D1%8B%D1%80%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-pull-api aggregate-performance-reports-available-via-pull-api=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D0%BC-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-pull-api h_01HE7S6WDV59VTP6Z4X790QDRD=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D0%BC-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-pull-api h_01KEVCHC25BDNS9F1GEPBDAW39=raw-data-reports-nonorganic h_01KEVCHJ8TRRM9BYW6C544PNFR=raw-data-reports-organic h_01KEVCHSNGPX2RW917QX4N03A2=retargeting h_01KEVCHYMHGC6VTVSERH611Q8X=ad-revenue-raw-data h_01KEVCJ3GWBZG8SWHZKTRJ6YAX=protect360-fraud h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B h_01HE7S6WDVF8T4719HWDJH8JN1=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields additional-information=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HE7S6WDW9V8XC3CJ0F96EHN0=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

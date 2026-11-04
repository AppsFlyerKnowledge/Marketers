---
title: Аудитории — атрибуты пользователей
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-06-11T06:13:55Z'
  edited_at: '2026-10-07T00:17:54Z'
  id: 360009775517
  locale: ru
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ru/articles/360009775517
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор:** Улучшите возможности сегментации пользователей по релевантным группам, добавив данные об их характеристиках в Аудитории.

[![UserAttributionNavigationXL3_us-en.png](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)

<div id="about-user-attributes" />

## Об атрибутах пользователей

Атрибуты пользователей, несхожие с данными, основанными на событиях, — это общие характеристики, которыми ваши пользователи делятся с вами. Они могут быть статичными, такими как пол, возраст, день рождения и страна; или динамическими, такими как счет пользователя в игре.

Данные об атрибутах пользователей:

* Обновляются с помощью импортирования CSV-файлов или JSON через API.
* Хранятся в хешированном виде.
* Доступны для использования в любом наборе правил аудитории.

Данные об атрибутах пользователей **не передаются рекламным партнерам.**

Атрибуты пользователей хранятся на уровне приложения или учетной записи, как описано в этой статье. Если используются атрибуты на уровне приложения, пользователю учетной записи необходимо <Anchor target="_blank" href="/marketers/ru/docs/user-management#обзор">разрешение приложения</Anchor> для управления и использования атрибутов.

Следующий сценарий предоставляет подробное объяснение атрибутов пользователя.

<div id="scenario-app-marketer-requirements" />

<Accordion title="Сценарий — требования к маркетологу приложений">

Вы, маркетолог приложений, заняты следующим:

* Поддержание 2 гейминговых приложений: game\_a и game\_b.
* Запуск игры game\_c
* Адресование, нацеливание текущих пользователей приложений с этими атрибутами пользователей:
  * Любимый вид спорта: Крикет
  * Текущий счет в игре: 15 и более в одной из текущих игр

Таблица содержит данные об атрибутах пользователей из вашей CRM. Наборы правил аудитории должны иметь доступ к этим данным.   
![UserAttributuesExample_us-en.png](https://files.readme.io/6f86d8659ef089ac82bb8401b4af650fbc590d2293ac93de30e6f9b4fc2ceb86-33375683035281.png)

**Используйте данные CRM в наборах правил**

В разделе «Аудитории» создайте атрибуты пользователей (любимый вид спорта и счет в игре). Это предоставляет наборам правил доступ к данным CRM.

<div id="scenario-user-attributes" />

#### Атрибуты пользователя в сценарии

| **Часть основной схемы отчета AppsFlyer**: | Фактическое значение идентификатора клика из целевого URL, используемое для отправки сигналов и для разрешения полной иерархии кампании через API партнеров. | Уровень |
| --- | --- | --- |
| <span id="game-score"></span>Счет игры | **Число**: Позволяет задавать такие правила, как «*ScoreGameB больше 29*». | **На уровне приложения**: Счет пользователя записывается за каждую сыгранную игру.<br /><br />Значение: СчетИгрыA, СчетИгрыB. |
| <span id="favorite-sport"></span>Любимый вид спорта | **Строка:** Позволяет задавать такие правила, как «*чей любимый вид спорта — теннис*».<br /><br />Внимание! Ценности, значения чувствительны к регистру. | **На уровне аккаунта**: Любимый вид спорта пользователя одинаков вне зависимости от Приложения.<br /><br />Внимание! У пользователя может быть только одно значение, связанное с атрибутами уровня аккаунта. |

**Атрибуты пользователей в наборах правил**

Атрибуты пользователей действуют как фильтры в наборах правил для аудиторий. В этом примере используются критерии (любимый вид спорта и счет игры), установленные маркетологом.

[<Image alt="UserAttributedExample.jpg" src="https://files.readme.io/296ab5e13abedd5f11c7d445ec9bf4a9b62295c18ad783228d6ccb9b631be74f-33375704836625.jpg" width="276px" />](https://files.readme.io/296ab5e13abedd5f11c7d445ec9bf4a9b62295c18ad783228d6ccb9b631be74f-33375704836625.jpg)

</Accordion>

<div id="implement-user-attributes" />

## Внедрение атрибутов пользователей

Настраивайте, добавляйте, управляйте и удаляйте атрибуты пользователей.

<div id="set-up" />

<Accordion title="Настройка">

**Предварительное условие**:

Для управления атрибутами на уровне приложения пользователь аккаунта должен иметь разрешение на доступ.

**Чтобы настроить атрибуты пользователей, выполните следующие шаги:**

1. [Добавление атрибутов пользователей.](/docs/audiences-create-better-audiences-with-user-attribute-data#add)
2. [Сделайте одно из следующих действий](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [Импортируйте данные атрибутов пользователей через CSV.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [Импортируйте данные атрибутов пользователей через API.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)
3. <Anchor target="_blank" href="/marketers/ru/docs/audiences-guide#user-attributes">Реализуйте атрибуты пользователей в наборах правил.</Anchor>

</Accordion>

<div id="add" />

<Accordion title="Добавление">

**Чтобы добавить атрибуты пользователей:**

1. В AppsFlyer в боковом меню выберите **Вовлеченность** > **Аудитории**.
2. Нажмите на вкладку Атрибуты пользователей.
3. Нажмите **Добавить атрибут пользователя**.

   ![UserAttributeAdd.png](https://files.readme.io/6c7f25bb23d47e67aaef34264029daa9ab058f08e218a441ab9dde8240b0b384-33375683046033.png)
4. Заполните поля. Характеристики полей перечислены в таблице ниже.
   * **Имя атрибута**
   * **Формат**
   * **Уровень**
5. Нажмите **Сохранить**.

| Поле | Характеристики |
| --- | --- |
| <span id="attribute-name"></span>Имя атрибута | <ul><li>Только английские символы.</li><li>Без знаков препинания или специальных символов.</li><li>Одно и то же имя не может быть использовано на уровне приложения и аккаунта.</li><li>На уровне приложения то же имя **можно** использовать; например, в примере выше используются ScoreGameA и ScoreGameB.</li></ul> |
| <span id="format"></span>Формат | <ul><li>Текст: Проверьте, равно ли значение атрибута или **не равно** указанному значению в правиле. Пример: Крикет или не крикет.</li><li>Число: Проверьте, является ли значение атрибута больше, меньше или равно указанному в правиле значению. Пример: Счет больше 15</li></ul> |
| <span id="level"></span>Уровень | <ul><li>Уровень аккаунта: Атрибут не имеет связи с приложением.<br />Пример: пол, любимый вид спорта.</li><li>Уровень приложения: Атрибут связан с приложением. Выберите приложения, связанные с атрибутом.</li></ul> |

**Поля атрибутов пользователей**

</Accordion>

<div id="manage" />

<Accordion title="Управление">

Чтобы управлять атрибутами пользователя, перейдите на вкладку **Аудитории** > **Атрибуты пользователей**.

[![AudiencesUserAttributes_us-en.png](https://files.readme.io/6baee58e9cd9b2b39bc8facf0af72abe71a4bd1cd2f844f49467fbaeb7252cd7-33375704844049.png)](https://files.readme.io/6baee58e9cd9b2b39bc8facf0af72abe71a4bd1cd2f844f49467fbaeb7252cd7-33375704844049.png)

| Функция | Описание |
| --- | --- |
| <span id="search-and-filter"></span>Поиск и фильтрация | По имени атрибута, имени приложения и уровню атрибута. |
| <span id="sort-by"></span>Сортировать по | Нажмите на заголовок столбца, чтобы отсортировать строки таблицы. |
| <span id="zd-import-data"></span><span id="import-data"></span>Импорт данных | <ul><li>[Импорт данных через CSV](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)</li><li>[Импорт данных через API](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)</li></ul> |
| <span id="change-api-import-key"></span>Изменить ключ импорта API | **Чтобы изменить ключ импорта API:**<ol><li>Нажмите **Импорт данных**.</li><li>Выберите **API**.</li><li>Кликните **Обновить ключ импорта**.</li></ol>**Примечание!** Если скрипты имеют встроенные ключи, обязательно обновите их, используя новый ключ. |

Управление атрибутами пользователей

</Accordion>

<div id="delete" />

<Accordion title="Удалить">

![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Только пользователь с правами администратора может удалить атрибут.

**Чтобы удалить атрибут, являющийся частью набора правил:**

1. Удалите атрибут из набора правил.
2. Удалите атрибут.

</Accordion>

## Импорт данных

<div id="import-field-specifications" />

<Accordion title="Спецификации полей импорта">

| Поле | Содержимое | Формат | Добавить данные  <br />по CSV | Удалить данные через CSV |
| --- | --- | --- | --- | --- |
| <span id="device_id"></span>device\_id | Включает 1 из следующих идентификаторов пользователей:<ul><li>IDFA</li><li>ГАИД</li></ul> | Текст | Либо **device\_id**, либо **customer\_id** является обязательным | Либо **device\_id**, либо **customer\_id** является обязательным<br /><br />Чтобы удалить существующие данные, не отправляйте |
| <span id="customer_id"></span>customer\_id | <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid">Тип события</Anchor> | текст. | Либо **device\_id**, либо **customer\_id** является обязательным | Либо **device\_id**, либо **customer\_id** является обязательным<br /><br />Чтобы удалить существующие данные, не отправляйте |
| <span id="app_id"></span>Выручка от события в долларах США | **Атрибут на уровне приложения:** Идентификатор приложения, как он отображается на дэшборде.<br /><br />Для приложений iOS включите префикс *идентификатор*.<br /><br />**Атрибут на уровне аккаунта**: Всегда заполнять * | текст. | Обязательно | Обязательно |
| <span id="attribute_key"></span>attribute\_key | Имя атрибута пользователей, точно как на вкладке атрибутов пользователей. | текст. | Обязательно | Обязательно |
| <span id="attribute_value"></span>attribute\_value | Присвоенное значение<br /><br />[*См. ограничения](/docs/audiences-create-better-audiences-with-user-attribute-data#limitations) | Текст или число | Обязательно | Не отправляйте |

Список полей атрибутов пользователей

</Accordion>

<div id="import-data-by-csv" />

<Accordion title="Импорт данных через CSV">

Данные атрибутов пользователя добавляются или удаляются через CSV файл. Рисунок и пример CSV файла, приведенные ниже, соответствуют сценарию, описанному в этой статье.

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012423857">Пример атрибутов пользователя.csv</Anchor>

![Файл для атрибутов.png](https://files.readme.io/2a9075ab7f900648aeebe3b5fca807c6b931ba5295f35708ee6c48d345f681b9-33375704847633.png)

**Требования к CSV файлу**

* Нет строки заголовка
* Содержит все столбцы, перечисленные в предыдущей таблице.

<div id="note" />

> 📘 **Примечание:**
>
> Этот формат CSV предназначен для импорта данных атрибутов пользователей. Если вы импортируете сегменты аудиторий, см. <Anchor target="_blank" href="/marketers/ru/docs/audiences-import-audience-segments-from-internal-systems">Import audience segments from internal systems</Anchor>, где используется другой формат CSV, требующий наличия строки заголовков.

**Чтобы импортировать CSV файл:**

1. Перейдите на вкладку **Аудитории** > **Атрибуты пользователей**.
2. Нажмите **Импорт данных**.
3. Выберите **CSV**.
4. Выберите одно из:
   * **Добавить данные**
   * **Удалить данные**
5. Выберите CSV файл для импорта.
6. Нажмите **Загрузить**; появится сообщение о статусе загрузки.

**Примечание:** При импорте атрибутов пользователей все известные устройства, связанные с идентификатором клиента, также получают этот атрибут. Например, если пользователь импортировал 10 устройств (по идентификатору клиента) для атрибута «Счет игры», и один из идентификаторов клиентов связан с 2 устройствами (т.е. 2 GAID с одинаковым CUID), то этот импорт будет содержать 11 записей атрибутов пользователей.

</Accordion>

<div id="import-data-by-api" />

<Accordion title="Импорт данных через API">

Этот метод импорта требует URL-адрес запроса и JSON с данными атрибутов пользователя.

1. На дэшборде получите подготовленные вызовы API-запросов и шаблон JSON.
2. Заполните шаблон JSON своими данными в соответствии со [спецификациями полей](/docs/audiences-create-better-audiences-with-user-attribute-data#import-field-specifications).

**Чтобы сгенерировать URL-адрес запроса API и шаблон JSON:**

1. Нажмите **Импортировать данные.**
2. Выберите **API.**
3. Выберите действие:  
   * Обновить атрибуты пользователей: Перезаписать или добавить.
   * Удалить атрибуты пользователей.
   * Удалить данные пользователя: Удаляет все данные, относящиеся к конкретному пользователю. Пользователь идентифицируется по своему идентификатору AppsFlyer.
   * Удалить данные приложения: Удаляет все данные на уровне приложения.
4. Скопируйте сгенерированный URL-адрес запроса API.
5. Скопируйте сгенерированное тело запроса API.
6. Подготовьте JSON (с данными атрибутов пользователя), используя указанный формат JSON. Для атрибутов на уровне аккаунта установите "app\_ids": ["*"]
7. Подготовьте вызов API на основе URL-адреса и тела запроса.
8. Отправьте запрос программно.

**Пример запроса и JSON**

```json
https://hq1.appsflyer.com/api/user-attributes-import-api/set-user-data
{
  "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
  "attributes_values": [
    {
      "device_id": "",
      "customer_id": "",
      "app_ids": [],
      "attributes": [
        {
          "attribute_key": "",
          "attribute_value": ""
        }
      ]
    }
  ]
}
```

<div id="note-1" />

> 📘 **Примечание:**
>
> Необходимо аутентифицировать запрос с помощью заголовка Authorization Bearer с <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens#рекламодатель">API токеном V2.0</Anchor>.

**Пример с несколькими идентификаторами устройств, ключами атрибутов и значениями атрибутов**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "2222222",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 5
                }
                ,
                {
                    "attribute_key": "favorite_sport",
                    "attribute_value": "cricket"
                }
            ]
        }
        ,
        {
            "device_id": "555555-d1d1-d1d1-555-fffffffff",
            "customer_id": "111111",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "order",
                    "attribute_value": 7
                }
                ,
                {
                    "attribute_key": "number",
                    "attribute_value": 8
                }
            ]
        }]
}
```

**Пример с одним идентификатором устройства и несколькими ключами и значениями атрибутов**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "12345678",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 90
                }
                ,
                {
                    "attribute_key": "favorite-sport",
                    "attribute_value": "cricket"
                }
                ,
                {
                    "attribute_key": "orderNumber",
                    "attribute_value": 93
                }
                ,
                {
                    "attribute_key": "netPromoterScore",
                    "attribute_value": 94
                }
            ]
        }
    ]
}
```

**Примечание:** При импорте атрибутов пользователей все известные устройства, связанные с идентификатором клиента, также получают этот атрибут. Например, если пользователь импортировал 10 устройств (по идентификатору клиента) для атрибута «Счет игры», и один из идентификаторов клиентов связан с 2 устройствами (т.е. 2 GAID с одинаковым CUID), то этот импорт будет содержать 11 записей атрибутов пользователей. Ограничения импорта CSV

</Accordion>

<div id="limitations" />

<Accordion title="Ограничения">

<div id="general-limitations" />

#### Общие ограничения

* В данных импорта CSV\/API поддерживаются только целые числа. Числа с плавающей запятой не поддерживаются. **Пример:** Значение атрибута "оценка" может быть равно 90, но не 90,5.
* Данные об атрибутах пользователя не могут быть распечатаны или загружены.
* #### <span id="attribute-value-limitations"></span>Ограничения значений атрибутов:

  * Внутри значений атрибутов не должно быть запятых, точек и других специальных символов.
  * Для строкового значения атрибута существует ограничение по длине в 40 символов.
  * Значения атрибутов не могут начинаться с 0.

<div id="api-import-limitations" />

#### Ограничения импорта API

* Максимум 350 запросов API в минуту, 10 тыс. устройств для плоской полезной нагрузки (10 тыс. устройств с одним атрибутом, 5 тыс. устройств с двумя атрибутами и т. д.)
* Оба ключа `device_id` и `customer_id` являются обязательными для каждого вызова импорта. Если вы хотите импортировать атрибуты только с одним из этих идентификаторов, вызов должен включать "заголовок" другого идентификатора с пустой строкой. Например, если вы хотите импортировать атрибуты для `device_id` и без `customer_id`, вызов должен выглядеть следующим образом:

```json
"attributes_values": [
{
"device_id": "39e123.......",
"customer_id": "",
```

<div id="csv-import-limitations" />

#### Ограничения импорта CSV

* При добавлении значений атрибутов пользователя существует ограничение на 10 миллионов строк в CSV файле.

</Accordion>

<div data-zendesk-anchors="user-attributes=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%B0%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01HDNZH1XVX5BYQBPG848M8QZM=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%B0%D1%85-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 scenario%E2%80%94app-marketer-requirements=scenario-app-marketer-requirements h_01HDNZH1XV8AWVVGNYVA9G4PAG=scenario-app-marketer-requirements scenario-user-attributes=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D1%8B-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%B2-%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B8 h_01HDNZH1XW32ZJJRSANBQCTBV0=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D1%8B-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%B2-%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B8 implement-user-attributes=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%BE%D0%B2-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01HDNZH1XWPBVDHJ7AGPT5ZM9W=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%BE%D0%B2-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01HDNZH1XWYA9TQZ1B342A661R=set-up h_01HDNZH1XW0PPJF78EVFQTW3R7=add h_01HDNZH1XWGZ04TQXD5D50771A=manage h_01HDNZH1XWP8P1ZVJX11AXCS2P=delete import-data::b50dc884=%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HDNZH1XWCXV89YJV7EBJXNK5=%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HDNZH1XW87W1PV4C3PMY9QD6=import-field-specifications h_01HDNZH1XW3XC893Q8BQZQW2AG=import-data-by-csv h_01M45D4VCXXKXV25MQNAKW53ZW=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HDNZH1XX7PMGNTD683DD2B49=import-data-by-api h_01HDNZH1XXF6DSNKG19ZRZ01AZ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01HDNZH1XX61DVGK96C2TDSYW9=limitations general-limitations=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HDNZH1XXZZFA3WHZEE5N24AB=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F attribute-value-limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%BE%D0%B2 h_01GZTGPK2FTHTV4NQ2HKV1HK00=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%BE%D0%B2 api-import-limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82%D0%B0-api h_01HDNZH1XX4JWSMSF4672ENWNS=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82%D0%B0-api csv-import-limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82%D0%B0-csv h_01J3APYQ8MXG1SGREVN638R75N=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82%D0%B0-csv" />

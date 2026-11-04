---
title: Аудитории — API дополнительных идентификаторов
metadata:
  keywords:
    - Advertisers
    - Developers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-22T14:05:51Z'
  edited_at: '2026-10-07T00:18:07Z'
  id: 4411552670993
  locale: ru
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ru/articles/4411552670993
---
> **Вкратце:** Используйте API дополнительных идентификаторов аудиторий для массовой загрузки идентификаторов пользователей из ваших внутренних систем (таких как бизнес-аналитика и CRM) в AppsFlyer Аудитории, что позволяет более активно взаимодействовать с аудиториями соответствующих партнеров, используя эти идентификаторы.

<div id="about-the-api" />

## Об API

API дополнительных идентификаторов аудитории позволяет добавлять следующие идентификаторы пользователей из ваших внутренних систем в аудитории AppsFlyer:

* До 2 хешированных адресов электронной почты
* Хешированный номер телефона
* Хешированный номер телефона в формате E164

После этого вы можете отправить эти идентификаторы своим партнерам по аудитории (при условии, что ваша <Anchor target="_blank" href="/marketers/ru/docs/audiences-user-identifier-policy">политика идентификаторов пользователей на уровне учетной записи</Anchor> позволяет это), что позволит им более точно определять ваши целевые аудитории. Обратите внимание, что не все рекламные партнеры поддерживают все виды идентификаторов.

<div id="when-should-i-use-this-api" />

### Когда следует использовать этот API?

Этот API предназначен для использования, когда необходимо загрузить большой объем данных идентификаторов. Обычно это данные, собранные за продолжительный период времени (например, хешированные адреса электронной почты всех пользователей приложения за последние 12 месяцев). Для обновления идентификаторов с конкретных устройств в реальном времени <Anchor target="_blank" href="/marketers/ru/docs/audiences-configure-additional-identifiers-for-partner-audience-creation">настройте дополнительные идентификаторы</Anchor> в AppsFlyer SDK (пакет средств разработки ПО) или S2S-мобильный API.

<div id="important" />

> 🚧 **Важно!**
>
> Все значения дополнительных идентификаторов **должны** быть зашифрованы с использованием хеширования SHA256. Незашифрованные идентификаторы не будут обработаны.
>
> **Время:** Для обеспечения точного сопоставления идентификаторов API дополнительных идентификаторов аудитории можно использовать уже **на следующий день после** отчета ключевых идентификаторов через AppsFlyer SDK (UTC). Например, ключевые идентификаторы, о которых сообщено 3 января 2022 года (UTC), могут быть обновлены через этот API 4 января 2022 года (UTC) или позже.

<div id="actions" />

## Действия

* [Добавить\/изменить идентификаторы](/docs/upload-additional-identifiers-to-audiences-via-api#addmodify-identifiers-put)
* [Удалить идентификаторы](/docs/upload-additional-identifiers-to-audiences-via-api#remove-identifiers-delete)

<div id="authentication" />

## Аутентификация

Запрос должен включать заголовок HTTP, содержащий API токен AppsFlyer V2.0 вашей учетной записи . Попросите администратора вашей учетной записи получить этот токен с дэшборда AppsFlyer.

<div id="api-specifications-and-sample-code" />

## Спецификации API и пример кода

<div id="addmodify-identifiers-put" />

<Accordion title="Добавить/изменить идентификаторы (PUT)">

<span id="01ECF4ZD0T03JBV8DDH25MM01W"></span>**URL-адрес запроса API**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| Параметр | Описание | Обязательно |
| --- | --- | --- |
| `{app-id}` | Идентификатор приложения, из которого были собраны идентификаторы (как отображается на дэшборде AppsFlyer) | Да |

<span id="01ECF4ZD0TWPH3DXV2YKN7G9B0"></span>**Тело запроса API**

```json
{
  "key_type": "<key_type>",
  "action": "add",
  "data": [
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    },  
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    }
  ]
}
```

| Параметр | Описание | Обязательно |
| --- | --- | --- |
| `{key_type}` | Идентификатор, используемый как уникальное значение для представления пользователя в каждой строке данных запроса.<br /><br />Указанное здесь значение применяется ко всем строкам запроса.<br /><br />Возможные значения:<ul><li>IDFA</li><li>gaid</li><li>IDFV</li><li>идентификатор\_пользователя\_клиента</li><li>imei</li><li>oaid</li></ul> | Да |
| `{action}` | добавить | Нет<br /><br />Значение по умолчанию: добавить |
| `{key_value}` | Допустимое значение идентификатора для указанного key\_type | Да |
| \{identifiers\} | Объект, содержащий имена и ценности идентификаторов для добавления:<ul><li>\{hashed\_emails\}</li><li>\{phone\_number\_sha256\}</li><li>\{phone\_number\_e164\_sha256\}</li></ul> | Да<ul><li>Необходимо указать ценность хотя бы для одного из этих трёх идентификаторов</li></ul> |
| `{hashed_emails}` | Массив из двух хешированных адресов электронной почты<br /><br />Формат:<ul><li>В нижнем регистре</li><li>Без пробелов</li><li>Хеширование SHA256</li></ul>Пример ценности до хеширования: name@domain.com | Нет |
| `{phone_number_sha256}` | Номер телефона (см. примечание ниже)<br /><br />Формат:<ul><li>Без символов, букв или начальных нулей</li><li>Включить код страны</li><li>Хеширование SHA256</li></ul>Пример ценности до хеширования:<br /><br />442070313000 | Нет |
| `{phone_number_e164_sha256}` | Номер телефона в формате E164 (см. примечание ниже)<br /><br />Формат<ul><li>Номер телефона E164</li><li>Хеширование SHA256</li></ul>Пример ценности до хеширования:<br /><br />+442070313000 | Нет |

<div id="notes" />

> 📘 **Примечания**
>
> * Разные рекламные Партнеры поддерживают разные форматы телефонных номеров. Поэтому, если вы решили добавить номер телефона, рекомендуется отправлять оба идентификатора: *phone\_number\_sha256* и *phone\_number\_e164\_sha256*.
> * `customer_user_id` — это тот же идентификатор, который в других местах этого раздела обозначается как CUID (Customer User ID). Если `key_type` имеет значение `customer_user_id`, используйте значение CUID учетной записи в качестве `key_value`. Подробнее об этом и других поддерживаемых идентификаторах см. в <Anchor target="_blank" href="/marketers/ru/docs/audiences-user-identifier-policy">политике идентификаторов пользователей Audiences</Anchor>.

**Ограничения**

К запросу **Добавить/изменить идентификаторы** применяются следующие ограничения:

* Ранее существующие ценности (если таковые имеются) будут перезаписаны ценностями, отправленными в запросе.
* Объект `{data}` может включать максимум 4 000 строк (ключевых значений) на запрос.

**Пример запроса на добавление идентификаторов**

```json
HTTP PUT
body:
{
  "key_type": "idfv",
  "action": "add",
  "data": [
    {
      "key_value": "CDDA802e-AAAA-BBBB-CCCC-DDDDDDDDDDDD",
      "identifiers": {
        "hashed_emails": [
          "34d31be18022626de6b311d6a76e791176d2691b6eef406f524d8f56364c187a",
          "d8c2aec999baad2464e521873ee4465caaf7ff6db8c8b4a25b09ca07694e4dee"
        ],
        "phone_number_sha256": "6c91c4c640f6ef0162833260db4f13dec0df2b683092f4dba7e874bef1acea37",
        "phone_number_e164_sha256": "f3d7e96c73fb0de1b66acfce541d7af758fbd4f3fa3af0ea4e10110000d3625e"
      }
    }
  ]
}
```

</Accordion>

<div id="remove-identifiers-delete" />

<Accordion title="Удалить идентификаторы (PUT)">

**URL-адрес запроса API**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| Параметр | Описание | Обязательно |
| --- | --- | --- |
| `{app-id}` | Идентификатор приложения, из которого были собраны идентификаторы (как отображается на дэшборде AppsFlyer) | Да |

**Тело запроса API**

```json
{
  "key_type": "<key_type>",
  "action": "remove",
  "data": [
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    },
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

| Параметр | Описание | Обязательно |
| --- | --- | --- |
| `{key_type}` | Идентификатор, используемый как уникальное значение для представления пользователя в каждой строке данных запроса.<br /><br />Указанное здесь значение применяется ко всем строкам запроса.<br /><br />Возможные значения:<ul><li>IDFA</li><li>gaid</li><li>IDFV</li><li>идентификатор\_пользователя\_клиента</li><li>imei</li><li>oaid</li></ul> | Да |
| `{key_value}` | Допустимое значение идентификатора для указанного key\_type | Да |
| `{action}` | удалить | Нет<br /><br />Значение по умолчанию: добавить |
| \{identifiers\} | Массив, содержащий имена идентификаторов, для которых необходимо удалить ценности:<ul><li>\{hashed\_emails\}</li><li>\{phone\_number\_sha256\}</li><li>\{phone\_number\_e164\_sha256\}</li></ul> | Да<ul><li>Необходимо включить как минимум один из этих трёх идентификаторов</li></ul> |

**Ограничения**

Объект `{data}` может включать максимум 4 000 строк (ключевых значений) на запрос.

**Пример запроса на удаление идентификаторов**

```json
HTTP PUT
body:
{
  "key_type": "gaid",
  "action": "remove",
  "data": [
    {
      "key_value": "cdda802e-aaaa-bbbb-cccc-dddddddddddd",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

</Accordion>

<div id="responses" />

<Accordion title="Ответы">

| Код | Сообщение | Описание |
| --- | --- | --- |
| 202 | Принято к обработке | Запрос будет применён в следующем окне обработки. |
| 400 | Тело запроса должно содержать допустимый key\_type | Поддерживаются следующие типы ключей:<ul><li>IDFA</li><li>gaid</li><li>IDFV</li><li>идентификатор\_пользователя\_клиента</li><li>imei</li><li>oaid</li></ul> |
| 400 | Запрос должен содержать «данные» как минимум с одним элементом | Список данных не может быть пустым. |
| 400 | Список «данных» не должен превышать размер 4000 в одном запросе | Список данных может содержать максимум 4000 строк. |
| 400 | В запросе слишком много недопустимых элементов данных | Более 10% данных для изменения не соответствуют спецификации. |
| 404 | AppsFlyer — Страница не найдена | Проверьте следующее:<ul><li>Указанный в URL-адресе API запроса `{app-id}` правильный.</li><li>В HTTP-заголовке указан правильный <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">токен API AppsFlyer V2.0</Anchor>. Администратор вашего аккаунта может получить этот токен на дэшборде AppsFlyer.</li></ul> |

**Примеры ответов**

```json
{
"message": "Accepted for processing",
"received": 1000,"invalid": 2,
"trace-id": "698ed323-c787-45b5-b792-463c67c94064"
}
```

```json
{
"error": "Тело запроса должно содержать допустимое значение key_type",
"trace-id": "18a5f685-ea4d-4ca9-beab-a542a3786d12"
}
```

```json
{
"error": "Запрос должен содержать 'data' как минимум с 1 элементом",
"trace-id": "c155a7fa-b573-4efe-9bfb-5ae7de40e7fd"
}
```

```json
{
"error": "Размер 'data' в запросе не должен превышать 4000 элементов в одном запросе",
"trace-id": "b325a7fa-b573-4efe-9bfb-5ae7de40e72c"
}
```

```json
{
"error": "Данные запроса содержат слишком много недопустимых элементов 'data'",
"valid": 2,
"invalid": 30,
"trace-id": "33551c1d-5682-405e-a959-c8729ca74735"
}
```

</Accordion>

<div id="rate-limitations" />

<Accordion title="Ограничения скорости">

* 5 запросов в секунду
* 350 запросов в минуту

</Accordion>

<div data-zendesk-anchors="api-overview=%D0%BE%D0%B1-api h_01HNZP1Y2MQ8W25SNP2XVNZ7WW=%D0%BE%D0%B1-api when-should-i-use-this-api=%D0%BA%D0%BE%D0%B3%D0%B4%D0%B0-%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D0%B5%D1%82-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D1%8D%D1%82%D0%BE%D1%82-api h_01HNZP1Y2MJY56TMN6QH4BVRPA=%D0%BA%D0%BE%D0%B3%D0%B4%D0%B0-%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D0%B5%D1%82-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D1%8D%D1%82%D0%BE%D1%82-api h_01HNZP1Y2MX414NJ49BCVW7KZC=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE methods=%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F h_01HNZP1Y2MS5V43XS008GG4S32=%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F authentication=%D0%B0%D1%83%D1%82%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F h_01HNZP1Y2MH2Y4P8ZT4SVM5GM2=%D0%B0%D1%83%D1%82%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F api-specifications-and-sample-code=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-api-%D0%B8-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BA%D0%BE%D0%B4%D0%B0 h_01HNZP1Y2MR0GCCA1916RMB6GJ=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-api-%D0%B8-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BA%D0%BE%D0%B4%D0%B0 h_01HNZP1Y2M1N548KSMA6MQ601W=addmodify-identifiers-put h_01HNZP1Y2P2VVV4WT88D82QXJ4=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D1%8F h_01HNZP1Y2Q0FAQQE3MTZ8B3FFS=remove-identifiers-delete h_01HNZP1Y2QK2J8ERP1SQTYB20C=responses h_01HNZP1Y2Q1WZCN2TCEAS6HB2X=rate-limitations" />

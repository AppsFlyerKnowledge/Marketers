---
title: API списка приложений для владельцев приложений
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2020-08-17T18:07:10Z'
  edited_at: '2026-08-19T00:17:06Z'
  id: 360011999877
  locale: ru
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ru/articles/360011999877
---
> **Краткий обзор:** Получение активных и ожидающих приложений, связанных с вашим аккаунтом AppsFlyer.

![mceclip0.png](https://files.readme.io/34b4b3d56ca5d7419830ba26701483f64ebb0a908e1e8e7ed65779bb89a14c67-24507752775313.png)

Если вы рекламная сеть, используйте API <Anchor target="_blank" href="/partners/ru/docs/app-list-api-for-ad-networks">списка приложений для рекламных сетей</Anchor>.

**Дополнительные материалы**: <Anchor target="_blank" href="/marketers/ru/docs/about-advertiser-apis">Список API для рекламодателей</Anchor>

## API для получения списка приложений

Следующие разделы содержат информацию, необходимую для использования API.

**Основные сведения о получении списка приложений**

<div id="get-api-list-basics" />

<Accordion title="Основные сведения о списке API">

<table><thead><tr><th>Категория</th><th>Элемент</th><th><span>Description(Описание)</span></th></tr></thead><tbody><tr><td rowspan="3">Запрос</td><td>HTTP-метод</td><td><code>УСТАНОВИТЬ</code></td></tr><tr><td>Путь</td><td><span>https://hq1.appsflyer.com/api/mng/apps</span></td></tr><tr><td>Заголовок авторизации </td><td><ul><li>Обязательный заголовок авторизации содержит токен Bearer. </li><li>Пользователь с правами администратора получает токен в дэшборде следующим образом: <a href="./managing-appsflyer-tokens" target="_blank">Администратор переходит в раскрывающийся список email &gt; API tokens, чтобы получить токен V2.0</a> </li></ul></td></tr><tr><td rowspan="3"> Ответ</td><td>Результаты</td><td>Возвращает в формате JSON</td></tr><tr><td>Лимит запросов</td><td><ul><li>20 запросов/мин</li><li>100 запросов/день</li></ul></td></tr><tr><td>Лимит записей</td><td>1,000 записей/запрос. Если нужно вернуть более 1,000 записей, используйте последующие запросы с пагинацией, описанные в этой статье.</td></tr></tbody></table>

</Accordion>

<div id="api-request" />

<Accordion title="Запрос API">

API-запрос состоит из метода, пути, обязательного параметра capabilities и необязательных параметров пагинации. Токен содержится в заголовке авторизации.

**Аудитории**

```http
GET https://hq1.appsflyer.com/api/mng/apps
```

Обязательные параметры для получения списка приложений:

| Параметр запроса | Description(Описание) |
| --- | --- |
|  | Для этого API нет обязательных параметров запроса |

#### **Механизм пагинации**

Механизм пагинации реализован и действует всегда.

**Принципы пагинации:**

* Возвращает до 1,000 записей на запрос (страницу).
* JSON-ответы содержат следующие ключи, связанные с пагинацией:
  * **meta.total\_items**: количество записей, возвращаемых на всех страницах вместе. Это число приложений, для которых вам были предоставлены запрашиваемые *capabilities* .
  * Ссылки пагинации (показанные в JSON ниже) имеют следующие ключи:
    * **links.prev**: если был предыдущий запрос, то это запрос, использованный для формирования предыдущей страницы.
    * **links.self**: текущий запрос — запрос, использованный для формирования текущего JSON (страницы)
    * **links.next**: запрос, необходимый для получения следующей страницы. Если ключа *next* нет, это последняя страница.

**Используйте один из следующих методов управления пагинацией:**

* [Практические рекомендации] Используйте *links* в JSON: если ключ *links.next* существует, используйте его, чтобы создать запрос для получения следующей страницы. Продолжайте, пока не получите JSON без ключа *links.next* key.
* Программно реализуйте параметры *limit* и *offset* вместе с ключом *total\_items*.

**Пример JSON со ссылками пагинации**

* В примере ниже показан результат второго запроса, содержащий две записи в разделе data (не показано).
* Общее количество возвращаемых записей — 6.
* Ключ **links.next** содержит запрос, который возвращает вторую страницу — записи 5 и 6.

```json
{                                                                                         
    "data": {[...]},   
    "meta": {
        "total_items": 6
    },
    "links": {
        "prev": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=2",
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=2&limit=2",
        "next": "https://hq1.appsflyer.com/api/mng/apps?offset=4&limit=2"
    }
}
```

Параметры механизма пагинации (необязательные):

| Параметр запроса | Description(Описание) |
| --- | --- |
| ограничение | Количество записей, возвращаемых за один вызов<ul><li>Maximum: 1,000</li><li>Если вы не отправляете`limit`, он автоматически устанавливается на 1,000.</li><li>Пример: `limit=2`</li><li>Обязательно: нет</li></ul> |
| offset | Первая запись, возвращаемая в этом вызове. Нумерация записей начинается с 0.<ul><li>Если вы не передаете `offset`, ему автоматически присваивается значение 0.</li><li>Пример: `offset=2`</li><li>Обязательно: нет</li></ul> |

</Accordion>

<div id="json-response" />

<Accordion title="Ответ JSON">

| **Ключ** | **Description(Описание)** |
| --- | --- |
| id | ID приложения, например: `id123456789`, `com.myapp.com` |
| type | Всегда возвращайте `app` |
| Имя камп. | ID приложения |
| platform | iOS или Android |
| currency (валюта) | Код валюты для приложения |
| time\_zone | Часовой пояс приложения |
| total\_items | Количество приложений в аккаунте |
| ссылки | Механизм пагинации (описан в разделе параметров)<ul><li>prev: вызов, используемый для генерации предыдущей страницы</li><li>self: вызов, используемый для генерации текущей страницы</li><li>next: вызов, используемый для генерации следующей страницы</li></ul> |

</Accordion>

<div id="get-app-list-curl-example-and-response" />

<Accordion title="Пример cURL-запроса для получения списка приложений и ответ">

**Запрос cURL**

В этом примере приведен полный вызов, включая необязательные параметры пагинации.

```bash
cURL --location --request GET 'https://hq1.appsflyer.com/api/mng/apps?limit=1000&offset=0' \
-H 'Authorization: Bearer {API V2.0 token having more than 700 characters available to the admin in the dashboard.}' \ \
```

**Ответ JSON**

```json
{
    "data": [
        {
            "id": "com.appsflyer.xpend_qa1",
            "type": "app",
            "attributes": {
                "name": "com.appsflyer.xpend_qa1",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC"
            }
        },
        {
            "id": "com.abc.app",
            "type": "app",
            "attributes": {
                "name": "com.abc.app",
                "platform": "android",
                "currency": "USD",
                "time_zone": "UTC",
                "enable_retargetting": true
            }
        },
        {
            "id": "com.def.app",
            "type": "app",
            "attributes": {
                "name": "com.def.app",
                "platform": "android",
                "currency": "JPY",
                "time_zone": "UTC"
            }
        }
    ],
    "meta": {
        "total_items": 6
    },
    "links": {
        "self": "https://hq1.appsflyer.com/api/mng/apps?offset=0&limit=1000"
           }
}
```

</Accordion>

<div id="http-response-codes" />

<Accordion title="Коды ответа HTTP">

| Код | Сообщение | Примечания/устранение неполадок |
| --- | --- | --- |
| 200 | OK | Возвращаются действительные данные |
| 200 | OK | **Симптом**: данные не возвращаются<br /><br />**Действие**: убедитесь, что токен аутентификации указан в заголовке Bearer. |
| 400 | Неверный запрос | См. сообщение, содержащееся в JSON |
| 401 | Не авторизовано | **Сообщение**: токен авторизации имеет неверный формат<br /><br />Убедитесь, что у вас правильный токен; токен должен содержать не менее 700 символов. |
| 404 | Не найдено | <ul><li>Устраните все проблемы, связанные с сетью или брандмауэром.</li><li>Убедитесь, что <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-server-ip-address-ranges-allowlisting">IP-адреса AppsFlyer внесены в список разрешённых</Anchor></li><li>Убедитесь, что вы используете последний выданный токен.</li><li>Данные не найдены: приложения не найдены.</li></ul> |
| 429 | Слишком много запросов | Превышено ограничение скорости запросов |

</Accordion>

<div data-zendesk-anchors="get-app-list-api=api-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%BF%D0%B8%D1%81%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01KQS56KS2G7TD4VHZCHVP0W9S=api-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%BF%D0%B8%D1%81%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01KQS56KS26TY81ACBN2XBK3W2=get-api-list-basics h_01KQS56KS27NETZ4C5RY28V804=api-request pagination-mechanism=%D0%BC%D0%B5%D1%85%D0%B0%D0%BD%D0%B8%D0%B7%D0%BC-%D0%BF%D0%B0%D0%B3%D0%B8%D0%BD%D0%B0%D1%86%D0%B8%D0%B8 h_01KQS56KS33VFVX099T1S2928G=%D0%BC%D0%B5%D1%85%D0%B0%D0%BD%D0%B8%D0%B7%D0%BC-%D0%BF%D0%B0%D0%B3%D0%B8%D0%BD%D0%B0%D1%86%D0%B8%D0%B8 h_01KQS56KS3Q5EEVSSC7G1FEFXR=json-response h_01KQS56KS3EZCH1KBBQQKTXWYP=get-app-list-curl-example-and-response h_01KQS56KS3S04KDZ58J7XKQNCK=http-response-codes" />

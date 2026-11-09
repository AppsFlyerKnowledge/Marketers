---
title: API межсерверных событий в вебе для PBA (веб-S2S)
metadata:
  keywords:
    - SDK
    - Developers
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-03-23T23:59:00Z'
  edited_at: '2026-08-31T00:23:25Z'
  id: 360006997298
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/360006997298
---
> **Краткий обзор:** Используйте API межсерверных событий в вебе (веб-S2S), чтобы сообщать в PBA о событиях и конверсиях, о которых не сообщает веб-SDK.

<Image align="center" alt="5107_Infographic_Web_S2S_759x270_option1.jpg" src="https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg" />

<div id="web-server-to-server-events-api-for-pba" />

## API межсерверных событий в вебе для PBA

API веб-S2S для атрибуции People-Based дополняет <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide">веб-SDK</Anchor>, позволяя маркетологам сообщать о событиях, происходящих на их сайтах, но не входящих в сферу веб-SDK. Например, посетитель сайта (веб-пользователь) запускает событие онлайн-платежа, которое обрабатывается внутренними системами. После обработки бэкэнд, используя API S2S, сообщает о событии в AppsFlyer.

События, отправленные API S2S:

* регистрируются аналогично событиям, сообщаемым через веб-SDK,
* показаны на дэшбордах PBA, если они указаны как события конверсии,
* заполняют сырые данные PBA, где для *поля event\_source* установлено *веб-S2S*.

<div id="api-use-instructions" />

## Инструкции по использованию API

Создайте вызов API, используя следующие разделы.

| № | Элемент | Примечания |
| --- | --- | --- |
| 1 | Уникальный идентификатор пользователя | <ul><li>Стремитесь предоставить нам наилучший доступный уникальный идентификатор пользователя. Это существенно влияет на анализ данных.</li><li>Лучше всего отправлять CustomerUserId. Если он недоступен, отправьте afUserId — идентификатор cookie сайта, установленный WebSdk.</li><li>В любой момент, когда вы связываете идентификатор клиента (<Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid">CUID</Anchor>) с [afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid), отправьте сообщение setCuID() с обоими идентификаторами.</li></ul> |
| 2 | Временная метка | <ul><li>AppsFlyer применяет строгую проверку входящих временных меток событий:</li></ul><ul><li>**События с поздним прибытием:** События принимаются с исходной временной меткой, если они приходят в течение 24 часов с момента их даты. **Например**, событие с временной меткой понедельника (2025-08-18 23:59 UTC) сохранит эту временную метку, если оно будет отправлено **в любое время до вторника** 23:59:59 UTC. Если то же событие отправляется после вторника 23:59:59 UTC, временная метка будет заменена на время получения события сервером.</li><li>**Метки будущего времени:** События с временной меткой позже фактического времени прибытия запрещены. Такие временные метки также заменяются на время получения сервером.</li></ul><ul><li>Временные метки основаны на UTC. При необходимости переведите местное время в UTC перед заполнением параметра.</li></ul> |
| 3 | Доходы и валюта | Вы должны заполнить *eventRevenueCurrency* и *eventRevenue*, даже если значения содержатся в eventValue. Сделайте это, потому что мы используем их на наших дэшбордах. |

<div id="api-basics" />

<Accordion title="Основы API">

Для реализации API требуются следующие учётные данные, доступные на дэшборде:

* Идентификатор пакета (он же идентификатор пакета бренда)
* Веб-ключ разработчика

**Чтобы получить учётные данные:**

1. В AppsFlyer в верхнем меню выберите **Мои приложения** > **Просмотр пакетов брендов**.  
   Отобразится список пакетов.
2. Скопируйте и запишите:
   * ***Идентификатор пакета бренда***
   * ***Веб-ключ разработчика***

<div id="web-s2s-api-basics" />

#### Основы API веб-S2S

| Путь | `https://webs2s.appsflyer.com/v1/bundleId/method`<ul><li>`bundleId`: идентификатор пакета приложения, доступный на дэшборде.</li><li>`method` — одно из следующего:<ul><li>[event](/docs/web-server-to-server-events-api-for-pba-web-s2s#event-method): отправляется для отчётных событиях бэкенда</li><li>[setCuId:](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method) отправляется при ассоциировании afUserId с вашим CUID</li></ul></li></ul> |
| --- | --- |
| HTTP-метод | `POST` |
| Принятый тип контента | `application/json` |
| Ограничение размера JSON | Размер полезной нагрузки JSON: не более 1 КБ |
| Ограничение предоставления данных | Ограничение POST: 60 000 POST в минуту. Чтобы увеличить лимит, обратитесь к своему менеджеру. |
| TLS | <ul><li>TLS 1.2 или более поздняя версия</li><li><Anchor target="_blank" href="/marketers/ru/docs/appsflyer-https-ssl-encryption-policy-support#исходящие-сообщения-appsflyer-в-роли-клиента">Поддерживаемые шифры</Anchor></li></ul> |

</Accordion>

<div id="setcuid-method" />

<Accordion title="Метод setCuId">

| Название метода | setCuId |
| --- | --- |
| Пример использования | О привязке CUID к посетителю вашего сайта. Например, каждый раз, когда вы сопоставляете веб `afUserId` с идентификатором клиента. Это позволяет PBA сопоставлять данные из различных источников. Это аналогично <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">setCustomerUserId</Anchor> на сайте. |
| Путь к методу | `https://webs2s.appsflyer.com/v1/bundleId/setcuid` |
| Полезная нагрузка | Полезная нагрузка JSON состоит из перечисленных здесь параметров. Все параметры являются обязательными.<ul><li>[customerUserID](/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method)</li><li>[afUserId](/docs/web-server-to-server-events-api-for-pba-web-s2s#extracting-the-web-sdk-afuserid)</li><li>[webDevKey](/docs/web-server-to-server-events-api-for-pba-web-s2s#webdevkey)</li></ul> |

<div id="curl-example-setcuid" />

#### Пример Curl setCuId

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/setcuid' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
        "webDevKey" : "99999999-9999-9999-9999-999999999999"}
```

</Accordion>

<div id="event-method" />

<Accordion title="Метод события">

| Название метода | event |
| --- | --- |
| Пример использования | Отправка |
| Путь к методу | `https://webs2s.appsflyer.com/v1/bundleId/event` |
| Подробная информация | В разделе [Описание метода события](/docs/web-server-to-server-events-api-for-pba-web-s2s#описание-метода-события) этой статьи содержится информация о полезной нагрузке, пример Curl, пример Python и рекомендации по тестированию. |

</Accordion>

<div id="event-method-details" />

## Описание метода события

<div id="payload-parameters" />

<Accordion title="Параметры полезных данных">

Параметры полезной нагрузки делятся на идентификаторы пользователей и параметры событий.

* Идентификатор пользователя: <mark>Вы должны отправить хотя бы один параметр идентификатора пользователя.</mark>
* Событие: Отправьте обязательные параметры и необязательные по мере необходимости.

<div id="user-identifier-parameters-send-at-least-one-parameter" />

#### Параметры идентификатора пользователя (отправьте хотя бы один параметр)

| Параметр Идентификатор пользователя | Описание |
| --- | --- |
| <span id="customeruserid"></span>customerUserId | <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid">Идентификатор клиента (CUID)</Anchor> — это уникальный идентификатор, установленный вами.<ul><li>Используйте идентичный идентификатор для событий, о которых AppsFlyer сообщает любым способом. Это означает, что один и тот же идентификатор используется в веб-SDK, мобильном SDK и S2S API.</li><li><Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">Идентификатор клиента в веб-SDK</Anchor></li><li>Формат: Строка</li><li>Пример: `"customerUserId" : "663274"`</li><li>Заполняет поле сырых данных: `customer_user_id`</li></ul> |
| <span id="afuserid"></span>afUserId | Уникальный идентификатор пользователя, присваиваемый веб-SDK каждому пользователю, который посещает ваш сайт. Вам нужно будет передать значение cookie на внутренние серверы.<ul><li>Подробности о cookie:<ul><li>Имя: afUserId</li><li>Значение: установите *afUserId* в это значение</li><li>Домен: website-domain</li></ul></li><li>Пример: `"afUserId" : "unique_cookie_uuid"`</li><li>Заполняет поле сырых данных: `af_web_id`</li></ul> |

<div id="event-parameters" />

#### Параметры события

| Название параметра | Обязательно | Описание |
| --- | --- | --- |
| <span id="webdevkey"></span>webDevKey | Да | Заполните с помощью [веб-ключа разработчика](/docs/web-server-to-server-events-api-for-pba-web-s2s#getting-the-web-dev-key), доступного на дэшборде.<ul><li>Пример:`"webDevKey" : "ffffffff-ffff-ffff-ffff-ffffffffffff"`</li></ul> |
| <span id="eventtype"></span>eventType | Да | Идентификатор атрибута события для внутреннего использования AppsFlyer. Всегда устанавливается на *EVENT*.<ul><li>Пример: `"eventType" : "EVENT"`</li></ul> |
| <span id="eventname"></span>eventName | Да | <ul><li>Мы используем этот параметр для разграничения событий конверсии и не конверсии, используя <Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings#web-event-settings">список событий конверсии</Anchor>, установленный маркетологом в настройках PBA.</li><li>Убедитесь, что вы заполнили его значениями, соответствующими логике конверсии маркетолога.</li><li>Формат: Строка</li><li>Пример: `"eventName" : "web_purchase"`</li><li>Заполняет поле сырых данных: `event_name`</li></ul> |
| <span id="timestamp"></span>временная метка | Нет | Время наступления события в миллисекундах. Отправьте в виде <Anchor target="_blank" href="https://www.unixtimestamp.com/">временной метки Unix</Anchor>, состоящей из 13 цифр.<ul><li>Если временная метка не отправлена, время устанавливается по времени сервера.</li><li>**События, поступающие с опозданием, отмечаются по текущему времени сервера.** Опоздание означает прибытие после полуночи по UTC на следующий день после события. Например, событие, произошедшее в понедельник, **должно** быть обработано до полуночи вторника по UTC.</li><li>События, имеющие временную метку в будущем (относительно текущего времени сервера), отмечаются временем сервера.</li><li>Формат: Int</li><li>Пример: `"timestamp" : 1584835200123`</li><li>Заполняет поле сырых данных: `event_time`</li></ul> |
| <span id="eventvalue"></span>Значение события | Нет | Сопоставление параметров события, описывающих событие. Используйте этот параметр для отправки расширенных внутренних событий приложения, таких как артикул товара, цена позиции.<ul><li>**Примечания о доходе:** Вы можете заполнить этот параметр данными о доходе. Вы можете заполнить этот параметр данными о доходе. Кроме того, необходимо заполнить поля *eventRevenue,* and *eventRevenueCurrency.*</li></ul><ul><li>Формат: JSON</li><li>Пример: Для отправки SKU ABC123, имеющего синий цвет и цену за единицу товара $3,99, установите eventValue на:<br />`{"Purchase": {"sku" : "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}}`</li><li>Ограничение: 1000 символов. Не превышайте этого значения, оно будет усечено.</li><li>Заполняет поле сырых данных: `event_value`</li></ul> |
| <span id="eventrevenuecurrency"></span>eventRevenueCurrency | Нет | Код валюты для события выручки, представляющий собой код валюты по <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> из 3 символов.<ul><li>По умолчанию: USD (доллар США)</li><li>Формат: Строка</li><li>Пример:  `"eventRevenueCurrency" : "EUR"`</li><li>Заполняет поле сырых данных: `event_revenue_currency`</li></ul> |
| <span id="eventrevenue"></span>eventRevenue | Нет | Доход (денежное выражение), назначенный событию.<br /><br />**Примечание!** Если доход указан в *eventValue*, укажите его также в *eventRevenue* и заполните eventRevenueCurrency.<ul><li>Допускаются отрицательные значения. Например, возврат денег.</li><li>Формат: Тип: Float</li><li>Примеры значений: `1` `1.2` `1234.20` `-1234.20`</li><li>Заполняет поле сырых данных: `event_revenue`</li></ul> |
| <span id="eventcategory"></span>~~eventCategory~~ | Нет | Этот параметр устарел и будет удалён из системы в будущем. Вместо этого используйте eventValue. |
| <span id="eventlabel"></span>~~eventLabel~~ | Нет | Этот параметр устарел и будет удалён из системы в будущем. Вместо этого используйте eventValue. |
| <span id="referrer"></span>Referrer | Нет | HTTP-реферер<ul><li>Формат: Строка</li><li>Пример:`"referrer" : "https://www.google.com/"`</li><li>Заполняет поле сырых данных: `http_referrer`</li></ul> |
| <span id="useragent"></span>userAgent | Нет | <Anchor target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/User-Agent">Запрос пользовательского агента</Anchor>, отправляемый браузером на сервер.<ul><li>По возможности отправьте это значение, так как оно помогает определить тип устройства.</li><li>Формат: Строка</li><li>Пример:`"userAgent" : "Chrome/80.0.3987"`</li><li>Заполняет поле сырых данных: `user_agent`</li></ul> |
| <span id="ip"></span>ip | Нет | IP-адрес пользователя<ul><li>По возможности отправьте значение этого поля. Оно помогает определить <Anchor target="_blank" href="/marketers/ru/docs/determine-user-location">геолокацию</Anchor> пользователя.</li></ul><ul><li>Формат: Строка</li><li>Пример:`"ip": "192.0.2.1"`</li><li>Заполняет поле сырых данных: `ip`</li></ul> |

</Accordion>

<div id="curl-example" />

<Accordion title="Пример для Сurl">

```bash
curl --location --request POST 'https://webs2s.appsflyer.com/v1/bundleId/event' \
--header 'Accept-Encoding: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"customerUserId": "1234567890abcdef",
	"afUserId":"9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey" : "99999999-9999-9999-9999-999999999999",
    "ip" : "192.0.2.1",
	"eventType":"EVENT",
	"timestamp" : 1234567890123,
	"eventName":"my_web_event",
	"eventRevenueCurrency" : "EUR",
	"eventRevenue" : 1234.56,

		"eventValue": {
		"purchase":{
		 "shoes": "color",
		 "quantity" : "3",
		 "Revenue" : "1234.56",
		 "Currency" : "ZAR"
		}
	}

}'
```

</Accordion>

<div id="python-example" />

<Accordion title="Пример для Python">

```python
''' using the requests python package, install using pip install requests  '''
import requests
url = "https://webs2s.appsflyer.com/v1/bundleId/event"
payload = {
    "customerUserId": "1234567890abcdef",
    "afUserId": "9999999-f848-4963-a091-568f0bf9a361",
    "webDevKey": "99999999-9999-9999-9999-999999999999",
    "ip": "192.0.2.1",
    "eventType": "EVENT",
    "timestamp": 1234567890123,
    "eventName": "my_web_event",
    "eventRevenenuCurrency": "EUR",
    "eventRevenue": 1234.56,
    "eventValue":
        {
            "purchase":
            {
                "shoes": "color",
                "quantity": "3",
                "Revenue": "1234.56",
                "Currency": "ZAR"
            }
        }
    }
headers = {
    'Accept-Encoding': 'application/json',
    'Content-Type': 'application/json'
}
response = requests.request("POST", url, headers=headers, json=payload)
print(response.text.encode('utf8'))
```

</Accordion>

<div id="testing" />

<Accordion title="Тестирование">

Для тестирования отправьте несколько событий следующим образом:

1. Отправьте событие.
2. Убедитесь, что вы получили код возврата 200 OK. Если нет, примите меры по исправлению ситуации, используя коды возврата и сообщения об ошибках.
3. Подождите несколько часов после полуночи UTC, чтобы увидеть зарегистрированное событие в сырых данных PBA. Вы должны подождать, потому что данные PBA обрабатываются один раз в день.

</Accordion>

<div id="additional-information" />

## Дополнительные сведения

<div id="getting-the-web-dev-key" />

<Accordion title="Получение веб-ключа разработчика.">

**Чтобы получить веб-ключ разработчика:**

1. В AppsFlyer перейдите на вкладку ***Мои приложения***.
2. Нажмите Просмотреть пакет бренда.

   <Image align="center" alt="GetWebDevKeyPba_us-en.pn" src="https://files.readme.io/e6fdec52461790183f1b12f540db51235a0bb01d3489084ed78a40e96e207495-360007733958.png" />
3. Скопируйте необходимый ***веб-ключ разработчика*.**

</Accordion>

<div id="extracting-the-web-sdk-afuserid" />

<Accordion title="Извлечение afUserID из веб-SDK">

* `afUserId` — это уникальный идентификатор, устанавливаемый в веб-SDK при первом посещении пользователем вашего сайта.
* Если вам нужен `afUserId`, воспользуйтесь одним из следующих способов.

<div id="get-afuserid-from-the-http-cookie-header" />

#### **Получение afUserId из заголовка HTTP cookie**

* Значение `afUserId` отправляется браузером посетителя при обращении к вашему сайту.
* При необходимости извлеките его из заголовка HTTP cookie.

<div id="viewing-afuserid-in-the-visitors-browser" />

#### **Просмотр afUserId в браузере посетителя**

* Просмотрите `afUserId` в браузере посетителя в целях устранения неполадок и отладки.
* Чтобы параметр стал доступен, посетитель должен хотя бы один раз зайти на страницу с веб-SDK.
* Файл cookie, содержащий `afUserId`, является файлом cookie первой стороны по отношению к вашему домену.
* Следующая процедура была подготовлена с использованием Chrome 81. В разных браузерах и операционных системах могут быть некоторые различия.

**Чтобы получить afUserId из браузера посетителя:**

1. В своём браузере перейдите на свой сайт.
2. Нажмите правой кнопкой мыши, выберите ***Inspect.***  
   Откроется окно браузера для проверки элементов.

   <Image align="center" alt="S2S_inspect.jpg" src="https://files.readme.io/d1608d0085cb5333ad9631acdfb5306398f0388f42b5b3a333493daad8923385-360008059697.jpg" />
3. Перейти на вкладку (A) ***Application***.
4. В боковом меню (B) раскройте Cookies.
5. Выберите свой сайт. Если он не отображается, обновите браузер.
6. В поле (C) ***фильтр*** введите `afUserId`  
   Отобразится значение afUserID.

</Accordion>

<div id="response-codes" />

<Accordion title="Коды ответа">

| Код ответа | Сообщение | Способ устранения |
| --- | --- | --- |
| 200 | OK |  |
| 404 | Не найдено | <ul><li>Проверьте конечную точку</li><li>Проверьте правильность идентификатора пакета</li></ul> |
| 400 | Неверный запрос | <ul><li>В JSON обнаружена ошибка. Подробности см. в сообщении об ошибке.</li></ul> |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Устранение неполадок">

* Признак ошибки:  Коды возврата HTTP не возвращаются  
  Решение: Внесите серверы AppsFlyer в <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-server-ip-address-ranges-allowlisting">список разрешённых</Anchor>

</Accordion>

<div id="release-notes" />

<Accordion title="Примечания">

<table><caption>Заметки о выпуске веб-SDK</caption><thead><tr><th>Дата </th><th>Версия конечной точки\*</th><th>Примечания</th></tr></thead><tbody><tr><td>12.05.2020</td><td>1</td><td> Первоначальный релиз</td></tr><tr><td>24.05.2020</td><td>1</td><td> </td></tr></tbody><tfoot><tr><td colspan="3">\* Номер версии относится к номеру версии конечной точки. <code>https://webs2s.appsflyer.com/v1/<var>method</var></code> </td></tr></tfoot></table>

</Accordion>

<div data-zendesk-anchors="web-servertoserver-events-api-for-pba=api-%D0%BC%D0%B5%D0%B6%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%BD%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%B2%D0%B5%D0%B1%D0%B5-%D0%B4%D0%BB%D1%8F-pba h_01HKW2YAW4HHYK27F41HC3B24Y=api-%D0%BC%D0%B5%D0%B6%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%BD%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2-%D0%B2%D0%B5%D0%B1%D0%B5-%D0%B4%D0%BB%D1%8F-pba api-use-instructions=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8E-api h_01HKW2YAW4DCESP3MNY9D4GTFK=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8E-api h_01HKW2YAW4Z6G8HEVJJHCVG9G3=api-basics web-s2s-api-basics=%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D1%8B-api-%D0%B2%D0%B5%D0%B1-s2s h_01HKW2YAW4XDKZ3YGAHAP3AG2T=%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D1%8B-api-%D0%B2%D0%B5%D0%B1-s2s h_01HKW2YAW4YFK2WWKM0VB8AGNN=setcuid-method curl-example-setcuid=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-curl-setcuid h_01HKW2YAW5SJFKGTNRGRKN6NCJ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-curl-setcuid h_01HKW2YAW5A9TJGZG08K4ZW69C=event-method event-method-details=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F h_01HKW2YAW53H43SCYTDXAYBDHX=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D0%B0-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F h_01HKW2YAW5WDPMXDKA3X4HZBD2=payload-parameters user-identifier-parameters-send-at-least-one-parameter=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-%D1%85%D0%BE%D1%82%D1%8F-%D0%B1%D1%8B-%D0%BE%D0%B4%D0%B8%D0%BD-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80 h_01HKW2YAW5RR4Q2PCWC9717ACG=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-%D1%85%D0%BE%D1%82%D1%8F-%D0%B1%D1%8B-%D0%BE%D0%B4%D0%B8%D0%BD-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80 event-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F h_01HKW2YAW5G46ZV4Z0CYEWB011=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F h_01HKW2YAW56HZ0WYRWNBATB8WR=curl-example h_01HKW2YAW5A78VREGZEZ12XMPE=python-example h_01HKW2YAW59JSCCACGD2H153M5=testing additional-information=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW2YAW5D4N3SYA625F10YFW=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW2YAW5HV506YV5328ME236=getting-the-web-dev-key h_01HKW2YAW52T0KME7P2CRQ6WBR=extracting-the-web-sdk-afuserid get-afuserid-from-the-http-cookie-header=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-afuserid-%D0%B8%D0%B7-%D0%B7%D0%B0%D0%B3%D0%BE%D0%BB%D0%BE%D0%B2%D0%BA%D0%B0-http-cookie h_01HKW2YAW5FK04C3AWCXGP1XAW=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-afuserid-%D0%B8%D0%B7-%D0%B7%D0%B0%D0%B3%D0%BE%D0%BB%D0%BE%D0%B2%D0%BA%D0%B0-http-cookie viewing-afuserid-in-the-visitors-browser=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-afuserid-%D0%B2-%D0%B1%D1%80%D0%B0%D1%83%D0%B7%D0%B5%D1%80%D0%B5-%D0%BF%D0%BE%D1%81%D0%B5%D1%82%D0%B8%D1%82%D0%B5%D0%BB%D1%8F h_01HKW2YAW5CT2WZ229KJD2FWYK=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-afuserid-%D0%B2-%D0%B1%D1%80%D0%B0%D1%83%D0%B7%D0%B5%D1%80%D0%B5-%D0%BF%D0%BE%D1%81%D0%B5%D1%82%D0%B8%D1%82%D0%B5%D0%BB%D1%8F h_01HKW2YAW5HTV9N4ZEJJ99RBN0=response-codes h_01HKW2YAW6MG7VNQJAB1Q37K6T=troubleshooting h_01HKW2YAW6RM6VJKFECT0ETGTG=release-notes" />

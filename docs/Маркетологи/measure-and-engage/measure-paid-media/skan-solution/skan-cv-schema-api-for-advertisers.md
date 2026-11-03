---
title: API схемы CV SKAN для рекламодателей
metadata:
  keywords:
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-08-24T12:59:10Z'
  edited_at: '2026-09-01T00:32:17Z'
  id: 8610329713553
  locale: ru
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ru/articles/8610329713553
---
> **Краткий обзор:** Просмотрите текущую схему значения конверсии (CV) SKAdNetwork (SKAN), настроенную в AppsFlyer Conversion Studio.

## API схемы значения конверсии SKAN

<div id="api-basics" />

<Accordion title="Основы API">

| Информация о компании | Просмотрите текущую схему значения конверсии (CV) SKAdNetwork (SKAN), настроенную в AppsFlyer Conversion Studio.<br /><br />**Внимание**:<ul><li>Историческая схема CV SKAN недоступна.</li><li>Вы также можете просмотреть свою схему SKAN, загрузив CSV-файл сопоставления, доступный в Conversion Studio.</li></ul> |
| --- | --- |
| Путь | `https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>` |
| Параметры пути (обязательные) | `<app_id>`: идентификатор приложения, указанный на дэшборде AppsFlyer. Вставьте его точно в том же виде, в каком он отображается на дэшборде. Пример: id123456789 |
| HTTP-метод | `УСТАНОВИТЬ` |
| Тип содержимого ответа | `text/plain` |
| Авторизация | Требуется HTTP-заголовок `Authorization`, содержащий токен API V2 (токен Bearer).<br /><br />![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Пользователь с правами администратора <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">получает токен V2 на дэшборде</Anchor>: в верхней панели откройте меню аккаунта (раскрывающееся меню с адресом электронной почты) > **Центр безопасности** > **Токены AppsFlyer API и S2S**. |
| Ограничение предоставления данных | <ul><li>Запросы возвращают до 50 тыс. строк</li><li>10 вызовов в минуту</li></ul> |
| Дата последнего изменения конфигурации | <ul><li>В режиме decode дата отображается в имени файла.</li><li>Во всех остальных режимах дата отображается в столбце last\_config\_change.</li></ul> |

### Пример запроса (cURL)

```shell
curl --request \
GET 'https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>' \
--header 'Authorization: Bearer <V2_AUTH_TOKEN_HERE (строка из более чем 700 символов)>'
```

</Accordion>

<div id="report-name" />

<Accordion title="Название отчёта">

API возвращает CSV-файл со следующей схемой именования:

Для режима decode: `conversion_value_mapping_<дата последнего изменения конфигурации схемы>`

Для всех остальных режимов: `conversion_schema_report_custom_encode`

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Спецификации и ограничения">

| Специфика | Примечания |
| --- | --- |
| Доступ к рекламной сети | Если вы являетесь партнером по аналитике, попросите рекламодателя предоставить вам разрешение. |
| Доступ агентств | Недоступно |
| Доступ пользователей аккаунта | Токен авторизации доступен администратору в дэшборде. |

</Accordion>

<div id="http-response-codes-and-troubleshooting" />

<Accordion title="Коды ответов HTTP и устранение неполадок">

| HTTP | Ответ | Специфика |
| --- | --- | --- |
| 200 | OK | Возвращены корректные данные (CSV) |
| 400 | Неверный запрос | Недопустимый запрос |
| 401 | Не авторизовано | Токен авторизации отсутствует или недействителен<br /><br />Убедитесь, что вы используете токен правильно |
| 401 | Слишком много запросов | Превышен лимит частоты запросов |
| 403 | Нет разрешения | У вас нет разрешения на доступ к этому отчету. Если вы являетесь партнером по аналитике, попросите рекламодателя предоставить вам разрешение. |
| 404 | Не найдено | <ul><li>Устраните все проблемы, связанные с сетью или брандмауэром.</li><li>Убедитесь, что <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-server-ip-address-ranges-allowlisting">IP-адреса AppsFlyer добавлены в список разрешенных</Anchor></li></ul> |

</Accordion>

<div data-zendesk-anchors="skan-conversion-value-schema-api=api-%D1%81%D1%85%D0%B5%D0%BC%D1%8B-%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-skan h_01HKW1B4XQH2JCJ3T0M1D6W7EM=api-%D1%81%D1%85%D0%B5%D0%BC%D1%8B-%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-skan h_01HKW1B4XQCZPQBQFADGNTZDC3=api-basics request-example-curl=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0-curl h_01HKW1B4XQXQW0Z0G8ZF9EE8AZ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0-curl h_01HKW1B4XQ6ZD45YPHKHDHAZX0=report-name h_01HKW1B4XQVFNM33WV73BA5QXG=traits-and-limitations h_01HKW1B4XQY0V30B4BYCRF9HP5=http-response-codes-and-troubleshooting" />

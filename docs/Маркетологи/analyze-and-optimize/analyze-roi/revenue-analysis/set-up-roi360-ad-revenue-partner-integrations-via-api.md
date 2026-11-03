---
title: Настройте интеграции с партнерами по доходу от рекламы в ROI360 через API
metadata:
  keywords:
    - ad revenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-10-16T14:53:47Z'
  edited_at: '2026-08-27T00:01:53Z'
  id: 9901416616465
  locale: ru
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ru/articles/9901416616465
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Кратко:** Настройте интеграции с партнерами по доходу от рекламы для своего аккаунта AppsFlyer или отдельных приложений через API.

## API интеграции с партнерами по доходу от рекламы

API интеграции с партнерами по доходу от рекламы используется для:

* Настройте конфигурации партнеров по доходу от рекламы на уровне приложения для всего аккаунта.
* Получите список текущих конфигураций партнеров по доходу от рекламы для всего аккаунта.

<div id="set-api" />

<Accordion title="Настроить API">

**Чтобы настроить (сконфигурировать) интеграции с партнерами по доходу от рекламы через API**:

1. Получите <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">токен API V2</Anchor> в дэшборде AppsFlyer. Требуется для авторизации API. **Примечание**: Это должен сделать администратор аккаунта.
2. Подготовьте параметры для включения в API-запрос, как описано в следующей таблице.
3. Передайте значения параметров своему разработчику и попросите его следовать <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">инструкциям API по настройке интеграций</Anchor> в Dev Hub.  
   Интеграция вступает в силу на следующий день в 00:00 UTC.

#### Параметры запроса

| Параметр | Description(Описание) |
| --- | --- |
| в один клик | <ul><li>Объект верхнего уровня, который должен включать app\_id, network и products (перечислены ниже).</li><li>Другие поля могут включать credentials, event\_name и source\_event.</li></ul> |
| app\_id (идентификатор приложения) | Идентификатор ID приложения, которое вы хотите интегрировать. |
| network | <ul><li>Партнер, которого вы хотите интегрировать.</li><li>Список поддерживаемых сетей см. в столбце network <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">таблицы параметров API партнеров по доходу от рекламы</Anchor>.</li></ul> |
| учётные данные | <ul><li>Для интеграции с сетью требуются 1 или несколько учетных данных.</li><li>Список учетных данных см. в столбцах cred <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">таблицы параметров API партнеров по доходу от рекламы</Anchor>.</li></ul> |
| имя\_события | <ul><li>Значение по умолчанию: af\_ad\_revenue</li><li>Также может быть пользовательским именем события [бета]</li><li>event\_name не требуется, если enabled имеет значение false.</li></ul> |
| продукты | <ul><li>Список всех включённых продуктов в интеграции, включая параметры name, enabled и, при необходимости, source\_event (перечислено ниже).</li><li>Список названий типов интеграции, см. в столбце bulk API products таблицы <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">параметров API партнёров по доходу от рекламы</Anchor>.</li></ul> |
| Имя камп. | <ul><li>Название типа интеграции.</li><li>Список поддерживаемых продуктов для каждой сети см. в столбце bulk API products таблицы <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">Ad revenue partner API parameter table</Anchor>.</li></ul> |
| вкл. | <ul><li>Идентификатор агентства, полученный от первой вспомогательной атрибуции<ul><li>true</li><li>= false\`</li></ul></li><li>Для типов интеграции на уровне приложения требуется source-event.</li><li>Если значение равно false, ни source\_event, ни event\_name не требуются.</li></ul> |
| source\_event | <ul><li>Применимо только к партнерским интеграциям S2S API на агрегированном уровне.</li><li>Для типов интеграции на уровне приложения, если enabled имеет значение true, требуется source\_event.</li></ul> |

</Accordion>

<div id="get-api" />

<Accordion title="Получить API">

**Чтобы получить через API список интеграций с партнерами по доходу от рекламы**:

1. Получите <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">токен API V2</Anchor> в дэшборде AppsFlyer. Требуется для авторизации API.
2. Попросите разработчика следовать <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">инструкциям по работе с API для получения списка интеграций</Anchor> в Dev Hub.

</Accordion>

### Спецификации и ограничения

| **Специфика** | **Специфика** |
| --- | --- |
| Лимит вызовов | До 1 0000 интеграций в рамках одного вызова. |
| OAuth | Партнеры, интегрированные через OAuth (например, Google и Facebook), не поддерживаются. |

<div data-zendesk-anchors="ad-revenue-partner-integration-api=api-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0%D0%BC%D0%B8-%D0%BF%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D1%83-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B h_01HYD2M7E1PH0ARZRF0P17K80J=api-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0%D0%BC%D0%B8-%D0%BF%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D1%83-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B h_01HYD2M7E1DX9FAJ0MGN500NZV=set-api request-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0 h_01HYD2M7E1FYY96HNM6DSHXPQ5=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D0%B0 h_01HYD2M7E19XCCFF1NT40VBWH7=get-api specs-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HYD2M7E1X2PEQ616PWMTWCH7=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

---
title: Редактирование измерений чистой выручки с помощью налогового API (Tax API)
metadata:
  keywords:
    - Revenue
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
  created_at: '2024-11-28T13:57:14Z'
  edited_at: '2026-08-19T00:02:14Z'
  id: 30468586765841
  locale: ru
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ru/articles/30468586765841
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Кратко:** настройте, как AppsFlyer рассчитывает чистый доход от покупок в приложении и подписок, используя Net Revenue API для настройки ставок комиссии магазина и налоговых правил для каждого приложения. Это гарантирует, что ваши отчеты точно отражают фактический доход, в том числе в случаях нестандартных комиссий или специальных налоговых правил.

Продукт ROI360 Store Revenue рассчитывает чистый доход от покупок в приложении и подписок, автоматически вычитая из валового дохода комиссию магазина и налог. Конфигурация по умолчанию отражает стандартные комиссии и налоговые правила, применяемые магазином приложений и Google Play. Если комиссия вашего магазина отличается или вы работаете в стране со специальным налогообложением, используйте Net Revenue API, чтобы переопределить конфигурацию по умолчанию.

Net Revenue API реализован через два REST API, которые позволяют настраивать ставки комиссии магазина и налоговые правила для отдельных приложений.

* [Ставки комиссии магазина](https://dev.appsflyer.com/hc/reference/post_store-commission-rates): создание, обновление, получение и удаление ставок комиссии магазина для одного или нескольких приложений. Для каждого приложения можно задать отдельную ставку комиссии в зависимости от различных программ магазина.
* [Правила налоговых ставок](https://dev.appsflyer.com/hc/reference/post_tax-rates-app-app-id): создание или получение пользовательских правил налоговых ставок для конкретного приложения.

Подробнее о том, как рассчитывается чистый доход, см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-roi360-store-revenue#true-revenue">Net revenue</Anchor>.

<div id="note" />

> 📘 **Примечание:**
>
> Чистый доход отображается в отчетах о сырых данных и в разделе «Мои дэшборды» как нетто-метрики (Net revenue, Net ROI, Net ROAS, Net ARPU, Net profit).

<div id="ios" />

<div id="update-tax-rate-rules" />

## Обновление правил налоговых ставок

**По умолчанию налог указывается в отчете по любой транзакции, измеряемой ROI360, с использованием конфигурации налоговых ставок по умолчанию.** В *странах с ценами с учетом налога*, где налог включен в прейскурантную цену, чистый доход рассчитывается после вычета налога. Так, например, в Великобритании AppsFlyer вычитает сумму налога и комиссии магазина. В *странах с ценами без учета налога*, например в США, где прейскурантная цена не включает налог, параметры дохода и чистого дохода по умолчанию не включают налог.

Чтобы настроить правила налоговых ставок с помощью Net Revenue API, выполните следующие действия:

1. Выполните следующие действия в настройках ROI360 Store Revenue:

   <Accordion title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

   * <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue#шаг-1-ios-настройка-ключей-app-store-connect">1. Настройка ключей App Store Connect</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue#шаг-2-ios-настройка-уведомлений-сервера-app-store">2. Настройка уведомлений сервера App Store</Anchor>

   </Accordion>

   <div id="android" />

   <Accordion title="Android;">

   * <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue#step-1-android-настройка-ключа-сервисного-аккаунта-и-разрешений">1. Настройка разрешений и ключа учётной записи службы</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue#шаг-2-android-настройка-уведомлений-сервера-google-play">2. Настройка уведомлений сервера Google Play</Anchor>

   </Accordion>

2. Предоставьте своему разработчику:
   * <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">Токен API V2</Anchor> для использования в качестве ключа авторизации.
   * Параметры и значения, содержащие информацию о том, какие налоги необходимо рассчитать, как указано в таблице ниже.
3. Сообщите своему разработчику, что ему необходимо следовать <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-tax-rate-rule">инструкции по налоговому API</Anchor> для создания правил расчета налоговых ставок. **Примечание**: API допускает наличие JSON-файла в теле запроса post. <Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">В этом JSON-файле</Anchor> отображаются все поддерживаемые страны и их налоговые ставки по умолчанию. Разработчик может редактировать его или использовать в API без изменений.

<div id="tax-rate-api-parameters" />

### Параметры и значения для использования в API

| Параметр | Обязательно | Примечания |
| --- | --- | --- |
| `tax_name` | Да | <ul><li>Название, указанное в счете-фактуре клиента, описывающее конкретный тип налога.</li><li>Пример: Налог с продаж, НДС, федеральный налог на товары и услуги</li></ul> |
| `tax_rate` | Да | <ul><li>Значение должно быть больше 0.</li><li>Число с количеством десятичных знаков до 4, отображающее в процентах налог, который нужно собрать.</li><li>Пример: 7,25</li></ul> |
| `tax_exclusive` | Нет | <ul><li>Логический параметр: true (истина) или false (ложь).</li><li>False означает, что налог включен в общую выручку.</li><li>True означает, что налог взимается дополнительно к общей заявленной выручке. Например, в США или Канаде цена указана без учета налога с продаж.</li><li>По умолчанию установлено значение false.</li></ul> |
| `Страна` | Нет | <ul><li><Anchor target="_blank" href="https://www.nationsonline.org/oneworld/country_code_list.htm">Двухбуквенный код страны по стандарту ISO,</Anchor> для которой применяется налог.</li><li>Пример: CA</li><li>Примечание. Для Великобритании используется код «UK», а не «GB».</li></ul> |
| `subdivision` | Нет | <ul><li>В некоторых странах может быть дополнительно указан штат/муниципальное образование.</li><li>Обрабатывается в соответствии с [кодами ISO 3166-2 для административных подразделений](https://service.unece.org/trade/locode/2022-2%20SubdivisionCodes.htm).</li><li>Должен включать код страны и код муниципального образования.</li><li>Пример: US-CA</li></ul> |
| `postal_code` | Нет | <ul><li>Строка из букв и/или цифр</li><li>Пример: L4J8E3</li></ul> |
| `deduction_order` | Нет | <ul><li>Перечисление: **0**, **1** или **2**:<ul><li>0 означает, что сначала из валового дохода вычитается комиссия магазина, а из оставшейся суммы вычитается налог.</li><li>1 означает, что сначала из валового дохода вычитается налог, а из оставшейся суммы вычитается комиссия магазина.</li><li>2 означает, что из валового дохода вычитается и налог, и комиссия магазина.</li></ul></li></ul> |

<div id="set-up-store-commission-rates" />

## Настройка ставок комиссии магазина

По умолчанию AppsFlyer применяет стандартную логику комиссии магазина при расчете чистого дохода. Значения по умолчанию в App Store зависят от региона (актуальные ставки для каждой витрины см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-roi360-store-revenue#true-revenue">О доходе магазина ROI360</Anchor>). Если для вашего приложения действуют сниженные или нестандартные сборы магазина, используйте Net Revenue API, чтобы переопределить ставку комиссии магазина на уровне приложения.

Несколько примеров:

* Ваше приложение подпадает под сниженные сборы магазина, например:
  * Программа Apple App Store Small Business Program (комиссия 15%; 12% в материковом Китае (CN))
  * Уровень сервисного сбора 15% в Google Play (первые 1 млн USD годового дохода)
* Размер комиссии магазина со временем меняется, и поскольку AppsFlyer не видит статус вашей комиссии магазина, вам нужно вручную обновлять применяемую ставку с помощью Net Revenue API, например:
  * Применение сниженной комиссии, когда ваше приложение начинает соответствовать условиям для более низкого сбора магазина
  * Возврат к логике комиссии магазина по умолчанию, когда сниженная ставка больше не применяется

<div id="ios::f410adfc" />

<div id="update-store-commission-with-the-net-revenue-api" />

### Обновление комиссии магазина с помощью Net Revenue API

С помощью Net Revenue API можно управлять настройками комиссии магазина следующими способами:

* Проверьте существующие конфигурации, отправив GET-запрос, чтобы получить ставки комиссии магазина для приложений в учетной записи
* Примените пользовательскую комиссию, отправив POST-запрос с требуемой ставкой комиссии
* Вернитесь к логике по умолчанию, отправив DELETE-запрос для соответствующего приложения

Перед использованием API:

1. Выполните следующие действия в настройках дохода магазина ROI360:

   <Accordion title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

   * <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue#шаг-1-ios-настройка-ключей-app-store-connect">1. Настройка ключей App Store Connect</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue#шаг-2-ios-настройка-уведомлений-сервера-app-store">2. Настройка уведомлений сервера App Store</Anchor>

   </Accordion>

   <div id="android::659c7976" />

   <Accordion title="Android;">

   * <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue#step-1-android-настройка-ключа-сервисного-аккаунта-и-разрешений">1. Настройка разрешений и ключа учётной записи службы</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue#шаг-2-android-настройка-уведомлений-сервера-google-play">2. Настройка уведомлений сервера Google Play</Anchor>

   </Accordion>

2. Подготовьте следующую информацию:
   * Токен API V2 для использования в качестве ключа авторизации
   * Ставка комиссии магазина для применения (поддерживаемые значения: 1%–30%)
   * Идентификаторы ID приложения (приложений), к которым применяется пользовательская комиссия
3. Обратите внимание на следующие сведения о конфигурации:
   * Комиссия магазина настраивается **для каждого приложения**
   * Поддерживаются значения **1%–30%**
   * Эта конфигурация применяется **только к новым входящим событиям**
   * Если пользовательская комиссия не задана, AppsFlyer использует **логику комиссии магазина по умолчанию**

Полные структуры запросов и примеры см. в [документации Net Revenue API](https://dev.appsflyer.com/hc/reference/overview-7).

<div data-zendesk-anchors="h_01KEFDF4KD0DCMP5DGE7ZJDBGX=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 update-tax-rate-rules=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB-%D0%BD%D0%B0%D0%BB%D0%BE%D0%B3%D0%BE%D0%B2%D1%8B%D1%85-%D1%81%D1%82%D0%B0%D0%B2%D0%BE%D0%BA h_01KEFDF4KDJ5PVS3AW46BS57NC=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB-%D0%BD%D0%B0%D0%BB%D0%BE%D0%B3%D0%BE%D0%B2%D1%8B%D1%85-%D1%81%D1%82%D0%B0%D0%B2%D0%BE%D0%BA ios=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB-%D0%BD%D0%B0%D0%BB%D0%BE%D0%B3%D0%BE%D0%B2%D1%8B%D1%85-%D1%81%D1%82%D0%B0%D0%B2%D0%BE%D0%BA h_01KEFDRXY0FWKKK0DK6PS340TC=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB-%D0%BD%D0%B0%D0%BB%D0%BE%D0%B3%D0%BE%D0%B2%D1%8B%D1%85-%D1%81%D1%82%D0%B0%D0%B2%D0%BE%D0%BA h_01KEFDRXY0RTBH293JQXFWYAM2=android tax-rate-api-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B8-%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%B2-api h_01KEFDF4KD60SEVBQ8G228PEXD=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B8-%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%B2-api set-up-store-commission-rates=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D1%82%D0%B0%D0%B2%D0%BE%D0%BA-%D0%BA%D0%BE%D0%BC%D0%B8%D1%81%D1%81%D0%B8%D0%B8-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0 h_01KEFDF4KDP4PFKFQ0D9FN8P5D=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D1%82%D0%B0%D0%B2%D0%BE%D0%BA-%D0%BA%D0%BE%D0%BC%D0%B8%D1%81%D1%81%D0%B8%D0%B8-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0 update-store-commission-with-the-net-revenue-api=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BC%D0%B8%D1%81%D1%81%D0%B8%D0%B8-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-net-revenue-api h_01KEFDF4KDVTHTGKJ35CQ1GQ1E=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BC%D0%B8%D1%81%D1%81%D0%B8%D0%B8-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-net-revenue-api ios::f410adfc=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BC%D0%B8%D1%81%D1%81%D0%B8%D0%B8-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-net-revenue-api h_01KEFDWVDFBPP7NPSZV0PRGKPZ=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BC%D0%B8%D1%81%D1%81%D0%B8%D0%B8-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-net-revenue-api h_01KEFDWVDFZPHJP6EG0CPNG5A0=android::659c7976" />

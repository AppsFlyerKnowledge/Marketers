---
title: О выручке магазина ROI360
metadata:
  keywords:
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
  created_at: '2025-12-21T16:34:39Z'
  edited_at: '2026-11-03T01:44:54Z'
  id: 42138855425297
  locale: ru
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ru/articles/42138855425297
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор:** Используйте данные о доходе магазина ROI360 для валидации покупок в приложении и подписок, предотвращения дублирования и расчета чистой выручки.

> 🚧 **Важно!**
>
> Выручка магазина ROI360 доступна только клиентам премиум-плана ROI360. Чтобы проверить условия вашего тарифного плана или перейти на другой, обратитесь к своему менеджеру по работе с клиентами (CSM).

Доходы от магазинов приложений ROI360 — премиальное решение AppsFlyer для полного и точного измерения доходов от покупок и подписок внутри приложений. Он дает всесторонний обзор жизненного цикла клиента, позволяя точно измерять показатель окупаемости рекламных расходов (ROAS).

| Функция | Подробности |
| --- | --- |
| Область измерения выручки | <ul><li>Выручка от всех покупок внутри приложения (товаров и подписок), управляемых через App Store Connect (iOS) и Google Play Console (Android).</li><li>Возвраты</li><li>Доход от ожидаемых и отложенных транзакций (Android).</li><li>События, связанные с подпиской, которые происходят как внутри приложения, так и за его пределами</li><li>Чистый доход, включающий комиссионные магазинов и налоги</li></ul> |
| Проверка и точность данных о выручке | Решение предотвращает регистрацию дублирующихся транзакций. В iOS это также включает предотвращение дублирования, вызванного функцией «Семейный доступ». Выручка магазина ROI360 также может пересылать данные о транзакциях приложения Apple Store напрямую рекламодателям. |
| Источники данных | <ul><li>Коннектор SDK AppsFlyer для покупок на Android и iOS</li><li>Серверные уведомления App Store</li><li>Уведомления для разработчиков в режиме реального времени (RTDN) в Google Play</li></ul> |
| Отчетность и доступность данных | Данные о выручке доступны в дэшбордах и отчетах AppsFlyer и могут также передаваться партнерам через постбэки. |

> ❗️ **Предупреждение**
>
> При использовании выручки магазина ROI360 не отправляйте события покупок внутри приложения, иначе произойдет двойной учет выручки.

## Как работает система учета дохода в ROI360?

1. Пользователь совершает покупку внутри приложения или оформляет автообновляемую подписку.
2. Приложение делает транзакцию в магазине приложений.
3. Коннектор покупок SDK от AppsFlyer автоматически определяет совершаемые покупки и отправляет данные о них в AppsFlyer для валидации и регистрации.
4. AppsFlyer проверяет покупку в соответствующем магазине, чтобы убедиться, что она не является мошеннической.
   * После успешной валидации AppsFlyer регистрирует событие покупки или подписки в приложении.
   * Если валидация чека не удалась, событие отображается в отчете сырых данных о заблокированных событиях в приложении (доступен подписчикам Protect360) и на странице просмотра событий в реальном времени с параметром `af_validated`= false.
5. AppsFlyer передает ответ коннектору SDK, который в свою очередь передает ответ по валидации чека (пройдена или не пройдена) в приложение.
6. Все входящие уведомления сервера от магазинов приложений также обрабатываются в соответствии с бизнес-логикой AppsFlyer для доходов от покупки или подписки.
   * Уведомления о транзакциях, ранее зарегистрированных через коннектор SDK, проходят проверку и обработку, в результате чего в системе создается событие покупки или событие жизненного цикла.
   * Уведомления в отношении неизвестных транзакций игнорируются.
   * В iOS все уведомления сервера можно перенаправить на собственные серверы.

## Активируйте выручку магазина ROI360

Чтобы включить функцию измерения выручки магазина в ROI360, выполните следующие шаги:

1. В AppsFlyer в боковом меню откройте <Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.17%" /> **Настройки** и в разделе **ROI360** выберите **Настройки доходов**.
2. Откройте вкладку **Покупки и подписки**.
3. В разделе **«1. Выбрать тип продукта**» выберите **«ROI360**».
4. Нажмите **«Далее»,** чтобы продолжить.

## Настройка выручки магазина ROI360

См. статью <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue">«Настройте выручку магазина ROI360.</Anchor> »

## Справочная информация

В следующих разделах приводятся дополнительные сведения о ключевых аспектах измерения выручки от покупок в приложении (IAP) и подписок в ROI360. Сюда входят события и параметры покупок внутри приложения и подписок, чистый доход (Net revenue), позволяющий рассчитывать чистый доход на основе валового, а также общие характеристики и ограничения решения ROI360 для измерения доходов от покупок внутри приложения и подписок.

> 📘 **Примечание:**
>
> Чтобы отправить дополнительные пользовательские параметры с событиями в приложении, настройте **пользовательский источник данных** в <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-connector">коннекторе SDK покупки</Anchor>. Это позволяет обогащать события покупок и подписок собственной бизнес-логикой или метаданными.
> Эти параметры будут доступны в `custom_data` поле отчета по сырым данным.

<div id="iaprelated-events-and-parameters" />

<Accordion title="События и параметры, связанные с внутренними покупками (IAP)">

В следующих разделах отображаются события, связанные с внутренними покупками, которые измеряет AppsFlyer, и параметры, записанные для каждого события. Чтобы ознакомиться с описанием включённых параметров, см. [«Словарь параметров событий»](#parameter-dictionary).

**Все сгенерированные события обладают следующими свойствами:**

* События «сервер-сервер» (S2S).
* Доступны в отчетах по сырым данным (как органические, так и неорганические внутренние события в приложении) и также включены в отчеты ETL-хранилища выручки.
* Отправляется партнерам посредством постбэков.
* Поддержка в SKAN Conversion Studio.

<div id="purchase-af_purchase" />

<Accordion title="Покупка (af_purchase)">

**Описание**

Записывается при совершении покупки пользователем.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_дата\_отправления\_обратного
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-af_purchase_free" />

<Accordion title="Покупка бесплатная (af_purchase_free)">

**Описание**

Записывается, когда пользователь совершает покупку, не приносящую дохода. Все параметры дохода будут отображаться как 0.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_дата\_отправления\_обратного
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-canceled-af_purchase_canceled" />

<Accordion title="Покупка отменена (af_purchase_canceled)">

**Описание**

Записывается, если пользователь отменяет покупку.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="purchase-pending-af_purchase_pending" />

<Accordion title="Ожидаемая покупка (af_purchase_pending)">

**Описание**

Записывается, если пользователь делает покупку, но платеж еще не обработан.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="refund-af_purchase_refund" />

<Accordion title="Возврат (af_purchase_refund)">

**Описание**

Записывается в случае возврата средств за покупку.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* тип\_скидки\_af
* event\_revenue\_usd
* event\_revenue (включается в событие, если доход больше нуля)
* store\_commission
* af\_выручка
* af\_дата\_отправления\_обратного
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="test-purchase-af_purchase_sandbox_sdk" />

<Accordion title="Тестовая покупка (af_purchase_sandbox_sdk)">

**Описание**

Записывается при тестировании покупки, зарегистрированной посредством SDK в безопасной среде.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_purchase_sandbox_s2s" />

<Accordion title="Тестовая покупка (af_purchase_sandbox_s2s)">

**Описание**

Записывается при тестировании покупки, зарегистрированной посредством S2S в безопасной среде.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="subscriptionrelated-events-and-parameters" />

<Accordion title="События и параметры, связанные с подпиской">

В следующих разделах отображаются события, связанные с подпиской, которые измеряет AppsFlyer, и параметры, записанные для каждого события. Включенные параметры разъяснены в [словаре](#parameter-dictionary).

Все сгенерированные события:

* Считаются событиями S2S.
* Доступны в отчетах по сырым данным (как органические и неорганические внутренние события приложения).
* Могут быть отправлены партнёрам через постбэки.
* Могут быть использованы в SKAN Conversion Studio.

**Примечание:** В зависимости от платформы пользовательского устройства некоторые параметры не всегда заполняются для события в приложении.

<div id="trial-started-af_ars_trial_started" />

<Accordion title="Пробный период начался (af_ars_trial_started)">

**Описание**

Записывается, когда подписчик начинает пробный период.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода

</Accordion>

<div id="trial-canceled-af_ars_trial_canceled" />

<Accordion title="Пробный период отменен (af_ars_trial_canceled)">

**Описание**

Записывается, когда подписчик отменяет автоматическое продление подписки в течение пробного периода. Если пользователь не восстанавливает автопродление в течение пробного периода, наступает событие оттока.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода

</Accordion>

<div id="trial-churned-af_ars_trial_churned" />

<Accordion title="Отток после пробного периода (af_ars_trial_churned)">

**Описание**

Записывается, когда подписчик уходит после пробного периода. Это происходит после отмены автопродления и истечения пробного периода. Это также может быть следствием проблем с биллингом или технических проблем с продлением, что приводит к оттоку подписчиков.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_reason

</Accordion>

<div id="trial-converted-af_ars_trial_converted" />

<Accordion title="Конверсия после пробного периода (af_ars_trial_converted)">

**Описание**

Записано, когда пользователь оформляет подписку по полной цене после пробного периода.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_discount\_id
* тип\_скидки\_af
* event\_revenue\_usd
* store\_commission
* af\_revenue (включается в событие, если доход от события больше нуля)
* af\_дата\_отправления\_обратного
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-started-af_ars_subscription_started" />

<Accordion title="Подписка началась (af_ars_subscription_started)">

**Описание**

Записывается, когда начинается подписка со скидкой или по полной цене.

**Примечание**:

* Новые подписки могут быть записаны только через коннектор SDK.
* Для iOS: если подписчик повторно покупает подписку, которая у него уже есть, коннектор SDK сообщает приложению об успешной проверке чека, но не регистрирует новую транзакцию в AppsFlyer.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_discount\_id
* тип\_скидки\_af
* event\_revenue\_usd
* event\_revenue (включается в событие, если доход больше нуля)
* store\_commission
* af\_выручка
* af\_дата\_отправления\_обратного
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-canceled-af_ars_subscription_canceled" />

<Accordion title="Подписка отменена (af_ars_subscription_canceled)">

**Описание**

Записывается, когда подписка с автопродлением отменяется в середине расчетного периода. Если пользователь не восстанавливает автопродление в течение этого же расчетного периода, наступает событие оттока.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода

</Accordion>

<div id="subscription-paused-af_ars_subscription_paused-android-only" />

<Accordion title="Подписка приостановлена (af_ars_subscription_paused) – только для Android">

**Описание**

Записывается, когда пользователь приостанавливает активную подписку.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода

</Accordion>

<div id="subscription-resumed-af_ars_subscription_resumed" />

<Accordion title="Подписка продолжена (af_ars_subscription_resumed)">

**Описание**

Записывается, когда подписка по полной цене возобновляется после отмены или возврата подписки.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_discount\_id
* тип\_скидки\_af
* af\_reason
* event\_revenue (включается в событие, если доход от события больше нуля)
* store\_commission
* af\_выручка
* af\_дата\_отправления\_обратного
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-churned-af_ars_subscription_churned" />

<Accordion title="Отток после подписки (af_ars_subscription_churned)">

**Описание**

Записывается, когда подписчик уходит. Это происходит после отмены автопродления и истечения расчетного периода. Это также может быть следствием проблем с биллингом или технических проблем с продлением, что приводит к оттоку подписчиков.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_reason

</Accordion>

<div id="subscription-refunded-af_ars_subscription_refunded" />

<Accordion title="Возврат стоимости подписки (af_ars_subscription_refunded)">

**Описание**

Записывается, когда подписчик оформляет возврат стоимости подписки.

**Примечание:**

* Это событие обычно генерируется вместе с отрицательным значением. В случаях, когда невозможно определить, какие транзакции были возмещены, или сведения о возмещении не включены в уведомление, событие возврата не показывает значение.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_reason
* af\_subscription\_ownership\_type
* af\_discount\_id
* тип\_скидки\_af
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_refunded\_transaction\_ids
* event\_revenue\_usd
* event\_revenue (включается в событие, если доход больше нуля)
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_store
* af\_environment
* af\_тип\_периода
* store\_commission
* af\_выручка
* af\_дата\_отправления\_обратного
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-billing-grace-af_ars_subscription_billing_grace" />

<Accordion title="Льготный период подписки (af_ars_subscription_billing_grace)">

**Описание**

Записывается, когда продление подписки не происходит из-за проблемы с расчетом, и подписчик входит в льготный расчетный период.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода

</Accordion>

<div id="subscription-renewed-af_ars_subscription_renewed" />

<Accordion title="Подписка возобновлена (af_ars_subscription_renewed)">

**Описание**

Записывается, когда происходит автопродление подписки.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_discount\_id
* тип\_скидки\_af
* event\_revenue\_usd
* event\_revenue (включается в событие, если доход больше нуля)
* store\_commission
* af\_выручка
* af\_дата\_отправления\_обратного
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-changed-af_ars_subscription_xgraded" />

<Accordion title="Подписка изменена (af_ars_subscription_xgraded)">

**Описание**

Записывается, когда подписчик переходит на другой продукт или изменяет стоимость подписки.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_discount\_id
* тип\_скидки\_af
* event\_revenue\_usd
* event\_revenue (включается в событие, если доход больше нуля)
* store\_commission
* af\_выручка
* af\_дата\_отправления\_обратного
* af\_net\_revenue\_factors

</Accordion>

<div id="existing-subscriber-af_ars_existing_subscriber" />

<Accordion title="Имеющийся подписчик (af_ars_existing_subscriber)">

**Описание**

Записывается, когда коннектор SDK получает уведомление о подписчике в середине платежного цикла, прежде чем получить последующее уведомление сервера, которое переводит подписчика на другую соответствующую стадию жизненного цикла. Это событие обычно генерируется в период интеграции и настройки коннектора SDK.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* Страна
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_cuids
* af\_validated

</Accordion>

<div id="test-purchase-af_ars_sandbox_sdk" />

<Accordion title="Тестовая покупка (af_ars_sandbox_sdk)">

**Описание**

Записывается при тестировании покупки, зарегистрированной посредством SDK в безопасной среде.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* Страна
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_ars_sandbox_s2s" />

<Accordion title="Тестовая покупка (af_ars_sandbox_s2s)">

**Описание**

Записывается при тестировании покупки, зарегистрированной посредством S2S в безопасной среде.

**Параметры**

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* Страна
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* IDFA
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_тип\_периода
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="parameter-dictionary" />

<Accordion title="Словарь параметров">

Параметры для событий внутренней покупки и подписки отображаются в отчетах по сырым данным либо как собственные столбцы, либо как часть **значения события**.

Параметры с собственными столбцами:

* app\_id (идентификатор приложения)
* идентификатор\_пользователя\_клиента
* код\_страны
* af\_currency
* event\_revenue\_usd
* af\_выручка
* android\_id
* ip
* IDFA
* appsflyer\_id

Более подробная информация по данным параметрам приведена в <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary">словаре полей данных</Anchor>.

В таблице ниже описаны параметры сырых данных, доступные в событиях ARS и VIAP.

| Параметр | Примечания | Продукт |
| --- | --- | --- |
| af\_cancelation\_date\_ms | Дата отмены | IAP |
| af\_cuids | <ul><li>В контексте ARS этот параметр содержит массив со всеми CUID-ами.</li><li>Массив CUID отображается независимо от идентификаторов устройства. Таким образом, одни и те же CUID могут отображаться для нескольких идентификаторов устройств.</li></ul> | Подписка |
| af\_discount\_id | Идентификатор предложения, представленный пользователю во время первой покупки. Идентификатор заполняется только при наличии кода скидки. | <ul><li>IAP</li><li>Подписка</li></ul> |
| тип\_скидки\_af | Тип скидки, который использовал пользователь. Возможные значения:<ul><li>iOS<ul><li>Фактическое значение идентификатора клика из целевого URL, используемое для отправки сигналов и для разрешения полной иерархии кампании через API партнеров.</li><li>promotional</li><li>offer\_codes</li><li>win\_back</li></ul></li><li>Android;<ul><li>Для CTV это поле заполняется custom\_device\_id (идентификатор устройства, управляемый рекламодателем).</li><li>one\_time\_code</li><li>vanity\_code (уникальный код)</li></ul></li></ul> | Подписка |
| af\_environment | Время касания контрибьютора | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_expires\_date\_ms | Дата истечения текущего расчетного периода подписки. | Подписка |
| af\_дата\_отправления\_обратного | Чистая выручка рассчитывается на основе всех учтенных факторов. См. af\_net\_revenue\_factors. | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_net\_revenue\_country | <ul><li><Anchor target="_blank" href="https://www.nationsonline.org/oneworld/country_code_list.htm">Двухбуквенный код страны по ISO</Anchor>, в отношении которой применяется налог.</li><li>Пример: CA</li><li>Примечание: Для Великобритании используется код «UK», а не «GB».</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_net\_revenue\_factors | <ul><li>Массив, представляющий все факторы, которые приводят к указанной сумме af\_net\_revenue.</li><li>Пример значения: store\_commission</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_net\_revenue\_postal\_code | <ul><li>Строка из букв и/или цифр</li><li>Пример: L4J8E3</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_net\_revenue\_subdivision | <ul><li>В некоторых странах может быть дополнительно указан штат/муниципальное образование. Обрабатывается в соответствии с кодами подразделений <Anchor target="_blank" href="https://service.unece.org/trade/locode/2023-1%20SubdivisionCodes.htm">ISO 3166-2</Anchor>.</li><li>Включает код страны и код подразделения.</li><li>Пример: US-CA</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_net\_revenue\_tax\_exclusive | <ul><li>Логический параметр: true (истина) или false (ложь).</li><li>False означает, что налог включен в общую выручку.</li><li>True означает, что налог взимается дополнительно к общей заявленной выручке.</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_net\_revenue\_tax\_name | <ul><li>Название, указанное в счете-фактуре клиента, описывающее конкретный тип налога.</li><li>Пример: Налог с продаж, НДС, федеральный налог на товары и услуги</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_net\_revenue\_tax\_rate | <ul><li>Число с точностью до 4 знаков после запятой, представляющее процент собранного налога.</li><li>Пример: 7.25</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_offer\_id | <ul><li>Идентификатор предложения, применяемый к транзакции, когда это релевантно, (например, скидки или рекламные предложения).</li><li>Только для Android</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_order\_id | <ul><li>Идентификатор заказа для транзакции</li><li>Только для Android</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_original\_transaction\_id | <ul><li>Идентификатор исходной транзакции</li><li>Только для iOS</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_original\_transaction\_id | <ul><li>Оригинальный идентификатор транзакции</li><li>Только для iOS</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_тип\_периода | <ul><li>Тип подписки или пробного периода.</li><li>Возможные значения:<ul><li>Пробный период</li><li>Ознакомительная</li><li>Обычная</li></ul></li></ul> | Подписка |
| af\_product\_id | Идентификатор продукта подписки | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_purchase\_date\_ms | Дата покупки для указанного идентификатора продукта в внутреннее событие приложения. | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_purchase\_option\_id | <ul><li>ID варианта покупки, связанный с транзакцией.</li><li>Только для Android</li></ul> | IAP |
| af\_purchase\_option\_type | Тип варианта покупки для данной транзакции. Возможные значения (Android):<ul><li>купить</li><li>аренда</li></ul> | IAP |
| af\_purchase\_state | Возможные значения:<ul><li>Сумма выручки от события в долларах США.</li><li>Значение представляет источник атрибутивной веб-рекламы.</li><li>Указывает тип рекламного идентификатора, предоставленного в поле [advertising\_id\_value](#attribution::be9cb893) Общие типы включают IDFA (iOS) и GAID (Android).</li></ul> | IAP |
| af\_purchase\_token | <ul><li>Токен покупки для транзакции</li><li>Только для Android</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_reason | [содержание не изменилось] | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_refunded\_transaction\_ids | <ul><li>Массив всех идентификаторов транзакций возврата средств</li><li>Только для iOS</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_store | Магазин приложений, из которого был приобретен продукт подписки. | <ul><li>IAP</li><li>Подписка</li></ul> |
| af\_subscription\_ownership\_type | FAMILY\_SHARED означает, что пользователь подключён через семейный доступ. PURCHASED означает, что платящий пользователь совершил покупку. | Подписка |
| af\_transaction\_id | <ul><li>Идентификатор транзакции</li><li>Только для iOS</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |
| store\_commission | <ul><li>Рассчитанный процент комиссии, который магазин получает от купленного продукта.</li><li>Отображается в виде десятичного числа.</li><li>Пример: 30</li></ul> | <ul><li>IAP</li><li>Подписка</li></ul> |

</Accordion>

<div id="true-revenue" />

<Accordion title="Чистый доход">

Чистая выручка — это слой бизнес-логики, созданный для решения ROI360 по выручке магазина. Он автоматически рассчитывает стоимость чистого дохода для каждой входящей транзакции в режиме реального времени и включает ее в отчеты.

> 📘 **Примечание**
>
> Чистая выручка отображается в отчетах о сырых данных и может передаваться в реальном времени посредством постбэков внутренних событий приложения. Также эти показатели доступны в <Anchor target="_blank" href="/marketers/ru/docs/my-dashboards">разделе «Мои дэшборды»</Anchor> в виде нетто-метрик (чистая выручка, чистый ROI, чистый ROAS, чистый ARPU, чистая валовая прибыль).
>
> Чтобы отправлять чистый доход в постбэках, настройте событие в приложении, выбрав параметр **«Значения, доход & чистый доход»**. Подробности см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#данные-для-включения-в-постбэки">«Настройка постбэка данных о внутренних событиях приложения</Anchor>».

> 📘 **Совет**
>
> Вы также можете настроить постбэки событий в приложении так, чтобы в стандартном параметре дохода (monetary) отправлялся чистый доход вместо валового. Чтобы получить доступ к этой настройке, обратитесь к вашему менеджеру по работе с клиентами (CSM).

Истинный доход учитывает следующие факторы при расчете валового и чистого дохода:

* **Комиссия магазина**:
  * Рассчитывается и отображается автоматически. От вас не требуется никаких действий.
  * В случае покупок (IAP) стандартная комиссия магазина зависит от конкретного магазина:
    * Магазин приложений — Япония и страны ЕС: 26%. Материковый Китай (CN): 25%. Остальные страны мира: 30%:
    * Play Store: 30%:
  * Для подписок комиссия автоматически рассчитывается для каждого подписчика, исходя из срока его подписки.
    * Магазин приложений — первые 12 месяцев: 26% в Японии и странах ЕС, 25% в материковом Китае (CN), 30% в остальных странах мира. С 13-го месяца: 15% в Японии, 12% в материковом Китае (CN), 15% в остальных странах мира.
    * Play Store: 15% с первого дня.
  * Соответствующие параметры чистого дохода доступны в отчетах по сырым данным.
  * Используйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">API чистой выручки,</Anchor> чтобы установить ставку комиссии магазина, отличную от значения по умолчанию. Это можно использовать, например, если ваше приложение участвует в программе Apple Small Business Program, в рамках которой комиссия составляет 15% (12% на территории материкового Китая (CN)).
* **Налог**:
  * По умолчанию налог указывается в отчете по любой транзакции, измеряемой ROI360, с использованием конфигурации налоговых ставок по умолчанию.
  * Это относится к странам, в которых налог включен в цену (где налог входит в цену по прейскуранту). Так, например, в Великобритании AppsFlyer вычитает сумму налога и комиссии магазина. В странах с ценами без учёта налога, например в США, параметры выручки и чистой выручки по умолчанию не включают налог.
  * Настройки можно изменить, используя <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">API чистой выручки</Anchor>. Чтобы узнать, какие страны поддерживаются и каковы их налоговые ставки по умолчанию, см. <Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">этот файл JSON</Anchor>. Разработчик может редактировать его или использовать в API без изменений.

При просмотре чистого дохода в отчетах следующие параметры содержат данные о чистом доходе. Более подробную информацию см. в [словаре параметров](#parameter-dictionary).

| Параметр | Фактор чистого дохода |
| --- | --- |
| `store_commission` | Комиссия магазина |
| `af_net_revenue_tax_name` | Налог |
| `af_net_revenue_tax_rate` | Налог |
| `af_net_revenue_tax_exclusive` | Налог |
| `af_net_revenue_postal_code` | Налог |
| `af_net_revenue_country` | Налог |
| `af_net_revenue_subdivision` | Налог |
| `af_дата_отправления_обратного` | <ul><li>Комиссия магазина</li><li>Налог</li></ul> |
| `af_net_revenue_factors` | <ul><li>Комиссия магазина</li><li>Налог</li></ul> |

</Accordion>

<div id="troubleshooting-and-disprepancies" />

<Accordion title="Устранение неполадок и несоответствий">

| Признак | Объяснение / Решение |
| --- | --- |
| AppsFlyer отображает меньшее количество событий покупок и подписок в приложении, чем фактически указано в магазинах приложений. | В AppsFlyer события создаются только для пользователей, которые обновили приложение до версии с коннектором SDK. А магазины приложений регистрируют каждое событие, независимо от версии приложения пользователя. В результате, пока обновленная версия приложения не будет полностью внедрена, ожидается расхождение между данными о доходе приложения и данными магазина. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Характеристики и ограничения">

| Спецификация | Продукт | Примечания |
| --- | --- | --- |
| Подписка с оплатой в рассрочку (Android) | Доход от подписки | Не поддерживается |
| Ожидание подписки  <br />транзакции (Android) | Доход от подписки | Не поддерживается |
| Новые подписки | Доход от подписки | Записывается только через SDK AppsFlyer для измерения доходов от покупок |
| Изменение цен | Доход от подписки | Если доход от подписки не получает созданное SDK уведомление о новой цене продукта, он продолжает указывать в качестве дохода предыдущую цену продукта. Как только новая цена продукта поступает из SDK покупки, она записывается. |
| Валовой доход | <ul><li>IAP</li><li>Доход от подписки</li></ul> | Поддерживается |
| Чистая выручка | <ul><li>IAP</li><li>Доход от подписки</li></ul> | Поддерживается в сырых данных и в «My Dashboards» (как метрики Net) |
| Возвраты | IAP | Возможен запрос в течение 180 дней после исходной покупки. |
| Устранение дубликатов | <ul><li>IAP</li><li>Доход от подписки</li></ul> | Поддерживается для транзакций, зарегистрированных в течение 180 дней после даты события. |
| Строгий режим SDK | <ul><li>IAP</li><li>Доход от подписки</li></ul> | Подписки ROI360 и покупки в приложении (IAP) поддерживаются в строгом режиме SDK через:<ul><li>Коннектор SDK для измерения доходов от покупок от AppsFlyer для iOS версии 6.13.0</li><li>Коннектор SDK для измерения доходов от покупок от Unity версии V2.0.1</li></ul> |
| Валюта | <ul><li>IAP</li><li>Доход от подписки</li></ul> | Доход отражается в исходной валюте (с помощью параметра event\_revenue) и в долларах США (с помощью параметра event\_revenue\_usd). |
| Обновление данных | <ul><li>IAP</li><li>Доход от подписки</li></ul> | <ul><li>Отчет о доходах магазина на уровне транзакций: Каждый час</li><li>Отчет о доходах магазина на уровне устройства: Каждые 8 часов</li></ul> |
| StoreKit 2 | <ul><li>IAP</li><li>Доход от подписки</li></ul> | <ul><li>Поддержка StoreKit 2 доступна, начиная с Purchase SDK Connector версии 6.16.2.</li><li>Убедитесь, что ваше приложение использует обновленные учетные данные App Store, как описано <Anchor target="_blank" href="/marketers/ru/docs/bulletin-update-app-store-credentials-for-ios-roi360-receipt-validation">здесь</Anchor>.</li></ul> |
| Разовые продукты Google | IAP | <ul><li>Поддерживаемые варианты покупок: Купить и арендовать</li><li>Предзаказ: не поддерживается</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01KSAJW61CZZBWBQ112VR5095C=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01KD0W3J6105033NV6FYKGQ8BQ=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 how-does-roi360-store-revenue-work=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B0-%D1%83%D1%87%D0%B5%D1%82%D0%B0-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0-%D0%B2-roi360 h_01KD2JZQ0JYVF8S1E2W3N91KYV=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%B0-%D1%83%D1%87%D0%B5%D1%82%D0%B0-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0-%D0%B2-roi360 enable-roi360-store-revenue=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D1%83%D0%B9%D1%82%D0%B5-%D0%B2%D1%8B%D1%80%D1%83%D1%87%D0%BA%D1%83-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0-roi360 h_01KD2JZQ0JS9YQ2SPNN6NHAJEH=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D1%83%D0%B9%D1%82%D0%B5-%D0%B2%D1%8B%D1%80%D1%83%D1%87%D0%BA%D1%83-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0-roi360 set-up-roi360-store-revenue=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B2%D1%8B%D1%80%D1%83%D1%87%D0%BA%D0%B8-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0-roi360 h_01KD2JZQ0JD53598CES8ECAHR3=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B2%D1%8B%D1%80%D1%83%D1%87%D0%BA%D0%B8-%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0-roi360 reference=%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D1%87%D0%BD%D0%B0%D1%8F-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F h_01JKWGTJQY938NV6VCJ7KKS23E=%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D1%87%D0%BD%D0%B0%D1%8F-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F h_01KD6B3KC75RFDV08G9RT1BX1M=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HDEPSK8DFQ24EZ5T0EPBSVS4=iaprelated-events-and-parameters 01H8VJJP1ER9N6BPAES8H8CK4T=purchase-af_purchase h_01J50N58GYF2BYC57HA7THSWW6=purchase-af_purchase_free 01H8VJJP1EXYE1EQS08CK8BG02=purchase-canceled-af_purchase_canceled 01H8VJJP1ET5TAAQ17EMK6TVRE=purchase-pending-af_purchase_pending 01H8VJJP1E8JKPGT2V9CCB1XW8=refund-af_purchase_refund 01H8VJJP1ECQMS49M8Z1X1FT4B=test-purchase-af_purchase_sandbox_sdk 01H8VJJP1E3X7YZNYT5D8REVEW=test-purchase-af_purchase_sandbox_s2s h_01HDEQBACTTPZ04YYD1KV49SEZ=subscriptionrelated-events-and-parameters 01H8VJJP1EHAZBGT82WRWB00JT=trial-started-af_ars_trial_started 01H8VJJP1ETCHTK6JMK9ERS5A5=trial-canceled-af_ars_trial_canceled 01H8VJJP1EC45X8PJVPWT3G7S3=trial-churned-af_ars_trial_churned 01H8VJJP1EYPQM50JVX1KPZXAZ=trial-converted-af_ars_trial_converted 01H8VJJP1EA4WTCEJWBB1HPRJF=subscription-started-af_ars_subscription_started 01H8VJJP1EF744NE425Y30VG0M=subscription-canceled-af_ars_subscription_canceled 01H8VJJP1EMKBP27070NRR9CZ5=subscription-paused-af_ars_subscription_paused-android-only 01H8VJJP1EGHNQ35JM1TWV4ND0=subscription-resumed-af_ars_subscription_resumed 01H8VJJP1EM2GJ28VBE6V76SBG=subscription-churned-af_ars_subscription_churned 01H8VJJP1E28XXAQSGZ9PYDT08=subscription-refunded-af_ars_subscription_refunded 01H8VJJP1E399B2AVWP9VKZ0D4=subscription-billing-grace-af_ars_subscription_billing_grace 01H8VJJP1EEZZ0DE75VXAZQP3E=subscription-renewed-af_ars_subscription_renewed 01H8VJJP1FGXHRK3J0XB2G4PCQ=subscription-changed-af_ars_subscription_xgraded 01H8VJJP1FKC8KZ2HKJVGZEV23=existing-subscriber-af_ars_existing_subscriber 01H8VJJP1F720QT97Q0TW4SEM2=test-purchase-af_ars_sandbox_sdk 01H8VJJP1FSRHG26EXMEG3325P=test-purchase-af_ars_sandbox_s2s 01H8VJJP1F0ZV2PX39D9JCG6B4=parameter-dictionary 01H8VJJP1FF219YN3XHRCGW7Z3=true-revenue h_01KBFWTM4XJ417930YVDD36ASK=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01KRKEP613DR8RZ5Q2A5H7KZAH=%D1%81%D0%BE%D0%B2%D0%B5%D1%82 01JHZG8FFHTYE2PMRWWS8WNR6X=troubleshooting-and-disprepancies 01H8VJJP1FP2MPRF8AN77REXD0=traits-and-limitations" />

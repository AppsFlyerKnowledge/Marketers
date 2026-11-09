---
title: Сопоставление с внутренними событиями Meta Ads
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2026-09-12T00:28:34Z'
  id: 4410480904081
  locale: ru
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ru/articles/4410480904081
---
> **Краткий обзор.** Отправляйте насыщенные внутренние события из AppsFlyer в Meta Ads.

<div id="meta-in-app-events-mapping" />

## Сопоставление с внутренними событиями Meta Ads

Рекламодатели могут сопоставить внутренние события своих приложений, события SDK и межсерверные события с предопределенными событиями Meta. Кроме того, рекламодатели могут отправлять в Meta постбэки о каждом <Anchor target="_blank" href="/marketers/ru/docs/measure-sessions">запуске приложения</Anchor> или о каждом известном <Anchor target="_blank" href="/marketers/ru/docs/measure-uninstalls#сопоставление-события-удаления">удалении приложения</Anchor>.

Это позволяет рекламодателям использовать дополнительные возможности оптимизации, предоставляемые Meta, а также выполнять пользовательскую сегментацию аудитории и выделять похожие аудитории.

<div id="predefined-event-mapping" />

### Сопоставление предопределенных событий

Meta Ads предлагает <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names">широкий спектр событий</Anchor>, которые определены заранее и могут сопоставляться.

<Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure">Здесь</Anchor> представлен список **насыщенных внутренних событий**, которые можно отправить в Meta с дополнительными параметрами, содержащими **информацию о качестве событий**.

Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#inapp-event-mapping">сопоставлении событий в Meta</Anchor>.

<Image align="center" alt="In-app_event_postbacks_en-us.png" src="https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png" />

Обратите внимание, что для отправки удалений в Meta Ads нет предопределенного события. Для отправки удалений используйте [настраиваемое событие](/docs/meta-ads-in-app-event-mapping#сопоставление-настраиваемых-внутренних-событий-приложения).

Ниже приведен список других предопределенных событий Meta, у которых нет дополнительных параметров:

| Идентификатор события в Meta | Описание | Рекомендованное имя AppsFlyer SDK |
| --- | --- | --- |
| Donate | Перечисление средств для вашей организации или акции. | af\_donate |
| График | Бронирование посещения одного из ваших местоположений. | af\_schedule |
| SubmitApplication | Подача заявки на предлагаемые вами продукт, услугу или программу, например, на банковскую карту, образовательную программу или работу. | af\_submit\_application |
| FindLocation | Когда человек находит ваше местоположение через веб-сайт или приложение и намеревается вас посетить. Например, поиск продукта и его обнаружение в одном из ваших местных магазинов. | af\_find\_location |
| Contact | Телефонный разговор, смс, электронное письмо, чат или иная форма контакта между клиентом и вашей компанией. | af\_contact |
| CustomizeProduct | Персонализация продуктов с помощью конфигуратора или иного приложения, которым владеет ваша компания. | af\_customize\_product |
| `Adimpression` — для Android  <br />`Fb_mobile_purchase` — для iOS | Оптимизирует доход от рекламы на платформе Meta. [См. подробности ниже](#сопоставление-данных-о-доходах-от-рекламы-для-оптимизации-кампании). | af\_ad\_revenue |

<div id="mapping-ad-revenue-data-for-campaign-optimization" />

### Сопоставление данных о доходах от рекламы для оптимизации кампании

Meta может оптимизировать ваши кампании на основе данных о доходе от рекламы. Для этого событие af\_ad\_revenue сопоставляется со следующим событием рекламы Meta:

<table><colgroup><col/><col/><col/><col/></colgroup><thead><tr><th><strong>Название события в AppsFlyer</strong></th><th><strong>Окно повторного вовлечения</strong> </th><th><strong>Связано с партнёрским событием</strong></th><th><strong>Оптимизация рекламы Meta на основе:</strong></th></tr></thead><tbody><tr><td rowspan="2"> <br/>af_ad_revenue</td><td>Android;</td><td>Adimpression</td><td>Конкретный доход от рекламы</td></tr><tr><td>https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png</td><td>fb_mobile_purchase</td><td>Покупок в приложении</td></tr></tbody></table>

<div id="availability-limitations" />

#### Ограничения доступности

* На данный момент оптимизация через событие **Adimpression** доступна только для:
  * Приложения для Android. iOS-приложения могут продолжать отправлять данные о доходе от рекламы, используя событие *fb\_mobile\_purchase*.
  * Отдельные рекламные аккаунты Meta, соответствующие критериям Meta. Отображение серым цветом может означать, что [критерии соответствия требованиям не соблюдены](https://ru-ru.facebook.com/business/help/571188993373447?id=561906377587030).
* Событие *af\_ad\_revenue* доступно только для тарифов с <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-cost-and-revenue-data">расширенной подпиской ROI360</Anchor>. Кроме того, вам нужен <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">тип интеграции дохода от рекламы через SDK на уровне показов</Anchor>.
  * Тарифы, не включающие в себя ROI360, могут отправлять данные о доходах от рекламы, используя другие названия событий.

<div id="custom-in-app-events-mapping" />

### Сопоставление настраиваемых внутренних событий приложения

В AppsFlyer есть возможность сопоставить любое настраиваемое внутреннее событие приложения для отправки в Meta, используя идентификатор CUSTOM Meta Event Identifier.

Имена и значения событий (в том числе параметры событий), заданные в SDK, передаются в Meta в исходном виде и отображаются с исходным именем события из SDK AppsFlyer, а не как «custom».

Обратите внимание, что <Anchor target="_blank" href="https://www.facebook.com/business/help/2308889442692949?id=1716638325041491">эти события можно использовать для оптимизации кампаний.</Anchor>

<Image align="center" alt="" src="https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png" />

<div id="automatic-parameter-mapping-with-the-custom-event" />

### Автоматическое сопоставление параметров с событием CUSTOM

Благодаря глубокой интеграции AppsFlyer и Meta многие стандартные параметры событий SDK AppsFlyer автоматически сопоставляются с предопределенными параметрами Meta. Например, параметр **af\_revenue** преобразуется в Meta в параметр **\_valueToSum**, который позволяет отправлять доход по каждому событию, и который можно измерить и оптимизировать в Meta.

<div id="note" />

> 📘 **Примечание**
>
> При автоматическом сопоставлении параметров для событий типа CUSTOM результаты могут отличаться от результатов сопоставления с предопределенными событиями.
>
> В некоторых <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-event-structure">предопределенных событиях</Anchor> параметр **af\_price** сопоставлен параметру **\_valueToSum** (например, в событии `fb_mobile_add_to_cart`). В других событиях параметру **af\_revenue** сопоставлен параметр **\_valueToSum** (например, в событии `fb_mobile_purchase`).
>
> При сопоставлении параметров событию типа CUSTOM параметр **af\_price** всегда сопоставлен параметру **fb\_price**, а параметр **af\_revenue** — параметру **\_valueToSum**.

В этой таблице приведены все параметры событий AppsFlyer, которые при сопоставлении с событием CUSTOM в Meta автоматически сопоставляются с параметрами Meta.

| Параметр AppsFlyer | Параметр Meta |
| --- | --- |
| af\_city | fb\_city |
| af\_класс | fb\_travel\_class |
| af\_content | fb\_content |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_content\_type | fb\_content\_type |
| af\_country | fb\_country |
| af\_currency | fb\_currency |
| af\_date\_a | fb\_checkin\_date |
| af\_date\_b | fb\_checkout\_date |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_description | fb\_description |
| af\_destination\_a | fb\_origin\_airport |
| af\_destination\_b | fb\_destination\_airport |
| af\_destination\_list | fb\_destination\_ids |
| af\_hotel\_score | fb\_hotel\_score |
| af\_уровень | fb\_level |
| af\_max\_rating\_value | fb\_max\_rating\_value |
| af\_num\_adults | fb\_num\_adults |
| af\_num\_children | fb\_num\_children |
| af\_num\_infants | fb\_num\_infants |
| af\_order\_id | fb\_order\_id |
| af\_платежная\_информация\_доступна | fb\_payment\_info\_available |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops |
| af\_preferred\_price\_range | fb\_preferred\_price\_range |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings |
| af\_price | fb\_price |
| af\_quantity | fb\_num\_items |
| af\_region | fb\_region |
| af\_метод\_регистрации | fb\_метод\_регистрации |
| af\_дата\_возвращения | fb\_returning\_arrival\_date |
| af\_дата\_отправления\_обратного | fb\_returning\_departure\_date |
| af\_выручка | \_valueToSum |
| строка\_поиска\_af | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | fb\_suggested\_destinations |
| af\_suggested\_hotels | fb\_предлагаемые\_отели |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |

<div id="predefined-events-automatic-mapping-to-the-_valuetosum-parameter" />

#### Автоматическое сопоставление предопределенных событий с параметром `_valueToSum`

Для предопределенных событий параметр Meta `_valueToSum` сопоставляется либо с параметром `af_price`, либо с параметром `af_revenue`.

В следующей таблице показано это сопоставление для всех предопределенных событий Meta с параметром `_valueToSum`:

| **Точка (.)** | **\_valueToSum сопоставляется с** |
| --- | --- |
| fb\_mobile\_level\_achieved | none |
| fb\_mobile\_add\_payment\_info | none |
| fb\_mobile\_add\_to\_cart | af\_price |
| fb\_mobile\_add\_to\_wishlist | af\_price |
| fb\_mobile\_complete\_registration | none |
| fb\_mobile\_tutorial\_completion | none |
| fb\_mobile\_initiated\_checkout | af\_price |
| fb\_mobile\_purchase | af\_выручка |
| fb\_mobile\_rate | af\_rating\_value |
| fb\_mobile\_search | af\_выручка |
| fb\_mobile\_spent\_credits | af\_price |
| fb\_mobile\_achievement\_unlocked | none |
| fb\_mobile\_content\_view | af\_price |
| StartTrial | af\_price |
| Подписаться | af\_выручка |

<div id="send-complex-in-app-events-to-meta-ads" />

### Сопоставление с внутренними событиями Meta Ads

По состоянию на сентябрь 2026 года мы рекомендуем использовать новый объект `af_order_info` для отправки сложных событий в приложении — событий с несколькими товарами — в Meta Ads. Этот объект позволяет рекламодателям передавать сложные события в приложении с несколькими товарами в несколько поддерживаемых сетей. Подробнее см. в статье <Anchor target="_blank" href="/marketers/ru/docs/item-level-order-data-for-ad-networks-af-order-info">Данные заказа на уровне товара для рекламных сетей (af\_order\_info)</Anchor>.

При использовании `af_order_info` AppsFlyer отправляет информацию о товарах в Meta в поле события `fb_contents`, которое поддерживает SKU, количество и доход по каждому товару.

В качестве альтернативы вы по-прежнему можете использовать структурированный массив `af_content`. Каждый объект в массиве должен включать `id` и `quantity`, чтобы обеспечить корректную обработку постбэка.

`af_content_list` является необязательным. Если он отсутствует, Meta использует поле `fb_content` (сопоставленное из `af_content`) для определения идентификаторов ID продуктов. Пока JSON `af_content` содержит поле `id` в каждом объекте, Meta может распознавать и извлекать из него идентификаторы контента.

Если вы включаете `af_content_list`, не включайте `af_content_id` в то же событие. Оба параметра сопоставляются с `fb_content_id`, и во избежание конфликтов следует заполнять только один из них.

<div id="note-1" />

> 📘 **Примечание**
>
> `fb_content_id` важен для сценариев использования на уровне продукта, таких как сопоставление событий с элементами каталога для Advantage+ Catalog Ads и Dynamic Ads, отчетность по эффективности на уровне продукта и сигналы оптимизации на основе продукта. Для общей оптимизации конверсии на основе количества событий и значения кампании работают и без него.

<div id="example-unified-format-compatible-with-meta-and-tiktok" />

> 📄 **Пример: единый формат, совместимый с Meta и TikTok**
>
> ```json
> {
>   "af_revenue": 4.99,
>   "af_currency": "USD",
>   "af_order_id": "12345",
>   "af_content": "[{\"id\":\"ID1\",\"quantity\":\"1\"},{\"id\":\"ID2\",\"quantity\":\"1\"},{\"id\":\"ID3\",\"quantity\":\"2\"}]"
> }
> ```

Этот формат работает и для Meta, и для TikTok. TikTok также считывает значения `id` из поля `af_content`, поэтому одного payload достаточно при отправке постбэков в обе сети.

<div id="important" />

> 🚧 **Важно!**
>
> Если параметр `af_content` превышает 1,000 символов, AppsFlyer может отправить событие в Meta без параметра `fb_content`. Если в этом сценарии также отсутствует `af_content_list`, Meta не получает никаких данных для идентификации продукта. Держите `af_content` в пределах 1000 символов для событий, которые включают множество элементов.

Подробнее о структурировании сложных событий в приложении см. в статье <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#what-are-complex-inapp-events-and-how-do-i-set-them-up">События в приложении: обзор</Anchor>.

<div id="event-and-parameter-limitations" />

## Ограничения для событий и параметров

Действуют следующие лимиты по [отправке событий в Meta Ads](https://developers.facebook.com/docs/app-events/faq#limits):

* Недопустимые символы:
  * Двоеточие (:)
  * Точка (.)
  * Нелатинские (неанглийские) символы: по состоянию на 12 января 2020 Meta не принимает китайские символы. AppsFlyer не проверял другие алфавиты, поэтому их стоит использовать только после верификации, поддерживает ли Meta эти символы в постбэках.
* Названия событий чувствительны к регистру. Чтобы избежать расхождений, убедитесь, что вы используете правильный регистр в названиях событий для всех медиа-источников и версий приложений.
* Максимальное количество параметров: 25.
* Длина имен и параметров событий: 2–40 символов.
* Максимальная длина параметра: 100 символов.
* Максимальная длина параметра af\_content: 1000 символов.
* Разрешенные символы: буквы, цифры, символ подчеркивания, дефис, пробел. Используйте только латинские (английские) буквы. Использование нелатинских символов приводит к расхождениям в результатах.

Рекомендации по именованию внутренних событий приложения:

* Имена событий в AppsFlyer могут совпадать с именами событий Meta (например, fb\_price), однако такие события нельзя отправлять в Meta как настраиваемые события (CUSTOM).  
  **Для надежности не следует использовать имена событий, которые совпадают с именами событий Meta.**
* Чтобы сопоставить внутренние события приложения с Meta с помощью постбэков, получите данные о событиях от ВСЕХ источников, включая органические.

<div id="important-1" />

> 🚧 **Двоеточие (:)**
>
> За исключением перечисленных выше параметров, AppsFlyer отправляет в Meta данные настраиваемых событий **в исходном виде**. Владелец приложения несет ответственность за проверку соответствия данных о событиях требованиям Meta, используя действительные параметры Meta (см. таблицу выше). В противном случае эти параметры не будут отправлены в Meta.

<div data-zendesk-anchors="facebook-iae-mapping=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC%D0%B8-meta-ads h_01J1WCP44CHN0Q73P6DN7H8FKG=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC%D0%B8-meta-ads predefined-event-mapping=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01J1WCP44D18WMXCMHJ0FNF6Y0=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 mapping-ad-revenue-data-for-campaign-optimization=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%BE%D0%BF%D1%82%D0%B8%D0%BC%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 01JAPZ6M11HSCE9QNN5NSD61FK=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%BE%D0%BF%D1%82%D0%B8%D0%BC%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 availability-limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D0%B8 01JAQ1ECZVR8SZ81KE6CDD08A2=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D0%B8 custom-inapp-events-mapping=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%B0%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D1%85-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01J1WCP44DK14AC5ZG4KTFFFSC=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%B0%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D1%85-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F automatic-parameter-mapping-with-the-custom-event=%D0%B0%D0%B2%D1%82%D0%BE%D0%BC%D0%B0%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-%D1%81-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B5%D0%BC-custom h_01J1WCP44D645TS6JFGM2BDGM9=%D0%B0%D0%B2%D1%82%D0%BE%D0%BC%D0%B0%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-%D1%81-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B5%D0%BC-custom h_01J1WCP44DSZ7G3603W5EBWZEW=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 value-to-sum=%D0%B0%D0%B2%D1%82%D0%BE%D0%BC%D0%B0%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D1%81-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%BC-_valuetosum 01JATBG1SZRRZ0PCANKQ6S8CX4=%D0%B0%D0%B2%D1%82%D0%BE%D0%BC%D0%B0%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D1%81-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%BC-_valuetosum send-complex-in-app-events-to-meta-ads=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC%D0%B8-meta-ads-1 h_01K1QR0NWMT1WCFWXF2GK9YZYF=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC%D0%B8-meta-ads-1 h_01KSMX6DZHA1HNQ2WGECZPEQGJ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01KSMX6DZHF0P97RTJHS065KB1=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%B5%D0%B4%D0%B8%D0%BD%D1%8B%D0%B9-%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82-%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B8%D0%BC%D1%8B%D0%B9-%D1%81-meta-%D0%B8-tiktok h_01KSMX6DZHWXYRJP5QK5BB730P=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE event-and-parameter-limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B8-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2 h_01J1WCP44DF2QMV10VXF8NQZ7W=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B8-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2 h_01J1WCP44D9SNEYZG59KNM822K=%D0%B4%D0%B2%D0%BE%D0%B5%D1%82%D0%BE%D1%87%D0%B8%D0%B5-" />

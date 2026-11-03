---
title: Интеграция с Google Analytics — расхождения
metadata:
  keywords:
    - Analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-12-07T13:38:17Z'
  edited_at: '2026-08-28T00:12:01Z'
  id: 4413026674833
  locale: ru
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/ru/articles/4413026674833
---
> **Кратко:** Узнайте, какие расхождения могут возникать между AppsFlyer и Google Analytics.

## Расхождения в данных между AppsFlyer и Google Analytics

Ниже перечислены причины расхождений между AppsFlyer и Google Analytics.

<div id="high-volume-of-nonconsenting-ios-145-users" />

<Accordion title="Большое количество пользователей iOS 14.5+, не давших согласия">

Когда <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">AAP включен для вашего приложения</Anchor>, AppsFlyer не отправляет постбэки в Google Analytics для пользователей iOS 14.5+, не давших согласия. Если в вашем приложении много таких пользователей, между дэшбордами AppsFlyer и Google Analytics возникнут расхождения.

</Accordion>

<div id="customer-user-id" />

<Accordion title="Идентификатор клиента">

Google Analytics связывает события по идентификатору Customer User ID. По умолчанию AppsFlyer передает в качестве Customer User ID значения GAID или IDFA.

Поэтому Google Analytics считает пользователей, которые повторно устанавливают приложение (устанавливают, удаляют, а затем снова устанавливают), одними и теми же пользователями.

> 📄 **Пример**
>
> Пользователь устанавливает ваше приложение, а затем удаляет его. Затем пользователь повторно устанавливает приложение через кампанию ретаргетинга в пределах окна реатрибуции.
>
> Google Analytics считает этого пользователя тем же самым пользователем. В User Explorer в Google Analytics у этого пользователя указаны все следующие элементы:
>
> * regular-install
> * regular-install
> * reattribution-install
> * reattribution-in-app-event
>
> AppsFlyer, в свою очередь, считает этого пользователя двумя разными пользователями:
>
> * Пользователь, пришедший из UA-кампании
> * Пользователь, пришедший из кампании ретаргетинга

Кроме того, расхождения могут возникнуть, если вы внедрите оба SDK: GA и AppsFlyer.

</Accordion>

<div id="time-zone-differences" />

<Accordion title="Различия часового пояса">

Если часовой пояс вашего дэшборда GA отличается от часового пояса приложения в AppsFlyer, данные могут не совпадать.

> 📄 **Пример**
>
> Дэшборд вашего приложения настроен на GMT +13, а дэшборд GA — на GMT. Это значит, что дэшборд вашего приложения опережает дэшборд GA на один день.
>
> Поэтому данные, которые отображаются в дэшборде GA за 2 марта, появятся в дэшборде вашего приложения, только если вы выберете в фильтре диапазона дат 3 марта.

</Accordion>

<div id="duplicate-events" />

<Accordion title="Дублирование событий">

Если события происходят близко друг к другу, AppsFlyer и Google Analytics могут отклонить их как дублирующиеся события. Механизм <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#how-does-appsflyer-handle-event-deduplication">дедупликации событий</Anchor> в AppsFlyer отличается от механизма, который использует Google Analytics.

Поскольку AppsFlyer и Google Analytics по-разному выполняют дедупликацию событий, в данных о событиях могут возникать расхождения.

</Accordion>

<div id="session-count" />

<Accordion title="Количество сессий">

AppsFlyer учитывает сессии каждый раз, когда приложение запускается или возвращается на передний план. Google Analytics учитывает сессии на основе CID (идентификатора пользователя клиента) и активности.

> 📄 **Пример**
>
> Пользователь запускает ваше приложение, выполняет несколько действий, а затем переводит приложение в фоновый режим. Затем пользователь повторяет этот процесс 4 раза, каждый раз с интервалом около 5 минут.
>
> Для AppsFlyer это считается 5 разными сессиями. Однако для Google Analytics это считается одной сессией.

Чтобы узнать больше о том, как AppsFlyer и Google Analytics рассчитывают сессии, ознакомьтесь с ресурсами ниже.

1. <Anchor target="_blank" href="/marketers/ru/docs/measure-sessions">Как AppsFlyer учитывает сессии</Anchor>
2. <Anchor target="_blank" href="https://support.google.com/analytics/answer/2731565?hl=en">Сессии в Google Analytics</Anchor>

</Accordion>

<div id="google-analytics-views-and-filters" />

<Accordion title="Представления и фильтры Google Analytics">

Google Analytics позволяет создавать разные обзоры и применять к ним разные фильтры. При сравнении данных AppsFlyer и Google Analytics убедитесь, что в Google Analytics вы просматриваете данные в представлении ***Все данные веб-сайта***.

</Accordion>

<div data-zendesk-anchors="discrepancies-in-data-between-appsflyer-and-google-analytics=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-appsflyer-%D0%B8-google-analytics h_01HDP3G48R2XXEQDEAAJYGR9V9=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-appsflyer-%D0%B8-google-analytics h_01HDP3G48RQD3EW0DTRE2252JF=high-volume-of-nonconsenting-ios-145-users h_01HDP3G48RPWDY7ZRG9HM1F5AR=customer-user-id h_01HDP3G48RMGSJSWQDSKW5DXD9=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01HDP3G48R2JWF3Y23011NDCAN=time-zone-differences h_01HDP3G48RXFWZX4FQ0V2ZE44D=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-1 h_01HDP3G48RHT7PWSWZZAG27CP0=duplicate-events h_01HDP3G48R1044364MF96QX41E=session-count h_01HDP3G48RHQ3VG6N4HTT1KJFS=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-2 h_01HDP3G48R9571AS0WH7TWQWJP=google-analytics-views-and-filters" />

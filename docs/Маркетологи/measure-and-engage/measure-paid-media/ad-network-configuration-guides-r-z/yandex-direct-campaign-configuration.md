---
title: Настройка кампаний в Яндекс.Директ
metadata:
  keywords:
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
  created_at: '2021-03-30T10:52:06Z'
  edited_at: '2026-08-19T00:26:51Z'
  id: 360018910138
  locale: ru
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ru/articles/360018910138
---
> **Краткий обзор.** Яндекс.Директ — это рекламная платформа, на которой можно запускать кампании по привлечению пользователей и ретаргетинг в Яндекс.Поиске, а также в тысячах приложений и на сайтах Рекламной сети Яндекса.

<div id="set-up-yandex-direct" />

## Настройка Яндекс.Директ

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В AppsFlyer в боковом меню выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
    Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации/деактивации партнеров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

В окне настроек Яндекс.Директ есть 3 активные вкладки: Integration (Интеграция), Attribution link (Ссылка атрибуции) и Permissions (Разрешения).

<div id="integration-tab" />

<Accordion title="Вкладка 'Интеграция'">

<div id="activate-partner" />

### Активация партнера

На вкладке **Интеграция** включите переключатель **Активировать партнера**.  
 Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.

<div id="advanced-privacy" />

### Повышенная конфиденциальность

Только для приложений iOS: настройка **Включить режим расширенной конфиденциальности (для iOS 14.5 и выше)** позволяет контролировать, какие данные передаются партнеру в постбэках и отчетах. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#b-advanced-privacy">Подробнее о режиме расширенной конфиденциальности</Anchor>.

<div id="transaction-id" />

### Идентификатор транзакции

Только для приложений iOS. Только для приложений для iOS: когда переключатель **Предоставлять идентификатор транзакции SKAN** включен, вы <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">передаете партнеру идентификаторы транзакций для постбэков SKAdNetwork</Anchor>. Тем самым партнер может расшифровать ваши значения конверсии SKAdNetwork.

<div id="general-settings" />

### Общие настройки

Для Яндекс.Директ доступны следующие общие настройки.

#### Yandex Ecom Feed Counter ID

Введите номер тега Metrika в поле **Yandex Ecom Feed Counter ID**, если вы проводите кампании смарт-баннеров с вашим товарным фидом.

#### Yandex app ID

Введите **Yandex App ID**, полученный от Яндекс Директ.

<div id="default-postbacks" />

### Постбэки по умолчанию

Автоматически отправляйте постбэки в Яндекс.Директ после установок приложений и повторного вовлечения. В этом разделе можно определить **источник пользователей**, который позволяет отправлять постбэки.

Выберите **This partner only** (Только от этого партнера) для событий, поступающих только от пользователей, атрибутированных Яндекс.Директу.  
Выберите **All sources, including organic (Все источники, включая органические)**, чтобы предоставлять в Яндекс.Директ отчеты о событиях всех пользователей, которые есть в вашей базе.

Как сеть, ориентированная на все установки, Яндекс.Директ предпочитает получать постбэки по всем новым установкам приложения изо всех источников. Рекомендуется выбрать вариант **Все медиа-источники и органический трафик**.

<div id="in-app-events-postbacks" />

### Постбэки внутренних событий приложений.

В этом разделе вы можете настроить отправляемые в Яндекс.Директ постбэки по внутренним событиям приложения.

1. Включите **In-app event postbacks** (Постбэки по внутренним событиям приложения).
2. При необходимости задайте **окно постбэка по внутренним событиям приложения** (подробнее о<Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям"> настройке окна постбэка по внутренним событиям приложения</Anchor>).
3. Чтобы добавить в список событие, определенное в SDK, нажмите **Добавить событие**.
4. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">Укажите обязательные параметры</Anchor>.
5. Нажмите **Сохранить интеграцию**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка Attribution Link (Ссылки атрибуции)">

Формируйте и сохраняйте ссылки атрибуции и отправляйте их партнеру, чтобы атрибутировать определенные кампании, группы объявлений и отдельные объявления — как для кампаний по привлечению пользователей, так и для ретаргетинговых кампаний. Вы можете использовать либо ссылку для конкретной платформы, либо <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее о структуре и параметрах ссылок атрибуции</Anchor>.

**Чтобы создать ссылку атрибуции,** следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">этой инструкции</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

AppsFlyer получает информацию о затратах через API. Подробную информацию <Anchor target="_blank" href="/marketers/ru/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">о поддерживаемых параметрах, метриках и функциях см. в</Anchor> таблице интеграции затрат рекламной сети. **Примечание**. Для получения сведений о затратах требуется подписка ROI360.

**Чтобы включить API данных о затратах**:

* Следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">этим инструкциям по интеграции</Anchor>. **Примечание**. Добавьте в свои ссылки идентификатор кампании (af\_c\_id=`{campaign_id}`) для получения точной отчетности о затратах. <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее</Anchor>

<Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#статус-api-затрат">Просмотреть статус API данных о затратах</Anchor> и время последнего получения AppsFlyer соответствующих данных о затратах можно либо на дэшборде статуса интеграции данных о затратах (и доходах от рекламы), либо на дэшборде конкретной рекламной сети.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка 'Ad Revenue' (Доходы от рекламы)">

Данные о доходах от рекламы недоступны для этого партнера.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

На этой вкладке можно выбрать разрешения для Яндекс.Директ в зависимости от того, в каком качестве выступает партнер: как рекламная сеть, агентство или и то, и то. Обратите внимание, что, даже когда атрибуция для Яндекс.Директ отключена, вкладка разрешений остается активной и можно предоставить Яндекс.Директ разрешение на управление. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">Настройка разрешений для Яндекс.Директ</Anchor>.

</Accordion>

<div data-zendesk-anchors="set-up-yandex-direct=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%8F%D0%BD%D0%B4%D0%B5%D0%BA%D1%81%D0%B4%D0%B8%D1%80%D0%B5%D0%BA%D1%82 h_01HJZW81YDFP6ZV188XP3H4H54=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%8F%D0%BD%D0%B4%D0%B5%D0%BA%D1%81%D0%B4%D0%B8%D1%80%D0%B5%D0%BA%D1%82 h_01HJZW81YD3S8BEE6MNT30VYZH=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HJZW81YD1JA5N01HT248PR8K=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 advanced-privacy=%D0%BF%D0%BE%D0%B2%D1%8B%D1%88%D0%B5%D0%BD%D0%BD%D0%B0%D1%8F-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C h_01HJZW81YDNWAEKA2DP0QPPQRC=%D0%BF%D0%BE%D0%B2%D1%8B%D1%88%D0%B5%D0%BD%D0%BD%D0%B0%D1%8F-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C transaction-id=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%82%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D0%B8 h_01HJZW81YD8QEETTP4NSG2QCPQ=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%82%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D0%B8 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HJZW81YDT69PGFTJMQ8WTYN2=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01HJZW81YD18MW2BNGTZCZM7ZW=yandex-ecom-feed-counter-id h_01HJZW81YDTQ0Q4H39GVJMHYNG=yandex-app-id default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HJZW81YDZDYDES5ZPRQ5BEC3=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01HJZW81YDMTRZ2VG8S9B48GTD=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01HJZW81YE8XP6Q9RA9XTCKX2T=attribution-link-tab h_01HJZW81YES6M13VVJMTAB6KXQ=cost-tab h_01HJZW81YE7CYXEDFZKWZYVYET=ad-revenue-tab h_01HJZW81YERG3X6RG9Z2CM3YSF=permissions-tab" />

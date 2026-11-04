---
title: Конфигурация кампании TVSquared (ранее WyWy)
metadata:
  keywords:
    - Advertisers
    - TV Squareed
    - Wywy
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-09-06T08:58:47Z'
  edited_at: '2026-10-19T14:23:21Z'
  id: 213836263
  locale: ru
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ru/articles/213836263
---
> **Кратко:** TVSquared (ранее WyWy) — интегрированный партнер AppsFlyer из категории рекламных сетей, который позволяет всей цифровой команде — маркетологам, менеджерам по продукту и специалистам по данным — вести бизнес на основе данных. TVSquared создает единое представление о пользователях на разных устройствах, предоставляя инструменты для оптимизации пользовательского опыта в режиме реального времени.

<div id="setting-up-tvsquared" />

## Настройка TVSquared

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

**Примечание:** для TVSquared нужно заполнить вкладку Integration. Остальные вкладки для TVSquared не применяются.

Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

Вкладка Integration («Интеграция») содержит несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

1. Включите ***Activate Partner***.  
   Отобразятся параметры интеграции.  
   Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
2. Заполните поля в разделе General Setting:
   * ***SITEID***: введите SITEID, полученный от TVSquared.
   * ***COLLECTORID***: введите COLLECTORID , полученный от TVSquared.
3. **Постбэки по умолчанию**: AppsFlyer отправляет постбэки в TVSquared после установки или повторного вовлечения пользователя. Выберите вариант отправки, для которого партнер будет получать постбэки:
   * **События, атрибутированные любому партнеру или как органические**: все установки, независимо от источника, передаются в TVSquared
   * **Откл.**
4. Заполните поля настроек событий в приложении:

* ***SITEID***: введите SITEID, полученный от TVSquared.
* ***COLLECTORID***: введите COLLECTORID , полученный от TVSquared.
* **customerid:** (необязательно) Это поле можно оставить пустым.
* (необязательно) Включите ***In-App Events Postback***: сопоставьте свои события в приложении с TVSquared с помощью постбэков. Настройте параметры следующим образом:
  * Нажмите Add Event, чтобы добавить в список событие SDK и заполнить параметры.
* Нажмите **Сохранить интеграцию**.

<div id="note" />

> 📘 **Примечание:**
>
> Согласно положениям и условиям Meta ads и X Ads, AppsFlyer не может передавать данные на уровне пользователя каким-либо 3rd party. Поэтому все установки из Meta ads и X Ads отправляются в TVSquared как органические.
>
> Подробнее о передаче данных третьим сторонам см. для 3rd parties <Anchor target="_blank" href="/marketers/ru/docs/user-level-data-retention">здесь</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для TVSquared.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения для TVSquared недоступны.

</Accordion>

<div data-zendesk-anchors="setting-up-tvsquared=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-tvsquared h_01HF9R4JZ504QNYCQQ8TFDM6FV=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-tvsquared h_01HF9R4JZ5VXT1P5T3RVRXN522=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HF9R4JZ55HMSRD3TNFF05PKZ=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HF9R4JZ5KWKPCN3ESQ9K27S7=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HF9R4JZ596NM643Z662BGY0M=attribution-link-tab h_01HF9R4JZ50XY445ABGAPDY962=cost-tab h_01HF9R4JZ5BA74FKFRKY4FPTAS=ad-revenue-tab h_01HF9R4JZ5BV6C6H6V6W53BXXK=permissions-tab" />

---
title: Интеграция Xsolla с AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2024-03-25T06:20:28Z'
  edited_at: '2026-08-19T00:12:08Z'
  id: 23593013687185
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/23593013687185
---
> **Краткий обзор:** Xsolla, интегрированный партнёр AppsFlyer, является технический партнер в сфере игровой коммерции, специализирующийся на обработке платежей вне традиционных платформ приложений. Интеграция между Xsolla и AppsFlyer позволяет Xsolla автоматизировать покупки в веб-магазине и отправлять доходы в AppsFlyer, чтобы получать полную информацию о ROAS и LTV игр, включая покупки, совершённые в веб-магазине Xsolla.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="integration-types" />

## Типы интеграции

Существует два возможных метода интеграции с Xsolla:

* [Интеграция технического партнёра](#настройка-интеграции-с-технологическим-партнёром): эта интеграция позволяет Xsolla отправлять покупки в веб-магазине и доход как внутренние события приложения, тем самым повышая ROAS и LTV кампаний в мобильном приложении помимо стандартных покупок в магазине приложений.
* [Интеграции веб-SDK PBA](#настройка-интеграции-веб-sdk-pba): такая интеграция позволяет Xsolla отправлять покупки в веб-магазине и доход в виде веб-событий, что позволяет AppsFlyer измерять эффективность веб-кампаний, направляя пользователей игр непосредственно в веб-магазин.

**Необходимые условия:**

* Перед настройкой интеграции обязательно <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">свяжитесь с партнёром</Anchor> и откройте у него аккаунт.
* Чтобы интеграция функционировала правильно, обязательно передайте идентификатор пользователя клиента (CUID) в AppsFlyer и убедитесь, что он соответствует идентификатору пользователя, переданному Xsolla. Такая синхронизация позволяет пользователям входить в веб-магазин Xsolla и обеспечивает точную отправку данных пользователя в AppsFlyer.

<div id="setting-up-the-tech-partner-integration" />

## Настройка интеграции с технологическим партнёром

**Необходимые условия:** Перед настройкой интеграции обязательно [свяжитесь с партнёром](#) и откройте у него аккаунт. Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В AppsFlyer в боковом меню выберите **Сотрудничество**> **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При первом входе вам нужно включить переключатель **Активация партнёра**, чтобы настроить интеграцию. Переключатель должен оставаться во включенном положении всё время, пока вы сотрудничаете с Xsolla. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнёров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

Окно настройки использует только вкладку **Интеграция**.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

<div id="activate-partner" />

#### Активация партнёра

Настройка выполняется со страницы **Активные интеграции**, но чтобы найти партнера, необходимо сначала перейти на <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations">маркетплейс</Anchor>. Переключатель должен оставаться во включенном положении всё время, пока вы сотрудничаете с Xsolla. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнёров</Anchor>.

<div id="advanced-privacy" />

#### Расширенные настройки конфиденциальности

Для приложений iOS появляется переключатель <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">Режим расширенной конфиденциальности</Anchor>. Когда он включен, он ограничивает предоставление партнёру идентификаторов пользователей. Обратите внимание, что когда в настройках приложения включен переключатель <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">Агрегированная расширенная конфиденциальность</Anchor>, то переключатель **Расширенная конфиденциальность (для iOS 14.5+ и выше)** включен по умолчанию и заблокирован.

<div id="default-postbacks" />

#### Постбэки по умолчанию

AppsFlyer отправляет постбэки в Xsolla после установки приложения пользователями. В этом разделе можно <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">определить эти постбэки</Anchor>.

* **Off**(Выкл.): постбэки об установках не отправляются в Xsolla.  
  **Примечание:** Интеграция Xsolla с AppsFlyer не требует отправки постбэков об установке. Поэтому рекомендуется установить значение Off (Выкл.).
* **Все медиа-источники, включая органические**: постбэки об установках отправляются для событий, атрибутированных любому партнёру, а также для органических событий.

<Image align="center" alt="default_postbacks.png" src="https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png" />

<div id="in-app-event-postbacks" />

#### Постбэки по внутренним событиям приложения

В этом разделе можно настроить отправку партнёру постбэков о своих событиях в AppsFlyer.

<Image align="center" alt="xsolla-af-login-3.jpg" src="https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg" />

1. Активируйте **Постбэки по внутренним событиям приложения**.
2. Нажмите **Добавить событие**, чтобы добавить событие SDK или между серверами в список.
3. Заполните следующие параметры:

| Название параметра | Описание |
| --- | --- |
| **Событие AppsFlyer** | Название события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<br /><br />**Примечание:**<ul><li>Для Xsolla обязательно добавьте событие `af_login` или любое другое событие, которое представляет собой вход пользователя в мобильное приложение, как показано на скриншоте выше.</li></ul> |
| **сопоставлено с событием партнёра** | Введите соответствующее название события, которое нужно отправить в Xsolla. В Xsolla гибкие правила наименования, поэтому в этом поле можно использовать любое название. |
| **для пользователей из** | Выберите **Все медиа-источники, включая органические**, чтобы отправлять постбэки для событий, атрибутированных любому партнёру, а также для органических событий. |
| **включая** | <ul><li>**Нет значений и дохода** Отправьте только само событие без каких-либо параметров (ценностей, значений или выручки).</li><li>**Ценности, значения и отсутствие выручки**: отправляются все параметры, **кроме** значения дохода.</li><li>**Значение и доход**: отправляются все параметры события, **включая** значение дохода (если оно есть в событии).</li></ul>Примечание: Интеграция Xsolla с AppsFlyer не требует отправки значений или дохода. Поэтому применим любой выбранный вариант. |

4. Нажмите **Сохранить интеграцию**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Xsolla.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о затратах не поддерживаются при интеграции с Xsolla.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Данные о доходах от рекламы не поддерживаются при интеграции с Xsolla.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для Xsolla.

</Accordion>

<div id="setting-up-the-pba-web-sdk-integration" />

## Настройка интеграции веб-SDK PBA

Эта интеграция позволяет представлять текущие данные LTV (пожизненной ценности) и аналитические данные для анализа эффективности приложения на дэшборде PBA.

**См. инструкции по настройке интеграции:**

1. **В AppsFlyer:** <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer?query=adding%20an%20app">Добавьте приложение Xsolla</Anchor>. Выберите в качестве платформы <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer#web-pba">Веб (PBA)</Anchor> и введите следующие данные:
   * Используйте домен вашего Веб-магазина в качестве URL-адреса веб-приложения. Например, если ваш домен в веб-магазине — [www.webshop.com,](http://www.webshop.com,) используйте его в качестве URL-адреса вашего веб-приложения.
   * В качестве имени приложения можно использовать любое значение.
2. **В AppsFlyer:** <Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings#add-brand-bundle">Добавьте пакет Xsolla</Anchor> со следующей информацией:
   1. Введите любое наименование в качестве названия пакета.
   2. Выберите созданное на предыдущем этапе веб-приложение в качестве веб-приложения пакета.
3. **In Xsolla:** Подключите AppsFlyer к аккаунту издателя Xsolla:
   1. Откройте свой проект в своём <Anchor target="_blank" href="https://publisher.xsolla.com/">аккаунте издателя</Anchor>.
   2. Выберите свой сайт и нажмите **Настроить**.
   3. На вкладке **Настройки сайта** перейдите в раздел **Приложения**.
   4. В блоке **AppsFlyer** нажмите «**Подключиться**».  
      <Image align="center" alt="xsolla-connect.jpg" src="https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg" />
   5. В поле **Ключ разработчика AppsFlyer** введите ключ веб-разработчика AppsFlyer. Смотрите ниже, как [найти этот ключ в AppsFlyer](/docs/xsolla-integration-with-appsflyer#как-найти-ключ-веб-разработчика-в-appsflyer).
   6. Нажмите **Подключить**.

<div id="finding-the-web-dev-key-in-appsflyer" />

#### Как найти ключ веб-разработчика в AppsFlyer

1. На странице **Мои приложения** нажмите **Посмотреть пакеты бренда**.
2. Нажмите значок «Копировать» в строке пакета Xsolla.

<Image align="center" alt="xsolla-brand-bundle2.jpg" src="https://files.readme.io/9cb6a9e872e482f7e426aea7e615afb1f91017c569e7cd67286cdb946d9d2445-26923253273361.jpg" />

<div id="identifying-xsollas-events-in-appsflyer" />

## Идентификация событий Xsolla в AppsFlyer

<div id="tech-partner-s2s-integration" />

### Интеграция с технологическими партнерами (S2S):

Xsolla отправляет AppsFlyer два внутренних события приложения:

* **xsolla-billing-payment** – покупка товара
* **xsolla-billing-return** – возврат купленного товара

Оба события относятся к внутренним событиям мобильного приложения.

<div id="web-sdk-integration" />

### Интеграция веб-SDK:

Xsolla отправляет AppsFlyer множество веб-событий, адаптированных под конкретную деятельность рекламодателя. Самый важный из них – это «ПОКУПКА», в котором содержится доход.  
Веб-события Xsolla будут отображаться в отчетах PBA по веб-атрибуции и отчётах DataLocker о сырых данных по «веб-событиям».

<div id="traits-and-limitations" />

<Accordion title="Характеристики и ограничения">

Поддержка ПК/ консолей – интеграция AppsFlyer с Xsolla на данном этапе не поддерживает приложения для ПК/ консолей

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="https://developers.xsolla.com/solutions/web-shop/analytics/appsflyer/">Документация Xsolla</Anchor>

<div data-zendesk-anchors="h_01HST42K52VQDWCWGP7TQVFB2X=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE integration-types=%D1%82%D0%B8%D0%BF%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01J3DB8MCNQKKKCV1M39KN7Q0H=%D1%82%D0%B8%D0%BF%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 setting-up-xsolla=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%BC-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%BE%D0%BC h_01HST42K52JKQ70F7Y5PHDZAZ5=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%BC-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%BE%D0%BC h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0 h_01HST42K52RCTSGRNRCJ1C70NP=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0 advanced-privacy=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HST42K52BBJ6JS5KM0WCN6CF=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HST47F5BXWV5W8BNHS9M2MTN=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FKEAV3GG6X17X3NCCSWJAS=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab setting-up-the-pba-web-sdk-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1-sdk-pba h_01J3DEZZHDPSRZRXDV6FD4HY6Q=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1-sdk-pba finding-the-web-dev-key-in-appsflyer=%D0%BA%D0%B0%D0%BA-%D0%BD%D0%B0%D0%B9%D1%82%D0%B8-%D0%BA%D0%BB%D1%8E%D1%87-%D0%B2%D0%B5%D0%B1-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-%D0%B2-appsflyer h_01J3F247QEAFGRW7CEP941KZE9=%D0%BA%D0%B0%D0%BA-%D0%BD%D0%B0%D0%B9%D1%82%D0%B8-%D0%BA%D0%BB%D1%8E%D1%87-%D0%B2%D0%B5%D0%B1-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D0%B0-%D0%B2-appsflyer identifying-xsollas-events-in-appsflyer=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-xsolla-%D0%B2-appsflyer h_01JMHXRGB60RVZ399FNHS18ZHZ=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-xsolla-%D0%B2-appsflyer tech-partner-s2s-integration=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81-%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%BC%D0%B8-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0%D0%BC%D0%B8-s2s h_01JMHXS5MZ7B781WNNVYMDGGFY=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81-%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%BC%D0%B8-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0%D0%BC%D0%B8-s2s web-sdk-integration=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%B5%D0%B1-sdk h_01JMHXX7VBPPS7GQ0VBGWRPT7X=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%B5%D0%B1-sdk h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations h_01J1C78W0MP8KXFB4251FKWJBX=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

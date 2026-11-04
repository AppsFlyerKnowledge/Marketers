---
title: Интеграция Appcharge с AppsFlyer
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
  created_at: '2025-06-17T13:21:47Z'
  edited_at: '2026-08-28T00:10:14Z'
  id: 36292113943825
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/36292113943825
---
> **Кратко:** Appcharge — интегрированный партнер AppsFlyer и поставщик технологий гейминг-коммерции, специализирующийся на обработке платежей за пределами традиционных экосистем магазинов приложений. Благодаря интеграции с AppsFlyer Appcharge может автоматически отправлять в AppsFlyer данные о покупках и возвратах из веб-магазина, обеспечивая более полное представление о рентабельности расходов на рекламу (ROAS) и пожизненной ценности пользователя (LTV).

<div id="about-appcharge" />

## Об Appcharge

<Anchor target="_blank" href="https://appcharge.com/">Appcharge</Anchor> — интегрированный партнер AppsFlyer и D2C-платформа (direct-to-consumer), созданная для мобильных гейминг-паблишеров. Интеграция помогает паблишерам отслеживать покупки в их веб-магазине — важном канале дохода за пределами традиционных магазинов приложений. Отправляя данные о покупках и возвратах напрямую в AppsFlyer, Appcharge обеспечивает точный расчет рентабельности расходов на рекламу (ROAS) на основе чистого дохода и дает более глубокие инсайты об эффективности кампаний и пожизненной ценности игрока (LTV).

Интеграция Appcharge поможет вам:

* Атрибуция и измерение эффективности электронной коммерции
* Убедитесь, что LTV учитывается на основе покупок в веб-магазине
* Атрибутируйте покупки в веб-магазине маркетинговым кампаниям
* Поддерживайте согласованность с данными ваших мобильных кампаний

Это руководство поможет вам настроить интеграцию Appcharge.

<div id="set-up-the-integration" />

## Настройка интеграции

**Необходимые условия:**

* У вас есть активная учетная запись Appcharge. Если нет, тогда пожалуйста обратитесь к партнеру (Appcharge) и зарегистрируйтесь у него, прежде чем настраивать интеграцию.
* Ваша учетная запись AppsFlyer включает необходимые разрешения для настройки интеграций с партнерами.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнеров**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Оставляйте его включенным, пока вы работаете с партнером.
5. Завершите настройку на вкладке **Integration**, как описано ниже.

**Для активации или изменения интеграции:**

В AppsFlyer перейдите на вкладку **Collaborate > Partner Integrations > Active integrations**, найдите партнера и внесите изменения.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

<div id="activate-partner" />

#### Активация партнёра

При первом входе вам нужно включить переключатель **Activate partner**, чтобы настроить интеграцию. Переключатель должен оставаться во включенном положении все время, пока вы работаете с Appcharge. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">partner activation</Anchor>.

<div id="advanced-privacy" />

#### Расширенные настройки конфиденциальности

Для приложений iOS появляется переключатель <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">Advance Privacy</Anchor>. Когда он включен, это ограничивает передачу идентификаторов пользователей партнеру. Обратите внимание, что когда в настройках приложения включен переключатель <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">Агрегированная расширенная конфиденциальность</Anchor> , то **Расширенная конфиденциальность (для iOS 14.5+ и более поздних версий)** включена по умолчанию и заблокирована.

<div id="default-postbacks" />

#### Постбэки по умолчанию

AppsFlyer отправляет постбэки по умолчанию в Appcharge после установок пользователями. Используйте этот раздел, чтобы <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">определить эти постбэки</Anchor>.

* **Off:** Постбэки об установках не отправляются в Appcharge.  
   **Примечание:** интеграция Appcharge с AppsFlyer не требует отправки постбэков об установках. Поэтому рекомендуется установить значение Off.
* **Все медиаисточники, включая органические:** постбэки об установках отправляются для событий, атрибутированных любому партнёру, а также для органических событий.

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

<div id="in-app-event-postbacks" />

#### Постбэки по внутренним событиям приложения

В этом разделе вы можете сопоставить свои события AppsFlyer с партнёрами через постбэки.

![xsolla-af-login-3.jpg](https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg)

1. Включите **постбэки событий в приложении**.
2. Нажмите **Add event**, чтобы добавить в список событие SDK или server-to-server.
3. Введите следующие параметры:
4. Нажмите кнопку **Save Integration** (Сохранить интеграцию).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Appcharge.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о затратах не поддерживаются при интеграции с Appcharge.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Данные о доходах от рекламы не поддерживаются при интеграции с Appcharge.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для Appcharge.

</Accordion>

<div id="identify-appcharge-events-in-appsflyer" />

## Идентификация событий Appcharge в AppsFlyer

Appcharge отправляет в AppsFlyer два типа мобильных событий в приложении:

* `ac_af_purchase` — когда пользователь успешно завершает покупку
* `ac_af_refund` — когда возврат средств завершён

<div id="traits-and-limitations" />

<Accordion title="Характеристики и ограничения">

Поддержка ПК/консолей: интеграция AppsFlyer с Appcharge не поддерживает приложения для ПК/консолей.

</Accordion>

Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">интеграциях с партнёрами</Anchor>.

<div data-zendesk-anchors="integration-types=%D0%BE%D0%B1-appcharge h_01J3DB8MCNQKKKCV1M39KN7Q0H=%D0%BE%D0%B1-appcharge setting-up-appcharge=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01HST42K52JKQ70F7Y5PHDZAZ5=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0 h_01HST42K52RCTSGRNRCJ1C70NP=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0 advanced-privacy=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HST42K52BBJ6JS5KM0WCN6CF=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HST47F5BXWV5W8BNHS9M2MTN=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FKEAV3GG6X17X3NCCSWJAS=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab identifying-appcharge-events-in-appsflyer=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-appcharge-%D0%B2-appsflyer h_01JMHXRGB60RVZ399FNHS18ZHZ=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-appcharge-%D0%B2-appsflyer h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations" />

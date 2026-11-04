---
title: Настройка кампании Appodeal
metadata:
  keywords:
    - ad revenue
    - cost
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
  created_at: '2019-12-17T19:36:02Z'
  edited_at: '2026-10-19T14:21:07Z'
  id: 360004404977
  locale: ru
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ru/articles/360004404977
---
> **Кратко:** Appodeal, интегрированный партнер AppsFlyer, предоставляет владельцам приложений атрибуцию по кликам и универсальное решение для монетизации рекламы. Доход от рекламы отображается с детализацией на уровне пользователя.

<div id="setting-up-appodeal-integration" />

## Настройка интеграции с Appodeal

![](https://cdn.appsflyer.com/marketplace/static/logo/appodeal.png)

Интеграция AppsFlyer с Appodeal поддерживает атрибуцию по кликам и <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">атрибуцию дохода от рекламы на уровне пользователя.</Anchor>

**Необходимые условия:** Перед настройкой интеграции обязательно [свяжитесь с партнёром](#) и откройте у него аккаунт. Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе:

<div id="integration" />

<Accordion title="Интеграция">

Настройте этот раздел, если Appodeal предоставляет рекламные услуги через рекламную сеть.

**Чтобы включить интеграцию**:

1. Включите **Активировать партнёра.**
2. Нажмите кнопку **Save Integration** (Сохранить интеграцию).

</Accordion>

<div id="attribution-link" />

<Accordion title="Ссылка атрибуции">

На этой вкладке можно создавать ссылки атрибуции по кликам (для использования Appodeal). <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее о структуре ссылок и параметрах</Anchor>.

**Чтобы создать ссылку атрибуции**:

1. Выберите параметр в раскрывающемся списке Parameter name и задайте значение.
2. Нажмите **Add parameter** и повторите предыдущий шаг, чтобы добавить другие параметры.
3. Определите продолжительность **окна атрибуции по кликам.**
4. Скопируйте ссылку атрибуции по кликам и отправьте ее в рекламную сеть.  
   Примечание: AppsFlyer не сохраняет ссылки.

**Ссылка атрибуции и окно атрибуции**

| Тип ссылки атрибуции | Активация ссылки | Окна атрибуции |
| --- | --- | --- |
| Клик | Пользователь нажимает на рекламу, показанную рекламной сетью | **Окно атрибуции по кликам** задано заранее; это **максимально допустимое время от клика до установки**.<br /><br />Пример: установка (первый запуск), выполненная после клика—но до истечения окна атрибуции—атрибутируется на Appodeal.<br /><br />**Название параметра**: `af_click_lookback`  <br />**Значение по умолчанию**: 7 дней  <br />**Диапазон:** 1–23 часа или 1–30 дней |

**Типичные параметры ссылки**

| Параметр | Название параметра | Description(Описание) |
| --- | --- | --- |
| кампания; | c | Название кампании |
| Блок рекламы | af\_adset | Используйте, чтобы различать наборы рекламных объявлений. |
| Название рекламного объявления | af\_ad | Используйте, чтобы различать креативы в наборе рекламных объявлений. |
| Тип устройства: xiaomi-Redmi Note 8 | af\_siteid  <br />af\_subsiteid | Используется для атрибуции установок конкретным паблишерам.<br /><br />**Рекомендуется!** Если есть несколько паблишеров,<ul><li>Ограничьте количество используемых идентификаторов ID сайта</li><li>Используйте параметр subsite ID, чтобы не <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">превысить ограничение по идентификатору ID сайта</Anchor></li></ul> |
| Параметры подписчика | af\_sub1, af\_sub2, af\_sub3, af\_sub4, and af\_sub5 | Используйте, чтобы вставлять значения.<ul><li>Параметры анализируются и включаются в отчет о сырых данных.</li><li>Используйте их для агрегации или фильтрации данных</li></ul> |

</Accordion>

<div id="cost" />

<Accordion title="затраты;">

Appodeal передает данные о стоимости CPI через ссылку атрибуции.

</Accordion>

<div id="ad-revenue" />

<Accordion title="Дата и время">

* Appodeal предоставляет медиацию рекламного дохода с <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">гранулярностью на уровне пользователя</Anchor>
* Узнайте больше об <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution">атрибуции дохода от рекламы в AppsFlyer</Anchor>

**Чтобы включить API доходов от рекламы**:

* Следуйте <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">этим инструкциям по интеграции</Anchor>.

</Accordion>

<div id="permissions" />

<Accordion title="Разрешения">

Для Appodeal не нужно настраивать разрешения.

</Accordion>

<div data-zendesk-anchors="setting-up-appodeal-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-appodeal h_01HKW9BK4ZAR4Q22Z9WBVFPPT7=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-appodeal h_01HKW9BK4ZDFDX9X7P2HW4QR1P=integration h_01HKW9BK4ZM4JMQKT4Y8ZC050V=attribution-link h_01HKW9BK4ZV8DWSZQ55332NQWY=cost h_01HKW9BK4ZS3GYMZ6E9T64PPGC=ad-revenue h_01HKW9BK4ZJ1F1Z099NJHRZRNE=permissions" />

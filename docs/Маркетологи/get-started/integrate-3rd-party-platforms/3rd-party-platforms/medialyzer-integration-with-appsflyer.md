---
title: Интеграция Medialyzer с AppsFlyer
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
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2026-08-19T00:11:26Z'
  id: 14963611180689
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/14963611180689
---
> **Краткий обзор.** Medialyzer, интегрированный партнер AppsFlyer, разрабатывает и продает программное обеспечение как сервисное решение. Решение позволяет медиапланировщикам оптимизировать свои кампании на ТВ для онлайн-бизнеса на основе мгновенно сгенерированных данных о посещениях и конверсиях во время показа рекламы на ТВ.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам.  Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.

<div id="setting-up-medialyzer" />

## Настройка Medialyzer

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При первом входе вам нужно включить переключатель **Активация партнера**, чтобы настроить интеграцию. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

Подробное описание заголовка окна "Partner Configuration" (Настройки партнера) см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка 'Интеграция'">

<div id="activate-partner" />

#### Активация партнера

Настройка выполняется со страницы **Активные интеграции**, но чтобы найти партнера, необходимо сначала перейти на <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations">маркетплейс</Anchor>. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнёров</Anchor>.

<div id="advanced-privacy" />

#### Расширенные настройки конфиденциальности

Для приложений iOS появляется переключатель <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">Режим расширенной конфиденциальности</Anchor>. Когда он включен, он ограничивает предоставление партнеру идентификаторов пользователей. Обратите внимание, что когда в настройках приложения включен переключатель <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">Агрегированная расширенная конфиденциальность</Anchor>, то переключатель **Расширенная конфиденциальность (для iOS 14.5+ и выше)** включен по умолчанию и заблокирован.

<div id="default-postbacks" />

#### Постбэки по умолчанию

AppsFlyer отправляет постбэки в Medialyzer после установок приложения пользователями. В этом разделе можно <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#f">определить эти постбэки</Anchor>.

* **Выключено**: постбэки об установках не отправляются в Medialyzer.
* **Все медиа-источники, включая органические**: постбэки об установках отправляются для событий, атрибутированных любому партнеру, а также для органических событий.

<Image align="center" alt="default_postbacks.png" src="https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png" />

<div id="in-app-event-postbacks" />

#### Постбэки внутренних событий приложений.

В этом разделе можно настроить отправку партнеру постбэков о своих событиях в AppsFlyer.

<Image align="center" alt="app_event_postbacks.JPG" src="https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png" />

1. Активируйте **In-app event postbacks** (Постбэки о внутренних событиях приложений).
2. Чтобы добавить в список событие, определенное в SDK, **или межсерверное событие**, нажмите Add Event (Добавить событие).
3. Введите следующие параметры:

| Имя параметра | Описание |
| --- | --- |
| **AppsFlyer event (Событие AppsFlyer)** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<br />**Совет**: Не нашли здесь нужное событие?<ul><li>Убедитесь, что событие активировано на устройстве с неорганической установкой, и повторите поиск.</li><li>Введите его в поле **AppsFlyer event** (Событие AppsFlyer) и нажмите **Create custom** (Добавить другое). Подробнее о сопоставлении пользовательских событий <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">читайте здесь</Anchor>.</li></ul> |
| **mapped to partner event (сопоставлено с событием партнера)** | Введите соответствующее название или ID каждого события, как определено в BPM, или отправьте события как они есть без сопоставления имен. |
| **for users from (для пользователей от)** | Выберите **Все медиа-источники, включая органические**, чтобы отправлять постбэки для событий, атрибутированных любому партнеру, а также для органических событий. |
| **Включая** | <ul><li>**Нет значений и нет дохода**: отправляет само событие без каких-либо параметров (значений или доходов).</li><li>**Значения, нет дохода:** отправляет все параметры, **кроме** значения дохода.</li><li>**Значения и доход**: отправляет все параметры события, **включая** значение дохода (если оно есть в событии).</li></ul> |

4. Нажмите кнопку **Save Integration** (Сохранить интеграцию).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка Attribution Link (Ссылки атрибуции)">

Ссылки атрибуции недоступны для Medialyzer.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с Medialyzer.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка 'Ad Revenue' (Доходы от рекламы)">

Данные о доходах от рекламы не поддерживаются при интеграции с Medialyzer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для Medialyzer.

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-spoteffects=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-medialyzer h_01H9FKEAV37AT3VTZ5WV1YMWC2=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-medialyzer h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FKEAV3DW2A6RQ1NS44FT5F=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 advanced-privacy=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01H9FKEAV3T3YCPBYW70QVF540=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FKEAV3Z1Y09P6E18J8AVX2=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01H9FKEAV3GG6X17X3NCCSWJAS=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />

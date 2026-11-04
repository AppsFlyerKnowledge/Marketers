---
title: Настройка кампании Bidease
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
  created_at: '2023-11-13T13:17:18Z'
  edited_at: '2026-09-12T00:23:17Z'
  id: 20106343354129
  locale: ru
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ru/articles/20106343354129
---
> **Краткий обзор.** Bidease (bidease\_int), интегрированный партнер AppsFlyer, — это полностью прозрачная платформа DSP для специалистов по мобильному маркетингу. Используя собственные технологии программируемой рекламы, машинное обучение и данные первой стороны (собственные данные), Bidease оптимизирует кампании во всех основных мобильных форматах для достижения желаемого поведения после установки без риска для клиентов.

<Image alt="bidease.png" src="https://files.readme.io/4a3373c0fdb73190017601c374ca7634cc0feb1954b6e23fc1bd9693c60605f9-20106376017041.png" width="100px" />

<div id="setting-up-bidease" />

## Настройка Bidease

Интеграция с Bidease поддерживает атрибуцию по кликам и просмотрам.

**Необходимые условия:** Перед настройкой интеграции обязательно [свяжитесь с партнёром](#) и откройте у него аккаунт. Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции. Этот переключатель **обязательно** должен быть включен все время, пока вы работаете с партнером.  
    Дополнительная информация по активации партнеров: нажмите <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

Окно общей конфигурации содержит следующие вкладки: Интеграция, Ссылка атрибуции, Затраты, Доход от рекламы, Разрешения. Для Bidease доступны следующие вкладки: Интеграция, Ссылка атрибуции и Разрешения.

<div id="note" />

> 📘 **Примечание**
>
> * Некоторые настройки отличаются для устройств iOS и Android.
> * Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">настройке партнерских интеграций.</Anchor>

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке **Интеграция** есть ряд разделов, описанных ниже.

<div id="activate-partner" />

#### Активация партнера

Включите переключатель **Активировать партнёра** .  
**Примечание:** переключатель **должен оставаться включённым (активным) as long as you work with the partner.**

<div id="advanced-privacy" />

#### Расширенные настройки конфиденциальности

**Только для приложений на iOS:** Ваш контроль над данными, передаваемыми партнеру через постбэки и <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">отчеты</Anchor>, зависит от состояния переключателя **Расширенная конфиденциальность (для iOS 14.5+ и более поздних версий)**:

| Расширенная конфиденциальность включена | Расширенная конфиденциальность выключена |
| --- | --- |
| Постбэки отправляются только для событий, атрибутированных партнеру | Постбэки отправляются в соответствии с вашей настройкой:<ul><li>**Все медиа-источники и органический трафик**</li><li>**Только данный партнер**</li></ul> |
| Постбэки отправляются в соответствии с <Anchor target="_blank" href="/partners/ru/docs/advanced-privacy-guide-postback-macros-for-ad-networks">шаблоном Расширенная конфиденциальность</Anchor> |  |
| Партнеру передаются <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">агрегированные и анонимные данные</Anchor>, то есть данные на уровне пользователя (ID устройства) не передаются. |  |

<div id="transaction-id" />

#### Идентификатор транзакции

**Только для приложений iOS:** Когда переключатель **Предоставлять идентификатор транзакции SKAN** включен, вы разрешаете AppsFlyer <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">передавать идентификатор транзакции постбэков SKAdNetwork</Anchor> в Reddit. Таким образом, Reddit может декодировать ваши значения конверсии SKAdNetwork.

<div id="install-attribution" />

#### Атрибуция установок

Чтобы атрибутировать установки по просмотрам от Bidease, включите опцию **Атрибуция установок по просмотрам**. На вкладке [Ссылка атрибуции](#attribution-link-tab) имеется слайдер окна атрибуции по просмотрам.

<div id="default-postbacks" />

#### Постбэки по умолчанию

Определите источник пользователей для автоматической отправки партнерам постбэков о действиях пользователя, совершенных до запуска приложения:

* Для параметра **Установки** выберите один из следующих вариантов:
  * **Только этот партнер**: постбэки отправляются только в том случае, когда событие атрибутируется этому партнеру, то есть когда пользователь, установивший приложение, пришел от Bidease.
  * **Все медиа-источники и органический трафик**: постбэки отправляются для установок, атрибутированных любому партнеру, а также для органических событий, то есть когда пользователь, установивший приложение, пришел из любого медиа-источника.
* Для **отклоненных установок** и **повторных вовлечений:** постбэки отправляются только в Bidease.

<div id="in-app-event-postbacks" />

#### Постбэки по внутренним событиям приложений

При необходимости настройте окно **Постбэки по внутренним событиям приложения**(подробнее о<Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям"> настройке окна постбэков по внутренним событиям приложения</Anchor>).

Настройте сопоставление внутренних событий приложения с событиями Bidease, отправляемыми через постбэки:

1. Активируйте **Постбэки по внутренним событиям приложения**.
2. Чтобы добавить в список событие, определенное в SDK, или межсерверное событие, нажмите **Добавить событие**. В таблице ниже описаны поля, которые необходимо заполнить:

| Имя параметра | Описание |
| --- | --- |
| **Событие AppsFlyer** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<br />**Совет**: Не нашли здесь нужное событие?<ul><li>Убедитесь, что событие активировано на устройстве с неорганической установкой, и повторите поиск.</li><li>Введите его в поле **Событие AppsFlyer** и нажмите **Добавить другое**. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">сопоставлении пользовательских событий</Anchor> читайте здесь.</li></ul> |
| **для пользователей от** | Выберите вариант отправки для события.<ul><li>**Только события партнера**: постбэки отправляются только в том случае, когда событие атрибутируется к этому партнеру.</li><li>**Все медиа-источники и органический трафик**: отправляйте постбэки для событий, атрибутированных к любому партнеру, а также для органических событий.</li></ul> |
| **включая** | <ul><li>**Нет данных (по умолчанию)**: отправляет только само событие без значения.</li><li>**Значения и доход**: отправляет все параметры события, **включая** значение дохода (если оно есть в событии).</li><li>**Значения без дохода**: отправляет все параметры, **кроме** значения дохода.</li></ul> |

3. [Необязательно] Нажмите на значок **Добавить условие** <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">установить условия</Anchor> для события.
4. Нажмите **Сохранить интеграцию**.
5. [Необязательно] После сохранения интеграции, оставаясь на странице конфигурации, вы можете интегрировать с этим партнером другие свои приложения:
   1. В левом верхнем углу под именем партнера нажмите на название приложения, чтобы открыть список приложений.
   2. Выберите другое приложение из выпадающего списка.
   3. Повторите шаги по интеграции для выбранного приложения.

<div id="note-1" />

> 📘 **Примечание**
>
> **Только для приложений на iOS:** Ваш контроль над данными, передаваемыми партнеру через постбэки и <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">отчеты</Anchor>, зависит от состояния переключателя **Расширенная конфиденциальность (для iOS 14.5+ и более поздних версий)**<Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">.</Anchor>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Формируйте и сохраняйте ссылки атрибуции и отправляйте их партнеру, чтобы атрибутировать определенные кампании, группы объявлений и отдельные объявления — как для кампаний по привлечению пользователей, так и для ретаргетинговых кампаний. Вы можете использовать либо ссылку для конкретной платформы, либо <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">OneLink</Anchor>.   
<Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее о структуре и параметрах ссылок атрибуции</Anchor>.

**Чтобы создать ссылку атрибуции,** следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">этой инструкции</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

<Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-cost-and-revenue-data">Данные о затратах</Anchor> для Bidease недоступны.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

<Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution">Доход от рекламы</Anchor> недоступен для Bidease.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Выберите, какие <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">разрешения предоставить</Anchor> Bidease для доступа к вашим данным и выполнения различных действий.

<div id="note-2" />

> 📘 **Примечание**
>
> Когда интеграция <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">деактивирована</Anchor>, а переключатель Разрешения все еще включен, разрешения действуют.

</Accordion>

<div data-zendesk-anchors="setting-up-bidease=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-bidease h_01HF4ED4B5QHY92B03426260QY=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-bidease h_01HF4DWFAP55JRXTR8Z65YAR68=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HF4DWFAP4S45241VR1PJ3RFC=integration-tab activate-partner::b746d215=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HF4DWFAP9BS1G612WS5HNQ6S=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 advanced-privacy=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HF4DWFAQHEJATJG6DRVMKA34=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 transaction-id=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%82%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D0%B8 h_01HF4DWFAQ1Y1AVQ0EV63H5YJ1=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%82%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D0%B8 install-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA h_01HF4DWFAQQRR8XH5S7NW2NCB6=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HF4DWFAQG4YEEH3HMD61GEWE=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01HF4DWFAQQCM4TK3JJNMSM6RD=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01HF4DWFAQQ3C7GBA4Q4SA6G0Y=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01HF4DWFAQ9D9BV6PG4BEYX788=attribution-link-tab h_01HF4DWFAQT2PD4863N6EB7HHH=cost-tab h_01HF4DWFAQXMNDHWT0Y4C0M6EN=ad-revenue-tab h_01HF4DWFAQJWNFMFDEZ8XT0DM5=permissions-tab h_01HF4DWFAQJ9HRMD1FE717F1WK=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2" />

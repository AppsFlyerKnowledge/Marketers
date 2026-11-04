---
title: Настройка кампании Persona.ly RTB
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
  created_at: '2023-09-20T07:13:43Z'
  edited_at: '2026-08-19T00:25:45Z'
  id: 18699025653265
  locale: ru
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ru/articles/18699025653265
---
> **Краткий обзор.** Persona.ly RTB (personalyrtb\_int), интегрированный партнер AppsFlyer, — это платформа DSP, ориентированная на мобильные устройства и работающая по всему миру. Используя собственные алгоритмы биддеров и машинного обучения, Persona.ly предлагает прозрачные, ориентированные на производительность, специализированные решения для привлечения пользователей и ретаргетинга.

<Image alt="persona.ly_logo.png" src="https://files.readme.io/b0dacbdc4c2e884610a040b5049a1410a88214f8275320163764bcf09f90305b-18699636413969.png" width="234px" />

<div id="setting-up-personaly-rtb" />

## Настройка Persona.ly RTB

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В AppsFlyer в боковом меню выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. На вкладке **Интеграция** включите переключатель **Активировать партнера**.  
    **Примечание.** Этот переключатель должен быть <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активирован</Anchor> все время, пока вы работаете с этим партнером.
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

Интеграция с Persona.ly RTB поддерживает атрибуцию по кликам и просмотрам.  
Окно общей конфигурации содержит следующие вкладки: Интеграция, Ссылка атрибуции, Затраты, Доход от рекламы, Разрешения. Для Persona.ly RTB доступны следующие вкладки: Интеграция, Ссылка атрибуции и Разрешения.

<div id="note" />

> 📘 **Примечание**
>
> * Некоторые настройки отличаются для устройств iOS и Android
> * Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">настройке партнерских интеграций.</Anchor>

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке **Интеграция** есть ряд разделов, описанных ниже.

<div id="activate-partner" />

#### Активация партнера

Чтобы настроить интеграцию, необходимо сначала <Anchor target="_blank" href="/marketers/ru/docs/amazon-ads-campaign-configuration#активировать-партнера">включить</Anchor> переключатель **Активировать партнера**. Узнайте больше об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#активировать-интеграцию-партнера">активации и деактивации партнерских интеграций</Anchor>.

<div id="note-1" />

> 📘 **Примечание**
>
> Как сеть, ориентированная на все установки, Persona.ly RTB предпочитает получать постбэки для всех новых установок вашего приложения из любого источника. Рекомендуется выбрать вариант **Все медиа-источники и органический трафик** для передачи всех постбэков по установкам в Persona.ly RTB.

<div id="advanced-privacy" />

#### Расширенные настройки конфиденциальности

Только для приложений на iOS: Ваш контроль над данными, передаваемыми партнеру через постбэки и <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">отчеты</Anchor>, зависит от состояния переключателя **Расширенная конфиденциальность (для iOS 14.5+ и более поздних версий)**:

| Расширенная конфиденциальность включена | Расширенная конфиденциальность выключена |
| --- | --- |
| Постбэки отправляются только для событий, атрибутированных партнеру | Постбэки отправляются в соответствии с вашей настройкой:<ul><li>**Все медиа-источники и органический трафик**</li><li>**Только данный партнер**</li></ul> |
| Постбэки отправляются в соответствии с <Anchor target="_blank" href="/partners/ru/docs/advanced-privacy-guide-postback-macros-for-ad-networks">шаблоном Расширенная конфиденциальность</Anchor> |  |
| Партнеру передаются <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">агрегированные и анонимные данные</Anchor>, то есть данные на уровне пользователя (ID устройства) не передаются. |  |

<div id="transaction-id" />

#### Идентификатор транзакции

Только для приложений iOS: Когда переключатель **Предоставлять идентификатор транзакции SKAN** включен, вы разрешаете AppsFlyer <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">передавать идентификатор транзакции постбэков SKAdNetwork</Anchor> в Reddit. Таким образом, Reddit может декодировать ваши значения конверсии SKAdNetwork.

<div id="install-attribution" />

#### Атрибуция установок

Чтобы атрибутировать установки по просмотрам от Persona.ly RTB, включите опцию **Атрибуция установок по просмотрам**. На вкладке [Ссылка атрибуции](#attribution-link-tab) имеется слайдер окна атрибуции по просмотрам.

<div id="default-postbacks" />

#### Постбэки по умолчанию

Определите источник пользователей для автоматической отправки партнерам постбэков о действиях пользователя, совершенных до запуска приложения:

* Для параметра **Установки** выберите один из следующих вариантов:
  * **Только этот партнер**: постбэки отправляются только в том случае, когда событие атрибутируется этому партнеру, то есть когда пользователь, установивший приложение, пришел от Persona.ly RTB.
  * **Все медиа-источники, включая органические**: постбэки отправляются для установок, атрибутированных любому партнеру, а также для органических событий, то есть когда пользователь, установивший приложение, пришел из любого медиа-источника.
* Для **отклоненных установок** и **повторных вовлечений:** постбэки отправляются только в Persona.ly RTB.

<div id="in-app-event-postbacks" />

#### Постбэки по внутренним событиям приложений

Настройте сопоставление внутренних событий приложения с событиями Persona.ly RTB, отправляемыми через постбэки:

1. Активируйте **Постбэки по внутренним событиям приложения**.
2. Чтобы добавить в список событие, определенное в SDK, или межсерверное событие, нажмите **Добавить событие**. В таблице ниже описаны поля, которые необходимо заполнить:

| Имя параметра | Описание |
| --- | --- |
| **Событие AppsFlyer** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<br />**Совет**: Не нашли здесь нужное событие?<ul><li>Убедитесь, что событие активировано на устройстве с неорганической установкой, и повторите поиск.</li><li>Введите его в поле **Событие AppsFlyer** и нажмите **Добавить другое**. Подробнее о сопоставлении пользовательских событий <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">читайте здесь</Anchor>.</li></ul> |
| **сопоставлено с событием партнера** | Уникальное имя или идентификатор каждого события, определенные партнером. Возможны следующие настройки сопоставления:<ul><li>**Текстовое поле**. Введите в него соответствующий идентификатор события, полученный от партнера.</li><li>**Раскрывающийся список**. Выберите наиболее подходящее предопределенное событие AppsFlyer.</li><li>**Как есть**. События отправляются в исходном виде, без сопоставления названий.</li></ul> |
| **для пользователей от** | Выберите вариант отправки для события.<ul><li>**Только события партнера**: постбэки отправляются только в том случае, когда событие атрибутируется к этому партнеру.</li><li>**Все медиа-источники и органический трафик**: отправляйте постбэки для событий, атрибутированных к любому партнеру, а также для органических событий.</li></ul> |
| **включая** | <ul><li>**Нет данных (по умолчанию)**: отправляет только само событие без значения.</li><li>**Значения и доход**: отправляет все параметры события, **включая** значение дохода (если оно есть в событии).</li><li>**Значения без дохода**: отправляет все параметры, **кроме** значения дохода.</li></ul> |

3. [Необязательно] Нажмите на значок **Добавить условие** <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">установить условия</Anchor> для события.
4. При необходимости настройте окно **Постбэки по внутренним событиям приложения**(подробнее о<Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям"> настройке окна постбэков по внутренним событиям приложения</Anchor>).
5. Нажмите **Сохранить интеграцию**.
6. [Необязательно] После сохранения интеграции, оставаясь на странице конфигурации, вы можете интегрировать с этим партнером другие свои приложения:
   1. В левом верхнем углу под именем партнера нажмите на название приложения, чтобы открыть список приложений.
   2. Выберите другое приложение из выпадающего списка.
   3. Повторите <Anchor target="_blank" href="/marketers/ru/docs/amazon-ads-campaign-configuration#integration-tab">шаги по интеграции</Anchor> для выбранного приложения.

<div id="note-2" />

> 📘 **Примечание**
>
> Только для приложений на iOS: Ваш контроль над данными, передаваемыми партнеру через постбэки и <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">отчеты</Anchor>, зависит от состояния переключателя **Расширенная конфиденциальность (для iOS 14.5+ и более поздних версий)**<Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">.</Anchor>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Формируйте и сохраняйте ссылки атрибуции и отправляйте их партнеру, чтобы атрибутировать определенные кампании, группы объявлений и отдельные объявления — как для кампаний по привлечению пользователей, так и для ретаргетинговых кампаний. Вы можете использовать либо ссылку для конкретной платформы, либо <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее о структуре и параметрах ссылок атрибуции</Anchor>. **Чтобы сформировать ссылку атрибуции,** следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">этим инструкциям</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

AppsFlyer получает информацию о затратах через API. Подробную информацию <Anchor target="_blank" href="/marketers/ru/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">о поддерживаемых параметрах, метриках и функциях см. в</Anchor> таблице интеграции затрат рекламной сети. **Примечание**. Для получения сведений о затратах требуется подписка ROI360.

**Чтобы включить API данных о затратах**:

* Следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">этим инструкциям по интеграции</Anchor>.

<Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#статус-api-затрат">Просмотрите статус вашего API данных о затратах</Anchor> и время, когда AppsFlyer получил соответствующие данные о затратах в последний раз, либо на дэшборде статуса интеграции затрат (и доходов от рекламы), либо на дэшборде отдельной рекламной сети.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы недоступен для Persona.ly RTB.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Выберите, какие <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">разрешения предоставить</Anchor> Persona.ly RTB для доступа к вашим данным и выполнения различных действий.

<div id="note-3" />

> 📘 **Примечание**
>
> Когда интеграция <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">деактивирована</Anchor>, а переключатель Разрешения все еще включен, разрешения действуют.

</Accordion>

<div data-zendesk-anchors="setting-up-amazon-dsp-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-personaly-rtb 01H88VAJH3VENKYVRQY5RXN63P=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-personaly-rtb 01H88VAJH3BYZSXQGGZZJQ9N0C=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 01H88VAJH34GP7FK1KTJGRDPM7=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HBB9EEMJ55BQDJ1ZEJT136ZF=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 advanced-privacy=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 01H88VAJH3G5FAR7RRNDEPNGME=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 transaction-id=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%82%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D0%B8 h_01HARQDVEDA206D0BBXBC6WEHH=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%82%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D0%B8 install-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA h_01HA6PNN6RJYTNXRAS3M9EA4M4=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E 01H88VAJH3WE9Z0971WMBRBJRS=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 01H88VAJH3AS37MVF75GANWX4B=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 01H88VAJH36MYZ9W1YPWA92Z1Z=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-3" />

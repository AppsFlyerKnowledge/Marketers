---
title: Конфигурация кампании Awin
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
  created_at: '2023-09-13T11:50:38Z'
  edited_at: '2026-09-12T00:23:15Z'
  id: 18532554968849
  locale: ru
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ru/articles/18532554968849
---
> **Краткий обзор:** Awin (affiliatewindow\_int) – интегрированный партнёр, который позволяет рекламодателям запускать кампании по UA и ретаргетингу. Маркетинговая платформа Awin помогает объединять продавцов (рекламодателей) с партнёрами-аффилиатами (издателями).

![awin icon.png](https://files.readme.io/2a7f22084586fec820c0bfab7f3a256259c43d37f14d6fed8e8db3d2e9905947-18533392495377.png)

<div id="activate-partner" />

## Активация партнёра

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции. Этот переключатель **обязательно** должен быть включен все время, пока вы работаете с партнером.  
    Дополнительная информация по активации партнеров: нажмите <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="setting-up-awin" />

## Настройка Awin

Интеграция с Awin поддерживает атрибуцию по кликам.

Окно конфигурации включает следующие вкладки: Интеграция, Ссылка атрибуции, Стоимость, Доход от рекламы и Разрешения. Для Awin доступны следующие вкладки: Интеграция, Ссылка атрибуции и Разрешения.

<div id="note" />

> 📘 **Примечание**
>
> * Некоторые настройки отличаются для устройств iOS и Android.
> * Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">настройке партнерских интеграций.</Anchor>

<div id="prerequisite" />

### Необходимое условие

Перед настройкой интеграции убедитесь, что в SDK реализованы необходимые параметры «группа комиссий», как указано в <Anchor target="_blank" href="https://help.awin.com/docs/appsflyer">документации Awin</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке **Интеграция** есть ряд разделов, описанных ниже.

<div id="activate-partner-1" />

#### Активировать партнера

Чтобы настроить интеграцию, необходимо сначала <Anchor target="_blank" href="/marketers/ru/docs/amazon-ads-campaign-configuration#активировать-партнера">включить</Anchor> переключатель **Активировать партнёра**. Узнайте больше об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#активировать-интеграцию-партнера">активации и деактивации партнерских интеграций</Anchor>.. Для получения дополнительной информации перейдите на <Anchor target="_blank" href="https://developer.awin.com/docs/appsflyer">страницу интеграции Awin</Anchor>.

<div id="advanced-privacy" />

#### Расширенные настройки конфиденциальности

Только для приложений на iOS: Ваш контроль над данными, которыми вы делитесь с партнером посредством постбэков и <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">отчетов</Anchor>, зависит от положения переключателя **«Расширенная конфиденциальность» (для iOS 14.5+ и более поздних версий)**.

| Расширенные настройки конфиденциальности: Вкл. | Расширенные настройки конфиденциальности: Откл. |
| --- | --- |
| Постбэки отправляются только для событий, атрибутированных партнеру | Постбэки отправляются в соответствии с вашей настройкой:<ul><li>**Все медиаисточники и органический трафик**</li><li>**Только данный партнер**</li></ul> |
| Постбэки отправляются в соответствии с <Anchor target="_blank" href="/partners/ru/docs/advanced-privacy-guide-postback-macros-for-ad-networks">шаблоном Расширенная конфиденциальность</Anchor>. |  |
| Партнеру передаются <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">агрегированные и анонимные данные</Anchor>, то есть данные на уровне пользователя (ID устройства) не передаются. |  |

<div id="general-settings" />

#### Общие настройки

**Идентификатор рекламодателя Awin**

Добавьте свой идентификатор продавца Awin.

<div id="note-1" />

> 📘 **Примечание**
>
> Идентификатор рекламодателя идентифицирует ваш аккаунт рекламодателя на стороне партнера и необходим для атрибуции AppsFlyer и постбэков. Идентификатор должен присутствовать в ссылке атрибуции.

<div id="default-postbacks" />

#### Постбэки по умолчанию

Постбэки по установкам отправляются только этому партнеру.

<div id="in-app-event-settings" />

#### Настройки внутренних событий приложения

**Идентификатор рекламодателя Awin**

Добавьте свой идентификатор продавца Awin.

<div id="in-app-event-postbacks" />

#### Постбэки событий внутри приложения

Настройте сопоставление внутренних событий приложения с событиями Awin, отправляемыми через постбэки:

1. Активируйте **Постбэки событий внутри приложения**.
2. Чтобы добавить в список событие, определенное в SDK, или межсерверное событие, нажмите **Добавить событие**. В таблице ниже описаны поля, которые необходимо заполнить:

| Название параметра | Описание |
| --- | --- |
| **Событие AppsFlyer** | Название события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<br />**Совет**: Не нашли здесь нужное событие?<ul><li>Убедитесь, что событие активировано на устройстве с неорганической установкой, и повторите поиск.</li><li>Введите его в поле **Событие AppsFlyer** и нажмите **Создать пользовательское**. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">сопоставлении пользовательских событий</Anchor>.</li></ul> |
| **сопоставлено с событием партнёра** | Уникальное имя или идентификатор каждого события, определенные партнером. Возможны следующие настройки сопоставления:<ul><li>**Текстовое поле:** Получите соответствующий идентификатор события от партнера.</li><li>**Раскрывающийся список:** Выберите наиболее подходящее предопределённое событие AppsFlyer.</li><li>**Как есть**: События отправляются в исходном виде, без сопоставления названий.</li></ul> |
| **для пользователей от** | **Только этот партнер:** Отправлять постбэки событий внутри приложения можно только если событие атрибутировано этому партнёру — то есть пользователь, совершивший его, пришёл от данного партнёра. |
| **включая** | <ul><li>**Без данных (по умолчанию)**: Отправлять только само событие без каких-либо значений.</li><li>**Значения и доход**: Отправьте все параметры события, **включая** ценность, значение выручки (если оно присутствует в событии).</li><li>**Значения без выручки**: Отправьте все параметры, **кроме** значения выручки.</li></ul> |

3. [Необязательно] Нажмите иконку **Добавить условие**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">установить условия</Anchor> для события.
4. Если требуется, установите **Окно постбэков по внутренним событиям** (подробнее о <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">настройке окна постбэков по внутренним событиям</Anchor>).
5. Нажмите **Сохранить интеграцию**.
6. [Необязательно] После сохранения интеграции, оставаясь на странице конфигурации, вы можете интегрировать больше своих приложений с партнёром:
   1. В верхнем левом углу под именем партнёра нажмите на название приложения, чтобы открыть список приложений.
   2. Выберите другое приложение из раскрывающегося списка.
   3. Повторите <Anchor target="_blank" href="/marketers/ru/docs/amazon-ads-campaign-configuration#integration-tab">шаги интеграции</Anchor> для выбранного приложения.

<div id="note-2" />

> 📘 **Примечание**
>
> Только для приложений на iOS: Ваш контроль над данными, которыми вы делитесь с партнером посредством постбэков и <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">отчетов</Anchor>, зависит от<Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">состояния переключателя</Anchor> **«Расширенная конфиденциальность» (для iOS 14.5+ и более поздних версий)**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Сгенерируйте и сохраните ссылки атрибуции и отправьте их партнеру, чтобы атрибутировать определенные кампании, блоки объявлений и отдельные объявления — как для кампаний по привлечению пользователей, так и для кампаний ретаргетинга. Вы можете использовать либо ссылку для конкретной платформы, либо <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее о структуре и параметрах ссылок атрибуции</Anchor>. **Чтобы создать ссылку атрибуции,** следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">этой инструкции</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о затратах недоступны для Awin.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы недоступен для Awin.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Выберите, какие разрешения предоставить Awin для доступа к вашим данным и выполнения различных действий.

<div id="note-3" />

> 📘 **Примечание**
>
> * Если интеграция <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">деактивирована</Anchor>, а переключатель «Разрешения» всё ещё включён, разрешения остаются в силе.
> * См. дополнительные сведения о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">предоставлении разрешений</Anchor>.

</Accordion>

<div id="deep-linking-and-deferred-deep-linking-using-onelink" />

## Диплинкинг и отложенный диплинкинг с помощью OneLink

AWIN оборачивает каждую ссылку, размещённую на их платформе, чтобы предоставлять клиентам аналитические данные AWIN оборачивает каждую ссылку, размещённую на их платформе, чтобы предоставлять клиентам аналитические данные Это означает, что перед тем как отправить пользователя к конечному адресу, ссылка сначала будет переадресована на сайт AWIN. AWIN оборачивает каждую ссылку, размещённую на их платформе, чтобы предоставлять клиентам аналитические данные Это означает, что перед тем как отправить пользователя к конечному адресу, ссылка сначала будет переадресована на сайт AWIN. <Anchor target="_blank" href="https://www.appsflyer.com/ru/blog/mobile-marketing/universal-links-app-links/">Узнайте больше об упаковывании ссылок</Anchor>.  
Платформа AWIN поддерживает схему URI, но **не поддерживает** обработку методов диплинкинга — iOS Universal Links и Android App Links. Это относится к любой ссылке, используемой в AWIN.

Для диплинкинга с помощью OneLink на AWIN:

* <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">Настройте OneLink URL с помощью схемы URI</Anchor>

<div id="note-4" />

> 📘 **Примечание:**
>
> Для приложений iOS используйте параметр `af_force_deeplink=true` в OneLink URL, чтобы активировать <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">схему URI</Anchor> глубокой ссылки.

<div data-zendesk-anchors="activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0 01H88VAJH3B5ESK12D3ATMMVZ8=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0 setting-up-amazon-dsp-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-awin 01H88VAJH3VENKYVRQY5RXN63P=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-awin 01H88VAJH3BYZSXQGGZZJQ9N0C=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 prerequisite=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 h_01HFPEEW4FXS9AFQTTEF2ZBDZW=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 01H88VAJH34GP7FK1KTJGRDPM7=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 advanced-privacy=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 01H88VAJH3G5FAR7RRNDEPNGME=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 01H88VAJH3F2FJK5YP3M2V7RWD=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01K4VVB00RYB0XRANWQ29M6P36=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E 01H88VAJH3WE9Z0971WMBRBJRS=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HA77JYAR06HA5FZGSRQJATHF=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F inapp-event-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F 01H88VAJH3AS37MVF75GANWX4B=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F 01H88VAJH36MYZ9W1YPWA92Z1Z=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-3 deep-linking-and-deferred-deep-linking-using-onelink=%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3-%D0%B8-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D1%8B%D0%B9-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink h_01HA77Q9RWZ3FRE5KEN854ZZ78=%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3-%D0%B8-%D0%BE%D1%82%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%BD%D1%8B%D0%B9-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink h_01HA78QWQVXEWHPEQE6XWBB64M=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-4" />

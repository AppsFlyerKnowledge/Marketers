---
title: Партнеры по постбэку Google Ads — конфигурация
metadata:
  keywords:
    - postbacks
    - Integration
    - Advertisers
    - Agencies
    - google ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-16T09:36:56Z'
  edited_at: '2026-10-19T14:25:57Z'
  id: 4411047077905
  locale: ru
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ru/articles/4411047077905
---
> **Кратко:** Включите партнеров по постбэку Google Ads, чтобы помогать запускать кампании Google Ads.

Некоторые партнеры (например, Bidalgo, Adquant), называемые **партнерами по постбэку Google Ads**, похожи на агентства. Они помогают своим клиентам-рекламодателям запускать кампании Google Ads, но для этого им необходимо получать постбэки по конверсиям Google Ads.

Эти партнеры по постбэку Google Ads (GAPP) также могут собирать постбэки по установкам Google Ads, привлеченным рекламодателем напрямую или даже другими агентствами (см. [кейсы](/docs/google-ads-postback-partners-configuration#варианты-использования-партнеров-по-постбэку-google-ads)). Используя информацию из постбэков, GAPP могут оптимизировать кампании Google Ads для приложения.

<div id="important" />

> 🚧 **Важно!**
>
> Партнерам по постбэку Google Ads **НЕ** атрибутируются установки или события в AppsFlyer.

Рекламодателю требуется активный аккаунт Google Ads, <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers">настроенный</Anchor> в AppsFlyer, а также настроенный в AppsFlyer конкретный GAPP, чтобы включить отправку ему постбэков.

Другие GAPP, интегрированные с AppsFlyer: Blackbox, Appreciate, Marin Software, Miramedia, Mpbisummer, Protonads, Springrain.

<div id="google-ads-postback-partner-setup" />

## Настройка партнера по постбэку Google Ads

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Активные интеграции**.

2. Введите в поле поиска имя GAPP, с которым вы хотите работать, и выберите его из раскрывающегося списка.

<div id="tip" />

> 👍 **Совет.**
>
> Введите "Google Ads" в поле поиска и нажмите Enter, чтобы получить список GAPP.

3. Нажмите нужный GAPP, чтобы открыть настройки его интеграции.

4. В аккаунте **Google Ads** скопируйте идентификатор клиента (без дефисов):

<Image align="center" alt="" src="https://files.readme.io/7afd536d06b1aca68744a83925ecac86fcef4cc47225826af20120f128da004f-21414601345681.png" />

5. Вставьте номер в поле **Google Ads Customer ID**.

6. Настройте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">раздел «Постбэк событий в приложении»</Anchor>.

7. Нажмите **Сохранить**.

<div id="important-notes" />

> 📘 **Важные примечания**
>
> * Если отключить атрибуцию для Google Ads, отправка постбэков в GAPP также прекратится.
> * Можно настроить несколько аккаунтов рекламы (CID) для отправки постбэков (шаг 5), разделяя каждый CID запятой.
>
>   ![zds_Agency_multiple.png](https://files.readme.io/36112b9a08ca1e6a2150523e1ec39eda5c28a4be826e9f776f5dbd7b1d0c5378-21414553418897.png)
> * Чтобы работать с несколькими GAPP, кампании для каждого GAPP следует запускать из отдельных аккаунтов Google. Если вы переключаетесь с одного GAPP на другой, обязательно отключите настройки первого GAPP в AppsFlyer.

<div id="google-ads-postback-partners-use-cases" />

## Варианты использования партнеров по постбэку Google Ads

<div id="use-case-1-advertiser-postbacks-only" />

<Accordion title="Кейс 1 — только постбэки рекламодателя">

Рекламодатель запускает кампании Google Ads и хочет, чтобы трафик из его аккаунтов Google Ads отправлялся в GAPP X.

1. Рекламодатель <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers">настраивает</Anchor> Google Ads
2. Рекламодатель [настраивает](/docs/google-ads-postback-partners-configuration#настройка-партнера-по-постбэку-google-ads) GAPP X — Google Ads

Рекламодатель должен ввести все свои CID (идентификаторы аккаунтов Ads) в настройках GAPP X — Google Ads.

</Accordion>

<div id="use-case-2-active-agency-with-advertiser-postbacks-only" />

<Accordion title="Кейс 2 — активное агентство, только постбэки рекламодателя">

И рекламодатель, и агентство запускают кампании Google Ads, но рекламодатель хочет, чтобы в GAPP X отправлялся только его трафик.

1. Рекламодатель <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers">настраивает</Anchor> Google Ads
2. Агентство <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-agencies">настраивает</Anchor> Google Ads (только для того, чтобы их трафик атрибутировался за ними как за агентством)
3. Рекламодатель [настраивает](/docs/google-ads-postback-partners-configuration#настройка-партнера-по-постбэку-google-ads) GAPP X — Google Ads

Рекламодатель должен ввести в конфигурации GAPP X — Google Ads ТОЛЬКО свои CID.

</Accordion>

<div id="use-case-3-active-advertiser-with-agency-postbacks-only" />

<Accordion title="Кейс 3 — активный рекламодатель, только постбэки агентства">

Рекламодатель и агентство запускают кампании Google Ads, а агентство хочет, чтобы в GAPP X отправлялся только его трафик.

1. Рекламодатель <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers">настраивает</Anchor> Google Ads
2. Агентство <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-agencies">настраивает</Anchor> Google Ads
3. Агентство [настраивает](/docs/google-ads-postback-partners-configuration#настройка-партнера-по-постбэку-google-ads) GAPP X — Google Ads

Агентство должно ввести в настройках GAPP X — Google Ads ТОЛЬКО свои CID

</Accordion>

<div id="use-case-4-advertiser-agency-postbacks" />

<Accordion title="Кейс 4 — постбэки рекламодателя & агентства">

Рекламодатель и агентство запускают кампании Google Ads, и оба хотят, чтобы их трафик отправлялся в GAPP X.

1. Рекламодатель <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers">настраивает</Anchor> Google Ads
2. Агентство <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-agencies">настраивает</Anchor> Google Ads
3. Рекламодатель [настраивает](/docs/google-ads-postback-partners-configuration#настройка-партнера-по-постбэку-google-ads) GAPP X — Google Ads для своих CID
4. Агентство [настраивает](/docs/google-ads-postback-partners-configuration#настройка-партнера-по-постбэку-google-ads) GAPP X — Google Ads для своих CID

Обратите внимание: у рекламодателя и агентства должны быть разные CID.

</Accordion>

<div id="available-parameters-for-gapps" />

## Доступные параметры для GAPPs

**Содержимое постбэков зависит от исходной интеграции GAPP с AppsFlyer** и не связано с какими-либо настройками рекламодателя. Поэтому у любых двух GAPP могут быть по-разному определены параметры постбэка.

Например, `campaign type`, `city`, `carrier` и `ad_type` — это параметры, которые могут присутствовать или отсутствовать в постбэке любого GAPP.

Есть два источника параметров постбэка GAPP:

1. **Макросы AppsFlyer** — чтобы получить подробную информацию обо всех макросах, доступных в постбэках AppsFlyer, нажмите <Anchor target="_blank" href="/partners/ru/docs/postback-macros-for-ad-networks">here</Anchor>.
2. **Ответ Google** — для каждой установки, атрибутированной Google Ads, AppsFlyer получает соответствующую информацию от Google. Ниже приведены параметры, доступные в постбэках GAPP и получаемые AppsFlyer от Google Ads (подробные описания параметров см. <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs#sample_responses">здесь</Anchor>)
   * Идентификатор ID событий рекламы
   * Строка
   * Название кампании
   * Тип кампании
   * Внешний идентификатор клиента (CID)
   * Тип сети
   * Подтип сети
   * Информация об устройстве
   * Идентификатор ID видео
   * Идентификатор группы объявлений
   * Идентификатор креатива
   * Ключевое слово
   * Тип сопоставления
   * Идентификатор источника
   * Тип взаимодействия
   * Тип рекламы
   * Метрика конверсии
   * Местоположение:

<div id="note" />

> 📘 **Примечание:**
>
> Доступная информация основана исключительно на данных, которые Google отправляет в AppsFlyer. Если Google по какой-либо причине не отправляет информацию об установке, AppsFlyer не может передать ее в GAPP.

<div data-zendesk-anchors="h_01HKA1HTJ4VW4YRXMSVG7WBTJM=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE google-ads-postback-partner-setup=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-%D0%BF%D0%BE-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D1%83-google-ads h_01HKA1HTJ5BE5EVQJ2T9HSHKQC=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-%D0%BF%D0%BE-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D1%83-google-ads h_01HKA1HTJ5BJTTS15QC44M63B2=%D1%81%D0%BE%D0%B2%D0%B5%D1%82 h_01HKA1HTJ5KSD1CVJ4FKDSATJX=%D0%B2%D0%B0%D0%B6%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D1%8F google-ads-postback-partners-use-cases=%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82%D1%8B-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D1%83-google-ads h_01HKA1HTJ5DX0Z2ZCGX07EX15F=%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82%D1%8B-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D1%83-google-ads h_01HKA1HTJ5T2XJJ4M9YZ1S52SF=use-case-1-advertiser-postbacks-only h_01HKA1HTJ5EFADYE33NQVP1NBQ=use-case-2-active-agency-with-advertiser-postbacks-only h_01HKA1HTJ5H4KK2M94QY0VFRSA=use-case-3-active-advertiser-with-agency-postbacks-only h_01HKA1HTJ537CYXEBQRCV5FSPK=use-case-4-advertiser-agency-postbacks available-parameters-for-gapps=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B4%D0%BB%D1%8F-gapps h_01HKA1HTJ5H0SXEMBVB6K2EZ91=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B4%D0%BB%D1%8F-gapps h_01HKA1HTJ55XWMX90KSYTGFB6C=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5" />

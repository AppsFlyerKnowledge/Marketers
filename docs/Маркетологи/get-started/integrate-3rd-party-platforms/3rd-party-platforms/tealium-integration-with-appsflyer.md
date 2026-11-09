---
title: Интеграция Tealium c AppsFlyer
metadata:
  keywords:
    - Marketers
    - TEST ID LOC
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-22T16:09:24Z'
  edited_at: '2026-08-18T00:12:51Z'
  id: 10820404821393
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/10820404821393
---
> **Краткий обзор.** Tealium, платформа данных о клиентах (CDP), объединяет данные о клиентах в интернете, на мобильных устройствах, в интернете вещей и вне сети. Узнайте, как автоматически обмениваться данными о конверсиях с помощью Tealium.

<Image align="center" alt="Tealium_icon.png" src="https://files.readme.io/e3cc1f95e8ce2de6fa83df63ff78dd4f4f76aebe1acb8e9378aa5b6aa4134364-10820461521681.png" width="276px" />

<div id="overview" />

## Обзор

Благодаря интеграции Tealium с AppsFlyer мобильные клиенты могут учитываться через SDK AppsFlyer для мобильной атрибуции, и данные атрибуции о конверсиях будут отправляться непосредственно в профиль Tealium AudienceStream.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам.  Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.

<div id="setting-up-tealium" />

## Настройка Tealium

Вы можете выбрать один из следующих способов интеграции Tealium с AppsFlyer:

* Интеграция на стороне клиента
* Интеграция на стороне сервера

<div id="client-side-integration" />

### Интеграция на стороне клиента

Используйте удаленные команды для библиотек iOS и Android, которые позволяют запускать нативный код в SDK AppsFlyer.

**Чтобы интегрировать Tealium с помощью интеграции на стороне клиента:**

* Следуйте <Anchor target="_blank" href="https://docs.tealium.com/platforms/remote-commands/integrations/appsflyer/">руководству по интеграции с помощью удаленных команд</Anchor>

<div id="server-side-integration" />

### Интеграция на стороне сервера

Настройте коннектор AppsFlyer App Events в аккаунте Customer Data Hub  для передачи данных между Tealium и AppsFlyer в режиме реального времени.

**Чтобы интегрировать Tealium с помощью интеграции на стороне сервера:**

* Следуйте руководству по <Anchor target="_blank" href="https://docs.tealium.com/server-side-connectors/appsflyer-app-events-connector/">коннектору AppsFlyer App Events.</Anchor>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01H9HWK1ACY09ZVD7WHEQR4MR3=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01H9HWK1ACA6A743PDY3Q1Y0KV=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-tealium=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-tealium h_01H9HWK1AC27GPZPZR13SFC3GM=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-tealium clientside-integration=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%BD%D0%B0-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%B5-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0 h_01H9HWK1ACH6K0FDTVCHAPSKME=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%BD%D0%B0-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%B5-%D0%BA%D0%BB%D0%B8%D0%B5%D0%BD%D1%82%D0%B0 serverside-integration=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%BD%D0%B0-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%B5-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0 h_01H9HWK1ACDZQEYVRZ7QWQ4KY3=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%BD%D0%B0-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%B5-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0" />

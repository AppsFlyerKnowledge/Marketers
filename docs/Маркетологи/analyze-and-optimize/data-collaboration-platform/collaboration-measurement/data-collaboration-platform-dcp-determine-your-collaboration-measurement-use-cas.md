---
title: >-
  Платформа для совместной работы с данными (DCP) — определите свой кейс для
  совместного измерения
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-02-25T15:52:06Z'
  edited_at: '2026-08-27T00:05:55Z'
  id: 32964487756561
  locale: ru
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ru/articles/32964487756561
---
> **Кратко:** Определите свой сценарий совместной работы, убедившись, что вы знаете, какие данные нужно предоставить, кто за них отвечает и в каком формате их отправлять.

## Информация о компании

DCP поддерживает различные кейсы для сценариев on-site и off-site. Для каждого кейса требуется отдельная настройка, которая определяет, какой участник совместной работы отвечает за подготовку каждого источника данных и в каком формате должны быть настроены данные.

Эта статья поможет Commerce Media Networks (CMN) и рекламодателям (брендам) определить, какой кейс им подходит. После того как подходящий кейс определен, владелец совместной работы может назначить соответствующим участникам необходимые задачи по подготовке и настройке (подробнее о назначении задач см.: <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configuration-task-assignment">Назначить задачу настройки</Anchor>.)

Здесь в дело вступает дерево решений по кейсам. Оно служит структурированным руководством, которое помогает вам определить свой кейс и получить соответствующие инструкции по подготовке.

## Как дерево решений помогает?

В зависимости от настройки одному участнику совместной работы может потребоваться подготовить и настроить задачи по конверсиям и кампаниям, а другой может отвечать за подготовку задач по вовлеченности или медиапартнерам. Дерево решений помогает владельцу совместной работы определить, какому участнику следует назначить каждую задачу, и предоставляет ссылки на соответствующие инструкции.

### Какое дерево решений мне нужно: onsite или offsite?

Можно использовать два дерева решений: одно для on-site-кампаний, другое — для off-site-кампаний. Чтобы определить, какое дерево решений подходит, учитывайте, где **показывается реклама** и где **происходит конверсия**.

* Используйте [дерево решений для off-site-кампаний](#дерево-решений-для-кампаний-вне-сайта) если реклама показывается на внешней рекламной платформе (например, Facebook, Google) вне ваших собственных ресурсов.
* Используйте [дерево решений для on-site-кампаний](#дерево-решений-для-on-site-кампаний) если реклама показывается в рамках вашей экосистемы, а конверсия происходит на вашей платформе.

## Дерево решений для on-site-кампаний

В сценарии on-site-кампании конверсия происходит на платформе, принадлежащей CMN или рекламодателю и управляемой ими. Отсюда следует первый вопрос в дереве решений для on-site-сценария: на какой платформе происходит конверсия — на платформе CMN или рекламодателя?

Ответьте на первый вопрос, выбрав правильный вариант ответа, и продолжайте раскрывать ветви, соответствующие вашим условиям.

#### **На какой платформе происходит конверсия?**

<div id="the-conversions-take-place-on-the-cmn-platform" />

<Accordion title="Конверсии происходят на платформе CMN">

<div id="the-cmn-platform-is-an-app" />

<Accordion title="Платформа CMN — это приложение">

Если платформа CMN — это приложение, следуйте приведенным ниже инструкциям для каждого типа данных:

| Выручка | Подготовлено и настроено по | Узнать как подготовиться | Узнать как настроить |
| --- | --- | --- | --- |
| Кампании | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи кампаний</Anchor></li></ul> |
| Конверсии | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсий</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Событие конверсии in-app</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи конверсий на сайте</Anchor></li></ul> |
| Типы взаимодействия | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Источник вовлечения</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Событие вовлеченности in-app</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-engagements-task">Конфигурация задачи вовлеченности</Anchor></li></ul> |
| Окна атрибуции | CMN/рекламодатель | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Конфигурация задачи окна атрибуции</Anchor></li></ul> |

</Accordion>

**ИЛИ**

<div id="the-cmn-platform-is-a-website" />

<Accordion title="Платформа CMN — это веб-сайт">

Если платформа CMN — веб-сайт, следуйте приведенным ниже инструкциям для каждого типа данных:

| Выручка | Подготовлено и настроено | Узнать как подготовиться | Узнать как настроить |
| --- | --- | --- | --- |
| Кампании | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи кампаний</Anchor></li></ul> |
| Конверсии | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсий</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи конверсий на сайте</Anchor></li></ul> |
| Типы взаимодействия | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Источник вовлечения</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-engagements-task">Настройка задачи по вовлеченности</Anchor></li></ul> |
| Окна атрибуции | CMN/рекламодатель | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Настройка задачи окон атрибуции</Anchor></li></ul> |

</Accordion>

</Accordion>

**ИЛИ**

<div id="the-conversions-take-place-on-the-advertiser-platform" />

<Accordion title="Конверсии происходят на платформе рекламодателя">

<div id="the-advertiser-platform-is-an-app" />

<Accordion title="Платформа рекламодателя — приложение">

Если платформа рекламодателя — приложение, следуйте приведенным ниже инструкциям для каждого типа данных:

| Выручка | Подготовлено и настроено по | Обучение подготовке | Обучение настройке |
| --- | --- | --- | --- |
| Кампании | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Настройка задачи кампаний</Anchor></li></ul> |
| Конверсии | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсий</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Событие конверсии в приложении</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Настройка задачи конверсии на сайте</Anchor></li></ul> |
| Типы взаимодействия | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Источник вовлечения</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Событие вовлеченности в приложении</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-engagements-task">Настройка задачи по вовлеченности</Anchor></li></ul> |
| Окна атрибуции | CMN/рекламодатель | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Настройка задачи окон атрибуции</Anchor></li></ul> |

</Accordion>

**ИЛИ**

<div id="the-advertiser-platform-is-a-website" />

<Accordion title="Платформа рекламодателя — веб-сайт">

Если платформа рекламодателя — веб-сайт, следуйте приведенным ниже инструкциям для каждого типа данных:

| Выручка | Подготовлено и настроено по | Обучение подготовке | Узнайте, как настроить |
| --- | --- | --- | --- |
| Кампании | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи «Кампании»</Anchor></li></ul> |
| Конверсии | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсий</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи «Конверсии на сайте»</Anchor></li></ul> |
| Типы взаимодействия | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Источник вовлеченности</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-engagements-task">Конфигурация задачи «Вовлеченность»</Anchor></li></ul> |
| Окна атрибуции | CMN/рекламодатель | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Конфигурация задачи «Окна атрибуции»</Anchor></li></ul> |

</Accordion>

</Accordion>

## Дерево решений для кампаний вне сайта

В сценарии внешней кампании рекламное объявление показывается на внешней рекламной платформе, такой как Facebook или Google. Это приводит к первому вопросу в дереве решений для внешней кампании: какая учетная запись на внешней рекламной платформе используется для показа рекламного объявления — CMN или рекламодателя?

Ответьте на первый вопрос, выбрав правильный ответ, а затем продолжайте раскрывать ветви, соответствующие вашим конкретным условиям.

#### **Какая учетная запись на внешней платформе используется для показа рекламного объявления?**

<div id="the-cmn-external-platform-account" />

<Accordion title="Учетная запись CMN на внешней платформе используется для показа рекламного объявления">

<div id="the-conversions-take-place-on-the-cmn-platform::e7b94fc0" />

<Accordion title="Конверсии происходят на платформе CMN">

<div id="the-cmn-platform-is-an-app::76ead17" />

<Accordion title="Платформа CMN — это приложение">

Если платформа CMN — это приложение, следуйте приведенным ниже инструкциям для каждой задачи:

| Выручка | Подготовлено и настроено по | Узнайте, как подготовить | Узнайте, как настроить |
| --- | --- | --- | --- |
| Конверсии | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсий</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">In-app событие конверсии</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи «Конверсии на сайте»</Anchor></li></ul> |
| Кампании | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник сопоставления кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи «Кампании»</Anchor></li></ul> |
| Медиапартнёры | CMN | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Конфигурация задачи «Медиапартнеры»</Anchor></li></ul> |
| Окна атрибуции | CMN/рекламодатель | Не относится | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Конфигурация окон ретроспективного обзора</Anchor></li></ul> |

</Accordion>

**ИЛИ**

<div id="the-cmn-platform-is-a-website::5144f168" />

<Accordion title="Платформа CMN — это сайт">

Если платформа CMN — это сайт, следуйте приведенным ниже инструкциям для каждой задачи:

| Выручка | Подготовлено и настроено по | Узнайте, как подготовить | Узнайте, как настроить |
| --- | --- | --- | --- |
| Конверсии | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсии (пользовательский)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи «Конверсии на сайте»</Anchor></li></ul> |
| Кампании | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник сопоставления кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи «Кампании»</Anchor></li></ul> |
| Медиапартнёры | CMN | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Конфигурация задачи «Медиапартнеры»</Anchor></li></ul> |
| Окна атрибуции | CMN/рекламодатель | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Конфигурация окон ретроспективного обзора</Anchor></li></ul> |

</Accordion>

</Accordion>

**ИЛИ**

<div id="the-conversions-take-place-on-the-advertiser-platform::aa9e89bf" />

<Accordion title="Конверсии происходят на платформе рекламодателя">

<div id="the-advertiser-platform-is-an-app::d36436f5" />

<Accordion title="Платформа рекламодателя — это приложение">

Если платформа рекламодателя — это приложение, следуйте приведенным ниже инструкциям для каждой задачи:

| Выручка | Подготовлено и настроено | Узнайте, как подготовить | Узнайте, как настроить |
| --- | --- | --- | --- |
| Конверсии | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсий</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Конверсионное событие в приложении</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи On-site Conversions</Anchor></li></ul> |
| Кампании | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник сопоставления кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи «Кампании»</Anchor></li></ul> |
| Медиапартнёры | CMN | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Конфигурация задачи «Медиапартнёры»</Anchor></li></ul> |
| Окна атрибуции | CMN/Рекламодатель | Не относится | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Конфигурация окон ретроспективного анализа</Anchor></li></ul> |

</Accordion>

**ИЛИ**

<div id="the-advertiser-platform-is-a-website::b70163fb" />

<Accordion title="Платформа рекламодателя — это веб-сайт">

Если платформа рекламодателя — это веб-сайт, для каждой задачи следуйте инструкциям ниже:

| Выручка | Подготовлено и настроено | Узнайте, как подготовить | Узнайте, как настроить |
| --- | --- | --- | --- |
| Конверсии | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсии (пользовательский)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи On-site Conversions</Anchor></li></ul> |
| Кампании | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник сопоставления кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи «Кампании»</Anchor></li></ul> |
| Медиапартнёры | CMN | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Конфигурация задачи «Медиапартнёры»</Anchor></li></ul> |
| Окна атрибуции | CMN/Рекламодатель | Не относится | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Конфигурация окон ретроспективного анализа</Anchor></li></ul> |

</Accordion>

</Accordion>

</Accordion>

**ИЛИ**

<div id="the-advertisers-external-platform-account" />

<Accordion title="Аккаунт рекламодателя на внешней платформе отображает рекламу">

<div id="the-conversions-take-place-on-the-cmn-platform::7b0781d3" />

<Accordion title="Конверсии происходят на платформе CMN">

<div id="the-cmn-platform-is-an-app::413a6003" />

<Accordion title="Платформа CMN — это приложение">

Если платформа CMN — это приложение, следуйте приведенным ниже инструкциям для каждой задачи:

| Выручка | Подготовлено и настроено | Узнайте, как подготовить | Узнайте, как настроить |
| --- | --- | --- | --- |
| Конверсии | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсий</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Событие конверсии в приложении</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи конверсий на сайте</Anchor></li></ul> |
| Кампании | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник сопоставления кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи кампаний</Anchor></li></ul> |
| Медиапартнёры | Рекламодатели | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Конфигурация задачи медиа-партнеров</Anchor></li></ul> |
| Окна атрибуции | CMN/рекламодатель | Не относится | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Конфигурация окна ретроспективного анализа</Anchor></li></ul> |

</Accordion>

**ИЛИ**

<div id="the-cmn-platform-is-a-website::95667666" />

<Accordion title="Платформа CMN — это веб-сайт">

Если платформа CMN — это веб-сайт, следуйте приведенным ниже инструкциям для каждой задачи:

| Выручка | Подготовлено и настроено | Узнайте, как подготовить | Узнайте, как настроить |
| --- | --- | --- | --- |
| Конверсии | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсии (пользовательский)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи конверсий на сайте</Anchor></li></ul> |
| Кампании | CMN | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник сопоставления кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи «Кампании»</Anchor></li></ul> |
| Медиапартнёры | Рекламодатели | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Конфигурация задачи «Медиапартнёры»</Anchor></li></ul> |
| Окна атрибуции | CMN | Нерелевантно | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Настройка окна ретроспективного анализа</Anchor></li></ul> |

</Accordion>

</Accordion>

**ИЛИ**

<div id="the-conversions-take-place-on-the-advertiser-platform::51470bc6" />

<Accordion title="Конверсии происходят на платформе рекламодателя">

<div id="h_01K3BAV1SP7RWP7K9TM7Y6MJVX" />

<Accordion title="Платформа рекламодателя — приложение">

Если платформа рекламодателя — приложение, следуйте приведенным ниже инструкциям для каждой задачи:

| Выручка | Подготовлено и настроено | Узнайте, как подготовить | Узнайте, как настроить |
| --- | --- | --- | --- |
| Конверсии | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсий</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Конверсия — in-app событие</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи «Конверсии на сайте»</Anchor></li></ul> |
| Кампании | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник сопоставления кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи «Кампании»</Anchor></li></ul> |
| Медиапартнёры | Рекламодатели | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Конфигурация задачи «Медиапартнёры»</Anchor></li></ul> |
| Окна атрибуции | CMN | Не относится | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Настройка окна ретроспективного анализа</Anchor></li></ul> |

</Accordion>

**ИЛИ**

<div id="the-advertiser-platform-is-a-website::8cb255ef" />

<Accordion title="Платформа рекламодателя — веб-сайт">

Если платформа рекламодателя — веб-сайт, следуйте приведенным ниже инструкциям для каждой задачи:

| Выручка | Подготовлено и настроено | Узнайте, как подготовить | Узнайте, как настроить |
| --- | --- | --- | --- |
| Конверсии | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Источник конверсии (пользовательский)</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task#настройте-конверсии-для-кампаний-на-площадке">Конфигурация задачи конверсий на сайте</Anchor></li></ul> |
| Кампании | Рекламодатели | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Источник сопоставления кампании</Anchor></li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Конфигурация задачи кампаний</Anchor></li></ul> |
| Медиапартнёры | Рекламодатели | Не применимо | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Конфигурация задачи медиа-партнеров</Anchor></li></ul> |
| Окна атрибуции | CMN | Не релевантно | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Конфигурация окон lookback</Anchor></li></ul> |

</Accordion>

</Accordion>

</Accordion>

<div data-zendesk-anchors="overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01JSKXR18RP691PT3Y5JGAJKF8=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 how-does-the-decision-tree-help=%D0%BA%D0%B0%D0%BA-%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BF%D0%BE%D0%BC%D0%BE%D0%B3%D0%B0%D0%B5%D1%82 h_01K3JR6NJ906S2HZC7YRWWFT2P=%D0%BA%D0%B0%D0%BA-%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BF%D0%BE%D0%BC%D0%BE%D0%B3%D0%B0%D0%B5%D1%82 which-decision-tree-do-i-need-onsite-or-offsite=%D0%BA%D0%B0%D0%BA%D0%BE%D0%B5-%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BC%D0%BD%D0%B5-%D0%BD%D1%83%D0%B6%D0%BD%D0%BE-onsite-%D0%B8%D0%BB%D0%B8-offsite h_01K3JR7AZFWJMTBZGAKYS4BFJS=%D0%BA%D0%B0%D0%BA%D0%BE%D0%B5-%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BC%D0%BD%D0%B5-%D0%BD%D1%83%D0%B6%D0%BD%D0%BE-onsite-%D0%B8%D0%BB%D0%B8-offsite the-onsite-use-case-decision-tree=%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-on-site-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 h_01JSKXR18R4A4WFPTQVB1DVV5Y=%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-on-site-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 on-which-platform-does-the-conversion-take-place=%D0%BD%D0%B0-%D0%BA%D0%B0%D0%BA%D0%BE%D0%B9-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5-%D0%BF%D1%80%D0%BE%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D0%B8%D1%82-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F h_01JSM17ZMGCF1FWQPM7T04C0MM=%D0%BD%D0%B0-%D0%BA%D0%B0%D0%BA%D0%BE%D0%B9-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5-%D0%BF%D1%80%D0%BE%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D0%B8%D1%82-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D1%8F h_01JSKXR18RTDSJ6W40D5JVFSS5=the-conversions-take-place-on-the-cmn-platform h_01JSKXR18R9A9MCZ7TPJHXWMBC=the-cmn-platform-is-an-app h_01JSKXR18RWSJTR5AKDBRGP0QS=the-cmn-platform-is-a-website h_01JSKXR18R083C5FY5FTESJDAZ=the-conversions-take-place-on-the-advertiser-platform h_01JSKXR18RH3SCQJRJA7QBVS6Y=the-advertiser-platform-is-an-app h_01JSKXR18R3N816VYJ4910VYGA=the-advertiser-platform-is-a-website the-offsite-use-case-decision-tree=%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2%D0%BD%D0%B5-%D1%81%D0%B0%D0%B9%D1%82%D0%B0 h_01JSKXR18R38YJZ2S410J4EH43=%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2%D0%BD%D0%B5-%D1%81%D0%B0%D0%B9%D1%82%D0%B0 which-account-on-the-external-platform-displays-the-ad=%D0%BA%D0%B0%D0%BA%D0%B0%D1%8F-%D1%83%D1%87%D0%B5%D1%82%D0%BD%D0%B0%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-%D0%BD%D0%B0-%D0%B2%D0%BD%D0%B5%D1%88%D0%BD%D0%B5%D0%B9-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D1%83%D0%B5%D1%82%D1%81%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F h_01JSM18A2R9015RWB05BE0YK7Q=%D0%BA%D0%B0%D0%BA%D0%B0%D1%8F-%D1%83%D1%87%D0%B5%D1%82%D0%BD%D0%B0%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-%D0%BD%D0%B0-%D0%B2%D0%BD%D0%B5%D1%88%D0%BD%D0%B5%D0%B9-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D1%83%D0%B5%D1%82%D1%81%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F h_01JSKXR18R4EKMWCYKFTBAEPH9=the-cmn-external-platform-account h_01JSKXR18RCKD3E841EQ2RC03B=the-conversions-take-place-on-the-cmn-platform::e7b94fc0 h_01JSKXR18R5115TP1BYE07TJ7V=the-cmn-platform-is-an-app::76ead17 h_01JSKXR18RCBGH6F8SNSRN2CJG=the-cmn-platform-is-a-website::5144f168 h_01JSKXR18RGQX77NM72G4WAC08=the-conversions-take-place-on-the-advertiser-platform::aa9e89bf h_01JSKXR18R61CTQ0VMRKD184VE=the-advertiser-platform-is-an-app::d36436f5 h_01JSKXR18RSQC7MCYZ5JE2VP3B=the-advertiser-platform-is-a-website::b70163fb h_01JSKXR18SYFX87XBSBNPJXAFA=the-advertisers-external-platform-account h_01JSKXR18S6TQMNW6PD65G67AQ=the-conversions-take-place-on-the-cmn-platform::7b0781d3 h_01JSKXR18SCDQXAN5NFQ1W17K2=the-cmn-platform-is-an-app::413a6003 h_01JSKXR18SDCDQX4SJ24ADZA18=the-cmn-platform-is-a-website::95667666 h_01JSKXR18S123PXD3FN2N11GCN=the-conversions-take-place-on-the-advertiser-platform::51470bc6 h_01JSKXR18STJV3GGW83123W7XC=the-advertiser-platform-is-a-website::8cb255ef" />

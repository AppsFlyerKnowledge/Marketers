---
title: Кроссплатформенные целевые страницы с использованием Smart Script
metadata:
  keywords:
    - CTV
    - Marketers
    - gaming
    - cross-platform
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2023-09-10T07:17:21Z'
  edited_at: '2026-08-18T00:22:38Z'
  id: 18440789126289
  locale: ru
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/ru/articles/18440789126289
---
> **Краткий обзор:** использовать кроссплатформенную целевую страницу с работающим Smart Script от AppsFlyer для выполнения атрибуция "из веба в Приложение". Это означает конвертацию пользователей, которые видят веб-реклама из любого медиа-источник, в пользователей приложений на CTV, ПК, консолях или мобильных платформах.

## Обзор

С помощью кроссплатформенной целевой страницы с работающим Smart Script от AppsFlyer вы можете выполнять атрибуция "из веба в Приложение". Это означает, что вы можете связывать установки на любой платформе с реклама, отображаемой в Интернете.

Умный скрипт на кроссплатформенной целевой странице использует входящую ссылка (ссылка на веб-реклама) для выполнения двух задач, которые обеспечивают атрибуция исходного медиа-источник и веб-реклама с установкой:

* Создайте кроссплатформенную ссылка OneLink, которая отправит показ в AppsFlyer.
* Создайте прямые ссылки атрибуция для каждого Приложение\/платформа.

## Настройка

#### ОБЪЕМ РАБОТ

| **Кто участвует**<ul><li>**Рекламодатель**:<ul><li>Определяет, что должны содержать исходящие [кроссплатформенные показы](#create-crossplatform-impression-link) и [прямые ссылки атрибуция](#create-direct-attribution-links) на основе <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#arguments">аргументов</Anchor> в скрипте. Это определяет данные атрибуция, которые добавляются к исходящему URL-адресу либо за счет манипуляции входящим URL-адресом, либо за счет задания определенных ценности, значения.</li><li>Обеспечивает, чтобывсе кампания, ведущие на веб-сайт, имели входящие URL-адреса с параметрами, которые скрипт может обработать.</li><li><Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Тестирует работа Smart Script</Anchor>.</li></ul></li><li>**Веб-разработчик**:<ul><li>Добавляет аргументы в скрипт и внедряет Smart Script на целевую страницу.</li><li>Тестирует Smart Script.</li></ul></li></ul> |
| --- |
| **Требования**<ul><li>Аккаунт в AppsFlyer с хотя бы одним Приложение.</li><li>Для URL-адреса показа: A Шаблон <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">OneLink</Anchor> с включенной кроссплатформенной атрибуцией.</li></ul> |

<div id="create-crossplatform-impression-link" />

<Accordion title="Создать кроссплатформенную ссылка показа">

**Чтобы создать кроссплатформенную ссылка OneLink, которая отправляет показ в AppsFlyer**:

1. Сопоставьте параметры входящей ссылки с параметрами, которые должна содержать ссылка показа (для медиа-источник, кампания, названия реклама и т. д.).
   * Узнать больше об <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#arguments">аргументах</Anchor> в скрипте, обрабатывающем входящий URL-адрес.
   * ценность, значение аргумента <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#arguments">OneLinkURL</Anchor> — это домен + идентификатор шаблона OneLink с включенной кроссплатформенной атрибуция.
2. Попросите вашего разработчика инициализировать аргументы Smart Script и вызвать метод Smart Script `generateOneLinkURL`. <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">Посмотрите демо и инструкции для разработчиков</Anchor>.  
   **Примечание:** Параметр `af_xplatform=true` необходим для включения межплатформенной атрибуции.

</Accordion>

<div id="create-direct-attribution-links" />

<Accordion title="Создайте прямые ссылки атрибуции">

1. Сопоставьте параметры входящей ссылки с параметрами, которые должны содержать исходящие прямые ссылки атрибуции (медиа-источник, кампания, название рекламы и т. д.). Узнайте больше об <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#arguments">аргументах</Anchor> в скрипте, обрабатывающем входящий URL-адрес.
2. Попросите вашего разработчика инициализировать аргументы Smart Script и запускать (программу) метод Smart Script , чтобы создать ссылку для каждой платформы/приложения. Посмотрите <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">демо</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/create-direct-click-url">инструкции</Anchor> для разработчиков.  
   **Примечание:** Разработчик должен добавить следующие параметры:  

| Параметр/Аргумент | Специфика | Запишите свои ответы (для использования вами или вашим разработчиком) |
| --- | --- | --- |
| platform | Строка описывает платформу и должна быть выбрана из этого списка:<ul><li>SmartCast</li><li>тизен</li><li>Roku</li><li>WebOS</li><li>VIDAA</li><li>PlayStation</li><li>Android</li><li>ios</li><li>Steam</li><li>Quest</li><li>battlenet</li><li>Native PC</li></ul> |  |
| app\_id (идентификатор приложения) | <ul><li>Время события</li><li>Пример: 123456</li></ul> |  |
| redirectURL | <ul><li>URL-адрес, на который следует перенаправить пользователя платформы/приложения.</li><li>Пример: `https://store.steampowered.com/app/123456/Team_Fortress_2/`</li></ul> |  |

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 01H8V0RV7X8JEVEJ36TJB1X43D=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 setup=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 01H8V0RV7X0K157JTDQMJSQYKF=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 scope-of-work=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D1%80%D0%B0%D0%B1%D0%BE%D1%82 h_01H95PGMNWPBRHSZBPMKNJ2PS6=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D1%80%D0%B0%D0%B1%D0%BE%D1%82 01H8EQ4KS75Q62Z7WVNSTDXBZX=create-crossplatform-impression-link 01H8EQ4KS7C6HADNKQZYNTTFMF=create-direct-attribution-links" />

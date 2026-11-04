---
title: Устранение неполадок Web SDK
metadata:
  keywords:
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2019-07-22T13:55:15Z'
  edited_at: '2026-08-31T00:23:23Z'
  id: 360002075858
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/360002075858
---
> **Кратко:** руководство по устранению неполадок AppsFlyer Web SDK, добавленного непосредственно на ваш сайт или реализованного через Google Tag Manager.

<div id="sdk-added-directly" />

## SDK, добавленный напрямую на сайт

Вы можете добавить SDK непосредственно на свой сайт.

<div id="no-data-or-partial-data-in-the-pba-dashboard" />

### Нет данных или отображаются только часть данных в дэшборде PBA

| Причина | РЕШЕНИЕ |
| --- | --- |
| После внедрения SDK данные могут отображаться в <Anchor target="_blank" href="/marketers/ru/docs/pba-website-attribution-dashboard">дэшбордах People-Based Analysis</Anchor> в течение 24 часов. | Подождите 24 часов. Если данные по-прежнему недоступны, см. дополнительные причины в этом документе. |
| Неверный веб-ключ разработчика | <ul><li>Web SDK использует веб-ключ разработчика для идентификации веб-событий, чтобы определить, какому бандлу следует атрибутировать данные.</li><li>Убедитесь, что вы используете <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working">правильный Web Dev Key.</Anchor></li></ul><Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings#add-brand-bundle">Страница бандла бренда</Anchor> |
| Вы разместили Web SDK в теле страницы | <ul><li>Вы можете разместить Web SDK в теле страницы, но это может повлиять на данные, отправляемые в AppsFlyer.</li><li>Рекомендуем разместить его в разделе head страницы.</li></ul> |
| Web SDK установлен не на всех страницах вашего сайта | Рекомендуем разместить веб-SDK на всех страницах вашего сайта. |

<div id="events-are-not-sent" />

### События не отправляются

| Причина | РЕШЕНИЕ |
| --- | --- |
| События отправляются до загрузки Web SDK. В таких случаях в консоли разработчика браузера отображается ошибка: `Uncaught ReferenceError: AF is not defined` | Убедитесь, что Web SDK загружается до кода, который отправляет события. |
| Неверный веб-ключ разработчика | <ul><li>Для PBA требуется веб-ключ разработчика, чтобы определить, какому бандлу следует атрибутировать данные. Убедитесь, что используется правильный web dev key.</li><li>Убедитесь, что вы используете <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working">правильный web dev key.</Anchor></li></ul> |
| Некорректно сформированные события | Убедитесь, что событие сформировано правильно.<br /><br />См. раздел <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">доступные параметры события</Anchor>, чтобы узнать больше о правильно сформированных событиях. |
| SDK вызван дважды |  |

<div id="conflicting-sdks-and-libraries" />

### Конфликтующие SDK и библиотеки

Многие веб-SDK используют популярные библиотеки JavaScript. Такие SDK также занимают имена в глобальной области видимости. Например, наш веб-SDK использует **AF** в качестве основного объекта, который обеспечивает работу веб-SDK.

* Если какой-либо SDK использует библиотеку X версии 1.2, а SDK AppsFlyer использует библиотеку X версии 2.1, эти две библиотеки могут конфликтовать.
* Если другой SDK или библиотека использует **AF** (в глобальной области видимости) как имя объекта, два SDK конфликтуют, и один SDK может переопределить другой.

<div id="sdk-added-using-google-tag-manager" />

## SDK, добавленный через Google Tag Manager

* Реализация веб-SDK с помощью Google Tag Manager (GTM) может сэкономить вам время.
* Вы можете внедрить его самостоятельно, не обращаясь к веб-разработчику для добавления на сайт.

Если у вас возникли проблемы. Помимо проблем, описанных в разделе [прямая реализация SDK](/docs/troubleshooting-the-web-sdk#sdk-добавленный-напрямую-на-сайт), возможны некоторые проблемы, характерные именно для GTM.

<div id="calling-the-sdk" />

### Вызов SDK

| Причина | РЕШЕНИЕ |
| --- | --- |
| <ul><li>В нашем руководстве по Web SDK показано, как добавить веб-SDK с помощью тега.</li></ul><ul><li>Некоторые пользователи при создании тегов для вызова событий настраивают тег так, чтобы он также повторно вызывал тег SDK. Но это может вызвать проблемы.</li></ul>![mceclip0.png](https://files.readme.io/77be12759c5ec5a04a517ee1b99109e8952b97d1d4280b71c51fa36304f5adbf-360003756558.png) | Лучше всего настроить один тег для загрузки SDK и запускать этот тег на всех страницах. Теги, которые отправляют события, не должны повторно вызывать тег SDK. |

<div id="tag-priority" />

### Приоритет тега

GTM позволяет <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">настроить приоритет тега</Anchor>. Это означает, что вы можете контролировать, какие теги срабатывают первыми.

| Причина | РЕШЕНИЕ |
| --- | --- |
| Для тега, который загружает SDK, установлен более низкий приоритет, чем для тега, который отправляет событие при загрузке страницы. В результате SDK не успевает инициализироваться вовремя, чтобы отправить событие. | Для тега, который загружает SDK, всегда задавайте более высокий приоритет, чем для тегов, которые отправляют события или идентифицируют пользователей. |

<div id="triggering-tags" />

### Триггеры тегов

В GTM у каждого тега есть триггер, который определяет, когда этот тег должен срабатывать.

| Причина | РЕШЕНИЕ |
| --- | --- |
| Триггер, отвечающий за срабатывание тега, который загружает SDK, настроен не для всех страниц. В результате регистрируются не все посещения страниц, и некоторые события не отправляются. | Оптимальный вариант — настроить для тега, который загружает SDK, триггер <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en">просмотра всех страниц</Anchor>. |
| Триггер, отвечающий за срабатывание тегов, которые отправляют события, настроен неправильно. В результате некоторые события не отправляются. | Определите условия срабатывания триггера. Например:<ul><li>взаимодействие с элементами DOM, например клик по кнопке</li><li>посещение страницы с определённым путём, например **/thank-you-page** или **/confirmation-page**</li></ul> |

<div id="publishing-gtm-containers" />

### Публикация контейнеров GTM

Чтобы изменения вступили в силу, после любого изменения в GTM, например добавления или редактирования тегов и триггеров, необходимо опубликовать контейнер GTM. Если вы используете веб-SDK через GTM, но SDK не загружается или события не отправляются, убедитесь, что вы [опубликовали контейнер GTM](https://support.google.com/tagmanager/answer/6107163?hl=en).

<div data-zendesk-anchors="sdk-added-directly=sdk-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B9-%D0%BD%D0%B0%D0%BF%D1%80%D1%8F%D0%BC%D1%83%D1%8E-%D0%BD%D0%B0-%D1%81%D0%B0%D0%B9%D1%82 no-data-or-partial-data-in-the-pba-dashboard=%D0%BD%D0%B5%D1%82-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8%D0%BB%D0%B8-%D0%BE%D1%82%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B0%D1%8E%D1%82%D1%81%D1%8F-%D1%82%D0%BE%D0%BB%D1%8C%D0%BA%D0%BE-%D1%87%D0%B0%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B2-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5-pba events-are-not-sent=%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BD%D0%B5-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D1%8F%D1%8E%D1%82%D1%81%D1%8F conflicting-sdks-and-libraries=%D0%BA%D0%BE%D0%BD%D1%84%D0%BB%D0%B8%D0%BA%D1%82%D1%83%D1%8E%D1%89%D0%B8%D0%B5-sdk-%D0%B8-%D0%B1%D0%B8%D0%B1%D0%BB%D0%B8%D0%BE%D1%82%D0%B5%D0%BA%D0%B8 sdk-added-using-google-tag-manager=sdk-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B9-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-google-tag-manager calling-the-sdk=%D0%B2%D1%8B%D0%B7%D0%BE%D0%B2-sdk tag-priority=%D0%BF%D1%80%D0%B8%D0%BE%D1%80%D0%B8%D1%82%D0%B5%D1%82-%D1%82%D0%B5%D0%B3%D0%B0 triggering-tags=%D1%82%D1%80%D0%B8%D0%B3%D0%B3%D0%B5%D1%80%D1%8B-%D1%82%D0%B5%D0%B3%D0%BE%D0%B2 publishing-gtm-containers=%D0%BF%D1%83%D0%B1%D0%BB%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D1%82%D0%B5%D0%B9%D0%BD%D0%B5%D1%80%D0%BE%D0%B2-gtm" />

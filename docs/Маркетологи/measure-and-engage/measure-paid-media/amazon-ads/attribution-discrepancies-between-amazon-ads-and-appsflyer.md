---
title: Расхождения в атрибуции между Amazon Ads и AppsFlyer
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-09-18T04:28:03Z'
  edited_at: '2026-08-28T00:26:29Z'
  id: 28461159218449
  locale: ru
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/ru/articles/28461159218449
---
> **At a glance:** Узнайте о различиях в моделях атрибуции между Amazon Ads и AppsFlyer.

<div id="overview" />

## Обзор

Amazon Ads и AppsFlyer — это два ключевых игрока в экосистеме привлечения мобильных пользователей, и они используют разные модели атрибуции. Это может вызвать расхождения между панелями управления Amazon реклама и AppsFlyer. Мы тесно работаем с Amazon Ads для минимизации этих расхождений, однако рекламодатели должны знать о возможных причинах.

<div id="differences-in-attribution-models" />

## Различия в моделях атрибуции

В таблица ниже описаны возможные причины расхождений между панелями Amazon реклама и AppsFlyer:

| Причина | Менеджер Amazon реклама | в AppsFlyer: |
| --- | --- | --- |
| <span id="multichannel-source-attribution"></span>Атрибуция многоканальных источников | Amazon Ads самостоятельно атрибутирует установки, независимо от других медиа-источников. | AppsFlyer использует атрибуцию по последнему клику.  <br />Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model">модели Атрибуции AppsFlyer</Anchor>. |
| <span id="different-timezones"></span>Разные часовые пояса | Часовой пояс Amazon Ads (отображается рядом с диапазоном дат) нельзя изменить. Он был установлен при создании рекламного аккаунта. | Часовой пояс приложения AppsFlyer по умолчанию — UTC+0. Чтобы соответствовать часовому поясу, указанному в Amazon Ads, измените часовой пояс приложения на <Anchor target="_blank" href="/marketers/ru/docs/app-settings#localization-time-zone">странице настроек приложения</Anchor>. |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01J81NN4J4A1KWBXJQD9SM2AWH=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 differences-in-attribution-models=%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%B8%D1%8F-%D0%B2-%D0%BC%D0%BE%D0%B4%D0%B5%D0%BB%D1%8F%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01J81NN4J4WSJBFHBARKTQ9JG5=%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%B8%D1%8F-%D0%B2-%D0%BC%D0%BE%D0%B4%D0%B5%D0%BB%D1%8F%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 reducing-discrepancies=%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%B8%D1%8F-%D0%B2-%D0%BC%D0%BE%D0%B4%D0%B5%D0%BB%D1%8F%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01J81NN4J4EJQH47YJF0H5M97G=%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%B8%D1%8F-%D0%B2-%D0%BC%D0%BE%D0%B4%D0%B5%D0%BB%D1%8F%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8" />

---
title: Удержание данных на уровне пользователя
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - SRN
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
    - Ad Networks
  created_at: '2020-02-23T15:35:57Z'
  edited_at: '2026-09-03T00:28:25Z'
  id: 360006091197
  locale: ru
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ru/articles/360006091197
---
> **Краткий обзор:** Правила хранения и использования необработанных данных на уровне пользователя определяются AppsFlyer, соответствующими законами и условиями использования SRN («**Партнеры**»).

<div id="caution" />

> ❗️ **Предупреждение**
>
> AppsFlyer предоставляет пояснения по ограничению данных в этой статье исключительно в информационных целях.  *Информация в данной статье не может считаться рекомендациями юриста. Информация предоставляется только для ознакомления.*

<div id="data-retention-and-deletion-obligations" />

## Обязательства по удержанию и удалению данных

AppsFlyer получает данные о пользователях из приложений, от партнеров и из других источников.

<div id="availability-of-user-level-data-to-advertisers" />

### Доступность данных на уровне пользователя для рекламодателей

Обычно данные на уровне пользователей предоставляются рекламодателям через инструменты формирования отчётов по сырым данным, если их пакет подписки включает сырые данные за 90 дней (см. <Anchor target="_blank" href="/marketers/ru/docs/data-availability-windows">окна доступности данных</Anchor>). В некоторых случаях существуют также <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">ограничения на сырые данные</Anchor>.

<div id="data-retention" />

### Хранение данных

AppsFlyer сохраняет данные на уровне пользователя в течение ограниченного периода. Сроки хранения необработанных данных варьируются в зависимости от метода доставки и требований партнера. В общем:

* Срок хранения**Необработанных данных на уровне пользователя** основывается на типе интеграции и требованиях партнера.
* **Агрегированные данные** хранятся до 25 месяцев.

До окончания периода хранения события пользователя атрибутируются медиаисточнику, который привел пользователя. По окончании периода хранения пользовательские события атрибутируются как органические.

Срок хранения определяется в соответствии со следующим:

* <Anchor target="_blank" href="https://www.appsflyer.com/legal/processing-customer-data/">Политика конфиденциальности при пользовании услугами AppsFlyer</Anchor>
* В соответствии с указаниями, требованиями или разрешениями законодательных положений
* Установленные партнерами условия использования и срок хранения, указанные в таблице ниже.

Обратите внимание на следующее:

* Окно доступа и период хранения могут отличаться
* AppsFlyer в некоторых случаях может расширить окно доступа
* Период хранения может изменяться в зависимости от партнера, приведшего пользователя
* Некоторые данные на уровне пользователя атрибутируются <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">медиаисточнику с ограниченным доступом</Anchor>, что означает, что необработанные данные не содержат данных атрибуции. Это может произойти в следующих случаях:
  * Политика обмена данными с партнерами
  * Включена <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">агрегированная расширенная конфиденциальность</Anchor>

<div id="partner-data-retention-periods" />

#### Установленные партнерами сроки хранения данных

| SRN/партнер | Идентификатор партнера (PID) | Удаление данных через [x] мес. после установки |
| --- | --- | --- |
| Реклама Amazon | amazondsp\_int | 12 |
| Apple Search Ads | Apple Search Ads | Без ограничений |
| Discord | discord\_int | 6 |
| DV360 | dv360\_int, doubleclick\_int | 6 |
| Google реклама* | googleadwords\_int (все каналы) | 6 |
| Hotstar | hotstar\_int | 6 |
| Meta ads* | facebook\_int (все каналы) | 6 |
| Microsoft | microsoftdisplay\_int и bingsearch\_int | 13 |
| pinterest | pinterest\_int | 6 |
| Samsung DSP | samsungdsp\_int | 3 |
| Snapchat (<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">TOS</Anchor>) | snapchat\_int | 6 |
| TikTok for Business | tiktokglobal\_int | 13 |
| X Ads (ранее Twitter) | twitter\_int | 3 |

<div id="note" />

> 📘 **Примечание***
>
> Для SRN сроки хранения, указанные в этой таблице, применимы только к данным, предоставленным непосредственно SRN. Они не применяются к атрибуции, осуществляемой через ссылки атрибуции AppsFlyer W2A (`googleads_int`, `metaweb_int`, `tiktokweb_int`, `snapweb_int`).

<div data-zendesk-anchors="h_01H95FY07TRAAD3K0A0TSG3RB6=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 data-retention-and-deletion-obligations=%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D1%82%D0%B2%D0%B0-%D0%BF%D0%BE-%D1%83%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D0%BD%D0%B8%D1%8E-%D0%B8-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D1%8E-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01H95FY07TABPC769R7TYGY5DD=%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D1%82%D0%B2%D0%B0-%D0%BF%D0%BE-%D1%83%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D0%BD%D0%B8%D1%8E-%D0%B8-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D1%8E-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 availability-of-userlevel-data-to-advertisers=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BD%D0%B0-%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01H95FY07T2Q9QAGW5A5S6KP6J=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BD%D0%B0-%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BE%D0%B4%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 data-retention=%D1%85%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01H95FY07TXS63FVDJC2NEFXYC=%D1%85%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 partner-data-retention-periods=%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0%D0%BC%D0%B8-%D1%81%D1%80%D0%BE%D0%BA%D0%B8-%D1%85%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01H95FY07TZ4N0RRJRGJ6FN2EK=%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0%D0%BC%D0%B8-%D1%81%D1%80%D0%BE%D0%BA%D0%B8-%D1%85%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01KRKAWSHH2WFZT9Q5M0FSBBAB=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5" />

---
title: Измерение кампаний с соблюдением конфиденциальности
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2023-11-28T07:10:15Z'
  edited_at: '2026-10-19T14:07:14Z'
  id: 20489739742609
  locale: ru
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ru/articles/20489739742609
---
> **Кратко:** получите ответы на распространенные вопросы FAQ о методах измерения кампаний с соблюдением конфиденциальности, задействованных сетях и их влиянии на ретаргетинг, просмотр и ограничения для приложений, ориентированных на детей.

## Информация о компании

В современных условиях повышенного внимания к конфиденциальности платформы и технологии все чаще ограничивают использование идентификаторов рекламодателя, что подталкивает индустрию к методам измерения, соответствующим требованиям конфиденциальности и при этом позволяющим эффективно измерять кампании. Для таких случаев AppsFlyer поддерживает несколько методов измерения кампаний с соблюдением конфиденциальности как для SRN, так и для не-SRN рекламных сетей, как описано ниже.

<div id="what-methods-of-attribution-dont-require-collecting-device-ids" />

<Accordion title="Как AppsFlyer измеряет эффективность кампании, когда идентификаторы рекламодателя недоступны?">

AppsFlyer предоставляет следующие методы измерения:

* <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#install-referrer-android-only">Сопоставление по рефереру установки</Anchor> (только для Android)
* <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">Вероятностное моделирование</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#deep-link">Диплинкинг</Anchor> (только для ретаргетинга)

</Accordion>

<div id="what-networks-can-be-attributed-without-using-a-device-id" />

<Accordion title="Какие методы атрибуции поддерживают рекламные сети?">

**Не-SRN рекламные сети** можно измерять с помощью дополнительных методов атрибуции с соблюдением конфиденциальности, описанных в [FAQ выше](#what-methods-of-attribution-dont-require-collecting-device-ids).

**Большинству** <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns">**SRN**</Anchor> для измерения требуется рекламный идентификатор; однако некоторые из них, указанные ниже, поддерживают другие методы с соблюдением конфиденциальности.

| СРН | Аудитории |
| --- | --- |
| Расширенные SRN (например, TikTok и Snapchat) | На основе кликов и показов в расширенных SRN |
| Meta реклама | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#агрегированное-измерение-событий-aem-для-ios">Использование AEM для устройств iOS</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#getting-userlevel-data-for-android-installs">Использование следующих параметров для устройств Android:</Anchor><ul><li>`gp_referrer`</li><li>`fb_referrer`</li><li>`ig_referrer`</li></ul></li></ul> |
| Google реклама | Использование параметра `gbraid` для устройств iOS |
| Apple Search Ads (ASA) | Использование <Anchor target="_blank" href="/marketers/ru/docs/apple-ads-integration-setup#asa-attribution">атрибуции ASA</Anchor> |
| <ul><li>Google реклама</li><li>Meta Ads</li><li>Snapchat</li><li>TikTok</li><li>Реклама в X</li><li>Yahoo! Япония</li></ul> | <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">SKAN</Anchor> |

</Accordion>

<div id="can-i-measure-retargeting-without-using-the-device-id" />

<Accordion title="Какие варианты измерения ретаргетинга поддерживает AppsFlyer?">

Атрибуцию ретаргетинга можно использовать с методами, указанными [выше](#what-methods-of-attribution-dont-require-collecting-device-ids).   
**Примечание:** атрибуция по рефереру установки (для Android) применяется только для реатрибуций, но не для повторных вовлечений.

</Accordion>

<div id="can-i-measure-viewthrough" />

<Accordion title="Поддерживается ли измерение по просмотрам указанными выше методами?">

Атрибуция по просмотрам поддерживается с помощью <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">вероятностного моделирования</Anchor>. Другие методы, такие как реферер и диплинкинг, поддерживают измерение кликов, но не просмотров.

Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#viewthrough-attribution">атрибуции по просмотрам</Anchor>.

</Accordion>

<div id="can-deep-linking-be-done-without-a-device-id" />

<Accordion title="Требуется ли для диплинкинга рекламный идентификатор?">

Диплинкинг пользователей из кампании на определенную активность в вашем приложении может происходить в разных сценариях в зависимости от того, установлено ли уже приложение.

Наличие рекламного идентификатора может влиять на поведение диплинкинга в зависимости от следующих сценариев:

* **Прямой диплинкинг:** **без воздействия**.   
  Диплинк отправляет существующих пользователей напрямую к определенной активности в вашем приложении. Как указано в <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#методы-атрибуции">таблице методов атрибуции</Anchor>, атрибуция выполняется с использованием данных URL-адреса диплинка, который напрямую передается в SDK.
* **Косвенный диплинкинг:** **работает только в случае успешной атрибуции**.   
  Диплинк направляет существующих пользователей к определенной активности в вашем приложении, но приложение не открывается сразу. Когда пользователь позже снова открывает приложение, фиксируется повторное вовлечение, и выполняется **косвенный диплинкинг. Однако это происходит только в том случае, если атрибуция выполнена успешно** (с использованием методов атрибуции, [описанных выше](#what-methods-of-attribution-dont-require-collecting-device-ids)). Поэтому, если атрибуция выполнена успешно, диплинкинг также будет работать.
* **Отложенный диплинкинг:** **работает только в случае успешной атрибуции**.  
  Диплинк отправляет новых пользователей в магазин приложений. После установки приложение открывается на определенной активности. **Это происходит только в том случае, если атрибуция выполнена успешно** (с использованием [описанных выше](#what-methods-of-attribution-dont-require-collecting-device-ids) методов атрибуции). Поэтому, если отсутствие рекламного идентификатора все же позволяет выполнить атрибуцию, диплинкинг также будет работать.

</Accordion>

<div id="what-are-the-implications-of-childdirected-app-limitations-on-attribution" />

<Accordion title="Чем отличается измерение, если рекламный идентификатор недоступен?">

В некоторых сценариях с ограничениями конфиденциальности охват измерения может быть более ограничен. AppsFlyer продолжает предоставлять значимое измерение кампаний, сохраняя конфиденциальность пользователей.

</Accordion>

> 📄 **Смотрите также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/preserve-user-privacy">Сохранение конфиденциальности пользователей</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#конфиденциальность-данных-пользователей">Конфиденциальность пользователей на уровне SDK</Anchor>

<div data-zendesk-anchors="eeee=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01HMBEZD0P31S8N9ZERB17ZHPT=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01HGAC6QR6XJ20K92DE8KQ02P3=what-methods-of-attribution-dont-require-collecting-device-ids 01HMEBCTBWJX03WEHY3QTR3RAS=what-networks-can-be-attributed-without-using-a-device-id h_01HGAC6QR7VXFNPENAXTAV97Y7=can-i-measure-retargeting-without-using-the-device-id h_01HGAC6QR7E298ZTH8G4TTD7EC=can-i-measure-viewthrough h_01HMRHWVEQCHS7QBJHPZS3B8KZ=can-deep-linking-be-done-without-a-device-id h_01HGAC6QR752QPT4MSDQ7TWAXT=what-are-the-implications-of-childdirected-app-limitations-on-attribution h_01HGAC6QR7R4ZTWJEMSKHACNPF=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

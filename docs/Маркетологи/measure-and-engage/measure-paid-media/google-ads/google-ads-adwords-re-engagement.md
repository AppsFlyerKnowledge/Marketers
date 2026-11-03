---
title: 'Google Ads (AdWords): повторное вовлечение'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2026-02-25T08:53:23Z'
  id: 4417296925073
  locale: ru
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ru/articles/4417296925073
---
> **Краткий обзор:** Измеряйте кампании ретаргетинга Google Ads.

## Кампании по ретаргетингу в Google Ads

AppsFlyer предоставляет возможность измерять результаты **кампаний по вовлечению для приложений, которые проводятся в Google Ads**.  
В AppsFlyer такие кампании называются <Anchor target="_blank" href="/marketers/ru/docs/retargeting-attribution-guide">кампаниями по ретаргетингу</Anchor>. В AppsFlyer можно получать данные о затратах, кликах и показах для ретаргетинговых кампаний. Эта интеграция позволяет вам просматривать и измерять свои затраты на рекламу в Google Ads, а затем вычислять показатели eCPI и ROI для своих кампаний в Google Ads.

Кампании по ретаргетингу направлены на пользователей, которые уже установили ваше приложение.

* Ретаргетинг для вовлечения пользователей, у которых до сих пор установлено ваше приложение, называется **повторное вовлечение**. Обычно это приводит к диплинкингу пользователей.
* Ретаргетинг для вовлечения пользователей, у которых не установлено ваше приложение, называется **повторные установки** или **реатрибуция**.

Подробные сведения см. в <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">справочных документах Google Ads по кампаниям, ориентированным на вовлечение</Anchor>.

## Настройка кампаний Google Ads для вовлечения в приложениях

Прежде чем начать, ознакомьтесь с <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">инструкцией Google о том, как поделиться ссылкой с другими аккаунтами Google Ads</Anchor>, чтобы убедиться, что ваши кампании по вовлечению должным образом измеряются с помощью существующего идентификатора ссылки.

Чтобы измерять кампании приложений Google Ads, направленные на вовлечение, выполните три шага:

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="Включение ретаргетинга в настройках приложения.">

Чтобы включить ретаргетинговые кампании для любых медиаисточников, нужно активировать эту опцию на уровне приложения. Если это первая ретаргетинговая кампания для вашего приложения, выполните следующие действия:

1. В AppsFlyer в боковом меню выберите **Настройки** > **Настройки приложения**.
2. Прокрутите список до конца.
3. Активируйте **Атрибуцию повторного вовлечения**.

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="Включите ретаргетинг Google Ads в AppsFlyer">

* Для настройки Google Ads в AppsFlyer следуйте <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">инструкциям</Anchor>.

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="Импорт конверсий «Начало сессии» в Google Ads">

Чтобы учитывать конверсии, полученные в ходе кампаний по повторному вовлечению **в Google Ads**, необходимо импортировать в Google Ads событие session\_start.

Это событие появится в Google Ads, если хотя бы один пользователь запустит приложение после включения ретаргетинга для Google Ads в AppsFlyer. На всякий случай запустите приложение сами после включения ретаргетинга.

Инструкции по импорту конверсий в Google Ads см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">здесь</Anchor>.

> 📘 **Примечание**
>
> В отличие от всех других событий, session\_start может быть востребован API Google Ads, даже если вы не импортируете session\_start в Google Ads из AppsFlyer.
> Однако в этом случае эти конверсии будут по-прежнему атрибутироваться в AppsFlyer. Из-за этого **появится существенное различие между вашими данными в AppsFlyer и в Google Ads**. Кроме того, это **помешает Google Ads оптимизировать** таргетинг пользователей рекламы.

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="Настройка диплинкинга для кампаний приложений, направленных на вовлечение">

В кампаниях Google Ads для приложений, ориентированных на вовлечение, необходимо использовать <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">диплинки для кампаний по повторному вовлечению.</Anchor> Использовать сторонние решения для диплинкинга нельзя из-за несоответствия доменов. Это относится и к решению OneLink от AppsFlyer. Используйте <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">самостоятельно настроенные ссылки приложения, универсальные ссылки или схемы URI</Anchor>.

Нет необходимости добавлять в глубинную ссылку какие-либо дополнительные параметры (is\_retargeting = true и pid = adwords не требуются).

</Accordion>

## Динамический ремаркетинг и торговые кампании

AppsFlyer поддерживает динамический ремаркетинг для приложений и торговых кампаний. Платформа AppsFlyer относится к ним так же, как и к любым другим кампаниям по повторному вовлечению.

* Подробные сведения о динамическом ремаркетинге для приложений см. <Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">здесь</Anchor>.
* Подробные сведения о торговых кампаниях см. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">здесь</Anchor>.
* Подробные сведения о кампаниях Google Ads для приложений, ориентированных на вовлечение, см. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">здесь</Anchor>.

### Поддержка кампаний без привязки к приложению (кампании для создания спроса и поисковый маркетинг)

AppsFlyer поддерживает измерение повторного вовлечения только для кампаний Google, не связанных с приложениями, включая:

* кампании для создания спроса;
* кампании маркетинга поисковиков (SEM).

Эти кампании работают **без дополнительных настроек** с AppsFlyer и не требуют:

* параллельного отслеживания;
* реализации Smart Script.

**Ограничения:**

* **Установки** из кампаний для создания спроса и SEM не атрибутируются ни на одной платформе.

**Отказ:** В отличие от TikTok и Meta, в Google пока нельзя включать или отключать измерение кампаний вне приложений.

> 📄 **См. также**
>
> * Для получения информации, связанной с iOS 14, см. раздел <Anchor target="_blank" href="/marketers/ru/docs/get-skan-postback-data-from-google-ads">Совместимость Google Ads SKAdNetwork с AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-retargeting-campaigns=%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BF%D0%BE-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D1%83-%D0%B2-google-ads h_01HDP34BWZFG09ABN5NQB6EY32=%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BF%D0%BE-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D1%83-%D0%B2-google-ads setting-up-google-ads-app-campaigns-for-engagement=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-google-ads-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F%D1%85 h_01HDP34BWZXXNZDE0SR4MXBC9V=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-google-ads-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F%D1%85 h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement dynamic-remarketing-and-shopping-campaigns=%D0%B4%D0%B8%D0%BD%D0%B0%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B9-%D1%80%D0%B5%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3-%D0%B8-%D1%82%D0%BE%D1%80%D0%B3%D0%BE%D0%B2%D1%8B%D0%B5-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01HDP34BWZ990SD3B1C5DZRESK=%D0%B4%D0%B8%D0%BD%D0%B0%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B9-%D1%80%D0%B5%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3-%D0%B8-%D1%82%D0%BE%D1%80%D0%B3%D0%BE%D0%B2%D1%8B%D0%B5-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_google-non-app-campaign-support=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B1%D0%B5%D0%B7-%D0%BF%D1%80%D0%B8%D0%B2%D1%8F%D0%B7%D0%BA%D0%B8-%D0%BA-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8E-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D1%8F-%D1%81%D0%BF%D1%80%D0%BE%D1%81%D0%B0-%D0%B8-%D0%BF%D0%BE%D0%B8%D1%81%D0%BA%D0%BE%D0%B2%D1%8B%D0%B9-%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3 support-for-nonapp-campaigns-demand-gen-and-sem=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B1%D0%B5%D0%B7-%D0%BF%D1%80%D0%B8%D0%B2%D1%8F%D0%B7%D0%BA%D0%B8-%D0%BA-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8E-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D1%8F-%D1%81%D0%BF%D1%80%D0%BE%D1%81%D0%B0-%D0%B8-%D0%BF%D0%BE%D0%B8%D1%81%D0%BA%D0%BE%D0%B2%D1%8B%D0%B9-%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3 h_01HDP2XBSEJVQ5G0MD0V5R05CM=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

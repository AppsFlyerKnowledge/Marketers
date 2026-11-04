---
title: Взаимодействие SKAN с TikTok for Business
metadata:
  keywords:
    - Advertisers
    - ios14
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-03-14T12:05:58Z'
  edited_at: '2026-08-18T00:32:17Z'
  id: 360018499098
  locale: ru
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ru/articles/360018499098
---
> **Краткий обзор:** Взаимодействие со SKAN позволяет TikTok обмениваться постбэками SKAN с AppsFlyer, а AppsFlyer — передавать TikTok сопоставление измерений значений конверсии.

<div id="skan-interoperability-appsflyer---tiktok" />

## Совместимость SKAN: AppsFlyer &lt;-> TikTok

Если вы работаете с несколькими партнерами — рекламными сетями, рекомендуется настроить все в AppsFlyer. В результате метрики эффективности SKAN, дополненные другими метриками, например данными о затратах, будут доступны на платформе AppsFlyer.

<div id="scope-of-skan-interoperability-with-tiktok" />

### Объем взаимодействия между SKAN и TikTok

Взаимодействие позволяет AppsFlyer и TikTok совместно использовать сопоставление значений конвертации SKAN (настроенное в AppsFlyer). Это позволяет обеим сторонам предоставлять метрики эффективности. При включении интеграции TikTok for Business (либо устаревшей, либо <Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup">расширенной интеграции SRN</Anchor> ) AppsFlyer предоставляет события TikTok в целях оптимизации. См. <Anchor target="_blank" href="/marketers/ru/docs/skan-integrated-partners-list">список полей обогащения</Anchor>, поддерживаемых TikTok.

<div id="tiktok-for-business-guidance" />

### Руководство по TikTok for Business

При настройке кампаний TikTok for Business ознакомьтесь с рекомендациями TikTok по <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10000858">воздействию iOS 14</Anchor> и примите во внимание следующее:

* Убедитесь, что <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">SDK AppsFlyer</Anchor> обновлен.
* [Настройте идентификатор приложения TikTok](https://ads.tiktok.com/help/article?aid=10001060) для каждого приложения, которое вы рекламируете в TikTok for Business.
  * TikTok App ID — это уникальный код, который генерируется в TikTok Ads Manager и используется TikTok для подтверждения того, что рекламодатель является владельцем своих приложений.
  * Хотя это не обязательно, рекомендуем указать App ID всех ваших приложений.  
    Так вы будете лучше контролировать свои данные в TikTok For Business и сможете разблокировать дополнительные продукты.
  * **Чтобы добавить несколько TikTok App ID:**
    1. Введите первый TikTok App ID.
    2. Нажмите **ВВОД.**
    3. Введите следующий TikTok App ID.
  * Настройка TikTok App ID не влияет на ваши данные в AppsFlyer.
  * [Подробнее о требованиях к TikTok App ID для iOS 14](https://ads.tiktok.com/help/article?aid=10001070).
* [Завершите сопоставление событий конверсии](/docs/skan-interoperation-with-tiktok-for-business#3) для bytedanceglobal\_int и tiktokglobal\_int.
* Ознакомьтесь с руководством по ограничению кампаний и объединению аккаунтов/кампаний.

Работайте над конфигурацией и стратегией SKAN непосредственно с вашим менеджером по работе с клиентами TikTok for Business.

TikTok поддерживает SKAN следующим образом:

* Измерение и оптимизация с помощью API для измерения конверсии.
* Отчетность по специальным кампаниям iOS 14 в TikTok for Business.

<div id="campaign-limits-for-dedicated-ios-14-campaigns" />

### Лимиты кампаний для специальных кампаний iOS 14

В связи с ограничениями API SKAN TikTok for Business поддерживает следующее при создании специальных кампаний iOS 14 (применимо к рекламе по установке приложений и динамической рекламе для поиска приложений):

* ​Приложения iOS ограничены 15 кампаниями с 5 блоками рекламы на кампанию.
* Специальные кампании для iOS 14:
  * Можно создавать несколько рекламных аккаунтов, но общее количество активных кампаний ограничено 15.
  * Все соответствующие цели учитываются в ограничении (15), и после достижения лимита кампании рекламодатели должны подождать не менее 72 часов после того, как кампания была приостановлена, выключена или удалена, чтобы освободить слот для кампании, прежде чем начинать новую кампанию.

<div id="enabling-interoperation" />

### Активация взаимодействия

Взаимодействие можно активировать при помощи настроек на дэшбордах AppsFlyer и TikTok for Business. Функциональная совместимость и изменения в приложении не требуются.

**Чтобы активировать взаимодействие AppsFlyer SKAN с** **TikTok for Business:**

| Шаг | Действие | Подробности |
| --- | --- | --- |
| <span id="1"></span>1 | Минимальные требования для Приложения | <ul><li>Интегрируйте новейший SDK AppsFlyer в свое приложение.</li></ul> |
| <span id="2"></span>2 | Обзор настроек SKAN | Настройте и включите решение <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">SKAN от AppsFlyer.</Anchor><br /><br />**Чтобы просмотреть настройки SKAN**:<ol><li>В AppsFlyer перейдите в **Настройки** > **SKAN Conversion Studio**.</li><li>Откройте опции (⋮) и убедитесь, что **измерение SKAN** включено.<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>Выберите предпочтительный режим измерения.<br />Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Запишите точные названия событий. Они потребуются вам на следующем шаге.</li></ol> |
| <span id="3"></span>3 | Сопоставление событий в приложении | Проверьте сопоставление с внутренними событиями приложения и, если требуется, внесите изменения в TikTok for Business.<br /><br />**Чтобы просмотреть и настроить сопоставления событий в приложении**:<ol><li>В AppsFlyer перейдите в раздел **Настройки** > **Активные интеграции**.</li><li>Найдите и выберите **TikTok For Business**.</li><li>На вкладке **Интеграция** убедитесь, что интеграция с TikTok for Business активирована и настроена.</li><li>В разделе **In-app events postback** (Постбэки внутренних событий):<ol><li>[Обязательно] Включите **постбэки внутренних событий приложения**, если они еще не включены.</li><li>Убедитесь, что внутренние события приложения, которые вы настроили в <Anchor target="_blank" href="/marketers/ru/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>, сопоставлены с названиями событий TikTok for Business или с событиями в вашей <Anchor target="_blank" href="/marketers/ru/docs/skan-cv-decode-map-your-cv-to-events">пользовательской карте конверсии</Anchor>.<br />**Примечание:** Сопоставление `af_skad_revenue` с событием TikTok `Purchase` необходимо только когда ваша схема конверсии SKAN измеряет общий доход.<br />[![](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)</li></ol></li><li>Нажмите **Сохранить интеграцию**.</li></ol> |

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">Руководство по решению AppsFlyer SKAN</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-tiktok=%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B8%D0%BC%D0%BE%D1%81%D1%82%D1%8C-skan-appsflyer---tiktok h_01HDNYZ0CT1MGCRSSP3MXTJK5V=%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B8%D0%BC%D0%BE%D1%81%D1%82%D1%8C-skan-appsflyer---tiktok scope-of-skan-interoperability-with-tiktok=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-skan-%D0%B8-tiktok h_01HDNYZ0CT5NZHDHDBDSCFG911=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-skan-%D0%B8-tiktok tiktok-for-business-guidance=%D1%80%D1%83%D0%BA%D0%BE%D0%B2%D0%BE%D0%B4%D1%81%D1%82%D0%B2%D0%BE-%D0%BF%D0%BE-tiktok-for-business 01HR1TPFCSXRGYC610AR7KMTS5=%D1%80%D1%83%D0%BA%D0%BE%D0%B2%D0%BE%D0%B4%D1%81%D1%82%D0%B2%D0%BE-%D0%BF%D0%BE-tiktok-for-business campaign-limits-for-dedicated-ios-14-campaigns=%D0%BB%D0%B8%D0%BC%D0%B8%D1%82%D1%8B-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-ios-14 h_01HDNYZ0CT7RNDAEWYKBHS6PET=%D0%BB%D0%B8%D0%BC%D0%B8%D1%82%D1%8B-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-ios-14 enabling-interoperation=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F h_01HDNYZ0CTJGY3GPC9F907NEPT=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F h_01HDNZ1BW5EBP0JCX84MTYPQ6K=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

---
title: Интегрируйте API SDK ROI360 для дохода от рекламы
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2026-08-18T00:02:13Z'
  id: 4416353506833
  locale: ru
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ru/articles/4416353506833
---
> **Краткий обзор:** API SDK для отчетности о доходах от рекламы AppsFlyer работает с рекламными сетями для предоставления отчетов на уровне показов.

<Image align="center" alt="mceclip1__1_.png" src="https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png" />

<div id="impression-level-ad-revenue-reporting-by-sdk-api" />

## Отчетность о доходах от рекламы на уровне показов через SDK API

**Варианты отчетности о доходах от рекламы**

Доходы от рекламы поступают в AppsFlyer либо в совокупной детализации (через API), либо на уровне показов (через SDK). Данные на уровне показов через SDK:

* Обладают большей актуальностью и раньше становятся доступны в AppsFlyer.
* Поддержка SKAN.
* Для SDK AppsFlyer V6.15+. В более ранних версиях SDK используется коннектор вместо API. Ссылки для разработчиков включены в эту документацию, где это уместно.

**Примечание:**

* Показы рекламы собираются и обрабатываются в AppsFlyer, но не учитываются в вашем пакете приложений.
* Смотрите полный <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">список плагинов SDK, поддерживающих Ad Revenue SDK API</Anchor>.

<div id="reporting-ad-revenue-using-the-sdk-api" />

### Отчетность о доходах от рекламы с использованием SDK API

**Принципы работы SDK**

API SDK для отчетности о доходах от рекламы отправляет данные о показах в SDK AppsFlyer. Эти события показов собираются и обрабатываются в AppsFlyer, а событие дохода от рекламы,  , создается на платформе с приписыванием дохода исходному источнику UA.

**Отображение данных**

Событие `af_ad_revenue` используется для идентификации доходов от рекламы. Это событие используется во всей платформе, включая дэшборды и другие инструменты предоставления данных.

**Поддерживаемые сети**

Список поддерживаемых сетей посредничества и монетизации, которые могут отправлять данные через API для отчетности о доходах от рекламы, выглядит следующим образом:

* <Anchor target="_blank" href="/marketers/ru/docs/ironsource-campaign-configuration#ad-revenue-tab">Посредничество Unity LevelPlay</Anchor> (ранее ironSource)
* <Anchor target="_blank" href="/marketers/ru/docs/applovin-max-ad-revenue-configuration">Applovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Topon Pte.
* Tradplus
* <Anchor target="_blank" href="/marketers/ru/docs/yandex-direct-campaign-configuration">Яндекс</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation (когда посредническое решение отсутствует в списке поддерживаемых партнеров)
* directMonetizationNetwork (когда приложение интегрируется непосредственно с сетями монетизации без посредничества)

**Актуальность данных**

SDK API отправляет данные о доходах на платформу в момент показа рекламы. Для премиальных клиентов ROI360 данные становятся доступны:

* **Тема уровня показов DataLocker в 1:00 и далее каждый час,**
* **Отчеты об активности и когортам в AppsFlyer появляются в 5:00 UTC и далее каждые 4 часа.**

<div id="implementing-appsflyer-ad-revenue-sdk-api" />

## Реализация API SDK для отчета о доходах от рекламы AppsFlyer

**Как внедрить API SDK для отчета о доходах от рекламы AppsFlyer**:

1. <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Включите отчетность о доходах от рекламы на уровне SDK в AppsFlyer</Anchor> для партнера, которого вы хотите подключить. **Примечание**: Это необходимо сделать для каждого приложения в отдельности.
2. Попросите вашего разработчика интегрировать API SDK для отчетности о доходах от рекламы AppsFlyer, используя <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">эти инструкции</Anchor>.
3. Чтобы зафиксировать доходы от рекламы на дэшборде SKAdNetwork, следуйте <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">инструкциям SKAN по учету доходов от рекламы</Anchor>.
4. Протестируйте интеграцию: после завершения интеграции убедитесь, что события дохода от рекламы поступают, используя один из следующих методов:
   * В <Anchor target="_blank" href="/marketers/ru/docs/testing-the-sdk-integration-for-marketers#view-live-events">средстве просмотра событий в реальном времени</Anchor> проверьте, что события дохода от рекламы отображаются в режиме реального времени. Обратите внимание: средство просмотра событий в реальном времени показывает только события, отправленные с зарегистрированных тестовых устройств.
   * На странице **Revenue Settings** отредактируйте соответствующую интеграцию дохода от рекламы и нажмите **Test Connection**, чтобы проверить, обрабатывались ли недавно какие-либо действительные события дохода от рекламы. Подробнее см. <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Подключение к интегрированным партнёрам, поддерживающим передачу данных о доходе от рекламы</Anchor>.

<div id="traits-and-limitations" />

## Характеристики и ограничения

| Специфика | Примечания |
| --- | --- |
| Admob | <ul><li>Чтобы активировать iLTV для Admob, следуйте <Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">этой ссылке</Anchor></li><li>Для Android и Unity выручка от показов отражается в Admob iLTV SDK в <Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">микроединицах</Anchor>. Чтобы в AppsFlyer отображалась правильная сумма дохода от рекламы в долларах США, перед отправкой дохода от рекламы в AppsFlyer разделите сумму, полученную из обработчика события iLTV, на 1 миллион.</li></ul> |
| Значение дохода от рекламы | События показов с доходом выше 10 долларов США (или эквивалентной суммы в других валютах) не обрабатываются API SDK. |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-API=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%BD%D0%B0-%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D0%B5-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-sdk-api 01H8HHAQHK6CDK8X2Y6N4GANNC=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%BD%D0%B0-%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D0%B5-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-sdk-api reporting-ad-revenue-using-the-sdk-API=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D1%81-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%D0%BC-sdk-api 01H8HHAQHKQ3H3R21Z1JYNJ2EE=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D1%81-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%D0%BC-sdk-api implementing-generic-appsflyer-ad-revenue-sdk-API=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-api-sdk-%D0%B4%D0%BB%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-appsflyer 01H8HHAQHKCXKPJJE8EDT1J9CR=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-api-sdk-%D0%B4%D0%BB%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-appsflyer traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F 01H8HHAQHMCSVQ2ZAT3G7XJKAN=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

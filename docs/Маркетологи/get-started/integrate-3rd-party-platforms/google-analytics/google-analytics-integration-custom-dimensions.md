---
title: Интеграция Google Analytics — пользовательские параметры
metadata:
  keywords:
    - Analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-12-07T13:34:54Z'
  edited_at: '2026-08-28T00:11:58Z'
  id: 4413033740817
  locale: ru
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/ru/articles/4413033740817
---
> **At a glance:** Настройте интеграцию с Google Analytics с помощью пользовательских измерений.

<div id="custom-dimensions-on-google-analytics" />

## Пользовательские параметры в Google Analytics

Есть еще один способ отправки данных атрибуции AppsFlyer в Google Analytics: он настраивается в GA, а не в дэшборде AppsFlyer.

> 🚧 **Important**
>
> **Важно!**
>
> Метод пользовательских измерений **НЕ РЕКОМЕНДУЕТСЯ** по следующим причинам:
>
> * Интеграция Google Analytics через дэшборд AppsFlyer — это просто, быстро и легко
> * Интеграция Google Analytics с помощью пользовательских измерений сложна и подвержена ошибкам
> * Для использования пользовательских измерений нужно использовать и SDK AppsFlyer, и SDK Google Analytics
> * Использование пользовательских измерений повышает вероятность расхождений

Рекламодателям, которые используют новую <Anchor target="_blank" href="/marketers/ru/docs/google-analytics-ga4-integration">интеграцию с Google Analytics</Anchor>, не нужно использовать метод пользовательских параметров.

> 📘 **Note**
>
> **Примечание**
>
> Этот метод требует интеграции SDK GA в ваше приложение.
>
> * <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/android/v4/">SDK GA для Android</Anchor>
> * <Anchor target="_blank" href="https://developers.google.com/analytics/devguides/collection/ios/v3/">SDK GA для iOS</Anchor>

<div id="setting-media-source-as-a-custom-dimension-on-google-analytics" />

### Настройка медиаисточника как пользовательского параметра в Google Analytics

В Google Analytics есть высокоэффективный инструмент сегментации на уровне пользователя, который называется пользовательскими параметрами. Значения пользовательских параметров отправляются с мобильных устройств, и на их основе в вашем дэшборде Google Analytics формируются отчеты.

<div id="step-1-define-it-on-google-analytics" />

### Шаг 1: определите это в Google Analytics

1. Выберите приложение в меню GA.
2. Выберите ***Администратор*** на верхней панели дэшборда GA.
3. В столбце ***СВОЙСТВО*** выберите ***Пользовательский параметр***.
4. Выберите ***Пользовательский параметр***  
   <Image align="center" alt="Опция пользовательских измерений в панели администратора Google Analytics" src="https://files.readme.io/e475ad1eda5b6338825b712e6c8254f245d5339f50ae40e723f465207e124262-4413121542033.png" />
5. Создайте новый параметр. Назовите его **медиаисточник AppsFlyer** и убедитесь, что выбрана область действия ***Пользователь***. Это гарантирует сохранение данных в течение нескольких сессий. ![ga2.png](https://files.readme.io/b2d85fd068e5523265a2b49b4218234fc77d5896ad41801cbe0e017752763cf2-4413121449873.png)

   Каждый параметр создается с индексом, который нужно запомнить, чтобы позже использовать его в API GA из вашего приложения. В этом примере индекс нового параметра — 10.

   <Image align="center" alt="ga3" src="https://files.readme.io/6efc2249ede92291a2aadd16eccbc5b38b580723c6277e3746bdd467de29764a-11179413394193.png" />

   Повторите этот шаг, создайте еще один параметр и назовите его **кампания AppsFlyer**

<div id="step-2-setting-and-sending-the-data-from-the-app" />

### Шаг 2: настройка и отправка данных из приложения

Сначала получите значение медиаисточника из SDK AppsFlyer. Это можно сделать с помощью метода `onConversionDataSuccess`.

**Примечание:** Начиная с SDK V5, `onConversionDataSuccess` — это название метода для получения данных конверсии. Если вы используете версию SDK ниже 5.0.0, имя метода — `onInstallConversionDataLoaded` в Android и `onConversionDataReceived` в iOS. Мы рекомендуем обновить SDK до версии 5.0.0. Подробнее см. <Anchor target="_blank" href="/marketers/ru/docs/links-to-appsflyer-sdk-release-notes">здесь</Anchor>.

Затем вы можете задать медиаисточник как пользовательский параметр с помощью Google Analytics SDK. См. следующие примеры кода, чтобы узнать, как это сделать:

<Tabs>
<Tab title="Android;">

```objectivec
private static Tracker sTracker;
@Override
public void onConversionDataSuccess(Map<String, String> conversionData)
{
  if (conversionData.get("af_status") == "Non-organic")
  {
    String mediaSource = conversionData.get("media_source");
    String campaign = conversionData.get("campaign");
    sTracker.set(Fields.customDimension(10), mediaSource);
    sTracker.set(Fields.customDimension(1), campaign);
  }
  else if (conversionData.get("af_status") == "Organic")
  {
    sTracker.set(Fields.customDimension(10), "Organic");
  }
}
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

```objectivec
-(void)onConversionDataSuccess:(NSDictionary*) installData {
  id status = [installData objectForKey:@"af_status"];
  if([status isEqualToString:@"Non-organic"]) {
		id mediaSource = [installData objectForKey:@"media_source"];
		id campaign = [installData objectForKey:@"campaign"];
		[[[GAI sharedInstance] defaultTracker] set:[
				GAIFields customDimensionForIndex:10
			] value: mediaSource];
    [[[GAI sharedInstance] defaultTracker] set:[
				GAIFields customDimensionForIndex:1
			]
			value: campaign];
   }
	 else if([status isEqualToString:@"Organic"]) {
    [[[GAI sharedInstance] defaultTracker] set:[
				GAIFields customDimensionForIndex:10
			]
			value: "Organic"];
   }
}
```

</Tab>
</Tabs>

<div id="step-3-see-the-results-in-google-analytics" />

### Шаг 3: просмотрите результаты в Google Analytics

В большинстве отчетов GA есть возможность детализировать данные с помощью параметра ***Пользовательские измерения***. Вы можете выбрать измерения ***AppsFlyer Media Source*** или ***AppsFlyer Campaign*** ([настраиваются на шаге 1](/docs/google-analytics-integration-custom-dimensions#шаг-1-определите-это-в-google-analytics)), чтобы увидеть, какие медиаисточники и кампании приводят пользователей, которые выполняют установку вашего приложения.

<Image align="center" alt="G_analytics1.png" src="https://files.readme.io/dde9219a7a8eec5c861b5031ad741ff7377d85ba9c3693bcbc455fd735f8af2d-4413121449617.png" />

<div data-zendesk-anchors="custom-dimensions-on-google-analytics=%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B2-google-analytics h_01HDP3FHGNR06EV1KS8F1PFQ09=%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B2-google-analytics setting-media-source-as-a-custom-dimension-on-google-analytics=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BA-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%B0-%D0%B2-google-analytics h_01HDP3FHGP9H18VJKNSR27HXEZ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BA-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%B0-%D0%B2-google-analytics step-1-define-it-on-google-analytics=%D1%88%D0%B0%D0%B3-1-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B8%D1%82%D0%B5-%D1%8D%D1%82%D0%BE-%D0%B2-google-analytics h_01HDP3FHGPTJ4EVYPDA7RWPJF9=%D1%88%D0%B0%D0%B3-1-%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B8%D1%82%D0%B5-%D1%8D%D1%82%D0%BE-%D0%B2-google-analytics step-2-setting-and-sending-the-data-from-the-app=%D1%88%D0%B0%D0%B3-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8%D0%B7-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HDP3FHGPF3BJZSG6G0QP5T1R=%D1%88%D0%B0%D0%B3-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8%D0%B7-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F step-3-see-the-results-in-google-analytics=%D1%88%D0%B0%D0%B3-3-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%80%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%D1%8B-%D0%B2-google-analytics h_01HDP3FHGP9G9BP956KM4ACDRC=%D1%88%D0%B0%D0%B3-3-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%80%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%D1%8B-%D0%B2-google-analytics" />

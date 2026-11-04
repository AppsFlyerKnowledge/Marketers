---
title: Интеграция Adobe Analytics с AppsFlyer
metadata:
  keywords:
    - Adobe Analytics
    - Integration
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-07-05T07:20:10Z'
  edited_at: '2026-09-24T00:11:10Z'
  id: 115003326706
  locale: ru
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/ru/articles/115003326706
---
> **Краткий обзор:** [Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html) (ранее Omniture) — это набор инструментов для предиктивной аналитики и аналитики в режиме реального времени, которые можно интегрировать в сторонние источники. Он включает в себя приложения для маркетинговых отчетов и аналитики (SiteCatalyst), специального анализа (Adobe Discover) и аналитических заключений, которые помогают создать целостное представление о бизнес-деятельности путем преобразования взаимодействия с клиентами в аналитические сведения.

<div id="overview" />

## Обзор

Эта интеграция заключается в двустороннем потоке данных между Adobe и AppsFlyer. Для успешной реализации интеграции необходимо внедрить код в приложение. Для полного успеха интеграции должны быть выполнены требования AppsFlyer и Adobe.

<div id="setting-up-adobe-analytics-integration" />

## Настройка интеграции с Adobe Analytics

Если вы используете Adobe Analytics Report Suite для общего анализа эффективности кампании и создания сегментов, то интеграция AppsFlyer с Adobe Analytics обеспечивает автоматическую передачу данных атрибуции из AppsFlyer в Adobe, чтобы помочь вам достичь ваших целей.

<div id="prerequisites" />

### Необходимые условия:

* Настройка <Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/">документации мобильного SDK для Adobe Experience Platform</Anchor>
* Сервис <Anchor target="_blank" href="https://experienceleague.adobe.com/en/docs/id-service/using/home">Marketing Cloud Visitor ID</Anchor> или Experience cloud ID
* Три eVar в каждом пакете отчетов, которые можно использовать только для этой интеграции

<div id="step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer" />

### Шаг 1: Передайте идентификатор Adobe Experience Cloud (ECID, идентификатор Marketing Cloud или идентификатор посетителя) в AppsFlyer.

Чтобы извлечь идентификатор Adobe Experience Cloud и передать его:

1. <Anchor target="_blank" href="https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid">Обновите приложение и извлеките идентификатор посетителя Marketing Cloud</Anchor> с помощью метода SDK Adobe сразу после инициализации SDK Adobe.
2. Используйте один из следующих методов SDK AppsFlyer для настройки идентификатора посетителя Adobe Marketing Cloud:

<div id="setadditionaldata" />

<Accordion title="setAdditionalData">

<Tabs>
<Tab title="Android">

Узнайте больше о [методе setAdditionalData](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata).

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
customData .put("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

Узнайте больше о [методе setAdditionalData](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata).

Objective C

```objectivec
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{
  @"marketingCloudID" : "ADOBE_VISITOR_ID"
}];
```

Swift

```swift
let CustomDataMap: [AnyHashable: Any] = [
  "marketingCloudID" : "ADOBE_VISITOR_ID"
]
AppsFlyerTracker.shared().customData = CustomDataMap
```

</Tab>

<Tab title="Unity">

Узнайте больше о [методе setAdditionalData](https://dev.appsflyer.com/hc/docs/api#setadditionaldata).

```csharp
Dictionary<string, string> CustomDataMap = new Dictionary<string, string>();
CustomDataMap.Add("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyer.setAdditionalData(CustomDataMap);
```

</Tab>
</Tabs>

</Accordion>

<div id="setcustomeruserid" />

<Accordion title="Установка Customer User ID">

<Tabs>
<Tab title="Android">

Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">методе</Anchor> <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId</Anchor>.

```java
AppsFlyerLib.getInstance().setCustomerUserId("ADOBE_VISITOR_ID");
```

</Tab>

<Tab title="iOS">

Узнайте больше о методе <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId</Anchor>.

Objective C

```objectivec
NSString *customerUserID = [AppsFlyerLib shared].customerUserID;
```

Swift

```swift
let customerUserID = AppsFlyerLib.shared().customerUserID
```

</Tab>
</Tabs>

</Accordion>

<div id="step-2-configure-adobe-analytics-in-appsflyer" />

### Шаг 2: Настройка аналитики Adobe в AppsFlyer

**Предварительные условия:** Перед настройкой интеграции не забудьте [передать идентификатор посетителя Adobe Marketing Cloud в SDK AppsFlyer](/docs/adobe-analytics-integration-with-appsflyer#шаг-1-передайте-идентификатор-adobe-experience-cloud-ecid-идентификатор-marketing-cloud-или-идентификатор-посетителя-в-appsflyer).

**Для активации или изменения интеграции:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** >**Маркетплейс партнеров**.  
   **Чтобы изменить:** В AppsFlyer в боковом меню выберите **Сотрудничество** > **Активные интеграции**.
2. Найдите и выберите **Adobe Analytics**.
3. Нажмите **Настроить интеграцию**. Вы будете перенаправлены на страницу настройки интеграции.
4. На вкладке **Интеграция** выберите приложение для интеграции и включите **Активировать партнера** .  
   **Примечание: Переключатель должен быть включен <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">(активирован)</Anchor> на всё время работы с партнером.**
5. Настройте постбэки по умолчанию, отправляемые в Adobe Analytics. AppsFlyer может отправлять автоматические постбэки как для установок, так и для повторных вовлечений (включая повторные атрибуции). Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэках по умолчанию</Anchor>.
6. Из **SDK Adobe Analytics** как часть файла **ADBMobileConfig.XML** скопируйте **Report\_Suite\_ID** (выделено синим цветом) и **Adobe\_Analytic\_server\_URL** (выделено зеленым цветом) и вставьте их в соответствующие поля на странице интеграции Adobe Analytics в AppsFlyer.

   ![](https://files.readme.io/fb46a40178b88dc8f8fb0f9bcce5aa289fc27c2dbf52d1e67783c7b764729f0f-360001063605.png)
7. Нажмите **Сохранить интеграцию**.

После сохранения AppsFlyer отправляет в Adobe Analytics следующие данные для каждой органической и неорганической установки:

* Идентификатор Adobe ID (MCVID)
* Идентификатор пакета отчетов и URL-адрес сервера
* Идентификатор устройства клиента
* Источник медиа
* Название кампании

<div id="note" />

> 📘 **Примечание:**
>
> В соответствии с условиями предоставления услуг как Meta Ads, так и X Ads AppsFlyer запрещено передавать третьим лицам данные на уровне пользователя. Это означает, что установки Meta Ads и X Ads отправляются как органические.

<div id="step-3-map-data-to-evars-in-adobe-analytics" />

### Шаг 3: Сопоставление данных с eVar в Adobe Analytics

В связи с тем, что коннекторы данных Adobe Analytics устарели, вам потребуется использовать правила обработки для сопоставления контекстных переменных с eVar.

Узнайте больше об [использовании правил обработки](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html?lang=en).

Переменные контекстных данных AppsFlyer сопоставлены следующим образом:

* MobileAdCampaign (контекстные данные)
* MobileAdNetwork (контекстные данные)
* MobileAdProvider(контекстные данные)

Если у вас возникли проблемы с сопоставлением переменных контекстных данных AppsFlyer с помощью правил обработки, обратитесь за дополнительной поддержкой к команде по работе с аккаунтами Adobe

<div id="step-4-optional-set-up-your-marketing-channel" />

### Шаг 4 [необязательно]: Настройка маркетингового канала

См. инструкции по настройке маркетингового канала на платформе в <Anchor target="_blank" href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-channels.html">документации к Adobe Analytics</Anchor>. Обязательно выберите следующие поля в соответствии с правилами идентификации:

1. «Значение переменной конверсии, заданное веб-маяком Adobe»: выберите **AppsFlyer** и **Существует**.
2. «Определение канала как»: выберите **Атрибуция мобильных приложений**.
3. «Установить значение канала:» выберите **Кампания AppsFlyer**.

<div id="domain-and-security-details" />

## Сведения о домене и безопасности

Ниже приведена подробная информация о домене и проблемах безопасности:

1. ANALYTIC\_SERVER\_DOMAIN можно найти как серверную переменную в файле конфигурации вашего приложения. Вы можете выбрать любой домен для аналитики атрибуции. Как правило, используются стандартные домены для сервиса коллекций Adobe Analytics, например sc.omtrdc.net. Их можно найти в настройках аналитики (сервера) в файле **ADBMobile.config**.
2. Протокол (HTTP/HTTPS) URL-адреса зависит от того, является ли домен сервера ANALYTIC безопасным или нет. Важно использовать правильный протокол. Чтобы узнать, является ли настройка безопасной, проверьте, установлено ли для параметра аналитики (SSL) значение **true** в файле **ADBMobile.config**. Если ваше соединение безопасно, используйте HTTPS, если оно небезопасно, используйте HTTP.
3. ИДЕНТИФИКАТОР ПАКЕТА ОТЧЕТОВ можно как переменную **rsids** в файле конфигурации вашего приложения. Вы можете присвоить своему пакету отчетов любое имя.
4. ts=`{timestamp}` используется только в том случае, если **offlineEnabled** имеет значение true в вашем файле конфигурации. Удалите этот параметр из URL-адреса, если параметр **offlineEnabled** имеет значение False или если ваш пакет отчетов не активирован с **меткой времени**.

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HA4ZWDM1MEW2VDFXYMAJ2QE2=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 setting-up-adobe-analytics-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-adobe-analytics h_01HA4ZWDM11RJ6GRJ7W8QMFACT=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-adobe-analytics prerequisite=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01HA4ZWDM1YK58Q56Y0S8PC1E2=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer=%D1%88%D0%B0%D0%B3-1-%D0%BF%D0%B5%D1%80%D0%B5%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-adobe-experience-cloud-ecid-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-marketing-cloud-%D0%B8%D0%BB%D0%B8-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D0%BF%D0%BE%D1%81%D0%B5%D1%82%D0%B8%D1%82%D0%B5%D0%BB%D1%8F-%D0%B2-appsflyer h_01HA4ZWDM1J65D32PVXY0ZD9YV=%D1%88%D0%B0%D0%B3-1-%D0%BF%D0%B5%D1%80%D0%B5%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-adobe-experience-cloud-ecid-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-marketing-cloud-%D0%B8%D0%BB%D0%B8-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D0%BF%D0%BE%D1%81%D0%B5%D1%82%D0%B8%D1%82%D0%B5%D0%BB%D1%8F-%D0%B2-appsflyer h_01HA4ZWDM1RDRDGZ3X7WC0ACV1=setadditionaldata h_01HA4ZWDM1CAXZH7ZNJ0Z37EE1=setcustomeruserid step-2-configure-adobe-analytics-in-appsflyer=%D1%88%D0%B0%D0%B3-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B8-adobe-%D0%B2-appsflyer h_01HA4ZWDM26AVEQKC4CXF18D22=%D1%88%D0%B0%D0%B3-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B8-adobe-%D0%B2-appsflyer h_01HA4ZWDM23A6BFXDV2JH4NR2J=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 step-3-map-data-to-evars-in-adobe-analytics=%D1%88%D0%B0%D0%B3-3-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D1%81-evar-%D0%B2-adobe-analytics h_01HA4ZWDM27S52KY36GS1QPKJ5=%D1%88%D0%B0%D0%B3-3-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D1%81-evar-%D0%B2-adobe-analytics step-4-%5Boptional%5D-set-up-your-marketing-channel=%D1%88%D0%B0%D0%B3-4-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%D0%BE%D0%B3%D0%BE-%D0%BA%D0%B0%D0%BD%D0%B0%D0%BB%D0%B0 h_01HA4ZX6FG6RM5JNDKQP6GVAD1=%D1%88%D0%B0%D0%B3-4-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%D0%BE%D0%B3%D0%BE-%D0%BA%D0%B0%D0%BD%D0%B0%D0%BB%D0%B0 domain-and-security-details=%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BE-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B5-%D0%B8-%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HA4ZWDM2NNFVPP1XYWKPS89A=%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BE-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B5-%D0%B8-%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D0%B8" />

---
title: Интеграция Batch с AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Batch
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
  created_at: '2019-01-28T10:06:24Z'
  edited_at: '2026-10-19T14:08:03Z'
  id: 360000833437
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/360000833437
---
> **At a glance:** Batch — интегрированный партнер AppsFlyer и платформа для аналитики приложений, автоматизации маркетинга и мобильной CRM.

Batch помогает рекламодателям максимально повысить вовлеченность пользователей, обеспечивая при этом персонализированный пользовательский опыт. Передовая платформа Batch для вовлечения пользователей позволяет вам более персонализированно общаться с пользователями смартфонов, снижать отток и повышать ROI вашего приложения. AppsFlyer в сочетании с Batch помогают рекламодателю дополнительно персонализировать пользовательский опыт и вовлеченность на основе пути пользователя. Это означает, что рекламодатель может отправлять определенные сообщения в приложении и push-уведомления на основе данных атрибуции, таких как медиаисточник и кампания. Интеграция Batch с AppsFlyer проста и понятна.

> 🚧 **Important**
>
> **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнеру, независимо от настроенной отправки постбэков.

## Интеграция Batch с AppsFlyer

### Настройка идентификатора Customer User ID

Чтобы Batch мог сопоставлять данные из AppsFlyer со своими собственными данными, рекламодатель должен передавать один и тот же <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid">Customer User ID</Anchor> в обе системы. Идентификатор Customer User ID задается в SDK.

Важно, чтобы вы указали реальный идентификатор пользователя клиента, а не значение-заполнитель. Реальный Customer User ID — это идентификатор пользователя, который вы используете для идентификации своих клиентов в собственных системах.

<Tabs>
<Tab title="Android;">

#### Batch

Задайте Customer User ID в Batch SDK.

```java
Batch.User.editor()
    .setIdentifier("user@example.com")
    .save();
```

#### AppsFlyer:

Задайте Customer User ID в AppsFlyer SDK.

```java
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

<Tabs>
<Tab title="Objective C">

#### Batch

Задайте идентификатор Customer User ID в SDK Batch.

```objectivec
BatchUserDataEditor *editor = [BatchUser editor];
[editor setIdentifier:@"user@example.com"];
[editor save];
```

#### AppsFlyer:

Задайте Customer User ID в SDK AppsFlyer.

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = @"user@example.com";
```

</Tab>

<Tab title="Swift">

#### Batch

Задайте Customer User ID в SDK Batch.

```swift
let editor = BatchUser.editor()
editor.setIdentifier("user@example.com")
editor.save()
```

#### AppsFlyer:

Задайте Customer User ID в SDK AppsFlyer.

```swift
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>
</Tabs>

</Tab>
</Tabs>

### Настройка Batch

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

Для конфигурации Batch требуется только вкладка **Интеграция**. Остальные четыре вкладки неактивны, так как они не требуются для этой интеграции.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

### Activate Partner (Активировать партнера)

При **первом посещении** этой страницы вам нужно перевести кнопку **Activate Partner** в положение «Включено», чтобы можно было настроить параметры вкладки интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

### Общие настройки

Перед настройкой интеграции с Batch обязательно получите **Batch Rest API Key** и **Batch API Key**. Если вы не уверены, [обратитесь в Batch](mailto:hello@batch.com) за дополнительной информацией.  

После получения двух ключей введите каждый из них в соответствующее поле. В разделе **General Settings** введите **Batch Rest API Key** в поле **BATCH\_REST\_API\_KEY**, а **Batch API Key** — в поле **BATCH\_API\_KEY**.

![batch-general-settings-keys.png](https://files.readme.io/fb165253ec81c0ad4ee9569ef928dc63fb476efe6da8fc7c9120d6619b3124c1-360001692717.png)

### Постбэки по умолчанию

В разделе **Default Postbacks** в раскрывающемся списке **Sending Option** выберите **События, атрибутированные любому партнеру или органическому источнику**.

![batch-default-postbacks.png](https://files.readme.io/e3e84f990d7f05c94fb69195a7e57caeffcd1ca35a5fb0148fc6a81ab9816673-360001778958.png)

Нажмите **Save** в правом нижнем углу экрана.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для Batch.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для Batch.

</Accordion>

## Просмотр данных AppsFlyer в дэшборде Batch

Когда AppsFlyer начнет отправлять в Batch постбэки установок, вы сможете просматривать данные в дэшборде Batch и настраивать вовлеченность пользователей на основе данных атрибуции.

Вы можете просмотреть данные на вкладке **Userbase** в дэшборде Batch.

![Userbase.png](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)

<div data-zendesk-anchors="integrating-batch-and-appsflyer=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-batch-%D1%81-appsflyer h_01H9FK389GXG3CDFPNM5ASKJ3N=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-batch-%D1%81-appsflyer setting-customer-user-id=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0-customer-user-id h_01H9FK389MPKFN8J74BX1E3MGG=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0-customer-user-id h_01H9FK389MK1HM1460VAT6X82Y=batch h_01H9FK389MPGNEX8B3923KYDB3=appsflyer batch::28a946d0=batch h_01H9FK389MC4K8PNVPAGC00TBW=batch appsflyer::3f0aa95b=appsflyer h_01H9FK389M7V83A66M6T9EV8QT=appsflyer batch::24c5c955=batch h_01H9FK389MRV4ARHMHXPAXVXQ9=batch appsflyer::deb78dd1=appsflyer h_01H9FK389MT6PD8FW21SYHBPCV=appsflyer setting-up-batch-in-appsflyer-dashboard=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-batch h_01H9FK389MCSR5YDSF4RKFDSDZ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-batch h_01H9FK389MG9459909JZBDN77E=integration-tab activate-partner=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FK389M19AVM63DEX5JTTQK=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FK389MN82EKHVGMM9Z6H58=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FK389MXA3DS403VXRRK5NX=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FK389MERP4XBF19T28E6DN=attribution-link-tab h_01H9FK389M3E05PVMNA83TBFJZ=cost-tab h_01H9FK389M06FEQ4RZJ04HTH33=ad-revenue-tab h_01H9FK389MB31S8BR8WX178GHX=permissions-tab viewing-appsflyer-data-in-the-batch-dashboard=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%B2-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5-batch h_01H9FK389M8BNRFECN0WG23BCD=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%B2-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5-batch" />

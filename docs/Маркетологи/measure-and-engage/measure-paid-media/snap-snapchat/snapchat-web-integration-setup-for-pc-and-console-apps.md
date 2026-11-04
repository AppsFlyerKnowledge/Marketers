---
title: Настройка интеграции Snapchat—Web для приложений для ПК и консолей
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2025-11-28T12:53:35Z'
  edited_at: '2026-09-17T00:30:08Z'
  id: 41396370612497
  locale: ru
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ru/articles/41396370612497
---
> **Краткий обзор:** Узнайте, как интегрировать Snapchat Ads web для приложений для ПК и консолей с AppsFlyer и настроить кампании в Snapchat Ads web.

<div id="warning" />

> ❗️ **Предупреждение**
>
> Эта интеграция доступна только для приложений для ПК и консолей, таких как Steam, Epic или нативный ПК. Для мобильных приложений см. страницу <Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup">настройки интеграции Snapchat Ads</Anchor> .

<div id="overview" />

## Информация о компании

Эта статья содержит информацию и шаги по настройке и использованию Snapchat Ads web для приложений для ПК и консолей с AppsFlyer.

<div id="prerequisite" />

### Необходимое условие

Прежде чем активировать интеграцию Snapchat Ads web, убедитесь, что у вас есть бизнес-аккаунт в <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/topic/0TO8b000000KfssGAC/ads-manager?language=en_US">Snapchat Ads Manager.</Anchor>

<div id="activating-partner-in-appsflyer" />

## Активация партнера в AppsFlyer

**Чтобы активировать партнерскую интеграцию:**

1. В AppsFlyer в боковом меню откройте **Collaborate** > **Partner Integrations > Marketplace** вкладку.
2. Найдите **Snapchat Ads web** (`snapweb_int`).
3. Нажмите **Integrate**. Вы будете перенаправлены на страницу настройки.
4. На вкладке **Интеграция** включите **Активировать партнера**. Переключатель должен оставаться в положении <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активирован</Anchor> всё время, пока вы работаете с партнером.
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе.

<div id="setting-up-snapchat-ads-web-in-appsflyer" />

## Настройка Snapchat Ads web в AppsFlyer

В этой части настройки вы также можете настроить постбэки для Snapchat Ads web через Snapchat Events API. Интеграция Snapchat Ads web (`snapweb_int`) использует инструмент Events API, предоставляемый Snapchat Ads, который позволяет рекламодателям отправлять данные из своих **приложений для ПК и консолей** напрямую на серверы Snapchat. Эти данные могут включать в себя действия пользователей, например покупки, регистрации и другие виды конверсий, выполненные на немобильных платформах (веб-сайты или приложения). Эти данные затем используются в Snapchat Ads для оптимизации таргетинга рекламы, измерения ее эффективности и создания пользовательских аудиторий для ретаргетинга.

Интеграция с Snapchat Ads web поддерживает отправку постбэков только для установок и событий в приложении.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

Вкладка **Интеграция** содержит несколько разделов, описанных ниже.

**Активация партнера**

Чтобы настроить интеграцию, необходимо сначала включить переключатель **Активировать партнера** .

**Общие настройки**

* **Идентификатор пикселя:** Введите идентификатор пикселя. Вы можете создать его или получить в Snapchat Ads Manager, следуя инструкциям из <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">официальной документации Snapchat Ads</Anchor>[.](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)
* **Токен доступа:** Введите токен доступа. Чтобы сгенерировать его или получить, следуйте инструкциям [in](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US) <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">официальной документации Snapchat Ads</Anchor>[.](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

**Активация атрибуции по просмотрам**

AppsFlyer поддерживает атрибуцию по просмотрам для кампаний Snapchat Ads web с использованием вероятностного моделирования (PMOD) и посадочной страницы с поддержкой [Smart Script](#create-a-landing-page-with-onelink-smart-script) или [Smart Banner](#create-a-landing-page-with-onelink-smart-banners)-enabled landing page. Это позволяет AppsFlyer атрибутировать установки приложений, которые происходят после того, как пользователи посмотрели рекламу, а затем установили приложение, даже на разных платформах, без необходимости прямого клика.

Когда пользователь нажимает на рекламу Snapchat в интернете и попадает на посадочную страницу с активированным [Smart Script](#create-a-landing-page-with-onelink-smart-script) или [Smart Banner](#create-a-landing-page-with-onelink-smart-banners)-enabled landing page, AppsFlyer может атрибутировать последующую установку приложения. Если доступно, `ScCid` будет включен в постбэк для Snapchat, чтобы повысить точность атрибуции.

**Активация атрибуции по просмотрам:**

1. В AppsFlyer, в боковой панели откройте **Активные интеграции** > **Snapchat Ads web ads**.
2. На вкладке **Интеграция** прокрутите до раздела **Атрибуция установки**.
3. Включите **Атрибуцию установок по просмотрам**.
4. **[необязательно]** Включите **Равный приоритет кроссплатформенной атрибуции** и задайте для него окно ретроспективы. Более подробно см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Включите равный приоритет для кроссплатформенных показов</Anchor>.
5. Откройте вкладку **Ссылка атрибуции**.
6. Прокрутите к разделу **Атрибуция по просмотрам** и установите **окно атрибуции по просмотрам** (до 24 часов).
7. Нажмите **Сохранить интеграцию** для применения ваших настроек.

**Постбэки по умолчанию**

Постбэки по установкам автоматически отправляются только в Snapchat Ads web.

https://files.readme.io/8d5c3b6d1dd7542860d58b2cff8581a8eb72880764b730a4c87b8161eb04edab-360001712765.png

Настройте сопоставление постбэков по событиям в приложении, отправляемых в Snapchat Ads web. Эти события можно просматривать в [Snapchat Ads Manager](https://businesshelp.snapchat.com/s/topic/0TO8b000000KfssGAC/ads-manager?language=en_US).

1. Активируйте **Постбэки по внутренним событиям приложения**.
2. Нажмите **Добавить событие**. В следующей таблице перечислены и описаны поля:

| **Название параметра** | **Description(Описание)** |
| --- | --- |
| AppsFlyer event (Событие AppsFlyer) | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<ul><li>Нажмите Add item и введите название события.</li></ul> |
| сопоставлено с партнерским событием | Уникальное имя или идентификатор каждого события, определенные партнером.<ul><li>Выберите из списка наиболее подходящее предопределённое событие партнёра.</li></ul> |
| для пользователей от | Только для этого партнера: постбэки по событиям в приложении отправляются только для событий, атрибутированных этому партнеру. |
| Включая | Значения и доход: в постбэке отправляются все параметры события, включая значение дохода (если оно есть в событии). |

3. [Необязательно] Нажмите значок **Add condition** icon to <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события. Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">условные постбэки по событиям в приложении</Anchor>.
4. Задайте **окно постбэка событий в приложении**. Дополнительные сведения см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">in-app event postback window</Anchor>.
5. Нажмите **Сохранить интеграцию**.
6. [Необязательно] После сохранения интеграции, оставаясь на странице конфигурации, вы можете интегрировать с этим партнером другие свои приложения:
   1. <span class="af-ol-a"></span>В левом верхнем углу под именем партнера нажмите на название приложения, чтобы открыть список приложений.
   2. Выберите другое приложение из раскрывающегося списка.
   3. Повторите шаги по интеграции для выбранного приложения.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Генерация ссылки атрибуции в пользовательском интерфейсе AppsFlyer в настоящее время недоступна. Вы можете использовать кроссплатформенную целевую страницу со SmartScript или создать прямую ссылку атрибуции для вашего приложения. См. таблицу ниже.

<Table>
  <thead>
    <tr>
      <th>
        Вариант
      </th>
      <th>
        Действия
      </th>
      <th>
        Кто участвует
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Кроссплатформенная целевая страница
      </td>
      <td>
        **Рекомендуется.** Используйте этот вариант, если ваша кампания продвигает приложение, доступное на нескольких платформах, например Epic и Steam.  
        <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Узнайте о кроссплатформенных целевых страницах</Anchor>  

        <Anchor target="_blank" href="/marketers/ru/docs/cross-platform-landing-pages-with-smart-script">Узнайте, как настроить кроссплатформенную целевую страницу</Anchor>  
        Убедитесь, что все релевантные параметры URL-адреса (которые затем захватываются Smart Script) добавлены в URL-адрес рекламы

        * Убедитесь, что скрипт берет значение `ScCid` из входящего URL-адреса и добавляет его в генерируемую ссылку. Это означает, что нужно сопоставить исходящий параметр URL-адреса `ScCid` с входящим параметром `ScCid`.  
          **Примечание:** Чтобы `ScCid` отображался в отчетах по сырым данным AppsFlyer, входящий параметр `ScCid` также нужно сопоставить с одним из исходящих параметров `af_sub[1–5]`.
        * Необязательно: Вместо того чтобы вручную прописывать значения, можно использовать динамические макросы URL-адресов Snapchat. Дополнительные сведения см. в [официальной документации Snapchat](https://businesshelp.snapchat.com/s/article/add-url-macros?language=en_US).
      </td>
      <td>
        Маркетолог (может потребоваться помощь разработчика)
      </td>
    </tr>
    <tr>
      <td>
        Прямая ссылка атрибуции
      </td>
      <td>
        Если вы не используете кроссплатформенную целевую страницу, потому что у вас есть только одно приложение на одной платформе, вы можете создать прямые ссылки атрибуции для размещения в рекламе.   
        <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor>

        Убедитесь, что в ссылке указаны обязательные параметры:

        * `media_source (медиа-источник)`
        * `af_campaign_id`
        * `af_r`

        **Шаблон для веб-ссылки рекламы Snapchat Ads:**

        ```
        https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}&af_r={encoded landing page and URL params}
        ```

        **Пример ссылки веб-рекламы Snapchat, ведущей в Steam:**

        ```
        https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
        ```

        **Примечание**: шаблон включает некоторые динамические параметры URL-адреса, поддерживаемые Snapchat. При желании вы можете заменить их реальными значениями вручную.
      </td>
      <td>
        Маркетолог
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Стоимость недоступна для Snapchat Ads web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы недоступен для Snapchat Ads web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

В настоящее время разрешения не предоставляются для Snapchat Ads web.

</Accordion>

<div id="setting-up-campaigns-in-snapchat-ads-web-for-pc-and-console-apps" />

## Настройка кампаний в Snapchat Ads web для приложений для ПК и консолей

Настройте свою кампанию в Snapchat Ads Manager. Более подробную информацию см. здесь: <Anchor target="_blank" href="/marketers/ru/docs/snapchat-create-web-based-campaigns#настройте-интеграцию-appsflyer-в-snapchat-ads">Настройка интеграции AppsFlyer в Snapchat Ads</Anchor>.

Когда вы создаете новую кампанию:

* Выберите **Веб-сайт** в качестве места конверсии.
* Когда вы даете название пикселю конверсии Snapchat, введите тот же идентификатор пикселя, который вы ввели для `snapweb_int` в *Партнерский маркетплейс AppsFlyer* .
* Когда вы вводите URL-адрес сайта в качестве пункта назначения объявления, он должен быть одним из следующих:
  * Целевая страница на сайте (рекомендуется, если приложение работает на нескольких платформах)
  * URL-адрес магазина (рекомендуется, если ваше приложение находится в одном магазине приложений на одной платформе)

<div id="view-web-to-app-attribution-data" />

## Посмотреть данные атрибуции web-to-app

Хотя события конверсии на вебе отправляются в Snapchat с исходным PID `snapweb_int`, на дэшборде AppsFlyer и в отчетах о сырых данных они отображаются под PID `snapchat_int`. Это относится как к основным событиям конверсии, так и к событиям-ассистам конверсии.

Этот унифицированный вид отчетов позволяет анализировать эффективность веб-кампаний и кампаний приложений в одном месте, включая подробную отчетность о стоимости для мобильных устройств и веба.

<div id="view-in-the-dashboard" />

### Посмотреть на дэшборде

Вся атрибуция Snapchat web-to-app отображается как `snapchat_int` на дэшбордах «Обзор» и «Активность». Это обеспечивает единое, консолидированное представление результатов кампаний на разных платформах. Используйте стандартные фильтры и разбивки, чтобы сравнить трафик приложения и веб-трафик в данных Snapchat Ads.

<div id="view-in-raw-data-and-api-reports" />

### Просмотр в отчетах о сырых данных и отчетах API

* **Экспорты сырых данных и ответы API** включают PID `snapchat_int` в поле `media_source` для активности Snapchat на вебе. Чтобы проверить детали настройки веб-кампании, обратитесь к полю `original_url`, в котором `snapweb_int` указан как PID, использованный при создании веб-кампаний.
* **Отчеты о постбэках** показывают `snapweb_int` как исходный медиаисточник, на который был отправлен постбэк.

<div id="traits-and-limitations" />

## Спецификации и ограничения

| Специфика | Описание |
| --- | --- |
| Клики и показы (Временное ограничение) | Данные о кликах и показах для кампаний с таргетингом на приложения для ПК & консолей временно недоступны в Snapchat SRN. |

<div data-zendesk-anchors="h_01KB58BEK73PMXZXB8RA59YHM2=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01KB58BEK78P4C35JYZXKJFPHW=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 prerequisite=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 h_01KB58BEK77YP1T2XCHZJ00V7S=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 activating-partner-in-appsflyer=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-%D0%B2-appsflyer h_01KB58BEK7A3MJT4C9ZA9ZFGDA=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-%D0%B2-appsflyer setting-up-snapchat-ads-web-in-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-snapchat-ads-web-%D0%B2-appsflyer h_01KB58BEK7CGYB1DZJCG2WMH0Y=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-snapchat-ads-web-%D0%B2-appsflyer h_01KB58BEK7SE837F67MKRFY6K2=integration-tab h_01KB58BEK74Q2K3SNCPFQSCJ2B=attribution-link-tab h_01KB58BEK7WAVABV4YBR728FCF=cost-tab h_01KB58BEK7ESEZFARRQ3HB6P8H=ad-revenue-tab h_01KB58BEK7WXEFMSSB0QRE4E6B=permissions-tab setting-up-campaigns-in-snapchat-ads-web-for-pc-and-console-apps=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-snapchat-ads-web-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BA-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B5%D0%B9 h_01KB58BEK7D8760J2ZWJ9B1K3Y=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-snapchat-ads-web-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BA-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B5%D0%B9 view-webtoapp-attribution-data=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app h_01KB58BEK7M96WYN7YMERH7CWW=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-in-the-dashboard=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 h_01KB58BEK70FB5SYQAV938CB5W=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 view-in-raw-data-and-api-reports=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-api h_01KB58BEK7YWM10A7RCNV7YDEM=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-api traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KB58BEK7MDZGT7G7RQ9VK9MZ=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

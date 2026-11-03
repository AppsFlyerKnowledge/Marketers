---
title: Настройка кампании Sina Weibo Ads
metadata:
  keywords:
    - Advertisers
    - Sina Weibo Ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-08-15T08:37:03Z'
  edited_at: '2026-09-17T00:26:30Z'
  id: 115004134086
  locale: ru
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ru/articles/115004134086
---
> **Краткий обзор:** Sina Weibo Ads, интегрированный партнер AppsFlyer среди рекламных сетей, — одна из самых популярных платформ социальных сетей в Китае.

## Настройка Sina Weibo Ads

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнеров**.  
   Чтобы отредактировать: Выберите **Совместная работа** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.  
    **Обратите внимание:** Переключатель должен оставаться включённым (активированным) всё время, пока вы работаете с партнёром. Этот переключатель должен быть <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">включен</Anchor> все время, пока вы работаете с этим партнером.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Для подробного описания заголовка окна для конфигурации партнера, нажмите <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

В окне настроек Sina Weibo Ads есть 3 активные вкладки: Integration, Attribution link и Permissions. Чтобы ознакомиться с настройками этих вкладок, нажмите на названия пунктов ниже.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

Этот раздел используется для подключения партнера к AppsFlyer. Здесь также отображаются сообщения рекламодателю относительно конкретного партнера.

### Активация партнеров

При **первом посещении** вам нужно перевести кнопку ***Активировать партнера*** в положение «ВКЛ», чтобы включить настройку параметров вкладки интеграции. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

Постбэки по умолчанию

Если для партнера активирована атрибуция или интеграция, AppsFlyer может автоматически отправлять ему постбэки после установок, запуска приложения, повторного вовлечения или отклонения установок. В этом разделе можно определить **источник пользователей**, для которых отправляются постбэки.

![Sina_Weibo_msc_new_2.png](https://files.readme.io/0f71568fd13ce9357f07282636e0b86fdbb9e9b1f6ef9db8ba673bb2066881aa-360002277585.png)

Параметр "**Only events attributed to this partner**" для пользователей, атрибутированных только этому партнеру, выбран по умолчанию.

Нажмите **Save** (Сохранить).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Эта вкладка позволяет создать для приложения ссылки атрибуции, которые нужно передать в Sina Weibo Ads для атрибуции кампаний, групп объявлений и даже отдельных объявлений Sina Weibo Ads. Обратите внимание, что AppsFlyer НЕ сохраняет ссылки атрибуции, созданные для вашего партнера.

На этой вкладке есть несколько разделов:

### Параметры ссылки атрибуции

В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

Здесь можно задавать дополнительные параметры ссылки атрибуции, чтобы затем использовать их для детального анализа. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* **Campaign** - добавьте этот параметр, чтобы сравнивать различные кампании, запущенные в Sina Weibo Ads.  
  **Параметр ссылки атрибуции:** c
* **Adset** - задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках отдельных кампаний Sina Weibo Ads.  
  **Параметр ссылки атрибуции:** af\_adset
* **Ad Name** - задайте названия групп объявлений, чтобы сравнивать разные креативы в определенных группах объявлений в рамках отдельных кампаний Sina Weibo Ads.  
  **Параметр ссылки атрибуции:** af\_ad
* **Site ID** и **Sub Site ID** — задайте параметр Site ID, чтобы атрибутировать установки определенным паблишерам. При наличии большого количества издателей рекомендуется ограничить количество используемых идентификаторов сайтов и использовать параметр идентификатора подсайта, чтобы избежать <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">превышения допустимого количества идентификаторов сайтов</Anchor>.  
  **Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* **Subscriber Parameters** - используйте любой из 5 параметров подписчика для вставки полезных значений. Обратите внимание, что эти параметры анализируются и отображаются в отчете о сырых данных, что делает их очень удобными для агрегации или фильтрации данных.  
  **Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

[![](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)

Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**Структура и параметры ссылки атрибуции в AppsFlyer**</Anchor>.

### Настройки ретаргетинга

Если нужно добавить в ссылку атрибуции еще какой-либо параметр, просто введите его в поле нового параметра. Все доступные в AppsFlyer параметры URL-адресов приведены в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**Структура и параметры ссылки атрибуции в AppsFlyer**</Anchor>

Если этот параметр включен, AppsFlyer распознает ссылку как ссылку атрибуции для <Anchor target="_blank" href="/marketers/ru/docs/retargeting-attribution-guide">ретаргетинга</Anchor>, а не как ссылку для привлечения пользователей, добавляя `&is_retargeting=true` в ссылку регистрации клика. Обратите внимание, что ретаргетинг в данное время поддерживается только для атрибуции по нажатиям, а для атрибуции по просмотрам — нет.

**Параметр ссылки атрибуции**: `is_retargeting`

Когда ретаргетинг включен, отображаются следующие настройки.

![retargeting_settings.png](https://files.readme.io/b90bbd6e3bea9dd862808343896b005071b7d9e564d31039c188c3ebf8e81077-360002254489.png)

***Стандартная ссылка*** **vs.** ***OneLink***

Выберите вариант ***стандартная ссылка атрибуции***, если:

* URL-адрес не будет использоваться в качестве глубинной ссылки или
* Вы планируете использовать только <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">схемы URI</Anchor> для диплинкинга

Выберите вариант ***Use OneLink*** для:

* Для приложений на Android и iOS используется одна и та же ссылка или
* Для диплинкинга используются универсальные ссылки или ссылки приложений

Обратите внимание, что при выборе OneLink ссылка для регистрации кликов меняется со ссылки для конкретного приложения на <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">URL-адрес OneLink</Anchor>.

***URL-адрес диплинка***

Используйте это поле, если ссылка предназначена для прямого перехода пользователей к какому-либо конкретному действию в вашем приложении.  
**Параметр ссылки атрибуции**: `af_dp`  
Подробную информацию о <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">решении AppsFlyer для диплинкинга см. в этом руководстве</Anchor>

***Окно повторного вовлечения***

Задайте временной интервал после повторного вовлечения, в течение которого внутренние события приложения пользователя будут атрибутироваться медиа-источнику ретаргетинга. Вы можете задать ценность, значение в днях (1-90), часах (до 23) или даже на весь период.

**Параметр ссылки атрибуции**: `af_reengagement_window`

Прочитайте [как настроить ретаргетинг](/docs/sina-weibo-ads-campaign-configuration#создание-ретаргетинговых-кампаний-на-дэшборде-weibo-ads) на дэшборде Sina Weibo.

### Атрибуция по кликам

Этот ползунок позволяет задать **максимальное время от клика до установки**. К Sina Weibo Ads могут быть атрибутированы только установки (первые запуски), которые происходят в течение окна атрибуции/лукбэка.

**Параметр ссылки атрибуции:** af\_click\_lookback

Подробные сведения об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">окне атрибуции по кликам см. здесь</Anchor>.

[![настройки переходов по кликам Sina Weibo](https://files.readme.io/2c6cba9eba0b01cba638707df6bdb94c1a78b4d2b98f65d5210538311458b763-360002715417.png)](https://files.readme.io/2c6cba9eba0b01cba638707df6bdb94c1a78b4d2b98f65d5210538311458b763-360002715417.png)

### Ссылка атрибуции для клика

Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в Sina Weibo Ads, чтобы она активировалась, когда потенциальные клиенты нажимают на соответствующее объявление.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Интеграция затрат недоступна для Sina Weibo Ads.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Этот партнер не поддерживает данные о доходах от рекламы.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

На этой вкладке можно выбрать разрешения, предоставляемые партнеру, в зависимости от того, в каком качестве он действует: рекламной сети, агентства или в обоих. Обратите внимание на то, что, даже если атрибуция для партнера отключена, вкладка разрешений остается активной и вы можете предоставить партнеру разрешение на управление.

![sina-weibo-permissions.png](https://files.readme.io/a22be58687921e80108fe4b2cbd2863d9277a938a751ed5c666f147d78041c05-360002799478.png)

Эти переключатели позволяют предоставить рекламной сети право самостоятельно выполнять настройки для вашего приложения:

* ***Разрешить настройку интеграции*** — разрешить партнеру настраивать вкладку интеграции (за исключением постбэков по внутренним событиям приложения).
* ***Разрешить настройку постбэков по внутренним событиям приложения*** — разрешить партнеру настраивать постбэки по внутренним событиям и отображать эти настройки на вкладке интеграции.
* ***Разрешить доступ к своему отчету об удержании*** — доступ предоставляется только к собственным данным партнера.
* ***Разрешить доступ к своим сводным данным о лояльных пользователях*** — доступ предоставляется только к собственным данным партнера.
* ***Разрешить доступ к своим сводным данным о внутренних событиях приложения*** — доступ предоставляется только к собственным данным партнера.
* ***Разрешить доступ к своим сводным данным о доходах*** — доступ предоставляется только к данным о доходах, атрибутированных партнеру.
* ***Разрешить доступ к панели управления Protect360*** — доступ предоставляется только к собственным данным Protect360 этого партнера, при условии что эта функция активирована для рекламодателя.

См. дополнительные сведения о предоставлении <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">разрешений рекламной сети</Anchor>.

</Accordion>

## Настройка атрибуции AppsFlyer на дэшборде Weibo Ads

Войдите в Sina Weibo Ads по этой ссылке: [https://ad.weibo.com/](https://ad.weibo.com)

Перейдите на страницу **Tools**, чтобы загрузить свои приложения в разделе управления приложениями:

[![](https://files.readme.io/56d413ce75a2a3b4ca78a6928f60b9898bbd892d43d370197189da66ef9b078b-360000449769.png)](https://files.readme.io/56d413ce75a2a3b4ca78a6928f60b9898bbd892d43d370197189da66ef9b078b-360000449769.png)

Нажмите, чтобы добавить новые приложения:

[![](https://files.readme.io/2c372745a5fe9b05325731e29e24f0b5097a43664e9a28e288d0b9300aecee8e-360000441885.png)](https://files.readme.io/2c372745a5fe9b05325731e29e24f0b5097a43664e9a28e288d0b9300aecee8e-360000441885.png)

Android: введите ссылку на страницу загрузки APK (должна оканчиваться на .apk) или загрузите APK-файл.

iOS: введите ссылку на iTunes.

### Настройка ссылки атрибуции

Перейдите на страницу **Промоакции** и создайте новую серию объявлений

[![](https://files.readme.io/eaf980c1adc0b134265162c114f66b1bf049a80336116db76d353ee5113a9ae5-360000449909.png)](https://files.readme.io/eaf980c1adc0b134265162c114f66b1bf049a80336116db76d353ee5113a9ae5-360000449909.png)

Если вы хотите привлечь новых пользователей для своего приложения, выберите тип рекламы **Increase App Installs**, как показано ниже:

[![](https://files.readme.io/b9e75ac4c9681cebfa06ba6965032b1ff0dc11b2da6e8c2b11cc9219555fa4e7-360000442105.png)](https://files.readme.io/b9e75ac4c9681cebfa06ba6965032b1ff0dc11b2da6e8c2b11cc9219555fa4e7-360000442105.png)

### Настройка серии объявлений

Выберите приложение, которое хотите продвигать:

[![](https://files.readme.io/cf9697b09d8d8b5416b8029cb20c2137eda24d9616bf2db2e1e45a3ec150fcf3-360000450049.png)](https://files.readme.io/cf9697b09d8d8b5416b8029cb20c2137eda24d9616bf2db2e1e45a3ec150fcf3-360000450049.png)

Задайте характеристики аудитории, бюджет и периоды продвижения:

[![](https://files.readme.io/709297bb78cbd48218ee5438a40a5a12e78eeeecf4e35414ec36de89420791b6-360000442205.png)](https://files.readme.io/709297bb78cbd48218ee5438a40a5a12e78eeeecf4e35414ec36de89420791b6-360000442205.png)

### Загрузка рекламных креативов и настройка ссылки атрибуции

Weibo предлагает четыре формата рекламы для продвижения установок приложения:

* Публикация в Weibo
* Большие карточки
* Карточка приложения
* 9 изображений приложения

Все форматы рекламы поддерживают атрибуцию AppsFlyer.

[![](https://files.readme.io/5404349a21a783509e6de074826ace0db0d66248853f229ad444fabec95b8311-360000450369.png)](https://files.readme.io/5404349a21a783509e6de074826ace0db0d66248853f229ad444fabec95b8311-360000450369.png)

Введите ссылку атрибуции AppsFlyer

> 📄 **Пример**
>
> ```http
> https://app.appsflyer.com/com.king.candycrushsaga?pid=sinaweibo_int&c=creative1
> 	&clickid={IMP}&md5_idfa={idfa_MD5}&md5_imei={imei_MD5}&redirect=false
> ```

[![](https://files.readme.io/27113a1303fea22bde74527c7103bfbda8e8fd7755c44a52508a02368e0a6407-360000442725.png)](https://files.readme.io/27113a1303fea22bde74527c7103bfbda8e8fd7755c44a52508a02368e0a6407-360000442725.png)

Завершите все дополнительные настройки и опубликуйте рекламное объявление.

> 📘 **Примечание:**
>
> * Вы можете просмотреть формат рекламы в правой верхней части страницы Ad Creative Setting.
> * Если вы не используете диплинкинг в рекламной кампании, оставьте поле глубокой ссылки пустым.

## Создание ретаргетинговых кампаний на дэшборде Weibo Ads

На уровне рекламной кампании настройте таргетинг, бюджет и продолжительность кампании:

![sina-weibo-retargeting.png](https://files.readme.io/8225fbfd74d16bb1a3e2e816933cb22d5f581a219ee35dd7f9d5285bacd49d2d-360002715577.png)

На уровне рекламного объявления настройте глубокую ссылку и ссылку атрибуции AppsFlyer:

1. Выберите ***deeplink+app*** и вставьте глубокую ссылку в соответствующее поле:

   ![sina-weibo-retargeting-deeplink.png](https://files.readme.io/dc5666893ff99dcb808a15aa2e41396b359617e2f6271f246a10893d4b05eebe-360002715557.png)

   > 📄 **Пример**
   >
   > ```http
   > myapp://products/page1&pid=sinaweibo_int&is_retargeting=true
   > ```

2. Скопируйте ссылку атрибуции с дэшборда AppsFlyer со всеми необходимыми параметрами и вставьте ее в поле ссылки атрибуции:

   ![sina-weibo-retargeting-links.png](https://files.readme.io/edd0861728e19a0bc0e23641161c2365cf5c41eeccaa801bd4e8c3392215fe83-360002799598.png)

   > 📄 **Пример**
   >
   > ```http
   > https://app.appsflyer.com/com.mycompany.myapp?pid=sinaweibo_int&c=test&clickid={IMP}
   > &md5_idfa={idfa_MD5}&md5_imei={imei_MD5}&redirect=false&is_retargeting=true
   > ```


   > 📘 **Примечание:**
   >
   > Обратите внимание: все следующие параметры должны быть включены и в глубокую ссылку, и в ссылку атрибуции и должны быть одинаковыми в обеих ссылках:
   >
   > * `&pid=sinaweibo_int` — параметр идентификатора партнера, который определяет Sina Weibo как медиаисточник
   > * `&c=campaign_name` — параметр, который определяет конкретную кампанию
   > * `&is_retargeting=true` — параметр, который определяет рекламу как часть кампании ретаргетинга
   >
   > Если вы используете отложенный диплинкинг, также добавьте следующие параметры:
   >
   > * `&af_adset=adset_name`
   > * `&af_ad=ad_name`
   >
   > Подробнее читайте в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Структура ссылки атрибуции AppsFlyer и параметры</Anchor> и о [ссылках атрибуции](#attribution-link-tab) Sina Weibo.

<div data-zendesk-anchors="setting-up-sina-weibo-ads=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-sina-weibo-ads h_01HKW6X6G9WGKHT7MXM3BKYX40=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-sina-weibo-ads h_01HKW6X6G9865NFC261ZCPC4AM=integration-tab activate-partners=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 h_01HKW6X6G98F7ERDGKN7K5PDVE=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 h_01HKW6X6GAR48FSFX7DVEWAMX8=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6X6GA0FPN5EMR68FH2HSR=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 retargeting-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 h_01HKW6X6GA287ZKAWG69497WRN=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HKW6X6GABBB9ZP8GP87JYZAE=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC click-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 h_01HKW6X6GAY9GP9P57RFPSFTVN=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 h_01HKW6X6GADFS59WJT2GHYQ317=cost-tab h_01HKW6X6GAG7TM4WFNJFHGY9QN=ad-revenue-tab h_01HKW6X6GAK8PN5PBFPZTGC0ES=permissions-tab setting-appsflyer-attribution-on-weibo-ads-dashboard=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-appsflyer-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5-weibo-ads h_01HKW6X6GA96QHGJY220JF5DF4=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-appsflyer-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5-weibo-ads setting-the-attribution-link=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6X6GA6XJSV02NTNDSRZ19=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 setup-ad-series=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D0%B5%D1%80%D0%B8%D0%B8-%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9 h_01HKW6X6GAJBYM89RYH65BAVNH=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D0%B5%D1%80%D0%B8%D0%B8-%D0%BE%D0%B1%D1%8A%D1%8F%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9 uploading-ad-creatives-and-set-the-attribution-link=%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D1%85-%D0%BA%D1%80%D0%B5%D0%B0%D1%82%D0%B8%D0%B2%D0%BE%D0%B2-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6X6GC2RHPJXWZAX8S758B=%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D1%85-%D0%BA%D1%80%D0%B5%D0%B0%D1%82%D0%B8%D0%B2%D0%BE%D0%B2-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HKW6X6GCNS88DFZTMM7BXMKT=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01HKW6X6GCBQNG4Q2RHJPCRCKS=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 creating-retargeting-campaigns-on-weibo-ads-dashboard=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%D1%8B%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5-weibo-ads h_01HKW6X6GE2RVQGSN9JM63SZYA=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%D1%8B%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5-weibo-ads h_01HKW6X6GEKZWAPZ6V2EXGY9SA=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-1 h_01HKW6X6GFQQSY19CRREVR8GRY=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-2 h_01HKW6X6GF815M1XE9HF631F1W=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1" />

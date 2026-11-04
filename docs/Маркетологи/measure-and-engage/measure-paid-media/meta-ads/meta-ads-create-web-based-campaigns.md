---
title: Meta Ads — Создавайте веб-кампании
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-04T16:08:28Z'
  edited_at: '2026-09-17T00:28:27Z'
  id: 25646834966033
  locale: ru
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ru/articles/25646834966033
---
> **Краткий обзор:** Используйте веб-кампании Meta Ads для атрибуции конверсий с веб-сайта в приложение из Meta Ads

<div id="overview" />

## Обзор

AppsFlyer поддерживает интеграцию с Meta Ads (`metaweb_int`) для веб-кампаний по UA, что позволяет вам передавать данные об атрибуции и конверсии напрямую через Meta Conversion API (CAPI). Meta затем может использовать эти данные \для оптимизации таргетинга рекламы, измерения эффективности и создания пользовательских аудиторий.

<div id="note" />

> 📘 **Примечание:**
>
> На данный момент интеграция с Meta Web не поддерживает отправку повторных постбэков в CAPI.

<div id="prerequisites" />

### Необходимые условия

Прежде чем активировать интеграцию Meta Ads, убедитесь, что у вас есть [бизнес-аккаунт в Meta Business Manager](https://www.facebook.com/business/help/1710077379203657?id=180505742745347).

<div id="how-to-create-a-meta-web-ads-campaign" />

### Как создать рекламную кампанию Meta Web Ads

Эта статья содержит информацию и пошаговые инструкции по настройке веб-кампании в Meta Ads для мобильных устройств, ПК и приложений для консолей с помощью AppsFlyer. Настройка включает в себя определение интеграции между Meta Ads и AppsFlyer, настройку конфигурации кампании на обеих платформах и создание посадочных страниц с помощью OneLink Smart Script или OneLink Smart Banners.  
Процесс настройки включает в себя следующие обязательные этапы:

* [Настройте интеграцию Meta Web Ads в AppsFlyer](#настройка-интеграции-meta-web-ads-в-appsflyer) (обязательно)
* [Настройте интеграцию AppsFlyer в Meta Ads](#настройка-интеграции-с-appsflyer-в-meta-ads) (обязательно)

И следующие необязательные шаги:

* [Создайте целевую страницу с помощью OneLink Smart Script](#создание-целевой-страницы-с-помощью-onelink-smart-script) (необязательно)
* [Создайте целевую страницу с помощью смарт-баннеров OneLink](#создание-целевой-страницы-с-помощью-смарт-баннеров-onelink) (необязательно)

<div id="set-up-meta-web-ads-integration-in-appsflyer" />

## Настройка интеграции Meta Web Ads в AppsFlyer

Начните с активации интеграции Meta Ads и настройки постбэков, которые AppsFlyer отправляет в CAPI.

<div id="a-activate-the-meta-ads-integration" />

<Accordion title="1. Активация интеграции Meta Web Ads">

Чтобы активировать интеграцию Meta Web Ads:

1. В AppsFlyer в боковом меню перейдите в **Сотрудничество** > **Партнерские интеграции** > **Partner Marketplace**.
2. Найдите и выберите **Meta Web**. Вы будете перенаправлены на страницу установки.
3. На вкладке **Интеграция** включите переключатель **Активировать партнера**. **Примечание: <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Переключатель должен оставаться включённым (</Anchor><Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активированным</Anchor>) всё время, пока вы работаете с партнёром.**
4. Отключите опцию **Расширенная конфиденциальность** (если вы настраиваете интеграцию приложения iOS).
5. **Обмен данными расширенного сопоставления:** Включите, чтобы передавать в Meta поля расширенного сопоставления, такие как хэшированные адрес электронной почты, номер телефона, имя и фамилия, а также идентификатор ID для входа в Facebook, если эти поля включены в данные о событии, отправляемые в AppsFlyer. Более подробную информацию см. здесь: <Anchor target="_blank" href="/marketers/ru/docs/advanced-matching-data-sharing">Обмен данными с расширенным сопоставлением</Anchor>.
6. Заполните поле **Идентификатор пикселя** . Вы можете получить идентификатор пикселя из своего менеджера Meta ads Manager:
   1. В боковом меню [Ads manager](https://www.facebook.com/ads/manager) перейдите в раздел **All tools** (Все инструменты) > **Events Manager**. **Примечание:** Убедитесь, что в выпадающем списке справа вверху выбран нужный бизнес.
   2. В боковом меню **Events Manager** выберите **Data sources** (Источники данных). Вы увидите список пикселей. Если у вас нет пикселя для выбранного бизнеса, вы можете создать его в том же окне.
   3. Скопируйте идентификатор пикселя, указанный под именем пикселя,  
      и вставьте его в  
      поле **Идентификатора пикселя** в AppsFlyer.Скопируйте идентификатор пикселя, указанный под именем пикселя,  
      и вставьте его в  
      поле **Идентификатора пикселя** в AppsFlyer.и вставьте его в поле  
      **Pixel ID** в AppsFlyer.
7. Заполните поле **Токен доступа** . Чтобы получить токен доступа, следуйте[этим инструкциям.](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)
8. Включите опцию **Ограничить использование Meta Ads личной информации пользователей (CCPA)**, чтобы обеспечить соблюдение <Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests">законов о защите данных</Anchor>. **Примечание:** Закон CCPA ограничивает использование данных, которые поступают от пользователей Meta Ads, находящихся в штате Калифорния (США).

</Accordion>

<div id="d-enable-view-through-attribution-for-meta-web" />

<Accordion title="2. Активация атрибуции по просмотрам">

AppsFlyer поддерживает атрибуцию по просмотрам для веб-кампаний в Meta с использованием посадочной страницы с активированными [смарт-скриптами](#set-up-smart-script-crossplatform-landing-page) или [смарт-баннерами](#set-up-smart-banners-landing-page). Это позволяет применять атрибуцию установок на основе вероятностного моделирования (PMOD) для установок, вызванных показами рекламы, даже если пользователи не переходят по объявлению напрямую.

Когда пользователь нажимает на рекламу Meta Web и попадает на посадочную страницу с активированным [Smart Script](#set-up-smart-script-crossplatform-landing-page) или [Smart Banner](#set-up-smart-banners-landing-page), AppsFlyer может атрибутировать вторичную установку приложения. Если доступно, в постбэк к Meta будет включён параметр `fbclid` для повышения точности атрибуции.

**Активация атрибуции по просмотрам через Meta Web:**

1. В AppsFlyer на боковой панели откройте **Сотрудничество** > **Партнерские интеграции > Активные интеграции** > **Meta web ads**.
2. На вкладке **Интеграция** прокрутите до раздела **Атрибуция установки**.
3. Включите **Атрибуцию установок по просмотрам**.
4. **[необязательно]** Включите **Равный приоритет кросс-платформенной атрибуции** и установите для него окно атрибуции. Более подробно см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Включите равный приоритет для кроссплатформенных показов</Anchor>.
5. Откройте вкладку **Ссылка атрибуции**.
6. Прокрутите к разделу **Атрибуция по просмотрам** и установите **окно атрибуции по просмотрам** (до 24 часов).
7. Нажмите **Сохранить интеграцию** для применения ваших настроек.

</Accordion>

<div id="b-set-inapp-event-postbacks" />

<Accordion title="3. Настройка постбэков по внутренним событиям приложений">

В настоящее время установки являются единственными событиями, которые запускают автоматические постбэки в Meta Ads по умолчанию. Для других типов событий вы можете создавать пользовательские постбэки, сопоставляя события AppsFlyer с событиями Meta Ads, которые можно просматривать в [Meta Events Manager](https://www.facebook.com/business/help/1541268312717919?id=818859032317965).  
Для настройки постбэков по внутренним событиям приложения выполните следующие действия:

1. Активируйте **Постбэки по внутренним событиям приложения**.
2. При необходимости установите окно постбэков по внутренним событиям приложения (подробнее о настройке окна постбэков по внутренним событиям приложения в целом читайте в <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">этой статье</Anchor>).
3. Нажмите**Добавить событие**, чтобы добавить событие в список.
4. В столбце **События AppsFlyer** выберите название события из выпадающего списка. AppsFlyer получает имя события либо из SDK, интегрированного в ваше приложение, либо из межсерверных событий.
5. В столбце, **сопоставленном с партнерским событием,** выберите из выпадающего списка самое подходящее предварительно заданное партнерское событие или опцию ПОЛЬЗОВАТЕЛЬСКОЕ.
6. В столбце **«Для пользователей из»** выберите вариант отправки для события:
   * **Только этот партнер**: отправляйте постбэки только если это событие атрибутировано Meta Ads.
   * **Все медиа-источники, включая органические** отправляют постбэки для событий, атрибутированных любому партнёру, а также для органических событий
7. В колонке **включая** выберите, будут ли события отправляться со своими значениями дохода. См. <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#данные-для-включения-в-постбэки">Данные для включения в постбэки</Anchor>.

   <div id="note-1" />

   > 📘 **Примечание:**
   >
   > Если вы настраиваете событие покупки, установите колонку **включая** на **Значения и доход**. Выбор любого другого варианта приведет к сбою в отправке постбэка.

8. [Необязательно] Нажмите на значок **Добавить условие**, чтобы<Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события.
9. Нажмите **Сохранить интеграцию**.
10. [Необязательно] После сохранения интеграции, оставаясь на странице конфигурации, вы можете интегрировать с этим партнером другие свои приложения:
    1. В верхнем левом углу нажмите на название приложения под названием партнера, чтобы открыть список приложений.
    2. Выберите другое приложение из раскрывающегося списка.
    3. Повторите шаги по интеграции для выбранного приложения.

<div id="note-2" />

> 📘 **Примечание**
>
> Если вы отправляете события S2S в `metaweb_int`, нагрузка S2S должна включать параметры `ua` (агент пользователя) и `ip` (IP- адрес). Эти значения необходимы для оптимизации кампании Meta CAPI. AppsFlyer включает их автоматически для событий SDK. Что касается S2S-событий, рекламодатели должны отправлять их напрямую. <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">API событий от сервера к серверу для мобильных приложений</Anchor>.

</Accordion>

<div id="set-up-appsflyer-integration-in-meta-ads" />

## Настройка интеграции с AppsFlyer в Meta Ads

Выполните следующие шаги в Meta Ads Manager.

<div id="a-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Установите тип, цель и задачи кампании">

1. Войдите в Meta Ads и создайте кампанию.
2. В поле **Campaign objective** (Цель кампании) выберите один из следующих вариантов: [![](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)
   * **Sales** (Продажи): цель позволяет Meta оптимизировать конкретное событие (ваш основной KPI).
   * **Traffic** (Трафик): цель позволяет Meta оптимизировать клики по рекламе. Эту цель следует использовать только в том случае, если у вас нет других KPI или если объем других KPI слишком мал.
3. [Необязательно] Если вы хотите добавить пользовательскую цель к указанным выше параметрам, выполните следующие действия:
   1. В Meta Ads выберите пользовательское событие, которое вы хотите установить в качестве цели кампании, и отметьте его как действие конверсии в Meta Ads.
   2. В AppsFlyer на странице **Интеграция Meta Web** в разделе **Постбэки по внутренним событиям приложения** сопоставьте событие AppsFlyer с пользовательским партнерским событием (в столбце, **сопоставленным с партнерским событием**) и назовите его тем же именем, что и действие конверсии в Meta Ads.

      <div id="note-3" />

      > 📘 **Примечание:**
      >
      > Дополнительную информацию о целях кампании Meta см. в [документации Meta](https://www.facebook.com/business/help/175683976191028).

4. В поле **Место конверсии** выберите **Веб-сайт**. [![](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)](https://files.readme.io/32e4dcb4ced7e2011728ed709069b78cffffc4090f09a33c729a2b2e7e882e8b-25646834954257.png)
5. В поле **Пиксель** введите тот же идентификатор пикселя, который вы ввели для `metaweb_int` на маркетплейсе партнеров AppsFlyer. Более подробная информация о пикселе Meta приведена в [документации Meta](https://www.facebook.com/business/help/742478679120153) (необходимо войти в систему).
6. Нажмите **Далее**.

</Accordion>

<div id="b-set-destination-url" />

<Accordion title="2. Настройка целевого URL-адреса">

1. В поле **назначения** **URL-адреса веб-сайта** введите URL-адрес, который будет использоваться в качестве назначения для вашей рекламы. URL-адрес должен соответствовать одному из следующих значений:

   [![](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)

   * **Целевая веб-страница:** Использование целевой страницы рекомендуется в следующих случаях:

     * У вас есть приложение на нескольких платформах.
     * Вы хотите использовать целевую страницу для предоставления дополнительной информации о рекламируемом продукте.
     * Вы хотите использовать целевую страницу для сбора дополнительных данных.

     Для всех этих вариантов использования создайте [целевую страницу с помощью Smart Script](#создание-целевой-страницы-с-помощью-onelink-smart-script) или [смарт-баннера](#создание-целевой-страницы-с-помощью-смарт-баннеров-onelink).
   * **Ссылки атрибуции AF** Использование ссылок атрибуции AF (OneLink, одноплатформенных или кроссплатформенных ссылок) рекомендуется в тех случаях, когда вы хотите, чтобы пользователь был перенаправлен непосредственно в магазин для загрузки приложения без предварительного посещения целевой страницы.

     <div id="important" />

     > 🚧 **Важно!**
     >
     > Иногда использование ссылок атрибуции AF может приводить к ошибкам. Если это произошло, обратитесь к представителям Meta за решением или просто используйте целевую веб-страницу в качестве целевого URL-адреса.

2. Нажмите **Создать параметр URL**, чтобы добавить параметры URL в URL (будь то URL-адрес целевой страницы или ссылка атрибуции AF).
3. В разделе **Пользовательские параметры** нажмите **Добавить параметр**.

   [![4.png](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)
4. Сопоставьте параметры AppsFlyer с их значениями Meta.

   * Если ваш целевой URL-адрес является **целевой страницей, ссылкой атрибуции OneLink или одноплатформернной ссылкой атрибуции**, сопоставьте следующие параметры AF с их аналогами в Meta: 

| Параметр AF | Сопоставленное значение Meta |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     Пример итогового URL должен быть таким:

     ```http
     https://app.appsflyer.com/{app_id}?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={https://Add-your-store-url.com}
     ```

     * Если APK вашего приложения НЕ размещен в Google Play Store, добавьте параметр <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> и сопоставьте с ним URL-адрес магазина, например, `https://Add-your-store-url.com`
   * Если ваш целевой URL-адрес — **магазин приложений для ПК или консоли**, создайте ссылку, следуя инструкциям в таблице ниже. Дополнительную информацию см. здесь: <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Прямые ссылки атрибуции для CTV, ПК и платформ для консолей</Anchor>

<table><thead><tr><th colspan="2">Структура ссылки атрибуции</th></tr></thead><tbody><tr><td>Базовый URL-адрес</td><td>engagements.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>Обязательные параметры пути</td><td><ul><li>платформа<br/>Пример: steam</li><li>app_id<br/>Пример: 123456</li></ul></td></tr><tr><td>Обязательные параметры запроса</td><td><ul><li>media_source (медиа-источник)</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>Другие параметры</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#параметры" target="_blank">См. все параметры</a></td></tr><tr><td>Структура URL-адреса</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr></tbody></table>

     Сопоставьте следующие параметры AppsFlyer с их аналогами в Meta:

| Параметр AF | Сопоставленное значение Meta |
| --- | --- |
| `media_source (медиа-источник)` | `metaweb_int` |
| `af_campaign` | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     Пример кроссплатформенного URL:

     ```http
     https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
     ```

   <div id="note-4" />

   > 📘 **Примечание:**
   >
   > Meta добавляет`fbclid={{fbclid}}` к целевому URL-адресу автоматически при нажатии на рекламу


   <div id="tip" />

   > 👍 **Совет.**
   >
   > Чтобы упростить анализ кампании, указывайте тип кампании -- веб или мобайл -- в префиксе или суффиксе названия кампании (например, название-кампании\_web).


<div id="note-5" />

> 📘 **Примечание**
>
> Полное руководство по параметрам ссылки AF см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#параметры-ссылки-атрибуции">Параметры ссылки атрибуции</Anchor>.

</Accordion>

<div id="c-select-tracked-events" />

<Accordion title="3. Выбор отслеживаемых событий">

Используйте раздел «Отслеживание», чтобы выбрать события конверсии, продвигаемые вашей рекламой (настройка событий осуществляется через [Event Manager](https://www.facebook.com/business/help/898185560232180?id=1205376682832142)).

[![](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)

<div id="important-1" />

> 🚧 **Важно!**
>
> Не выбирайте **События приложения**, иначе Meta будет регистрировать эти конверсии с помощью API SRN, что может привести к несоответствиям в отчетах и оптимизации.

</Accordion>

<div id="create-a-landing-page-with-onelink-smart-script" />

## Создание целевой страницы с помощью OneLink Smart Script

**Путь пользователя:** Пользователь нажимает на рекламу Meta и перенаправляется на ваш мобильный сайт. Она или она попадает на страницу с кнопками CTA, призывающими их загрузить ваше приложение с одной или нескольких платформ. Нажатие кнопки перенаправляет пользователя в магазин.

<div id="end-to-end-data-flow" />

<Accordion title="Сквозной поток данных">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. URL-адрес рекламы Meta включает в себя параметр `pid=metaweb_int`. Когда пользователь нажимает на рекламу, параметр `fbclid` автоматически добавляется к URL-адресу, на который нажал пользователь.
2. Пользователь перенаправляется на целевой URL-адрес — целевую страницу, содержащую Smart Script.
3. Когда целевая страница загружается, Smart Script отправляет в AppsFlyer показ с входящими параметрами URL. Показ позволит выполнить атрибуцию просмотров с целевой страницы веб-сайта. Подробнее об атрибуции показов и просмотров читайте <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">здесь</Anchor>.
4. Smart Script генерирует исходящие URL-адреса для кнопок CTA на странице на основе параметров входящего URL-адреса, включая параметр `fbclid`. Кнопки могут вести к следующему:
   * Google Play и App Store через ссылку атрибуции OneLink.
   * Магазины на нескольких платформах (например, CTV, Epic и Steam). В этом случае Smart Script генерирует для каждой платформы одноплатформенную ссылку атрибуции, ведущую в магазин указанной платформы.
   * Загрузка файла APK на устройство пользователя.
5. Когда пользователь нажимает кнопку CTA, клик срабатывает и регистрируется в AppsFlyer.
6. Пользователь перенаправляется в магазин и скачивает приложение.
7. Когда пользователь открывает приложение, в AppsFlyer регистрируется событие установки.
8. AppsFlyer атрибутирует установку на основе вероятностного моделирования или детерминированно, если доступна [реферальная ссылка](https://www.appsflyer.com/glossary/install-referrer/) .
9. Постбэк, содержащий параметры `fbclid` и другие параметры события, генерируется и отправляется в Meta через API CAPI. Meta использует параметр `fbclid` для идентификации конкретного клика, тогда как другие параметры помогают оптимизировать кампанию.

</Accordion>

<div id="set-up-smart-script-landing-page" />

<Accordion title="Настройка целевой страницы Smart Script">

Чтобы настроить кампании Meta Ads при помощи Smart Script, выполните следующие действия:

1. Настройте шаблон атрибуционных ссылок OneLink для кампании. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Как создавать шаблоны OneLink</Anchor>.
2. Создайте Smart Script. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Как создать OneLink Smart Script</Anchor>.

   <div id="note-6" />

   > 📘 **Примечание:**
   >
   > Приведенные ниже инструкции посвящены конкретным шагам, которые необходимы для настройки кампании Meta Ads с помощью Smart Script. Подробное руководство по настройке кампаний Smart Script см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Как создать OneLink Smart Script</Anchor> статьи <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Настройка OneLink Smart Script V2</Anchor> .

3. Убедитесь, что к входящему URL-адресу добавлены все соответствующие параметры URL. Чтобы просмотреть параметры, добавленные к входящему URL-адресу, откройте Meta Ads Manager и проверьте параметры URL-адреса, заданные при создании целевого URL-адреса. Для получения дополнительной информации см. раздел [Настройка целевого URL-адреса](#b-set-destination-url).
4. Сопоставьте параметры входящего URL-адреса, необходимые для кампании Meta Ads, с параметрами исходящего URL-адреса, которые будут отправлены в AppsFlyer, когда пользователь нажмет кнопку CTA:
   * **PID**: Убедитесь, что Smart Script принимает значение параметра `pid=metaweb_int` из входящего URL-адреса и сопоставляет его с соответствующими параметрами в исходящем URL-адресе.
   * **FBCLID**: Параметр `fbclid` крайне важен для успешной отправки постбэков событий в приложении в Meta. Сопоставление параметра FBCLID в исходящем URL зависит от вашей версии Smart Script:

     * Версия 2.8.1 и выше: Параметр `fbclid` автоматически передается в параметр исходящего URL-адреса, если он присутствует во входящем URL-адресе, что устраняет необходимость сопоставления вручную.
     * Версия 2.8.0 и ниже: Параметр `fbclid` должен быть сопоставлен вручную в разделе **Сопоставление параметров URL** на странице **Smart Script**:
       1. Выберите **Пользовательский параметр** в разделе **Сопоставление для**.
       2. Введите **fbclid** в **Параметр исходящего URL** и **Входящий URL**.

     <div id="note-7" />

     > 📘 **Примечание:**
     >
     > Для отображения в отчетах по необработанным данным AppsFlyer входящий параметр `fbclid` также должен быть сопоставлен (в дополнение к исходящему параметру `fbclid`) с одним из исходящих параметров `af_sub[1-5]`. Более подробную информацию можно найти на странице <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">Facebook FBCLID</Anchor>.


</Accordion>

<div id="set-up-smart-script-crossplatform-landing-page" />

<Accordion title="Настройка кроссплатформенной целевой страницы Smart Script">

Чтобы настроить кампании Meta Ads при помощи Smart Script для кроссплатформенных целевых страниц, выполните следующие действия:

1. Настройте шаблон атрибуционных ссылок OneLink для кампании. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Как создавать шаблоны OneLink</Anchor>.
   * Активируйте шаблон OneLink для кроссплатформенной атрибуции, см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-cross-platform-links-for-multi-device-campaigns#создание-шаблона-onelink-для-кроссплатформенной-атрибуции">здесь</Anchor>.
2. Убедитесь, что все необходимые параметры URL добавлены к входящему URL-адресу. Чтобы просмотреть параметры, добавленные к входящему URL-адресу, откройте Meta Ads Manager и проверьте параметры URL-адреса, заданные при создании целевого URL-адреса. Более подробную информацию см. здесь: [Настройка целевого URL-адреса](#b-set-destination-url).
3. Определите для каждого входящего параметра исходящий параметр, с которым он будет сопоставлен. Например параметр `af_site_id` во входящем URL-адресе будет сопоставлен с параметром `af_site_id` в исходящем URL-адресе.
4. Определите значение по умолчанию для обязательных исходящих параметров, которые не могут быть пустыми.
5. Отправьте своему разработчику следующую информацию:
   * Сопоставление входящих и исходящих параметров. Разработчик создаст скрипт, который сгенерирует исходящий прямой URL-адрес на основе сопоставления входящих и исходящих параметров.
   * Значения параметров по умолчанию. Скрипт заполнит параметры исходящего URL-адреса значениями по умолчанию, если отсутствуют соответствующие значения параметров входящего URL-адреса.
   * Если вы используете ссылку атрибуции OneLink, отправьте домен и идентификатор шаблона своему разработчику. Разработчик использует их для создания исходящего URL-адреса OneLink. Например: `yourbrand.onelink.me/A1b2` или пример брендированного домена: `click.yourbrand.com/A1b2`
   * Отправьте своему разработчику следующие ссылки из хаба разработчиков:
     * [Инструкции и примеры кода](https://dev.appsflyer.com/hc/docs/create-direct-click-url) по созданию исходящих прямых URL-адресов для немобильных платформ.
     * [Демонстрация и инструкция](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) по созданию кроссплатформенной целевой страницы.
   * Напомните разработчику включить входящий параметр `fbclid` в исходящий URL-адрес.

     <div id="note-8" />

     > 📘 **Примечание:**
     >
     > Для отображения в отчетах по необработанным данным AppsFlyer входящий параметр `fbclid` также должен быть сопоставлен (в дополнение к исходящему параметру `fbclid`) с одним из исходящих параметров `af_sub[1-5]`.


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## Создание целевой страницы с помощью смарт-баннеров OneLink

**Путь пользователя:** Пользователь нажимает на рекламу Meta и перенаправляется на ваш мобильный сайт. Он или она попадает на страницу, где отображается смарт-баннер с призывом загрузить приложение из магазина приложений.

<div id="end-to-end-data-flow::4f887e1c" />

<Accordion title="Сквозной поток данных">

1. URL-адрес рекламы Meta включает в себя параметр `pid=metaweb_int`. Когда пользователь нажимает на рекламу, параметр `fbclid` автоматически добавляется к URL-адресу, на который нажал пользователь.
2. Пользователь перенаправляется на целевой URL-адрес — целевую страницу, содержащую смарт-баннер.
3. При загрузке целевой страницы смарт-баннер отправляет событие <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">показа</Anchor> в AppsFlyer, которое включает параметры входящего URL-адреса. Этот показ позволяет выполнить атрибуцию по просмотрам для целевой страницы. Подробнее об атрибуции по показам и просмотрам читайте <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">здесь</Anchor>.
4. Смарт-баннер генерирует исходящий URL-адрес для кнопки CTA на баннере. Исходящий URL-адрес основан на параметрах входящего URL-адреса, включая параметр `fbclid`. Смарт-баннер может генерировать только ссылки на основе OneLink.
5. Когда пользователь нажимает кнопку CTA на смарт-баннере, в AppsFlyer регистрируется клик.
6. Пользователь перенаправляется в магазин и скачивает приложение.
7. Когда пользователь открывает приложение, в AppsFlyer регистрируется событие установки.
8. AppsFlyer атрибутирует установку на основе вероятностного моделирования или детерминированно, если доступна реферальная ссылка.
9. Постбэк, содержащий параметры `fbclid` и другие параметры события, генерируется и отправляется в Meta через API CAPI. Meta использует параметр `fbclid` для идентификации конкретного клика, тогда как другие параметры помогают оптимизировать кампанию.

</Accordion>

<div id="set-up-smart-banners-landing-page" />

<Accordion title="Настройка целевой страницы смарт-баннеров">

Чтобы настроить кампании Meta Ads при помощи смарт-баннеров, выполните следующие действия:

1. Настройте шаблон атрибуционных ссылок OneLink для кампании. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Как создавать шаблоны OneLink</Anchor>.
2. Создайте смарт-баннер.

   <div id="note-9" />

   > 📘 **Примечание:**
   >
   > Приведенные ниже инструкции посвящены конкретным шагам, которые необходимы для настройки кампании Meta Ads при помощи смарт-баннеров. Подробное руководство по настройке кампаний при помощи смарт-баннеров приведено в <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers#настройки">разделе «Настройка»</Anchor> статьи <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers">Смарт-баннеры: mobile web-to-app (для маркетологов)</Anchor>.

3. Настройте параметры смарт-баннера для кампаний Meta Ads:
   * Убедитесь, что к входящему URL-адресу добавлены все соответствующие параметры URL. Самое главное, `pid=metaweb_int` и `fbclid` доступны во входящем URL-адресе, что позволяет смарт-баннеру собирать их. Эти два параметра необходимы для атрибуции и отправки постбэков в Meta Ads. Чтобы просмотреть параметры, добавленные к входящему URL-адресу, откройте Meta Ads Manager и проверьте параметры URL-адреса, заданные при создании целевого URL-адреса, см. здесь: [Настройка целевого URL-адреса](#b-set-destination-url).

</Accordion>

<div id="view-web-to-app-attribution-data" />

## Просмотреть данные атрибуции web-to-app

Хотя события конверсии, происходящие в вебе, отправляются в Meta с исходным PID `metaweb_int`, на дэшборде и в отчётах о сырых данных AppsFlyer они отображаются под PID `Facebook Ads`. Это относится как к основным событиям конверсии, так и к событиям-ассистам конверсии.

Объединённый формат отчётности позволяет анализировать эффективность веб-кампаний и кампаний приложений в одном месте, включая полные отчёты по затратам в вебе и мобильным кампаниям.

<div id="view-in-the-dashboard" />

### Посмотреть на дэшборде

Вся атрибуция Meta web-to-app отображается как `Facebook Ads` в дэшбордах «Обзор» и «Активность». Это обеспечивает единый консолидированный обзор результатов кампаний на всех платформах. Используйте стандартные фильтры и разбивки, чтобы сравнить трафик приложений и веб-трафик в данных Meta Ads.

<div id="view-in-raw-data-and-api-reports" />

### Просмотр в отчетах о сырых данных и отчетах API

* В **экспортах сырых данных и ответах API** используется PID `Facebook Ads` в поле `media_source` для веб-активности Meta. Чтобы верифицировать детали настройки веб-кампании, обратитесь к полю `original_url`, которое показывает `metaweb_int` как PID, использованный при создании веб-кампаний.
* **Отчеты о постбэках** показывают `metaweb_int` как оригинальный медиаисточник, к которому был отправлен постбэк.

<div id="traits-and-limitations" />

## Характеристики и ограничения

| Специфика | Примечания |
| --- | --- |
| Данные о затратах, кликах и показах | Данные о стоимости, кликах и показах для Meta Ads Web (`metaweb_int`) поддерживаются через интеграцию Meta Ads (`Facebook Ads`).<ul><li>Чтобы получить данные, убедитесь, что аккаунт рекламной сети подключен к основному PID (`Facebook Ads`):<ul><li>Подписчики ROI360: на странице **Настройки стоимости**,</li><li>Пользователи без подписки ROI360: на странице **Активная интеграция** (вкладка **Стоимость**).</li></ul></li><li>Чтобы просмотреть данные о стоимости, кликах и показах для кампаний Meta Ads Web, убедитесь, что идентификатор кампании (<Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>) включен в ссылку атрибуции.</li><li>Ссылка атрибуции должна содержать полную иерархию кампании, чтобы отображались данные о стоимости, кликах и показах, привязанные к атрибуции на самом детализированном уровне.</li></ul> |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HZKNS17JYFQ3F5TKNE5Q5TJ4=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01J8CYG29BETYPZ03A1X54M3ZF=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 prerequisite=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01HZKNS17JTCXE4JMZ64NEVPS6=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F how-to-create-a-meta-ads-campaign=%D0%BA%D0%B0%D0%BA-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D1%82%D1%8C-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%83%D1%8E-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D1%8E-meta-web-ads h_01HZKNS17JERCAKZHK43ZQWARJ=%D0%BA%D0%B0%D0%BA-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D1%82%D1%8C-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%83%D1%8E-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D1%8E-meta-web-ads set-up-meta-ads-integration-in-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-meta-web-ads-%D0%B2-appsflyer h_01HZKNS17J284R2MAN42WV7F0S=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-meta-web-ads-%D0%B2-appsflyer h_01HZKNS17JGQBENY2X8S5PHFVH=a-activate-the-meta-ads-integration h_01ZXVWB1ZYKK4DP38QY1RMEY6M=d-enable-view-through-attribution-for-meta-web h_01HZKNS17JH2ZJKATV1AP6JDWP=b-set-inapp-event-postbacks 01JJ4MGS84WXEVG4FWQ0YQ7GN6=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01_s2s_metaweb_ua_ip=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 set-up-appsflyer-integration-in-meta-ads=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-appsflyer-%D0%B2-meta-ads h_01HZKNS17JJWX7N9W6BN05B57C=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-appsflyer-%D0%B2-meta-ads h_01HZKNS17JTVX8N5CKTKVGH0QB=a-set-the-campaign-type-objective-and-goals h_01HZKNS17JHHS7GYPBT441ND7A=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-3 h_01HZKNS17KT8TRD2TGDBRGKBZ3=b-set-destination-url h_01HZKNS17KCNKS4YY4JHMQRM1Z=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01J2V9WF300WDY0PWV68TDR9TT=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-4 h_01K88MSNRX9QFQ49FN2MXPMADX=%D1%81%D0%BE%D0%B2%D0%B5%D1%82 01J2V903C36X5K6VRPGQQGWFMW=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-5 h_01HZKNS17K07CENP8GG7MQRKHK=c-select-tracked-events h_01HZKNS17KARAENYPMVJSM1ARQ=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE-1 create-landing-page-with-onelink-smart-script=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-script h_01HZKNS17KPJMP74HQKWY022T2=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-script h_01HZKNS17K5PRRXSD2JMJ54NTN=end-to-end-data-flow h_01HZKNS17KA8VAK5TDFG1NV9YN=set-up-smart-script-landing-page h_01HZKNS17K6DPA6E9CTM5F3X1A=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-9 h_01HZKNS17K2W4XJB0BH87RZYTJ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-8 h_01HZKNS17K5RRAFFTNA6QT7AKJ=set-up-smart-script-crossplatform-landing-page h_01HZKNS17K03S4B3ZRQ62TRFRE=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-8 create-landing-page-with-onelink-smart-banners=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-%D1%81%D0%BC%D0%B0%D1%80%D1%82-%D0%B1%D0%B0%D0%BD%D0%BD%D0%B5%D1%80%D0%BE%D0%B2-onelink h_01HZKNS17KH8NQ68RPZGMEAQTV=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-%D1%81%D0%BC%D0%B0%D1%80%D1%82-%D0%B1%D0%B0%D0%BD%D0%BD%D0%B5%D1%80%D0%BE%D0%B2-onelink h_01HZKNS17K4Y7WSM14EEJ2G5NC=end-to-end-data-flow::4f887e1c h_01HZKNS17KZ3YKS5R52SRKR9P2=set-up-smart-banners-landing-page h_01HZKNS17K3W3GPV6TM5RQS1WP=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-9 meta%20view=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-webtoapp-attribution-data-from-november-2-2025=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-in-the-dashboard=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 h_01K88J8JFNMHCVZ0C34E3D7AST=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 view-in-raw-data-and-api-reports=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-api h_01K88J8JFN8W2572N92466YFZQ=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-api traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F 01JEZXJNF1C932KGAEFS4P5D51=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

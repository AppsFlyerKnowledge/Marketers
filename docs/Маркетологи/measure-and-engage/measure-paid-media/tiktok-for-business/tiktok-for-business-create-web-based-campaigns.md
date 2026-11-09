---
title: TikTok for Business — создание веб-кампаний
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
  created_at: '2025-10-31T12:09:51Z'
  edited_at: '2026-09-17T00:30:20Z'
  id: 40496161157521
  locale: ru
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ru/articles/40496161157521
---
> **Краткий обзор:** Используйте веб-кампании TikTok Ads, чтобы атрибутировать Web-to-app конверсии из TikTok Ads

<div id="overview" />

## Информация о компании

AppsFlyer поддерживает интеграцию с TikTok Ads (`tiktokweb_int`) для веб-кампаний по привлечению пользователей, позволяя передавать данные атрибуции и конверсий напрямую через Events API TikTok. Затем TikTok сможет использовать эти данные для оптимизации таргетинга рекламы, измерения эффективности и создания кастомных аудиторий.

<div id="important" />

> 🚧 **Важно!**
>
> На данный момент интеграция с TikTok Web не поддерживает отправку постбэков повторного вовлечения в CAPI.

<div id="prerequisites" />

### Требования

Прежде чем активировать интеграцию TikTok Web, убедитесь, что у вас есть бизнес-аккаунт в [TikTok Ads Manager](https://getstarted.tiktok.com/grow-your-business-gb?lang=en&attr_source=google&attr_source=google&attr_medium=search-br-ad&attr_medium=search-br-ad&attr_adgroup_id=155057567247&attr_adgroup_id=155057567247&attr_term=tiktok%20ads%20manager&attr_term=tiktok%20ads%20manager&no_parent_redirect=1&no_parent_redirect=1&creative=%7BGenZCopy%7D&matchtype=e&gad_source=1&gad_campaignid=20368896948&gbraid=0AAAAACeGRgRdqveOjiUJwxN0-j9g7VjPg&gclid=Cj0KCQjwmYzIBhC6ARIsAHA3IkTKsL0d1xAZLIO_9GIkDDIJR-jZs9jDGVa1hTDbsLzcxZl2j6p7ITcaAhf1EALw_wcB).

<div id="how-to-create-a-tiktok-web-ads-campaign" />

### Как создать рекламную кампанию TikTok Web Ads

Эта статья содержит информацию и пошаговые инструкции по настройке веб-кампании в TikTok Ads для мобильных приложений с помощью AppsFlyer. Настройка включает в себя определение интеграции между TikTok Ads и AppsFlyer, настройку конфигурации кампании на обеих платформах и создание посадочных страниц с помощью OneLink Smart Script или OneLink Smart Banners.

Процесс настройки включает следующие обязательные этапы:

* [Настройте интеграцию TikTok Web Ads в AppsFlyer](#настройте-интеграцию-с-tiktok-web-ads-в-appsflyer) (обязательно)
* [Настройте интеграцию AppsFlyer в TikTok Ads](#настройте-интеграцию-с-appsflyer-в-tiktok-ads) (обязательно)

И следующие необязательные шаги:

* <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-create-web-based-campaigns#создание-целевой-страницы-с-помощью-onelink-smart-script">создание целевой страницы с помощью OneLink Smart Script</Anchor> (необязательно)
* [Создание целевой страницы с помощью OneLink Smart Banners](#создание-целевой-страницы-с-помощью-onelink-smart-banners) (необязательно)

<div id="set-up-tiktok-web-ads-integration-in-appsflyer" />

## Настройте интеграцию с TikTok Web Ads в AppsFlyer

Для начала активируйте интеграцию TikTok Web и настройте постбэки, которые AppsFlyer отправляет в Events API.

<div id="1-activate-the-tiktok-web-ads-integration" />

<Accordion title="1. Включить интеграцию с TikTok Web Ads">

Чтобы активировать интеграцию с TikTok Web Ads:

1. В AppsFlyer в боковом меню откройте **Сотрудничество** > **Партнерские интеграции** > **Partner Marketplace**.
2. Найдите **TikTok Web** (или `tiktokweb_int`) и выберите его. Вы будете перенаправлены на страницу настройки.
3. На вкладке **Интеграция** включите переключатель **Активировать партнера**. Переключатель должен оставаться в положении <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активирован</Anchor> всё время, пока вы работаете с партнером.
4. Отключите опцию **Расширенная конфиденциальность** (если вы настраиваете интеграцию приложения iOS).
5. **Обмен данными с расширенным сопоставлением:** Включите, чтобы передавать в TikTok поля расширенного сопоставления, такие как хешированный email, хешированный номер телефона, хешированное имя и хешированную фамилию, если эти поля включены в данные о событии, отправляемые в AppsFlyer. Более подробную информацию см. здесь: <Anchor target="_blank" href="/marketers/ru/docs/advanced-matching-data-sharing">Обмен данными с расширенным сопоставлением</Anchor>.
6. **Идентификатор пикселя:** Введите идентификатор пикселя. Вы можете сгенерировать его или получить в TikTok Ads Manager, следуя инструкциям, приведенным <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">ЗДЕСЬ</Anchor>.
7. **Токен доступа:** Введите токен доступа. Чтобы сгенерировать или получить его, следуйте <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">этим инструкциям</Anchor>
8. **Ограничение использования персональных данных пользователей в рекламе TikTok (CCPA):** Включите этот переключатель, чтобы обеспечить соблюдение <Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests">законов о защите данных</Anchor>.

   <div id="note" />

   > 📘 **Примечание:**
   >
   > Соблюдение требований CCPA ограничивает объем данных, поступающих от пользователей рекламы TikTok, проживающих в Калифорнии или других чувствительных штатах США.


</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2. Активация атрибуции по просмотрам">

AppsFlyer поддерживает атрибуцию по просмотрам для веб-кампаний TikTok с использованием посадочной страницы с поддержкой [Smart Script](#создание-целевой-страницы-с-помощью-onelink-smart-script) или [Smart Banner](#создание-целевой-страницы-с-помощью-onelink-smart-banners). Это позволяет выполнять атрибуцию на основе вероятностного моделирования для установок приложений, вызванные показом рекламы, даже когда пользователи не нажимают на рекламу напрямую.

Когда пользователь нажимает на рекламное объявление TikTok Web и попадает на посадочную страницу с поддержкой [Smart Script](#создание-целевой-страницы-с-помощью-onelink-smart-script) или [Smart Banner](#создание-целевой-страницы-с-помощью-onelink-smart-banners), AppsFlyer может атрибутировать последующую установку приложения. Если доступно, параметр `ttclid` будет включён в постбэк к TikTok для повышения точности атрибуции.

**Активация атрибуции по просмотрам через TikTok Web:**

1. В AppsFlyer, из боковой панели, откройте **Активные интеграции** > **TikTok web ads**.
2. На вкладке **Интеграция** прокрутите до раздела **Атрибуция установки**.
3. Включите **Атрибуцию установок по просмотрам**.
4. **[необязательно]** Включите **Равный приоритет кроссплатформенной атрибуции** и задайте для него окно ретроспективы. Более подробно см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Включите равный приоритет для кроссплатформенных показов</Anchor>.
5. Откройте вкладку **Ссылка атрибуции**.
6. Прокрутите к разделу **Атрибуция по просмотрам** и установите **окно атрибуции по просмотрам** (до 24 часов).
7. Нажмите **Сохранить интеграцию** для применения ваших настроек.

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3. Постбэки по внутренним событиям приложений.">

В настоящее время установки являются единственными событиями, которые запускают автоматические постбэки в TikTok Ads по умолчанию. Для других типов событий вы можете создавать пользовательские постбэки, сопоставляя события AppsFlyer с событиями TikTok Ads, которые можно просмотреть в TikTok Ads Manager.

Для настройки постбэков по внутренним событиям приложения выполните следующие действия:

1. Активируйте **Постбэки по внутренним событиям приложения**.
2. При необходимости задайте окно постбэков по событиям в приложении (подробнее о настройке окна постбэков по событиям в приложении в целом читайте в <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">этой статье</Anchor>).
3. Нажмите**Добавить событие**, чтобы добавить событие в список.
4. При необходимости задайте **Iокно постбэка события в приложении.** AppsFlyer получает название события либо из SDK, интегрированного в ваше приложение, либо из межсерверных событий.
5. В столбце **mapped to partner event** column, выберите в раскрывающемся списке наиболее подходящее предопределенное партнерское событие.
6. В столбце **For Users From** выберите **This Partner Only** , чтобы постбэки событий в приложении отправлялись исключительно по событиям, выполненным пользователями, пришедшими от этого партнера.
7. В столбце **including** выберите, будут ли события отправляться со значениями дохода. См.  <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#данные-для-включения-в-постбэки">Данные для включения в постбэки</Anchor>.

   <div id="note-1" />

   > 📘 **Примечание:**
   >
   > * Если вы настраиваете событие покупки, в столбце **«Включая»** установите значение **«Значения и выручка».** Выбор любого другого варианта приведет к сбою в отправке постбэка.
   > * В настоящее время для включения дохода может быть настроено только событие покупки.

8. [Необязательно] Нажмите на значок **Добавить условие**, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события.
9. Нажмите **Сохранить интеграцию**.
10. [Необязательно] После сохранения интеграции, оставаясь на странице конфигурации, вы можете интегрировать с этим партнером другие свои приложения:
    1. <span class="af-ol-a"></span>В верхнем левом углу нажмите на название приложения под названием партнера, чтобы открыть список приложений.
    2. Выберите другое приложение из раскрывающегося списка.
    3. Повторите шаги по интеграции для выбранного приложения.

</Accordion>

<div id="set-up-appsflyer-integration-in-tiktok-ads" />

## Настройте интеграцию с AppsFlyer в TikTok Ads

Выполните следующие шаги в TikTok Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Установите тип, цель и задачи кампании">

Вы можете выбрать любое предопределенное in-app событие, отправленное из AppsFlyer, в качестве цели кампании, или выбрать «Download», если вы хотите оптимизировать кампанию под установки мобильного приложения.

<div id="warning" />

> ❗️ **Предупреждение**
>
> Если вы хотите, чтобы события конверсии, инициированные Web-to-app, отправлялись через TikTok Events API, пропустите <Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup#measuring-app-activity-for-nonapp-campaigns">эти шаги</Anchor> при создании кампании; в противном случае TikTok будет учитывать эти конверсии через SRN API, что может привести к расхождениям в отчетности и оптимизации.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Укажите целевой URL">

1. В разделе  **«Назначение»** в поле <strong>«URL-адрес веб-сайта»</strong>введите URL, который будет целевым адресом вашего объявления. URL-адрес должен соответствовать одному из следующих значений:
   * **Целевая веб-страница:** Использование целевой страницы рекомендуется в следующих случаях:
     * У вас есть приложение на нескольких платформах.
     * Вы хотите использовать целевую страницу для предоставления дополнительной информации о рекламируемом продукте.
     * Вы хотите использовать целевую страницу для сбора дополнительных данных.

       Для всех этих сценариев использования создайте целевую страницу с поддержкой [Smart Script](#создание-целевой-страницы-с-помощью-onelink-smart-script) или [Smart Banner](#создание-целевой-страницы-с-помощью-onelink-smart-banners)-enabled landing page.
   * **Ссылки атрибуции AF:** Использование ссылок атрибуции AF (OneLink, одноплатформенных или кроссплатформенных ссылок) рекомендуется в тех случаях, когда вы хотите, чтобы пользователь был перенаправлен непосредственно в магазин для загрузки приложения без предварительного посещения целевой страницы.
2. Нажмите **Создать параметр URL**, чтобы добавить параметры URL к URL (будь то URL-адрес целевой страницы или ссылка атрибуции AF).
3. В разделе **Настраиваемые параметры** нажмите **Добавить параметр**.
4. Сопоставьте параметры AppsFlyer с соответствующими значениями в TikTok. Параметры, которые вы будете сопоставлять, зависят от того, ведет ли целевой URL-адрес на целевую страницу, атрибуционную ссылку или в магазин для ПК или консоли.

   <div id="landing-page-or-attribution-link" />

   #### Целевая страница или атрибуционная ссылка

   Если в качестве целевого URL-адреса используется **целевая страница, атрибуционная ссылка OneLink или одноплатформенная атрибуционная ссылка**, сопоставьте следующие параметры AF с их эквивалентами в TikTok:

| Параметр AF | Сопоставленное значение TikTok |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `tiktokweb_int` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#c">`c`</Anchor>* | **\_\_campaign\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | **\_\_campaign\_id\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | **\_\_aid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | **\_\_aid\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | **\_\_cid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | **\_\_cid\_\_** |

   * Чтобы упростить анализ кампании, указывайте тип кампании -- веб или мобайл -- в префиксе или суффиксе названия кампании (например, название-кампании\_web).

   Пример итогового URL должен быть таким:

   ```
   https://app.appsflyer.com/{app_id}?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
   ```

   Если APK вашего приложения НЕ размещен в Google Play Store, добавьте параметр <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> и сопоставьте с ним URL-адрес магазина, например, `https://Add-your-store-url.com`

   <div id="pc-or-console-store" />

   #### Магазин для ПК или консоли

   Если ваш целевой URL-адрес — **магазин приложений для ПК или консоли**, создайте ссылку, следуя инструкциям в таблице ниже. Дополнительную информацию см. здесь: <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Прямые ссылки атрибуции для CTV, ПК и консолей</Anchor>

| Компонент ссылки | Значение |
| --- | --- |
| Базовый URL-адрес | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Обязательные параметры пути | ▪ platformExample: steam  <br />▪ app\_idExample: 123456 |
| Обязательные параметры запроса | af\_media\_source  <br />af\_campaign\_id  <br />▪ af\_r |
| Другие параметры | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links#параметры">См. все параметры</Anchor> |
| Структура URL-адреса | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

   Сопоставьте следующие параметры AppsFlyer с их эквивалентами в TikTok:

| Параметр AF | Сопоставленное значение TikTok |
| --- | --- |
| `media_source (медиа-источник)` | `tiktokweb_int` |
| `af_campaign` * | **\_\_campaign\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | **\_\_campaign\_id\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | **\_\_aid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | **\_\_aid\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | **\_\_cid\_name\_\_** |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | **\_\_cid\_\_** |

   * Чтобы упростить анализ кампании, указывайте тип кампании -- веб или мобайл -- в префиксе или суффиксе названия кампании (например, название-кампании\_web).

   Пример кроссплатформенного URL:

   ```
   https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__campaign_id__&af_campaign=__campaign_name__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
   ```

   <div id="note-2" />

   > 📘 **Примечание:**
   >
   > TikTok автоматически добавляет `ttclid={{ttclid}}` к целевому URL-адресу, когда пользователь кликает по рекламе


</Accordion>

<div id="note-3" />

<div id="create-a-landing-page-with-onelink-smart-script" />

## Создание целевой страницы с помощью OneLink Smart Script

**Путь пользователя:** Пользователь нажимает на рекламу TikTok и перенаправляется на ваш мобильный сайт. Она или она попадает на страницу с кнопками CTA, призывающими их загрузить ваше приложение с одной или нескольких платформ. Нажатие кнопки перенаправляет пользователя в магазин.

<div id="endtoend-data-flow" />

<Accordion title="Сквозной поток данных">

<Image align="center" alt="" src="https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png" />

1. URL-адрес рекламы TikTok включает  `pid=tiktokweb_int` параметр. Когда пользователь нажимает на рекламу, к URL-адресу автоматически добавляется `ttclid` параметр.
2. Пользователь перенаправляется на целевой URL-адрес — целевую страницу, содержащую Smart Script.
3. Когда целевая страница загружается, Smart Script отправляет в AppsFlyer показ с входящими параметрами URL. Показ позволит выполнить атрибуцию просмотров с целевой веб-страницы. Подробнее об атрибуции по показам и просмотрам читайте <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">здесь</Anchor>.
4. Smart Script генерирует исходящие URL-адреса для кнопок CTA на странице на основе параметров входящего URL-адреса, включая параметр `ttclid` параметр. Кнопки могут вести к:
   * Google Play и App Store через ссылку атрибуции OneLink.
   * Магазины на нескольких платформах (например, CTV, Epic и Steam). В этом сценарии Smart Script создаёт отдельную атрибуционную ссылку для каждой платформы, ведущую в магазин соответствующей платформы.
   * Загрузка файла APK на устройство пользователя.
5. Когда пользователь нажимает кнопку CTA, клик срабатывает и регистрируется в AppsFlyer.
6. Пользователь перенаправляется в магазин и скачивает приложение.
7. Когда пользователь открывает приложение, в AppsFlyer регистрируется событие установки.
8. AppsFlyer атрибутирует установку на основе вероятностного моделирования или, если доступен [реферер установки](https://www.appsflyer.com/glossary/install-referrer/) , детерминированно.
9. Генерируется постбэк, содержащий параметры `ttclid` и другие параметры события, и отправляется в TikTok через Events API. TikTok использует параметр `ttclid` для идентификации конкретного клика, а другие параметры помогают оптимизировать кампанию.

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="Настройка целевой страницы Smart Script">

Чтобы настроить кампании TikTok Ads при помощи Smart Script, выполните следующие действия:

1. Настройте шаблон атрибуционных ссылок OneLink для кампании. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Как создавать шаблоны OneLink</Anchor>.
2. Создайте Smart Script. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Как создать OneLink Smart Script</Anchor>.

   > 📘 **Примечание:**
   >
   > Приведенные ниже инструкции посвящены конкретным шагам, которые необходимы для настройки кампании TikTok Ads с помощью Smart Script. Подробное руководство по настройке кампаний Smart Script см. в статье <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Как создать OneLink Smart Script</Anchor> раздел <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Настройка OneLink Smart Script V2</Anchor> .

3. Убедитесь, что все необходимые параметры URL добавлены к входящему URL-адресу. Чтобы просмотреть параметры, добавленные к входящему URL-адресу, откройте TikTok Ads Manager и проверьте параметры URL-адреса, заданные при создании целевого URL-адреса. Для получения дополнительной информации см.  [Set destination UR](#2-set-destination-url)[L](#set-destination-url).
4. Сопоставьте параметры входящего URL-адреса, необходимые для кампании TikTok Ads, с параметрами исходящего URL-адреса, которые будут отправлены в AppsFlyer, когда пользователь нажмет кнопку CTA:
   * **PID**: Убедитесь, что Smart Script принимает значение параметра `pid=tiktokweb_int` из входящего URL-адреса и сопоставляет его с соответствующими параметрами в исходящем URL-адресе.
   * **TTCLID**: Параметр `ttclid` крайне важен для успешной отправки постбэков событий в приложении в TikTok. Параметр `ttclid` необходимо сопоставить вручную в разделе **URL parameter mapping** на странице **Smart Script** :

     1. Выберите **Пользовательский параметр** в разделе **Сопоставление для**.
     2. Введите **ttclid** в полях **Outgoing URL parameter** и **Incoming URL parameters**.

     <div id="note-4" />

     > 📘 **Примечание:**
     >
     > Для отображения в отчетах о сырых данных AppsFlyer входящий параметр `ttclid` также должен быть сопоставлен (в дополнение к исходящему параметру `ttclid` ) с одним из исходящих параметров `af_sub[1-5]` .


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="Настройка кроссплатформенной целевой страницы Smart Script">

Чтобы настроить кампании TikTok Ads при помощи Smart Script для кроссплатформенных целевых страниц, выполните следующие действия:

1. Настройте шаблон атрибуционных ссылок OneLink для кампании. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Как создавать шаблоны OneLink</Anchor>.
   * Активируйте шаблон OneLink для кроссплатформенной атрибуции, см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-cross-platform-links-for-multi-device-campaigns#создание-шаблона-onelink-для-кроссплатформенной-атрибуции">здесь</Anchor>.
2. Убедитесь, что все необходимые параметры URL добавлены к входящему URL-адресу. Чтобы просмотреть параметры, добавленные к входящему URL-адресу, откройте TikTok Ads Manager и проверьте параметры URL-адреса, заданные при создании целевого URL-адреса. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-create-web-based-campaigns#b-set-destination-url">Настройка целевого URL-адреса</Anchor>.
3. Определите для каждого входящего параметра исходящий параметр, которому он будет сопоставлен. Например, входящий параметр `af_site_id` во входящем URL будет сопоставлен параметр  `af_site_id` в исходящем URL.
4. Определите значение по умолчанию для обязательных исходящих параметров, которые не могут быть пустыми.
5. Отправьте своему разработчику следующую информацию:
   * Сопоставление входящих и исходящих параметров. Разработчик создаст скрипт, который сгенерирует исходящий прямой URL-адрес на основе сопоставления входящих и исходящих параметров.
   * Значения параметров по умолчанию. Скрипт заполнит параметры исходящего URL-адреса значениями по умолчанию, если отсутствуют соответствующие значения параметров входящего URL-адреса.
   * Если вы используете ссылку атрибуции OneLink, отправьте домен и идентификатор шаблона своему разработчику. Разработчик использует их для создания исходящего URL-адреса OneLink. Например: `yourbrand.onelink.me/A1b2` или пример брендированного домена: `click.yourbrand.com/A1b2`
   * Отправьте вашему разработчику следующие ссылки Dev Hub:
     * [Инструкции и примеры кода](https://dev.appsflyer.com/hc/docs/create-direct-click-url) для создания исходящих прямых URL-адресов для немобильных платформ.
     * [Демо и инструкция](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) по созданию кроссплатформенной целевой страницы.

* Напомните разработчику включить входящий параметр `ttclid` в исходящий URL-адрес.

  <div id="note-5" />

  > 📘 **Примечание:**
  >
  > Для отображения в отчетах о сырых данных AppsFlyer входящий параметр `ttclid` также должен быть сопоставлен (в дополнение к исходящему параметру `ttclid` ) с одним из исходящих параметров `af_sub[1-5]` .


</Accordion>

<div id="create-a-landing-page-with-onelink-smart-banners" />

## Создание целевой страницы с помощью OneLink Smart Banners

**Путь пользователя:** Пользователь нажимает на рекламу TikTok и перенаправляется на ваш мобильный сайт. Они попадают на страницу, где отображается умный баннер с кнопкой-призывом скачать приложение из App Store.

<div id="endtoend-data-flow::e62b5c1b" />

<Accordion title="Сквозной поток данных">

1. URL-адрес рекламы TikTok включает  `pid=tiktokweb_int` параметр. Когда пользователь нажимает на рекламу, an `ttclid` параметр автоматически добавляется к URL-адресу, по которому выполнен переход.
2. Пользователь перенаправляется на целевой URL-адрес — целевую страницу, содержащую Smart Banner.
3. При загрузке целевой страницы Smart Banner отправляет в AppsFlyer событие <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">показа</Anchor>, которое включает параметры входящего URL-адреса. Этот показ позволяет выполнить атрибуцию по просмотрам для целевой страницы. Подробнее об атрибуции по показам и просмотрам читайте <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">здесь</Anchor>.
4. Smart Banner генерирует исходящий URL-адрес для кнопки CTA на баннере. Исходящий URL-адрес основан на параметрах входящего URL-адреса, включая `ttclid` параметр. Smart Banner может генерировать только ссылки на основе OneLink.
5. Когда пользователь нажимает кнопку CTA на смарт-баннере, в AppsFlyer регистрируется клик.
6. Пользователь перенаправляется в магазин и скачивает приложение.
7. Когда пользователь открывает приложение, в AppsFlyer регистрируется событие установки.
8. AppsFlyer атрибутирует установку на основе вероятностного моделирования или детерминированно, если доступна реферальная ссылка.
9. Генерируется и отправляется в TikTok через Events API постбэк, содержащий `ttclid` параметры и другие параметры события. TikTok использует `ttclid` параметр для идентификации конкретного клика, а другие параметры помогают оптимизировать кампанию.

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="Настройте целевую страницу с умным баннером Smart Banners.">

Чтобы настроить кампании TikTok Ads при помощи смарт-баннеров, выполните следующие действия:

1. Настройте шаблон атрибуционных ссылок OneLink для кампании. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Как создавать шаблоны OneLink</Anchor>.
2. Создайте Smart Banner

   <div id="note-6" />

   > 📘 **Примечание:**
   >
   > Приведенные ниже инструкции посвящены конкретным шагам, которые необходимы для настройки кампании TikTok Ads с помощью смарт-баннеров. Подробное руководство по настройке кампаний при помощи смарт-баннеров приведено в <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers#настройки">разделе «Настройка»</Anchor> статьи <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers">Смарт-баннеры: mobile web-to-app (для маркетологов)</Anchor>.

3. Настройте параметры смарт-баннера для кампаний TikTok Ads:
   * Убедитесь, что к входящему URL-адресу добавлены все соответствующие параметры URL. Самое важное: `pid=tiktokweb_int` и `ttclid` должны быть доступны во входящем URL-адресе, чтобы Smart Banner мог их собрать. Эти два параметра необходимы для атрибуции и отправки постбэков в TikTok Ads. Чтобы проверить параметры, добавленные к входящему URL-адресу, откройте TikTok Ads Manager и проверьте параметры URL, заданные при создании целевого URL. См. <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-create-web-based-campaigns#b-set-destination-url">Настройка целевого URL</Anchor>.

</Accordion>

<div id="view-web-to-app-attribution-data" />

## Просмотреть данные атрибуции web-to-app

Хотя события конверсии в вебе отправляются в TikTok с исходным PID `tiktokweb_int`, в дэшборде AppsFlyer и отчетах о сырых данных они отображаются под PID `tiktokglobal_int`. Это относится как к основным событиям конверсии, так и к событиям-ассистам конверсии.

Этот унифицированный вид отчетов позволяет анализировать эффективность веб-кампаний и кампаний для приложения в одном месте, включая подробную отчетность по стоимости для веба и мобильных устройств.

<div id="view-in-the-dashboard" />

### Посмотреть на дэшборде

Вся атрибуция TikTok web-to-app отображается под `tiktokglobal_int` в дэшбордах Overview и Activity. Это обеспечивает единое, консолидированное представление результатов кампаний на разных платформах. Используйте стандартные фильтры и разбивки, чтобы сравнивать трафик в приложении и веб-трафик в ваших данных TikTok Ads.

<div id="view-in-raw-data-and-api-reports" />

### Просмотр в отчётах о сырых данных и через API

Экспорты сырых данных и ответы API включают PID `tiktokglobal_int` в поле `media_source` для веб-активности TikTok. Чтобы проверить детали настройки веб-кампании, обратитесь к полю `original_url`, в котором указан PID `tiktokweb_int`, использованный при создании веб-кампании.

<div id="measure-cost-clicks-and-impressions" />

## Измеряйте затраты, клики и показы

Вы можете измерять стоимость, клики и показы TikTok вместе с данными атрибуции web-to-app в дэшборде и в отчетах Cost ETL (ROI360 customers only):

1. Подключите TikTok как интеграцию данных о стоимости в мобильном приложении:  
   Перейдите на вкладку **Расходы** или страницу **Настройки расходов** и подключите через `tiktokglobal_int`. Пошаговые инструкции см. в статье <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data">Настройка ROI360 Cost API для измерения данных о затратах</Anchor>.
2. Добавьте идентификатор кампании в URL-адрес целевой страницы:  
   Включите `af_c_id` вместе с полной иерархией кампании в URL-адрес целевой страницы. Это гарантирует, что стоимость, клики и показы сопоставляются с вашими данными веб-атрибуции на максимально гранулярном уровне.

<div id="note-7" />

> 📘 **Примечание**
>
> Данные о затратах доступны только для клиентов ROI360. Клики и показы доступны всем клиентам, завершившим эту настройку.

<div data-zendesk-anchors="overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01K8X2TS8CYRY1XVQNEABWHVF4=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01K8X2TS8C356J1VSAG70EB8HF=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE prerequisites=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01K8X2TS8CEFSS92A9MRE7MQD1=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F how-to-create-a-tiktok-web-ads-campaign=%D0%BA%D0%B0%D0%BA-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D1%82%D1%8C-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%83%D1%8E-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D1%8E-tiktok-web-ads h_01K8X2TS8CXP0R5WQN14W8S8G3=%D0%BA%D0%B0%D0%BA-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D1%82%D1%8C-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%83%D1%8E-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D1%8E-tiktok-web-ads set-up-tiktok-web-ads-integration-in-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-%D1%81-tiktok-web-ads-%D0%B2-appsflyer h_01K8X2TS8CQDNNX59WDW38V24X=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-%D1%81-tiktok-web-ads-%D0%B2-appsflyer h_01K8X2TS8CYNWESDXCCFCE4TTA=1-activate-the-tiktok-web-ads-integration h_01K8X2TS8C4HNWR2Z3MTMKQ92Q=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01K8X2TS8C3RDCEX0R8HJGCARH=2-enable-viewthrough-attribution h_01K8X2TS8CP915Y7C5WSEYAJQV=3-set-inapp-event-postbacks h_01K8X2TS8CYD41E31EJ0ES76HP=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 set-up-appsflyer-integration-in-tiktok-ads=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-%D1%81-appsflyer-%D0%B2-tiktok-ads h_01K8X2TS8CNQEQCB9SBVESBJ9H=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-%D1%81-appsflyer-%D0%B2-tiktok-ads h_01K8X2TS8CZCGK55A71SVDRFXJ=1-set-the-campaign-type-objective-and-goals h_01K8X2TS8C8AFR6M3ME0SPP4QN=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01K8X2TS8CC4ZTST3Y5Q2RRVTC=2-set-destination-url landing-page-or-attribution-link=%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%B0%D1%8F-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D0%B0-%D0%B8%D0%BB%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D0%B0%D1%8F-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0 h_01K8X5E9VSFTD53NCA03KYT80P=%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%B0%D1%8F-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D0%B0-%D0%B8%D0%BB%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%BE%D0%BD%D0%BD%D0%B0%D1%8F-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0 pc-or-console-store=%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BA-%D0%B8%D0%BB%D0%B8-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8 h_01K8X5XC69TDW2DNFWFYRN9TMF=%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BA-%D0%B8%D0%BB%D0%B8-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B8 h_01K8X2TS8DQ70RSFHBGM7ZHRYE=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 create-a-landing-page-with-onelink-smart-script=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-script h_01K8X2TS8DZ62VHY2W7SCBSWEN=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-script h_01K8X2TS8D7X7YT9FBDPZPVAH3=endtoend-data-flow h_01K8X2TS8DJ54M3H11PTXVE2JF=set-up-a-smart-script-landing-page h_01K8X2TS8DFS70S7YNA89R6N95=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-6 h_01K8X2TS8DZT5GG7BW41A3FA4B=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-5 h_01K8X2TS8DMTGJNQX3B3VXAM0W=set-up-a-smart-script-crossplatform-landing-page h_01K8X2TS8DZEY18AMT5J14VW42=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-5 create-a-landing-page-with-onelink-smart-banners=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-banners h_01K8X2TS8DAAN8JGJNJGJKD6PP=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-banners h_01K8X2TS8DC94419514NK8Y98S=endtoend-data-flow::e62b5c1b h_01K8X2TS8E5EHDFX6RW34TQN4A=set-up-a-smart-banners-landing-page h_01K8X2TS8EC16VZXC9JZJ9Y3VG=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-6 TikTok-view=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-webtoapp-attribution-data-from-november-2-2025=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-in-the-dashboard=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 h_01K88J8JFNMHCVZ0C34E3D7AST=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 view-in-raw-data-and-api-reports=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-api h_01K88J8JFN8W2572N92466YFZQ=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-api h_01_measure-cost-clicks-impressions-tiktok-w2a=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D1%8F%D0%B9%D1%82%D0%B5-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D1%8B-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D1%8B measure-cost-clicks-impressions-tiktok-w2a=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D1%8F%D0%B9%D1%82%D0%B5-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D1%8B-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D1%8B h_01_tiktok_w2a_cost_note=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-7" />

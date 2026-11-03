---
title: Snapchat — запускайте веб-кампании
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
  created_at: '2025-11-27T14:39:44Z'
  edited_at: '2026-09-17T00:30:06Z'
  id: 41365000854161
  locale: ru
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ru/articles/41365000854161
---
> **Краткий обзор:** Используйте веб-кампании Snapchat Ads, чтобы атрибутировать конверсии «веб → приложение» из рекламы Snapchat Ads.

## Обзор

AppsFlyer поддерживает интеграцию с Snapchat Ads (`snapweb_int`) для веб-кампаний по привлечению пользователей, позволяя передавать данные атрибуции и конверсий напрямую через Events API Snapchat. Затем Snapchat может использовать эти данные для оптимизации таргетинга рекламы, оценки эффективности и создания пользовательских аудиторий.

> 🚧 **Важно!**
>
> В настоящее время интеграция с Snapchat Web не поддерживает отправку постбэков повторного вовлечения в CAPI.

### Необходимые условия

Прежде чем активировать веб-интеграцию Snapchat, убедитесь, что у вас есть бизнес-аккаунт в œœœœ.

### Как создать веб-кампанию в Snapchat Ads

Эта статья содержит информацию и пошаговые инструкции по настройке веб-кампании в Snapchat Ads для мобильных приложений с помощью AppsFlyer. Настройка включает определение интеграции между Snapchat Ads и AppsFlyer, конфигурацию кампании на обеих платформах и создание целевых страниц с помощью OneLink Smart Script или OneLink Smart Banners.

Процесс настройки включает следующие обязательные этапы:

* [Настройте веб-интеграцию Snapchat Ads в AppsFlyer](#настройте-веб-интеграцию-snapchat-ads-в-appsflyer) (Обязательно)
* [Настройка интеграции AppsFlyer в Snapchat Ads](#настройте-интеграцию-appsflyer-в-snapchat-ads) (Обязательно)

И следующие необязательные шаги:

* [Создание целевой страницы с помощью OneLink Smart Script](#создание-целевой-страницы-с-помощью-onelink-smart-script) (необязательно)
* [Создание целевой страницы с помощью OneLink Smart Banners](#создание-целевой-страницы-с-помощью-onelink-smart-banners) (необязательно)

## Настройте веб-интеграцию Snapchat Ads в AppsFlyer

Начните с активации веб-интеграции Snapchat Ads. Затем настройте постбэки, которые AppsFlyer отправляет в Events API.

<div id="1-activate-the-snapchat-ads-web-integration" />

<Accordion title="1. Активируйте веб-интеграцию Snapchat Ads">

Чтобы активировать веб-интеграцию Snapchat Ads:

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Маркетплейс партнеров**.
2. Надите **Snapchat Web** и выберите его.
3. Нажмите **Настроить интеграцию**. Вы будете перенаправлены на страницу настроек **Активные интеграции**.
4. На вкладке **Интеграция** включите переключатель **Активировать партнера**. Переключатель должен оставаться в положении <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активирован</Anchor> всё время, пока вы работаете с партнером.
5. Отключите опцию **Расширенная конфиденциальность** (если вы настраиваете интеграцию приложения iOS).
6. **Обмен данными расширенного сопоставления:** Включите, чтобы передавать в Snapchat поля расширенного сопоставления, такие как хешированный адрес электронной почты, хешированный номер телефона, хешированное имя и хешированную фамилию, если эти поля включены в информацию о событии, отправляемую в AppsFlyer. Более подробную информацию см. здесь: <Anchor target="_blank" href="/marketers/ru/docs/advanced-matching-data-sharing">Обмен данными с расширенным сопоставлением</Anchor>.
7. **Идентификатор пикселя:** Введите идентификатор пикселя. Вы можете сгенерировать его или получить его из Snapchat Ads Manager, следуя инструкциям, приведенным в разделе [Официальная документация Snapchat Ads](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)
8. **Токен доступа:** Введите токен доступа. Чтобы сгенерировать или получить токен, следуйте[инструкции в официальной документации Snapchat Ads](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2. Активируйте атрибуцию по просмотрам">

AppsFlyer поддерживает атрибуцию по просмотрам для веб-кампаний Snapchat, если вы используете целевую страницу с поддержкой [Smart Script](#создание-целевой-страницы-с-помощью-onelink-smart-script) или [Smart Banner](#set-up-smart-banners-landing-page). Это позволяет использовать вероятностное моделирование (PMOD) для атрибуции установок приложений, вызванных показами объявлений, даже если пользователи не нажимают на рекламу.

Если доступно, в постбэк к Meta будет включен параметр `ScCid` для повышения точности атрибуции.

**Чтобы включить атрибуцию по просмотрам Snapchat Web:**

1. В AppsFlyer в боковой панели откройте **Активные интеграции** > **Snapchat Ads web**.
2. На вкладке **Интеграция** прокрутите до раздела **Атрибуция установки**.
3. Включите **Атрибуцию установок по просмотрам**.
4. **[необязательно]** Включите **Равный приоритет кроссплатформенной атрибуции** и задайте для него окно ретроспективы. Более подробно см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Включите равный приоритет для кроссплатформенных показов</Anchor>.
5. Откройте вкладку **Ссылка атрибуции**.
6. Прокрутите к разделу **Атрибуция по просмотрам** и установите **окно атрибуции по просмотрам** (до 24 часов).
7. Нажмите **Сохранить интеграцию** для применения ваших настроек.

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3. Настройка постбэков по внутренним событиям приложений">

В настоящее время установки являются единственными событиями, которые запускают автоматические постбэки в Snapchat Ads. Для всех других типов событий вы можете создавать пользовательские постбэки, сопоставляя события AppsFlyer с событиями Snapchat Ads. Эти постбэки можно просмотреть в менеджере Snapchat Ads.

Для настройки постбэков по внутренним событиям приложения выполните следующие действия:

1. Активируйте **Постбэки по внутренним событиям приложения**.
2. При необходимости задайте окно отправки постбэков событий внутри приложения (подробнее об общей настройке окна отправки постбэков см. в разделе  <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">«Настройка постбэков событий в приложении»).</Anchor>
3. Нажмите**Добавить событие**, чтобы добавить событие в список.
4. В столбце **Событие AppsFlyer** выберите название события из выпадающего списка. AppsFlyer получает название события либо из SDK, интегрированного в ваше приложение, либо из межсерверных событий.
5. В столбце **Сопоставлено с событием партнера**, выберите наиболее подходящее предопределенное событие партнера из списка.
6. В столбце **Для пользователей из** выберите **Только этот партнер**, чтобы постбэки событий в приложении отправлялись только по событиям пользователей, пришедших от этого партнера.
7. В столбце **включая**  выберите, отправлять ли события с их значениями дохода. См.  <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#данные-для-включения-в-постбэки">Данные для включения в постбэки</Anchor>.

   > 📘 **Примечание:**
   >
   > * Если вы настраиваете событие покупки, в столбце **«Включая»** установите значение **«Значения и выручка».** Выбор любого другого варианта приведет к сбою отправки постбэка.
   > * В настоящее время вы можете настроить только событие покупки для включения дохода.

8. [Необязательно] Нажмите на значок **Добавить условие**, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события.
9. Нажмите **Сохранить интеграцию**.
10. [Необязательно] После сохранения интеграции и пока вы находитесь на странице конфигурации, вы можете интегрировать дополнительные приложения с партнером:
    1. В верхнем левом углу нажмите на название приложения под названием партнера, чтобы открыть список приложений.
    2. Выберите другое приложение из списка.
    3. Повторите вышеуказанные шаги для выбранного приложения.

</Accordion>

## Настройте интеграцию AppsFlyer в Snapchat Ads

Выполните следующие шаги в Snapchat Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Установите тип, цель и задачи кампании">

Вы можете выбрать любое предопределенное событие INAPP, отправленное из AppsFlyer, в качестве цели кампании, или выбрать «PAGE\_VIEW», если вы хотите оптимизировать под мобильные установки приложений.

> ❗️ **Предупреждение**
>
> Убедитесь в том, что вы не выбираете **События приложений;** в противном случае Snapchat будет запрашивать эти конверсии с использованием SRN API, что может привести к несоответствиям в отчетности и оптимизации.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Укажите целевой URL">

1. В разделе  **«Назначение»** в поле **«URL-адрес веб-сайта»**введите URL, который будет целевым адресом вашего объявления. URL-адрес должен соответствовать одному из следующих значений:
   * **Целевая веб-страница:** Использование целевой страницы рекомендуется в следующих случаях:

     * У вас есть приложение на нескольких платформах.
     * Вы хотите использовать целевую страницу для предоставления дополнительной информации о рекламируемом продукте.
     * Вы хотите использовать целевую страницу для сбора дополнительных данных.

     Для всех этих вариантов использования создайте [целевую страницу с помощью Smart Script](#создание-целевой-страницы-с-помощью-onelink-smart-script) или [Smart Banner](#создание-целевой-страницы-с-помощью-onelink-smart-banners).
   * **Ссылки атрибуции AF** Рекомендуется использовать атрибуционные ссылки AF (OneLink, одноплатформенные или кроссплатформенные), когда нужно, чтобы пользователь сразу переходил в магазин и загружал приложение, минуя целевую страницу.
2. Нажмите **Создать параметр URL**, чтобы добавить параметры URL к URL (будь то URL-адрес целевой страницы или ссылка атрибуции AF).
3. В разделе **Настраиваемые параметры** нажмите **Добавить параметр**.

   [<Image alt="Screenshot 2025-11-26 at 8.56.29.png" src="https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png" width="2810px" />](https://files.readme.io/cb3ceba75974f7a57d7f26c3587fd0d0c401427d26fcacff40f2514981b9b02f-small-41366139737873.png)
4. Сопоставьте параметры AppsFlyer с их значениями в Snapchat.
   * Если в качестве целевого URL используется **целевая страница, атрибуционная ссылка OneLink или одноплатформенная атрибуционная ссылка**, сопоставьте следующие параметры AF с их эквивалентами в Snapchat:

| Параметр AF | Соответствующее значение Snapchat |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `snapweb_int` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_channel`</Anchor> | `{{site_source_name}}` |

     Пример итогового URL должен быть таким:

     ```
     https://app.appsflyer.com/{app_id}?pid=snapweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
     ```

     * Если APK вашего приложения НЕ размещен в Google Play Store, добавьте параметр <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> и сопоставьте с ним URL-адрес магазина, например, `https://Add-your-store-url.com`

* Если ваш целевой URL-адрес — **магазин приложений для ПК или консоли**, создайте ссылку, следуя инструкциям в таблице ниже. Дополнительную информацию см. здесь: <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Прямые ссылки атрибуции для CTV, ПК и консолей</Anchor>

| Структура ссылки атрибуции |  |
| --- | --- |
| Базовый URL-адрес | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Обязательные параметры пути | ▪ platformExample: steam  <br />▪ app\_idExample: 123456 |
| Обязательные параметры запроса | af\_media\_source  <br />af\_campaign\_id  <br />▪ af\_r |
| Другие параметры | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links#параметры">См. все параметры</Anchor> |
| Структура URL-адреса | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

  Сопоставьте следующие параметры AppsFlyer с их аналогами в Snapchat:

| Параметр AF | Соответствующее значение Snapchat |
| --- | --- |
| `media_source (медиа-источник)` | `snapweb_int` |
| `af_campaign` * | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_channel`</Anchor> | `{{site_source_name}}` |

  * Чтобы упростить анализ кампании, указывайте тип кампании -- веб или мобайл -- в префиксе или суффиксе названия кампании (например, название-кампании\_web).

  Пример кроссплатформенного URL:

  ```
  https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
  ```

  > 📘 **Примечание:**
  >
  > Snapchat добавляет`ScCid={{ScCid}}` к целевому URL-адресу автоматически при нажатии на рекламу


  > 📄
  >
  > Полное руководство по параметрам ссылки AF см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#параметры-ссылки-атрибуции">Параметры ссылки атрибуции</Anchor>.


</Accordion>

## Создание целевой страницы с помощью OneLink Smart Script

**Путь пользователя:** Пользователь нажимает на рекламу Snapchat и перенаправляется на ваш мобильный сайт. Они попадают на страницу с кнопками-CTA, предлагающими скачать ваше приложение с одной или нескольких платформ. Нажатие кнопки перенаправляет пользователя в магазин.

<div id="endtoend-data-flow" />

<Accordion title="Сквозной поток данных">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. URL-адрес рекламы Snapchat включает в себя `pid=snapweb_int``pid=snapweb_int` параметр. Когда пользователь нажимает на рекламу, параметр `pid=snapweb_int` автоматически добавляется к URL-адресу.
2. Пользователь перенаправляется на целевой URL-адрес — целевую страницу, содержащую Smart Script.
3. Когда целевая страница загружается, Smart Script отправляет в AppsFlyer показ с входящими параметрами URL. Показ позволит выполнить атрибуцию просмотров с целевой веб-страницы. Подробнее об атрибуции по показам и просмотрам читайте <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">здесь</Anchor>.
4. Smart Script генерирует исходящие URL-адреса для кнопок CTA на странице на основе параметров входящего URL-адреса, включая параметр `ScCid`. Кнопки могут вести к:
   * Google Play и App Store через ссылку атрибуции OneLink.
   * Магазины на нескольких платформах (например, CTV, Epic и Steam). В этом сценарии Smart Script создаёт отдельную атрибуционную ссылку для каждой платформы, ведущую в магазин соответствующей платформы.
   * Загрузка файла APK на устройство пользователя.
5. Когда пользователь нажимает кнопку CTA, клик срабатывает и регистрируется в AppsFlyer.
6. Пользователь перенаправляется в магазин и скачивает приложение.
7. Когда пользователь открывает приложение, в AppsFlyer регистрируется событие установки.
8. AppsFlyer атрибутирует установку на основе вероятностного моделирования или детерминированно, если доступна [реферальная ссылка](https://www.appsflyer.com/glossary/install-referrer/).
9. Постбэк, содержащий `ScCid``ScCid` параметры и другие параметры события генерируются и отправляются в Snapchat через API событий. Snapchat использует параметр `ScCid` для идентификации конкретного клика, тогда как другие параметры помогают оптимизировать кампанию.

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="Настройка целевой страницы Smart Script">

Чтобы настроить кампании Snapchat Ads с помощью Smart Script, выполните следующие действия:

1. Настройте шаблон атрибуционных ссылок OneLink для кампании. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Как создавать шаблоны OneLink</Anchor>.
2. Создайте Smart Script. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Как создать OneLink Smart Script</Anchor>.

   > 📘 **Примечание:**
   >
   > В приведенных ниже инструкциях описаны конкретные шаги, необходимые для настройки кампании в Snapchat Ads с помощью Smart Script. Подробное руководство по настройке кампаний Smart Script см. в статье <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Как создать OneLink Smart Script</Anchor> раздел <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">Настройка OneLink Smart Script V2</Anchor> .

3. Убедитесь, что все необходимые параметры URL добавлены к входящему URL-адресу. Чтобы проверить параметры, добавленные к входящему URL, откройте Snapchat Ads Manager и проверьте параметры URL, которые вы задали при создании целевого URL-адреса. Для получения дополнительной информации см. раздел [Настройка целевого URL-адреса](#2-set-destination-url).
4. Сопоставьте входящие параметры URL, необходимые для кампании Snapchat Ads, с исходящими параметрами URL. Эти параметры отправляются в AppsFlyer, когда пользователь нажимает кнопку CTA :
   * **PID**: Убедитесь, что Smart Script принимает значение параметра `pid=snapweb_int` из входящего URL-адреса и сопоставляет его с соответствующими параметрами в исходящем URL-адресе.
   * **ScCid**: The `ScCid` параметр необходим для успешной отправки постбэков событий в приложении в Snapchat. Параметр **должен быть сопоставлен вручную в разделе `ScCid`Сопоставление параметров URLScCid на странице `ScCid`Smart ScriptScCid:**

     1. Выберите **Пользовательский параметр** в разделе **Сопоставление для**.
     2. В **Исходящий параметр URL** и **Входящие параметры URL,** введите **ScCid**.

     > 📘 **Примечание:**
     >
     > Чтобы отобразить в отчетах о необработанных данных AppsFlyer, вы также должны сопоставить входящий параметр `ScCid` (отдельно от исходящего параметра `ScCid`) с одним из исходящих параметров `af_sub[1–5]`.


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="Настройка кроссплатформенной целевой страницы Smart Script">

Чтобы настроить кампании Snapchat Ads с помощью Smart Script для кроссплатформенных целевых страниц, выполните следующее:

1. Настройте шаблон атрибуционных ссылок OneLink для кампании. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Как создавать шаблоны OneLink</Anchor>.
   * Активируйте шаблон OneLink для кроссплатформенной атрибуции. Для получения дополнительной информации см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-cross-platform-links-for-multi-device-campaigns#создание-шаблона-onelink-для-кроссплатформенной-атрибуции">Создайте шаблон OneLink для кросс-платформенной атрибуции</Anchor>.
2. Убедитесь, что все необходимые параметры URL добавлены к входящему URL-адресу. Чтобы просмотреть параметры, добавленные к входящему URL-адресу, откройте Snapchat Ads Manager и проверьте параметры URL-адреса, заданные при создании целевого URL-адреса. Для получения дополнительной информации см. раздел [Настройка целевого URL-адреса](#2-set-destination-url).
3. Определите для каждого входящего параметра исходящий параметр, которому он будет сопоставлен. Например, входящий параметр `af_site_id` во входящем URL будет сопоставлен параметр  `af_site_id` в исходящем URL.
4. Определите значение по умолчанию для обязательных исходящих параметров, которые не могут быть пустыми.
5. Отправьте своему разработчику следующую информацию:
   * Сопоставление входящих и исходящих параметров. Разработчик создаст скрипт, который сгенерирует исходящий прямой URL-адрес на основе сопоставления входящих и исходящих параметров.
   * Значения параметров по умолчанию. Скрипт заполнит параметры исходящего URL-адреса значениями по умолчанию, если отсутствуют соответствующие значения параметров входящего URL-адреса.
   * Если вы используете ссылку атрибуции OneLink, отправьте домен и идентификатор шаблона своему разработчику. Разработчик использует их для создания исходящего URL-адреса OneLink. Например: `yourbrand.onelink.me/A1b2` или пример брендированного домена: `click.yourbrand.com/A1b2`
   * Отправьте вашему разработчику следующие ссылки Dev Hub:
     * [Инструкции и примеры кода](https://dev.appsflyer.com/hc/docs/create-direct-click-url) для создания исходящих прямых URL-адресов для немобильных платформ.
     * [Демо и инструкция](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) по созданию кроссплатформенной целевой страницы.

* Напомните разработчику включить входящий параметр `ScCid` в исходящий URL-адрес.

  > 📘 **Примечание:**
  >
  > Для отображения в отчетах по необработанным данным AppsFlyer входящий параметр `ScCid` также должен быть сопоставлен (в дополнение к исходящему параметру `ScCid`) с одним из исходящих параметров `af_sub[1-5]`.


</Accordion>

## Создание целевой страницы с помощью OneLink Smart Banners

**Путь пользователя:** Пользователь нажимает на рекламу Snapchat и перенаправляется на ваш мобильный сайт. Они попадают на страницу, где отображается умный баннер с кнопкой-призывом скачать приложение из App Store.

<div id="endtoend-data-flow::b905b9a5" />

<Accordion title="Сквозной поток данных">

1. URL-адрес рекламы Snapchat включает в себя `pid=snapweb_int``pid=snapweb_int` параметр. Когда пользователь нажимает на рекламу, параметр `pid=snapweb_int` автоматически добавляется к URL-адресу.
2. Пользователь перенаправляется на целевой URL-адрес — целевую страницу, содержащую Smart Banner.
3. При загрузке целевой страницы Smart Banner отправляет в AppsFlyer событие <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">показа</Anchor>, которое включает параметры входящего URL-адреса. Этот показ позволяет выполнить атрибуцию по просмотрам для целевой страницы. Чтобы узнать о показах и атрибуции по просмотрам, см. <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">Создайте пользовательский URL для показа</Anchor>.
4. Smart Banner генерирует исходящий URL-адрес для кнопки CTA на баннере. Исходящий URL-адрес основан на параметрах входящего URL-адреса, включая параметр `ScCid`. Smart Banner может генерировать только ссылки на основе OneLink.
5. Когда пользователь нажимает кнопку Smart Banner CTA, клик срабатывает и регистрируется в AppsFlyer.
6. Пользователь перенаправляется в магазин и скачивает приложение.
7. Когда пользователь открывает приложение, в AppsFlyer регистрируется событие установки.
8. AppsFlyer атрибутирует установку на основе вероятностного моделирования или детерминированно, если доступна реферальная ссылка.
9. Постбэк, содержащий `ScCid``ScCid` параметры и другие параметры события генерируются и отправляются в Snapchat через API событий. Snapchat использует параметр `ScCid` для идентификации конкретного клика, тогда как другие параметры помогают оптимизировать кампанию.

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="Настройте целевую страницу с умным баннером Smart Banners.">

Чтобы настроить кампании Snapchat Ads с использованием Smart Banners, выполните следующее:

1. Настройте шаблон атрибуционных ссылок OneLink для кампании. Для получения дополнительной информации см. раздел <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Как создавать шаблоны OneLink</Anchor>.
2. Создайте Smart Banner

   > 📘 **Примечание:**
   >
   > Ниже приведены инструкции, описывающие конкретные шаги по настройке кампании Snapchat Ads с использованием Smart Banners. Подробное руководство по настройке кампаний при помощи смарт-баннеров приведено в <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers#настройки">разделе «Настройка»</Anchor> статьи <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers">Смарт-баннеры: mobile web-to-app (для маркетологов)</Anchor>.

3. Установите параметры Smart Banner для кампаний Snapchat Ads:

   * Убедитесь, что все необходимые параметры URL добавлены к входящему URL-адресу.
   * Чтобы просмотреть параметры, добавленные к входящему URL, откройте Snapchat Ads Manager и просмотрите параметры URL, которые вы установили, когда [создавали целевой URL-адрес](#2-set-destination-url).

   > 📘 **Примечание:**
   >
   > Важно чтобы `pid=snapweb_int` и `ScCid` были доступны во входящем URL-адресе, что позволяет Smart Banner собирать их. Эти два параметра необходимы для атрибуции и отправки постбэков в Snapchat Ads.


</Accordion>

## **Посмотреть данные атрибуции web-to-app**

Хотя события конверсии, происходящие в вебе, отправляются в Snapchat с исходным PID `snapweb_int`, на дэшборде и в отчётах о сырых данных AppsFlyer они отображаются под PID `snapchat_int`. Это относится как к основным событиям конверсии, так и к событиям-ассистам конверсии.

Этот унифицированный вид отчетов позволяет анализировать эффективность кампаний для веб и приложений в одном месте, включая подробные отчеты о затратах на мобильные устройства и веб.

### **Посмотреть на дэшборде**

Вся атрибуция Snapchat web-to-app отображается как `snapchat_int` в дэшбордах «Обзор» и «Активность». Это обеспечивает единый консолидированный обзор результатов кампаний на всех платформах. Используйте стандартные фильтры и разбивки, чтобы сравнить трафик приложений и веб-трафик в данных Snapchat.

### **Просмотр в отчетах о сырых данных и отчетах API**

* В **экспортах сырых данных и ответах API** идентификатор `snapchat_int`PID присутствует в поле `media_source` для веб-активности Google. Чтобы верифицировать детали настройки веб-кампании, обратитесь к полю **, которое показывает `snapchat_int` как PID, использованный при создании веб-кампаний.**
* **Отчеты о постбэках** показывают `snapweb_int` как оригинальный медиаисточник, к которому был отправлен постбэк.

## Характеристики и ограничения

| Специфика | Примечания |
| --- | --- |
| Данные о затратах | Данные о стоимости для Snapchat Ads в вебе(`snapweb_int`) не извлекаются автоматически. Вместо этого их необходимо импортировать вручную, используя  <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data#процедуры">один из двух поддерживаемых методов: загрузка файла через электронную почту или ручная загрузка через интерфейс AppsFlyer</Anchor> Это касается всех пользователей, включая подписчиков ROI360. Это касается всех пользователей, включая подписчиков ROI360. |
| Клики и показы (временно ограничено) | Клики и показы для веб-кампаний временно недоступны в Snapchat SRN (`snapchat_int`). |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01KB2W28THC55F0AJ0KZJPQ6S5=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01KB2W28THSST3148Y5Y07PJ7S=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01KB2W28THW7E6TRVTTHJZ9BP4=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F how-to-create-a-snapchat-ads-web-campaign=%D0%BA%D0%B0%D0%BA-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D1%82%D1%8C-%D0%B2%D0%B5%D0%B1-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D1%8E-%D0%B2-snapchat-ads h_01KB2W28THTST7HWTJA9TTGPGG=%D0%BA%D0%B0%D0%BA-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D1%82%D1%8C-%D0%B2%D0%B5%D0%B1-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D1%8E-%D0%B2-snapchat-ads set-up-snapchat-ads-web-integration-in-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-snapchat-ads-%D0%B2-appsflyer h_01KB2W28THQJF8K4AWTRXNA3RX=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-snapchat-ads-%D0%B2-appsflyer h_01KB2W28TH6NZCGCJAN8K3WFGA=1-activate-the-snapchat-ads-web-integration h_01KB2W28TJ6XY7WKR4VC5XS7DS=2-enable-viewthrough-attribution h_01KB2W28TJGRKP3C50ZPQAWAS9=3-set-inapp-event-postbacks h_01KB2W28TJ14KC606KE82Q7BB7=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 set-up-appsflyer-integration-in-snapchat-ads=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-appsflyer-%D0%B2-snapchat-ads h_01KB2W28TJVZ1BX94SZYH1K5EM=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-appsflyer-%D0%B2-snapchat-ads h_01KB2W28TJ2R95JK7C1PQE644C=1-set-the-campaign-type-objective-and-goals h_01KB2W28TJ4BK88DVYJG4XYE0S=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01KB2W28TJB1V382HD09M9Y0C3=2-set-destination-url h_01KB2W28TJT7QZ2P7AZ5X61ZXV=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 create-a-landing-page-with-onelink-smart-script=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-script h_01KB2W28TJQA1TBXXQ7MA1F0CB=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-script h_01KB2W28TJ4J426HD3ZFHXAV4J=endtoend-data-flow h_01KB2W28TJR8S029FJ3Y81MG8Y=set-up-a-smart-script-landing-page h_01KB2W28TJBYHKYNQRMJ4ZGWYD=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 h_01KB2W28TJZMQEDSNVWRZCNXYD=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-3 h_01KB2W28TJT0TEFB97RXEGDVRM=set-up-a-smart-script-crossplatform-landing-page h_01KB2W28TJ6XWR7GW4SQQAKZH9=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-4 create-a-landing-page-with-onelink-smart-banners=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-banners h_01KB2W28TJM0X7K5Z7M2120MT9=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-onelink-smart-banners h_01KB2W28TKJZBNFR335SXKY6FC=endtoend-data-flow::b905b9a5 h_01KB2W28TKKA9NTQEC7ZA9E6EA=set-up-a-smart-banners-landing-page h_01KB2W28TKW8B6H4W0R9YJM3ZE=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-5 h_01KB2W28TKRH3NC73J2JHNSMWD=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-6 view-webtoapp-attribution-data=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app h_01KB2W28TKDAV34JGYJKF2VT43=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-in-the-dashboard=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 h_01KB2W28TKNWYXJX189EP2HPN2=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 view-in-raw-data-and-api-reports=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-api h_01KB2W28TKJ1MAMM00KY3M3S2W=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-api traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KB2W28TKFY74YBXHD91QP9V0=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

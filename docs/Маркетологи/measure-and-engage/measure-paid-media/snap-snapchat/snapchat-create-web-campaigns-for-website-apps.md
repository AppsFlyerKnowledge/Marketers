---
title: Snapchat — создание веб-кампаний для веб-приложений
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
  created_at: '2026-04-29T09:02:24Z'
  edited_at: '2026-09-01T00:32:37Z'
  id: 46196482479249
  locale: ru
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ru/articles/46196482479249
---
> **Краткий обзор:** Настройте интеграцию Snapchat Web Ads для вашего сайта, чтобы отправлять сигналы конверсии в Snapchat через API конверсий.

<div id="overview" />

## Обзор

AppsFlyer поддерживает интеграцию с Snapchat Web Ads (`snapweb_int`) для кампаний в приложениях сайтов, позволяя напрямую сообщать о данных об атрибуции и конверсиях через API конверсий Snapchat. Затем Snapchat может использовать эти данные для оптимизации таргетинга рекламы, оценки эффективности и создания пользовательских аудиторий.

Вот как это работает: когда пользователь кликает по рекламе в Snapchat и попадает на ваш сайт, а затем завершает событие на сайте (например, покупку или регистрацию), AppsFlyer отправляет сигнал конверсии в Snapchat через API конверсий. Snapchat использует эти данные для оптимизации таргетинга рекламы и измерения эффективности кампании.

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/web-performance-measurement-overview">Web Performance Measurement — обзор</Anchor>

<div id="important" />

> 🚧 **Важно!**
>
> В настоящее время интеграция не поддерживает отправку постбэков о повторном взаимодействии через API конверсий.

<div id="prerequisites" />

### Необходимые условия

Перед активацией интеграции Snapchat Web Ads для приложения вашего сайта убедитесь, что у вас есть:

* Веб-приложение, созданное в AppsFlyer
* Бизнес-аккаунт в <Anchor target="_blank" href="https://ads.snapchat.com/">Snapchat Ads Manager</Anchor>

<div id="how-to-set-up-snapchat-ads-for-your-website-app" />

### Как настроить Snapchat Web Ads для приложения вашего сайта

Настройка включает определение интеграции между Snapchat Web Ads и AppsFlyer, а также настройку кампании в Snapchat Ads Manager. Он включает следующие шаги:

* [Часть 1: Настройте интеграцию Snapchat Web Ads в AppsFlyer (обязательно)](#часть-1-настройте-интеграцию-snapchat-web-ads-в-appsflyer)
* [Часть 2: Настройка интеграции AppsFlyer в Snapchat Ads (Обязательно)](#часть-2-настройте-интеграцию-appsflyer-в-snapchat-web-ads)

<div id="part-1-set-up-snapchat-ads-integration-in-appsflyer" />

## Часть 1: Настройте интеграцию Snapchat Web Ads в AppsFlyer

Начните с активации интеграции Snapchat Web Ads. Затем настройте постбэки, которые AppsFlyer отправляет в API конверсий.

<div id="1-activate-the-snapchat-ads-integration" />

<Accordion title="1. Активируйте интеграцию Snapchat Web Ads">

Чтобы активировать интеграцию Snapchat Web Ads:

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Маркетплейс партнёров**.
2. Найдите **Snapchat** и выберите его.
3. Нажмите **Настроить интеграцию**. Вы будете перенаправлены на страницу настроек **Активные интеграции**.
4. На вкладке **Интеграция** включите переключатель **Активировать партнера**. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.
5. **Идентификатор пикселя:** Введите идентификатор пикселя. Вы можете сгенерировать или получить его из Snapchat Ads Manager, следуя инструкциям в <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">Документации Snapchat Web Ads</Anchor>.
6. **Токен доступа:** Введите токен доступа. Чтобы создать или получить его, следуйте <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">инструкции в официальной документации Snapchat Web Ads</Anchor>.

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. Настройка постбэков по внутренним событиям приложений">

Вы можете определить, какие события веб-конверсии AppsFlyer отправляет в Snapchat Ads, сопоставив события AppsFlyer с событиями Snapchat Web Ads. Эти постбэки можно посмотреть в менеджере Snapchat Ads. Snapchat использует отображаемые события для оптимизации кампании и отчетности.

Настройка постбэков по внутренним событиям приложений:

1. Активируйте **Постбэки событий внутри приложения**.
2. Если нужно, настройте окно для событий в приложении. Читать дальше в <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">Конфигурация постбэков событий в приложении</Anchor>.
3. Нажмите**Добавить событие**, чтобы добавить событие в список.
4. В столбце **Событие AppsFlyer** выберите название события из списка. AppsFlyer получает имя события либо из Web SDK, интегрированного на вашем сайте, либо из событий server-to-server (S2S), которые вы отправляете в AppsFlyer.
5. В столбце **Сопоставлено с событием партнера** выберите наиболее подходящее предопределенное событие партнера из списка.
6. В столбце **Для пользователей из** выберите подходящий вариант:
   * **Только этот партнер** отправляет события, атрибутированные рекламе Snapchat Web Ads.
   * **Все медиаисточники, включая органические**, отправляют все события независимо от источника атрибуции.
7. В столбце **включая** выберите, отправлять ли события с их значениями дохода. См. <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#данные-для-включения-в-постбэки">Данные для включения в постбэки</Anchor>.
8. [Необязательно] Нажмите значок **Добавить условие**, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события.

   > 📘 **Примечание**
   >
   > * Если вы настраиваете событие покупки, установите в столбце **включая** значение **Значения и выручка**. При выборе любого другого варианта отправка постбэка завершится с ошибкой.
   > * Сейчас включить доход можно только для события покупки.

9. Нажмите **Сохранить интеграцию**.

<div id="note-2" />

<div id="note-1" />

> 📘 **Note**
>
> Если на вашем сайте также установлен Snap Pixel, отправляйте один и тот же идентификатор события и в AppsFlyer, и в Snapchat, чтобы AppsFlyer мог дедуплицировать события:
>
> * Включите `af_customer_event_id` в полезную нагрузку события, которую вы отправляете в AppsFlyer, — в `eventValue` для Web SDK или в `event_value` для API S2S (server-to-server).
> * Передайте то же значение в соответствующем событии Pixel.
>
> AppsFlyer передает это значение в Snapchat как идентификатор события. Затем Snapchat использует его, чтобы дедуплицировать серверное событие, полученное от AppsFlyer, с событием Pixel, поэтому AppsFlyer засчитывает конверсию только один раз.
>
> Если вы не отправляете `af_customer_event_id`, AppsFlyer автоматически генерирует идентификатор события. Этот идентификатор не будет совпадать с событиями Pixel.
>
> Дополнительную информацию см. в статье <Anchor target="_blank" href="/marketers/ru/docs/integrate-appsflyer-web-sdk">[Бета] Интеграция Web SDK AppsFlyer</Anchor>.

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-snapchat-ads" />

## Часть 2: Настройте интеграцию AppsFlyer в Snapchat Web Ads

Выполните следующие шаги в Snapchat Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Установите тип, цель и задачи кампании">

Вы можете выбрать любое заранее определённое внутри приложения событие, отправленное из AppsFlyer, в качестве цели вашей кампании. Выберите цель кампании, которая соответствует целям конверсии вашего сайта, например, привлечь трафик на сайт или оптимизировать конверсии на сайте.

</Accordion>

<div id="2-set-the-destination-url" />

<Accordion title="2. Задайте URL назначения">

1. В разделе **Назначение**, в поле**URL сайта** введите URL вашего сайта — страницу, на которую попадают пользователи после клика по вашей рекламе. **URL сайта** является основным вариантом назначения. Пользователи кликают по объявлению и попадают прямо на ваш сайт, чтобы завершить события конверсии.
2. **[Альтернативная] атрибуционная ссылка AF (OneLink):** Если вы хотите перенаправить пользователей на мобильное приложение с резервным вариантом на сайт, можно использовать ссылку на атрибуцию AF (OneLink) в качестве целевого URL.
3. Нажмите **Создать параметр URL** чтобы добавить параметры URL к целевому URL.
4. В разделе **Настраиваемые параметры** нажмите **Добавить параметр**.
5. Сопоставьте параметры AppsFlyer с их значениями в Snapchat.

| Параметр AF | Соответствующее значение Snapchat |
| --- | --- |
| `pid` | `snapweb_int` |
| `c` * | `{{campaign.name}}` |
| `af_c_id` | `{{campaign.id}}` |
| `af_adset` | `{{adSet.name}}` |
| `af_adset_id` | `{{adSet.id}}` |
| `af_ad` | `{{creative.name}}` |
| `af_ad_id` | `{{ad.id}}` |
| `af_channel` | `{{site_source_name}}` |

   * Для упрощения анализа кампании, указывайте в префиксе или суффиксе тип кампании – веб или мобайл (например, `campaign-name_web`).

   Лучший опыт по конфигурации параметров URL и разрешению источников трафика см. <Anchor target="_blank" href="/marketers/ru/docs/about-traffic-source-resolution">О разрешении источника трафика</Anchor>.

   Пример полученного URL:

   ```http
   https://www.example.com?pid=snapweb_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}
   ```

<div id="note-3" />

> 📘 **Примечание**
>
> Snapchat добавляет`ScCid={{ScCid}}` к целевому URL-адресу автоматически при нажатии на рекламу

</Accordion>

<div id="view-web-attribution-data" />

## Просмотр данных по атрибуции веба

Вот чего ожидать при просмотре данных атрибуции после настройки:

* **Экспорт исходных данных и ответы API** включают Snap Web в `media_source` поле для активности Snap в веб-формате.
* Чтобы проверить детали настройки веб-кампании, проверьте `original_url` поле, которое показывает `snapchat_int` как PID, используемый при создании веб-кампании.

> 📘 **Примечание**
>
> Отчетность дэшборда для кампаний веб-приложений пока недоступна. Объединённый отчёт, позволяющий анализировать эффективность веб-кампаний наряду с другими каналами, запланирован к выпуску в одном из будущих релизов.

<div id="measure-web-attribution-data-with-web-cost" />

## Измеряйте данные веб-атрибуции вместе с данными о затратах на веб.

Чтобы получить полный обзор эффективности данных о веб-атрибуции и данных о стоимости веба из Snapchat Ads, в панели управления и в <Anchor target="_blank" href="/marketers/ru/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Отчеты по стоимости ETL</Anchor>, убедитесь, что у вас есть <Anchor target="_blank" href="/marketers/ru/docs/roi360-onboarding-guide#о-roi360">Пакет ROI360</Anchor>, и вы завершаете следующую настройку:

1. Подключите стоимость к вашему веб-приложению через`snapchat_int` (не через `snapweb_int`) из вкладки**Стоимость** или со страницы**Параметры стоимости** . Дополнительные сведения о подключении к данным о стоимости см. в статье <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#включение-api-затрат">«Настройка API ROI360 для измерения данных о стоимости</Anchor>».
2. Укажите ID кампании (`af_c_id`) в URL целевой страницы. Убедитесь, что URL содержит полную иерархию кампании, чтобы максимально детализировать стоимость, клики и показы, сопоставленные с веб-атрибуцией.

<div id="traits-and-limitations" />

## Характеристики и ограничения

| Специфика | Примечания |
| --- | --- |
| Клики и показы | Клики и показы для веб-кампаний требуют <Anchor target="_blank" href="/marketers/ru/docs/roi360-onboarding-guide">Подписки на ROI360</Anchor>. |
| Повторное вовлечение | Постбэки повторного взаимодействия через API конверсий в настоящее время не поддерживаются. |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01KQC7RA5R1PS69N3015WY4QRY=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01KQC80MBB1KCVVNDSFSJHG5ZT=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5 h_01KQC7RA5RAY6R70GNHCYWAMRC=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01KQC7RA5R02QV60T81NX055DM=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F how-to-set-up-snapchat-ads-for-your-website-app=%D0%BA%D0%B0%D0%BA-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-snapchat-web-ads-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2%D0%B0%D1%88%D0%B5%D0%B3%D0%BE-%D1%81%D0%B0%D0%B9%D1%82%D0%B0 h_01KQC7RA5RPWP0X927ENN6KJ9V=%D0%BA%D0%B0%D0%BA-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-snapchat-web-ads-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2%D0%B0%D1%88%D0%B5%D0%B3%D0%BE-%D1%81%D0%B0%D0%B9%D1%82%D0%B0 part-1-set-up-snapchat-ads-integration-in-appsflyer=%D1%87%D0%B0%D1%81%D1%82%D1%8C-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-snapchat-web-ads-%D0%B2-appsflyer h_01KQC7RA5RY1HF9VHC332FVBFR=%D1%87%D0%B0%D1%81%D1%82%D1%8C-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-snapchat-web-ads-%D0%B2-appsflyer h_01KQC7RA5RJXR5N13SYW3QMMDQ=1-activate-the-snapchat-ads-integration h_01KQC7RA5R3TZZ8PPHHC8EXPG1=2-set-inapp-event-postbacks h_01KQC7RA5RZVTM2X3N6WXRTAT8=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 part-2-set-up-appsflyer-integration-in-snapchat-ads=%D1%87%D0%B0%D1%81%D1%82%D1%8C-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-appsflyer-%D0%B2-snapchat-web-ads h_01KQC7RA5REPX0WDDHT7YWDHMC=%D1%87%D0%B0%D1%81%D1%82%D1%8C-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-appsflyer-%D0%B2-snapchat-web-ads h_01KQC7RA5R8MDFAF9R5YH1TFPX=1-set-the-campaign-type-objective-and-goals h_01KQC7RA5SB11HRSQR493PM121=2-set-the-destination-url h_01KQC7RA5S422C22YQX1VQ4R7A=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 view-web-attribution-data=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1%D0%B0 h_01KQC7RA5SKRWGGCKV71MV8J56=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1%D0%B0 h_01KQC7RA5S5VWHT4DW2MPSMNY0=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 measure-web-attribution-data-with-web-cost=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D1%8F%D0%B9%D1%82%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B5-%D1%81-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-%D0%BE-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D0%B0%D1%85-%D0%BD%D0%B0-%D0%B2%D0%B5%D0%B1 h_01KQC7XYSWPTHVDY5R3EG8H4K2=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D1%8F%D0%B9%D1%82%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B5-%D1%81-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-%D0%BE-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D0%B0%D1%85-%D0%BD%D0%B0-%D0%B2%D0%B5%D0%B1 traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KQC7RA5SSZB8M8G00NTXG71K=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

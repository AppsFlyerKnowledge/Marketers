---
title: TikTok for Business — Создание веб-кампаний для веб-приложений
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-29T07:09:07Z'
  edited_at: '2026-09-01T00:32:51Z'
  id: 46191822292113
  locale: ru
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ru/articles/46191822292113
---
> **Краткий обзор:** Настройте интеграцию TikTok Web Ads для веб-приложения, чтобы отправлять сигналы о веб-конверсиях в TikTok через Events API.

## Обзор

AppsFlyer поддерживает интеграцию с TikTok Web Ads (`tiktokweb_int`) для рекламных кампаний веб-приложений, что позволяет вам отчитываться по данным атрибуции и данных конверсии напрямую через TikTok's Events API. Затем TikTok сможет использовать эти данные для оптимизации таргетинга рекламы, измерения эффективности и создания кастомных аудиторий.

Как это работает: когда пользователь кликает по рекламе TikTok, переходит на ваш сайт и выполняет событие (например, покупку или регистрацию), AppsFlyer отправляет сигнал конверсии в TikTok через Events API. TikTok использует эти данные для оптимизации таргетинга рекламы и измерения эффективности рекламных кампаний.

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/web-performance-measurement-overview">Измерение эффективности веб-сайта — обзор</Anchor>

> 🚧 **Важно!**
>
> В настоящее время данная интеграция не поддерживает отправку постбэков повторного вовлечения через Events API.

### Необходимые условия

Прежде чем активировать интеграцию TikTok Web Ads для вашего веб-приложения, убедитесь, что у вас есть:

* Веб-приложение, настроенное в AppsFlyer
* Бизнес-аккаунт в <Anchor target="_blank" href="https://getstarted.tiktok.com/grow-your-business-gb">TikTok Ads Manager</Anchor>

### Как настроить TikTok Web Ads для вашего веб-приложения

Настройка включает в себя определение интеграции между TikTok Web Ads и AppsFlyer, а также настройку кампании в TikTok Ads Manager. Он состоит из следующих частей:

* [Часть 1: Настройте интеграцию TikTok Web Ads в AppsFlyer](#часть-1-настройте-интеграцию-с-tiktok-web-ads-в-appsflyer) (обязательно)
* [Часть 2: Настройте интеграцию с AppsFlyer в TikTok Web Ads](#часть-2-настройте-интеграцию-с-appsflyer-в-tiktok-web-ads) (обязательно)

## Часть 1: Настройте интеграцию с TikTok Web Ads в AppsFlyer

Для начала активируйте интеграцию с TikTok Web Ads и настройте отправку постбэков, которые AppsFlyer передает в Events API.

<div id="1-activate-the-tiktok-ads-integration" />

<Accordion title="1. Включить интеграцию с TikTok Web Ads">

Чтобы активировать интеграцию с TikTok Web Ads:

1. В AppsFlyer в боковом меню перейдите в раздел **Сотрудничество** > **Маркетплейс партнёров**.
2. Найдите **«TikTok For Business — Advanced SRN**» (или `tiktokweb_int`) и выберите его.
3. Нажмите **Настроить интеграцию**. Вы будете перенаправлены на страницу настроек **Активные интеграции**.
4. На вкладке **Интеграция** включите переключатель **Активировать партнера**. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.
5. **Идентификатор пикселя:** Введите идентификатор пикселя. Вы можете сгенерировать его или получить в TikTok Ads Manager, следуя инструкциям, приведенным в <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">документации</Anchor> <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">руководстве TikTok</Anchor>.
6. Токен доступа: Введите токен доступа. Чтобы создать или получить его, следуйте инструкциям, приведенным в <Anchor target="_blank" href="https://business-api.tiktok.com/portal/docs?id=1771100865818625">руководстве TikTok</Anchor>.
7. **Ограничить использование персональных данных пользователей в TikTok Web Ads' :** Включите этот переключатель, чтобы обеспечить соблюдение <Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests">законов о защите данных</Anchor>.

> 📘 **Примечание**
>
> Включение функции обеспечения соблюдения правовых норм CCPA ограничивает объем данных, поступающих от пользователей TikTok Web Ads, проживающих в Калифорнии или других штатах США, относящихся к категории «чувствительных».

</Accordion>

<div id="2-set-inapp-event-postbacks" />

<Accordion title="2. Настройка постбэков по внутренним событиям приложений">

Вы можете определить, какие события веб-конверсии AppsFlyer будет отправлять в TikTok Ads, сопоставив события AppsFlyer с событиями TikTok Web Ads. Эти постбэки можно просматривать в TikTok Ads Manager, а TikTok использует сопоставленные события для оптимизации кампаний и составления отчетности.

Настройка постбэков по внутренним событиям приложений

1. Активируйте **Постбэки событий внутри приложения**.
2. При необходимости настройте окно отправки постбэка для событий в приложении. Подробнее\n о настройке окна постбэка событий в приложении см. в разделе\n <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">In-app event postback configuration</Anchor>.
3. Нажмите**Добавить событие**, чтобы добавить событие в список.
4. В столбце **Событие AppsFlyer** выберите название события из выпадающего списка. AppsFlyer получает имя события либо из Web SDK, интегрированного на вашем сайте, либо из событий server-to-server (S2S), которые вы отправляете в AppsFlyer.
5. В столбце **«Сопоставлено с событием партнера»** выберите наиболее подходящее предопределенное событие партнера.
6. В столбце **«Для пользователей из»** выберите подходящий вариант:
   * **Только для этого партнера** — чтобы отправлять только события, атрибутированные TikTok Web Ads.
   * **Все медиаисточники, включая органические** — чтобы отправлять все события независимо от источника атрибуции.
7. В столбце **включая** выберите, будут ли события отправляться со значениями дохода. См. <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#данные-для-включения-в-постбэки">Данные для включения в постбэки</Anchor>.

   > 📘 **Примечание**
   >
   > * Если вы настраиваете событие покупки, установите в столбце **включая** значение **Значения и доход**. Выбор любого другого варианта приведет к сбою в отправке постбэка.
   > * В настоящее время для включения дохода можно настроить только событие покупки.

8. [Необязательно] Нажмите значок **Добавить условие**, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события.
9. Нажмите **Сохранить интеграцию**.

> 📘 **Note**
>
> Если на вашем сайте также используется TikTok Pixel, отправляйте один и тот же идентификатор события и в AppsFlyer, и в TikTok, чтобы AppsFlyer мог дедуплицировать события:
>
> * Включите `af_customer_event_id` в полезную нагрузку события, которое вы отправляете в AppsFlyer, внутри `eventValue` для Web SDK или `event_value` для API S2S (server-to-server).
> * Передайте то же значение в соответствующем событии Pixel.
>
> AppsFlyer передает это значение в TikTok как идентификатор события. Затем TikTok использует его, чтобы дедуплицировать серверное событие, полученное от AppsFlyer, с событием Pixel, и AppsFlyer учитывает конверсию только один раз.
>
> Если вы не отправляете `af_customer_event_id`, AppsFlyer автоматически генерирует идентификатор события. Этот идентификатор не будет совпадать с событиями Pixel.
>
> Дополнительную информацию см. в статье <Anchor target="_blank" href="/marketers/ru/docs/integrate-appsflyer-web-sdk">[Бета] Интеграция Web SDK AppsFlyer</Anchor>.

</Accordion>

## Часть 2: Настройте интеграцию с AppsFlyer в TikTok Web Ads

Выполните следующие шаги в TikTok Ads Manager.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. Установите тип, цель и задачи кампании">

В качестве цели кампании вы можете выбрать любое предустановленное внутреннее событие приложения, отправляемое AppsFlyer. Выберите цель кампании, соответствующую целям конверсии вашего сайта, например, стимулирование трафика на сайт или оптимизация конверсий на сайте.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. Укажите целевой URL">

1. В разделе **«Место назначения»** в поле **«URL сайта**» введите URL-адрес вашего веб-сайта — страницы, на которую попадают пользователи после перехода по вашей рекламе.

   **URL сайта** является основным вариантом назначения. Пользователи нажимают на рекламу и попадают прямо на ваш сайт, где совершают события конверсии.
2. **[Альтернативная] Атрибуционная ссылка AF (OneLink):** Если вы хотите перенаправить пользователей в мобильное приложение с резервным вариантом перехода на веб-сайт, вместо этого в качестве URL-адреса назначения можно использовать атрибуционную ссылку AF (OneLink).
3. Кликните **«Создать параметр URL»,** чтобы добавить параметры URL в URL назначения.
4. В разделе **Настраиваемые параметры** нажмите **Добавить параметр**.
5. Сопоставьте параметры AppsFlyer с соответствующими значениями в TikTok:

| Параметр AF | Сопоставленное значение TikTok |
| --- | --- |
| `pid` | `tiktokweb_int` |
| `c` | `__campaign_name__` |
| `af_c_id` | `__campaign_id__` |
| `af_adset` | `__aid_name__` |
| `af_adset_id` | `__aid__` |
| `af_ad` | `__cid_name__` |
| `af_ad_id` | `__cid__` |

   > 📘 **Примечание**
   >
   > Чтобы упростить анализ кампании, указывайте в префиксе или суффиксе тип кампании – веб или мобайл (например, `campaign-name_web`).


   Практические рекомендации по настройке параметров URL и определению источников трафика см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/about-traffic-source-resolution">«Об определении источников трафика</Anchor>».

   Пример итогового URL:

   ```http
   https://www.example.com?pid=tiktokweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__
   ```

   > 📘 **Примечание**
   >
   > TikTok автоматически добавляет`ttclid={{ttclid}}` к целевому URL при клике по объявлению.


</Accordion>

## Просмотреть данные атрибуции веб-сайтов

События веб-конверсии регистрируются под `tiktokweb_int`PID в поле`media_source`. Чтобы просмотреть данные атрибуции, используйте отчеты о сырых данных и примените фильтр,`media_source = tiktokweb_int`чтобы выделить конверсии из веб-приложения TikTok.

Отчетность в дэшборде для рекламных кампаний по веб-приложениям пока недоступна. В одном из будущих релизов планируется внедрить единый интерфейс отчетности, который позволит анализировать эффективность веб-кампаний наряду с другими каналами.

## Измерение стоимости, кликов и показов

Измеряйте стоимость TikTok, клики и показы вместе с данными веб-атрибуции в дэшборде и в отчетах Cost ETL (только для клиентов ROI360).

1. Чтобы получить данные о расходах в TikTok для кампаний в веб-приложении в отчете **«Все затраты**», подключите свою рекламную учетную запись TikTok к сервису интеграции данных о затратах TikTok (`tiktokglobal_int`) через страницу **«Настройки затрат»** или вкладку **«Затраты**». Пошаговые инструкции см. в статье <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data">Set up ROI360 cost API to measure cost data</Anchor>.
2. **Добавьте идентификатор кампании в URL лендинга:** добавьте `af_c_id` вместе с полной иерархией кампании в URL лендинга. Это гарантирует, что стоимость, клики и показы будут сопоставлены с данными веб-атрибуции на самом гранулярном уровне.

## Характеристики и ограничения

| Специфика | Примечания |
| --- | --- |
| Повторное вовлечение | В настоящее время отправка данных о повторном вовлечении через Events API не поддерживается. |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01KQC152Q49R7P96BPMMZGVZWS=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01KQC25PY3PPRTQBJ7K8NV3JWQ=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5 h_01KQC152Q42VT7XKTGCEJV7V7S=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01KQC152Q4A31VJ1JTXWJG6CN0=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F how-to-set-up-tiktok-ads-for-your-website-app=%D0%BA%D0%B0%D0%BA-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-tiktok-web-ads-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%B0%D1%88%D0%B5%D0%B3%D0%BE-%D0%B2%D0%B5%D0%B1-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01KQC152Q4S1VTK7BGWPHHD27W=%D0%BA%D0%B0%D0%BA-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-tiktok-web-ads-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%B0%D1%88%D0%B5%D0%B3%D0%BE-%D0%B2%D0%B5%D0%B1-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F part-1-set-up-tiktok-ads-integration-in-appsflyer=%D1%87%D0%B0%D1%81%D1%82%D1%8C-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-%D1%81-tiktok-web-ads-%D0%B2-appsflyer h_01KQC152Q4J5ZCSFVM8EZ8ZBTZ=%D1%87%D0%B0%D1%81%D1%82%D1%8C-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-%D1%81-tiktok-web-ads-%D0%B2-appsflyer h_01KQC152Q4WDH8W6AVV679JPGS=1-activate-the-tiktok-ads-integration h_01KQC152Q492SBJMJ3J10B1R84=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01KQC152Q4QWF2996MBS0BYCK7=2-set-inapp-event-postbacks h_01KQC152Q4561EWHVKB7A1AWDX=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 part-2-set-up-appsflyer-integration-in-tiktok-ads=%D1%87%D0%B0%D1%81%D1%82%D1%8C-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-%D1%81-appsflyer-%D0%B2-tiktok-web-ads h_01KQC152Q4NKQHF75Y14XCCFNH=%D1%87%D0%B0%D1%81%D1%82%D1%8C-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-%D1%81-appsflyer-%D0%B2-tiktok-web-ads h_01KQC152Q4TMJ0F09Q1PZYV71A=1-set-the-campaign-type-objective-and-goals h_01KQC152Q414XNHHR0Q2B8ZCST=2-set-destination-url h_01KQC152Q4F3WQKETR34WRHACT=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 h_01KQC152Q4BYHRW52BYBJHBGJ4=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-3 view-web-attribution-data=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%BE%D0%B2 h_01KQC152Q45QE5M5BGD4RJNFR9=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%BE%D0%B2 h_01KQD9Z1XY7AB3CDE4FGHTKLM=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D1%82%D0%BE%D0%B8%D0%BC%D0%BE%D1%81%D1%82%D0%B8-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%B8-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 measure-cost-clicks-and-impressions=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D1%82%D0%BE%D0%B8%D0%BC%D0%BE%D1%81%D1%82%D0%B8-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%B8-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KQC152Q45WC7HNZ64T98JJ6Y=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

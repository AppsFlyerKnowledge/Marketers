---
title: Meta Ads — Создание веб-кампаний для веб-приложений
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
  created_at: '2026-04-28T14:18:14Z'
  edited_at: '2026-09-01T00:30:57Z'
  id: 46172666260241
  locale: ru
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ru/articles/46172666260241
---
> **Краткий обзор:** Настройте интеграцию Meta Ads для приложения вашего веб-сайта, чтобы отправлять сигналы о веб-конверсиях в Meta через Conversions API (CAPI), что позволит Meta оптимизировать таргетинг рекламы и оценивать эффективность рекламных кампаний.

<div id="overview" />

## Обзор

AppsFlyer поддерживает интеграцию с Meta Ads (`metaweb_int`) для рекламных кампаний веб-приложений. Благодаря этой интеграции вы можете передавать данные атрибуции и конверсии напрямую Conversions API (CAPI) Meta, которые Meta затем использует для оптимизации таргетинга рекламы, измерения эффективности и формирования пользовательских аудиторий.

Вот как это работает: когда пользователь кликнул по рекламе Meta и попал на ваш сайт, AppsFlyer фиксирует все события конверсии, совершаемые пользователем, такие как покупка или регистрация, и отправляет соответствующий сигнал в Meta через CAPI. Meta использует эти данные для уточнения таргетинга и оценки результатов рекламных кампаний.

<div id="see-also-1" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/web-performance-measurement-overview">Измерение производительности веб-сайта — обзор</Anchor>

> 📘 **Примечание**
>
> Текущая веб-интеграция Meta не поддерживает отправку постбэков о повторном вовлечении в CAPI.

<div id="prerequisites" />

### Необходимые условия

Перед активацией интеграции Meta Ads проверьте, что у вас есть:

* Веб-приложение, настроенное в AppsFlyer. Более подробную информацию см. здесь:
  * <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer#web">Добавление веб-приложения</Anchor>
  * <Anchor target="_blank" href="/marketers/ru/docs/configure-web-performance-measurement-settings">Настройка параметров веб-атрибуции AppsFlyer</Anchor>
* <Anchor target="_blank" href="https://www.facebook.com/business/help/1710077379203657?id=180505742745347">Бизнес-аккаунт в Meta Business Manager</Anchor>.

<div id="set-up-meta-ads-web-campaigns-for-website-apps" />

## Настройте веб-кампании Meta Ads для приложений веб-сайтов

Настройка включает определение интеграции между Meta Ads и AppsFlyer и настройку конфигурации кампании на обеих платформах. Выполните обе части по порядку.

* [Часть 1:](#set-up-meta-ads-integration-in-appsflyer) [Настройте интеграцию Meta Web Ads в AppsFlyer](#set-up-meta-ads-integration-in-appsflyer) (обязательно)
* [Часть 2:](#часть-2-настройка-интеграции-с-appsflyer-в-meta-ads) [Настройте интеграцию AppsFlyer в Meta Ads](#часть-2-настройка-интеграции-с-appsflyer-в-meta-ads) (обязательно)

<div id="part-1-set-up-meta-ads-integration-in-appsflyer" />

## Часть 1: Настройка интеграции Meta Web Ads в AppsFlyer

Начните с активации интеграции Meta Ads и настройки постбэков, которые AppsFlyer отправляет в CAPI.

<div id="step-1-activate-the-meta-ads-integration" />

<Accordion title="Шаг 1. Активируйте интеграцию с Meta Ads">

Чтобы активировать интеграцию Meta Ads:

1. В AppsFlyer в боковом меню перейдите в раздел **Сотрудничество** > **Маркетплейс партнёров**.
2. Найдите и выберите **Meta Ads**.
3. Нажмите **Настроить интеграцию**. Вы будете перенаправлены на страницу настроек **Активные интеграции**.
4. На вкладке **Интеграция** включите переключатель **Активировать партнера**.

   <div id="note-1" />

   > 📘 **Примечание**
   >
   > Переключатель должен оставаться в положении <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активирован</Anchor> всё время, пока вы работаете с партнером.

5. Заполните поле **«Идентификатор Pixel**». Чтобы узнать свой идентификатор пикселя в Meta Ads Manager:
   1. <span class="af-ol-a"></span>В боковом меню <Anchor target="_blank" href="https://www.facebook.com/ads/manager">Ads Manager</Anchor> перейдите в раздел **Все инструменты** > **Events Manager**.

      <div id="note-2" />

      > 📘 **Примечание**
      >
      > Убедитесь, что в выпадающем списке справа вверху выбран нужный бизнес.

   2. В боковом меню **Менеджер событий** выберите **Источники данных**. Вы увидите список пикселей. Если у вас нет пикселя для выбранного бизнеса, вы можете создать его в том же окне.
   3. Скопируйте идентификатор пикселя, указанный под названием пикселя, и вставьте его в поле **«Pixel ID»** в AppsFlyer.
6. Заполните поле **«Токен доступа»**. Чтобы получить токен доступа, следуйте<Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token">этим инструкциям.</Anchor>
7. Включите опцию **Ограничить использование Meta Ads личной информации пользователей (CCPA)**, чтобы обеспечить соблюдение <Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests">законодательных положений по защите данных</Anchor>.

   <div id="note-3" />

   > 📘 **Примечание**
   >
   > Закон CCPA ограничивает использование данных, которые поступают от пользователей Meta Ads, находящихся в штате Калифорния (США).


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="Шаг 2: Настройка постбэков по внутренним событиям приложений">

Вы можете определить, какие события веб-конверсии AppsFlyer будет отправлять в Meta Ads, сопоставив события AppsFlyer с событиями Meta Ads. Эти постбэки можно просмотреть в <Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Менеджере событий Meta</Anchor>. Meta использует данные о событиях для оптимизации рекламных кампаний и составления отчетов.

Настройка постбэков по внутренним событиям приложений

1. Активируйте **Постбэки событий внутри приложения**.
2. При необходимости настройте окно постбэка событий в приложении. Дополнительные сведения см. в разделе\n \n <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">Настройка окна постбэка событий в приложении</Anchor>.
3. Нажмите**Добавить событие**, чтобы добавить событие в список.
4. В столбце **Событие AppsFlyer** выберите название события из выпадающего списка. AppsFlyer получает имя события из Web SDK, интегрированного на вашем сайте, или из событий server-to-server (S2S), которые вы отправляете в AppsFlyer.
5. В столбце **Сопоставлено с событием партнера** выберите\n из выпадающего списка наиболее подходящее предопределенное событие партнера\n или выберите **CUSTOM**.
6. В столбце **«Для пользователей из»** выберите вариант отправки для события:
   * **Только этот партнер**: отправляйте постбэки только\n в том случае, если это событие атрибутировано Meta Ads.
   * **Все медиаисточники, включая органические**:\n отправляйте постбэки для событий, атрибутированных любому партнеру, а также\n для органических событий.
7. В столбце **«Включая»** выберите, будут ли события отправляться со значениями дохода. См. <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#данные-для-включения-в-постбэки">«Данные для включения в постбэки»</Anchor>.

   <div id="note-5" />

   <div id="note-4" />

   <div id="important" />

   > 🚧 **Важно!**
   >
   > Если вы настраиваете событие покупки, установите в столбце **«Включая» «Значения и доход»**. Выбор любого другого варианта приведет к сбою отправки постбэка.

8. [Необязательно] Нажмите значок **Добавить условие**, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события.
9. Нажмите **Сохранить интеграцию**.

> 📘 **Note**
>
> Если на вашем сайте также используется Meta Pixel, отправляйте один и тот же идентификатор события и в AppsFlyer, и в Meta, чтобы AppsFlyer мог дедуплицировать события:
>
> * Включите `af_customer_event_id` в полезную нагрузку события, которую вы отправляете в AppsFlyer, — в `eventValue` для Web SDK или `event_value` для S2S (server-to-server) API.
> * Передавайте то же значение в соответствующем событии Pixel.
>
> AppsFlyer передает это значение в Meta как идентификатор события. Затем Meta использует его, чтобы дедуплицировать серверное событие, полученное от AppsFlyer, по событию Pixel, чтобы AppsFlyer засчитал конверсию один раз.
>
> Если вы не отправляете `af_customer_event_id`, AppsFlyer автоматически генерирует идентификатор события. Этот идентификатор не будет совпадать с вашими событиями Pixel.
>
> Дополнительные сведения см. в статье <Anchor target="_blank" href="/marketers/ru/docs/integrate-appsflyer-web-sdk">[Бета] Интеграция Web SDK AppsFlyer</Anchor>.

</Accordion>

<div id="part-2-set-up-appsflyer-integration-in-meta-ads" />

## Часть 2: Настройка интеграции с AppsFlyer в Meta Ads

Выполните следующие шаги в Meta Ads Manager.

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="Шаг 1. Установите тип, цель и задачи кампании">

1. Войдите в Meta Ads и создайте кампанию.
2. В поле **Цель кампании** выберите один из следующих вариантов:
   * **Продажи**: Позволяет Meta оптимизировать конкретное событие (ваш основной KPI).
   * **Трафик**: Позволяет Meta оптимизировать клики по рекламе. Используйте этот параметр только в том случае, если у вас нет других KPI или если количество событий по другим KPI слишком мало.
3. [Необязательно] Чтобы добавить пользовательскую цель, выполните следующие действия:

   1. В Meta Ads выберите пользовательское событие, которое вы хотите установить в качестве цели кампании, и отметьте его как действие конверсии.
   2. В AppsFlyer на странице **Интеграция Meta Web** в разделе **Постбэки по событиям в приложении** сопоставьте событие AppsFlyer с пользовательским партнерским событием в столбце, **Сопоставлено с партнерским событием** и назовите его тем же именем, что и действие конверсии в Meta Ads.

   <div id="note-6" />

   > 📘 **Примечание**
   >
   > Дополнительную информацию о целях кампании Meta см. <Anchor target="_blank" href="https://www.facebook.com/business/help/175683976191028">документацию Meta</Anchor>.

4. В поле **Место конверсии** выберите **Веб-сайт**.
5. В поле **Пиксель** введите тот же идентификатор пикселя, который вы ввели для `metaweb_int` на Маркетплейсе партнеров AppsFlyer. Более подробная информация о пикселе Meta приведена в <Anchor target="_blank" href="https://www.facebook.com/business/help/742478679120153">документации Meta</Anchor> (необходимо войти в систему).
6. Нажмите **Далее**.

</Accordion>

<div id="step-2-set-destination-url" />

<Accordion title="Шаг 2: Укажите целевой URL">

1. В разделе  **«Назначение»** в поле <strong>«URL сайта»</strong>введите URL, который будет целевым адресом вашего объявления. Выберите одну из следующих опций:

   * **URL сайта**: Используйте URL вашего сайта, если хотите, чтобы пользователи попадали прямо на ваш сайт и совершали там события конверсии, такие как покупка или регистрация.
   * **Ссылка для атрибуции AF (OneLink)**: Используйте атрибуционную ссылку AF, если хотите перенаправлять пользователей в мобильное приложение с резервным переходом на сайт, если приложение не установлено. Это полезно, если ваша кампания ориентирована как на пользователей приложения, так и на пользователей веб-версии. Дополнительную информацию см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">«Ссылки и сцеарии OneLink</Anchor>».

   <div id="important-1" />

   > 🚧 **Важно!**
   >
   > В некоторых случаях использование атрибуционных ссылок AF может приводить к ошибкам. Если это произойдёт, обратитесь за решением к своему представителю Meta или используйте URL вашего веб-сайта в качестве целевого URL.

2. Кликните **«Создать параметр URL»,** чтобы добавить параметры URL в целевой URL.
3. В разделе **Настраиваемые параметры** нажмите **Добавить параметр**.
4. Сопоставьте параметры AppsFlyer с соответствующими значениями Meta, как показано в таблице ниже:

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

Пример итогового URL:

```http
https://www.example.com?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}
```

<div id="note-7" />

> 📘 **Примечание**
>
> Meta автоматически добавляет `fbclid={{fbclid}}` к целевому URL при клике по объявлению.

<div id="tip" />

> 👍 **Совет**
>
> Для упрощения анализа кампании, указывайте в префиксе или суффиксе тип кампании – веб или мобайл (например, `campaign-name_web`).

<div id="see-also" />

> 📄 **См. также**
>
> * Практические рекомендации по формированию URL рекламного объявления с указанием всех необходимых параметров см. в <Anchor target="_blank" href="/marketers/ru/docs/about-traffic-source-resolution">разде</Anchor>ле <Anchor target="_blank" href="/marketers/ru/docs/about-traffic-source-resolution">«Об определении источника трафика</Anchor>».

</Accordion>

<div id="step-3-select-tracked-events" />

<Accordion title="Шаг 3: Выбор отслеживаемых событий">

В разделе **«Отслеживание»** используйте события конверсии, которые продвигаются вашей рекламой. Настройка событий осуществляется через <Anchor target="_blank" href="https://www.facebook.com/business/help/898185560232180?id=1205376682832142">«Менеджер событий</Anchor>».

<div id="important-2" />

> 🚧 **Важно!**
>
> Не выбирайте **«События приложения**». В этом случае Meta засчитает эти конверсии через SRN API, что может привести к расхождениям в отчётности и неправильной оптимизации.

</Accordion>

<div id="view-web-attribution-data" />

## Просмотреть данные веб-атрибуции

Вот чего ожидать при просмотре данных атрибуции после настройки:

* В **экспортах сырых данных и ответах API** содержится значение Meta Web`media_source` в поле для веб-активности Meta.
* Чтобы проверить данные настройки веб-кампании, обратите внимание на`original_url`поле, в котором указан`facebook_int` PID, использованный при создании веб-кампании.

> 📘 **Примечание**
>
> Отчетность в дэшборде для рекламных кампаний по веб-приложениям пока недоступна. Объединённый отчёт, позволяющий анализировать эффективность веб-кампаний наряду с другими каналами, запланирован к выпуску в одном из будущих релизов.

<div id="measure-web-attribution-data-with-web-cost" />

## Измеряйте данные веб-атрибуции вместе с данными о затратах на веб.

Чтобы получить полную картину эффективности данных по веб-атрибуции и данных о веб-затратах из Meta Ads на дэшборде и в <Anchor target="_blank" href="/marketers/ru/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">отчетах стоимости ETL</Anchor>, убедитесь, что у вас установлен <Anchor target="_blank" href="/marketers/ru/docs/roi360-onboarding-guide#о-roi360">пакет ROI360</Anchor>, и выполните следующие настройки:

1. Подключите стоимость к приложению вашего сайта через `facebook_int` (а не через `metaweb_int`) на вкладке **«Стоимость»** или на странице **«Настройки стоимости**». Дополнительные сведения о подключении к данным о стоимости см. в статье <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#включение-api-затрат">«Настройка API ROI360 для измерения данных о стоимости</Anchor>».
2. Включите идентификатор кампании (`af_c_id`) в URL-адрес целевой страницы. Убедитесь, что URL содержит полную иерархию кампании, чтобы отображались данные о затратах, кликах и показах, сопоставленные с веб-атрибуцией на максимально детализированном уровне.

<div id="traits-and-limitations" />

## Характеристики и ограничения

| Специфика | Примечания |
| --- | --- |
| Клики и показы | Для просмотра данных о кликах и показах в рамках веб-кампаний требуется <Anchor target="_blank" href="/marketers/ru/docs/roi360-onboarding-guide">подписка на ROI360</Anchor>. |

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01KQA78RE9FRENQAK31Q641C0N=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01KQC27K5KWP3A6HMM2W7N3MVB=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5 h_01KQA78RE9F82ZBVF4YZHZTEEX=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01KQA78RE93B09A9YH2FRB3XRR=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F set-up-meta-ads-web-campaigns=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-meta-ads-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%BE%D0%B2 h_01KQA78RE9J681CJ8DQNWJC37H=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-meta-ads-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%BE%D0%B2 part-1-set-up-meta-ads-integration-in-appsflyer=%D1%87%D0%B0%D1%81%D1%82%D1%8C-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-meta-web-ads-%D0%B2-appsflyer h_01KQA78RE93JYCV2P0DDZC0A4B=%D1%87%D0%B0%D1%81%D1%82%D1%8C-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-meta-web-ads-%D0%B2-appsflyer h_01KQA78RE94B1JSVJFWR1V9QE5=step-1-activate-the-meta-ads-integration h_01KQA78REA5VN1229F2J3QH794=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01KQA78REANHAQ88N4MXWM832D=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 h_01KQA78REA08SNB0BKCJDJZ2R0=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-3 h_01KQA78REACR7QTMQWJMV6VJSF=step-2-set-inapp-event-postbacks h_01KQA78REA1EB5ZHX4HKJSW7ZD=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE part-2-set-up-appsflyer-integration-in-meta-ads=%D1%87%D0%B0%D1%81%D1%82%D1%8C-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-appsflyer-%D0%B2-meta-ads h_01KQA78REAEZQPDSKZ0GRNKEJJ=%D1%87%D0%B0%D1%81%D1%82%D1%8C-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-appsflyer-%D0%B2-meta-ads h_01KQA78REASX8JX1H37075WT82=step-1-set-the-campaign-type-objective-and-goals h_01KQA78REA5JZ44C4BE77JCHG8=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-4 h_01KQA78REAKBGQRC713FZ3J02P=step-2-set-destination-url h_01KQA78REAXZ1BFGC5BR75ZB5X=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE-1 h_01KQA78REARWGQDCJ4KN3FM120=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-5 h_01KQA78REA7MZSG5JZ1XX2C65P=%D1%81%D0%BE%D0%B2%D0%B5%D1%82 h_01KQA78REA3ZW7W9M3VFSQASB6=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5-1 h_01KQA78REASTZH19CM58M5Z43R=step-3-select-tracked-events h_01KQA78REBHCR1AHA254BTFZC6=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE-2 view-web-attribution-data=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01KQA78REBK1PWXNA1PM9118TA=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01KQA78REBAW2SM5DRD68DP8W1=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-6 measure-web-attribution-data-with-web-cost=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D1%8F%D0%B9%D1%82%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B5-%D1%81-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-%D0%BE-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D0%B0%D1%85-%D0%BD%D0%B0-%D0%B2%D0%B5%D0%B1 h_01KNM00RR9TF8JRTJXWN23MF1S=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D1%8F%D0%B9%D1%82%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%B5-%D1%81-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-%D0%BE-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D0%B0%D1%85-%D0%BD%D0%B0-%D0%B2%D0%B5%D0%B1 traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KQAE3JKMQ6ZEATDAEXBC4PT6=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

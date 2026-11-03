---
title: Настройка веб-интеграции TikTok for Business для приложений ПК и консолей
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
  created_at: '2025-10-31T13:58:16Z'
  edited_at: '2026-09-17T00:30:22Z'
  id: 40500157955601
  locale: ru
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/ru/articles/40500157955601
---
> **Краткий обзор:** Узнайте, как интегрировать TikTok Web для приложений для ПК и консолей с AppsFlyer и настроить кампании в TikTok Web.

> ❗️ **Предупреждение**
>
> Эта интеграция доступна только для приложений для ПК и консолей, таких как Steam, Epic или нативный ПК. Для мобильных приложений см. страницу <Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup">Настройка интеграции рекламы TikTok</Anchor> .

## Информация о компании

Эта статья содержит информацию и шаги по настройке и использованию TikTok Web для приложений для ПК и консолей с AppsFlyer.

### Необходимое условие

Прежде чем активировать интеграцию TikTok Web, убедитесь, что у вас есть бизнес-аккаунт в TikTok Ads Manager.

## Активация партнера в AppsFlyer

**Чтобы активировать партнерскую интеграцию:**

1. В AppsFlyer в боковом меню откройте **Collaborate** > **Partner Integrations > Marketplace** вкладку.
2. Найдите **TikTok Web** (`tiktokweb_int`).
3. Нажмите **Integrate**. Вы будете перенаправлены на страницу настройки.
4. На вкладке **Интеграция** включите **Активировать партнера**. Переключатель должен оставаться в положении <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активирован</Anchor> всё время, пока вы работаете с партнером.
5. Завершите настройку, используя соответствующие вкладки, как описано в следующем разделе.

## Настройка TikTok Web в AppsFlyer

В этой части настройки вы также можете настроить постбэки в TikTok Web через TikTok Events API. Интеграция TikTok Web (tiktokweb\_int) использует инструмент Events API, предоставляемый TikTok ads для рекламодателей, чтобы отправлять данные из своих **приложений для ПК и консолей** напрямую на серверы TikTok. Эти данные могут включать в себя действия пользователей, например покупки, регистрации и другие виды конверсий, выполненные на немобильных платформах (веб-сайты или приложения). Полученные данные используются TikTok ads для оптимизации таргетинга, оценки эффективности рекламы и создания пользовательских аудиторий для ретаргетинга.

Интеграция с TikTok Web поддерживает только отправку постбэков для установок и событий в приложении.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке **Интеграция** есть несколько разделов, описанных ниже.

#### Активация партнера

Чтобы настроить интеграцию, необходимо сначала включить переключатель **Активировать партнёра** .

#### Общие настройки

* **Идентификатор пикселя:** Введите идентификатор пикселя. Вы можете сгенерировать его или получить в TikTok Ads Manager, следуя инструкциям, приведенным [ЗДЕСЬ](https://business-api.tiktok.com/portal/docs?id=1771100865818625).
* **Токен доступа:** Введите токен доступа. Чтобы сгенерировать или получить его, следуйте [этим инструкциям](https://business-api.tiktok.com/portal/docs?id=1771100865818625)
* **Ограничить использование TikTok Ads’ личной информации пользователей (CCPA):** Включите этот переключатель, чтобы обеспечить соблюдение <Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests">законов о защите данных</Anchor>.

  > 📘 **Примечание:**
  >
  > Соблюдение требований CCPA ограничивает объем данных, поступающих от пользователей TikTok Ads, проживающих в Калифорнии или других чувствительных штатах США.


#### Активация атрибуции по просмотрам

AppsFlyer поддерживает атрибуцию по просмотрам для кампаний TikTok Web с использованием вероятностного моделирования (PMOD) и [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) или [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page. Это позволяет AppsFlyer атрибутировать установки приложений, которые происходят после того, как пользователи посмотрели рекламу, а затем установили приложение, даже на разных платформах, без необходимости прямого клика.

Когда пользователь нажимает на рекламу TikTok Web и попадает на [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) или [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page, AppsFlyer может атрибутировать последующую установку приложения. Если доступно, параметр `ttclid` будет включён в постбэк к TikTok для повышения точности атрибуции.

Активация атрибуции по просмотрам:

1. В AppsFlyer в боковом меню откройте **Collaborate** > **Partner Integrations** > **Active Integrations** > **TikTok web ads**.
2. На вкладке **Интеграция** прокрутите до раздела **Атрибуция установки**.
3. Включите **Атрибуцию установок по просмотрам**.
4. **[необязательно]** Включите **Равный приоритет кроссплатформенной атрибуции** и задайте для него окно ретроспективы. Более подробно см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Включите равный приоритет для кроссплатформенных показов</Anchor>.
5. Откройте вкладку **Ссылка атрибуции**.
6. Прокрутите к разделу **Атрибуция по просмотрам** и установите **окно атрибуции по просмотрам** (до 24 часов).
7. Нажмите **Сохранить интеграцию** для применения ваших настроек.

#### Постбэки по умолчанию

Постбэки по установкам автоматически отправляются только в TikTok Web.

#### https://support.appsflyer.com/hc/article_attachments/360001712765

Настройте сопоставление постбэков по событиям в приложении, отправляемых в TikTok Web. Эти события можно просмотреть в TikTok Ads Manager

1. Активируйте **Постбэки по внутренним событиям приложения**.
2. Нажмите **Добавить событие**. В таблице ниже описаны поля, которые необходимо заполнить:

| **Название параметра** | **Description(Описание)** |
| --- | --- |
| AppsFlyer event (Событие AppsFlyer) | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<ul><li>Нажмите Add item (Добавить событие), введите имя события и нажмите.</li></ul> |
| сопоставлено с партнерским событием | Уникальное имя или идентификатор каждого события, определённого на стороне партнёра.<ul><li>Выберите в раскрывающемся списке наиболее подходящее предопределенное событие партнера</li></ul> |
| для пользователей от | Только этот партнер: постбэки по внутренним событиям приложения отправляются только в том случае, когда событие атрибутируется этому партнеру, то есть когда пользователь, выполнивший событие, пришел от этого партнера. |
| Включая | Значения и доход: в постбэке отправляются все параметры события, включая значение дохода (если оно есть в событии). |

3. [Необязательно] Нажмите значок **Добавить условие** , чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события.
4. Если требуется, установите **окно постбэков по внутренним событиям** (подробнее о<Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#окно-постбэков-по-внутренним-событиям">настройке окна постбэков по внутренним событиям</Anchor>).
5. Нажмите **Сохранить интеграцию**.
6. [Необязательно] После сохранения интеграции, оставаясь на странице конфигурации, вы можете интегрировать с этим партнером другие свои приложения:
   1. В левом верхнем углу под именем партнера нажмите на название приложения, чтобы открыть список приложений.
   2. Выберите другое приложение из раскрывающегося списка.
   3. Повторите шаги по интеграции для выбранного приложения.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Генерация ссылки атрибуции в пользовательском интерфейсе AppsFlyer в настоящее время недоступна. Однако вы можете либо использовать кроссплатформенную целевую страницу с SmartScript, либо создать прямую ссылку атрибуции для своего приложения (см. таблицу ниже).

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
        **Рекомендация:** для случаев, когда ваша кампания продвигает приложение, которое также доступно на нескольких платформах, например Epic и Steam.  
        <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Узнайте о кроссплатформенных целевых страницах</Anchor>  
        <Anchor target="_blank" href="/marketers/ru/docs/cross-platform-landing-pages-with-smart-script">Узнайте, как настроить кроссплатформенную целевую страницу</Anchor>

        * Убедитесь, что все соответствующие параметры URL (которые впоследствии будут считаны Smart Script) добавлены к URL объявления.
        * Убедитесь, что скрипт берет TTCLID из входящего URL и добавляет его в сгенерированную ссылку. То есть сопоставьте исходящий TTCLID URL-параметр ttclid со входящим URL-параметром ttclid. **Важно!** Чтобы данные отображались в отчетах о сырых данных AppsFlyer, входящий параметр ttclid также должен быть сопоставлен с одним из исходящих параметров  `af_sub[1-5]`.
        * Необязательно: используйте динамические макросы URL TikTok вместо того, чтобы вводить значения вручную. [Узнать больше](https://ads.tiktok.com/help/article/track-offsite-web-events-with-utm-parameters)
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
        Если вы не используете кроссплатформенную целевую страницу, потому что у вас есть только одно приложение на одной платформе, вы можете создать прямые ссылки атрибуции для размещения в объявлениях.   
        <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создать прямые ссылки атрибуции</Anchor>

        * Убедитесь, что в ссылке указаны обязательные параметры:
          * `media_source (медиа-источник)`
          * `af_campaign_id`
          * `af_r`
        * Используйте следующие рекомендуемые макросы для параметра `af_os_version`:
          * Клик: `__OS_VERSION__`
          * Показ: `__TPL_OS_VERSION__`

        Шаблон для ссылки на рекламное объявление TikTok Web:

        ```http
        https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r={encoded landing page and URL params}&af_os_version=__TPL_OS_VERSION__
        ```

        Пример ссылки рекламного объявления TikTok Web, ведущей в Steam:

        ```http
        https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello&af_os_version=__OS_VERSION__
        ```

        **Примечание**: шаблон включает некоторые динамические параметры URL-адреса, поддерживаемые TikTok. При желании вы можете заменить их реальными значениями вручную.
      </td>
      <td>
        Маркетолог
      </td>
    </tr>
  </tbody>
</Table>

> 👍 **Совет.**
>
> Чтобы упростить анализ кампании, указывайте тип кампании -- веб или мобайл -- в префиксе или суффиксе названия кампании (например, название-кампании\_web).

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Стоимость недоступна для TikTok Web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы недоступен для TikTok Web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

В настоящее время TikTok Web не предоставляются разрешения.

</Accordion>

## Настройка кампаний в TikTok Web для приложений для ПК и консолей

Когда вы создаете новую кампанию:

* Выберите **Website** в качестве места конверсии.
* Когда вы будете называть свой пиксель конверсии TikTok, введите тот же идентификатор ID пикселя, который вы ввели для `tiktokweb_int` в *AppsFlyer Partner Marketplace*.
* Когда вы вводите URL-адрес сайта в качестве пункта назначения объявления, он должен быть одним из следующих:
  * Целевая страница на сайте (рекомендуется, если приложение работает на нескольких платформах)
  * URL-адрес магазина (рекомендуется, если ваше приложение находится в одном магазине приложений на одной платформе)

## Посмотреть данные атрибуции web-to-app

Хотя события конверсии, происходящие в вебе, отправляются в TikTok с исходным PID `tiktokweb_int`, на дэшборде AppsFlyer и в отчетах о сырых данных они отображаются под PID `tiktokglobal_int`. Это относится как к основным событиям конверсии, так и к событиям-ассистам конверсии.

Этот унифицированный вид отчетов позволяет анализировать эффективность кампаний для веба и приложений в одном месте, включая подробную отчетность о затратах для веба и мобильных устройств.

### Посмотреть на дэшборде

Вся атрибуция TikTok Web-to-app отображается как `tiktokglobal_int` в дэшбордах «Обзор» и «Активность». Это обеспечивает единое, консолидированное представление результатов кампаний на разных платформах. Используйте стандартные фильтры и разбивки, чтобы сравнить трафик в приложении и на вебе в данных TikTok Ads.

### Просмотр в отчётах о сырых данных и через API

Экспорты сырых данных и ответы API включают PID `tiktokglobal_int` в поле `media_source` для веб-активности TikTok. Чтобы проверить детали настройки веб-кампании, обратитесь к полю `original_url`, в котором показан PID `tiktokweb_int`, использованный при создании веб-кампании.

## Спецификации и ограничения

| Специфика | Description(Описание) |
| --- | --- |
| Клики и показы (Временное ограничение) | Данные о кликах и показах для кампаний, нацеленных на приложения для ПК & консолей, временно недоступны в TikTok SRN. |

<div data-zendesk-anchors="h_01K8X90869H29Q9N873FAT8BM4=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01K8X90869QTX2RG0KHHM8EHAT=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 prerequisite=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 h_01K8X9086AJ6B9BKNF0EZQASCJ=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 activating-partner-in-appsflyer=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-%D0%B2-appsflyer h_01K8X9086ADTE56DR3MK8MXAFR=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-%D0%B2-appsflyer setting-up-tiktok-web-in-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-tiktok-web-%D0%B2-appsflyer h_01K8X9086AMHZR7GADTH8N07DZ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-tiktok-web-%D0%B2-appsflyer h_01K8X9086AHN8761VPM4QA7E6S=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01K8XAAM5SH1XXNX0DNGGS5NHT=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01K8XAATC3M5NW722QD93DRN94=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01K8X9086A2FFDCRE2JHXQHGET=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 enable-viewthrough-attribution=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01K8XAB2SK68WTGYZY7EGHR4SZ=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01K8XABK08NCFQSRN41ASKQ7SY=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-postbacks=httpssupportappsflyercomhcarticle_attachments360001712765 h_01K8XAC3NAYY8S012K2W60TKBJ=httpssupportappsflyercomhcarticle_attachments360001712765 h_01K8X9086A001XKD94G50XY708=attribution-link-tab h_01K88N0TDSFDX5J22YWZPF2J1N=%D1%81%D0%BE%D0%B2%D0%B5%D1%82 h_01K8X9086AFH7J75J9K1QRV1DR=cost-tab h_01K8X9086ACM5WBH6GW243A0PZ=ad-revenue-tab h_01K8X9086AEHV42XZZKA0ATBH2=permissions-tab setting-up-campaigns-in-tiktok-web-for-pc-and-console-apps=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-tiktok-web-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BA-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B5%D0%B9 h_01K8X9086AARVTEDRMQW32BABF=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%B2-tiktok-web-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BA-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D0%B5%D0%B9 TikTok-view=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-webtoapp-attribution-data-from-november-2-2025=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-web-to-app view-in-the-dashboard=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 h_01K88J8JFNMHCVZ0C34E3D7AST=%D0%BF%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B5%D1%82%D1%8C-%D0%BD%D0%B0-%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4%D0%B5 view-in-raw-data-and-api-reports=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-api h_01K88J8JFN8W2572N92466YFZQ=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D0%B2-%D0%BE%D1%82%D1%87%D1%91%D1%82%D0%B0%D1%85-%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B8-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-api traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KB58BEK7MDZGT7G7RQ9VK9MZ=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

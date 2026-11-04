---
title: Pinterest — создание интеграции приложения для сайта
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
  created_at: '2026-06-14T13:07:07Z'
  edited_at: '2026-09-01T00:31:26Z'
  id: 47721580892433
  locale: ru
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/ru/articles/47721580892433
---
**Краткий обзор:** Настройте интеграцию Pinterest для приложения вашего сайта, чтобы отправлять в Pinterest события веб-конверсий для оптимизации кампаний и отчетности.

<div id="set-up-integration" />

## **Настроить интеграцию**

**Необходимые условия:**

* Аккаунт в Pinterest
* Веб-приложение, настроенное в AppsFlyer. <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer#web">Узнать больше</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/integrate-appsflyer-web-sdk">Web SDK</Anchor> AppsFlyer или <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-s2s-api-for-web-performance-measurement">Server-to-Server (S2S) API</Anchor> для веб-атрибуции

**Чтобы активировать или изменить интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Marketplace** .  
   **Чтобы отредактировать:** В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Активные интеграции** .
2. Выберите приложение вашего сайта в раскрывающемся меню выше.
3. Найдите Pinterest и кликните **Integrate**.
4. При **первом посещении** вам необходимо ***Активировать партнера***, чтобы включить настройку параметров вкладки интеграции.**Примечание:** переключатель должен оставаться <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">(activated)</Anchor> включенным все время, пока вы работаете с Pinterest.
5. Завершите настройку на вкладке **интеграция**, как описано ниже.

<div id="integration-tab" />

## **Вкладка «Интеграция»**

<div id="activate-partner" />

### **Активация партнера**

При **первом посещении** включите переключатель **Activate Partner**, чтобы включить настройку параметров вкладки интеграции. Переключатель должен оставаться включенным все время, пока вы работаете с Pinterest.

Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнера</Anchor>.

<div id="in-app-event-settings" />

### **Настройки внутренних событий приложения**

Чтобы отправлять в Pinterest постбэки по событиям в приложении, укажите следующие учетные данные Pinterest. Эти учетные данные включаются в постбэки событий, отправляемые в Pinterest.

* **Ad Account ID** — уникальный идентификатор ID вашего рекламного аккаунта Pinterest.
* **Access Token** - Токен доступа, созданный в Pinterest.

Значения Ad Account ID и Access Token можно найти в интерфейсе Pinterest Ads Manager (см. <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/tracking-conversions/#getting-your-access-token-and-ad-account-id">документацию Pinterest</Anchor>). Обратитесь в службу поддержки Pinterest, если вам нужна помощь.

**Чтобы настроить учетные данные Pinterest:**

1. В AppsFlyer на странице Pinterest **активный** интеграции > вкладка **интеграция** прокрутите до раздела **In-app event settings**.
2. Введите значения Ad Account ID и Access Token в соответствующие поля.

<div id="in-app-event-postbacks" />

### https://files.readme.io/8d5c3b6d1dd7542860d58b2cff8581a8eb72880764b730a4c87b8161eb04edab-360001712765.png

В этом разделе вы сопоставляете веб-события AppsFlyer с событиями Pinterest через постбэки.

1. В настройках интеграции Pinterest прокрутите страницу до раздела **Постбэки событий в приложении**.
2. Включите **постбэки событий в приложении**.
3. https://files.readme.io/8d5c3b6d1dd7542860d58b2cff8581a8eb72880764b730a4c87b8161eb04edab-360001712765.png
4. Выберите настройки постбэков и сопоставления для событий.

| **Название параметра** | **Description(Описание)** |
| --- | --- |
| **Имя события в SDK** | Название веб-события, полученное AppsFlyer либо из Web SDK, интегрированного на вашем сайте, либо из событий server-to-server.<br /><br />**Примечание:** если в списке нет нужного события, убедитесь, что оно активировано, и проверьте снова. |
| **Идентификатор события партнера** | Событие Pinterest для сопоставления, выбранное из предопределенного списка событий Pinterest. Названия событий Pinterest см. в <Anchor target="_blank" href="https://developers.pinterest.com/docs/api-features/track-conversion-events/#understand-conversion-events">документации Pinterest</Anchor>. |
| **Пользователям из** | **Только этот партнер:** события, поступающие только от пользователей, атрибутированных Pinterest.<br /><br />**Все медиаисточники, включая органические:** вся ваша пользовательская база доступна для отправки в отчетности партнеру. |
| **преимущества** | Выберите, отправлять ли партнеру в постбэке доход от события или значения параметров. AppsFlyer может отправлять все параметры расширенного веб-события, кроме параметра дохода (содержится в **af\_revenue**), или все параметры, включая значение дохода (если оно есть). |

> 📘 **Note**
>
> Если вы также используете Pinterest Tag на своем сайте, отправляйте один и тот же идентификатор события и в AppsFlyer, и в Pinterest, чтобы AppsFlyer мог дедуплицировать события:
>
> * Добавьте af\_customer\_event\_id в полезную нагрузку события, которую вы отправляете в AppsFlyer, внутри eventValue для Web SDK или event\_value для S2S (server-to-server) API.
> * Отправьте то же значение в соответствующем событии тега.
>
> AppsFlyer передает это значение в Pinterest как идентификатор события. Затем Pinterest использует его, чтобы дедуплицировать серверное событие, полученное от AppsFlyer, с событием Tag, чтобы AppsFlyer засчитывал конверсию один раз.
>
> Если вы не отправляете af\_customer\_event\_id, AppsFlyer автоматически генерирует идентификатор события. Этот идентификатор не будет совпадать с событиями тега.
>
> Дополнительную информацию см. в разделе «Интеграция AppsFlyer Web SDK».

5. Нажмите **Добавить событие**, чтобы добавить событие в список.

<div data-zendesk-anchors="set-up-pinterest=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E h_01KV339A5ZGK96JNCNR78PDMNH=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E integration-tab=%D0%B2%D0%BA%D0%BB%D0%B0%D0%B4%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F h_01KV339A67N4436STPW1VJR585=%D0%B2%D0%BA%D0%BB%D0%B0%D0%B4%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01KV339A67H0DSSJ3P84PXGQ2F=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 inapp-event-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01KV339A68YZBZZ73T8XTBE6BR=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F inapp-event-postbacks=httpssupportappsflyercomhcarticle_attachments360001712765 h_01KV339A6BN0CWYX7GCJ19RN0J=httpssupportappsflyercomhcarticle_attachments360001712765" />

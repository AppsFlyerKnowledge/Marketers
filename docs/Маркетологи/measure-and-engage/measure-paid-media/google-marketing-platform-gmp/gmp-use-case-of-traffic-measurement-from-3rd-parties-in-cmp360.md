---
title: >-
  Пример использования  Google Платформы для маркетинга (GMP) для измерения
  трафика от третьих сторон в Менеджере кампаний 360 (CM360)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-03-03T12:42:31Z'
  edited_at: '2026-10-08T00:14:40Z'
  id: 360018228758
  locale: ru
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/ru/articles/360018228758
---
> **Краткий обзор**: Закупайте трафик у сторонних медиа-источников в CM360 и измеряйте конверсии мобильных приложений из этого источника как в AppsFlyer (атрибуция стороннему медиа-источнику), так и в CM360.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

## Измерение CM360 со сторонними медиа-источниками, не относящимися к Дисплею и Видео 360 (DV360)

Google Платформа для маркетинга (GMP) объединяет вашу рекламу и аналитику, чтобы помочь вам выявить качественные закономерности, связанные с клиентами, обнаружить более глубокие инсайты и повысить эффективность маркетинговых мероприятий.

В контексте AppsFlyer стандартная интеграция SRN DV360 (dv360\_int) с GMP позволяет легко атрибутировать кампании в DV360, **управление которыми осуществляется в CM360**, без необходимости в атрибуционных ссылках. AppsFlyer атрибутирует установки и повторные взаимодействия к DV360 через заявки SRN DV360 посредством интеграции.

> 📘 **Примечание:**
>
> * AppsFlyer атрибутирует кампании DV360, управляемые в CM360, через стандартную интеграцию с SRN DV360, без необходимости в атрибуционных ссылках. Установки и повторные взаимодействия атрибутируются к DV360 через заявки SRN DV360 посредством интеграции. Если вы проводите кампании в DV360 с управлением через CM360, см. <Anchor target="_blank" href="/marketers/ru/docs/google-marketing-platform-display-video-360-dv360-integration">руководство по интеграции DV360</Anchor>.
> * Если сторонний медиа-источник является SRN, AppsFlyer рекомендует не использовать интеграцию, описанную в этой статье, чтобы избежать конфликтов, когда конверсии от одного и того же партнёра сообщаются через две разные интеграции. Например, если в AppsFlyer активирована <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup">интеграция с SRN Meta Ads</Anchor>, но также используется CM360 для отчётности по трафику Meta Ads (facebook\_int) с использованием метода, описанного в этой статье, конверсии могут быть зафиксированы как в Meta Ads, так и в CM360, при этом CM360 фиксирует некоторые конверсии, которые могли бы быть заявлены основной интеграцией Meta Ads.

### Измерение трафика третьих сторон, проходящего через CM360

Для измерения сторонних медиа-источников, управляемых через CM360, как в AppsFlyer, так и в CM360, рекомендуется выполнить следующие действия:

#### 1. Интеграция стороннего медиа-источника и GMP с AppsFlyer

Как обеспечить атрибуцию от AppsFlyer:

* Проверьте, чтобы сторонний медиа-источник был интегрирован и активирован, так как он, а не CM360 получает атрибуцию. Активация GMP (dv360\_int) необходима только для обеспечения отправки данных обратно в CM360.
* Если сторонний медиа-источник не интегрирован с AppsFlyer, его следует рассматривать как пользовательский или собственный медиа-источник. В этом случае реализуйте атрибуционную ссылку с любым значением PID (медиа-источника).

> 📘 **Примечание:**
>
> Атрибуция агентства: AppsFlyer требуется название агентства для атрибуции установок. Включите его, используя параметр `af_prt` в ссылке атрибуции или через реферер в URL.

#### 2. Создание необходимых ссылок атрибуции

1. <Anchor target="_blank" href="https://support.google.com/campaignmanager/answer/3040965?hl=en&ref_topic=2826011">Создайте «отслеживающее объявление» в CM360</Anchor>
2. Создайте ссылку атрибуции в AppsFlyer:
   * Ссылка атрибуции должна содержать название фактического стороннего медиа-источника, который будет указан в отчете, а не GMP. Например, если сторонний медиаисточник — Rocketfuel, используйте `pid=rocketfuel_int`, а не `pid=dv360_int`. <Anchor target="_blank" href="/marketers/ru/docs/retargeting-attribution-guide">Подробнее</Anchor>.
   * Если ваша цель — **повторно вовлечь существующих пользователей, открыв приложение**, когда они кликают по рекламной ссылке (вместо перенаправления в магазин приложений), **используйте метод URI scheme** для диплинкинга. Для этого необходимо настроить ссылку CM360 следующим образом:
     * Параметр `af_dp`, настроенный в соответствии с URI scheme вашего приложения.
     * Параметр `af_force_deeplink=true`, чтобы явно принудительно включить поведение диплинкинга.
3. Добавьте ссылку атрибуции AppsFlyer к ссылке CM360:

   <Tabs>
   <Tab title="Android">

   ```http
   https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
   dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
   ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
   &c=campaign_name&advertising_id=13******-****-****-****-54**********
   ```

   </Tab>

   <Tab title="iOS">

   ```http
   https://ad.doubleclick.net/ddm/trackclk/N736113.127733/B202683.204586115;
   dc_trk_aid=404426918;dc_trk_cid=92566356;dc_lat=;dc_rdid=13******-****-****-****-54**********
   ?https://app.appsflyer.com/com.example?pid=rocketfuel_int
   &c=campaign_name&idfa=13******-****-****-****-54**********
   ```

   </Tab>
   </Tabs>

   * Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters?">структуре и параметрах ссылок атрибуции для iOS и Android</Anchor>
   * Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">структуре и параметрах ссылок атрибуции для CTV, консолей и ПК</Anchor>

#### 3. Настройка постбэков по внутренним событиям приложений

Чтобы гарантировать, что CM360 получает постбэки для событий из этих кампаний, рекомендуется установить для постбэков событий в приложении в dv360\_int значение «Все медиа-источники, включая органические».

### Применение ссылки атрибуции

Когда у вас будет ссылка атрибуции, убедитесь, что она используется при запуске рекламы на вашем целевом стороннем медиа-источнике. Когда происходит установка, AppsFlyer атрибутирует установку к выбранному стороннему медиа-источнику и уведомляет партнёра через постбэки. Затем AppsFlyer сообщает CM360 об установке или любом последующем событии в приложении через интеграцию DV360, если она активна.

Конечный результат – это установка или событие в приложении, которое атрибутируется к медиа-источнику и также регистрируется в CM360.

<div data-zendesk-anchors="google-marketing-platform-cm360-nondv360-thirdparty-media-source-for-click-and-impression-measurement=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-cm360-%D1%81%D0%BE-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%BD%D0%B8%D0%BC%D0%B8-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0%D0%BC%D0%B8-%D0%BD%D0%B5-%D0%BE%D1%82%D0%BD%D0%BE%D1%81%D1%8F%D1%89%D0%B8%D0%BC%D0%B8%D1%81%D1%8F-%D0%BA-%D0%B4%D0%B8%D1%81%D0%BF%D0%BB%D0%B5%D1%8E-%D0%B8-%D0%B2%D0%B8%D0%B4%D0%B5%D0%BE-360-dv360 h_01HN0GE07NDVK8MWQEYMKDFAE6=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-cm360-%D1%81%D0%BE-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%BD%D0%B8%D0%BC%D0%B8-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0%D0%BC%D0%B8-%D0%BD%D0%B5-%D0%BE%D1%82%D0%BD%D0%BE%D1%81%D1%8F%D1%89%D0%B8%D0%BC%D0%B8%D1%81%D1%8F-%D0%BA-%D0%B4%D0%B8%D1%81%D0%BF%D0%BB%D0%B5%D1%8E-%D0%B8-%D0%B2%D0%B8%D0%B4%D0%B5%D0%BE-360-dv360 h_01HVXSGQZP305D7EF1SY56F26B=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 measuring-thirdparty-traffic-running-via-cm360=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D1%80%D0%B0%D1%84%D0%B8%D0%BA%D0%B0-%D1%82%D1%80%D0%B5%D1%82%D1%8C%D0%B8%D1%85-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD-%D0%BF%D1%80%D0%BE%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B5%D0%B3%D0%BE-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-cm360 h_01HVK04VANY30B8EX94F9WPBGB=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D1%80%D0%B0%D1%84%D0%B8%D0%BA%D0%B0-%D1%82%D1%80%D0%B5%D1%82%D1%8C%D0%B8%D1%85-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD-%D0%BF%D1%80%D0%BE%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B5%D0%B3%D0%BE-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-cm360 step-1-integrate-the-thirdparty-media-source-and-gmp-with-appsflyer=1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%BD%D0%B5%D0%B3%D0%BE-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0-%D0%B8-gmp-%D1%81-appsflyer h_01HYBRGBH10N9H0WT45NQ65C6R=1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%BD%D0%B5%D0%B3%D0%BE-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0-%D0%B8-gmp-%D1%81-appsflyer h_01HYBB2SJEYE0WV2PRY5SK51GB=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 step-2-create-the-required-attribution-links=2-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D1%85-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HYBA8YS1CWHN3APE5SV506TC=2-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D1%85-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01JXQGQPDB66E3HWWEVPXXB8BZ=3-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%BC-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D0%BC-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 using-the-attribution-link=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HN0GE07N10T92EKR5B2482KB=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8" />

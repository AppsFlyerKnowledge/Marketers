---
title: >-
  Отправляйте пользователям настольных компьютеров ссылку на ваше мобильное
  приложение по СМС
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2019-11-21T09:13:52Z'
  edited_at: '2026-09-02T00:33:47Z'
  id: 360003799658
  locale: ru
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ru/articles/360003799658
---
> **Кратко:** Конвертируйте пользователей десктопа в пользователей мобильного приложения с помощью СМС-поставщиков и OneLink.

<Image align="center" alt="web-form-text-me-the-app.png" src="https://files.readme.io/d28b843ab7528138b4d85b147b8d613efde740d354238227b0f123030fa3a1de-360004940018.png" />

<div id="introduction" />

## Введение

Если у вашего бренда есть и веб-приложение, и мобильное приложение, пользователи десктопной веб-версии в какой-то момент могут решить, что хотят установить мобильное приложение.

Чтобы помочь им сделать это и улучшить пользовательский опыт, вы можете отправить им в SMS прямую ссылку на приложение. Это самый быстрый способ помочь им установить приложение.

Так им не придется открывать магазин приложений на мобильном устройстве, искать ваше приложение и устанавливать его. Если вы экономите пользователям время и силы, вероятность того, что они совершат конверсию и установят ваше мобильное приложение, повышается.

<div id="note" />

> 📘 **Примечание:**
>
> Мы предлагаем другое решение для <Anchor target="_blank" href="/marketers/ru/docs/qr-to-app-conversion">конверсии с десктопа в веб</Anchor>, которое требует лишь разместить на вашем десктопном сайте QR-код (сгенерированный на основе OneLink).

<div id="requirements" />

## Требования

Чтобы отправлять десктопным пользователям ссылку на ваше мобильное приложение в SMS, вам потребуется следующее:

1. Аккаунт у СМС-поставщика, например Twilio, AWS SNS или bandwidth.com.
2. Бэкенд-среда, в которой можно обрабатывать логику отправки пользователям ссылок в SMS.
3. Мультиплатформенная пользовательская ссылка, например <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">OneLink</Anchor>.

<div id="setting-up" />

## Настройка

В следующем разделе приведен общий обзор требований, описанных выше.

<div id="sms-provider-account-to-text-a-link-to-the-app" />

### Аккаунт у СМС-поставщика для отправки ссылки на приложение

Создайте аккаунт у любого СМС-поставщика. После этого вы сможете в любой момент отправлять ссылки на ваше мобильное приложение большому числу пользователей.

См. приведенный ниже список популярных поставщиков, которые поддерживают различные языки программирования и предоставляют комплексные API для разных сценариев использования:

* <Anchor target="_blank" href="https://www.twilio.com/docs/sms/send-messages">Twilio</Anchor>
* <Anchor target="_blank" href="https://dev.bandwidth.com/messaging/about.html">bandwidth</Anchor>
* <Anchor target="_blank" href="https://docs.aws.amazon.com/sns/latest/dg/sns-mobile-phone-number-as-subscriber.html">AWS SNS</Anchor>
* <Anchor target="_blank" href="https://www.braze.com/docs/user_guide/message_building_by_channel/sms/create/">Braze</Anchor>
* <Anchor target="_blank" href="https://www.airship.com/platform/channels/sms/">Airship</Anchor>
* [Swrve](https://docs.swrve.com/user-documentation/campaigns/campaign-channels/intro-to-sms/)
* <Anchor target="_blank" href="https://help.mixpanel.com/hc/en-us/articles/115004730066-Send-SMS-Messages-From-Mixpanel">Mixpanel</Anchor>

<div id="a-backend-environment-to-communicate-with-the-sms-provider" />

### Бэкенд-среда для взаимодействия с СМС-поставщиком

СМС-поставщикам требуются токены аутентификации, чтобы использовать их сервисы. Кроме того, номера телефонов пользователей относятся к конфиденциальным данным. Поэтому лучше всего обрабатывать всё на своем бэкенде.

<div id="a-multi-platform-custom-link" />

### Пользовательская ссылка для нескольких платформ

Пользовательская ссылка для нескольких платформ перенаправляет пользователя в нужный магазин приложений или в нужное место назначения в зависимости от его устройства. Так вы сможете отправить одну и ту же ссылку любому пользователю независимо от того, какое у него устройство.

<div id="texting-the-app-to-users" />

## Отправка пользователям ссылки на приложение в SMS

В этом разделе описан процесс отправки пользователям ссылки на приложение в SMS. В нем также объясняется, как отслеживать количество пользователей, которые устанавливают приложение по ссылке.

<div id="create-a-multi-platform-onelink" />

### Создайте OneLink для нескольких платформ

Создайте OneLink для нескольких платформ, чтобы вставить его в СМС. При создании ссылки можно указать медиаисточник и кампанию. Рекомендуем указать медиаисточник и кампанию следующим образом:

* медиаисточник: веб-сайт
* кампания: text-me-the-app

При отправке OneLink в СМС лучше использовать короткую версию ссылки OneLink.

Узнать, как создать ссылку, можно <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">здесь</Anchor>.

<div id="set-up-an-sms-topic-in-your-sms-provider-account" />

### Настройте тему СМС в аккаунте поставщика СМС

На этом этапе вы создаете тему СМС или сообщение, содержащее OneLink на приложение. Это СМС отправляется, когда пользователи заполняют и отправляют форму со своим номером телефона. Когда пользователи отправляют форму, ваш бэкенд получает запрос и взаимодействует с API поставщика СМС, чтобы отправить ссылку.

<div id="set-up-a-web-form-to-collect-phone-numbers" />

### Настройте веб-форму для сбора номеров телефонов

На выбранных страницах вашего сайта разместите призыв к действию, чтобы побудить пользователей установить ваше приложение. Призыв к действию должен открывать веб-форму, через которую пользователи смогут отправить свои номера телефонов.

<div id="apply-logic-in-your-backend" />

### Реализуйте логику в бэкенде

При отправке формы сайт должен отправить запрос в ваш бэкенд. Бэкенд получает номер телефона и отправляет запрос поставщику СМС, чтобы отправить на телефон пользователя ссылку на приложение в СМС.

Обратитесь к API и документации вашего SMS-провайдера, чтобы узнать, как реализовать соответствующую логику на вашем бэкенде.

<div id="how-attribution-works-when-sending-a-link-to-the-app" />

## Как работает атрибуция при отправке ссылки на приложение

 Невозможно включить идентификатор ID рекламы при отправке пользователям настольных компьютеров ссылки на приложение. Поэтому AppsFlyer использует <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">атрибуцию с использованием вероятностного моделирования</Anchor>.

AppsFlyer <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows#окно-атрибуции-вероятностного-моделирования">ограничивает окно атрибуции</Anchor> для кликов вероятностного моделирования, чтобы поддерживать точность. Ограничения:

* iOS: до 24 часов
* Android (Google Play): до одного часа
* Android (не из магазина): до 24 часов

Побуждайте пользователей устанавливать приложение как можно скорее после перехода по ссылке, чтобы AppsFlyer мог точно атрибутировать установку к ссылке из SMS-сообщения. Для этого можно предлагать купоны, скидки или внутриигровую валюту.

## people-based attribution

Есть и другие способы, помимо отправки ссылки на приложение в сообщении, с помощью которых пользователи переходят из веба в приложение. Не всегда понятно, откуда приходят эти пользователи и какие медиаисточники и кампании влияют на их конверсию.

Чтобы получить больше инсайтов о том, сколько веб-пользователей конвертируются в пользователей мобильных приложений и какие медиаисточники и кампании участвуют в этом процессе, используйте People-based attribution.

People-based attribution (PBA) объединяет данные из веб-кампаний и кампаний мобильных приложений. Консолидированные данные помогают анализировать пользовательские пути между платформами и переход пользователей из веба в мобильные приложения.

Чтобы узнать больше, см. <Anchor target="_blank" href="/marketers/ru/docs/people-based-attribution-pba-overview">здесь</Anchor>.

<div data-zendesk-anchors="introduction=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01KQS4E94MVN7NEEDR7ESA17K9=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01KQS4E94MSP2PQ0RVAHS2JY8R=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 requirements=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01KQS4E94MVYA0EZ7Y0FCMZEBC=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F setting-up=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 h_01KQS4E94MF2BZZ5AXP67R7YRW=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 sms-provider-account-to-text-a-link-to-the-app=%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82-%D1%83-%D1%81%D0%BC%D1%81-%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%89%D0%B8%D0%BA%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 h_01KQS4E94MYPEBKN80CNHCV1DG=%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82-%D1%83-%D1%81%D0%BC%D1%81-%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%89%D0%B8%D0%BA%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 a-backend-environment-to-communicate-with-the-sms-provider=%D0%B1%D1%8D%D0%BA%D0%B5%D0%BD%D0%B4-%D1%81%D1%80%D0%B5%D0%B4%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F-%D1%81-%D1%81%D0%BC%D1%81-%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%89%D0%B8%D0%BA%D0%BE%D0%BC h_01KQS4E94MW7DWRGPNX8D98W46=%D0%B1%D1%8D%D0%BA%D0%B5%D0%BD%D0%B4-%D1%81%D1%80%D0%B5%D0%B4%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F-%D1%81-%D1%81%D0%BC%D1%81-%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%89%D0%B8%D0%BA%D0%BE%D0%BC a-multiplatform-custom-link=%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B0%D1%8F-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%B8%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC h_01KQS4E94MP2Q29S7892GGT0QM=%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B0%D1%8F-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%B8%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC texting-the-app-to-users=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F%D0%BC-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B2-sms h_01KQS4E94MGBCX0TM5AGHXPX0Z=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F%D0%BC-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B2-sms create-a-multiplatform-onelink=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-onelink-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%B8%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC h_01KQS4E94MQSWQ9S0CHNJG8B77=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-onelink-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B5%D1%81%D0%BA%D0%BE%D0%BB%D1%8C%D0%BA%D0%B8%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC set-up-an-sms-topic-in-your-sms-provider-account=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D1%82%D0%B5%D0%BC%D1%83-%D1%81%D0%BC%D1%81-%D0%B2-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B5-%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%89%D0%B8%D0%BA%D0%B0-%D1%81%D0%BC%D1%81 h_01KQS4E94MG7KGB8HQVT11717J=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D1%82%D0%B5%D0%BC%D1%83-%D1%81%D0%BC%D1%81-%D0%B2-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B5-%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%89%D0%B8%D0%BA%D0%B0-%D1%81%D0%BC%D1%81 set-up-a-web-form-to-collect-phone-numbers=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B2%D0%B5%D0%B1-%D1%84%D0%BE%D1%80%D0%BC%D1%83-%D0%B4%D0%BB%D1%8F-%D1%81%D0%B1%D0%BE%D1%80%D0%B0-%D0%BD%D0%BE%D0%BC%D0%B5%D1%80%D0%BE%D0%B2-%D1%82%D0%B5%D0%BB%D0%B5%D1%84%D0%BE%D0%BD%D0%BE%D0%B2 h_01KQS4E94MNPRC5AJ9EJD4GPG3=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B2%D0%B5%D0%B1-%D1%84%D0%BE%D1%80%D0%BC%D1%83-%D0%B4%D0%BB%D1%8F-%D1%81%D0%B1%D0%BE%D1%80%D0%B0-%D0%BD%D0%BE%D0%BC%D0%B5%D1%80%D0%BE%D0%B2-%D1%82%D0%B5%D0%BB%D0%B5%D1%84%D0%BE%D0%BD%D0%BE%D0%B2 apply-logic-in-your-backend=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D1%83%D0%B9%D1%82%D0%B5-%D0%BB%D0%BE%D0%B3%D0%B8%D0%BA%D1%83-%D0%B2-%D0%B1%D1%8D%D0%BA%D0%B5%D0%BD%D0%B4%D0%B5 h_01KQS4E94MA810B0QRSMDQ0FQM=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D1%83%D0%B9%D1%82%D0%B5-%D0%BB%D0%BE%D0%B3%D0%B8%D0%BA%D1%83-%D0%B2-%D0%B1%D1%8D%D0%BA%D0%B5%D0%BD%D0%B4%D0%B5 how-attribution-works-when-sending-a-link-to-the-app=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 h_01KQS4E94MC8C19RCCPV52G7N1=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 peoplebased-attribution=people-based-attribution h_01KQS4E94MJ0C6Q82H67R22S2W=people-based-attribution" />

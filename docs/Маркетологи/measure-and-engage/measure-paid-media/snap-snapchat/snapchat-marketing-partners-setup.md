---
title: Настройка маркетинговых партнеров Snapchat
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
  created_at: '2022-01-24T08:47:31Z'
  edited_at: '2026-09-17T00:29:57Z'
  id: 4417694142481
  locale: ru
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ru/articles/4417694142481
---
> **Кратко:** Интегрируйтесь с маркетинговыми партнерами Snapchat, чтобы измерять кампании, которые вы проводите совместно с ними. Когда AppsFlyer настроен, он отправляет постбэки настроенному маркетинговому партнеру Snapchat.

## Настройка маркетингового партнера Snapchat

Выполните следующие действия, чтобы настроить свои кампании с любым из маркетинговых партнеров Snapchat.

* Активируйте <Anchor target="_blank" href="/marketers/ru/docs/snapchat-advanced-srn-integration-setup">атрибуцию Snapchat</Anchor>.
* На дэшборде Snapchat **Business Manager** скопируйте **Snap Account ID**, выделенный ниже зеленым цветом.

  ![snapchat-dashboard.png](https://files.readme.io/a0942bd27528d4a837edc6eb5d11338bf0622ddc42e382231a8f210aedad1424-50902448760337.png)

После активации Snapchat и получения Snap Account ID настройте маркетингового партнера:

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Интеграции партнеров** > **Активные интеграции**.
2. В поле поиска введите название нужного партнера или "Snapchat", чтобы увидеть полный список маркетинговых партнеров Snapchat.
3. Щелкните логотип нужного партнера, чтобы открыть окно настройки.
4. Включите **Activate partner**.
5. Вставьте **Snap account ID**, полученный на дэшборде Snapchat (с дефисами), в поле **Snap Account ID**.
6. Нажмите **Save** (Сохранить).

### Постбэки по умолчанию

AppsFlyer может автоматически отправлять партнерам постбэки по установкам и повторному вовлечению. Используйте этот раздел, чтобы определить **источник пользователей** , которым разрешено отправлять эти постбэки. В некоторых случаях источник пользователей предопределен и не может быть изменен:

![remerge2.png](https://files.readme.io/4f3f52b3610b3e3bcf0adc6e963f1f2c39cdb0b2de27569c890844aac477b3d0-50902448761873.png)

Выберите **Only events attributed to this partner** для событий, которые приходят только от пользователей, атрибутированных этому партнеру.  
Выберите **Events attributed to any partner or organic** , чтобы вся ваша база пользователей была доступна для передачи отчетности этому партнеру.

### События в приложении

1. Чтобы отправлять маркетинговому партнеру Snapchat, которого вы настраиваете, постбэки по событиям в приложении, установите переключатель In-App Events Postback в положение **ON**.
2. По отдельности добавьте события в приложении (события SDK), которые вы хотите отправлять партнеру, и <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#сопоставление-событий">сопоставьте их нужным образом.</Anchor>

> 🚧 **Важно!**
>
> Отключение атрибуции для Snapchat предотвращает отправку постбэков маркетинговым партнерам Snapchat.

> 📄 **Смотрите также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/skan-interoperation-with-snapchat">Взаимодействие Snapchat и AppsFlyer SKAdNetwork</Anchor>

<div data-zendesk-anchors="setting-up-a-snapchat-marketing-partner=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-snapchat h_01HDNZAAS11ADG02FXNPSYYH69=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BC%D0%B0%D1%80%D0%BA%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%BE%D0%B2%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0-snapchat default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HDNZAAS1M2317CKQ13SP11KM=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events=%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HDNZAAS1JZPHS32PNFFCR12A=%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8 h_01HDNZAAS1PRWK6EVQTTV3YNQM=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01HDNZBZARD9E54VAFVSRQFWEH=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

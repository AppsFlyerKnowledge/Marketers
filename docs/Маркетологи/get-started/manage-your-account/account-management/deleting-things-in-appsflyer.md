---
title: Удаление элементов в AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-11-21T16:07:58Z'
  edited_at: '2026-08-18T00:16:54Z'
  id: 360000603117
  locale: ru
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/ru/articles/360000603117
---
> **Краткий обзор.** Как рекламодатели могут удалить приложения, чтобы прекратить атрибуцию, удалить медиа-источники или связанные с пользователем данные.

<Image align="center" alt="shutterstock_699498934.jpg" src="https://files.readme.io/db2cd79f6da6de42042707fb2c8bbfe450a6cdc17a93f7a9dc9ea27d04716ef3-34228068995857.jpg" width="363px" />

<div id="delete-user-history" />

## Удаление истории пользователя

Некоторые законодательные акты по защите данных, такие как GDPR или CCPA, дают пользователям *право на удаление их данных*.

**Сценарий:** Пользователь направляет вам запрос на удаление связанных с ним данных. Согласно GDPR, это должно быть сделано в течение 30 дней.

**Необходимое действие:** Отправьте запрос на удаление через <Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests">API OpenDSR</Anchor>.

<div id="stop-attributing-installs-to-a-media-source" />

## Прекращение атрибуции установок к медиа-источнику

AppsFlyer собирает информацию об установках и событиях для настроенных вами медиа-источников. Если для медиа-источника настроена атрибуция, новые установки атрибутируются.

**Сценарий:** Если вы прекратите запускать кампании в медиа-источнике и по нему не будет кликов, показов или установок, атрибуция прекращается. Однако внутренние события имеющихся пользователей продолжают регистрироваться и атрибутироваться.

**Чтобы прекратить атрибуцию установок медиа-источнику:**

* **SKAN (для приложений iOS):**
  1. <Anchor target="_blank" href="/marketers/ru/docs/skan-conversion-studio#disable-skan-measurement">Отключите измерение SKAN</Anchor>.
  2. Для <Anchor target="_blank" href="/marketers/ru/docs/get-skan-postback-data-from-google-ads#turning-off-the-skan-integration">Google Ads</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-interoperation-with-meta-ads#turning-off-the-skan-integration">Meta ads</Anchor> вам также нужно удалить подключения SKAN, чтобы остановить запись данных SKAN.
* **SRN:** <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#деактивировать-партнерскую-интеграцию">Деактивируйте интеграцию партнера</Anchor>.
* **Не-SRNs:**  
  1. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#деактивировать-партнерскую-интеграцию">Деактивируйте интеграцию партнера</Anchor>.
  2. Клики и установки, приходящие из ссылки атрибуции AppsFlyer в вашей рекламе, будут по-прежнему регистрироваться и атрибутироваться. Убедитесь, что реклама, показываемая лидам, больше не содержит ссылок атрибуции AppsFlyer.
* **Собственные каналы взаимодействия:**
  * Прекратите использовать соответствующие настраиваемые ссылки OneLink.

<div id="remove-or-delete-an-app" />

## Удаление приложения

У вас есть возможность временно удалить приложение.

<div id="temporarily-removing-an-app" />

#### Временное удаление приложения

При временном удалении приложения запись данных прекращается, приложение не отображается в дэшбордах и становится серым на странице «Мои приложения». Тем не менее приложение остается связанным с аккаунтом, и его можно восстановить. При восстановлении приложения сохраняются исторические данные, такие как настройки приложения, одобренные агентства и токены.

<div id="note" />

> 📘 **Примечание:**
>
> Удаление приложения выполняется индивидуально. Тем не менее вы можете <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer#управляйте-своими-приложениями-массово-через-api">удалить несколько приложений через API</Anchor>.

**Чтобы удалить приложение:**

1. В верхней панели нажмите **Мои приложения**.
2. Выберите меню действий с приложением.
3. Нажмите **Удалить**, затем подтвердите действие.  
   Приложение будет удалено и пропадет из списка приложений.

**Чтобы восстановить удаленное приложение:**

* Свяжитесь со своим CSM или напишите на [hello@appsflyer.com](mailto:hello@appsFlyer.com), чтобы начать процесс. Как только CSM восстановит приложение, вы сможете снова добавить его в свой аккаунт.

<div id="transfer-apps-between-accounts" />

## Перенос приложений между аккаунтами

Подробнее см. в этом руководстве: <Anchor target="_blank" href="/marketers/ru/docs/transferring-apps-between-accounts">Перенос приложений между аккаунтами</Anchor>.

<div id="delete-your-account-or-downgrade-your-subscription-plan" />

## Удаление аккаунта или понижение тарифного плана

Свяжитесь с вашим менеджером или с нами по адресу [hello@appsflyer.com](mailto:hello@appsFlyer.com).

<div data-zendesk-anchors="delete-user-history=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8%D1%81%D1%82%D0%BE%D1%80%D0%B8%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F h_01HNZ7TNZM4P5APM2B1WQ4X7S5=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8%D1%81%D1%82%D0%BE%D1%80%D0%B8%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F stop-attributing-installs-to-a-media-source=%D0%BF%D1%80%D0%B5%D0%BA%D1%80%D0%B0%D1%89%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA-%D0%BA-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D1%83 h_01HNZ7VPA16065PGCSZDMQZ3ZC=%D0%BF%D1%80%D0%B5%D0%BA%D1%80%D0%B0%D1%89%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA-%D0%BA-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D1%83 delete-an-app=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HNZ7XKEFRNEWGQZ58T7H0KDH=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F removing-an-app=%D0%B2%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D0%B5-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01J52J31FDKSPNWSD5J2V5BYTW=%D0%B2%D1%80%D0%B5%D0%BC%D0%B5%D0%BD%D0%BD%D0%BE%D0%B5-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HYJ5EPX4B1G1SAF6XGZ7ADWZ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 transfer-apps-between-accounts=%D0%BF%D0%B5%D1%80%D0%B5%D0%BD%D0%BE%D1%81-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0%D0%BC%D0%B8 h_01HNZ7ZW7ZKDSD2TTEX55PYB91=%D0%BF%D0%B5%D1%80%D0%B5%D0%BD%D0%BE%D1%81-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0%D0%BC%D0%B8 delete-your-account-or-downgrade-your-subscription-plan=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0-%D0%B8%D0%BB%D0%B8-%D0%BF%D0%BE%D0%BD%D0%B8%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%B0%D1%80%D0%B8%D1%84%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D0%BB%D0%B0%D0%BD%D0%B0 h_01HNZ81GQ8Z6R8DV8Z6SAXYRB9=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0-%D0%B8%D0%BB%D0%B8-%D0%BF%D0%BE%D0%BD%D0%B8%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%B0%D1%80%D0%B8%D1%84%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D0%BB%D0%B0%D0%BD%D0%B0" />

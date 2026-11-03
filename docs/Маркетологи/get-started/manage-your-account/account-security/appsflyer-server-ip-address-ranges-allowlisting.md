---
title: >-
  Диапазоны IP-адресов серверов AppsFlyer (для включения в список разрешенных
  адресов)
metadata:
  keywords:
    - whitelisting
    - AppsFlyer
    - IPs
    - Advertisers
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Ad Networks
  created_at: '2015-12-24T11:30:11Z'
  edited_at: '2026-08-19T00:16:32Z'
  id: 207447093
  locale: ru
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ru/articles/207447093
---
> **Краткий обзор.** IP-адреса AppsFlyer, используемые для исходящих запросов API.

## Диапазоны IP-адресов серверов AppsFlyer

Перечисленные IP-адреса контролируются и используются AppsFlyer. Список время от времени изменяется в соответствии с используемыми нами мощностями и другими эксплуатационными требованиями. Мы прилагаем все усилия, чтобы изменять этот список как можно реже.

С помощью API AppsFlyer рекламодатели и партнеры получают услуги атрибуции и отчетности, в частности: в частности: в частности:

* Отправка постбэков
* Отправка сообщений Push API

Если вы используете устройства защиты периметра сети, такие как межсетевые экраны и прокси-серверы, попросите службу безопасности внести IP-адреса из <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTzJqwOhIkSV0Mbnu4DZOx2eWKAd8OPRUNCu2REjz9z9qonI5ZDlHl6kGd1KAXopaDbf1MzuNXjeVj-/pub?gid=0&single=true&output=csv">этого файла</Anchor> в список разрешенных.

16 февраля 2022 года мы отключили старые IP-адреса и удалили их из списка разрешенных адресов.

Адреса в списке разрешенных адресов используют следующие блоки CIDR:

* [45.92.116.0/22]
* [194.28.46.0/23]

### Загрузка аудиторий

Если вы используете устройства защиты периметра сети, такие как межсетевые экраны и прокси-серверы, попросите службу безопасности внести IP-адреса из этого файла в список [разрешенных адресов AppsFlyer для аудиторий](https://support.appsflyer.com/hc/article_attachments/16888953497617).

Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/audiences-guide">аудиториях</Anchor>.

### Pull API и межсерверное взаимодействие (S2S)

Адреса, приведенные в этой статье, не влияют на Pull API и S2S. Однако убедитесь, что домен *\*.appsflyer.com* внесен в список разрешенных и никаким образом не заблокирован.

<div data-zendesk-anchors="appsflyer-server-ip-address-ranges=%D0%B4%D0%B8%D0%B0%D0%BF%D0%B0%D0%B7%D0%BE%D0%BD%D1%8B-ip-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%BE%D0%B2-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%BE%D0%B2-appsflyer uploading-audiences=%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B0-%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B9 pull-api-and-servertoserver-s2s=pull-api-%D0%B8-%D0%BC%D0%B5%D0%B6%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%BD%D0%BE%D0%B5-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D0%B5-s2s" />

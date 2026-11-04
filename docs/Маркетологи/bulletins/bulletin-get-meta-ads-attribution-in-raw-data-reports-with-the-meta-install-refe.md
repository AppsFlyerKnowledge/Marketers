---
title: >-
  Бюллетень: получите атрибуцию рекламы Meta в отчетах о сырых данных с помощью
  реферера установки Meta
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-02-12T10:47:33Z'
  edited_at: '2026-10-19T14:39:15Z'
  id: 22461635687185
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/22461635687185
---
| **Что нового?** | Реферер установки Meta помогает с измерением атрибуции для ваших рекламных кампаний Android в Facebook, Instagram и Audience Network, цель которых — установка приложения. Это в дополнение к Google Play Install Referrer. |
| --- | --- |
| **Дата вступления в силу** | 28 февраля 2024 г. |
| **Необходимые условия** | Убедитесь, что выполнены следующие условия:<ul><li>У вас установлена версия SDK AppsFlyer **V6.12.6** или более поздняя, чтобы данные реферера передавались корректно</li><li>На странице интеграции указан <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#encrypted-data-from-the-referrer">ключ дешифрования Install Referrer</Anchor></li><li>На устройствах пользователей установлены <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#prerequisites">версии, описанные здесь</Anchor></li></ul> |
| **Необходимые действия** | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#configure-meta-install-referrer-support">Настройте поддержку реферера установки Meta</Anchor> |
| **Что мне нужно знать?** | Данные реферера имеют приоритет над данными, предоставляемыми интеграцией рекламы Meta, и доступны в отчетах о сырых данных. Это решение применимо как к атрибуции по кликам, так и к атрибуции по просмотрам. |
| **Каково влияние?** | <ul><li>Вы можете увидеть увеличение количества установок, атрибутированных Meta, в отчетах о сырых данных</li><li>В отчетах о сырых данных теперь доступны два новых поля типа соответствия: `fb_referrer` и `ig_referrer`:<ul><li>`fb_referrer` — для атрибуции из приложения Facebook</li><li>`ig_referrer` — для атрибуции из приложения Instagram</li><li>`fb_referrer` или `ig_referrer` — для атрибуции из Audience Network.</li></ul></li></ul> |

<div id="see-also" />

> 📄 **Смотрите также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#userlevel-data">Реферер установки Meta</Anchor>

<div data-zendesk-anchors="h_01H9FHRVKE88CXGH8G7E26ZXT2=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

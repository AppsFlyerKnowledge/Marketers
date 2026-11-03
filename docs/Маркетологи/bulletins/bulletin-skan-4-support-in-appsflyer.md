---
title: "Бюллетень: Поддержка SKAN\_4 в AppsFlyer"
metadata:
  keywords:
    - iOS
    - Marketers
    - SKAN
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2026-08-18T00:21:19Z'
  id: 11938810583825
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/11938810583825
---
| **Заголовок** | Решение AppsFlyer SKAdNetwork теперь поддерживает SKAN 4. Сюда входят значительные изменения в SKAN Conversion Studio, а также дэшборды и отчеты SKAN. |
| --- | --- |
| **Дата вступления в силу** | <ul><li>15 февраля 2023 года: С нативным SDK iOS V6.10+</li><li>Мы рекомендуем перейти на новую версию V6.12+, даже если вы используете V6.10 с февраля.<ul><li>Список изменений см. <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-ios-sdk-release-notes">здесь</Anchor>.</li></ul></li><li>Скоро: Поддержка других SDK и плагинов AppsFlyer</li></ul> |
| **Необходимые условия** | Для правильной записи данных iOS в SKAN 4 необходимо следующее:<ul><li><Anchor target="_blank" href="/marketers/ru/docs/appsflyer-ios-sdk-release-notes">SDK AppsFlyer версии V6.12.1+</Anchor></li><li>Рекламная сеть должна генерировать подпись рекламы для SKAdNetwork V4.</li><li>Для рекламных объявлений, отображаемых в приложении, приложение должно быть создано с использованием SDK iOS 16.1 или более поздней версии.</li><li>Для веб-рекламы требуется Safari 16.1 или более поздней версии.</li><li>Рекламируемое приложение должно быть подписано в App Store и работать на устройстве с iOS 16.1 или более поздней версии.</li></ul> |
| **Необходимые действия** | <ul><li>Обновите <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-ios-sdk-release-notes">SDK AppsFlyer до версии V6.12.1+.</Anchor></li><li>В AppsFlyer SKAN Conversion Studio перейдите на <Anchor target="_blank" href="/marketers/ru/docs/skan-conversion-studio#skan-4">режим измерения SKAN 4</Anchor> и настройте CV для 3 окон SKAN (или сохраните настройки по умолчанию).</li></ul>**Примечание.** После обновления до SKAN 4:<ul><li>Таймер активности для установок до SKAN 4 составляет 48 часов.</li><li>Вы не можете вернуться к более ранней версии SKAN.</li></ul> |
| **Изменения в <Anchor target="_blank" href="/marketers/ru/docs/skan-conversion-studio#skan-4">SKAN Conversion Studio</Anchor>** | Новый режим измерения SKAN 4 для настройки 3 окон SKAN |
| **Изменения в <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">дэшбордах</Anchor>** | <ul><li>Обзорный дэшборд SKAN включает новые поля (доступные в настройках таблицы) для подсчета количества событий и доходов в течение 3 окон SKAN:<ul><li>Количество событий D0-D2</li><li>Количество событий D0-D2 (смоделировано)</li><li>Количество событий D3-D7</li><li>Количество событий D8-D35</li><li>Доход D0-D2 ($)</li><li>Доход D0-D2 ($) (смоделировано)</li><li>Доход D3-D7 ($)</li><li>Доход D8-D35 ($)</li></ul></li><li>Представление дэшборда SSOT отображает поля данных D2 вместо окна активности (AW). Для данных SKAN 3 в этом поле отображаются все данные окна активности, даже если окно длиннее или короче 2 дней.</li></ul> |
| **Изменения в <Anchor target="_blank" href="/marketers/ru/docs/skan-raw-data-reports">отчетах</Anchor>** | <ul><li>Отчеты SKAdNetwork включают следующие новые поля для поддержки SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: Значением будет целое число, которое представляет собой окно SKAN, либо`0`, либо`1`, либо `2`. Для SKAN 3 значение равно `0`</li><li>**skad\_coarse\_conversion\_value**: Значение может быть`низким`, `средним` или `высоким`. Для SKAN 3 значение равно `null`.</li><li>**skad\_source\_identifier**: Значение — строка до 4 цифр. Для SKAN 3 значение равно `null`.</li><li>**skad\_source\_domain**: Значение — это строка, которая представляет собой источник атрибутируемой веб-рекламы. Для SKAN 3 значение равно `null`.</li><li>**ad\_network\_creative**: Значение — это строка на основе обогащении данных, полученных от рекламной сети. Для SKAN 3 значение пустое.</li></ul></li><li>Затронуты следующие отчеты Data Locker и Push API:</li></ul><ul><li>**skad\_installs** (через Data Locker и Push API)</li><li>**skad\_redownloads** (через Data Locker и Push API)</li><li>**skad\_inapps** (через Data Locker и Push API)</li><li>**skad\_postbacks** (через Data Locker)</li><li>**skad\_postbacks\_copy** (не включает поле ad\_network\_creative) (через Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">См. примеры схем отчетов</Anchor></li></ul><ul><li>API для даты прибытия агрегированных постбэков SKAN и API для агрегированной отчетности об эффективности SKAN содержат поля SKAN 4. **Примечание**: Вы должны использовать путь для токена API V2 для SKAN 4.</li></ul> |
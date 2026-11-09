---
title: Миграция на AppsFlyer с других платформ
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
  created_at: '2019-07-01T13:11:37Z'
  edited_at: '2026-08-19T00:17:44Z'
  id: 360001923697
  locale: ru
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ru/articles/360001923697
---
> **Краткий обзор:** Запланируйте миграцию на AppsFlyer от другого поставщика атрибуции. Вы узнаете, как в период миграции избежать двойной оплаты, дублирования и потери данных.

<Image align="center" alt="migration flow" src="https://files.readme.io/31d67493ae3ae6912b4da3163ebb731a8d58494c3007ef1d08cb7332226d9e81-360017326677.png" />

<div id="about-migrating-to-appsflyer-from-other-vendors" />

## О миграции на AppsFlyer с других платформ

Миграция на AppsFlyer с решения другого поставщика включает следующие основные задачи:

* [Интеграция SDK](/docs/migration-to-appsflyer-from-other-vendors#интеграция-sdk)
* [Миграция устройств](/docs/migration-to-appsflyer-from-other-vendors#миграция-устройств--необязательно)
* [Миграция кампаний](/docs/migration-to-appsflyer-from-other-vendors#миграция-кампаний)
* [Настройка отчетов по данным](/docs/migration-to-appsflyer-from-other-vendors#настройка-отчетов-по-данным)

Над решением этих задач можно работать одновременно. Однако мы рекомендуем:

* Выполнить все задачи до релиза обновленного приложения с SDK AppsFlyer.
* Приостановить текущие маркетинговые кампании, прежде чем выполнять миграцию идентификаторов устройств.

<div id="compare-measurement-between-appsflyer-and-other-mmps" />

### Сравните измерения между AppsFlyer и другими MMP

При рассмотрении вопроса о миграции от других MMP, рекламодателям, возможно, захочется сравнить показатели атрибуции обоих MMP по одним и тем же медиа-источникам и кампаниям. Однако не все медиа-источники поддерживают измерение с помощью более, чем одного MMP. Те, которые это делают, могут иметь определенные ограничения и трудности в предотвращении расхождений в атрибуции. Подробнее см. в статье <Anchor target="_blank" href="/marketers/ru/docs/measuring-attribution-with-multiple-mmps">Измерение атрибуции с помощью нескольких MMP</Anchor>.

<div id="tasks" />

## Действия

В таблице ниже описан объем работ по каждой задаче. Чтобы увидеть точную разбивку основных задач, а также фиксировать прогресс, загрузите <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">эту электронную таблицу</Anchor>

<div id="scope-of-work" />

#### Объем работ

<table><thead><tr><th>Выручка</th><th>Необходимое действие</th><th>Кто задействован</th><th>Ожидаемое время выполнения</th><th>Примечания</th></tr></thead><tbody><tr><td>Предварительные условия</td><td><ol><li> <a href="https://www.appsflyer.com/get-started" target="_blank">Создайте аккаунт AppsFlyer</a>.</li><li> <a href="./adding-an-app-to-appsflyer" target="_blank">Добавьте приложение</a> в AppsFlyer.</li><li>[Необязательно] Измените заданное по умолчанию <a href="./set-up-re-attribution-window" target="_blank">окно реатрибуции</a> в 90 дней, чтобы оно соответствовало <span>вашему определению активных пользователей.</span> </li></ol></td><td>Маркетолог / пользователь дэшборда AppsFlyer</td><td>2 часа</td><td> </td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#интеграция-sdk">Интеграция SDK</a></td><td><ul><li>Интегрируйте SDK AppsFlyer в приложение.</li><li>Сопоставьте внутренние события S2S или SDK.</li><li>Обновите версию приложения в магазинах приложений.</li></ul></td><td>Разработчики приложений</td><td>1–2 недели</td><td><ul><li> <strong>Рекомендация:</strong> Интегрируйте SDK AppsFlyer в версию приложения для тестирования.</li><li>Готовое приложение должно быть обновлено в магазинах приложений после выполнения всех остальных задач.</li></ul></td></tr><tr><td> <a href="./migration-to-appsflyer-from-other-vendors#миграция-устройств--необязательно">Миграция устройств</a> [необязательно]</td><td>Мигрируйте идентификаторы устройств, чтобы избежать двойной атрибуции имеющихся пользователей.</td><td>Инженер данных</td><td>1–2 недели</td><td rowspan="2"><ul><li>Перед миграцией рекомендуем приостановить текущие кампании и возобновить их после обновления версии приложения.</li><li>Чтобы обеспечить полный охват, повторите перенос устройств в последний день миграции. </li></ul></td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#миграция-кампаний">Миграция кампаний</a></td><td><ul><li>Интегрируйте рекламные сети в AppsFlyer</li><li>Перенесите текущие кампании из следующих источников:<ul><li>SRN:</li><li>Рекламные сети без собственной атрибуции (не относящиеся к SRN)</li><li>Собственные медиа</li></ul></li></ul></td><td>Маркетолог / UA менеджер</td><td>1–3 недели</td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#настройка-отчетов-по-данным">Настройка отчетов по данным</a></td><td><ul><li>Адаптируйте / сопоставьте структуры имеющихся отчетов со структурами отчетов AppsFlyer.</li><li>Подготовьтесь к получению отчетов AppsFlyer.</li></ul></td><td>Инженер данных</td><td>2–4 недели</td><td> </td></tr></tbody></table>

<div id="sdk-integration" />

### Интеграция SDK

<div id="sdk-integration::c763138b" />

<Accordion title="Интеграция SDK">

SDK AppsFlyer, интегрированный в приложение, является связующим звеном между приложением и платформой AppsFlyer. Он сообщает об установках, открытиях и внутренних событиях приложения и т. д.

**Чтобы интегрировать SDK AppsFlyer**:

1. Интегрируйте SDK AppsFlyer в приложение.  
   См. руководства по интеграции SDK для <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">Android</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">iOS</Anchor>.
2. Сопоставьте внутренние события приложения, которые вы хотите регистрировать, с помощью схем AppsFlyer.  
   Это можно сделать через <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview">SDK</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Удалите SDK конкурирующего поставщика атрибуции.  
   Это можно сделать сразу, перейдя исключительно на AppsFlyer, или одновременно использовать оба SDK в течение нескольких недель. Смотрите описание этих вариантов в таблице ниже.

| Вариант | Что происходит после  <br />выпуска обновленной версии приложения | Эффект |
| --- | --- | --- |
| Удалить SDK конкурента (рекомендуется) | Новые установки и обновления регистрирует только AppsFlyer.  <br />Конкурент по-прежнему отображает события, выполненные пользователями, пока пользователи не обновят свое приложение. | <ul><li>Быстрый переход.</li><li>Отсутствие двойной атрибуции.</li></ul> |
| Оставить SDK конкурента на период миграции | Атрибутируют новые установки и регистрируют события и AppsFlyer, и конкурент. На следующем этапе следует удалить SDK конкурента. | <ul><li>Возможна проверка данных. Это означает, что вы можете сравнивать данные AppsFlyer и системы другого поставщика.</li><li>Двойная атрибуция может вызвать двойные расходы в рекламных сетях. См. приведенные ниже примеры.</li><li>Повышенная нагрузка.</li></ul> |

4. После выполнения всех задач по миграции выпустите обновленную версию приложения с SDK AppsFlyer. Новые пользователи будут атрибутироваться через AppsFlyer.   
   **Примечание**:
   * Обязательно обновите приложение для магазинов iOS, Google Play и всех независимых площадок для Android.
   * Ваше приложение для Android может быть выложено на неофициальных сайтах APK, даже если вы этого не знаете (чтобы это выяснить, введите в интернете название пакета вашего приложения). Сайтам APK требуется некоторое время для обновления до последней версии, поэтому они могут привлекать органических пользователей, которые устанавливают старые версии без SDK AppsFlyer.
   * Обновление приложения в магазинах приложений может занять пару дней. Пользователи, устанавливающие приложение в этот период, могут получить предыдущую версию.

</Accordion>

<div id="device-migrationoptional" />

### Миграция устройств — необязательно

<div id="about-device-migration" />

<Accordion title="О миграции устройств">

Миграция устройств — это процесс загрузки в AppsFlyer списка идентификаторов устройств ваших имеющихся пользователей (IDFA, IDFV, GAID, CUID). Этот процесс нужно выполнить до выпуска новой версии приложения, в которой есть SDK AppsFlyer. Есть два варианта миграции устройств: [с атрибуцией](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) или [без атрибуции](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration).

Миграция устройств решает проблемы с данными по имеющимся пользователям, которые загрузили приложение и были атрибутированы предыдущим поставщиком систем атрибуции. Например, в случае двойной оплаты в SRN, которая возникает, когда пользователи, изначально атрибутированные SRN-сети предыдущим поставщиком, все еще находятся в ее окне атрибуции и повторно атрибутируются этой SRN уже системой AppsFlyer.

<div id="example" />

> 📄 **Пример**
>
> * Новый пользователь кликает по рекламному объявлению в приложении Facebook и устанавливает ваше приложение 15 июня.
> * 24 июня этот пользователь обновляет приложение до версии с SDK AppsFlyer и запускает его. Для AppsFlyer это новый пользователь, которого нужно атрибутировать в реальном времени.
> * AppsFlyer запрашивает у Meta Ads идентификатор устройства пользователя. Поскольку пользователь все еще находится в рамках 28-дневного окна атрибуции Meta Ads, то Meta Ads атрибутирует пользователя себе. Из-за этого владелец приложения несет двойные расходы за этого пользователя.

После миграции устройств данные отражаются в AppsFlyer следующим образом:

* **Установки** **данные:** Как и в случае с <Anchor target="_blank" href="/marketers/ru/docs/set-up-re-attribution-window#reinstall">повторными установками</Anchor>, у перенесенных устройств нет данных об установках. Установки по перенесенным устройствам не отображаются в AppsFlyer.
* **Данные о внутренних событиях и сессиях:** Регистрируются и отображаются как органические при использовании [метода миграции устройств без атрибуции](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration), или атрибутируются медиа-источнику и кампании при использовании [метода атрибуции](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration).
* **Ретаргетинг:** Реатрибуции и повторные вовлечения отображаются в обычном режиме.
* **Данные об активности:** Отображаются в обычном режиме.
* **Данные по удержанию и когортам:** По перенесенным устройствам нет записи об установке. Поэтому они не связаны с какой-либо когортой и не могут отображаться в отчетах «Удержание пользователей» и «Когорта».

<div id="note" />

> 📘 **Примечание:**
>
> Если приложение не будет открыто в течение 180 дней с даты миграции, все перенесенные данные устройства будут удалены. Следовательно, если приложение будет открыто по истечении 180 дней, будет зафиксирована новая установка.

</Accordion>

<div id="how-to-migrate-devices" />

<Accordion title="Как мигрировать устройства">

**Чтобы осуществить миграцию устройств:**

1. Решите, какую группу пользователей следует перенести. Вы можете перенести всех существующих пользователей (что может помешать вам получить точные данные повторной атрибуции от AppsFlyer) или пользователей, которые только недавно установили ваше приложение (что может привести к двойной оплате за пользователей, установивших его ранее).  
   **Мы рекомендуем переносить пользователей, активных в течение текущего периода окна реатрибуции.** Например, если окно реатрибуции вашего приложения составляет 90 дней, переносите тех пользователей, у которых за предыдущие 90 дней была хотя бы одна сессия.
2. [Необязательно] Попросите маркетолога/UA-менеджера приостановить текущие маркетинговые кампании (из SRN, не-SRN рекламных сетей, собственных медиа и т. д.) до завершения миграции устройств.  
   Если вы решите не приостанавливать кампании, перенесите все оставшиеся идентификаторы устройств из системы другого поставщика, как только обновленная версия приложения с SDK AppsFlyer будет выпущена в магазинах приложений.
3. Подготовьте CSV-файл на основе выбранной группы пользователей, используя структуру миграции [с атрибуцией](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) или [без атрибуции](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration). <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">См. пример CSV-файла</Anchor>
4. Отправьте CSV-файл своему менеджеру AppsFlyer.  
   Ваш CSM менеджер проведет миграцию идентификаторов устройств в AppsFlyer.

</Accordion>

<div id="attributed-migration" />

<Accordion title="Атрибутируемая миграция">

Для устройств, перенесенных в AppsFlyer с помощью этого метода, внутренние события и сессии регистрируются и отображаются в соответствии с медиа-источником, указанным предыдущим поставщиком атрибуции, и в соответствии с политиками хранения данных рекламных сетей.

<div id="attributed-device-migration-csv-structure" />

#### Структура CSV-файла для миграции устройств с атрибуцией

| Название  <br />столбца | Description(Описание) | Обязательно | Примеры |
| --- | --- | --- | --- |
| app\_id | Идентификатор приложения (App ID) в том виде, в каком он отображается на дэшборде AppsFlyer | Да | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| platform | Платформа устройства: ios или android | Да | <ul><li>ios</li><li>Android</li></ul> |
| device\_id | <ul><li>Android: gaid или android\_id,</li><li>iOS: IDFV (рекомендуется, если доступен) или IDFA</li><li>Не используйте одну и ту же комбинацию идентификатора устройства и идентификатора приложения в нескольких строках. Если происходит дублирование, используется последнее вхождение в файле.</li></ul> | Да | <ul><li>**gaid** (в нижнем регистре): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id** (в нижнем регистре): f35aea8908254891</li><li>**IDFV** (в верхнем регистре): A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (в верхнем регистре): 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android:<ul><li>advertiserId</li><li>android\_id</li><li>amazon\_aid</li></ul></li><li>iOS<ul><li>IDFA</li><li>IDFV</li></ul></li><li>В настоящее время другие идентификаторы (OAID, IMEI) не поддерживаются.<br />Используйте миграцию без атрибуции для пользователей Android, которые не из Google Play.</li></ul>**Примечание**<br />`android_id` по умолчанию не собирается SDK AppsFlyer. Если вы используете `android_id` в качестве идентификатора, обязательно <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">собирайте его при интеграции SDK</Anchor>. | Да | <ul><li>advertiserId</li><li>android\_id</li><li>IDFA</li><li>IDFV</li><li>amazon\_aid (строчными буквами): df07c7dc-cea7-4a89-b328-810ff5acb15d</li></ul> |
| install\_time | Время первоначальной установки приложения в формате <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor> UTC:  <br />**yyyy-mm-ddTHH:MM:SS.SSS** | Ни один | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>Выберите один из вариантов ниже:<ul><li>Идентификатор партнера AppsFlyer</li><li>Настраиваемый медиа-источник (не может быть идентификатором партнера).</li></ul></li><li>Чтобы получить список идентификаторов партнеров в соответствии с требованиями AppsFlyer:<ul><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">Включите всех соответствующих интегрированных партнеров.</Anchor></li><li>Запустите <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">API Get active integrations</Anchor>, чтобы получить список всех активных интеграций.</li><li>Используйте **media\_source\_name** из API в качестве значения **media\_source** в CSV.</li><li>Исключения:<ul><li>Для Apple Search Ads используйте **Apple Search Ads**.</li><li>Для Twitter используйте **twitter**.</li></ul></li></ul></li><li>Формат: значения чувствительны к регистру</li></ul> | Да | Неорганические: facebook\_int, googleadwords\_int<br /><br />Органические: organic |
| integrated\_partner | <ul><li>Указывает, является ли медиаисточник интегрированным партнером или нет. Имеется в виду органический или пользовательский медиаисточник.</li><li>Формат: значения чувствительны к регистру</li></ul> | Да | <ul><li>Да</li><li>Нет (если media\_source имеет значение custom)</li></ul> |
| кампания | Для более детальной атрибуции укажите исходное название кампании.<br /><br />форматирования ячеек с затратами; | Ни один |  |
| campaign\_id | Для более детальной атрибуции укажите исходный идентификатор кампании.<br /><br />Формат: строка без пробелов | Ни один |  |

**Правила для CSV-файла:**

* CSV-файл может содержать сведения об устройствах пользователей по нескольким приложениям.
* Не используйте одну и ту же комбинацию идентификатора устройства и идентификатора приложения в нескольких строках. Если происходит дублирование, используется последнее вхождение в файле.
* Должны быть включены все заголовки столбцов: app\_id, platform, device\_id, id\_type, install\_time, media\_source, integrated\_partner, campaign, campaign\_id. **Примечание**: Порядок полей важен и должен быть сохранен.
* По одному и тому же устройству можно добавить и IDFV, и IDFA, но они должны находиться в разных строках. В этих строках все поля, кроме device\_id, будут одинаковыми.
* Каждая строка должна содержать ровно 9 полей, разделенных запятыми.
* Оставьте необязательные поля пустыми.
* Файлы могут содержать до 5 млн строк.
* Если у вас несколько файлов, дайте каждому файлу уникальное имя.
* В качестве кодировки используйте UTF-8.
* [Необязательно] Сжимайте файлы с помощью ZIP или GZIP.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">См. образец CSV</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="Неатрибутируемая миграция">

Устройства, перенесенные в AppsFlyer с помощью этого метода, регистрируются (но не отображаются) как органические пользователи. Их данные о внутренних событиях и сессиях регистрируются и отображаются как органические.

<div id="non-attributed-device-migration-csv-file-structure" />

#### Структура CSV-файла для миграции устройств без атрибуции

| Вариант | Столбцы | Когда использовать | Пример |
| --- | --- | --- | --- |
| 1 | Идентификатор приложения + IDFA/GAID | <ul><li>Если у всех ваших пользователей Android есть идентификаторы GAID.</li><li>Только пользователи iOS</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png)](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png) |
| 2 | App ID + Device ID + Device ID type | <ul><li>Если у некоторых из ваших пользователей Android есть только IMEI или Android ID, но нет GAID (независимые площадки, версии Android ниже 4.4.2).</li><li>Android ID должен иметь шестнадцатеричный формат.</li></ul>**Примечание**:<ul><li>Используйте точно эти строки для столбца **ID type**: advertiserId (также поддерживается amazon\_aid), idfa, idfv, android\_id, imei.</li><li>Если вы используете android\_id или imei, и позднее AppsFlyer получит лучший идентификатор, может быть зарегистрирована новая атрибуция.</li><li>`android_id` и `imei` по умолчанию не собираются SDK AppsFlyer. Если вы используете любой из этих идентификаторов, обязательно <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">собирайте их при интеграции SDK</Anchor>.</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png)](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png) |

**Правила для CSV-файла:**

* CSV-файл может содержать сведения об устройствах пользователей по нескольким приложениям.
* Каждая строка содержит один идентификатор устройства для одного приложения.
* В зависимости от выбранного варианта структуры файла столбцы файла должны быть следующими (и в указанном порядке):
  * Вариант 1: app\_id,device\_id
  * Вариант 2: app\_id,device\_id,id\_type
* App ID в нижнем регистре
* Идентификаторы Android в нижнем регистре
* IDFA/IDFV в верхнем регистре
* Допускается до 25 млн строк

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">См. образец CSV</Anchor>

</Accordion>

<div id="campaign-migration" />

### Миграция кампаний

Переключите текущие маркетинговые кампании на AppsFlyer, чтобы активировать атрибуцию AppsFlyer и избежать двойной оплаты и потери данных атрибуции.

**Примечание**: Вы можете выбрать перенос только нескольких маркетинговых кампаний за один раз. Чтобы осуществить перенос нескольких кампаний, выделите их в сегмент по медиа-источнику (такому как рекламная сеть или агентство), гео или кампании.

<div id="srns" />

<Accordion title="SRN:">

SRN отвечают партнерам по измерению эффективности мобильной рекламы (MMP) на запросы об интеракциях конкретных устройств. Если два MMP, например AppsFlyer и конкурирующий поставщик системы атрибуции, запрашивают одну и ту же сеть SRN об установке на одно и то же устройство, это может повлечь двойную оплату.

**Чтобы мигрировать кампании в SRN**:

* Активируйте и настройте в AppsFlyer соответствующие <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns#srn-интегрированные-с-appsflyer">SRN</Anchor>.

<div id="note-1" />

> 📘 **Примечание:**
>
> * В SRN (кроме Meta Ads и Twitter) может быть запущено несколько MMP.
> * Meta Ads не может выполнять дедупликацию внутренних событий приложения.

</Accordion>

<div id="nonsrn-ad-networks" />

<Accordion title="Рекламные сети без собственной атрибуции (не относящиеся к SRN)">

Ссылки атрибуции рекламной сети регистрируют интеракции пользователей и впоследствии используются для атрибуции интеракций, которые становятся фактическими установками.

**Чтобы мигрировать кампании рекламных сетей без самостоятельной атрибуции (не относящиеся к SRN)**:

1. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">Активируйте</Anchor> соответствующие рекламные сети в AppsFlyer.
2. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">Сформируйте ссылки атрибуции AppsFlyer</Anchor> для каждой рекламной сети.
3. Замените имеющиеся ссылки в каждой вашей кампании на ссылки атрибуции AppsFlyer.

</Accordion>

<div id="owned-media" />

<Accordion title="Метрики заголовка">

К собственным медиа относятся ссылки атрибуции, используемые в следующих каналах:

* Использование функции "поделиться контентом"
* Вовлечение по всем платформам
* Электронная почта
* СМС
* Посты в социальных сетях
* Блоги
* Интернет-сообщества (например, Quora)
* и др.

Для этих кампаний AppsFlyer использует <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">ссылки OneLink</Anchor>. Ссылки OneLink перенаправляют пользователей с учетом их устройства в нужный магазин приложений, непосредственно в приложение или на веб-URL-адрес/целевую страницу.

**Чтобы изменить текущие ссылки собственных медиа на ссылки AppsFlyer OneLink**:

* Обратитесь к своему CSM, который поможет вам преобразовать ваши собственные медиассылки в ссылки OneLink в соответствии с используемыми вами в данный момент каналами и инструментами.

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

Для атрибуции SKAdNetwork (SKAN) обновлять значение конверсии может только один SDK. В противном случае данные SKAN станут бессмысленными. Поэтому убедитесь, что после миграции только SDK AppsFlyer обновляет значение конверсии SKAN.

<Anchor target="_blank" href="/marketers/ru/docs/skan-conversion-studio">Как настроить значение конверсии SKAN в AppsFlyer.</Anchor>

</Accordion>

<div id="data-report-setup" />

### Настройка отчетов по данным

<div id="adapt-and-map-report-structures" />

<Accordion title="Адаптация и сопоставление структур отчетов">

До миграции ваши системы сохраняют данные атрибуции, предоставляемые текущим поставщиком, в соответствии с настроенными для него структурами, полями и параметрами отчетов. Чтобы данные правильно отображались в AppsFlyer, необходимо адаптировать и сопоставить имеющиеся структуры отчетов со структурой, полями и параметрами отчета AppsFlyer.

**Чтобы адаптировать и сопоставить структуры отчетов:**

* Свяжитесь со своим менеджером AppsFlyer, чтобы быстро адаптировать и сопоставить структуры данных ваших отчетов от Adjust, Branch/Tune или Kochava с используемыми AppsFlyer.

</Accordion>

<div id="prepare-report-methods" />

<Accordion title="Настройка методов создания отчетов">

Вы можете получать данные отчетов из AppsFlyer в <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-apis">необработанном</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/analytics-and-aggregate-reporting-apis">агрегированном</Anchor> виде несколькими способами. Ознакомьтесь с доступными методами и настройте те, которые вам подходят.

Методы создания отчетов:

* Панели управления
* Экспорт отчетов
* push
* Pull API
* Отчет Data Locker

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BD%D0%B0-appsflyer-%D1%81-%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC 01H8EDSTP8N4GZJQ5J609C3DHM=%D0%BE-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BD%D0%B0-appsflyer-%D1%81-%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC compare-measurement-between-appsflyer-and-other-mmps=%D1%81%D1%80%D0%B0%D0%B2%D0%BD%D0%B8%D1%82%D0%B5-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-appsflyer-%D0%B8-%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D0%BC%D0%B8-mmp h_01HQJ10ZFJR43KBYMD9A07CJ99=%D1%81%D1%80%D0%B0%D0%B2%D0%BD%D0%B8%D1%82%D0%B5-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-appsflyer-%D0%B8-%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D0%BC%D0%B8-mmp tasks=%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F 01H8EDSTP8YGDZBPEY1976JP8C=%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F scope-of-work=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D1%80%D0%B0%D0%B1%D0%BE%D1%82 01H8EDSTP8HGCVHYX49GQQEHBB=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D1%80%D0%B0%D0%B1%D0%BE%D1%82 sdk-integration=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-sdk h_01F0RDXJ4F34DDKRFV5G6WZQX0=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-sdk 01H8EDSTP97C85X2E9EKBSVFQJ=sdk-integration::c763138b device-migration%E2%80%94optional=%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2--%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE h_01F0RDXVSQ13R9Q2KT7PK1KSCQ=%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2--%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE 01H8EDSTP9NDF6611MVEMWQSMZ=about-device-migration 01H8EDSTP93QJA4XZB6TDWWH1V=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 01JA2CAMW3HCHC4B9FX7517FJ6=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 01H8EDSTP9M2MDMGZ8QBQGPM6S=how-to-migrate-devices h_01F0RPWKQ4B0T1TXRGPVTYPPFB=attributed-migration attributed-device-migration-csv-structure=%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D0%B0-csv-%D1%84%D0%B0%D0%B9%D0%BB%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-%D1%81-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B5%D0%B9 01H8EDSTP9HABKEZJXMB84CDDE=%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D0%B0-csv-%D1%84%D0%B0%D0%B9%D0%BB%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-%D1%81-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B5%D0%B9 h_01KV852C6CGBHSB6EFY122DRQY=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01F0RPX3SJ391M8SPNNN50DDA8=nonattributed-migration nonattributed-device-migration-csv-file-structure=%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D0%B0-csv-%D1%84%D0%B0%D0%B9%D0%BB%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-%D0%B1%D0%B5%D0%B7-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H8EDSTP9AFDMQS6BPQJY19ZH=%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D0%B0-csv-%D1%84%D0%B0%D0%B9%D0%BB%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2-%D0%B1%D0%B5%D0%B7-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 campaign-migration=%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 h_01F0RDY9WPSBZVP3B7XN3ZEJKK=%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 01H8EDSTP94KSE1J4J5B7HX96Z=srns 01H8EDSTP9ZGMHSM44BWGF1FJN=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 01H8EDSTP981XVWVM2NE0A45RM=nonsrn-ad-networks 01H8EDSTP9XNJA80Z5XR7WR9QN=owned-media 01H8EDSTP9Q8JAPNXSQWSHSK32=skan data-report-setup=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC h_01F0RDYKYHAEZ65GZBZ3MWTB5Z=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC 01H8EDSTP91E934EDXTPXW2ARJ=adapt-and-map-report-structures 01H8EDSTPAF8H5ESHDVK42M0RB=prepare-report-methods" />

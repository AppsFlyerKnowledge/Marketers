---
title: Измеряйте вовлеченность после просмотра
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2026-08-18T00:10:32Z'
  id: 210084473
  locale: ru
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ru/articles/210084473
---
> **Краткий обзор.** В отношении пользователя, который просмотрел рекламу (показ) и впоследствии установил приложение, применяется атрибуция по просмотрам.

<div id="overview" />

## Обзор

Атрибуция по просмотрам измеряет установки, реатрибуцию и повторное вовлечение пользователей, которые просматривали рекламу, но не нажимали на нее.

<div id="view-through-attribution-flow" />

### Процесс атрибуции по просмотрам

![Retargeting_-_View-through__1_.png](https://files.readme.io/86d32778a8a0966499a0c5c91c1b2d8aed6d5bb24214b1a32fd484779c105a98-4412917609489.png)

<div id="terminology" />

### Терминология

* **Показ:** просмотр рекламы пользователем независимо от наличия клика и других взаимодействий пользователя с рекламой.
* **Установка**: в данной статье это понятие включает установки, реатрибуции и повторные вовлечения.
* **Атрибуция по просмотрам:** атрибуция установок медиа-источнику после показа рекламы пользователю.

<div id="view-through-attribution-principles" />

### Принципы атрибуции по просмотрам

* Поддерживаются как <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#device-id-matching">сопоставление идентификаторов устройств</Anchor>, так и <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">вероятностное моделирование</Anchor> (<Anchor target="_blank" href="/marketers/ru/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">необходимо включить</Anchor>).
* Поддерживается партнерами, указанными в [списке партнеров с атрибуцией по просмотрам](/docs/measure-view-through-engagements#view-vta-partner-list).

Показы учитываются при атрибуции по просмотрам на основе следующих принципов:

* Показ произошел в течение окна атрибуции по просмотрам (по умолчанию 24 часа).
* Если обнаружено несколько показов, учитывается последний показ.
* Клики имеют приоритет перед показами. Это означает, что если в рамках окна атрибуции есть клики, учитывается последний клик. Самый последний показ регистрируется как ассистент.

<div id="view-through-lookback-window" />

### Окно атрибуции по просмотрам

* Для сетей без самостоятельной атрибуции (не-SRN) окно атрибуции по просмотрам составляет 1–24 часа. Для SRN окно атрибуции может быть более продолжительным.
* Чтобы задать окно:
  * **Не-SRN**: установите продолжительность с помощью ссылок атрибуции просмотров, задав параметр `af_viewthrough_lookback`. Если параметр не задан, используется окно атрибуции по умолчанию в 24 часа.
  * **SRN**: Окно определяется в SRN. Рекомендуем установить в AppsFlyer то же значение, что и у SRN.

<div id="view-through-attribution-reporting-and-metrics" />

### Отчеты и показатели атрибуции по просмотрам

* **Агрегированные данные**: рекламные сети передают в AppsFlyer агрегированные данные о показах через API или по каждому показу. Обратите внимание, что подсчет показов и отчетность определяется каждым партнером индивидуально. Связанные метрики доступны на обзорном дэшборде и через другие инструменты отчетности. Доступные показатели:
  * Показы: количество показов за период.
  * Просмотры: количество установок, атрибутированных по показам.
* **Сырые данные**:
  * Данные уровня пользователя (сырые данные) по пользователям, атрибутированным по просмотрам, доступны аналогично данным пользователей, атрибутированных по кликам. Некоторые партнеры ограничивают доступность таких данных.
  * Доступны данные по показам (аналогично данным по кликам).
  * Поле attributed\_touch\_type содержит значение *impression* (показы).

<div id="view-through-operations" />

## Настройка атрибуции по просмотрам

<div id="set-impression-links" />

<Accordion title="Настройка ссылок для отслеживания показов">

Рекламные сети отправляют в AppsFlyer ссылки для отслеживания показов, которые содержат данные о кампании и другие сведения, аналогичные включаемым в <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">ссылки атрибуции</Anchor> для отслеживания кликов.

Ссылки отправляются в реальном времени, поэтому, если за показом последовала установка, она будет атрибутирована правильно.

При подготовке ссылок обратите внимание на следующее:

* Базовый URL-адрес — `http://impression.appsflyer.com`.
* Используйте запрос GET.
* Включите идентификаторы устройств, такие как IDFA, GAID, IDFV, если они доступны.
* Добавьте параметры <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling-parameters-for-ad-networks">вероятностного моделирования</Anchor>.
* Для повышение надежности значения Device ID можно хэшировать по алгоритму SHA1. Имя параметра должно начинаться с префикса "sha1\_", за которым следуют имя параметра и хэшированное значение, например: sha1\_idfa, sha1\_advertising\_id, sha1\_android\_id, sha1\_imei.

> 📄
>
>  Пример
>
> ```http
> http://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
> &af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
> &af_sub1={free value}&idfa={idfa value}
> ```

</Accordion>

<div id="set-custom-impression-links" />

<Accordion title="Создание настраиваемых ссылок для отслеживания показов">

Рекламодатели используют ссылки атрибуции для отслеживания показов со своими собственными медиа-источниками, например с баннерами сайта.

Когда рекламодатели <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">создают настраиваемые ссылки атрибуции</Anchor>, они получают полные ссылки для отслеживания показов, которые можно запускать при каждом взаимодействии пользователя с их рекламой.

Настраиваемые ссылки для отслеживания показов (созданные через OneLink) также можно использовать для атрибуции по просмотрам посетителей мобильной версии сайта. Узнайте больше <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">о создании настраиваемых ссылок для отслеживания показов</Anchor>.

</Accordion>

<div id="turn-off-viewthroughattribution" />

<Accordion title="Отключение атрибуции по просмотрам">

По умолчанию атрибуция по просмотрам включена. Если AppsFlyer получает действительную ссылку атрибуции показов, этот показ используется в процессе атрибуции.

Поскольку атрибуция по просмотрам включена по умолчанию, рекламодателям нужно заранее договориться с сетью о том, включать или нет атрибуцию по просмотрам.

Атрибуцию по просмотрам можно отключить для каждого медиа-источника. При этом, если поступают данные о показах, а атрибуция по просмотрам отключена:

* Метрики по просмотрам доступны на дэшборде.
* Процесс атрибуции игнорирует эти показы.

**Чтобы отключить атрибуцию по просмотрам:**

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите интегрированного партнера.
3. На вкладке интеграции отключите **атрибуцию установок по просмотрам**.
4. Нажмите **Сохранить интеграцию**.

Для SRN: отключение атрибуции по просмотрам в AppsFlyer не влияет на соответствующие настройки сетей с самостоятельной атрибуцией. Во избежание несоответствий следите за тем, чтобы настройки атрибуции по просмотрам в AppsFlyer совпадали с настройками в сетях.

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HEMT7T1TB9W7ZBRPQW29SRPF=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 viewthrough-attribution-flow=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HEMT7T1T6ZK4ZH7DKV3162J1=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC terminology=%D1%82%D0%B5%D1%80%D0%BC%D0%B8%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F h_01HEMT7T1TY46QXBDS6MBF1DZ5=%D1%82%D0%B5%D1%80%D0%BC%D0%B8%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F viewthrough-attribution-principles=%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF%D1%8B-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HEMT7T1THD8TVKRRJ168HKY2=%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF%D1%8B-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC viewthrough-lookback-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HEMT7T1TWHN2AB3Q5X36TKKB=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC viewthrough-attribution-reporting-and-metrics=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%B8-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HEMT7T1TQNKM5GABA7VY6KR1=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D0%B8-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC viewthrough-operations=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HEMT7T1T13JC75ZYY01N8PS6=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HEMT7T1TQ3YNQ2Y0CCGPXWDX=set-impression-links h_01HEMT7T1T75MBS64JE837CJ0E=set-custom-impression-links h_01HEMT7T1T253G1CZNS9KVDFCP=turn-off-viewthroughattribution" />

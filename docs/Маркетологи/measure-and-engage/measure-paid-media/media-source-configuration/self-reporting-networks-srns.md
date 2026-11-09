---
title: Сети с самостоятельной отчетностью (SRN)
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Ad Networks
    - srn
    - Self-reporting
    - networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-10-22T05:21:45Z'
  edited_at: '2026-08-18T00:31:04Z'
  id: 360001546905
  locale: ru
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ru/articles/360001546905
---
> **Краткий обзор:** Узнайте о сетях с самостоятельной отчетностью (SRN) — Атрибуция, диплинкинг, особенности для iOS и часто задаваемые вопросы.

<div id="srns-integrated-with-appsflyer" />

## SRN, интегрированные с AppsFlyer

| **СРН** | **Логотип** |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ru/docs/amazon-ads-campaign-configuration">Реклама Amazon</Anchor> | <Image alt="amazon-ads-logo.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" width="134px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/apple-ads-integration-setup">Apple Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/iossearchads.png" width="131px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers">Google Реклама</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png?v=1" width="47px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/google-marketing-platform-display-video-360-dv360-integration">Google Маркетинговая платформа</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png?v=1" width="45px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup">Meta реклама</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png?v=1" width="67px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/roku-integration-with-appsflyer">Roku</Anchor> | <Image alt="roku.png" src="https://files.readme.io/4909a45e611700e5c2a69f94710226e65e10faf620e3a7939a2c038bea1736ca-33565070184337.png" width="150px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/snapchat-advanced-srn-integration-setup">Snapchat — расширенный SRN</Anchor> | <Image alt="snapchat_logo.png" src="https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png" width="41px" /> |
| Социальная реклама Tencent | <Image alt="blobid0.jpg" src="https://files.readme.io/6d6e9661c9d81f80ffeedfdf4850a84f3cc183faa49a514d1d3bb116641738da-32259428896017.jpg" width="80px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok для бизнеса — расширенный SRN</Anchor> | ![TTFB_logo__4C_horizontal_black.png](https://files.readme.io/caa8c9e02b161eea10740cb79f26d04d3324e87b9cfd929281374d2d7936ef2e-32259428903953.png) |
| <Anchor target="_blank" href="/marketers/ru/docs/x-ads-formerly-twitter-ads-setup-guide-overview">Twitter</Anchor> | <Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="37px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/yahoo-integration-setup">Yahoo (Oath: Рекламные платформы \/ Yahoo Gemini)</Anchor> | <Image alt="verizonmedia.png" src="https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png" width="76px" /> |
| <Anchor target="_blank" href="/marketers/ru/docs/yahoo-japan-search-ads-campaign-configuration">Yahoo! Поиск рекламы</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoojapansearch.png" width="139px" /> |

**Примечание:** У SRN есть <Anchor target="_blank" href="/marketers/ru/docs/user-level-data-retention">ограничения на использование и удержание данных на уровне пользователя.</Anchor>

<div id="attribution" />

## Атрибуция

Несхожий с не-SRN (рекламные сети), которые используют ссылки для атрибуции событий в AppsFlyer, SRN исполняют самоатрибуцию с использованием идентификатора устройства при получении уведомления об установке от AppsFlyer. Для приложений iOS для атрибуции используется <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">SKAN</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">фреймворк Aggregated Advanced Privacy</Anchor>.

Атрибуция AppsFlyer для SRN и не-SRN основывается на:

* Методологии последнего касания и мультитач.
* Стандартная логика атрибуции AppsFlyer для последовательности данных о показах и кликах.

<div id="how-does-attribution-work-with-srns" />

### Как работает атрибуция с SRN?

SRN отчет о событиях, таких как новые установки и события в приложении, отправляет в AppsFlyer следующим образом:

* Использование API для связи с поставщиками атрибуции и измерения.
* Когда сторонние поставщики атрибуции обнаруживают установку, они отправляют запрос в сеть, используя рекламный идентификатор.
* Отчет с подробностями о любых значимых кликах или показах рекламы.

После выполнения атрибуции AppsFlyer, внутренние постбэки отправляются в SRN на протяжении <Anchor target="_blank" href="/marketers/ru/docs/user-level-data-retention#установленные-партнерами-сроки-хранения-данных">периода удержания данных партнера</Anchor>.

<div id="how-does-attribution-work-with-advanced-srns" />

### Как работает атрибуция с расширенными SRN?

Расширенные SRN поддерживают те же методы атрибуции, что и стандартные SRN. Однако расширенные SRN могут атрибутировать вовлечения даже при отсутствии идентификатора устройства (IDFA), используя фреймворк <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-knowledge-base-glossary#агрегированная-расширенная-конфиденциальность">Aggregated Advanced Privacy</Anchor>. В зависимости от сети это может включать атрибуцию на основе рекламного идентификатора при наличии двойного согласия или моделирование измерения кампании на основе данных о кликах и показах.

<div id="install-attribution" />

### Атрибуция установок

Потенциальные пользователи приложения видят и взаимодействуют с несколькими рекламами, прежде чем установить приложение. Как правило, поставщики атрибуции предлагают рекламодателям атрибуцию последнего касания, которая приписывает установку к последнему клику, сделанному перед фактической установкой.

При первом запуске приложения:

* AppsFlyer убеждается, что:
  * Приложение настроено на получение трафика от SRN.
  * У пользователя есть идентификатор рекламодателя.
* Если оба условия соблюдаются, AppsFlyer запрашивает SRN, используя идентификатор рекламодателя.
* AppsFlyer выполняет атрибуцию после анализа заявок SRN.

<div id="install-attribution-examples" />

#### Примеры атрибуции установок

<div id="example-a-assisted-attribution" />

<Accordion title="Пример A: Вспомогательная атрибуция">

<Image align="center" alt="SRN_1.png" src="https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png" />

**Понедельник:** Сеть A сообщает о клике пользователя.

**Вторник:** Сеть B сообщает о вовлечении с видео.

**Среда:** Сеть C сообщает о клике по интерактивной рекламе, и через 30 минут происходит установка.

**AppsFlyer** приписывает установку сети C и признает вклад сетей A и B за их помощь в установке.

AppsFlyer предоставляет рекламодателям данные о вспомогательной активности (взаимодействия, не связанные с атрибуцией, но происходящие до установки). Это позволяет рекламодателям настраивать свои мультитач или фракционные модели атрибуции. Для получения дополнительной информации см. <Anchor target="_blank" href="/marketers/ru/docs/measure-assisted-installs">Объяснение Вспомогательные установки (ассисты)</Anchor>.

</Accordion>

<div id="example-b-last-click-attribution" />

<Accordion title="Пример B: Атрибуция последнего клика">

<Image align="center" alt="SRN_2.png" src="https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png" />

**Сеть D** (SRN) сообщает о клике за несколько минут до сети C.

**Сеть C** использует стандартную интеграцию атрибуции.

**AppsFlyer** приписывает установку сети C, так как именно она совершила последний клик.

</Accordion>

<div id="attribution-windows" />

### Окна атрибуции

Окна атрибуции включают в себя лукбэк и просмотр. Некоторые SRN взимают с рекламодателей плату за установку на основе стоимости за показ (CPM) и стоимости за действие (CPA), которые рассчитываются по кликам или показам в течение периода от 1 до 28 дней.

**AppsFlyer** атрибутирует установки, активность, эффективную стоимость за установку (eCPI) и эффективную стоимость за действие (eCPA) на основе предпочитаемой рекламодателем методологии атрибуции и окон лукбэк.

**Рекламодатели**, возможно, будут платить за установки на основе окон ретроспективной атрибуции (лукбэк) SRN и моделей просмотра.

* Рекламодатели ожидают, что универсальная сторонняя методология атрибуции AppsFlyer позволит им оптимизировать и распределить их рекламные расходы.
* Почему? Потому что AppsFlyer сообщает фактические eCPI и eCPA на основе условий, определенных рекламодателем.
* SRN могут извлечь краткосрочную выгоду, поскольку часто сами определяют условия оплаты. Тем не менее, рекламодатели исправляют это, пользуясь услугами сторонних поставщиков атрибуции.

<div id="deep-linking-with-srns" />

## Диплинкинг с SRN

Чтобы пользователи открывали ваше Приложение при клике на ссылку, вам нужно лишь настроить App Links/глобальные ссылки/схему URI. Однако для выполнения диплинкинга или отложенного диплинкинга к конкретной странице или активности в вашем приложении SRN используют собственные методы — без задействования метода диплинкинга AppsFlyer.

Так как же можно организовать диплинкинг для пользователей и получить актуальные данные из SRN?

<div id="direct-deep-linking" />

<Accordion title="Прямой диплинкинг">

Когда устройство пользователя выполняет диплинкинг, прямой диплинкинг с SRN осуществляется без вызова метода диплинкинга AppsFlyer. В приведенном ниже примере существующие пользователи, нажимающие на рекламу, перенаправляются к активности напрямую с помощью методов Facebook, тогда как новые пользователи получают тот же опыт с использованием данных о конверсиях AppsFlyer. Узнайте, как <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-faq#who-needs-facebooks-sdk">Meta реклама использует OneLink для диплинкинга</Anchor>

<div id="example" />

> 📄 **Пример**
>
> Джилл, мобильный маркетолог приложения «greatapp», решает запустить кампанию по диплинкингу в Meta ads, ориентированную на широкую аудиторию. Кампания перенаправляет всех кликнувших пользователей на «бонусную» активность.
> Джек, разработчик мобильных приложений, добавляет эту логику после получения данных о конверсиях:
>
> 1. Происходит ли это из Facebook («is\_fb=true»)?
> 2. Если да, получите значение параметра группы объявлений.
> 3. Если значение содержит слово «бонус», перенаправьте пользователя на «бонусную» активность.

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Отложенная глубинная ссылка (диплинкинг)">

В отличие от диплинкинга, отложенный диплинкинг с SRN возможен с использованием API AppsFlyer GCD.  После первого запуска приложения AppsFlyer получает данные о конверсии и предоставляет их приложению. Используя данные о конверсии, можно перенаправить в нужный раздел приложения новых пользователей, которые выполняют установку после клика по диплинку или в рамках ретаргетинговой кампании в SRN-сети.

Отложенный диплинкинг поддерживается для Google Ads, Meta (при условии, что в приложении установлен FB SDK), Snapchat и TikTok for Business с использованием фактического значения диплинка, которое можно запросить через GCD с помощью поля `af_dp`. В случае с TikTok для бизнеса это значение также можно получить из поля `deep_link_value`.

Однако в других SRN обычные параметры диплинкинга AppsFlyer не присутствуют в данных диплинка. Чтобы использовать эти данные в приложении, разработчику необходимо применять дополнительную логику на основе доступных параметров, таких как кампания, набор объявлений или отдельные названия объявлений.

</Accordion>

<div id="ios-implications" />

## Влияние на iOS

Большинство SRN поддерживают SKAdNetwork и имеют необходимую интеграцию с AppsFlyer.

<div id="ios-145-srn-attribution" />

<Accordion title="Атрибуция SRN для iOS 14.5">

Начиная с iOS 14.5, когда пользователи дают согласие ATT как в приложениях рекламодателя, так и издателя (<Anchor target="_blank" href="/marketers/ru/docs/appsflyer-knowledge-base-glossary#двойное-согласие">двойное согласие</Anchor>), установки SRN, которые отмечены на <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">дэшборде SKAdNetwork</Anchor>, также отображаются на традиционных дэшбордах.

<div id="note" />

> 📘 **Примечание:**
>
> * Традиционный дэшборд показывает снижение числа установок, приписываемых SRN. При оценке эффективности SRN используйте <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">дэшборд SKAdNetwork</Anchor>. Ожидается уменьшение количества установок, приписываемых SRN, с соответствующим увеличением органических установок. Однако для продвинутых SRN воздействие будет менее значительным, поскольку они также атрибутируют взаимодействия, даже если отсутствует идентификатор устройства.
> * Дэшборд <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAdNetwork</Anchor> обновляется с задержкой в 48–72 часа после установок.
> * Установки, полученные через Apple Search Ads (ASA), не атрибутируются на дэшборде SKAdNetwork.

</Accordion>

<div id="sending-event-postbacks-to-srns" />

<Accordion title="Отправка постбэков о событиях к SRN">

SRN, получающие постбэки о событиях, полагаются на включение идентификатора устройства в постбэк. Это позволяет SRN самостоятельно приписывать действия пользователей, о которых сообщается. Многие пользователи iOS 14 не дают своего согласия, что означает, что они не разрешают доступ к идентификатору устройства (IDFA). В этом случае вы должны ожидать:

* Уменьшение количества постбэков о событиях, отправляемых в SRN
* Несоответствия в количестве постбэков о событиях между SRN и AppsFlyer, которые регистрируют все события.

<div id="note-1" />

> 📘 **Примечание:**
>
> * Если IDFA отсутствует, постбэки для установок, открытий приложения или событий в приложении не отправляются в SRN. [Однако, в некоторых случаях AppsFlyer отправляет постбэки в SRN даже при отсутствии рекламного идентификатора](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid).
> * Кликовые рекламные сети не затрагиваются, так как они используют собственные идентификаторы транзакций, а не идентификаторы устройств, для самостоятельной атрибуции информации о событиях постбэка.

</Accordion>

<div id="faq" />

## Вопросы и ответы

<div id="how-does-retargeting-work-with-srns" />

<Accordion title="Как работает ретаргетинг с SRN?">

Ретаргетинговые клики от не-SRN легко определяются по наличию параметра `is_retargeting=true` в ссылке атрибуции ретаргетинга.  
Для SRN такого указания нет. Вместо этого, чтобы обеспечить атрибуцию повторных вовлечений от SRN, AppsFlyer использует другую логику:

* Предварительные условия:
  * На странице **Настройки приложения** включите **Включение ретаргетинга**.
  * На странице **Активные интеграции** выберите SRN и включите **Ретаргетинг**.
* При каждом запуске приложения AppsFlyer запрашивает у SRN данные о недавних вовлечениях идентификатора устройства с рекламными кампаниями для приложения.
  * Если SRN возвращает данные о вовлечении, AppsFlyer проверяет, что вовлечение находится в пределах окна лукбэк и превышает минимальное время между повторными вовлечениями.
  * Подтвержденные вовлечения регистрируются как повторные и атрибутируются к SRN.

</Accordion>

<div id="what-is-srn-mistargeting" />

<Accordion title="Что такое неправильное таргетирование SRN?">

Кампании SRN должны быть нацелены на определенную аудиторию, но это не всегда происходит: Непользователи в кампаниях по привлечению пользователей и существующие пользователи в ретаргетинговых кампаниях.

Если SRN используется для запуска кампаний по привлечению пользователей и ретаргетинговых кампаний, это может привести к неправильному таргетированию. В результате вы платите за ненужный трафик.

**Сценарий:** SRN на платформе AppsFlyer активирован для кампании по привлечению пользователей.

* После каждого запуска приложения AppsFlyer запрашивает SRN, проверяя, было ли у рекламного идентификатора (пользователя) недавнее вовлечение.
* Если да,
  * SRN отвечает названием кампании.
  * AppsFlyer определяет, был ли это первый запуск или нет и соответствующим образом присваивает атрибуты:  
    **Первый запуск**: Новая установка приписывается к кампании.  
    **Второй или последующий запуск**: Событие ретаргетинга связано с кампанией.

**Вывод:** Получение событий ретаргетинга из кампании по привлечению пользователей — это расточительно.

<div id="is-mistargeting-a-problem" />

#### Является ли неправильное направление таргетинга проблемой?

Аналитики данных AppsFlyer проверили кампании по **привлечению пользователей** через Meta реклама в течение определенного месяца.

* Ретаргетинг был включен.
* В 30% кампаний не менее 15% целевых пользователей были уже существующими пользователями приложения.
* В 5% кампаний не менее 40% были уже существующими пользователями приложения.
* **Вывод: В кампаниях SRN по привлечению пользователей 1 из 10 целевых пользователей уже является существующим пользователем.**

<Image align="center" alt="mistargeted_users.png" src="https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png" />

<div id="solving-the-mistargeting-problem" />

#### Решение проблемы неверного таргетинга

**Основное решение:** Не включайте существующих пользователей приложения в кампанию по привлечению пользователей.

* SRN будет ориентироваться только на потенциальных новых пользователей.
* **Максимизирует результаты привлечения новых пользователей при том же бюджете**.
* Периодически (и вручную) обновляйте кампанию, например, раз в месяц.
* Однако временные разрывы означают, что существующие пользователи могут стать объектом кампаний по привлечению в течение первого месяца после установки приложения.

<Anchor target="_blank" href="/marketers/ru/docs/audiences-guide">**Аудитории**</Anchor>, функция категории "Премиум" от AppsFlyer, позволяет вам автоматически ежедневно отправлять любой сегмент вашей пользовательской базы в десятки рекламных сетей.

Исследования AppsFlyer показывают, что исправление неверного таргетинга может существенно повлиять на ваши маркетинговые и пользовательские усилия.

</Accordion>

<div id="why-is-the-original-url-field-empty-in-raw-data-reports" />

<Accordion title="Почему поле «Исходный URL-адрес» пустое в отчетах о необработанных данных?">

Клик выполняется в среде SRN, но без ссылки атрибуции от AppsFlyer. Поэтому данные исходного URL-адреса, связанные с кликом, недоступны AppsFlyer.

</Accordion>

<div id="dashboard-doesnt-show-srn-clicks-and-impressions" />

<Accordion title="Дэшборд не показывает клики и показы SRN">

Клик выполняется в среде SRN, но без ссылки атрибуции от AppsFlyer. Поэтому некоторые SRN не предоставляют AppsFlyer данные о кликах и показах.

<Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta реклама</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-cost-and-ad-revenue">Google</Anchor> предоставляют AppsFlyer некоторые обобщенные данные.

</Accordion>

<div id="can-agencies-configure-srn-campaigns" />

<Accordion title="Могут ли агентства настраивать кампании SRN?">

Да, <Anchor target="_blank" href="/partners/ru/docs/about-agency-accounts#рекламные-сети-с-автоматической-отчетностью">см. здесь о конфигурации SRN Агентствами</Anchor>.

</Accordion>

<div id="does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />

<Accordion title="Отправляет ли AppsFlyer постбэки об отсутствующих рекламных идентификаторах (IDFA/GAID)?">

Если рекламные идентификаторы содержат пустую строку («») или показывают значение «00000000-0000-0000-0000-000000000000» (обнуленные IDFA), AppsFlyer не отправляет постбэки для установок, открытий приложений или событий в приложении, за исключением следующих сценариев:

* Google Реклама: В рамках интеграции для измерения ремаркетинга с Google Ads, когда несогласованный пользователь iOS открывает Приложение или выполняет внутреннее событие приложения, AppsFlyer отправляет `gbraid` и информацию о событии в Google Ads (для события `additional_data_json`).
* Google Реклама: На Android, если идентификатор устройства отсутствует, но ценность, значение реферера содержит `gclid` (для установок) или событие повторного вовлечения содержит Глубокий ссылка с параметром `gclid`, AppsFlyer отправляет `gclid` и информацию о событии в Google Ads.
* Meta: Файлы cookie Facebook или идентификаторы кампании (по Глубокий ссылка или предыдущему повторному вовлечению) или переключатель AEM включен.
* Snapchat и <Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business—Advanced SRN</Anchor>: если установка атрибутирована Snapchat или TikTok с помощью вероятностного моделирования и поступает событие в приложении, связанное с этой установкой, отправляется постбэк.

**Параметр** Google Рекламы: **Агрегированный идентификатор, сгенерированный Google, который идентифицирует группу Устройства и на который ссылается Глубокий ссылка.**

**Идентификатор клика Google (параметр  ):**  Параметр, передаваемый в URL-адрес с кликами по рекламе, который идентифицирует кампанию и другие атрибуты клика, связанные с рекламой. Это используется для отслеживания рекламы и атрибуции кампании.

</Accordion>

<div id="are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />

<Accordion title="Доступны ли клики и показы из SRN (сетей с самостоятельной атрибуцией) в отчётах о сырых данных?">

Нет, клики и показы из SRN не отображаются в отчётах о сырых данных. Хотя данные SRN используются для атрибуции, сырые данные о кликах и показах в отчёты не включаются. Это относится ко всем SRN, включая TikTok, Snap, Meta и Google.

</Accordion>

<div data-zendesk-anchors="srns-integrated-with-appsflyer=srn-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D1%81-appsflyer h_01HFM2MET40AFB84AW5N8GKWF3=srn-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D1%81-appsflyer attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F h_01HFM2MET4ZNKEZBT3S74N8CMC=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F how-does-attribution-work-with-srns=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-srn h_01HFM2MET42R6C87XB5RWX9ABJ=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-srn how-does-attribution-work-with-advanced%E2%80%94srns=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-srn h_01HFM2MET4Q6WCSANH18VTGBQX=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%81-%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-srn install-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA h_01HFM2MET4YQGN3GZKTTBRQ4HK=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA install-attribution-examples=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA h_01HFM2MET40Y9V8YGA20CCGVNN=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA h_01HFM2MET47BP3T07NTRVDWSJ3=example-a-assisted-attribution h_01HFM2MET4FY6SRS534NEA25WV=example-b-last-click-attribution attribution-windows=%D0%BE%D0%BA%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HFM2MET4ZJF290QNE3TPXQMA=%D0%BE%D0%BA%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 deep-linking-with-srns=%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3-%D1%81-srn h_01HFM2MET4ZA6WD6HX92JNFW7X=%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3-%D1%81-srn h_01HFM2MET4VZX943736W52V0ZJ=direct-deep-linking h_01HFM2MET4HSVHM0Q1C8D5Z279=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01HFM2MET4WGVMRJW7NJ7TF8GQ=deferred-deep-linking ios-implications=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-ios h_01HFM2MET4DGERZJ18A7CEFDS9=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-ios h_01HFM2MET4SRX0YRZRMHBY6DKT=ios-145-srn-attribution h_01HFM2MET471M5J2XFE7G2Z6J3=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HFM2MET42KNAMWE9S9BSF4PK=sending-event-postbacks-to-srns h_01HFM2MET4WJ6TMTXM03NFFCAG=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 faq=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B h_01HFM2MET49FZ8QHDMA7H92BTE=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B h_01HFM2MET4VYGPWR98HMAWK4YP=how-does-retargeting-work-with-srns h_01HFM2MET4JGYTW6P1VGYMYGFS=what-is-srn-mistargeting is-mistargeting-a-problem=%D1%8F%D0%B2%D0%BB%D1%8F%D0%B5%D1%82%D1%81%D1%8F-%D0%BB%D0%B8-%D0%BD%D0%B5%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D1%8C%D0%BD%D0%BE%D0%B5-%D0%BD%D0%B0%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0-%D0%BF%D1%80%D0%BE%D0%B1%D0%BB%D0%B5%D0%BC%D0%BE%D0%B9 h_01HFM2MET4C1HMWH715XP42ZAQ=%D1%8F%D0%B2%D0%BB%D1%8F%D0%B5%D1%82%D1%81%D1%8F-%D0%BB%D0%B8-%D0%BD%D0%B5%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D1%8C%D0%BD%D0%BE%D0%B5-%D0%BD%D0%B0%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0-%D0%BF%D1%80%D0%BE%D0%B1%D0%BB%D0%B5%D0%BC%D0%BE%D0%B9 solving-the-mistargeting-problem=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%BE%D0%B1%D0%BB%D0%B5%D0%BC%D1%8B-%D0%BD%D0%B5%D0%B2%D0%B5%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 h_01HFM2MET41CDCP8VNGR39YMCK=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%BE%D0%B1%D0%BB%D0%B5%D0%BC%D1%8B-%D0%BD%D0%B5%D0%B2%D0%B5%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 h_01HFM2MET4DETEHT8PACHS6C6B=why-is-the-original-url-field-empty-in-raw-data-reports h_01HFM2MET48Y4ATGB1HNDGSFEP=dashboard-doesnt-show-srn-clicks-and-impressions h_01HFM2MET4JEA8BBGN564CQPYX=can-agencies-configure-srn-campaigns h_01HFM2MET42V7AVV2BPZGDRARV=does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid h_01JMJ79S862T4M96ECZPVRZVJJ=are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />

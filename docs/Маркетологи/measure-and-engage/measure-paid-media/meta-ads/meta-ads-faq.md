---
title: Вопросы и ответы по Meta Ads
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
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
  created_at: '2021-11-09T10:04:49Z'
  edited_at: '2026-08-18T00:31:22Z'
  id: 4410472805649
  locale: ru
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ru/articles/4410472805649
---
> **Краткий обзор:** Ответы на часто задаваемые вопросы об использовании Meta Ads в AppsFlyer.

<div id="meta-ads-faq" />

## Вопросы и ответы по Meta Ads

<div id="i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard" />

<Accordion title="На дэшборде AppsFlyer не отображаются данные о кликах для кампании в Meta Ads">

По умолчанию Meta Ads предоставляет только данные о конверсиях и вовлечении. Тем не менее, вы можете настроить <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#cost-clicks-and-impressions">кампании Meta Ads для получения данных о кликах, показах и расходах</Anchor>.

</Accordion>

<div id="can-appsflyer-show-the-campaign-level-and-ad-groups" />

<Accordion title="Можно ли увидеть в AppsFlyer данные уровня кампании и групп объявлений?">

Да. В AppsFlyer отображаются еще и данные уровня объявления, так что вы можете использовать 3 уровня детализации данных рекламной кампании в Meta: кампании>> группы объявлений >> объявления.

</Accordion>

<div id="is-facebook-data-shown-in-realtime" />

<Accordion title="Отображаются ли данные Meta Ads в режиме реального времени?">

Да, все установки и последующие внутренние события приложения отображаются в режиме реального времени. Однако данные о кликах, показах и расходах AppsFlyer получает от Meta Ads в агрегированном виде с интервалом в несколько часов.

</Accordion>

<div id="when-can-i-see-a-new-campaigns-data-on-appsflyer" />

<Accordion title="Когда я смогу увидеть в AppsFlyer данные новой кампании?">

Данные, полученные от новых объявлений, блоков рекламы и кампаний в Meta Ads, можно увидеть только после выполнения хотя бы одной установки.

Например, новое объявление получило 100 кликов, не принесло ни одной установки, поэтому оно не отображается в AppsFlyer ни на дэшборде, ни в данных. По другому объявлению был только 1 клик, но была выполнена 1 установка, поэтому оно отображается в AppsFlyer.

</Accordion>

<div id="how-can-i-get-more-installs-from-facebook" />

<Accordion title="Как увеличить количество установок из Meta Ads?">

Если для кампаний в Meta Ads активировать ретаргетинг, то можно бесплатно получить на 100% больше установок в своих кампаниях по привлечению пользователей!  
Как? Читать <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns#what-is-srn-mistargeting">здесь</Anchor>.

</Accordion>

<div id="how-can-i-get-device-level" />

<Accordion title="Как получить данные об установках на Android на уровне устройств с помощью реферера установки Google Play и Meta?">

<div id="google-play-install-referrer-api" />

#### API реферера установки Google Play

API реферера установки Google Play позволяет рекламодателям извлекать такие данные об атрибуции, как информация о кампаниях, из установок, источником которых является Google Play Store. Этот API должен быть <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">интегрирован в ваше приложение</Anchor> и работать путем передачи данных о реферере при первом открытии приложения после установки. Поля атрибуции будут доступны в отчётах AppsFlyer по сырым данным с типом совпадения `gp_referrer` после отправки необходимого ключа расшифровки.

<div id="meta-install-referrer" />

#### Реферер установки Meta

Реферер установки Meta предоставляет дополнительные метаданные кампании, хранящиеся на устройстве локально. Доступ возможен через [SDK AppsFlyer](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer). Он дополняет реферер установки Google Play, обеспечивая более обширные данные, включая данные как о кликах, так и о показах, и потенциально охватывает несколько сеансов. Для атрибуции через реферер установки Meta используются такие типы соответствия, как `fb_referrer` (Facebook) и `ig_referrer` (Instagram).

<div id="campaign-attribution-fields" />

#### Поля атрибуции кампании

* идентификатор рекламы
* название рекламы;
* идентификатор адсета
* название группы объявлений;
* Идентификатор кампании
* название кампании;
* идентификатор аккаунта;
* Канал

<div id="sdk-and-setup-notes" />

#### SDK и настройка

* Для данных реферера Google Play требуется SDK AppsFlyer версии 5.4.0+.
* Поддержка реферера Meta зависит от правильной конфигурации SDK. Подробные сведения о реализации см. в <Anchor target="_blank" href="/marketers/ru/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">этом бюллетене</Anchor>.

<div id="submitting-the-decryption-key" />

#### Представление ключа расшифровки

Для обоих типов рефереров требуется ключ расшифровки из вашего аккаунта разработчика Meta. Нужно предоставить этот ключ только один раз для каждого приложения. Как это сделать:

1. Войдите в свой аккаунт на портале Meta для разработчиков.
2. Перейдите в **Мои приложения** и выберите соответствующее приложение.
3. Перейдите в раздел **Настройки > Основные** и найдите «Ключ расшифровки реферера установки».
4. В AppsFlyer перейдите к пункту **Сотрудничество > Активные интеграции > Meta Ads**.
5. Вставьте ключ в поле **Ключ расшифровки реферера установки** и нажмите сохранить.

</Accordion>

<div id="do-you-make-facebook-raw-data-available-to-agencies" />

<Accordion title="Предоставляются ли агентствам сырые данные от Meta Ads?">

Нет. Мы не можем предоставлять агентствам сырые данные Meta Ads, поскольку по условиям представления услуг Meta агентства считаются третьими лицами.

</Accordion>

<div id="i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports" />

<Accordion title="В отчетах об установках и внутренних событиях приложения нет сырых данных от Meta Ads.">

По умолчанию Meta Ads не позволяет распространение данных на уровне устройства без ограничений в отношении информации об атрибуции. Однако, если вы примете условия использования Meta Advanced Mobile Measurement (AMM), вы сможете получить доступ к данным атрибуции на уровне устройства для рекламы Meta без ограничений. См. <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">Включение данных на уровне устройства в Meta Ads</Anchor>.

</Accordion>

<div id="any-specific-columns-for-facebook-in-appsflyers-performance-reports" />

<Accordion title="Есть ли в отчетах об эффективности AppsFlyer отдельные столбцы для Meta Ads?">

Да. Отчеты об эффективности имеют статическую структуру столбцов, которая не зависит от выбора медиа-источника, где представлены данные до уровня кампании.  
Однако при загрузке отчетов об эффективности ТОЛЬКО для рекламы в Meta, AppsFlyer добавляет в них еще 4 столбца, где представлены данные до уровня отдельного объявления! Добавляются такие столбцы: Adset Name (Название блока рекламы), Adset ID (Идентификатор блока рекламы), Adgroup Name (Название группы объявлений) (т.е. отдельного объявления) и Adgroup ID (Идентификатор группы объявлений).

[![](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)

</Accordion>

<div id="can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer" />

<Accordion title="Можно ли работать с партнерами по управлению кампаниями Meta и измерять эффективность с помощью AppsFlyer?">

Да. AppsFlyer интегрирован с десятками партнеров по управлению кампаниями Meta. Для этих партнеров можно настроить атрибуцию на странице активных интеграций на дэшборде.

Подробные сведения о настройке атрибуции с партнерами по управлению кампаниями Meta см. <Anchor target="_blank" href="/marketers/ru/docs/configuring-meta-campaign-management-partners">здесь</Anchor>.

</Accordion>

<div id="what-should-i-do-when-i-receive-the-following-warning" />

<Accordion title="Что делать при получении такого предупреждения?">

[![](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)

* Подтвердите свой идентификатор приложения Facebook и проверьте, нет ли для этого идентификатора каких-либо ограничений по географическому положению или по возрасту.
* Если атрибуция уже выполняется, это означает, что приложение уже доступно для сообщества на портале разработчиков Meta, и вы можете проигнорировать это сообщение об ошибке.

</Accordion>

<div id="what-happens-with-different-lookback-windows-than-on-facebook" />

<Accordion title="Что произойдет, если окно атрибуции будет отличаться от такого окна в Meta Ads?">

В Meta Ads максимальное окно атрибуции по кликам – 7 дней, а по просмотрам – 1 день.

Если в AppsFlyer задать для этих окон более короткий период, это приведет к сокращению объёма данных атрибуции Meta Ads, доступных в AppsFlyer. И наоборот, более длинный период для окон в AppsFlyer приводит к тому, что объём данных атрибуции на стороне AppsFlyer будет больше, чем на стороне Meta.

Поэтому, чтобы свести расхождения к минимуму, рекомендуется задавать в AppsFlyer для окон атрибуции Meta Ads такие значения: 7 дней для атрибуции по кликам и 1 день для атрибуции по просмотрам.

</Accordion>

<div id="what-are-the-facebook-api-parameters" />

<Accordion title="Каковы параметры API для Meta?">

С целью обратной совместимости в некоторых API AppsFlyer имена параметров Meta отличаются от имен, отображаемых на дэшборде. Сопоставленные параметры показаны в таблице ниже:

| Данные о конверсиях | Необработанные данные AppsFlyer | Meta |
| --- | --- | --- |
| campaign (кампания) | campaign (кампания) | campaign\_group\_name |
| campaign\_id (идентификатор кампании) | Идентификатор кампании | campaign\_group\_id |
| adgroup | Реклама | adgroup\_name |
| adgroup\_id | идентификатор рекламы | adgroup\_id |
| рекламный набор | Блок рекламы | campaign\_name |
| adset\_id (идентификатор группы объявлений) | идентификатор адсета | campaign\_id (идентификатор кампании) |
| агентство | Партнер | Н/Д |
| is\_fb | Источник медиа | is\_fb |
| af\_channel | Канал | publisher\_platform |
| af\_siteid | ID сайта | publisher\_platform, если значение `publisher_platform` не равно `facebook` иначе `null`. |

</Accordion>

<div id="how-long-do-you-keep-facebook-s-userlevel-data" />

<Accordion title="Сколько времени хранятся данные Meta Ads пользовательского уровня?">

Meta Ads требует от поставщиков атрибуции удалять свои данные уровня пользователей через 6 месяцев после установки. Это означает, что события этих пользователей, которые произошли через 6 месяцев после установки приложения, считаются органическими.  
Сводные данные за прошлое время не изменяются.  
Это относится ко всем каналам Meta Ads (приложения Facebook, Instagram, Messenger и AudienceNetwork).

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-meta-ads" />

<Accordion title="Поддерживаются ли универсальные ссылки iOS и Android App Links в Meta Ads?">

Универсальные ссылки iOS и Android App Links поддерживаются и могут использоваться в Meta Ads. Подробнее смотрите в <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">справочном центре Meta</Anchor>.

* Для статических объявлений (без каталога) универсальные ссылки iOS и Android App Links поддерживаются только в кампаниях, где в качестве назначения выбрано **App** (Приложение).
* Для динамических объявлений могут использоваться универсальные ссылки iOS, Android App Links и схемы URI, описанные [здесь](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).

**Примечание.** Универсальные ссылки iOS и Android App Links поддерживаются только в платной рекламе.

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content" />

<Accordion title="Поддерживаются ли универсальные ссылки iOS и Android App Links в бесплатном контенте для Meta?">

Универсальные ссылки iOS и Android App Links поддерживаются только в платной рекламе. В отношении бесплатного контента для приложений соцсетей, может потребоваться настроить лендинг для приложения соцсети или схему URI, чтобы перенаправлять пользователей или направлять их по диплинкам.

</Accordion>

<div id="aem-attribution-is-not-working" />

<Accordion title="Атрибуция AEM не работает">

Если переключатель **Расширенный обмен данными** включен и вы не получаете атрибуцию от Meta, проверьте, соответствуют ли общие события критериям приемлемости Meta. См. [документацию Meta](https://www.facebook.com/business/help/716239976391518?id=1877298665783613).

</Accordion>

<div id="can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads" />

<Accordion title="Можно ли использовать ссылки OneLink для открытия приложений и диплинкинга в динамических объявлениях о товарах?">

Да. Ссылки OneLink с настроенными App Links, Universal Links или схемами URI поддерживаются в динамической рекламе продукта. В новостной ленте можно использовать ссылки OneLink для каталогов, используемых в динамических объявлениях в полях **applink.ios\_url** и **applink.android\_url.**

</Accordion>

<div id="conversion-events-are-not-sent-to-meta-ads" />

<Accordion title="События конверсии не отправляются в Meta Ads">

Возможно у вас тарифный план Zero, который не включает в себя атрибуцию.

</Accordion>

<div id="can-i-use-get" />

<Accordion title="Можно ли использовать Get Conversion Data (GCD) для получения данных о конверсиях из Meta?">

**Да.** Вы можете продолжать использовать **GCD** для получения данных о конверсиях из Meta в зависимости от настроек вашего приложения и статуса соглашения AMM:

* **Если SDK Facebook интегрирован в ваше приложение:**

  Как описано в <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns#deferred-deep-linking">документации по отложенному диплинкингу (DDL)</Anchor>, вы можете получить данные DDL и использовать их через GCD.
* **Если SDK Facebook не интегрирован в ваше приложение:**

  Вы по-прежнему можете получить **кампанию, группу объявлений и названия объявлений** через GCD при условии, что <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#meta-ads">при условии, что подписано соглашение Advanced Mobile Measurement (AMM).</Anchor> . В этом случае вы можете использовать эти значения для применения собственной **логики настраиваемого диплинкинга**.

<div id="note" />

> 📘 **Примечание:**
>
> Политики обмена данными Meta могут влиять на уровень детализации, доступный через GCD. Убедитесь, что AMM подписан, чтобы получить максимальный доступ к данным на уровне кампании.

</Accordion>

<div id="meta-ads-cost-faq" />

## Вопросы и ответы по затратам в Meta Ads

<div id="getting-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="Отображение данных о затратах в Meta Ads на дэшборде AppsFlyer">

AppsFlyer получает данные о затратах (включая клики и показы) в кампаниях Meta Ads, если за предыдущие 7 дней была выполнена хотя бы одна установка.

Если кампания в Meta Ads развернута на нескольких платформах (Android, iOS, настольный ПК и т.д.), то затраты на дэшборде отображаются по каждой платформе, и их рассчитывает Meta Ads.

<Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Как получить затраты в Meta Ads, в том числе по кликам и показам</Anchor>.

</Accordion>

<div id="facebook-cost-example" />

<Accordion title="Пример данных по затратам в Meta Ads">

Рекламодатель запускает рекламную кампанию в Meta Ads. В AppsFlyer рекламодатель увидит такую информацию:

![mceclip2.png](https://files.readme.io/a1aa5847db5c0b873b34b1d4de43ade7d4109608371e05a84342122e56d0ce08-4411031032081.png)

Данные о затратах AppsFlyer получает из Meta Ads. AppsFlyer определяет количество **установок** расчетным путем на основании своих правил атрибуции. Поэтому расчетные показатели eCPI в Meta Ads и AppsFlyer, как правило, отличаются.

</Accordion>

<div id="i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="Я не вижу старые данные Meta Ads о затратах на дэшборде AppsFlyer">

Данные о затратах в Meta Ads для действующих кампаний будут с определенной периодичностью поступать в AppsFlyer в течение 7 дней после первого входа в Meta Ads с правами администратора (см. выше). Данные о затратах, полученные ранее, недоступны.

При последующих синхронизациях AppsFlyer получает данные за последние 7 дней. Это означает, что собираются данные о затратах, кликах и показах по всем кампаниям, в которых за последние 7 дней произошла по крайней мере одна конверсия.

</Accordion>

<div id="can-i-stop-cost-data-sync" />

<Accordion title="Можно ли прекратить синхронизацию данных о расходах?">

Чтобы прекратить синхронизацию данных о расходах с Meta Ads, <Anchor target="_blank" href="https://www.facebook.com/help/405094243235242">войдите в свой аккаунт Meta Ads и удалите AppsFlyer из раздела Business Integration (Бизнес-интеграция)</Anchor>.

</Accordion>

<div id="cost-data-was-fine-for-a-few-months-but-it-stopped-displaying" />

<Accordion title="Данные о затратах отображались несколько месяцев, но потом перестали">

Meta Ads сбрасывает разрешение на получение этих данных каждые несколько месяцев. Если вы заметили, что данные о затратах больше не отображаются на дэшборде, еще раз выполните вход в Meta Ads с правами администратора.

После изменения пароля аккаунта администратора также нужно повторить вход в Meta Ads.

</Accordion>

<div id="i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer" />

<Accordion title="Я кликнул по моему объявлению на Facebook 5 минут назад. Почему я не вижу этот клик в AppsFlyer?">

AppsFlyer периодически получает от Meta Ads агрегированные данные о кликах, показах и затратах с интервалом в несколько часов. Поэтому эти действия будут показаны на дэшборде AppsFlyer только через несколько часов.

</Accordion>

<div id="can-i-get-raw-data-on-clicks-and-impressions-from-facebook" />

<Accordion title="Могу ли я получить сырые данные о кликах и показах из Meta Ads?">

AppsFlyer получает от Meta Ads только агрегированные данные о кликах и показах, поэтому полный набор сырых данных о кликах и показах недоступен. В отчетах по сырым данным есть данные только о тех кликах и показах, которые привели к установкам.

</Accordion>

<div id="are-there-limitations-of-facebook-cost-data-by-geo" />

<Accordion title="Есть ли ограничения на данные о затратах в Meta Ads в зависимости от географического положения?">

Если на дэшборде AppsFlyer используется фильтрация по геоданным, вы можете увидеть и агрегированные данные о затратах в Meta Ads, и данные с разбивкой по географическому положению.

Эти данные доступны в Meta Ads только для кампаний типа «Mobile App Install Campaigns» (Кампании с целью установки мобильных приложений).

Кроме того, разбивка затрат по географическому положению доступна только для одноплатформенных кампаний. Это означает, что для кампаний, где есть блоки рекламы, предназначенные как для пользователей устройств Android, так и для пользователей устройств iOS, разбивка данных о затратах по географическому положению недоступна. **Чтобы получать полные данные о затратах, создавайте отдельные кампании для каждой платформы**.

</Accordion>

<div id="what-are-the-limitations-of-facebook-cost-data-in-master-api" />

<Accordion title="Какие ограничения на данные о затратах в Meta Ads есть в Master API?">

Meta Ads не позволяет одновременно группировать данные в <Anchor target="_blank" href="/marketers/ru/docs/master-api-user-acquisition-metrics-via-api">отчетах Master API</Anchor> и по географическому положению, и по каналам.

Чтобы сформировать отчет с полными данными о затратах, сгруппируйте данные только по одному из этих параметров.

</Accordion>

<div id="the-total-cost-doesnt-match" />

<Accordion title="Почему общие затраты, отображаемые в Meta и AppsFlyer, не совпадают?">

Модели атрибуции, которые используются в Meta Ads и AppsFlyer, немного отличаются. Эти различия могут привести к расхождениям с данными о затратах в Meta Ads:

* **В Meta Ads используется атрибуция на нескольких устройствах** — для кампаний, предназначенных для одной платформы (iOS или Android), установки могут отображаться с данными о затратах для другой платформы.
* **Кампании в Meta Ads для немобильных платформ** — в этих кампаниях, так же как и в кампаниях Meta Ads типа «Нажмите ссылку», мобильное приложение может установить и пользователь ПК. Для таких кампаний, которые предназначены для нескольких устройств, AppsFlyer не показывает данные о затратах. Однако если ссылка была нажата на том же устройстве, где установлено приложение, то данные о затратах будут получены.  
  Например, пользователь Facebook нажимает на объявление, которое перенаправляет его на целевую страницу рекламодателя на ПК. Через неделю этот же пользователь устанавливает на iPhone рекламируемое приложение, предназначенное для iOS. Эта установка атрибутируется и отображается на дэшборде AppsFlyer, однако данные о затратах для этой кроссплатформенной установки не отображаются.
* **Кампании, которые принесли 0 результатов за последние 7 дней** — AppsFlyer синхронизирует данные о затратах только для тех кампаний, которые за последние 7 дней привели к установкам или конверсиям. Не отображаются данные о затратах для кампаний, которые на момент активации функции «Затраты в Meta Ads» были неактивны в течение 7 дней.
* **Удаленные и архивированные объявления**: Meta не сообщает в AppsFlyer о затратах на удаленные и архивированные объявления, однако эти затраты отражаются на панели управления Meta. Это может привести к расхождениям между отчётами Meta и AppsFlyer при сравнении данных на уровне кампании.

</Accordion>

<div id="why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical" />

<Accordion title="Почему расчет eCPI в AppsFlyer отличается от стоимости, рассчитанной Meta Ads, в то время как общая стоимость одинакова?">

Показатель «Стоимость установки» рассчитывается как частное от деления общей суммы затрат на количество установок. Поскольку <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-discrepancies">AppsFlyer подсчитывает количество установок не так, как Meta Ads</Anchor>, значения показателя eCPI на этих платформах, как правило, отличаются.

</Accordion>

<div id="why-doesnt-cost-data-include-data-from-all-campaigns" />

<Accordion title="Почему данные о затратах не включают данные по всем кампаниям?">

Когда пользователь, выполняющий вход в Meta Ads (описано выше), не имеет доступа к некоторым запущенным кампаниям, то кампании отображаются на дэшборде AppsFlyer, но в них отсутствуют некоторые данные о затратах, кликах и показах.

**Примечание:** Хотя на проведение кампаний в Meta Business Manager могут иметь разрешение несколько пользователей Meta Ads, для выполнения входа в Meta Ads требуется только один.

</Accordion>

<div id="is-facebook-cost-data-displayed-for-retargeting-campaigns" />

<Accordion title="Можно ли получать от Meta Ads данные о затратах для ретаргетинговых кампаний?">

Данных о расходах и окупаемости инвестиций по ретаргетинговым кампаниям можно найти в **Объединённом** представлении <Anchor target="_blank" href="/marketers/ru/docs/cohort-and-retention-dashboard">когортных отчетов</Anchor>.

</Accordion>

<div id="why-does-the-facebook-cost-configuration-window-close-before-login" />

<Accordion title="Почему окно настройки данных о затратах в Meta Ads закрывается перед входом в систему?">

Если выполнить вход в Meta Ads в том же браузере, в котором выполняются настройки, окно автоматически подключится к Meta Ads с использованием тех же учетных данных. Если доступ AppsFlyer уже предоставлен, то больше никаких действий не требуется и окно закроется.

</Accordion>

<div id="why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store" />

<Accordion title="Почему есть расхождения в данных о стоимости приложений в магазине приложений Amazon?">

В отличие от AppsFlyer, Meta Ads не видит разницы между данными о затратах для приложений Android и приложений из магазина Amazon, так как они тоже на базе Android. Поэтому данные о затратах для пользователей приложений из Amazon могут атрибутироваться кампаниям, ориентированным на других пользователей приложений Android, а не на кампании, созданные для Amazon.

</Accordion>

<div id="how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked" />

<Accordion title="Как подключить данные о затратах с нового рекламного аккаунта Meta Ads, пока подключен мой старый аккаунт?">

Если вы хотите перейти на новый рекламный аккаунт, но ваши затраты в Meta Ads уже связаны через AppsFlyer со старым рекламным аккаунтом, вам необходимо отключить рекламный аккаунт через Meta Ads и подключить новый рекламный аккаунт в AppsFlyer.

1. В Meta Ads перейдите в раздел **Settings** > **Business Integration** (Настройки > Бизнес-интеграция).
2. Удалите интеграцию с AppsFlyer на вкладке **Active** (Активные).  

   [![](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)
3. Перейдите на дэшборд AppsFlyer и подключите затраты к новому аккаунту.

</Accordion>

<div id="facebook-sdk-faq" />

## Вопросы и ответы по SDK Facebook

<div id="who-needs-facebooks-sdk" />

<Accordion title="Кому необходим SDK Facebook?">

Возможно, SDK Facebook был интегрирован в ваше приложение раньше, чем SDK AppsFlyer. Даже если это не так, у вас может возникнуть вопрос, действительно ли вам нужен SDK Facebook в дополнение к SDK AppsFlyer? А если нужен, могут ли они работать параллельно без дублирования данных в отчетах?

Для выполнения следующих задач наличие SDK Facebook в приложении не требуется:

* **Привлечение пользователей**: Как правило, в SDK AppsFlyer есть все необходимые средства для атрибуции привлечения пользователей мобильных приложений из Meta Ads, в том числе для отслеживания интеракций, установок, сессий и событий после установки.
* **Диплинкинг**: Чтобы при клике по ссылке открывать приложение и перенаправлять пользователей на определенную страницу или активность в приложении, можно использовать OneLink как с SDK Facebook, так и без него. Для этого можно использовать универсальные ссылки iOS (iOS Universal Links), Android App Links и схемы URI. Подробнее смотрите в <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">справочном центре Meta</Anchor>.  

  **Примечание:**   
  Для статических объявлений (без каталога) универсальные ссылки iOS и Android App Links поддерживаются только в кампаниях, где в качестве назначения выбрано **App** (Приложение).  
  Например, если вы настроили информационно-образовательную кампанию в Meta: поскольку для таких кампаний нельзя выбрать **приложение** в качестве пункта назначения, универсальные ссылки iOS и Android App Links не поддерживаются.  

  Для динамических объявлений могут использоваться универсальные ссылки iOS, Android App Links и схемы URI, описанные [здесь](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads).  

  Meta Ads извлекает URL-адрес OneLink и создает на его основе ссылку Meta Ads App Link, которая открывает приложения и перенаправляет пользователя по диплинку.

В следующих случаях в приложение помимо SDK AppsFlyer должен быть интегрирован SDK Facebook:

* **Отложенный диплинкинг**:  
  Значения отложенного диплинкинга в Meta Ads недоступны в данных о конверсиях. Клиенты должны обеспечить координацию с Meta, и обычно для доступа к этим данным требуется SDK Facebook.
* **Данные о кампаниях динамической рекламы**: Данные о кампаниях динамической рекламы можно получить только из SDK Facebook.
* **Другие возможности Meta Ads**: Вам может понадобиться SDK Facebook по причинам, не связанным с атрибуцией, таким как проверка подлинности, монетизация рекламы, обмен данными в социальных сетях, приглашения пользователей и т.д.

<div id="note-1" />

> 📘 **Примечание:**
>
> Приведенные выше информация и рекомендации по диплинкингу и отложенному диплинкингу составлены по результатам тщательного тестирования, проведенного нами с использованием доступных инструментов Meta Ads для демонстрации и предварительного просмотра, в которых используется не опубликованная реклама, а другой механизм.

</Accordion>

<div id="avoiding-duplicates-with-facebook-sdk" />

<Accordion title="Как избежать дублирования данных при использовании SDK Facebook">

Если <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#faq_593792547454717">в вашем приложении есть оба SDK, AppsFlyer и Facebook</Anchor>, данные о событиях установки и внутренних событиях приложения передаются в SDK Facebook, а затем AppsFlyer передает их с помощью постбэков на серверы Meta Ads. Как избежать такой повторной передачи данных?

* **Установки**. Это означает, что **нет дублирования** и каждая установка учитывается только один раз.
* **В отношении внутренних событий приложения**, Meta Ads не устраняет дубликаты внутренних событий приложения, что потенциально может привести к двойному учёту и неточностях в отчетности о внутренних событиях приложения. Чтобы избежать такого дублирования в Meta Ads, рассмотрите один из следующих вариантов:
  * Не выполняйте настройку событий в SDK Facebook
  * Для Android: отключите в AppsFlyer <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-in-app-event-mapping">сопоставление внутренних событий приложения с событиями в Meta Ads</Anchor>.  
    Обратите внимание, что для включения атрибуции SKAN для iOS 14.5+, потребуется <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-interoperation-with-meta-ads#in-app-event-mapping">сопоставить внутренние события приложения событиям Meta Ads</Anchor>.

</Accordion>

<div id="meta-ads-attribution-faq" />

## Вопросы и ответы об атрибуции Meta Ads

<div id="attributing-agencies-with-facebook" />

<Accordion title="Атрибутирование агентств с Meta Ads">

Агентства и партнеры по управлению кампаниями Meta могут запускать кампании в Meta Ads и выполнять для них атрибуцию от имени рекламодателей в AppsFlyer или даже вместе с собственными кампаниями рекламодателей в Meta Ads. Для того чтобы кампании агентств атрибутировались агентствам, названия этих кампаний ДОЛЖНЫ начинаться с названия агентства.

Обратите внимание, что для пользователей iOS 14 только **одно** агентство может запускать кампании для определенного рекламного аккаунта. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-interoperation-with-meta-ads#взаимодействие-со-skan-appsflyer---meta-реклама">совместимости Meta Ads и AppsFlyer SKAdNetwork</Anchor>.

Подробные сведения об агентствах и атрибуции установок, выполненных из Meta Ads, см. <Anchor target="_blank" href="/partners/ru/docs/about-agency-accounts#конфигурации-srn">здесь</Anchor>.

Кроме того, **агентства не могут изменять значения окон атрибуции Meta Ads и положение переключателя ретаргетинга**. Если им необходимо внести такие изменения, они должны попросить об этом рекламодателя.

Кроме того, агентства не могут вносить никаких изменений в постбэки внутренних событий приложения, отправленных в Meta Ads. Причина этого в том, что Meta Ads требует предоставления информации обо всех установках, включая те, которые этой сети не атрибутированы (то есть могли быть произведены в результате кампаний, не проводимых данным агентством).

На рисунке ниже показаны все параметры, которые рекламодатель должен настроить для агентства, чтобы дать ему возможность управлять своими кампаниями в Meta Ads:

[![advertiser-vs-agency-facebook-int-new.png](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)

</Accordion>

<div id="attribution-for-facebook-for-outofstore-android-apps" />

<Accordion title="Выполнение в Meta Ads атрибуции для приложений Android, не связанных с магазином Google Play">

Meta Ads не позволяет создавать рекламные кампании по продвижению мобильных приложений для Android, опубликованных на торговых площадках, не связанных с магазинами, например на Baidu.

Тем не менее, приложения, не связанные с магазином, можно рекламировать в Meta Ads и регистрировать их установки. Для этого нужно выполнить следующие действия:

1. Разработчик должен подготовить отдельные файлы АРК для каждой торговой площадки, не связанной с магазинами, на которой рекламируется ваше приложение. Подробные сведения <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution">см. здесь</Anchor>.
2. Создайте в Meta Ads кампанию **Traffic** или **Conversions** с активированной мобильной атрибуцией, через которую лиды будут направляться на целевую страницу.
3. На целевой странице должна быть кнопка **Скачать приложение**, которая ведет напрямую на независимую торговую площадку с пакетом APK.
4. Когда потенциальные пользователи нажимают на кнопку, они перенаправляются на независимую торговую площадку. После выполнения установки AppsFlyer атрибутирует пользователя к Meta Ads через API MMP.

<div id="note-2" />

> 📘 **Примечание:**
>
> Это же решение применимо и к приложениям в Google Play и App Store, так как в них пользователю сначала нужно попасть на <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">целевую страницу</Anchor>, а потом уже в магазин приложений.

Инструкции по выполнению атрибуции для приложений, размещенных в Amazon, см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-multi-store-android-attribution#driving-users-to-the-amazon-app-store-from-facebook">здесь</Anchor>.

</Accordion>

<div id="what-is-facebook-android-and-ios-crossattribution" />

<Accordion title="Что такое перекрестная атрибуция Meta Ads для Android и iOS?">

Meta Ads идентифицирует пользователей по аккаунту Meta Ads. У некоторых пользователей с одним аккаунтом Meta Ads связаны устройства и iOS, и Android.

Если такой пользователь просматривает рекламу приложения или кликает по ней на устройстве Android, а устанавливает приложение на устройстве iOS, Meta Ads считает себя источником установки. В результате на вашем дэшборде для iOS отображается название кампании для Android.

<div id="example" />

> 📄 **Пример**
>
> Эндрю Йозеф использует устройство Android. В процессе он кликает по рекламе приложения **Bubbles** в Meta Ads из кампании для Android. Он НЕ скачивает приложение.
>
> Через день уже на устройстве iOS Эндрю Йозеф решает найти приложение **Bubbles** через поиск, скачивает его и запускает.
>
> В этой ситуации система атрибуции AppsFlyer получает из Meta Ads данные о рекламной кампании в Meta Ads для Android и указывает их на дэшборде для iOS — по устройству, на которое Эндрю Йозеф скачал и на котором запустил приложение.

</Accordion>

<div id="what-are-facebook-ads-channels" />

<Accordion title="Что такое «каналы Meta Ads»?">

Вы могли заметить, что Meta Ads предоставляет данные не только на уровне кампаний, рекламных блоков и объявлений, но и на уровне каналов Meta Ads (которые называются «Места размещения»).

* **Facebook** — пользователи приложения Facebook
* **Instagram** — пользователи приложения в Instagram.
* **Messenger** — пользователи приложения в Facebook Messenger.
* **AudienceNetwork** — пользователи других приложений, которые относятся к Meta Ads или связаны с этой сетью.
* **Threads** — пользователи из приложения Threads
* **WhatsApp** — пользователи приложения WhatsApp

Эти данные можно использовать для сравнения качества пользователей, получаемых от различных каналов.

![Facebook_channels.png](https://files.readme.io/f6b51baf3056f42ee32ac9709b1e4b3661580ce6148acfa36fc2bad102e7bfd8-4411036713745.png)

</Accordion>

<div data-zendesk-anchors="facebook-ads-faq=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-meta-ads h_01HD1JTW2EP1MY3DD9136E9CHC=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-meta-ads h_01HD1JTW2EN36V9SHH11283Y3A=i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard h_01HD1JTW2EJE0K034KSV8B3WZQ=can-appsflyer-show-the-campaign-level-and-ad-groups h_01HD1JTW2EFKCJMNBXBK2C55DN=is-facebook-data-shown-in-realtime h_01HD1JTW2E4SVC1Z9C3K6XJB2G=when-can-i-see-a-new-campaigns-data-on-appsflyer h_01HD1JTW2ECWSXFKQC1YBP1592=how-can-i-get-more-installs-from-facebook h_01K8B4YFDKKYP25V6NR12CE9RF=how-can-i-get-device-level h_google_play_referrer=api-%D1%80%D0%B5%D1%84%D0%B5%D1%80%D0%B5%D1%80%D0%B0-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-google-play google-play-install-referrer-api=api-%D1%80%D0%B5%D1%84%D0%B5%D1%80%D0%B5%D1%80%D0%B0-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-google-play h_meta_install_referrer=%D1%80%D0%B5%D1%84%D0%B5%D1%80%D0%B5%D1%80-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-meta meta-install-referrer=%D1%80%D0%B5%D1%84%D0%B5%D1%80%D0%B5%D1%80-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-meta h_attribution_fields=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 campaign-attribution-fields=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_sdk_requirements=sdk-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 sdk-requirements=sdk-%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 h_decryption=%D0%BF%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%84%D1%80%D0%BE%D0%B2%D0%BA%D0%B8 decryption-key=%D0%BF%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%84%D1%80%D0%BE%D0%B2%D0%BA%D0%B8 h_01HD1JTW2ED762B3K1QS6QC38M=do-you-make-facebook-raw-data-available-to-agencies h_01HD1JTW2EWQGK4QA9W8DFZTMH=i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports h_01HD1JTW2EYSBJ38WNS1HP5MCE=any-specific-columns-for-facebook-in-appsflyers-performance-reports h_01HD1JTW2ETTXQAP7ZSTMVGA8K=can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer h_01HD1JTW2EPY8W5Z84PBWSM86G=what-should-i-do-when-i-receive-the-following-warning h_01HD1JTW2ED2DNPTXAFYJTTGV3=what-happens-with-different-lookback-windows-than-on-facebook h_01HD1JTW2EXF1R0MA91ZSW7QG4=what-are-the-facebook-api-parameters how-long-do-you-keep-facebook%E2%80%99s-userlevel-data=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EPDNSY30J45JB443A=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EN8THFCRNZ0EBQ2M3=are-ios-universal-links-and-android-app-links-supported-in-meta-ads h_01JJVVX9NCSTVQKG2ENTGDRDK9=are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content 01H7YJVNMVBRVTT9HH7KM8P33B=aem-attribution-is-not-working h_01HD1JTW2ETG739TWQVTKPCM2R=can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads h_01JTG2474VHWAD8EK8ASPWZY0W=conversion-events-are-not-sent-to-meta-ads h_01K8B4AKSHSMP18MM0GAAZEQMF=can-i-use-get h_01K8B4AKSH7E8TBEG024NAV1A5=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 facebook-ads-cost-faq=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D0%B0%D0%BC-%D0%B2-meta-ads h_01HD1JTW2EEVD1PDPFW15K45CE=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D0%B0%D0%BC-%D0%B2-meta-ads h_01HD1JTW2EE0WQ90J431Z8NQ8Q=getting-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2ESVMMPK32W34PA54T=facebook-cost-example h_01HD1JTW2EVFXAET26WK2KSHTV=i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2EJQHKVJF4XHWGVASJ=can-i-stop-cost-data-sync h_01HD1JTW2EYJTA2TRY7EE75KXA=cost-data-was-fine-for-a-few-months-but-it-stopped-displaying h_01HD1JTW2EYXZW2QCMQH5CRFSK=i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer h_01HD1JTW2EYE2ZDNVRT5BCRXZJ=can-i-get-raw-data-on-clicks-and-impressions-from-facebook h_01HD1JTW2EG11RRBYHJ5BMJM5M=are-there-limitations-of-facebook-cost-data-by-geo h_01HD1JTW2E3RMV2TMPNZZ86HG5=what-are-the-limitations-of-facebook-cost-data-in-master-api h_01HD1JTW2EKVSAQ3706NC8JV9M=the-total-cost-doesnt-match h_01HD1JTW2EMJQJHBBB9SRJ6MZN=why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical h_01HD1JTW2E2S79FC9VAHA12X93=why-doesnt-cost-data-include-data-from-all-campaigns h_01HD1JTW2ET6Y2EHG29AQS09NA=is-facebook-cost-data-displayed-for-retargeting-campaigns h_01HD1JTW2EXTS1GDZHN8PAMV8C=why-does-the-facebook-cost-configuration-window-close-before-login h_01HD1JTW2FC0NJK00HZ76SFH30=why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store how-to-connect-cost-data-of%C2%A0a-new-facebook-ad-account-while-my-old-account-is-linked=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked h_01HD1JTW2F401DA2NHBSPTKATB=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked facebook-ads-sdk-faq=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-sdk-facebook h_01HD1JTW2FPRCVGBF7CG7ZMKXF=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-sdk-facebook h_01HD1JTW2F03XQSEVTFBW8JCX3=who-needs-facebooks-sdk h_01HD1JTW2FB09HM2CC83GMT901=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01HD1JTW2FNNHPZQARZNCCP7ER=avoiding-duplicates-with-facebook-sdk facebook-ads-attribution-faq=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-meta-ads h_01HD1JTW2F2JV2BMDS40HFG6K0=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-meta-ads h_01HD1JTW2FK1ZTPTA8B8A4N64Z=attributing-agencies-with-facebook h_01HD1JTW2F63AT1NGBY96Y6CCE=attribution-for-facebook-for-outofstore-android-apps h_01HD1JTW2FMKYDHNSM7G182EY0=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 h_01HD1JTW2F8JT69CSN04GCZ91V=what-is-facebook-android-and-ios-crossattribution h_01HD1JTW2F5PY7A8T5NMHBZ87B=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01HD1JTW2FX3QWC9BKWQ65E5B8=what-are-facebook-ads-channels" />

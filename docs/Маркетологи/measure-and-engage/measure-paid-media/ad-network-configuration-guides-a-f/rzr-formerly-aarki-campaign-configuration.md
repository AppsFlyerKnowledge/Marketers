---
title: Настройка кампании RZR (ранее Aarki)
metadata:
  keywords:
    - Advertisers
    - aarki
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-12T06:15:54Z'
  edited_at: '2026-09-11T00:23:44Z'
  id: 360000423105
  locale: ru
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ru/articles/360000423105
---
> **Краткий обзор:** RZR — известная мобильная DSP и интегрированный партнер рекламной сети AppsFlyer. RZR предлагает мобильную атрибуцию как по кликам, так и по просмотрам. Кроме того, RZR также предлагает ретаргетинг по кликам, который можно отслеживать с помощью AppsFlyer.

<Image alt="RZR Logo Horizontal gradient black wordmark (3).png" src="https://files.readme.io/b1064bdec0e836399c583c3f55e5e79a81380a9a8d86eeaee19391b6d09f2bbd-small-46161100230545.png" width="58.83%" />

## Настройка RZR

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции. Этот переключатель **обязательно** должен быть включен все время, пока вы работаете с партнером.  
    Дополнительная информация по активации партнеров: нажмите <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

### Активация партнера

<span id="01ECJ9TJKEFXN53XDEBJ5Z92SS"></span>При **первом посещении** нужно перевести кнопку ***Активировать партнера*** в положение «Включено», чтобы стала доступна настройка параметров вкладки интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером. Дополнительная информация по активации партнеров: нажмите <Anchor target="_blank" href="/marketers/ru/docs/user-level-data-retention">здесь</Anchor>.

> 📘 **Примечание:**
>
> Как сеть, ориентированная на все установки, RZR предпочитает получать постбэки для всех новых установок вашего приложения из любого источника, включая органические. Рекомендуется выбрать **События, атрибутированные любому партнеру**, чтобы отправлять в RZR постбэки по всем установкам.

### Общие настройки

<span id="01ECJ9TJKF9QBT98Z7XJM3H8F1"></span>**Partner ID (Идентификатор партнера)**

<span id="01ECJ9TJKF6R5F2K8VGMR7KFHN"></span>RZR подключается к AppsFlyer посредством уникального сетевого идентификатора. Если у вас еще нет идентификатора ID сети, его нужно получить у RZR, чтобы продолжить интеграцию.

<span id="01ECJ9TJKFZN0WVXXS0B89CMBY"></span>**Активация атрибуции по просмотрам**

<span id="01ECJ9TJKFE4E8GZQ2EN3Z1SM4"></span>Установите этот переключатель в положение «Включено», если хотите атрибутировать установки по просмотрам в RZR. На вкладке «Ссылка атрибуции» (описана ниже) имеется шкала для окна атрибуции по просмотрам.

### Постбэки по умолчанию

<span id="01ECJ9TJKFT13WB1T328ET3PGC"></span>Автоматически отправляйте постбэки в RZR после установок и повторного вовлечения пользователей. В этом разделе можно определить **источник пользователей**, который позволяет отправлять постбэки.

<span id="01ECJ9TJKFQH37DQZ3V3NAESRF"></span>Выберите **Только события, атрибутированные этому партнеру** для событий, поступающих только от пользователей, атрибутированных RZR. Выберите **События, атрибутированные любому партнеру или органические**, чтобы вся ваша база пользователей была доступна для отчетности в RZR.

### In-App Events Settings (Настройки внутренних событий приложения)

<span id="01ECJ9TJKF6QKF23NRTA5VS8Y9"></span>В этом разделе можно сопоставить события AppsFlyer с RZR и настроить отправку постбэков.

**Чтобы настроить постбэки для внутренних событий приложения:**

1. Активируйте **Постбэки событий внутри приложения**.
2. Чтобы добавить в список событие, определенное в SDK, или межсерверное событие, нажмите **Добавить событие**. В таблице ниже описаны поля, которые необходимо заполнить:

| Название параметра | Description(Описание) |
| --- | --- |
| **Событие AppsFlyer** | Название события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<br />**Совет**: Не нашли здесь нужное событие?<ul><li>Убедитесь, что событие активировано на устройстве с неорганической установкой, и повторите поиск.</li><li>Введите его в поле **Событие AppsFlyer** и нажмите **Создать пользовательское**. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">сопоставлении пользовательских событий</Anchor>.</li></ul> |
| **сопоставлено с событием партнёра** | Уникальное имя или идентификатор каждого события, определенные партнером. Возможны следующие настройки сопоставления:<ul><li>**Текстовое поле:** Получите соответствующий идентификатор события от партнера.</li><li>**Раскрывающийся список:** Выберите наиболее подходящее предопределённое событие AppsFlyer.</li><li>**Как есть**: События отправляются в исходном виде, без сопоставления названий.</li></ul> |
| **для пользователей от** | Выберите вариант отправки для события.<ul><li>**Только события партнера**: постбэки отправляются только в том случае, когда событие атрибутируется к этому партнеру.</li><li>**Все медиа-источники и органический трафик**: отправляйте постбэки для событий, атрибутированных к любому партнеру, а также для органических событий.</li></ul> |
| **включая** | <ul><li>**Без данных (по умолчанию)**: Отправлять только само событие без каких-либо значений.</li><li>**Значения и доход**: Отправьте все параметры события, **включая** ценность, значение выручки (если оно присутствует в событии).</li><li>**Значения без выручки**: Отправьте все параметры, **кроме** значения выручки.</li></ul> |

3. [Необязательно] Нажмите кнопку **Добавить условие**<Image alt="conditional-iae-postbacks-icon.pngicon" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />, чтобы <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">задать условия</Anchor> для события.
4. Нажмите **Сохранить интеграцию**.
5. [Необязательно] После сохранения интеграции, оставаясь на странице конфигурации, вы можете интегрировать больше своих приложений с партнёром:
   1. В верхнем левом углу под именем партнера нажмите на имя приложения, чтобы открыть список приложений.
   2. Выберите другое приложение из выпадающего списка.
   3. Повторите <Anchor target="_blank" href="/marketers/ru/docs/amazon-ads-campaign-configuration#integration-tab">шаги по интеграции</Anchor> для выбранного приложения.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

<span id="01ECSMR3VTP3SVSP9YXGW526PA"></span>На этой вкладке можно создавать ссылки атрибуции, которые нужно передать RZR для атрибуции кампаний, групп объявлений или даже отдельных объявлений RZR. Обратите внимание, что AppsFlyer НЕ сохраняет ссылки атрибуции, созданные для вашего партнера.

<span id="01ECJ9TJKFTGNEZ68AR6DGXJNA"></span>На этой вкладке есть несколько разделов:

### Параметры ссылки атрибуции

<span id="01ECJ9TJKFJRJ2BYN069CK80C8"></span>В этом разделе можно выбрать параметры для добавления в ссылку атрибуции.

<span id="01ECJ9TJKG144FJ8R72S2XDKQS"></span><span id="01ECJ9TJKFY5Q8P4QS57HD44T3"></span>Здесь можно задавать дополнительные параметры ссылки атрибуции, чтобы затем использовать их для детального анализа. Параметры, уже заданные в ссылке атрибуции, можно редактировать, добавляя их и их новые значения здесь.

* <span id="01ECJ9TJKGTPN4NF8CC66XBRRS"></span>**<span id="01ECJ9TJKGZP0D1TYCB5R8XJ80"></span>Campaign** — добавьте этот параметр, чтобы сравнивать разные кампании, запущенные в RZR.**Параметр ссылки атрибуции:** c
* <span id="01ECJ9TJKGSVH0XGW2R8HRDA4T"></span>**Ad Name** — задайте названия групп объявлений, чтобы сравнивать разные креативы в определенных группах объявлений в рамках определенных кампаний Aarki.**Параметр ссылки атрибуции:** af\_ad
* <span id="01ECJ9TJKGC25XCE8GEB04ZE0P"></span>**Adset** — задайте названия групп объявлений, чтобы сравнивать разные группы объявлений в рамках определенных кампаний RZR.**Параметр ссылки атрибуции:** af\_adset
* <span id="01ECJ9TJKGWG1QBKJ9MVW4Q5FG"></span>**Site ID** и **Sub Site ID** — задайте параметр Site ID, чтобы атрибутировать установки конкретным паблишерам. При наличии большого количества паблишеров рекомендуется ограничить количество используемых идентификаторов сайтов и использовать параметр идентификатора подсайта, чтобы <Anchor target="_blank" href="/marketers/ru/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit"><span id="01ECJ9TJKGEPHEXZ60NAN9JPWG"></span>не превысить ограничения по количеству идентификаторов сайтов</Anchor>.**Параметры ссылки атрибуции:** af\_siteid и af\_sub\_siteid
* <span id="01ECJ9TJKGQPS0GAY5SY562VFS"></span>**Subscriber Parameters** — используйте любой из 5 параметров подписчика, чтобы вставить полезные значения. Обратите внимание, что эти параметры анализируются и отображаются в отчете о сырых данных, что делает их очень удобными для агрегации или фильтрации данных.**Параметры ссылки атрибуции:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<span id="01ECJ9TJKGQN0Y1H6F2WNHRBCV"></span>Если нужно добавить в ссылку атрибуции другой параметр, просто введите его в поле нового параметра. Дополнительные сведения <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">**<span id="01ECJ9TJKG3AQCMW2FDDZ7HWWB"></span>о структуре и параметрах ссылки атрибуции AppsFlyer**</Anchor>.

### Настройки ретаргетинга

<span id="01ECJ9TJKG820HKXXZTS89ES65"></span>При активации AppsFlyer распознает ссылку как ссылку атрибуции для <Anchor target="_blank" href="/marketers/ru/docs/retargeting-attribution-guide"><span id="01ECJ9TJKGRTSNR53S5XX76K61"></span>ретаргетинга</Anchor>, а не как ссылку для привлечения пользователей, добавляя параметр &is\_retargeting=true к ссылке регистрации кликов. Обратите внимание, что ретаргетинг в настоящее время поддерживается только для атрибуции по кликам, а не по просмотрам.**Параметр ссылки атрибуции:** is\_retargeting.

<span id="01ECJ9TJKGPRH6P36208EH0C44"></span>Когда ретаргетинг активирован, отображаются следующие настройки.

<span id="01ECJ9TJKH63B6KS5WE93F0SMM"></span>1. Стандартная ссылка и ссылка OneLink

<span id="01ECJ9TJKHH7YZCNS0P0TT0B45"></span>Вариант ***стандартная ссылка атрибуции*** следует выбирать в следующих случаях:

* <span id="01ECJ9TJKHCZFTSWGGC2XHW6N5"></span><span id="01ECJ9TJKHP90T48TJPV80AP2T"></span>URL-адрес не будет использоваться в качестве глубинной ссылки или
* <span id="01ECJ9TJKHYPT6RQ5NTVPV8FA2"></span>Если планируете использовать для диплинкинга только <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"><span id="01ECSNC07ND552HVWJD2GF8YSD"></span>схемы URI</Anchor>

<span id="01ECJ9TJKH6GTCN390D87MYPHV"></span>Вариант ***Use OneLink*** следует выбирать в следующих случаях:

* <span id="01ECJ9TJKHVJCE2XM6X6AJS4YY"></span><span id="01ECJ9TJKHSJAC8HW8YERAKDVC"></span>Для приложений на Android и iOS используется одна и та же ссылка или
* <span id="01ECJ9TJKH0W7PXF4EJKM20ZRQ"></span>Для диплинкинга используются универсальные ссылки или ссылки приложений

<span id="01ECJ9TJKHEDATPHFM1EN5NZFQ"></span>Обратите внимание, что при выборе OneLink ссылка для регистрации кликов меняется со ссылки для конкретного приложения на <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide"><span id="01ECJ9TJKHQTEYP3PPXHVWYF9V"></span>URL-адрес OneLink</Anchor>.

<span id="01ECJ9TJKH59CKTD3ZNMZ37W09"></span>2. URL-адрес диплинка

<span id="01ECJ9TJKHKQMJFN1Z3G7JTN5V"></span>Используйте это поле, если ссылка предназначена для диплинкинга пользователей к определенной активности в вашем приложении.**Параметр ссылки атрибуции:** af\_dp Дополнительные сведения о решении AppsFlyer для диплинкинга см. в <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink"><span id="01ECJ9TJKHK7S19JDRMS3Z318C"></span>этом руководстве.</Anchor>

<span id="01ECJ9TJKH1QVW9NG1P4JY165N"></span>3. Окно повторного вовлечения

<span id="01ECJ9TJKHAZ5N1Y7NACJPMT4S"></span>Задайте временной интервал после повторного вовлечения, в течение которого внутренние события приложения пользователя будут атрибутироваться медиа-источнику ретаргетинга. Вы можете задать ценность, значение в днях (1-90), часах (до 23) или даже на весь период.

<span id="01ECJ9TJKH449C02X1Y3ESR48Y"></span>**Параметр ссылки атрибуции:** af\_reengagement\_window

### Атрибуция по кликам

<span id="01ECJ9TJKHGWANE9EGZZ0KKEX9"></span>На этой шкале можно задать **максимальное время от клика до установки**. К RZR атрибутируются только те установки (первые запуски), которые произошли в пределах окна атрибуции/лукбэка.

<span id="01ECJ9TJKHF1JQM37P7SAYP8G6"></span>**Параметр ссылки атрибуции:** af\_click\_lookback

<span id="01ECJ9TJKHY557S7J91YTE5VH8"></span>Подробные сведения об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows"><span id="01ECJ9TJKHWEDC7RP2ZHHPFDNV"></span>окне атрибуции по кликам см. здесь</Anchor>.

### Ссылка атрибуции для клика

<span id="01ECJ9TJKJ6TJBPEP5JNEPYTVB"></span>Это ссылка атрибуции, которая содержит все заданные для нее настройки. Отправьте ее в RZR для активации, когда лиды кликают по соответствующей рекламе.

### Окно лукбэк на основе просмотров

<span id="01ECJ9TJKJVDX13ZVFH8T5BVG7"></span>На этой шкале можно задать **максимальное время от показа до установки**. К RZR атрибутируются только те установки (первые запуски), которые произошли в рамках окна атрибуции после показа рекламы, при условии отсутствия других релевантных кликов по объявлению.

<span id="01ECJ9TJKJ1JEA3HME63V9EWA0"></span>Это значение можно задать в часах (от 1 до 23) или в днях (от 1 до 7).

<span id="01ECJ9TJKJB20VJH63A8NK3KGB"></span>**Параметр ссылки атрибуции:** af\_viewthrough\_lookback

<span id="01ECJ9TJKJNTQ7AJVYKVWYMJNZ"></span>Подробные сведения об <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows"><span id="01ECJ9TJKJX8GHDCAW0QQYD4BV"></span>атрибуции по просмотрам см. здесь</Anchor>.

### Ссылка на атрибуцию показов

<span id="01ECJ9TJKJ34K4MSK1BK687Q9Y"></span>Ссылка атрибуции показа содержит такие же данные атрибуции, как и ссылка регистрации кликов (за исключением другого окна атрибуции). Отправьте ее в RZR для активации при просмотре соответствующей рекламы, обычно в течение 1 секунды или более.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

AppsFlyer получает информацию о затратах через API. Подробную информацию <Anchor target="_blank" href="/marketers/ru/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">о поддерживаемых параметрах, метриках и функциях см. в</Anchor> таблице интеграции затрат рекламной сети. **Примечание**. Для получения сведений о затратах требуется подписка ROI360.

**Чтобы включить API данных о затратах:**

* Следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">этим инструкциям по интеграции</Anchor>.

<Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#статус-api-затрат">Просмотрите статус вашего API данных о затратах</Anchor> и время, когда AppsFlyer получил соответствующие данные о затратах в последний раз, либо на дэшборде статуса интеграции затрат (и доходов от рекламы), либо на дэшборде отдельной рекламной сети. 

#### Предупреждение

<span id="01ECJ9TJKQX7K80360QJ9RACV1"></span>После настройки данных о затратах в RZR не изменяйте название какой-либо запущенной кампании, группы объявлений или отдельного объявления, так как это может привести к серьезным расхождениям или отсутствию данных о затратах.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

<span id="01ECJ9TJKQNQBY77FTTFRZ0PGS"></span>Данные Ad Revenue не поддерживаются RZR.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

<span id="01ECJ9TJKQ8FK7KPD84RHW11HQ"></span>На этой вкладке можно выбрать разрешения для RZR в зависимости от того, в каком качестве выступает партнер: как рекламная сеть, агентство или и то, и другое. Обратите внимание, что, даже если атрибуция для RZR отключена, вкладка разрешений остается активной, и вы можете предоставить RZR контроль.

<span id="01ECJ9TJKQFJM45QTAMC6AJQW3"></span>Используйте эти переключатели, чтобы уполномочить рекламную сеть самостоятельно обрабатывать конфигурацию для вашего приложения:

### Ad Network Permissions (Разрешения для рекламной сети)

* <span id="01ECJ9TJKQAHY9CZ2H3W09GQPZ"></span>***<span id="01ECJ9TJKQXT4HNE0HKH13F4SX"></span>Разрешить настройку интеграции*** — разрешить партнеру настраивать вкладку интеграции (за исключением постбэков по внутренним событиям приложения)
* <span id="01ECJ9TJKRMQDVQV6EJAEC8DPG"></span><span id="01ECJ9TJKQKZVDT6A960BMPW5Q"></span>***Разрешить настройку постбэков по внутренним событиям приложения*** — разрешить партнеру настраивать постбэки по внутренним событиям и отображать эти настройки на вкладке интеграции.
* <span id="01ECJ9TJKRKVWZG0WYVK1533A9"></span><span id="01ECJ9TJKQYN16W3C8YYFM14XP"></span>***Разрешить доступ к своему отчету об удержании*** — доступ предоставляется только к собственным данным партнера.
* <span id="01ECJ9TJKQQSP4G7H71AZBQMXW"></span>***Разрешить доступ к своим сводным данным о лояльных пользователях*** — доступ предоставляется только к собственным данным партнера.
* <span id="01ECJ9TJKQXG55YJGYJV9AZFNH"></span>***Разрешить доступ к своим сводным данным о внутренних событиях приложения*** — доступ предоставляется только к собственным данным партнера.
* <span id="01ECJ9TJKQ9809CG0G2QK43RGQ"></span>***Разрешить доступ к своим сводным данным о доходах*** — доступ предоставляется только к данным о доходах, атрибутированных партнеру.
* <span id="01ECJ9TJKQZJGSVZMKFDHE2ACJ"></span>***Разрешить доступ к панели управления Protect360*** — доступ предоставляется только к собственным данным Protect360 этого партнера, при условии что эта функция активирована для рекламодателя.

<span id="01ECJ9TJKQJ0Y1QQK4EM92C06V"></span>См. дополнительные сведения о предоставлении <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab"><span id="01ECJ9TJKQZ5ADC4QSTHP0KN95"></span>разрешений рекламной сети</Anchor>.

### Разрешения агентства

<span id="01ECJ9TJKRNETK1FH4ZRSNE1V4"></span>Эти переключатели позволяют предоставить агентству право самостоятельно выполнять настройки для вашего приложения:

* <span id="01ECJ9TJKRADJZ8B7KNZH0HSQQ"></span>***<span id="01ECJ9TJKR3ZRZX5W0KD91BFV3"></span>Главный переключатель*** — установите в положение «Включено», чтобы получить доступ к списку <span id="01ECJ9TJKRMD549KXA59E682CH"></span>разрешений для агентства
* ***Разрешить настройку постбэков по внутренним событиям приложения*** — разрешить агентству настраивать сопоставление постбэков по внутренним событиям приложения с самим собой на вкладке интеграции
* <span id="01ECJ9TJKRF7NMH6E1NDZ57S0E"></span>***Разрешить доступ к агрегированным органическим данным***
* ***Разрешить доступ к своему отчету об удержании*** — доступ предоставляется только к собственным данным агентства об удержании

<span id="01ECJ9TJKRS878CPXQYSBAJCA1"></span>См. дополнительные сведения о предоставлении <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#разрешения-агентства">разрешений для агентства</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-aarki=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-rzr h_01HJR5M5C0P759S4X5SSJCY501=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-rzr h_01J4KVYPZMZWJKV6KZQHNBZV0T=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 01ECJ9TJKE15MJE7WS26VP52A0=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01J4KWRE6ECKEWEG4WP10N3BF7=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 01ECJ9TJKFGQQVWA7SA3PRS690=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E 01ECJ9TJKF7G9KMGMGMAD414ZF=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F 01ECJ9TJKFWH38NKYPDEZR4FRV=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01J4KVYPZMF0CZMR1PTS97JNNJ=attribution-link-tab attribution-link-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01ECJ9TJKFD91X9DQXB8PV3840=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 retargeting-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 01ECJ9TJKGJF1FS642MEM6WX4A=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D1%80%D0%B5%D1%82%D0%B0%D1%80%D0%B3%D0%B5%D1%82%D0%B8%D0%BD%D0%B3%D0%B0 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC 01ECJ9TJKHWMXAZYWNMVPDS8NY=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC click-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 01ECJ9TJKJ0EQE45TB9S0WS2ZB=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0 viewthrough-attribution-lookback-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 01ECJ9TJKJ72AN26F2FQ8VVKQ4=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 impressions-attribution-link=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 01ECJ9TJKJZV9PADNEETA6GFRZ=%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B0-%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2 h_01J4KVYPZMEDPXBXYFVT85AJ67=cost-tab warning=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 01ECJ9TJKQ8A7BFZR3MJ5H35CA=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01J4KVYPZMQHGHDPEE1Q5M1KX8=ad-revenue-tab h_01J4KVYPZMRFMNCR61M4Z4388Y=permissions-tab ad-network-permissions=ad-network-permissions-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 01ECJ9TJKQ9E3A5863Z3TRVAWZ=ad-network-permissions-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 agency-permissions=%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0 01ECJ9TJKQ0SAV4ZJB8DFRTE5C=%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0" />

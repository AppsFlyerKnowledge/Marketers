---
title: Правила атрибуции медиаисточников PBA
metadata:
  keywords:
    - media source
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-09-03T07:30:08Z'
  edited_at: '2026-08-31T00:23:03Z'
  id: 360002386997
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/360002386997
---
> **Краткий обзор**. Измеряйте результаты маркетинговых активностей и привлекайте на сайт эффективный трафик. Какие медиа-источники, типы и каналы трафика приносят посещения сайта и события конверсии. Доступны метрики на уровне рекламного объявления.

![Touchpoints_us-en.png](https://files.readme.io/45c45c9a1b108ea31e450df4c2aaab20482c9829726d9860e55e2c9ca32c401a-360008629017.png)

<div id="website-visits-and-web-events" />

## Посещения сайта и веб-события

* **Распознавание посещения:** PBA регистрирует посещение в соответствии с [правилами распознавания посещений.](/docs/pba-media-source-attribution-rules#visit-recognition-rules)
* **Атрибуция посещений**
  * Чтобы определить медиаисточник, ответственный за привлечение пользователя на сайт, PBA анализирует query parameters на URL и HTTP-рефереры документов, собранные веб SDK.
  * Определение медиаисточника на основе правил использует данные, собранные и описанные в этой статье. Аналогичным образом определяются тип медиа и медиа-канал.
  * Это посещение регистрируется в <Anchor target="_blank" href="/marketers/ru/docs/pba-raw-data-reports">сырых данных PBA</Anchor>.
* **Информация о кампании** извлекается из:
  * Параметры запроса с использованием медиаисточника
  * Gclid (если доступен) с использованием <Anchor target="_blank" href="/marketers/ru/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">интеграции с Google Ads</Anchor>
* **Веб-событие**
  * Веб-событие происходит, когда посетитель выполняет действие на сайте, например поиск продукта, выбор продукта или покупку.
  * События атрибутируются посещению последнего непрямого веб-посещения, произошедшего в течение 30-дневного ретроспективного окна.
  * События подразделяются на:   
    * **События конверсии**: значимые события, определенные маркетологом. Например, покупка или регистрация.
    * **Стандартные события**: другие события.
  * Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/pba-website-attribution-url-best-practices">практических рекомендациях по URL-адресам атрибуции для сайта PBA</Anchor>.

Дэшборды PBA и отчеты о сырых данных используют атрибутированные медиаисточники, типы, каналы и кампании.

![MediaSource_us-en.png](https://files.readme.io/bcb3e471753809b0fdf1a0e1dc9783002004b1988f4701ab30524c1eb7b9fbfc-360008629057.png)

Для удобства понимания в следующей таблице приведены примеры определенных медиаисточников с указанием их типа и канала.

| Медиаисточник | ID аккаунта сети | Дополнительная причина блокировки |
| --- | --- | --- |
| Прямые заходы | Отток | Прямые заходы |
| <ul><li>Социальный: Facebook</li><li>Социальный X (ранее Twitter)</li></ul> | Собственные | Социальные сети |
| <ul><li>Meta реклама</li><li>Twitter</li></ul> | Платный | Социальные сети |
| Поиск Google | Отток | Органический поиск |
| Электронная почта | Собственные | Электронная почта |
| googleadwords\_int | Платный | Рекламное объявление |
| usatoday.com | Отток | Реферал |

<div id="determining-the-media-source" />

## Определение медиаисточника

PBA определяет медиаисточник, тип медиа и медиаканал в иерархическом порядке. Это означает определение соответствующего правила медиаисточника и самого медиаисточника. Затем определяются тип медиа и медиаканал.

<div id="media-source-rules" />

<Accordion title="Правила медиаисточника">

Правила медиаисточника, показанные в следующей таблице, ранжируются от более высокого приоритета к более низкому:

<Table>
  <thead>
    <tr>
      <th>
        Правило медиаисточника
      </th>
      <th>
        Определение медиаисточника
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Предотвращение самоатрибуции
      </td>
      <td>
        Чтобы предотвратить атрибуцию событий самому веб-сайту (самоатрибуцию) и другим связанным доменам, используется список <Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings#domain-exclusion">исключения доменов</Anchor>. Список состоит из:

        * Основной домен: определяется URL-адресом веб-приложения, включенного в пакет бренда
        * Внутренние домены: домены, входящие в состав бренда
        * Внешние домены: платежные шлюзы и сайты обработки платежей, заданные вами, а также некоторые домены, например PayPal и Stripe, заданные AppsFlyer, исключаются автоматически
      </td>
    </tr>
    <tr>
      <td>
        pid
      </td>
      <td>
        Преобразуется в значение pid в URL-адресе. Для некоторых SRN pid преобразуется в коммерческое название SRN для единообразия и ясности. Например, pid=facebook\_int преобразуется в Facebook Ads, а twitter\_int — в Twitter.
      </td>
    </tr>
    <tr>
      <td>
        4. ID кликов
      </td>
      <td>
        Крупные рекламные сети, такие как Google, используют идентификаторы кликов для автоматической маркировки кампаний. Идентификаторы кликов преобразуются следующим образом:

        * **gclid:** <Anchor target="_blank" href="https://support.google.com/searchads/answer/7342044?hl=en">идентификатор клика Google</Anchor> преобразуется в *googleadwords\_int*. Примечание! *Решение GCLID официально не поддерживается Google и в будущем может быть выведено из эксплуатации.*
        * **dclid**: идентификатор клика DoubleClick преобразуется в *doubleclick\_int.*
        * **msclkid:** <Anchor target="_blank" href="http://help.ads.microsoft.com/apex/index/3/en/60000">Идентификатор клика Bing</Anchor> преобразуется в *bingsearch\_int*.
      </td>
    </tr>
    <tr>
      <td>
        Параметры UTM
      </td>
      <td>
        **Пользовательские правила UTM**

        | utm\_source | utm\_medium | Медиаисточник |
        | --- | --- | --- |
        | * | * email, mail, e-mail<br />* Внимание! Если utm\_medium содержит одно из этих значений, utm\_source игнорируется. | Электронная почта |
        | google | cpc/ppc/paidsearch/search | googleadwords\_int |
        | google | cpm/display/banner/video/listing | doubleclick\_int |
        | dfa / dbm | CPM | doubleclick\_int |
        | facebook | cpc/ppc/cpm/cpa/paidsocial/paid-social | Реклама в Facebook |
        | bing | cpc | bingsearch\_int |
        | yahoo / gemini | cpc/display/listing | yahoogemini\_int |
        | Twitter | cpc | Twitter |
        | snapchat | swipe | snapchat\_int |
        | pinterest | cpc | pinterest\_int |

        Если пользовательское правило не найдено, медиаисточник определяется по значению параметра utm\_source.

        <Anchor target="_blank" href="https://en.wikipedia.org/wiki/UTM_parameters">Информация о параметрах UTM</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Реферер
      </td>
      <td>
        Реферер — это HTTP-источник, который привел пользователя на сайт. Медиаисточник — это доменное имя реферера.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="media-source-type" />

<Accordion title="Тип медиа-источника">

Маркетологи обычно делят веб-медиаисточники на три типа:

* **Платные:** рекламные кампании, такие как медийные баннеры, видео и поисковая реклама.
* **Собственные:** маркетинговые кампании из собственных медиа, например email-кампании, публикации в социальных сетях и блоги.
* **Earned:** прямой или органический трафик из поисковых систем, реферальный трафик и фактический прямой трафик.

Тип медиа определяется на основе применяемого правила для медиаисточника в сочетании с параметрами медиаисточника/другими параметрами.

<table><thead><tr><th>Применимое правило медиаисточника</th><th>Медиаисточник</th><th>ID аккаунта сети</th></tr></thead><tbody><tr><td colspan="1" rowspan="2"><div>pid</div></td><td><p>Правило pid определяет, каким является медиаисточник: </p><ul><li>Социальный: Facebook</li><li>Социальный: X (ранее Twitter)</li><li>СМС</li><li>блог</li><li>Электронная почта</li></ul></td><td>Собственные</td></tr><tr><td>Любой другой медиаисточник</td><td>Платный</td></tr><tr><td>Идентификатор ID клика</td><td><p><span>Определяется с помощью идентификатора ID клика:</span></p><ul><li>gclid</li><li>dclid</li><li>msclkid</li></ul></td><td>Платный</td></tr><tr><td colspan="1" rowspan="2"><div>UTM</div></td><td>Пользовательские правила UTM определяют медиаисточник</td><td>Платный</td></tr><tr><td>Любой другой медиаисточник</td><td>Собственные</td></tr><tr><td rowspan="2">Реферер</td><td><p><span>Значение домена реферера — одно из следующих:</span></p><ul><li>googleads.g.doubleclick.net </li><li>tpc.googlesyndication.com</li></ul></td><td><p>Платный</p></td></tr><tr><td><span>Любой другой медиаисточник </span></td><td><p>Отток</p></td></tr></tbody></table>

</Accordion>

<div id="media-source-channel" />

<Accordion title="Канал медиаисточника">

Медиа-канал определяется по правилам, перечисленным здесь.

<table><thead><tr><th>Приоритет</th><th>Правило медиа-канала</th><th>ценности, значения</th><th>Дополнительная причина блокировки</th></tr></thead><tbody><tr><td rowspan="4">Самый высокий приоритет</td><td rowspan="4">Медиаисточник соответствует одному из указанных значений</td><td>Прямые заходы</td><td>Прямые заходы</td></tr><tr><td><ul><li>Поиск Google</li><li>Поиск Yahoo</li><li>Поиск Bing</li></ul></td><td>Органический поиск</td></tr><tr><td><ul><li>facebook</li><li>Twitter</li><li>snapchat</li><li>pinterest</li><li>LinkedIn</li><li>whatsapp</li></ul></td><td>Социальные сети</td></tr><tr><td>Электронная почта</td><td>Электронная почта</td></tr><tr><td> </td><td>Тип медиа — платный</td><td> </td><td><div>Рекламное объявление</div></td></tr><tr><td> </td><td>Медиаисточник определяется по рефереру</td><td> </td><td>Реферал</td></tr><tr><td>Самый низкий приоритет</td><td>Ни одно из предыдущих условий не выполнено</td><td> </td><td>Рассчитанный процент комиссии, который магазин получает от купленного продукта.</td></tr></tbody></table>

</Accordion>

<div id="determine-the-campaign" />

<Accordion title="Определить кампанию">

* Кампании определяются следующим образом: 
  * Параметры URL-адреса кампании в соответствии с параметрами URL-адреса для каждого медиаисточника.
  * Идентификатор клика gclid и использование <Anchor target="_blank" href="/marketers/ru/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Ads</Anchor> интеграции
* Если соответствующий параметр кампании не найден в URL-адресе, то кампания не определяется.

| Используемый параметр медиаисточника | Используемый параметр кампании |
| --- | --- |
| pid | Параметры медиаисточника AppsFlyer, доступные в URL-адресе, используются для заполнения сырых данных и дэшборда Website Attribution. Доступные параметры: af\_c\_id, af\_adset, af\_adset\_id, af\_ad\_id |
| Идентификатор клика — gclid | Получается через API из Google Ads |
| utm\_source | utm\_campaign |

</Accordion>

<div id="additional-attribution-rules" />

## Дополнительные правила атрибуции

<div id="visit-recognition-rules" />

<Accordion title="Правила распознавания посещений">

Посещение сайта регистрируется по следующим правилам с учетом статуса текущей сессии. Активная сессия — это сессия, в которой период неактивности составляет менее 30 минут.

* Не регистрируйте посещение, если пользователь пришел с <Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings#domain-exclusion">внешнего исключенного</Anchor> домена.
* Во время активной сессии: регистрируйте посещение, если загрузка страницы включает медиаисточник.
* Если нет активной сессии, регистрируется посещение.
* Минимальное время посещения не установлено.

**Правила регистрации посещений PBA**

![PBA_-_PBA-vist.png](https://files.readme.io/651c3ee4d39832297b7d6dc871aa281f1fa3219264ba264851ad0cc643b8baee-360015532817.png)

</Accordion>

<div id="data-finalization" />

<Accordion title="Финализация данных">

* Финализация данных:
  * Для Web-Assisted Installs и Website Attribution PBA определяет дополнительные связанные события в течение первых 7 дней после конверсии. Это может изменить медиаисточник, определенный как тот, который в конечном итоге привел к конверсии.
  * В связанных отчетах по сырым данным поле *final\_data* имеет значение false в течение начального 7-дневного периода.

</Accordion>

<div data-zendesk-anchors="website-visits-and-web-events=%D0%BF%D0%BE%D1%81%D0%B5%D1%89%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%B0%D0%B9%D1%82%D0%B0-%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F h_01H936NV7VP8CTE9BZP6D5E7NK=%D0%BF%D0%BE%D1%81%D0%B5%D1%89%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%B0%D0%B9%D1%82%D0%B0-%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F determining-the-media-source=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0 h_01H936NV7VZHWBDPHFJRFFCPSW=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0 h_01H936NV7V6GMWSCHNDMJ205JS=media-source-rules h_01H936NV7W9ZFMET29GY6JTBGN=media-source-type h_01H936NV7W61DB43D3E1MNEJHN=media-source-channel h_01H936NV7WZYE3EKYZ9PX9ZJXW=determine-the-campaign additional-attribution-rules=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01H936NV7WA9WZM4RTQZHD22VV=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01H936NV7W323HQMG5E6SQFQEN=visit-recognition-rules h_01H936NV7WSB2FMRBPDN936TWM=data-finalization" />

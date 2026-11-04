---
title: Выберите параметры атрибуции для URL-адресов целевых страниц.
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T16:46:08Z'
  edited_at: '2026-08-19T00:22:33Z'
  id: 43525434385809
  locale: ru
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ru/articles/43525434385809
---
> **Краткий обзор:** Используйте единообразные и полные параметры URL в ссылках, ведущих на целевые страницы вашего сайта, чтобы получить максимально детализированные данные о кампаниях и при этом обеспечить точную атрибуцию в Web Performance Measurement.

<div id="about-url-attribution-parameter-classes" />

## О классах параметров URL для атрибуции

AppsFlyer считывает параметры кампани из URL вашей целевой страницы (ссылка, по которой приходит пользователь) и использует их для атрибуции сессий и событий к правильному **медиаисточнику** , **кампании** и (при наличии данных) более низким уровням иерархии, таким как **группа объявлений** и **объявление** .

Указанные вами параметры определяют результаты измерения эффективности вашей кампании. Иными словами, одна и та же целевая страница может давать совершенно разные результаты в зависимости от того, какие параметры вы включили.

Параметры URL-адреса могут принадлежать одному из двух классов: PID и UTM.

* Класс PID включает параметры URL AppsFlyer.
* Класс UTM включает стандартные параметры UTM.

Для получения дополнительной информации о том, как Web Performance Measurement обрабатывает параметры URL , см. раздел <Anchor target="_blank" href="/marketers/ru/docs/about-traffic-source-resolution">«Об определении источника трафика»</Anchor> .

<div id="supported-pid-and-utm-parameters" />

### Поддерживаемые параметры PID и UTM.

Web Performance Measurement поддерживает следующие параметры.

| № | Параметр | Используется для | Класс параметров | Доступно на дэшборде | Поле сырых данных |
| --- | --- | --- | --- | --- | --- |
| 1 | `pid` | Медиаисточник | pid | Да | `медиа-источник` |
| 2 | `c` | Название кампании | pid | Да | `campaign_name` |
| 3 | `af_c_id` | ID кампании | pid | Да | `campaign_id (идентификатор кампании)` |
| 4 | `af_adset` | Название блока рекламы | pid | Да | `adset_name` |
| 5 | `af_adset_id` | ID блока рекламы | pid | Да | `adset_id (идентификатор группы объявлений)` |
| 6 | `af_ad` | Название рекламного объявления | pid | Да | `ad_name` |
| 7 | `af_ad_id` | ID рекламного объявления | pid | Да | `ad_id (идентификатор объявления)` |
| 8 | `utm_source` | Медиаисточник | UTM | Да | `медиа-источник` |
| 9 | `utm_medium` | Тип медиа | UTM | Нет | `media_type` |
| 10 | `utm_campaign` | Название кампании | UTM | Да | `campaign_name` |

<div id="choose-the-right-attribution-parameters" />

## Выберите правильные параметры атрибуции

AppsFlyer независимо оценивает параметры URL для каждого поля отчета (например, «Медиаисточник» или «Кампания») в соответствии с определенным порядком приоритетности. Этот подход позволяет поддерживать атрибуцию AppsFlyer наряду с другими инструментами, такими как Google Analytics, используя как **класс PID** (собственный для AppsFlyer), так и **класс UTM** (стандартный маркетинговый) в одном и том же URL.

Web Performance Measurement проверяет порядок приоритета для каждого поля по отдельности. Если параметр из класса PID с более высоким приоритетом отсутствует для определенного атрибута, система автоматически использует соответствующий параметр из класса UTM, чтобы определить правильное значение для этого поля.

<div id="scenario-a-url-with-pid-class-only-appsflyer-reporting" />

<Accordion title="Сценарий А. URL только с классом PID (отчетность AppsFlyer)">

Использовать класс PID, если вашей основной целью является отчетность в AppsFlyer .

<div id="example" />

#### Пример

```http
www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}
```

**Результат:** AppsFlyer определяет медиаисточник, используя`pid` и кампанию с использованием`c`.

</Accordion>

<div id="scenario-b-url-with-utm-class-only-fallback" />

<Accordion title="Сценарий B. URL-адрес только с UTM-классом (резервный вариант)">

Если`pid` отсутствует, AppsFlyer использует класс UTM.

<div id="example-1" />

#### Пример

```http
 www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}
```

**Результат:** AppsFlyer определяет медиаисточник, используя`utm_source` и кампанию с использованием`utm_campaign`.

</Accordion>

<div id="scenario-c-url-with-both-pid-and-utm-classes" />

<Accordion title="Сценарий C. URL-адрес с классами PID и UTM.">

AppsFlyer позволяет включать параметры из разных классов (например, PID и UTM) в один и тот же URL. Это полезно, когда вам необходимо поддержать атрибуцию AppsFlyer наряду с другими аналитическими инструментами, такими как Google Analytics или внутренние системы измерения.

AppsFlyer обрабатывает поля атрибуции, такие как «Медиаисточник» и «Кампания», независимо друг от друга. Для каждого конкретного поля система использует алгоритм определения приоритетов для записи соответствующего значения. Как правило, для данного поля **класс PID** имеет приоритет над **классом UTM** .

<div id="example-1-overlapping-parameters" />

#### Пример 1: Пересекающиеся параметры

```http
www.website.com?pid=facebook_ads&c=summer_sale&utm_source=facebook&utm_campaign=seasonal_promo
```

* **Медиаисточник:** AppsFlyer обнаруживает`utm_source` . Поскольку нет эквивалентного класса PID (`pid` ), он записывает`facebook` из класса UTM.
* **Кампания:** AppsFlyer обнаруживает`c` . Поскольку нет эквивалента класса UTM (`utm_campaign` ), он записывает`summer_sale` из класса PID.
* **Результат:** AppsFlyer использует значения из класса PID с более высоким приоритетом, при этом внешние инструменты по-прежнему могут считывать значения UTM.

<div id="example-2-mixed-parameter-classes" />

#### Пример 2: Смешанные классы параметров

```http
www.website.com?utm_source=facebook&c=summer_sale
```

* **Медиаисточник:** AppsFlyer обнаруживает оба варианта.`Так как эквивалент класса PID (pid) отсутствует, система записывает facebook из класса UTM.`
* **Кампания:** AppsFlyer обнаруживает оба варианта.`c` и`utm_campaign` . Так как эквивалент класса UTM (`utm_campaign`) отсутствует, система записывает `summer_sale` из класса PID.
* **Результат:** AppsFlyer успешно атрибутирует событие, используя значения из обоих классов, поскольку значение каждого поля определяется независимо.

</Accordion>

<div id="other-best-practices" />

## Другие рекомендации

<div id="keep-parameter-values-in-a-consistent-case" />

<Accordion title="Соблюдайте единый регистр значений параметров">

Значения параметров **чувствительны к регистру** . Например,`utm_source=channel1` и`utm_source=CHANNEL1` рассматриваются как **разные медиаисточники** .

Практические рекомендации: Определите единый регистр для значений параметров (обычно используется нижний регистр) и применяйте его во всех URL.

</Accordion>

<div id="use-question-marks-only-once" />

<Accordion title="Используйте знаки вопроса только один раз.">

Правила:

* Использовать только **один** знак вопроса (`?`) перед параметрами запроса в URL.
* Не используйте дополнительные знаки вопроса в URL.

Правильно:

* `www.website.com?parameters`

Неправильно:

* `www.website.com??parameters`
* `www.website.com?parameter1?parameter2`

</Accordion>

<div id="don-t-use-anchor-signs" />

<Accordion title="Не используйте символ решетки (#)">

Не используйте символ решетки (`#` ) в URL.

Почему: параметры после `#` могут не загружаться и не регистрироваться веб-SDK.

</Accordion>

<div data-zendesk-anchors="about-website-attribution-urls=%D0%BE-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0%D1%85-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-url-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01KGMRXNWGXQ3CH5XGSREV6Z3R=%D0%BE-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D0%B0%D1%85-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-url-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 supported-pid-and-utm-parameters=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-pid-%D0%B8-utm h_01KGMRXNWG88REW1CVJ4XMYFHQ=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-pid-%D0%B8-utm choose-the-right-attribution-parameters=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01KGMRXNWGP1SFBWE3KG6VRZ9V=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01KGMRXNWGT9MS799QH9EP29XR=scenario-a-url-with-pid-class-only-appsflyer-reporting example=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01KGMS1RMN3F1D0Q7HDZMGG19E=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01KGMRXNWG0T3YCK0RPKX4B3BT=scenario-b-url-with-utm-class-only-fallback example::4f5c28b5=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-1 h_01KGMS215ARDSY6NFQ8VEF6C2Y=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-1 h_01KGMRXNWGZH2ZBP9XR8C8TNFN=scenario-c-url-with-both-pid-and-utm-classes example-1-overlapping-parameters=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-1-%D0%BF%D0%B5%D1%80%D0%B5%D1%81%D0%B5%D0%BA%D0%B0%D1%8E%D1%89%D0%B8%D0%B5%D1%81%D1%8F-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B h_01KGMS10B1QCRJ5N28FBNEEKR2=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-1-%D0%BF%D0%B5%D1%80%D0%B5%D1%81%D0%B5%D0%BA%D0%B0%D1%8E%D1%89%D0%B8%D0%B5%D1%81%D1%8F-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B example-2-mixed-parameter-classes=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-2-%D1%81%D0%BC%D0%B5%D1%88%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D1%8B-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2 h_01KGMS17B500RPGHSKJ1AJSYH8=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-2-%D1%81%D0%BC%D0%B5%D1%88%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BA%D0%BB%D0%B0%D1%81%D1%81%D1%8B-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2 other-best-practices=%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D0%B5-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D0%B0%D1%86%D0%B8%D0%B8 h_01KGMRXNWGVJY55M83FVMKBP1X=%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D0%B5-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D0%B0%D1%86%D0%B8%D0%B8 h_01KGMRXNWG9S03GGBDXPN34DDM=keep-parameter-values-in-a-consistent-case h_01KGMRXNWGEF9D0ZH5M81RP0PH=use-question-marks-only-once don%E2%80%99t-use-anchor-signs-=don-t-use-anchor-signs h_01KGMRXNWGX6HA0R9X3VC2WFXV=don-t-use-anchor-signs" />

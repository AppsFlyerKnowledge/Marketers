---
title: Лучшие практики для URL-адресов атрибуции веб-сайта PBA
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-05-23T05:29:27Z'
  edited_at: '2026-10-19T14:19:55Z'
  id: 6313062676497
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/6313062676497
---
> **Кратко:** лучшие практики по атрибуции кампаний атрибуции веб-сайта с максимально доступной детализацией кампаний.

<div id="pba-website-attribution-urls" />

## URL-адреса для атрибуции веб-сайтов PBA

Чтобы получить наилучшие результаты по детализации кампаний в сочетании с максимально точной атрибуцией в данных атрибуции веб-сайта, заполняйте URL-адреса (ссылки), по которым пользователи переходят на ваш веб-сайт, следуя рекомендациям, приведенным в этой статье.

<div id="url-parametersgroup-and-priority" />

### Параметры URL-адреса — группа и приоритет

Решение AppsFlyer для атрибуции веб-сайта поддерживает несколько классов параметров кампании. Классы ранжируются по приоритету следующим образом:

* [Высший приоритет] PID
* Идентификаторы кликов из определенных каналов, таких как Google, DoubleClick и Microsoft
* [Низший приоритет] UTM

<Anchor target="_blank" href="/marketers/ru/docs/pba-media-source-attribution-rules">Правила атрибуции медиаисточников PBA</Anchor> определяют, как атрибутируется конкретный пользователь. Классы параметров ранжируются по приоритету. Если в ссылке найдено более одного класса параметров, атрибуция присваивается классу с наивысшим приоритетом.

<div id="supported-parameters" />

#### Поддерживаемые параметры

| # | Параметр | Используется для | Класс параметра | Доступно на дэшборде | Поле сырых данных PBA |
| --- | --- | --- | --- | --- | --- |
| 1 | pid | Медиаисточник | pid | Д | медиа-источник |
| 2 | c | Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>. | pid | Д | campaign (кампания) |
| 3 | af\_c\_id | Строка | pid | Д | campaign\_id (идентификатор кампании) |
| 4 | af\_adset | название группы объявлений; | pid | Д | Извлечено из query\_params |
| 5 | af\_adset\_id | идентификатор группы объявлений (adset); | pid | Д | Извлечено из query\_params |
| 6 | af\_ad | Название рекламного объявления | pid | Д | Извлечено из query\_params |
| 7 | af\_ad\_id | Идентификатор | pid | Д | Извлечено из query\_params |
| 8 | utm\_source | Медиаисточник | UTM | Д | медиа-источник |
| 9 | utm\_medium | ID аккаунта сети | UTM | Д | media\_type |
| 10 | utm\_campaign | кампания; | UTM | Д | campaign (кампания) |

<div id="url-parameter-best-practices" />

## Лучшие практики использования параметров URL-адресов

<div id="selecting-url-parameters" />

### Выбор параметров URL-адреса

Каждый класс параметров функционирует изолированно. Поэтому, если вам нужны URL-адреса с несколькими классами, URL-адрес должен содержать соответствующие параметры каждого класса. Это позволяет оптимизировать детализацию отчетности.

Ниже показано, как используются параметры нескольких классов в контексте рекламы Meta:

* **Группа PID**:  `www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}`
* **Группа UTM**: `www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}`
* Если вы комбинируете классы, но включаете только часть обязательных параметров, AppsFlyer может не обеспечить полную детализацию. Например, если вы используете `www.website.com?utm_source=facebook&c={{campaign.name}}`, происходит следующее:
  * AppsFlyer использует класс UTM, поскольку класс PID отсутствует, и определяет медиаисточник с помощью utm\_source.
  * Однако кампанию определить нельзя, поскольку *c=* относится к классу PID, а pid не включен.
  * Чтобы решить эту проблему, если utm\_source нужен вам для других целей, рассмотрите такой вариант: `www.website.com?pid=facebook_int&c={{campaign.name}}&utm_source=facebook`. При такой структуре AppsFlyer использует класс PID для определения медиаисточника. Можно также включить другие параметры PID, например c=, а utm\_source будет проигнорирован, поскольку у него более низкий приоритет.

<div id="implement-dynamic-urls-using-ad-network-macros" />

### Используйте динамические URL-адреса с помощью макросов рекламной сети

Используйте макросы сети (также называемые valuetrack params), чтобы сэкономить время при создании шаблонов и применении параметров URL-адресов для платных кампаний.

Сети используют разные макросы для заполнения параметров в URL-адресах. Поэтому необходимо проверять документацию рекламной сети, чтобы убедиться, что вы используете макросы правильно. Например, если вы хотите передавать идентификатор кампании в af\_c\_id, можно не прописывать фактический идентификатор кампании вручную для каждого URL-адреса, а просто использовать макросы:

* Google Adwords: `www.website.com?af_c_id={campaignid}`
* Реклама Meta: `www.website.com?af_c_id={{campaign.id}}`
* Реклама Pinterest: `www.website.com?af_c_id={campaignid}`
* Реклама Snapchat: `www.website.com?af_c_id={{campaign.id}}`
* Реклама Microsoft (Bing): `www.website.com?af_c_id={campaignid}`

<div id="consistent-case-within-parameters" />

### Единый регистр в параметрах

Значения параметров чувствительны к регистру. Например, utm\_source=channel1 и utm\_source=CHANNEL1 считаются разными медиаисточниками. Поэтому проверяйте, что вы последовательно используете один и тот же регистр.

<div id="use-google-ads-integration-to-automate-granularity" />

### Используйте интеграцию Google Ads для автоматизации детализации

Для кампаний Google Ads вы можете получить детализацию кампании, интегрировав PBA со своим <Anchor target="_blank" href="/marketers/ru/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">аккаунтом Google Ads</Anchor>. Это гарантирует, что ваши данные будут заполнены всеми данными иерархии кампании без необходимости использовать PID или UTM-параметры в URL-адресе.

<div id="common-url-parameter-mistakes-to-avoid" />

## Распространенные ошибки в URL-параметрах, которых следует избегать

<div id="question-marks" />

### Вопросительные знаки

* Используйте только один вопросительный знак между целевой страницей URL-адреса и параметрами
* В URL-адресе не должно быть других вопросительных знаков

Например,  `www.website.com?параметры`

Примеры **неправильного** использования: 

`www.website.com??параметры`

`www.website.com?parameter1?parameter2`

<div id="anchor-signs" />

### Символы привязки

Символы привязки (#) не следует использовать в URL-адресе. Использование символа привязки в URL-адресе может привести к тому, что параметры после него не будут загружаться и не будут собираться нашим веб-SDK.

<div data-zendesk-anchors="pba-website-attribuiton-urls=url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%BE%D0%B2-pba h_01KQS4QK4Z70GC9VVFQCFHK4SQ=url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%BE%D0%B2-pba url-parameters%E2%80%94group-and-priority=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0--%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D0%B0-%D0%B8-%D0%BF%D1%80%D0%B8%D0%BE%D1%80%D0%B8%D1%82%D0%B5%D1%82 h_01KQS4QK4Z3YTXHGQMYNZ36DZ1=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0--%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D0%B0-%D0%B8-%D0%BF%D1%80%D0%B8%D0%BE%D1%80%D0%B8%D1%82%D0%B5%D1%82 supported-parameters=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B h_01KQS4QK4Z1RVQKZX94MJJQSQW=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B url-parameter-best-practices=%D0%BB%D1%83%D1%87%D1%88%D0%B8%D0%B5-%D0%BF%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%BE%D0%B2 h_01KQS4QK4Z3V5Y9RSM20VTESDP=%D0%BB%D1%83%D1%87%D1%88%D0%B8%D0%B5-%D0%BF%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%BE%D0%B2 selecting-url-parameters=%D0%B2%D1%8B%D0%B1%D0%BE%D1%80-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0 h_01KQS4QK4ZP6WCWEG4FH9R1N8Q=%D0%B2%D1%8B%D0%B1%D0%BE%D1%80-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%BE%D0%B2-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0 implement-dynamic-urls-using-ad-network-macros=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D1%83%D0%B9%D1%82%D0%B5-%D0%B4%D0%B8%D0%BD%D0%B0%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-%D0%BC%D0%B0%D0%BA%D1%80%D0%BE%D1%81%D0%BE%D0%B2-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 h_01KQS4QK50MTKRPPNYNWZKPMSD=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D1%83%D0%B9%D1%82%D0%B5-%D0%B4%D0%B8%D0%BD%D0%B0%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-%D0%BC%D0%B0%D0%BA%D1%80%D0%BE%D1%81%D0%BE%D0%B2-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 consistent-case-within-parameters=%D0%B5%D0%B4%D0%B8%D0%BD%D1%8B%D0%B9-%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80-%D0%B2-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%B0%D1%85 h_01KQS4QK50K5Q5NV2VQTASHDGD=%D0%B5%D0%B4%D0%B8%D0%BD%D1%8B%D0%B9-%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80-%D0%B2-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%B0%D1%85 use-google-ads-integration-to-automate-granularity=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D1%83%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-google-ads-%D0%B4%D0%BB%D1%8F-%D0%B0%D0%B2%D1%82%D0%BE%D0%BC%D0%B0%D1%82%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-%D0%B4%D0%B5%D1%82%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8 h_01KQS4QK505R1Y4TED19FWCY6M=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D1%83%D0%B9%D1%82%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8E-google-ads-%D0%B4%D0%BB%D1%8F-%D0%B0%D0%B2%D1%82%D0%BE%D0%BC%D0%B0%D1%82%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-%D0%B4%D0%B5%D1%82%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8 common-url-parameter-mistakes-to-avoid=%D1%80%D0%B0%D1%81%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D1%88%D0%B8%D0%B1%D0%BA%D0%B8-%D0%B2-url-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%B0%D1%85-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D1%8B%D1%85-%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D0%B5%D1%82-%D0%B8%D0%B7%D0%B1%D0%B5%D0%B3%D0%B0%D1%82%D1%8C h_01KQS4QK50XDC8216WBJJ6DJJ7=%D1%80%D0%B0%D1%81%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BE%D1%88%D0%B8%D0%B1%D0%BA%D0%B8-%D0%B2-url-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%B0%D1%85-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D1%8B%D1%85-%D1%81%D0%BB%D0%B5%D0%B4%D1%83%D0%B5%D1%82-%D0%B8%D0%B7%D0%B1%D0%B5%D0%B3%D0%B0%D1%82%D1%8C question-marks=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%B7%D0%BD%D0%B0%D0%BA%D0%B8 h_01KQS4QK50KAS1DVXASYB81PGJ=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%B7%D0%BD%D0%B0%D0%BA%D0%B8 anchor-signs=%D1%81%D0%B8%D0%BC%D0%B2%D0%BE%D0%BB%D1%8B-%D0%BF%D1%80%D0%B8%D0%B2%D1%8F%D0%B7%D0%BA%D0%B8 h_01KQS4QK507423MN3RWN94CWEY=%D1%81%D0%B8%D0%BC%D0%B2%D0%BE%D0%BB%D1%8B-%D0%BF%D1%80%D0%B8%D0%B2%D1%8F%D0%B7%D0%BA%D0%B8" />

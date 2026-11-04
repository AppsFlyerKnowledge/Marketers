---
title: Расхождения между AppsFlyer и сторонними платформами
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-10-16T08:59:17Z'
  edited_at: '2026-08-18T00:13:26Z'
  id: 19384888063249
  locale: ru
  section: Integrate 3rd-party platforms
  section_id: 6551084534545
  url: https://support.appsflyer.com/hc/ru/articles/19384888063249
---
> **At a glance:** **Краткий обзор:** Узнайте о причинах расхождений в атрибуции между AppsFlyer и сторонними платформами.

<div id="overview" />

## Обзор

Из-за политик обмена данными медиаисточников не все данные на уровне пользователя <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">передаются сторонним платформам</Anchor> (таким как аналитические и маркетинговые платформы). Из-за этого могут возникать несоответствия в атрибуции между данными, отображаемыми на сторонних платформах, и данными в AppsFlyer.

> 📘 **Note**
>
> **Примечание**
>
> Агрегированные и аналитические данные от платформы AppsFlyer доступны без ограничений.

<div id="postback-restrictions-on-third-party-platforms" />

## Ограничения постбэков на сторонних платформах

Когда речь идет об отправке постбэков в сторонние платформы, существуют различные уровни ограничений для медиаисточников. Постбэки могут либо вообще не отправляться, либо отправляться без атрибуции, либо отправляться без каких-либо ограничений.

<div id="types-of-postback-restrictions" />

#### Типы ограничений для постбэков

<div id="no-postbacks-sent" />

<Accordion title="Постбэки не отправляются">

Постбэки для событий с сырыми данными, ограниченные медиаисточниками, как указано в <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">этой таблице</Anchor>, не отправляются на сторонние платформы. Это означает, что сторонние платформы не получают постбэки о таких событиях, что приводит к меньшей атрибуции на их платформе по сравнению с AppsFlyer.

</Accordion>

<div id="postbacks-with-no-attribution" />

<Accordion title="Постбэки отправляются без атрибуции">

Для событий, кроме событий с ограниченными сырыми данными, перечисленные ниже рекламные сети требуют, чтобы рекламодатели скрывали источник медиа при передаче постбэков сторонним платформам. Для этого AppsFlyer **заменяет оригинальный медиаисточник на органическую атрибуцию**. Это означает, что постбэки по таким событиям, отправленные на сторонние платформы, не включают атрибуцию к медиаисточнику, что приводит к снижению атрибуции на их платформе по сравнению с AppsFlyer:

* Amazon
* Meta реклама
* pinterest
* Snapchat (<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">Условия использования</Anchor>)
* Twitter
* Bing
* Yahoo (Oath: Рекламные платформы / Yahoo Gemini)

> 📘 **Note**
>
> **Примечание**
>
> Для рекламы Meta поведение постбэков зависит от того, принял ли рекламодатель условия Расширенного мобильного измерения (AMM):
>
> * **AMM не принято:** Постбэки отправляются только для установок <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#install-referrer-android-only">атрибутированных по ссылке установки</Anchor>. Постбэки не включают данные атрибуции.
> * **AMM принято:** Постбэки отправляются для установок, атрибутированных <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#методы-атрибуции">всеми методами атрибуции</Anchor>. Тем не менее, данные постбэков не включают данные атрибуции, что означает, что все постбэки отправляются на сторонние платформы как неатрибутированные (органические) данные.

</Accordion>

<div id="regular-postbacks" />

<Accordion title="Обычные постбэки">

Все остальные события, которые не ограничены или медиаисточник не скрыт, отправляются как обычные постбэки. Это касается и агрегированных событий.

</Accordion>

<table><colgroup><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th colspan="6">Ограничения на постбэки распространяются на все сторонние платформы, интегрированные с AppsFlyer, включая следующие:</th></tr></thead><tbody><tr><td><span id="airship"></span>Airship</td><td>Amplitude</td><td>Batch</td><td>Braze</td><td>CleverTap</td><td>Облачная</td></tr><tr><td><span id="convertro"></span>Convertro</td><td>deltaDNA</td><td>Eulerian</td><td>GameAnalytics</td><td>IBM UBX</td><td>Insider</td></tr><tr><td><span id="itunes"></span>iTunes</td><td>Kahuna</td><td>Leanplum</td><td>Liquid</td><td>Localytics</td><td>Luna labs</td></tr><tr><td><span id="Medialyzer"></span>Medialyzer</td><td>Mixpanel</td><td>MoEngage</td><td>mParticle</td><td>OneSignal</td><td>Rocketbox</td></tr><tr><td><span id="salesforce"></span>salesforce.png</td><td>Маркетинг</td><td>MobilePush</td><td>Подписка IAP</td><td>Spoteffects</td><td>Swrve</td></tr><tr><td><span id="tapcart"></span>Tapcart</td><td>Tealium</td><td>WebEngage</td><td>Winclap Analytics</td><td>Google Analytics</td><td> </td></tr></tbody></table>

<div id="examples-of-discrepancies" />

## Примеры расхождений

<div id="example-1" />

<Accordion title="Ограничения сырых данных в Mixpanel">

<Tabs>
<Tab title="AMM не принято">

> 📘 **Note**
>
> **Пример 1**
>
> Рекламодатель использует Meta ads для размещения объявления. Они также сотрудничают с Mixpanel, чтобы лучше понять, как пользователи ведут себя и взаимодействуют с их сайтом. Рекламодатель проверяет количество установок, атрибутированных Meta ads за последний месяц:
>
>
>
> | В AppsFlyer | В Mixpanel |
> | --- | --- |
> | Рекламодатель видит 100 установок, атрибутированных Meta ads.<br /><br />30 установок были атрибутированы с помощью параметра`gp_referrer`. Эти события не ограничены и отображаются в отчетах по сырым данным. | Рекламодатель видит только 30 установок, атрибутированных Meta ads.<br /><br />Mixpanel не получает постбэки для 70 ограниченных событий. Постбэки для 30 установок, атрибутированных с использованием параметра `gp_referrer`, отправляются как органические. |

</Tab>

<Tab title="AMM принято">

> 📘 **Note**
>
> **Пример 1**
>
> Рекламодатель использует Meta ads для размещения объявления и принял условия AMM. Они также сотрудничают с Mixpanel, чтобы лучше понять, как пользователи ведут себя и взаимодействуют с их сайтом. Рекламодатель проверяет количество установок, атрибутированных Meta ads за последний месяц:
>
>
>
> | В AppsFlyer | В Mixpanel |
> | --- | --- |
> | Рекламодатель видит 100 установок, атрибутированных Meta ads.<br /><br />Отчет о сырых данных установок будет включать все 100 установок, а не только установки, атрибутированные через метод gp\_referrer. | Рекламодатель видит 100 установок, атрибутированных как органические.<br /><br />Поскольку AMM принято, Mixpanel получает постбэки для всех 100 установок. Тем не менее, ни один из постбэков не включает данные атрибуции, поэтому все установки отображаются как органические. |

</Tab>
</Tabs>

</Accordion>

<div id="example-2" />

<Accordion title="Ограничение сырых данных в MoEngage">

> 📘 **Note**
>
> **Пример 2**
>
> Рекламодатель использует Pinterest для размещения рекламы. Они также сотрудничают с MoEngage, чтобы получить информацию о вовлеченности клиентов. Рекламодатель проверяет, сколько событий «Добавить в список пожеланий» было атрибутировано к Pinterest за последний месяц:
>
>
>
> | В AppsFlyer | В MoEngage |
> | --- | --- |
> | Рекламодатель видит 97 событий «Добавить в список пожеланий», атрибутированных к Pinterest. | Рекламодатель не видит каких-либо событий «Добавить в список пожеланий», атрибутированных к Pinterest. MoEngage не получали от Pinterest постбэки по событиям, атрибутированным по кликам и просмотрам, поскольку они являются ограниченными событиями. |

</Accordion>

<div id="example-3" />

<Accordion title="Ограничения в Airship">

> 📘 **Note**
>
> **Пример 3**
>
> Рекламодатель использует Bing для размещения объявления. Они также работают с Airship над оптимизацией пути пользователей в своем мобильном приложении. Рекламодатель проверяет, сколько событий покупки было атрибутировано Bing за последний месяц:
>
>
>
> | В AppsFlyer | В Airship |
> | --- | --- |
> | Рекламодатель видит 35 событий покупки, атрибутированных Bing. | Рекламодатель видит 84 события покупки из органических источников. 35 из них пришли из Bing, но они об этом не узнают, поскольку эти покупки отображаются как органические. |

</Accordion>

> 📘 **Note**
>
> **См. также**
>
> Часто задаваемые вопросы об <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#часто-задаваемые-вопросы">ограничениях содержимого сырых данных</Anchor>.

<div data-zendesk-anchors="Overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HCVTKD7ZH991A8JF7XCNNE91=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 postback-restrictions=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BD%D0%B0-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%BD%D0%B8%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%85 h_01HDDR9JG5303R38QCAB2ZF6CW=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BD%D0%B0-%D1%81%D1%82%D0%BE%D1%80%D0%BE%D0%BD%D0%BD%D0%B8%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%85 types-of-postback-restrictions=%D1%82%D0%B8%D0%BF%D1%8B-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2 h_01HE05EXEFJF6SGYTKZ78FPP7Z=%D1%82%D0%B8%D0%BF%D1%8B-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2 h_01HDDRVF8J36N3J9AB3YRD8TZP=no-postbacks-sent h_01HDDRVF8JP2FWCA7PH58TZDBY=postbacks-with-no-attribution h_01HDDRVF8J9QRWN8MCKXRV0J3M=regular-postbacks examples=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B9 h_01HCW4HS35ZTAEWPXB9JKCR725=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B9 h_01HDDS499QJTX5RJY6CR98BDFB=example-1 h_01HDDS499QG48D1AFR3Z59J1HP=example-2 h_01KQZ0Q440XSG96Q3W65RYVYAG=example-3" />

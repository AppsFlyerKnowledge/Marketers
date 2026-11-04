---
title: Об ATT и SKAN
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2026-08-19T00:09:45Z'
  id: 360011890298
  locale: ru
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ru/articles/360011890298
---
> **Краткий обзор.** Начиная с iOS 14.5, Apple требует, чтобы вы внедрили и соблюдали условия <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">AppTrackingTransparency</Anchor> (ATT). ATT означает, что *если ваше приложение собирает данные о конечных пользователях и передает их другим компаниям для отслеживания в приложениях и на веб-сайтах,* вы должны использовать запрос согласия ATT и получить согласие пользователя на предоставление данных как в приложении издателя, так и в приложении рекламодателя. Если вы не отслеживаете путь пользователя, нет необходимости отображать запрос.

![iOS14-consent-pre-ATT-enforcement-6522_Cover-image_917x480.jpg](https://files.readme.io/622b57cf6b6b7ad9472b3d072f44d9b451e82fec6b0c918427e39e9e6700602e-360019478118.jpg)

<div id="attribution-measurement-in-an-att-environment" />

## Измерение атрибуции в среде ATT

AppsFlyer предоставляет несколько методов атрибуции, обеспечивая полный спектр решений для атрибуции. Требование о согласии [ATT](/docs/about-att-and-skan#att-principles) влияет на атрибуцию в контексте платных кампаний из приложения в приложение. Таким образом, рекламодателям необходимо использовать сочетание решений для атрибуции и отчетности. 

В случае платных кампаний из приложения в приложение [SKAN](/docs/about-att-and-skan#skan-solution-principles) предоставляет детерминированные результаты атрибуции. Другие типы кампаний, такие как собственные каналы, из веба в приложение и Apple Search Ads, используют традиционные инструменты атрибуции AppsFlyer. Традиционные инструменты обеспечивают долгосрочное измерение LTV, в то время как SKAN измеряет результативность пользователей во время короткого периода после установки.

Таким образом, чтобы получить полную картину, используйте традиционные решения AppsFlyer и SKAN, потому что они дополняют друг друга.

В этой статье рекламодатели познакомятся с SKAN и ATT. Она предназначена для рекламодателей, знакомых с платформой AppsFlyer.

<div id="skan-solution-principles" />

<Accordion title="Принципы решения SKAN">

AppsFlyer предоставляет агрегированные результаты атрибуции iOS, используя постбэки SKAN от iOS. Эти постбэки iOS отправляет рекламным сетям, которые затем пересылают их в AppsFlyer. Постбэки содержат анонимизированные записи атрибуции, обогащенные значением конверсии (CV), установленным рекламодателем. CV — это показатель качества пользователя во время изначального окна после установки приложения.

<Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">Решение SKAN</Anchor> от AppsFlyer предоставляет рекламодателям:

* Данные SKAN на дэшбордах и в отчетах, полученные путем агрегирования постбэков из всех рекламных сетей, обогащенные другими данными, такими как затраты.
* Возможность контролировать с помощью AppsFlyer Conversion Studio, что измеряет CV, без необходимости вносить изменения в код приложения. CV можно использовать для измерения доходов, интеракций или конверсии.

**Ограничения SKAN**

* **Кампании:** Не поддерживает Apple Search Ads, перекрестные рекламные кампании и мобильные установки, на которые повлияло посещение веб-сайта.
* **Период измерения:** Эффективный период измерения ограничен несколькими днями.

**Поток SKAN**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. Рекламодатель задает параметры измерения SKAN в AppsFlyer Conversion Studio.
2. Пользователь открывает приложение в первый раз.
3. Во время каждого окна AppsFlyer устанавливает CV на основе действий пользователя и заданной схемы CV.
4. После закрытия окна iOS отправляет постбэк в рекламную сеть и копию постбэка в AppsFlyer. Постбэк поступает с некоторой задержкой:
   * SKAN 4 окно измерения 1: 24-48 часов
   * SKAN 4 окно измерения 2-3: 24-144 часов
   * Для SKAN 3: 24-48 часов после последнего повышения значения CV.
5. Копии постбэков, отправленные с устройства iOS напрямую в AppsFlyer, пересылаются на конечную точку, определенную рекламодателем. См. статью <Anchor target="_blank" href="/marketers/ru/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Отправка копий постбэков SKAN в AppsFlyer.</Anchor>
6. Рекламная сеть пересылает постбэк с дополнительными данными в AppsFlyer, или SRN передает данные постбэка через API.
7. AppsFlyer проверяет и расшифровывает CV. Декодированные данные записываются и атрибутируются до того, как они станут доступны в AppsFlyer на дэшбордах, в отчетах и через API.

</Accordion>

<div id="att-principles" />

<Accordion title="Принципы ATT">

Запрос ATT предоставляет рекламодателям способ получения явного согласия пользователя на сбор данных, что позволяет рекламодателям собирать и передавать данные. Начиная с iOS 14.5, IDFA доступен только при условии согласия пользователя через запрос.

Запрос отображается как в приложении издателя, так и в приложении рекламодателя. Если пользователь дает согласие в обоих приложениях, это означает, что пользователь соглашается на *отслеживание,* и Apple разрешает рекламодателям отслеживать пользователя между приложениями, принадлежащими разным компаниям.

**Настройка ATT**

ATT имеет одно из значений, перечисленных в следующей таблице. Изначально iOS устанавливает для ATT значение «Не определено» или «Ограничено».

Учтите, что использование запроса согласия для преобразования статуса пользователя из *не определено* в *авторизовано* является необязательным. Но если вы не отобразите запрос, вы не сможете получить *авторизацию.*

| Значение ATT | Согласие  <br />(IDFA доступен) | Примечания |
| --- | --- | --- |
| Ограничено | Нет | <ul><li>Определяется компанией Apple на основе возраста пользователя и других критериев. Не может быть изменен пользователем устройства.</li><li>Запрос не может быть показан этим пользователям.</li></ul> |
| Не определено (до iOS 14.4) | Да | Значение по умолчанию |
| Не определено<br /><br />(начиная с iOS 14.5) | Нет | Значение по умолчанию |
| Отклонено | Нет | Возникает, если выполняется одно из следующих условий:<ul><li>Задано после показа запроса</li><li>Пользователь отключил параметр *Разрешить приложениям запрашивать отслеживание* (главный переключатель на уровне устройства).</li><li>До установки iOS 14 на устройство был включен LAT</li></ul> |
| Авторизовано | Да | Задано после показа запроса |

**Влияние ATT**

Из-за ATT многие пользователи не дают согласия на сбор данных, IDFA будет недоступен, а отслеживание запрещено. В результате рекламодатели, которые до iOS 14.5 полагались на отчеты по атрибуции на уровне пользователя, должны переключить часть анализа на агрегированные методы атрибуции и отчетности. <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model">Модели атрибуции AppsFlyer</Anchor>.

Данные, связанные с атрибуцией приложения, поступают из нескольких источников. Идентификаторы, доступные и используемые каждым из них, различаются. Большинство данных отображаются с использованием традиционных инструментов атрибуции. Однако для установок, атрибутированных с помощью SKAN, отчеты поступают через дэшборд SKAN.

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="На каком дэшборде показана установка?">

В iOS 14 установка может быть атрибутирована как к традиционным дэшбордам, так и к дэшбордам SKAN. Кроме того, в зависимости от контекста медиа-источника, она может быть атрибутирована к органическим установкам на одном дэшборде и к неорганическим на другом.

</Accordion>

<div id="ios-attribution-and-privacy-important-knowledge" />

## iOS атрибуция и конфиденциальность: что важно знать

<div id="ios-attribution-skan-and-privacy-articles-and-links" />

#### Статьи и ссылки по iOS 14 и SKAN

| Область | Статья | Особый интерес: Вопросы и ответы, расхождения, сравнения |
| --- | --- | --- |
| SKAN | <Anchor target="_blank" href="/marketers/ru/docs/skan-raw-data-reports">Поля сырых данных SKAN</Anchor> | Дополнительные поля SKAN для сырых данных, поддерживающие did\_win и SKAN 3.0 |
| SKAN | <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">Решение SKAN</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Время от установки приложения до обновления дэшборда</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#organic-metrics-in-the-context-of-skadnetwork">Органические метрики в контексте SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#appsflyer-attribution-vs-skan-attribution">Атрибуция AppsFlyer в сравнении с атрибуцией SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#faq-skan-discrepancies">Вопросы и ответы — расхождения SKAN</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/ru/docs/skan-interoperation">Функциональная совместимость партнеров SKAN</Anchor> (раздел статьи) | <Anchor target="_blank" href="/marketers/ru/docs/skan-integrated-partners-list">Список интегрированных партнеров SKAN</Anchor> |
| SKAN | <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-interoperation-with-meta-ads">Интеграция Meta ads и AppsFlyer SKAN</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq">Устранение неполадок и несоответствий</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook">Различия в измерениях и временных характеристиках</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/ru/docs/skan-interoperation-with-snapchat">Взаимодействие Snapchat и AppsFlyer SKAN</Anchor> | <Anchor target="_blank" href="/marketers/ru/docs/skan-interoperation-with-snapchat#discrepancies-guide">Руководство по несоответствиям</Anchor> |
| Конфиденциальность | <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">Агрегированная расширенная конфиденциальность (AAP)</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework#функции-на-которые-влияет-aap">Функции, на которые влияет AAP</Anchor></li></ul> |
| Конфиденциальность | <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions">Ограниченные медиа-источники</Anchor> | <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">Ограниченные поля сырых данных</Anchor> |
| ios 14 | <Anchor target="_blank" href="/marketers/ru/docs/preparing-for-the-app-store-review-nutrition-labels">Этикетки с описанием — подготовьтесь к проверке в App Store</Anchor> |  |
| ios 14 | <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Настройка ATT в приложении</Anchor> (руководство по SDK для разработчиков) |  |
| ios 14 | <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns">О сетях с самостоятельной атрибуцией (SRN), таких как Google, Meta ads и т. д.</Anchor> | <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns#ios-145-srn-attribution">Где регистрируются установки SRN?</Anchor> |
| Биллинг | <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/billing/">Биллинг для приложений iOS</Anchor> |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="Влияние доступности IDFA на атрибуцию и измерение">

<div id="metrics" />

#### **Метрики**

Обратите внимание, что, если IDFA недоступен, это может повлиять на следующие метрики:

| Метрики | Увеличение | Снижение | Примечания |
| --- | --- | --- | --- |
| Неорганические и органические установки | Органические | Неорганические |  |
| Повторные установки и установки | Установки | Повторные установки |  |
| Обязательный | Органические установки и внутренние события приложения | Повторные вовлечения и реатрибуции |  |
| Apple Search Ads | -- | -- | Без изменений. Как согласные, так и несогласные пользователи атрибутируются правильно. |

<div id="deep-linking" />

#### **Диплинкинг**

Отложенный диплинкинг с использованием <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-legacy-apis#deferred-deep-linking">устаревшего метода onConversionDataSuccess</Anchor> может не работать для iOS 14.5+, так как для него требуются данные атрибуции, которые могут быть недоступны из-за защиты конфиденциальности.

Мы рекомендуем использовать <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">унифицированный диплинкинг (UDL).</Anchor> UDL соответствует стандартам конфиденциальности iOS 14.5+ и возвращает только параметры, относящиеся к диплинкингу и отложенному диплинкингу: `deep_link_value` и `deep_link_sub1`. Параметры атрибуции, такие как `media_source`, `campaign` и `af_sub1-5`, возвращают null и не могут использоваться для диплинкинга.

</Accordion>

<div id="faqios-attribution-and-att" />

## Вопросы и ответы — iOS 14+

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="Что произойдет с приложением, использующим версию SDK до V6+?">

Если вы используете SDK версии V6.0 или ранее,

* SKAdNetwork и Apple Search Ads работать не будут.
* Если вы отправите приложение в App Store, ожидайте, что оно будет отклонено.

Для приложений, использующих SDK до версии 6.10: SKAN 4 не будет работать.

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="Обязательно ли отображать запрос ATT?">

Нет. Вам нужно запросить согласие ATT только в том случае, если вы хотите *отслеживать* пользователя, собирать IDFA или и то, и другое.

</Accordion>

<div id="faqskan" />

## Вопросы и ответы — SKAN

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="Как узнать, когда я получу постбэки и будут ли они SKAN 3 или SKAN 4?">

Тип постбэка SKAN, который вы получаете, зависит от множества факторов, в том числе от того, какой режим вы используете в Conversion Studio, какую рекламную сеть вы используете и какая версия iOS у ваших пользователей.

Эти факторы влияют на:

* Версия постбэка: Либо SKAN 3, либо SKAN 4. <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#principles-and-flow">Узнать больше</Anchor>
* Окно 1 (AW): Для SKAN 4 это 48 часов. Для SKAN 3 это основано на окне активности. Примечание. Если SKAN 4 используется не в Conversion Studio, но в подписи рекламной сети, то окно рассчитывается на основе окна активности или 48 часов, в зависимости от того, что меньше.
* Задержка постбэка: Через несколько часов после установки, когда приходит постбэк SKAN. Это зависит от того, когда закрывается окно. <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update">Узнать больше</Anchor>
* Обновление таймера: Для SKAN 3 окно активности может быть продлено до 63 дней; постбэк приходит только после закрытия окна.

На следующей блок-схеме это объясняется более подробно.

![SKAN_4_matrix_-_Page_8__1_.png](https://files.readme.io/0dbd4cae34d9f9fed80dbe835485789dab75d46dbb38de055f454d01efb97350-13756140934545.png)

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="Есть ли в SKAN ограничение по определенному количеству идентификаторов источника / идентификаторов кампаний в каждой рекламной сети?">

Да. Ранее ограничение составляло 100 идентификаторов кампаний. Однако начиная со SKAN 4, идентификаторы кампаний называются иерархическими идентификаторами источника, и ограничение составляет 10000. Идентификатор источника представляет собой 4-значное целое число.

Рекламные сети сопоставляют идентификатор источника SKAN со своим идентификатором кампании.

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="Как используются сырые данные SKAN?">

* Используйте сырые данные для агрегирования параметров, которые недоступны через агрегированные API.
* Легко настраивайте существующие процессы импорта сырых данных для получения сырых данных SKAN.

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="Почему значения ценности конверсий, которые я получаю, не соответствуют моей конфигурации в AppsFlyer Conversion Studio?">

Обычно это происходит из-за того, что в вашем приложении есть другой SDK, который может задавать значение конверсии и конфликтует с вашим SDK AppsFlyer и значениями конверсий, которые вы настроили в AppsFlyer. Убедитесь, что в приложение не интегрирован другой SDK, который задает значения ценности конверсии.

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="Почему агрегированные данные на дэшборде SKAN не совпадают с числами сырых данных в отчетах SKAN Data Locker?">

Часто это несоответствие происходит из-за того, что отчеты Data Locker находятся не в том месте. Получение данных от Google может занять до 13 дней. А в отчетах по сырым данным данные записываются в день их получения, а не кумулятивно. Поэтому, чтобы получить корректные метрики по установкам, относящимся к определенной дате, нужно посмотреть все отчеты за 13 дней после этой даты.

Пример: В отчете от 12 июня отображаются 100 установок из Google, которые произошли 11 июня. В отчете от 24 июня говорится, что 11 июня произошло еще 100 установок. Чтобы получить точные данные — 200 установок, совершенных 11 июня, вам нужно просмотреть все отчеты за последние 13 дней (с 12 по 24 июня) и агрегировать данные на основе времени установки или временной метки рекламной сети.

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/getting-started-onboarding-for-marketers#шаг-3-настройка-атрибуции">Начало работы с AppsFlyer</Anchor>

<div data-zendesk-anchors="attribution-measurement-in-an-att-environment=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D1%81%D1%80%D0%B5%D0%B4%D0%B5-att h_01HE0C8YXSXSX003X0671Z97KZ=%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B2-%D1%81%D1%80%D0%B5%D0%B4%D0%B5-att h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=ios-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D1%87%D1%82%D0%BE-%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE-%D0%B7%D0%BD%D0%B0%D1%82%D1%8C h_01HE0C8YXS3BH109DF1Y1KNK5P=ios-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D1%87%D1%82%D0%BE-%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE-%D0%B7%D0%BD%D0%B0%D1%82%D1%8C ios-14-and-skan-articles-and-links=%D1%81%D1%82%D0%B0%D1%82%D1%8C%D0%B8-%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BF%D0%BE-ios-14-%D0%B8-skan h_01HE0C8YXSPZKBWXC51Z2636R0=%D1%81%D1%82%D0%B0%D1%82%D1%8C%D0%B8-%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-%D0%BF%D0%BE-ios-14-%D0%B8-skan h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement metrics=%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D0%BA%D0%B8 h_01HE0C8YXSJMYN81FKPCA8ATK7=%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D0%BA%D0%B8 deep-linking=%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3 h_01HE0C8YXS6ADG1SQCMVP0W69B=%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3 faq%E2%80%94ios-14=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B--ios-14 h_01HE0C8YXSV9VSK1NPG9RCTQW1=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B--ios-14 h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B--skan h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B--skan how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

---
title: Агрегированное измерение событий (AEM) для iOS от Meta Ads
metadata:
  keywords:
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
  created_at: '2023-10-09T16:40:55Z'
  edited_at: '2026-08-18T00:31:30Z'
  id: 19228737402129
  locale: ru
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ru/articles/19228737402129
---
> **Краткий обзор:** Подробнее об AEM-решении для оптимизации конверсий iOS и событий в приложении, а также для атрибуции повторных взаимодействий на iOS в Meta Ads.

## Обзор

AppsFlyer поддерживает решение <Anchor target="_blank" href="https://www.facebook.com/business/help/721422165168355">Meta Ads Aggregated Event Measurement (AEM)</Anchor>. Это решение позволяет измерять события в вебе и в приложениях для устройств на iOS 14+ с использованием следующих методов атрибуции:

* [AEM в приложениях с целью повторного вовлечения](#app-aem-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F)
* [AEM в приложениях с целью продвижения приложения](#app-aem-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%BE%D0%B4%D0%B2%D0%B8%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F)

В рамках своего AEM-решения Meta принимает конверсии и постбэки приложений от AppsFlyer при условии, что события соответствуют требованиям AEM. Проверить соответствие AEM можно следующим образом:

* [Проверить, соответствуют ли события в приложении требованиям AEM](#%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%BF%D1%80%D0%B0%D0%B2%D0%BE-%D0%BD%D0%B0-%D1%83%D1%87%D0%B0%D1%81%D1%82%D0%B8%D0%B5)

## AEM в приложениях с целью повторного вовлечения

При помощи AEM Meta Ads получает по диплинкам данные атрибуции после повторного вовлечения для пользователей iOS без идентификаторов устройств.

### Порядок атрибуции

Meta Ads добавляет данные атрибуции к диплинку вместе с идентификатором AEM `campaign_ids`. AppsFlyer получает идентификатор с данными, отображёнными в диплинке, затем:

* Передаёт агрегированные отчётные данные назад в Meta Ads.
* Выполняет атрибуцию на основе информации о диплинке, добавленной Meta Ads.
* Включает данные атрибуции из диплинка в отчёты по сырым и агрегированным данным

### Параметры данных атрибуции

В отчёты включаются следующие параметры данных атрибуции, переданные Meta Ads:

* `ad_id (идентификатор объявления)`
* `adgroup_id`
* `campaign_id (идентификатор кампании)`
* `campaign_group_id`
* `account_id`

> 📘 **Примечание**
>
> Чтобы использовать AEM для ремаркетинга, SDK AppsFlyer получает строку `campaign_ids` при открытии диплинка. По умолчанию SDK передает глубокие ссылки из всех доменов. Если вы настроили интеграцию под свои требования, убедитесь, что она настроена на передачу глубоких ссылок из всех доменов, включая домен Meta, а не только из домена AppsFlyer.

### Вопросы и ответы по атрибуции после повторного вовлечения по диплинку

<div id="what-must-the-advertiser-do-to-enable-this-attribution" />

<Accordion title="Что должен сделать рекламодатель, чтобы включить эту атрибуцию?">

Для получения этих параметров для атрибуции от рекламодателя **не требуются никакие действия**.

Однако для измерения атрибуции после повторного вовлечения по диплинку должен быть **включён** переключатель **«Атрибуция после повторного вовлечения»**.

Примечание. Согласно условиям использования Meta Ads относительно AEM, включение измерения атрибуции после повторного вовлечения с помощью Meta Ads означает, что все постбэки, отправленные в Meta Ads, содержат частичные IP-адреса.

</Accordion>

<div id="what-about-agencies-and-meta-campaign-management-partners" />

<Accordion title="Что насчёт агентств и партнёров по управлению кампаниями Meta?">

На данном этапе атрибуция для агентств и партнёров по управлению кампаниями Meta не поддерживается. Это значит, что весь трафик атрибутируется Meta Ads. Это временно и скоро изменится.

</Accordion>

<div id="are-there-any-restrictions-on-data-from-this-attribution" />

<Accordion title="Если какие-либо ограничения по данным такой атрибуции?">

Данные, полученные от атрибуций по диплинку, не подлежат ограничениям. Это значит, что все данные появляются как в отчётах по сырым данным, так и в агрегированных отчётах на уровне пользователя.

</Accordion>

## AEM в приложениях с целью продвижения приложения

### Использование AEM

Если приложение имеет право на использование AEM в Meta Ads, то в процессе создания набора объявлений параметр **Измерение на основе агрегированных данных о событиях** выбран по умолчанию. Это означает, что для кампании можно одновременно использовать и AEM, и SKAN. Если вместо этого выбрано **SKAdNetwork от Apple**, то для кампании будет применяться только SKAN. Это означает, что AppsFlyer имеет ограниченные возможности по измерению активности приложений в Meta Ads.

<Image alt="aem_meta_ads_platform.png" src="https://files.readme.io/9ce9735024294967545fee9e9fc44cc49834ffcb5b3496febd50f8466c1bd397-46192072798737.png" width="563px" />

> 📘 **Примечание**
>
> Если у вас есть проблемы с соответствием AEM, [проверьте, соответствуют ли ваши события в приложении требованиям AEM](#как-проверить-соответствуют-ли-события-в-приложении-требованиям-aem).

### Передача данных AEM

**Расширенный обмен данными** позволяет обмениваться всеми событиями конверсии с Meta Ads и атрибутировать все установки и последующие события в приложении независимо от статуса ATT-согласия.

* Когда этот параметр отключен, расширенный обмен данными ограничен событиями конверсии для пользователей, у которых доступен идентификатор рекламодателя. События от пользователей без идентификатора рекламодателя не передаются и не атрибутируются.
* При включении расширенного обмена данными осуществляется отправка событий конверсии всех пользователей, независимо от статуса ATT-запроса. AppsFlyer атрибутирует эти события. Общие данные могут включать дополнительную информацию, связанную с устройством, которая не включает в себя с идентификатор устройства. Подробнее см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-integration-setup#advanced_data_sharing">Расширенный обмен данными</Anchor>.

![aem](https://files.readme.io/77e44d893994581dbe1a058fb5bebbf9b5e8bf167abe6e9d35ea8aa809ceca4b-46192056604305.png)

> 📘 **Примечание**
>
> * Все события включают в себя установки, открытия приложения и внутренние события приложения.
> * Прежде чем включить **Расширенный обмен данными**, убедитесь, что такой обмен, включая любое использование ваших данных третьими лицами, соответствует любым политикам и/или условиям платформы, которым вы передаёте данные. Обмен данными может содержать IP-адреса, anon\_ids (если есть), vendor\_id и пользовательских агентов.
> * Meta требует, чтобы для событий в приложении, пересылаемых через сервер-сервер (S2S), в полезную нагрузку события включались как **IP-адрес**, так и **идентификатор поставщика (IDFV)**. Без этих идентификаторов событие не будет соответствовать требованиям, необходимым для присвоения AEM от Meta.
> * AEM от Meta для продвижения приложений может также включать недетерминированные атрибуции по просмотрам. Для поддержки недетерминированной атрибуции по просмотрам через Meta AEM, убедитесь, что включён переключатель **Активировать** **атрибуцию по просмотрам через вероятностное моделирование**. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">атрибуции по просмотрам через вероятностное моделирование</Anchor>.

## Как проверить, соответствуют ли события в приложении требованиям AEM

Вы можете перейти в Управление событиями Meta, чтобы проверить, соответствуют ли события приложения требованиям AEM. После того, как станет понятно, что событие приложения соответствует, результаты выбранных кампаний AEM можно будет увидеть в Ads Manager. Чтобы проверить, соответствуют ли события в приложении требованиям AEM, см. <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">документацию Meta</Anchor>.

## Как активировать AEM-резюме

Используйте таблицу ниже в качестве быстрого чек-листа для активации Meta Ads AEM в AppsFlyer.

| **Решение** | **Переключатель** | **Расположение переключателя** | **Последствия** |
| --- | --- | --- | --- |
| **Ремаркетинг AEM (повторное вовлечение)** | Атрибуция повторного вовлечения | Партнёрская интеграция (Meta Ads) | Активирует AEM для ремаркетинга (атрибуция повторного вовлечения). |
| **Продвижение приложения AEM (установки)** | Расширенный обмен данными | Партнёрская интеграция (Meta Ads) | Включает в себя AEM для продвижения приложений, включая отправку событий от пользователей, не давших согласие ан ATT-запрос, в Meta и приём недетерминированной атрибуции (когда это применимо). |
| **Продвижение приложения AEM (установки)** | Активировать атрибуцию по просмотрам с помощью вероятностного моделирования | Настройки приложения | Активирует атрибуцию по просмотрам для недетерминированных требований. |

## Устранение неполадок

<div id="troubleshooting-ineligible-events-in-meta-aem" />

<Accordion title="Устранение проблем с несоответствующими требованиями событиями в Meta AEM">

Если Meta Ads помечает события приложения как недопустимые, выдавая ошибки типа **«Отсутствует событие отказа»** или другие сообщения, связанные с AEM это обычно связано с отсутствующими или неправильно настроенными данными. Используйте приведённый ниже чек-лист со списком для диагностики и устранения общих проблем.

> 🚧 **Важно!**
>
> После того, как вы выполните приведённые ниже действия, немного подождите, чтобы изменения вступили в силу. После внесения изменений у Meta Ads может уйти до **2–3 дней** на отражение соответствия требованиям AEM.

<div id="step-1-advanced-data-sharing-is-enabled" />

<Accordion title="Шаг 1. Включение расширенного обмена данными">

1. Перейдите в раздел **Совместная работа** > **Активные интеграции** > **Meta Ads**.
2. Проверьте, чтобы **расширенный обмен данными** был включён.

</Accordion>

<div id="step-2-ip-masking-is-disabled" />

<Accordion title="Шаг 2. Отключение маскировки IP-адресов">

События с IP-адресами с маской не соответствуют требованиям AEM.

* Перейдите в **Настройки приложения**.
* Убедитесь, что **IP-маскировка** выключена.

</Accordion>

<div id="step-3-servertoserver-s2s-events-include-required-parameters" />

<Accordion title="Шаг 3. Включение необходимых параметров в межсерверные (S2S) события">

Каждое S2S-событие должно включать в себя:

* **IP-адреса**
* **IDFV** (идентификатор поставщика).

</Accordion>

<div id="step-4-review-att-consent-rate" />

<Accordion title="Шаг 4: Проверка коэффициента согласия на АТТ-запрос">

Meta принимает ограниченный объём событий с отсутствующими или нулевыми IDFA. Если ваше приложение превышает этот порог, вы можете увидеть такую ошибку: **Объём параметра «Активировано отслеживание рекламодателя» выходит за пределы диапазона.**

</Accordion>

<div id="step-5-postback-mapping-configuration" />

<Accordion title="Шаг 5: Конфигурация сопоставления постбэков">

Проверьте, чтобы постбэки событий сопоставлялись с **Отправить всё (включая органические)**.

</Accordion>

<div id="step-6-check-reengagement-settings-if-relevant" />

<Accordion title="Шаг 6: Проверка параметров повторного вовлечения (если необходимо)">

Для кампаний по повторному вовлечению:

* Включите **Атрибуцию повторного вовлечения** в **Настройках приложения** и на странице **Активной интеграции с Meta**.

</Accordion>

#### Всё ещё не работает?

Если какие-то конкретные события по-прежнему не соответствуют требованиям:

1. Перейдите в Управление событиями Meta и следуйте указаниям на экране.
2. Выберите нужное событие приложения.
3. Установите **трафик MMP** как предпочтительный способ подключения.

#### Нужна помощь?

Если проблема остаётся:

* отправьте заявку в службу поддержки;
* прикрепите снимок экрана из Meta Ads, где видно событие (события), не соответствующее требованиям.

</Accordion>

<div id="i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible" />

<Accordion title="Данные об AEM не поступают в мой дэшборд и отчёты, хотя мои кампании соответствуют AEM.">

Ответ от Meta: «Мы работаем над этим обновлением в сотрудничестве с вашим MMP и выпустим его в течение последующих нескольких месяцев. У некоторых рекламодателей может отсутствовать доступ до полного завершения этого процесса».

</Accordion>

<div id="why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />

<Accordion title="Почему я не вижу установки, атрибутированные AEM, в отчётах о сырых данных даже после подписания соглашения AMM?">

При включении AAP, установки, атрибутируемые через AEM от Meta, исключаются из отчётов о сырых данных. Это действует даже в случае подписания соглашения АММ.

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HCAM4CEVRCG13CA32B0GM9QS=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 app-aem-for-reengagement=aem-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F%D1%85-%D1%81-%D1%86%D0%B5%D0%BB%D1%8C%D1%8E-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F 01H88ZM20H99W37M0H6XXQVMQA=aem-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F%D1%85-%D1%81-%D1%86%D0%B5%D0%BB%D1%8C%D1%8E-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F attribution-flow=%D0%BF%D0%BE%D1%80%D1%8F%D0%B4%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H7YJVNMV7QSZJWKZZA9042K6=%D0%BF%D0%BE%D1%80%D1%8F%D0%B4%D0%BE%D0%BA-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 attribution-data-parameters=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H7YJVNMVPPCD08Z2R0V5GCMY=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_attribution_deeplink_note=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 faqs-on-deep-link-reengagement-attribution=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D1%81%D0%BB%D0%B5-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D1%83 01H7YJVNMV4ZKMWKD06RC6GKFW=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D1%81%D0%BB%D0%B5-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D1%83 01H7YJVNMVSGMNJ3K84MCENXYG=what-must-the-advertiser-do-to-enable-this-attribution 01H7YJVNMVP7ZRCKXDRRH7GZBY=what-about-agencies-and-meta-campaign-management-partners are-there-any-restrictions-on-data-from-this%20attribution=are-there-any-restrictions-on-data-from-this-attribution 01H7YJVNMVQF0B0DV2NQYQVYHK=are-there-any-restrictions-on-data-from-this-attribution app-aem-for-app-promotion=aem-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F%D1%85-%D1%81-%D1%86%D0%B5%D0%BB%D1%8C%D1%8E-%D0%BF%D1%80%D0%BE%D0%B4%D0%B2%D0%B8%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F 01H88ZM20HQFMG962AZGYA98FR=aem-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F%D1%85-%D1%81-%D1%86%D0%B5%D0%BB%D1%8C%D1%8E-%D0%BF%D1%80%D0%BE%D0%B4%D0%B2%D0%B8%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F aem-eligibility=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-aem 01H7YJVNMVPB054VFS60KH9N7W=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-aem h_01HR886Q0KPM99FCQXD6RDPSBK=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 aem-data-sharing=%D0%BF%D0%B5%D1%80%D0%B5%D0%B4%D0%B0%D1%87%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-aem 01H88ZM20HK2HY32M4BKZ4N0B9=%D0%BF%D0%B5%D1%80%D0%B5%D0%B4%D0%B0%D1%87%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-aem 01H7YK9CHHNARCD7M2VZRMEW6S=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 check-eligibility=%D0%BA%D0%B0%D0%BA-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%B8%D1%82%D1%8C-%D1%81%D0%BE%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%81%D1%82%D0%B2%D1%83%D1%8E%D1%82-%D0%BB%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8-%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F%D0%BC-aem 01JBHQSHF8NA4SGVJ3WYPRN9B3=%D0%BA%D0%B0%D0%BA-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%B8%D1%82%D1%8C-%D1%81%D0%BE%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%81%D1%82%D0%B2%D1%83%D1%8E%D1%82-%D0%BB%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8-%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F%D0%BC-aem enable-aem-toggles-summary=%D0%BA%D0%B0%D0%BA-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-aem-%D1%80%D0%B5%D0%B7%D1%8E%D0%BC%D0%B5 h_01KJ28ETP9GK6TBTJK8SBZ5PFW=%D0%BA%D0%B0%D0%BA-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-aem-%D1%80%D0%B5%D0%B7%D1%8E%D0%BC%D0%B5 faqs-and-troubleshooting=%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA 01H7YK9CHHZN78CBHFTQ7E9RKQ=%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA h_01K720W9MYXFTYG18368SKHGGC=troubleshooting-ineligible-events-in-meta-aem h_01K720W9MYDKK5Q2J1M8VT9JFP=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01K722GQSB92J5KFFYQNP5WR29=step-1-advanced-data-sharing-is-enabled h_01K722GQSBV3GY2ZNN29ENG7Q2=step-2-ip-masking-is-disabled h_01K722GQSBVTSC09EPPCZQ6WN3=step-3-servertoserver-s2s-events-include-required-parameters h_01K722GQSBSX06A56ZX8RJ6YKT=step-4-review-att-consent-rate h_01K722GQSB26TN65JVJD6R7BAV=step-5-postback-mapping-configuration h_01K722GQSBTD4J9TZHBRGYS1XV=step-6-check-reengagement-settings-if-relevant still-not-working=%D0%B2%D1%81%D1%91-%D0%B5%D1%89%D1%91-%D0%BD%D0%B5-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 h_01K722GQSB8CXSSCVZPA3R3CJX=%D0%B2%D1%81%D1%91-%D0%B5%D1%89%D1%91-%D0%BD%D0%B5-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 need-help=%D0%BD%D1%83%D0%B6%D0%BD%D0%B0-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C h_01K722GQSBBB8KS8JNRBJZ4WWT=%D0%BD%D1%83%D0%B6%D0%BD%D0%B0-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C 01JCX7SKJ76KGW9SN7RCFA18E6=i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible why-can%27t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01K4ADBT26D2KD5MH568542XSV=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />

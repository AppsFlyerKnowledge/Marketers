---
title: Приложения для детей — вопросы и ответы
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2023-09-05T19:02:32Z'
  edited_at: '2026-08-18T00:18:11Z'
  id: 18324823209745
  locale: ru
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ru/articles/18324823209745
---
**Краткий обзор.** Ответы на часто задаваемые вопросы о приложениях, предназначенных для детей.

<div id="overview" />

## Обзор

Существует множество политик, законов и правил, касающихся приложений для детей и направленных на защиту их конфиденциальности. Главные из них — это Закон о защите конфиденциальности детей в Интернете [(COPPA)](https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa) и Общий регламент по защите данных [(GDPR)](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN#d1e2029-1-1). В последние годы такие платформы, как iOS и Android, внедрили политику, направленную на повышение уровня конфиденциальности для детей. При создании приложения на одном из первых этапов нужно указать, предназначено оно для детей или для смешанной аудитории (как для детей, так и для взрослых). Из <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">этого руководства</Anchor> вы узнаете, как реализовать соответствующее нормам решение по атрибуции для приложений, предназначенных для детей.

<div id="adding-a-child-directed-app" />

## Добавление приложения для детей

<div id="what-steps-do-i-need-to-take-when-adding-a-childdirected-app" />

<Accordion title="Какие шаги необходимо предпринять при добавлении приложения, предназначенного для детей?">

1. <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Следуйте указаниям мастера добавления приложений</Anchor>.
2. В шаге 2 мастера <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer#определите-аудиторию-приложения">см. инструкции о приложениях для детей</Anchor>.
3. После добавления приложения:
   * Используйте  <Anchor target="_blank" href="/marketers/ru/docs/basic-sdk-integration-guide#внедрение-ключа-разработчика-в-ваше-приложение">ключ разработчика</Anchor> в SDK
   * Добавьте соответствующие <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">элементы управления конфиденциальностью</Anchor>

 Подробнее о [внедрении инструментов для контроля соблюдения правовых норм в рекламных сетях](#внедрение-инструментов-appsflyer-для-контроля-соблюдения-правовых-норм).

</Accordion>

<div id="when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children" />

<Accordion title="Что происходит дальше, если при добавлении приложения отметить его как предназначенное для детей?">

Через две недели после добавления приложения вы получите уведомление, в котором вам будет предложено подтвердить, что вы внедрили элементы управления конфиденциальностью для приложений, предназначенных для детей. После подтверждения вы получите сообщение с подтверждением. Вы всегда можете открыть сообщение с подтверждением из центра уведомлений или посмотреть детали подтверждения в <Anchor target="_blank" href="/marketers/ru/docs/audit-log">журнале аудита</Anchor>.

</Accordion>

<div id="if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later" />

<Accordion title="Можно ли изменить выбор приложения, предназначенного для детей?">

На этапе, когда вы выбираете, предназначено ли приложение для детей или нет, ваш выбор уже нельзя отменить. Это возможно только при добавлении приложения.

</Accordion>

<div id="how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps" />

<Accordion title="Можно ли посмотреть, отметил ли кто-либо из моей команды приложение как предназначенное для детей?">

Подтвердив, что приложение предназначено для детей, вы можете увидеть подтверждение двумя способами:

* **Центр уведомлений:** щелкните по значку![notificatin center icon.png](https://files.readme.io/5d0b4f1712ba0c05786025adf183e065a2144e1917542ebec0f302688dccb5eb-18473195561489.png) уведомления в строке меню и найдите уведомление о подтверждении.
* **Журнал аудита:**
  1. В строке меню откройте меню пользователя (раскрывающийся список под адресом электронной почты).
  2. Выберите **центр безопасности.**
  3. В разделе **Журнал аудита** нажмите **Смотреть журнал аудита.** Информацию о подтверждении можно просмотреть в сервисе **Мои приложения**.

</Accordion>

<div id="implementing-appsflyer-compliance-tools" />

## Внедрение инструментов AppsFlyer для контроля соблюдения правовых норм

<div id="how-do-i-know-which-tool-to-use" />

<Accordion title="Как узнать, какой инструмент использовать?">

Если ваше приложение предназначено для детей или смешанной аудитории (дети и взрослые), вы можете использовать любой из рекомендуемых инструментов из <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">этого руководства</Anchor>, которые соответствуют требованиям законодательства. См. больше ресурсов SDK в нижней части этой страницы. 

<div id="examples-of-compliance-tools-and-their-use" />

#### Примеры инструментов для контроля соблюдения правовых норм и их использования

<table><thead><tr><th>Инструмент</th><th>https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png</th><th>Android;</th><th>Доступность сырых данных</th></tr></thead><tbody><tr><td><span id="strict-sdk"></span><p><a href="./additional-sdk-integration-guide#strictmode-sdk" target="_blank">Строгий режим SDK</a>: </p><p>Блокирует передачу IDFA в AppsFlyer. Обычно это рекомендуемый вариант для приложений, предназначенных для детей.</p></td><td><span><span>✓</span></span></td><td>- </td><td>Доступно только для рекламодателей</td></tr><tr><td><span id="standard-sdk-using-the-setdisableadvertisingidentifiers-api"></span><p>Стандартный SDK с использованием <a href="./android-oaid-implementation-in-the-sdk#opting-out-of-oaid-collection" target="_blank"><kbd>setDisableAdvertisingIdentifiers</kbd> API</a>:</p><p>Блокирует передачу AAID (рекламный идентификатор Google Android) в AppsFlyer. Обычно это рекомендуемый вариант для приложений, предназначенных для детей.</p></td><td>- </td><td><span><span>✓</span></span></td><td>Доступно только для рекламодателей</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-specific-ad-networks"></span><p>Стандартный SDK с ограничением по возрасту посредством функции <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank"><kbd>setSharingFilterForPartners</kbd></a> для <strong>определенных</strong> рекламных сетей: </p><p>Предотвращает доступ таких рекламных сетей к данным, если возраст пользователей ниже установленного предела.\*</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Ограничено для определенных рекламных сетей</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks"></span><p>Стандартный SDK с ограничением по возрасту посредством функции <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank"><kbd>setSharingFilterForPartners</kbd></a> для <strong>всех</strong> рекламных сетей:</p><p>Предотвращает доступ всех рекламных сетей к данным, если возраст пользователей ниже установленного предела.\*</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Доступно только для рекламодателей</td></tr><tr><td><span id="skan-only"></span><p><a href="./skadnetwork-skan-solution-guide" target="_blank">Только SKAN</a>:</p><p>Блокирует передачу рекламного идентификатора в другие рекламные сети.</p></td><td><span><span>✓</span></span></td><td>- </td><td>Доступно только для рекламодателей</td></tr><tr><td><span id="sdkless-solutions-less-recommended"></span><p>Решения без SDK (рекомендуется реже):</p><p><span>Настройте собственные серверы для передачи данных в AppsFlyer в качестве альтернативы отправке данных через </span><span>SDK</span>.</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>В соответствии с вашей настройкой</td></tr><tr><td><span id="aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners"></span><p><a href="./apply-aggregated-advanced-privacy-framework" target="_blank">Фрейморк Агрегированной расширенной конфиденциальности</a>: </p><p>Обеспечивает соблюдение уровней конфиденциальности Apple ATT, гарантируя, что данные на уровне пользователя <span>недоступны </span><span>для рекламодателей и рекламных сетей</span>.</p></td><td><span><span>✓</span></span></td><td>- </td><td>Недоступно для рекламодателей и рекламных сетей</td></tr><tr><td colspan="4"><span id="-when-applying-an-age-gate-block-userlevel-data-that-doesnt-fall-under-the-age-gate-is-available-in-raw-data-reports"></span><p>\* При применении блокировки возрастных ограничений данные на уровне пользователя, которые не попадают под возрастные ограничения, доступны в отчетах по сырым данным.</p></td></tr></tbody></table>

</Accordion>

<div id="how-does-using-the-tools-in-the-guide-affect-attribution" />

<Accordion title="Как использование инструментов из руководства влияет на атрибуцию?">

<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">Руководство AppsFlyer по решениям для обеспечения соблюдения правовых норм</Anchor> предлагает различные инструменты, каждый из которых имеет [разные уровни контроля](#how-do-i-know-which-tool-to-use). Влияние на атрибуцию зависит от конкретного инструмента, который вы решили внедрить.

При использовании инструмента, ограничивающего передачу данных пользователя, таких как идентификатор устройства, применяются другие методы атрибуции, например <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#probabilistic-modeling">вероятностное моделирование</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model#install-referrer-android-only">инициатор установки (для Android)</Anchor>.

Инструменты, которые не передают данные на уровне пользователя, считаются сохраняющими конфиденциальность и позволяют получать агрегированные данные о кампаниях.

</Accordion>

<div id="i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do" />

<Accordion title="Я не знаю, соответствует ли рекламная сеть, с которой я работаю, требованиям законодательства, что мне делать?">

Часто бывает неясно, соблюдают ли рекламные сети, с которыми вы сотрудничаете, соответствующие правовые нормы. Вы можете обратиться с этим вопросом в рекламную сеть. Если они не соблюдают требования или вы в них не уверены, можете не передавать им свои данные. Вы можете использовать **<Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">функцию`setSharingFilterForPartners`</Anchor>**, чтобы указать рекламные сети, в которые запрещено передавать данные вашего приложения. Эту функцию также можно использовать для блокировки всех рекламных сетей. См. больше [примеров инструментов для контроля соблюдения правовых норм](#примеры-инструментов-для-контроля-соблюдения-правовых-норм-и-их-использования).

</Accordion>

<div id="do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant" />

<Accordion title="Нужно ли внедрять инструменты AppsFlyer для контроля соблюдения правовых норм, если рекламная сеть соответствует требованиям?">

Инструменты AppsFlyer для контроля соблюдения правовых норм должны быть внедрены всегда. Какие из них подойдут для ваших нужд, зависит от аудитории вашего приложения. Вы можете использовать  **<Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">функцию`setSharingFilterForPartners`</Anchor>**  ("MediaSourceName"), если рекламная сеть, с которой вы работаете, обязалась обрабатывать данные, которыми вы поделились с ней, исключительно в ограниченных целях, предусмотренных COPPA, GDPR, действующими законами и правилами или другими правилами платформы, которые этого требуют, и с соответствующего согласия.

Это относится к каждой из рекламных сетей, с которыми вы работаете.

</Accordion>

<div id="what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this" />

<Accordion title="Какие данные я передаю в рекламные сети? Как я могу их контролировать?">

Рекламные сети, не являющиеся <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns">SRN</Anchor>, получают ваши данные через постбэки. Они могут определять, какие события включать в постбэки . Постбэки по установкам передаются для атрибуции по умолчанию, а постбэки по внутренним событиям приложения передаются только в том случае, если вы <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">настроили передачу определенных событий</Anchor>. Если постбэки не заблокированы или не ограничены SDK, они могут содержать данные пользовательского уровня, связанные с вовлеченностью пользователей приложения (установки, внутренние события приложения и повторные вовлечения).

Помимо постбэков, рекламные сети и агентства имеют <Anchor target="_blank" href="/marketers/ru/docs/manage-data-access-permissions">ограниченный доступ к данным через платформу</Anchor>.

**Чтобы узнать, какие данные были переданы рекламным сетям через постбэки:**

* Скачайте <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview#postbacks">отчеты по постбэкам</Anchor> из меню **Отчеты** > **Экспорт сырых данных**

**Для контроля передаваемых данных:**

* Используйте любой из инструментов SDK для контроля соблюдения правовых норм, например <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners`</Anchor>, чтобы заблокировать или ограничить передачу определенных данных.
* Выберите, куда вы будете передавать <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#default-postbacks">постбэки по умолчанию</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">постбэки по внутренним событиям приложения</Anchor>: либо рекламной сети, к которой атрибутировано событие, либо всем медиа-источникам, включая органические.

**Для контроля доступности данных по атрибуции на уровне пользователя для пользователей iOS:**

* Используйте <Anchor target="_blank" href="/marketers/ru/docs/apply-aggregated-advanced-privacy-framework">фреймворк агрегированной расширенной конфиденциальности</Anchor> для обеспечения уровней конфиденциальности Apple ATT. Это гарантирует, что данные на уровне пользователя, хотя и используемые для атрибуции, не будут доступны в AppsFlyer рекламодателям или рекламным сетям. Агрегированные данные доступны без ограничений.

</Accordion>

<div id="do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked" />

<Accordion title="Нужен ли мне SDK, если мое приложение предназначено для детей и все рекламные сети заблокированы?">

SDK записывает события вашего приложения, такие как установки, повторные вовлечения и внутренние события приложения. Без SDK атрибуция невозможна. С помощью SDK можно <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#конфиденциальность-данных-пользователей">сохранить конфиденциальность пользователей</Anchor> и показывать только агрегированные данные.

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">Обзор интеграции SDK</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/apply-privacy-preserving-sdk-methods">SDK: Методы сохранения конфиденциальности</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#конфиденциальность-данных-пользователей">SDK: Настройки конфиденциальности пользователя</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/trust/privacy/">Меры по обеспечению конфиденциальности в AppsFlyer</Anchor>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HA20EGWDBSNAFZ7WNXJFFRRV=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 general-questions=%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%B4%D0%B5%D1%82%D0%B5%D0%B9 h_01H9ZK2THJVFYQ49HHRYKZZNEK=%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%B4%D0%B5%D1%82%D0%B5%D0%B9 h_01HHCE11YQX4DKV5BEW6QHKN55=what-steps-do-i-need-to-take-when-adding-a-childdirected-app when-adding-a-new-app-what-happens-after-i%E2%80%99ve-indicated-my-app-is-directed-towards-children=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children h_01H9ZK2THJ225P38Q9CHQSTNY4=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children if-ive-added-an-app-and-didn%E2%80%99t-define-it-as-directed-towards-children-can-i-change-this-later=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01HGZ5VAJHNW2K62ARTK43SG19=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01H9ZK2THJK5Q5EE3K38GTCCT7=how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps implementing-compliance-tools=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%BE%D0%B2-appsflyer-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D1%8F-%D1%81%D0%BE%D0%B1%D0%BB%D1%8E%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D0%B2%D1%8B%D1%85-%D0%BD%D0%BE%D1%80%D0%BC h_01HGZ5VAJHNJVM2ENFZ3DEAK42=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%BE%D0%B2-appsflyer-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D1%8F-%D1%81%D0%BE%D0%B1%D0%BB%D1%8E%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D0%B2%D1%8B%D1%85-%D0%BD%D0%BE%D1%80%D0%BC h_01HGZ4VWDBZJE8RWM05EJNH0S9=how-do-i-know-which-tool-to-use examples-of-compliance-tools-and-their-use=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%BE%D0%B2-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D1%8F-%D1%81%D0%BE%D0%B1%D0%BB%D1%8E%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D0%B2%D1%8B%D1%85-%D0%BD%D0%BE%D1%80%D0%BC-%D0%B8-%D0%B8%D1%85-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01HHEED2AQTW7G0MJJZDZV2B09=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%BE%D0%B2-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D1%8F-%D1%81%D0%BE%D0%B1%D0%BB%D1%8E%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B0%D0%B2%D0%BE%D0%B2%D1%8B%D1%85-%D0%BD%D0%BE%D1%80%D0%BC-%D0%B8-%D0%B8%D1%85-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function%C2%A0for-all-ad-networks=standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks aggregated-advanced-privacy-framework%C2%A0%0Aenforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners=aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners h_01HKHX0GBS9EWMXMY387FQ95X1=how-does-using-the-tools-in-the-guide-affect-attribution h_01HH9EAB8T4Z6RMT8MVS77Q6BP=i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do h_01HKHWSQQKEDZBCDH0P8H760K6=do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant h_01HHEEQ4AAEZSA0YB6V2DSRYXK=what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this h_01HKJ843208PMQF1MCYCWMJC3H=do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked h_01HE7TQV7VDSEX3E7RTKAHBMNN=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

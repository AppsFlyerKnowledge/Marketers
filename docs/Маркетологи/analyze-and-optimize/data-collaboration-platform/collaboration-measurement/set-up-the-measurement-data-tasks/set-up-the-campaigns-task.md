---
title: Настройте задачу «Кампании»
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-08-18T11:31:27Z'
  edited_at: '2026-08-27T00:05:36Z'
  id: 38190881693969
  locale: ru
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/ru/articles/38190881693969
---
> **Кратко:** Узнайте, как настроить источник кампании для on-site, off-site и комбинированных кампаний (on-site и off-site).

<Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#campaign-mapping">Источник кампании</Anchor> связывает on-site события конверсии с соответствующими off-site, on-site и комбинированными кампаниями, обеспечивая точную атрибуцию и отчетность по эффективности. В отличие от других задач в DCP (например, конверсий или вовлеченности), **задача кампаний одинакова как для on-site, так и для off-site кампаний**. Это означает, что вы используете один и тот же процесс настройки независимо от типа кампании.

## Требования

Прежде чем можно будет настроить задачу кампаний, владелец совместной работы должен назначить ее участнику совместной работы, который владеет платформой, где генерируются события конверсии. Подробнее см. в статье Назначение задач настройки

## Настройте задачу «Кампании»

Источник кампаний связывает внутренние события конверсии с идентификаторами на уровне кампании (например, идентификатором кампании) в контексте on-site, off-site или комбинированных кампаний. Информация о кампании, которую вы задаете в этой задаче, передается в DCP через пользовательский источник данных.

<div id="1-prepare-campaign-data" />

<Accordion title="1. Подготовьте данные кампании">

Прежде чем настраивать источник кампании в DCP, подготовьте пользовательский источник кампании и загрузите его в облачный сервис. Подробнее о схеме сопоставления и о том, как загрузить источник кампании в облачную среду, см. в статье <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#подготовка-источника-сопоставления-кампаний">Подготовка источника кампании</Anchor>.

Чтобы настроить источник кампании в DCP:

1. Перейдите на страницу **измерения сотрудничества**.
2. Нажмите **Кампании**.
3. В диалоговом окне **Кампании** нажмите **+ Новый источник кампании**.
4. В диалоговом окне **Новый источник кампании** введите название в поле **Название источника** в соответствии с <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#требования-и-рекомендации">требованиями и рекомендациями</Anchor>.
5. Создайте информативное название для эксперимента, затем нажмите **Далее**.

</Accordion>

<div id="2-open-campaigns-settings" />

<Accordion title="2. Откройте настройки кампаний">

На странице **Настройки измерения** вы настраиваете, как кампании собираются, атрибутируются и связываются с данными медиапартнеров в рамках настройки совместной работы.

Чтобы открыть страницу **Настройки измерения**, выполните следующие действия:

1. В AppsFlyer в боковом меню выберите **Collaborate** > **Data Clean Room**.
2. На странице **Платформа совместной работы с данными** выберите сотрудничество, которое вы хотите настроить.
3. В нижней части страницы совместной работы нажмите **Настроить измерение.**
   * Если ссылка неактивна, настройте <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources">источники данных</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-build-and-activate-audiences">аудитории</Anchor> для совместной работы.
4. На странице **Настройки измерения** нажмите панель **Кампании**, чтобы открыть диалоговое окно **Кампании**.

   > 📘 **Примечание:**
   >
   > * Если диалоговое окно **Campaigns** заблокировано, это означает, что задача **Campaigns** назначена вашему соисполнителю, и вы не можете просматривать ее содержимое. Если вы владелец совместной работы, вы можете снять блокировку, переназначив задачу себе. Однако все предыдущие настройки будут удалены, и задача будет сброшена.
   > * Если панель **Campaigns** неактивна, попросите владельца совместной работы назначить вам задачу Campaigns.


</Accordion>

<div id="3-set-campaign-data-provision-method" />

<Accordion title="3. Настройка метода предоставления данных кампании">

Данные кампании предоставляются в DCP в пользовательском файле источника, который хранится в вашем облаке.

Чтобы настроить метод предоставления данных о конверсиях в DCP, выполните следующие шаги:

1. В диалоговом окне **Campaigns** нажмите + **New campaign source**.
2. В диалоговом окне **New conversion source** на шаге **Source name** задайте имя источника кампании в поле **Source name** в соответствии с <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#требования-и-рекомендации">требованиями и рекомендациями</Anchor>.
3. Нажмите **Next**.

</Accordion>

<div id="4-set-source-location" />

<Accordion title="4. Задайте местоположение источника">

Укажите местоположение источника кампании в вашем облачном сервисе.

1. На шаге **Set source location step** выберите подключение, через которое осуществляется доступ к источнику.
   * Если подключения в аккаунте не определены, откроется диалоговое окно **New connection** с предложением создать подключение.
   * Если у вас уже есть подключения, но вы хотите использовать новое, откройте список **Select connection** и выберите **+ New connection**.
2. Укажите параметры доступа в соответствии с вашим облачным сервисом:
   * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#расположение-источника-в-bigquery">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#расположение-источника-в-snowflake">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#расположение-источника-в-облачных-корзинах">Amazon S3 и GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#расположение-источника-локальные-файлы">Локальная файловая система</Anchor>
3. Выберите, как следует обрабатывать новые данные. Подробнее см.: <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Set source sync method</Anchor>.
4. Создайте информативное название для эксперимента, затем нажмите **Далее**.

</Accordion>

<div id="5-map-campaign-fields" />

<Accordion title="5. Сопоставление полей кампании">

Если для передачи событий конверсии в DCP используется пользовательский источник, сопоставьте поля пользовательского источника конверсий на сайте с соответствующими полями DCP.

**Загрузка полей источника кампании**

Если поля источника кампании еще не загружены, возможно, вам придется загрузить их вручную, чтобы сопоставить их с полями DCP.

Чтобы загрузить поля источника конверсии, выполните следующие действия:

1. На шаге **Map source fields** нажмите **Load fields from source**.
2. Подробнее о том, как загружать поля вручную, см.: <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-загрузите-поляисточника">Загрузка полей источника</Anchor>.

**Автосопоставление полей кампании**

Когда поля источника кампании загружены, DCP автоматически сопоставляет их с соответствующими полями DCP. Автосопоставление может занять до 10 секунд. Отображается баннер с результатом сопоставления: в нем показано, сколько полей было сопоставлено, и перечислены все столбцы источника, для которых не удалось найти соответствия.

Чтобы повторно запустить автосопоставление, нажмите **Update mapping**.

**Сопоставьте поля кампании**

Если поля источника конверсии загружены, вы можете сопоставить их с полями DCP.

Чтобы сопоставить пользовательские поля источника кампаний, выполните следующие действия:

1. Сопоставьте поля в разделе **Source fields** с соответствующими полями в разделе **DCP fields**.
   * Список полей и их описания см. в статье The campaigns scheme.
2. Нажмите **Save** (Сохранить). Отображается сообщение **campaign\_mapping source created**.

</Accordion>

<div id="5-align-collaborator-name" />

<Accordion title="6. Согласовать имя партнера по совместной работе">

Последний шаг после завершения задачи Campaigns — согласовать имя партнера по совместной работе. Это необходимо, потому что у каждой учетной записи DCP есть только один источник кампании. Поскольку владелец учетной записи может поддерживать несколько совместных проектов с разными партнерами по совместной работе, DCP должен знать, какой партнер по совместной работе активен в текущем совместном проекте.

Чтобы согласовать имя партнера по совместной работе:

* В диалоговом окне **Campaigns**, в разделе **Align collaborator names**, выберите партнера по совместной работе для текущего совместного проекта.

</Accordion>

<div data-zendesk-anchors="prerequisites=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01K3BEVMGMPENVYY18EB0ANQCP=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F set-up-the-campaigns-task=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B7%D0%B0%D0%B4%D0%B0%D1%87%D1%83-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01K3BEVMGM6EEP6DY54HDDVKTR=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B7%D0%B0%D0%B4%D0%B0%D1%87%D1%83-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01K3BEVMGMC9C09FJTRVMS2J32=1-prepare-campaign-data h_01K3BEVMGMT28RXKBN31EBAFYJ=2-open-campaigns-settings h_01K3BEVMGMGV8GVGKZFDCSC0DF=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01K3BEVMGM2D9TA52F9F36Z31W=3-set-campaign-data-provision-method h_01K3BEVMGM67JV6VT6TBXTYACC=4-set-source-location h_01K3BEVMGNNFYFF939RHB8Z8E1=5-map-campaign-fields h_01K3BEVMGN4MAV9B0HP2TK5XCC=5-align-collaborator-name" />

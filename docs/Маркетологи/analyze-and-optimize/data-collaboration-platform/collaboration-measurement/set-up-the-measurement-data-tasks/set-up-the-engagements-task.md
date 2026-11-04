---
title: Настройте задачу вовлеченности
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
  created_at: '2025-08-18T10:19:20Z'
  edited_at: '2026-08-27T00:05:41Z'
  id: 38188042548113
  locale: ru
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/ru/articles/38188042548113
---
> **Кратко:** Узнайте, как настроить события вовлеченности для on-site и комбинированных кампаний (on-site и off-site кампаний).

<Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#engagements">События вовлеченности</Anchor> фиксируют взаимодействия пользователей, такие как просмотры рекламы или клики, которые происходят до конверсии. Они настраиваются только для on-site кампаний — отдельно или в сочетании с off-site кампаниями. (Для off-site кампаний данные о вовлеченности напрямую предоставляются внешними партнерами, такими как Meta или Google. В этой статье объясняется, как настраивать вовлеченность по типу кампании.

<div id="prerequisites" />

## Требования

Прежде чем можно будет настроить задачу Engagements, владелец совместной работы должен назначить ее участнику совместной работы, которому принадлежит платформа, где создаются события вовлеченности. Для получения дополнительной информации смотрите Назначение задач настройки

<div id="set-up-engagements-for-on-site-or-combined-campaigns" />

## Настройте вовлеченность для кампаний на сайте или комбинированных кампаний

В контексте on-site и комбинированных кампаний все события вовлеченности исходят из ресурсов, принадлежащих участнику совместной работы, — например, из его приложения, веб-сайта или систем в магазине. Эти события вовлеченности обычно собираются с помощью SDK AppsFlyer или передаются через пользовательские источники данных и относятся исключительно к on-site активности пользователей.

<div id="1-prepare-engagement-data" />

<Accordion title="1. Подготовка данных о вовлечении">

Перед настройкой пользовательского источника вовлеченности в DCP вы можете предоставить данные о вовлеченности одним из двух способов:

* **Пользовательский файл источника:** создайте файл с данными о взаимодействиях и загрузите его в свое облачное хранилище. Для получения дополнительной информации смотрите <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Подготовка пользовательских файлов источников для вовлеченности</Anchor>.
* **AppsFlyer SDK:** Интегрируйте AppsFlyer SDK в свое приложение, чтобы автоматически отправлять в DCP события вовлеченности в приложении. Дополнительные сведения см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Подготовка событий в приложении для вовлеченности</Anchor>.

</Accordion>

<div id="2-open-engagement-settings" />

<Accordion title="2. Откройте настройки вовлеченности">

На странице **Measurement settings** в рамках настройки измерения совместной работы вы определяете, как собираются данные о вовлеченности и как выполняется их атрибуция.

Чтобы открыть страницу **Настройки измерения**, выполните следующие действия:

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Data Clean Room**.
2. На странице **Платформа совместной работы с данными** выберите сотрудничество, которое вы хотите настроить.
3. В нижней части страницы совместной работы нажмите **Настроить измерение.**
   * Если ссылка неактивна, настройте <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources">источники данных</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-build-and-activate-audiences">аудитории</Anchor> для совместной работы.
4. На странице **Measurement Setting** нажмите панель **Engagements**, чтобы открыть диалоговое окно **Engagements**.

   <div id="note" />

   > 📘 **Примечание:**
   >
   > * Если диалоговое окно **Engagements** заблокировано, это означает, что задача Engagements назначена вашему участнику совместной работы и вы не можете просматривать ее содержимое. Если вы владелец совместной работы, вы можете разблокировать ее, переназначив задачу себе. Однако все предыдущие настройки будут удалены, а задача будет сброшена.
   > * Если панель **Engagements** неактивна, попросите владельца совместной работы назначить вам задачу Engagements.


</Accordion>

<div id="3-set-data-provision-method" />

<Accordion title="3. Настройка метода предоставления данных">

Данные о вовлеченности передаются в DCP через события в приложении, пользовательский источник или оба варианта:

* **События в приложении** — источником данных о событиях вовлечения является SDK AppsFlyer, интегрированный в ваше мобильное приложение. SDK отправляет события вовлечения в реальном времени из вашего приложения каждый раз, когда пользователь выполняет определенное действие.
* **Пользовательский источник** — источником событий вовлечения является файл пользовательского источника, хранящийся в вашем облаке.

Чтобы настроить метод предоставления данных о вовлеченности в DCP, выполните следующие действия:

1. В диалоговом окне **Engagements** выберите тип предоставления данных о вовлеченности: события в приложении, файл пользовательского источника или оба варианта.
2. В зависимости от метода предоставления данных введите следующие сведения:
   * **События в приложении:**
     1. Выберите приложение, которое отправляет внутренние события приложения, содержащие данные о вовлечённости.
     2. В списке **Select ad engagement event** выберите, какое из событий в приложении, отправляемых SDK AppsFlyer, является событием вовлечения.
     3. В списке **Select advertised item (SKU)** выберите параметр в событии в приложении, который содержит значение SKU.
   * **Пользовательский источник:**
     1. Нажмите **+ New engagement source**.
     2. В диалоговом окне **New engagement source** введите название источника вовлеченности в поле **Source name** в соответствии с <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#требования-и-рекомендации">требованиями и рекомендациями</Anchor>.
3. Создайте информативное название для эксперимента, затем нажмите **Далее**.

</Accordion>

<div id="4-set-source-location" />

<Accordion title="4. Задайте местоположение источника">

Если для передачи событий вовлечения в DCP используется пользовательский источник, настройте параметры, которые позволят DCP получить к нему доступ в вашем облачном сервисе.

1. На этапе **Set source location** выберите подключение, через которое осуществляется доступ к источнику.
   * Если подключения в аккаунте не определены, откроется диалоговое окно **New connection** с предложением создать подключение.
   * Если у вас уже есть подключения, но вы хотите использовать новое, откройте список **Select connection** и выберите **+ New connection.**
2. Укажите детали доступа к источнику в соответствии с требованиями своего облачного сервиса:
   * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#расположение-источника-в-bigquery">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#расположение-источника-в-snowflake">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#расположение-источника-в-облачных-корзинах">Amazon S3 и GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#расположение-источника-локальные-файлы">Локальная файловая система</Anchor>
3. Выберите, как следует обрабатывать новые данные. Подробнее см. раздел: <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Set source sync method</Anchor>.
4. Создайте информативное название для эксперимента, затем нажмите **Далее**.

</Accordion>

<div id="5-map-engagement-source-fields" />

<Accordion title="5. Сопоставление полей источника вовлечения">

Если для передачи событий вовлечения в DCP используется пользовательский источник, сопоставьте поля вашего пользовательского источника вовлечения с соответствующими полями DCP.

<div id="note-1" />

> 📘 **Примечание:**
>
> **База данных событий конверсии DCP** хранит все события конверсии в рамках текущей совместной работы по единой схеме, включая события конверсии из **событий в приложении** или **кампаний за пределами сайта** (если вы проводите комбинированную кампанию на сайте и за его пределами).

**Загрузка полей источника вовлечения**

Если поля источника вовлеченности ещё не загружены, возможно, вам потребуется загрузить их вручную, чтобы сопоставить их с полями DCP.

Чтобы загрузить поля источника вовлеченности, выполните следующие действия:

1. На шаге **Map source fields** нажмите **Load fields from source**.
2. Сведения о том, как загружать поля вручную, см. в статье: <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-загрузите-поляисточника">Load your source fields</Anchor>.

**Автосопоставление полей вовлечённости**

Когда поля источника вовлеченности загружены, DCP автоматически сопоставляет их с соответствующими полями DCP. Автосопоставление может занять до 10 секунд. На баннере отображается результат сопоставления: сколько полей сопоставлено и какие столбцы источника не удалось сопоставить.

Чтобы повторно запустить автосопоставление, нажмите **Update mapping**.

**Сопоставление полей вовлечённости**

Если поля источника вовлеченности загружены, вы можете сопоставить их с полями DCP.

Чтобы сопоставить пользовательские поля источника вовлеченности, выполните следующие действия

1. Если вы настраиваете комбинированную **On-site and Off-site campaign**, на шаге **Map source fields** разверните **Data for on-site attribution;** else, пропустите шаг ниже.
2. Сопоставьте все обязательные поля в разделе **Required**.
3. (Необязательно) Разверните **Optional enrichment data** чтобы сопоставить дополнительные поля.
4. Нажмите **Сохранить**. Отображается сообщение **`{source name}` source created** .[<Image alt="" src="https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png" width="40.62%" />](https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png)

</Accordion>

<div data-zendesk-anchors="prerequisites=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01K3EFVGA56P7FB605JY1BQ34M=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F set-up-engagements-for-onsite-or-combined-campaigns=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%BD%D0%B0-%D1%81%D0%B0%D0%B9%D1%82%D0%B5-%D0%B8%D0%BB%D0%B8-%D0%BA%D0%BE%D0%BC%D0%B1%D0%B8%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 h_01K3EFVGA6GT10BXJYE9SFM9TE=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9-%D0%BD%D0%B0-%D1%81%D0%B0%D0%B9%D1%82%D0%B5-%D0%B8%D0%BB%D0%B8-%D0%BA%D0%BE%D0%BC%D0%B1%D0%B8%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 h_01K3EFVGA6NM4YKZ8MEEYXX58B=1-prepare-engagement-data h_01K3EFVGA65CFME4H3ZC89X471=2-open-engagement-settings h_01K3EFVGA618KT7PGSVQXF6JSV=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01K3EFVGA6BKGAS5GZR3GW2N2M=3-set-data-provision-method h_01K3EFVGA64CQTKZ8C227042PY=4-set-source-location h_01K3EFVGA6J7PX1QE8TRA42QEY=5-map-engagement-source-fields h_01K3EFVGA6E3WH7FEYCW09P74V=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1" />

---
title: Data Clean Room — работа с подключениями
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2023-03-20T13:18:17Z'
  edited_at: '2026-10-19T14:03:08Z'
  id: 13886278812817
  locale: ru
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ru/articles/13886278812817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Кратко:** Подключите свои облачные сервисы к Data Clean Room, чтобы загружать данные и получать отчеты.

<div id="overview" />

## Информация о компании

После настройки облачных сервисов для использования с Data Clean Room (DCR) следующим шагом будет подключение их к DCR.

* Подключения, через которые DCR считывает first-party данные из ваших систем, называются **входящими подключениями.** Вы используете эти подключения при настройке пользовательских источников данных.
* Подключения, через которые DCR отправляет отчеты после обработки, называются **исходящими подключениями.** Вы используете эти подключения при настройке отчетов.

<div id="creating-inbound-connections" />

## Создание входящих подключений

Входящие подключения можно создать одним из следующих способов:

* До их использования для создания источников; ***или***
* В процессе создания источника.

В любом случае процесс одинаков, и созданные подключения можно использовать одинаковым образом. Разница только во времени и способе запуска процесса.

**Чтобы создать новое входящее подключение вне процесса создания источника:**

1. В верхней части главной страницы DCR в AppsFlyer нажмите кнопку **Manage connections**:

   <Image align="center" alt="dcr_manage_connections_button.png" src="https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png" />

   * Если в вашем аккаунте уже есть входящие подключения, откроется диалоговое окно **Manage connections**. В нем нажмите кнопку ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png), чтобы открыть диалоговое окно **New connection**.
   * Если вы создаете первое входящее подключение в аккаунте, диалоговое окно **New connection** откроется автоматически.
2. Далее следуйте инструкциям в разделе [Complete the connection](#завершение-настройки-подключения), приведенном ниже.

**Чтобы создать новое входящее подключение в процессе создания источника:**

1. Создайте подключение на этапе <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-sources#2-specify-the-source-location">указания местоположения источника</Anchor>.
   * Если подключения в аккаунте не определены, откроется диалоговое окно **Новое подключение** с предложением создать подключение.
   * Если у вас уже есть подключения, но вы хотите использовать новое, нажмите кнопку ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png) для открытия диалогового окна **New connection**.
2. Далее следуйте инструкциям в разделе [Complete the connection](#завершение-настройки-подключения), приведенном ниже.

<div id="complete-the-connection" />

#### Завершение настройки подключения

В диалоговом окне **«Новое подключение»** выберите облачный сервис, который вы подключаете к DCR, а затем следуйте инструкциям на соответствующей вкладке ниже.

<Image align="center" alt="dcr_create_inbound_connection.png" src="https://files.readme.io/b30606026761528f4a0d3efcc1a3207e8b9c99ca8202f76b2d698a86efaa21ee-13913809617297.png" width="457px" />

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

В диалоговом окне **«Новое подключение»** введите **ID проекта** BigQuery для проекта, содержащего ваш пользовательский источник данных.

* Эту информацию можно получить на странице BigQuery в консоли Google Cloud.

  <Image align="center" alt="BQ_project_ID.png" src="https://files.readme.io/de295dfc0224ff90f041b1aeaf2996828ec1920a715ba668b46a2f50489fd15b-13910856739857.png" width="457px" />

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

В диалоговом окне **«Новое подключение»** введите **ID учетной записи Snowflake** и **регион** для учетной записи, содержащей ваш пользовательский источник данных. Эту информацию можно получить, нажав на имя учетной записи в меню в левом нижнем углу консоли Snowflake:

* **ACCOUNTADMIN** > **Учетная запись** > наведите курсор на соответствующую учетную запись > **Скопировать идентификатор учетной записи.** <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">См. документацию Snowflake</Anchor>.

<Image align="center" alt="ui-snowsight-account-identifier.png" src="https://files.readme.io/9995c3fd523548de93bafc7c575203e7d38be3b6be2a5e876d7a0a8495ca04c9-24698313004433.png" />

</Accordion>

<div id="s3-gcs-inbound" />

<Accordion title="Amazon S3 и GCS">

В диалоговом окне **«Новое подключение»** введите имя <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-setting-up-cloud-services#облачные-корзины-amazons3-и-gcs">бакета, который вы создали</Anchor> для эксклюзивного использования DCR.

</Accordion>

<div id="creating-outbound-connections" />

## Создание исходящих подключений

DCR передает отчеты в выбранные вами облачные сервисы с помощью <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>. Поскольку отчеты доставляются через Data Locker, исходящие подключения DCR фактически являются подключениями Data Locker. Вы можете создать эти подключения одним из следующих способов:

* Перед использованием этих подключений для создания отчетов (начиная со страницы Data Locker в AppsFlyer); ***или***
* В рамках процесса создания отчета (начиная со страницы DCR в AppsFlyer).

В любом случае процесс практически одинаков, и созданные подключения можно использовать абсолютно одинаково.

<div id="note" />

> 📘 **Примечание:**
>
> Получение отчетов DCR не требует премиум-подписки на Data Locker. Если вы заинтересованы в получении других отчетов AppsFlyer через Data Locker, свяжитесь с вашим менеджером или отправьте письмо по адресу [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Чтобы создать новое исходящее подключение вне процесса создания отчета:**

1. В меню навигации слева в AppsFlyer выберите **Отчет > Data Locker.**  
   * Если в вашей учетной записи уже есть подключения Data Locker, вы перейдете на главную страницу Data Locker. Там нажмите кнопку ![dcr_dl_new_connection_button.png](https://files.readme.io/8261a480674822371c6e585f995a496a6b5682dd935351375db200bbb1272689-13919327056657.png) в правом верхнем углу, чтобы открыть диалоговое окно **«Новое подключение»**.
   * Если вы создаете первое подключение Data Locker для своей учетной записи, откроется страница **Начало работы** Data Locker. Нажмите кнопку ![dcr_dl_get_started_button.png](https://files.readme.io/3176ed5c35cba0939dd36de8c1136d15dc8ce27ee2891894ef65dba92fc7e91a-13919329616657.png), чтобы открыть диалоговое окно **«Новое подключение»**.
2. Затем следуйте инструкциям в разделе [Завершение подключения](#завершить-подключение) ниже.

**Чтобы создать новое исходящее подключение в рамках процесса создания отчета:**

1. Создайте подключение во время <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-creating-attribution-data-reports#set-the-report-destination-and-save-the-report">настройки места назначения отчета</Anchor>.
   * Если в вашем аккаунте не определены подключения:
     * В вашем браузере откроется новая вкладка (со страницей AppsFlyer Data Locker)
     * Откроется окно **Новое подключение**.
   * Если у вас уже есть подключения, но вы хотите использовать новое, нажмите на кнопку ![dcr_new_connection_data_locker_button.png](https://files.readme.io/9850a4b8ea4f40f6320903c545c51add7b90207538a27c83a3b02a41197ba567-14995870859281.png):
     * В вашем браузере откроется новая вкладка (со страницей AppsFlyer Data Locker)
     * Откроется окно **Новое подключение**.
2. Продолжите, следуя инструкциям в разделе [Завершить подключение](#завершить-подключение) ниже.
3. После создания подключения вернитесь на вкладку DCR в браузере и выберите только что созданное подключение из списка подключений Data Locker.

<div id="complete-the-connection-1" />

#### Завершить подключение

<div id="important" />

> 🚧 **Важно!**
>
> Параметр **AppsFlyer AWS Bucket** не следует использовать для отчетов DCR.

В диалоговом окне **New connection** выберите облачный сервис, к которому вы подключаетесь, а затем следуйте инструкциям на соответствующей вкладке ниже.

<Image align="center" alt="dcr_dl_new_connection_dialog.png" src="https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png" />

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

1. В диалоговом окне **New connection** введите имя подключения, затем выберите **BigQuery**.
2. Введите **идентификатор проекта** и **название набора данных** для проекта BigQuery, который содержит <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-setting-up-cloud-services#bigquery-outbound">созданный вами набор данных</Anchor> для Data Locker.  
   * Эту информацию можно найти на странице BigQuery в консоли Google Cloud.

     <Image align="center" alt="BQ_project_ID_dataset_name.png" src="https://files.readme.io/c784b0369c51a6e123279fdc5b2fa1fba255ae371d436e9247cb5e4685387983-13928683779089.png" width="457px" />
3. Кликните кнопку ![dcr_dl_test_connection_button.png](https://files.readme.io/8c789303491a4524515216aca06dc4b3435b5b0baa3aaa8726ff73cce968c5bc-13928683412241.png), чтобы убедиться, что Data Locker подключен к набору данных.
4. Чтобы создать подключение, кликните **Сохранить**.

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

Процедура подключения Snowflake к Data Locker состоит из 2 шагов:

* **[Шаг 1](/docs/data-clean-room-working-with-connections#step-1) —** В AppsFlyer создайте исходное подключение.
  * Это дает вашей учетной записи Snowflake доступ к AppsFlyer Snowflake share.
* **[Шаг 2](/docs/data-clean-room-working-with-connections#step-2) —** В своей учетной записи Snowflake создайте базу данных из share.
  * При этом в вашей учетной записи создается база данных, которая ссылается на таблицы в AppsFlyer share.

**Примечание.** Следующая процедура должна выполняться **администратором аккаунта** Snowflake.

<span id="step-1"></span>**Шаг 1 (создание исходного подключения) —**

1. В диалоговом окне **New connection** введите имя подключения, затем выберите **Snowflake**.
2. Введите регион вашей учетной записи Snowflake и идентификатор ID учетной записи.
   * Эту информацию можно получить, кликнув имя учетной записи в левом нижнем углу консоли Snowflake, а затем наведя указатель на имя учетной записи во всплывающем окне. **Важно!** Найдите идентификатор с меткой **Locator.** Это **НЕ** тот же идентификатор ID, который используется для создания входящих подключений Snowflake.  

     <Image align="center" alt="snowflake_account_locator.png" src="https://files.readme.io/23495b3209129f48ed1ca3442a1e96fac791d46df6f87050ac036893a050e427-13930022354961.png" width="536px" />
3. Кликните кнопку ![dcr_dl_test_connection_button.png](https://files.readme.io/8c789303491a4524515216aca06dc4b3435b5b0baa3aaa8726ff73cce968c5bc-13928683412241.png), чтобы убедиться, что Data Locker подключен к вашей учетной записи Snowflake.
4. Чтобы создать подключение, кликните **Сохранить**.

<span id="step-2"></span>**Шаг 2 (создание базы данных из share)** —

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Войдите в свой аккаунт Snowflake</Anchor>.
2. Смените роль на **Accountadmin** (Администратор аккаунта).
3. На панели слева выберите **Private Sharing.**
4. На открывшейся странице выберите вкладку **Shared With You** .
5. В общем ресурсе, имя которого начинается с **APPSFLYER**, кликните кнопку **Get data** ![snowflake_get_data_button.png](https://files.readme.io/fbda3603d504f08980bd5329aad49e5e0c562e1de556ffb0e04ad4a1abbac89c-13930725492497.png).
6. [Необязательно] В диалоговом окне **Get Data** при необходимости измените имя базы данных по умолчанию и выберите роли, которые, помимо Accountadmin, будут иметь доступ к базе данных.
7. Кликните **Get Data**, чтобы создать базу данных.

</Accordion>

<div id="s3-gcs-outbound" />

<Accordion title="Amazon S3 и GCS">

1. В диалоговом окне **New connection** в Data Locker введите имя подключения, затем выберите **Amazon S3** или **GCS**.
2. Введите имя <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-setting-up-cloud-services#облачные-корзины-amazons3-и-gcs">бакета, который вы создали</Anchor> исключительно для DCR.

</Accordion>

<div data-zendesk-anchors="overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01HKA1AS2QGDTPW85WA07K35M0=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 creating-inbound-connections=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 h_01HKA1AS2QRRBJAYNKSWWZXE3N=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 complete-the-connection-inbound=%D0%B7%D0%B0%D0%B2%D0%B5%D1%80%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HKA1AS2Q06F07RDD8W384RE2=%D0%B7%D0%B0%D0%B2%D0%B5%D1%80%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HKA1AS2QXP5H2HBJ911F3TPZ=bigquery-inbound h_01HKA1AS2QCPC6515FZ45E8Q67=snowflake-inbound h_01HKA1AS2QQZWFMRQD0T0FNQM5=s3-gcs-inbound creating-outbound-connections=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 h_01HKA1AS2QAV9DJWZQ2703TS0Z=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 h_01HKA1AS2Q76NP9FY7S4H0QP4D=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 complete-the-connection-outbound=%D0%B7%D0%B0%D0%B2%D0%B5%D1%80%D1%88%D0%B8%D1%82%D1%8C-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5 h_01HKA1AS2RKTWNY2ZR7VYAJC90=%D0%B7%D0%B0%D0%B2%D0%B5%D1%80%D1%88%D0%B8%D1%82%D1%8C-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5 h_01HKA1AS2R7RFWKM2W89QSEH3V=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01HKA1AS2RJXZPCBKE7ST0SA63=bigquery-outbound h_01HKA1AS2R7TV495V39N35CWAR=snowflake-outbound h_01HKA1AS2RBTK8NZF09BYWDX2G=s3-gcs-outbound" />

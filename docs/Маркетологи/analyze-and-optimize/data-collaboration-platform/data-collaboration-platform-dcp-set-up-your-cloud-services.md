---
title: Платформа для совместной работы с данными (DCP) — настройка облачных сервисов
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2024-04-28T14:01:34Z'
  edited_at: '2026-10-19T14:04:19Z'
  id: 24604528827921
  locale: ru
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ru/articles/24604528827921
---
> **Кратко:** Настройте облачные сервисы, чтобы подключить исходные данные к DCP и экспортировать аудитории в бакеты облачного хранилища.

<div id="about-cloud-service-setup" />

## О настройке облачных сервисов

DCP использует два типа подключений для передачи данных между вашими облачными сервисами и платформой:

* **Подключения к источникам:** позволяют подключать данные из ваших собственных источников к DCP для совместной работы и создания аудиторий.
* **Подключения к облачному хранилищу:** позволяют экспортировать ваши аудитории в бакеты облачного хранилища после каждого обновления аудитории.

Настройка подключения — это двухэтапный процесс:

* **Шаг 1:** Используйте интерфейс облачного сервиса, чтобы подготовить его к использованию с DCP.
* **Шаг 2:** Подключите его к DCP на платформе AppsFlyer. См. <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-add-connections">Платформа для совместной работы с данными (DCP) – добавление подключений</Anchor>.

В таблице ниже показано, какие сервисы поддерживаются для каждого типа подключения:

| Облачный сервис | Источник (входящий) | Облачное хранилище (исходящее) |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

Для Amazon S3 и GCS одни и те же настройки бакета и разрешения применяются как к подключениям к источникам, так и к подключениям к облачному хранилищу, поэтому отдельная настройка для каждого направления не требуется. При создании подключения к источнику автоматически создается соответствующее подключение к облачному хранилищу (и наоборот), а при удалении одного удаляется и другое, поскольку фактически это одно базовое подключение, общее для обеих вкладок.

<div id="set-up-your-cloud-services" />

## Настройте свои облачные сервисы

Ниже выберите облачный сервис, чтобы просмотреть инструкции по настройке.

<div id="amazon-s3" />

<Accordion title="Amazon S3">

Следующие инструкции помогут подготовить бакет Amazon S3 к использованию с DCP.

<div id="note" />

> 📘 **Примечание**
>
> Описанная ниже процедура должна быть выполнена вашим администратором AWS.

**Чтобы создать бакет:**

1. Войдите в консоль AWS.
2. Откройте сервис S3.
3. Создайте корзину:
   1. Нажмите **Create bucket** (Создать корзину).
   2. Заполните поле **Bucket name**, указав имя бакета, начинающееся с `af-dcr-`

       и продолжите своим текстом в соответствии с [требованиями к именованию DCR](#dcr-naming-requirements).
   3. Нажмите **Create bucket** (Создать корзину).

**Чтобы предоставить AppsFlyer права доступа к корзине:**

1. Выберите созданную вами корзину.
2. Перейдите на вкладку **Permissions** (Разрешения).
3. В разделе **Bucket policy** нажмите **Edit**. Откроется окно **Edit bucket policy**.
4. Вставьте в это окно следующий фрагмент кода:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [
             "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",
             "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
           ]
         },
         "Action": [
           "s3:GetObject",
           "s3:ListBucket",
           "s3:DeleteObject",
           "s3:PutObject"
         ],
         "Resource": [
           "arn:aws:s3:::af-dcr-mybucket",
           "arn:aws:s3:::af-dcr-mybucket/*"
         ]
       }
     ]
   }
   ```
5. Во фрагменте кода замените `af-dcr-mybucket` (в двух строках, где оно встречается) именем созданного вами бакета.
6. Примечание

<div id="important" />

> 🚧 **Двоеточие (:)**
>
> При замене имени бакета во фрагменте кода не удаляйте `/*` во второй строке, где встречается имя бакета.

</Accordion>

<div id="google-cloud-storage-gcs" />

<Accordion title="Google Cloud Storage">

Используйте следующие инструкции, чтобы подготовить бакет GCS для использования с DCP.

<div id="note-2" />

<div id="note-1" />

> 📘 **Вкладка «Разрешения»**
>
> Описанная ниже процедура должна быть выполнена вашим администратором Google Cloud.

**Чтобы создать бакет:**

1. Войдите в консоль GCS.
2. Перейдите на страницу Cloud Storage Browser.
3. Создайте корзину:
   1. Нажмите **Create bucket** (Создать корзину).
   2. Введите информацию о бакете на странице **Create a bucket**. Укажите имя бакета, начинающееся с `af-dcr-`

       и продолжите своим текстом в соответствии с [требованиями к именованию DCR](#dcr-naming-requirements).
   3. Нажмите **Продолжить**.
   4. Нажмите **Создать**.

**Чтобы предоставить AppsFlyer права доступа к корзине:**

1. Выберите созданную вами корзину.
2. Перейдите на вкладку **Permissions** (Разрешения).
3. В разделе **Permissions** нажмите **+ Add**. Откроется окно **Add members**.
4. В поле **New members** введите следующие учетные записи:
   * `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   * `af-data-delivery@af-raw-data.iam.gserviceaccount.com`
5. В списке **Role** выберите **Cloud storage** > **Storage Admin**.
6. Нажмите **Save** (Сохранить).

</Accordion>

<div id="bigquery" />

<Accordion title="BigQuery">

BigQuery поддерживает только подключения к источникам данных. Используйте следующие инструкции, чтобы создать набор данных и предоставить AppsFlyer разрешения.

> 📘 **Вкладка «Разрешения»**
>
> Описанная ниже процедура должна быть выполнена вашим администратором Google Cloud.

**Чтобы создать набор данных:**

1. Войдите в консоль Google Cloud Console.
2. Перейдите на страницу BigQuery.
3. В новом или существующем проекте Google Cloud создайте набор данных для исключительного использования DCP:
   1. На панели слева кликните значок меню с тремя точками (**View actions**) справа от идентификатора ID проекта.
   2. Выберите **Создать набор данных**.
   3. В открывшейся панели справа введите название набора данных и выберите другие необходимые параметры.
      * Можно использовать любое название: только буквы, цифры и знаки подчёркивания.
        * **Рекомендация:** используйте название, указывающее на то, что набор данных используется для подключения к источнику.
      * Не используйте параметр **Enable table expiration**, так как после истечения срока действия таблиц DCP не сможет прочитать ваши данные.
   4. Нажмите кнопку **Создать набор данных**.

**Чтобы предоставить AppsFlyer права доступа к набору данных:**

1. На панели слева нажмите значок меню с тремя точками (**View actions**) справа от созданного набора данных.
2. Выберите **Поделиться**.
3. В открывшейся панели справа нажмите **Add principal**.
4. В разделе **Add principals** введите следующий аккаунт в поле **New principals**:
   * `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
5. В разделе **Assign roles** выберите **BigQuery** > **BigQuery Data Viewer**.
6. Нажмите **Save** (Сохранить).
7. Нажмите **Close**, чтобы закрыть правую боковую панель.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Snowflake поддерживает только подключения к источникам. Воспользуйтесь следующими инструкциями, чтобы создать приватный общий доступ для использования DCP.

<div id="note-3" />

> 📘 **Вкладка «Разрешения»**
>
> Следующая процедура должна выполняться администратором аккаунта Snowflake **Accountadmin**.

**Чтобы создать приватный общий доступ:**

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Войдите в аккаунт Snowflake</Anchor>, содержащий данные, которыми вы хотите поделиться с DCP.
2. Смените роль на **Account admin**.
3. На панели слева выберите **Private Sharing**.
4. На открывшейся странице выберите вкладку **Shared By Your Account**.
5. Кликните **Поделиться**. В открывшемся списке выберите **Create a Direct Share**.
6. Выберите таблицы и/или представления, которыми вы хотите поделиться с DCP, затем нажмите **Done**.
7. Измените **Secure Share Identifier** и при необходимости добавьте дополнительное описание.
8. В поле **Add accounts in your region by name** введите аккаунт AppsFlyer Snowflake для вашего региона:

| Доход от рекламы | Аккаунт AppsFlyer |
| --- | --- |
| ЕС Запад (eu-west-1) | QL63117 |
| США Восток – Сев. Вирджиния (us-east-1) | MWB70410 |
| США Восток – Огайо (us-east-2) | BM15378 |

9. Кликните **Create Share**.

</Accordion>

<div id="salesforce-cloudcrm" />

<Accordion title="Salesforce Cloud/CRM">

Salesforce Cloud/CRM поддерживает только подключения к источникам. Инструкции по настройке см. в статье <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">DCP - Интеграция с Salesforce Data Cloud</Anchor>.

</Accordion>

<div id="traits-and-limitations" />

## Спецификации и ограничения

| Специфика | Описание |
| --- | --- |
| Поддерживаемые облачные сервисы | Amazon S3 и GCS поддерживают подключения как к источникам, так и к облачным хранилищам. BigQuery, Snowflake и Salesforce Cloud/CRM поддерживают только подключения к источникам. |
| Использование бакета | Бакеты S3 и GCS должны использоваться исключительно для DCP. Никакой другой сервис не может записывать данные в бакет. |
| <span id="dcr-naming-requirements"></span>Требования DCR к именам | В отношении всех объектов данных DCR, включая бакеты, папки и файлы, действуют следующие требования к именованию:<ul><li>**Максимальная длина:** 200 символов</li><li>**Допустимые символы:** буквы (A-Z, a-z), цифры (0-9), дефисы (-)</li><li>**Недопустимые символы:** пробелы и любые другие символы или специальные знаки</li><li>Цифры и дефисы не могут быть первым символом имени</li><li>**Только специальные символы следующего назначения:**<ul><li>Знак равенства (=): только в <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">именах папок с датой и версией</Anchor></li><li>Нижнее подчёркивание {"(_):"} только в <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#file-format">именах многочастных GZIP-файлов</Anchor> или файлов <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources#_success-files">{"_SUCCESS"}</Anchor></li><li>Точка (.): только непосредственно перед расширением имени файла (.csv, .gzip)</li></ul></li></ul> |
| Именование бакетов | Имена бакетов должны начинаться с `af-dcr-`, за которым следует ваш текст. Пример: `af-dcr-example-bucket`. |

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-add-connections">DCP — Добавить подключения</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-build-and-activate-audiences">DCP — создавайте и активируйте аудитории</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources">DCP - Создание источников и управление ими</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-guide">Руководство по Data Collaboration Platform (DCP)</Anchor>

<div data-zendesk-anchors="about-cloud-service-setup=%D0%BE-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B5-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D1%85-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%BE%D0%B2 h_01KY1VRHDTX2W1YC4QX1N093GF=%D0%BE-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B5-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D1%85-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%BE%D0%B2 set-up-your-cloud-services=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D1%81%D0%B2%D0%BE%D0%B8-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D0%B5-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D1%8B h_01KY1VRHDT63WWBPNNN3QC9N49=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D1%81%D0%B2%D0%BE%D0%B8-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D0%B5-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D1%8B h_01KY1VRHDT2GRP2MMYTKFNRN3P=amazon-s3 h_01KY1VRHDTYMG39CRENZC971RS=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01KY1VRHDVV1ZHTVV5SXGXRZ59=%D0%B4%D0%B2%D0%BE%D0%B5%D1%82%D0%BE%D1%87%D0%B8%D0%B5- h_01KY1VRHDVS3S0F22T0EQ5MCKY=google-cloud-storage-gcs h_01KY1VRHDVX4KYCT627NN92TCT=%D0%B2%D0%BA%D0%BB%D0%B0%D0%B4%D0%BA%D0%B0-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F h_01KY1VRHDVR3CZAZK0PGXDBWRC=bigquery h_01KY1VRHDV8Q3TRG7TBM5TRDYM=%D0%B2%D0%BA%D0%BB%D0%B0%D0%B4%D0%BA%D0%B0-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-1 h_01KY1VRHDVSE9WJSDFXYV7W2R3=snowflake h_01KY1VRHDVDDK9B8Y7DKA5GA75=%D0%B2%D0%BA%D0%BB%D0%B0%D0%B4%D0%BA%D0%B0-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-2 h_01KY1VRHDV9PJQMAGBY52G9RS8=salesforce-cloudcrm traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KY1VRHDVT3PYP5QVKNKQ803G=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KY1VRHDVEWNCDKZYCGWD1SRM=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

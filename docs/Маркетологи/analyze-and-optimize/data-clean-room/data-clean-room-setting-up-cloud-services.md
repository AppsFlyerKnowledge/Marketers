---
title: Data Clean Room — создание облачных сервисов
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
  created_at: '2022-03-06T08:23:55Z'
  edited_at: '2026-08-18T00:06:15Z'
  id: 4591167507217
  locale: ru
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ru/articles/4591167507217
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор.** Настройте одно или несколько локальных хранилищ данных (BigQuery, Snowflake) и/или облачных хранилищ (Amazon S3, GCS) для загрузки данных в Data Clean Room и получения отчетов.

<div id="overview" />

## Обзор

Для использования Data Clean Room (DCR) нужно настроить:

* Облачные сервисы/локации, из которых DCR считывает ваши собственные данные из ваших систем (пользовательские источники). Эти локации используются для создания **входящих подключений**.
* Облачные сервисы/локации, в которые DCR доставляет отчеты после обработки. Эти локации используются для создания **исходящих подключений**.

Создание входящих или исходящих подключений — это двухэтапный процесс:

* **Шаг 1 —** Используйте интерфейсы выбранных облачных сервисов, чтобы подготовить их к использованию с DCR (эта статья).
* **Шаг 2 —** Используйте платформу AppsFlyer для подключения к DCR. (См. статью: <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-connections">Data Clean Room: работа с подключениями</Anchor>).

<div id="note" />

> 📘 **Примечание**
>
> См. <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-sources#требования-к-данным-источника">Data Clean Room — Работа с источниками</Anchor> для получения полной информации о требованиях к исходным данным:
>
> * Формат данных *(для всех источников)*
> * Столбцы таблицы *(для источников в локальных хранилищах данных)*
> * Имя и формат файла *(для источников в облачных корзинах)*

<div id="supported-cloud-services" />

### Поддерживаемые облачные сервисы

Для входящих и исходящих подключений с DCR поддерживаются два типа облачных сервисов:

* **Локальные хранилища данных:** BigQuery и Snowflake.
* **Облачные корзины:** Amazon S3 (AWS) и GCS.

Вы можете использовать один или любую комбинацию этих сервисов для входящих и исходящих подключений.

<div id="important" />

> 🚧 **Важно!**
>
> * Если вы будете использовать несколько пользовательских источников для одного отчета, они должны быть расположены в облачных корзинах.
> * Обычно используют одну и ту же облачную корзину на Amazon S3 или GCS для входящих и исходящих подключений. Следуйте специальным инструкциям [для этой настройки](/docs/data-clean-room-setting-up-cloud-services#настройка-одной-и-той-же-облачной-корзины-для-входящих-и-исходящих-подключений).

<div id="setting-up-cloud-services-for-inbound-connections" />

## Настройка облачных сервисов для входящих подключений

Подготовьте выбранные облачные сервисы для использования с входящими подключениями DCR в соответствии с инструкциями на следующих вкладках.

<div id="data-warehouses--bigquery-and-snowflake" />

### Локальные хранилища данных — BigQuery и Snowflake.

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

**Примечание**. Описанная ниже процедура должна быть выполнена вашим администратором Google Cloud.

**Чтобы создать набор данных и предоставить DCR разрешения:**

1. Войдите в консоль Google Cloud Console.
2. Перейдите на страницу BigQuery.
3. В новом или существующем проекте Google Cloud создайте набор данных для исключительного использования DCR:
   1. На панели **слева** нажмите кнопку **Просмотр действий** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> справа от идентификатора проекта.
   2. Выберите **Создать набор данных.**

      <Image align="center" alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. В открывшейся панели **справа** введите название набора данных и выберите другие необходимые параметры.
      * Вы можете использовать любое подходящее вам название, используя только буквы, цифры и знак подчеркивания (\_).
        * **Рекомендация:** используйте название, указывающее на то, что набор данных используется для входящего подключения.
      * Настоятельно рекомендуется **НЕ** использовать опцию **Enable table expiration** (Включить срок действия таблиц), поскольку DCR не сможет прочитать источники после истечения срока действия таблиц.
   4. Нажмите кнопку <Image alt="BQ_create_dataset_button.png" src="https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png" width="88px" /> .
4. Предоставьте DCR права доступа к набору данных:
   1. На панели **слева** нажмите кнопку **Просмотр действий** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> справа от созданного набора данных.
   2. Выберите **Share** (Общая папка).
   3. В открывшейся панели **справа** нажмите кнопку ![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png) .
   4. В разделе **Добавить принципала** введите следующий аккаунт в поле **Новые принципалы**:  
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com.`
   5. В разделе **Назначение ролей** выберите **BigQuery > BigQuery Data Viewer** (BigQuery — Просмотр данных).

      <Image align="center" alt="BQ_data_viewer.png" src="https://files.readme.io/beec60ee830957ff265f8046875d1b8fa006a2c0cb60427ac969d7d45efa8b5b-14964740088721.png" width="311px" />
   6. Нажмите кнопку ***Save*** (Сохранить).
   7. Нажмите **CLOSE** (Закрыть), чтобы закрыть правую боковую панель.

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

**Примечание.** Следующая процедура должна выполняться **администратором аккаунта** Snowflake.

**Чтобы создать папку ограниченного доступа для использования DCR:**

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Войдите в аккаунт Snowflake</Anchor>, содержащий данные, которыми вы хотите поделиться с DCR.
2. Смените роль на **Accountadmin** (Администратор аккаунта).
3. На панели слева выберите **Private Sharing** (Ограниченный доступ).
4. На открывшейся странице выберите вкладку **Shared By Your Account** (Предоставлено вашим аккаунтом).

   <Image align="center" alt="snowflake_private_sharing.png" src="https://files.readme.io/e99ddd6acf3a3714ea1818fc1d28489b0ea458abac3519d6e4fe67ab643de5bb-13879858362257.png" width="609px" />
5. Нажмите кнопку **Поделиться**. В открывшемся списке выберите **Create a Direct Share** (Создать прямой обмен данными).

   <Image align="center" alt="snowflake_create_direct_share.png" src="https://files.readme.io/0a33cddd326d03a13da19a1e1b4d75a7f6a9c5479dad2fdcad52f111bc5b4e14-13879858320913.png" width="219px" />
6. Выберите таблицы и/или представления, которыми вы хотите поделиться с DCR, затем нажмите **Done** (Готово).
7. В соответствии с вашими потребностями измените **Secure Share Identifier** (Идентификатор безопасного обмена) и добавьте дополнительное описание.
8. В поле **Добавить аккаунты в вашем регионе по имени** введите один из следующих аккаунтов AppsFlyer Snowflake, в соответствии с регионом вашего аккаунта Snowflake:

| Регион | Аккаунт AppsFlyer |
| --- | --- |
| ЕС Запад (eu-west-1) | QL63117 |
| США Восток – Сев. Вирджиния (us-east-1) | MWB70410 |
| США Восток – Огайо (us-east-2) | BM15378 |

9. Нажмите кнопку **Create Share** (Создать обмен данными).

</Accordion>

<div id="cloud-storage-buckets--amazon-s3-and-gcs" />

### Облачные корзины — Amazon S3 и GCS.

Для загрузки данных в DCR можно использовать одну или несколько корзин (на Amazon S3, GCS или обе). Однако в большинстве случаев самая простая в управлении структура включает в себя одну корзину в одном облачном сервисе.

* Вы можете настроить одну и ту же корзину для использования с входящими и исходящими подключениями, следуя [этим инструкциям](/docs/data-clean-room-setting-up-cloud-services#настройка-одной-и-той-же-облачной-корзины-для-входящих-и-исходящих-подключений).

<span id="both-cloud-services"></span>Следующие требования относятся к корзинам в обоих облачных сервисах:

* **Использование.** Корзина должна быть выделена исключительно для AppsFlyer Data Clean Room. Иными словами, никакие другие сервисы не могут записывать данные в эту корзину.
* **Разрешения.** Службе AppsFlyer DCR должны быть предоставлены права доступа к соответствующей корзине. Инструкции по предоставлению этих прав приведены на вкладках по каждому облачному сервису.
* **Название.** Название корзины должно начинаться с `af-dcr-` или `af-datalocker-.`
  * Пример: `af-dcr-example-bucket`
* <span id="dcr-naming-requirements"></span>**Требования к названиям в DCR**. В отношении всех объектов данных в DCR (корзины, папки и файлы) действуют следующие требования к названиям:
  * Максимум 200 символов
  * Допустимые символы:
    * буквы `(A–Z, a–z)`
    * цифры `(0–9)`, *имя не может начинаться с цифры*
    * дефисы `(-)`, *имя не может начинаться с дефиса*
    * Недопустимые символы:
      * пробелы
      * все остальные символы или специальные символы
    * Символы, используемые только в определенных целях:
      * * знак равенства `(=)` *только если требуется в* <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">именах папок даты и времени</Anchor>
        * нижнее подчеркивание `(_)` *только для обозначения частей* <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-sources#file-format">составных файлов GZIP</Anchor> *или для файлов* <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-sources#_success-files">\_SUCCESS</Anchor>
        * точка `(.)`, *только непосредственно перед расширением файла* `(.csv, .gzip)`

<div id="amazon-s3-inbound" />

<Accordion title="Amazon S3">

**Примечание**. Описанная ниже процедура должна быть выполнена вашим администратором AWS.

**Чтобы создать корзину и предоставить разрешения AppsFlyer:**

1. Войдите в консоль AWS.
2. Откройте сервис S3.
3. Создайте корзину:
   1. Нажмите **Создать корзину**.
   2. Укажите **название корзины**, сначала префикс `af-dcr-` или `af-datalocker-` и далее ваш текст (в соответствии с требованиями [к названиям в DCR](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements) выше).
   3. Нажмите **Создать корзину**.
4. <span id="step-4"></span>Предоставьте AppsFlyer права доступа к корзине:
   1. Выберите созданную вами корзину.
   2. Перейдите на вкладку **Permissions** (Разрешения).
   3. В разделе **Bucket policy** (Политика корзины) нажмите **Edit** (Редактировать).  
      Откроется окно для **редактирования политики корзины**.
   4. <span id="code-snippet"></span>Вставьте в это окно следующий фрагмент кода.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF-DCR-DL",
            "Effect": "Allow",
            "Principal": {
              "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
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
5. Во фрагменте кода замените имя *`af-dcr-mybucket`* (в обеих строках, где оно встречается) на имя созданной вами корзины.  
   **Внимание**! *При замене имени корзины во фрагменте кода будьте внимательны, чтобы не удалить символы* `/*` *в строке, в которой имя корзины встречается второй раз.*
6. Нажмите **Save changes** (Сохранить изменения).

</Accordion>

<div id="gcs-inbound" />

<Accordion title="GCS">

**Примечание**. Описанная ниже процедура должна быть выполнена вашим администратором Google Cloud.

**Чтобы создать корзину и предоставить разрешения AppsFlyer:**

1. Войдите в консоль GCS.
2. Перейдите на страницу Cloud Storage Browser.
3. Создайте корзину:
   1. Нажмите  **Create bucket** (Создать корзину).
   2. Введите информацию о корзине на странице **создания корзины** . Укажите название корзины, сначала префикс `af-dcr-` или `af-datalocker-` и далее ваш текст (в соответствии с требованиями [к названиям в DCR](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements) выше).
   3. Нажмите **Continue** (Продолжить).
   4. Нажмите **Create** (Создать).
4. Предоставьте AppsFlyer права доступа к корзине:
   1. Выберите созданную вами корзину.
   2. Перейдите на вкладку **Permissions** (Разрешения).
   3. В разделе **Permissions** (Разрешения) нажмите **+ Add** (Добавить).  
      Откроется окно **Add members** (Добавить пользователей).
   4. В поле **New members** (Новые пользователи) введите следующий аккаунт:  
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com.`
   5. В списке **Role** (Роль) выберите **Cloud storage** (Облачное хранилище) > **Storage Admin** (Администратор хранилища).  

      <Image align="center" alt="dcr_gcs_permissions.png" src="https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png" />
   6. Нажмите кнопку ***Save*** (Сохранить).

</Accordion>

<div id="setting-up-cloud-services-for-outbound-connections" />

## Настройка облачных сервисов для исходящих подключений

DCR передает отчеты в выбранные вами облачные сервисы с помощью <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>.

* **Примечание.** Получение отчетов DCR не требует премиум-подписки на Data Locker. Если вы заинтересованы в получении других отчетов AppsFlyer через Data Locker, свяжитесь с вашим менеджером или отправьте письмо по адресу [hello@appsflyer.com](mailto:hello@appsflyer.com).

Ваши отчеты DCR могут быть доставлены в одно или несколько мест в ваших облачных сервисах (независимо от того, используете ли вы те же сервисы для входящих подключений). Подготовьте их для использования с исходящими подключениями DCR в соответствии с инструкциями на следующих вкладках.

<div id="data-warehouses--bigquery-and-snowflake-1" />

### Локальные хранилища данных — BigQuery и Snowflake.

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

**Примечание**. Описанная ниже процедура должна быть выполнена вашим администратором Google Cloud.

**Чтобы создать набор данных и предоставить разрешения Data Locker:**

1. Войдите в консоль Google Cloud Console.
2. Перейдите на страницу BigQuery.
3. В новом или существующем проекте Google Cloud создайте набор данных для эксклюзивного использования Data Locker:
   1. На панели **слева** нажмите кнопку **Просмотр действий** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> справа от идентификатора проекта.
   2. Выберите **Создать набор данных.**

      <Image align="center" alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. В открывшейся панели **справа** введите название набора данных и выберите другие необходимые параметры.
      * Вы можете использовать любое подходящее вам название, используя только буквы, цифры и знак подчеркивания (\_).
        * **Рекомендация:** используйте название, указывающее на то, что набор данных используется для исходящего подключения.
      * Настоятельно рекомендуется **НЕ** использовать опцию **Enable table expiration** (Включить срок действия таблиц), поскольку Data Locker не сможет записывать отчеты в набор данных после истечения срока действия таблиц.
   4. Нажмите кнопку <Image alt="BQ_create_dataset_button.png" src="https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png" width="88px" /> .
4. Предоставьте Data Locker права доступа к набору данных:
   1. На панели **слева** нажмите кнопку **Просмотр действий** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> справа от созданного набора данных.
   2. Выберите **Share** (Общая папка).
   3. В открывшейся панели **справа** нажмите кнопку ![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png) .
   4. В разделе **Добавить принципала** введите следующий аккаунт в поле **Новые принципалы**:  
      `datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com.`
   5. В разделе **Назначение ролей** выберите **BigQuery > BigQuery Data Editor** (BigQuery — Редактирование данных).

      <Image align="center" alt="BQ_data_editor.png" src="https://files.readme.io/cc26288d02f10805c971167d42d77efc9c7702f7fe231724b66eddd9b1b0e252-13879852726929.png" width="323px" />
   6. Нажмите кнопку ***Save*** (Сохранить).
   7. Нажмите **CLOSE** (Закрыть), чтобы закрыть правую боковую панель.

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

Процедура подготовки Snowflake к исходящим подключениям выполняется в сочетании с <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-connections#snowflake-outbound">процедурой создания самого исходящего подключения</Anchor>.

</Accordion>

<div id="cloud-storage-buckets--amazon-s3-and-gcs-1" />

### Облачные корзины — Amazon S3 и GCS.

Процедура подготовки облачных корзин к исходящим подключениям очень похожа на процедуру подготовки их к [входящим подключениям](/docs/data-clean-room-setting-up-cloud-services#настройка-облачных-сервисов-для-входящих-подключений) (включая инструкции, относящиеся к обоим облачным сервисам хранения данных).

Инструкции на вкладках ниже применяются, когда вы используете корзину **только для исходящих подключений**.

* Если вы будете использовать одну и ту же корзину для входящих и исходящих подключений, следуйте специальным инструкциям [для этой настройки](/docs/data-clean-room-setting-up-cloud-services#настройка-одной-и-той-же-облачной-корзины-для-входящих-и-исходящих-подключений).

<div id="amazon-s3-outbound" />

<Accordion title="Amazon S3">

Следуйте инструкциям по созданию [корзины Amazon S3 для входящих подключений](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) (без каких-либо изменений в этой процедуре).

</Accordion>

<div id="gcs-outbound" />

<Accordion title="GCS">

Следуйте инструкциям по созданию корзины [GCS для входящих подключений](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound). На шаге 4 этой процедуры введите следующий аккаунт в поле **Новые пользователи**:  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com.`

</Accordion>

<div id="setting-up-the-same-cloud-storage-bucket-for-both-inbound-and-outbound-connections" />

## Настройка одной и той же облачной корзины для входящих и исходящих подключений

Как уже упоминалось, обычно используют одну и ту же облачную корзину на Amazon S3 или GCS для входящих и исходящих подключений.

Инструкции по этой настройке лишь незначительно отличаются от [инструкций для входящих подключений](/docs/data-clean-room-setting-up-cloud-services#настройка-облачных-сервисов-для-входящих-подключений). Однако они различаются в зависимости от того, что вы делаете:

* создаете новую корзину для входящих и исходящих подключений DCR ***или***
* изменяете корзину, ранее использовавшуюся только для Data Locker, в корзину, которая теперь используется для входящих и исходящих подключений DCR.

Инструкции для обоих этих сценариев содержатся на вкладках ниже:

<div id="amazon-s3-inbound-outbound" />

<Accordion title="Amazon S3">

<div id="creating-a-new-bucket-for-inboundoutbound-connections" />

#### Создание новой корзины для входящих и исходящих подключений

Следуйте инструкциям по созданию [корзины Amazon S3 для входящих подключений](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) (без каких-либо изменений в этой процедуре).

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker" />

#### Изменение существующей корзины, ранее использовавшейся только для Data Locker

Изменение существующей корзины, которую вы ранее использовали только для Data Locker, требует изменения разрешений корзины (чтобы разрешить доступ как DCR, так и Data Locker).

**Чтобы изменить разрешения корзины:**

1. Войдите в консоль AWS.
2. Откройте сервис S3.
3. Выберите корзину, которая ранее использовалась только для Data Locker.
4. Перейдите на вкладку **Permissions** (Разрешения).
5. В разделе **Bucket policy** (Политика корзины) нажмите **Edit** (Редактировать).  
   Откроется окно для **редактирования политики корзины**.
6. **Замените контент** окна следующим фрагментом кода:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
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

   * Во фрагменте кода замените имя *`af-dcr-mybucket`* (в обеих строках, где оно встречается) на имя созданной вами корзины.
   * **Внимание**! *При замене имени корзины во фрагменте кода будьте внимательны, чтобы не удалить символы* `/*` *в строке, в которой имя корзины встречается второй раз.*
7. Нажмите **Save changes** (Сохранить изменения).

</Accordion>

<div id="gcs-inbound-outbound" />

<Accordion title="GCS">

<div id="creating-a-new-bucket-for-inboundoutbound-connections-1" />

#### Создание новой корзины для входящих и исходящих подключений

Следуйте инструкциям по созданию корзины [GCS для входящих подключений](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound). На шаге 4 этой процедуры введите следующие **2 аккаунта** в поле **Новые пользователи**:  
`appsflyer-dcr@dcr-report.iam.gserviceaccount.com`  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker-1" />

#### Изменение существующей корзины, ранее использовавшейся только для Data Locker

Изменение существующей корзины, которую вы ранее использовали только для Data Locker, требует изменения разрешений корзины (чтобы разрешить доступ как DCR, так и Data Locker).

**Чтобы изменить разрешения корзины:**

1. Войдите в консоль GCS.
2. Перейдите на страницу Cloud Storage Browser.
3. Выберите корзину, которая ранее использовалась только для Data Locker.
4. Перейдите на вкладку **Permissions** (Разрешения).
5. В разделе Permissions (Разрешения) нажмите **+ Add** (Добавить).  
   Откроется окно **Add members** (Добавить пользователей).
6. В поле **New members** (Новые пользователи) введите следующий аккаунт:  
   `appsflyer-dcr@dcr-report.iam.gserviceaccount.com.`
7. В списке **Role** (Роль) выберите **Cloud storage** (Облачное хранилище) > **Storage Admin** (Администратор хранилища).  

   <Image align="center" alt="dcr_gcs_permissions.png" src="https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png" />
8. Нажмите кнопку ***Save*** (Сохранить).

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01J6Y2P4CKMZ3R8WZ4X76DZ6ZY=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01J6Y2P4CMJ4CXJZ3EDDXQG4Y3=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 supported-cloud-services=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D0%B5-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D1%8B h_01J6Y2P4CMNMTSPWDK9GGSDYMJ=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D0%B5-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D1%8B h_01J6Y2P4CM8VDWCD5XH91DJPYX=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-cloud-services-inbound=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D1%85-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%BE%D0%B2-%D0%B4%D0%BB%D1%8F-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 h_01J6Y2P4CM61DEXMWB626X25TT=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D1%85-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%BE%D0%B2-%D0%B4%D0%BB%D1%8F-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 data-warehouses-inbound=%D0%BB%D0%BE%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%85%D1%80%D0%B0%D0%BD%D0%B8%D0%BB%D0%B8%D1%89%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-bigquery-%D0%B8-snowflake h_01J6Y2P4CMDX64XXGNS7ZP3GKZ=%D0%BB%D0%BE%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%85%D1%80%D0%B0%D0%BD%D0%B8%D0%BB%D0%B8%D1%89%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-bigquery-%D0%B8-snowflake h_01J6Y2P4CMY5DHFEFGHQQPAPK9=bigquery-inbound h_01J6Y2P4CMMZFYDZWK82F5J65W=snowflake-inbound cloud-storage-buckets-inbound=%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D0%B5-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-amazons3-%D0%B8-gcs h_01J6Y2P4CMCJDT2W6C52MF71TB=%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D0%B5-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-amazons3-%D0%B8-gcs h_01J6Y2P4CMS2JF9Z7F13XW485F=amazon-s3-inbound h_01J6Y2P4CM9Y9114CH1ESY0QPJ=gcs-inbound setting-up-cloud-services-outbound=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D1%85-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%BE%D0%B2-%D0%B4%D0%BB%D1%8F-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 h_01J6Y2P4CMEEG6PNM2PMEYGQ3A=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D1%85-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%BE%D0%B2-%D0%B4%D0%BB%D1%8F-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 data-warehouses-outbound=%D0%BB%D0%BE%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%85%D1%80%D0%B0%D0%BD%D0%B8%D0%BB%D0%B8%D1%89%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-bigquery-%D0%B8-snowflake-1 h_01J6Y2P4CMNWQ0D3EZXJZZM1EY=%D0%BB%D0%BE%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%85%D1%80%D0%B0%D0%BD%D0%B8%D0%BB%D0%B8%D1%89%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-bigquery-%D0%B8-snowflake-1 h_01J6Y2P4CM8MVS3SZAYE2YDV2T=bigquery-outbound h_01J6Y2P4CN97P8GCV314TQ91EE=snowflake-outbound cloud-storage-buckets-outbound=%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D0%B5-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-amazons3-%D0%B8-gcs-1 h_01J6Y2P4CNZ61PG9BTCVRFZ20K=%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D1%8B%D0%B5-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-amazons3-%D0%B8-gcs-1 h_01J6Y2P4CN4ZRAMQ2E3R4Q4KHS=amazon-s3-outbound h_01J6Y2P4CN39GT0QT6THFAA3ZY=gcs-outbound setting-up-cloud-services-inbound-outbound=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%B4%D0%BD%D0%BE%D0%B9-%D0%B8-%D1%82%D0%BE%D0%B9-%D0%B6%D0%B5-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%BE%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%B8-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 h_01J6Y2P4CN2ARMJKRSAFZNN59G=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%B4%D0%BD%D0%BE%D0%B9-%D0%B8-%D1%82%D0%BE%D0%B9-%D0%B6%D0%B5-%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%BE%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%B8-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 h_01J6Y2P4CNKC9P1FKECHZJ6AXP=amazon-s3-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BD%D0%BE%D0%B2%D0%BE%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%B8-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 h_01J6Y2P4CN216K0VZSWRP699TF=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BD%D0%BE%D0%B2%D0%BE%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%B8-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9 modifying-an-existing-bucket-previously-used-only-for-data-locker=%D0%B8%D0%B7%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D1%83%D1%89%D0%B5%D1%81%D1%82%D0%B2%D1%83%D1%8E%D1%89%D0%B5%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D1%80%D0%B0%D0%BD%D0%B5%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%B2%D1%88%D0%B5%D0%B9%D1%81%D1%8F-%D1%82%D0%BE%D0%BB%D1%8C%D0%BA%D0%BE-%D0%B4%D0%BB%D1%8F-data-locker h_01J6Y2P4CNDW888XTMKAMZAFCS=%D0%B8%D0%B7%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D1%83%D1%89%D0%B5%D1%81%D1%82%D0%B2%D1%83%D1%8E%D1%89%D0%B5%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D1%80%D0%B0%D0%BD%D0%B5%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%B2%D1%88%D0%B5%D0%B9%D1%81%D1%8F-%D1%82%D0%BE%D0%BB%D1%8C%D0%BA%D0%BE-%D0%B4%D0%BB%D1%8F-data-locker h_01J6Y2P4CN0MEEKG0D2SKMDZVY=gcs-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections::e1cda9c8=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BD%D0%BE%D0%B2%D0%BE%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%B8-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9-1 h_01J6Y2P4CN336CRH1CWRJVCHHY=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BD%D0%BE%D0%B2%D0%BE%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%B8-%D0%B8%D1%81%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B8%D1%85-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B9-1 modifying-an-existing-bucket-previously-used-only-for-data-locker::ba0d4803=%D0%B8%D0%B7%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D1%83%D1%89%D0%B5%D1%81%D1%82%D0%B2%D1%83%D1%8E%D1%89%D0%B5%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D1%80%D0%B0%D0%BD%D0%B5%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%B2%D1%88%D0%B5%D0%B9%D1%81%D1%8F-%D1%82%D0%BE%D0%BB%D1%8C%D0%BA%D0%BE-%D0%B4%D0%BB%D1%8F-data-locker-1 h_01J6Y2P4CNYCTVGN6CH0748S24=%D0%B8%D0%B7%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D1%81%D1%83%D1%89%D0%B5%D1%81%D1%82%D0%B2%D1%83%D1%8E%D1%89%D0%B5%D0%B9-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D1%8B-%D1%80%D0%B0%D0%BD%D0%B5%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%B2%D1%88%D0%B5%D0%B9%D1%81%D1%8F-%D1%82%D0%BE%D0%BB%D1%8C%D0%BA%D0%BE-%D0%B4%D0%BB%D1%8F-data-locker-1" />

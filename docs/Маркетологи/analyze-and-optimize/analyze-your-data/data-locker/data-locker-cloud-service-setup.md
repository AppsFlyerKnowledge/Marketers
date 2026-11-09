---
title: 'Data Locker: настройка облачного сервиса'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-02-10T17:35:25Z'
  edited_at: '2026-08-27T00:04:22Z'
  id: 360017603577
  locale: ru
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/ru/articles/360017603577
---
> **Краткий обзор**: Настройте свой облачный сервис для получения данных из Data Locker: GCS, AWS, BigQuery или Snowflake.

Data Locker позволяет передавать потоковые данные в выбранное вами собственное хранилище – бакет или хранилище данных. Настройте облачный сервис, используя одну из следующих процедур.

<div id="bucket-cloud-storage" />

## Облачная корзина

<div id="gcs-storage" />

<Accordion title="Хранилище GCS">

Прежде чем начать, обратите внимание на следующее:

* Процедуру, описанную в этом разделе, должен выполнить ваш администратор Google Cloud.
* Вы можете удалить файлы из Data Locker через 25 и более часов после того, как они были созданы. Не удаляйте файлы до истечения этого времени.

**Информация для администратора GCS**

Data Locker — это решение AppsFlyer для потоковой передачи данных в хранилище.

**Требования**

* Создайте бакет GCS исключительно для использования Data Locker. Исключительно означает, что никакие другие сервисы не должны записывать данные в эту корзину.
* Рекомендуемое название корзины: `af-datalocker`.
* Предоставьте Data Locker необходимые разрешения, используя следующую процедуру.

**Чтобы предоставить разрешения Data Locker:**

В этой процедуре замените `data-locker-example`, указанное значение на имя бакета, который вы ранее создали для Data Locker.

1. Войдите в консоль GCS.
2. Перейдите в **Хранилище** > **Браузер хранилища**

   <Image align="center" alt="mceclip0.png" src="https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png" />
3. Выберите бакет, который вы создали ранее, например `data-locker-example`.
4. Перейдите на вкладку **Разрешения**.
5. Нажмите **+Добавить**.  
   Откроется окно Add members (Добавить пользователей).
6. Заполните следующим образом:
   1. **Новые члены**, вставьте следующий фрагмент.

      ```http
      af-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```
   2. **Выберите роль**: **Cloud storage** > **Storage Object Admin** (Администратор объектов хранилища).

      <Image align="center" alt="mceclip0.png" src="https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png" />
7. Нажмите **Сохранить**.

</Accordion>

<div id="aws-storage" />

<Accordion title="Хранилище AWS">

Прежде чем начать, обратите внимание на следующее:

* Процедуру, описанную в этом разделе, должен выполнить ваш администратор AWS.
* Вы можете удалить файлы из Data Locker через 25 и более часов после того, как они были созданы. Не удаляйте файлы до истечения этого времени.

**Информация для администратора AWS**

Data Locker — это решение AppsFlyer для потоковой передачи данных в хранилище.

**Требования**

* Создайте AWS- бакет с именем af-datalocker -mybucket. Префикс af-datalocker- обязателен. В суффиксе можно указать любое текстовое значение.
* Рекомендуем использовать формат "af-datalocker-гггг-мм-дд-чч-мм-произвольный-текст". Где "гггг-мм-дд-чч-мм" — это текущие дата и время, и вы можете добавить любой текст произвольно, как описано на следующем изображении.

**Пользовательский интерфейс в консоли AWS**

<Image align="center" alt="MyBucket.jpg" src="https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg" />

После создания бакета предоставьте AppsFlyer необходимые разрешения, используя следующие правила.

**Чтобы создать корзину и предоставить разрешения AppsFlyer:**

1. Войдите в консоль AWS.
2. Откройте сервис S3.
3. **Чтобы создать корзину**:
   1. Нажмите **Create bucket** (Создать корзину).
   2. Заполните **название корзины** следующим образом: Начните с `af-datalocker-` и затем добавьте любой другой текст, как описано выше.
   3. Укажите один из [поддерживаемых AWS](#поддерживаемые-регионы-aws) регионов.
   4. Нажмите **Создать корзину**.
4. **Чтобы предоставить разрешения AppsFlyer:**
   1. Выберите корзину.
   2. Перейдите на вкладку **Разрешения**.
   3. В разделе **Политика бакета** нажмите **Редактировать**.   
      Откроется окно политики корзины.
   4. Вставьте в это окно следующий фрагмент кода.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF_DataLocker_Direct",
            "Effect": "Allow",
            "Principal": {
              "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-datalocker-my-bucket",
              "arn:aws:s3:::af-datalocker-my-bucket/*"
            ]
          }
        ]
      }
      ```
5. В этом коде замените `af-datalocker-my-bucket` на название созданного вами бакета.
6. [Необязательно] Добавьте поддержку бакетов с шифрованием KMS. Для этого в разделе **Политика ключей выберитеПереключиться в режим просмотра политики вставьте следующий фрагмент в** Массив утверждений.

   ```json
   {
         "Sid": "Разрешить использование ключа",
         "Effect": "Allow",
         "Principal": {
             "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
         },
         "Action": "kms:GenerateDataKey*",
         "Resource": "*"
     }
   ```
7. Выберите **Сохранить изменения**.
8. Выполните <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers#настройка-параметров-отчета-data-locker">процедуру настройки Data Locker</Anchor>.

<div id="supported-aws-regions" />

#### **Поддерживаемые регионы AWS**

Data Locker поддерживает следующие регионы для AWS:

* Азиатско-Тихоокеанский регион (Токио): `ap-northeast-1`
* Азиатско-Тихоокеанский регион (Сеул): `ap-northeast-2`
* Азиатско-Тихоокеанский регион (Мумбаи): `ap-south-1`
* Азиатско-Тихоокеанский регион (Сингапур): `ap-southeast-1`
* Азиатско-Тихоокеанский регион (Сидней): `ap-southeast-2`
* Канада (Центральный): `ca-central-1`
* ЕС (Франкфурт): `eu-central-1`
* ЕС (Ирландия): `eu-west-1`
* ЕС (Лондон): `eu-west-2`
* Южная Америка (Сан-Паулу): `sa-east-1`
* США, восток (Сев. США Восток (Северная Вирджиния): `us-east-1`
* США Восток (Огайо): `us-east-2`
* США, запад (Сев. США Запад (Северная Калифорния): `us-west-1`
* США Запад (Орегон): `us-west-2`

</Accordion>

<div id="beta--azure-storage" />

<Accordion title="Хранилище Azure">

Прежде чем начать, обратите внимание на следующее:

* Процедуру, описанную в этом разделе, должен выполнить ваш администратор Azure Cloud.
* Вы можете удалить файлы из Data Locker через 25 и более часов после того, как они были созданы. Не удаляйте файлы до истечения этого времени.

**Информация для администратора Azure**

Data Locker — это решение AppsFlyer для потоковой передачи данных в ваш аккаунт хранилища.

**Чтобы определить аккаунт хранилища для Data Locker:**

1. На портале Azure перейдите в [учетные записи хранилищ Azure](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) и нажмите <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Создать**, чтобы создать новую учетную запись хранилища для получения данных Appsflyer. и нажмите <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Создать**, чтобы создать учетную запись хранения для получения данных AppsFlyer.
2. На вкладке**Базовый>Детали проекта** выберите из выпадающих списков:
   1. **подписку**;
   2. **группу ресурсов.**  
      Необязательно: Если группы ресурсов не существует, нажмите **Создать новую**, чтобы создать группу ресурсов.
3. В разделе **Детали события:**
   1. Введите **Название учётной записи хранения.**
   2. Выберите **регион** из ниспадающего списка.
4. Нажмите **Далее. Advanced (Расширенные настройки) >**
5. Во вкладке **Безопасность** выберите **Включить иерархический список имен.**
6. Нажмите**Обзор -> Создать.**
7. После завершения развертывания вернитесь к своим [учетным записям хранилища Azure](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) и выберите только что созданную учетную запись.
8. Перейдите к **Ключи доступа**, скопируйте своё **Название учётной записи хранилища** и один из ваших **ключей**.
9. Перейдите к **Обозреватель хранилищ -> Blob-контейнеры**и нажмите <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Добавить контейнер.**
   1. Введите **Название** для нового контейнера.
   2. Нажмите **Создать.**
10. После активации в AppsFlyer перейдите в <Anchor target="_blank" href="https://hq1.appsflyer.com/datalocker/overview">**Data Locker**</Anchor> **> <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />Новое соединение.**
11. В новом соединении:
    1. Дайте название подключению.
    2. Выберите **Azure Blob**.
    3. Введите **Название контейнера**Azure в поле **Название бакета** (то же самое, что и на шаге 9).
    4. Введите ваше скопированное **Название учётной записи хранения** из шага 8.
    5. Введите скопированный**Ключ** из шага 8.
    6. Нажмите **Тестировать подключение**.
    7. **Сохранить**

</Accordion>

<div id="yandex" />

<Accordion title="[Бета-версия] Облачное хранилище Yandex Cloud">

Прежде чем начать, обратите внимание на следующее:

* Процедуру, описанную в этом разделе, должен выполнить ваш администратор Yandex Cloud.
* Вы можете удалить файлы из Data Locker через 25 и более часов после того, как они были созданы. Не удаляйте файлы до истечения этого времени.

**Информация для администратора Yandex**

Data Locker — это решение AppsFlyer для потоковой передачи данных в хранилище.

**Чтобы создать корзину и предоставить разрешения Data Locker:**

1. В вашей консоли <Anchor target="_blank" href="https://console.cloud.yandex.com/">Yandex Cloud</Anchor> перейдите на вкладку **Служебная учетная запись** и нажмите **Создать служебный аккаунт**.
2. Назовите аккаунт службы, например, `af-datalocker`.
3. Создайте статический ключ доступа для аккаунта службы. В служебном аккаунте:
   1. Нажмите **Создать новый ключ**.
   2. Выберите **Создать статический ключ доступа**.
   3. Сохраните **идентификатор ключа** и **секретный ключ**.
4. Дайте новому аккаунту службы разрешение **storage.editor**
   1. В настройках бакета откройте раздел **«Привязки доступа»** и нажмите **«Назначить привязки»**.
   2. Для нового служебного аккаунта добавьте роль **редактор хранилища** и нажмите **Сохранить**.
5. Свяжитесь с вашим менеджером AppsFlyer, чтобы включить Яндекс в Data Locker.
6. После включения используйте идентификатор ключа и секретный ключ во время настройки <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers#set-up-data-locker">Data Locker</Anchor>.

</Accordion>

<div id="data-warehouse-cloud-storage" />

## Облачное хранилище данных

<div id="bigquery" />

<Accordion title="BigQuery">

Процедуру, описанную в этом разделе, должен выполнить ваш администратор BigQuery.

**Информация для администратора BigQuery**

Data Locker — это решение AppsFlyer для потоковой передачи данных в хранилище.

**Требования**

* Создайте набор данных BigQuery

**Чтобы создать набор данных BigQuery:**

1. В BigQuery создайте проект или используйте существующий проект
2. В проекте нажмите **CREATE DATASET**. [![GCSCreateDataSEt_1_.png](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)
3. Присвойте набору данных подходящий идентификатор.

   <div id="note" />

   > 📘 **Примечание:**
   >
   > Убедитесь, что целевой проект или набор данных связан с активным биллинговым счётом. Без биллингового счёта Data Locker не сможет создавать и записывать таблицы в назначении BigQuery, и процесс настройки подключения может завершиться неудачей.

4. Предоставьте AppsFlyer доступ к этому набору данных. <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">См. инструкции BigQuery</Anchor>
   * Для **Add principal** (Добавить принципала) используйте следующего пользователя AppsFlyer: [datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com.](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   * Для **Assign roles** (Назначить роли), выберите BigQuery Data Editor (Редактор данных BigQuery).
5. Задайте значения других необходимых параметров.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Подключите Data Locker к своему аккаунту Snowflake. Данные будут отправляться в Snowflake и останутся доступны в выбранном вами облачном хранилище.

**Примечания для разработчиков решений бизнес-аналитики**

* Частота обновления данных такая же, как и для данных, предоставляемых в бакете.
* Структура таблиц и столбцов соответствует структуре данных, доступных непосредственно в бакете Data Locker.
* По мере добавления строк в общий доступ Snowflake, `_ingestion_time` столбец заполняется в местном часовом поясе системы (не UTC). Чтобы обеспечить уникальность строк и не допустить многократный импорт одной и той же строки:
  1. Сохраните `max_ingestion_time` для таблицы, которая была загружена.
  2. При каждом запуске процесса импорта загружать только те строки, у которых `_ingestion_time > max_ingestion_time`.

Выполните следующие действия, чтобы подключить Snowflake к Data Locker.

<div id="snowflake-connector-procedures" />

#### **Процедура для коннектора Snowflake**

**Чтобы узнать регион и идентификатор аккаунта Snowflake**:

1. В Snowflake <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">войдите в свой аккаунт Snowflake</Anchor>.
2. В строке меню выберите свое имя.  
   Появятся регион и идентификатор аккаунта.

   <Image align="center" alt="Детали учетной записи Snowflake" src="https://files.readme.io/6f508a5c2c6cd5dd84dd2639c73e62ff819e0a06ea3323d7a999a6b4fc717009-40394499797393.png" width="875px" />

**Чтобы подключить Data Locker к Snowflake**:

1. В AppsFlyer перейдите в раздел **Отчеты** > **Data Locker**.
2. Выберите Snowflake.
3. Введите регион Snowflake и идентификатор учётной записи, используя сведения, ранее полученные от Snowflake.
4. Нажмите **Сохранить**.

**Чтобы** **создать базу данных из общей папки Snowflake**:

1. В Snowflake <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">войдите в свой аккаунт Snowflake</Anchor>.
2. Смените роль на **Accountadmin** (Админстратор аккаунта). См. раздел <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share">Создание базы данных из общей папки</Anchor>.
3. Выберите **Shares** (Общие папки).
4. Выберите общую папку AppsFlyer. Например, APPSFLYER\_ACC\_XXX\_DATA\_LOCKER.
5. Нажмите **Create Database from Secure Share** и укажите необходимые данные. **Важно!** Обязательно загрузите данные из общей базы в свои таблицы, поскольку срок их доступности в базе данных ограничен (в настоящее время – 14 днями).
6. В вашей базе данных отображаются импортированные таблицы. Названия и структура таблиц аналогичны используемым в корзинах Data Locker.

</Accordion>

<div id="traits-and-limitations" />

## Характеристики и ограничения

| Специфика | Описание |
| --- | --- |
| Подключение к облаку AppsFlyer | Отчеты не могут храниться в несжатом виде |
| Изменение местоположения набора данных BigQuery | Если вы измените расположение набора данных в BigQuery, необходимо заново сохранить соединение в AppsFlyer. Поскольку в настройках подключения AppsFlyer не требуется изменений конфигурации, кнопка**Сохранить** отключена. Чтобы активировать кнопку, внесите временное изменение, сохраните соединение, затем отмените изменение и снова сохраните соединение. |
| Поддерживаемые регионы Snowflake | **Поддерживаемые регионы AWS:**<ul><li>us-east-1</li><li>us-east-2</li><li>us-west-2</li><li>eu-west-1</li><li>eu-west-2</li><li>eu-west-3</li><li>eu-central-1</li><li>eu-north-1</li><li>ca-central-1</li><li>sa-east-1</li><li>ap-south-1</li><li>ap-southeast-1</li><li>ap-southeast-2</li><li>ap-northeast-1</li><li>ap-northeast-2</li><li>ap-northeast-3</li></ul>**Поддерживаемые регионы Azure:**<ul><li>australia-east</li><li>east-us-2</li><li>central-us</li><li>southcentral-us</li><li>west-europe</li><li>west-us-2</li></ul>**Поддерживаемые регионы GCP:**<ul><li>Ограниченная поддержка. Свяжитесь с поддержкой AppsFlyer, чтобы подтвердить доступность для вашего региона.</li></ul> |

<div data-zendesk-anchors="bucket-cloud-storage=%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%B0%D1%8F-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D0%B0 h_01HE2SPKYZWFXA63YD5NK4KJRD=%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%B0%D1%8F-%D0%BA%D0%BE%D1%80%D0%B7%D0%B8%D0%BD%D0%B0 h_01HE2SPKYZM9QQCGFN86J7FNDY=gcs-storage h_01HE2SPKYZK4F9E22MG3K8SJE8=aws-storage supported-aws-regions=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D1%80%D0%B5%D0%B3%D0%B8%D0%BE%D0%BD%D1%8B-aws h_01J2DSZ4NVVMTTNSXP2Z9DAS0Q=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D1%80%D0%B5%D0%B3%D0%B8%D0%BE%D0%BD%D1%8B-aws %5Bbeta%5D-azure-storage=beta--azure-storage h_01HE2SRAJA94R8ZKHRBEFNKX8D=beta--azure-storage h_01HE2SPKYZXAXMKPH5DQV40X1W=yandex data-warehouse-cloud-storage=%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%BE%D0%B5-%D1%85%D1%80%D0%B0%D0%BD%D0%B8%D0%BB%D0%B8%D1%89%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HE2SPKYZ77X8WP9ZNRB1D05B=%D0%BE%D0%B1%D0%BB%D0%B0%D1%87%D0%BD%D0%BE%D0%B5-%D1%85%D1%80%D0%B0%D0%BD%D0%B8%D0%BB%D0%B8%D1%89%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HE2SPKYZMNW776CZRZAFVV5H=bigquery h_01JXQM7DAHD40DJYERY106H826=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HE2SPKYZC3W4G3YXFM10H9D3=snowflake snowflake-connector-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%BD%D0%BD%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D0%B0-snowflake h_01HE2SPKYZ11B1MJYX2HRCS07D=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0-%D0%B4%D0%BB%D1%8F-%D0%BA%D0%BE%D0%BD%D0%BD%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D0%B0-snowflake traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KYVRP8CVMD01EZY5561W2RCJ=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />

---
title: Отчеты с сырыми данными PBA
metadata:
  keywords:
    - Data Locker
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-07-01T07:53:57Z'
  edited_at: '2026-08-31T00:23:06Z'
  id: 360001917778
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/360001917778
---
> **Краткий обзор**: отчеты с сырыми данными PBA доступны через Data Locker.

<div id="pba-raw-data-reports" />

## Отчеты с сырыми данными PBA

Используйте отчеты с сырыми данными PBA для анализа путей и действий пользователей.

<div id="report-descriptions" />

### Описание отчетов

Темы отчетов с сырыми данными PBA

| Тема отчета с сырыми данными | Описание |
| --- | --- |
| <span id="website-visits"></span>[Посещения сайта](#website-visits-and-website-events) | <ul><li>Посещения сайта.</li><li>Измеряйте воздействие кампаний по привлечению веб-трафика и взаимодействие пользователей с этими кампаниями.</li></ul> |
| <span id="website-events"></span><Anchor target="_blank" href="/marketers/ru/docs/pba-website-attribution-dashboard">События на сайте</Anchor> | <ul><li>Содержит действия, выполняемые посетителями сайта, такие как подписка или покупка.</li><li>События атрибутируются последнему за предыдущие 30 дней непрямому посещению сайта.</li><li>Параметры атрибуции, связанные с событием, например, медиа-источник, медиа-канал, кампания и др.</li><li>Используйте эти параметры для оптимизации маркетинговых активностей.</li><li>Анализируйте поведение пользователей по медиа-источнику.</li><li>Значения этих полей определяются на основе атрибутированного посещения по <Anchor target="_blank" href="/marketers/ru/docs/pba-media-source-attribution-rules">правилам атрибуции медиа-источников PBA.</Anchor></li><li>Цель: связывать события с определенным посещением сайта, а не просмотром страницы.</li><li>Определите по этому отчету, какие источники и кампании привлекают пользователей и какие действия эти пользователи выполняют.</li></ul> |

<div id="raw-data-report-fields" />

## Поля отчета с сырыми данными

<div id="website-visits-and-website-events" />

<Accordion title="Посещения сайта и события на сайте">

<div id="sample-reports" />

#### Примеры отчетов

* События сайта: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=1096347999&single=true&output=csv">CSV</Anchor>
* Посещения сайта: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=432734495&single=true&output=csv)

Поля в отчетах с сырыми данными частично заполняются на основе данных из ссылки атрибуции пользователей мобильного приложения и события установки приложения.

[Скачать список полей в формате CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmRBeUQS-xeiv069vIgnfBoJW8Wfl1ojv0rAK-pcOlAzNveG1lqvExVdhWfgCKIpJxczWksUiHjSa3/pub?gid=0&single=true&output=csv)

<div id="field-list-website-visits-and-website-events-report" />

#### Список полей в отчетах «Посещения сайта» и «События на сайте»:

| Имя поля | Описание | Формат | Пример |
| --- | --- | --- | --- |
| рекламный\_идентификатор | Рекламный идентификатор (GAID) | строка | 7fzzz3fa-8bad-46c9-bb03-fffffffffffffffffffffffff |
| af\_web\_id | Идентификатор файла cookie, отправляемый из веб-SDK | строка | 68972980-58f9-4ca6-8743-c0d633364b6d |
| amazon\_aid | Рекламный идентификатор Amazon Fire TV | строка | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| android\_id | Идентификатор устройства Android | строка | 68999980-58f9-4ca6-8743-c0d633364b6d |
| app\_id (идентификатор приложения) | Идентификатор последнего установленного приложения | строка | id123456789 |
| имя\_приложения | Последнее название приложения | строка | Мое приложение |
| версия\_приложения | Последняя версия приложения | строка | 6.32 |
| appsflyer\_id | Идентификатор AppsFlyer (установка) | строка | 1594825729709-5655157112349378588 |
| attributed\_touch\_time | Посещения сайта: время посещения. События на сайте: время события. | гггг-мм-дд чч:мм:сс | 9/17/2020 0:09:25 |
| attributed\_touch\_type (атрибутированный тип взаимодействия) | Тип точки взаимодействия. На данный момент всегда задается как посещение сайта. | строка | Посещение сайта |
| Авторизовано | Идентификатор пакета PBA | строка | 048db9bf-97r7-4m2f-919b-607b7kk806d0 |
| campaign (кампания) | Атрибутируется посещению сайта | строка | Летняя кампания |
| campaign\_id (идентификатор кампании) | Атрибутируется посещению сайта | строка | 12343425 |
| город | Определено по IP-адресу | строка | Спринг Вэлли |
| код\_страны | Определено по IP-адресу | строка | США |
| идентификатор\_пользователя\_клиента | Идентификатор клиента (CUID) | строка | 5a8771ecbb986ABC |
| тип\_устройства | Тип устройства | строка | Десктоп |
| дма | Определено по IP-адресу | строка | 501 |
| имя\_события | В отчете о посещениях сайта: всегда посещение сайта. В отчете о посещениях сайта: eventName, отправленное из веб-SDK. | строка | покупка |
| event\_revenue | Сумма дохода от события в валюте покупки | строка | 199.99 |
| event\_currency | 3-символьный код валюты event\_revenue | строка | USD, ZAR, EUR |
| event\_revenue\_usd | event\_revenue в долларах США | строка | 57.46 |
| источник события | Веб-SDK или сервер-сервер | строка | веб-SDK, S2S |
| время\_события | События на сайте | гггг-мм-дд чч:мм:сс | 9/17/2020 0:09:25 |
| тип\_события | Следующие: стандартное событие, событие конверсии, посещение сайта | строка | событие конверсии |
| event\_url | URL-адрес веб-страницы, на которой произошло событие (соответствует исходному URL-адресу в посещениях сайта) | строка | http://www.brandpit.com/checkout |
| event\_value | События на сайте: сведения о значении события, содержащиеся в JSON. Посещения сайта: всегда null. | JSON | `{"sku": "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}` |
| IDFA | Рекламный идентификатор | строка | A56B9887-FEBA-458C-BEFC-C891F9DF7681 |
| IDFV | Рекламный идентификатор | строка | EBC2F523-B1E5-4484-A4C8-ADC32DC7C23D |
| imei | Идентификатор устройства | строка | 3532211234 |
| время\_установки | Последнее время установки приложения | гггг-мм-дд чч:мм:сс | 9/17/2020 0:09:25 |
| ip | IP-адрес посетителя | строка | 24.7.104.115 |
| язык | Переданный user agent | строка | Английский |
| медиа\_канал | Атрибутируется посещению сайта | строка | Реклама |
| медиа-источник | Атрибутируется посещению сайта | строка | googleadwords\_int |
| media\_type | Атрибутируется посещению сайта | строка | Платный |
| oaid | Рекламный идентификатор | строка | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| original\_url | URL-адрес, перенаправивший пользователя на сайт при атрибутированном посещении сайта | строка | https://www.brandpitt.com/signin?utm_source=Googleg&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld |
| platform | Платформа | строка | macOS |
| postal\_code | Определено по IP-адресу | строка | 10977 |
| query\_params | Параметры запроса в URL перенаправления (после ?) Параметры запроса в URL перенаправления (после ?) Параметры запроса в URL-адресе перенаправления (после ?) Пример: https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes Если в URL-адресе нет параметров запроса, это поле имеет значение null | JSON | `{"c":"summer",af_siteid":"publisher",af_sub1":helloworld",af_keywords":"shoes","utm_source":"Google","utm_campaign":"cool","utm_term":"shoes"}` |
| Referrer | HTTP-реферер атрибутированного посещения сайта | строка | https://www.google.com/ |
| Регион | Определено по IP-адресу | строка | NA |
| Состояние | Определено по IP-адресу | строка | Нью-Йорк |

</Accordion>

<div id="field-release-notes" />

<Accordion title="Поля: примечания к выпуску">

| Дата | Отчет | Изменение |
| --- | --- | --- |
| 18.11.2020 | Событие<br /><br />Посещения сайта | Изменены названия и структура отчетов:<ul><li>**Посещения сайта** (Website visits) вместо «Точки взаимодействия на вебе» (Web touchpoints)</li><li>**События на сайте** (Website events) вместо «Веб-события» (Web events)</li></ul> |
| 04.10.2020 | Вовлечение по всем платформам | Добавлены поля:<ul><li>mobile\_campaign\_id</li><li>web\_campaign\_id</li></ul> |

</Accordion>

<div id="procedures" />

### Процедура

<div id="setting-up-pba-reports-in-data-locker" />

<Accordion title="Настройка отчетов PBA в Data Locker">

* Отчеты PBA записываются в Data Locker ежедневно в папку h=23 по событиям, произошедшим за данный день.
* Данные не могут быть записаны задним числом.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Чтобы включить отчеты PBA, администратор аккаунта должен настроить Data Locker:**

1. Перейдите в раздел **Интеграция** > **Data Locker**.
2. Выберите все отчеты в разделе «Атрибуция People-Based».
3. Нажмите **Сохранить конфигурацию**.

Как скачивать отчеты, читайте в разделе <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers">Доступ к отчетам Data Locker</Anchor>.

В **Data Locker** отчеты с сырыми данными PBA доступны в папке h=23.

Пример: t=website\_events/dt=2020-11-26/h=23

</Accordion>

<div id="combining-pba-and-mobile-data" />

<Accordion title="Объединение данных PBA и данных по мобильным устройствам">

Эти данные показывают, какие пользователи с наибольшей вероятностью будут взаимодействовать и с мобильным приложением, и с сайтом.

Объедините данные по мобильному приложению и сайту.

**Решение**:

* Объединение отчетов по <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid">идентификатору клиента</Anchor> (CUID)
  * Используйте один и тот же CUID для мобильных приложений и <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">веба</Anchor>, чтобы использовать его как ключ для объединения отчетов.
  * Затем объедините отчеты по полю CUID.
* PBA: идентификация пользователя на нескольких платформах:
  * PBA позволяет определить, что пользователь веба и мобильного приложения — один и тот же человек.
  * Если это так, то веб-отчеты с PBA содержат идентификатор мобильной рекламы: рекламный идентификатор Android, iOS IDFA, OAID или рекламный идентификатор Amazon.
  * Затем объедините мобильный и веб-отчеты по идентификатору мобильной рекламы.

<div id="use-cases-for-pba-and-mobile" />

#### **Примеры использования PBA и данных по мобильным устройствам**

Объедините данные по мобильному приложению и вебу, чтобы увидеть активность пользователя на различных платформах и устройствах. На их основе вы сможете:

* Проследить путь пользователя по цифровым ресурсам бренда.
* Проанализировать поведение пользователя на каждой платформе.
* Выяснить, на какой платформе вовлечение пользователей выше.
* Понять, на какой платформе происходит больше всего конверсий.
* Измерить эффективность своих усилий по переводу пользователей из веба в мобильное приложение.

</Accordion>

<div id="application-note-downloading-and-combining-data-locker-files" />

<Accordion title="Примечание по применению: скачивание и объединение файлов Data Locker">

Сырые данные PBA доступны в Data Locker. Данные по конкретному отчету находятся в папке h=23 для соответствующего типа отчетов и в виде нескольких сжатых файлов.

Используйте эту процедуру, чтобы:

* Скопировать файлы из Data Locker с помощью Cyber Duck или любого другого инструмента для копирования файлов S3.
* Соедините файлы в один файл CSV с помощью [Q.](http://harelba.github.io/q/)

**Копирование данных PBA из Data Locker**

**Прежде чем начать**:

* <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers#cyberduck">Установите и настройте Cyber Duck.</Anchor>

**Чтобы скопировать данные с помощью Cyber Duck:**

1. Откройте Cyberduck  
   Отобразится список доступных типов данных.

   <Image align="center" alt="Duck_us-en.jpg" src="https://files.readme.io/b8e93ad9423605b3247531d276b9c2d45abd4ea044dde29ee177f4d71b738e9d-360008254377.jpg" />
2. **Дважды щелкните** тип отчета PBA и выберите web\_events, web\_to\_app или web\_touch\_points.  
   На экране появится список дат, за которые доступны отчеты.
3. **Правой кнопкой мыши** щелкните нужную дату.
4. Выберите **Download to a specific location** (Скачать в определенное расположение) и укажите его.  
    Начнется скачивание файлов.
5. Повторите предыдущие шаги, чтобы копировать данные из отчетов других типов. Данные по каждому типу отчета и дате должны храниться в отдельных папках на вашем компьютере.

**Создание объединенного файла CSV:**

**Прежде чем начать:**

Установите <Anchor target="_blank" href="http://harelba.github.io/q/">Q</Anchor> на свой компьютер.

**Чтобы объединить данные в файл CSV с помощью Q**:

1. Используя командную строку / терминал Mac, перейдите в каталог с данными.
2. Используйте следующую команду, чтобы объединить сжатые файлы в один файл с именем pbadata.csv.  
   Примечание. Символом «~» обозначается путь/домашняя папка, в которой на вашем компьютере выполнится команда Q. Для вызова команды иногда требуется указать полный путь.

   ```
   ~q "SELECT * from part*.gz" -d , -H -z -O >pbadata.csv
   ```
3. Откройте файл с помощью Excel или другого инструмента.

</Accordion>

<div data-zendesk-anchors="pba-raw-data-reports=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D1%81-%D1%81%D1%8B%D1%80%D1%8B%D0%BC%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-pba h_01HKW341NVTCP4FY5G4TC94MZY=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-%D1%81-%D1%81%D1%8B%D1%80%D1%8B%D0%BC%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8-pba report-descriptions=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 h_01HKW341NVC83ZC3HCH86QBJYG=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 rawdata-report-fields=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0-%D1%81-%D1%81%D1%8B%D1%80%D1%8B%D0%BC%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8 h_01HKW341NVNYM1AGFC8GHV7VR2=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0-%D1%81-%D1%81%D1%8B%D1%80%D1%8B%D0%BC%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC%D0%B8 h_01EQD0FBKE0J71MA9MNETEZAMA=website-visits-and-website-events sample-reports=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 h_01HKW341NVX51NQFAA79BD7MF3=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2 website-visits-events=%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA-%D0%BF%D0%BE%D0%BB%D0%B5%D0%B9-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-%D0%BF%D0%BE%D1%81%D0%B5%D1%89%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%B0%D0%B9%D1%82%D0%B0-%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BD%D0%B0-%D1%81%D0%B0%D0%B9%D1%82%D0%B5 field-list-website-visits-and-website-events-report=%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA-%D0%BF%D0%BE%D0%BB%D0%B5%D0%B9-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-%D0%BF%D0%BE%D1%81%D0%B5%D1%89%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%B0%D0%B9%D1%82%D0%B0-%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BD%D0%B0-%D1%81%D0%B0%D0%B9%D1%82%D0%B5 h_01J53BGNDSQCCFV1VQA8EV50GR=%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA-%D0%BF%D0%BE%D0%BB%D0%B5%D0%B9-%D0%B2-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%B0%D1%85-%D0%BF%D0%BE%D1%81%D0%B5%D1%89%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D0%B0%D0%B9%D1%82%D0%B0-%D0%B8-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BD%D0%B0-%D1%81%D0%B0%D0%B9%D1%82%D0%B5 h_01HKW341NW43C07KYAN3WCV0WY=field-release-notes procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0 h_01HKW341NWXQ19ZB5QXZK84VMQ=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0 h_01HKW341NXR3MP2T99AAHNH3SG=setting-up-pba-reports-in-data-locker h_01HKW341NX2S093V1Y8YVY45VP=combining-pba-and-mobile-data use-cases-for-pba-and-mobile=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-pba-%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE-%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D0%BC-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0%D0%BC h_01HKW341NXTXX4FJ2ZZQFZ2V85=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-pba-%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE-%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D0%BC-%D1%83%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%B0%D0%BC h_01HKW341NX95YBGHZZG8KZC3KX=application-note-downloading-and-combining-data-locker-files" />

---
title: Политика идентификаторов пользователей в аудиториях
metadata:
  keywords:
    - IDFA
    - Audiences
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-12-23T15:39:55Z'
  edited_at: '2026-08-19T00:35:43Z'
  id: 360016791118
  locale: ru
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ru/articles/360016791118
---
> **Краткий обзор:** Настройте политику идентификаторов пользователей, чтобы иметь контроль на **уровне аккаунта** над данными, которыми аудитории делится с партнерами.

## О проекте

После того как вы определили аудиторию, AppsFlyer аудитории отправляет идентификаторы членов этой аудитории выбранным вами <Anchor target="_blank" href="/marketers/ru/docs/audiences-partner-connections">рекламным партнерам</Anchor>. Это позволяет им показывать вашу рекламу только этим пользователям.

Для обеспечения соблюдения требований конфиденциальности iOS 14.5 и других аспектов конфиденциальности пользователей, аудитории предоставляют вам полный контроль над определением того, какие идентификаторы будут предоставлены партнерам:

* на уровне аккаунта
* на уровне партнерского подключения

Эта статья объясняет процесс управления политикой идентификаторов пользователей на уровне аккаунта. Для получения дополнительной информации об управлении идентификаторами на уровне партнерского подключения, см. раздел <Anchor target="_blank" href="/marketers/ru/docs/audiences-guide#manage-connections">Управление подключениями</Anchor> руководства по аудиториям.

## Идентификаторы пользователей

В этом разделе описываются идентификаторы, которыми можно делиться с партнерами.

<div id="shared-identifiers" />

<Accordion title="Настройки идентификаторов по умолчанию">

По умолчанию аудитории предоставляют партнерам следующие идентификаторы:

* **iOS:** IDFA (на iOS 14.5 и выше, доступно только если пользователь разрешает использование этого идентификатора)
* Android: GAID

Вы также можете настроить аудитории так, чтобы отправлять следующие идентификаторы партнерам, которые их поддерживают:

* Электронная почта, электронное сообщение (хэшированная)
* Номер телефона (хешированный)
* OAID и IMEI (оба актуальны только для магазинов Android, отличных от Google Play)

Некоторые другие дополнительные идентификаторы могут быть полезны для ваших внутренних процессов (например, CRM или аналитика):

* CUID
* IDFV (актуально только для iOS)

Для получения дополнительной информации (включая требования к использованию определенных идентификаторов в AppsFlyer), см. таблицу идентификаторов ниже.

</Accordion>

<div id="identifiers-table" />

<Accordion title="Таблица идентификаторов">

<table><thead><tr><th>Идентификатор</th><th>ОС</th><th>Делиться по умолчанию?</th><th>Требования к использованию\/<br/>Примечания<br/><br/> </th></tr></thead><tbody><tr><td>IDFA</td><td>https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png</td><td>См. примечание<br/>(справа)</td><td>По умолчанию делится только для пользователей со <a href="./audiences-user-identifier-policy#правила-конфиденциальности">статусом ATT: авторизован или не определен</a> </td></tr><tr><td>ГАИД</td><td>Android;</td><td>Д</td><td>Ничего</td></tr><tr><td>OAID</td><td>Android<br/>(не Google Play)</td><td>Н</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">Необходимо настроить</a> в SDK (пакет средств разработки ПО) AppsFlyer</td></tr><tr><td>imei</td><td>Android<br/>(не Google Play)</td><td>Н</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">Необходимо настроить</a> в SDK (пакет средств разработки ПО) AppsFlyer</td></tr><tr><td>CUID</td><td>iOS<br/>Android</td><td>Н</td><td><ul><li>Генерируется рекламодателем и  <a href="./customer-user-id-field-cuid" target="_blank">передается в AppsFlyer</a>  с помощью API или SDK AppsFlyer.</li><li>Не передается рекламным партнерам, но может быть полезен для ваших внутренних нужд.</li><li>Регулируется  <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Условиями использования дополнительных идентификаторов</a> . </li></ul></td></tr><tr><td>IDFV</td><td>https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png</td><td>Н</td><td><ul><li>Не передается рекламным партнерам, но может быть полезен для ваших внутренних нужд.</li><li>Регулируется  <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Условиями использования дополнительных идентификаторов</a> . </li></ul></td></tr><tr><td>Электронная почта (хешированная)</td><td>iOS<br/>Android</td><td>Н</td><td rowspan="2"><ul><li> <a href="./audiences-configure-additional-identifiers-for-partner-audience-creation" target="_blank">Должна быть настроена</a> через <span> AppsFlyer SDK или S2S-mobile API</span>.</li><li>Должна быть зашифрована с использованием хеширования SHA256.</li><li>Регулируется  <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Условиями использования дополнительных идентификаторов</a> . </li></ul></td></tr><tr><td>Номер телефона (хэшированный)</td><td>iOS<br/>Android</td><td>Н</td></tr></tbody></table>

</Accordion>

## Настройка политики идентификаторов пользователей на уровне учётной записи

Политику идентификаторов пользователей может установить только администратор.

**Чтобы установить или изменить политику, выполните следующие шаги:**

1. В AppsFlyer в боковом меню выберите **Вовлеченность** > **Аудитории**.
2. Нажмите на значок настроек (шестерёнка) в верхнем правом углу.
3. В окне **Политика идентификаторов пользователей** выберите настройки, соответствующие политике конфиденциальности вашей организации.
   * Некоторые рекламные партнёры также поддерживают следующие идентификаторы:
   * Если вы решите запретить передачу идентификаторов, загруженных существующими партнёрскими соединениями, вам будет предложено подтвердить ваше желание прекратить их загрузку.
4. Нажмите **Сохранить.**

## Правила конфиденциальности

Этот раздел описывает правила конфиденциальности, влияющие на то, как могут быть переданы идентификаторы пользователей.

<Accordion title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

Начиная с версии 14.5, iOS требует, чтобы каждое приложение предлагало пользователю возможность разрешить или запретить передачу идентификатора устройства IDFA в рекламных целях (прозрачность отслеживания приложения). То, увидел ли пользователь это предложение (диалог согласия ATT) и ответил на него, определяет его <Anchor target="_blank" href="/marketers/ru/docs/att-implications-ios-14-and-deprecation-of-lat">статус ATT</Anchor>.

Параметры политики аудитории для обмена идентификаторами в iOS основаны на последнем статусе ATT пользователя. Ваши варианты обмена следующие:

| Вариант политики пользователя | Соответствующий статус ATT |
| --- | --- |
| Никогда не загружать | Этот идентификатор не загружается партнерам |
| Статус ATT: только авторизовано | Идентификатор загружается, если последний статус ATT — **authorized** или **af\_authorized** |
| Статус ATT: авторизовано или не определено | Идентификатор загружается, если последний статус ATT — **authorized**, **af\_authorized**, **not\_determined** или **af\_unavailable***Опция по умолчанию для IDFA, начиная с релиза iOS 14.5 от Apple* |
| Всегда загружать | Идентификатор загружается независимо от статуса ATT. Обеспечьте соблюдение правовых норм условий использования вашего приложения.  <br />  <br />*Опция недоступна для IDFA* |

**Примечание:** аудитории рассматривает статус ATT нового пользователя как **не определено**, пока они не увидят и не ответят на диалоговое окно согласия ATT.

Для подробных определений статуса ATT, см.:

* <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">Определения статуса Apple ATT</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/att-implications-ios-14-and-deprecation-of-lat#значения-att">Определения статуса AppsFlyer ATT</Anchor> (af\_authorized, af\_unavailable)

Кроме того, все пользователи из Европейской экономической зоны (ЕЭЗ) подпадают под исполнение положений [Закона о цифровых рынках (DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act) компанией Google.

</Accordion>

<div id="android" />

<Accordion title="Android;">

Пользователи Android из Европейской экономической зоны (ЕЭЗ) подпадают под действие положений [Закона о цифровых рынках (DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act) принимаемых компанией Google.

</Accordion>

<div id="eu-digital-markets-act" />

<Accordion title="Закон ЕС о цифровых рынках">

В рамках исполнения Закона о цифровых рынках (DMA) 6 марта 2024 года Google обновляет свою политику согласия пользователей из ЕС. Будучи Партнером Google по Атрибуции приложений, AppsFlyer вносит необходимые изменения для поддержка требований своей политики, обеспечивая рекламодателям максимальную ценность, значение от их маркетинговых каналов Google Ads. <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">Узнать больше</Anchor>

**Вот как изменения повлияют на аудитории:**

* **Новый SDK AppsFlyer**  
  Последняя версия AppsFlyer SDK будет собирать согласие пользователей от владельцев приложений для <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">Европейской экономической зоны (ЕЭЗ)</Anchor>, чтобы их данные могли передаваться в Google. Для аудиторий, созданных в AppsFlyer (например, пользовательских и предлагаемых аудиторий), информация о согласии, собранная из SDK, будет автоматически передана в аудитории, а затем в Google. После обновления до новой версии SDK (пакет средств разработки ПО) этот процесс будет происходить автоматически.
* **Аудитории, связанные с Google**
  * **Согласие предоставлено** — AppsFlyer отправит устройства пользователей ЕЭЗ, которые согласились на передачу своей информации в Google.
  * **В согласии отказано** — AppsFlyer не будет отправлять устройства пользователей ЕЭЗ, которые отказались предоставить Google согласие на передачу своей информации.
  * **Согласие неизвестно** — AppsFlyer отправит устройства пользователей ЕЭЗ, которые не предоставили или не отклонили свое согласие, как «Не указано». Google, скорее всего, не примет их для включения в свою аудиторию.  

    Дополнительную информацию смотрите в <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">FAQ</Anchor> Google.
* **Существующие аудитории**  
  Все устройства, которые уже были частью аудитории в Google до 6 марта 2024 года, останутся в аудитории и не будут затронуты. Только новые аудитории или новые устройства из ЕЭЗ, добавленные к существующей аудитории, будут передаваться в Google с согласием.
* **Размер загружаемой аудитории**  
  Оценочный и фактический размер загружаемых аудиторий может изменяться в зависимости от количества пользователей, предоставляющих или отклоняющих согласие.
* #### **Импорт аудиторий**

  * **Импорт стандартной аудитории** — AppsFlyer добавит данные о согласии, собранные из SDK AppsFlyer, и удалит несогласованные или неуказанные устройства из аудитории перед отправкой её в Google.
  * **Импорт аудитории «как есть»** — При импорте аудитории «как есть» через <Anchor target="_blank" href="/marketers/ru/docs/audiences-import-audience-segments-from-internal-systems#import-a-csv-file">CSV</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/audiences-import-audience-segments-from-internal-systems#use-the-import-audience-api">API</Anchor> потребуется добавить два дополнительных поля согласия. Эти поля:

| Поле AppsFlyer (1) | Поле Google (2) | ценности, значения | Объяснение поля |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true\/false | Пользователь дал согласие Google на использование своих данных для персонализированной рекламы? |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true\/false | Пользователь дал согласие на отправку своих данных в Google? |

Если поля согласия не заполнены значениями, они будут отправлены в Google как «Не указано».

> 📘 **Примечание**
>
> Реализация компанией Google Закона о цифровых рынках (DMA) распространяется как на платформы Android, так и на iOS.

</Accordion>

<div data-zendesk-anchors="background=%D0%BE-%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B5 h_01HKA2FS9VBCSV8FP8FH79H4R0=%D0%BE-%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B5 user-identifiers=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01HKA2FS9VSVJD54R14GC7G0P4=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9 h_01HNZH99Z8NA9607VHSYH5XVW0=shared-identifiers h_01HKA2FS9V1KBK9BJAJ63FP6CV=identifiers-table setting-accountlevel-user-identifier-policy=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%BE%D0%B2-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%BD%D0%B0-%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D0%B5-%D1%83%D1%87%D1%91%D1%82%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D0%B8 h_01HKA2FS9WNGGRP3NX5NKV15SK=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D0%BE%D0%BB%D0%B8%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%BE%D0%B2-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%BD%D0%B0-%D1%83%D1%80%D0%BE%D0%B2%D0%BD%D0%B5-%D1%83%D1%87%D1%91%D1%82%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D0%B8 user-identifier-policy-options=%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HKA2FS9W5NSKKRK2VCZARG15=%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 ios=%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HNZJ1ET6F87AHHVQK17QHZDD=%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HNZJ1ET67JQQCPYSM3H6Y9VW=android h_01HNZN8MWETDCMGWKJ0MMM8JK4=eu-digital-markets-act importing-audiences=%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82-%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B9 h_01HPGV1GYT8DW0GYWTC031TNVH=%D0%B8%D0%BC%D0%BF%D0%BE%D1%80%D1%82-%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D0%B9 h_01HNZEAJT00KKEBDPR7FD0TJNR=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5" />

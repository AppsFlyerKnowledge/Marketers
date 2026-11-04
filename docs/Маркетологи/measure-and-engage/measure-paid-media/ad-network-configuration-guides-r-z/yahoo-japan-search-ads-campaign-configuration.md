---
title: Конфигурация кампании Yahoo Japan Search Ads
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-12-02T10:07:00Z'
  edited_at: '2026-09-17T00:25:24Z'
  id: 4412602890641
  locale: ru
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ru/articles/4412602890641
---
> **Кратко:** Yahoo Japan Search Ads — партнер по сети с самоотчетностью (SRN), который сочетает рекламу и аналитику.
>
> * 15 декабря 2021 года прежняя интеграция с Yahoo Japan Search Ads, *yahoojapansearch\_int,* была заменена новой интеграцией, *yjsearch\_int*. Узнайте, как [начать работать с новым API](/docs/yahoo-japan-search-ads-campaign-configuration#integrating-with-the-new-api).

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yjsearch.png" width="121px" />

<div id="yahoo-japan-search-ads-integration-principles" />

## Принципы интеграции Yahoo Japan Search Ads

Интеграция AppsFlyer с Yahoo Japan Search Ads актуальна только для Android-приложений. 

Интеграция использует идентификатор ссылки для измерения конверсий и основана на предварительно заданных событиях конверсии в Yahoo Japan Search Ads. Вы можете сопоставить события в приложении, такие как подписки и покупки, с этими событиями. Это позволяет измерять конверсии и обеспечивать отчетность между AppsFlyer и Yahoo Japan Search Ads.

<div id="comparing-the-legacy-and-new-integration" />

<Accordion title="Сравнение прежней и новой интеграции">

Поддержка функций API Yahoo Japan Search Ads:

| Особенность | Прежняя (yahoojapansearch\_int) | Новый<br /><br />(yjsearch\_int) |
| --- | --- | --- |
| Конверсия установки (только после клика) | Да | Да |
| Конверсия в приложении | Ни один | Да |

</Accordion>

<div id="integrating-with-the-new-api" />

<Accordion title="Интеграция с новым API">

**Чтобы включить интеграцию с новым API:**

1. В дэшборде Yahoo Japan Search Ads <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">сгенерируйте идентификатор ссылки</Anchor>. Необходимо выбрать AppsFlyer в качестве MMP.
2. В AppsFlyer [настройте интеграцию с Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).
3. [Сопоставьте события в приложении](/docs/yahoo-japan-search-ads-campaign-configuration#2), которые вы хотите измерять, и <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">создайте новую аналитику конверсий в Campaign Management Tool</Anchor> в Yahoo Japan Search Ads.

</Accordion>

<div id="data-sharing-between-appsflyer-and-yahoo-japan-search-ads" />

<Accordion title="Обмен данными между AppsFlyer и Yahoo Japan Search Ads">

Отправляйте постбэки в Yahoo Japan Search Ads, связанные с конверсиями и событиями в приложении. События в приложении сопоставляются с предопределенными событиями конверсии, которые Yahoo Japan Search Ads использует для оптимизации и обновления отчетов об эффективности. Сопоставление выполняется в настройках интеграции.

См. следующую таблицу сопоставления для событий в приложении AppsFlyer (вашего приложения) и предопределенного сопоставления событий Yahoo Japan Search Ads.

| AppsFlyer in-app событие | Тип события в приложении Yahoo Japan Search Ads |
| --- | --- |
| af\_purchase | in\_app\_purchase |
| af\_app\_opened | session\_start |
| af\_search | просмотр\_результатов\_поиска |
| af\_content\_view | view\_item |
| af\_list\_view | view\_item\_list |
| af\_add\_to\_cart | добавить в корзину |
| af\_travel\_booking | ecommerce\_purchase |
| Любое событие в приложении | Если у вас есть дополнительные события, сопоставьте их с настраиваемым событием. |

**Данные, предоставляемые AppsFlyer сервисом Yahoo Japan Search Ads**

Когда Yahoo Japan Search Ads регистрирует конверсию, сервис передает нам параметры медиаисточника, указанные в таблице. Эти параметры используются для заполнения аналитических отчетов и отчетов по необработанным данным. В следующей таблице приведено сопоставление параметров Yahoo Japan Search Ads и AppsFlyer.

<div id="yahoo-japan-search-ads-appsflyer-media-source-mapping" />

#### Сопоставление медиаисточников Yahoo Japan Search Ads и AppsFlyer

| Поисковая реклама Yahoo! Япония | AppsFlyer: |
| --- | --- |
| временная метка | attributed\_touch\_time |
| campaign\_tracking\_id | campaign\_id (идентификатор кампании) |
| ad\_group\_tracking\_id | adset\_id (идентификатор группы объявлений) |
| ad\_tracking\_id | ad\_id (идентификатор объявления) |
| keyword | keywords (ключевые слова) |
| Местоположение устройства | keyword\_match\_type |
| account\_id | network\_account\_id |

</Accordion>

<div id="integration-procedures" />

## Процедуры интеграции

Вы можете интегрироваться с Yahoo Japan Search Ads как с одной сущностью: напрямую как рекламодатель или через агентство.  
Заполните разделы следующим образом:

* [Заполняется один раз — обязательно] [Интеграция рекламодателя с Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).
* [Необязательно для каждого агентства] [Интеграция агентства](/docs/yahoo-japan-search-ads-campaign-configuration#agency-integration).

<div id="yahoo-japan-search-ads-integration-tab-sections" />

<Accordion title="Разделы вкладки интеграции Yahoo Japan Search Ads">

<Table>
  <thead>
    <tr>
      <th>
        Step
      </th>
      <th>
        Раздел
      </th>
      <th>
        Description(Описание)
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="1"></span>
        1
      </td>
      <td>
        Активация партнера
      </td>
      <td>
        **Необходимые условия:**

        Получите <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">сID сылки</Anchor> Yahoo Japan Search Ads.

        **Чтобы активировать интеграцию атрибуции приложения Yahoo Japan Search Ads:**

        1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Маркетплейс партнеров**.
        2. Найдите **Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - Новый API**, и выберите его.
        3. Убедитесь, что в URL-адресе отображается **yjsearch\_int** . Если это не так, вы выбрали неправильного интегрированного партнера.
        4. На вкладке **Интеграция** включите **Активировать партнёра**.  
           **Примечание:** Переключатель должен быть включен <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">(активирован)</Anchor> на протяжении всего времени, пока вы работаете с партнером.
        5. В поле Link ID вставьте идентификатор ID ссылки, указанный в предварительных требованиях.
        6. [Необязательно] Изменения настроек по умолчанию для окна ретроспективы по клику для установки <Anchor target="_blank" href="/marketers/ru/docs/set-up-lookback-windows">click-through lookback</Anchor> window. По умолчанию в Yahoo Japan Search Ads установлено 7 дней. Чтобы свести к минимуму расхождения [практические рекомендации], ориентируйтесь на значение по умолчанию в Yahoo Japan Search Ads.
        7. Нажмите **Сохранить интеграцию**.
        8. В **Yahoo Japan Search Ads** задайте для новых настроек конверсии значение "app\_first\_open". Узнать больше о настройке в Yahoo Japan Search Ads.
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        Сопоставьте события в приложении AppsFlyer с событиями Yahoo Japan Search Ads
      </td>
      <td>
        **Чтобы сопоставить предопределенные события Yahoo Japan Search Ads с событиями в приложении AppsFlyer:**

        1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Активные интеграции**.
        2. Выберите **Yahoo! Найдите Ads (Yahoo! JAPAN Sponsored Search) - Новый API**.
        3. Активируйте **постбэки внутренних событий приложений**.
        4. Чтобы добавить в список событие приложения, нажмите **Add event**.
        5. Заполните необходимые параметры.
        6. Нажмите **Сохранить интеграцию**.
        7. В **Yahoo Japan Search Ads** задайте новые настройки конверсии в соответствии с настроенными событиями в приложении. Узнать больше о настройке в Yahoo Japan Search Ads.

        | Название параметра | Description(Описание) |
        | --- | --- |
        | <span id="sdk-event-name"></span>Имя события в SDK | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверных событий. |
        | <span id="partner-event-identifier"></span>Идентификатор события партнера | Предопределенные события Yahoo Japan Search Ads. Рекомендуемые стандартные конфигурации сопоставления перечислены в таблице в предыдущем разделе. |
        | <span id="sending-option"></span>Sending option (Вариант отправки) | Выберите вариант отправки для события:<br /><br />* **Только этот партнер:** для событий, поступающих только от пользователей, атрибутированных Yahoo Japan Search Ads.<br />* **Все медиаисточники, включая органические:** вся ваша пользовательская база будет доступна для передачи в отчетность Yahoo Japan Search Ads. |
        | <span id="send-revenue"></span>Отправить доход | * **Нет значений & нет дохода:** отправляет только само событие без значения.<br />* **Значения & нет дохода:** отправляет все параметры, кроме значения дохода.<br />* **Значения & доход**: отправляет все параметры события, включая значение дохода (если оно есть в событии). |

        Примечания:

        * Названия событий чувствительны к регистру. Чтобы избежать расхождений, убедитесь, что вы используете корректное название события для всех медиа-источников и версий приложения.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="agency-integration" />

<Accordion title="Интеграция агентства">

Агентства могут запускать кампании в Yahoo Japan Search Ads от вашего имени.

<div id="agency-setup" />

#### Настройка агентства

| Процедура для выполнения | Процедура |
| --- | --- |
| Рекламодатели | <ol><li>Убедитесь, что вы завершили [интеграцию рекламодателя Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).</li><li>В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции** > **Активные интеграции**.</li><li>Выберите агентство.</li><li>Перейдите на вкладку **Разрешения** и включите **разрешения агентства**.</li></ol> |
| Доступно с Android SDK версии 4.8.5 | <ol><li>В AppsFlyer перейдите в **Сотрудничество** > **Партнерские интеграции** > **Активные интеграции**.</li><li>Выберите **Yahoo! Найдите Ads (Yahoo! JAPAN Sponsored Search) - Новый API**.</li><li>Перейдите на вкладку **Интеграция**.</li><li>Убедитесь, что переключатель **Активировать партнера** **включен.** Если это не так, рекламодатель должен выполнить [интеграцию Yahoo Japan Search Ads для рекламодателей](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).</li><li>Проверьте правильность остальных настроек, таких как окна атрибуции и сопоставление событий в приложении. При необходимости попросите рекламодателя внести изменения.</li><li>Введите **идентификатор клиента Yahoo Japan Search Ads**. Идентификатор доступен в <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=36745&o=default#:~:text=How%20to%20check%20Account%20ID">инструменте управления кампаниями</Anchor>. Обратите внимание: можно подключить только один идентификатор клиента.</li><li>Нажмите **Save** (Сохранить).</li></ol> |

</Accordion>

<div id="subsidiary-procedures" />

## Дополнительные процедуры

<div id="get-the-app-link-id" />

<Accordion title="Получите идентификатор ссылки приложения">

**Чтобы получить идентификатор ссылки Campaign Manager,** <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">см. документацию Yahoo Japan Search Ads.</Anchor>

</Accordion>

<div id="create-a-new-yahoo-japan-search-ads-predefined-event" />

<Accordion title="Создайте новое предопределенное событие Yahoo Japan Search Ads">

**Чтобы создать новое предопределенное событие,** см. <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">инструкции Yahoo Japan Search Ads</Anchor>.

</Accordion>

<div id="yahoo-japan-search-ads-discrepancies" />

<Accordion title="Расхождения в Yahoo Japan Search Ads">

См. таблицу ниже, чтобы узнать о расхождениях и способах их минимизации.

**Различия в моделях атрибуции**

| Причина | Description(Описание) | Совет AppsFlyer |
| --- | --- | --- |
| Неправильное сопоставление событий в приложении | Сопоставление между AppsFlyer и Yahoo Japan Search Ads выполнено неправильно. | <ul><li>Проверьте идентификатор ссылки,</li><li>Убедитесь, что события в приложении AppsFlyer правильно сопоставлены с событиями Yahoo Japan Search Ads.</li></ul> |

</Accordion>

<div data-zendesk-anchors="yahoo-japan-search-ads-integration-principles=%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-yahoo-japan-search-ads h_01HH1RS8ZJSWTCDY5QBN3E041D=%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-yahoo-japan-search-ads h_01HH1RS8ZJATXC84X8C74B95C8=comparing-the-legacy-and-new-integration h_01HH1RS8ZJWESR21H0BE7S3HV5=integrating-with-the-new-api h_01HH1RS8ZJM3EHGMKJF409QPTX=data-sharing-between-appsflyer-and-yahoo-japan-search-ads yahoo-japan-search-adsappsflyer-media-source-mapping=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%BE%D0%B2-yahoo-japan-search-ads-%D0%B8-appsflyer h_01HH1RS8ZM0ZEPJ7ZJYY286J2F=%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%BE%D0%B2-yahoo-japan-search-ads-%D0%B8-appsflyer integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01HH1RS8ZMAFNAGWAZDWX5PJT4=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 yahoo-japan-search-ads%E2%80%94integration-tab-sections=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMS287YR3K9CW7HN37=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMGTJQB3ANAJB8MY52=agency-integration agency-setup=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0 h_01HH1RS8ZMCBT0NJ5Z23ZAK6TV=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0 subsidiary-procedures=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B h_01HH1RS8ZMKHBA000CEX6KHQJK=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B h_01HH1RS8ZMWPS69ASK452QAXAK=get-the-app-link-id h_01HH1RS8ZMXVXH745DP5Q8SZ3D=create-a-new-yahoo-japan-search-ads-predefined-event h_01HH1RS8ZM5SXTQDPJ5E9YEKPS=yahoo-japan-search-ads-discrepancies" />

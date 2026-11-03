---
title: Отчеты SKAN по сырым данным
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2026-08-19T00:31:21Z'
  id: 360014261518
  locale: ru
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ru/articles/360014261518
---
> **Краткий обзор.** Отчеты SKAN по сырым данным содержат данные, созданные после преобразования и декодирования постбэков, полученных AppsFlyer от iOS, а также сырые постбэки SKAN. Данные доступны через <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers">Data Locker</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/push-api-streaming-raw-data">Push API</Anchor>. Если ваш план подписки включает сырые данные, подписка на Data Locker не требуется.

## Отчеты SKAN по сырым данным

Принципы:

* **Данные предоставляет:**
  * **Отчет Data Locker**
    * **Примечание**! Доступно для аккаунтов, имеющих подписку на сырые данные. Т. е. подписка на Data Locker не требуется. Если в настоящее время вы не используете Data Locker, пользователь с правами администратора должен настроить Data Locker и включить отчеты SKAN. Для этого перейдите в раздел **Интеграция** > **Data Locker**. Выберите отчеты SKAN.
    * **Обновление данных**: ежедневно. Данные содержатся в папке h=23 за дату получения постбэка в AppsFlyer.
  * **push**
    * Обновление данных: См. <Anchor target="_blank" href="/marketers/ru/docs/push-api-streaming-raw-data">Push API для данных SKAN</Anchor>.
* **Дата установки**: Вычисляется по времени прибытия постбэка в AppsFlyer следующим образом:
  * Если для постбэков используется SKAN V4, формула даты установки такая: Дата установки = время прибытия постбэка - [аккумулированная длина окна] - [средняя задержка постбэка].
    * Постбэк 1: дата установки = время прибытия постбэка - 48ч. - 36ч.
    * Постбэк 2: дата установки = время прибытия постбэка - 168ч. - 84ч.
    * Постбэк 3: дата установки = время прибытия постбэка - 840ч. - 84ч.
  * Если для постбэков используется SKAN V3, формула даты установки такая: Дата установки = время прибытия постбэка - 36ч. - [средний диапазон последней активности]. 
    * По умолчанию [средний диапазон последней активности] составляет 12 часов.
    * Если значение конверсии равно 0, средний диапазон последней активности устанавливается равным 0.
  * Google самостоятельно оценивает время установки, а AppsFlyer использует это время. **Примечание**. Сообщение Google об установках может занять до 13 дней. <Anchor target="_blank" href="/marketers/ru/docs/get-skan-postback-data-from-google-ads#получение-данных-постбэков-skan-из-google-ads">Узнать больше</Anchor>

Доступные типы отчетов:

* **Постбэк устройства**: 1 постбэк от устройства на каждую установку или повторную загрузку, полученную на устройстве iOS.
* **Сырые данные SKAN**:
  * AppsFlyer декодирует и переводит постбэк устройства в записи сырых данных.
  * При каждом постбэке создается запись об установке или повторной загрузке и записи о событиях в приложении.
  * Количество записей о событиях в приложении зависит от значения конверсии (CV) следующим образом:
    * CV = 0, пусто или null: Записи о событиях в приложении не создаются.
    * Диапазон CV:
      * 1-63: Для SKAN 3 и SKAN 4 окно 1 точное значение, это количество записей о событиях в приложении, в зависимости от ваших настроек измерения.
      * Низкий, средний или высокий: Для приблизительных значений SKAN 4 это количество записей о событиях в приложении, в зависимости от настроек измерения.

**Почему некоторые поля пустые?** Это происходит по любой из следующих причин:

* Необязательные поля обогащения, такие как campaign\_name, ad\_network\_campaign\_id, ip, которые рекламная сеть не предоставила.
* Apple скрывает эти данные из-за политики пороговых значений Apple. Такие поля, как source\_app\_id, skad\_campaign\_id, skad\_conversion\_value.

## Формат и содержание отчетов SKAN по сырым данным

<div id="raw-data-report-types" />

<Accordion title="Типы отчетов по сырым данным">

<Table>
  <thead>
    <tr>
      <th>
        Тип отчета
      </th>
      <th>
        Название отчета
      </th>
      <th>
        Описание
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="postback"></span>
        постбэк
      </td>
      <td>
        Постбэки
      </td>
      <td>
        Постбэки, отправленные iOS в рекламную сеть. После обогащения данных рекламной сетью постбэк направляется в AppsFlyer. [Скачать пример постбэков](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv) (CSV).

        Примечание: при did\_win=false постбэки не отправляются.

        **Название темы в Data Locker**: skad\_postbacks
      </td>
    </tr>
    <tr>
      <td><span id="postback::315d5a62"></span>
        постбэк
      </td>
      <td>
        Копия постбэков (напрямую от Apple)
      </td>
      <td>
        Постбэки, отправленные iOS непосредственно в AppsFlyer.

        Доступны начиная с iOS 15+ и требуют от рекламодателя настройки приложения, чтобы <Anchor target="_blank" href="/marketers/ru/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">отправлять постбэки от основной сети</Anchor> (т.е. о конверсии) в AppsFlyer. [Скачать пример копии постбэков](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv) (CSV).

        Примечание: Эта тема содержит постбэки только от основной сети (принесшей конверсию).

        **Название темы в Data Locker**: skad\_postbacks\_copy
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event"></span>
        Декодированное событие
      </td>
      <td>
        Установки
      </td>
      <td>
        **Первые установки приложений**

        SKAN сообщает *redownload=false*. Это означает, что пользователь, представленный через Apple ID, загрузил приложение впервые.  
        [Скачать пример установок](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv) (CSV).

        **Название темы в Data Locker**: skad\_installs
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5c7e459f"></span>
        Декодированное событие
      </td>
      <td>
        повторные загрузки
      </td>
      <td>
        **Установки приложений, которые не являются первыми установками**

        SKAN сообщает *redownload=true*. Это означает, что пользователь, представленный через Apple ID, загрузил приложение не первый раз.  
         Этот отчет имеет такую же структуру, как и отчет по установкам.

        **Название темы в Data Locker**: skad\_redownloads
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::b8f2b4a4"></span>
        Декодированное событие
      </td>
      <td>
        Внутренние события приложений
      </td>
      <td>
        **Внутренние события приложений**

        Начиная с 21 июля 2021 года вносятся изменения в порядок предоставления сырых данных о событиях в приложении, как указано в таблицах.

        Количество записей о событиях в приложении зависит от настроек измерения.

        [Скачать пример событий в приложении](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv) (CSV).

        **Название темы в Data Locker**: skad\_inapps

        Действует для постбэков iOS, полученных начиная с 21 июля 2021 года:

        | Тип измерения | Описание |
        | --- | --- |
        | Вовлечение | * Доход от данного пользователя. Если доход > 0, запись содержит поля skad\_revenue и event\_name.<br />* Поля min\_revenue и max\_revenue заполняются вашими пользовательскими значениями диапазона конверсии. |
        | Конверсия в приложении и события воронки | * Запись для каждого выполненного уникального события конверсии. Поле event\_name заполняется соответствующим образом. Если никаких событий не происходит, запись не производится.<br />* События конверсии имеют min\_event\_counter = 0 и max\_event\_counter = 1. |
        | Взаимодействие с приложением | Чтобы определить, сколько раз пользователь выполнил то или иное событие в приложении, используйте формулу`[округление (min_event_counter + max_event_counter) / 2]` |

        Действует для постбэков iOS, полученных до 20 июля 2021 года:

        | Тип измерения | Количество записей | Описание |
        | --- | --- | --- |
        | Вовлечение | 0-1 | Если доход > 0, запись содержит поля skad\_revenue и event\_name. |
        | Конверсии | 0-6 | Запись для каждого выполненного уникального события конверсии. Поле event\_name заполняется соответствующим образом. Если никаких событий не происходит, запись не производится. |
        | Вовлеченность | 0-63 | Количество записей представляет собой количество раз, когда пользователь выполнял событие вовлечения. Если пользователь не вовлекался, записи отсутствуют. |
        | Специфика | 0-без ограничений | В соответствии с вашей пользовательской схемой конверсии. |
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5dac9cbb"></span>
        Декодированное событие
      </td>
      <td>
        Параметры рекламы SRN
      </td>
      <td>
        * Отчет содержит события Meta Ads с детализацией до кампаний, групп объявлений и отдельных объявлений. Каждая строка отчета может быть как событием установки, так и событием в приложении.
        * Детализация на уровне групп объявлений и отдельных объявлений не включена в постбэки SKAN из Meta Ads. Эти данные уникальны для данного отчета и не отображаются на дэшборде SKAN, в API эффективности и других отчетах SKAN Data Locker.
        * Отчет без схемы. Параметры Data Locker по выбору полей не применяются.
        * Рекомендация: Не объединяйте и не сравнивайте данные из этого отчета с другими отчетами SKAN, поскольку между этим отчетом, который использует данные, декодированные SRN, и другими отчетами, которые используют данные, декодированные AppsFlyer, могут быть расхождения. Эти расхождения могут быть вызваны разницей в часовых поясах, разницей в схемах SRN или неправильным сопоставлением внутренних событий с CV в интеграции SRN.
        * <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx">Скачайте пример рекламных показателей SRN</Anchor> (CSV).

        **Название темы в Data Locker**: skad\_srn\_advertising\_dimensions
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-field-format-types" />

<Accordion title="Типы форматов полей сырых данных">

#### Форматы полей

| Название формата | Описание |
| --- | --- |
| Строка [n] | Максимальная длина строки. Обычно мы не применяем ограничения длины поля при получении данных, но превышающие данные могут быть обрезаны. |
| Строка времени | Строка, имеющая формат, `гггг-мм-дд чч:мм:сс`. Например, `2019-09-17 00:09:25` |
| Перечисление [n] | Поля Enum (перечисление) могут содержать только определенные значения. Например, поле Валюта расходов содержит 3 символа и может содержать только определенные коды валют. |
| Временная отметка | 10-значная метка времени Unix. Пример:<br /><br />4 августа 2020, 07:25 UTC переведено в `"timestamp": "1596525944"` |
| Логическое значение | Значение поля может быть либо `TRUE`, либо `FALSE.` |
| Целое число | Целое число |
| Число с плавающей запятой | Вещественное число с плавающей точкой, которое может иметь десятичную точку и значения после десятичной точки. |

</Accordion>

<div id="fields-available-in-postback-and-postback-copy-reports" />

<Accordion title="Поля, доступные в отчетах по постбэкам и копиям постбэков">

<table><thead><tr><th>Имя поля</th><th>Источник или начальная версия iOS SKAN</th><th>Описание</th><th>Формат</th><th>Доступно в копии постбэков </th></tr></thead><tbody><tr><td>идентификатор_кампании_рекламной_сети</td><td>Рекламная сеть</td><td>Идентификатор кампании, сообщенный рекламной сетью в AppsFlyer</td><td>строка</td><td>Нет</td></tr><tr><td><p>ad_network_campaign</p><p>_name</p></td><td>Рекламная сеть</td><td><p>Название кампании, сообщенное рекламной сетью в AppsFlyer.</p></td><td>строка</td><td>Нет</td></tr><tr><td>ad_network_timestamp</td><td>Рекламная сеть</td><td><p>Время получения постбэка рекламной сетью.</p><p>В случае Google Рекламы это время определяется по времени последнего клика, которое сообщает Google.</p></td><td>Временная отметка</td><td>Нет</td></tr><tr><td>app_id (идентификатор приложения)</td><td>AppsFlyer:</td><td>Идентификатор приложения (приложение рекламодателя) с префиксом ID.</td><td>строка</td><td>Да</td></tr><tr><td>город</td><td>AppsFlyer:</td><td>С 30 августа 2021 года значение всегда null </td><td>строка</td><td>Нет</td></tr><tr><td>код_страны</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>дма</td><td> </td><td>С 30 августа 2021 года значение всегда null </td><td>строка</td><td>Нет</td></tr><tr><td>postal_code</td><td> </td><td>С 30 августа 2021 года значение всегда null  </td><td>строка</td><td>Нет</td></tr><tr><td>Регион</td><td>AppsFlyer:</td><td>Согласно сообщаемому коду страны country_code</td><td>строка</td><td>Нет</td></tr><tr><td>skad_ad_network_id</td><td>1.0 </td><td>Некоторые SRN не сообщают свой идентификатор, и поле остается пустым. Например, Twitter. </td><td>строка</td><td>Да </td></tr><tr><td>skad_attribution_signature</td><td>1.0</td><td> </td><td>строка</td><td>Да</td></tr><tr><td>skad_campaign_id</td><td>1.0</td><td>Идентификатор кампании, используемый для публикации объявления. Диапазон: 0–100</td><td>строка</td><td>Да</td></tr><tr><td>skad_conversion_value</td><td>2.0 </td><td><p>Значение конверсии, сообщаемое iOS. Диапазон 0–63.</p><p>Если null, iOS не заполнила поле\*\* </p></td><td>Целое число</td><td>Да</td></tr><tr><td>skad_redownload</td><td>2.0</td><td>Если true, приложение было загружено повторно</td><td>Логическое значение</td><td>Да</td></tr><tr><td>skad_source_app_id</td><td>2.0</td><td><p>ID сайта. Приложение, разместившее объявление. Это поле идентично source_app_id.</p><p>Заполнение полей зависит от пороговых значений конфиденциальности\*\*</p></td><td>строка</td><td>Да</td></tr><tr><td>skad_transaction_id</td><td>1.0</td><td> </td><td>строка</td><td>Да</td></tr><tr><td>skad_версия</td><td>2.0</td><td> </td><td>строка</td><td>Да</td></tr><tr><td>временная метка</td><td>Рекламная сеть</td><td>Время, когда AppsFlyer получил постбэк SKAN. </td><td>Строка времени</td><td>Да</td></tr><tr><td>имя_рекламной_сети</td><td>Рекламная сеть</td><td>Название рекламной сети, сообщаемое рекламной сетью в AppsFlyer. <ul><li>Если это поле пустое, значит, рекламная сеть не заполнила (не смогла заполнить) его.</li><li>Название рекламной сети можно определить с помощью skad_ad_network_id. Для этого используйте эту <a href="./skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks" target="_blank">таблицу</a>. </li></ul></td><td>строка</td><td>Нет</td></tr><tr><td>ip</td><td> </td><td><p>IP-адрес в HTTP-сообщении устройства iOS, отправляющего постбэк.</p><p>Это поле заполняется, если рекламная сеть предоставляет нам этот адрес.</p><p>Внимание! SDK не участвует в получении адреса.</p></td><td>строка</td><td>Нет</td></tr><tr><td>skad_app_id</td><td>1.0</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>идентификатор_приложения_источника</td><td>AppsFlyer:</td><td>ID сайта. Приложение, разместившее объявление. Это поле идентично полю skad_source_app_id</td><td>строка</td><td>Нет</td></tr><tr><td>идентификатор_набора_объявлений_рекламной_сети</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>название_набора_объявлений_рекламной_сети</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>название_рекламной_сети_рекламы</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>идентификатор_рекламы_рекламной_сети</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>выиграл_ли</td><td>3.0 (iOS 14.6)</td><td>Используется для различения кампаний, которые <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">способствовали установке или которым атрибутирована</a> установка: <ul><li>Если true, установка атрибутирована этой кампании.</li><li>Если false, то кампания считается ассистентом в установке, но она не включается ни в какие дэшборды или отчеты SKAN.</li><li>Если null, то iOS не заполнила поле из-за устаревшей версии iOS <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">или SKAdNetwork</a>.</li></ul></td><td>Логическое значение</td><td>Да</td></tr><tr><td>fidelity_type</td><td>2.2 (iOS 14.5)</td><td><p>Различает варианты <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">представления объявлений</a>, влияющие на атрибуцию. Указывается с помощью значений 0 и 1 следующим образом: </p><ul><li>Просмотры рекламы (0)</li><li>Реклама с рендерингом StoreKit (1)</li></ul><p>Не учитывайте значение поля, если версия SKAN старше 2.2.</p></td><td>Целое число</td><td>Да</td></tr><tr><td>ad_network_source_app_id</td><td>Рекламная сеть</td><td><span>ID приложения издателя, который сообщает рекламная сеть. Используется для сверки затрат; сообщается рекламной сетью. Приложение издателя дает основу для этих данных. </span></td><td>строка</td><td>Нет</td></tr><tr><td>канал_рекламной_сети</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>af_prt</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0 (iOS 16.2)</td><td><ul><li>Значение представляет собой окно SKAN, либо<code>0</code>, либо<code>1</code>, либо<code>2</code>.</li><li>Для SKAN 3 значение равно<code>0</code> </li></ul></td><td>Целое число</td><td>Да</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li>Значение может быть <code>низкое</code>, <code>среднее</code> или <code>высокое</code>.</li><li>Для SKAN 3 значение равно <code>null</code>.</li></ul></td><td>строка</td><td>Да</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>Значение может иметь до 4 цифр.</li><li>Для SKAN 3 значение равно <code>null</code>. </li></ul></td><td>строка</td><td>Да</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>Значение представляет собой источник атрибутируемой веб-рекламы.</li><li>Для SKAN 3 значение равно <code>null</code>.</li></ul></td><td>строка</td><td>Да</td></tr><tr><td>креатив_рекламной_сети</td><td>Рекламная сеть</td><td><ul><li>Значение основано на обогащении данных, полученных от рекламной сети.</li><li>Для SKAN 3 значение равно <code>null</code> </li></ul></td><td>строка</td><td>Нет</td></tr><tr><td colspan="4">\*\* Apple определяет, заполнено ли поле, используя механизм порога конфиденциальности </td><td> </td></tr></tbody></table>

</Accordion>

<div id="fields-available-in-decoded-event-reports" />

<Accordion title="Поля, доступные в декодированных отчетах о событиях">

<table><thead><tr><th>Имя поля</th><th>Источник</th><th>Описание</th><th>Формат</th><th>Включено в отчет о показателях рекламы SRN</th></tr></thead><tbody><tr><td>идентификатор_кампании_рекламной_сети</td><td>Рекламная сеть</td><td>Идентификатор кампании, сообщенный рекламной сетью в AppsFlyer</td><td>строка</td><td>Да</td></tr><tr><td>ad_network_campaign<br/>_name</td><td>Рекламная сеть</td><td>Название кампании, сообщенное рекламной сетью в AppsFlyer</td><td>строка</td><td>Да</td></tr><tr><td>ad_network_timestamp</td><td>Рекламная сеть</td><td><p>Время получения постбэка рекламной сетью</p><p>В случае с Google Ads это поле не заполняется. </p></td><td><p>Временная отметка</p><p>(строка времени для отчета о показателях рекламы для SRN)</p></td><td>Да</td></tr><tr><td>app_id (идентификатор приложения)</td><td>iOS.</td><td>ID приложения (приложение рекламодателя)</td><td>строка</td><td>Да</td></tr><tr><td>город</td><td> </td><td>С 30 августа 2021 года значение всегда null </td><td>строка</td><td>Нет</td></tr><tr><td>код_страны</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>дма</td><td> </td><td>С 30 августа 2021 года значение всегда null </td><td>строка</td><td>Нет</td></tr><tr><td>имя_события</td><td>AppsFlyer:</td><td><p>Имя события в приложении, настроенное в AppsFlyer.</p><p>Для отчета SRN это имя события в приложении, настроенное в Meta Ads.</p></td><td>строка</td><td>Да</td></tr><tr><td>event_uuid</td><td>AppsFlyer:</td><td>Уникальный случайный идентификатор, позволяющий партнерам идентифицировать дублирующиеся постбэки</td><td>строка</td><td>Нет</td></tr><tr><td>дата_установки</td><td>iOS.</td><td>Оценивается AppsFlyer на основе времени прибытия постбэка.</td><td>Строка времени</td><td>Нет</td></tr><tr><td>install_type</td><td>iOS.</td><td>Новые установки</td><td>строка</td><td>Нет</td></tr><tr><td>ip</td><td>iOS.</td><td><p>IP-адрес в HTTP-сообщении устройства iOS, отправляющего постбэк.</p><p>Это поле заполняется, если рекламная сеть предоставляет нам этот адрес.</p><p>Внимание! SDK не участвует в получении адреса. </p></td><td>строка</td><td>Нет</td></tr><tr><td>медиа-источник</td><td>iOS.</td><td>Рекламная сеть, атрибутированная с помощью имен сетей в AppsFlyer</td><td>строка</td><td>Да</td></tr><tr><td>postal_code</td><td> </td><td>С 30 августа 2021 года значение всегда null </td><td>строка</td><td>Нет</td></tr><tr><td>Регион</td><td>AppsFlyer:</td><td>Определяется в соответствии с кодом страны country_code</td><td>строка</td><td>Нет</td></tr><tr><td>skad_ad_network_id</td><td>iOS.</td><td>Идентификатор рекламной сети, куда был отправлен постбэк</td><td>строка</td><td>Нет</td></tr><tr><td>skad_ambiguous_event</td><td>AppsFlyer:</td><td>Если true, то постбэк iOS был получен в течение первых 72 часов после того, как рекламодатель изменил настройки SKAN на дэшборде. Из-за различных таймеров, используемых SKAN, AppsFlyer не может точно сопоставить событие.<ul><li>Недоступно в SKAN 4 и более поздних версиях</li></ul></td><td>Логическое значение</td><td>Нет</td></tr><tr><td>skad_attribution_signature</td><td>iOS.</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>skad_campaign_id</td><td>iOS.</td><td>Идентификатор кампании, используемый для публикации объявления. Диапазон: 0–100</td><td>Целое число</td><td>Нет</td></tr><tr><td>skad_conversion_value</td><td>iOS.</td><td><p>Значение конверсии, сообщаемое iOS. Диапазон 0–63.</p><p>Если null, iOS не заполнила поле\*\*.</p></td><td>Целое число</td><td>Нет</td></tr><tr><td>skad_mode</td><td>AppsFlyer:</td><td>Режим измерения конверсий, используемый для декодирования постбэка iOS. Варианты:<ul><li>custom_decode</li><li>выручка</li><li>события</li><li>skan4</li><li>custom_encode</li><li>engagement</li></ul></td><td>строка</td><td>Нет</td></tr><tr><td>skad_redownload</td><td>iOS.</td><td>Если true, приложение было загружено повторно</td><td>Логическое значение</td><td>Нет</td></tr><tr><td>Строка (JSON)</td><td>iOS.</td><td>Сумма выручки от события в USD.</td><td>Число с плавающей запятой</td><td>Нет</td></tr><tr><td>skad_source_app_id</td><td>iOS.</td><td><p>ID сайта — приложение, разместившее объявление.</p><p>Заполнение полей зависит от пороговых значений конфиденциальности\*\*</p></td><td>строка</td><td>Нет</td></tr><tr><td>skad_transaction_id</td><td>iOS.</td><td>-</td><td>строка</td><td>Нет</td></tr><tr><td>skad_версия</td><td>iOS.</td><td>-</td><td>строка</td><td>Нет</td></tr><tr><td>временная метка</td><td>iOS.</td><td><p>Время, когда AppsFlyer получил постбэк SKAN.</p><p>Для Google Рекламы и Meta Ads это время, когда AppsFlyer получает данные из API Google и Meta Ads соответственно.</p></td><td><p>Временная отметка</p><p>(строка времени для отчета о показателях рекламы для SRN)</p></td><td>Да</td></tr><tr><td>event_value</td><td>S2S</td><td><p>Значение по умолчанию: null</p><p>Содержит строку, задаваемую приложениями, указывающую на пользовательское декодирование.</p><p>Рекламодатели употребляют это в своих системах. В AppsFlyer это не используется. </p></td><td>Строка (JSON)</td><td>Нет</td></tr><tr><td>идентификатор_набора_объявлений_рекламной_сети</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Да</td></tr><tr><td>название_набора_объявлений_рекламной_сети</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Да</td></tr><tr><td>название_рекламной_сети_рекламы</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Да</td></tr><tr><td>идентификатор_рекламы_рекламной_сети</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Да</td></tr><tr><td>skad_did_win (1)</td><td>3.0 (iOS 14.6)</td><td>Используется для различения кампаний, которые <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">способствовали установке или которым атрибутирована</a> установка: <ul><li>Если true, установка атрибутирована этой кампании.</li><li>Если false, то кампания считается ассистентом в установке, но она не включается ни в какие дэшборды или отчеты SKAN.</li><li>Если null, то iOS не заполнила поле из-за устаревшей версии iOS <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">или SKAdNetwork</a>.</li></ul></td><td>Логическое значение</td><td>Нет</td></tr><tr><td>skad_fidelity_type (1)</td><td>2.2 (iOS 14.5)</td><td><p>Различает варианты <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">представления объявлений</a>, влияющие на атрибуцию. Указывается с помощью значений 0 и 1 следующим образом: </p><ul><li>Просмотры рекламы (0)</li><li>Реклама с рендерингом StoreKit (1)</li></ul><p>Не учитывайте значение поля, если версия SKAN старше 2.2.</p></td><td>Целое число</td><td>Да</td></tr><tr><td>ad_network_source_app_id (1)</td><td>Рекламная сеть</td><td><span>ID приложения издателя, который сообщает рекламная сеть. Используется для сверки затрат; сообщается рекламной сетью. Основой для этих данных служит приложение издателя.</span></td><td>строка</td><td>Нет</td></tr><tr><td>ad_network_channel (1)</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>af_prt (1)</td><td>Рекламная сеть</td><td> </td><td>строка</td><td>Нет</td></tr><tr><td>min_revenue </td><td>AppsFlyer:</td><td>См. примечание (4)</td><td>Вещественное число</td><td>Нет</td></tr><tr><td>макс_выручка </td><td>AppsFlyer:</td><td>См. примечание (4)</td><td>Вещественное число</td><td>Нет</td></tr><tr><td>event_revenue</td><td>AppsFlyer:</td><td>Формула: [сумма значений для конкретного события в USD] / [Количество событий, произошедших в конкретный день]</td><td>Число с плавающей запятой</td><td>Да</td></tr><tr><td>min_event_counter</td><td>AppsFlyer:</td><td>Используется для подсчета количества раз, когда пользователь выполняет то или иное событие. См. примечание (3)</td><td>Целое число</td><td>Нет</td></tr><tr><td>max_event_counter</td><td>AppsFlyer:</td><td>См. примечание (3)</td><td>Целое число</td><td>Нет</td></tr><tr><td>min_time_post_install</td><td>AppsFlyer:</td><td>См. примечание (5)</td><td>Целое число</td><td>Нет</td></tr><tr><td>max_time_post_install</td><td>AppsFlyer:</td><td>См. примечание (5)</td><td>Целое число</td><td>Нет</td></tr><tr><td>af_attribution_flag</td><td>AppsFlyer:</td><td>Когда включен механизм единого источника истины (SSOT): Если true, установка была атрибутирована и AppsFlyer, и SKAN. Если false, установка не была атрибутирована AppsFlyer. Если значение skad_conversion_value равно null, флаг будет true или false (на основе <a href="./skan-modeled-data#null-conversion-values" target="_blank">моделирования</a>).</td><td>Логическое значение</td><td>Нет</td></tr><tr><td>measurement_window</td><td>AppsFlyer:</td><td>Продолжительность окна активности. По умолчанию 24 часа. </td><td>Целое число</td><td>Нет</td></tr><tr><td>Интервал</td><td>AppsFlyer:</td><td>Интервалы окна активности. </td><td>Целое число</td><td>Нет</td></tr><tr><td>user_agent</td><td>AppsFlyer:</td><td>Агент пользователя устройства</td><td>строка</td><td>Нет</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0 (iOS 16.2)</td><td><ul><li>Значение представляет собой окно SKAN, либо<code>0</code>, либо<code>1</code>, либо<code>2</code>.</li><li>Для SKAN 3 значение равно<code>0</code> </li></ul></td><td>Целое число</td><td>Да</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li>Значение может быть <code>низкое</code>, <code>среднее</code> или <code>высокое</code>.</li><li>Для SKAN 3 значение равно <code>null</code>.</li></ul></td><td>строка</td><td>Да</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>Значение может иметь до 4 цифр.</li><li>Для SKAN 3 значение равно <code>null</code>. </li></ul></td><td>строка</td><td>Да</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>Значение представляет собой источник атрибутируемой веб-рекламы.</li><li>Для SKAN 3 значение равно <code>null</code>.</li></ul></td><td>строка</td><td>Да</td></tr><tr><td>креатив_рекламной_сети</td><td>Рекламная сеть</td><td><ul><li>Значение основано на обогащении данных, полученных от рекламной сети.</li><li>Для SKAN 3 значение равно <code>null</code> </li></ul></td><td>строка</td><td>Нет</td></tr><tr><td colspan="4"><p>\*\* Apple определяет, заполнено ли поле, используя механизм порога конфиденциальности</p><p>(1) Начиная со 2 июня 2021 года, поле добавляется в отчеты, но не обязательно заполняется.</p><p>(3) Чтобы определить, сколько раз пользователь выполнил то или иное событие в приложении, используйте формулу <code>[округление (min_event_counter + max_event_counter) / 2]</code>. Примечание! <mark> Вы должны округлить до ближайшего целого числа.</mark><br/>Пример:<br/>А. <br/>Пример:<br/>А. <br/>Пример:<br/>A. Если min = 0 и max = 1, среднее равно 0,5; округление дает результат 1.<br/>Б. Б. B. Если min = 5 и max = 10, среднее равно 7,5; округление дает результат 8.</p><p>(4) Доход всегда указывается в поле <code>skad_revenue</code>. Если вы используете<span> SKAN 4 или пользовательский режим </span><span><a href="./skan-conversion-studio" target="_blank">Custom mode</a></span>, то диапазон корзины, связанной с событием и используемой для расчета skad_revenue, описывается в полях min_revenue и max_revenue.</p><p>(5)</p><ul><li>В пользовательской конверсии: AppsFlyer рассчитывает время установки как время прихода постбэка - 36ч. - среднее (min_time_post_install + max_time_post_install). Однако, если CV=0, то среднее (min_time_post_install + max_time_post_install) считается равным 0. </li><li>В декодированной конверсии: min_time_post_install на один час меньше, чем задано в max_time_post_install, что равно <a href="./skan-cv-decode-map-your-cv-to-events#decode-csv-file-specification" target="_blank">hours_from_install</a>, установленному вами в сопоставлении декодированных конверсий. </li></ul></td><td> </td></tr></tbody></table>

</Accordion>

## Дополнительные сведения

<div id="traits-and-limitations" />

<Accordion title="Ограничения и особенности">

| Специфика | Показы |
| --- | --- |
| Доступ рекламной сети | Рекламным сетям отправляются постбэки |
| Доступ агентств | Не доступно |
| Прозрачность агентства | Переменное число |
| Time Zone (Часовой пояс) | UTC |
| Валюта | USD (доллар США) |
| органические данные | На основе данных о событиях SDK. Например, метрики органических установок рассчитываются следующим образом: все установки, данные по которым переданы SDK, минус неорганические установки, данные о которых переданы SKAN. |
| Неорганические данные | На основе постбэков SKAN |
| Актуальность данных | Ежедневно. Время SKAN означает, что iOS сообщает об установке через 24-48 часов после закрытия окна. |
| Исторические данные | Ограничено окном доступности Data Locker. |
| Доступ пользователей аккаунта | Доступно. Согласно разрешениям аккаунта |

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#reporting-options">Доступные отчеты SKAN (руководство по решению SKAN)</Anchor>

<div data-zendesk-anchors="skan-raw-data-reports=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-skan-%D0%BF%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D0%BC-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC 01H8XHATZB2G6YZ9AJNPRZS59Y=%D0%BE%D1%82%D1%87%D0%B5%D1%82%D1%8B-skan-%D0%BF%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D0%BC-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC skan-raw-data-report-format-and-content=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82-%D0%B8-%D1%81%D0%BE%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2-skan-%D0%BF%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D0%BC-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC 01H8XHATZCJQZTZF0Y5P18XMEA=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82-%D0%B8-%D1%81%D0%BE%D0%B4%D0%B5%D1%80%D0%B6%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BE%D0%B2-skan-%D0%BF%D0%BE-%D1%81%D1%8B%D1%80%D1%8B%D0%BC-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%BC 01H8XHATZCR5BC2P5TSQTMDY5Q=raw-data-report-types 01H8XHATZC0MST5ASGWDGGK2R8=raw-data-field-format-types field-formats=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D1%8B-%D0%BF%D0%BE%D0%BB%D0%B5%D0%B9 01H8XHATZCZMNGK72DDE5HS6E9=%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%82%D1%8B-%D0%BF%D0%BE%D0%BB%D0%B5%D0%B9 01H8XHATZC24DH4AYB2C523JDH=fields-available-in-postback-and-postback-copy-reports 01H8XHATZCNXVG0E3MZ9H68AA1=fields-available-in-decoded-event-reports additional-information=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F 01H8XHATZD9D7JBHTFZ095EBD5=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F 01H8XHATZDMV0VN4BDTECGF91K=traits-and-limitations h_01HDNYQBVZP0A6SQASGDRFVFGP=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

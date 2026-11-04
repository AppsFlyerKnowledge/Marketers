---
title: Потоковая передача сырых данных через Push API
metadata:
  keywords:
    - Push API
    - Real-time
    - Installation and Conversion
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:19:42Z'
  edited_at: '2026-08-18T00:04:46Z'
  id: 207034356
  locale: ru
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ru/articles/207034356
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор:** Отправляйте сырые данные о событиях атрибуции на серверные конечные точки.

![6970_Push_API_image.png](https://files.readme.io/0bb5747a65a6ca6ed8f55f72f189b92e780649d55b766c5d295f5602745f04f5-4405028260241.png)

<div id="push-api" />

## push

Push API передает сырые данные, создаваемые средствами атрибуции AppsFlyer и SKAdNetwork, в виде сообщений на ваши серверы. Вы можете выбрать типы и контент сообщений и задать конечные точки.

Доступные типы сообщений, свежесть данных и поля зависят от выполняющей атрибуцию инфраструктуры (AppsFlyer или SKAN), как описано в следующих разделах.

<div id="appsflyer-attribution-messages" />

<Accordion title="Сообщения атрибуции AppsFlyer">

Характеристики сообщения

| Характеристика | Подробности |
| --- | --- |
| Разделение сообщений на типы | <ul><li>Сообщения могут разделяться по конечных точкам (до 6 конечных точек на приложение), или тип сообщения можно определять по значениям следующих полей:<ul><li>event\_name (название события)</li><li>conversion\_type (тип конверсии)</li><li>тип\_кампании</li></ul></li><li>Значения полей по каждому типу сообщений указаны в следующей таблице.</li></ul>**Пример:**<br /><br />Сообщение содержит следующие данные:<ul><li>conversion\_type=install</li><li>campaign\_type=organic</li><li>event\_name=install</li></ul>Используя таблицу, определяем, что это событие является событием установки, выполненной органическим пользователем. |
| Обновление данных | Сообщения отправляются вскоре после регистрации события на платформе AppsFlyer. Обычно это происходит в течение нескольких минут. |
| Содержание сообщения (поля) | <ul><li>Сообщения имеют структуру `key:value`.</li><li>См. доступные поля <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#field-availability-by-reporting-tool">Push API</Anchor> для атрибуции AppsFlyer.</li><li>Каждый ключ представляет собой поле с сырыми данными. См. <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#data-fields-dictionary">описание полей с сырыми данными в AppsFlyer</Anchor>.</li><li>Пустые ключи и ключи со значением null не отправляются.</li><li>Примеры содержат пустые поля и поля с нулевым значением. В реальных постбэках нет пустых или нулевых полей. В приведенном примере используется формат JSON.<ul><li>[https://support.appsflyer.com/hc/article\_attachments/360016192917](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=0&single=true&output=csv)</li><li>[Android;](https://docs.google.com/spreadsheets/d/e/2PACX-1vRMoTZpgttICSjjjXTh4JU5m9p3ky7Ej_MYc0kZ3vYs7sNq6u_wNvWBgjFLF_VjdRbY54aE5e-4keLY/pub?gid=233131974&single=true&output=csv)</li></ul></li></ul> |
| Формат полей меток времени | <ul><li>Временные метки UTC: `yyyy-mm-dd hh:mm:ss.sss`. Например, `2019-09-17 00:09:00.123`. Событие произошло в 18:00 по токийскому времени. Время события преобразуется в UTC: 09:00. Записанное время является временем UTC.</li><li>Выбранные временные метки (для конкретного приложения): `yyyy-mm-dd hh:mm:ss.sss±th:tm`. Например `2019-09-17 18:00:16.000+0900`. Событие произошло в 18:00 по токийскому времени. Указанное время события — 18:00+09:00. 09:00 — часовой пояс Токио.</li></ul> |

<div id="available-message-types" />

#### Доступные типы сообщений

<table><thead><tr><th>Контекст атрибуции</th><th>Тип сообщения</th><th>Поле conversion_type</th><th>Поле campaign_type</th><th>Поле event_name</th><th>Поле event_type</th></tr></thead><tbody><tr><td>Привлечение пользователей</td><td>Установка\*</td><td>Установить</td><td><p>Неорганические: UA</p><p>Органические: organic</p></td><td>Установить</td><td><ul><li>Установить</li><li>organic-install</li></ul></td></tr><tr><td>Привлечение пользователей </td><td>События внутри приложения при установке</td><td><span>Установить</span></td><td><p>Неорганические: UA</p><p>Органические: organic</p></td><td>Имена событий, определяемые рекламодателем</td><td><ul><li>install-in-app-event</li><li>organic-install-in-app-event</li></ul></td></tr><tr><td>Обязательный</td><td>повторное вовлечение</td><td>повторное вовлечение</td><td>ретаргетинг</td><td>повторное вовлечение</td><td>повторная атрибуция</td></tr><tr><td>Обязательный </td><td>События повторного вовлечения внутри приложения</td><td>повторное вовлечение</td><td>ретаргетинг</td><td>Имена событий, определяемые рекламодателем</td><td>re-engagement-in-app-event</td></tr><tr><td>Обязательный </td><td>Ретаргетинг </td><td>Повторные установки</td><td>ретаргетинг</td><td>повторная атрибуция</td><td>повторная атрибуция</td></tr><tr><td>Привлечение пользователей </td><td>Переустановка</td><td>Повторные установки</td><td><p>Неорганические: UA</p><p>Органические: organic</p></td><td>Повторные установки</td><td><ul><li>Повторные установки</li><li>organic-reinstall</li></ul></td></tr><tr><td>Обязательный</td><td>События реатрибуции внутри приложения</td><td>Повторные установки</td><td>ретаргетинг</td><td>Имена событий, определяемые рекламодателем</td><td>re-attribution-in-app-event</td></tr><tr><td colspan="6">\* Некоторые установки, связанные с атрибуцией по просмотрам, атрибутируются <a href="./about-raw-data-identifier-restrictions" target="_blank">ограниченному медиа-источнику.</a> </td></tr></tbody></table>

<div id="unique-fields" />

#### Уникальные поля

<table><thead><tr><th>Отображаемое имя</th><th>Название Push API</th></tr></thead><tbody><tr><td>Выбранная валюта\*</td><td>selected_currency</td></tr><tr><td>Выручка в выбранной валюте</td><td>revenue_in_selected_<br/>currencyвалюта</td></tr><tr><td>Затраты в выбранной валюте</td><td>cost_in_selected_<br/>currencyвалюта</td></tr><tr><td>Время загрузки на устройство согласно выбранному часовому поясу</td><td>device_download_time_selected_timezone</td></tr><tr><td>Время атрибутированного взаимодействия согласно выбранному часовому поясу</td><td>attributed_touch_time_selected_timezone</td></tr><tr><td>Время установки согласно выбранному часовому поясу</td><td>install_time_selected_<br/>timezoneчасовой пояс</td></tr><tr><td>Время события согласно выбранному часовому поясу</td><td>event_time_selected_<br/>timezoneчасовой пояс</td></tr><tr><td>Выбранный часовой пояс(\*)</td><td>selected_timezone</td></tr><tr><td colspan="2">\*Это настройка уровня приложения, действующая на момент отправки сообщения API.</td></tr></tbody></table>

</Accordion>

<div id="skan-attribution-messages" />

<Accordion title="Сообщения атрибуции SKAN">

В этом разделе описаны сообщения (типы отчетов), доступные для SKAN, и способы их идентификации. Ознакомившись с содержимым этого раздела, переходите к теме [Настройка конечной точки для атрибуции SKAN](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint).

Связанная литература: <Anchor target="_blank" href="/marketers/ru/docs/skan-raw-data-reports">Поля сырых данных SKAN</Anchor>. Сообщения Push API имеют аналогичную структуру и поля.

Характеристики сообщений

| Характеристика | Подробности |
| --- | --- |
| Разделение сообщений на типы | <ul><li>Все сообщения отправляются на одну заданную вами конечную точку.</li><li>Чтобы определить тип сообщения, используйте поле event\_type.<br />Примечание. Используя поле event\_type, вы также можете определить поле event\_name и поле skad\_redownload.</li><li>Значения поля event\_ type указаны в [следующей таблице](/docs/push-api-streaming-raw-data#типы-сообщений-для-атрибуции-skan).</li></ul>Пример:<br /><br />Сообщение содержит следующие данные:<ul><li>event\_type: skad-re-download</li></ul>Исходя из этого, мы можем определить, что:<ul><li>Это событие повторной загрузки</li><li>event\_name: install</li><li>skad\_redownload: true</li></ul> |
| Обновление данных | <ul><li>Установки, повторные загрузки и внутренние события приложения:<ul><li>Обрабатываются ежедневно</li><li>Отправляются на вашу конечную точку на следующий день после получения AppsFlyer постбэка iOS</li><li>Ожидайте сообщения о событиях с 08:00 до 11:00 UTC (точное время может меняться)</li><li>Пример: постбэки, полученные в понедельник, отправляются, начиная с 08:00 UTC вторника</li></ul></li><li>Постбэки от iOS и копии постбэков: сообщения отправляются вскоре после поступления в AppsFlyer</li></ul> |
| Примеры сообщений | Файл содержит примеры сообщений. В приведенном примере используется формат JSON. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vS0CO6W7jgx6zxMeSGIo-hbqLbFh3AO0OT6qp4cWmgdbWVMjLJ-2dermVz49jmAXexewiOGzR1YjGzu/pub?output=xlsx">Пример сообщений SKAN</Anchor>. |

<div id="message-types-for-skan-attribution" />

#### Типы сообщений для атрибуции SKAN

| Тип сообщения | Поле event\_name | Поле skad\_redownload | Поле event\_type |
| --- | --- | --- | --- |
| Установки | Установить | <ul><li>Возможные значения: false, blank, null.</li><li>Если поля нет в сообщении, значением считается false.</li></ul> | skad-install |
| Повторные загрузки | Установить | Истина | skad-re-download |
| Внутренние события приложения | Название события, заданное рекламодателем | Название события, заданное рекламодателем | skad-in-app-event |
| Постбэки от iOS | Недоступно в этом сообщении | Иногда доступно | skad\_postback |
| <Anchor target="_blank" href="/marketers/ru/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Копии постбэков</Anchor> | Недоступно в этом сообщении | Иногда доступно | skad-postback-copy |

</Accordion>

<div id="set-up-push-api-endpoints" />

## Настройка конечных точек Push API

<div id="01H8E8DET2PBGQAKHJY40R1P9Z" />

<div id="caution" />

> ❗️ **Предупреждение**
>
> Не используйте Push API для отправки данных атрибуции AppsFlyer третьим сторонам, поскольку:
>
> * Вы можете нарушить законы о конфиденциальности, такие как GDPR, если пользователь сообщил о своем нежелании передавать данные третьим сторонам.
> * Некоторые медиа-источники ограничивают использование предоставляемых ими данных уровня пользователя, передачу таких данных третьим сторонам, или и то, и другое. Убедитесь, что вы соблюдаете условия использования медиа-источников.
>   Например, [X Ads,](https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html) [Snapchat,](https://www.snap.com/en-US/privacy/privacy-policy/)[Pinterest.](https://policy.pinterest.com/en/privacy-policy)
>
> Примечание:  Это предупреждение не распространяется на данные SKAN. Для отправки данных SKAN на сторонние конечные точки используйте Push API.

Чтобы настроить Push API, выполните следующий список действий.

<div id="push-api-setup-checklist" />

#### Чек-лист по настройке Push API

<table><thead><tr><th>Шаг № </th><th>Атрибуция Appsflyer</th><th>Атрибуция SKAdNetwork </th></tr></thead><tbody><tr><td>1</td><td colspan="2"><p>Если у вас уже есть активная конечная точка Push API, этот шаг можно пропустить. </p><p>Заполните <a href="./push-api-streaming-raw-data#serverside-requirements-your-server">требования к серверу</a>.</p></td></tr><tr><td>2</td><td>Для атрибуции AppsFlyer планируйте настройки конечных точек с помощью <a href="./push-api-streaming-raw-data#push-api-planning-checklist-for-appsflyer-attribution">чек-листа для планирования Push API</a>. </td><td>Не применимо</td></tr><tr><td>3</td><td><a href="./push-api-streaming-raw-data#set-up-appsflyer-attribution-endpoint">Настройка конечной точки для атрибуции AppsFlyer</a></td><td><a href="./push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint">Настройка конечной точки для атрибуции SKAdNetwork</a></td></tr></tbody></table>

<div id="serverside-requirements-your-server" />

<Accordion title="Требования к серверу (ваш сервер)">

Убедитесь, что ваш сервер соответствует следующим требованиям:

<div id="server-side-requirements" />

#### Требования к серверу

| URL-адрес конечной точки | <ul><li>Действительное доменное имя</li><li>Максимальное количество уникальных конечных точек на приложение:<ul><li>AppsFlyer: 6 конечных точек</li><li>SKAdNetwork: 3 конечные точки</li></ul></li></ul> |
| --- | --- |
| Ответный код конечной точки | После получения сообщения конечная точка должна вернуть код состояния HTTP 200. |
| Список одобренных серверов AppsFlyer | Для обеспечения связи с конечной точкой занесите <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-server-ip-address-ranges-allowlisting">IP-адреса</Anchor> серверов AppsFlyer в разрешенный список ваших межсетевых экранов и систем безопасности. |
| Версии TLS | <ul><li>TLS 1.1</li><li>TLS 1.2+. См. <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-https-ssl-encryption-policy-support#исходящие-сообщения-appsflyer-в-роли-клиента">поддерживаемые шифры</Anchor></li></ul> |
| Порты | Порты: 80, 443 |

**Важно!** Действует механизм тайм-аута со временем ожидания 4 секунды. Если за это время AppsFlyer не получит сообщение OK, AppsFlyer будет считать это сбоем отправки сообщения.

</Accordion>

<div id="push-api-planning-checklist-for-appsflyer-attribution" />

<Accordion title="Чек-лист планирования Push API для атрибуции AppsFlyer">

* Используйте этот чек-лист для планирования настроек конечных точек AppsFlyer. Цифры на рисунке соответствуют номерам строк в чек-листе.
* Этот раздел неактуален для атрибуции SKAdNetwork. См. раздел [Настройка атрибуции SKAdNetwork.](/docs/push-api-streaming-raw-data#set-up-skadnetwork-attribution-endpoint)

**Конечная точка**

[![PushAPI_us-en.png](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)](https://files.readme.io/38b22e23c087e97c5424b649552823635310402a5c7be742bf6fc4e16d86cc42-360007246758.png)

<div id="endpoint-planning-table" />

#### Таблица планирования конечных точек

| Нет. | Настройка | Подробности | Используйте этот столбец для записи планируемых настроек |
| --- | --- | --- | --- |
| 1 | Метод | POST или GET |  |
| 2 | URL-адрес конечной точки | - |  |
| 3 | Типы сообщений о событиях | <ul><li>Выберите хотя бы один тип сообщения о событии.</li><li>Чтобы выбрать сообщения о событиях в приложении, необходимо зарегистрировать внутреннее событие. Без этого вы не можете выбрать сообщения о событиях в приложении.</li></ul>[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png) |  |
| 4 | <ul><li>Поля</li><li>Список полей является общим для всех типов сообщений</li></ul> | **Предупреждение**<br />Выбор всех полей не приводит к автоматическому включению полей сообщения, которые будут добавлены в будущем. Для добавления новых полей необходимо вручную обновить выбранные значения.<br /><br /><br /><br />Выберите нужные поля.<ul><li>Наиболее часто используемые поля уже выбраны по умолчанию.</li><li>Мы не отправляем пустые поля</li></ul> |  |
| 5 | Типы внутренних событий | Фильтруйте по внутренним событиям, чтобы уменьшить трафик, отправляемый на вашу конечную точку.<ul><li>Выберите один или несколько типов событий внутри приложения. Примечание! Если событие не отображается в списке, задайте его поиск.</li><li>Внутреннее событие можно выбрать только после того, как оно будет зарегистрировано хотя бы один раз. При необходимости используйте <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>, чтобы инициировать событие.</li><li>[![mceclip1.png](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)](https://files.readme.io/b945d7bf1b8cebb3a4b925fb240e3e1976aee934f1179cca68680ae21d565bf3-360007337257.png)</li></ul> |  |

</Accordion>

<div id="set-up-appsflyer-attribution-endpoint" />

<Accordion title="Настройка конечной точки для атрибуции AppsFlyer">

Все члены команды, имеющие права доступа к API, могут вносить изменения в настройки Push API . Другие пользователи аккаунта могут только просматривать эти настройки.

<div id="add-an-appsflyer-attribution-endpoint" />

#### Чтобы добавить конечную точку атрибуции AppsFlyer

1. В AppsFlyer, на боковой панели, откройте **Экспорт > Доступ к API.** Прокрутите вниз до раздела Push API.
2. Нажмите **Добавить конечную точку.**
3. Выберите метод HTTP: **POST** или **GET**
4. Введите **URL-адрес конечной точки**. Если вы получили сообщение «*Этот URL-адрес небезопасен*», свяжитесь со службой поддержки AppsFlyer.
5. Выберите один или несколько типов событий. **Примечание**: Если сообщения о внутренних событиях отключены, значит, пока не было записано ни одного внутреннего события.
6. Выберите поля, которые нужно включить в сообщение Push API. Примечание:
   * Обязательные поля, которые отправляются всегда: идентификатор приложения, имя события, время события, IDFA (iOS) или Advertising ID (Android)
   * Используйте элементы управления, показанные на рисунке ниже, чтобы выбрать необязательные поля.[![PushAPIFieldSelect1.jpg](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)](https://files.readme.io/316bdfcb4740d870875176e7806f969c89784406c3abc5ca34c9fa0c675a5497-360007416298.jpg)
     * Наиболее часто используемые поля уже выбраны по умолчанию. Вы можете отменить их выбор.
     * Выберите нужные вам дополнительные поля.
     * Выберите **Очистить все** , чтобы очистить все дополнительные поля.
     * Мы не отправляем пустые поля и связанный с ними ключ. Просим учесть это при планировании ваших процессов импорта/анализа.
7. Выберите одно или несколько (до 52) событий или **Все** события в приложении.
   * Список заполняется типами событий, которые уже зарегистрированы. Если какое-то событие отсутствует, отправьте событие такого типа с помощью тестового устройства.
8. Нажмите **Сохранить**.  
   Push API активен. Данные о конверсиях отправляются на конечную точку.
9. Проверьте конечную точку в соответствии с описанной ниже процедурой.

<div id="test-the-endpoint" />

#### Проверить конечную точку:

1. Нажмите **Отправить тест.**   
   Сообщение с результатом теста появится под кнопкой **Отправить тест**.   
   Тестовое сообщение отправлено на конечную точку. Если тест пройдет неудачно, проверьте, внесены ли <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-server-ip-address-ranges-allowlisting">IP-адреса AppsFlyer в список разрешенных</Anchor>.   
   **Важно!** Действует механизм тайм-аута со временем ожидания 2 секунды. Если за это время AppsFlyer не получит сообщение OK, AppsFlyer будет считать это сбоем отправки сообщения.
2. Проверьте, получено ли тестовое сообщение конечной точкой.  
   [Смотреть копию отправленного сообщения.](https://docs.google.com/spreadsheets/d/e/2PACX-1vScQf189h3Ry0BU-ejbZYkMZCJRdXXYeOwuNxPEHwY77vCVYWW9P9xCTUSJKmTvVbp_yzLidXD0WGLm/pub?gid=0&single=true&output=csv)

</Accordion>

<div id="set-up-skadnetwork-attribution-endpoint" />

<Accordion title="Настройка конечной точки для атрибуции SKAdNetwork">

Все члены команды, имеющие права доступа к API, могут вносить изменения в настройки Push API . Другие пользователи аккаунта могут только просматривать эти настройки.

**Чтобы добавить конечную точку SKAdNetwork для Push API:**

1. В AppsFlyer, на боковой панели, откройте **Экспорт > Доступ к API.** Прокрутите вниз до раздела Push API.
2. Выберите **SKAdNetwork** в качестве субъекта, выполняющего атрибуцию.
3. Нажмите **Добавить конечную точку.**   
   **Примечание**: Можно задать 1–3 конечные точки SKAdNetwork на приложение.
4. Выберите метод HTTP: **POST** или **GET**
5. Введите **URL-адрес** **конечной точки.** Если вы получили сообщение «*Этот URL-адрес небезопасен*», свяжитесь со службой поддержки AppsFlyer.
6. Мы не отправляем пустые поля и связанный с ними ключ. Просим учесть это при планировании ваших процессов импорта/анализа.
7. Нажмите **Сохранить**.  
   Push API активен. Данные отправляются на конечную точку.

</Accordion>

<div id="configure-authentication-token" />

<Accordion title="Настройка токена аутентификации">

Используя <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_tokens-app-app-id">токен аутентификации Push API</Anchor>, клиенты могут бесшовно интегрировать и защитить свои сообщения Push-API, добавив пользовательский заголовок авторизации с запрашиваемым токеном.  
Вы можете настроить заголовок авторизации, который будет отправляться вместе с вашими сообщениями Push-API, определив имя и значение токена, связанные с каждым идентификатором приложения. Это гарантирует, что ваши сообщения будут не только безопасны, но и настроены под ваши конкретные требования.

</Accordion>

<div id="additional-proceduresmanaging-endpoints" />

## Дополнительные процедуры: управление конечными точками

Все члены команды, имеющие права доступа к API, могут вносить изменения в настройки Push API . Другие пользователи аккаунта могут только просматривать эти настройки.

<div id="change-an-endpoint" />

<Accordion title="Изменение конечной точки">

**Чтобы изменить настройки конечной точки:**

1. В AppsFlyer, на боковой панели, откройте **Экспорт > Доступ к API.** Прокрутите вниз до раздела Push API.
2. Найдите конечную точку, которую нужно изменить.
3. Внесите изменения.
4. Нажмите **Сохранить.**

</Accordion>

<div id="delete-an-endpoint" />

<Accordion title="Удаление конечной точки">

**Чтобы удалить конечную точку**:

1. В AppsFlyer, на боковой панели, откройте **Экспорт > Доступ к API.** Прокрутите вниз до раздела Push API access (Доступ к Push API).
2. Нажмите **Удалить конечную точку**.
3. Нажмите **Сохранить.**  
   Конечная точка удалена.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## Поиск и устранение неполадок, особенности и ограничения

<div id="test-message-fails" />

<Accordion title="Ошибка тестового сообщения">

Если вы не получили тестовое сообщение, и доступ к вашим серверам органичен по IP-адресу, проверьте, что <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-server-ip-address-ranges-allowlisting">все IP-адреса AppsFlyer внесены в разрешенный список</Anchor>.

</Accordion>

<div id="duplicate-retargeting-inapp-events" />

<Accordion title="Повторяющиеся события ретаргетинга в приложении">

События ретаргетинга в приложении дублируются, когда событие покупки происходит как часть кампании ретаргетинга во время окна повторного вовлечения UA. Это сделано, чтобы атрибутировать доход как медиа-источнику UA, так и медиа-источнику ретаргетинга.

Вы будете получать дублированные события, только если активированы одновременно:

* События внутри приложения при установке
* События ретаргетинга внутри приложений.

<Anchor target="_blank" href="/marketers/ru/docs/resolve-retargeting-double-attribution">Выявление и дедупликация внутренних событий приложения</Anchor>

</Accordion>

<div id="inapp-event-message-selection-is-disabled" />

<Accordion title="Выбор сообщений о событиях приложения отключен">

[![InappSelectionDisabled_us-en.png](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)](https://files.readme.io/3fd283063aeaa9a6183a980689d7c77fc00b9d7023006a367b0d4f026928d128-360007246818.png)

* Событие приложения можно выбрать только после того, как было зарегистрировано хотя бы одно такое событие.
* Используйте тестовое устройство, чтобы сгенерировать внутреннее событие, или <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor>, чтобы сделать это вручную.

</Accordion>

<div id="missing-push-messages-and-cloudfront" />

<Accordion title="Отсутствующие push-сообщения и CloudFront">

Вы используете Amazon CloudFront в качестве конечной точки? Если да, проверьте, не отклоняет ли CloudFront сообщение с кодом 421. Если это так, обратитесь к статье <Anchor target="_blank" href="https://docs.aws.amazon.com/en_pv/AmazonCloudFront/latest/DeveloperGuide/cnames-https-dedicated-ip-or-sni.html">Как CloudFront отрабатывает запросы HTTPS</Anchor>.

</Accordion>

<div id="endpoint-error-messages" />

<Accordion title="Сообщения об ошибках конечных точек">

**Признак ошибки:** сообщение «*Этот URL-адрес небезопасен*» отображается при установке URL-адреса конечной точки.

**Требуемое действие**: обратитесь в службу поддержки AppsFlyer; сообщите идентификатор приложения, URL-адрес конечной точки и приложите скриншот с сообщением об ошибке.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Характеристики и ограничения">

| **Специфика** | Примечания |
| --- | --- |
| <span id="ad-networks"></span>Рекламные сети | Недоступно |
| <span id="agencies"></span>Агентства | Недоступно |
| <span id="appspecific-time-zone"></span>Часовой пояс конкретного приложения | Поддерживается |
| <span id="appspecific-currency"></span>Валюта приложения | Поддерживается |
| <span id="size-limitations"></span>Ограничения на размер | Не применимо |
| <span id="organic"></span>Органический | Да |
| <span id="nonorganic"></span>Неорганические | Да |
| <span id="data-freshness"></span>Обновление данных | Непрерывно |
| <span id="historical-data"></span>Исторические данные | Не поддерживается. Если вам не хватает данных, используйте Pull API, чтобы получить нужные данные. В случае SKAN некоторые исторические данные можно получить через Data Locker (ограничено окном доступности Data Locker). |
| <span id="account-owneruser-access"></span>Доступ владельца аккаунта / пользователей | Только **владелец аккаунта** AppsFlyer может изменять настройки Push API.<ul><li>У каждого аккаунта AppsFlyer есть **только один** владелец аккаунта. Это первый пользователь AppsFlyer (созданный при открытии аккаунта).</li></ul>Другие пользователи аккаунта могут просматривать настройки Push API, но не могут их изменять. |
| <span id="authentication-token-in-test-messages"></span>Токен аутентификации в тестовых сообщениях | Заголовки [тестовых сообщений](#проверить-конечную-точку) не содержат токен аутентификации. |

</Accordion>

<div id="can-i-include-custom-headers-with-the-push-api-request" />

<Accordion title="Могу ли я включить пользовательские заголовки в запрос Push API?">

Нет. Push API поддерживает использование заголовка `Authorization` только для токенов аутентификации. Дополнительные пользовательские заголовки, такие как `consumer-key`, **не поддерживаются**.

Если вам нужно передать дополнительные параметры, включите их в URL-адрес. Например:

```
https://your.server.com?consumer_key=abc456
```

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Сравнение инструментов для доставки сырых данных</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/put_app-app-id">Настройка Push API с помощью API</Anchor>

<div data-zendesk-anchors="push-api=push 01H89PJFBPXVKJGGH18CJBJ41W=push 01H89PJFBP45FQDHT4YGS58NP8=appsflyer-attribution-messages available-message-types=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D1%82%D0%B8%D0%BF%D1%8B-%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D0%B9 01H89PJFBP9DEX520BDGC5PANQ=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B%D0%B5-%D1%82%D0%B8%D0%BF%D1%8B-%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D0%B9 unique-fields=%D1%83%D0%BD%D0%B8%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8F 01H89PJFBPBK09Q7CRPMM4G7PJ=%D1%83%D0%BD%D0%B8%D0%BA%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8F 01H89PJFBQM4NKFSFF8XGMX9XT=skan-attribution-messages message-types-for-skan-attribution=%D1%82%D0%B8%D0%BF%D1%8B-%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-skan 01H89PJFBQBFCK5QVWW2X09H28=%D1%82%D0%B8%D0%BF%D1%8B-%D1%81%D0%BE%D0%BE%D0%B1%D1%89%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B4%D0%BB%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-skan set-up-push-api-endpoints=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%8B%D1%85-%D1%82%D0%BE%D1%87%D0%B5%D0%BA-push-api 01H89PJFBQZ2FW3ST5V4FW91GS=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%8B%D1%85-%D1%82%D0%BE%D1%87%D0%B5%D0%BA-push-api 01H89PJFBQ6WP7ERP0DJ69QZ1G=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 push-api-setup-checklist=%D1%87%D0%B5%D0%BA-%D0%BB%D0%B8%D1%81%D1%82-%D0%BF%D0%BE-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B5-push-api 01H89PJFBQ625A7G3QT5HQJXMW=%D1%87%D0%B5%D0%BA-%D0%BB%D0%B8%D1%81%D1%82-%D0%BF%D0%BE-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B5-push-api 01H89PJFBQGW8ZV76Z0HTNX2AB=serverside-requirements-your-server serverside-requirements=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BA-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D1%83 01H89PJFBQ2BC5GHX403RD2RAT=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BA-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D1%83 01H89PJFBQ4FXB7ABMFVHX326H=push-api-planning-checklist-for-appsflyer-attribution endpoint-planning-table=%D1%82%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D0%B0-%D0%BF%D0%BB%D0%B0%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%8B%D1%85-%D1%82%D0%BE%D1%87%D0%B5%D0%BA 01H89PJFBQJXWWPQDKZ387VYX3=%D1%82%D0%B0%D0%B1%D0%BB%D0%B8%D1%86%D0%B0-%D0%BF%D0%BB%D0%B0%D0%BD%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%8B%D1%85-%D1%82%D0%BE%D1%87%D0%B5%D0%BA 01H8E8DET2PBGQAKHJY40R1P9Z=%D0%BF%D1%80%D0%B5%D0%B4%D1%83%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 01H89PJFBQZE6KJDHXRB8GK7TF=set-up-appsflyer-attribution-endpoint add-an-appsflyer-attribution-endpoint=%D1%87%D1%82%D0%BE%D0%B1%D1%8B-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%B8%D1%82%D1%8C-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%83%D1%8E-%D1%82%D0%BE%D1%87%D0%BA%D1%83-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-appsflyer h_01JFSS65G8GTZNMY257QCV922M=%D1%87%D1%82%D0%BE%D0%B1%D1%8B-%D0%B4%D0%BE%D0%B1%D0%B0%D0%B2%D0%B8%D1%82%D1%8C-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%83%D1%8E-%D1%82%D0%BE%D1%87%D0%BA%D1%83-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-appsflyer test-the-endopoint=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%B8%D1%82%D1%8C-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%83%D1%8E-%D1%82%D0%BE%D1%87%D0%BA%D1%83 h_01JFSS6YVP1WFWXSZ7HP7GTDA2=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%B8%D1%82%D1%8C-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%83%D1%8E-%D1%82%D0%BE%D1%87%D0%BA%D1%83 01H89PJFBQQS31C6AF245SSJ61=set-up-skadnetwork-attribution-endpoint h_01HSDW5XQ28T3SQJTN5PBSBCFT=configure-authentication-token additional-procedures%E2%80%94managing-endpoints=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%82%D0%BE%D1%87%D0%BA%D0%B0%D0%BC%D0%B8 01H89PJFBQ7WV3NM7JR5Z9QEFB=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D1%83%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-%D1%82%D0%BE%D1%87%D0%BA%D0%B0%D0%BC%D0%B8 01H89PJFBQ9RZXNHGNNYV5MP7P=change-an-endpoint 01H89PJFBQGE1WESD7ZEMBEFNE=delete-an-endpoint troubleshooting-traits-and-limitations=%D0%BF%D0%BE%D0%B8%D1%81%D0%BA-%D0%B8-%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F 01H89PJFBQJDGT1FVHKG9DETHJ=%D0%BF%D0%BE%D0%B8%D1%81%D0%BA-%D0%B8-%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F 01H89PJFBQAAZYF7YWKC7TP884=test-message-fails 01H89PJFBQHQJSHE09GC599AQ6=duplicate-retargeting-inapp-events 01H89PJFBRDET8T8CTAP1GW0J9=inapp-event-message-selection-is-disabled 01H89PJFBRH58FX1FTH37DP3HC=missing-push-messages-and-cloudfront 01H89PJFBR3CJSR2AEFP3HT5JE=endpoint-error-messages 01H89PJFBRZXXEMPBGBPB35MQ9=specifications-and-limitations h_01JQY6KXYBGXTSVDC18H5CZCWR=can-i-include-custom-headers-with-the-push-api-request h_01HE7SH7XFMPJ13DKCZ04RCJDD=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

---
title: Master API — метрики привлечения пользователей через API
metadata:
  keywords:
    - Master API
    - Customizable
    - Aggregated Data
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-09-27T15:10:38Z'
  edited_at: '2026-08-27T00:02:31Z'
  id: 213223166
  locale: ru
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ru/articles/213223166
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор.** Выбранные KPI для LTV, активности, удержания, когорты и эффективности кампании Protect360 по API, в формате CSV или JSON. Выберите 1 или несколько приложений.

<div id="master-apiuser-acquisition-metrics-via-api" />

## Master API — метрики привлечения пользователей через API

Master API:

* Позволяет получить выбранные ключевые показатели эффективности для LTV, активности, удержания, когорты и эффективности кампании Protect360. Доступные KPI эквивалентны KPI, которые можно найти на дэшбордах Обзорный, Активность, Удержание, Когорта и Protect360.
* Рассчитываются ежедневно. Обновленные данные будут доступны вам в течение 24–48 часов, в зависимости от часового пояса вашего приложения.
* Это инфраструктура, на которой построена <Anchor target="_blank" href="/marketers/ru/docs/pivot-table-user-metrics">сводная таблица</Anchor> AppsFlyer.

Чтобы использовать Master API, вы определяете данные, которые хотите просмотреть (аналогично реализации <Anchor target="_blank" href="/marketers/ru/docs/pull-api-aggregate-data">Pull API</Anchor>). Результат возвращается в виде файла CSV или JSON.

**Чтобы использовать Мастер API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Получите <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">токен API</Anchor>. Получить токен должен админ.
2. Дайте разработчику токен API, который будет использоваться в заголовке аутентификации.
3. Предоставьте разработчикам параметры, которые они должны ввести при вызове API, как описано в следующем разделе. Параметры определяют, что содержится в отчете, как он организован, а также устанавливают временные рамки отчетности.
4. Попросите своего разработчика следовать <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-9">инструкциям для Master API</Anchor> в Центре разработчиков.
5.
   <div id="api-parameters" />

   <Accordion title="Параметры API">

   | Параметр | Значение | Обязательно/Необязательно |
   | --- | --- | --- |
   | app\_id (идентификатор приложения) | * Идентификатор приложения, указанный в AppsFlyer.<br />* Вставьте идентификатор приложения точно как он указан в AppsFlyer.<br />* Для приложений iOS необходим префикс **id**<br />* Используйте **все идентификаторы приложений** для запроса всех ваших приложений. | Да |
   | from (от) | Нижняя граница диапазона дат атрибуции LTV.<br /><br />* Формат: строка гггг-мм-дд<br />* Пример: `from: 2020-01-02` | Да |
   | to (по) | Верхняя граница диапазона дат атрибуции LTV<br /><br />* Количество дней в диапазоне: 1-31 дней<br />* За один день: значения `from` и `to` идентичны.<br />* Формат: гггг-мм-дд<br />* Пример: `from: 2021-01-01, to: 2021-01-31` составляет 31 день. | Да |
   | [Группировки](/docs/master-api-user-acquisition-metrics-via-api#groupings) | Группировка по параметрам, через запятую. Доступный список см. в таблице группировок. <br /><br />Например: `groupings=pid,geo` | Да |
   | [Локальные настройки](/docs/master-api-user-acquisition-metrics-via-api#kpis) | Список KPI, которые необходимо включить, каждый отделяется запятой. Список KPI приведен в таблице KPI.<br /><br />Пример: `kpis=installs,clicks, impressions,sessions,retention_day_7` | Да |
   | [Фильтры](/docs/master-api-user-acquisition-metrics-via-api#filters-optional) | Данные можно фильтровать с помощью одного или нескольких параметров фильтра. | Нет |
   | [Валюта](/docs/master-api-user-acquisition-metrics-via-api#localization) | Чтобы получать данные с использованием валюты приложения, установите currency=preferred | Нет |
   | [Часовой пояс](/docs/master-api-user-acquisition-metrics-via-api#localization) | Чтобы получать данные с использованием часового пояса приложения, установите timezone=preferred.  Посмотреть [правила локализации](/docs/master-api-user-acquisition-metrics-via-api#localization) | Нет |
   | Формат | По умолчанию данные ответа приходят в формате CSV. Если вы предпочитаете получать данные в формате JSON, выберите `format=json`. | Нет |

   </Accordion>

   <div id="groupings" />

   <Accordion title="Группировки">

   Эти показатели используются для объединения данных в группы, что позволяет легче и точнее изучать информацию. Описание этих полей можно найти <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary">здесь</Anchor>.

   <table><thead><tr><th>Группировать по<br/>Имя API</th><th>Группировать по отображаемому имени</th><th>KPI для LTV</th><th>KPI удержания</th><th>KPI активности</th><th>Дэшборд Protect360</th><th>Когорта</th></tr></thead><tbody><tr><td>app_id (идентификатор приложения)</td><td>Идентификатор приложения</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td></tr><tr><td>pid</td><td>Медиа-источник</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td></tr><tr><td>af_prt</td><td>Агентство</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td><td>Нет</td></tr><tr><td>c</td><td>Кампания</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td></tr><tr><td>af_adset</td><td>Группа объявлений</td><td>Да</td><td>Да</td><td>Да</td><td>Нет</td><td>Нет</td></tr><tr><td>af_ad</td><td>Реклама</td><td>Да</td><td>Да</td><td>Да</td><td>Нет</td><td>Нет</td></tr><tr><td>af_channel</td><td>Канал</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td><td>Нет</td></tr><tr><td>af_siteid</td><td>Идентификатор издателя</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td></tr><tr><td>af_keywords</td><td>Ключевые слова</td><td>Да</td><td>Да</td><td>Да</td><td>Нет</td><td>Нет</td></tr><tr><td>is_primary</td><td>Is Primary Attribution (Основная атрибуция)</td><td>Да</td><td>Нет</td><td>Да</td><td>Да</td><td>Нет</td></tr><tr><td>af_c_id</td><td>ID кампании</td><td>Да</td><td>Нет</td><td>Да</td><td>Да</td><td>Нет</td></tr><tr><td>af_adset_id</td><td>ID блока рекламы</td><td>Да</td><td>Нет</td><td>Да</td><td>Нет</td><td>Нет</td></tr><tr><td>af_ad_id</td><td>ID рекламы</td><td>Да</td><td>Нет</td><td>Да</td><td>Нет</td><td>Нет</td></tr><tr><td>время_установки</td><td>Время установки</td><td>Да</td><td>Да</td><td>Да\*</td><td>Да</td><td>Да</td></tr><tr><td>attributed_touch_type (атрибутированный тип взаимодействия)</td><td>Тип взаимодействия</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td><td>Нет</td></tr><tr><td>geo (гео)</td><td>Геоданные</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td><td>Да</td></tr><tr><td colspan="7">\* В контексте KPI активности считайте время установки временем события. </td></tr></tbody></table>

   </Accordion>

   <div id="kpis" />

   <Accordion title="Специфика">

   KPI — это метрики, используемые для получения информации о поведении вашего приложения. KPI сгруппированы по типам на следующих вкладках.

   <div id="ltv" />

   <Accordion title="Данные LTV: 5 лет">

   Суммарная прибыль от пользователя (LTV) — агрегированные данные о событиях, сегментированные по дням установки и до сегодняшнего дня.

   | Имя API для KPI | Описание |
   | --- | --- |
   | impressions (показы) | Количество показов за выбранный промежуток времени |
   | clicks (клики) | Количество кликов за выбранный промежуток времени |
   | installs (установки) | Количество установок за выбранный промежуток времени |
   | cr | Коэффициент конверсии |
   | sessions (сеансы) | Количество сессий от пользователей, установивших приложение, за выбранный промежуток времени |
   | loyal\_users | Количество лояльных пользователей, установивших приложение, за выбранный промежуток времени |
   | loyal\_users\_rate | Лояльные пользователи / Установки |
   | cost (затраты) | Общие затраты за выбранный период времени. [См. ограничения](/docs/master-api-user-acquisition-metrics-via-api#limitations). |
   | revenue (доход) | Доход от пользователей в течение их жизненного цикла, которые установили приложение в выбранный промежуток времени. |
   | roi | Рентабельность инвестиций за определенный период времени |
   | arpu\_ltv | Средний доход от пользователя, для пользователей, которые установили приложение в выбранный промежуток времени. |
   | average\_ecpi | Эффективная цена за установку (eCPI) в течение определенного периода времени. Доступно только в том случае, если в вызов включены затраты и установки. |
   | uninstalls (удаления) | Пользователи, удалившие приложение, которые установили приложение в выбранный промежуток времени. |
   | uninstalls\_rate | Процент удалений |
   | event\_counter\_[event\_name] | Сколько раз произошло событие |
   | unique\_users\_[event\_name] | Количество уникальных пользователей, выполнивших событие |
   | sales\_in\_usd\_[event\_name] | Доход, отраженный как часть отчетных событий |

   </Accordion>

   <div id="retention" />

   <Accordion title="Удержание">

   Удержание является метрикой того, насколько существующие пользователи активны в вашем приложении.

   **Примечание.**

   * Максимальное количество дней для удержания составляет 30 дней после установки, где день 0 — это день установки. Это означает, что значение [x] не может превышать 30.
   * Если вы запрашиваете retention\_day\_1 до того, как данные за этот день станут доступны, возвращаемая метрика будет относиться к пользователям, установившим приложение в предыдущий день. Например, 2 января вы запрашиваете retention\_day\_1 для пользователей, установивших 1 января. Поскольку метрика еще недоступна, возвращаемая метрика относится к пользователям, которые установили приложение 31 декабря.

   | KPI | Описание |
   | --- | --- |
   | retention\_day\_[x] | Количество удержанных пользователей в день X |
   | retention\_rate\_day\_[x] | Количество удержанных пользователей в день X из всего числа установивших пользователей |

   </Accordion>

   <div id="activity" />

   <Accordion title="Активность приложения за выбранный диапазон дат.">

   Активность приложения за выбранный диапазон дат. **Примечание**: KPI активности включают объединённые данные (UA и ретаргетинг вместе).

   | KPI | Описание |
   | --- | --- |
   | activity\_average\_dau | Среднесуточное количество активных пользователей (DAU) за выбранный период времени |
   | activity\_average\_mau | Среднемесячное количество активных пользователей за выбранный период времени (один день MAU представляет собой количество уникальных пользователей за предшествующие 30 дней) |
   | activity\_average\_dau\_mau\_rate | Среднее соотношение DAU/MAU |
   | activity\_average\_arpdau | Средний доход на одного активного пользователя в день — средний доход за определенный день от всех уникальных пользователей |
   | activity\_sessions | Количество сессий за выбранный промежуток времени |
   | activity\_revenue | Доход, сообщенный за выбранный промежуток времени |
   | activity\_event\_counter\_[event\_name] | Количество событий, сгенерированных пользователями за выбранный промежуток времени |
   | activity\_sales\_in\_usd\_[event\_name] | Доход, сообщенный как часть отчетных событий за выбранный промежуток времени |
   | activity\_average\_unique\_users\_[event\_name] | Среднее количество уникальных пользователей, совершивших данное событие за выбранный промежуток времени |

   </Accordion>

   <div id="cohort" />

   <Accordion title="Ретаргетинг">

   Когорты AppsFlyer предоставляют рекламодателям возможность просматривать и сравнивать различные метрики для нескольких когорт за разные периоды времени.

   **Примечание.**

   * **Ошибки округления:** KPI когорты на пользователя рассчитываются с использованием четырех десятичных знаков. Это означает, что если рассчитанное значение для каждого пользователя &lt;0,0001, оно отображается как 0. Например, количество пользователей — 100 000, а общий доход — 9 долларов. Доход на одного пользователя составляет 9/100000=0,00009. При 0,00009&lt;0,0001 отображаемое значение будет равно 0.
   * **Дни когорты**: Максимальное количество дней в когорте составляет 90 дней после установки, где день 0 — это день установки. Значение дня когорты [x] должно находиться в диапазоне 1–90.  **Примечание**. cohort\_day\_0 не поддерживается в Master API, хотя поддерживается на дэшборде когорт.
   * **Master API, API когорты и <Anchor target="_blank" href="/marketers/ru/docs/cohort-and-retention-dashboard">дэшборд когорты:</Anchor>** Результаты могут отличаться из-за различной обработки повторных установок и проблем со временем.

   **Сеансы**

   | KPI | Описание |
   | --- | --- |
   | cohort\_day\_[x]\_total\_sessions\_per\_user | День когорты x — совокупное количество сессий на пользователя до дня x (включая день x) |
   | cohort\_day\_[x]\_sessions\_per\_user | День когорты x — сессии в день x только из когорты |
   | cohort\_[x]\_days\_total\_sessions\_per\_user | Заменяет указание KPI Cohort\_day\_1\_total\_sessions\_per\_user на Cohort\_day\_x\_total\_sessions\_per\_user в URL-адресе.<br /><br />Например: cohort\_3\_days\_total\_sessions\_per\_user (всего сессий на пользователя за три дня когорты) в URL-адресе создает 3 столбца отчета:  <br />Cohort\_day\_1\_total\_sessions\_per\_user+ Cohort\_day\_2\_total\_sessions\_per\_user+Cohort\_day\_3\_total\_sessions\_per\_user |

   **Доход**

   | KPI | Описание |
   | --- | --- |
   | cohort\_day\_[x]\_total\_revenue\_per\_user | День когорты x — совокупный доход на пользователя до дня x (включая день x) |
   | cohort\_day\_[x]\_revenue\_per\_user | День когорты x — ARPU, полученный в день x только из когорты |
   | cohort\_[x]\_days\_total\_revenue\_per\_user | Заменяет Cohort\_day\_1\_total\_revenue\_per\_user, определяющее KPI, на Cohort\_day\_x\_total\_revenue\_per\_user.<br /><br />Например: cohort\_3\_days\_total\_revenue\_per\_user (общий доход на пользователя за три дня когорты) в URL-адресе создает 3 столбца отчета:  <br />Cohort\_day\_1\_total\_revenue\_per\_user+ Cohort\_day\_2\_total\_revenue\_per\_user+Cohort\_day\_3\_total\_revenue\_per\_user |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_revenue\_per\_user | Совокупный доход на пользователя в день когорты x в зависимости от конкретного события в приложении. |
   | cohort\_day\_[x]\_event\_[eventname]\_revenue\_per\_user | Доход на пользователя в день когорты х в зависимости от конкретного события в приложении |

   **События**

   | KPI | Описание |
   | --- | --- |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_per\_user | День когорты x — совокупное количество событий на пользователя до дня x (включая день x) |
   | cohort\_day\_[x]\_event\_[eventname]\_per\_user | День когорты x — события, полученные в день x только из когорты |
   | cohort\_[x]\_days\_total\_event\_[eventname]\_per\_user | Заменяет события, определяющие KPI, на Cohort\_day\_x\_total\_events\_per\_user.<br /><br />Например: cohort\_3\_days\_total\_events\_per\_user (всего событий пользователя за три дня когорты) в URL-адресе создает 3 столбца отчета:  <br />Cohort\_day\_1\_total\_events\_per\_user+ Cohort\_day\_2\_total\_events\_per\_user+Cohort\_day\_3\_total\_events\_per\_user |

   </Accordion>

   <div id="protect360" />

   <Accordion title="Дэшборд Protect360">

   **KPI Protect360**

   | Описание | KPI |
   | --- | --- |
   | **Установки** |  |
   | Всего | protect360\_total\_installs |
   | Заблокировано | blocked\_installs |
   | % заблокированных | blocked\_installs\_rate |
   | Пост-атрибуция | post\_attribution\_installs |
   | % после атрибуции | post\_attribution\_installs\_rate |
   | Общее число мошеннических установок | total\_fraudulent\_installs |
   | % мошеннических установок | fraudulent\_installs\_rate |
   | **Ложные установки** |  |
   | Блокировка в реальном времени | real\_time\_fake\_installs |
   | Пост-атрибуционное мошенничество | post\_attribution\_fake\_installs |
   | **Перехваченные установки** |  |
   | Блокировка в реальном времени | real\_time\_hijacked\_installs |
   | Пост-атрибуционное мошенничество | post\_attribution\_installs\_hijacked\_installs |
   | **Правила проверки** |  |
   | Заблокированные установки | validation\_rules\_blocked\_installs |
   | Заблокированная атрибуция | validation\_rules\_blocked\_attribution |
   | **Разбивка заблокированных фальшивых установок** |  |
   | Черный список заблокированных идентификаторов сайтов | blocked\_installs\_siteid\_blacklist |
   | Пост-атрибуционный черный список идентификаторов сайтов | post\_attribution\_installs\_siteid\_blacklist |
   | Заблокированные боты | blocked\_installs\_bots |
   | Пост-атрибуционные боты | post\_attribution\_installs\_bots |
   | Заблокированные поведенческие аномалии | blocked\_installs\_behavioral\_anomalies |
   | Post-attribution behavioral anomalies (Пост-атрибуционные поведенческие аномалии) | post\_attribution\_installs\_behavioral\_anomalies |
   | Установки, заблокированные при проверке | blocked\_installs\_install\_validation |
   | **Разбивка заблокированных перехватов установок** |  |
   | Заблокированные перехваты установок | blocked\_installs\_install\_hijacking |
   | Перехваты установок, выявленные после атрибуции | post\_attribution\_installs\_installs\_hijacking |
   | Заблокированные из-за отклонения CTIT | blocked\_installs\_ctit\_anomalies |
   | Пост-атрибуционные отклонения CTIT | post\_attribution\_installs\_ctit\_anomalies |
   | Блокировка клик-флудинга | blocked\_installs\_click\_flood |
   | Клик-флудинг после атрибуции | post\_attribution\_installs\_click\_flood |
   | **Клики** |  |
   | Всего | protect360\_total\_clicks |
   | Заблокировано | blocked\_clicks |
   | % | blocked\_clicks\_rate |
   | **Внутренние события приложений** |  |
   | Всего | protect360\_total\_in\_apps |
   | Заблокировано | blocked\_in-app-events |
   | % | blocked\_in-app-events\_rate |
   | Признаки фермы устройств — новые устройства |  |
   | Установки | install\_fraud\_new\_devices\_total |
   | % установок | install\_fraud\_new\_devices\_total\_installs\_rate |
   | % лояльных пользователей | install\_fraud\_new\_devices\_total\_loyal\_user\_rate |
   | **Признаки фермы устройств — устройства, использующие ограничение отслеживания рекламы** |  |
   | Установки | install\_fraud\_lat\_devices\_total |
   | % установок | install\_fraud\_lat\_devices\_total\_installs\_rate |
   | % лояльных пользователей | install\_fraud\_lat\_devices\_total\_loyal\_user\_rate |
   | **Признаки клик-флудинга** |  |
   | Коэффициент конверсии | conversion\_rate |
   | **Признаки клик-флудинга — CTIT** |  |
   | Больше 60 минут | click\_flood\_over\_1\_hour\_rate |
   | Больше 5 часов | click\_flood\_over\_5\_hours\_rate |

   </Accordion>

   <div id="calculated-kpis" />

   #### Рассчитанные KPI

   В дополнение к описанным ранее KPI в отчеты по Master API можно добавлять рассчитанные KPI. Это позволяет включать собственные отчеты в отчеты Master API.

   В вычисляемые формулы KPI можно вставлять любое количество встроенных объектов KPI. Каждый объект расчета KPI включает в себя ключ и значение. Ключ — это имя, которое вы даете KPI, а значение — это формула KPI.

   Поддерживаются стандартные арифметические операторы: сложение (+), закодированное как %2b, вычитание (-), умножение (*), деление (/), закодированное как %2f.

   Ключи полей рассчитываемых KPI **должны** начинаться с «calculated\_kpi\_», за которым следует любая допустимая строка, например «calculated\_kpi\_purchaserate».

   <div id="example" />

   > 📄 **Пример**
   >
   > ```http
   > kpis=installs,loyal_users_rate&calculated_kpi_3days_retention=
   > retention_day_1%2Bretention_day_2%2Bretention_day_3
   > ```
   >
   > **Средний доход от показа**
   >
   > ```http
   > kpis=installs&calculated_kpi_rev_per_impression=revenue%2Fimpression
   > ```
   >
   > **ROI за день когорты 7**
   >
   > ```http
   > kpis=installs,roi,arpu_ltv,cost,revenue&calculated_kpi_roi_day_7=
   > (cohort_day_7_total_revenue_per_user-average_ecpi)%2Faverage_ecpi
   > ```

   </Accordion>

   <div id="filters-optional" />

   <Accordion title="Фильтры (необязательно)">

   | Параметр | Описание | Пример | Обязательно/Необязательно |
   | --- | --- | --- | --- |
   | pid | * Используется для выбора строк, в которых отображаются указанные медиа-источники.<br />* Поддерживается множественный выбор через запятую. | pid=organic,applovin\_int | Нет |
   | c | * Используется для фильтрации по названию кампании.<br />* Поддерживается множественный выбор через запятую. | c=my\_sample\_campaign | Нет |
   | af\_prt | * Используется для фильтрации по названию агентства.<br />* Поддерживается множественный выбор через запятую. | af\_prt=moburst | Нет |
   | af\_channel | * Используется для фильтрации по названию канала.<br />* Поддерживается множественный выбор через запятую. | af\_channel=Instagram | Нет |
   | af\_siteid | * Используется для фильтрации по идентификатору издателя.<br />* Поддерживается множественный выбор через запятую. | af\_siteid=12345678 | Нет |
   | geo (гео) | * Используется для фильтрации по стране.<br />* Поддерживается множественный выбор через запятую. | geo=US,DE | Нет |

   </Accordion>

   <div id="localization" />

   <Accordion title="Localization (Локальные настройки)">

   Местная валюта и часовой пояс для конкретного приложения задаются на <Anchor target="_blank" href="/marketers/ru/docs/app-settings">странице настроек приложения</Anchor>. Данные Master API могут извлекать данные, используя либо валюту и часовой пояс системы по умолчанию, либо часовой пояс и валюту приложения.

   Применяется следующее:

   * Использование часового пояса/валюты конкретного приложения поддерживается только в том случае, если все приложения имеют одинаковый часовой пояс/валюту. В противном случае используются UTC и доллары США. Часовой пояс и валюта разделены. Это означает, что если валюта всех приложений одинакова, а часовые пояса — нет, то вы можете использовать валюту приложения, но не часовой пояс приложения.
   * Если предпочтительный часовой пояс был изменен на дэшборде в пределах запрошенного диапазона времени, созданный отчет будет содержать значения, начиная с самого последнего изменения часового пояса.

   Используйте следующие параметры, чтобы выбрать настройку для конкретного приложения. **Примечание.** Если вы не используете предпочтительные параметры, вы получаете настройки по умолчанию: доллары США для валюты и UTC для часового пояса.

   | Параметр | Описание | Пример | Обязательно/Необязательно |
   | --- | --- | --- | --- |
   | currency (валюта) | Денежные значения указываются в валюте конкретного приложения | currency=preferred | Нет |
   | timezone (часовой пояс) | Используемый часовой пояс соответствует часовому поясу приложения. | timezone=preferred | Нет |

   </Accordion>

<div id="additional-information" />

## Дополнительные сведения

<div id="limitations" />

<Accordion title="Ограничения и особенности">

| Специфика | Примечания |
| --- | --- |
| Данные о затратах | <ul><li>Доступность различных параметров затрат, то есть для группы объявлений, отдельного объявления, гео, канала и идентификатора сайта, <Anchor target="_blank" href="/marketers/ru/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">зависит от рекламной сети</Anchor>.</li><li>Чтобы получить eCPI: Если данные о затратах доступны, включите в вызов как установки, так и затраты.</li><li>В целом, все источники, включая собственные медиа, которые используют ссылки AppsFlyer и содержат параметр затрат в ссылках, полностью поддерживают данные о затратах, независимо от запрошенных показателей. Сети с самостоятельной атрибуцией и собственными API обычно поддерживают данные о затратах только по некоторым доступным показателям. Например, <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-faq#what-are-the-limitations-of-facebook-cost-data-in-master-api">Meta ads</Anchor> не поддерживает группировку по гео и каналу в одном вызове. Поддерживается группировка по любому из них отдельно.</li><li>Кампании, в которых есть данные о затратах, но нет данных об установках за недавнее время (около 7 дней), недоступны через Master API.</li></ul> |
| Группировки | Конкретные группировки доступны только для KPI для LTV, активности или удержания. API возвращает значение N/A, если данные для определенного KPI недоступны. Например, запрос retention\_rate\_day\_7 с группировкой по af\_channel возвращает значение N/A. |
| Аспекты | Для когортных данных: если в атрибуции участвует агентство, в качестве медиаисточника возвращается название агентства |
| Максимальное количество строк в отчете | 200 тыс. |
| Название события | Master API в настоящее время не поддерживает имена событий, содержащие косую черту `/` . Чтобы преодолеть это ограничение, избегайте использования `/` в названиях событий. |
| Время обработки | Выбор более одного приложения увеличивает время обработки, и ответ может занять больше времени. |
| Диапазон дат | Детализация периода времени — ежедневно. |
| Агентства | Master API недоступен |
| Рекламные сети | Master API недоступен |
| Исторические данные | <ul><li>Данные LTV: 25 месяцев (2 года + 1 месяц)</li><li>Данные когорты (ежедневная когорта): 2 года</li><li>Данные об активности: 3 года</li></ul> |
| Обязательный | <ul><li>Не поддерживается</li><li>Исключение: KPI активности для трафика после 1 февраля 2025 года включают объединенные данные (UA и ретаргетинг вместе).</li></ul> |

</Accordion>

<div data-zendesk-anchors="master-api%E2%80%94user-acquisition-metrics-via-api=master-api--%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-api h_01JJVMXKACJ2V4YZFGYXVB8FQF=master-api--%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-api h_01JJVMXKACZDXPQG4271HFYWCE=api-parameters h_01JJVMXKAEXMKQQRT0RT6N8P74=groupings h_01JJVMXKAEHM0871GBQHZENRXA=kpis h_01JK2ZEH32Y92Y553540XDYZFA=ltv h_01JK2ZEH32A08EEDZEWFSX3ZFS=retention h_01JK2ZEH3219694E4PFPZ8ZXZF=activity h_01JK2ZEH32NCWZWKTDS0J6DFS2=cohort h_01JK2ZEH32Q7B6RCQYXNHM8KGK=protect360 calculated-kpis=%D1%80%D0%B0%D1%81%D1%81%D1%87%D0%B8%D1%82%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-kpi h_01JJVMXKAFW1TEE35GK9B20TRP=%D1%80%D0%B0%D1%81%D1%81%D1%87%D0%B8%D1%82%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-kpi h_01JJVMXKAFZDPNXKAZCBQ27DBD=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01JJVMXKAFWA4D47MH7VSXKN14=filters-optional h_01JJVMXKAFSBXJ9EJJ16BF8H7Q=localization additional-information=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01JJVMXKAFFW2G3N7188DHYCB8=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01JJVMXKAF25YX092NE9DV9862=limitations" />

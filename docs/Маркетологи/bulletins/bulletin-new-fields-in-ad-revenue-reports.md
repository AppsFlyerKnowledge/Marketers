---
title: 'Бюллетень: Новые поля в отчетах о выручке от рекламы'
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-07-22T13:25:32Z'
  edited_at: '2026-10-19T14:38:44Z'
  id: 26907692192273
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/26907692192273
---

<Table>
  <tbody>
    <tr>
      <td>
        **Что нового?**
      </td>
      <td>
        В отчетах о выручке от рекламы появились новые поля.
      </td>
    </tr>
    <tr>
      <td>
        **Дата вступления в силу**
      </td>
      <td>
        19 сентября 2024 г.
      </td>
    </tr>
    <tr>
      <td>
        **Что вам нужно знать**
      </td>
      <td>
        Следующая таблица показывает, какие поля добавляются в какие отчеты. Определения и подробную информацию о каждом поле смотрите в <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary">словаре полей необработанных данных</Anchor>.

        | Отчет | Наименования полей API |
        | --- | --- |
        | <Anchor target="_blank" href="/marketers/ru/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Выручка от рекламы [прежняя версия]</Anchor> | * тип{"_"}взаимодействия<br />* пользовательские{"_"}данные<br />* идентификатор{"_"}пользователя{"_"}клиента<br />* тип{"_"}рекламы |
        | <Anchor target="_blank" href="/marketers/ru/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Выручка от рекламы [версионность]</Anchor> | * тип{"_"}взаимодействия<br />* пользовательские{"_"}данные<br />* идентификатор{"_"}пользователя{"_"}клиента<br />* тип{"_"}рекламы |
        | <Anchor target="_blank" href="/marketers/ru/docs/revenue-etl-reports#impression-level-report">Выручка от рекламы [SDK уровень показов]</Anchor> | * тип{"_"}взаимодействия<br />* пользовательские{"_"}данные<br />* идентификатор{"_"}пользователя{"_"}клиента<br />* тип{"_"}рекламы<br />* {"ad_revenue_custom_parameters"}<br />* версия{"_"}приложения<br />* версия{"_sdk"} |
      </td>
    </tr>
    <tr>
      <td>
        **Что вам нужно сделать**
      </td>
      <td>
        * В <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers#set-up-data-locker">настройках AppsFlyer Data Locker</Anchor> выберите новые поля для добавления в ваши отчеты.**Совет!** Если вы уже получаете поле, например customer\_user\_id, через настройки Data Locker по умолчанию, то для заполнения полей в отчетах о доходе от рекламы нужно добавить еще одно новое поле и сохранить настройки. Вы сможете отменить изменения позже.
        * Настройте свои системы бизнес-аналитики для приема и использования новых полей.
      </td>
    </tr>
  </tbody>
</Table>

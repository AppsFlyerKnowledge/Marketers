---
title: Интеграция Meta Quest (Oculus) с AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-12-08T10:10:00Z'
  edited_at: '2026-10-07T00:11:22Z'
  id: 11241398279569
  locale: ru
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/ru/articles/11241398279569
---
> **Кратко:** Интегрируйте ваше приложение Meta Quest (Oculus) с AppsFlyer, чтобы получать данные об атрибуции и событиях для ваших кампаний на Meta Quest (Oculus).

## Об атрибуции Meta Quest (Oculus)

ОС Meta Quest (Oculus) для игр работает на всех устройствах Meta Quest (Oculus).

Приложения, работающие на Meta Quest, могут интегрироваться с AppsFlyer через S2S API или SDK, чтобы получать данные об атрибуции и эффективности, о том, какие источники и кампании способствуют открытию приложения и событиям в приложении. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

## Процедуры интеграции

В следующей таблице перечислены задачи, необходимые для интеграции вашего приложения для Meta Quest (Oculus) в AppsFlyer.

<Table>
  <thead>
    <tr>
      <th>
        Выручка
      </th>
      <th>
        Действия
      </th>
      <th>
        Кто задействован
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Настройка приложения
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Создание аккаунта</Anchor>
        * <Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими правами</Anchor>
        * <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте ваше приложение для Meta Quest (Oculus) в AppsFlyer</Anchor>
      </td>
      <td>
        Маркетолог
      </td>
    </tr>
    <tr>
      <td>
        Интеграция SDK с вашим приложением (через S2S или SDK)
      </td>
      <td>
        Вы можете использовать два метода интеграции: S2S и SDK.

        Для метода S2S <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">интегрируйте API AppsFlyer</Anchor> в ваше приложение с командами для отправки в AppsFlyer отчетов о следующих событиях.

        * Первое открытие
        * События в приложении
        * Sessions (Сеансы)

        **Внимание**:

        * О первых открытиях приложения необходимо сообщать перед внутренними событиями и сеансами приложения.
        * Для параметра `device_ids` выберите тип `custom`.
          * Сгенерированный идентификатор `custom` для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">первых открытий</Anchor> должен совпадать с идентификатором <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">событий в приложении</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">сеансов</Anchor>.
          * Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить. Убедитесь, что при настройке API вы задали и сопоставили события для отправки в AppsFlyer.
          * Чтобы сообщать о вовлеченности в собственных медиа, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API вовлеченности по показам.</Anchor>

        Для метода SDK существует две версии: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unity">Unity</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unreal">Unreal</Anchor>.

        **Внимание**:

        Если у вас есть уже созданная база пользователей и поэтому вы хотите, чтобы первая сессия считалась сессией, а не установкой, разработчик может использовать метод `skipFirst=true`.
      </td>
      <td>
        Разработчик приложения
      </td>
    </tr>
    <tr>
      <td>
        Настройка кросс-платформенной целевой страницы
      </td>
      <td>
        **Рекомендуется:** Кроссплатформенная целевая страница, на которой запущен смарт-скрипт AppsFlyer, позволяет проводить атрибуцию из веба в приложение. Рекомендуется для случаев, когда ваша кампания продвигает приложение, которое также доступно на нескольких платформах, например Epic и Native PC.

        <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Узнайте о кросс-платформенных целевых страницах</Anchor>

        <Anchor target="_blank" href="/marketers/ru/docs/cross-platform-landing-pages-with-smart-script">Узнайте, как создать кросс-платформенную целевую страницу</Anchor>

        **Внимание**:

        Для Meta Quest необходимы следующие параметры:

        * **платформа**: quest
        * **QUEST\_APP\_ID**: идентификатор ID приложения в Quest Store.  
          Для Quest 2 это номер в URL-адресе магазина, например:

          ```http
          https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/
          ```

          где **XXXXXXXXXXXXXXXX** — уникальный идентификатор приложения.
        * **Подписка IAP**

        Следующие параметры не являются обязательными, но рекомендуются:

        * **Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>.**
        * **ad (объявление)**
        * **ad\_set (группа объявлений)**
        * **storefront\_redirect\_url**: полный URL-адрес витрины Oculus для вашего приложения, включая ваш **QUEST\_APP\_ID**. Например: `https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/`
      </td>
      <td>
        Маркетолог (может потребоваться помощь разработчика)
      </td>
    </tr>
    <tr>
      <td>
        Настройка ссылки
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor>
      </td>
      <td>
        Маркетолог
      </td>
    </tr>
    <tr>
      <td>
        Настройка отчета / просмотр данных
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#доступность-данных">Узнайте о доступности данных на дэшбордах и в отчетах</Anchor>
      </td>
      <td>
        Маркетолог/инженер по обработке и анализу данных
      </td>
    </tr>
  </tbody>
</Table>

<div id="traits-and-limitations" />

<Accordion title="Спецификации и ограничения">

| Специфика | Примечания |
| --- | --- |
| Тип периода подписки | В настоящее время не поддерживается |
| Данные о затратах | Импортируйте данные о расходах через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">Cost Import</Anchor>, используя метод загрузки файла **по электронной почте**. Вы также можете получать данные **через API** для Google, Meta и TikTok. |

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-meta-quest-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-meta-quest-oculus 01H7Z1MK9JHA4C5CB7YME4AJMA=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-meta-quest-oculus integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z1MK9JNRKAY9VNH5RTF03F=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z1MK9KXFY4XVPCDSJPQ26N=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

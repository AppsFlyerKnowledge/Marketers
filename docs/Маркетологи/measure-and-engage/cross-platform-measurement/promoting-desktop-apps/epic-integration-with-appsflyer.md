---
title: Интеграция Epic с AppsFlyer
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-04-03T07:18:07Z'
  edited_at: '2026-08-19T00:22:21Z'
  id: 14241298075921
  locale: ru
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ru/articles/14241298075921
---
> **Краткий обзор:** Интегрируйте свою игру Epic с AppsFlyer, чтобы получать данные об атрибуции и событиях для своих кампаний Epic. Интеграция Epic поддерживает атрибуцию и запись событий в приложении для игр Epic (другими словами, атрибуцию и запись на устройстве пользователя).

<div id="about-epic-game-attribution" />

## Об атрибуции игр Epic

Игры на платформе Epic могут интегрироваться с AppsFlyer через API (как S2S, так и client-side), чтобы получать данные атрибуции и измерения эффективности о том, какие источники и кампании обеспечивают открытие приложения и события в приложении. Маркетологи полагаются на эту информацию для измерения и оптимизации маркетинговой деятельности.

<div id="example-attribution-flow" />

### Пример процесса атрибуции

Ниже приведен пример процесса, в котором описаны наиболее важные этапы пути пользователя от вовлечения по рекламе до атрибуции. Он включает рекомендованную AppsFlyer кроссплатформенную целевую страницу. **Примечание:** Хотя мы рекомендуем использовать кроссплатформенную целевую страницу, вы также можете использовать прямые ссылки атрибуции.

<Image align="center" alt="Epic_journey.jpg" src="https://files.readme.io/c5807442cff142ceb4aa3c4d55628e75b37627a011ca531fa390e46ccc3e23b8-small-14241275857553.jpg" />

1. Маркетинговая точка взаимодействия: Клиенты взаимодействуют с вашим брендом через онлайн- или офлайн-точки взаимодействия. К ним могут относиться электронные сообщения и информационные бюллетени, социальные сети, мобильный Интернет и многое другое.
2. Целевая страница игры:  Целевая страница игры направляет клиентов на страницу вашей игры в Epic. Этот шаг важен для сбора UTM и других параметров URL-адреса для атрибуции клиентов с момента клика/установки к исходным медиа-источникам или вашим собственным медиа-источникам.  
   Целевая страница также полезна, потому что на ней есть ссылки на различные платформы, поддерживаемые вашей игрой. Например, на целевой странице можно разместить ссылки на страницы Xbox, магазина Microsoft и Steam.
3. Страница приложения в Epic: Это страница витрины Epic, на которой размещена ваша игра Epic, доступная клиентам для загрузки.
4. Установка игры: Пользователь устанавливает игру, запуская атрибуцию и запись событий в приложении и сессий.

<div id="integration-procedures" />

## Процедуры интеграции

В следующей таблице перечислены задачи, необходимые для интеграции вашей игры Epic с AppsFlyer.∑

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
        Кто участвует
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
        * <Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими разрешениями</Anchor>
        * <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте свою игру Epic в AppsFlyer</Anchor>
      </td>
      <td>
        Маркетолог
      </td>
    </tr>
    <tr>
      <td>
        Интеграция API с вашим приложением (через S2S или client-side)
      </td>
      <td>
        Вы можете использовать два метода интеграции: S2S и client-side.

        Для метода S2S:

        <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">Интегрируйте Epic API AppsFlyer</Anchor> в свое приложение с помощью команд, чтобы отправлять в AppsFlyer следующие события.

        * Первое открытие
        * События в приложении
        * Sessions (Сеансы)

        **Внимание**:

        * О первых открытиях приложения необходимо сообщать перед внутренними событиями и сеансами приложения.
        * Для параметра `device_ids` выберите тип `custom` или `epicid`.
          * Значение `custom` или `epicid` для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">первых открытий</Anchor> должно совпадать с идентификатором ID ваших <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">событий в приложении</Anchor> и с идентификатором ID <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">сессий</Anchor> .
        * Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить.
        * Чтобы сообщать о взаимодействиях с собственными каналами, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API взаимодействия по показам.</Anchor>

        Для метода client-side существует три версии: нативный <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">C++</Anchor>, <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unreal-epic-sample-app">Unreal</Anchor> и <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-epic-sample-app">Unity</Anchor>.

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
        **Рекомендуется:** Кроссплатформенная целевая страница, на которой запущен смарт-скрипт AppsFlyer, позволяет проводить атрибуцию из веба в приложение. Рекомендуется для случаев, когда ваша кампания продвигает приложение, которое также доступно на нескольких платформах, например Epic и Steam.

        <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Узнайте о кросс-платформенных целевых страницах</Anchor>

        <Anchor target="_blank" href="/marketers/ru/docs/cross-platform-landing-pages-with-smart-script">Узнайте, как создать кросс-платформенную целевую страницу</Anchor>

        **Внимание**:

        Для Epic необходимы следующие параметры:

        * **platform**  
          epic
        * **app\_id**  
          ID приложения страницы игры в магазине Epic.

          Уникальный идентификатор игры можно найти в консоли разработчика Epic. Например:

          ```http
          https://store.epicgames.com/en-us/p/YOUR-GAME-ID
          ```
        * **медиа-источник**

        Следующие параметры не являются обязательными, но рекомендуются:

        * **campaign (кампания)**
        * **ad (объявление)**
        * **ad\_set (группа объявлений)**
        * **storefront\_redirect\_url**  
          Полный URL-адрес вашей витрины Epic для вашего приложения, включая **app\_id**.  
          Например: `https://store.epicgames.com/en-us/p/12345678/`
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
        Если вы не используете кроссплатформенную целевую страницу, вы можете создать прямые ссылки атрибуции для размещения за рекламой.

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
        Маркетолог/Инженер по обработке и анализу данных
      </td>
    </tr>
  </tbody>
</Table>

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

### Удаление данных AppsFlyer при удалении приложения

Чтобы удалить все данные AppsFlyer SDK при удалении приложения, попросите разработчика выполнить указанные [здесь](https://dev.appsflyer.com/hc/docs/epic-vanilla#deleting-appsflyer-data-on-uninstall) действия.

<div id="traits-and-limitations" />

## Спецификации и ограничения

| Специфика | Примечание |
| --- | --- |
| Обязательный | В настоящее время не поддерживается |
| Данные о затратах | Данные о расходах необходимо отправлять через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">Ad Spend Ingestion</Anchor> методом загрузки файла по электронной почте. |

<div id="see-also" />

> 📄 **Смотрите также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-steam-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B8%D0%B3%D1%80-epic 01H7Z1F3SE03BXJD0WAJV8RE7Q=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B8%D0%B3%D1%80-epic flow=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H7Z1F3SETVXQKRQ71YAJACY3=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z1F3SF4J2WJ2Y6QG3VGGVK=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 removing-appsflyer-data-when-uninstalling-the-app=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%BF%D1%80%D0%B8-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01J3349MAA4J231B6FJ74V3PTB=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%BF%D1%80%D0%B8-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HF9WA5FJ6P4C357ZE231GMR0=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HE7T4JX3RX3SZW2VPW5ZZY7E=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

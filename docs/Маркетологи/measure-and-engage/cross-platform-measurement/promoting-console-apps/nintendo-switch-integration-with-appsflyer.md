---
title: Интеграция Nintendo Switch с AppsFlyer
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
  created_at: '2023-05-02T10:50:43Z'
  edited_at: '2026-10-19T14:18:32Z'
  id: 14988397864593
  locale: ru
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/ru/articles/14988397864593
---
> **Краткий обзор:** Интегрируйте свою игру или приложение для Nintendo Switch с AppsFlyer, чтобы получать данные об атрибуции и событиях для своих кампаний на Nintendo Switch.

## Об атрибуции для Nintendo Switch

Приложения, работающие на Nintendo Switch, могут интегрироваться с AppsFlyer через S2S API, чтобы получать данные атрибуции и измерения эффективности о том, какие источники и кампании приводят к открытию приложения и событиям в приложении. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

### Пример процесса атрибуции

Ниже приведен пример процесса, в котором описаны наиболее важные этапы пути пользователя от вовлечения по рекламе до атрибуции. Он включает рекомендованную AppsFlyer кроссплатформенную целевую страницу. **Примечание**: Хотя мы рекомендуем использовать кросс-платформенную целевую страницу, вы также можете использовать прямые ссылки атрибуции

![User_windows.jpg](https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg)

1. <span id="marketing-touchpoint"></span>Маркетинговая точка взаимодействия: Клиенты взаимодействуют с вашим брендом через маркетинговые точки взаимодействия офлайн или онлайн. Это может быть рассылка по электронной почте, социальные сети, мобильный интернет и многое другое.
2. Целевая страница игры: Целевая страница игры направляет клиентов на страницу загрузки приложения. Этот шаг важен для сбора UTM и других параметров URL, чтобы атрибутировать клиентов после клика/установки к исходным или вашим собственнным медиа-источникам.  
   Целевая страница полезна еще и тем, что на ней находятся ссылки на различные платформы, на которых доступна ваша игра. Например, на целевой странице можно разместить ссылки на страницы Xbox, магазина Microsoft и Steam.
3. Страница приложения: Это URL-адрес страницы вашего приложения Nintendo Switch, на которой размещено ваше приложение для загрузки клиентами.
4. Установка игры: Пользователь устанавливает игру, запуская атрибуцию и запись внутренних событий приложения и сессий.

## Процедуры интеграции

В таблице ниже перечислены задачи, необходимые для интеграции вашего приложения Nintendo Switch с AppsFlyer.

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
        * <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте приложение Nintendo Switch в AppsFlyer</Anchor>
      </td>
      <td>
        Маркетолог
      </td>
    </tr>
    <tr>
      <td>
        Интеграция API с вашим приложением (через S2S)
      </td>
      <td>
        <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">Интегрируйте API AppsFlyer</Anchor> в свое приложение с помощью команд, чтобы сообщать в AppsFlyer о следующих событиях.

        * Первое открытие
        * События в приложении
        * Sessions (Сеансы)

        **Внимание**:

        * О первых открытиях приложения необходимо сообщать перед внутренними событиями и сеансами приложения.
        * Для параметра `device_ids` выберите тип `custom`.
          * Сгенерированный идентификатор `custom` для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">первых открытий</Anchor> должен совпадать с идентификатором <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">событий в приложении</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">сеансов</Anchor>.
          * Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить. Убедитесь, что при настройке API вы задали и сопоставили события для отправки в AppsFlyer.

        Чтобы сообщать о взаимодействиях с собственными каналами, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API взаимодействия по показам.</Anchor>
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

        Для Nintendo Switch необходимы следующие параметры:

        * **platform**  
          switch
        * **nintendo\_app\_id**  
          ID страницы приложения.  

          Вы можете найти свой уникальный идентификатор приложения, скопировав его из строки URL-адреса или перейдя по адресу <Anchor target="_blank" href="https://www.nintendo.com/store/products/octopath-traveler-ii-switch/">https://www.nintendo.com/store/products/</Anchor> и выполнив поиск своей игры. Например:

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```

          где **app-id** — ваш уникальный идентификатор приложения.
        * **медиа-источник**

        Следующие параметры не являются обязательными, но рекомендуются:

        * **campaign (кампания)**
        * **ad (объявление)**
        * **ad\_set (группа объявлений)**
        * **storefront\_redirect\_url**  
          Полный URL-адрес витрины Nintendo Switch для вашего приложения, включая ваш **nintendo\_app\_id**.  
          Например:

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```
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
        Маркетолог/инженер по обработке и анализу данных
      </td>
    </tr>
  </tbody>
</Table>

<div id="traits-and-limitations" />

<Accordion title="Спецификации и ограничения">

| Специфика | Специфика |
| --- | --- |
| Обязательный | В настоящее время не поддерживается |
| Данные о затратах | Данные о расходах должны быть отправлены через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">Ad Spend Ingestion</Anchor> с использованием метода отправки файла для загрузки по электронной почте. |

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-nintendo-switch-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-nintendo-switch 01H7Z1HPD0AB0VP6REMBF2HCR8=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-nintendo-switch example-attribution-flow=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HP1QDGDAXV0Y7MVJYHW3H4SQ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z1HPD0VAMPEHBPN8MAT3ST=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z1HPD0CS7CTX2KS2RVD3VA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

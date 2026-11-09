---
title: Интеграция Steam с AppsFlyer
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
  created_at: '2022-12-08T10:02:09Z'
  edited_at: '2026-10-07T00:11:45Z'
  id: 11241130508433
  locale: ru
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ru/articles/11241130508433
---
> **Краткий обзор:** Интегрируйте игру/приложение Steam с AppsFlyer, чтобы получать данные об атрибуции и событиях для своих кампаний в Steam. Интеграция Steam поддерживает атрибуцию и запись внутренних событий приложений Steam на устройстве пользователя Steam.

<div id="about-steam-attribution" />

## Об атрибуции Steam

Steam работает на устройствах Windows и Mac, Steam Deck и других устройствах со Steam OS.

Приложения, работающие на Steam, могут интегрироваться с AppsFlyer через S2S API или SDK, чтобы получать данные об атрибуции и эффективности, о том, какие источники и кампании способствуют открытию приложения и внутренним событиям приложения. Маркетологи полагаются на эти данные для измерения и оптимизации маркетинговой деятельности.

<div id="example-attribution-flow" />

### Пример процесса атрибуции

Ниже приведен пример процесса, в котором описаны наиболее важные этапы пути пользователя от вовлечения по рекламе до атрибуции. Он включает рекомендованную AppsFlyer кроссплатформенную целевую страницу. **Примечание:** Хотя мы рекомендуем использовать кроссплатформенную целевую страницу, вы также можете использовать прямые ссылки атрибуции

<Image align="center" alt="Steam_user_journey.jpg" src="https://files.readme.io/4979821043af1ed3e662b55c84df10a17a863e79084d050c478fa31767ed8eaa-51473918246929.jpg" />

1. Маркетинговая точка взаимодействия: Клиенты взаимодействуют с вашим брендом через маркетинговый точки взаимодействия офлайн или онлайн. К ним могут относиться электронные сообщения и информационные бюллетени, социальные сети, мобильный Интернет и многое другое.
2. Целевая страница игры: Целевая страница игры направляет клиентов на страницу вашей игры в Steam. Этот шаг важен для сбора UTM и других параметров URL-адреса для атрибуции клиентов с момента клика/установки к исходным медиа-источникам или вашим собственным медиа-источникам.  
   Целевая страница также полезна, потому что на ней есть ссылки на различные платформы, поддерживаемые вашей игрой. Например, на целевой странице можно разместить ссылки на Xbox, магазин Microsoft и страницу Steam.  
   <Image align="center" alt="awesome_game.png" src="https://files.readme.io/37cabff10a2e0a721b4d2901e7df47f53a7dedff25bdac80b97003b60eaef430-51473918248465.png" />
3. <span id="marketing-touchpoint"></span>Страница приложения в Steam: Это страница вашего магазина Steam, на которой размещено ваше приложение Steam, которое клиенты могут загрузить.
4. Установка игры: Пользователь устанавливает игру, запуская атрибуцию и запись внутренних событий приложения и сессий.

<div id="integration-procedures" />

## Процедуры интеграции

В следующей таблице перечислены задачи, необходимые для интеграции приложения Steam с AppsFlyer.

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
        * <Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими правами</Anchor>
        * <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте свое приложение Steam в AppsFlyer</Anchor>
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
        Вы можете использовать два метода интеграции: S2S и SDK.

        Для метода S2S,  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">интегрируйте AppsFlyer API</Anchor> в ваше приложение, добавив команды для отправки в AppsFlyer отчетов о следующих событиях.

        * Первое открытие
        * События в приложении
        * Sessions (Сеансы)

        **Внимание**:

        * О первых открытиях приложения необходимо сообщать перед внутренними событиями и сеансами приложения.
        * В качестве параметра `platform` выберите `steam`.
        * В качестве параметра `device_ids` выберите `custom`.
          * Сгенерированный идентификатор `custom` для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">первого открытия</Anchor> должен совпадать с идентификатором <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">событий в приложении</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">сеансов</Anchor>.
        * Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить. Убедитесь, что при настройке API вы задали и сопоставили события для отправки в AppsFlyer.
        * Чтобы сообщать о взаимодействиях с собственными каналами, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API взаимодействия по показам.</Anchor>

        Для метода SDK существует три версии: нативный <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/steam-vanilla">C++</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-steam">Unreal</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-steam">Unity</Anchor>.

        **Внимание**:

        Если у вас есть уже созданная база пользователей и поэтому вы хотите, чтобы первая сессия считалась сессией, а не установкой, разработчик может использовать метод `skipFirst=true`.
      </td>
      <td>
        Разработчик приложений
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

        **Примечание**.

        Для Steam необходимы следующие параметры:

        * **платформа**: steam
        * **steam\_app\_id**: идентификатор страницы приложения.

          Вы можете найти свой уникальный идентификатор приложения, скопировав его из строки URL-адреса или перейдя по адресу <Anchor target="_blank" href="https://steamdb.info/">https://steamdb.info/</Anchor> и выполнив поиск своей игры. Например,

          ```http
          https://store.steampowered.com/app/12345678/
          ```

          где **12345678** — ваш уникальный идентификатор приложения.
        * **Подписка IAP**

        Следующие параметры не являются обязательными, но рекомендуются:

        * **Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>.**
        * **ad (объявление)**
        * **ad\_set (группа объявлений)**
        * **storefront\_redirect\_url**: полный URL-адрес витрины вашего приложения в Steam, включая ваш **steam\_app\_id**. Например: `https://store.steampowered.com/app/12345678/`
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

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

### Удаление данных AppsFlyer при удалении приложения

Чтобы удалить все данные AppsFlyer SDK при удалении приложения, попросите разработчика выполнить указанные [здесь](https://dev.appsflyer.com/hc/docs/steam-vanilla#deleting-appsflyer-data-on-uninstall) действия.

<div id="traits-and-limitations" />

## Ограничения и особенности

| Специфика | Примечание |
| --- | --- |
| Тип периода подписки | В настоящее время не поддерживается |
| Данные о затратах | Импортируйте данные о расходах через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">Cost Import</Anchor>, используя метод загрузки файла **по электронной почте**. Вы также можете получать данные **через API** для Google, Meta или TikTok. |

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Атрибуция платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-steam-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-steam 01H7Z1DJRW1KPJQ4CZ6T85ASRK=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-steam flow=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H7Z1DJRWHB8TQC15WW4FVSHG=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z1DJRWX54DN2SNS21GPGXB=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 removing-appsflyer-data-when-uninstalling-the-app=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%BF%D1%80%D0%B8-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01J3349MAA4J231B6FJ74V3PTB=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%BF%D1%80%D0%B8-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F traits-and-limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HDEHMH0HF201TH4XDW691STH=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HDP1K6FDDEED5P2WNESST7GE=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

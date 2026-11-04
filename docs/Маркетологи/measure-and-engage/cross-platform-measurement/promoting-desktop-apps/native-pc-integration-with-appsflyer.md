---
title: Интеграция Native PC с AppsFlyer
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
  created_at: '2023-06-20T05:52:13Z'
  edited_at: '2026-10-07T00:11:43Z'
  id: 16308237781649
  locale: ru
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ru/articles/16308237781649
---
> **Краткий обзор.** Интегрируйте свою игру или приложение для ПК с AppsFlyer, чтобы получать данные об атрибуции и событиях для своих кампаний на ПК. Интеграция с Native PC поддерживает атрибуцию и запись событий в приложении для ПК (другими словами, атрибуция и запись действий на компьютере пользователя).

<div id="about-native-pc-attribution" />

## Об атрибуции Native PC

Native PC работает на устройствах под управлением Windows за счет установки файлов с расширением .EXE или .MSI.

Это отличается от <Anchor target="_blank" href="/marketers/ru/docs/windows-sdk-integration-for-developers">AppsFlyer Windows SDK 2.4.1</Anchor>, который работает с установками из Microsoft App Store, Windows Phones и UWP.

Приложения, работающие на ПК, могут интегрироваться с AppsFlyer через S2S API или SDK, чтобы получать данные об атрибуции и измерениях эффективности, о том, какие источники и кампании способствуют открытию приложения и событиям в приложении. Маркетологи полагаются на эту информацию для измерения и оптимизации маркетинговой деятельности.

<div id="example-attribution-flow" />

### Пример процесса атрибуции

Ниже приведен пример процесса, в котором описаны наиболее важные этапы пути пользователя от вовлечения по рекламе до атрибуции. В него входит рекомендованная AppsFlyer кроссплатформенная целевая страница. **Примечание:** Хотя мы рекомендуем использовать кроссплатформенную целевую страницу, вы также можете использовать прямые ссылки атрибуции

![User_windows.jpg](https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg)

1. <span id="marketing-touchpoint"></span>Маркетинговая точка взаимодействия: Клиенты взаимодействуют с вашим брендом через маркетинговый точки взаимодействия офлайн или онлайн. Это может быть рассылка по электронной почте, социальные сети, мобильный интернет и многое другое.
2. Целевая страница игры: Целевая страница игры направляет клиентов на страницу загрузки приложения. Этот шаг важен для сбора UTM и других параметров URL-адреса для атрибуции клиентов с момента клика/установки к исходным медиа-источникам или вашим собственным медиа-источникам.  
   Целевая страница также полезна, потому что на ней есть ссылки на различные платформы, поддерживаемые вашей игрой. Например, на целевой странице можно разместить ссылки на страницы Xbox, магазина Microsoft и Steam.
3. Страница приложения: Это URL-адрес страницы приложения для ПК, на которой размещено ваше приложение для загрузки клиентами.
4. Установка игры: Пользователь устанавливает игру, запуская атрибуцию и запись внутренних событий приложения и сессий.

<div id="integration-procedures" />

## Процедуры интеграции

В следующей таблице перечислены задачи, необходимые для интеграции вашего приложения для ПК с AppsFlyer.

**Внимание**: Добавление членов команды и настройка отчетов в Data Locker не обязательны.

| Выручка | Действия | Кто участвует |
| --- | --- | --- |
| Настройка приложения | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Создание аккаунта</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими правами</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте свое приложение для ПК в AppsFlyer</Anchor></li></ul> | Маркетолог |
| Интеграция SDK с вашим приложением (через S2S или SDK) | Вы можете использовать два метода интеграции: S2S и SDK.<br /><br />Для метода S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">интегрируйте AppsFlyer API</Anchor> в свое приложение с командами для отправки в AppsFlyer отчетов о следующих событиях.<ul><li>Первое открытие</li><li>События в приложении</li><li>Sessions (Сеансы)</li></ul>**Внимание**:<ul><li>О первых открытиях приложения необходимо сообщать перед внутренними событиями и сеансами приложения.</li><li>Для параметра `device_ids` выберите тип `custom`.<ul><li>Сгенерированный идентификатор `custom` для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">первых открытий</Anchor> должен совпадать с идентификатором <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">событий в приложении</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">сеансов</Anchor>.</li></ul></li><li>Отправляйте события с помощью API. Сообщите разработчику, какие события нужно отправить. Убедитесь, что при настройке API вы задали и сопоставили события для отправки в AppsFlyer.</li><li>Чтобы сообщать о взаимодействиях с собственными каналами, интегрируйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API взаимодействия по показам.</Anchor></li></ul>Для метода SDK существует три версии: нативный <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/nativepc-vanilla">C++</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-nativepc">Unreal</Anchor> и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-nativepc">Unity</Anchor>.<br /><br />**Внимание**:<br /><br />Если у вас уже есть база пользователей и вы хотите, чтобы первая сессия считалась сессией, а не установкой, разработчик может использовать метод `skipFirst=true`. | Разработчик приложений |
| Настройка кросс-платформенной целевой страницы | **Рекомендуется:** Кроссплатформенная целевая страница, на которой запущен смарт-скрипт AppsFlyer, позволяет проводить атрибуцию из веба в приложение. Рекомендуется для случаев, когда ваша кампания продвигает приложение, которое также доступно на нескольких платформах, например Epic и Steam.<br /><br /><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Узнайте о кроссплатформенных целевых страницах</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ru/docs/cross-platform-landing-pages-with-smart-script">Узнайте, как создать кросс-платформенную целевую страницу</Anchor><br /><br />Для Native PC необходимы следующие параметры:<ul><li>**ID приложения**</li><li>**app\_id**<br />Для использования AppsFlyer требуется идентификатор приложения. Для нативных приложений для ПК не существует определенных правил для идентификаторов приложений, поэтому ваш разработчик может выбрать и создать любой идентификатор приложения, который он захочет. **Рекомендуется:** Выберите значимый для вас идентификатор, который, однако, вряд ли будет использоваться приложениями. Например: `app-name-is-the-best`.</li><li>**media\_source (медиа-источник)**</li><li>**af\_campaign\_id**</li><li>**платформа**<br />Пример: Steam</li></ul>Следующие параметры не являются обязательными, но рекомендуются:<ul><li>**campaign (кампания)**</li><li>**ad (объявление)**</li><li>**ad\_set (группа объявлений)**</li></ul> | Маркетолог (может потребоваться помощь разработчика) |
| Настройка ссылки | <ul><li>Если вы не используете кросс-платформенную целевую страницу, вы можете создать прямые ссылки атрибуции для размещения в объявлениях.</li><li>Специфика</li><li><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-direct-attribution-links">Узнайте, как создавать прямые ссылки атрибуции</Anchor></li></ul> | Маркетолог |
| Настройка отчета/просмотр данных | <Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts#доступность-данных">Узнайте о доступности данных на дэшбордах и в отчетах</Anchor> | Маркетолог / инженер по обработке и анализу данных |

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

### Удаление данных AppsFlyer при удалении приложения

Чтобы удалить все данные AppsFlyer SDK при удалении приложения, попросите разработчика выполнить указанные [здесь](https://dev.appsflyer.com/hc/docs/nativepc-vanilla#deleting-appsflyer-data-on-uninstall) действия.

<div id="traits-and-limitations" />

## Ограничения и особенности

| Специфика | Примечания |
| --- | --- |
| Обязательный | В настоящее время не поддерживается |
| Данные о затратах | Импортируйте данные о расходах через <Anchor target="_blank" href="/marketers/ru/docs/import-cost-data">Cost Import</Anchor>, используя метод загрузки файла **по электронной почте**. Вы также можете получать данные **через API** для Google, Meta и TikTok. |

<div id="see-also" />

> 📄 **См. также**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/ru/docs/ctv-pc-and-console-platform-attribution-concepts">Обзор платформ CTV, ПК и консолей</Anchor>

<div data-zendesk-anchors="about-steam-attribution=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-native-pc 01H7Z19FJ5J1CB4ESE55Z32C1C=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-native-pc flow=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H7Z19FJ5R869054GDRKHTBJ8=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H7Z19FJ5KKPJ88KAQM49FNVA=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 removing-appsflyer-data-when-uninstalling-the-app=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%BF%D1%80%D0%B8-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01J3349MAA4J231B6FJ74V3PTB=%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer-%D0%BF%D1%80%D0%B8-%D1%83%D0%B4%D0%B0%D0%BB%D0%B5%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F traits-and-limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HF9W8YG149TMQE1F57BG0ZS7=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HE0T79YSNWGB3W4S7WEBW1B5=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

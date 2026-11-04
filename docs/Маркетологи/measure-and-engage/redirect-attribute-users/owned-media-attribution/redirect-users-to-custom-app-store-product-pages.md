---
title: Перенаправление на настраиваемые страницы продукта в магазине приложений
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - OneLink
  created_at: '2021-08-26T07:25:53Z'
  edited_at: '2026-08-18T00:36:13Z'
  id: 4406217556625
  locale: ru
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ru/articles/4406217556625
---
> **Краткий обзор.** Перенаправляйте пользователей на настраиваемые листинги вашего приложения в Google Play или на настраиваемые страницы продукта в App Store. Используйте данные AppsFlyer о настраиваемых страницах в магазинах для оптимизации кампаний.

<div id="overview" />

## Обзор

Настраиваемые листинги в магазине Google Play и настраиваемые страницы продуктов в Apple App Store (далее в статье они называются настраиваемыми страницами продуктов в магазине) позволяют владельцам приложений создавать дополнительные версии своих страниц в Google Play и  App Store, демонстрирующие различные функции или контент приложения. Настраиваемые страницы продуктов в магазине могут содержать рекламный текст, скриншоты и превью, которые отличаются от тех, что представлены на стандартной странице магазина.

В Google Play можно создать до 50 настраиваемых страниц. В App Store до 35.

Вы можете использовать ссылки для конкретных платформ или URL-адреса OneLink AppsFlyer, чтобы перенаправлять пользователей на такие настраиваемые страницы продукта в магазинах и создавать отдельные контекстные пути для различных целевых аудиторий.

Данные, связанные с настраиваемыми страницами продукта в магазинах, доступны на дэшборде AppsFlyer и в отчетах с сырыми данными, как описано ниже. Их можно использовать для проведения A/B тестов и оптимизации кампаний и страниц продукта.

<div id="data-availability" />

## Доступность данных

<div id="dashboard" />

<Accordion title="Дэшборд">

Агрегированные данные по настраиваемым страницам продукта в App Store доступны на обзорном дэшборде. Для настраиваемого листинга в магазине Google Play скоро будет доступно.

**Для просмотра этих данных**:

* На обзорном дэшборде добавьте параметр группировки **Страница продукта в магазине приложений**.  
  На графиках и в таблицах дэшборда появятся данные о настраиваемых страницах продукта.

</Accordion>

<div id="raw-data" />

<Accordion title="Сырые данные">

Сырые данные доступны через <Anchor target="_blank" href="/marketers/ru/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">инструменты отчетности AppsFlyer</Anchor>.

В отчетах поле `store_product_page` показывает, на какую настраиваемую страницу был перенаправлен конкретный пользователь.

</Accordion>

<div id="setup" />

## Настройки

<div id="google-play" />

<Accordion title="Google Play">

Настроить перенаправление на настраиваемую страницу в Google Play вы можете одним из способов:

* Через пользовательский интерфейс OneLink.
* Добавьте параметр `af_android_store_csl` в URL-адреса OneLink или одноплатформенные ссылки атрибуции со значением настраиваемого листинга в магазине, который вы выбрали в Google Console. Например: `af_android_store_csl=abc123`

<span id="use-the-onelink-ui-google-play"></span>**Примечание:** Из-за системных изменений в некоторых браузерах, включая Google Chrome, использование перенаправления на пользовательский листинг в магазине может привести к открытию веб-версии Google Play с отображением пользовательского листинга (вместо версии в приложении).

<div id="use-the-onelink-uigoogle-play" />

#### Пользовательский интерфейс OneLink — Google Play

Необходимые условия:

* Настраиваемый листинг в магазине, созданный в Google Console.  
  **Примечание**. В Google Console настраиваемый листинг должен быть настроен через уникальный параметр URL.
* <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Шаблон OneLink</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">Настраиваемая ссылка OneLink.</Anchor>

**Чтобы добавить перенаправление на настраиваемый листинг продукта в настраиваемую ссылку OneLink**:

1. В настройках ссылки OneLink перейдите в раздел **Deep linking & redirections** (Диплинкинг и перенаправления).
2. Прокрутите вниз до раздела **When app isn’t installed** (Если приложение не установлено).  
   ![android_cpp.png](https://files.readme.io/d354feb4d47171b14f0612011b7a52b579bd9062a87544095df226ba58c57ec6-11591784334865.png)
3. Для Android убедитесь, что для опции **Перенаправлять на** установлено значение Google Play.
4. В текстовом поле **Настраиваемый листинг в магазине** введите значение, которое вы определили для уникального параметра URL листинга в Google Console. Например: abc123
5. Нажмите **Обновить ссылку**.
6. [Рекомендуется] Протестируйте ссылку в разных браузерах Android, чтобы убедиться, что она работает так, как ожидается.

</Accordion>

<div id="app-store" />

<Accordion title="App Store">

Задать перенаправления на настраиваемую страницу продукта в App Store можно двумя способами:

* Через пользовательский интерфейс OneLink.
* Добавив параметр `af_ios_store_cpp` в URL-адреса OneLink или ссылки атрибуции для конкретных платформ и указав идентификатор настраиваемой страницы продукта в качестве его значения. Пример: `af_ios_store_cpp=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

<div id="use-the-onelink-uiapp-store" />

#### Пользовательский интерфейс OneLink — App Store

Необходимые условия:

* Настраиваемая страница продукта создана в App Store Connect.
* <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Шаблон OneLink</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">Настраиваемая ссылка OneLink.</Anchor>

**Чтобы добавить перенаправление на настраиваемую страницу продукта в настраиваемую ссылку OneLink**:

1. В настройках ссылки OneLink перейдите в раздел **Deep linking & redirections** (Диплинкинг и перенаправления).
2. Прокрутите вниз до раздела **When app isn’t installed** (Если приложение не установлено).  
   ![ios_cpp.png](https://files.readme.io/76f6b46644efc478dc27cb373b3de4a4a80600936db5d7e6725fdb4b9182f6bb-11591824202641.png)
3. Для iOS: убедитесь, что для параметра **Redirect to** (Куда перенаправлять) задано значение App Store.
4. В текстовом поле **Custom product page** (Настраиваемая страница продукта) укажите идентификатор нужной страницы (ppid) из App Store Connect. Например: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
5. Нажмите **Обновить ссылку**.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Ограничения и особенности">

| Специфика | Заметки |
| --- | --- |
| Браузеры | <ul><li>Настраиваемые листинги в магазине Google Play не поддерживаются в Naver Blog.</li></ul> |

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01J851YT6WHWEA6RTBFP1S9FT8=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 data-availability=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01J851YT6XG2A6VETQ3XSNZWVX=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01J851YT6XXTZVMPQFK4YDMACC=dashboard h_01J851YT6XHR6Y3KB30AMMGZXS=raw-data setup=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01J851YT6XWVEMRG9R5DYKJ70N=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01J851YT6X21X787WNDFGAW5EZ=google-play use-the-onelink-ui%E2%80%94google-play=use-the-onelink-ui-google-play h_01J851YT6XSVG70DX841NKVGDY=%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D0%B9-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81-onelink-googleplay h_01J851YT6XYQG2FGWBEPAJ686X=app-store use-the-onelink-ui%E2%80%94app-store=%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D0%B9-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81-onelink-appstore h_01J851YT6XJ9NBK5KKHV1Y07M4=%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D0%B9-%D0%B8%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81-onelink-appstore h_01J851YT6XE6P2FDE9KEMH9SYN=traits-and-limitations" />

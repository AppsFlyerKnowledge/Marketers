---
title: Внедрение кода смарт-баннеров на сайт (для маркетологов)
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developer
    - Developers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-10T11:25:54Z'
  edited_at: '2026-08-18T00:36:40Z'
  id: 4416119954705
  locale: ru
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ru/articles/4416119954705
---
> **Краткий обзор.** Добавьте код смарт-баннеров на свой сайт, чтобы конвертировать посетителей вашего сайта в пользователей мобильного приложения.

> 📘 **Примечание**
>
> Веб SDK AppsFlyer для смарт-баннеров v1 устарел с 8 ноября 2023 года. Для показа смарт-баннеров на вашем сайте необходимо обновить версию до v2. <Anchor target="_blank" href="/marketers/ru/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">Узнать больше</Anchor>

## Внедрение кода веб-сайта

Эта статья предназначена для маркетологов, которые хотят внедрить код смарт-баннеров на свой сайт при помощи одного из следующих инструментов:

* Google Tag Manager (GTM)
* Native  Google Tag Manager  Adobe Launch Tag Manager
* Shopify
* Wix
* Squarespace
* WordPress

Как добавить код на свой сайт через другие платформы или внести изменения в код в зависимости от задачи (например, чтобы добавить параметры, настроить диплинкинг, скрыть баннер или интегрировать PBA со смарт-баннерами, читайте в статье <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Внедрение кода смарт-баннеров на сайт (для разработчиков)</Anchor>.

**Чтобы внедрить код смарт-баннеров на свой сайт**:

1. Чтобы получить код смарт-баннеров, следуйте <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">инструкциям на веб-сайте</Anchor>.
2. Чтобы внедрить код на свой веб-сайт, используйте следующие инструкции для конкретной платформы:

<Accordion title="https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png">

**Чтобы внедрить код через Google Tag Manager**:

1. В GTM создайте новый тег.
2. Присвойте тегу имя, нажмите **Tag Configuration** (Конфигурация тега) и выберите **Custom HTML** (Пользовательский HTML).
3. Вставьте фрагмент кода смарт-баннера в поле HTML. Во фрагменте кода вместо YOUR-BANNER-KEY укажите фактический ключ баннера.
4. Выберите **Triggering** (Запуск) и создайте новый триггер, нажав значок с плюсом в правом верхнем углу экрана.
5. Присвойте триггеру имя, нажмите **Trigger Configuration** (Конфигурация триггера) и выберите **Page View** (Просмотр страницы).
6. Если нужно, чтобы баннер показывался на всех страницах, выберите **All Page Views** (Все просмотры страниц). Если нужно, чтобы баннер показывался на определенных страницах, выберите **Some Page Views** (Некоторые просмотры страниц) и определите условие срабатывания тэга. Более подробные сведения о триггерах можно найти в <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">документации GTM</Anchor>.
7. Нажмите **Save** (Сохранить) в правом верхнем углу.
8. Вернитесь на экран настройки тэга. Проверьте, все ли готово, и нажмите **Save** (Сохранить) в правом верхнем углу.
9. Опубликуйте свой контейнер GTM.

</Accordion>

<div id="adobe-launch-tag-manager" />

<Accordion title="Native Google Tag Manager Adobe Launch Tag Manager">

**Чтобы внедрить код через Adobe Launch Tag Manager**:

<div id="step-1-create-a-property-in-adobe-experience-cloud" />

<Accordion title="Шаг 1: Создание свойства в Adobe Experience Cloud">

**Чтобы создать свойство (тег), в котором будет размещен код смарт-баннеров**:

1. Перейдите в раздел **Adobe Experience Cloud** > **Launch** (Запуск).
2. В разделе **Adobe Experience Cloud Launch** (Запуск Adobe Experience Cloud) нажмите **Go to Launch** (Перейти к запуску).
3. Нажмите **New Property** (Новое свойство).
4. Дайте свойству название.
5. В разделе **Platform** (Платформа) выберите **Web** (Веб-сайт).
6. Укажите домен своего сайта.
7. Нажмите **Сохранить**.

</Accordion>

<div id="step-2-add-smart-banners-code-to-the-adobe-launch-property" />

<Accordion title="Шаг 2: Добавьте код смарт-баннеров в свойство Adobe Launch">

**Чтобы добавить код смарт-баннеров в тег**:

1. На странице **My web property** (Мой веб-ресурс) выберите вкладку **Rules** (Правила).
2. Дайте правилу название. Рекомендуется: **Смарт-баннеры AppsFlyer**.
3. В разделе **If** (Если) под пунктом **EVENTS** (События) нажмите **+Add** (Добавить).
   * В разделе **Event Type** (Тип события) выберите **Core - DOM Ready** (Основное, с поддержкой DOM).
   * Нажмите **Keep Changes** (Сохранить изменения).
4. В разделе **Then** (Тогда) в пункте **Actions** (Действия) нажмите **+Add** (Добавить).
   * В разделе **Action Type** (Тип действия) > **Custom Code** (Пользовательский код).
   * Выберите **JavaScript** > **Open Editor** (Открыть редактор) и вставьте фрагмент кода SDK для смарт-баннеров **без тэгов &lt;script>**.
   * Нажмите **Keep Changes** (Сохранить изменения), чтобы закрыть Редактор кода.
5. Нажмите **Сохранить**.

</Accordion>

<div id="step-3-add-the-adobe-launch-tag-to-your-website" />

<Accordion title="Шаг 3: Добавьте тег Adobe Launch на свой сайт.">

**Чтобы добавить тег Adobe Launch на свой веб-сайт (который загружает код смарт-баннеров)**:

1. На странице **My web property** (Мой веб-ресурс) выберите вкладку **Environments** (Среды).
2. Найдите строку со средой, которую вы хотите опубликовать (разработка или рабочая).
   * В столбце **Install** (Установить) щелкните значок коробки в нужной строке; как правило, выбирают строку, соответствующую производственной среде.
   * См. раздел о публикации среды для **запуска Adobe**.
3. В диалоговом окне **Web Install Instructions** (Инструкция по установке через интернет):
   * Скопируйте фрагмент кода скрипта.
   * Закройте диалоговое окно.
4. Вставьте этот фрагмент кода в тег &lt;head> сайта.

</Accordion>

<div id="step-4-publish-the-adobe-launch-environment" />

<Accordion title="Шаг 4: Публикация среды Adobe Launch">

Опубликуйте среду, чтобы активировать тег Adobe Launch.

1. На странице **My web property** (Мой веб-ресурс) выберите вкладку **Publishing** (Публикация).
2. В разделе **Development** (Разработка) щелкните **Add New Library** (Добавить новую библиотеку).
   1. Назовите библиотеку и выберите среду.
   2. В пункте **Resource Changes** (Изменения ресурсов) нажмите **Add a Resource** (Добавить ресурс).
   3. Нажмите **Rules** (Правила) > **Load Smart Banners** (Загрузить смарт-баннеры) > **Latest** (Последние) > **Select & Create a New Revision** (Выбрать и создать новую редакцию).
   4. Нажмите **Сохранить**.
3. В разделе **Development** (Разработка):
   1. Рядом с только что созданной библиотекой откройте меню действий (3 точки) и выберите **Build for Development** (Создать сборку для разработки).
   2. Снова откройте меню действий и выберите опцию **Submit for Approval** (Отправить на утверждение).
4. В разделе **Submitted** (Отправленные):
   1. Откройте меню действий и выберите опцию **Build for Staging** (Создать сборку для стейджинга).
   2. Снова откройте меню действий и выберите опцию **Approve for Publishing** (Утвердить для публикации).
5. В разделе **Approved** (Утвержденные) откройте меню действий выберите опцию **«Build & Publish to Production» (Создать сборку и опубликовать в производственной среде).** Процесс завершен.

</Accordion>

Теперь при загрузке вашего сайта на мобильном устройстве будет отображаться активный креатив баннера. Чтобы настроить отображение баннера только на определенных страницах или в соответствии с действиями пользователей, см. <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">правила Adobe Launch</Anchor>.

</Accordion>

<div id="shopify" />

<Accordion title="Shopify">

**Чтобы внедрить код на ваш сайт Shopify**:

1. На дэшборде Shopify перейдите в раздел **Sales Channels** (Каналы продаж) > **Online Store** (Онлайн-магазин) > **Themes** (Темы).  
   Отобразится ваша текущая тема.
2. Нажмите **Actions** (Действия) > **Edit code** (Редактировать код).  
   Откроется страница редактирования кода вашей темы.
3. В папке Layout (Макет) выберите файл, имя которого начинается с **`{/}` theme**.  
   Отобразится код веб-страницы.
4. В коде, непосредственно под заголовком **&lt;head>**, вставьте код смарт-баннеров.

</Accordion>

<div id="wix" />

<Accordion title="Wix">

**Чтобы внедрить код на ваш сайт Wix**:

1. На дэшборде Wix нажмите **Settings** (Настройки).
2. В разделе Advanced (Расширенные) страницы Settings (Настройки) нажмите **Custom code** (Пользовательский код).
3. Нажмите **+ Add Custom Code** (Добавить пользовательский код).
4. В поле**Paste the code snippet here** (Вставьте здесь фрагмент кода) вставьте код смарт-баннеров.
5. В поле Name (Имя) введите имя вашего кода. **Рекомендуется:** Смарт-баннеры AppsFlyer.
6. В разделе **Add Code to Pages** (Добавить код на страницы) выберите, где будут отображаться ваши баннеры. Одно из следующего:
   * Все страницы
   * Выберите определенные страницы
7. Нажмите **Применить**.  
   Теперь на странице пользовательского кода должен отображаться ваш код. Убедитесь, что он находится в разделе **Head** (Заголовок).

</Accordion>

<div id="squarespace" />

<Accordion title="Squarespace">

**Чтобы внедрить код на ваш сайт Squarespace**:

1. На дэшборде Squarespace нажмите **Website** (Веб-сайт).
2. Нажмите **Settings** (Настройки).
3. Нажмите **Advanced** (Расширенные).
4. Нажмите **Code Injection** (Внедрение кода).
5. В разделе **Header** (Заголовок) вставьте код смарт-баннеров.
6. Нажмите **Save** (Сохранить).

</Accordion>

<div id="wordpress" />

<Accordion title="WordPress">

**Чтобы внедрить код на ваш сайт WordPress**:

1. На дэшборде WordPress нажмите **Appearance** (Вид) > **Theme Editor** (Редактор тем).  
   Откроется страница редактирования темы и отобразится CSS-код вашего сайта.
2. В разделе **Theme Files** (Файлы темы) нажмите **Theme Header (header.php)** (Заголовок темы).
3. В отобразившемся коде под **&lt;head>** вставьте код смарт-баннеров.
4. Нажмите **Update File** (Обновить файл).

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#installation-and-integration">Интеграция PBA со смарт-баннерами</Anchor>

<div data-zendesk-anchors="h_01HBT97B1ZGKKTD0TN2J2W56ZQ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 website-code-implementation=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%B4%D0%B0-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%B0 h_01HBT97B1Z0F4B8E9GQWJEE6BH=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%B4%D0%B0-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%B0 google-tag-manager=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%B4%D0%B0-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%B0 h_01HBT97B1ZKW36W9F0XQKM323P=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%B4%D0%B0-%D0%B2%D0%B5%D0%B1-%D1%81%D0%B0%D0%B9%D1%82%D0%B0 h_01HBT97B1ZX6VM1YER2HXTYQJ2=adobe-launch-tag-manager h_01HBT97B1ZPP0AKB5E31W36VC2=step-1-create-a-property-in-adobe-experience-cloud h_01HBT97B1ZK4T23MF4D6VGP4B8=step-2-add-smart-banners-code-to-the-adobe-launch-property h_01HBT97B1Z0W9VJ5FCW4605RDC=step-3-add-the-adobe-launch-tag-to-your-website h_01HBT97B1Z1W33DTT6NR4PQHQ0=step-4-publish-the-adobe-launch-environment h_01HBT97B1Z0NTYJKB2YFMX62P9=shopify h_01HBT97B1ZYVJ6PW7F811V5TAX=wix h_01HBT97B1ZS0FDM60M1GA04PRT=squarespace h_01HBT97B1ZKYB7XPGFG00PB2BT=wordpress h_01HE7SG3MJ4WTPMTXF0DA0M07D=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

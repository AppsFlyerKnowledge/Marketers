---
title: Руководство по интеграции веб-SDK PBA
metadata:
  keywords:
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-05-17T09:05:30Z'
  edited_at: '2026-08-31T00:23:09Z'
  id: 360001610038
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/360001610038
---
> **At a glance:** **Краткий обзор:** Интегрируйте AppsFlyer в сайты с помощью веб-SDK для учета и измерения посещений, событий, конверсий и доходов.

<Image align="center" alt="5107_Infographic_Web_S2S_759x270_option1.jpg" src="https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg" />

<div id="web-sdk-user-and-integration-guide" />

## Руководство пользователя и по интеграции веб-SDK

* Тег JavaScript для веб-SDK:
  * является частью решения People-Based Attribution (PBA) для анализа путей пользователей на нескольких платформах.
  * сообщает платформе AppsFlyer о посещениях и действиях пользователей на вашем сайте.
  * является плагином для веб-сайта, который не требует программирования. Он не зависит от операционной системы и браузера посетителя веб-сайта.
  * Размер: 40-60Кб.
* Внедрите веб-SDK вместе с мобильным SDK AppsFlyer для регистрации и отображения активности пользователей в мобильных приложениях и веб-средах.
* События, происходящие за пределами веб-сайта, могут быть записаны с помощью <Anchor target="_blank" href="/marketers/ru/docs/web-server-to-server-events-api-for-pba-web-s2s">API server-to-server для событий в браузере</Anchor> (веб-S2S)

<div id="selecting-a-code-snippet" />

## Выбор фрагмента кода

Выберите сниппет, который соответствует вашему типу интеграции и требованиям безопасности. Доступны две опции:

* [Стандартный Web SDK](#standard): Стандартная интеграция.
* [Расширенная проверка SDK](#advanced-sdk-verification): Улучшенная интеграция, которая добавляет защиту цепочки поставок для Web SDK. Используйте это решение, чтобы добавить дополнительный слой безопасности против компрометации CDN, DNS-подмены и атак посредников.

> 🚧 **Important**
>
> **Важно!**
>
> Если вы переходите от стандартного веб-SDK к расширенной проверке SDK, замените свой текущий сниппет новым. Не добавляйте новый сниппет поверх существующего.

<div id="standard-web-sdk" />

### Стандартный Web SDK

Используйте этот сниппет для развертывания стандартной интеграции Web SDK. Вставьте его рядом с верхней частью тега  на всех страницах, где вы хотите загрузить SDK.

<div id="standard-without-smart-banners" />

<Accordion title="Без Smart Banners">

```html
<script>\n  // Очередь — буферизует вызовы AF() до готовности SDK\n  window.AppsFlyerSdkObject = "AF";\n  window.AF = window.AF || function() {\n    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));\n  };\n  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };\n  window.AF.plugins = {};\n\n  // Внедрение SDK\n  var o = document.createElement("script"),\n      p = document.getElementsByTagName("script")[0];\n  o.async = 1;\n  o.src = "https://websdk.appsflyersdk.com?" + "st=pba&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
</script>
```

</Accordion>

<div id="standard-with-smart-banners" />

<Accordion title="С Smart Banners">

```html
<script>\n  // Очередь — буферизует вызовы AF() до готовности SDK\n  window.AppsFlyerSdkObject = "AF";\n  window.AF = window.AF || function() {\n    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));\n  };\n  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };\n  window.AF.plugins = {};\n\n  // Внедрение SDK\n  var o = document.createElement("script"),\n      p = document.getElementsByTagName("script")[0];\n  o.async = 1;\n  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
</script>
```

</Accordion>

<div id="advanced-sdk-verification" />

### Расширенная проверка SDK

Расширенная проверка SDK добавляет защиту цепочки поставок для Web SDK. Она гарантирует, что код, выполняющийся в браузерах ваших пользователей, точно соответствует тому, что опубликовал AppsFlyer. Исходный код SDK идентичен стандартной интеграции; различаются только механизмы доставки и проверки.

Расширенная проверка SDK:

* Добавляет дополнительный уровень безопасности против компрометации CDN, захвата DNS и атак посредника.
* Добавляет примерно 250 мс к времени загрузки SDK.

Расширенная проверка SDK является необязательной. Стандартная интеграция по-прежнему полностью поддерживается и остаётся отраслевым стандартом для сторонних аналитических пикселей. Расширенная проверка SDK предоставляет дополнительный уровень защиты помимо этого стандарта.

Если ваш сайт применяет Политику безопасности контента (CSP) с использованием nonce, смотрите [Политику безопасности контента (CSP)](#content-security-policy-csp) в разделе Управление конфиденциальностью для варианта этого сниппета с расширенным nonce.

<div id="advanced-verification-without-smart-banners" />

<Accordion title="Без Smart Banners">

```html
<script>\n  // Очередь — буферизует вызовы AF() до готовности SDK\n  window.AppsFlyerSdkObject = "AF";\n  window.AF = window.AF || function() {\n    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));\n  };\n  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };\n  window.AF.plugins = {};\n\n  // Конфигурация загрузчика манифеста\n  window.AF_LOADER_CONFIG = {\n    baseUrl: "https://websdk.appsflyersdk.com",\n    plugins: ["pba"]\n  };\n\n  // Внедрение загрузчика манифеста\n  var loaderScript = document.createElement("script");\n  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";\n  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";\n  loaderScript.crossOrigin = "anonymous";\n  loaderScript.async = true;\n  document.head.appendChild(loaderScript);\n</script>
```

</Accordion>

<div id="advanced-verification-with-smart-banners" />

<Accordion title="С Smart Banners">

```html
<script>\n  // Очередь — буферизует вызовы AF() до готовности SDK\n  window.AppsFlyerSdkObject = "AF";\n  window.AF = window.AF || function() {\n    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));\n  };\n  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };\n  window.AF.plugins = {};\n\n  // Конфигурация загрузчика манифеста\n  window.AF_LOADER_CONFIG = {\n    baseUrl: "https://websdk.appsflyersdk.com",\n    plugins: ["banners", "pba"]\n  };\n\n  // Внедрение загрузчика манифеста\n  var loaderScript = document.createElement("script");\n  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";\n  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";\n  loaderScript.crossOrigin = "anonymous";\n  loaderScript.async = true;\n  document.head.appendChild(loaderScript);\n</script>
```

</Accordion>

<div id="integrating-the-web-sdk-into-the-website" />

## Интеграция веб-SDK в сайт

<div id="installation-and-integration" />

<Accordion title="Установка и интеграция">

<div id="considerations-and-actions-required" />

#### Соображения и необходимые действия

| Чек-лист по интеграции |
| --- |
| Чтобы обеспечить учет посещений и событий, на всех страницах сайта должен быть установлен веб-SDK. |
| Поместите код сниппета, [который вы выбрали выше,](#step-2-select-a-code-snippet) так, чтобы он загружался как можно раньше в области страницы. Для этого разместите код в верхней части тега head. |
| Если вы интегрируете SDK с помощью Google Менеджера тегов (GTM):<ul><li>Убедитесь, что пакет SDK загружается один раз за каждую загрузку страницы.</li><li>Установите SDK на загрузку сразу после загрузки страницы, используя <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">приоритеты GTM</Anchor>.</li></ul> |
| Вы можете реализовать веб-SDK как **со** смарт-баннерами, так и **без** них. Следуйте соответствующим инструкциям в следующих разделах. |
| Обязательные требования к интеграции<ul><li>Запись посещений</li><li>Запись событий</li><li>Настройка [идентификатора клиента](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid) <mark>(CUID)</mark>: Если у вас нет CUID, обратитесь к своему менеджеру по работе с клиентами, чтобы обсудить альтернативные варианты.</li></ul>Проверьте интеграцию с помощью <Anchor target="_blank" href="/marketers/ru/docs/test-pba-web-sdk-integration">инструмента тестирования</Anchor> |

**Прежде чем начать**:

* Уточните у маркетолога, что он создал <Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings">пакет бренда.</Anchor>
* Дополнительные указания см. в <Anchor target="_blank" href="/marketers/ru/docs/onboarding-guide-to-people-based-attribution">руководстве по интеграции PBA</Anchor>.
* Обратите внимание: Если у вас уже установлен автономный Web-SDK Smart Banners, удалите его и замените Web-SDK, который поддерживает и Smart Banners, и People-based Attribution (PBA); не добавляйте отдельный Web-SDK только для PBA.

**Выполните следующие действия:**

* Получите веб-ключ разработчика для веб-SDK. **Примечание!** Это не тот же ключ, который используется мобильными приложениями.
  * **Чтобы получить веб-ключ разработчика:**
    1. В AppsFlyer в верхнем меню выберите вкладку **Мои приложения**.
    2. Нажмите **Просмотреть пакет бренда.**
    3. Скопируйте необходимый **веб-ключ разработчика. (WEB\_DEV\_KEY)**
* Если вы используете смарт-баннеры, получите ключ смарт-баннера.
  * **Чтобы получить ключ смарт-баннера:**
    1. В AppsFlyer в боковом меню перейдите в раздел **Вовлечение** > **Web to App** > **Smart Banners**.
    2. Скопируйте необходимый ключ **смарт-баннеров**.
* Разрешения на добавление скриптов в теги head на сайте.
* Если вы используете Google Менеджер тегов, он должен быть интегрирован в сайт.

**Перейдите к интеграции веб-SDK с помощью одного из следующих вариантов.**

<Tabs>
<Tab title="Нативная">

<div id="javascript-code-snippet" />

#### Фрагмент кода JavaScript

Интегрируйте веб-пакет SDK одним из следующих способов.

<div id="to-install-the-web-sdk-without-smart-banners" />

#### **Чтобы установить веб-SDK без смарт-баннеров:**

1. Повторите следующую процедуру на всех страницах вашего сайта.
2. В следующем фрагменте кода замените `WEB_DEV_KEY` на ключ, указанный в необходимых условиях.
3. Вставьте [выбранный выше](#step-2-select-a-code-snippet) сниппет кода в тег head вашего сайта. В теге head он должен располагаться ближе к началу.

<div id="to-implement-the-web-sdk-with-smart-banners" />

#### **Чтобы внедрить веб-SDK со смарт-баннерами:**

1. Повторите процедуру ниже на всех страницах вашего сайта.
2. В сниппете кода, [который вы выбрали выше,](#step-2-select-a-code-snippet) замените `WEB_DEV_KEY` и `YOUR_BANNER_KEY`, используя ключи, указанные в предварительных условиях.
3. Вставьте этот сниппет кода в тег head сайта. В теге head он должен располагаться ближе к началу.

</Tab>

<Tab title="https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png">

**Чтобы внедрить веб-SDK с помощью Google Менеджера тегов (GTM):**

1. <Anchor target="_blank" href="https://developers.google.com/tag-manager/quickstart">Перейдите в Google Tag Manager.</Anchor>
2. Создайте новый тег для веб-SDK AppsFlyer.

   <Image align="center" alt="" src="https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png" />
3. Выберите тип тега **Custom HTML**.
4. Присвойте тегу понятное имя.
5. Выполните одно из следующих действий:
   * Если вы интегрируете веб-SDK **без** смарт-баннеров:
     1. Вставьте сниппет кода, [который вы выбрали выше,](#step-2-select-a-code-snippet) в окно **Конфигурация тега**.
     2. Во фрагменте кода замените `WEB_DEV_KEY` на ключ, указанный в необходимых условиях.
   * Если вы интегрируете веб-SDK **со** смарт-баннерами:
     1. Вставьте сниппет кода, [который вы выбрали выше,](#step-2-select-a-code-snippet) в окно **Конфигурация тега**.
     2. Во фрагменте кода замените `WEB_DEV_KEY` и `YOUR_BANNER_KEY` на ключи, указанные в необходимых условиях.
6. Нажмите **Сохранить**.
7. Выполните одно из следующих действий:
   * **Чтобы добавить триггер на все страницы:**
     1. Нажмите **Добавить триггер**.

        <Image align="center" alt="gtm-af-tag-sdk-trigger.png" src="https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png" />
     2. Выберите **Все страницы**.
     3. Нажмите кнопку **Сохранить.**
     4. Введите название тега и нажмите **Сохранить**.  
        Вы завершили процедуру.
   * **Чтобы добавить триггер на определенные страницы:**
     1. Нажмите **Сохранить тег**.
     2. В главном окне GTM выберите **Триггеры.** Нажмите **Новый**.
     3. Нажмите на значок карандаша.
     4. Выберите тип триггера **Просмотр страницы**.  
        <Image align="center" alt="PBAselectTrigger_us-en.jpg" src="https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg" />
     5. Выберите **Несколько просмотров страниц.**
     6. Настройте страницу и условия триггера.
     7. Нажмите кнопку **Сохранить.**
     8. Свяжите триггер с тегом веб-SDK AppsFlyer. Для этого:
        1. В главном окне GTM выберите Теги.
        2. Выберите тег, который вы создали ранее.
        3. На панели триггеров нажмите на ручку.
        4. Выберите триггер просмотра страницы, который вы создали ранее.

           <Image align="center" alt="Нативный Менеджер тегов Google" src="https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png" />
        5. Нажмите **Сохранить**.

</Tab>

<Tab title="Native Google Tag Manager Adobe Launch Tag Manager">

1. [Создание свойства в Adobe Experience Cloud](/docs/pba-web-sdk-integration-guide#create-a-property-in-adobe-experience-cloud)
2. [Добавление веб-SDK в свойство Adobe Launch](/docs/pba-web-sdk-integration-guide#add-the-web-sdk-to-the-adobe-launch-property)
3. [Добавление тега Adobe Launch на сайт](/docs/pba-web-sdk-integration-guide#add-the-adobe-launch-tag-to-the-website)
4. [Публикация среды Adobe Launch](/docs/pba-web-sdk-integration-guide#publish-the-adobe-launch-environment)

<div id="create-a-property-in-adobe-experience-cloud" />

<Accordion title="Создание свойства в Adobe Experience Cloud">

<Image align="center" alt="adobe_create_property.png" src="https://files.readme.io/1f97d619d5fdfe47b1dd1a2e17c0169e939c32bcda62580ba259d6e86f61d6c2-20260884824209.png" />

1. Перейдите в раздел **Adobe Experience Cloud** >**Запустить**.
2. В разделе **Adobe Experience Cloud Launch** (Запуск Adobe Experience Cloud) нажмите **Go to Launch** (Перейти к запуску).
3. Нажмите **New Property** (Новое свойство).
4. Присвойте свойству имя.
5. В разделе **Platform** (Платформа) выберите **Web** (Веб-сайт).
6. Укажите домен своего сайта.
7. Нажмите **Сохранить**.

</Accordion>

<div id="add-the-web-sdk-to-the-adobe-launch-property" />

<Accordion title="Добавление веб-SDK в свойство Adobe Launch">

<Image align="center" alt="web_property_rules.png" src="https://files.readme.io/5f592f3ce1f5b319c8f6f96a6235618d884a4faccb1387b1f22c1fd2ce662d15-360006168098.png" width="491px" />

1. На странице **My web property** (Мой веб-ресурс) выберите вкладку **Rules** (Правила).
2. Дайте правилу название. Рекомендуется использовать **Загрузить веб-SDK.**
3. В разделе **IF** (Если) под пунктом **EVENTS** (События) нажмите **+Add** (Добавить).
   * В разделе **Event Type** (Тип события) выберите **Core - DOM Ready** (Основное, с поддержкой DOM).
   * Нажмите **Keep Changes** (Сохранить изменения).
4. В разделе **THEN** (Тогда) в пункте **Actions** (Действия) нажмите **+Add** (Добавить).
   * В разделе **Action Type** (Тип действия) > **Custom Code** (Пользовательский код).
   * Выберите **JavaScript** > **Open Editor** (Открыть редактор) и вставьте фрагмент кода веб-SDK **без тегов &lt;script>**.
   * Нажмите **Keep Changes** (Сохранить изменения), чтобы закрыть Редактор кода.
5. Нажмите **Сохранить**.

</Accordion>

<div id="add-the-adobe-launch-tag-to-the-website" />

<Accordion title="Добавление тега Adobe Launch на сайт">

<Image align="center" alt="adobe_tag.png" src="https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png" />

1. На странице **My web property** (Мой веб-ресурс) выберите вкладку **Environments** (Среды).
2. Найдите строку со средой, которую вы хотите опубликовать (разработка или рабочая).
   * В столбце **INSTALL** (Установить) щелкните значок коробки в нужной строке; как правило, выбирают строку, соответствующую производственной среде.
   * См. раздел о публикации среды для **запуска Adobe**.
3. В диалоговом окне **Web Install Instructions** (Инструкция по установке через интернет):
   * Скопируйте фрагмент кода скрипта.
   * Закройте диалоговое окно.
4. Вставьте этот фрагмент кода в тег &lt;head> сайта.

</Accordion>

<div id="publish-the-adobe-launch-environment" />

<Accordion title="Публикация среды Adobe Launch">

<Image align="center" alt="adobe_publishing_env.png" src="https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png" />

1. На странице **My web property** (Мой веб-ресурс) выберите вкладку **Publishing** (Публикация).
2. В разделе **Development** (Разработка) щелкните **Add New Library** (Добавить новую библиотеку).
   * Назовите библиотеку и выберите среду.
   * В пункте **RESOURCE CHANGES** (Изменения ресурсов) нажмите **Add a Resource** (Добавить ресурс).
   * Нажмите **Rules** (Правила) > **Load web SDK** (Загрузить веб-SDK) > **Latest** (Последние) > **Select & Create a New Revision** (Выбрать и создать новую редакцию).
   * Нажмите **Сохранить**.
3. В разделе **Development** (Разработка):
   * Рядом с только что созданной библиотекой откройте меню действий (3 точки) и выберите **Build for Development** (Создать сборку для разработки).
   * Снова откройте меню действий и выберите опцию **Submit for Approval** (Отправить на утверждение).
4. В разделе **Submitted** (Отправленные):
   * Откройте меню действий и выберите опцию **Build for Staging** (Создать сборку для стейджинга).
   * Снова откройте меню действий и выберите опцию **Approve for Publishing** (Утвердить для публикации).
5. В разделе **Approved** (Утвержденные):
   * Откройте меню действий > выберите **Build & Publish to Production**
   * Процесс завершен.

</Accordion>

Когда сайт загружается на мобильном устройстве, активный креатив отображается в баннере. Чтобы узнать, как показывать баннер на определенных страницах или в соответствии с действиями пользователя, см. <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Правила Adobe Launch</Anchor>.

</Tab>
</Tabs>

</Accordion>

<div id="ensure-that-the-sdk-is-working" />

<Accordion title="Убедитесь, что пакет SDK работает">

После установки проверьте, что веб-SDK AppsFlyer вызывается браузером посетителя и что сообщения отправляются. Это делается путем проверки сообщения о сетевом соединении, о котором сообщается в браузере.

**Чтобы убедиться, что пакет SDK загружается и работает:**

1. Перейдите на сайт.
2. Откройте инструменты разработчика браузера.

   <Image align="center" alt="WebSDK_us-en.jpg" src="https://files.readme.io/5550f0ee8c1a5852a983e6482cb0489696b669ffe5fade49d2308ee32f57201b-360009548497.jpg" />
3. Перейдите на вкладку (A) **Сеть**.
4. Обновите страницу.
5. Отфильтруйте по (B) **wa.appsflyer**.
6. Выберите (C) сообщение **о событиях**.
7. На вкладке Headers (D):
   * **URL-адрес запроса** — wa.appsflyer.com/events.
   * site\_id query parameter= `WEB_DEV_KEY`.
   * (E) **код статуса 200**.
8. Убедитесь, что значение site\_id равно значению `WEB_DEV_KEY` в настройках пакета бренда:
   1. В AppsFlyer в боковом меню выберите **Настройки** > **Пакеты бренда**.
   2. Нажмите на **веб-ключ разработчика**, чтобы скопировать его.
   3. Вставьте ключ в любое место (новая вкладка браузера, блокнот), чтобы отобразить ключ.
   4. Убедитесь, что site\_id и `WEB_DEV_KEY` совпадают.
9. Убедитесь, что пакет SDK загружается только один раз. Многократная загрузка SDK может привести к тому, что SDK перестанет работать.

</Accordion>

<div id="sending-events-optinoptout" />

<Accordion title="Согласие на отправку событий">

<Image align="center" alt="5578-VistiorPrivacyOptIn_us-en.png" src="https://files.readme.io/cd6cbcaeb7f831f4efe74a9a6c6b20d5095602e7edf4dd38becd90864e73c2fb-360010263157.png" />

Веб-SDK отправляет данные о событиях посетителей в AppsFlyer. Вы можете управлять, останавливать или запускать отправку событий, как описано в этом разделе.

Обратите внимание:

* Настройка **начального состояния SDK**: Определяет, отправляет ли SDK события при первоначальной загрузке страницы или должен ждать, пока вы не дадите явную команду, чтобы начать отправку событий. Настройка содержится в веб-фрагменте.
* **Явный контроль:** Используется, чтобы остановить или начать отправку событий. Например, если вы реализуете баннеры согласия/отказа предоставления данных (также известные как баннеры согласия на использование файлов cookie), интегрируйте явные команды в элементы управления баннером, чтобы запускать и останавливать отправку событий. Явный контроль имеет приоритет над настройкой начального состояния SDK и использует постоянные файлы cookie первой стороны со следующими характеристиками:
  * Устанавливается на домене сайта.
  * Срок действия истекает по истечении периода, установленного веб-SDK или определенного браузером. После истечения срока действия файлов cookie веб-SDK возвращается к исходным настройкам состояния.
  * Файл cookie Web-SDK не вмешивается в настройки файлов cookie, задаваемые в браузере, и всегда подчиняется им.

<div id="sdk-initial-state-setting" />

#### Настройка начального состояния SDK

| Настройка | Фрагмент кода обязателен |
| --- | --- |
| [По умолчанию] Отправлять события | Внесите следующие изменения во фрагмент кода веб-SDK. При необходимости добавьте параметр measurementStatus:<br /><br />Установите measurementStatus=true<br /><br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:true}` |
| Не отправлять события | Внесите следующие изменения во фрагмент кода веб-SDK. При необходимости добавьте параметр measurementStatus:<br /><br />Установите measurementStatus=false  <br />  <br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:false}` |

<div id="explicit-control" />

#### Явный контроль

| Вариант | Команда |
| --- | --- |
| Начать отправлять события (согласие) | `window.AF_SDK.PLUGINS.PBA.enableMeasurement()` |
| Прекратить отправлять события (отказ) | `window.AF_SDK.PLUGINS.PBA.disableMeasurement()` |

</Accordion>

<div id="implement-a-content-security-policy-csp-policy" />

<Accordion title="Реализация политики безопасности контента (CSP)">

Если вашему сайту требуются строгие протоколы безопасности или конфиденциальности данных, используйте следующие механизмы, чтобы настроить взаимодействие Web-SDK с вашей средой и данными.

<div id="content-security-policy-csp" />

#### Политика безопасности контента (CSP)

Если ваш сайт требует, чтобы JavaScript был защищен CSP, Web SDK поддерживает два подхода в зависимости от вашей конфигурации CSP.

* CSP с директивой **self** Добавьте `https://websdk.appsflyersdk.com` в ваш `script-src` белый список. Это работает как для Стандартного Web SDK, так и для Расширенной проверки SDK.
* **CSP с использованием nonce**: Если ваша политика использует `script-src 'nonce-...'`, вы можете использовать [вариант расширенной проверки SDK с nonce](#advanced-sdk-verification-with-csp-nonce-snippets). Это передает nonce всем трем тегам скриптов, необходимым для процесса проверки. Замените `{{CSP_NONCE}}` на сгенерированное сервером уникальное значение nonce для каждого запроса.

Таблица ниже показывает, какие политики CSP совместимы с вариантом с расширенным nonce.

| Политика | Работы | Примечания |
| --- | --- | --- |
| `script-src 'self'` | Нет | Внешний источник CDN не разрешён; встроенный скрипт также блокируется. |
| `script-src 'self' https://websdk.appsflyersdk.com` | Частичный | Разрешает загрузчик и SDK, но встроенный скрипт настройки все еще заблокирован. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | Да | Nonce охватывает встроенный скрипт и загрузчик; тег SDK получает nonce, переданный загрузчиком. |
| `script-src 'nonce-...' 'strict-dynamic'` | Да (рекомендуется) | Nonce охватывает встроенный скрипт и загрузчик; `strict-dynamic` тем самым переносит доверие на динамически вставляемый тег SDK. CDN-источник не нужен в белом списке. |

Совместимость политики CSP

<div id="advanced-sdk-verification-with-csp-nonce-snippets" />

#### Расширенная проверка SDK с фрагментами CSP nonce

<div id="nonce-without-smart-banners" />

<Accordion title="Без Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">\n  // Очередь — буферизует вызовы AF() до готовности SDK\n  window.AppsFlyerSdkObject = "AF";\n  window.AF = window.AF || function() {\n    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));\n  };\n  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };\n  window.AF.plugins = {};\n\n  // Конфигурация загрузчика манифеста — nonce передаётся во внедряемый тег <script> SDK\n  window.AF_LOADER_CONFIG = {\n    baseUrl: "https://websdk.appsflyersdk.com",\n    plugins: ["pba"],\n    nonce: "{{CSP_NONCE}}"\n  };\n\n  // Внедрение загрузчика манифеста\n  var loaderScript = document.createElement("script");\n  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";\n  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";\n  loaderScript.crossOrigin = "anonymous";\n  loaderScript.nonce = "{{CSP_NONCE}}";\n  loaderScript.async = true;\n  document.head.appendChild(loaderScript);\n</script>
```

</Accordion>

<div id="nonce-with-smart-banners" />

<Accordion title="С Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">\n  // Очередь — буферизует вызовы AF() до готовности SDK\n  window.AppsFlyerSdkObject = "AF";\n  window.AF = window.AF || function() {\n    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));\n  };\n  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };\n  window.AF.plugins = {};\n\n  // Конфигурация загрузчика манифеста — nonce передаётся во внедряемый тег <script> SDK\n  window.AF_LOADER_CONFIG = {\n    baseUrl: "https://websdk.appsflyersdk.com",\n    plugins: ["banners", "pba"],\n    nonce: "{{CSP_NONCE}}"\n  };\n\n  // Внедрение загрузчика манифеста\n  var loaderScript = document.createElement("script");\n  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";\n  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";\n  loaderScript.crossOrigin = "anonymous";\n  loaderScript.nonce = "{{CSP_NONCE}}";\n  loaderScript.async = true;\n  document.head.appendChild(loaderScript);\n</script>
```

</Accordion>

</Accordion>

<div id="discard-query-params" />

<Accordion title="Сброс параметров запроса">

Если параметры запроса содержат данные, которые AppsFlyer не должен для вас регистрировать, вы можете указать платформе AppsFlyer отбрасывать некоторые или все параметры запроса. В таком случае они недоступны ни в сырых данных, ни в отчетах.

Вы можете реализовать описанные методы в отношении url, рефереров и header\_referer.

<div id="query-discard-options" />

#### Параметры сброса запросов

| Метод | Описание |
| --- | --- |
| Сброс всех параметров запроса | Добавьте `af_url=true` к url |
| Сброс определенных параметров запроса | Задавая маску параметров запроса, вы указываете, какие параметры будут отброшены.  Установите маску сброса с помощью `af_url_mask=param`, где param — имя параметра.<br /><br />Пример:<br /><br />**Url с маской:**<br /><br />`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`<br /><br />**Url после сброса параметров:**<br /><br />`param1=value1&af_url_mask=param2;param3` |

</Accordion>

<div id="principles-of-event-recording" />

## Принципы записи событий

<div id="conversion-and-standard-events" />

<Accordion title="Конверсии и стандартные события">

* Пользовательские события записываются SDK, который отправляет событие на платформу AppsFlyer.
* Используя список <Anchor target="_blank" href="/marketers/ru/docs/pba-brand-bundles-and-settings#web-event-settings">событий конверсии</Anchor>, заданный маркетологом, AppsFlyer разбивает события на стандартные и события конверсии.
* Данные о событиях конверсии доступны на дэшбордах PBA.
* Данные о конверсиях и стандартных событиях доступны в <Anchor target="_blank" href="/marketers/ru/docs/pba-raw-data-reports">отчетах по сырым данным.</Anchor>

<div id="conversion-events" />

### События конверсии

* События конверсии дают представление о ваших маркетинговых и бизнес-усилиях. К событиям конверсии относятся покупки, загрузки, регистрации и подписки.
* PBA атрибутирует события конверсии к медиа-источнику, который побудил пользователя посетить веб-сайт.
* Определив атрибутированный медиа-источник, вы можете измерить и дифференцировать качество пользователей, привлеченных разными медиа-источниками.
* События конверсии используются для учета дохода и расчета ROI.
* Используйте их для сравнения бюджета рекламы для конкретных медиа-источников с доходом, полученным от пользователей, которые приходят из этих медиа-источников.

<div id="standard-events" />

### Стандартные события

* Стандартные события используются для проверки пути пользователя и воронок, которые приводят к конверсиям.
* Используйте их для измерения активности пользователей и выделения медиа-источников, которые привлекают вовлеченных пользователей.
* Записывайте действия пользователей, чтобы помечать их для кампаний по повторному вовлечению.

<div id="recording-events" />

### Запись событий

Запускайте веб-SDK для записи событий при выполнении определенных условий, например, при загрузке целевой страницы или при взаимодействии пользователей с элементами сайта. [Смотрите примеры записи событий](#recording-events::f1e16eae).

</Accordion>

<div id="identifying-users-using-customer-user-id-cuid" />

<Accordion title="Идентификация пользователей с помощью идентификатора клиента (CUID)">

* Веб-пользователи идентифицируются в AppsFlyer с помощью уникального CUID, который вы им выделяете. Как правило, CUID управляется внутренними серверами.
* Используйте то же значение CUID, которое вы используете в мобильной среде. Это позволяет получить целостное представление об активности пользователей на нескольких платформах. Функция в мобильном SDK – это функция setCustomerUserId (<Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid#установка-cuid">iOS</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid#установка-cuid">Android, Unity</Anchor>).
* Чтобы задать CUID в веб-SDK:
  * Установите CUID в самой ранней точке, когда у вас есть к нему доступ. В большинстве случаев это означает, что вам нужно подождать, пока пользователь пройдет идентификацию через вход или регистрацию.
  * Запустите вызов JavaScript для setCustomerUserId(), как показано в следующем примере.   
    Примечание! Отправляйте CUID в виде строки, даже если это число. Сделайте это, заключив его в кавычки.
* **Текущий метод:** Отправьте CUID с помощью функции setCustomerUserId().
* CUID не должен содержать <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid#cuid-и-конфиденциальность">персональную информацию, позволяющую установить личность</Anchor>, такую как номер телефона или адрес электронной почты.

**Пример: задайте CUID**

```javascript
// Associate all current user web events to distinct ID 663274 
AF('pba', 'setCustomerUserId' , '663274')
```

</Accordion>

<div id="web-sdk-event-parameters" />

<Accordion title="Параметры событий веб-SDK">

| Имя параметра | Обязательно | Описание |
| --- | --- | --- |
| eventType | Да | Тип события<br /><br />Формат: Строка<br /><br />Всегда заполняйте этот параметр значением EVENT.<br /><br />Пример: eventType: "EVENT" |
| eventName | Да | Имя события<br /><br />Формат: Строка<br /><br />Пример: Покупка, подписка |
| ~~eventCategory~~ | Нет | Этот параметр устарел и будет удален из системы в срок, который будет объявлен позднее. Вместо этого используйте параметр eventValue. |
| ~~eventLabel~~ | Нет | Этот параметр устарел и будет удален из системы в срок, который будет объявлен позднее. Вместо этого используйте параметр eventValue. |
| eventRevenue | Нет | Доход, присвоенный событию конверсии<br /><br />Формат: Тип: Float |
| eventRevenueCurrency | Нет | Валюта выручки<ul><li>Код валюты по <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> из трех символов</li><li>По умолчанию: USD</li></ul>Формат: Строка |
| Значение события | Нет | Сопоставление параметров события, описывающих событие. Используйте этот параметр для отправки расширенных внутренних событий приложения, таких как артикул товара, цена позиции.<br /><br />Формат: JSON<br /><br />**Пример:** Чтобы отправить артикул ABC123 для товара синего цвета с ценой за единицу $3,99<br /><br />`{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}`<br /><br />**Ограничение:** 1000 символов. Не превышайте этого значения, оно будет усечено. |

</Accordion>

<div id="recording-event-scenarios" />

<Accordion title="Запись сценариев событий">

Пример события

```javascript
// событие покупки обуви с соответствующим доходом
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

Отправляемые события зависят от характера веб-приложения. Например, для приложения интернет-магазина требуется набор событий, которые отличаются от событий новостного издания. Ознакомьтесь с приведенными ниже сценариями, чтобы получить представление о событиях, которые вы должны отправить, а также о том, когда они должны быть отправлены.

<div id="online-store" />

#### Интернет-магазин

Предположим, вы управляете интернет-магазином. Вот некоторые стандартные события, которые вы, возможно, захотите записать:

* Поиск: стандартное событие
* Добавить в корзину: стандартное событие
* Удалить из корзины: стандартное событие
* Покупка: событие конверсии

Новостное издание

Предположим, вы управляете новым новостным изданием. Вот некоторые события, которые вы можете записать:

* Регистрация: событие конверсии
* Покупка подписки: событие конверсии

</Accordion>

<div id="ensuring-that-events-are-sent" />

<Accordion title="Обеспечение отправки событий">

Эта часть предназначена для веб-разработчиков.

<Anchor target="_blank" href="/marketers/ru/docs/test-pba-web-sdk-integration">Тестирование интеграции веб-SDK для PBA:</Anchor> просмотрите тестовые события в режиме реального времени.

**Чтобы убедиться, что события отправляются в AppsFlyer**:

1. Откройте веб-сайт.
2. Откройте инструменты разработчика в браузере.
   * <Anchor target="_blank" href="https://developers.google.com/web/tools/chrome-devtools/open#console">Как открыть инструменты разработчика в Chrome</Anchor>
   * <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html">Как открыть инструменты разработчика в Safari</Anchor>
3. Перейдите на вкладку Network (Сеть).
4. Запустите событие.
5. Фильтр по сообщениям.

   <Image align="center" alt="pba_af_event.png" src="https://files.readme.io/394f43890d1aaf09114054a3bca1a003178526e768a5da0b554dbc8d63ef1eb4-360003502238.png" />
6. Найдите сетевой запрос, начинающийся с wa.appsflyer.com (см. скриншот ниже).
7. Убедитесь, что:
   1. Код состояния — 200.
   2. Полезные данные запроса согласуются с параметрами события.

</Accordion>

<div id="examples" />

## Примеры

<div id="recording-events::f1e16eae" />

<Accordion title="Запись событий">

Приведенный код носит иллюстративный характер. Не используйте этот код как есть.

* Предположения: Веб-SDK уже загружен страницей к моменту отправки события.
* Примеры сценариев содержат код для записи событий в следующих случаях:
  * Загружается целевая страница.
  * Пользователи взаимодействуют с веб-сайтом.

<Tabs>
<Tab title="Обязательный">

**Запись событий при загрузке лендинга**

* У вас есть страница подписки на новостные рассылки и вы хотите записывать подписки.
* Вы также можете настроить страницу благодарности и перенаправлять на нее пользователей после того, как они подпишутся.

```html
<html>
    <head>
        <!-- Assume that the server returns a response with details about the newly subscribed user -->
        <!-- Alternatively, you can extract data from localStorage or cookies,
            in case data was set in either of them during the subscription process
        -->
        <script>window.onload = function(){
            AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion', eventValue: {'label' : 'newspaper'}, eventName: 'subscription',}); } </script> </head> <body> <h1>Thank You for Subscribing to Our Newsletter</h1> </body> </html>
```

* Приведенный выше код содержит базовую HTML-страницу. Веб-страница должна загрузить веб-SDK, чтобы вы могли отправлять события.
* После загрузки страницы и перенаправления на нее пользователя метод загрузки окна вызывает метод AF() для отправки события подписки в AppsFlyer.

**Запись событий, когда пользователи взаимодействуют с сайтом**

* У вас есть сайт электронной коммерции и вы хотите записывать события оформления заказа.
* Когда пользователь нажимает кнопку оформления заказа, веб-SDK отправляет событие в AppsFlyer.

```html
<html>
<head>
    <!-- Предполагается, что данные о продуктах в корзине покупок
    хранятся в localStorage -->
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Корзина покупок</h1>
    <h2>Рубашка</h2>
    <p>
        <ul>
            <li>Цвет: Blue</li>
            <li>Количество: 2</li>
            <li>Цена: $20</li>
        </ul>
    </p>
    <h2>Брюки</h2>
    <p>
        <ul>
            <li>Цвет: Black</li>
            <li>Количество: 3</li>
            <li>Цена: $15</li>
        </ul>
    </p>
    <button id='checkout'>Оформление заказа</button>
</body>
</html>
```

В приведенном выше коде показана базовая HTML-страница. Веб-страница должна загрузить веб-SDK, чтобы вы могли отправлять события.

* Когда страница загрузится, она привязывает слушателя клика к кнопке **Оформление заказа**.
* Когда пользователь нажимает на кнопку **Оформление заказа**, функция обратного вызова:
  * извлекает данные из localStorage.
  * вызывает метод AF() и передает ему данные.
* Метод AF() отправляет событие в AppsFlyer.

</Tab>

<Tab title="Нативная запись событий Запись событий Менеджером тегов">

**Запись событий при загрузке лендинга**

* У вас есть страница подписки на новостные рассылки и вы хотите записывать успешные подписки.
* Вы настраиваете страницу благодарности, на которую перенаправляются пользователи после успешной подписки.

1. Создайте страницу благодарности

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager загружает Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
        <script>
           // Предполагается, что сервер возвращает ответ с данными о пользователе, который недавно подписался
           function getResponseFromServer() {
               return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
           }
           // В качестве альтернативы можно извлечь данные из localStorage или cookies,
           // если данные были сохранены в них в процессе подписки
           localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
       </script>
   </head>
   <body>
       <h1>Спасибо за подписку на нашу рассылку</h1>
   </body>
   </html>
   ```

   Предшествующий код загружает GTM, который, в свою очередь, загружает веб-SDK. После этого в сценарии происходят два других действия. Одно из них — функция, которая получает ответ от сервера с данными о пользователе. Другое устанавливает данные в локальное хранилище. GTM имеет доступ как к функции, так и к localStorage. Вы можете вызвать функцию и получить доступ к localStorage с помощью GTM.
2. Добавьте новый тег для атрибуции подписок после загрузки страницы благодарности

   <Image align="center" alt="Ограничение: 1000 символов Не превышайте этого значения, оно будет усечено." src="https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png" />
3. Дайте тегу отдельное имя и выберите тип тега **Custom HTML**.
4. Поместите следующий код в **Custom HTML**.

   ```html
   <script> 
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'}); </script>
   ```

   <Image align="center" alt="gtm_tag_after_subscribe.png" src="https://files.readme.io/6cf080f94a97a7f38c50899a93d154320995e91f60963c075a5dd03b3a080408-360003515298.png" />
5. Разверните **Расширенные настройки**, затем **Последовательность тегов** под текстовой областью и убедитесь, что он настроен на запись конверсии после выполнения тега.

   <Image align="center" alt="Срок действия" src="https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png" />
6. Для запуска тега конверсии установите триггер. В примере триггер срабатывает при загрузке страницы благодарности.

   <Image align="center" alt="Триггер настроен на срабатывание при загрузке страницы «Спасибо»" src="https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png" />

**Запись событий, когда пользователи взаимодействуют с сайтом**

* У вас есть сайт электронной коммерции и вы хотите записывать события оформления заказа.
* После того, как пользователь нажмет кнопку оформления заказа, веб-SDK отправит событие в AppsFlyer.

1. Настройка страницы оформления заказа

   ```html Markup
   <html>
   <head>
       <script>
           // Google Tag Manager загружает Web SDK
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
   </head>
   <body>
       <h1>Корзина покупок</h1>
       <h2>Рубашка</h2>
       <p>
           <ul>
               <li>Цвет: Синий</li>
               <li>Количество: 2</li>
               <li>Цена: $20</li>
           </ul>
       </p>
       <h2>Брюки</h2>
       <p>
           <ul>
               <li>Цвет: Черный</li>
               <li>Количество: 3</li>
               <li>Цена: $15</li>
           </ul>
       </p>
       <button id='checkout'>Оформление заказа</button>
   </body>
   </html>
   ```

   Предшествующий код загружает веб-SDK с помощью GTM. Остальное — просто HTML, имитирующий страницу корзины. Обратите внимание на кнопку **Оформление заказа**, которая имеет идентификатор оформления заказа. Это необходимо при настройке GTM для обработки нажатия на эту кнопку.
2. В GTM нажмите **Variables** (Переменные), нажмите **Configure** (Настроить) и отметьте **Click Element** (Клик по элементу) в списке **Built-In Variables** (Встроенные переменные).  

   <Image align="center" alt="gtm-create-variable.png" src="https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png" />
3. Создайте новую переменную, дайте ей осмысленное название и выберите тип **Все элементы**.  

   <Image align="center" alt="gtm-checkout-all-elements.png" src="https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png" />
4. В конфигурации триггера выберите **Some Clicks**, выберите **Click Element**, который соответствует **CSS Selector** для #checkout.  

   <Image align="center" alt="gtm-checkout-click-elememt.png" src="https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png" />
5. Создайте новый тег для действия оформления заказа, выберите тип Custom HTML и установите триггер на оформление заказа.

   ```html
   <script>
    AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'}); </script>
   ```

   <Image align="center" alt="gtm-checkout-tag.png" src="https://files.readme.io/8d3f99dcd3c3ff8df9e6fc13076b798237b86f8cbc5bbd26f349fa9948edb0d6-360003431857.png" />

</Tab>
</Tabs>

* Убедитесь, что тег функций веб-SDK загружен перед запуском события.
* Не отправляйте специальные символы в значениях событий, например символы валюты в значении дохода.
* Строки значений должны быть короче 50 символов.

</Accordion>

<div id="setting-customer-user-id-after-signup" />

<Accordion title="Установка идентификатора клиента после регистрации">

Код, приведенный в этих примерах, приведен только для справки. Не используйте этот код как есть. Если вы не знаете, как использовать этот код, проконсультируйтесь со своим веб-разработчиком. 

Предположение: Веб-SDK загружается страницей перед отправкой события; не загружайте SDK повторно.

Сценарий пользователя:

* Пользователь регистрируется на вашем сайте.
* Код сайта собирает данные о пользователе и отправляет их на ваш сервер.
* Сервер генерирует уникальный CUID для пользователя.
* На странице благодарности после регистрации вы запрашиваете у сервера новый CUID.
* Используя ответ сервера, вы устанавливаете CUID AppsFlyer с помощью метода веб-SDK setCustomerUserId().

<Tabs>
<Tab title="Нативная">

Настройте страницу регистрации:

```html Markup
<html>
<head>
    <!-- Сначала загружается скрипт Web SDK -->
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        };
    // Эта функция сохраняет адрес электронной почты пользователя, отправленный на сервер после того, как пользователь перейдет на страницу благодарности
    // Ответ от сервера — это уникальный CUID, который нужно задать с помощью метода setCustomerUserId в Web SDK
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Регистрация</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Имя</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>Электронная почта</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

Приведенный выше код представляет собой простую форму регистрации. При отправке формы электронный адрес сохраняется в localStorage. Когда пользователь переходит на страницу благодарности, адрес электронной почты пользователя отправляется на сервер для создания уникального CUID для этого адреса.

Настройте страницу благодарности для пользователей, которые регистрируются:

```html Markup
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        // Используйте API fetch, чтобы отправить адрес электронной почты пользователя на сервер
        // и получить в ответ уникальный идентификатор пользователя	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Спасибо за регистрацию!</h1> 
     </body> 
</html>
```

В коде используется fetch API. Он отправляет серверу адрес электронной почты, введенный пользователем. Предполагая, что сервер создает пользователя с уникальным CUID при регистрации, отправка адреса электронной почты на сервер осуществляется с целью получения уникального CUID. Сервер отвечает уникальным CUID, и этот уникальный CUID является значением, передаваемым с помощью метода setCustomerUserId.

</Tab>

<Tab title="https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png">

1. Настройте страницу регистрации:

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager загружает Web SDK
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({
                   'gtm.start':
                       new Date().getTime(), event: 'gtm.js'
               }); var f = d.getElementsByTagName(s)[0],
                   j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true; j.src =
                       'https://www.googletagmanager.com/gtm.js?id=' + i + dl; f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');

       // Эта функция сохраняет адрес электронной почты пользователя, который будет отправлен на сервер после того, как пользователь перейдет на страницу благодарности
       // ответ от сервера — это уникальный CUID, который следует использовать в методе setCustomerUserId Web SDK
           function storeUserEmail (){
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Регистрация</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Имя</label>
               <input type="text" name="name" id="name"></div>
           <br />
           <div> <label>Электронная почта</label>
               <input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```

   Приведенный выше код представляет собой простую форму регистрации. При отправке формы адрес электронной почты сохраняется в localStorage. Когда пользователь переходит на страницу благодарности, адрес электронной почты пользователя отправляется на сервер для получения уникального CUID для этого адреса.
2. Настройте страницу благодарности для пользователей, которые регистрируются:

   ```
   (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
   t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
   o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
   p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
       </script>
       <script>
           // используйте API fetch, чтобы отправить адрес электронной почты пользователя на сервер
           // и получить в ответ уникальный идентификатор пользователя 
           window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
                  res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
           } </script> 
       </head>
       <body> 
               <h1>Спасибо за регистрацию!</h1> 
        </body> 
    </html>
   ```

   Приведенный выше код представляет собой страницу благодарности с триггером GTM, который отправляет на сервер адрес электронной почты, указанный пользователем в форме регистрации.  
   Предположим, что при регистрации сервер создает пользователя с уникальным CUID.  
   Отправка адреса на сервер осуществляется с целью получения уникального CUID.  
   Сервер отвечает уникальным CUID, который отправляется с помощью метода setCustomerUserId().  
   Продолжите эту процедуру, чтобы создать триггер и вкладку.
3. Добавьте новый тег для атрибуции подписок после загрузки страницы благодарности.![Если вы реализуете веб-S2S, учтите, что вам может потребоваться уведомить PBA, когда вы связываете CUID с идентификатором веб-посетителя в вашем бэкенде.](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. Присвойте тегу отдельное имя и выберите тип тега «Пользовательский HTML» ![GoogleTag.jpg](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```html
   <script>
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
            res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
   </script>
   ```
5. Разверните **Расширенные настройки**, затем **Последовательность тегов** под текстовой областью и убедитесь, что он настроен на запись конверсии после выполнения тега.

   <Image align="center" alt="Фрагмент кода обязателен" src="https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png" />
6. Установите триггер для тега конверсии, чтобы указать, когда тег конверсии должен срабатывать (в приведенном ниже примере он срабатывает при загрузке страницы благодарности).

   <Image align="center" alt="Триггер настроен на срабатывание при загрузке страницы «Спасибо»" src="https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png" />

</Tab>
</Tabs>

Функция setCustomerUserId может быть отправлена на любом этапе пользовательского потока, например, после входа и регистрации пользователя. AppsFlyer использует самый последний отправленный CUID, чтобы обновить для текущего наблюдаемого пользователя прошлые или будущие точки взаимодействия и события.

Используйте то же значение CUID, что и в функции setCustomerUserd в мобильном приложении (см. мобильный setCustomerUserId для: <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid#установка-cuid">iOS</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid#установка-cuid">Android,</Anchor> Unity).

</Accordion>

<div id="addtional-information" />

## Дополнительные сведения

<div id="web-sdk-cookies" />

<Accordion title="Файлы cookie для веб-SDK">

Файлы cookie, перечисленные в следующей таблице, устанавливаются или используются в веб-SDK на вашем сайте.

В таблице используются следующие сокращения:

* AMP: Технология ускоренных мобильных страниц (Accelerated Mobile Pages)
* CDN: Сеть доставки контента (Content Delivery Network)
* 3PC: Сторонние файлы cookie (Third-party Cookies)

| Имя файла cookie | Домен | Срок действия | Когда применяется | Подробности |
| --- | --- | --- | --- | --- |
| afUserid | Домен вашего сайта | 395 дней | не-AMP | Идентификация пользователя в контексте событий загрузки и навигации по сайту |
| AF\_SYNC | Домен вашего сайта | 1 неделя | не-AMP | <ul><li>Флаг, указывающий на то, что установлен конечный идентификатор пользователя</li><li>Это используется для сокращения времени загрузки сайта</li></ul> |
| af\_id | appsflyer.com | 395 дней | не-AMP, если разрешены 3PC | Идентификация пользователя в контексте событий запуска приложения и навигации |
| af\_id | onelink.me | 395 дней | не-AMP, если разрешены 3PC | Привяжите интеракции с баннером, интеракции с onelink или и то и другое к событиям запуска приложения. |
| amp-afUserid | CDN AMP или домен вашего сайта | 1 год | Для страниц, обслуживаемых с помощью AMP |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | Домен вашего сайта | 395 дней | Хранит состояние согласия PBA. Предотвращает работу SDK до получения согласия пользователя. По умолчанию не установлено — используется только когда [конфигурация согласия](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) настроена. | не-AMP |

</Accordion>

<div id="release-notes" />

<Accordion title="Заметки о выпуске веб-SDK">

| Дата | Версия | Примечания |
| --- | --- | --- |
| 01.07.2021 | 1.0 | [Сброс параметров запроса](/docs/pba-web-sdk-integration-guide#discard-query-params) |
| 01.06.2021 | 1.0 | [Внедрение политики безопасности контента (CSP)](/docs/pba-web-sdk-integration-guide#implement-a-content-security-policy-csp-policy) |
| 31.08.2020 | 1.0 | [Добавлена функция отказа и согласия на предоставление данных](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) |
| 16.04.2020 | 1.0 | Функция customerUserId() заменяет событие IDENTIFY для отправки уникального CUID |
| 30.07.2020 | 1.0 | <ul><li>Явное управление запуском/остановкой отправки событий</li><li>Изменение начального состояния по умолчанию</li></ul> |

</Accordion>

<div id="deprecations" />

<Accordion title="Прекращение поддержки">

* Уведомление о прекращении поддержки предупреждает о нашем намерении прекратить поддержку функции или метода. Функция или метод продолжает работать до даты деактивации.
* Рассматривайте уведомления о прекращении поддержки как возможность внести изменения в код.

| Дата прекращения поддержки | Дата деактивации | Подробности |
| --- | --- | --- |
| 16.04.2020 | Будет объявлено позже | **Устаревший метод:** Отправка идентификатора клиента (CUID) в параметре события customUserId с параметром eventType, установленным на "IDENTIFY".<br /><br />**Текущий метод:** Отправьте CUID с помощью функции setCustomerUserId(). |

</Accordion>

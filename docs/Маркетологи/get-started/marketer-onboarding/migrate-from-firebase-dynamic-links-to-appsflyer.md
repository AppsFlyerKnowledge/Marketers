---
title: Переход с динамических ссылок Firebase на AppsFlyer
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-06-19T09:27:37Z'
  edited_at: '2026-08-28T00:17:09Z'
  id: 16282289097105
  locale: ru
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ru/articles/16282289097105
---
> Поскольку <Anchor target="_blank" href="https://firebase.google.com/support/dynamic-links-faq">Google объявил</Anchor> о прекращении работы динамических ссылок Firebase, пришло время легко перейти на AppsFlyer.

## ![53375 Firebase migration KB image.png](https://files.readme.io/b5340a5b30c160bca2b420052fd60b23f4bfe0de6d2868f91ad4342bee36c7df-30063560499345.png)

<div id="about-the-migration" />

## О миграции

<Anchor target="_blank" href="https://firebase.google.com/docs/dynamic-links">Firebase Dynamic Links</Anchor> от Google будет выведена из эксплуатации 25 августа 2025 года. С этой даты все ссылки, обслуживаемые Firebase Dynamic Links (как на пользовательских доменах, так и в поддоменах page.link), перестанут работать, а создание новых ссылок будет отключено. Если вы используете Firebase Dynamic Links, крайне важно как можно скорее предпринять проактивные шаги и перенести свои ссылки на другую платформу, чтобы избежать сбоев на пути пользователя из ваших кампаний.

AppsFlyer OneLink позволяет легко создавать ссылки с возможностями атрибуции, перенаправления и диплинкинга в собственных или платных медиа независимо от устройства, операционной системы, канала или платформы. Сотрудничайте с AppsFlyer, чтобы создавать персонализированные пользовательские пути с учетом контекста, направлять пользователей в приложение и тем самым максимально повышать конверсию и доход. Легко перейдите от использования динамических ссылок Firebase на AppsFlyer с помощью нашего пошагового руководства по миграции

<div id="migrate-from-firebase-to-appsflyer" />

## Как перейти с Firebase на AppsFlyer

<Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors">Нажмите здесь</Anchor>, чтобы узнать, есть ли в Smart Script функции, которые могут быть более подходящими для вас.

**Чтобы перейти на AppsFlyer:**

**Необходимые условия**

Перед началом вам потребуется:

* Ваши динамические ссылки из Firebase
* Разработчик приложения

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="1. Создание аккаунта">

* Создайте аккаунт AppsFlyer
* <Anchor target="_blank" href="/marketers/ru/docs/user-management">Добавьте пользователей аккаунта с соответствующими правами</Anchor>.

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="2. Добавление приложения">

* <Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer">Добавьте приложение</Anchor> в AppsFlyer.
* [Необязательно] Измените заданное по умолчанию <Anchor target="_blank" href="/marketers/ru/docs/set-up-re-attribution-window">окно реатрибуции</Anchor> в 90 дней, чтобы оно соответствовало вашему определению активных пользователей.

![добавление](https://files.readme.io/7f7bab2277d0f45434618d28714c727ccbb9e414192b765dd22551bcbd5b0a37-16950840602769.png)

</Accordion>

<div id="step-3-create-a-onelink-template" />

<Accordion title="3. Настройка шаблона OneLink">

**Для этого шага нужны и вы, и ваш разработчик приложений**.

Шаблон необходим для создания ссылок и опыта конечных пользователей. Он лежит в основе логики перенаправления для всех ссылок OneLink, которые вы создаете для различных маркетинговых кампаний.

* <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Создайте шаблон OneLink</Anchor>
  * Маркетолог должен быть пользователем AppsFlyer с правами администратора <Anchor target="_blank" href="/marketers/ru/docs/user-management">или иметь разрешение на добавление/редактирование шаблонов OneLink.</Anchor>

</Accordion>

<div id="step-4-set-up-the-appsflyer-sdk" />

<Accordion title="4. Настройка пакета SDK">

**Для этого шага нужен ваш разработчик приложения**.

SDK AppsFlyer, интегрированный в приложение, является связующим звеном между приложением и платформой AppsFlyer. Он обеспечивает:

* Диплинкинг — SDK позволяет реализовать унифицированный диплинкинг (UDL)
* Атрибуция — пакет SDK сообщает об установках приложения, открытиях приложений, внутренних событиях приложения и т. д.

Интегрируйте SDK AppsFlyer в свое приложение, выполнив следующие действия.

<div id="appsflyer-sdk-integration-steps" />

#### Интеграция AppsFlyer SDK

1. Интегрируйте SDK AppsFlyer в приложение.  
   См. руководства по интеграции SDK для <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">Android</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">iOS</Anchor>.
2. Сопоставьте внутренние события приложения, которые вы хотите регистрировать, с помощью схем AppsFlyer.  
   Это можно сделать через <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview">SDK</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Обработка SDK Firebase.  
   Что делать с SDK Firebase:  
   Вы можете перейти исключительно на AppsFlyer, или одновременно использовать оба SDK в течение нескольких недель. Смотрите описание этих вариантов в таблице ниже.

| Вариант | Что происходит после  <br />выпуска обновленной версии приложения | Эффект |
| --- | --- | --- |
| Удалить SDK Firebase (рекомендуется) | Новые установки и обновления регистрирует только AppsFlyer.  <br />Firebase по-прежнему отображает события, выполненные пользователями, пока пользователи не обновят свое приложение. | <ul><li>Быстрый переход.</li><li>Отсутствие двойной атрибуции.</li><li>Позволяет увидеть, есть ли у вас какие-либо устаревшие версии приложений с Firebase SDK.</li></ul> |
| Сохранить SDK Firebase в течение переходного периода | Атрибутируют новые установки и регистрируют события и AppsFlyer, и Firebase. Позже удалите Firebase SDK. | <ul><li>Возможна проверка данных. Это означает, что вы можете сравнивать данные AppsFlyer и Firebase.</li><li>Двойная атрибуция может вызвать двойные расходы в рекламных сетях.</li><li>Повышенная нагрузка.</li></ul> |

4. После выполнения всех задач по миграции выпустите обновленную версию приложения с SDK AppsFlyer. Новые пользователи будут атрибутироваться через AppsFlyer.   
   **Примечание**:
   * Обязательно обновите приложение для магазинов iOS, Google Play и всех независимых площадок для Android.
   * Ваше приложение для Android может быть выложено на неофициальных сайтах APK, даже если вы этого не знаете (чтобы это выяснить, введите в интернете название пакета вашего приложения). Сайтам APK требуется некоторое время для обновления до последней версии, поэтому они могут привлекать органических пользователей, которые устанавливают старые версии без SDK AppsFlyer.
   * Обновление приложения в магазинах приложений может занять пару дней. Пользователи, устанавливающие приложение в этот период, могут получить предыдущую версию.

</Accordion>

<div id="step-5-understand-parameter-mapping" />

<Accordion title="5. Общие сведения о сопоставлении параметров">

**Для этого шага нужен ваш разработчик приложения**.

Узнайте, как параметры динамических ссылок Firebase сопоставляются с соответствующими параметрами AppsFlyer.

Правильное сопоставление и понимание соответствующих параметров гарантирует, что ваши ссылки получат одинаковые результаты.

В таблице ниже перечислены все параметры Firebase и соответствующие параметры AppsFlyer.

Используйте эту таблицу в качестве справочника по всем параметрам, которые вы используете в настоящее время при переходе на AppsFlyer.

<div id="note" />

> 📘 **Примечание:**
>
> Если параметр Firebase отсутствует в списке, это связано с тем, что AppsFlyer покрывает его в настройке шаблона OneLink без необходимости указывать параметр в ссылках.

<table><thead><tr><th>Группировки</th><th>Firebase</th><th>AppsFlyer:</th><th>Описание</th></tr></thead><tbody><tr><td>Мобильные параметры</td><td>link</td><td><ul><li>af_dp</li><li>deep_link_value</li></ul></td><td><ul><li> <strong>af_dp</strong> — это схема URI, используемая в качестве резервного метода запуска приложений для iOS и Android.</li><li> Значение <strong>deep_link_value</strong> — это имя для определенного контента в приложении, на который будут перенаправлены пользователи.</li></ul></td></tr><tr><td> <br/><span>Параметры Android</span> </td><td>afl</td><td>af_android_url;</td><td>Позволяет перенаправлять пользователей Android на настроенную веб-страницу.</td></tr><tr><td rowspan="2"> <span>Параметры iOS</span><br/><br/><br/> </td><td>ifl</td><td>af_ios_url;</td><td>Позволяет перенаправлять пользователей iOS на настроенную веб-страницу.</td></tr><tr><td>efr</td><td>af_force_deeplink</td><td>Используется для принудительного открытия приложения iOS по схеме URI, заданной в параметре af_dp. Без этого приложение не будет открываться по схеме URI.</td></tr><tr><td>URL-адрес другой платформы</td><td>ofl</td><td>af_web_dp.</td><td>Позволяет перенаправлять пользователей настольных компьютеров на настроенную веб-страницу.</td></tr><tr><td rowspan="3"> <br/>Теги для соцсетей<br/><br/> </td><td>st</td><td>af_og_title</td><td>Используется для настройки заголовков контента в социальных сетях.</td></tr><tr><td>sd</td><td>af_og_description</td><td>Используется для настройки описания контента в социальных сетях.</td></tr><tr><td>si</td><td>af_og_image</td><td>Используется для настройки изображений для контента в социальных сетях.</td></tr><tr><td rowspan="5"><p>Аналитические параметры <br/><br/><br/><br/> </p></td><td>utm_source</td><td>pid</td><td>Медиа-источник</td></tr><tr><td>utm_medium</td><td>af_channel</td><td>Определяет каналы медиа-источников, по которым распространяется ваша реклама.</td></tr><tr><td>utm_campaign</td><td>c</td><td>Название кампании</td></tr><tr><td>utm_term</td><td>af_keywords</td><td>Список ключевых слов для SMS кампаний.</td></tr><tr><td>utm_content</td><td>af_adset</td><td>Коллекция объявлений, связанных с кампанией.</td></tr></tbody></table>

</Accordion>

<div id="step-6-create-onelink-links-with-mapped-parameters" />

<Accordion title="6. Создайте ссылки OneLink с сопоставленными параметрами">

Используя сопоставленные параметры, вы можете создавать ссылки OneLink в шаблоне OneLink.

Ссылки можно создавать с помощью <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">дэшборда AppsFlyer</Anchor>, <Anchor target="_blank" href="/marketers/ru/docs/perform-onelink-bulk-actions-via-csv">массово</Anchor> через CSV, программно с помощью <Anchor target="_blank" href="/marketers/ru/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">нашего API OneLink</Anchor>, в <Anchor target="_blank" href="/marketers/ru/docs/user-invite-attribution">SDK</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/understand-onelink-short-vs-long-urls">с помощью длинных ссылок</Anchor>.

Используйте следующую таблицу, чтобы определить, какой метод лучше всего подходит для вашего использования.

| Firebase | AppsFlyer: | Используйте его, если | Примечания |
| --- | --- | --- | --- |
| Консоль Firebase | <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">Страница управления ссылками</Anchor> | Вы хотите создавать ссылки OneLink одну за другой. Таким образом, вы можете использовать все функции и возможности OneLink |  |
| API для создания динамических ссылок | <Anchor target="_blank" href="/marketers/ru/docs/user-invite-attribution">SDK (пакет средств разработки ПО)</Anchor> | Вы хотите создавать программно генерируемые в приложении ссылки для таких целей, как приглашения пользователей и рефералы | <ul><li>Требуется разработчик iOS или Android</li></ul> |
| Firebase REST API | <Anchor target="_blank" href="/marketers/ru/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> | Вы хотите создавать ссылки программно вне мобильного приложения | <ul><li>Требуется разработчик</li><li>Недоступно на бесплатном тарифном плане</li></ul> |
| Ручное создание ссылок | <Anchor target="_blank" href="/marketers/ru/docs/understand-onelink-short-vs-long-urls">Длинные ссылки</Anchor> | Вы хотите вручную создать ссылку с параметрами запроса. Используйте, если вам не нужны короткие ссылки. Например, если ссылка будет находиться за кнопкой или баннером |  |
|  | <Anchor target="_blank" href="/marketers/ru/docs/perform-onelink-bulk-actions-via-csv">Массовые ссылки</Anchor> | Вы хотите массово перенести все свои динамические ссылки Firebase в AppsFlyer.<br /><br />Это рекомендуется для быстрого переноса всех ваших ссылок без каких-либо ошибок | <ul><li>Требуется предварительный шаг: [сопоставление ключей и значений параметров ссылки с соответствующими параметрами Firebase](/docs/migrate-from-firebase-dynamic-links-to-appsflyer#map-parameters)</li><li>Недоступно на бесплатном тарифном плане.</li></ul> |
|  | <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers">Умный баннер</Anchor> | Кто нужен — разработчик приложений |  |
|  | <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors">Smart Script</Anchor> | Если вы хотите динамически создать длинную ссылку на веб-странице для перехода из веба в приложение |  |

</Accordion>

<div id="see-also" />

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/brand-onelink-with-your-domain">Брендированные домены</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/using-firebase-and-google-tag-manager-with-appsflyer-overview">Использование Firebase и Google Tag Manager с AppsFlyer — Обзор</Anchor>

<div data-zendesk-anchors="overview=%D0%BE-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01J7ZPPQ340PNQ70FZAQY4GBZ1=%D0%BE-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01H8K961JHRXNQHBVN930XW70Q=%D0%BE-%D0%BC%D0%B8%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 how-to-migrate-from-firebase-to-appsflyer=%D0%BA%D0%B0%D0%BA-%D0%BF%D0%B5%D1%80%D0%B5%D0%B9%D1%82%D0%B8-%D1%81-firebase-%D0%BD%D0%B0-appsflyer 01H8K961JHCK0Z4GTTHCAKF98E=%D0%BA%D0%B0%D0%BA-%D0%BF%D0%B5%D1%80%D0%B5%D0%B9%D1%82%D0%B8-%D1%81-firebase-%D0%BD%D0%B0-appsflyer h_01J5QWWGWGDBEF8RY3DZ5XAN3G=step-1-create-an-appsflyer-account h_01J5QWWGWGN17673GYFZWPNKQR=step-2-add-your-app h_01J5QWWGWGKJPRCG9N93B8KBYW=step-3-create-a-onelink-template h_01J5QWWGWGCQFHBQ9EC0QTPF4S=step-4-set-up-the-appsflyer-sdk appsflyer-sdk-integration-steps=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-appsflyer-sdk h_01J5QXST2K890DV7QS6S9K3A01=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-appsflyer-sdk h_01J5QWWGWGPRF5DRMMQ14BJCFA=step-5-understand-parameter-mapping 01H8K961JHBXVKXM0XQYY605EQ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01J5QWWGWG3ST19WDRZXN8FK8Q=step-6-create-onelink-links-with-mapped-parameters h_01HE7SZPKKQETH260G45V0D0HN=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

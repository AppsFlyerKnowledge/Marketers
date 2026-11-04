---
title: Начало работы с Web Performance Measurement
metadata:
  keywords:
    - Attribution
    - Agencies
    - Web Attribution
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T19:35:31Z'
  edited_at: '2026-08-31T00:22:46Z'
  id: 43529798016401
  locale: ru
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ru/articles/43529798016401
---
> **Краткий обзор:** Воспользуйтесь инструкциями по подключению из этого руководства, чтобы настроить Web Performance Measurement. После настройки вы сможете измерять посещения сайта и веб-события и атрибутировать их маркетинговым источникам, понимать, какие источники приводят к значимым результатам на сайте, а также использовать кроссплатформенное измерение.

<div id="about-web-performance-measurement" />

## Об инструменте Web Performance Measurement

Web Performance Measurement позволяет связать действия на вашем сайте, такие как посещения и веб-события, с маркетинговыми источниками, которые привели к ним. Иными словами, инструмент показывает, какие медиаисточники и рекламные кампании привлекают пользователей на ваш сайт и влияют на их дальнейшие действия, позволяя измерять эффективность и оптимизировать ROI.

<div id="create-a-web-app-in-appsflyer" />

### Создайте веб-приложение в AppsFlyer

<Embed title="Начало работы с Web Performance Measurement" typeOfEmbed="youtube" url="https://www.youtube.com/embed/MOn_UsirYCU" providerUrl="https://www.youtube.com" />

<div id="set-up-network-integrations-postbacks-and-cost-measurement" />

### Настройка интеграций с рекламными сетями, постбэков и измерения затрат

<Embed title="Начало работы с Web Performance Measurement" typeOfEmbed="youtube" url="https://www.youtube.com/embed/-sYIv3YQEwo" providerUrl="https://www.youtube.com" />

Чтобы начать измерять посещения сайта и веб-события в AppsFlyer, выполните шаги из приведенного ниже чек-листа по настройке Web Performance Measurement.

<div id="web-performance-measurement-setup-checklist" />

## Чек-лист по настройке Web Performance Measurement

В таблице ниже перечислены основные задачи по настройке, их исполнители и порядок выполнения, необходимые для начала сбора данных о посещениях сайта и веб-событиях в AppsFlyer.

| Выручка | Необходимые действия | Где узнать больше | Кто участвует |
| --- | --- | --- | --- |
| 1. Создайте веб-приложение | Перейдите на страницу **страницу "Настройки приложения"**<ul><li>Скопируйте **Web SDK ID** и поделитесь им со своим разработчиком.</li><li>Настройте **часовой пояс** и **валюту** для отчетов.</li><li>Выберите **Исключенные домены** .</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/adding-an-app-to-appsflyer#web">Настройте параметры веб-приложения.</Anchor></li></ul> | Маркетолог |
| 2. (Необязательно) Создайте линейку продуктов для кроссплатформенного LTV | Чтобы включить кроссплатформенную атрибуцию и измерение жизненной ценности пользователя (LTV) на протяжении всего его пути, создайте продуктовую линейку и либо свяжите с ней соответствующие приложения и веб-ресурсы, либо добавьте веб-приложение в существующую линейку продуктов. | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/product-line-group-apps-for-cross-platform-attribution">Создать линейку продуктов.</Anchor></li></ul> | Маркетолог |
| 3. Установите и настройте Web SDK. | Интегрируйте веб- SDK AppsFlyer в свой веб-сайт. | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/integrate-appsflyer-web-sdk">Интегрируйте Web SDK в свой веб-сайт.</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/use-the-web-sdk-test-page">Протестируйте интеграцию Web SDK</Anchor></li></ul> | Разработчик |
| 4. Отправляйте веб-данные с помощью S2S API | Используйте API Server-to-Server (S2S), чтобы отправлять данные о посещениях сайта и веб-событиях в AppsFlyer непосредственно с вашего сервера. Используйте его вместе с Web SDK, чтобы расширить охват измерения и дополнить данные о событиях, или отдельно — для полностью серверной интеграции. | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/server-to-server-s2s-api-for-web-performance-measurement">Настройте S2S AP для Web Performance Measurement</Anchor></li></ul> | Инженер по бизнес-аналитике (BI) |
| 5. Настройте параметры атрибуции веб-приложения. | На странице **Настройки приложения** настройте параметры атрибуции веб-приложения, например окна атрибуции и события привлечения пользователей.  <br />**Примечание:** Пользовательские события привлечения пользователей можно выбрать только после интеграции Web SDK с вашим сайтом. | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/configure-web-performance-measurement-settings">Настройте параметры атрибуции веб-приложения.</Anchor></li></ul> | Маркетолог |
| 6. Создание URL-адресов для Web Performance Measurement | Создавайте URL-адреса, используя правильные параметры атрибуции, чтобы получить наиболее точные и гранулярные результаты атрибуции. | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/choose-attribution-parameters-for-landing-page-urls">Выберите параметры атрибуции для URL-адресов целевых страниц.</Anchor></li></ul> | Маркетолог |
| 7. Настройте интеграцию с поддерживаемыми партнерами. | Активируйте партнеров и настройте постбэки, отправляемые им.<br />Поддерживаемые партнеры:<ul><li>Google реклама</li><li>Meta Ads</li><li>TikTok Ads</li><li>Реклама Snapchat</li></ul> | Создание веб-кампаний для веб-приложений с:<ul><li><Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-create-web-campaigns-for-website-apps">Google реклама</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/meta-ads-create-web-campaigns-for-website-apps">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/tiktok-for-business-create-web-campaigns-for-website-apps">TikTok Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/snapchat-create-web-campaigns-for-website-apps">Реклама Snapchat</Anchor></li></ul> | Маркетолог |
| 8. Экспорт данных Web Performance Measurement из Data Locker | Настройте **Data Locker** для отчетов Web Performance Measurement с необработанными данными, чтобы команды бизнес-аналитики и аналитики могли анализировать пользовательские пути на сайте. | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/export-web-performance-measurement-report-data-from-data-locker">Экспорт данных Web Performance Measurement из Data Locker</Anchor></li></ul> | Маркетолог / BI-инженер |
| 9. Просматривайте ваши веб-данные в кроссплатформенном дэшборде | Посмотрите, как веб-сессии и события отображаются на кроссплатформенном дэшборде. | <ul><li><Anchor target="_blank" href="/marketers/ru/docs/my-dashboards#веб-атрибуция-на-кроссплатформенном-дэшборде">Веб-атрибуция на кроссплатформенном дэшборде</Anchor></li></ul> | Маркетолог |
| 10. Измерьте стоимость веб-кампаний.<br /><br />**(Только для ROI360)** | Подключите ваше веб-приложение к интеграциям затрат в **разделе «Настройки затрат»** для поддерживаемых сетей с собственной атрибуцией (SRN): Google, Meta (Facebook), Snapchat и TikTok.  <br />  <br />После подключения AppsFlyer передаёт данные о затратах, кликах и показах по веб-кампаниям практически в реальном времени, в отчетах стоимости ETL и разделе «Мои дэшборды».  <br />  <br />Для **расширенного пакета ROI360** добавьте свое веб-приложение в список включенных приложений на странице конфигурации стоимости ETL.  <br />  <br />**Примечание:** Ссылки атрибуции должны содержать идентификатор кампании в URL целевой страницы. | Подключите своё веб-приложение к интеграциям затрат:<ul><li><Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-create-web-campaigns-for-website-apps#измеряйте-данные-веб-атрибуции-с-учётом-затрат-на-веб-трафик">Google реклама</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/meta-ads-create-web-campaigns-for-website-apps#измеряйте-данные-веб-атрибуции-вместе-с-данными-о-затратах-на-веб">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/snapchat-create-web-campaigns-for-website-apps#измеряйте-данные-веб-атрибуции-вместе-с-данными-о-затратах-на-веб">Реклама Snapchat</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Настройка Cost ETL</Anchor></li></ul> | Маркетолог / BI-инженер |

<div data-zendesk-anchors="about-appsflyer-web-attribution=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B5-web-performance-measurement h_01KGN43TYPKCQ7H3SRRHHPT387=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B5-web-performance-measurement how-to-create-a-web-app-in-appsflyer=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B2-appsflyer h_01KVSNN9H462X8DVYBS6TJ8JXQ=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%B9%D1%82%D0%B5-%D0%B2%D0%B5%D0%B1-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B2-appsflyer how-to-set-up-network-integrations-postbacks-and-cost-measurement=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B9-%D1%81-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%B8-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82 h_01KVSNSSZ7QY090JVWVTRF88ND=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B9-%D1%81-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%BC%D0%B8-%D1%81%D0%B5%D1%82%D1%8F%D0%BC%D0%B8-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%B8-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82 appsflyer-web-attribution-setup-checklist=%D1%87%D0%B5%D0%BA-%D0%BB%D0%B8%D1%81%D1%82-%D0%BF%D0%BE-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B5-web-performance-measurement h_01KGN43TYP1EV5KFQ37FC4SM0C=%D1%87%D0%B5%D0%BA-%D0%BB%D0%B8%D1%81%D1%82-%D0%BF%D0%BE-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B5-web-performance-measurement" />

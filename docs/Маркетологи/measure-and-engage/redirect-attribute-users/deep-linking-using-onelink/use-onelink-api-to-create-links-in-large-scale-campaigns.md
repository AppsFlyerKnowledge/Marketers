---
title: Используйте API OneLink для создания ссылок в масштабных кампаниях
metadata:
  keywords:
    - api
    - Premium
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Premium
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2018-06-27T12:00:29Z'
  edited_at: '2026-08-19T00:33:58Z'
  id: 360001250345
  locale: ru
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ru/articles/360001250345
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор:** API OneLink позволяет вовлекать конечных пользователей и использовать собственные медиа, создавая персонализированные ссылки для крупномасштабных кампаний, СМС-рассылок и т.д. Для реализации требуется участие рекламодателя и разработчика. Используйте его, чтобы создавать бесшовные кросс-канальные пути, повышать вовлеченность и улучшать конверсию.

<div id="about-onelink-api" />

## OneLink API

OneLink API — это премиум-функция, которая позволяет превратить любой собственный канал в прямой путь к вашему мобильному приложению. Программно создавая персонализированные короткие ссылки, вы можете предоставлять персонализированные пути пользователей в масштабе, повышать вовлеченность и стимулировать более высокую конверсию через СМС, электронную почту, веб-сайты, публикации в социальных сетях и другие каналы. Передайте разработчику идентификатор OneLink и ключ API OneLink.

* https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link
* Параметры, связанные с атрибуцией, такие как медиа-источник, кампания или ресурс, используемые для измерения и отслеживания маркетинговых инициатив.**Примечание**: Параметр медиа-источника (pid) является обязательным.
* Параметры для персонализации, которые позволяют настроить индивидуальный пользовательский интерфейс при открытии приложения по соответствующей ссылке. Эти параметры позволяют отправлять пользователей на настраиваемый контент в приложении, например на страницу определенного продукта, код купона или рекламную акцию.
* Автоматически создавайте большое количество коротких ссылок и <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-qr">QR-кодов</Anchor>.
* Настраивайте TTL (Time To Live) и поведение продления для каждого кейса. <Anchor target="_blank" href="/marketers/ru/docs/bulletin-onelink-short-url-ttls-automatically-extend">Узнать больше</Anchor>
* Применяйте строгую валидацию параметров, чтобы обеспечить предсказуемое поведение перенаправления и надежное измерение.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota">Получайте данные об использовании квоты</Anchor> для управления потреблением.

<div id="example" />

> 📄 **Пример**
>
> Глобальное туристическое приложение ежедневно генерирует миллионы контекстных коротких ссылок для CRM, электронной почты и QR-кодов. Используя OneLink API v2, их платформа автоматизации создает персонализированные диплинки, учитывающие локаль, уровень лояльности и конкретные разделы в приложении, — при этом обеспечивая управление и согласованное измерение на всех рынках.

<div id="get-started" />

## Начало

**OneLink API является премиум-функцией, которая используется для:**

**Необходимое условие:** учетная запись AppsFlyer. Чтобы получить доступ к OneLink API, свяжитесь со своим CSM или напишите на hello@appsflyer.com.

**Чтобы настроить API OneLink:**

1. Скопируйте <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens#типы-токенов">токен API OneLink</Anchor>.
2. <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Создайте шаблон OneLink</Anchor>.
3. Скопируйте идентификатор ID шаблона.    
   <Image align="center" alt="" src="https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg" />
4. Передайте разработчику идентификатор шаблона и токен API и попросите его следовать этим <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelinkapi_v2_overview">инструкциям</Anchor>.

<div id="dashboard" />

## **Дэшборд**

Дэшборд API OneLink отображает ваше использование API за день, месяц и три месяца. Это помогает отслеживать потребление в сравнении с ежемесячным лимитом квоты. 

**Чтобы открыть дэшборд API OneLink**: 

В AppsFlyer в боковом меню выберите **Engage** > **OneLink API**.

<div id="use-cases" />

## Использование когорты

Ниже приведены кейсы, которые показывают распространенные способы применения OneLink API для создания бесшовных контекстных путей в ваше приложение.

<div id="crossplatform-journeys-ctv-desktop-webtoapp" />

<Accordion title="Кросс-платформенные пути (CTV, настольные ПК, web-to-app)">

Создавайте краткосрочные или посессионные ссылки, которые помогают пользователям бесшовно перемещаться между устройствами. Типичные примеры включают QR-коды в ТВ-рекламе или сценарии «отсканируйте, чтобы продолжить» на настольных ПК, которые направляют пользователей прямо к нужному шагу в приложении.

**Ценность:** бесшовная непрерывность и улучшенная конверсия на разных устройствах.

</Accordion>

<div id="crmpowered-channels-sms-email-whatsapp" />

<Accordion title="Каналы на базе CRM (СМС, электронная почта, WhatsApp)">

Создавайте персонализированные короткие ссылки для каждого пользователя в момент отправки для сообщений с высоким намерением, таких как уведомления о снижении цены, листы ожидания, win-back-кампании, напоминания об оплате или сценарии входа по magic link.

**Ценность:** персонализация в масштабе с согласованной атрибуцией.

</Accordion>

<div id="offline-and-qrbased-engagement" />

<Accordion title="Офлайн- и QR-вовлеченность">

Создавайте сканируемые ссылки для материалов в магазине, чеков, упаковки или вывесок на событиях. Вы можете обновлять настройки назначения без повторной печати физических материалов.

**Ценность:** Динамическая маршрутизация и офлайн-атрибуция без повторной печати физических материалов.

</Accordion>

<div id="referral-and-advocate-sharing" />

<Accordion title="Реферальный обмен и обмен через амбассадоров">

Включите короткие ссылки для совместного использования в программах рекомендаций для инфлюенсеров, авторов контента или клиентов с настраиваемыми параметрами и маршрутизацией, готовой для атрибуции.

**Ценность:** Масштабируемое измерение и точная атрибуция для рефералов.

</Accordion>

<div id="traits-and-limitations" />

## **Характеристики и ограничения**

В этом разделе перечислены некоторые ключевые особенности и ограничения OneLink API. Сообщите ему о том, что необходимо следовать <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelink_rest_api">инструкциям для разработчиков</Anchor>.

| Специфика | Примечания |
| --- | --- |
| Ограничение квоты API | <ul><li>Ограничение по использованию API OneLink для создания, редактирования или удаления ссылок OneLink составляет 7,5 миллионов в месяц (часовой пояс UTC), на один аккаунт.</li><li>Запросы POST, PUT и DELETE учитываются в этом лимите. Запросы GET и GET QR не учитываются в квоте.</li><li>Все запросы, отправленные после превышения этой квоты, не обслуживаются; вызов API получает код статуса 429 с сообщением «Monthly quota exceeded».</li><li>Проверить, какая часть квоты уже использована и сколько осталось, можно одним из следующих способов:<br />• Откройте страницу OneLink API на платформе AppsFlyer, чтобы просмотреть историю использования за последние 4 месяца, или<br />• Используйте API GET quota, чтобы получить текущий статус квоты.<br />Вы также можете использовать <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-v2-link-quota">GET quota API</Anchor> для запуска внутренних оповещений, когда использование приближается к заданному порогу.</li></ul> |
| Видимость ссылки | <ul><li>Ссылки, созданные через API, не отображаются в списке настраиваемых ссылок OneLink на дэшборде AppsFlyer.</li></ul>af\_dp |

> 📘 **Примечание.**
>
> Новая версия OneLink API (v2) была выпущена в декабре 2025 года. Предыдущая версия (v1) устарела и продолжит работать до июня 2026 года, после чего поддерживаться не будет. В новых интеграциях следует использовать OneLink API v2. Руководство по миграции см. в <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/migrate_to_onelink_api_v2">руководстве по миграции</Anchor> в Dev Hub.

<div data-zendesk-anchors="h_01HJR5MAKKNH236MVDZ03X1B1P=onelink-api h_01HJR5MAKKTDRPS0WQ44VN594X=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 get-started=%D0%BD%D0%B0%D1%87%D0%B0%D0%BB%D0%BE h_01KATK4KWTGSHTW5BEY8TEE5JD=%D0%BD%D0%B0%D1%87%D0%B0%D0%BB%D0%BE dashboard=%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4 h_01KATKWCPHZB1MKCJ8DVDYZ1B3=%D0%B4%D1%8D%D1%88%D0%B1%D0%BE%D1%80%D0%B4 use-cases=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D1%8B h_01KAGQNZZA0NM19KV29QZ9ZDKP=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D1%8B h_01KBJ92FSTKCH9KXGWKJAF1DFH=crossplatform-journeys-ctv-desktop-webtoapp h_01KBJ92FST51NKDB465N76EX3M=crmpowered-channels-sms-email-whatsapp h_01KBJ92FST5H7V5S13TZ502VJV=offline-and-qrbased-engagement h_01KBJ92FST4FP4ZES5T643DD3R=referral-and-advocate-sharing traits-and-limitations=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KAGQP00QZ2VBE9EY3SNPHGBP=%D1%85%D0%B0%D1%80%D0%B0%D0%BA%D1%82%D0%B5%D1%80%D0%B8%D1%81%D1%82%D0%B8%D0%BA%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01KAGM8HN6FHRK73FSF0TGXSX7=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5" />

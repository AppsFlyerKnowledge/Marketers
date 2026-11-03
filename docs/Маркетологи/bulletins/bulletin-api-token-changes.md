---
title: 'Бюллетень: Изменения в токенах API'
metadata:
  keywords:
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2026-08-18T00:19:14Z'
  id: 12399683708305
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/12399683708305
---
| **Что нового?** | Чтобы обеспечить более безопасный и надежный опыт использования API, токен API V1, который был включен в URL-адреса API, отменен в пользу токена API V2, который представляет собой токен на основе JWT, передаваемый в заголовке для авторизации предъявителя.<br /><br />Токен API V1 и использующие его API прекратили свое действие с 18 сентября 2023 года. |
| --- | --- |
| **Дата вступления в силу** | 18 сентября 2023 г. |
| **Необходимые условия** | Только пользователь с правами администратора <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens#получение-токенов">может получить токен API V2</Anchor> на дэшборде AppsFlyer. |
| **Кому нужно обновить токен API?** | Рекламодатели и агентства, по-прежнему использующие токен API V1, должны обновить его. |
| **Как найти токены API V1** | Воспользуйтесь  <Anchor target="_blank" href="/marketers/ru/docs/audit-log">журналом аудита</Anchor>, чтобы отфильтровать все используемые токены API V1. Затем можно скачать данные в файл CSV:<ol><li>Перейдите на [дэшборд журнала аудита](https://hq1.appsflyer.com/audit-reader/dashboard).</li><li>Введите «API Token V1» в строку поиска.</li><li>В фильтре**Служба**  выберите только **Вызовы API** и отфильтруйте результаты.</li><li>Нажмите на значок загрузки в правом верхнем углу страницы.<br />Загрузится CSV-файл, содержащий идентификатор вашего приложения, используемую службу и URL-адрес вызова API.</li></ol> |
| **Необходимое действие** | **Обновите следующие API для токена API V2:**<ol><li>Перейдите на страницу <Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">токена API</Anchor>.</li><li>В разделе токен API V2.0 нажмите на значок **Копировать в буфер обмена**.</li><li>Для каждого из следующих API:<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">Master API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">Pull API V2 для доступа к агрегированным данным</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">Pull API V2 для доступа к сырым данным</Anchor></li></ul><ol><li>Замените URL API V1 на URL, указанный в приведенной выше документации.</li><li>Вставьте скопированный токен в заголовок аутентификации предъявителя.<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>Для API **OpenDSR**  добавьте токен в заголовок предъявителя запроса:<br />`'Authorization': 'Bearer %AuthTokenV2%'.`</li></ol></li></ol> |
| **О токенах API** | **Подробнее о токенах API:**<ul><li><Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">Управление токенами API</Anchor><ul><li><Anchor target="_blank" href="/marketers/ru/docs/master-api-user-acquisition-metrics-via-api">Master API.</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/pull-api-aggregate-data">Pull API для доступа к агрегированным данным</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/pull-api-raw-data">Сырые данные</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/send-opendsr-api-requests#формат-запроса-gdpr">OpenDSR API</Anchor></li></ul></li></ul> |
---
title: >-
  Бюллетень: Обновление интеграции API затрат Unity Ads Обновление интеграции
  API затрат Unity Ads
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2024-06-20T14:43:15Z'
  edited_at: '2026-10-19T14:38:57Z'
  id: 26078530790289
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/26078530790289
---
| **Что нового** | AppsFlyer имеет интеграцию API с Unity, которая позволяет нам получать данные о затратах. В ближайшее время API будет обновлен. Поэтому вам необходимо обновить интеграцию, чтобы продолжать получать от Unity данные о затратах. |
| --- | --- |
| **Дата обновления** | 6 августа 2024 г. |
| **Что нужно знать** | <ul><li>Unity вводит новую интеграцию API затрат.</li><li>Старая интеграция API затрат может получать данные о затратах до даты прекращения его действия 1 октября 2024 года.</li></ul> |
| **Что нужно сделать** | Чтобы продолжать получать данные о затратах после 1 октября 2024 года, необходимо обновить учетные данные для новой интеграции API затрат Unity.<br /><br />Требуются следующие учетные данные:<ul><li>Основной идентификатор организации</li><li>Секретный ключ аккаунта службы</li><li>Идентификатор ключа аккаунта службы</li></ul>Следуйте нашим инструкциям в следующих разделах, чтобы обновить интеграцию данных о затратах Unity в AppsFlyer. Интеграция состоит из 2 этапов:<ol><li>[Получите новые учетные данные Unity](/docs/bulletin-unity-ads-cost-api-integration-update#get-unity-credentials).</li><li>[Обновите интеграцию API затрат Unity, введя учетные данные в AppsFlyer.](/docs/bulletin-unity-ads-cost-api-integration-update#set-up-unity-cost-api-integration-in-appsflyer)</li></ol> |

<div id="unity-cost-api-integration-procedures" />

## Процедуры интеграции API затрат Unity

Интеграция API затрат Unity состоит из 2 этапов:

1. Получите новые учетные данные Unity.
2. Обновите интеграцию API затрат Unity, введя учетные данные в AppsFlyer.

Эти этапы описаны в следующих разделах.

<div id="get-unity-credentials" />

<Accordion title="Получение учетных данных Unity">

Для интеграции API затрат Unity требуются следующие учетные данные:

* Основной идентификатор организации
* Секретный ключ аккаунта службы
* Идентификатор ключа аккаунта службы

**Примечание.** Рекомендуется создать новый аккаунт службы Unity, чтобы получить секретный ключ и идентификатор ключа. Ниже мы приводим инструкции о том, как это сделать.

**Чтобы настроить аккаунт службы Unity и получить необходимые учетные данные для интеграции API затрат Unity**:

1. Войдите в свой аккаунт Unity Cloud.
2. В левом боковом меню выберите пункт **Grow (Unity Ads User Acquisition) (Рост (Привлечение пользователей Unity Ads)** > **Settings (Настройки**).  
    <Image align="center" alt="" src="https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png" />
3. Найдите, скопируйте и сохраните **основной идентификатор организации**.  
   Пример основного идентификатора организации: 5773102414648
4. В левом боковом меню выберите пункт **Grow (Unity Ads User Acquisition) (Рост (Привлечение пользователей Unity Ads)** > **`{}` API Management (Управление API)** и в разделе **Stats API v2.0** нажмите **Service Account (Аккаунт службы).**  
    <Image align="center" alt="" src="https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png" />
5. Нажмите **+ New (Создать)**, чтобы создать новый аккаунт службы.  
    <Image align="center" alt="" src="https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png" />
6. В разделе **Keys (Ключи)** нажмите **+ Add key (Добавить ключ)**, чтобы создать ключ для аккаунта службы.  
    <Image align="center" alt="" src="https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png" />
7. Скопируйте и сохраните **идентификатор ключа** и **секретный ключ**. **Примечание.** Это единственный раз, когда вы можете получить доступ к секретному ключу, поэтому обязательно сохраните его сейчас!
   * Пример секретного ключа аккаунта службы: b0de73b1-b3ad-4175-bf9b-4913a0ff83ec
   * Пример идентификатора ключа аккаунта секретной службы: a0X\_cqHiXH4ABPS1Qr9TCy6EJdvG8ql5  
      <Image align="center" alt="" src="https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png" />
8. В разделе **Organization roles (Роли организации)** нажмите **+ Manage organization roles (Управление ролями организации)**.  
    <Image align="center" alt="" src="https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png" />
9. В разделе **Edit roles in organization (Редактирование ролей в организации)** установите для опции **Growth (Рост)** параметр **Advertise Stats API MMP Viewer**.  
    <Image align="center" alt="" src="https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png" />

</Accordion>

<div id="set-up-unity-cost-api-integration-in-appsflyer" />

<Accordion title="Обновление интеграции API затрат Unity в AppsFlyer">

**Чтобы обновить API затрат Unity в AppsFlyer**:

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Активные интеграции** и выберите **Unity**.
2. Нажмите **Управление интеграцией**.
3. Откройте вкладку **Затраты** интегрированного партнера.
4. Включите переключатель **Получать данные о затратах**. Появятся инструкции, как подключиться к данным партнера.
5. Введите свои учетные данные Unity.
6. Нажмите **Сохранить затраты**.
7. Нажмите **Тестировать подключение**.  
   * API теперь активен. AppsFlyer собирает данные от партнеров 6 раз в день, в среднем каждые четыре часа.

<Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data">Узнайте больше о подключении интеграций данных о затратах</Anchor>

</Accordion>

<div data-zendesk-anchors="unity-cost-api-integration-procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-api-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82-unity h_01J11ZP5XG6VDSQKRWASAYK4QJ=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-api-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82-unity h_01J14M3C6WNXPJJQHVWVNFB4GS=get-unity-credentials h_01J11ZHPJDZDZ7S24ZQK58B2FN=set-up-unity-cost-api-integration-in-appsflyer" />

---
title: >-
  Платформа совместной работы с данными (DCP) — интеграция с Salesforce Data
  Cloud
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-02-29T14:30:51Z'
  edited_at: '2026-10-19T14:04:13Z'
  id: 22977208909969
  locale: ru
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ru/articles/22977208909969
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Кратко:** интеграция с Salesforce Data Cloud позволяет перенести ваши данные первой стороны на платформу совместной работы с данными AppsFlyer одним нажатием кнопки.

> 🚧 **Прежде чем начать**
>
> Перед интеграцией с Salesforce Data Cloud необходимо **установить расширение приложения AppsFlyer** из Salesforce AppExchange. Это должен выполнить пользователь с правами администратора Salesforce и разрешением на загрузку пакетов AppExchange.
>
> 1. Перейдите на <Anchor target="_blank" href="https://appexchange.salesforce.com/appxListingDetail?listingId=6c756ddf-777c-42fc-9eaf-d96ca36ed2e3">страницу AppsFlyer</Anchor> в Salesforce AppExchange.
> 2. Нажмите **Get It Now**.
> 3. Следуйте шагам, описанным в <Anchor target="_blank" href="https://developer.salesforce.com/docs/atlas.en-us.appExchangeInstallGuide.meta/appExchangeInstallGuide/appexchange_install_installation.htm">руководстве по установке приложения</Anchor>.
>
> После успешной установки процесс завершен, и дополнительная настройка пакета не требуется.

## Настройка интеграции

Интеграция включает создание подключения к Salesforce Data Cloud, а затем создание источников. Для аутентификации учетной записи Salesforce требуется только одно подключение. С помощью этого подключения можно создать несколько источников на основе таблиц Salesforce.

> 📘 **Примечание:**
>
> Если вы уже настроили подключение к Salesforce Data Cloud, создать еще одно не получится.

### Создание подключения к Salesforce Data Cloud

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Data Clean Room**.
2. В правом верхнем углу страницы нажмите **Manage connections** > **+ New connection**.
3. В диалоговом окне **New connection** выберите **Data providers** > **Salesforce Data Cloud**.  

   <Image alt="salesforce-data-cloud-new-connection.jpg" src="https://files.readme.io/6b240e0cff3f0bc9e6b7f6eaf45520a78252e1619769a696855e8d68d322ce60-23301617982353.jpg" width="517px" />
4. Нажмите **Log in to Salesforce**.
5. Продолжите процесс аутентификации и предоставьте Salesforce доступ к AppsFlyer.   
   **Примечание:** если аутентификация не удалась, вы вернетесь в диалоговое окно **New connection**, чтобы повторить попытку.
6. После успешной аутентификации вы вернетесь в диалоговое окно **New connection**, где увидите, что подключение к Salesforce активно. Теперь можно продолжить и создать источник.
7. Нажмите **Create source** и следуйте [инструкциям ниже](#создание-источника-salesforce-data-cloud), чтобы создать источник Salesforce Data Cloud.

### Создание источника Salesforce Data Cloud

После аутентификации учетной записи Salesforce и настройки подключения к Salesforce Data Cloud следующим шагом будет создание источников. Эти источники предоставляют AppsFlyer необходимые данные при каждом обновлении.

Перейдите на вкладку **Источники** одним из следующих способов:

* После выполнения предыдущего шага кликните **Создать источник**.
* В боковом меню AppsFlyer перейдите в **Collaborate** > **Data Clean Room** > **+ New Source** в правом верхнем углу страницы.

> 📘 **Примечание:**
>
> При создании источника убедитесь, что в AppsFlyer не отправляются данные с ограниченным доступом.

**Чтобы создать источник:**

1. **Укажите имя источника:** Введите <Anchor target="_blank" href="/marketers/ru/docs/data-clean-room-working-with-sources#1-name-the-source">имя для источника</Anchor> и нажмите **Далее**.
2. **Задайте местоположение источника:**
   * **Выберите подключение:** После добавления подключения поле Salesforce Data Cloud заполняется автоматически. Если нет, выберите его из списка подключений.
   * **Таблица или представление:** После выбора подключения Salesforce Data Cloud названия таблиц и представлений из вашей учетной записи Salesforce заполняются автоматически. Выберите таблицу или представление и кликните **Далее**.  

     ![create-source-sf-3-steps.jpg](https://files.readme.io/44549ef1cd59b99610944c604c1cdfd4d598352cd106877fab3a301ce14650f8-23306070497169.jpg)
3. **Настройте схему источника:** После выбора таблицы или представления названия и типы полей заполняются автоматически. Вы можете изменить типы полей или удалить ненужные поля, выбрав значок корзины в конце строки поля.  
   **Примечание:** Убедитесь, что хотя бы один тип поля используется как идентификатор. Например, CUID, идентификатор платформы, идентификатор AppsFlyer ID и идентификатор ID с хешем SHA256.
4. Нажмите **Save** (Сохранить). Новый источник отображается в списке всех существующих источников.

<div data-zendesk-anchors="h_01HPKB2ERPGD2PS4JBSDGYW3MC=%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5-%D1%87%D0%B5%D0%BC-%D0%BD%D0%B0%D1%87%D0%B0%D1%82%D1%8C set-up-the-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01HRW9TK3YZV32CXRM6Q2HCHS4=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01HRSFKVQNJ264M16A9X9AEP53=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 create-a-salesforce-data-cloud-connection=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA-salesforce-data-cloud h_01HRSDCVMHQ6C5R6R4S5XRT5KQ=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA-salesforce-data-cloud create-a-salesforce-data-cloud-source=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0-salesforce-data-cloud h_01HRSG0P4Q38WHGQWBY3S3D11W=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0-salesforce-data-cloud h_01HRVPJ801B0VC879APZCGKDNE=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1" />

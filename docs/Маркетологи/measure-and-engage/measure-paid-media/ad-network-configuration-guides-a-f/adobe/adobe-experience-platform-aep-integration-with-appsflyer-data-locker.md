---
title: Интеграция Adobe Experience Platform (AEP) с AppsFlyer Data Locker
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2023-03-19T06:54:23Z'
  edited_at: '2026-10-19T14:20:37Z'
  id: 13856826626321
  locale: ru
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/ru/articles/13856826626321
---
> **Кратко:** Настройте интегрированное решение с Adobe Experience Platform (AEP), чтобы отправлять данные о событиях на уровне raw в озеро данных Adobe. AEP — это слой данных для всех клиентов, централизующий данные в Adobe — платформе данных о клиентах, которая фиксирует пути пользователей, предоставляет их и позволяет анализировать.

<div id="overview" />

## Информация о компании

Интеграция Data Locker—AEP позволяет использовать данные AppsFlyer в Adobe Experience Platform. В интеграции используется готовый компонент (OOTB) на базе платформы данных о клиентах в реальном времени (RTCDP). Чтобы загрузить данные AppsFlyer в Adobe Experience Platform (AEP), клиенты должны сначала настроить подключение бакета Data Locker (GCS и AWS), а затем настроить AEP для загрузки данных из бакета в существующий или новый набор данных.

<div id="setting-up-the-integration" />

## Настройка интеграции

<span id="prerequisites"></span>**Необходимые условия**:

* Подписка <Anchor target="_blank" href="/marketers/ru/docs/data-locker">Data Locker</Anchor> Data Locker
* Учетная запись <Anchor target="_blank" href="https://business.adobe.com/products/experience-platform/adobe-experience-platform.html">Experience Platform</Anchor> с правами администратора

**Чтобы настроить интеграцию**:

1. <span id="step-1-aws-create-an-aws-iam-user-with-bucket-access"></span>Создайте бакет с разрешениями для Data Locker. Следуйте инструкциям для хранилища <Anchor target="_blank" href="/marketers/ru/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>.
2. Настройте Data Locker. Следуйте <Anchor target="_blank" href="/marketers/ru/docs/data-locker-for-marketers#set-up-data-locker">инструкциям по настройке Data Locker</Anchor>, и при выборе бакета GCS или AWS обязательно установите флажок **Make this connection compatible with Adobe Experience Platform**.
3. Настройте схему Data Locker в AEP.
   1. Войдите в AEP, используя учетные данные администратора.
   2. Создайте класс событий Adobe XDM [experience event](https://experienceleague.adobe.com/docs/experience-platform/xdm/classes/experienceevent.html?lang=en#).
   3. Добавьте новую группу полей для полей AppsFlyer.
   4. Создайте первое поле как объектное поле с именем AppsFlyer.  
      Это родительское поле. Все остальные создаваемые поля будут дочерними для этого объектного поля.
   5. Добавьте остальные поля схемы Data Locker. Если вы используете Adobe CJA, отметьте customer\_user\_id как бизнес-идентификатор.
4. Настройте источник бакета в AEP.
   1. В AEP добавьте коннектор бакета (тот же бакет AWS или GCS, который вы использовали в Data Locker).
   2. Заполните обязательные данные для аутентификации.
   3. Нажмите **Connect to source**.
5. Настройте поток данных в AEP.
   1. В разделе **AEP Select data** выберите соответствующие отчеты AppsFlyer Data Locker из списка папок бакета.
   2. Установлено:
      * Формат данных — Delimited.
      * Разделитель — ",".
      * Тип сжатия — Gzip.
   3. Создайте информативное название для эксперимента, затем нажмите **Далее**.
   4. В разделе **Dataflow details** укажите сведения о наборе данных и потоке данных.
   5. Создайте информативное название для эксперимента, затем нажмите **Далее**.
   6. В разделе **Scheduling** установите частоту 60 минут.
   7. Повторите эти действия для каждого нужного отчета Data Locker.

<div id="see-also" />

> 📄 **Смотрите также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/adobe-launch-sdk-extension?query=adobe">Расширение для SDK Adobe Launch</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/adobe-air-plugin?query=adobe">Плагин Adobe Air</Anchor>

<div data-zendesk-anchors="overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01HDNYXDFCQQBNBB6ZQQTJS189=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 setting-up-the-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01HDNYXDFCEVVDS5RANQMP6K3G=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01HDNZ1AS5YTK6N26PD7S7C0XF=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

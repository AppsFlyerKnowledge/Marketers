---
title: Аудитории — использование событий Braze при создании аудитории
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-17T09:55:26Z'
  edited_at: '2026-10-06T00:17:56Z'
  id: 4411130243217
  locale: ru
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ru/articles/4411130243217
---
> **At a glance:** **Краткий обзор:** Отправляйте события вовлечения с сообщениями Braze в AppsFlyer аудитории и используйте их для повышения точности ваших определений аудиторий.

Настраивая входящее подключение между вашей учетной записью Braze и AppsFlyer аудитории, вы интегрируете данные о событиях вовлечения с сообщениями Braze в аудитории. Затем вы можете использовать эти данные в <Anchor target="_blank" href="/marketers/ru/docs/audiences-guide#все-о-наборах-правил">наборах правил</Anchor> при определении аудиторий.

> 🚧 **Important**
>
> **Предварительные требования**
>
> * В приложение должны быть интегрированы SDK (пакет средств разработки ПО) Braze и AppsFlyer.
> * Вам необходимо подписаться на функцию **Currents** в Braze.

<div id="set-up-the-braze-incoming-connection" />

## Настройка входящего подключения Braze

Настройка входящего подключения Braze включает три основных шага:

1. [Настройка AppsFlyer SDK](/docs/audiences-use-braze-events-in-audience-creation#set-up-the-appsflyer-sdk)
2. [Создание входящего подключения в AppsFlyer](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer)
3. [Создание Currents в Braze](/docs/audiences-use-braze-events-in-audience-creation#create-a-current-in-braze)

<Accordion title="Настройка AppsFlyer SDK">

Чтобы создать входящее подключение из Braze, AppsFlyer SDK (пакет средств разработки ПО) в ваших приложениях должен быть настроен на передачу каждому пользователю **внешнего идентификатора Braze** в AppsFlyer. Это можно сделать, используя один из следующих методов:

* Параметр внешнего идентификатора Braze
* Поле CUID

<div id="using-a-braze-external-id-parameter" />

#### **Использование параметра внешнего идентификатора Braze**

Вы можете настроить специальный параметр для передачи внешнего идентификатора Braze в AppsFlyer с помощью функции `setPartnerData` AppsFlyer SDK. Примеры использования приведены ниже:

<Tabs>
<Tab title="Android;">

```java
Map<String, Object> brazeData = new HashMap<>();
partnerData.put("external_user_id", "some-braze-external-id-value");
AppsFlyerLib.getInstance().setPartnerData("braze_int", brazeData);
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

```objectivec
NSDictionary *brazeInfo = @{
@"external_user_id":@"some-braze-external-id-value"
};
[[AppsFlyerLib shared] setPartnerDataWithPartnerId:@"braze_int"
partnerInfo:brazeInfo];
```

</Tab>
</Tabs>

<div id="using-the-cuid-field" />

#### **Использование поля CUID**

Нет необходимости в настройке специального параметра для внешнего идентификатора Braze, если:

* Вы задали SDK (пакет средств разработки ПО), чтобы отправлять AppsFlyer <Anchor target="_blank" href="/marketers/ru/docs/customer-user-id-field-cuid">CUID</Anchor> для каждого пользователя.
* CUID имеет такое же значение, как внешнее идентификатор Braze.

В этом случае вы можете просто выбрать опцию **CUID** как параметр SDK при [создании входящего подключения Braze](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer).

</Accordion>

<Accordion title="Создание входящего подключения Braze в AppsFlyer">

**Следуйте этим шагам, чтобы создать входящее подключение в AppsFlyer:**

1. В AppsFlyer в боковом меню выберите **Вовлечение** > **Аудитории**.
2. На странице аудиторий перейдите на вкладку **Подключения > Входящие** .
3. Нажмите кнопку **Новое входящее подключение**.
4. Выберите Braze из списка доступных партнеров.
5. Кликните кнопку **Сохранить**, чтобы создать подключение.  
   Откроется диалоговое окно **Учетные данные подключения**.
6. Скопируйте учетные данные для подключения, чтобы использовать их при настройке соединения с AppsFlyer аудиториями в платформе Braze:
   * Идентификатор ключа доступа
   * Секретный ключ доступа
   * Имя корзины
   * Путь к папке
7. Выберите параметр SDK (пакет средств разработки ПО), который вы используете для отправки внешнего идентификатора Braze:
   * Внешний идентификатор Braze
   * CUID

</Accordion>

<Accordion title="Создание Currents в Braze">

**Следуйте этим шагам, чтобы создать Current в Braze:**

1. Перейдите в раздел **Интеграция** в левой панели меню.
2. Кликните **Current.**
3. Кликните кнопку **Создать Current**.
4. Выберите **Экспорт данных Amazon S3.**
5. В разделе **Создание интеграции Currents**:
   1. Введите имя для Current (например, AppsFlyer аудитории).
   2. Введите электронную почту человека из вашей команды, которого Braze уведомит в случае проблем с учетными данными для Current.
6. В разделе **Учетные данные**:
   1. Оставьте выбранным параметр **Секретный ключ доступа AWS** (это значение по умолчанию).
   2. Введите учетные данные, скопированные из AppsFlyer, в соответствующие поля.
   3. Не отмечайте опцию **Включить шифрование**.
7. В разделе **Общие настройки** оставьте включенной опцию **Включить события от анонимных пользователей**.
8. В разделе **События вовлечения с сообщениями** выберите события, которые Braze должен отправлять в AppsFlyer. Список поддерживаемых событий см. [ниже](/docs/audiences-use-braze-events-in-audience-creation#поддерживаемые-события).
9. В разделе «Поведение клиентов и события пользователя» оставьте опцию **Отслеживать поведение клиентов и события пользователя** отключенной.
10. Кликните кнопку **Запустить Current**, чтобы сохранить конфигурацию и начать отправлять события вовлечения с сообщениями Braze в аудитории.

<div id="supported-events" />

#### поддерживаемые события

> 📘 **Note**
>
> **Поддерживаемые события Braze**
>
> * Изменение состояния группы подписки
> * Клик по электронной почте
> * Открытие электронной почты
> * Отправка электронной почты
> * Доставка электронной почты
> * Отметка как спам
> * Отписка от электронной почты
> * Возврат электронной почты
> * Мягкий возврат электронной почты
> * Открытие push-сообщения
> * Отправка push-сообщения
> * Отказ push-сообщения
> * Все iOS push-сообщения на переднем плане
> * Отправка СМС\/ММС

</Accordion>

<div id="using-braze-data-in-audiences" />

## Использование данных Braze в аудиториях

После настройки входящего подключения Braze определенные вами события вовлеченности будут доступны как параметры в <Anchor target="_blank" href="/marketers/ru/docs/audiences-guide#ruleset-filters">фильтрах набора правил</Anchor> для определения аудиторий.

![audiences_braze_ruleset.png](https://files.readme.io/766a5ec25de3cf82c1411ce25864a5c8ce6c77ac338c20699e61be1c45ae3d98-33375723752337.png)

**Примечание:** События вовлечения с сообщениями Braze станут доступны в AppsFlyer примерно через 24 часа после запуска Current в Braze.

<div data-zendesk-anchors="set-up-the-braze-incoming-connection=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B5%D0%B3%D0%BE-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-braze h_01HKW0BS5H1ANWAJZTVBWDQHJH=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B2%D1%85%D0%BE%D0%B4%D1%8F%D1%89%D0%B5%D0%B3%D0%BE-%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-braze using-a-braze-external-id-parameter=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%B0-%D0%B2%D0%BD%D0%B5%D1%88%D0%BD%D0%B5%D0%B3%D0%BE-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0-braze h_01HKW0BS5HGB2RYGWNXT1M163C=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D0%B0-%D0%B2%D0%BD%D0%B5%D1%88%D0%BD%D0%B5%D0%B3%D0%BE-%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D0%B0-braze using-the-cuid-field=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8F-cuid h_01HKW0BS5HQJZRR60VKBCWGHQB=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8F-cuid supported-events=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F h_01HKW0BS5JM8A9XFVX22KWFE3H=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F using-braze-data-in-audiences=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-braze-%D0%B2-%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D1%8F%D1%85 h_01HKW0BS5JTZQ71HFE305ZT1CS=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-braze-%D0%B2-%D0%B0%D1%83%D0%B4%D0%B8%D1%82%D0%BE%D1%80%D0%B8%D1%8F%D1%85" />

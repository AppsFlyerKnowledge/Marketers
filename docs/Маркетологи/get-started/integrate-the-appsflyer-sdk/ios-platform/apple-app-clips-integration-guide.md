---
title: Руководство по интеграции Apple App Clips
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2020-10-09T00:42:10Z'
  edited_at: '2026-08-18T00:15:03Z'
  id: 360014262358
  locale: ru
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ru/articles/360014262358
---
> **Краткий обзор.** Мини-приложения App Clips позволяют пользователям iOS 14 или более поздней версии быстро получить доступ к вашему приложению и ознакомиться с ним. AppsFlyer обеспечивает атрибуцию App Clip и при необходимости перенаправляет пользователей, которые не могут использовать App Clip (например, пользователей Android).

![app_clip_flow_3.png](https://files.readme.io/1a5ec7a6b8a061955742d8e79ba78fa0262c0609e1e801decc92300d6c24a774-360012832058.png)

## Интеграция App Clip

* Мини-приложения App Clips предоставляют пользователям iOS 14 быстрый и удобный доступ к приложениям без необходимости загружать их целиком.
* App Clips устанавливаются и запускаются с помощью их инициирования (например, QR-кода или NFC-метки). **Примечание.** Смарт-баннеры и ссылки в сообщениях в Safari не поддерживаются.
* AppsFlyer SDK необходим для атрибуции кликов, установок, событий в приложении App Clip и установок App Clip в полные приложения.
* Независимо от SDK, OneLink перенаправляет пользователей по мере необходимости:
  * Пользователи без установленного приложения:
    * С iOS 14 или более поздней версией перенаправляются в App Clip.
    * С iOS 13 или более ранней версией, или Android, перенаправляются на основе ваших настроек в OneLink (в магазин приложений и т.д.).
  * Пользователи, у которых установлено приложение, переходят к нему в соответствии с настройками Universal Link или App Link в OneLink.

### Соображения

* Размер App Clip может достигать 10 МБ. AppsFlyer SDK занимает ~1,5 МБ.
* Рекламные идентификаторы отсутствуют.
* App Clip удаляются ОС автоматически после 30-дневного периода бездействия.

> 📄 **Пример**
>
> Марк — маркетолог сети кофеен. Он поручает своему iOS-разработчику создать мини-приложение App Clip, которое позволит покупателям миновать очередь и сделать заказ за считанные секунды. Они просто идентифицируют себя с помощью <Anchor target="_blank" href="https://developer.apple.com/sign-in-with-apple/">Apple Sign-in</Anchor>, заказывают кофе и расплачиваются с помощью <Anchor target="_blank" href="https://developer.apple.com/apple-pay/">Apple Pay</Anchor>. Разработчик добавляет AppsFlyer SDK и проверяет, что он работает как в приложении, так и в мини-приложении.
>
> Марк создает OneLink и размещает QR-код в кофейне вместе со слоганом "Покупайте без очереди!".
>
> Клиенты сканируют QR-код и:
>
> * Если у них есть устройство с iOS 14 или более поздней версией, откроется приложение App Clip с нужным филиалом кофейни и купоном на скидку.
> * Если у них уже установлено полное приложение, оно откроется на странице заказа кофе.
> * Если у них нет приложения и есть устройство с iOS 13 или более ранней версией или Android, откроется страница магазина приложений для приложения кофейни.
>
> Марк использует дэшборд и отчеты AppsFlyer, чтобы посмотреть, сколько кликов и установок получает App Clip и сколько пользователей в итоге скачивают полное приложение.

## Показатели и отчетность

Аналитические и сырые данные App Clips доступны на платформе на основе действий пользователей, описанных в следующей таблице.

| Действия пользователя | Событие AppsFlyer | Обзорный дэшборд и аналитические инструменты | Сырые данные |
| --- | --- | --- | --- |
| Инициирование (пример: QR-код) | Нет события | Нет события | Нет события |
| Нажимает на карточку приложения и открывается App Clip | Клик и установка атрибутированы к источнику инициирования | <ul><li>клики;</li><li>Установки</li></ul> | <Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor> |
| Использует App Clip | <ul><li>[Необязательно] Разработчик отправляет событие в приложении</li><li>После первого запуска App Clip последующие запуски учитываются как сессии.</li></ul> | <ul><li>Внутреннее событие приложения</li><li>Сессия</li></ul> | <ul><li>Событие в приложении, отправленное разработчиком</li><li><Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor></li></ul> |
| Загрузка и запуск полного приложения | Внутреннее событие приложения | Имя события в приложении = af\_app\_clip\_to\_full\_app | <ul><li>Имя события в приложении = af\_app\_clip\_to\_full\_app</li><li><Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |
| Постоянное использование полного приложения | [Необязательно] Разработчик отправляет событие в приложении | Внутреннее событие приложения | <ul><li>Событие в приложении, отправленное разработчиком</li><li><Anchor target="_blank" href="/marketers/ru/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |

**Ретаргетинг**

Просматривайте показатели App Clip на <Anchor target="_blank" href="/marketers/ru/docs/cohort-and-retention-dashboard#trend-type%E2%80%94user-lifetime-performance">дэшборде когорт</Anchor>, где вы можете:

* Узнать, сколько времени требуется пользователям, чтобы перейти из App Clip к установке полного приложения.
* Использовать метрику конверсий в приложении, чтобы сравнить эффективность различных кампаний по инициированию мини-приложений.

## Реализация App Clip

Ниже подробно описано, что нужно сделать вам и разработчику iOS для разработки и интеграции App Clips.

#### Объем работ

| **Кто задействован**<ul><li>**Рекламодатель**:<ul><li>Настраивает Apple App Clips в шаблонах OneLink.</li><li>Размещает ссылки OneLink на портале Apple App Store Connect.</li><li>Просматривает показатели на дэшборде и в отчетах AppsFlyer.</li></ul></li><li>**Разработчик iOS**:<ul><li>Создает App Clip</li><li>Интегрирует AppsFlyer SDK в App Clip.</li></ul></li></ul> |
| --- |
| **Необходимые условия**<ul><li>Аккаунт AppsFlyer с хотя бы одним приложением.</li><li>Шаблон OneLink с универсальными ссылками и настройка ссылок OneLink для направления пользователей вашего полного приложения.<br />**Рекомендация**: Инициирование (запуск) шаблона и ссылки, которые вы используете для App Clip, отправляют всех пользователей, не имеющих вашего полного приложения, в App Clip. Поэтому рассмотрите возможность создания отдельного шаблона и настраиваемой ссылки для случаев, когда вы хотите отправить пользователей в App Store, а не в App Clip.</li></ul> |

<div id="develop-app-clip" />

<Accordion title="Разработка App Clip">

Полные инструкции по созданию App Clip для вашего приложения вы найдете в <Anchor target="_blank" href="https://developer.apple.com/app-clips/">руководстве по Apple App Clip для разработчиков</Anchor>.

Упрощенный пример приложения, демонстрирующий использование App Clips и его интеграцию с полноценным приложением, приведен в <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips/">руководстве AppsFlyer по App Clip</Anchor>.

</Accordion>

<div id="integrate-sdk" />

<Accordion title="Интеграция SDK">

* SDK необходим для атрибуции в AppsFlyer кликов, установок, событий в приложении App Clip и установок App Clip в полное приложение.
* OneLink перенаправляет пользователей независимо от интеграции SDK.

**Чтобы установить SDK и настроить SDK для полного приложения**:

Отправьте следующие ссылки своему разработчику iOS и попросите его следовать инструкциям:

* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-sdk-integration">Интеграция SDK в App Clip</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-to-full-app-install">Настройка атрибуции установок App Clip в полное приложение</Anchor>
* [Необязательно] <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events">Настройте события в приложении</Anchor>, если вы еще не измеряете события в приложении для полного приложения или хотите использовать другие события в приложении для App Clip.

</Accordion>

<div id="configure-onelink" />

<Accordion title="Конфигурация OneLink">

**Необходимые условия**:

* <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Шаблон OneLink</Anchor> для вашего полного приложения с настроенными универсальными ссылками iOS.
* <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">Ссылка OneLink</Anchor>.
* **Рекомендация**: Инициирование (запуск) шаблона и ссылки, которые вы используете для App Clip, отправляют всех пользователей, не имеющих вашего полного приложения, в App Clip. Поэтому рассмотрите возможность создания отдельного шаблона и настраиваемой ссылки для случаев, когда вы хотите отправить пользователей в App Store, а не в App Clip.

Чтобы настроить шаблон OneLink для вашего App Clip:

1. На дэшборде AppsFlyer перейдите в раздел **Вовлечение** > **Управление OneLink**.
2. Выберите **шаблон OneLink**, который вы используете для перенаправления пользователей в ваше полное приложение.
3. Убедитесь, что в шаблоне OneLink настроены универсальные ссылки. (См. <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">инструкции</Anchor> по добавлению универсальных ссылок).
4. Нажмите **Сохранить**.  
   Файл AASA обновится для поддержки App Clip.
5. На дэшборде AppsFlyer перейдите в раздел **Вовлечение** > **Управление OneLink**.
6. Выберите **настраиваемую ссылку OneLink**, основанную на шаблоне, который вы настроили в шагах 1-4 и используемую для направления пользователей в App Clip.
7. Убедитесь, что указан медиа-источник (pid).  
   Медиа-источник должен быть указан в URL (например: **pid=chartboost\_int**) или содержаться внутри ссылки.

**Чтобы проверить, что App Clips включены в AppsFlyer OneLink:**

1. Создайте URL-адрес для получения файла ассоциации. URL создается с помощью добавления `/.well-known/apple-app-site-association` к домену шаблона OneLink.   
   Например, `coffee.onelink.me/.well-known/apple-app-site-association`.
2. Перейдите по URL-адресу файла ассоциации.  
   Файл apple-app-site-association загрузится автоматически.
3. Откройте файл apple-app-site-association с помощью текстового редактора (например, Notepad).
4. Убедитесь, что файл содержит слово "**appclips**" и что идентификатор пакета заканчивается на "**.Clip**". и что идентификатор ID пакета заканчивается на "**.Clip**". Например:  

   ```java
   "appclips": {
       "apps": [
         "ABCD1234.id.your.app.Clip",
         ...
       ]
   ...
   }
   ```

   Если это так, значит, вы успешно настроили App Clips на стороне AppsFlyer, и App Clip будет реализован в любом шаблоне OneLink с тем же поддоменом.

</Accordion>

<div id="configure-app-store-connect" />

<Accordion title="Настройка App Store Connect">

**Необходимые условия**: Завершение [настройки шаблона OneLink для App Clips](/docs/apple-app-clips-integration-guide#configure-onelink)

**Чтобы настроить App Clip для работы с OneLink**:

1. На странице вашего приложения в App Store Connect перейдите в раздел **Build** > **Domain Status**.
2. Убедитесь, что ваш домен OneLink отображается в разделе **Build domains**, а **статус Cache** и **статус Debug** оба "validated".
3. На дэшборде AppsFlyer перейдите в раздел **Вовлечение** > **Управление OneLink**.
4. Наведите курсор на значок **Действия** ссылки, которую вы хотите использовать, и нажмите **Получить URL**.
5. Запишите короткий URL-адрес (или префикс длинного URL-адреса).
6. На странице вашего приложения в App Store Connect перейдите в раздел **App Clip** > **Edit Advanced Experiences** > **+Add** > **Next**.
7. В **поле App Clip Experience URL** вставьте пользовательский URL OneLink, который вы записали в шаге 5.  
   **Примечание.** Вы можете добавлять параметры запроса после основного пользовательского URL, но не можете изменять путь.
8. Нажмите **Далее**.  
   Теперь ваше мини-приложение App Clip настроено для работы с OneLink. Дополнительные инструкции по настройке App Store Connect можно найти в <Anchor target="_blank" href="https://developer.apple.com/documentation/app_clips/configuring_your_app_clip_s_launch_experience">руководстве для разработчиков Apple</Anchor>.

</Accordion>

<div id="testing" />

<Accordion title="Тестирование">

**Необходимые условия**: <Anchor target="_blank" href="/marketers/ru/docs/registering-test-devices">Зарегистрированное тестовое устройство</Anchor> с iOS 14 без установленного полного приложения.

**Чтобы проверить интеграцию OneLink и App Clip:**

1. На дэшборде AppsFlyer перейдите в раздел **Вовлечение** > **Управление OneLink**.
2. Наведите курсор на значок Действия **для ссылки, которую вы хотите протестировать, и нажмите** Получить URL-адрес.
3. Отсканируйте QR-код с помощью своего устройства.  
   На устройстве отобразится карточка App Clip, указывающая на то, что интеграция OneLink и App Clip настроена правильно.

</Accordion>

## Ограничения и особенности

<div id="traits-and-limitations::26141033" />

<Accordion title="Ограничения и особенности">

| Особенность/ограничение | Описание |
| --- | --- |
| Методы запуска | <ul><li>Поддерживаются QR-коды и метки NFC.</li><li>Смарт-баннеры и ссылки в сообщениях в Safari не поддерживаются.</li></ul> |
| SKAdNetwork | Функциональность SKAdNetwork недоступна. Поэтому установки App Clip отображаются на дэшборде SKAdNetwork как органические. |
| Универсальные ссылки OneLink | Для одной настраиваемой ссылки OneLink разрешено только одно расширенное использование App Clip. Это означает, что вы не можете добавить дополнительные пути к OneLink в App Store Connect. |
| Дэшборд Protect360 | Protect360 не поддерживает App Clips. |

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/guides/ios-14-app-clips/">Решение для атрибуции Apple App Clips от AppsFlyer</Anchor>

<div data-zendesk-anchors="app-clip-integration=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-app-clip h_01HDNZQTCBXY0Y3QYCBNVH7EAW=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-app-clip considerations=%D1%81%D0%BE%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HDNZQTCBPJWY6H2M452QH644=%D1%81%D0%BE%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HDNZQTCB7NB682YTSMNCJSDP=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 metrics-and-reporting=%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D0%B8-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C h_01HDNZQTCBNG3TYRAA7GVPF39P=%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D0%B8-%D0%B8-%D0%BE%D1%82%D1%87%D0%B5%D1%82%D0%BD%D0%BE%D1%81%D1%82%D1%8C app-clip-implementation=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-app-clip h_01HDNZQTCBJK7SB96G8A4DHR34=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-app-clip scope-of-work=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D1%80%D0%B0%D0%B1%D0%BE%D1%82 h_01HDNZQTCB1AKW9QFRRM9VVN4D=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D1%80%D0%B0%D0%B1%D0%BE%D1%82 h_01HDNZQTCBN04J3GA8H64V70YY=develop-app-clip h_01HDNZQTCBHHENFYJK7MFJTZ14=integrate-sdk h_01HDNZQTCBN9QV4MZAAWMV164Y=configure-onelink h_01HDNZQTCC6F8TTM2FRQK6DB2E=configure-app-store-connect h_01HDNZQTCCN2BX9NZ4027ZCEFB=testing traits-and-limitations=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HDNZQTCCMW2YNK1G34EBM7DM=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B8-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HDNZQTCCV0S78NRK00PK4S0J=traits-and-limitations::26141033 h_01HDNZS83EKJNZGG1QEVS9RMCA=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

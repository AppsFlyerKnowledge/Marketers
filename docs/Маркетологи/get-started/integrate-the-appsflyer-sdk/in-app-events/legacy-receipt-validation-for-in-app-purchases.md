---
title: '[Устарело] Валидация чека для покупок в приложениях'
deprecated: true
metadata:
  keywords:
    - iOS
    - Android
    - Receipt
    - Validation
    - Receipt Validation
    - SDK
    - Advertisers
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
  created_at: '2015-02-26T10:30:58Z'
  edited_at: '2026-08-18T00:13:59Z'
  id: 207032106
  locale: ru
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ru/articles/207032106
---
<div id="important" />

> 🚧 **Важно!**
>
> В этой статье описывается устаревшая функция валидации чеков. Дополнительную информацию см. в статье <Anchor target="_blank" href="/marketers/ru/docs/bulletin-legacy-receipt-validation-is-deprecated">Bulletin: устаревшая валидация чека больше не поддерживается</Anchor>

> **Кратко:** Реализуйте валидацию чека, чтобы защититься от мошеннических покупок в приложении в магазинах приложений для iOS и Android, а также убедиться, что покупка в приложении действительно произошла, как указано в отчёте. **Примечание**: Это устаревшая функция. Узнайте подробнее о новом, полностью автоматическом и улучшенном <Anchor target="_blank" href="/marketers/ru/docs/purchase-and-subscription-validation-overview">механизме валидации покупок в приложении</Anchor>.

<div id="receipt-validation-flow" />

## Процесс валидации квитанций

Процесс валидации чека выглядит следующим образом:

1. Пользователь совершает покупку в приложении.
2. Магазин приложений уведомляет приложение об успешной покупке.
3. Разработчик приложения вызывает функцию SDK для валидации чеков.

   ```
   validateAndLogInAppPurchase
   ```
4. SDK вызывает сервис валидации AppsFlyer.
5. AppsFlyer выполняет валидацию покупки, чтобы убедиться, что она не является мошеннической.
6. В случае успешной валидации AppsFlyer на внутреннем уровне создаёт стандартное событие af\_purchase. В противном случае созданное событие помечается как мошенническое (доступно через Protect360).
7. Сервис валидации AppsFlyer передаёт ответ SDK.
8. SDK передаёт приложению результат валидации чека (успех или ошибка).  
   Если валидация чека не пройдена, событие отображается в отчете <Anchor target="_blank" href="/marketers/ru/docs/protect360-raw-data-reports#inapp-level-blocked-reasons">blocked in-app events raw-data</Anchor> (доступно подписчикам Protect360).

Для получения подробной информации о реализации валидации чеков см. нашу документацию для разработчиков SDK:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#validating-purchases">Android;</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#purchase-validation-using-validateandloginapppurchase">https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png</Anchor>

**ПРИМЕЧАНИЯ**

* Для песочничных приложений iOS, то есть приложений, которые ещё не опубликованы в App Store, валидация чека требует <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/validate-and-log-purchase-ios#testing-purchase-validation-in-sandbox-mode">дополнительного кода</Anchor>.
* Покупки, сделанные в тестовой среде, регистрируются как стандартные события af\_purchase, и их доход отражается в дэшбордах и отчётах AppsFlyer.
* Сервис валидации чеков AppsFlyer бесплатен для всех тарифных планов.
* Для Android валидация чека может вернуть результат `null` и считаться неудачной, если у конечного пользователя во время покупки нет доступа к интернету.

<div id="important-1" />

> 🚧 **Важно!**
>
> Вызов `validateAndLogInAppPurchase` также создает in-app событие **af\_purchase**. Поэтому, не нужно генерировать событие af\_purchase во время валидации. Иначе это приведёт к дублированию события дохода.

<div id="note" />

> 📘 **Примечание:**
>
> * *T*he legacy receipt validation explained here does not support *StoreKit v2*. Текущую версию см. в статье Настройка интеграции с iOS App Store.
> * Валидация квитанций для покупок в приложении не поддерживается для сторонних магазинов приложений на Android.

<div data-zendesk-anchors="h_01KDJ7QZD8X692EVP1XXGV0KY4=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE receipt-validation-flow=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81-%D0%B2%D0%B0%D0%BB%D0%B8%D0%B4%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%B2%D0%B8%D1%82%D0%B0%D0%BD%D1%86%D0%B8%D0%B9 01JDSM0JDAQXH8QX8ZAXNB0ZMB=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D1%81%D1%81-%D0%B2%D0%B0%D0%BB%D0%B8%D0%B4%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%B2%D0%B8%D1%82%D0%B0%D0%BD%D1%86%D0%B8%D0%B9 01JDSM0JDT6Q3WYW9K484QHY2M=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE-1 01JDSM0JD90J3EDMVN6D6Z9J40=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5" />

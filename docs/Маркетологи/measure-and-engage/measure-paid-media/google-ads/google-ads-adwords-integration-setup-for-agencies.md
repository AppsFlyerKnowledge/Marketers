---
title: Google Ads (AdWords) — настройка интеграции для агентств
metadata:
  keywords:
    - Google
    - AdWords
    - Advertisers
    - Agencies
    - (AdWords)
    - google ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2017-07-23T11:26:20Z'
  edited_at: '2026-09-17T00:27:27Z'
  id: 115003669983
  locale: ru
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ru/articles/115003669983
---
> **Кратко:** настройка интеграции Google Ads с AppsFlyer со стороны агентства.

И рекламодатели, и агентства должны активно настраивать систему. В следующем видео показаны шаги, которые должны выполнить и рекламодатель, и агентство, чтобы агентство могло измерять мобильный трафик и выполнять его атрибуцию для приложения рекламодателя с помощью Google Ads.

Эта конфигурация позволяет AppsFlyer атрибутировать конверсии агентству в дэшборде AppsFlyer.

Прежде чем агентство сможет начать этот процесс, рекламодатель должен сначала настроить интеграцию Google Ads. Для получения подробной информации нажмите <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers">здесь</Anchor>.

<div id="enabling-agency-attribution-of-google-ads" />

## Включение атрибуции Google Ads для агентства

AppsFlyer поддерживает настройку агентств для работы с Google реклама. Важно, чтобы у рекламодателя и агентства были отдельные аккаунты в Google реклама, чтобы AppsFlyer мог правильно атрибутировать данные.

<div id="setting-up-google-ads-attribution-for-agencies" />

## Настройка атрибуции Google Ads для агентств

Чтобы начать атрибуцию кампаний Google Ads с помощью AppsFlyer — со стороны агентства, выполните следующие шаги:

<Accordion title="Смотреть">

<Embed title="Google Ads (AdWords) — настройка интеграции для агентств" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/fzihkki0qd" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Читать">

<div id="advertiser-prestep-enabling-the-agency-access-to-google-ads" />

<Accordion title="Предварительный шаг для рекламодателя: предоставление агентству доступа к Google Ads">

**Необходимые условия:**

* В AppsFlyer предоставьте агентству доступ к приложению, следуя инструкциям <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#разрешения-агентства">здесь</Anchor>.
* В AppsFlyer <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">активируйте</Anchor> партнера Google Ads.

**Чтобы поделиться Link ID рекламодателя:**

1. В Google перейдите в дэшборд Google Ads и нажмите значок ***Tools***

![Google_Ag_1.png](https://files.readme.io/3a1188bc11e09779076c880c1b4d5e933845ee642393ff1367b2368c1199d8a2-50897694578449.png)

2. Выберите ***Связанные аккаунты***.

![Google_Ag_2.png](https://files.readme.io/5bf0fb06df3263bc65a4e7e78539c06f2fce552b24b2913c18e155eff56f18ad-50897658813841.png)

3. В разделе поставщика аналитики приложений найдите AppsFlyer. Выберите Options.

4. Нажмите ***Share with another account***.

![Google_Ag_3.png](https://files.readme.io/0659fc1f193ffc668f18f13641d07e085c94a97fb9e5c6c0f35188e1c18c632b-50897694583441.png)

5. Введите **идентификатор клиента Google Ads агентства**

![Google_Ag_4.png](https://files.readme.io/cce6c7aa387f354c004682c6d46b804897654c99b3346ce6c27a2bcf43259c2e-50897694584849.png)

6. Кликните ***Далее***. Нажмите ***Отправить приглашение.***

![Google_Ag_5.png](https://files.readme.io/d3da1850913f2c2a9b9125460cebd7e61922a177178c48cf23904d5a42445972-50897658822801.png)

Теперь рекламодатель видит, что запрос на приглашение отправлен в агентство. Когда агентство принимает приглашение, статус меняется на «Активный».

Чтобы узнать больше о том, как поделиться идентификатором ссылки Google Ads, кликните <Anchor target="_blank" href="https://support.google.com/adwords/answer/7365001">здесь</Anchor>.

![Google_Ag_6.png](https://files.readme.io/b205e5b2771a128846b22d653998da09f8d600b6b60efb6ca1e90042ffba5ee7-50897694593041.png)

</Accordion>

<div id="agency-step-1-accepting-the-link-id" />

<Accordion title="Шаг 1 для агентства: принятие идентификатора ID ссылки">

На дэшборде Google Ads агентство получает приглашение и должно принять ссылку.

![Google_Ag_7.png](https://files.readme.io/f64942b5f67d9cb3ce692380626d9b87fb43a98ce825544b84e49c36162e349d-50897694593937.png)

Агентство может увидеть, что статус ссылки теперь — «Активный».

![Google_ag_8.png](https://files.readme.io/e44b590d4720accfde2ac95b97b18250ba2aab07f12651749592d4ad5aa8c947-50897658832017.png)

</Accordion>

<div id="agency-step-2-setting-up-google-ads-on-appsflyer" />

<Accordion title="Шаг 2 для агентства: настройка Google Ads в AppsFlyer">

При необходимости агентство может настроить несколько идентификаторов Google Ads Customer ID.

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Интеграции партнеров**.
2. Найдите и выберите **Google Ads**.

   ![gads-search.png](https://files.readme.io/97f9abe0e6bf4e07b81341f1c0a9978f6387747b412c53f7755c53a76ba0eaeb-50897694596881.png)

   ***Activate partner*** должен быть включен, а ***Link ID*** — задан рекламодателем. Для агентства эти настройки недоступны для редактирования.

   ![gads_agency-integration-link-id.png](https://files.readme.io/6d59ccad7fb3a4a0269b9e868e30b0b87eb23a83e07e6ef1d2603815352786bf-50897658836625.png)
3. Агентство задает свой идентификатор ID клиента Google Ads.

   Введите **все** идентификаторы клиентов Google Ads (**субаккаунтов**) тех аккаунтов Google Ads, в которых агентство проводит кампании для приложения рекламодателя.

   Идентификатор клиента Google Ads можно найти, нажав стрелку в левом верхнем углу и открыв таким образом панель навигации.

   [![](https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png)](https://files.readme.io/5cc63138208e0ba55a59b4c2514dff373e45a25f50d92f9e6d8316356d078ed3-50897658839185.png)
4. Чтобы измерять запущенные ретаргетинговые кампании в Google Ads, попросите рекламодателя активировать **Google Ads Retargeting**. После этого можно настроить **Re-Engagement Window**.

   ![gads-agency-retargeting.png](https://files.readme.io/42008f063585b0a1dff553b8391b9dca48c2a3657786c263459c717cc94b5b19-50897658842385.png)
5. Рекомендуется установить для окна атрибуции по кликам значение **30 дней**, чтобы оно соответствовало значению в Google Ads .

   ![gads-click-through.png](https://files.readme.io/9bf0456ecb003e4b2750e4e5c1455d4418de00b8815ae08e9e580763948e3721-50897694603025.png)
6. Для атрибуции по просмотрам рекомендуется установить значение **1 день**, чтобы оно соответствовало значению в Google Ads . С помощью масштаба можно настроить количество часов или дней после просмотра рекламы, в течение которых показ можно атрибутировать этому партнеру.

   ![gads-view-through.png](https://files.readme.io/c26b18ff2d51ade48a9e57e0bb5097e4a0671f0ba78583cfeaa17848bebf9a34-50897658845969.png)
7. ***Атрибуция повторных установок***:
   * Чтобы включить атрибуцию повторных установок, установите переключатель в положение "включено".
   * Вам необязательно включать атрибуцию по просмотрам или настраивать окно атрибуции для повторных установок, так как эти значения подставляются из настроек атрибуции установки.
8. Кликните ***Save & Close***.

</Accordion>

<div id="agency-step-3-mapping-your-inapp-events" />

<Accordion title="Шаг 3 для агентства: сопоставление событий в приложении">

1. Нажмите вкладку **События в приложении**.

2. Выберите, отправлять в Google Ads только события в приложении из установок Google Ads или все события в приложении.  
[![](https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png)](https://files.readme.io/c2d22406f549db47de21beb54b7f9c8f94419702d0f78f46b2dbf0785e2ba94a-50897694609297.png)

3. Сопоставьте все события в приложении, которые вы хотите отправлять в Google Ads, с предопределенными событиями Google Ads.

[![](https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png)](https://files.readme.io/036b4f1cef8fa9b537b3aeaaab3f4072a099f94b3a8bbc539838d7898185a1ad-50897694610065.png)

4. Нажмите кнопку ***Сохранить***.

<div id="important" />

> 🚧 **Важно!**
>
> Чтобы начать учитывать конверсии в Google Ads и в дэшборде AppsFlyer, импортируйте в Google Ads действия «первое открытие» и действия в приложении.
>
> Чтобы импорт стал доступен, необходимо как минимум один раз запустить приложение и выполнить сопоставленные события в приложении.

<div id="note" />

> 📘 **Примечание:**
>
> * Может пройти до 6 часов, прежде чем статус новых конверсий изменится с «Нет недавних конверсий» на «Запись конверсий».
> * Если агентство работает с аккаунтом MCC и приложение продвигается через несколько субаккаунтов MCC, все субаккаунты должны быть настроены в поле **Google Ads Customer ID** field (как показано на снимке экрана выше).
>   В таком случае нет необходимости настраивать customer id аккаунта MCC.

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="Шаг 4 для агентства: измерение конверсий в приложении (обязательно)">

(**только для администратора Google Ads**)

<div id="important-1" />

> 🚧 **Двоеточие (:)**
>
> Для регистрации новых конверсий в Google Ads вам необходимо **запустить свое приложение и выполнить сопоставленные внутренние события** хотя бы один раз. Для тестирования приложений iOS необходимо собрать IDFA, чтобы увидеть событие. Добавление конверсий события в очередь может занять до 6 часов. После добавления вы сможете их импортировать, и новый статус конверсий изменится с «Нет недавних конверсий» на «Запись конверсий».

1. Вернитесь в аккаунт Google Ads (**Overview** page and go to **TOOLS AND SETTINGS** > **Measurement** > **Conversions**.  
   [![conversions_overview_en-us__1_.png](https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png)](https://files.readme.io/8e4217e0fc2d9696b9aaee3e247ce38fbd5bafd70f05101b31b4ab8de524b3cb-50897694610833.png)
2. Нажмите **+ Новое действие конверсии**.   
   [![New_conversion_action_en-us__2_.png](https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png)](https://files.readme.io/e4140f9a279c53bed9f0b576cc006bccd30fe737ea791ade47cd4d42c3e2074b-50897694612113.png)
3. В списке типов конверсии выберите **Приложение**, затем выберите **Third-party app analytics** и нажмите **Continue**.  
   [![select_app_en-us__3_.png](https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png)](https://files.readme.io/60d68af7588d5840bd478f2d6c7513f3a93fd2c409f780e13049cc5e639f2e98-50897658853137.png)
4. Установите флажок рядом с событием **first\_open** для всех своих приложений, а также для каждого события, которое нужно импортировать.

   **Примечание:**

   <div id="note-1" />

   > 📘 **Примечание:**
   >
   > Необходимо заново импортировать событие, если изменился **идентификатор события партнера** в Google Ads или если это пользовательский и соответствующее название события изменилось в AppsFlyer.


   Нажмите **Import and Continue**, затем нажмите **Done**.   
   [![select_events_to_import_ru-ru__4_.png](https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png)](https://files.readme.io/efe5458d26e6085aa0c228b98f63d37ef932e672e83ebc9050437b3b1259eea1-50897658853905.png)
5. Теперь вы можете просматривать сторонние события конверсии на странице **Conversions** > **Summary**. Если событие не отображается в списке или было удалено из списка конверсий Google Ads, кликните **View all conversion actions**. Появится фильтр **Статус**.   
   [![conversions_summary_en-us__5_.png](https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png)](https://files.readme.io/406121cc793f06d778192f8c8b191d7db0f11f91614cc4cf411a940ea176cd95-50897694614801.png)
6. Нажмите **Статус** и выберите **Все**, чтобы увидеть все события, включая отключённые и удалённые.  
   [![conversion_action_status__6_.png](https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png)](https://files.readme.io/f1294f57798cb4222775678a496be20b57238316b03a11e9a390b5362d1878c8-50897694615313.png)
7. Поздравляем! Теперь вы измеряете показатели мобильных кампаний Google Ads с помощью AppsFlyer!

<div id="note-2" />

> 📘 **Примечание**
>
> Убедитесь, что настройки параметра "include in conversions" (Включить в столбец "Конверсии") соответствуют целям вашей кампании в Google Ads. За дополнительной информацией обратитесь к представителю Google или ознакомьтесь с документацией Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">здесь</Anchor>.



</Accordion>

</Accordion>

Чтобы посмотреть видео «Настройка атрибуции Google Ads для рекламодателей», <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#настройка-атрибуции-в-google-ads-для-рекламодателей">нажмите здесь</Anchor>.

Подробнее о том, как рекламодатели могут настроить атрибуцию для нескольких аккаунтов агентств/MCC Google Ads, см. <Anchor target="_blank" href="/marketers/ru/docs/recording-multiple-agency-mcc-google-ads-accounts">здесь</Anchor>.

<div id="agencies-collecting-cost-clicks-and-impression-data" />

## Агентства: сбор данных о расходах, кликах и показах

Агентства могут <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#cost-tab">получать данные о расходах</Anchor> из Google Ads, включая данные о кликах и показах.

Данные о расходах отображаются в дэшбордах агентства и рекламодателя на уровне кампании.

Если агентство является прозрачным, то в дэшборде рекламодателя данные о расходах отображаются в кампаниях Google Рекламы. В противном случае данные отображаются в кампаниях агентства.

<div data-zendesk-anchors="enabling-agency-attribution-of-google-ads=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-google-ads-%D0%B4%D0%BB%D1%8F-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0 h_01HKA1J5ES5T65NT5QMY5ZGXP6=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-google-ads-%D0%B4%D0%BB%D1%8F-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0 setting-up-google-ads-attribution-for-agencies=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-google-ads-%D0%B4%D0%BB%D1%8F-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2 h_01HKA1J5ESJYS902S9Z3YY5FV9=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-google-ads-%D0%B4%D0%BB%D1%8F-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2 h_01HKA1J5ESF3ZK9E9PKM9AN8C8=advertiser-prestep-enabling-the-agency-access-to-google-ads h_01HKA1J5ETKV3H3KYBEYQZMSXA=agency-step-1-accepting-the-link-id h_01HKA1J5ET2BV8GHXZS5T8KCGZ=agency-step-2-setting-up-google-ads-on-appsflyer h_01HKA1J5ETH4TTVDSP0HNK6F0Q=agency-step-3-mapping-your-inapp-events h_01HKA1J5ETK5PXYFPXPBVH0HJQ=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01HKA1J5ETNQ1FCBMVTQED74HG=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HKA1J5ETKH9GKAX3HZMA7W57=step-4-measure-your-app-conversions-mandatory h_01HKA1J5ET210B40MPFQ79PPSN=%D0%B4%D0%B2%D0%BE%D0%B5%D1%82%D0%BE%D1%87%D0%B8%D0%B5- h_01HKA1J5ETNTFKKDF6NC635H3W=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01HKA1J5ETEWJN8MH9NPWTWX0F=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 agencies-collecting-cost-clicks-and-impression-data=%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0-%D1%81%D0%B1%D0%BE%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D1%85-%D0%B8-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%85 h_01HKA1J5ETPYE7B2NFPFHA05YT=%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0-%D1%81%D0%B1%D0%BE%D1%80-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D1%85-%D0%B8-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%B0%D1%85" />

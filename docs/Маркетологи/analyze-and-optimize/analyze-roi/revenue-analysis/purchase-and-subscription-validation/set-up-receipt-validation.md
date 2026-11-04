---
title: Настройка валидации чека
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T15:14:21Z'
  edited_at: '2026-08-27T00:01:21Z'
  id: 42137474889489
  locale: ru
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ru/articles/42137474889489
---
> **Краткий обзор:** Валидация чека измеряет доход от покупок в приложении и подписок и проверяет его в магазинах приложений, обеспечивая точные результаты Return on Ad Spend (ROAS).

<div id="upgrade-to-new-receipt-validation" />

## Переход на новую валидацию чека

Поддержка устаревшей валидации чека будет прекращена **7 сентября 2026 года**. Подробнее см. в <Anchor target="_blank" href="/marketers/ru/docs/bulletin-legacy-receipt-validation-is-deprecated">бюллетене: устаревшая валидация чека выводится из эксплуатации</Anchor>. Если в вашем приложении используется устаревшая валидация чека, перейдите на новую, выполнив приведенные ниже шаги настройки. Прежде чем начать, ознакомьтесь с основными различиями и подготовьтесь к миграции.

<div id="h_migration_key_differences" />

<Accordion title="Что нового в валидации чека">

| Область | Устаревший | Новая валидация чека |
| --- | --- | --- |
| Метод SDK | `validateAndLogInAppPurchase` (legacy/v1) | `validateAndLogInAppPurchase` (v2), то же название и новая сигнатура в iOS и Android |
| Передача цены и валюты | Передаются в вызове SDK | Автоматически извлекаются из магазина |
| Тип покупки | Не требуется | Обязательный параметр `PurchaseType` (*subscription* или *one-time purchase*) |
| Настройка параметров дохода | Не требуется | Требуется (страница настроек дохода) |
| Источник значения `af_revenue` | Значение, переданное в вызове SDK | Валовое значение, возвращаемое магазином; любое пользовательское значение, переданное в вызове SDK, попадает в объект `custom_data` события |
| Детализация событий покупки | Одно событие `af_purchase` для всех типов транзакций | Отдельные события для каждого типа транзакций: `af_purchase`, `af_ars_trial_started`, `af_ars_subscription_started` и их варианты для sandbox |
| Поддержка StoreKit 2 (iOS) | Не поддерживается | Поддерживается |
| Фильтрация мошенничества | Ограниченные возможности | Улучшено на Android и iOS |
| Доступность SDK | Удалено из SDK AppsFlyer версии 7.0.0+ | Доступно начиная с Android версии 6.17.5, iOS версии 6.17.8 и плагинов версии 6.17.8 |
| Запись проверенных событий покупки | Поддерживается до 7 сентября 2026 г. | Регулярно |

</Accordion>

<div id="h_migration_what_to_plan" />

<Accordion title="Подготовка миграции">

Перед началом миграции ознакомьтесь со следующими важными моментами:

* **Выполняйте миграцию постепенно, не затрагивая текущих пользователей.** Включение новой валидации чека в дэшборде AppsFlyer не влияет на версии приложения, которые по-прежнему используют устаревший метод. Оба варианта продолжат работать до прекращения поддержки устаревшего метода 7 сентября 2026 г.
* **Ожидайте изменений в доходе после миграции.** Новая валидация чека использует валовое значение, возвращаемое магазином, тогда как устаревшая валидация чека использовала значение дохода, переданное в вызове SDK. Если в вызове SDK передавалось неваловое значение, после миграции дэшборды и постбэки партнеров, которые теперь отражают валовые значения, будут показывать другое число. Для чистого дохода используйте **ROI360 Store Revenue**; подробнее см. в статье <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue">Настройте доход магазина ROI360</Anchor>.
* **Сообщите своим UA-партнерам об изменении дохода.** Рекламные сети, которые раньше получали неваловой доход из постбэка `af_purchase`, после миграции увидят другие значения.
* **Спланируйте график выпуска новой версии приложения.** После 7 сентября 2026 г. пользователи версий приложения, собранных с версиями SDK ниже Android версии 6.17.5 или iOS версии 6.17.8, перестанут генерировать проверенные события `af_purchase`. Выпустите новую версию приложения заранее, чтобы до прекращения поддержки она успела охватить большинство ваших пользователей.

</Accordion>

<div id="h_migration_upgrade_path" />

<Accordion title="Переход на ROI360 Store Revenue">

Для перехода на ROI360 Store Revenue не требуется изменять SDK, так как оба продукта используют один и тот же метод `validateAndLogInAppPurchase` (v2). Добавление Purchase Connector для автоматического определения покупок необязательно.

Дополнительную информацию и инструкции по настройке см. в статье <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-store-revenue">Настройка дохода магазина ROI360</Anchor>.

</Accordion>

<div id="overview" />

## Информация о компании

<div id="note" />

> 📘 **Примечание:**
>
> Дополнительную информацию о валидации чека, включая принцип её работы и способ её включения в AppsFlyer, см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-receipt-validation">О валидации чека</Anchor>.

Чтобы настроить валидацию чека, выполните следующие шаги по порядку:

1. Настройте учётные данные магазина (iOS и Android)
   * [iOS](#шаг-1-ios-настройка-ключей-app-store-connect): Настройте ключи App Store Connect (ключ In-App Purchase, идентификатор Key ID и идентификатор Issuer ID) в AppsFlyer, чтобы включить валидацию чека.
   * [Android](#шаг-1-android-настройка-разрешений-и-ключа-учётной-записи-службы): Настройте сервисный аккаунт Google Cloud, задайте необходимые разрешения в Google Play Console и загрузите JSON-ключ сервисного аккаунта в AppsFlyer.
2. [Реализуйте SDK API validateAndLog](#2-внедрение-sdk): Подготовьте разработчиков к интеграции AppsFlyer SDK API `validateAndLog` и настройте среду sandbox для тестирования.
3. [Проверьте реализацию SDK API validateAndLog](#3-проверьте-использование-sdk): Выполните тестовые покупки и подписки в sandbox на iOS и Android, чтобы убедиться, что события валидации чека генерируются и корректно регистрируются в AppsFlyer.
4. [Проверьте и обновите настройки](#шаг-6-проверьте-и-обновите-настройки): Убедитесь, что для типа продукта задана валидация чека, и проверьте статусы ключей магазина и интеграции SDK, чтобы обеспечить точное и непрерывное измерение дохода.
5. [Выпустите версии приложения с SDK API validateAndLog](#шаг-5-выпустите-версии-приложения-с-sdk-api-validateandlog): Выпустите обновлённые версии приложения со встроенным SDK API `validateAndLog`, убедившись, что флаги sandbox отключены, а необходимые события в приложении не блокируются правилами валидации.

<div id="step-1-ios-set-up-app-store-connect-keys" />

## Шаг 1 (iOS) Настройка ключей App Store Connect

На шаге 1 получите следующие учётные данные из *App Store Connect* и введите их на странице **Revenue Settings** на платформе AppsFlyer.

* ключ для покупок в приложении;
* идентификатор ключа;
* идентификатор эмитента.

**Прежде чем начать**:

* Настройка учётных данных включает шаги, выполняемые как в App Store Connect, так и в AppsFlyer. Держите вкладки App Store Connect и AppsFlyer открытыми во время настройки.
* Для вашего приложения iOS требуется StoreKit v1 или v2, который предоставляет фреймворк для обработки покупок в приложении и подписок.

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 Создание ключей App Store Connect">

Чтобы настроить учётные данные iOS, выполните следующие шаги:

1. В App Store Connect перейдите в **Users and Access**.

   [![](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)
2. Перейдите в **Users and Access** > **Integrations** и в списке **Keys** выберите **In-App Purchase**.

   [![](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)
3. Нажмите + , чтобы сгенерировать новый ключ In-App Purchase.

   [![](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)
4. Введите название для вашего ключа API.
5. Нажмите **Создать**.
6. Нажмите **Download In-App Purchase Key** next to the key you just generated to download it. **Примечание**: Вы можете скачать ключ только один раз.
7. Скопируйте **Key ID** ключа, который вы только что сгенерировали, и вставьте его в настройки покупок & подписок AppsFlyer в поле **Key ID**.

   [![](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)
8. Скопируйте **Issuer ID**. **Примечание**: если **Issuer ID** не отображается в верхней части страницы, создайте ключ API App Store Connect (с любым уровнем доступа). После этого Issuer ID появится в верхней части страницы ключа In-App Purchase.

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

</Accordion>

<div id="12-set-the-app-store-connect-key" />

<Accordion title="1.2 Set the App Store Connect key">

1. Включите валидацию чека. #включить-валидацию-чека
2. На шаге **Ключи App Store Connect** нажмите [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.45%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **Upload** в поле **In-App Purchase key** , чтобы загрузить файл p8.
3. В разделе titled **App Store Connect keys**, вставьте значения, которые вы скопировали из App Store Connect.

   * **идентификатор ключа;**
   * **идентификатор эмитента.**
4. Нажмите 0**Validate keys** 0, чтобы убедиться, что введённые вами ключи верны. **Примечание**: The **Validate keys** action может не работать, если ваше приложение ещё не опубликовано в App Store.
5. Нажмите **Сохранить и продолжить**.

</Accordion>

<div id="step-1-android-set-up-service-account-key-and-permissions" />

## Шаг 1 (Android). Настройка разрешений и ключа учётной записи службы

На шаге 1 получите следующие учётные данные из *Google Play* и *Google Cloud* и введите их на странице **Настройки дохода** на платформе AppsFlyer.

**Прежде чем начать**:

* Настройка измерения дохода от покупок в приложении и подписок включает шаги, выполняемые в <Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>, <Anchor target="_blank" href="https://play.google.com/console/">Google Play Console,</Anchor> и the <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">UI AppsFlyer</Anchor>. Мы рекомендуем не закрывать все три вкладки на протяжении всего процесса настройки.
* Для настройки в пользовательском интерфейсе AppsFlyer требуются права администратора.

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1 Свяжите свой аккаунт разработчика Google Play со своим проектом Google Cloud">

**Предварительные условия**: доступ к Google Play Console и проекту Google Cloud.

**Чтобы связать свой аккаунт разработчика Google Play со своим проектом Google Cloud, выполните следующие действия**:

1. В Google Play Console откройте свой аккаунт разработчика Google Play.
2. Привяжите аккаунт к своему проекту вGoogle Cloud. Инструкции см. в этом <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">разделе справки Google</Anchor>.
3. Активируйте API разработчика Google Play. Инструкции см. в <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">этом разделе справки Google</Anchor>.

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2 Настройте свой сервисный аккаунт на платформе Google Cloud">

**Предварительные условия**: доступ к Google Cloud Platform.

**Чтобы настроить свой сервисный аккаунт, выполните следующие действия**:

1. Создайте или найдите **сервисный аккаунт**:

   1. <span class="af-ol-a"></span>Перейдите в раздел **Service Accounts** на платформе Google Cloud и нажмите **CREATE SERVICE ACCOUNT**.[![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. Введите данные для сервисного аккаунта.[![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. Скопируйте адрес электронной почты.[![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. Нажмите **Create and continue**.[![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. На шаге **Grant this service account access to the project** выберите роль подписчика **Pub/Sub**.[![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. Нажмите **Continue** > **Done**.

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. Скачайте service account private key:

   1. <span class="af-ol-a"></span>В Google Cloud Platform перейдите в раздел **Service accounts**, найдите в списке нужный аккаунт (тот, который вы только что создали) и нажмите значок **More actions**.
   2. Нажмите **Manage keys**.[![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. Нажмите 0**Добавить ключ** 0> 0**Создать новый ключ**.

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. Во всплывающем окне **Create private key** в разделе **Key type** выберите **JSON** и нажмите **Create**.[![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. Нажмите 0**Create**. Загрузится файл JSON закрытого ключа.

      [![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. Сохраните файл ключа JSON, который вы позже загрузите в AppsFlyer. **Важно!** Вы должны сохранить ключ. его нельзя будет получить позже. Если вы его не сохраните, вам придётся создать совершенно новый ключ.

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3 Настройте права доступа к API в Google Play Console">

**Предварительные условия**: доступ к Google Play Console.

**Примечание**: после настройки учётных данных и разрешений сервисного аккаунта может пройти некоторое время (иногда до 24 часов), прежде чем вы сможете их использовать. Это может привести к появлению ошибок на последующих этапах.

**Настройка прав доступа к API в Google Play Console**:

1. В Google Play Console перейдите в раздел 0**Пользователи и разрешения**, найдите созданный сервисный аккаунт и нажмите 0**Пригласить новых пользователей**.

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. Введите **адрес электронной почты** , который вы скопировали при настройке учётной записи службы на шаге 1.2.1.3.

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. В разделе 0**Разрешения** 0перейдите на вкладку 0**Разрешения аккаунта** 0и выберите оба варианта:

   * Просматривать финансовые данные, заказы и ответы на анкетирование после отмены.
   * Управление заказами и подписками.[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. На вкладке 0**Разрешения приложения** 0нажмите 0**Добавить приложение, 0**затем выберите ваше приложение. Добавьте несколько приложений, если необходимо.

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. Нажмите 0**Пригласить пользователя**.

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. Во всплывающем окне подтверждения нажмите 0**Отправить приглашение**.

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4 Загрузите закрытый ключ сервисного аккаунта в AppsFlyer">

Загрузите и выполните валидацию ключа JSON Google, который вы скачали в 0[шаге 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).

**Предварительные условия**: права администратора в AppsFlyer.

**Чтобы загрузить закрытый ключ сервисного аккаунта в AppsFlyer, выполните следующие шаги**:

1. <Anchor target="_blank" href="/marketers/ru/docs/about-receipt-validation#активировать-валидацию-чека">Активируйте валидацию чека</Anchor><Anchor target="_blank" href="/marketers/ru/docs/about-receipt-validation#активировать-валидацию-чека">.</Anchor>
2. На этапе **Ключ сервисного аккаунта и разрешения** в поле **Загрузить ключ Google JSON** нажмите [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.23%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **Загрузить**.
3. Загрузите файл JSON, который вы скачали в 0[шаге 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).
4. Нажмите 0**Проверить ключ**. **Примечание.**

   * После установки учётных данных и разрешений аккаунта службы может пройти до 24 часов, прежде чем вы сможете их использовать. Из-за этого при попытке валидации ключа или выполнить тестовую проверку могут возникнуть ошибки.
   * Чтобы обойти 24-часовое время ожидания, в Google Play Console перейдите к любому приложению, затем откройте **Monetize** > **Products** > **Subscriptions/In-app products**, и внесите изменения. Например, отредактируйте описание вашего продукта и сохраните его. Обычно это приводит к немедленному обновлению учётных данных и разрешений аккаунта. Затем вы можете отменить эти изменения.
5. Нажмите **Далее**. Откроется шаг **Внедрение SDK**.

</Accordion>

<div id="step-2-implement-sdk" />

## 2. Внедрение SDK

На этом шаге вы подготовите разработчиков к интеграции API `validateAndLog` в SDK и настроите среду песочницы для тестирования. Минимальные версии SDK, поддерживающие последнюю версию API `validateAndLog`: **6.17.5** для Android и **6.17.8** для iOS.

Чтобы внедрить validateAndLog SDK API, выполните следующие шаги:

1. На шаге **Внедрение SDK** скопируйте **готовое сообщение** отображаемое в дэшборде.
2. Отправьте его своим разработчикам. оно включает в себя:

   * название и идентификатор приложения;
   * Ссылку на <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">руководство по интеграции SDK</Anchor>.
   * Инструкции по настройке среды песочницы (`sandbox = true`).
   * Этапы тестирования (с использованием **TestFlight**).

   Это сообщение содержит всю информацию, необходимую вашим разработчикам для завершения интеграции и начала тестирования.
3. Нажмите **Далее**. Откроется шаг **Проверка внедрения SDK**.

<div id="step-3-verify-sdk-implementation" />

## 3. Проверьте использование SDK

Протестируйте интеграцию доходов от покупок в приложении и подписок в среде песочницы, чтобы убедиться, что коннектор SDK интегрирован правильно, а серверные уведомления должным образом настроены и принимаются AppsFlyer.

<div id="test-sdk-implementation" />

<Accordion title="Тестирование реализации SDK">

Чтобы проверить, получал ли AppsFlyer действительные полезные данные `validateAndLog` из вашего приложения за последние 7 дней, выполните следующие действия:

1. На шаге **Проверка внедрения SDK** нажмите **Проверить внедрение SDK**.
2. Просмотрите результаты, включая метку времени последней полезной нагрузки, полученной AppsFlyer. Обратите внимание, что эта проверка только подтверждает, что запросы доходят до AppsFlyer, и не проверяет полноту или корректность данных.
3. Чтобы полностью проверить внедрение, выполните шаги тестирования, приведённые ниже.

</Accordion>

<div id="sandbox-environment-considerations" />

<Accordion title="Соображения по поводу среды песочницы">

В среде песочницы:

* Только события первичной покупки приводят к тому, что validateAndLog SDK API создаёт событие, которое регистрируется AppsFlyer. Событие покупки в приложении называется `af_purchase_sandbox_sdk`. Событие подписки называется `af_ars_sandbox_sdk`.
* События в тестовой среде имеют доход 0.
* Для Android тесты, выполняемые License Testers, приводят к событиям песочницы, даже если среда песочницы в SDK не настроена.

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="Тестирование измерения доходов от внутренних покупок (IAP) и подписок">

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

**Чтобы протестировать доходы от покупок в приложении и подписок**:

1. Попросите разработчиков следовать их инструкциям по настройке среды sandbox для SDK API validateAndLog.
2. Совершите тестовую покупку или оформите подписку с помощью <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">License Tester в Google Play</Anchor> и <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight в iOS</Anchor>.
3. Проверьте, что тестовые события отображаются одним из следующих способов:

   * Просмотрите событие в <Anchor target="_blank" href="/marketers/ru/docs/testing-the-sdk-integration-for-marketers#view-live-events">Live event viewer.</Anchor>
   * Просмотрите данные события в <Anchor target="_blank" href="/marketers/ru/docs/activity-metrics-in-my-dashboards">My Dashboards - Activity View</Anchor>.
4. Найдите следующие тестовые события:

   * The `af_purchase_sandbox_sdk` для события покупки.
   * The `af_ars_sandbox_sdk` для события подписки.
5. Убедитесь, что тестовые события включают следующее:

   * Значение дохода равно **0** (чтобы не искажать реальные отчеты AppsFlyer).
   * Параметр `af_sandbox_revenue` , который включает значение дохода от приобретенного продукта, чтобы обеспечить корректное отражение дохода в отчетах.
   * Параметр `af_validated` имеет значение `true`. Если `af_validated` имеет значение `false`, вернитесь к шагу 2 выше и проверьте ключ, предоставленный магазином
   * Параметр `af_validation_type` имеет значение `receipt_validation`.

</Accordion>

<div id="step-4-verify-and-update-settings" />

## Шаг 6. Проверьте и обновите настройки

После завершения настройки параметров выше и сохранения выполненных шагов вы будете перенаправлены в представление активной конфигурации, где сможете проверить или обновить следующие настройки:

1. Убедитесь, что для параметра **Product type** выбрано значение **валидация чека**
2. Убедитесь, что **Verify purchases with the App Store** включен.
3. Проверьте или обновите следующие настройки:

   * The **App Store key** setup
   * The **SDK integration** setup

<div id="step-5-release-the-app-versions-with-the-validateandlog-sdk-api" />

## Шаг 5. Выпустите версии приложения с SDK API validateAndLog

После того как все на предыдущих шагах настроено, а AppsFlyer API validateAndLog SDK интегрирован в приложение, попросите разработчиков выпустить версию приложения с интегрированным API validateAndLog SDK.

Прежде чем разработчики выпустят новую версию приложения, убедитесь, что:

* События в приложении, которые вы хотите регистрировать как <Anchor target="_blank" href="/marketers/ru/docs/about-receipt-validation#события-покупок-в-приложении-и-параметры-валидации-чека">покупки в приложении или подписки</Anchor>, не блокируются ни одним из правил валидации, настроенных в AppsFlyer.
* У всех ваших разработчиков все sandbox-флаги установлены в значение `false`.

[<Image alt="" src="https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png" width="512px" />](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

После релиза приложения с SDK API validateAndLog <Anchor target="_blank" href="/marketers/ru/docs/about-receipt-validation#события-покупок-в-приложении-и-параметры-валидации-чека">события покупок в приложении и подписок</Anchor> генерируются и становятся доступны на всех дэшбордах AppsFlyer, а также в агрегированных отчетах и отчетах о сырых данных.

События генерируются только для пользователей, которые обновили приложение до версии, включающей validateAndLog SDK API. В результате до полного перехода на обновленную версию приложения ожидается расхождение между данными о доходе из приложения и данными магазина.

<div data-zendesk-anchors="h_migrating-from-legacy=%D0%BF%D0%B5%D1%80%D0%B5%D1%85%D0%BE%D0%B4-%D0%BD%D0%B0-%D0%BD%D0%BE%D0%B2%D1%83%D1%8E-%D0%B2%D0%B0%D0%BB%D0%B8%D0%B4%D0%B0%D1%86%D0%B8%D1%8E-%D1%87%D0%B5%D0%BA%D0%B0 upgrade-to-new-receipt-validation=%D0%BF%D0%B5%D1%80%D0%B5%D1%85%D0%BE%D0%B4-%D0%BD%D0%B0-%D0%BD%D0%BE%D0%B2%D1%83%D1%8E-%D0%B2%D0%B0%D0%BB%D0%B8%D0%B4%D0%B0%D1%86%D0%B8%D1%8E-%D1%87%D0%B5%D0%BA%D0%B0 whats-new-in-receipt-validation=h_migration_key_differences prepare-the-migration=h_migration_what_to_plan switch-to-roi360-store-revenue=h_migration_upgrade_path overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01KD0RY1HMV71TGDZZX7JWM3XJ=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01KD0RY1HMMSR4ZDW5GF4N05P1=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 step-1-ios-set-up-app-store-connect-keys=%D1%88%D0%B0%D0%B3-1-ios-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%B9-app-store-connect h_01KD0RY1HM14KNGKADCBMHJXH6=%D1%88%D0%B0%D0%B3-1-ios-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%B9-app-store-connect h_01KD0RY1HM08AS4RGNR1QE598K=11-create-the-app-store-connect-keys h_01KD0RY1HMPJGGHQ19D5K70JSZ=12-set-the-app-store-connect-key step-1-android-set-up-service-account-key-and-permissions=%D1%88%D0%B0%D0%B3-1-android-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B8-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%83%D1%87%D1%91%D1%82%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D0%B8-%D1%81%D0%BB%D1%83%D0%B6%D0%B1%D1%8B h_01KD0RY1HMG9DGKGEY8XVR3K7Z=%D1%88%D0%B0%D0%B3-1-android-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B8-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%83%D1%87%D1%91%D1%82%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D0%B8-%D1%81%D0%BB%D1%83%D0%B6%D0%B1%D1%8B h_01KD0RY1HMRK0B1Z4FKD0DD2KQ=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD0RY1HN9ER2FZ7XN93SGEN9=12-configure-your-service-account-in-the-google-cloud-platform h_01KD0RY1HN03Y7T4KCNYX9FWS0=13-set-api-access-permissions-in-google-play-console h_01KD0RY1HNS6EPAKZ4YY3MZZK9=14-upload-the-service-account-private-key-to-appsflyer step-2-implement-sdk=2-%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-sdk h_01KD0RY1HN63X3WM1RH19W2HZ5=2-%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-sdk step-3-verify-sdk-implementation=3-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-sdk h_01KD0RY1HNDMSWGDW6ZQDZ5DAM=3-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-sdk h_01KD0RY1HNC4VXSRFC1ZMKWWS6=test-sdk-implementation h_01KD0RY1HNDFF6J29AHG6S4EFM=sandbox-environment-considerations h_01KD0RY1HN5EBX3VGMH5PNHTA8=test-inapp-purchase-and-subscription-revenue step-4-verify-and-update-settings=%D1%88%D0%B0%D0%B3-6-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%B8-%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01KD0RY1HN2HZEW9ANBPNRMXPP=%D1%88%D0%B0%D0%B3-6-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%B8-%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 step-5-release-the-app-versions-with-the-validateandlog-sdk-api=%D1%88%D0%B0%D0%B3-5-%D0%B2%D1%8B%D0%BF%D1%83%D1%81%D1%82%D0%B8%D1%82%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81-sdk-api-validateandlog h_01KD0RY1HNECTDNNHK78F9KDPS=%D1%88%D0%B0%D0%B3-5-%D0%B2%D1%8B%D0%BF%D1%83%D1%81%D1%82%D0%B8%D1%82%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81-sdk-api-validateandlog" />

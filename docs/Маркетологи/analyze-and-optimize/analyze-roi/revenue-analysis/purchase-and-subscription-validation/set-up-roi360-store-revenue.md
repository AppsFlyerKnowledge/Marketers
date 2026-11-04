---
title: Доход магазина ROI360
metadata:
  keywords:
    - Premium
    - Advertisters
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-22T11:05:11Z'
  edited_at: '2026-08-27T00:01:25Z'
  id: 42158608158353
  locale: ru
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/ru/articles/42158608158353
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Кратко:** Настройте решение AppsFlyer ROI360 по доходу магазина.

<div id="important" />

> 🚧 **Двоеточие (:)**
>
> Выручка магазина ROI360 доступна только клиентам премиум-плана ROI360. Чтобы проверить свой тарифный план или перейти на более высокий, обратитесь к своему менеджеру по работе с клиентами (CSM).

<div id="overview" />

## Информация о компании

<div id="note" />

> 📘 **Примечание:**
>
> Дополнительные сведения о ROI360, в том числе о принципе его работы и о том, как включить его в AppsFlyer, см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-roi360-store-revenue">О доходе магазина ROI360</Anchor>.

Чтобы настроить ROI360 Store Revenue, выполните следующие шаги по порядку:

1. Настройте учётные данные магазина (iOS и Android):
   * [iOS:](#шаг-1-ios-настройка-ключей-app-store-connect) Настройте ключи App Store Connect (ключ In-App Purchase, Key ID и Issuer ID) в AppsFlyer.
   * [Android](#step-1-android-настройка-ключа-сервисного-аккаунта-и-разрешений): Настройте сервисный аккаунт Google Cloud, задайте необходимые разрешения в Google Play Console и загрузите JSON-ключ сервисного аккаунта в AppsFlyer.
2. Настройте уведомления сервера (iOS и Android):
   * [iOS](#шаг-2-ios-настройка-уведомлений-сервера-app-store): Настройте App Store Server Notifications: отправляйте уведомления напрямую в AppsFlyer (рекомендуется) или перенаправляйте их с собственной конечной точки, а затем проверьте интеграцию.
   * [Android](#шаг-2-android-настройка-уведомлений-сервера-google-play): Настройте уведомления разработчика Google Play в реальном времени (RTDN): разрешите Google Play отправлять уведомления напрямую в AppsFlyer (рекомендуется) или перенаправляйте их через Pub/Sub.
3. [Внедрите SDK Connector](#шаг-3-реализация-коннектора-sdk): подготовьте разработчиков к интеграции AppsFlyer Purchase SDK Connector.
4. [Проверьте реализацию SDK](#шаг-4-проверка-реализации-sdk): протестируйте sandbox-покупки in-app и подписки на обеих платформах, чтобы убедиться, что события SDK и уведомления сервера корректно принимаются и обрабатываются в AppsFlyer.
5. [Проверьте и обновите настройки](#шаг-5-проверьте-и-обновите-настройки): проверьте и подтвердите статусы валидации покупок, обработки возвратов, измерения подписок и интеграции с магазином, чтобы обеспечить точную и непрерывную атрибуцию дохода на разных платформах.
6. [Выпустите версии приложения](#шаг-6-выпустите-версии-приложения-с-коннектором-sdk): выпустите обновлённые версии приложения со встроенным SDK Connector, убедившись, что sandbox-флаги отключены, а правила валидации допускают необходимые события дохода.

<div id="step-1-ios-set-up-app-store-connect-keys" />

## Шаг 1 (iOS): Настройка ключей App Store Connect

На шаге 1 получите следующие учётные данные в App Store Connect и введите их на странице «Настройки дохода» на платформе AppsFlyer

* ключ для покупок в приложении;
* идентификатор ключа;
* идентификатор эмитента.

**Прежде чем начать**:

Настройка учётных данных включает шаги, выполняемые как в App Store Connect, так и в AppsFlyer. Держите вкладки App Store Connect и AppsFlyer открытыми во время настройки.

<div id="11-create-the-app-store-connect-keys" />

<Accordion title="1.1 Создание ключей App Store Connect">

Чтобы настроить учётные данные iOS, выполните следующие шаги:

1. В App Store Connect перейдите в **Пользователи и доступ**

   [![](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)](https://files.readme.io/34b3e97bf4401aa8896662a3a949b393bc7786b60762567cb6949ec615eddfde-33405937624849.png)
2. Перейдите в **Пользователи и доступ** > **Интеграции**, и в списке **Ключи** выберите **In-App Purchase**.

   [![](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)](https://files.readme.io/8ca4e57e716ea28e4f72074bd5b927b3f1b99aadfbdf791565b31604644f3ed2-33372428310929.png)
3. Нажмите + чтобы сгенерировать новый ключ In-App Purchase.

   [![](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)](https://files.readme.io/b9d59f9c1cdd2c232b8f21bff95b800c107e700095622b8fdd9d4e1fcd1f798f-33405937633297.png)
4. Введите название для вашего ключа API.
5. Нажмите **Создать**.
6. Нажмите **Download In-App Purchase Key** рядом с ключом, который вы только что сгенерировали, чтобы загрузить его. **Примечание**: Вы можете скачать ключ только один раз.
7. Скопируйте **Key ID** ключа, который вы только что сгенерировали, и вставьте его в настройках покупок & подписок AppsFlyer в поле **Key ID**.

   [![](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)](https://files.readme.io/681a546b5eaf3dd8304d82f01316281aed269982860528244b1954499f04b290-33405907545361.png)
8. Скопируйте **Issuer ID**. **Примечание**: если **Issuer ID** не отображается вверху страницы, создайте API-ключ App Store Connect (с любым уровнем доступа). После этого идентификатор эмитента появится в верхней части страницы для ключа покупки в приложении.

   [![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmSumtIHlYN5qrkRKGp-CLtjQG42__uc9a8YOseildcyEryXdC6msP3rShuUN7ezOk7qMT0wgJ-xP1Z-qT31kufDyidX_l-FYbx4kSJblM1kl5On2aDXzR4xSOSydyIM8Mm5khQQ?key=2hTJo3FPQZul9a_zeStquw)

</Accordion>

<div id="12-set-the-app-store-connect-key-in-appsflyer" />

<Accordion title="1.2 Настройка ключа App Store Connect в AppsFlyer">

1. <Anchor target="_blank" href="/marketers/ru/docs/about-roi360-store-revenue#активируйте-выручку-магазина-roi360">Включите ROI360 Store Revenue</Anchor>.
2. На шаге **App Store Connect keys** кликните [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **Upload** в **In-App Purchase key** поле, чтобы загрузить файл p8.
3. В разделе titled **App Store Connect keys**, вставьте значения, которые вы скопировали из App Store Connect.

   * **идентификатор ключа;**

   * **идентификатор эмитента.**
4. Кликните **Validate keys** , чтобы убедиться, что введённые вами ключи верны. **Примечание: Validate key** может не работать, если ваше приложение ещё не опубликовано в App Store.
5. нажмите **Сохранить и продолжить**

</Accordion>

<div id="step-1-android-set-up-service-account-key-and-permissions" />

## Step 1 (Android): Настройка ключа сервисного аккаунта и разрешений

На шаге 1 вы можете получить следующие учётные данные из App Store Connect и введите их на странице «Настройка дохода» на платформе AppsFlyer.

**Прежде чем начать**:

* Настройка измерения дохода от покупок в приложении и подписок включает шаги, выполняемые в <Anchor target="_blank" href="https://cloud.google.com/">Google Cloud Platform</Anchor>, <Anchor target="_blank" href="https://play.google.com/console/">Google Play Console</Anchor>, и в <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">интерфейсе AppsFlyer</Anchor>. Мы рекомендуем не закрывать все три вкладки на протяжении всего процесса настройки.
* Для настройки в интерфейсе AppsFlyer требуются права администратора.

<div id="11-link-your-google-play-developer-account-to-your-google-cloud-project" />

<Accordion title="1.1. Привяжите аккаунт разработчика Google Play к проекту в Google Cloud">

**Предварительные условия**: доступ к Google Play Console и проекту в Google Cloud.

**Чтобы привязать свой аккаунт разработчика Google Play к проекту в Google Cloud, выполните следующие действия**:

1. В Google Play Console откройте свой аккаунт разработчика в Google Play Developer .
2. Привяжите аккаунт к своему проекту вGoogle Cloud. Инструкции см. в этом <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#linking">разделе справки Google</Anchor>.
3. Активируйте API разработчика Google Play. Инструкции см. в <Anchor target="_blank" href="https://developers.google.com/android-publisher/getting_started#enable">этом разделе справки Google</Anchor>.

   [![](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)](https://files.readme.io/67852d990ca3ff9e48708fb74ec59c84009b33699e3094688d113f138cc4c847-42144934507665.png)

</Accordion>

<div id="12-configure-your-service-account-in-the-google-cloud-platform" />

<Accordion title="1.2. Настройте свой сервисный аккаунт на Google Cloud Platform">

**Предварительные условия**: доступ к Google Cloud Platform.

**Чтобы настроить свой сервисный аккаунт, выполните следующие действия**:

1. Создайте или найдите **Service Account**:
   1. <span class="af-ol-a"></span>Перейдите в **Service accounts** раздел в Google Cloud Platform и нажмите **Create Service Account**.

      [![](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)](https://files.readme.io/044db0b4d6fb556ab70d1f5a31b2e63ef45443e21d5f22c026460adbdfc8b238-42144939169937.png)
   2. Введите данные для сервисного аккаунта.

      [![](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)](https://files.readme.io/a78faa6f79b79a3a8238963ce2139fd262bc4467730fbb4fa6188f9356eac13c-42144934512785.png)
   3. Скопируйте адрес электронной почты.

      [![](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)](https://files.readme.io/f4da7e559e22e85446c6e0bb582cdfbd1b85f47702fcf0b3e82397d8cee93e87-42144934515473.png)
   4. Нажмите **Create and continue**.

      [![](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)](https://files.readme.io/56e4d0973444fddb36cfb69960de46b626ad158c92d196ed40eacac2dac0a505-42144939175313.png)
   5. На шаге **Grant this service account access to the project** step выберите роль подписчика **Pub/sub** .

      [![](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)](https://files.readme.io/70b71a09fd401220bb1f507ac8580fc6e446d8922fd8faab00e37a1ce7e265d0-42144934522769.png)
   6. Нажмите **Continue** > **Done**.

      [![](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)](https://files.readme.io/27406f405e31a7ad613b49c92c304e39366b0aee313f6b9eb8c109c5bf5f4a33-42144934524049.png)
2. Скачайте **Service Account Private Key**:
   1. <span class="af-ol-a"></span>В Google Cloud Platform перейдите в раздел **Service accounts** , найдите в списке нужный аккаунт (тот, который вы только что создали) и кликните значок **More actions** .
   2. Кликните **Управление ключами**.

      [![](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)](https://files.readme.io/4b35fffa35f6b84112b4e6bdcb7656f3ddc1d72599140195f5a21158111f371f-42144934526353.png)
   3. Нажмите **Add key** > **Create new key**.

      [![](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)](https://files.readme.io/01b244c8fb818b9b479e154876de2a3a5ff258b2d7e83a91a2ea804791cd3e26-42144939182097.png)
   4. Во всплывающем окне **Create private key** в разделе **Key type**, выберите **JSON**, и нажмите **Create**.

      [![](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)](https://files.readme.io/713f0a2c0c2aca1bab8b965291d8e9839b1e183dac63e66721064be67b879c5f-42144939185297.png)
   5. Нажмите **Создать**. Загрузится файл JSON закрытого ключа.

      [![](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)](https://files.readme.io/ab22f49448fa2b2a392fc4a1e27e9570fcdecaa9aa9ae8f0f7056dedf70ef9ac-42144934528529.png)
   6. Сохраните файл ключа JSON, который нужно будет загрузить в AppsFlyer позже. **Важно!** Ключ необходимо сохранить; его нельзя будет загрузить позже. Если вы его не сохраните, вам придётся генерировать ключ заново.

</Accordion>

<div id="13-set-api-access-permissions-in-google-play-console" />

<Accordion title="1.3. Настройка прав доступа к API в Google Play Console">

**Предварительные условия**: доступ к Google Play Console.

**Примечание**: после установки учетных данных и разрешений аккаунта службы может пройти некоторое время (иногда до 24 часов), прежде чем вы сможете их использовать. Это может привести к появлению ошибок на последующих этапах.

**Настройка прав доступа к API в Google Play Console**:

1. В Google Play Console перейдите в раздел **Пользователи и разрешения**, найдите созданный сервисный аккаунт и нажмите кнопку **Пригласить новых пользователей**.

   [![](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)](https://files.readme.io/cd78d8eb4daf7d81dbe429c75b5e433f0244e3f1a9373bd49392fe0a48e7fa74-42144939189265.png)
2. Введите **адрес электронной почты** который вы скопировали при настройке сервисного аккаунта на шаге 1.2.1.3.

   [![](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)](https://files.readme.io/93cf0394b19d75901fbc70eab570a4d34aec23b0d43ce85e5e18f1c2cf219407-42144934531217.png)
3. В разделе **Разрешения** перейдите на вкладку **Разрешения аккаунта** и выберите оба варианта:

   * Просматривать финансовые данные, заказы и ответы на анкетирование после отмены.
   * Управление заказами и подписками.[![](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)](https://files.readme.io/90e9603142babec1a86e3788db4b71f6efbd3bb6e3969c9e29153e3fa4b9597d-42144939195409.png)
4. На вкладке **Разрешения приложения** нажмите **Добавить приложение,** затем выберите ваше приложение. Добавьте несколько приложений, если необходимо.

   [![](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)](https://files.readme.io/ad6e0b452d94a6bc7747f2b6386dd0fd52ed9ce654870ff26e866b9f7eb670e6-42144934538641.png)
5. Нажмите **Пригласить пользователя.**

   [![](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)](https://files.readme.io/207e877e404195eb6420a91aab5106843596d23bb4b59abbc825ac664cbeadea-42144934539537.png)
6. Во всплывающем окне подтверждения нажмите **Отправить приглашение**.

   [![](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)](https://files.readme.io/ca5010e1312cb7cb99bef435f139ea9c44ecaccf491e0b6d2720119e39175bc6-42144934540433.png)

</Accordion>

<div id="14-upload-the-service-account-private-key-to-appsflyer" />

<Accordion title="1.4. Загрузите закрытый ключ сервисного аккаунта в AppsFlyer">

Загрузите и выполните валидацию ключа JSON Google, который вы скачали в [шаге 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).

**Предварительные условия**: доступ администратора к AppsFlyer.

**Чтобы загрузить закрытый ключ учетной записи службы в AppsFlyer, выполните следующие шаги**:

1. <Anchor target="_blank" href="/marketers/ru/docs/about-roi360-store-revenue#активируйте-выручку-магазина-roi360">Включите данные о доходах магазина в ROI360</Anchor>.
2. На этапе **Ключ и разрешения служебной учётной записи** в поле **Загрузить ключ JSON Google** нажмите [<Image alt="" src="https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png" width="2.2%" />](https://files.readme.io/33006d5242412a3e5d81196002067c119f188b28456634b898d1f10b44dad2be-27881642552593.png) **(значок загрузки).**
3. Загрузите файл JSON, который вы скачали в [шаге 1.2](#12-configure-your-service-account-in-the-google-cloud-platform).
4. Нажмите **Проверить ключ.** **Примечание:**
   * После установки учётных данных и разрешений аккаунта службы может пройти до 24 часов, прежде чем вы сможете их использовать. Из-за этого при попытке валидации ключа или выполнить тестовую проверку могут возникнуть ошибки.
   * Чтобы обойти 24-часовое время ожидания, в Google Play Console откройте любое приложение, затем перейдите в **Монетизация** > **Продукты** > **Подписки/In-app products**, и внесите изменения. Например, отредактируйте описание вашего продукта и сохраните его. Это должно привести к мгновенному обновлению учётных данных и разрешений аккаунта. Затем вы можете отменить эти изменения.
5. Нажмите **Сохранить и продолжить**.

</Accordion>

<div id="step-2-ios-set-up-app-store-server-notifications" />

## Шаг 2 (iOS): Настройка уведомлений сервера App Store

Задайте способ получения уведомлений от App Store в AppsFlyer.

* Если в App Store Connect у вас уже настроен endpoint для уведомлений сервера App Store (например, ваш собственный бэкенд или другой сервис), выберите **Вариант 1 (рекомендуется)** или **Вариант 2**.
* Если вы еще не настроили endpoint в App Store Connect, выберите **Вариант 1**.

<div id="option-1-recommended---appsflyer-as-the-primary-endpoint" />

#### Вариант 1 (рекомендуется) — AppsFlyer как основной endpoint

Замените существующий URL-адрес уведомлений в App Store Connect на endpoint AppsFlyer и добавьте прежний endpoint в AppsFlyer как адрес назначения для пересылки. Текущая логика подписки и рабочие процессы остаются без изменений и продолжают работать как и ожидалось.

Поток уведомлений для этого варианта выглядит следующим образом:

1. App Store Connect отправляет уведомления в AppsFlyer
2. AppsFlyer обрабатывает их для ROI360
3. AppsFlyer пересылает все уведомления на вашу существующую конечную точку **в реальном времени**

Чтобы использовать этот вариант, выполните шаги [2.1](#21-copy-the-appsflyer-server-notifications-endpoint), [2.2](#22-send-notifications-directly-to-appsflyer) и [2.4](#24-test-the-server-notifications-integration).

<div id="option-2---your-endpoint-as-the-primary-endpoint" />

#### Вариант 2 — ваша конечная точка как основная

Если вы предпочитаете оставить существующую конечную точку в качестве основного адресата, настройте свой сервер так, чтобы он пересылал серверные уведомления App Store в AppsFlyer.

Чтобы использовать этот вариант, пропустите шаги 2.1, 2.2 и выполните шаги [2.3](#23--optional--forward-notifications-from-your-endpoint-to-appsflyer) и [2.4](#24-test-the-server-notifications-integration)

<div id="note-1" />

> 📘 **Примечание**
>
> Apple поддерживает только одну конечную точку серверных уведомлений App Store для каждого приложения и отправляет на нее все типы уведомлений, а не только уведомления о покупках и подписках. AppsFlyer использует уведомления о покупках и подписках для измерения дохода. Любой другой тип уведомлений он подтверждает обратно в Apple, чтобы Apple прекратила повторные попытки отправки, но не обрабатывает его и не выполняет по нему никаких действий.
>
> Если ваше приложение зависит от типов уведомлений помимо уведомлений о покупках и подписках (например, уведомлений о согласии), убедитесь, что эти уведомления поступают на ваш собственный сервер:
>
> * **Вариант 1:** Оставьте AppsFlyer в качестве основной конечной точки и включите пересылку (шаг 2.1). AppsFlyer пересылает копию всех уведомлений на вашу конечную точку в реальном времени без изменений относительно того, как их отправила Apple, включая типы, которые AppsFlyer не обрабатывает.
> * **Вариант 2:** Оставьте свою конечную точку основным адресатом, чтобы ваш сервер напрямую получал и обрабатывал все типы уведомлений, и пересылайте уведомления о покупках и подписках в AppsFlyer.

<div id="21-copy-the-appsflyer-server-notifications-endpoint" />

<Accordion title="2.1 Копирование конечной точки уведомлений сервера в AppsFlyer">

Чтобы скопировать конечную точку уведомлений сервера AppsFlyer, выполните следующие действия:

1. **В AppsFlyer,** на шаге **Уведомления сервера App Store** скопируйте конечную точку уведомлений сервера AppsFlyer.
2. Если ранее у вас была другая конечная точка серверных уведомлений App Store и вы хотите, чтобы AppsFlyer пересылал на нее уведомления, выберите **Переслать копию уведомлений на ваш сервер (актуально только для варианта 1).**
3. Введите конечную точку для пересылки уведомлений в отображаемом текстовом поле.

</Accordion>

<div id="22-send-notifications-directly-to-appsflyer" />

<Accordion title="2.2 Как отправлять уведомления напрямую в AppsFlyer">

Чтобы отправлять уведомления напрямую в AppsFlyer, настройте AppsFlyer как основную конечную точку серверных уведомлений App Store.

1. В **App Store Connect**, в разделе **Информация о приложении** прокрутите до **Уведомления сервера App Store** и рядом с **URL-адресом производственного сервера**, нажмите **Изменить**.

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. Вставьте [конечную точку уведомлений сервера AppsFlyer, скопированную из AppsFlyer](#21-copy-the-appsflyer-server-notifications-endpoint), выберите **Уведомления версии 2** и нажмите **Сохранить**. **Примечание:** Уведомления версии 1 больше не поддерживаются. Если селектор версии уведомлений не отображается в Apple Store Connect, это означает, что вы уже используете версию 2.

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. В разделе **Информация о приложении** прокрутите до **Уведомления сервера App Store** и рядом с **URL-адресом тестового сервера**, нажмите **Изменить**.

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
4. Вставьте [конечную точку уведомлений сервера AppsFlyer, скопированную из AppsFlyer](#21-copy-the-appsflyer-server-notifications-endpoint), выберите **Уведомления версии 2** и нажмите **Сохранить**. **Примечание:** Уведомления версии 1 больше не поддерживаются. Если селектор версии уведомлений не отображается в App Store Connect, это означает, что вы уже используете версию 2.

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)

</Accordion>

<div id="23--optional--forward-notifications-from-your-endpoint-to-appsflyer" />

<Accordion title="2.3 [Необязательно] Пересылка уведомлений от конечной точки в AppsFlyer">

Используйте этот шаг, только если хотите оставить свою конечную точку основным назначением для серверных уведомлений App Store, вместо того чтобы отправлять уведомления напрямую в AppsFlyer.

Этот вариант не является рекомендуемой настройкой и требует реализации на бэкенде. Если вы уже настроили AppsFlyer как основную конечную точку на шаге **2.2** выше, пропустите этот шаг.

Для пересылки уведомлений сервера от конечной точки в AppsFlyer, выполните следующие действия:

1. В **App Store Connect**, в разделе **Информация о приложении** прокрутите до **Уведомления сервера App Store**, и рядом с **URL-адресом производственного сервера** нажмите **Изменить**.

   [![](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)](https://files.readme.io/3c22959c2d38f25cf0d339bf88381281f13ea924e6db35e6d824837fc4e9483f-42158637544081.png)
2. Вставьте **свой URL-адрес конечной точки сервера**.

   [![](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)](https://files.readme.io/506430461b1890bf1e2c0ed785618a606d7c4bd848a47003e3504f2b8c427695-42158608092561.png)
3. Выберите **Уведомления версии 2. Note:** уведомления версии 1 **больше не поддерживаются**. Если селектор версии уведомлений не отображается в Apple Store Connect, это означает, что вы уже используете версию 2.
4. Нажмите **Сохранить**.
5. В **App Store Connect**, в разделе **Информация о приложении** прокрутите до **Уведомления сервера App Store**, и рядом с **URL-адресом тестового сервера** нажмите **Изменить**.

   [![](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)](https://files.readme.io/196fbb6bd2569e19566a75557c16b4853539d8eb491a3b9430d0139801e6b31c-33376298958481.png)
6. Вставьте **свой URL-адрес конечной точки сервера**.

   [![](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)](https://files.readme.io/8e267eb88e90ea23fa2594660cec6726e26ca89ba906ade8392f5f7a61c034cf-42158637553297.png)
7. Выберите **Уведомления версии 2. Примечание:** Уведомления версии 1 **больше не поддерживаются**.
8. Нажмите **Сохранить**.
9. Настройте бэкенд так, чтобы он пересылал уведомления сервера Apple на URL-адрес конечной точки уведомлений AppsFlyer. Запросы должны в точности соответствовать полезной нагрузке App Store в том виде, в котором она получена от Apple. См. <Anchor target="_blank" href="https://developer.apple.com/documentation/appstoreserverapi/signedpayload#discussion">требования к формату Apple</Anchor>.

</Accordion>

<div id="24-test-the-server-notifications-integration" />

<Accordion title="2.4 Test the server notifications integration">

Чтобы подтвердить, что AppsFlyer правильно получает уведомления сервера App Store, или если вы недавно настроили конечную точку и уведомления сервера еще не поступали:

1. В AppsFlyer перейдите к шагу **Уведомления сервера App Store**.
2. Кликните **Тестировать интеграцию**. AppsFlyer отправляет в Apple тестовый запрос уведомления, проверяет, были ли получены от Apple действительные уведомления за последние 7 дней, и отображает один из следующих результатов:

   * Подтверждение того, были ли получены действительные уведомления.
   * Сообщение о статусе, указывающее, что уведомления не найдены.

   <div id="note-2" />

   > 📘 **Примечание:**
   >
   > Apple может занять несколько секунд на отправку тестового сообщения.


   * Если статус остается недействительным, подождите немного и повторите попытку.
   * После успешного выполнения теста или когда будете готовы продолжить, нажмите **Сохранить и далее**.

</Accordion>

<div id="step-2-android-set-up-google-play-server-notifications" />

## Шаг 2 (Android): Настройка уведомлений сервера Google Play

Для получения данных о доходах от покупок в приложении и подписок из Google Play, выберите один из следующих вариантов:

* (Рекомендовано) Google Play отправляет уведомления непосредственно в AppsFlyer. С этой опцией копии уведомлений не могут быть пересланы на вашу конечную точку. Если вы хотите выбрать этот вариант, см. [Отправка уведомлений Google Play непосредственно в AppsFlyer](#21-send-google-play-notifications-directly-to-appsflyer).
* Google Play сначала отправляет уведомления вам, а затем они пересылаются в AppsFlyer. Если вы выберете этот вариант, смотрите [Перенаправление уведомлений Google Play в AppsFlyer.](#22--optional--forward-google-play-notifications-to-appsflyer)

**Предварительные условия**: доступ к Google Play Console и пользовательскому интерфейсу AppsFlyer.

<div id="21-send-google-play-notifications-directly-to-appsflyer" />

<Accordion title="2.1 Отправка уведомлений Google Play непосредственно в AppsFlyer">

1. В AppsFlyer на шаге 2,**Set up Google Play server notifications**, выберите **Allow AppsFlyer topic to get RTDN messages directly from Google**.
2. Скопируйте тему AppsFlyer в буфер обмена.
3. В **Google Play Console** > **Главная**, выберите приложение для просмотра. Откроется дэшборд.

   [![](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)](https://files.readme.io/1fdd2632aaf3a412987aa5dae5ad5a7350836f1ad4cd2f1c228b4cc96acdb9ff-42158608097297.png)
4. Перейдите в **Monetize with Play** > **Monetization setup**, и в **Google Play Billing** разделе убедитесь, что **Enable real-time notification** отмечено.

   [![](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)](https://files.readme.io/f133ffefac1ec4b4eb9225c498f475163a69d1fd1f61b3d1c7cee7a71c42fea4-42158637562769.png)
5. В поле **Название темы** вставьте адрес темы AppsFlyer, который вы скопировали.

   [![](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)](https://files.readme.io/b6ac3a569210b026096b5592a575500b1bdb03376ec0641f4ceeaf9402ea4549-42158608104081.png)
6. Для **Содержания уведомлений** выберите **Подписки, аннулированные покупки и все одноразовые продукты**.

   [![](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)](https://files.readme.io/8aa48cebc2f0712204d5d5c2e45727879814aaae2d03732228e0f8e607fccdc9-42158608105233.png)
7. Нажмите **Save changes**. Чтобы изменения вступили в силу, может потребоваться время (иногда вплоть до 24 часов). Поэтому не спешите проводить тестирование.

</Accordion>

<div id="22--optional--forward-google-play-notifications-to-appsflyer" />

<Accordion title="2.2. [Необязательно] Перенаправление уведомлений Google Play в AppsFlyer">

**Примечание**: этот шаг предназначен только для тех случаев, когда вы не выбрали рекомендуемый способ получения данных о доходах от покупок в приложении и подписок от Google Play, отправляя уведомления напрямую в AppsFlyer. Если вы выполнили всё необходимое для выбора рекомендуемого метода и создали тему, в которой AppsFlyer напрямую получает RTDN-уведомления от Google Play, пропустите этот шаг.

Если вы хотите добавить AppsFlyer в качестве подписчика на существующий топик PUB/SUB, следуйте приведенным ниже инструкциям.

**Предварительные условия**: доступ к Google Cloud Platform и пользовательскому интерфейсу AppsFlyer.

**Чтобы перенаправлять уведомления Google Play в AppsFlyer**:

1. В AppsFlyer в боковом меню перейдите в **Settings** > **Revenue Settings**,
2. Выберите своё приложение.
3. На вкладке **Purchases & subscriptions** выберите **Forward your RTDN topic messages to AppsFlyer**.
4. Скопируйте URL конечной точки в буфер обмена.
5. В Google Cloud Platform в вашем проекте найдите **Pub/Sub**.

   [![](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)](https://files.readme.io/fc99b942cec1dc7c1442b6d85142be12011a0b91ab40110e6d454b8b12faa5cb-42158637570705.png)
6. В **Pub/Sub** перейдите в **Topics** раздел и убедитесь, что у вас есть специальная тема pub/sub для подписок.

   [![](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)](https://files.readme.io/6ae2654906ba62cac901b0d8a0b54d86ea92690e947621a578b93fc7225f550e-42158608108689.png)
7. В **Pub/Sub,** перейдите в **Subscriptions** раздел и нажмите **Create Subscriptions**.

   [![](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)](https://files.readme.io/d89659f6789cc4fd3c1888742583dc6e0aa2c8ad15229d11a8618251152864f4-42158637572369.png)
8. Введите **идентификатор ID подписки**.

   [![](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)](https://files.readme.io/1d4e42829a45c30253f68a164780185eb1b5723605870b7cc14450c80689f7bc-42158637574673.png)
9. Выберите соответствующую тему pub/sub подписки из раскрывающегося списка.

   [![](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)](https://files.readme.io/b2a3f816734039821830cd6f2bf8047cb1927a27e232f1caf5757310815ee0b3-42158637581329.png)
10. Для **Типа доставки** выберите **Push**.

    [![](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)](https://files.readme.io/cb716ee0392cf71b20e3aac9af4c050e9495a0e5c384594eb1af3d3fb5da454c-42158637584657.png)
11. Вставьте **URL-адрес конечной точки** который вы скопировали из AppsFlyer.

    [![](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)](https://files.readme.io/11610d67b24ea1b5afb6560c30352ec3e0bbfc5b8ebb2bf27545d838f7c999aa-42158637585681.png)
12. В разделе **Expiration period** выберите **Never expire**.

    [![](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)](https://files.readme.io/ab7d994b97137d39f77ffb11d772b37dc9033550bdb7ba95d3c9c2ff748cb54a-42158608120209.png)
13. Нажмите **Создать**.

    [![](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)](https://files.readme.io/bf8aed929c5f35847dda934677fc333ef111dc1f1281494582f1da4b776499c8-42158637592721.png)
14. Перейдите в раздел **Подписки** и нажмите на название нужной темы.

    [![](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)](https://files.readme.io/4b5f7b0c369fc4abddfbec35887a62221a55d838672872091b634343691dd9b8-42158608126993.png)
15. Скопируйте название темы в буфер обмена.

    [![](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)](https://files.readme.io/3ec5abc49588477d0567a26a3f6734f5e9c0ab0f677cfee0cf4d413aab0fcc5d-42158608127505.png)
16. В **Google Play Console** перейдите в **Monetize with Play** > **Monetization setup.** и в разделе **Google Play Billing** вставьте в поле Topic name название темы, которое вы скопировали на предыдущем шаге.

    [![](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)](https://files.readme.io/d5368f4c9326e5c0a9d0f75167bd12ee1ddb58381379ceefedeaae3917806163-42158608128785.png)
17. Для **Notification content**, выберите **Subscriptions, voided purchases, and all one-time products**.

    [![](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)](https://files.readme.io/6c1b473ee54c1db69e7359d99a86efee359113ed76d52d2cd2dfe05557f7ee91-42158637598737.png)
18. Нажмите **Сохранить изменения**. Чтобы изменения вступили в силу, может потребоваться время (иногда вплоть до 24 часов). Поэтому не спешите проводить тестирование.

</Accordion>

<div id="23-send-a-test-notification-from-google-play-console" />

<Accordion title="2.3 Отправка тестового уведомления из Google Play Console">

Чтобы проверить, что AppsFlyer корректно получает уведомления разработчика Google Play в реальном времени (RTDN), отправьте тестовое уведомление из Google Play Console:

1. Нажмите **Send test notification**. При этом в тему Pub/Sub, настроенную для AppsFlyer, отправляется тестовое сообщение RTDN.

   <Image alt="image (33).png" src="https://files.readme.io/4d7aa79eb963373223cfde1d32db16b739119a86d8d4f0cf6ce026d42a709bf3-42170040528657.png" width="1444px" />
2. В разделе **Google Play Billing** найдите раздел Topic name.
3. В меню слева перейдите в **Monetise with Play** → **Monetisation setup**.
4. Перейдите в Google Play Console.

<div id="24-confirm-notification-delivery-in-appsflyer" />

<Accordion title="2.4 Подтверждение доставки уведомлений в AppsFlyer">

1. Если тест выполнен успешно или вы готовы продолжить, нажмите **Save and next**.
2. Результат: AppsFlyer показывает, были ли получены какие-либо уведомления за последние 7 дней.
   * Если проверка прошла успешно, в интерфейсе отображаются дата и время самого последнего уведомления.
   * Если уведомления не были получены, интерфейс указывает, что за последние 7 дней уведомления не найдены.
   * Если статус не отображается, проверьте конфигурацию Pub/Sub и повторно отправьте тестовое уведомление.
3. На шаге **Google Play Server Notifications** нажмите **Test integration**.

</Accordion>

</Accordion>

<div id="step-3-implement-sdk-connector" />

## Шаг 3: Реализация коннектора SDK

В этом шаге вы подготовите своих разработчиков к интеграции коннектора SDK для покупок от AppsFlyer и настройке тестовой среды для тестирования.

Чтобы реализовать коннектор SDK, выполните следующие шаги:

1. На шаге **Implement SDK Connector** скопируйте **готовое сообщение** отображаемое на дэшборде.
2. Отправьте его своим разработчикам. Оно включает в себя:
   * название и идентификатор приложения;
   * Ссылка на <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">руководство по интеграции SDK</Anchor>.
   * Инструкции по настройке тестовой среды (`sandbox = true`)
   * Этапы тестирования (с использованием **TestFlight**)

Это сообщение содержит всю информацию, необходимую вашим разработчикам для завершения интеграции и начала тестирования.

<div id="note-3" />

> 📘 **Примечание:**
>
> Коннектор использует автоматическое обнаружение транзакций. В качестве альтернативы можно реализовать метод SDK `validateAndLog`, чтобы вручную регистрировать каждую транзакцию. Этот метод поддерживает не все функции, доступные при использовании коннектора. Подробнее о двух вариантах интеграции SDK см. в <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-and-subscription-validation">документации DevHub</Anchor>.

<div id="step-4-verify-sdk-implementation" />

## Шаг 4. Проверка реализации SDK

Протестируйте интеграцию дохода от покупок в приложении и подписок в среде песочницы, чтобы убедиться, что коннектор SDK интегрирован правильно, а уведомления сервера корректно настроены и получены AppsFlyer.

<div id="test-sdk-implementation" />

<Accordion title="Тестирование реализации SDK">

Чтобы проверить, получила ли AppsFlyer действительные полезные нагрузки событий покупок и подписок из вашего приложения за последние 7 дней, выполните следующие шаги:

1. На шаге **Проверка реализации SDK** нажмите **Тест реализации SDK**.
2. Просмотрите результаты, включая временную метку самой последней полезной нагрузки, полученной AppsFlyer.

   <div id="note-4" />

   > 📘 **Примечание:**
   >
   > Этот тест только подтверждает, что запросы доходят до AppsFlyer, и не проверяет полноту или корректность данных.

3. Чтобы полностью проверить реализацию, выполните приведенные ниже шаги тестирования.

</Accordion>

<div id="sandbox-events-and-parameters" />

<Accordion title="События и параметры песочницы">

* Коннектор SDK генерирует события только для начальной транзакции в песочнице:
  * Покупка в приложении: `af_purchase_sandbox_sdk`
  * Подписка: `af_ars_sandbox_sdk`
* AppsFlyer обрабатывает уведомления сервера, только если было зафиксировано событие SDK для исходной транзакции.
  * Покупка в приложении S2S: `af_purchase_sandbox_s2s`
  * Подписка S2S: `af_ars_sandbox_s2s`
* Если SDK никогда не регистрирует исходную транзакцию. S2S-событие не создается.

**Особенности iOS**

* Если `af_purchase_sandbox_sdk` включает `af_sandbox_revenue`, оно сопоставляется с production-событием `af_purchase`.
* Если доход отсутствует, оно сопоставляется с production-событием `af_purchase_free`.

**Особенности Android**

* Покупки, совершенные **лицензированными тестировщиками**, всегда генерируют события песочницы. даже если режим песочницы не настроен в SDK.

**Обязательные параметры для тестовых событий**

Убедитесь, что каждое событие покупки в песочнице включает:

* **Доход = 0** (чтобы не повлиять на реальные отчеты).
* `af_sandbox_revenue` = фактическая цена продукта (чтобы корректный доход был атрибутирован).
* `af_validated` **= true**. Если `false`, вернитесь назад и проверьте ключ магазина.
* `af_validation_type` = `receipt_validation`.

</Accordion>

<div id="test-inapp-purchase-and-subscription-revenue" />

<Accordion title="Тестирование измерения доходов от внутренних покупок (IAP) и подписок">

**Необходимые условия**:

* Для iOS убедитесь, что в App Store Connect в разделе App Store Server Notifications эндпоинт AppsFlyer указан в качестве **Sandbox Server URL**.

  [![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

**Чтобы протестировать доход от покупок в приложении и подписок**:

1. Скажите разработчикам, чтобы они следовали инструкциям<Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-android-purchase-connector#-testing-the-integration">Android</Anchor>, <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-apple-purchase-connector#-testing-the-implementation-in-sandbox">iOS</Anchor> и <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-purchase-connector/blob/master/docs/purchaseConnectorUnity.md#testing-the-implementation-in-sandbox">Unity</Anchor> , чтобы настроить среду песочницы в коннекторе SDK.
2. Сделайте тестовые покупки или оформите подписку с помощью <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">Тестировщика лицензий в Google Play</Anchor>. Для iOS используйте <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight</Anchor>. **Примечание**: продукт подписки можно протестировать только один раз на устройстве. На практике устройство не может зарегистрировать несколько тестовых покупок одной и той же подписки. Дополнительные попытки не будут зарегистрированы.
3. Выполните тестовый возврат средств, продление или отмену подписки с помощью <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6062777?hl=en">тестировщика лицензий в Google Play</Anchor> и <Anchor target="_blank" href="https://developer.apple.com/testflight/">TestFlight в iOS</Anchor>. **Примечание**. Если вы тестируете подписку, подождите, пока AppsFlyer получит серверное уведомление от магазина. Обычно оно поступает в течение нескольких минут после первоначальной покупки.
4. На шаге **Проверка реализации коннектора SDK** нажмите **Проверить реализацию SDK**. Показывает, были ли за последние 7 дней успешно получены какие-либо полезные данные SDK от Purchase Connector.
5. Убедитесь, что тестовые события отображаются одним из следующих способов:

   * Просмотрите событие в <Anchor target="_blank" href="/marketers/ru/docs/testing-the-sdk-integration-for-marketers#view-live-events">Просмотре события в реальном времени</Anchor>.

   * Просмотрите данные события в <Anchor target="_blank" href="/marketers/ru/docs/activity-metrics-in-my-dashboards">Мои дэшборды - Обзор активности</Anchor>.
6. Убедитесь, что событие отображается на дэшборде активности AppsFlyer. В AppsFlyer перейдите в раздел **Анализ > Активность**, затем на графике **Динамика активности** откройте вкладку «События в приложении» и выберите событие для тестирования. Покупка подписки с автоматическим продлением называется `af_ars_s2s_sandbox`. Мероприятие включает в себя:
   * Значение дохода равно 0 (чтобы не искажать реальные отчеты AppsFlyer).
   * Параметр `af_sandbox_revenue`, который содержит значение дохода от купленного продукта, обеспечивая корректную отчетность по доходу.

</Accordion>

<div id="step-5-verify-and-update-settings" />

## Шаг 5: Проверьте и обновите настройки

После завершения настройки указанных выше параметров и сохранения последнего шага вы будете перенаправлены в представление активной конфигурации, где сможете проверить или обновить следующие настройки:

1. Убедитесь, что переключатель **Проверять покупки через App Store** включен.
2. Проверьте следующие варианты в разделе **Покупки**:
   * **Предотвращать дублирование покупок для чистоты данных**: предотвращает запись транзакций, о которых уже сообщалось в отчетности.
   * **Автоматически измерять возвраты, отмены и отрицательный доход**: измеряет события, связанные с возвратами, и регистрирует их как отрицательный доход.
   * **Избегать двойного учета дохода от Family Sharing**: предотвращает дублирование дохода от Family Sharing. Эти события помечаются значением `purchase_ownership_type=FAMILY_SHARED` и сообщают о нулевом доходе.
3. Убедитесь, что переключатель **Измерять и атрибутировать доход для автоматически продлеваемых подписок** включен:
4. Статус следующих настроек:
   * Настройка **ключа App Store**
   * Настройка **конечной точки уведомлений сервера** setup
   * Внедрение & тестирование коннектора SDK

<div id="step-6-release-the-app-versions-with-the-sdk-connector" />

## Шаг 6: Выпустите версии приложения с коннектором SDK

После того, как все предыдущие шаги настроены, а коннектор SDK от AppsFlyer для измерения дохода от покупок интегрирован в приложение, вашему разработчику необходимо выпустить версию приложения с интегрированным коннектором SDK.

Однако, прежде чем разработчик выпустит новую версию приложения, убедитесь, что:

* Внутренние события приложения, которые вы хотите регистрировать как покупки в приложении или подписки, не блокируются одним из правил проверки, которые вы настроили в AppsFlyer.
* Ваш разработчик должен отметить все флажки безопасной среды как false.

[![](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)](https://files.readme.io/eda1b7d22391e763dc6e6e4bf7e0046f39bb6ebff815b93721601a96fc3d7e42-42138012409105.png)

После релиза приложения с коннектором SDK будут генерироваться <Anchor target="_blank" href="/marketers/ru/docs/about-roi360-store-revenue#iaprelated-events-and-parameters">события покупок в приложении</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/about-roi360-store-revenue#subscriptionrelated-events-and-parameters">события подписок</Anchor> и будут доступны на всех дэшбордах AppsFlyer, а также в агрегированных отчетах и отчетах о сырых данных, включая <Anchor target="_blank" href="/marketers/ru/docs/revenue-etl-reports">Revenue ETL</Anchor>.

**Примечание:** События будут генерироваться только для пользователей, которые обновились до версии приложения, включающей коннектор SDK. В результате до полного перехода на обновленную версию приложения ожидается расхождение между данными о доходе из приложения и данными магазина.

<div id="switch-to-roi360-store-revenue-from-receipt-validation" />

## Переход на ROI360 Store revenue (с валидации чека)

Если вы завершили онбординг для валидации чека, но хотите активировать продукт ROI360 Store revenue, выполните следующие действия:

1. В AppsFlyer в боковом меню откройте [<Image alt="" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.54%" />](https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png) **Настройки** и в разделе **ROI360** выберите **Настройки дохода**.
2. Откройте вкладку **Покупки и подписки**. Появится баннер о том, что ROI360 доступен, но не активен.
3. Нажмите **Просмотреть сравнение продуктов**, чтобы понять преимущества, включая атрибуцию возвратов, отчетность по чистому доходу и измерение полного жизненного цикла подписки.
4. Кликните **Активировать ROI360.**
5. Выполните шаг **Включить уведомления сервера магазина приложений**. Дополнительные сведения см. в разделе [Настройка серверных уведомлений App Store](#шаг-2-ios-настройка-уведомлений-сервера-app-store) или [Настройка серверных уведомлений Google Play](#шаг-2-android-настройка-уведомлений-сервера-google-play).
6. В разделе **Purchases & subscriptions** убедитесь, что параметр **Тип продукта** теперь установлен на **ROI360**.
7. Проверьте текущую настройку SDK, чтобы убедиться, что она поддерживает необходимую вам функцию учета дохода ROI360 Store.

<div id="note-5" />

> 📘 **Примечание:**
>
> Функция учета дохода ROI360 Store поддерживает два метода интеграции: Purchase SDK connector и Validate and Log. Из этих двух вариантов мы рекомендуем использовать **Purchase SDK Connector**, чтобы получить следующие преимущества:
>
> * Автоматическое обнаружение транзакций
> * Измерение дохода от существующих подписчиков (пользователей, оформивших подписку до интеграции)
> * Поддержка изменений цены подписки, обеспечивающая точную отчетность по доходу при обновлении цен.
>
> Если эти возможности вам не нужны, вы можете продолжить использовать интеграцию **Validate and Log**.
>
> **Как проверить метод интеграции SDK**
>
> Чтобы подтвердить, использует ли ваше приложение Purchase SDK Connector или Validate and Log:
>
> 1. Перейдите к шагу **Integrate SDK Connector**.
> 2. Нажмите **Test SDK integration**. Вы увидите, когда AppsFlyer получил последний payload SDK за последние 7 дней и поступил ли он из **Purchase SDK Connector** или **Validate and Log**.

<div data-zendesk-anchors="h_01KSAG4Y3BP0NWYNCX3AJG47JR=%D0%B4%D0%B2%D0%BE%D0%B5%D1%82%D0%BE%D1%87%D0%B8%D0%B5- overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01KD31QE0BCW0BX9BNNDK6DJRA=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 h_01KD31QE0BQAQ0CS1FJ46TV6K1=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 step-1-ios-set-up-app-store-connect-keys=%D1%88%D0%B0%D0%B3-1-ios-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%B9-app-store-connect h_01KD31QE0BE3ST0TV3KQ1M5AB0=%D1%88%D0%B0%D0%B3-1-ios-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%B9-app-store-connect h_01KD31QE0BBYES1C2Y1MB665EF=11-create-the-app-store-connect-keys h_01KD31QE0B4G0NGRYBTS2TRZQR=12-set-the-app-store-connect-key-in-appsflyer step-1-android-set-up-service-account-key-and-permissions=step-1-android-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0-%D0%B8-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9 h_01KD31QE0BVQNJZ8PKKYKK9Q79=step-1-android-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0-%D0%B8-%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B9 h_01KD31QE0BP21EHP5RPBZ5PX2N=11-link-your-google-play-developer-account-to-your-google-cloud-project h_01KD31QE0B5G8SDGZQ8NE07QAE=12-configure-your-service-account-in-the-google-cloud-platform h_01KD31QE0CBMGHXJTXT4JPBV70=13-set-api-access-permissions-in-google-play-console h_01KD31QE0CH5M5X9M9G68N2PPZ=14-upload-the-service-account-private-key-to-appsflyer step-2-ios-set-up-app-store-server-notifications=%D1%88%D0%B0%D0%B3-2-ios-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0-app-store h_01KD31QE0CZAJ7SH2EECDJ11YN=%D1%88%D0%B0%D0%B3-2-ios-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0-app-store option-1-recommended-appsflyer-as-the-primary-endpoint=%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-1-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D1%82%D1%81%D1%8F--appsflyer-%D0%BA%D0%B0%D0%BA-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D0%BE%D0%B9-endpoint h_01KW7HDDAQEHGY33SQ2AHWVJAC=%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-1-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D1%82%D1%81%D1%8F--appsflyer-%D0%BA%D0%B0%D0%BA-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D0%BE%D0%B9-endpoint option-2-your-endpoint-as-the-primary-endpoint=%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-2--%D0%B2%D0%B0%D1%88%D0%B0-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D0%B0%D1%8F-%D1%82%D0%BE%D1%87%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BA-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D0%B0%D1%8F h_01KW7HDDAQK8Z279CEG7N33FKT=%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82-2--%D0%B2%D0%B0%D1%88%D0%B0-%D0%BA%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D0%B0%D1%8F-%D1%82%D0%BE%D1%87%D0%BA%D0%B0-%D0%BA%D0%B0%D0%BA-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%BD%D0%B0%D1%8F h_01_roi360_notification_types=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01KD31QE0C9YFBM01GGE2PZDNR=21-copy-the-appsflyer-server-notifications-endpoint h_01KD31QE0C4MRYPMMQ31BRAYS7=22-send-notifications-directly-to-appsflyer 23-%5Boptional%5D-forward-notifications-from-your-endpoint-to-appsflyer=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0CWXTKDND5F4Q34J7G=23--optional--forward-notifications-from-your-endpoint-to-appsflyer h_01KD31QE0C2QWHBJ8AWMEMP2SD=24-test-the-server-notifications-integration h_01KD31QE0CA26Y430AMK474NTC=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 step-2-android-set-up-google-play-server-notifications=%D1%88%D0%B0%D0%B3-2-android-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0-google-play h_01KD31QE0CKP0PTBQ4XCT9NDE1=%D1%88%D0%B0%D0%B3-2-android-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%83%D0%B2%D0%B5%D0%B4%D0%BE%D0%BC%D0%BB%D0%B5%D0%BD%D0%B8%D0%B9-%D1%81%D0%B5%D1%80%D0%B2%D0%B5%D1%80%D0%B0-google-play h_01KD31QE0C1RYXW6ADHMQJ3908=21-send-google-play-notifications-directly-to-appsflyer 22-%5Boptional%5D-forward-google-play-notifications-to-appsflyer=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CFVEBJV3E93Z5RDAP=22--optional--forward-google-play-notifications-to-appsflyer h_01KD31QE0CTFNTY52F0C9D3RY2=23-send-a-test-notification-from-google-play-console h_01KD31QE0CV17JMVVB7ZPT1G8W=24-confirm-notification-delivery-in-appsflyer step-3-implement-sdk-connector=%D1%88%D0%B0%D0%B3-3-%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D0%BD%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D0%B0-sdk h_01KD31QE0CPK1EYVT0BSYTTZFM=%D1%88%D0%B0%D0%B3-3-%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%BA%D0%BE%D0%BD%D0%BD%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D0%B0-sdk h_01KD31QE0C65DQ59ZKG8V886JW=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-3 step-4-verify-sdk-implementation=%D1%88%D0%B0%D0%B3-4-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-sdk h_01KD31QE0C9KGGFVQR6HYR5AYM=%D1%88%D0%B0%D0%B3-4-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-sdk h_01KD31QE0C0VKWF5EBBR761C1J=test-sdk-implementation h_01KD31QE0C7RN657P9KPFV5725=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-4 h_01KD31QE0D0CR02260J5K8V8QX=sandbox-events-and-parameters h_01KD31QE0DNEBYXH4672363WYM=test-inapp-purchase-and-subscription-revenue step-5-verify-and-update-settings=%D1%88%D0%B0%D0%B3-5-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%B8-%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01KD31QE0DQP78QG5HRSERR5S9=%D1%88%D0%B0%D0%B3-5-%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D1%8C%D1%82%D0%B5-%D0%B8-%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%B8%D1%82%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 step-6-release-the-app-versions-with-the-sdk-connector=%D1%88%D0%B0%D0%B3-6-%D0%B2%D1%8B%D0%BF%D1%83%D1%81%D1%82%D0%B8%D1%82%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81-%D0%BA%D0%BE%D0%BD%D0%BD%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D0%BE%D0%BC-sdk h_01KD31QE0D3HX2DEH7FQ1JR4MS=%D1%88%D0%B0%D0%B3-6-%D0%B2%D1%8B%D0%BF%D1%83%D1%81%D1%82%D0%B8%D1%82%D0%B5-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81-%D0%BA%D0%BE%D0%BD%D0%BD%D0%B5%D0%BA%D1%82%D0%BE%D1%80%D0%BE%D0%BC-sdk switch-to-roi360-store-revenue-from-receipt-validation=%D0%BF%D0%B5%D1%80%D0%B5%D1%85%D0%BE%D0%B4-%D0%BD%D0%B0-roi360-store-revenue-%D1%81-%D0%B2%D0%B0%D0%BB%D0%B8%D0%B4%D0%B0%D1%86%D0%B8%D0%B8-%D1%87%D0%B5%D0%BA%D0%B0 h_01KD31QE0DJNJ8T5XSZFCACMQF=%D0%BF%D0%B5%D1%80%D0%B5%D1%85%D0%BE%D0%B4-%D0%BD%D0%B0-roi360-store-revenue-%D1%81-%D0%B2%D0%B0%D0%BB%D0%B8%D0%B4%D0%B0%D1%86%D0%B8%D0%B8-%D1%87%D0%B5%D0%BA%D0%B0 h_01KD31QE0DX0VDXKHDZTWTYHHX=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-5" />

---
title: Настройка SSO AppsFlyer в OneLogin
metadata:
  keywords:
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2023-05-04T07:41:06Z'
  edited_at: '2026-10-19T14:12:52Z'
  id: 15044997313041
  locale: ru
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ru/articles/15044997313041
---
> **Кратко:** Настройте процесс SSO, используя OneLogin в качестве поставщика удостоверений (IdP).

Первый этап настройки процесса SSO AppsFlyer выполняется на платформе OneLogin. Выполните следующие действия:

<div id="create-the-appsflyer-app-in-oonelogin" />

<Accordion title="Создайте приложение AppsFlyer в OneLogin">

**Предварительное условие:** Учетная запись OneLogin с правами администратора.

1. В консоли администратора OneLogin перейдите в **Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**.
2. В правом верхнем углу нажмите **Add App**.
3. Найдите и выберите **SAML Custom Connector (Advanced)**.  

   <Image align="center" alt="onelogin_saml_app.png" src="https://files.readme.io/c1e5ec122e21f05e860486ad280ba9e692b3d05b05105d9c1ca700b8921ee6ab-15045173609745.png" width="601px" />
4. В поле **Display Name** введите имя, которое будет отображаться в списке приложений плагина OneLogin.
5. [Необязательно] **App logo**: добавьте логотип, который будет отображаться рядом с названием приложения.
6. [Необязательно] Добавьте описание.
7. Нажмите **Save** (Сохранить). Вверху появится сообщение об успешном выполнении.
8. Перейдите на вкладку **Configuration** в боковом меню.
9. Настройте интеграцию в соответствии со следующими полями:
   * **Audience (EntityID):** Введите эту ссылку: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com</Anchor>
   * **ACS (Consumer) URL Validation**, **ACS (Consumer) URL:** Введите конечную точку, на которую OneLogin отправляет данные проверки пользователя. Используйте ссылку в соответствии с <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">описанной здесь конфигурацией URL-адреса обратного вызова</Anchor>
   * **Получатель:** Введите тот же URL-адрес, который указан в поле **ACS (Consumer) URL** .
   * **URL-адрес входа:** Введите URL-адрес входа AppsFlyer <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">login URL</Anchor>.
   * **SAML not valid before**, **SAML not valid on or after:** Укажите период времени (в минутах), в течение которого утверждение действительно.
   * **SAML initiator:** <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">Выберите, откуда начинается аутентификация</Anchor>:
     * Если аутентификация начинается со стороны IdP, выберите **OneLogin**
     * Если аутентификация начинается со стороны AppsFlyer, выберите **Service Provider**
   * **SAML nameID format:** Выберите Email.
   * **Тип издателя SAML:** Выберите Specific.
   * **Элемент подписи SAML:** Выберите **Both**.
   * **Шифровать утверждение**: установите этот флажок.
   * **Метод шифрования SAML:** Выберите **AES-256-CBC**.
10. Нажмите **Save** (Сохранить).
11. **Шифрование утверждения:** 
    1. Откройте <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">URL-адрес метаданных SSO</Anchor> и скопируйте значение сертификата шифрования.
    2. Вернитесь на вкладку **Configuration** и вставьте его в текстовое поле **SAML encryption**.
    3. Нажмите **Save** (Сохранить).

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Получение метаданных SSO IdP">

1. В выбранном приложении (**Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**), выберите **SSO** в боковом меню.
2. Скопируйте **URL-адрес Issuer** и вставьте его в новую вкладку, чтобы загрузить метаданные SSO.

</Accordion>

<div id="create-onelogin-users" />

<Accordion title="Создание пользователей OneLogin">

1. В верхнем меню перейдите в **Users** > <Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/users">**Users**</Anchor>.
2. Нажмите **New User** в правом верхнем углу.
3. Введите **First name**, **Last name** и **Email** пользователя.
4. В правом верхнем углу нажмите **Save User**, затем **More Actions** и выберите **Change Password**, чтобы задать пароль для пользователя.
5. Задайте пароль для пользователя и нажмите **Update**.

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="Назначение пользователей вашему приложению">

1. Перейдите на вкладку **Application** в боковом меню выбранного пользователя.
2. Нажмите значок + рядом с **Applications**.
3. Выберите созданное вами приложение AppsFlyer и нажмите **Continue**.  

   <Image align="center" alt="onelogin_assign_app.png" src="https://files.readme.io/a1769673f3f167f728a00fb1cccb951bd246798fd7327c51b021f73987bc8fb2-15552909316241.png" width="326px" />
4. В верхнем меню перейдите в **Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**.
5. Выберите приложение, которое вы только что создали.
6. Нажмите **Save** (Сохранить).

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Завершите процесс в AppsFlyer">

Теперь, когда вы настроили часть IdP, вернитесь в AppsFlyer, чтобы <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">завершить настройку</Anchor>. Затем вы можете <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">провести тест</Anchor> , чтобы убедиться, что всё работает.

</Accordion>

<div data-zendesk-anchors="h_01HF690GVE4FXXTMC5QWSJTY3C=create-the-appsflyer-app-in-oonelogin h_01HF690GVECMCVQAJFZ509MD50=get-idp-sso-metadata h_01HF690GVEKMV3TZ8MAD4HM635=create-onelogin-users h_01HF690GVEVEQ4GNJGXHKF5VT1=assign-users-to-your-app h_01HF690GVEWYEGR2Z9F22FQHGE=complete-the-process-in-appsflyer" />

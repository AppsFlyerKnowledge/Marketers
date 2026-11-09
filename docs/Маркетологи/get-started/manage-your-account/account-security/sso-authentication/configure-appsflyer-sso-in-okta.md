---
title: Настройка SSO AppsFlyer в Okta
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
  created_at: '2023-02-12T13:10:51Z'
  edited_at: '2026-08-28T00:15:44Z'
  id: 12934808889745
  locale: ru
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ru/articles/12934808889745
---
> **Кратко:** Настройте процесс SSO, используя Okta в качестве поставщика удостоверений (IdP).

Первый шаг настройки процесса SSO AppsFlyer выполняется на платформе Okta. Выполните следующие действия:

<div id="create-the-appsflyer-app-in-okta" />

<Accordion title="Создайте приложение AppsFlyer в Okta">

**Необходимое условие:** учетная запись Okta с правами администратора.

1. В Admin Console перейдите в **Applications** > **Applications**.  
   <Image align="center" alt="Okta_side_menu___applications.png" src="https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png" width="241px" />
2. Нажмите **Create App Integration**.
3. В диалоговом окне **Create a new app integration** выберите **SAML 2** и нажмите **Next**.
4. В разделе **(1) General Settings** в поле **App name** введите имя, которое должно отображаться в списке приложений плагина Okta.  
   <Image align="center" alt="Okta_app_name_and_icon__1_.png" src="https://files.readme.io/6998e7737b0aa5c4d70ad97ab41e17e471ddaf060e78c44fa2de41be1df17574-13572380565521.png" width="639px" />
5. [Необязательно] **App logo**: добавьте логотип, который будет отображаться рядом с названием приложения.
6. Создайте информативное название для эксперимента, затем нажмите **Далее**.
7. В разделе **(2) Configure SAML Integration** настройте интеграцию в соответствии со следующими полями: ![okta-create-saml-integration.png](https://files.readme.io/6c276dd54afd30e828b989fc6796de5eca46282ade015e7a34e0bd1cc95d7fb8-16870970396177.png)
   * **Single sign-on URL:** введите конечную точку, на которую Okta отправляет данные для проверки пользователя. Используйте ссылку согласно <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">описанной здесь конфигурации callback URL-адреса</Anchor>
   * **Audience URI (SP Entity ID):** введите эту ссылку: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com</Anchor>
   * **Name ID format:** выберите **EmailAddress** в качестве формата для идентификации пользователя
   * **Application username:** выберите **Okta username**  
     **Примечание:** адрес электронной почты пользователя Okta должен совпадать с адресом электронной почты учетной записи AppsFlyer этого пользователя
8. Нажмите **Show Advanced Settings** и настройте интеграцию в соответствии с полями, показанными на изображении ниже:

   <Image align="center" alt="Okta_расширенные_настройки__1_.png" src="https://files.readme.io/9a3461f700cc50a54237578a304206ed7693e30cdd516398089954321cd44af4-13572576788241.png" width="640px" />

   * **Assertion Encryption:** выберите **Encrypted** или **Unencrypted**.   
     **Примечание:** поскольку утверждения контролируются вашим IdP, рекомендуется выбрать **Encrypted**.
   * **Encryption certificate:** загрузите <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url">сертификат шифрования AppsFlyer</Anchor>. Этот сертификат подписан AppsFlyer и используется как для шифрования, так и для подписи запроса.
   * [Необязательно] **Signature certificate:** загрузите <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#the-authentication-certificate">сертификат подписи AppsFlyer</Anchor>.
9. Прокрутите страницу до конца и нажмите **Далее**.
10. Выберите **I’m an Okta customer adding an internal app** и нажмите **Finish**.

</Accordion>

<div id="create-okta-users" />

<Accordion title="Создание пользователей Okta">

Теперь, когда приложение Okta SAML создано, добавьте пользователей.

1. В консоли администратора выберите **Directory** > **People**.

   <Image align="center" alt="Okta___directory___people.png" src="https://files.readme.io/d9c5da8787fdb81bf97bc0753b2f7794cdc59060e5026348428545064d138d18-13572579297169.png" width="226px" />
2. Нажмите **Add Person**.

   <Image align="center" alt="Okta___People___Add_person.png" src="https://files.readme.io/6bb8b854cf000259970d63b9eacb28bf6d4079d648939814aaa0e456a96c9bbe-13572600647697.png" width="524px" />
3. В диалоговом окне **Add Person**:

   <Image align="center" alt="Okta_Add_person__1_.png" src="https://files.readme.io/d6d7e198fab965872b5a01302a00bdbd0bfb5d561af372fc4390c9882a22a42c-13572617052689.png" width="620px" />

   * В поле **User type** выберите **User**.
   * Заполните все обязательные поля: **First name**, **Last name**, **Username** (должен быть адресом электронной почты) и **Primary email**.
   * Для **Password** можно выбрать, кто будет его задавать: пользователь или администратор.
4. Чтобы продолжить добавлять пользователей, кликните **Сохранить и добавить еще**, затем повторите шаги 1–4. Когда добавите всех пользователей, нажмите **Save**.

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="Назначение пользователей вашему приложению">

1. В консоли администратора вернитесь в **Applications** > **Applications**.
2. В разделе **Browse App Catalog** выберите приложение, которое вы только что создали.  
   <Image align="center" alt="Okta_side_menu___applications.png" src="https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png" width="233px" />
3. В выбранном приложении на вкладке **Assignments** нажмите **Assign** > **Assign to People**.  
   <Image align="center" alt="Okta_sso_assign_to_people.png" src="https://files.readme.io/50930693a4a58ad8162b2ac81e476081c9b0288da4dab5b92bb41fece4aff586-14942267242769.png" />
4. Найдите пользователя, которого нужно назначить вашему приложению, и нажмите **Assign**.
5. Повторите этот шаг для всех пользователей.
6. Нажмите **Done**, когда закончите добавлять всех пользователей. Новые пользователи теперь отображаются в разделе **People**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Получить метаданные SSO IdP">

1. В консоли администратора вернитесь в раздел **Applications** > **Applications**.
2. В разделе **Browse App Catalog** выберите свое приложение.
3. Кликните вкладку **Sign On**.
4. В разделе **SAML Signing Certificates** кликните **Actions** > **View IdP metadata** для активного сертификата. <Image alt="okta_sso_view_idp_metadata.png" src="https://files.readme.io/a6d9f6753ead962713851bcc367abba6fad226d6e0a5f908055e44b1d3e1b2be-14942369009809.png" width="601px" />
5. Скопируйте URL-адрес из открывшейся вкладки. Этот URL-адрес вы используете на следующем шаге на платформе AppsFlyer.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Завершите процесс в AppsFlyer">

Теперь, когда вы настроили часть IdP, вернитесь в AppsFlyer, чтобы <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">завершить настройку</Anchor>. Затем можно <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">протестировать</Anchor> , чтобы убедиться, что это работает.

</Accordion>

<div id="see-also" />

> 📄 **Смотрите также**
>
> * <Anchor target="_blank" href="https://developer.okta.com/docs/guides/build-sso-integration/openidconnect/main/">Документация по SSO Okta</Anchor>

<div data-zendesk-anchors="h_01HDNZYDQGGBMB9MJ97RF4BADM=create-the-appsflyer-app-in-okta h_01HDNZYDQGGFCA2KB9PDQY1ZTG=create-okta-users h_01HDNZYDQGC9MRQH92MM8W4FVE=assign-users-to-your-app h_01HDNZYDQGWRE9K6XG5EPYTYYX=get-idp-sso-metadata h_01HDNZYDQG6GNEP3TQMXVT5FTG=complete-the-process-in-appsflyer h_01HDP00WTAVP0X8FT51JC1JKKC=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

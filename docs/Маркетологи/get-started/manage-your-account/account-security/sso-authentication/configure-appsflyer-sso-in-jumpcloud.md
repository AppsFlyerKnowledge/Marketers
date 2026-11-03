---
title: Настройка SSO AppsFlyer в JumpCloud
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
  created_at: '2023-03-08T07:39:41Z'
  edited_at: '2026-10-19T14:12:47Z'
  id: 13563131567249
  locale: ru
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ru/articles/13563131567249
---
> **Кратко:** Настройте процесс SSO, используя JumpCloud в качестве поставщика удостоверений (IdP).

Первый этап настройки процесса SSO AppsFlyer выполняется на платформе JumpCloud. Выполните следующие действия:

<div id="create-the-appsflyer-app-in-jumpcloud" />

<Accordion title="Создайте приложение AppsFlyer в JumpCloud">

**Предварительное условие:** Учетная запись JumpCloud с правами администратора.

1. В меню администратора JumpCloud перейдите в <Anchor target="_blank" href="https://console.jumpcloud.com/#/sso">SSO</Anchor> и нажмите **+ Add New Application**.
2. Найдите AppsFlyer в списке приложений и нажмите **configure**.
3. В разделе **New SSO** на вкладке **General Info** укажите имя приложения в поле **Display label** .
4. [Необязательно] Добавьте описание.
5. На вкладке **SSO**:
   1. **Upload Metadata:** Скачайте <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">метаданные SSO AppsFlyer</Anchor> в виде XML-файла, затем загрузите его здесь.
   2. **ACS URLs:** Введите URL-адрес обратного вызова в соответствии с <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">методом аутентификации ваших пользователей</Anchor>.
   3. **Login URL:** Введите <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">URL-адрес входа</Anchor> AppsFlyer.  

      <Image alt="jumpcloud_sso_tab2__1_.png" src="https://files.readme.io/3b45c98d191a35644c5479a0237e92908ca6f18416f6df2b6e0c84a30940307b-15934671100561.png" width="477px" />
6. Нажмите **activate**.
7. Будет создан общедоступный сертификат. Уведомление об этом появится в правом верхнем углу страницы. Нажмите **Download Certificate**. Этот сертификат потребуется на <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">шаге 2 на платформе AppsFlyer</Anchor>.

</Accordion>

<div id="create-jumpcloud-users" />

<Accordion title="Создайте пользователей JumpCloud">

1. В меню администратора JumpCloud перейдите в <Anchor target="_blank" href="https://console.jumpcloud.com/#/users">Users</Anchor> и нажмите значок + .
2. Выберите **Manual user entry**.  
   <Image alt="cloud_jump_manual_user_entry.png" src="https://files.readme.io/d00299979fa5e036c464c8c6d360965d46e42d5042a31366ced7adc84914c0be-14947838808081.png" width="417px" />
3. Заполните все обязательные поля: **Username**, **Company Email**, затем нажмите **save user**.
4. Настройте параметры пароля пользователя в соответствии с принятым в вашей компании методом.
5. Чтобы продолжить добавление пользователей, кликните **Save And Create Another**, затем повторите шаг 3. Закончив добавлять всех пользователей, кликните **Save**.

</Accordion>

<div id="create-jumpcloud-groups" />

<Accordion title="Создайте группы JumpCloud и назначьте их Приложению AppsFlyer">

Создайте группу и назначьте пользователей в неё:

1. В меню администратора JumpCloud перейдите в <Anchor target="_blank" href="https://console.jumpcloud.com/#/groups/user">User Groups</Anchor> и кликните значок +.
2. Введите имя группы.
3. На вкладке **Users** выберите пользователей, которых нужно добавить в эту группу.
4. На вкладке **Applications** выберите Приложение AppsFlyer, которое вы только что создали.
5. Кликните **save**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Получите метаданные IdP SSO">

1. В меню администратора JumpCloud перейдите в **SSO**.
2. Выберите Приложение AppsFlyer, которое вы только что настроили, и в правом верхнем углу кликните **Copy Metadata URL**. Вы вставите эту ссылку на следующем шаге.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Завершите процесс в AppsFlyer">

Теперь, когда вы настроили часть IdP, вернитесь в AppsFlyer, чтобы <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">завершить настройку</Anchor>. Затем вы можете <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">проверить</Anchor> — чтобы убедиться, что все работает.

</Accordion>

<div data-zendesk-anchors="h_01HF99ZFBKPYCP8228VKWPCRHX=create-the-appsflyer-app-in-jumpcloud h_01HF99ZFBKXD6HQE44FDQVQZWK=create-jumpcloud-users h_01HF99ZFBK0T9JQVFNTX705V9M=create-jumpcloud-groups h_01HF99ZFBKDFKTFXEE8Q0MH6SY=get-idp-sso-metadata h_01HF99ZFBK40ZTFKKJNXP4N294=complete-the-process-in-appsflyer" />

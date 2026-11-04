---
title: Настройка AppsFlyer SSO в Ping Identity
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - security
    - Marketers
    - authentication
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2023-06-11T09:28:10Z'
  edited_at: '2026-10-19T14:12:55Z'
  id: 16062655361937
  locale: ru
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ru/articles/16062655361937
---
> **Кратко:** Настройте процесс SSO, используя Ping Identity в качестве поставщика удостоверений (IdP).

Первый шаг настройки процесса SSO AppsFlyer выполняется на платформе Ping Identity. Выполните следующие действия:

<div id="create-the-appsflyer-app-in-ping" />

<Accordion title="Создайте приложение AppsFlyer в Ping Identity">

**Предварительное условие:** Учетная запись Ping Identity с правами администратора.

1. В меню администратора Ping Identity перейдите в **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** и нажмите +.
2. В открывшемся справа разделе:
   * Введите имя, которое должно отображаться в списке приложений в плагине Ping Identity.
   * Выберите SAML Application в качестве типа приложения.
3. Нажмите **Configure**. Откроется раздел SAML Configuration.
   * Для аутентификации, инициируемой поставщиком услуг (AppsFlyer), выберите **Import From URL**:
     * **Import URL:** <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">https://hq1.appsflyer.com/auth/sso-metadata</Anchor>
     * **ACS URLs:** Enter the following link using your AppsFlyer account ID:  
       <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">https://hq1.appsflyer.com/auth/sso-callback</Anchor>
     * **Entity ID:** Введите следующую ссылку: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>  

       <Image alt="ping" src="https://files.readme.io/8b265666f05bc4f6ab984151d7d73653b9ea5dcb837898d17e96bf9c392fe638-16063467179921.png" width="419px" />
   * Для аутентификации, инициируемой поставщиком удостоверений (IdP) Ping Identity, выберите **Manually Enter**:
     * **URL-адреса ACS:** Введите следующую ссылку, используя идентификатор вашей учетной записи AppsFlyer:   
       `https://hq1.appsflyer.com/auth/sso-callback/<Введите здесь идентификатор вашей учетной записи AppsFlyer>`
     * **Entity ID:** Введите следующую ссылку: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>
4. Нажмите **Save** (Сохранить).
5. На вкладке **Configuration**:
   1. Кликните **Download Metadata**.
   2. В правом верхнем углу нажмите значок редактирования и заполните поля ниже:  

      <Image alt="ping" src="https://files.readme.io/386fab01b9389d88ea0c4870ba2ea8e33d9ab6e27322059be5e46efbf248714b-16063435689233.png" width="487px" />

      * **КЛЮЧ ПОДПИСИ:**
        * Выберите **Sign Assertion & Response**.
        * **Алгоритм подписи:** выберите **RSA\_SHA256**.
      * **ШИФРОВАНИЕ:**
        * Выберите **Enable Encryption**.
        * АЛГОРИТМ: выберите **AES\_256**.
      * **СЕРТИФИКАТ:**
        * Выберите **Import** и загрузите <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url">сертификат шифрования AppsFlyer</Anchor>. Этот сертификат подписан AppsFlyer и используется как для шифрования, так и для подписи запроса.  
          **Примечание:** Вы можете загрузить сертификат AppsFlyer, подписанный Amazon. Обратитесь к своему CSM, чтобы получить этот сертификат.
        * Выберите **Enforced Signed Authn Request**.
6. Нажмите **Save** (Сохранить).
7. На вкладке **Attribute Mappings** нажмите значок редактирования и выберите **Email Address** в разделе **PingOne Mappings**.  

   <Image alt="ping-identity" src="https://files.readme.io/b93ac5463868c8f5f7760b60492a30f7ae59c52b766e76ef57fbe42e00f4bf2b-16292200523025.png" width="620px" />
8. Нажмите **Save** (Сохранить).

</Accordion>

<div id="create-ping-groups" />

<Accordion title="Создание групп Ping Identity">

Теперь, когда SAML-приложение Ping Identity создано, создайте группы пользователей, а затем добавьте в них пользователей.

1. В меню администратора Ping Identity перейдите в **Identity** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/group">Groups</Anchor>** и кликните +.  

   <Image alt="ping" src="https://files.readme.io/fcc2a3f035a285d96d7b7c3e83cfeed64e86cb0f0807e6acced75df89bd8dfc4-16292210866705.png" width="216px" />
2. В открывшейся справа панели введите название группы и кликните **Save**.
3. Повторите шаги 1–2 для всех групп пользователей.

</Accordion>

<div id="create-ping-identity-users-and-assign-them-to-groups-and-roles" />

<Accordion title="Создание пользователей Ping Identity и назначение им групп и ролей">

1. В меню администратора Ping Identity перейдите в **Identity** > <Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/user">**Users**</Anchor> и кликните +.  

   ![ping](https://files.readme.io/802946a62c1df918b82cccc1cf0855ffea8167ed91aa6b0d6bce8973c37b4e75-16292200536081.png)
2. В открывшемся справа разделе:
   1. Введите имя пользователя и адрес электронной почты.
   2. Выберите **Administrator Population**.
   3. Создайте одноразовый пароль для пользователя или нажмите **Generate Password**, чтобы сгенерировать пароль автоматически. Когда пользователь войдёт в Ping Identity, ему потребуется создать
   4. Нажмите **Save** (Сохранить).
3. Нажмите кнопку Edit для **Groups**, установите флажок рядом с группой, в которую нужно добавить пользователя, и нажмите **Save**.
4. Перейдите на вкладку **Roles** > **Grant roles**, выберите роли для пользователя и нажмите **Save**.

</Accordion>

<div id="provide-access-to-your-groups-and-activate-the-app" />

<Accordion title="Предоставьте доступ к своим группам и активируйте приложение">

<div id="provide-access-to-your-groups" />

### Предоставьте доступ к своим группам

1. В меню администратора Ping Identity перейдите в **Connections** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** и выберите созданное приложение.  

   ![pi-applications.png](https://files.readme.io/6c8545bc5334747d7da6a090ca745c1b00cfedc3f48e59ccc304c814885cd183-16522614384785.png)
2. На панели, открывшейся справа, выберите вкладку **Access** и нажмите кнопку Edit.
3. Выберите созданные группу или группы и нажмите **Save**.

<div id="activate-the-app" />

### Активируйте приложение

1. В меню администратора Ping Identity перейдите в **Connections** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** и выберите созданное приложение.
2. Активируйте приложение.  

   ![pi-appsflyer](https://files.readme.io/24c34f3426ae7b46301316937ae8485464e0b3810808e3bbcc1be843ba34a616-16523020816657.png)

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Завершите процесс в AppsFlyer">

Теперь, когда вы настроили часть IdP, вернитесь в AppsFlyer, чтобы <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">завершить настройку</Anchor>. Затем вы можете <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">провести тест</Anchor> , чтобы убедиться, что всё работает.

</Accordion>

<div id="see-also" />

> 📄 **Смотрите также**
>
> * <Anchor target="_blank" href="https://docs.pingidentity.com/r/en-us/pingfederate-112/pf_ident_provid_sso_config">Документация по настройке SSO в Ping Identity</Anchor>

<div data-zendesk-anchors="h_01HDP087XSDCY9W577GARNQ5GS=create-the-appsflyer-app-in-ping h_01HDP087XSRYXKE5TW7HYR3NYZ=create-ping-groups h_01HDP087XSKBVDREY0YZ27CG8T=create-ping-identity-users-and-assign-them-to-groups-and-roles h_01HDP087XSQPN3DAH8HAKMH3GS=provide-access-to-your-groups-and-activate-the-app provide-access-to-your-groups=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF-%D0%BA-%D1%81%D0%B2%D0%BE%D0%B8%D0%BC-%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D0%B0%D0%BC h_01HDP087XST1C28TEJXF3X8XK4=%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%8C%D1%82%D0%B5-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF-%D0%BA-%D1%81%D0%B2%D0%BE%D0%B8%D0%BC-%D0%B3%D1%80%D1%83%D0%BF%D0%BF%D0%B0%D0%BC activate-the-app=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D1%83%D0%B9%D1%82%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 h_01HDP087XSMBE3G6A4DSQ1WHBT=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D1%83%D0%B9%D1%82%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 h_01HDP087XS1S0XC5W74MK2AYY3=complete-the-process-in-appsflyer h_01HDP0ARX3NJZWBK0KC9Q64MG8=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />

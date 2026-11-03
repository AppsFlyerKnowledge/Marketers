---
title: Configure AppsFlyer SSO in Ping Identity
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
  edited_at: '2026-10-13T00:42:36Z'
  id: 16062655361937
  locale: zh-cn
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/zh-cn/articles/16062655361937
---
> **At a glance:** Configure the SSO process using Ping Identity as an identity provider (IdP).

The first step in configuring the AppsFlyer SSO process is done on the Ping Identity platform. Follow the steps below:

<div id="create-the-appsflyer-app-in-ping" />

<Accordion title="Create the AppsFlyer app in Ping Identity">

**Prerequisite:** A Ping Identity account with administrative privileges.

1. In the Ping Identity admin menu, go to **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** and click +.
2. From the section opened on the right:
   * Enter the name that you want to show in the Ping Identity plugin list of apps.
   * Select SAML Application as the app type.
3. Click **Configure**. SAML Configuration appears.
   * For authentication starting from the service provider (AppsFlyer), select **Import From URL**:
     * **Import URL:** <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">https://hq1.appsflyer.com/auth/sso-metadata</Anchor>
     * **ACS URLs:** Enter the following link using your AppsFlyer account ID:  
       <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">https://hq1.appsflyer.com/auth/sso-callback</Anchor>
     * **Entity ID:** Enter the following link: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>  

       <Image alt="ping" src="https://files.readme.io/8b265666f05bc4f6ab984151d7d73653b9ea5dcb837898d17e96bf9c392fe638-16063467179921.png" width="419px" />
   * For authentication starting from the IdP (Ping Identity), select **Manually Enter**:
     * **ACS URLs:** Enter the following link using your AppsFlyer account ID:   
       `https://hq1.appsflyer.com/auth/sso-callback/<Enter your AppsFlyer account ID here>`
     * **Entity ID:** Enter the following link: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>
4. Click **Save**.
5. Under the **Configuration** tab:
   1. Click **Download Metadata**.
   2. From the top right corner, click the Edit icon and enter the fields below:  

      <Image alt="ping" src="https://files.readme.io/386fab01b9389d88ea0c4870ba2ea8e33d9ab6e27322059be5e46efbf248714b-16063435689233.png" width="487px" />

      * **SIGNING KEY:**
        * Select **Sign Assertion & Response**.
        * **Signing Algorithm:** Select **RSA\_SHA256**.
      * **ENCRYPTION:**
        * Select **Enable Encryption**.
        * ALGORITHM: Select **AES\_256**.
      * **CERTIFICATE:**
        * Select **Import** and upload the <Anchor target="_blank" href="/marketers/zh/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url">AppsFlyer encryption certificate</Anchor>. This certificate is signed by AppsFlyer and is used to both encrypt and sign the request.  
          **Note:** You can upload the AppsFlyer certificate signed by Amazon. Contact your CSM to obtain this certificate.
        * Select **Enforced Signed Authn Request**.
6. Click **Save**.
7. Under the **Attribute Mappings** tab, click the Edit icon and select **Email Address** under **PingOne Mappings**.  

   <Image alt="ping-identity" src="https://files.readme.io/b93ac5463868c8f5f7760b60492a30f7ae59c52b766e76ef57fbe42e00f4bf2b-16292200523025.png" width="620px" />
8. Click **Save**.

</Accordion>

<div id="create-ping-groups" />

<Accordion title="Create Ping Identity groups">

Now that the Ping Identity SAML application is created, let’s create user groups and then add users to the groups.

1. In the Ping Identity admin menu, go to **Identity** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/group">Groups</Anchor>** and click +.  

   <Image alt="ping" src="https://files.readme.io/fcc2a3f035a285d96d7b7c3e83cfeed64e86cb0f0807e6acced75df89bd8dfc4-16292210866705.png" width="216px" />
2. From the section opened on the right, enter the group name and click **Save**.
3. Repeat steps 1-2 for all user groups.

</Accordion>

<div id="create-ping-identity-users-and-assign-them-to-groups-and-roles" />

<Accordion title="Create Ping identity users and assign them to groups and roles">

1. In the Ping Identity admin menu, go to **Identity** > <Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/user">**Users**</Anchor> and click +.  

   ![ping](https://files.readme.io/802946a62c1df918b82cccc1cf0855ffea8167ed91aa6b0d6bce8973c37b4e75-16292200536081.png)
2. From the section opened on the right:
   1. Enter the user's name and email address.
   2. Select **Administrator Population**.
   3. Create a one-time password for the user or click **Generate Password** to have one generated for the user. When the user enters Ping Identity, they'll need to create
   4. Click **Save**.
3. Click the Edit button for **Groups**, check the group to add the user, and click **Save**.
4. Click the **Roles** tab > **Grant roles**, select the roles for the user, and click **Save**.

</Accordion>

<div id="provide-access-to-your-groups-and-activate-the-app" />

<Accordion title="Provide access to your groups and activate the app">

### Provide access to your groups

1. In the Ping Identity admin menu, go to **Connections** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** and select the app you created.  

   ![pi-applications.png](https://files.readme.io/6c8545bc5334747d7da6a090ca745c1b00cfedc3f48e59ccc304c814885cd183-16522614384785.png)
2. From the section opened on the right, select the **Access** tab and click the Edit button.
3. Select the group or groups you created, and click **Save**.

### Activate the app

1. In the Ping Identity admin menu, go to **Connections** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** and select the app you created.
2. Activate the app.  

   ![pi-appsflyer](https://files.readme.io/24c34f3426ae7b46301316937ae8485464e0b3810808e3bbcc1be843ba34a616-16523020816657.png)

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Complete the process in AppsFlyer">

Now that you've configured the IdP part, go back to AppsFlyer to <Anchor target="_blank" href="/marketers/zh/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">complete the configuration</Anchor>. You can then <Anchor target="_blank" href="/marketers/zh/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">test</Anchor> to see that it works.

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="https://docs.pingidentity.com/r/en-us/pingfederate-112/pf_ident_provid_sso_config">Pin Identity SSO configuration documentation</Anchor>

<div data-zendesk-anchors="h_01HDP087XSDCY9W577GARNQ5GS=create-the-appsflyer-app-in-ping h_01HDP087XSRYXKE5TW7HYR3NYZ=create-ping-groups h_01HDP087XSKBVDREY0YZ27CG8T=create-ping-identity-users-and-assign-them-to-groups-and-roles h_01HDP087XSQPN3DAH8HAKMH3GS=provide-access-to-your-groups-and-activate-the-app h_01HDP087XST1C28TEJXF3X8XK4=provide-access-to-your-groups h_01HDP087XSMBE3G6A4DSQ1WHBT=activate-the-app h_01HDP087XS1S0XC5W74MK2AYY3=complete-the-process-in-appsflyer h_01HDP0ARX3NJZWBK0KC9Q64MG8=see-also" />

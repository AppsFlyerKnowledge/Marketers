---
title: Configure o SSO da AppsFlyer no Ping Identity
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
  edited_at: '2026-08-18T00:16:55Z'
  id: 16062655361937
  locale: pt
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/pt/articles/16062655361937
---
> **Em resumo:** Configure o processo de SSO usando o Ping Identity como provedor de identidade (IdP).

A primeira etapa da configuração do processo de SSO da AppsFlyer é realizada na plataforma Ping Identity. Siga as etapas abaixo:

<div id="create-the-appsflyer-app-in-ping" />

<Accordion title="Crie o aplicativo da AppsFlyer no Ping Identity">

**Pré-requisito:** uma conta do Ping Identity com privilégios administrativos.

1. No menu de administração do Ping Identity, acesse **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Aplicativos</Anchor>** e clique em +.
2. Na seção aberta à direita:
   * Insira o nome que você quer exibir na lista de aplicativos do plugin do Ping Identity.
   * Selecione SAML Application como o tipo de aplicativo.
3. Clique em **Configure**. A configuração de SAML é exibida.
   * Para autenticação iniciada pelo provedor de serviço (AppsFlyer), selecione **Import From URL**:
     * **URL de importação:** <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">https://hq1.appsflyer.com/auth/sso-metadata</Anchor>
     * **URLs ACS:** Insira o link a seguir usando o ID da sua conta da AppsFlyer:  
       <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">https://hq1.appsflyer.com/auth/sso-callback</Anchor>
     * **Entity ID:** Insira o link a seguir: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>  

       <Image align="center" alt="ping" src="https://files.readme.io/8b265666f05bc4f6ab984151d7d73653b9ea5dcb837898d17e96bf9c392fe638-16063467179921.png" width="419px" />
   * Para autenticação iniciada pelo IdP (Ping Identity), selecione **Manually Enter**:
     * **ACS URLs:** Insira o link a seguir usando o ID da sua conta da AppsFlyer:   
       `https://hq1.appsflyer.com/auth/sso-callback/<Insira aqui o ID da sua conta da AppsFlyer>`
     * **Entity ID:** Insira o link a seguir: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com/</Anchor>
4. Clique em **Guardar**.
5. Na guia **Configuration**:
   1. Clique em **Download Metadata**.
   2. No canto superior direito, clique no ícone de edição e preencha os campos abaixo:  

      <Image align="center" alt="ping" src="https://files.readme.io/386fab01b9389d88ea0c4870ba2ea8e33d9ab6e27322059be5e46efbf248714b-16063435689233.png" width="487px" />

      * **CHAVE DE ASSINATURA:**
        * Selecione **Sign Assertion & Response**.
        * **Algoritmo de assinatura:** selecione **RSA\_SHA256**.
      * **CRIPTOGRAFIA:**
        * Selecione **Ativar criptografia**.
        * ALGORITMO: selecione **AES\_256**.
      * **CERTIFICADO:**
        * Selecione **Importar** e faça upload do <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url">certificado de criptografia da AppsFlyer</Anchor>. Este certificado é assinado pela AppsFlyer e é usado tanto para criptografar quanto para assinar a solicitação.  
          **Observação:** Você pode fazer upload do certificado da AppsFlyer assinado pela Amazon. Entre em contato com seu CSM para obter este certificado.
        * Selecione **Enforced Signed Authn Request**.
6. Clique em **Guardar**.
7. Na guia **Attribute Mappings**, clique no ícone de edição e selecione **Email Address** em **PingOne Mappings**.  

   <Image align="center" alt="ping-identity" src="https://files.readme.io/b93ac5463868c8f5f7760b60492a30f7ae59c52b766e76ef57fbe42e00f4bf2b-16292200523025.png" width="620px" />
8. Clique em **Guardar**.

</Accordion>

<div id="create-ping-groups" />

<Accordion title="Criar grupos do Ping Identity">

Agora que o aplicativo SAML do Ping Identity foi criado, vamos criar grupos de usuários e depois adicionar usuários aos grupos.

1. No menu de administração do Ping Identity, acesse **Identity** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/group">Groups</Anchor>** e clique em +.  

   <Image align="center" alt="ping" src="https://files.readme.io/fcc2a3f035a285d96d7b7c3e83cfeed64e86cb0f0807e6acced75df89bd8dfc4-16292210866705.png" width="216px" />
2. Na seção aberta à direita, insira o nome do grupo e clique em **Salvar**.
3. Repita as etapas 1 a 2 para todos os grupos de usuários.

</Accordion>

<div id="create-ping-identity-users-and-assign-them-to-groups-and-roles" />

<Accordion title="Criar usuários do Ping Identity e atribuí-los a grupos e funções">

1. No menu de administração do Ping Identity, acesse **Identity** > <Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/user">**Users**</Anchor> e clique em +.  

   <Image align="center" alt="ping" src="https://files.readme.io/802946a62c1df918b82cccc1cf0855ffea8167ed91aa6b0d6bce8973c37b4e75-16292200536081.png" />
2. Na seção aberta à direita:
   1. Insira o nome e o endereço de e-mail do usuário.
   2. Selecione **Administrator Population**.
   3. Crie uma senha de uso único para o usuário ou clique em **Generate Password** para que uma senha seja gerada para o usuário. Quando o usuário entrar no Ping Identity, ele precisará criar
   4. Clique em **Guardar**.
3. Clique no botão Editar de **Groups**, marque o grupo para adicionar o usuário e clique em **Save**.
4. Clique na guia **Roles** > **Grant roles**, selecione as funções para o usuário e clique em **Save**.

</Accordion>

<div id="provide-access-to-your-groups-and-activate-the-app" />

<Accordion title="Forneça acesso aos seus grupos e ative o aplicativo">

<div id="provide-access-to-your-groups" />

### Forneça acesso aos seus grupos

1. No menu de administração do Ping Identity, acesse **Connections** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** e selecione o aplicativo que você criou.  

   <Image align="center" alt="pi-applications.png" src="https://files.readme.io/6c8545bc5334747d7da6a090ca745c1b00cfedc3f48e59ccc304c814885cd183-16522614384785.png" />
2. Na seção aberta à direita, selecione a guia **Access** e clique no botão Editar.
3. Selecione o grupo ou os grupos que você criou e clique em **Save**.

<div id="activate-the-app" />

### Ative o aplicativo

1. No menu de administração do Ping Identity, acesse **Connections** > **<Anchor target="_blank" href="https://console.pingone.com/index.html?env=7ea15898-af17-4469-8a1e-eba50c4675a1#/7ea15898-af17-4469-8a1e-eba50c4675a1/applications">Applications</Anchor>** e selecione o aplicativo que você criou.
2. Ative o aplicativo.  

   <Image align="center" alt="pi-appsflyer" src="https://files.readme.io/24c34f3426ae7b46301316937ae8485464e0b3810808e3bbcc1be843ba34a616-16523020816657.png" />

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Conclua o processo na AppsFlyer">

Agora que você configurou a parte do IdP, volte para a AppsFlyer para <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">concluir a configuração</Anchor>. Em seguida, você pode fazer o <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">teste</Anchor> para verificar se funciona.

</Accordion>

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="https://docs.pingidentity.com/r/en-us/pingfederate-112/pf_ident_provid_sso_config">Documentação de configuração de SSO do Ping Identity</Anchor>

<div data-zendesk-anchors="h_01HDP087XSDCY9W577GARNQ5GS=create-the-appsflyer-app-in-ping h_01HDP087XSRYXKE5TW7HYR3NYZ=create-ping-groups h_01HDP087XSKBVDREY0YZ27CG8T=create-ping-identity-users-and-assign-them-to-groups-and-roles h_01HDP087XSQPN3DAH8HAKMH3GS=provide-access-to-your-groups-and-activate-the-app provide-access-to-your-groups=forne%C3%A7a-acesso-aos-seus-grupos h_01HDP087XST1C28TEJXF3X8XK4=forne%C3%A7a-acesso-aos-seus-grupos activate-the-app=ative-o-aplicativo h_01HDP087XSMBE3G6A4DSQ1WHBT=ative-o-aplicativo h_01HDP087XS1S0XC5W74MK2AYY3=complete-the-process-in-appsflyer h_01HDP0ARX3NJZWBK0KC9Q64MG8=consulte-tamb%C3%A9m" />

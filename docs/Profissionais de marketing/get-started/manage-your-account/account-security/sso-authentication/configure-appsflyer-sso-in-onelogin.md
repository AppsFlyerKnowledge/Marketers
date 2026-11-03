---
title: Configure o SSO do AppsFlyer no OneLogin
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
  edited_at: '2026-08-18T00:16:52Z'
  id: 15044997313041
  locale: pt
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/pt/articles/15044997313041
---
> **Em resumo:** Configure o processo de SSO usando o OneLogin como provedor de identidade (IdP).

A primeira etapa da configuração do processo de SSO do AppsFlyer é realizada na plataforma OneLogin. Siga as etapas abaixo:

<div id="create-the-appsflyer-app-in-oonelogin" />

<Accordion title="Crie o aplicativo AppsFlyer no OneLogin">

**Pré-requisito:** uma conta do OneLogin com privilégios administrativos.

1. No console de administração do OneLogin, acesse **Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**.
2. No canto superior direito, clique em **Add App**.
3. Pesquise e selecione **Conector personalizado SAML (Advanced)**.  

   <Image alt="onelogin_saml_app.png" src="https://files.readme.io/c1e5ec122e21f05e860486ad280ba9e692b3d05b05105d9c1ca700b8921ee6ab-15045173609745.png" width="601px" />
4. No campo **Display Name**, insira o nome a ser exibido na lista de aplicativos do plugin do OneLogin.
5. [Opcional] **Logo do aplicativo**: adicione um logotipo para aparecer ao lado do nome do aplicativo.
6. [Opcional] Adicione uma descrição.
7. Clique em **Guardar**. Uma mensagem de sucesso aparece na parte superior.
8. Acesse a guia **Configuration** no menu lateral.
9. Defina a integração de acordo com os campos a seguir:
   * **Audience (EntityID):** insira este link: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com</Anchor>
   * **ACS (Consumer) URL Validation**, **ACS (Consumer) URL:** insira o endpoint para o qual o OneLogin envia a verificação do usuário. Use o link de acordo com a <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">configuração da URL de callback descrita aqui</Anchor>
   * **Recipient:** insira a mesma URL informada no campo **ACS (Consumer) URL** field.
   * **Login URL:** insira a <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">URL de login</Anchor> do AppsFlyer .
   * **SAML not valid before**, **SAML not valid on or after:** especifique o período (em minutos) durante o qual a asserção é válida.
   * **Iniciador SAML:** <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">Selecione de onde a autenticação começa</Anchor>:
     * Para autenticação iniciada pelo IdP, selecione **OneLogin**
     * Para autenticação iniciada pelo AppsFlyer, selecione **Service Provider**
   * **Formato de nameID do SAML:** selecione e-mail.
   * **Tipo de emissor SAML:** Selecione Specific.
   * **Elemento de assinatura SAML:** Selecione **Both**.
   * **Criptografar asserção**: marque esta caixa de seleção.
   * **Método de criptografia SAML:** Selecione **AES-256-CBC**.
10. Clique em **Guardar**.
11. **Criptografia da asserção:** 
    1. Abra <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">a URL de metadados de SSO</Anchor> e copie o valor do certificado de criptografia.
    2. Volte para a guia **Configuration** e cole na caixa de texto **SAML encryption** .
    3. Clique em **Guardar**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Obter metadados de SSO do IdP">

1. No aplicativo selecionado (**Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**), selecione **SSO** no menu lateral.
2. Copie a **Issuer URL** e cole-a em uma nova guia para fazer o download dos metadados de SSO.

</Accordion>

<div id="create-onelogin-users" />

<Accordion title="Criar usuários do OneLogin">

1. No menu superior, vá para **Users** > <Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/users">**Users**</Anchor>.
2. Clique em **New User** no canto superior direito.
3. Digite o **First name**, o **Last name** e o **Email** do usuário.
4. No canto superior direito, clique em **Save User**, depois em **More Actions,** e selecione **Change Password** para definir uma senha para o usuário.
5. Defina uma senha para o usuário e clique em **Update**.

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="Atribuir usuários ao seu aplicativo">

1. Vá para a guia **Application** no menu lateral do usuário selecionado.
2. Clique no sinal + ao lado de **Applications**.
3. Selecione o aplicativo da AppsFlyer que você criou e clique em **Continue**.  

   <Image alt="onelogin_assign_app.png" src="https://files.readme.io/a1769673f3f167f728a00fb1cccb951bd246798fd7327c51b021f73987bc8fb2-15552909316241.png" width="326px" />
4. No menu superior, vá para **Applications** > **<Anchor target="_blank" href="https://appsflyer-dev.onelogin.com/admin2/apps">Applications</Anchor>**.
5. Selecione o aplicativo que você acabou de criar.
6. Clique em **Guardar**.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Conclua o processo na AppsFlyer">

Agora que você configurou a parte do IdP, volte para a AppsFlyer para <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">concluir a configuração</Anchor>. Em seguida, você pode <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">testar</Anchor> para ver se funciona.

</Accordion>

<div data-zendesk-anchors="h_01HF690GVE4FXXTMC5QWSJTY3C=create-the-appsflyer-app-in-oonelogin h_01HF690GVECMCVQAJFZ509MD50=get-idp-sso-metadata h_01HF690GVEKMV3TZ8MAD4HM635=create-onelogin-users h_01HF690GVEVEQ4GNJGXHKF5VT1=assign-users-to-your-app h_01HF690GVEWYEGR2Z9F22FQHGE=complete-the-process-in-appsflyer" />

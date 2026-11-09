---
title: Configure o SSO da AppsFlyer no Okta
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
  edited_at: '2026-08-18T00:16:50Z'
  id: 12934808889745
  locale: pt
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/pt/articles/12934808889745
---
> **Em resumo:** Configure o processo de SSO usando o Okta como provedor de identidade (IdP).

A primeira etapa da configuração do processo de SSO da AppsFlyer é realizada na plataforma Okta. Siga as etapas abaixo:

<div id="create-the-appsflyer-app-in-okta" />

<Accordion title="Crie o aplicativo da AppsFlyer no Okta">

**Pré-requisito:** uma conta Okta com privilégios administrativos.

1. No Console de Administração, acesse **Aplicativos** > **Aplicativos**.  
   <Image align="center" alt="Okta_menu_lateral_aplicativos.png" src="https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png" width="241px" />
2. Clique em **Create App Integration**.
3. Na caixa de diálogo **Create a new app integration**, selecione **SAML 2.0** e clique em **Next**.
4. Em **(1) General Settings**, no campo **App name**, insira o nome que você quer exibir na lista de aplicativos do plugin do Okta.  
   <Image align="center" alt="Okta_nome_e_ícone_do_aplicativo__1_.png" src="https://files.readme.io/6998e7737b0aa5c4d70ad97ab41e17e471ddaf060e78c44fa2de41be1df17574-13572380565521.png" width="639px" />
5. [Opcional] **App logo**: adicione um logotipo para aparecer ao lado do nome do aplicativo.
6. Clique em **próximo**.
7. Em **(2) Configure SAML Integration**, defina a integração de acordo com os seguintes campos: ![okta-create-saml-integration.png](https://files.readme.io/6c276dd54afd30e828b989fc6796de5eca46282ade015e7a34e0bd1cc95d7fb8-16870970396177.png)
   * **Single sign-on URL:** Insira o endpoint para o qual o Okta envia a verificação do usuário. Use o link de acordo com a <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">configuração da URL de callback descrita aqui</Anchor>
   * **Audience URI (SP Entity ID):** Insira este link: <Anchor target="_blank" href="https://hq1.appsflyer.com/">https://hq1.appsflyer.com</Anchor>
   * **Name ID format:** Selecione **EmailAddress** como formato para identificar o usuário
   * **Application username:** Selecione **Okta username**  
     **Observação:** o e-mail do usuário do Okta deve ser o mesmo e-mail da conta do usuário na AppsFlyer
8. Clique em **Show Advanced Settings** e defina a integração de acordo com cada um dos campos mostrados na imagem abaixo:

   <Image align="center" alt="Okta_configurações_avançadas__1_.png" src="https://files.readme.io/9a3461f700cc50a54237578a304206ed7693e30cdd516398089954321cd44af4-13572576788241.png" width="640px" />

   * **Assertion Encryption:** Selecione **Encrypted** ou **Unencrypted**.   
     **Observação:** como as asserções são controladas pelo seu IdP, recomendamos selecionar **Encrypted**.
   * **Encryption certificate:** Faça upload do <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#obtaining-the-appsflyer-certificate-from-the-metadata-url">certificado de criptografia da AppsFlyer</Anchor>. Este certificado é assinado pela AppsFlyer e é usado tanto para criptografar quanto para assinar a solicitação.
   * [Opcional] **Signature certificate:** Faça upload do <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#the-authentication-certificate">certificado de assinatura da AppsFlyer</Anchor>.
9. Role até o final da página e clique em **Próximo**.
10. Selecione **Sou cliente da Okta e estou adicionando um Aplicativo interno** e clique em **Concluir**.

</Accordion>

<div id="create-okta-users" />

<Accordion title="Criar usuários do Okta">

Agora que o aplicativo SAML do Okta foi criado, vamos adicionar usuários.

1. No console de administração, selecione **Directory** > **People**.

   <Image align="center" alt="Okta___directory___people.png" src="https://files.readme.io/d9c5da8787fdb81bf97bc0753b2f7794cdc59060e5026348428545064d138d18-13572579297169.png" width="226px" />
2. Clique em **Adicionar pessoa**.

   <Image align="center" alt="Okta___People___Add_person.png" src="https://files.readme.io/6bb8b854cf000259970d63b9eacb28bf6d4079d648939814aaa0e456a96c9bbe-13572600647697.png" width="524px" />
3. Na caixa de diálogo **Adicionar pessoa**:

   <Image align="center" alt="Okta_Add_person__1_.png" src="https://files.readme.io/d6d7e198fab965872b5a01302a00bdbd0bfb5d561af372fc4390c9882a22a42c-13572617052689.png" width="620px" />

   * Em **User type**, selecione **usuário**.
   * Preencha todos os campos obrigatórios: **First name**, **Last name**, **Username** (deve ser um e-mail) e **Primary email**.
   * Em **Password**, você pode escolher se ela será definida pelo usuário ou pelo administrador.
4. Para continuar adicionando usuários, clique **Save and Add Another**, e repita as etapas 1 a 4. Quando terminar de adicionar todos os usuários, clique em **Save**.

</Accordion>

<div id="assign-users-to-your-app" />

<Accordion title="Atribuir usuários ao seu Aplicativo">

1. No console de administração, volte para **Applications** > **Applications**.
2. Em **Browse App Catalog**, selecione o aplicativo que você acabou de criar.  
   <Image align="center" alt="Okta_side_menu___applications.png" src="https://files.readme.io/c218e729a7c00158e3804e7c7d884ec5b098e56628037ced54ad3c311470e038-13572360791825.png" width="233px" />
3. No aplicativo selecionado, na guia **Assignments**, clique em **Assign** > **Assign to People**.  
   <Image align="center" alt="Okta_sso_assign_to_people.png" src="https://files.readme.io/50930693a4a58ad8162b2ac81e476081c9b0288da4dab5b92bb41fece4aff586-14942267242769.png" />
4. Encontre o usuário que será atribuído ao seu aplicativo e clique em **Assign**.
5. Repita esta etapa para todos os usuários.
6. Clique em **Done** quando terminar de adicionar todos os usuários. Os novos usuários agora aparecem em **People**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Obter metadados de SSO do IdP">

1. No console de administração, volte para **Applications** > **Applications**.
2. Em **Browse App Catalog**, selecione seu aplicativo.
3. Clique na aba **Sign On**.
4. Na seção **SAML Signing Certificates** , clique em **Actions** > **View IdP metadata** do certificado ativo. <Image alt="okta_sso_view_idp_metadata.png" src="https://files.readme.io/a6d9f6753ead962713851bcc367abba6fad226d6e0a5f908055e44b1d3e1b2be-14942369009809.png" width="601px" />
5. Copie a URL da guia que foi aberta. Você usará essa URL na próxima etapa na plataforma AppsFlyer.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Conclua o processo na AppsFlyer">

Agora que você configurou a parte do IdP, volte para a AppsFlyer para <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">concluir a configuração</Anchor>. Em seguida, você pode <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">testar</Anchor> para ver se funciona.

</Accordion>

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="https://developer.okta.com/docs/guides/build-sso-integration/openidconnect/main/">Documentação do SSO do Okta</Anchor>

<div data-zendesk-anchors="h_01HDNZYDQGGBMB9MJ97RF4BADM=create-the-appsflyer-app-in-okta h_01HDNZYDQGGFCA2KB9PDQY1ZTG=create-okta-users h_01HDNZYDQGC9MRQH92MM8W4FVE=assign-users-to-your-app h_01HDNZYDQGWRE9K6XG5EPYTYYX=get-idp-sso-metadata h_01HDNZYDQG6GNEP3TQMXVT5FTG=complete-the-process-in-appsflyer h_01HDP00WTAVP0X8FT51JC1JKKC=consulte-tamb%C3%A9m" />

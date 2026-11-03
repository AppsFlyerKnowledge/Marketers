---
title: Configure o SSO do AppsFlyer no JumpCloud
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
  edited_at: '2026-08-18T00:16:46Z'
  id: 13563131567249
  locale: pt
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/pt/articles/13563131567249
---
> **Em resumo:** Configure o processo de SSO usando o JumpCloud como provedor de identidade (IdP).

A primeira etapa da configuração do processo de SSO do AppsFlyer é realizada na plataforma JumpCloud. Siga as etapas abaixo:

<div id="create-the-appsflyer-app-in-jumpcloud" />

<Accordion title="Criar o aplicativo do AppsFlyer no JumpCloud">

**Pré-requisito:** uma conta do JumpCloud com privilégios administrativos.

1. No menu de administração do JumpCloud, acesse <Anchor target="_blank" href="https://console.jumpcloud.com/#/sso">SSO</Anchor> e clique em **+ Add New Application**.
2. Procure por AppsFlyer na lista de aplicativos e clique em **configure**.
3. No **New SSO**, na guia **General Info** , dê um nome ao seu aplicativo no campo **Display label** .
4. [Opcional] Adicione uma descrição.
5. Na guia **SSO**:
   1. **Upload Metadata:** Faça download dos <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">metadados de SSO do AppsFlyer</Anchor> como um arquivo XML e, em seguida, faça upload deles aqui.
   2. **ACS URLs:** Insira a URL de callback de acordo com o <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#single-signon-url-configuration">método de autenticação dos seus usuários</Anchor>.
   3. **Login URL:** Insira a <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">URL de login</Anchor> do AppsFlyer.  

      <Image alt="jumpcloud_sso_tab2__1_.png" src="https://files.readme.io/3b45c98d191a35644c5479a0237e92908ca6f18416f6df2b6e0c84a30940307b-15934671100561.png" width="477px" />
6. Clique em **Ativar**.
7. Um certificado público é criado. Uma indicação disso aparece no canto superior direito da página. Clique em **Download Certificate**. Este certificado é necessário na <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">Etapa 2, na plataforma AppsFlyer</Anchor>.

</Accordion>

<div id="create-jumpcloud-users" />

<Accordion title="Criar usuários no JumpCloud">

1. No menu de administração do JumpCloud, acesse <Anchor target="_blank" href="https://console.jumpcloud.com/#/users">Users</Anchor> e clique no ícone +.
2. Selecione **Manual user entry**.  
   <Image alt="cloud_jump_manual_user_entry.png" src="https://files.readme.io/d00299979fa5e036c464c8c6d360965d46e42d5042a31366ced7adc84914c0be-14947838808081.png" width="417px" />
3. Preencha todos os campos obrigatórios: **Username**, **Company Email**, e clique em **save user**.
4. Defina as configurações de senha do usuário de acordo com o método aceito na sua empresa.
5. Para continuar adicionando usuários, clique em **Salvar e criar outro** e repita a etapa 3. Quando terminar de adicionar todos os usuários, clique em **Salvar**.

</Accordion>

<div id="create-jumpcloud-groups" />

<Accordion title="Crie grupos no JumpCloud e atribua-os ao aplicativo AppsFlyer">

Crie um grupo e atribua usuários a ele:

1. No menu de administração do JumpCloud, acesse <Anchor target="_blank" href="https://console.jumpcloud.com/#/groups/user">Grupos de usuários</Anchor> e clique no ícone + .
2. Digite o nome do grupo.
3. Na guia **Usuários**, selecione os usuários para adicionar a este grupo.
4. Na guia **Aplicativos**, selecione o aplicativo AppsFlyer que você acabou de criar.
5. Clique em **save**.

</Accordion>

<div id="get-idp-sso-metadata" />

<Accordion title="Obter metadados de SSO do IdP">

1. No menu de administração do JumpCloud, acesse **SSO**.
2. Selecione o aplicativo AppsFlyer que você acabou de configurar e clique em **Copy Metadata URL** no canto superior direito. Você colará este link na próxima etapa.

</Accordion>

<div id="complete-the-process-in-appsflyer" />

<Accordion title="Conclua o processo na AppsFlyer">

Agora que você configurou a parte do IdP, volte para a AppsFlyer para <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">concluir a configuração</Anchor>. Em seguida, você pode <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-3-test-the-sso-process">testar</Anchor> para verificar se funciona.

</Accordion>

<div data-zendesk-anchors="h_01HF99ZFBKPYCP8228VKWPCRHX=create-the-appsflyer-app-in-jumpcloud h_01HF99ZFBKXD6HQE44FDQVQZWK=create-jumpcloud-users h_01HF99ZFBK0T9JQVFNTX705V9M=create-jumpcloud-groups h_01HF99ZFBKDFKTFXEE8Q0MH6SY=get-idp-sso-metadata h_01HF99ZFBK40ZTFKKJNXP4N294=complete-the-process-in-appsflyer" />

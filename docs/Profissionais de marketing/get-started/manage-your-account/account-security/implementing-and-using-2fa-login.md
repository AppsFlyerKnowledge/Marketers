---
title: Como implementar a autenticação de dois fatores
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
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
  created_at: '2020-06-22T10:25:26Z'
  edited_at: '2026-08-18T00:17:19Z'
  id: 360010178037
  locale: pt
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/pt/articles/360010178037
---
> **Resumo:** a autenticação de dois fatores (2FA) oferece uma camada adicional de segurança no processo de login. As credenciais de login podem ser verificadas pelo Google Authenticator ou via SMS.

<div id="highlights" />

## Destaques

* A autenticação de dois fatores (2FA) é um recurso opcional, que deve ser ativado por um usuário administrador.
* As opções de autenticação são **Google Authenticator** e **verificação por SMS.**
* A ativação ou desativação desse recurso impacta todos os usuários da conta.
* No momento da ativação, os usuários fazem o login e recebem uma solicitação para configurar a autenticação de dois fatores para o próximo login.

<div id="-admin-managing-2fa" />

## ![admin.png](https://files.readme.io/d54680123b25ab7929285cebd778e0e74bd0d032df994b04d1bca106381c3dc6-360014518718.png) Admin: Gerir 2FA

Apenas um usuário administrador pode ativar, resetar ou desativar as configurações de autenticação de um usuário.

<div id="activate" />

<Accordion title="Ativar">

Se o administrador ativar tanto o **Google Authenticator** quanto a **verificação por SMS**, os usuários da conta podem escolher seu método preferido.

<div id="note" />

> 📘 **Nota**
>
> a verificação por SMS depende do status de envio do SMS, que varia de acordo com a operadora de celular e o país. Portanto, recomendamos a ativação tanto da verificação por SMS quanto do Google Authenticator, para evitar bloqueios devido a falhas na entrega de SMS.

**Para ativar a autenticação de dois fatores:**

1. Na barra superior, abra o menu da conta (menu suspenso no endereço de e-mail) > **Centro de segurança.**
2. Em **Segurança aprimorada para login**, clique em **Configurar método de login** para acessar a página **Segurança no login**.
3. Em **Autenticação de dois fatores (2FA)**, ative o botão para **Google Authenticator** e/ou **verificação por SMS.**

</Accordion>

<div id="reset" />

<Accordion title="Resetar">

Em alguns casos, é necessário resetar a autenticação de dois fatores de um usuário. Ao fazer isso, o **Google Authenticator** se torna automaticamente a tela de login padrão para autenticação de dois fatores.

**Para resetar a configuração de autenticação de um usuário:**

1. Na barra de menu, clique no menu suspenso no endereço de e-mail.
2. Selecione **Gerenciar usuários.**
3. Em **Usuários**, clique no botão <Image alt="" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />Ações altactions\_icon.png no lado direito.
4. Selecione **Resetar autenticação de dois fatores (2FA)** no menu.

**Atenção:** Um administrador pode resetar a autenticação de dois fatores de qualquer outro administrador, exceto a sua própria ou a do <Anchor target="_blank" href="/marketers/pt/docs/user-management#administrador">proprietário da conta</Anchor>. Para resetar a autenticação de dois fatores do proprietário da conta, entre em contato com a equipe de suporte da AppsFlyer.

</Accordion>

<div id="deactivate" />

<Accordion title="Desativar">

Se a autenticação de dois fatores estiver desativada, os usuários da conta farão login usando apenas seu nome de usuário e senha.

**Para desativar esse recurso:**

1. Na barra superior, abra o menu da conta (menu suspenso no endereço de e-mail) **> Centro de segurança.**
2. Em **Segurança aprimorada para login**, clique em **Configurar método de login** para acessar a página **Segurança no login**.
3. Em **Autenticação de dois fatores (2FA)**, desative **Google Authenticator** e/ou **verificação por SMS.**
4. Confirme a desativação.

</Accordion>

<div id="account-users-using-google-or-microsoft-authenticator" />

## Usuários da conta: usando o Google Authenticator

O **Google Authenticator** é a tela inicial padrão; no entanto, o último método de autenticação usado aparece no próximo login.

Se você optar por não usar o **Google Authenticator**, então as telas de configuração e login mostram um link para a tela de **verificação por SMS**.

<div id="firsttime-setup" />

<Accordion title="Configuração inicial">

Antes de usar a autenticação de dois fatores pela primeira vez, cada usuário da conta deve baixar o **Google Authenticator** e um aplicativo de leitura de **QR code**. Esses aplicativos estão disponíveis via **Google Play** (Android) e na **App Store** (iOS).

**Novo usuário da conta**

1. Siga as instruções do e-mail e crie uma senha.
2. Faça login na **AppsFlyer**. Em seguida, você será redirecionado para a página de configuração da autenticação de dois fatores.
3. Configure o método desejado.
   * Baixe o **Google Authenticator** e um aplicativo de leitura de **QR codes**.
   * Escaneie o QR code.
   * Digite o código de verificação emitido pelo **Google Authenticator**.
   * Clique em **verificar**, e você será redirecionado para a página **meus aplicativos**.

**Usuários existentes**

1. Faça login na **AppsFlyer** (nome de usuário e senha). Em seguida, você será redirecionado para a página de configuração da autenticação de dois fatores.
2. Configure o método desejado.
   * Baixe o **Google Authenticator** e um aplicativo de leitura de **QR codes**.
   * Escaneie o QR code.
   * Digite o código de verificação emitido pelo **Google Authenticator**.
   * Clique em **verificar**. Em seguida, você será redirecionado para a página **meus aplicativos**.

</Accordion>

<div id="ongoing-use" />

<Accordion title="Uso contínuo">

**Siga as etapas abaixo para uso contínuo.**

1. Faça login na **AppsFlyer** (nome de usuário e senha). Em seguida, você será redirecionado para a página de login com a autenticação de dois fatores.
2. Abra **Google Authenticator** no seu celular para obter o código de verificação.
3. Digite o código na página de autenticação.
4. Clique em **verificar**. Em seguida, você será redirecionado para a página **meus aplicativos**.

</Accordion>

<div id="account-users-using-sms-verification" />

## Usuários da conta: verificação por SMS

Se você não quiser usar a **verificação por SMS**, as telas de configuração e login mostram um link para a tela de autenticação do **Google Authenticator**.

<div id="firsttime-sms-setup" />

<Accordion title="Configuração de SMS pela primeira vez">

O **Google Authenticator** é o método padrão. Para acessar o método de **verificação por SMS**, clique no link **verificação por SMS**.

**Novo usuário da conta**

1. Siga as instruções do e-mail e crie uma senha.
2. Faça login na **AppsFlyer**. Em seguida, você será redirecionado para a página de configuração da autenticação de dois fatores.
3. Configure a autenticação de dois fatores:
   * Digite seu número de celular (apenas números, sem caracteres especiais) e clique em **enviar código.**
   * Digite o código de verificação por SMS > clique em **verificar.** Etapa 1:

**Usuários existentes**

1. Faça login na **AppsFlyer** (nome de usuário e senha). Em seguida, você será redirecionado para a página de configuração da autenticação de dois fatores.
2. Configure a autenticação de dois fatores:
   * Digite seu número de celular (apenas números, sem caracteres especiais) e clique em **enviar código.**
   * Digite o código de verificação por SMS > clique em **verificar.**

</Accordion>

<div id="ongoing-sms-use" />

<Accordion title="Uso contínuo">

**Siga as etapas abaixo para uso contínuo.**

1. Faça login na **AppsFlyer** (nome de usuário e senha). Em seguida, você será redirecionado para a página de login com a autenticação de dois fatores.
2. Caso esse tenha sido o método usado no último login, a página de **verificação por SMS** é exibida. Caso contrátio, clique no link na parte inferior da página do **Google Authenticator**.
3. Seu número de celular será exibido automaticamente. Clique em **enviar código.**
4. Digite o código de verificação enviado por SMS.
5. Clique em **verificar**.

</Accordion>

<div data-zendesk-anchors="highlights=destaques h_01HEHRKE8PY64KWVSSFR6T4F1Z=destaques admin-managing-2fa=-admin-gerir-2fa h_01HEHRKE8PZA3H9SXPRD1FZ50S=-admin-gerir-2fa h_01HEHRKE8PV0ZADPXHNBBDMKAF=activate 01JCDTA1W486FEFRPT2VYJ2PVX=nota h_01HEHRKE8P9N2W871ZEB1D3MYN=reset h_01HEHRKE8PEDWCNKMG1N4CFDMN=deactivate account-users-using-google-authenticator=usu%C3%A1rios-da-conta-usando-o-google-authenticator h_01HEHRKE8P1A2BARBDVMJPH1WY=usu%C3%A1rios-da-conta-usando-o-google-authenticator h_01HEHRKE8QQTX3Y9ZY1HZ6GBAG=firsttime-setup h_01HEHRKE8QHWHCMNB5M7S5YVYJ=ongoing-use account-users-using-sms-verification=usu%C3%A1rios-da-conta-verifica%C3%A7%C3%A3o-por-sms h_01HEHRKE8QZ245ZYBZ4FF814KN=usu%C3%A1rios-da-conta-verifica%C3%A7%C3%A3o-por-sms h_01HEHRKE8Q30QHGZ5QYMV4MR27=firsttime-sms-setup h_01HEHRKE8Q0229YE5QP5EJFSD8=ongoing-sms-use" />

---
title: Gerenciar usuários de exceção para SSO
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2026-05-27T08:43:46Z'
  edited_at: '2026-08-18T00:16:58Z'
  id: 47096696016529
  locale: pt
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/pt/articles/47096696016529
---
> **Em resumo:** usuários de exceção são usuários que não precisam fazer login por SSO. O SSO continua sendo aplicado à conta, e os administradores podem conceder a usuários específicos acesso a um método alternativo de login atribuído.

## **Sobre usuários de exceção**

Usuários de exceção fornecem acesso controlado para usuários que precisam de um método de login sem SSO. Por exemplo, os administradores podem usar usuários de exceção para acesso de emergência ou para usuários que não podem usar o provedor de identidade da conta.

Usuários de exceção podem fazer login com SSO ou com o método alternativo de login atribuído a eles. Usuários que não forem adicionados como usuários de exceção devem fazer login por SSO.

Recomendamos adicionar pelo menos um administrador confiável como usuário de exceção durante a configuração inicial do SSO. Se a configuração de SSO estiver incorreta, o administrador poderá fazer login com o método alternativo de login atribuído e atualizar a configuração.

## **Pré-requisitos**

* O SSO deve estar configurado para a conta.
* Para gerenciar o SSO e os usuários de exceção, você deve ter a permissão **Segurança de login** definida como **Gerenciar**.

<div id="add-exception-users-during-sso-setup" />

<Accordion title="Adicionar usuários de exceção durante a configuração do SSO">

**Recomendado:** adicione pelo menos um administrador confiável como usuário de exceção antes de ativar o SSO. Isso ajuda a evitar o bloqueio da conta se a configuração de SSO estiver incorreta.

Para adicionar usuários de exceção:

1. Na etapa **Adicionar usuários de exceção**, clique em **Adicionar usuários de exceção**.
2. Busque um usuário por nome ou e-mail.
3. Selecione o usuário que você deseja adicionar.
4. Na lista suspensa **Método alternativo de login**, selecione uma das seguintes opções:
   * **Nome de usuário & senha**
   * **App de autenticação**
5. Repita as etapas 2 a 4 para cada usuário que você deseja adicionar.
6. Provedor de serviços (metadados da AppsFlyer) — os detalhes estão disponíveis
7. Vá para qualquer uma das seções e selecione a opção desejada.

Se você não adicionar usuários de exceção, todos na conta deverão fazer login por SSO após a ativação.

</Accordion>

<div id="add-login-methods-for-multiple-users" />

<Accordion title="Adicionar métodos de login para vários usuários">

Para adicionar o mesmo método alternativo de login para vários usuários:

1. Marque as caixas de seleção dos usuários que você deseja atualizar.
2. Clique em **Definir método de login para os usuários selecionados**.
3. Escolha uma das seguintes opções:
   * **Utilizar nome de usuário e senha para todos os usuários selecionados**
   * **Usar aplicativo de autenticação para todos os usuários selecionados**

</Accordion>

<div id="edit-exception-users-after-sso-activation" />

<Accordion title="Editar usuários de exceção após a ativação do SSO">

Depois que o SSO estiver ativo, você poderá adicionar usuários de exceção, excluir usuários de exceção ou atualizar os métodos alternativos de login deles.

Para editar usuários de exceção:

1. Acesse **Central de segurança** > **Segurança de login**.
2. Clique em **Excluir** no ícone de lixeira do lado direito da seção **Single sign-on (SSO) do SAML**.
3. Abra a seção **Usuários de exceção**.
4. Clique no ícone **Editar** <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="24px" /> do lado direito da seção **Single sign-on (SSO) do SAML**.
5. Adicione usuários, exclua usuários ou atualize métodos alternativos de login.
6. Clique em **Guardar**.
7. Clique em **Salvar alterações**. Clique em **Salvar alterações**.

Os usuários de exceção adicionados anteriormente aparecem com o método alternativo de login atual.

</Accordion>

<div id="delete-exception-users" />

<Accordion title="Excluir usuários de exceção">

Para excluir um usuário de exceção:

Na caixa de diálogo Editar usuários de exceção, localize o usuário que você deseja excluir.

Clique no ícone Excluir.

O usuário é removido da lista imediatamente.

</Accordion>

<div id="alternative-login-methods" />

<Accordion title="Método de login">

| **Método de login** | **A descrição** |
| --- | --- |
| Nome de usuário & senha | Permite que o usuário de exceção faça login com o nome de usuário e a senha do AppsFlyer. |
| App de autenticação | Permite que o usuário de exceção faça login usando um aplicativo de autenticação. SMS não tem suporte. |

</Accordion>

<div id="handle-partial-activation-failures" />

<Accordion title="Lidar com falhas parciais de ativação">

Em alguns casos, a ativação do SSO é bem-sucedida, mas um ou mais usuários de exceção não são adicionados.

Quando isso acontece:

* O SSO permanece ativo.
* Os usuários que não foram adicionados como usuários de exceção devem fazer login pelo SSO.
* Os administradores podem adicionar ou atualizar usuários de exceção em **Editar SSO**.

</Accordion>

<div id="reset-passwords-for-sso-accounts" />

<Accordion title="Redefinir senhas de contas de SSO">

Todos os usuários podem iniciar o fluxo de "Esqueci a senha". No entanto, apenas os usuários de exceção aos quais foi atribuído o método alternativo de login **Nome de usuário & senha** podem fazer login com a nova senha.

Os usuários que não são usuários de exceção devem continuar fazendo login por SSO.

</Accordion>

<div id="migrate-from-legacy-unforce-sso" />

<Accordion title="Migrar do Unforce SSO legado">

Para contas migradas do Unforce SSO legado no nível da conta, os usuários existentes que faziam login com nome de usuário e senha são adicionados como usuários de exceção, com **Nome de usuário & senha** como método alternativo de login.

Os novos usuários criados após a migração devem fazer login por SSO, a menos que um administrador os adicione explicitamente como usuários de exceção.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificações e limitações">

| **Caraterística** | **A descrição** |
| --- | --- |
| Imposição de SSO | O SSO continua sendo aplicado à conta. Os usuários de exceção são exceções controladas no nível do usuário. |
| Métodos alternativos de login compatíveis | Os usuários de exceção podem usar **Nome de usuário & senha** ou **Aplicativo autenticador**. |
| Autenticação por SMS | O SMS não é compatível como método alternativo de login. |
| Permissão necessária | Para gerenciar usuários de exceção, os administradores devem ter a permissão **Segurança de login** definida como **Gerenciar**. |
| Permissão somente para visualização | Administradores com acesso somente para visualização podem ver os usuários de exceção existentes, mas não podem editá-los. |
| Novos usuários após a migração | Os novos usuários devem fazer login por SSO, a menos que um administrador os adicione como usuários de exceção. |

</Accordion>

<div data-zendesk-anchors="about-exception-users=sobre-usu%C3%A1rios-de-exce%C3%A7%C3%A3o h_01KSM9MR6FEJH62VN5BPG7C8C8=sobre-usu%C3%A1rios-de-exce%C3%A7%C3%A3o prerequisites=pr%C3%A9-requisitos h_01KSM9MR6GG6K3JVYEDKKSARH5=pr%C3%A9-requisitos h_01KSM9RZPTBKSBH788FNP1PMDH=add-exception-users-during-sso-setup h_01KSM9RZPT9WGSMX5K10BA9WSY=add-login-methods-for-multiple-users h_01KSM9RZPTXDTM7Y0RV2PVRAX7=edit-exception-users-after-sso-activation h_01KSM9RZPT1G9MJ4BQYTSKPZ0F=delete-exception-users h_01KSM9RZPT3CZR4QGMWAH534H5=alternative-login-methods h_01KSM9RZPTJ988PFQA68DVE73G=handle-partial-activation-failures h_01KSM9RZPVS8AVWAD7EPGCG6F9=reset-passwords-for-sso-accounts h_01KSM9RZPV36BQWH360QSP98SY=migrate-from-legacy-unforce-sso h_01KSMA3KYT6F2FSB2QGDPV4CAM=traits-and-limitations" />

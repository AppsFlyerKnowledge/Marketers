---
title: Configurar a autenticação SSO com o seu fornecedor de identidade (IdP)
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - login security
    - SSO
    - SSO verification
    - SSO certificate
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
  created_at: '2020-11-02T10:50:55Z'
  edited_at: '2026-08-19T00:16:15Z'
  id: 360015017198
  locale: pt
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/pt/articles/360015017198
---
> **Resumo:** Ao integrar a AppsFlyer com o seu provedor de identidade (IdP), os usuários da conta da AppsFlyer podem fazer login na AppsFlyer usando single sign-on (SSO). Aprenda a configurar a autenticação SSO na AppsFlyer e na plataforma do seu IdP.

## Considerações

* **Pré-requisito:** Os usuários devem ser configurados em ambos os sistemas (AppsFlyer e IdP) com o mesmo e-mail.
* As configurações do login SSO só podem ser gerenciadas e removidas por um administrador.
* O SSO é aplicado à conta por padrão.
* Os administradores podem adicionar usuários de exceção que podem fazer login com SSO ou com um método de login alternativo atribuído.
* Os métodos de login alternativos compatíveis para usuários de exceção são:
  * Nome de usuário & senha
  * Aplicativo de autenticação (2FA)
* SMS não tem suporte como método de login alternativo para usuários de exceção.
* Quando nenhum usuário de exceção é adicionado, o SSO é aplicado por padrão a todos os usuários após a ativação.

> 📘 **Atenção**
>
> Recomendamos adicionar pelo menos um administrador confiável como usuário de exceção antes de ativar o SSO. Isso ajuda a evitar o bloqueio da conta se a configuração de SSO estiver incorreta

## Acessar a página de configuração do SSO

1. Na barra superior, abra o menu da conta (menu dropdown de endereço de e-mail) > **Central de segurança**.
2. Em **Segurança de login melhorado**, selecione **Configurar método de login**.
3. Na página **Segurança de login**, clique em **Configurar SSO**.

## Configurar SSO

A configuração do SSO é feita tanto na plataforma do seu IdP quanto na AppsFlyer, conforme descrito nas etapas abaixo. O status da configuração pode estar **Ativo** quando o SSO é configurado ou **Não configurado** quando não há nenhuma configuração ou quando a configuração já foi removida.

> 📘 **Nota**
>
> * Este guia inclui os processos detalhados para os IdPs abaixo e um resumo da configuração geral para todos os outros IdPs. um resumo da configuração geral para todos os outros IdPs.
>   * JumpCloud
>   * Okta
>   * OneLogin
>   * Ping Identity

<div id="step-1-set-up-the-idp-platform" />

<Accordion title="Etapa 1: Configurar a plataforma do seu IdP">

Veja os processos detalhados para configurar a autenticação SSO nos seguintes IdPs:

* <Anchor target="_blank" href="/marketers/pt/docs/configure-appsflyer-sso-in-jumpcloud">JumpCloud</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/configure-appsflyer-sso-in-okta">Okta</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/configure-appsflyer-sso-in-onelogin">OneLogin</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/configure-appsflyer-sso-in-ping-identity">Ping Identity</Anchor>

#### Resumo da configuração para outras plataformas de IdP

Este é processo para configurar outras plataformas de IdP:

* Crie um aplicativo AppsFlyer na plataforma do seu IdP usando o protocolo SAML2.0 e integre o [certificado de autenticação da AppsFlyer](#the-authentication-certificate) na plataforma.
* Atribua usuários ao aplicativo AppsFlyer recém-criado.
* Recupere o certificado ou os metadados do IdP que serão usados na AppsFlyer (conforme mencionado na [Etapa 2: Configure a AppsFlyer --> 5. Forneça os metadados do IdP](#step-5-provide-idp-metadata)).

> 📘 **Nota**
>
> * **Importante!** Ao atribuir usuários ao IdP, certifique-se de que você está usando o mesmo e-mail de usuário que na AppsFlyer, para que cada usuário em ambas as plataformas tenha o mesmo e-mail.
> * <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">Os metadados da AppsFlyer</Anchor> contêm:
>   * Certificados de encriptação e assinatura
>   * ID da entidade
>   * URL de callback

<div id="step-2-set-up-appsflyer" />

<Accordion title="Etapa 2: Configurar a AppsFlyer">

Siga todas as etapas abaixo para configurar a autenticação SSO na AppsFlyer depois de configurá-la na plataforma do seu IdP.

Veja como [acessar a página de configuração do SSO](#acessar-a-página-de-configuração-do-sso).

<div id="step-1-select-authentication-starting-point" />

<Accordion title="1. Selecionar o ponto de partida da autenticação">

1. Selecione a origem de acesso dos usuários na AppsFlyer. Isso também define o processo de autenticação.
   * [Provedor de identidade (IdP)](#provedor-de-identidade-idp)
   * [Provedor de serviços (AppsFlyer)](#provedor-de-serviços-appsflyer)
2. Clique em **Próximo**.

#### Provedor de identidade (IdP)

Os usuários que fazem login por meio do plug-in de autenticação do IdP ou da página da web são direcionados à AppsFlyer após a autenticação.

> 📘 **Nota**
>
> Ao selecionar essa opção, os usuários podem fazer login por meio do IdP e do provedor de serviços (AppsFlyer).

#### Provedor de serviços (AppsFlyer)

Os usuários também podem entrar na AppsFlyer pela <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-callback">página de login SSO da AppsFlyer</Anchor> clicando em **Login com SSO** e inserindo o endereço de e-mail. Eles serão direcionados ao IdP para autenticação e redirecionados para a página inicial da AppsFlyer.

[<Image alt="AppsFlyer_login_page.png" src="https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png" width="257px" />](https://files.readme.io/fb80e44cf0cad29349ec85f75f65de73041b1787b278ae9d96449783580faeaa-17233244722577.png)

> 📘 **Nota**
>
> Ao selecionar essa opção, os usuários podem fazer login somente por meio do provedor de serviços (AppsFlyer) e não diretamente do IdP.

<div id="step-3-select-certificate-type" />

<Accordion title="2. Selecionar o tipo de certificado">

A AppsFlyer oferece dois tipos de certificados de chave de encriptação pública para criptografar dados e assinar a solicitação SSO:

* **Certificado assinado pela AppsFlyer:** um certificado da AppsFlyer criado a partir da <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">URL de metadados da AppsFlyer</Anchor>.
* **Certificado assinado pela CA:** um certificado da AppsFlyer **assinado pela Amazon**.

**Para realizar essa etapa:**

* Selecione o tipo de certificado e clique em **Próximo**.

> 📘 **Nota**
>
> O certificado é ativado somente após ambas as partes completarem o processo de implementação do certificado: a AppsFlyer incorpora a configuração SAML do IdP e o IdP integra os metadados SSO mais recentes da AppsFlyer. Isso é feito nas etapas abaixo.

</Accordion>

<div id="step-4-obtain-service-provider-appsflyer-metadata" />

<Accordion title="3. Obter metadados do provedor de serviços (AppsFlyer)">

1. Copie os metadados SSO mais recentes da AppsFlyer e implemente-os na configuração SAML do seu IdP.
   * Se você selecionou o **certificado assinado pela AppsFlyer:** Copie qualquer um dos campos abaixo.
     * **URL de metadados:** Para IdPs compatíveis com URLs de metadados completos, copie a URL e implemente-a no seu IdP.
     * **Componentes de metadados:** Para IdPs não compatíveis com URLs de metadados completos, copie cada um dos componentes e implemente-os na seção correspondente do seu IdP: **ID da Entidade**, **Chave de encriptação** (disponível para download) e **URL de localização**.
     * **Arquivo XML:** Você tem a opção de baixar os metadados SSO da AppsFlyer como um arquivo XML.
   * Se você selecionou o **certificado assinado pela CA:** Copie os **componentes de metadados**.
2. Clique em **Próximo**.

</Accordion>

<div id="step-5-provide-idp-metadata" />

<Accordion title="4. Fornecer metadados do IdP">

Forneça os metadados SSO do seu IdP usando as opções abaixo e depois valide o formato desses metadados. **Atenção:** Os dados do certificado do seu IdP precisam estar em uma única linha de texto, sem metacaracteres.

1. Selecione o método desejado para fornecer os metadados do seu IdP:
   * **URL:** Insira a URL dos metadados do seu IdP
   * **Arquivo XML:** Faça upload do arquivo XML dos metadados do seu IdP.
2. Clique em **Validar**. Você verá uma mensagem de confirmação na parte superior da página que indica o status da validação.
3. Clique em **Ativar**. Você verá uma mensagem de confirmação na parte superior da página que indica o status da ativação da autenticação SSO.

</Accordion>

<div id="5-add-exception-users" />

<Accordion title="5. Adicionar exceções">

Usuários de exceção são usuários que não precisam fazer login via SSO. O SSO continua sendo aplicado à conta, e somente os usuários adicionados explicitamente como usuários de exceção podem fazer login com um método de login alternativo atribuído.

Adicionar usuários de exceção é opcional. Se você não adicionar usuários de exceção, todos os usuários deverão fazer login por SSO após a ativação.

> 📘 **Atenção**
>
> Adicione pelo menos um administrador confiável como usuário de exceção antes de ativar o SSO. Se a configuração de SSO estiver incorreta, esse usuário poderá fazer login com o método de login alternativo atribuído e atualizar a configuração.

Para adicionar usuários de exceção:

1. Provedor de serviços (metadados da AppsFlyer) — os detalhes estão disponíveis
2. Na caixa de diálogo **Adicionar usuários de exceção**, pesquise um usuário por nome ou e-mail.
3. Selecione o usuário que você quer adicionar.
4. Na lista suspensa **Método de login alternativo**, selecione uma das seguintes opções:
   * **Nome de usuário & senha**
   * **App de autenticação**
5. Repita as etapas de 2 a 4 para cada usuário que você quer adicionar.
6. Selecione como os usuários podem fazer login na AppsFlyer:

### **Adicionar métodos de login para vários usuários**

Para adicionar o mesmo método alternativo de login para vários usuários de exceção:

1. Selecione as caixas de seleção dos usuários que você quer atualizar.
2. Clique em **Definir método de login para os usuários selecionados**.
3. Escolha uma das seguintes opções:
   * **Utilizar nome de usuário e senha para todos os usuários selecionados**
   * **Aplicar aplicativo autenticador a todos os usuários selecionados**

### **Excluir um usuário de exceção**

Para excluir um usuário da lista de usuários de exceção:

* Clique no ícone **Excluir** na linha do usuário.

O usuário é excluído da lista imediatamente.

</Accordion>

<div id="6-activate-sso" />

<Accordion title="6. Ativar SSO">

> 📘 **Atenção**
>
> Antes de ativar o SSO, recomendamos adicionar pelo menos um administrador confiável como usuário de exceção. Isso ajuda a evitar o bloqueio da conta se a configuração do SSO estiver incorreta.

Não é recomendado ativar o SSO e o login com nome de usuário e senha ao mesmo tempo.

1. Vá para qualquer uma das seções e selecione a opção desejada.
2. Na caixa de diálogo **Ativar SSO?** revise suas configurações de SSO.
3. **SSO ou nome de usuário e senha**: os usuários podem optar por fazer login SSO ou com nome de usuário e senha.

Uma configuração incorreta pode bloquear os usuários da AppsFlyer. Revise sua configuração antes de ativar o SSO.

Se nenhum usuário de exceção tiver sido adicionado, a caixa de diálogo de confirmação mostrará uma mensagem informando que todos precisarão fazer login por SSO após a ativação.

### **Resultados da ativação**

| **Resultado** | **Descrição** |
| --- | --- |
| A ativação do SSO é bem-sucedida e os usuários de exceção são adicionados | O SSO está ativo, e os usuários de exceção estão configurados. |
| A ativação do SSO é bem-sucedida, mas alguns usuários de exceção não são adicionados | O SSO permanece ativo. Adicione ou atualize usuários de exceção em **Editar SSO**. |
| A ativação do SSO falha | O SSO não é ativado, e o status da configuração volta para **Não configurado**. |

## **Atenção**

Depois que o SSO estiver ativo, você poderá editar a configuração do SSO e gerenciar usuários de exceção.

O método 2FA não é compatível com SSO.

1. Clique em **Excluir** no ícone de lixeira do lado direito da seção **Single sign-on (SSO) do SAML**.
2. Abra a seção que você quer atualizar.
3. Faça as alterações necessárias.
4. **Forçar SSO** [recomendado]: esse método impõe um login mais seguro.
5. Clique em **Salvar alterações**. Você verá uma mensagem de confirmação que indica o status das alterações.
6. Vá para qualquer uma das seções e selecione a opção desejada.

Ao alterar o tipo de certificado ou o ponto de partida da autenticação, os metadados da AppsFlyer mudam. Copie os metadados mais recentes do provedor de serviços do AppsFlyer e adicione-os à configuração SAML do seu provedor de identidade (IdP) imediatamente após salvar as alterações

### **Editar exceções**

Para editar usuários de exceção:

1. Na página de edição de SSO, abra a seção **Usuários de exceção**.
2. Clique no ícone **Editar** <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="24px" /> do lado direito da seção **Single sign-on (SSO) do SAML**.
3. Na caixa de diálogo **Editar usuários de exceção**, adicione usuários, exclua usuários ou atualize métodos alternativos de login.
4. Clique em **Próximo**.
5. Clique em **Salvar alterações**. Clique em **Salvar alterações**.

Os usuários de exceção adicionados anteriormente aparecem com seu método alternativo de login atual.

</Accordion>

</Accordion>

<div id="step-3-test-the-sso-configuration" />

<Accordion title="Etapa 3: Testar a configuração do SSO">

Depois de concluir a configuração do SSO em ambos os sistemas (AppsFlyer e IdP), verifique se os usuários podem fazer login na AppsFlyer em **qualquer um** dos [métodos de callback de URL](#single-signon-url-configuration): seu IdP ou o provedor de serviços (AppsFlyer), mas não ambos.

#### Teste a autenticação através do seu IdP

Se você tiver configurado a autenticação para fazer login através do seu IdP, verifique se os usuários podem entrar na AppsFlyer a partir do plugin IdP ou da página web:

1. Se você estiver conectado à AppsFlyer e ao IdP, desconecte-se de ambos.
2. Abrir uma página web no modo incógnito.
3. Acesse a página web do seu IdP. Quando você não estiver conectado ao IdP, você passará por um processo de autenticação. Inicie a sessão com o usuário relevante.
4. Pesquise e selecione a AppsFlyer. Você é direcionado para a página inicial da AppsFlyer. Isto indica que o processo foi bem sucedido.

#### Testar a autenticação através do seu provedor de serviços (AppsFlyer)

Se você tiver configurado o fluxo de autenticação para fazer login através do seu provedor de serviço (AppsFlyer), verifique se os usuários podem entrar na AppsFlyer usando o email:

<Image alt="log_in_to_af_by_email2.png" src="https://files.readme.io/ae22ff9ba0216f54bee4cea82ed7d35cea656a68e30c0a0e4f549b1855ec7cfd-17233244746257.png" width="245px" />

1. Se você estiver conectado à AppsFlyer e ao IdP, desconecte-se de ambos.
2. Abrir uma página web no modo incógnito.
3. Vá para a <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">página de login da AppsFlyer</Anchor> e clique em **Login com SSO**.
4. Insira o e-mail relevante e clique em **Continuar**. Agora você é direcionado para o IdP para autenticação.
5. Após a autenticação do IdP, você é direcionado de volta para a AppsFlyer como um usuário conectado. Isso indica que o processo foi bem sucedido.

</Accordion>

</Accordion>

</Accordion>

## Gerenciar a configuração do SSO

Depois de configurar o SSO, você pode editar ou remover a configuração.

Veja como [acessar a página de configuração do SSO](#acessar-a-página-de-configuração-do-sso).

<div id="edit-sso" />

<Accordion title="Editar SSO">

Nessa página, você pode editar qualquer uma das seguintes opções:

* Ponto de partida da autenticação
* Tipo de certificado
* Metadados do provedor de serviços
* Metadados do provedor de identidade
* Usuários de exceção

> 🚧 **Importante!**
>
> Ao alterar o tipo de certificado ou o ponto de partida da autenticação, os metadados da AppsFlyer mudam. É fundamental copiar os metadados SSO mais recentes do provedor de serviços (AppsFlyer) e implementá-los na configuração SAML do seu IdP logo após salvar as alterações.

> 📘 **Atenção**
>
> Adicione pelo menos um administrador confiável como usuário de exceção. Se a configuração de SSO estiver incorreta, esse usuário poderá fazer login com o método alternativo de login atribuído e atualizar a configuração.

Para editar a configuração do SSO:

1. Clique em **Excluir** no ícone de lixeira do lado direito da seção **Single sign-on (SSO) do SAML**.
2. Abra a seção que você deseja atualizar.
3. Faça as alterações necessárias.
4. Clique em **Guardar**.
5. Clique em **Salvar alterações**. Você verá uma mensagem de confirmação que indica o status das alterações.
6. Clique em **Save changes**.

### Editar exceções

Para editar usuários de exceção:

1. Abra a seção **Usuários de exceção**.
2. Clique no ícone **Editar** <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="24px" /> do lado direito da seção **Single sign-on (SSO) do SAML**.
3. Na lista de usuários de **Editar usuários de exceção**, adicione usuários, exclua usuários ou atualize métodos alternativos de login.
4. Clique em **Guardar**.
5. Clique em **Salvar alterações**. Clique em **Salvar alterações**.

Os usuários de exceção adicionados anteriormente aparecem com seu método alternativo de login atual.

</Accordion>

<div id="remove-sso-configuration" />

<Accordion title="Excluir configuração do SSO">

Para excluir a configuração do SSO:

1. Na seção **Single sign-on (SSO) do SAML**, clique no ícone **Excluir**.
2. Na caixa de diálogo de confirmação, revise o impacto de excluir a configuração.
3. Clique em **Excluir**.

Ao remover a configuração do SSO, os metadados SSO do seu IdP armazenados na AppsFlyer serão excluídos.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Nome | Atenção |
| --- | --- |
| Símbolos no endereço de e-mail | O SSO não é compatível com endereços de e-mail que contêm o símbolo de + no nome.<br /><br />Exemplo: my+customer@demo.com<br /><br />Isso resultará em falha no login. |
| Usuários de exceção | Os usuários de exceção devem ser adicionados explicitamente por um administrador. |
| Método de login | Os métodos alternativos de login compatíveis são **Nome de usuário & senha** e **Aplicativo autenticador**. |
| Autenticação por SMS | O SMS não é compatível como método alternativo de login para usuários de exceção. |
| Sem usuários de exceção | Quando a opção **Forçar login SSO** está ativada, todos os usuários devem fazer login com o SSO, e usuários individuais não podem ser excluídos. |
| Authorization: Bearer | Para configurar o SSO e gerenciar usuários de exceção, os administradores devem ter a permissão **Segurança de login** definida como **Gerenciar**. |
| Permissões somente de visualização | Administradores com acesso somente de visualização à **Segurança de login** podem ver a página de SSO, mas não podem editar as configurações de SSO nem os usuários de exceção. |
| Migração legada para desativar a obrigatoriedade do SSO | Para contas migradas do recurso legada de desativar a obrigatoriedade do SSO no nível da conta, os usuários existentes de nome de usuário/senha são adicionados como usuários de exceção. Novos usuários devem fazer login por SSO, a menos que um administrador os adicione explicitamente como usuários de exceção. |
| Usuário de exceção recomendado | Recomendamos adicionar pelo menos um administrador confiável como usuário de exceção antes de ativar o SSO. Isso ajuda a evitar o bloqueio da conta se a configuração de SSO estiver incorreta. |

</Accordion>

> 📄 **Veja também**
>
> <Anchor target="_blank" href="/marketers/pt/docs/sso-authentication-overview-and-faq">Saiba mais sobre a autenticação SSO e tire suas dúvidas com as perguntas frequentes</Anchor>
>
> <Anchor target="_blank" href="/marketers/pt/docs/manage-exception-users-for-sso">Saiba mais sobre como gerenciar usuários de exceção para SSO</Anchor>

<div data-zendesk-anchors="considerations=considera%C3%A7%C3%B5es h_01J7KK52TX8WGA3EK110R9M0GY=considera%C3%A7%C3%B5es h_01KSM8FMC9SCPBY2P56QPD6WJ2=aten%C3%A7%C3%A3o access-the-sso-configuration-page=acessar-a-p%C3%A1gina-de-configura%C3%A7%C3%A3o-do-sso h_01J7X4Y5Y50EFAPVP6JY8WAMKN=acessar-a-p%C3%A1gina-de-configura%C3%A7%C3%A3o-do-sso setting-up-sso-authentication=configurar-sso h_01HCHG901V25TSRGRT9244384D=configurar-sso h_01J530X1930CMCF7XJM1XKPC74=nota 01J530ZP34SQKHM5324DNFA25Y=step-1-set-up-the-idp-platform configuration-overview-for-other-idp-platforms=resumo-da-configura%C3%A7%C3%A3o-para-outras-plataformas-de-idp h_01HCHG901VPG0ZJ20XJBFPY7CD=resumo-da-configura%C3%A7%C3%A3o-para-outras-plataformas-de-idp h_01HCHG901VH2XZS9Q0KM9D26WX=nota-1 h_01J5303SNTEVQNA4KZEMS2VG04=step-2-set-up-appsflyer h_01J4PGJ2T73313B1X6ECQ17S7Q=step-1-select-authentication-starting-point identity-provider-idp=provedor-de-identidade-idp h_01J4PHJ8FECGSAGQJGWREX3PKK=provedor-de-identidade-idp h_01J4PHSVS55G2M00S00KG06BB7=nota-2 service-provider-appsflyer=provedor-de-servi%C3%A7os-appsflyer h_01J4PHTR1E9JV3SM0A7N4X3WJY=provedor-de-servi%C3%A7os-appsflyer h_01J4PJEQTBJ9P2SZBKGPF2696S=nota-3 h_01J4PGJ2T76F7YTK42VBW8J1P6=step-3-select-certificate-type h_01J8CEE2BZN0THJ7DNSGRCGJNQ=nota-4 h_01J4PGJ2T76PKE0V7NS7YXC4T5=step-4-obtain-service-provider-appsflyer-metadata h_01J4PGJ2T7SM8EGYZCW6D7AQN8=step-5-provide-idp-metadata h_01KSM7TN32SDETTPJRX5WPR707=5-add-exception-users h_01KSM8FMC91SDE8JQS12J7WXAG=aten%C3%A7%C3%A3o-4 add-login-methods-for-multiple-users=adicionar-m%C3%A9todos-de-login-para-v%C3%A1rios-usu%C3%A1rios h_01KSM7WDKE0PGCMFC6JCKTC107=adicionar-m%C3%A9todos-de-login-para-v%C3%A1rios-usu%C3%A1rios delete-an-exception-user=excluir-um-usu%C3%A1rio-de-exce%C3%A7%C3%A3o h_01KSM7WDKFBFDN7TQVK4YWH3FR=excluir-um-usu%C3%A1rio-de-exce%C3%A7%C3%A3o h_01KSM7TN324FN2QS5W6XBY91ES=6-activate-sso h_01KSM8H456C2SFE9E21HNAWFQM=aten%C3%A7%C3%A3o-2 activation-results=resultados-da-ativa%C3%A7%C3%A3o h_01KSM7YKYJ22W6TM1Q2EQGAAZ9=resultados-da-ativa%C3%A7%C3%A3o edit-sso::496a151=aten%C3%A7%C3%A3o-3 h_01KSM7YKYPNA5MZKMZH7K5R09S=aten%C3%A7%C3%A3o-3 edit-exception-users=editar-exce%C3%A7%C3%B5es h_01KSM7YKYSVF5ZSMSYK5HPQJQ0=editar-exce%C3%A7%C3%B5es h_01J5303SNTYMDMP2DW4GQCGEHK=step-3-test-the-sso-configuration testing-authentication-via-the-idp=teste-a-autentica%C3%A7%C3%A3o-atrav%C3%A9s-do-seu-idp h_01HCHG901WXSQ2VPCH2NKE63SE=teste-a-autentica%C3%A7%C3%A3o-atrav%C3%A9s-do-seu-idp testing-authentication-via-appsflyer=testar-a-autentica%C3%A7%C3%A3o-atrav%C3%A9s-do-seu-provedor-de-servi%C3%A7os-appsflyer h_01HCHG901W6DJ3GN6E7WFR6RNK=testar-a-autentica%C3%A7%C3%A3o-atrav%C3%A9s-do-seu-provedor-de-servi%C3%A7os-appsflyer manage-sso-configuration=gerenciar-a-configura%C3%A7%C3%A3o-do-sso h_01J7WKPGTNPF10N4XMJG9ZDN87=gerenciar-a-configura%C3%A7%C3%A3o-do-sso h_01J7X4P6B18HXJB99JYTVSC75N=edit-sso h_01KSMFXHV6501KFVD9SCCMJCF9=importante h_01KSMFXHV6NJ4PKQ5117HB5B4H=aten%C3%A7%C3%A3o-4 edit-exception-users::6da5a820=editar-exce%C3%A7%C3%B5es-1 h_01KSMFSP2QXYEQWB2CM4YHTTS0=editar-exce%C3%A7%C3%B5es-1 h_01J7X4P6B1THTVR1M966JS4P99=remove-sso-configuration h_01K44S4WP3N8HG872PQX1CCES8=traits-and-limitations h_01HDPF69BTMRYR6E6VNMFR4JY4=veja-tamb%C3%A9m" />

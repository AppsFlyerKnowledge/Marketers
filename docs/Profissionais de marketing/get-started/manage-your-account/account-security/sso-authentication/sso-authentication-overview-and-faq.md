---
title: Autenticação SSO — visão geral e perguntas frequentes
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
  created_at: '2024-08-11T07:54:46Z'
  edited_at: '2026-08-18T00:17:03Z'
  id: 27434547337617
  locale: pt
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/pt/articles/27434547337617
---
> **Em resumo:** Saiba mais sobre a autenticação de single sign-on (SSO) e o processo de fazer login no AppsFlyer com o seu provedor de identidade (IdP) usando SSO. Encontre respostas para perguntas frequentes sobre login SSO.

## O que é a autenticação SSO?

O SSO é um método de autenticação que permite aos usuários acessar vários aplicativos, sistemas ou plataformas independentes, iniciando sessão uma vez através do seu fornecedor de identidade (por exemplo, Okta, Azure AD ou OneLogin). Adicionar a AppsFlyer ao seu IdP permite que seus usuários façam login na AppsFlyer diretamente do seu IdP através de um processo de login único (SSO). Isso permite que os seus usuários iniciem sessão automaticamente com uma **autenticação mais segura** usando apenas um conjunto de credenciais.

## Como é que a autenticação SSO funciona?

A plataforma da AppsFlyer é compatível com a verificação SSO usando o protocolo SAML2.0. Ao implementar o certificado de autenticação da AppsFlyer em seu IdP SAML 2.0, seu IdP gera um token com dados de usuário autenticados. O mesmo processo é feito do seu IdP para a AppsFlyer - seu token é implementado na AppsFlyer.

## O certificado de autenticação da AppsFlyer (provedor de serviços)

A AppsFlyer fornece um certificado de criptografia para criptografar dados e assinar o pedido de SSO. Você pode escolher qual certificado usar:

* **Certificado assinado pela AppsFlyer:** um certificado da AppsFlyer criado a partir da <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">URL de metadados da AppsFlyer</Anchor>
* **Certificado assinado por CA:** um certificado da AppsFlyer **assinado pela Amazon**.

> 📘 **Atenção**
>
> A AppsFlyer não oferece suporte a números de série negativos no certificado.

## Solução de problemas e perguntas frequentes

<div id="can-users-log-in-using-both-sso-and-2fa-methods" />

<Accordion title="Os usuários podem iniciar sessão usando os métodos SSO e 2FA?">

Só pode ser usado um método de login de segurança de cada vez, SSO ou 2FA.

* **Para ativar o método 2FA quando o SSO estiver ativo:** primeiro desative o SSO e depois ative o 2FA
* **Para ativar o método SSO quando o 2FA estiver ativo:** primeiro desative o 2FA e depois ative o SSO

</Accordion>

<div id="why-cant-some-users-connect-using-sso" />

<Accordion title="Por que alguns usuários não conseguem se conectar usando o SSO?">

Certifique-se de que todos os e-mails do usuário estejam configurados em ambos os sistemas - no seu IdP e na plataforma da AppsFlyer. Se não for esse o motivo, entre em contato com o seu CSM para descobrir o motivo e a forma de resolvê-lo. Entretanto, o seu CSM pode desativar temporariamente a opção **Forçar login SSO** para que os usuários possam fazer login usando seu e-mail e senha.

</Accordion>

<div id="do-i-need-a-test-environment-to-test-setup-before-pushing-to-production" />

<Accordion title="Preciso de um ambiente de teste para testar a instalação antes de definir a configuração?">

Não é necessário um ambiente de teste. Siga as etapas na Etapa 3 para testar o login SSO, seja pelo IdP ou pelo lado do provedor de serviços (AppsFlyer).

</Accordion>

<div id="what-should-i-do-before-the-appsflyer-certificate-expires" />

<Accordion title="O que devo fazer antes de o certificado da AppsFlyer expirar?">

A AppsFlyer avisará você através da plataforma quando seu certificado SSO da AppsFlyer estiver prestes a expirar. Siga estas etapas para implementar o novo certificado da AppsFlyer:

1. [Crie um novo arquivo de certificado com a chave de criptografia atualizada](#how-to-create-the-appsflyer-certificate-file).
2. Acesse seu IdP e implemente o novo certificado da AppsFlyer:
3. Após a implementação, volte para a seção **Single sign-on (SSO)** , clique em **Confirmar implementação do certificado**, e confirme que você atualizou o certificado mais recente da AppsFlyer.

</Accordion>

<div id="how-can-i-unselect-the-force-sso-login-option" />

<Accordion title="A opção Forçar login SSO está desativada, como posso ativá-la?">

Quando a opção **Forçar login SSO** é selecionada e a configuração é salva, essa opção fica desativada. Para reverter e ativar **Forçar login SSO**, você precisará reconfigurar a <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">Etapa 2</Anchor> do processo de SSO desde o início.

> 📘 **Observação:**
>
> Manter **Forçar login SSO** selecionado é o método recomendado para impor um login mais seguro. Isto significa que os usuários que tentam iniciar sessão são autenticados pelo IdP e não podem iniciar sessão com o seu nome de usuário e senha.

</Accordion>

<div id="is-it-required-to-use-the-appsflyer-certificate-in-my-idp" />

<Accordion title="É necessário usar o certificado da AppsFlyer no meu IdP?">

Implementar o certificado da AppsFlyer no seu IdP é **fortemente recomendado**, mas não é obrigatório. Alguns IdPs, como o Google Workspace e o Microsoft Entra ID, não requerem, por padrão, um certificado de provedor de serviços.

</Accordion>

<div id="what-happens-when-i-deactivate-sso-and-how-do-i-do-it" />

<Accordion title="O que acontece quando eu desativo o SSO e como faço isso?">

Ao desativar a autenticação SSO, os usuários poderão fazer login usando outros métodos, como seus nomes de usuário e senhas da AppsFlyer e o método <Anchor target="_blank" href="/marketers/pt/docs/implementing-and-using-2fa-login">2FA</Anchor>.

1. Na barra superior, abra o menu da conta (menu dropdown de endereço de e-mail) > **Central de segurança**.
2. Em **Segurança de login melhorado**, selecione **Configurar método de login**.
3. Na seção **Single sign-on (SSO)**, desative o botão de alternância **Single sign-on**.

</Accordion>

<div id="can-i-have-negative-serial-numbers-in-the-certificate" />

<Accordion title="Posso ter números de série negativos no certificado?">

Sem. A AppsFlyer não oferece suporte a números de série negativos no certificado.

</Accordion>

<div data-zendesk-anchors="what-is-sso=o-que-%C3%A9-a-autentica%C3%A7%C3%A3o-sso h_01J5QR4DE5EBSVWHXXENZTRPWQ=o-que-%C3%A9-a-autentica%C3%A7%C3%A3o-sso how-does-sso-authentication-work=como-%C3%A9-que-a-autentica%C3%A7%C3%A3o-sso-funciona h_01HCHG901WVRX1MKNB0KF02PSJ=como-%C3%A9-que-a-autentica%C3%A7%C3%A3o-sso-funciona the-authentication-certificate=o-certificado-de-autentica%C3%A7%C3%A3o-da-appsflyer-provedor-de-servi%C3%A7os h_01HCHG901WG05TP2NJBJRDRWPN=o-certificado-de-autentica%C3%A7%C3%A3o-da-appsflyer-provedor-de-servi%C3%A7os h_01JJH8DC3AHNC6GST0S41X8MFV=aten%C3%A7%C3%A3o faq=solu%C3%A7%C3%A3o-de-problemas-e-perguntas-frequentes h_01HCHG901XSAQ7HSGM0ZVT7B70=solu%C3%A7%C3%A3o-de-problemas-e-perguntas-frequentes h_01HCHG901XJ77NQFVX01YZPGT2=can-users-log-in-using-both-sso-and-2fa-methods h_01HCHG901XH0ED40MK2YM1NGRP=why-cant-some-users-connect-using-sso h_01HCHG901X942E0WCBC00KRFSE=do-i-need-a-test-environment-to-test-setup-before-pushing-to-production h_01HCHG901XNNT8GA3TSP5XJC3B=what-should-i-do-before-the-appsflyer-certificate-expires h_01HCHG901XSKPTTRECJPNA09XR=how-can-i-unselect-the-force-sso-login-option h_01HCHG901XPKMP7HSJ04PY9KHW=observa%C3%A7%C3%A3o h_01HYDBV18S924FNRCBSPR56CTR=is-it-required-to-use-the-appsflyer-certificate-in-my-idp h_01J5QRR54JNC5YNZHQ463KS7BS=what-happens-when-i-deactivate-sso-and-how-do-i-do-it h_01JJH8F3VFTQA1AANNNS85YBF8=can-i-have-negative-serial-numbers-in-the-certificate" />

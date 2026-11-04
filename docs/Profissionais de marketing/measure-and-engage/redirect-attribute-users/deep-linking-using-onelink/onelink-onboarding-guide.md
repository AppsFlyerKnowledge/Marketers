---
title: Guia de integração do OneLink
metadata:
  keywords:
    - Marketers
    - set up
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-08-21T11:48:39Z'
  edited_at: '2026-08-18T00:34:57Z'
  id: 27699299657617
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/27699299657617
---
> **Visão geral**: Use o OneLink para redirecionar usuários, ativar o deep linking e fazer a atribuição das suas campanhas, independentemente do dispositivo do usuário, sistema operacional, canal ou plataforma, garantindo o máximo de conversão e receita para o seu negócio.

## ![53010_Onelink.jpg](https://files.readme.io/c0d24ab87126bf765a89a25077b07d8678159cdb6f1b68eddc14a4cd2759b12a-30192941047185.jpg)

<div id="about-onelink" />

## Sobre o OneLink

O <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor> da AppsFlyer permite que você crie links para as suas campanhas, oferecendo recursos de atribuição, redirecionamento e deep linking que impulsionam a conversão de visitantes casuais em usuários do seu aplicativo. Além disso, ele permite que você engaje usuários através de experiências contextuais relevantes, independentemente do dispositivo, sistema operacional, canal ou plataforma de onde eles vieram. Use o OneLink para criar jornadas contextuais e personalizadas que levam os usuários ao seu app e impulsione suas taxas de conversão e receitas. As experiências personalizadas que você pode criar incluem:

* **Social-to-app**: **engaje seus usuários nas redes sociais e envie-os das suas publicações para o seu app.**
* **App-to-app**: conduza os usuários ao seu aplicativo de dentro de outros aplicativos.
* <Anchor target="_blank" href="/marketers/pt/docs/convert-your-mobile-web-visitors-to-app-users">Web-to-app</Anchor>: converta os visitantes do seu site mobile em novos usuários de aplicativos mobile usando Smart Banners ou Smart Script. **Inclui funcionalidades pagas**
* QR-to-app: use QR codes para impulsionar instalações de aplicativos, fazendo com que os usuários escaneiem um QR code em pontos importantes durante a experiência offline. Você também pode colocar QR codes em seu site para desktop ou em anúncios de TV e CTV para direcionar os usuários ao seu aplicativo.
* Email-to-app: use provedores de serviços de e-mail (ESPs) para engajar os usuários por e-mail e enviá-los da caixa de entrada para o seu app. **Inclui funcionalidades pagas**
* Text-to-app: crie links para as suas campanhas de SMS e mensagens e engaje seus usuários por meio de mensagens de texto.
* **Referral-to-app**: crie links que permitam que usuários ou influenciadores convidem outras pessoas para seu aplicativo ou compartilhem um conteúdo específico no aplicativo como, por exemplo, um artigo. **Inclui funcionalidades pagas**
* **Personalizado**: crie uma experiência personalizada com uma infinidade de opções para máxima personalização. Independentemente do canal de onde os seus usuários venham, seja via desktop ou celular, online ou offline, mídia própria ou paga, use o OneLink para enviá-los diretamente para o destino certo.

**Observação:** Embora a configuração básica do OneLink esteja disponível nos planos gratuitos, a maioria das funcionalidades exige um plano de assinatura pago da AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/account-management-plans-payments-and-billing#appsflyer-plans">subscription plan</Anchor>.

<div id="onelink-onboarding" />

## Integração do OneLink

**Para começar a usar o OneLink, siga os passos abaixo:**

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**Pré-requisitos**

* Uma <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">conta</Anchor> na AppsFlyer com pelo menos um aplicativo adicionado.
* A maioria das funcionalidades requer um <Anchor target="_blank" href="/marketers/pt/docs/account-management-plans-payments-and-billing#appsflyer-plans">plano de assinatura</Anchor> pago da AppsFlyer. Para obter ajuda, entre em contato com [hello@appsflyer.com](mailto:hello@appslfyer.com)
* Para configurar o OneLink, você deve ser um usuário administrador na AppsFlyer ou ter <Anchor target="_blank" href="/marketers/pt/docs/user-management">permissões</Anchor> para adicionar/editar templates do OneLink.
* O <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-appsflyer-sdk">SDK da AppsFlyer</Anchor> deve estar instalado nos seus aplicativos mobile para atribuir instalações, eventos in-app e deep linking.
  * Se o SDK ainda não estiver instalado nos seus apps, ainda é possível criar um link de redirecionamento funcional, mas sem atribuição.

| Função | Objetivo | Ações necessárias | Quem está envolvido |
| --- | --- | --- | --- |
| 1. Criar um template do OneLink | Um template do OneLink é a base necessária da lógica de redirecionamento para os links que você criará. | <ul><li>Profissional de marketing/gerente de produto: Configurar um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">template do OneLink</Anchor> na AppsFlyer.</li><li>Desenvolvedor Android: Configurar métodos de abertura para usuários existentes (Android App Links e esquema URI).</li><li>Desenvolvedor iOS: Configurar métodos de abertura para usuários existentes (iOS Universal Links e esquema URI).</li></ul><Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">Instruções para desenvolvedores</Anchor> | Profissional de marketing e desenvolvedor |
| 2. Criar um link do OneLink | Crie um link do OneLink a partir do seu template recém-criado, que será usado na sua campanha. | <ul><li>Profissional de marketing/gerente de produto: Configurar um <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">link do OneLink</Anchor> na AppsFlyer. Lembre-se de selecionar da experiência que deve ser oferecida ao cliente e adicione qualquer parâmetro de atribuição e de deep linking.</li><li>Desenvolvedores Android e iOS: Configurar <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking</Anchor> (caso seja necessário).</li></ul> | Profissional de marketing e desenvolvedor |
| 3. Configurar a domain redirect allowlist | Por segurança, os links na AppsFlyer redirecionam apenas para URLs cujos domínios estão na sua lista de permissões. | Certifique-se de que a sua <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">redirect allowlist de domínio</Anchor> está atualizada com todos os domínios para os quais você deseja redirecionar os usuários. | Marketer |
| 4. Teste o novo link | Verifique se o link redireciona com sucesso:<ul><li>Novos usuários sem seu aplicativo instalado</li><li>Usuários existentes com seu aplicativo instalado</li></ul> | <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">Teste</Anchor> o link recém-criado. | Marketer |
| 5. Use o link na sua campanha e avalie os resultados |  | <ol><li>Adicione o novo link à sua campanha e compartilhe-o com a sua audiência.</li><li>Consulte os resultados da sua campanha no dashboard Overview da AppsFlyer (filtre por campanha).</li></ol>Parabéns! Você concluiu a integração com o OneLink. | Profissional de marketing, analista de dados |
| **Funcionalidades opcionais** |  | Agora que está tudo configurado, você pode explorar e descobrir funcionalidades adicionais do OneLink, como:<ul><li>Web-to-app: Transforme usuários da web em usuários do app e mensure os funis web-to-app.</li><li><Anchor target="_blank" href="/marketers/pt/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/perform-onelink-bulk-actions-via-csv">criação de links em massa</Anchor>: Amplie e conduza múltiplas campanhas simultaneamente e crie milhares de links do OneLink de forma rápida e fácil.<br />*A OneLink API requer uma assinatura Enterprise.</li><li>Exportar URLs do OneLink: Baixe as URLs do OneLink criados na AppsFlyer.</li><li><Anchor target="_blank" href="/marketers/pt/docs/user-invite-attribution">Atribuição de convite de usuário</Anchor> - Crie engajamento integrando links de convite de usuário criados diretamente no aplicativo.</li><li><Anchor target="_blank" href="/marketers/pt/docs/cross-promotion-attribution-for-marketers">Atribuição de cross-promotion</Anchor>: os usuários existentes do seu aplicativo são excelentes candidatos para instalar seus novos aplicativos. Descubra como usar os métodos do SDK para criar e mensurar campanhas de promoção cruzada.</li><li><Anchor target="_blank" href="/marketers/pt/docs/understand-onelink-short-vs-long-urls">URLs longas</Anchor>: adicione parâmetros aos links personalizados do OneLink ou <Anchor target="_blank" href="/marketers/pt/docs/understand-onelink-short-vs-long-urls">gere um grande número de links personalizados do OneLink</Anchor> aplicando suas próprias fórmulas simples em uma planilha.</li></ul>**Observação:** A maioria das funcionalidades requer um <Anchor target="_blank" href="/marketers/pt/docs/account-management-plans-payments-and-billing#appsflyer-plans">plano de assinatura</Anchor> pago da AppsFlyer. | Profissional de marketing e desenvolvedor |

Se precisar de ajuda para começar a usar o OneLink, fale com o seu representante de vendas ou escreva para [hello@appsflyer.com](mailto:hello@appsflyer.com)

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Atribuição de mídia própria no Safari do iPad | Quando os usuários clicam em links de mídia própria em um iPad usando o navegador Safari, o navegador pode relatar um **Macintosh-like user agent** em vez de um modelo de dispositivo iPad. Como resultado, a AppsFlyer identifica o clique como originado de um dispositivo Mac, enquanto a instalação do aplicativo é identificada como originada de um iPad. Como a atribuição probabilística depende da correspondência das características do dispositivo entre o clique e a instalação, essa incompatibilidade impede a atribuição e pode resultar em instalações não atribuídas ou falhas no deferred deep linking. Essa limitação se aplica apenas ao tráfego de mídia própria em dispositivos iPad usando o Safari. |

<div data-zendesk-anchors="overview=sobre-o-onelink h_01J2G7RMHSPPXCWJ60W9HZASXX=sobre-o-onelink h_01HKHGX9JJQQCKF9SDZRSCM1XJ=sobre-o-onelink xyz-onboarding=integra%C3%A7%C3%A3o-do-onelink h_01J2RJFH0B4R815CWDQNEB2C1P=integra%C3%A7%C3%A3o-do-onelink traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KFAG3N0X0W0RCJXK00KX038E=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />

---
title: Redirecionar para páginas de produtos personalizadas
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - OneLink
  created_at: '2021-08-26T07:25:53Z'
  edited_at: '2026-08-18T00:35:50Z'
  id: 4406217556625
  locale: pt
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/pt/articles/4406217556625
---
> **Visão geral:** redirecione os usuários do iOS para as páginas de produtos personalizadas do seu aplicativo na App Store. Use os dados da AppsFlyer sobre as páginas de produtos personalizadas para otimizar suas campanhas.

<div id="overview" />

## Visão geral

Com o lançamento do iOS 15, a Apple introduziu páginas de produtos personalizadas, que permitem que os proprietários de aplicativos criem até 35 versões adicionais de sua página de produtos do Google Play e da App Store que mostram diferentes recursos ou conteúdo em seu aplicativo. As páginas de produtos personalizadas podem exibir texto promocional, capturas de tela e prévias diferentes daquelas exibidas na página de produto padrão da App Store.

Para o Google Play, você pode criar até 50 páginas personalizadas. Para a App Store, você pode criar até 35.

Você pode usar URLs do OneLink da AppsFlyer ou links de atribuição de plataforma única para redirecionar os usuários para essas páginas de produtos personalizadas e criar jornadas contextuais distintas para diferentes audiências.

Os dados referentes às páginas de produtos personalizadas estão disponíveis no painel da AppsFlyer e nos relatórios de dados brutos, conforme descrito na seção a seguir. Você pode usar os dados para fazer testes A/B e otimizar suas campanhas e páginas de produtos.

<div id="data-availability" />

## Disponibilidade de dados

<div id="dashboard" />

<Accordion title="Painel">

Os dados agregados para páginas de produtos personalizadas da App Store estão disponíveis no painel de Visão geral. Para listagens de loja personalizadas do Google Play, a disponibilidade será adicionada em breve.

**Para visualizar os dados**:

* No painel de visão geral, adicione a dimensão do agrupamento **Página do produto da loja**.  
  A página de produto personalizada é exibida nos gráficos e tabelas do dashboard.

</Accordion>

<div id="raw-data" />

<Accordion title="Dados brutos">

Os dados brutos estão disponíveis por meio das <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">ferramentas de relatório da AppsFlyer</Anchor>.

Nos relatórios, o campo `store_product_page` indica para qual página personalizada um determinado usuário foi redirecionado.

</Accordion>

<div id="setup" />

## Configuração

<div id="google-play" />

<Accordion title="Google Play">

Para configurar redirecionamentos para uma listagem de loja personalizada no Google Play, você pode:

* Usar a interface do usuário do OneLink.
* Adicionar o parâmetro `af_android_store_csl` às suas URLs do OneLink ou links de atribuição de plataforma única com o valor sendo o ID da página personalizada do produto. Por exemplo: `af_android_store_csl=abc123`

<span id="use-the-onelink-ui-google-play"></span>**Observação:** Devido a alterações do sistema em alguns navegadores, incluindo o Google Chrome, usar o redirecionamento de listagem personalizada da loja pode levar a uma versão web da loja Google Play com a visualização de listagem personalizada da loja (em vez da versão do aplicativo).

<div id="use-the-onelink-uigoogle-play" />

#### Use a IU do OneLink — Google Play

Pré-requisitos:

* Listagem de loja personalizada criada no Google Console.  
  **Observação**: no Google Console, a listagem personalizada deve ser definida por meio de um parâmetro de URL exclusivo.
* <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Modelo do OneLink</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">Link personalizado do OneLink</Anchor>

**Para adicionar um redirecionamento para uma listagem de loja personalizada a um link personalizado do OneLink**:

1. No link personalizado do OneLink, vá para a seção **Deep linking e redirecionamentos.**
2. Vá até as configurações **Quando o aplicativo não está instalado**.  
   <Image align="center" alt="android_cpp.png" src="https://files.readme.io/d354feb4d47171b14f0612011b7a52b579bd9062a87544095df226ba58c57ec6-11591784334865.png" />
3. Para Android, certifique-se de que **Redirecionar para** está definido como Google Play.
4. Na caixa de texto **Listagem de loja personalizada**, insira o valor que você definiu para o parâmetro de URL exclusivo da listagem no Google Console. Por exemplo: abc123
5. Clique em **Atualizar link**.
6. [Recomendado] Teste o link em diferentes navegadores Android para garantir que funcione conforme o esperado.

</Accordion>

<div id="app-store" />

<Accordion title="Loja de aplicativos">

Para configurar redirecionamentos para uma página de produto personalizada na App Store, você pode:

* Usar a interface do usuário do OneLink.
* Adicionar o parâmetro `af_ios_store_cpp` às suas URLs do OneLink ou links de atribuição de plataforma única com o valor sendo o ID da página personalizada do produto. Por exemplo: `af_ios_store_cpp=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

<div id="use-the-onelink-uiapp-store" />

#### Use a IU do OneLink — App Store

Pré-requisitos:

* Página de produto personalizada criada no App Store Connect
* <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Modelo do OneLink</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">Link personalizado do OneLink</Anchor>

**Para adicionar um redirecionamento para uma página de produto personalizada a um link personalizado do OneLink**:

1. No link personalizado do OneLink, vá para a seção **Deep linking e redirecionamentos.**
2. Vá até as configurações **Quando o aplicativo não está instalado**.  
   <Image align="center" alt="ios_cpp.png" src="https://files.readme.io/76f6b46644efc478dc27cb373b3de4a4a80600936db5d7e6725fdb4b9182f6bb-11591824202641.png" />
3. Para iOS, certifique-se de que **Redirecionar para** está definido como App Store.
4. Na caixa de texto **Página de produto personalizada**, insira a ID da sua página de produto personalizada (ppid), conforme definido no App Store Connect. Por exemplo: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
5. Clique em **Atualizar link**.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Navegadores | <ul><li>As listagens de lojas personalizadas do Google Play não são compatíveis com o Naver Blog.</li></ul> |

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01J851YT6WHWEA6RTBFP1S9FT8=vis%C3%A3o-geral data-availability=disponibilidade-de-dados h_01J851YT6XG2A6VETQ3XSNZWVX=disponibilidade-de-dados h_01J851YT6XXTZVMPQFK4YDMACC=dashboard h_01J851YT6XHR6Y3KB30AMMGZXS=raw-data setup=configura%C3%A7%C3%A3o h_01J851YT6XWVEMRG9R5DYKJ70N=configura%C3%A7%C3%A3o h_01J851YT6X21X787WNDFGAW5EZ=google-play use-the-onelink-ui%E2%80%94google-play=use-the-onelink-ui-google-play h_01J851YT6XSVG70DX841NKVGDY=use-a-iu-do-onelink--google-play h_01J851YT6XYQG2FGWBEPAJ686X=app-store use-the-onelink-ui%E2%80%94app-store=use-a-iu-do-onelink--app-store h_01J851YT6XJ9NBK5KKHV1Y07M4=use-a-iu-do-onelink--app-store h_01J851YT6XE6P2FDE9KEMH9SYN=traits-and-limitations" />

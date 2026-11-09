---
title: Conversão QR-to-app
metadata:
  keywords:
    - OneLink
    - Advertisers
    - owned media
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2020-11-04T09:49:23Z'
  edited_at: '2026-08-19T00:34:17Z'
  id: 360015119718
  locale: pt
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/pt/articles/360015119718
---
> **Visão geral:** converta usuários de desktop, TV, CTV ou usuários offline em clientes ativos do seu aplicativo mobile, usando QR codes criados com o OneLink.

<Image align="center" alt="6005_QR_code_4.jpg" src="https://files.readme.io/6db45d7e82bc33ba8af8c6e7d096011d71b06766da9df348dccfa1b3e4aa380d-12368835107601.jpg" />

<div id="converting-mobile-non-mobile-and-offline-traffic-into-mobile-app-users" />

## Como converter seu tráfego offline, mobile, e de outros dispositivos em usuários ativos do seu app

O uso de QR codes criados pelo OneLink em seus anúncios de desktop, TV, CTV e offline (como panfletos, cartazes e embalagens) traz as seguintes vantagens:

* Os usuários podem escanear um QR code com um dispositivo mobile para instalar seu aplicativo.
* Os clientes economizam tempo e esforço necessários para acessar uma loja de aplicativos e pesquisar pelo seu app. Assim, suas taxas de conversão de instalação QR-to-app aumentam consideravelmente.
* Aumento na proteção da privacidade - como esse método não necessita do uso de SMS, os usuários não precisam fornecer informações pessoais, como seu número de telefone.
* Você pode atribuir e mensurar rapidamente a eficácia dos seus anúncios.

QR codes podem ser criados das seguintes maneiras:

* [Manualmente, em sua interface do usuário da AppsFlyer.](/docs/qr-to-app-conversion#configuração-manual-de-qr-codes)
* [Dinamicamente, usando o OneLink Smart Script](/docs/qr-to-app-conversion#dynamic-qr-code-setup) (especificamente desenvolvido para fluxos web-to-app no desktop)

<div id="qr-to-app-conversion" />

<Accordion title="Configuração de conversões QR-to-app">

<div id="manual-qr-code-setup" />

#### Configuração manual de QR codes

**Pré-requisitos:**

* Uma conta da AppsFlyer com pelo menos um aplicativo.
* Para atribuição: <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-appsflyer-sdk">O SDK da AppsFlyer, que já está integrado</Anchor> a cada um dos seus aplicativos mobile.
  * Se o nosso SDK não estiver instalado em seus apps, você ainda poderá criar um link de redirecionamento funcional. No entanto, não será possível realizar deep linking, deferred deep linking ou mensurar instalações em seu dashboard.

* Configuração de um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor>.

**Para configurar um QR code para conversões QR-to-app**:

1. **Para testar seu QR code**:
   * <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">Crie uma imagem única de QR code</Anchor>
     1. [Recomendado] Crie um novo link e configure o canal de mídia personalizado. Por exemplo: **desktop\_web**.  
         Você pode usar um QR code de um link já existente. No entanto, para fins de relatório, recomendamos que você não use um mesmo canal de mídia em outros links. O ideal é usar um canal de mídia para um único link específico.
     2. Depois de clicar em **gerar link**, o QR code é exibido.
     3. Clique no QR code para baixá-lo em resolução máxima, nos formatos SVG ou PNG.
   * <Anchor target="_blank" href="/marketers/pt/docs/perform-onelink-bulk-actions-via-csv#downloading-a-collection-of-qr-codes">Crie um link personalizado do OneLink.</Anchor>
     1. Na página **Bulk Links**, crie uma coleção de links.
     2. Faça o download das imagens de QR code dos links na coleção.
2. Adicione o QR code ao seu anúncio, assim como você adicionaria outras imagens/conteúdos.
   * Veja as [práticas recomendadas](/docs/qr-to-app-conversion#best-practices).
   * Pode ser necessária a ajuda de um desenvolvedor.

</Accordion>

<div id="customize-qr-code" />

<Accordion title="Personalizar código QR">

<Image align="center" alt="OnelinkQRFinal__1_.gif" src="https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif" />

Você pode personalizar os códigos QR gerados via OneLink ao:

* Adicionar seu logotipo ao código QR
* Mudar a cor do código QR.

Observação:

* A personalização de QR codes é feita no nível do template; não no nível do link individual. Portanto, as personalizações afetam todos os QR codes feitos com base no template editado.
* QR codes criados através do Smart Script não podem ser personalizados.

**Para personalizar seu código QR**:

1. No dashboard da AppsFlyer, vá para **experiências e deep linking** > **gerenciar o OneLink**.
2. Selecione o template que você deseja editar e clique em **personalizar QR code**.  
   O editor abre.
3. Enter the URL where your logo is hosted. For example: https://yourbrand.com/logo.png.

   Requisitos do logotipo

   * Formato PNG ou JPG
   * Quadrado ou circular com fundo transparente
   * Dimensões mínimas 400 x 400 px
   * Para impressão, use a resolução máxima de imagem
4. Defina a cor do código QR.
5. Clique em **Salvar**.

</Accordion>

<div id="measure-qrtoapp-conversions" />

<Accordion title="Mensuração de conversões QR-to-app">

Você pode mensurar a performance do seu QR code em diferentes anúncios/canais de mídia, comparando impressões (para visualizações em desktop), cliques (para leituras de QR code) e instalações do app.

**Para mensurar conversões QR-to-app**:

1. Na AppsFlyer, veja o dashboard de visão geral e outras ferramentas de analytics, registrando o total de **cliques** e **instalações** obtidos no canal de mídia do seu QR code (como **desktop\_web**).
2. Faça o registro do total de visualizações de páginas de desktop (impressões) usando seu software de web analytics.
3. Mensure a performance:
   * <Anchor target="_blank" href="/marketers/pt/docs/about-conversion-rates#estágios-de-funil-de-marketing-e-taxas-de-conversão-1">Taxa de cliques</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/about-conversion-rates#estágios-de-funil-de-marketing-e-taxas-de-conversão-1">Taxa de click-to-install</Anchor>

</Accordion>

<div id="best-practices" />

<Accordion title="Melhores práticas">

A seguir, listamos algumas dicas para a otimização de conversões QR-to-app.

* Para desktop, se você estiver usando a configuração manual, crie uma página separada em seu site para inserir o QR code.
  * Escolha um slug de URL para a página, como **/app**, **/download-app,** ou **/mobile-app**.
  * Faça com que a página fique visível apenas para desktop/tela grande.
* Para todos os anúncios:
  * Certifique-se de que o QR code seja grande e esteja em alta resolução, para que ele seja escaneado com facilidade.
  * Adicione badges em destaque de **baixar na App Store** e **baixar no Google Play** como gatilhos visuais (e não links).
  * Você também pode adicionar instruções sobre como escanear um QR code.
* Já usa o OneLink? Em *outros* OneLinks personalizados usados em e-mails ou outros canais, adicione um parâmetro **af\_web\_dp**, no qual o valor inserido é uma URL para uma página que contém o QR code. Assim, os usuários de desktop serão enviados para uma webpage, e não para a loja de aplicativos.

  <Image align="center" alt="" src="https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg" />

</Accordion>

<div id="faq" />

## Perguntas frequentes

Nesta seção, você encontra uma lista de perguntas frequentes sobre QR codes.

<div id="qr-with-long-links-vs-short-links---is-there-any-difference" />

<Accordion title="Criação de QR code com links longos vs. links curtos — há alguma diferença?">

Seu QR code funcionará com uma URL longa ou curta. No entanto, se você usar uma URL curta, poderá atualizar os parâmetros e o comportamento do link no dashboard do OneLink (na seção Link Management ou Bulk Links) sem precisar substituir o QR code publicado, já que a própria URL curta permanece inalterada.

* **URLs curtas:** Se você alterar os parâmetros na configuração da URL curta, o QR code permanecerá o mesmo. Você não precisa publicá-lo novamente.
* **URLs longas (por exemplo, Smart Script):** Se você alterar os parâmetros de uma URL longa, o QR code também mudará. Depois de publicá-lo, você não poderá atualizar o conteúdo da URL remotamente: será necessário gerar e distribuir um novo QR code.

**Dica:** Criar um QR code usando uma URL curta permite que você modifique depois os parâmetros e o comportamento do link sem precisar gerar o QR code novamente.

</Accordion>

<div id="can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example" />

<Accordion title="É possível criar um QR code e alterar retroativamente o comportamento por trás dele, por exemplo, depois de imprimir o QR code?">

Sim, é possível — se o QR code for baseado em uma URL curta do OneLink que você pode editar (por exemplo, uma criada pela interface do OneLink). Um **QR code é uma representação visual da URL por trás dele**.  Alterar a própria URL criará um novo QR code correspondente (por exemplo, o QR code de mike.onelink.me/123A/shorturl é diferente do QR code de mike.onelink.me/123A/example).

No entanto, como uma URL curta do OneLink é uma URL com hash, seus parâmetros e regras de redirecionamento são configurados no backend e não são visíveis na URL. Isso significa que você pode manter a mesma URL visível e o mesmo QR code enquanto edita a configuração no backend.

</Accordion>

<div id="what-appsflyer-options-are-available-for-generating-qr-codes" />

<Accordion title="Quais opções da AppsFlyer estão disponíveis para gerar QR codes?">

Você tem as seguintes opções:

* **Pelo dashboard da AppsFlyer → interface do OneLink:**
  * Gera automaticamente um QR code quando você cria um link
  * **Para configurar um QR code para conversões QR-to-app de desktop**:
  * Pode ser exportado como SVG ou PNG
  * Baseado em uma URL curta
* **QR code da API v2 do OneLink:**
  * Siga as <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#qr-codes">instruções para QR codes do Smart Script</Anchor>.
* **Criação em massa de QR codes (pela página de links em massa):**
  * Vá para o anúncio que possui o QR code.
  * Pode ser exportado como SVG ou PNG
  * Oferece suporte à nomeação contextual de arquivos
  * Com base em URLs curtas
* **Integração do Smart Script V2.1+**
  * Com base em URLs longas geradas dinamicamente
  * Os QR codes são criados adequadamente
  * Configuração dinâmica de QR codes

</Accordion>

<div id="can-you-bulk-create-qr-codes" />

<Accordion title="É possível criar QR codes em massa?">

sim, sim, Você pode:

* Configuração de um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor>.
* Para atribuição: <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-appsflyer-sdk">O SDK da AppsFlyer, que já está integrado</Anchor> a cada um dos seus aplicativos mobile.

</Accordion>

<div data-zendesk-anchors="converting-mobile-nonmobile-and-offline-traffic-into-mobile-app-users=como-converter-seu-tr%C3%A1fego-offline-mobile-e-de-outros-dispositivos-em-usu%C3%A1rios-ativos-do-seu-app h_01HKWVMKP3QT59EXPHQEPHW8K9=como-converter-seu-tr%C3%A1fego-offline-mobile-e-de-outros-dispositivos-em-usu%C3%A1rios-ativos-do-seu-app h_01HKWWQXVC11E8M3NV3A03SWYD=qr-to-app-conversion manual-qr-code-setup=configura%C3%A7%C3%A3o-manual-de-qr-codes h_01HKWWQXVCB96WDMBSE9WH9ZC5=configura%C3%A7%C3%A3o-manual-de-qr-codes h_01HKWVMKP3R5C5FPH010ZJZAHS=customize-qr-code h_01HKWVMKP3XTF6NNPNM8J00NWD=measure-qrtoapp-conversions h_01HKWVMKP3P6FNRPP1X7ZTNH10=best-practices qr-code-%E2%80%93-faq=perguntas-frequentes h_01K42Q4QQVNQ4579CCM7QF7MQS=perguntas-frequentes qr-with-long-links-vs-short-links-%E2%80%93-is-there-any-difference=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVKGQZKAS1PZ3B9H20=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVTV0KP280D15JF7NB=can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example h_01K42Q4QQVV1RZZXZK2Y9W8R58=what-appsflyer-options-are-available-for-generating-qr-codes h_01K42Q4QQVZF4H8FYZCTJPR0RX=can-you-bulk-create-qr-codes" />

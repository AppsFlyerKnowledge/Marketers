---
title: Implementação do código do site Smart Banners para profissionais de marketing
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developer
    - Developers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-10T11:25:54Z'
  edited_at: '2026-08-18T00:36:18Z'
  id: 4416119954705
  locale: pt
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/pt/articles/4416119954705
---
> **Visão geral:** Adicione o SDK dos Smart Banners ao seu site para converter os visitantes do seu site em usuários de aplicativos móveis.

> 📘 **Observação**
>
> O web SDK v1 do Smart Banner da AppsFlyer foi desativado em 8 de novembro de 2023. Para exibir Smart Banners em seu site, você precisa atualizar para a v2. <Anchor target="_blank" href="/marketers/pt/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">Saiba mais</Anchor>

## Implementação do código do site

Este artigo destina-se aos profissionais de marketing que pretendem implementar o código Smart Banners no seu sítio através de um dos seguintes métodos

* Google Tag Manager (GTM)
* Adobe Launch Tag Manager
* Shopify
* Wix
* Squarespace
* WordPress

Para adicionar o código ao seu site por meio de outras plataformas ou fazer alterações no código de acordo com as suas necessidades (incluindo a adição de parâmetros, deep linking, ocultação do banner ou integração do PBA com os Smart Banners), consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Implementação de código de site aos Smart Banners - para desenvolvedores</Anchor>.

**Para implementar o código dos Smart Banners no seu site**:

1. Siga <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">as instruções do site</Anchor> para obter o código dos Smart Banners.
2. Use as instruções específicas da plataforma que se seguem para implementar o código no seu site:

<div id="google-tag-manager" />

<Accordion title="Google Tag Manager">

**Para implementar o código através do Google Tag Manager**:

1. No GTM, crie uma nova tag.
2. Nomeie a tag, clique em Configuração de tags **e selecione** HTML personalizado.
3. Na caixa HTML, cole o snippet de código do Smart Banner. Substitua YOUR-BANNER-KEY no trecho de código pela sua chave de banner real.
4. Clique em **Gatilho** e crie um novo gatilho clicando no ícone de + no canto superior direito da tela.
5. Nomeie o gatilho, em seguida, clique em **Configuração de gatilho,** e escolha a **Visualização da página** .
6. Se quiser que o banner apareça em todas as páginas, selecione **Visualizar em todas as páginas**. Se quiser que o banner apareça nas páginas selecionadas, escolha **Visualizar em algumas páginas** e defina a condição para disparar a tag. Para saber mais sobre gatilhos, leia a <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">documentação do GTM</Anchor>.
7. Clique em **Salvar** no canto superior direito.
8. Retorne à tela de configuração da tag. Verifique se tudo está corretamente configurado e clique em **Salvar** no canto superior direito.
9. Publique seu contêiner GTM.

</Accordion>

<div id="adobe-launch-tag-manager" />

<Accordion title="Adobe Launch Tag Manager">

**Para implementar o código através do Adobe Launch Tag Manager**:

<div id="step-1-create-a-property-in-adobe-experience-cloud" />

<Accordion title="Passo 1: Crie uma propriedade na Adobe Experience Cloud">

**Crie uma propriedade (tag) que hospede o Smart Banner SDK**:

1. Acesse o **Adobe Experience Cloud**> **Inicialização**.
2. Em **Adobe Experience Cloud Launch**, clique em **Ir para Inicialização**.
3. Clique em **Nova propriedade**.
4. Nomeie sua propriedade.
5. Em **Plataforma**, selecione **Web**.
6. Insira o domínio do seu site.
7. Clique em **Salvar**.

</Accordion>

<div id="step-2-add-smart-banners-code-to-the-adobe-launch-property" />

<Accordion title="Passo 2: Adicionar o código Smart Banners à propriedade do Adobe Launch">

**Para adicionar o código dos Smart Banners à tag**:

1. Na página **Minha propriedade da web**, selecione a aba **Regras**.
2. Nomeie a regra. Recomendado: **AppsFlyer Smart Banners**.
3. Na seção **IF**, em **Eventos**, clique em **+Adicionar**.
   * Em **Tipo de evento**, selecione **Core - DOM Ready**.
   * Clique em **Manter alterações**.
4. Na seção **Then**, em **Ações**, clique em **+Adicionar** .
   * Em **Tipo de ação** > **Código personalizado**.
   * Selecione **JavaScript** > **Abrir Editor** e cole o trecho do código do SDK dos Smart Banners **sem as tags de &lt;script>**.
   * Clique em **Manter alterações** para fechar o editor de código.
5. Clique em **Salvar**.

</Accordion>

<div id="step-3-add-the-adobe-launch-tag-to-your-website" />

<Accordion title="Passo 3: Adicione a tag Adobe Launch ao seu site.">

**Para adicionar a tag Adobe Launch ao seu site (que carrega o código dos Smart Banners)**:

1. Na página de **Propriedade da minha web**, selecione a aba **Ambientes** .
2. Encontre a linha com o ambiente no qual você deseja publicar (desenvolvimento ou produção).
   * No cabeçalho **Instalação**, clique no ícone de caixa na linha relevante; geralmente, esse é um ambiente de produção.
   * Consulte a seção sobre como publicar o ambiente do **Adobe Launch**.
3. Na caixa de diálogo **Instruções de instalação na web**:
   * Copie o trecho de código de script.
   * Feche a caixa de diálogo.
4. Cole o trecho de código na tag &lt;head> do seu site.

</Accordion>

<div id="step-4-publish-the-adobe-launch-environment" />

<Accordion title="Etapa 4: Publique o ambiente do Adobe Launch">

**Publique o ambiente para ativar a tag Adobe Launch**:

1. Na página **Propriedade da minha web**, acesse a aba **Publicação** .
2. Na seção  **Desenvolvimento**, clique em **Adicionar nova biblioteca.**
   1. Nomeie a biblioteca e escolha um ambiente.
   2. Em **Alterações de recurso**, clique em **Adicionar um recurso.**
   3. Clique em **Regras** > **Carregar Smart Banners** > **Mais Recentes** > **Selecionar e Criar uma Nova Revisão**.
   4. Clique em **Salvar**.
3. Na seção **Desenvolvimento**:
   1. Ao lado da biblioteca recém-criada, clique no menu Ação (3 pontos) e selecione **Construir para Desenvolvimento**.
   2. Clique no menu de ação novamente e selecione **Enviar para aprovação**.
4. Na seção **Submetido**:
   1. Clique no menu de ação e selecione **Construir para Preparação**.
   2. Clique novamente no menu de ação e selecione **Aprovar para publicação**.
5. Na seção **Aprovado**, clique no menu de ação e selecione **Criar e Publicar para Produção.** O processo está concluído.

</Accordion>

Agora, quando seu site for carregado em dispositivos mobile, o criativo ativo do banner será exibido. Para exibir somente o banner em determinadas páginas ou de acordo com as ações do usuário, consulte as <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Regras do Adobe Launch</Anchor>.

</Accordion>

<div id="shopify" />

<Accordion title="Shopify">

**Para implementar o código no seu site do Shopify**:

1. No seu painel de controle do Shopify, acesse **Canais de vendas** > **Loja online** > **Temas**.  
   O tema atual aparece.
2. Clique em **Ações** > **Editar código**.  
   A página Editar código abre para o seu tema.
3. Na pasta Layout, clique no arquivo que começa com o **tema `{/}`**.  
   O código da página aparece.
4. No código, diretamente sob **&lt;head>,** cole o seu código de Smart Banners.

</Accordion>

<div id="wix" />

<Accordion title="Wix">

**Para implementar o código no seu site Wix**:

1. No seu painel de controle Wix, clique em **Configurações**.
2. Na seção Avançado da página Configurações, clique em **Código personalizado**.
3. Clique em **+ Adicionar código personalizado**.
4. Na caixa **Cole o trecho de código aqui**, cole o código dos Smart Banners.
5. Na caixa Nome, insira um nome para o seu código. **Recomendado**: AppsFlyer Smart Banners.
6. Em **Adicionar código às páginas**, selecione o local onde pretende exibir seus banners. Ou:
   * Todas as páginas
   * Selecionar páginas específicas
7. Clique em **Aplicar**.  
   A página Código personalizado deve agora mostrar o seu código. Certifique-se de que ele está na seção **Cabeçalho**.

</Accordion>

<div id="squarespace" />

<Accordion title="Squarespace">

**Para implementar o código no seu site Squarespace**:

1. No painel de controle do Squarespace, clique em **Site**.
2. Clique em **Configurações**.
3. Clique em **Avançado**.
4. Clique em **Injeção de código**.
5. Na seção **Cabeçalho**, cole o código dos Smart Banners.
6. Clique em **Salvar**.

</Accordion>

<div id="wordpress" />

<Accordion title="WordPress">

**Para implementar o código no seu site WordPress**:

1. No seu painel de controle do WordPress, clique em **Aparência** > **Editor de temas**.  
   A página Editar temas abre e o código CSS do seu site é exibido.
2. Em **Arquivos de tema**, clique em **Cabeçalho do tema (header.php)**.
3. No código que é exibido, em **&lt;head>,** cole o código dos Smart Banners.
4. Clique em **Atualizar arquivo**.

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#installation-and-integration">Integração do PBA com Smart Banners</Anchor>

<div data-zendesk-anchors="h_01HBT97B1ZGKKTD0TN2J2W56ZQ=observa%C3%A7%C3%A3o website-code-implementation=implementa%C3%A7%C3%A3o-do-c%C3%B3digo-do-site h_01HBT97B1Z0F4B8E9GQWJEE6BH=implementa%C3%A7%C3%A3o-do-c%C3%B3digo-do-site h_01HBT97B1ZKW36W9F0XQKM323P=google-tag-manager h_01HBT97B1ZX6VM1YER2HXTYQJ2=adobe-launch-tag-manager h_01HBT97B1ZPP0AKB5E31W36VC2=step-1-create-a-property-in-adobe-experience-cloud h_01HBT97B1ZK4T23MF4D6VGP4B8=step-2-add-smart-banners-code-to-the-adobe-launch-property h_01HBT97B1Z0W9VJ5FCW4605RDC=step-3-add-the-adobe-launch-tag-to-your-website h_01HBT97B1Z1W33DTT6NR4PQHQ0=step-4-publish-the-adobe-launch-environment h_01HBT97B1Z0NTYJKB2YFMX62P9=shopify h_01HBT97B1ZYVJ6PW7F811V5TAX=wix h_01HBT97B1ZS0FDM60M1GA04PRT=squarespace h_01HBT97B1ZKYB7XPGFG00PB2BT=wordpress h_01HE7SG3MJ4WTPMTXF0DA0M07D=veja-tamb%C3%A9m" />

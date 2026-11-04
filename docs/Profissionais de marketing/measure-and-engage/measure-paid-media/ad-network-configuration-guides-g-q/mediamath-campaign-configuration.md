---
title: Configuração de campanha do MediaMath
metadata:
  keywords:
    - Advertisers
    - MediaMath
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-10-06T14:55:35Z'
  edited_at: '2026-08-19T00:25:18Z'
  id: 214956583
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/214956583
---
> **Visão geral:** MediaMath, um parceiro integrado da AppsFlyer, é especializado em tecnologia de marketing programático, com plataformas de gerenciamento de dados e DSPs omnichannel. Além da atribuição mobile baseada em cliques, o MediaMath também oferece retargeting e atribuição view-through, que você pode registrar com a AppsFlyer.

![](https://cdn.appsflyer.com/marketplace/static/logo/mediamath.png)

<div id="setting-up-mediamath" />

## Configurando o MediaMath

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

Ativar o **Compartilhamento avançado de dados** permitirá que a AppsFlyer envie ao MediaMath os dados de fonte atribuída e de referenciador para postbacks de instalação. O botão de alternância ‘CB\_AD’ faz o mesmo para eventos in-app.

A janela de configuração do MediaMath inclui 3 abas ativas: Integração, link de atribuição e Permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="tip" />

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="note" />

> 📘 **Nota**
>
> Como uma all-installs network, o MediaMath prefere receber postbacks de todas as novas instalações do seu aplicativo de QUALQUER fonte, inclusive orgânica. Para fazer isso, selecione **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação ao MediaMath.

<div id="general-settings" />

### Configurações gerais

**ID do parceiro**

O MediaMath se conecta com a AppsFlyer por meio de um Advertiser ID e um Pixel ID exclusivos. Se você ainda não tiver o Advertiser ID e o Pixel ID, deverá obtê-los com o MediaMath para continuar com a integração.

**Compartilhamento avançado de dados**

Alterne para ON se quiser que a AppsFlyer envie informações adicionais ao MediaMath.

**Habilitar a atribuição de view-through**

Alterne para ON se quiser atribuir instalações view-through do MediaMath. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos ao MediaMath após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribu ddos a este parceiro** para eventos provenientes apenas de usu rios atribu ddos ao MediaMath.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para reportar ao MediaMath.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com o MediaMath por meio de postbacks.

1. Insira o Advertiser ID novamente.
2. Mude o botão Postbacks do evento in-app para ATIVO
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido no lado do MediaMath.  <br />Obtenha o ID de evento correspondente do MediaMath e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não são compatíveis com o MediaMath.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com o MediaMath.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas ao MediaMath, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que, mesmo se a atribuição estiver desativada para o MediaMath, a aba de permissões estará ativa e você poderá conceder controle ao MediaMath.

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mediamath=configurando-o-mediamath h_01HKW2X0DS3WRS3N268E2SH2HT=configurando-o-mediamath h_01HKW2X0DSW1P1RZGK26RS20QM=dica h_01HKW2X0DSSQVB3MSSEK1HB7V7=integration-tab activate-partner=ativar-parceiro h_01HKW2X0DS26H7GFZKBY3VJV59=ativar-parceiro h_01HKW2X0DSBYTBEDCM4YCPHEPA=nota general-settings=configura%C3%A7%C3%B5es-gerais h_01HKW2X0DSQWZY0KPS42RQKCFB=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HKW2X0DSAM76C6S22VMVTPGZ=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW2X0DSS1TN1B4GWP8SHY6X=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW2X0DSWT4VW9J5DMYZ2DPJ=attribution-link-tab h_01HKW2X0DS69CD1QKF8CZM3MN4=cost-tab h_01HKW2X0DS4B391FNY0W6W9YAK=ad-revenue-tab h_01HKW2X0DTC7BR20T5FPP8PW0X=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW2X0DTFX6A7X3F67WW0XNW=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />

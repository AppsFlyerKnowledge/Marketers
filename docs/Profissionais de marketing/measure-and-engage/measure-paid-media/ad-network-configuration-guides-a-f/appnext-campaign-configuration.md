---
title: Configuração de campanhas da Appnext
metadata:
  keywords:
    - Advertisers
    - appnext
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-08-20T07:46:36Z'
  edited_at: '2026-09-10T00:23:40Z'
  id: 360001407109
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/360001407109
---
> **Em resumo:** a Appnext, parceira integrada de ad network da AppsFlyer, usa tecnologia e soluções de dados para monetização mobile premium, app marketing e reengajamento. Além da atribuição mobile baseada em cliques, a Appnext também oferece atribuição de custo, retargeting e view-through, que você pode registrar com a AppsFlyer.

## Configurando a Appnext

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

### Ativar parceiro

Em sua **primeira visita** aqui, você precisará ativar a opção. Ative o botão **Ativar parceiro** para permitir a configuração dos parâmetros da aba de integração. A opção deve permanecer ativada enquanto você trabalhar com o parceiro.  

Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.

A guia Integração é dividida em diferentes seções, conforme descrito abaixo.

### Configurações gerais

**Habilitar a atribuição de view-through**

Ative esta opção se quiser atribuir instalações view-through da Appnext. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

![appnext_msc_new_2.png](https://files.readme.io/f974ed2ccc5550cebb87e5070d177fb88efb0c82fe15cbc300979d54b1297a6a-50705658863249.png)

### Postbacks padrão

Envie postbacks automáticos para a Appnext após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Observação: para instalações, você pode selecionar either **Apenas eventos atribuídos a este parceiro** (para eventos provenientes apenas de usuários atribuídos à Appnext), ou **Eventos atribuídos a qualquer parceiro ou orgânico** (para eventos provenientes de todos os parceiros). Para instalações e reengajamentos rejeitados, **apenas eventos atribuídos a este parceiro** podem ser enviados por postback.

> 📘 **Nota**
>
> Como uma ALL-Installs network, a Appnext prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER fonte, inclusive orgânica. Recomendamos selecionar **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a Appnext.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Appnext por meio de postbacks.

1. Ative a opção Postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer a partir do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido pela Appnext.  <br />Obtenha o ID do evento correspondente com a Appnext e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um OneLink.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura do link de atribuição e seus parâmetros</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A Appnext envia automaticamente dados de custo de CPI no link de atribuição para todas as instalações.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da receita publicitária não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões para conceder à Appnext. Observe que, mesmo que a atribuição esteja desativada para a Appnext, a aba de permissões permanece ativa e você pode conceder controle à Appnext.

### Permissões da rede de anúncios

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* **Permitir a configuração da integração** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* **Permitir a configuração de postbacks de evento in-app** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* **Permitir o acesso ao relatório de retenção** – somente aos próprios dados de retenção do parceiro
* **Permitir acesso aos dados agregados de usuário fiéis** — apenas aos dados de usuários fieis do parceiro
* **Permitir acesso aos seus dados agregados de eventos in-app** - apenas aos próprios dados de eventos in-app do parceiro
* **Permitir acesso aos dados agregados de receita** — apenas aos dados da receita atribuídos ao parceiro
* **Permitir o acesso ao painel Protect360** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

### Permissões da agência

Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* **Opção principal** - defina como ATIVADO para exibir as opções de permissões da agência
* **Permitir acesso ao seu relatório de retenção** - apenas aos dados de retenção da própria agência
* **Permitir acesso a dados orgânicos agregados**
* **Permitir configurar postbacks de eventos in-app** - permite que a agência configure o mapeamento de postbacks de eventos in-app para si mesma na aba de integração

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-appnext=configurando-a-appnext h_01HKW999WPN45PNK2XN3RD9NTX=configurando-a-appnext h_01HKW999WPT67XT04P3GG7PTBS=integration-tab activate-partner=ativar-parceiro h_01HKW999WPB6KKPN9MZ8N1GM70=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01HKW999WQK8P62W20K1AWHBEN=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HKW999WQS7FM0TE95G7R56M8=postbacks-padr%C3%A3o h_01HKW999WQP04CC7YPTEJ4E6AJ=nota inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW999WQFR3DMNGEJFS6ZS7N=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW999WQWFDDS13K2V3F2G3A=attribution-link-tab h_01HKW999WQKB9VNRSVV6JM15ES=cost-tab h_01HKW999WQ1C5CDN4JDYE1XMRZ=ad-revenue-tab h_01HKW999WQ9K1376YHF92GYW45=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW999WQG5KB588ESQ5XS4HM=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HKW999WQZMAX4MSM3B49H63W=permiss%C3%B5es-da-ag%C3%AAncia" />

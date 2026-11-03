---
title: Configuração da campanha da RTB House
metadata:
  keywords:
    - Advertisers
    - RTB
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-07-05T08:30:48Z'
  edited_at: '2026-08-19T00:25:52Z'
  id: 360001274325
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/360001274325
---
> **Num relance:** a RTB House, parceira integrada da rede de anúncios da AppsFlyer, fornece tecnologia de retargeting para empresas de comércio eletrônico e jogos. A RTB House desenvolveu sua própria solução de retargeting, baseada em algoritmos de deep learning, para compra de anúncios online no modelo Real-Time Bidding. Além da atribuição móvel baseada em cliques, a RTB House oferece atribuição de retargeting, que pode ser registrada com a AppsFlyer.

## Configurando a RTB House

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração de RTB House inclui 3 guias ativas: Integração, link de atribuição e permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba de integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar a opção **Ativar parceiro** para permitir a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

### Postbacks padrão

Envie postbacks automáticos para a RTB House após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

> 📘 **Nota**
>
> Como uma all-installs network, a LINE prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER canal, inclusive canais orgânicos. Para fazer isso, selecione **eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a LINE.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com ironSource por meio de postbacks.

#### Região

Insira a região do seu data center RTB House. Opções possíveis: **EMEA**, **nos**, **Ásia**.

#### Configurações de eventos in-app

1. Ative Postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido no lado da RTB House.  <br />Obtenha o ID do evento correspondente da RTB House e defina no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">siga</Anchor> essas instruções.

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

Os dados de custo são compatíveis com a integração com este parceiro por meio da <Anchor target="_blank" href="/partners/pt/docs/incost-api-for-ad-networks">API InCost</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas ao Twitter, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a RTB House, a guia de permissões estará ativa e você poderá conceder controle à RTB House.

### Permissões da ad network

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* *Permitir a configuração de postbacks de evento in-app* – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-rtb-house=configurando-a-rtb-house h_01HJRZXXH277REM62TJA907WX0=configurando-a-rtb-house h_01HJRZXXH2P8Q15V7DKQT7AVTT=dica h_01HJRZXXH2DJ8WMYPQ0NV08R05=integration-tab activate-partner=ativar-parceiro h_01HJRZXXH309BVZZ2VRRJQ02N8=ativar-parceiro default-postbacks=postbacks-padr%C3%A3o h_01HJRZXXH3X46N8KQ8GTP4BYYP=postbacks-padr%C3%A3o h_01HJRZXXH3SDCH4K86YV4VC5VH=nota inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJRZXXH3HJP28D34NW8A8EZN=configura%C3%A7%C3%B5es-de-eventos-in-app region=regi%C3%A3o h_01HJRZXXH3E7STC8XVRDP39282=regi%C3%A3o inapp-event-postback-settings=configura%C3%A7%C3%B5es-de-eventos-in-app-1 h_01HJRZXXH3336ZJZZD1P8408GP=configura%C3%A7%C3%B5es-de-eventos-in-app-1 h_01HJRZXXH3R7F4QA9PYWY7EYZZ=attribution-link-tab h_01HJRZXXH30PDV0S32THB0C4FM=cost-tab h_01HJRZXXH37CHDD10ASEXPN7VH=ad-revenue-tab h_01HJRZXXH3CASE2ZTRJDSW9545=permissions-tab ad-network-permissions=permiss%C3%B5es-da-ad-network h_01HJRZXXH3TJSTVG4Z8ZDQBATG=permiss%C3%B5es-da-ad-network" />

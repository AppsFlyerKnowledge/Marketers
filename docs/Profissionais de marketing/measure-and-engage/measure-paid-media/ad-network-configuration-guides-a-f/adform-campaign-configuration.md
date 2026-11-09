---
title: Configuração de campanhas da Adform
metadata:
  keywords:
    - adform
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-05-01T07:23:12Z'
  edited_at: '2026-08-19T00:24:00Z'
  id: 208641516
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/208641516
---
> **Em resumo:** a Adform, uma parceira integrada de ad network da AppsFlyer, oferece tecnologias abertas e transparentes que conectam anunciantes e agências a publishers, viabilizando a publicidade digital em todos os dispositivos. Além da atribuição mobile baseada em cliques, a Adform também oferece atribuição de view-through, que você pode registrar com a AppsFlyer.

<div id="setting-up-adform" />

## Configurando a Adform

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração da Adform inclui 2 abas ativas: **Integração** e **Link de atribuição**. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="tip" />

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="note" />

> 📘 **Nota**
>
> Como uma all-installs network, a Adform prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER fonte, inclusive orgânica. Recomenda-se selecionar **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a Adform.

<div id="general-settings" />

### Configurações gerais

**ID de rastreamento do cliente**

A Adform se conecta à AppsFlyer por meio de um ID de rastreamento do cliente exclusivo. Se você ainda não o tem, deve obtê-lo com a Adform para continuar com a integração.

<Image align="center" alt="adform_msc_new_2.png" src="https://files.readme.io/d3d72b295a6d3bdc7f097128a6399bd4cd60309118750b4e2217a2b01ca5362a-360002140925.png" />

**Habilitar a atribuição de view-through**

Alterne para LIGADO se quiser atribuir instalações de view-through da Adform. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para a Adform após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Adform.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à Adform.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear os eventos da AppsFlyer com a Adform por meio de postbacks.

1. Insira o Client\_Tracking\_ID e a senha novamente.
2. Mude o botão Postbacks do evento in-app para ATIVO
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido pela Adform.  <br />Obtenha o ID do evento correspondente da Adform e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para fazer a atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para campanhas de aquisição como para retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Não há permissões a serem concedidas à Adform.

</Accordion>

<div data-zendesk-anchors="setting-up-adform=configurando-a-adform h_01HJR630HMJCK05KSJ1P57KJD1=configurando-a-adform h_01HJR630HMXT2T93RH2DZ709Z6=dica h_01HJR630HMT23996KHW0Z2Z9BT=integration-tab activate-partner=ativar-parceiro h_01HJR630HM3QQVARD5YN3WG6D4=ativar-parceiro h_01HJR630HMR742Z6N1HWFGDM4Z=nota general-settings=configura%C3%A7%C3%B5es-gerais h_01HJR630HMYXE1R9WBDBBV5K39=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HJR630HMHMC5WP2F4CYP8GG0=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJR630HM4XGH1DYSHYH7EPQ4=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJR630HM00A090TQNW6Z11RY=attribution-link-tab h_01HJR630HMP3AE90YEWNVHN19Q=cost-tab h_01HJR630HMSE5DFR6Y4T3TP34C=ad-revenue-tab h_01HJR630HMF4ZJFNX6RAGT8PJA=permissions-tab" />

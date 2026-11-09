---
title: Configuração de campanhas da Bidease
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-13T13:17:18Z'
  edited_at: '2026-09-10T00:23:53Z'
  id: 20106343354129
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/20106343354129
---
> **Visão geral:** a Bidease (bidease\_int), uma parceira integrada da AppsFlyer, é uma DSP completamente transparente voltada para profissionais de marketing mobile. Usando tecnologias de publicidade programática, machine learning e dados primários, a Bidease otimiza campanhas nos principais formatos mobile com foco no comportamento após a instalação, sem oferecer nenhum risco para seus clientes.

<Image align="center" alt="bidease.png" src="https://files.readme.io/4a3373c0fdb73190017601c374ca7634cc0feb1954b6e23fc1bd9693c60605f9-20106376017041.png" width="100px" />

<div id="setting-up-bidease" />

## Como configurar a Bidease

A integração com a Bidease oferece suporte para a atribuição de click-through e view-through.

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração inclui as seguintes abas: integração, link de atribuição, custo, receita de anúncios e permissões. Para a Bidease, as abas disponíveis são as de integração, link de atribuição e permissões.

<div id="note" />

> 📘 **Observação**
>
> * Algumas configurações são diferentes para dispositivos iOS e Android
> * Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">configurar integrações de parceiros</Anchor>

<div id="integration-tab" />

<Accordion title="Aba de integração">

A aba **Integração** inclui várias seções, conforme descrito abaixo.

<div id="activate-partner" />

#### Ativar parceiro

Ative a opção **Ativar parceiro**.  
**Observação:** A opção **deve permanecer ativada (ativa)** enquanto você trabalhar com o parceiro. **Etapa 1**:

<div id="advanced-privacy" />

#### Privacidade avançada

**Somente para aplicativos iOS:** seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> depende do status da **Privacidade Avançada (para iOS 14.5+ em diante)**:

| Privacidade avançada: ativada | Privacidade avançada: desativada |
| --- | --- |
| Postbacks são enviados apenas para eventos atribuídos ao parceiro | Postbacks são enviados de acordo com sua configuração:<ul><li>**Todas as fontes de mídia, inclusive orgânicas**</li><li>**Somente este parceiro**</li></ul> |
| Os postbacks são enviados de acordo com o <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks">template de privacidade avançada</Anchor> |  |
| <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Dados agregados e anônimos</Anchor> são compartilhados com o parceiro, o que significa que nenhum dado no nível do usuário (ID do dispositivo) é compartilhado. |  |

<div id="transaction-id" />

#### ID da transação

**Somente para aplicativos iOS:** quando a opção **compartilhar ID de transação da SKAN** está ativada, você permite que a AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">compartilhe o ID de transação de postbacks da SKAdNetwork</Anchor> com o Reddit. Assim, o Reddit pode decodificar seus valores de conversão da SKAN.

<div id="install-attribution" />

#### Atribuição de instalação

Para atribuir instalações com view-through obtidas na Bidease, ative a **atribuição de instalação com view-through**. O cursor de lookback de view-through está disponível na [aba do link de atribuição](#attribution-link-tab).

<div id="default-postbacks" />

#### Postbacks padrão

Para enviar postbacks automáticos para parceiros vinculados às ações dos usuários antes da abertura do app, defina qual é a fonte desses usuários:

* Para **instalações**, selecione uma das opções abaixo:
  * **Somente esse parceiro**: enviar postbacks somente quando o evento for atribuído a esse parceiro—ou seja, o usuário que instalou o aplicativo veio da Bidease.
  * **Todas as fontes de mídia, incluindo orgânicas**: enviar postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos — ou seja, o usuário que instalou o aplicativo veio de qualquer fonte de mídia.
* Para **instalações rejeitadas** e **reengajamentos:** os postbacks são enviados apenas para a Bidease.

<div id="in-app-event-postbacks" />

#### Postback de eventos in-app

Defina a **janela de postback de eventos in-app**, se necessário (saiba mais sobre a<Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app"> configuração dessa janela aqui</Anchor>).

Configure o mapeamento de eventos in-app com eventos da Bidease, enviados via postbacks:

1. Ative **Postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para incluir um SDK ou evento de servidor para servidor. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **AppsFlyer event**, depois clique em **Criar personalizado**. Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados.</Anchor></li></ul> |
| **para utilizadores de** | Selecione a opção de envio para o evento:<ul><li>**Somente este parceiro**: envie postbacks somente quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: envie postbacks para eventos atribuídos a qualquer parceiro, bem como eventos orgânicos.</li></ul> |
| **Incluindo** | <ul><li>**Nenhum dado (padrão)**: envia apenas o evento em si sem nenhum valor de evento.</li><li>**Valores e receita**: envia todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envia todos os parâmetros **excluindo** o valor da receita.</li></ul> |

3. [Opcional] Clique no ícone **Adicionar condição**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
4. Clique em **Salvar integração.**
5. [Opcional] Após salvar a integração, você pode integrar mais aplicativos com o parceiro em questão:
   1. Do canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione a partir da lista suspensa.
   3. Repita as <Anchor target="_blank" href="/marketers/pt/docs/amazon-ads-campaign-configuration#integration-tab">etapas de integração</Anchor> para o aplicativo selecionado.

<div id="note-1" />

> 📘 **Observação**
>
> **Somente para aplicativos iOS:** seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> depende do <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">status</Anchor> da **Privacidade Avançada (para iOS 14.5+ em diante)**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuir campanhas específicas, conjuntos de anúncios ou anúncios exclusivos, tanto para campanhas de UA quanto de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de custo">

Os <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-cost-and-revenue-data">dados de custo</Anchor> não estão disponíveis para a Bidease.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba de receita de anúncios">

A <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution">receita de anúncios</Anchor> não está disponível para a Bidease.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

Selecione as <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões que você deseja conceder</Anchor> à Bidease, para que o parceiro possa acessar seus dados e executar diferentes ações.

<div id="note-2" />

> 📘 **Observação**
>
> Quando a integração é <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">desativada</Anchor> enquanto a opção Permissões ainda está ativada, as permissões permanecem inalteradas.

</Accordion>

<div data-zendesk-anchors="setting-up-bidease=como-configurar-a-bidease h_01HF4ED4B5QHY92B03426260QY=como-configurar-a-bidease h_01HF4DWFAP55JRXTR8Z65YAR68=observa%C3%A7%C3%A3o h_01HF4DWFAP4S45241VR1PJ3RFC=integration-tab activate-partner::b746d215=ativar-parceiro h_01HF4DWFAP9BS1G612WS5HNQ6S=ativar-parceiro advanced-privacy=privacidade-avan%C3%A7ada h_01HF4DWFAQHEJATJG6DRVMKA34=privacidade-avan%C3%A7ada transaction-id=id-da-transa%C3%A7%C3%A3o h_01HF4DWFAQ1Y1AVQ0EV63H5YJ1=id-da-transa%C3%A7%C3%A3o install-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o h_01HF4DWFAQQRR8XH5S7NW2NCB6=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o default-postbacks=postbacks-padr%C3%A3o h_01HF4DWFAQG4YEEH3HMD61GEWE=postbacks-padr%C3%A3o inapp-event-postbacks=postback-de-eventos-in-app h_01HF4DWFAQQCM4TK3JJNMSM6RD=postback-de-eventos-in-app h_01HF4DWFAQQ3C7GBA4Q4SA6G0Y=observa%C3%A7%C3%A3o-1 h_01HF4DWFAQ9D9BV6PG4BEYX788=attribution-link-tab h_01HF4DWFAQT2PD4863N6EB7HHH=cost-tab h_01HF4DWFAQXMNDHWT0Y4C0M6EN=ad-revenue-tab h_01HF4DWFAQJWNFMFDEZ8XT0DM5=permissions-tab h_01HF4DWFAQJ9HRMD1FE717F1WK=observa%C3%A7%C3%A3o-2" />

---
title: Configurando parceiros de gerenciamento de campanha do Meta
metadata:
  keywords:
    - Facebook
    - FMP
    - Advertisers
    - Partners
    - facebook marketing partner
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-18T12:43:51Z'
  edited_at: '2026-08-18T00:31:25Z'
  id: 360000562569
  locale: pt
  section: Meta campaign management partners
  section_id: 6551188365457
  url: https://support.appsflyer.com/hc/pt/articles/360000562569
---
> **Visão geral:** Otimize campanhas de anúncios do Meta usando parceiros de gerenciamento de campanhas Meta (anteriormente conhecidos como Parceiros de Marketing do Facebook), como Kenshoo, Bidalgo e Smartly. Quando configurado, o AppsFlyer envia os postbacks.

<div id="configure-meta-campaign-management-partners" />

## Configure Parceiros de gerenciamento de campanhas do Meta

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** Na AppsFlyer, no menu lateral, selecione**Colaborar** > **Partner Marketplace**.  
   **Para editar**: Na AppsFlyer, vá para o menu lateral e selecione **Colaborar** > **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Pesquise pelo parceiro (`rokuads_int`) e selecione-o.
4. Na aba  **integração**, selecione o aplicativo e clique em **ativar parceiro**.  
    **Observação:** essa opção deve permanecer habilitada (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativada</Anchor>) enquanto você trabalhar com o parceiro. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

<div id="in-app-event-postback-setup" />

## Configuração de postback de evento in-app

**Pré-requisito**:

Para que o parceiro receba postbacks, os nomes das campanhas **devem** ser prefixados pelo nome do parceiro de gerenciamento de campanhas do Meta. Por exemplo, se o nome do parceiro de gerenciamento de campanha Meta for *Mcmpexample* e o segmento for *Young\_Segment,* defina o nome da campanha como *mcmpexample\_Young\_Segment*.  
**Observação:** O nome do parceiro de gerenciamento de campanha do Meta diferencia **maiúsculas de minúsculas.**

**Para configurar postbacks de eventos in-app**:

<Image align="center" alt="in-app_event_mapping.png" src="https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png" />

1. Ative **Postbacks de eventos in-app.**
2. Complete os parâmetros necessários de acordo com o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#métodos-de-mapeamento">método de mapeamento</Anchor>:

   

| Nome do parâmetro | Descrição |
| --- | --- |
| <span id="appsflyer-event"></span>**Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: Não vê o evento que você está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| <span id="mapped-to-partner-event"></span>**mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#métodos-de-mapeamento">As configurações de mapeamento possíveis</Anchor> são:<ul><li>**Campo de texto:** Obtenha o ID do evento correspondente no parceiro.</li><li>**Caixa dropdown:** Selecione o evento de parceiro predefinido mais adequado.</li><li>**Sem alterações**: Enviar os eventos como eles estiverem, sem mapear o nome do evento.</li></ul> |
| <span id="for-users-from"></span>**para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Somente esse parceiro**: Envie postbacks somente quando o evento for atribuído a este parceiro—ou seja, o usuário que o executou o evento veio deste parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: Enviar postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos - ou seja, o usuário que o executou veio de qualquer fonte de mídia.</li></ul> |
| <span id="including"></span>**Incluindo** | Selecione <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">quais dados do evento</Anchor> você deseja compartilhar com o parceiro no postback:<ul><li>**Sem valores e sem receita**: Envie apenas o evento em si, sem nenhum parâmetro (valores ou receita).</li><li>**Com valores e sem receita**: Envie todos os parâmetros, com **exceção** do valor da receita.</li><li>**Valores e receita**: Envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li></ul> |

3. [Opcional] Clique em ![conditional-iae-postbacks-icon.png](https://files.readme.io/5345c5ebe95b3f1a0d0858b88ce29f9965178ce750df86c04cb131a93d006a5e-14050481317393.png) para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para o envio de determinados eventos in-app para o parceiro.
4. [Opcional] Clique em **Adicionar evento** para adicionar outro SDK ou evento de servidor para servidor à lista.
5. Clique em **Salvar integração**.

<div id="important-notes" />

> 📘 **Observações importantes**
>
> * Desabilitar a atribuição para anúncios do Meta impede o envio de postbacks para parceiros de gerenciamento de campanha do Meta
> * O mapeamento de eventos in-app com os parceiros de gerenciamento de campanhas do Meta, ou a falta dele, não afeta o envio de eventos in-app para anúncios do Meta diretamente da conta do anunciante.
> * O mapeamento de eventos in-app pode exigir parâmetros de configuração diferentes, dependendo do parceiro de gerenciamento de campanha do Meta.
> * Os das campanhas de anúncios do Meta e do X devem começar com o nome da conta do parceiro de gerenciamento da campanha do Meta, conforme definido na plataforma da AppsFlyer, seguido por um sublinhado "\_". Quando as campanhas não são nomeadas conforme mencionado, elas ficam visíveis para o anunciante, mas não para o parceiro de gerenciamento de campanhas do Meta. O nome do parceiro de gerenciamento de campanha do Meta diferencia **maiúsculas de minúsculas**.

<div data-zendesk-anchors="configuring-facebook-marketing-partners=configure-parceiros-de-gerenciamento-de-campanhas-do-meta h_01HGFQCBT217ZV0R6E2YHTV88N=configure-parceiros-de-gerenciamento-de-campanhas-do-meta inapp-event-postback-setup=configura%C3%A7%C3%A3o-de-postback-de-evento-in-app h_01HGFQCBT3R7HH8M5SQJK1EPSP=configura%C3%A7%C3%A3o-de-postback-de-evento-in-app h_01HGFQCBT3HGZVFHCC1S04MVQW=observa%C3%A7%C3%B5es-importantes" />

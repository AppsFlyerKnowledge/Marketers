---
title: configuração de campanha da ironSource
metadata:
  keywords:
    - Supersonic
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
  created_at: '2016-03-06T10:47:23Z'
  edited_at: '2026-08-19T00:25:03Z'
  id: 208005096
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/208005096
---
> **Visão geral:** ironSource, um parceiro integrado da AppsFlyer, cria ferramentas de monetização, engajamento, análise e descoberta para desenvolvedores de aplicativos, fabricantes de dispositivos, operadoras de celular e anunciantes. Além da atribuição mobile baseada em cliques, a ironSource também oferece atribuição de custo, receita publicitária, redirecionamento e visualização, que você pode registrar com a AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png?v=1" width="213px" />

## Configurando o ironSource

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Observação:** a opção deve permanecer habilitada (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativada</Anchor>) enquanto você trabalhar com o parceiro.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção **Ativar parceiro** para habilitar a configuração dos parâmetros da aba de integração. A opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
    Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

> 📘 **Observação**
>
> Como uma rede de todas as instalações, a ironSource prefere receber postbacks para todas as novas instalações do seu aplicativo de qualquer fonte, inclusive orgânica. Para fazer isso, selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para enviar todos os postbacks de instalação para ironSource.

A janela de configuração da ironSource inclui 5 abas: Integração, Link de atribuição, Custo, Receita publicitária e Permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

> 📘 **Note**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba de integração">

### Ativar parceiros

Na **primeira visita** aqui, você precisará ativar o botão de alternância **Ativar parceiro** para habilitar a configuração dos parâmetros da aba de integração. O botão de alternância deve permanecer ativado durante todo o tempo em que você trabalhar com o parceiro.  
Para obter uma descrição detalhada do Cabeçalho da janela de configuração de parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

#### Privacidade avançada

Somente para aplicativos iOS, quando **a Privacidade Avançada (para iOS 14.5+ e posterior)** está ativada, você pode <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#b">controlar quais dados são compartilhados</Anchor> com ironSource por meio de postbacks e relatórios.

### ID da transação

Somente para aplicativos iOS, quando **Compartilhar ID de transação SKAN** está ativado, você  permite que a AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">compartilhe o ID de transação de postbacks SKAdNetwork</Anchor> com ironSource. Ao fazer isso, a ironSource pode decodificar seus valores de conversão SKAdNetwork.

> 📘 **Observação**
>
> Para interoperação SKAN com a AppsFlyer, entre em contato com seu gerente de conta ironSource para <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1">permitir o envio de dados SKAN para MMPs</Anchor>.

### Configurações gerais

**ID do anunciante**

A ironSource se conecta à AppsFlyer por meio de um ID de anunciante exclusivo (número de 6 dígitos) e uma senha. Se você ainda não possui o ID e a senha do anunciante, deverá obtê-los da ironSource para continuar com a integração. Caso contrário, copie o ID e a senha e cole-os nos respectivos campos.

### Atribuição de instalação e reengajamento

Essas duas opções permitem atribuir à ironSource novas instalações e reatribuições de usuários que **visualizaram** seu anúncio, mas **não clicaram** nele. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/measure-view-through-engagements">atribuição de visualização</Anchor>.

**Para atribuir novas instalações:**

1. Ative **Instalar atribuição de visualização**.
2. Configure o comprimento da janela de lookback de **visualização** na [aba de link de atribuição](/docs/ironsource-campaign-configuration#attribution-link-tab).

**Para atribuir novos reengajamentos de usuários existentes:**

1. Ative **a atribuição de exibição de reengajamento**.
2. Configure o comprimento da janela de lookback de **visualização** na [aba de link de atribuição](/docs/ironsource-campaign-configuration#attribution-link-tab).

### Postbacks padrão

Envie postbacks automáticos para ironSource após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à ironSource.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser relatada à ironSource.

> 📘 **Observação**
>
> Observação Como uma rede de todas as instalações, a ironSource prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER fonte, incluindo orgânica. Para fazer isso, selecione Eventos atribuídos a qualquer parceiro para enviar todos os postbacks de instalação para ironSource.

### Postback de evento in-app

Configure o mapeamento de eventos in-app com eventos ironSource, enviados via postbacks:

1. Ative **Postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **mapeado para evento parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** obtenha o ID de evento correspondente do parceiro.</li><li>**Caixa drop-down:** selecione o evento AppsFlyer pré-definido mais adequado</li><li>**Como está**: envie os eventos como eles estiverem, sem mapeamento de nomes.</li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Somente este parceiro**: envie postbacks somente quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: envie postbacks para eventos atribuídos a qualquer parceiro, bem como eventos orgânicos.</li></ul> |
| **incluindo** | <ul><li>**Nenhum dado (padrão)**: envia apenas o evento em si sem nenhum valor de evento.</li><li>**Valores e receita**: envia todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envia todos os parâmetros **excluindo** o valor da receita.</li></ul> |

3. [Opcional] Clique no ícone **Adicionar condição**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
4. Clique em **Salvar integração.**
5. [Opcional] Após salvar a integração, enquanto permanece na página de configuração, você pode integrar mais de seus aplicativos com o parceiro:
   1. Do canto superior esquerdo, sob o nome do parceiro, clique no nome do aplicativo para abrir a lista de aplicativos.
   2. Selecione um aplicativo diferente a partir da lista suspensa.
   3. Repita as <Anchor target="_blank" href="/marketers/pt/docs/amazon-ads-campaign-configuration#integration-tab">etapas de integração</Anchor> para o aplicativo selecionado.

> 📘 **Observação**
>
> * Somente para aplicativos iOS: seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> **depende do** <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">estado do botão</Anchor> Privacidade Avançada (para iOS 14.5+ e posterior).
> * Você pode enviar <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postbacks de receita publicitária</Anchor> para o ironSource para que eles possam otimizar campanhas usando dados de receita publicitária:
>   * **Nome do evento:** af\_ad\_revenue
>   * **Mapeado para:** adRevenue

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Gerar e salvar links de atribuição e enviá-los ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para a UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba Cost (Custo)">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis. **Observação:** os dados de custo exigem uma assinatura ROI360.

**Para ativar a API de custo**:

* <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Siga estas instruções de integração</Anchor>

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba Receita publicitária">

Se você exibir anúncios no aplicativo enviados pela mediação Unity LevelPlay (anteriormente ironSource) ou pela network de monetização ironSource, esta seção é relevante.

As seguintes opções de granularidade da receita de anúncios estão disponíveis:

* Nível agregado (via S2S API).
* Nível de dispositivo (via S2S API).
* Nível de impressão (via SDK).
* Nível de impressão (via SDK) com nível de dispositivo (via S2S API)

Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution">atribuição de receita de anúncios</Anchor>.

**Para ativar a API de receita publicitária**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instruções de integração.</Anchor>

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba de permissões">

Nesta aba, você pode selecionar as permissões para conceder à ironSource, se o parceiro atua como uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para ironSource, a aba de permissões está ativa e você pode conceder o controle para ironSource.

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

### Permissões da ad network

* **Permitir a configuração da integração** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* **Permitir a configuração de postbacks de evento in-app** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* **Permitir o acesso ao relatório de retenção** – somente aos próprios dados de retenção do parceiro
* **Permitir acesso aos dados agregados de usuário fiéis** — apenas aos dados de usuários fieis do parceiro
* **Permitir acesso aos dados agregados de eventos in-app** — apenas aos dados de eventos in-app próprios do parceiro
* **Permitir acesso aos dados agregados de receita** — apenas aos dados da receita atribuídos ao parceiro
* **Permitir o acesso ao painel Protect360** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões da rede de anúncios</Anchor>.

### Permissões da agência

Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* **Opção principal** - defina como Ativado para revelar as opções de permissões da agência
* **Permitir acesso ao seu relatório de retenção** - apenas aos dados de retenção da própria agência
* **Permitir acesso a dados orgânicos agregados**
* **Permitir configurar postbacks de eventos in-app** - permite que a agência configure o mapeamento de postbacks de eventos in-app para si mesma na aba de integração

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-ironsource=configurando-o-ironsource h_01KZX3MPJ9HY5WJB3MS65SZXNY=configurando-o-ironsource h_01HKW1E1KBG121H7YJBW2SZS6E=observa%C3%A7%C3%A3o h_01HCFHXQQ8XYCKWPVTMK8HF165=integration-tab activate-partners=ativar-parceiros h_01HCFHXQQ8HCXPEWR4CWY55M2H=ativar-parceiros advanced-privacy=privacidade-avan%C3%A7ada h_01HCFHXQQ8ABQYRSBGC7Z1F1SV=privacidade-avan%C3%A7ada transaction-id=id-da-transa%C3%A7%C3%A3o h_01HCFHXQQ8Q3BX7GSGD5MH4QT8=id-da-transa%C3%A7%C3%A3o h_01HCFHXQQ8D26KT5E6YEQ50DA4=observa%C3%A7%C3%A3o-1 general-settings=configura%C3%A7%C3%B5es-gerais h_01HCFHXQQ8J0ZC9FGCNTPMKHK6=configura%C3%A7%C3%B5es-gerais install-and-reengagement-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o-e-reengajamento h_01HCFHXQQ8V2E8982XRSY4G50F=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o-e-reengajamento default-postbacks=postbacks-padr%C3%A3o h_01HCFHXQQ8Q27JXG2V7G4XZX43=postbacks-padr%C3%A3o h_01HCFHXQQ8XZ6H3733GPR3ZFYE=observa%C3%A7%C3%A3o-2 inapp-event-postbacks=postback-de-evento-in-app h_01HCFHXQQ891GH196XFRXY8MYS=postback-de-evento-in-app h_01HCFHXQQ8VF25W10CWQHTEAYW=observa%C3%A7%C3%A3o-3 h_01HCFHXQQ8AYNTCH9GHZJG594E=attribution-link-tab h_01HCFHXQQ87EBRW9NBY58XYFGP=cost-tab h_01HCFHXQQ8XZ8XQFH3XRFVHRZV=ad-revenue-tab h_01HCFHXQQ891P7ET9Q4BSQWJXT=permissions-tab ad-network-permissions=permiss%C3%B5es-da-ad-network h_01HCFHXQQ86VNX9WRFEZECYV7R=permiss%C3%B5es-da-ad-network agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HCFHXQQ936CQ1FVHCRC58H4C=permiss%C3%B5es-da-ag%C3%AAncia" />

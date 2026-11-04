---
title: Configuração de campanha do Reddit
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - Agencies
    - reddit
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2020-07-09T09:50:46Z'
  edited_at: '2026-11-02T13:15:12Z'
  id: 360011016138
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/360011016138
---
> **Visão geral:** O Reddit, um parceiro integrado de ad network da AppsFlyer, abriga 430 milhões de usuários mensais altamente engajados que não podem ser encontrados em nenhum outro lugar.

<div id="setting-up-reddit" />

## Configurando o Reddit

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

<Accordion title="Aba de integração">

A ***aba Integração*** é dividida em diferentes seções.

<div id="activate-partners" />

#### Ativar parceiros

Para habilitar a configuração, <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ative o parceiro</Anchor>.

<div id="advanced-privacy" />

#### Privacidade avançada

**Somente para aplicativos iOS, quando <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#b-advanced-privacy">a Privacidade Avançada (para iOS 14.5+ e posterior)</Anchor>** está ativada, você pode controlar quais dados são compartilhados com Reddit por meio de postbacks e relatórios.

<div id="transaction-id" />

#### ID da transação

**Somente para aplicativos iOS, quando <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">Compartilhar ID de transação SKAN</Anchor>** está ativado, você está permitindo que a AppsFlyer compartilhe o ID da transação dos postbacks do SKAdNetwork com o Reddit. Ao fazê-lo, o Reddit pode decodificar seus Valores de Conversão da SKAdNetwork.

<div id="general-settings" />

#### Configurações gerais

**Habilitar atribuição de visualização**

Ative se quiser atribuir instalações de visualização a partir do Reddit. O cursor de lookback de view-through está disponível na aba [***Link da atribuição***](/docs/reddit-campaign-configuration#attribution-link-tab).

**Compartilhamento de dados de correspondência avançada**

Ative esta opção para compartilhar campos de correspondência avançada, como e-mail com hash, número de telefone com hash, nome com hash e sobrenome com hash, com o Reddit, se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.

<div id="default-postbacks" />

#### Postbacks padrão

Envie postbacks automáticos para o Reddit após instalações de usuários. Selecione se deseja enviar postbacks para instalações atribuídas a:

* Somente Reddit
* Todas as fontes, incluindo orgânicas

<div id="in-app-events-settings" />

#### Configurações de eventos in-app

Nesta seção, você pode configurar postbacks de eventos in-app que são enviados ao Reddit.

**Para configurar postbacks de eventos in-app:**

1. Ativar ***postbacks de eventos in-app***
2. Clique em *Adicionar evento* para adicionar um evento SDK à lista.
3. Preencha os seguintes dados:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Nome do evento do SDK** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK ou de eventos de servidor para servidor.  <br />**Dica**: Se você não vir o evento desejado na lista, ative esse evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento conforme definido pelo Reddit. Selecione o evento predefinido mais adequado para seu evento SDK:<ul><li>rdt\_install</li><li>rdt\_signup</li><li>rdt\_app\_launch</li><li>rdt\_search</li><li>rdt\_view\_content</li><li>rdt\_add\_payment\_info</li><li>rdt\_add\_to\_cart</li><li>rdt\_purchase</li><li>rdt\_completed\_tutorial</li><li>rdt\_level\_achieved</li><li>rdt\_spend\_credits</li><li>rdt\_ad\_click</li><li>rdt\_ad\_view</li><li>rdt\_add\_to\_wishlist</li><li>rdt\_unlock\_achievement</li><li>rdt\_login</li><li>rdt\_rate</li><li>rdt\_checkout</li><li>rdt\_start\_trial</li><li>rdt\_subscribe</li><li>rdt\_onboard\_started</li><li>rdt\_onboard\_completed</li><li>rdt\_first\_time\_purchase</li></ul> |
| **Opção de envio** | Selecione se deseja enviar eventos por:<ul><li>Somente Reddit</li><li>todas as fontes, incluindo orgânicas</li></ul> |
| **Enviar dados do evento** | <ul><li>**Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.</li><li>**Valores e sem receita:** envia todos os parâmetros, com exceção do valor da receita.</li><li>**Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).</li></ul> |

4. Clique em ***Salvar***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um OneLink.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no painel de status de integração de custo (e receita de publicitária) ou no painel individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

Os dados de receita publicitária não são compatíveis com o Reddit.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões para conceder ao Reddit. Observe que mesmo que a atribuição estiver desativada para o parceiro, a aba de permissões está ativa e você pode conceder controle ao Reddit.

<div id="ad-network-permissions" />

#### Permissões da ad network

Nesta aba, você pode selecionar as permissões para conceder ao Reddit. Observe que mesmo que a atribuição estiver desativada para o parceiro, a aba de permissões está ativa e você pode conceder controle ao Reddit.

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* <span id="01EDKYCTJGZCQ05BQ5JXR6457Y"></span>***<span id="01EDKYCTJHNYT3SRD6Q40YJKR1"></span>Permitir a configuração da integração:*** permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* <span id="01EDKYCTJHVW0E6TD5ARMFEQQC"></span>***Permitir a configuração de postbacks de evento in-app:***  permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* <span id="01EDKYCTJH6C06V91M50CXNSZS"></span>***Permitir o acesso ao relatório de retenção:*** somente aos próprios dados de retenção do parceiro
* <span id="01EDKYCTJHY2JXJHQRQM6S1T7H"></span>***Permitir acesso aos dados agregados de usuários fiéis:*** apenas aos dados de usuários fieis do próprio parceiro
* <span id="01EDKYCTJHF1W3FPJCSSEKJ4GZ"></span>***Permitir acesso aos dados agregados de eventos in-app:*** apenas aos dados de eventos in-app próprios do parceiro
* <span id="01EDKYCTJHVN8E1QPY3BSMC3WD"></span>***Permitir acesso aos dados agregados de receita:*** **apenas aos dados da receita atribuídos ao parceiro**
* <span id="01EDKYCTJHX0T89JNPJKY71WVW"></span>***Permitir ingestão de gastos:*** permitir que o parceiro envie dados de gastos com anúncios em arquivos somente para este aplicativo.
* <span id="01EDKYCTJHWKWYJS7ZFCJ8558V"></span>***Permitir o acesso ao painel Protect360:*** somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div id="raw-data-restrictions" />

## Restrições de dados brutos

A partir de 8 de setembro de 2026: as restrições anteriores foram removidas e todos os campos de atribuição têm suporte total.

Clique e impressões do Reddit não são incluídos nos relatórios de dados brutos.

**Lembrete:** os dados recebidos sobre uma campanha do Reddit estão sujeitos aos <Anchor target="_blank" href="https://protect.checkpoint.com/v2/___https:/business.reddithelp.com/s/article/Reddit-Business-Tool-Terms___.YzJ1OnJlZGRpdDpjOmc6OGFlZGI3Y2U5MDg3ZTgxNzYxYzdjMzEzYzgwZjI3ZDI6NjowMDg5Ojg1MmViZDg4YWY2ZTg4NThjMDE2NjhkYTk2ZjZkYmZlYWI1NGY3MGEwNDk0MmE0ODQ0NTI3ZDM0ZWYwOWVlMmI6cDpUOk4#:%7E:text=These%20Reddit%20Business%20Tool%20Terms,advertising%20purposes%20or%20to%20otherwise">Termos da Ferramenta de Negócios do Reddit</Anchor> e incluem, entre outras restrições, a proibição de usar dados do Reddit para criar perfis de quaisquer usuários.

<div data-zendesk-anchors="setting-up-reddit=configurando-o-reddit 01EDKYCH117BTY81G0Z2NF181F=configurando-o-reddit 01EDKYCH11YM04HDJTAWP4XHWH=integration-tab activate-partners=ativar-parceiros 01EDKYCH11E2X1VSSG2HKKP6VS=ativar-parceiros advanced-privacy=privacidade-avan%C3%A7ada h_01HJRZF42CYME3EZ37470339CF=privacidade-avan%C3%A7ada transaction-id=id-da-transa%C3%A7%C3%A3o h_01HJRZF42CN7VT8SKNX5E638R0=id-da-transa%C3%A7%C3%A3o general-settings=configura%C3%A7%C3%B5es-gerais 01EDKYCH11WFJ09XBND6RQT0XA=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o 01EDKYCH11KZT2BN64AGETTMD6=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app 01EDKYCH11QAYSV2GMYD4R6DJJ=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJRZF42DHDDHPCE4NYA7QKV2=attribution-link-tab h_01HJRZF42DYG18DTKSV4G8NHV4=cost-tab 01EDKYCH124QTAFK6VQ3ARHCTM=ad-revenue-tab 01EDKYCH12RY4P6DY3QSWG1A18=permissions-tab ad-network-permissions=permiss%C3%B5es-da-ad-network 01EDKYCH12FXE1WASY5YQF80CV=permiss%C3%B5es-da-ad-network raw-data-restrictions=restri%C3%A7%C3%B5es-de-dados-brutos 01JAQ0TCR54Q03RQWPNT5PJGPN=restri%C3%A7%C3%B5es-de-dados-brutos" />

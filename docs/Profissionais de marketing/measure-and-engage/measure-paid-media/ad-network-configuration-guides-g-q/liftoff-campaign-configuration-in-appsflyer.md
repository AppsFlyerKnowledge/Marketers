---
title: Configuração da campanha da Liftoff na AppsFlyer
metadata:
  keywords:
    - liftoff
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
  created_at: '2016-03-28T09:38:23Z'
  edited_at: '2026-09-10T00:24:40Z'
  id: 209731633
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/209731633
---
> **Visão geral:** A Liftoff, um parceiro integrado de ad network da AppsFlyer, é um dos principais parceiros de demanda para marcas e desenvolvedores de aplicativos. A Liftoff oferece atribuição mobile baseada em clique e view-through, além de retargeting baseado em clique e view-through, que você pode registrar com a AppsFlyer.

![](https://cdn.appsflyer.com/marketplace/static/logo/liftoff.png)

> 🚧 **Importante!**
>
> Algumas fontes de mídia restringem o compartilhamento de dados com terceiros. A AppsFlyer não pode compartilhar dados no nível de usuário adquiridos por meio dessas fontes de mídia com plataformas ou serviços de terceiros. Todas as instalações de tais fontes de mídia são, portanto, enviadas como orgânicas.
>
> Para mais detalhes e uma lista de canais de mídia que restringem o compartilhamento de dados com terceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention">aqui</Anchor>.

## Como configurar a Liftoff

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.  
   Para editar: vá para **colaborar** > **integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na aba **Integração**, selecione o aplicativo e ative a opção **Ativar parceiro**.  
    **Atenção:** **o toggle deve permanecer ligado ([ativado](#)) enquanto você trabalhar com o parceiro. [Saiba mais sobre a ativação de parceiros](#).**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do cabeçalho da janela de configuração do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A **aba de integração** se divide em diferentes seções, conforme descrito abaixo.

### Ativar parceiros

O <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">parceiro deve ser ativado</Anchor> ao ligar o botão de alternância **Ativar parceiro** na primeira visita, para permitir a configuração.

### Configurações gerais

**Ative a atribuição de view-through**

Ative se quiser atribuir instalações view-through da Liftoff. O cursor de lookback de view-through está disponível na aba [**Link da atribuição**](/docs/liftoff-campaign-configuration-in-appsflyer#attribution-link-tab).

### Postbacks padrão

Envie postbacks automáticos para a Liftoff após instalações de usuários, instalações rejeitadas e reengajamentos. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente este parceiro** para eventos provenientes apenas de usuários atribuídos à Liftoff.  
Selecione **todas as fontes, incluindo orgânicas** para ter toda a sua base de usuários disponível para ser reportada à Liftoff.

> 📘 **Nota**
>
> Como uma all-installs network, a Liftoff prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER fonte, inclusive orgânica. Para fazer isso, selecione **Todas as fontes, incluindo orgânicas** para enviar todos os postbacks de instalação para a Liftoff.

**Para configurar os postbacks de eventos na aplicação:**

1. Ativar **postbacks de eventos in-app**
2. Escolha se deseja reportar **eventos selecionados** ao parceiro ou **todos** eles.
   * Observação: se você optar por reportar todos os eventos, o evento af\_app\_opened não será reportado.
3. Se você optar por selecionar eventos manualmente, clique em **Adicionar evento** para adicionar um evento de SDK à lista.
4. Preencha os seguintes dados:

| Nome do parâmetro | A descrição |
| --- | --- |
| **Nome do evento de SDK** (obrigatório apenas para seleção manual) | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK ou de eventos de servidor para servidor.  <br />**Dica**: Se você não vir o evento desejado na lista, ative esse evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Opção de envio** | Selecione a opção de envio para o evento:  <br />**Somente este parceiro** para eventos provenientes **apenas** de usuários atribuídos à Liftoff.  <br />**Todas as fontes, incluindo orgânicas** para ter toda a sua base de usuários disponível para ser reportada ao parceiro |
| **Enviar dados do evento** | <ul><li>**Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.</li><li>**Valores e sem receita:** envia todos os parâmetros, com exceção do valor da receita.</li><li>**Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).</li></ul> |

5. Clique em **Salvar**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Gere e salve links de atribuição e envie-os ao parceiro para atribuir campanhas específicas, conjuntos de anúncios ou anúncios exclusivos, tanto para campanhas de UA quanto de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no painel de status de integração de custo (e receita de publicitária) ou no painel individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

Os dados de receita de anúncios não têm suporte por parte deste parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões para conceder à Liftoff. Observe que, mesmo que a atribuição esteja desativada para a Liftoff, a aba de permissões está ativa e você pode conceder controle à Liftoff.

### Permissões da rede de anúncios

Nesta aba, você pode selecionar as permissões para conceder à Liftoff. Observe que, mesmo que a atribuição esteja desativada para a Liftoff, a aba de permissões está ativa e você pode conceder controle à Liftoff.

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* **Permitir a configuração da integração** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* **Permitir a configuração de postbacks de evento in-app** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* **Permitir o acesso ao relatório de retenção** – somente aos próprios dados de retenção do parceiro
* **Permitir acesso aos seus dados agregados de usuários fidelizados** - apenas aos dados de usuários fidelizados do próprio parceiro
* **Permitir acesso aos seus dados agregados de eventos in-app** - apenas aos dados de eventos in-app do próprio parceiro
* **Permitir acesso aos dados agregados de receita** — apenas aos dados da receita atribuídos ao parceiro
* **Permitir o acesso ao painel Protect360** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

### Permissões da agência

Se você trabalha com a Liftoff como parceira de agência, nesta seção você pode conceder a ela permissões para gerenciar a própria configuração do seu aplicativo:

* **Chave seletora principal** - Definir como **LIGADA**:

  * Revela as opções de permissões da agência
  * Permite que a agência seja atribuída às instalações do aplicativo
  * Permite que a agência veja os dados promovidos dos anúncios da Meta e do X Ads

  **Aviso: as instalações da agência que ocorrerem enquanto o botão de alternância estiver DESLIGADO não serão atribuídas à agência** e não aparecerão no dashboard nem nos dados da agência (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#permissões-da-agência">mais detalhes</Anchor>).

* **Permitir acesso ao seu painel Protect360**
* **Permitir acesso aos seus relatórios de retenção e coorte** - dados de retenção/coorte criados apenas pelos usuários trazidos pela agência.
* **Permitir acesso a dados orgânicos agregados**
* **Permitir configurar postbacks de eventos in-app** - permite que a agência configure o mapeamento de postbacks de eventos in-app para si mesma na aba de integração
  * **Permissões de compartilhamento de eventos** - selecione aqui a opção de sua preferência:  
    a) **Somente este parceiro** - envie apenas eventos do tráfego trazido pela própria agência para o aplicativo  
    b) **Todas as fontes, incluindo orgânico** - envie eventos de todas as fontes do seu tráfego, incluindo outros canais de mídia, agências e usuários orgânicos
  * **Permitir o envio de receita de eventos** - permita que a agência envie eventos, incluindo seu valor monetário
  * Certifique-se de selecionar eventos específicos para os quais deseja conceder permissão à agência. Clique em **Add event** e selecione o evento na lista suspensa. Faça isso para cada evento que você deseja adicionar.

Saiba mais sobre <Anchor target="_blank" href="/partners/pt/docs/about-agency-accounts">trabalhar com agências</Anchor>.

</Accordion>

## Configure a integração da SKAdNetwork com a Liftoff

**Para receber dados da SKAdNetwork da Liftoff:**

1. <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Para ter suporte à SKAdNetwork, atualize o SDK da AppsFlyer para a versão mais recente</Anchor>.
2. No Conversion Studio da AppsFlyer, <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#configuração-de-valores-de-conversão-no-skan-conversion-studio">configure valores de conversão para mensurar os eventos que você quer</Anchor>.
3. Compartilhe com a Liftoff o objetivo da sua campanha e o evento final com o qual você quer otimizar suas campanhas. Recomenda-se que o evento final se correlacione com o seu evento preferido e ocorra próximo ao momento da instalação.  
   Exemplo:
   * **Campanhas de CPA:** Compartilhe o evento obrigatório e o objetivo de CPA a ser usado na otimização de campanhas da SKAdNetwork.
   * **Campanhas de CPI:** Compartilhe o objetivo de CPI a ser usado na otimização de campanhas da SKAdNetwork.
4. Entre em contato com a equipe de contas da Liftoff para confirmar que os postbacks da SKAdNetwork estão sendo enviados com valores de conversão.
5. [Opcional] Para compartilhar o ID da transação da SKAdNetwork com a Liftoff, ative **Share Transaction ID in SKAdNetwork mode**.  
   Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">ID da transação.</Anchor>

## Retargeting de feed de produtos com Liftoff

Para que a atribuição de eventos de produto funcione corretamente, a Liftoff precisa receber os IDs de produto associados a cada um dos seus eventos. Por exemplo, os IDs de produtos específicos que os usuários compram ou adicionam ao carrinho.

Esses IDs devem ser vinculados aos IDs exclusivos que você envia para a Liftoff no seu feed de produtos. A Liftoff é compatível com a <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#parâmetros-de-eventos-predefinidos">convenção padrão da AppsFlyer para compartilhar esses dados</Anchor> por meio de atributos af\_content\_id por padrão.

Se você tiver uma implementação não padrão de dados de evento, entre em contato com seu CSM da Liftoff para verificar se a integração é possível.

<div data-zendesk-anchors="h_01HGFR9QYBQ3BK3TM364SJDKWZ=importante setting-up-liftoff=como-configurar-a-liftoff h_01HGFR9QYBPY2XR4KMWMJKHHMQ=como-configurar-a-liftoff h_01HGFR9QYBJG0WD6X203X8MYFV=integration-tab activate-partners=ativar-parceiros h_01HGFR9QYBXAQQKPRW1KKF6989=ativar-parceiros general-settings=configura%C3%A7%C3%B5es-gerais h_01HGFR9QYBPCYCJRY20S1TCF6R=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HGFR9QYB8JHTAAB591QQ1P6J=postbacks-padr%C3%A3o h_01HGFR9QYBW8DFZK63EZ3V5622=nota h_01HGFR9QYB42YK8FJD308YWXC7=attribution-link-tab h_01HGFR9QYBJ20T4F0W5486B4NW=cost-tab h_01HGFR9QYBV9ZCGJ1D6BD1T9JG=ad-revenue-tab h_01HGFR9QYB9DA5XYXPEARZSCHF=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HGFR9QYB0VCPG7YCX64BBKY9=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HGFR9QYBR3W0JXY7MHQ8PZT7=permiss%C3%B5es-da-ag%C3%AAncia set-up-skadnetwork-integration-with-liftoff=configure-a-integra%C3%A7%C3%A3o-da-skadnetwork-com-a-liftoff h_01HGFR9QYBG4830DKGMGV716B7=configure-a-integra%C3%A7%C3%A3o-da-skadnetwork-com-a-liftoff product-feed-retargeting-with-liftoff=retargeting-de-feed-de-produtos-com-liftoff h_01HGFR9QYB302DVBYXMK0XY4ED=retargeting-de-feed-de-produtos-com-liftoff" />

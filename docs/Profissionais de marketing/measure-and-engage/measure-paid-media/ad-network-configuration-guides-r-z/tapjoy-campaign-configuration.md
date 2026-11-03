---
title: Configuração de campanha da Tapjoy
metadata:
  keywords:
    - Tapjoy
    - SDK
    - configuration
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
  created_at: '2015-06-10T14:19:38Z'
  edited_at: '2026-09-09T00:25:20Z'
  id: 207033956
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/207033956
---
> **Visão geral:** a Tapjoy, um parceiro integrado de ad network da AppsFlyer, é uma plataforma de publicidade e monetização de aplicativos. Além da atribuição mobile baseada em cliques, a Tapjoy oferece atribuição view-through, que pode ser registrada com a AppsFlyer.

Para configurar suas campanhas com a Tapjoy, siga as etapas abaixo.

## Configurando a Tapjoy

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Se você não tiver uma conta, entre em contato com o parceiro para abrir uma antes de configurar a integração.

**Para ativar a integração:**

1. Na AppsFlyer, acesse a guia **Colaborar > Integrações de parceiros > Marketplace** .  
    **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na guia **Integração**, ative a opção **Ativar parceiro**.   
    **Observação:** A opção **deve permanecer ativada (ativa) enquanto você trabalhar com o parceiro**.   
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">integrações de parceiros.</Anchor>

<div id="integration-tab" />

<Accordion title="Aba Integração">

A ***aba de integração*** se divide em diferentes seções, conforme descrito abaixo.

### Ativar parceiros

Na primeira visita, <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">o parceiro deve ser ativado</Anchor> ao habilitar a opção ***Ativar parceiro***, para permitir sua configuração.

### Configurações gerais

#### ativado

A Tapjoy se conecta à AppsFlyer por meio de um ID de network exclusivo. Se você ainda não tiver o ID do aplicativo, deverá obtê-lo com a Tapjoy para continuar com a integração.

#### Habilitar a atribuição de view-through

Ative esta opção se quiser atribuir instalações view-through da Tapjoy. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

### Postbacks padrão

Envie postbacks automáticos para a Tapjoy após instalações e instalações rejeitadas. Use esta seção para definir a **fonte dos usuários** para os postbacks.

Selecione ***Somente este parceiro*** para instalações provenientes apenas de usuários atribuídos à Tapjoy.  
Selecione ***Todas as fontes, incluindo orgânico*** para ter toda a sua base de usuários disponível para ser reportada à Tapjoy.

Instalações rejeitadas podem ser enviadas para **somente este parceiro**.

#### Postbacks de inicialização

Desde 1º de julho de 2020, não enviamos mais postbacks de inicialização para a Tapjoy. Se sua integração foi configurada antes dessa data, pode haver alterações nas suas configurações. A tabela a seguir explica as possíveis alterações e as ações necessárias, quando aplicável:

| Sua configuração | Será atualizada para | Suas próximas ações |
| --- | --- | --- |
| Enviar para a Tapjoy **todos os lançamentos** (de todos os canais de mídia, incluindo orgânico) | Enviar para a Tapjoy:<ul><li>**todas as instalações** (de todos os canais de mídia, incluindo orgânico)</li><li>**todos os eventos `af_app_opened`** (de todos os canais de mídia, incluindo orgânico)</li></ul> | Não é necessária nenhuma ação adicional. Esta atualização não tem nenhum impacto real na configuração. |
| Enviar para a Tapjoy **somente os primeiros lançamentos atribuídos** | Enviar para a Tapjoy **instalações** atribuídas somente à Tapjoy | Se você também quiser enviar eventos `af_app_open`:<ul><li>No AppsFlyer, na página de integração da Tapjoy, configure o envio do evento na seção ***Postbacks de evento in-app***</li></ul> |
| Enviar para a Tapjoy **todos os lançamentos** (de todos os canais de mídia, incluindo orgânico)<br /><br />**MAS**<br /><br />Nenhuma conversão foi atribuída à Tapjoy nos 3 meses anteriores a 1º de julho de 2020 | Enviar **todas as instalações**<br /><br />**AND**<br /><br />Por 30 dias após 1º de julho de 2020, **todas as inicializações** | Se você também quiser enviar eventos `af_app_open`:<ul><li>No AppsFlyer, na página de integração da Tapjoy, configure o envio do evento na seção ***Postbacks de evento in-app***.</li></ul>Se isso for feito durante o período de 30 dias, deixaremos de enviar todas as inicializações e passaremos a enviar todos os eventos `af_app_open`.<br /><br />Se isso for feito após o período de 30 dias, pararemos de enviar inicializações e não enviaremos eventos `af_app_open` até que isso seja configurado de outra forma. |

### Configurações de eventos in-app

Nesta seção, você pode configurar postbacks de eventos in-app que são enviados à Tapjoy.

**Para configurar os postbacks de eventos na aplicação:**

1. Ative **Postbacks de eventos in-app**.
2. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista.
3. Preencha os seguintes dados: 

| Nome do parâmetro | A descrição |
| --- | --- |
| **Evento na AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos S2S.<br /><br />**Dica** : não vê o evento que você está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de evento personalizado.</Anchor></li></ul> |
| **Mapeado para evento do parceiro** | O nome ou ID único de cada evento, como definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** Obtenha o ID do evento correspondente no parceiro.</li><li>**Caixa suspensa:** selecione o evento predefinido mais adequado.</li><li>**Como está**: envie os eventos como estão, sem mapeamento de nomes.</li></ul> |
| **para utilizadores de** | Selecione a opção de envio para o evento:<ul><li>**Somente esse parceiro**: Enviar postbacks somente quando o evento for atribuído a este parceiro—ou seja, o usuário que o executou o evento veio deste parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: Enviar postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos - ou seja, o usuário que o executou veio de qualquer fonte de mídia.</li></ul> |
| **Incluindo** | <ul><li>**Sem dados (padrão)**: Envie apenas o evento em si, sem qualquer valor de evento.</li><li>**Valores e receita**: Envie todos os parâmetros do evento, incluindo valores de receita (se existirem no evento).</li><li>**Valores sem receita**: Envie todos os parâmetros do evento, excluindo valores de receita.</li></ul> |

4. [Opcional] Clique em Adicionar condição![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) ícone de um evento para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições para o evento</Anchor> enviado para a Tapjoy.   

   > 📘 **Importante!**
   >
   > A Tapjoy recomenda não adicionar condições aos eventos enviados a ela, pois isso pode causar problemas no sistema de recompensas proprietário da Tapjoy e pode impactar negativamente a experiência do usuário.

5. Clique em **Salvar Integração**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

**Observação:** a TapJoy não reporta impressões de Offerwall à AppsFlyer. Portanto, as instalações após impressões de Offerwall não são contabilizadas na AppsFlyer. Saiba mais sobre [impressões de Offerwall](https://www.tapjoy.com/offerwall/).

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="Status de sincronização dos dados de custo">

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

> 📘 **Notas**
>
> * Se macros de custo estiverem sendo passadas no link de atribuição, a integração da API não poderá ser ativada. Ativar a integração da API de custo enquanto houver macros de custo no link de atribuição pode causar relatórios duplicados de custo. Entre em contato com seu gerente de contas da TapJoy e com seu CSM da AppsFlyer para remover todas as macros de custo dos links de atribuição existentes.
> * Depois de definir o custo na TapJoy, não altere o nome de nenhuma campanha ativa, conjunto de anúncios ou anúncio individual, nem use macros dinâmicas com o parâmetro de nome da campanha, pois elas podem causar discrepâncias graves ou a perda de dados de custo.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

Esta seção é relevante se você for um publisher que exibe anúncios de parceiros para seus usuários. Nesse caso, você certamente deseja mensurar o engajamento dos usuários adquiridos de várias fontes para encontrar as fontes mais lucrativas para você. Saiba mais sobre a <Anchor target="_blank" href="https://dev.tapjoy.com/en/graphql-api/Appsflyer#iap-and-ad-revenue-configuration-for-roas">configuração de receita de anúncios da Tapjoy</Anchor>.

**Para ativar a API de receita de anúncios**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instruções de integração</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Tapjoy, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo os dois. Observe que, mesmo se a atribuição estiver desativada para a Tapjoy, a aba de permissões estará ativa e você poderá conceder controle à Tapjoy.

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo.

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* *Permitir a configuração de postbacks de evento in-app* – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos seus dados agregados de usuário fidelizado*** - somente aos dados de usuário fidelizado do próprio parceiro
* ***Permitir acesso aos seus dados agregados de eventos in-app** -* somente aos dados de eventos in-app do próprio parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre as <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-tapjoy=configurando-a-tapjoy h_01HJS1SANCA03NGA11EA2359Z9=configurando-a-tapjoy h_01HJS1SANC560TH8VJ2R2ZRKZA=integration-tab activate-partners=ativar-parceiros h_01HJS1SANC0KMZ3HFM2MNJ6SCV=ativar-parceiros general-settings=configura%C3%A7%C3%B5es-gerais h_01HJS1SANCN7RXVCKCQD4N8B2S=configura%C3%A7%C3%B5es-gerais app_id=ativado h_01HJS1SANCSQ8Z3YB41V7KHAZD=ativado enable-viewthrough-attribution=habilitar-a-atribui%C3%A7%C3%A3o-de-view-through h_01HJS1SANCR3DEAPQW0F1S0YP9=habilitar-a-atribui%C3%A7%C3%A3o-de-view-through default-postbacks=postbacks-padr%C3%A3o h_01HJS1SANCN0KQ7APJBPAVD7G7=postbacks-padr%C3%A3o launch-postbacks=postbacks-de-inicializa%C3%A7%C3%A3o h_01HJS1SANCZTZ2NR3XTEPVRKXG=postbacks-de-inicializa%C3%A7%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJS1SANDCNEXH91VMY2E0KYJ=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJS1SAND8DY0SNRZKGBFAZKK=importante h_01HJS1SANDQK7DT52KF9011YZB=attribution-link-tab h_01HJS1SAND247NKAB9FQBBCSPQ=cost-tab h_01HJS1SANDWEMAHC3SJ64EMR7F=cost-data-sync-status h_01HJS1SANDVWHSW4GPQHS0ZM6G=notas h_01HJS1SANDTWFDTAZYEHB3KKEH=ad-revenue-tab h_01HJS1SAND4S7S8NW05N4R20NB=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HJS1SANDAW1MH9EYRZSD5BTG=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />

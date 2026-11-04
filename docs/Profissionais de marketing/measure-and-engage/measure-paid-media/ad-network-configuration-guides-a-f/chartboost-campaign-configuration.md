---
title: Configuração da campanha do Chartboost
metadata:
  keywords:
    - Chartboost
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
  created_at: '2016-03-28T08:01:01Z'
  edited_at: '2026-09-10T00:23:58Z'
  id: 209731553
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/209731553
---
> **Visão geral:** o Chartboost, uma ad network parceira integrada da AppsFlyer, é uma das maiores plataformas de anúncios voltadas exclusivamente para jogos mobile, para aumentar a receita. Além da atribuição mobile baseada em cliques, o Chartboost também oferece atribuição de custo, receita publicitária e view-through, que você pode registrar com a AppsFlyer.

<div id="note" />

> 📘 **Nota**
>
> Integrar o SDK do Chartboost só é necessário se você atua como publisher do Chartboost e deseja atribuir receita publicitária. Caso contrário, apenas o SDK da AppsFlyer é necessário. Para mais informações, consulte a [seção de receita publicitária](/docs/chartboost-campaign-configuration#ad-revenue-tab) deste artigo.

<div id="setting-up-chartboost" />

## Configurando o Chartboost

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

A ***aba de integração*** se divide em diferentes seções, conforme descrito abaixo.

<div id="activate-partners" />

### Ativar parceiros

O <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">parceiro deve ser ativado</Anchor> ao habilitar o botão de alternância ***Ativar parceiro*** na primeira visita, para permitir sua configuração.

<div id="general-settings" />

### Configurações gerais

**ID e assinatura do aplicativo do Chartboost**

O Chartboost requer conexão com a AppsFlyer por meio de um ID de aplicativo exclusivo e uma assinatura. Se você não souber qual é o seu, poderá obtê-lo diretamente com o Chartboost.

**Habilitar a atribuição de view-through**

Ative essa opção se quiser atribuir instalações por view-through do Chartboost. O cursor de lookback de view-through está disponível na ***aba Link da atribuição***.

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para o Chartboost após registrar instalações bem-sucedidas e instalações rejeitadas. Use essa seção para definir a **fonte dos usuários** para os postbacks.

Selecione ***somente este parceiro*** para instalações provenientes apenas de usuários atribuídos ao Chartboost.  
Selecione ***todas as fontes, incluindo orgâni*cas** para ter toda a sua base de usuários disponível para ser reportada ao Chartboost.

Instalações rejeitadas podem ser enviadas para **somente este parceiro**.

<div id="launch-postbacks" />

#### Postbacks de inicialização

Desde 1º de julho de 2020, não enviamos mais postbacks de lançamento para o Chartboost. Se a sua integração foi configurada antes dessa data, pode haver alterações nas suas configurações. A tabela a seguir explica as possíveis alterações e as ações necessárias da sua parte, quando aplicável:

| Sua configuração | Será atualizado para | Suas próximas ações |
| --- | --- | --- |
| Enviar ao Chartboost **todos os lançamentos** (de todas as fontes de mídia, incluindo orgânico) | Enviar ao Chartboost:<ul><li>**todas as instalações** (de todos os canais de mídia, incluindo orgânico)</li><li>**todos os** `af_app_opened` **eventos** (de todos os canais de mídia, incluindo orgânico)</li></ul> | Nenhuma ação adicional é necessária. Esta atualização não tem impacto real na configuração. |

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode configurar postbacks de eventos in-app que são enviados ao Chartboost.

**Para configurar os postbacks de eventos na aplicação:**

1. Ative ***postback de evento in-app***.
2. Escolha se deseja reportar eventos selecionados ao parceiro ou reportar todos.
   * Observação: se você optar por reportar todos os eventos, o evento *af\_app\_opened* não será reportado.
3. Se você optar por selecionar eventos manualmente, clique em ***Adicionar evento*** para adicionar um evento do SDK à lista.

| Nome do parâmetro | A descrição |
| --- | --- |
| **Nome do evento do SDK** *(obrigatório apenas para seleção manual)* | O nome do evento, conforme recebido pelo AppsFlyer, seja do SDK ou de eventos de servidor para servidor.  <br />**Dica**: Se você não vir o evento desejado na lista, ative esse evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Opção de envio** | Selecione a opção de envio do evento:  <br />**Somente este parceiro** para eventos provenientes **apenas** de usuários atribuídos ao Chartboost.  <br />**Todas as fontes, incluindo orgânico** para disponibilizar toda a sua base de usuários para ser reportada ao parceiro |
| **Enviar dados do evento** | <ul><li>**Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.</li><li>**Valores e sem receita:** envia todos os parâmetros, com exceção do valor da receita.</li><li>**Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).</li></ul> |

4. Clique em ***Salvar***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Chartboost para atribuir campanhas, conjuntos de anúncios ou anúncios individuais do Chartboost. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução no Chartboost.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Chartboost.  
  **Parâmetro do link de atribuição:** af\_adset
* **Nome do anúncio** - defina os nomes dos anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas do Chartboost.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e usar o parâmetro de ID do subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para obter mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro da janela de lookback podem ser atribuídas ao Chartboost.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o ao Chartboost para ser ativado quando os leads clicarem em um anúncio correspondente.

<div id="view-through-attribution-lookback-window" />

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente as instalações (primeiras aberturas) que acontecem durante essa janela de lookback, após uma impressão de anúncio, são atribuídas ao Chartboost, desde que não haja nenhum outro clique em anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição view-through aqui</Anchor>.

<div id="impressions-attribution-link" />

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o ao Chartboost para ser ativado quando um anúncio correspondente for assistido.

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

Essa seção é relevante somente se você estiver atuando como publisher, exibindo anúncios do parceiro aos usuários. Nesse caso, você certamente deseja mensurar o engajamento dos usuários adquiridos de várias fontes para encontrar as fontes mais lucrativas para você.

**Para ativar a API de receita publicitária**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">essas instruções de integração</Anchor>.

<div id="important" />

> 🚧 **Importante!**
>
> Como publisher do Chartboost, há dois requisitos adicionais além da configuração do AppsFlyer:
>
> 1. [Integrar o SDK do Chartboost](https://answers.chartboost.com/en-us/child_article/ios) - isso só é necessário se você atuar como publisher. **Se você usa o Chartboost apenas para anunciar seu aplicativo, o SDK da AppsFlyer é tudo o que você precisa integrar**.
> 2. [Habilite o S2S do Chartboost](https://answers.chartboost.com/en-us/child_article/s2s-setup) - esta etapa é necessária para permitir que a AppsFlyer consulte o Chartboost para obter dados de receita de anúncios. **Isso não deve ser confundido com** <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">**AppsFlyer S2S**</Anchor>**, que é a sua forma de enviar eventos in-app para a AppsFlyer usando uma API dedicada.**

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas ao Chartboost, independentemente de o parceiro atuar como uma ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para o Chartboost, a aba de permissões estará ativa e você poderá conceder controle ao Chartboost.

Use estas alternâncias para conceder à ad network permissões para gerenciar sua própria configuração no seu aplicativo: Permissões da ad network

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div id="discrepancies-between-chartboost-and-appsflyer" />

## Discrepâncias entre o Chartboost e a AppsFlyer

Às vezes, há discrepâncias entre o dashboard do Chartboost e o dashboard do AppsFlyer.

Os anunciantes devem estar cientes dos seguintes motivos:

| Causa | Chartboost | A AppsFlyer |
| --- | --- | --- |
| **Janela de atribuição** | A janela de atribuição da Chartboost é de 21 dias | A janela de lookback da AppsFlyer é de 7 dias<br /><br />**\*\* Esta é a principal causa das discrepâncias entre a AppsFlyer e a Chartboost** |
| **Atribuição de origem multi-canal** | A atribuição da Chartboost funciona conforme especificado acima, independentemente de outras fontes. | A AppsFlyer usa a atribuição do último clique (para mais informações sobre a atribuição da AppsFlyer, clique <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">aqui</Anchor>) |

<div id="note-1" />

> 📘 **Nota**
>
> Enquanto a Chartboost mostra todas as instalações de uma campanha de retargeting no mesmo lugar, no dashboard da AppsFlyer as instalações são divididas entre a página Visão geral (novas instalações) e a página Retargeting (reatribuição e reengajamentos).

<div data-zendesk-anchors="h_01HFRFDP5V8Q9F0KTEX8X917ZX=nota setting-up-chartboost=configurando-o-chartboost h_01HFRFDP5V0CTXQ0B0JXYD0TKS=configurando-o-chartboost h_01HFRFDP5V7BEPGG4226CYWCS7=integration-tab activate-partners=ativar-parceiros h_01HFRFDP5V26M3RV5986P768A7=ativar-parceiros general-settings=configura%C3%A7%C3%B5es-gerais h_01HFRFDP5VPBY1W81DRVVWJ54D=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HFRFDP5V2GAJQ81NYKDGF16K=postbacks-padr%C3%A3o launch-postbacks=postbacks-de-inicializa%C3%A7%C3%A3o h_01HFRFDP5VGFJ8K0J9GA0EX3K1=postbacks-de-inicializa%C3%A7%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HFRFDP5V3Z41EEASQD7ZPJRD=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HFRFDP5VKTGQFHMMXTD6KQTY=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HFRFDP5VA3DQSH3TRYJC47JZ=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HFRFDP5VQFQHH6ZZ6DWXSJ9C=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HFRFDP5WAJ5Y0K27DY21NZ91=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HFRFDP5WTKE6WJ3CVS16PDF9=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HFRFDP5WSM97SFDS8YC64X31=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HFRFDP5W0K5A3E229PS25N9P=cost-tab h_01HFRFDP5WAB1F5YBA9BW3QYPM=ad-revenue-tab h_01HFRFDP5WMREFM3Q0DXJYTHCD=importante h_01HFRFDP5WHAKN44VT9Y90P6BJ=permissions-tab discrepancies-between-chartboost-and-appsflyer=discrep%C3%A2ncias-entre-o-chartboost-e-a-appsflyer h_01HFRFDP5WHWZARGXQ5ZTRC8BD=discrep%C3%A2ncias-entre-o-chartboost-e-a-appsflyer h_01HFRFDP5WN483XJN4PDV2KCR0=nota-1" />

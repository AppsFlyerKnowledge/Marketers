---
title: Configuração da campanha da Jampp, uma empresa da Affle
metadata:
  keywords:
    - Advertisers
    - Jampp
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-12-29T12:49:55Z'
  edited_at: '2026-09-10T00:24:35Z'
  id: 115000151226
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/115000151226
---
> **Em resumo:** a Jampp, uma empresa da Affle e parceira integrada da AppsFlyer, fornece uma plataforma de marketing de performance para adquirir e fazer retargeting de clientes de aplicativo. Além da atribuição mobile baseada em cliques, a Jampp também oferece atribuição de custo, retargeting e view-through, que você pode registrar com a AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jampp.png" width="213px" />

## Configuração da integração da Jampp

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="h_01HKW1V0MN1PQ9HWC0TK0WSWER" />

<div id="integration-tab" />

<Accordion title="Aba Integração">

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

> 📘 **Importante!**
>
> Como uma all-installs network, a Jampp prefere receber postbacks de todas as novas instalações do seu aplicativo de QUALQUER fonte, inclusive orgânica. Para fazer isso, selecione **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação à Jampp.

### Configurações gerais

**Habilitar a atribuição de view-through**

Alterne isso para LIGADO se quiser atribuir instalações view-through da Jampp. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

### Postbacks padrão

Envie postbacks automáticos para a Jampp após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Jampp.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à Jampp.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Jampp por meio de postbacks.

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pela Jampp.  <br />Obtenha o ID de evento correspondente da Jampp e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Jampp para atribuir as campanhas, os conjuntos de anúncios ou até mesmo anúncios individuais do Jampp. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Jampp.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Jampp.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da Jampp.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, recomendamos limitar o número de IDs do site usados e usar o parâmetro de ID do subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**Estrutura e parâmetros do link de atribuição da AppsFlyer**</Anchor>.

### Configurações de retargeting

Quando ativado, a AppsFlyer reconhece um link como um link de atribuição de <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">retargeting</Anchor>, em vez de um link de aquisição de usuários, ao adicionar `&is_retargeting=true` ao link de registro de cliques. Observe que, no momento, o retargeting é compatível apenas com atribuição por clique, e não com atribuição view-through.  
**Parâmetro do link de atribuição:** is\_retargeting.

O exemplo a seguir abaixo é exibido quando o retargeting está ativado.

1. Link padrão vs. OneLink

Selecione a opção ***link de atribuição padrão*** se:

* Não for necessário realizar link direto com o URL ou
* Você planeja usar apenas <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para deep linking

selecione ***Usar OneLink*** para:

* Usar um único link para aplicativos Android e iOS ou
* Links diretos usando links universais ou do aplicativo

Observe que selecionar o OneLink altera o link de registro de cliques de específico do aplicativo para uma <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">URL do OneLink</Anchor>.

2. Deep Link URL

Use este campo se o link servir para direcionar usuários via deep link a qualquer atividade específica no seu aplicativo.  
**Parâmetro do link de atribuição:** af\_dp  
Você pode encontrar mais informações sobre a solução de deep linking da AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">neste guia.</Anchor>

3. Janela de reengajamento

Defina o período após o reengajamento, onde os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting. Pode definir o valor em dias (1-90), horas (até 23) ou mesmo vitalício.

**Parâmetro do link de atribuição:** af\_reengagement\_window

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas ao Jampp.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o ao Jampp para ser ativado quando os leads clicarem em um anúncio correspondente.

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo entre a impressão e a instalação**. Somente as instalações (primeiras aberturas) que ocorrerem dentro dessa janela de lookback, após uma impressão de anúncio, serão atribuídas ao Jampp, desde que não tenha havido outro clique em anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição view-through aqui</Anchor>.

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o ao Jampp para ser ativado quando um anúncio correspondente for assistido, normalmente por 1 segundo ou mais.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da receita publicitária não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Jampp, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo como ambos. Observe que, mesmo que a atribuição esteja desativada para a Jampp, a aba de permissões está ativa e você pode conceder controle à Jampp.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos seus dados agregados de usuários fidelizados*** - apenas aos dados de usuários fidelizados do próprio parceiro
* ***Permitir acesso aos seus dados agregados de eventos in-app** -* apenas aos dados de eventos in-app do próprio parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

### Permissões da agência

Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* ***Alternância principal*** - defina como Ativado para revelar as opções de permissões da agência
* ***Permitir o acesso ao seu relatório de retenção*** - somente aos próprios dados de retenção da agência
* ***Permitir acesso a dados orgânicos agregados***
* ***Permitir a configuração de postbacks de evento in-app*** - permite que a agência configure o mapeamento de postbacks de evento in-app para si mesma na guia de integração

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-jampp-integration=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o-da-jampp h_01HKW1V0MNP0000KY7SHWQNF16=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o-da-jampp h_01HKW1V0MNSFFFKSQJTDF91NCS=integration-tab activate-partner=ativar-parceiro h_01HKW1V0MN2CQGVKBRQ67SMQ2P=ativar-parceiro h_01HKW1V0MNKR4M4EA5JNT361Y1=importante general-settings=configura%C3%A7%C3%B5es-gerais h_01HKW1V0MNDPJ67HMC0GXYG55B=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HKW1V0MNVEYNY7PZ12QX30QP=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW1V0MN1Q4AR9HASGTCM6AJ=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW1V0MN5HD3TN7AQ1SS8VM7=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW1V0MNDJG02Q0V315N2HAZ=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o retargeting-settings=configura%C3%A7%C3%B5es-de-retargeting h_01HKW1V0MNHZ2JKKEAYWWQ36BA=configura%C3%A7%C3%B5es-de-retargeting clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKW1V0MNKJCETPMASGRYJ368=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW1V0MND4RT49E8TX448Q9H=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HKW1V0MN3VB4HJFDKAH1KAAG=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKW1V0MN86VRX5VPB1K8HACD=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKW1V0MNY13FH61E5AJ27NWJ=cost-tab h_01HKW1V0MNG84N4GKFDACB498E=ad-revenue-tab h_01HKW1V0MNQHRZCMV9WZMFY1G5=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW1V0MNP0K2WYMQ1AHBKH17=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HKW1V0MNV7HGV88HVVPG1397=permiss%C3%B5es-da-ag%C3%AAncia" />

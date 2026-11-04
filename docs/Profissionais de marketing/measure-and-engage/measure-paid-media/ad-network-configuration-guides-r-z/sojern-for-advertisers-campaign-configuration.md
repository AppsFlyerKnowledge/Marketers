---
title: Configuração da campanha do Sojern for Advertisers para anunciantes
metadata:
  keywords:
    - Advertisers
    - Sojern
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-08-07T08:59:30Z'
  edited_at: '2026-09-10T00:25:29Z'
  id: 360001378265
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/360001378265
---
> **Em resumo:** Sojern for Advertisers, um parceiro integrado de ad network da AppsFlyer, é especializado em compra programática para o mercado de viagens.

Para configurar suas campanhas com o Sojern for Advertisers, siga as etapas abaixo.

<div id="setting-up-sojern-for-advertisers" />

## Configuração do Sojern for Advertisers

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

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="note" />

> 📘 **Nota**
>
> Como uma all-installs network, o Sojern for Advertisers prefere receber postbacks de todas as novas instalações do seu aplicativo de QUALQUER fonte, incluindo orgânico. Para fazer isso, selecione **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação ao Sojern for Advertisers.

<div id="general-settings" />

### Configurações gerais

**ID do parceiro**

O Sojern for Advertisers se conecta à AppsFlyer por meio de um ID de parceiro exclusivo. Se você ainda não tiver o ID de parceiro, deverá obtê-lo com o Sojern for Advertisers para continuar com a integração.

![Sojern_msc_new_2.png](https://files.readme.io/35d02000642f8dc768c5bd1b0ca7846b9575900b2e9b3169673840f438815ef1-360002443905.png)

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos ao Sojern for Advertisers após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos ao Sojern for Advertisers.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para disponibilizar toda a sua base de usuários para ser reportada ao Sojern for Advertisers.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com o Sojern for Advertisers por meio de postbacks.

1. Insira o ID de parceiro do Sojern for Advertisers novamente.
2. Ative a opção Postbacks de eventos in-app.
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Adicionar evento** para adicionar um evento de SDK à lista.  
   Para mais detalhes sobre os eventos in-app do Sojern for Advertisers, clique aqui.
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido no lado do Sojern for Advertisers.  <br />Obtenha o ID de evento correspondente do Sojern for Advertisers e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

<div id="event-types" />

### Tipos de evento

O Sojern for Advertisers exige a implementação dos seguintes eventos:

**Hotel**

| Tipo de evento | Eventos do Sojern for Advertisers | Evento SDK | A descrição |
| --- | --- | --- | --- |
| Página inicial | HOME\_PAGE | af\_app\_opened | Aplicativo aberto/trazido para o primeiro plano |
| Resultado da pesquisa | HOTEL\_SEARCH | af\_list\_view | Página de resultados da pesquisa mostrando uma lista de opções |
| Produto | HOTEL\_PRODUCT | af\_content\_view | Visualização de um produto/opção específico nos resultados da pesquisa |
| Confirmação | HOTEL\_CONFIRMATION | af\_compra | Compra do(s) item(s) |

**Voo**

| Tipo de evento | Eventos da Sojern para anunciantes | Evento SDK | A descrição |
| --- | --- | --- | --- |
| Página inicial | HOME\_PAGE | af\_app\_opened | Aplicativo aberto/trazido para o primeiro plano |
| Resultado da pesquisa | FLIGHT\_SEARCH | af\_list\_view | Página de resultados da pesquisa mostrando uma lista de opções |
| Produto | FLIGHT\_PRODUCT | af\_content\_view | Visualização de um produto/opção específico nos resultados da pesquisa |
| Confirmação | FLIGHT\_CONFIRMATION | af\_compra | Compra do(s) item(s) |

**Cruzeiro**

| Tipo de evento | Eventos do Sojern para anunciantes | Evento SDK | A descrição |
| --- | --- | --- | --- |
| Página inicial | HOME\_PAGE | af\_app\_opened | Aplicativo aberto/trazido para o primeiro plano |
| Resultado de pesquisa | CRUISE\_SEARCH | af\_list\_view | Página de resultados de pesquisa com uma lista de opções |
| Produto | CRUISE\_PRODUCT | af\_content\_view | Visualização de um produto/opção específico dos resultados de pesquisa |
| Confirmação | CRUISE\_CONFIRMATION | af\_compra | Compra do(s) item(ns) |

**Carro**

| Tipo de evento | Eventos do Sojern para anunciantes | Evento SDK | A descrição |
| --- | --- | --- | --- |
| Página inicial | HOME\_PAGE | af\_app\_opened | Aplicativo aberto/trazido para o primeiro plano |
| Resultado de pesquisa | CAR\_SEARCH | af\_list\_view | Página de resultados de pesquisa com uma lista de opções |
| Produto | CAR\_PRODUCT | af\_content\_view | Visualização de um produto/opção específico dos resultados de pesquisa |
| Confirmação | CAR\_CONFIRMATION | af\_compra | Compra do(s) item(s) |

**Entretenimento**

| Tipo de evento | Eventos do Sojern para anunciantes | Evento SDK | A descrição |
| --- | --- | --- | --- |
| Página inicial | HOME\_PAGE | af\_app\_opened | Aplicativo aberto/trazido para o primeiro plano |
| Resultado da pesquisa | ENTERTAINMENT\_SEARCH | af\_list\_view | Página de resultados da pesquisa mostrando uma lista de opções |
| Produto | ENTERTAINMENT\_PRODUCT | af\_content\_view | Visualização de um produto/opção específico nos resultados da pesquisa |
| Confirmação | ENTERTAINMENT\_CONFIRMATION | af\_compra | Compra do(s) item(s) |

**Trem**

| Tipo de evento | Eventos do Sojern para anunciantes | Evento SDK | A descrição |
| --- | --- | --- | --- |
| Página inicial | HOME\_PAGE | af\_app\_opened | Aplicativo aberto/trazido para o primeiro plano |
| Resultado da pesquisa | RAIL\_SEARCH | af\_list\_view | Página de resultado da pesquisa mostrando uma lista de opções |
| Produto | PRODUTO\_RAIL | af\_content\_view | Visualização de um produto/opção específico nos resultados de pesquisa |
| Confirmação | CONFIRMAÇÃO\_RAIL | af\_compra | Compra do(s) item(s) |

**Férias**

| Tipo de evento | Eventos do Sojern for Advertisers | Evento SDK | A descrição |
| --- | --- | --- | --- |
| Página inicial | PÁGINA\_INICIAL | af\_app\_opened | Aplicativo aberto/trazido para o primeiro plano |
| Resultado da pesquisa | PESQUISA\_FÉRIAS | af\_list\_view | Página de resultados de pesquisa mostrando uma lista de opções |
| Produto | PRODUTO\_FÉRIAS | af\_content\_view | Visualização de um produto/opção específico nos resultados de pesquisa |
| Confirmação | CONFIRMAÇÃO\_FÉRIAS | af\_compra | Compra do(s) item(s) |

<div id="correct-configuration-of-in-app-events" />

#### Configuração correta dos eventos in-app

Ao configurar uma campanha com o Sojern for Advertisers, é importante definir eventos in-app específicos.

Quando a convenção de nomenclatura do AppsFlyer não estiver disponível, use a chave Param do Sojern for Advertisers.

O Sojern for Advertisers tem quatro tipos de eventos in-app:

* Confirmação
* Produto
* Busca
* Carrinho

A seguir, apresentamos um exemplo de pesquisa e confirmação para o setor de hotéis e voos:

|  | YouTube video player | Chave do parâmetro | Nome do rich in-app event do AppsFlyer |
| --- | --- | --- | --- |
| **Pesquisa de voos** | Tipo de evento | et | valor 'fs' |
|  | Número de viajantes | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Número de adultos | tad | af\_num\_adults |
|  | Número de crianças | tch | af\_num\_children |
|  | Classe de serviço | fc | af\_class |
|  | Somente ida | fow | N/D |
|  | Multi-cidade | fmc | N/D |
|  | Domínio do país do site | dctry | N/D |
|  | Domínio do site | domínio | N/D |
|  | Aeroporto de origem | fa1 | af\_destination\_a |
|  | Aeroporto de destino | fa2 | af\_destination\_b |
|  | Cidade de destino | fc1 | af\_city |
|  | Cidade de origem | fc2 | N/D |
|  | Data de partida | fd1 | af\_departing\_departure\_date |
|  | Data de retorno | fd2 | af\_returning\_departure\_date |
| **Confirmação do voo** | YouTube video player | Param key |  |
|  | Tipo de evento | et | valor 'fc' |
|  | Número de viajantes | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Número de adultos | tad | af\_num\_adults |
|  | Quantidade de crianças | tch | af\_num\_children + af\_num\_infants |
|  | Classe de serviço | fc | af\_class |
|  | Domínio do país do website | dctry | N/D |
|  | Domínio do site | domínio | N/D |
|  | Aeroporto de origem | fa1 | af\_destination\_a |
|  | Aeroporto de destino | fa2 | af\_destination\_b |
|  | Cidade de destino | fc1 | af\_city |
|  | Cidade de origem | fc2 | N/D |
|  | Data de partida | fd1 | af\_departing\_departure\_date |
|  | Data de retorno | fd2 | af\_returning\_departure\_date |
|  | Moeda da compra | fcu | af\_currency |
|  | Preço da compra | fp | af\_revenue |
| **Pesquisa de hotel** | YouTube video player | Param key |  |
|  | Tipo de evento | et | valor 'hs' |
|  | Domínio do país do site | dctry | af\_country |
|  | Cidade de destino | hc1 | af\_city |
|  | Data do check-in | hd1 | af\_date\_a |
|  | Data do check-out | hd2 | af\_date\_b |
|  | Número de viajantes | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Número de adultos | tad | af\_num\_adults |
|  | Quantidade de crianças | tch | af\_num\_children + af\_num\_infants |
|  | Domínio do site | domínio | N/D |
| **Confirmação do hotel** | YouTube video player | Param key |  |
|  | Tipo de evento | et | valor 'hc' |
|  | Domínio do país do site | dctry | N/D |
|  | Cidade de destino | hc1 | af\_city |
|  | Data do check-in | hd1 | af\_date\_a |
|  | Data do check-out | hd2 | af\_date\_b |
|  | Número de viajantes | t | af\_num\_adults + af\_num\_children + af\_num\_infants |
|  | Número de adultos | tad | af\_num\_adults |
|  | Quantidade de crianças | tch | af\_num\_children + af\_num\_infants |
|  | Domínio do site | domínio | N/D |
|  | País de destino | hn1 | af\_country |
|  | Preço de compra | hp | af\_revenue |
|  | Moeda da compra | hcu | af\_currency |

<div id="example" />

> 📄 **Exemplo**
>
> Valores do evento de pesquisa de voos:
>
> Evento in-app: af\_list\_view valores do evento in-app: et=‘fs’&af\_num\_adults=`{number of adults}&af_num_children={number of children}&af_class={service class}&fow={one way}&fmc={multi city}&dctry={website country domain}&af_destination_a={departure airport code}&af_destination_b={arrival airport code}&af_city={destination city}&fc2={origin city}&af_departing_departure_date={YYYY-MM-DD}&af_returning_departure_date={YYYY-MM-DD}`

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Sojern for Advertisers para atribuir campanhas, conjuntos de anúncios ou até mesmo anúncios individuais. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com o Sojern for Advertisers.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Sojern for Advertisers.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas do Sojern for Advertisers.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos que você limite o número de site IDs e use o parâmetro de subsite ID, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de site ID</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros de link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro da janela de lookback podem ser atribuídas ao Sojern for Advertisers.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de cliques aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie isso para o Sojern for Advertisers para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de custos não está disponível para o Sojern for Advertisers.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da guia Receita de Anúncios não está disponível para o Sojern for Advertisers.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nenhuma configuração de permissões está disponível para o Sojern for Advertisers.

</Accordion>

<div data-zendesk-anchors="setting-up-sojern-for-advertisers=configura%C3%A7%C3%A3o-do-sojern-for-advertisers h_01HJS0FHZ6KE2Z93F3SWGEM5B8=configura%C3%A7%C3%A3o-do-sojern-for-advertisers h_01HJS0FHZ7Z9H58D8SWRCM64JH=integration-tab activate-partner=ativar-parceiro h_01HJS0FHZ7SZ1EPN7PDH7EYP0T=ativar-parceiro h_01HJS0FHZ778T3QF4XNM8FCHX0=nota general-settings=configura%C3%A7%C3%B5es-gerais h_01HJS0FHZ7EEAGSCDM4XXJVYC3=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HJS0FHZ78EV1K8DVKN50VJ0B=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJS0FHZ7AN3ZQYF4ZS3X4BVT=configura%C3%A7%C3%B5es-de-eventos-in-app event-types=tipos-de-evento h_01HJS0FHZ7EVPMN25Y1985NFSS=tipos-de-evento correct-configuration-of-inapp-events=configura%C3%A7%C3%A3o-correta-dos-eventos-in-app h_01HJS0FHZ8807QADT9Z35NAWFT=configura%C3%A7%C3%A3o-correta-dos-eventos-in-app h_01HJS0FHZ9J3MWRKF2YCWZ611Z=exemplo h_01HJS0FHZ9ASEYGFWZ681EMZ47=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HJS0FHZ9YVAG37CQQK33RNJ2=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HJS0FHZ9R2SM91Y5WBP002M1=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJS0FHZ9GVGWJEPJ337B1DHE=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJS0FHZ9BXJHQWC9CQWNVANS=cost-tab h_01HJS0FHZ9TARRTF5WZZ6P2V30=ad-revenue-tab h_01HJS0FHZ9J271QZ8SKXKY6Z67=permissions-tab" />

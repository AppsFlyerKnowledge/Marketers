---
title: Configuração da campanha do UC Toutiao Ads
metadata:
  keywords:
    - Advertisers
    - UC Toutiao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-25T05:41:49Z'
  edited_at: '2026-09-16T00:26:51Z'
  id: 115004843026
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/115004843026
---
> **Visão geral:** UC Toutiao Ads, um parceiro integrado de ad network da AppsFlyer, é um dos principais aplicativos agregadores de notícias da China.

<div id="setting-up-uc-toutiao" />

## Configurando o UC Toutiao

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração do UC Toutiao inclui 2 abas ativas: Integração e link de atribuição.

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="activate-partners" />

### Ativar parceiros

Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="default-postbacks" />

### Postbacks padrão

Por padrão, o UC Toutiao recebe postbacks apenas de eventos de nova instalação atribuídos a ele.

<Image align="center" alt="uc-toutiao-integration.png" src="https://files.readme.io/1ed78bd49d9a49d134f5c48655765ad205515752d88528a0a453bd3a091492c0-360002074869.png" />

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com o UC Toutiao por meio de postbacks.

<Image align="center" alt="" src="https://files.readme.io/ae230875cb4d08e7b58249a9bf61a1fcabe2893b1a338c01bdc57b2043deda55-21594057898769.png" />

1. Defina novamente aqui o ID da network do UC Toutiao
2. Mude o botão Postbacks do evento in-app para ATIVO
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido no lado do UC Toutiao.  <br />Obtenha o ID do evento correspondente do UC Toutiao e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - a AppsFlyer envia todos os parâmetros do evento in-app avançado para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - a AppsFlyer envia todos os parâmetros, incluindo o valor da receita (se existir no evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta aba, você pode criar os links de atribuição que deseja enviar ao UC Toutiao para atribuir as campanhas, os conjuntos de anúncios ou até mesmo os anúncios individuais do UC Toutiao. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

<Image align="center" alt="UC_Toutiao_aba_link_de_atribuição.png" src="https://files.readme.io/d8e96914bb9bc703fc7540cd8abc82b745a96066493240952720c2c82d7d21d0-360002880397.png" />

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução no UC Toutiao.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do UC Toutiao.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas do UC Toutiao.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos que você limite o número de IDs de site utilizados e use o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="attribution-link-params.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" />

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**estrutura e parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro da janela de lookback podem ser atribuídas ao UC Toutiao.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<Image align="center" alt="uc-toutiao-click-through.png" src="https://files.readme.io/8128e80c365aa223105260a25aa99a61bd9eeccdf19d311804ed3e66b744ef39-360002074929.png" />

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o ao UC Toutiao para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de custos não está disponível para este parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da receita publicitária não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nenhuma configuração de permissão está disponível para este parceiro.

</Accordion>

## Create conversion at uc toutiao ads

Faça login no UC Toutiao Ads (<Anchor target="_blank" href="https://e.uc.cn/">https://e.uc.cn/</Anchor>) e acesse **Click Promotion Tools** >> **Click Conversion Tools** >> **Create Conversion**

<Image align="center" alt="Toutiao_4.png" src="https://files.readme.io/40e4c3f26faf2cf928fe874398a7e505d100e717669867fc8a55b8b9fec1f021-115016024743.png" />

Insira as informações relacionadas ao aplicativo >> **Click Confirm** >> **Generate 2-dimension code**

Aplicativo Android:

<Image align="center" alt="Toutiao_5.png" src="https://files.readme.io/8db1f985882f847aad08e4e46710bd9af8a95b62e0a0b488d5242879cd11b7bd-115015832006.png" />

iOS App:

<Image align="center" alt="Toutiao_6.png" src="https://files.readme.io/18b8ba97b8792db66ec4874269bf1b6ccb21ad68016a57e52534f4e97835cc92-115016025123.png" />

Use o aplicativo Alipay ou o aplicativo Dingding para escanear o código de 2 dimensões e instalar seu Aplicativo. Conclua o teste de conversão e então o status dessa conversão ficará ativo.

6. Crie seus anúncios

Crie seu anúncio acessando: **Nível da unidade de anúncio** >> **Seção de configuração de lances** >> **Ative a conversão**

<Image align="center" alt="Toutiao_7.png" src="https://files.readme.io/f2c49499432c3c358d737544ea02cb5b1e634244313606a62102707dd8a3c31e-115015832146.png" />

<div data-zendesk-anchors="setting-up-uc-toutiao=configurando-o-uc-toutiao h_01HKW6Y1PVGS22BXK54VW8C488=configurando-o-uc-toutiao h_01HKW6Y1PWJEJHCCY5WM8AYNGE=integration-tab activate-partners=ativar-parceiros h_01HKW6Y1PWX3TMM41S78MJ21C1=ativar-parceiros default-postbacks=postbacks-padr%C3%A3o h_01HKW6Y1PWRZNRX6061KFECTDN=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6Y1PWRMK1H7QCW1GQWAA7=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW6Y1PW95EWPGP09CCJF97M=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW6Y1PWVTGGNX96AWVZJ9PP=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKW6Y1PWEW2FWN8K5S8DKQJJ=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6Y1PWKPJ09G70XMQG8H1S=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW6Y1PWFS5X835MYJG0CVJ0=cost-tab h_01HKW6Y1PWJW4EW33MYRDN2FJB=ad-revenue-tab h_01HKW6Y1PWDWN4KWMA1KX5FYDT=permissions-tab h_01HKW6Y1PWVMM70F6MJVCJYKT3=create-conversion-at-uc-toutiao-ads" />

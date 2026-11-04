---
title: Configuração da campanha da StartApp
metadata:
  keywords:
    - StartApp
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
  created_at: '2016-06-30T10:55:10Z'
  edited_at: '2026-09-08T00:25:07Z'
  id: 210042746
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/210042746
---
> **Em resumo:** a StartApp, parceira integrada de ad network da AppsFlyer, é uma empresa de tecnologia mobile orientada por insights que permite aos seus parceiros oferecer as experiências mobile mais satisfatórias do mundo para seus usuários. Além da atribuição mobile baseada em cliques, a StartApp oferece atribuição de custo, retargeting e view-through, que podem ser registrados na AppsFlyer.

Para configurar suas campanhas com a StartApp, siga as etapas abaixo.

<div id="setting-up-startapp" />

## Configuração da StartApp

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração da StartApp inclui 4 abas ativas: Integração, link de atribuição, Custo e Permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="tip" />

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar o toggle **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="note" />

> 📘 **Nota**
>
> Como uma all-installs network, a StartApp prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER canal, inclusive canais orgânicos. Para fazer isso, selecione **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a StartApp.

<div id="general-settings" />

### Configurações gerais

**Habilitar a atribuição de view-through**

Ative essa opção se quiser atribuir instalações por view-through da StartApp. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para a StartApp após as instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à StartApp.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à StartApp.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a StartApp por meio de postbacks.

1. Mude o botão Postbacks do evento in-app para ATIVO
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos S2S.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido no lado da StartApp.  <br />Obtenha o ID do evento correspondente da StartApp e configure no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar à StartApp para atribuir as campanhas, os conjuntos de anúncios ou até mesmo os anúncios individuais da StartApp. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a StartApp.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da StartApp.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da StartApp.  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e usar o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinantes** - use qualquer um dos 5 parâmetros de assinantes para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para a realização de agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de Atribuição da AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configurações de retargeting

Quando ativado, a AppsFlyer reconhece um link como um link de atribuição de <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">retargeting</Anchor>, em vez de um link de aquisição de usuários, ao adicionar `&is_retargeting=true` ao link de registro de cliques. Observe que, atualmente, o retargeting é compatível apenas com atribuição click-through, e não com atribuição view-through.  
**Parâmetro do link de atribuição:** is\_retargeting.

O exemplo a seguir abaixo é exibido quando o retargeting está ativado.

1. Link padrão vs. OneLink

Selecione a opção ***link de atribuição padrão*** se:

* Não for necessário realizar link direto com o URL ou
* Planeja usar apenas <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para Deep Linking

select ***Usar OneLink*** para:

* Usar um único link para aplicativos Android e iOS ou
* Links diretos usando links universais ou do aplicativo

Observe que selecionar o OneLink altera o link de registro de cliques de específico do aplicativo para uma <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">URL do OneLink</Anchor>.

2. Deep Link URL

Use este campo se o link se destinar a fazer deep linking de usuários para qualquer atividade específica no seu aplicativo.  
**Parâmetro do link de atribuição:** af\_dp  
Você pode encontrar mais informações sobre a solução de Deep linking da AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">neste guia.</Anchor>

3. Janela de reengajamento

Defina o período após o reengajamento, onde os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting. Pode definir o valor em dias (1-90), horas (até 23) ou mesmo vitalício.

**Parâmetro do link de atribuição:** af\_reengagement\_window

<div id="click-through-attribution" />

### Atribuição de click-through

Esta barra deslizante permite definir o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro da janela de lookback podem ser atribuídas à StartApp.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a StartApp para ser ativado quando os leads clicarem em um anúncio correspondente.

<div id="view-through-attribution-lookback-window" />

### Janela de retrospetiva da atribuição por visualização

Esta barra deslizante permite definir o **tempo máximo entre a impressão e a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro desta janela de lookback, após uma impressão de anúncio, serão atribuídas à StartApp, desde que não tenha havido nenhum outro clique em anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição view-through aqui</Anchor>.

<div id="impressions-attribution-link" />

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o para a StartApp para ser ativado quando um anúncio correspondente for assistido, normalmente por 1 segundo ou mais.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A StartApp envia automaticamente dados de custo de CPI criptografados no link de atribuição para todas as instalações.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da receita publicitária não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à StartApp, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a StartApp, a aba de permissões está ativa e você pode conceder controle à StartApp.

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* *Permitir a configuração de postbacks de evento in-app* – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-startapp=configura%C3%A7%C3%A3o-da-startapp h_01HJS066SXX0W7DC81VDREFN1T=configura%C3%A7%C3%A3o-da-startapp h_01HJS066SXGFZ2FWKQ4F6VR081=dica h_01HJS066SX3R7N34PTFWCP1W5Y=integration-tab activate-partner=ativar-parceiro h_01HJS066SXE913QSB0CYQMSY04=ativar-parceiro h_01HJS066SX19P84WN0BT4KYC12=nota general-settings=configura%C3%A7%C3%B5es-gerais h_01HJS066SX9D6FMANAK0GZ303P=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HJS066SYHCHF56ZYD51JXYSK=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJS066SY0SC8R4098V4V19HA=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJS066SYSBHM3C3HH8WD2DYE=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HJS066SYVDYD2Q8K13CQ8HHR=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o retargeting-settings=configura%C3%A7%C3%B5es-de-retargeting h_01HJS066SY7ZB2ZP98JN7N4M6J=configura%C3%A7%C3%B5es-de-retargeting clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HJS066SYT59WAV9RGYBZXAY9=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJS066SYF3TAZBFNPMAV40TP=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HJS066SYMRX14D36G4MB6CWW=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HJS066SYECNKHCRW4SE7FPQF=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HJS066SYNY9NFSV2YQRJJ08R=cost-tab h_01HJS066SYVQ9C5G21VARRJ7FR=ad-revenue-tab h_01HJS066SYVSNZDT3Z89G0HRWS=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HJS066SYH20AG9XFNDWFBM0W=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />

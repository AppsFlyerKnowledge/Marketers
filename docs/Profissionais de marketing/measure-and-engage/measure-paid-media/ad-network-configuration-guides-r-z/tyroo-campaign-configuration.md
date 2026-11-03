---
title: Configuração de campanha da Tyroo
metadata:
  keywords:
    - Advertisers
    - Tyroo
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-03T11:32:42Z'
  edited_at: '2026-09-10T00:25:52Z'
  id: 208270836
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/208270836
---
> **Em resumo:** A Tyroo, uma parceira integrada de ad network da AppsFlyer, é uma plataforma líder global em aquisição de usuários mobile e monetização. Além da atribuição mobile baseada em cliques, a Tyroo oferece atribuição de custo e view-through, que pode ser registrada na AppsFlyer.

Para configurar suas campanhas com a Tyroo, siga as etapas abaixo.

## Configurando a Tyroo

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

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar o toggle ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

> 📘 **Nota**
>
> Como uma all-installs network, a Tyroo prefere receber postbacks para todas as novas instalações do seu Aplicativo de QUALQUER fonte, inclusive orgânico. Para fazer isso, selecione **eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a Tyroo.

### Configurações gerais

**ID do parceiro**

A Tyroo se conecta à AppsFlyer por meio de uma chave de ação exclusiva. Se você ainda não tem a chave de ação, deve obtê-la com a Tyroo para continuar com a integração.

**Habilitar a atribuição de view-through**

Ative esta opção se quiser atribuir instalações por view-through da Tyroo. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

### Postbacks padrão

Envie postbacks automáticos para a Tyroo após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Apenas eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Tyroo.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à Tyroo.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Tyroo por meio de postbacks.

1. Ative postbacks de eventos in-app
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido pela Tyroo.  <br />Obtenha o ID de evento correspondente da Tyroo e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar à Tyroo para atribuir as campanhas, os conjuntos de anúncios ou até mesmo os anúncios individuais da Tyroo. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Tyroo.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Tyroo.  
  **Parâmetro do link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos em campanhas específicas da Tyroo.  
  **Parâmetro do link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos que você limite o número de IDs de site usados e utilize o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição do AppsFlyer**</Anchor>.

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas à Tyroo.

**Parâmetro do link de atribuição:** af\_click\_lookback

Para obter mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique, clique aqui</Anchor>.

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o para a Tyroo para ser ativado quando os leads clicarem em um anúncio correspondente.

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo da impressão até a instalação**. Somente as instalações (primeiras aberturas) que ocorrerem dentro desta janela de lookback, após uma impressão de anúncio, serão atribuídas à Tyroo, desde que não tenha havido nenhum outro clique em anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Obtenha mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição view-through aqui</Anchor>.

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o para a Tyroo para ser ativado quando um anúncio correspondente for visualizado, geralmente por 1 segundo ou mais.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A Tyroo envia automaticamente dados de custo de CPI no link de atribuição para todas as instalações.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Tyroo, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a Tyroo, a aba de permissões está ativa e você pode conceder controle à Tyroo.

Use estes botões para dar à ad network as permissões para gerenciar a própria configuração do seu aplicativo: Permissões da ad network

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* *Permitir a configuração de postbacks de evento in-app* – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-tyroo=configurando-a-tyroo h_01HJZTZ361TE694SVPQTN8Q4C1=configurando-a-tyroo h_01HJZTZ361V5G81NBA1G0ZBXJG=integration-tab activate-partner=ativar-parceiro h_01HJZTZ361FKYED35K4E57DEJ4=ativar-parceiro h_01HJZTZ361QM6Z3N693N3PJ1Z9=nota general-settings=configura%C3%A7%C3%B5es-gerais h_01HJZTZ362XG66Q54JRATHJW9X=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HJZTZ3621ZWG5TZD76Z80DHE=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJZTZ362WMPD0C1HMG8HC2HD=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJZTZ3627FHZS6J5FABPJJ1Q=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HJZTZ362TG648JZEXWX3MK5P=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HJZTZ362TCHGN0MGRA0B9Z7P=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HJZTZ36282E6VNNH740AF9EW=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HJZTZ362V11V157Q2NFN550W=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HJZTZ362ZF2FY83NMD5ZJ89J=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HJZTZ362JBBAZ5RDWJ03EE2X=cost-tab h_01HJZTZ36323B1PET2X3FPD1H1=ad-revenue-tab h_01HJZTZ3637M1AMNTWXV9NPNGV=permissions-tab" />

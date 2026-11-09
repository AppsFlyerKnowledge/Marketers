---
title: Configuração da campanha da Nativex (anteriormente Mobvista)
metadata:
  keywords:
    - mobvista
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
  created_at: '2016-03-28T09:15:13Z'
  edited_at: '2026-08-19T00:25:30Z'
  id: 208209476
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/208209476
---
> **Em resumo:** a Nativex, parceira integrada da AppsFlyer, é uma plataforma de marketing mobile que oferece soluções de aquisição de usuários, análises e monetização para desenvolvedores e marcas mobile do mundo todo. Além da atribuição mobile baseada em cliques, a Nativex também oferece atribuição por custo e view-through, que você pode registrar com a AppsFlyer.

<Image align="center" alt="nativex.png" src="https://files.readme.io/840450215d38dc171452049ce1e9ce8c5f289e489fcb985a8d7ecb745fd11ede-49783409596049.png" />

<div id="setting-up-nativex" />

## Configurando a Nativex

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração da Nativex inclui 4 abas ativas: Integração, link de atribuição, custo e permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

<div id="tip" />

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="activate-partners" />

### Ativar parceiros

Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da guia de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="general-settings" />

### Configurações gerais

**Mobvista\_campuuid**

A Nativex se conecta com a AppsFlyer por meio de um ID de network exclusivo. Se você ainda não tiver o ID de network, deverá obtê-lo com a Nativex para continuar com a integração.

**Habilitar a atribuição de view-through**

Ative esta opção se quiser atribuir instalações view-through da Nativex. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para a Nativex após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Nativex.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à Nativex.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a Nativex por meio de postbacks.

1. Defina novamente aqui o ID de network da Nativex
2. Mude o botão Postbacks do evento in-app para ATIVO
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
5. Preencha os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido pela Nativex.  <br />Obtenha o ID do evento correspondente da Nativex e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar à Nativex para atribuir as campanhas, os conjuntos de anúncios ou até mesmo anúncios individuais da Nativex. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

Adicionar parâmetros ao link de atribuição aqui permite que você faça análises detalhadas posteriormente. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione para comparar diferentes campanhas em execução com a Nativex.  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Nativex.  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de conjuntos de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da Nativex.  
  **Parâmetro do link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos que você limite o número de IDs do site usados e use o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder as limitações de ID do site</Anchor>.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a Estrutura e os Parâmetros do Link de Atribuição da AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que acontecerem dentro da janela de lookback podem ser atribuídas à Nativex.

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie-o à Nativex para ser ativado quando os leads clicarem em um anúncio correspondente.

<div id="view-through-attribution-lookback-window" />

### Janela de retrospetiva da atribuição por visualização

Essa barra deslizante permite definir o **tempo máximo desde a impressão até a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro desta janela de lookback, após uma impressão de anúncio, serão atribuídas à Nativex, desde que não tenha havido nenhum outro clique de anúncio relevante.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">atribuição view-through aqui</Anchor>.

<div id="impressions-attribution-link" />

### Link de atribuição para impressões

O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o à Nativex para ser ativado quando um anúncio correspondente for assistido, normalmente por 1 segundo ou mais.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A Nativex envia automaticamente dados de custo de CPI criptografados no link de atribuição para todas as instalações.

Para obter a lista completa de parceiros que oferecem suporte aos dados de custo, clique <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#informações-adicionais">aqui</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Nativex, quer o parceiro atue como ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para a Nativex, a aba de permissões está ativa e você pode conceder controle à Nativex.

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

Use essas chaves seletoras para conceder à Nativex permissões para gerenciar a própria configuração do seu Aplicativo:

* ***Permitir a configuração da integração*** - permite que a Nativex configure a aba de integração (exceto postbacks de eventos in-app)
* ***Permitir a configuração de postbacks de eventos in-app*** - permite que a Nativex configure, na aba de integração, o mapeamento de postbacks de eventos in-app para si mesma
* ***Permitir acesso ao seu relatório de retenção*** - somente aos dados de retenção da própria Nativex
* ***Permitir acesso ao seu dashboard do Protect360*** - somente aos próprios dados do Protect360 da Nativex e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

<div id="agency-permissions" />

### Permissões da agência

Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* ***Opção principal*** - defina como Ativado para revelar as opções de permissões da agência
* ***Permitir acesso ao seu relatório de retenção*** - somente aos próprios dados de retenção da agência
* ***Permitir acesso a dados orgânicos agregados***
* ***Permitir a configuração de postbacks de eventos in-app*** - permite que a agência configure o mapeamento de postbacks de eventos in-app para si mesma na guia de integração

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mobvista=configurando-a-nativex h_01HKW7VFYJ6CZP5JD29YAS3AAH=configurando-a-nativex h_01HKW7VFYJ02HSZ963PX5H38ZS=dica h_01HKW7VFYJXNP3AP7FZPFBRHA7=integration-tab activate-partners=ativar-parceiros h_01HKW7VFYJB9F9M8KGEA52ZQGD=ativar-parceiros general-settings=configura%C3%A7%C3%B5es-gerais h_01HKW7VFYJDAT6G9VSC5H50Y9K=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HKW7VFYJVW66881ZHG2Q1B31=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW7VFYJA1919WZ0XPY8SP98=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW7VFYJKD1BHDDAG8VKFTYB=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKW7VFYJFGKPDDBT09T3BXAN=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKW7VFYJMYJ508P8E3B5WNN2=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKW7VFYJ6N5JMZTDBAKX02A4=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o h_01HKW7VFYK0YRYZXMPFRJNQJKP=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKW7VFYKD6S2NZ280VXRQT1F=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01HKW7VFYKDN59CAGE3JC11G7D=cost-tab h_01HKW7VFYK3AGC81SBA00C43AD=ad-revenue-tab h_01HKW7VFYKS66EAP51QECZPFQH=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW7VFYKRE972AJAM499H241=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HKW7VFYK1T10MR5AJ436C2NS=permiss%C3%B5es-da-ag%C3%AAncia" />

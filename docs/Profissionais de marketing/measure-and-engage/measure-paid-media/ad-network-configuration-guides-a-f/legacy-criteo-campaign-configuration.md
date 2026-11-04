---
title: '[Legacy] Configuração da campanha do Criteo'
deprecated: true
metadata:
  keywords:
    - Campaign
    - SDK
    - Configure
    - Criteo
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
  created_at: '2015-06-03T08:06:04Z'
  edited_at: '2026-09-08T00:22:56Z'
  id: 207033946
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/207033946
---
> **Resumo:** Criteo (Legacy), um parceiro integrado de ad network da AppsFlyer, é uma empresa de retargeting personalizado que trabalha com varejistas online para veicular anúncios gráficos online personalizados a consumidores que já visitaram o site do anunciante. Além da atribuição mobile baseada em cliques, o Criteo (Legacy) também oferece retargeting, que pode ser registrado com a AppsFlyer.

<div id="setting-up-criteo-legacy" />

## Configurando o Criteo (Legacy)

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração do Criteo (Legacy) inclui 4 abas: Integração, Link de atribuição, Enriquecimento de dados e Permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="tip" />

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partners" />

### Ativar parceiros

No **primeira visita** aqui, você deve ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da guia de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique aqui.**

<div id="note" />

> 📘 **Nota**
>
> Como uma ALL-Installs network, o Criteo (Legacy) prefere receber postbacks de todas as novas instalações do seu aplicativo de QUALQUER fonte, incluindo orgânica. Recomenda-se selecionar **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação ao Criteo (Legacy).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos ao Criteo (Legacy) após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos ao Criteo (Legacy).  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada ao Criteo (Legacy).

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com o Criteo (Legacy) por meio de postbacks.

1. Ative a opção Postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome ou ID exclusivo de cada evento, conforme definido no lado do Criteo (Legacy).  <br />Obtenha o ID do evento correspondente no Criteo (Legacy) e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Nesta guia, você pode criar os links de atribuição que deseja enviar ao Criteo (Legacy) para atribuir as campanhas, os conjuntos de anúncios ou até mesmo os anúncios individuais do Criteo (Legacy). Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* **Campanha** - adicione-a para comparar diferentes campanhas em execução com o Criteo (Legacy).  
  **Parâmetro de link de atribuição:** c
* **Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas do Criteo (Legacy).  
  **Parâmetro de link de atribuição:** af\_adset
* **Nome do anúncio** - defina nomes de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas do Criteo (Legacy).  
  **Parâmetro de link de atribuição:** af\_ad
* **ID do site** e **ID do subsite** - defina o parâmetro ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs de site usados e usar o parâmetro de ID de subsite, para evitar exceder as limitações de ID de site.  
  **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* **Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados.  
  **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configurações de retargeting

Quando ativado, o AppsFlyer reconhece um link como um link de atribuição de <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">retargeting</Anchor>, em vez de um link de aquisição de usuários, ao adicionar `&is_retargeting=true` ao link de registro de cliques. Observe que, atualmente, o retargeting é compatível apenas com a atribuição por clique, e não com a atribuição view-through.  
**Parâmetro do link de atribuição:** is\_retargeting.

A configuração a seguir é exibida quando o retargeting está ativado.

1. Link padrão vs. OneLink

Selecione a opção ***link de atribuição padrão*** se:

* Não for necessário realizar link direto com o URL ou
* Planeje usar apenas <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para Deep linking

select ***Usar OneLink*** para:

* Usar um único link para aplicativos Android e iOS ou
* Links diretos usando links universais ou do aplicativo

Observe que selecionar OneLink altera o link de registro de cliques de específico do aplicativo para uma <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">URL do OneLink</Anchor>.

2. Deep Link URL

Use este campo se o link servir para fazer deep linking de usuários para qualquer atividade específica no seu aplicativo.  
**Parâmetro do link de atribuição:** af\_dp  
Você pode encontrar mais informações sobre a solução de deep linking da AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">neste guia.</Anchor>

3. Janela de reengajamento

Defina o período após o reengajamento, onde os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting. Pode definir o valor em dias (1-90), horas (até 23) ou mesmo vitalício.

**Parâmetro do link de atribuição:** af\_reengagement\_window

<div id="click-through-attribution" />

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro da janela de lookback podem ser atribuídas à Criteo (Legacy).

**Parâmetro do link de atribuição:** af\_click\_lookback

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie isso para a Criteo (Legacy) para ser ativado quando os leads clicarem em um anúncio correspondente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de dados de custo via API não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Criteo (Legacy), independentemente de o parceiro atuar como ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para a Criteo (Legacy), a aba de permissões está ativa e você pode conceder controle à Criteo (Legacy).

**Permissões da rede de anúncios**

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

<div id="agency-permissions" />

### Permissões da agência

Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* ***Opção principal*** - defina como Ativado para revelar as opções de permissões da agência
* ***Permitir a configuração de postbacks de evento in-app*** - permite que a agência configure o mapeamento de postbacks de evento in-app para si mesma na guia de integração
* ***Permitir o acesso ao seu relatório de retenção*** - somente aos próprios dados de retenção da agência
* ***Permitir acesso a dados orgânicos agregados***
* ***Permitir a configuração de postbacks de evento in-app*** - permite que a agência configure o mapeamento de postbacks de evento in-app para si mesma na guia de integração

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-criteo-legacy=configurando-o-criteo-legacy h_01HKWB5RYT5Y39MWXD6F57T4MN=configurando-o-criteo-legacy h_01HKWB5RYT26M2R3HMG35A51GA=dica h_01HKWB5RYV88ATKSS55B29GT6F=integration-tab activate-partners=ativar-parceiros h_01HKWB5RYVSMPRK7RD6QN8BANB=ativar-parceiros h_01HKWB5RYVSK56GNW4805XDFCT=nota default-postbacks=postbacks-padr%C3%A3o h_01HKWB5RYV68B5XWQA5D9W4ZM9=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKWB5RYVCPM15F8DWBZ3BEMZ=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKWB5RYV9TKBY8V3R4N8FWNM=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o h_01HKWB5RYVKXJT3MFGS7A8EKB9=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o retargeting-settings=configura%C3%A7%C3%B5es-de-retargeting h_01HKWB5RYVYMY772BDY4Z83N84=configura%C3%A7%C3%B5es-de-retargeting clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HKWB5RYV6Z028TM6YF0X6PWQ=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKWB5RYVGK3DT0AB89YPZS22=clique-no-link-de-atribui%C3%A7%C3%A3o h_01HKWB5RYVZ367Y3GY329608G3=cost-tab h_01HKWB5RYVNTRC44XVZ3H7M2H5=permissions-tab agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HKWB5RYV6MSCFCB387342NJ4=permiss%C3%B5es-da-ag%C3%AAncia" />

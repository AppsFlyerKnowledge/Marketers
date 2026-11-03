---
title: Configuração da campanha da Criteo
metadata:
  keywords:
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
  created_at: '2018-03-27T06:56:54Z'
  edited_at: '2026-09-10T00:24:05Z'
  id: 360000601785
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/360000601785
---
> **Visão geral:** a Criteo, uma parceira integrada de ad network da AppsFlyer, impulsiona o crescimento por meio de tecnologia de aprendizado de máquina, dados e performance em escala, além de ROI mensurável para seus clientes. Além da atribuição mobile baseada em cliques, a Criteo também oferece atribuição de retargeting, que pode ser registrada com a AppsFlyer.

## Configurando a Criteo

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

### Ativar parceiro

Na **primeira visita**, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para mais informações sobre a ativação de parceiros, por favor clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

> 📘 **Observação:**
>
> Como uma all-installs network, a Criteo prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER fonte, inclusive orgânica. Recomenda-se selecionar **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a Criteo.

### Postbacks padrão

Envie postbacks automáticos para a Criteo após as instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à Criteo.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à Criteo.

### Configurações de eventos in-app

Nesta seção, mapeie seus eventos da AppsFlyer com a Criteo por meio de postbacks.

1. Ative a opção Postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a este parceiro** para eventos provenientes **apenas** de usuários atribuídos a este parceiro.  
   **- Eventos atribuídos a qualquer parceiro ou orgânico** para que toda a sua base de usuários fique disponível para ser reportada ao parceiro.
3. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pela Criteo.  <br />Obtenha o ID do evento correspondente da Criteo e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

> ❗️ **Aviso**
>
> <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#what-are-complex-inapp-events-and-how-do-i-set-them-up">Eventos in-app complexos</Anchor> causam problemas de postback com a Criteo. Se você precisar que o evento seja totalmente mapeado com a Criteo, envie eventos separados por ação do usuário (por exemplo, envie um evento Adicionar ao carrinho para cada item adicionado). Use os dados brutos de eventos in-app para agrupar esses eventos.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. 

**Atenção**:

* Os dados de custo requerem uma assinatura do ROI360.
* Os dados de custo da Criteo podem ser recebidos apenas para downloads provenientes do Google Play ou da Apple App Store. Para Android, os dados de custo para lojas de aplicativos Android de terceiros não são compatíveis.
* O custo da agência só está disponível por <Anchor target="_blank" href="/marketers/pt/docs/view-aggregated-cost-data-for-attribution-links">clique</Anchor>; não via integração de API.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração de receita publicitária não está disponível para a Criteo.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à Criteo, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a Criteo, a aba de permissões está ativa e você pode conceder controle à Criteo.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

Permissões da rede de anúncios

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-criteo=configurando-a-criteo h_01HKWB41KJ4XG0SGX69NHGYBYD=configurando-a-criteo h_01HKWB41KJR5H4TDH80AG7JEYQ=integration-tab activate-partner=ativar-parceiro h_01HKWB41KJ2Z3RHNQ2XYJXJBKC=ativar-parceiro h_01HKWB41KJRHZCFJ0CF7K3SMAS=observa%C3%A7%C3%A3o default-postbacks=postbacks-padr%C3%A3o h_01HKWB41KJHZM1P6ZKJ1Q10C7D=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKWB41KJSDADQZYVAD13QYEH=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HDBZW9XF33FHR418MNVH6BS2=aviso h_01HKWB41KKPPSGDVB1EKDXD6A5=attribution-link-tab h_01HKWB41KKW3EEF3VVMS9BSZ53=cost-tab h_01HKWB41KKFT61V0TWGM5P5X8H=ad-revenue-tab h_01HKWB41KKPFBWKE748V5FD5Y3=permissions-tab" />

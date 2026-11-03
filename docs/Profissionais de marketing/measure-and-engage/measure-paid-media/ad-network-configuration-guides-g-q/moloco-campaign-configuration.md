---
title: Configuração de campanha da MOLOCO
metadata:
  keywords:
    - Advertisers
    - Moloco
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-16T07:37:12Z'
  edited_at: '2026-08-19T00:25:25Z'
  id: 360000691978
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/360000691978
---
> **Em resumo:** a MOLOCO, parceira integrada da AppsFlyer, transforma dados de usuário em performance de anúncios, permitindo que empresas mobile executem programas de marketing e monetização de publicidade.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/moloco.png?v=1" width="149px" />

## Configurando a MOLOCO

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração da MOLOCO inclui 3 abas ativas: integração, link de atribuição e permissões. Clique nos itens abaixo para ler sobre a configuração das abas.

Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

> 👍 **Dica**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

> 📘 **Nota**
>
> Como uma network de todas as instalações, a MOLOCO prefere receber postbacks de todas as novas instalações do seu Aplicativo de qualquer fonte, incluindo orgânica. Para fazer isso, selecione **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação para a MOLOCO.

### Configurações gerais

**Habilitar a atribuição de view-through**

Ative esta opção se quiser atribuir instalações view-through da MOLOCO. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

### Postbacks padrão

Envie postbacks automáticos para a MOLOCO após instalações e reengajamentos de usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à MOLOCO.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à MOLOCO.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a MOLOCO por meio de postbacks.

1. Ative a opção Postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a este parceiro** para eventos provenientes **apenas** de usuários atribuídos a este parceiro  
   **- Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada ao parceiro
3. Clique em **Adicionar evento** para adicionar um evento de SDK à lista.
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **Evento na AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados"> mapeamento de eventos personalizados.</Anchor></li></ul> |
| **mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** obtenha o ID do evento correspondente do parceiro.</li><li>**Caixa suspensa:** selecione o evento AppsFlyer predefinido mais adequado.</li><li>**Sem alterações**: envie os eventos como eles estiverem, sem mapeamento de nomes.</li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Somente este parceiro**: enviar postbacks somente quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: envie postbacks para eventos atribuídos a qualquer parceiro, bem como eventos orgânicos. De acordo com Unity Ads, esta opção é recomendada.</li></ul> |
| **incluindo** | <ul><li>**Nenhum dado (padrão)**: enviar somente o evento em si sem o valor do evento.</li><li>**Valores e receita**: envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento). De acordo com Unity Ads, esta opção é recomendada.</li><li>**Valores sem receita**: enviar todos os parâmetros **excluindo** o valor da receita.</li></ul> |

> 📘 **Nota**
>
> Você pode enviar <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postbacks de receita de anúncios</Anchor> para a MOLOCO usando o`af_ad_revenue` evento para que ela possa otimizar campanhas.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

Os dados de ontem ficam disponíveis na MOLOCO aproximadamente às 4h (dependendo das configurações de fuso horário na sua conta da MOLOCO). Por exemplo, se o evento ocorreu na segunda-feira, os dados de custo podem ser coletados pela AppsFlyer na terça-feira aproximadamente às 4h. Depois de coletar os dados de custo da MOLOCO, a AppsFlyer analisa e prepara os dados e, assim que esse processo for concluído, os dados poderão ser consumidos.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no painel de status de integração de custo (e receita de publicitária) ou no painel individual da ad network.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A integração da receita publicitária não está disponível para este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas à MOLOCO, independentemente de o parceiro atuar como ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para a MOLOCO, a aba de permissões está ativa e você pode conceder controle à MOLOCO.

#### ![MOLOCO_permissions.png](https://files.readme.io/f443306f1b56197709308c0a33e436dc26adc7a0e80e6c2887edc63a5697b6d4-360002616197.png) Permissões da rede de anúncios

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* **Permitir a configuração da integração** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* **Permitir a configuração de postbacks de evento in-app** - permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na aba Integração
* **Permitir o acesso ao seu relatório de retenção** - somente aos próprios dados de retenção do parceiro
* **Permitir o acesso ao dashboard do Protect360** - apenas aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-moloco=configurando-a-moloco h_01HBB9EEMJRHWC21713D60725N=configurando-a-moloco h_01HBB9EEMJQ9VAMJMYG2T5FX0S=dica h_01HBB9EEMJ7X92Y5TK4YXXGSZX=integration-tab activate-partner=ativar-parceiro h_01HBB9EEMJ0EW14NZE9WCKJR1M=ativar-parceiro h_01HBB9EEMJ55BQDJ1ZEJT136ZF=nota general-settings=configura%C3%A7%C3%B5es-gerais h_01HBB9EEMJ2XSWFQZZFJ7J54VY=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HBB9EEMJV2SS4VJW0HW8D12R=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HBB9EEMJE2X04XZGMSJSSXAT=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HBB9EEMJ6WA79D7R4BG8S9HS=nota-1 h_01HBB9EEMJXGFHY28K2DDHKBF8=attribution-link-tab h_01HBB9EEMJT7VSNFQJC86TS1YX=cost-tab h_01HBB9EEMJ61WDHNPKMW5A1YKM=ad-revenue-tab h_01HBB9EEMJ3Z40S2A6FZG7RJ6K=permissions-tab ad-network-permissions=-permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HBB9EEMJ54Y8KJBK4395ENPJ=-permiss%C3%B5es-da-rede-de-an%C3%BAncios" />

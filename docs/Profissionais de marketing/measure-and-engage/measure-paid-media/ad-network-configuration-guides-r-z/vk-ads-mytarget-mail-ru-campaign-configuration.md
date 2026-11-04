---
title: Configuração da campanha do VK Ads (myTarget, Mail.ru)
metadata:
  keywords:
    - mytarget
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
  created_at: '2016-03-28T11:53:13Z'
  edited_at: '2026-09-10T00:25:57Z'
  id: 209731913
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/209731913
---
> **Em resumo:** o VK Ads é uma plataforma de anúncios mobile voltada a conectar anunciantes a usuários mobile falantes de russo. Com o VK Ads, os anunciantes podem veicular publicidade segmentada em redes sociais (Vkontakte, Odnoklassniki, Moi Mir) e no Mail. Ru Group. Além da atribuição mobile baseada em cliques, o VK Ads também oferece atribuição de retargeting.

![](https://cdn.appsflyer.com/marketplace/static/logo/mail.ru.png?v=1)

<div id="setting-up-vk-ads" />

## Configurando o VK Ads

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

<div id="activate-partners" />

### Ativar parceiros

Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para mais informações sobre a ativação de parceiros, por favor clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="general-settings" />

### Configurações gerais

As seguintes configurações gerais estão disponíveis para o VK Ads.

<div id="app-id" />

### ID da aplicação

Este campo não é obrigatório, e sua funcionalidade ainda será definida. Em caso de dúvidas adicionais, entre em contato com o VK Ads.

<div id="enable-view-through-attribution" />

### Ative a atribuição de view-through

Ative se quiser atribuir instalações view-through do VK Ads. O cursor de lookback de view-through está disponível na aba [***Link da atribuição***](/docs/vk-ads-mytarget-mail-ru-campaign-configuration#attribution-link-tab).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para o VK Ads após as instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos ao VK Ads.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para reportar ao VK Ads.

<div id="in-app-events-postbacks" />

### Postbacks de eventos in-app

Nesta seção, você pode configurar postbacks de eventos in-app que são enviados ao VK Ads.

1. Ativar ***postbacks de eventos in-app***
2. Escolha se deseja reportar **eventos selecionados** ao parceiro ou **todos** eles.
   * Observação: se você optar por reportar todos os eventos, o evento *af\_app\_opened* não será reportado.
3. Se você optar por selecionar eventos manualmente, clique em ***Adicionar evento*** para adicionar um evento do SDK à lista.
4. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **Nome do evento do SDK** *(obrigatório somente para seleção manual)* | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK ou de eventos de servidor para servidor.  <br />**Dica**: Se você não vir o evento desejado na lista, ative esse evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Opção de envio** | Selecione a opção de envio do evento:  <br />**Somente este parceiro** para eventos provenientes **apenas** de usuários atribuídos ao VK Ads.  <br />**Todas as fontes, incluindo orgânico** para ter toda a sua base de usuários disponível para reportar ao parceiro |
| **Enviar dados do evento** | <ul><li>**Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.</li><li>**Valores e sem receita:** envia todos os parâmetros, com exceção do valor da receita.</li><li>**Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).</li></ul> |

5. Clique em ***Salvar***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um OneLink.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

**Observação**: o OneLink não é compatível com o VK Ads. Use links de atribuição padrão para retargeting.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instruções de integração</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="Status de sincronização dos dados de custo">

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<div id="removing-connected-accounts" />

<Accordion title="Remover contas conectadas">

**Para excluir uma conta conectada:**

* <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Na coluna de ações, passe o mouse sobre uma conta, clique ***Excluir conexão***</Anchor>

</Accordion>

<div id="notes" />

> 📘 **Observações**
>
> 1. Para dar suporte ao custo com o VK Ads, o anunciante deve adicionar o ID da campanha ao link **af\_c\_id=**.
> 2. Depois de definir o custo no VK Ads, não altere o nome de nenhuma campanha ativa, recurso ou anúncio individual, nem use macros dinâmicas com o parâmetro de nome da campanha, pois elas podem causar discrepâncias graves ou a perda de dados de custo.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

Os dados de receita publicitária não são compatíveis com o VK Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões a serem concedidas ao VK Ads, seja o parceiro uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para o VK Ads, a aba de permissões está ativa e você pode conceder Controle ao VK Ads.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* *Permitir a configuração de postbacks de evento in-app* – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-vk-ads=configurando-o-vk-ads h_01HJZV9DR3A3W91BQCE2548M0P=configurando-o-vk-ads h_01HJZV9DR31B2EW88NG57XV2WH=integration-tab activate-partners=ativar-parceiros h_01HJZV9DR4A51AC03J82BMH8R0=ativar-parceiros general-settings=configura%C3%A7%C3%B5es-gerais h_01HJZV9DR4WXN4985B5YYHN065=configura%C3%A7%C3%B5es-gerais app-id=id-da-aplica%C3%A7%C3%A3o h_01HJZV9DR4RDFCE9FF8P61H5G7=id-da-aplica%C3%A7%C3%A3o enable-viewthrough-attribution=ative-a-atribui%C3%A7%C3%A3o-de-view-through h_01HJZV9DR4EFADPVTYYRT4ZYZD=ative-a-atribui%C3%A7%C3%A3o-de-view-through default-postbacks=postbacks-padr%C3%A3o h_01HJZV9DR408AXGRVRBV6KK9CJ=postbacks-padr%C3%A3o inapp-events-postbacks=postbacks-de-eventos-in-app h_01HJZV9DR43RZ5W4B71SASKY42=postbacks-de-eventos-in-app h_01HJZV9DR47N1SFC26DHT4BCCE=attribution-link-tab h_01HJZV9DR4G92S9CZZW3JE5HTS=cost-tab h_01HJZV9DR47Q48ZTJVK1M5DDM8=cost-data-sync-status h_01HJZV9DR5SHYA20GE711S6VT5=removing-connected-accounts h_01HJZV9DR5Q8W34HW2GRWCCMEB=observa%C3%A7%C3%B5es h_01HJZV9DR5696R8NE7R5YYZ2JB=ad-revenue-tab h_01HJZV9DR5YQH7HF32M8R1YBKZ=permissions-tab" />

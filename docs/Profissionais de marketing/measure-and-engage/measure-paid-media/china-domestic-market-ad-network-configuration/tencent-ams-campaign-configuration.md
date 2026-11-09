---
title: Configuração da campanha do Tencent AMS
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - China
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-02-01T18:20:01Z'
  edited_at: '2026-09-16T00:26:49Z'
  id: 360017577338
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/360017577338
---
> **Em resumo:** Tencent AMS, um parceiro integrado de ad network da AppsFlyer, opera propriedades de rede social e utilitários mobile na China e permite que profissionais de marketing executem campanhas de instalação de aplicativos em: WeChat, a plataforma de comunicação mobile da empresa, QQ, o serviço de mensagens instantâneas, QQ Music, QQ Browser, Myapp e muito mais.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/tencentams.png" width="120px" />

<div id="setting-up-tencent-ams" />

## Configuração do Tencent AMS

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

<div id="general-settings" />

### Configurações gerais

A aba Integração está dividida em diferentes seções, conforme descrito abaixo. Para integrar o TencentAMS à AppsFlyer, você precisará das seguintes credenciais: **account\_id, user\_action\_set\_id e access\_token**. Se você ainda não tiver esses valores, obtenha-os diretamente com o Tencent AMS antes de prosseguir com a integração.

<Image align="center" alt="tencent.png" src="https://files.readme.io/56bfdc43b976f1f29f5ba121986aa66228cd79029025e84278cb3c304989fc3e-38300461521041.png" width="248px" />

<div id="note" />

> 📘 **Atenção**
>
> O **access\_token** é emitido pelo Tencent AMS e é válido por 30 dias. Conforme exigência da Tencent, você (ou a agência que gerencia sua conta) deve **atualizar manualmente o token a cada 30 dias e inseri-lo no campo acima**.
>
> * Se o token expirar, os postbacks para o Tencent AMS falharão até que um novo token seja inserido.
> * Se você não souber como obter ou atualizar o token, entre em contato com seu gerente de contas do Tencent AMS para receber orientações.
>
> **Tráfego gerenciado por agência:** Se o seu tráfego for promovido por uma agência, **a agência também deverá preencher e manter o token do lado dela**.

<div id="enable-view-through-attribution" />

#### Habilitar a atribuição de view-through

Para ativar a atribuição de instalação view-through, habilite esta opção.  
O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

#### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para o Tencent AMS após instalações de usuários. Esta seção exibe a **origem dos usuários** que permitem o envio desses postbacks.

<div id="in-app-event-settings" />

#### Configurações de eventos in-app

Nesta seção, você pode configurar postbacks de eventos in-app que são enviados ao Tencent AMS.

**Para configurar postbacks de eventos in-app**,

1. Ative **Postback de evento in-app** .
2. Defina a **janela de postbacks de eventos in-app**, se necessário (saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração dessa janela aqui</Anchor>).
3. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
4. Preencha os seguintes parâmetros na tabela abaixo

| Nome do parâmetro | A descrição |
| --- | --- |
| **Nome do evento do SDK** | O nome do evento, conforme recebido pela AppsFlyer do SDK ou de eventos de servidor para servidor.  <br />**Dica**: Se você não vir o evento desejado na lista, ative esse evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido no lado do parceiro. Selecione o evento predefinido mais adequado para seu evento SDK. |
| **Opção de envio** | Selecione a opção de envio do evento:  <br />**Somente este parceiro** para eventos provenientes **somente** de usuários atribuídos ao Tencent AMS.  <br />**Todas as fontes, incluindo orgânicas** para que toda a sua base de usuários esteja disponível para ser reportada ao parceiro. |
| **Enviar dados do evento** | <ul><li>**Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.</li><li>**Valores e sem receita:** envia todos os parâmetros, com exceção do valor da receita.</li><li>**Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).</li></ul> |

5. Clique em **Salvar Integração**.

</Accordion>

<div id="attribution-link" />

<Accordion title="Link de atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

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

A integração de receita publicitária não está disponível para o Tencent AMS.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões a serem concedidas ao Tencent AMS. Observe que, mesmo que a atribuição esteja desativada para o Tencent AMS, a aba de permissões fica ativa e você pode conceder controle ao Tencent AMS.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* **Permitir configurar a integração** - permite que o parceiro configure a aba de integração (exceto postbacks de eventos in-app)
* **Permitir a configuração de postbacks de evento in-app** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* **Permitir o acesso ao relatório de retenção** – somente aos próprios dados de retenção do parceiro
* **Permitir acesso aos seus dados agregados de usuários fidelizados** - apenas aos dados de usuários fidelizados do próprio parceiro
* **Permitir acesso aos seus dados agregados de eventos in-app** - apenas aos próprios dados de eventos in-app do parceiro
* **Permitir acesso aos dados agregados de receita** — apenas aos dados da receita atribuídos ao parceiro
* **Permitir ingestão de gastos** - permite que o parceiro envie dados de gastos com anúncios em arquivos; somente para este aplicativo.
* **Permitir acesso ao seu dashboard do Protect360 & de dados brutos** - apenas aos próprios dados do Protect360 do parceiro, desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-ad-network">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-tencent-ams=configura%C3%A7%C3%A3o-do-tencent-ams h_01HJNQZJX2TX4C8ZR2Y9JCANGC=configura%C3%A7%C3%A3o-do-tencent-ams h_01HJNQZJX26YHHDX8GBBGBG68M=integration-tab general-settings=configura%C3%A7%C3%B5es-gerais h_01HJNQZJX2QSYR4D6EWB8S1BHQ=configura%C3%A7%C3%B5es-gerais h_01KXZFXJJGZHGQT345V190R5RJ=aten%C3%A7%C3%A3o enable-viewthrough-attribution=habilitar-a-atribui%C3%A7%C3%A3o-de-view-through h_01HJNQZJX2VSCTVPE1B63P24TQ=habilitar-a-atribui%C3%A7%C3%A3o-de-view-through default-postbacks=postbacks-padr%C3%A3o h_01HJNQZJX2K7EJZ89TQBKF8SB7=postbacks-padr%C3%A3o inapp-event-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJNQZJX2W7F5HCEGNVQHMTVE=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJNQZJX2XFD0Q8J3XSCN6ZVP=attribution-link h_01HJNQZJX2R4R6FQ01BTAR184H=cost-tab h_01HJNQZJX2T985MXFNSHAP58Y9=ad-revenue-tab h_01HJNQZJX29H2ZTR0PSRHMXAM8=permissions-tab" />

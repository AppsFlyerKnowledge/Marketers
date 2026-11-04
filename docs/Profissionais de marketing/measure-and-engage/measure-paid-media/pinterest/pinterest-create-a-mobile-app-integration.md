---
title: Pinterest — Criar uma integração de app mobile
metadata:
  keywords:
    - Pinterest
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-11-09T12:51:03Z'
  edited_at: '2026-09-10T00:29:51Z'
  id: 216912786
  locale: pt
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/pt/articles/216912786
---
> **Resumo:** o Pinterest, um parceiro integrado da AppsFlyer, é um dos principais parceiros disponíveis para o mapeamento de tráfego para blogueiros e marcas. A empresa oferece atribuição mobile baseada em cliques e view-through. Além disso, ela também oferece retargeting baseado em cliques, que você pode acompanhar com a AppsFlyer.

<div id="note" />

> 📘 **Nota**
>
> * Depois de aceitar os Termos de anúncios, lembre-se de aceitar os Termos e condições de mensuração mobile do Pinterest <Anchor target="_blank" href="https://ads.pinterest.com/terms/app_install/">aqui</Anchor>.
> * O Pinterest exige que os provedores de atribuição excluam dados a nível de usuário <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention#períodos-de-retenção-de-dados-de-parceiros">6 meses após a instalação</Anchor>. Isso significa que os eventos realizados por esses usuários seis meses após a instalação do aplicativo são registrados como orgânicos. Dados agregados permanecem os mesmos, sem alterações.
> * A partir de 4 de setembro de 2023, o Pinterest passou a exigir que provedores de atribuição <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">restrinjam a disponibilidade de alguns campos nos relatórios de dados brutos</Anchor>, para preservar a privacidade do usuário e garantir a conformidade com a regulamentação.

<div id="set-up-pinterest" />

## Configurar o Pinterest

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

<div id="activate-partner" />

### Ativar parceiro

Em seu **primeiro acesso**, você precisará clicar no botão **Ativar parceiro** para habilitar a configuração dos parâmetros da aba de integração. A opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
Para mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.

<div id="general-settings" />

### Configurações gerais

A seguir estão as configurações gerais da aba de integração do Pinterest.

**Habilitar a atribuição de view-through**

Ative essa opção se quiser atribuir instalações por view-through do Pinterest. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

**Compartilhamento de dados de correspondência avançada**

Ative esta opção para compartilhar campos de correspondência avançada, como e-mail com hash, número de telefone com hash, nome com hash e sobrenome com hash, com o Pinterest, se esses campos estiverem incluídos nas informações do evento enviadas ao AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Para enviar postbacks de eventos in-app para o Pinterest, você deve inserir um tag ID. Essas credenciais serão incluídas nos postbacks de evento enviados ao Pinterest.

* **ID da conta de anúncio** - O identificador exclusivo da sua conta do Pinterest.
* **Token de acesso** - Um token de acesso gerado no Pinterest.

Você pode encontrar o ID da conta de anúncio e o token de acesso diretamente na interface do Gerenciador de Anúncios do Pinterest (consulte a [documentação do Pinterest](https://developers.pinterest.com/docs/api-features/tracking-conversions/#getting-your-access-token-and-ad-account-id)).  Entre em contato com a equipe do Pinterest se precisar de ajuda.

**Configuração de campanhas no Pinterest**

1. **Pré-requisito:** Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.
2. Insira os valores de ID da conta de anúncio e token de acesso nos respectivos campos.

<div id="legacy-set-tag-id" />

#### Tag ID

Para obter o tag ID e configurar os postbacks de eventos in-app:

1. Na sua Conta Comercial (Business Account) do Pinterest, vá para **Anúncios** > **Conversões** e copie o **tag ID** .  
   Clique em **Criar tag** se você ainda não tiver uma tag e conclua o processo de criação. Copie a nova tag.
2. Na AppsFlyer, nas configurações de integração do Pinterest, vá para **Configurações de eventos in-app** e insira o tag ID do Pinterest.

<div id="in-app-event-postbacks" />

### Aba Permissões

Aqui, você pode mapear seus eventos da AppsFlyer com o Pinterest por meio de postbacks.

1. Configuração de campanhas no Pinterest
2. Ative os **postbacks de eventos in-app.**
3. Configure a janela de postback de eventos in-app.
4. Selecione as configurações e mapeamentos de postbacks para eventos.

| Nome do parâmetro | Descrição |
| --- | --- |
| <span id="appsflyer-event-name"></span>**AppsFlyer event name** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado ao seu app ou de eventos de servidor para servidor (S2S).  <br /> **Dica** - não está encontrando o evento na lista? Certifique-se de ativá-lo em um dispositivo com uma instalação não orgânica e verifique novamente. |
| <span id="partner-event-name"></span>**Partner event name** | O nome ou ID exclusivo de cada evento conforme definido pelo Pinterest.  <br /> Obtenha o ID do evento correspondente no Pinterest e insira-o no campo de texto. |
| <span id="to-users-from"></span>**To users from** | <ul><li>Somente este parceiro: para eventos provenientes apenas de usuários atribuídos a esse parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: para ter toda a sua base de usuários disponível para ser relatada ao parceiro.</li></ul> |
| <span id="including"></span>**Including** | Selecione se a receita do evento ou os valores dos parâmetros serão enviados ao parceiro no postback, ou se esses dados não serão incluídos.<br /><br />A AppsFlyer pode enviar todos os parâmetros de eventos in-app avançados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro af\_revenue. Ou então, a AppsFlyer pode enviar todos os parâmetros, incluindo o valor da receita (caso exista no evento). |

5. Clique em **adicionar evento** para adicionar um evento de SDK à lista.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba Link de atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para fazer a atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para campanhas de aquisição como para retargeting. Você pode usar um link de plataforma única ou um <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

<div id="attribution-link-for-retargeting-campaign" />

#### Link de atribuição para campanhas de retargeting

O Pinterest recomenda o uso de links de atribuição específicos para cada sistema operacional. Selecione a opção **Usar um link de plataforma única** e adicione os parâmetros necessários ao link de atribuição de retargeting.

#### Deep Link URL

<div id="note-1" />

> 📘 **Nota**
>
> O deep link dentro de um pin somente funcionará quando seu aplicativo estiver na lista de permissões do Pinterest.
> Entre em contato com seu representante do Pinterest ou envie um e-mail para [apps@pinterest.com](mailto:apps@pinterest.com) para entrar na lista de permissões para deep linking.

Use esse campo se o link for usado para o deep linking de usuários em qualquer atividade específica do seu aplicativo.

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

Depois de definir o custo no Pinterest, não altere o nome de nenhuma campanha em execução, conjunto de anúncios ou anúncio, nem use macros dinâmicas no parâmetro do nome da campanha, pois elas podem causar discrepâncias graves ou a perda de dados de custo.

<div id="enabling-and-testing-pinterest-integration" />

### Ativando e testando a integração com o Pinterest

A AppsFlyer recebe dados de custo via API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para mais detalhes sobre as dimensões, métricas e recursos compatíveis. **Atenção:** os dados de custo exigem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<div id="cost-data-sync-status" />

### Status de sincronização dos dados de custo

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja seu status na Cost API</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo no dashboard de status da integração de custos (ou de receita de anúncio) ou no dashboard individual da ad network. 

<div id="stop-pinterest-cost-sync" />

### Interromper a sincronização de custos com o Pinterest

**Para excluir uma conta conectada:**

* <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Na coluna ações, passe o mouse sobre uma conta e clique em *excluir conexão*</Anchor> Feito isso, a AppsFlyer deixa de receber dados de custo. Feito isso, a AppsFlyer deixa de receber dados de custo. A exclusão da conexão não afeta os dados históricos.

<div id="ad-revenue-tab" />

<Accordion title="Aba Receita de anúncios">

A receita de anúncios não é compatível com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar permissões para o Pinterest. Atenção: mesmo que a atribuição estiver desativada para o Pinterest, a aba de permissões está ativa e você pode conceder permissões ao Pinterest.

Saiba mais sobre as <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões que você pode conceder ao Pinterest</Anchor>.

</Accordion>

</Accordion>

<div id="troubleshooting" />

## Resolução de problemas

Mensagem de erro da aba Custo: *Nenhum dado correspondente* significa que a conta do Pinterest conectada à AppsFlyer não é a conta correta. Não foram encontrados dados que correspondam ao aplicativo. Você deve fazer login no Pinterest com credenciais diferentes

<div data-zendesk-anchors="h_01H95QTA3ZZ9GJW9EN1VZ01TH2=nota set-up-pinterest=configurar-o-pinterest h_01H95QTA3Z5HXW39AHAF8FMFWH=configurar-o-pinterest h_01H95QTA3ZNQWBRA86E6TRQ46Y=integration-tab activate-partner=ativar-parceiro h_01H95QTA3ZGEM34HY1A7NC8NX7=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H95QTA3Z0NW9V51D8J7MHEX0=configura%C3%A7%C3%B5es-gerais inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01JTDP2T0BFP5WP03X5EMXVAWA=configura%C3%A7%C3%B5es-de-eventos-in-app %5Blegacy%5D-set-tag-id=tag-id h_01JTMX6DD0G101KC0HQ0D34S48=tag-id inapp-event-postbacks=aba-permiss%C3%B5es h_01JTDP2T0BTW986GN5HSWPR3JH=aba-permiss%C3%B5es h_01H95QTA3ZT7PVGAJW5AKPC186=attribution-link-tab attribution-link-for-retargeting-campaigns=link-de-atribui%C3%A7%C3%A3o-para-campanhas-de-retargeting h_01H95QTA3ZPQZ422AB2JBZAS07=link-de-atribui%C3%A7%C3%A3o-para-campanhas-de-retargeting h_01H95QTA3ZT23CYTCE2V3728MD=deep-link-url h_01H95QTA3ZYHQED2T5B2FA5PV8=nota-1 h_01H95QTA3Z3XJDM5YRXFK7DA0E=cost-tab enabling-and-testing-pinterest-integration=ativando-e-testando-a-integra%C3%A7%C3%A3o-com-o-pinterest h_01H95QTA3ZZ56R8EZBJY1ESX5W=ativando-e-testando-a-integra%C3%A7%C3%A3o-com-o-pinterest cost-data-sync-status=status-de-sincroniza%C3%A7%C3%A3o-dos-dados-de-custo h_01H95QTA3ZST8WS3TAR79H06FM=status-de-sincroniza%C3%A7%C3%A3o-dos-dados-de-custo stop-pinterest-cost-sync=interromper-a-sincroniza%C3%A7%C3%A3o-de-custos-com-o-pinterest h_01H95QTA3ZFCJ82E3YDMP7S716=interromper-a-sincroniza%C3%A7%C3%A3o-de-custos-com-o-pinterest h_01H95QTA3ZM2REWR2A5DHK1DSA=ad-revenue-tab h_01H95QTA3ZM4WPHV3MB00WZXSB=permissions-tab troubleshooting=resolu%C3%A7%C3%A3o-de-problemas h_01H95QTA3ZP20DSJQGY4QQX0Z7=resolu%C3%A7%C3%A3o-de-problemas" />

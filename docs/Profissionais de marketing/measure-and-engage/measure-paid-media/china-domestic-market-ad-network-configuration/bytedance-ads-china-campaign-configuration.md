---
title: 'ByteDance Ads China: configuração da campanha'
metadata:
  keywords:
    - bytedance
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
  created_at: '2017-06-18T07:05:42Z'
  edited_at: '2026-09-08T00:26:33Z'
  id: 115003019403
  locale: pt
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/pt/articles/115003019403
---
> **Num relance:** A ByteDance Ads China (Ocean Engine), parceira integrada da AppsFlyer, é uma empresa de tecnologia da Internet que opera várias plataformas de conteúdo habilitadas para aprendizado de máquina.

<div id="note" />

> 📘 **Nota**
>
> Se você deseja promover seus aplicativos para Android com a ByteDance Ads China, é necessário enviar seu OAID para o SDK da AppsFlyer de acordo com as instruções no <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">Integração do SDK da AppsFlyer - Android</Anchor>. O serviço do Google Play está bloqueado na China, OAID é o ID de dispositivo Android mais popular para atribuição de anúncios.

Além da atribuição móvel baseada em cliques, a ByteDance Ads China também oferece atribuição de visualização, que você pode registrar com a AppsFlyer.

Para configurar suas campanhas com a ByteDance Ads China, siga as etapas abaixo.

<div id="setting-up-bytedance-ads-china" />

## Configurando a ByteDance Ads China

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

Observação

> 👍 **Tip**
>
> * A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d">Configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros
> * O restante das etapas são descritivas ou **opcionais**.

<div id="integration-tab" />

<Accordion title="Aba de integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partners" />

### Ativar parceiros

No **primeira visita** aqui, você deve ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da guia de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
**Para obter mais detalhes sobre a ativação do parceiro, clique aqui.**

Configurações gerais

**Habilitar a atribuição de visualização**

<Image align="center" alt="" src="https://files.readme.io/3340b894428079e37c238cd78883669abd53cd6895165c5f9b5ea90d27d570c9-50612201111697.png" />

Alterne para **LIGADO** se você quiser atribuir instalações de visualização da ByteDance Ads China. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para a ByteDance Ads China após instalações e reengajamentos de usuários. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

<Image align="center" alt="bytedance-default-postbacks.png" src="https://files.readme.io/5f3cb637fb9ff652533fcfd9c02ea8dc1768e0e1c1686a180ea18c0d2e09309f-50612201121425.png" />

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com a ByteDance Ads China por meio de postbacks.

1. Ative os postbacks de eventos in-app.
2. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
3. Clique em **Adicionar evento** para adicionar um evento SDK à lista.
4. Complete os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de evento personalizado.</Anchor></li></ul> |
| **mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** obtenha o ID do evento correspondente no parceiro.</li><li>**Caixa suspensa:** selecione o evento predefinido mais adequado.</li><li>**Sem alterações**: Enviar os eventos como eles estiverem, sem mapear o nome do evento.</li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Somente esse parceiro**: Envie postbacks somente quando o evento for atribuído a este parceiro—ou seja, o usuário que o executou o evento veio deste parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas:** Enviar postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos - ou seja, o usuário que o executou veio de qualquer fonte de mídia.</li></ul> |
| **incluindo** | Selecione os dados do evento a compartilhar com o parceiro no postback:<ul><li>**Sem valores e sem receita**: Envie apenas o evento em si, sem nenhum parâmetro (valores ou receita).</li><li>**Com valores e sem receita**: envie todos os parâmetros, com **exceção** do valor da receita.</li><li>**Valores e receita**: envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um OneLink.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.  

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.

<div id="click-attribution-link" />

### Link de atribuição de cliques

Depois de gerar o link de atribuição, conclua o processo de configuração da campanha no site da ByteDance Ads China.

**1. Crie o acompanhamento de conversões no Ocean Engine.**

Faça login no Ocean Engine ([https://ad.oceanengine.com/](https://ad.oceanengine.com/)) > **Biblioteca** > **Acompanhamento de conversões**.

<Image align="center" alt="OE_dashboard_1.png" src="https://files.readme.io/fda140ac7e3023033880b04ed500a675ae78187e4eb694ee200922b729ab119f-50612185108497.png" />

Clique em **Aplicativo de rastreamento** e crie um **Nova transformação de aplicativos**.

<Image align="center" alt="OE_dashboard_2.png" src="https://files.readme.io/dbf0c13c23d21d08c195a4ab747e5de0986cb01f5ebde98f6c701ce731480958-50612185109009.png" />

Clique no botão **API** método.

<Image align="center" alt="OE_dashboard3.png" src="https://files.readme.io/70e7f6ca01c532fafb8f2ab7d31d6de51494f11749329c1c1333d1da6f28f284-50612185110417.png" />

Na parte do link Monitoramento, insira o link de atribuição de clique da AppsFlyer e/ou o link de atribuição de impressão.

<Image align="center" alt="dashboard4.png" src="https://files.readme.io/d36ec92a03062fc7ee169bb1ff3863722343577f3ee2b12779065b3e52731348-50612201124369.png" />

**2. Conclua o teste de atribuição seguindo as instruções no site**.

**3. Criar uma campanha publicitária com a conversão recém-criada**.

Ir para **Novo anúncio** >> **Definir orçamento e lance** Selecione a conversão que você criou para este aplicativo.

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

A AppsFlyer obtém detalhes de custo por API. Observe que a AppsFlyer não oferece suporte aos dados de custo no nível do anúncio para ByteDance, exceto para campanhas em execução no sistema ByteDance v1.0.

<div id="api-dimensions-supported" />

### Dimensões da API compatíveis

| Geolocalização | Canal de mídia | Campanha | Conjunto de anúncios | Anúncio | Outros |
| --- | --- | --- | --- | --- | --- |
| Yes | - | Sim | Sim | Não<br /><br />(Os anúncios são compatíveis apenas com campanhas v1.0 da ByteDance) | - |

**Para ativar a API de custo de anúncios da ByteDance China**:

1. Na aba do parceiro integrado Custo , ative ***Obter Custo Dados***.
2. Faça login na ByteDance Ads China.
3. Clique ***Salvar Custo***.
   * Você concluiu o procedimento com sucesso. A API está ativa. A AppsFlyer coleta dados do parceiro 6 vezes por dia, em média uma vez a cada quatro horas.
   * A aba de custos mostra o status da sua integração de custo e a última vez que a AppsFlyer extraiu dados de custos correspondentes.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

Essa seção é relevante somente se você estiver atuando como publisher, exibindo anúncios do parceiro aos usuários. Dessa forma, você certamente deseja medir o engajamento dos usuários adquiridos de várias fontes para encontrar as fontes mais lucrativas para você.

**Para ativar a API de receita publicitária**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">essas instruções de integração</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode selecionar as permissões que serão concedidas à Roku OneView, mesmo que o parceiro atue como uma ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para a ByteDance Ads China, a guia de permissões estará ativa e você poderá conceder controle à ByteDance Ads China.

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

<div id="ad-network-permissions" />

### Permissões da ad network

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJR1HREQDCQDN6JZRPD356VS=nota setting-up-bytedance-ads-china=configurando-a-bytedance-ads-china h_01HJR1HREQ6YAW1WPX2BTZS2R7=configurando-a-bytedance-ads-china h_01HJR1HRERBBZFKBHH78BK6QW2=integration-tab activate-partners=ativar-parceiros h_01HJR1HRER22XX94R1WEQK60GJ=ativar-parceiros default-postbacks=postbacks-padr%C3%A3o h_01HJR1HRERMXHAAGXEFJS4ZS8C=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJR1HRERF2Y205KP0J8HZFR3=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJR1HRER391J6PD9Q0M1MW3F=attribution-link-tab click-attribution-link=link-de-atribui%C3%A7%C3%A3o-de-cliques h_01HJR1HRERCHNHQGX3X1E1ARDK=link-de-atribui%C3%A7%C3%A3o-de-cliques h_01HJR1HRER1G4K3PQG1Z7M6CCX=cost-tab api-dimensions-supported=dimens%C3%B5es-da-api-compat%C3%ADveis h_01HJR1HRES86BJM4ABQ0B414F1=dimens%C3%B5es-da-api-compat%C3%ADveis h_01HJR1HRES470MKXS1S08X202D=ad-revenue-tab h_01HJR1HRESJ7KNFZ9TDHZKESJ7=permissions-tab ad-network-permissions=permiss%C3%B5es-da-ad-network h_01HJR1HRESZCC6YV9D40YYSYX0=permiss%C3%B5es-da-ad-network" />

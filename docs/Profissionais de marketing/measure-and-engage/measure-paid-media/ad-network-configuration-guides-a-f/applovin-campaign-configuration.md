---
title: Configuração de campanhas da AppLovin
metadata:
  keywords:
    - Applovin
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
  created_at: '2016-03-06T12:20:32Z'
  edited_at: '2026-09-10T00:23:35Z'
  id: 208335613
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/208335613
---
> **Visão geral:** a AppLovin, um parceiro integrado da AppsFlyer, é uma ad network bem conhecida para tráfego de app mobile. Além da atribuição mobile baseada em cliques, a AppLovin também oferece atribuição de custo, receita publicitária e view-through, que você pode registrar com a AppsFlyer.

<div id="setting-up-applovin" />

## Configurando a AppLovin

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

Na **primeira visita** aqui, você precisará ativar o botão **Ativar parceiro** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique aqui.**

<div id="note" />

> 📘 **Atenção**
>
> Como uma all-installs network, a AppLovin prefere receber postbacks para todas as novas instalações do seu aplicativo de QUALQUER fonte, incluindo orgânicas. Recomenda-se selecionar *Eventos atribuídos a qualquer parceiro* para enviar todos os postbacks de instalação para a AppLovin.

<div id="general-settings" />

### Configurações gerais

**Compartilhar indicação de orgânico/não orgânico**

Quando essa opção estiver ativada, se um postback de instalação for enviado para todos os canais de mídia, incluindo orgânicos, a AppLovin receberá uma indicação sobre se a instalação foi orgânica ou não orgânica.

**Chave do SDK**

A AppLovin se conecta à AppsFlyer por meio de uma sdk\_key exclusiva. Se você ainda não tiver a sdk\_key, deverá obtê-la com a AppLovin para continuar com a integração.

**Habilitar a atribuição de view-through**

Ative esta opção se quiser atribuir instalações view-through da AppLovin. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

Envie postbacks automáticos para a AppLovin após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à AppLovin.  
Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser relatada à AppLovin.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

Nesta seção, você pode mapear quais eventos da AppsFlyer enviar para a AppLovin por meio de postbacks.

1. Defina novamente a sdk\_key da AppLovin aqui.
2. Ative a opção Postbacks de eventos in-app.
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
5. Preencha os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido no lado da AppLovin.  <br />Obtenha o nome do evento correspondente da AppLovin e configure-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

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

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no painel de status de integração de custo (e receita de publicitária) ou no painel individual da ad network. 

<div id="applovin-billable-cost" />

> 🚧 **Custo faturável da AppLovin**
>
> A partir de 1º de agosto de 2024, a AppLovin fatura todos os seus clientes com base em instalações probabilísticas. Antes dessa data, alguns clientes eram cobrados com base em instalações SKAN. <Anchor target="_blank" href="https://support.applovin.com/hc/en-us/articles/28531589437965-iOS-Billing-Method">Consulte a AppLovin para mais informações</Anchor>
>
> A integração de custo da AppsFlyer com a AppLovin reflete com precisão esse custo faturável. Isso significa que o custo na AppsFlyer corresponde corretamente ao custo na plataforma AppLovin.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

* A AppLovin fornece mediação de receita de anúncios com dados agregados.
* Sobre a <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution">atribuição de receita de anúncios</Anchor> (monetização de anúncios)

**Para ativar a API de receita publicitária**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">essas instruções de integração</Anchor>.

<div id="note-1" />

> 📘 **Atenção**
>
> * A AppLovin envia a receita de anúncios gerada por ela mesma.
> * A receita de anúncios de parceiros de mediação, como ironSource e Unity, pode ser exibida no dashboard da AppLovin, mas não é enviada à AppsFlyer. Ative outros parceiros de mediação no dashboard da AppsFlyer para enviar dados de receita de anúncios diretamente à AppsFlyer.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões para conceder à AppLovin. Observe que, mesmo se a atribuição estiver desativada para a AppLovin, a aba de permissões estará ativa e você poderá conceder controle à AppLovin.

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* **Permitir configurar a integração** - permite que o parceiro configure a aba de integração (exceto postbacks de eventos in-app)
* **Permitir a configuração de postbacks de evento in-app** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* **Permitir o acesso ao relatório de retenção** – somente aos próprios dados de retenção do parceiro
* **Permitir acesso aos dados agregados de usuário fiéis** — apenas aos dados de usuários fieis do parceiro
* **Permitir acesso aos dados agregados de eventos in-app** — apenas aos dados de eventos in-app próprios do parceiro
* **Permitir acesso aos dados agregados de receita** — apenas aos dados da receita atribuídos ao parceiro
* **Permitir o acesso ao painel Protect360** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-applovin=configurando-a-applovin h_01HKW93TKBNYVC05MA5GB37JVH=configurando-a-applovin h_01HKW93TKCPCFYD6HV2XH1QTHS=integration-tab activate-partner=ativar-parceiro h_01HKW93TKCG5JCQK52QJ65483M=ativar-parceiro h_01HKW93TKC2XGTZ7WAQ2E2AGPD=aten%C3%A7%C3%A3o general-settings=configura%C3%A7%C3%B5es-gerais h_01HKW93TKCZCK6GB7M4VV5C1NB=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HKW93TKCCRB21JAFDA2GWH6F=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW93TKCVWKTM9C8J220Q41E=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HKW93TKCCXVQMBCGW02J7JK4=attribution-link-tab h_01HKW93TKCXMG7BHMEWRFSCM6N=cost-tab h_01J43V7Z67C98TG7CE2QQGVVWE=custo-fatur%C3%A1vel-da-applovin h_01HKW93TKDDWXA2C7456E8Q8GG=ad-revenue-tab h_01HKW93TKD8Z0QQADBJWMBP962=aten%C3%A7%C3%A3o-1 h_01HKW93TKDBCXNA68YVMQVBVP0=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HKW93TKD21RF42KMNA9J9WXF=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />

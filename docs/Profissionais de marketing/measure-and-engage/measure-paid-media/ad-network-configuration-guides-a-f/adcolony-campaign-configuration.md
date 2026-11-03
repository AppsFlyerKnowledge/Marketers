---
title: Configuração da campanha da AdColony
metadata:
  keywords:
    - Adcolony
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
  created_at: '2016-03-06T10:58:12Z'
  edited_at: '2026-09-10T00:23:22Z'
  id: 208005106
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/208005106
---
> **Visão geral:** a AdColony, um parceiro integrado de ad network da AppsFlyer, é uma network de publicidade em vídeo premium, fornecendo a anunciantes e marcas uma audiência engajada e responsiva, além de oferecer soluções de monetização a publishers e desenvolvedores. Além da atribuição mobile baseada em cliques, a AdColony também oferece atribuição de custo, receita publicitária e view-through, que você pode registrar com a AppsFlyer.

## Configurando a AdColony

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

A aba **Integração** está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiros

Na primeira visita, o <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">parceiro deve ser ativado</Anchor> acionando a opção ***Ativar parceiro***, para habilitar sua configuração.

### Configurações gerais

#### Habilitar a atribuição de view-through

Ative esta opção se quiser atribuir instalações view-through da AdColony. O controle deslizante de lookback de view-through está disponível na aba ***Link de atribuição***.

### Postbacks padrão

Envie postbacks automáticos para a AdColony após instalações e instalações rejeitadas. Use esta seção para definir a **fonte dos usuários** para os postbacks.

Selecione ***Somente este parceiro*** para instalações provenientes apenas de usuários atribuídos à AdColony.  
Selecione ***Todas as fontes, incluindo orgâni*co** para ter toda a sua base de usuários disponível para ser reportada à AdColony.

Instalações rejeitadas podem ser enviadas para **Somente este parceiro**.

#### Postbacks de launch

Desde 1º de julho de 2020, não enviamos mais postbacks de lançamento para a AdColony. Se a sua integração foi configurada antes dessa data, talvez haja alterações nas suas configurações. A tabela a seguir explica as possíveis alterações e as ações necessárias, quando aplicável:

| Sua configuração | Será atualizada para | Suas próximas ações |
| --- | --- | --- |
| Enviar para AdColony **todos os launches** (de todos os canais de mídia, incluindo orgânico) | Enviar para a AdColony:<ul><li>**todas as instalações** (de todos os canais de mídia, incluindo orgânico)</li><li>**todos os** `af_app_opened` **eventos** (de todos os canais de mídia, incluindo orgânico)</li></ul> | Nenhuma ação adicional é necessária. Esta atualização não tem impacto real na configuração. |
| Enviar à AdColony **apenas as primeiras aberturas atribuídas** | Enviar à AdColony **instalações** atribuídas apenas à AdColony | Se você também quiser enviar eventos `af_app_open`:<ul><li>No AppsFlyer, na página de integração da AdColony, configure o envio do evento na seção ***Postbacks de eventos in-app***</li></ul> |
| Enviar à AdColony **todas as aberturas** (de todos os canais de mídia, incluindo orgânico)<br /><br />**MAS**<br /><br />Nenhuma conversão foi atribuída à AdColony nos 3 meses anteriores a 1º de julho de 2020 | Enviar **todas as instalações**<br /><br />**AND**<br /><br />Durante 30 dias após 1º de julho de 2020, **todas as aberturas** | Se você também quiser enviar eventos `af_app_open`:<ul><li>No AppsFlyer, na página de integração da AdColony, configure o envio do evento na seção ***Postbacks de eventos in-app***.</li></ul>Se isso for feito durante o período de 30 dias, deixaremos de enviar todas as aberturas e passaremos a enviar todos os eventos `af_app_open`.<br /><br />Se isso for feito após o período de 30 dias, deixaremos de enviar aberturas e não enviaremos eventos `af_app_open` até que isso seja configurado de outra forma. |

### Configurações de eventos in-app

Nesta seção, você pode configurar postbacks de eventos in-app que são enviados à AdColony.

**Para configurar os postbacks de eventos na aplicação:**

1. Ativar ***postbacks de eventos in-app***
2. Clique em ***Add event*** para adicionar um evento de SDK à lista
3.
   | Nome do parâmetro | A descrição |
   | --- | --- |
   | **Nome do evento do SDK** | O nome do evento, conforme recebido pelo AppsFlyer, seja pelo SDK ou por eventos de servidor para servidor.  <br />**Dica**: Se você não vir o evento desejado na lista, ative esse evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
   | **Identificador de evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido no lado do parceiro. Selecione o evento predefinido mais adequado para seu evento SDK. |
   | **Opção de envio** | Selecione a opção de envio do evento:  <br />**Somente este parceiro** para eventos provenientes **apenas** de usuários atribuídos à AdColony.  <br />**Todas as fontes, incluindo orgânico** para disponibilizar toda a sua base de usuários para ser relatada ao parceiro |
   | **Enviar dados do evento** | * **Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.<br />* **Valores e sem receita:** envia todos os parâmetros, com exceção do valor da receita.<br />* **Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento). |

4. Clique em ***Salvar***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um OneLink.

<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura e os parâmetros do link de atribuição</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">essas instruções</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de custo via API não está disponível para este parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível no momento com esta integração de parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões para conceder à AdColony. Observe que, mesmo que a atribuição esteja desativada para a AdColony, a aba de permissões está ativa e você pode conceder controle à AdColony.

Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

### Permissões da rede de anúncios

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* ***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos seus dados agregados de usuários fidelizados*** - apenas aos próprios dados de usuários fidelizados do parceiro para sincronizar dados
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-adcolony=configurando-a-adcolony h_01HJR62VJZXTFPXYRMYT05EV1X=configurando-a-adcolony h_01HJR62VJZZZQRBHAA6FT8D6GY=integration-tab activate-partners=ativar-parceiros h_01HJR62VJZQRBWFACANBJ6HG14=ativar-parceiros general-settings=configura%C3%A7%C3%B5es-gerais h_01HJR62VJZFDKC4N7BC5P1TSZK=configura%C3%A7%C3%B5es-gerais enable-viewthrough-attribution=habilitar-a-atribui%C3%A7%C3%A3o-de-view-through h_01HJR62VJZEC4E5FZVCKWDXNEY=habilitar-a-atribui%C3%A7%C3%A3o-de-view-through default-postbacks=postbacks-padr%C3%A3o h_01HJR62VJZR34JMT4TM0YG1DC6=postbacks-padr%C3%A3o launch-postbacks=postbacks-de-launch h_01HJR62VJZJX57VMDNEQFKFB9C=postbacks-de-launch inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJR62VJZJHHH4Q8P8ZERXVRM=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJR62VK0980EE3ZKYT2KFB5H=attribution-link-tab h_01HJR62VK0G62A2S3WTW49150C=cost-tab h_01HJR62VK0869W4K5R1JF7V0C4=ad-revenue-tab h_01HJR62VK0GMA3TTGPPS3ND64F=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios h_01HJR62VK0AHRTPN92TGGCMC5D=permiss%C3%B5es-da-rede-de-an%C3%BAncios" />

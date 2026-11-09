---
title: Integração da Roku com a AppsFlyer
metadata:
  keywords:
    - Advertisers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-19T09:00:10Z'
  edited_at: '2026-08-18T00:22:45Z'
  id: 4404257169169
  locale: pt
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/pt/articles/4404257169169
---
> **Resumo:** A Rokuads\_int é uma integração de SRN que permite que os anunciantes integrem seu app mobile ou de CTV à Roku Ads e recebam atribuição e dados de eventos para suas campanhas nessa plataforma.

<div id="about-roku-ads-attribution" />

## Sobre a atribuição da Roku Ads

A Roku é uma ad network única que possui um inventário de anúncios disponível tanto para TV Conectada (CTV) quanto para aplicativos mobile. A integração de SRN entre AppsFlyer e Roku Ads permite que os anunciantes mensurem várias jornadas de usuários, incluindo:

* CTV para CTV: anúncios de CTV que impulsionam instalações e eventos de aplicativos de CTV.
* Mobile para mobile: anúncios de aplicativos mobile que impulsionam instalações e eventos de aplicativos mobile.
* CTV para mobile &lt; > mobile para CTV: impressões de anúncios em uma plataforma, que impulsionam instalações e eventos em outra plataforma.

<div id="roku-attribution-flow" />

### Fluxo de atribuição da Roku

<Image align="center" alt="54525 inline.jpg" src="https://files.readme.io/5634ed65702e1d4c90250a7f7b4448c225d5f769936b2a120ddbac1a76752c09-39534517801617.jpg" width="895px" />

<div id="setting-up-roku-ads-integration-for-advertisers" />

## Configurando a integração da Roku Ads para anunciantes

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Para ativar: na AppsFlyer, no menu lateral, selecione **Colaborar**> **Partner Marketplace**.  
   Para editar: vá para **colaborar** > **integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Pesquise pelo parceiro (`rokuads_int`) e selecione-o.
4. Na aba **Integração** selecione **Ativar parceiro**.  
    **Atenção:** **o toggle deve permanecer ligado ([ativado](#)) enquanto você trabalhar com o parceiro. [Saiba mais sobre a ativação de parceiros](#).**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do cabeçalho da janela de configuração do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

**Atenção:** Existem algumas diferenças entre as configurações de aplicativos do iOS, Android e Roku.

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="general-settings" />

#### Configurações gerais

* **ID do grupo de eventos:** Insira o ID do grupo de eventos para conectar seu aplicativo à AppsFlyer.
  * **Event Group ID:** insira o Event Group ID, conforme obtido do Roku Ads Manager, para conectar seu app à AppsFlyer. Para mais informações, consulte a <Anchor target="_blank" href="https://help.ads.roku.com/en/articles/11885912-setting-up-an-integration-with-appsflyer-a-mobile-measurement-partner-mmp">documentação da Roku Ads</Anchor>.
  * **Clientes de serviços gerenciados**: Entre em contato com seu representante da Roku para obter o ID do grupo de eventos.
* **Compartilhamento avançado de dados:**  quando ATIVADO, a Roku receberá postbacks e dados de eventos com endereços IP para todos os dispositivos, incluindo aqueles que não disponibilizam seu Advertising ID (IDFA). Manter o compartilhamento avançado DESATIVADO faz com que o parceiro receba apenas postbacks e dados de eventos para dispositivos que disponibilizam o IDFA.
* **Compartilhamento de dados de correspondência avançada:** Quando ativado, a Roku recebe campos de correspondência avançada, como e-mail com hash, número de telefone com hash, primeiro nome com hash e sobrenome com hash, se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada (em inglês)</Anchor>.
* **Uso limitado de dados:** ative essa opção para indicar que a Roku Ads deve limitar o uso de informações pessoais para um determinado evento em estados específicos dos EUA. Para mais informações, consulte a <Anchor target="_blank" href="https://help.ads.roku.com/en/articles/8766138-limited-data-use">documentação da Roku Ads</Anchor>.

<div id="install-attribution" />

#### Atribuição de instalação

Defina as diferentes janelas de atribuição para atribuir novas instalações (primeiros lançamentos) de usuários que visualizaram, clicaram ou interagiram com seu anúncio. **Atenção:** a atribuição de reinstalações (ou seja, qualquer instalação que não seja a configuração inicial no dispositivo) não está disponível.

* Defina a **janela de lookback de click-through de instalação** para 1 a 23 horas ou 1 a 14 dias. **Atenção:** a Roku Ads recomenda que você configure essa janela para 14 dias.
* [Opcional] Ative a **atribuição de view-through de instalação**e defina a **janela de lookback** para 1 a 23 horas ou 1 a 14 dias. **Atenção:** a Roku Ads recomenda 14 dias.

<div id="re-engagement-attribution" />

#### Atribuição de reengajamento

* Defina a **janela de lookback de click-through de reengajamento** para 1 a 23 horas ou 1 a 14 dias. **Atenção:** a Roku Ads recomenda 14 dias.
* [Opcional] Ative a **atribuição de view-through de reengajamento** e defina a **janela de lookback** para 1 a 23 horas ou 1 a 14 dias. **Atenção:** a Roku Ads recomenda 14 dias.
* Defina a **janela de reengajamento** para 1 a 23 horas, 1 a 90 dias ou como **vitalícia**.

Saiba mais sobre as regras e janelas de reengajamento.

<div id="ignore-active-users-for-retargeting" />

#### Ignorar usuários ativos para retargeting

Defina um período de tempo para ignorar reengajamentos e reatribuições de usuários que inicializaram o seu aplicativo. Isso significa que a atividade realizada durante o período de tempo escolhido não é atribuída. Para mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/set-retargeting-inactivity-window#período-de-inatividade">período de inatividade</Anchor>.

1. Ative a opção **Ignorar usuários ativos para retargeting**.
2. Defina a **janela de inatividade**.

<div id="cross-platform-attribution" />

#### Atribuição cross-platform

A atribuição cross-platform fica ativada por padrão para essa integração.

* Defina a **janela de lookback** para 1 a 23 horas ou 1 a 3 dias.
* A janela de prioridade igual entre plataformas está definida como 3 horas. Quando ativada, as impressões cross-platform relatadas pela Roku possuem a mesma prioridade que os cliques de outras ad networks.

<div id="in-app-events-postbacks" />

#### Postbacks de eventos in-app

Mapeie eventos in-app da AppsFlyer para eventos da Roku Ads, enviados via postbacks:

1. Ative os **postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para adicionar um SDK ou evento de server-to-server à lista. A tabela abaixo descreve os campos a serem preenchidos:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento na AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de server-to-server. |
| **Mapeado para eventos de parceiros** | Selecione na lista de eventos pré-definidos da Roku. Veja o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#nomes-de-eventos-predefinidos">mapeamento sugerido</Anchor>.  <br />**Atenção:** a Roku não oferece suporte para o envio de eventos personalizados. |
| **Para usuários de** | <ul><li>**Apenas para este parceiro** (padrão): envie postbacks apenas quando o evento for atribuído a esse parceiro.<br />Ou</li><li>**Todos os canais de mídia, incluindo orgânicos:** envie postbacks para eventos atribuídos a qualquer parceiro, assim como eventos orgânicos.</li></ul> |
| **Incluindo** | <ul><li>**Sem valores e sem receitas** (padrão): envie apenas o evento em si, sem qualquer valor de evento.</li><li>**Com valores e sem receita**: envie todos os parâmetros **exceto** o valor de receita.</li><li>**Valores e receita**: envie todos os parâmetros de evento, **incluindo** o valor da receita (se existir no evento).</li></ul> |

* [Opcional] Clique no ícone **Adicionar condição** para definir condições para um evento.
* Clique em **Salvar integração.**
* [Opcional] Para integrar mais aplicativos:
  1. No canto superior esquerdo, embaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
  2. Selecione outro aplicativo na lista.
  3. Repita a configuração para o aplicativo selecionado.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba Link de atribuição">

Os links de atribuição não são relevantes para SRNs ou Advanced SRNs.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba Custo (para custo, cliques e impressões)">

A integração de custos ainda não está disponível para a Roku Ads.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba Receita de anúncios">

A receita de anúncios não está disponível para a Roku Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nessa aba, você pode escolher quais permissões conceder à Roku Ads — independentemente da sua atuação como ad network, agência ou ambos. Mesmo que a atribuição esteja desativada para a Roku Ads, a aba de Permissões permanece ativa e você ainda pode conceder acesso a ela.

Depois de habilitar as permissões para a Roku Ads, você pode adicionar membros da equipe e atribuir acesso com base nas permissões selecionadas. **Atenção:** as permissões só podem ser concedidas a funcionários da Roku Ads que possuem uma conta de membro da equipe na AppsFlyer.

**Para conceder essas permissões, siga essas etapas:**

1. Clique em **Adicionar membro da equipe**.
2. Insira o e-mail do membro da equipe da ad network
3. Clique em **Adicionar**.

<div id="important" />

> 🚧 **Importante!**
>
> * Ao permitir que a Roku Ads configure a integração e faça alterações nos postbacks de eventos in-app, você permite que a ad network acesse todos os eventos de atribuição, incluindo o tráfego orgânico e não orgânico de todos os canais de mídia.
> * As alterações feitas pela Roku Ads substituem a configuração atual, mesmo que você (o anunciante) tenha sido responsável por defini-las.

<div id="types-of-permissions-advertisers-can-grant-to-roku-ads" />

#### Tipos de permissões que os anunciantes podem conceder à Roku Ads

| Permissão | Recurso concedido |
| --- | --- |
| Configurar integração | Permitir que o parceiro configure a aba de integração (exceto postbacks de evento in-app). |
| Configurar postbacks de eventos in-app | Permitir que o parceiro configure o postback de eventos in-app.<br /><br />**Atenção!** Isso concede acesso a todos os eventos de atribuição, incluindo tráfego orgânico e não orgânico de todos os canais de mídia. |
| Acesso ao relatório de retenção | Permitir acesso apenas aos dados de retenção do próprio parceiro. |
| Acesso a dados agregados de usuários fidelizados | Permitir que o parceiro acesse sua métrica de usuários fidelizados. |
| Acesso a dados agregados de conversão | Permitir acesso a métricas de instalações, reengajamentos, reinstalações e reatribuições. Por exemplo, <Anchor target="_blank" href="/partners/pt/docs/aggregated-campaign-performance-report-for-ad-networks">relatórios agregados de performance de campanha</Anchor>. |
| Acesso a dados agregados de eventos in-app | Conceder acesso a todos os dados de eventos in-app, incluindo dados do Protect360—não apenas os eventos configurados no mapeamento de postback.  <br />Isso também inclui o acesso a dados de monetização de anúncios, que podem conter eventos de outras fontes de mídia. |
| Ver regras de validação | Permitir que o parceiro veja os detalhes da sua regra de validação. |
| Acesso a dados agregados de receita | Permitir acesso a dados de receita de anúncios para otimização de UA. |
| Usar Cost Import | Permitir que o parceiro faça upload de dados de custo usando o Cost Import. |
| Acesso ao dashboard do Protect360 e dados brutos | <ul><li>O acesso a dados brutos está disponível apenas se sua assinatura incluir Protect360, Regras de Validação ou Dados Brutos.</li><li>Concede acesso ao dashboard do Protect360, incluindo o ProtectLITE.</li><li>**Atenção:** O ProtectLITE inclui acesso ao dashboard, mas não fornece acesso a dados brutos.</li></ul> |

</Accordion>

<div id="setting-up-roku-ads-integration-for-agencies" />

## Configurando a integração da Roku Ads para agências

Agências que trabalham em nome de anunciantes podem ativar a integração com o Snapchat e começar a receber atribuição por suas campanhas. No entanto, essa integração tem algumas limitações para agências.

<div id="agency-limitations" />

### Limitações da agência

* Uma agência pode acessar a integração com a Roku Ads somente depois que o anunciante com quem ela trabalha ativar a integração.
* Os parâmetros de atribuição exibidos na página de integração da agência são herdados da integração do anunciante no modo visualização.

**Para configurar a Roku Ads para agências:**

1. Na AppsFlyer, no menu lateral, abra <Image alt="collaborate.png" src="https://files.readme.io/70400e32ef967b981aabd47faf97880368585fdf52ad29c0d4c2d4c31751e6a3-37844129188753.png" width="2%" /> **Colaborar** > **Partner Marketplace**.
2. Procure por **Roku Ads (rokuads\_int)** e selecione-a.
3. Insira o **Roku Ads Account ID** da sua agência. Isso identifica o tráfego da agência e o distingue do tráfego do anunciante.
4. Clique em **Salvar integração**.

<div id="warning" />

> ❗️ **Aviso**
>
> Os Roku Ads account IDs NÃO devem ser compartilhados entre o anunciante e a agência. Caso contrário, TODAS as instalações do anunciante serão atribuídas automaticamente no dashboard da agência.

<div data-zendesk-anchors="overview=sobre-a-atribui%C3%A7%C3%A3o-da-roku-ads roku-attribution-flow=fluxo-de-atribui%C3%A7%C3%A3o-da-roku 01H7Z13QPBTKZ9BVCMGASYEM0R=fluxo-de-atribui%C3%A7%C3%A3o-da-roku setting-up-roku-ads=configurando-a-integra%C3%A7%C3%A3o-da-roku-ads-para-anunciantes general-settings=configura%C3%A7%C3%B5es-gerais h_01K0P7PHA89T432XNW0C4BZ4VH=configura%C3%A7%C3%B5es-gerais install-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o h_01K0P7PHA8X7E7MC7JNVG86JAV=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o reengagement-attribution=atribui%C3%A7%C3%A3o-de-reengajamento h_01K0P7PHA8GR0SYPNKSP4D90AF=atribui%C3%A7%C3%A3o-de-reengajamento ignore-active-users-for-retargeting=ignorar-usu%C3%A1rios-ativos-para-retargeting h_01K0P7PHA85619R1SM4SR49TQ3=ignorar-usu%C3%A1rios-ativos-para-retargeting crossplatform-attribution=atribui%C3%A7%C3%A3o-cross-platform h_01K0P7PHA80KKG06719ZWE8JB0=atribui%C3%A7%C3%A3o-cross-platform inapp-events-postbacks=postbacks-de-eventos-in-app h_01K0P7PHA89Y8W70NTF40S6PC4=postbacks-de-eventos-in-app cost-tab-for-cost-clicks-and-impressions=cost-tab h_01K0P7PHA840N225ABCSGTTCAN=importante types-of-permissions-advertisers-can-grant-to-roku-ads=tipos-de-permiss%C3%B5es-que-os-anunciantes-podem-conceder-%C3%A0-roku-ads h_01K0P7PHA8D7WQR02129YADZZP=tipos-de-permiss%C3%B5es-que-os-anunciantes-podem-conceder-%C3%A0-roku-ads setting-up-agencies=configurando-a-integra%C3%A7%C3%A3o-da-roku-ads-para-ag%C3%AAncias setting-up-roku-ads-integration-for-agencies=configurando-a-integra%C3%A7%C3%A3o-da-roku-ads-para-ag%C3%AAncias agency-limitations=limita%C3%A7%C3%B5es-da-ag%C3%AAncia h_01K0P7PHA8MSV6Q13P9ATAX8SJ=limita%C3%A7%C3%B5es-da-ag%C3%AAncia h_01K0P7PHA8KXP5H9WXJ1J2VFR2=aviso" />

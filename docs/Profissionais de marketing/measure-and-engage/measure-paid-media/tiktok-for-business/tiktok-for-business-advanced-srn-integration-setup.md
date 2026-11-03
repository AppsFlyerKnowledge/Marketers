---
title: TikTok for Business—configuração da integração de Advanced SRN
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-06-09T16:49:57Z'
  edited_at: '2026-11-03T01:31:27Z'
  id: 6722785184913
  locale: pt
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/pt/articles/6722785184913
---
> **At a glance:** O TikTok for Business (tiktokglobal\_int) é uma rede avançada de autorrelato (SRN) que permite que proprietários de aplicativos mensurem a atribuição mobile baseada em cliques e visualizações com a AppsFlyer. Isso inclui instalações de aplicativos provenientes de campanhas de aplicativos fora do mobile.

> 📘 **Note**
>
> Em 30 de janeiro de 2023, a nova integração do TikTok for Business (Advanced SRN) `tiktokglobal_int` foi adicionada. A integração [Legacy] TikTok for Business `bytedanceglobal_int` foi descontinuada gradualmente e oficialmente descontinuada em 20 de março de 2024. O TikTok cuida dessa transição e notificará você quando puder excluir a integração antiga. Para evitar qualquer perda de dados, certifique-se de manter ambas as integrações ativas durante a fase de transição. Saiba mais em nosso <Anchor target="_blank" href="/marketers/pt/docs/bulletin-tiktok-for-business-advanced-srn">boletim</Anchor>.
>
> A AppsFlyer oferece suporte à mensuração da atividade do aplicativo para [campanhas não relacionadas a aplicativos](#web-para-aplicativo-mensure-a-atividade-do-aplicativo-para-campanhas-que-não-são-do-aplicativo).

<Image alt="TTFB_logo__4C_stacked_black_1.png" src="https://files.readme.io/f876dca1810a33266ad93de7822354d3a9aeb41a1e064a1f85f7120f713e699d-23689976309905.png" width="218px" />

## Visão geral

Na integração Advanced SRN, todo o tráfego que inclui um advertising ID é atribuído e relatado como tráfego regular de SRN. Quando um ID de publicidade não está disponível, a AppsFlyer mensura a atribuição com base em cliques e impressões do TikTok, de acordo com as restrições de privacidade.

## Configurar o TikTok for Business

**Pré-requisito:** Antes de configurar a integração, <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entre em contato com o parceiro</Anchor> e abra uma conta com ele.

**Para ativar ou editar a integração:**

1. **Para ativar:** Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Marketplace de parceiros**.  
   **Para editar:** Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações ativas**.
2. Pesquise por **TikTok for Business** e selecione-o.
3. Clique em **Configurar integração**. Você será direcionado para a página de configuração da integração.
4. Na aba **Integração**, selecione o aplicativo para a integração e ative **Ativar parceiro**.  
   **Observação:** O botão deve permanecer ativado <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">(ativado)</Anchor> durante todo o tempo em que você trabalhar com o parceiro.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração inclui as seguintes abas: Integração, link de atribuição, custo, receita de anúncios e permissões. A aba **Link de atribuição** não está disponível para o TikTok for Business; as abas restantes são opcionais.

> 📘 **Note**
>
> Algumas configurações são diferentes para dispositivos iOS e Android
>
> Ao configurar uma campanha, o nome da campanha não deve começar nem terminar com um espaço, pois isso pode causar discrepâncias em dashboards e relatórios. Saiba mais sobre <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=9535">como configurar uma campanha no TikTok</Anchor>.
>
> Os anúncios provenientes do <Anchor target="_blank" href="https://www.tiktok.com/business/en/blog/introducing-tiktok-search-ads-toggle">TikTok Search Ads Toggle</Anchor> estão incluídos em todas as atribuições do TikTok. A AppsFlyer não recebe dados sobre termos de pesquisa ou palavras-chave específicos.

<Accordion title="Aba de integração">

A aba **Integração** inclui várias seções, conforme descrito abaixo.

#### Ativar parceiro

Para configurar a integração, você primeiro precisa ativar o botão de alternância **Ativar parceiro**. Para mais informações sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">como ativar e desativar um parceiro</Anchor>, consulte as integrações.

#### Compartilhamento avançado de dados

Somente para aplicativos iOS: use o **Compartilhamento avançado de dados** (ADS) para controlar como a AppsFlyer compartilha dados de instalação, reinstalação e postback com o TikTok. Somente para aplicativos iOS: Seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> depende do <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">status</Anchor> **da Privacidade Avançada (para iOS 14.5+ em diante)**.

| Compartilhamento avançado de dados: Ativado | Compartilhamento avançado de dados: Desativado |
| --- | --- |
| A AppsFlyer compartilha todas as instalações e reinstalações com o TikTok. | A AppsFlyer compartilha instalações e reinstalações apenas com usuários que deram consentimento. |
| Postbacks são enviados de acordo com sua configuração:<ul><li>**Todas as fontes de mídia, inclusive orgânicas**</li><li>**Somente este parceiro**</li></ul> | Postbacks são enviados apenas para eventos atribuídos ao parceiro<ul><li>**Usuários com consentimento:** os postbacks seguem o modelo padrão.</li><li>Os postbacks são enviados de acordo com o <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Template de privacidade avançada</Anchor></li></ul> |

> 📘 **Note**
>
> Ao ativar a integração (`tiktokglobal_int`), a opção **Privacidade Avançada** é ativada por padrão.

#### Compartilhamento de dados de correspondência avançada

Quando o **Compartilhamento de dados de correspondência avançada** está ativado, os campos de Correspondência avançada, como e-mail com hash, número de telefone com hash, nome com hash e sobrenome com hash, são compartilhados com o TikTok se esses campos estiverem incluídos nas informações do evento enviadas à AppsFlyer. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada</Anchor>.

#### Configurações gerais

**ID do aplicativo TikTok**

Um código exclusivo gerado no TikTok Ads Manager e usado pelo TikTok para confirmar a propriedade do anunciante de seus aplicativos. Embora não seja obrigatório, é recomendável inserir IDs de aplicativo para cada um dos seus aplicativos. Isso ajuda você a controlar melhor seus dados no TikTok for Business e a desbloquear produtos adicionais.

**Para adicionar seus IDs do aplicativo:**

1. [Opcional] Insira o <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001060">ID do aplicativo TikTok</Anchor>, disponível no dashboard do TikTok Ads.
2. [Opcional] Para adicionar mais IDs do aplicativo:
   1. Depois de inserir o primeiro ID do aplicativo, pressione a tecla Enter.
   2. Insira seu próximo ID do aplicativo TikTok.

> 📘 **Note**
>
> Configurar um ID do aplicativo do TikTok não afeta seus dados na AppsFlyer.
>
> Ao migrar para a nova integração (`tiktokglobal_int`), todos os valores da integração legada (`bytedanceglobal_int`) são preenchidos automaticamente neste campo.
>
> <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10001070">Saiba mais sobre os requisitos do TikTok App ID para iOS 14</Anchor>.

#### Postbacks padrão

Configure como enviar postbacks para **instalações** do aplicativo. Para **instalações rejeitadas** e **reengajamentos**, os postbacks são enviados apenas para o TikTok for Business.

* **Apenas este parceiro** [Padrão]: Envie postbacks somente quando o evento for atribuído a este parceiro, ou seja, quando o usuário que o realizou tiver vindo deste parceiro.
* **Todos os canais de mídia, incluindo orgânicos**: Envie postbacks para eventos atribuídos a qualquer parceiro e para eventos orgânicos, ou seja, quando o usuário que o realizou tiver vindo de qualquer canal de mídia. O TikTok for Business recomenda alterar a seleção para **Todas as fontes de mídia, incluindo orgânicas** para melhor otimização.

> 📘 **Note**
>
> Somente para apps iOS: seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> depende do **botão de alternância de Compartilhamento avançado de dados (iOS 14.5+ e posteriores)**.
>
> Ao migrar da integração legada (`bytedanceglobal_int`) e ativar a nova integração (`tiktokglobal_int`), o estado padrão selecionado para postbacks de instalações é "**Apenas este parceiro**", independentemente do estado anterior à migração.

#### Atribuição de instalação

Defina as diferentes janelas de atribuição para atribuir novas instalações (primeiros lançamentos) de usuários que visualizaram, clicaram ou interagiram com seu anúncio. Observe que apenas as instalações dentro da janela de lookback podem ser atribuídas ao TikTok for Business.

1. Defina a **janela de lookback de clique de instalação** para 1 a 23 horas ou 1 a 30 dias. o TikTok for Business recomenda o alinhamento com eles definindo a janela de lookback de click-through para 7 dias.

> 📘 **Note**
>
> A configuração da janela de retrospectiva por clique também determina as janelas de retrospectiva para visualizações engajadas e cliques engajados.

1. [Opcional] Ative a **atribuição de view-through de instalação** e defina as janelas de lookback:
   * **Janela de lookback de view-through de instalação** entre 1 e 24 horas. **Observação:** o TikTok for Business recomenda alinhar essa configuração definindo a janela de lookback de visualização para instalação como 1 dia.

> 📘 **Note**
>
> O TikTok for Business está implementando medidas avançadas de privacidade de dados para proteger os usuários de seus serviços. A partir de 23 de outubro de 2021, o TikTok for Business fornecerá aos anunciantes dados de atribuição de visualização limitados no nível do dispositivo. Para fontes de nível de usuário, como relatórios de dados brutos, mensagens da Push API, relatórios da Pull API, página Exportar dados e Data Locker, apenas os seguintes campos são preenchidos:
>
> * Fonte de mídia (bytedanceglobal\_int)
> * Canal
> * Tipo de toque atribuído (impressão)
> * Horário do toque atribuído (relatado apenas como data, "dd/mm/yyyy")
> * A campanha é relatada como "restricted." Esses dados não estão disponíveis no GCD. Relatórios de dados agregados continuam exibindo conversões de exibição.
>
> Ao migrar da integração legada (`bytedanceglobal_int`) e ativar a nova integração (`tiktokglobal_int`), as configurações da janela de lookback (click-through e view-through) são definidas para os **valores padrão**, independentemente de seu estado antes da migração. Você pode atualizar essas configurações.

#### Atribuição de reinstalação

A atribuição de reinstalação permite a mensuração de usuários que reinstalam seu app durante a janela de reatribuição para atribuí-los a cliques e impressões elegíveis do TikTok.

Quando ativadas, as reinstalações são consideradas como novas conversões nas campanhas do TikTok e são relatadas de forma consistente com as suas configurações de atribuição de instalação. Para mais informações sobre reinstalações, consulte <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls">Mensuração de reinstalações</Anchor>.

* Para ativar a atribuição de reinstalação, na aba **Integração**, selecione **Atribuição de reinstalação**.

> 📘 **Note**
>
> Não são necessárias janelas de lookback separadas para reinstalações. A atribuição de reinstalação utiliza o mesmo status e janelas de lookback de click e view-through das suas configurações de atribuição de instalação.
>
> Quando ativada, postbacks de reinstalação elegíveis são enviados ao TikTok.

#### Atribuição de reengajamento

Defina as diferentes janelas de atribuição para atribuir novos engajamentos de seus usuários existentes que visualizaram, clicaram ou interagiram com seu anúncio. Observe que apenas reengajamentos dentro da janela de lookback podem ser atribuídos ao TikTok for Business.

1. Defina a **janela de reengajamento de clique de instalação** para 1 a 23 horas ou 1 a 30 dias. o TikTok for Business recomenda o alinhamento com eles definindo a janela de lookback de click-through para 7 dias.

> 📘 **Note**
>
> A configuração da janela de retrospectiva por cliques de reengajamento também determina as janelas de retrospectiva de reengajamento para visualizações engajadas e cliques engajados.

1. [Opcional] Ative a **atribuição de view-through para reengajamento** e defina as janelas de lookback:
   * **Janela de lookback de view-through para reengajamento** entre 1 e 24 horas. **Observação:** o TikTok for Business recomenda alinhar-se a eles definindo a janela de lookback de view-through para reengajamento como 1 dia.
2. Defina a **janela de reengajamento** como 1-23 horas, 1-90 dias ou **Lifetime**.

> ❗️ **Warning**
>
> Ao migrar da integração legada (`bytedanceglobal_int`) e ativar a nova integração (`tiktokglobal_int`), o botão de alternância **Reengajamento** fica desativado por padrão, independentemente do seu estado antes da migração. Se a sua integração legada tiver <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">campanhas de retargeting</Anchor>, ative-as na nova integração para garantir a continuidade.

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#reengagement-rules-and-windows">regras e janelas</Anchor> de reengajamento.

#### Ignorar usuários ativos para retargeting

Defina um período de tempo para <Anchor target="_blank" href="/marketers/pt/docs/set-retargeting-inactivity-window#período-de-inatividade">ignorar reengajamentos e reatribuições</Anchor> de usuários que inicializaram o seu aplicativo. Isso significa que a atividade deles durante o período da janela não é registrada na AppsFlyer.

> 📘 **Note**
>
> **São registradas** as conversões de reengajamento e reatribuição de usuários que estavam **inativos** no período de tempo definido.

1. Ative a opção **Ignorar usuários ativos para retargeting**.
2. Configure a janela de inatividade.

#### Postbacks de eventos in-app

Configure o mapeamento de eventos in-app com eventos do TikTok For Business, enviados por meio de postbacks:

1. Ative **Postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer, vem do SDK integrado ao seu aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **evento da AppsFlyer**, depois clique em **criar evento personalizado**. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de evento personalizado</Anchor>.</li></ul> |
| **mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Caixa suspensa:** selecione o evento predefinido do TikTok mais adequado.</li><li>**Sem alterações**: se você escolher **Personalizado** no menu suspenso, a AppsFlyer envia os eventos como estão, sem mapeá-los para nenhum dos eventos predefinidos do TikTok. Observe que o TikTok não usa eventos personalizados para otimização, apenas para fins de relatórios, portanto essa configuração não é recomendada pelo TikTok. Para saber mais sobre eventos padrão e personalizados do TikTok, consulte a <Anchor target="_blank" href="https://ads.tiktok.com/help/article/standard-events-parameters">documentação do TikTok</Anchor>.</li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Apenas para este parceiro** (padrão): envie postbacks somente quando esse evento for atribuído a esse parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas:** Envie postbacks para eventos atribuídos a qualquer parceiro, assim como eventos orgânicos. O TikTok for Business recomenda selecionar **Todas as fontes de mídia, incluindo orgânicas** para melhor otimização.</li></ul> |
| **incluindo** | <ul><li>**Sem valores e sem receitas** (padrão): Envie somente o evento em si, sem o valor do evento.</li><li>**Valores & sem receita**: envie todos os parâmetros, exceto o valor da receita.</li><li>**Valores & receita**: envie todos os parâmetros do evento, incluindo o valor da receita (se ele existir no evento). O TikTok for Business recomenda selecionar **Valores & receita** para uma melhor otimização.</li></ul> |

3. [Opcional] Clique no ícone **Adicionar condição** <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
4. Clique em **Salvar integração.**
5. [Opcional] Após salvar a integração, você pode integrar mais aplicativos com o parceiro em questão:
   1. No canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de aplicativos.
   2. Selecione um aplicativo diferente a partir da lista suspensa.
   3. Repita as etapas de integração para o aplicativo selecionado.

> 📘 **Note**
>
> Somente para aplicativos iOS: Seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> depende do **botão de alternância Compartilhamento avançado de dados (iOS 14.5+ e posterior)** [toggle](#compartilhamento-avançado-de-dados).
>
> Ao migrar para a nova integração (`tiktokglobal_int`), todos os eventos de postback configurados na integração legada (`bytedanceglobal_int`) são preenchidos automaticamente com a mesma configuração.
>
> * Se um evento estiver mapeado para o evento **Pay** do TikTok for Business [Legacy], ele será renomeado automaticamente para Purchase ao migrar para a nova integração.

</Accordion>

<Accordion title="Aba do link de atribuição">

Os links de atribuição não são relevantes para <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">SRNs</Anchor> ou SRNs avançadas.

As SRNs realizam a atribuição em sua própria plataforma. A atribuição para SRNs avançadas é realizada pela combinação dos dados de engajamento delas com os dados da AppsFlyer, usando as configurações de atribuição que você definiu na [aba Integração](#integration-tab).

</Accordion>

<Accordion title="Aba Custo (para custo, cliques e impressões)">

Essa integração fornece dados agregados sobre custo, cliques e impressões para suas campanhas, conjuntos de anúncios, anúncios e regiões geográficas/países. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis.

os dados sobre cliques e impressões estão incluídos na integração. No entanto, **os dados de custo exigem uma** <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview?query=xpend">**assinatura do ROI360**</Anchor> **assinatura**.

**Para habilitar a conexão da API para custo, cliques e impressões com o TikTok for Business:**

1. Aceda ao separador **Custo** e ative a opção **Obter dados de custo**.
2. Clique em **Fazer login no TikTok Ads**.
3. Na janela do TikTok que se abre, faça login na sua conta do TikTok e confirme as permissões necessárias.
4. Depois que uma mensagem de sucesso aparecer na janela do TikTok, feche-a. Os detalhes da sua conta do TikTok agora aparecem em **Contas conectadas**.
5. Em **IDs da conta do anunciante** > **ID do anunciante**: insira o ID da conta do anunciante do TikTok e clique em **Adicionar**.

> 📘 **Note**
>
> Para obter o seu **ID do anunciante** da sua conta comercial do TikTok: Vá para **Usuários** > **Membros** e, na conta do anunciante, você pode ver o código.
>
> Certifique-se de que o **ID do anunciante** que você adicionou esteja associado à **conta do TikTok** que você conectou na etapa 2, pois esta é a conta da qual os dados serão coletados.
>
> Conecte pelo menos um **ID de anunciante**. Você pode adicionar até 30.

1. Clique em **Salvar custo**.

#### Para assinantes do ROI360

* Anunciantes e agências que têm a API de custo habilitada nas integrações `bytedanceglobal_int` legada e `tiktokglobal_int` atual podem ver dados de custo duplicados. Para evitar isso, vá para a integração `bytedanceglobal_int` > aba **Custo** e desative a alavanca. No entanto, ao ativar a nova integração de custos, os dados de custos dos 5 dias anteriores ao dia da transição são automaticamente recolhidos. Isso significa que espera-se que a nova integração mostre dados de custos duplicados nesses cinco dias. Por exemplo, se a integração de custo antiga foi desativada em 15 de janeiro e a nova integração de custo foi ativada no mesmo dia, dados de custo duplicados aparecem na nova integração de custo entre 10 e 14 de janeiro, mesmo que a nova integração de custo só tenha sido ativada em 15 de janeiro.
* Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis.
* <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da API de custo</Anchor> e a última vez em que a AppsFlyer conseguiu extrair dados de custo correspondentes, seja no dashboard de status da integração de custo (e receita de anúncios), seja no dashboard individual da ad network.
* Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">como habilitar a API de custo</Anchor>.

</Accordion>

<Accordion title="Aba receita de anúncios">

Para enviar seus dados de receita de anúncios ao TikTok para otimização de aquisição de usuários (UA), você pode configurar <Anchor target="_blank" href="/marketers/pt/docs/share-ad-revenue-data-with-partners">postbacks de receita de anúncios ou sinais de UA</Anchor>.

Para obter dados de receita de anúncios do Pangle, use a integração de parceiro Pangle (receita de anúncios).

</Accordion>

<Accordion title="Aba permissões">

Neste separador, pode definir permissões para conceder ao TikTok for Business o acesso aos seus dados e executar várias ações.

Observe que, mesmo depois que a integração for <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">desativada</Anchor>, o botão de alternância **Permissões do TikTok for Business** ainda concede permissões.

Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">conceder permissões</Anchor>.

</Accordion>

## Deep linking com o TikTok for Business

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/understanding-deeplinks-and-deferred-deeplinks?lang=en">O TikTok é compatível com deep linking e deferred deep linking</Anchor> para vários objetivos de campanha no nível do anúncio ao criar uma campanha, um grupo de anúncios e um anúncio. A criação de links diretos para o usuário navegar para um conteúdo específico permite que você veicule conteúdo personalizado com base no envolvimento do usuário com seu anúncio do TikTok.

### Acesse os dados de conversão do TikTok pela API GCD da AppsFlyer para deep linking

A AppsFlyer fornece várias soluções para deep linking diferido:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">**UDL (Unified deep linking)**</Anchor>: os cliques do TikTok incluem um campo <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#deep_link_value">deep\_link\_value</Anchor> (quando um deep link é definido para o anúncio) e são compatíveis com a solução UDL.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">**GCD (Get Conversions Data) API**</Anchor>: esta é a opção recomendada para acessar os dados de conversão do usuário do TikTok em tempo real, diretamente no nível do SDK. Os dados retornados na GCD API incluem <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_dp">`af_dp`</Anchor>, que contém o destino do deep link (destino do usuário no aplicativo).
* **Usando parâmetros de dados de conversão,** você pode criar uma lógica personalizada para orientar o usuário até seu conteúdo usando outros parâmetros, como o nome da campanha, o nome do conjunto de anúncios ou qualquer outro campo retornado nos dados de atribuição para instalações do TikTok.

## Web para aplicativo: mensure a atividade do aplicativo para campanhas que não são do aplicativo

A integração da AppsFlyer com o TikTok permite a mensuração completa da atividade do aplicativo, como instalações, reengajamentos e eventos in-app, para campanhas não relacionadas a aplicativos atribuídas ao TikTok for Business.

Por exemplo, as instalações de aplicativos podem ser mensuradas mesmo quando o destino do anúncio é uma web landing page, permitindo a mensuração da jornada web-to-app (W2A).

Ao seguir os passos abaixo no TikTok Ads Manager, você pode mensurar a atividade do aplicativo a partir de campanhas não relacionadas a aplicativos e obter insights valiosos sobre o comportamento do usuário. Você também pode ver a <Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-measure-app-activity-for-non-app-promotion-campaigns?lang=en">documentação do TikTok</Anchor>.

1. Vá para a página da campanha de anúncios do TikTok e selecione **Editar anúncio**.
2. Em **rastreamento** > **eventos do aplicativo**, selecione seu aplicativo.
3. Clique em **salvar**.
4. Repita essas etapas para todos os anúncios relevantes da sua campanha.

## Configurar o TikTok for Business para agências

As agências que trabalham em nome dos anunciantes podem ativar a integração do TikTok for Business e começar a receber atribuição para suas campanhas. Contudo, esta integração tem algumas limitações quando se trata de agências.

### Limitações da agência

As seguintes limitações se aplicam quando uma agência trabalha com essa integração:

| Caraterística | Descrição |
| --- | --- |
| O acesso depende do anunciante | Uma agência pode acessar a integração do TikTok for Business somente depois que o anunciante com quem trabalha a tiver ativado. |
| Parâmetros de atribuição somente para visualização | A partir de 1º de janeiro de 2024, os parâmetros de atribuição exibidos na página de integração da agência serão herdados da integração do anunciante no modo **somente visualização**. Isso significa que a agência pode ver como o anunciante configurou as janelas de lookback de atribuição, mas não pode configurá-las por conta própria. |
| Sem controle sobre o Compartilhamento avançado de dados | Uma agência não pode ativar a configuração de Compartilhamento avançado de dados, mesmo quando recebe permissão. Isso é limitado apenas ao anunciante. |
| Configuração do evento in-app | Com a <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#configure-inapp-event-postbacks::8743ba60">permissão</Anchor> do anunciante, uma agência pode configurar postbacks de eventos in-app. |
| Recomenda-se o alinhamento do mapeamento | Ao mapear postbacks de eventos no aplicativo, recomendamos verificar se a configuração de mapeamento é idêntica para a agência e o profissional de marketing. |

**Para configurar o TikTok for Business para agências:**

1. Na AppsFlyer, em **Configuração**, vá para **Marketplace de parceiros**.
2. Encontre **TikTok for Business** e selecione-o.
3. Insira o **ID do aplicativo TikTok**.
4. Insira **o ID da conta TikTok** da sua agência. Isso **identifica o tráfego da agência e o distingue do tráfego do anunciante.**
5. Clique em **Salvar Integração**.

   <Image alt="tiktok.png" src="https://files.readme.io/b13ee9cd005b97c37019154a0caa10e03b846e7405777d9fc0e3db11bfb233b4-33379202036369.png" width="664px" />

> 🚧 **Important**
>
> Os IDs das contas do TikTok for Business não devem ser compartilhados entre o anunciante e a agência. Se forem compartilhados, todas as instalações do anunciante serão automaticamente atribuídas no dashboard da agência.

## Enviar eventos in-app complexos para o TikTok

Para enviar eventos in-app complexos, com vários itens, para o TikTok, recomendamos usar o novo objeto de evento `af_order_info`. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/item-level-order-data-for-ad-networks-af-order-info">Dados de pedido em nível de item para ad networks (af\_order\_info)</Anchor>.

O TikTok oferece suporte a até 7 campos nesse objeto, permitindo que anunciantes compartilhem vários pontos de dados sobre cada item incluído no evento.

## Relatório de campanhas Smart Plus

Smart Plus é um novo tipo de campanha do TikTok que permite que os anunciantes testem múltiplos criativos dentro da mesma unidade de anúncio, ajudando a otimizar a performance através de testes criativos automatizados.

<Anchor target="_blank" href="https://ads.tiktok.com/help/article/about-smart-plus-campaign?lang=en">Saiba mais sobre campanhas Smart Plus</Anchor>.

### Como campanhas Smart Plus são estruturadas

Ao contrário das campanhas padrão do TikTok, que incluem três níveis (campanha, grupo de anúncios e anúncio), as campanhas Smart Plus adicionam uma quarta camada, criativo.

1. Campanha
2. Conjunto de anúncios
3. Anúncio
4. Criativo

### Como os dados das campanhas Smart Plus são relatados na AppsFlyer

A AppsFlyer mapeia os dados das campanhas Smart Plus da seguinte forma:

| Nível no TikTok | Equivalente na AppsFlyer | Observações |
| --- | --- | --- |
| Campanha | Campanha | Mapeado diretamente |
| Grupo de anúncios | Conjunto de anúncios | Mapeado diretamente |
| Anúncio | Não aplicáveis | Não mapeado na AppsFlyer |
| Criativo | Anúncio | Mapeado a nível de anúncio na AppsFlyer |

> 📘 **Note**
>
> A estrutura de mapeamento da AppsFlyer para campanhas Smart Plus é diferente do mapeamento no TikTok Ads Manager. No TikTok Ads Manager, os relatórios são exibidos apenas até o nível de anúncio, sem uma análise específica por criativo. Já a AppsFlyer mapeia dados de criativos diretamente em nível de anúncio. Assim, você pode notar algumas discrepâncias nos dados de performance da AppsFlyer e do TikTok.

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H8VVCC8G3ZXZJMHSMJ67GMG4=vis%C3%A3o-geral set-up-tiktok-for-business-integration=configurar-o-tiktok-for-business 01H8VVCC8GPY4SEFGK30Q1BJZ6=configurar-o-tiktok-for-business activate-partner=ativar-parceiro 01H8VVCC8G0KR4AA2HD9S8QBKD=ativar-parceiro advanced-data-sharing=compartilhamento-avan%C3%A7ado-de-dados 01H8VVCC8G0Z6ZHC10KVY9CGGQ=compartilhamento-avan%C3%A7ado-de-dados h_01_advanced-matching-data-sharing=compartilhamento-de-dados-de-correspond%C3%AAncia-avan%C3%A7ada advanced-matching-data-sharing=compartilhamento-de-dados-de-correspond%C3%AAncia-avan%C3%A7ada general-settings=configura%C3%A7%C3%B5es-gerais 01H8VVCC8GSDPSNN0AJPVZPR8P=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o 01H8VVCC8GW677RN6R6CV35KGG=postbacks-padr%C3%A3o install-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o 01H8VVCC8GK8VFPBEPAMVHCAWM=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o reinstall-attribution=atribui%C3%A7%C3%A3o-de-reinstala%C3%A7%C3%A3o h_01K6D37PG96P2MG99BETK25GYA=atribui%C3%A7%C3%A3o-de-reinstala%C3%A7%C3%A3o reengagement-attribution=atribui%C3%A7%C3%A3o-de-reengajamento 01H8VVCC8HHG5290PYF0BT29QA=atribui%C3%A7%C3%A3o-de-reengajamento ignore-active-users-for-retargeting=ignorar-usu%C3%A1rios-ativos-para-retargeting h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignorar-usu%C3%A1rios-ativos-para-retargeting inapp-event-postbacks=postbacks-de-eventos-in-app 01H8VVCC8HHZRFQ2T1X478YZMP=postbacks-de-eventos-in-app for-roi360-subscribers=para-assinantes-do-roi360 01H8VVCC8HWDC9A03FRY5BC87Y=para-assinantes-do-roi360 deep-linking-with-tiktok-for-business=deep-linking-com-o-tiktok-for-business h_01JJM8MPX2X37WVR86S7786S06=deep-linking-com-o-tiktok-for-business access-tiktok-conversion-data-via-appsflyers-gcd-api-for-deep-linking=acesse-os-dados-de-convers%C3%A3o-do-tiktok-pela-api-gcd-da-appsflyer-para-deep-linking h_01HVQR1TC5WVRDS24R9ZKD2HW2=acesse-os-dados-de-convers%C3%A3o-do-tiktok-pela-api-gcd-da-appsflyer-para-deep-linking measure-app-activity-for-nonapp-campaigns=web-para-aplicativo-mensure-a-atividade-do-aplicativo-para-campanhas-que-n%C3%A3o-s%C3%A3o-do-aplicativo h_01J7MYAMBQ8M0JN005FSXQDZNS=web-para-aplicativo-mensure-a-atividade-do-aplicativo-para-campanhas-que-n%C3%A3o-s%C3%A3o-do-aplicativo set-up-tiktok-for-business-for-agencies=configurar-o-tiktok-for-business-para-ag%C3%AAncias 01H8VVCC8HVNNQ9PJS4ZQCVDNS=configurar-o-tiktok-for-business-para-ag%C3%AAncias agency-limitations=limita%C3%A7%C3%B5es-da-ag%C3%AAncia h_01HHVGS94CB9XC0T63VFDZ18JS=limita%C3%A7%C3%B5es-da-ag%C3%AAncia send-complex-in-app-events-to-tiktok=enviar-eventos-in-app-complexos-para-o-tiktok h_01M22GT5M1VJ691TX74VN18SYX=enviar-eventos-in-app-complexos-para-o-tiktok smart-plus-campaigns-reporting=relat%C3%B3rio-de-campanhas-smart-plus h_01K9AGYS6XCDS3193ZAK7Z208F=relat%C3%B3rio-de-campanhas-smart-plus how-smart-plus-campaigns-are-structured=como-campanhas-smart-plus-s%C3%A3o-estruturadas h_01K9AGYS6XSXJ9DD6XYDHVYMYK=como-campanhas-smart-plus-s%C3%A3o-estruturadas how-smart-plus-data-is-reported-in-appsflyer=como-os-dados-das-campanhas-smart-plus-s%C3%A3o-relatados-na-appsflyer h_01K9AGYS6XYT763ST1H1T4SXT8=como-os-dados-das-campanhas-smart-plus-s%C3%A3o-relatados-na-appsflyer" />

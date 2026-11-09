---
title: Implemente regras de validação para evitar fraudes
metadata:
  keywords:
    - Advertisers
    - validation rule
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2017-09-14T14:43:46Z'
  edited_at: '2026-11-02T01:04:25Z'
  id: 115004703926
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/115004703926
---
> **At a glance:** adicione uma camada personalizada de proteção contra campanhas e fraudes direcionadas incorretamente. As regras permitem que os proprietários de aplicativos controlem quais instalações e eventos in-app são bloqueados ou atribuídos à fonte válida mais recente.

<Image align="center" alt="5906_animation-750x330__1_.gif" src="https://files.readme.io/2a5fbee83bdbc342c744f8079b743f06cb3205697bd9caa183593c411ae03d08-360014483338.gif" />

<div id="overview" />

## Visão geral

* As regras de validação são definidas no criador de regras usando condições personalizadas e lógicas que filtram e selecionam quais instalações do aplicativo ou eventos in-app devem ser mantidos ou bloqueados.
* As regras se baseiam em uma variedade de parâmetros para vários casos de uso, incluindo:
  * Instalações não direcionadas para sua campanha (geolocalização ou versão do sistema operacional errada, etc.)
  * Instalações que não atendem à ordem de inserção acordada com a ad network
  * Hijacking de instalações por redes fraudulentas
  * Instalações falsas ou eventos in-app enviados de bots, emuladores ou device farms
* As regras definidas para eventos in-app só entram em vigor em eventos in-app associados a instalações que não foram bloqueadas anteriormente.
* As regras que incluem uma ad network são visíveis para a equipe dessa ad network (mas essa equipe não pode ver outras ad networks incluídas na regra). Isso faz parte do interesse da transparência, que ajuda as ad networks a entenderem melhor a performance do tráfego que elas oferecem.
* As regras são executadas em tempo real e tomam medidas imediatas. Saiba mais na seção de [resultados](/docs/implement-validation-rules-to-prevent-fraud#outcomes).
* O modo tagged permite que você teste as regras de validação com tráfego em tempo real antes de bloquear a atribuição. Quando uma regra é definida como "tagged", a AppsFlyer sinaliza instalações correspondentes e eventos in-app para relatórios e análises, mas a atribuição não é afetada. Use o modo tagged para monitorar o comportamento da regra, identificar possíveis falsos positivos e confirmar o impacto antes de alterar o status para "implemented". Veja mais na seção [Modo VR tagged](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact).
* Outras opções de regra de validação estão disponíveis para os clientes do <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide">Protect360</Anchor>, além do bloqueio e detecção automáticos de fraudes do Protect360. Essas condições são conhecidas por ajudar na detecção de vários tipos de hijacking de instalação, instalação falsa e fraude de eventos in-app falsos.  
  **Atenção:** as regras de validação validam apenas instalações/eventos in-app que não foram identificados como fraude pelo Protect360.

<Accordion title="Engajamentos">

* Para instalações: as regras de validação, dependendo da ação selecionada, bloqueiam a atribuição e a corrigem para a última fonte de mídia válida ou bloqueiam completamente a atribuição.
* Para eventos in-app: As regras de validação bloqueiam a atribuição do evento in-app.
* Consulte a tabela a seguir mostrando os resultados do tipo de bloco de regra de validação.

<table><thead><tr><th> </th><th>Tipo de bloqueio</th><th>A descrição</th><th>Onde os dados de instalação podem ser visualizados</th><th>Eventos in-app que se seguem</th></tr></thead><tbody><tr><td rowspan="2"><strong>de instalações</strong></td><td>Bloquear atribuição e corrigi-la para a última fonte de mídia válida.</td><td><ul><li><span>Selecionado quando você considera a instalação real, mas suas condições determinam quais canais devem ou não ser atribuídas a ela. </span></li><li><span>A atribuição é corrigida e a instalação é atribuída ao último canal de mídia válido.</span></li><li><span>Se nenhum canal de mídia válido for identificado, a instalação será marcada como orgânica.</span></li></ul></td><td><ul><li>Dashboards da AppsFlyer e relatórios de dados brutos como uma instalação regular (atribuída ao último canal de mídia válido)</li><li>Com o Protect360 Premium:<ul><li><a href="./protect360-dashboard#dashboard-de-instalação" target="_blank">Dashboard de instalações do Protect360</a></li><li>Relatório de dados brutos de instalações do Protect360 (<span>com a fonte de mídia bloqueada)</span> </li></ul></li><li>Sem o plano Protect360 Premium:<ul><li>Relatório de dados brutos de instalações do Protect360 (<span>com a fonte de mídia bloqueada)</span> </li></ul></li></ul></td><td><ul><li>Tem a mesma atribuição corrigida que a instalação</li><li>Dados disponíveis com o plano Protect360 Premium:<ul><li>Com atribuição corrigida nos dashboards e relatórios da AppsFlyer como um IAE regular</li><li>Com fonte de mídia bloqueada no dashboard de eventos in-app do Protect360 e relatório de dados brutos de eventos in-app bloqueados do Protect360</li></ul></li></ul></td></tr><tr><td>Marque instalações como inválidas e não faça sua atribuição</td><td><ul><li><span>Selecionado quando as instalações inválidas com base nas condições da regra são consideradas falsas.</span></li><li><span>A instalação não é atribuída (nem como não-orgânica ou orgânica)</span></li></ul></td><td><ul><li>Com o Protect360 Premium:<ul><li><a href="./protect360-dashboard#dashboard-de-instalação" target="_blank">Dashboard de instalações do Protect360</a></li><li>Relatório de dados brutos de instalações do Protect360 (<span>com a fonte de mídia bloqueada)</span> </li></ul></li><li>Sem o plano Protect360 Premium:<ul><li>Relatório de dados brutos de instalações do Protect360 (<span>com a fonte de mídia bloqueada)</span> </li></ul></li></ul></td><td><ul><li><span>Bloqueado</span></li><li><span>Dados disponíveis com o plano Protect360 Premium no dashboard de eventos in-app do Protect360 e relatório de dados brutos de eventos bloqueados</span></li></ul></td></tr><tr><td rowspan="2">https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg</td><td>Bloquear atribuição </td><td><ul><li><span>Selecionado quando eventos in-app que são inválidos com base nas condições da regra são considerados falsos.</span></li></ul></td><td><ul><li> <span>Com o Protect360 Premium:</span><ul><li><a href="./protect360-dashboard#painel-de-eventos-in-app" target="_blank">Dashboard de eventos in-app do Protect360</a></li><li>Relatório de dados brutos de eventos in-app do Protect360</li></ul></li><li>Sem o plano Protect360 Premium: N/D</li></ul></td><td><ul><li> <span>Dados disponíveis com o plano Protect360 Premium no </span><a href="./protect360-dashboard#painel-de-eventos-in-app" target="_blank"><span>dashboard de eventos in-app</span></a><span> do Protect360 e relatório de dados brutos de eventos in-app bloqueados</span> </li></ul></td></tr><tr><td>Remover da AppsFlyer</td><td><ul><li><span>Recomendado quando há eventos in-app para os quais você não precisa de nenhum dado.</span></li><li><span>A AppsFlyer não registra esses eventos. </span></li></ul></td><td><span></span></td><td><span></span></td></tr></tbody></table>

* Somente os usuários da conta com as <Anchor target="_blank" href="/marketers/pt/docs/user-management">permissões apropriadas</Anchor> podem visualizar, adicionar e editar regras de validação.
* Quando uma atribuição de instalação é bloqueada ou atribuída a uma fonte de mídia válida em tempo real, um postback rejeitado é enviado instantaneamente para a ad network bloqueada, para agilizar seu fluxo de reconciliação. Quando a atribuição é bloqueada e corrigida para a última fonte de mídia válida, um postback também é enviado para a última ad network válida.
* Quando um evento in-app é bloqueado, um postback de rejeição é enviado instantaneamente para a ad network bloqueada.  
  **Atenção:**
  * um postback só é enviado se o conjunto de ad networks configurado para recebê-lo estiver integrado à AppsFlyer.
  * Os relatórios de postbacks e de postbacks rejeitados estão disponíveis na página de exportação.
  * Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks</Anchor> e <Anchor target="_blank" href="/partners/pt/docs/rejected-attribution-postbacks-to-integrated-partners">postbacks rejeitados</Anchor>.
* O bloqueio de instalações e a atribuição de eventos in-app afeta apenas a forma como e onde os dados são relatados na AppsFlyer. Eles não impedem o uso do aplicativo pelos seus usuários finais.
  * Se necessário, você pode usar os <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">relatórios de dados brutos de instalações e eventos in-app bloqueados</Anchor> (disponíveis via exportação, pull API e data locker), para que a lista de usuários do aplicativo seja desativada.
* Os relatórios de instalações/eventos in-app bloqueados e postbacks rejeitados contêm o nome das regras que bloquearam as instalações/eventos in-app sob o motivo do bloqueio. Consulte a seção [regras múltiplas](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules) se houver mais de uma regra.
  * Quando as instalações/eventos in-app são bloqueados pelo mecanismo antifraude do Protect360, mesmo que também haja uma regra de validação, os motivos do Protect360 são exibidos.
* As regras podem resultar em discrepâncias entre os relatórios da AppsFlyer e SRNs, como o <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-discrepancies">Meta ads</Anchor> e o<Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-faq-and-discrepancies">Google Adwords</Anchor>, pois eles implementam sua própria lógica para validar as instalações.

</Accordion>

<Accordion title="Várias regras">

* Várias regras de validação podem ser executadas na mesma instalação/evento in-app. Isso acontece quando a instalação atende às condições de várias regras.
* A instalação/evento in-app é classificada como inválida quando não cumpre as condições de nenhuma das regras separadamente.
* Em relatórios de dados brutos e postbacks rejeitados, o campo do **valor do motivo do bloqueio** contém os nomes de todas as regras que classificam a instalação ou evento in-app como inválidos.
* Várias regras para a mesma instalação são sequenciadas para serem executadas na seguinte ordem, com base nos tipos de bloqueio das regras:

| Tipos de regra/bloqueio | Pedido |
| --- | --- |
| Bloquear instalações | Atraso |
| Bloquear atribuição | Atraso |
| Bloquear evento in-app | Atraso |
| Remova da AppsFlyer e de qualquer outra parte | Removido da AppsFlyer. Outras regras são ignoradas. |
| Bloquear instalações e bloquear atribuição | <ol><li>Bloquear regras de instalação (em ordem aleatória)</li><li>Bloquear regras de atribuição (em ordem aleatória)</li></ol> |
| Bloquear instalações e bloquear atribuição através do mecanismo do Protect360 e das regras de validação | <ol><li>Bloquear instalações a partir do mecanismo do Protect360</li><li>Bloquear instalação a partir de regras de validação</li><li>Bloquear atribuição a partir do mecanismo do Protect360</li><li>Bloquear atribuição a partir de regras de validação</li></ol> |
| Bloquear eventos in-app com o mecanismo do Protect360 e regras de validação | <ol><li>Bloquear evento in-app a partir do mecanismo do Protect360</li><li>Bloquear IAE a partir das regras de validação</li></ol> |

</Accordion>

<div id="rule-builder" />

## Criador de regras

A interface de usuário do criador de regras foi projetada para criação de regras interativa. **Dica!** Familiarize-se e teste o criador de regras antes de ler este artigo em detalhes.

<div id="use-categorized-dimensions" />

### Usar dimensões categorizadas

Ao adicionar condições de regra, os parâmetros são agrupados em categorias para facilitar a configuração da regra. As categorias e os parâmetros são exibidos com base no tipo de evento selecionado e nas permissões da sua conta.

Você pode pesquisar em todas as categorias ao mesmo tempo. As categorias correspondentes são expandidas automaticamente.

Os parâmetros que não são relevantes para o tipo de evento selecionado ou não estão incluídos nas suas permissões ficam ocultos.

| Categoria | Parâmetros |
| --- | --- |
| Campanha & fonte | Canal de mídia, Campanha, ID da campanha, ID do site, Nome do conjunto de anúncios, ID do conjunto de anúncios, ID do anúncio, AF Sub 1-5 |
| Geolocalização & dispositivo | Geolocalização, plataforma, versão do SO, modelo do dispositivo, operadora, agente do usuário |
| Campo do Google Play | CTIT, dias de lookback, horas de lookback, tipo de toque de atribuição |
| Identidade | ID de usuário do cliente, IDFA, ID do anunciante, endereço IP |
| Bloquear evento in-app a partir do mecanismo do Protect360 | Versão do aplicativo, versão do SDK, instalador/loja, instalador/loja personalizado, está pré-instalado, é deeplink |
| Evento do usuário final | Nome do evento, Valor do evento, Tempo entre a instalação e o evento, Fonte do evento, Moeda, Receita |
| Engajamentos | com o anúncios |

<Image align="center" alt="New Validation Rule page.jpg" src="https://files.readme.io/23875c647c24226c09f5aa2f4dbb85264f95b09e867a053ee55bc2d3ebbc9895-21855980276753.png" />

O criador de regras contém as seguintes seções:

| Secção | Observações |
| --- | --- |
| Detalhes gerais | <ul><li>**Nome da regra -** Insira um nome para a nova regra.</li><li>**Tipo de regra -** Selecione o tipo de regra: **tempo real** ou **pós-atribuição**.</li><li>**Eventos** - Selecione o tipo de evento para o qual a regra é aplicada: **instalações** ou **eventos in-app**.</li><li>**Seleção do aplicativo -** Selecione **aplicativos selecionados** ou **todos os aplicativos.**<ul><li>Se você escolher a opção **aplicativos selecionados**:<br />**Selecione os aplicativos -** escolha os aplicativos para os quais a regra é aplicada: Um único aplicativo, vários aplicativos ou todos os aplicativos na conta.</li><li>Se **todos os aplicativos** estiverem selecionados:<br />**Incluir aplicativos futuros -** essa opção permite que aplicativos futuros sejam incluídos nessa regra.</li></ul></li></ul>Isso afeta as opções disponíveis nas seguintes seções (agência, fonte de mídia, campanha etc.)<br /><br /><br /><br />**Atenção**<br />A versão do aplicativo deve conter apenas números. Por exemplo, 2.2.1.<br /><br />Nota:<br /><br />as versões numéricas do aplicativo (por exemplo, 2.2.1) oferecem suporte a todos os operadores (iguais, maiores que, menores que, etc.).<br /><br />Se a versão do aplicativo for de texto personalizado (por exemplo, version123 ou our\_latest\_version), somente os operadores "igual a" ou "não é igual a" funcionarão; "maior do que" ou "inferior do que" não será aplicado. |
| Fontes de tráfego | Origem do tráfego para a qual a regra é aplicada. [Veja também fontes do Protect360](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) |
| Condições | Escolha se deseja bloquear instalações/eventos in-app que "correspondem" ou "não correspondem" às condições definidas.<ul><li>**Condições de correspondência -** a atribuição será bloqueada para instalações/eventos in-app que correspondam às condições definidas e a ação selecionada abaixo se aplicará a todas elas.</li><li>**Não corresponde às condições -** A atribuição será bloqueada para instalações/eventos in-app que não correspondam às condições abaixo, e a ação selecionada abaixo será aplicada a todas as instalações restantes.</li></ul>Quando **eventos in-app** são selecionados na seção **Eventos**, além das [opções de fonte regulares](/docs/implement-validation-rules-to-prevent-fraud#install-sources), os clientes têm outra opção de fonte para definir a quais eventos in-app sua regra se aplica. |
| Ações | Para instalações: selecione o que fazer com as instalações que atendem às condições especificadas:<ul><li>**Marque instalações como inválidas e não as atribua**. As instalações não aparecerão nos dashboards da AppsFlyer, exceto no Protect360 e em relatórios.</li><li>**Bloquear atribuição e corrigi-la para a última fonte de mídia válida.** Se nenhuma fonte de mídia válida for identificada, a instalação será considerada orgânica.</li></ul>Para eventos in-app: selecione o que fazer com as instalações que atendem às condições específicas:<ul><li>**Bloquear atribuição, mas mostrar nos dados do Protect360**. Os eventos não são atribuídos, mas são exibidos no dahsboard do Protect360 e nos dados brutos.</li><li>**Remover da AppsFlyer**. Os eventos não serão exibidos na plataforma da AppsFlyer.</li></ul>Consulte [resultados](/docs/implement-validation-rules-to-prevent-fraud#outcomes) para mais informações. |

<div id="validation-rule-examples" />

## Exemplos de regras de validação

<Accordion title="Fontes de instalação">

Em **Fontes**, você pode definir a origem do tráfego de instalações às quais a regra se aplica.

Existem três opções principais:

* **Todo o tráfego:** inclui instalações orgânicas e não orgânicas. Informações sobre a fonte não estão disponíveis para instalações orgânicas. Essa opção inclui todas as fontes de mídia, incluindo aquelas que serão adicionadas no futuro.  
  *Exemplo*: aplique uma regra a todo o tráfego vindo da versão do aplicativo anterior à versão X.
* **Todo o tráfego não orgânico:** aplicável a todas as fontes de tráfego não orgânico (agências ou outros), incluindo novas fontes adicionadas posteriormente.  
  *Exemplo*: bloqueie o tráfego não orgânico de uma geolocalização específica onde você não faz campanhas de UA ou retargeting.
* **Tráfego não orgânico específico:** aplica a regra apenas a agências ou canais de mídia específicos. Você deve selecionar ou adicionar manualmente canais de mídia ao editar a regra.  
  *Exemplo*: bloqueie instalações de um canal de mídia específico se o CTIT for maior que X dias.

Opções de fonte adicionais estão disponíveis para clientes do Protect360, para [instalações](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) e [eventos in-app](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions).

<table><thead><tr><th>Campo</th><th>Fonte do evento</th><th>Valor</th><th>Considerações</th></tr></thead><tbody><tr><td>Acesso para</td><td><ul><li>Neste caso,</li></ul></td><td><ul><li>Tráfego de agência e não agência</li><li>Tráfego de outras fontes</li><li>Agências transparentes (menu)</li></ul></td><td><p><span>Agências transparentes:</span></p><ul><li>agências que especificam suas fontes de mídia.</li><li>Agências que são transparentes para apenas alguns dos aplicativos selecionados são exibidas no menu de agências não transparentes.</li><li>Todas as agências devem compartilhar seus canais de mídia.&lt;/li&gt;&lt;li&gt;Agências que compartilham canais de mídia somente para alguns dos aplicativos selecionados aparecem no menu "Agências transparentes".&lt;/li&gt;&lt;/ul&gt;</li></ul></td></tr><tr><td>compras in-app</td><td><ul><li><span>Na lista</span></li><li><span>Não listados</span></li><li><span>Parâmetros</span></li><li><span>Doesn't equal</span></li><li><span>Contém</span></li><li><span>Não contém</span></li><li><span>Starts with</span></li><li><span>Ends with</span></li><li> <span>Corresponde à expressão regular</span><span></span> </li></ul></td><td><ul><li><span>Procure o valor desejado.</span></li><li><span>Selecione a partir do menu.</span></li><li><span>Selecione o valor no menu.</span></li></ul></td><td rowspan="6"><ul><li> <span>Menu se baseia em:</span><ul><li>Aplicativos e agências selecionadas.</li><li>Tráfego dos últimos 30 dias, ordenado por volume de tráfego.</li></ul></li><li><span>Indica que o tráfego recebeu uma tag das regras de validação.</span></li></ul></td></tr><tr><td>Campaign</td><td rowspan="5"><ul><li><span>Na lista</span></li><li><span>Não listados</span></li><li><span>Parâmetros</span></li><li><span>Doesn't equal</span></li><li><span>Contém</span></li><li><span>Não contém</span></li><li><span>Starts with</span></li><li><span>Ends with</span></li><li><span>Está vazio</span></li><li><span>Não está vazio</span></li><li><span>Corresponde à expressão regular</span></li></ul></td><td><ul><li>Procure o valor desejado.</li><li>Select value from menu.</li><li>Selecione o valor no menu.</li></ul></td></tr><tr><td>ID da campanha</td><td rowspan="4"><ul><li><span>Apenas texto livre.</span></li><li><span>É possível adicionar vários valores separados por espaços.</span></li></ul></td></tr><tr><td>Disponível apenas em <a href="./about-data-locker-advanced-reports" target="_blank">relatórios avançados</a>.</td></tr><tr><td>ID do conjunto de anúncios</td></tr><tr><td>Nome do adset</td></tr></tbody></table>

</Accordion>

<Accordion title="Condições de instalação">

A seção **Condições** é onde você define as condições que determinam quando as instalações são bloqueadas ou atribuídas à última fonte válida.

Você pode adicionar várias condições e grupos de condições a cada regra.

As condições são definidas de acordo com as condições, operadores e valores descritos na tabela a seguir.

<div id="bulk-upload" />

#### Upload em massa

Ao selecionar os operadores **na lista** ou **fora da lista** dentro das condições disponíveis, você tem a opção de fazer upload em massa de um arquivo CSV ao adicionar novos itens.

Para isso:

1. Selecione uma condição com um operador **na lista** ou **fora da lista** .
2. Selecione **na lista** ou **fora da lista** na lista suspensa do operador.
3. Selecione **fazer upload de arquivo CSV** na caixa **adicionar novos itens**.

Atenção: o arquivo CSV pode conter até 17 mil valores.

Opções de condição adicionais estão disponíveis para os clientes do Protect360, para [instalações](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) e [eventos in-app](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions).

<table><thead><tr><th><span>Condição</span></th><th><span>Fonte do evento</span></th><th><span>Valor</span></th><th><span>Considerações</span></th></tr></thead><tbody><tr><td><span>Campaign</span></td><td rowspan="6"><ul><li><span>Parâmetros</span></li><li><span>Doesn't equal</span></li><li><span>Não contém</span></li><li><span>Contém</span></li><li><span>Starts with</span></li><li><span>Ends with</span></li><li><span>Na lista</span></li><li><span>Não listados</span></li><li><span>Corresponde à expressão regular</span></li><li><span>Está vazio</span></li><li><span>Não está vazio</span></li></ul></td><td><ul><li>Procure o valor desejado.</li><li>Select value from menu.</li><li>Selecione o valor no menu.</li></ul></td><td rowspan="11"><ul><li> <span>Menu se baseia em:</span><ul><li>Aplicativos e agências selecionadas.</li><li>Tráfego dos últimos 30 dias, ordenado pela frequência do tráfego.</li></ul></li><li><span>Indica que o tráfego recebeu uma tag das regras de validação.</span></li></ul></td></tr><tr><td><span>ID da campanha</span></td><td rowspan="5"><ul><li><span>Apenas texto livre.</span></li><li><span>É possível adicionar vários valores separados por espaços.</span></li></ul></td></tr><tr><td><span>Disponível apenas em <a href="./about-data-locker-advanced-reports" target="_blank">relatórios avançados</a>.</span></td></tr><tr><td><span>ID do conjunto de anúncios</span></td></tr><tr><td><span>Nome do adset</span></td></tr><tr><td><span>Tipo do dispositivo</span></td></tr><tr><td><span>Geografia</span></td><td rowspan="3"><ul><li><span>Na lista</span></li><li><span>Não listados</span></li><li><span>Parâmetros</span></li><li><span>Doesn't equal</span></li></ul></td><td><ul><li><span>Pesquisar o valor desejado (com base no nome do país, código do país, estado ou cidade).</span></li><li><span>Select value from menu.</span></li></ul></td></tr><tr><td><span>Platform</span></td><td><span>Select value from menu.</span></td></tr><tr><td><span>Currency</span></td><td><p>Apenas moeda. Tipo de engajamento do colaborador</p><p>USD, NZD, SGD, IMP, ANG, MNT, BIF, BBD, HUF, ERN, AZN, AOA, PYG, MYR, GYD, VUV, SLL', FKP, DJF, GNF, LVL, MMK, MRO, RSD, CLF, XDR, ZAR, TND, PHP, KGS, XPD, RON, RUB, KMF, SCR, GIP, TRY, JEP, UYU, XCD, FJD, GHS, MVR, AWG, UGX, TOP, CVE, MKD, COP, CUC, GTQ, KZT, MXN, MGA, AUD, BDT, ISK, KRW, DZD, GGP, OMR, ZMW, MOP, CUP, JPY, SHP, LSL, ETB, BWP, MAD, AED, NGN, BRL, GEL, IDR, EUR, GBP, WST, XAF, SZL, XOF, SEK, UZS, KES, KYD, ILS, KWD, NPR, BZD, QAR, UAH, BTN, HTG, DKK, VND, SBD, JMD, IQD, LBP, XPT, HRK, HKD, JOD, PAB, CDF, VEF, XAU, BAM, CNY, SOS, XPF, GMD, DOP, XAG, KPW, BOB, BHD, BYN, BYR, LRD, BGN, AMD, CZK, CAD, LAK, EEK, MTL, PLN, LKR, BTC, MWK, LTL, ZMK, PGK, YER, PEN, KHR, RWF, BSD, AFN, ZWL, LYD, TMT, HNL, TWD, IRR, MUR, THB, ALL, TJS, SDG, BMD, CRC, NOK, SRD, MZN, CLP, STD, SYP, TZS, EGP, ARS, MDL, INR, SAR, PKR, TTD, NIO, BND, NAD, SVC, CHF</p></td></tr><tr><td><span>Sequência de caracteres</span></td><td><ul><li><span>Lower then</span></li><li><span>Menor que ou igual a</span></li><li><span>Maior que</span></li><li><span>Maior que ou igual a</span></li><li><span>Está entre</span></li><li><span>Parâmetros</span></li><li><span>Doesn't equal</span></li></ul></td><td><ul><li><span>Apenas texto livre.</span></li></ul></td></tr><tr><td><span>Nome do Adset</span></td><td><ul><li><span>Mais baixo do que</span></li><li><span>Menor que ou igual a</span></li><li><span>Maior que</span></li><li><span>Maior que ou igual a</span></li><li><span>Parâmetros</span></li><li><span>Doesn't equal</span></li><li><span>Está entre</span></li><li><span>Na lista</span></li><li><span>Não listados</span></li><li><span>Está vazio</span></li><li><span>Não está vazio</span></li></ul></td><td><ul><li><span>Procure o valor desejado.</span></li><li><span>Selecione a partir do menu.</span></li><li><span>Selecione o valor no menu.</span></li></ul></td></tr><tr><td><span>Idêntico a <a href="#device-info-advertising-id">advertising_id</a>, <a href="#device-info::e0372922">idfa</a>, <a href="#device-info::4afa15f">oaid</a>.</span></td><td><ul><li><span>Mais baixo do que</span></li><li><span>Menor que ou igual a</span></li><li><span>Maior que</span></li><li><span>Maior que ou igual a</span></li><li><span>Parâmetros</span></li><li><span>Doesn't equal</span></li><li><span>Is Between</span></li><li><span>Na lista</span></li><li><span>Não listados</span></li><li><span>Não está por último</span></li><li><span>Não está por último (maior)</span></li><li><span>Está vazio</span></li><li><span>Não está vazio</span></li></ul></td><td><ul><li>Procure o valor desejado.</li><li>Select value from menu.</li><li>Selecione o valor no menu.</li></ul></td><td><ul><li> Selecione o valor no menu.</li><li><span>Indica que o tráfego recebeu uma tag das regras de validação.</span></li><li> <span>Para "Not in last", se você tiver mais de uma série de versões, selecione "Not in last (major)". </span><a href="./implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work"><span>Saiba mais</span></a> </li></ul></td></tr><tr><td><span>Dias de lookback</span></td><td><ul><li><span>Mais baixo do que</span></li><li><span>Maior que ou igual a</span></li><li><span>Está entre</span></li></ul></td><td><ul><li><span>Texto livre: Um único valor numérico.</span></li></ul></td><td><ul><li><span>Refere-se à janela de lookback de impressão/clique em dias.</span></li><li><span>Garante que você não pague por instalações com um link de atribuição que foi modificado para permitir um período de atribuição mais longo.</span></li><li><span>Não substitui a configuração da janela de lookback no link de atribuição.</span></li><li> <span>[Recomendado] Use combinado com a condição de tipo de toque de atribuição (</span><a href="./implement-validation-rules-to-prevent-fraud#protect360-install-conditions"><span>disponível com o Protect360</span></a><span>)</span> </li></ul></td></tr><tr><td><span>Está pré-instalado</span></td><td rowspan="2"><ul><li><span>Sim</span></li><li><span>Retargeting</span></li></ul></td><td rowspan="2"><ul><li>Nenhum valor (o operador é o valor)</li></ul></td><td><ul><li> <span>Valida todos os tipos de pré-instalações:</span><ul><li><span>Pré-instalações de fábrica, ou seja, um aplicativo que vem no dispositivo como parte do sistema operacional.</span></li><li><span>Pré-instalações oferecidas, ou seja, um aplicativo promovido e oferecido aos usuários assim que o dispositivo é inicializado. Isso é feito por canais de mídia designados para pré-instalações.</span></li></ul></li><li>Para instalações com vários cliques/fontes, essa condição valida se uma das fontes é uma pré-instalação.</li></ul></td></tr><tr><td><span>Is deeplink</span></td><td><span>Um campo de deep link vazio em dados brutos é considerado "Is deeplink = No"</span></td></tr></tbody></table>

<div id="note" />

> 📘 **Atenção**
>
> As instalações orgânicas não têm campanha nem canal de mídia associados, portanto campos como **Campanha** e **Nome do conjunto de anúncios** são sempre **null** para elas, e não strings vazias. Uma regra que usa **Condições de correspondência** com o operador **Está vazio** nesses campos não corresponderá a instalações orgânicas; portanto, não as bloqueará.
>
> Para também capturar o tráfego orgânico, configure a regra com **Não corresponder às condições**, combinando suas condições com **Ou** e usando **Não está vazio** nos mesmos campos (por exemplo, **Campanha não está vazia** **Ou** **Nome do conjunto de anúncios não está vazio**, além de quaisquer outras condições de que a regra precise). Ao inverter a lógica dessa forma, a regra pode corresponder a valores null junto com strings vazias.

</Accordion>

<Accordion title="Fontes de eventos in-app">

Veja também as condições do Protect360 para [instalações](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) e [eventos in-app.](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions)

A origem é definida de acordo com o campo, operadores e valores descritos na tabela a seguir.

**Atenção**: todas as outras fontes de eventos in-app têm como base a origem da instalação à qual o IAE está associado (por exemplo, agência, fonte de mídia, campanha, ID da campanha, ID do site etc).

| Campo | Operador | Valor | Observações |
| --- | --- | --- | --- |
| Nome do evento | <ul><li>Na lista</li><li>Não listados</li><li>Igual a</li><li>Não é igual a</li><li>Contém</li><li>não contém</li><li>Starts with</li><li>Ends with</li><li>Está vazio</li><li>Não está vazio</li><li>Corresponde à expressão regular</li></ul> | <ul><li>Procure o valor desejado.</li><li>Select value from menu.</li><li>Free text (para valores que não existem nos resultados da pesquisa).</li></ul> | <ul><li>O texto livre deve ser digitado exatamente como aparece nos dados brutos.</li></ul> |

</Accordion>

<Accordion title="Condições do evento in-app">

Quando os **eventos in-app** são selecionados na seção **Eventos**, os clientes têm opções de condição adicionais para definir a quais eventos in-app sua regra se aplica. Essas condições podem ser misturadas e combinadas com qualquer uma das condições fora do Protect360 [listadas anteriormente](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

As condições do Protect360 são definidas de acordo com as condições, operadores e valores descritos na tabela a seguir.

| Condição | Operador | Valor | Observações |
| --- | --- | --- | --- |
| Nome do evento | <ul><li>Na lista</li><li>Não listados</li><li>Igual a</li><li>Não é igual a</li><li>Contém</li><li>não contém</li><li>Starts with</li><li>Ends with</li><li>Está vazio</li><li>Não está vazio</li><li>Corresponde à expressão regular</li></ul> | <ul><li>Procure o valor desejado.</li><li>Select value from menu.</li><li>Free text (para valores que não existem nos resultados da pesquisa).</li></ul> | <ul><li>O texto livre deve ser digitado exatamente como aparece nos dados brutos.</li></ul> |
| Versão do aplicativo | <ul><li>Mais baixo do que</li><li>Menor que ou igual a</li><li>Maior que</li><li>Maior que ou igual a</li><li>Igual a</li><li>Doesn't equal</li><li>Is Between</li><li>Na lista</li><li>Não listados</li><li>Não está por último</li><li>Não está por último (maior)</li><li>Está vazio</li><li>Não está vazio</li></ul> | <ul><li>Procure o valor desejado.</li><li>Select value from menu.</li><li>Free text (para valores que não existem nos resultados da pesquisa).</li></ul> | <ul><li>O menu se baseia no tráfego dos últimos 30 dias, ordenado pela frequência de tráfego.</li><li>Indica que o tráfego recebeu uma tag das regras de validação.</li><li>Para "Not in last", se você tiver mais de uma série de versões, selecione "Not in last (major)". [Saiba mais](/docs/implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work)</li></ul> |

<div id="note-1" />

> 📘 **Atenção**
>
> O nome do evento não é sensível a maiúsculas de minúsculas. Todos os nomes de eventos são convertidos automaticamente para letras minúsculas antes da avaliação. Por exemplo, se você escolher o nome como **Formulário de envio**, o sistema o converterá como um **formulário de envio**.

</Accordion>

<Accordion title="Fontes de instalação e de eventos in-app do Protect360">

Além das [opções de fontes](/docs/implement-validation-rules-to-prevent-fraud#install-sources) regulares, os clientes do Protect360 têm outra opção de fonte para definir a quais instalações sua regra se aplica. A fonte é definida de acordo com o campo, operadores e valores descritos na tabela a seguir.

| Campo | Operador | Valor | Observações |
| --- | --- | --- | --- |
| ID do site | <ul><li>Na lista</li><li>Não listados</li><li>Igual a</li><li>Não é igual a</li><li>Contém</li><li>não contém</li><li>Starts with</li><li>Ends with</li><li>Está vazio</li><li>Não está vazio</li><li>Corresponde à expressão regular</li></ul> | <ul><li>Apenas texto livre.</li><li>É possível adicionar vários valores separados por espaços.</li></ul> | <ul><li>O texto livre deve ser digitado exatamente como aparece nos dados brutos.</li></ul> |

</Accordion>

<Accordion title="Condições de instalação do Protect360">

Os clientes do Protect360 têm um conjunto adicional de condições para validar suas instalações. Essas condições podem ser misturadas e combinadas com qualquer uma das condições fora do Protect360 [listadas anteriormente](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

As condições do Protect360 são definidas de acordo com as condições, operadores e valores descritos na tabela a seguir.

<table><thead><tr><th><span>Condição</span></th><th><span>Operador</span></th><th><span>Valor</span></th><th><span>Observações</span></th></tr></thead><tbody><tr><td><span>CTIT (Click Time to Install Time, tempo do clique à instalação)</span></td><td><ul><li><span>Mais baixo do que</span></li><li><span>Maior que ou igual a</span></li><li><span>Está entre</span></li></ul></td><td><ul><li><span>Texto livre: Um único valor numérico.</span></li></ul></td><td><ul><li> Use esse campo somente se você tiver certeza de um CTIT específico (geralmente em uma geolocalização específica). Caso contrário, você pode causar o bloqueio de instalações como falso-positivas.<br/><span><strong>Atenção</strong>: o mecanismo antifraude do Protect360 tem formas sofisticadas incorporadas de identificar anomalias complexas de CTIT devido ao hijacking de atribuição, flooding de cliques, instalações falsas por bots e mais.</span> </li><li> <span>Considere usar esse campo junto com os seguintes campos:</span><ul><li>É pré-instalado</li><li>Is deeplink</li><li>Geolocalização/país</li></ul></li></ul><p>Atenção: A condição de instalação CTIT não oferece suporte ao bloqueio de instalações atribuídas ao engajamento de engaged click, apenas cliques "regulares".</p></td></tr><tr><td><span>ID de usuário cliente (CUID)</span></td><td><ul><li><span>Igual a</span></li><li><span>Doesn't equal</span></li><li><span>Não contém</span></li><li><span>Contém</span></li><li><span>Starts with</span></li><li><span>Ends with</span></li><li><span>Na lista</span></li><li><span>Não listados</span></li><li><span>Corresponde à expressão regular</span></li><li><span>Está vazio</span></li><li><span>Não está vazio</span></li></ul></td><td><ul><li><span>Apenas texto livre.</span></li><li><span>É possível adicionar vários valores separados por espaços.</span></li></ul></td><td><ul><li> <span>O menu se baseia</span> no tráfego dos últimos 30 dias, ordenado pela frequência de tráfego.</li><li><span>O texto livre deve ser digitado exatamente como aparece nos dados brutos.</span></li></ul></td></tr><tr><td><span>Versão do SDK</span></td><td><ul><li><span>Mais baixo do que</span></li><li><span>Menor que ou igual a</span></li><li><span>Maior que</span></li><li><span>Maior que ou igual a</span></li><li><span>Igual a</span></li><li><span>Doesn't equal</span></li><li><span>Is Between</span></li><li><span>Na lista</span></li><li><span>Não listados</span></li></ul></td><td><ul><li>Procure o valor desejado.</li><li>Select value from menu.</li><li>Free text (para valores que não existem nos resultados da pesquisa).</li></ul></td><td><ul><li> <span>O menu se baseia</span> no tráfego dos últimos 30 dias, ordenado pela frequência de tráfego.</li><li><span>O texto livre deve ser digitado exatamente como aparece nos dados brutos.</span></li></ul></td></tr><tr><td><span>Instalador/Loja</span></td><td rowspan="3"><ul><li>Na lista</li><li>Não listados</li><li>Igual a</li><li>Não é igual a</li></ul></td><td><p><span>Selecione o valor no menu:</span></p><ul><li>Google Play</li><li>Outras stores</li><li>Out of store</li></ul></td><td><ul><li>Google Play: a AppsFlyer identifica que o pacote de instalação é <code>com.android.vending</code>.</li><li>Outras lojas: a AppsFlyer identifica que a instalação é de uma loja externa do Android.</li><li>Fora da loja: a AppsFlyer identifica um APK que não está em nenhuma loja Android.</li></ul><p><span>Caso o dispositivo de um usuário não ofereça o parâmetro instalador/loja para a AppsFlyer, a regra não entra em vigor.</span></p></td></tr><tr><td>Instalador/Loja personalizada</td><td>Free text (para valores que não existem nos resultados da pesquisa).</td><td><ul><li>Se o cliente escolheu uma condição de "other" E também uma condição de "custom installer=X" - o bocking será apenas para o instalador X</li><li>Se o cliente escolheu uma condição de "other" OU uma condição de "custom installer=X" - o bocking será para TODOS os "outros" instaladores/lojas - e X faz parte desse grupo</li></ul></td></tr><tr><td><span>Tipo de toque de atribuição</span></td><td><ul><li><span>CLIQUE</span></li><li><span>Impressão</span></li></ul></td><td><ul><li>[Recomendado] Use junto com a condição de dias de lookback.</li><li>Para não atribuir impressões, você pode <a href="./measure-view-through-engagements#turn-off-viewthroughattribution" target="_blank">desativar a atribuição de view-through</a>.</li></ul></td></tr><tr><td><span>Operadora</span></td><td><ul><li>Na lista</li><li>Não listados</li><li>Igual a</li><li>Doesn't equal</li></ul></td><td><ul><li><span>Apenas texto livre.</span></li></ul></td><td> </td></tr><tr><td><span>Agente do usuário</span></td><td><ul><li>Contém</li><li>Não contém</li></ul></td><td><ul><li><span>Apenas texto livre.</span></li></ul></td><td> </td></tr><tr><td><span>Endereço IP</span></td><td><ul><li>Na lista</li><li>Não listados</li><li>Igual a</li><li>Doesn't equal</li></ul></td><td><ul><li><span>Apenas texto livre.</span></li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<Accordion title="Condições de eventos in-app do Protect360">

Quando os **eventos in-app** são selecionados na seção **eventos**, os clientes do Protect360 têm opções adicionais de condições para definir a quais eventos in-app sua regra se aplica. Essas condições podem ser misturadas e combinadas com qualquer uma das condições fora do Protect360 [listadas anteriormente](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

As condições do Protect360 são definidas de acordo com as condições, operadores e valores descritos na tabela a seguir.

| Condição | Operador | Valor | Observações |
| --- | --- | --- | --- |
| Fonte do evento | <ul><li>Na lista</li><li>Não listados</li><li>Igual a</li><li>Não é igual a</li></ul> | <ul><li>Procure o valor desejado.</li><li>Select value from menu.</li></ul> | Selecione SDK ou Server-to-server. |
| Valor do evento | <ul><li>Na lista</li><li>Não listados</li><li>Parâmetros</li><li>Não é igual a</li><li>Contém</li><li>não contém</li><li>Starts with</li><li>Ends with</li><li>Está vazio</li><li>Não está vazio</li><li>Corresponde à expressão regular</li></ul> | <ul><li>Apenas texto livre.</li><li>É possível adicionar vários valores separados por espaços.</li></ul> | <ul><li>Selecione seus valores preferidos.</li></ul> |
| Instalação x tempo do evento (em segundos) | <ul><li>Mais baixo do que</li><li>Maior que ou igual a</li><li>Está entre</li></ul> | texto livre. Um único valor numérico. | <ul><li>Com base no fluxo do seu aplicativo, você decide o tempo válido entre a instalação do aplicativo e um IAE.<ul><li>Exemplo: tempo necessário para alcançar o nível 5, tempo para o primeiro depósito (FTD), tempo para finalizar o check-out etc.</li></ul></li><li>O tempo é em segundos, mas você pode validar minutos, horas ou dias usando o equivalente em segundos.</li></ul> |

</Accordion>

<Accordion title="Lógica entre condições e grupos de condições">

Se você adicionar várias condições ou grupos de condições a uma regra, selecione a relação lógica entre eles usando: 

* And: o que significa que a instalação está em conformidade com todas as condições definidas.
* Or: o que significa que a instalação está em conformidade com pelo menos uma das condições definidas.

Por exemplo, se você quiser validar instalações com base tanto na plataforma quanto no sistema operacional, você deve selecionar and. Dessa forma, a plataforma definida deve sempre acompanhar o sistema operacional definido. Se quiser validar instalações com base em plataforma ou sistema operacional, você deve selecionar or.

</Accordion>

<div id="additional-features" />

## Recursos adicionais

<Accordion title="Ver lista de regras">

**Para visualizar todas as regras criadas na sua conta**:

1. Na AppsFlyer, acesse **Configurações** > **Regras de validação.**  
   A janela Regras de validação é aberta, com a lista de regras de validação.
2. Selecione sua exibição de tabela preferida usando o botão de **Ver lista/Detalhes**.
3. Filtre as regras na lista usando as opções de pesquisa e filtro.
   * Você pode pesquisar pelo nome da regra, fonte, nome da condição e valor.
   * Por exemplo, digite **7** para encontrar todas as regras definidas para uma versão do sistema operacional que contenha 7. “2.7.4”, “7.1”, etc.). Ou digite **Canadá** para encontrar regras definidas para o Canadá na condição Geolocalização.

A tabela Regras de Validação mostra 25 regras por página por padrão. Você pode alterar o número de regras mostradas por página para 10, 25 ou 50.

A pesquisa e os filtros se aplicam ao conjunto completo de regras, independentemente da página que você está visualizando.

</Accordion>

<Accordion title="Adicionar regra">

**Para configurar uma nova regra**:

1. Na AppsFlyer, acesse **Configurações** > **Regras de validação.**  
   A janela de regras de validação abre.
2. Clique em **Adicionar regra.**  
   A janela para adicionar nova regra é aberta.
3. Insira um **nome de regra**. Use um nome exclusivo que:
   * descreva precisamente a regra.
   * não seja ofensivo para ad networks, pois ele é exibido no relatório de instalações bloqueadas, assim como nos postbacks rejeitados para ad networks.
4. Complete as [seções do criador de regras](/docs/implement-validation-rules-to-prevent-fraud#criador-de-regras).
5. [Opcional] Adicione condições e/ou grupos de condições, conforme necessário. Certifique-se de selecionar a [lógica relevante entre condições/grupos de condição](/docs/implement-validation-rules-to-prevent-fraud#logic-between-conditions-and-condition-groups).
6. [Opcional] **Clique em**[Estimar impacto no tráfego](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact) para ver como sua regra afetará o tráfego.
7. Clique em **Salvar**.

<div id="note-2" />

> 📘 **Atenção**
>
> A versão do aplicativo deve conter apenas números. Por exemplo, 2.2.1.
>
> Atenção:
>
> as versões numéricas do aplicativo (por exemplo, 2.2.1) oferecem suporte a todos os operadores (iguais, maiores que, menores que, etc.).
>
> Se a versão do aplicativo for de texto personalizado (por exemplo, version123 ou our\_latest\_version), somente os operadores "igual a" ou "não é igual a" funcionarão; "maior do que" ou "inferior do que" não será aplicado.

</Accordion>

<Accordion title="Modo VR tagged">

Use o modo tagged para testar as regras de validação com tráfego em tempo real antes de bloquear a atribuição. O modo tagged indica instalações e eventos in-app que correspondem às condições das regras, mas a atribuição não é afetada.

O modo tagged aceita apenas instalações e eventos in-app.

Use o modo tagged para:

* Testar regras complexas no tráfego em tempo real antes de bloquear a atribuição.
* Identificar possíveis falsos positivos.
* Analisar por que uma regra teria sido acionada antes que você a aplique.
* Entender o impacto real no tráfego antes de alterar o status da regra para "implemented".

Recomendado: crie a regra no modo tagged, revise o tráfego sinalizado no Data Locker e altere o status para "implemented" após validar a precisão da regra. Tente concluir essa avaliação em menos de 7 dias para manter a proteção ativa.

<div id="how-tagged-mode-works" />

#### Como funciona o modo tagged

Ao criar ou editar uma regra de validação, selecione o status de detecção na seção "Resultados da regra".

* Tagged: as regras sinalizam dados correspondentes para relatórios e análises. A atribuição não é afetada.
* Implemented: a regra bloqueia ativamente a atribuição de acordo com o resultado da regra selecionada.

Atenção: O modo tagged se aplica apenas ao tráfego em tempo real a partir do momento em que a regra é salva. Ele não adiciona tags aos dados históricos.

<div id="rule-outcome-configuration" />

#### Configuração dos resultados da regra

A seção "Resultados da regra" (anteriormente nomeada "Ação"), define como a AppsFlyer lida com o tráfego que corresponde às condições da regra. Ela também fornece um resumo detalhado da configuração da regra para que você possa verificar o impacto esperado antes de salvá-la.

| Status de detecção | Impacto na atribuição | Disponibilidade de dados |
| --- | --- | --- |
| Tagged | Não. O tráfego é atribuído normalmente. | Visível nos relatórios do Data Locker. |
| Implementadas | Bloqueio ativo. A atribuição é bloqueada de acordo com o resultado da regra selecionada. | Visível nos dashboards do Protect360 e nos relatórios de exportação. |

<div id="what-to-expect-when-configuring-a-rule" />

#### O que acontece ao configurar uma regra

Quando você configura a regra, um painel de informações dinâmicas mostra o comportamento esperado com base em:

* Lógica de correspondência ou não correspondência
* Seleção de aplicativos
* Status de detecção

Quando o status de detecção está definido como "tagged", a regra funciona como uma ferramenta de descoberta. A AppsFlyer mostra uma notificação para confirmar que os dados correspondentes estão sinalizados em relatórios de exportação, incluindo Data Locker, mas não são bloqueados da atribuição.

Quando o status de detecção é definido como "implemented", as instalações ou eventos in-app que correspondem aos critérios da regra são bloqueados da atribuição ou reatribuídos de acordo com o resultado da regra selecionada. O painel de informações resume o resultado real antes de salvar a regra.

<div id="example-match-logic" />

#### Exemplo: lógica de correspondência

Para instalações detectadas que atendem às condições da regra para os aplicativos selecionados, o painel de informações pode indicar que essas instalações são:

* Bloqueadas da atribuição ou detectadas como pós-atribuição.
* Reatribuídas ao último canal não orgânico ou orgânico válido.
* Visíveis nos relatórios de exportação.

<div id="example-do-not-match-logic" />

#### Exemplo: não correspondem à lógica

Para instalações detectadas que não atendem às condições da regra para os aplicativos selecionados, incluindo apps futuros, o painel de informações pode indicar que essas instalações são:

* Bloqueadas da atribuição ou detectadas como pós-atribuição.
* Sinalizadas como fraudes sem correção de atribuição.
* Visíveis nos relatórios de exportação.

Todas as outras instalações que atendem às condições da regra nesses aplicativos não são bloqueadas.

<div id="set-a-rule-to-tagged-mode" />

#### Definir uma regra como modo tagged

Para testar uma regra de validação com o modo tagged:

1. Na AppsFlyer, acesse Configurações > Regras de validação.
2. Selecione uma regra existente ou clique em "Adicionar regra".
3. Preencha os detalhes da regra, fontes de tráfego e condições.
4. Na seção "Resultado da regra", defina o status de detecção como "tagged".
5. Clique em "Salvar".

Depois que a regra for salva, a AppsFlyer sinaliza o tráfego em tempo real correspondente para relatórios e análises. A atribuição continua normalmente.

<div id="analyze-tagged-data" />

#### Analise dados com tags

Os dados com tags das regras de validação não estão visíveis no dashboard do Protect360 ou na ferramenta de proteção contra fraudes.

Para analisar o impacto das regras com tags, use o Data Locker para exportar dados com tags. Os dados com tags são preenchidos nos relatórios de instalação e eventos in-app, para que você possa comparar o tráfego com tags com as atribuições válidas.

**Mapeamento de dados no Data Locker:**

| Dados com tags | Relatório do Data Locker | Relatório de dados brutos |
| --- | --- | --- |
| Instalações com tags | Relatório de instalações | Tagged Installs |
| Eventos in-app com tags | Relatório de eventos in-app | Relatório de Eventos in-app marcados |

**Campos de dados marcados**

Use as colunas abaixo nas exportações do Data Locker para identificar o tráfego sinalizado por regras de validação:

| Coluna | Descrição |
| --- | --- |
| Nome da regra<br /><br />(Relatório Retargeting) | O nome da regra de validação que sinalizou o registro. |
| ID da regra<br /><br />(Relatório Retargeting) | O ID exclusivo da regra de validação que sinalizou o registro. |
| detected\_rule\_name<br /><br />(Relatório do Data Locker) | O nome da regra de validação que sinalizou o registro. |
| detected\_rule\_id<br /><br />(Relatório do Data Locker) | O ID exclusivo da regra de validação que sinalizou o registro. |

<div id="change-a-tagged-rule-to-implemented" />

#### Alterar uma regra de "tagged" para "implemented"

Depois de analisar os dados com tags e confirmar se a regra está funcionando conforme o esperado, altere o status para "implemented".

Para alterar uma regra de "tagged para "implemented":

1. Na AppsFlyer, acesse Configurações > Regras de validação.
2. Selecione a regra.
3. Na seção "Resultados da regra", defina o status de detecção como "implemented".
4. Clique em "Salvar".

A partir do momento em que a regra é salva, a AppsFlyer bloqueia o tráfego correspondente de acordo com o resultado da regra selecionada.

</Accordion>

<Accordion title="Editar ou excluir uma regra">

**Para editar, excluir, ativar ou desativar uma regra**:

* Na [lista de regras](/docs/implement-validation-rules-to-prevent-fraud), selecione a ação que você deseja executar para uma regra específica.
  * Em **Ativo**: habilite ou desabilite a regra.
  * Em **Ação**: edite ou exclua a regra.

</Accordion>

<div id="faq" />

## Perguntas frequentes

<Accordion title="O que é uma 'expressão regular'?">

Um padrão de expressão regular é composto por caracteres para os quais você deseja encontrar uma correspondência. Padrões simples são construídos com caracteres para os quais você deseja encontrar uma correspondência direta. Quando a busca por uma correspondência requer algo mais do que uma correspondência direta, você pode incluir caracteres especiais no padrão.

**Exemplos**:

| **Expressão regular** | **Descrição** |
| --- | --- |
| ^abc | Começa com abc |
| xyz$ | Termina com xyz |
| ^abc.*xyz$ | Começa com abc e termina com xyz |
| ^abc.*(?&lt;xyz)$ | Começa com abc e não termina com xyz |
| ^([0-9]`{2}`) | Começa com 2 dígitos |
| "example\_param":"[5\|6] | O valor do parâmetro especificado começa com 5 ou 6. |
| ^.\{0\}$\|^\{\}$ | Está vazio, ou é apenas \{\} |

</Accordion>

<Accordion title="Por que a fonte ou condição não é exibida como um valor sugerido quando eu procuro por ela?">

Existem duas razões possíveis:

* Verifique se os aplicativos relevantes estão selecionados. Se o aplicativo não estiver selecionado, os valores não serão exibidos nos resultados da pesquisa.
* Os resultados são exibidos somente se o valor que você está procurando aparecer em seu tráfego durante os últimos 30 dias. Além disso, há um intervalo de até um dia entre quando a conversão ocorre e quando a fonte ou condição é exibida como uma opção de menu.

Se o valor não aparecer como resultado de pesquisa, você pode digitar o valor como texto livre e pressionar a tecla Enter no teclado.

</Accordion>

<Accordion title="Por que minhas opções de fonte de mídia incluem apenas Meta ads e X Ads?">

As opções de campo Fontes de mídia são afetadas pela seleção da Agência.

</Accordion>

<Accordion title="É necessário ter ambos 'and/or' dentro de condições e entre grupos específicos?">

Depende do seu caso. Às vezes, qualquer opção alcança os mesmos resultados. Outras vezes, ambas as opções são necessárias.

Por exemplo, se nos EUA você registrar instalações apenas na V10 do sistema operacional ou versões mais recentes, mas no Brasil você registrar instalações com V7 e versões mais recentes, você precisará de uma regra como:

`{[Geo = US] and [OS version = 10]} OR {[Geo = Brazil] and [OS version = 7]}`

</Accordion>

<Accordion title="As regras de validação bloqueiam cliques?">

Não. As regras de validação podem bloquear instalações, bloquear a atribuição a fontes de uma instalação (que impede que a fonte de mídia de um clique/impressão receba atribuição) e bloquear eventos in-app. No entanto, nenhuma dessas opções bloqueia o clique real e os KPIs de cliques não são afetados pela execução de regras de validação.

</Accordion>

<Accordion title="Olhando para os dados brutos, vejo que as instalações que eu esperava que seriam bloqueadas por regras de validação têm um motivo de bloqueio diferente do nome da minha regra. Por que?">

Isso significa que o bloqueio ocorreu por conta do <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#razões-para-bloqueio">mecanismo do Protect360</Anchor> e não de uma regra de validação. Consulte também [várias regras](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules).

</Accordion>

<Accordion title="As regras existentes se aplicam automaticamente ao tráfego de agências recém-integrado?">

Isso depende das configurações de **Fonte**, conforme descrito na tabela abaixo.

Se a regra não for aplicada automaticamente, você deverá editar a regra:

* Altere o campo **Agência para Tráfego de agência e de não agência** ou selecione a agência específica.

<table><thead><tr><th>Configuração de fonte</th><th>Seleção de campo de agência</th><th>A regra é aplicada se a regra foi criada antes de qualquer integração de agência com um dos seus aplicativos?</th><th>A regra será aplicada se a regra tiver sido criada após pelo menos uma integração de agência com um dos seus aplicativos?</th></tr></thead><tbody><tr><td>Todo o tráfego</td><td>N/R</td><td>Yes</td><td>Yes</td></tr><tr><td rowspan="3">Só não orgânicas</td><td>N/R</td><td>Sem</td><td>N/R</td></tr><tr><td>Tráfego de agência e de outras fontes</td><td>N/R</td><td>Yes</td></tr><tr><td><p>Tráfego de não agência e/ou</p><p>agências específicas</p></td><td>N/R</td><td>Sim</td></tr></tbody></table>

</Accordion>

<Accordion title="Como funcionam as condições 'not in last'?">

Use **Not in last** para permitir instalações das **versões mais recentes do aplicativo** e bloquear instalações de **versões mais antigas**.

* **Not in last** ***X*** **versions**: permite instalações das **últimas X versões** do aplicativo selecionado e **bloqueia** instalações de **todas as versões anteriores**.
* **Not in last (major)** ***X*** **versions**: use quando sua versão incluir **várias séries de versões principais** (por exemplo, 1.x e 2.x). Essa condição permite as **últimas X versões dentro de cada série principal** e bloqueia versões anteriores em cada série.

<div id="example-not-in-last" />

##### Exemplo: Not in last

Você tem essas versões de aplicativos existentes:

* 1.0.01
* 1.0.02
* 1.0.03
* 2.0.01
* 2.0.02
* 2.0.03

Uma regra definida com blocos **"Not in last 2 versions"**:

* **Permite**:
  * 2.0.02
  * 2.0.03
* **Bloqueia**:
  * 1.0.01
  * 1.0.02
  * 1.0.03
  * 2.0.01

<div id="example-not-in-last-major" />

##### Exemplo: Not in last (major)

Usando a mesma lista de versões acima, uma regra definida como **Not in last (major) 2 versions**:

* **Permite**:
  * 1.0.02
  * 1.0.03
  * 2.0.02
  * 2.0.03
* **Bloqueia**:
  * 1.0.01
  * 2.0.01

<div id="understand-how-the-condition-works-with-multiple-apps" />

##### **Entenda como a condição funciona com vários aplicativos**

Se você selecionar **vários aplicativos** na regra, a AppsFlyer avalia o status de **Not in last** **para cada aplicativo separadamente**.

Por exemplo, se você definir **Not in last 3 versions** e selecionar o app A, B e C:

* O aplicativo A permite suas **últimas 3 versões** com base no histórico de versões do **aplicativo A**.
* O aplicativo B permite suas **últimas 3 versões** com base no histórico de versões do **aplicativo B**.

O aplicativo C permite suas **últimas 3 versões** com base no histórico de versões do **aplicativo C**.

<div id="how-appsflyer-determines-the-latest-version" />

##### Como a AppsFlyer determina a versão mais recente

As versões mais recentes usadas pelas condições **Não está entre as últimas** não são simplesmente os números de versão mais novos no seu tráfego. A AppsFlyer calcula diariamente a lista das versões mais recentes, usando um mecanismo de proteção criado para impedir que fraudadores façam spoofing de uma versão mais recente falsa para burlar a regra.

A AppsFlyer adiciona uma versão à lista de versões mais recentes de um aplicativo apenas se a versão atender a estas três condições naquele dia:

* Ela recebeu atribuição de uma rede de autorrelato (SRN).
* Ela tem pelo menos 100 instalações atribuídas naquele dia.
* Essas instalações representam pelo menos 70% das instalações atribuídas a SRN do aplicativo naquele dia.

<div id="example-latest-version-calculation" />

##### Exemplo: cálculo da versão mais recente

Em um determinado dia, um aplicativo recebe 300 instalações atribuídas a SRN: 210 na v6.1.0, 45 na v6.2.0 e 45 na v6.3.0.

* v6.1.0 atende às três condições: tem atribuição SRN, tem mais de 100 instalações e tem uma participação de 70%. A AppsFlyer a adiciona à lista de versões mais recentes, e ela passa a fazer parte da base de comparação da regra.
* v6.2.0 e v6.3.0 não se qualificam. Cada uma tem menos de 100 instalações e representa menos de 70% do total.

Se nenhuma versão atender às três condições em um determinado dia, a AppsFlyer não atualiza a lista de versões mais recentes naquele dia. Isso significa que a regra pode não bloquear o tráfego como esperado até que uma versão se qualifique.

</Accordion>

<Accordion title="Como bloquear a atribuição de instalações ou eventos in-app a partir de impressões?">

Use uma regra de validação quando quiser impedir a atribuição de engajamentos baseados em impressões e manter a atribuição apenas para cliques válidos. Se nenhum canal de mídia tiver cliques válidos, a instalação será atribuída como orgânica. Essa configuração pode ajudar a solucionar cenários de atribuição relacionados ao hijacking de instalação.

Para configurar a regra:

* Em **Fontes de tráfego**, selecione **Todo o tráfego não orgânico.**
* Em **Condições**, selecione **Tipo de toque de atribuição**.
  * Defina o operador como **Na lista**.
  * Selecione **Impressão**.
* Em **Ação**, selecione **Bloquear atribuição e corrigi-la para o último canal de mídia válido**.

Não selecione **Marcar instalações como inválidas e não as atribua** para este caso de uso. Essa ação destina-se a instalações que você considera inválidas ou falsas. Se a instalação for real, mas você não quiser atribuí-la ao engajamento baseado em impressões, use **Bloquear atribuição e corrigir para último canal de mídia válido**.

</Accordion>

<Accordion title="O modo tagged é compatível com todos os tipos de condição?">

Sim. O modo tagged é compatível com todos os operadores e campos da regra de validação, incluindo lógica e/ou, geolocalização, versão do SO, versão do SDK e valor do evento.

</Accordion>

<Accordion title="Os dados com tags aparecerão em relatórios bloqueados?">

Não. Os dados com tags não são classificados como tráfego bloqueado. O tráfego com tags faz o mapeamento como "tagged" e é considerado um subconjunto de tráfego válido. Eles estão visíveis em relatórios válidos no Data Locker.

</Accordion>

<Accordion title="Onde posso visualizar os dados com tags?">

Use o Data Locker para visualizar os dados da regra de validação com tags. As instalações com tags estão disponíveis no relatório de instalações e os eventos in-app com tags estão disponíveis no relatório de eventos in-app.

Os dados com tags não estão visíveis no dashboard do Protect360 nem na ferramenta de proteção contra fraudes.

</Accordion>

<Accordion title="Posso alterar uma regra de 'tagged' para 'implemented' quando quiser?">

Sim. Depois de analisar os dados de exportação e confirmar se a regra está funcionando conforme o esperado, edite-a, defina o status de detecção como "implemented" e salve-a. A partir desse momento, a regra bloqueia o tráfego correspondente de acordo com o resultado da regra selecionada. A partir desse momento, a regra bloqueia o tráfego correspondente de acordo com o resultado da regra selecionada.

</Accordion>

<Accordion title="Há um limite para quantas regras podem ser definidas como 'tagged'?">

O modo tagged está disponível para clientes premium. Não há um limite obrigatório para o número de regras que podem ser definidas como "tagged". Como recomendação, revise as regras de "tagged" e altere-as para "implemented" após validar a precisão das regras.

</Accordion>

<Accordion title="Características e limitações">

| Caraterística | Descrição |
| --- | --- |
| Acesso do usuário à conta | As ad networks e agências só poderão visualizar os dados se o anunciante lhes der as <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#protect360-fraud-and-validation-rules">permissões necessárias.</Anchor> |
| Aquisição de usuários | As regras de validação se aplicam a instalações, reinstalações e reatribuições (quando o aplicativo foi removido do dispositivo). Elas não se aplicam a casos de reengajamento, ou seja, quando o aplicativo ainda está no dispositivo. |
| Desativação automática das regras | Se você criar regras:<ul><li>usando fontes ou condições do Protect360 e, em seguida, sua licença ou período de avaliação do Protect360 expirar, as regras são automaticamente desativadas.</li></ul> |
| Redes de anúncios | Solicite permissão do anunciante para **visualizar regras de validação** e ver detalhes das regras. **Atenção:** os nomes das regras sempre são exibidos (inclusive nos dados brutos).<br /><br /><Anchor target="_blank" href="/partners/pt/docs/validation-rules-for-ad-networks-and-agencies">Saiba mais sobre as regras de validação para ad networks</Anchor> |
| Agências | Solicite a permissão do anunciante para:<ul><li>**Ver as regras de validação** e ver os detalhes das regras. **Atenção:** os nomes das regras sempre são exibidos (inclusive nos dados brutos).</li><li>**Adicionar regras de validação** para adicionar e editar regras. **Atenção:** As agências não podem editar regras criadas pelos anunciantes.</li><li>**Acesse o dashboard do Protect360 e dados brutos** para visualizar e adicionar regras com as condições do Protect360.</li></ul><Anchor target="_blank" href="/partners/pt/docs/validation-rules-for-ad-networks-and-agencies">Saiba mais sobre as regras de validação para agências</Anchor> |
| Usuários únicos | Se você tiver mais de 100 eventos in-app configurados, mesmo que use regras de validação para invalidar determinados eventos in-app, a <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#limitations">limitação para contagem de usuários únicos</Anchor> ainda se aplica. Significa que eventos acima de 100 não contam com usuários únicos, mesmo que sejam invalidados pelas regras de validação. |
| SKAN | Não suportado |
| Aleatório | A condição de **Engagement** oferece suporte ao bloqueio apenas dos tipos de engajamento **click\_to\_app** e **view**. Outros tipos de engajamento não são suportados. |

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H8VFA2ADGT4AMC0NGDFXRB6Z=vis%C3%A3o-geral rule-builder=criador-de-regras 01H8VFA2ADQVCR8RYV9SBG52R7=criador-de-regras use-categorized-dimensions=usar-dimens%C3%B5es-categorizadas h_01KTHT74EKM95D26AJJNCFG0XZ=usar-dimens%C3%B5es-categorizadas h_01JK5G66CM9TCDK6GATNZC4QMW=aten%C3%A7%C3%A3o-2 validation-rule-examples=exemplos-de-regras-de-valida%C3%A7%C3%A3o h_01KQER0NTPGGC7RYVBGKTZP02S=exemplos-de-regras-de-valida%C3%A7%C3%A3o bulk-upload=upload-em-massa h_01J4HRXAH6DEXXQZZ3YAWHY4TP=upload-em-massa h_01M22JGTYB4YJXBRVWB8RDBK86=aten%C3%A7%C3%A3o h_01JWX0RVRCNAQ0SVRDMAJ5HPW1=aten%C3%A7%C3%A3o-1 procedures=recursos-adicionais 01H8VFA2AF6M84FKKVDTCXJEFR=recursos-adicionais h_01JK5GDDGAZRKBVXZCCZ0RRB56=aten%C3%A7%C3%A3o-2 how-tagged-mode-works=como-funciona-o-modo-tagged h_01KQERXDE5SPB182AFA2CM2C78=como-funciona-o-modo-tagged rule-outcome-configuration=configura%C3%A7%C3%A3o-dos-resultados-da-regra h_01KQERXDE6668BR0EFDX9F5CYZ=configura%C3%A7%C3%A3o-dos-resultados-da-regra what-to-expect-when-configuring-a-rule=o-que-acontece-ao-configurar-uma-regra h_01KQERXDE9AM8TWAAQK6XHETSA=o-que-acontece-ao-configurar-uma-regra example-match-logic=exemplo-l%C3%B3gica-de-correspond%C3%AAncia h_01KQERXDEAQHC3SVFRT8V5X5S3=exemplo-l%C3%B3gica-de-correspond%C3%AAncia example-do-not-match-logic=exemplo-n%C3%A3o-correspondem-%C3%A0-l%C3%B3gica h_01KQERXDEA63J9ST9YSF27JKRD=exemplo-n%C3%A3o-correspondem-%C3%A0-l%C3%B3gica set-a-rule-to-tagged-mode=definir-uma-regra-como-modo-tagged h_01KQERXDEBEKF59KBVYTBWS471=definir-uma-regra-como-modo-tagged analyze-tagged-data=analise-dados-com-tags h_01KQERXDEC1574K0V677N6ZGSY=analise-dados-com-tags change-a-tagged-rule-to-implemented=alterar-uma-regra-de-tagged-para-implemented h_01KQERXDEG3ZQPEYTSXAMMJNYC=alterar-uma-regra-de-tagged-para-implemented faq=perguntas-frequentes 01H8VFA2AG5DW5Z9G9FPSWM464=perguntas-frequentes h_01KHRB9CBYYPK73K7SVC3N4B6A=exemplo-not-in-last h_01KHRB9CC3BBTC41SXC482S7EY=exemplo-not-in-last-major h_01KHRB9CC6GJDNH97N0GSHDNKE=entenda-como-a-condi%C3%A7%C3%A3o-funciona-com-v%C3%A1rios-aplicativos h_01M6BACJ5QD39N6V4G455EFA96=como-a-appsflyer-determina-a-vers%C3%A3o-mais-recente h_01M6BACJ5QAZZNGT5MMGB9Q8WY=exemplo-c%C3%A1lculo-da-vers%C3%A3o-mais-recente" />

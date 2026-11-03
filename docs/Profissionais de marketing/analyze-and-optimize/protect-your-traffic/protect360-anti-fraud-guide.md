---
title: Guia antifraude Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - p360
    - p 360
    - 360protect
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2016-12-06T07:47:17Z'
  edited_at: '2026-08-19T00:07:43Z'
  id: 218254203
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/218254203
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** a atribuição fraudulenta drena orçamentos de marketing, poluindo dados de performance de marketing e transformando campanhas bem-sucedidas em fracassos. **O Protect360 oferece aos proprietários de aplicativos proteção contra fraudes em tempo real e detecção pós-atribuição.** Etapa 1:

![p360intro2.jpg](https://files.readme.io/c8476382eeff62164ca93b9bf2f3c4cdbe0609d4160047eac36a44d5f333ffdb-360014803578.jpg)

## Visão geral do Protect360

* Protege contra fraudes de atribuição. Consiste em ferramentas dinâmicas que detectam fraudes e bloqueiam atribuições fraudulentas.
* Usa escala, machine learning e análise comportamental da AppsFlyer para oferecer cobertura contra métodos novos e conhecidos de clique/instalação, incluindo bots e anomalias comportamentais.
* Protege os profissionais de marketing contra fraudes nos níveis do dispositivo, do editor e da fonte de mídia.
* Usa uma abordagem em camadas de bloqueio de fraudes em tempo real e identificação de fraude pós-atribuição
* Não afeta a experiência do usuário do aplicativo. Em caso de tentativas de fraude envolvendo usuários reais, as instalações do aplicativo são concluídas normalmente e somente a gravação de atribuição é afetada.

<div id="realtime-blocking" />

<Accordion title="Bloqueio em tempo real">

* Em tempo real, antes da atribuição, a instalação é identificada como proveniente de uma fonte de mídia fraudulenta e é bloqueada da atribuição.
* Eventos in-app posteriores do mesmo usuário são bloqueados.
* Instalações bloqueadas e eventos in-app são reportados no dashboard do Protect360 e relatórios de fraude bloqueados.
  * Instalações bloqueadas e eventos in-app: Não estão incluídos na atribuição e nos dashboards da AppsFlyer, pois nunca foram atribuídos.
* Os postbacks de instalação bloqueados são enviados com o motivo do bloqueio para as fontes de mídia, permitindo que elas façam as otimizações necessárias.

<Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">Sobre eventos bloqueados</Anchor>

</Accordion>

<div id="postattribution-detection" />

<Accordion title="Detecção pós-atribuição">

* A fraude identificada após a atribuição é referida como fraude pós-atribuição. A fraude pós-atribuição pode ser identificada no dia da instalação e até 7 dias depois (8 dias no total).
* Uma vez atribuída, uma instalação não pode ser apagada. Por esta razão, a fraude pós-atribuição é tratada de forma diferente da fraude em tempo real.
* Instalações fraudulentas e eventos in-app identificados retrospectivamente devem ser tratados como fraude real e não cobrados.

Assim que uma fonte, como uma ad network ou uma ID de site, for identificada como fraudulenta:

* Cliques futuros da fonte são bloqueados.
* Instalações anteriores:
  * Desde o início do mês corrente até o dia de hoje, são rotuladas como fraude pós-atribuição mas **não são excluídas dos dados**. A partir de janeiro de 2020, as faturas do anunciante são creditadas pelas taxas de atribuição dessas instalações.
  * Antes do início do mês vigente, não são alterados.
* Eventos in-app que ocorrem:

  * **Até** a rotulagem da instalação: rotulados como fraude.
  * **Após** a rotulagem da instalação: rotulados como fraude.

  Atenção: Para reinstalações identificadas como fraudulentas, o Protect360 corrige a atribuição, reatribuindo a instalação a uma fonte orgânica. Consequentemente, quaisquer eventos subsequentes no aplicativo são atribuídos com orgânicos e aparecem nos relatórios de eventos in-app orgânicos.

Exemplos de fraude pós-atribuição:

* Instalações aparentemente normais seguidas de indícios fraudulentos em eventos in-app
* Uma nova forma de fraude encontrada
* Instalações que se mostram fraudulentas somente depois que algoritmos de detecção de anomalias coletam dados estatísticos suficientes sobre as instalações de qualquer editor

</Accordion>

<div id="common-fraud-issues-and-solutions" />

<Accordion title="Problemas comuns relacionados a fraudes e soluções">

Quando a AppsFlyer identifica a fraude, **o evento** **de atribuição** associado à fraude é bloqueado. Isso elimina os ganhos e reduz a motivação dos fraudadores. **Atenção:** a instalação do aplicativo em si ocorre e não é bloqueada. Isso significa que o usuário do aplicativo pode usá-lo e gerar receita para o anunciante.

Cliques fraudulentos, instalações e eventos in-app bloqueados encontram-se nos <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">relatórios de dados brutos de fraude do Protect360</Anchor>.

A tabela a seguir descreve alguns tipos de fraude e como o Protect360 lida com eles.

| Tipo de fraude | Descrição | Solução da AppsFlyer |
| --- | --- | --- |
| <span id="device-id-reset-fraud"></span>**Fraude de reinicialização de ID de dispositivos** | A ID do dispositivo é constantemente redefinida pelo fraudador no mesmo dispositivo físico, de modo a gerar  um grande número de instalações. | A AppsFlyer identifica taxas anormais de novos dispositivos e, consequentemente, adiciona as fontes fraudadoras a uma lista de exclusão. |
| <span id="install-hijacking"></span>**Hijacking de instalações** | Os fraudadores implantam malwares em dispositivos móveis que alertam quando ocorre o download de um aplicativo. Instantaneamente, um clique é enviado para a AppsFlyer reivindicando crédito pela instalação. | Bloqueia cliques atribuídos com um CTIT (<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-to-install-time-ctit/">Tempo do clique à instalação</Anchor>) muito pequeno e com base na Google Play Server-Side API. |
| <span id="click-hijacking"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-hijacking/">**Hijacking de cliques**</Anchor> | O malware identifica um clique no link de atribuição da instalação e envia instantaneamente outro clique que o credita caso seja atribuído. | Bloqueia os cliques atribuídos que ocorrem muito rapidamente após outros cliques para o mesmo aplicativo no mesmo dispositivo. |
| <span id="click-flooding"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-flooding/">**Flooding de cliques**</Anchor> | Fraude móvel que envia um grande número de cliques fraudulentos com a finalidade de gerar o último clique antes da instalação. | Bloqueia cliques atribuídos de IDs de sites com uma baixa taxa de conversão e CTIT longo. |
| <span id="behavioral-anomalies"></span>**Anomalias comportamentais** | Fraude móvel, onde o fraudador gera uma atividade pós-instalação inconsistente e anormal. | Nossa escala única permite acompanhar e entender os padrões comportamentais de engajamento em vários níveis, por exemplo, por aplicativo, região, fonte de mídia e editor. Os padrões comportamentais não humanos são identificados quase em tempo real e bloqueados na fonte. |
| <span id="ip-denylists"></span>**Denylists de IP** | Geralmente, os fraudadores operam em <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-farms/">fazendas de cliques</Anchor>, que podem ser identificadas por seus endereços IP por longos períodos de tempo. | <ul><li>Endereços IP suspeitos de fraude são adicionados diariamente à lista de exclusão com base nos dados atualizados recebidos do provedor global terceirizado <Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element.</Anchor></li><li>A proteção de denylists de IP está habilitada para todos os aplicativos.</li></ul> |
| <span id="sdk-authentication"></span>**Autenticação do SDK** | Os fraudadores enviam mensagens SDK falsas para simular ações importantes do usuário. | <ul><li>Um protocolo de hash proprietário é usado para criptografar mensagens entre SDKs e serviços da web, impedindo que os fraudadores imitem as mensagens.</li><li>A proteção de autenticação do SDK está habilitada para todos os aplicativos.</li></ul> |
| <span id="store-validations"></span>**Validações das lojas** | Fraudadores enviam mensagens de SDK falsas para simular instalações ou compras in-app e reivindicar altas taxas de custo por aquisição. <Anchor target="_blank" href="/marketers/pt/docs/implement-apple-app-store-itunes-install-validation">Validações de lojas da Apple</Anchor>. | Permite <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/install-validation/">a validação da instalação</Anchor> no iTunes e a validação de compras in-app para o iTunes e o Google Play de qualquer instalação ou compra in-app que tenha ocorrido, para evitar a atribuição de atividades fraudulentas. |

**Atenção:** os valores de tempo preciso citados acima são retidos para proteger nossos clientes.

Motivos adicionais de bloqueio são explicados no <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">artigo sobre dados brutos</Anchor>.

</Accordion>

A tabela abaixo descreve os vários tipos de instalações fraudulentas e eventos in-app, e o que acontece quando o mecanismo Protect360 as bloqueia em tempo real, ou as detecta pós-atribuição.

<table><thead><tr><th>Tipo de fraude</th><th>Hora da detecção</th><th>O que acontece com a instalação</th><th>O que acontece com o evento in-app</th></tr></thead><tbody><tr><td rowspan="2"><span>Instalação falsa</span></td><td><span>Em tempo real</span></td><td><span>Bloqueado em tempo real</span></td><td><span>Bloqueado em tempo real</span></td></tr><tr><td><span>Pós-atribuição</span></td><td><span>Sinalizado no relatório de instalações pós-atribuição</span></td><td><ul><li><span>Os eventos in-app que ocorreram antes da detecção de fraude serão sinalizados no relatório de eventos in-app pós-atribuição.</span></li><li><span>Após a detecção: bloqueado em tempo real</span></li></ul></td></tr><tr><td rowspan="2"><span>Hijacking de atribuição de instalação</span></td><td><span>Em tempo real</span></td><td><ul><li><span>Bloqueado em tempo real</span></li><li><span>A atribuição é corrigida para a última fonte válida</span></li></ul></td><td><ul><li><span>Não é mostrado em relatórios brutos e é visível apenas no dashboard</span></li><li><span>Atribuído à mesma fonte válida como a instalação</span></li></ul></td></tr><tr><td><span>Pós-atribuição</span></td><td><span>Sinalizado no relatório de instalações pós-atribuição</span></td><td><ul><li><span>Os eventos in-app que ocorreram antes da detecção de fraude serão sinalizados no relatório de eventos in-app pós-atribuição.</span></li><li><p>Após a detecção de fraude: sinalizada no relatório de eventos in-app pós-atribuição até 30 dias a partir da instalação.\*</p><p>\*Os eventos in-app são corrigidos para a última fonte de mídia válida por 30 dias a partir da instalação. Eventos ocorridos após 30 dias não são corrigidos.</p></li></ul></td></tr><tr><td rowspan="2"><span>Evento in-app fraudulento</span></td><td><span>Em tempo real</span></td><td>-</td><td><span>Bloqueado em tempo real</span></td></tr><tr><td><span>Pós-atribuição</span></td><td>-</td><td><span>Sinalizado no relatório de eventos in-app pós-atribuição</span></td></tr></tbody></table>

Detecção e resultados de fraude do Protect360

## Utilizando o Protect360

<div id="dashboard" />

<Accordion title="Painel">

O <Anchor target="_blank" href="/marketers/pt/docs/protect360-dashboard">dashboard do Protect360</Anchor> exibe dados agregados de fraude e oferece informações relacionadas ao tráfego fraudulento.

Visualizações do dashboard:

**Instalações**: insights <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">baseados em LTV</Anchor> sobre instalações fraudulentas bloqueadas em tempo real e instalações pós-atribuição identificadas. Você pode detalhar para examinar mais profundamente os eventos de fraude usando as opções de filtragem e agrupamento.

**Eventos in-app**: insights <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">baseados em atividades</Anchor> sobre eventos fraudulentos no aplicativo bloqueados em tempo real e eventos pós-atribuição identificados. Você pode detalhar para examinar mais profundamente os eventos de fraude usando as opções de filtragem e agrupamento.

</Accordion>

<div id="raw-data" />

<Accordion title="Dados brutos">

Os <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">dados brutos</Anchor> sobre fraudes estão disponíveis através da Pull API, dos Dados de exportação e do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker (um recurso premium)</Anchor>.

Os relatórios de dados brutos são divididos da seguinte forma:

* Relatórios de bloqueio: instalações, cliques e eventos in-app de usuários cuja atribuição foi bloqueada e não atribuída a nenhuma fonte de mídia.
* Relatórios pós-atribuição:
  * Instalações atribuídas a uma fonte de mídia, mas posteriormente encontradas como fraudulentas.
  * Eventos na Aplicação:
    * de instalações identificadas como fraude após serem atribuídas a uma fonte de mídia.
    * julgados fraudulentos, sem levar em conta a instalação em si.

* Os anunciantes usam esses relatórios para reconciliar contas de ad networks, otimizar e ajustar painéis de atribuição para fraudes pós-atribuição.

</Accordion>

<div id="validation-rules" />

<Accordion title="Regras de validação">

<Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud">Regras de Validação</Anchor> permitem que os proprietários do aplicativo definam condições para bloquear determinadas instalações, atribuições (e garantir que as instalações sejam atribuídas à fonte de mídia válida mais recente) ou eventos in-app.

</Accordion>

<div id="fraud-reconciliation-with-ad-networks" />

<Accordion title="Reconciliação de fraudes com ad networks">

Com o Protect360, os anunciantes obtêm dados brutos sobre instalações fraudulentas e eventos in-app com ad networks que podem não ter sido registrados como fraudes.

Se você descobrir que uma ad network está enviando tráfego de fontes suspeitas, notifique-a e peça que pare de enviar tráfego dessas fontes suspeitas. Use a coluna de relatório de instalações de dados brutos chamada **Tempo de Toque Atribuído** para verificar se nenhuma outra instalação é recebida da fonte após a solicitação de interrupção.

Você também pode usar os dados do Protect360 para fazer a reconciliação de ad networks e receber reembolsos completos ou parciais de tráfego passado de fontes suspeitas.

**Para reconciliar campanhas baseadas em CPI usando o Protect360:**

* No início de cada mês, entre em contato com o gerente da conta em cada ad network que sofreu fraude.
* Colete os dados brutos relevantes de instalações fraudulentas dos relatórios de instalações bloqueadas e [pós-atribuição](/docs/protect360-anti-fraud-guide#postattribution-detection).
* Compartilhe os dados brutos das fraudes com a rede para reconciliação e otimização do tráfego.
* É possível criar um relatório de dados brutos que inclui apenas as instalações válidas, mas exclui as instalações fraudulentas pós-atribuição. Para fazer isso, você precisa baixar o relatório mensal de ***instalações de UA atribuídas*** e excluir todas as entradas do relatório de ***instalações pós-atribuição***.

**Para reconciliar campanhas baseadas em CPA/CPE usando o Protect360:**

* No início de cada mês, entre em contato com o gerente da conta em cada ad network que sofreu fraude.
* Colete os dados brutos relevantes de eventos in-app fraudulentos dos relatórios de Eventos in-app bloqueados e [Eventos in-app pós-atribuição](/docs/protect360-anti-fraud-guide#postattribution-detection).
* Compartilhe os dados brutos das fraudes com a rede para reconciliação e otimização do tráfego.
* É possível criar um relatório de dados brutos que inclui apenas os eventos in-app válidos, mas exclui eventos fraudulentos pós-atribuição. Para fazer isso, você precisa baixar o relatório mensal ***eventos in-app atribuídos após UA*** e excluir todas as entradas do relatório ***eventos in-app pós-atribuição***.

</Accordion>

## Características e Limitações

<div id="traits-and-limitations::a07033c3" />

<Accordion title="Características e Limitações">

| Caraterística | Observações |
| --- | --- |
| Acesso do anunciante | Todos os usuários da conta. |
| Acesso à rede de anúncios | <ul><li>O dashboard do Protect360 e o acesso a dados brutos exigem a <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-ad-network">permissão do anunciante</Anchor>.</li><li>O anunciante deve ter a ad network como um parceiro integrado.</li></ul> |
| Acesso de agência | O dashboard do Protect360 e o acesso a dados brutos exigem a <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-ad-network">permissão do anunciante</Anchor>. |
| Transparência das agências | Agência transparente: pode acessar fontes de mídia específicas<br /><br />Agências não transparentes: não acessam fontes de mídia específicas |
| Fuso horário específico do aplicativo | <ul><li>O fuso horário específico do aplicativo é usado no dashboard se todos os aplicativos estiverem configurados para o mesmo fuso horário.</li><li>Se os aplicativos não estiverem definidos para o mesmo fuso horário, o dashboard usa UTC como padrão.</li></ul> |
| Atualização dos dados | <ul><li>Dashboard do Protect360: <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#eod">atualizado diariamente.</Anchor><br />O horário da atualização mais recente é exibido abaixo do filtro de intervalo de datas no dashboard.</li><li>Relatórios:<ul><li>Instalações bloqueadas e eventos in-app: atualização contínua, praticamente em tempo real.</li><li>Pós-atribuição: <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#eod">diariamente</Anchor> usando UTC.</li></ul></li></ul> |
| Reinstalações | Os dados de fraude para reinstalações só estão disponíveis em dados brutos. Portanto, pode haver discrepâncias entre os números gerais no dashboard e os relatórios de dados brutos. |
| Redirecionamento | <ul><li>Para as instalações identificadas como fraude, é mostrada a divisão por toque atribuída entre instalações, reatribuições e reengajamentos.</li><li>Para eventos in-app:<ul><li>O dashboard de eventos in-app (CPA) exibe eventos fraudulentos de instalação da UA, mas não do retargeting.</li><li>Eventos fraudulentos de reatribuições que são identificados em tempo real podem ser vistos em relatórios de dados brutos. Não é possível identificar eventos fraudulentos de reengajamento.</li><li>Eventos fraudulentos de retargeting não podem ser identificados após a atribuição.</li></ul></li></ul> |
| Limitações | <ul><li>Tabelas limitadas a um máximo de 20.000 linhas.</li><li>Se você consultar um conjunto de dados maior, algumas fontes de mídia poderão ser excluídas. Para superar essa limitação, recomendamos o seguinte:<ul><li>Consulte um conjunto de dados menor - intervalo de datas menor, aplicativos específicos e fontes de mídia específicas</li><li>Exportar <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">relatórios de dados brutos</Anchor> do Protect360</li><li>Exportar relatórios agregados de detecção avançada do Protect360 <Anchor target="_blank" href="/marketers/pt/docs/pull-api-aggregate-data">através da Pull API</Anchor></li></ul></li></ul> |

Características e Limitações

</Accordion>

## Perguntas frequentes e dicas

<div id="faq" />

<Accordion title="Perguntas frequentes">

| **O Protect360 funciona contra fraudes provenientes de links de atribuição personalizados?**<br /><br />Sim! O Protect360 detecta e bloqueia fraudes provenientes de links de atribuição personalizados, além de ad networks. Isso significa que você também estará protegido se tiver campanhas de mídia de propriedade, como influenciadores, campanhas de e-mail e SMS, banners e páginas de destino de sites, postagens virais nas mídias sociais, notificações push ou até códigos QR. |
| --- |
| **O que há de novo no Protect360 V2 em comparação com o V1?**<ol><li>Lançamos 3 novidades principais no P360 V2.0:<br />Fraude pós-atribuição - apresentamos instalações bloqueadas e também mostramos instalações de fraude pós-atribuição. A pós-atribuição também está disponível em formato de relatório de dados brutos.</li><li>Insights de anomalias - adicionamos uma nova seção chamada "Insights de anomalias", onde os anunciantes podem analisar anomalias através de ferramentas de visualização. Ela está substituindo os 2 gráficos na antiga guia "Detecção avançada".</li><li>Centralização de todos os dados relacionados a fraudes - removemos a guia "Detecção avançada" e, em vez disso, apresentamos todas as informações em 1 guia.</li></ol> |
| **Por que os dados brutos de pós-atribuição não estão disponíveis na página Exportar dados?**<br /><br />Os relatórios pós-atribuição estão disponíveis no nível da conta por fonte de mídia para facilitar o processo de reconciliação. A página **Exportar dados** está no nível do aplicativo único e ainda contém os dados de fraudes bloqueadas no nível do aplicativo, para compatibilidade com versões anteriores. |
| **Os dados pós-atribuição são atualizados retroativamente?**<ul><li>**Instalações** - os dados de instalação na página de visão geral e todos os outros relatórios fora do dashboard do Protect360 não são atualizados retroativamente.</li><li>**Eventos in-app** - depois que a camada de proteção pós-atribuição identifica uma instalação como falsa, os eventos subsequentes provenientes dessa instalação serão bloqueados. Eventos in-app anteriores não são atualizados retroativamente.</li></ul> |
| **Por que os dados parecem diferentes ao selecionar redes específicas/diferentes no Anomaly Insights?**<br /><br />Quando você olha para as anomalias de CTIT e seleciona AF\_Baseline como referência, você pode ver anomalias da Rede A. Em seguida, se, por exemplo, você selecionar a Rede A como benchmark, verá anomalias de outras redes, mas não Rede A. Em seguida, se, por exemplo, você selecionar a Rede A como benchmark, verá anomalias de outras redes, mas não Rede A. Em seguida, se, por exemplo, você selecionar a Rede A como benchmark, verá anomalias de outras redes, mas não Rede A.<br /><br />Esse resultado é o esperado. Quando a linha de base de confiança da AppsFlyer é usada, as redes com taxas anormais de CTIT são exibidas. Quando a rede anômala é usada como linha de base, suas instalações não são mais incluídas como anomalias, mas as instalações de outras redes podem ser consideradas anômalas em relação a ela. |
| **O tráfego orgânico anormal é realmente fraudulento?**<br /><br />É possível que picos anormais no tráfego orgânico sejam realmente fraudulentos. Em geral, se você vir tráfego orgânico na AppsFlyer que você tem motivos para acreditar que seja realmente fraudulento, pode ser um dos três casos a seguir:<ul><li>**Falha na fraude de atribuição:** os cliques do fraudador não foram atribuição. Por exemplo, no flooding de cliques, o último clique ocorreu para além da janela de lookback.</li><li>**Fraude sem atribuição:** o usuário faz uma fraude que não está relacionada à atribuição, por exemplo, usando métodos fraudulentos para coletar itens em jogos de estratégia.</li><li>**Problemas de integração do SDK:** verifique se os eventos no aplicativo foram enviados corretamente, ou seja, no momento certo do fluxo e com os valores corretos dos parâmetros do evento.</li></ul> |

Perguntas frequentes

</Accordion>

<div id="benchmarks-and-tips" />

<Accordion title="Comparativos e dicas">

| **Detectar fraudes em novos dispositivos**<br /><br />Os fraudadores podem mascarar seus dispositivos, redefinindo frequentemente as principais IDs de seus dispositivos, ou seja, IDFA para iOS e GAID para Android.<br /><br />Felizmente, a AppsFlyer identifica mais de 98% dos dispositivos mobile em todo o mundo.<br /><br />Portanto, uma alta porcentagem de dispositivos novos e desconhecidos é um forte indício de fraude por fazendas de cliques, a menos que os novos dispositivos sejam intencionalmente direcionados.<br /><br />**Detectar novos dispositivos:**<ol><li>No Protect360, acesse a tabela  de ***análise de fraudes identificadas***.</li><li>Deslize para a direita até as colunas ***Indicadores de device farm - novos dispositivos***.</li><li>Clique no nome da coluna ***% Instalações*** para classificar a tabela em ordem decrescente de acordo com a proporção de novos dispositivos.</li><li>Indicadores de fraude de novos dispositivos:</li></ol><ul><li>Fontes com uma alta porcentagem de**novos** dispositivos. **Atenção:** à medida que o número de instalações aumenta, porcentagens mais baixas também podem ser consideradas fraude (já que a quantidade total é grande).<ul><li>Quando a relação de usuário fidelizado da fonte é comparada com a relação geral de usuários fidelizados, uma porcentagem relativamente baixa é uma forte indicação de fraude.</li></ul></li></ul>**Atenção:** As campanhas de <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-factory-preinstall-using-manifest-android">aplicativos pré-instalados</Anchor> geralmente apresentam taxas extremamente altas de novos dispositivos, pois podem estar entre os primeiros aplicativos que os usuários iniciam ao ativar seus novos dispositivos. Portanto, para aplicativos pré-instalados, é improvável a fraude de novos dispositivos, mesmo com altas taxas de novos dispositivos. |
| --- |
| **Detectar fraude no LAT**<br /><br />Usuários LAT (Limited Ad Tracking) optam por não expor o ID, IDFA ou GAID de seus dispositivos aos anunciantes. Aproximadamente 15% dos usuários do iOS e 10% dos usuários do Android fazem essa escolha.<br /><br />Da mesma forma que a nova classificação de dispositivos, os usuários LAT podem ser legítimos. No entanto, uma alta porcentagem deles pode indicar atividade fraudulenta.<br /><br />**Detectar o LAT:**<ol><li>No Protect360, acesse a tabela  de ***análise de fraudes identificadas***.</li><li>Role para a direita para os ***indicadores de device farm -  colunas de dispositivos LAT***.</li><li>Clique na coluna ***Installs %*** para classificar a tabela em ordem decrescente de taxa de dispositivos LAT.</li><li>Indicadores de fraude de dispositivos LAT:</li></ol><ul><li>Fontes com uma alta porcentagem de dispositivos **LAT**. **Atenção:** à medida que o número de instalações aumenta, porcentagens mais baixas também podem ser consideradas fraude (já que a quantidade total é grande).</li><li>Quando a relação de usuário fidelizado da fonte é comparada com a relação geral de usuários fidelizados, uma porcentagem relativamente baixa é uma forte indicação de fraude.</li></ul> |
| **Detectar fraude de flooding de cliques**<ol><li>Usando o flooding de cliques, os fraudadores enviam milhões de cliques com device IDs reais, com o objetivo de se registrar como o último clique para usuários reais. As fontes com esse tipo de fraude possuem **taxas de conversão muito baixas, mas usuários de alta qualidade**, pois são usuários reais.</li></ol>**Como detectar flooding de cliques:**<ol><li>No Protect360, acesse a tabela  de ***análise de fraudes identificadas***.</li><li>Role para a direita até as colunas ***Indicadores de flooding de cliques***.</li><li>Clique na coluna ***Taxa de conversão*** para classificar a tabela em ordem crescente de taxa de conversão.</li><li>Comparativos de flooding de cliques:</li></ol><ul><li>As ***taxas de conversão*** normais estão entre 0,5% a 35%.<br />Suspeite de fontes cujas taxas de conversão são estranhamente baixas, ou que **têm 25% ou menos de taxa de conversão média**. Você pode encontrar esse KPI na tabela Relatório de performance agregada na página de Overview do dashboard.</li><li>Para fontes limítrofes, compare a taxa de ***assistências (%)*** com a taxa média de assistências. Você pode ver a taxa normal de assistências no widget de assistências, na página de Overview do dashboard.<br />Fontes cuja proporção de assistências é **50% maior do que a proporção média** de assistências do aplicativo são consideradas suspeitas.<br />Observe que, quanto mais fontes são usadas por um aplicativo, maiores são suas taxas de contribuição.</li></ul> |
| **Detectar flooding de cliques com indicadores CTIT**<br /><br />Outra indicação de flooding de cliques é a **distribuição uniforme de CTIT**.<br />Geralmente, cerca de 70% das instalações normais ocorrem dentro de 1 hora após o engajamento do anúncio.<br />Com o flooding de cliques, não há ligação entre o engajamento falso e a instalação real. Isso leva a muito mais do que 30% das instalações fraudulentas, com mais de 1 hora de CTIT.<br /><br />**Como detectar indicações CTIT de flooding de cliques:**<ol><li>No Protect360, acesse a tabela  de ***análise de fraudes identificadas***.</li><li>Role para a direita até os ***indicadores de flooding de cliques*** ***- colunas CTIT***.</li><li>Comparativos de CTIT de flooding de cliques:</li></ol><ul><li>Normalmente, valores ***acima de 60 minutos*** devem estar em torno de 30%. Suspeite de fontes que tenham mais de 50% com essa métrica.</li><li>Normalmente, valores ***acima de 5 horas*** devem estar em torno de 20%. Suspeite de fontes que tenham mais de 40% com essa métrica.</li></ul>Use a <Anchor target="_blank" href="/marketers/pt/docs/protect360-dashboard#anomalies-dashboard">página</Anchor> ***Insights de anomalia*** para investigar fontes com CTIT suspeito. |

Comparativos e dicas

</Accordion>

<div id="advanced-antifraud-tips" />

<Accordion title="Dicas avançadas antifraude">

| **Número de instalações**<br /><br />A filtragem pelo número de instalações por fonte verificada é importante para detectar as maiores fontes de fraude. Além disso, um número menor de instalações pode não ser matematicamente significativo. Atenção:<br /><br />**Atenção:** Fontes com menos de 30 instalações, ou até mesmo 50, não são significativas o suficiente para tirar conclusões. Expanda o intervalo de datas ou outros critérios de pesquisa para obter resultados mais significativos. |
| --- |
| **Alterar definição de usuário leal**<br /><br />A definição padrão de usuários leais é de 3 ou mais inicializações do aplicativo. É um KPI importante para o engajamento do usuário, mas, infelizmente, muitos fraudadores o conhecem e o usam para falsificar altas taxas de usuários fidelizados, evitando suspeitas. Evite ser enganado ao criar e selecionar uma definição de usuário leal melhor e mais elaborada.<br /><br />Analise os KPIs de qualidade do usuário em seu aplicativo, como cadastro, conclusão de tutorial, compra, várias sessões, etc. No código do aplicativo, envie um novo evento in-app de **usuário fidelizado** se um usuário executar a lista COMPLETA de KPIs. No código do aplicativo, envie um novo evento in-app de **usuário fidelizado** se um usuário realizar TODA a lista de KPIs.<br /><br />Após o envio do primeiro evento não orgânico por um **usuário fidelizado**, acesse as **configurações do aplicativo** e selecione-o para indicar os usuários fidelizados do seu aplicativo. Espere que as taxas gerais de usuários leais caiam levemente e depois caiam drasticamente nas fontes fraudulentas. |

Dicas avançadas antifraude

</Accordion>

> 👍 **Dica**
>
> Quer saber mais sobre proteção contra fraudes? Confira este <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7809/play/18635/mobile-app-fraud-and-protect360">curso curto e informativo</Anchor> no Portal de Aprendizado da AppsFlyer.

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">Dados brutos</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/marketers-guide-mobile-ad-fraud/">Guia introdutório para profissionais de marketing para fraude de anúncios mobile.</Anchor>

<div data-zendesk-anchors="protect360-overview=vis%C3%A3o-geral-do-protect360 h_01HE7RSPPQ4T5J3W038EZRCTCE=vis%C3%A3o-geral-do-protect360 h_01HE7RSPPQ5BH7HBK0R8SY1T16=realtime-blocking h_01HE7RSPPRW4CQ3GB9ZEYAA6YN=postattribution-detection h_01HE7RSPPRYMQKJH46JET2ZZ0T=common-fraud-issues-and-solutions using-protect360=utilizando-o-protect360 h_01HE7RSPPR8Y8J1VJJXXDCAZE6=utilizando-o-protect360 h_01HE7RSPPR04G3SCSYHSWJKQDG=dashboard h_01HE7RSPPRS6PSTZCR5RT4A5ND=raw-data h_01HE7RSPPR8C9MHRAGJXYD2VVZ=validation-rules h_01HE7RSPPR1PQ2R6NJPRQGS1K1=fraud-reconciliation-with-ad-networks traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HE7RSPPRV797PS12NFQHX1X5=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HE7RSPPRWRKR1Y25PZV2RMVV=traits-and-limitations::a07033c3 faq-and-tips=perguntas-frequentes-e-dicas h_01HE7RSPPSV2TT8SMK8JZXFKMC=perguntas-frequentes-e-dicas h_01HE7RSPPS01J796008HDS1CRW=faq h_01HE7RSPPS018W98JWZGED54W8=benchmarks-and-tips h_01HE7RSPPSEDZWRH929DBSWEWM=advanced-antifraud-tips h_01HE7RSPPSY161MSQVQW7M767F=dica h_01HE7RX6167Q5QP5JNZDSXCCK5=veja-tamb%C3%A9m" />

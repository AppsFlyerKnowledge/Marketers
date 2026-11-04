---
title: Guia para a solução SKAdNetwork (SKAN)
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-07-25T21:19:42Z'
  edited_at: '2026-08-19T00:30:48Z'
  id: 360011420698
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/360011420698
---
> **Resumo:** como atribuir instalações de aplicativos usando a SkadNetwork.

![5754](https://files.readme.io/a970d7b0e8da300ded2138f941bf2e891f32d396c8500292534992a4b4449d71-30757780264337.png)

## SKAN

A SKAdNetwork (SKAN), parte do iOS da Apple, ajuda os anunciantes a mensurar a performance da campanha, ao mesmo tempo em que mantém a privacidade do usuário. A SKAN funciona sem o IDFA ou outro ID de anúncio. A SKAN funciona sem a necessidade de consentimento à ATT.

<div id="tip" />

> 👍 **Observação**
>
> * A partir do iOS 15, recomendamos que você envie <Anchor target="_blank" href="/marketers/pt/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">cópias de postback da SKAN</Anchor> para a AppsFlyer. Isso permite que a AppsFlyer verifique se os valores de conversão em postbacks não foram manipulados.
> * Quer saber mais sobre a solução para SKAN da AppsFlyer? Confira este  <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/internal/view/elearning/7810/ios14-and-skadnetwork">curso curto e informativo, disponível no portal de aprendizagem da AppsFlyer</Anchor>.

**Configurações**

* <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">SDK</Anchor>: versão atual do SDK da AppsFlyer para iOS integrada em um aplicativo.
* **Janela de mensuração da SKAN**: relevante para SKAN 4+. Existem 3 períodos de tempo (janelas) durante os quais a atividade pós-instalação do usuário é mensurada:
  * Janela 1: 1-2 dias
  * Janela 2: 3-7 dias
  * Janela 3: 8-35 dias
* **Valor de Conversão (CV)**: a medida da qualidade do usuário relatada nos postbacks enviados pelo iOS no final das janelas de mensuração da SKAN 4 ou, para SKAN 3 e versões anteriores, no final da Janela de Atividade. O SDK da AppsFlyer define os CVs para você. No entanto, se você quiser definir o CV, use a opção <Anchor target="_blank" href="/marketers/pt/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> para carregar o arquivo de mapeamento do CV.
  * Para SKAN 4+, existem valores de conversão totais e parciais.
* **Conversion Studio**: solução da AppsFlyer para mapear valores de conversão (CV) de infraestrutura para eventos
* **Solução:** SDK, Infraestrutura, Conversion Studio e plataforma da AppsFlyer, trabalhando juntas. A solução oferece aos anunciantes e ad networks dados de LTV por meio de análises de dashboard, relatórios e postbacks.
* **Janela de atividade:** relevante para SKAN 3 e versões anteriores. Tem duração definida, padrão de 24 horas, a partir da primeira abertura do app. Se você estiver usando a SKAN 4+, mas os dispositivos do usuário ou as ad networks ainda não oferecem suporte para a SKAN 4, a janela de atividade é de 48 horas.

Este artigo descreve as características relevantes da infraestrutura e da solução. Para configurar a mensuração, consulte <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.

<div id="about-apple-skan" />

<Accordion title="Sobre a SKAN da Apple">

| Características | Descrição |
| --- | --- |
| Pré-requisitos | Para habilitar o uso da SKAN no aplicativo:<ul><li>Aplicativo do anunciante (seu aplicativo), ou seja, o aplicativo que está sendo anunciado implementa o SDK da AppsFlyer para definir o CV. Como alternativa, você pode definir o CV usando o <Anchor target="_blank" href="/marketers/pt/docs/skan-cv-decode-map-your-cv-to-events">modo Decode</Anchor>.</li><li>Aplicativos do publisher (aplicativo exibindo um anúncio): deve <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">configurar um aplicativo de origem</Anchor>.</li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/registering_an_ad_network">As ad networks devem se registrar com a Apple</Anchor></li></ul>**\*Atenção:** Certifique-se de não ter outro SDK que defina valores de conversão em seu aplicativo. |
| Com suporte. | <ul><li>A versão da SKAdNetwork que é compatível depende da versão do iOS:<ul><li>iOS 11-13: V1 (somente instalações sem valores de conversão)</li><li>iOS 14-14.5: V2+ (com valores de conversão)</li><li>iOS 14.6-16: V3 (com valores de conversão)</li><li>iOS 16.1+: V4+ (com valores de conversão para 3 janelas e valores totais e parciais)</li></ul></li><li>Atribuição de aplicativo para aplicativo</li></ul> |
| Limitações | <ul><li>Há suporte para Apple Ads (Search Ads) nas versões 1 a 3 do SKAN. O suporte a view-through e ao SKAN 4 está pendente</li><li>Web mobile não compatível</li><li>Até a SKAN 4, a numeração dos IDs de campanha estava <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skstoreproductparameteradnetworkcampaignidentifier">restrita ao intervalo 1-100</Anchor>; isso significa 100 valores exclusivos por ad network por aplicativo. As ad networks fornecem à AppsFlyer o ID e o nome da campanha. Isso se reflete nos dashboards e relatórios da AppsFlyer.</li><li>A partir da SKAN 4, o source identifier é de 1 a 10.000.</li><li>Instalações orgânicas: a SKAN não é compatível com instalações orgânicas.</li><li>Reengajamento.</li></ul> |
| Princípios de atribuição da SKAN | <ul><li>A SKAN faz a atribuição seguindo o <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">seguinte modelo</Anchor>:<ul><li>O usuário clica em um anúncio, em 30 dias instala (faz download) o aplicativo e, a partir de então, em 60 dias abre o aplicativo pela primeira vez.</li><li>O usuário visualiza um anúncio, em 24 horas instala (faz download) o aplicativo e, posteriormente, em 60 dias, abre o aplicativo pela primeira vez.</li><li>A partir da versão 2.2 da SKAdNetwork, a atribuição de cliques tem prioridade sobre a atribuição de view-through. A versão SKAN depende da versão do iOS.</li><li>O iOS envia postbacks para a ad network atribuída. A partir do iOS 15, os anunciantes podem enviar uma cópia do postback diretamente para a AppsFlyer.</li></ul></li></ul> |
| Crowd anonymity | A Apple envia alguns postbacks com dados limitados para proteger a privacidade do usuário. De acordo com a Apple, o postback não incluirá os CVs totais ou parciais, nem o source app ID ou o identificador completo da origem se isso violar os limites de privacidade da Apple. <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">Saiba mais</Anchor> |

</Accordion>

<div id="appsflyer-skan-solution" />

## Solução para SKAN da AppsFlyer

A AppsFlyer fornece resultados agregados de atribuição do iOS usando postbacks da SKAN. Esses postbacks são enviados pelo iOS para ad networks, que os encaminham para a AppsFlyer. Os postbacks contêm registros de atribuição anônimos enriquecidos com um valor de conversão (CV) definido pelo anunciante. O CV é uma medida da qualidade do usuário durante uma janela inicial de pós-instalação.

A solução da AppsFlyer para SKAN fornece aos anunciantes:

* Dados da SKAN em dashboards e relatórios obtidos a partir da agregação de postbacks de todas as ad networks enriquecidas com outros pontos de dados, como custo.
* A capacidade de controlar, por meio do Conversion Studio, o que o CV mensura sem a necessidade de fazer alterações no código do aplicativo. O CV pode ser usado para mensurar receita, engajamentos ou eventos de conversão.  
  **Atenção:** Apenas o SDK da AppsFlyer deve ter a capacidade de definir valores de conversão. Certifique-se de não ter outro SDK que defina valores de conversão em seu aplicativo.

<div id="principles-and-flow" />

<Accordion title="Princípios e fluxo">

<div id="skan-attribution-flow" />

#### **Fluxo de atribuição da SKAN**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. O anunciante define as configurações de mensuração da SKAN no Conversion Studio da AppsFlyer.
2. O usuário abre o aplicativo pela primeira vez.
3. Durante cada janela, a AppsFlyer define o CV com base nas ações do usuário e no esquema de valores de conversão configurado.
4. Depois que a janela fecha, o iOS envia o postback para a ad network e uma cópia do postback para a AppsFlyer. O postback chega com algum atraso:
   * 1ª janela de mensuração da SKAN 4: 24-48 horas
   * 2ª e 3ª janelas de mensuração da SKAN 4 24-144 horas
   * Para SKAN 3: 24-48 horas após o aumento mais recente no CV.
5. As cópias de postback enviadas diretamente do dispositivo iOS para a AppsFlyer são reencaminhadas para o endpoint definido pelo anunciante. Consulte <Anchor target="_blank" href="/marketers/pt/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">enviar cópias de postback do SKAN para a AppsFlyer.</Anchor>
6. A ad network encaminha um postback enriquecido para a AppsFlyer ou a SRN comunica dados de postback por API.
7. A AppsFlyer valida e descodifica o CV. Os dados descodificados são registados e atribuídos antes de serem disponibilizados na AppsFlyer através de dashboards, relatórios e APIs.

Para superar as limitações funcionais e estruturais da infraestrutura da SKAdNetwork, a solução leva em consideração as características da tabela a seguir.

| Características | Descrição |
| --- | --- |
| <span id="data-collection"></span>Coleta de dados | <ul><li>Para o anunciante, os postbacks de SKAdNetwork são coletados de várias ad networks.</li><li>Os anunciantes não precisam fazer a integração individualmente com cada ad network — uma tarefa complexa e chata.</li></ul> |
| <span id="data-validation"></span>Validação de dados | <ul><li>Garante que os postbacks sejam assinados pela Apple. Isso reduz as chances de manipulação de postbacks.</li><li>Usa o campo transaction ID para validar se os postbacks são exclusivos.</li></ul> |
| <span id="data-enrichment"></span>Enriquecimento de dados | <ul><li>Enriquece os dados de postback de SKAdNetwork com outros pontos de dados para oferecer uma análise completa do ROI. Por exemplo, o nome da campanha fornecido pela ad network e assim por diante.</li><li>Os pontos de dados incluem impressões, cliques, custos, entre outros.</li></ul> |
| <span id="data-delivery"></span>Entrega de dados | Os dados enriquecidos da SKAdNetwork ficam disponíveis da seguinte forma:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Dashboard da solução para SKAdNetwork</Anchor></li><li>[Relatórios para download](/docs/skadnetwork-skan-solution-guide#reporting-options)</li></ul> |
| <span id="seamless-integration"></span>Integração direta | <ul><li>O encapsulamento total permite um esforço quase nulo da parte do anunciante através da página de configurações do aplicativo.</li><li>Não é necessária programação. O aplicativo requer a versão mais recente do SDK.</li><li>Inclui suporte para alterações esperadas a serem feitas pela Apple na infraestrutura SKAdNetwork.</li></ul> |
| <span id="agility"></span>Agilidade | Os anunciantes podem alterar as configurações de mensuração conforme necessário no dashboard. |

</Accordion>

<div id="conversion-studio" />

<Accordion title="Conversion Studio">

O <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">Conversion Studio</Anchor> da AppsFlyer é o centro da nossa solução para SKAN. Ele fornece flexibilidade máxima para fazer com que cada bit de um valor de conversão seja útil. Você determina com precisão quais dados de mensuração devem ser codificados no CV - incluindo qual atividade e por quanto tempo mensurar durante o período pós-instalação. Existem vários modos de mensuração que você pode usar para definir suas configurações de CV.

| Tipo | Modo de mensuração | Descrição | Janela de atividade |
| --- | --- | --- | --- |
| Flexível | SKAN 4.0<br /><br />[Melhores práticas] | Defina uma combinação de mensurações de receita, conversão (eventos in-app) e engajamento durante 3 janelas de mensuração configuráveis. | <ul><li>Janela 1: 1-2 dias</li><li>Janela 2: 3-7 dias</li><li>Janela 3: 8-35 dias</li></ul> |
| Flexível | <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#custom">Personalizado</Anchor> | Defina uma combinação de mensurações de receita, conversão (eventos in-app) e métricas de engajamento durante uma janela de atividade configurável. | 12h-63 dias |
| Fixo | Resultados<br /><br />[Padrão]<br /><br />[Legacy] | Mensure a receita usando um dos seguintes intervalos:<ul><li>$1-$630 em incrementos de $10</li><li>$1-$63 em incrementos de $1</li><li>$0,01-$0,63 em incrementos de $0,01</li></ul> | 24 h |
| Fixo | Conversão<br /><br />[Legacy] | Selecione de 1 a 6 eventos in-app | 24 h |
| Fixo | com o anúncios<br /><br />[Legacy] | Número de vezes que um usuário realiza um evento | 24 h |
| Flexível | <Anchor target="_blank" href="/marketers/pt/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> | <ul><li>Crie o seu próprio mapeamento de eventos para CVs e configure-o manualmente no seu app. Use essa opção se não for possível integrar o SDK da AppsFlyer ao seu aplicativo. Para usar o Decode, vá para o **SKAN Conversion Studio,** clique nas opções (⋮), selecione Enviar arquivo de mapeamento de decodificação personalizado.</li></ul> | 12-1512h (63 dias) |

</Accordion>

<div id="additional-skadnetwork-information" />

## Informações adicionais sobre a SKAdNetwork

<div id="reporting-options" />

<Accordion title="Opções de relatórios">

Os relatórios da SKAdNetwork não contêm identificadores a nível de usuário.

| Nome do relatório | Tipo | Enriquecido pela AppsFlyer | Método de entrega | Funcionalidade premium |
| --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/skan-aggregated-performance-report-api">Relatório de performance agregada da SKAN.</Anchor><br /><br />Agregados de instalação, eventos in-app e receita. Os dados são semelhantes aos encontrados no dashboard da SKAN. | Agregado usando a data de chegada da instalação ou do postback | Sim | API | Não |
| <Anchor target="_blank" href="/marketers/pt/docs/skan-aggregated-postback-arrival-date-api">Relatório de postback agregado da SKAN</Anchor>.<br /><br />Postbacks agregados da SKAN, no nível mais granular possível. | Agregação de postback usando a data de chegada do postback | Não | API | Não |
| <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports#raw-data-report-types">Relatórios de dados brutos da SKAN (a nível de linha) via Data Locker</Anchor> (com exemplos).<br /><br />Relatórios disponíveis:<ul><li>Postbacks enviados pelo iOS com enriquecimento de dados fornecidos por parceiros de ad network</li><li>Instalações</li><li>Re-downloads</li><li>Eventos in-app</li><li>Dimensões de anúncios em SRNs</li></ul> |  | Sim | Relatório do Data Locker | Sim. Dados brutos necessários. A assinatura do Data Locker não é obrigatória. |
| Dados da SKAN via Push API |  | Sim | API de push | Sim |

</Accordion>

<div id="skadnetwork-solution-implementation-checklist" />

<Accordion title="Checklist da implementação da solução para SKAdNetwork">

| Não. | Ação | Descrição | Responsabilidade |
| --- | --- | --- | --- |
| 1 | Preparar | <ul><li>Leia o <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">guia da solução SKAdNetwork</Anchor></li><li>Leitura adicional: <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">Prepare seus aplicativos para o iOS 14</Anchor></li></ul> | Profissional de marketing, desenvolvedor |
| 2 | Configurar | Na AppsFlyer, configure a solução SKAdNetwork no <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>. | Marketer |
| 3 | Preparar o aplicativo | Migre o aplicativo para o <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">SDK V6</Anchor> da AppsFlyer.<ul><li>Nenhuma alteração na lógica do aplicativo ou no código do aplicativo é necessária.</li><li>A solução depende de eventos in-app para definir o CV. Envie eventos in-app da maneira usual. Nenhum teste específico da solução é necessário.</li><li>Enviar o aplicativo para a App Store</li><li>Nenhum cadastro ou processo da SKAdNetwork é necessário na app store.</li></ul> | Desenvolvedor |
| 4 | Integrações com parceiros | Os parceiros de ad networks devem se integrar com a AppsFlyer usando a integração de SKAdNetwork. Atenção! A simulação da SKAdNetwork da AppsFlyer contém os dados de todos os seus parceiros, independentemente do status atual de integração. Esse não será o caso dos live data relatados por postbacks da SKAdNetwork.<br /><br />Em relação aos parceiros que executam suas campanhas, faça o seguinte, conforme necessário:<br /><br />**Não-SRNs**:<ol><li>Verifique se o parceiro tem um <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#c-transaction-id">sinalizador de aptidão da SKAdNetwork</Anchor> da AppsFlyer e se, na interface de usuário do parceiro, o relatório da campanha SKAdNetwork está habilitado.</li><li>Verifique se seus [nomes de eventos in-app estão mapeados](#sending-postbacks-to-integrated-partners) para parceiros de nomes de eventos in-app.</li></ol>**anúncios Meta**:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-interoperation-with-meta-ads">Configurar a interoperação entre a SkadNetwork e a AppsFlyer com o Meta ads</Anchor></li></ul> | Marketer |

</Accordion>

<div id="troubleshooting-guide" />

<Accordion title="Solução de problemas">

| Sintoma | Descrição |
| --- | --- |
| O dashboard não contém instalações não-orgânicas. | <ol><li>Verifique se a **mensuração de SKAdNetwork** está ativa.<ol><li>Acesse **configurações** > **Conversion Studio da SKAN.**</li><li>Clique nas opções (⋮), avalie a configuração de mensuração da SKAN.</li></ol></li><li>Verifique se a versão do seu SDK é 6.2.6+.<ul><li>Para isso, acesse **Integração** > **Informações do SDK > Usuários por versão do SDK.**</li></ul></li><li>Se estiver usando plug-ins do SDK, verifique se você implementou uma versão compatível com o SKAdNetwork da AppsFlyer.</li><li>Verifique se seus parceiros de ad networks estão integrados à AppsFlyer e se eles encaminham postbacks do iOS para a AppsFlyer.</li></ol> |
| O dashboard contém instalações não-orgânicas, mas nenhum evento in-app. | <ol><li>Verifique se a versão do seu SDK é 6.2.6+.<ul><li>Para isso, acesse **Integração** > **Informações do SDK > Usuários por versão do SDK.**</li></ul></li><li>Se estiver usando plug-ins do SDK, verifique se você implementou uma versão compatível com o SKAdNetwork da AppsFlyer.</li><li>Você envia eventos usando S2S? Se sim, verifique se a opção **Gravar eventos dentro da aplicação enviados pela server-to-server API** está ativa.<ol><li>Acesse **configurações** > **Conversion Studio da SKAN.**</li><li>**Clique nas opções (⋮) e confirme se a configuração S2S está ativa.** Atenção: No modo de mensuração Personalizado e Decode, essa configuração está sempre ativa e não pode ser alterada.</li></ol></li></ol> |
| O dashboard contém instalações e alguns eventos in-app. Alguns eventos in-app estão faltando. | <ol><li>Você envia eventos usando S2S? Se sim, verifique se a opção **Gravar eventos dentro da aplicação enviados pela server-to-server API** está ativa.<ol><li>Acesse **configurações** > **Conversion Studio da SKAN.**</li><li>**Clique nas opções (⋮) e confirme se a configuração S2S está ativa.** Atenção: No modo de mensuração Personalizado e Decode, essa configuração está sempre ativa e não pode ser alterada.</li></ol></li><li>Verifique seus <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports#raw-data-report-types">dados brutos de postback</Anchor> para ver se todos os eventos são relatados.</li></ol> |
| As localizações geográficas (países) são confusas | Os dados de geolocalização são obtidos da seguinte forma:<ul><li>De acordo com o país associado a uma campanha e conforme foi relatado à AppsFlyer pela ad network.</li><li>Usando o endereço de IP do dispositivo. A partir do iOS 14.6, esse endereço é um endereço proxy e não representa realmente a geolocalização do usuário.</li></ul> |

</Accordion>

<div id="timing-from-app-install-until-dashboard-and-reports-update" />

<Accordion title="Tempo desde a instalação do aplicativo até a atualização do dashboard e dos relatórios">

| Chave | Nome do elemento | Descrição | Exemplo A | Exemplo B | Exemplo C | Exemplo D | Exemplo E |
| --- | --- | --- | --- | --- | --- | --- | --- |
| E | 1ª janela de mensuração da SKAN 4 | <ul><li>Durante a janela, os CVs são definidos pelo aplicativo</li><li>0-2 dias</li><li>A janela pode ser bloqueada antes de chegar a 2 dias no Conversion Studio</li></ul> | - | - | 2 dias | - | - |
| B | 2ª janela de mensuração da SKAN 4 | <ul><li>Durante a janela, o CV é definido pelo aplicativo</li><li>3-7 dias</li><li>A janela pode ser bloqueada antes de chegar a 7 dias no Conversion Studio</li></ul> | - | - | - | 7 dias | - |
| C | 3ª janela de mensuração da SKAN 4 | <ul><li>Durante a janela, o CV é definido pelo aplicativo</li><li>8-35 dias</li><li>A janela pode ser bloqueada antes de chegar a 35 dias no Conversion Studio</li></ul> | - | - |  | - | 35 dias |
| J | Atraso no postback da 1ª janela de mensuração da SKAN 4 | 24-48 horas | - | - | 24-48 h | - | - |
| E | Atraso na 2ª e 3ª janelas de mensuração da SKAN 4 | 24-144 horas | - | - | - | 24-144 h | 24-144 h |
| F | Janela de atividade<br /><br />(Não é relevante para a SKAN 4) | <ul><li>Durante a janela, o CV é definido pelo aplicativo.</li><li>A janela começa quando o aplicativo é aberto pela primeira vez.</li><li>Duração 12 horas - 63 dias.</li></ul> | 24 h | 72 h | - | - | - |
| G | Timer da SKAdNetwork<br /><br />(Não é relevante para a SKAN 4) | <ul><li>Timer de contagem regressiva: 24 horas</li><li>A cada vez que o CV aumenta, o timer é reiniciado. Ou seja, a contagem recomeça a partir de 24 horas.</li></ul> | 0-24 h | 0-24 h | - | - | - |
| H | Atraso aleatório da SKAdNetwork<br /><br />(Não é relevante para a SKAN 4) | Tempo de atraso aleatório de postback. A contagem regressiva começa no final do período definido por F+G. | 0-24 h | 0-24 h | - | - | - |
| I | Processamento pela AppsFlyer | Postbacks recebidos em um determinado dia são processados no final do dia a partir das 00:01 no dia seguinte. Os dados ficam disponíveis 8 horas depois. Isso significa que o processamento leva de 8 a 32 horas. Atraso médio de 20 horas. Por exemplo, um postback recebido na segunda-feira é processado na terça-feira. O dashboard é atualizado até às 08:00 UTC. | 8-32h | 8-32h | 8-32h | 8-32h | 8-32h |
| J | Resumo | O tempo total que pode decorrer | 32 horas-104h | 80-152h | 80-128 horas | 200-344h | 872-1016h |

</Accordion>

<div id="organic-metrics-in-the-context-of-skadnetwork" />

<Accordion title="Métricas orgânicas no contexto da SKAdNetwork">

As métricas orgânicas no dashboard da SKAdNetwork são calculadas usando o seguinte mecanismo:

* A **receita orgânica** está disponível apenas para receita no modo <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#fixed-modes">fixo</Anchor> ou legado.
* Eventos **orgânicos no aplicativo** estão disponíveis apenas para "conversão" no modo <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#fixed-modes">fixo</Anchor> ou legado.
* Para os **modos não legados** (<Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#skan-4">SKAN 4</Anchor>, personalizado e encode), os dados orgânicos estão disponíveis apenas para instalações.
* A SKAdNetwork da Apple envia postbacks relacionados aos usuários que instalam depois de engajar com uma fonte de mídia. Isso oferece as métricas não orgânicas.
* Os dashboards tradicionais da AppsFlyer contêm métricas de todas as instalações, independentemente da fonte.  Veja a <Anchor target="_blank" href="/marketers/pt/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side">atribuição da AppsFlyer lado a lado com a atribuição SKAN</Anchor>.
* Usando esses dados, as métricas orgânicas são calculadas como A-B, onde:
  * A = Total de todos os usuários com base no dashboard de visão geral tradicional
  * B = Usuários não orgânicos conforme relatado nos postbacks da SKAdNetwork

**Advertência relativa ao Apple Search Ads**: as instalações trazidas pelo Apple Search Ads no dashboard tradicional não são orgânicas. No entanto, no contexto da SKAdNetwork, elas fazem parte da métrica orgânica.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Acesso da ad network | As ad networks recebem postbacks |
| Agências | Não compatível Não compatível Indisponível Isso significa que as agências não devem habilitar as ad networks que executam campanhas de SKAdNetwork. Agência! Peça ao anunciante para ativar a ad network, não faça isso sozinho. As agências podem indicar que trouxeram o usuário implementando o <Anchor target="_blank" href="/partners/pt/docs/getting-started-agency-onboarding#campanhas-da-agência-de-skadnetwork">reconhecimento de agência da SKAN</Anchor>. |
| Transparência da agência | N/D |
| Fuso horário | UTC |
| Moeda | USD |
| Dados orgânicos | Com base nos dados de eventos do SDK. Por exemplo, as métricas de instalação orgânica são calculadas assim: Dados de todas as instalações reportadas pelo SDK menos as instalações não orgânicas reportadas pela SKAdNetworks. |
| Dados não orgânicos | Baseado em postbacks da SKAdNetwork |
| Atualização dos dados | Diária |
| Histórico de dados | Data mais antiga, disponibilidade do iOS 14 (16 de setembro de 2020) |
| Acesso do usuário | Os usuários da conta devem ter as <Anchor target="_blank" href="/marketers/pt/docs/user-management">permissões necessárias</Anchor> |
| App clips | Os App clips são atribuídos como orgânicos no dashboard da SKAdNetwork. Use o dashboard de Visão Geral para exibir fontes de mídia de invocação. |

</Accordion>

<div id="skan-integrated-partners" />

## Parceiros integrados da SKAN

<div id="recording-ad-revenue" />

<Accordion title="Registrando receita de anúncios">

Atribua a receita de anúncios gerada durante a janela de mensuração da SKAdNetwork à campanha que traz o usuário. Atualmente, isso é limitado aos anunciantes integrados à receita de anúncios a nível de impressão da MoPub via SDK.

Para registrar a receita de anúncios no dashboard da SKAN:

* <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-roi360-ad-revenue-sdk-api">Integre o SDK de receita de anúncios a nível de impressão</Anchor> ao seu aplicativo.
* Se você usar o modo fixo do Conversion Studio da SKAN [legacy], <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#report-events-by-servertoserver-api">ative o suporte de servidor para servidor da SKAdNetwork</Anchor>.

**Atenção**: veja a documentação do <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-roi360-ad-revenue-sdk-api">conector genérico do SDK</Anchor> para mais informações sobre as fontes de anúncios disponíveis para mediação.

</Accordion>

<div id="sending-postbacks-to-integrated-partners" />

<Accordion title="Envio de postbacks para parceiros integrados">

A AppsFlyer envia postbacks de parceiros integrados relacionados à atribuição SKAN (para SKAN 4, os postbacks são enviados apenas para a janela 1).

Confira as várias opções e requisitos na tabela a seguir

| Assunto | Descrição |
| --- | --- |
| <span id="transaction-id-sharing"></span>Compartilhamento de transcation ID | **Ação necessária**: verifique com o parceiro integrado se eles exigem o <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/verifying_an_install_validation_postback">ID da transação</Anchor> e configure a definição de acordo.<br /><br />A AppsFlyer envia os postbacks de parceiros de ad networks atribuídas. Ou seja, os postbacks decodificados, e não uma cópia do postback SKAdNetwork recebido do iOS. Esses postbacks contêm dados de CV decodificados relacionados à instalação e dados de eventos in-app associados de ações realizadas pelo usuário durante a janela de atividade.<br /><br />Como o transaction ID pode ser usado para decodificar o seu CV, não o compartilhamos sem a sua permissão.<br /><br />**Compartilhamento de transcation ID**<br /><br />Anunciantes <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#b-advanced-privacy">podem ativar o compartilhamento do transaction ID</Anchor> da seguinte forma: na AppsFlyer, acesse **configuração** > **integrações ativas** > selecione um parceiro > **aba integração** > **compartilhamento de dados**. |
| <span id="inapp-event-mapping-verification"></span>Verificação de mapeamento de eventos in-app | **<span id="1611499069.009700"></span>Ação necessária**: você deve <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#métodos-de-mapeamento">mapear seus eventos in-app</Anchor> com os nomes de eventos de parceiros correspondentes, de modo que o parceiro registre os postbacks corretamente.<br /><br />Para cada um dos parceiros que executam campanhas da SKAdNetwork, verifique se o evento no aplicativo está definido de acordo com o tipo de mensuração do aplicativo selecionado.<br /><br />**Para verificar e alterar mapeamentos de eventos in-app do parceiro**:<ol><li>Na AppsFlyer, acesse **colaborar**  >  **integrações ativas**.</li><li>Selecione o parceiro.</li><li>Acesse a aba de **Integração**.</li><li>Confirme e, se necessário, faça alterações nas configurações da seguinte forma:<ol><li>Ative o **postback de eventos in-app**.</li><li>Certifique-se de que os eventos in-app, os **nomes de eventos SDK** configurados na mensuração da SKAdNetwork, estão mapeados para os **identificadores de eventos dos parceiros**.</li></ol></li><li>Clique em **Salvar integração**.</li></ol> |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/about-att-and-skan">Guia rápido e perguntas frequentes sobre o iOS 14, a ATT e a SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">Configurar a mensuração usando o Conversion Studio para SKAN (configurações da SKAdNetwork)</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Dashboard SKAN da AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/skan-integrated-partners-list">Lista de parceiros integrados da SKAN</Anchor>
> * Interoperação com parceiros da SKAN que exigem que seja feita uma configuração na AppsFlyer:
>   * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/pt/docs/get-skan-postback-data-from-google-ads">Google Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/pt/docs/skan-interoperation-with-tiktok-for-business">Tik Tok for Business</Anchor>
>   * <Anchor target="_blank" href="/marketers/pt/docs/skan-interoperation-with-snapchat">Snapchat</Anchor>

<div data-zendesk-anchors="01H7Z06Z03AQY25A3E45Z47A9G=skan 01H7Z06Z03CSKH1ZB9RQP6SHA8=observa%C3%A7%C3%A3o 01H7Z06Z03MRE6BCSG1AEXN947=about-apple-skan appsflyer-skan-solution=solu%C3%A7%C3%A3o-para-skan-da-appsflyer 01H7Z06Z04G479NAKBEA33SGSZ=solu%C3%A7%C3%A3o-para-skan-da-appsflyer 01H7Z06Z05CAVK3CR7F5FBKFC5=principles-and-flow skan-attribution-flow=fluxo-de-atribui%C3%A7%C3%A3o-da-skan 01H7Z06Z05EGK5QBDK6G7BJQJK=fluxo-de-atribui%C3%A7%C3%A3o-da-skan 01H7Z06Z053M2H3CJ6SV4VDZPZ=conversion-studio additional-skadnetwork-information=informa%C3%A7%C3%B5es-adicionais-sobre-a-skadnetwork 01H7Z06Z05556NQ35HMR4E2TRY=informa%C3%A7%C3%B5es-adicionais-sobre-a-skadnetwork 01H7Z06Z05G0YB56GDG5E196QM=reporting-options 01H7Z06Z05M3BPSBTCMJ3NHK5D=skadnetwork-solution-implementation-checklist 01H7Z06Z05YF4J0MPMJ40EG7BX=troubleshooting-guide 01H7Z06Z0502NW8KFJ7XRZFWJR=timing-from-app-install-until-dashboard-and-reports-update 01H7Z06Z068462E4QTGTSMNS7H=organic-metrics-in-the-context-of-skadnetwork 01H7Z06Z0615QHCY6JZ4MAMTJ8=traits-and-limitations skadnetwork-integrated-partners=parceiros-integrados-da-skan 01H7Z06Z06KGT6ESN42XTJSK2F=parceiros-integrados-da-skan 01H7Z06Z06NWJQ6W50MCD3P352=recording-ad-revenue 01H7Z06Z06K2ZB949GGTJV6MJP=sending-postbacks-to-integrated-partners h_01HE7TC49KRRX1RVGX1FY7C52T=veja-tamb%C3%A9m" />

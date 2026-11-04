---
title: Relatórios de dados brutos
metadata:
  keywords:
    - LTV
    - raw data
    - uninstalls
    - AFI
    - Advertisers
    - Agencies
    - Premium Feature
    - Gray
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2016-03-21T08:32:06Z'
  edited_at: '2026-08-18T00:05:24Z'
  id: 209680773
  locale: pt
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/pt/articles/209680773
---
> **Resumo:** Os dados a nível de linha (também conhecidos como dados brutos) descrevem eventos de usuários, como instalações, eventos in-app, visitas ao site, instalações bloqueadas pelo Protect360, receitas de anúncios e postbacks associados ao usuário enviados aos parceiros. Os dados brutos estão disponíveis por download, API e Data Locker.

<div id="raw-data-reportingtools-and-reports" />

## Relatórios de dados brutos – ferramentas e relatórios

Os relatórios de dados brutos permitem analisar o comportamento e as jornadas do usuário, reconciliar contas de ad network e enriquecer seus sistemas de CRM e BI. Ao usar dados brutos, você aumenta sua capacidade de analisar, otimizar e melhorar a performance do aplicativo.

Os relatórios são disponibilizados por ferramentas de relatórios. As ferramentas possuem características distintas, adequadas a diferentes casos de uso. Por exemplo, para reconciliar uma determinada conta de ad network, faça o download do relatório conforme necessário por meio da página Exportar dados. Para fazer com que os dados de performance do usuário sejam enviados aos seus sistemas de BI, obtenha os dados de forma programática usando o Data Locker ou a Pull API.

<div id="tip" />

> 👍 **Dica**
>
> Quer entender mais sobre seus dados brutos? Confira este <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7806/play/18629/viewing-and-understanding-your-raw-data">curso breve e informativo</Anchor> no Portal de aprendizagem da AppsFlyer.

<div id="reporting-tools-characteristics-and-features" />

<Accordion title="Ferramentas de relatórios—características e recursos">

Os relatórios são disponibilizados usando as ferramentas de relatório listadas nesta seção.

Considerações:

* O intervalo de datas do relatório está relacionado à data da atividade (real) em que o evento ocorreu. Isso contrasta com os relatórios agregados em que o intervalo de datas é <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">baseado em LTV</Anchor>.
* Descrições dos campos: consulte o <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">dicionário de campos de dados</Anchor>.

<div id="reporting-tools" />

#### Ferramentas de relatório

<table><thead><tr><th>Ferramenta</th><th>Descrição</th><th>Vários / um único app (1)</th><th>Capacidade de atualização de dados (2)</th><th>Incorporar em scripts</th><th>Fuso horário</th><th>Moeda</th></tr></thead><tbody><tr><td><a href="./raw-data-export-page" target="_blank">Página de exportação de dados brutos</a></td><td><ul><li>Baixe o relatório usando a interface do usuário</li><li>Formato: Arquivo CSV</li></ul></td><td>Único</td><td>Atualizado continuamente</td><td><span><strong>X</strong></span></td><td>Específico do aplicativo</td><td>Específico do aplicativo</td></tr><tr><td><a href="./pull-api-raw-data" target="_blank">Pull API\*</a></td><td><ul><li>Baixe o relatório usando chamadas de API.</li><li>Formato: Arquivos CSV</li></ul></td><td>Único</td><td>Atualizado continuamente</td><td><span>✓</span></td><td><ul><li>Selecionável</li><li>Predefinição: UTC</li></ul></td><td><ul><li>Selecionável</li><li>Predefinição: USD</li></ul></td></tr><tr><td> <a href="./data-locker-for-marketers" target="_blank">Data Locker</a> <span><strong>P</strong></span> </td><td><ul><li>Dados enviados para um <a href="./data-locker-cloud-service-setup" target="_blank">bucket na nuvem</a> </li><li>Sem limitações de volume</li><li>Janela de disponibilidade de dados: 14 dias.</li><li>Formato: CSV ou parquet</li></ul></td><td>Múltiplos apps</td><td>Atualizado continuamente com um atraso de várias horas</td><td><span>✓</span></td><td>UTC</td><td>USD </td></tr><tr><td> <a href="./push-api-streaming-raw-data" target="_blank">Push API<span></span></a> <span><strong>P</strong></span> </td><td><ul><li>Dados da jornada do usuário (instalações, eventos in-app, retargeting, SKAN) enviados para seus servidores em tempo real.</li><li>Formato: JSON ou parâmetros de query</li></ul></td><td>Pode usar o mesmo endpoint</td><td>Minutos após o evento ser registrado na AppsFlyer</td><td><span>✓</span></td><td>UTC + específico do app</td><td>USD + específico do app</td></tr><tr><td> <a href="./conversion-data-payloads-and-scenarios" target="_blank">Dados de conversão do SDK</a> (3)</td><td><ul><li>Obtenha dados de conversão de atribuição no aplicativo.</li><li>Formato: JSON</li></ul></td><td>N/D</td><td>Os dados de conversão do SDK recuperam os dados de atribuição do usuário em até 8 segundos a partir da primeira abertura do Aplicativo (até 5 segundos nos servidores da AppsFlyer, mais o atraso de ponta a ponta da network).</td><td><span>✓</span></td><td>UTC</td><td>N/D</td></tr><tr><td colspan="7"> <strong>Notas e abreviaturas:</strong><br/>(1) Suporte para vários apps<br/>(2) A atualização real dos dados depende do relatório em si, pois alguns relatórios são diários.<br/>(3) Os dados de conversão do SDK recuperam os dados de atribuição do usuário segundos após a primeira abertura do aplicativo, tornando-se o método menos preciso.<br/><span><strong>(P)</strong> </span><span>Funcionalidade premium</span><br/><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Aplicam-se as cotas de geração de relatórios</a> </td></tr></tbody></table>

<div id="tool-limitations" />

#### Limitações da ferramenta

<table><thead><tr><th>Limitação </th><th>Pull API (\*)</th><th>API de push</th><th>Relatório do Data Locker</th><th>SDK<br/>Dados de conversão</th></tr></thead><tbody><tr><td>Limite de dados</td><td>1 milhão de linhas por chamada</td><td>N/D</td><td>N/D</td><td>N/D</td></tr><tr><td>Opções de seleção de dados</td><td>Selecione os tipos de dados. Opções limitadas para seleção de campos</td><td>Selecione os tipos de dados, campos e eventos in-apps</td><td>Selecione os tipos de dados, campos e eventos in-apps</td><td>Não</td></tr><tr><td>Janela de disponibilidade de dados</td><td>90 dias</td><td>N/D</td><td>14 dias </td><td>Vitalício (disponível no SDK)</td></tr><tr><td colspan="5"><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Aplicam-se as cotas de geração de relatórios</a></td></tr></tbody></table>

<div id="integration-considerations" />

#### Considerações de integração

| Consideração | Extrair API | API de push | Relatório do Data Locker | SDK  <br />Dados de conversão |
| --- | --- | --- | --- | --- |
| Desenvolvimento do lado do servidor | Opcional | Obrigatório | Opcional | Opcional |
| Requer processamento de dados | Opcional | Obrigatório | Opcional | Opcional |
| Risco de perda de dados | Não | Sim, se os servidores de recepção estiverem inativos | Não | Pequeno, se houver atrasos na resposta da ad network |
| Custos de processamento cliente-servidor | Nenhum | Alto | Baixo | Nenhum (a menos que os dados sejam enviados para os servidores) |
| Manutenção cliente-servidor | Nenhum | Alto | Baixo | Nenhum (a menos que os dados sejam enviados para os servidores) |
| Formato de dados | Arquivo CSV | JSON ou parâmetros de query | CSV ou parquet | JSON |

</Accordion>

Os registros de dados brutos que ocorrem em um determinado contexto são agrupados em relatórios. Por exemplo, instalações não orgânicas, eventos in-app orgânicos. Para facilitar a explicação, os relatórios são agrupados da seguinte forma:

* **Jornada do usuário:** use para rastrear a jornada e o engajamento de um usuário com o aplicativo.  
  Por exemplo: clique > instalação > evento in-app > desinstalação.
* **Funcionalidade:** relacionada a uma determinada funcionalidade da AppsFlyer, mas não faz parte da jornada principal do usuário. Por exemplo, postbacks para ad networks, relatórios de fraude e de regras de validação e relatórios de receita publicitária no nível do usuário.

<div id="report-fields" />

<Accordion title="Campos de relatório">

O dicionário de campos de <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">dados brutos</Anchor> contém campos relevantes para relatórios de jornada do usuário e alguns campos do relatório de recurso. Os princípios são os seguintes:

* **Viagem do utilizador:**
  * conjunto comum de campos.
  * O preenchimento do campo depende do contexto da jornada. Por exemplo, relatórios não orgânicos contêm a fonte de mídia creditada por trazer o usuário. Os campos de atribuição em relatórios orgânicos não são preenchidos porque não há fonte de mídia.
* **Funcionalidade**: têm um conjunto exclusivo de campos ou contêm campos de jornada do usuário e campos adicionais relevantes para a funcionalidade específica. Por exemplo, os relatórios da SKAdNetwork têm uma lista exclusiva de campos, já os relatórios de postback contêm os campos de jornada do usuário e campos adicionais relacionados ao envio de postback aos parceiros.

**Dica**! A melhor forma de se familiarizar com os relatórios é visualizá-los. Você pode baixar seus relatórios na <Anchor target="_blank" href="/marketers/pt/docs/raw-data-export-page">página de exportação de dados.</Anchor>

Para facilitar a compreensão, os campos de jornada do usuário são divididos em grupos com base no contexto.

<div id="user-journey-raw-data-field-groups" />

#### Grupos de campos de dados brutos da jornada do usuário

| Grupo de campos | Relevante para usuários orgânicos | Exemplos de campos |
| --- | --- | --- |
| Aplicativo | Sim | App ID, nome do app, versão do app, versão do SDK, ATT |
| Atribuição | Não, exceto para a hora da instalação | Hora da instalação, hora do toque atribuído, fonte de mídia, campanha, adset, anúncio, parceiro e tipo de conversão de retargeting |
| Atribuição de colaboradores | Não | Parceiro colaborador, tipo de correspondência |
| Informação do dispositivo | Sim | Advertising ID, GAID, OAID, tipo de dispositivo, customer user ID |
| Localização do dispositivo | Sim | Endereço IP, cidade, país |
| Evento | Sim | Preenchido nos relatórios de eventos in-app:<br /><br />Nome do evento, valor do evento, receita do evento |

</Accordion>

<div id="user-journey-reports" />

## Relatórios de jornada do usuário

![Raw_data_-_User_acquisition_.png](https://files.readme.io/319da2a6a5567d6cfe4a74337279e67e0bdcdb063e62ecacde5eb4293a98a1a2-36317497158033.png)

<div id="user-journey-basics" />

<Accordion title="Noções básicas da jornada do usuário">

Os relatórios de jornada do usuário contêm dados coletados para eventos que ocorrem durante a vida útil de um usuário. Os dados são divididos em relatórios de acordo com:

* Fonte do usuário: orgânica ou não orgânica
* Contexto da jornada:
  * Engajamento com anúncios antes da instalação do aplicativo (impressões e cliques)
  * Aquisição
  * Redirecionamento

**Os relatórios de aquisição de usuários (UA) contêm:**

* As impressões e cliques que ocorrem antes da instalação feita por qualquer usuário *potencial* que engaja com um anúncio.
* Evento de instalação.
* Eventos in-app subsequentes realizados pelo usuário.

**Os relatórios de retargeting incluem:**

* As impressões e cliques que ocorrem quando o usuário é redirecionado.
* Eventos de conversão: Reengajamento ou reatribuição
* Eventos in-app subsequentes realizados como parte do reengajamento. Considere:
  * Os dados de retargeting são sempre de origem não orgânica.
  * Os eventos in-app de retargeting estão nos relatórios tanto de UA quanto de eventos in-app de retargeting. Consulte a metodologia de <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">atribuição dupla de retargeting</Anchor>.

    ![Raw_data_-_Retargeting.png](https://files.readme.io/717f6e43ca3b224ead9e3e1c5f9b277d2f21dbc1fe3b4c217ebf4bdbc539bab7-36317470735249.png)

Para seguir uma jornada do usuário, combine os relatórios relacionados à parte da jornada que lhe interessa, por exemplo, instalações e eventos in-app. Depois isso, classifique o relatório usando o AppsFlyer ID, o horário do evento e o tipo de relatório. O resultado são os eventos de um determinado usuário ao longo do tempo, ou seja, a jornada do usuário.

</Accordion>

<div id="user-journey-report-availability" />

<Accordion title="Disponibilidade do relatório da jornada do usuário">

* A disponibilidade do relatório depende do seu plano de assinatura.
* Os relatórios podem incluir usuários orgânicos, usuários não orgânicos ou ambos, conforme indicado.
* As políticas de retenção se aplicam aos relatórios de dados brutos históricos, dependendo da ferramenta de relatório e da origem dos dados brutos. Em geral, os dados estão disponíveis para os 90 dias anteriores. **Atenção**! As políticas de retenção não se aplicam a dados agregados.

<div id="user-journey-reports-1" />

#### Relatórios de jornada do usuário

<table><thead><tr><th>Categoria</th><th>Exclusivo para Data Locker</th><th>Tópico do relatório</th><th>Orgânico</th><th>Não orgânico</th></tr></thead><tbody><tr><td>Aquisição de usuários</td><td><span>✓</span></td><td>Cliques</td><td colspan="2">N/D</td></tr><tr><td>Redirecionamento</td><td><span>✓</span></td><td>Cliques de campanhas de retargeting </td><td colspan="2">Retargeting sempre não orgânico</td></tr><tr><td>Aquisição de usuários</td><td><span>✓</span></td><td>Impressões</td><td colspan="2">N/D</td></tr><tr><td>Redirecionamento</td><td><span>✓</span></td><td>Impressões de campanhas de retargeting</td><td colspan="2">Retargeting sempre não orgânico</td></tr><tr><td>Aquisição de usuários</td><td>-</td><td>Instalações </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Aquisição de usuários</td><td>-</td><td>Eventos in-app </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Aquisição de usuários</td><td>-</td><td>Receita de anúncios atribuída</td><td>-</td><td><span>✓</span></td></tr><tr><td>Aquisição de usuários</td><td>-</td><td>Receita publicitária orgânica</td><td><span>✓</span></td><td>-</td></tr><tr><td>Redirecionamento</td><td>-</td><td>Receita publicitária de retargeting</td><td colspan="2">Retargeting sempre não orgânico</td></tr><tr><td>Redirecionamento</td><td>-</td><td>Conversões de retargeting (reengajamentos e reatribuições)</td><td colspan="2">Retargeting sempre não orgânico</td></tr><tr><td>Redirecionamento</td><td>-</td><td>Retargeting de eventos in-app (reengajamentos e reatribuições)</td><td colspan="2">Retargeting sempre não orgânico</td></tr><tr><td>Redirecionamento</td><td><span>✓</span></td><td>Sessões de retargeting (reengajamentos e reatribuições)</td><td colspan="2">Retargeting sempre não orgânico</td></tr><tr><td>Aquisição de usuários</td><td><span>✓</span></td><td>Sessões</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Aquisição de usuários</td><td>-</td><td>Desinstalações não orgânicas </td><td>-</td><td><span>✓</span></td></tr><tr><td>Aquisição de usuários</td><td>-</td><td>Desinstalações orgânicas</td><td><span>✓</span></td><td>-</td></tr><tr><td>Aquisição de usuários</td><td><span>✓</span></td><td>Engajamento entre plataformas</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div id="user-journey-report-descriptions" />

<Accordion title="Descrições do relatório de jornada do usuário">

<div id="clicks-and-impressions" />

#### Cliques e impressões

| Relatório | Características |
| --- | --- |
| Contexto | Um usuário engaja com uma campanha e clica ou visualiza um anúncio. |
| Características | Os relatórios contêm um registro do link de atribuição e cabeçalhos HTTP presentes quando um usuário clica ou <Anchor target="_blank" href="/marketers/pt/docs/measure-view-through-engagements#set-impression-links">visualiza</Anchor> um anúncio. |
| Caso de uso | <ul><li>Otimize campanhas que não levam a um aplicativo aberto (instalação, reatribuição, reengajamento).</li><li>Faça o retargeting desses usuários usando campanhas diferentes.</li></ul> |
| Exemplo de relatório | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1036692270&single=true&output=csv">Cliques</Anchor> |
| Observações | Dados de SRN não disponíveis. |
| Usuários restritos | Em alguns casos, devido a regras de privacidade, os dados de impressão e cliques são restritos (não têm identificadores de usuário) ou não estão disponíveis. A disponibilidade depende da fonte de mídia e da plataforma. |

<div id="installs-and-retargeting-conversions" />

#### Instalações e conversões de retargeting

<table><thead><tr><th rowspan="2">Nome do relatório </th><th rowspan="2"><p>Aquisição de usuários: Instalações</p></th><th rowspan="2">Retargeting: Conversões</th></tr></thead><tbody><tr><td>Contexto</td><td><p>Quando um usuário abre um aplicativo pela primeira vez.</p></td><td><p>Depois que um usuário engaja com um anúncio de retargeting e, em seguida, abre o aplicativo. Uma conversão de retargeting é um reengajamento ou reatribuição.</p> Consulte o <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">Guia de atribuição de retargeting.  </a> </td></tr><tr><td>Casos de uso</td><td><ul><li>Gerar relatórios agregados usando campos não disponíveis através das ferramentas de análise da AppsFlyer.</li><li>Combine-os com outros relatórios para realizar análises avançadas e transversais.</li><li>Analise a performance em diferentes dimensões, como cidades, áreas metropolitanas e outros. </li><li>Segmente utilizadores conforme o país, cidade e idioma para fins de direcionamento.</li><li>Obtenha IDs de dispositivo do usuário para fins de retargeting.</li></ul></td><td>Semelhante às instalações.</td></tr><tr><td>Orgânico vs. não orgânico</td><td><ul><li> <strong>Não orgânico:</strong> Os grupos de campos de atribuição e contribuição são preenchidos</li><li> <strong>Orgânico:</strong> O campo da fonte de mídia está em branco, nulo, ou orgânico. Lembre-se disso ao carregar dados em seus sistemas. </li></ul></td><td>Não aplicável</td></tr><tr><td>Exemplo de relatório</td><td><a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR2yvNGmZp8ataHBj89CFq856PmDixnyjKK75O8fQcS9TjT8J2jBAnJoTn3350NV-7pCSlaT0oh8ebs/pub?output=csv" target="_blank">Instalações</a></td><td>O relatório de conversões de retargeting tem a mesma estrutura que o relatório de instalações. Alguns campos são preenchidos no contexto do retargeting. Consulte os <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">dados brutos de retargeting</a>. </td></tr></tbody></table>

<div id="in-app-events" />

#### Eventos in-app

<Table>
  <thead>
    <tr>
      <th>
        Relatório
      </th>
      <th>
        Características
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-context"></span>
        Contexto do relatório
      </td>
      <td>
        Lista cronológica das ações realizadas pelos usuários após a atribuição (instalação, reatribuição ou reengajamento)
      </td>
    </tr>
    <tr>
      <td><span id="characteristics"></span>
        Características
      </td>
      <td>
        * A estrutura do relatório e os campos são semelhantes aos dos relatórios de instalação.
        * Campos dedicados descrevem o evento. Isso inclui o nome, o valor, a receita e o horário do evento.
      </td>
    </tr>
    <tr>
      <td><span id="use-case"></span>
        Caso de uso
      </td>
      <td>
        Use o relatório para:

        * Obter insights ao observar a jornada do usuário durante a vida útil do usuário
        * Combinar os dados brutos de instalações e eventos in-app-para acompanhar a jornada completa do usuário.
      </td>
    </tr>
    <tr>
      <td><span id="event-values"></span>
        Valores dos eventos
      </td>
      <td>
        **Campo valor do evento**

        O campo valor do evento contém todos os dados relacionados ao evento em um JSON. Você pode enviá-lo ao seu sistema de BI para análises mais aprofundadas.

        **Dica!** Você pode usar o <Anchor target="_blank" href="https://docs.microsoft.com/en-us/power-query/parse-json-xml">Power Query no Microsoft Excel</Anchor> para analisar os parâmetros de evento das strings JSON.

        ```json
        {"af_level":"10","af_user_journey":"3387","arena":"7","char_type":"paladin"}
        ```

        **Relatórios de receita**

        Os dados de receita e ROI na AppsFlyer são derivados do af\_revenue enviado em eventos.

        Quando o parâmetro af\_revenue é enviado em um evento in-app, a AppsFlyer usa isso para preencher o campo de receita do evento. É esse campo que a AppsFlyer usa para atualizar o dashboard e os relatórios agregados.

        Atenção! Use o parâmetro af\_revenue apenas com eventos in-app que descrevem a **receita real gerada.** Para outros eventos que envolvem receita, mas não são finais, por exemplo, add\_to\_cart, use parâmetros diferentes, como af\_price
      </td>
    </tr>
    <tr>
      <td><span id="example-report"></span>
        Exemplo de relatório
      </td>
      <td>
        <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQhOF-g3HeqZt3rXx7WZVQnB54p7ALW_IEpnJ9xtAkrcb9XzZwweiNCZzEmuX7q0i1g6yYMxYtuuX1c/pub?output=csv">Eventos in-app</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="remarks"></span>
        Observações
      </td>
      <td>
        * Os eventos in-app de retargeting são <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">duplamente registrados</Anchor> nos relatórios de UA e de dados brutos de eventos in-app de retargeting.
        * Os eventos in-app não incluem o evento de inicialização (af\_app\_opened). Isso está disponível no relatório de dados brutos das <Anchor target="_blank" href="/marketers/pt/docs/measure-sessions">sessões</Anchor>.
        * Localização geográfica: é determinada com base no endereço IP do usuário no momento em que o evento ocorre.
      </td>
    </tr>
  </tbody>
</Table>

<div id="sessions" />

#### Sessões

| Relatório | Características |
| --- | --- |
| Contexto | Quando o usuário abre o aplicativo, um evento de sessão é enviado para a AppsFlyer. O evento é registrado se o <Anchor target="_blank" href="/marketers/pt/docs/measure-sessions">tempo mínimo entre o limite de sessões</Anchor> for excedido. |
| Características | A estrutura do relatório é a mesma dos relatórios de eventos in-app. As sessões (eventos de sessão) estão em um relatório separado devido ao grande número desses eventos. |
| Caso de uso | Entender o engajamento do usuário com o aplicativo. |
| Exemplo de relatório | O relatório de sessões é semelhante ao relatório de eventos in-app. Atenção: em dados brutos, as sessões têm o nome do evento *abertura*. |

<div id="uninstalls" />

#### Desinstalações

| Relatório | Características |
| --- | --- |
| Contexto | Registro de usuários que desinstalam o aplicativo. |
| Características | <ul><li>Esse relatório é atualizado diariamente e não continuamente, como é o caso de outros relatórios da jornada do usuário.</li><li>No relatório, o horário do evento representa o horário em que a AppsFlyer determina que o aplicativo foi desinstalado e não a desinstalação real em si. Consulte a página Medição de desinstalação.</li></ul> |
| Campos disponíveis | <ul><li>Se o usuário vier de uma fonte de mídia não orgânica, os campos da fonte de mídia serão preenchidos.</li><li>Considere que o evento de desinstalação é gerado pelos servidores da AppsFlyer depois de determinar que o usuário foi desinstalado. Consequentemente, muitos campos não são preenchidos.</li><li>Os identificadores de usuário disponíveis são aqueles registrados no momento da instalação. O CUID nunca está disponível.</li><li>Os campos relacionados à área geográfica são preenchidos com a localização do usuário no momento do engajamento com a fonte de mídia (clique ou impressão). Se o local do engajamento não estiver disponível, o local associado ao evento de instalação será usado.</li></ul> |
| Exemplo de relatório | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1558773473&single=true&output=csv">Desinstalações</Anchor> Atenção! No exemplo, para maior clareza, a linha 2 indica quais campos são preenchidos, se os dados relevantes estiverem disponíveis. |
| Casos de uso | <ul><li>Analisar o evento de desinstalação, dispositivo e características do usuário.</li><li>Criar um público de eventos de desinstalação para retargeting.</li></ul> |

</Accordion>

<div id="user-journey-report-availability-per-tool" />

<Accordion title="Disponibilidade do relatório da jornada do usuário por ferramenta">

<div id="ad-engagement-report-by-tool" />

#### Relatório de engajamento com anúncios por ferramenta

<table><thead><tr><th>Relatório</th><th>Exportar dados</th><th>Extrair API</th><th>Relatório do Data Locker</th><th>API de push</th><th>SDK<br/>Dados de conversão</th></tr></thead><tbody><tr><td>Impressões (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Cliques (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td colspan="6">(1) Os dados de cliques e impressões são disponibilizados por não SRNS. As SRNs não disponibilizam esses dados.</td></tr></tbody></table>

<div id="user-acquisition-reports-by-tool" />

#### Relatórios de aquisição de usuários por ferramenta

| Relatório | Exportar dados | Extrair API | Relatório do Data Locker | API de push | Dados de conversão do SDK |
| --- | --- | --- | --- | --- | --- |
| Instalações | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sessões | - | - | ✓ | - | - |
| Eventos in-app | ✓ | ✓ | ✓ | ✓ | - |
| Desinstalações | ✓ | ✓ | ✓ | - | - |

<div id="retargeting-raw-data-reports-by-tool" />

#### Relatórios de dados brutos de retargeting por ferramenta

<table><thead><tr><th>Relatório</th><th>Exportar dados</th><th>Extrair API</th><th>Relatório do Data Locker</th><th>API de push</th><th>SDK<br/>Dados de conversão</th></tr></thead><tbody><tr><td>Cliques (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Conversões (reatribuições + reengajamentos)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Impressões (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Sessões</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Eventos in-app</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) Os dados de cliques e impressões são disponibilizados por não SRNS. As SRNs não disponibilizam esses dados.</td></tr></tbody></table>

</Accordion>

<div id="faq" />

<Accordion title="Perguntas frequentes">

| Detalhes |
| --- |
| **Qual é a diferença entre os marcadores de data/hora?**<br /><br />Os marcadores de data e hora são comuns a todos os relatórios. Isso possibilita combinar relatórios diferentes.<br /><br />Os seguintes marcadores de data/hora são relevantes:<ul><li>**Hora de toque atribuído**: hora em que o usuário engajou com um anúncio.</li><li>**Hora de instalação** : hora em que o aplicativo é iniciado pela primeira vez.</li><li>**Hora do evento**: hora em que o evento ocorre.</li></ul>Considere:<ul><li>Nos relatórios de instalação, os horários de instalação e de evento são os mesmos.</li><li>Nos relatórios de eventos in-app, os horários de instalação e de evento são diferentes. A diferença pode mostrar o tempo que passa entre a abertura do aplicativo e o engajamento do usuário com o aplicativo.</li></ul> |
| **Qual é o objetivo do campo de colaborador?**<br /><br />O campo de colaborador lista as fontes de mídia colaboradoras. Às vezes chamadas de <Anchor target="_blank" href="/marketers/pt/docs/measure-assisted-installs#relatórios-de-instalações-auxiliadas">Instalações Assistidas</Anchor>. No Protect360, elas também são usadas para a <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#correção-de-atribuição-para-instalações-sequestradas">correção de atribuição da instalação que sofreu hijacking</Anchor>. |
| **O que é o campo de palavras-chave—por que ele não está disponível em todas as instalações não-orgânicas?**<br /><br />As instalações atribuídas ao Google Ads ou Apple Ads podem conter palavras-chave ou keyword IDs associados ao anúncio que levou à instalação. |

</Accordion>

<div id="install-report-tips" />

<Accordion title="Dicas de relatório de instalação">

**Compreendendo a jornada do usuário**

A jornada do usuário é uma série de etapas que o usuário executa antes de atingir uma meta, como comprar um produto ou reservar um voo. A ideia por trás da análise da jornada do usuário é ver o que o usuário faz no aplicativo, quão ativo ele é e qual valor ele traz durante um determinado período.

Você pode identificar e destacar as jornadas do usuário com a ajuda do AppsFlyer ID. O ID é gerado para cada instalação de aplicativo por dispositivo. O ID permanece inalterado durante todo o ciclo de vida do usuário (da instalação à desinstalação.) O ID persiste mesmo que o usuário redefina o device ID. O ID persiste mesmo que o usuário redefina o ID do dispositivo.

Como os relatórios de instalação e eventos in-app têm as mesmas estruturas, eles podem ser mesclados em um único relatório. No relatório mesclado, você pode agregar e filtrar usando o AppsFlyer ID e o Costumer User ID (se disponível) para analisar as jornadas do usuário.

<div id="engaged-userstrong" />

> 📄 **Usuário engajado—forte**
>
> * Um usuário instalou o aplicativo em 20 de agosto às 09:31.
> * O relatório mesclado mostra que ele realizou compras em 20 de agosto às 10:31, 22 de agosto às 15:22 e 25 de agosto às 16:47.
> * A partir disso, concluímos que o usuário é um usuário engajado. Ele fez uma compra uma hora após a inicialização do aplicativo e continuou comprando nos dias seguintes à instalação.
>
> #### <span id="engaged-userweak"></span>Usuário engajado—fraco
>
> * Um usuário instala o aplicativo em 30 de julho. O relatório mesclado mostra que ele adicionou um item ao carrinho em 15 de agosto, mas não há eventos de compra subsequentes.
> * Você pode assumir que o usuário está hesitante em fazer uma compra e fazer o retargeting desse usuário com os itens já adicionados ao carrinho.
>
> #### <span id="analyzing-the-user-journey-for-campaign-optimization"></span>Analisando a jornada do usuário para otimização de campanhas
>
> * O gerente de aquisição de usuários (UA) de um aplicativo de viagens baixa os relatórios de eventos in-app e de instalação e os mescla.
> * Depois, para visualizar as jornadas do usuário no aplicativo, ele filtra ou agrega dados usando o AppsFlyer ID.
> * Ele percebe que um determinado usuário, identificado pelo AppsFlyer ID, fez download do aplicativo há 12 meses e reservou um voo vários dias depois.
> * Posteriormente, o usuário visualizou algumas ofertas de voos, mas não fez nenhuma reserva. Em uma análise mais profunda, o gerente de UA encontra mais usuários com o mesmo padrão e decide investigar mais a fundo.
> * Ele descobre que a maioria desses usuários veio do **Anúncio A** da **Campanha B** realizada na **Fonte de Mídia C.** Esse anúncio e campanha tinham como alvo usuários que desejavam viajar para um determinado destino. Esse anúncio e campanha tinham como alvo usuários que desejavam viajar para um determinado destino.
> * Ao analisar a jornada do usuário, o gerente de UA entende que a campanha pode ter sido muito limitada ou muito focada, e que os usuários não estavam suficientemente engajados com o aplicativo.

</Accordion>

<div id="feature-reports" />

## Relatórios de funcionalidades

Relatórios que mostram funcionalidades adicionais disponíveis na plataforma

* <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">Receita de anúncios</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview#relatórios-de-dados-brutos">Incrementalidade</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">Proteção contra fraudes</Anchor>

<div id="postbacks" />

<Accordion title="Postbacks">

Use relatórios de postback para revisar cópias de dados enviados para uma ad network. Por exemplo, use-os para investigar discrepâncias. Esses relatórios são para fins informativos e não são necessários para a integração com as ad networks.

* O relatório contém:
  * Cópias de postbacks enviados para a fonte de mídia atribuída.
  * <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">Campos de dados brutos</Anchor> e campos adicionais, conforme detalhado nesta seção.
* O relatório não contém:
  * Instalações de SRNs.
  * Eventos in-app relacionados ao Meta Ads, X Ads e Apple Ads.
  * Postbacks de parceiros não atribuídos. Veja <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">eventos atribuídos a qualquer parceiro ou atribuídos como orgânicos</Anchor>.
  * Usuários orgânicos. Saiba mais <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">sobre instalações orgânicas.</Anchor>
* Desde março de 2021, os campos são preenchidos de acordo com a configuração de Privacidade Avançada de uma ad network. Ou seja, se a Privacidade Avançada estiver ativada, alguns campos, como identificadores de usuário, não serão inclusos. Consulte <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification">especificação de postbacks de Privacidade Avançada para ad networks</Anchor>.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5">Obtenha relatórios de postback pela PULL API</Anchor>

<div id="postback-reports-available-via-the-export-data-page-and-pull-api" />

#### Relatórios de postback (disponíveis na página Exportar dados e Pull API)

| Tópico do relatório | Eventos enviados para a fonte de mídia atribuída |
| --- | --- |
| Instalações | Instalações não orgânicas (UA) |
| Eventos in-app | Eventos in-app não orgânicos |
| Postbacks de conversão de retargeting | Retargeting (reengajamento e reatribuição) |
| Eventos in-app de retargeting | Eventos in-app de retargeting |

<div id="additional-fields-in-postback-reports" />

#### Campos adicionais em relatórios de postback

| Campo | Observações |
| --- | --- |
| URL de postback | Alguns valores, como receita, podem não aparecer no campo apropriado, mas você ainda pode ver esses dados na URL do **postback**. |
| Método de postback |  |
| Código de resposta HTTP de postback | 200: confirma que o postback foi recebido pela ad network. |
| Mensagem de erro de postback |  |

</Accordion>

<div id="protect360-fraud-and-validation-rules" />

<Accordion title="Regras de fraude e de validação do Protect360">

* Veja os relatórios de dados brutos do <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports">Protect360</Anchor> e das <Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud#outcomes">regras de validação</Anchor>
* As ad networks e agências precisam da <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#access-protect360-dashboard-raw-data">permissão</Anchor> do anunciante para acessar os relatórios do Protect360 e das regras de validação

**Para dar permissão a um parceiro integrado para acessar o Protect360:**

1. Vá para **colaborar** > **integrações ativas**.
2. Escolha o parceiro integrado.
3. Na aba **Permissões**, ative **Acessar seu dashboard do Protect360 e dados brutos via API**.
4. Para dar acesso ao dashboard de eventos in-app (CPA), também ative **Acessar dados de eventos in-app agregados**.

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview">Relatórios agregados e analíticos</Anchor>

<div data-zendesk-anchors="raw-data-reporting%E2%80%94tools-and-reports=relat%C3%B3rios-de-dados-brutos--ferramentas-e-relat%C3%B3rios h_01HE7SRDXQ9TR0CRB2JC9XCQE2=relat%C3%B3rios-de-dados-brutos--ferramentas-e-relat%C3%B3rios h_01HE7SRDXQQJFMV9EJKPY34D00=dica reporting-tools%E2%80%94characteristics-and-features=reporting-tools-characteristics-and-features h_01HE7SRDXQFJGMY05K1SV4TF63=reporting-tools-characteristics-and-features reporting-tools=ferramentas-de-relat%C3%B3rio h_01HE7SRDXQ647XRQ8QVMPGH43B=ferramentas-de-relat%C3%B3rio tool-limitations=limita%C3%A7%C3%B5es-da-ferramenta h_01HE7SRDXQWQAKR0G6CNKC5AMT=limita%C3%A7%C3%B5es-da-ferramenta integration-considerations=considera%C3%A7%C3%B5es-de-integra%C3%A7%C3%A3o h_01HE7SRDXQN3HSMGAPBAX9S3MB=considera%C3%A7%C3%B5es-de-integra%C3%A7%C3%A3o h_01HE7SRDXQRPD8MHC8M5916HTQ=report-fields user-journey-raw-data-field-groups=grupos-de-campos-de-dados-brutos-da-jornada-do-usu%C3%A1rio h_01HE7SRDXQMGQEG1QWGWEESQER=grupos-de-campos-de-dados-brutos-da-jornada-do-usu%C3%A1rio user-journey-reports=relat%C3%B3rios-de-jornada-do-usu%C3%A1rio h_01HE7SRDXQZ50WMKCMYHZM7D92=relat%C3%B3rios-de-jornada-do-usu%C3%A1rio h_01HE7SRDXQFN0P9QK8SKAZKVKP=user-journey-basics h_01HE7SRDXRS2B12Z67MYMH0QN9=user-journey-report-availability user-journey-reports::d286e1f5=relat%C3%B3rios-de-jornada-do-usu%C3%A1rio-1 h_01HE7SRDXR7YQGWN4FNDXMNMX8=relat%C3%B3rios-de-jornada-do-usu%C3%A1rio-1 h_01HE7SRDXRK6G27SDFK3CGDCRC=user-journey-report-descriptions clicks-and-impressions=cliques-e-impress%C3%B5es h_01HE7SRDXRC9YKZ0P9ED0218SJ=cliques-e-impress%C3%B5es installs-and-retargeting-conversions=instala%C3%A7%C3%B5es-e-convers%C3%B5es-de-retargeting h_01HE7SRDXRN60XE5BSDQY28N71=instala%C3%A7%C3%B5es-e-convers%C3%B5es-de-retargeting inapp-events=eventos-in-app h_01HE7SRDXR3ZT39EDNW4MVZZTX=eventos-in-app sessions=sess%C3%B5es h_01HE7SRDXRY05XQCMZE6YPXGWQ=sess%C3%B5es uninstalls=desinstala%C3%A7%C3%B5es h_01HE7SRDXRA7ESDD4ME51WWBPR=desinstala%C3%A7%C3%B5es h_01HE7SRDXRZYNFGK4CNP4VPAE0=user-journey-report-availability-per-tool ad-engagement-report-by-tool=relat%C3%B3rio-de-engajamento-com-an%C3%BAncios-por-ferramenta h_01HE7SRDXR171M74HMQBZJ2E8R=relat%C3%B3rio-de-engajamento-com-an%C3%BAncios-por-ferramenta user-acquisition-reports-by-tool=relat%C3%B3rios-de-aquisi%C3%A7%C3%A3o-de-usu%C3%A1rios-por-ferramenta h_01HE7SRDXRMGEP5QB452ZKQ8X7=relat%C3%B3rios-de-aquisi%C3%A7%C3%A3o-de-usu%C3%A1rios-por-ferramenta retargeting-raw-data-reports-by-tool=relat%C3%B3rios-de-dados-brutos-de-retargeting-por-ferramenta h_01HE7SRDXRXR4J3HTMYW2P233Y=relat%C3%B3rios-de-dados-brutos-de-retargeting-por-ferramenta h_01HE7SRDXRWW3JKNESSN2QA4DV=faq h_01HE7SRDXR61K28JGA8944D6HV=install-report-tips h_01HE7SRDXRKFR2WYGNF317CTRX=relat%C3%B3rios-de-dados-brutos-de-retargeting-por-ferramenta engaged-user%E2%80%94strong=usu%C3%A1rio-engajadoforte h_01HE7SRDXRW0CWHGQV75VF66DC=usu%C3%A1rio-engajadoforte engaged-user%E2%80%94weak=usu%C3%A1rio-engajadofraco h_01HE7SRDXRNMDZEJQ32665T14F=usu%C3%A1rio-engajadofraco analyzing-the-user-journey-for-campaign-optimization=analisando-a-jornada-do-usu%C3%A1rio-para-otimiza%C3%A7%C3%A3o-de-campanhas h_01HE7SRDXRRET0YN4Q8WYMENSR=analisando-a-jornada-do-usu%C3%A1rio-para-otimiza%C3%A7%C3%A3o-de-campanhas feature-reports=relat%C3%B3rios-de-funcionalidades h_01HE7SRDXSVAHKBYQK0C71K6AR=relat%C3%B3rios-de-funcionalidades h_01HE7SRDXSFWMVY61NBYFQ4XSM=postbacks postback-reports-available-via-the-export-data-page-and-pull-api=relat%C3%B3rios-de-postback-dispon%C3%ADveis-na-p%C3%A1gina-exportar-dados-e-pull-api h_01HE7SRDXS6T4M4CRQN0ZTJETR=relat%C3%B3rios-de-postback-dispon%C3%ADveis-na-p%C3%A1gina-exportar-dados-e-pull-api additional-fields-in-postback-reports=campos-adicionais-em-relat%C3%B3rios-de-postback h_01HE7SRDXSYBDG0H2QEYBFWSRH=campos-adicionais-em-relat%C3%B3rios-de-postback h_01HE7SRDXS8K4MB76WVBCBHASQ=protect360-fraud-and-validation-rules h_01HE7ST20N8ZBFNY2QXW5G44A1=veja-tamb%C3%A9m" />

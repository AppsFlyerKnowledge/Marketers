---
title: Relatórios de dados brutos da SKAN
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2026-10-20T03:49:11Z'
  id: 360014261518
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/360014261518
---
> **Resumo:** os relatórios de dados brutos da SKAN contêm dados em nível de linha gerados após a tradução e decodificação de postbacks recebidos pela AppsFlyer do iOS, assim como postbacks brutos da SKAN. Os dados estão disponíveis através do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker</Anchor> e da <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">Push API</Anchor>. Se o seu plano de assinatura incluir dados brutos, não há necessidade de uma assinatura do Data Locker.

<div id="skan-raw-data-reports" />

## Relatórios de dados brutos da SKAN

Princípios:

* **Os dados são fornecidos via:**
  * **Relatório do Data Locker**
    * **Atenção**! Disponível para contas com assinatura de dados brutos. Ou seja, não há necessidade de uma assinatura do Data Locker. Se você não estiver usando o Data Locker no momento, um usuário administrador deverá configurar o Data Locker e ativar os relatórios da SKAN. Para isso, acesse **relatórios** > **Data Locker**. Selecione os relatórios da SKAN.
    * **Atualização dos dados**: Diariamente. Os dados estão contidos na pasta h=23 da data em que o postback é recebido pela AppsFlyer.
  * **API de push**
    * Atualização de dados: Veja <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">Push API para dados da SKAN</Anchor>.
* **Data de instalação**: derivada da hora de chegada do postback pela AppsFlyer da seguinte forma:
  * se os postbacks forem SKAN V4, a fórmula da data de instalação é: Data de instalação = hora de chegada do postback - [duração acumulada da janela] - [atraso médio do postback].
    * Postback 1: data de instalação = hora de chegada do postback - 48h - 36h
    * Postback 2: data de instalação = hora de chegada do postback - 168h - 84h
    * Postback 3: data de instalação = hora de chegada do postback - 840h - 84h
  * Se os postbacks forem SKAN V3, a fórmula da data de instalação é: Data de instalação = hora de chegada do postback - 36 horas - [intervalo médio do último ativo]. 
    * O padrão [faixa média da última atividade] é de 12 horas.
    * Para um valor de conversão de 0, o último intervalo ativo médio é definido como 0.
  * O Google faz uma estimativa da hora de instalação por conta própria e essa informação é usada pela AppsFlyer. **Atenção:** pode levar até 45 dias para o Google relatar as instalações. <Anchor target="_blank" href="/marketers/pt/docs/get-skan-postback-data-from-google-ads#obtenha-dados-de-postback-skan-do-google-ads">Saiba mais</Anchor>

Os tipos de relatórios disponíveis são:

* **Postbacks de dispositivos:** 1 postback de dispositivo por instalação ou novo download recebido do dispositivo iOS.
* **Dados brutos da SKAN**:
  * a AppsFlyer decodifica e traduz o postback do dispositivo em registros de dados brutos.
  * Cada postback gera um registro de instalação ou novo download e registros de eventos in-app.
  * O número de registros de eventos in-app depende do valor de conversão (CV) da seguinte forma:
    * CV = 0, em branco ou null: nenhum registro no aplicativo é gerado.
    * Faixa de CV:
      * 1-63: para valores ge granularidade total (fine-grained) da janela 1 da SKAN 3 e SKAN 4, esse é o número de registros no aplicativo, dependendo das suas configurações de mensuração.
      * Baixo, médio ou alto: para valores parciais (coarse-grained) da SKAN 4, esse é o número de registros no aplicativo, dependendo das suas configurações de mensuração.

**Por que alguns campos estão vazios?** Isso ocorre por qualquer um dos seguintes motivos:

* Campos de enriquecimento não obrigatórios, como campaign\_name, ad\_network\_campaign\_id, ip que a ad network não forneceu.
* A Apple reteve os dados devido às políticas de limite da Apple. Campos como source\_app\_id, skad\_campaign\_id, skad\_conversion\_value.

<div id="skan-raw-data-report-format-and-content" />

## Formato e conteúdo do relatório de dados brutos da SKAN

<div id="raw-data-report-types" />

<Accordion title="Tipos de relatórios de dados brutos">

<Table>
  <thead>
    <tr>
      <th>
        Tipo de relatório
      </th>
      <th>
        Nome do relatório
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="postback"></span>
        Postback
      </td>
      <td>
        Postbacks
      </td>
      <td>
        Postbacks enviados pelo iOS para a ad network. O postback, depois de ser enriquecido pela ad network, é enviado para a AppsFlyer. [Baixe nosso exemplo de postbacks](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv) (CSV).

        Atenção: postbacks não estão incluídos quando did\_win=false.

        **Nome do tópico no Data Locker**: skad\_postbacks
      </td>
    </tr>
    <tr>
      <td><span id="postback::315d5a62"></span>
        Postback
      </td>
      <td>
        Postbacks copy (direto da Apple)
      </td>
      <td>
        Postbacks enviados diretamente pelo iOS para a AppsFlyer.

        Disponível a partir do iOS 15+ e exige que o anunciante configure o aplicativo para <Anchor target="_blank" href="/marketers/pt/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">enviar o postback vencedor</Anchor> para a AppsFlyer. [Baixe nosso exemplo de cópia de postbacks](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv) (CSV).

        Atenção: esse tópico contém apenas postbacks vencedores.

        **Nome do tópico no Data Locker**: skad\_postbacks\_copy
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event"></span>
        Evento decodificado
      </td>
      <td>
        de instalações
      </td>
      <td>
        **Primeiras instalações do aplicativo**

        SKAN relatou *redownload=false*. Ou seja, é a primeira vez que o usuário, representado pelo ID Apple, fez o download do app.  
        *[Baixe nosso exemplo de instalação](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv) (CSV).*

        **Nome do tópico no Data Locker**: skad\_installs
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5c7e459f"></span>
        Evento decodificado
      </td>
      <td>
        Re-downloads
      </td>
      <td>
        **Reinstalações do aplicativo**

        SKAN relatou *redownload=true*. Ou seja, não é a primeira vez que o usuário, representado pelo ID da Apple, faz download do app. Esse relatório tem a mesma estrutura do relatório de installs.

        **Nome do tópico no Data Locker**: skad\_redownloads
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::b8f2b4a4"></span>
        Evento decodificado
      </td>
      <td>
        https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg
      </td>
      <td>
        https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg

        A partir de 21 de julho de 2021, haverá mudanças na forma como fornecemos dados brutos de eventos in-app, conforme detalhado nas tabelas.

        O número de registros de eventos in-app depende das suas configurações de mensuração.

        [Baixe nosso exemplo de eventos in-app](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv) (CSV).

        **Nome do tópico no Data Locker**: skad\_inapps

        Válido para postbacks do iOS recebidos a partir de 21 de julho de 2021:

        | Tipo de mensuração | Descrição |
        | --- | --- |
        | Resultados | * Receita de um determinado usuário. Se receita > 0, um registro contendo os campos skad\_revenue e event\_name.<br />* Os campos min\_revenue e max\_revenue são preenchidos com seus valores de intervalo de conversão personalizados. |
        | Conversão in-app e eventos de funil | * Um registro para cada evento de conversão exclusivo realizado. O campo event\_name é preenchido de forma correspondente. Se nenhum evento for executado, não há registro.<br />* Os eventos de conversão têm min\_event\_counter = 0 e max\_event\_counter = 1. |
        | Engajamento in-app | Para determinar o número de vezes que um usuário realizou um determinado evento in-app, use a fórmula`[round up (min_event_counter + max_event_counter) / 2]` |

        Válido para postbacks do iOS recebidos até 20 de julho de 2021:

        | Tipo de mensuração | Número de registros | Descrição |
        | --- | --- | --- |
        | Resultados | 0 a 1 | Se receita > 0, um registro contendo os campos skad\_revenue e event\_name. |
        | Conversão | 0-6 | Um registro para cada evento de conversão exclusivo realizado. O campo event\_name é preenchido de forma correspondente. Se nenhum evento for executado, não há registro. |
        | com o anúncios | 0 a 63 | O número de registros representa o número de vezes que o usuário realizou o evento de engajamento. Se o usuário não se engajar, não haverá registros de engajamento. |
        | Personalizado | 0-ilimitado | De acordo com seu esquema de conversão personalizado. |
      </td>
    </tr>
    <tr>
      <td><span id="decoded-event::5dac9cbb"></span>
        Evento decodificado
      </td>
      <td>
        Dimensões de publicidade da SRN
      </td>
      <td>
        * O relatório contém eventos do Meta ads com a granularidade da campanha, adset e anúncios. Cada linha no relatório pode ser um evento de instalação ou evento in-app.
        * A granularidade do adset e dos anúncios não está incluída nos postbacks da SKAN do Meta Ads. Esses dados são exclusivos para esse relatório e não são exibidos no dashboard da SKAN, na Performance API e em outros relatórios da SKAN no Data Locker.
        * O relatório não tem esquema. As opções de seleção de campo do Data Locker não se aplicam.
        * Prática recomendada: Não combine ou compare os dados desse relatório com outros relatórios da SKAN, pois pode haver discrepâncias entre esse relatório, que usa dados decodificados pela SRN, e outros relatórios, que usam dados decodificados pela AppsFlyer. Essas discrepâncias podem ocorrer devido a diferenças de fuso horário, diferenças no esquema da SRN ou eventos in-app mapeados incorretamente para CVs na integração da SRN.
        * <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx">Baixe nosso um exemplo de dimensões de publicidade da SRN</Anchor> (CSV).

        **Nome do tópico no Data Locker**: skad\_srn\_advertising\_dimensions
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-field-format-types" />

<Accordion title="Tipos de formato do campo de dados brutos">

<div id="field-formats" />

#### Formatos de campo

| Nome do formato | Descrição |
| --- | --- |
| String [n] | O comprimento máximo da string. Normalmente, não impomos limitações de comprimento de campo no recebimento dos dados, mas os dados podem ser truncados depois disso. |
| Descrição de tempo | String com o formato `yyyy-mm-dd hh:mm:ss`. Por exemplo, `2019-09-17 00:09:25` |
| Enumeração [n] | Os campos de enumeração só podem conter valores específicos. Por exemplo, a moeda de custo tem 3 caracteres e pode conter apenas códigos de moeda conforme especificado. |
| Carimbo de data/hora | Carimbo de data/hora UNIX de 10 dígitos. Exemplo:<br /><br />4 de agosto de 2020, 07:25 UTC se traduz em `"timestamp": "1596525944"` |
| Booleano | O valor do campo pode ser `TRUE` ou `FALSE`. |
| Inteiro | Número flutuante |
| float | Número flutuante real que pode ter uma vírgula decimal e valores após a vírgula. |

</Accordion>

<div id="fields-available-in-postback-and-postback-copy-reports" />

<Accordion title="Campos disponíveis em relatórios de postback e cópia de postback">

<table><thead><tr><th>Nome do campo</th><th>Fonte de origem ou versão inicial da SKAN</th><th>Descrição</th><th>Formato</th><th>Disponível em cópia de postbacks </th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>Rede de anúncios</td><td>ID da campanha reportado pela ad network à AppsFlyer</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td><p>ad_network_campaign</p><p>_name</p></td><td>Rede de anúncios</td><td><p>Nome da campanha informado pela ad network à AppsFlyer.</p></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>ad_network_timestamp</td><td>Rede de anúncios</td><td><p>Hora em que a ad network recebeu o postback.</p><p>No caso do Google Ads, o tempo é derivado da hora do último clique informado pelo Google.</p></td><td>Carimbo de data/hora</td><td>Não</td></tr><tr><td>ativado</td><td>A AppsFlyer</td><td>App ID (aplicativo do anunciante) com prefix ID.</td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>cidade</td><td>A AppsFlyer</td><td>A partir de 30 de agosto de 2021, sempre null </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>código_país</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>dma</td><td> </td><td>A partir de 30 de agosto de 2021, sempre null </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>postal_code</td><td> </td><td>A partir de 30 de agosto de 2021, sempre null  </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>Região</td><td>A AppsFlyer</td><td>De acordo com o country_code informado</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_ad_network_id</td><td>1.0 </td><td>Algumas SRNs não compartilham seu ID e o campo é deixado em branco. Por exemplo, X Ads. </td><td>Sequência de caracteres</td><td>Sim </td></tr><tr><td>skad_attribution_signature</td><td>1.0</td><td> </td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>skad_campaign_id</td><td>1.0</td><td>ID da campanha utilizada para publicar o anúncio. Intervalo 0-100</td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>skad_conversion_value</td><td>2.0 </td><td><p>Valor de conversão reportado pelo iOS. Intervalo 0-63.</p><p>Se null, o iOS não preencheu o campo\*\* </p></td><td>Número flutuante</td><td>Sim</td></tr><tr><td>skad_redownload</td><td>2.0</td><td>Se true, o aplicativo foi baixado novamente</td><td>Booleano</td><td>Sim</td></tr><tr><td>skad_source_app_id</td><td>2.0</td><td><p>Site ID. O aplicativo que publica o anúncio. Esse campo é idêntico ao source_app_id.</p><p>O preenchimento do campo depende dos limites de privacidade\*\*</p></td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>skad_transaction_id</td><td>1.0</td><td> </td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>skad_version</td><td>2.0</td><td> </td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>timestamp</td><td>Rede de anúncios</td><td>Horário em que a AppsFlyer recebeu o postback da SKAN. </td><td>Timestring</td><td>Sim</td></tr><tr><td>ad_network_name</td><td>Rede de anúncios</td><td><p>Código do país </p><ul><li>Se esse campo estiver vazio, significa que a ad network não o preencheu (ou não pôde preencher).</li><li>Pode determinar o nome da ad network utilizando o skad_ad_network_id. Use <a href="./skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks" target="_blank">essa tabela</a> para isso. </li></ul></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>ip</td><td> </td><td><p>Endereço IP na mensagem HTTP do dispositivo iOS que envia o postback.</p><p>Esse campo é preenchido se a ad network nos fornecer o endereço.</p><p>Atenção! O SDK não obtém essa informação.</p></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_app_id</td><td>1.0</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>source_app_id</td><td>A AppsFlyer</td><td>Site ID. O aplicativo que publica o anúncio. Esse campo é igual ao skad_source_app_id</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>ad_network_adset_id</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>ad_network_adset_name</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>ad_network_ad_name</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>ad_network_ad_id</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>did_win</td><td>3.0 (iOS 14.6)</td><td><p>Usado para distinguir entre campanhas <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">que contribuem ou são atribuídas</a> à instalação. </p><ul><li>Se true, a campanha é atribuída como responsável pela instalação.</li><li>Se o valor for false, a campanha é reconhecida como contribuindo para a instalação, mas não é incluída em dashboards ou relatórios SKAN.</li><li>Se null, o iOS não preencheu o campo devido a uma <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">versão legada do iOS ou da SKAdNetwork</a>.</li></ul></td><td>Booleano</td><td>Sim</td></tr><tr><td>fidelity_type</td><td>2.2 (iOS 14.5)</td><td><p>Diferencia as opções <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">de exibição de anúncios</a> que afetam a atribuição. Indicado pelos valores 0 e 1 da seguinte forma: </p><ul><li>Anúncios visualizados (0)</li><li>Anúncios renderizados pelo StoreKit (1)</li></ul><p>Ignore o valor do campo se a versão da SKAN for anterior à 2.2</p></td><td>Inteiro</td><td>Sim</td></tr><tr><td>ad_network_source_app_id</td><td>Rede de anúncios</td><td><span>Publisher app ID informado pela ad network. Use-o para ajudar a reconciliar custos, reportado pela ad network. O aplicativo do publisher fornece a base para esses dados. </span></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>ad_network_channel</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>af_prt</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0 (iOS 16.2)</td><td><ul><li>O valor representa a janela SKAN: <code>0</code>, <code>1</code> ou<code>2</code>.</li><li>Para SKAN 3, o valor é <code>0</code> </li></ul></td><td>Inteiro</td><td>Sim</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li>O valor pode ser <code>low</code>,<code>medium</code> ou<code>high</code>.</li><li>Para SKAN 3, o valor é <code>null</code>.</li></ul></td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>O valor pode ter até 4 dígitos.</li><li>Para SKAN 3, o valor é <code>null</code>. </li></ul></td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>O valor representa a origem dos anúncios web atribuídos.</li><li>Para SKAN 3, o valor é <code>null</code>.</li></ul></td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>ad_network_creative</td><td>Rede de anúncios</td><td><ul><li>O valor é baseado no enriquecimento de dados recebido da ad network.</li><li>Para SKAN 3, o valor é <code>null</code>.</li></ul></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td colspan="4">\*\* A Apple determina se o campo é preenchido usando um mecanismo de limite de privacidade </td><td> </td></tr></tbody></table>

</Accordion>

<div id="fields-available-in-decoded-event-reports" />

<Accordion title="Campos disponíveis em relatórios de eventos decodificados">

<table><thead><tr><th>Nome do campo</th><th>Fonte</th><th>Descrição</th><th>Formato</th><th>Incluído no relatório de dimensões de publicidade SRN</th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>Rede de anúncios</td><td>ID da campanha reportado pela rede de anúncios à AppsFlyer</td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>ad_network_campaign<br/>_name</td><td>Rede de anúncios</td><td>Nome da campanha reportado pela ad network à AppsFlyer</td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>ad_network_timestamp</td><td>Rede de anúncios</td><td>sem valores No Google Ads, este campo é preenchido, mas o valor é um tempo estimado de instalação, não o momento real de recebimento do postback. Consulte <a href="./get-skan-postback-data-from-google-ads" target="_blank">Obter dados de postback do SKAN do Google Ads</a> para mais detalhes.</td><td><p>Carimbo de data/hora</p><p>(string de tempo para relatório de dimensões de publicidade SRN)</p></td><td>Sim</td></tr><tr><td>ativado</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>O app ID (aplicativo do anunciante)</td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>cidade</td><td> </td><td>A partir de 30 de agosto de 2021, sempre null </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>código_país</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>dma</td><td> </td><td>A partir de 30 de agosto de 2021, sempre null </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>nome_do_evento</td><td>A AppsFlyer</td><td><p>Nome do evento in-app conforme configurado na AppsFlyer.</p><p>Para a SRN ___report, esse é o nome do evento in-app conforme configurado no Meta ads.</p></td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>evento_uuid</td><td>A AppsFlyer</td><td>Um identificador aleatório e único que permite aos parceiros identificar postbacks duplicados.</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>install_date</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>Estimado pela AppsFlyer com base na hora de chegada do postback.</td><td>Descrição de tempo</td><td>Não</td></tr><tr><td>install_type</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>Novas instalações</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>ip</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td><p>O endereço IP na mensagem HTTP do dispositivo iOS que está enviando o postback.</p><p>Esse campo é preenchido se a ad network nos fornecer o endereço.</p><p>Atenção! O SDK não obtém essa informação. </p></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>fonte_de_mídia</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>Ad network atribuída usando nomes de rede da AppsFlyer</td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>postal_code</td><td> </td><td>A partir de 30 de agosto de 2021, sempre null </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>Região</td><td>A AppsFlyer</td><td>Determinado de acordo com o country_code</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_ad_network_id</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>ID da rede de anúncios para a qual o postback foi enviado</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_ambiguous_event (obsoleto com SKAN 4+)</td><td>A AppsFlyer</td><td><p>Se verdadeiro (true), o postback do iOS foi recebido durante as primeiras 72 horas depois que um anunciante alterou as configurações de SKAN no dashboard. Devido aos diversos timers usados pela SKAN, a AppsFlyer não consegue mapear o evento com precisão.</p><ul><li>Indisponível na SKAN 4 e versões mais recentes</li></ul></td><td>Booleano</td><td>Não</td></tr><tr><td>skad_attribution_signature</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_campaign_id</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>ID da campanha utilizada para publicar o anúncio. Intervalo 0-100</td><td>Inteiro</td><td>Não</td></tr><tr><td>skad_conversion_value</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td><p>Valor de conversão reportado pelo iOS. Intervalo 0-63.</p><p>Se null, o iOS não preencheu o campo\*\*</p></td><td>Inteiro</td><td>Não</td></tr><tr><td>skad_mode</td><td>A AppsFlyer</td><td><p>O modo de mensuração de conversão usado para decodificar o postback do iOS. Opções:</p><ul><li>custom_decode</li><li>revenue</li><li>events</li><li>skan4</li><li>custom_encode</li><li>engagement</li></ul></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_redownload</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>Se verdadeiro, a aplicação foi descarregada novamente</td><td>Booleano</td><td>Não</td></tr><tr><td>skad_receita</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>Montante da receita do evento em USD.</td><td>float</td><td>Não</td></tr><tr><td>skad_source_app_id</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td><p>Site ID - o aplicativo que publica o anúncio.</p><p>O preenchimento do campo depende dos limites de privacidade\*\*</p></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_transaction_id</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>-</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_version</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>-</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>timestamp</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td><p>Horário em que a AppsFlyer recebeu o postback da SKAN.</p><p>Para Google Ads e Meta ads, este é o momento em que a AppsFlyer obtém os dados da API do Google e do Meta ads, respectivamente.</p></td><td><p>Carimbo de data/hora</p><p>(string de tempo para relatório de dimensões de publicidade SRN)</p></td><td>Sim</td></tr><tr><td>event_value</td><td>S2S</td><td><p>Valor padrão: null</p><p>Contém uma string definida por apps que implementam descodificação personalizada.</p><p>Os anunciantes consomem isso em seus sistemas. A AppsFlyer não faz uso disso. </p></td><td>Sequência (JSON)</td><td>Não</td></tr><tr><td>ad_network_adset_id</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>ad_network_adset_name</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>ad_network_ad_name</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>ad_network_ad_id</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>skad_did_win (1)</td><td>3.0 (iOS 14.6)</td><td><p>Usado para distinguir entre campanhas <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">que contribuem ou são atribuídas</a> à instalação. </p><ul><li>Se true, a campanha é atribuída como responsável pela instalação.</li><li>Se o valor for false, a campanha é reconhecida como contribuindo para a instalação, mas não é incluída em dashboards ou relatórios SKAN.</li><li>Se null, o iOS não preencheu o campo devido a uma <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">versão legada do iOS ou da SKAdNetwork</a>.</li></ul></td><td>Booleano</td><td>Não</td></tr><tr><td>skad_fidelity_type (1)</td><td>2.2 (iOS 14.5)</td><td><p>Diferencia as opções <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">de exibição de anúncios</a> que afetam a atribuição. Indicado pelos valores 0 e 1 da seguinte forma: </p><ul><li>Anúncios visualizados (0)</li><li>Anúncios renderizados pelo StoreKit (1)</li></ul><p>Ignore o valor do campo se a versão da SKAN for anterior à 2.2</p></td><td>Inteiro</td><td>Sim</td></tr><tr><td>ad_network_source_app_id (1)</td><td>Rede de anúncios</td><td><span>Publisher app ID informado pela ad network. Use-o para ajudar a reconciliar custos, reportado pela ad network. A base desses dados é fornecida pela app do publisher.</span></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>ad_network_channel (1)</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>af_prt (1)</td><td>Rede de anúncios</td><td> </td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>min_revenue </td><td>A AppsFlyer</td><td>Ver nota (4)</td><td>Número real</td><td>Não</td></tr><tr><td>max_revenue </td><td>A AppsFlyer</td><td>Ver nota (4)</td><td>Número real</td><td>Não</td></tr><tr><td>event_revenue</td><td>A AppsFlyer</td><td>Fórmula: [soma dos valores para o evento específico em USD]/[Número de eventos que ocorreram em um dia específico]</td><td>float</td><td>Sim</td></tr><tr><td>mínimo_contador_evento</td><td>A AppsFlyer</td><td>Use para calcular o número de vezes que um usuário realiza um evento. Ver nota (3)</td><td>Inteiro</td><td>Não</td></tr><tr><td>máximo_contador_evento</td><td>A AppsFlyer</td><td>Ver nota (3)</td><td>Inteiro</td><td>Não</td></tr><tr><td>mínimo_tempo_pós_instalação</td><td>A AppsFlyer</td><td>Ver nota (5)</td><td>Inteiro</td><td>Não</td></tr><tr><td>máximo_tempo_pós_instalação</td><td>A AppsFlyer</td><td>Ver nota (5)</td><td>Inteiro</td><td>Não</td></tr><tr><td>af_attribution_flag</td><td>A AppsFlyer</td><td>Quando o mecanismo do Single Source of Truth (SSOT) está ativo: Se true, a instalação foi atribuída tanto pela AppsFlyer quanto pela SKAN. Se false, a instalação não foi atribuída pela AppsFlyer. Se o valor de skad_conversion for nulo, a flag será true ou false (com base na <a href="./skan-modeled-data#null-conversion-values" target="_blank">modelagem</a>).</td><td>Booleano</td><td>Não</td></tr><tr><td>measurement_window</td><td>A AppsFlyer</td><td>Duração da janela de atividade. Padrão 24 horas. </td><td>Inteiro</td><td>Não</td></tr><tr><td>Intervalo</td><td>A AppsFlyer</td><td>Intervalos da janela de atividades. </td><td>Inteiro</td><td>Não</td></tr><tr><td>user_agent</td><td>A AppsFlyer</td><td>User agent do dispositivo</td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td>skad_postback_sequence_index</td><td>4.0 (iOS 16.2)</td><td><ul><li>O valor representa a janela SKAN: <code>0</code>, <code>1</code> ou<code>2</code>.</li><li>Para SKAN 3, o valor é <code>0</code> </li></ul></td><td>Número flutuante</td><td>Sim</td></tr><tr><td>skad_coarse_conversion_value</td><td><p>4.0 (iOS 16.2)</p></td><td><ul><li>O valor pode ser <code>low</code>,<code>medium</code> ou<code>high</code>.</li><li>Para SKAN 3, o valor é <code>null</code>.</li></ul></td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>skad_source_identifier</td><td>4.0 (iOS 16.2)</td><td><ul><li>O valor pode ter até 4 dígitos.</li><li>Para SKAN 3, o valor é <code>null</code>. </li></ul></td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>skad_source_domain</td><td>4.0 (iOS 16.2)</td><td><ul><li>O valor representa a origem dos anúncios web atribuídos.</li><li>Para SKAN 3, o valor é <code>null</code>.</li></ul></td><td>Sequência de caracteres</td><td>Sim</td></tr><tr><td>ad_network_creative</td><td>Rede de anúncios</td><td><ul><li>O valor é baseado no enriquecimento de dados recebido da ad network.</li><li>Para SKAN 3, o valor é <code>null</code>.</li></ul></td><td>Sequência de caracteres</td><td>Não</td></tr><tr><td colspan="4"><p>\*\* A Apple determina se o campo é preenchido usando um mecanismo de limite de privacidade</p><p>(1) A partir de 2 de junho de 2021, o campo será adicionado aos relatórios, mas não será necessariamente preenchido.</p><p>(3) Para determinar o número de vezes que um usuário realizou um determinado evento in-app, use a fórmula<code>[round up (min_event_counter + max_event_counter) / 2]</code> Atenção! Observação! <mark>Você deve arredondar para o número inteiro mais próximo.</mark><br/>Exemplo:<br/>A. <br/>Exemplo:<br/>A. <br/>Exemplo:<br/>A. Se min = 0 e max = 1, a média é 0,5; arredondando, obtém-se 1.<br/>B. B. B. Se min = 5 e max = 10, a média é 7,5; arredondando, obtém-se 8.</p><p>(4) A receita é sempre apresentada no campo <code>skad_revenue</code>. Se você usar a SKAN 4 ou o <a href="./skan-conversion-studio" target="_blank">modo personalizado</a>, o intervalo associado ao evento usado para calcular skad_revenue é descrito por min_revenue e max_revenue.</p><p>(5)</p><ul><li>Na conversão personalizada: A AppsFlyer calcula o tempo de instalação como o tempo de chegada do postback menos 36 horas, menos a média (min_time_post_install + max_time_post_install). No entanto, se CV=0, a média (min_time_post_install + max_time_post_install) é considerada 0. </li><li>Na conversão de decodificação: O min_time_post_install é uma hora a menos do que o definido em max_time_post_install, igualando <a href="./skan-cv-decode-map-your-cv-to-events#decode-csv-file-specification" target="_blank">hours_from_install</a> definido por si no mapeamento de conversão Decode. </li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Acesso à ad network | As ad networks recebem postbacks |
| Acesso de agência | Indisponível |
| Transparência das agências | N/D |
| Fuso horário | UTC |
| Moeda | USD |
| Dados orgânicos | Baseado em dados de eventos do SDK. Por exemplo, as métricas de instalação orgânica são calculadas assim: Dados de todas as instalações reportadas pelo SDK menos as instalações não orgânicas reportadas pela SKAN. |
| Dados não orgânicos | Com base em postbacks da SKAN |
| Atualização dos dados | Diária. O tempo da SKAN significa que o iOS informa sobre uma instalação de 24 a 48 horas após o fechamento da janela. |
| Histórico de dados | Limitado à janela de disponibilidade do Data Locker. |
| Acesso do usuário à conta | Disponível. De acordo com as permissões da conta |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#reporting-options">Relatórios SKAN disponíveis (guia da solução SKAN)</Anchor>

<div data-zendesk-anchors="skan-raw-data-reports=relat%C3%B3rios-de-dados-brutos-da-skan 01H8XHATZB2G6YZ9AJNPRZS59Y=relat%C3%B3rios-de-dados-brutos-da-skan skan-raw-data-report-format-and-content=formato-e-conte%C3%BAdo-do-relat%C3%B3rio-de-dados-brutos-da-skan 01H8XHATZCJQZTZF0Y5P18XMEA=formato-e-conte%C3%BAdo-do-relat%C3%B3rio-de-dados-brutos-da-skan 01H8XHATZCR5BC2P5TSQTMDY5Q=raw-data-report-types 01H8XHATZC0MST5ASGWDGGK2R8=raw-data-field-format-types field-formats=formatos-de-campo 01H8XHATZCZMNGK72DDE5HS6E9=formatos-de-campo 01H8XHATZC24DH4AYB2C523JDH=fields-available-in-postback-and-postback-copy-reports 01H8XHATZCNXVG0E3MZ9H68AA1=fields-available-in-decoded-event-reports additional-information=informa%C3%A7%C3%B5es-adicionais 01H8XHATZD9D7JBHTFZ095EBD5=informa%C3%A7%C3%B5es-adicionais 01H8XHATZDMV0VN4BDTECGF91K=traits-and-limitations h_01HDNYQBVZP0A6SQASGDRFVFGP=veja-tamb%C3%A9m" />

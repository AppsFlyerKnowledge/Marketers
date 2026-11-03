---
title: Configuração da campanha do Yahoo Japan Search Ads Japão
metadata:
  keywords:
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
  created_at: '2021-12-02T10:07:00Z'
  edited_at: '2026-09-16T00:25:37Z'
  id: 4412602890641
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/4412602890641
---
> **Em resumo:** Yahoo Japan Search Ads, um parceiro de network de auto-relato (SRN) que combina publicidade e análises.
>
> * Em 15 de dezembro de 2021, a integração legada com o Yahoo Japan Search Ads, *yahoojapansearch\_int,* foi substituída por uma nova integração, *yjsearch\_int*. Saiba como [começar a trabalhar com a nova API](/docs/yahoo-japan-search-ads-campaign-configuration#integrating-with-the-new-api).

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yjsearch.png" width="121px" />

## Princípios da integração com o Yahoo Japan Search Ads Japão

A integração da AppsFlyer com o Yahoo Japan Search Ads é relevante apenas para aplicativos Android. 

A integração usa um ID de link para a mensuração de conversões e se baseia em eventos de conversão predefinidos no Yahoo Japan Search Ads. Você pode mapear eventos in-app, como assinaturas e compras, para esses eventos. Isso permite a mensuração e o relatório de conversões entre a AppsFlyer e o Yahoo Japan Search Ads.

<div id="comparing-the-legacy-and-new-integration" />

<Accordion title="Comparação entre a integração legada e a nova integração">

Suporte a recursos da API do Yahoo Japan Search Ads:

| Características | Legada (yahoojapansearch\_int) | Novidade<br /><br />(yjsearch\_int) |
| --- | --- | --- |
| Conversão de instalação (somente clique) | Yes | Yes |
| Conversão in-app | Sem | Yes |

</Accordion>

<div id="integrating-with-the-new-api" />

<Accordion title="Integração com a nova API">

**Para ativar a integração com a nova API:**

1. No dashboard do Yahoo Japan Search Ads Japão, <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">gere um ID de link</Anchor>. Você deve selecionar a AppsFlyer como sua MMP.
2. Na AppsFlyer, [configure a integração com o Yahoo Japan Search Ads Japão](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).
3. [Mapeie os eventos in-app](/docs/yahoo-japan-search-ads-campaign-configuration#2) que você quer mensurar e <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">crie novas análises de conversão na Campaign Management Tool</Anchor> no Yahoo Japan Search Ads.

</Accordion>

<div id="data-sharing-between-appsflyer-and-yahoo-japan-search-ads" />

<Accordion title="Compartilhamento de dados entre a AppsFlyer e o Yahoo Japan Search Ads Japão">

Envie postbacks ao Yahoo Japan Search Ads Japão relacionados a conversões e eventos in-app. Os eventos in-app são mapeados para eventos de conversão predefinidos usados pelo Yahoo Japan Search Ads Japão para otimizar e atualizar relatórios de performance. Você faz o mapeamento como parte das configurações da integração.

Considere a tabela de mapeamento a seguir no contexto dos eventos in-app da AppsFlyer (seu aplicativo) e do mapeamento de eventos predefinidos do Yahoo Japan Search Ads Japão.

| Evento in-app da AppsFlyer | Tipo de evento do aplicativo do Yahoo Japan Search Ads |
| --- | --- |
| af\_compra | in\_app\_purchase |
| af\_app\_opened | session\_start |
| af\_search | view\_search\_results |
| af\_content\_view | view\_item |
| af\_list\_view | view\_item\_list |
| af\_add\_to\_cart | adicionar\_ao\_carrinho |
| af\_travel\_booking | ecommerce\_purchase |
| Qualquer evento in-app | Se você tiver eventos adicionais, mapeie-os para o evento personalizado. |

**Dados fornecidos à AppsFlyer pelo Yahoo Japan Search Ads**

Quando o Yahoo Japan Search Ads reivindica uma conversão, ele nos fornece os parâmetros do canal de mídia listados na tabela. Estes parâmetros preenchem relatórios analíticos e de dados brutos. A tabela a seguir contém o mapeamento entre os parâmetros do Yahoo Japan Search Ads e da AppsFlyer.

#### Mapeamento do canal de mídia entre Yahoo Japan Search Ads e AppsFlyer

| Yahoo Japan Search Ads | A AppsFlyer |
| --- | --- |
| timestamp | attributed\_touch\_time |
| campaign\_tracking\_id | id\_da\_campanha |
| ad\_group\_tracking\_id | id\_conjunto\_de\_anúncios |
| ad\_tracking\_id | id\_anúncio |
| palavra-chave | keywords |
| match\_type | keyword\_match\_type |
| account\_id | network\_account\_id |

</Accordion>

## Procedimentos de integração

Você pode integrar o Yahoo Japan Search Ads usando uma única entidade: diretamente como anunciante ou por meio de uma agência.  
Preencha as seções da seguinte maneira:

* [Preencher uma vez — obrigatório] [Integração do anunciante do Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).
* [Opcional por agência] [Integração da agência](/docs/yahoo-japan-search-ads-campaign-configuration#agency-integration).

<div id="yahoo-japan-search-ads-integration-tab-sections" />

<Accordion title="Yahoo Japan Search Ads — seções da guia de integração">

<Table>
  <thead>
    <tr>
      <th>
        Etapa
      </th>
      <th>
        Secção
      </th>
      <th>
        A descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="1"></span>
        1
      </td>
      <td>
        Ativar parceiro
      </td>
      <td>
        **Pré-requisitos:**

        Obtenha o <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">ID do link</Anchor> do Yahoo Japan Search Ads.

        **Para ativar a integração de atribuição de aplicativo do Yahoo Japan Search Ads:**

        1. No AppsFlyer, no menu lateral, selecione **Collaborate** > **Partner Integrations** > **Partner Marketplace**.
        2. Pesquise por **Yahoo! Search Ads (Yahoo! JAPAN Sponsored Search) - New API**, e selecione-o.
        3. Verifique se **yjsearch\_int** é exibido na URL. Caso contrário, você selecionou o parceiro integrado errado.
        4. No separador **Integração**, ligue o **Ativar parceiro**.  
           **Observação:** O botão de alternância deve estar <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">(ativado)</Anchor> pelo tempo em que você trabalhar com o parceiro.
        5. No campo ID do link, cole o ID do link mencionado nos pré-requisitos.
        6. [Opcional] Alterações nas configurações padrão da janela de instalação de <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">lookback de clique</Anchor>. O padrão do Yahoo Japan Search Ads é de 7 dias. Para minimizar discrepâncias [melhores práticas], alinhe-se ao padrão do Yahoo Japan Search Ads.
        7. Clique em **Guardar integração**.
        8. No **Yahoo Japan Search Ads**, defina as novas configurações de conversão como "app\_first\_open". Saiba mais sobre a configuração no Yahoo Japan Search Ads.
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        Mapeie eventos in-app da AppsFlyer para eventos do Yahoo Japan Search Ads
      </td>
      <td>
        **Para mapear os eventos predefinidos do Yahoo Japan Search Ads para eventos in-app da AppsFlyer:**

        1. Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas**.
        2. Selecione **Yahoo! Anúncios de pesquisa (Yahoo! JAPÃO Sponsored Search) - Nova API**.
        3. Ative **Postback de eventos in-app.**
        4. Clique em **Adicionar evento** para adicionar um evento do aplicativo à lista.
        5. Complete os parâmetros necessários.
        6. Clique em **Salvar integração.**
        7. No **Yahoo Japan Search Ads**, defina as novas configurações de conversão para corresponder aos eventos in-app configurados. Saiba mais sobre a configuração no Yahoo Japan Search Ads.

        | Nome do parâmetro | A descrição |
        | --- | --- |
        | <span id="sdk-event-name"></span>Nome do evento do SDK | O nome do evento, conforme recebido pela AppsFlyer por meio do SDK integrado ao aplicativo ou por meio de eventos de servidor para servidor. |
        | <span id="partner-event-identifier"></span>Identificador de evento do parceiro | Os eventos predefinidos do Yahoo Japan Search Ads. As configurações de mapeamento padrão sugeridas estão listadas na tabela da seção anterior. |
        | <span id="sending-option"></span>Opção de envio | Selecione a opção de envio para o evento:<br /><br />* **Somente este parceiro:** para eventos provenientes apenas de usuários atribuídos ao Yahoo Japan Search Ads.<br />* **Todos os canais de mídia, incluindo orgânico:** tenha toda a sua base de usuários disponível para ser reportada ao Yahoo Japan Search Ads. |
        | <span id="send-revenue"></span>Send Revenue (Enviar receita) | * **Sem valores & sem receita:** envia apenas o evento em si sem o valor do evento.<br />* **Valores & sem receita:** envia todos os parâmetros, com exceção do valor da receita.<br />* **Valores & receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento). |

        Considerações:

        * Os nomes dos eventos são sensíveis a maiúsculas e minúsculas. Para evitar discrepâncias, certifique-se de usar o nome de evento correto para todas as fontes de mídia e versões do aplicativo.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="agency-integration" />

<Accordion title="Integração com agências">

As agências podem executar campanhas com o Yahoo Japan Search Ads em seu nome.

#### Configuração da agência

| Procedimento realizado por | Procedimento |
| --- | --- |
| AppsFlyer | <ol><li>Verifique se você concluiu a [integração de anunciante do Yahoo Japan Search Ads](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections).</li><li>Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas**.</li><li>Selecione uma agência.</li><li>Vá para a **aba Permissões** e ative **permissões de agência**.</li></ol> |
| Acesso para | <ol><li>Na AppsFlyer, acesse **Colaborar** > **Integrações de parceiros** > **Integrações ativas**.</li><li>Selecione **Yahoo! Anúncios de pesquisa (Yahoo! JAPAN Sponsored Search) - Nova API.**</li><li>Acesse a aba de **Integração**.</li><li>Verifique se a opção **Ativar parceiro** está habilitada. Se não for esse o caso, o anunciante deve concluir a [integração do anunciante do Yahoo Japan Search Ads.](/docs/yahoo-japan-search-ads-campaign-configuration#yahoo-japan-search-ads-integration-tab-sections)</li><li>Verifique se as configurações restantes, como as janelas de lookback e o mapeamento de eventos in-app, estão corretas. Se necessário, peça para o anunciante realizar alterações.</li><li>Insira seu **ID do cliente do Yahoo Japan Search Ads**. O ID está disponível na <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=36745&o=default#:~:text=How%20to%20check%20Account%20ID">ferramenta de gerenciamento de campanhas</Anchor>. Observe que apenas um ID do cliente pode ser conectado.</li><li>Clique em **Guardar**.</li></ol> |

</Accordion>

## Procedimentos auxiliares

<div id="get-the-app-link-id" />

<Accordion title="Obter o ID do link do Aplicativo">

**Para obter o ID do link do Campaign Manager,** <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/search/articledetail?lan=en&aid=44102">consulte a documentação do Yahoo Japan Search Ads.</Anchor>

</Accordion>

<div id="create-a-new-yahoo-japan-search-ads-predefined-event" />

<Accordion title="Criar um novo evento predefinido do Yahoo Japan Search Ads">

**Para criar um novo evento predefinido,** consulte as <Anchor target="_blank" href="https://ads-help.yahoo.co.jp/yahooads/ss/articledetail?lan=en&aid=6380&o=default#:~:text=Create%20conversion%20analytics%20%5BCampaign%20Management%20Tool%5D">instruções do Yahoo Japan Search Ads</Anchor>.

</Accordion>

<div id="yahoo-japan-search-ads-discrepancies" />

<Accordion title="Discrepâncias do Yahoo Japan Search Ads">

Consulte a tabela a seguir para saber mais sobre as discrepâncias e como minimizá-las.

**Diferenças em modelos de atribuição**

| Causa | A descrição | Dica da AppsFlyer |
| --- | --- | --- |
| Mapeamento incorreto de eventos in-app | O mapeamento entre o AppsFlyer e o Yahoo Japan Search Ads não está correto. | <ul><li>Verifique o ID do link,</li><li>Verifique se os eventos in-app da AppsFlyer estão mapeados corretamente para os eventos do Yahoo Japan Search Ads.</li></ul> |

</Accordion>

<div data-zendesk-anchors="yahoo-japan-search-ads-integration-principles=princ%C3%ADpios-da-integra%C3%A7%C3%A3o-com-o-yahoo-japan-search-ads-jap%C3%A3o h_01HH1RS8ZJSWTCDY5QBN3E041D=princ%C3%ADpios-da-integra%C3%A7%C3%A3o-com-o-yahoo-japan-search-ads-jap%C3%A3o h_01HH1RS8ZJATXC84X8C74B95C8=comparing-the-legacy-and-new-integration h_01HH1RS8ZJWESR21H0BE7S3HV5=integrating-with-the-new-api h_01HH1RS8ZJM3EHGMKJF409QPTX=data-sharing-between-appsflyer-and-yahoo-japan-search-ads yahoo-japan-search-adsappsflyer-media-source-mapping=mapeamento-do-canal-de-m%C3%ADdia-entre-yahoo-japan-search-ads-e-appsflyer h_01HH1RS8ZM0ZEPJ7ZJYY286J2F=mapeamento-do-canal-de-m%C3%ADdia-entre-yahoo-japan-search-ads-e-appsflyer integration-procedures=procedimentos-de-integra%C3%A7%C3%A3o h_01HH1RS8ZMAFNAGWAZDWX5PJT4=procedimentos-de-integra%C3%A7%C3%A3o yahoo-japan-search-ads%E2%80%94integration-tab-sections=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMS287YR3K9CW7HN37=yahoo-japan-search-ads-integration-tab-sections h_01HH1RS8ZMGTJQB3ANAJB8MY52=agency-integration agency-setup=configura%C3%A7%C3%A3o-da-ag%C3%AAncia h_01HH1RS8ZMCBT0NJ5Z23ZAK6TV=configura%C3%A7%C3%A3o-da-ag%C3%AAncia subsidiary-procedures=procedimentos-auxiliares h_01HH1RS8ZMKHBA000CEX6KHQJK=procedimentos-auxiliares h_01HH1RS8ZMWPS69ASK452QAXAK=get-the-app-link-id h_01HH1RS8ZMXVXH745DP5Q8SZ3D=create-a-new-yahoo-japan-search-ads-predefined-event h_01HH1RS8ZM5SXTQDPJ5E9YEKPS=yahoo-japan-search-ads-discrepancies" />

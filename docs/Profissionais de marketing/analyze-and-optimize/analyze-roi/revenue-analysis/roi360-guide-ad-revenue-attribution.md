---
title: Guia ROI360 - atribuição de receita de anúncios
metadata:
  keywords:
    - ad revenue
    - ad monetization
    - monetization
    - Advertisers
    - adrevenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2016-12-12T10:53:27Z'
  edited_at: '2026-10-27T03:34:40Z'
  id: 217490046
  locale: pt
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/pt/articles/217490046
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Atribua a receita de anúncios para completar a visualização de performance do LTV (lifetime value).

![Attributes_ad_revenue.png](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)

## Atribuição de receita de anúncios

* Os anúncios são exibidos no aplicativo em banners, murais de ofertas, intersticiais etc. e geram receita de anúncios.
* A receita de anúncios, combinada com compras in-app e receita de assinaturas, fornece a visão completa do LTV do usuário. Ao relacionar o LTV do usuário à campanha de gasto de mídia, você pode determinar o ROI e analisá-lo na plataforma.

**Dados de receita de anúncios atribuída**:

* É obtida das plataformas de mediação ou networks de monetização de anúncios por meio de APIs de servidor ou de um SDK de reportar incorporado ao aplicativo (incluindo iOS 14).
* É atribuída ao canal de mídia que originalmente trouxe o usuário, por exemplo:
  * Um usuário vê um anúncio da Network A e baixa o seu aplicativo.
  * O anúncio é exibido dentro do aplicativo.
  * A receita de anúncios é atribuída à Network A (responsável pela aquisição de usuários), independentemente de quem publicou o anúncio.
* A granularidade dos relatórios depende da integração da rede de monetização e do tipo de atribuição da receita de anúncios.

<Accordion title="Tipos de integração para atribuição de receita de anúncios">

A precisão e a atualização dos dados dependem do tipo de integração da atribuição de receita de anúncios, como mostrado na tabela a seguir.

**Atenção:** Diferentes tipos de integração do SDK exigem a ação de um desenvolvedor. Para a integração S2S, é necessário ter as credenciais de rede corretas.

| Tipo de integração | Descrição |
| --- | --- |
| [Nível agregado](#h_01JYRKB8Q3D3W0FM75VH78XQTS) via S2S API | <ul><li>A AppsFlyer recebe a receita diária, discriminada por geo.</li><li>A receita efetiva por ação (eRPA) é obtida através da divisão da receita pelo número de vezes em que ocorre um evento de disparo.</li><li>Os eventos de disparo podem ser aberturas do app ou eventos in-app específicos definidos no aplicativo.</li><li>Se você estiver usando uma plataforma de mediação, desative as integrações de receita de anúncios dos parceiros de monetização mediados pela plataforma antes de ativar a integração de receita de anúncios com a plataforma. Caso contrário, você terá dados duplicados.</li><li>Os dados não estão disponíveis nos Relatórios de dados brutos e não podem ser compartilhados com ad networks via postbacks ou sinais de UA.</li></ul> |
| [Nível do dispositivo](#01ECF1PZ36R9W7A0X4WBR95JDS) via S2S API | <ul><li>A plataforma de mediação ou monetização relata a receita por usuário no nível do dispositivo. Nem todas as redes são compatíveis com a granularidade a nível de usuário.</li><li>Essa receita é atribuída à fonte de mídia que trouxe o usuário. Ou seja, a atribuição da receita publicitária da AppsFlyer segue as regras de atribuição encontradas na plataforma, incluindo regras de atribuição de retargeting.</li><li>Se você estiver usando uma plataforma de mediação, certifique-se de desativar as integrações de receita de anúncios para parceiros de monetização mediados pela plataforma antes de ativar a integração de receita de anúncios com a plataforma. Caso contrário, você terá dados duplicados.</li><li>O device-level via API S2S inclui 100% da receita de anúncios e oferece a maior precisão de dados entre os tipos de integração de receita de anúncios.</li><li>Os dados estão disponíveis nos Relatórios de dados brutos e podem ser compartilhados com ad networks somente via <Anchor target="_blank" href="/marketers/pt/docs/share-ad-revenue-data-with-partners">sinais de UA.</Anchor></li><li>Para Android: Certifique-se de que os desenvolvedores ativaram a coleta de AppSet\_id, pois algumas mediações podem fornecer apenas esse identificador. Consulte as instruções do desenvolvedor para [Coletar AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |
| Nível de impressão via SDK | <ul><li>O nível de impressão refere-se à maneira como a AppsFlyer recebe os dados. Os dados podem acabar sendo reportados em outros níveis de granularidade (como o nível do dispositivo).</li><li>A plataforma de mediação ou monetização relata a receita por usuário a nível de impressão. Nem todas as redes são compatíveis com a granularidade a nível de impressão.</li><li>Essa receita é atribuída à fonte de mídia que trouxe o usuário. Ou seja, a atribuição da receita publicitária da AppsFlyer segue as regras de atribuição encontradas na plataforma, incluindo regras de atribuição de retargeting.</li><li>Se você estiver usando uma plataforma de mediação, certifique-se de desativar as integrações de receita de anúncios para parceiros de monetização mediados pela plataforma antes de ativar a integração de receita de anúncios com a plataforma. Caso contrário, você terá dados duplicados.</li><li>Essa opção oferece a melhor atualização de dados dentre todos os tipos de integração de receita de anúncios.</li><li>É compatível com SKAN (SKAdNetwork).</li><li>Esse é o tipo de integração que deve ser usado quando você usa uma plataforma de mediação que não está incluída na lista de parceiros integrados da AppsFlyer. No Ad revenue SDK, para mediation\_network, o desenvolvedor deve escolher customMediation.</li><li>Os dados podem ser compartilhados com ad networks somente via <Anchor target="_blank" href="/marketers/pt/docs/share-ad-revenue-data-with-partners">postbacks</Anchor>.</li></ul> |
| Nível de impressão (via SDK) com nível de dispositivo (via S2S API) | <ul><li>Permite que os dados no nível de impressões que chegam via SDK sejam atribuídos e reportados no Dia X e sejam substituídos por dados device-level que chegam via API a partir do Dia 1 em diante. **Atenção:** para Android, os dados relatados via SDK de dispositivos desconhecidos (sem IDs de dispositivos disponíveis) não são substituídos por dados que chegam via API.</li><li>Permite atualização de dados precisa. Ou seja, você tem o benefício da atualização dos dados para o Dia X com a precisão dos dados para os Dias X+1 em diante.</li><li>Compatível com SKAN.</li><li>Os dados podem ser compartilhados com as ad networks por meio de <Anchor target="_blank" href="/marketers/pt/docs/share-ad-revenue-data-with-partners">postbacks e sinais de UA</Anchor>.</li><li>Para Android: Certifique-se de que os desenvolvedores ativaram a coleta de AppSet\_id, pois algumas mediações podem fornecer apenas esse identificador. Consulte as instruções do desenvolvedor para [Coletar AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |

</Accordion>

## Implementação

As seções a seguir descrevem os tipos de atribuição de receita de anúncios disponíveis, bem como os fluxos de trabalho e as etapas necessárias para implementação e manutenção.

<Accordion title="Conectar-se com parceiros integrados">

**Antes de começar**:

* Solicite que o parceiro integrado de receita de anúncios forneça a você as credenciais da API.

**Para ativar a integração da receita de anúncios com a ad network**:

1. Na AppsFlyer, no menu lateral, selecione **configurações** > **configurações de receita** > receita de anúncios.
2. Em integração de receita de anúncios, clique em **nova integração de receita de anúncios**.
3. Selecione um parceiro de receita de anúncios e clique em **Avançar**.

   ![ad revenue 3.6(2).png](https://files.readme.io/8ccba7d0909c15e92507bc55c7bf2bf003e1a9431fb6bd1d32a0f41959f7a904-47792643579153.png)

   > 📘 **Atenção**
   >
   > Se a sua solução de mediação não aparecer na lista de parceiros suportados, selecione **Mediação personalizada** e integre-a através da <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/gs-ad-revenue">API do SDK de receita de anúncios da AppsFlyer</Anchor>.

4. Selecione o tipo de dados de receita de anúncios que você deseja receber. **Atenção:** Nem todas as ad networks oferecem todas as opções listadas abaixo.
   * Receita atribuída. Ou seja, receita com base na fonte de aquisição do usuário. Os relatórios de receita atribuída podem exibir:
     * [Nível agregado](#h_01JYRKB8Q3D3W0FM75VH78XQTS) via API S2S
       * Selecione o evento no qual basear a receita de anúncios. Por exemplo, se você escolher o evento af\_app\_opened, a receita total de anúncios será dividida entre todos os eventos de abertura do aplicativo, fornecendo a receita de anúncios por abertura do aplicativo.
     * Nível do dispositivo via S2S API.
       * **Para Android:** Certifique-se de que os desenvolvedores ativem a coleta de`app_set_id`, pois algumas mediações podem fornecer apenas esse identificador. Consulte as instruções do desenvolvedor para [Coletar AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).
       * **Observação**: Se você estiver ativando a API de receita de anúncios device-level para uma plataforma de mediação, deverá desativar as integrações de receita de anúncios das networks de monetização mediadas por ela. Caso contrário, você terá dados duplicados.
     * Nível de impressão via SDK.
       * Peça aos desenvolvedores do seu aplicativo que integrem a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/gs-ad-revenue">ad revenue SDK API da AppsFlyer</Anchor>.
     * **Recomendado:** Nível de impressão (via SDK) com nível de dispositivo (via API S2S).
       * Peça aos desenvolvedores do seu aplicativo que integrem a [ad revenue SDK API da AppsFlyer](https://dev.appsflyer.com/hc/docs/gs-ad-revenue).
     * **Para Android:** Certifique-se de que os desenvolvedores ativem a coleta de`app_set_id`, pois algumas mediações podem fornecer apenas esse identificador. Consulte as instruções do desenvolvedor para [Coletar AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).
     * **Observação**: Se você estiver usando uma plataforma de mediação, certifique-se de desativar as integrações de receita de anúncios para parceiros de monetização mediados pela plataforma antes de ativar a integração de receita de anúncios com a plataforma. Caso contrário, você terá dados duplicados.
5. Preencha as credenciais da API ou faça login, conforme exigido pelo parceiro integrado. Essa ação não é relevante para as integrações de SDK.
6. Clique em Salvar.
7. Para verificar se a conexão da API é operacional:
   * Se chave de API verificada aparecer, você concluiu o procedimento com sucesso.
   * Se qualquer outra mensagem for exibida, consulte a tabela [Status e testes da integração de receita de anúncios](#01ECF1PZ32Z4C20NADJ2SF3EPC) e siga a ação corretiva recomendada. Em seguida, repita o procedimento.
8. A AppsFlyer coleta dados várias vezes por dia. Para mais informações, consulte [Atualização de dados](#01H8V10BKK6N5XJ6GHKC201E3Y).
9. [Opcional] Faça o controle de qualidade e compare os dados de receita publicitária que você vê na AppsFlyer com os dados de receita de anúncios que você vê nos painéis do seu parceiro de mediação e do parceiro de UA. <Anchor target="_blank" href="/marketers/pt/docs/compare-roi360-ad-revenue-data-with-partner-data">Saiba mais</Anchor>
10. [Opcional] Compartilhe dados de receita de anúncios com seus parceiros via sinais de UA e postbacks de eventos de receita de anúncios.

**Atenção**: se você mudar de um tipo de integração para outro, essa alteração entrará em vigor às 12h UTC do dia seguinte.

</Accordion>

<Accordion title="Visualize, edite e exclua parceiros integrados">

![delete_edit_adi.png](https://files.readme.io/2d2153ec3248061dab4072e1d981e237f553e32824a68e392ae239778b307610-47792653636113.png)

**Para visualizar, editar ou excluir integrações**:

1. Na AppsFlyer, no menu lateral, selecione configurações > configurações de receita > receita de anúncios e selecione o seu app.  
   Uma lista de todas as suas integrações de parceiros é exibida, juntamente com informações sobre o produto e o tipo de integração, o status da integração e os nomes dos eventos de receita publicitária.
2. Passe o mouse sobre a integração e clique em **editar** ou **excluir** conforme necessário.

</Accordion>

<Accordion title="Desduplicação da receita de anúncios cruzada">

Quando um aplicativo usa duas <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#plataforma-de-mediação">plataformas de mediação</Anchor> com tipos de integração de API (nível agregado ou device-level), ambas associadas à mesma <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#monetization-network">network de monetização</Anchor>, pode ocorrer duplicação parcial dos dados de receita de anúncios. Nesses casos, cada plataforma de mediação reporta toda a receita de anúncios gerada por sua network de monetização associada, independentemente de essa receita ter sido gerada enquanto era mediada por apenas uma das plataformas.

**Para evitar a duplicação parcial dos dados**:

* Se disponíveis, use integrações a nível de impressão via SDK. Os dados em nível de impressão reportados dessa forma não são deduplicados. O SDK reporta cada impressão uma vez, então não há sobreposição a ser removida.
* Para integrações **via API**, deduplique a receita de anúncios:
  1. Na AppsFlyer, no menu lateral, selecione **configurações** > **configurações de receita** > receita de anúncios.
  2. Em **Configurações gerais**, clique em **Desduplicar receita de anúncios quando dois parceiros de mediação fizerem referências cruzadas**. **Observação**: Não marque a caixa se as 2 plataformas de mediação mediarem formatos de anúncio diferentes. Por exemplo, quando a plataforma 1 mostra Banner e Intersticial, e a plataforma 2 mostra AppOpen e anúncios nativos.

     > 📘 **Importante!**
     >
     > A configuração é sempre ignorada para:
     >
     > * **Integrações no nível de impressão (SDK)** — todos os Parceiros.
     > * **Integrações no nível do dispositivo (API)** - para AppLovin MAX ou ironSource (Unity LevelPlay)
     >
     > Elas já não contêm dados duplicados, então não há nada para desduplicar.


![dedup.png](https://files.readme.io/a739bc7e3557913bf6a67afa74a71dd72673d5b4e4d6bbe1d3ef872e46609422-47792653637265.png)

</Accordion>

<Accordion title="Agregar granularidade usando a abertura de aplicativo ou eventos in-app">

A granularidade agregada das receitas de anúncios funciona da seguinte forma:

* A rede integrada relata a receita diária total, detalhada por geo.
* A AppsFlyer obtém a receita efetiva por ação (eRPA) através da divisão da receita de anúncios pelo número de instâncias de um evento de disparo.
* A AppsFlyer cria um evento \_monetized que inclui o eRPA total para cada dispositivo atribuído. Por exemplo, ad\_matched\_monetized.
* Usando o eRPA, a receita é atribuída às fontes de mídia.
* Você pode usar um dos seguintes tipos de eventos:
  * **Evento in-app exclusivo de monetização**, que requer modificações no aplicativo.
  * Evento **af\_app\_opened** disponível por padrão.
* Não informe os valores de receita em eventos in-app em paralelo a uma integração de receita de anúncios. Isso faz com que a receita de anúncios seja duplicada no dashboard, pois a AppsFlyer obtém os dados de receita da network de monetização por meio da integração.

#### Receita de anúncios agregada usando eventos

| Método do evento | Como é implementado | Considerações |
| --- | --- | --- |
| Evento in-app exclusivo de monetização | <ul><li>Um evento in-app é definido no momento da exibição do anúncio</li><li>Isso fornece uma contagem distinta de ações do usuário, o que permite cálculos de eRPA aprimorados</li><li>Isso pode ser refinado ainda mais com um evento in-app diferente para cada network de monetização. Isso permite detalhar a receita por network de monetização<br />Consulte a tabela a seguir para uma explicação completa.</li></ul> | <ul><li>Requer que o desenvolvedor modifique o aplicativo</li><li>A receita pode ser separada por rede de monetização no dashboard</li></ul> |
| af\_app\_opened event | <ul><li>O evento af\_app\_opened é enviado pelo SDK da Appsflyer por padrão</li><li>Ele é acionado a cada sessão de usuário</li></ul> | <ul><li>Nenhuma modificação do aplicativo é necessária</li><li>Rápida implementação</li><li>Os valores de eRPA ficam bastante distorcidos, a menos que você mostre apenas um anúncio por sessão</li><li>Sem divisão da receita por rede de monetização</li><li>O evento se aplica a todos os usuários que abrem o aplicativo, e você não tem nenhuma indicação da disposição do usuário de assistir a anúncios</li></ul> |

#### Comparação de métodos de eventos in-app

| Mensuração | Prós | Contras | considerações |
| --- | --- | --- | --- |
| Usa o mesmo evento para todas as redes. Por exemplo, ad\_watched. Isso gera automaticamente o evento ad\_watched\_monetized, contendo as informações de monetização | Implementação mais simples | Sem informações de qualidade, como o número de cliques e a receita de anúncios por rede | <ul><li>Mais adequado se o objetivo principal for encontrar fontes/campanhas que atraem usuários com maior tendência a clicar em anúncios.</li><li>Não é adequado para comparar a performance das redes de monetização.</li></ul> |
| **(Prática recomendada)** Cada rede recebe um evento exclusivo para a visualização de anúncios. Exemplo: ad\_watch\_admob,<br /><br /> ad\_watch\_vungle. | Visibilidade total e capacidade de comparar as redes de monetização no dashboard, além de exibir dados brutos. | A receita de anúncios não é acumulada em um único evento. O número de eventos é equivalente ao número de redes | Permite a comparação de redes de monetização no dashboard. A receita de anúncios é separada por rede usando um evento in-app por rede. |

</Accordion>

<Accordion title="Status e testes da integração de receita de anúncios">

O status operacional da integração da receita de anúncios é disponibilizado da seguinte forma:

* <Anchor target="_blank" href="/marketers/pt/docs/dashboard-cost-and-ad-revenue-status">Dashboard do status da integração</Anchor>: Lista de parceiros com os quais a integração da receitas de anúncios está ativada para um ou mais aplicativos da sua conta.
* **Botão Testar conexão:** Disponível quando você adiciona ou edita uma integração de receita de anúncios. Use-o para verificar se a integração está operacional.

Para verificar se a integração está funcionando:

1. Para verificar se a conexão da API é operacional:
2. Uma mensagem informando que a chave da API foi verificada é exibida. Se qualquer outra mensagem aparecer, siga as orientações de ação corretiva na tabela abaixo.

| Estado | Significado | Observações/ação necessária |
| --- | --- | --- |
| Chave verificada | Se não houver a opção de testar conexão, o procedimento está concluído.   <br />A AppsFlyer coleta dados do parceiro várias vezes por dia. Para mais informações, consulte [Atualização de dados](#01H8V10BKK6N5XJ6GHKC201E3Y). | Nenhuma. |
| A autenticação foi bem sucedida | Eventos válidos de receita de anúncios foram recebidos do SDK. | Nenhuma. |
| Credenciais inválidas | Uma ou mais das credenciais fornecidas estão incorretas. | Obtenha as credenciais corretas com o parceiro de receita de anúncios |
| Detalhes de configuração ausentes | Um ou mais campos estão incompletos | Recupere as credenciais no dashboard do parceiro ou entre em contato com ele e solicite as credenciais. |
| Nenhum evento encontrado | Nenhum evento válido de receita de anúncios foi recebido do SDK recentemente. | Confirme se a integração do SDK está concluída e se os eventos de teste estão sendo enviados. Você pode verificar a entrega de eventos em tempo real usando o <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers#view-live-events">Live Events viewer</Anchor>. |

> 📘 **Atenção**
>
> Para integrações do SDK, você também pode verificar se os eventos de receita de anúncios são registrados em tempo real usando o <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers#view-live-events">Live Events viewer</Anchor>. Observe que ele exibe apenas eventos enviados de dispositivos de teste registrados.

</Accordion>

## Dados de receita de anúncios

Os dados de receita de anúncios estão disponíveis por meio dos dashboards da AppsFlyer e relatórios de dados brutos.

<Accordion title="Dados agregados de receita de anúncios">

A receita de anúncios mostra a qualidade dos usuários obtidos de diferentes fontes ao longo do tempo. À medida que os usuários continuam abrindo o aplicativo e interagindo com anúncios, o LTV deles aumenta.

**Atenção:** pode haver discrepâncias entre os dados de receita de anúncios em diferentes dashboards e relatórios.

A atribuição de receita de anúncios está disponível da seguinte forma:

* Baseado em LTV:
  * Nos dashboards: visão geral, eventos
  * Relatórios de LTV
  * Dashboard e relatórios de cohort
  * Master API
* Baseado em atividades:
  * Dashboard: atividades
  * Dados brutos de receita de anúncios

#### **Dashboard de visão geral - relatório de performance agregada**

![](https://files.readme.io/f3ea2c79ed42c59d26f6f82d7f68e20b319a005e6a3131239b99f13db59b3cff-47792643589393.png)

No dashboard de visão geral:

* Os valores, incluindo a receita, são LTV. Consulte <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV vs. dados de atividade</Anchor>.
* A coluna **receita** inclui toda a receita, inclusive a receita de anúncios e de compras in-app.
* Faça uma análise detalhada da hierarquia de anúncios (canal de mídia, campanha, conjunto de anúncios, geolocalização) para visualizar os eventos **monetized** no relatório.

**Painel de eventos**

![](https://files.readme.io/c7c8fddb68f705a7be694afdde6faf387cf34b79abfbc68c39e53823549a385d-47792643591057.png)

No dashboard de atividades:

* Os valores, incluindo a receita, são baseados na data da atividade. Consulte <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV vs. dados de atividade</Anchor>.
* A **média de ações por usuário** indica a tendência dos usuários de interagir com os anúncios exibidos no aplicativo.

#### Exemplos

Três usuários instalaram um aplicativo em 31 de dezembro de 2017. Eles são atribuídos da seguinte forma:

* Usuário A: Network A
* Usuário B Network B
* Usuário C: Orgânico

O aplicativo está integrado a cinco plataformas de monetização diferentes. Cada plataforma usa um evento in-app exclusivo no SDK da AppsFlyer:

* Meta Audience Network: fb\_ad\_view
* Chartboost: chartboost\_ad\_view
* Admob: admob\_ad\_view
* Applovin: applovin\_ad\_view
* IronSource: is\_ad\_view

Quatro dias após a instalação, os usuários visualizam os anúncios da seguinte forma:

| Usuário | Rede de UA | fb\_  <br />ad\_view | chartboost\_  <br />ad\_view | admob\_  <br />ad\_view | applovin\_  <br />ad\_view | is\_ad\_view | Total |
| --- | --- | --- | --- | --- | --- | --- | --- |
| E | Ad network A<br /><br />31/12/2017 | 01/01/2018<br /><br />US$ 1 | 02/01/2018<br /><br />US$ 1 | 03/01/2018<br /><br />US$ 1 | 04/01/2018<br /><br />US$ 1 |  | US$4 |
| B | Ad network B<br /><br />31/12/2017 | 02/01/2018<br /><br />US$ 1 |  | 04/01/2018<br /><br />US$ 1 |  |  | US$2 |
| C | Orgânico<br /><br />31/12/2017 | 01/01/2018<br /><br />US$ 1 |  |  |  | 02/01/2018<br /><br />US$ 1 | US$2 |

Olhando para os dados, podemos resumir a receita coletada por usuário, por dia (e por evento in-app):

| Usuário | 01/01/2018 | 02/01/2018 | 03/01/2018 | 04/01/2018 | LTV total |
| --- | --- | --- | --- | --- | --- |
| E | US$ 1 | US$ 1 | US$ 1 | US$ 1 | US$4 |
| B |  | US$ 1 |  | US$ 1 | US$2 |
| C | US$ 1 | US$ 1 |  |  | US$2 |
| Total | US$2 | US$3 | US$ 1 | US$2 | US$8 |

**Entendendo os relatórios:**

A receita de anúncios está vinculada ao LTV do usuário. Portanto, o período de tempo selecionado no dashboard representa o cohort de instalações com a receita é agregada até a hora e o dia atuais. Vamos analisar um relatório com duas seleções de datas diferentes:

Relatório agregado: Datas selecionadas: 2017-12-31-2018-01-05

| Rede | Receita do LTV |
| --- | --- |
| Orgânico | US$2 |
| Ad network A | US$4 |
| Ad network B | US$2 |
| Rede C | US$2 |

Nesse caso, o cohort é composto por usuários que instalaram o aplicativo entre 2017-12-31 e o dia atual, 2018-01-05. Toda a receita gerada por esses usuários está vinculada à fonte de aquisição e refletida no LTV do usuário.

</Accordion>

<Accordion title="Dados brutos de receita de anúncios">

<Image alt="PremiumFeature.jpg" src="https://files.readme.io/674e5d0c9efde9d12008bd705b3ba95f04e133fec3f39d4278612675123d4de4-360007173877.jpg" width="78px" />

Os relatórios de dados brutos de receita de anúncios contêm dados de networks de monetização com integração device-level ou impression-level com a AppsFlyer.

**Princípios dos dados brutos de receita de anúncios**

* Os dados são agregados pelo número de impressões exclusivas por usuário. As impressões exclusivas são derivadas da combinação da network de monetização de anúncios, da unidade de anúncio e do posicionamento.
* Os dados brutos a nível de impressão são:
  * Agregados ao nível device-level e disponíveis em relatórios device-level.
  * Disponíveis como relatórios impression-level no Data Locker.

<table><thead><tr><th>Relatório</th><th>Página de<br/>exportação de dados</th><th>Extrair API </th><th>Relatório do Data Locker</th></tr></thead><tbody><tr><td>Receita atribuída (não-orgânica)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Receita publicitária orgânica</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Receita publicitária de retargeting </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Dados brutos em nível de impressão\*\*</td><td><span>-</span></td><td><span>-</span></td><td><span>✓ </span></td></tr><tr><td colspan="4"><p>\* O relatório versionado também está disponível, atualizado várias vezes por dia. Os relatórios do Data Locker sem versão controlada são diários. Para mais informações, consulte <a href="#01H8V10BKK6N5XJ6GHKC201E3Y">Data Freshness</a>.</p><p>\*\* Refere-se a relatórios com "impression-level" no nome e não à integração de receita de anúncios no nível de impressão.</p></td></tr></tbody></table>

**Características e campos dos dados**

Os campos nos relatórios de receita de anúncios são preenchidos:

* Pelo próprio evento de receita de anúncios e listado na tabela a seguir. Esses campos são divididos em:
  * **Específicos:** campos específicos para a receita de anúncios. Por exemplo, impressões e posicionamento. **Atenção!** Os campos preenchidos diferem por parceiro de monetização, conforme mostrado na tabela.
  * **Contextuais:** campos com um significado parecido em outros relatórios de dados brutos. Por exemplo, nome do evento, valor do evento e moeda.
* Como resultado da atribuição do evento à fonte de mídia que trouxe o usuário. Isso significa que esses campos são copiados do evento de conversão que trouxe o usuário. Por exemplo, canal de mídia e uma campanha. Esses campos não estão listados na tabela a abaixo.

#### Campos preenchidos pela receita de anúncios

| api\_name | Nome do campo | Tipo de campo | Descrição |
| --- | --- | --- | --- |
| <span id="event_time"></span>event\_time | Hora do evento | Contextual | A data à qual a receita é atribuída |
| <span id="event_name"></span>nome\_do\_evento | Nome do evento | Contextual | Definido como af\_ad\_revenue |
| <span id="event_revenue"></span>event\_revenue | Moeda da receita do evento | Contextual | <ul><li>Valor da receita usando a moeda da receita do evento</li><li>Um valor zero indica impressões sem receita</li></ul> |
| <span id="event_revenue_currency"></span>event\_currency | Moeda do evento | Contextual | Moeda da receita do evento |
| <span id="event_revenue_xxx"></span>event\_revenue\_XXX | Receita do evento XXX | Contextual | <ul><li>Na página de exportação: receita convertida para a moeda específica do aplicativo</li><li>No Data Locker, sempre em USD</li><li>Na Pull API, de acordo com a moeda do Pull.</li></ul> |
| <span id="country"></span>país | País | Contextual | País da instalação da conversão de instalação |
| <span id="ad_unit"></span>ad\_unit | Unidade do anúncio | Específico | O valor desse campo é específico para a ad network. Para integrações de servidor para servidor (S2S):<ul><li>**MAX:** Use o ad unit ID (por exemplo, f53328a3c).</li><li>**IronSource:** Use o tipo de ad unit, como banner, rewarded\_video ou interstitial.</li></ul>Para outras redes, consulte o guia de integração de parceiros relevante ou entre em contato com o representante da rede para confirmar o formato necessário. |
| <span id="segment"></span>segment | Segmento | Específico | Nome do posicionamento do anúncio |
| <span id="monetization_network"></span>monetization\_network | Rede de monetização | Específico | Network está enviando o anúncio |
| <span id="impressions"></span>impressions | Impressões | Específico | Número de vezes que o usuário viu o anúncio |
| <span id="mediation_network"></span>mediation\_network | Rede de mediação | Específico | Rede de mediação que relata o evento para a AppsFlyer |
| <span id="customer_user_id"></span>customer\_user\_  <br />id | Customer User ID | Contextual | Se disponível pelo anunciante:<ul><li>Para integrações em nível de impressão (SDK): coletado via `setCustomerUserId()` no SDK do AppsFlyer.</li><li>Para integrações no nível do dispositivo (API): coletado da API de mediação (user ID ou publisher user ID definido via SDK de mediação).</li><li>Não compatível com Odeeo e Appodeal.</li></ul> |

#### Campos por rede

<table><thead><tr><th>Nome de exibição</th><th>AdMob</th><th>IronSource (LevelPlay)</th><th>AppLovin MAX</th><th>Appodeal</th><th>Fyber </th></tr></thead><tbody><tr><td>Unidade do anúncio</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Segmento</td><td>-</td><td>(1)</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Posicionamento</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Rede de monetização</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Impressões</td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td>Rede de mediação</td><td><span>-</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) O anunciante precisa configurar no ironSource</td></tr></tbody></table>

[Relatório de amostra de dados brutos de receita de anúncios](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm_1tevWFdzdj6JgdxYawLBtYAJj-ubDeY4g1QfbdSkd2-Adi18oemPMdd7m7cM2e3fzm7VH0w6lhD/pub?output=xlsx)

</Accordion>

<Accordion title="Atualização dos dados">

A atualização dos dados depende do tipo de integração e do método de relatório.

Para **integrações da S2S API**, a data mais recente de disponibilização dos dados varia:

* Em dashboards e relatórios de dados brutos (via Data Locker), disponibilizados a partir do Dia X+1, 12 AM UTC, aproximadamente 4 vezes por dia, de 6 em 6 horas. E nos dias 2, 3, 7 e 14, uma vez por dia.

Para **integrações de SDK em nível de impressão**, a data mais recente de disponibilização dos dados varia:

* Dashboards (métricas de atividade e cohort): contínua (15 a 60 minutos após a ocorrência do evento)
* Na melhor das hipóteses, os dados são disponibilizados nos dashboards e relatórios de dados brutos (via Data Locker), no Dia X a partir das 5h UTC, atualizados aproximadamente 6 vezes por dia, a cada 4 horas.
* Relatórios de dados brutos de nível de impressão (via Data Locker) no dia X a partir da 1h UTC, atualizados a cada hora.

Para **nível de impressão (via SDK) com nível de dispositivo (via S2S API), você obtém a atualização dos dados para o Dia X com a precisão dos dados para os Dias X+1, da seguinte forma:**

* Para dados no nível da impressão que chegam via SDK:

  * Dashboards (métricas de atividade e cohort): contínua (15 a 60 minutos após a ocorrência do evento)
  * Na melhor das hipóteses, os dados são disponibilizados nos dashboards e relatórios de dados brutos (via Data Locker), no Dia X a partir das 5h UTC, atualizados aproximadamente 6 vezes por dia, a cada 4 horas.
  * Relatórios de dados brutos de nível de impressão (via Data Locker) no dia X a partir da 1h UTC, atualizados a cada hora.
* Para dados no nível do dispositivo que chegam via API S2S:

  * Em dashboards e relatórios de dados brutos (via Data Locker), disponibilizados a partir do Dia X+1, 12 AM UTC, aproximadamente 4 vezes por dia, de 6 em 6 horas. E nos dias 2, 3, 7 e 14, uma vez por dia.

Para a **Exportação de dados brutos e Pull API**, independentemente do tipo de integração ou pacote ROI360 (Advanced ou Standard), os dados de um determinado dia ficam disponíveis no dia seguinte, às 6 PM UTC no Dia X+1. Os dados não são atualizados após esse horário para essas ferramentas.

**Atenção:** A disponibilidade de dados intradiários em dashboards requer uma assinatura ROI360 Advanced.

</Accordion>

<Accordion title="Relatórios de receita de anúncios no Data Locker">

| Nome | Pouca atualização | Seções do relatório |
| --- | --- | --- |
| ***Receita de anúncios diária (agregada no nível do dispositivo)*** | A receita de anúncios de um determinado dia (dia X) é informada no dia seguinte (X+1), às 5 PM UTC.<br /><br />Por exemplo, a receita publicitária de 1º de maio será informada no dia 2 de maio. | O relatório inclui as seções de receita de anúncios atribuída, orgânica e de retargeting. |
| \*\*Relatório diário de receita de anúncios versionado\*\** (agregado no nível do dispositivo)\*\** | O relatório diário consiste em:<ul><li>Versões do dia são criadas a cada 4 horas durante o dia da receita (dia X). Os dados do dia são coletados pela API do SDK.</li><li>Versões de um dia inteiro são criadas nos dias 1, 2, 3, 7 e 14, com base nos dados originados dos relatórios da S2S API.</li></ul>Ou seja, o conjunto de versões de um relatório diário inclui as seguintes versões:<ul><li>00:00 — 04:00 no dia X.</li><li>00:00 — 08:00 no dia X [API SDK]</li><li>00:00 — 12:00 no dia X [API SDK]</li><li>00:00 — 24:00 no dia X [API do SDK]</li><li>00:00 — 24:00 no dia x+1 [S2S]</li><li>00:00 — 24:00 no dia x+2 [S2S]</li><li>00:00 — 24:00 no dia x+3 [S2S]</li><li>00:00 — 24:00 no dia x+7 [S2S]</li><li>00:00 até 24:00 no dia x+14 [S2S]</li></ul> | Cada versão do relatório inclui as seções de receita de anúncios Atribuída, Orgânica e de Retargeting. |
| ***Relatório de receita de anúncios no nível de impressão (impression-level)*** | Os registros de receita de anúncios no nível de impressão são gravados em um arquivo separado a cada hora. |  |

<span id="h_01KRKHJN2G5SER73D3EZB14GDS"></span>**Veja também:**

* <Anchor target="_blank" href="/marketers/pt/docs/revenue-etl-reports">Relatórios de Revenue ETL</Anchor>

</Accordion>

## Informações adicionais

<Accordion title="Migrando da granularidade agregada para a granularidade no nível do dispositivo">

Lembre-se do seguinte ao migrar da granularidade agregada para a granularidade device-level:

* A migração não afeta os dados históricos de receita de anúncios. Esses dados permanecem inalterados.
* Os dados de receita de anúncios são extraídos várias vezes ao dia, a partir das 03:00 UTC, usando as opções de granularidade selecionadas naquele momento.
* A granularidade no nível do dispositivo não exige que você defina eventos in-app (como você faz para relatórios no nível agregado). Você pode continuar enviando esses eventos, mas eles não afetam o relatório de granularidade no nível do dispositivo.

</Accordion>

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Limitações | Os eventos de receita de anúncios não estão disponíveis para:<ul><li>API de push</li><li>Dashboard de retargeting</li></ul>Limitações de granularidade no nível do dispositivo:<ul><li>O evento af\_ad\_revenue não está disponível para cohorts no Pivot e Master API.</li><li>O evento está disponível na análise de cohort.</li><li><Anchor target="_blank" href="/marketers/pt/docs/applovin-max-ad-revenue-configuration#prática-recomendada">Podem ocorrer discrepâncias na implementação da receita de bids **in-app** do Meta ads.</Anchor></li></ul>A contagem de usuários únicos que acionam um evento af\_ad\_revenue não tem suporte nos dashboards da AppsFlyer. |
| Device IDs compatíveis | Os device IDs abaixo são compatíveis com a atribuição de receita de anúncios:<ul><li>ID da AppsFlyer</li><li>IDFA</li><li>IDFV</li><li>GAID</li><li>AppSet ID*</li><li>ID Android</li><li>IMEI</li></ul><ul><li>AppSet ID é compatível apenas com mediações da Applovin MAX e IronSource LevelPlay. Consulte as instruções do desenvolvedor para [Coletar AppSet ID](https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id).</li></ul> |
| Acesso da ad network | Não é possível acessar relatórios de cohort |
| Acesso de agência | Agências:<ul><li>Não é possível acessar as configurações da receita de anúncios</li><li>É possível visualizar todos os dashboards e dados relevantes.</li></ul> |
| Transparência da agência | Não compatível |
| Fuso horário | A receita de anúncios é exibida nos dashboards e relatórios da AppsFlyer somente no fuso horário UTC. Ou seja, se os dados forem reportados às 2 PM UTC+2, na AppsFlyer eles serão exibidos como 2 PM UTC. processado diariamente.<br /><br />Isso ocorre porque a AppsFlyer precisa padronizar os dados coletados de múltiplas fontes e parceiros, a maioria dos quais relata seus dados em UTC. |
| Moeda | Na AppsFlyer:<ul><li>O dashboard exibe a moeda específica do aplicativo do anunciante.</li><li>Os relatórios de dados brutos exibem a moeda original e também a convertem para a moeda específica do aplicativo do anunciante.</li></ul> |
| Tipo de dados | Dados orgânicos e não-orgânicos são compatíveis. |
| Atualização dos dados | [Receita de anúncios](#01H8V10BKK6N5XJ6GHKC201E3Y) |
| Dados históricos/retroativos | <ul><li>Os dados são extraídos e ficam disponíveis a partir do dia da integração. Isso significa que os dados históricos não ficam disponíveis antes da data da integração (dia 0).</li><li>Os dados de receita de anúncios recebidos via S2S API para um dia específico são atualizados nos dias 1, 2, 3, 7 e 14.</li><li>Os dados de receita de anúncios nos dashboards de Visão geral, Cohort e Atividade, assim como os dados via Master API e Cohort API, são atualizados retroativamente; via exportação de dados brutos e Pull API, não. Se você tiver o pacote de receita avançada, os dados também são atualizados no Data Locker.</li></ul> |
| Acesso do usuário da conta | Com suporte. |
| SKAN | Compatível com a ad revenue SDK API a nível de impressão. |
| Geolocalização/país | No dashboard de Cohort, quando a geolocalização é desconhecida (N/A), os dados N/A não são exibidos ao agregar por geolocalização. |
| Postbacks de eventos in-app | <ul><li>Postbacks para parceiros podem ser para "somente este parceiro" ou "todos os canais de mídia, incluindo orgânico". <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#opções-para-envio-de-postbacks">Saiba mais</Anchor></li><li>Os postbacks de eventos de receita de anúncios para ad networks funcionam apenas com a integração de receita de anúncios a nível de impressão (via SDK) com integração de receita de anúncios a nível de dispositivo (via S2S API).</li></ul> |
| Aplicativos de CTV, PC e console | <ul><li>Apenas aplicativos Android e iOS são compatíveis.</li><li>A plataforma Windows (UWP) é compatível com a Vungle.</li><li>Todas as outras plataformas não são compatíveis.</li></ul> |
| Customer User ID (CUID) | Disponível para integrações de SDK e no nível de dispositivo. |
| Contagem de eventos em dashboards | A expectativa é que o número eventos seja maior para os dados intradiários em comparação com períodos históricos. Os dados históricos são agregados em impressões únicas de receita de anúncios (mesmo dispositivo × rede × unidade de anúncio × posicionamento), resultando em uma contagem de eventos menor. |

</Accordion>

<Accordion title="Lista de parceiros integrados de receita de anúncios">

<table><thead><tr><th rowspan="2">Parceiro</th><th colspan="3">Tipo de integração disponível</th></tr><tr><th>Nível agregado</th><th>Nível do dispositivo</th><th>Nível de impressão</th></tr></thead><tbody><tr><td>Admost</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./applovin-campaign-configuration#ad-revenue-tab" target="_blank">AppLovin</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./applovin-max-ad-revenue-configuration" target="_blank">AppLovin Max</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./appodeal-campaign-configuration" target="_blank">Appodeal</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./bytedance-ads-china-campaign-configuration" target="_blank">Bytedance Ads (tráfego da China)</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Pingle (TikTok for Business)</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./chartboost-campaign-configuration#ad-revenue-tab" target="_blank">Chartboost</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td>Mediação personalizada</td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td>Google Ad Manager</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./meta-ads-integration-setup" target="_blank">Meta Ads</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./fyber-campaign-configuration#ad-revenue-tab" target="_blank">Fyber</a> </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./google-admob-ad-revenue-attribution-configuration" target="_blank">Google Admob</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td> <a href="./ironsource-campaign-configuration#ad-revenue-tab" target="_blank">ironSource</a> (LevelPlay)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Odeeo</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tapjoy</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Topon</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Topon Pte</td><td>-</td><td>-</td><td> <span>✓</span><br/> </td></tr><tr><td>Tradplus</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./unity-ads-campaign-configuration" target="_blank">Unity Ads</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Mediação do Unity Ads</td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td>Voodoo</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./vungle-campaign-configuration" target="_blank">Vungle</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Yandex</td><td>-</td><td>-</td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div data-zendesk-anchors="ad-revenue-attribution=atribui%C3%A7%C3%A3o-de-receita-de-an%C3%BAncios 01ECF1PZ2XNCHR4QPATTBV0VMV=atribui%C3%A7%C3%A3o-de-receita-de-an%C3%BAncios implementation=implementa%C3%A7%C3%A3o 01ECF1PZ2Y9ERT5C50ZD4CDJET=implementa%C3%A7%C3%A3o h_01_custom_mediation_note=aten%C3%A7%C3%A3o h_01M1TXMH5P53PNVW56GHZEXKKK=importante aggregate-ad-revenue-using-events=receita-de-an%C3%BAncios-agregada-usando-eventos 01H8V10BKK06Z3E823G6GNTPKH=receita-de-an%C3%BAncios-agregada-usando-eventos comparison-of-inapp-event-methods=compara%C3%A7%C3%A3o-de-m%C3%A9todos-de-eventos-in-app 01H8V10BKKMG2A704NZC2VFSJM=compara%C3%A7%C3%A3o-de-m%C3%A9todos-de-eventos-in-app h_01_sdk_live_events_note=aten%C3%A7%C3%A3o-1 ad-revenue-data=dados-de-receita-de-an%C3%BAncios 01ECF1PZ3315R242DC78HV60YC=dados-de-receita-de-an%C3%BAncios overview-dashboard-aggregated-performance-report=dashboard-de-vis%C3%A3o-geral---relat%C3%B3rio-de-performance-agregada 01ECF1PZ348365STFGE3136WEJ=dashboard-de-vis%C3%A3o-geral---relat%C3%B3rio-de-performance-agregada 01ECF1PZ348P0JCBASS4QBD56W=exemplos fields-populated-by-ad-revenue=campos-preenchidos-pela-receita-de-an%C3%BAncios 01H8V10BKK7BHC31W27G22D23K=campos-preenchidos-pela-receita-de-an%C3%BAncios fields-by-network=campos-por-rede 01H8V10BKKW6NERRYCRD6BVZ54=campos-por-rede additional-information=informa%C3%A7%C3%B5es-adicionais 01H8V10BKMX7H9H04ZBF3HRJVY=informa%C3%A7%C3%B5es-adicionais" />

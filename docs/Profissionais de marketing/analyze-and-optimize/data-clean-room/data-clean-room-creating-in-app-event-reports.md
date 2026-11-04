---
title: Data Clean Room — Criação de relatórios de eventos in-app
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-09-22T12:03:40Z'
  edited_at: '2026-08-19T00:05:38Z'
  id: 9312610473233
  locale: pt
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/pt/articles/9312610473233
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral:** Crie  relatórios de eventos in-app para se concentrar na atividade do usuário que ocorre após a instalação de um aplicativo. Extraia parâmetros de eventos específicos de seus dados brutos de eventos in-app, opcionalmente, combine os dados com fontes personalizadas e, em seguida, processe-os e apresente-os de forma agregada.

<div id="creating-an-in-app-event-report" />

## Criação de um relatório de eventos in-app

**Para criar um relatório de eventos in-app, siga as etapas detalhadas nas abas abaixo.**

**Observação:** Essas etapas são divididas em abas para facilitar a leitura. Todas as etapas devem ser concluídas para criar o relatório. *(Algumas etapas, conforme indicado, não são relevantes para relatórios que não usam fontes personalizadas.)*

<div id="perform-preliminary-steps" />

<Accordion title="Execute etapas preliminares">

1. Vá para a aba **Relatórios** do **DCR.**
2. Clique no botão **+ Novo relatório**.
3. Selecione **Eventos in-app** como o tipo de dados de origem e clique em **Avançar** no canto inferior direito da tela.
4. Insira um nome para o relatório
   * Pode ser qualquer nome que ajude você a identificar o relatório na plataforma DCR.
   * **Importante!** Certifique-se de que o nome do relatório é diferente de todos os outros relatórios em sua conta ou você não poderá **salvá-lo**.
   * Requisitos do nome do relatório:
     * Duração: 2-80 caracteres.
     * Caracteres válidos:
       * letras **(A-Z, a-z)**
       * números **(0-9)**,  *não pode ser o primeiro caractere de um nome*
       * um hífen (-), *não pode ser o primeiro caractere de um nome*
     * Caracteres inválidos:
       * espaços
       * todos os outros símbolos ou caracteres especiais

</Accordion>

<div id="select-sources" />

<Accordion title="Selecionar fontes">

Especifique os dados de origem a serem usados para o relatório:

<div id="in-app-event-sources" />

#### **Fontes de eventos in-app**

* Aplicativos Selecione um ou mais dos aplicativos em sua conta da AppsFlyer.
* **Período de tempo:** Selecione o número de dias de dados históricos que você deseja que o DCR pesquise eventos in-app (de 1 a 30 dias).
* **Eventos:** Selecione um ou mais eventos no aplicativo para incluir no relatório.
  * Os eventos disponíveis incluem todos os eventos in-app **dos aplicativos selecionados** que foram configurados para reportar dados à AppsFlyer por meio do SDK ou da API server-to-server (S2S).
* **Tipos de fonte:** Selecione um ou mais tipos de dados de eventos in-app: 

| Instalações | Eventos in-app relacionados às atribuições de instalação<ul><li>Uma instalação é registrada quando um usuário faz o download, instala e inicializa um aplicativo móvel.</li></ul> |
| --- | --- |
| Reengajamentos | Eventos in-app relacionados a reengajamentos<ul><li>Um reengajamento é registrado quando um usuário inativo de um aplicativo específico engaja com com uma campanha de retargeting para o aplicativo e, posteriormente, a lança.</li></ul> |
| Reatribuições | Eventos in-app relacionados a reatribuições<ul><li>Uma reatribuição é registrada quando um ex-usuário de um aplicativo específico (que o desinstalou) engaja com uma campanha de retargeting para o aplicativo e, posteriormente, o reinstala.</li></ul> |

<div id="data-sources" />

#### **Fontes de dados**

1. [Opcional] Adicione outras fontes para usar no relatório. Ao escolher entre mais fontes, observe a diferença significativa entre os relatórios que **usam** e que **não usam** fontes personalizadas.
   * Um relatório que **não** usa fontes personalizadas extrai parâmetros e valores específicos do evento dos dados brutos dos eventos in-app.
   * Um relatório que **usa** fontes personalizadas extrai parâmetros e valores de eventos específicos dos dados brutos do evento no aplicativo e, em seguida, combina esses dados com dados de nível de usuário de suas fontes personalizadas (como dados de seus sistemas de BI ou CRM).
2. Conclua as próximas etapas com base no fato de seu relatório usar ou não fontes personalizadas:
   * Se seu relatório **não** usar fontes personalizadas, vá para **[Selecionar dimensões](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions)** e continue com as etapas em todas as guias restantes.
   * Se seu relatório **usar** fontes personalizadas, continue com as etapas na aba [**Unir fontes**](#join-sources-only-for-reports-containing-custom-sources) (imediatamente a seguir) e em todas as abas restantes.

</Accordion>

A etapa a seguir é relevante **somente para relatórios que usam fontes personalizadas.**

<div id="join-sources-only-for-reports-containing-custom-sources" />

<Accordion title="Unir fontes (somente para relatórios que contêm fontes personalizadas)">

Para combinar os dados entre as fontes, cada uma das fontes **personalizadas** usadas no relatório deve incluir um <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services">identificador</Anchor> mapeado para um **identificador de chave** nos dados do evento in-app.

* Os relatórios de eventos in-app incluem **todos** os eventos selecionados que correspondem ao identificador da chave durante o período selecionado.

<div id="what-is-a-key-identifier" />

#### **O que é um identificador de chave?**

Você pode mapear para qualquer um desses identificadores de dados de eventos no aplicativo como **identificadores-chave**:

* **ID da AppsFlyer (af\_id):** Identificador de aplicativo exclusivo gerado pela AppsFlyer na instalação.
  * O ID aparece em todos os eventos registrados pela AppsFlyer.
  * Um novo ID da AppsFlyer é gerado se um aplicativo for excluído e depois reinstalado.
* **customer\_user\_id (CUID)** Um identificador de usuário exclusivo geralmente gerado e definido pelo proprietário do aplicativo no momento do registro do usuário.
  * O uso do CUID para mapear dados exige que seu aplicativo esteja configurado para <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">enviar o CUID à AppsFlyer</Anchor> por meio do SDK ou da API de servidor para servidor (S2S).

<div id="important" />

> 🚧 **Importante!**
>
> Nem todas as fontes de mídia permitem a correspondência usando CUID. É altamente recomendável usar o ID da AppsFlyer.

<div id="mapping-schemes-directindirect" />

#### **Esquemas de mapeamento (direto/indireto)**

Se o relatório incluir mais de uma fonte personalizada, somente uma delas precisará ser mapeada **diretamente** para um identificador de chave de evento no aplicativo. Outras fontes personalizadas podem ser mapeadas **direta ou indiretamente,** conforme ilustrado no exemplo a seguir:

<div id="example" />

> 📄 **Exemplo**
>
> ![dcr_mapping_identifiers_eventos no app.png](https://files.readme.io/73d0e929663bda4e6f142c64d0228fdf1eeec3b02ef1560f6f03f2a089d00664-9969546429713.png)
>
> No cenário mostrado acima:
>
> * O identificador de fonte #1 personalizado **AF** é mapeado diretamente para o identificador de chave de evento in-app af\_id.
> * A fonte personalizada #2 é mapeada indiretamente: **user\_code** --> **AF** --> **af\_id.**
> * A fonte personalizada #3 é mapeada indiretamente (por meio de uma cadeia mais longa):
>   **user\_id** --> **user\_code** --> **AF** --> **af\_id.**
> * O **ID** do identificador #4 da fonte personalizada é mapeado diretamente para o identificador de chave de evento in-app **af\_id.**
>   * Observe que, em vez disso, ele poderia ter sido mapeado indiretamente (por meio do identificador **user\_id** da fonte personalizada #3), mas qualquer uma das opções funciona bem.
>
> ✓ **Esse esquema de mapeamento funciona para combinar dados entre todas as fontes, já que cada fonte personalizada é mapeada direta ou indiretamente para o identificador de chave de evento in-app af\_id.**

</Accordion>

As abas restantes são relevantes para **todos os relatórios de eventos in-app,** independentemente de incluírem fontes personalizadas ou não.

<div id="select-dimensions" />

<Accordion title="Selecionar dimensões">

Lembre-se de que os dados no nível de usuário não podem ser reportados pelo DCR. Em vez disso, ele fornece os insights de que você precisa para tomar decisões agregando (ou agrupando) os dados pelas dimensões que você escolher.

Uma dimensão geralmente é um atributo pelo qual você categoriza os usuários do aplicativo (por exemplo, localização geográfica, data de instalação, campanha etc.)

<div id="extracting-dimensions-from-event_value" />

#### **Extraindo dimensões de event\_value**

Quando eventos in-app são reportados à AppsFlyer por meio do SDK ou da API S2S, muitos dos dados brutos estão contidos em um único campo chamado event\_value. Esse campo de dados estruturados inclui todos os parâmetros específicos de eventos in-app que foram configurados para os eventos que seus aplicativos enviam à AppsFlyer.

Uma das principais vantagens dos relatórios de eventos in-app é que eles permitem que você extraia parâmetros específicos e seus valores do campo **event\_value** para os eventos que você escolher.

**Para extrair dimensões do campo event\_value para uso em relatórios DCR:**

1. Na lista **Dimensões das fontes**, clique no botão <Image alt="botão_extrair_dimensão.png" src="https://files.readme.io/c238da4a1d2a15fe2249070747fa6247db63ab4129b1c72804b84550675214f3-10754426767761.png" width="123px" /> .

   A janela **Extrair campo do event\_value** é aberta.
2. Na caixa **Campo Relatório**, insira o nome da dimensão extraída conforme você deseja que ela apareça em seu relatório.
3. Na lista de parâmetros **Event\_value** selecione o parâmetro de evento in-app que deve ser mapeado por padrão para o campo do relatório (dimensão) que você definiu na etapa 2.
   * Os parâmetros disponíveis incluem aqueles que foram configurados nos **eventos in-app selecionados** **nos aplicativos selecionados**.
4. Pode ser que o mapeamento padrão seja diferente por aplicativo e/ou evento. Se for esse o caso:
   1. Clique no botão **Adicionar exceção**
   2. Selecione o aplicativo e o evento para os quais o campo do relatório deve ser mapeado de forma diferente.
   3. Selecione o parâmetro de evento in-app que deve ser mapeado no campo do relatório para essa combinação de aplicativo/evento.
   4. Siga estas etapas para quantas exceções você quiser configurar.
5. Quando terminar de configurar o mapeamento para a dimensão extraída, clique em **Salvar e adicionar outra** para extrair outra dimensão do campo event\_value ou em **Salvar** para retornar à tela principal.

**Para editar as dimensões extraídas:**

1. Na lista **Dimensões das fontes** ou na lista de **dimensões do relatório**, passe o mouse sobre o nome da dimensão que você deseja editar.
2. Clique no botão <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> que é exibido à direita da dimensão.
3. Selecione **Editar campo extraído**.
4. Faça alterações no nome do **Campo Relatório** e/ou no mapeamento de parâmetros conforme necessário.
5. Clique em **Salvar** para salvar suas alterações.

**Para excluir as dimensões extraídas:**

1. Na lista **Dimensões das fontes** ou na lista de **dimensões do relatório**, passe o mouse sobre o nome da dimensão que você deseja excluir.
2. Clique no botão <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> que é exibido à direita da dimensão.
3. Selecione **Excluir campo.**
   * **Atenção!** Se você excluir um campo extraído da lista **Dimensões do relatório**, ele excluirá a definição do campo extraído. Se você quiser remover o campo do relatório enquanto preserva sua definição, selecione o campo e, em vez disso, use o botão **Remover**.

<div id="selecting-report-dimensions" />

#### **Selecionando dimensões do relatório**

As dimensões do relatório de eventos in-app podem incluir:

* Dimensões que você extraiu do event\_value
* [Dimensões padrão de eventos in-app](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)
* Qualquer campo nas fontes personalizadas do relatório que tenha sido <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#3-define-the-source-structure">categorizado como uma dimensão</Anchor> (se aplicável)

**Para selecionar as dimensões a serem incluídas em seu relatório:**

1. Selecione uma ou mais dimensões na lista **Dimensões das fontes** à esquerda e use o botão **Adicionar** no meio da tela para adicioná-las à lista **Dimensões do relatório.**
   * Você pode usar a barra de pesquisa para pesquisar dimensões nas listas.
2. Para remover uma dimensão, selecione-a na lista **Dimensões do relatório** e use o botão **Remover** para retorná-la à lista **Dimensões das fontes**.
3. Repita este processo até que você tenha adicionado cada dimensão que deseja incluir nos relatórios do DCR.

**Observação:** Por padrão, todos os relatórios são agrupados pela dimensão de evento in-app **media\_source.** Se você não quiser usar essa dimensão em seu relatório, você pode removê-la da lista **Dimensões do relatório**.

<div id="optional-customizing-dimension-display-names" />

#### **[Opcional] Personalizando nomes de exibição de dimensões**

Por padrão, os nomes das dimensões são exibidos em seu relatório exatamente como são nomeados nos dados de eventos in-app ou em suas fontes personalizadas. Se desejar, você pode personalizar os nomes das dimensões do seu relatório.

**Para personalizar os nomes de exibição da dimensão:**

1. Na lista **Dimensões do relatório**, passe o mouse sobre o nome da dimensão que você deseja editar.
2. Clique no botão de edição ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que é exibido à direita da dimensão.
3. Altere o nome para o nome de exibição da dimensão a ser usado em seu relatório (até 50 caracteres).
4. Clique em **OK** para salvar o nome de exibição ou em **X** para cancelá-lo.

**Observação:** Se você quiser alterar o nome de uma **dimensão extraída**, use as etapas para editar as dimensões extraídas (acima).

<div id="preserving-privacy-while-grouping-by-dimension-regrouping" />

#### **Preservando a privacidade ao agrupar por dimensão (reagrupamento)**

Dependendo do tamanho do seu conjunto de dados, do número de dimensões que você escolher e de outros fatores, é possível que um relatório inclua um ou mais grupos contendo poucos usuários para permitir a geração de relatórios. Se os dados fossem relatados dessa forma, isso violaria as restrições ao fornecimento de dados em nível de usuário.

No entanto, em vez de remover ou ocultar completamente os dados do relatório, o DCR usa um **mecanismo de reagrupamento** para fornecer o máximo de detalhes possível, mantendo a privacidade do usuário.

<div id="regrouping-example" />

> 📄 **Exemplo de reagrupamento**
>
> Suponha que você tenha configurado um relatório de acordo com as seguintes dimensões (em ordem):
>
> * **Dimensões do evento in-app:**
>   * fonte de mídia
>   * campanha
>   * adset\_name
>   * id\_anúncio
> * **Dimensões de origem personalizadas:**
>   * user\_type
>
> **Antes do reagrupamento**
>
> Após a análise inicial dos dados, o DCR determina que os dados seriam divididos da seguinte forma:
>
>
>
> | mídia  <br />fonte | campanha | nome do  <br />conjunto de anúncios | anúncio  <br />id | user  <br />Tipo | receita  <br />D0 | receita  <br />D7 | contagem | reportável? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | fonte\_de\_mídia | UA\_100 | green | kjh867 | comprador | 1 | 4 | 120 | ✓ |
> | fonte\_de\_mídia | UA\_101 | green | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | fonte\_de\_mídia | UA\_200 | green | lkh123 | beg | 6 | 7 | N | **N** |
> | fonte\_de\_mídia | UA\_200 | green | ilk945 | beg | 3 | 21 | N | **N** |
> | fonte\_de\_mídia | UA\_200 | green | plm654 | beg | 8 | 17 | N | **N** |
>
>
>
> Na forma atual, as 3 linhas finais não são reportáveis porque há poucos usuários em cada uma. (Essa fonte de mídia requer um mínimo de **y** usuários para ser reportável. Aqui, temos apenas **x.** )
>
> **De acordo com a lógica de reagrupamento, o DCR primeiro “elimina” a última dimensão de evento in-app listada (nesse caso, ad\_id).** Em seguida, ele analisa os dados novamente para ver quais linhas podem ser reportadas.
>
> **Depois de reagrupar**
>
> Depois de aplicar a lógica de reagrupamento, o relatório aparece da seguinte forma:
>
>
>
> | mídia  <br />fonte | campanha | nome do  <br />conjunto de anúncios | anúncio  <br />id | user  <br />Tipo | receita  <br />D0 | receita  <br />D7 | contagem | reportável? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | fonte\_de\_mídia | UA\_100 | green | kjh867 | comprador | 1 | 4 | 120 | ✓ |
> | fonte\_de\_mídia | UA\_101 | green | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | fonte\_de\_mídia | UA\_200 | green | RESTRITO | beg | 17 | 45 | y (x+x+x) | ✓ |
>
>
>
> **Resultados:**
>
> * A última linha agora combina os dados que estavam anteriormente em 3 linhas. Agora, a linha combinada tem uma contagem de usuários igual a **y** e pode ser reportada.
> * A dimensão que foi eliminada agora é reportada como RESTRITA.
> * Se ainda houvesse linhas não reportáveis (menos de **y** usuários), o DCR continuaria analisando os dados de forma iterativa, eliminando uma dimensão após a outra até que:
>   * pode reportar todas as linhas; ou
>   * fica sem dimensões de eventos in-app para eliminar
>
> **Observação:** Por padrão, o DCR aplica o reagrupamento somente às dimensões **[padrão do evento in-app](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)** (não às dimensões extraídas do evento in-app ou às dimensões de origem personalizadas). Se os dados agrupados por uma dimensão padrão de evento in-app resultarem em uma linha contendo menos de **y** usuários, os dados nessa linha serão relatados como RESTRITOS.
>
> * *Veja abaixo uma opção avançada que você também pode usar para aplicar o reagrupamento a dimensões de origem personalizadas.*

<div id="optional-managing-dimension-priority" />

#### **[Opcional] Gerenciando a prioridade da dimensão**

Por padrão, as dimensões de eventos in-app são eliminadas na ordem inversa da ordem em que aparecem na lista **Dimensões do relatório**. No entanto, você pode modificar a sequência padrão e/ou aplicar o reagrupamento às dimensões de origem personalizadas selecionadas (se aplicável) para preservar as dimensões mais importantes para você.

**Para alterar a ordem na qual as dimensões são eliminadas:**

1. Clique no botão **Gerenciar prioridade da dimensão**.
2. Selecione uma dimensão e arraste-a até a posição desejada na lista (ou use os botões de seta à direita para movê-la).
   * A dimensão rotulada como **Prioridade mais alta** (no topo da lista) significa que ela é a última a ser eliminada se o reagrupamento for necessário.
3. [Opcional] Para aplicar o reagrupamento às dimensões de origem personalizadas (para relatórios usando fontes personalizadas):
   1. Clique em **Usar opções avançadas para refinar o reagrupamento**
   2. Selecione dimensões de origem personalizadas às quais você gostaria de aplicar o reagrupamento.
   3. As dimensões selecionadas são adicionadas à lista **Gerenciar prioridades de dimensões**.
      * Por padrão, essas dimensões são adicionadas ao final da lista, como **Menor prioridade** para reagrupamento. No entanto, você pode reordená-las da mesma forma que as dimensões de eventos in-app, conforme descrito acima.
4. Clique em **OK** para salvar suas alterações.
   * A lista **Dimensões do relatório** na tela principal permanece em sua ordem original, mas a ordem revisada foi salva. (Clique novamente no botão **Gerenciar prioridade da dimensão** se quiser revisar ou editar sua seleção.)

</Accordion>

<div id="select-metrics" />

<Accordion title="Selecionar métricas">

As métricas são os dados numéricos que você coletou com relação a um usuário do aplicativo (exemplos podem incluir receita, número de aberturas de aplicativos, LTV etc.) e podem ser qualquer campo de dados numéricos de suas fontes que você categorizou como métrica.

<div id="extracting-metrics-from-event_value" />

#### **Extraindo métricas de event\_value**

Assim como você pode fazer com as [dimensões do relatório](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions), você pode extrair parâmetros de eventos no aplicativo do campo **event\_value** para usar como métricas em seus relatórios.

**Para extrair dimensões do campo event\_value para uso em relatórios DCR:**

1. Na lista **Métricas de fontes**, clique no botão <Image alt="extract_metric_button.png" src="https://files.readme.io/93ca5970968816d452331df4ce5ff4cfb678cbb24f65eb99fe01bd3bb3016959-10755235273233.png" width="102px" /> .

   A janela **Extrair campo do event\_value** é aberta.
2. Na caixa d**Campo Relatório**, insira o nome da métrica extraída conforme você gostaria que ela aparecesse em seu relatório.
3. Na lista de parâmetros **Event\_value** selecione o parâmetro de evento in-app que deve ser mapeado por padrão para o campo do relatório (métrica) que você definiu na etapa 2.
   * Os parâmetros disponíveis incluem aqueles que foram configurados nos **eventos in-app selecionados** **nos aplicativos selecionados**.
4. Pode ser que o mapeamento padrão seja diferente por aplicativo e/ou evento. Se for esse o caso:
   1. Clique no botão **Adicionar exceção**
   2. Selecione o aplicativo e o evento para os quais o campo do relatório deve ser mapeado de forma diferente.
   3. Selecione o parâmetro de evento in-app que deve ser mapeado no campo do relatório para essa combinação de aplicativo/evento.
   4. Siga estas etapas para quantas exceções você quiser configurar.
5. Quando terminar de configurar o mapeamento para a métrica extraída, clique em **Salvar e adicionar outra** para extrair outra métrica do campo event\_value ou em **Salvar** para retornar à tela principal.

**Para editar as métricas extraídas:**

1. Na lista **Métricas das fontes** ou na lista **Métricas do relatório**, passe o mouse sobre o nome da métrica que você deseja editar.
2. Clique no botão <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> que é exibido à direita da métrica.
3. Selecione **Editar campo extraído**.
4. Faça alterações no nome do **Campo Relatório** e/ou no mapeamento de parâmetros conforme necessário.
5. Clique em **Salvar** para salvar suas alterações.

**Para excluir métricas extraídas:**

1. Na lista **Métricas das fontes** ou na lista **Métricas do relatório**, passe o mouse sobre o nome da métrica que você deseja excluir.
2. Clique no botão <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> que é exibido à direita da métrica.
3. Selecione **Excluir campo.**
   * **Atenção!** Se você excluir um campo extraído da lista **Métricas do relatório**, ele excluirá a definição do campo extraído. Se você quiser remover o campo do relatório enquanto preserva sua definição, selecione o campo e, em vez disso, use o botão **Remover**.

<div id="select-report-metrics" />

#### **Selecione as métricas do relatório**

**Para selecionar as métricas a serem incluídas em seu relatório:**

1. Selecione uma ou mais métricas na lista **Métricas das fontes** à esquerda e use o botão **Adicionar** no meio da tela para adicioná-las à lista **Métricas do relatório.**
   * Você pode usar a barra de busca para pesquisar as métricas das listas.
2. Para cada métrica na lista de **Métricas do relatório**, selecione se você deseja que os dados sejam relatados da seguinte forma:
   * uma soma de valores numéricos; ou
   * uma contagem de valores distintos
3. Para remover uma métrica, selecione-a na lista **Dimensões da métrica** e use o botão **Remover** para retorná-la à lista **Métricas das fontes**.
4. Repita este processo até que você tenha adicionado cada métrica que deseja incluir no relatório.

<div id="optional-customizing-metric-display-names" />

#### **[Opcional] Personalizando nomes de exibição de métricas**

Por padrão, os nomes das métricas são exibidos em seu relatório exatamente como são nomeados nos dados de eventos in-app ou em suas fontes personalizadas. Se desejar, você pode personalizar os nomes das métricas para seu relatório.

**Para personalizar nomes de exibição de métricas:**

1. Na lista **Dimensões da métrica**, passe o mouse sobre o nome da métrica que você deseja editar.
2. Clique no botão de edição ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que é exibido à direita da métrica.
3. Altere o nome para o nome de exibição da métrica a ser usado em seu relatório (até 50 caracteres).
4. Clique em **OK** para salvar o nome de exibição ou em **X** para cancelá-lo.

**Observação:** Se você quiser alterar o nome de uma **métrica extraída**, use as etapas para editar as métricas extraídas (acima).

<div id="optional-select-identifiers-to-count" />

#### **[Opcional] Selecione identificadores para contar**

Por padrão, cada linha do relatório termina com uma coluna contendo uma contagem dos IDs distintos da AppsFlyer agrupados nos dados dessa linha.

**Se você quiser adicionar colunas para as contagens distintas de outros identificadores de suas fontes, faça o seguinte:**

1. Selecione um ou mais identificadores na lista **Identificadores das fontes** à esquerda e use o botão **Adicionar** no meio da tela para adicioná-las à lista **Identificadores de contagem distinta**.
   * Você pode usar a barra de busca para pesquisar os identificadores nas listas.
2. Para remover um identificador, selecione-o na lista **Identificadores de contagem distinta** e use o botão **Remover** para retorná-lo à lista **Identificadores de fontes**.
3. Repita este processo até que você tenha adicionado cada identificador que você quer que seja contado no relatório.

</Accordion>

<div id="configure-report-settings-and-save-the-report" />

<Accordion title="Defina as configurações do relatório e salve o relatório">

<div id="schedule-only-for-reports-without-custom-sources" />

#### **Cronograma (somente para relatórios sem fontes personalizadas)**

Os relatórios sem fontes personalizadas são executados de acordo com o cronograma definido por você.

**Para definir o cronograma do relatório:**

1. Selecione se deseja executar o relatório diariamente ou em um ou mais dias por semana.
2. Selecione a hora em que o relatório será executado (o fuso horário é UTC).

<div id="important-1" />

> 🚧 **Importante!**
>
> As opções de agendamento estão desativadas para relatórios que usam fontes personalizadas. Esse tipo de relatório é executado sempre que novas versões de todas as <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-creating-attribution-data-reports#fontes-personalizadas">fontes personalizadas que ele usa</Anchor> são detectadas:
>
> * Para fontes localizadas em **armazéns de dados** (BigQuery e Snowflake), o DCR reconhece que uma nova versão de uma fonte foi criada quando detecta um novo valor na coluna da tabela de origem. `v`
>   * **Importante!** Para garantir a integridade do seu relatório, certifique-se de preencher a tabela de origem com um conjunto completo de dados sempre que o valor da coluna for alterado.
> * Para fontes localizadas em **compartimentos de armazenamento em nuvem** (Amazon S3 e GCS), o DCR reconhece que uma nova versão de uma fonte foi criada quando detecta que uma <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#atualizando-fontes-para-acionar-o-processamento-de-relatórios">nova versão de um arquivo de origem foi carregada junto com o arquivo \_SUCCESS</Anchor> que o acompanha.
>
> A AppsFlyer procura continuamente por novas versões de arquivos fonte para a **data atua e 2 dias antes.**

<div id="report-destination" />

#### **Destino do relatório:**

O DCR entrega relatórios para seus serviços de nuvem selecionados usando o <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker da AppsFlyer</Anchor>. Portanto, especificar o destino do relatório envolve selecionar ou criar uma conexão com o Data Locker.

* **Observação:** para receber relatórios do DCR não é necessário uma assinatura premium do Data Locker. Se você estiver interessado em receber outros relatórios da AppsFlyer por meio do Data Locker, entre em contato com seu CSM ou envie um e-mail para **hello@appsflyer.com**.

**Para definir o destino do relatório e salvá-lo:**

1. Selecione na lista de conexões do Data Locker disponíveis em sua conta da AppsFlyer.
   * Se não houver conexões definidas em sua conta:
     * Uma nova guia será aberta em seu navegador (mostrando a página do Data Locker da AppsFlyer)
     * Um diálogo de **Nova conexão** abrirá. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#concluir-a-conexão-1">estas instruções</Anchor> para criar a conexão.
   * clique no botão ![dcr_new_connection_data_locker_button.png](https://files.readme.io/9850a4b8ea4f40f6320903c545c51add7b90207538a27c83a3b02a41197ba567-14995870859281.png) :
     * Uma nova aba será aberta em seu navegador (mostrando a página do Data Locker da AppsFlyer)
     * Um diálogo de **Nova conexão** abrirá. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#concluir-a-conexão-1">estas instruções</Anchor> para criar a conexão.
   * Depois de criar a conexão, retorne à aba DCR em seu navegador e selecione a conexão recém-criada na lista de conexões do Data Locker.
2. Clique em **Salvar** para salvar o relatório.
3. O novo relatório agora é exibido na aba **Relatórios** da aba **Data Clean Room.**

</Accordion>

<div id="reference" />

## Referência

<div id="default-inapp-event-dimensions" />

<Accordion title="Dimensões padrão de eventos in-app">

Além das dimensões extraídas de **event\_value** e das dimensões de suas fontes personalizadas (se aplicável), as seguintes dimensões de eventos in-app podem ser usadas para agrupar relatórios:

* media\_source *([incluído como uma dimensão de relatório por padrão)](#selecionando-dimensões-do-relatório)*
* anúncio
* id\_anúncio
* ad\_type
* id\_conjunto\_de\_anúncios
* adset\_name
* ativado
* app\_version
* tipo\_de\_toque\_atribuído
* Marca
* campanha
* id\_da\_campanha
* Canal
* cidade
* tipo\_de\_conversão
* país
* device\_type
* dma
* engagement\_type
* nome\_do\_evento
* event\_currency
* geo\_region
* is\_attributed
* keywords
* match\_type
* Modelo
* parceiro
* platforma
* id\_do\_site

</Accordion>

<div id="default-inapp-event-metrics" />

<Accordion title="Métricas padrão de eventos in-app">

Além das métricas extraídas do **event\_value** e das métricas de suas fontes personalizadas (se aplicável), as seguintes métricas de eventos in-app podem ser incluídas nos relatórios:

* event\_revenue
* event\_revenue\_u\_s\_d

</Accordion>

<div data-zendesk-anchors="creating-an-inapp-event-report=cria%C3%A7%C3%A3o-de-um-relat%C3%B3rio-de-eventos-in-app h_01HA9W7NP4CR9CVXY9CXENYSPF=cria%C3%A7%C3%A3o-de-um-relat%C3%B3rio-de-eventos-in-app h_01HA9W7NP4B55Y2SB6ADKE06JV=perform-preliminary-steps h_01HA9W7NP4A7YK5JFYNFXFY6ZJ=select-sources inapp-event-sources=fontes-de-eventos-in-app h_01HA9W7NP4G0S2TQT9W2RK1QBA=fontes-de-eventos-in-app custom-sources=fontes-de-dados h_01HA9W7NP46D57Q7H8611K4KBB=fontes-de-dados h_01HA9W7NP4K2055TXTE98HWTAW=join-sources-only-for-reports-containing-custom-sources what-is-a-key-identifier=o-que-%C3%A9-um-identificador-de-chave h_01HA9W7NP4WTBJ83MY73JQ2ESH=o-que-%C3%A9-um-identificador-de-chave h_01HA9W7NP5N8W4X8H1WRN1183Z=importante mapping-schemes-directindirect=esquemas-de-mapeamento-diretoindireto h_01HA9W7NP51HWA36BBP1JC3HMW=esquemas-de-mapeamento-diretoindireto h_01HA9W7NP5V1SV5PGF277G5P6T=exemplo h_01HA9W7NP56M09TF9CB7FCBPBR=select-dimensions extracting-dimensions-from-event_value=extraindo-dimens%C3%B5es-de-event_value h_01HA9W7NP5BV7GJXMEMS57HNJ9=extraindo-dimens%C3%B5es-de-event_value selecting-report-dimensions=selecionando-dimens%C3%B5es-do-relat%C3%B3rio h_01HA9W7NP5S6EWDE38Q6T42QEB=selecionando-dimens%C3%B5es-do-relat%C3%B3rio %5Boptional%5D-customizing-dimension-display-names=opcional-personalizando-nomes-de-exibi%C3%A7%C3%A3o-de-dimens%C3%B5es h_01HA9W7NP5YC8E3B05GV7J1Z5V=opcional-personalizando-nomes-de-exibi%C3%A7%C3%A3o-de-dimens%C3%B5es preserving-privacy-while-grouping-by-dimension-regrouping=preservando-a-privacidade-ao-agrupar-por-dimens%C3%A3o-reagrupamento h_01HA9W7NP5XJGK4CXNHK02NYT4=preservando-a-privacidade-ao-agrupar-por-dimens%C3%A3o-reagrupamento h_01HA9W7NP596RGHA1BES64GSK1=exemplo-de-reagrupamento %5Boptional%5D-managing-dimension-priority=opcional-gerenciando-a-prioridade-da-dimens%C3%A3o h_01HA9W7NP5781HV31T5DAYSMMT=opcional-gerenciando-a-prioridade-da-dimens%C3%A3o h_01HA9W7NP6WCSRSH157P78QEQF=select-metrics extracting-metrics-from-event_value=extraindo-m%C3%A9tricas-de-event_value h_01HA9W7NP6JEXE67A935BJ93AQ=extraindo-m%C3%A9tricas-de-event_value select-report-metrics=selecione-as-m%C3%A9tricas-do-relat%C3%B3rio h_01HA9W7NP6EF23ZDGZHDKVTS7V=selecione-as-m%C3%A9tricas-do-relat%C3%B3rio %5Boptional%5D-customizing-metric-display-names=opcional-personalizando-nomes-de-exibi%C3%A7%C3%A3o-de-m%C3%A9tricas h_01HA9W7NP6X584YAXT030A6BEY=opcional-personalizando-nomes-de-exibi%C3%A7%C3%A3o-de-m%C3%A9tricas %5Boptional%5D-select-identifiers-to-count=opcional-selecione-identificadores-para-contar h_01HA9W7NP6YETQ1ND0K8XZTZZ0=opcional-selecione-identificadores-para-contar h_01HA9W7NP6ZH3KRN7YNWCPFZC9=configure-report-settings-and-save-the-report schedule-only-for-reports-without-custom-sources=cronograma-somente-para-relat%C3%B3rios-sem-fontes-personalizadas h_01HA9W7NP62DCR2SWD8X4M61R7=cronograma-somente-para-relat%C3%B3rios-sem-fontes-personalizadas h_01HA9W7NP6XQE1MN0J08FE89V4=importante-1 report-destination=destino-do-relat%C3%B3rio h_01HA9W7NP6BQYAF3RMZSW747HH=destino-do-relat%C3%B3rio reference=refer%C3%AAncia h_01HA9W7NP6BS0TE332GNPTW9M1=refer%C3%AAncia h_01HA9W7NP606HF0MSPQ4S09YRS=default-inapp-event-dimensions h_01HA9W7NP6A1N25KQ947J3EJW3=default-inapp-event-metrics" />

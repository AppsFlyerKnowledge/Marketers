---
title: Data Clean Room — Criando relatórios de dados de atribuição
metadata:
  keywords:
    - Premium Feature
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-09-11T10:42:43Z'
  edited_at: '2026-08-19T00:05:35Z'
  id: 9035047905297
  locale: pt
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/pt/articles/9035047905297
---
> **Visão geral:** Crie relatórios de dados de atribuição para combinar dados de nível de usuário de instalações/eventos de retargeting com dados de seus sistemas.

## Criando um relatório de dados de atribuição

**Para criar um relatório de dados de atribuição, siga as etapas detalhadas nas abas abaixo.**

**Observação:** Essas etapas são divididas em abas para facilitar a leitura. Todas as etapas devem ser concluídas para criar o relatório.

<div id="perform-preliminary-steps" />

<Accordion title="Execute etapas preliminares">

1. Vá para a aba **Relatórios** do **DCR.**
2. Clique no botão **+ Novo relatório**.
3. Selecione **Dados de atribuição** como o tipo de dados de origem e clique em **Avançar** no canto inferior direito da tela.
4. Insira um nome para o relatório
   * Pode ser qualquer nome que ajude você a identificar o relatório na plataforma DCR.
   * **Importante!** Certifique-se de que o nome do relatório é diferente de todos os outros relatórios em sua conta ou você não poderá **salvá-lo**.
   * Requisitos do nome do relatório:
     * Duração: 2-80 caracteres
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

Especifique os dados a serem usados para o relatório:

#### **Fontes de dados de atribuição**

* **Aplicativos:** Selecione um ou mais dos aplicativos em sua conta da AppsFlyer.
* **Tipos de atribuição:** Selecione um ou mais tipos de dados de atribuição a serem usados no relatório:

| Instalações | Uma instalação é registrada quando um usuário faz o download, instala e inicializa um aplicativo móvel. |
| --- | --- |
| Reinstalações | Uma reinstalação é registrada quando um usuário instala um aplicativo, depois o desinstala e reinstala durante a janela de reatribuição.<ul><li>**Observação**: A duração da janela de reatribuição é definida em Configurações > Configurações do aplicativo.</li></ul> |
| Reengajamentos | Um reengajamento é registrado quando um usuário inativo de um aplicativo específico engaja com com uma campanha de retargeting para o aplicativo e, posteriormente, a lança. |
| Reatribuições | Uma reatribuição é registrada quando um ex-usuário de um aplicativo específico (que o desinstalou) engaja com uma campanha de retargeting para o aplicativo e, posteriormente, o reinstala. |
| Instalações orgânicas | Instalações orgânicas são aquelas não atribuídas a um canal de mídia específico.<ul><li>**Observação**: Incluir instalações orgânicas em seu relatório pode aumentar significativamente o número de linhas escaneadas.</li></ul> |

* **Período de tempo:** Selecione o número de dias de dados históricos que você deseja que o DCR pesquise eventos de atribuição que correspondem a eventos de fontes personalizadas (de 1 a 180 dias).

#### **Fontes personalizadas**

Ao definir a estrutura do relatório, você pode escolher usar dados de qualquer uma das <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources">fontes personalizadas que você configurou</Anchor>.

</Accordion>

<div id="join-sources" />

<Accordion title="Juntar fontes">

Para combinar os dados entre as fontes, cada uma das fontes **personalizadas** usadas no relatório deve incluir um <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services">identificador</Anchor> mapeado para um **identificador de chave** nos dados de atribuição.

#### **O que é um identificador de chave?**

Você pode mapear para qualquer um desses identificadores dados de atribuição **identificadores-chave**:

* Identificador de aplicativo exclusivo gerado pela AppsFlyer na instalação.
  * O ID aparece em todos os eventos registrados pela AppsFlyer.
  * Um novo ID da AppsFlyer é gerado se um aplicativo for excluído e depois reinstalado.
* **ID de usuário do cliente (CUID)** Um identificador de usuário exclusivo geralmente gerado e definido pelo proprietário do aplicativo no momento do registro do usuário.
  * O uso do CUID para mapear dados exige que seu aplicativo esteja configurado para <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">enviar o CUID à AppsFlyer</Anchor> por meio do SDK ou da API de servidor para servidor (S2S).

> 🚧 **Importante!**
>
> Nem todos os canais de mídia permitem a correspondência usando CUID. É altamente recomendável usar o ID da AppsFlyer.

#### **Esquemas de mapeamento (direto/indireto)**

Se o relatório usar mais de uma fonte personalizada, somente uma delas precisará ser mapeada **diretamente** para um identificador de chave da dados de atribuição. Outras fontes personalizadas podem ser mapeadas **direta ou indiretamente,** conforme ilustrado no exemplo a seguir:

> 📄 **Exemplo**
>
> ![dcr_mapping_identifiers_attribution_data.png](https://files.readme.io/18d1ddd8305f790dc621f871695b8cfb30f5e5a5d758c219e76ec7822ec18f2f-9969690360849.png)
>
> No cenário mostrado acima:
>
> * O identificador de fonte #1 personalizado **AF** é mapeado diretamente para o identificador de chave de dados de atribuição de atribuição **af\_id.**
> * A fonte personalizada #2 é mapeada indiretamente: **user\_code** --> **AF** --> **af\_id.**
> * A fonte personalizada #3 é mapeada indiretamente (por meio de uma cadeia mais longa):
>   **user\_id** --> **user\_code** --> **AF** --> **af\_id.**
> * O identificador de fonte #4 personalizado **ID** é mapeado diretamente para o identificador de chave de dados de atribuição de atribuição **af\_id.**
>   * Observe que, em vez disso, ele poderia ter sido mapeado indiretamente (por meio do identificador **user\_id** da fonte personalizada #3), mas qualquer uma das opções funciona bem.
>
> ✓ Esse esquema de mapeamento funciona para combinar dados entre todas as fontes, já que cada fonte personalizada é mapeada direta ou indiretamente para o identificador de chave de dados de atribuição **af\_id.**

</Accordion>

<div id="determine-treatment-of-multiple-matching-events" />

<Accordion title="Determinar o tratamento de vários eventos correspondentes">

> 📘 **Observação**
>
> Se os tipos de atribuição selecionados para este relatório **incluírem apenas instalações e/ou instalações orgânicas,** esta seção será irrelevante. Pular para **[Selecionar dimensões](/docs/data-clean-room-creating-attribution-data-reports#select-dimensions).**

**reengajamentos ou reatribuições,** é possível que os dados de atribuição incluam mais de um evento durante o período selecionado com o mesmo identificador de chave. Quando esse for o caso, você deve instruir o DCR sobre quais eventos correspondentes ele deve incluir no relatório.

#### **Correspondendo todos os eventos**

O método de correspondência mais abrangente permite que seu relatório inclua todos os eventos correspondentes. Para atingir esse resultado, você deve mapear um identificador em uma das fontes personalizadas do relatório para o identificador de dados de atribuição **install\_time.**

* O identificador na sua fonte que é mapeado para install\_time deve estar no seguinte formato: **aaaa-MM-dd HH:mm:ss.**
* **Observação:** Embora o nome do identificador de dados de atribuição seja install\_time, na verdade ele significa **hora do evento** ao se referir a eventos de reinstalação, reengajamento ou reatribuição.

#### **Correspondendo um único evento**

Se os tipos de atribuição selecionados para seu relatório incluírem reinstalações, reengajamentos ou reatribuições, mas você não mapear um identificador para **install\_time,** deverá optar por usar o **último** ou **o primeiro** evento correspondente em seu relatório.

O comportamento da correspondência de evento único difere quando a fonte de dados de atribuição do AppsFlyer é usada sozinha ou combinada com fontes personalizadas.

* Quando a fonte de dados de atribuição é usada sozinha, o AppsFlyer seleciona o evento correspondente com o `event_time` mais recente no intervalo de tempo que corresponde a um identificador de chave específico.
* Se os tipos de atribuição selecionados para seu relatório incluírem **reinstalações,**
  * **Último evento:** O evento de atribuição incluído no relatório é o último evento (cronologicamente) no período que corresponde a um identificador de chave específico.
  * **Primeiro evento:** O evento de atribuição incluído no relatório é o primeiro evento (cronologicamente) no período que corresponde a um identificador de chave específico.

Faça essa seleção com base no evento que você considera mais relevante para os insights que deseja obter do relatório.

> 📘 **Observação:**
>
> Em caso de registros duplicados, o DCR remove a duplicação de registros com o mesmo `appsflyer_id`, selecionando o evento mais recente com base no `event_time`.

</Accordion>

<div id="select-dimensions" />

<Accordion title="Selecionar dimensões">

Lembre-se de que os dados no nível de usuário não podem ser reportados pelo DCR. Em vez disso, ele fornece os insights de que você precisa para tomar decisões agregando (ou agrupando) os dados pelas dimensões que você escolher.

Uma dimensão geralmente é um atributo pelo qual você categoriza os usuários do aplicativo (por exemplo, localização geográfica, data de instalação, campanha etc.)

#### **Selecionando dimensões do relatório**

As dimensões do relatório de dados de atribuição podem incluir:

* Qualquer [dimensão de dados de atribuição disponível](/docs/data-clean-room-creating-attribution-data-reports#available-attribution-data-dimensions)
* Qualquer campo nas fontes personalizadas do relatório que tenha sido <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#3-define-the-source-structure">categorizado como uma dimensão</Anchor>

**Para selecionar as dimensões a serem incluídas em seu relatório:**

1. Selecione uma ou mais dimensões na lista **Dimensões das fontes** à esquerda e use o botão **Adicionar** no meio da tela para adicioná-las à lista **Dimensões do relatório.**  
   * Você pode usar a barra de pesquisa para pesquisar dimensões nas listas.
2. Para remover uma dimensão, selecione-a na lista **Dimensões do relatório** e use o botão **Remover** para retorná-la à lista **Dimensões das fontes**.
3. Repita este processo até que você tenha adicionado cada dimensão que deseja incluir nos relatórios do DCR.

**Observação:** Por padrão, todos os relatórios são agrupados pela dimensão de dados de atribuição **media\_source.** Se você não quiser usar essa dimensão em seu relatório, você pode removê-la da lista **Dimensões do relatório**.

#### **[Opcional] Personalizando nomes de exibição de dimensões**

Por padrão, os nomes das dimensões são exibidos em seu relatório exatamente como são nomeados nos dados de atribuição ou em suas fontes personalizadas. Se desejar, você pode personalizar os nomes das dimensões do seu relatório.

**Para personalizar os nomes de exibição da dimensão:**

1. Na lista **Dimensões do relatório**, passe o mouse sobre o nome da dimensão que você deseja editar.
2. Clique no botão de edição ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que é exibido à direita da dimensão.
3. Altere o nome para o nome de exibição da dimensão a ser usado em seu relatório (até 50 caracteres).
4. Clique em **OK** para salvar o nome de exibição ou em **X** para cancelá-lo.

#### Preservando a privacidade ao agrupar por dimensão (reagrupamento)

Dependendo do tamanho do seu conjunto de dados, do número de dimensões que você escolher e de outros fatores, é possível que um relatório inclua um ou mais grupos contendo poucos usuários para permitir a geração de relatórios. Se os dados fossem relatados dessa forma, isso violaria as restrições ao fornecimento de dados em nível de usuário.

* **Importante!** O número mínimo de usuários necessário para permitir a reportagem varia de acordo com o canal de mídia.

No entanto, em vez de remover ou ocultar completamente os dados do relatório, o DCR usa um **mecanismo de reagrupamento** para fornecer o máximo de detalhes possível, mantendo a privacidade do usuário.

> 📄 **Exemplo de reagrupamento**
>
> Suponha que você tenha configurado um relatório de acordo com as seguintes dimensões (em ordem):
>
> * **Dimensões de dados de atribuição:**
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
> | mídia  <br />fonte | campanha | nome do  <br />conjunto de anúncios | anúncio  <br />id | user  <br />Tipo | rev  <br />D0 | rev  <br />D7 | contagem | reportável? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | fonte\_de\_mídia | UA\_100 | green | kjh867 | comprador | 1 | 4 | 120 | ✓ |
> | fonte\_de\_mídia | UA\_101 | green | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | fonte\_de\_mídia | UA\_200 | green | lkh123 | beg | 6 | 7 | N | **N** |
> | fonte\_de\_mídia | UA\_200 | green | ilk945 | beg | 3 | 21 | N | **N** |
> | fonte\_de\_mídia | UA\_200 | green | plm654 | beg | 8 | 17 | N | **N** |
>
>
>
> Na forma atual, as 3 linhas finais não são reportáveis porque há poucos usuários em cada uma. (Esse canal de mídia requer um mínimo de **y** usuários para ser reportável. Aqui, temos apenas **x.** )
>
> **De acordo com a lógica de reagrupamento, o DCR primeiro “elimina” a última dimensão de dados de atribuição listada (nesse caso, ad\_id).** Em seguida, ele analisa os dados novamente para ver quais linhas podem ser reportadas.
>
> **Depois de reagrupar**
>
> Depois de aplicar a lógica de reagrupamento, o relatório aparece da seguinte forma:
>
>
>
> | mídia  <br />fonte | campanha | nome do  <br />conjunto de anúncios | anúncio  <br />id | user  <br />Tipo | rev  <br />D0 | rev  <br />D7 | contagem | reportável? |
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
>   * fica sem dimensões de dados de atribuição para eliminar
>
> **Observação:** Por padrão, o DCR aplica o reagrupamento somente às [**dimensões de dados de atribuição**](/docs/data-clean-room-creating-attribution-data-reports#available-attribution-data-dimensions) (não às dimensões de fonte personalizadas). Se os dados agrupados por uma dimensão padrão de dados de atribuição resultarem em uma linha contendo menos de **y** usuários, os dados nessa linha serão relatados como RESTRITOS.
>
> * *Veja abaixo uma opção avançada que você também pode usar para aplicar o reagrupamento a dimensões de origem personalizadas.*

#### **[Opcional] Gerenciando a prioridade da dimensão**

Por padrão, as dimensões de dados de atribuição são eliminadas na ordem inversa da ordem em que aparecem na lista **Dimensões do relatório**. No entanto, você pode modificar a sequência padrão e/ou aplicar o reagrupamento às dimensões de origem personalizadas selecionadas para preservar as dimensões mais importantes para você.

**Para alterar a ordem na qual as dimensões são eliminadas:**

1. Clique no botão **Gerenciar prioridade da dimensão**.
2. Selecione uma dimensão e arraste-a até a posição desejada na lista (ou use os botões de seta à direita para movê-la).
   * A dimensão rotulada como **Prioridade mais alta** (no topo da lista) significa que ela é a última a ser eliminada se o reagrupamento for necessário.
3. [Opcional] Para aplicar o reagrupamento às dimensões de origem personalizadas:
   1. Clique em **Usar opções avançadas para refinar o reagrupamento**
   2. Selecione dimensões de origem personalizadas às quais você gostaria de aplicar o reagrupamento.
   3. As dimensões selecionadas são adicionadas à lista **Gerenciar prioridades de dimensões**.
      * Por padrão, essas dimensões são adicionadas ao final da lista, como **Menor prioridade** para reagrupamento. No entanto, você pode reordená-las da mesma forma que as dimensões de dados de atribuição, conforme descrito acima.
4. Clique em **OK** para salvar suas alterações.
   * A lista **Dimensões do relatório** na tela principal permanece em sua ordem original, mas a ordem revisada foi salva. (Clique novamente no botão **Gerenciar prioridade da dimensão** se quiser revisar ou editar sua seleção.)

</Accordion>

<div id="select-metrics" />

<Accordion title="Selecionar métricas">

As métricas são os dados numéricos que você coletou com relação a um usuário do aplicativo (exemplos podem incluir receita, número de aberturas de aplicativos, LTV etc.) e podem ser qualquer campo de dados **numéricos** de suas fontes que você categorizou como métrica.

**Para selecionar as métricas a serem incluídas em seu relatório:**

1. Selecione uma ou mais métricas na lista **Métricas das fontes** à esquerda e use o botão **Adicionar** no meio da tela para adicioná-las à lista **Métricas do relatório.**
   * Você pode usar a barra de busca para pesquisar as métricas das listas.
2. Para cada métrica na lista de **Métricas do relatório**, selecione se você deseja que os dados sejam relatados da seguinte forma:
   * uma soma de valores numéricos; ou
   * uma contagem de valores distintos
3. Para remover uma métrica, selecione-a na lista **Dimensões da métrica** e use o botão **Remover** para retorná-la à lista **Métricas das fontes**.
4. Repita este processo até que você tenha adicionado cada métrica que deseja incluir no relatório.

#### **[Opcional] Personalizando nomes de exibição de métricas**

Por padrão, os nomes das métricas são exibidos em seu relatório exatamente como são nomeados nos dados de atribuição ou em suas fontes personalizadas. Se desejar, você pode personalizar os nomes das métricas para seu relatório.

**Para personalizar nomes de exibição de métricas:**

1. Na lista **Dimensões da métrica**, passe o mouse sobre o nome da métrica que você deseja editar.
2. Clique no botão de edição ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que é exibido à direita da métrica.
3. Altere o nome para o nome de exibição da métrica a ser usado em seu relatório (até 50 caracteres).
4. Clique em **OK** para salvar o nome de exibição ou em **X** para cancelá-lo.

#### **[Opcional] Selecione identificadores para contar**

Por padrão, cada linha do relatório termina com uma coluna contendo uma contagem dos IDs distintos da AppsFlyer agrupados nos dados dessa linha.

**Se você quiser adicionar colunas para as contagens distintas de outros identificadores de suas fontes, faça o seguinte:**

1. Selecione um ou mais identificadores na lista **Identificadores das fontes** à esquerda e use o botão **Adicionar** no meio da tela para adicioná-las à lista **Identificadores de contagem distinta**.
   * Você pode usar a barra de busca para pesquisar os identificadores nas listas.
2. Para remover um identificador, selecione-o na lista **Identificadores de contagem distinta** e use o botão **Remover** para retorná-lo à lista **Identificadores de fontes**.
3. Repita este processo até que você tenha adicionado cada identificador que você quer que seja contado no relatório.

</Accordion>

<div id="set-the-report-destination-and-save-the-report" />

<Accordion title="Defina o destino do relatório e salve o relatório">

O DCR entrega relatórios para seus serviços de nuvem selecionados usando o <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker da AppsFlyer</Anchor>. Portanto, especificar o destino do relatório envolve selecionar ou criar uma conexão com o Data Locker.

* **Observação:** para receber relatórios do DCR não é necessário uma assinatura premium do Data Locker. Se você estiver interessado em receber outros relatórios da AppsFlyer por meio do Data Locker, entre em contato com seu CSM ou envie um e-mail para  [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Para definir o destino do relatório e salvá-lo:**

1. Selecione na lista de conexões do Data Locker disponíveis em sua conta da AppsFlyer.
   * Se não houver conexões definidas em sua conta:
     * Uma nova guia será aberta em seu navegador (mostrando a página do Data Locker da AppsFlyer)
     * Um diálogo de **Nova conexão** abrirá. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#concluir-a-conexão-1">estas instruções</Anchor> para criar a conexão.
   * Se você tiver conexões existentes, mas quiser usar uma nova, ![dcr_new_connection_data_locker_button.png](https://files.readme.io/9850a4b8ea4f40f6320903c545c51add7b90207538a27c83a3b02a41197ba567-14995870859281.png) button:
     * Uma nova guia será aberta em seu navegador (mostrando a página do Data Locker da AppsFlyer)
     * Um diálogo de **Nova conexão** abrirá. Siga <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-connections#concluir-a-conexão-1">estas instruções</Anchor> para criar a conexão.
   * Depois de criar a conexão, retorne à aba DCR em seu navegador e selecione a conexão recém-criada na lista de conexões do Data Locker.
2. Clique em **Salvar** para salvar o relatório.
3. O novo relatório agora é exibido na aba **Relatórios** da aba **Data Clean Room.**

</Accordion>

## Quando o relatório é executado?

Quando você tiver criado e salvo um relatório, o relatório é executado sempre que novas versões de todas as [fontes personalizadas que ele usa](/docs/data-clean-room-creating-attribution-data-reports#fontes-personalizadas) são detectadas:

* Para fontes localizadas em **armazéns de dados** (BigQuery e Snowflake), o DCR reconhece que uma nova versão de uma fonte foi criada quando detecta um novo valor na coluna da tabela de origem. `v`
  * **Importante!** Para garantir a integridade do seu relatório, certifique-se de preencher a tabela de origem com um conjunto completo de dados sempre que o valor da coluna for alterado.
* Para fontes localizadas em **compartimentos de armazenamento em nuvem** (Amazon S3 e GCS), o DCR reconhece que uma nova versão de uma fonte foi criada quando detecta que uma <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#atualizando-fontes-para-acionar-o-processamento-de-relatórios">nova versão de um arquivo de origem foi carregada junto com o arquivo \_SUCCESS</Anchor> que o acompanha.

A AppsFlyer procura continuamente por novas versões de arquivos fonte para a **data atua e 2 dias antes.**

## Referência

<div id="available-attribution-data-dimensions" />

<Accordion title="Dimensões de dados de atribuição disponíveis">

Além das dimensões de suas fontes personalizadas, as seguintes dimensões de dados de atribuição podem ser usadas para agrupar relatórios:

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
* contributor\_1\_campaign¹
* contributor\_1\_engagement\_type¹
* contributor\_1\_match\_type¹
* contributor\_1\_media\_source¹
* contributor\_1\_partner¹
* contributor\_1\_touch\_type¹
* contributor\_2\_campaign¹
* contributor\_2\_engagement\_type¹
* contributor\_2\_match\_type¹
* contributor\_2\_media\_source¹
* contributor\_2\_partner¹
* contributor\_2\_touch\_type¹
* contributor\_3\_campaign¹
* contributor\_3\_engagement\_type¹
* contributor\_3\_match\_type¹
* contributor\_3\_media\_fonte¹
* contributor\_3\_parceiro¹
* contributor\_3\_tipo de toque¹
* tipo\_de\_conversão
* país
* ID\_do\_cliente
* device\_type
* dma
* engagement\_type
* geo\_region
* keywords
* match\_type
* fonte\_de\_mídia
* Modelo
* original\_url
* parceiro
* platforma
* id\_do\_site

¹ *Para reengajamentos e reatribuições, os relatórios mostrarão esses campos como vazios.*

</Accordion>

<div data-zendesk-anchors="creating-an-attribution-data-report=criando-um-relat%C3%B3rio-de-dados-de-atribui%C3%A7%C3%A3o h_01HA9W4BCJSS2803JHV9K5KVP8=criando-um-relat%C3%B3rio-de-dados-de-atribui%C3%A7%C3%A3o h_01HA9W4BCJX9PJ2E4ADDC58GJ1=perform-preliminary-steps h_01HA9W4BCJNB64K3GZAKM7G0SS=select-sources attribution-data-sources=fontes-de-dados-de-atribui%C3%A7%C3%A3o h_01HA9W4BCJD51WM7504F94009R=fontes-de-dados-de-atribui%C3%A7%C3%A3o custom-sources=fontes-personalizadas h_01HA9W4BCJNRBD1NSWAH92B85V=fontes-personalizadas h_01HA9W4BCJW56NG637AZNP0DW0=join-sources what-is-a-key-identifier=o-que-%C3%A9-um-identificador-de-chave h_01HA9W4BCJ6A5EVFVR6G2SHEQD=o-que-%C3%A9-um-identificador-de-chave h_01HA9W4BCJ2GAZ96FHNN3HP6BY=importante mapping-schemes-directindirect=esquemas-de-mapeamento-diretoindireto h_01HA9W4BCJ6ZT4DSE3J5364D2C=esquemas-de-mapeamento-diretoindireto h_01HA9W4BCJKA8AWQGEHGQ5JT4P=exemplo h_01HA9W4BCJ6ZM47HQMARQ50ZQ1=determine-treatment-of-multiple-matching-events h_01HA9W4BCJE9ABACTWWTNJXVVQ=observa%C3%A7%C3%A3o matching-all-events=correspondendo-todos-os-eventos h_01HA9W4BCJ6FPCNP8K8D2CR1ST=correspondendo-todos-os-eventos matching-a-single-event=correspondendo-um-%C3%BAnico-evento h_01HA9W4BCJ99Z4A16N05799VZS=correspondendo-um-%C3%BAnico-evento 01JFZ2GJTJ566AWS3Z3KTWNMVE=observa%C3%A7%C3%A3o-1 h_01HA9W4BCKDVYTG08M2CWBWYC3=select-dimensions selecting-report-dimensions=selecionando-dimens%C3%B5es-do-relat%C3%B3rio h_01HA9W4BCKWCDWB4W0HZM4Z6E7=selecionando-dimens%C3%B5es-do-relat%C3%B3rio %5Boptional%5D-customizing-dimension-display-names=opcional-personalizando-nomes-de-exibi%C3%A7%C3%A3o-de-dimens%C3%B5es h_01HA9W4BCKEW1Z25ZXS9EXZYSA=opcional-personalizando-nomes-de-exibi%C3%A7%C3%A3o-de-dimens%C3%B5es preserving-privacy-while-grouping-by-dimension-regrouping=preservando-a-privacidade-ao-agrupar-por-dimens%C3%A3o-reagrupamento h_01HA9W4BCKA4248PEYNWZS87EW=preservando-a-privacidade-ao-agrupar-por-dimens%C3%A3o-reagrupamento regrouping-example=exemplo-de-reagrupamento h_01HA9W4BCK41W87486KG4RAAX8=exemplo-de-reagrupamento %5Boptional%5D-managing-dimension-priority=opcional-gerenciando-a-prioridade-da-dimens%C3%A3o h_01HA9W4BCKHABH7K80DKAQDDTR=opcional-gerenciando-a-prioridade-da-dimens%C3%A3o h_01HA9W4BCK1G0A2HTYRDQTMF5B=select-metrics %5Boptional%5D-customizing-metric-display-names=opcional-personalizando-nomes-de-exibi%C3%A7%C3%A3o-de-m%C3%A9tricas h_01HA9W4BCKZTAP4AWMNJKEKX2E=opcional-personalizando-nomes-de-exibi%C3%A7%C3%A3o-de-m%C3%A9tricas %5Boptional%5D-select-identifiers-to-count=opcional-selecione-identificadores-para-contar h_01HA9W4BCK5Y97RFYEMT24BABV=opcional-selecione-identificadores-para-contar h_01HA9W4BCKE1P7TBJANN0PD03D=set-the-report-destination-and-save-the-report when-does-the-report-run=quando-o-relat%C3%B3rio-%C3%A9-executado h_01HA9W4BCK3GX1KMVAXN5ZKA3A=quando-o-relat%C3%B3rio-%C3%A9-executado reference=refer%C3%AAncia h_01HA9W4BCK0VHS90ZXX00BF80N=refer%C3%AAncia h_01HA9W4BCMAYC661HFNRY3HWY2=available-attribution-data-dimensions" />

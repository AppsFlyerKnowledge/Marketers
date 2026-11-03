---
title: Incrementalidade para remarketing
metadata:
  keywords:
    - Analytics
    - Audiences
    - Advertisers
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2020-05-29T19:29:03Z'
  edited_at: '2026-08-19T00:35:36Z'
  id: 360009360978
  locale: pt
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/pt/articles/360009360978
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** Entenda como a Incrementalidade mensura o aumento incremental gerado por campanhas de retargeting.

## O que é a incrementalidade?

Provavelmente, a melhor maneira de compreender a análise da incrementalidade é através de um exemplo:

Digamos que você fez recentemente uma campanha de remarketing. Por uma questão de simplicidade, diremos que você usou uma única ad network. A taxa de conversão da campanha foi de 5%.

Agora você quer avaliar o sucesso da campanha e precisa responder a perguntas importantes (e, claro, às mais difíceis):

* 5% é uma boa taxa de conversão para essa campanha?
* Como sei que a campanha realmente resultou em mais conversões?
* A campanha valeu o custo da sua realização?

Para responder a essas perguntas de forma precisa, temos de considerar mais do que apenas as conversões mensuradas. É importante levar em consideração a quantidade de usuários que teriam convertido de forma orgânica, mesmo que eles nunca tenham se engajado com uma campanha de remarketing.

Essa diferença entre o total de conversões e as que teriam ocorrido de qualquer forma é conhecida como **aumento incremental** (ou, por vezes, simplesmente **"aumento")** e é fundamental para determinar o verdadeiro valor de uma campanha. Ela pode ser bastante difícil de mensurar, mas é exatamente para isso que criamos nosso recurso de Incrementalidade.

### Testes de Incrementalidade

A Incrementalidade soluciona o desafio de mensurar seu aumento incremental, possibilitando a criação de experiências cientificamente válidas para comparar o comportamento de grupos semelhantes. A variação entre esses grupos está no fato de que alguns deles (os **"grupos de teste")** são expostos à sua campanha e um grupo específico (o **"grupo de controle")** não.

<Anchor target="_blank" href="/marketers/pt/docs/run-an-incrementality-for-remarketing-experiment">Saiba mais sobre como criar e executar testes de Incrementalidade</Anchor>

## Metodologia do cálculo

As seções abaixo explicam os cálculos por trás dos números apresentados no dashboard de Incrementalidade.

<div id="lift" />

<Accordion title="aumento">

A Incrementalidade da AppsFlyer usa dois métodos alternativos para calcular o aumento:

* Intenção de tratar
* Reach-based

Embora **a metodologia baseada no alcance seja preferível** para avaliar a performance da campanha, o seu cálculo exige a mensuração de pontos de dados que não são fornecidos por todas as ad networks. Para essas ad networks, usamos a metodologia intent-to-treat.

> 📘 **Observação:**
>
> Antes de 16 de dezembro de 2021, o aumento era calculado usando apenas o método intent-to-treat. No entanto, os dados de datas anteriores foram atualizados para usar o aumento reach-based, quando aplicável. Portanto, você pode revisar seu histórico de experimentos para analisar seus resultados e comparar com a nova metodologia.

#### Aumento baseado em ITT

A metodologia experimental de Intent-to-treat (ITT) se baseia na ciência médica. Usando o ITT, os pesquisadores dividem aleatoriamente uma determinada população entre um grupo de controle que não é tratado e um grupo de teste que os pesquisadores pretendem tratar. Os investigadores avaliam a eficácia de um determinado tratamento comparando os resultados dos grupos. O fato de um membro do grupo de teste *ter* ou não recebido tratamento não é levado em conta.

Do mesmo modo, no remarketing, a métrica de aumento avalia a eficácia da campanha. Não importa se um usuário do grupo de teste se engajou *efetivamente* com uma campanha (recebeu tratamento), porque é a intenção que é relevante no cálculo da incrementalidade. Em outras palavras, os resultados são calculados como se todos os membros do grupo de teste tivessem efetivamente participado na campanha.

**Quando esse método é usado?**

A Incrementalidade da AppsFlyer usa o cálculo de aumento baseado em ITT para SRNs.

Embora esse não seja o melhor método para mensurar o aumento no nosso contexto, o ITT continua a ser um método experimental cientificamente sólido e fornece resultados válidos quando o cálculo reach-based não é possível.

**Interpretação dos resultados**

Assumir que todos os membros do grupo de teste foram efetivamente alcançados por uma campanha frequentemente resulta em taxas de conversão baixas e, consequentemente, em um aumento incremental baixo.

#### Aumento reach-based

Como o nome indica, o cálculo do aumento reach-based (que se baseia em alcance) considera o fato de que um membro do grupo de teste pode ter sido *efetivamente alcançado* ou não (ou seja, ele visualizou um anúncio da campanha) antes de converter. Além de exigir dados adicionais, esse cálculo também é mais complexo, pois ele requer determinados ajustes matemáticos ao grupo de controle para ser estatisticamente válido. Estes ajustes levam à criação de um grupo de controle "contrafactual".

**Quando esse método é usado?**

A Incrementalidade da AppsFlyer usa o cálculo reach-based para redes não-SRNs (que usam links de atribuição específicos para ad networks).

Embora esse seja nosso método preferido para calcular o aumento, e,e exige que as ad networks compartilhem os seguintes dados com a AppsFlyer:

* Dados de impressão
* Campaign ID (a partir do link de atribuição)

Se esses dados não forem compartilhados, a mensuração da Incrementalidade não é possível (e é exibida como **N/A** no dashboard de Incrementalidade).

**Interpretação dos resultados**

Como o cálculo reach-based leva em consideração somente membros do grupo de teste que de fato foram impactados por uma campanha, as ad networks que são mensuradas via incrementalidade reach-based normalmente mostram resultados amplificados (o aumento positivo será bem maior e o aumento negativo será bem menor)

#### Práticas recomendadas

Como as duas metodologias de cálculo de aumento podem gerar resultados significativamente diferentes, temos algumas práticas recomendadas que podem melhorar a interpretação:

* Ao criar seus testes, selecione audiências que estejam divididas apenas entre um grupo de controle e uma ou mais ad networks do mesmo tipo:
  * Ad networks que usam links de atribuição (não-SRN) para cálculo baseado no alcance; ou
  * SRNs para cálculo de ITT
* Nos seus testes iniciais, considere usar uma audiência dividida apenas para uma única ad network e um grupo de controle. Isso reduz a probabilidade de que as comparações sejam feitas entre 2 ou mais ad networks que possuem diferentes cálculos de aumento incremental.

</Accordion>

<div id="statistical-significance" />

<Accordion title="Significância estatística">

Ao avaliar a validade dos testes de Incrementalidade, a metodologia científica exige que consideremos a significância estatística (ou seja, precisamos confirmar que o resultado do aumento não se deve a eventos aleatórios).

No dashboard de Incrementalidade, a significância é relatada como uma porcentagem para cada fonte de mídia:

* A porcentagem indica a probabilidade de os resultados para essa fonte de mídia se repetirem se o mesmo teste for realizado novamente em circunstâncias semelhantes.
* Se for determinado que a significância estatística é inferior a 60%, o dashboard mostrará o texto **Resultados não confiáveis** em vez de uma porcentagem.
* A significância é afetada pela dimensão da audiência, pela duração da experiência e pela performance da fonte de mídia.

</Accordion>

<div id="scaled-control-group" />

<Accordion title="Grupo de controle escalonado">

Para [métricas a nível de grupo de teste](/docs/incrementality-for-remarketing-overview#::2c5f08ec) (em contraste com as [métricas por usuário](/docs/incrementality-for-remarketing-overview#::6143ff4f)), o aumento é calculado com base em um **grupo de controle escalonado**. Ou seja, a dimensão do grupo de controle é ajustada para corresponder à dimensão do grupo de controle para cada fonte de mídia.

> 📄 **Exemplo**
>
> Considere o seguinte cenário:
>
> * Dimensão do grupo de teste para a ad network A = 100 membros
> * Tamanho do grupo de controle = 90 membros
> * Resultados da experiência:
>   * A ad network A teve 40 conversões
>   * O grupo de controle teve 20 conversões
> * O total de conversões será ajustado com base em uma suposta dimensão do grupo de controle de 100 membros:
>   * Supostos membros - membros efetivos = 100 - 90 = 11%
>      Membros efetivos 90
>   * Conversões incrementais efetivas + 11% = 20 x 1,11 = 22
>
> O aumento será calculado com base em uma dimensão de grupo de controle de 100 membros e 22 conversões incrementais.

</Accordion>

## Dashboard de Incrementalidade

[![New_Incrementality_Guide_image.jpg](https://files.readme.io/a14fa7ae346177dbdd7de5fde4917d7300cbc148097a2239e29460a67eacd9a6-15317247527569.jpg)](https://files.readme.io/a14fa7ae346177dbdd7de5fde4917d7300cbc148097a2239e29460a67eacd9a6-15317247527569.jpg)

<div id="accessing-the-dashboard" />

<Accordion title="O acesso ao dashboard de">

Incrementalidade é um recurso premium. Para começar, entre em contato com seu customer success manager ou envie uma mensagem para [hello@appsflyer.com](mailto:hello@appsflyer.com). Feito isso, você poderá acessar o dashboard de Incrementalidade.

**Para acessar o dashboard de Incrementalidade:**

1. Na AppsFlyer, no menu lateral, selecione **Otimizar** > **Incrementalidade**.
2. Na lista de testes, clique na linha do teste que você deseja analisar.

</Accordion>

<div id="a-tour-of-the-dashboard" />

<Accordion title="Conhecendo o dashboard">

<Table>
  <thead>
    <tr>
      <th>

      </th>
      <th>
        Componente
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ![A.png](https://files.readme.io/66b5bb0c4ea35f232f65dbc8dcbdfd6a91c12cf94915b19d33dae44834127058-31237653543313.png)
      </td>
      <td>
        Barra de filtro
      </td>
      <td>
        **Mensurar:** Selecione a métrica que deseja visualizar no dashboard:

        * **Conversões** - O número de usuários únicos que realizaram o evento selecionado
        * **Receita** - Receita gerada pela conversão de usuários do evento selecionado
        * **Eventos** - O número de ocorrências do evento selecionado realizadas pelos usuários que convertem

        A sua seleção no filtro de **mensuração** determina quais métricas são exibidas em todo o dashboard.

        **Evento:** Selecione o evento in-app cujos dados você deseja visualizar no dashboard.

        **Fonte de mídia:** Filtre a visualização do dashboard por uma ou mais fontes de mídia testadas na experiência.

        **Intervalo de datas:** **Filtre a análise incremental da audiência de acordo com o intervalo de datas selecionado.**
      </td>
    </tr>
    <tr>
      <td>
        ![B.png](https://files.readme.io/f63914d3fefb55b627559c6e4c7d7cdef89239c0376a14c25c713a0a76dbad1b-31237653544337.png)
      </td>
      <td>
        <span id="::3b361a96"></span>Resumo do teste
      </td>
      <td>
        Resume todo o experimento em resultados rápidos.
      </td>
    </tr>
    <tr>
      <td>
        ![C.png](https://files.readme.io/b428e77b299e10fe0701b7850cea1da8942905ad38d7b30c32f99f0240b22a63-5397303804945.png)
      </td>
      <td>
        <span id="::6ba593ae"></span>Bloco de significância
      </td>
      <td>
        Apresenta a [significância estatística](/docs/incrementality-for-remarketing-overview#statistical-significance) dos resultados mostrados no dashboard
      </td>
    </tr>
    <tr>
      <td>
        ![D.png](https://files.readme.io/9d9abd09fc45ec65fc52cbc1c8011117b555629d243444d076a392b4245effdd-5397362181265.png)
      </td>
      <td>
        <span id="::4c3ffd21"></span>Bloco de métrica principal
      </td>
      <td>
        A métrica apresentada é controlada pela sua seleção no filtro de mensuração, como mostrado abaixo.

        | Seleção do filtro de mensuração | Métrica principal apresentada |
        | --- | --- |
        | <span id="conversionsevents"></span>Conversões/Eventos | Custo por ação incremental (CPiA)<br /><br />* Custo médio de cada evento incremental, com base no custo da campanha |
        | <span id="revenue"></span>Resultados | Retorno incremental do investimento em anúncios (iROAS)<br /><br />* Proporção de receita incremental gerada por cada centavo gasto na campanha |

        **Atenção:** O cálculo das métricas apresentadas no bloco principal requer dados de custo. Portanto, essas métricas estão disponíveis apenas para assinantes do <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">ROI360</Anchor> . Se os dados de custo e/ou receita não estiverem disponíveis por esse ou qualquer outro motivo, a métrica relevante será exibida como **N/D.**
      </td>
    </tr>
    <tr>
      <td>
        ![E.png](https://files.readme.io/28563cf0057cdd6ccfd8ebb5b727ae80bef81ec66697f8e11eadc698f72e7acd-5397355189777.png)
      </td>
      <td>
        <span id="::c0b74d1b"></span>Tamanho da audiência e alcance
      </td>
      <td>
        Tamanho da audiência: O número de usuários distintos, para cada fonte de mídia, que foram adicionados à audiência pela primeira vez durante o intervalo de datas do teste

        * Também representado pelo anel interno do gráfico de pizza (cor mais escura)

        **Alcance:** A porcentagem da audiência que de fato viu um anúncio da campanha da fonte de mídia relevante

        * Também representado pelo anel exterior do gráfico de pizza(cor mais clara)
      </td>
    </tr>
    <tr>
      <td>
        ![F.png](https://files.readme.io/99f2fb8f45215ddebf9582f215e3647bc35f5a812015733b3f6e3cb8d2784bd7-5397365201809.png)
      </td>
      <td>
        <span id="::2c5f08ec"></span>Bloco de aumento a nível de grupo de teste
      </td>
      <td>
        Apresenta a métrica incremental **total** e o aumento **para o grupo de teste** (por fonte de mídia):

        * O aumento incremental total é calculado utilizando um [grupo de controle escalonado](/docs/incrementality-for-remarketing-overview#scaled-control-group).
        * A métrica apresentada é controlada pela sua seleção no filtro de mensuração, como mostrado abaixo.

        | Seleção do filtro de mensuração | Métrica apresentada |
        | --- | --- |
        | <span id="conversions"></span>Conversões | Total de conversões incrementais |
        | <span id="events"></span>Eventos | Total de eventos incrementais |
        | <span id="revenue::3f000a8e"></span>Resultados | Receita incremental total |
      </td>
    </tr>
    <tr>
      <td>
        ![G.png](https://files.readme.io/7301cda39a8a6bcd08d199097ff9b11d496c5f01ab34422364a4e467a752338a-5397303963409.png)
      </td>
      <td>
        <span id="::6143ff4f"></span>Bloco de aumento por usuário
      </td>
      <td>
        Apresenta a métrica incremental e o aumento **por usuário** (por fonte de mídia):

        * O aumento incremental por usuário é calculado utilizando o número real de usuários no grupo de teste e no grupo de controle.
        * A métrica apresentada é controlada pela sua seleção no filtro de mensuração, como mostrado abaixo.

        | Seleção do filtro de mensuração | Métrica apresentada |
        | --- | --- |
        | <span id="conversions::b51393dc"></span>Conversões | Taxa de conversão incremental |
        | <span id="events::3b4fa416"></span>Eventos | Eventos incrementais por usuário |
        | <span id="revenue::b432caf"></span>Resultados | Receitas incrementais por usuário |
      </td>
    </tr>
    <tr>
      <td>
        ![H.png](https://files.readme.io/36085f38ba02d718acc766af3865073bf13960b2a1c755bd48302ab5415ff89a-5397355274513.png)
      </td>
      <td>
        <span id="::a6a95657"></span>Gráfico de tendências
      </td>
      <td>
        Apresenta a métrica/aumento incremental **por usuário** selecionados ao longo do intervalo de datas da experiência:

        * A métrica apresentada é controlada pela sua seleção no filtro de mensuração e é a mesma métrica apresentada no **bloco de aumento por usuário.**
        * Uma linha pontilhada (na visualização do gráfico) indica os dados parciais para a data relatada (o que significa que eventos futuros ainda podem afetar os dados).
        * Selecione várias opções de visualização e download utilizando os **controles de visualização do gráfico de tendências** (conforme descrito mais adiante).
      </td>
    </tr>
    <tr>
      <td><span id="::64e4f3f6"></span>
        <Image alt="I.jpg" src="https://files.readme.io/19ab5c305d3eb2609031a1a88f6f4069015b6eefe9ef4f1501613f62e5024739-15317326904465.jpg" width="29px" />
      </td>
      <td>
        Controles da visualização do gráfico de tendências
      </td>
      <td>
        Use os controles de visualização para selecionar as opções de visualização e download do **gráfico de tendências**:

        * Valores acumulados ou diários (no dia)
        * Formato de gráfico ou tabela

        Use o botão **Exportar** para fazer download dos dados como um relatório em formato CSV.

        * Os dados baixados são controlados pela sua seleção com os controles de visualização: **Acumulado** ou **no dia**

        **Descrição dos termos do relatório**

        | Termo | Descrição |
        | --- | --- |
        | Métrica bruta | A quantidade total de conversões/eventos/receitas gerada pelo grupo de teste, independentemente das impressões (apenas com base na ad network à qual cada usuário foi atribuído pela configuração). |
        | Métrica alcançada | A quantidade de conversões/eventos/receitas gerada pelo grupo de teste, apenas por usuários que tiveram uma impressão na campanha selecionada antes de ativar o evento seguinte. |
        | Métrica não alcançada | Métrica bruta menos a métrica alcançada. Descreve a quantidade total de conversões/eventos/receitas gerada pelos usuários do grupo de teste que não tiveram uma impressão antes de desencadear o evento seguinte. |
        | Métrica por usuário | Métrica de alcance/resultado bruto do grupo de teste (a depender se a ad network selecionada é compatível ou não com o alcance) dividida pela dimensão do grupo/alcance do grupo de teste. |
        | Métrica bruta do grupo de controle | A quantidade total de conversões/eventos/receitas gerada pelo grupo de controle. |
        | Métrica atingida pelo grupo de controle | A quantidade de conversões/eventos/receitas gerada pelo grupo de controle, ajustada para o alcance do grupo de teste (esse valor é contrafactual e serve como meio de comparação). |
        | Métrica não alcançada pelo grupo de controle | Métrica bruta menos a métrica contrafactual alcançada. Descreve a quantidade total de conversões/eventos/receitas gerada pelos usuários do grupo de controle. |
        | Grupo de controle por métrica do usuário | Alcance contrfactual/métrica bruta do grupo de controle (a depender se a ad network selecionada oferece suporte para o alcance) dividido pelo tamanho do grupo/alcance contrafactual do grupo de controle. |
        | Métrica incremental total | Métrica de teste alcançada menos a métrica de controle contrafactual alcançada. |
        | Métrica incremental por usuário | Métrica por usuário menos a métrica de controle por usuário. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

## Relatórios de dados brutos

Use os relatórios de dados brutos de Incrementalidade para analisar a interação dos usuários com campanhas de remarketing:

* **Conteúdos:** Dados ao nível da linha dos usuários incluídos nas experiências de Incrementalidade.
* **Disponibilidade:**
  * Através do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker</Anchor>
  * Atualização dos dados: diariamente 19:00-23:00 UTC

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012600697">Faça o download de exemplos de arquivos de dados brutos de Incrementalidade</Anchor>

<div id="available-reports" />

<Accordion title="Relatórios disponíveis">

<table><thead><tr><th>Categoria</th><th>Nome do relatório </th><th>Pasta do Data Locker</th></tr></thead><tbody><tr><td>Visto pela primeira vez</td><td>First-seen users</td><td>incrementality_first_seen_users</td></tr><tr><td rowspan="3">Eventos in-app</td><td>Eventos orgânicos in-app</td><td>incrementality_organic_inapps</td></tr><tr><td>In-app events non-organic</td><td>incrementality_inapps</td></tr><tr><td>In-app events re-attributions</td><td>incrementality_inapps_reattr</td></tr><tr><td rowspan="3"><p>Sessões</p></td><td>Organic sessions</td><td>incrementality_organic_sessions</td></tr><tr><td>Sessions non-organic</td><td>incrementality_sessions</td></tr><tr><td>Sessions re-attributions</td><td>incrementality_sessions_reattr</td></tr><tr><td>Uninstalls</td><td>Uninstalls<br/>(atualmente não preenchido) </td><td>incrementality_uninstalls</td></tr></tbody></table>

</Accordion>

<div id="report-logic" />

<Accordion title="Lógica do relatório">

A lógica básica subjacente à estrutura do relatório é a seguinte:

* **Usuários que participaram na experiência - Relatório inédito**
  * No Audiences, algumas regras são definidas para caracterizar os usuários que serão incluídos na experiência.
  * Quando um determinado usuário se encaixa nas regras, o evento é registrado no relatório *first\_seen*.
    * Os usuários são atribuídos aleatoriamente a um grupo de teste ou de controle indicado pelo campo *is\_control\_group* .
    * Os usuários do grupo de teste são atribuídos a uma fonte de mídia*(pid\_destination*) para retargeting.
* **Engajamento do usuário no aplicativo:** O engajamento do usuário com o aplicativo durante o reste é registado em relatórios específicos, de acordo com o contexto:
  * **Tipo de engajamento:** Sessão ou evento in-app
  * **Status de atribuição do usuário** quando ele é first-seen: Orgânico, não orgânico, reatribuição. Por exemplo, no passado, um usuário instalou o aplicativo e foi atribuído como orgânico. Assim, durante uma experiência, o status de atribuição é orgânico.
* **Desinstalações:** Usuários que desinstalam o aplicativo durante o teste. A mensuração de desinstalação deve estar ativada.

</Accordion>

<div id="data-characteristics-and-fields" />

<Accordion title="Características e campos dos dados">

A disponibilidade do campo varia de acordo com o tipo de relatório, conforme indicado abaixo:

#### Campos exclusivos de Incrementalidade (por tipo de relatório)

| Campo | Descrição | Visto pela primeira vez | Eventos in-app | Sessões | Uninstalls |
| --- | --- | --- | --- | --- | --- |
| <span id="is_control_group"></span>is\_control\_group | Se "true", o usuário faz parte do grupo de controle | S | S | S | S |
| <span id="pid_destination"></span>pid\_destination | A fonte de mídia para a qual o usuário é enviado | S | S | S | S |
| <span id="audience_id"></span>audience\_id | Identificador único | S | S | S | S |
| <span id="joined_audience_date"></span>joined\_audience\_date | Data em que o usuário foi incluído na audiência pela primeira vez | S | S | S | S |
| <span id="audience_name"></span>audience\_name | Nome da audiência (não exclusivo) | S | S | S | S |
| <span id="tm"></span>TM | Hora do dia |  | S | S | S |
| <span id="timestamp"></span>timestamp | Carimbo de data e hora do evento AAAA-MM-DD HH:MM |  | S | S |  |
| <span id="app_ids"></span>app\_ids | IDs de aplicativos associados às regras de audiência | S |  |  |  |

#### Outros campos do relatório de Incrementalidade (por tipo de relatório)

<table><thead><tr><th>Campo</th><th>Nome de exibição\*</th><th>Visto pela primeira vez</th><th>Eventos in-app</th><th>Sessões</th><th>Uninstalls</th></tr></thead><tbody><tr><td><span id="advertising_id"></span>advertising_id</td><td>ID de publicidade (GAID)</td><td>S</td><td>S</td><td>S</td><td>S</td></tr><tr><td><span id="android_id"></span>android_id</td><td>ID Android</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="app_id"></span>ativado</td><td>ID da aplicação</td><td>S</td><td>S</td><td>S</td><td>S</td></tr><tr><td><span id="app_name"></span>ativado</td><td>Nome do aplicativo</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="app_version"></span>app_version</td><td>Versão do aplicativo</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="appsflyer_id"></span>appsflyer_id</td><td>Appsflyer ID</td><td> </td><td>S</td><td>S</td><td>S</td></tr><tr><td><span id="revenue_alt"></span>revenue_alt</td><td>Moeda específica do aplicativo</td><td> </td><td>S</td><td> </td><td> </td></tr><tr><td><span id="bundle_id"></span>bundle_id</td><td>ID do pacote</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="country"></span>país</td><td>Código do país</td><td> </td><td>S</td><td>S</td><td>S</td></tr><tr><td><span id="currency"></span>símbolos monetários</td><td>Código da moeda</td><td> </td><td>S</td><td>S</td><td>S</td></tr><tr><td><span id="customer_user_id"></span>customer_user_<br/>id</td><td>ID de usuário cliente</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="brand"></span>Marca</td><td>Marca do dispositivo</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="device_category"></span>device_category</td><td>Categoria do dispositivo</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="model"></span>Modelo</td><td>Modelo do dispositivo</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="device_model"></span>device_model</td><td>Modelo do dispositivo</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="device_type"></span>device_type</td><td>Tipo de dispositivo</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="event_name"></span>nome_do_evento</td><td>Nome do evento</td><td> </td><td>S</td><td>S</td><td>S</td></tr><tr><td><span id="event_revenue"></span>event_revenue</td><td>Receita do evento</td><td> </td><td>S</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_currency"></span>event_currency</td><td>Moeda da receita do evento</td><td> </td><td>S</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_u_s_d"></span>event_revenue_u_s_d</td><td>Receita do evento em USD</td><td> </td><td>S</td><td> </td><td> </td></tr><tr><td><span id="event_time"></span>event_time</td><td>Hora do evento</td><td> </td><td>S</td><td>S</td><td>S</td></tr><tr><td><span id="event_value"></span>event_value</td><td>Valor do evento</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="idfa"></span>idfa</td><td>IDFA</td><td>S</td><td>S</td><td>S</td><td>S</td></tr><tr><td><span id="idfv"></span>idfv</td><td>IDFV</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="imei"></span>imei</td><td>IMEI</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="is_purchase_validated"></span>is_purchase_validated</td><td>Se o recibo foi validado</td><td> </td><td>S</td><td> </td><td> </td></tr><tr><td><span id="os_version"></span>os_version</td><td>Versão do sistema operacional</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td><span id="platform"></span>platforma</td><td>Plataforma</td><td> </td><td>S</td><td>S</td><td>S</td></tr><tr><td><span id="sdk_version"></span>sdk_version</td><td>Versão do SDK</td><td> </td><td>S</td><td>S</td><td> </td></tr><tr><td colspan="6"><span id="-according-to-raw-data-specification"></span>\* <a href="./raw-data-field-dictionary#data-fields-dictionary" target="_blank">De acordo com a especificação dos dados brutos</a> </td></tr></tbody></table>

</Accordion>

## Especificações e limitações da incrementalidade

| Caraterística | Observações |
| --- | --- |
| Acesso do usuário à conta | Sim (de acordo com as permissões da conta) |
| Acesso da ad network | Indisponível |
| Acesso de agência | Indisponível. A incrementalidade está disponível apenas para contas de anunciantes. |
| Transparência da agência | Você pode mensurar campanhas feitas por agências que tenham a transparência de agência ativada. |
| Moeda | USD |
| Atualização dos dados | Dashboard: diariamente às 18:00 UTC para o dia anterior<br /><br />Relatórios de dados brutos no Data Locker: diariamente entre 19:00 e 23:00 para o dia anterior |
| Histórico de dados | N/D |
| Dados não orgânicos | Sim |
| Dados orgânicos | Sim |
| Eventos S2S | Para serem mensurados na incrementalidade, <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile#api-de-eventos-de-servidor-para-servidor-para-mobile">eventos S2S</Anchor> devem incluir o advertising ID em seu payload (IDFA para iOS, GAID para Android). |
| Fuso horário | UTC |

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide">Guia do Audiences</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/tips-strategy/incrementality-testing-for-marketers/">Blog sobre testes de incrementalidade para profissionais de marketing</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/topic/incrementality/">Blog sobre a incrementalidade</Anchor>

<div data-zendesk-anchors="what-is-incrementality=o-que-%C3%A9-a-incrementalidade h_01HB86QVQ0TM91XB8VSZYD42ZA=o-que-%C3%A9-a-incrementalidade incrementality-experiments=testes-de-incrementalidade h_01HB86QVQ0HR436K24V3SQXVXT=testes-de-incrementalidade calculation-methodology=metodologia-do-c%C3%A1lculo h_01HB86QVQ0FYTCEVATBEC91ZC1=metodologia-do-c%C3%A1lculo h_01HB86QVQ0SMJFEPJ8048NBQTN=lift h_01HB86QVQ1MREDW50YTKSY2KZJ=observa%C3%A7%C3%A3o ittbased-lift=aumento-baseado-em-itt h_01HB86QVQ1NGWZM604A45K03TA=aumento-baseado-em-itt reachbased-lift=aumento-reach-based h_01HB86QVQ1N67SFWKRG1BKZE5A=aumento-reach-based best-practices=pr%C3%A1ticas-recomendadas h_01HB86QVQ1RDMFT5FH53BYDNSV=pr%C3%A1ticas-recomendadas h_01HB86QVQ1K2SPBXTG67B5PV33=statistical-significance h_01HB86QVQ1CAZ0ZDJDKPC1B36S=scaled-control-group h_01HB86QVQ16EZVAATG4DPTDVTQ=exemplo incrementality-dashboard=dashboard-de-incrementalidade h_01HB86QVQ10C1YHC8HZ9Z8T089=dashboard-de-incrementalidade h_01HB86QVQ1ECVT0BT4GYC81DH4=accessing-the-dashboard h_01HB86QVQ1JN8SPHXJGHT4NFSB=a-tour-of-the-dashboard raw-data-reports=relat%C3%B3rios-de-dados-brutos h_01HB86QVQ27FXXBRSH2V8ZK78X=relat%C3%B3rios-de-dados-brutos h_01HB86QVQ24932F7CHY666730J=available-reports h_01HB86QVQ2YXRVFKEE20E787BK=report-logic h_01HB86QVQ2VK6TX3CSA4S6QSKZ=data-characteristics-and-fields fields-unique-to-incrementality-per-report-type=campos-exclusivos-de-incrementalidade-por-tipo-de-relat%C3%B3rio h_01HB86QVQ2CAN02B8GWEZTTTVW=campos-exclusivos-de-incrementalidade-por-tipo-de-relat%C3%B3rio other-incrementality-report-fields-per-report-type=outros-campos-do-relat%C3%B3rio-de-incrementalidade-por-tipo-de-relat%C3%B3rio h_01HB86QVQ221QK6WYRZQ3MJDSY=outros-campos-do-relat%C3%B3rio-de-incrementalidade-por-tipo-de-relat%C3%B3rio incrementality-specifications-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es-da-incrementalidade h_01HB86QVQ2W6X5Z485WM371GGE=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es-da-incrementalidade h_01HE7RBMSE1RHVSJC7B7FZG8SJ=veja-tamb%C3%A9m" />

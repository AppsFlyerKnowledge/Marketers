---
title: Guia do Audiences
metadata:
  keywords:
    - Audiences
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2017-05-30T07:21:22Z'
  edited_at: '2026-08-18T00:36:51Z'
  id: 115002689186
  locale: pt
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/pt/articles/115002689186
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** Aumente a eficiência de suas campanhas de aquisição e remarketing usando o Audiences da AppsFlyer para criar e conectar segmentos de audiência com suas redes parceiras.

![Intro_image.png](https://files.readme.io/645503f41e6a76c854c62236fc279be591849879790d02001eafc75f0d1a974a-30258966500753.png)

## Noções básicas sobre o Audiences

O Audiences permite que você crie facilmente segmentos de audiências e conecte-os aos seus canais próprios e pagos - para que você possa oferecer campanhas personalizadas e melhorar o engajamento e a performance. E depois que sua campanha for enviada, você também poderá visualizar as métricas de performance no Audiences.

Uma audiência é um segmento de usuários do seu aplicativo que atendem aos critérios específicos definidos por você. As audiências podem se basear em características pessoais, de comportamento, atividade in-app, origem de atribuição, receita gerada, localização geográfica, tipo de dispositivo e muito mais.

**Passo 1 - Construa a sua audiência na AppsFlyer:** você pode criar uma audiência personalizada do zero, importar uma audiência já pronta ou selecionar um modelo em nossa lista totalmente personalizável de “audiências sugeridas”.

**Passo 2 - Conecte sua audiência:** o próximo passo é se conectar com seus parceiros de mídia no dashboard da AppsFlyer, que envia identificadores dos membros de uma audiência aos seus parceiros e cria essa audiência nos sistemas desses parceiros. Isso permite que eles mostrem anúncios específicos apenas para esses usuários. As audiências são atualizadas automaticamente e enviadas aos parceiros uma vez por dia. Além disso, você pode fazer o upload de uma audiência em ferramentas externas, como buckets Amazon S3, ou baixá-la como um arquivo CSV diretamente do dashboard.

Todas as informações necessárias para o upload dos dados da audiência estão especificadas em cada conexão de parceiro. Você pode ter várias conexões para um único parceiro de mídia (usando contas diferentes, informações de login, etc.). Para garantir a conformidade com os requisitos de privacidade do iOS 14.5 e outras diretrizes, **o Audiences permite que você tenha total controle para determinar quais identificadores serão compartilhados com parceiros**, tanto no nível da conta quanto para cada conexão de parceiro.

### Divisão de audiências e testes de incrementalidade

O teste de <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview">incrementalidade</Anchor> avalia o impacto real das suas campanhas com testes A/B que mensuram com precisão o "aumento incremental" — a diferença entre conversões que aconteceram como resultado de suas campanhas de marketing e aquelas que aconteceriam de qualquer forma. O AppsFlyer Audiences prepara o terreno para testes com um recurso opcional que divide a audiência entre parceiros de mídia selecionados e um grupo de controle, para que você possa usar o dashboard de Incrementalidade para entender o verdadeiro valor das suas campanhas.

## Iniciar

Siga essas etapas para começar a usar o Audiences:

|  | Etapas |
| --- | --- |
| 1 | Na AppsFlyer, no menu lateral, selecione **Engajamento** > **Audiences**<br /><br />**Atenção:** O Audiences é um recurso premium. Se você precisar de ajuda para começar, entre em contato com seu Customer Success Manager ou envia uma mensagem para [hello@appsflyer.com](mailto:hello@appsflyer.com) |
| 2 | Configure a <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy">política</Anchor> de nível de conta para compartilhar identificadores de usuários com parceiros |
| 3 | Criar uma nova audiência:<ul><li>[Audiência personalizada](/docs/audiences-guide#create-a-custom-audience) - crie sua audiência do zero</li><li>[Audiência sugerida](/docs/audiences-guide#create-a-suggested-audience) - audiências prontas e personalizáveis com base nas práticas recomendadas do setor</li><li><Anchor target="_blank" href="/marketers/pt/docs/audiences-import-audience-segments-from-internal-systems">Importar audiência</Anchor> - importar segmentos de audiência de seus sistemas internos (tais como BI ou CRM)</li></ul> |
| 4 | Conecte a audiência a um ou mais parceiros de mídia |
| Opcional | [Divida a audiência entre parceiros e um grupo de controle](/docs/audiences-guide#audience-split-and-control-groups) |
| Opcional | <Anchor target="_blank" href="/marketers/pt/docs/audiences-create-better-audiences-with-user-attribute-data">Importar atributos do usuário</Anchor> |

## Criar e gerenciar audiências

Descubra como criar e gerenciar audiências e configurar testes de incrementalidade.

<div id="create-a-custom-audience" />

<Accordion title="Criar uma audiência personalizada">

Uma audiência personalizada é criada utilizando qualquer conjunto de regras e filtros que você desejar.

**Para criar uma audiência personalizada:**

1. Na AppsFlyer, no menu lateral, selecione **Engajamento** > **Audiences**.
2. Clique em **nova audiência**.
3. Selecione **audiência personalizada**.  
   A aba **Criar** será exibida.
4. Insira um **Nome de audiência** exclusivo.  
   **Nota:** Os nomes da audiência não podem incluir caracteres especiais (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
5. Selecione a plataforma: **Android** ou **iOS**.
6. Selecione o [identificador de usuário](/docs/audiences-guide#user-identifier-device-id-vs-customer-id):
7. [Default] **Device ID**: avalia as regras apenas por ID de dispositivo.
8. **Customer ID**: avalia as regras agrupando dispositivos usando o CUID (use esse método somente depois de verificar que seus dados possuem CUIDs válidos).
9. Selecione **novo conjunto de regras**, ou, se você deseja adicionar os usuários de uma audiência já existente, clique em **audiência existente** e selecione a audiência específica da lista.
10. Crie a audiência através da interface do usuário. Para informações específicas sobre opções de regras, acesse [tudo sobre conjuntos de regras](/docs/audiences-guide#tudo-sobre-conjuntos-de-regras) .
11. Combine e/ou exclua conjuntos de regras usando os operadores.
12. À medida que você cria sua audiência, os painéis do lado direito atualizam automaticamente os tamanhos de upload por parceiro.
13. Termine de configurar sua audiência, depois clique em **próximo**.  
    A janela **Conexão da audiência** aparecerá. Nela, você pode [conectar a audiência aos seus parceiros de mídia](/docs/audiences-guide#connect-an-audience-to-media-partners).

> 📘 **Observações**
>
> * Você pode ter até 100 audiências personalizadas/sugeridas ativas por vez.
> * Os nomes das audiências podem estar visíveis nos sites dos seus parceiros conectados. Não inclua informações sensíveis nos nomes das suas audiências.

</Accordion>

<div id="create-a-suggested-audience" />

<Accordion title="Criar uma audiência sugerida">

Audiências sugeridas permitem que você explore e descubra **segmentos de audiências prontos, que se baseiam nas melhores práticas da indústria.** Você pode selecionar uma audiência, personalizá-la e conectá-la com suas redes de parceiros para campanhas de marketing bem direcionadas.

Escolha entre mais de 30 audiências dentro das categorias **Adquirir, Ativar, Engajar, Monetizar e audiências específicas por indústria.** A audiência é 100% personalizável, de modo que você pode criar a audiência exata que você deseja. As audiências incluem:

* Conversão de cliques em anúncios em instalações
* Obtenha sósias
* Listas de exclusão
* Incentivar cadastros
* Incentivar compras
* Monetizar compradores
* E muito mais...

> 📄 **Exemplo de caso de uso**
>
> Esse exemplo ilustra um caso de uso típico. Vamos supor que você quer incentivar os usuários do seu app, que nunca fizeram uma compra, a comprar um produto pela primeira vez. Você pode selecionar a audiência "Incentivar compras" e personalizá-la para especificar qual evento define uma compra in-app. Então você pode conectar a audiência aos seus parceiros e executar uma campanha promocional que incentiva os usuários a fazer uma compra, direcionando-os para a página de compra.
>
> ![Encourage_purchase_image_this_one.jpeg](https://files.readme.io/8b49590a0c97707bd4a0b151d30cc48183e15ffb13d2d4e9ee25d522de71846c-30259018203153.jpg)

**Para criar uma audiência sugerida:**

1. Na AppsFlyer, no menu lateral, selecione **Engajamento** > **Audiences**.
2. Clique em **nova audiência**.
3. Selecione **audiência sugerida**.
4. Selecione o aplicativo.
5. Navegue pelas várias categorias e selecione uma audiência que corresponda aos seus objetivos.   
   **Atenção: Algumas audiências exigem que você adicione <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">eventos in-app</Anchor> específicos para definir os critérios da audiência. Se o <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#nomes-de-eventos-predefinidos">evento predefinido</Anchor> da AppsFlyer já estiver configurado no seu aplicativo, ele será pré-selecionado. Caso contrário, você precisará selecionar o evento personalizado apropriado no menu suspenso. Caso contrário, você precisará selecionar o evento personalizado apropriado no menu suspenso. <Image alt="Select_an_event__1_.jpeg" src="https://files.readme.io/b5055ca61791f15efc3a91f3f2d749e1df9e3f5e8b956b9167e186474de57ac4-30258966520721.jpg" width="419px" />**
6. Clique em **Selecionar e personalizar**.
7. Insira um **Nome de audiência** exclusivo.  
   **Atenção:** Os nomes da audiência não podem incluir caracteres especiais (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
8. Selecione a plataforma: Android ou iOS.
9. Selecione o [identificador de usuário](/docs/audiences-guide#user-identifier-device-id-vs-customer-id):
   * [Padrão] **ID de dispositivo**: avalia as regras apenas por ID de dispositivo.
   * **ID do cliente**: avalia as regras agrupando dispositivos usando o CUID (use esse método somente depois de verificar que seus dados possuem CUIDs válidos).
10. Se você deseja personalizar ainda mais a audiência, adicionando outros [conjuntos de regras](/docs/audiences-guide#tudo-sobre-conjuntos-de-regras), você pode fazer isso se desejar clicando em **+ Filtrar**. Quando terminar, clique em **Próximo**.   
    A janela **Conexão da audiência** aparecerá. Nela, você pode [conectar a audiência aos seus parceiros de mídia](/docs/audiences-guide#connect-an-audience-to-media-partners).

> 📘 **Observações**
>
> * Você pode ter até 100 audiências personalizadas/sugeridas ativas por vez.
> * Os nomes das audiências podem estar visíveis nos sites dos seus parceiros conectados. Não inclua informações sensíveis nos nomes das suas audiências.

</Accordion>

<div id="import-an-audience" />

<Accordion title="Importar uma audiência">

Você pode <Anchor target="_blank" href="/marketers/pt/docs/audiences-import-audience-segments-from-internal-systems">importar segmentos de audiências predefinidas</Anchor> de seus sistemas internos (como BI e CRM) para o AppsFlyer Audiences, e usá-los como seu ponto central para conectar e manter todos os segmentos de sua audiência com seus parceiros publicitários. Além disso, permite que você desfrute de recursos do Audiences, tais como correspondência de identificadores/enriquecimento de dados e métricas de campanha conectadas.

</Accordion>

<div id="connect-an-audience-to-media-partners" />

<Accordion title="Conecte uma audiência a parceiros de mídia">

Uma vez definida sua audiência, o próximo passo é conectá-la a seus parceiros de mídia.

**Para conectar sua audiência aos parceiros de mídia:**

1. Depois de definir sua nova audiência na página **Criar** audiência, clique em **Avançar**. A janela **Conexão da audiência** aparecerá.
2. Clique em **+ Conexão de parceiro**, depois faça uma das seguintes opções:
   * **Para adicionar uma nova conexão**, clique em **+ Adicionar conexão de parceiro** (veja a seção [Criar uma nova conexão](/docs/audiences-guide#create-a-new-connection) abaixo para instruções detalhadas).
   * **Para selecionar a partir de conexões existentes:**
     1. Procure a conexão do parceiro.
     2. Selecione uma ou mais conexões existentes.
     3. Clique em **Salvar**.  
        A janela de conexão de audiências é aberta.
     4. [Opcional] [Divida uma audiência entre parceiros e um grupo de controle](/docs/audiences-guide#audience-split-and-control-groups)
     5. [Opcional] [Copie grupos divididos para o S3](/docs/audiences-guide#audience-split-and-control-groups).
3. Clique em **Salvar**.  
   Uma vez conectada, a audiência será atualizada e enviada diariamente aos parceiros.

</Accordion>

<div id="user-identifier-device-id-vs-customer-id" />

<Accordion title="Identificador do usuário — ID do dispositivo vs. ID do cliente">

A avaliação das regras de audiências é realizada utilizando um identificador de usuário do aplicativo. Selecione entre:

* [Padrão] **ID de dispositivo**: A conformidade com o conjunto de regras é avaliada usando o ID do dispositivo (GAID ou IDFA/IDFV). Se houver conformidade com o conjunto de regras, o ID do dispositivo será adicionado à lista de audiências. **Atenção:** o ID do dispositivo será compartilhado com parceiros somente quando isso for permitido pela sua política de identificador de usuário.
* <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">**ID do cliente (CUID)**</Anchor>:
  * A conformidade com o conjunto de regras é avaliada agrupando todos os IDs de dispositivos associados ao mesmo CUID. Se o grupo estiver em conformidade com o conjunto de regras, os IDs de dispositivo que incluem o grupo serão adicionadas à audiência. **Nota**: a CUID em si não faz parte da lista de audiências e não é enviada aos parceiros de mídia.
  * Considerações da implementação do CUID:
    * Certifique-se de que seus dados estejam preenchidos com CUIDs válidos.
    * Os usuários de aplicativos (dispositivos) sem um CUID são ignorados.
    * Quando um ID de dispositivo corresponde a um CUID, os dados históricos da audiência para o usuário são atualizados retroativamente e incluídos nas compilações de audiência a partir de então. **Nota**: nenhuma alteração é feita em dados brutos.
    * Se um ID de dispositivo for associado a dois CUIDs diferentes, o CUID mais recente é usado.
    * Ao criar uma audiência que possui um CUID como identificador, a associação de CUID deve ter sido recebida pela AppsFlyer na instalação (e não apenas em eventos pós-instalação), garantindo a associação completa com os dispositivos relevantes e um enriquecimento eficaz com os identificadores de dispositivos (como GAID, IDFA, etc.). <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid#configuração-do-cuid">Saiba mais</Anchor>

<Image alt="CuidExaplainded_us-en.jpg" src="https://files.readme.io/d40309ab2fd34a4862b9c089ac2fade2f5642973fc4d4977da66f1ee6bf1e390-30258966523921.jpg" width="387px" />

> 📄 **Exemplo: ID do dispositivo vs. CUID**
>
> Uma audiência de usuários que gastaram mais de US$ 5
>
>
>
> | ID de  <br />Publicidade | CLIQUE | Compra US$ |
> | --- | --- | --- |
> | E | 99 | 1 |
> | E | 99 | 2 |
> | B | 77 | 1 |
> | B | 77 | 5 |
> | C | 99 | 3 |
> | J | Nenhum | 50 |
>
>
>
> | Regra avaliada por | IDs de dispositivo incluídos na audiência | Explicação |
> | --- | --- | --- |
> | ID de dispositivo | B, D | A e C não estão incluídos - o gasto foi inferior a US$ 5 |
> | CLIQUE | A, B, C | * A e C têm o mesmo CUID (99) - o gasto em conjunto é de US$ 6.<br />* D é ignorado - não há CUID |
>
>
>
> **<span id="h_01K0PAQ4SFXBK0TZ3MH07PWN4A"></span>Atenção**
>
> O mesmo método de somar o gasto entre IDs de dispositivos agrupados por CUID, mostrado no exemplo acima, também se aplica a outros atributos numéricos (por exemplo, pontuação).



</Accordion>

<div id="audience-split-and-control-groups" />

<Accordion title="Divisão de audiências e grupos de controle">

Use a alternância que divide a audiência entre parceiros e um grupo de controle para definir facilmente o cenário para testes A/B e <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview">medição de incrementalidade</Anchor> para que você possa obter os insights cruciais de que precisa sobre o impacto da campanha. Quando ativado, o recurso divide aleatoriamente a audiência entre seus parceiros selecionados e um grupo de controle. O grupo de controle é a parte da audiência que é retida dos parceiros e é um requisito necessário para a medição da Incrementalidade. Você pode ajustar qualquer uma das porcentagens de divisão que desejar e desativar ou reativar a divisão por audiência.

| Características | Descrição |
| --- | --- |
| Dividir audiência | <ul><li>Esse recurso divide aleatoriamente a audiência entre seus parceiros selecionados e um grupo de controle. **Ele é ativado por padrão para assinantes de Incrementalidade** e pode ser facilmente desativado ou reativado a qualquer momento.</li><li>Divida a audiência por vários motivos, como teste A/B e medição de incrementalidade.</li><li>**Nota:** modificar uma alocação de divisão existente entre parceiros causa a redistribuição de toda a audiência. Isso pode afetar negativamente a validade do teste A/B e fará com que os experimentos de Incrementalidade ativos sejam encerrados e reiniciados como novos experimentos.</li></ul> |
| Grupo de controle | Uma parte da audiência fica retida em um grupo de controle, que não é enviado a nenhum parceiro:<ul><li>Grupos de controle são usados em testes A/B e para medir o aumento incremental de suas campanhas de marketing.</li><li>15% da audiência (ou mais) é recomendável para um grupo de controle eficaz.</li><li>A % do grupo de controle mínimo necessário para executar um experimento de incrementalidade é de 1%.</li></ul> |
| Enviar uma cópia de listas divididas para um bucket do S3 | Os arquivos CSV contendo as listas de audiências divididas e o grupo de controle podem ser enviados para um bucket Amazon S3.<ul><li>**Nota**: Isso não é o mesmo que definir o Amazon S3 como um parceiro conectado.</li><li>As listas de audiências podem ser baixadas para um arquivo CSV. Use o arquivo CSV, por exemplo, para enviar a parceiros que não estão integrados à AppsFlyer.</li></ul> |

**Para dividir a audiência e realizar outras ações do parceiro:**

1. No dashboard esquerdo da AppsFlyer, acesse **engajamento**>**Audiences**.
2. Na guia **Audiences**, selecione a audiência.
3. Acesse a aba **Conectar**.  
   [![audience_split_1200px.png](https://files.readme.io/1a9decaea5f77ec36c111a132c12733cfa44bb1e87c6515e71843e6c7fcabfee-46335667595281.png)](https://files.readme.io/1a9decaea5f77ec36c111a132c12733cfa44bb1e87c6515e71843e6c7fcabfee-46335667595281.png) As configurações atuais exibem:
   * O painel superior direito exibe a audiência total estimada e os tamanhos de upload (para todos os parceiros)
   * O lado inferior direito apresenta uma visualização de:
     * Tamanho estimado do upload para cada parceiro
     * Sobreposição de parceiros (para audiências que não estão divididas)
4. Execute uma das ações abaixo:

<Table>
  <thead>
    <tr>
      <th>
        Ação
      </th>
      <th>
        Procedimento
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="split-an-audience-between-partners-and-control-group"></span>
        Dividir uma audiência entre parceiros e grupo de controle
      </td>
      <td>
        1. Certifique-se de que a opção **Dividir audiência/Medir impacto incremental** esteja ativada.
           * O total do grupo de controle e da divisão para parceiros combinados deve ser de 100%.
           * Se você não quiser incluir o grupo de controle na divisão: alocar 0%.
           * Todos os parceiros conectados devem ter uma parte da divisão alocada a eles (não alocar um parceiro 0%)
           * Para exibir o total alocado: role para baixo. O percentual total de divisão é exibido.
        2. Informe a porcentagem alocada para:
           * **Grupo de controle -** 15% ou mais é recomendado.
           * Insira uma porcentagem dividida por conexão.
           * Role para baixo para exibir a alocação total em porcentagem e certifique-se de que a alocação total seja 100%.
           * Clique em **Salvar divisão**.
           * Clique em **Salvar**.
      </td>
    </tr>
    <tr>
      <td><span id="copy-split-groups-to-s3"></span>
        Copiar grupos divididos para o S3
      </td>
      <td>
        **Para enviar uma cópia da lista dividida de audiências para um bucket S3:**

        1. Clique em **Copiar grupos divididos para o S3.**
        2. Selecione uma conexão.
        3. Clique em **Salvar**.

        Os arquivos são enviados usando a seguinte estrutura de diretório e nome de arquivo:

        * **Diretório**:

          ```
           \YYYY-MM-DD\audienceID_audienceName_timestamp
          ```
        * **Nome do arquivo**: o nome do parceiro ou grupo de controle.  
           Nota: Se a conexão com o parceiro falhar e o arquivo não for carregado, a palavra **falha** (failed) será anexada ao nome do parceiro (por exemplo, *partner\_name\_failed.csv*)
      </td>
    </tr>
    <tr>
      <td><span id="create-and-add-a-new-connection"></span>
        Criar e adicionar uma nova conexão
      </td>
      <td>
        **Para criar uma nova conexão:**

        1. Clique em **Adicionar** **conexão** de **parceiro.**
        2. Digite um nome de conexão.
        3. Selecione um parceiro.
        4. Conclua o processo de acordo com as instruções na interface do usuário.
        5. Clique em **Adicionar conexão de parceiro**.
      </td>
    </tr>
    <tr>
      <td><span id="add-or-remove-an-existing-connection"></span>
        Adicionar/remover uma conexão existente
      </td>
      <td>
        **Para remover ou adicionar uma conexão existente:**

        1. Passe o mouse sobre a conexão do parceiro.
        2. Clique no ícone "Remover".
        3. Clique em **Salvar**.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="manage-audiences" />

<Accordion title="Gerenciar audiências">

**Para gerenciar audiências no dashboard do Audiences:**

1. No dashboard esquerdo da AppsFlyer, acesse **engajamento**>**Audiences**.
2. As seguintes opções estão disponíveis:

| Opção | Descrição |
| --- | --- |
| <span id="create-a-new-audience"></span>Criar uma nova audiência | Criar uma nova audiência |
| <span id="change-audience-settings"></span>Alterar as configurações da audiência | Clique em um **Nome da audiência,** siga um destes procedimentos:<ul><li>Na aba **Criar** : Visualize e altere conjuntos de regras.</li><li>Na aba **Conectar** : Defina a divisão da audiência e as opções do grupo de controle.</li></ul> |
| <span id="actions"></span>Ações | No ícone <Image alt="3_dots_icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" /> que aparece à direita ao passar o mouse sobre uma audiência na página principal do Audiences:<ul><li>**Ver histórico**: exibe o histórico de upload da audiência, incluindo o tamanho da audiência e a divisão entre parceiros.</li><li>**Fazer upload agora**: envia a audiência para parceiros conectados.</li><li>**Download como CSV**:<ul><li>Gera e faz o download da lista de audiências como arquivo(s) CSV que inclui(em) os identificadores selecionados. <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy">O download será feito apenas de dados que estejam em conformidade com a sua política de identificador de usuário.</Anchor></li><li>Um arquivo é gerado para cada parceiro.</li><li>O download do(s) arquivo(s) é feito após o cálculo da audiência, o que pode levar algum tempo depois de criar ou modificar uma audiência.</li><li>Os arquivos de download estão limitados a 5 milhões de registros. Para arquivos maiores, envie o arquivo para um <Anchor target="_blank" href="/marketers/pt/docs/audiences-partner-connections#amazon-s3">bucket de S3</Anchor> ou use SFTP.</li><li>Somente uma audiência conectada a ad networks parceiras será atualizada diariamente e mantida atualizada. Se a audiência não estiver conectada a ad networks parceiras, ela não será mantida atualizada além da data de criação da audiência. Se quiser fazer download das informações mais atuais, você pode duplicar a audiência para recriá-la (veja abaixo) e, em seguida, fazer download do CSV da audiência duplicada.</li></ul></li><li>**Duplicar**:<ul><li>Copia a definição da audiência.</li><li>Quando você duplicar uma audiência, dê um nome exclusivo a ela.</li><li>[Opção] Remova um ou mais parceiros conectados durante a duplicação.</li></ul></li><li>**Calcular agora**: [para audiências importadas]. Recalcula o número de usuários em uma audiência. Use conforme necessário para atualizar o tamanho da audiência, caso ele não pareça correto.</li><li>**<span id="pause"></span>Pausa:**</li></ul><ul><li>Pausar a audiência o desativa para que ele não seja mais calculado e enviado aos parceiros conectados (os dados de audiência existentes dos últimos 3 anos são mantidos).</li><li>Você pode pausar audiências que não utiliza para se manter dentro do número máximo permitido de audiências ativas. Você pode ter até 100 audiências personalizadas/sugeridas ativas e até 500 audiências importadas ativas por vez.</li></ul>**Para pausar uma audiência:**<ol><li>Passe o mouse sobre a audiência na página principal do Audiences para que o ícone <Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" /> (menu Ações) apareça à direita.</li></ol>![Menu de ações.jpg](https://files.readme.io/d7ad8445c7e886ef4669155391419c9bb5538552f9a0bc1dabaa85a4ad819a1e-46335625065873.jpg)<ol><li>Clique no ícone e selecione **Pausar**.</li></ol>A audiência agora está em pausa.<br /><br />Você também pode pausar várias audiências de uma vez marcando a caixa ao lado delas e clicando em **Pausar** , que aparecerá no canto superior direito.<ul><li>**Excluir:** exclui a audiência permanentemente.</li></ul> |
| <span id="bulk-actions"></span>Ações em massa | Execute a mesma ação em várias audiências. Para usar ações em massa, selecione duas ou mais audiências e uma ação em massa da seguinte forma:<ul><li>**Fazer upload agora**</li><li>**Mostrar sobreposição de audiências**: exibe a sobreposição de audiências entre as audiências selecionadas</li><li>**Excluir**</li></ul> |

</Accordion>

## Tudo sobre conjuntos de regras

Saiba como utilizar os conjuntos de regras para definir sua audiência.

<div id="audience-segmentation-rulesets" />

<Accordion title="Conjuntos de regras de segmentação de audiências">

![audience_segmentation_rulesets.jpg](https://files.readme.io/4407da232d372a98afcd30df3a832f6ef38bb55a6b02640587f44c7501b014f2-46335625066897.jpg)

* Um conjunto de regras do segmento de audiência consiste em uma ou várias regras para permitir uma filtragem de precisão.
* Combine conjuntos de regras usando os operadores: and, or, exclude.
* À medida que as regras são definidas e separadas em camadas, o tamanho estimado da audiência é exibido em tempo real.
* Os conjuntos de regras podem ser duplicados clicando em <Image alt="duplicate_icon.png" src="https://files.readme.io/c4e2321280c4141e70c499adc92837d663fd29942b1c88532c6f2f3327efc400-46335667603729.png" width="17px" />ícone .
* Quando uma audiência consiste de vários conjuntos de regras, use a exibição de visualização de sobreposição para entender melhor seus segmentos de audiências.
* O [identificador de usuário](/docs/audiences-guide#user-identifier-device-id-vs-customer-id) usado para avaliar regras é o ID do dispositivo [padrão] ou o ID de cliente do usuário (CUID).

Os exemplos que se seguem ilustram a implementação do conjunto de regras em vários cenários.

</Accordion>

<div id="ruleset-examples" />

<Accordion title="Exemplos de conjuntos de regras">

> 📄 **Exemplo: Regra baseada em localização**
>
> Usuários de Nova York que desinstalaram o aplicativo no último mês
>
> ![example_location_based_rule.jpg](https://files.readme.io/7ee7e2b9e8f06dc47c93148767fd67d87855a05cd09ba06f2dd2c0ea9dc29607-46335625068817.jpg)

> 📄 **Exemplo: Regra baseada em atributos do usuário**
>
> Usuários que inicializaram o aplicativo nos últimos 7 dias pelo menos uma vez e cuja arma favorita é uma espada.
>
> ![example_user_attributes_based_rule.jpg](https://files.readme.io/8ab97cdccd2a1b33b671b1f686ca642306197ccf5151ca2ba9836db8ca496d03-46335625073809.jpg)

> 📄 **Exemplo: Receita**
>
> Usuários que instalaram o aplicativo durante os últimos sete dias e gastaram US$1
>
> ![example_revenue.jpg](https://files.readme.io/d7768bec78ff5981639da4e1c8e1a3121961464c0a5932bf8f542f27979358a8-46335625074833.jpg)

> 📄 **Exemplo: Filtro de mídia próprio**
>
> Crie audiências compostas por usuários que foram atribuídos a fontes específicas de mídia própria, tais como mídia social (excluindo publicidade paga), SMS, e-mail, indicações, web, ou códigos QR. Você também pode escolher seu nível de granularidade e direcionar usuários que vieram de uma fonte específica de mídia, campanha, conjunto de anúncios ou anúncio individual.
>
> Aqui está um exemplo com usuários que inciaram o aplicativo pelo menos uma vez nos últimos 7 dias e cuja instalação foi atribuída a uma campanha de e-mail específica, assim como conjuntos de anúncios e anúncios específicos.
>
> ![Owned_media_example.jpg](https://files.readme.io/4b9c076f5299f4f59524a7f816964f4db2c8edd73690aa899e34fcac0d145628-46335667611409.jpg)
>
> A audiência pode ser usada para re-engajar esses usuários com mensagens personalizadas em mídia própria ou paga, ou como uma lista de exclusão para evitar que eles vejam anúncios irrelevantes ou desnecessários ao realizarem campanhas.

> 📄 **Exemplo: Remarketing**
>
> Usando cliques e visualizações para remarketing eficaz. Para converter esses usuários, é necessário ser um pouco mais convincente ou mandar um lembrete simpático. Esses usuários têm uma alta probabilidade de conversão, de modo que o remarketing, para eles, pode produzir resultados significativamente melhores do que enviar anúncios para novos segmentos. Crie audiências precisas para remarketing com base nos dados de cliques e impressões coletados.
>
> Crie uma audiência de usuários potenciais que clicaram em um anúncio, mas não instalaram nos últimos dois dias.
>
> ![example_remarketing.jpg](https://files.readme.io/715c42d56c0deffdb4d28acd213f4a5da62de75bbcd6834a927b9226d2fea43e-46335667613329.jpg)
>
> Esses são aqueles usuários que, recentemente, estavam suficientemente interessados em seu aplicativo mobile para clicar no seu anúncio, mas por algum motivo não instalaram o aplicativo, ou o instalaram, mas não o inicializaram. Alguns usuários só precisam de um lembrete (push) para instalá-lo. Outros podem precisar ver mais exemplos ou recursos do seu aplicativo para finalmente converter. Portanto, se você tiver um criativo primário usado em novas audiências, talvez seja melhor usar um criativo diferente para audiências que clicaram, mas não instalaram.

</Accordion>

<div id="ruleset-filters" />

<Accordion title="Filtros do conjunto de regras">

* Um conjunto de regras consiste em uma ou várias regras.
* Existem várias categorias de filtro de conjunto de regras, como Eventos, Receita, Geolocalização, Atribuição, Atributos de usuário, Dispositivos e Mídia própria.
* As regras têm parâmetros e configurações diferentes, conforme listado na tabela abaixo.

<table><tbody><tr><td colspan="3"><h4><span id="events"></span>Eventos</h4><p><img alt="engagement_filter_with_A___B.jpg" src="https://files.readme.io/ea3063532ff666f6d8a0f90d55c86007d8a54b25017d93ed7bc19e0d727d9193-46335625077777.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Visualizou um anúncio</li><li>Clicou em um anúncio</li><li>Instalou o aplicativo</li><li>Não instalou o aplicativo</li><li>Inicializou o aplicativo</li><li>Não iniciou o aplicativo</li><li>Desinstalou o aplicativo </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><p>Período de tempo e frequência </p></td></tr><tr><td colspan="3"><h4><span id="inapp-events"></span>Eventos in-app</h4><p><img alt="in-app_event_filter.jpg" src="https://files.readme.io/1bb8a78b3c64ab8e0d01c1e2be63e9bdd00b2be2396335b3a01289b0b0837593-46335625078929.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Fez evento [<em>nome do evento</em>]</li><li>Não fez evento: [<em>nome do evento]</em> </li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><p>Período de tempo e frequência </p></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/></p><p>Atributo do evento + valor:</p><ul><li>É</li><li>Não é</li><li>Maior que</li><li>Menor que</li><li><a href="./audiences-guide#contains-does-not-contain-logic">Contém</a></li><li><a href="./audiences-guide#contains-does-not-contain-logic">Não contém</a></li></ul></td></tr><tr><td colspan="3"><p><br /><br /><strong><span id="h_01K5EHGKDPWS16HP9Q7KX9JXFY"></span>Observações sobre eventos in-app</strong><br /></p><ul><li>A lista de eventos in-app é atualizada <a href="./about-data-freshness-and-timezone-support#processamento-diário" target="_blank">diariamente.</a> </li><li>Se <strong>Executou evento</strong>  for selecionado e o evento in-app tiver atributos associados a ele, você poderá filtrar por valor de atributo do evento in-app. </li><li><p>Os eventos in-app, por padrão, são limitados a 100 valores únicos por atributo. Por exemplo, se o evento for "purchase" e o atributo for "content-type", somente poderá haver 100 (ou menos) tipos de conteúdo possíveis. Entretanto, os valores numéricos são ilimitados.<br/>Se houver atributos (parâmetros) e valores de eventos em um evento que não aparecem na lista, você pode adicioná-los manualmente clicando em <strong>Adicionar atributo de evento</strong> &gt; <strong>Adicionar item</strong><br/> </p><p><strong><img alt="Add_item.jpg" src="https://files.readme.io/00d62c7edfa556c3ecb50842003fb64ecde848413f1b81fd100f3da7257bc38e-46335625079825.jpg"/></strong></p></li><li>- Todos os itens de eventos adicionados manualmente devem ser inseridos apenas como tipo de string (texto). Valores numéricos não devem ser adicionados e não funcionarão corretamente.</li><li>- Quando um item de evento adicionado manualmente é adicionado, o "Estimativa do tamanho da audiência" pode não refletir com precisão. <br/>Se você precisar que mais de 100 atributos/valores apareçam na lista, você também pode entrar em contato com seu CSM ou enviar um e-mail para hello@AppsFlyer.com.</li></ul><h4><strong><span id="contains-does-not-contain-logic"></span>Lógica "Contém" / "Não contém":</strong></h4><p><strong>Contém:</strong> Corresponde a usuários cujos valores de atributo de evento contêm uma palavra específica ou várias palavra(s). A correspondência é parcial e não diferencia maiúsculas de minúsculas. Por exemplo, a palavra-chave "bag" corresponde a atributos como "handbag" ou "Bag".</p><p><strong>Não contém:</strong> Corresponde a usuários cujos valores de atributos de evento não contêm as palavras especificadas. A lógica de correspondência também é parcial e não diferencia maiúsculas de minúsculas.</p><p><br /><br /><strong><span id="h_01K5EH9WVTEX56980MCR81ZAHH"></span>Observações sobre a lógica "Contém"</strong><br /></p><ul><li>Comprimento mínimo da palavra-chave: 2 caracteres.</li><li>Máximo de entradas permitidas por regra: 1 palavra-chave por condição AND.</li><li>Não há suporte para atributos compostos apenas por números e caracteres especiais.</li><li>O suporte multilíngue inclui caracteres acentuados e não latinos (por exemplo, é, ü, caracteres coreanos).</li><li>Ao usar os operadores "Contém" ou "Não contém", o tamanho estimado da audiência e o tamanho estimado do upload não ficam disponíveis. </li></ul></td></tr><tr><td colspan="3"><h4><span id="revenue::3358edf4"></span>Resultados</h4><p><img alt="revenue_filter.jpg" src="https://files.readme.io/e896abde88511e5675074d5e4d995ed810637be8327c7c157ddf65668839fd4a-46335625080209.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Receita total de compras in-app</li><li>Receita publicitária total</li><li>Receita total </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>É</li><li>Maior que</li><li>Menos do que </li></ul><p><strong>Definições:</strong></p><ul><li> <strong>Receita total de compras in-app:</strong> valor total de todos os eventos reportados usando o parâmetro <code>af_revenue</code> para um dispositivo específico/CUID</li><li> <strong>Total da receita publicitária:</strong> to total da receita publicitária gerada por um dispositivo específico/CUID</li><li> <strong>Receita total</strong>: Receita total de compras no aplicativo + Receita total de anúncios</li></ul><p><strong>Observações:</strong></p><ul><li>Para utilizar os filtros <strong>Receita publicitária total</strong> e <strong>Receita total</strong>, <a href="./roi360-guide-ad-revenue-attribution" target="_blank">Atribuição de receita publicitária</a> deve ser implementada em sua conta AppsFlyer.</li><li>Todas as opções de filtro de receita são medidas em USD.</li></ul></td></tr><tr><td colspan="3"><h4><span id="geo"></span>Geografia</h4><p><img alt="location_filter.jpg" src="https://files.readme.io/62f6144d23ef23070e2d6d8891a420691633a466d1b8d76365b4d82f40c725c6-46335625081361.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Localização </li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>É</li><li>Não é</li></ul></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/></p><p><strong>Opções de localização</strong></p><ul><li>País</li><li>Estado</li><li>CIDADE</li></ul></td></tr><tr><td colspan="3"><p><strong>Notas relativas à localização:</strong></p><ul><li>Se você selecionar vários países, não poderá selecionar estados.</li><li>Se você selecionar vários estados, poderá selecionar cidades.</li></ul></td></tr><tr><td colspan="3"><h4><span id="owned-media"></span>Mídias próprias</h4><p><img alt="doctored_owned_media_image_with_app_specified__final_version_.jpg" src="https://files.readme.io/0d15fa734e11164e6e525e26c66291c52144586c8c35dad77a71e471cbf3326d-46335667621649.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Canal de mídia própria</li><li>Campanha de mídia própria</li><li>Conjunto de anúncios de mídia própria</li><li>Anúncio de mídia própria</li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>É</li><li>Não é</li></ul></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/></p><p>Valores como:</p><ul><li>E-mail</li><li>SMS</li><li>Web</li><li>Redes sociais (excluindo publicidade paga)</li><li>QR codes</li><li>Recomendações</li><li>Campanhas de mídia específicas, conjuntos de anúncios e anúncios</li></ul></td></tr><tr><td colspan="3"><p>Você pode criar audiências compostas por usuários que foram atribuídos a fontes de mídia próprias específicas. Além disso, você pode escolher o nível de granularidade e segmentar usuários que vieram de uma fonte de mídia própria específica, campanha, conjunto de anúncios e/ou anúncio individual.</p><p>Use as audiências que você criar para re-engajar esses usuários com mensagens personalizadas em mídia própria ou paga, ou como uma lista de exclusão para evitar que eles vejam anúncios irrelevantes ou desnecessários ao executarem campanhas de aquisição de usuário ou re-engajamento.</p></td></tr><tr><td colspan="3"><h4><span id="device"></span>Dispositivo</h4><p><img alt="device_filter.jpg" src="https://files.readme.io/184cd84f83b94c38f53ca5a9ef67a4f2c6ad8f8a78d832f6c7979a2c88f61cb5-46335667623441.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Marca do dispositivo</li><li>Modelo do dispositivo</li><li>Versão do aplicativo</li><li>Versão do sistema operacional</li><li>Operadora</li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>É</li><li>Não é </li></ul></td><td> <img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/> Valor selecionado</td></tr><tr><td colspan="3"><h4><span id="attribution"></span>Atribuição</h4><p><img alt="Attribution_filter.jpg" src="https://files.readme.io/c7aee01564562bc7d468d6b2bd59ff3d26a028d19382dfdbc35c3fe700f214e7-46335625087249.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><ul><li>Orgânico</li><li>Redirecionamento</li></ul></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Falso</li><li>True</li></ul></td><td> </td></tr><tr><td colspan="3"><h4><a href="./audiences-create-better-audiences-with-user-attribute-data" target="_blank"><span id="user-attributes"></span>Atributos do usuário</a></h4><p><img alt="user_attribute_filter.jpg" src="https://files.readme.io/add34f52509bf733f10364691e32ab88331a1caee4bbc4627fb665ec3826422d-46335625088145.jpg"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://files.readme.io/5fbc4d182835a4896c37fc8e1fd06f2844420a2c5a8de00e62d4a145f38c8559-46335625078033.jpg"/></p><p>Nome do atributo do usuário</p></td><td><p><img alt="B.jpg" src="https://files.readme.io/4b530dbfc66cf23e14e4045804ce9f7e97f63993adbd9a745fbea4c969cac041-46335667616017.jpg"/></p><ul><li>Tipo de string<ul><li>É</li><li>Não é</li></ul></li><li>Tipo de número<ul><li>É</li><li>É superior a</li><li>É inferior a</li></ul></li></ul></td><td><p><img alt="C.jpg" src="https://files.readme.io/9008324dc6fae630fd64a13e0cae65107f966d905c951151b1f908617bd4933c-46335625079441.jpg"/><br/>Para string: selecione um valor</p><p>Para número: insira um valor</p></td></tr></tbody></table>

</Accordion>

<div id="combine-rulesets" />

<Accordion title="Combine conjuntos de regras">

**Para combinar um conjunto de regras com uma audiência existente**

1. Acesse **Engajamento** > **Audiences**.
2. Clique em **Adicionar audiência**.  
   A aba **Criar** será exibida.
3. Insira um **Nome de audiência** exclusivo.
4. Selecione a plataforma: **Android** ou **iOS**.
5. [Opcional] Selecione **Configurações avançadas** para selecionar o  [identificador do usuário:](/docs/audiences-guide#user-identifier-device-id-vs-customer-id)
   * [Padrão] **ID do dispositivo**: avalia regras somente por ID do dispositivo.
   * **ID de usuário cliente**: avalia regras agrupando dispositivos usando o CUID. Use este método depois de verificar se seus dados têm CUIDs válidos.
6. Clique em **Existing audience**, depois selecione a audiência específica.
7. Selecione um operador: e, ou, excluir.

**Limitações:**

* A audiência existente deve estar na mesma plataforma (como o iOS ou Android) que a nova audiência.
* Uma audiência que se baseia em uma audiência existente não pode ser incluída.
* Uma audiência importada não pode ser usada.

</Accordion>

## Criar e gerenciar conexões de parceiros

Esta seção descreve como criar e gerenciar conexões de parceiros de mídia.

<div id="create-a-new-connection" />

<Accordion title="Criar uma nova conexão">

A aba **Conexões** exibe todas as conexões de parceiros e o status de cada uma. Todas as informações necessárias para o upload dos dados da audiência estão especificadas em cada conexão de parceiro. Você pode ter várias conexões para um único parceiro de mídia (usando contas diferentes, informações de login, etc.).

**Para criar uma nova conexão:**

1. Acesse **Engajamento** > **Audiences > Conexões**
2. Clique em **+ Nova conexão**.  

   **Nota:** se você estiver criando uma nova conexão de parceiro de dentro do criador de audiências, clique em **+ Adicionar conexão de parceiro** dentro da janela **Gerenciar conexões de audiência**.
3. Selecione um **Nome do parceiro**.
4. Insira um **Nome de conexão.**  

   **Nota:** deve ser um nome novo que nunca foi usado ao criar outras conexões.
5. Preencha os campos/dados de login para o parceiro. Alguns parceiros <Anchor target="_blank" href="/marketers/pt/docs/audiences-partner-connections">deram instruções detalhadas sobre como se conectar.</Anchor>   

   **Nota:** As credenciais devem ser exclusivas. Para evitar conexões duplicadas, você não poderá criar uma nova conexão se as credenciais já tiverem sido usadas em outra conexão de parceiro.
6. Selecione os identificadores de usuário que você autoriza compartilhar com esse parceiro.
   * Os identificadores compatíveis variam de acordo com o parceiro. Somente os identificadores compatíveis com o parceiro selecionado aparecerão na lista.
   * O download será feito apenas de dados que estejam em conformidade com a sua <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy">política de identificador a nível da conta</Anchor>. Você verá uma mensagem de alerta se selecionar um identificador que não é permitido pela política da sua conta.  
     ![doctored_connection_image.jpg](https://files.readme.io/5de138c4a2c2a3f26bebc6bd14d9703408a986dc4f8c53235d4be337784603af-46335625091345.jpg)
7. Clique em **Salvar.** Etapa 1:

</Accordion>

<div id="manage-connections" />

<Accordion title="Gerenciar conexões">

**Para gerenciar uma conexão existente:**

1. Selecione um parceiro.
2. Selecione uma conexão. ![Edit_connection_screen.jpg](https://files.readme.io/8c13e9dc04e98ca959b9ca250ff4954079d71e4ccd4cb2047f9037f31def0aeb-46335625091729.jpg)
3. Execute uma das ações abaixo:

| Opção | Procedimento |
| --- | --- |
| <span id="change-the-connection-name"></span>Alterar o nome da conexão | **Para alterar o nome da conexão,** edite-o diretamente no campo **Nome da conexão**. |
| <span id="reconnect"></span>Reconectar | **Para reconectar:**<ol><li>Se o status da conexão não estiver ativo, clique em **Reconectar**.</li><li>Atualize as credenciais de conexão ou faça o login para que o parceiro faça a autenticação novamente de acordo com as instruções na interface do usuário.</li></ol> |
| <span id="modify-user-identifiers"></span>Modificar identificadores de usuários | **Para modificar identificadores de usuário,** selecione/desmarque os identificadores de usuário que você permite que sejam compartilhados com esse parceiro. O download será feito apenas de dados que estejam em conformidade com a sua <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy">política de identificador a nível da conta</Anchor>. |
| <span id="delete-connection"></span>Excluir conexão | **Para excluir uma conexão:**<ol><li>Se houver alguma audiência conectada, remova-as da seguinte forma:<ol><li>Selecione a audiência.</li><li>A aba que conecta a audiência será aberta em uma nova guia.</li><li>Remova a conexão.</li><li>Feche a aba.</li></ol></li><li>Repita este procedimento até que nenhuma audiência esteja conectada à conexão.</li><li>Clique em **Excluir conexão**.</li></ol> |

</Accordion>

## Dashboard e métricas

Esta seção descreve as características e métricas de campanha que aparecem no dashboard.

<div id="audiences-dashboard" />

<Accordion title="Dashboard do Audiences">

[![new_dashboard_image_doctored.jpg](https://files.readme.io/98da5fffae48c7fafd48d45444085fb9bce804e2f03690994a23699604e0367e-46335625092369.jpg)](https://files.readme.io/98da5fffae48c7fafd48d45444085fb9bce804e2f03690994a23699604e0367e-46335625092369.jpg)

| Coluna | Descrição |
| --- | --- |
| <span id="audience-name"></span>Nome da audiência | Nome da audiência |
| <span id="size"></span>Tamanho | Todos os usuários que correspondem aos critérios de audiência |
| <span id="upload-size"></span>Tamanho do upload | Tamanho estimado da audiência disponível para upload após a aplicação da política de identificador de usuário a nível da conta e identificadores selecionados para as conexões de parceiros vinculados.<br /><br />**Atenção:** O tamanho real do lado do parceiro pode ser diferente por várias razões, incluindo:<ul><li>O processo de matching do parceiro.</li><li>O tamanho do upload para iOS reflete o número de segmentos enriquecidos com base nos IDFVs, que podem incluir IDFAs duplicados. A desduplicação é feita quando enviada para o parceiro, podendo causar discrepâncias de tamanho.</li></ul> |
| <span id="app-name"></span>Nome do aplicativo | O(s) aplicativo(s) referenciado(s) na definição da audiência. Esses não são necessariamente os aplicativos direcionados pelas campanhas que utilizam a audiência. |
| <span id="upload-to"></span>Fazer upload para | <ul><li>Ícones de parceiros para quem a audiência é enviada</li><li><Image alt="SplitAudiences.png" src="https://files.readme.io/85891dd56649980b8324ee9680e8e0d73898dc3f18a66428c147bc689ba08201-46335667629457.png" width="36px" /> indica que a audiência é dividida entre parceiros</li></ul> |
| <span id="incrementality"></span>Incrementalidade | Esta coluna será exibida se você se inscrever em <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview">Incrementalidade.</Anchor>  Os status incluem:<ul><li>**Pendente** - Período inicial de coleta de dados (48 horas) a partir da data de início da campanha</li><li>**Vincular campanha** - selecione as campanhas relevantes para vincular à experiência. Se tivermos uma sugestão de campanha para você, ela será pré-selecionada (com quaisquer sugestões adicionais ordenadas por relevância na lista suspensa).</li><li>**Ativo** - O experimento está em andamento</li><li>**Concluído** - O experimento terminou</li></ul>Ao clicar em um status, você será direcionado para o dashboard Incrementalidade. |
| <span id="upload-status"></span>Status do upload | <ul><li>O status atual do upload da audiência</li><li>O tooltip exibe a data e a hora do upload mais recente</li><li>Em caso de falha, clique em **Exibir detalhes** e faça correções de acordo com a mensagem de erro detalhada exibida</li></ul> |

</Accordion>

<div id="campaign-metrics" />

<Accordion title="Métricas da campanha">

#### métricas hash

#### Noções básicas sobre métricas da campanha

A seção **Métricas da campanha** no dashboard do Audiences exibe dados de campanhas que usaram uma audiência para o direcionamento (seja para inclusão, exclusão ou como base de uma audiência semelhante - lookalike).

* Usar uma audiência para o direcionamento (e decidir como ela é usada) faz parte da configuração das campanhas com parceiros de mídia. Os parceiros de mídia variam no suporte dado às diferentes maneiras de uso de audiências.

**Parceiros compatíveis:** atualmente, os dados estão disponíveis para o Meta ads, Google Ads e Snapchat. A seção **Métricas da campanha** do dashboard fica visível somente se você tiver audiências conectadas a parceiros compatíveis.

**Para ver as métricas da campanha:**

1. Role até a extrema direita do dashboard do Audiences para tornar a seção **Métricas da campanha** totalmente visível.
2. Use o seletor de data para selecionar o período do qual você deseja exibir os dados. (Por padrão, o dashboard exibe dados dos últimos 7 dias.)

**Para fazer download das métricas da campanha** **para o período de tempo selecionado:**

1. Clique no botão **Exportar** na parte superior do dashboard do Audiences.
2. Depois que o arquivo tiver sido gerado, ele será baixado automaticamente.


#### Visualização de resumo

A visualização inicial das **Métricas da campanha** exibe dados resumidos da campanha para cada audiência:

[<Image alt="campaign_metrics_summary_view.jpg" src="https://files.readme.io/a7fb8a1909ca9536914822008dc140cb66270d3ff9ceec8d09647a9f81b463ae-46335625093649.jpg" width="433px" />](https://support.appsflyer.com/hc/article_attachments/30626498333457)

| Coluna | Descrição |
| --- | --- |
| <span id="campaigns"></span>Campanhas | Número total de campanhas que usaram a audiência para direcionamento durante o período selecionado (campanhas executadas somente com parceiros compatíveis) |
| <span id="campaign-cost"></span>Custo da campanha | Custo total dessas campanhas durante o período de tempo selecionado |
| <span id="campaign-revenue"></span>Receita da campanha | Receita total atribuída a essas campanhas durante o período selecionado |

#### Visão detalhada

Na visualização resumida, clique no ícone <Image alt="show_detailed_view_icon.png" src="https://files.readme.io/597b5a91c35cab2df040fbf12be1b4bf41fa82471e4f533e8da48a7aa93bb174-46335667631761.png" width="24px" /> para entrar na visualização detalhada da audiência selecionada. (O ícone <Image alt="show_detailed_view_icon.png" src="https://files.readme.io/597b5a91c35cab2df040fbf12be1b4bf41fa82471e4f533e8da48a7aa93bb174-46335667631761.png" width="24px" /> aparece na extremidade direita de uma linha quando você posiciona o mouse em qualquer lugar dessa linha.)

A visualização detalhada exibe dados detalhados por parceiros e campanhas compatíveis:

[![campaign_metrics_detailed_view.jpg](https://files.readme.io/cee8910e07bdf6707feeda39dd5e480b19b27fad801dd99d501c2c1ceb4bb49d-46335667634193.jpg)](https://support.appsflyer.com/hc/article_attachments/30626490281617)

Se a audiência selecionada foi usada para direcionar mais de um aplicativo, use a lista suspensa ![pin_A.png](https://files.readme.io/dcf60cd17a1135e63f6443728c3d713d9cacd6af0e1c010c226d1a092770c40b-46335667636113.png) para filtrar os dados por aplicativo.

Clique no link do dashboard de **Visão geral** ![pin_B.png](https://files.readme.io/b8c902aab2ca2f748dfe647dab3f52e66f6c161d173cb3cf53dbf4ecdc1edef1-46335667637009.png) para visualizar as campanhas no dashboard Visão geral:

* O dashboard será aberto em uma nova aba do navegador, filtrado automaticamente pelas campanhas relevantes.
* Se o link do **dashboard de Visão geral** estiver desativado, você poderá ativá-lo selecionando um único aplicativo na lista suspensa ![pin_A.png](https://files.readme.io/dcf60cd17a1135e63f6443728c3d713d9cacd6af0e1c010c226d1a092770c40b-46335667636113.png). Assim que o link estiver ativado, clicar nele o levará ao dashboard de Visão geral do aplicativo selecionado.

| Coluna | Descrição |
| --- | --- |
| <span id="cost"></span>Custo | Custo da campanha durante o período de tempo selecionado (no total, depois dividido por parceiro e campanha compatíveis) |
| <span id="revenue"></span>Resultados | Receita atribuída às campanhas durante o período selecionado (no total, depois dividida por parceiro e campanha compatíveis) |
| <span id="daily-reach"></span>Alcance diário | O número médio de usuários únicos por dia que viram anúncios da campanha durante o período de tempo selecionado (conforme reportado pelo parceiro) |

#### Fontes de dados e disponibilidade

É mais fácil entender a disponibilidade dos dados do **Métricas da campanha** quando analisamos de onde os dados vêm:

* **Dados do parceiro:** como você seleciona a(s) audiência(s) a ser alvo de campanhas específicas através de seus parceiros de mídia, somente estes parceiros são capazes de fornecer certas informações:
  * A conexão de uma audiência a uma campanha (em outras palavras, o fato de que uma audiência específica foi usada para segmentação por essa campanha)
  * O número de usuários exclusivos por dia que visualizaram anúncios da campanha ("alcance diário")
* **Dados da Appsflyer:** os dados de custo e receita são fornecidos pela AppsFlyer.

<div id="partner-data-availability" />

<Accordion title="Disponibilidade de dados do parceiro">

Os dados são relatados apenas para campanhas executadas com [parceiros compatíveis](/docs/audiences-guide#noções-básicas-sobre-métricas-da-campanha).

* **Nota:** o Google Ads não é compatível com relatórios de alcance diário.

</Accordion>

<div id="appsflyer-data-availability" />

<Accordion title="Disponibilidade de dados da AppsFlyer">

Os dados de custo e receita estarão disponíveis no contexto das **Métricas da campanha** se forem relatadas para seus aplicativos em outras áreas da AppsFlyer (por exemplo, os dashboards de Visão geral e de Eventos).

* Os dados de custo requerem uma assinatura do <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">ROI360</Anchor>.
* Os dados de receita exigem que você tenha configurado a <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution">atribuição de receita de anúncios</Anchor> e/ou a <Anchor target="_blank" href="/marketers/pt/docs/roi360-revenue-attribution-overview">atribuição de receita de eventos in-app</Anchor>.

</Accordion>

<div id="why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners" />

<Accordion title="Por que não vejo os dados de métricas da campanha para campanhas executadas com parceiros compatíveis?">

Os dados de métricas da campanha estão disponíveis apenas para:

* Campanhas que estão conectadas a uma audiência.
* Campanhas em execução em sites de parceiros de mídia compatíveis.
* Campanhas ativas no período principal selecionado.
* Campanhas das quais recebemos tráfego de instalação, dentro do intervalo de datas selecionado no filtro Métricas da campanha.
* Usuários configurado para a conexão de parceiro não têm permissões para receber dados no nível da campanha. Para visualizar esses dados, altere as permissões do usuário com o parceiro ou use credenciais diferentes nas configurações de conexão do parceiro.

</Accordion>

</Accordion>

## Características e limitações

Observe as seguintes características e limitações.

<div id="traits" />

<Accordion title="Características">

| Caraterística | Com suporte. | Observações |
| --- | --- | --- |
| Redes de anúncios | **X** |  |
| Agências | **X** |  |
| Transparência da agência | **X** |  |
| Fuso horário específico do aplicativo | N/D |  |
| Moeda específica do aplicativo | N/D |  |
| Proteção de dados | ✓ | Os dados da sua audiência podem ser processados para auxiliar os recursos do Audiences com tecnologia de IA. Os dados da sua conta nunca são compartilhados, sendo usados apenas para melhorar os modelos e as previsões internas. |
| Limitações de tamanho | N/D |  |
| Dados não orgânicos | ✓ | Incluso |
| Dados orgânicos | ✓ | Incluso |
| Atualização dos dados | UTC diário | <ul><li>As atualizações são enviadas aos parceiros diariamente.</li><li>As listas de eventos in-app no construtor de regras são atualizadas diariamente.</li></ul> |
| Dados históricos | ✓ | O Audiences tem acesso aos dados de eventos in-app 90 dias antes da data da sua assinatura do Audiences (para cliques e impressões, esse prazo é de 31 dias). Os dados estarão disponíveis por completo assim que o processo de preenchimento for concluído (o que pode levar até 2 semanas). |
| Acesso do utilizador à conta | ✓ | <ul><li>Algumas funções, como download de CSV, configuração de conexões de parceiros S3, SFTP e Slack, exigem permissão da conta do usuário para acessar dados brutos.</li><li>Como medida de segurança, se a conta de um usuário que criou uma audiência tiver sido excluída, a AppsFlyer deixa de fazer o upload dos dados dessa audiência para o(s) parceiro(s) de mídia. Para verificar o status de upload das suas audiências, acesse **Engajamento** > **Audiences**. Para reativar a audiência, duplique-a e configure as definições de [audiência dividida](/docs/audiences-guide#audience-split-and-control-groups) .</li></ul> |

</Accordion>

<div id="limitations" />

<Accordion title="Limitações">

| Limitações | Observações |
| --- | --- |
| Dados de atribuição | Os dados de cliques e impressões contêm apenas dispositivos que possuem advertising\_id/idfa na sua URL de clique original. Os dispositivos de usuários de SRNs, que não usam links de atribuição externos, não estão incluídos nos dados de cliques para audiências. |
| Criar uma audiência | <ul><li>Os nomes das audiências não podem ser alterados pelos parceiros conectados.</li><li>Ao criar uma audiência, apenas os 100 principais eventos são exibidos. No entanto, quando você começa a inserir um nome de evento, todos os eventos são exibidos.</li><li>Ao usar o filtro Receita Total no criador de consultas, o tamanho estimado da audiência não está disponível. Isso não afeta o processo de criação da audiência.</li></ul> |
| Conexões | Criar conexões de parceiros duplicadas (conexões com a mesma conta / login / property ID / etc.) não é permitido e resultará em erros. |
| Baixar audiência em arquivo CSV | Tamanho do arquivo para download limitado a 5 milhões de registros. |
| Audiências importadas | Não é possível combinar audiências importadas com outras audiências ou conjuntos de regras. |
| Audiências inativas: | As audiências inativas serão pausadas. Isso significa que elas não serão mais calculadas ou enviadas para parceiros conectados. A audiência sempre pode ser "retomada" ao clicar em Fazer upload agora. Isso retomará os cálculos de audiência e os uploads automáticos para os parceiros como antes. |
| Não suportado | Listamos abaixo recursos indisponíveis:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/audiences-partner-connections#google-ads">Google Ads</Anchor>: campanhas de UAC não são suportadas. Outros tipos de campanha são permitidos.</li><li>Windows Phone</li><li>Valores de eventos aninhados</li></ul> |
| Número de audiências | <ul><li>Você pode criar até 100 audiências por dia.</li><li>Você pode ter até 100 audiências personalizadas/sugeridas ativas por vez.</li><li>Você pode ter até 500 audiências importadas ativas de uma só vez.</li></ul> |
| Conjuntos de regras | <ul><li>Nos conjuntos de regras, os eventos in-app são limitados a 100 valores únicos por atributo. Por exemplo, se o evento for "purchase" e o atributo for "content-type", somente poderá haver 100 (ou menos) tipos de conteúdo possíveis. Entretanto, os valores numéricos são ilimitados. Se forem necessários mais valores por atributo, entre em contato com seu CSM ou envie um e-mail para hello@AppsFlyer.com.</li><li>Somente números inteiros são compatíveis com os filtros de conjunto de regras numéricas. Os números do tipo flutuante (decimal) não são compatíveis. Exemplo: a receita in-app é igual a US$ 1 e é compatível, mas US$ 1,5 não é.</li></ul> |
| Relatório S2S | Os identificadores de usuário (IDFV ou IDFA) devem ser enviados em eventos in-app de payload S2S. Além disso, o IDFV ou IDFA deve ser consistente com a coleta do SDK da AppsFlyer. Isso garantirá que os dados não sejam perdidos e que os cálculos de audiência sejam precisos. |

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview">Guia de incrementalidade</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/run-an-incrementality-for-remarketing-experiment">Executando um experimento de incrementalidade</Anchor>

<div data-zendesk-anchors="audiences-basics=no%C3%A7%C3%B5es-b%C3%A1sicas-sobre-o-audiences h_01HBQMA619CKEESZD3ADSP3PSB=no%C3%A7%C3%B5es-b%C3%A1sicas-sobre-o-audiences audience-split-and-incrementality-testing=divis%C3%A3o-de-audi%C3%AAncias-e-testes-de-incrementalidade h_01HBQMA619KMJFVX7Y8MXMMQ6N=divis%C3%A3o-de-audi%C3%AAncias-e-testes-de-incrementalidade get-started=iniciar h_01HBQMA619118PWF4TA98C4X0B=iniciar create-and-manage-audiences=criar-e-gerenciar-audi%C3%AAncias h_01HBQMA619DBX2C7DRY7MSV3P9=criar-e-gerenciar-audi%C3%AAncias h_01HBQMA6195AT0YD7783V6BQR6=create-a-custom-audience h_01JXA0GDBMBX541W6P63XXDVKQ=observa%C3%A7%C3%B5es h_01HBQMA619F2P2CVPCSMX9RTKB=create-a-suggested-audience h_01HBQMA619RBRYNMVMNQ839196=exemplo-de-caso-de-uso h_01JXA0WJFMSHA710CTNF84BPQ5=observa%C3%A7%C3%B5es-1 h_01HBQMA619ATHVJARHYXQNY955=import-an-audience h_01HBQMA6193FFM66XDTB6WYX06=connect-an-audience-to-media-partners user-identifier%E2%80%94device-id-vs-customer-id=user-identifier-device-id-vs-customer-id h_01HBQMA61A192YFES8TK1347FJ=user-identifier-device-id-vs-customer-id 01ECF4ZD0NWN5QQPP88ZKW0578=exemplo-id-do-dispositivo-vs-cuid 01ECF4ZD0WNEF6FRPF1NJHZ9WR=audience-split-and-control-groups h_01HBQMA61ANM52HBDAFA5QZPFN=manage-audiences h_01HT04HW2VBB9ZY28V5KQ5K2AJ=pause all-about-rulesets=tudo-sobre-conjuntos-de-regras h_01HBQMA61ANB4K0TCJ4WBHMV8D=tudo-sobre-conjuntos-de-regras h_01HBQMA61A30YGERD8Z6DXV3KA=audience-segmentation-rulesets h_01HBQMA61AF7V3M0Y8ZN1R0HZC=ruleset-examples h_01HBQMA61ATV5MHN35XMTJ8MEH=exemplo-regra-baseada-em-localiza%C3%A7%C3%A3o h_01HBQMA61ATB7NYKBP7CD6SZZH=exemplo-regra-baseada-em-atributos-do-usu%C3%A1rio h_01HBQMA61APWHKS4EP2NKABSQD=exemplo-receita 01ECF4ZD0MJ8HVQCC54YHFE6DX=exemplo-filtro-de-m%C3%ADdia-pr%C3%B3prio h_01JRAGFYEQ28R6RQNPEK6WZV2F=exemplo-remarketing h_01HBQMA61AEKT6N97SJBW4B01C=ruleset-filters h_01HBQMA61A17Y4928D2ZDGAEXV=events h_01HBQMA61BK8NZF79KDPK0JBX6=inapp-events h_01K5EHBY8ESJFS3GKJW1RCB99X=contains-does-not-contain-logic h_01HBQMA61B4FGBE11W6BW2Z9AH=revenue::3358edf4 h_01HBQMA61BX9XQKBX3MAGYXC2Y=geo h_01HBQMA61B9DRMSNKJM3B0WBE1=owned-media h_01HBQMA61BC1G2VZSJEJF90T7Q=device h_01HBQMA61BF2N8FN6TJ3JD6YXC=attribution h_01HBQMA61CKVMYYS8GG6CP72WD=user-attributes h_01HBQMA61C7K8R4AR13D4WHTHX=combine-rulesets create-and-manage-partner-connections=criar-e-gerenciar-conex%C3%B5es-de-parceiros h_01HBQMA61C6WS72DQ8FXVR0KVW=criar-e-gerenciar-conex%C3%B5es-de-parceiros h_01HBQMA61CRDF41WBYCDQ91M3R=create-a-new-connection h_01HBQMA61CXZYEW2R12KS99X2N=manage-connections dashboard-and-metrics=dashboard-e-m%C3%A9tricas h_01HBQMA61C6WPFFR1F8P0HE4KA=dashboard-e-m%C3%A9tricas h_01HBQMA61CMPNC9TYAW82ED18Q=audiences-dashboard h_01HBQMA61CWHR9GDANKT7P6Z27=campaign-metrics metrics-hash=m%C3%A9tricas-hash h_01HBQMA61CMF3WZFPXKY89076K=m%C3%A9tricas-hash campaign-metrics-basics=no%C3%A7%C3%B5es-b%C3%A1sicas-sobre-m%C3%A9tricas-da-campanha h_01HBQMA61C4D5HFCDY83HNF5K7=no%C3%A7%C3%B5es-b%C3%A1sicas-sobre-m%C3%A9tricas-da-campanha summary-view=visualiza%C3%A7%C3%A3o-de-resumo h_01HBQMA61DW9Z84G8CH1RNY2RF=visualiza%C3%A7%C3%A3o-de-resumo h_01K3R8C7GK77FNVZ3N0C3XZGYG=visualiza%C3%A7%C3%A3o-de-resumo detailed-view=vis%C3%A3o-detalhada h_01HBQMA61D3VHDKD103EMN61YH=vis%C3%A3o-detalhada data-sources-and-availability=fontes-de-dados-e-disponibilidade h_01HBQMA61DB595QKRTPE97F94E=fontes-de-dados-e-disponibilidade h_01HBQMA61DCV0M97GMXRA1A30F=partner-data-availability h_01HBQMA61DXNR275AT9SK0G32S=appsflyer-data-availability h_01HBQMA61DH9P5B1H5GYXQ9CCN=why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HBQMA61DT46P43FNSRC1KGAX=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HBQMA61DYHF0REXYKDQBDXP5=traits h_01HBQMA61D28F5RG2WXT801XXZ=limitations h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=veja-tamb%C3%A9m" />

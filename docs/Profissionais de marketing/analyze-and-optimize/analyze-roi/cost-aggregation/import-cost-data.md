---
title: Importar dados de custo
metadata:
  keywords:
    - Ad Network
    - Agency
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Xpend
    - Marketers
    - ROI360
    - Ad Networks
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
    - Ad Networks
  created_at: '2019-09-15T15:53:44Z'
  edited_at: '2026-08-19T00:01:04Z'
  id: 360002516838
  locale: pt
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/pt/articles/360002516838
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** o Cost Import, parte do ROI360 da AppsFlyer, permite que os anunciantes tenham uma cobertura completa e precisa de seus custos de marketing ao importar arquivos CSV via upload ou e-mail.

<div id="overview" />

## Visão geral

Use o Cost Import para:

* obter os custos de campanha de qualquer atividade de marketing (campanhas mobile, campanhas de influenciadores, CTV e mais) para a AppsFlyer. Isso é particularmente importante para fontes de mídia que não relatam custos via API ou link de atribuição.
* Substitua e corrija retroativamente os dados de custo existentes.

O custo é relatado por meio de arquivos CSV ou enviados por e-mail para a AppsFlyer. Uma vez que a AppsFlyer recebe o arquivo, os dados são processados e ficam disponíveis nos seus dashboards e relatórios dentro de algumas horas. Com isso você tem uma visão completa dos custos da sua campanha e do seu ROI.

**Observação**:

* As ad networks podem importar arquivos de custo para seus clientes se as permissões relevantes forem fornecidas.
* As agências não podem fazer upload de dados. Elas podem preparar seus arquivos e enviá-los ao anunciante para upload.

<div id="procedures" />

## Procedimentos

Para usar o Cost Import e enviar dados de custo para a AppsFlyer, você precisa:

1. [Preparar o arquivo CSV](/docs/import-cost-data#prepare-csv-file-with-cost-data) com os dados de custo a serem enviados.
2. Enviar o arquivo para a AppsFlyer via:
   * [Upload](/docs/import-cost-data#email-file) na interface da AppsFlyer.
   * [E-mail](/docs/import-cost-data#email-file). [E-mail](/docs/import-cost-data#email-file) **Atenção:** Para aplicativos em plataformas CTV, PC e console, use somente esse método.

Veja as seções abaixo para instruções detalhadas.

<div id="prepare-csv-file-with-cost-data" />

<Accordion title="Prepare o arquivo CSV com dados de custo">

Anunciantes, ad networks e agências podem preparar o arquivo CSV de Cost Import. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv">Ver arquivo de amostra</Anchor>

**Para preparar o arquivo CSV**:

* Siga o esquema do arquivo, formato e regras detalhadas nas tabelas a seguir.  
  Opcionalmente, você pode incluir os cliques e as impressões reportados pela ad network junto com seus dados de custo. **Atenção:** Se você usar Excel ou Google Sheets para criar o arquivo, siga as [instruções de formatação do Excel e do Google Sheets](/docs/import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file).

<div id="csv-schema" />

#### Esquema CSV

<table><thead><tr><th><p><span>Nome da coluna </span></p><p><span>(diferenciação de maiúsculas e minúsculas)</span></p></th><th><span>Formato/observação</span></th><th><span>Exemplo</span></th><th><span>Obrigatoriedade</span></th></tr></thead><tbody><tr><td><span>data</span></td><td><ul><li><span>A data em que o custo ocorreu</span></li><li> <span>Formato: String</span><br/><span>(Recomendado):</span><ul><li><span>AAAA-MM-DD</span></li><li><span>AAAA/MM/DD</span></li><li><span>MM-DD-AAAA</span></li><li> <span>MM/DD/AAAA </span><br/> </li></ul></li><li>Datas futuras não permitidas</li><li> <strong>Prática recomendada</strong>: use o mesmo fuso horário definido para o seu app na AppsFlyer.</li><li> <strong>Atenção:</strong> Você está usando Excel/Google Sheets para preparar o arquivo? <a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">Leia aqui</a>. </li></ul></td><td><ul><li><span>05-2019-30</span></li><li><span>2019/05/30</span></li><li><span>05-30-2019</span></li><li>5/30/2019</li><li>05-30-2019</li><li>05/30/2019</li></ul></td><td><span>✓</span></td></tr><tr><td><span>app-id</span></td><td><ul><li><span>Formato: String</span></li><li> <span>O App ID como ele aparece na AppsFlyer</span>.</li><li>Vários app IDs são permitidos em um único arquivo</li><li>Todos os app IDs precisam pertencer à mesma conta de anunciante.</li></ul></td><td><ul><li><span>com.app.nome </span></li><li><span>id12356789</span></li></ul></td><td><span>✓</span></td></tr><tr><td><span>media-source</span></td><td><ul><li><span>Formato: String</span></li><li><span>Nome da fonte de mídia <strong>exatamente</strong> como aparece na AppsFlyer. <strong>Atenção:</strong> Inclua o sufixo _int se relevante.</span></li><li> <span>Somente um canal de mídia por arquivo é permitido.</span> /span&gt; São permitidos vários aplicativos para o mesmo canal de mídia</li></ul></td><td><span>network_x_int</span></td><td><span>✓</span></td></tr><tr><td><span>Twitter</span></td><td><ul><li> <span>Formato: String</span><span></span> </li><li><span>Nome da campanha. Se o nome da campanha aparecer na ad network, o nome nesse arquivo deve corresponder a ele (sensível a maiúsculas e minúsculas).</span></li><li>Não use o mesmo nome de campanha para vários aplicativos.</li></ul></td><td>campaign_a</td><td><p><span>✓</span></p><p><span><strong>Atenção</strong>: se existirem dados de atribuição com nome e ID, o CSV deverá conter ambos para garantir a correspondência.</span></p></td></tr><tr><td><span>gasto</span></td><td><ul><li><span>Custo monetário</span></li><li><span>Cinco dígitos permitidos após a vírgula</span></li><li><span>O valor 0 (zero) é permitido</span></li><li> <span><strong>Atenção</strong>: </span><ul><li>Separadores de 1.000 com vírgula não são permitidos, por exemplo: "2,874.12".</li><li>Você está usando Excel/Google Sheets para preparar o arquivo? <a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">Leia aqui</a>.</li></ul></li></ul></td><td><p><span>2874.12345</span></p></td><td><span><span>✓</span></span></td></tr><tr><td><span>cliques reportados</span></td><td><ul><li><span>Formato: String</span></li><li><span>O número de cliques reportados pela ad network.</span></li><li><span>Somente números inteiros. Sem casas decimais, separadores por vírgula, símbolos de moeda nem notação científica.</span></li><li><span>O valor deve ser 0 ou maior. O valor 0 é permitido.</span></li></ul></td><td><span>1200</span></td><td><span>Não</span></td></tr><tr><td><span>impressões reportadas</span></td><td><ul><li><span>Formato: String</span></li><li><span>O número de impressões reportadas pela ad network.</span></li><li><span>Somente números inteiros. Sem casas decimais, separadores por vírgula, símbolos de moeda nem notação científica.</span></li><li><span>O valor deve ser 0 ou maior. O valor 0 é permitido.</span></li></ul></td><td><span>45000</span></td><td><span>Não</span></td></tr><tr><td><span>geo</span></td><td><ul><li><span>Formato: String</span></li><li> <span>Código de duas letras do país, seguindo as regras </span><a href="https://www.iso.org/iso-3166-country-codes.html"><span>ISO 3166</span></a><span>. <strong>Atenção</strong>: envie dois caracteres, sem espaços em branco.</span> </li><li> <span>Para o Reino Unido, use UK,</span><span> e não GB.</span><br/> </li></ul></td><td><p><span>US, CN, AU</span></p></td><td><span>Não</span></td></tr><tr><td><span>símbolos monetários</span></td><td><ul><li><span>Formato: String</span></li><li>Código de três letras da moeda utilizada, seguindo as regras <a href="https://www.iso.org/iso-4217-currency-codes.html" target="_blank">ISO 4217</a>. <strong>Atenção:</strong> envie três caracteres, sem espaços em branco no início ou no final.</li><li> <span>É permitido um código de moeda por aplicativo. D</span><span>iferentes aplicativos podem ter diferentes códigos de moeda </span>.  </li></ul></td><td><span>USD, GBP, EUR, JPY</span></td><td><p><span>Não.</span></p><p><span>O padrão será USD se deixado em branco.</span></p></td></tr><tr><td><span>campaign-id</span></td><td>Formato: String</td><td>abc1234def</td><td rowspan="5"><p>Não.</p><p><strong>Atenção:</strong> se existirem dados de atribuição com nome e ID, o CSV deverá conter ambos para garantir a correspondência.</p></td></tr><tr><td><span>conjunto_de_anúncios</span></td><td>Formato: String </td><td>my_adset_1</td></tr><tr><td><span>adset-id</span></td><td>Formato: String</td><td>id5678ghi</td></tr><tr><td><span>Anúncio</span></td><td>Formato: String </td><td>my_ad_name</td></tr><tr><td> <span>ad-</span><span>id</span> </td><td>Formato: String </td><td>id91011jkl</td></tr><tr><td><span>site-id</span></td><td><ul><li>Formato: String </li><li>ID exclusivo que identifica o publisher que exibe o anúncio. <a href="./about-link-structure-and-parameters#site-id-parameter" target="_blank">Saiba mais</a> </li></ul></td><td>id1213mno</td><td>Não</td></tr><tr><td><span>Canal</span></td><td>Formato: String </td><td> Vídeo</td><td>Não</td></tr><tr><td><span>keywords</span></td><td> <span>Token do anunciante</span>:</td><td><ul><li>better</li><li>better you app</li><li>better you online</li></ul></td><td>Indisponível</td></tr><tr><td><span>agency</span></td><td><ul><li>Regra</li><li>O nome da agência. O valor no parâmetro <code>af_prt</code>.</li><li>Apenas uma agência pode ser incluída em um arquivo e apenas campanhas gerenciadas por essa agência podem ser incluídas no arquivo.</li><li>O nome da agência é obrigatório por linha. Não são permitidas células em branco na coluna agência.</li><li>A agência deve ter permissão para todos os aplicativos incluídos no arquivo.</li><li>Somente anunciantes podem fazer o upload do arquivo. As agências não podem fazer upload de dados. Elas podem preparar seus arquivos e enviá-los ao anunciante para upload.</li><li>Se os dados de custo forem reenviados para as mesmas datas e o nome da agência (<code>af_prt</code>) for incluído posteriormente, você terá dados de custo duplicados.</li></ul></td><td>Nome da agência</td><td>Indisponível</td></tr><tr><td colspan="4"><span><strong>Atenção</strong>: nomes que incluem caracteres especiais (fora do alfabeto latino) devem ser codificados usando UTF-8.</span></td></tr></tbody></table>

<div id="csv-format-and-rules" />

#### Formato e regras CSV

| Regra | Requisito |
| --- | --- |
| Caracteres proibidos | Os campos no formato de string não podem ter `=`, `+`, `-` ou `@` como primeiro caractere. Por exemplo, `@example_campign` ou `=123` são proibidos. |
| Proprietário do aplicativo | É permitido um anunciante (proprietário do aplicativo) por arquivo. Vários aplicativos da mesma conta de anunciante são permitidos. |
| Extensão filename | Exemplo de CSV: abc123.csv |
| Estrutura do arquivo | <ul><li>**Formato:** os arquivos têm formato CSV, o que significa que cada coluna é separada por uma vírgula.</li><li>**Linha do header**: a primeira linha é uma linha de header que corresponde ao esquema</li><li>**Linhas de dados**: contém as colunas obrigatórias. **Atenção:** certifique-se de que não haja espaços em branco nos seus dados. Por exemplo, [USD ] (o espaço em branco após o **D** deve ser alterado para [USD].</li><li>**Linhas em branco**: não são permitidas.</li><li>**Linhas duplicadas** com a mesma chave: não são permitidas. A chave é derivada do uso dos campos obrigatórios.</li><li>**Células em branco:** <mark>não são permitidos valores vazios no arquivo.</mark> Se você não quiser fazer o upload de determinados campos, eles não devem ser enviados no arquivo.</li></ul> |
| Hierarquia publicitária | O custo deve ser registrado no nível da campanha, sendo opcionais outras dimensões na hierarquia de publicidade.<br /><br />Quaisquer dados parciais enviados em uma hierarquia inferior substituirão todos os dados do nível da campanha para baixo.<br /><br />**Por exemplo:** se você importar um arquivo com os custos de campanha para o adset 1 e importar separadamente outro arquivo para o adset 2 da mesma campanha, o custo total da campanha será substituído, exibindo somente os dados do adset 2. Para o custo total da campanha, o arquivo importado precisa incluir o adset 1 e o adset 2. |

</Accordion>

<div id="upload-file" />

<Accordion title="Upload do arquivo">

Anunciantes e ad networks podem enviar arquivos CSV de Cost Import.

**Pré-requisitos**: As ad networks exigem [permissão de Cost Import do anunciante](/docs/import-cost-data#cost-import-permissions-for-ad-networks). 

Para enviar o arquivo CSV via interface do usuário da AppsFlyer:

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **Cost Import**.  
   A página de Cost Import é exibida. **Etapa 1**:
2. Clique em **+ Importar arquivo de custo**  
   A janela de Cost import é aberta.
3. Arraste o arquivo CSV para a janela de **importação de arquivo de custo**.  
   A mensagem processando arquivo é exibida.
4. Se uma mensagem de erro for exibida durante o upload: corrija o erro e repita as etapas necessárias.
5. A janela **Cost Import: resumo do arquivo** é exibida.
6. Faça uma das seguintes opções:
   * Para cancelar o upload, clique em **Cancelar ingestão**.
   * Para concluir o processo, clique em **importar arquivo.**  
     A mensagem "Tudo pronto!" é exibida.
   * Se uma mensagem de erro for exibida, siga as [instruções da mensagem de erro.](#error-messages-and-solutions)
7. Clique em **importar outro arquivo** ou em **concluído**.

</Accordion>

<div id="email-file" />

<Accordion title="Arquivo de e-mail">

Anunciantes e ad networks podem enviar arquivos CSV de Cost Import por e-mail.

**Pré-requisitos**:

* **Anunciantes**: 
  * O e-mail do remetente deve ser um usuário cadastrado da AppsFlyer.
* **Ad networks**:
  * O e-mail do remetente deve ser um usuário cadastrado da AppsFlyer.
  * [Permissão de Cost Import do anunciante](/docs/import-cost-data#cost-import-permissions-for-ad-networks).

Para enviar o arquivo CSV por e-mail:

1. Obtenha o [token para importação por e-mail](/docs/import-cost-data#token-for-email-import).
   1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **Cost Import.** Etapa 1:
   2. No canto superior direito da página, clique em **Token para importação de e-mail.**
   3. Copie e salve o token.
2. Coloque os seguintes campos no e-mail:
   * **Para**:`adspend-upload@appsflyer.com`
   * **CC:** **Usuários que devem receber uma cópia automática das respostas ao e-mail**
   * **Assunto:** Cole o token para importação no campo de assunto.
   * **Anexar**: Arquivo CSV com os dados.
3. Envie o e-mail.
   * Uma vez que o arquivo é recebido e processado, um e-mail de status resume os detalhes, problemas ou erros encontrados durante o processamento. O e-mail é enviado a todos que fazem parte do e-mail de envio e ao administrador. Quando erros são identificados, [siga as instruções da mensagem de erro](#error-messages-and-solutions).
   * Você pode ver o status dos arquivos enviados no [dashboard de Cost Import](/docs/import-cost-data#error-messages-and-solutions)

</Accordion>

<div id="dashboard" />

## Painel

O dashboard de Cost Import permite que você faça upload de arquivos e visualize detalhes de arquivos enviados anteriormente.

<div id="cost-import-dashboard" />

<Accordion title="Dashboard de Cost Import">

Para visualizar o dashboard de Cost Import, abra a AppsFlyer e, no menu lateral, selecione **Configurações** > **Cost Import**.

Detalhes sobre as informações disponíveis para arquivos importados anteriormente estão descritos na tabela a seguir.

| Nome da coluna | Descrição |
| --- | --- |
| Nome do arquivo CSV | O nome dos arquivos de custo enviados para a AppsFlyer. |
| Upload date | Data em que o arquivo foi enviado. |
| Canal de mídia | Canal de mídia incluído no arquivo. |
| Date range | Primeiras e últimas datas no arquivo em que o gasto com anúncios ocorreu. |
| Matched rows (%) | A porcentagem de linhas no arquivo com correspondência entre o custo e a atribuição. [Saiba mais](#matched-rows). |
| Estado | O status do arquivo importado:<ul><li>**Success**: ação concluída com sucesso. O custo é registrado e fica disponível nos dashboards e relatórios da AppsFlyer.</li><li>**Validation error**: problema no sistema da AppsFlyer. Aguarde 10 minutos e tente novamente. Se falhar novamente, entre em contato com o suporte da AppsFlyer.</li><li>**No permissions**: o token não foi aprovado para esse aplicativo.<ul><li>Anunciantes: certifique-se de que o App ID está correto.</li><li>Ad networks: confirme com o anunciante que ele lhe deu permissão para usar o Cost Import.</li></ul></li><li>**Reverted**: ação concluída com sucesso. O arquivo foi substituído por outros dados.</li></ul> |
| Action | <ul><li>At the file level: se você tiver permissões para todos os aplicativos contidos no arquivo, você pode:<ul><li>**Baixar o arquivo CSV**: essa é uma cópia do arquivo CSV importado.</li><li>**Baixar o relatório sem correspondência** para todos os aplicativos no arquivo. Veja a seção de correspondência de linhas dessa tabela para saber mais.</li></ul></li><li>At the app level: Se você clicar em um arquivo específico, as informações sobre todos os Cost Import para o aplicativo serão exibidas, a partir daquele arquivo específico, bem como outros arquivos. Se você tiver permissão para o aplicativo, você pode:<ul><li>**Baixar os dados do aplicativo.**</li><li>**Baixar um relatório sem correspondência** para o aplicativo</li><li>**Reverter** (cancelar) o Cost Import para o aplicativo selecionado.</li></ul></li></ul> |

</Accordion>

<div id="matched-rows" />

<Accordion title="Correspondência de linhas">

A correspondência de linhas é o processo onde o custo relatado via upload é combinado com os dados de atribuição registrados na AppsFlyer. Isso é feito usando todos os nomes de dimensão (não IDs) disponíveis, como canal de mídia, campanha, conjunto de anúncios, anúncio, etc. Se todas as linhas corresponderem, elas serão designadas como is-matching=TRUE. Se todas as linhas corresponderem, elas serão designadas como is-matching=TRUE.

O custo é registrado e fica disponível nos dashboards e relatórios da AppsFlyer, independentemente do status de correspondência.

A porcentagem de linhas correspondentes é exibida no dashboard de Cost Import. Se linhas não correspondentes forem inesperadas ou o número de linhas correspondentes (%) for maior do que o esperado:

* Baixe o relatório Unmatched para investigar a causa. O relatório Unmatched contém uma coluna, com correspondência, que pode ter um valor de linhas TRUE (com correspondência) ou FALSE (sem correspondência).
* Se necessário, cancele a importação.
* Veja a seção Ação desta tabela para detalhes.

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="using-excel-or-google-sheets-to-prepare-csv-file" />

<Accordion title="Usar o Excel ou Google Sheets para preparar o arquivo CSV">

Ao usar o Excel/Google Sheets para criar um arquivo CSV, as colunas de data e gastos precisam ser formatadas corretamente antes de salvar o arquivo como um arquivo CSV. Após salvar o arquivo, verifique se o conteúdo está formatado corretamente. Use as seguintes diretrizes para:

* Formatar as células de data.
* Formatar as células de gasto.
* Verificar o formato do conteúdo.

<div id="format-date-cells" />

#### Formatar células de data

**Para formatar células de data no Excel com o formato AAAA-MM-DD**:

1. Selecione as células a serem formatadas.
2. Clique com o botão direito e selecione **Formatar células**.  
   A janela formatar células é aberta.  
   <Image alt="Formatdate..png" src="https://files.readme.io/43d0f370f299d73b8ce93fec1c912cb7525d0071db779a64a58f5917df2a5531-360004042458.png" width="379px" />
3. Selecione **Personalizada**.
4. No campo Tipo, insira **AAAA-MM-DD**
5. Clique em **OK**.  
   A data é formatada.

<div id="formatting-spend-cells" />

#### Formatando células de gastos

O Excel geralmente formata células de valor com vírgula para separar os milhares, conforme mostrado na figura. Esse formato não é adequado para arquivos de Cost Import.

<Image alt="mceclip1.png" src="https://files.readme.io/d54e21ddd937dfe25a33bb96193761a5a724c22a35a55bb7d71eb03a6433d7ed-360003949177.png" width="291px" />

**Para formatar células de gastos sem uma vírgula de milhar:**

1. Selecione as células a serem formatadas.
2. Clique com o botão direito e selecione **Formatar células**.  
   A janela formatar células é aberta.
3. Selecione **Número**.  
   <Image alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />
4. Desmarque **Usar separador de 1000 (,).**
5. (Opcional) Defina o número de **Casas decimais**. O padrão é 2. O máximo permitido é 5.
6. Clique em **OK**.  
   As células estão formatadas corretamente.

<div id="verify-content-format" />

#### Verifique o formato do conteúdo

Para verificar o formato do conteúdo:

1. Use um editor para visualizar o arquivo.
   * Windows: Bloco de Notas, Bloco de Notas++
   * macOS: TextEdit
2. Preste atenção em:
   * **Espaços em branco:** certifique-se de que não há espaços em branco à esquerda ou à direita antes ou depois das vírgulas que separam os campos. No Excel, use o comando @trim para remover espaços em branco.
   * **Data:** Certifique-se de que as células de data tenham o formato AAAA-MM-DD.
   * Gastos: Certifique-se de que não haja vírgulas nas células de gastos.
   * **Delimitadores:** devem ser vírgulas. Se forem ponto e vírgula:
     * Isso ocorre quando as configurações regionais do seu computador estão definidas para um idioma/região que não é o inglês, mais especificamente o alemão.
     * A solução difere dependendo do sistema operacional do seu computador (macOS ou Windows).
     * Para resolver esse problema, procure as orientações mais recentes da <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> ou de outros fóruns. Use os seguintes termos de pesquisa: Operating system (macOS or Windows) Excel change delimiter for CSV files.

Veja a captura de tela abaixo com um [exemplo de arquivo CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv) exibido em um editor.

<Image alt="mceclip1.png" src="https://files.readme.io/1398c5e9bad7a46b697e3b21030e64d656162e33a4a63f39475c64993bbe7a72-360003996197.png" width="672px" />

</Accordion>

<div id="token-for-email-import" />

<Accordion title="Token para importação de e-mail">

O token para importação de e-mail é usado para verificar se o remetente do e-mail está autorizado a enviar o arquivo de Cost Import.

Os tokens do anunciante e da ad network são diferentes.

* Token do anunciante:
  * O mesmo token é usado para todos os aplicativos da conta
  * Qualquer usuário da conta pode obter o token.
* Token da ad network:
  * O mesmo token é usado para todos os anunciantes.

Anunciantes e ad networks não devem compartilhar seus tokens entre si!

</Accordion>

<div id="cost-import-permissions-for-ad-networks" />

<Accordion title="Permissões de Cost Import para ad networks">

As ad networks exigem a permissão do anunciante por aplicativo para acessar o Cost Import.

**Para conceder a permissão de Cost Import:**

1. Na AppsFlyer, o **anunciante** precisa acessar o menu lateral e selecionar **Colaborar** > **Integrações ativas.**   
   A página de Parceiros Integrados é exibida.
2. Escolha o parceiro integrado.
3. Acesse a aba de **Permissões**.
4. Ative **Permissões da ad network**, se ainda não o tiver feito.
5. (opcional) Adicione usuários da conta.
6. Ative **Usar Cost Import.**
7. Clique em**Salvar permissões**.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## Solução de problemas, características e limitações

<div id="error-messages-and-solutions" />

<Accordion title="Mensagens de erro e soluções">

A tabela abaixo lista todas as mensagens de erro possíveis do Cost Import e suas respectivas soluções.

| Mensagem de erro | Descrição | Solução |
| --- | --- | --- |
| Nenhum dos App IDs fornecidos no arquivo existe na AppsFlyer. Verifique a precisão dos App IDs. | O App ID não existe na conta. | Altere o App ID e reenvie. |
| A linha [nome da linha] possui o número errado de colunas. [Número] colunas esperadas, [número] colunas recebidas. | Todas as colunas do arquivo devem ter um valor. | Altere os valores preenchidos no arquivo com base nos headers definidos. |
| Falta 'media-source' no header do arquivo. | <ul><li>Falta o header do arquivo media-source.</li><li>O nome da coluna precisa ser exatamente como está no esquema.</li></ul> | Adicione media-source como nome do header. |
| O arquivo pode conter apenas um canal de mídia. Vários canais de mídia encontrados no arquivo: [número de canais de mídia]. | O arquivo contém mais de um canal de mídia. No CSV, linhas vazias ocultas ou linhas inválidas também podem acionar esse erro, mesmo que não estejam visíveis no Excel. | Abra o arquivo em um editor de texto, como o Notepad++, e remova quaisquer linhas vazias ou inválidas. Salve o arquivo e faça upload novamente. Se o arquivo contiver mais de um canal de mídia, crie um arquivo para cada canal de mídia. |
| O valor fornecido [valor] para [campo] não é um valor válido para esta coluna. | O formato dos dados na coluna está incorreto. Por exemplo, a data é dd-mm-aa em vez de aaaa-mm-dd. | Corrija o formato e reenvie. |
| Várias moedas identificadas para o aplicativo. Use uma moeda única para cada aplicativo no arquivo. Moedas encontradas: %número de moedas%. | Apenas uma moeda pode ser usada para um aplicativo. | Use uma moeda no upload e reenvie. |
| As seguintes colunas no header do arquivo não são compatíveis: [headers do arquivo] | O header do arquivo não corresponde ao esquema. Ou seja, o nome da coluna precisa ser exatamente como está no esquema. | Remova as colunas não suportadas e reenvie. |
| Colunas obrigatórias ausentes no cabeçalho do arquivo: [cabeçalhos de arquivo] | Falta uma coluna obrigatória no header do arquivo. | Adicione a coluna ausente e seus valores e reenvie. |
| O aplicativo contém uma data futura: [data] | Datas futuras não são permitidas. | Corrija a data para a data de hoje ou para uma data anterior e reenvie. |
| O arquivo está vazio. Não há dados para processar. | O arquivo está vazio. | Preencha os dados no arquivo e reenvie. |
| As duas linhas a seguir entram em conflito devido a dimensões idênticas. Forneça uma única linha de gastos por conjunto de dimensões. [linhas em conflito]. | Existe mais de uma linha com os mesmos campos-chave (obrigatórios). | Remova as linhas duplicadas e reenvie. |
| O arquivo pode conter dados somente de uma única conta de anunciante. Diferentes anunciantes encontrados no arquivo: [nomes dos anunciantes] | O upload de um parceiro não pode ser feito para mais de um anunciante. | Faça o upload de um arquivo por anunciante. |
| O aplicativo [app ID] não existe na conta. Verifique o App ID. | O App ID não existe. | Corrija o App ID e reenvie. |
| O código de geolocalização (país) não foi encontrado para o aplicativo [app ID]. Use um código ISO 3166 de 2 letras | Geolocalização não existe. | Corrija a geolocalização e reenvie. |
| O código da moeda não foi encontrado para o aplicativo [app ID]. Use um código ISO 4217 de 3 letras. | A moeda não existe | Altere a moeda para uma moeda válida e reenvie. |
| Ocorreram erros de validação para um ou mais aplicativos no arquivo. Revise as informações do arquivo para obter mais detalhes. | Há mais de um erro no arquivo. | Baixe o arquivo e verifique se há erros. |
| Ocorreu um erro interno ao processar o arquivo. Tente carregá-lo novamente. | <ul><li>Problema de backend ao processar o arquivo.</li><li>Normalmente, esse é um problema temporário.</li></ul> | Aguarde 1 hora e faça o upload novamente. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e Limitações">

| Caraterística | Observações |
| --- | --- |
| Redes de anúncios | Suportado.<br /><br />Exceções:<ul><li>Meta Ads</li><li>AppsFlyer</li><li>ASA</li></ul> |
| Agências | <ul><li>As agências não podem fazer upload de dados. Elas podem preparar seus arquivos e enviá-los ao anunciante para upload.</li><li>Para isso, os arquivos CSV devem conter uma coluna Agência com o nome da agência (que é o valor do parâmetro af\_prt). [Ver esquema CSV](/docs/import-cost-data#esquema-csv)</li></ul> |
| Transparência das agências | Não suportado |
| Fuso horário específico da aplicação | Com suporte. |
| Moeda específica da aplicação | Suportado. Disponível Os custos da campanha são convertidos para a moeda específica do aplicativo. |
| Nome da campanha | O mesmo nome de campanha não pode ser usado para vários aplicativos, ou o custo de um aplicativo será aplicado a ambos. |
| Nomes dos campos | Se os nomes dos campos na hierarquia da campanha não corresponderem aos nomes dos campos conforme aparecem nos dados de atribuição, eles serão contados separadamente. <br /><br />Por exemplo, se os nomes das campanhas não corresponderem, mesmo que os IDs das campanhas sejam iguais, eles serão contados como campanhas diferentes. |
| Tamanho do arquivo | Ao enviar um arquivo CSV de Cost Import, o limite de tamanho é:<ul><li>Através do dashboard da AppsFlyer: (2 MB)</li><li>Por e-mail: 5 MB por arquivo</li></ul> |
| Dados orgânicos | Com suporte. |
| Dados não orgânicos | Com suporte. |
| Atualização dos dados | <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">gasto com anúncios</Anchor> |
| Dados históricos | Suportado. Disponível Os custos reportados podem ser revertidos e os dados corrigidos podem ser enviados em até 90 dias. |
| Redirecionamento | Não compatível |
| Acesso do usuário à conta | Indisponível para usuários com restrições de geolocalização ou canal de mídia. |

</Accordion>

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Parâmetros e estrutura do link de atribuição</Anchor>
> * Linhas combinadas

<div data-zendesk-anchors="ad-spend-import=vis%C3%A3o-geral 01H7VYHJ2BN3EFDC4J3YN3P4WM=vis%C3%A3o-geral procedures=procedimentos h_01HYZBZMNTM0244V4PN6AJ45KR=procedimentos h_01HYZD52VRTMGJ0BFBFJNGQ50E=prepare-csv-file-with-cost-data ad-spend-csv-schema=esquema-csv 01H7VYHJ2CWF2HWHCTZDEZHT29=esquema-csv csv-format-and-rules=formato-e-regras-csv h_01HYZEDYKCAPTK1WD6VGWTA6PQ=formato-e-regras-csv h_01HYZD52VRWK7D6Q0YBW9SEFK6=upload-file h_01HYZKN3YEPFG8525GFQD0PC5K=email-file dashboard=painel h_01HZ4NVKPVHV1KT12V59MZBGPZ=painel h_01HZ1SXQQ2CHG77KX96D74J6TQ=cost-import-dashboard h_01HZ4NVKPVSM5ZTG76HJF3GW4J=matched-rows additional-information=informa%C3%A7%C3%B5es-adicionais h_01HYZFNKFEQW13F0BWAG3FZF69=informa%C3%A7%C3%B5es-adicionais h_01HYZFNKFE3AVH1GNGDT511M5B=using-excel-or-google-sheets-to-prepare-csv-file formatting-date-cells-in-excel=formatar-c%C3%A9lulas-de-data 01H7VYHJ2DSWC2J1NY04Q9Q620=formatar-c%C3%A9lulas-de-data formatting-spend-cells-in-excel=formatando-c%C3%A9lulas-de-gastos 01H7VYHJ2DA9JM4Q33V2TF7BD3=formatando-c%C3%A9lulas-de-gastos verify-content-format=verifique-o-formato-do-conte%C3%BAdo h_01HYZJJVC463C141AQ3VY5Z0TQ=verifique-o-formato-do-conte%C3%BAdo h_01HYZFNKFEXK4CYRBZ3ABRCWNJ=token-for-email-import h_01HZ1XV6ZX5FAN9JJPQM9RYD3Z=cost-import-permissions-for-ad-networks troubleshooting-traits-and-limitations=solu%C3%A7%C3%A3o-de-problemas-caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HZ4PBGAG9R9JMHPXVQC1GX3V=solu%C3%A7%C3%A3o-de-problemas-caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HZ2859J5P6MFKACKBK46J6GP=error-messages-and-solutions h_01HZ27W0409NF4Y6RNT8WPW8HP=traits-and-limitations h_01KZ8QYNGH1Q6QXQDC14QG96FZ=consulte-tamb%C3%A9m" />

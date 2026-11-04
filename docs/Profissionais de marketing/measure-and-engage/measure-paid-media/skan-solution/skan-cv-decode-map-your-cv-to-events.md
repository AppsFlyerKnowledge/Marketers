---
title: Descodificação de CV SKAN (mapear o seu CV para eventos)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-26T20:31:40Z'
  edited_at: '2026-08-18T00:32:27Z'
  id: 360014696297
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/360014696297
---
> **Visão geral:** A AppsFlyer descodifica e transforma o valor de conversão definido por você em eventos. Os eventos são usados para preencher o painel do SKAN, os dados brutos e os postbacks para os parceiros.

![SKAdNetwork_-_Custom__1_.png](https://files.readme.io/74f0d3836ee6a73f6746afa2d6d6a468c09cba696561c5a2075149ca360b78bf-34255690318097.png)

<div id="decode-skan-conversion-value" />

## Descodificar o valor de conversão SKAN

Os anunciantes utilizam a descodificação do valor de conversão como uma alternativa à utilização das opções disponíveis no <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">Conversion Studio</Anchor>. Se você usa Decodificação, significa que você é responsável por definir <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/4097267-updatepostbackconversionvalue">updatePostbackConversionValue</Anchor> de acordo com a lógica do seu aplicativo.

Além da definição do valor de conversão (CV) no aplicativo, as restantes opções de fluxo, funcionalidades e relatórios são as mesmas que as descritas no <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">guia de soluções SKAN</Anchor>. Isto significa que, ao expirar a janela de atividade (controlada por você), o iOS envia o postback para a ad network, que o reencaminha para a AppsFlyer. A AppsFlyer descodifica o CV de acordo com o seu mapeamento em eventos processados tal como os CVs descodificados definidos pelo SDK.

<div id="custom-conversion-valuedecode" />

## Valor de conversão personalizado-Decodificação

A implementação da decodificação de CV personalizada requer o carregamento de um arquivo CSV contendo o seu mapeamento de CV para a plataforma AppsFlyer.

**Descodificar os princípios de mapeamento**

* Forneça mapeamento de decodificação para valores de conversão precisa (1-63) e valores de conversão bruta (baixa, média e alta) para as janelas 1-3. Não é obrigatório mapear toda a gama de valores. Por exemplo, é possível mapear os valores 1, 2, 10 e 43.
* CV 0 é sempre mapeado para instalar. Não é possível defini-lo.
* A tabela de mapeamento é carregada para a AppsFlyer em um arquivo CSV. Você pode carregar uma tabela de mapeamento atualizada, se necessário.
* Ao receber um postback do iOS, o CV é decodificado em eventos, tal como ilustrado nos exemplos.
* O tempo de instalação é derivado usando o tempo de chegada do postback.
* Os eventos têm a mesma hora que a hora de instalação.
* Para compreender melhor como preparar o esquema, confira os cenários de mapeamento a seguir:
* Nomes de <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">eventos in-app personalizados</Anchor> são permitidos.
  * O que significa que você envia novos nomes de eventos, mesmo que eles nunca tenham sido enviados pelo SDK.
  * Você pode mapear os eventos in-app para eventos in-app da ad network.
  * O mesmo se aplica à integração do Meta Ads, sujeita às regras específicas do Meta Ads descritas na seção seguinte.

<div id="decode-mapping-scenario-rules" />

<Accordion title="Decodificar as regras do cenário de mapeamento">

Considere o seguinte:

* Gama de valores de conversão precisa: 1-63
* Intervalo de valores de conversão bruta: Baixa, média e alta
* Um determinado valor de conversão é mapeado para um ou mais eventos in-app especificados por você. Os eventos in-app têm parâmetros opcionais.
* Para os exemplos: Suponha que a data de instalação é 1 de fevereiro às 08:00.
* A tabela que se segue é um exemplo de tabela de mapeamento de descodificação. A sua estrutura é semelhante à do arquivo CSV necessário. Depois da tabela estão os eventos gerados como resultado do processo de decodificação.
* É sempre gerado um evento de instalação, independentemente do seu mapeamento.
* Medição de receita:
  * As receitas são em USD.
  * Um determinado valor de conversão tem um intervalo de receita delimitado por min\_revenue e max\_revenue.
  * Nos relatórios e painéis agregados, a receita é calculada como a média do intervalo. Exemplo: min\_revenue=4 e max\_revenue=10. A receita calculada é de 7.
  * Os relatórios de dados brutos incluem a receita calculada (skad\_revenue), min\_revenue e max\_revenue.

<div id="meta-specific-rules" />

#### **Regras meta-específicas**

Se você fizer a integração com Meta Ads, respeite as seguintes regras:

* Os valores mínimo e máximo de receita para um determinado valor de conversão devem ser diferentes. Ou seja eles não são iguais.
* Os valores não se devem sobrepor e devem estar por ordem consecutiva, como ilustrado para conversion\_value 1-2 e 62 no quadro seguinte.
* event\_counter: O Meta Ads não considera este valor. [Melhor prática] Preencha-o com um valor de 1.

<div id="example-decode-mapping" />

### Exemplo: Mapeamento de descodificação

| conversão\_  <br />value | nome do  <br />evento | valor do  <br />evento | min\_revenue<br /><br />(não -inclusivo) | max\_revenue (inclusivo) | contador de  <br />evento | horas desde a  <br />instalação |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | af\_compra | `{abc}` | 0 | 3 | 1 | 24 |
| 2 | af\_compra | `{def}` | 3 | 10 | 3 | 36 |
| 21 | evento\_a |  |  |  | 1 | 24 |
| 21 | evento\_b |  |  |  | 3 | 24 |
| 21 | evento\_c | `{xyz}` |  |  | 2 | 24 |
| 21 | evento\_d |  |  |  | 1 | 24 |
| 21 | evento\_e |  |  |  | 1 | 24 |
| 21 | evento\_f |  |  |  | 1 | 24 |
| 21 | evento\_g |  |  |  | 1 | 24 |
| 62 | af\_compra | \{fgh) | 10 | 17 | 2 | 72 |
| 62 | evento\_a | `{klm}` |  |  | 3 | 72 |

<div id="example-a-fine-conversion-value-1" />

### Exemplo A: Valor de conversão preciso 1

| nome\_do\_evento | skad\_receita | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| instalação |  |  |  |  |
| af\_compra | 1.5 | 0 | 3 | `{abc}` |

<div id="example-b-fine-conversion-value-2" />

### Exemplo B: Valor de conversão preciso 2

| nome\_do\_evento | skad\_receita | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| instalação |  |  |  |  |
| af\_compra | 6.5 | 3 | 10 | `{def}` |
| af\_compra | 6.5 | 3 | 10 | `{def}` |
| af\_compra | 6.5 | 3 | 10 | `{def}` |

<div id="example-c-fine-conversion-value-21" />

### Exemplo C: Valor de conversão preciso 21

| nome\_do\_evento | skad\_receita | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| instalação |  |  |  |  |
| evento\_a |  |  |  |  |
| evento\_b |  |  |  |  |
| evento\_b |  |  |  |  |
| evento\_b |  |  |  |  |
| evento\_c |  |  |  | `{xyz}` |
| evento\_c |  |  |  | `{xyz}` |
| evento\_d |  |  |  |  |
| evento\_e |  |  |  |  |
| evento\_f |  |  |  |  |
| evento\_g |  |  |  |  |

<div id="example-d-fine-conversion-value-62" />

### Exemplo D: Valor de conversão preciso 62

| nome\_do\_evento | skad\_receita | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| instalação |  |  |  |  |
| af\_compra | 13.5 | 10 | 17 | `{fgh}` |
| af\_compra | 13.5 | 10 | 17 | `{fgh}` |
| evento\_a |  |  |  | `{klm}` |
| evento\_a |  |  |  | `{klm}` |
| evento\_a |  |  |  | `{klm}` |

</Accordion>

<div id="ssot-support-for-decode-mode" />

<Accordion title="Suporte a SSOT para o modo Decode">

<div id="overview" />

#### Informações

Agora, clientes do modo Decode podem acessar a atribuição do SSOT (Single Source of Truth), trazendo benefícios de desduplicação que antes estavam disponíveis apenas para usuários do modo Encode. Isso melhora a mensuração da performance não orgânica sem exigir a implementação do modo encode.

<div id="key-benefits" />

#### Principais benefícios

* Recupere, em tempo real, por meio de uma API, uma indicação sobre se uma instalação é atribuída (não orgânica) ou não (orgânica) pela AppsFlyer.
* Reflita o sinal de atribuição do SSOT ao atualizar os valores de conversão.
* Use esquemas de decode compatíveis com SSOT fazendo upload de arquivos de esquema atualizados com um sinalizador especial do SSOT.
* Acesse os dashboards do SSOT e os relatórios do DataLocker.
* Desduplique instalações não orgânicas entre networks.
* Habilite atribuição e relatórios mais precisos.
* Reduza a complexidade de desenvolvimento e QA.

<div id="how-to-enable-ssot-for-decode-mode" />

#### Como ativar o SSOT para o modo Decode

1. **Extraia o ID da AppsFlyer -** <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id">Recupere o ID da AppsFlyer do SDK no momento da instalação</Anchor>.
2. **Consulte a API do SSOT -** Use o ID da AppsFlyer e o ID do aplicativo para verificar se a instalação foi atribuída pela AppsFlyer.
   * A API retorna:  
     `"is-non-organic-install": true/false`
3. **Aplique o sinal de atribuição -** Use esse sinal para ajustar sua lógica de CV. Por exemplo, reflita a atribuição adicionando um evento `af_attribution_flag` às entradas de CV relevantes.
4. **Envie o arquivo de esquema atualizado -** [Use seu esquema de decode existente](/docs/skan-cv-decode-map-your-cv-to-events#decode-mapping-scenario-rules). Para CVs afetados pela atribuição SSOT, adicione o evento `af_attribution_flag` para indicar a desduplicação.
5. **Acesse os relatórios**  
   Os dashboards do SSOT e os arquivos do DataLocker agora incluem dados do modo decode.

<div id="faq" />

#### Perguntas frequentes

**P: Quando devo consultar a API para obter o sinalizador de atribuição do SSOT?**  
**R:**

* Consulte a API imediatamente após a instalação.
* Consulte novamente a cada 10 segundos (até 5 vezes) para considerar o atraso na atribuição.
* Como alternativa, consulte uma vez pelo menos 25 segundos após a instalação para garantir a precisão.

</Accordion>

<div id="zd-decode-csv-file-specification" />

<div id="decode-csv-file-specification" />

<Accordion title="Decodificar a especificação do arquivo csv">

Os valores de conversão são mapeados para um ou mais eventos in-app.

**Regras do arquivo**

* Formato: Arquivo CSV
* Número máximo de linhas: 640 + linha de cabeçalho; total 641.
* A linha de cabeçalho  deve incluir todos os nomes das colunas exatamente como são apresentados aqui. Prática recomendada: Use o arquivo de exemplo em anexo como template. Ver exemplos de ficheiros CSV de decodificação para <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=0&single=true&output=csv">SKAN 3</Anchor> e <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=1187444449&single=true&output=csv">SKAN 4</Anchor>.
* Não use os seguintes caracteres como o primeiro carácter de uma coluna: `=`, `+`,`-`, e `@` (editado).

### Decodificar a especificação do arquivo csv

| Coluna | Valor obrigatório | Conteúdo | Atenção |
| --- | --- | --- | --- |
| valor\_de\_conversão | Sim, para:<ul><li>SKAN 3 e abaixo</li><li>SKAN 4 em que postback\_sequence\_index é 0</li></ul> | Valor inteiro 1-63 | O mesmo valor de conversão preciso pode ser listado mais de uma vez. Confira os exemplos para mais explicações. |
| coarse\_conversion\_value | Relevante apenas para o SKAN 4 | Sequência de caracteres:<ul><li>baixo</li><li>médio</li><li>elevado</li></ul> | O mesmo valor de conversão bruto pode ser listado mais de uma vez. |
| nome\_do\_evento | Sim | Sequência de caracteres | Evento in-app: Não tem que ser um evento que já existe na AppsFlyer.<br /><br />Atenção! Os nomes dos eventos in-app diferenciam entre maiúsculas e minúsculas.<br /><br />[Prática recomendada]: Nome do evento para a receita af\_skad\_revenue. |
| event\_value | Não | Sequência de caracteres | String definido pelo desenvolvedor que contém dados a decodificar pelo anunciante nos seus sistemas. Normalmente, ele tem o formato de um JSON. |
| min\_revenue | Não | Inteiro ou flutuante | Use os valores min\_revenue e max\_revenue para definir um intervalo de receitas em USD.<ul><li>Se você não pretende associar a receita a um valor de conversão, deixe min\_revenue e max\_revenue em branco.</li><li>O valor definido em min\_revenue não é inclusivo. Significa maior que 0. Semelhante a 0,0001</li><li>O valor definido em max\_value é inclusivo.</li><li>Exemplo: Se min\_revenue for 0 e max\_revenue for 4, isso significa que o intervalo é de 0,0001-4</li><li>max\_revenue deve ser superior a min\_revenue</li></ul>**Atenção!** Se você gerar o arquivo usando Excel, antes de guardar, altere o formato da coluna para vírgula e não para moeda para evitar que o Excel incorpore um símbolo $ no arquivo CSV. |
| max\_revenue | Não |  | Se você preencher min\_revenue: max\_revenue deve ter um valor superior a 0.<br /><br />Confira min\_revenue para a explicação. |
| event\_revenue\_usd | Não |  | Descontinuado a partir de 7 de julho de 2021. Use min\_revenue e max\_revenue |
| contador\_de\_evento | Sim | Inteiro | <ul><li>Número de vezes em que o evento é duplicado na descodificação. Normalmente, isso representa o número de vezes em que o usuário executou uma determinada ação.</li><li>Valor mínimo 1.</li></ul>Exemplo: Se o usuário realizou um determinado evento 5 vezes, são gerados 5 eventos.<br /><br />Considerações: Se você enviar receitas, o valor total em USD comunicado é multiplicado pelo valor em event\_counter. Ou seja, se min\_revenue = 0, max\_revenue = 3 e event\_counter = 4, a receita total registrada é 1,5 X 4 = 6.<br /><br />Confira os exemplos. |
| horas\_desde\_a\_instalação | Sim | Inteiro | <ul><li>Horas decorridas desde a instalação</li><li>Valor mínimo: 1</li><li>Valor máximo: 1512 (63 dias)</li><li>O valor de todas as linhas de um determinado conversion\_value tem que ser idêntico. Ou seja, valores diferentes para valores de conversão diferentes são permitidos.</li></ul>A AppsFlyer usa isso para derivar e definir a data de instalação da seguinte forma:<ul><li>Se os postbacks forem SKAN V4, a fórmula da data de instalação é: Data de instalação = hora de chegada do postback - [duração acumulada da janela] - [atraso médio do postback].<ul><li>Postback 1: data de instalação = hora de chegada do postback - 48h - 36h</li></ul></li><li>Se os postbacks forem SKAN V3, a fórmula da data de instalação é: Data de instalação = hora de chegada do postback - 36 horas - [intervalo médio do último ativo].<ul><li>O padrão [faixa média da última atividade] é de 12 horas.</li><li>Para um valor de conversão de 0, o último intervalo ativo médio é definido como 0.</li></ul></li></ul> |
| índice\_de\_sequência\_de\_postback | Sim, mas apenas relevante para o SKAN 4 | Inteiro<ul><li>0</li><li>1</li><li>2</li></ul> | Para o valor preciso, só pode ser recebido o valor 0. |

</Accordion>

<div id="upload-conversion-value-schema-file" />

<Accordion title="Carregar arquivo de esquema de valores de conversão">

**Antes de começar**:

* Prepare o arquivo CSV do esquema de valores de conversão.
* Se você integrar o Meta Ads e medir as receitas, verifique se o seu esquema está em conformidade com as [regras relativas ao Meta.](/docs/skan-cv-decode-map-your-cv-to-events#regras-meta-específicas) Se não o fizer, os Meta Ads não conseguem interpretar o esquema.

**Para ativar a mensuração do SKAN usando a mensuração por decodificação:**

1. Na AppsFlyer, acesse **configurações** > **SKAN Conversion Studio**.
2. Clique em opções(⋮), selecione **Carregar arquivo de mapeamento de decodificação.**
3. Se ainda não fez upgrade para o SKAN 4, escolha carregar um arquivo para o SKAN 4 ou pré SKAN 4. Depois de fazer upgrade para o SKAN 4, a escolha de outras versões fica indisponível.
4. Siga um dos procedimentos abaixo:
   * **Clique em Arrastar e largar arquivo.**
   * **Carregar arquivo de mapeamento atualizado**
5. Siga as instruções na interface do usuário para carregar o arquivo.
6. Ative **Mensuração do SKAN.**
7. Clique em **Salvar alterações**.   
   Observação: Durante as seguintes 48-72 horas, os dados no painel ficam ambíguos. Ou seja, devido a problemas com o temporizador do iOS, não podemos ter a certeza se o mapeamento de descodificação corresponde ao mapeamento de codificação usado por você.
8. Certifique-se de que você mapeou os seus eventos in-app para os usados pelos parceiros, de modo que esses possam consumir corretamente os postbacks.

</Accordion>

<div id="troubleshooting-the-csv-upload-errors-file" />

## Resolução de problemas no upload de arquivo CSV

<div id="upload-error-messages" />

<Accordion title="Mensagens de erro de upload">

Um ou mais valores no arquivo não correspondem ao formato exigido: O formato do arquivo foi alterado a partir de 7 de junho de 2021. Verifique se o formato do arquivo corresponde ao exemplo deste artigo.

</Accordion>

<div id="using-excel-to-format-the-event_revenue_usd-column" />

<Accordion title="Usar o Excel para formatar a coluna event_revenue_usd">

Ao usar o Excel/Planilhas Google para criar um arquivo CSV, as colunas event\_revenue\_usd precisam ser formatadas corretamente antes de salvar o arquivo como um arquivo CSV.

Após salvar o arquivo CSV, verifique se o conteúdo está formatado corretamente. **Observação**: Não use o Excel para fazer a verificação, use um [editor](/docs/skan-cv-decode-map-your-cv-to-events#visual-inspection-of-the-csv-file-without-excel).

<div id="formatting-event_revenue_usd-cells-in-excel" />

#### Formatação de células event\_revenue\_usd no Excel

O Excel geralmente formata células de valor com vírgula para separar os milhares, conforme mostrado na figura. Este formato não é adequado para carregar arquivos CSV. Também é necessário remover o símbolo $.

![mceclip0.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

Você pode corrigir isso formatando as células no Excel.

**Para formatar os valores de gastos sem uma vírgula 1000 ou o símbolo $:**

1. Selecione as células a serem formatadas.
2. Clique com o botão direito e selecione **Formatar células**.  
   A janela formatar células é aberta.
3. Selecione **Número**.  

   <Image alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />

1. Desmarque **Usar separador de 1000 (,).** Etapa 1:
2. (Opcional) Defina o número de **Casas decimais**. O padrão é 2. O máximo permitido é 5.
3. Clique em **OK**.  
   As células estão formatadas corretamente.

</Accordion>

<div id="visual-inspection-of-the-csv-file-without-excel" />

<Accordion title="Inspeção visual do arquivo CSV sem Excel">

Para examinar o conteúdo do arquivo CSV, use um editor para visualizar o arquivo.

* Windows: Bloco de Notas, Bloco de Notas++
* macOS: TextEdit

Veja a captura de tela abaixo com um <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?output=csv">exemplo de arquivo CSV</Anchor> exibido em um editor.

**Visualização do editor**

![SKCustomeEditor.png](https://files.readme.io/d8677e9967a70db32e8d04c4ee835bd477b18c1cb464a9cd0e593f72ce3f3c15-34255690323217.png)

Usando um editor, examine o arquivo CSV. Preste atenção em:

* **Espaços em branco:** certifique-se de que não há espaços em branco à esquerda ou à direita antes ou depois das vírgulas que separam os campos. No Excel, use o comando @trim para remover espaços em branco.
* **event\_revenue\_usd:** Certifique-se de que não há vírgula nem o símbolo $ na coluna event\_revenue\_usd.  

  ![mceclip1.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

</Accordion>

<div id="csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

<Accordion title="Arquivos CSV gerados pelo Excel não possuem vírgulas como delimitadores">

Se o Excel criar um arquivo CSV com ponto e vírgula ";" ou outro caracteres como delimitador, mas não como vírgula:

* Isso ocorre quando as configurações regionais do seu computador estão definidas para um idioma/região que não é o inglês.
* Esse problema é particularmente prevalente quando o alemão é selecionado nos contextos regionais.
* A solução difere dependendo do sistema operacional do seu computador (macOS ou Windows).
* Para resolver esse problema, procure as orientações mais recentes da <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> ou de outros fóruns. Use os seguintes termos de pesquisa: *Operating system (macOS or Windows) Excel change delimiter for CSV files.*

</Accordion>

<div data-zendesk-anchors="decode-skan-conversion-value=descodificar-o-valor-de-convers%C3%A3o-skan h_01HAMKKCKJEGCDPN5P8J6X0E8E=descodificar-o-valor-de-convers%C3%A3o-skan custom-conversion-value%E2%80%94decode=valor-de-convers%C3%A3o-personalizado-decodifica%C3%A7%C3%A3o h_01HAMKKCKJ5K6J6NNPF394ZK61=valor-de-convers%C3%A3o-personalizado-decodifica%C3%A7%C3%A3o h_01HAMKKCKJT7MA03SHT4X3MH4W=decode-mapping-scenario-rules facebookspecific-rules=regras-meta-espec%C3%ADficas h_01HAMKKCKJDCEKCNZFSF0V6KH8=regras-meta-espec%C3%ADficas example-decode-mapping=exemplo-mapeamento-de-descodifica%C3%A7%C3%A3o h_01HAMKKCKJ5B7W8FGK01QCKN7Y=exemplo-mapeamento-de-descodifica%C3%A7%C3%A3o example-b-conversion-value-1=exemplo-a-valor-de-convers%C3%A3o-preciso-1 h_01HAMKKCKJ1ZRH00A7Q4HZ4BBK=exemplo-a-valor-de-convers%C3%A3o-preciso-1 example-b-conversion-value-2=exemplo-b-valor-de-convers%C3%A3o-preciso-2 h_01HAMKKCKJZBASWWM1VD0VXWBX=exemplo-b-valor-de-convers%C3%A3o-preciso-2 example-c-conversion-value-21=exemplo-c-valor-de-convers%C3%A3o-preciso-21 h_01HAMKKCKJ4YHMQENKNVPMV4KC=exemplo-c-valor-de-convers%C3%A3o-preciso-21 example-d-conversion-value-62=exemplo-d-valor-de-convers%C3%A3o-preciso-62 h_01HAMKKCKJP7V7D26MGM1WVDTE=exemplo-d-valor-de-convers%C3%A3o-preciso-62 h_01JQX7MY9QRH71M4S6W9CKCQ5Z=ssot-support-for-decode-mode overview=informa%C3%A7%C3%B5es h_01JQX7NZD3KBYTBJMS2VEMK1MT=informa%C3%A7%C3%B5es key-benefits=principais-benef%C3%ADcios h_01JQX7PPSRCZXNTH890PP5TD1Q=principais-benef%C3%ADcios how-to-enable-ssot-for-decode-mode=como-ativar-o-ssot-para-o-modo-decode h_01JQX7QKV73WT10Q8QG0DKSB4S=como-ativar-o-ssot-para-o-modo-decode faq=perguntas-frequentes h_01JQX8JC023CMFSD1T6N60YHR8=perguntas-frequentes h_01HAMKKCKKJFRTXYJNWZNGF97V=decode-csv-file-specification decode-csv-file-specification::d6a1f3f1=decodificar-a-especifica%C3%A7%C3%A3o-do-arquivo-csv h_01HAMKKCKK7G7VP6SDEHBH6383=decodificar-a-especifica%C3%A7%C3%A3o-do-arquivo-csv h_01HAMKKCKKN7WDP6F5E4W91HQJ=upload-conversion-value-schema-file troubleshooting-the-csv-upload-errors-file=resolu%C3%A7%C3%A3o-de-problemas-no-upload-de-arquivo-csv h_01HAMKKCKK0QQ8AS8FZ83MZ8FH=resolu%C3%A7%C3%A3o-de-problemas-no-upload-de-arquivo-csv h_01HAMKKCKK3B2T9VSTYCVE0017=upload-error-messages h_01HAMKKCKKFJAE4B88QV00HYPW=using-excel-to-format-the-event_revenue_usd-column formatting-event_revenue_usd-cells-in-excel=formata%C3%A7%C3%A3o-de-c%C3%A9lulas-event_revenue_usd-no-excel h_01HAMKKCKKKVYCWCQCAEMSBMF7=formata%C3%A7%C3%A3o-de-c%C3%A9lulas-event_revenue_usd-no-excel h_01HAMKKCKK39C9SP7K86ER3HZK=visual-inspection-of-the-csv-file-without-excel h_01HAMKKCKK9GEBC64JE4DSDAMQ=csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

---
title: Execute ações em massa do OneLink via CSV
metadata:
  keywords:
    - Marketers
    - bulk
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2023-04-13T11:31:43Z'
  edited_at: '2026-08-19T00:33:40Z'
  id: 14511403892369
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/14511403892369
---
> **Visão geral:** a página de links em massa do OneLink permite gerar um grande número de links personalizados do OneLink instantaneamente e visualizá-los em um local para uso futuro.

Os links em massa permitem que você crie e exiba links criados em massa. Esses links em massa são agrupados em um formato de coleção conveniente, permitindo que você execute ações em toda a coleção, como adicionar novos links ou fazer downloa deles.

## Getting Started

1. Na AppsFlyer, vá para **Experiências e deep linking** > **Links em massa do OneLink**.
2. Você verá uma página de introdução com um dos seguintes botões:
   1. **Comece** - (envie para criar sua primeira coleção).
   2. **Criar um template do OneLink** - Um template do OneLink é necessário para criar uma coleção. Consulte <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">os templates do OneLink</Anchor>.
   3. **Upgrade** -  links em massa não estão disponíveis com seu pacote atual. Entre em contato com seu CSM ou escreva para [hello@appsflyer.com](mailto:hello@appsflyer.com) sobre como atualizar seu pacote.

## Criando sua primeira coleção

1. Clique em **Começar.**
2. Insira um nome para sua coleção.Escolha um nome que reflita o objetivo de sua coleção, para que você possa identificá-la facilmente mais tarde.
3. Selecione um template do Onelink. Observação: todos os links da coleção serão baseados neste modelo
4. Clique em **Salvar e continuar.**
5. Faça upload do seu arquivo CSV. Você pode usar o seguinte <Anchor target="_blank" href="https://cdn.appsflyer.com/onelink-bulk-links-mgmt/sample_file.csv">exemplo de CSV</Anchor> como guia.  
   Consulte [Formato de upload](/docs/perform-onelink-bulk-actions-via-csv#upload-format) para garantir que seu CSV seja compatível e carregado com sucesso. Depois que o arquivo CSV é carregado, ele é validado. Se houver linhas inválidas, um relatório de validade CSV estará disponível para download para ajudar a corrigir seu arquivo. Siga as instruções na IU e carregue um arquivo corrigido.
6. Clique em **Criar coleção.**

## Gerenciando seus links em massa com coleções

Links em massa são gerenciados em coleções.

* Na parte superior da página, o widget **Uso de link em massa neste mês** mostra o número de solicitações de links (que incluem criações e atualizações de links) fora da cota mensal do mês atual.
  * No momento, o limite padrão é de 20.000 criações de links por mês

* A seção **Coleções** permite que você crie uma nova coleção e execute outras ações em suas coleções de links atuais.
* Se houver mais de sete coleções, você poderá pesquisar e filtrar sua lista de coleções.
* Máximo de 2000 links por coleção

## Outras ações

A seguir estão as outras ações que podem ser executadas em uma coleção:

<div id="creating-a-new-collection" />

<Accordion title="Criando uma nova coleção">

A criação de uma nova coleção está disponível quando o [uso mensal](/docs/perform-onelink-bulk-actions-via-csv#collection-features) não foi excedido.

1. Clique em **Nova coleção**.
2. Siga as instruções.
   1. O processo segue as mesmas etapas de [Criar sua primeira coleção](/docs/perform-onelink-bulk-actions-via-csv#criando-sua-primeira-coleção).

</Accordion>

<div id="downloading-a-collection-of-links" />

<Accordion title="Fazendo download de uma coleção">

A opção de download de coleção está disponível quando:

* Existem links ativos nessa coleção.
* Você tem permissões de acesso de aplicativo para pelo menos um dos aplicativos móveis do template do OneLink relacionado à coleção.

Para fazer download de uma coleção:

1. Links em massa
2. Clique no ícone de download na linha da coleção.
3. Selecione o domínio para a saída de URL curto.
4. Clique em **Download**.

> 🚧 **Importante!**
>
> A AppsFlyer recomenda o uso de domínios de marca, pois eles podem melhorar o desempenho da campanha gerando confiança e promovendo o conhecimento da marca. <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain">Saiba mais aqui.</Anchor>

</Accordion>

<div id="downloading-a-collection-of-qr-codes" />

<Accordion title="Baixar uma coleção de códigos QR">

Você pode criar imagens de QR code para toda a coleção.

1. Links em massa
2. Na linha da coleção, clique no ícone de download de imagens de QR code <Image alt="generate qr.png" src="https://files.readme.io/23dbd4b2e3ed248e868ae7d5deee3cac383b0e018ae17204f9547f5707a428c9-21656949404561.png" width="22px" /> .
3. Na caixa de diálogo **Gerar imagens de QR code**, defina o seguinte:
   * **Domínio:** selecione o subdomínio ou o domínio de marca da URL que os usuários finais verão depois de escanear o QR code.
   * **Formato da imagem do QR code:** escolha PNG ou SVG como formato da imagem do QR code.
   * **Formato do nome do arquivo do QR code:** selecione o parâmetro cujos valores serão usados como prefixo dos nomes de arquivo da imagem do QR code. Certifique-se de que os valores desse parâmetro adicionem um contexto significativo aos nomes dos arquivos, ajudando você a identificar a finalidade de cada imagem de QR code.
4. Clique em **Generate.** Você pode monitorar o processo de geração do arquivo no painel **Download QR code images**.
5. Para baixar o arquivo ZIP, clique no ícone de download <Image alt="download-bulk.png" src="https://files.readme.io/8436aed2633bbed2f6cb65c00690711766c153c97042b5b157c199333e8723c2-21656949409041.png" width="18px" />.

> 📘 **Observação**
>
> * Após a geração bem-sucedida, o arquivo ficará acessível no painel por 24 horas e depois será excluído automaticamente.
> * O arquivo baixado é fornecido em formato ZIP porque o conteúdo consiste em vários arquivos de imagem de QR code. Se o navegador solicitar que você permita downloads de ZIP, forneça a confirmação necessária para continuar.
> * Você pode executar até 2 processos de geração de QR code simultaneamente.

</Accordion>

<div id="adding-links-to-a-collection" />

<Accordion title="Adicionando links a uma coleção">

A opção de adicionar links está disponível quando:

* Você tem permissões de acesso de aplicativo para pelo menos um dos aplicativos móveis do template do OneLink relacionado à coleção.
* Existem menos de 2.000 links ativos na coleção.
* [O uso mensal](/docs/perform-onelink-bulk-actions-via-csv#collection-features) não foi excedido.

Para adicionar links a uma coleção, clique em **opções de menu** > **Adicionar links à coleção.**

* Os links serão adicionados usando o mesmo método descrito em [Criando sua primeira coleção](/docs/perform-onelink-bulk-actions-via-csv#criando-sua-primeira-coleção) do ponto 5 em diante.

</Accordion>

<div id="editing-links-in-a-collection" />

<Accordion title="Editando links em uma coleção">

A opção de edição de links está disponível quando:

* Existem links ativos nessa coleção.
* Você tem permissões de acesso de aplicativo para pelo menos um dos aplicativos móveis do template do OneLink relacionado à coleção.
* [O uso mensal](/docs/perform-onelink-bulk-actions-via-csv#collection-features) não foi excedido.

**Para editar links em uma coleção:**

1. Clique em **opções de menu** > **Editar links**.
2. Baixe o CSV base da coleção. Este arquivo contém todos os links na coleção que você pode editar.
3. Siga as instruções na primeira etapa para editar os parâmetros do link. Para todos os links que você deseja atualizar, certifique-se de que **Marcar para atualização** esteja definido como **verdadeiro**.
4. Clique em **Avançar**.
5. Faça upload de seu CSV editado. Consulte o [formato de upload](/docs/perform-onelink-bulk-actions-via-csv#upload-format) para garantir que seu CSV seja compatível e carregado com sucesso.
   * Depois que o arquivo CSV é carregado, ele é validado.
   * Se houver linhas inválidas, um relatório de validade CSV estará disponível para download para ajudar a corrigir seu arquivo. Siga as instruções na IU e carregue um arquivo corrigido.
6. Clique em **Atualizar links**.

> 📘 **Observações**
>
> * Se você tiver feito download de imagens de QR code desta coleção de links, poderá atualizar os parâmetros do link e continuar usando as mesmas imagens, já que os próprios QR codes não mudam.
> * Atualizar links por edição em massa estenderá o tempo de vida (TTL) dos links em 365 dias.

</Accordion>

<div id="viewing-the-collection-history" />

<Accordion title="Visualizando o histórico da coleção">

Para visualizar o histórico de uma coleção, clique em **opções de menu** > **Exibir histórico de coleção.**

A janela do histórico mostrará as seguintes ações, assim como a data e hora em que a ação foi realizada e por quem:

* **Mudanças de nome:** As mudanças no nome da coleção.
* **Links adicionados:** quando os links foram adicionados à coleção.
* **Links atualizados**: quando os links da coleção foram editados e atualizados.
* **Coleção** **criada**: quando a coleção foi criada.
* **ZIP de QR codes baixado**: quando as imagens de QR code foram geradas e baixadas para a coleção.

**Os links adicionados e atualizados** também mostram como as alterações afetaram sua [quantidade de uso](/docs/perform-onelink-bulk-actions-via-csv#collection-features) e permitem que você faça download de um relatório de ação sobre essa alteração.

* Os relatórios de ação só podem ser baixados se você tiver permissões de acesso de aplicativo para pelo menos um dos aplicativos móveis do template do OneLink relacionado à coleção.

</Accordion>

<div id="editing-the-collection-name" />

<Accordion title="Editando o nome da coleção">

A opção de edição do nome da coleção está disponível quando:

* Você tem permissões de acesso de aplicativo para pelo menos um dos aplicativos móveis do template do OneLink relacionado à coleção.

Para editar um nome de coleção:

1. Passe o mouse sobre o nome da coleção que você deseja alterar.
2. Clique no ícone de edição ao lado do nome da coleção.
3. Depois de editar o nome, clique em Enter ou clique em outro lugar na tela.

</Accordion>

<div id="deleting-empty-collections" />

<Accordion title="Excluindo coleções vazias">

Se uma coleção estiver vazia e você tiver permissões de acesso de aplicativo para pelo menos um dos aplicativos móveis do template do OneLink relacionados à coleção, ela poderá ser excluída clicando em **opções de menu -> Excluir coleção**.

**Por quê**

1. As agências precisam adicionar manualmente o parâmetro `af_prt` aos seus links.
2. Se uma coleção estiver vazia e você tiver permissões de acesso de aplicativo para pelo menos um dos aplicativos móveis do template do OneLink relacionados à coleção, ela poderá ser excluída clicando em **opções de menu -> Excluir coleção**.

> 📘 **Observações importantes**
>
> * Certifique-se de que você deseja excluir a coleção. Excluir uma coleção com links ativos fará com que os links parem de funcionar, o que significa que os usuários que clicarem neles não serão atribuídos nem redirecionados corretamente. **Excluir uma coleção é irreversível.**
> * Se você quiser manter um registro dos links excluídos, poderá fazer download da coleção antes de excluí-la. **Para baixar como arquivo CSV:**
>   Clique em **Baixar a coleção** na mensagem de confirmação.

### Parâmetros CSV

**As coleções podem estar vazias devido a:**

* O <Anchor target="_blank" href="/marketers/pt/docs/bulletin-onelink-short-url-ttls-automatically-extend">TTL (time to live)</Anchor> de todos os links na coleção expirou.
* O novo processo de coleta foi interrompido ou não foi concluído antes da criação dos links.

Coleções vazias também podem ser excluídas da maneira descrita acima.

</Accordion>

## Informações gerais

> 📘 **Observação:**
>
> Os links em massa criados antes de abril de 2023 não serão exibidos ou gerenciados na página de links em massa.

<div id="upload-format" />

<Accordion title="Fazer upload de formato">

Para garantir que seu CSV seja carregado sem erros, certifique-se de que seu arquivo atenda aos seguintes padrões.

* O arquivo deve estar no formato CSV
* O arquivo não pode ser maior que 4 MB
* O arquivo deve conter apenas o conteúdo dos links que você está criando/atualizando
* Cada link deve estar em sua própria linha
* O ID do link personalizado é uma coluna exclusiva que permite ao usuário definir o ID da URL curta do link. O ID da URL curta não pode ser editado depois que o link é criado. Para saber mais sobre o ID da URL, consulte <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#url-id">aqui</Anchor>.
* Máximo de 35 colunas de parâmetros
* Somente a codificação de caracteres UTF-8 é aceita

</Accordion>

<div id="parameters-in-the-uploaded-csv" />

<Accordion title="Parâmetros no CSV carregado">

* Os parâmetros no CSV podem ser qualquer parâmetro aceitável em um link da AppsFlyer. Podem ser parâmetros reservados para atribuição (por exemplo: c, af\_channel, af\_adset, etc.), para redirecionamento e deep linking (por exemplo: af\_ios\_url, af\_dp, deep\_link\_value, etc.) ou parâmetros personalizados.
* O parâmetro fonte de mídia (pid) é obrigatório.
* Mesmo que um esquema de URI seja definido no template do OneLink, para links criados em massa, o parâmetro af\_dp com o esquema de URI deve ser especificado em seu arquivo CSV.

</Accordion>

## Perguntas frequentes

<div id="qr-with-long-links-vs-short-links---is-there-any-difference" />

<Accordion title="QR com links longos vs. curtos — há alguma diferença?">

Seu QR code funcionará com uma URL longa ou curta. No entanto, se você usar uma URL curta, poderá atualizar os parâmetros e o comportamento do link pelo dashboard do OneLink (na seção de gerenciamento de links) sem precisar substituir o QR code publicado, já que a própria URL curta permanece inalterada.

* **URLs curtas:** Se você alterar os parâmetros na configuração da URL curta, o QR code permanecerá o mesmo. Você não precisa publicá-lo novamente.
* **URLs longas (por exemplo, Smart Script):** Se você alterar os parâmetros em uma URL longa, o QR code também será alterado. Depois de publicá-lo, você não poderá atualizar o conteúdo da URL remotamente — será necessário gerar e distribuir um novo QR code.

</Accordion>

<div id="can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example" />

<Accordion title="É possível criar um QR code e mudar retroativamente o comportamento por trás dele, por exemplo, depois de imprimir o QR?">

Sim, é possível — se o QR code for baseado em uma URL curta do OneLink que você possa editar (por exemplo, criada pela interface do OneLink). Um **QR code é uma representação visual da URL por trás dele**.  Alterar a própria URL criará um novo QR code correspondente (por exemplo, o QR code de mike.onelink.me/123A/shorturl é diferente do QR code de mike.onelink.me/123A/example).

No entanto, como uma URL curta do OneLink é uma URL com hash, seus parâmetros e regras de redirecionamento são configurados no backend e não ficam visíveis na URL. Isso significa que você pode manter a mesma URL visível e o mesmo QR code enquanto edita a configuração no backend.

</Accordion>

<div id="what-options-are-available-for-generating-qr-codes-in-appsflyer" />

<Accordion title="Quais opções estão disponíveis para gerar QR codes na AppsFlyer?">

Você tem as seguintes opções:

* **Pelo dashboard da AppsFlyer → UI do OneLink:**
  * Gera automaticamente um QR code quando você cria um link
  * **Para configurar um QR code para conversões QR-to-app de desktop**:
  * Pode ser exportado como SVG ou PNG
  * Baseado em uma URL curta
* **Criação em massa de QR codes (pela página Bulk Links):**
  * **Para configurar um QR code para conversões QR-to-app de desktop**:
  * Pode ser exportado como SVG ou PNG
  * Oferece suporte à nomenclatura contextual de arquivos
  * Baseado em URLs curtas
* **Integração do Smart Script V2.1+**
  * Baseado em URLs longas geradas dinamicamente
  * Os QR codes são criados de acordo com isso
  * **Para configurar um QR code para conversões QR-to-app de desktop**:
  * Suporta a criação em massa de QR codes de URL

</Accordion>

<div id="can-you-bulk-create-qr-codes" />

<Accordion title="É possível criar QR codes em massa?">

sim, Você pode criar QR codes em massa usando o [recurso de criação em massa de QR code](/docs/perform-onelink-bulk-actions-via-csv) disponível na página Links em massa.

</Accordion>

<div data-zendesk-anchors="h_01HKWSS511PMGTVEJN82SF5NX5=getting-started creating-your-first-collection=criando-sua-primeira-cole%C3%A7%C3%A3o h_01HKWSS511SD4DFH7TMZV1EETH=criando-sua-primeira-cole%C3%A7%C3%A3o managing-your-bulk-links-with-collections=gerenciando-seus-links-em-massa-com-cole%C3%A7%C3%B5es h_01HKWSS511XMB3CZ563SBZTEAC=gerenciando-seus-links-em-massa-com-cole%C3%A7%C3%B5es other-actions=outras-a%C3%A7%C3%B5es h_01HKWSS5113EPY13J2KHMWGDS7=outras-a%C3%A7%C3%B5es h_01HKWSS511G8AREWDP05F6ZMER=creating-a-new-collection h_01HKWSS511DN9BSXFDNV053K63=downloading-a-collection-of-links h_01HKWSS511EDVWMAPHNGN711MG=importante h_01HKWSS511SQR18RGSSKGTERCV=downloading-a-collection-of-qr-codes h_01HKWSS5112CT9HV7K81QSHMGM=observa%C3%A7%C3%A3o h_01HKWSS51125ZBCRQ087159YFH=adding-links-to-a-collection h_01HKWSS511AWCA4QV2NKVTTNKA=editing-links-in-a-collection h_01HKWSS512QYQBY0ZRE317528Z=observa%C3%A7%C3%B5es h_01HKWSS512NZC3X8CPDDWB47JH=viewing-the-collection-history h_01HKWSS512RP5ATJWB38G88793=editing-the-collection-name h_01HKWSS512Q4MDFX75CK9VCREK=deleting-empty-collections h_01JQ69NF4SR7FT765JQP35B25G=observa%C3%A7%C3%B5es-importantes empty-collections=par%C3%A2metros-csv h_01JQ69A1511N1GQFMBA2S748JK=par%C3%A2metros-csv general-information=informa%C3%A7%C3%B5es-gerais h_01HKWSS512JYNT3386P1KPZ452=informa%C3%A7%C3%B5es-gerais h_01HKWSS5123XVFKBZ892YCTFAC=observa%C3%A7%C3%A3o-1 h_01HKWSS5126A9XVE645CHCJD7X=upload-format h_01HKWSS512P7ZB213PCZ7JQTYP=parameters-in-the-uploaded-csv faq=perguntas-frequentes h_01K42S97K7KSKFC6BYEHPT0GZ5=perguntas-frequentes qr-with-long-links-vs-short-links-%E2%80%93-is-there-any-difference=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVKGQZKAS1PZ3B9H20=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVTV0KP280D15JF7NB=can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example h_01K42Q4QQVV1RZZXZK2Y9W8R58=what-options-are-available-for-generating-qr-codes-in-appsflyer h_01K42Q4QQVZF4H8FYZCTJPR0RX=can-you-bulk-create-qr-codes" />

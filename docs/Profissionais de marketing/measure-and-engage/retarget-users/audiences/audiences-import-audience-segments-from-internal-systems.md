---
title: Audiences - importar segmentos de audiências de sistemas internos
metadata:
  keywords:
    - Developers
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-09-15T10:45:43Z'
  edited_at: '2026-10-06T00:18:04Z'
  id: 360013291857
  locale: pt
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/pt/articles/360013291857
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** você pode importar segmentos de audiências predefinidas de seus sistemas internos (como BI e CRM) para o Audiences, e usá-los como seu ponto central para conectar e manter todos esses segmentos com seus parceiros publicitários.

<div id="why-import-audiences" />

## Por que importar audiências?

Em certas situações, você pode ter segmentos de audiências predefinidos em seus sistemas internos. Ao importar essas audiências (como listas de device e/ou user IDs) para a AppsFlyer, você pode usar o Audiences como o ponto central para conectar e gerenciar todos os seus segmentos com seus parceiros publicitários. Além disso, você pode aproveitar os recursos do Audiences, tais como ID matching/enriquecimento de dados e métricas de campanha conectadas.

Considere os exemplos seguintes:

<div id="examples" />

> 📄 **Exemplos**
>
> **Remarketing promocional**
> Você quer enviar ofertas promocionais para os usuários no mês dos seus aniversários.
>
> Veja como fazer isso com o Audiences:
>
> 1. Use o seu CRM interno para criar uma lista de usuários com as suas datas de aniversário.
> 2. Divida a lista de acordo com o mês de aniversário e exporte-a como listas individuais de advertising IDs.
> 3. Importe as listas para a AppsFlyer como audiências e conecte-os aos parceiros para as campanhas promocionais que você pretende realizar.
> 4. Configure campanhas com os parceiros adequados para direcionar corretamente as audiências.
>
> **Aquisição de novos usuários**
> Vamos supor que o seu studio de desenvolvimento de aplicativos adquiriu um novo studio. Esse novo studio tem os device IDs de usuários que instalaram os apps desse studio no passado, e você quer segmentar esses usuários para que eles instalem seus apps atuais.
>
> Veja como fazer isso com o Audiences:
>
> 1. Obtenha a lista de device IDs do studio adquirido e importe-a para a AppsFlyer como uma audiência.
> 2. Conecte a audiência importada aos parceiros com os quais você pretende realizar campanhas.
> 3. Configure campanhas com os parceiros relevantes para alcançar esses usuários da melhor forma.

## Audiences import V2.0

Veja os conceitos e procedimentos relacionados com a nova funcionalidade de importação do Audiences V2.0, que inclui opções para importação por CSV e API.

<div id="imported-audience-types" />

## Tipos de audiências importadas

Quando importar uma audiência, você deverá definir o seu tipo, determinando como a AppsFlyer processa e envia a audiência para os parceiros. **Isso é feito na primeira importação de uma audiência e não pode ser alterado posteriormente.**

**Uma audiência importada padrão:**

* Passa por ID matching e enriquecimento de dados—um processo em que o Audiences combina os identificadores importados com os existentes na base de dados (para o mesmo usuário no mesmo app), enriquecendo os dados enviados aos parceiros.
* É enviado para parceiros conforme a política de identificadores de usuário da sua conta.
* Deve ser importado usando a funcionalidade de importação V2.0 descrita neste artigo.

**Uma audiência importada "como está":**

* Não passa por ID matching e enriquecimento de dados.
* É enviado para os parceiros sem seguir a política de identificadores de usuário da sua conta (ou seja, todos os identificadores importados são enviados para os parceiros).
* Pode ser importado usando a funcionalidade de importação V2.0 (descrita neste artigo).

<div id="important" />

> 🚧 **Importante!**
>
> * Todas as audiências existentes a partir de 23 de novembro de 2021, **são designadas como audiências "como estão" e não podem ser alteradas para audiências padrão.** Pode continuar a atualizar essas audiências conforme necessário, usando a funcionalidade de importação V2.0 (descrita neste artigo).
> * Você pode ter até 500 audiências importadas ativas de uma só vez.
> * Apenas um administrador pode designar uma nova audiência importada para como "como está".
> * Ao importar uma audiência que possui um CUID como identificador, a associação de CUID deve ter sido recebida pela AppsFlyer na instalação (e não apenas em eventos pós-instalação), garantindo a associação completa com os dispositivos relevantes e um enriquecimento eficaz com os identificadores de dispositivos (como GAID, IDFA, etc.). <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid#configuração-do-cuid">Saiba mais</Anchor>

<div id="audience-import-procedures" />

## Procedimentos para importação de audiências

Importe uma audiência fazendo o upload de um arquivo CSV ou usando a Import Audience API.

<div id="import-a-csv-file" />

<Accordion title="Importar um arquivo CSV">

Prepare um arquivo CSV com as seguintes especificações:

**Formato**

* Uma coluna para cada identificador de usuário a ser enviado
* Uma linha de header com o nome do identificador em cada coluna (tudo em letras minúsculas)
* Sem linhas em branco
* Número máximo de linhas: 1 milhão
* Se você preparar o arquivo no Excel, salve-o como um arquivo **CSV (delimitado por vírgula) (\*.csv)**, como mostrado na imagem a seguir:

<Image align="center" alt="CSV.jpg" src="https://files.readme.io/863505596fd525ff0750f05db70413e9aaee51beb208bd0fbc8ab718ad4e4576-32897281151633.jpg" width="339px" />

<div id="identifier-hash" />

#### hash do identificador

<div id="note" />

> 📘 **Importante!**
>
> Este formato CSV serve para importar segmentos de audiência. Se, em vez disso, você estiver importando dados de atributos de usuário, consulte <Anchor target="_blank" href="/marketers/pt/docs/audiences-create-better-audiences-with-user-attribute-data">Criar audiências melhores com dados de atributos de usuário</Anchor>, que usa um formato CSV diferente, sem linha de cabeçalho.

**Colunas e identificadores**

* Os dados são processados usando a linha de header para identificar os dados em cada coluna, portanto:
  * Não é necessário que as colunas apareçam em uma ordem específica.
  * Não é necessário incluir colunas para identificadores que não serão enviados.
  * Você pode importar quantos identificadores desejar em um único arquivo CSV, desde que cada linha inclua os identificadores obrigatórios, conforme detalhado abaixo.
* Identificadores disponíveis:
  * ativado
  * idfv
  * idfa
  * gaid
  * OAID
  * imei
  * cuid
  * e-mails
  * phone
  * phone\_e164
  * braze\_id
  * amplitude\_id  

    **Atenção:** Identificadores adicionais, como emails e phone, devem estar no formato sha256 criptografado ou deixados em branco.
* Identificadores obrigatórios:
  * Para audiências Android: **app\_id** + um dos seguintes: **gaid** OU **oaid** OU **imei** OU **cuid** OU **braze\_id** OU **amplitude\_id**
  * Para audiências iOS: **app\_id** + um dos seguintes: **idfv** OU **cuid**OU **braze\_id** OU **amplitude\_id**
* Em conformidade com o <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy#eu-digital-markets-act">Digital Markets Act (DMA)</Anchor> da Google: a partir de 6 de março de 2024, ao importar uma audiência "como está", será necessário adicionar duas colunas adicionais de consentimento da AppsFlyer. São elas:

| Colunas de consentimento da AppsFlyer | Campo do Google | Valores | Explicação do campo |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | personalização\_de\_anúncio | verdadeiro/falso | O usuário permitiu que o Google use seus dados para receber anúncios personalizados? |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | dados\_do\_utilizador\_anúncio | verdadeiro/falso | O usuário permitiu o compartilhamento de seus dados com o Google? |

Se os campos de consentimento não forem preenchidos com valores, serão enviados para a Google como "Não especificado" e provavelmente não serão incluídos na audiência do lado do Google. Preencher esses campos assegura a máxima inclusão de usuários do <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">Espaço Econômico Europeu (EEE)</Anchor> nas suas audiências do Google.

**Exemplos de arquivos CSV:**

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413851475729">new-import-android-example.csv</Anchor>  
<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413840980497">new-import-ios-example.csv</Anchor>

<span id="01ECF4ZD0RB90HZC6ZFNTKMDSG"></span>**Para criar e importar uma nova audiência usando um arquivo CSV:**

1. No dashboard esquerdo da AppsFlyer, vá até **Engajar** > **Audiences**.
2. Clique em **Nova audiência**.
3. Escolha **Importar audiência**.  
   A janela **Importar audiência** será aberta.
4. Insira um **Nome de audiência** exclusivo.  
   **Nota:** Os nomes das audiências não podem incluir caracteres especiais (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
5. Selecione a plataforma: **Android** ou **iOS**.
6. Indique se essa audiência é [**padrão** ou **como está**](/docs/audiences-import-audience-segments-from-internal-systems#tipos-de-audiências-importadas) .
7. Para uma audiência padrão, mantenha a caixa desmarcada.
8. Para uma audiência no estado atual, marque a caixa. (**Atenção:** disponível apenas para administradores.)
9. Clique em **Próximo**.  
   **A aba Conectar é exibida.**
10. Em **Importar usando CSV**, mantenha a opção padrão de **Adicionar novos dispositivos/usuários** (já que se trata de uma nova audiência).
11. Escolha o arquivo CSV para upload.  
    Aguarde a mensagem de confirmação **Upload feito com sucesso.**
12. Clique em **Próximo**.  
    **A aba Conectar é exibida.**
13. **(Opcional)** Siga as instruções para <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#connect-an-audience-to-media-partners">conectar uma audiência a parceiros</Anchor>.
14. Clique em **Concluir**.

A sua audiência já aparece no dashboard do Audiences, e já foi importada e conectada aos seus parceiros. É importante observar, no entanto, que a lista de audiências importada ainda não está disponível para upload para os parceiros, pois as audiências importadas são processadas com uma <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#eod">atualização de dados diária</Anchor>.

**Para atualizar uma audiência existente usando um arquivo CSV:**

1. No dashboard esquerdo da AppsFlyer, vá até **Engajar** > **Audiences**.
2. Clique no nome da audiência que você deseja atualizar.  
   A tela **Editar audiência** aparece, com a aba **Definir**.
3. Se você deseja alterar o nome da audiência, você pode fazer isso agora. Caso contrário, selecione a aba **Importar** para enviar o novo arquivo CSV.
4. Em**Importar usando CSV**, escolha a o que fazer com a lista enviada:
5. **Adicionar novos dispositivos/usuários:** Adicione identificadores de dispositivos/usuários à audiência existente.
6. **Remover dispositivos/usuários:** Remova os identificadores de dispositivos/usuários da lista.
7. **Substituir a audiência existente por novos dispositivos/usuários:** Substitua a audiência pela lista carregada.
8. Escolha o arquivo CSV para upload.  
   Aguarde a mensagem de confirmação **Upload feito com sucesso.**
9. Clique em **Próximo**.  
   **A aba Conectar é exibida.**
10. Faça alterações nas <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#connect-an-audience-to-media-partners">conexões de parceiros</Anchor> para essa audiência, se necessário.
11. Clique em **Concluir**.

A sua audiência foi atualizado usando o arquivo CSV. É importante observar, no entanto, que a lista de audiências revisada ainda não está disponível para upload para os parceiros, pois as audiências importadas são processadas com uma <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#eod">atualização de dados diária</Anchor>.

<div id="error-messages" />

### Mensagens de erro

| Mensagem | Causa | O que fazer |
| --- | --- | --- |
| Problema com a lista de dispositivos | Um ou mais problemas com a lista de dispositivos | Verifique se o arquivo CSV:<ul><li>está preenchido com dispositivos e identificadores GAID/IDFA no formato correto</li><li>contém os identificadores necessários</li><li>tem uma linha de header com os cabeçalhos no formato correto</li><li>não possui linhas em branco</li><li>app\_id está associado ao app correto que você usa para o Audiences</li></ul> |
| Parece que a sua lista de dispositivos está vazia. Adicione alguns device IDs e tente novamente. | O arquivo CSV está vazio | Verifique se o CSV contém pelo menos um device ID. |
| Não conseguimos entender um ou mais dos seus device IDs. | <ul><li>O formato do CSV está incorreto</li><li>O arquivo enviado não é um arquivo CSV</li><li>O arquivo CSV foi editado e salvo por um programa que não é um editor CSV válido (por exemplo, Microsoft Excel) Microsoft Excel) Microsoft Excel)</li><li>Um ou mais device IDs estão no formato errado</li></ul> | <ul><li>Verifique se o CSV está no formato correto.</li><li>Verifique se todos os device IDs estão no formato correto.</li><li>Se tiver usando o Excel, salve o arquivo como um arquivo CSV, conforme descrito acima.</li></ul> |
| Não é possível usar a importação v1 ao aplicar a política de conta de usuário à audiência. | Você enviou um arquivo CSV para uma [audiência padrão](/docs/audiences-import-audience-segments-from-internal-systems#tipos-de-audiências-importadas) utilizando a estrutura de importação V1.0. As audiências padrão devem ser enviadas usando um CSV na estrutura V2.0. | Edite o arquivo CSV para utilizar o formato, as colunas e os identificadores descritos acima. |
| Tivemos um problema temporário de conexão e não conseguimos carregar o seu arquivo. Tente novamente agora. | Possível erro de rede | Tente enviar novamente o arquivo CSV. |

</Accordion>

<div id="use-the-import-audience-api" />

<Accordion title="Usando a Import Audience API">

A Import Audience API é usada para adicionar ou remover dispositivos de uma audiência.

**Para importar uma nova audiência usando a API:**

1. No dashboard esquerdo da AppsFlyer, vá até **Engajar** > **Audiences**.
2. Clique em **Nova audiência**.
3. Escolha **Importar audiência**.  
   A janela **Importar audiência** será aberta.
4. Insira um **Nome de audiência** exclusivo. **Nota:** Os nomes das audiências não podem incluir caracteres especiais (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
5. Selecione a plataforma: **Android** ou **iOS**.
6. Indique se essa audiência é [**padrão** ou **como está**](/docs/audiences-import-audience-segments-from-internal-systems#tipos-de-audiências-importadas) .
   * Para uma **audiência padrão**, mantenha a caixa desmarcada.
   * Para uma **audiência tal como está**, marque a caixa (essa opção está disponível apenas para administradores). Em conformidade com o Digital Markets Act (DMA) da Google: a partir de 6 de março de 2024, ao importar uma audiência "como está", será necessário adicionar <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy#importação-de-audiências">duas colunas adicionais de consentimento</Anchor>. Preencher esses campos assegura a máxima inclusão de usuários do <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">Espaço Econômico Europeu (EEE)</Anchor> nas suas audiências do Google.
7. Clique em **Salvar**.  
   A página importar é exibida.
8. Em **Importar usando a API**, mantenha a opção padrão de **Adicionar novos dispositivos/usuários** (já que se trata de uma nova audiência).
9. Copie a URL de pedido da API da página <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">Importar uma nova audiência</Anchor> (o token da API já está incluído).
10. Depois, copie e cole o corpo do pedido da API.
11. Clique em **Concluído**.  
    **A aba Conectar é exibida.**
12. **(Opcional)** Siga as instruções para <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#connect-an-audience-to-media-partners">conectar uma audiência a parceiros</Anchor>.
13. Clique em **Concluir**.
14. Prepare o pedido da API incluindo os identificadores de usuário/dispositivo e envie-o para a AppsFlyer.

**Para atualizar uma audiência existente usando a API:**

1. No dashboard esquerdo da AppsFlyer, vá até **Engajar** > **Audiences**.
2. Clique no nome da audiência que você deseja atualizar.  
   A tela **Editar audiência** aparece, com a aba **Definir**.
3. Se você deseja alterar o nome da audiência, você pode fazer isso agora. Caso contrário, selecione a aba **Importar**.
4. Em **Importar usando a API**, escolha o que fazer com a lista enviada:
5. **Adicionar novos dispositivos/usuários:** Adicione identificadores de dispositivos/usuários à audiência existente.
6. **Remover dispositivos/usuários:** Remova os identificadores de dispositivo/usuário da audiência existente.
7. Copie a **API request URL** da página <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">Importar uma nova API de audiência</Anchor> (o token da API já está incluído). **Atenção:** Alterar essa opção modifica o caminho do endpoint no código a ser copiado. Certifique-se de que está usando o endpoint correto para a ação que está realizando (nessa e em futuras solicitações de API).
8. Em seguida, copie o **corpo do pedido da API.**
9. **A aba Importar é mostrada.**
10. Faça alterações nas <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#connect-an-audience-to-media-partners">conexões de parceiros</Anchor> para essa audiência, se necessário.
11. Clique em **Concluir**.
12. Prepare o pedido da API incluindo os identificadores de usuário/dispositivo e envie-o para a AppsFlyer.

**Atenção:** Ao importar através da API, a atualização da audiência levará 24 horas.

<div id="response-codes" />

### Códigos de resposta

| Código | Mensagem | Descrição |
| --- | --- | --- |
| 200 | A solicitação foi bem-sucedida | Audiência importada com sucesso |
| 400 | Essa audiência já está configurada para Android/iOS. Para usar uma plataforma diferente, crie uma nova audiência na interface do usuário. | A plataforma especificada no corpo do pedido não corresponde à plataforma especificada ao criar a audiência. |
| 400 | X ou mais linhas não contêm um App ID. É necessário anexar um App ID a cada linha. | Cada linha deve incluir um **app\_id**.<ul><li>**Atenção:** o app\_id não é necessário para uma [audiência tal como está](/docs/audiences-import-audience-segments-from-internal-systems#tipos-de-audiências-importadas), quando importada usando a funcionalidade legada de importação da versão V1.0.</li></ul> |
| 400 | X ou mais das suas linhas não contêm um identificador único válido. | Algumas ou todas as linhas não contêm pelo menos um dos seguintes identificadores em um formato válido:<ul><li>Para audiências Android: **gaid** OU **oiad** OU **imei** OU **cuid** OU **braze\_id** OU **amplitude\_id**</li><li>Para audiências iOS: **idfv** OU **cuid** OU **braze\_id** OU **amplitude\_id**</li></ul> |
| 400 | Não é possível processar mais de Y dispositivos por pedido (foram contados n dispositivos nesse pedido) | O corpo do pedido inclui uma lista com mais de 10.000 device IDs |
| 400 | A lista de dispositivos não pode estar vazia | O corpo do pedido contém uma lista de dispositivos vazia<br /><br />É necessário fornecer pelo menos um device ID por pedido |
| 400 | Não conseguimos interpretar um ou mais dos seus device IDs | Alguns ou todos os device IDs não estão em um formato válido |
| 400 | X ou mais dispositivos a remover contêm mais do que um device ID | Foi enviada uma solicitação de remoção com mais de um device ID |
| 403 | Proibido | Pedido não autorizado: Chave de importação incorreta ou ausente |
| 429 | Pedidos em excesso | Os pedidos estão limitados a 350 por minuto |
| 500 | Não foi possível interpretar o pedido | Formato do corpo do pedido inválido (não corresponde à estrutura JSON esperada ou não é JSON)<br /><br />Consulte o exemplo de pedido acima |

**Limitações da API**

* Você só pode adicionar dispositivos a uma audiência através de uma solicitação.
* Só é possível remover dispositivos de uma audiência através de uma solicitação.
* Você pode enviar até 20.000 device IDs por solicitação.
* Você pode enviar até 350 solicitações por minuto.

</Accordion>

<div id="imported-audience-management-api" />

<Accordion title="Imported Audience Management API">

A <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-2">Imported Audience Management API</Anchor> permite criar e configurar audiências importadas, conectar essas audiências a parceiros, eviar essas audiências aos parceiros e muito mais.

</Accordion>

<div data-zendesk-anchors="why-import-audiences=por-que-importar-audi%C3%AAncias h_01HA4M61P4H5AVXQFA5ETABA67=por-que-importar-audi%C3%AAncias 01ECF4ZD0QQ5JJNH624D0E9WRF=exemplos h_01HA4M61P41RSJMKSJ2V9WJH8W=audiences-import-v20 imported-audience-types=tipos-de-audi%C3%AAncias-importadas h_01HA4M61P4TEBNF264RNFC57YP=tipos-de-audi%C3%AAncias-importadas h_01HA4M61P4NVDJ393HA4V75PQV=importante audience-import-procedures=procedimentos-para-importa%C3%A7%C3%A3o-de-audi%C3%AAncias h_01HA4M61P4EEYGJNZ3N2D0KXS5=procedimentos-para-importa%C3%A7%C3%A3o-de-audi%C3%AAncias 01ECF4ZD0RHJAQ31NKFCX8QEWW=import-a-csv-file identifier-hash=hash-do-identificador h_01HA4M61P4BJZKN97ZTT8TKRBK=hash-do-identificador h_01M45CYAAKF4MV0S3Z89NW6PQS=importante-1 confirmation-messages=mensagens-de-erro h_01HA4M61P57TMZRK4XX7ARK896=mensagens-de-erro h_01HA4M61P5XZR7C20Y5D3XX4K9=use-the-import-audience-api response-codes=c%C3%B3digos-de-resposta h_01HA4M61P5YGX4QP2PDSVW7D3G=c%C3%B3digos-de-resposta h_01HA4M61P6CE4RBCVTA3KE15VN=imported-audience-management-api" />

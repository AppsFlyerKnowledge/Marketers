---
title: Audências – atributos dos utilizadores
metadata:
  keywords:
    - Advertisers
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
  created_at: '2020-06-11T06:13:55Z'
  edited_at: '2026-10-06T00:18:00Z'
  id: 360009775517
  locale: pt
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/pt/articles/360009775517
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão Geral:** Aumente a sua capacidade de segmentar utilizadores em grupos relevantes ao adicionar dados sobre suas características aos Públicos.

[![UserAttributionNavigationXL3_us-en.png](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)](https://files.readme.io/d308c590f656a155845af5c181322a3876d2e4dd7df458f4899861954dbd4de7-33375683032465.png)

## Sobre os atributos dos utilizadores

Os atributos dos utilizadores, ao contrário de dados baseados em eventos, são características gerais que os seus utilizadores partilham com a sua empresa. Podem ser estáticos, como género, idade, data de nascimento e país, ou dinâmicos, como a pontuação de um jogo.

Os dados dos atributos dos utilizadores são:

* Atualizados através da importação de ficheiros CSV ou JSON via API.
* Armazenados em formato encriptado.
* Disponíveis para uso em qualquer conjunto de regras de audiências.

Os dados dos atributos dos utilizadores **não são partilhados com parceiros publicitários.**

Os atributos dos utilizadores estão disponíveis quer ao nível da aplicação quer ao nível da conta, conforme descrito neste artigo. Se utilizar atributos ao nível da aplicação, o utilizador da conta precisará de ter <Anchor target="_blank" href="/marketers/pt/docs/user-management#visão-geral">permissão da aplicação</Anchor> para gerir e utilizar os atributos.

O cenário seguinte oferece uma explicação detalhada dos atributos dos utilizadores.

<div id="scenario-app-marketer-requirements" />

<Accordion title="Cenário – requisitos para marqueteiros de aplicações">

Como marqueteiro de aplicações, está a realizar as seguintes tarefas:

* Gerenciar duas aplicações de jogos: jogo\_a e jogo\_b.
* Lançar o jogo\_c
* Direcionar os utilizadores atuais da aplicação com estes atributos:
  * Desporto favorito: Críquete
  * Pontuação atual do jogo: 15 ou mais em algum dos jogos atuais

A tabela contém dados de atributos dos utilizadores do seu CRM. Os conjuntos de regras de audiências necessitam de acesso a esses dados.   
![UserAttributuesExample_us-en.png](https://files.readme.io/6f86d8659ef089ac82bb8401b4af650fbc590d2293ac93de30e6f9b4fc2ceb86-33375683035281.png)

**Utilizar dados CRM em conjuntos de regras**

Em Audiências, crie atributos de utilizador (como desporto favorito e pontuação de jogo). Isto permite que o conjunto de regras aceda aos dados do CRM.

#### Atributos dos utilizadores no cenário

| UA: para atribuição de clique, defina o parâmetro de link de atribuição af\_click\_lookback. | ID da rede de anúncios para a qual o postback foi enviado | Nível |
| --- | --- | --- |
| <span id="game-score"></span>Pontuação do jogo | **Número**: Permite definir regras como '*PontuaçãoJogoB é maior que 29'*. | **Nível da aplicação**: A pontuação do utilizador é registada para cada jogo jogado.<br /><br />Significado: PontuaçãoJogoA, PontuaçãoJogoB. |
| <span id="favorite-sport"></span>Desporto favorito | **String:** Permite definir regras como "*cujo desporto favorito é ténis".*<br /><br />Nota! Os valores distinguem entre maiúsculas e minúsculas. | **Nível da conta**: O desporto favorito do utilizador mantém-se o mesmo, independentemente da aplicação.<br /><br />Nota! Um utilizador pode ter apenas um valor associado a atributos ao nível da conta. |

**Atributos do utilizador em conjuntos de regras**

Os atributos do utilizador funcionam como filtros nos conjuntos de regras dos Públicos. Este exemplo usa critérios (desporto favorito e pontuação do jogo) definidos pelo marketeer.

[<Image alt="UserAttributedExample.jpg" src="https://files.readme.io/296ab5e13abedd5f11c7d445ec9bf4a9b62295c18ad783228d6ccb9b631be74f-33375704836625.jpg" width="276px" />](https://files.readme.io/296ab5e13abedd5f11c7d445ec9bf4a9b62295c18ad783228d6ccb9b631be74f-33375704836625.jpg)

</Accordion>

## Implementar atributos de utilizador

Configure, adicione, gere e elimine atributos de utilizador.

<div id="set-up" />

<Accordion title="Configurar">

**Pré-requisito**:

Para gerir atributos ao nível da aplicação, o utilizador da conta deve ter permissão para tal.

**Para configurar os atributos do utilizador, siga os procedimentos seguintes:**

1. [Adicionar atributos do utilizador.](/docs/audiences-create-better-audiences-with-user-attribute-data#add)
2. [Realize uma das seguintes ações](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [Importe dados de atributos do utilizador via CSV.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [Importe dados de atributos do utilizador via API.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)
3. <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#user-attributes">Implemente os atributos do utilizador em conjuntos de regras.</Anchor>

</Accordion>

<div id="add" />

<Accordion title="Adicionar">

**Para adicionar atributos do utilizador:**

1. Na AppsFlyer, no menu lateral, selecione **Envolver** > **Públicos-alvo**.
2. Clique no separador Atributos do Utilizador.
3. Clique em **Adicionar atributo do utilizador**.

   ![UserAttributeAdd.png](https://files.readme.io/6c7f25bb23d47e67aaef34264029daa9ab058f08e218a441ab9dde8240b0b384-33375683046033.png)
4. Preencha os campos. As especificações dos campos estão listadas na tabela seguinte.
   * **Nome do atributo**
   * **Formato**
   * **Nível**
5. Clique em **Guardar**.

| Campo | Características |
| --- | --- |
| <span id="attribute-name"></span>Nome do atributo | <ul><li>Apenas caracteres em inglês</li><li>Sem pontuação ou caracteres especiais</li><li>O mesmo nome não pode ser usado tanto ao nível da aplicação quanto da conta</li><li>O mesmo nome **pode** ser usado ao nível da aplicação; por exemplo, conforme o cenário acima, a utilização de ScoreGameA e ScoreGameB</li></ul> |
| <span id="format"></span>Formato | <ul><li>Texto: Teste se o valor do atributo **é** ou **não é igual** a um valor de regra especificado. Exemplo: É críquete ou não é críquete.</li><li>Número: Teste se o valor do atributo é maior, menor ou igual a um valor de regra especificado. Exemplo: Pontuação superior a 15</li></ul> |
| <span id="level"></span>Nível | <ul><li>Nível da conta: Um atributo não tem ligação com a aplicação.<br />Exemplo: género, desporto favorito</li><li>Nível da aplicação: Um atributo está relacionado com a aplicação. Selecione as aplicações associadas ao atributo.</li></ul> |

**Campos de atributos do utilizador**

</Accordion>

<div id="manage" />

<Accordion title="Gerenciar">

Para gerir os atributos do utilizador, vá para **Públicos-alvo** > separador **Atributos do Utilizador**.

[![AudiencesUserAttributes_us-en.png](https://files.readme.io/6baee58e9cd9b2b39bc8facf0af72abe71a4bd1cd2f844f49467fbaeb7252cd7-33375704844049.png)](https://files.readme.io/6baee58e9cd9b2b39bc8facf0af72abe71a4bd1cd2f844f49467fbaeb7252cd7-33375704844049.png)

| Função | Descrição |
| --- | --- |
| <span id="search-and-filter"></span>Pesquisa e filtro | Por nome de atributo, nome da aplicação e nível de atributo. |
| <span id="sort-by"></span>Ordenar por | Clique no cabeçalho da coluna para ordenar as linhas da tabela. |
| <span id="import-data"></span>Importar dados | <ul><li>[Importar dados por CSV](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)</li><li>[Importar dados por API](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)</li></ul> |
| <span id="change-api-import-key"></span>Alterar chave de importação da API | **Para alterar a chave de importação da API:**<ol><li>Clique em **Importar dados**.</li><li>Selecione **API**.</li><li>Clique em **Atualizar chave de importação**.</li></ol>**Nota!** Se os scripts tiverem chaves incluídas, atualize-as com a nova chave. |

Gerir atributos de utilizador

</Accordion>

<div id="delete" />

<Accordion title="Eliminar">

![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Apenas um utilizador administrador pode eliminar um atributo.

**Para eliminar um atributo que faz parte de um conjunto de regras:**

1. Remova o atributo do conjunto de regras.
2. Elimine o atributo.

</Accordion>

## Importar dados

<div id="import-field-specifications" />

<Accordion title="Especificações dos campos de importação">

| Campo | Conteúdo | Formato | Adicionar dados  <br />por CSV | Remover dados por CSV |
| --- | --- | --- | --- | --- |
| <span id="device_id"></span>ID\_do\_dispositivo | Inclui um destes IDs de utilizador:<ul><li>IDFA</li><li>GAID</li></ul> | Texto | Obrigatório que **device\_id** ou **customer\_id** sejam fornecidos | Obrigatório que **device\_id** ou **customer\_id** sejam fornecidos<br /><br />Para remover dados existentes, não os envie |
| <span id="customer_id"></span>ID\_do\_cliente | <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">Idêntico a</Anchor> [campaign](#attribution::274e74d5). | Caraterística | Obrigatório que **device\_id** ou **customer\_id** sejam fornecidos | Obrigatório que **device\_id** ou **customer\_id** sejam fornecidos<br /><br />Para remover dados existentes, não os envie |
| <span id="app_id"></span>Preenchido para posicionamento de anúncio de CTV | **Atributo a nível da aplicação:** ID da aplicação conforme exibido no painel.<br /><br />Para aplicações iOS, inclua o prefixo *ID*.<br /><br />**Atributo a nível da conta**: Preencha sempre com * | Caraterística | Obrigatoriedade | Obrigatoriedade |
| <span id="attribute_key"></span>chave\_atributo | Nome do atributo do utilizador, tal como apresentado no separador de atributos do utilizador. | Caraterística | Obrigatoriedade | Obrigatoriedade |
| <span id="attribute_value"></span>valor\_atributo | Valor atribuído<br /><br />[*Consulte as limitações](/docs/audiences-create-better-audiences-with-user-attribute-data#limitations) | Texto ou número | Obrigatoriedade | Não enviar |

Lista de campos de atributos do utilizador

</Accordion>

<div id="import-data-by-csv" />

<Accordion title="Importar dados por CSV">

Os dados dos atributos do utilizador são adicionados ou removidos via ficheiro CSV. A figura e o ficheiro CSV de exemplo que se seguem correspondem ao cenário descrito neste artigo.

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012423857">Exemplo-atributo-do-utilizador.csv</Anchor>

![FileForAttributes.png](https://files.readme.io/2a9075ab7f900648aeebe3b5fca807c6b931ba5295f35708ee6c48d345f681b9-33375704847633.png)

**Requisitos do ficheiro CSV**

* Sem linha de cabeçalho
* Contém todas as colunas listadas na tabela anterior.

> 📘 **Importante!**
>
> Este formato CSV é para importar dados de atributos de usuário. Se, em vez disso, você estiver importando segmentos de audiências, consulte <Anchor target="_blank" href="/marketers/pt/docs/audiences-import-audience-segments-from-internal-systems">Importar segmentos de audiências de sistemas internos</Anchor>, que usa um formato CSV diferente que exige uma linha de cabeçalho.

**Para importar um ficheiro CSV:**

1. Aceda a **Públicos** > separador **Atributos do utilizador**.
2. Clique em **Importar dados**.
3. Selecione **CSV**.
4. Escolha uma das opções:
   * **Adicionar dados**
   * **Remover dados**
5. Escolha um ficheiro CSV para importar.
6. Clique em **Fazer upload**; aparecerá uma mensagem de estado da carga.

**Nota:** Ao importar atributos de utilizador, todos os dispositivos conhecidos associados a um ID de cliente recebem também o atributo. Por exemplo, se um utilizador importar 10 dispositivos (por customer\_id) para o atributo “Game Score”, e um dos customer\_ids estiver associado a 2 dispositivos (por exemplo, 2 GAIDs com o mesmo CUID), então esta importação conterá 11 registos de atributos do utilizador.

</Accordion>

<div id="import-data-by-api" />

<Accordion title="Importar dados através de API">

Este método de importação requer um URL de solicitação e um JSON com os dados dos atributos do utilizador.

1. No painel, obtenha as chamadas de solicitação de API preparadas e o modelo de JSON.
2. Preencha o modelo JSON com os seus dados de acordo com as [especificações dos campos](/docs/audiences-create-better-audiences-with-user-attribute-data#import-field-specifications).

**Para gerar o URL de solicitação da API e o modelo JSON:**

1. Clique em **Importar dados.**
2. Selecione **API.**
3. Escolha uma ação:  
   * Atualizar os atributos do utilizador: Substituir ou adicionar.
   * Remover os atributos do utilizador.
   * Remover dados do utilizador: Remove todos os dados relacionados a um utilizador específico. O utilizador é identificado pelo seu ID AppsFlyer.
   * Remover dados da aplicação: Remove todos os dados ao nível da aplicação.
4. Copie o URL de solicitação da API gerado.
5. Copie o corpo da solicitação de API gerado.
6. Prepare o JSON (com dados de atributos do utilizador) utilizando o formato JSON especificado. Para os atributos ao nível da conta, defina "app\_ids": ["*"]
7. Prepare a chamada da API baseada no URL e no corpo da solicitação.
8. Envie a solicitação de forma programática.

**Exemplo de solicitação e JSON**

```json
https://hq1.appsflyer.com/api/user-attributes-import-api/set-user-data
{
  "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
  "attributes_values": [
    {
      "device_id": "",
      "customer_id": "",
      "app_ids": [],
      "attributes": [
        {
          "attribute_key": "",
          "attribute_value": ""
        }
      ]
    }
  ]
}
```

> 📘 **Nota**
>
> Deve autenticar a solicitação usando um cabeçalho de autorização Bearer com um <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#appsflyer">token API V2.0</Anchor>

**Exemplo com múltiplos IDs de dispositivos, chaves de atributos e valores de atributos**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "2222222",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 5
                }
                ,
                {
                    "attribute_key": "favorite_sport",
                    "attribute_value": "cricket"
                }
            ]
        }
        ,
        {
            "device_id": "555555-d1d1-d1d1-555-fffffffff",
            "customer_id": "111111",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "order",
                    "attribute_value": 7
                }
                ,
                {
                    "attribute_key": "number",
                    "attribute_value": 8
                }
            ]
        }]
}
```

**Exemplo com um único ID de dispositivo e várias chaves e valores de atributos**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "12345678",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 90
                }
                ,
                {
                    "attribute_key": "favorite-sport",
                    "attribute_value": "cricket"
                }
                ,
                {
                    "attribute_key": "orderNumber",
                    "attribute_value": 93
                }
                ,
                {
                    "attribute_key": "netPromoterScore",
                    "attribute_value": 94
                }
            ]
        }
    ]
}
```

**Nota:** Ao importar atributos de utilizador, todos os dispositivos conhecidos associados a um ID de cliente recebem também o atributo. Por exemplo, se um utilizador importar 10 dispositivos (por customer\_id) para o atributo “Game Score”, e um dos customer\_ids estiver associado a 2 dispositivos (por exemplo, 2 GAIDs com o mesmo CUID), então esta importação conterá 11 registos de atributos do utilizador. Limitações de importação de CSV

</Accordion>

<div id="limitations" />

<Accordion title="Limitações">

#### Limitações gerais

* Apenas números inteiros (números inteiros) são suportados nos dados de importação CSV/API. Números do tipo float (decimais) não são suportados. **Exemplo:** Um valor de atributo "pontuação" pode ser 90, mas não 90,5.
* Os dados sobre atributos de utilizador não podem ser impressos ou descarregados.
* #### Limitações dos valores de atributos:

  * Não são permitidas vírgulas, pontos ou outros caracteres especiais nos valores de atributos.
  * Os valores de atributo de tipo sequência de caracteres estão limitados a 40 caracteres.
  * Os valores dos atributos não devem começar por 0.

#### Limitações de importação via API

* Máximo de 350 pedidos API por minuto, podendo a carga útil abranger até 10 mil dispositivos (10 mil dispositivos com um atributo, 5 mil dispositivos com dois atributos, etc.)
* As chaves `device_id` e `customer_id` são necessárias em todas as chamadas de importação. Se desejar importar atributos com apenas um desses identificadores, a chamada deve incluir o "cabeçalho" do outro identificador com uma sequência de caracteres vazia. Por exemplo, se quiser importar atributos por `device_id` e não por `customer_id`, a chamada deve ser semelhante a esta:

```json
"attributes_values": [
{
"device_id": "39e123.......",
"customer_id": "",
```

#### Limitações de importação de CSV

* Ao adicionar valores de atributos de utilizador, cada ficheiro CSV pode ter no máximo 10 milhões de linhas.

</Accordion>

<div data-zendesk-anchors="user-attributes=sobre-os-atributos-dos-utilizadores h_01HDNZH1XVX5BYQBPG848M8QZM=sobre-os-atributos-dos-utilizadores scenario%E2%80%94app-marketer-requirements=scenario-app-marketer-requirements h_01HDNZH1XV8AWVVGNYVA9G4PAG=scenario-app-marketer-requirements scenario-user-attributes=atributos-dos-utilizadores-no-cen%C3%A1rio h_01HDNZH1XW32ZJJRSANBQCTBV0=atributos-dos-utilizadores-no-cen%C3%A1rio implement-user-attributes=implementar-atributos-de-utilizador h_01HDNZH1XWPBVDHJ7AGPT5ZM9W=implementar-atributos-de-utilizador h_01HDNZH1XWYA9TQZ1B342A661R=set-up h_01HDNZH1XW0PPJF78EVFQTW3R7=add h_01HDNZH1XWGZ04TQXD5D50771A=manage h_01HDNZH1XWP8P1ZVJX11AXCS2P=delete import-data::b50dc884=importar-dados h_01HDNZH1XWCXV89YJV7EBJXNK5=importar-dados h_01HDNZH1XW87W1PV4C3PMY9QD6=import-field-specifications h_01HDNZH1XW3XC893Q8BQZQW2AG=import-data-by-csv h_01M45D4VCXXKXV25MQNAKW53ZW=importante h_01HDNZH1XX7PMGNTD683DD2B49=import-data-by-api h_01HDNZH1XXF6DSNKG19ZRZ01AZ=nota h_01HDNZH1XX61DVGK96C2TDSYW9=limitations general-limitations=limita%C3%A7%C3%B5es-gerais h_01HDNZH1XXZZFA3WHZEE5N24AB=limita%C3%A7%C3%B5es-gerais attribute-value-limitations=limita%C3%A7%C3%B5es-dos-valores-de-atributos h_01GZTGPK2FTHTV4NQ2HKV1HK00=limita%C3%A7%C3%B5es-dos-valores-de-atributos api-import-limitations=limita%C3%A7%C3%B5es-de-importa%C3%A7%C3%A3o-via-api h_01HDNZH1XX4JWSMSF4672ENWNS=limita%C3%A7%C3%B5es-de-importa%C3%A7%C3%A3o-via-api csv-import-limitations=limita%C3%A7%C3%B5es-de-importa%C3%A7%C3%A3o-de-csv h_01J3APYQ8MXG1SGREVN638R75N=limita%C3%A7%C3%B5es-de-importa%C3%A7%C3%A3o-de-csv" />

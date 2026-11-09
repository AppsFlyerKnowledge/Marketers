---
title: Migração de outros fornecedores para a AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2019-07-01T13:11:37Z'
  edited_at: '2026-08-18T00:18:21Z'
  id: 360001923697
  locale: pt
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/pt/articles/360001923697
---
> **Resumo:** planeje sua migração para a AppsFlyer a partir de outro fornecedor de atribuição. Entenda como evitar cobranças duplas, duplicação de dados e perda de dados durante o período de migração.

<Image align="center" alt="fluxo de migração" src="https://files.readme.io/31d67493ae3ae6912b4da3163ebb731a8d58494c3007ef1d08cb7332226d9e81-360017326677.png" />

<div id="about-migrating-to-appsflyer-from-other-vendors" />

## Migração de outros fornecedores para a AppsFlyer

A migração de outro fornecedor para a AppsFlyer inclui as seguintes etapas:

* [Integração do SDK](/docs/migration-to-appsflyer-from-other-vendors#integração-do-sdk)
* [Migração de dispositivos](/docs/migration-to-appsflyer-from-other-vendors#migração-de-dispositivosopcional)
* [Migração de campanhas](/docs/migration-to-appsflyer-from-other-vendors#migração-de-campanhas)
* [Configuração do relatório de dados](/docs/migration-to-appsflyer-from-other-vendors#configuração-do-relatório-de-dados)

Você pode fazer essas tarefas simultaneamente. No entanto, recomendamos que você:

* Conclua todas as tarefas antes de lançar seu aplicativo atualizado com o SDK da AppsFlyer.
* Pause as campanhas de marketing existentes antes de executar a migração do device ID.

<div id="compare-measurement-between-appsflyer-and-other-mmps" />

### Comparando a mensuração entre a AppsFlyer e a Adjust

Ao considerar a migração para a AppsFlyer a partir de outra MMP, os anunciantes podem querer comparar as mensurações de atribuição de ambas as MMPs nas mesmas fontes de mídia e campanhas. No entanto, nem todos os canais de mídia oferecem suporte à mensuração com mais de uma MMP. Aqueles que o fazem podem apresentar certas limitações para evitar discrepâncias de atribuição. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/measuring-attribution-with-multiple-mmps">mensuração de atribuição com mais de uma MMP</Anchor>.

<div id="tasks" />

## Tarefas

A tabela a seguir descreve o escopo de trabalho necessário para cada tarefa. Para ver uma análise precisa das tarefas gerais na ordem na qual você deve realizá-las e acompanhar o seu progresso, baixe <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">essa planilha</Anchor>.

<div id="scope-of-work" />

#### Escopo do trabalho

<table><thead><tr><th>Função</th><th>Ação necessária</th><th>Quem está envolvido</th><th>Tempo estimado</th><th>Observações</th></tr></thead><tbody><tr><td>Pré-requisitos</td><td><ol><li> <a href="https://www.appsflyer.com/get-started" target="_blank">Crie uma conta na AppsFlyer</a>.</li><li> <a href="./adding-an-app-to-appsflyer" target="_blank">Adicione o aplicativo</a> à AppsFlyer.</li><li>[Opcional] Altere a <a href="./set-up-re-attribution-window" target="_blank">janela de reatribuição</a> padrão de 90 dias para alinhar <span>com a sua definição de usuários ativos.</span> </li></ol></td><td>Profissional de marketing/usuário do dashboard da AppsFlyer</td><td>2 horas</td><td> </td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#integração-do-sdk">Integração do SDK</a></td><td><ul><li>Integre o SDK da AppsFlyer ao seu aplicativo.</li><li>Mapeie eventos in-app S2S ou SDK.</li><li>Atualize a versão do aplicativo nas app stores.</li></ul></td><td>Desenvolvedores do app</td><td>1-2 semanas</td><td><ul><li> <strong>Recomendado</strong>: integre o SDK da AppsFlyer em um aplicativo de pré-produção para teste.</li><li>O aplicativo de produção deve ser atualizado nas lojas de aplicativos depois que todas as outras tarefas forem concluídas.</li></ul></td></tr><tr><td> <a href="./migration-to-appsflyer-from-other-vendors#migração-de-dispositivosopcional">Migração de dispositivos</a> [opcional]</td><td>Migre os IDs dos dispositivos para evitar a dupla atribuição dos seus usuários existentes.</td><td>Engenheiro de dados</td><td>1-2 semanas</td><td rowspan="2"><ul><li>Considere pausar suas campanhas existentes antes da migração e retome-as depois que a versão do aplicativo for atualizada.</li><li>Considere repetir a migração de dispositivos na data final da migração para garantir uma cobertura completa. </li></ul></td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#migração-de-campanhas">Migração de campanhas</a></td><td><ul><li>Integre suas ad networks na AppsFlyer</li><li>Migre campanhas existentes de:<ul><li>SRNs</li><li>Ad networks que não são SRNs</li><li>Mídias próprias</li></ul></li></ul></td><td>Profissional de marketing/Gerente de UA</td><td>1-3 semanas</td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#configuração-do-relatório-de-dados">Configuração do relatório de dados</a></td><td><ul><li>Adapte/mapeie as estruturas dos seus relatórios atuais para as estruturas da AppsFlyer.</li><li>Prepare-se para receber relatórios da AppsFlyer.</li></ul></td><td>Engenheiro de dados</td><td>2-4 semanas</td><td> </td></tr></tbody></table>

<div id="sdk-integration" />

### Integração do SDK

<div id="sdk-integration::c763138b" />

<Accordion title="Integração do SDK">

O SDK integrado ao aplicativo é a conexão entre o aplicativo e a plataforma da AppsFlyer. Ele relata instalações, aberturas do app, eventos in-app e outros.

**Para fazer a integração do SDK da AppsFlyer**:

1. Integre o SDK da AppsFlyer ao aplicativo.  
   Consulte os guias de integração do SDK para <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">Android</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">iOS</Anchor>.
2. Mapeie os eventos in-app que você quiser registrar usando os esquemas da AppsFlyer.  
   Isso pode ser feito via <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">SDK</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Remova o SDK do fornecedor de atribuição concorrente.  
   Você pode fazer isso imediatamente e mudar exclusivamente para a AppsFlyer, ou executar os dois SDKs simultaneamente por algumas semanas. Veja mais detalhes sobre essas opções na tabela abaixo.

| Opção | O que acontece depois do  <br />lançamento da versão atualizada do aplicativo? | Impacto |
| --- | --- | --- |
| Remova o SDK do concorrente (recomendado) | Somente a AppsFlyer registra novas instalações e atualiza o número de usuários.  <br />O concorrente ainda mostra eventos realizados pelos usuários, até que os usuários também atualizem seu aplicativo. | <ul><li>Transição rápida.</li><li>Sem atribuição duplicada.</li></ul> |
| Mantenha o SDK do concorrente para um período de transição | A AppsFlyer e o concorrente atribuem novas instalações e registram eventos. Após determinado tempo, remova o SDK do concorrente. | <ul><li>A validação de dados é possível. Ou seja, você pode comparar dados da AppsFlyer e do outro fornecedor.</li><li>Atribuição duplicada, que pode causar cobranças duplas com ad networks. Veja o exemplo abaixo.</li><li>Maior carga de trabalho.</li></ul> |

4. Depois que todas as outras tarefas no escopo do trabalho forem concluídas, atualize a versão do aplicativo com o SDK da AppsFlyer para o mercado. Novos usuários são atribuídos pela AppsFlyer.   
   **Atenção:**
   * Certifique-se de atualizar o aplicativo para iOS, Google Play e outros mercados relevantes fora da loja Android.
   * Seu aplicativo Android pode existir em sites de APK não oficiais, mesmo que você não os conheça (pesquise pelo nome do pacote do seu aplicativo para descobrir se esse é o caso). Os sites de APK levam algum tempo para atualizar para a versão mais recente. Por isso, eles podem trazer usuários orgânicos, que instalam versões antigas sem o SDK da AppsFlyer.
   * Os lançamentos de atualizações do aplicativo nas lojas podem levar alguns dias para serem totalmente concluídos. Os usuários que fizerem a instalação durante essa fase ainda podem obter a versão anterior.

</Accordion>

<div id="device-migrationoptional" />

### Migração de dispositivos—opcional

<div id="about-device-migration" />

<Accordion title="Sobre a migração de dispositivos">

A migração de dispositivo é o processo de upload de uma lista de device IDs de usuários existentes (IDFA, IDFV, GAID) na AppsFlyer. Você deve realizar esse processo antes de lançar a nova versão do aplicativo, que incluirá o SDK da AppsFlyer. Há duas opções ao migrar dispositivos: migração [atribuída](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) ou [não atribuída](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration).

A migração de dispositivos resolve os problemas de dados relacionados aos usuários existentes do aplicativo, que fizeram o download do aplicativo e foram atribuídos pelo fornecedor anterior. Por exemplo, as cobranças duplas da SRN, que ocorrem quando os usuários originalmente atribuídos a uma SRN pelo seu fornecedor anterior, e que ainda estão dentro da janela de lookback, são reivindicados pela SRN novamente na AppsFlyer.

<div id="example" />

> 📄 **Exemplo**
>
> * Um novo usuário clica em um anúncio no Facebook e instala seu aplicativo no dia 15 de junho.
> * No dia 24 de junho, o usuário atualiza o aplicativo para a versão com o SDK da AppsFlyer e o inicializa. Para a AppsFlyer, esse é um novo usuário, que precisa ser atribuído em tempo real.
> * A AppsFlyer consulta o Meta ads com o ID do dispositivo do usuário. Como o usuário ainda está dentro da janela de lookback de 28 dias do Meta ads, o Meta ads auto-atribui o usuário. Isso causa uma cobrança dupla para o proprietário do aplicativo em relação ao mesmo usuário.

Depois de migrar os dispositivos, os dados são refletidos na AppsFlyer da seguinte maneira:

* Dados de instalações: assim como as <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window#reinstall">reinstalações</Anchor>, dispositivos migrados não têm dados de instalação. As instalações de dispositivos migrados não são exibidas na AppsFlyer.
* **Dados de eventos e sessões in-app:** são registrados e exibidos como orgânicos para o [método de migração de dispositivo não atribuído](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration) ou são atribuídos ao canal de mídia e campanha, quando o [método atribuído](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) é usado.
* **Retargeting:** eatribuições e reengajamentos são exibidos normalmente.
* **Dados de atividade:** mostrados normalmente.
* **Dados de retenção e de cohort:** dispositivos migrados não têm registros de instalação. Portanto, eles não estão associados a qualquer cohort e não podem ser exibidos nos relatórios de retenção e cohort.

<div id="note" />

> 📘 **Nota**
>
> Se o aplicativo não for aberto dentro de 180 dias a partir da data de migração, todos os dados do dispositivo migrado serão excluídos. Consequentemente, se o aplicativo for aberto após o período de 180 dias, uma nova instalação será registrada.

</Accordion>

<div id="how-to-migrate-devices" />

<Accordion title="Como migrar dispositivos">

**Para migrar dispositivos:**

1. Decida qual população de usuários você deseja migrar. Você pode migrar todos os usuários existentes (o que pode impedir que você acesse dados precisos de reatribuição da AppsFlyer) ou usuários que instalaram seu aplicativo recentemente (o que pode levar a cobranças duplicadas de usuários um pouco mais antigos).  
   **Recomendamos que você migre usuários ativos durante o período da janela de reatribuição atual.** Por exemplo, se o aplicativo tiver uma janela de reatribuição de 90 dias, migre os usuários que tiveram pelo menos uma sessão durante os 90 dias anteriores.
2. [Opcional] Peça ao profissional de marketing/gerente de UA para pausar campanhas de marketing existentes (de SRNs, ad networks não-SRNs, mídias próprias, etc.) até depois da migração do dispositivo.  
   Se você decidir não pausar as campanhas, migre os device IDs que permaneceram no outro fornecedor assim que a versão atualizada do aplicativo com o SDK da AppsFlyer for lançada nas lojas de aplicativos.
3. Prepare um arquivo CSV com base na população de usuários selecionada, usando a estrutura de migração [atribuída](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) ou [não atribuída](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration). <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">Veja um exemplo de CSV</Anchor>
4. Envie o CSV ao seu CSM da AppsFlyer.  
   Seu CSM migrará os device IDs para a AppsFlyer.

</Accordion>

<div id="attributed-migration" />

<Accordion title="Migração atribuída">

Os dispositivos migrados para a AppsFlyer com esse método têm seus eventos in-app e sessões registrados e exibidos de acordo com o canal de mídia relatado pelo fornecedor de atribuição anterior, e de acordo com as políticas de retenção de dados das ad networks.

<div id="note-1" />

<div id="attributed-device-migration-csv-structure" />

#### Estrutura CSV de migração de dispositivo atribuído

| Nome da  <br />coluna | Descrição | Obrigatório | Exemplos |
| --- | --- | --- | --- |
| app\_id | App ID exibido no dashboard da AppsFlyer | Sim | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| platform | Plataforma do dispositivo: ios ou android | Sim | <ul><li>ios</li><li>Android</li></ul> |
| device\_id | <ul><li>Android: gaid, android\_id</li><li>iOS: IDFV (recomendado, se disponível) ou IDFA</li><li>Não duplique a mesma combinação de device ID e app ID em múltiplas linhas. Se ocorrer duplicação, a última ocorrência no arquivo será usada.</li></ul> | Sim | <ul><li>**gaid** (letras minúsculas): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id** (letras minúsculas): f35aea8908254891</li><li>**IDFV** (letras maiúsculas): A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (letras maiúsculas): 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android:<ul><li>advertiserId</li><li>android\_id</li><li>amazon\_aid</li></ul></li><li>iOS:<ul><li>idfa</li><li>idfv</li></ul></li><li>No momento, outros identificadores, como OAID e IMEI, não são compatíveis.<br />Use a migração não atribuída para usuários Android que não vêm do Google Play.</li></ul>**Atenção**<br />`android_id` não é coletado pelo SDK da AppsFlyer por padrão. Se você usa `android_id` como seu identificador, certifique-se de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">coletá-lo na sua integração do SDK</Anchor>. | Sim | <ul><li>advertiserId</li><li>android\_id</li><li>idfa</li><li>idfv</li><li>amazon\_aid (letras minúsculas): df07c7dc-cea7-4a89-b328-810ff5acb15d</li></ul> |
| install\_time | O tempo de instalação do aplicativo original com o <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor> no formato UTC:  <br />**aaaa-mm-ddTHH:MM:SS.SSS** | Não | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>Ou:<ul><li>ID de parceiro da AppsFlyer</li><li>Canal de mídia personalizada (não pode ser um ID de parceiro).</li></ul></li><li>Para obter a lista de IDs de parceiros, conforme exigido pela AppsFlyer:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">Ative todos os parceiros integrados relevantes.</Anchor></li><li>Execute a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">Get active integrations API</Anchor> para obter uma lista de todas as integrações ativas.</li><li>Use o **media\_source\_name** da API como o valor **media\_source** no CSV.</li><li>Exceções:<ul><li>Para o Apple Search Ads use **Apple Search Ads**.</li><li>Para Twitter, use **twitter**.</li></ul></li></ul></li><li>Formato: Os valores fazem distinção entre maiúsculas e minúsculas.</li></ul> | Sim | Não orgânico: facebook\_int, googleadwords\_int<br /><br />Orgânico: organic |
| integrated\_partner | <ul><li>Indica se o canal de mídia é um parceiro integrado ou não. Ou seja, canal de mídia orgânica ou personalizada.</li><li>Formato: Os valores fazem distinção entre maiúsculas e minúsculas.</li></ul> | Sim | <ul><li>Sim</li><li>no (se media\_source for personalizado)</li></ul> |
| campanha | Para obter detalhes de atribuição mais granulares, forneça o nome da campanha original.<br /><br />Formato: String | Não |  |
| campaign\_id | Para obter detalhes de atribuição mais granulares, forneça o ID da campanha original.<br /><br />Formato: Formato: string sem espaços | Não |  |

**Regras de arquivo CSV:**

* O arquivo CSV pode conter dispositivos de usuários de vários aplicativos.
* Não duplique a mesma combinação de device ID e app ID em múltiplas linhas. Se ocorrer duplicação, a última ocorrência no arquivo será usada.
* Todos os cabeçalhos de coluna devem ser incluídos: app\_id, platform, device\_id, id\_type, install\_time, media\_source, integrated\_partner, campaign, campaign\_id. **Atenção:** a ordem dos campos é importante e deve ser mantida.
* Você pode adicionar o IDFV e o IDFA para o mesmo dispositivo, mas eles devem estar em linhas separadas. Todos os campos nas linhas separadas devem ser os mesmos, exceto device\_id.
* Cada linha deve conter exatamente 9 campos separados por vírgulas.
* Deixe os campos não obrigatórios vazios (em branco).
* Os arquivos podem conter até 5 milhões de linhas.
* Caso você tenha vários arquivos, dê a cada arquivo um nome exclusivo.
* Codifique dados usando UTF-8.
* [Opcional] Compacte arquivos usando ZIP ou GZIP.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">Veja um exemplo de CSV</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="Migração não atribuída">

Os dispositivos migrados para a AppsFlyer com esse método são registrados (mas não são exibidos) como usuários orgânicos. Seus eventos in-app e dados de sessões também são gravados e exibidos como orgânicos.

<div id="non-attributed-device-migration-csv-file-structure" />

#### Estrutura de arquivo CSV de migração de dispositivos não atribuídos

| Opção | Colunas | Quando utilizar | Exemplo |
| --- | --- | --- | --- |
| 1 | App ID + IDFA/GAID | <ul><li>Se todos os usuários Android tiverem identificadores GAID.</li><li>Somente usuários do iOS</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png)](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png) |
| 2 | App ID + Device ID + tipo do Device ID | <ul><li>Se alguns dos seus usuários Android tiverem apenas IMEI ou Android ID, mas não GAID (mercados fora da loja, versões Android anteriores à versão 4.4.2).</li><li>O Android ID precisa ter um formato hexadecimal.</li></ul>**Observação**:<ul><li>Use as strings específicas para a coluna de **tipo de ID**: advertiserId (também compatível com amazon\_aid), idfa, idfv, android\_id, imei.</li><li>Se você usar android\_id ou imei e, posteriormente, a AppsFlyer receber um identificador melhor, uma nova atribuição poderá ser registrada.</li><li>`android_id` e `imei` não são coletados pelo SDK da AppsFlyer por padrão. Se você usa algum desses identificadores, certifique-se de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">coletá-lo na sua integração do SDK</Anchor>.</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png)](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png) |

**Regras de arquivo CSV:**

* O arquivo CSV pode conter dispositivos de usuários de vários aplicativos.
* Cada linha contém um device ID único por aplicativo.
* Dependendo da opção de estrutura de arquivo escolhida, as colunas de arquivo devem ser as seguintes (na ordem listada):
  * Opção 1: app\_id, device\_id
  * Opção 2: app\_id, device\_id, id\_type
* IDs de aplicativos em letras minúsculas
* Identificadores Android em letras minúsculas
* IDFA/IDFV em maiúsculas
* Até 25 milhões de linhas permitidas

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">Veja um exemplo de CSV</Anchor>

</Accordion>

<div id="campaign-migration" />

### Migração de campanhas

Transfira as campanhas de marketing existentes para a AppsFlyer para ativar a atribuição da AppsFlyer, evitando cobranças duplicadas e perda de dados de atribuição.

**Atenção:** você pode optar por migrar apenas algumas campanhas de marketing de cada vez. Nesse caso, você pode segmentar as que deseja migrar por canal de mídia (por exemplo, ad network ou agência), geolocalização ou campanha.

<div id="srns" />

<Accordion title="SRNs">

As SRNs respondem às parceiras de mensuração mobile (MMPs) quando consultados sobre engajamentos de dispositivos específicos. Se dois MMPs, como a AppsFlyer e um fornecedor de atribuição concorrente, consultarem a mesma SRN sobre a mesma instalação do dispositivo, isso poderá resultar em cobranças duplas.

**Para migrar campanhas de SRN**:

* Ative e configure as <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">SRNs</Anchor> relevantes na AppsFlyer.

> 📘 **Nota**
>
> * SRNs podem executar várias MMPs (exceto Meta Ads e Twitter).
> * O Meta Ads não corrige eventos in-app duplicados.

</Accordion>

<div id="nonsrn-ad-networks" />

<Accordion title="Ad networks que não são SRNs">

Os links de atribuição das ad networks registram os engajamentos dos usuários e, posteriormente, são usados para a atribuição desses engajamentos, que se tornam instalações reais.

**Para migrar campanhas de ad networks que não são SRNs**:

1. <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">Ative</Anchor> as ad networks relevantes na AppsFlyer.
2. <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">Gere links de atribuição da AppsFlyer</Anchor> para cada ad network.
3. Troque os links existentes em cada uma das suas campanhas pelos links de atribuição da AppsFlyer.

</Accordion>

<div id="owned-media" />

<Accordion title="Mídias próprias">

Mídias próprias se referem aos links de atribuição que você usa em:

* Compartilhamento de conteúdo
* web-to-app
* E-mail
* SMS
* Posts em redes sociais
* Blogs
* Comunidades virtuais (Quora, etc.)
* E mais...

Para essas campanhas, a AppsFlyer usa <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">links do OneLink</Anchor>. Os links do OneLink redirecionam os usuários com base em seus dispositivo para a loja correta, diretamente para o aplicativo ou para uma URL/landing page na web.

**Para mudar seus links de mídia própria atuais para links do OneLink**:

* Entre em contato com seu CSM, que o ajudará a transformar seus links de mídias própria em links do OneLink de acordo com os canais e ferramentas que você usa atualmente.

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

Para a atribuição da SKAdNetwork (SKAN), você deve ter um único SDK para atualizar o valor de conversão. Caso contrário, os dados da SKAN não têm utilidade. Portanto, certifique-se de que, após a migração, apenas o SDK da AppsFlyer poderá atualizar o valor de conversão da SKAN.

<Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">Saiba mais sobre como configurar o valor de conversão da SKAN na AppsFlyer.</Anchor>

</Accordion>

<div id="data-report-setup" />

### Configuração do relatório de dados

<div id="adapt-and-map-report-structures" />

<Accordion title="Adaptar e mapear estruturas de relatório">

Antes da migração, seus sistemas armazenam seus dados de atribuição do fornecedor atual de acordo com as estruturas, campos e parâmetros de relatórios que você configurou com eles. Para que a AppsFlyer relate corretamente os dados, você deve adaptar e mapear suas estruturas de relatório atuais para a estrutura, campos e parâmetros de relatório da AppsFlyer.

**Para adaptar/mapear suas estruturas de relatório:**

* Entre em contato com o CSM da AppsFlyer para obter ajuda para adaptar/migrar rapidamente as estruturas de dados dos seus relatórios do Adjust, Branch/Tune ou Kochava para a AppsFlyer.

</Accordion>

<div id="prepare-report-methods" />

<Accordion title="Preparar métodos de relatório">

Você pode obter dados <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-apis">brutos</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/analytics-and-aggregate-reporting-apis">agregados</Anchor> dos relatórios da AppsFlyer usando diversos métodos. Familiarize-se com os métodos e configure aqueles que são relevantes para você.

Os métodos incluem:

* Painéis
* Exportação de relatórios
* API de push
* Extrair API
* Relatório do Data Locker

</Accordion>

<div data-zendesk-anchors="overview=migra%C3%A7%C3%A3o-de-outros-fornecedores-para-a-appsflyer 01H8EDSTP8N4GZJQ5J609C3DHM=migra%C3%A7%C3%A3o-de-outros-fornecedores-para-a-appsflyer compare-measurement-between-appsflyer-and-other-mmps=comparando-a-mensura%C3%A7%C3%A3o-entre-a-appsflyer-e-a-adjust h_01HQJ10ZFJR43KBYMD9A07CJ99=comparando-a-mensura%C3%A7%C3%A3o-entre-a-appsflyer-e-a-adjust tasks=tarefas 01H8EDSTP8YGDZBPEY1976JP8C=tarefas scope-of-work=escopo-do-trabalho 01H8EDSTP8HGCVHYX49GQQEHBB=escopo-do-trabalho sdk-integration=integra%C3%A7%C3%A3o-do-sdk h_01F0RDXJ4F34DDKRFV5G6WZQX0=integra%C3%A7%C3%A3o-do-sdk 01H8EDSTP97C85X2E9EKBSVFQJ=sdk-integration::c763138b device-migration%E2%80%94optional=migra%C3%A7%C3%A3o-de-dispositivosopcional h_01F0RDXVSQ13R9Q2KT7PK1KSCQ=migra%C3%A7%C3%A3o-de-dispositivosopcional 01H8EDSTP9NDF6611MVEMWQSMZ=about-device-migration 01H8EDSTP93QJA4XZB6TDWWH1V=exemplo 01JA2CAMW3HCHC4B9FX7517FJ6=nota 01H8EDSTP9M2MDMGZ8QBQGPM6S=how-to-migrate-devices h_01F0RPWKQ4B0T1TXRGPVTYPPFB=attributed-migration attributed-device-migration-csv-structure=estrutura-csv-de-migra%C3%A7%C3%A3o-de-dispositivo-atribu%C3%ADdo 01H8EDSTP9HABKEZJXMB84CDDE=estrutura-csv-de-migra%C3%A7%C3%A3o-de-dispositivo-atribu%C3%ADdo h_01KV852C6CGBHSB6EFY122DRQY=estrutura-csv-de-migra%C3%A7%C3%A3o-de-dispositivo-atribu%C3%ADdo h_01F0RPX3SJ391M8SPNNN50DDA8=nonattributed-migration nonattributed-device-migration-csv-file-structure=estrutura-de-arquivo-csv-de-migra%C3%A7%C3%A3o-de-dispositivos-n%C3%A3o-atribu%C3%ADdos 01H8EDSTP9AFDMQS6BPQJY19ZH=estrutura-de-arquivo-csv-de-migra%C3%A7%C3%A3o-de-dispositivos-n%C3%A3o-atribu%C3%ADdos campaign-migration=migra%C3%A7%C3%A3o-de-campanhas h_01F0RDY9WPSBZVP3B7XN3ZEJKK=migra%C3%A7%C3%A3o-de-campanhas 01H8EDSTP94KSE1J4J5B7HX96Z=srns 01H8EDSTP9ZGMHSM44BWGF1FJN=nota-1 01H8EDSTP981XVWVM2NE0A45RM=nonsrn-ad-networks 01H8EDSTP9XNJA80Z5XR7WR9QN=owned-media 01H8EDSTP9Q8JAPNXSQWSHSK32=skan data-report-setup=configura%C3%A7%C3%A3o-do-relat%C3%B3rio-de-dados h_01F0RDYKYHAEZ65GZBZ3MWTB5Z=configura%C3%A7%C3%A3o-do-relat%C3%B3rio-de-dados 01H8EDSTP91E934EDXTPXW2ARJ=adapt-and-map-report-structures 01H8EDSTPAF8H5ESHDVK42M0RB=prepare-report-methods" />

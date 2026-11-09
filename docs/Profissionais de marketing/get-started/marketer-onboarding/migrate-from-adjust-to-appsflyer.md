---
title: Migre da Adjust para a AppsFlyer
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-12-02T10:01:48Z'
  edited_at: '2026-08-18T00:18:15Z'
  id: 30563700129297
  locale: pt
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/pt/articles/30563700129297
---
> **Em resumo:** Planeje sua migração da Adjust para a AppsFlyer. Entenda como evitar cobranças duplas, duplicação de dados e perda de dados durante o período de migração.

<Image align="center" alt="" src="https://files.readme.io/cc012894dd05255c0b7fa448b1c95d925d556ddb43dc461086bb71e9279da90d-30633481029137.png" width="1765px" />

<div id="about-migrating-to-appsflyer" />

## Sobre a migração para a AppsFlyer

A migração da Adjust para a AppsFlyer consiste de uma transição simples e fácil para uma plataforma confiável de atribuição e marketing analytics. A AppsFlyer oferece soluções seguras e imparciais, juntamente com um conjunto de ferramentas avançadas projetadas para te ajudar a navegar pelas mudanças no mercado. Com um suporte global e foco na melhoria contínua do produto, a AppsFlyer visa equipar empresas com as ferramentas e insights necessários para que elas cresçam e se adaptem.

<div id="compare-measurement-between-appsflyer-and-adjust" />

#### Compare a mensuração entre a AppsFlyer e a Adjust

Ao considerar a migração, recomendamos que você compare as mensurações de atribuição da AppsFlyer e da Adjust nos mesmos canais de mídia e campanhas. No entanto, nem todos os canais de mídia oferecem suporte à mensuração com mais de uma MMP. Aqueles que o fazem podem apresentar certas limitações para evitar discrepâncias de atribuição. Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/measuring-attribution-with-multiple-mmps">mensuração de atribuição com mais de uma MMP</Anchor>.

<div id="tasks" />

## Tarefas

[![](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png)](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png) A tabela a seguir descreve as principais etapas necessárias para a migração. Para ver uma análise detalhada das tarefas gerais, bem como registrar seu progresso, faça o download <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">desta planilha</Anchor>.

Você pode fazer essas tarefas simultaneamente, o que significa que os profissionais de marketing, desenvolvedores e engenheiros de dados podem, na maioria das vezes, trabalhar em suas tarefas simultaneamente. Recomendamos que você:

* Conclua todas as tarefas antes de lançar seu aplicativo atualizado com o SDK da AppsFlyer.
* Pause as campanhas de marketing existentes antes de executar a migração do device ID.

<table><thead><tr><th>Passo</th><th>Quem está envolvido</th><th>Tempo estimado</th><th>Considerações</th></tr></thead><tbody><tr><td>1. Crie uma conta</td><td>Profissional de marketing/usuário do dashboard da AppsFlyer</td><td>2 horas</td><td> </td></tr><tr><td>2. Adicione o aplicativo à AppsFlyer</td><td>Profissional de marketing/usuário do dashboard da AppsFlyer</td><td>2 horas</td><td> </td></tr><tr><td>3. Integrar o SDK</td><td>Desenvolvedores do aplicativo</td><td>1 dia + 1 semana de testes e iterações</td><td><ul><li> <strong>Recomendado</strong>: integre o SDK da AppsFlyer em um aplicativo de pré-produção para teste.</li><li>O aplicativo de produção deve ser atualizado nas lojas de aplicativos depois que todas as outras tarefas forem concluídas.</li></ul></td></tr><tr><td>4. Migrar dispositivos (opcional)</td><td>Engenheiro de dados</td><td>1-2 semanas</td><td rowspan="2"><ul><li>Considere pausar suas campanhas existentes antes da migração e retome-as depois que a versão do aplicativo for atualizada. </li><li>Considere repetir a migração de dispositivos na data final da migração para garantir uma cobertura completa. </li></ul></td></tr><tr><td>5. Migrar campanhas</td><td>Profissional de marketing/Gerente de UA</td><td>1-3 dias para cada canal de mídia</td></tr><tr><td>6. Configurar relatórios de dados</td><td>Engenheiro de dados</td><td>3-6 semanas</td><td> </td></tr></tbody></table>

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="1. Crie uma conta">

**Para criar uma conta na AppsFlyer**:

1. <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta na AppsFlyer</Anchor>.
2. Adicione usuários de conta com as permissões adequadas

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="3. Adicione o aplicativo">

**Para adicionar seu aplicativo à AppsFlyer**:

1. <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione o aplicativo</Anchor> à AppsFlyer
2. [Opcional] Altere a  <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor>  padrão de 90 dias para alinhar  com a sua definição de usuários ativos.
3. Como parte do assistente de onboarding da AppsFlyer, prepare e envie um e-mail para seu desenvolvedor com instruções e tarefas para a integração do SDK e o mapeamento de eventos no aplicativo.

</Accordion>

<div id="step-3-integrate-the-sdk" />

<Accordion title="3. Integrar o SDK">

O SDK integrado ao aplicativo é a conexão entre o aplicativo e a plataforma da AppsFlyer. Ele relata instalações, aberturas do app, eventos in-app e outros.

**Para fazer a integração do SDK da AppsFlyer**:

1. Verifique se recebeu o e-mail enviado pelo profissional de marketing com instruções e tarefas para a integração do SDK e o mapeamento de eventos no aplicativo.
2. Siga as instruções do e-mail e use o <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">assistente de integração do SDK da AppsFlyer</Anchor> para integrar o SDK da AppsFlyer ao aplicativo.
   * O assistente ajuda o desenvolvedor desde a instalação até o teste bem-sucedido da integração. Ele também orienta o desenvolvedor durante a configuração de eventos in-app e testes da sua transmissão para a AppsFlyer. <Anchor target="_blank" href="/marketers/pt/docs/for-ios-and-android-the-sdk-integration-wizard">Saiba mais sobre o assistente de integração do SDK</Anchor>
   * Veja guias adicionais para desenvolvedores sobre a integração do SDK para <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">Android</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">iOS</Anchor>.
   * Mapeie os eventos in-app que você quiser registrar usando os esquemas da AppsFlyer.  
     Isso pode ser feito via <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">SDK</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Remova o SDK da Adjust.  
   Você pode fazer isso imediatamente e mudar exclusivamente para a AppsFlyer, ou executar os dois SDKs simultaneamente por algumas semanas. Veja mais detalhes sobre essas opções na tabela abaixo.

| Opção | O que acontece depois do  <br />lançamento da versão atualizada do aplicativo? | Impacto |
| --- | --- | --- |
| Remover o SDK da Adjust (recomendado) | Somente a AppsFlyer registra novas instalações e atualiza o número de usuários.  <br />O concorrente ainda mostra eventos realizados pelos usuários, até que os usuários também atualizem o app. | <ul><li>Transição rápida.</li><li>Sem atribuição dupla.</li></ul> |
| Manter o SDK da Adjust por um período de transição | A AppsFlyer e a Adjust atribuem novas instalações e registram eventos. Posteriormente, remova o SDK da Adjust. | <ul><li>A validação de dados é possível. Ou seja, você pode comparar dados da AppsFlyer com os dados da Adjust.</li><li>Atribuição duplicada, que pode causar cobranças repetidas com as ad networks. Veja o exemplo abaixo.</li><li>Maior volume de trabalho.</li></ul> |

4. Depois que todas as outras tarefas nesse artigo de migração forem concluídas, libere a versão do aplicativo com o SDK da AppsFlyer. Novos usuários são atribuídos pela AppsFlyer.    
   **Nota**:
   * Certifique-se de atualizar o aplicativo para iOS, Google Play e outros mercados relevantes fora da loja Android.
   * Seu aplicativo Android pode existir em sites de APK não oficiais, mesmo que você não os conheça (pesquise pelo nome do pacote do seu aplicativo para descobrir se esse é o caso). Os sites de APK levam algum tempo para atualizar para a versão mais recente, portanto podem trazer usuários orgânicos, que instalam versões antigas sem o SDK da AppsFlyer.
   * Os lançamentos de atualizações do aplicativo nas lojas podem levar alguns dias para serem totalmente concluídos. Os usuários que fizerem a instalação durante essa fase ainda podem obter a versão anterior.

</Accordion>

<div id="step-4-migrate-devices-optional" />

<Accordion title="4. Migrar dispositivos — opcional">

A migração de dispositivo é o processo de upload de uma lista de device IDs de usuários existentes (IDFA, IDFV, GAID) na AppsFlyer. (se você não tiver todos os device IDs necessários, entre em contato com seu CSM para que ele possa te orientar no processo de migração usando o CUID.) Você deve realizar esse processo antes de lançar a nova versão do aplicativo, que incluirá o SDK da AppsFlyer. Há duas opções ao migrar dispositivos: migração [atribuída](/docs/migrate-from-adjust-to-appsflyer#attributed-migration) ou [não atribuída](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration).

A migração de dispositivos resolve os problemas de dados relacionados aos usuários existentes do aplicativo, que fizeram o download do app e foram atribuídos pela Adjust. Por exemplo, as cobranças duplicadas da SRN, que ocorrem quando os usuários originalmente atribuídos a uma SRN pela Adjust, e que ainda estão dentro da janela de lookback, são reivindicados pela SRN novamente na AppsFlyer.

<div id="example" />

> 📄 **Exemplo**
>
> * Um novo usuário clica em um anúncio no Facebook e instala seu aplicativo no dia 15 de junho.
> * No dia 24 de junho, o usuário atualiza o aplicativo para a versão com o SDK da AppsFlyer e o inicializa. Para a AppsFlyer, esse é um novo usuário, que precisa ser atribuído em tempo real.
> * A AppsFlyer consulta o Meta ads com o ID do dispositivo do usuário. Como o usuário ainda está dentro da janela de lookback de 28 dias do Meta ads, o Meta ads auto-atribui o usuário. Isso causa uma cobrança dupla para o proprietário do aplicativo em relação ao mesmo usuário.

Depois de migrar os dispositivos, os dados são refletidos na AppsFlyer da seguinte maneira:

* Dados de instalações: assim como as <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window#reinstall">reinstalações</Anchor>, dispositivos migrados não têm dados de instalação. As instalações de dispositivos migrados não são exibidas na AppsFlyer.
* **Dados de eventos e sessões in-app:** são registrados e exibidos como orgânicos para o [método de migração de dispositivo não atribuído](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration) ou são atribuídos ao canal de mídia e campanha, quando o [método atribuído](/docs/migrate-from-adjust-to-appsflyer#attributed-migration) é usado.
* **Retargeting:** eatribuições e reengajamentos são exibidos normalmente.
* **Dados de atividade:** mostrados normalmente.
* **Dados de retenção e de cohort:** dispositivos migrados não têm registros de instalação. Assim, eles não sãp associados a nenhum cohort e não podem ser exibidos nos relatórios de retenção e cohort.

<div id="note" />

> 📘 **Observação:**
>
> Se o aplicativo não for aberto dentro de 180 dias a partir da data de migração, todos os dados do dispositivo migrado serão excluídos. Consequentemente, se o aplicativo for aberto após o período de 180 dias, uma nova instalação será registrada.

**Para migrar dispositivos:**

1. Decida qual população de usuários você deseja migrar. Você pode migrar todos os usuários existentes (o que pode impedir que você acesse dados precisos de reatribuição da AppsFlyer) ou usuários que instalaram seu aplicativo recentemente (o que pode levar a cobranças duplicadas de usuários um pouco mais antigos).  
   **Recomendamos que você migre usuários ativos durante o período da janela de reatribuição atual.** Por exemplo, se o aplicativo tiver uma janela de reatribuição de 90 dias, migre os usuários que tiveram pelo menos uma sessão durante os 90 dias anteriores.
2. [Opcional] Peça ao profissional de marketing/gerente de UA para pausar campanhas de marketing existentes (de SRNs, ad networks não-SRNs, mídias próprias, etc.) até depois da migração do dispositivo.  
   Se você decidir não pausar as campanhas, migre os device IDs que permaneceram no outro fornecedor assim que a versão atualizada do aplicativo com o SDK da AppsFlyer for lançada nas lojas de aplicativos.
3. Prepare um arquivo CSV com base na população de usuários selecionada, usando a estrutura de migração [atribuída](/docs/migrate-from-adjust-to-appsflyer#attributed-migration) ou [não atribuída](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration). <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">Veja um exemplo de CSV</Anchor>
4. Envie o CSV ao seu CSM da AppsFlyer.  
   Seu CSM migrará os device IDs para a AppsFlyer.

</Accordion>

<div id="step-5-migrate-campaigns" />

<Accordion title="5. Migrar campanhas">

Transfira as campanhas de marketing existentes para a AppsFlyer para ativar a atribuição da AppsFlyer, evitando cobranças duplicadas e perda de dados de atribuição.

**Atenção:** você pode optar por migrar apenas algumas campanhas de marketing de cada vez. Nesse caso, você pode segmentar as que deseja migrar por canal de mídia (por exemplo, ad network ou agência), geolocalização ou campanha.

As seções a seguir explicam o que é necessário para ativar a mensuração da AppsFlyer para diferentes tipos de canais de mídia: SRNs, ad networks não SRN, mídias próprias e SKAN.

#### SRNs

As SRNs respondem às parceiras de mensuração mobile (MMPs) quando consultados sobre engajamentos de dispositivos específicos. Se a AppsFlyer e a Adjust consultarem a mesma SRN sobre a mesma instalação, você poderá receber cobranças duplas.

**Para migrar campanhas de SRN**:

* Ative e configure as <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">SRNs</Anchor> relevantes na AppsFlyer.

<div id="note-1" />

> 📘 **Observação:**
>
> * SRNs podem executar várias MMPs (exceto Meta Ads e Twitter).
> * O Meta Ads não corrige eventos in-app duplicados.

<div id="non-srn-ad-networks" />

#### Ad networks que não são SRNs

Os links de atribuição das ad networks registram os engajamentos dos usuários e, posteriormente, são usados para a atribuição desses engajamentos, que se tornam instalações reais.

**Para migrar campanhas de ad networks que não são SRNs**:

1. <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">Ative</Anchor> as ad networks relevantes na AppsFlyer.
2. <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">Gere links de atribuição da AppsFlyer</Anchor> para cada ad network.
3. Troque os links existentes em cada uma das suas campanhas pelos links de atribuição da AppsFlyer.

<div id="owned-media" />

#### Mídia própria

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

**Para migrar seus links da Adjust para links do OneLink da AppsFlyer**:

* Entre em contato com seu CSM, que o ajudará a transformar seus links de mídias própria em links do OneLink de acordo com os canais e ferramentas que você usa atualmente.

#### SKAN

Para a atribuição da SKAdNetwork (SKAN), você deve ter um único SDK para atualizar o valor de conversão. Caso contrário, os dados da SKAN não têm utilidade. Portanto, certifique-se de que, após a migração, apenas o SDK da AppsFlyer poderá atualizar o valor de conversão da SKAN.

<Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">Saiba mais sobre como configurar o valor de conversão da SKAN na AppsFlyer.</Anchor>

</Accordion>

<div id="step-6-set-up-data-reporting" />

<Accordion title="Passo 6: Configurar relatórios de dados">

Você pode obter dados <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-apis">brutos</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/analytics-and-aggregate-reporting-apis">agregados</Anchor> dos relatórios da AppsFlyer usando diversos métodos. Familiarize-se com os métodos e configure aqueles que são relevantes para você.

Os métodos incluem:

* Painéis
* Exportação de relatórios
* API de push
* Extrair API
* Relatório do Data Locker

Antes da migração, seus sistemas armazenam seus dados de atribuição da Adjust de acordo com as estruturas, campos e parâmetros de relatórios que você configurou com ela. Para que a AppsFlyer informe os dados corretamente, você deve adaptar e mapear suas estruturas de relatório atuais para a estrutura, os campos e os parâmetros de relatório da AppsFlyer.

**Para adaptar/mapear suas estruturas de relatório:**

* Entre em contato com seu CSM da AppsFlyer para obter ajuda para adaptar/migrar rapidamente as estruturas de dados dos seus relatórios da Adjust para a AppsFlyer.

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="attributed-migration" />

<Accordion title="Migração atribuída">

Os dispositivos migrados para a AppsFlyer com esse método têm seus eventos in-app e sessões registrados e exibidos de acordo com o canal de mídia relatado pelo fornecedor de atribuição anterior, e de acordo com as políticas de retenção de dados das ad networks.

<div id="attributed-device-migration-csv-structure" />

#### Estrutura CSV de migração de dispositivo atribuído

| Nome da  <br />coluna | A descrição | Obrigatório | Exemplos |
| --- | --- | --- | --- |
| app\_id | App ID exibido no dashboard da AppsFlyer | Yes | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| plataforma | Plataforma do dispositivo: ios ou android | Yes | <ul><li>ios</li><li>Android</li></ul> |
| device\_id | <ul><li>Android: gaid ou android\_id</li><li>iOS: IDFV (recomendado, se disponível) ou IDFA</li><li>Não duplique a mesma combinação de device ID e app ID em múltiplas linhas. Se ocorrer duplicação, a última ocorrência no arquivo será usada.</li></ul> | Yes | <ul><li>**gaid** (letras minúsculas): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id** (letras minúsculas): f35aea8908254891</li><li>**IDFV** (letras maiúsculas): A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (letras maiúsculas): 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android: advertiserId (também compatível com amazon\_aid), android\_id</li><li>iOS:idfa ou idfv</li><li>No momento, outros identificadores, como OAID e IMEI, não são compatíveis.<br />Use a migração não atribuída para usuários Android que não vêm do Google Play.</li></ul> | Yes | <ul><li>advertiserId</li><li>android\_id</li><li>idfa</li><li>idfv</li></ul> |
| install\_time | O tempo de instalação do aplicativo original com o <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor> no formato UTC:  <br />**aaaa-mm-ddTHH:MM:SS.SSS** | Sem | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>Ou:<ul><li>ID de parceiro da AppsFlyer</li><li>Canal de mídia personalizada (não pode ser um ID de parceiro).</li></ul></li><li>Para obter a lista de IDs de parceiros, conforme exigido pela AppsFlyer:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">Ative todos os parceiros integrados relevantes.</Anchor></li><li>Execute a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">Get active integrations API</Anchor> para obter uma lista de todas as integrações ativas.</li><li>Use o **media\_source\_name** da API como o valor **media\_source** no CSV.</li><li>Exceções:<ul><li>Para o Apple Search Ads use **Apple Search Ads**.</li><li>Para Twitter, use **twitter**.</li></ul></li></ul></li><li>Formato: Os valores fazem distinção entre maiúsculas e minúsculas.</li></ul> | Yes | Não orgânico: facebook\_int, googleadwords\_int<br /><br />Orgânico: orgânico |
| integrated\_partner | <ul><li>Indica se o canal de mídia é um parceiro integrado ou não. Ou seja, canal de mídia orgânica ou personalizada.</li><li>Formato: Os valores fazem distinção entre maiúsculas e minúsculas.</li></ul> | Yes | <ul><li>Sim</li><li>no (se media\_source for personalizado)</li></ul> |
| campanha | Para obter detalhes de atribuição mais granulares, forneça o nome da campanha original.<br /><br />Formato: Sequência de caracteres | Sem |  |
| campaign\_id | Para obter detalhes de atribuição mais granulares, forneça o ID da campanha original.<br /><br />Formato: Formato: string sem espaços | Sem |  |

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
| 1 | App ID + IDFA/GAID/IDFV | <ul><li>Se todos os usuários Android tiverem identificadores GAID.</li><li>Somente usuários do iOS</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png)](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png) |
| 2 | App ID + Device ID + tipo do Device ID | <ul><li>Se alguns dos seus usuários Android tiverem apenas IMEI ou Android ID, mas não GAID (mercados fora da loja, versões Android anteriores à versão 4.4.2).</li><li>O Android ID precisa ter um formato hexadecimal.</li></ul>**Observação**:<ul><li>Use as strings específicas para a coluna de **tipo de ID**: advertiserId (também compatível com amazon\_aid), idfa, idfv, android\_id, imei.</li><li>Se você usar android\_id ou imei e, posteriormente, a AppsFlyer receber um identificador melhor, uma nova atribuição poderá ser registrada.</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png)](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png) |

**Regras de arquivo CSV:**

* O arquivo CSV pode conter dispositivos de usuários de vários aplicativos.
* Cada linha contém um device ID único por aplicativo. Etapa 1:
* Dependendo da opção de estrutura de arquivo escolhida, as colunas de arquivo devem ser as seguintes (na ordem listada):
  * Opção 1: app\_id, device\_id
  * Opção 2: app\_id, device\_id, id\_type
* App IDs em letras minúsculas.
* Identificadores Android em letras minúsculas.
* IDFA/IDFV em letras maiúsculas.
* Até 25 milhões de linhas permitidas

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">Veja um exemplo de CSV</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=sobre-a-migra%C3%A7%C3%A3o-para-a-appsflyer 01H8EDSTP8N4GZJQ5J609C3DHM=sobre-a-migra%C3%A7%C3%A3o-para-a-appsflyer compare-measurement-between-appsflyer-and-adjust=compare-a-mensura%C3%A7%C3%A3o-entre-a-appsflyer-e-a-adjust h_01HQJ10ZFJR43KBYMD9A07CJ99=compare-a-mensura%C3%A7%C3%A3o-entre-a-appsflyer-e-a-adjust tasks=tarefas 01H8EDSTP8YGDZBPEY1976JP8C=tarefas 01JE3EC4C847ZEK769Y9G237KG=step-1-create-an-appsflyer-account 01JE3EC4C9V83D0V46EJK49JZ2=step-2-add-your-app 01JE3EC4CAKY4FQBPPZSJFP5V5=step-3-integrate-the-sdk step-4-migrate-devices%E2%80%94optional=step-4-migrate-devices-optional 01JE3EC4CPT4KAER27C8C0DHH7=step-4-migrate-devices-optional 01H8EDSTP93QJA4XZB6TDWWH1V=exemplo 01JA2CAMW3HCHC4B9FX7517FJ6=observa%C3%A7%C3%A3o 01JE3EJ5DVXF1VT28ZCGR7SMF3=step-5-migrate-campaigns 01JE3EXVNRMA2MFVPSJZ2RMR09=srns 01H8EDSTP9ZGMHSM44BWGF1FJN=observa%C3%A7%C3%A3o-1 nonsrn-ad-networks=ad-networks-que-n%C3%A3o-s%C3%A3o-srns 01JE3EXVNTWK4ZJS55WXHFKSMX=ad-networks-que-n%C3%A3o-s%C3%A3o-srns owned-media=m%C3%ADdia-pr%C3%B3pria 01JE3EXVNTS4FVXN370G1CR8Z9=m%C3%ADdia-pr%C3%B3pria 01JE3EXVP4TSMGSZD4B460RSQA=skan 01JE3F6VXDG9MDCVWN81RSHXVG=step-6-set-up-data-reporting additional-information=informa%C3%A7%C3%B5es-adicionais 01JE3E5VHV2WCFWABC9FYQW3VG=informa%C3%A7%C3%B5es-adicionais 01JE3FG6K95QT60C36R88WGDG4=attributed-migration attributed-device-migration-csv-structure=estrutura-csv-de-migra%C3%A7%C3%A3o-de-dispositivo-atribu%C3%ADdo 01H8EDSTP9HABKEZJXMB84CDDE=estrutura-csv-de-migra%C3%A7%C3%A3o-de-dispositivo-atribu%C3%ADdo 01JE3FG6MKNJMTHSR5B2ZMQP1K=nonattributed-migration nonattributed-device-migration-csv-file-structure=estrutura-de-arquivo-csv-de-migra%C3%A7%C3%A3o-de-dispositivos-n%C3%A3o-atribu%C3%ADdos 01H8EDSTP9AFDMQS6BPQJY19ZH=estrutura-de-arquivo-csv-de-migra%C3%A7%C3%A3o-de-dispositivos-n%C3%A3o-atribu%C3%ADdos" />

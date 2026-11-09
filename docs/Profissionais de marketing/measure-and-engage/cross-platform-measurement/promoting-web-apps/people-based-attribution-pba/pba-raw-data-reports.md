---
title: Relatórios de dados brutos do PBA
metadata:
  keywords:
    - Data Locker
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-07-01T07:53:57Z'
  edited_at: '2026-08-19T00:23:02Z'
  id: 360001917778
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360001917778
---
> **Visão geral:** os relatórios de dados brutos do PBA estão disponíveis via Data Locker.

<div id="pba-raw-data-reports" />

## Relatórios de dados brutos do PBA

Use os relatórios de dados brutos do PBA para analisar as jornadas e ações do usuário.

<div id="report-descriptions" />

### Descrições do relatório

Tópicos do relatório de dados brutos do PBA

| Tópico do relatório de dados brutos | Descrição |
| --- | --- |
| <span id="website-visits"></span>[Visitas ao site](#visitas%20e%20eventos%20do%20site) | <ul><li>Visitas ao site.</li><li>Mensure a exposição e o engajamento do usuário com campanhas de tráfego da web.</li></ul> |
| <span id="website-events"></span><Anchor target="_blank" href="/marketers/pt/docs/pba-website-attribution-dashboard">Eventos do site</Anchor> | <ul><li>Contêm as ações realizadas pelos visitantes do site, como inscrição ou compra.</li><li>Os eventos são atribuídos à última visita não direta à web ocorrida nos últimos 30 dias.</li><li>Os parâmetros de atribuição associados ao evento podem incluir fonte de mídia, canal de mídia, campanha e assim por diante.</li><li>Use esses parâmetros para otimizar seus esforços de marketing.</li><li>Analise o comportamento do usuário por fonte de mídia.</li><li>Os valores desses campos são determinados por meio da visita atribuída usando as <Anchor target="_blank" href="/marketers/pt/docs/pba-media-source-attribution-rules">regras de atribuição de fonte de mídia do PBA.</Anchor></li><li>A intenção é associar eventos a uma visita específica ao site e não a uma visualização de página específica.</li><li>Use este tópico para descobrir quais fontes e campanhas impulsionam os usuários e quais ações os usuários realizam.</li></ul> |

<div id="raw-data-report-fields" />

## Campos do relatório de dados brutos

<div id="website-visits-and-website-events" />

<Accordion title="Visitas ao site e eventos do site">

<div id="sample-reports" />

#### Relatórios de amostra

* Eventos no site: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=1096347999&single=true&output=csv">CSV</Anchor>
* Visitas ao site: [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=432734495&single=true&output=csv)

Os campos de dados brutos são preenchidos em parte a partir de dados originados no link de atribuição do usuário do aplicativo mobile e no evento de instalação do aplicativo.

[Faça o download da lista de campos como um arquivo CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmRBeUQS-xeiv069vIgnfBoJW8Wfl1ojv0rAK-pcOlAzNveG1lqvExVdhWfgCKIpJxczWksUiHjSa3/pub?gid=0&single=true&output=csv)

<div id="field-list-website-visits-and-website-events-report" />

#### Visitas ao site da lista de campos e relatório de eventos do site:

| Nome do campo | Descrição | Formato | Exemplo |
| --- | --- | --- | --- |
| advertising\_id | ID de publicidade (GAID) | Sequência de caracteres | 7fzzz3fa-8bad-46c9-bb03-fffffffffffffffffffffffff |
| af\_web\_id | ID de cookie enviado do SDK da web | Sequência de caracteres | 68972980-58f9-4ca6-8743-c0d633364b6d |
| amazon\_aid | ID de publicidade da Amazon Fire TV | Sequência de caracteres | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| android\_id | ID do dispositivo Android | Sequência de caracteres | 68999980-58f9-4ca6-8743-c0d633364b6d |
| ativado | O ID do aplicativo mais recente instalado | Sequência de caracteres | id123456789 |
| ativado | O nome do aplicativo mais recente | Sequência de caracteres | Meu aplicativo |
| app\_version | A versão mais recente do aplicativo | Sequência de caracteres | 6.32 |
| appsflyer\_id | ID da AppsFlyer (instalação) | Sequência de caracteres | 1594825729709-5655157112349378588 |
| attributed\_touch\_time | Em visitas na web, o carimbo de data/hora da visita na web Em eventos da web, o carimbo de data/hora da visita atribuída na web | aaaa-mm-dd hh:mm:ss | 9/17/2020 0:09:25 |
| tipo\_de\_toque\_atribuído | Tipo do touchpoint. Atualmente, sempre definido para visita ao site. | Sequência de caracteres | Visita web |
| bundle\_id | ID do bundle PBA | Sequência de caracteres | 048db9bf-97r7-4m2f-919b-607b7kk806d0 |
| campanha | Atribuído à visita ao site | Sequência de caracteres | Campanha de verão |
| id\_da\_campanha | Atribuído à visita ao site | Sequência de caracteres | 12343425 |
| cidade | Resolvido usando o endereço IP | Sequência de caracteres | Spring Valley |
| código\_país | Resolvido usando o endereço IP | Sequência de caracteres | EUA |
| customer\_user\_  <br />id | Identificador de Usuário do Cliente (CUID) | Sequência de caracteres | 5a8771ecbb986ABC |
| device\_type | O tipo de dispositivo | Sequência de caracteres | Desktop |
| dma | Resolvido usando o endereço IP | Sequência de caracteres | 501 |
| nome\_do\_evento | No relatório de visita ao site: sempre visita ao site. No relatório de eventos do site: eventName enviado pelo SDK da web. | Sequência de caracteres | compra |
| event\_revenue | Valor da receita do evento na moeda de compra | Sequência de caracteres | 199.99 |
| event\_currency | código de moeda de 3 dígitos do event\_revenue | Sequência de caracteres | USD, ZAR, EUR |
| event\_revenue\_usd | event\_revenue convertido para USD | Sequência de caracteres | 57.46 |
| event\_source | SDK web ou servidor para servidor | Sequência de caracteres | SDK web, S2S |
| event\_time | Visitas ao site: hora da visita Evento no site: hora do evento | aaaa-mm-dd hh:mm:ss | 9/17/2020 0:09:25 |
| event\_type | O seguinte: evento padrão, evento de conversão, visita ao site | Sequência de caracteres | evento de conversão |
| event\_url | URL da página da web na qual o evento ocorreu (é igual à URL original nas visitas ao site) | Sequência de caracteres | http://www.brandpit.com/checkout |
| event\_value | Eventos no site: detalhes do valor do evento contidos em um JSON. Visitas ao site: sempre nulo | JSON | `{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}` |
| idfa | Identificador do anúncio | Sequência de caracteres | A56B9887-FEBA-458C-BEFC-C891F9DF7681 |
| idfv | Identificador do anúncio | Sequência de caracteres | EBC2F523-B1E5-4484-A4C8-ADC32DC7C23D |
| imei | Identificador do dispositivo | Sequência de caracteres | 3532211234 |
| install\_time | O horário de instalação mais recente do aplicativo | aaaa-mm-dd hh:mm:ss | 9/17/2020 0:09:25 |
| ip | Endereço IP do visitante | Sequência de caracteres | 24.7.104.115 |
| language | Relatado pelo agente do usuário | Sequência de caracteres | Inglês |
| media\_channel | Atribuído à visita ao site | Sequência de caracteres | Anúncio |
| fonte\_de\_mídia | Atribuído à visita ao site | Sequência de caracteres | googleadwords\_int |
| media\_type | Atribuído à visita ao site | Sequência de caracteres | Paga |
| OAID | Identificador do anúncio | Sequência de caracteres | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| original\_url | Endereço URL redirecionando o usuário para o site na visita atribuída ao site | Sequência de caracteres | https://www.brandpitt.com/signin?utm_source=Googleg&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld |
| platforma | A plataforma | Sequência de caracteres | macOS |
| postal\_code | Resolvido usando o endereço IP | Sequência de caracteres | 10977 |
| query\_params | Parâmetros de consulta no URL de redirecionamento (após o ?) Parâmetros de consulta no URL de redirecionamento (após o ?) Parâmetros de consulta na URL de redirecionamento (após o '?') Exwmplo: https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes Se a URL não tiver parâmetros de consulta, o valor será nulo | JSON | `{"c":"summer",af_siteid":"publisher",af_sub1":helloworld",af_keywords":"shoes","utm_source":"Google","utm_campaign":"cool","utm_term":"shoes"}` |
| referrer | Referenciador do documento HTTP da visita atribuída ao site | Sequência de caracteres | https://www.google.com/ |
| Região | Resolvido usando o endereço IP | Sequência de caracteres | NA |
| Estado | Resolvido usando o endereço IP | Sequência de caracteres | NY |

</Accordion>

<div id="field-release-notes" />

<Accordion title="Notas de versão">

| Data | Relatório | Mudança |
| --- | --- | --- |
| 17/01/2020 | Eventos do site<br /><br />Visitas ao site | Os nomes e a estrutura do relatório são alterados:<ul><li>Touchpoints da web substituídos por **Visitas ao site**</li><li>Eventos da web substituídos por **Eventos ao site**</li></ul> |
| 04/10/2020 | web-to-app | Campos adicionados:<ul><li>mobile\_campaign\_id</li><li>web\_campaign\_id</li></ul> |

</Accordion>

<div id="procedures" />

### Procedimentos

<div id="setting-up-pba-reports-in-data-locker" />

<Accordion title="Configurando relatórios de PBA no Data Locker">

* Os relatórios de PBA são registrados diariamente no Data Locker na pasta h=23 para eventos que ocorrem em um determinado dia.
* Os dados não podem ser gravados retroativamente.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Para ativar os relatórios do PBA, um administrador de conta deve configurar o Data Locker:**

1. Vá para **Integração** > **Data Locker**.
2. Selecione todos os relatórios na seção People-Based Attribution.
3. Clique em **Salvar configuração**.

Para fazer download de relatórios, consulte <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Acessando relatórios do Data Locker</Anchor>.

Os relatórios de dados brutos PBA do **Data Locker** são disponibilizados na pasta h=23.

Exemplo: t=website\_events/dt=2020-11-26/h=23

</Accordion>

<div id="combining-pba-and-mobile-data" />

<Accordion title="Combinando os dados de PBA e dados mobile">

Os dados refletem os usuários com maior probabilidade de interagir com o aplicativo mobile e o site.

Combine dados de aplicativos mobile e de sites.

**Solução**:

* Combinar relatórios usando o <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">ID de usuário do cliente</Anchor> (CUID)
  * Use o mesmo CUID para mobile e <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid">web</Anchor> e combine relatórios usando o CUID como chave.
  * Depois combine relatórios usando o campo CUID
* Identificação do usuário da plataforma cruzada do PBA:
  * O PBA pode determinar que um usuário da web e um usuário mobile são a mesma pessoa.
  * Nesse caso, os relatórios da web com o PBA incluem um ID de anúncios mobile: ID de anúncios do Android, IDFA do iOS, OAID ou ID de anúncios da Amazon.
  * Em seguida, combine relatórios mobile e da web com base no ID de anúncios mobile.

<div id="use-cases-for-pba-and-mobile" />

#### **Casos de uso para PBA e dispositivos mobile**

Combine dados mobile e da web para ver a atividade do usuário em várias plataformas e dispositivos. Os dados combinados permitem que você:

* Acompanhe a jornada do usuário pelas propriedades digitais da sua marca
* Analise o comportamento do usuário em cada plataforma
* Considere qual plataforma recebe engajamento do usuário
* Veja qual plataforma produz mais conversões
* Mensure os seus esforços para enviar os seus usuários da web para o mobile

</Accordion>

<div id="application-note-downloading-and-combining-data-locker-files" />

<Accordion title="Nota do aplicativo - fazendo o download e combinando arquivos do Data Locker">

Os dados brutos do PBA estão disponíveis no Data Locker. Para um determinado relatório, os dados estão contidos na pasta h=23 do tipo de relatório e consistem em vários arquivos compactados.

Use este procedimento para:

* Copiar os arquivos do Data Locker usando o Cyber-Duck ou qualquer outra ferramenta para copiar arquivos do S3.
* Combinar os arquivos em um único arquivo CSV usando [Q.](http://harelba.github.io/q/)

**Copiando dados do PBA do Data Locker**

**Antes de começar**:

* <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#cyberduck">Instale e configure o Cyber-Duck</Anchor>.

**Para copiar dados usando o Cyber Duck:**

1. Abrir Cyberduck   
   A lista de tipos de dados disponíveis é exibida.

   <Image align="center" alt="Duck_us-en.jpg" src="https://files.readme.io/b8e93ad9423605b3247531d276b9c2d45abd4ea044dde29ee177f4d71b738e9d-360008254377.jpg" />
2. **Clique duas vezes** em um tipo de relatório PBA e escolha entre web\_events, web\_to\_app ou web\_touch\_points.  
   A lista de datas de relatório disponíveis é exibida.
3. **Clique com o botão direito** em uma determinada data.
4. Selecione **Fazer download para um local específico e preencha o local.**   
   O download dos arquivos é realizado.
5. Repita as etapas acima para copiar dados de outros tipos de relatórios. Cada tipo de relatório e data devem ser armazenados em um diretório diferente no seu computador.

**Criando um arquivo CSV combinado:**

**Antes de começar:**

Instale o <Anchor target="_blank" href="http://harelba.github.io/q/">Q</Anchor> no seu computador.

**Para combinar os dados em um arquivo CSV usando Q**:

1. Usando a linha de comando/maс terminal, vá para o diretório que contém os dados.
2. Use o comando a seguir para combinar os arquivos compactados em um único arquivo com o nome pbadata.csv.  
   Observação: o símbolo ~ representa o caminho/pasta inicial onde o comando Q está localizado em seu computador. Talvez seja necessário incluir o caminho completo para invocar o comando.

   ```
   ~q "SELECT * from part*.gz" -d , -H -z -O >pbadata.csv
   ```
3. Abra o arquivo usando o Excel ou qualquer outra ferramenta

</Accordion>

<div data-zendesk-anchors="pba-raw-data-reports=relat%C3%B3rios-de-dados-brutos-do-pba h_01HKW341NVTCP4FY5G4TC94MZY=relat%C3%B3rios-de-dados-brutos-do-pba report-descriptions=descri%C3%A7%C3%B5es-do-relat%C3%B3rio h_01HKW341NVC83ZC3HCH86QBJYG=descri%C3%A7%C3%B5es-do-relat%C3%B3rio rawdata-report-fields=campos-do-relat%C3%B3rio-de-dados-brutos h_01HKW341NVNYM1AGFC8GHV7VR2=campos-do-relat%C3%B3rio-de-dados-brutos h_01EQD0FBKE0J71MA9MNETEZAMA=website-visits-and-website-events sample-reports=relat%C3%B3rios-de-amostra h_01HKW341NVX51NQFAA79BD7MF3=relat%C3%B3rios-de-amostra website-visits-events=visitas-ao-site-da-lista-de-campos-e-relat%C3%B3rio-de-eventos-do-site field-list-website-visits-and-website-events-report=visitas-ao-site-da-lista-de-campos-e-relat%C3%B3rio-de-eventos-do-site h_01J53BGNDSQCCFV1VQA8EV50GR=visitas-ao-site-da-lista-de-campos-e-relat%C3%B3rio-de-eventos-do-site h_01HKW341NW43C07KYAN3WCV0WY=field-release-notes procedures=procedimentos h_01HKW341NWXQ19ZB5QXZK84VMQ=procedimentos h_01HKW341NXR3MP2T99AAHNH3SG=setting-up-pba-reports-in-data-locker h_01HKW341NX2S093V1Y8YVY45VP=combining-pba-and-mobile-data use-cases-for-pba-and-mobile=casos-de-uso-para-pba-e-dispositivos-mobile h_01HKW341NXTXX4FJ2ZZQFZ2V85=casos-de-uso-para-pba-e-dispositivos-mobile h_01HKW341NX95YBGHZZG8KZC3KX=application-note-downloading-and-combining-data-locker-files" />

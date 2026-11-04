---
title: Política de identificadores de utilizador para públicos-alvo
metadata:
  keywords:
    - IDFA
    - Audiences
    - Advertisers
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
  created_at: '2020-12-23T15:39:55Z'
  edited_at: '2026-08-19T00:35:29Z'
  id: 360016791118
  locale: pt
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/pt/articles/360016791118
---
> **Visão Geral:** Configure a sua política de identificadores de utilizador para exercer controlo **ao nível da conta** sobre os dados que os públicos-alvo partilham com os parceiros.

<div id="about" />

## Sobre

Após definir um público, o AppsFlyer Audiences envia os identificadores dos membros desse público para os <Anchor target="_blank" href="/marketers/pt/docs/audiences-partner-connections">parceiros publicitários</Anchor> escolhidos. Isto possibilita que exibam os seus anúncios apenas para esses utilizadores.

Para assegurar a conformidade com os requisitos de privacidade do iOS 14.5, assim como de outras considerações de privacidade do utilizador, o Audiences oferece controlo total sobre quais identificadores são partilhados com parceiros:

* ao nível da conta
* ao nível da ligação com o parceiro

Este artigo descreve o processo para gerir a política de identificadores de utilizador ao nível da conta. Para mais informações sobre a gestão dos identificadores partilhados ao nível da ligação com o parceiro, consulte a secção <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#manage-connections">Gerir ligações</Anchor> do guia de Públicos-alvo.

<div id="user-identifiers" />

## Identificadores de utilizador

Esta secção descreve os identificadores que podem ser partilhados com parceiros.

<div id="shared-identifiers" />

<Accordion title="Configurações predefinidas do identificador">

Por padrão, o Audiences partilha os seguintes identificadores com os parceiros:

* **iOS:** IDFA (no iOS 14.5 e superior, disponível apenas se o utilizador permitir a partilha deste identificador)
* Android: GAID

Alguns parceiros de publicidade também suportam os seguintes identificadores:

* E-mail (com hash)
* Número de telefone (com hash)
* OAID e IMEI (relevantes apenas para lojas Android fora do Google Play)

Certos outros identificadores adicionais podem ser úteis para processos internos (como CRM ou análise de dados):

* CLIQUE
* IDFV (apenas para iOS)

Para mais informações (incluindo os requisitos para usar identificadores específicos no AppsFlyer), consulte a tabela de identificadores abaixo.

</Accordion>

<div id="identifiers-table" />

<Accordion title="Tabela de identificadores">

<table><thead><tr><th>Identificador</th><th>Sistema Operativo</th><th>Partilha por defeito?</th><th>Requisitos para utilização\/<br/>Notas<br/><br/> </th></tr></thead><tbody><tr><td>IDFA</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>Consulte a nota<br/>(à direita)</td><td>Por defeito, apenas é partilhado para utilizadores com <a href="./audiences-user-identifier-policy#regulamentos-de-privacidade">estado ATT: autorizado ou não determinado</a> </td></tr><tr><td>GAID</td><td>com o Android</td><td>S</td><td>Nenhum</td></tr><tr><td>OAID</td><td>Android<br/>(fora do Google Play)</td><td>Não</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">Deve ser configurado</a> no SDK do AppsFlyer</td></tr><tr><td>IMEI</td><td>Android<br/>(fora do Google Play)</td><td>Não</td><td> <a href="./android-oaid-implementation-in-the-sdk" target="_blank">Deve ser configurado</a> no SDK do AppsFlyer</td></tr><tr><td>CLIQUE</td><td>iOS<br/>Android</td><td>Não</td><td><ul><li>Gerado pelo anunciante e <a href="./customer-user-id-field-cuid" target="_blank">reportado à AppsFlyer</a> através das APIs ou SDKs da AppsFlyer.</li><li>Não é partilhado com parceiros de publicidade, mas pode ser útil para finalidades internas.</li><li>Sujeito aos <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Termos de Utilização de Identificadores Adicionais</a>. </li></ul></td></tr><tr><td>IDFV</td><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>Não</td><td><ul><li>Não é partilhado com parceiros de publicidade, mas pode ser útil para finalidades internas.</li><li>Sujeito aos <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Termos de Utilização de Identificadores Adicionais</a>. </li></ul></td></tr><tr><td>E-mail (com hash)</td><td>iOS<br/>Android</td><td>Não</td><td rowspan="2"><ul><li> <a href="./audiences-configure-additional-identifiers-for-partner-audience-creation" target="_blank">Deve ser configurado</a> através do <span>SDK da AppsFlyer ou da API S2S-mobile</span>.</li><li>Deve ser encriptado com hashing SHA256.</li><li>Sujeito aos <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">Termos de Utilização de Identificadores Adicionais</a>. </li></ul></td></tr><tr><td>Número de telefone (com hash)</td><td>iOS<br/>Android</td><td>Não</td></tr></tbody></table>

</Accordion>

<div id="setting-account-level-user-identifier-policy" />

## Configurar a política de identificadores de utilizador ao nível da conta.

A política de identificadores de utilizador só pode ser definida por um utilizador administrador.

**Para definir ou modificar a sua política, siga estes passos:**

1. Na AppsFlyer, no menu lateral, selecione **Envolver** > **Públicos-alvo**.
2. Clique no ícone de definições (engrenagem) no canto superior direito.
3. Na janela **Política de Identificadores de Utilizador**, selecione as definições que estão de acordo com as políticas de privacidade da sua organização.
   * Se optar por permitir a partilha de identificadores diferentes de IDFA, GAID, OAID e IMEI, deve primeiro ler e aceitar os [Termos de Utilização de Identificadores Adicionais.](https://support.appsflyer.com/hc/article_attachments/360017900558)
   * Se decidir proibir identificadores enviados por ligações de parceiros existentes, terá de confirmar se pretende interromper o carregamento desses identificadores.
4. Clique em **Guardar.**

<div id="ios" />

<div id="privacy-regulations" />

## Regulamentos de Privacidade

Esta secção descreve os regulamentos de privacidade que afetam a partilha de identificadores de utilizador.

<Accordion title="/docs/ctv-pc-and-console-platform-attribution-concepts">

A partir da versão 14.5, o iOS exige que cada aplicação ofereça ao utilizador a opção de permitir ou proibir a partilha do identificador de dispositivo IDFA para fins publicitários (App Tracking Transparency). O facto de um utilizador ter visto e respondido a esta opção (a "caixa de diálogo de consentimento ATT") determina o seu <Anchor target="_blank" href="/marketers/pt/docs/att-implications-ios-14-and-deprecation-of-lat">estado ATT.</Anchor>

As opções de política de públicos-alvo para a partilha de identificadores no iOS baseiam-se no estado ATT mais recente do utilizador. As suas opções de partilha são as seguintes:

| Opção de política do utilizador | Estado ATT correspondente |
| --- | --- |
| Nunca enviar | Este identificador não é enviado aos parceiros |
| Estado ATT: apenas autorizado | O identificador é enviado se o estado ATT mais recente for **autorizado** ou **af\_autorizado** |
| Estado ATT: autorizado ou não determinado | O identificador é enviado se o estado ATT mais recente for **autorizado**, **af\_authorized**, **não\_determinado** ou **af\_unavailable**  <br />  <br />*Opção padrão para o IDFA, com o lançamento do iOS 14.5 da Apple* |
| Enviar sempre | O identificador é enviado independentemente do estado ATT. Assegure-se de cumprir os termos de uso da sua aplicação.  <br />  <br />*Opção indisponível para IDFA* |

**Nota:** Os públicos tratam o estado ATT de um novo utilizador como **não determinado** até que este veja e responda ao diálogo de consentimento ATT.

Para definições detalhadas do estado ATT, consulte:

* <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">Definições de estado ATT da Apple</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/att-implications-ios-14-and-deprecation-of-lat#valores-att">Definições de estado ATT da AppsFlyer</Anchor> (af\_authorized, af\_unavailable)

Além disso, todos os utilizadores do Espaço Económico Europeu (EEE) estão sujeitos à aplicação da [Lei dos Mercados Digitais (DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act) pela Google.

</Accordion>

<div id="android" />

<Accordion title="com o Android">

Os utilizadores de Android do Espaço Económico Europeu (EEE) são sujeitos à aplicação da [Lei dos Mercados Digitais (DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act) pela Google.

</Accordion>

<div id="eu-digital-markets-act" />

<Accordion title="Lei dos Mercados Digitais da UE">

Como parte da implementação da Lei dos Mercados Digitais (DMA) pela Google em 6 de março de 2024, a Google está a atualizar a sua política de consentimento para utilizadores da UE. Como parceiro de atribuição de aplicações da Google, a AppsFlyer está a efetuar as alterações necessárias para cumprir os requisitos das suas políticas, garantindo que os anunciantes maximizam o valor dos seus canais de marketing do Google Ads. <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">Saiba mais</Anchor>

**Assim afetarão as mudanças os Públicos:**

* **Novo SDK da AppsFlyer**  
  O mais recente SDK da AppsFlyer recolherá o consentimento do utilizador de proprietários de aplicações do <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">Espaço Económico Europeu (EEE)</Anchor> para que os dados possam ser partilhados com a Google. Para os públicos criados na AppsFlyer (como públicos personalizados e sugeridos), as informações de consentimento recolhidas pelo SDK serão automaticamente partilhadas com o Audiences e, posteriormente, com o Google. Assim que atualizar para a versão mais recente do SDK, este processo ocorrerá automaticamente.
* **Audiências conectadas ao Google**
  * **Consentimento concedido** - A AppsFlyer enviará os dispositivos dos utilizadores do EEE que deram consentimento para partilhar as suas informações com o Google.
  * **Consentimento negado** - A AppsFlyer não enviará os dispositivos dos utilizadores do EEE que recusaram o consentimento para partilhar as suas informações com o Google.
  * **Consentimento desconhecido** - A AppsFlyer enviará os dispositivos dos utilizadores do EEE que não concederam nem negaram o consentimento como "Não especificado". O Google provavelmente não os aceitará para inclusão na sua audiência.  

    Para mais pormenores, consulte as <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">FAQ</Anchor> do Google.
* **Audiências existentes**  
  Todos os dispositivos que já faziam parte de uma audiência no Google antes de 6 de março de 2024 não serão afetados e continuarão a integrar a audiência. Apenas novas audiências ou novos dispositivos do EEE adicionados a uma audiência existente serão enviados para o Google com consentimento.
* **Tamanho da carga da audiência**  
  O tamanho estimado e real das cargas da audiência pode ser afetado, dependendo do número de utilizadores que concedem ou recusam o consentimento.
* #### <span id="importing-audiences"></span>**Importação de audiências**

  * **Importar audiência padrão** - A AppsFlyer adicionará os dados de consentimento que recolher do SDK da AppsFlyer e removerá dispositivos sem consentimento ou não especificados antes de os enviar para o Google.
  * **Importar audiência "como está"** - Ao importar uma audiência "como está" via <Anchor target="_blank" href="/marketers/pt/docs/audiences-import-audience-segments-from-internal-systems#import-a-csv-file">CSV</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/audiences-import-audience-segments-from-internal-systems#use-the-import-audience-api">API</Anchor>, será necessário adicionar dois campos de consentimento adicionais. Esses campos incluem:

| Campo AppsFlyer (1) | Campo Google (2) | Valores | Explicação do campo |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | personalização\_de\_anúncio | verdadeiro/falso | O utilizador deu consentimento à Google para usar os seus dados para publicidade personalizada? |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | dados\_do\_utilizador\_anúncio | verdadeiro/falso | O utilizador deu consentimento para enviar os seus dados de utilizador ao Google? |

Se os campos de consentimento não forem preenchidos com valores, serão enviados para o Google como "Não especificado".

<div id="note" />

> 📘 **Nota**
>
> A aplicação da Lei dos Mercados Digitais (DMA) pelo Google aplica-se tanto às plataformas Android como iOS.

</Accordion>

<div data-zendesk-anchors="background=sobre h_01HKA2FS9VBCSV8FP8FH79H4R0=sobre user-identifiers=identificadores-de-utilizador h_01HKA2FS9VSVJD54R14GC7G0P4=identificadores-de-utilizador h_01HNZH99Z8NA9607VHSYH5XVW0=shared-identifiers h_01HKA2FS9V1KBK9BJAJ63FP6CV=identifiers-table setting-accountlevel-user-identifier-policy=configurar-a-pol%C3%ADtica-de-identificadores-de-utilizador-ao-n%C3%ADvel-da-conta h_01HKA2FS9WNGGRP3NX5NKV15SK=configurar-a-pol%C3%ADtica-de-identificadores-de-utilizador-ao-n%C3%ADvel-da-conta user-identifier-policy-options=regulamentos-de-privacidade h_01HKA2FS9W5NSKKRK2VCZARG15=regulamentos-de-privacidade ios=regulamentos-de-privacidade h_01HNZJ1ET6F87AHHVQK17QHZDD=regulamentos-de-privacidade h_01HNZJ1ET67JQQCPYSM3H6Y9VW=android h_01HNZN8MWETDCMGWKJ0MMM8JK4=eu-digital-markets-act importing-audiences=importa%C3%A7%C3%A3o-de-audi%C3%AAncias h_01HPGV1GYT8DW0GYWTC031TNVH=importa%C3%A7%C3%A3o-de-audi%C3%AAncias h_01HNZEAJT00KKEBDPR7FD0TJNR=nota" />

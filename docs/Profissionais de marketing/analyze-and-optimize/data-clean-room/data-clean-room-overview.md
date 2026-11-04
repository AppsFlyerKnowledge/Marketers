---
title: Dashboard de visão geral — Data Clean Room
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-08T14:47:36Z'
  edited_at: '2026-08-18T00:06:01Z'
  id: 4626852381713
  locale: pt
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/pt/articles/4626852381713
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**![privacy_cloud_logo.png](https://files.readme.io/5862beb63a4b22f68fc230f89c3faa260a15ab40e1defa70c59604d5a81e759d-5583061038225.png)**

> **Visão geral:** enriqueça seus dados no nível do usuário, combinando-os com os dados de atribuição da AppsFlyer para criar relatórios agregados e obter insights valiosos.

<div id="introduction" />

## Introdução

Ao longo da história, o ecossistema de marketing mobile sempre usou dados no nível do usuário para gerar insights e otimizar campanhas publicitárias:

1. Os canais de mídia forneciam dados no nível do usuário para fornecedores de mensuração (como a AppsFlyer), que usavam esses dados para atribuição e, depois, os compartilhavam com os anunciantes.
2. Os anunciantes combinavam essas informações com seus próprios dados no nível do usuário (de seus sistemas de BI ou CRM, por exemplo), faziam análises e agrupavam esses dados para obter os insights agregados necessários para otimizar suas campanhas.

Com a ascensão de novas políticas de privacidade, o acesso a esses dados se tornou bastante restrito:

1. Os canais de mídia fornecem dados no nível do usuário para fornecedores de mensuração (como a AppsFlyer), que usam essas informações para atribuição; **no entanto, agora eles não podem mais enviar esses dados para os anunciantes.**
2. Isso faz com que os anunciantes não consigam fazer a correspondência com seus próprios dados no nível do usuário, como eles faziam no passado – impedindo-os de acessar os insights necessários.

Esse é justamente o "problema" que o Data Clean Room (DCR) da AppsFlyer ajuda a solucionar.

<div id="how-does-it-work" />

### Como ele funciona?

Em vez de enviar esses dados para o ***anunciante***, para que ele faça a correspondência com seus próprios dados, o ***DCR assume essa tarefa*** – transferindo a responsabilidade para a AppsFlyer. Feito isso, o DCR analisa e agrupa esses dados, enviando-os de forma agregada aos anunciantes – e permitindo que eles acessem os insights agregados necessários,**sem violar a privacidade dos usuários.**

<div id="how-does-the-dcr-obtain-data" />

### Como o DCR obtém esses dados?

Atualmente, essa solução usa 2 tipos de dados:

* **Dados de origem personalizada:** dados no nível do usuários enviados para o armazenamento em cloud para uso do DCR. Esses dados se originam dos sistemas internos dos anunciantes (como os sistemas de BI ou CRM)
* **Dados de atribuição:** dados no nível do usuário fornecidos pelos canais de mídia para atribuição na AppsFlyer

<div id="what-does-the-dcr-do-with-the-data" />

### O que o DCR faz com esses dados?

O DCR funciona de acordo com os princípios padrões das bases de dados. Ou seja, ele combina dados de diferentes tabelas (ou **“fontes”**) em um único conjunto de dados. Esse conjunto de dados é usado para criar **relatórios** que usam a combinação desses dados:

* Para fazer a correspondência entre diferentes fontes e combiná-las em um único conjunto de dados, cada fonte deve compartilhar pelo menos um campo que identifique um usuário exclusivo do app **(“identificador”)** em comum com outra fonte.
* Ao usar identificadores para a correspondência entre os dados no nível do usuário e os dados de atribuição, o DCR cria um conjunto que mescla essas informações.
* Em seguida, para fornecer insights protegidos, o DCR processa esses dados e cria **relatórios agregados,** agrupados de acordo com as características **("dimensões")** definidas por você.

<div id="dcr-terminology" />

## Terminologia do DCR

Listamos abaixo alguns dos termos mais usados no DCR:

* **Conector:** o bucket AWS ou GCS (de propriedade do anunciante), no qual os dados do DCR são armazenados. Um conector pode incluir pastas para os dados de origem que entram no DCR e/ou destinos para os relatórios que saem. Você pode usar um único conector ou diversos conectores para o fluxo de dados que entram e saem do DCR.
* **Fontes:**
  * **Fonte do anunciante:** o arquivo de dados first-party que entra no DCR (usado para a correspondência e enriquecimento com dados de atribuição da AppsFlyer). Novas versões desse arquivo podem ser enviadas para processamento a cada 6 horas. Ao configurar uma fonte na plataforma do DCR, você configura sua **estrutura** e **local**:
    * **Estrutura da fonte:** uma lista de campos de dados da fonte e a categoria atribuída a cada um, que define como eles serão usados nos relatórios (identificador, dimensão ou métrica).
    * **Local da fonte:** a pasta do serviço em cloud a partir da qual a AppsFlyer obtém o arquivo da fonte sempre que ele é atualizado. Essa pasta fica dentro de um bucket (“conector”).
  * **Dados de atribuição:** dados no nível do usuário da sua conta da AppsFlyer (usados para a correspondência e o enriquecimento de dados do anunciante no DCR).
* **Relatório:** um arquivo de dados obtido pelo DCR após o processamento. Os relatórios são criados sempre que novas versões dos arquivos de fonte são enviados. Ao configurar um relatório na plataforma do DCR, você configura sua **estrutura** e **destino:**
  * **Estrutura do relatório:** é a especificação das fontes do anunciante e dos dados de atribuição que devem ser usados nos relatórios, seus identificadores correspondentes, métricas que devem ser incluídas e dimensões que devem ser usadas para o agrupamento dos relatórios.
  * **Destino do relatório:** a pasta do serviço em cloud para a qual a AppsFlyer deve enviar o relatório sempre que ele for processado. Essa pasta fica dentro de um bucket (“conector”).

<div id="working-with-the-dcr-setup-workflow" />

## Trabalhando com o DCR (configuração do workflow)

O Data Clean Room (DCR) da AppsFlyer é muito flexível quanto aos tipos de dados que você pode enviar, os relatórios que você deseja receber e o tempo e frequência de processamento. Por isso, é necessário um longo processo de planejamento e configuração – que provavelmente envolverá a colaboração com diversas pessoas da sua empresa.

Para configurar o DCR de acordo com as necessidades da sua empresa, siga esses passos:

1. Defina quais relatórios você deseja receber do DCR. Esses relatórios são o resultado do enriquecimento das suas fontes de anunciantes com os dados de atribuição da AppsFlyer. Determine quais são as fontes de dados first-party que você precisa enviar para o DCR para criar esses relatórios.
2. <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-setting-up-cloud-services">Crie uma estrutura básica de armazenamento em cloud</Anchor> para garantir o suporte a essas fontes e relatórios.
3. Defina quais queries serão responsáveis por extrair os dados e criar os arquivos de dados de origem/protótipos dos arquivos de dados de origem.
4. Desenvolva as automatizações necessárias para extrair os dados, criar as subpastas de origem e enviar as fontes e <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#_success-files">arquivos \_SUCCESS</Anchor> regularmente.
5. Configure suas <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources">fontes</Anchor> na plataforma do DCR .
6. Configure seus <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-reports">relatórios</Anchor> na plataforma do DCR.
7. Desenvolva as automatizações que irão ingerir os relatórios depois de serem enviados pelo DCR para o seu armazenamento em cloud.

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01HE7SDH5PWCW6YG00GC12W4BS=introdu%C3%A7%C3%A3o how-does-it-work=como-ele-funciona h_01HE7SDH5PW64CHNJVJJ30V5ZY=como-ele-funciona how-does-the-dcr-obtain-data=como-o-dcr-obt%C3%A9m-esses-dados h_01HE7SDH5P82HCEN52ZBPMQV16=como-o-dcr-obt%C3%A9m-esses-dados what-does-the-dcr-do-with-the-data=o-que-o-dcr-faz-com-esses-dados h_01HE7SDH5PWDQ61389TT7V83F8=o-que-o-dcr-faz-com-esses-dados dcr-terminology=terminologia-do-dcr h_01HE7SDH5P3QSG874XASXNH1YS=terminologia-do-dcr working-with-the-dcr-setup-workflow=trabalhando-com-o-dcr-configura%C3%A7%C3%A3o-do-workflow h_01HE7SDH5P0S9542P2CB22KKVT=trabalhando-com-o-dcr-configura%C3%A7%C3%A3o-do-workflow" />

---
title: 'Boletim: compatibilidade do SKAN 4 na AppsFlyer'
metadata:
  keywords:
    - iOS
    - Marketers
    - SKAN
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2023-01-05T12:36:02Z'
  edited_at: '2026-08-18T00:20:59Z'
  id: 11938810583825
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/11938810583825
---
| **O título** | A solução SKAdNetwork da AppsFlyer agora é compatível com o SKAN 4. Isso inclui alterações importantes no SKAN Conversion Studio, assim como nos painéis e relatórios SKAN. |
| --- | --- |
| **Data de início** | <ul><li>15 de fevereiro de 2023: com iOS SDK V6.10+ nativo</li><li>Recomendamos atualizar para a versão mais recente V6.12+ mesmo se você estiver usando a V6.10 desde fevereiro<ul><li>Você pode ver a lista de mudanças <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-ios-sdk-release-notes">aqui</Anchor></li></ul></li><li>Em breve: suporte para outros SDKs e plug-ins da AppsFlyer</li></ul> |
| **Pré-requisitos** | Para que os dados do SKAN 4 iOS sejam devidamente registrados, é necessário o seguinte:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/appsflyer-ios-sdk-release-notes">SDK da AppsFlyer versão V6.12.1+</Anchor></li><li>A ad network deve gerar uma assinatura de anúncio para SKAdNetwork V4.</li><li>Para anúncios exibidos em um aplicativo, o aplicativo deve ser criado com iOS 16.1 SDK ou posterior.</li><li>Para anúncios na web, o anúncio precisa do Safari 16.1 ou posterior.</li><li>O aplicativo anunciado deve ser assinado pela App Store e executado em um dispositivo com iOS 16.1 ou posterior.</li></ul> |
| **Ações necessárias** | <ul><li>Atualize seu <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-ios-sdk-release-notes">SDK da AppsFlyer para V6.12.1+</Anchor></li><li>No SKAN Conversion Studio da AppsFlyer, atualize para o <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#skan-4">modo de métrica SKAN 4</Anchor> e configure CVs para as 3 janelas SKAN (ou mantenha as configurações padrão).</li></ul>**Observação:** depois de atualizar para o SKAN 4:<ul><li>O cronômetro de atividade para instalações pré-SKAN 4 é de 48 horas.</li><li>Você não pode reverter para uma versão anterior do SKAN.</li></ul> |
| **Mudanças no <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#skan-4">SKAN Conversion Studio</Anchor>** | Novo modo de métrica do SKAN 4 para configurar as 3 janelas SKAN |
| **Mudanças nos <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">painéis</Anchor>** | <ul><li>O painel de visão geral do SKAN inclui novos campos (disponíveis nas configurações da tabela) para contagens de eventos e receita durante as 3 janelas do SKAN:<ul><li>Contagem de eventos D0-D2</li><li>Contagem de eventos D0-D2 (modelado)</li><li>Contagem de eventos D3-D7</li><li>Contagem de eventos D8-D35</li><li>Receita D0-D2 ($)</li><li>Receita D0-D2 ($) (modelado)</li><li>Receita D3-D7 ($)</li><li>Receita D8-D35 ($)</li></ul></li><li>A exibição do painel SSOT exibe os campos de dados D2, em vez da Janela de Atividade (AW). Para dados SKAN 3, este campo mostra todos os dados da janela de atividade, mesmo se a janela for maior ou menor que 2 dias.</li></ul> |
| **Mudanças nos <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">relatórios</Anchor>** | <ul><li>Os relatórios da SKAdNetwork incluem os seguintes novos campos para dar suporte à SKAN 4:<ul><li>**skad\_postback\_sequence\_index**: valor é um número inteiro que representa a janela SKAN, ou`0`,`1`, ou`2`. Para SKAN 3 o valor é`0`.</li><li>**skad\_coarse\_conversion\_value**: o valor pode ser `baixo (low)`,`médio (medium)` ou `alto (high)`. Para SKAN 3 o valor é`nulo (null)`.</li><li>**skad\_source\_identifier**: o valor é uma string de até 4 dígitos. Para SKAN 3 o valor é`null`.</li><li>**skad\_source\_domain**: o valor é uma string que representa a origem dos anúncios da web atribuíveis. Para SKAN 3 o valor é `nulo (null)`.</li><li>**ad\_network\_creative**: o valor é uma string baseada no enriquecimento de dados recebido da ad network. Para SKAN 3 o valor está vazio.</li></ul></li><li>Os seguintes relatórios do Data Locker e Push API são afetados:</li></ul><ul><li>**skad\_installs** (via Data Locker e Push API)</li><li>**skad\_redownloads** (via Data Locker e Push API)</li><li>**skad\_inapps** (via Data Locker e Push API)</li><li>**skad\_postbacks** (via Data Locker)</li><li>**skad\_postbacks\_copy** (não inclui o campo ad\_network\_creative) (via Data Locker)</li><li><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQJzfkXrrdYU15SkRoEx2HlgezlNar76MHFMP1JWqNnGrtYuHFNz4Mf8u0diflSx-5-k0zfsMEzsuLS/pub?output=xlsx">Veja exemplos de esquemas de relatório</Anchor></li></ul><ul><li>A API de data de chegada de postback agregado SKAN e a API de relatório de performance agregada SKAN contêm campos da SKAN 4. **Observação**: você deve usar o caminho para o token da API V2 para a SKAN 4.</li></ul> |
---
title: 'Novidade: Solução de atribuição da AppsFlyer em parceria com o Google'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-08-06T13:24:32Z'
  edited_at: '2026-10-20T03:54:34Z'
  id: 37857301293457
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/37857301293457
---
<Embed title="Reprodutor de vídeo do YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/VilMr6T0Yd0?si=p7FezQwuKkBtwkaB" providerUrl="https://www.youtube.com" />

| Seção | Detalhes |
| --- | --- |
| **Novidades** | A solução ICM (Integrated Conversions Measurement) do Google estará disponível para todos os clientes que usam o Google Ads para mensurar instalações e reatribuições. |
| **Data estimada de disponibilidade geral (beta aberta):** | <ul><li>**iOS** – Beta aberta (desde 12 de novembro) - aberta para todos os Apps.</li><li>**Android** – Beta aberta (desde 5 de dezembro de 2025) - aberta para todos os Apps.</li></ul> |
| **O que você precisa saber** | <ul><li>O ICM permite que a AppsFlyer atribua instalações ao Google Ads sem precisar de device IDs, usando métodos de proteção à privacidade.</li><li>O Google envia reivindicações de instalação não determinísticas para a AppsFlyer.<br />Se validadas pelos dados da AppsFlyer, essas reivindicações são usadas para atribuição. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#fluxo-de-atribuição-do-google-ads-com-compartilhamento-avançado-de-dados">o fluxo de atribuição do Google Ads com o compartilhamento avançado de dados</Anchor>.</li></ul> |
| **O que você precisa fazer** | <ul><li>**Requisitos do SDK:**<ul><li>**iOS:** Requer a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">versão 6.17.5</Anchor> ou versões mais recentes do iOS SDK *e* a <Anchor target="_blank" href="https://github.com/firebase/firebase-ios-sdk/releases">versão 11.14.0</Anchor> ou versões mais recentes do Google Firebase SDK, ou o <Anchor target="_blank" href="https://support.google.com/google-ads/answer/16384720">Google ODM SDK</Anchor>.</li><li>**Android:** nenhuma atualização necessária do SDK.</li></ul></li><li>**Compartilhamento avançado de dados:** uma nova configuração nas integrações `googleadwords_int` para iOS e Android:<ul><li>Quando **ativado**: a AppsFlyer enviará todos os eventos de instalação para o Google, mesmo sem um device ID.</li><li>Quando **desativado**: Apenas eventos de instalação com o device ID e/ou GCLID disponíveis serão compartilhados, limitando a eficácia do ICM.</li></ul></li><li>**Importante:** No iOS, o ICM **não** está **disponível** para usuários da UE.</li></ul> |
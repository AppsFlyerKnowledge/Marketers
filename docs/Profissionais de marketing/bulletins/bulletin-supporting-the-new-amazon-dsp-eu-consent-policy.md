---
title: 'Boletim: Nova política de consentimento da Amazon DSP na UE'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-12T09:11:36Z'
  edited_at: '2026-10-20T03:54:19Z'
  id: 45664244736529
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/45664244736529
---
| Seção | Detalhes |
| --- | --- |
| **Novidades** | Para se preparar para o Digital Markets Act (DMA), a Amazon Ads está atualizando a política de consentimento para usuários da UE. A AppsFlyer está fazendo as alterações necessárias para atender às novas diretrizes e garantir que os anunciantes maximizem o valor dos seus canais de marketing do Amazon Ads. |
| **Data de início** | <ul><li>Data de entrada em vigor na Amazon – 30 de junho de 2026</li><li>Data de início do suporte na AppsFlyer – 18 de maio de 2026</li></ul> |
| **O que você precisa saber** | **Integrações e audiências relevantes** Todos os anunciantes que possuem aplicativos integrados com o Amazon Ads via `amazondsp_int` com SRN e atividade publicitária na União Europeia, no Reino Unido e na Suíça.<br /><br />**Ações necessárias:** Certifique-se de enviar sinais de consentimento válidos à AppsFlyer para qualquer evento (abertura do app ou eventos in-app) para usuários na União Europeia, no Reino Unido e na Suíça.<br /><br />Exemplos de sinais de consentimento:<ol><li>**Consentimento manual:** `ad_user_data_enabled` é o único campo obrigatório como parte da lista de consentimento manual. Os outros campos exigidos para o consentimento em compliance com o DMA não são relevantes para a Amazon.</li><li>**Consentimento do TCF:** Envie os dados de consentimento do TCF gerados pela sua CMP e inclua o ID do fornecedor da Amazon Ads (`793`) na lista de fornecedores autorizados.</li><li>**Condições de consentimento da GPP:** A Amazon é compatível com strings de consentimento da GPP, mas essa opção não está disponível na AppsFlyer.</li></ol>**<span id="h_01KP0FAZ70YDRQ71TDRYFEG120"></span>Veja também**<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">Como enviar consentimento em compliance com o DMA via SDK da AppsFlyer</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">Como enviar consentimento em compliance com o DMA via S2S da AppsFlyer</Anchor> (pesquise `consent_data`)</li></ul> |
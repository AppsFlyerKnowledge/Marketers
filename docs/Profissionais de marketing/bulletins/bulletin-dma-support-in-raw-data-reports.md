---
title: 'Boletim: suporte ao DMA nos relatórios de dados brutos'
metadata:
  keywords:
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2024-05-29T16:52:12Z'
  edited_at: '2026-10-20T03:55:38Z'
  id: 25485269115793
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/25485269115793
---
| **Novidades** | Os seguintes campos de consentimento do DMA estão sendo adicionados às ferramentas de dados brutos na AppsFlyer:<ul><li>**gdpr\_applies:** Indica se o usuário se enquadra na jurisdição do DMA (true) ou não (false).</li><li>**ad\_user\_data\_enabled**: Indica se o usuário consentiu em permitir que o Google use os dados do usuário em nível de usuário para mensuração e anúncios personalizados (true) ou não (false).</li><li>**ad\_personalization\_enabled**: Indica se o usuário consentiu em permitir que o Google use os dados do usuário em nível de usuário para anúncios pessoais (true) ou não (false).</li><li>**raw\_consent\_data**: Retorna um objeto JSON com todos os dados brutos de consentimento, conforme enviados do anunciante para a AppsFlyer. As informações enviadas neste objeto são então usadas para preencher os três campos acima.<ul><li>Este campo não está disponível na exportação de dados brutos nem na Pull API</li></ul></li></ul> |
| --- | --- |
| **Data de início** | <ul><li>Página de exportação de dados brutos e Pull API - 3 de junho de 2024</li><li>Push API e Data Locker - 14 de outubro de 2024</li></ul> |
| **Onde:** | <ul><li>Página de exportação de dados em bruto</li><li>Extrair API</li><li>API de push</li><li>Data Locker</li></ul> |
| **Quem deve saber** | <ul><li>Anunciantes e agências que usam a página de exportação de dados brutos, Push API, Pull API e Data Locker para exportar dados brutos (nível de evento) da AppsFlyer.</li></ul> |
| **Como isso afeta você** | <ul><li>Configure seu esquema e quaisquer outros processos envolvidos no consumo dos dados.</li><li>Verifique se os novos campos não comprometem seu esquema para Push API e Data Locker.</li></ul> |
| **Informações adicionais** | Revise o nosso artigo <Anchor target="_blank" href="/marketers/pt/docs/support-google-eu-consent-policy">Suporte para a política de consentimento do Google na UE</Anchor>. |
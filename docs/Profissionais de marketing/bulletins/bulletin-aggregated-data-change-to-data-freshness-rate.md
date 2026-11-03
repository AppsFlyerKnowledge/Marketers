---
title: 'Boletim: alteração de dados agregados para taxa de atualização de dados'
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Marketing Analytics
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Ad Networks
  created_at: '2021-07-20T11:47:58Z'
  edited_at: '2026-10-20T03:56:53Z'
  id: 4404329828497
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/4404329828497
---

<Table>
  <tbody>
    <tr>
      <td>
        O título
      </td>
      <td>
        Taxa de atualização de dados de instalações e eventos in-app em relatórios de analytics e dashboards
      </td>
    </tr>
    <tr>
      <td>
        Data do boletim
      </td>
      <td>
        24 de agosto de 2021
      </td>
    </tr>
    <tr>
      <td>
        O que vai mudar?
      </td>
      <td>
        As taxas de atualização de dados de instalações e de eventos in-app estão mudando. A tabela detalha a atualização dos dados antes e depois da alteração.

        #### Taxa de atualização de dados por tipo de evento

        | ID do produto | Antes da alteração (minutos) | Depois da mudança<br /><br />(Minutos) |
        | --- | --- | --- |
        | Instalação, reatribuição, reengajamento | 3-5 | 15-30 |
        | Evento na Aplicação | 90 | 30-60 |
      </td>
    </tr>
    <tr>
      <td>
        O que vai mudar
      </td>
      <td>
        A alteração na atualização de dados afeta os dashboards e as ferramentas de reportar listados. A alteração ocorrerá em fases, da seguinte forma:

        **Fase 1 — a partir de 12 de setembro de 2021 (sujeito a alterações)**

        * Dashboards:
          * Retorna um objeto JSON com os dados brutos de consentimento do DMA conforme enviados do anunciante para a AppsFlyer
          * Visão geral V2
          * Categoria do dispositivo (por exemplo, MOBILE\_PHONE, TV)
          * Recurso
          * Personalizada
        * Relatórios agregados por meio da Pull API

        **Fase 2 — a partir de 6 de outubro de 2021 (planejado)**

        * Dashboards:
          * ativado
          * Coorte
        * API: cohort
      </td>
    </tr>
    <tr>
      <td>
        O que não vai mudar
      </td>
      <td>
        Master API e dados brutos
      </td>
    </tr>
    <tr>
      <td>
        Ação necessária
      </td>
      <td>
        * Ao visualizar ou fazer download dos dados, considere a alteração na atualização de dados.
        * Se você usa o dashboard Overview para testar a integração do SDK ou a integração com um parceiro de ad network, os eventos de instalação levarão mais tempo para serem exibidos. Considere usar relatórios de dados brutos para verificar seus testes de integração.
      </td>
    </tr>
  </tbody>
</Table>

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support">Atualização de dados da AppsFlyer</Anchor>
> * Novidades na AppsFlyer

<div data-zendesk-anchors="data-freshness-rate-per-event-type=taxa-de-atualiza%C3%A7%C3%A3o-de-dados-por-tipo-de-evento h_01HDP21Y0H5S3R4GR5411R6D4Y=taxa-de-atualiza%C3%A7%C3%A3o-de-dados-por-tipo-de-evento h_01HDPE9QAQ41ADC9DQGSK80288=consulte-tamb%C3%A9m" />

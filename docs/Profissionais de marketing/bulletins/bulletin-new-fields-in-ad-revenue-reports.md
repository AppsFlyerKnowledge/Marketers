---
title: 'Boletim: novos campos nos relatórios de receita de anúncios'
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-07-22T13:25:32Z'
  edited_at: '2026-10-20T03:55:16Z'
  id: 26907692192273
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/26907692192273
---

<Table>
  <tbody>
    <tr>
      <td>
        **Novidades**
      </td>
      <td>
        Os relatórios de receita de anúncios têm novos campos.
      </td>
    </tr>
    <tr>
      <td>
        **Data de início**
      </td>
      <td>
        19 de setembro de 2024
      </td>
    </tr>
    <tr>
      <td>
        **O que você deve saber**
      </td>
      <td>
        A tabela a seguir mostra quais campos estão sendo adicionados a quais relatórios. Consulte o <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">dicionário de campos de dados brutos</Anchor> para ver as definições e os detalhes de cada campo.

        | Relatório | Nomes dos campos da API |
        | --- | --- |
        | <Anchor target="_blank" href="/marketers/pt/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Legacy ad revenue [versão única]</Anchor> | * {"engagement_type"}<br />* {"custom_data"}<br />* Taxa de imposto sobre a receita líquida<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/pt/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Receita de anúncios [com versão]</Anchor> | * {"engagement_type"}<br />* {"custom_data"}<br />* Taxa de imposto sobre a receita líquida<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/pt/docs/revenue-etl-reports#impression-level-report">Receita de anúncios [Nível de impressão SDK]</Anchor> | * {"engagement_type"}<br />* {"custom_data"}<br />* Taxa de imposto sobre a receita líquida<br />* {"ad_revenue_ad_type"}<br />* {"ad_revenue_custom_parameters"}<br />* {"app_version"}<br />* {"sdk_version"} |
      </td>
    </tr>
    <tr>
      <td>
        **O que é preciso fazer**
      </td>
      <td>
        * Em <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#set-up-data-locker">Configurações do Data Locker da AppsFlyer</Anchor>, selecione os novos campos que serão adicionados aos seus relatórios.  
          **Dica**! Se você já recebe um campo como customer\_user\_id pelas configurações padrão do Data Locker, para preencher os campos nos relatórios de receita de anúncios, você precisa adicionar outro campo novo e salvar as configurações. Você pode reverter as alterações depois.
        * Configure seus sistemas de BI para ingerir e usar os novos campos.
      </td>
    </tr>
  </tbody>
</Table>

---
title: 'Bulletin : Nouveaux champs dans les rapports sur les revenus publicitaires'
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
  edited_at: '2024-09-25T09:59:10Z'
  id: 26907692192273
  locale: fr
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/fr/articles/26907692192273
---

<Table>
  <tbody>
    <tr>
      <td>
        **Quoi de neuf ?**
      </td>
      <td>
        Les rapports sur les revenus publicitaires comportent de nouveaux champs.
      </td>
    </tr>
    <tr>
      <td>
        **Date d'entrée en vigueur**
      </td>
      <td>
        Septembre 19, 2024
      </td>
    </tr>
    <tr>
      <td>
        **Ce que vous devez savoir**
      </td>
      <td>
        Le tableau suivant indique quels champs sont ajoutés aux différents rapports. Consultez le <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">dictionnaire des champs de données brutes</Anchor> pour les définitions et les détails de chaque champ.

        | Rapport | Noms des champs API |
        | --- | --- |
        | <Anchor target="_blank" href="/marketers/fr/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Revenus publicitaires hérités [version unique]</Anchor> | * {"engagement_type"}<br />* {"custom_data"}<br />* {"customer_user_id"}<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/fr/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Revenus publicitaires [versionnés]</Anchor> | * {"engagement_type"}<br />* {"custom_data"}<br />* {"customer_user_id"}<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/fr/docs/revenue-etl-reports#impression-level-report">Revenus publicitaires [Niveau d'impression du SDK]</Anchor> | * {"engagement_type"}<br />* {"custom_data"}<br />* {"customer_user_id"}<br />* {"ad_revenue_ad_type"}<br />* {"ad_revenue_custom_parameters"}<br />* {"app_version"}<br />* {"sdk_version"} |
      </td>
    </tr>
    <tr>
      <td>
        **Ce que vous devez faire**
      </td>
      <td>
        * Dans les <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers#set-up-data-locker">paramètres d'AppsFlyer Data Locker</Anchor>, sélectionnez les nouveaux champs à ajouter à vos rapports.
        * Configurez vos systèmes de BI pour intégrer et utiliser les nouveaux champs.
      </td>
    </tr>
  </tbody>
</Table>

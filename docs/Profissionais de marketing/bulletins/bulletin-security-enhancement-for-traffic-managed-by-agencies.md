---
title: 'Boletim: Reforço da segurança do tráfego gerenciado pelas agências'
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2024-06-09T14:08:35Z'
  edited_at: '2026-10-20T03:55:33Z'
  id: 25770412740369
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/25770412740369
---
| **Novidades** | Para proteger os seus dados, garantir a segurança e reduzir a fraude, estamos melhorando as medidas de segurança para as agências que gerenciam o tráfego em nome de anunciantes que estão a executar campanhas em ad networks. A partir de 14 de julho de 2024, apenas o tráfego de agências autorizadas pelas ad networks será registado e medido na AppsFlyer. Isso significa que agências não autorizadas não poderão configurar a integração (a janela de configuração do parceiro ficará esmaecida) e o tráfego não autorizado dessas agências resultará em uma resposta 403 (Forbidden) da AppsFlyer. Depois que as agências forem adicionadas à lista, a aprovação será aplicada em toda a conta, permitindo que elas executem campanhas com todos os aplicativos na sua network.<br /><br />**Onde**:<ul><li>Também se aplica a parâmetros af\_prt vazios em links de atribuição</li><li>Não se aplica a agências que trabalham com <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">SRNs</Anchor></li></ul> |
| --- | --- |
| **Data de início** | 14 de julho de 2024 |
| **Onde:** | <ul><li>**Agência:** Página de integração</li><li>**Ad network** Central de segurança</li></ul> |
| **O que você deve saber** | <ul><li>**Agência:** Entre em contato com o parceiro e certifique-se de que o ID da sua agência (o nome af\_prt) é adicionado à lista de permissões da agência.</li><li>**Partner:** Certifique-se de adicionar todos os IDs de agência (af\_prt) na <Anchor target="_blank" href="/partners/pt/docs/set-up-your-list-of-authorized-agencies">secção da lista de permissões de novas agências</Anchor>.</li></ul> |
| **Implicações** | A partir da data especificada, as agências que não constarem da lista de aprovados da ad network não terão o seu tráfego registado e medido, nem poderão aceder à página de integração de todos os apps que executam campanhas na ad network. |
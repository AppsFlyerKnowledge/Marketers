---
title: Sobre o modelo de atribuição aprimorada
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2025-11-30T11:53:35Z'
  edited_at: '2026-08-18T00:09:16Z'
  id: 41442782045073
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/41442782045073
---
> **Em resumo:** o modelo de atribuição aprimorada melhora a precisão da atribuição ao atribuir somente cliques e impressões qualificados quando é detectada inundação de cliques e impressões no dispositivo.

## O que é o modelo de atribuição aprimorada?

O modelo de atribuição aprimorada combate a inundação de engajamento ao considerar, para atribuição, apenas sinais que reflitam o engajamento real do usuário. Quando a AppsFlyer detecta padrões de engajamento que indicam inundação, a AppsFlyer considera apenas cliques e impressões qualificados. Como resultado, a atribuição é baseada no último clique qualificado, que não é necessariamente o clique mais recente.

O modelo funciona continuamente em segundo plano e se aplica a todo o tráfego relevante sem exigir nenhuma ação de anunciantes ou parceiros.

## Como o modelo de atribuição aprimorada ajuda

O modelo de atribuição aprimorada ajuda anunciantes, ad networks e parceiros das seguintes formas:

* Anunciantes
  * Aumenta a precisão da atribuição nos fluxos de aquisição e retargeting.
  * Permite escalabilidade com confiança em canais de alto crescimento sem comprometer a qualidade da atribuição.
  * Melhora a proteção do gasto ao embasar decisões em dados de atribuição mais confiáveis.
  * Ajuda a identificar e priorizar canais e parceiros de alto valor.

* Ad networks e parceiros
  * Garante que a atribuição seja baseada na atividade real do usuário.
  * Melhora a precisão dos relatórios e das decisões de otimização.
  * Mantém uma competição de atribuição consistente e justa.
  * Reduz o efeito de volumes de engajamento inflados artificialmente.

## Como o modelo de atribuição aprimorada funciona

Veja como funciona:

1. A AppsFlyer recebe registros de engajamento de várias fontes de mídia, como cliques ou impressões.
2. Quando a AppsFlyer detecta um padrão de inundação durante o processo de atribuição, um modelo adicional ajuda a selecionar engajamentos qualificados.

## Onde os dados de atribuição aprimorada aparecem nos relatórios da AppsFlyer

Você pode visualizar dados de atribuição aprimorada nos seguintes canais:

### Relatório Retargeting

**Total de candidatos para atribuição** é uma métrica exibida nos relatórios de dados brutos. Ela indica o número de engajamentos que teriam entrado na competição de atribuição antes que a atribuição aprimorada e a lógica de detecção de fraude do Protect360 fossem aplicadas. Como o relatório dos contribuidores reflete os resultados pós-filtragem, o número total de candidatos pode ser significativamente maior do que o número de contribuidores.

Essa métrica pode indicar um possível excesso de engajamento e ajuda os anunciantes a entender o volume de engajamento e os padrões da fonte. Ela não representa o número de dispositivos ou usuários.

> 📘 **Nota**
>
> A métrica também pode ser maior que zero para instalações orgânicas, já que engajamentos orgânicos ainda podem entrar na competição de atribuição antes da validação.

### Dashboards e relatórios do Protect360

* Média de engajamentos por instalações comprometidas e não comprometidas
* Tendências de atribuição segmentadas por instalações comprometidas e não comprometidas

**Observação:** Os dados comprometidos começam a aparecer no dashboard do Protect360 somente depois que um aplicativo é adicionado à atribuição avançada. No entanto, os dados comprometidos e não comprometidos ainda podem ser exibidos para períodos históricos anteriores à adição do aplicativo ao recurso.

<div data-zendesk-anchors="what-is-the-enhanced-attribution-model=o-que-%C3%A9-o-modelo-de-atribui%C3%A7%C3%A3o-aprimorada h_01KEC2P5M5EPDA22XZ6XSQRZFQ=o-que-%C3%A9-o-modelo-de-atribui%C3%A7%C3%A3o-aprimorada how-the-enhanced-attribution-model-helps=como-o-modelo-de-atribui%C3%A7%C3%A3o-aprimorada-ajuda h_01KEC2P5M5NZ5F134TPRPN8K15=como-o-modelo-de-atribui%C3%A7%C3%A3o-aprimorada-ajuda how-the-enhanced-attribution-model-works=como-o-modelo-de-atribui%C3%A7%C3%A3o-aprimorada-funciona h_01KEC2P5M59QCG1E5C74ERASYE=como-o-modelo-de-atribui%C3%A7%C3%A3o-aprimorada-funciona where-enhanced-attribution-data-appears-in-appsflyer-reports=onde-os-dados-de-atribui%C3%A7%C3%A3o-aprimorada-aparecem-nos-relat%C3%B3rios-da-appsflyer h_01KEC2P5M52MG4EWD63PE761G9=onde-os-dados-de-atribui%C3%A7%C3%A3o-aprimorada-aparecem-nos-relat%C3%B3rios-da-appsflyer raw-data-reports=relat%C3%B3rio-retargeting h_01KEC2P5M5VTJ5YF4NJ13ZY0NF=relat%C3%B3rio-retargeting h_01KEC2P5M5T43VGNWF9HW9K76Z=nota protect360-dashboards-and-reports=dashboards-e-relat%C3%B3rios-do-protect360 h_01KEC2P5M5TAHRRC3YCSB5EQE5=dashboards-e-relat%C3%B3rios-do-protect360" />

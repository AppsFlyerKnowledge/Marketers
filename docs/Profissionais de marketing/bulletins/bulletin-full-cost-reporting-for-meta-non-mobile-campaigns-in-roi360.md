---
title: >-
  Comunicado: relatório completo de custos para campanhas não mobile da Meta no
  ROI360
deprecated: false
hidden: false
metadata:
  keywords:
    - Cost
    - ROI360
    - Meta
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
  created_at: '2026-11-01T08:56:35Z'
  edited_at: '2026-11-03T01:37:47Z'
  id: 52545079276561
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/52545079276561
---
| **Secção** | **Atenção** |
| --- | --- |
| **Novidade** | Após esta atualização, o ROI360 agora reporta o custo completo das campanhas não mobile da Meta nos relatórios de canal e geo, e o número de cliques reportados da Meta aumentou. Essa mudança corrige a discrepância conhecida entre o dashboard da Meta e os relatórios de geo e canal.<br /><br />A Meta reporta o custo de campanhas não mobile sem IDs de app. O ROI360 atribui esse custo aos aplicativos que têm atribuição no AppsFlyer e o divide entre esses aplicativos na proporção das conversões de cada aplicativo. Essa abordagem se aplica aos relatórios de geo e canal. Depois da atualização:<ul><li>O custo no nível de campanha é o mesmo nos relatórios de geo e canal porque ambos os relatórios incluem todos os custos que a Meta reporta.</li><li>O custo no nível do aplicativo pode diferir entre os relatórios de geo e canal. O ROI360 divide o custo entre os aplicativos ao relacionar a divisão do custo à divisão das conversões. Como os dois relatórios usam granularidades diferentes (geo e canal), a divisão de conversões por aplicativo difere; portanto, o custo alocado para cada aplicativo também difere.</li></ul> |
| **Data de vigência** | 9 de novembro de 2026<br /><br />As mudanças entram em vigor gradualmente. Elas se aplicam aos novos dados daqui para frente e preenchem dados históricos dos últimos 7 dias. |
| **O que é preciso fazer** | Se você aplicar uma lógica interna para completar o custo da Meta nos relatórios de canal e geo, remova essa lógica após a atualização entrar no ar para evitar reportar o custo em excesso. |
| **O que você deve saber** | **Relatório de canal**<ul><li>Mudança: hoje, o ROI360 mensura apenas o custo que mapeia claramente para um app mobile (iOS ou Android). Após esta atualização, o ROI360 reporta o custo total das campanhas não mobile da Meta e resolve os aplicativos usando dados de atribuição e lógica de divisão de custos. Isso encerra a discrepância conhecida com a Meta.</li><li>Impacto: o custo total no relatório de canal aumenta nos níveis de campanha e aplicativo para corresponder ao seu gasto real na Meta.</li></ul>Para ver um exemplo, consulte o [exemplo de relatório de canal](#REPLACE_CHANNEL_EXAMPLE_ID).<br /><br />**Relatório de geolocalização**<ul><li>Mudança: hoje, o custo no nível de geo para campanhas não mobile da Meta está disponível apenas para clientes beta. Após esta atualização, o custo no nível de geo fica disponível para todos os clientes no dashboard e no relatório geo do Cost ETL. O ROI360 aloca custos entre geos e aplicativos atribuídos usando lógica de divisão de custos.</li><li>Impacto: o custo total mensurado da Meta com granularidade de geo aumenta nos níveis de campanha e aplicativo.</li></ul>Para ver um exemplo, consulte o [exemplo de relatório de geo](#REPLACE_GEO_EXAMPLE_ID).<br /><br />**Métrica de cliques**<ul><li>Mudança: **Depois desta atualização, o ROI360 usa uma métrica de cliques da Meta diferente.** Hoje, o ROI360 usa a métrica de cliques inline da Meta, que mede apenas o número de cliques em links para destinos ou experiências selecionados, dentro ou fora das propriedades da Meta. Após esta atualização, o ROI360 usa a métrica de cliques da Meta, que mede o número total de cliques em anúncios. Isso pode incluir cliques em links inline, curtidas na página, comentários em publicações e respostas a eventos.</li><li>Impacto: os cliques reportados pela Meta aumentam.</li></ul> |

## Exemplos

### Exemplo de relatório do canal

**Quando o dashboard da Meta mostra o custo por dispositivo de impressão:**

| **Dispositivo de impressão** | **Custo (3)** |
| --- | --- |
| iPhone | $100 |
| Android / iOS | US$ 200 |
| Desktop | US$ 50 |
| **Total** | **$350** |

**Antes da atualização, o ROI360 reporta o custo parcial:**

| **Sequência de caracteres** | **Custo (3)** |
| --- | --- |
| id12345 | $100 |
| android.com | US$ 200 |
| **Total** | **US$ 300** |

O ROI360 reporta apenas o custo que corresponde claramente a app mobile. Ele não reporta o restante. Neste exemplo, são os US$ 50 que a Meta retornou com dispositivo de impressão = desktop.

**Após a atualização, o ROI360 reporta todos os custos:**

| **Sequência de caracteres** | **Taxa** | **Custo (3)** |
| --- | --- | --- |
| id12345 | 0.3 | $105 |
| android.com | 0.6 | $210 |
| www.test.com | 0.1 | $35 |
| **Total** |  | **$350** |

O ROI360 reporta todo o custo no nível da campanha, em linha com os relatórios da Meta. Ele divide o custo entre os aplicativos atribuídos (mobile e não mobile).

### Exemplo de relatório por geolocalização

**Quando o dashboard da Meta mostra o custo por geo:**

| **Geografia** | **Custo (3)** |
| --- | --- |
| Reino Unido | US$ 200 |
| BE | US$ 150 |
| **Total** | **$350** |

**Depois da atualização, o ROI360 reporta o custo por geo e aplicativo:**

| **Geografia** | **Sequência de caracteres** | **Custo (3)** |
| --- | --- | --- |
| Reino Unido | id12345 | US$ 50 |
| Reino Unido | android.com | US$ 150 |
| BE | id12345 | US$ 50 |
| BE | android.com | $100 |
| **Total** |  | **$350** |

<div data-zendesk-anchors="h_01M6BT1WAPZBCJQMGSFEYNX4D4=exemplos h_01M6BT1WAPJHDGF5N5SACGDWAX=exemplo-de-relat%C3%B3rio-do-canal h_01M6BT1WAP2PW79ZZPM4WD7SKK=exemplo-de-relat%C3%B3rio-por-geolocaliza%C3%A7%C3%A3o" />

---
title: Selecionar os parâmetros de atribuição para as URLs das landing pages
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T16:46:08Z'
  edited_at: '2026-08-18T00:23:14Z'
  id: 43525434385809
  locale: pt
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/pt/articles/43525434385809
---
> **Em resumo:** Use parâmetros de URL consistentes e completos nos links das landing pages do seu site para obter o melhor nível de granularidade da campanha e, ao mesmo tempo, manter a atribuição precisa na mensuração de performance web.

## Sobre as classes de parâmetros de atribuição de URL

A AppsFlyer lê os parâmetros de campanha da URL da sua landing page (o link em que o usuário clica) e os usa para atribuir sessões e eventos à **fonte de mídia**, à **campanha** e, quando disponível, a níveis mais profundos da hierarquia, como **conjunto de anúncios** e **anúncio**.

Os parâmetros que você inclui determinam os resultados da mensuração da sua campanha. Em outras palavras, a mesma landing page pode produzir resultados muito diferentes, dependendo de quais parâmetros você inclui.

Os parâmetros de URL podem pertencer a uma de duas classes: PID e UTM.

* A classe PID inclui os parâmetros de URL da AppsFlyer.
* A classe UTM inclui os parâmetros UTM padrão.

Para mais informações sobre como a Mensuração de Performance Web processa parâmetros de URL, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-traffic-source-resolution">Sobre a resolução da fonte de tráfego</Anchor>.

### Parâmetros PID e UTM compatíveis

A mensuração de performance web oferece suporte aos seguintes parâmetros.

| # | Parâmetro | Usado para | Classe do parâmetro | Disponível no painel | Campo de dados brutos |
| --- | --- | --- | --- | --- | --- |
| 1 | `pid` | Canal de mídia | PID | Yes | `fonte_de_mídia` |
| 2 | `C` | Campaign name | PID | Yes | `campaign_name` |
| 3 | `af_c_id` | ID da campanha | PID | Yes | `id_da_campanha` |
| 4 | `af_adset` | Nome do adset | PID | Yes | `adset_name` |
| 5 | `af_adset_id` | ID do conjunto de anúncios | PID | Yes | `id_conjunto_de_anúncios` |
| 6 | `af_ad` | Ad name | PID | Yes | `ad_name` |
| 7 | `af_ad_id` | ID do anúncio | PID | Yes | `id_anúncio` |
| 8 | `utm_source` | Canal de mídia | UTM | Yes | `fonte_de_mídia` |
| 9 | `utm_medium` | Tipo de mídia | UTM | Sem | `media_type` |
| 10 | `utm_campaign` | Campaign name | UTM | Yes | `campaign_name` |

## Escolha os parâmetros de atribuição certos

A AppsFlyer avalia os parâmetros de URL de forma independente para cada campo de relatório (como canal de mídia ou campanha), usando uma cascata de prioridade específica. Essa abordagem permite usar a atribuição da AppsFlyer junto com outras ferramentas, como o Google Analytics, usando a **classe PID** (nativa da AppsFlyer) e a **classe UTM** (marketing padrão) na mesma URL.

A Mensuração de Performance Web verifica a ordem de prioridade de cada campo individualmente. Se um parâmetro da classe PID, que tem prioridade mais alta, não estiver presente para um atributo específico, o sistema recorrerá automaticamente ao parâmetro correspondente na classe UTM para determinar o valor correto desse campo.

<div id="scenario-a-url-with-pid-class-only-appsflyer-reporting" />

<Accordion title="Cenário A. URL somente com a classe PID (relatórios da AppsFlyer)">

Use a classe PID quando os relatórios da AppsFlyer forem seu objetivo principal.

#### Exemplo

```http
www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}
```

**Resultado**: o AppsFlyer identifica o canal de mídia usando `pid` e a campanha usando `c`.

</Accordion>

<div id="scenario-b-url-with-utm-class-only-fallback" />

<Accordion title="Cenário B. URL apenas com a classe UTM (reserva)">

Se `pid` estiver ausente, o AppsFlyer recorre à classe UTM.

#### Exemplo

```http
 www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}
```

**Resultado**: o AppsFlyer identifica o canal de mídia usando `utm_source` e a campanha usando `utm_campaign`.

</Accordion>

<div id="scenario-c-url-with-both-pid-and-utm-classes" />

<Accordion title="Cenário C. URL com as classes PID e UTM">

O AppsFlyer permite incluir parâmetros de classes diferentes (por exemplo, PID e UTM) na mesma URL. Isso é útil quando você precisa dar suporte à atribuição do AppsFlyer juntamente com outras ferramentas de análise, como o Google Analytics ou sistemas internos de mensuração.

O AppsFlyer processa campos de atribuição, como canal de mídia e campanha, de forma independente. Para cada campo específico, o sistema segue uma cascata de prioridade para determinar qual valor registrar. Em geral, a **classe PID** tem precedência sobre a **classe UTM** para esse campo específico.

#### Exemplo 1: Parâmetros sobrepostos

```http
www.website.com?pid=facebook_ads&c=summer_sale&utm_source=facebook&utm_campaign=seasonal_promo
```

* **Canal de mídia:** o AppsFlyer detecta `pid` e `utm_source`. Seguindo a cascata de prioridade desse campo, ele registra `facebook_ads`.
* **Campanha:** o AppsFlyer detecta `c` e `utm_campaign`. Seguindo a cascata de prioridade desse campo, ele registra `summer_sale`.
* **Resultado:** o AppsFlyer usa os valores da classe PID, que têm prioridade mais alta, enquanto as ferramentas externas ainda podem ler os valores de UTM.

#### Exemplo 2: Classes de parâmetros mistas

```http
www.website.com?utm_source=facebook&c=summer_sale
```

* **Canal de mídia:** o AppsFlyer detecta `utm_source`. Como não há um equivalente da classe PID (`pid`), ele registra `facebook` da classe UTM.
* **Campanha:** o AppsFlyer detecta `c`. Como não há um equivalente da classe UTM (`utm_campaign`), ele registra `summer_sale` da classe PID.
* **Resultado:** o AppsFlyer atribui o evento com sucesso usando valores de ambas as classes, porque cada campo é resolvido de forma independente.

</Accordion>

## Outras Melhores práticas

<div id="keep-parameter-values-in-a-consistent-case" />

<Accordion title="Mantenha os valores dos parâmetros com um uso consistente de maiúsculas e minúsculas">

Os valores dos parâmetros **diferenciam maiúsculas de minúsculas**. Por exemplo, `utm_source=channel1` e `utm_source=CHANNEL1` são tratados como **canais de mídia diferentes**.

Melhor prática: defina uma convenção de maiúsculas/minúsculas (o uso de minúsculas é comum) e aplique-a em todas as URLs.

</Accordion>

<div id="use-question-marks-only-once" />

<Accordion title="Use pontos de interrogação apenas uma vez">

Rules:

* Use apenas **um** ponto de interrogação (`?`) antes dos parâmetros de consulta na URL.
* Não use pontos de interrogação adicionais na URL.

Correto:

* `www.website.com?parameters`

Incorreto:

* `www.website.com??parameters`
* `www.website.com?parameter1?parameter2`

</Accordion>

<div id="don-t-use-anchor-signs" />

<Accordion title="Não use sinais de âncora (#)">

Não use sinais de âncora (`#`) na URL.

Por quê: os parâmetros após `#` podem não carregar e podem não ser registrados pelo SDK web.

</Accordion>

<div data-zendesk-anchors="about-website-attribution-urls=sobre-as-classes-de-par%C3%A2metros-de-atribui%C3%A7%C3%A3o-de-url h_01KGMRXNWGXQ3CH5XGSREV6Z3R=sobre-as-classes-de-par%C3%A2metros-de-atribui%C3%A7%C3%A3o-de-url supported-pid-and-utm-parameters=par%C3%A2metros-pid-e-utm-compat%C3%ADveis h_01KGMRXNWG88REW1CVJ4XMYFHQ=par%C3%A2metros-pid-e-utm-compat%C3%ADveis choose-the-right-attribution-parameters=escolha-os-par%C3%A2metros-de-atribui%C3%A7%C3%A3o-certos h_01KGMRXNWGP1SFBWE3KG6VRZ9V=escolha-os-par%C3%A2metros-de-atribui%C3%A7%C3%A3o-certos h_01KGMRXNWGT9MS799QH9EP29XR=scenario-a-url-with-pid-class-only-appsflyer-reporting example=exemplo h_01KGMS1RMN3F1D0Q7HDZMGG19E=exemplo h_01KGMRXNWG0T3YCK0RPKX4B3BT=scenario-b-url-with-utm-class-only-fallback example::4f5c28b5=exemplo-1 h_01KGMS215ARDSY6NFQ8VEF6C2Y=exemplo-1 h_01KGMRXNWGZH2ZBP9XR8C8TNFN=scenario-c-url-with-both-pid-and-utm-classes example-1-overlapping-parameters=exemplo-1-par%C3%A2metros-sobrepostos h_01KGMS10B1QCRJ5N28FBNEEKR2=exemplo-1-par%C3%A2metros-sobrepostos example-2-mixed-parameter-classes=exemplo-2-classes-de-par%C3%A2metros-mistas h_01KGMS17B500RPGHSKJ1AJSYH8=exemplo-2-classes-de-par%C3%A2metros-mistas other-best-practices=outras-melhores-pr%C3%A1ticas h_01KGMRXNWGVJY55M83FVMKBP1X=outras-melhores-pr%C3%A1ticas h_01KGMRXNWG9S03GGBDXPN34DDM=keep-parameter-values-in-a-consistent-case h_01KGMRXNWGEF9D0ZH5M81RP0PH=use-question-marks-only-once don%E2%80%99t-use-anchor-signs-=don-t-use-anchor-signs h_01KGMRXNWGX6HA0R9X3VC2WFXV=don-t-use-anchor-signs" />

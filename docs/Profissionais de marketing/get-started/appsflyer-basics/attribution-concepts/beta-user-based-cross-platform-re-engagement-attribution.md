---
title: '[Beta] Atribuição cross-platform e user-based de reengajamento'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2026-04-05T12:40:10Z'
  edited_at: '2026-08-18T00:08:51Z'
  id: 45444294953361
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/45444294953361
---
> **Resumo:** Saiba como a atribuição cross-platform de reengajamento credita as fontes de mídia que levam usuários existentes de volta ao seu produto em diferentes plataformas.

<div id="about-cross-platform-re-engagement-attribution" />

## Sobre a atribuição cross-platform de reengajamento

A atribuição cross-platform de reengajamento amplia o modelo de <Anchor target="_blank" href="/marketers/pt/docs/beta-user-based-cross-platform-attribution">atribuição cross-platform e user-based</Anchor> para incluir a mensuração de cohort de usuários com base no engajamento mais recente com anúncios, além da fonte de aquisição original.

Na atribuição cross-platform de aquisição de usuários, todas as atividades de um usuário são creditadas à fonte de mídia original que gerou a primeira conversão. Para vincular eventos entre dispositivos e plataformas, utiliza-se um Customer User ID (CUID). Isso oferece uma visão unificada da jornada de cada usuário, independentemente de onde ela ocorra.

A atribuição cross-platform de reengajamento adiciona uma camada a esse modelo. Em vez de sempre creditar a fonte de aquisição original, ela também credita as fontes de mídia que levam usuários existentes de volta ao seu produto após um período de inatividade. Assim você consegue mensurar o verdadeiro impacto das suas campanhas em toda a sua linha de produtos, não apenas no dispositivo ou na plataforma onde foram executadas.

Veja como os dois modelos estão relacionados:

|  | Atribuição cross-platform de aquisição de usuários | Atribuição cross-platform de reengajamento |
| --- | --- | --- |
| **O que é mensurado?** | Primeira conversão e toda as atividades posteriores | Reativação de usuários existentes após um período de inatividade |
| **O crédito é atribuído a quem?** | Fonte de aquisição original | Fonte de mídia de reengajamento (exemplo: Meta) |
| **Escopo** | Todos os eventos dentro da janela de restauração da inatividade | Apenas eventos dentro da janela de reengajamento |
| **Configuração** | No nível da linha de produtos | Opt-in: sobre a configuração de aquisição de usuários no nível da linha de produtos |

A atribuição de reengajamento está ao lado da aquisição de usuários, para que você tenha uma visão única tanto da fonte que adquiriu um usuário quanto da fonte que o reconquistou, em um mesmo relatório.

<div id="how-does-re-engagement-attribution-work" />

## Como funciona a atribuição de reengajamento

Para que um evento in-app seja atribuído a uma fonte de mídia de reengajamento, todas as seguintes condições precisam ser cumpridas:

* **O reengajamento cross-platform está habilitado:** A atribuição de reengajamento precisa estar habilitada para a linha de produtos nas suas configurações da AppsFlyer.
* **O CUID está presente:** O evento precisa incluir um CUID válido que corresponda a um CUID previamente registrado na mesma linha de produtos. É assim que a AppsFlyer identifica o usuário como recorrente em vez de novo.
* **O período de inatividade do retargeting expirou:** O CUID não pode ter sido registrado durante, no mínimo, toda a janela de inatividade para reengajamento desde a última aparição. Se o evento ocorrer dentro dessa janela, não é contabilizado como um reengajamento e é atribuído à fonte de aquisição original.
* **O evento ocorre dentro da janela de reengajamento:** Depois que uma atribuição de reengajamento de qualidade é detectada, a janela de reengajamento é aberta. Apenas eventos in-app que ocorrem dentro dessa janela são atribuídos à fonte de mídia de reengajamento. Eventos que ocorrem após o fechamento da janela são atribuídos à fonte de aquisição original.

<div id="cross-platform-re-engagement-user-journey-example" />

## Jornada de reengajamento cross-platform

Os exemplos abaixo mostram a mesma jornada do usuário duas vezes: primeiro sem reengajamento cross-platform, depois com reengajamento opt-in. Uma comparação entre ambos ilustra exatamente como o reengajamento muda a atribuição.

<div id="user-journey-without-re-engagement" />

<Accordion title="Jornada do usuário sem reengajamento">

Considere uma jornada do usuário em três plataformas. Um anúncio do Google leva os usuários a instalar um aplicativo mobile, no qual eles se cadastram usando um CUID. Mais tarde, um anúncio da Meta leva o mesmo usuário a visitar a web, na qual ele faz login com o mesmo CUID. Após fazer login, o usuário realiza duas compras no mobile: US$ 100 e US$ 50.

[![](https://files.readme.io/0cd29d386c9b8b83811aa048174ba38b25a551e060c64409b27b1735bb4051eb-45444733164945.png)](https://files.readme.io/0cd29d386c9b8b83811aa048174ba38b25a551e060c64409b27b1735bb4051eb-45444733164945.png)

Nesse cenário, como o reengajamento não está habilitado, todas as atividades são atribuídas ao Google Ads: a fonte de aquisição original. As compras de US$ 100 e US$ 50, assim como ambas as ativações de plataforma (mobile e web), são creditadas ao Google. A Meta não recebe crédito dentro da atribuição cross-platform, mesmo que seu anúncio tenha levado à instalação pela web.

| Fonte de mídia | Total de atribuições | Aquisição de usuários | Reengajamentos | Ativações de plataformas | Mobile | Web | Dados de LTV: 5 anos |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 2 | 1 | 1 | US$ 150 |
| Meta | 0 | 0 | 0 | 0 | 0 | 0 | US$ 0 |

</Accordion>

<div id="user-journey-with-re-engagement" />

<Accordion title="Jornada do usuário com reengajamento">

A jornada do usuário é idêntica à anterior. A diferença é que a linha de produtos optou pelo reengajamento.

[![](https://files.readme.io/9981d9d9ffc20841778f390941f7759d9ff0c3e630e14e4578dc001c9d692cbf-45444733163409.png)](https://files.readme.io/9981d9d9ffc20841778f390941f7759d9ff0c3e630e14e4578dc001c9d692cbf-45444733163409.png)

Nesse caso, a janela de inatividade de retargeting determina se o login na web impulsionado pela Meta é considerado um evento de reengajamento. A janela se abre depois da última vez em que o CUID foi registrado, ou seja, no cadastro no mobile. Se houver um intervalo de tempo suficiente antes do login na web, o que significa que o login ocorreu fora da janela de inatividade para reengajamento, a Meta recebe crédito pelo reengajamento.

Depois que a Meta é creditada, a janela de reengajamento é aberta. Quaisquer eventos in-app que ocorram dentro dessa janela são atribuídos à Meta. No nosso exemplo, a compra de US$ 100 ocorre dentro da janela de reengajamento e é atribuída à Meta. A compra de US$ 50, por sua vez, ocorre fora da janela de reengajamento e é atribuída novamente ao Google.

| Fonte de mídia | Total de atribuições | Aquisição de usuários | Reengajamentos | Ativações de plataformas | Mobile | Web | Dados de LTV: 5 anos |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Google | 1 | 1 | 0 | 1 | 1 | 0 | US$ 50 |
| Meta | 1 | 0 | 1 | 1 | 0 | 1 | US$ 100 |

</Accordion>

<div id="set-up-cross-platform-re-engagement-attribution" />

## Configurar a atribuição cross-platform de reengajamento

Para configurar a atribuição cross-platform de reengajamento, você precisa definir algumas configurações específicas para reengajamento na AppsFlyer, além de configurar sua linha de produtos. Para mais informações, descubra <Anchor target="_blank" href="/marketers/pt/docs/product-line-group-apps-for-cross-platform-attribution#como-criar-uma-linha-de-produto">como criar uma linha de produtos</Anchor>.

<div id="view-cross-platform-attribution-results" />

## Ver resultados de atribuição cross-platform

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/end-user-events-cross-platform-report-in-data-locker">[Beta] Data Locker: relatório de eventos cross-platform realizados por usuários finais</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#crossplatform-dashboard">Dashboard cross-platform</Anchor>

<div data-zendesk-anchors="about-cross-platform-re-engagement-attribution=sobre-a-atribui%C3%A7%C3%A3o-cross-platform-de-reengajamento h_01KNEVA6TAJZRZYS11Z0Q59AQJ=sobre-a-atribui%C3%A7%C3%A3o-cross-platform-de-reengajamento how-does-re-engagement-attribution-work=como-funciona-a-atribui%C3%A7%C3%A3o-de-reengajamento h_01KNEVA6TASWZ0S6HH5QT0ZZF0=como-funciona-a-atribui%C3%A7%C3%A3o-de-reengajamento a-cross-platform-re-engagement-user-journey-example=jornada-de-reengajamento-cross-platform h_01KNEVA6TA5PVF5E8YWFE13QAQ=jornada-de-reengajamento-cross-platform h_01KNEVA6TAPFZ48SHNN1F8Y8P5=user-journey-without-re-engagement h_01KNEVA6TA0ZRG6Z6A38JGEFAQ=user-journey-with-re-engagement set-up-cross-platform-re-engagement-attribution=configurar-a-atribui%C3%A7%C3%A3o-cross-platform-de-reengajamento h_01KNEVH8QZ2K59BJX0HZ908FXR=configurar-a-atribui%C3%A7%C3%A3o-cross-platform-de-reengajamento view-cross-platform-attribution-results=ver-resultados-de-atribui%C3%A7%C3%A3o-cross-platform h_01KNEVH8QZNV046JAF9PRADK4E=ver-resultados-de-atribui%C3%A7%C3%A3o-cross-platform h_01KNEVH8QZK4J276D8RPBH15JY=veja-tamb%C3%A9m" />

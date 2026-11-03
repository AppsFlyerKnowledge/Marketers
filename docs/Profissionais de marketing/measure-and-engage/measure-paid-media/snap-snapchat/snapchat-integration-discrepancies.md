---
title: Discrepâncias de integração do Snapchat
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-24T08:57:20Z'
  edited_at: '2026-08-18T00:32:40Z'
  id: 4417686973841
  locale: pt
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/pt/articles/4417686973841
---
> **Visão geral:** Saiba mais sobre as diferentes discrepâncias entre os dashboards do Snapchat e da AppsFlyer e os relatórios.

Em certos casos, os anunciantes podem ver menos instalações no dashboard da AppsFlyer do que no dashboard do Snapchat Ads Manager. Às vezes, a discrepância pode ser resolvida fazendo alterações nas configurações do dashboard da AppsFlyer ou do Snapchat Ads Manager (por exemplo, configurações de fuso horário, janelas de atribuição etc.). No entanto, é esperado que haja discrepância entre os dois dashboards. Os anunciantes devem considerar o dashboard da AppsFlyer como fonte de verdade ao avaliar o CPI e a performance.

Os anunciantes devem estar cientes das causas a seguir e considerar tomar as medidas necessárias.

## Fontes de discrepâncias e soluções

Veja abaixo algumas causas de discrepâncias e possíveis soluções.

### Diferentes janelas de lookback

Por padrão, o Snapchat Ads Manager e a AppsFlyer têm janelas de atribuição diferentes.

| Janela de lookback | Snapchat Ads Manager | A AppsFlyer |
| --- | --- | --- |
| Janela de lookback de atribuição de cliques | 28 dias | 7 dias por padrão (pode ser configurada para 1-30 dias) |
| Janela de lookback de atribuição de exibição | 1 dia | 1 dia por padrão (pode ser configurada para 1-48 horas) |

> 👍 **Soluções**
>
> 1. Configure a janela de atribuição na AppsFlyer para corresponder aos valores padrão do Snapchat.
> 2. Os anunciantes podem selecionar janelas de atribuição no dashboard do Ads Manager para corresponder ao que definiram como padrão no dashboard do parceiro de atribuição (MMP). Entre em contato com seu CSM do Snapchat para incluir sua conta na allowlist e ativar esse recurso.

### Diferenças de fuso horário

Por padrão, o Ads Manager usa o fuso horário PST, enquanto a AppsFlyer usa UTC +0 por padrão. Como resultado, por exemplo, o Snapchat pode atribuir uma instalação à sexta-feira, enquanto a AppsFlyer a atribui ao sábado.

> 👍 **solução**
>
> Configure PST como o fuso horário de cada aplicativo na AppsFlyer. Clique <Anchor target="_blank" href="/marketers/pt/docs/changing-app-time-zone-settings">aqui</Anchor> para ver detalhes sobre como alterar o fuso horário de aplicativos existentes.

### Atribuição de fonte multicanal

Um usuário pode interagir com um anúncio do mesmo aplicativo em várias plataformas, especialmente em campanhas multiplataforma muito grandes. Quando o usuário instala o aplicativo, várias plataformas podem reivindicar o crédito pela instalação.

Snapchat Ads Manager:

* Conta cada instalação que ocorre dentro da janela de atribuição como uma instalação atribuída ao Snapchat.
* Atribui eventos in-app por até 28 dias após a instalação.

AppsFlyer:

* Aplica a atribuição de último toque e credita apenas a última plataforma que exibiu ao usuário um anúncio que levou a uma instalação.
* Atribui eventos in-app à fonte da instalação por até 180 dias.

Isso pode levar a discrepâncias de até 40% entre a AppsFlyer e o Snapchat Ads Manager.

> 👍 **solução**
>
> O Snapchat é apenas um app mobile, enquanto outras plataformas possuem vários apps mobile ou ad networks/exchanges mobile. Devido ao alcance adicional delas em várias propriedades, é possível que concorrentes ganhem o último toque, mas o Snapchat ainda esteja gerando valor significativo.
>
> Em última análise, a AppsFlyer deve ser o dashboard usado para avaliar o eCPI e a performance. Quando houver uma discrepância, use a AppsFlyer como fonte de verdade. Lembre-se de que, para avaliar totalmente o impacto das suas campanhas do Snapchat, você deve trabalhar com a AppsFlyer para manter um registro do volume de conversões em que o Snapchat contribuiu para a conversão, mas não foi o último toque. Há valor em entender isso, mesmo que você atribua com base no último toque.
>
> Para gerenciar a discrepância, os anunciantes devem manter registros da porcentagem aproximada do total de conversões em que o Snapchat foi um contribuidor, mas não o último contribuidor, e assim criar um novo objetivo de eCPI para o Snapchat com base nesse delta aproximado.

### Menos instalações nos dados brutos

Em certos casos, devido a restrições de dados brutos do Snapchat, as instalações via <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary?query=glossary#aggregated-advancedprivacy">Aggregated Advanced Privacy</Anchor> não aparecerão nos Relatórios de dados brutos. Isso significa que os anunciantes podem ver na plataforma AppsFlyer menos instalações nos dados brutos do que nos dados agregados.

> 📄 **Veja também**
>
> <Anchor target="_blank" href="/marketers/pt/docs/skan-interoperation-with-snapchat">Interoperação Snapchat e AppsFlyer SKAdNetwork</Anchor>

<div data-zendesk-anchors="source-of-discrepancies-and-solutions=fontes-de-discrep%C3%A2ncias-e-solu%C3%A7%C3%B5es h_01HE7RM7ME5JTFFC2MYSBG6SWC=fontes-de-discrep%C3%A2ncias-e-solu%C3%A7%C3%B5es different-lookback-windows=diferentes-janelas-de-lookback h_01HE7RM7MEYAZ42A1Y7X8J008Q=diferentes-janelas-de-lookback h_01HE7RM7ME31WACZRZDXRW5CNR=solu%C3%A7%C3%B5es time-zone-differences=diferen%C3%A7as-de-fuso-hor%C3%A1rio h_01HE7RM7METGPE38QV8FAMW9WA=diferen%C3%A7as-de-fuso-hor%C3%A1rio h_01HE7RM7MEC91WZDZQMXZ4Q7DV=solu%C3%A7%C3%A3o multichannel-source-attribution=atribui%C3%A7%C3%A3o-de-fonte-multicanal h_01HE7RM7ME2NAB9ET38P5JD82E=atribui%C3%A7%C3%A3o-de-fonte-multicanal h_01HE7RM7MFP65KYHFDZZTC8K3J=solu%C3%A7%C3%A3o-1 fewer-installs-in-raw-data=menos-instala%C3%A7%C3%B5es-nos-dados-brutos h_01HE7RM7MFR4CSEK2HCZWB8BT9=menos-instala%C3%A7%C3%B5es-nos-dados-brutos h_01HE7RP6VPPAY2CCSNTJ0RVSXM=veja-tamb%C3%A9m" />

---
title: Cotas de geração de relatórios (limitações de taxa)
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2014-05-01T12:55:30Z'
  edited_at: '2026-10-20T03:41:35Z'
  id: 207034366
  locale: pt
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/pt/articles/207034366
---
> **At a glance:** Um mecanismo de cota (limitação de taxa) limita o número de relatórios que você pode gerar por dia pela Pull API e pelas páginas de exportação de dados.

## Limites de taxa para relatórios

A cota limita o número de relatórios que você pode gerar por dia por tipo de relatório. A cota varia de acordo com seu plano de assinatura.

**Princípios:**

* **Agências:** as agências e os anunciantes têm cotas separadas para a Pull API. A cota é aplicada por relatório, dia e aplicativo, da mesma forma em ambos os casos. Para relatórios das páginas de dados de exportação, agências e anunciantes também têm cotas separadas. Se você costuma atingir o limite da cota, entre em contato com seu Account Executive.
* **Ad networks:** os relatórios gerados por ad networks não contam para a cota do anunciante.
* **Dia:** as cotas se aplicam por dia corrido, a partir de 00:00 UTC.

### Relatórios agregados e analíticos

| Ferramenta de entrega de dados | Quota |
| --- | --- |
| Pull API agregada | <ul><li>Até 2 dias no intervalo de datas:<ul><li>Máximo de 1 chamada por minuto por aplicativo para cada relatório</li></ul></li><li>Intervalo de datas de 3+ dias: aplicam-se os seguintes limites:<ul><li>Máximo de 120 chamadas por dia para cada conta</li><li>24 chamadas por dia para cada aplicativo</li></ul></li></ul> |
| Página de exportação de dados agregados | Ilimitada |
| Master API | Ilimitada |
| API de Coorte | 60 chamadas por minuto para cada conta |
| Relatórios agregados da SKAN | 10 chamadas por minuto para cada conta |

### Dados brutos

* Uma cota separada se aplica a cada ferramenta de relatório, ou seja, à Pull API e à página de exportação de dados brutos.
* As agências e os anunciantes têm cotas separadas para a Pull API. Os relatórios gerados pela agência não são contabilizados na cota do anunciante. A única exceção ocorre quando uma agência usa o token da API do anunciante em vez do próprio token. Nesse caso, não é possível distinguir as solicitações, que são contabilizadas na cota do anunciante. Para relatórios das páginas de dados de exportação, agências e anunciantes também têm cotas separadas.
* As cotas de pull da API se aplicam por:
  * Relatório
  * Dia
  * Nível do aplicativo
  * Nível da conta
* Para anunciantes, as cotas dependem da sua assinatura da AppsFlyer. as cotas também se aplicam a relatórios que exigem uma assinatura premium.
* As cotas diárias para relatórios de dados brutos da Pull API e relatórios de postback de ad networks são as indicadas nas tabelas a seguir.

Para ver exemplos, consulte as Perguntas frequentes a seguir.

#### Cota diária de dados brutos da Pull API

Os relatórios de dados brutos da Pull API têm as seguintes cotas diárias:

| Esta seção descreve como editar sua configuração existente do Data Locker para adicionar relatórios do Creative Optimization. | Cota diária no nível do aplicativo (relatórios) | Cota diária no nível da conta (relatórios) |
| --- | --- | --- |
| Instalações | 24 | 120 |
| Eventos in-app | 12 | 60 |

> 📘 **Importante!**
>
> As cotas se aplicam por tipo de relatório, então cada tipo de relatório tem uma cota separada.

#### Cota diária de relatórios de postback das ad networks

As ad networks podem obter os seguintes tipos de relatórios de postback:

| Grupo de postback | Tipo de relatório  <br />(cada tipo de relatório tem uma cota separada) | Cota diária no nível do aplicativo | Cota diária no nível da conta |
| --- | --- | --- | --- |
| Postbacks para atribuição | <ul><li>de instalações</li><li>Conversões de retargeting</li></ul> | 24 | 120 |
| Postbacks para eventos in-app | <ul><li>https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg</li><li>Retargeting de eventos in-app</li></ul> | 12 | 60 |

## Perguntas frequentes

* P: Para um determinado aplicativo, posso gerar 24 relatórios de instalação orgânica usando a Pull API e outros 24 relatórios usando a página de exportação de dados brutos?  
  A: Sim. A cota por ferramenta de relatório é separada.
* P: Para um determinado aplicativo, usando a página de exportação de dados brutos, posso gerar 24 relatórios de instalações orgânicas, 24 relatórios de instalações não orgânicas e 24 relatórios de conversão de retargeting?  
  R: Sim. A cota por tipo de relatório é separada.
* P: Tenho 25 aplicativos na minha conta. Posso gerar 10 relatórios de instalação orgânica para cada aplicativo?  
  R: Não. Isso resulta em um total de 250 relatórios, o que excede a cota de 120 no nível da conta.
* P: Os relatórios da Pull API gerados pela agência são contabilizados na cota do anunciante?  
  R: Não. As agências e os anunciantes têm cotas separadas para a Pull API. Os relatórios gerados pela agência não são contabilizados na cota do anunciante. A única exceção é quando uma agência usa o token da API do anunciante em vez do próprio token, caso em que essas solicitações contam como solicitações do anunciante.

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/data-availability-windows">Janelas de disponibilidade de dados</Anchor>

<div data-zendesk-anchors="rate-limits-for-reports=limites-de-taxa-para-relat%C3%B3rios h_01H9JNZFPSVXPKMEVR1ZR6PSYG=limites-de-taxa-para-relat%C3%B3rios aggregated-and-analytics-reports=relat%C3%B3rios-agregados-e-anal%C3%ADticos h_01H9JNZFPS62A5CFWSXVPN8XM5=relat%C3%B3rios-agregados-e-anal%C3%ADticos raw-data=dados-brutos h_01H9JNZFPSPYWBB2MCZV2R2KX1=dados-brutos h_01M4WW4PAZ64FXVR1QPKE53DS7=cota-di%C3%A1ria-de-dados-brutos-da-pull-api h_01M4WW4PAZFMX9X0DFX1E6F9M0=importante ad-network-postback-reports-daily-quota=cota-di%C3%A1ria-de-relat%C3%B3rios-de-postback-das-ad-networks h_01H9JNZFPSYXZNW81BZTRDS576=cota-di%C3%A1ria-de-relat%C3%B3rios-de-postback-das-ad-networks h_01H9JNZFPT76RAV8JBTY2K75V4=perguntas-frequentes h_01HE7SW3VWRNVY1WFB4YCSAVY6=veja-tamb%C3%A9m" />

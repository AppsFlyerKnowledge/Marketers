---
title: '[Beta] Atribuição cross-platform e user-based'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Cross-Platform Measurement
    - pm-gil-bouchnik
  created_at: '2025-09-16T13:58:09Z'
  edited_at: '2026-08-18T00:08:48Z'
  id: 39104189339793
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/39104189339793
---
> **At a glance:** **Resumo:** Descubra o que é a atribuição cross-platform e user-based e entenda como ela opera e como ela é configurada na AppsFlyer.

## O que é atribuição user-based?

Esse tipo de atribuição é um modelo cross-platform que usa de um <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor> persistente para conectar eventos de conversão entre plataformas. Usando o CUID, esse modelo atribui qualquer atividade à fonte de mídia responsável por impulsionar o primeiro evento de conversão do usuário.

> 📘 **Note**
>
> Se você quiser usar o reengajamento entre plataformas, continue lendo este artigo, pois ele aborda o modelo fundamental de atribuição. Em seguida, você pode ler sobre reengajamento entre plataformas para atribuição baseada no usuário para obter orientações específicas.

### Exemplo de jornada cross-platform

Um usuário clica em um anúncio no Google web, completa o cadastro e faz uma compra no navegador no desktop. Mais tarde, o mesmo usuário clica em um anúncio mobile do Instagram, instala o aplicativo e faz outra compra dentro do app. Uma semana depois, o usuário instala o aplicativo de CTV da marca, faz o login usando o mesmo CUID e se inscreve para uma assinatura paga.

Como o CUID identifica o usuário em todas essas plataformas, e a campanha web do Google foi o primeiro evento não orgânico associado a esse CUID, toda a atividade subsequente – incluindo a compra no aplicativo mobile e a assinatura na CTV – é atribuída à campanha do Google.

### Atribuição user-based vs. device-based

Esse modelo soluciona uma limitação intrínseca da **atribuição device-based**, que trata cada dispositivo como um usuário separado e isola a jornada do usuário entre plataformas. Em contraste, a **atribuição user-based** conecta eventos em diferentes dispositivos através do CUID, oferecendo uma mensuração consistente, atribuição precisa e uma verdadeira compreensão do lifetime value em toda a linha de produtos.

O exemplo abaixo ilustra a diferença entre os dois tipos de atribuição:

[<Image alt="user-journey.png" src="https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png" width="2048px" />](https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png)

Um usuário clica em um anúncio do Meta na web, é redirecionado para o site do anunciante e cria uma conta. Mais tarde, o mesmo usuário instala o aplicativo iOS do anunciante, faz login e faz uma compra de 50 dólares. Alguns dias depois, o usuário vê um anúncio no YouTube, instala o aplicativo de PC do anunciante, faz um novo login e faz uma compra de 100 dólares.

A atribuição device-based atribui $0 ao Meta Ads, enquanto a atribuição user-based atribui $150. A tabela abaixo mostra como essa jornada seria atribuída em cada modelo:

| Evento in-app de compra | **Atribuição device-based** | **Atribuição user-based (CUID)** |
| --- | --- | --- |
| **Compra no aplicativo no PC** ($100) | Atribuída como **orgânica** (nenhum clique registrado no dispositivo) | Atribuída ao **Meta** (mesmo usuário identificado via CUID) |
| **Total de compras** ($150) | Atribuída ao **YouTube** (com base em interações recentes a nível de dispositivo) | Atribuída ao **Meta** (no anúncio inicial na web) |
| **Compra no aplicativo iOS** ($50) | **50 dólares como orgânico**, **100 dólares para o YouTube** (dividido entre campanhas) | **$150 no total** atribuídos ao Meta (fonte unificada) |

### O que faz com que um evento se torne um candidato para a atribuição cross-platform?

Um evento é considerado um **candidato para a atribuição cross-platform** quando ele atende a **todas** as seguintes condições:

* **O CUID está presente:** p evento deve incluir um <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor> válido. Esse é um identificador persistente, fornecido pelo anunciante (por exemplo, login ID ou email anonimizado) que identifica o usuário entre dispositivos e plataformas.
  * Se um evento não tiver um CUID mas compartilhar do mesmo `appsflyer_id`, a AppsFlyer pode preencher o CUID em uma janela de processamento curta, de até 4 horas antes do primeiro evento recebido com um CUID. Para mais informações, consulte [janela de processamento de enriquecimento de CUID](#janela-de-processamento-de-enriquecimento-de-cuid) abaixo.
  * Eventos que são enviados sem um CUID e que não podem ser enriquecidos através de um processo de enriquecimento continuam a ser incluídos na atribuição cross-platform. Nesses casos, a atribuição é determinada usando o método de atribuição a nível de dispositivo (clássico).
* **Ele pertence a uma linha de produtos:** o aplicativo que gera o evento deve fazer parte de uma **linha de produtos**, um agrupamento de aplicativos relacionados (por exemplo, iOS, Android, CTV) à mesma marca, para as quais a atribuição é definida e configurada coletivamente. Para mais informações, veja <Anchor target="_blank" href="/marketers/pt/docs/product-line-group-apps-for-cross-platform-attribution#sobre-a-linha-de-produto">agrupar aplicativos para atribuição cross-platform</Anchor>.
* **Dentro da janela de restauração da inatividade:** o evento deve se enquadrar no âmbito da **janela de inatividade**, um período configurável (por exemplo, 7 a 390 dias) durante o qual um CUID ainda é considerado ativo e elegível para atribuição dentro de uma determinada linha de produtos. Se o CUID não for identificado dentro dessa janela, o seu mapeamento de atribuição anterior será descartado.
* **Os campos de atribuição a nível de dispositivo estão presentes:** o evento já deve conter **parâmetros de atribuição a nível de dispositivo** válidos (por exemplo, fonte de mídia, campaign ID) derivados do modelo clássico de atribuição device-based da AppsFlyer.

### Como a fonte de atribuição é determinada?

Esse modelo atribui todos os eventos para um usuários específico (CUID) à **fonte de mídia original** que impulsionou a primeira conversão do usuário.

A fonte de mídia originalmente atribuída é determinada usando a seguinte lógica:

* Para cada evento in-app com um CUID em uma linha de produtos, a AppsFlyer identifica o evento de lançamento **mais antigo** desse CUID (ou seja, um evento de lançamento com uma fonte de mídia válida).
* A fonte de mídia atribuída a esse evento pela atribuição clássica é considerada a fonte de atribuição para o evento in-app.
* Essa fonte de mídia é usada como a **fonte de atribuição cross-platform** para todos os eventos subsequentes associados a essa CUID e linha de produtos.
* Se um evento in-app não possuir um CUID, a AppsFlyer tenta preenchê-lo em uma [janela de processamento de enriquecimento](#janela-de-processamento-de-enriquecimento-de-cuid) que dura de 1 a 4 horas.
* Se um evento sem CUID ocorrer fora da [janela de enriquecimento](#janela-de-processamento-de-enriquecimento-de-cuid) definida, ele ainda será incluído na atribuição cross-platform. Esses eventos são atribuídos através do método de atribuição device-level (clássico).

> 📘 **Note**
>
> A AppsFlyer apenas vincula CUIDs idênticos **dentro da mesma linha de produtos**. Não tentamos vincular, inferir ou compartilhar CUIDs entre diferentes linhas de produtos ou clientes. Isso garante uma metodologia rigorosa, que garante a compliance com a privacidade, mantendo os dados de cada cliente isolados e independentes.

#### Janela de processamento de enriquecimento de CUID

A janela de processamento de enriquecimento de CUID é o período (1–4 horas) durante o qual a AppsFlyer processa eventos recém-chegados para preencher customer user IDs (CUIDs) que estão em falta. Isso permite que a atribuição cross-platform ocorra, mesmo que alguns eventos in-app sejam enviados sem um CUID.

**Como funciona o enriquecimento de CUID**

* A cada 1 a 4 horas, a AppsFlyer executa um trabalho de processamento.
* Se um evento chegar sem um CUID mas compartilhar do mesmo `appsflyer_id` que um outro evento que possui um CUID, a AppsFlyer preenche o CUID em falta.
* Isso se aplica apenas a eventos recebidos durante a janela de processamento.

**Exemplo de enriquecimento de CUID**

* **8:01**: um evento de *primeira abertura* é registrado com `appsflyer_id = XYZ`.
* **9:00**: um evento de *cadastro* é registrado com `cuid = 123` e `appsflyer_id = XYZ`.
* **12:00**: a janela de processamento de 4 horas termina. A AppsFlyer faz a conexão retroativa do `cuid = 123` ao evento de *primeira abertura*.
* **12:30**: Um evento de *purchase* com `appsflyer_id = XYZ`  é registrado, mas não tem
* **12:30**: um evento de *compra* é registrado com `appsflyer_id = XYZ` mas sem CUID. Como o evento foi enviado depois que a janela terminou, a AppsFlyer não conecta o `cuid = 123` a esse evento.

**Limitações de enriquecimento de CUID**

* Eventos sem um CUID enviados **fora da janela de processamento de 1–4 horas** são atribuídos usando a atribuição clássica da AppsFlyer e são adicionados aos resultados do método de atribuição cross-platform.
* O enriquecimento de CUID **não é aplicado retroativamente** fora da janela de processamento.

> 👍 **Tip**
>
> Para maximizar a correspondência entre plataformas, inclua sempre um CUID em cada evento in-app enviado.

## Configurar a atribuição criss-platform

Para configurar a atribuição cross-platform, você deve aplicar algumas configurações na AppsFlyer e implementar funções específicas do SDK ao código do seu aplicativo.

* **Na AppsFlyer**, atribua os seus aplicativos a uma linha de produtos, selecione a atribuição cross-platform e especifique a janela de restauração. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/product-line-group-apps-for-cross-platform-attribution#como-configurar-uma-linha-de-produto">criar uma linha de produtos</Anchor>.
* **No seu aplicativo**, configure o SDK daAppsFlyer para enviar eventos com CUIDs. Se precisar de instruções para desenvolvedores, acesse o artigo [Set Customer User ID](https://dev.appsflyer.com/hc/docs/set-customer-user-id).

## Ver resultados de atribuição cross-platform

* Para ver resultados de atribuição cross-platform, consulte o artigo <Anchor target="_blank" href="/marketers/pt/docs/end-user-events-cross-platform-report-in-data-locker">Data Locker: relatório de eventos cross-platform realizados por usuários finais</Anchor>.
* **My Dashboards:** Disponível pelo modelo "Cross Platform". Para mais informações sobre como selecionar um modelo de dashboard, consulte <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#create-dashboard">Criar um dashboard personalizado</Anchor>.

## Perguntas frequentes (FAQs)

<Accordion title="Por que os resultados da atribuição entre plataformas são diferentes dos resultados da atribuição clássica da AppsFlyer?">

Existem alguns motivos que podem explicar as diferenças.

#### Lógica de atribuição diferente

* **A atribuição entre plataformas é baseada no usuário.** Ela vincula a atividade usando o CUID e atribui toda a atividade subsequente do usuário à coorte da campanha do usuário dentro da linha de produtos.
* **A atribuição clássica da AppsFlyer é centrada no dispositivo** (um ID da AppsFlyer por dispositivo). Isso significa que o mesmo usuário do mundo real em vários dispositivos ou plataformas pode ser contabilizado como usuários separados e creditado a touchpoints diferentes.

**Impacto:** Mesmo que a receita geral seja semelhante, a receita por canal de mídia ou campanha pode mudar significativamente.

#### Data de atribuição diferente

* Nos resultados clássicos de coorte e LTV, a data de atribuição reflete a data da primeira abertura do aplicativo pelo usuário ou, no caso da web, a data inicial de aquisição do usuário.
* Na visualização de UA entre plataformas, a data de atribuição representa a primeira data de aquisição do usuário em todas as plataformas. Quando o reengajamento entre plataformas está ativado, a data de atribuição reflete a abertura não orgânica mais recente do aplicativo.

Como resultado, algumas métricas na atribuição entre plataformas podem ser atribuídas a datas anteriores em comparação com a atribuição clássica.

</Accordion>

<div data-zendesk-anchors="what-is-userbased-attribution=o-que-%C3%A9-atribui%C3%A7%C3%A3o-user-based h_01K59D3JXN9P5ZN40WX957CHKC=o-que-%C3%A9-atribui%C3%A7%C3%A3o-user-based a-crossplatform-user-journey-example=exemplo-de-jornada-cross-platform h_01K59D3JXN4WJ3HN0AXN58N877=exemplo-de-jornada-cross-platform userbased-vs-devicebased-attribution=atribui%C3%A7%C3%A3o-user-based-vs-device-based h_01K59D3JXN3EXS90N2AX7DXV3B=atribui%C3%A7%C3%A3o-user-based-vs-device-based what-makes-an-event-a-candidate-for-crossplatform-attribution=o-que-faz-com-que-um-evento-se-torne-um-candidato-para-a-atribui%C3%A7%C3%A3o-cross-platform h_01K59D3JXNNYZHYFAPRH50E4Z4=o-que-faz-com-que-um-evento-se-torne-um-candidato-para-a-atribui%C3%A7%C3%A3o-cross-platform how-is-the-attribution-source-determined=como-a-fonte-de-atribui%C3%A7%C3%A3o-%C3%A9-determinada h_01K59D3JXNGNZYAYPG13SZ98V1=como-a-fonte-de-atribui%C3%A7%C3%A3o-%C3%A9-determinada the-cuid-enrichment-processing-window=janela-de-processamento-de-enriquecimento-de-cuid h_01K59D3JXN5CYVB6F84DTRBZS9=janela-de-processamento-de-enriquecimento-de-cuid set-up-crossplatform-attribution=configurar-a-atribui%C3%A7%C3%A3o-criss-platform h_01K59D3JXNH84WMZ6PQ4BVF44B=configurar-a-atribui%C3%A7%C3%A3o-criss-platform view-crossplatform-attribution-results=ver-resultados-de-atribui%C3%A7%C3%A3o-cross-platform h_01K59D3JXNGGG4AKEXM9Q9KA6A=ver-resultados-de-atribui%C3%A7%C3%A3o-cross-platform frequently-asked-questions-faqs=perguntas-frequentes-faqs h_01KNSGZXB1EFD78QSA8B28XCN9=perguntas-frequentes-faqs different-attribution-logic=l%C3%B3gica-de-atribui%C3%A7%C3%A3o-diferente h_01KNSG79PE8RFRSHYWGTGWN4VV=l%C3%B3gica-de-atribui%C3%A7%C3%A3o-diferente different-attribution-date=data-de-atribui%C3%A7%C3%A3o-diferente h_01KNSG79PEBXX0H14B9SQZ0W83=data-de-atribui%C3%A7%C3%A3o-diferente" />

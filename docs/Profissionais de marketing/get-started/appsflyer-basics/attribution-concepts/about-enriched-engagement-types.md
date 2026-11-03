---
title: Engajamentos enriquecidos
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
  created_at: '2024-01-21T13:45:23Z'
  edited_at: '2026-08-18T00:09:05Z'
  id: 21837486015889
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/21837486015889
---
> **Resumo:** Embora os anúncios tenham se tornado cada vez mais sofisticados nos últimos anos, os relatórios permaneceram os mesmos, focando principalmente na atribuição de visualização e clique. Os engajamentos enriquecidos refletem todo o espectro do engajamento e intencionalidade dos usuários quando eles visualizam ou interagem com um anúncio.

## Introdução

Nos últimos anos, novos tipos de criativos, como os anúncios reproduzíveis, puláveis e em vídeos curtos, foram introduzidos ao mercado, oferecendo novas maneiras de se conectar com os usuários. Esses novos formatos são bem diferentes dos anúncios estáticos e simples do passado, e permitem que os anunciantes tenham acesso a uma variedade de recursos e formatos mais completos.

No entanto, ainda que os tipos de anúncios tenham se tornado mais sofisticados, os relatórios permaneceram os mesmos, focando principalmente na atribuição de visualização e clique. Diferentes tipos de engajamentos possuem diferentes pesos, níveis de intenção e impacto, mas as metodologias de mensuração atuais ignoram essa nova realidade. Naturalmente, as ad networks desejam garantir que os níveis de intenção e engajamento com um anúncio sejam representados da melhor forma possível. Consequentemente, isso levou a uma falta de padronização no ecossistema, fazendo com que os anunciantes tenham apenas uma compreensão parcial dos resultados obtidos com seu investimento em anúncios.

Em colaboração com as principais ad networks da indústria, a AppsFlyer decidiu introduzir um novo padrão de engajamento, com o intuito de proporcionar confiança e transparência para todo o ecossistema. Esse novo padrão de qualidade reflete todo o espectro do engajamento e intencionalidade dos usuários quando eles visualizam ou interagem com um anúncio, desde uma exposição momentânea até uma resposta direta. Essa estrutura garante que esses padrões sejam mantidos dentro e fora de todo o ecossistema de parceiros da AppsFlyer. Por meio dos tipos de engajamentos enriquecidos, os anunciantes podem garantir que eles terão uma visão completa e padronizada da performance dos seus investimentos em anúncios, aproveitando esses insights para melhorar seu budget e ROAS.

## Engajamentos enriquecidos

Esse novo framework oferece visibilidade sobre diferentes nuances da jornada dos usuários, indicando quando uma visualização foi ativa (por exemplo, quando um usuário assistiu a mais de 5 segundos de um vídeo pulável) e quando cliques geraram engajamentos mais significativos do que a abertura de um app ou o acesso à loja de aplicativos. Com isso, os profissionais de marketing acessam mais insights sobre as ações dos seus usuários, o que, por sua vez, leva a uma distribuição melhor do budget e a um aumento no ROI.

Listamos abaixo os novos tipos de engajamento:

| engagement\_type | Descrição |
| --- | --- |
| <span id="preload"></span>preload | O aplicativo é pré-carregado pelo fabricante do dispositivo ou por seu fornecedor na primeira vez em que ele é ativado. Ou então, um assistente sugere que os usuários façam o download do aplicativo quando o dispositivo é ativado pela primeira vez. |
| <span id="click_to_download"></span>click\_to\_download | Quando o usuário interage com um anúncio, o aplicativo é automaticamente baixado e instalado no dispositivo, sem o redirecionamento para uma loja de aplicativos. |
| <span id="click_to_app"></span>click\_to\_app | Um clique em anúncio, leitura de QR code, deep link ou qualquer outro tipo de clique que redireciona o usuário para o app ou para a loja de aplicativos relevante, incentivando-o a baixar o aplicativo. |
| <span id="engaged_click"></span>engaged\_click | Um clique que mantém o usuário engajado com o anúncio dentro de um mesmo contexto, e NÃO o direciona para uma loja de aplicativos ou para o aplicativo em si. |
| <span id="engaged_view"></span>engaged\_view | Uma visualização ativa é quando ocorre uma visualização significativa, em vídeos que podem ser pulados, vídeos que oferecem recompensas ou anúncios renderizados do storekit. Por exemplo, quando um usuário assiste a um anúncio em vídeo que pode ser pulado por pelo menos 5 segundos após a opção de pular aparecer. |
| <span id="view"></span>view | Uma visualização (view) de um anúncio ocorre quando um anúncio é renderizado e uma impressão é identificada. |
| <span id="listening"></span>listening | Essa ação ocorre quando um usuário ouve um anúncio em áudio, como um anúncio em um podcast. |

## **Prioridade de atribuição e janela de lookback do EET**

O framework dos Tipos de Engajamentos Enriquecidos não afeta a prioridade de atribuição do tipo de engajamento. Portanto, a introdução do EET não deve afetar sua taxa de instalação e conversão.

A tabela abaixo especifica a <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#prioridades-do-método-de-atribuição-cascata-de-atribuição">prioridade de atribuição</Anchor> e a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows#janelas-de-lookback">janela de lookback</Anchor> de cada tipo de engajamento:

<table><thead><tr><th>com o anúncios</th><th>Tipo de engajamento</th><th>Prioridade de atribuição\*</th><th>Janela de lookback\*\*</th></tr></thead><tbody><tr><td rowspan="2">Baixar</td><td>preload</td><td>1</td><td>1h-180d | padrão: 90d</td></tr><tr><td>click_to_download</td><td>2</td><td>1h-30d | padrão: 7d</td></tr><tr><td rowspan="2">Clique</td><td>click_to_app</td><td>2</td><td>1h-30d | padrão: 7d</td></tr><tr><td>engaged_click</td><td>2</td><td>1h-7d | padrão: 2d </td></tr><tr><td rowspan="3">Impressão</td><td>engaged_view</td><td>2</td><td>1h-7d | padrão: 2d</td></tr><tr><td>view</td><td>3</td><td>1h-24h | padrão: 24h</td></tr><tr><td>listening</td><td>3</td><td>1h-24h | padrão: 24h</td></tr></tbody></table>

Quando um tipo de engajamento não é relatado, a prioridade padrão é definida como (2 para cliques, 3 para impressões).

<strong>As janelas de lookback para `engaged_click` e `engaged_view` só podem ser configuradas para não SRNs. Para SRNs, `engaged_click` e `engaged_view` compartilham a mesma janela de lookback que os cliques e, portanto, é configurada pelos sliders de </strong>Install Click-Through Attribution Lookback.

## Quais networks podem relatar engaged views e engaged clicks?

A tabela abaixo lista as network qualificadas pela AppsFlyer para relatar `engaged_clicks` e `engaged_views`.  Networks que desejam fazer parte dessa lista devem entrar em contato com a AppsFlyer.

| **Ad network** | **Visualizações engajadas** | **Engaged clicks** |
| --- | --- | --- |
| facebook\_int | Sim |  |
| googleadwords\_int | Sim |  |
| tiktokglobal\_int* | Sim | Sim |
| twitter\_int | Sim | Sim |
| "snapchat\_int" | Sim | Sim |
| bytedanceglobal\_int | Sim | Sim |
| aarki\_int | Sim | Sim |
| adjoe\_int |  | Sim |
| appier\_int | Sim | Sim |
| appnext\_int | Sim |  |
| bidease\_int | Sim | Sim |
| bigabid\_int | Sim | Sim |
| inmobidsp\_int | Sim | Sim |
| ironsource\_int | Sim |  |
| lap\_int | Sim |  |
| liftoff\_int | Sim | Sim |
| mdsp\_int | Sim | Sim |
| mintegral\_int | Sim | Sim |
| onedigitalturbine\_int | Sim |  |
| personalyrtb\_int | Sim | Sim |
| pinterest\_int | Sim |  |
| remerge\_int | Sim | Sim |
| revx\_int | Sim | Sim |
| rtbhouse\_int | Sim | Sim |
| smadex\_int | Sim | Sim |
| trademob\_int | Sim | Sim |
| unityads\_int | Sim | Sim |
| vungle\_int | Sim |  |
| yahoojapan\_int | Sim |  |
| yandexdirect\_int | Sim | Sim |
| youappi\_int | Sim | Sim |
| jampp\_int | Sim | Sim |

* O TikTok é compatível com o engajamento enriquecido, mas suas engaged views não foram devidamente refletidas nos relatórios. A AppsFlyer está trabalhando com o TikTok para resolver esse problema.

> 📘 **Nota**
>
> **Nem todas as networks listadas realmente oferecem suporte para engaged clicks e engaged views.** Para saber se uma network qualificada específica oferece suporte, na prática, a `engaged_clicks` e `engaged_views`. Para saber se uma network específica oferece suporte para `engaged_clicks` e `engaged_views`, veja o relatório de dados brutos que contém os engajamentos relatados pela network e veja se o parâmetro `engagement_type` foi preenchido com os valores acima.

## Configurar janelas de lookback para engaged clicks e engaged views

**Para configurar essas janelas de lookback:**

1. Na AppsFlyer, vá para o menu lateral e selecione **Colaborar** > **Integrações ativas**.
2. Escolha o parceiro integrado.
3. Configure as janelas de lookback para a atribuição de engaged view-through e click-through.

   > 📘 **Nota**
   >
   > As janelas de lookback de engaged click e engaged view sempre são configuradas na aba de Integração do parceiro, em contraste com as janelas de lookback de view-through e click-through, que podem ser configuradas nos links de atribuição.
   >
   > Para SRNs, a configuração da janela de lookback de click-through também determina as janelas de lookback de engaged click e engaged view.

4. Clique em **Salvar integração**.

## Visualizar e analisar dados de EET

### Relatórios de dados brutos

`engagement_type` serão comunicados nos relatórios de dados brutos sempre que comunicados pela ad network. Ele também ficará disponível para os dados de colaboradores.

> 📘 **Nota**
>
> Engaged views sempre são incluídas nos relatórios de dados brutos, mesmo quando a atribuição de view-through está desativada.

Quando não houver cliques registrados, como no caso de preload ou deep links, a AppsFlyer definirá o valor relevante (preload ou `click_to_app` para deep links) dentro do novo campo `engagement_type` nos relatórios de dados brutos.

Nos cenários abaixo, o campo `engagement_type` nos relatórios de dados brutos recebe os valores `click_unspecified` e `impression_unspecified`.

* Quando há uma discrepância entre o engajamento (click/impression) e o tipo de engajamento.
* Quando `af_engagement_type` não é enviado ou é enviado com um valor vazio.

Para ver o tipo de engajamento nos relatórios de dados brutos, os anunciantes têm de selecionar estes campos no produto de dados brutos relevante (o tipo de engajamento e o tipo de engajamento dos contribuidores não são selecionados por predefinição).

### Painéis

A dimensão do tipo de engajamento foi adicionada aos dashboards.

[![eet-dashboard.png](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)

> 📘 **Nota**
>
> Engaged views sempre são exibidas no dashboard, mesmo quando a atribuição de view-through está desativada.

### Como calcular **Instalações por Mil (IPM)**

As impressões totais incluem tanto engaged views quando views comuns. Para calcular o IPM, você deve subtrair **engaged views do total de impressões**, pois engaged views são um subconjunto das impressões, e contá-las duas vezes pode inflacionar a contagem de impressões.

## Perguntas frequentes

<div id="what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types" />

<Accordion title="Quais tipos de campanhas são relevantes?">

O engajamento enriquecido pode se aplicar tanto a campanhas de UA quanto a campanhas de retargeting, dependendo da ad network. Para saber se uma ad network oferece suporte a campanhas de retargeting, consulte os relatórios de dados brutos dela e verifique se `engagement_type` está preenchido para a campanha de retargeting.

</Accordion>

<div id="are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard" />

<Accordion title="Engaged clicks e engaged views serão incluídos no valor agregado de cliques e impressões no dashboard de Visão geral?">

Para não SRNs, os valores são incluídos e contabilizados de acordo com o tipo de toque, ou seja, engaged\_click contam como cliques e engaged\_views contam como impressões. Para SRNs, esses valores não serão incluídos ou contados - suporte pendente pelas APIs das SRNs.

</Accordion>

<div id="why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions" />

<Accordion title="Porque não consigo ver o tipo de engajamento nas conversões gp_referrer do Meta?">

O Meta comunica somente engagement\_type=engaged\_view na sua SRN API. Para outras conversões, incluindo gp\_referrer, o tipo de engajamento não está disponível.

</Accordion>

<div id="why-cant-i-see-the-engagement-type-i2" />

<Accordion title="Por que ainda vejo instalações e reengajamentos com attributed_touch_type = impression mesmo depois de desativar a opção de view-through?">

Engaged views são mensuradas e relatadas mesmo se **view-through** estiver desativado. Para identificar essas impressões como engaged views, use a métrica `engagement_type = engaged_views` nos dashboards e relatórios de dados brutos em vez de confiar apenas no `attributed_touch_type`.

</Accordion>

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| <span id="cross-platform-engaged-view-support"></span>Suporte multiplataforma a engaged view | Os engajamento enriquecidos ainda não têm suporte para casos de uso entre plataformas. Mesmo quando `engaged_view` é enviado na URL de impressão, parceiros e anunciantes verão `view` nos dados de atribuição. |
| <span id="owned-media-support"></span>Suporte para mídias próprias | No momento, não há suporte para mídias próprias. Os links usados em mídias próprias não devem incluir o parâmetro `af_engagement_type`. |

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01HNCNA03SZ0MJFQ9XHDFXNTA1=introdu%C3%A7%C3%A3o enriched-engagement-types=engajamentos-enriquecidos h_01HNCNBR7KMT1KQBG5CPZY8YQY=engajamentos-enriquecidos eet-attribution-priority-and-lookback-window=prioridade-de-atribui%C3%A7%C3%A3o-e-janela-de-lookback-do-eet h_01HNCVYDH17NGA8SH5XNWR4P9X=prioridade-de-atribui%C3%A7%C3%A3o-e-janela-de-lookback-do-eet allowed-networks=quais-networks-podem-relatar-engaged-views-e-engaged-clicks h_01J00XFV136HPEHVQNPD934409=quais-networks-podem-relatar-engaged-views-e-engaged-clicks 01JENXRAMPFXTMF7SKDN2Y0E5M=nota set%C2%A0engaged-enrichment-attribution=configurar-janelas-de-lookback-para-engaged-clicks-e-engaged-views h_01J5B6EVM9P3M1SVR3K7WWK02J=configurar-janelas-de-lookback-para-engaged-clicks-e-engaged-views h_01J5B97RCQQG6GN4PCKTQWVF54=nota-1 reporting=visualizar-e-analisar-dados-de-eet h_01J00XFV13YN8QNFZJTGM78EG2=visualizar-e-analisar-dados-de-eet raw-data=relat%C3%B3rios-de-dados-brutos h_01J00XFV132M8TM6EGFZ7A7C3A=relat%C3%B3rios-de-dados-brutos 01JFCPX6WKCWY9RM470H23EDQ0=nota-2 dashboards=pain%C3%A9is h_01J00XFV13W0SD4MD7H4BT1RC9=pain%C3%A9is 01JFCPX6WNCFC0R0N90G4HFYZX=nota-3 how-to-calculate-installs-per-mille-ipm=como-calcular-instala%C3%A7%C3%B5es-por-mil-ipm h_01JHG3EQN6FNJAHX1S91JE3MPT=como-calcular-instala%C3%A7%C3%B5es-por-mil-ipm faqs=perguntas-frequentes 01JFCKK7FK0B5Z7QCZNSX14WF2=perguntas-frequentes h_01HNFTS74KF3YFA0SWRGEQAGYQ=what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types h_01HNYY1S6YQ6YNR6RSY7B8H4EM=are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard h_01HQG5Y4JVNCB60AXR9K2GGD0H=why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions h_01JJP3TT2QMH5Y94C4Q7V6HFP1=why-cant-i-see-the-engagement-type-i2 cross-platform-traits-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />

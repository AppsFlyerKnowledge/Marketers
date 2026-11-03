---
title: Configurar janelas de lookback
metadata:
  keywords:
    - Advertisers
    - look back
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-07T09:27:55Z'
  edited_at: '2026-08-19T00:09:28Z'
  id: 208338403
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/208338403
---
> **Resumo:** personalize as janelas de lookback de click-through e view-through com base em seus contratos com canais de mídia.

## Janelas de lookback

A janela de lookback de atribuição configurável permite que você personalize o período de atribuição com base em seu contrato com os canais de mídia.

Ao definir janelas de lookback de atribuição por canal de mídia, a AppsFlyer atribui de acordo com os termos acordados.

**Tipos de janelas de lookback**:

* **Janela de lookback de clique**: período máximo de tempo após o clique em um anúncio dentro do qual uma instalação pode ser atribuída ao anúncio. As instalações que ocorrem após a janela de lookback são consideradas orgânicas.
* **Janela de lookback de engaged click:** período máximo de tempo após um clique ativo (engaged click) dentro do qual uma instalação pode ser atribuída ao engaged click.  As instalações que ocorrem após a janela de lookback são consideradas orgânicas.
* **Janela de lookback de view-through**: período máximo após a visualização de um anúncio, dentro do qual uma instalação pode ser atribuída ao anúncio.  Instalações que ocorrem após a janela de lookback são consideradas orgânicas.
* Janela de lookback de engaged view **período máximo de tempo após uma visualização ativa (engaged view) dentro do qual uma instalação pode ser atribuída ao engaged view. As instalações que ocorrem após a janela de lookback são consideradas orgânicas.**

#### Janelas de lookback configuráveis por tipo de atribuição

<table><thead><tr><th rowspan="2"><p><strong>Tipo de atribuição</strong></p></th><th rowspan="2"><p><strong>Método de atribuição</strong></p></th><th colspan="2"><strong>Janela de lookback</strong> </th></tr><tr><th><strong>Alcance</strong></th><th><strong>Padrão</strong></th></tr></thead><tbody><tr><td rowspan="3"><p>Cliques</p><p>(Todos os canais de mídia)</p></td><td>Referenciador, Correspondência de ID</td><td>1-30 dias OU<br/>1-23 horas</td><td>7 dias</td></tr><tr><td>Modelagem probabilística (mobile)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptável</a></td><td>Até 24 horas</td></tr><tr><td>Modelagem probabilística (CTV, PC e Console - links de plataforma única)</td><td>Até 7 dias Até 7 dias Até 7 dias (Definido no parâmetro de link <code>af_lookback_window</code>.)</td><td>7 dias</td></tr><tr><td rowspan="2"><p>Engaged click-through</p><p>(<a href="./about-enriched-engagement-types#quais-networks-podem-relatar-engaged-views-e-engaged-clicks" target="_blank">Fontes de mídia</a> não-SRN selecionadas\*)</p></td><td>ID matching</td><td>1-7 dias ou 1-23 horas</td><td>2 dias</td></tr><tr><td>Modelagem probabilística (mobile)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptável</a></td><td>Até 24 horas</td></tr><tr><td rowspan="2"><p>Engaged view-through</p><p>(<a href="./about-enriched-engagement-types#quais-networks-podem-relatar-engaged-views-e-engaged-clicks" target="_blank">Fontes de mídia</a> não-SRN selecionadas\*)</p></td><td>ID matching</td><td>1-7 dias ou 1-23 horas</td><td>2 dias</td></tr><tr><td>Modelagem probabilística (mobile)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptável</a></td><td>Até 24 horas</td></tr><tr><td rowspan="4"><p>Exibição (view-through)</p><p>(<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">Fontes de mídia</a> selecionadas)</p></td><td>ID matching</td><td><p>1 a 24 horas</p><p>[Até 15 de dezembro de 2021, o limite superior era de 7 dias]</p></td><td>24 horas</td></tr><tr><td>Modelagem probabilística (mobile)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptável</a></td><td>Até 24 horas</td></tr><tr><td>Modelagem probabilística (CTV, PC e Console - links de plataforma única)</td><td>Até 7 dias Até 7 dias Até 7 dias (Definido no parâmetro de link <code>af_lookback_window</code>.)</td><td>24 horas</td></tr><tr><td>Modelagem probabilística (CTV, PC e Console - <a href="./set-up-cross-platform-links-for-multi-device-campaigns#características-e-limitações" target="_blank">links de atribuição multiplataforma do OneLink</a>)</td><td>Até 72 horas Até 72 horas Até 72 horas (Definido no parâmetro de link <code>af_xplatform_vt_lookback</code>.)</td><td>24 horas</td></tr></tbody></table>

As janelas de lookback para `engaged_click` e `engaged_view` só podem ser configuradas para não SRNs. Para SRNs, os parâmetros `engaged_click` e `engaged_view` compartilham a mesma janela de lookback que os cliques e, portanto, ela é configurada pelos sliders de `engaged_click`Install Click-Through Attribution Lookbackengaged\_click.

### Janela de lookback de modelagem probabilística

A janela de lookback de modelagem probabilística, usada para garantir a precisão da atribuição, tem as seguintes características:

* Aplica-se a cliques e impressões
* Tem uma duração adaptável de até 24 horas
* Desconsidera as configurações de duração da janela enviadas no link de atribuição
* Tem uma duração mais curta do que as janelas usadas por modelos determinísticos

Para saber mais, leia sobre o <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">método de modelagem probabilística da AppsFlyer</Anchor>.

## Configuração da janela de lookback

A seguir, listamos o processo de configuração da janela de lookback para SRNs e links de atribuição

<Tabs>
<Tab title="Janela de lookback de SRNs">

### Janela de lookback de atribuição para SRNs

> 🚧 **Importante!**
>
> Cada SRN tem seu próprio lookback padrão. Recomendamos combinar o valor da janela de lookback na AppsFlyer com o valor da SRN para minimizar as discrepâncias. Alterá-lo pode resultar em discrepâncias. Para saber mais, veja um [exemplo de discrepância de SRN](#cenários-e-exemplos).

1. na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.
2. Pesquise e selecione a SRN - veja a <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">lista de SRNs compatíveis</Anchor>.
3. Por padrão, a atribuição de view-through está habilitada.
4. Na aba **Integração**, role para baixo até a configuração **Atribuição de click-through** e **Atribuição de view-through**.
5. Use os sliders para definir a janela de atribuição

Veja abaixo cada janela de lookback da SRN:

| SRN | Janela padrão de lookback de click-through (dias) | Janela padrão de lookback de view-through (horas) |
| --- | --- | --- |
| Google | 30 | 24 |
| Meta Ads | 7 | 24 |
| Snapchat | 28 | 24 |
| AppsFlyer | 14 | 24 |
| Anúncios de Busca da Apple | 30 | 24 |
| Oath (YahooGemini) | 7 | 24 |

</Tab>

<Tab title="Janela de lookback de não-SRNs">

<div id="attribution-lookback-window-with-attribution-links" />

### Janela de lookback de atribuição não-SRNs para click-through e view-through

1. na AppsFlyer, vá para o menu lateral e selecione **colaborar** > **integrações ativas**.
2. Pesquise e selecione um parceiro.
3. Por padrão, a atribuição de view-through está habilitada.
4. Clique na aba **link de atribuição**.
5. Escolha se deseja definir o tempo em dias ou horas.
6. Use os sliders abaixo de **Atribuição de click-through** (parâmetro `af_click_lookback`) e **Atribuição de view-through** (parâmetro `af_viewthrough_lookback`) para definir a janela de atribuição.  
   A hora selecionada é refletida automaticamente no link de atribuição.
7. Selecione os parâmetros que correspondem à campanha, ou seja, nome da campanha, conjunto de anúncios, etc.
8. Copie e salve o link - esse é o link que você fornece para a ad network.

<div id="h_01JKWVQB6TTA24VAZ9WVJMGY4X" />

### Janela de lookback de atribuição não-SRNs para engaged click-through e engaged view-through

1. na AppsFlyer, vá para o menu lateral e selecione **colaborar** > **integrações ativas**.
2. Pesquise e selecione um parceiro.
3. Na aba de integração, role para baixo até o slider de **Janela de lookback de install engaged click-through** ou até o slider de **Janela de lookback de install engaged view-through**.
4. Configure a janela de lookback usando os sliders.

<div id="h_01HGFQVP7Q69H5621GXMYZ441N" />

> 👍 **Observação**
>
> * Quer algumas dicas e truques para a configuração de janelas de lookback? Confira esse <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">curso curto e informativo</Anchor> no Portal de Aprendizado da AppsFlyer.
> * [Clique aqui](/docs/set-up-lookback-windows#lookback-in-hours-for-flash-campaigns) para saber quando você deve usar horas para janelas de atribuição.

<div id="lookback-window-in-onelink" />

### Janela de lookback no OneLink™

Você também pode configurar a janela de lookback no OneLink.

1. <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">Configure um OneLink</Anchor>
2. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">Crie um link de atribuição personalizado</Anchor>
3. Em **Avançado**, ative **Personalizar janela de lookback** e configure a janela de lookback.

</Tab>
</Tabs>

## Distribuição das primeiras aberturas do aplicativo

Abaixo está um gráfico que mostra a distribuição das primeiras aberturas do aplicativo desde o dia do engajamento.

[![](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)

O gráfico pode fornecer uma noção melhor do número de usuários que instalam o aplicativo em função da janela de lookback.

A maioria dos usuários que inicia o aplicativo, ou seja, cerca de 97% dos usuários, o faz em até 7 dias após o engajamento com o anúncio. Os 2% restantes o fazem no intervalo entre o dia 7 e o final da janela de lookback (dia 30).

Na verdade, quase 62% dos usuários que inicializam o aplicativo fazem isso em até 15 minutos após o engajamento com o anúncio. 72% dos usuários fazem isso na primeira hora.

## Cenários e exemplos

Abaixo está uma lista de possíveis cenários e exemplos de uso da janela de lookback.

<div id="srn-discrepancy-srn-lookback-longer-than-appsflyer" />

<Accordion title="Discrepância com SRNs: O lookback da SRN é mais longo que o da AppsFlyer">

Você configura uma campanha no X Ads e configura a janela de lookback de click-through para 7 dias. O X Ads, por outro lado, tem uma janela de lookback padrão de 14 dias.

[![srn-discrepancy-srn-lookback-larger-than-appsflyer.png](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)

</Accordion>

<div id="srn-lookback-smaller-than-appsflyer" />

<Accordion title="Lookback da SRN menor do que o da AppsFlyer">

Você configura uma campanha no X Ads e configura a janela de lookback de click-through para 28 dias. O X Ads, por outro lado, tem uma janela de lookback padrão de 14 dias.

[![srn-lookback-smaller-than-appsflyer.png](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)

</Accordion>

<div id="attribution-link-without-a-lookback-window-parameter" />

<Accordion title="Link de atribuição sem um parâmetro de janela de lookback">

É possível ter um link de atribuição que não tenha um parâmetro de janela de lookback. Nesses casos, o padrão da AppsFlyer é uma janela de lookback de 7 dias para cliques e uma janela de lookback de 1 dia para impressões.

</Accordion>

<div id="lookback-in-hours-for-flash-campaigns" />

<Accordion title="Lookback em horas para campanhas relâmpago">

As campanhas relâmpago são campanhas cuja intenção é solicitar que os usuários instalem o aplicativo o mais rápido possível e dentro de uma curta janela de divulgação.

Um aplicativo de eCommerce chamado SuperShopping executa uma campanha relâmpago. Nessa campanha, o usuário que instalar o aplicativo em até uma hora ganha ofertas especiais.

João, o profissional de marketing líder do SuperShopping, cria um link de atribuição e define a janela de lookback para 1 hora. Dessa forma, João sabe quantos usuários respondem à campanha.

Além disso, o desenvolvedor do aplicativo pode identificar os usuários que vêm dessa campanha relâmpago e compartilhar as promoções que a campanha anuncia.

</Accordion>

> 👍 **Dica**
>
> Quer algumas dicas e truques sobre janelas de lookback e atribuição? Veja esse breve e informativo <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">curso no Portal de Aprendizagem da AppsFlyer</Anchor>.

<div data-zendesk-anchors="lookback-windows=janelas-de-lookback h_01HGFQVP7QZACJ3EGSWEP4HPFV=janelas-de-lookback configurable-lookback-windows-per-attribution-type=janelas-de-lookback-configur%C3%A1veis-por-tipo-de-atribui%C3%A7%C3%A3o h_01HGFQVP7QM0J507CFQ753YS5X=janelas-de-lookback-configur%C3%A1veis-por-tipo-de-atribui%C3%A7%C3%A3o probabilistic-modeling-lookback-window=janela-de-lookback-de-modelagem-probabil%C3%ADstica h_01JKWV7S7J5B4YA84VGEB478TT=janela-de-lookback-de-modelagem-probabil%C3%ADstica lookback-window-setup=configura%C3%A7%C3%A3o-da-janela-de-lookback h_01HGFQVP7QCCN7CHRCAFSNJVHA=configura%C3%A7%C3%A3o-da-janela-de-lookback attribution-lookback-window-for-srns=janela-de-lookback-de-atribui%C3%A7%C3%A3o-para-srns h_01HGFQVP7QP61C2K0P7C7YM56Z=janela-de-lookback-de-atribui%C3%A7%C3%A3o-para-srns h_01HGFQVP7QXTQKGVQJEZ0NEW0M=importante h_01HGFQVP7QDBFP85A9DJFZE38S=attribution-lookback-window-with-attribution-links lookback-window-in-onelink%E2%84%A2=lookback-window-in-onelink h_01HGFQVP7QSJEE8D7TCWZMSXGK=lookback-window-in-onelink distribution-of-first-app-launches=distribui%C3%A7%C3%A3o-das-primeiras-aberturas-do-aplicativo h_01HGFQVP7Q96827N7Q9Q0363SR=distribui%C3%A7%C3%A3o-das-primeiras-aberturas-do-aplicativo scenarios-and-examples=cen%C3%A1rios-e-exemplos h_01HGFQVP7Q02NS8MXF7WKYQ8V1=cen%C3%A1rios-e-exemplos h_01HGFQVP7Q1CYRAHAKY3WK8BK0=srn-discrepancy-srn-lookback-longer-than-appsflyer h_01HGFQVP7QAWDP40H89YBN66GV=srn-lookback-smaller-than-appsflyer h_01HGFQVP7QYE3V2DKW7T4171MX=attribution-link-without-a-lookback-window-parameter h_01HGFQVP7Q7CXSK5G8A0937H5Z=lookback-in-hours-for-flash-campaigns h_01HGFQVP7QM3R973QS99661VPG=dica" />

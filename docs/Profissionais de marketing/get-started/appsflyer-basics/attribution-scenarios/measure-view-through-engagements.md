---
title: Medir engajamentos view-through
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2026-08-18T00:10:16Z'
  id: 210084473
  locale: pt
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/pt/articles/210084473
---
> **Visão geral:** um usuário que visualiza um anúncio (impressão) e logo depois instala o aplicativo é atribuído pela atribuição de visualização.

## Visão geral

A atribuição de visualização mede instalações, reatribuições e reengajamentos de usuários que visualizaram um anúncio, mas não clicaram nele.

### Fluxo de atribuição de exibição

![Retargeting_-_View-through__1_.png](https://files.readme.io/86d32778a8a0966499a0c5c91c1b2d8aed6d5bb24214b1a32fd484779c105a98-4412917609489.png)

### Terminologia

* **Impressão:** a exibição de um anúncio para um usuário, independentemente de qualquer clique ou outro envolvimento do usuário.
* **Instalação**: neste artigo, inclui instalações, reatribuições e reengajamentos.
* **Atribuição de exibição:** atribuição de instalações a uma fonte de mídia depois que o usuário vê uma impressão.

### Princípios de atribuição de exibição

* Tanto <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#device-id-matching">a correspondência de ID do dispositivo</Anchor> quanto a <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">modelagem probabilística</Anchor> (<Anchor target="_blank" href="/marketers/pt/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">que você deve ativar</Anchor>) são compatíveis.
* Compatível com parceiros listados na [lista de parceiros de atribuição de visualização](/docs/measure-view-through-engagements#view-vta-partner-list).

As impressões são candidatas para atribuição de visualização usando os seguintes princípios:

* A impressão ocorreu dentro da janela de lookback de visualização (padrão de 24 horas).
* Se várias impressões forem encontradas, a impressão mais recente será considerada.
* Os cliques têm prioridade sobre as impressões. Isso significa que, se houver cliques na janela de lookback de cliques, o clique mais recente vence. A impressão mais recente é atribuída como colaborador (assistência).

### Janela de lookback de exibição

* Para não-SRNs, a janela de lookback de atribuição de exibição é de 1-24 horas. Para SRNs, a janela de lookback pode ser mais longa.
* Para configurar a janela:
  * **Não SRNs:** defina a duração usando links de atribuição de impressão definindo o parâmetro  `af_viewthrough_lookback`. Se o parâmetro não estiver definido, uma janela padrão de 24 horas será usada.
  * **SRNs**: a janela é determinada pelo SRN. Recomendamos definir o mesmo valor que os SRNs na AppsFlyer.

### Relatórios e métricas de atribuição de visualização

* **Dados agregados:** as ad networks relatam dados de impressão agregados à AppsFlyer via API ou por impressão. Considere que a contagem de impressões e os relatórios são definidos individualmente por cada parceiro. As métricas relacionadas estão disponíveis no painel Visão geral e por meio de outras ferramentas de relatório. As métricas disponíveis são: 
  * Impressões: número de impressões exibidas durante um determinado período.
  * Exibições: o número de instalações atribuídas usando a atribuição de exibição.
* **Dados brutos**:
  * Os dados no nível do usuário (dados brutos) dos usuários atribuídos por meio da atribuição de visualização estão disponíveis e semelhantes aos dos usuários atribuídos por clique. No entanto, alguns parceiros restringem a disponibilidade desses dados.
  * Os dados de impressão (semelhantes aos dados de cliques) estão disponíveis.
  * O campo attributed\_touch\_type contém a *impressão de valor.*

## Operações de exibição

<div id="set-impression-links" />

<Accordion title="Definir links de impressão">

As ad networks enviam links de impressão para a AppsFlyer preenchidos com a campanha e outros detalhes semelhantes aos incluídos nos <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">links de atribuição</Anchor> de cliques.

Os links são enviados em tempo real para que, se uma instalação seguir uma impressão, ela seja atribuída corretamente.

Considere o seguinte na preparação de links:

* O domínio da URL é `http://impression.appsflyer.com`.
* Use uma solicitação GET.
* Inclua IDs de dispositivos quando disponíveis: IDFA, GAID, IDFV e assim por diante.
* Inclua parâmetros de <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling-parameters-for-ad-networks">modelagem probabilística</Anchor>.
* Os valores de ID do dispositivo podem ser codificados para melhor segurança usando o SHA1. O nome do parâmetro deve começar com "sha1\_" e ser seguido pelo nome do parâmetro e o valor do hash, por exemplo, sha1\_idfa, sha1\_advertising\_id, sha1\_android\_id e sha1\_imei.

> 📄
>
>  Exemplo
>
> ```http
> http://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
> &af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
> &af_sub1={free value}&idfa={idfa value}
> ```

</Accordion>

<div id="set-custom-impression-links" />

<Accordion title="Definir links de impressão personalizados">

Os anunciantes utilizam links de impressão de atribuição com suas próprias fontes de mídia personalizadas, por exemplo, banners de sites.

Quando os anunciantes <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">criam links de atribuição personalizados</Anchor>, eles recebem links de impressão completos, que podem ser disparados toda vez que um usuário se envolve com seus próprios anúncios.

Links de impressão personalizados (criados através do OneLink) também podem ser usados para realizar a atribuição de exibição de visitantes de sites móveis. Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">criar URLs de impressão personalizadas</Anchor>.

</Accordion>

<div id="turn-off-viewthroughattribution" />

<Accordion title="Desativar a atribuição de exibição">

Por padrão, a atribuição de visualização é ativada. Se a AppsFlyer receber um link de atribuição de impressão válido, a impressão participa do fluxo de atribuição.

Como a atribuição de exibição é habilitada por padrão, é importante que os anunciantes concordem contratualmente com a rede de antemão se sua atribuição de exibição deve ser ativada ou não.

A atribuição de visualização pode ser desativada por fonte de mídia. No entanto, se as impressões forem recebidas e a atribuição de visualização estiver desativada:

* As métricas de impressão estão disponíveis no painel.
* O processo de atribuição ignora essas impressões.

**Para desativar a atribuição de exibição:**

1. Na AppsFlyer, vá para o menu lateral e selecione **colaborar** > **integrações ativas**.
2. Selecione o parceiro integrado.
3. Na aba Integração, desative **Atribuição de exibição de instalação**.
4. Clique em **Salvar integração.**

Em relação aos SRNs: desativar a atribuição de exibição na AppsFlyer não faz o mesmo no lado da rede. Certifique-se de alinhar as configurações de exibição na AppsFlyer e nas redes para evitar discrepâncias.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HEMT7T1TB9W7ZBRPQW29SRPF=vis%C3%A3o-geral viewthrough-attribution-flow=fluxo-de-atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o h_01HEMT7T1T6ZK4ZH7DKV3162J1=fluxo-de-atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o terminology=terminologia h_01HEMT7T1TY46QXBDS6MBF1DZ5=terminologia viewthrough-attribution-principles=princ%C3%ADpios-de-atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o h_01HEMT7T1THD8TVKRRJ168HKY2=princ%C3%ADpios-de-atribui%C3%A7%C3%A3o-de-exibi%C3%A7%C3%A3o viewthrough-lookback-window=janela-de-lookback-de-exibi%C3%A7%C3%A3o h_01HEMT7T1TWHN2AB3Q5X36TKKB=janela-de-lookback-de-exibi%C3%A7%C3%A3o viewthrough-attribution-reporting-and-metrics=relat%C3%B3rios-e-m%C3%A9tricas-de-atribui%C3%A7%C3%A3o-de-visualiza%C3%A7%C3%A3o h_01HEMT7T1TQNKM5GABA7VY6KR1=relat%C3%B3rios-e-m%C3%A9tricas-de-atribui%C3%A7%C3%A3o-de-visualiza%C3%A7%C3%A3o viewthrough-operations=opera%C3%A7%C3%B5es-de-exibi%C3%A7%C3%A3o h_01HEMT7T1T13JC75ZYY01N8PS6=opera%C3%A7%C3%B5es-de-exibi%C3%A7%C3%A3o h_01HEMT7T1TQ3YNQ2Y0CCGPXWDX=set-impression-links h_01HEMT7T1T75MBS64JE837CJ0E=set-custom-impression-links h_01HEMT7T1T253G1CZNS9KVDFCP=turn-off-viewthroughattribution" />

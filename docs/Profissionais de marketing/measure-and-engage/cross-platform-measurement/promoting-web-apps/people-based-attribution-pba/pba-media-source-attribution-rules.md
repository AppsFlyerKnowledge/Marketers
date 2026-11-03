---
title: Regras de atribuição de canais de mídia do PBA
metadata:
  keywords:
    - media source
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-09-03T07:30:08Z'
  edited_at: '2026-08-19T00:22:59Z'
  id: 360002386997
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360002386997
---
> **Visão geral:** mensure o impacto dos seus esforços de marketing para impulsionar o tráfego ativo do site. Quais fontes de mídia, tipos de mídia e canais são responsáveis por visitas e eventos de conversão. Métricas a nível de anúncio disponíveis.

![Touchpoints_us-en.png](https://files.readme.io/45c45c9a1b108ea31e450df4c2aaab20482c9829726d9860e55e2c9ca32c401a-360008629017.png)

## Visitas ao site e eventos do site

* **Reconhecer uma visita:** O PBA registra uma visita de acordo com as [regras de reconhecimento de visitas.](/docs/pba-media-source-attribution-rules#visit-recognition-rules)
* **Atribuição de visita**
  * Para determinar o canal de mídia responsável por trazer um usuário para o site, o PBA analisa os parâmetros de consulta na URL e os referenciadores de documento HTTP coletados pelo SDK web.
  * A determinação do canal de mídia com base em regras usa os dados coletados, conforme detalhado neste artigo. Da mesma forma, o tipo de mídia e o canal de mídia são determinados.
  * A visita é registrada nos <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports">dados brutos do PBA</Anchor>.
* **Campanha** informações são extraídas de:
  * Parâmetros de consulta usando o canal de mídia
  * Gclid (se disponível) usando a <Anchor target="_blank" href="/marketers/pt/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">integração com anúncios do Google</Anchor>
* **Evento web**
  * Um evento web ocorre quando um visitante realiza uma ação no site, por exemplo, busca de produto, seleção de produto ou compra.
  * Os eventos são atribuídos à visita web não direta mais recente, ocorrida dentro de uma janela de retrospectiva de 30 dias.
  * Os eventos são subdivididos em:   
    * **Eventos de conversão**: eventos significativos designados pelo profissional de marketing. Por exemplo, compra ou cadastro.
    * **Eventos padrão**: outros eventos.
  * Saiba mais sobre as <Anchor target="_blank" href="/marketers/pt/docs/pba-website-attribution-url-best-practices">melhores práticas de URL de atribuição de site do PBA</Anchor>.

Os dashboards do PBA e os relatórios de dados brutos usam os canais de mídia, os tipos, os canais e as campanhas atribuídos.

![MediaSource_us-en.png](https://files.readme.io/bcb3e471753809b0fdf1a0e1dc9783002004b1988f4701ab30524c1eb7b9fbfc-360008629057.png)

Para facilitar a compreensão, a tabela a seguir contém exemplos do canal de mídia determinado, com seu tipo e canal.

| Canal de mídia | Tipo de mídia | Canal de mídia |
| --- | --- | --- |
| Direto | Obtenção | Direto |
| <ul><li>Social Facebook</li><li>Social X (antigo Twitter)</li></ul> | Próprias | Mídia social |
| <ul><li>Anúncios Meta</li><li>AppsFlyer</li></ul> | Paga | Mídia social |
| Pesquisa no Google | Obtenção | Busca orgânica |
| E-mail | Próprias | E-mail |
| googleadwords\_int | Paga | As ad |
| usatoday.com | Obtenção | Indicação |

## Determinação do canal de mídia

O PBA determina o canal de mídia, o tipo de mídia e o canal de mídia de forma hierárquica. Isso significa determinar a regra de canal de mídia relevante e o canal de mídia. Depois, o tipo de mídia e o canal de mídia são determinados.

<div id="media-source-rules" />

<Accordion title="Regras de canal de mídia">

As regras de canal de mídia mostradas na tabela a seguir são classificadas da maior para a menor prioridade:

<Table>
  <thead>
    <tr>
      <th>
        Regra de canal de mídia
      </th>
      <th>
        Resolução do canal de mídia
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Evitar autoatribuição
      </td>
      <td>
        Para evitar atribuir eventos ao próprio site (autoatribuição) e a outros domínios relacionados, é usada uma lista de <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings#domain-exclusion">exclusão de domínios</Anchor>. A lista consiste em:

        * Domínio principal: determinado pela URL do aplicativo web incluído no bundle da marca
        * Domínios internos: domínios que fazem parte da marca
        * Domínios externos: gateways de pagamento e sites de processamento de pagamento definidos por você, além de alguns domínios, como PayPal e Stripe, definidos pela AppsFlyer, são excluídos automaticamente
      </td>
    </tr>
    <tr>
      <td>
        pid
      </td>
      <td>
        Resolve para o valor de pid na URL. Para algumas SRNs, o pid é resolvido para o nome comercial da SRN, para manter a consistência e a clareza. Por exemplo, pid=facebook\_int é resolvido como Facebook Ads e twitter\_int é resolvido como Twitter.
      </td>
    </tr>
    <tr>
      <td>
        IDs de clique
      </td>
      <td>
        Grandes ad networks, como o Google, usam IDs de clique para marcar campanhas automaticamente. Os IDs de clique são resolvidos da seguinte forma:

        * **gclid:** <Anchor target="_blank" href="https://support.google.com/searchads/answer/7342044?hl=en">ID de clique do Google</Anchor> é resolvido como *googleadwords\_int*. Nota! *A solução GCLID não é oficialmente compatível com o Google, que pode descontinuá-la no futuro.*
        * **dclid**: o ID de clique do DoubleClick é resolvido como *doubleclick\_int.*
        * **msclkid:** <Anchor target="_blank" href="http://help.ads.microsoft.com/apex/index/3/en/60000">ID de clique do Bing</Anchor> corresponde a *bingsearch\_int*.
      </td>
    </tr>
    <tr>
      <td>
        Parâmetros UTM
      </td>
      <td>
        **Regras personalizadas de UTM**

        | utm\_source | utm\_medium | Canal de mídia |
        | --- | --- | --- |
        | * | * e-mail, mail, e-mail<br />* Observação! Se utm\_medium contiver um destes valores, a utm\_source será ignorada. | E-mail |
        | google | cpc/ppc/paidsearch/search | googleadwords\_int |
        | google | cpm/display/banner/video/listing | doubleclick\_int |
        | dfa / dbm | CPM (custo por mil impressões) | doubleclick\_int |
        | facebook | cpc/ppc/cpm/cpa/paidsocial/paid-social | Anúncios do Facebook |
        | bing | cpc | bingsearch\_int |
        | yahoo / Gemini | cpc/display/listing | yahoogemini\_int |
        | twitter | cpc | AppsFlyer |
        | snapchat | swipe | "snapchat\_int" |
        | Pinterest | cpc | pinterest\_int |

        Se não houver correspondência com nenhuma regra personalizada, o canal de mídia corresponderá ao valor do parâmetro utm\_source.

        <Anchor target="_blank" href="https://en.wikipedia.org/wiki/UTM_parameters">Informações sobre parâmetros UTM</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Referrer
      </td>
      <td>
        O referenciador é a fonte HTTP que enviou o usuário para o site. O canal de mídia é o nome de domínio do referenciador.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="media-source-type" />

<Accordion title="Tipo de fonte de mídia">

Os profissionais de marketing geralmente segmentam os canais de mídia da web em três tipos:

* **Pago:** campanhas de anúncios, como banners de display, vídeos e anúncios de pesquisa.
* **Próprio:** campanhas de marketing que vêm de mídias próprias, ou seja, campanhas de e-mail, posts sociais e blogs.
* **Ganho:** tráfego direto ou orgânico de mecanismos de busca, referências e tráfego direto real.

O tipo de mídia é determinado consultando a regra de canal de mídia usada em combinação com o canal de mídia/outros parâmetros.

<table><thead><tr><th>Regra de canal de mídia aplicável</th><th>Canal de mídia</th><th>Tipo de mídia</th></tr></thead><tbody><tr><td colspan="1" rowspan="2"><div>pid</div></td><td><p>A regra de pid determina se o canal de mídia é: </p><ul><li>Social Facebook</li><li>Social X (antigo Twitter)</li><li>SMS</li><li>Blog</li><li>E-mail</li></ul></td><td>Próprias</td></tr><tr><td>Qualquer outro canal de mídia</td><td>Paga</td></tr><tr><td>ID de clique</td><td><p><span>Determinado usando um ID de clique:</span></p><ul><li>gclid</li><li>dclid</li><li>msclkid</li></ul></td><td>Paga</td></tr><tr><td colspan="1" rowspan="2"><div>UTM</div></td><td>As regras personalizadas de UTM determinam o canal de mídia</td><td>Paga</td></tr><tr><td>Qualquer outro canal de mídia</td><td>Próprias</td></tr><tr><td rowspan="2">Referrer</td><td><p><span>O valor do domínio de referência é um dos seguintes:</span></p><ul><li>googleads.g.doubleclick.net </li><li>tpc.googlesyndication.com</li></ul></td><td><p>Paga</p></td></tr><tr><td><span>Qualquer outro canal de mídia </span></td><td><p>Obtenção</p></td></tr></tbody></table>

</Accordion>

<div id="media-source-channel" />

<Accordion title="Canal da fonte de mídia">

O canal de mídia é determinado pelas regras conforme listado aqui.

<table><thead><tr><th>Prioridade</th><th>Regra do canal de mídia</th><th>Valores</th><th>Canal de mídia</th></tr></thead><tbody><tr><td rowspan="4">Prioridade máxima</td><td rowspan="4">O canal de mídia é um dos valores listados</td><td>Direto</td><td>Direto</td></tr><tr><td><ul><li>Google Search</li><li>Yahoo Search</li><li>Bing Search</li></ul></td><td>Busca orgânica</td></tr><tr><td><ul><li>facebook</li><li>twitter</li><li>snapchat</li><li>Pinterest</li><li>linkedin</li><li>whatsapp</li></ul></td><td>Mídia social</td></tr><tr><td>E-mail</td><td>E-mail</td></tr><tr><td> </td><td>O tipo de mídia é pago</td><td> </td><td><div>As ad</div></td></tr><tr><td> </td><td>Canal de mídia determinado pelo referenciador</td><td> </td><td>Indicação</td></tr><tr><td>Prioridade mais baixa</td><td>Nenhuma outra condição anterior correspondeu</td><td> </td><td>Outros</td></tr></tbody></table>

</Accordion>

<div id="determine-the-campaign" />

<Accordion title="Determinar a campanha">

* As campanhas são determinadas usando: 
  * Parâmetros de URL da campanha, por parâmetros de URL do canal de mídia.
  * ID de clique do Gclid e uso da integração com <Anchor target="_blank" href="/marketers/pt/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Ads</Anchor>
* Se o parâmetro de campanha relevante não for encontrado na URL, a campanha não será derivada.

| Parâmetro do canal de mídia usado | Parâmetro de campanha usado |
| --- | --- |
| pid | Os parâmetros de canal de mídia da AppsFlyer disponíveis na URL são usados para preencher os dados brutos e o dashboard de atribuição do site. Parâmetros disponíveis: af\_c\_id, af\_adset, af\_adset\_id, af\_ad\_id |
| ID de clique — gclid | Obtido via API do Google Ads |
| utm\_source | utm\_campaign |

</Accordion>

## Regras de atribuição adicionais

<div id="visit-recognition-rules" />

<Accordion title="Regras de reconhecimento de visita">

Uma visita ao site é registrada usando as regras a seguir e considerando o status da sessão atual. Uma sessão ativa é uma sessão com menos de 30 minutos de inatividade.

* Não registre uma visita se o usuário tiver vindo de um domínio <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings#domain-exclusion">externo excluído</Anchor>.
* Durante uma sessão ativa: registre uma visita se o carregamento da página incluir um canal de mídia.
* Se não houver sessão ativa, grave a visita.
* Não há tempo mínimo de visita.

**Regras de registro de visita do PBA**

![PBA_-_PBA-vist.png](https://files.readme.io/651c3ee4d39832297b7d6dc871aa281f1fa3219264ba264851ad0cc643b8baee-360015532817.png)

</Accordion>

<div id="data-finalization" />

<Accordion title="Finalização de dados">

* Finalização de dados:
  * Para instalações assistidas pela web e atribuição de site, o PBA identifica eventos relacionados adicionais durante os primeiros 7 dias após a conversão. Isso pode alterar o canal de mídia identificado como o responsável final por impulsionar a conversão.
  * Nos relatórios de dados brutos relacionados, o campo *final\_data* é false durante o período inicial de 7 dias.

</Accordion>

<div data-zendesk-anchors="website-visits-and-web-events=visitas-ao-site-e-eventos-do-site h_01H936NV7VP8CTE9BZP6D5E7NK=visitas-ao-site-e-eventos-do-site determining-the-media-source=determina%C3%A7%C3%A3o-do-canal-de-m%C3%ADdia h_01H936NV7VZHWBDPHFJRFFCPSW=determina%C3%A7%C3%A3o-do-canal-de-m%C3%ADdia h_01H936NV7V6GMWSCHNDMJ205JS=media-source-rules h_01H936NV7W9ZFMET29GY6JTBGN=media-source-type h_01H936NV7W61DB43D3E1MNEJHN=media-source-channel h_01H936NV7WZYE3EKYZ9PX9ZJXW=determine-the-campaign additional-attribution-rules=regras-de-atribui%C3%A7%C3%A3o-adicionais h_01H936NV7WA9WZM4RTQZHD22VV=regras-de-atribui%C3%A7%C3%A3o-adicionais h_01H936NV7W323HQMG5E6SQFQEN=visit-recognition-rules h_01H936NV7WSB2FMRBPDN936TWM=data-finalization" />

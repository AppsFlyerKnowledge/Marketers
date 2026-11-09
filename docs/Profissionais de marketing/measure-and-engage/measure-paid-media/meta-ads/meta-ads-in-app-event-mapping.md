---
title: Mapeamento de evento in-app do Meta Ads
metadata:
  keywords:
    - Facebook
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
  created_at: '2021-11-09T09:57:19Z'
  edited_at: '2026-09-11T00:28:23Z'
  id: 4410480904081
  locale: pt
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/pt/articles/4410480904081
---
> **Visão geral:** envie eventos avançados dentro do aplicativo pelo seu aplicativo da AppsFlyer para Meta ads.

<div id="meta-in-app-events-mapping" />

## Mapeamento de eventos in-app do Meta

Os anunciantes mapeiam seus eventos in-app, SDK ou de servidor para servidor para eventos do Meta predefinidos. Os anunciantes também podem enviar postbacks do Meta sobre cada <Anchor target="_blank" href="/marketers/pt/docs/measure-sessions">inicialização de aplicativo</Anchor> ou qualquer <Anchor target="_blank" href="/marketers/pt/docs/measure-uninstalls#mapeando-o-evento-de-desinstalação">desinstalação de aplicativo</Anchor> conhecidas.

Isso permite que os anunciantes utilizem os recursos avançados de otimização do Meta, bem como criem segmentos de público personalizado e semelhante.

<div id="predefined-event-mapping" />

### Mapeamento de eventos predefinidos

Os anúncios do Meta oferecem uma <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/getting-started-app-events-android#event-names">ampla gama de eventos</Anchor> que já estão predefinidos e podem ser mapeados.

Encontre <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure">aqui</Anchor> a lista de **eventos avançado dentro do aplicativo** que podem ser enviados para o Meta com parâmetros adicionais que fornecem **informações extras sobre a qualidade dos eventos**.

Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#inapp-event-mapping">mapear eventos no Meta</Anchor>.

<Image align="center" alt="Os postbacks seguem o" src="https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png" />

Observe que não há evento predefinido para enviar desinstalações para anúncios do Meta. Para enviar desinstalações, use um [evento personalizado](/docs/meta-ads-in-app-event-mapping#mapeamento-de-eventos-in-app-personalizados).

Abaixo está a lista de outros eventos do Meta predefinidos que não possuem parâmetros adicionais:

| Identificador de evento do Meta | Descrição | Nome recomendado do SDK da AppsFlyer |
| --- | --- | --- |
| Doar | A doação de fundos para sua organização ou causa. | af\_donate |
| Agenda | O agendamento de um horário para visitar um dos seus locais. | af\_schedule |
| Dois pontos (:) | O envio de uma inscrição para um produto, serviço ou programa que você oferece, como cartão de crédito, programa educacional ou emprego. | af\_submit\_application |
| Encontrar local | Quando uma pessoa encontra um dos seus locais via web ou aplicativo, com a intenção de visitá-lo. Por exemplo, pesquisando um produto e localizando-o em uma de suas lojas locais. | af\_find\_location |
| Contato | Um telefone ou SMS, e-mail, chat ou outro tipo de contato entre um cliente e sua empresa. | af\_contact |
| Personalizar produto | A personalização de produtos por meio de uma ferramenta de configuração ou outro aplicativo da sua empresa. | af\_customize\_product |
| `Adimpression`—para Android  <br />`Fb_mobile_purchase`—para iOS | Otimiza a receita de anúncios na plataforma de anúncios da Meta. [Veja os detalhes abaixo](#mapeamento-de-dados-de-receita-de-anúncios-para-otimização-de-campanhas). | af\_ad\_revenue |

<div id="mapping-ad-revenue-data-for-campaign-optimization" />

### Mapeamento de dados de receita de anúncios para otimização de campanhas

Os anúncios da Meta podem otimizar suas campanhas com base em seus dados de receita de anúncios. Isso é feito mapeando o evento af\_ad\_revenue para o seguinte evento de anúncios da Meta:

<table><colgroup><col/><col/><col/><col/></colgroup><thead><tr><th><strong>Nome do evento na AppsFlyer</strong></th><th><strong>Platform</strong> </th><th><strong>Mapeado para eventos de parceiros</strong></th><th><strong>Otimização de anúncios da Meta com base em:</strong></th></tr></thead><tbody><tr><td rowspan="2"> <br/>af_ad_revenue</td><td>com o Android</td><td>Adimpression</td><td>Receita de anúncios específica</td></tr><tr><td>/docs/ctv-pc-and-console-platform-attribution-concepts</td><td>fb_mobile_purchase</td><td>In-app purchases</td></tr></tbody></table>

<div id="availability-limitations" />

#### Limitações de disponibilidade

* Atualmente, a otimização por meio do evento **Adimpression** está disponível apenas para:
  * Apps Android. Aplicativos iOS podem continuar enviando dados de receita de anúncios usando o evento *fb\_mobile\_purchase*.
  * Contas selecionadas de anúncios da Meta, de acordo com os critérios da Meta. Quando indisponível, os [critérios de elegibilidade podem não ser atendidos](https://www.facebook.com/business/help/571188993373447?id=561906377587030).
* O evento *af\_ad\_revenue* está disponível apenas para planos com uma <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-cost-and-revenue-data">assinatura avançada do ROI360</Anchor>. Além disso, você precisa do <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">tipo de integração de receita de anúncios via SDK no nível de impressão</Anchor>.
  * Planos sem o ROI360 podem enviar dados de receita de anúncios usando outros nomes de eventos.

<div id="custom-in-app-events-mapping" />

### Mapeamento de eventos in-app personalizados

A AppsFlyer permite que você mapeie qualquer evento in-app personalizado para enviar ao Meta, usando a opção de evento PERSONALIZADO do Meta.

O nome do evento e o valor do evento (incluindo os parâmetros do evento) configurados no SDK são encaminhados para o Meta, da forma como estão, e exibidos sob o nome de evento original do SDK da AppsFlyer - não como "personalizado".

Observe que você pode <Anchor target="_blank" href="https://www.facebook.com/business/help/2308889442692949?id=1716638325041491">usar esses eventos para otimizar suas campanhas</Anchor>.

<Image align="center" alt="" src="https://files.readme.io/b41d1fa6c42284db9992260e58083bc2ef46ee3e98dbe4e063cdb28883553471-37750368969233.png" />

<div id="automatic-parameter-mapping-with-the-custom-event" />

### Mapeamento automático de parâmetros com o evento PERSONALIZADO

Através da integração direta da AppsFlyer com o Meta, muitos dos parâmetros de eventos do SDK padrão são automaticamente mapeados para os parâmetros predefinidos do Meta. Por exemplo, o parâmetro **af\_revenue** é convertido para o parâmetro **\_valueToSum** no Meta, o que permite que você envie uma receita por evento que pode ser mensurada e otimizada para o Meta.

<div id="note" />

> 📘 **Observação**
>
> O mapeamento automático de parâmetros pode diferir entre eventos PERSONALIZADOS e predefinidos.
>
> Para <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure">eventos predefinidos</Anchor>, **af\_price** é mapeado para **\_valueToSum** em alguns casos (por exemplo, `fb_mobile_add_to_cart`). Em outros casos, **af\_revenue** é mapeado para **\_valueToSum** (por exemplo, em `fb_mobile_purchase`).
>
> Para eventos mapeados para PERSONALIZADO, **af\_price** é sempre mapeado para **fb\_price** e **af\_revenue** para **\_valueToSum**.

A tabela a seguir detalha todos os parâmetros de eventos da AppsFlyer que, quando mapeados através do evento PERSONALIZADO para o Meta, são automaticamente mapeados para os parâmetros do Meta.

| Parâmetro da AppsFlyer | Parâmetro do Meta |
| --- | --- |
| af\_city | fb\_city |
| af\_class | fb\_travel\_class |
| af\_content | fb\_content |
| af\_content\_id | fb\_content\_id |
| af\_content\_list | fb\_content\_id |
| af\_content\_type | fb\_content\_type |
| af\_country | fb\_country |
| af\_currency | fb\_currency |
| af\_date\_a | fb\_checkin\_date |
| af\_date\_b | fb\_checkout\_date |
| af\_departing\_arrival\_date | fb\_departing\_arrival\_date |
| af\_departing\_departure\_date | fb\_departing\_departure\_date |
| af\_description | fb\_description |
| af\_destination\_a | fb\_origin\_airport |
| af\_destination\_b | {"fb_destination_"}  <br />airport |
| af\_destination\_list | fb\_destination\_ids |
| af\_hotel\_score | fb\_hotel\_score |
| af\_level | fb\_level |
| af\_max\_rating\_value | fb\_max\_rating\_value |
| af\_num\_adults | fb\_num\_adults |
| af\_num\_children | fb\_num\_children |
| af\_num\_infants | fb\_num\_infants |
| af\_order\_id | fb\_order\_id |
| af\_payment\_info\_available | fb\_payment\_info\_available |
| af\_preferred\_neighborhoods | fb\_preferred\_neighborhoods |
| af\_preferred\_num\_stops | fb\_preferred\_num\_stops |
| af\_preferred\_price\_range | fb\_preferred\_price\_range |
| af\_preferred\_star\_ratings | fb\_preferred\_star\_ratings |
| af\_preço | fb\_price |
| af\_quantity | fb\_num\_items |
| af\_region | fb\_region |
| af\_registration\_method | fb\_registration\_method |
| af\_returning\_arrival\_date | fb\_returning\_arrival\_date |
| af\_returning\_departure\_date | fb\_returning\_departure\_date |
| af\_revenue | \_valueToSum |
| af\_search\_string | fb\_search\_string |
| af\_success | fb\_success |
| af\_suggested\_destinations | fb\_suggested\_destinations |
| af\_suggested\_hotels | fb\_suggested\_hotels |
| af\_travel\_end | fb\_travel\_end |
| af\_travel\_start | fb\_travel\_start |
| af\_user\_score | fb\_user\_score |

<div id="predefined-events-automatic-mapping-to-the-_valuetosum-parameter" />

#### Mapeamento automático de eventos predefinidos para o parâmetro `_valueToSum`

Para eventos predefinidos, o parâmetro `_valueToSum` da Meta é mapeado para os parâmetros `af_price` ou `af_revenue`.

A tabela a seguir detalha esse mapeamento para todos os eventos predefinidos da Meta com o parâmetro `_valueToSum`:

| **Ponto final (.)** | **\_valueToSum mapeado para** |
| --- | --- |
| fb\_mobile\_level\_achieved | none |
| fb\_mobile\_add\_payment\_info | none |
| fb\_mobile\_add\_to\_cart | af\_preço |
| fb\_mobile\_add\_to\_wishlist | af\_preço |
| fb\_mobile\_complete\_registration | none |
| fb\_mobile\_tutorial\_completion | none |
| fb\_mobile\_initiated\_checkout | af\_preço |
| fb\_mobile\_purchase | af\_revenue |
| fb\_mobile\_rate | af\_rating\_value |
| fb\_mobile\_search | af\_revenue |
| fb\_mobile\_spent\_credits | af\_preço |
| fb\_mobile\_achievement\_unlocked | none |
| fb\_mobile\_content\_view | af\_preço |
| Iniciar avaliação | af\_preço |
| Enviar inscrição | af\_revenue |

<div id="send-complex-in-app-events-to-meta-ads" />

### Enviar eventos in-app complexos para anúncios da Meta

Em setembro de 2026, recomendamos usar o novo objeto `af_order_info` para enviar eventos in-app complexos — eventos com vários itens — para anúncios da Meta. Esse objeto permite que anunciantes compartilhem eventos in-app complexos com várias networks compatíveis. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/item-level-order-data-for-ad-networks-af-order-info">Dados de pedidos em nível de item para ad networks (af\_order\_info)</Anchor>.

Ao usar `af_order_info`, a AppsFlyer envia as informações do item para a Meta no campo de evento `fb_contents`, que oferece suporte a SKU, quantidade e receita por item.

Como alternativa, você ainda pode usar um array estruturado de `af_content`. Cada objeto na matriz deve incluir `id` e `quantity` para garantir o tratamento adequado do postback.

`af_content_list` é opcional. Quando ele está ausente, a Meta recorre ao campo `fb_content` (mapeado a partir de `af_content`) para identificar IDs de produto. Desde que o JSON `af_content` inclua um campo `id` em cada objeto, a Meta pode analisá-lo e extrair dele os IDs de conteúdo.

Se você incluir `af_content_list`, não inclua também `af_content_id` no mesmo evento. Ambos os parâmetros são mapeados para `fb_content_id`, e apenas um deles deve ser preenchido para evitar conflitos.

<div id="note-1" />

> 📘 **Atenção**
>
> `fb_content_id` é importante para casos de uso no nível do produto, como a correspondência de eventos com itens do catálogo para Advantage+ Catalog Ads e Dynamic Ads, relatórios de performance no nível do produto e sinais de otimização baseados no produto. Para a otimização geral de conversão com base na contagem e no valor dos eventos, as campanhas funcionam sem ele.

<div id="example-unified-format-compatible-with-meta-and-tiktok" />

> 📄 **Exemplo: formato unificado compatível com Meta e TikTok**
>
> ```json
> {
>   "af_revenue": 4.99,
>   "af_currency": "USD",
>   "af_order_id": "12345",
>   "af_content": "[{\"id\":\"ID1\",\"quantity\":\"1\"},{\"id\":\"ID2\",\"quantity\":\"1\"},{\"id\":\"ID3\",\"quantity\":\"2\"}]"
> }
> ```

Esse formato funciona tanto para Meta quanto para TikTok. O TikTok também lê os valores de `id` do campo `af_content`, portanto uma única carga útil é suficiente ao enviar postbacks para ambas as networks.

<div id="important" />

> 🚧 **Importante!**
>
> Se o parâmetro `af_content` exceder 1.000 caracteres, a AppsFlyer poderá enviar o evento para a Meta sem o parâmetro `fb_content`. Se `af_content_list` também estiver ausente nesse cenário, a Meta não receberá dados de identificação do produto. Mantenha `af_content` abaixo de 1.000 caracteres para eventos que incluam muitos itens.

Para mais detalhes sobre como estruturar eventos in-app complexos, consulte o artigo <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#what-are-complex-inapp-events-and-how-do-i-set-them-up">Eventos in-app: Visão geral</Anchor>.

<div id="event-and-parameter-limitations" />

## Limitações de eventos e parâmetros

Os limites a seguir se aplicam aos [eventos que você envia para o Meta Ads](https://developers.facebook.com/docs/app-events/faq#limits):

* Os seguintes caracteres não são permitidos:
  * Dois pontos (:)
  * Ponto (.)
  * Conjuntos de caracteres não latinos (inglês): desde o dia 12 de janeiro de 2020, o Meta rejeita caracteres chineses. A AppsFlyer não testou outros conjuntos de caracteres e você deve usá-los somente depois de verificar com o Meta se há suporte para esses conjuntos de caracteres em postbacks.
* Os nomes de eventos diferenciam letras maiúsculas e minúsculas. Para evitar discrepâncias, use o nome do evento correto para todas as fontes de mídia e versões de aplicativos.
* Número máximo de parâmetros: 25.
* Comprimento dos nomes e parâmetros de eventos: 2—40.
* Comprimento máximo do parâmetro: 100 caracteres.
* Comprimento máximo do parâmetro af\_content: 1000 caracteres.
* Caracteres permitidos: caracteres alfanuméricos, sublinhados, hifens ou espaços. Não use caracteres não latinos. O uso de letras não-latinas gera resultados inconsistentes.

Considerações sobre a nomeação de eventos in-app:

* Nomes de eventos na AppsFlyer podem ser nomeados igual aos nomes dos eventos do Meta (por exemplo, fb\_price). No entanto, eles não devem ser enviados como eventos PERSONALIZADOS para o Meta.  
  **Por questões de segurança, evite nomear os eventos igual aos nomes de eventos do Meta.**
* Para realizar o mapeamento de postback de eventos in-app com o Meta, obtenha dados de eventos de todas as fontes, incluindo orgânica.

<div id="important-1" />

> 🚧 **Importante!**
>
> Com exceção dos parâmetros acima, a AppsFlyer envia os dados dos eventos PERSONALIZADOS **nas condições em que se encontram** para o Meta. É responsabilidade do proprietário do aplicativo verificar se os dados de eventos estão de acordo com os requisitos do Meta, usando parâmetros válidos para o Meta (veja a tabela acima). Caso contrário, esses parâmetros não são enviados ao Meta.

<div data-zendesk-anchors="facebook-iae-mapping=mapeamento-de-eventos-in-app-do-meta h_01J1WCP44CHN0Q73P6DN7H8FKG=mapeamento-de-eventos-in-app-do-meta predefined-event-mapping=mapeamento-de-eventos-predefinidos h_01J1WCP44D18WMXCMHJ0FNF6Y0=mapeamento-de-eventos-predefinidos mapping-ad-revenue-data-for-campaign-optimization=mapeamento-de-dados-de-receita-de-an%C3%BAncios-para-otimiza%C3%A7%C3%A3o-de-campanhas 01JAPZ6M11HSCE9QNN5NSD61FK=mapeamento-de-dados-de-receita-de-an%C3%BAncios-para-otimiza%C3%A7%C3%A3o-de-campanhas availability-limitations=limita%C3%A7%C3%B5es-de-disponibilidade 01JAQ1ECZVR8SZ81KE6CDD08A2=limita%C3%A7%C3%B5es-de-disponibilidade custom-inapp-events-mapping=mapeamento-de-eventos-in-app-personalizados h_01J1WCP44DK14AC5ZG4KTFFFSC=mapeamento-de-eventos-in-app-personalizados automatic-parameter-mapping-with-the-custom-event=mapeamento-autom%C3%A1tico-de-par%C3%A2metros-com-o-evento-personalizado h_01J1WCP44D645TS6JFGM2BDGM9=mapeamento-autom%C3%A1tico-de-par%C3%A2metros-com-o-evento-personalizado h_01J1WCP44DSZ7G3603W5EBWZEW=observa%C3%A7%C3%A3o value-to-sum=mapeamento-autom%C3%A1tico-de-eventos-predefinidos-para-o-par%C3%A2metro-_valuetosum 01JATBG1SZRRZ0PCANKQ6S8CX4=mapeamento-autom%C3%A1tico-de-eventos-predefinidos-para-o-par%C3%A2metro-_valuetosum send-complex-in-app-events-to-meta-ads=enviar-eventos-in-app-complexos-para-an%C3%BAncios-da-meta h_01K1QR0NWMT1WCFWXF2GK9YZYF=enviar-eventos-in-app-complexos-para-an%C3%BAncios-da-meta h_01KSMX6DZHA1HNQ2WGECZPEQGJ=aten%C3%A7%C3%A3o h_01KSMX6DZHF0P97RTJHS065KB1=exemplo-formato-unificado-compat%C3%ADvel-com-meta-e-tiktok h_01KSMX6DZHWXYRJP5QK5BB730P=importante event-and-parameter-limitations=limita%C3%A7%C3%B5es-de-eventos-e-par%C3%A2metros h_01J1WCP44DF2QMV10VXF8NQZ7W=limita%C3%A7%C3%B5es-de-eventos-e-par%C3%A2metros h_01J1WCP44D9SNEYZG59KNM822K=importante-1" />

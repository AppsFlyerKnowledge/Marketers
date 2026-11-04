---
title: Cenários e cargas de dados de conversão
metadata:
  keywords:
    - Conversion
    - Retargeting
    - Installs
    - Re-attribution
    - Re-engagement
    - Developers
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-12-31T13:05:33Z'
  edited_at: '2026-08-19T00:12:50Z'
  id: 360000726098
  locale: pt
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/pt/articles/360000726098
---
> **At a glance:** **Visão geral:** use os dados de conversão para identificar vários cenários de conversão, personalizar a experiência do usuário e muito mais.

<div id="overview" />

## Visão geral

O guia a seguir contém vários cenários de conversão do usuário e suas cargas de dados de conversão correspondentes:

* [Aquisição de usuários (UA)](#dados-de-conversão-de-ua-com-srns)
* [Redirecionamento](#dados-de-conversão-de-retargeting)

Os dados de conversão são disponibilizados na plataforma usando um dos seguintes itens:

* <Anchor target="_blank" href="/marketers/pt/docs/raw-data-export-page">Relatórios de dados brutos</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">API de push</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">O SDK da AppsFlyer</Anchor>

Por conta da troca inerente entre precisão/latência, os dados de conversão para os mesmos IDs de dispositivo podem diferir entre as APIs.

<div id="non-organic-conversion-data-payload-fields" />

### Campos de carga de dados de conversão não orgânica

<div id="fields-always-available" />

#### Campos sempre disponíveis

A tabela a seguir lista os campos que sempre existem para conversões **não orgânicas**, independentemente do `media_source` da conversão.

| Nome do campo de carga | Nome do campo de dados brutos | Observações |
| --- | --- | --- |
| `fonte_de_mídia` | Canal de mídia | Publisher atribuído. Equivalente ao parâmetro `pid` em links de atribuição |
| `install_time` | Hora da instalação |  |
| `click_time` | Tempo de toque atribuído | A hora em que um clique ou impressão ocorreu em UTC |
| `is_first_launch` | N/D | `true`, `false` |
| `af_status` | Os dados brutos são divididos em relatórios separados: orgânicos, não orgânicos | `"Não orgânicas"` |
| `af_siteid` | ID do site |  |
| `adgroup_id` | ID do anúncio |  |
| `conjunto_de_anúncios` | Conjunto de anúncios |  |
| `id_conjunto_de_anúncios` | Adset ID |  |
| `agency` | parceira | `null`, ou nome da agência (para campanhas executadas por agências) |
| `campanha` | Campanha |  |
| `id_da_campanha` | ID da campanha |  |
| `http_referrer` | Referência HTTP |  |
| `retargeting_conversion_type` | Tipo de conversão de redirecionamento | "none" ou retargeting\_conversion\_type |
| `af_sub[n] (n=1—5)` | Subparâmetro [n] (n=1–5) |  |

<div id="fields-available-in-some-cases" />

#### Campos disponíveis em alguns casos

Os campos na tabela a seguir estão disponíveis em alguns casos, dependendo de como a SRN preenche o evento individual.

<table><thead><tr><th>Nome dos campos de carga</th><th>Nome do campo de dados brutos</th><th>Observações</th><th> </th></tr></thead><tbody><tr><td><code>af_canal</code></td><td>Canal</td><td><p>SRNs que preenchem esse parâmetro:</p><ul><li>AppLovin</li><li>Google Ads</li><li>Meta Ads</li><li>Snapchat</li><li>TikTok para Empresas</li><li> Exemplo</li></ul><p>Exemplo: Facebook—Instagram, Google—YouTube </p></td><td> </td></tr><tr><td><code>orig_cost</code></td><td> </td><td>Observação (1)</td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td> </td><td>Observação (1)</td><td> </td></tr><tr><td><code>af_cpi</code></td><td> </td><td>Observação (1)</td><td> </td></tr><tr><td colspan="4"><p> <strong>Importante!</strong></p><p>(1) Os campos de custo são preenchidos com valores compartilhados pela ad network. Para que a ad network compartilhe dados de custo com a AppsFlyer, você deve ativar a integração de custos na página <a href="./roi360-cost-aggregation-overview#ad-networks-supporting-cost-api" target="_blank"><strong>Integrações ativas</strong></a>. Algumas SRNs são compatíveis com compartilhamento de custos em massa. Nesse caso, os campos de custo no nível do evento retornam como 0. </p></td></tr></tbody></table>

<div id="additional-fields" />

### Campos adicionais

* <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#parâmetros-do-link-de-atribuição">Lista de parâmetros da AppsFlyer</Anchor>
* Você pode adicionar parâmetros ao link de atribuição, eles são disponibilizados na carga

Consulte o <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#data-fields-dictionary">dicionário de campos de dados brutos</Anchor> para obter informações adicionais.

<div id="limitations" />

### Limitações

<div id="custom-parameter-names" />

<Accordion title="Nomes de parâmetros personalizados">

Parâmetros personalizados não podem ser chamados `name` ("n" minúscula. `Name` é válido).

Se um parâmetro for chamado `name`, ele será removido da carga.

</Accordion>

---

<div id="ua-conversion-data-with-srns" />

## Dados de conversão de UA com SRNs

<Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">Redes de autorrelato</Anchor> (SRNs) são ad networks que implementam seus próprios mecanismos de atribuição, por exemplo, Meta ads e Google.

SRNs não usam links de atribuição. Isso significa que:

* Os campos de carga são predefinidos
* Você não pode adicionar campos à carga anexando parâmetros a um link de atribuição.

SRNs relatam conversões para a AppsFlyer. Os dados de conversão são disponibilizados no aplicativo. Os campos disponíveis variam de acordo com a SRN e são detalhados nas guias individuais das SRNs a seguir.

<div id="a-note-about-meta-ads" />

#### Uma observação sobre o Meta ads

Se você realizar campanhas no Meta ads e não aceitar os termos de serviço do Meta, a AppsFlyer atribuirá a instalação. A disponibilidade do relatório é limitada da seguinte forma:

* **Disponível:** dashboards e relatórios agregados e de analytics
* **Não disponível:** dados brutos

<Tabs>
<Tab title="Meta Ads">

<div id="meta-ads-conversion-data" />

### Dados de conversão do Meta ads

| Nome do campo | Observações | Fonte de dados |
| --- | --- | --- |
| `match_type` | `srn`, `gp_referrer`, `probabilistic` | AF |
| `fonte_de_mídia` | Sempre `"Anúncios do Meta"` | AF |
| `agency` | nulo ou valor do parâmetro `af_prt` no link de atribuição | Meta Ads |
| `http_referrer` | Sempre `null` | Meta Ads |
| `retargeting_conversion_type` |  | AF |
| `af_canal` |  | Meta ads (publisher\_platform) |
| `af_status` | Sempre `"Non-organic"` | AF |
| `id_anúncio` | Somente para uso interno do Meta ads. | Meta ads (ad\_id) |
| `click_time` |  | AF |
| `install_time` |  | AF |
| `is_first_launch` | `true`, `false` | Dispositivo |
| `id_conjunto_de_anúncios` | Disponível em dados brutos: Adset ID | Meta ads (campaign\_id) |
| `is_fb` | Sempre `true` | AF |
| `Carga útil` | Disponível em dados brutos: Nome da campanha | Meta ads (campaign\_group\_name) |
| `id_da_campanha` | Disponível em dados brutos: ID da campanha | Meta ads (campaign\_group\_id) |
| `is_paid` | Sempre `true` | Meta Ads |
| `adgroup` | Disponível em dados brutos: anúncio | Meta ads (adgroup\_name) |
| `adgroup_id` | Disponível em dados brutos: Ad ID | Meta ads (adgroup\_id) |
| `conjunto_de_anúncios` | Disponível em dados brutos: Adset | Meta ads (campaign\_name) |
| `af_siteid` | **mapeamento de af\_siteid:**  <br />  <br />***publisher\_platform*** → ***af\_siteid***  <br />Facebook → ""  <br />Instagram → Instagram  <br />AudienceNetwork → AudienceNetwork  <br />Messenger → Messenger  <br />unknown → unknown  <br />"" + is\_instagram=true → Instagram  <br />"" + is\_external=true → AudienceNetwork | Meta ads Google ASA Snap Twitter Oath |
| `af_sub[1-5]` | Sempre `null` | AppsFlyer |

**Observação:** os campos relacionados ao custo não estão disponíveis porque os anúncios do Meta não compartilham dados de custo na conversão. Se o <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#cost-clicks-and-impressions">compartilhamento de custos</Anchor> estiver ativado, os anúncios da Meta compartilham dados de custo com a AppsFlyer várias vezes ao dia.

</Tab>

<Tab title="Google Ads">

<div id="google-ads-conversion-data" />

### Dados de conversão do Google Ads

<table><thead><tr><th>Nome do campo</th><th>Observação</th></tr></thead><tbody><tr><td><code>match_type</code></td><td> Sempre <code>"srn"</code> </td></tr><tr><td><code>fonte_de_mídia</code></td><td>Sempre <code>"googleadwords_int"</code> </td></tr><tr><td><code>agency</code></td><td> <code>none</code> ou valor de <code>af_prt</code> </td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td><code>af_canal</code></td><td>Observação (1)</td></tr><tr><td><code>af_status</code></td><td>Sempre <code>"Non-organic"</code> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>adgroup_name</code></td><td> </td></tr><tr><td><code>id_conjunto_de_anúncios</code></td><td>Sempre <code>null</code> </td></tr><tr><td><code>campanha</code></td><td>Observação (3)</td></tr><tr><td><code>id_da_campanha</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>conjunto_de_anúncios</code></td><td>Observação (3)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>ad_event_id</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td>String vazia</td></tr><tr><td><code>af_ad_id</code></td><td>Disponível nos dados brutos quando o Google retorna o valor de <code>creative_id</code>.</td></tr><tr><td><code>af_ad_type</code></td><td><span>Tipo de anúncio do AdWords</span></td></tr><tr><td><code>af_adset</code></td><td>Disponível em dados brutos: Adset</td></tr><tr><td><code>af_adset_id</code></td><td>Disponível em dados brutos: Adset ID</td></tr><tr><td><code>af_c_id</code></td><td>Disponível em dados brutos: ID da campanha</td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Observação (2)</td></tr><tr><td><code>af_dp</code></td><td>Relevante apenas para <a href="./google-ads-adwords-integration-setup-for-advertisers#usando-deferred-deep-linking-em-campanhas-de-aplicativos" target="_blank">campanhas do Google App em feeds</a>.</td></tr><tr><td><code>af_keywords</code></td><td>Disponível em dados brutos: palavras-chave</td></tr><tr><td><code>af_prt</code></td><td> <code>none</code> ou valor de <code>af_prt</code> </td></tr><tr><td><code>af_reengagement _window</code></td><td>Disponível em dados brutos: janela de reengajamento </td></tr><tr><td><code>af_viewthrough_lookback</code></td><td>Disponível em dados brutos: janela de lookback para atribuição de view-through</td></tr><tr><td><code>click_url</code></td><td>Disponível em dados brutos: HTTP Referrer</td></tr><tr><td><code>click-timestamp</code></td><td>Fonte: AppsFlyer</td></tr><tr><td><code>cost_cents_USD</code></td><td>Observação (2)</td></tr><tr><td><code>external_account_id</code></td><td>ID da conta do AdWords</td></tr><tr><td><code>gclid</code></td><td> </td></tr><tr><td><code>lat</code></td><td> </td></tr><tr><td><code>network</code></td><td>Observação (1)</td></tr><tr><td><code>orig_cost</code></td><td>Observação (2)</td></tr><tr><td><code>video_id</code></td><td>Sempre <code>null</code> </td></tr><tr><td colspan="2"> <strong>Observações</strong><br/>(1) O Google faz uso de várias ad networks. Use <code>af_channel</code> em conjunto com <code>network</code> para derivar a fonte da instalação.<br/>(2) Esses campos retornam como 0. Se o anunciante ativar o compartilhamento de custos, o Google enviará os dados de custo da AppsFlyer várias vezes ao dia.<br/>(3) Use <code>campaign</code> e <code>af_adset</code> para personalizar o conteúdo do usuário.</td></tr></tbody></table>

</Tab>

<Tab title="ASA">

<div id="apple-search-ads-conversion-data" />

### Dados de conversão do Apple Search Ads

<table><thead><tr><th>Nome do campo</th><th>Observações</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Sempre <code>"srn"</code> </td></tr><tr><td><code>fonte_de_mídia</code></td><td>Sempre <code>"Apple Search Ads"</code> </td></tr><tr><td><del><code>adset</code></del></td><td>Observação (2)</td></tr><tr><td><code>id_conjunto_de_anúncios</code></td><td> </td></tr><tr><td><del><code>af_adset</code></del></td><td>Observação (2)</td></tr><tr><td><code>af_adset_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_click_lookback</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Observação (1)</td></tr><tr><td><del><code>af_keywords</code></del></td><td>Observação (2)—Use ID de palavras-chave</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Sempre <code>"Non-organic"</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> <code>null</code> ou valor de <code>af_prt</code> </td></tr><tr><td><del><code>campanha</code></del></td><td>Observação (2)</td></tr><tr><td><code>id_da_campanha</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> <code>true</code>, <code>false</code> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Observação (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Observação (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="3"> <strong>Observações</strong><br/>(1) O Apple Search Ads oferece suporte ao compartilhamento de custos em massa, não em dados de conversão.<br/>(2) Desativado desde 15 de fevereiro de 2021, devido à adoção do AdServices API pela Apple Search Ads. </td></tr></tbody></table>

</Tab>

<Tab title="Snapchat">

<div id="snapchat-conversion-data" />

### Dados de conversão do Snapchat

| String vazia | Observações |
| --- | --- |
| `match_type` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`   <br />Como um Advanced SRN, há suporte para todos os tipos de correspondência. |
| `fonte_de_mídia` | `"snapchat_int"` |
| `conjunto_de_anúncios` |  |
| `id_conjunto_de_anúncios` |  |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_c_id` |  |
| `af_canal` |  |
| `af_cpi` |  |
| `af_siteid` |  |
| `af_status` | Sempre `"Non-organic"` |
| `af_sub[1-5]` |  |
| `af_viewthrough_lookback` |  |
| `agency` |  |
| `campanha` |  |
| `id_da_campanha` |  |
| `click_time` |  |
| `cost_cents_USD` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `orig_cost` |  |
| `retargeting_conversion_type` |  |

</Tab>

<Tab title="Dica">

<div id="twitter-conversion-data" />

<div id="x-ads-conversion-data" />

### Dados de conversão do X Ads

| Nome do campo | Observações |
| --- | --- |
| `match_type` | Sempre `"srn"` |
| `fonte_de_mídia` | Sempre `"Twitter"` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_canal` |  |
| `af_siteid` |  |
| `af_status` | Sempre `"Non-organic"` |
| `af_sub[1-5]` |  |
| `agency` | Sempre `null` |
| `campanha` |  |
| `id_da_campanha` | `null` ou ID da campanha |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` | `true`, `false` |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` | Sempre `"none"` |

**Observação:** os campos de custo não aparecem no payload porque o Twitter não oferece suporte ao compartilhamento de dados de custo.

</Tab>

<Tab title="Tiktok">

<div id="tiktok-conversion-data" />

<div id="tiktok-for-business-conversion-data" />

### Dados de conversão do TikTok for Business

| Nome do campo | Observações |
| --- | --- |
| `match_type` | `srn`, `gp_referrer`, `id_matching`, `probabilistic`   <br />Como um Advanced SRN, há suporte para todos os tipos de correspondência. |
| `fonte_de_mídia` | `tiktokglobal_int` |
| `af_ad` |  |
| `af_ad_id` |  |
| `af_adset` |  |
| `af_adset_id` |  |
| `af_canal` | Sempre `"srn"` |
| `af_siteid` |  |
| `af_status` | Sempre `"Non-organic"` |
| `af_sub[1-5]` |  |
| `agency` |  |
| `campanha` |  |
| `id_da_campanha` |  |
| `click_time` |  |
| `http_referrer` |  |
| `install_time` |  |
| `is_first_launch` |  |
| `adgroup` |  |
| `adgroup_id` |  |
| `retargeting_conversion_type` |  |

**Observação:** os campos de custo não aparecem no payload porque o TikTok não oferece suporte ao compartilhamento de dados de custo.

</Tab>

<Tab title="Oath">

<div id="oath-ad-platforms-conversion-data" />

### Dados de conversão do Oath Ad Platforms

<table><thead><tr><th>Nome do campo</th><th>Observações</th></tr></thead><tbody><tr><td><code>match_type</code></td><td>Sempre <code>"srn"</code> </td></tr><tr><td><code>fonte_de_mídia</code></td><td>Sempre <code>"yahoogemini_int"</code> </td></tr><tr><td><code>conjunto_de_anúncios</code></td><td> </td></tr><tr><td><code>id_conjunto_de_anúncios</code></td><td> </td></tr><tr><td><code>af_ad</code></td><td> </td></tr><tr><td><code>af_ad_id</code></td><td> </td></tr><tr><td><code>af_c_id</code></td><td> </td></tr><tr><td><code>af_cpi</code></td><td>Observação (1)</td></tr><tr><td><code>af_siteid</code></td><td> </td></tr><tr><td><code>af_status</code></td><td>Sempre <code>null</code> </td></tr><tr><td><code>af_sub[1-5]</code></td><td> </td></tr><tr><td><code>agency</code></td><td> </td></tr><tr><td><code>campanha</code></td><td> </td></tr><tr><td><code>id_da_campanha</code></td><td> </td></tr><tr><td><code>campaign_type</code></td><td> </td></tr><tr><td><code>click_time</code></td><td> </td></tr><tr><td><code>cost_cents_USD</code></td><td>Observação (1)</td></tr><tr><td><code>http_referrer</code></td><td> </td></tr><tr><td><code>install_time</code></td><td> </td></tr><tr><td><code>is_first_launch</code></td><td> </td></tr><tr><td><code>adgroup</code></td><td> </td></tr><tr><td><code>adgroup_id</code></td><td> </td></tr><tr><td><code>orig_cost</code></td><td>Observação (1)</td></tr><tr><td><code>retargeting_conversion_type</code></td><td> </td></tr><tr><td colspan="2"> <strong>Observação</strong><br/>(1) O Oath é compatível com o compartilhamento de custos, mas envia dados relacionados a custos em massa, não em quantidades menores de dados de conversão.</td></tr></tbody></table>

</Tab>
</Tabs>

<div id="ua-conversion-with-other-ad-networks" />

## Conversão de UA com outras ad networks

Para outras ad networks, os dados na carga são afetados diretamente pelos <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">parâmetros no link de atribuição</Anchor>.

Examine as seguintes cargas JSON.

**Atenção!** Os dados de conversão retornam como uma estrutura de dados semelhante a um mapa. O desenvolvedor **não** interage com o JSON bruto.

<div id="applovin" />

<Accordion title="Applovin">

<div id="attribution-link" />

#### Link de atribuição:

```http HTTPS
https://app.appsflyer.com/com.company.app?af_ad=ad_name&af_ad_type=INTER
  &af_channel=video&af_siteid=123_site_id&af_c_id=b8******************************&
  af_adset=_DEFAULT&pid=applovin_int&c=campaign_name
  &af_click_lookback=7d&clickid=10****************
  &advertising_id=50********************************&af_ip=
```

<div id="payload" />

#### Carga:

```json
nulo ou valor do parâmetro af_prt no link de atribuição
```

* Os parâmetros no link de atribuição aparecem como campos na carga
* Outros campos na carga que **não estão no link de atribuição** aparecem com um valor nulo
* O AppLovin é compatível com o compartilhamento de custos de anúncios, mas envia dados de custo para a AppsFlyer em massa. Os campos relacionados ao custo retornam como 0.

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

<div id="attribution-link-1" />

#### Link de atribuição:

```http HTTPS
https://app.appsflyer.com/id123456789?
  af_ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &clickid=ab***************&redirect=false
  &ua=Mozilla/5.0+(iPhone;+CPU+iPhone+OS+12_1_2+like+Mac+OS+X)+AppleWebKit/605.1.15+(KHTML,+like+Gecko)+Mobile/16C101
  &af_lang=pt&imei=&af_sub1=&advertising_id=&af_ip=192.168.0.1&pid=ironsource_int
  &device_ip=192.168.0.1&c=campaign_name
  &idfa=01**********************************&af_siteid=123_site_id&
  af_enc_data=cN*********************************************************************
```

<div id="payload-1" />

#### Carga:

```json
{
      "adgroup": null,
      "af_enc_data": "cN*************************************************************************************",
      "campaign": "campaign_name",
      "media_source": "ironsource_int",
      "retargeting_conversion_type": "none",
      "adset_id": null,
      "campaign_id": null,
      "install_time": "2018-12-30 23:59:32.194",
      "adgroup_id": null,
      "redirect": "false",
      "orig_cost": "0.75",
      "click_time": "2018-12-30 23:58:54.517",
     "agency": null,
      "cost_cents_USD": "75",
      "adset": null,
      "advertising_id": "35****************************",
      "af_sub1": null,
      "af_ip": "192.168.0.1",
      "clickid": "ab*******************",
      "af_sub3": null,
      "af_cost_value": "0.75",
      "af_ref": "ironsource_5f******************************************",
      "af_siteid": "123_site_id",
      "http_referrer": null,
      "af_cost_model": "cpi",
      "af_ua": "Mozilla/5.0 (Linux; Android 8.0.0; SM-N950F Build/R16NW; wv) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/71.0.3578.99 Mobile Safari/537.36",
      "af_cost_currency": "USD",
      "af_sub5": null,
      "af_sub4": null,
      "af_lang": "en",
      "af_cpi": null,
      "af_click_lookback": "7d",
      "af_sub2": null,
      "af_status": "Non-organic"
  }
```

ironSource compartilha dados relacionados a custos com a AppsFlyer na conversão usando os campos `orig_cost`, `cost_cents_USD` e `af_cost_value`.

No entanto, os dados relacionados ao custo **não aparecem no link de atribuição**. O ironSource criptografa dados de custo e os armazena no campo `af_enc_data`.

</Accordion>

<div id="retargeting-conversion-data" />

## Dados de conversão de retargeting

O retargeting inclui dois tipos de conversões, reatribuição ou reengajamento.

> 👍 **Tip**
>
> **Carga útil**
>
> Os dados de conversão para retargeting nem sempre fornecem uma indicação clara quanto ao tipo de conversão. Consulte [fontes alternativas de dados de conversão](#fontes-de-dados-de-conversão-alternativas).

<div id="re-attribution-with-srns" />

### Reatribuição com SRNs

Quando um usuário é reatribuído por meio de uma SRN, a carga dos dados de conversão não indica que se trata de uma campanha de retargeting. Como as SRNs não usam links de atribuição, não há como definir um parâmetro `is_retargeting=true` no link de atribuição. Para **SRNs compatíveis com retargeting**, a AppsFlyer determina se o usuário deve ser reatribuído ou não.

Isso significa que não há como determinar, no nível do SDK, se uma instalação vem de uma campanha de retargeting. A única maneira é definir o nome da campanha de forma que indique uma campanha de retargeting.

> 📘 **Note**
>
> **Importante!**
>
> Definir o nome da campanha de forma que indique o retargeting **não é um método infalível**. Veja [exemplos para saber mais](#exemplos-de-aquisição-e-reatribuição-de-usuários-mistos).

<div id="re-attribution-with-regular-ad-networks" />

### Reatribuição com ad networks regulares

A atribuição a ad networks depende de links de atribuição. Sejam links de atribuição regulares ou OneLink, com retargeting, o link de atribuição sempre tem o parâmetro `is_retargeting=true` definido nele.

<div id="retargeting-campaign-with-criteo" />

<Accordion title="Campanha de retargeting com Criteo">

<div id="attribution-link-2" />

#### Link de atribuição

```http
https://app.appsflyer.com/id1234567895?pid=criteo_int&af_click_lookback=30d&
  c=campaign_name&is_retargeting=true&redirect=false&idfa=68**********************************
  &af_reengagement_window=30d
```

<div id="conversion-data-payload" />

#### Carga de dados de conversão

```json
 Observação
```

* Parâmetro `retargeting_conversion_type` - esse parâmetro indica o tipo de retargeting. Pode ser reatribuição, reengajamento ou nenhum.
* Parâmetro `is_retargeting: true` - este parâmetro indica que a instalação é uma instalação reatribuída
* `af_reengagement_window`: a janela de atribuição de reengajamento é o número de dias em que um evento pode ser atribuído a um **usuário reengajado**. Como essa é uma conversão de nova atribuição, esse parâmetro é redundante.

</Accordion>

<div id="re-attribution-with-deferred-deep-linking" />

### Reatribuição com deferred deep linking

Muitas vezes, é possível que você queira criar deep links para usuários reatribuídos que, por serem reatribuídos, não têm o aplicativo instalado. Por exemplo, você define uma campanha com o intuito de trazer de volta os usuários que desinstalaram o aplicativo. A campanha promove um produto ou serviço e você deseja atender os usuários com conteúdo relacionado ao produto ou serviço que você anuncia.

Isso é conhecido como deferred deep linking. A carga de dados de conversão para deferred deep linking vem do método `onConversionDataSuccess`.

<div id="deferred-deep-linking-with-srns" />

<Accordion title="Vinculação profunda adiada com SRNs">

Os parâmetros de deep link definidos nas campanhas de SRNs não estão disponíveis fora da SRN. Isso inclui o parâmetro `af_dp`, que contém o caminho do esquema no aplicativo. A única exceção para isso é ao se usar <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#usando-deferred-deep-linking-em-campanhas-de-aplicativos">Campanhas do Google App em Feeds</Anchor>. Para implementar deferred deep linking, uma lógica adicional deve ser aplicada para campanhas de SRN. Use os dados na resposta `onConversionSuccess`, como campanha, conjunto de anúncios, grupo de anúncios, para redirecionar de forma programática os seus usuários.

<div id="conversion-data-for-deferred-deep-linking-with-meta-ads" />

#### Dados de conversão para deferred deep linking com o Meta ads

<Tabs>
<Tab title="Android iOS">

```json
{
     "adset":"Adidas Running Shoes Women",
       "adgroup": null,
     "campaign_id":"6**********",
     "af_status":"Non-organic",
     "retargeting_conversion_type": "none",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,
     "is_first_launch":true,
     "click_time":"2017-07-18 12:55:05",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "campaign":"running shoes summer collection",
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "media_source":"Meta ads",
     "install_time":"2017-07-19 08:06:56.189",
     "af_sub2":null
  }
```

</Tab>

<Tab title="Exemplo">

```json
  {
     "media_source":"Meta ads",
     "campaign":"running shoes summer collection",
     "adset":"Running Shoes Women",
     "adgroup":null,
     "campaign_id":"6**********",
     "retargeting_conversion_type": "none",
     "af_status":"Non-organic",
     "agency":null,
     "af_sub3":null,
     "af_siteid":null,
     "adset_id":"6**********",
     "is_fb":true,  
   "is_first_launch":true,
     "click_time":"2017-07-17 16:23:18",
     "iscache":false,
     "ad_id":"6**********",
     "af_sub1":null,
     "is_paid":true,
     "af_sub4":null,
     "adgroup_id":"6**********",
     "is_mobile_data_terms_signed":true,
     "af_channel":"Facebook",
     "af_sub5":null,
     "install_time":"2017-07-18 15:10:50.190",
     "af_sub2":null
  }
```

</Tab>
</Tabs>

Você pode usar os dados na resposta getConversionData, como campanha, conjunto de anúncios etc., para redirecionar programaticamente seus usuários e exibir um conteúdo relevante para eles.

> 📘 **Note**
>
> **AppsFlyer**
>
> O aplicativo é um aplicativo de eCommerce especializado em roupas esportivas. Um usuário que não tem o aplicativo instalado interage com um anúncio e instala o aplicativo. Depois que o aplicativo é iniciado, o SDK retorna os dados de conversão. O desenvolvedor faz com que o aplicativo abra a atividade de **coleção de tênis de corrida de verão** (campanha) na loja, mostrando a categoria **tênis de corrida para mulheres** (conjunto de anúncios).

</Accordion>

<div id="deferred-deep-linking-with-attribution-links" />

<Accordion title="Deferred deep linking com links de atribuição">

Existem três maneiras de fazer o deep linking dos usuários:

<div id="uri-schemes" />

#### Esquemas URI

Ao usar esquemas URI, tanto para links de atribuição quanto para OneLink, o link de atribuição e a carga são os seguintes:

**Link de atribuição**

```http
http://app.appsflyer.com/com.appsflyer.nivisampleapp?pid=media_source_name
  &c=campaign_name&af_dp=superapp%3A%2F%2deeplink-activity
```

**Os links diretos universais do OneLink**

```http
// OneLink curto
  https://dhba.onelink.me/2rAD/71ba577e

  // OneLink longo
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true&af_dp=superapp%3A%2F%2deeplink-activity
```

**Carga útil**

```json
Android iOS
```

* `af_deeplink: true` - quando esse parâmetro aparecer e for definido como true, procure os campos `scheme` e `host`
* `scheme` e `host` - esses campos vêm do parâmetro `af_dp` no link de atribuição e indicam o esquema e a atividade para os quais o usuário deve ser direcionado por deep link

<div id="ios-universal-links-and-android-app-links" />

#### Universal Links do iOS e App Links do Android

Essas são as outras duas das três maneiras de realizar deep linking.

Ao usar Universal Links ou App Links, o OneLink e a carga são os seguintes:

**Os links diretos universais do OneLink**

```http
// OneLink curto
  https://dhba.onelink.me/2rAD/71ba577e

  // OneLink longo
  https://dhba.onelink.me/2rAD?pid=media_source_name&c=campaign_name
  &is_retargeting=true
```

**Carga útil**

```json
{
      "install_time": "2019-01-08 16:24:49.853",
      "cost_cents_USD": "0",
      "campaign": "campaign_name",
      "retargeting_conversion_type": "none",
      "is_first_launch": true,
      "click_time": "2019-01-08 16:24:14.322",
      "af_click_lookback": "7d",
      "orig_cost": "0.0",
      "af_status": "Non-organic",
      "iscache": "true",
      "shortlink": "71ba577e",
      "media_source": "media_source_name",
      "is_retargeting": true
  }
```

* Campo `shortlink` - este é o campo que indica o OneLink específico de onde o usuário vem. Ele ajuda o desenvolvedor a saber como proceder em termos de lançamento de uma atividade e veiculação de conteúdo. Outros campos, como `campaign` também podem ser usados para essa finalidade.

  > 🚧 **Important**
  >
  > **Importante!**
  >
  > O `shortlink` do campo não aparece na carga ao usar o OneLink longo.
  >
  > Em ambos os casos (OneLink curto ou longo), recomendamos adicionar um parâmetro personalizado que indique a atividade. Por exemplo `&deep_link_activity=shoes_cateogry`


> 📘 **Note**
>
> **Observação**
>
> O uso de Universal Links e App Links só é possível com o OneLink.

</Accordion>

<div id="re-engagement-with-srns" />

### Reengajamento com SRNs

Assim como nas campanhas de reatribuição, quando um usuário é reengajado por meio de uma SRN, os dados de conversão não indicam que se trata de uma campanha de reengajamento. Você pode definir o nome da campanha de forma que indique uma campanha de reengajamento.

<div id="re-engagement-with-regular-ad-networks" />

### Reengajamento com ad networks regulares

Aqui também, a carga dos dados de conversão não indica que o usuário vem de uma campanha de reengajamento. Para superar essa limitação, você pode definir o nome da campanha para indicar um reengajamento.

<div id="re-engagement-with-deep-linking" />

### Reengajamento com deep linking

Uma parte importante do reengajamento é enviar o usuário para uma atividade específica. Por exemplo, se você anunciar algum produto ou promoção. Nesses casos, recomendamos que você envie os usuários que clicam no anúncio diretamente para a atividade do aplicativo desse produto ou venda.

Para fazer isso, você usa deep linking. Os dados de conversão no deep linking são muito importantes. Eles contêm as informações necessárias para o desenvolvedor customizar a experiência do usuário e encaminhá-lo para a atividade correta.

<div id="reengagement-deep-linking-with-srns" />

<Accordion title="Reengajamento: deep linking com SRNs">

Os dados de conversão não estão disponíveis quando um usuário reengajado vem de uma SRN. O desenvolvedor precisa usar os métodos de SRN para obtê-lo na inicialização do aplicativo.

</Accordion>

<div id="reengagement-deep-linking-with-ad-networks" />

<Accordion title="Reengajamento: deep linking com ad networks">

Quando um usuário é engajado novamente e o aplicativo é iniciado, os seguintes dados de conversão ficam disponíveis no método `onAppOpenAttribution`:

Para iOS e Android, ao usar a versão curta do OneLink, os dados de conversão são um mapa estruturado de todos os parâmetros no link:

Exemplo:

```json
{
     af_dp: "superapp://Deeplink",
     pid: "media_source_name"
     c: "campaign_name",
     link: "https://abcd.onelink.me/12ab/12ab34c"
     is_retargeting: true
  }
```

* O desenvolvedor do aplicativo pode usar tais parâmetros, como `af_dp` e nome da campanha, para direcionar o usuário a uma atividade específica e exibir o conteúdo relevante.

> 🚧 **Important**
>
> **Importante!**
>
> Recomendamos usar a versão curta do OneLink. Clique <Anchor target="_blank" href="/marketers/pt/docs/understand-onelink-short-vs-long-urls">aqui</Anchor> para saber mais.

Outro motivo para usar a versão curta do OneLink é a estrutura de dados de conversão que a versão longa retorna. Ao usar a versão longa, os dados de conversão são um mapa com um único campo chamado `link` que contém todo o OneLink longo.

```json
{
     "link": "https://abcd.onelink.me/12ab?pid=media_source&c=campaign_name&is_retargeting=true&af_dp=superapp%3A%2F%2FDeepLink"
  }
```

</Accordion>

<div id="alternative-conversion-data-sources" />

### Fontes de dados de conversão alternativas

* A Push API oferece uma carga de conversão detalhada que indica reatribuição ou reengajamento. As cargas da Push API incluem um campo chamado `re_targeting_conversion_type`. Esse campo indica o tipo de conversão, seja reatribuição ou reengajamento. Para saber mais, consulte nosso <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">guia de Push API</Anchor>.
* Os relatórios de dados brutos também contêm indicadores para o tipo de conversão. No relatório de dados brutos para conversões de retargeting, há uma coluna chamada ***nome do evento***. O valor nesta coluna é ***reengajamento*** ou ***reatribuição*** de acordo com o tipo de conversão.

<div id="examples-of-mixed-user-acquisition-and-re-attribution" />

### Exemplos de aquisição e reatribuição de usuários mistos

> 📘 **Note**
>
> **Twitter**
>
> 1. Um usuário instala seu aplicativo e depois o desinstala. O ato de instalação coloca o usuário em uma <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor>. Você define uma campanha de aquisição de usuários (não de retargeting) com anúncios da Meta. Você também configura a integração da AppsFlyer com o Meta ads para permitir o retargeting.
>
>    Ainda na janela de reatribuição, o usuário vê o anúncio, clica nele e reinstala o aplicativo. De acordo com a AppsFlyer, o usuário é um usuário reatribuído.
>
>    Isso se deve a dois fatores:
>
>    1. A configuração com o Meta ads permite o retargeting
>    2. O usuário está na janela de reatribuição
>
>    Nesse caso, o nome da campanha não indica a reatribuição.
> 2. Vamos pegar o mesmo exemplo, só que desta vez o usuário está fora da janela de reatribuição. Nesse caso, a instalação é uma nova instalação não orgânica.
> 3. Vamos avaliar outro exemplo. Você define uma campanha de retargeting no Meta ads. Alguns usuários se deparam com a campanha e instalam o app. No entanto, esses usuários instalam o aplicativo pela primeira vez. Esses usuários não são considerados usuários reatribuídos. Em vez disso, a AppsFlyer os considera como usuários provenientes de uma campanha de aquisição de usuários.

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HCY86CKDJK9TNHPAZB0QX2ZX=vis%C3%A3o-geral nonorganic-conversion-data-payload-fields=campos-de-carga-de-dados-de-convers%C3%A3o-n%C3%A3o-org%C3%A2nica h_01HCY86CKDEMB3428YHCNJQA5R=campos-de-carga-de-dados-de-convers%C3%A3o-n%C3%A3o-org%C3%A2nica fields-always-available=campos-sempre-dispon%C3%ADveis h_01HCY86CKDBQRGAY7GHNBJE4WK=campos-sempre-dispon%C3%ADveis fields-available-in-some-cases=campos-dispon%C3%ADveis-em-alguns-casos h_01HCY86CKDYQMYB9BQ4MXWP8A5=campos-dispon%C3%ADveis-em-alguns-casos additional-fields=campos-adicionais h_01HCY86CKD47M85AZVEA5C4JH7=campos-adicionais limitations=limita%C3%A7%C3%B5es h_01HCY86CKEFX646H9BSKSFGZ36=limita%C3%A7%C3%B5es h_01HCY86CKEZ2483XB461M2C9EC=custom-parameter-names ua-conversion-data-with-srns=dados-de-convers%C3%A3o-de-ua-com-srns h_01EGKTQN6XDYHA60P2WKHBBVFT=dados-de-convers%C3%A3o-de-ua-com-srns a-note-about-facebook=uma-observa%C3%A7%C3%A3o-sobre-o-meta-ads h_01HCY86CKENFEGX53G9G4SGPSK=uma-observa%C3%A7%C3%A3o-sobre-o-meta-ads facebook-conversion-data=dados-de-convers%C3%A3o-do-meta-ads h_01HCY86CKE658H36F3VJQMATQK=dados-de-convers%C3%A3o-do-meta-ads h_01HCY86CKF6FY96PAWB5Y7YXSQ=google-ads-conversion-data h_01HCY86CKFMNNNJZTPGK4870YN=apple-search-ads-conversion-data h_01HCY86CKF26JRT64JR9JZEAKJ=snapchat-conversion-data h_01HCY86CKFM94SQWYARCM0GEJ9=twitter-conversion-data h_01HSQRQSK8W9K6871K0EWHDF76=tiktok-conversion-data h_01HCY86CKFS5SJBECSY42VRJWP=oath-ad-platforms-conversion-data ua-conversion-with-other-ad-networks=convers%C3%A3o-de-ua-com-outras-ad-networks h_01HCY86CKFB0GEJRTYSXN9YZ08=convers%C3%A3o-de-ua-com-outras-ad-networks h_01HCY86CKFY787RD4BHQDVEVFV=applovin attribution-link=link-de-atribui%C3%A7%C3%A3o h_01HCY86CKFXM5XXJZSPXPB6397=link-de-atribui%C3%A7%C3%A3o payload=carga h_01HCY86CKFDDXWT2KKFTKKBGHM=carga h_01HCY86CKFV55GYY7C51D7F72S=ironsource attribution-link::a45a1b4a=link-de-atribui%C3%A7%C3%A3o-1 h_01HCY86CKFYGEYR2TRPSD87KDA=link-de-atribui%C3%A7%C3%A3o-1 payload::81867f5c=carga-1 h_01HCY86CKFKKFQDG1P42R1FSDJ=carga-1 retargeting-conversion-data=dados-de-convers%C3%A3o-de-retargeting h_01EHQ74JS84509GT6M93SZA4HX=dados-de-convers%C3%A3o-de-retargeting reattribution-with-srns=reatribui%C3%A7%C3%A3o-com-srns h_01HCY86CKFAVWP1W0ZNEN5P30A=reatribui%C3%A7%C3%A3o-com-srns reattribution-with-regular-ad-networks=reatribui%C3%A7%C3%A3o-com-ad-networks-regulares h_01HCY86CKF1PV8MRR902RAHQGW=reatribui%C3%A7%C3%A3o-com-ad-networks-regulares h_01HCY86CKF1RGK01VTV3EEHQVM=retargeting-campaign-with-criteo attribution-link::c16e96bb=link-de-atribui%C3%A7%C3%A3o-2 h_01HCY86CKFSKBBMFKA8NN8XTPC=link-de-atribui%C3%A7%C3%A3o-2 conversion-data-payload=carga-de-dados-de-convers%C3%A3o h_01HCY86CKG2YQQC629SC3RAFKE=carga-de-dados-de-convers%C3%A3o reattribution-with-deferred-deep-linking=reatribui%C3%A7%C3%A3o-com-deferred-deep-linking h_01HCY86CKGXV50H79R0YH1GB2C=reatribui%C3%A7%C3%A3o-com-deferred-deep-linking h_01HCY86CKG12YRGFEEJ27DQART=deferred-deep-linking-with-srns conversion-data-for-deferred-deep-linking-with-facebook=dados-de-convers%C3%A3o-para-deferred-deep-linking-com-o-meta-ads h_01HCY86CKGX9VHSV3ASKXMFM0X=dados-de-convers%C3%A3o-para-deferred-deep-linking-com-o-meta-ads h_01HCY86CKG3XWM4X0YH7WYCEH4=deferred-deep-linking-with-attribution-links uri-schemes=esquemas-uri h_01HCY86CKGDM2NE1FCRC92K8R0=esquemas-uri ios-universal-links-and-android-app-links=universal-links-do-ios-e-app-links-do-android h_01HCY86CKGY1NE4214DES0Y2AV=universal-links-do-ios-e-app-links-do-android reengagement-with-srns=reengajamento-com-srns h_01HCY86CKG4TRYR6TWYYVB0FJE=reengajamento-com-srns reengagement-with-regular-ad-networks=reengajamento-com-ad-networks-regulares h_01HCY86CKGM2JS7C9T71R6GPH1=reengajamento-com-ad-networks-regulares reengagement-with-deep-linking=reengajamento-com-deep-linking h_01HCY86CKG0NPQAA2ZRWWNKGQD=reengajamento-com-deep-linking h_01HCY86CKGEBHQVFRGJH96KDFJ=reengagement-deep-linking-with-srns h_01HCY86CKGJ9HG7AGB5MFP33RK=reengagement-deep-linking-with-ad-networks alternative-conversion-data-sources=fontes-de-dados-de-convers%C3%A3o-alternativas h_01HCY86CKG3N6ZXV70G4VMZ0X5=fontes-de-dados-de-convers%C3%A3o-alternativas examples-of-mixed-user-acquisition-and-reattribution=exemplos-de-aquisi%C3%A7%C3%A3o-e-reatribui%C3%A7%C3%A3o-de-usu%C3%A1rios-mistos h_01HCY86CKGK9DVVB7T6CVNB8ZN=exemplos-de-aquisi%C3%A7%C3%A3o-e-reatribui%C3%A7%C3%A3o-de-usu%C3%A1rios-mistos" />

---
title: Melhores práticas de URL de atribuição do site PBA
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2022-05-23T05:29:27Z'
  edited_at: '2026-08-18T00:23:55Z'
  id: 6313062676497
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/6313062676497
---
> **Em resumo:** Melhores práticas para atribuir suas campanhas de atribuição do site com a melhor granularidade de campanha disponível.

## URLs de atribuição do site PBA

Para obter os melhores resultados de granularidade de campanha combinados com a atribuição mais precisa nos seus dados de atribuição do site, preencha as URLs (links) que direcionam os usuários ao seu site usando as práticas detalhadas neste artigo.

### Parâmetros de URL: grupo e prioridade

A solução de atribuição do site da AppsFlyer oferece suporte a várias classes de parâmetros de campanha. As classes são classificadas por prioridade da seguinte forma:

* [Prioridade máxima] PID
* IDs de clique de canais específicos, como Google, DoubleClick e Microsoft
* [Prioridade mínima] UTM

As <Anchor target="_blank" href="/marketers/pt/docs/pba-media-source-attribution-rules">regras de atribuição de canal de mídia do PBA</Anchor> determinam como um determinado usuário recebe a atribuição. As classes de parâmetros são classificadas por prioridade. Se mais de uma classe de parâmetros for encontrada em um link, a classe com a prioridade mais alta receberá a atribuição.

#### Parâmetros compatíveis

| # | Parâmetro | Usado para | Classe de parâmetros | Disponível no Dashboard | Campo de dados brutos do PBA |
| --- | --- | --- | --- | --- | --- |
| 1 | pid | Canal de mídia | PID | S | fonte\_de\_mídia |
| 2 | C | Campaign name | PID | S | Twitter |
| 3 | af\_c\_id | ID da campanha | PID | S | id\_da\_campanha |
| 4 | af\_adset | Nome do Adset | PID | S | Extrair de query\_params |
| 5 | af\_adset\_id | Adset ID | PID | S | Extrair de query\_params |
| 6 | af\_ad | Ad name | PID | S | Extrair de query\_params |
| 7 | af\_ad\_id | ID do anúncio | PID | S | Extrair de query\_params |
| 8 | utm\_source | Canal de mídia | UTM | S | fonte\_de\_mídia |
| 9 | utm\_medium | Tipo de mídia | UTM | S | media\_type |
| 10 | utm\_campaign | Campaign | UTM | S | Twitter |

## Melhores práticas para parâmetros de URL

### Selecionar parâmetros de URL

Cada classe de parâmetros funciona no contexto de um silo. Portanto, se você precisar de URLs com várias classes, a URL deverá ter os parâmetros relevantes de cada classe. Ao fazer isso, a granularidade dos seus relatórios é otimizada.

O uso de parâmetros de várias classes é ilustrado no contexto de anúncios da Meta da seguinte forma:

* **Grupo PID**:  `www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}`
* **Grupo UTM**: `www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}`
* Se você combinar classes, mas incluir apenas alguns dos parâmetros obrigatórios, a AppsFlyer talvez não forneça a granularidade completa. Por exemplo, se você usar `www.website.com?utm_source=facebook&c={{campaign.name}}`, ocorrerá o seguinte:
  * A AppsFlyer usa a classe UTM porque não há nenhuma classe PID e determina o canal de mídia usando utm\_source.
  * No entanto, a campanha não pode ser determinada, já que *c=* faz parte da classe PID, mas pid não está incluído.
  * Para resolver isso, supondo que você precise de utm\_source para outras finalidades, considere esta opção: `www.website.com?pid=facebook_int&c={{campaign.name}}&utm_source=facebook`. Com essa estrutura, a AppsFlyer usa a classe PID para identificar o canal de mídia. Outros parâmetros PID, como c=, podem ser incluídos, e utm\_source é desconsiderado porque tem prioridade menor.

### Implemente URLs dinâmicas usando macros de ad network

Use macros de network (também conhecidas como parâmetros valuetrack) para economizar tempo ao criar modelos e aplicar parâmetros de URL para campanhas pagas.

As networks usam macros diferentes para preencher os parâmetros na URL. Consequentemente, você deve verificar a documentação da ad network para confirmar que está usando as macros corretamente. Por exemplo, se você quiser transmitir o ID da campanha em af\_c\_id, pode evitar codificar manualmente o ID real da campanha para cada URL e simplesmente usar as macros:

* Google Adwords: `www.website.com?af_c_id={campaignid}`
* Anúncios da Meta: `www.website.com?af_c_id={{campaign.id}}`
* Anúncios do Pinterest: `www.website.com?af_c_id={campaignid}`
* Anúncios do Snapchat: `www.website.com?af_c_id={{campaign.id}}`
* Anúncios da Microsoft (Bing): `www.website.com?af_c_id={campaignid}`

### Uso consistente de maiúsculas e minúsculas nos parâmetros

Os valores dos parâmetros diferenciam maiúsculas e minúsculas. Por exemplo, utm\_source=channel1 e utm\_source=CHANNEL1 são considerados fontes de mídia diferentes. Por isso, verifique se você está usando maiúsculas e minúsculas de forma consistente.

### Use a integração com o Google Ads para automatizar a granularidade

No caso de campanhas do Google Ads, você pode obter granularidade da campanha integrando o PBA à sua <Anchor target="_blank" href="/marketers/pt/docs/integrating-google-ads-auto-tagging-gclid-campaign-data-into-pba">Google Ads</Anchor> conta. Isso garante que seus dados sejam preenchidos com todos os dados da hierarquia da campanha sem a necessidade de parâmetros PID ou UTM na URL.

## Erros comuns de parâmetros de URL que você deve evitar

### Pontos de interrogação

* Use apenas um ponto de interrogação entre a página de destino da URL e os parâmetros
* Não deve haver nenhum outro ponto de interrogação na URL

Por exemplo:  `www.website.com?parâmetros`

Exemplos de usos **incorretos**: 

`www.website.com??parâmetros`

`www.website.com?parameter1?parameter2`

### Símbolos de âncora

Símbolos de âncora (#) não devem ser usados na URL. O uso de um símbolo de âncora em uma URL pode fazer com que os parâmetros após esse símbolo não sejam carregados nem coletados pelo nosso SDK web.

<div data-zendesk-anchors="pba-website-attribuiton-urls=urls-de-atribui%C3%A7%C3%A3o-do-site-pba h_01KQS4QK4Z70GC9VVFQCFHK4SQ=urls-de-atribui%C3%A7%C3%A3o-do-site-pba url-parameters%E2%80%94group-and-priority=par%C3%A2metros-de-url-grupo-e-prioridade h_01KQS4QK4Z3YTXHGQMYNZ36DZ1=par%C3%A2metros-de-url-grupo-e-prioridade supported-parameters=par%C3%A2metros-compat%C3%ADveis h_01KQS4QK4Z1RVQKZX94MJJQSQW=par%C3%A2metros-compat%C3%ADveis url-parameter-best-practices=melhores-pr%C3%A1ticas-para-par%C3%A2metros-de-url h_01KQS4QK4Z3V5Y9RSM20VTESDP=melhores-pr%C3%A1ticas-para-par%C3%A2metros-de-url selecting-url-parameters=selecionar-par%C3%A2metros-de-url h_01KQS4QK4ZP6WCWEG4FH9R1N8Q=selecionar-par%C3%A2metros-de-url implement-dynamic-urls-using-ad-network-macros=implemente-urls-din%C3%A2micas-usando-macros-de-ad-network h_01KQS4QK50MTKRPPNYNWZKPMSD=implemente-urls-din%C3%A2micas-usando-macros-de-ad-network consistent-case-within-parameters=uso-consistente-de-mai%C3%BAsculas-e-min%C3%BAsculas-nos-par%C3%A2metros h_01KQS4QK50K5Q5NV2VQTASHDGD=uso-consistente-de-mai%C3%BAsculas-e-min%C3%BAsculas-nos-par%C3%A2metros use-google-ads-integration-to-automate-granularity=use-a-integra%C3%A7%C3%A3o-com-o-google-ads-para-automatizar-a-granularidade h_01KQS4QK505R1Y4TED19FWCY6M=use-a-integra%C3%A7%C3%A3o-com-o-google-ads-para-automatizar-a-granularidade common-url-parameter-mistakes-to-avoid=erros-comuns-de-par%C3%A2metros-de-url-que-voc%C3%AA-deve-evitar h_01KQS4QK50XDC8216WBJJ6DJJ7=erros-comuns-de-par%C3%A2metros-de-url-que-voc%C3%AA-deve-evitar question-marks=pontos-de-interroga%C3%A7%C3%A3o h_01KQS4QK50KAS1DVXASYB81PGJ=pontos-de-interroga%C3%A7%C3%A3o anchor-signs=s%C3%ADmbolos-de-%C3%A2ncora h_01KQS4QK507423MN3RWN94CWEY=s%C3%ADmbolos-de-%C3%A2ncora" />

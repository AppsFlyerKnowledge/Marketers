---
title: >-
  Plataforma de colaboração de dados (DCP) - Prepare-se para a mensuração e a
  colaboração
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-01-27T08:47:05Z'
  edited_at: '2026-08-19T00:06:25Z'
  id: 32144170371985
  locale: pt
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/pt/articles/32144170371985
---
> **Resumo:** Descubra como criar fontes de dados de mensuração e como fornecer acesso a elas de uma forma que possa ser digerida para atribuição.

<div id="overview" />

## Visão geral

A primeira etapa na configuração da mensuração é preparar os três inputs que a alimentam: conversões, engajamentos e mapeamento de campanhas. Esses inputs devem ser preparados com base no esquema predefinido ou na estrutura do evento, dependendo do modo de fornecimento de dados: eventos in-app ou arquivos fonte personalizados.

Quando você utiliza arquivos fonte personalizados, o trabalho de atribuição é acionado automaticamente quando as pastas de conversão e de registro de engajamento necessárias são enviadas para a nuvem. Para o modo de evento in-app, o trabalho é acionado quando os eventos in-app relevantes são selecionados.

<div id="prepare-in-app-events" />

## Prepare a lista de eventos in-app

Você pode enviar dados de conversão e engajamento através de eventos in-app enviados pelo SDK da AppsFlyer integrado ao seu aplicativo.

<div id="note" />

> 📘 **Nota**
>
> Se você já estiver enviando eventos in-app da AppsFlyer através do SDK ou através de solicitações S2S, essa opção pode ser mais fácil de implementar do que a opção de arquivo fonte personalizado.

<div id="prepare-conversion-inapp-events" />

<Accordion title="Prepare os eventos in-app de conversão">

O evento in-app de conversão deve incluir a informação SKU. No exemplo seguinte, a chave `af_order_info` identifica as informações de SKU:

```
"event_value": {
    "af_currency": "EUR",
    "af_content": "retail",
    "af_order_id": "637f7c400f0e3fddd9e5bcbc",
    "af_order_info": [
        {
            "sku": "a",
            "revenue": 1.1,
            "qty": 2
        },
        {
            "sku": "b",
            "revenue": 100.5,
            "qty": 1
        }
    ]
}
```

Para mais informações sobre como preparar eventos in-app, consulte a seção [Criar eventos in-app](#create-inapp-events) abaixo.

</Accordion>

<div id="prepare-engagement-inapp-events" />

<Accordion title="Prepare eventos in-app de reengajamento">

<Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#onsite-and-offsite-campaign-measurement">As campanhas on-site</Anchor> podem receber engajamentos através de eventos in-app. O evento in-app de engajamento deve incluir os dados de atribuição na chave `event_value`. Veja, como exemplo, a seguinte estrutura JSON `event_value`:

```
"event_value": {
    "media_source": "onsite",
    "campaign_name": "winter_bags",
    "campaign_id": "637f7c400f0e3fddsdfaafe33",
    "engagement_type": "click"
}
```

Pode usar os campos abaixo na sua chave JSON `evant_value`:

| **Campo** | **Descrição** | **Obrigatório** | **Disponível no esquema de eventos in-app** | **Tipo** |
| --- | --- | --- | --- | --- |
| `id_da_campanha` | ID da campanha | Sim | Não | `string` |
| `campaign_name` | Nome da campanha | Não | Não | `string` |
| `engagement_type` | Distingue entre cliques e impressões | Sim | Não | `string` |
| `fonte_de_mídia` | Canal de mídia restrito ou atribuído a um evento (<Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">saiba mais</Anchor>) | Sim | Não | `string` |
| `id_anúncio` | ID do anúncio | Não | Não | `string` |
| `ad_name` | Nome do anúncio | Não | Não | `string` |
| `ad_type` | Exemplo: banner, footer | Não | Não | `string` |
| `id_conjunto_de_anúncios` | ID do conjunto de anúncios, identifica um grupo que contém um ou mais anúncios | Não | Não | `string` |
| `adset_name` | Nome do conjunto de anúncios, identifica um grupo que contém um ou mais anúncios | Não | Não | `string` |
| `Canal` | Fonte do canal de mídia Fonte do canal de mídia Fonte do canal de mídia Exemplo: YouTube para Google, Instagram para Meta Ads | Não | Não | `string` |

Para mais informações sobre como preparar eventos in-app, consulte a seção Criar eventos in-app abaixo.

</Accordion>

<div id="create-inapp-events" />

<Accordion title="Criar eventos in-app">

Para fornecer dados de conversão e engajamento através de eventos in-app, configure o SDK da AppsFlyer integrado ao seu aplicativo. Para mais informações sobre a criação de eventos in-app, consulte:

* <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">Visão geral de eventos no aplicativo (in-app events)</Anchor>
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">Implementar eventos in-app ao SDK da AppsFlyer - para desenvolvedores</Anchor>

</Accordion>

<div id="prepare-custom-source-files" />

## Preparar arquivos fonte personalizados

Se você estiver executando uma [campanha on-site](#onsite-and-offsite-campaign-measurement), pode usar arquivos fonte personalizados como fonte das suas conversões e engajamentos, usando o esquema descrito nas tabelas abaixo.

<div id="the-conversion-source-scheme" />

<Accordion title="Esquema da fonte de conversão">

Use o esquema na tabela abaixo para criar um arquivo fonte de conversão personalizado:   
O esquema de conversão é unitário para os tipos de campanha off-site e on-site e para os diferentes parceiros de mídia.   
O esquema de conversão é unitário para os tipos de campanha off-site e on-site e para os diferentes parceiros de mídia.

<div id="media-partners" />

#### Parceiros de mídia selecionados:

**G**: Google

**M**: Meta

<div id="background-colors" />

#### Cores de fundo:

      Campos obrigatórios

      Campos recomendados

      Qualquer um dos campos selecionados é obrigatório

      Os campos passam por hashing de acordo com as regras especificadas pela SRN.

<table><colgroup><col/><col/><col/><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th>Categoria</th><th>Parâmetro</th><th>Descrição</th><th>Tipo de valor esperado</th><th>CMN</th><th colspan="4">Parceiros de mídia</th></tr><tr><th></th><th></th><th></th><th></th><th></th><th colspan="2">Aplicação</th><th colspan="2">Web</th></tr><tr><th></th><th></th><th></th><th></th><th></th><th>G</th><th>M</th><th>G</th><th>M</th></tr></thead><tbody><tr><td>Hora do evento, arredondada para a hora mais próxima</td><td>Receita associada ao SKU na moeda fornecida no campo <code>event_revenue_currency</code>.</td><td>Identificador exclusivo do evento.</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>nome_do_evento</td><td>Nome ou tipo do evento (por exemplo, "purchase", "clique").</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_time</td><td>Carimbo de data/hora de quando o evento ocorreu.</td><td>data e hora</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Informações do aplicativo</td><td>ativado</td><td>Um ID exclusivo do usuário do app, definido pelo proprietário do app.</td><td>string</td><td>✓</td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>ativado</td><td>Nome do aplicativo.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>app_version</td><td>Número da versão do aplicativo.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td>Validações de dados</td><td>facebook_browser_id</td><td>Identificador único para rastreamento do navegador do Facebook.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_cookie</td><td>Identificador de clique para atribuição de anúncios do Facebook.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>gbraid</td><td>Identificador de atribuição de anúncios do Google.</td><td>string</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td> </td><td>google_click_id</td><td>ID único para rastreamento de cliques de anúncios do Google.</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>wbraid</td><td>Identificador de atribuição baseado na web para o Google.</td><td>string</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td> </td><td>tiktok_id</td><td>Identificador exclusivo para rastreamento do TikTok.</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Dados da campanha</td><td>id_da_campanha</td><td>Identificador exclusivo da campanha de marketing.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>install_id</td><td>Identificador do evento de instalação do aplicativo.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td>Dados de conversão</td><td>sku</td><td>SKUs dos produtos envolvidos na conversão.</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>sku_quantity</td><td>Identificador exclusivo de um produto (SKU).</td><td>número inteiro</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>sku_revenue</td><td>Receita gerada pelo evento.</td><td>Número decimal</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>event_revenue</td><td>Receita gerada por este evento.</td><td>Obrigatório</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>event_currency</td><td>Moeda do valor da receita.</td><td>Número decimal</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Informação do dispositivo</td><td>client_ip</td><td>Endereço IP do usuário ou dispositivo.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>client_user_agent</td><td>String do agente do usuário do dispositivo/navegador do usuário.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>device_category</td><td>Categoria do dispositivo do usuário (por exemplo, mobile, desktop).</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>plataforma (os?)</td><td>Sistema operacional do dispositivo do usuário (por exemplo, iOS, Android).</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>os_version</td><td>Versão do sistema operacional do dispositivo.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td>ID do usuário</td><td>advertising_id</td><td>Identificador único para fins publicitários (por exemplo, IDFA).</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>appsflyer_id</td><td>Identificador exclusivo do app na Appsflyer.</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>android_id</td><td>Identificador exclusivo de dispositivo Android.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>idfa</td><td>Definido pelo anunciante</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>idfv</td><td>Vendor ID fornecido pelo iOS.</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>client_id</td><td>Identificador exclusivo do cliente (por exemplo, gerado pelo sistema).</td><td>string</td><td>✓</td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_client_id</td><td>nenhuma regra especificada</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>tiktok_hashed_client_id</td><td>aparar, converter para minúsculas</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>cookie</td><td>Dados de cookie do navegador para rastreamento de usuário/sessão.</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>first_name</td><td>Primeiro nome do usuário.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>sobrenome</td><td>Sobrenome do utilizador.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>número de telefone</td><td>Número de telefone do utilizador.</td><td>Obrigatório</td><td></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>data de nascimento</td><td>Data de nascimento do utilizador.</td><td>data e hora</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>género</td><td>Género do utilizador.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>language</td><td>Idioma ou localidade preferidos do utilizador.</td><td>string</td><td></td><td></td><td>✓</td><td></td><td></td></tr><tr><td> </td><td>campanhas de mensagens por e-mail</td><td>Endereço de e-mail do utilizador.</td><td>string</td><td></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>e-mail com Hashing do TikTok</td><td>remover espaços, converter para minúsculas, remover pontos de endereços de e-mail do Google</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>telefone com Hashing do TikTok</td><td>E164</td><td>string</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>e-mail com Hashing do Google</td><td>remover espaços, converter para minúsculas, remover pontos de endereços de e-mail do Google</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>telefone com Hashing do Google</td><td>E164</td><td>string</td><td></td><td>✓</td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>nome com Hashing do Google</td><td>remover espaços, converter para minúsculas</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>apelido com Hashing do Google</td><td>remover espaços, converter para minúsculas</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>e-mail com Hashing do Facebook</td><td>remover espaços, converter para minúsculas</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>telefone com Hashing do Facebook</td><td>formato personalizado (sem +?)</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_first_name</td><td>minúsculas, sem pontuação</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_last_name</td><td>minúsculas, sem pontuação</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_date_of_birth</td><td>YYYYMMDD</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_gender</td><td>recomenda-se f/m, mas qualquer valor com hash é aceitável</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td>Atributos do usuário</td><td>att_status</td><td>Status da App Tracking Transparency (ATT) para o consentimento do usuário.</td><td>string</td><td></td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td>Localização do dispositivo</td><td>Região</td><td>Região geográfica do usuário.</td><td>string</td><td>✓</td><td></td><td></td><td></td><td></td></tr><tr><td> </td><td>cidade</td><td>Cidade associada ao usuário.</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>estado</td><td>Estado ou província do usuário.</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>código_país</td><td>Código ISO do país do usuário.</td><td>string</td><td>✓</td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>zip_code</td><td>Código postal/CEP do usuário.</td><td>string</td><td></td><td></td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td> </td><td>street</td><td>Endereço do usuário (se disponível).</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>google_hashed_street</td><td>remover espaços em branco; minúsculas</td><td>string</td><td></td><td></td><td></td><td>✓</td><td></td></tr><tr><td> </td><td>facebook_hashed_city</td><td>minúsculas, sem pontuação, sem espaços</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_state</td><td>ANSI para os EUA, em minúsculas, sem pontuação, sem espaços</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_zip_code</td><td>regras especiais para EUA/Reino Unido, em minúsculas, sem pontuação, sem espaços</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td> </td><td>facebook_hashed_country_code</td><td>Código do país usando ISO 3166 (alfa-2).</td><td>string</td><td></td><td></td><td>✓</td><td></td><td>✓</td></tr><tr><td>Dados de referência/tráfego</td><td>referrer_url</td><td>URL do site que encaminhou o usuário para a página atual.</td><td>string</td><td></td><td></td><td></td><td></td><td>✓</td></tr><tr><td> </td><td>source_url</td><td>URL de origem em que o usuário interagiu pela primeira vez com a campanha.</td><td>string</td><td></td><td></td><td></td><td></td><td>✓</td></tr></tbody></table>

</Accordion>

<div id="the-engagement-source-scheme" />

<Accordion title="Necessário na fonte de dados personalizada">

Use o esquema abaixo para criar a fonte de dados de engajamento.

<div id="note-1" />

> 📘 **Nota**
>
> Os campos de Informações Pessoais Identificáveis (PII) mapeados no esquema de fonte de engajamento devem ter uma intersecção não vazia com as PII mapeadas no esquema de fonte de conversão acima

| **Campo** | **Descrição** | Obrigatório | **Tipo de valor esperado** |
| --- | --- | --- | --- |
| `appsflyer_id` | Um ID exclusivo gerado pelo SDK quando o app está instalado | Campo opcional de PII. Um campo de PII é obrigatório. | `string` |
| `cuid` | Um ID exclusivo do usuário do app, definido pelo proprietário do app. | Campo opcional de PII. Um campo de PII é obrigatório. | `string` |
| `idfa` | Advertising ID que pode ser redefinido pelo usuário em dispositivos iOS. Se não estiver disponível, é preenchido com zeros | Campo opcional de PII. Um campo de PII é obrigatório. | `string` |
| `idfv` | Vendor ID fornecido pelo iOS. | Campo opcional de PII. Um campo de PII é obrigatório. | `string` |
| `ativado` | Identificador exclusivo do app na Appsflyer. Exemplo: iOS: `id123456789`, Android: `com.appsflyer.referrersender` | Opcional | `string` |
| `id_da_campanha` | ID da campanha | Obrigatório | `string` |
| `campaign_name` | Nome da campanha | Opcional | `string` |
| `fonte_de_mídia` | Canal de mídia restrito ou atribuído a um evento (<Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">saiba mais</Anchor>) | Obrigatório | `string` |
| `engagement_type` | Distingue entre cliques e impressões | Obrigatório | `string` |
| `nome_do_evento` | Definido pelo anunciante | Obrigatório | `string` |
| `event_time` | Hora do evento, arredondada para a hora mais próxima | Obrigatório | `data e hora` |
| `ativado` | Definido pelo anunciante | Opcional | `string` |
| `app_version` | Definido pelo anunciante | Opcional | `string` |
| `id_anúncio` | ID do anúncio | Opcional | `string` |
| `ad_name` | Nome do anúncio | Opcional | `string` |
| `ad_type` | Exemplo: banner, footer | Opcional | `string` |
| `id_conjunto_de_anúncios` | ID do conjunto de anúncios, identifica um grupo que contém um ou mais anúncios | Opcional | `string` |
| `adset_name` | Nome do conjunto de anúncios, identifica um grupo que contém um ou mais anúncios | Opcional | `string` |
| `Canal` | Fonte do canal de mídia Fonte do canal de mídia Fonte do canal de mídia Exemplo: YouTube para Google, Instagram para Meta Ads | Opcional | `string` |
| `platforma` | Plataforma do dispositivo: iOS, Android ou Windows Mobile | Opcional | `string` |

</Accordion>

Para mais informações sobre como preparar fontes e enviá-las para a sua nuvem, consulte a seção [Criar e conectar fontes de dados personalizadas](#criar-e-conectar-fontes-de-dados-personalizadas).

<div id="prepare-campaign-mapping-source" />

## Prepare a fonte de mapeamento da campanha

A fonte dos dados de mapeamento da campanha é um arquivo fonte de dados personalizado, que utiliza o esquema descrito na tabela abaixo.

<div id="note-2" />

> 📘 **Nota**
>
> Recomendamos o uso de um único arquivo de mapeamento para todas as colaborações, pois é mais fácil de manter e atualizar.

<div id="the-campaign-mapping-scheme" />

<Accordion title="Esquema de mapeamento da campanha">

Use o esquema abaixo para criar a fonte de mapeamento da campanha.

| **Tipo de campo** | **É obrigatório?** | **Valor esperado** | **Descrição** |
| --- | --- | --- | --- |
| collaborator\_name | Sim | string | O nome do colaborador com quem você trabalha. |
| collaborator\_id | Sim | string | Um identificador exclusivo para o colaborador. |
| id\_da\_campanha | Sim | string | O identificador exclusivo da campanha. |
| conversion\_targets | Sim | string array | Um parâmetro que espera uma lista separada por vírgulas de SKUs alvo da campanha, por exemplo, sku1, sku2, etc. |
| campaign\_name | Sem | string | O nome da campanha. |

</Accordion>

Para mais informações sobre como preparar arquivos fonte e enviá-los para a sua nuvem, consulte a seção [Criar e conectar fontes de dados personalizadas](#criar-e-conectar-fontes-de-dados-personalizadas).

<div id="attribution-job-ingestion-flow" />

## Fluxo de ingestão de jobs de atribuição

Cada job de atribuição é dedicado a um único dia e é executado após o fim do dia. No início desse processo, o job ingere as conversões, os engajamentos e os dados de mapeamento de campanhas relevantes da nuvem ou de eventos in-app.

<div id="campaign-mapping-source-ingestion" />

<Accordion title="Ingestão de fontes de mapeamento de campanhas">

Antes de cada execução de atribuição, o DCP carrega registros de mapeamento de campanhas a partir das fontes personalizadas. É possível escolher entre dois modos de carregamento desses registros:

* **Última estratégia**: o DCP usa os registros mais recentes com base na data de envio do registro.

  Por exemplo, se a fonte contiver registros com datas de envio de 18 de janeiro, 17 de janeiro ou 29 de dezembro, o sistema selecionará os registros com a data de 18 de janeiro.
* **Estratégia diária**: o DCP só aceita registos cuja data de envio corresponde ao dia da execução da atribuição. Por exemplo, se a execução ocorrer à meia-noite de 19 de janeiro, o sistema só selecionará registros de campanha com a data de envio de 19 de janeiro.

</Accordion>

<div id="conversion-source-ingestion" />

<Accordion title="Ingestão de fontes de conversão">

No final de cada dia, o DCP executa o trabalho de atribuição para esse dia **apenas se puder acessar a pasta dedicada a esse dia e aos registros de conversão nela contidos**. No entanto, você pode enviar a pasta para um determinado dia em uma data posterior. Por exemplo, você pode enviar a pasta de 17 de janeiro em 22 de janeiro.

* No final de cada dia, o DCP executa o trabalho de atribuição para esse dia. O job **só** será executado **se o DCP conseguir encontrar a pasta para esse dia**. O nome da pasta é idêntico ao nome do dia.
* A pasta diária pode incluir registros de eventos que datam de 30 dias a partir do dia da pasta. Por exemplo, na pasta Jan 17, o trabalho processa registros de 18 de dezembro a 17 de janeiro.
* Se você não enviar a pasta para um determinado dia, você tem 30 dias para enviá-la. Por exemplo, se você não enviou a pasta de 17 de janeiro, pode enviá-la até 17 de fevereiro. No entanto, recomendamos que ela seja enviada o mais próximo possível da data da pasta.
* Se o DCP não encontrar a pasta do dia atual, continuará a procurar a pasta de 10 em 10 minutos durante os 7 dias seguintes.

</Accordion>

<div id="engagement-source-ingestion" />

<Accordion title="Ingestão de fontes de engajamento">

Para cada registro de conversão, o DCP procura os eventos de engajamento que a desencadearam.

* Os registos dos engajamentos estão incluídos em pastas datadas. No entanto, não é necessário enviar uma pasta de engajamento para cada dia. Por exemplo, você pode enviar uma pasta de 13 e 15 de janeiro sem enviar a pasta de 14 de janeiro. Nesse exemplo, os registros de 14 de janeiro serão retirados da pasta 15 de janeiro.
* **O job de atribuição para uma determinada pasta de conversão será iniciado apenas se existir uma pasta de engajamento com a mesma data que a pasta de conversão ou uma data posterior.** Por exemplo, o job de atribuição para a pasta de **conversão** de 17 de janeiro será iniciado somente se a pasta de engajamento de 17 de janeiro ou as pastas com datas posteriores, como 18 de janeiro, existirem.
* O job de atribuição recolhe todos os eventos de engajamento que se enquadram na janela de lookback do engajamento.

</Accordion>

<div id="inapp-data-ingestion" />

<Accordion title="Ingestão de dados in-app">

Os dados de conversão e engajamento podem ser obtidos de eventos in-app, fontes personalizadas ou uma combinação de ambos. O DCP permite que você escolha se pretende usar um único modo ou misturá-los, permitindo que as conversões sejam obtidas de eventos in-app enquanto os engajamentos são obtidos a partir de arquivos personalizados, ou vice-versa.

Ao configurar eventos in-app para conversões, engajamentos ou ambos, é necessário especificar o App ID e o nome do evento de conversão ou engajamento. No final do dia, o job de atribuição seleciona todos os eventos com o nome especificado e o App ID que tem a mesma data de evento que o dia da conversão.

</Accordion>

<div id="create-and-connect-custom-data-sources" />

## Criar e conectar fontes de dados personalizadas

Para conectar os dados através de fontes personalizadas, o cliente terá de seguir as instruções nos seguintes artigos da base de dados de conhecimento do DCP:

* <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">Plataforma de colaboração de dados - Configure a sua nuvem</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-add-connections">Plataforma de colaboração de dados - Adicionar conexões</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources">Plataforma de colaboração de dados - Criar e gerenciar fontes</Anchor>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01JJKFW5Z2D7Y1MM5A7YR0TY0T=vis%C3%A3o-geral prepare-inapp-events-for-conversions-and-engagements=prepare-a-lista-de-eventos-in-app h_01JJKFW5Z22DG4CKFMXPGR3BW0=prepare-a-lista-de-eventos-in-app h_01JJKFW5Z2NP9187GYHS0YEXED=nota h_01JJKFW5Z2AX7SHHZ23P0KDQJY=prepare-conversion-inapp-events h_01JJKFW5Z2YD0B151VSR3TG6SP=prepare-engagement-inapp-events h_01JJKFW5Z3QES9BAZX7KNSPCM8=create-inapp-events prepare-custom-source-files-for-engagements-and-conversions=preparar-arquivos-fonte-personalizados h_01JJKFW5Z3QX33NK3XP452AAFB=preparar-arquivos-fonte-personalizados h_01JK3QFQCK30A7SSPWXSH3VP0D=the-conversion-source-scheme media-partners=parceiros-de-m%C3%ADdia-selecionados h_01K399C7NME67HQGJKRG1A5JB2=parceiros-de-m%C3%ADdia-selecionados background-colors=cores-de-fundo h_01K399DC8ZAEA86DD4W0181EM6=cores-de-fundo h_01JK3QFQCKD1TV5G4N0KP85AWS=the-engagement-source-scheme h_01JK3QFQCK6C16SCW8EYQNS47F=nota-1 prepare-campaign-mapping-source=prepare-a-fonte-de-mapeamento-da-campanha h_01JJKFW5Z3QR107P3M111P4STG=prepare-a-fonte-de-mapeamento-da-campanha h_01JJKFW5Z3ZSYET4HMWD7TWSD8=nota-2 h_01JJKFW5Z3Q6F3DP0EMTNQRD8R=the-campaign-mapping-scheme prepare-data-for-attribution-job-ingestion=fluxo-de-ingest%C3%A3o-de-jobs-de-atribui%C3%A7%C3%A3o h_01JJKFW5Z38W581F4CBW3T4CPZ=fluxo-de-ingest%C3%A3o-de-jobs-de-atribui%C3%A7%C3%A3o h_01JK5R1VPJ0WAF3WX4R1ECE0R7=campaign-mapping-source-ingestion h_01JK5R1VPJT41RF2EN8806ZY5C=conversion-source-ingestion h_01JK5R1VPJN8KTFTN21DA3619Y=engagement-source-ingestion h_01JK5R1VPJV6F5Y5JB3Q45R89B=inapp-data-ingestion create-and-connect-custom-data-sources=criar-e-conectar-fontes-de-dados-personalizadas h_01JJKFW5Z3NKB0MB7GN2FC87H5=criar-e-conectar-fontes-de-dados-personalizadas" />

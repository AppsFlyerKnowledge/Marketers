---
title: Links de atribuição direta das plataforma de CTV, PC e console
metadata:
  keywords:
    - Advertiser
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2023-05-10T10:21:14Z'
  edited_at: '2026-10-20T03:44:25Z'
  id: 15199908310801
  locale: pt
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/pt/articles/15199908310801
---
> **Resumo:**  saiba mais sobre a estrutura e os parâmetros de links de atribuição da AppsFlyer para plataformas de CTV, PC e console. **Atenção:** para os aplicativos de Android e iOS, incluindo jogos de Android para PC, use as <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">instruções do link de atribuição para dispositivos móveis</Anchor>.

## Visão geral

Os links de atribuição direta para plataformas de CTV, PC e console permitem que os anunciantes redirecionem os usuários e coletem dados após os cliques. Os links de atribuição direta são links da AppsFlyer compatíveis com o redirecionamento e a atribuição **para um único aplicativo de destino em uma única plataforma por vez**. O destino de redirecionamento é o valor do parâmetro af\_r incluído no link.

**Atenção:** para os aplicativos de Android e iOS, incluindo jogos de Android para PC, use as <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">instruções do link de atribuição para dispositivos mobile</Anchor>.

Os links de atribuição podem ser criados diretamente por você e colocados atrás de anúncios. Para criar esses links, siga as instruções neste artigo.

Como alternativa, os links podem ser criados via S2S usando a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_click-app-platform-app-id">Engagements API.</Anchor> Isso envolve um pouco de programação. **Atenção:** os links criados por meio de S2S também podem coletar dados de impressão.

### Link de atribuição

| Propriedade | Valores |
| --- | --- |
| URL base | engagements.appsflyer.com/v1.0/c2s/click/app/ |
| Parâmetros de caminho obrigatórios | <ul><li>platform<br />Exemplo: steam</li><li>app\_id<br />Exemplo: 123456</li></ul> |
| Parâmetros de consulta obrigatórios | <ul><li>media\_source</li><li>af\_campaign\_id</li></ul> |
| Outros parâmetros | [Ver todos os parâmetros](/docs/ctv-pc-and-console-platform-direct-attribution-links#parâmetros) |
| Estrutura da URL | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |
| URL de exemplo | `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=aloha&af_campaign_id=1234&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello` |

### Parâmetros

| Parâmetro | Nome de exibição na exportação de Dados Brutos e na API de Pull | Descrição | Tipo de campo |
| --- | --- | --- | --- |
| platforma | Plataforma | <ul><li>Parâmetro de caminho que especificou a plataforma do aplicativo.</li><li>Valores possíveis:<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>steam</li><li>quest</li><li>battlenet</li><li>epic</li><li>switch</li><li>xbox</li><li>nativepc</li></ul></li></ul> | Sequência de caracteres |
| ativado | ID da aplicação | <ul><li>Parâmetro de caminho que especifica a ID do aplicativo para o qual você está postando.</li><li>Exemplo: `ap123456`</li><li>Não adicione um prefixo de plataforma ao valor do App ID. Por exemplo, se o app ID for `ap123456` e a plataforma for `platformX`, não use `platformX_ap123456` como o valor de `app_id`.</li></ul> | Sequência de caracteres |
| media\_source | Fonte de mídia | Esse é o identificador exclusivo do parceiro, conforme definido na plataforma da AppsFlyer.  <br />Os seguintes caracteres não são permitidos: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %. | Sequência de caracteres |
| af\_campaign | Campanha | Nome da campanha | Sequência de caracteres |
| af\_campaign\_id | ID da campanha | ID da campanha | Sequência de caracteres |
| af\_request\_id | N/D | Um identificador que identifica exclusivamente uma solicitação de um parceiro. | Sequência de caracteres |
| af\_adset | Conjunto de anúncios | Nome do conjunto de anúncios | Sequência de caracteres |
| af\_adset\_id | ID do conjunto de anúncios | ID do conjunto de anúncios | Sequência de caracteres |
| af\_ad | Anúncio | Nome do anúncio | Sequência de caracteres |
| af\_ad\_id | ID do anúncio | ID do anúncio | Sequência de caracteres |
| af\_campaign\_type | Tipo de campanha | Ou:<ul><li>user\_acquisition</li><li>retargeting</li></ul> | Sequência de caracteres |
| af\_prt | Parceiro | <ul><li>Nome da conta da agência que permite atribuir instalações à agência</li><li>Atenção não use esse parâmetro antes de garantir que as **Permissões de Agência** estejam habilitadas</li></ul> | Sequência de caracteres |
| af\_siteid | ID do site | <span id="query-getImpressionAppPlatformApp_id_af_siteid__description"></span>ID exclusivo que identifica o publisher que exibe o anúncio. | Sequência de caracteres |
| af\_sub\_siteid | ID do subsite | <span id="query-getImpressionAppPlatformApp_id_af_sub_siteid__description"></span>ID da sub-rede de anúncios/publisher. | Sequência de caracteres |
| af\_click\_id | N/D | <span id="query-getImpressionAppPlatformApp_id_af_click_id__description"></span><span id="query-getImpressionAppPlatformApp_id_af_ad_placement__description"></span>Identificador exclusivo de transação da rede de anúncios | Sequência de caracteres |
| af\_lookback\_window | N/D | <ul><li>Número configurável de dias/horas para o período de atribuição da janela de lookback. Valores de parâmetros disponíveis:<ul><li>Cliques: 1d-7d (dias).</li><li>Impressões: 1d-7d (dias) ou 1h-23h (horas).</li></ul></li><li>Validação: máx. de 3 caracteres, usando o esquema acima.</li><li>Validação: 3 caracteres no máximo, usando o esquema acima.</li></ul> | Sequência de caracteres |
| af\_ad\_placement | N/D | Identificador exclusivo de transação da rede de anúncios | Sequência de caracteres |
| af\_ad\_type | Tipo de anúncio | <ul><li>Tipo de anúncio Tipo de anúncio Use a seguinte convenção de nomenclatura:<ul><li>**text:** uma unidade de anúncios contendo apenas texto, por exemplo, um resultado de pesquisa</li><li>**banner:** um formato básico que aparece na parte superior ou inferior da tela do dispositivo</li><li>**interstitial:** um anúncio de página inteira que aparece durante pausas na experiência vigente</li><li>**video:** um vídeo padrão, ou seja, não recompensado</li><li>**rewarded\_video:** uma unidade de anúncio que oferece recompensas no aplicativo em troca de assistir a um vídeo</li><li>**playable:** uma unidade de anúncio que contém uma visualização interativa da experiência do aplicativo</li><li>**audio:** um anúncio em áudio</li></ul></li><li>Diferenciação de maiúsculas e minúsculas.</li></ul> | Sequência de caracteres |
| af\_canal | Canal | <span id="query-getImpressionAppPlatformApp_id_af_channel__description"></span>O canal de origem dos meios de comunicação através do qual os anúncios são distribuídos, por exemplo, UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | Sequência de caracteres |
| af\_model | Modelo do dispositivo | Modelo do dispositivo | String 64 |
| af\_os\_version | N/D | <ul><li>Versão do sistema operacional do dispositivo</li><li>Apenas dígitos e pontos</li><li>Exemplo: 8.1.0</li></ul> | Sequência de caracteres |
| af\_device\_id\_type | N/D | <span id="query-getImpressionAppPlatformApp_id_af_device_id_type__description"></span>Tipo de identificador de dispositivo. Ou:<ul><li>VIDA</li><li>TIFA</li><li>rida</li><li>lgudid</li><li>fire</li><li>advertising\_id</li><li>fire</li><li>personalizado</li></ul> | Sequência de caracteres |
| af\_device\_id\_value | N/D | <span id="query-getImpressionAppPlatformApp_id_af_device_id_value__description"></span>Tipo de identificador de dispositivo | Sequência de caracteres |
| af\_r | N/D | <ul><li>Contém o link para a loja de aplicativos ou página de destino correta</li><li>Tudo dentro do parâmetro af\_r precisa ser codificado. Isso inclui quaisquer valores de parâmetro UTM, se anexados.</li></ul>**Atenção:** certifique-se de que o domínio da URL para af\_r esteja incluído na sua <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">redirect allowlist</Anchor>. | Sequência de caracteres |

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Atribuição de agência | <ul><li>CTV-PC-Console para fluxo mobile - a atribuição de agência é suportada.</li><li>Fluxo de dispositivos mobile para CTV-PC-Console - a atribuição de agência não é compatível.</li></ul> |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H7Z1003GTTMRY072BXWDFNP0=vis%C3%A3o-geral attribution-link=link-de-atribui%C3%A7%C3%A3o 01H7Z1003G0WYBCK3530064WM1=link-de-atribui%C3%A7%C3%A3o attribution-link-parameters=par%C3%A2metros 01H7Z1003GNC551PDCKKFQMPVN=par%C3%A2metros traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HVED5DJPFR5XCWYDSYCHMCR6=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />

---
title: Migrar do PBA para a mensuração da performance na web
metadata:
  keywords:
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-07-26T11:53:06Z'
  edited_at: '2026-09-08T12:22:09Z'
  id: 49156441281425
  locale: pt
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/pt/articles/49156441281425
---
> **At a glance:** People-Based Attribution (PBA) está sendo substituída por Mensuração de performance web, a solução de mensuração web aprimorada da AppsFlyer. Este artigo explica o que está mudando, as etapas da migração e o mapeamento completo dos campos para seus relatórios e integrações server-side.

## Por que estamos aprimorando sua mensuração web

A mensuração web importa mais do que nunca. É no site que muitos dos seus usuários convertem e onde começa o caminho até o seu app mobile. Não é apenas uma landing page; é um funil completo de aquisição com fluxos de quiz, onboarding personalizado, paywalls e lojas web que muitas vezes conquistam usuários com maior intenção a um custo de aquisição menor.

A AppsFlyer está levando a mensuração web ao mesmo padrão do mobile. People-Based Attribution (PBA), o produto web legado, está sendo substituída por Mensuração de performance web, criada com base no mecanismo principal de atribuição da AppsFlyer e em um modelo de dados unificado. A Mensuração de performance web iguala tudo o que o PBA faz hoje e ainda adiciona:

* **Uma única fonte de verdade**, mensuração na web e mensuração de app mobile em um só lugar, com custos agregados, postbacks de otimização e otimização de criativos.
* **Melhores decisões de orçamento**, atribuição flexível que corresponde à lógica do seu negócio, para que você invista mais nas campanhas que realmente funcionam.
* **ROAS aprimorado**, postbacks de otimização enriquecidos para suas ad networks e uma configuração server-side completa que mensura mais conversões, para que as networks possam otimizar usando sinais melhores.
* **ROI real entre plataformas**, mensure toda a jornada do usuário na web, no app e em qualquer plataforma.
* **Relatórios simples e unificados**, um dashboard e um conjunto de relatórios de dados para cada plataforma, atualizados a cada hora.

> 📘 **Note**
>
> Você não precisa substituir seu SDK web. A Mensuração de performance web usa o mesmo SDK, sem alterações de código no seu site. O esforço envolvido no restante da mudança varia, dependendo de como você recebe seus dados atualmente: pelo dashboard, pelo Data Locker ou pela API Server-to-server (S2S).

## Comparando o PBA e a Mensuração de performance web

Esta seção compara o PBA e a Mensuração de performance web de duas formas: recursos gerais e resolução da fonte de tráfego.

### Web Performance Measurement vs. PBA

A tabela abaixo compara os recursos do PBA e da Mensuração de performance web em dados, relatórios e atribuição.

<table><tbody><tr><td>Recursos</td><td>A descrição</td><td>PBA</td><td>Mensuração de performance web</td></tr><tr><td colspan="4"><strong>agregados</strong></td></tr><tr><td>Relevância dos dados</td><td>Com que rapidez os dados ficam disponíveis para reportar</td><td> <span>✗</span> Diariamente</td><td> <span>✓</span> Relatórios por hora, com aproximadamente 2 horas de atualização dos dados</td></tr><tr><td>Modelo de dados</td><td>Alinhamento de esquema com dados de atribuição mobile</td><td> <span>✗</span> Diferente do mobile</td><td> <span>✓</span> Alinhado ao mobile, fácil de unir e analisar</td></tr><tr><td colspan="4"><strong>Relatórios</strong></td></tr><tr><td>Dashboard de atividades</td><td>Dashboard com base no horário do evento</td><td> <span>✓</span> Com suporte</td><td> <span>✓</span> Com suporte</td></tr><tr><td>Painel de coorte</td><td>Analise a performance por coorte de aquisição ao longo do tempo</td><td> <span>✗</span> Sem suporte</td><td> <span>✓</span> Com suporte</td></tr><tr><td>Dados brutos do Data Locker</td><td>Acesso aos dados brutos de atribuição via exportação do Data Locker</td><td> <span>✓</span> Com suporte</td><td> <span>✓</span> Com suporte</td></tr><tr><td>Granularidade no nível do anúncio</td><td>Detalhamento do relatório da campanha até o nível do anúncio</td><td> <span>✗</span> Somente no dashboard, não nos dados brutos</td><td> <span>✓</span> Granularidade completa da campanha no dashboard e nos dados brutos</td></tr><tr><td>LTV cross-platform</td><td>Unifique as jornadas de usuários na web e no mobile em um único LTV</td><td> <span>✗</span> Sem suporte</td><td> <span>✓</span> Com suporte</td></tr><tr><td colspan="4"><strong>Custo e sinais</strong></td></tr><tr><td>Custo web</td><td>Ingira e gere relatórios sobre gasto com anúncios para campanhas web</td><td> <span>✗</span> Sem suporte</td><td> <span>✓</span> Com suporte</td></tr><tr><td>Postbacks de otimização</td><td>Envie sinais de otimização de volta para as ad networks</td><td> <span>✗</span> Sem suporte</td><td> <span>✓</span> Com suporte</td></tr><tr><td colspan="4"><strong>Implementação</strong></td></tr><tr><td>SDK web (pixel)</td><td>SDK do lado do cliente para mensurar visitas e eventos web</td><td> <span>✓</span> Com suporte</td><td> <span>✓</span> Mesmo SDK, sem necessidade de alterações no código</td></tr><tr><td>Suporte S2S</td><td>Mensuração completa do lado do servidor para visitas e eventos</td><td> <span>✗</span> Somente eventos</td><td> <span>✓</span> Eventos e visitas. Suporta uma implementação completa do lado do servidor.</td></tr><tr><td colspan="4"><strong>Motor de atribuição</strong></td></tr><tr><td>Janelas de atribuição</td><td>Janelas configuráveis de lookback, atribuição, reengajamento e inatividade</td><td> <span>✗</span> Somente janela de lookback de clique</td><td> <span>✓</span> 5 janelas configuráveis (controle total)</td></tr><tr><td>Evento de UA personalizado</td><td>Define qual evento conta como um evento de aquisição de usuários (UA) além da primeira visita</td><td> <span>✗</span> Somente a primeira visita</td><td> <span>✓</span> Qualquer evento personalizado (por exemplo, cadastro, compra)</td></tr><tr><td>UA vs. retargeting</td><td>Crédito separado para nova aquisição vs. reengajamento</td><td> <span>✗</span> Sem conceito de UA, eventos atribuídos ao último toque</td><td> <span>✓</span> Visualizações dedicadas de UA e retargeting com crédito de atribuição dupla</td></tr></tbody></table>

### Resolução da fonte de tráfego, PBA vs. Mensuração de performance web

Se os valores de canal de mídia, canal ou campanha forem diferentes do que o PBA reportou, aqui está o motivo. Ambos usam a mesma abordagem subjacente: resolvem o canal de mídia a partir de parâmetros de URL e do referenciador na visita web, percorrendo uma lista de prioridades até que a primeira correspondência prevaleça. Mas várias regras mudaram, e essas mudanças alteram os valores que você vê nos relatórios, com base nas <Anchor target="_blank" href="/marketers/pt/docs/pba-media-source-attribution-rules">regras de atribuição de canal de mídia do PBA</Anchor> e em <Anchor target="_blank" href="/marketers/pt/docs/about-traffic-source-resolution">Sobre a resolução da fonte de tráfego</Anchor>.

<Accordion title="Valores de canal de mídia renomeados">

| Trigger | Valor do PBA | Novo valor |
| --- | --- | --- |
| Google display/video (utm\_source=Google + utm\_medium= cpm / display/banner/video/listing) | `doubleclick_int` | `dv360_int` |
| Twitter via UTM (twitter + cpc) | AppsFlyer | Twitter |

A mensuração de performance da web também remapeia mais valores de PID para nomes de exibição, por exemplo, `iossearchads_int` para Apple Search Ads, `metweb_int` para Facebook Ads, `twitterweb_int` para Twitter, `tiktokweb_int` para `tiktokglobal_int`, `snapweb_int` para `snapchat_int`. Relatórios criados com base nos valores brutos antigos precisam considerar os novos.

</Accordion>

<Accordion title="Cobertura de IDs de clique ampliada e dclid removido">

O PBA resolvia três IDs de clique: `gclid` para `googleadwords_int`, `dclid` para `doubleclick_int` e `msclkid` para `bingsearch_int`.

A web performance mensuração resolve muitos outros: `gclid`/`wbraid`/`gbraid` para `googleadwords_int`, `msclkid` para `bingsearch_int`, `twclid` para Twitter, `vmcid` para `yahoogemini_int`, `sccid` para `snapchat_int`, `li_fat_id` para `linkedin_int`, `ttclid` para `tiktokglobal_int`, `tbclid` para `taboola_int`, `ob_click_id`/`dicbo` para `outbrain_int`, `yclid` para `yandex_int`, `rdt_cid` para `reddit_int`.

> 🚧 **Important**
>
> Duas mudanças de comportamento: dclid não é mais usado sozinho para resolução (o PBA o resolvia como doubleclick\_int), e fbclid explicitamente não é usado.

</Accordion>

<Accordion title="Regras personalizadas de UTM ampliadas">

O mapeamento personalizado de `utm_source` + `utm_medium` é mais amplo na web performance mensuração: inclui mais sinônimos de mídia (paid, paid\_search, paid-search etc.) e adicionou cobertura para TikTok, Snapchat e Pinterest além das regras restritas de mídia única do PBA. Quando nenhuma regra personalizada corresponde, ambos recorrem ao valor bruto de `utm_source`.

</Accordion>

<Accordion title="Canal">

Os **valores** de canal também mudam de formato, de Direct / Organic search / Social media / Email / Ad / Referral / Other do PBA para os novos DIRECT / ORGANIC\_SEARCH / SOCIAL\_MEDIA / EMAIL / AD / REFERRAL / OTHER. Os filtros e agrupamentos baseados nos rótulos antigos precisam ser atualizados.

</Accordion>

## Migrar para a mensuração de performance web

A migração tem uma etapa obrigatória para todos. Depois disso, execute as etapas aplicáveis à sua configuração de PBA.

> 📘 **Note**
>
> **Espere diferenças nos números (todos)**
>
> Os números do PBA não corresponderão exatamente aos que você terá após a migração. A lógica de atribuição na mensuração de performance web é mais avançada e flexível. O PBA aplicava suas próprias regras de atribuição de canais de mídia; a mensuração de performance web usa uma resolução aprimorada de fonte de tráfego. Veja "Resolução da fonte de tráfego, PBA vs. mensuração de performance web" abaixo para saber quais valores esperar. A lógica de gravação de sessão em si não mudou; a sessão continua em execução por 30 minutos de atividade, o padrão de mercado.

### 1. Criar um aplicativo web (obrigatório para todos)

1. <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#web">Crie o novo aplicativo web</Anchor>, selecionando sua Dev Key web existente no campo **ID do SDK web**. Isso mantém o código atual do seu site funcionando como está, sem alterações no código.
2. <Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings">Configure as definições de atribuição</Anchor> no novo aplicativo.

### 3. Se você envia eventos pela API S2S

Migre para a nova API S2S:

1. Consulte [a migração de PBA Web-S2S para a nova API S2S](#migração-de-pba-web-s2s-para-a-nova-api-s2s) para ver o que muda em relação à sua integração S2S atual do PBA, endpoints, autenticação e campos de payload.
2. Configure a <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-s2s-api-for-web-performance-measurement">nova API S2S</Anchor> para a mensuração de performance web.
3. Atualize sua integração do lado do servidor para enviar aos novos endpoints.

### 3. Se você consome os relatórios de dados brutos do PBA

Migre para os novos relatórios do Data Locker. O relatório de eventos do usuário final substitui os <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports">relatórios de visitas ao site e eventos do site do PBA</Anchor>.

1. Confirme que você tem o Data Locker. Se não tiver, você precisará adicioná-lo à sua conta ou comprá-lo.
2. Consulte o [mapeamento de campos de dados brutos](#mapeamento-de-campos-de-dados-brutos) para ver o mapeamento completo no nível de campo, incluindo os campos renomeados, redefinidos ou descontinuados.
3. Habilite o novo relatório usando <Anchor target="_blank" href="/marketers/pt/docs/export-web-performance-measurement-report-data-from-data-locker">Exportar dados de relatório de atribuição web da AppsFlyer do Data Locker</Anchor>.
4. Aponte seu BI/ETL para o novo local e os novos campos do relatório. Isso se aplica independentemente de seus eventos chegarem via SDK ou S2S; ambos vão para o mesmo relatório de dados brutos.

### 4. Se você usa o PBA Brand Bundle para reportar multiplataforma

1. <Anchor target="_blank" href="/marketers/pt/docs/product-line-group-apps-for-cross-platform-attribution">Crie uma linha de produtos</Anchor>.
2. Agrupe seu aplicativo web com seus outros aplicativos nessa linha de produtos para desbloquear <Anchor target="_blank" href="/marketers/pt/docs/beta-user-based-cross-platform-attribution">relatórios de LTV do usuário multiplataforma</Anchor>.

## Capacidades que serão descontinuadas

| Recursos | O que muda | Atenção |
| --- | --- | --- |
| Caminho de conversão | Já está obsoleto. | Sequência de caracteres |
| Instalações assistidas pela web (crédito para uma campanha web que ajudou a impulsionar uma instalação mobile posterior) | Não há uma visualização dedicada de "instalações assistidas pela web". | As jornadas Web-to-app são mensuradas com Smart Script e Smart Banner. O relatório entre plataformas oferece uma análise semelhante, embora não idêntica. Assim como o PBA, ele se baseia no Identificador de Usuário do Cliente (CUID):<ul><li>Campanhas web que antes auxiliavam uma instalação reportada como orgânica agora aparecem como aquisição de usuários não orgânica. Não se trata de assistências; a campanha web é a fonte de aquisição.</li><li>Campanhas web que assistiram a uma instalação não orgânica: a campanha web serve como aquisição de usuários, e a instalação mobile serve como retargeting multiplataforma.</li></ul> |
| Recálculo retroativo | Sem recálculo retroativo além do atraso padrão de 30 minutos. | A atribuição é finalizada após um atraso de 30 minutos, dando aos usuários tempo para se identificarem durante essa janela. |
| Campos de dados brutos | Os campos relacionados a mobile foram descontinuados para a web. Alguns campos são renomeados, e alguns valores mudam. | Consulte [Mapeamento de campos de dados brutos](#mapeamento-de-campos-de-dados-brutos) para ver o mapeamento completo dos campos. |
| Eventos S2S atrasados | Eventos que chegam mais de 30 minutos após o fim do dia UTC em que ocorreram ainda são aceitos, mas o horário do evento é substituído pelo horário em que a AppsFlyer os recebeu. | Envie eventos em tempo real, de preferência em até 30 minutos após a ocorrência do evento, em vez de agrupá-los em um único upload diário. A atribuição precisa depende do recebimento de eventos próximo ao momento em que acontecem. Isso alinha a web ao comportamento mobile existente. |

## Mapeamento de campos de dados brutos

Se você já consome os relatórios de dados brutos de visitas ao site e eventos do site do PBA, veja o que muda. O relatório em si passa para o Data Locker, e este é o mapeamento completo, campo a campo, para o novo relatório de eventos do usuário final, com base nos <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports">Relatórios de dados brutos do PBA</Anchor>.

> 📘 **Note**
>
> Os dados brutos de qualquer plataforma e o reportar multiplataforma estão disponíveis apenas por meio do Data Locker. Consulte a Etapa 3 ou a Etapa 4 acima se você ainda não tiver o Data Locker.

* **Inalterado**, mesmo nome de campo e mesmos dados.
* **Renomeado**, mesmos dados, novo nome de coluna.
* **Redefinido**, nome igual ou semelhante, mas os dados ou o formato do valor mudam (requer cuidado antes da reutilização).
* **Descontinuado**, sem equivalente no novo relatório.

| String vazia | A descrição | Estado | Novo campo/observação |
| --- | --- | --- | --- |
| `advertising_id` | ID de publicidade (GAID) | Descontinuado | ID de publicidade do dispositivo mobile, vinculado entre plataformas no PBA. Os relatórios de LTV entre plataformas e de jornada do usuário são baseados em CUID e não usam esse campo. |
| `af_web_id` | ID de cookie enviado do SDK da web | Renomeado | `appsflyer_id_value`, mesmo cookie web. |
| `amazon_aid` | ID de publicidade da Amazon Fire TV | Descontinuado | Device ID mobile/do dispositivo, não relevante para web. |
| `android_id` | ID do dispositivo Android | Descontinuado | Device ID mobile/do dispositivo, não relevante para web. |
| `ativado` | ID do aplicativo mais recente instalado | Idêntico a [af\_siteid](#attribution::e9b53459). | Campo multiplataforma mobile. O identificador do aplicativo web no novo relatório é `unified_app_id` ("website-`{domain}`"), um conceito diferente. |
| `ativado` | Nome do aplicativo mais recente | Inalterado | `app_name`. |
| `app_version` | Versão mais recente do aplicativo | Descontinuado | Campo mobile multiplataforma, não relevante para web. |
| `appsflyer_id` | ID da AppsFlyer (instalação) | Descontinuado | ID de instalação mobile. O novo `appsflyer_id_value` é o cookie web (`af_web_id`), um identificador distinto. |
| `attributed_touch_time` | Carimbo de data/hora da visita web (atribuída) | Renomeado | `event_time__attribution`, o horário do toque (engajamento) atribuído. |
| `tipo_de_toque_atribuído` | Tipo de touchpoint, sempre "visita web" | Descontinuado | Valor constante em PBA. Visita vs. evento agora fica em `end_user_event_type` (SESSION / IN\_APP). |
| `bundle_id` | ID do bundle PBA | Descontinuado | Substituído pelo agrupamento Linha de Produto (web + aplicativo mobile) no relatório multiplataforma. |
| `Twitter` | Atribuído à visita ao site | Renomeado | `campaign_name`. |
| `id_da_campanha` | Atribuído à visita ao site | Inalterado | `campaign_id`. |
| `cidade` | Resolvido usando o endereço IP | Inalterado | `city`. |
| `código_país` | Resolvido usando o endereço IP | Inalterado | `country_code`. |
| `customer_user_  <br />id` | Identificador de Usuário do Cliente (CUID) | Inalterado | `customer_user_id`. |
| `device_type` | O tipo de dispositivo | Renomeado | `device_category`, os valores diferem ("Desktop" vs. "MOBILE\_PHONE" / "TV"). |
| `dma` | Resolvido usando o endereço IP | Inalterado | `dma`. |
| `nome_do_evento` | Visitas: sempre "website visit". Eventos: nome do evento enviado | Redefinido | Vazio nas visitas (o PBA registrava "website visit"). Inalterado para eventos. |
| `event_revenue` | Valor da receita do evento na moeda de compra | Renomeado | `revenue_value_original`. |
| `event_currency` | Código de moeda de 3 dígitos de `event_revenue` | Renomeado | `revenue_currency_original`. |
| `event_revenue_usd` | `event_revenue` convertido para USD | Renomeado | `revenue_usd`. |
| `event_source` | Ou o SDK web ou servidor a servidor | Inalterado | `event_source`. |
| `event_time` | Visitas: horário da visita. Eventos: horário do evento | Inalterado | `event_time`. |
| `event_type` | Evento padrão/evento de conversão/visita ao website | Redefinido | A marcação de evento de conversão não existe mais. Visit vs. event fica em `end_user_event_type` (SESSION / IN\_APP). |
| `event_url` | URL da página web onde ocorreu o evento (igual à URL original nas visitas ao site) | Inalterado | `event_url`, agora também é o principal local para ler os parâmetros de consulta da URL (UTMs etc.). |
| `event_value` | Eventos: detalhes do evento como JSON. Visitas: nulo | Inalterado | `event_value`. |
| `idfa` | Identificador do anúncio | Descontinuado | ID de mobile/dispositivo, não relevante para web. |
| `idfv` | Identificador do anúncio | Descontinuado | ID de mobile/dispositivo, não relevante para web. |
| `imei` | Identificador do dispositivo | Descontinuado | ID de mobile/dispositivo, não relevante para web. |
| `install_time` | Horário de instalação mais recente do aplicativo | Descontinuado | Campo mobile multiplataforma. O tempo de aquisição de usuários na web (conversão) é `event_time__conversion`, um conceito separado. |
| `ip` | Endereço IP do visitante | Renomeado | `ip_address_value`, mesmo valor, mais `ip_address_type` para o método de hashing. |
| `language` | Informado pelo user agent (por exemplo, "English") | Redefinido | `language`, o formato do valor muda para ISO 639-1 e código do país. |
| `media_channel` | Atribuído à visita ao site ("Anúncio") | Descontinuado | Pode ser coberto por `sub_param_1-5`, se necessário. |
| `fonte_de_mídia` | Atribuído à visita ao site | Inalterado | `media_source`. |
| `media_type` | Atribuído à visita ao site ("Pago") | Descontinuado | Vazio para web. Orgânico vs. pago agora vem do booleano `is_organic`. |
| `OAID` | Identificador do anúncio | Descontinuado | ID de mobile/dispositivo, não relevante para web. |
| `original_url` | URL que redirecionou o usuário na visita atribuída | Renomeado | Consolidado em `event_url` (em visitas, `event_url` é igual à URL original). A coluna independente não existe mais. |
| `platforma` | A plataforma ("macOS", "Windows") | Redefinido | A plataforma é sempre "WEBSITE". O sistema operacional foi movido para `os_version` / `user_agent`. |
| `postal_code` | Resolvido usando o endereço IP | Inalterado | `postal_code`. |
| `query_params` | Parâmetros de consulta na URL de redirecionamento, como JSON | Descontinuado | A string de consulta bruta fica em `event_url`. A coluna de JSON analisado não existe mais. |
| `referrer` | Referenciador HTTP da visita ao website atribuída | Renomeado | `http_referrer`. |
| `Região` | Resolvido usando o endereço IP ("NA") | Renomeado | `continent`, código do continente, por exemplo, "NA". |
| `estado` | Resolvido usando o endereço IP | Inalterado | `state`. |

<Accordion title="Prompt pronto para uso de um agente de codificação para migração de ETL do Data Locker">

Para facilitar essa transição, preparamos um prompt pronto para uso para o seu agente de codificação de IA (Claude Code, Cursor ou similar). Dê ao agente acesso ao seu código ETL existente e cole o prompt abaixo; ele contém o mapeamento completo dos campos e todas as diferenças de comportamento. Ele orientará o agente a aprender seu pipeline atual e recriá-lo para o novo relatório.

```
Você está migrando um pipeline de ETL dos relatórios de dados brutos do PBA legado do Data Locker da AppsFlyer (visitas ao site + eventos do site) para o relatório de Data Locker de Mensuração de Performance Web da AppsFlyer (eventos do usuário final). Tudo o que você precisa está neste prompt: as mudanças estruturais, o mapeamento completo campo a campo e as etapas de validação. Não suponha nada além do que está escrito aqui; se algo estiver ambíguo, pergunte-me.

## Etapa 1: Aprenda o pipeline atual

Antes de escrever qualquer código, explore a base de código existente e produza um inventário:
1. Quais relatórios PBA consumimos (visitas ao web, eventos do web ou ambos) e onde eles são ingeridos.
2. Todos os campos PBA que lemos e onde cada um é usado adiante (transformações, junções, dashboards, alertas, exportações).
3. A cadência de carga e as premissas de agendamento (PBA entregue diariamente).
4. Qualquer lógica que separe ou una linhas de visita e linhas de evento.
5. Quaisquer filtros, agrupamentos ou valores codificados com base em valores de campos do PBA (por exemplo, nomes de media_source, rótulos de canal, event_type, valores de plataforma).

Apresente esse inventário para mim e aguarde minha confirmação antes de prosseguir.

## Etapa 2: Faça estas perguntas para mim

1. O novo relatório End User Events já está habilitado no Data Locker (habilitado pela interface do AppsFlyer)? Se não, preciso habilitá-lo primeiro.
2. Qual é o Unified App ID do nosso novo aplicativo web? Formato: "website-{domain}" (por exemplo, website-www.example.com). Se eu não souber, vou obtê-lo no dashboard do AppsFlyer antes de continuarmos.
3. Queremos um período de execução paralela (pipelines antiga e nova lado a lado, comparando as saídas) ou uma migração direta? Recomendo a execução paralela.
4. O novo pipeline também deve consumir o relatório Conversions (instâncias de atribuição únicas, sem linhas duplicadas) ou o relatório End User Events entre plataformas, deduplicado por CUID (nível de usuário em web+mobile)? O escopo padrão é o relatório End User Events no nível da plataforma, o sucessor direto dos relatórios PBA.

## Mudanças estruturais para considerar no design

1. **Um relatório em vez de dois.** O PBA dividia visitas e eventos em dois relatórios. O novo relatório End User Events contém ambos: as visitas são linhas com end_user_event_type = 'SESSION' e os eventos são linhas com end_user_event_type = 'IN_APP'. Somente as linhas IN_APP têm um event_name válido; nas linhas SESSION, event_name fica vazio (o PBA registrava "website visit" ali).
2. **Um schema em todas as plataformas.** O relatório é compartilhado entre website, mobile, CTV e PC. Sempre filtre platform = 'WEBSITE' para isolar os dados web.
3. **Crédito de atribuição duplo, deduplique.** A mesma ação pode aparecer duas vezes: uma linha de crédito primário e uma linha de crédito secundário (fonte de UA original, para LTV na visualização de UA). Por padrão, filtre is_primary_attribution = true para evitar contagem dupla. Remova o filtro apenas para análises dedicadas de visualização de UA vs. visualização de retargeting usando conversion_type.
4. **Por hora em vez de diariamente.** O novo relatório é entregue por hora, com aproximadamente 2 horas de defasagem na atualização dos dados. Reestruture as cargas incrementais em torno de lotes por hora, em vez de uma entrega diária.
5. **Orgânico vs. pago.** O media_type ("Paid") do PBA não existe mais. Use o booleano is_organic; nunca infira orgânico/pago a partir de media_source.
6. **Contagem de usuários.** Conte e una os usuários com COALESCE(customer_user_id, appsflyer_id_value), usando primeiro o ID de usuário do cliente estável e, como fallback, o ID baseado em cookie.
7. **Valores vazios.** Os campos STRING são '', os campos NUMERIC são NULL.

## Mapeamento campo a campo (PBA → Eventos do Usuário Final)

Legenda de status: Inalterado = mesmo nome e mesmos dados. Renomeado = mesmos dados, nova coluna. Redefinido = alterações nos dados ou no formato do valor (trate com cuidado). Obsoleto = sem equivalente.

| Campo do PBA | Status | Novo campo / tratamento |
|---|---|---|
| advertising_id | Obsoleto | Device ID mobile/dispositivo. Os relatórios entre plataformas são baseados em CUID; descarte-o. |
| af_web_id | Renomeado | appsflyer_id_value, mesmo cookie da web. |
| amazon_aid | Obsoleto | ID de dispositivo/mobile, não relevante para web. |
| android_id | Obsoleto | ID de dispositivo/mobile, não relevante para web. |
| app_id | Obsoleto | Campo mobile entre plataformas. O novo identificador do Aplicativo web é unified_app_id ("website-{domain}"), um conceito diferente, não uma renomeação. |
| app_name | Inalterado | app_name. |
| app_version | Obsoleto | Campo mobile entre plataformas. |
| appsflyer_id | Obsoleto | ID de instalação mobile. Observação: o novo appsflyer_id_value é o cookie da web (o af_web_id do PBA), NÃO este campo. |
| attributed_touch_time | Renomeado | event_time__attribution. |
| attributed_touch_type | Obsoleto | Era uma constante. A distinção entre visita vs. evento agora está em end_user_event_type. |
| bundle_id | Obsoleto | Substituído pelo agrupamento de Linha de Produto no relatório entre plataformas. |
| campaign | Renomeado | campaign_name. |
| campaign_id | Inalterado | campaign_id. |
| city | Inalterado | city. |
| country_code | Inalterado | country_code. |
| customer_user_id | Inalterado | customer_user_id. |
| device_type | Renomeado + valores alterados | device_category, valores diferentes (por exemplo, valores no estilo "Desktop" → "MOBILE_PHONE" / "TV"). Atualize qualquer lógica baseada em valores. |
| dma | Inalterado | dma. |
| event_name | Redefinido | Eventos: inalterado. Visitas: agora vazio (o PBA escreveu "website visit"). Use end_user_event_type = 'SESSION' para identificar visitas. |
| event_revenue | Renomeado | revenue_value_original. |
| event_revenue_currency | Renomeado | revenue_currency_original. |
| event_revenue_usd | Renomeado | revenue_usd. |
| event_source | Inalterado | event_source. |
| event_time | Inalterado | event_time. |
| event_type | Redefinido | A marcação de "evento de conversão" não existe mais. A distinção entre visita e evento está em end_user_event_type (SESSION / IN_APP). |
| event_url | Inalterado | event_url, agora também é o principal local de onde os parâmetros de consulta da URL (UTMs etc.) são lidos. |
| event_value | Inalterado | event_value. |
| idfa / idfv / imei / oaid | Descontinuado | IDs mobile/de dispositivo, não relevantes para web. |
| install_time | Descontinuado | Campo mobile. O momento de aquisição do usuário na web é event_time__conversion, um conceito separado. |
| ip | Renomeado | ip_address_value (mais ip_address_type para o método de hashing). |
| language | Redefinido | language, o formato muda para ISO 639-1 + código do país (antes era, por exemplo, "English"). |
| media_channel | Obsoleto | Pode ser coberto por sub_param_1-5, se necessário. |
| media_source | Inalterado | media_source (mas veja abaixo as renomeações de valores). |
| media_type | Obsoleto | Use o booleano is_organic em vez disso. |
| original_url | Renomeado | Consolidado em event_url (em visitas, event_url é igual à URL original). A coluna independente foi removida. |
| platform | Redefinido | platform é sempre "WEBSITE". O SO foi movido para os campos os_version / user_agent. |
| postal_code | Inalterado | postal_code. |
| query_params | Obsoleto | A string de consulta bruta fica em event_url; a coluna de JSON analisado foi removida. Reimplemente o parsing a partir de event_url, se necessário. |
| referrer | Renomeado | http_referrer. |
| region | Renomeado | continent, código do continente (por exemplo, "NA"). |
| state | Inalterado | state. |

## Alterações de valores atribuídos (atualize filtros e agrupamentos)

O mecanismo de atribuição resolve as fontes de tráfego de forma diferente, então alguns VALORES mudam mesmo quando os nomes dos campos não mudam:
- renomeações de media_source: doubleclick_int → dv360_int (display/video do Google via UTM); "X Ads" → "Twitter" (Twitter via UTM). Mais valores de PID agora são remapeados para nomes de exibição (por exemplo, iossearchads_int → Apple Search Ads, metweb_int → Facebook Ads, tiktokweb_int → tiktokglobal_int, snapweb_int → snapchat_int).
- Os rótulos de canal mudam de formato: Direct / Organic search / Social media / Email / Ad / Referral / Other passam a ser DIRECT / ORGANIC_SEARCH / SOCIAL_MEDIA / EMAIL / AD / REFERRAL / OTHER.
- A cobertura de IDs de clique foi ampliada (mais networks são resolvidas a partir de IDs de clique); dclid sozinho não é mais resolvido; fbclid não é usado.

Examine a base de código em busca de qualquer filtro, CASE, chave de join ou agrupamento de dashboard baseado nesses valores antigos e atualize-os.

## Etapa 3: Criar

1. Proponha o novo design de ETL (ingestão, esquema, lógica incremental por hora, os filtros obrigatórios de "Structural changes").
2. Após minha aprovação, implemente-o reutilizando nossas convenções e infraestrutura existentes.
3. Para cada campo obsoleto que o inventário encontrar em uso downstream, liste o consumidor e proponha uma solução (remover, substituir pela alternativa sugerida ou sinalizar ao responsável de negócios).

## Etapa 4: Validar

1. Execute ambos os pipelines no mesmo intervalo de dias e compare: visitas (linhas SESSION) vs. visitas ao site no PBA, eventos (linhas IN_APP) vs. eventos do site no PBA e totais de receita.
2. Espere diferenças, não igualdade: a nova lógica de atribuição é mais avançada, então as dimensões atribuídas (media_source, campanha) não corresponderão exatamente ao PBA. A lógica de contagem de sessões permanece inalterada (30 minutos de atividade), portanto espere que os volumes de visitas permaneçam na mesma faixa.
3. Verifique se o filtro is_primary_attribution é aplicado em todos os lugares; a ausência dele aparece como contagens infladas de eventos.
4. Produza um breve relatório de migração: o que foi mapeado, o que foi descartado, o que mudou nos valores e quaisquer itens pendentes para o responsável pela área de negócios.
```

</Accordion>

## Migração de PBA web-S2S para a nova API S2S

Se você reporta eventos ao PBA por meio da <Anchor target="_blank" href="/marketers/pt/docs/web-server-to-server-events-api-for-pba-web-s2s">API de eventos servidor a servidor web (Web-S2S)</Anchor>, migre para a <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-s2s-api-for-web-performance-measurement">nova API S2S</Anchor>. A nova API oferece suporte a visitas e eventos, para que seu site possa funcionar totalmente no lado do servidor; o S2S do PBA aceita apenas eventos.

<Accordion title="Endpoints e autenticação">

|  | PBA web-S2S | Nova API S2S |
| --- | --- | --- |
| URL base | `https://webs2s.appsflyer.com` | `https://events.appsflyer.com` |
| Chamada de evento | `POST /v1/{bundleId}/event` | `POST /v2.0/s2s/inapps/app/web/{appId}` |
| Chamada de visita | Não disponível (as visitas vinham apenas do SDK web) | `POST /v2.0/s2s/visits/app/web/{appId}` |
| Chamada de identidade | `POST /v1/{bundleId}/setcuid` (chamada separada para associar um CUID a um usuário web) | Nenhuma, a identidade é enviada em linha no objeto `user_id` em cada evento/visita |
| Identificador do aplicativo | `bundleId` (ID do pacote da marca) no caminho | `appId` = o `unified_app_id` web ("website-`{domain}`") no caminho |
| Autenticação | `webDevKey` dentro do corpo JSON em cada chamada | Cabeçalho Authorization contendo a chave da API S2S |
| Tipo de conteúdo | `application/json` | `application/json` |
| Resposta de sucesso | 200 OK | 202 Aceito |

</Accordion>

<Accordion title="Mapeamento de campos do payload">

| Campo PBA web-S2S | Novo campo S2S | Atenção |
| --- | --- | --- |
| `customerUserId` | `user_id.customer_user_id` | Agora aninhado no objeto `user_id`. |
| `afUserId` | `user_id.appsflyer_id` | Agora aninhado no objeto `user_id`. Envie pelo menos um entre `customer_user_id` e `appsflyer_id`; envie ambos sempre que o usuário for identificado. |
| `webDevKey` | Sequência de caracteres | Removido do corpo. A autenticação foi movida para o cabeçalho Authorization; o Aplicativo é identificado por `appId` no caminho. |
| `eventType` (sempre EVENT) | Sequência de caracteres | Removido. O endpoint (/inapps vs. /visits) determina o tipo. |
| `eventName` | `nome_do_evento` | 1-64 caracteres; não pode conter `@ = + -`. |
| `timestamp` (Unix ms, 13 dígitos) | `timestamp` (Unix ms) | Mesmo formato. Recomendado em todas as chamadas; se omitido, a AppsFlyer usa o tempo de recebimento. |
| `Valor do evento` | `event_value` | Formato livre; oferece suporte a um subobjeto `custom_parameters`. |
| `eventRevenue` | `event_revenue` | Agora opcional (o PBA exigia isso para dashboards). |
| `eventRevenueCurrency` | `event_currency` | Agora opcional (o PBA exigia isso para dashboards). |
| `referrer` | `http_referrer` | Renomeado. |
| `userAgent` | `user_agent` | Renomeado. |
| `ip` | `ip` | Inalterado. |
| Sequência de caracteres | `event_url` | Novidade. Obrigatório em visitas; opcional em eventos. |
| Sequência de caracteres | `customer_dedup_id` | Novidade. Remove duplicações do mesmo evento que chega de outra fonte (por exemplo, o SDK web). |
| Sequência de caracteres | `email_hashed`, `phone_number_hashed`, `phone_number_e164_hashed`, `first_name_hashed`, `last_name_hashed` | Novidade. SHA256 (hexadecimal em minúsculas com 64 caracteres) de valores normalizados, para enriquecimento de identidade. |

</Accordion>

<Accordion title="Observações sobre a API S2S">

* **As visitas agora são do lado do servidor.** O S2S do PBA aceitava apenas eventos; as visitas precisavam vir do SDK web. O novo endpoint /visits permite que o site opere totalmente do lado do servidor.
* **Não é mais necessária a chamada setcuid.** O PBA exigia o SDK web, então era necessária uma chamada separada para vincular um CUID a um usuário da web. A nova API carrega a identidade inline em todas as solicitações, então essa etapa foi removida.
* **Janela para dados atrasados.** Envie eventos e visitas em tempo real, de preferência em até 30 minutos após a ocorrência do evento, em vez de agrupá-los em um único upload diário. Os dados que chegam mais de 30 minutos após o fim do dia UTC em que o evento ocorreu ainda são aceitos, mas o horário do evento é substituído pelo horário em que a AppsFlyer os recebeu.

</Accordion>

<Accordion title="Migração do serviço S2S: prompt pronto para uso para agente de código">

Se você reporta eventos pela API servidor a servidor do PBA, preparamos um prompt pronto para uso para seu agente de codificação com IA (Claude Code, Cursor ou similar). Dê ao agente acesso ao serviço que envia eventos para a AppsFlyer e cole o prompt abaixo; ele contém o endpoint completo e o mapeamento da carga útil. Ele orientará o agente a entender sua implementação atual e criar a versão atualizada.

```
Você está migrando uma integração do lado do servidor da API legada de eventos PBA Web S2S da AppsFlyer (webs2s.appsflyer.com) para a nova API S2S da AppsFlyer para mensuração de performance web (events.appsflyer.com). Tudo o que você precisa está neste prompt: endpoints, autenticação, o mapeamento completo da carga útil e as mudanças de comportamento. Não presuma nada além do que está escrito aqui; se algo estiver ambíguo, pergunte-me.

## Etapa 0: Faça estas perguntas antes de mexer no código

1. Devemos modificar o serviço existente no local ou criar um novo serviço/módulo em paralelo a ele (permitindo uma execução paralela e uma transição limpa)? Recomende um novo módulo em paralelo.
2. Eu sei o ID unificado do aplicativo do nosso novo aplicativo web? Formato: "website-{domain}" (por exemplo, website-www.example.com). Ele substitui o ID do pacote do PBA no caminho da URL. Se eu não souber, vou obtê-lo no dashboard da AppsFlyer antes de continuarmos.
3. Tenho a nova chave da API S2S? A autenticação passou da webDevKey no corpo da solicitação para um cabeçalho Authorization que carrega esta chave. Se eu não a tiver, vou recuperá-la no dashboard da AppsFlyer.
4. Queremos enviar apenas eventos (como no PBA) ou adotar também o novo endpoint de visitas? A nova API oferece suporte a visitas do lado do servidor, então o site pode ser executado totalmente do lado do servidor; o PBA aceitava apenas eventos.
5. O SDK web da AppsFlyer ainda está em execução no nosso site? (Isso determina se as visitas vêm do SDK e se precisamos de desduplicação de eventos entre o SDK e o S2S.)

## Etapa 1: Conheça o serviço atual

Explore a base de código e produza um inventário:
1. Todos os pontos de chamada para webs2s.appsflyer.com, as chamadas para /event e quaisquer chamadas para /setcuid.
2. Os campos preenchidos em cada chamada (customerUserId, afUserId, eventName, eventValue, eventRevenue, timestamp, referrer, userAgent, ip etc.) e de onde vêm seus valores.
3. Tratamento de erros e monitoramento com base na resposta 200 OK.
4. Comportamento de tentativas, processamento em lote e enfileiramento.

Apresente este inventário para mim e aguarde minha confirmação antes de prosseguir.

## O que mudou: endpoints e autenticação

|  | PBA Web-S2S (antigo) | Nova API S2S |
|---|---|---|
| URL base | https://webs2s.appsflyer.com | https://events.appsflyer.com |
| Chamada de evento | POST /v1/{bundleId}/event | POST /v2.0/s2s/inapps/app/web/{appId} |
| Chamada de visita | Não disponível | POST /v2.0/s2s/visits/app/web/{appId} |
| Chamada de identidade | POST /v1/{bundleId}/setcuid | Nenhuma; a identidade está embutida no objeto user_id em todas as chamadas |
| Identificador do aplicativo no caminho | bundleId (ID do pacote da marca) | appId = o ID unificado do aplicativo web ("website-{domain}") |
| Autenticação | webDevKey no corpo JSON | Cabeçalho Authorization com a chave da API S2S |
| Tipo de conteúdo | application/json | application/json (415 se estiver ausente) |
| Resposta de sucesso | 200 OK | 202 Accepted |

## Mapeamento de campos do payload

| Campo do PBA | Novo campo | Observação |
|---|---|---|
| customerUserId | user_id.customer_user_id | Aninhado no objeto user_id. |
| afUserId | user_id.appsflyer_id | Aninhado no objeto user_id. Envie pelo menos um entre customer_user_id ou appsflyer_id; envie ambos sempre que o usuário estiver identificado. |
| webDevKey | (removido) | A autenticação foi movida para o cabeçalho Authorization; o aplicativo é identificado pelo appId no caminho. |
| eventType (sempre "EVENT") | (removido) | O endpoint (/inapps vs /visits) determina o tipo. |
| eventName | event_name | 1-64 caracteres; não pode conter os caracteres @ = + -. |
| timestamp (Unix ms) | timestamp (Unix ms) | Mesmo formato. Recomendado em todas as chamadas; se omitido, o AppsFlyer usa o horário de recebimento. |
| eventValue | event_value | Formato livre; oferece suporte a um subobjeto custom_parameters. |
| eventRevenue | event_revenue | Agora é opcional (o PBA exigia isso para dashboards). |
| eventRevenueCurrency | event_revenue_currency | Agora é opcional (o PBA exigia isso para dashboards). |
| referrer | http_referrer | Renomeado. |
| userAgent | user_agent | Renomeado. |
| ip | ip | Inalterado. |
| (novo) | event_url | Obrigatório em visitas; opcional em eventos. |
| (novo) | customer_dedup_id | Remove duplicações do mesmo evento que chega de outra fonte (por exemplo, o SDK web). |
| (novo) | email_hashed, phone_number_hashed, phone_number_e164_hashed, first_name_hashed, last_name_hashed | SHA256 (hexadecimal minúsculo de 64 caracteres) de valores normalizados, para enriquecimento de identidade. |

## Mudanças de comportamento e pontos de atenção

1. **appId é o ID unificado do Aplicativo, não o "ID do SDK web".** A página de configurações do Aplicativo no AppsFlyer mostra um UUID de "ID do SDK web" (a antiga Web Dev Key, mantida para continuidade do SDK). O caminho S2S deve incluir o ID unificado do Aplicativo ("website-{domain}"), nunca esse UUID. Um 401 "app not found" geralmente significa um appId incorreto no caminho ou um cabeçalho Authorization ausente/inválido.
2. **O sucesso é 202, não 200.** Atualize as verificações de integridade, as novas tentativas e os alertas adequadamente.
3. **Não valide em relação ao endpoint antigo.** O endpoint legado ainda pode retornar 200, mas essa resposta não prova que os dados chegaram à mensuração de performance web. Sempre verifique se os eventos realmente aparecem nos dados do novo Aplicativo web.
4. **Elimine totalmente o fluxo setcuid.** A identidade é enviada inline no objeto user_id em cada evento e visita.
5. **Visitas antes de eventos.** O sistema espera uma visita antes de qualquer evento de um usuário; eventos de um usuário sem visita anterior são classificados como orgânicos. As visitas vêm do SDK web ou, agora, do endpoint /visits.
6. **Envie em tempo real; não agrupe em lote.** Envie cada evento e visita conforme acontecer, de preferência em até 30 minutos após a ocorrência do evento. Os dados que chegam mais de 30 minutos após o fim do dia UTC em que o evento ocorreu ainda são aceitos, mas o horário do evento é substituído pelo horário de recebimento, o que distorce a atribuição. Sempre envie um registro de data/hora. Observe que o atraso de atribuição de aproximadamente 30 minutos sobre o qual você pode ler é uma retenção separada, no lado do servidor, do AppsFlyer — não é algo que precisemos implementar.
7. **Opção completa do lado do servidor (se adotarmos visitas).** Sem o Web SDK, o nosso servidor controla o identificador do usuário na web: gere um ID estável para visitantes de primeira visita, persista-o como um cookie HTTP first-party definido pelo servidor (cabeçalho Set-Cookie, não JavaScript; cookies JS têm um limite de aproximadamente 7 dias no Safari), reutilize-o em todas as solicitações e envie-o como user_id.appsflyer_id. O payload de visita deve incluir event_url, e recomendamos também incluir ip, user_agent e http_referrer para a qualidade da atribuição.
8. **SDK + S2S juntos.** Se ambos enviarem o mesmo evento, preencha customer_dedup_id para que o AppsFlyer mantenha apenas uma cópia.

## Etapa 2: Criar

1. Proponha o design: novo cliente/módulo, configuração (URL base, appId, armazenamento da chave de API no nosso gerenciador de segredos, nunca codificada diretamente), builders de carga útil para eventos (e visitas, se estiverem no escopo) e o tratamento de resposta/repetição para 202.
2. Após a minha aprovação, implemente isso seguindo nossas convenções existentes.
3. Mapeie todos os campos do inventário por meio do mapeamento de carga útil acima; sinalize qualquer campo que enviamos atualmente e que não tenha um novo equivalente.

## Etapa 3: Validar

1. Envie um evento de teste (e visita, se estiver no escopo) e confirme uma resposta 202.
2. Verifique se os dados de teste aparecem no novo aplicativo web na AppsFlyer (dashboard ou Data Locker); esse é o sinal real de sucesso, não a resposta HTTP.
3. Confirme se os nomes dos eventos estão em conformidade com as novas restrições (1 a 64 caracteres, sem @ = + -).
4. Se estiver em execução em paralelo com o serviço antigo, compare os volumes de eventos entre o antigo e o novo por alguns dias antes da transição e, em seguida, desative as chamadas antigas, incluindo setcuid.
```

</Accordion>

<div data-zendesk-anchors="why-were-upgrading-your-web-measurement=por-que-estamos-aprimorando-sua-mensura%C3%A7%C3%A3o-web h_01KYM7JM37WVTV7XHEHVTPKWM9=por-que-estamos-aprimorando-sua-mensura%C3%A7%C3%A3o-web comparing-pba-and-web-performance-measurement=comparando-o-pba-e-a-mensura%C3%A7%C3%A3o-de-performance-web h_01KYM7JM3711FXC132MSC3B4A9=comparando-o-pba-e-a-mensura%C3%A7%C3%A3o-de-performance-web h_01KYM7JM3711FXC132MSC3B4A8=web-performance-measurement-vs-pba traffic-source-resolution-pba-vs-web-performance-measurement=resolu%C3%A7%C3%A3o-da-fonte-de-tr%C3%A1fego-pba-vs-mensura%C3%A7%C3%A3o-de-performance-web h_01KYM7JM387R5YEYJK9CD0AQJ0=resolu%C3%A7%C3%A3o-da-fonte-de-tr%C3%A1fego-pba-vs-mensura%C3%A7%C3%A3o-de-performance-web migrate-to-web-performance-measurement=migrar-para-a-mensura%C3%A7%C3%A3o-de-performance-web h_01KYM7JM37HG8YAX02XMSKBTPP=migrar-para-a-mensura%C3%A7%C3%A3o-de-performance-web h_01KYM7JM37HG8YAX02XMSKBTPP01=1-criar-um-aplicativo-web-obrigat%C3%B3rio-para-todos create-a-web-app=1-criar-um-aplicativo-web-obrigat%C3%B3rio-para-todos h_01KYM7JM37HG8YAX02XMSKBTPP02=3-se-voc%C3%AA-envia-eventos-pela-api-s2s if-you-send-events-through-the-s2s-api=3-se-voc%C3%AA-envia-eventos-pela-api-s2s h_01KYM7JM37HG8YAX02XMSKBTPP03=3-se-voc%C3%AA-consome-os-relat%C3%B3rios-de-dados-brutos-do-pba if-you-consume-pbas-raw-data-reports=3-se-voc%C3%AA-consome-os-relat%C3%B3rios-de-dados-brutos-do-pba h_01KYM7JM37HG8YAX02XMSKBTPP04=4-se-voc%C3%AA-usa-o-pba-brand-bundle-para-reportar-multiplataforma if-you-use-pba-brand-bundle-for-cross-platform-reporting=4-se-voc%C3%AA-usa-o-pba-brand-bundle-para-reportar-multiplataforma capabilities-being-discontinued=capacidades-que-ser%C3%A3o-descontinuadas h_01KYM7JM37JJ25D3RFE2V7BM4D=capacidades-que-ser%C3%A3o-descontinuadas raw-data-field-mapping=mapeamento-de-campos-de-dados-brutos h_01KYM7JM37Z7Z21FJ2G83T2WPG=mapeamento-de-campos-de-dados-brutos pba-web-s2s-to-new-s2s-api-migration=migra%C3%A7%C3%A3o-de-pba-web-s2s-para-a-nova-api-s2s h_01KYM7JM38K9C01XDZY99KZVTX=migra%C3%A7%C3%A3o-de-pba-web-s2s-para-a-nova-api-s2s" />

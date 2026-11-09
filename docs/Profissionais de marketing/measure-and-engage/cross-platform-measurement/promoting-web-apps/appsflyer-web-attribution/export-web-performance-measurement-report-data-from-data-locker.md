---
title: Exportar dados de relatórios de mensuração de performance web do Data Locker
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T10:49:59Z'
  edited_at: '2026-08-25T00:22:06Z'
  id: 43510758321809
  locale: pt
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/pt/articles/43510758321809
---
> **Em resumo:** Exporte dados de mensuração de performance web do Data Locker em dois tipos de relatório que permitem analisar a performance do site no nível certo. Use End User Events para analisar todas as visitas e eventos e use Conversions para contar e atribuir âncoras de conversão únicas (primeiras visitas, revisitas e eventos de aquisição de usuários).

> ❗️ **Warning**
>
> **Importante!** Você precisa ter uma assinatura do Data Locker para usar os relatórios de mensuração de performance web no Data Locker.

<div id="about-the-web-performance-measurement-reports" />

## Sobre os relatórios de mensuração de performance web

O Data Locker oferece dois relatórios para mensuração de performance web, **End User Events** e **Conversions**, cada um projetado para diferentes necessidades de análise.

* O relatório **End User Events** é a principal fonte para analisar a atividade do site:
  * Inclui **todos os eventos web e todas as visitas**
  * Registra cada visita como uma `SESSION` atribuída
  * Ideal para relatórios no **nível de visita** e no **nível de evento**
* O relatório de **Conversions** é mais adequado para análises no nível de conversão. Uma conversão é uma âncora de atribuição, um touchpoint que determina quando e como atribuir crédito de marketing. Isso inclui:
  * *primeiras visitas* (quando um usuário chega ao seu site pela primeira vez),
  * *revisitas* (quando um usuário retorna após um engajamento com anúncio não orgânico) e
  * *eventos de aquisição de usuários* (eventos personalizados, como cadastro ou primeiro depósito) que indicam que um usuário foi adquirido.
* Todos os eventos do usuário são vinculados posteriormente a essas conversões e herdam os detalhes da campanha

A interface Advanced Reports do Data Locker também lista **Engagements** e **End User Events Cross-Platform** como opções separadas de relatório de mensuração da performance web. Este artigo aborda **End User Events** e **Conversions**, os dois relatórios usados na maior parte das análises de mensuração da performance web.

<div id="select-a-web-performance-measurement-report" />

## Selecione um relatório de mensuração da performance web

Antes de exportar os dados de mensuração da performance web, selecione o relatório relevante no Data Locker.

1. Na AppsFlyer, no menu lateral, selecione **Exportar > Data Locker**.
2. Clique na aba **Advanced Reports**.
3. Selecione **End User Events** ou **Conversions** na lista de relatórios de mensuração de performance web.
4. Clique em **Salvar configuração**.

<div id="report-fields" />

## Campos do relatório

Para saber quais campos estão contidos nos relatórios, baixe uma amostra de cada relatório:

* [Amostra do relatório de eventos do usuário final](https://docs.google.com/spreadsheets/d/e/2PACX-1vQYFF0r4pMpo_voSK8QObpiRtx-diU_0a-0XVuKIVMEfh6rRPudIDXA5bgDw_lcc0qwBPcPhYtLdWwh/pub?output=csv)
* [Amostra do relatório de eventos de conversão](https://docs.google.com/spreadsheets/d/e/2PACX-1vTMqcc6PKBATBg1DYVO8MWKrAs_wlqXxyANe3a_gu62xp3hFZV9wWT1X8c9oRekaIEwCfKZ2y9agVeV/pub?output=csv)

A amostra do relatório inclui todos os campos do relatório e seus valores. Para as definições dos campos, consulte <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">o dicionário de campos</Anchor>.

<div id="report-timing-and-data-freshness" />

## Periodicidade do relatório e atualização dos dados

Use estes detalhes para entender quando novos dados são adicionados e quando eventos recentes ficam disponíveis no relatório.

* **Frequência do relatório**: novos dados são adicionados a cada hora.
* **Atualização dos dados**: os eventos normalmente aparecem no relatório entre 2 e 3 horas após a ocorrência.

<div id="heres-how-each-batch-works" />

### Veja como cada lote funciona:

* Cada lote **processa** eventos de uma janela de 1,5 horas.
* Dentro dessa janela, somente a primeira hora de eventos é **atribuída**.
* Os 30 minutos restantes são usados **exclusivamente para enriquecer** os eventos atribuídos com IDs de usuário do cliente (CUIDs).
* Os 30 minutos mais recentes de eventos **ainda não são atribuídos** — serão incluídos no próximo lote.

<Image align="center" alt="" src="https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png" />

<div id="when-will-these-events-appear-in-the-report" />

### Quando esses eventos aparecerão no relatório?

Os eventos são gravados nos relatórios **após o término do processamento**. Assim, por exemplo, eventos de **08:00–09:00**, atribuídos no lote das 10:00, aparecerão na **versão do relatório das 11:00**.

<div id="example-what-the-1000-am-batch-does" />

### Exemplo: o que o lote das 10:00 faz

| **Date** | **Relatório disponível às** | **Eventos web atribuídos (hora do evento)** | **Eventos web processados para enriquecer eventos anteriores com CUIDs** |
| --- | --- | --- | --- |
| 2026-01-28 | 11:00 | 08:00 – 09:00 | 09:00–09:30 |
| 01-2026-28 | 12:00 | 09:00 – 10:00 | 10:00–10:30 |
| 2026-01-28 | 13:00 | 10:00 – 11:00 | 10:00-11:30 |

<div id="download-report-data-from-your-cloud-bucket" />

## Faça download dos dados do relatório do seu cloud bucket

Para mais informações sobre como fazer download dos dados do relatório do seu cloud bucket, consulte <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#folder-structure">a estrutura de pastas do Data Locker</Anchor>.

<div id="bi-developer-considerations" />

## Considerações para desenvolvedores de BI

<Accordion title="Principais diferenças: web vs. mobile">

A atribuição web difere da atribuição mobile tanto nos identificadores quanto na lógica de dados. Para melhorar a precisão dos dados, aplique os filtros e as melhores práticas a seguir nas suas consultas.

| Aspecto | Mobile | Web |
| --- | --- | --- |
| Filtro de plataforma | `platform = 'IOS'` ou `platform = 'ANDROID’` | `plataforma = 'WEBSITE'` |
| Identificador do usuário (valor) | `appsflyer_id` (baseado no dispositivo) | `appsflyer_id_value` (baseado em cookie) |
| Tipo de identificador | Varia de acordo com o dispositivo | `appsflyer_id_type` é sempre `web_id` |
| Evento de aquisição | não relacionada | First Visit é o padrão, mas o evento de aquisição de usuários pode ser personalizado |
| Re-engajamento | `REENGAJAMENTO` | `REVISIT` |
| Re-atribuição | Com suporte. | Não suportado — a web só tem Aquisição de usuários e revisitas |
| ID da aplicação | ID do aplicativo (por exemplo, `id123456789`) | Domínio com prefixo (por exemplo, `website-www.example.com`) |

</Accordion>

<Accordion title="Qual tabela consultar?">

O relatório **End User Events** é adequado para a maioria das análises. Ele inclui todos os eventos e visitas do site. Cada visita na web também é registrada como uma `SESSION` atribuída neste relatório, tornando-o a principal fonte para reportar em nível de visita e em nível de evento.

A tabela **Conversions** é adequada principalmente para contar primeiras visitas, revisitas e aquisições de usuários quando você precisa de conversões únicas sem registros de eventos duplicados.

| Caso de uso | Tabela | Por quê |
| --- | --- | --- |
| Contar visitas/sessões | `end_user_events` | Cada linha é uma sessão ou evento |
| Contar conversões únicas | `conversões` | Evita duplicações |
| Analise eventos in-app | `end_user_events` com `end_user_event_type = 'IN_APP'` | Somente eventos in-app têm nomes de evento |

</Accordion>

<Accordion title="Implementar filtros de consulta">

Aplique os filtros a seguir para garantir que as consultas de dados brutos sejam precisas. Não implementar esses filtros resultará em entradas duplicadas e métricas entre plataformas.

* **Filtrar por plataforma (obrigatório):** Inclua `WHERE platform = 'WEBSITE'` para isolar dados originados na web e excluir registros de ambientes mobile, PC ou CTV.
* **Filtrar por crédito de atribuição (obrigatório):** A mesma ação do usuário pode aparecer duas vezes em `end_user_events` porque a AppsFlyer pode atribuir a ela dois créditos de atribuição diferentes, dependendo da visualização do relatório.

  Isso pode acontecer quando o usuário tem:

  * uma fonte original de **Aquisição de usuários (UA)** e, posteriormente,
  * uma fonte de **reengajamento**.

  Nesse caso, a AppsFlyer pode gravar dois registros para o mesmo evento:

  * **Crédito primário:** atribui o evento à interação de marketing relevante mais recente. Usado nas visualizações unificada e de retargeting.

    Para evitar contagem dupla, consulte `end_user_events` usando apenas o registro de crédito primário por padrão:

    ```sql
    WHERE platform = 'WEBSITE'
      AND is_primary_attribution = true
    ```
  * **Crédito secundário:** atribui o evento de volta à fonte original de UA. Usado na visualização de aquisição de usuários para mensuração do valor vitalício (LTV).

    Como a mesma ação do usuário pode ser armazenada como dois registros (um com crédito primário e outro com crédito secundário), contar eventos sem um filtro pode resultar em contagem dupla dessa ação.

    Use estas consultas como modelos para analisar dados de atribuição web no BigQuery ou em outras ferramentas de BI.

* **Filtrar por tipo de conversão (opcional):** Inclua `WHERE conversion_type = 'USER_ACQUISITION'` ou `WHERE conversion_type = 'RETARGETING'` para isolar dados de atribuição com base no tipo de campanha.

<div id="filter-summary-table" />

#### Tabela de resumo dos filtros

| Requisito do filtro | Lógica SQL | Contexto de implementação |
| --- | --- | --- |
| Especificação da plataforma | `WHERE platform = 'WEBSITE'` | Isola dados originados na web de registros de outras plataformas. |
| Visualização unificada (evita duplicatas) | `WHERE is_primary_attribution = true AND platform = 'WEBSITE'` | Priorize o crédito da campanha de retargeting em detrimento da campanha de UA original. Use para relatórios gerais e para evitar contagem dupla. |
| Somente visualização de retargeting | `WHERE conversion_type = 'RETARGETING' AND platform = 'WEBSITE'` | Use especificamente ao analisar a performance apenas de campanhas de retargeting. |
| Somente visualização de aquisição de usuários | `WHERE conversion_type = 'USER_ACQUISITION' AND platform = 'WEBSITE'` | Use especificamente para visualizações focadas em aquisição, nas quais os eventos precisam estar vinculados à visita inicial. |

</Accordion>

<Accordion title="Identificação e contagem de usuários finais">

Nos dados brutos da mensuração de performance web, um usuário final pode aparecer com dois identificadores diferentes:

* `customer_user_id`: Um identificador estável definido por você (normalmente para usuários conectados).
* `appsflyer_id_value`: Um ID baseado em cookie que pode expirar com o tempo.

Para identificar corretamente **usuários únicos** e calcular **métricas em nível de usuário**, sempre use:

```sql
COALESCE(customer_user_id, appsflyer_id_value)
```

Veja como funciona:

* Se `customer_user_id` existir, a AppsFlyer o usa (preferencial, estável).
* Se não existir, a AppsFlyer recorre a `appsflyer_id_value`.

Use `COALESCE(customer_user_id, appsflyer_id_value)` sempre que precisar:

* Contar usuários distintos
* Agrupar por usuário
* Filtrar por usuários específicos
* Fazer join de tabelas por usuário
* Calcular quaisquer métricas em nível de usuário

<div id="example-count-distinct-users" />

#### Exemplo: contar usuários distintos

```sql
SELECT 
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users FROM `end_user_events` WHERE platform = 'WEBSITE'
  AND is_primary_attribution = TRUE
```

</Accordion>

<Accordion title="Tráfego orgânico vs. não orgânico">

Use o campo `is_organic`:

| Tipo de tráfego | Filtro |
| --- | --- |
| Orgânico | `is_organic = true` |
| Não orgânica | `is_organic = false` |

</Accordion>

<Accordion title="Como lidar com valores vazios">

| Tipo de dados | Valor vazio |
| --- | --- |
| Sequência de caracteres | `''` (string vazia) |
| Numérico | `NULL` |

</Accordion>

<Accordion title="Exemplos de query">

<Accordion title="1. Total de visitas por canal de mídia (7 dias)">

Conta as sessões web atribuídas a cada canal de mídia.

```sql
SELECT media_source, COUNT(*) AS total_visits FROM end_user_events WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'SESSION' GROUP BY media_source ORDER BY total_visits DESC
```

</Accordion>

<Accordion title="2. Primeiras visitas e revisitas por campanha">

```sql
SELECT campaign_name, conversion_name, COUNT(*) AS conversion_count FROM conversions WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name IN ('FIRST_VISIT', 'REVISIT')
GROUP BY campaign_name, conversion_name ORDER BY conversion_count DESC
```

</Accordion>

<Accordion title="3. Contar nomes de eventos distintos (somente eventos in-app)">

```sql
SELECT
  event_name,
  COUNT(*) AS event_count FROM end_user_events WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'IN_APP' GROUP BY event_name ORDER BY event_count DESC
```

</Accordion>

<Accordion title="4. Contar usuários distintos por canal de mídia">

```sql
SELECT
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users FROM end_user_events WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true GROUP BY media_source ORDER BY unique_users DESC
```

</Accordion>

<Accordion title="5. Taxa de conversão - da primeira visita à compra (junção entre tabelas)">

```sql
WITH first_visits AS (
  SELECT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id,
    media_source
  FROM conversions
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND conversion_name = 'FIRST_VISIT'
),
purchases AS (
  SELECT DISTINCT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id
  FROM end_user_events
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND is_primary_attribution = true
    AND end_user_event_type = 'IN_APP'
    AND event_name = 'purchase'
)
SELECT
  fv.media_source,
  COUNT(DISTINCT fv.user_id) AS first_visit_users,
  COUNT(DISTINCT p.user_id) AS purchasers,
  SAFE_DIVIDE(COUNT(DISTINCT p.user_id), COUNT(DISTINCT fv.user_id)) AS conversion_rate FROM first_visits fv LEFT JOIN purchases p ON fv.user_id = p.user_id GROUP BY fv.media_source ORDER BY conversion_rate DESC
```

</Accordion>

<Accordion title="6. Receita por campanha (últimos 7 dias)">

```sql
SELECT
  campaign_name,
  media_source,
  SUM(revenue_usd) AS total_revenue_usd,
  COUNT(*) AS revenue_events FROM end_user_events WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND revenue_usd IS NOT NULL
  AND revenue_usd <> 0.0 GROUP BY campaign_name, media_source ORDER BY total_revenue_usd DESC
```

</Accordion>

<Accordion title="7. Primeiras visitas orgânicas vs. não orgânicas por dia">

```sql
SELECT
  DATE(event_time) AS visit_date,
  CASE WHEN is_organic = true THEN 'Organic' ELSE 'Non-Organic' END AS traffic_type,
  COUNT(*) AS first_visits FROM conversions WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name = 'FIRST_VISIT' GROUP BY visit_date, traffic_type ORDER BY visit_date, traffic_type
```

</Accordion>

<Accordion title="8. Detalhamento de aquisição de usuários vs. retargeting">

```sql
SELECT
  conversion_type,
  conversion_name,
  COUNT(*) AS conversions FROM conversions WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com' GROUP BY conversion_type, conversion_name ORDER BY conversions DESC
```

</Accordion>

<Accordion title="9. Distribuição de IDs de clique (Google, Meta, TikTok etc.)">

```sql
SELECT
  click_id_type,
  COUNT(*) AS events_with_click_id FROM end_user_events WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND click_id_type != '' GROUP BY click_id_type ORDER BY events_with_click_id DESC
```

</Accordion>

<Accordion title="10. Agrupe os usuários em coortes por data de conversão (equivalente à data de instalação no mobile)">

```sql
SELECT
  DATE(event_time__conversion) AS cohort_date,
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS cohort_users FROM end_user_events WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true GROUP BY cohort_date, media_source ORDER BY cohort_date, cohort_users DESC
```

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

## Especificações e limitações

Os campos a seguir **não são compatíveis com dados da web** e sempre estarão vazios:

| Caraterística | Descrição |
| --- | --- |
| `advertising_id_type`, `hardware_id_type`, etc. | Ambos |
| `agency`, `site_id`, `ad_type` | Ambos |
| `platform_group` | conversões |
| `app_version__conversion` | end\_user\_events |
| Todos os campos `__assist_*` | conversões |

<div id="see-also" />

## Consulte também

* <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports">Sobre os relatórios avançados do Data Locker</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker para profissionais de marketing</Anchor>

<div data-zendesk-anchors="about-the-data-locker-web-attribution-reports=sobre-os-relat%C3%B3rios-de-mensura%C3%A7%C3%A3o-de-performance-web h_01KGM4FT90X1K2V8M8GJV6EW5K=sobre-os-relat%C3%B3rios-de-mensura%C3%A7%C3%A3o-de-performance-web h_01_select-web-performance-measurement-report=selecione-um-relat%C3%B3rio-de-mensura%C3%A7%C3%A3o-da-performance-web select-a-web-performance-measurement-report=selecione-um-relat%C3%B3rio-de-mensura%C3%A7%C3%A3o-da-performance-web report-fields=campos-do-relat%C3%B3rio h_01KGM4FT90WP73N1D75WWNT2TE=campos-do-relat%C3%B3rio report-timing-and-data-freshness=periodicidade-do-relat%C3%B3rio-e-atualiza%C3%A7%C3%A3o-dos-dados h_01KGM4FT90B6W7KBS9K1FSSETD=periodicidade-do-relat%C3%B3rio-e-atualiza%C3%A7%C3%A3o-dos-dados here%E2%80%99s-how-each-batch-works=veja-como-cada-lote-funciona h_01KGM4FT91MCGCBYSHE18JHQ96=veja-como-cada-lote-funciona when-will-these-events-appear-in-the-report=quando-esses-eventos-aparecer%C3%A3o-no-relat%C3%B3rio h_01KGM4FT91XF7HCM8E8TQ56D0D=quando-esses-eventos-aparecer%C3%A3o-no-relat%C3%B3rio example-what-the-1000-am-batch-does=exemplo-o-que-o-lote-das-1000-faz h_01KGM4FT91D90DWYGSE3SES2ZY=exemplo-o-que-o-lote-das-1000-faz download-report-data-from-your-cloud-bucket=fa%C3%A7a-download-dos-dados-do-relat%C3%B3rio-do-seu-cloud-bucket h_01KGM4FT91NECKXMDW60A4B9X5=fa%C3%A7a-download-dos-dados-do-relat%C3%B3rio-do-seu-cloud-bucket bi-developer-considerations=considera%C3%A7%C3%B5es-para-desenvolvedores-de-bi h_01KGM4FT91C2KP050ZAYW6K8FD=considera%C3%A7%C3%B5es-para-desenvolvedores-de-bi filter-summary-table=tabela-de-resumo-dos-filtros h_01KGM4FT91MSN2SN7TKNJZ54V4=tabela-de-resumo-dos-filtros example-count-distinct-users=exemplo-contar-usu%C3%A1rios-distintos h_01KGM4FT91VDR0FWTMAPW6GM83=exemplo-contar-usu%C3%A1rios-distintos traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KGM4FT91QZR30KJAQ87AG691=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01_web-perf-see-also=consulte-tamb%C3%A9m see-also=consulte-tamb%C3%A9m" />

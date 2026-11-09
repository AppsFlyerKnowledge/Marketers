---
title: Relatório multiplataforma de eventos de usuário final no Data Locker
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-10-07T10:37:56Z'
  edited_at: '2026-10-20T03:54:59Z'
  id: 39748676204817
  locale: pt
  section: Cross platform reports
  section_id: 50467263168657
  url: https://support.appsflyer.com/hc/pt/articles/39748676204817
---
> **Resumo:** O relatório de eventos cross-platform realizados por usuários finais mensura jornadas completas dos usuários, conversões e LTV entre diferentes plataformas e dispositivos

O relatório de eventos cross-platform realizados por usuários finais é um relatório de dados brutos que fornece logs de eventos a nível de sessão e eventos in-app para cada usuário, conectando os dados entre plataformas usando o Customer User ID (CUID). Cada evento inclui o resultado da atribuição cross-platform, permitindo que você analise jornadas completas de usuários.

Para mais informações sobre o fluxo e a configuração da atribuição baseada em usuário, acesse o artigo sobre a <Anchor target="_blank" href="/marketers/pt/docs/beta-user-based-cross-platform-attribution">atribuição cross-platform baseada em usuário</Anchor>.

<div id="report-fields" />

## Campos do relatório

Para saber quais campos estão contidos no relatório, [baixe o relatório de exemplo](https://docs.google.com/spreadsheets/d/e/2PACX-1vRhOl-tyaJvgPd9rxGkGMNrgzHPpr7ZsMMnONOHkzdObor158gJPt7XwCBkreM4ka4OkGIyDmqCp_hh/pub?output=csv).

Ele inclui todos os campos do relatório e seus valores. Para as definições dos campos, acesse <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">o dicionário de campos de dados brutos</Anchor>.

<div id="report-data-freshness" />

## Atualização dos dados do relatório

* O relatório executa um lote a cada 4 horas.
* Cada execução de lote processa eventos que entraram no banco de dados durante as últimas 4 horas.
  * Exemplo: A execução do lote das 8h processa eventos que foram inseridos no banco de dados entre 3h e 7h.

* Os eventos são distribuídos em seus respectivos buckets por hora.
  * Exemplo: Eventos que entraram no banco de dados entre 3h e 4h aparecerão no bucket das 3h.

<div id="important" />

> 🚧 **Importante!**
>
> Normalmente, há um pequeno atraso entre o momento em que um evento ocorre e sua entrada no banco de dados. O relatório usa o horário de entrada no banco de dados para garantir um agrupamento horário preciso e consistente.

<div id="example-of-the-800-am-batch-run" />

### Exemplo da execução do lote das 8h

| Data | Versão do relatório | Relatório disponível às | O relatório inclui eventos que ocorreram entre | O relatório inclui eventos que entraram no banco de dados entre |
| --- | --- | --- | --- | --- |
| 01/10/2025 | 3:00 | 9:00 | 2:00-4:00 | 3:00-4:00 |
| 01/10/2025 | 4:00 | 9:00 | 3:00-5:00 | 4:00-5:00 |
| 01/10/2025 | 5:00 | 9:00 | 4:00-6:00 | 5:00-6:00 |
| 01/10/2025 | 6:00 | 9:00 | 5:00-7:00 | 6:00-7:00 |

Observações sobre o exemplo acima:

* Eventos que ocorrem na última hora antes da execução não são processados. O objetivo é que tempo o suficiente passe para enriquecer eventos com o CUID relacionado. No exemplo acima, o processo em lote das 8:00h processa eventos que entraram no banco de dados entre 3:00h e 7:00h. Eventos que entraram no banco de dados entre 7:00h e 8:00h não são processados.
* O relatório está disponível apenas uma hora após a execução do lote, pois um processo interno atualiza o lote durante essa hora. No exemplo acima, o lote das 8:00h está disponível às 9:00h.

<div id="how-to-subscribe-to-the-report" />

## Como posso me inscrever para esse relatório?

1. Na AppsFlyer, no menu lateral, selecione **Exportar > Data Locker**.
2. No painel de conteúdo do **Data Locker**, vá até a seção **Relatórios avançados**.
3. Selecione **Eventos cross-platform de usuários finais**

<div id="how-to-access-the-report-data-in-your-cloud-bucket" />

## Como acessar os dados do relatório no seu bucket na nuvem?

O caminho (path) para o relatório consiste na seguinte hierarquia de pastas:

```
<bucket-name>/<DataLocker connection name>/t=end_user_events_user_level_cross_platform/dt=<dt=yyyy-mm-dd>/h=<hour>/
```

<div id="dl-report-folder-hierarchy" />

### Hierarquia de pastas de relatório

<Image align="center" alt="" src="https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png" />

<div id="bi-developer-considerations" />

## Considerações para o desenvolvedor de BI

* Cada bucket de relatório por hora contém eventos de usuários finais únicos. Certifique-se de extrair todos os relatórios em uma base horária ou diária.
* Eventos de receita de anúncios ainda não estão inclusos.
* Todos os dados do aplicativo são fornecidos em um único arquivo. Use o campo App ID para separar dados por aplicativo ou defina o Data Locker para segregar por aplicativo. É recomendado usar o tipo de segregação unificada.
* Os dados de pré-atribuição, como custo, cliques e impressões, devem ser extraídos do relatório de Cost ETL.

<div id="query-examples" />

### Exemplos de query

Veja a seguir exemplos de alguns usos práticos e populares dos dados via Data Locker. Cada exemplo é ilustrado por uma declaração SQL.

<div id="calculating-total-user-acquisitions" />

<Accordion title="Calculando o total de aquisições de usuários">

Conte o número de novos usuários únicos por canal de mídia e campanha.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT customer_user_id) AS user_acquisition
	, FROM end_user_events_user_level_cross_platform WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME' GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-platform-activations" />

<Accordion title="Calculando o total de ativações de plataforma">

Some o total de novos grupos, plataformas, canais de mídia e campanhas trazidos por usuário.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT CASE 
			WHEN platform_group = 'PC'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CONSOLE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CTV'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'MOBILE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Web'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Other'
				THEN customer_user_id
			ELSE NULL
			END) AS total_activations FROM end_user_events_user_level_cross_platform WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME' GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-revenue" />

<Accordion title="Calculando a receita total">

Some a receita total por canal de mídia e campanha.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,SUM(revenue_value_customer) AS total_revenue FROM end_user_events_user_level_cross_platform WHERE product_line_name = ’YOUR_PRODUCT_LINE_NAME’ GROUP BY install_date
	,media_source
	,campaign_name;
```

</Accordion>

<div data-zendesk-anchors="the-report-fields=campos-do-relat%C3%B3rio h_01K6Z40KG9H1AC81H77XXEGK1B=campos-do-relat%C3%B3rio report-data-freshness=atualiza%C3%A7%C3%A3o-dos-dados-do-relat%C3%B3rio h_01K6Z40KG9PTRAFGXB3XJH5TJ7=atualiza%C3%A7%C3%A3o-dos-dados-do-relat%C3%B3rio h_01K6Z40KG9QPSMXT13N50TE7KE=importante example-of-the-800-am-batch-run=exemplo-da-execu%C3%A7%C3%A3o-do-lote-das-8h h_01K6Z40KG9JTHGJG7YJNH9TTDT=exemplo-da-execu%C3%A7%C3%A3o-do-lote-das-8h how-to-subscribe-to-the-report=como-posso-me-inscrever-para-esse-relat%C3%B3rio h_01K6Z40KG9J1XWV99Z9M7AG0BY=como-posso-me-inscrever-para-esse-relat%C3%B3rio how-to-access-the-report-in-your-bucket=como-acessar-os-dados-do-relat%C3%B3rio-no-seu-bucket-na-nuvem h_01K6Z40KG9CDQ43ASM5T80AK65=como-acessar-os-dados-do-relat%C3%B3rio-no-seu-bucket-na-nuvem dl-report-folder-hierarchy=hierarquia-de-pastas-de-relat%C3%B3rio h_01K6Z40KG9NSVWTRSHR71Q7PM6=hierarquia-de-pastas-de-relat%C3%B3rio bi-developer-considerations=considera%C3%A7%C3%B5es-para-o-desenvolvedor-de-bi h_01K6Z7QHDT4Q2D4JFGC28W8MND=considera%C3%A7%C3%B5es-para-o-desenvolvedor-de-bi query-examples=exemplos-de-query h_01K6Z40KG9E2F30Q9P5GFA9TWT=exemplos-de-query h_01K6Z40KG9Y4MWKY6HX8A5NPXA=calculating-total-user-acquisitions h_01K6Z40KG9J9VKC3JH6XNNDA52=calculating-total-platform-activations h_01K6Z40KG9SE8068HG75H59E8Q=calculating-total-revenue" />

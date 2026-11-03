---
title: Dados brutos da Pull API
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2026-08-19T00:04:24Z'
  id: 360007530258
  locale: pt
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/pt/articles/360007530258
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** use essa API para obter relatórios de dados brutos em arquivos CSV.

[![PullAPIRaw_us-en.png](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)

## Dados brutos da Pull API

* A Pull API permite que você obtenha relatórios de dados brutos em arquivos CSV. <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Saiba mais sobre relatórios de dados brutos</Anchor>
* Filtre pelas opções disponíveis: fonte de mídia, intervalo de datas, nome do evento in-app e geolocalização.
* Os recursos adicionais da Pull API são:
  * Escolha a moeda
  * Escolha o fuso horário

#### Relatórios de dados brutos disponíveis através da Pull API

<table><thead><tr><th>Relatório</th><th>Descrição</th><th>Taxa de atualização</th></tr></thead><tbody><tr><td colspan="3"><h4><strong><span id="raw-data-reports-nonorganic"></span>Relatórios de dados brutos (não orgânicos)</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5" target="_blank">Instalações</a></td><td>Registra instalações não orgânicas. O registro é gerado quando um usuário abre o aplicativo pela primeira vez.<br/> </td><td>Em tempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5" target="_blank">Eventos in-app</a></td><td>Registra os eventos realizados pelos usuários.<br/> </td><td>Em tempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5" target="_blank">Desinstalações</a></td><td>Registra quando um usuário desinstala o aplicativo.<br/> </td><td>Diário</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">Reinstalações</a><br/> </td><td>Registra os usuários que, após desinstalar o aplicativo, engajam com um canal de mídia de UA e reinstalam o aplicativo durante a janela de reatribuição.</td><td>Diário</td></tr><tr><td colspan="3"><h4><strong><span id="raw-data-reports-organic"></span>Relatórios de dados brutos (orgânicos)</strong></h4></td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">Instalações orgânicas</a><br/> </td><td>Registra quando o aplicativo é aberto por um usuário pela primeira vez.<br/> </td><td>Contínuo</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">Eventos orgânicos in-app</a><br/> </td><td>Registra informações sobre os eventos realizados pelos usuários.<br/> </td><td>Contínuo</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">Desinstalações orgânicas</a><br/> </td><td>Registra os usuários que desinstalaram o aplicativo.<br/> </td><td>Diário</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">Reinstalações orgânicas</a><br/> </td><td>Registra os usuários que, após desinstalar o aplicativo, engajam com um canal de mídia de UA e reinstalam o aplicativo durante a janela de reatribuição.</td><td>Diário<br/> </td></tr><tr><td colspan="3"><h4><strong><span id="retargeting"></span>Redirecionamento</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-retarget-v5">Conversões</a></td><td>Registro do usuário que abre o aplicativo depois de se engajar com uma campanha de retargeting.</td><td>Em tempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-retarget-v5">Eventos in-app</a></td><td>Eventos in-app realizados pelo usuário durante a janela de reengajamento.</td><td>Em tempo real</td></tr><tr><td colspan="3"><h4><strong><span id="ad-revenue-raw-data"></span>Receitas de anúncios em dados brutos</strong></h4></td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">Receita de anúncios atribuída</a><br/> </td><td>Registra a receita de anúncios dos usuários atribuída a um canal de mídia.</td><td>Diário</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5" target="_blank">Receita publicitária orgânica</a></td><td>Registra a receita de anúncios dos usuários não atribuída a um canal de mídia.</td><td>Diário</td></tr><tr><td colspan="3"><h4><strong><span id="protect360-fraud"></span>Fraude no Protect360</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5" target="_blank">Instalações</a></td><td>Registra instalações identificadas como fraudulentas e, portanto, não atribuídas a nenhum canal de mídia.</td><td>Em tempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5" target="_blank">Instalações pós-atribuição</a></td><td>Registra eventos in-app de instalações fraudulentas e, portanto, não são atribuídos de forma alguma.</td><td>Diário</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5" target="_blank">Eventos in-app</a></td><td>Registra eventos in-app identificados como fraudulentos pelo Protect360.</td><td>Em tempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5" target="_blank">Eventos in-app pós-atribuição</a></td><td>Registra eventos in-app para instalações identificadas como fraudulentas após serem atribuídas a um canal de mídia ou consideradas fraudulentas sem levar em conta a instalação em si.</td><td>Diário</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5" target="_blank">Cliques</a></td><td>Registra cliques realizados por usuários bloqueados pelo Protect360.</td><td>Em tempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5" target="_blank">Postbacks de instalação bloqueados</a></td><td>Registra cópias de postbacks enviados para um canal de mídia, resultando em uma instalação bloqueada.</td><td>Em tempo real</td></tr><tr><td colspan="3"><strong>Postbacks</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5" target="_blank">Postbacks de instalação</a></td><td>Registra eventos de instalação gerados quando um usuário abre o aplicativo pela primeira vez.</td><td>Diário</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5" target="_blank">Postbacks de eventos in-app</a></td><td>Registra postbacks de eventos in-app enviados ao canal de mídia.</td><td>Diário</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5" target="_blank">Postbacks de eventos in-app de retargeting</a></td><td>Registra eventos in-app realizados por usuários durante a janela de reengajamento.</td><td>Em tempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5" target="_blank">Postbacks de conversões de retargeting</a></td><td>Registra eventos in-app realizados por usuários durante a janela de reengajamento.</td><td>Em tempo real</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="Utilização de dados brutos da API Pull">

**Para utilizar dados brutos da API Pull**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#acessando-a-página-de-tokens">Obter o token da API</Anchor>. Um administrador precisa de recuperar o token.
2. Forneça ao seu desenvolvedor o token da API para ser usado no header de autenticação.
3. Forneça aos seus desenvolvedores os parâmetros que eles devem inserir quando fizerem a chamada da API, conforme indicado nas secções seguintes. Os parâmetros determinam o foco do relatório, como ¬ele está organizado e fornecem um período para o relatório.
4. Diga ao seu desenvolvedor para seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">instruções de dados brutos da Pull API</Anchor> no hub do desenvolvedor.

#### Parâmetros

| Parâmetro | Descrição |
| --- | --- |
| início | <ul><li>O intervalo de datas é composto pelos parâmetros `from` e `to`. As datas estão relacionadas com a data da atividade.</li><li>**Receitas de anúncios em dados brutos**</li><li>Exemplo: 01-01-2010 ou 01-01-2010 20:15 (Com parâmetros de horas e minutos disponíveis para relatórios de dados brutos).</li></ul> |
| to (até) | Data final. Quanto ao `from_install time` |
| fonte\_de\_mídia | `media_source`: Para restringir (filtrar) a chamada a uma fonte de mídia específica.<br /><br />Estabeleça os parâmetros `media_source` e `category` da seguinte forma:<ul><li>Para Meta ads, defina a categoria e a fonte de mídia como *facebook*</li><li>Para X Ads, defina a categoria e a fonte de mídia como *twitter*</li><li>Para todas as outras fontes de mídia, defina a categoria como *padrão* e a fonte de mídia como o nome da fonte de mídia.</li></ul><ul><li>Exemplos<ul><li>`media_source=facebook&category=facebook`</li><li>`media_source=abc_example&category=standard`</li></ul></li></ul> |
| maximum\_rows | Número máximo de linhas devolvidas por uma única chamada de API.<ul><li>[Padrão] Se não for enviado nenhum valor, até 200 mil linhas</li><li>200.000: Até 200 mil linhas retornadas</li><li>1.000.000: Até 1 milhão de linhas retornadas</li><li>Exemplo: `maximum_rows=1000000` permite até 1 milhão de linhas.</li></ul> |
| nome\_do\_evento | Filtre eventos in-app por eventos específicos. Selecione vários eventos utilizando uma lista separada por vírgulas.<br /><br />**Exemplo**: `event_name=af_purchase,ftd` |
| reattr | Defina os dados de atribuição de retargeting.<ul><li>[Padrão] Se for false, devolve campanhas de aquisição de usuários (UA).</li><li>Se for true, serão devolvidos dados de atribuição de retargeting.</li><li>**Exemplo**:`reattr=true`</li></ul> |
| additional\_fields | Para obter campos adicionais além dos campos padrão.<br /><br />**Exemplo**: `additional_fields=device_download_time,deeplink_url` |
| símbolos monetários | Moeda de receita e custo<ul><li>[Padrão] Se o parâmetro não for enviado, os dados serão devolvidos em USD. Ou seja, não envie nada e os resultados serão em dólares americanos.</li><li>Se enviar `currency=preferred`, a moeda <Anchor target="_blank" href="/marketers/pt/docs/app-settings#localization-time-zone">específica do aplicativo</Anchor> será utilizada.  Refere-se à moeda definida nas configurações do aplicativo.</li></ul>**Exemplo**: Se a moeda específica do aplicativo for EUR, ao enviar `currency=preferred`os valores serão devolvidos em EUR. |
| Fuso horário | [Padrão] Os dados são retornados utilizando UTC.<ul><li>Para obter dados no fuso horário <Anchor target="_blank" href="/marketers/pt/docs/app-settings#localization-time-zone">específico do aplicativo</Anchor>, adicione `timezone` à chamada, conforme mostrado nesta seção:</li></ul><ul><li>`timezone=[Numerical value]`</li><li>Exemplo: Para o fuso horário UTC+10:00, use `timezone=+10:00` **Atenção:** `+` `-` e `:` precisam ser codificados. Exemplo: +10:00 é codificado para `%2B10%3A00`</li></ul> |
| geo | Filtre os dados por código de país.<br /><br />Limitação: você pode definir apenas um filtro de código de país por chamada de API.<br /><br />Exemplo: `geo=ZA` |
| from\_install time | <ul><li>O intervalo de datas é composto pelos parâmetros `from`e `to`. As datas estão relacionadas com a data da atividade.</li><li>Formato: `yyyy-mm-dd`</li><li>Exemplo: 01-01-2010</li></ul> |
| to\_install\_time | Data final. Relativo a `from_install time` |
| agency | Para restringir (filtrar) a chamada a uma agência específica. |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Campos Protect360">

<Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#postattribution-reports">Consulte o guia de dados brutos do Protect360</Anchor>

</Accordion>

<div id="time-frame-fields" />

<Accordion title="Campos de intervalo de tempo">

Se os resultados da API excederem o máximo, divida o relatório com base em horas e minutos. Aplique o seguinte:

* **from**/**to:** **aaaa-mm-dd hh:mm**
* **Receitas de anúncios em dados brutos**
  * Apenas data = desde o início (00:00) da data selecionada
  * Data e hora = a partir das 00h, inclusive
* Parâmetro **to:**
  * Apenas data = até ao fim (24h) do dia selecionado
  * Data e hora = até, mas sem incluir, a hora apresentada

**Exemplo:** um proprietário de aplicativo tem 1300K de instalações diárias de todas as fontes. Para superar o limite de linha de 1M, o proprietário do aplicativo divide o dia em duas chamadas URI de 12 horas. Consulte a tabela a seguir para opções.

<table><thead><tr><th>Chamada de API</th><th>From </th><th>to (até) </th></tr></thead><tbody><tr><td><strong>Primeira chamada de API</strong> </td><td><p><strong>from</strong>=aaaa-mm-dd</p><p><strong>Exemplo:</strong></p><ul><li> <strong>from</strong> </li><li>Inicia nesta data no começo do dia às 00:00</li></ul></td><td><p><span><strong>to</strong>=aaaa</span><span>a-mm-dd 12:00</span></p><p><strong>Exemplo:</strong></p><ul><li> <strong>to</strong> </li><li> <span>Continua até às 11:59:59, e não às 12:00</span> </li></ul></td></tr><tr><td><p>Opção A: <strong><strong>Segunda chamada de API</strong></strong>  </p><p><strong>Exemplo:</strong> </p><p><code><kbd>&amp;from=2019-12-29 12:00&amp;to=2019-12-29</kbd></code></p><ul><li>Inicia ao meio-dia de 29 de dezembro de 2019</li><li>Termina à meia-noite de 29 de dezembro de 2019</li></ul></td><td><p><strong>from</strong>=aaaa-mm-dd 12:00</p><p><strong>Exemplo:</strong></p><ul><li> <strong>from</strong> </li><li>Começa a partir das 12:00, inclusive</li></ul></td><td><p><strong>to</strong></p><p><strong>Exemplo:</strong></p><ul><li> <span><strong>Exemplo:</strong></span> </li><li>Termina à meia-noite</li></ul></td></tr><tr><td><strong>Opção B: Segunda chamada API</strong></td><td><p><strong>from</strong>=aaaa-mm-dd 12:00</p><p><strong>Exemplo:</strong></p><ul><li> <strong>from</strong> </li><li>Começa a partir das 12:00, inclusive</li></ul></td><td><p><strong>to</strong>=aaaa-mm-dd+1 00:00</p><p><strong>+1</strong> = dia seguinte às 00:00</p><p><strong>Exemplo:</strong></p><ul><li> <span><strong>to</strong>=aaaa</span><span>a-mm-dd </span> </li><li>Significa antes de qualquer tempo ter decorrido em 30 de dezembro.</li></ul></td></tr><tr><td colspan="3"> <span>Observação: </span>use a opção A ou B, pois elas têm os mesmos resultados. </td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="Campos adicionais">

Os campos adicionais do relatório não são incluídos na lista padrão de campos para evitar que novos campos afetem os seus processos atuais de importação e ingestão. Utilize o parâmetro `additional_fields` para obter campos que não são default.

* Liste cada campo apenas uma vez.
* Consulte a <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">lista de campos disponíveis</Anchor>.
* Exemplo: `additional_fields=device_download_time,deeplink_url`

</Accordion>

<div id="default-fields" />

<Accordion title="Campos padrão">

| Campos padrão da Pull API |
| --- |
| Tipo de toque atribuído |
| Tempo de toque atribuído |
| Tempo de instalação |
| Hora do evento |
| Nome do evento |
| Valor do evento |
| Receita do evento |
| Moeda da receita do evento |
| Receita do evento em USD |
| Fonte do evento |
| Recibo validado |
| Parceiro |
| Fonte de mídia |
| Canal |
| Palavras-chave |
| Campanha |
| ID da campanha |
| Conjunto de anúncios |
| Adset ID |
| Anúncio |
| ID do anúncio |
| Tipo de anúncio |
| ID do site |
| ID do subsite |
| Subparâmetro 1 |
| Subparâmetro 2 |
| Subparâmetro 3 |
| Subparâmetro 4 |
| Subparâmetro 5 |
| Modelo de custo |
| Valor de custo |
| Moeda de custo |
| Colaborador 1 Parceiro |
| Fonte de mídia do Colaborador 1 |
| Campanha do Colaborador 1 |
| Tipo de toque do Colaborador 1 |
| Tempo de toque do Colaborador 1 |
| Colaborador 2 Parceiro |
| Fonte de mídia do Colaborador 2 |
| Campanha do Colaborador 2 |
| Tipo de toque do Colaborador 2 |
| Tempo de toque do Colaborador 2 |
| Colaborador 3 Parceiro |
| Fonte de mídia do Colaborador 3 |
| Campanha do Colaborador 3 |
| Tipo de toque do Colaborador 3 |
| Tempo de toque do Colaborador 3 |
| Região |
| Código do país |
| Estado |
| Cidade |
| Código postal |
| DMA (área de mercado designada) |
| IP |
| WiFi |
| Operador |
| Operadora |
| Idioma |
| ID da AppsFlyer |
| ID de publicidade |
| IDFA |
| ID Android |
| Customer User ID |
| IMEI |
| IDFV |
| Plataforma |
| Tipo de dispositivo |
| Versão do sistema operativo |
| Versão do aplicativo |
| Versão do SDK |
| ID da aplicação |
| Nome do aplicativo |
| ID do pacote |
| É retargeting |
| Tipo de conversão de retargeting |
| Lookback de atribuição |
| Janela de reengajamento |
| É atribuição primária |
| User-Agent |
| Referência HTTP |
| URL original |

</Accordion>

## Informações adicionais

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Comentários |
| --- | --- |
| Tipo de token API necessário | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">Token V2.0</Anchor> |
| Acesso da ad network | Não |
| Acesso da agência | Sim |
| Transparência da agência | Sim. No entanto, é importante lembrar que se você tanto usar o filtro de agência quanto os filtros de fonte de mídia, os filtros de fonte de mídia não se aplicarão a agências não transparentes. Isso implica que, para agências não transparentes, todos os dados são incluídos, e não apenas aqueles provenientes das fontes de media filtradas. |
| Moeda específica do aplicativo | Sim |
| Fuso horário específico do aplicativo | Sim |
| Atualização de dados | <ul><li>Equivalente à disponibilidade dos dados no dashboard de visão geral.</li><li>Relatórios atualizados com um atraso de algumas horas:<ul><li>Eventos in-app orgânicos</li></ul></li><li>Relatórios atualizados diariamente:<ul><li>Desinstalações</li><li>Eventos in-app pós-atribuição</li><li>Receita de anúncios</li></ul></li></ul> |
| Dados históricos | Sim.  De acordo com as políticas de <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention">retenção</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/report-generation-quotas-rate-limitations">limite de taxa</Anchor>. |
| Dados não orgânicos | Sim |
| Dados orgânicos | Sim |
| Limite de taxa | Limitações da API para <Anchor target="_blank" href="/marketers/pt/docs/report-generation-quotas-rate-limitations">dados brutos</Anchor>. |
| Limitações de tamanho | <ul><li>As chamadas de API devolvem um máximo de 200K/1M linhas.</li><li>Se um relatório tem exatamente 200K/1M linhas, então suponha que faltam linhas.</li><li>Use o parâmetro maximum\_rows para selecionar o número máximo de linhas.</li><li>Faça várias chamadas de API, usando parâmetros from/to que incluam a hora do dia.</li></ul> |
| install\_date de e install\_date\_to | O intervalo de datas de instalação deve ser anterior ao intervalo de datas de atividades. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Resolução de problemas">

| Sintoma/mensagem | Solução |
| --- | --- |
| O relatório não contém os dados esperados de acordo com o intervalo de tempo selecionado ou há uma discrepância entre o relatório de dados brutos e o relatório de dados agregados. | Verifique se configurou o parâmetro `timezone`. Caso contrário, os dados são enviados usando UTC e não o fuso horário do seu app. |

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Selecionar a ferramenta/API de relatórios correta para entrega de dados</Anchor>

<div data-zendesk-anchors="pull-api-raw-data=dados-brutos-da-pull-api h_01HE7S6WDVJD2XFW498P8FPY7W=dados-brutos-da-pull-api aggregate-performance-reports-available-via-pull-api=relat%C3%B3rios-de-dados-brutos-dispon%C3%ADveis-atrav%C3%A9s-da-pull-api h_01HE7S6WDV59VTP6Z4X790QDRD=relat%C3%B3rios-de-dados-brutos-dispon%C3%ADveis-atrav%C3%A9s-da-pull-api h_01KEVCHC25BDNS9F1GEPBDAW39=raw-data-reports-nonorganic h_01KEVCHJ8TRRM9BYW6C544PNFR=raw-data-reports-organic h_01KEVCHSNGPX2RW917QX4N03A2=retargeting h_01KEVCHYMHGC6VTVSERH611Q8X=ad-revenue-raw-data h_01KEVCJ3GWBZG8SWHZKTRJ6YAX=protect360-fraud h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data parameters=par%C3%A2metros h_01HE7S6WDVF8T4719HWDJH8JN1=par%C3%A2metros h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields additional-information=informa%C3%A7%C3%B5es-adicionais h_01HE7S6WDW9V8XC3CJ0F96EHN0=informa%C3%A7%C3%B5es-adicionais h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=veja-tamb%C3%A9m" />

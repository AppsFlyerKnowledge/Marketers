---
title: Dados modelados da SKAN
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T12:02:02Z'
  edited_at: '2026-08-18T00:32:32Z'
  id: 7086372479505
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/7086372479505
---
> **Visão geral**: os modelos da AppsFlyer agregam dados que os relatórios básicos da SKAdNetwork são incapazes de fornecer.

<div id="overview" />

## Visão geral

Os relatórios da SKAdNetwork (SKAN) podem ser limitados, pois:

* A SKAN se baseia em valores de conversão (CVs) limitados a 6 bits, que resultam em 64 valores possíveis (0-63).
* A Apple às vezes retém o CV real (e retorna dados como "null") para preservar a privacidade do usuário.
* Os dados só estão disponíveis dentro de uma janela de atividades entre 12-72 horas e o lifetime value (LTV) completo não é conhecido.

Os dados modelados da SKAN resolvem esses problemas:

* A AppsFlyer utiliza machine learning, estatísticas Bayesianas, dados reportados pela AppsFlyer e dados da SKAN para modelar pontos de dados ocultos.
* Os anunciantes têm uma visão mais completa da performance do LTV de uma campanha e do aplicativo

**Observação**: quando você altera seu esquema de valores de conversão, são necessários dois dias para que os dados modelados sejam disponibilizados.

<div id="modeled-data-types-and-availability" />

## Tipos de dados modelados e disponibilidade

| Tipo de dados | Disponibilidade | Observações |
| --- | --- | --- |
| Valores de conversão nulos | <ul><li>Visualização no dashboard de visão geral do Single Source of Truth</li><li>Dashboard da SKAN</li><li>Relatório de performance agregada da SKAN</li><li>API de data de chegada de postbacks agregados da SKAN</li></ul> |  |
| LTV de receita | Visualização no dashboard de visão geral do Single Source of Truth | Até 30 dias no relatório do SSOT Data Locker (D7 ainda exibido no dashboard) |
| LTV de evento in-app | Visualização no dashboard de visão geral do Single Source of Truth | A modelagem de LTV de receita está atualmente limitada a 7 dias |
| Geolocalização | Visualização no dashboard de visão geral do Single Source of Truth |  |

<div id="null-conversion-values" />

<Accordion title="Valores de conversão nulos">

Às vezes o valor da conversão (CV) tem um valor nulo porque a Apple retém o CV real para proteger a privacidade do usuário. Na AppsFlyer, um CV nulo é contado como uma instalação. Considere o seguinte:

* Nulo e zero têm significados diferentes:
  * Zero: o usuário instalou o aplicativo, mas não executou nenhuma ação mensurável durante a janela de atividade. Consequentemente, a métrica é precisa e não é modelada.
  * Nulo: não sabemos o que o usuário fez; a Apple reteve o CV.
* Os CVs nulos podem distorcer suas métricas de performance. Para superar a distorção e fornecer uma mensuração mais verdadeira da performance de um app, os valores nulos de conversão são modelados para valores de conversão entre 0-63.
  * A modelagem nula requer um mínimo de dois dias de dados nos últimos 14 dias.

Valores de conversão modelados:

* Usam a distribuição de instalações da SKAN com valores de conversão para modelar instalações nulas. O algoritmo usado para modelar os dados é dinâmico e leva em consideração diversas variáveis. Veja o exemplo a seguir de como isso pode funcionar:
  * Há 100 instalações, 60 são nulas, 10 em que CV=1, 5 em que CV=3 e 25 em que CV=5.
  * Isso significa que, das 40 instalações com valores de conversão, 25% têm CV=1, 12,5% têm CV=3 e 62,5% têm CV=5.
  * As 60 instalações nulas recebem a mesma distribuição modelada: 15 recebem CV=1, 7 recebem CV=3 e 38 recebem CV=5.
* Estão incluídos no painel SKAN e nas métricas da API. As métricas originais e inalteradas, que não incluem dados modelados, estão disponíveis juntamente com essas métricas e são marcadas como *não modeladas*.
* Usam dados dos seguintes níveis de granularidade: aplicativo, canal de mídia, campanha e conjunto de anúncios. Se os dados modelados que usam esses níveis não estiverem disponíveis, o valor N/A é exibido.

Métricas modeladas disponíveis com base no valor de conversão:

* Resultados
* Ocorrências de eventos
* eCPA
* OPCIONAL
* ROI
* ROAS

</Accordion>

<div id="revenue-ltv" />

<Accordion title="LTV de receita">

<Image align="center" alt="modeled_d7.png" src="https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png" />

Os relatórios da SKAN por conta própria só fornecem a receita com base na janela de mensuração da SKAN e na configuração de CVs para receita no Conversion Studio. A modelagem da SKAN pode modelar a receita até 7 dias (168 horas) após a instalação.

**Benefícios**:

Para SKAN versão 3 e anterior, os dados modelados se estendem além do prazo da janela de atividade.

Para SKAN versão 4+:

* Atualização de dados: o LTV de receita fica disponível antes da chegada do segundo postback da SKAN (o atraso do postback é de 24 a 144 horas).
* Mensure mais: você pode usar a configuração de valor aproximado do segundo e terceiro postbacks para outras métricas, como eventos e retenção, e ainda obter dados de LTV de receita por modelagem.
* Enriquecimento de dados: se você usar o segundo postback para mensurar a receita, os dados do postback serão usados para melhorar os dados de LTV de receita modelados e fornecer dados de receita em um nível mais granular do que os três níveis fornecidos pelo postback.

**Considerações**:

* As métricas de LTV de receita são exibidas para aplicativos com a configuração de receita no SKAN Conversion Studio, para receita proveniente de compras in-app e receita publicitária.
* O LTV de receita requer pelo menos 14 dias de dados de receita. Ou seja, se você configurar a receita geral em 1 de novembro de 2022, a primeira data de instalação para a qual os dados modelados estão disponíveis é 14 de novembro de 2022. Os dados são exibidos 8 dias depois disso (22 de novembro de 2022).
* O LTV de receita (atualmente limitado a 7 dias) e outras métricas derivadas estão disponíveis no dashboard do SSOT (nos widgets, gráficos e tabelas) no dia 8 após a instalação da seguinte forma:
  * Receita D[X]
  * ARPU D[X]
  * Lucro bruto D[X]
  * ROI D[X]
  * ROAS D[X]

</Accordion>

<div id="inapp-event-ltv" />

<Accordion title="LTV de evento in-app">

A estrutura da SKAN, por si só, fornece insights limitados sobre eventos in-app pós-instalação. A modelagem da SKAN amplia a análise de eventos in-app e fornece métricas de eventos in-app por até 7 dias pós-instalação.

**Benefícios**:

Para SKAN versão 3 e anterior, os dados modelados se estendem além do prazo da janela de atividade.

Para SKAN versão 4+:

* Atualização de dados: o LTV de eventos in-app fica disponível antes da chegada do segundo postback da SKAN (o atraso do postback é de 24 a 144 horas).
* Meça mais: você pode usar a configuração de valor aproximado do segundo e do terceiro postbacks para medir receita, taxas de retenção etc. e ainda obter métricas de LTV de evento in-app por meio de modelagem.
* Enriquecimento de dados: se você usar o segundo postback para mensurar eventos in-app, os dados do postback serão usados para melhorar a precisão das métricas modeladas de evento in-app, oferecendo uma mensuração mais detalhada do que a fornecida apenas pelo postback aproximado da SKAN.

**Considerações**:

* As métricas estão disponíveis a partir de 7 de março de 2024.
* Os eventos na aplicação (como dimensões) e as suas métricas estão disponíveis apenas para:
  * Eventos configurados no SKAN Conversion Studio.
  * Eventos que ocorreram durante o período da Janela 1 da SKAN.
* As métricas de evento in-app D7 exigem pelo menos 14 dias de dados de eventos in-app. Por exemplo, se você configurar um evento in-app no SKAN Conversion Studio em 1 de janeiro de 2024, a primeira data de instalação para a qual os dados modelados estarão disponíveis será 14 de janeiro de 2024. Os dados são exibidos 8 dias depois disso (22 de janeiro de 2024).
* As métricas de LTV de evento in-app (atualmente limitadas a 7 dias) e outras métricas derivadas estão disponíveis no dashboard do SSOT (nos widgets, gráficos e tabela) no dia 8 pós-instalação da seguinte forma:
  * Usuários únicos do evento D7
  * Conversão de evento D7
  * Event eCPA D7
  * Lucro bruto D7
* A contagem de usuários únicos do evento D2 pode ser maior do que a contagem de D7 se nem todas as datas dentro do intervalo selecionado tiverem alcançado o dia 7, o que restringe as métricas de D7 aos dados da AppsFlyer. A hierarquia de “fonte” ou de "método de atribuição" pode ser adicionada às tabelas para fins de visualização.

</Accordion>

<div id="geo" />

<Accordion title="Geolocalização">

Postbacks SKAN não incluem uma dimensão geográfica. Portanto, os dados SKAN não podem ser agrupados por área geográfica usando apenas postbacks SKAN. No entanto, a AppsFlyer é capaz de modelar geolocalizações de instalação SKAN para fornecer a dimensão geográfica e agrupamento para dados SKAN.

Quando não há dados de atribuição do AppsFlyer Classic disponíveis no nível da campanha, a modelagem de geolocalização não estima nenhuma distribuição geográfica na visualização SSOT.

Geolocalizações modeladas:

* Use ferramentas de machine learning que levam em consideração a distribuição de geolocalização para instalações de campanha atribuídas por meio de outros métodos da AppsFlyer.
* Estão disponíveis por meio da dimensão geográfica no painel SSOT.  
  **Observação**: se você agrupar dados por geolocalização e método de atribuição, poderá ver os dados para cada divisão geográfica entre o modelo AF e os exclusivos do SKAN. Os exclusivos do SKAN são modelados.

Considerações:

* A precisão da modelagem de geolocalização da AppsFlyer é de aproximadamente 90%. Se a geolocalização não puder ser modelada, a instalação do SKAN será agrupada em Nenhum. Nenhum significa que a geolocalização é desconhecida.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H8TZR38AC6P264CGF4PX4SJ5=vis%C3%A3o-geral modeled-data-types-and-availability=tipos-de-dados-modelados-e-disponibilidade 01H8TZR38A2V9ZSSGKHF3XCX0P=tipos-de-dados-modelados-e-disponibilidade 01H8TZR38A4RDX42B7J5X9SPMQ=null-conversion-values 01H8TZR38BG9XEM2FTJADJ27VK=revenue-ltv h_01HTW0XNB2W7JMD9ECZHSN91GZ=inapp-event-ltv 01H8TZR38BSFVDSQCH915ACSYH=geo" />

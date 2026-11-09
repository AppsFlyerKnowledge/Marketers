---
title: >-
  Métricas do iOS no painel Visão geral (métricas da SKAN e da AppsFlyer lado a
  lado)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-08-02T07:18:18Z'
  edited_at: '2026-08-19T00:03:51Z'
  id: 4404976682257
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/4404976682257
---
> **Visão geral**: Veja as métricas das estruturas de atribuição da SKAdNetwork (SKAN) e da AppsFlyer lado a lado no painel Visão geral . Identifique a estrutura com a melhor métrica de desempenho de campanha para você e, em seguida, aproveite-a para obter insights e otimizar campanhas.

**As métricas de atribuição são exibidas lado a lado no painel Visão geral V2.0**

<Image align="center" alt="SBSDB.png" src="https://files.readme.io/550c465c329eac484d2b2e5a65c8f48831c350c3c4b967315e3b2059ab95a36d-4409263804049.png" />

<div id="finding-the-best-ios-14-campaign-performance-metrics" />

## Como encontrar as melhores métricas de desempenho da campanha do iOS 14+

A partir do iOS 14+, as estruturas tanto da atribuição SKAN quanto da <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">Atribuição da AppsFlyer</Anchor> geram métricas de desempenho de campanha. Elas atribuem de maneira diferente, têm características e limitações diferentes, e muitas vezes ocorrem discrepâncias entre elas. Por exemplo, o SKAN não contém métricas de campanhas do Apple Search Ads nem de mídia própria. Por outro lado, as métricas da AppsFlyer de SRNs não incluem instalações de usuários que não consentem. Além disso, o SKAN mede o desempenho durante uma janela inicial pós-instalação de 1 a 3 dias, enquanto a AppsFlyer mede o valor da vida útil (<Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV</Anchor>).

Em lado a lado, você exibe o desempenho da campanha usando os dados fornecidos por ambas as estruturas. Compare as métricas de cada estrutura e decida qual métrica representa melhor o desempenho real da campanha.

**Limitação do compartilhamento de dados**: As métricas SKAN no painel Visão geral não estão disponíveis para ad networks e agências.

<mark>Se as métricas SKAN não aparecerem no painel, você deve atualizar as [configurações da tabela](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#display-skan-metrics-in-the-table).</mark>

A visualização lado a lado fornece insights sobre as métricas da campanha. Use-a para avaliar as métricas de desempenho da campanha em termos de:

* [Precisão](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-precision):
  * Quantas instalações uma campanha trouxe?
  * Por que as métricas da SKAN e da AppsFlyer diferem?
* [Eficácia](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-effectiveness) Quantos usuários converteram e qual é o ROI?
* [Eficiência](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-efficiency) O que é a campanha eCPI?

Este artigo contém orientações baseadas em nosso conhecimento de mercado e observações sobre como interpretar os dados e obter insights acionáveis a partir deles. Considere que o cenário de marketing de cada aplicativo é diferente e valide nossas diretrizes no contexto do seu aplicativo.

**Terminologia**

* **Instalação**:
  * AppsFlyer: Novas instalações e reatribuições
  * SKAN: Novas instalações e novos downloads
* **Real:** Real significa a métrica que melhor representa os dados, mesmo que não inclua todos os dados.
* **Usuários que permitem o rastreamento:** Um usuário do iOS 14+ que concede <Anchor target="_blank" href="/marketers/pt/docs/about-att-and-skan#att-principles">Autorização ATT</Anchor> no editor e no aplicativo anunciado.

<div id="campaign-precision" />

<Accordion title="Precisão da campanha">

| Pergunta | Quantas instalações reais são atribuídas a uma campanha? |
| --- | --- |
| Problema | As métricas de instalação diferem entre as estruturas. Cada estrutura conta algumas das instalações e pode haver sobreposições e discrepâncias entre as estruturas. |
| Remédio | <ul><li>Compare as métricas de instalação das estruturas no nível da campanha.</li><li>A estrutura que reporta a maioria das instalações é considerada a estrutura que tem a métrica mais precisa, mesmo que essa métrica não inclua 100% das atribuições.</li></ul> |
| Exemplo | ![S2Sinstalls.png](https://files.readme.io/9599ef8ac37aa1bc0da46112c1a7d6b4c42f3ff82efda0d0e4b47b8bddc6b52a-4406110225425.png)<br /><br />Na tabela, o framework que traz mais instalações é destacado. Este é o número real de instalações trazidas pela campanha. |
| Observação | Você pode automatizar o processo para estabelecer qual métrica é maior importando a tabela para uma planilha. Use a função @max e a formatação condicional para identificar a estrutura que relata a maioria das instalações. |

| Pergunta | Por que as métricas da SKAN e da AppsFlyer diferem? |
| --- | --- |
| Problema | As métricas de instalação diferem. |
| Explicação | <ul><li>A estrutura da AppsFlyer determina as instalações de acordo com a AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">Modelo de atribuição</Anchor> abrangendo diferentes tipos de campanha e métodos de atribuição, enquanto a SKAN mede as instalações no contexto de campanhas pagas app-to-app.</li><li>Normalmente, as métricas da SKAN de instalações de campanhas de SRN são maiores do que as da AppsFlyer, porque a AppsFlyer registra apenas usuários que consentem.</li><li>No caso de redes não SRN (redes de clique), geralmente há um alinhamento muito mais próximo entre as métricas por estrutura.</li></ul> |

</Accordion>

<div id="campaign-effectiveness" />

<Accordion title="Eficácia da campanha">

| Pergunta | Quantos usuários converteram e qual é o ROI? |
| --- | --- |
| Considerações | <ul><li>Determinar as métricas de receita e taxa de conversão requer que o desempenho do usuário seja medido ao longo do tempo.</li><li>A SKAN limita a mensuração entre 12 a 72 horas após a instalação, enquanto a mensuração da AppsFlyer é ilimitada (LTV).</li><li>A atribuição da AppsFlyer contém apenas métricas de usuários que consentiram.</li></ul> |
| Remédio | Considere se as métricas de atribuição da AppsFlyer representam com precisão toda a população de usuários (incluindo usuários relatados via SKAN). Em caso afirmativo, use-as para extrapolar métricas de eficácia da campanha, como ROI e métricas de taxa de conversão.<br /><br />**Para calcular o número de usuários que converteram:**<ol><li>Use a métrica de taxa de conversão da AppsFlyer (por evento).</li><li>Multiplique a taxa de conversão pelo número real de usuários, derivado conforme descrito na seção de precisão da campanha.</li></ol>**Para calcular a receita e o ROI da campanha:**<ol><li>Derive o número real de usuários (a) conforme descrito na seção de precisão da campanha.</li><li>Use a métrica ARPU (b) fornecida pela atribuição da AppsFlyer.</li><li>Calcule a receita da campanha usando a fórmula: a * b</li><li>Use o custo da campanha conforme exibido no painel.</li><li>ROI = (receita da campanha - custo da campanha) / (custo da campanha * 100)</li></ol> |
| Exemplo | **Calculando ROI**<br /><br />![SBSCost.png](https://files.readme.io/052c862e0a93c4e938f84b22e04e8b088bf50acbf047b821ca6cd20f5b9eae57-4409270882577.png)<br /><br />**Exemplo de cálculo de ROI para a campanha a:**<ol><li>Suposto número de usuários 2000</li><li>Métrica ARPU no painel: $ 0,76</li><li>Receita da campanha = 2000 * $0,76 = $1520</li><li>Custo da campanha: $905,88</li><li>ROI= ($1520 - $905,88) / ($905,88 * 100) = 68%</li></ol> |
| Observação | Use sua ferramenta BI de análise de produto para comparar o desempenho dos usuários que consentiram com toda a população de usuários do aplicativo. Se os resultados forem diferentes, você deverá ajustar o cálculo da solução para levar isso em consideração. |

</Accordion>

<div id="campaign-efficiency" />

<Accordion title="Eficiência da campanha">

| Pergunta | Qual é o eCPI real da campanha? |
| --- | --- |
| Problema | As métricas relacionadas ao custo da campanha, como o eCPI, são enganosas porque dependem de um número preciso de usuários. |
| Remédio | <ol><li>Derive o número real de usuários (a) conforme descrito na seção de precisão da campanha.</li><li>Calcule o eCPI usando a seguinte fórmula: eCPI = custo / (a)</li></ol> |
| Exemplo | ![mceclip1.png](https://files.readme.io/98fc80d1e995ba8ef0cce267fa12f22d48a77d7e25db4add1108144c6de7136d-4406111715217.png)<ul><li>As instalações reais são determinadas usando a estrutura com mais instalações.</li><li>O eCPI é calculado usando a fórmula: custo/número de instalações.</li></ul> |

</Accordion>

<div id="using-side-by-side" />

## Usando lado a lado

<div id="principles" />

<Accordion title="Princípios">

* Contém instalações relatadas por ambas as estruturas de atribuição
* Use a visualização unificada, na Visão geral V2.0, para garantir que todos os dados disponíveis no contexto de uma campanha sejam exibidos e não sejam ocultados inadvertidamente pela filtragem
* Os dados do SKAN são os mesmos disponíveis no painel do SKAN
* Para reduzir as discrepâncias devido a diferenças de tempo entre as estruturas, defina um intervalo de datas no painel da seguinte maneira:
  * Duração: Mínimo 7 dias
  * Data mais recente:
    * 3 a 5 dias antes da data atual. O intervalo depende da sua janela de atividade
    * Se você executar campanhas do Google Ads, a data mais antiga precisará ser 8 dias antes da data atual

</Accordion>

<div id="display-skan-metrics-in-the-table" />

<Accordion title="Exibir métricas SKAN na tabela">

**Para exibir métricas SKAN na tabela**:

1. Clique em ⚙ (configurações da tabela).   
   A janela para selecionar métricas é aberta.

   <Image align="center" alt="SelectSkan.png" src="https://files.readme.io/6b60fa8e2d10a1b61b1bfb4b7a968adb5ee16086d80c9cc8bc097b8e8ed77b51-4408473842833.png" />
2. Clique em **Atribuição SKAN**.
3. Clique em **Instalações SKAN**.
4. Clique em **Receita SKAN**.
5. [Opcional] Para adicionar ou remover eventos in-app:
   1. Selecione eventos in-app.
   2. Adicione ou remova os eventos in-app necessários.
6. Clique em Aplicar.   
   As métricas selecionadas e os eventos in-app são exibidos.

</Accordion>

<div id="timerelated-differences" />

<Accordion title="Diferenças relacionadas ao tempo">

<table><thead><tr><th>Diferença</th><th>A AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>Histórico de dados</td><td><p>Disponível; sem limitação</p></td><td><p>Disponível; sem limitação. </p></td></tr><tr><td>Fuso horário</td><td><p>Fuso horário específico do aplicativo</p></td><td>UTC </td></tr><tr><td>Atualização dos dados </td><td>Atualiza continuamente com uma latência de até 60 minutos</td><td><p>A<span>tualiza diariamente às 08:00 UTC.</span> </p><p><span>A latência depende da duração da janela de atividade. Padrão: 2-5 dias; no caso de campanhas executadas pela campanha do Google Ads, até 13 dias.</span></p></td></tr><tr><td>Data de instalação</td><td>Data em que a instalação ocorreu </td><td>Derivado do horário de chegada do postback. (1) </td></tr><tr><td>Duração da mensuração</td><td>Ilimitado; Baseado em LTV</td><td><p>Limitado à duração da janela de atividade de 12 a 72 horas. Padrão = 24 horas</p></td></tr><tr><td>Janela de lookback de atribuição</td><td><ul><li>Determinado pelo anunciante ou SRN</li><li>Clique para abrir: 7 dias</li></ul></td><td><ul><li>Determinado pela Apple</li><li>Click_to_download: 30 dias</li><li>Download-to-open: 60 dias</li></ul></td></tr><tr><td colspan="3"><p>Observações</p><p>(1) Atualizações de dados do Google Ads com um atraso de até 13 dias.</p></td></tr></tbody></table>

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Custo, cliques e impressões">

As ad networks fornecem métricas de custo, cliques e impressões para a AppsFlyer, que são comuns a ambas as estruturas. Não há segregação dessas métricas por estrutura.

No caso de métricas de custo, aplica-se o seguinte:

* Atualiza 6 vezes ao dia, em média a cada 4 horas.
* A AppsFlyer registra o primeiro engajamento (clique ou impressão) associado a uma campanha; depois disso, o custo da campanha associado ao engajamento é exibido.
* Como as instalações da SKAN são reportadas de 72 a 120 horas após a abertura do primeiro aplicativo, é provável que você veja as métricas de custo alguns dias antes de serem associadas às instalações.
* Para instalações do Google Ads, o atraso pode ser de até 13 dias.

</Accordion>

<div id="data-scope-differences" />

<Accordion title="Diferenças de escopo de dados">

| Diferença | A AppsFlyer | SKAN |
| --- | --- | --- |
| Plataforma | Tudo | /docs/ctv-pc-and-console-platform-attribution-concepts |
| Tipos de atribuição | <ul><li>Instalações</li><li>Reengajamentos</li><li>Reatribuições</li></ul> | <ul><li>Instalações</li><li>Redownloads</li></ul> |
| Receita de anúncios | Disponível | <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">Limitado; depende do parceiro de mediação</Anchor>. |
| Apple Search Ads | Disponível | Não aplicável à atribuição SKAN |
| Mídias próprias | Disponível | Não aplicável à atribuição SKAN |
| web-to-app | Disponível | Disponível para atribuição SKAN 4 |
| Moeda | Moeda específica do aplicativo | USD |

</Accordion>

<div id="matching-considerations" />

<Accordion title="Considerações sobre correspondência">

<table><thead><tr><th>Consideração</th><th>A AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>Transparência da agência</td><td>Com suporte.</td><td><p>Atribuído ao canal de mídia mídia que traz a instalação. As agências podem instruir as fontes de mídia a prefixar os nomes das campanhas com seus <em><a href="/partners/pt/docs/getting-started-agency-onboarding" target="_blank">prt</a>,</em> nesse caso, você pode identificar o tráfego direcionado pela agência.</p></td></tr><tr><td>Alterações no nome da campanha</td><td><ul><li>Com suporte.</li><li>O nome mais recente reportado pela ad network determina o nome da campanha usado para todas as instalações associadas a um determinado ID de campanha. Isso inclui instalações gravadas anteriormente. </li></ul></td><td><ul><li>Não compatível</li><li>O nome da campanha reportado quando o usuário instala o aplicativo é usado. Isso não muda com o tempo. Consequentemente, vários nomes podem ser associados a um determinado ID de campanha. </li></ul></td></tr><tr><td>Dimensões compatíveis</td><td>Sem limitação</td><td><p><strong>Disponível</strong>: Geolocalização, anúncio, ID do anúncio, canal, conjunto de anúncios, ID do site.</p><p><strong>Agência:</strong> Atualmente não.</p><p>Se você selecionar uma dimensão que não é compatível, os dados SKAN serão exibidos como nenhum.</p></td></tr><tr><td>Métricas de instalação de SRN</td><td>Limitado a usuários que consentem; como resultado, é provável que as métricas reportadas pela AppsFlyer sejam menores do que as métricas reportadas pela SKAN e as métricas fornecidas pela própria SRN. </td><td>Todas as instalações atribuídas ao SKAN. Geralmente maior do que a métrica da AppsFlyer. </td></tr><tr><td>Campanhas ocultas do SKAN</td><td colspan="2"><p>A tabela no painel contém um número limitado de linhas. As linhas restantes são combinadas na linha designada <em>Outros</em>.</p><p>Para exibir um detalhamento dessa linha, exporte a tabela inteira para uma planilha. </p></td></tr></tbody></table>

</Accordion>

<div id="dimensions-available" />

<Accordion title="Dimensões disponíveis">

As seguintes dimensões estão disponíveis na visualização lado a lado:

* Canal de mídia
* Nome da campanha
* ID da campanha
* Data
* Tipo de atribuição

</Accordion>

<div data-zendesk-anchors="finding-the-best-ios-14-campaign-performance-metrics=como-encontrar-as-melhores-m%C3%A9tricas-de-desempenho-da-campanha-do-ios-14 h_01HYAQAR84BP9MRRXP7BPPDJ4N=como-encontrar-as-melhores-m%C3%A9tricas-de-desempenho-da-campanha-do-ios-14 h_01HYAQAR856G6VARSH746SJB5Z=campaign-precision h_01HYAQAR856JT2JX28SE3QY7VZ=campaign-effectiveness h_01HYAQAR85GZN1RZYNV2MV7DAP=campaign-efficiency using-sidebyside=usando-lado-a-lado h_01HYAQAR85FY6K8R574GWFQW91=usando-lado-a-lado h_01HYAQAR85Z09SXSE8JGTG5AMF=principles h_01HYAQAR85V6CD29T9AY9XYX0Z=display-skan-metrics-in-the-table h_01HYAQAR85QSTB8QZPGMEV6MR9=timerelated-differences h_01HYAQAR85A03KNAHC5TEAZAZK=cost-clicks-and-impressions h_01HYAQAR85SPYQKDFP3CRGW5FN=data-scope-differences h_01HYAQAR85FSAXQ25X16N6XQEW=matching-considerations h_01HYAQAR85XF7CEG6F7PC44F1C=dimensions-available" />

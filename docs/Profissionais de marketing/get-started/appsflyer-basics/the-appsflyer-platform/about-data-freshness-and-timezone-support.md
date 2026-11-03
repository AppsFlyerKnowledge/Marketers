---
title: Atualização de dados e suporte a fuso horário
metadata:
  keywords:
    - Reports
    - Advertisers
    - Agencies
    - Ad Networks
    - timezone
    - data freshness
    - data
    - Developers
    - Gray
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2018-02-19T15:57:01Z'
  edited_at: '2026-10-29T01:13:00Z'
  id: 360000310629
  locale: pt
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/pt/articles/360000310629
---
> **At a glance:** Visão geral: a atualização dos dados é o período de tempo entre a ocorrência do evento e a disponibilidade de dados na plataforma.

**Fusos horários**

![TimeZoneMap.jpg](https://files.readme.io/eddfa3df4d43fed82ba5e867eb1278466d1ba51f9fbc2970f62fa61c6659d340-360005463738.jpg)

## Atualização de dados e compatibilidade com fusos horários específicos do aplicativo

### Atualização dos dados

A plataforma da AppsFlyer utiliza diferentes [tipos de atualização de dados,](/docs/about-data-freshness-and-timezone-support#data-freshness-types) como diária e em tempo real. Eles são usados para apresentar e disponibilizar dados. Cada um tem sua própria [taxa de atualização de dados](/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support).

Exemplo: taxas de atualização de dados no painel Eventos:

* Métrica KPI: em tempo real
* KPI médio: diário

### Fusos horários

Na plataforma da AppsFlyer, um dia começa às 00:01 e termina às 24:00. O fuso horário padrão é UTC (GMT). Você pode modificar o padrão definindo um <Anchor target="_blank" href="/marketers/pt/docs/changing-app-time-zone-settings">fuso horário específico do aplicativo.</Anchor>

<Accordion title="Princípios de data e fuso horário">

O horário UTC é constante e não tem horário de verão/inverno.

Hemisférios

* Leste: os fusos horários designados como UTC+ são aqueles localizados a leste do UTC.
* Oeste: os fusos horários designados como UTC - são aqueles localizados a oeste do UTC.

#### Fuso horário específico do aplicativo

Você pode definir um fuso horário específico do aplicativo. Isso significa que os dados são agrupados em dias usando a hora local em vez de UTC.

Exemplo:

**Pequim:** se o fuso horário específico do aplicativo estiver definido como Beijing (UTC +8), o dia começará às 16:01 UTC e terminará às 16:00 UTC do dia seguinte.

**Los Angeles**: se o fuso horário específico do aplicativo estiver definido como Los Angeles (UTC -8), o dia começará às 08:01 UTC e terminará às 08:00 UTC do dia seguinte.

#### Diretrizes de fuso horário

* Alinhe o fuso horário específico do aplicativo com o fuso horário definido com outros parceiros de atribuição, como o Google e o Meta ads.
* Se você tiver mais de um aplicativo, recomendamos que você configure todos os aplicativos para o mesmo fuso horário. Para ver a configuração de fuso horário de um aplicativo, vá para **Configurações** > **Configurações do aplicativo.**
* A maioria dos relatórios e ferramentas de extração de dados é compatível com fusos horários específicos do aplicativo. Isso inclui relatório de diversos aplicativos se todos os aplicativos estiverem definidos no mesmo fuso horário específico do aplicativo.

#### Processamento diário

Alguns relatórios e listas suspensas são processados uma vez por dia, isso é conhecido como atualização diária ou processamento diário. Estes são os princípios do processamento diário:

* Os dados pertencentes a um dia específico, por exemplo, segunda-feira, são coletados em um *intervalo*. O dia começa às 00:01 e termina às 24:00 usando o horário específico do aplicativo.
* Os dados recebidos até duas horas após a meia-noite são incluídos no intervalo do dia. Os dados recebidos até às 02:00 de terça-feira estão incluídos no intervalo de segunda-feira.
* Às 02:00, horário local, o intervalo é fechado e nenhum dado pode ser adicionado a ele.
* Os dados recebidos após as 02:00 são colocados no próximo bucket disponível, independentemente da data do evento.
* O processamento diário do período fechado começa duas horas após a meia-noite UTC, independentemente do fuso horário específico do aplicativo. Por uma questão de simplicidade, afirmamos que o processamento começa à meia-noite UTC. Isso significa que, dependendo do fuso horário local, o repositório precisa esperar até a meia-noite UTC antes do início do processamento.

**Fuso horário do hemisfério oriental e UTC**:

![[É NECESSÁRIO TEXTO ALTERNATIVO DESCRITIVO — CONFIRMAR]: diagrama dos tempos de espera do processamento diário para os fusos horários do hemisfério oriental](https://files.readme.io/cbea9d910695b39f59b342da6f56fa51df76afc910c4eea60f6dd49fbee2a0d6-8272818122769.png)

* Podem passar até 11 horas desde o término do dia (hora local) até o início do processamento. Por exemplo:
  * Pequim (UTC+8): Necessidade de esperar oito horas antes do início do processamento
  * Berlim (UTC +1): Necessidade de esperar uma hora antes do início do processamento
  * UTC: Sem tempo de espera.
* Dependendo do tipo de relatório, os dados ficam disponíveis 8 a 20 horas após o início do processamento. Por exemplo, os dados de Beijing ficam disponíveis a partir das 16:00, horário local. Os dados de Berlim ficam disponíveis a partir das 09:00.

**Hemisfério ocidental:**

![[É NECESSÁRIO TEXTO ALTERNATIVO DESCRITIVO — CONFIRMAR]: diagrama dos tempos de espera do processamento diário para os fusos horários do hemisfério ocidental](https://files.readme.io/ac5e3046b3f55916bb73732801c7e0bdef714cc45b89b6c4d70bbc2009cd64c8-8272698121489.png)

* Podem passar até 23 horas desde o término do dia até o início do processamento. Por exemplo:
  * Los Angeles (UTC -8): necessário esperar 16 horas antes do início do processamento
  * Nova York (UTC -5): necessário esperar 19 horas antes do início do processamento
* Dependendo do tipo de relatório, os dados processados ficam disponíveis 8 a 20 horas após o início do processamento. Por exemplo, os dados de Los Angeles ficam disponíveis a partir das 00:01, horário local, dois dias após o evento. Os dados de Nova York ficam disponíveis a partir das 03:01, horário local, dois dias após o evento.
* Exemplo:
  * Os eventos acontecem na segunda-feira, horário de Los Angeles (UTC -8), o processamento diário começa à meia-noite UTC de terça-feira. Estamos em Los Angeles, terça-feira, 16:01.
  * Oito horas depois, na quarta-feira 00:01, horário de Los Angeles, o processamento de dados está concluído. Em termos práticos, os dados de segunda-feira ficam disponíveis para os anunciantes em Los Angeles quando eles começarem a trabalhar na manhã de quarta-feira.

</Accordion>

<Accordion title="Tipos de atualização de dados">

| Classificar | Disponibilidade | Descrição |
| --- | --- | --- |
| Contínuo (também chamado de tempo real) | 15 a 60 minutos apósa ocorrência do evento | O processamento de dados é contínuo. Este termo o distingue do processamento em lote que ocorre, por exemplo, diariamente. Os dados contínuos são atualizados com um atraso de 15 a 60 minutos após a ocorrência de um evento da seguinte forma:<ul><li>Atribuições (instalações, reatribuições e reengajamentos): 15 a 30 minutos.</li><li>Eventos in-app: 30 a 60 minutos.</li></ul> |
| Relatório em tempo real | Poucos minutos depois de solicitar um relatório | Os dados são atualizados minutos após a ocorrência do evento. |
| Diariamente | **Zona UTC**: 8 horas após a meia-noite UTC do dia do evento<br /><br />**Hemisfério oriental**: 9 a 20 horas após a meia-noite UTC no dia do evento.<br /><br />Hemisfério ocidental: **Zona UTC**: 21 a 32 horas após a meia-noite UTC no dia do evento. | <ul><li>Os dados são processados diariamente</li><li>A disponibilidade desses dados varia de acordo com o fuso horário específico do aplicativo</li><li>Os tipos de dados não compatíveis com fusos horários específicos do aplicativo usam o horário UTC</li><li>Os horários de disponibilidade de dados podem variar do dia a dia ou conforme indicado em artigos específicos</li></ul> |
| EOD (fim do dia) | Diariamente no final do dia, fuso horário específico do aplicativo | No final do dia do calendário. Ou seja, 00:01 do dia seguinte. Exemplo: os dados registrados na segunda-feira estão disponíveis a partir de terça-feira às 00:01, independentemente do fuso horário específico do aplicativo. |
| Intradiário (durante o dia) | A cada 4 horas, em média | <ul><li>Os dados são coletados seis vezes ao dia, em média a cada quatro horas.</li><li>Os dados de cliques e impressões SRN para clientes sem ROI360 são coletados 3 vezes ao dia.</li><li>Os dados ETL de custo são enviados 4 vezes por dia, em média a cada 6 horas.</li></ul> |
| Ad revenue | Depende do tipo de integração e do relatório | <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#data-freshness">Veja o artigo sobre receita publicitária para maiores detalhes</Anchor>. |
| PBA Diariamente | Os dados ficam disponíveis de 11 a 12 horas após o final do dia UTC | <ul><li>O dashboard e os relatórios do PBA são atualizados [diariamente](/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles) usando o fuso horário UTC.</li><li>O processamento diário inclui eventos recebidos durante o dia anterior.</li><li>Durante os primeiros sete dias após a conversão, o PBA pode identificar eventos adicionais relacionados a uma conversão. Isso pode alterar os KPIs e a atribuição da fonte de mídia retroativamente.</li><li>Após sete dias, os caminhos fecham e não ocorrem mais mudanças.</li><li>Os relatórios de dados brutos incluem o campo *final\_data.* Quando os dados verdadeiros são finais.</li><li><Anchor target="_blank" href="/marketers/pt/docs/using-pba-dashboards#traits-and-limitations">Exemplo detalhado</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Consulte o tempo</Anchor> desde o horário de chegada do postback até a disponibilidade de dados em painéis e relatórios. | Postbacks recebidos em um determinado dia são processados no final do dia UTC. Os dados ficam disponíveis até às 11:00 UTC do dia seguinte. Ou seja, os postbacks do iOS recebidos na segunda-feira ficam disponíveis em relatórios e painéis na terça de manhã. Da mesma forma, os postbacks para parceiros são enviados na terça de manhã.<br /><br />A data de instalação nos relatórios e painéis é derivada da hora de chegada do postback, conforme detalhado no <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#activity-window">artigo do estúdio de conversão SKAN</Anchor>. |
| Data Locker Diariamente | Os dados ficam disponíveis de 8 a 10 horas após o final do dia UTC | <ul><li>Os dados são processados diariamente.</li><li>Os dados estão contidos na pasta h=23 na data do evento. Por exemplo, os dados de segunda-feira estão disponíveis na pasta h=23 de segunda-feira na terça-feira, das 08:00 às 10:00 UTC.</li><li>Os dados da SKAN podem chegar um pouco mais tarde (consulte as informações da SKAN acima).</li></ul> |

</Accordion>

<Accordion title="Atualização de dados e compatibilidade com fuso horário">

<table><thead><tr><th>Dados relacionados</th><th>Como é apresentado</th><th>Taxa de atualização dos dados<br/>Taxa de atualização de dados(consulte a seção anterior para obter a chave para as taxas)</th><th>Dados aparecem usando o fuso horário específico do aplicativo</th></tr></thead><tbody><tr><td>Instalações</td><td>KPI</td><td><p>Contínuo</p><p>Exceções a serem observadas:</p><ul><li>Os alertas do Protect360 são atualizados no horário UTC diário.<ul><li>Atualizado diariamente às 16:00 UTC</li></ul></li></ul></td><td><span>✓</span></td></tr><tr><td>Sessões, cliques, impressões, usuários leais</td><td>KPI</td><td><ul><li>Links de atribuição: Contínuo</li><li>SRNs: Intradiário</li></ul></td><td><span>✓</span></td></tr><tr><td>Eventos de receita in-app</td><td>KPI</td><td>Contínuo</td><td><span>✓</span></td></tr><tr><td>Ad revenue</td><td>KPI</td><td>Ad revenue</td><td><span>✓</span></td></tr><tr><td>Gastos com anúncios (custo)</td><td>KPI</td><td><ul><li>Link de atribuição: Contínuo (máximo até 2 horas após o clique)</li><li>API Intradiário</li><li>Ingestão de gastos com anúncios Até 4 horas após a ingestão</li></ul></td><td><span>✓</span></td></tr><tr><td>Desinstalações</td><td>KPI</td><td>diariamente. A AppsFlyer executa ping das lojas de aplicativos a cada 24 horas. A hora do evento da desinstalação representa a hora em que a AppsFlyer executou ping na notificação push silenciosa e descobriu que o aplicativo foi desinstalado. Este não é o horário real da desinstalação.</td><td><span><strong>X</strong></span></td></tr><tr><td>Eventos in-app na interface</td><td>Lista suspensa</td><td><p>Os nomes de eventos in-app exibidos nas listas suspensas são atualizados diariamente.</p><p>Isso não afeta a taxa de atualização dos dados em si.</p><p><strong>Exemplos:</strong> listas suspensas de eventos in-app na Push API, em dashboard e em audiências.</p></td><td><span>✓</span></td></tr><tr><td>Dahsboard de Visão Geral</td><td>Página</td><td>Contínuo</td><td><span>✓</span></td></tr><tr><td>Painel do Protect360</td><td>Página</td><td>Diariamente</td><td> <span>✓ </span>(1)</td></tr><tr><td>Dashboard da SKAN</td><td>Página</td><td>Diariamente</td><td><span><strong>X</strong></span></td></tr><tr><td>Página de atividade</td><td>Página</td><td><ul><li>KPIs: Contínuo</li><li>Médias: à meia-noite do fuso horário específico do aplicativo</li></ul></td><td><p><span>✓</span></p><p>Exceção: Os dados MAU são UTC</p></td></tr><tr><td>Página de eventos</td><td>Página</td><td>Contínuo</td><td><span>✓</span></td></tr><tr><td> </td><td> </td><td>(Essa linha foi deixada em branco intencionalmente)</td><td> </td></tr><tr><td>Retenção</td><td>Página</td><td><p>Os KPIs de retenção estão disponíveis com granularidade diária e semanal. A atualização dos dados para cada um é diferente.</p><ul><li>KPIs de retenção diários: Diariamente</li><li>KPIs de retenção semanal: A semana começa na segunda-feira e termina no domingo. A retenção é calculada na segunda-feira às 12:00 UTC. A falta de compatibilidade com fuso horário específico do aplicativo para o KPI semanal resulta em uma diferença insignificante.</li></ul></td><td><p>Diariamente: <span>✓</span></p><p>KPIs de retenção semanal: <strong><span>x</span></strong></p></td></tr><tr><td>Coorte</td><td>Página</td><td>Contínuo</td><td> <span>✓ </span>(2)</td></tr><tr><td>Painel Personalizado</td><td>Página</td><td>Contínua</td><td> <span>✓ </span>(3)</td></tr><tr><td>Audiências</td><td>Página</td><td><ul><li>As atualizações são enviadas aos parceiros a cada 24 horas.</li><li>A base de usuários é atualizada diariamente e armazena até 90 dias de dados do dispositivo</li></ul></td><td><span>✓</span></td></tr><tr><td>Página de informações do SDK</td><td>Página</td><td>Diariamente</td><td><span><strong>X</strong></span></td></tr><tr><td>Dados de exportação</td><td>Página</td><td><p>Contínuo</p><p>Live Alerts</p><ul><li>Dados brutos de receita de anúncios: Diariamente</li><li>Protect360:<ul><li>Relatórios agregados: Diariamente</li><li>Dados brutos bloqueados: Contínuo</li><li>Dados brutos pós-atribuição: Diariamente</li></ul></li><li>Eventos in-app orgânicos: Atualização com um atraso de várias horas.</li></ul></td><td><span>✓</span></td></tr><tr><td>Extrair API</td><td>API</td><td>A atualização dos dados da Pull API é a mesma que os dados de exportação.</td><td><p><span>✓</span></p><p><span>UTC padrão</span></p></td></tr><tr><td>Pivot</td><td>Página</td><td>Diariamente</td><td><p><span>✓</span></p><p>KPI regulares:</p></td></tr><tr><td>Master API</td><td>API</td><td>Diariamente</td><td> <span>✓ </span>(3)</td></tr><tr><td>Relatório do Data Locker</td><td>API</td><td>Conforme especificado no artigo do Data Locker.</td><td><p><span><strong>X</strong></span></p><p><span><strong>UTC</strong></span></p></td></tr><tr><td>Postbacks</td><td>API</td><td>Contínuo</td><td>N/D</td></tr><tr><td>API de push</td><td>API</td><td>Contínuo (4)</td><td><p><span>✓</span></p><p><span><strong>Ambos</strong></span></p></td></tr><tr><td>Eventos in-app servidor para servidor</td><td>API</td><td>Contínuo</td><td>N/D</td></tr><tr><td colspan="4"><p>Observações:</p><p>(1) Todos os aplicativos para os quais o usuário tem permissão devem usar o mesmo fuso horário específico do aplicativo. Caso contrário, o fuso horário será revertido para UTC.</p><p>(2) Consulte <a href="./cohort-and-retention-dashboard#traits-and-limitations" target="_blank">as características e limitações de coorte</a> quando o fuso horário for revertido para UTC.</p><p>(3) Todos os aplicativos selecionados devem usar o mesmo fuso horário específico do aplicativo. Caso contrário, o fuso horário será revertido para UTC.</p><p>(4) Os dados do relatório SKAN estarão disponíveis diariamente entre 08:00 e 10:00 UTC.</p></td></tr></tbody></table>

> 📘 **Exceção: métricas de cohort e atividade do My Dashboards**
>
> Estas métricas têm sua própria frequência de atualização dos dados:
>
> * **Métricas de cohort (apps web, CTV, PC e console):** Os dados do mesmo dia ficam disponíveis no dia seguinte, após a conclusão do processamento diário.
> * **Métricas de atividade (atribuição clássica):** A atualização dos dados depende do tipo de aplicativo:
>   * **Apps web:** até 3,5 horas
>   * **Apps de CTV, PC e console:** até 50 minutos
>   * **Apps mobile:** até 70 minutos
> * **Atribuição cross-platform:** A atualização se aplica apenas à atribuição clássica. A atualização dos dados cross-platform no My Dashboards continua diária.
>
> Veja <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#traits-and-limitations">características e limitações do My Dashboards</Anchor> para mais detalhes.

</Accordion>

<div data-zendesk-anchors="data-freshness-and-support-for-appspecific-time-zones=atualiza%C3%A7%C3%A3o-de-dados-e-compatibilidade-com-fusos-hor%C3%A1rios-espec%C3%ADficos-do-aplicativo 01EDBBPAH96ADJ56FRNB34K3VB=atualiza%C3%A7%C3%A3o-de-dados-e-compatibilidade-com-fusos-hor%C3%A1rios-espec%C3%ADficos-do-aplicativo data-freshness=atualiza%C3%A7%C3%A3o-dos-dados 01EDBBPAH9M5KQRXJ1TNN3RJAX=atualiza%C3%A7%C3%A3o-dos-dados time-zones=fusos-hor%C3%A1rios 01EDBBPAH92JJVVGXN61N4SV89=fusos-hor%C3%A1rios appspecific-time-zone=fuso-hor%C3%A1rio-espec%C3%ADfico-do-aplicativo 01EDBBPAH9WHDY875Y913PV00Z=fuso-hor%C3%A1rio-espec%C3%ADfico-do-aplicativo timezone-guidelines=diretrizes-de-fuso-hor%C3%A1rio 01EDBBPAH9TRH8HBB0JAX2369H=diretrizes-de-fuso-hor%C3%A1rio daily-processing=processamento-di%C3%A1rio 01EDBBPAH98F0641D934W9NJD8=processamento-di%C3%A1rio h_01M2MJESA4EG1BEVM5T6N9FH0D=exce%C3%A7%C3%A3o-m%C3%A9tricas-de-cohort-e-atividade-do-my-dashboards" />

---
title: Compare os dados de receita de anúncios do ROI360 com os dados dos parceiros
metadata:
  keywords:
    - ad revenue
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2023-10-11T17:40:51Z'
  edited_at: '2026-08-19T00:01:57Z'
  id: 19287636823953
  locale: pt
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/pt/articles/19287636823953
---
> **Em resumo:** Compare os dados de receita de anúncios do ROI360 da AppsFlyer com os dados dos parceiros de mediação e de aquisição de usuários.

Os dados precisam ser recebidos e processados antes de ficarem disponíveis nos dashboards e relatórios. O tempo que os dados levam para ficar disponíveis depende do pacote ROI360 que você tem, bem como do tipo de integração do parceiro, da atualização dos dados e do tipo de relatório.

As seções a seguir explicam quando e como comparar dados de receita de anúncios do ROI360 nos relatórios da AppsFlyer com os dados que você pode ver nos dashboards e relatórios dos parceiros.

<div id="comparing-appsflyer-data-with-mediation-partner-data" />

<Accordion title="Compare os dados da AppsFlyer com os dados do parceiro de mídia">

| Tipo de integração | Tipo de dados | Quais dados podem ser comparados entre si |
| --- | --- | --- |
| S2S API | Nível do dispositivo | <ul><li>Compare a receita total exibida no dashboard de atividade da AppsFlyer ou a receita total exibida nos relatórios de receita de anúncios de versão única no Data Locker com os dados de receita total do parceiro de mídia.</li><li>Espere até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados, para que tanto a AppsFlyer quanto o parceiro de mídia tenham tempo para processar os dados.</li><li>Não compare as contagens de eventos de receita de anúncios (reportadas em eventos af\_ad revenue) com as contagens de impressões.</li></ul> |
| SDK | Nível do dispositivo | <ul><li>Compare a receita total exibida no dashboard de atividade da AppsFlyer ou a receita total exibida nos relatórios de receita de anúncios de versão única no Data Locker com os dados de receita total do parceiro de mídia.</li><li>Espere até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados, para que tanto a AppsFlyer quanto o parceiro de mídia tenham tempo para processar os dados.</li><li>Não compare as contagens de eventos de receita de anúncios (reportadas em eventos af\_ad revenue) com as contagens de impressões.</li></ul>**Observação**: Como os dados de receita de anúncios são mutáveis e é possível que nem todos os usuários do aplicativo tenham atualizado para a versão mais recente com o conector SDK de receita de anúncios, comparar os dados da AppsFlyer com os dados do parceiro de mídia pode resultar em diferenças. |
| SDK | Impression-level | Compare os dados no dashboard de receita do parceiro de mídia com:<ul><li>O relatório de receita no nível de impressão no Data Locker.<ul><li>Compare no dia do evento de receita (Dia 0).</li><li>Relevante apenas para clientes do ROI360 Advanced.</li></ul></li><li>Receita de anúncios no nível do dispositivo nos relatórios de receita de anúncios de versão única no Data Locker.<ul><li>Espere até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados, para que tanto a AppsFlyer quanto o parceiro de mídia tenham tempo para processar os dados.</li></ul></li><li>Receita agregada exibida no dashboard de atividade.<ul><li>Espere até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados, para que tanto a AppsFlyer quanto o parceiro de mídia tenham tempo para processar os dados.</li></ul></li></ul> |
| SDK e S2S (de atualização dos dados à precisão) | Nível de impressão (via SDK) | Compare os dados no dashboard de receita do parceiro de mídia com:<ul><li>A receita exibida no dashboard de atividade ou a receita total exibida nos relatórios de receita de anúncios de versão única no Data Locker.<ul><li>Espere até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados, para que tanto a AppsFlyer quanto o Parceiro de mediação tenham tempo de processá-los.</li></ul></li><li>O relatório de receita em nível de impressão no Data Locker.<ul><li>Compare no dia do evento de receita (Dia 0).</li><li>Relevante apenas para clientes do ROI360 Advanced.</li></ul></li></ul>**Observação**: Como os dados de receita de anúncios são mutáveis e é possível que nem todos os usuários do Aplicativo tenham atualizado para a versão mais recente com o conector SDK de receita de anúncios, a comparação dos dados da AppsFlyer com os dados do Parceiro de mediação pode resultar em diferenças. |
| SDK e S2S (atualização de dados vs. precisão) | Nível de dispositivo (via S2S API) | <ul><li>Compare a receita total exibida no dashboard de atividade da AppsFlyer ou a receita total exibida no relatório de receita de anúncios de versão única via Data Locker com os dados de receita total do Parceiro de mediação.</li><li>Espere até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados, para que tanto a AppsFlyer quanto o Parceiro de mediação tenham tempo de processá-los.</li><li>Não compare as contagens de eventos de receita de anúncios (reportadas em eventos af\_ad\_revenue) com as contagens de impressões.</li></ul> |

</Accordion>

<div id="comparing-appsflyer-data-with-user-acquisition-partner-data" />

<Accordion title="Comparação de dados da AppsFlyer com dados de Parceiros de aquisição de usuários">

O ROI360 Advanced é necessário para que Parceiros de aquisição de usuários tenham dados de receita de anúncios (via postbacks de receita de anúncios ou sinais de UA) disponíveis para comparação.

| Tipo de integração | Tipo de dados | Fonte de dados do Parceiro | Quais dados podem ser comparados com quais |
| --- | --- | --- | --- |
| S2S API | Nível do dispositivo | Sinais de aquisição de usuários | <ul><li>Compare a receita total exibida no dashboard de atividade da AppsFlyer ou a receita total exibida nos relatórios de receita de anúncios de versão única via Data Locker com os dados de receita total do Parceiro de UA.</li><li>Espere até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados.</li><li>Não compare as contagens de eventos de receita de anúncios (reportadas em eventos af\_ad\_revenue) com as contagens de impressões.</li></ul> |
| SDK | Nível do dispositivo | Sinais de aquisição de usuários | <ul><li>Compare a receita total exibida no dashboard de atividade da AppsFlyer ou a receita total exibida nos relatórios de receita de anúncios de versão única via Data Locker com os dados de receita total do Parceiro de UA.</li><li>Espere até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados.</li><li>Não compare as contagens de eventos de receita de anúncios (reportadas em eventos af\_ad\_revenue) com as contagens de impressões.</li></ul> |
| SDK | Impression-level | Postbacks de receita de anúncios | Compare os dados no dashboard de receita do parceiro de aquisição de usuários com:<ul><li>Dashboard/relatório de coorte da AppsFlyer.<ul><li>Agrupe os dados pelo canal de mídia específico (parceiro de UA).</li><li>Veja a receita total dos eventos af\_ad\_revenue ao filtrar por uma data específica. Isso permite comparar a receita de anúncios gerada por instalações que ocorreram em uma determinada data de relatório com a receita de anúncios reportada em postbacks relacionados a essas instalações.</li><li>Espere até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados.</li></ul></li><li>Dashboard de atividade do AppsFlyer/relatórios de receita de anúncios da versão única via Data Locker.<ul><li>Agrupe os dados por canal de mídia específico (parceiro de UA).</li><li>Veja a receita total dos eventos af\_ad\_revenue ao filtrar por uma data específica. Isso permite comparar a receita de anúncios gerada por instalações que ocorreram em uma determinada data de relatório com a receita de anúncios reportada nos postbacks relacionados a essas instalações.</li><li>Aguarde até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados.</li></ul></li></ul> |
| SDK e S2S (atualização dos dados vs. precisão) | Nível de impressão (via SDK) | Postbacks de receita de anúncios | Compare os dados no dashboard de receita do parceiro de aquisição de usuários com:<ul><li>Relatório ETL ROI360 de receita de anúncios do SDK em nível de impressão.<ul><li>Aguarde até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados, para que tanto a AppsFlyer quanto o parceiro de mediação tenham tempo de processar os dados.</li></ul></li><li>Relatório de postbacks de dados brutos de eventos in-app.<ul><li>Aguarde até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados, para que tanto a AppsFlyer quanto o parceiro de mediação tenham tempo de processar os dados.</li></ul></li></ul> |
| SDK e S2S (atualização dos dados vs. precisão) | Nível de dispositivo (via S2S API) | Sinais de aquisição de usuários | <ul><li>Compare a receita total exibida no dashboard de atividade da AppsFlyer ou a receita total exibida nos relatórios de receita de anúncios da versão única via Data Locker com os dados de receita total do parceiro de UA.</li><li>Aguarde até o dia seguinte ao evento de receita (Dia 0+1) para comparar os dados.</li><li>Não compare as contagens de eventos de receita de anúncios (reportadas em eventos af\_ad\_revenue) com as contagens de impressões.</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01HCSS64Y99ZNAX64JRE5ZN3J7=comparing-appsflyer-data-with-mediation-partner-data h_01HCSS64Y9FDE00JN8XPWXG0CV=comparing-appsflyer-data-with-user-acquisition-partner-data" />

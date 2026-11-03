---
title: 'Boletim: migração da Digital Turbine para a integração unificada da AppsFlyer'
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-01T10:27:56Z'
  edited_at: '2026-10-20T03:54:00Z'
  id: 50419778565521
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/50419778565521
---
| **Secção** | **Atenção** |
| --- | --- |
| **Novidades** | A Digital Turbine (DT) está migrando os anunciantes do PID legado `digitalturbine_int` para o novo PID unificado `onedigitalturbine_int`, como parte da migração da DT para a plataforma de anúncios dela.<br /><br />A integração unificada dá a você acesso aos recursos de machine learning da DT e aos sinais de dispositivo first-party. |
| **Data de início** | 1 de outubro de 2026 |
| **O que você precisa saber** | **Novo canal de mídia**<ul><li>O novo canal de mídia é `onedigitalturbine_int`.</li></ul>**Dimensões de relatórios de campanha**<ul><li>Os relatórios mudam de Campanha/ID da campanha para Adset/ID do adset.</li><li>Isso afeta os relatórios de cohort e LTV.</li></ul>**Relatórios durante a transição**<ul><li>Selecione os dois canais de mídia (`digitalturbine_int` e `onedigitalturbine_int`) ao revisar os relatórios durante o período de transição.</li><li>Revise todos os dashboards personalizados, integrações de BI ou relatórios salvos que fazem referência ao PID legado, já que eles não passarão a incluir automaticamente o novo PID.</li></ul> |
| **O que é preciso fazer** | <ol><li>Gere novos links de atribuição usando o <Anchor target="_blank" href="https://docs.digitalturbine.com/measurement/mmp-guides/appsflyer">Guia de integração DT&lt;>AppsFlyer</Anchor> e envie-os ao seu gerente de conta da DT.</li><li>A DT migrará suas campanhas para os novos links. Você não precisa recriá-los manualmente.</li><li>Mantenha sua integração legada ativa até que sua janela de lookback expire, para que as conversões em andamento continuem sendo atribuídas corretamente. No dia da transição, mude os relatórios de custo para usar apenas a Unified Reporting API da DT. Faça isso assim que `onedigitalturbine_int`  estiver ativo e evite executar os dois ao mesmo tempo para não contabilizar o gasto em duplicidade.</li></ol>**Reporting API e dados de custo**<ul><li>Faça a transição da Reporting API legada para a Unified Reporting API da DT para evitar dados duplicados.</li><li>O InCost é configurado no nível da conta.</li><li>A aba Custo no nível do aplicativo está sendo descontinuada para networks migradas.</li><li>A autenticação da API no nível da conta é necessária na configuração do parceiro `onedigitalturbine_int`.</li><li>Nenhum Client ID ou Secret é necessário para os dados de custo. A AppsFlyer os recebe diretamente da DT. O que mudou foi o fluxo de configuração: a integração de custos costumava ser ativada por aplicativo e agora é configurada uma única vez no nível da conta para vários aplicativos.</li></ul>**Prazo de migração**<ul><li>O **prazo é 1º de outubro de 2026**. Gere seus novos links o quanto antes.</li><li>A DT monitorará os dados de entrega e de custo após a migração.</li><li>Se você tiver problemas, entre em contato com o suporte da AppsFlyer ou com seu CSM, ou fale com o gerente de conta da DT.</li></ul> |
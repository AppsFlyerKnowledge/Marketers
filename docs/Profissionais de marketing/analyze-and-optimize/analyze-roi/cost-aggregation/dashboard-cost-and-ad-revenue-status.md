---
title: Dashboard - Status de custo e receita de anúncios
metadata:
  keywords:
    - ad revenue
    - cost
    - Advertisers
    - Agencies
    - Xpend
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-12-23T12:52:57Z'
  edited_at: '2026-08-19T00:01:01Z'
  id: 360016789458
  locale: pt
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/pt/articles/360016789458
---
> **Resumo:** Anunciantes e agências podem verificar o status das integrações de custo e receita de anúncios.

## Status da integração de custo e receita de anúncios

* O dashboard exibe o status operacional atual das suas integrações de custo/receita de anúncios.
  * Os anunciantes veem os status de todos os aplicativos, canais de mídia e agências na conta.
  * As agências veem os status de todos os aplicativos e canais de mídia com que trabalham.
* As integrações de receita de anúncios são listadas pelo canal de mídia de receita de anúncios, não pelo canal de mídia de aquisição de usuários.
* Para integrações que exigem ações corretivas, a ação necessária é exibida.
* Para ver o status de custo e receita de anúncios, na AppsFlyer, no menu lateral, selecione **Configurações** > **Status de custo & receita de anúncios**.
* A imagem e a tabela a seguir detalham os componentes do dashboard.

#### Dashboard de status de custo & receita de anúncios

[![dashboard_de_status_de_custo_e_receita_de_anúncios.jpg](https://files.readme.io/da713daae6c7044e8e4f32274520961e1b43c183d8e4cb95f58854cb614efb39-360016000898.jpg)](https://files.readme.io/da713daae6c7044e8e4f32274520961e1b43c183d8e4cb95f58854cb614efb39-360016000898.jpg)

| Seção | Descrição |
| --- | --- |
| <span id="a-filters"></span>A. Classificar Classificar | <ul><li>Aplicação</li><li>Agências</li><li>Canal de mídia</li><li>Estado</li><li>Tipo de integração (custo ou receita de anúncios)</li><li>Problema</li></ul> |
| <span id="b-headline-metrics"></span>B. Métricas do título | <ul><li>**Total de integrações**: Número de aplicativos/parceiros para os quais a integração está habilitada, independentemente do status. Por exemplo, se você tiver um aplicativo Android e um iOS, ambos integrados aos anúncios da Meta, o total de integrações será dois.</li><li>**Ação necessária**: Número de aplicativos e canais de mídia na sua conta com problemas de API que precisam ser atualizados.</li><li>**Aviso**: Número de integrações para as quais não há dados ou que estão enfrentando um erro temporário de network.</li><li>**Aguardando sincronização**: Número de integrações conectadas, mas aguardando que os dados sejam obtidos. Pode levar até 24 horas para ver os dados na AppsFlyer.</li><li>**Ativo**: Número de parceiros com as APIs de custo/receita de anúncios sincronizadas e operacionais.</li></ul> |
| <span id="c-status"></span>C. Estado Estado | Cada status tem uma tabela separada no dashboard com todas as integrações que se aplicam. Para ver as definições de status, consulte as métricas principais acima.<ul><li>**Ação necessária**</li><li>**Atenção**</li><li>**Aguardando sincronização**</li><li>**Ativa**</li></ul> |
| <span id="d-columns"></span>D. Colunas | Cada seção de status contém várias colunas:<ul><li>Canal de mídia</li><li>Aplicativo: Aplicativo com integração de API de dados de custo ou receita de anúncios.</li><li>Última sincronização: Momento mais recente em que os dados foram recebidos.</li><li>Tipo de integração:<ul><li>Custo (3)</li><li>Receita de anúncios (atrib.): Significa que a receita de anúncios é atribuída ao canal de mídia de aquisição de usuários</li><li>Receita de anúncios (agreg.): Significa que a receita de anúncios é agregada com base na fonte de monetização (o canal de mídia que exibiu o anúncio)</li></ul></li><li>Custo/receita da campanha (com base na API): Custo da campanha ou receita de anúncios do aplicativo por canal de mídia nos últimos 7 dias.</li><li>Problema: Veja a lista abaixo.</li><li>Ação: Ação necessária para habilitar os dados, se houver um problema na integração da API. Clicar em **Reconnect** leva à ação necessária.</li></ul> |
| <span id="e-problem"></span>E. Problema Problema | <ul><li>**Credenciais inválidas**: A AppsFlyer não consegue obter dados por meio da API porque as credenciais não são válidas. Reconecte-se usando as credenciais corretas.</li><li>**Aguardando a primeira sincronização**: Aguardando a extração inicial de dados do parceiro. Volte novamente em algumas horas.</li><li>**Não habilitado**: O anunciante ou a agência recebeu tráfego e mais de 20 instalações desse parceiro nos últimos 28 dias, mas a integração de custo não está habilitada. Habilite a integração de custo.</li><li>**Sem dados**: Integração ativa, mas o parceiro não está retornando dados.<ul><li>Para receber uma notificação quando o problema ocorrer, habilite o alerta por e-mail de falha de dados de receita de anúncios.</li></ul></li><li>**Não disponível**: A integração está ativa, mas não há dados de custo dos últimos 30 dias do parceiro devido à falta de campanhas ativas.</li><li>**Problema de network**: Há um problema temporário com este parceiro. Verifique novamente daqui a algumas horas.</li><li>**Erro geral**: Há um problema temporário com este parceiro. Contate o suporte.</li><li>**Versão antiga da API**: Revise a integração e atualize as credenciais da API.</li><li>**Configuração inválida**: Nome do evento configurado não encontrado para atribuição de receita. Revise a configuração e atualize o nome da fonte do evento.</li><li>**Integração desativada**: Reconecte sua integração.</li><li>**Restrito pelo parceiro**: Sua conta não está ativada no sistema do parceiro para obter custo. Contate o parceiro.</li><li>**Integração suspensa**: A integração do parceiro ficou com o status de aviso por 30 dias consecutivos. Reconecte-se ao parceiro.<ul><li>Para receber uma notificação quando o problema ocorrer, habilite o alerta por e-mail de integração suspensa de receita de anúncios.</li><li>**Observação**: Após 180 dias, parceiros com uma integração suspensa não são exibidos no dashboard de status.</li></ul></li><li>**Incompatibilidade entre API e atribuição**: A API do parceiro não está retornando dados de custo correspondentes. Isto acontece por:<ul><li>Foi integrada uma conta de anúncio de parceiro diferente ao entrar através da AppsFlyer (por exemplo, uma conta de anúncios Meta diferente). Verifique se ligou a conta correta do parceiro de anúncios.</li><li>Um dos campos de credenciais na integração de custos do parceiro está incorreto. Por exemplo, o ID do pacote. Verifique e corrija as credenciais da integração.</li></ul></li><li>**Erro de configuração**: A API do parceiro não está retornando dados. Isto acontece por:<ul><li>As suas campanhas estão pausadas e não há dados disponíveis.</li><li>Foi integrada uma conta de anúncio de parceiro diferente ao entrar através da AppsFlyer (por exemplo, uma conta de anúncios Meta diferente). Verifique se ligou a conta correta do parceiro de anúncios.</li><li>Um dos campos de credenciais na integração de custos do parceiro está incorreto. Por exemplo, o ID do pacote. Verifique e corrija as credenciais da integração.</li></ul></li></ul> |

<div data-zendesk-anchors="cost-and-ad-revenue-integration-status=status-da-integra%C3%A7%C3%A3o-de-custo-e-receita-de-an%C3%BAncios h_01HKW10FWXCZ1QFFJA1FTYH50F=status-da-integra%C3%A7%C3%A3o-de-custo-e-receita-de-an%C3%BAncios cost-ad-revenue-status-dashboard=dashboard-de-status-de-custo--receita-de-an%C3%BAncios h_01HKW10FWXGWHSQKFTHRDHGWSP=dashboard-de-status-de-custo--receita-de-an%C3%BAncios" />

---
title: ROI360—guia de integração
metadata:
  keywords:
    - ROI
    - cost
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-05-23T08:36:31Z'
  edited_at: '2026-09-10T12:01:02Z'
  id: 25301111725329
  locale: pt
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/pt/articles/25301111725329
---
> **Visão Geral**: Siga as instruções de integração deste artigo para começar a utilizar o ROI360 para dados de custos e receitas.

![](https://files.readme.io/fa3644980702d735f81d7243f91cb0f0d454bd971e83685ab9759ff7bd925e93-26137252926097.png)

<div id="about-roi360" />

## Sobre o ROI360

O ROI360 é um conjunto exclusivo de ferramentas de relatórios de custos e receitas que oferece dados precisos e atualizados. Com os insights de custos e receitas combinados, obtém uma visão completa do retorno do gasto publicitário (ROAS) e do retorno do investimento (ROI), permitindo otimizar e melhorar as suas estratégias.

Siga as instruções de integração abaixo para ativar os relatórios de custos, receitas de anúncios, compras na aplicação e receitas de subscrições no ROI360. A integração requer a participação de profissionais de marketing, programadores de aplicações e programadores de BI.

**Sugestão**! Para uma integração rápida, priorize uma aplicação e conclua todos os passos para operacionalizar o ROI360. Pode focar-se nos custos, receitas de anúncios ou receitas de compras e subscrições na aplicação, mas garanta que completa a integração de uma aplicação primeiro.

<div id="cost-onboarding" />

<Accordion title="Integração de custos">

![](https://files.readme.io/0e7102766b3b7cdba3f301ca89c51edf8e4bd2ec88e09bc912ce3c1436c43fcb-26137252929681.png)

Com a solução de custos ROI360, obterá insights detalhados de custos e ROI, atualizados diversas vezes ao dia. Isso permite gerir eficazmente os custos de campanha e visualizar alocações de orçamento em várias fontes de media (redes de anúncios), campanhas e regiões geográficas, quer use redes de anúncios, meios próprios ou agências.

Após concluir a integração de custos, poderá:

* Obter visões gerais abrangentes e atualizadas dos custos da campanha com consolidação automática através de todas as fontes de media.
* Basear a sua análise de dados nos dados de custos mais precisos, atualizados após a instalação.
* Para utilizadores do ROI360 Advanced, transmitir dados de custos detalhados para o seu sistema de BI até 4 vezes por dia.
* Gerir taxas de agência e medir com precisão os custos gerais da campanha para supervisão financeira e transparência.

| Função | Objetivo | Ações necessárias | Quem está envolvido |
| --- | --- | --- | --- |
| Ligue as integrações de API de custos para todas as redes de anúncios com as quais trabalha. | Obtenha dados de custo de todas as fontes ligadas à atribuição ao nível mais detalhado. | <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Ative a API de Custos</Anchor> para cada rede de anúncios na interface do AppsFlyer. **Nota**: Antes da integração, é necessário obter as credenciais de acesso para cada rede de anúncios. | Marketer |
| Configure relatórios ETL de Custos. (Disponível para subscritores do ROI360 Advanced) | Visualize os dados de custo de campanha com a melhor granularidade disponível por fonte de média, atualizados até 4 vezes por dia. | Configure relatórios ETL de Custos para <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-aws-s3">AWS S3</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-gcs">GCS</Anchor>. | Profissional de Marketing/Desenvolvedor de BI |
| Carregue dados de custo através da Importação de Custos. | Obtenha dados de custo:<ul><li>Para redes de anúncios que não reportam custos via API ou cliques.</li><li>Quando utiliza links OneLink para publicitar através de influenciadores, etc.</li><li>Quando precisar de corrigir dados de custo.</li></ul> | Carregue ou envie por e-mail os ficheiros de dados de custo utilizando a <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Importação de Custos</Anchor>. | Marketer |
| Configure comissões de agência. | Se utilizar agências, obtenha o custo total da campanha, incluindo as comissões percentuais que as agências cobram pelo tráfego. | Crie <Anchor target="_blank" href="/marketers/pt/docs/incorporate-agency-fees-into-campaign-costs">regras de comissões de agência</Anchor> para cada agência com a qual trabalha. | Marketer |

</Accordion>

<div id="ad-revenue-onboarding" />

<Accordion title="Integração de Receita de Anúncios">

![](https://files.readme.io/877e4abddd466bbe7dfa31f7fffb2f17fe3e6419f3bf6345e9d619253126b0e6-26137252932369.png)

Com a solução de receita publicitária ROI360, receberá dados valiosos e detalhados de receita publicitária, atualizados várias vezes ao dia.

Após completar a integração da receita de anúncios, incluindo a conexão às plataformas de mediação ou redes de monetização com as quais trabalha, bem como a implementação da API SDK ao nível da impressão e a partilha de dados com parceiros de UA, será capaz de:

* Obtenha dados precisos e atualizados sobre receitas de anúncios em todos os painéis e relatórios da AppsFlyer.
* Transmita dados para o seu sistema de BI com precisão e atualização conforme as suas necessidades.
* Melhore o desempenho das campanhas, permitindo que as redes UA otimizem métricas de receita de anúncios.

| Função | Objetivo | Ações necessárias | Quem está envolvido |
| --- | --- | --- | --- |
| Escolha o tipo de integração de atribuição de receita de anúncios. | Compreenda os benefícios de cada tipo de integração e decida qual se adapta melhor às necessidades do seu negócio. | Saiba mais sobre os diferentes <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">tipos de integração de receita de anúncios</Anchor> e escolha um. | Marketer |
| Conecte-se a todas as redes de mediação e monetização de receita de anúncios com as quais trabalha. | Obtenha dados de receita publicitária das suas redes de mediação ou monetização. | <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Conecte integrações de receita de anúncios</Anchor> na interface do AppsFlyer. | Marketer |
| Implemente a API SDK de receita de anúncios ao nível da impressão. | <ul><li>Relevante para tipos de integração ao nível do SDK.</li><li>Obtenha dados de receita de anúncios com atualização quase em tempo real.</li></ul> | <ol><li>Integre o <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-roi360-ad-revenue-sdk-api">API ROI360 Ad Revenue SDK da AppsFlyer</Anchor>.</li><li>Para visualizar dados de receita de anúncios no painel SKAN, ative o <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#report-events-by-servertoserver-api">suporte servidor a servidor SKAdNetwork</Anchor>.</li></ol> | Desenvolvedor/Profissional de Marketing |
| Partilhe dados de receita de anúncios com parceiros UA. | As redes de publicidade UA podem utilizar os dados de receita de anúncios para otimizar as suas campanhas. | <ol><li>Saiba mais sobre os dois <Anchor target="_blank" href="/marketers/pt/docs/share-ad-revenue-data-with-partners#compartilhamento-de-dados-de-receita-de-anúncios-com-parceiros">métodos para partilhar dados de receita de anúncios com parceiros UA</Anchor>.</li><li><Anchor target="_blank" href="/marketers/pt/docs/share-ad-revenue-data-with-partners#procedimentos">Implemente o método</Anchor> que escolheu.</li></ol> | Marketer |
| Configure relatórios ETL de Receita. (Disponível para subscritores do ROI360 Advanced) | Transmita e visualize dados de receita de anúncios no seu BI com a melhor granularidade disponível, atualizados várias vezes por dia. | Configure <Anchor target="_blank" href="/marketers/pt/docs/revenue-etl-reports">relatórios ETL de receita de anúncios</Anchor>. | Profissional de Marketing/Desenvolvedor de BI |

</Accordion>

<div id="revenue-onboarding" />

<Accordion title="Integração de receita de compras na aplicação e subscrições">

![](https://files.readme.io/811c90ec42465994455fe42be8400b4ebb94ab6d1a5703bc9a77251aba95ed3b-26137252934545.png)

Com a solução de receita ROI360, adquire um controlo proativo sobre os seus fluxos de renda.

Após completar a integração da receita, incluindo a configuração de notificações da loja e a implementação de APIs de SDK de compra para Android e iOS, irá:

* Estabelecer validação e medição automáticas para transações na App Store e no Google Play.
* Desfrute de relatórios de receita contínuos e precisos, sem necessidade de esforços extra de desenvolvimento; o ROI360 irá tratar do registo de todos os eventos de receita na aplicação para si.
* Obtenha medições precisas de receita para gerir eficazmente iniciativas de crescimento estratégico em todo o seu portfólio.

| Função | Objetivo | Ações necessárias | Quem está envolvido |
| --- | --- | --- | --- |
| Implemente a solução ROI360 de receita de compra na aplicação e subscrições. | Valide e meça automaticamente a receita proveniente de compras na aplicação, subscrições de renovação automática e eventos relacionados através da App Store (iOS) ou Google Play (Android). | Siga <Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview">estas instruções</Anchor> para:<ol><li>Configurar notificações do Google Play.</li><li>Configurar notificações da App Store iOS.</li><li>Integre a API do SDK de compras da AppsFlyer para Android e iOS.</li><li>Testar a mensuração de receita de compras in-app e assinaturas.</li><li>Publique as versões da aplicação Android e iOS com as APIs do SDK de compras.</li></ol> | Desenvolvedor/Profissional de Marketing |
| Configure relatórios ETL de Receita. (Disponível para subscritores do ROI360 Advanced) | Transmita e veja os dados de receita no seu BI com a melhor granularidade disponível, atualizados várias vezes ao dia. | Configure <Anchor target="_blank" href="/marketers/pt/docs/revenue-etl-reports">os relatórios de ETL de receita</Anchor>. | Profissional de Marketing/Desenvolvedor de BI |

</Accordion>

<div data-zendesk-anchors="overview=sobre-o-roi360 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=sobre-o-roi360 h_01HYJ8PSPTFR6QH329TBR73AXM=cost-onboarding h_01HYJ8PSPTKBZ60TF7T0EMSCXW=ad-revenue-onboarding h_01HYJ8PSPTWK4SEGVJWG5J86E2=revenue-onboarding" />

---
title: Primeiros passos — Onboarding para profissionais de marketing
metadata:
  keywords:
    - SDK
    - Integration
    - Reports
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2015-01-18T11:03:01Z'
  edited_at: '2026-08-18T00:18:09Z'
  id: 207033486
  locale: pt
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/pt/articles/207033486
---
> **Resumo:** deixe tudo configurado e aproveite ao máximo a sua conta da AppsFlyer. Entenda as etapas, os cronogramas e as dependências para fazer a integração dos seus aplicativos e da sua equipe.

<Embed title="Primeiros passos — Onboarding para profissionais de marketing" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/gamcb25kgu" providerUrl="https://fast.wistia.com" />

## Introdução

Esse documento ajuda gerentes de produto (ou seja, os proprietários do aplicativo) **a planejar e executar sua integração com a AppsFlyer**. Para cada item, destacamos o proprietário e o tempo aproximado de implementação.

Observe que as estimativas de tempo neste artigo servem apenas como orientação geral. Elas se baseiam em nossa experiência de trabalho com diversos novos clientes, mas reconhecemos que cada proprietário, aplicativo e implementação de aplicativo é diferente. O tempo necessário para o seu caso pode variar.

## Configuração da conta

O **administrador da conta** deve completar as seguintes etapas:

| Etapa | Tempo | Comentários |
| --- | --- | --- |
| <Anchor target="_blank" href="https://www.appsflyer.com/pt/get-started/">Cadastre-se</Anchor> na AppsFlyer | 5 mins | O ideal é que o administrador da conta seja um usuário real da AppsFlyer que pode receber mensagens importantes quando necessário. |
| <Anchor target="_blank" href="/marketers/pt/docs/user-management#creating-users">Adicione usuários da conta</Anchor> que usarão o dashboard da AppsFlyer, e defina suas permissões | 1 min por usuário da conta | <Anchor target="_blank" href="/marketers/pt/docs/user-management#creating-users">Em alguns casos</Anchor>, os usuários podem ser adicionados a várias contas. |

**Resultado:** **Bem-vindo!** Agora você tem uma conta ativa da AppsFlyer e usuários da conta que podem acessá-la.

> 👍 **Dica**
>
> É novo na AppsFlyer e quer saber o que ela pode fazer por você? <Anchor target="_blank" href="/marketers/pt/docs/welcome-to-appsflyer#o-que-você-pode-fazer-com-a-appsflyer">Assista esse vídeo de 6 minutos</Anchor>.

## Integração do aplicativo

As **etapas 1 a 3 a seguir são obrigatórias para todos os aplicativos** adicionados à AppsFlyer (exceto quando indicado como opcional).

Você pode seguir as etapas usando esse guia ou por meio da página de integração do aplicativo no dashboard. A página de integração do aplicativo orienta você nas etapas básicas necessárias para preparar seu aplicativo para atribuição. Se preferir usá-lo, recomendamos também usar este guia para as subetapas adicionais que podem ser necessárias para suas necessidades comerciais específicas.

**Para abrir a página de integração do aplicativo:**

1. Na barra de menu, clique no menu do usuário (menu suspenso no endereço de e-mail)
2. Selecione integração do aplicativo

## Passo 1: Configuração do aplicativo

O **administrador da conta** deve completar as seguintes etapas para cada um dos seus apps:

| Etapa | Tempo | Comentários |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione o seu aplicativo</Anchor> à conta da AppsFlyer | 1 min | Se a adição de um aplicativo falhar, geralmente é porque ele foi configurado anteriormente em uma conta diferente (normalmente uma agência publicitária com a qual os seus profissionais de marketing trabalham). Entre em contato com o seu CSM ou envie um e-mail para hello@appsflyer.com para <Anchor target="_blank" href="/marketers/pt/docs/transferring-apps-between-accounts">transferir o aplicativo para sua conta</Anchor>.<br /><br />Consulte as <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#resolução-de-problemas">etapas adicionais de identificação e solução de problemas</Anchor> para adicionar aplicativos. |
| Defina <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#insira-informações-adicionais-não-aplicáveis-a-aplicativos-da-web">o fuso horário do aplicativo, sua moeda</Anchor> e se ele é direcionado para crianças | 1 min |  |
| Configure a <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor>  <br /> do aplicativo (na página de <Anchor target="_blank" href="/marketers/pt/docs/app-settings#reattribution-window">Configurações do aplicativo</Anchor>) | 1 min | A janela de reatribuição é o período que se inicia com a data da primeira instalação, durante o qual **as reinstalações do mesmo dispositivo não são atribuídas** como novas instalações. O valor padrão é 90 dias, que você pode personalizar conforme necessário. |
| [Opcional] Migre dispositivos de usuário existentes para a AppsFlyer | 2 horas | Se o seu aplicativo já tiver uma base de usuários considerável, considere <Anchor target="_blank" href="/marketers/pt/docs/migration-to-appsflyer-from-other-vendors#migração-de-dispositivosopcional">migrá-los para a AppsFlyer</Anchor> para evitar cobranças duplas.<br /><br />**Atenção:** com a ajuda do seu CSM da AppsFlyer ou da equipe de suporte, por meio do e-mail [hello@appsflyer.com](mailto:hello@appsflyer.com)). |

**Resultado:** seus aplicativos agora estão configurados no dashboard da AppsFlyer.

## Passo 2: Integração SDK / API

Complete as etapas abaixo para cada app configurado na [Etapa 1: configuração do aplicativo](/docs/getting-started-onboarding-for-marketers#passo-1-configuração-do-aplicativo)

| Etapa | Proprietário | Tempo | Comentários |
| --- | --- | --- | --- |
| Considere as opções disponíveis e selecione as <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">funcionalidades do SDK</Anchor> que você deseja que seu aplicativo use | Gerente de produto | 1 hora | <ul><li>Algumas considerações além da atribuição básica:<ul><li>Suas campanhas farão o deep linking dos usuários para o aplicativo?</li><li>O aplicativo precisará <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#acessando-dados-de-atribuição-e-deep-linking">acessar dados de atribuição ou de deep linking</Anchor>?</li><li>Os dados da AppsFlyer devem conter o seu <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">Customer User ID</Anchor> para referência?</li><li>Como você implementará as <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">configurações de privacidade para dispositivos iOS 14+</Anchor>? Você fará a mensuração de desinstalações, executará campanhas de promoção cruzada e mais?</li></ul></li><li>Você tem um aplicativo CTV? Veja uma <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">visão geral da CTV</Anchor>.</li></ul> |
| Selecione quais <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">eventos in-app</Anchor> devem ser registrados | Gerente de produto | 1 hora | Registrar os eventos pós-instalação que os seus usuários realizam no aplicativo ajuda a entender melhor a **qualidade** dos seus usuários.<br /><br />Visite o [gerador de eventos in-app](https://evgen.appsflyer.com/) para acessar nossa lista completa de <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#recommended-events-by-business-vertical">eventos in-app</Anchor> e parâmetros recomendados para a sua vertical. Você pode adicionar seus próprios eventos e parâmetros.  <br />Clique no botão **Código** para visualizar e copiar o código gerado automaticamente para seus desenvolvedores. |
| Selecione métodos para recuperar dados de atribuição/deep linking | Gerente de produto | 30 minutos | Saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#acessando-dados-de-atribuição-e-deep-linking">métodos</Anchor> disponíveis:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data">Extrair API</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">API de push</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">Unified deep linking API</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/conversion-data-payloads-and-scenarios">Get conversion data</Anchor></li></ul> |
| Tarefas do desenvolvedor | Gerente de produto | 5 mins | Prepare e envie um e-mail para o seu desenvolvedor com instruções e tarefas para:<ul><li>Integração SDK / API</li><li>Mapeamento de eventos in-app</li></ul>Esses podem ser encontrados na aba <Anchor target="_blank" href="https://hq1.appsflyer.com/onboarding/apps">Integrar o SDK</Anchor> do assistente para adicionar um aplicativo. |
| Implementação pelo desenvolvedor | Desenvolvedor de aplicativos | 3 horas | Verifique se recebeu o e-mail enviado pelo profissional de marketing com instruções e tarefas para a integração do SDK e o mapeamento de eventos no aplicativo.<br /><br />Implemente-os automaticamente para Android e iOS usando o <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=dashboard&utm_medium=app-onbrd-mail-a">AppsFlyer Dev Journey</Anchor> ou manualmente usando os links abaixo.<br /><br />Recursos da AppsFlyer para os seus desenvolvedores:<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">com o Android</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">/docs/ctv-pc-and-console-platform-attribution-concepts</Anchor></li><li>Unity</li><li><Anchor target="_blank" href="/marketers/pt/docs/windows-sdk-integration-for-developers">Windows Phone</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/other-platforms">Outras plataformas</Anchor></li></ul> |
| <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers">Teste a integração</Anchor> | Gerente de produto  <br />Desenvolvedor de aplicativos | 1 hora | Você pode testar a integração do SDK antes ou depois do seu aplicativo estar ativo na loja de aplicativos. Você pode usar aplicativos de debug para manter os dados do seu aplicativo limpos.<br /><br />Apenas para aplicativos Android e iOS: Certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">registrar seus dispositivos de teste</Anchor>. |
| Lance a nova versão do aplicativo | Gerente de produto | 1 hora | <Anchor target="_blank" href="/marketers/pt/docs/preparing-for-the-app-store-review-nutrition-labels">Prepare-se para a análise da App Store no iOS</Anchor>. |

**Resultado:** seus aplicativos estão prontos para a atribuição de instalação, mensuração de eventos in-app e outras funcionalidades da AppsFlyer, que não exigirão recursos de dev adicionais.

## Passo 3: Configuração de atribuição

Complete as etapas abaixo para cada app configurado na [Etapa 1: configuração do aplicativo](/docs/getting-started-onboarding-for-marketers#passo-1-configuração-do-aplicativo)

| Etapa | Proprietário | Tempo | Comentários |
| --- | --- | --- | --- |
| Configure fontes de mídia **pagas** para atribuição na AppsFlyer | Profissional de Marketing | 15 minutos por fonte de mídia | Saiba mais sobre como atribuir <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">redes de autorrelato</Anchor> (SRNs), especificamente:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/apple-ads-integration-setup">Anúncios de Busca da Apple</Anchor></li><li>GMP (Doubleclick)</li></ul>Saiba mais sobre como atribuir ad networks que não são SRNs:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">Outros parceiros integrados</Anchor></li><li>Estrutura e parâmetros do <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">link de atribuição da</Anchor> AppsFlyer</li></ul> |
| Use o OneLink para atribuir fontes de mídia **própria**: sites mobile, mídias sociais, convites de usuário e muito mais | Responsável | 1 hora | Saiba mais sobre as <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide#opções-adicionais">soluções baseadas no Onelink</Anchor> para seus casos de uso de mídia própria |
| Implementação de mídia própria | Desenvolvedor de aplicativos | 0-6,5 horas (dependendo das soluções implementadas) | 0-6,5 horas (dependendo das soluções implementadas) Para desenvolvedores: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">primeiros passos no deep linking</Anchor> |
| Configurar janelas de atribuição | Gerente de produto | Configure fontes de mídia **pagas** para atribuição na AppsFlyer  <br />Profissional de Marketing | 2 min por fonte de mídia Saiba mais: <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">Explicação das janelas de lookback de click-through e view-through</Anchor> |
| [Opcional] Ative campanhas de retargeting | Gerente de produto | 2 mins | <Anchor target="_blank" href="/marketers/pt/docs/app-settings#reengagement-attribution">Ative o retargeting na página de configurações do aplicativo</Anchor>.<br /><br />Saiba mais: <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">Guia de retargeting</Anchor> |

**Resultado:** todas as fontes de mídia que levam tráfego para os seus aplicativos são atribuídas sempre que usuários novos ou antigos interagem com elas.

## Passo 4: Configuração adicional

Complete as etapas abaixo para cada app configurado na [Etapa 1: configuração do aplicativo](/docs/getting-started-onboarding-for-marketers#passo-1-configuração-do-aplicativo)

Para que você possa atingir seus objetivos de negócios, algumas etapas podem ser obrigatórias.

| Etapa | Proprietário | Recursos adicionais |
| --- | --- | --- |
| Otimize campanhas de aquisição de usuários ao gravar a receita | Gerente de produto  <br />Desenvolvedores | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/legacy-receipt-validation-for-in-app-purchases">Validações de compras in-app</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution">Monetização de anúncios</Anchor></li><li>Assinaturas de usuários</li></ul> |
| Saiba mais sobre métodos para agregar e visualizar dados de custo de marketing | Gerente de produto | <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">ROI360 — visão geral da agregação de custos</Anchor> |
| Configure outras <Anchor target="_blank" href="/marketers/pt/docs/3rd-party-platforms">plataformas externas</Anchor> com as quais seu aplicativo trabalha | Gerente de produto  <br />Desenvolvedores | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/mparticle-integration-with-appsflyer">mParticle</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/segment-integration">Segment</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/mixpanel-integration-with-appsflyer">Mixpanel</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/amplitude-integration-with-appsflyer">Amplitude</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/adobe-analytics-integration-with-appsflyer">Adobe Analytics</Anchor> (Omniture)</li><li><Anchor target="_blank" href="/marketers/pt/docs/braze-formerly-appboy-integration-with-appsflyer">Braze</Anchor></li></ul> |
| Confira esses recursos premium da AppsFlyer que podem economizar o seu tempo e dinheiro. | Gerente de produto | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/audiences-guide">Audiências</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/pivot-table-user-metrics">Tabela dinâmica</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Relatório do Data Locker</Anchor></li></ul> |
| Proteja suas campanhas contra fraudes e erros de direcionamento | Gerente de produto | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide">Protect360—solução antifraudes</Anchor></li><li>Use as <Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud">regras de validação</Anchor> para garantir que as campanhas não sejam direcionadas incorretamente</li></ul> |
| Implementar a API server-to-server para eventos in-app reportados fora do aplicativo | Gerente de produto  <br />Desenvolvedores | <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S REST API</Anchor> |
| Mensure as taxas de desinstalação das suas fontes de mídia | Gerente de produto  <br />Desenvolvedores | Mensuração de desinstalação |
| Tenha uma visão unificada das jornadas dos seus clientes em todos os canais, plataformas e dispositivos | Gerente de produto  <br />Desenvolvedores | <Anchor target="_blank" href="/marketers/pt/docs/people-based-attribution-pba-overview">People-Based Attribution (PBA)</Anchor> |
| Assegure a conformidade com as regulamentações de privacidade: LGPD, CCPA, etc. | Gerente de produto  <br />Desenvolvedores | Permitir que os usuários <Anchor target="_blank" href="/marketers/pt/docs/apply-privacy-preserving-sdk-methods">optem por não serem rastreados</Anchor> na atribuição. |

## Amplie o seu conhecimento

Recomendado para todos os usuários da AppsFlyer:

| Etapa | Tempo |
| --- | --- |
| Conheça o dashboard de visão geral da AppsFlyer | 15 minutos |
| Explore a diferença entre<Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports"> dados de Lifetime Value (LTV) e dados de atividade</Anchor> na AppsFlyer (resolvendo o mistério de por que o resumo de eventos in-app difere entre os dashboards de Visão geral e de Atividade) | 15 minutos |
| Entenda o <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">modelo de atribuição</Anchor> da AppsFlyer | 30 minutos |
| Saiba mais sobre as <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview">ferramentas de relatório e análises agregadas</Anchor> | 30 minutos |
| Saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">relatórios de dados brutos</Anchor> | 30 minutos |

## Relacionado

> 👍 **Dica**
>
> Novo em UA (aquisição de usuário)? Saiba <Anchor target="_blank" href="https://www.appsflyer.com/pt/resources/ecommerce/getting-started-user-acquisition-apps-complete-guide/">tudo sobre</Anchor> os maiores desafios e os pontos críticos do planejamento e da execução, e continue otimizando seus esforços de aquisição de usuário.

> 📘 **Observação:**
>
> Novo na AppsFlyer, mas não é um profissional de marketing? Não se preocupe!
> Escolha o guia certo para você:
>
> * <Anchor target="_blank" href="/partners/pt/docs/getting-started-agency-onboarding">Primeiros passos para agências</Anchor>
> * <Anchor target="_blank" href="/partners/pt/docs/getting-started-onboarding-guide-for-ad-networks">Primeiros passos para ad networks</Anchor>

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o 01H8BD2FJ6TQ5FP9625MNP2B3Z=introdu%C3%A7%C3%A3o step-1-account-setup=configura%C3%A7%C3%A3o-da-conta 01H8BD2FJ6E8KZW41V04SBDQPQ=configura%C3%A7%C3%A3o-da-conta 01H8BD2FJ6A39JB8J0PQ3EY52N=dica app-onboarding=integra%C3%A7%C3%A3o-do-aplicativo 01H8V6FS97NTTF1VPQQDZQT973=integra%C3%A7%C3%A3o-do-aplicativo step-2-app-setup=passo-1-configura%C3%A7%C3%A3o-do-aplicativo 01H8BD2FJ61S3Z22CD01H6F39E=passo-1-configura%C3%A7%C3%A3o-do-aplicativo step-3-sdk-integration=passo-2-integra%C3%A7%C3%A3o-sdk--api 01H8BD2FJ6CY53QXVB5QC98KTT=passo-2-integra%C3%A7%C3%A3o-sdk--api step-4-attribution-setup=passo-3-configura%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o 01H8BD2FJ6Q8R83FV0XS5B93B3=passo-3-configura%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o step-5-additional-setup=passo-4-configura%C3%A7%C3%A3o-adicional 01H8BD2FJ76WD0MRCJXZH8XABN=passo-4-configura%C3%A7%C3%A3o-adicional enrich-your-knowledge=amplie-o-seu-conhecimento 01H8BD2FJ7ZV0ZYHQZ8DBTTFFK=amplie-o-seu-conhecimento related=relacionado 01H8BD2FJ748GFC4VJWWYGGN1K=relacionado 01H8BD2FJ712NGA534TCSWQGR8=dica-1 01H8BD2FJ7PRJAA1K8MESRK7VA=observa%C3%A7%C3%A3o" />

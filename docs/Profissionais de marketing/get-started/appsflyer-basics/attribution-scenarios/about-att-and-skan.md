---
title: Sobre ATT e SKAN
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Agencies
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-08-11T09:19:23Z'
  edited_at: '2026-08-19T00:09:41Z'
  id: 360011890298
  locale: pt
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/pt/articles/360011890298
---
> **Visão geral**: a partir do iOS 14.5, a Apple exige a implementação e compliance com os termos da <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency">AppTrackingTransparency</Anchor> (ATT). Ou seja, *se o seu aplicativo coleta dados sobre usuários finais e os compartilha com outras empresas para fins de rastreamento em aplicativos e sites,* você deverá usar o prompt de consentimento da ATT e obter o consentimento do usuário no aplicativo do publisher e do anunciante. Se esse não for o caso, não é necessário exibir o prompt.

![iOS14-consent-pre-ATT-enforcement-6522_Cover-image_917x480.jpg](https://files.readme.io/622b57cf6b6b7ad9472b3d072f44d9b451e82fec6b0c918427e39e9e6700602e-360019478118.jpg)

## Mensuração de atribuição na ATT

A AppsFlyer oferece diferentes soluções e métodos de atribuição. A exigência de consentimento à [ATT](/docs/about-att-and-skan#att-principles) afeta a atribuição no contexto de campanhas app-to-app pagas. Por isso, os anunciantes precisam usar um mix de soluções de atribuição e relatórios. 

No caso de campanhas app-to-app pagas, a [SKAN](/docs/about-att-and-skan#skan-solution-principles) fornece resultados determinísticos de atribuição. Outras campanhas, como as de mídias próprias, web-to-app e Apple Search Ads usam as ferramentas tradicionais da AppsFlyer. Essas ferramentas fornecem uma mensuração do LTV de longo prazo, enquanto a SKAN mensura a performance do usuário durante um curto período após a instalação.

Em resumo, para visualizar o quadro completo, é importante usar tanto as soluções tradicionais da AppsFlyer quanto a SKAN, pois elas se complementam.

Esse artigo é uma introdução à SKAN e à ATT. Ele foi criado pensando em anunciantes que já estão familiarizados com a plataforma da AppsFlyer.

<div id="skan-solution-principles" />

<Accordion title="Noções básicas">

No iOS, a AppsFlyer fornece resultados agregados de usando postbacks da SKAN. Esses postbacks são enviados pelo iOS para ad networks, que os encaminham para a AppsFlyer. Os postbacks contêm registros de atribuição anônimos enriquecidos com um valor de conversão (CV) definido pelo anunciante. O CV é uma medida da qualidade do usuário durante uma janela inicial após a instalação.

Nossa <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">solução para SKAN</Anchor> permite que os anunciantes:

* Dados da SKAN em dashboards e relatórios obtidos a partir da agregação de postbacks de todas as ad networks enriquecidas com outros pontos de dados, como custo.
* Controlem o que é mensurado, por meio do Conversion Studio, sem a necessidade de fazer alterações no código do aplicativo. O CV pode ser usado para mensurar receita, engajamentos ou eventos de conversão.

**Limitações da SKAN**

* **Campanhas:** suporte limitado, Apple Search Ads, campanhas de promoção cruzada e instalações assistidas pela web mobile.
* **Período de mensuração:** limitado a poucos dias.

**Fluxo da SKAN**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. O anunciante define as configurações de mensuração da SKAN no Conversion Studio da AppsFlyer.
2. O usuário abre o aplicativo pela primeira vez.
3. Durante cada janela, a AppsFlyer define o CV com base nas ações do usuário e no esquema de valores de conversão configurado.
4. Depois que a janela fecha, o iOS envia o postback para a ad network e uma cópia desse postback para a AppsFlyer. Ele pode chegar com atraso:
   * Para a 1ª janela de mensuração da SKAN 4: 24-48 horas
   * Para a 2ª-3ª janelas de mensuração da SKAN 4: 24-144 horas
   * Para SKAN 3: 24-48 horas após o aumento mais recente no CV.
5. Cópias de postback enviadas diretamente do dispositivo iOS para a AppsFlyer são encaminhadas para o endpoint definido pelo anunciante. Saiba como <Anchor target="_blank" href="/marketers/pt/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">enviar cópias de postback da SKAN para a AppsFlyer.</Anchor>
6. A ad network encaminha um postback enriquecido para a AppsFlyer ou a SRN comunica dados de postback por API.
7. A AppsFlyer valida e decodifica o CV. Os dados decodificados são registrados e atribuídos antes de serem disponibilizados por meio de dashboards, relatórios e APIs.

</Accordion>

<div id="att-principles" />

<Accordion title="Princípios da ATT">

O prompt da ATT é usado para receber o consentimento explícito para a coleta e compartilhamento de dados dos usuários. A partir do iOS 14.5, o IDFA está disponível apenas caso o usuário permita o rastreamento no prompt.

Tanto os aplicativos do publisher quanto do anunciante devem exibir o prompt. Se o usuário der seu consentimento nos dois apps, isso significa que ele concorda em ser *rastreado* e os anunciantes recebem a permissão da Apple para o rastreio entre aplicativos de diferentes empresas.

**Configurando a ATT**

A ATT pode ser configurada de acordo com a tabela abaixo. A configuração inicial definida pelo iOS é "não determinado" ou "restrito".

Considere que o uso do prompt de consentimento para converter um usuário de *não determinado* para *autorizado* é opcional. No entanto, se você não exibir o prompt, não poderá obter *authorization.*

| Valor ATT | Consentimento  <br />(IDFA disponível) | Observações |
| --- | --- | --- |
| Restrito | Não | <ul><li>Definido pela Apple com base na idade do usuário, ou outros critérios. Não pode ser alterado pelo usuário do dispositivo.</li><li>O prompt não pode ser exibido para esses usuários.</li></ul> |
| Não determinado (até iOS 14.4) | Sim | Valor padrão |
| Não determinado<br /><br />(a partir do iOS 14.5) | Não | Valor padrão |
| Negado | Não | Ocorre quando:<ul><li>Esse valor foi definido antes da exibição do prompt</li><li>O usuário desativou a opção *permitir solicitações* (no nível do dispositivo)</li><li>Antes que o usuário instalasse o iOS 14 no dispositivo, a opção LAT estava ativada</li></ul> |
| Autorizado | Sim | Esse valor foi definido antes da exibição do prompt |

**Consequências da ATT**

Com a ATT, muitos usuários podem optar por negar o consentimento, fazendo com que o IDFA não fique disponível e impossibilitando o rastreamento. Como resultado, anunciantes que dependiam de relatórios de atribuição no nível do usuário agora terão que usar métodos agregados. <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">Modelos de atribuição da AppsFlyer</Anchor>.

Os dados de atribuição são recebidos de diversas fontes. O identificador coletado e usado por cada uma é diferente. A maioria dos dados são exibidos usando ferramentas de atribuição tradicionais. No entanto, para atribuições feitas pela SKAN, os relatórios podem ser acessados no dashboard da SKAN.

</Accordion>

<div id="which-dashboard-has-the-install" />

<Accordion title="Onde posso visualizar as instalações?">

No iOS 14, uma instalação pode ser atribuída nos dashboards tradicionais e no dashboard da SKAN. Além disso, dependendo do contexto do canal de mídia, ela pode ser atribuída como orgânica em um dashboard e como não orgânica em outro.

</Accordion>

## iOS attribution and privacy: conhecimentos importantes

#### Artigos e links sobre iOS 14 e SKAN

| Área | Artigo | FAQ, discrepâncias e comparações |
| --- | --- | --- |
| SKAN | <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">Campos de dados brutos da SKAN</Anchor> | Campos adicionais de dados brutos com suporte para did\_win e SKAN 3.0 |
| SKAN | <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Solução SKAN</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Tempo entre a instalação do aplicativo e a atualização do dashboard</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#organic-metrics-in-the-context-of-skadnetwork">Métricas orgânicas no contexto da SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#appsflyer-attribution-vs-skan-attribution">Atribuição da AppsFlyer vs. atribuição da SKAN</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#faq-skan-discrepancies">Perguntas frequentes: discrepâncias da SKAN</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/pt/docs/skan-interoperation">Interoperabilidade com parceiros da SKAN</Anchor> (seção do artigo) | <Anchor target="_blank" href="/marketers/pt/docs/skan-integrated-partners-list">Lista de parceiros integrados da SKAN</Anchor> |
| SKAN | <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-interoperation-with-meta-ads">Integração Meta ads e AppsFlyer</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq">Solução de problemas e discrepâncias</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook">Diferenças de mensuração e tempo</Anchor></li></ul> |
| SKAN | <Anchor target="_blank" href="/marketers/pt/docs/skan-interoperation-with-snapchat">Interoperação Snapchat e AppsFlyer</Anchor> | <Anchor target="_blank" href="/marketers/pt/docs/skan-interoperation-with-snapchat#discrepancies-guide">Guia de discrepâncias</Anchor> |
| Privacidade | <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada Agregada (AAP)</Anchor> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework#recursos-afetados-pela-aap">Recursos afetados pela AAP</Anchor></li></ul> |
| Privacidade | <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">Canais de mídia restritos</Anchor> | <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">Campos de dados brutos restritos</Anchor> |
| iOS 14 | <Anchor target="_blank" href="/marketers/pt/docs/preparing-for-the-app-store-review-nutrition-labels">Tabelas nutricionais—prepare-se para a avaliação da App Store</Anchor> |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">Configurando a ATT no app</Anchor> (orientações para desenvolvedores) |  |
| iOS 14 | <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">Sobre redes de autorrelato (SRNs) como Google, Meta ads, etc.</Anchor> | <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#ios-145-srn-attribution">Onde posso visualizar as instalações de SRNs?</Anchor> |
| Cobrança | <Anchor target="_blank" href="https://content.appsflyer.com/ios-14-hub/billing/">Faturamento para aplicativos iOS</Anchor> |  |

<div id="ios-14-impact-on-attribution-and-measurement" />

<Accordion title="Impacto da disponibilidade do IDFA na atribuição e na mensuração">

#### **Métricas**

Considere que, quando um IDFA não está disponível, as seguintes métricas podem ser afetadas:

| Métricas | Aumenta | Diminui | Observações |
| --- | --- | --- | --- |
| Não orgânico vs. orgânico | Orgânico | Não orgânico |  |
| Reinstalações vs. instalações | Instalações | Reinstalações |  |
| Redirecionamento | Instalações orgânicas e eventos in-app | Reengajamentos, reatribuições |  |
| Apple Search Ads | -- | -- | Inalterado. Todos os usuários são atribuídos corretamente, independentemente do status da ATT. |

#### **Deep linking**

O deferred deep linking usando o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-legacy-apis#deferred-deep-linking">método onConversionDataSuccess</Anchor> pode não funcionar para a versão 14.5+, pois ele exige dados de atribuição que podem não estar disponíveis por motivos de privacidade.

Recomendamos o uso de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl-1">unified deep linking (UDL)</Anchor>. O UDL cumpre com os padrões de privacidade do iOS 14.5+, utilizando apenas parâmetros relevantes para o deep linking e deferred deep linking: `deep_link_value` e `deep_link_sub1`. Parâmetros de atribuição como `media_source`, `campaign` e `af_sub1-5` retornam nulos e não podem ser usados para fins de deep linking.

</Accordion>

## Perguntas frequentes sobre iOS 14, ATT e SKAN

<div id="what-happens-to-an-app-using-an-sdk-version-before-v6" />

<Accordion title="O que acontece quando um aplicativo está usando uma versão do SDK anterior à 6+?">

Para apps que usam uma versão anterior à 6.0:

* a SKAdNetwork e o Apple Search Ads não funcionam.
* Se você enviar o aplicativo para a App Store, ele será rejeitado.

Para apps que usam uma versão anterior à 6.10: a SKAN 4 não funciona.

</Accordion>

<div id="is-it-mandatory-to-display-the-att-prompt" />

<Accordion title="É obrigatório exibir o prompt da ATT?">

Não. Você só precisa solicitar o consentimento da ATT se quiser *rastrear* um usuário, coletar IDFA ou ambos.

</Accordion>

## Perguntas frequentes—SKAN

<div id="how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4" />

<Accordion title="Como posso saber quando receberei postbacks e se serão da SKAN 3 ou SKAN 4?">

O tipo de postback recebido é determinado por inúmeros fatores, incluindo o modo definido no Conversion Studio, a ad network utilizada e versões do iOS no dispositivo dos usuários.

Esses fatores podem afetar:

* A versão do postback: SKAN 3 ou SKAN 4. <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#principles-and-flow">Saiba mais</Anchor>
* Janela 1 (AW): para a SKAN 4, ela é de 48 horas. Para a SKAN 3, ela se baseia na janela de atividade. Obs.: se o Conversion Studio não estiver configurado para SKAN 4, mas a assinatura da ad network sim, a janela se baseará na janela de atividades ou em 48 horas, a depender de qual for menor.
* Atraso no postback: horas após a instalação, quando o postback da SKAN chega. Isso depende do momento em que a janela fecha. <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide?query=skan%20faq#timing-from-app-install-until-dashboard-and-reports-update">Saiba mais</Anchor>
* Timer contínuo: para SKAN 3, a janela de atividade pode ser estendida em até 63 dias; o postback só chega depois que a janela fecha.

O fluxograma a seguir explica isso em mais detalhes.

![SKAN_4_matrix_-_Page_8__1_.png](https://files.readme.io/0dbd4cae34d9f9fed80dbe835485789dab75d46dbb38de055f454d01efb97350-13756140934545.png)

</Accordion>

<div id="in-skan-am-i-limited-to-100-campaign-ids-per-ad-network" />

<Accordion title="Na SKAN, só posso ter um número limitado de IDs de fonte/campanha por ad network?">

Sim. Antes, o limite era de 100 IDs de campanha. A partir da SKAN 4, os IDs de campanha são chamados de identificadores de fontes hierárquicos, com um limite de 10.000. O identificador de fonte é um número inteiro de 4 dígitos.

As ad networks mapeiam o identificador de fonte para o ID da campanha.

</Accordion>

<div id="what-is-the-use-case-for-skan-raw-data" />

<Accordion title="Qual é o uso dos dados brutos da SKAN?">

* Use dados brutos para agregar dimensões que não estão disponíveis por meio de APIs agregadas.
* Ajuste facilmente os processos de importação para consumir dados brutos da SKAN.

</Accordion>

<div id="why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio" />

<Accordion title="Por que os valores de conversão que recebo não correspondem à minha configuração no Conversion Studio?">

Geralmente, isso ocorre porque outro SDK em seu aplicativo tem a capacidade de definir valores de conversão, gerando um conflito com seu SDK da AppsFlyer e com os valores de conversão que você configurou na plataforma. Certifique-se de não ter outro SDK que defina valores de conversão em seu aplicativo.

</Accordion>

<div id="why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports" />

<Accordion title="Por que os dados agregados no meu dashboard da SKAN não correspondem aos dados brutos em meus relatórios do Data Locker?">

No geral, essas discrepâncias ocorrem pois você está analisando os relatórios do Data Locker no lugar errado. Dados do Google podem levar até 13 dias para serem recebidos. Já nos relatórios de dados brutos, os dados são gravados no dia em que são recebidos, e não cumulativamente. Portanto, para obter métricas corretas para instalações relacionadas a uma data específica, você também precisa analisar todos os relatórios 13 dias após essa data.

Exemplo: no relatório de 12 de junho, vemos 100 instalações do Google, que ocorreram no dia 11 de junho. No relatório de 24 de junho, vemos que MAIS 100 instalações ocorreram em 11 de junho. Você precisará analisar todos os relatórios dos últimos 13 dias (de 12 a 24 de junho) e agregá-los com base no horário de instalação ou no timestamp da ad network para ter uma leitura precisa do total de 200 instalações ocorridas em 11 de junho.

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/getting-started-onboarding-for-marketers#passo-3-configuração-de-atribuição">Introdução: passo a passo da AppsFlyer</Anchor>

<div data-zendesk-anchors="attribution-measurement-in-an-att-environment=mensura%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-na-att h_01HE0C8YXSXSX003X0671Z97KZ=mensura%C3%A7%C3%A3o-de-atribui%C3%A7%C3%A3o-na-att h_01HE0C8YXSCA8M57F1RG4CJ7HK=skan-solution-principles h_01HE0C8YXSSCTQJAPDE27FB1H8=att-principles h_01HE0C8YXS0BFA2M16D1Q2PQYW=which-dashboard-has-the-install ios-14-important-knowledge=ios-attribution-and-privacy-conhecimentos-importantes h_01HE0C8YXS3BH109DF1Y1KNK5P=ios-attribution-and-privacy-conhecimentos-importantes ios-14-and-skan-articles-and-links=artigos-e-links-sobre-ios-14-e-skan h_01HE0C8YXSPZKBWXC51Z2636R0=artigos-e-links-sobre-ios-14-e-skan h_01HE0C8YXSTCVA8YYR4BQVHVXS=ios-14-impact-on-attribution-and-measurement metrics=m%C3%A9tricas h_01HE0C8YXSJMYN81FKPCA8ATK7=m%C3%A9tricas h_01HE0C8YXS6ADG1SQCMVP0W69B=deep-linking faq%E2%80%94ios-14=perguntas-frequentes-sobre-ios-14-att-e-skan h_01HE0C8YXSV9VSK1NPG9RCTQW1=perguntas-frequentes-sobre-ios-14-att-e-skan h_01HE0C8YXS1FFYQJ8YZXP9W9ZV=what-happens-to-an-app-using-an-sdk-version-before-v6 h_01HE0C8YXSKA0325YJSXV81ZB9=is-it-mandatory-to-display-the-att-prompt faq%E2%80%94skan=perguntas-frequentesskan h_01HE0C8YXSQKH8ER1Q5VS6Z0NM=perguntas-frequentesskan how-do-i-know-when-i%E2%80%99ll-receive-postbacks-and-if-they%E2%80%99ll-be-skan-3-or-skan-4=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXS44YXAN2DV2ZR03GE=how-do-i-know-when-i-ll-receive-postbacks-and-if-they-ll-be-skan-3-or-skan-4 h_01HE0C8YXSCWM892QH0N7YQ8HP=in-skan-am-i-limited-to-100-campaign-ids-per-ad-network h_01HE0C8YXSSWHV45M6P7SQGCRD=what-is-the-use-case-for-skan-raw-data h_01HE0C8YXS8GJKFC23S1R9TWW0=why-dont-the-conversion-values-i-receive-match-my-configuration-in-appsflyer-conversion-studio why-doesn%E2%80%99t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE0C8YXS1VW1T50ARJE0MP62=why-doesn-t-the-aggregate-data-in-my-skan-dashboard-match-the-raw-data-numbers-in-my-skan-data-locker-reports h_01HE7SNR02VQDKG55QP06ECNAR=veja-tamb%C3%A9m" />

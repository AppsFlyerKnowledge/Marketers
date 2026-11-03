---
title: Suporte à política de consentimento do Google na UE
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2024-02-07T07:28:17Z'
  edited_at: '2026-08-19T00:33:12Z'
  id: 22310731147153
  locale: pt
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/pt/articles/22310731147153
---
> **Resumo:** queremos ajudar os profissionais de marketing a cumprir com o Digital Markets Acs (DMA, também conhecido como Lei dos Mercados Digitais) e melhorar seus anúncios no Google. Encontre respostas para as perguntas mais frequentes sobre a compliance com o DMA e a otimização de anúncios.

## Visão geral

O Google está atualizando sua <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">política de consentimento na UE</Anchor> em preparação para o <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">Digital Markets Act (DMA)</Anchor>. Como uma <Anchor target="_blank" href="https://ads.google.com/lp/appcampaigns/attribution/">parceira de atribuição de aplicativos</Anchor> do Google, a AppsFlyer está fazendo as mudanças necessárias para se adaptar à nova política e garantir que anunciantes tirem o máximo proveito de seus anúncios no Google. A política atualizada entrou em vigor em 6 de março de 2024.

## Integrações relevantes e uso ininterrupto dos recursos do Google

<div id="which-integrations-are-involved" />

<Accordion title="Quais são as integrações relevantes?">

As seguintes integrações são relevantes para a nova política de consentimento:

* Anúncios do Google (`googleadwords_int`)
* GMP DV360 (`dv360_int`)

Se os usuários finais adquiridos por meio dessas integrações estiverem localizados no Espaço Econômico Europeu (EEE), tome as medidas necessárias para cumprir com os requisitos da nova política de consentimento do Google na UE.

> 📘 **Importante!**
>
> A integração [legada] Google Marketing Platform DV360/CM (`doubleclick_int`) será desativada e não será compatível com a nova política. Se você usa essa integração, recomendamos que você faça a <Anchor target="_blank" href="/marketers/pt/docs/bulletin-google-marketing-platform-gmp-integration-transition">transição para a nova integração DV360 (dv360\_int)</Anchor>.

</Accordion>

<div id="what-must-i-do-to-continue-using-googles-features" />

<Accordion title="O que deve ser feito para continuar usando os recursos do Google">

Para continuar usando recursos do Google Ads e GMP DV360, é necessário que os usuários dentro do EEE permitam o uso de seus dados pessoais para fins de mensuração, personalização de anúncios e remarketing.

</Accordion>

## Atualizando o SDK da AppsFlyer.

<div id="what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk" />

<Accordion title="Etapas necessárias para implementar dados de consentimento via SDK da AppsFlyer">

O SDK da AppsFlyer (Android - v6.13.0+, iOS - v6.13.1+) envia dados de consentimento necessários a cada evento, seguindo as diretrizes do Google.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">Atualize seu SDK</Anchor> para a versão mais recente (Android - v6.13.0+, iOS - v6.13.1+), para aplicativos Android ou iOS. Isso se aplica a apps do Android e iOS.
* Feito isso, <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">clique aqui</Anchor> e siga as instruções de implementação para compatibilidade com o DMA.

</Accordion>

## Enviando dados de consentimento

<div id="how-do-i-send-consent-data-to-appsflyer" />

<Accordion title="Como enviar dados de consentimento para a AppsFlyer">

Você tem duas opções:

* [**Diretamente via SDK**](#atualizando-o-sdk-da-appsflyer) **ou via S2S API**: profissionais de marketing podem enviar dados de consentimento diretamente para a AppsFlyer usando o SDK. Isso se aplica a apps do Android e iOS.
* **Via TCF Strings:** se você usa ou pretende usar uma Plataforma de Gestão de Consentimento (CMP), você pode enviar os campos de dados por meio de IAB TCF strings (TCF V2.2) padrão. Lembre-se de incluir o Google vendor ID (755) na lista de fornecedores autorizados.

Assim, a AppsFlyer permite que os clientes enviem sinais de consentimento ao Google. No entanto, é importante observar que a AppsFlyer não coleta, altera ou controla o consentimento dos usuários finais. Profissionais de marketing que trabalham com o Google são responsáveis por coletar os campos de consentimento necessários.

Veja <Anchor target="_blank" href="https://appsflyer.wistia.com/medias/0tnlyre8ai">esse vídeo</Anchor> sobre como enviar dados de consentimento para a AppsFlyer.

</Accordion>

<div id="which-consent-values-does-appsflyer-send-to-google" />

<Accordion title="Valores de consentimento que a AppsFlyer envia para o Google">

Os dados de consentimento das integrações relevantes (`googleadwords_int` e `dv360_int`) são enviados para o Google usando os campos abaixo:

| Campo AppsFlyer | Campo Google (1) | Valores | Campo explicado |
| --- | --- | --- | --- |
| <span id="gdpr_applies"></span>gdpr\_applies | eea | verdadeiro/falso (2) | O DMA se aplica a esse usuário? |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | personalização\_de\_anúncio | verdadeiro/falso | O utilizador deu consentimento à Google para utilizar os seus dados em publicidade personalizada? |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | dados\_do\_utilizador\_anúncio | verdadeiro/falso | O usuário permitiu o compartilhamento de seus dados com o Google? |

1. Veja qual é a <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">definição do Google para cada campo</Anchor>.
2. Quando o DMA não se aplica ao usuário, a AppsFlyer sugere evitar o envio de campos de consentimento além de `gdpr_applies=false`

</Accordion>

### Enviando dados de consentimento—FAQ

<div id="do-i-have-control-over-consent-data-for-nonue-users" />

<Accordion title="Existe a opção de não enviar dados de consentimento para o Google?">

Quando o DMA não se aplica aos seus usuários finais (por exemplo, caso eles estejam fora da UE), a AppsFlyer oferece a opção de não enviar dados de consentimento para o Google. Para isso, basta ativar o botão relevante nas páginas de integração.

> 🚧 **Importante!**
>
> Antes de usar essa opção, recomendamos que os anunciantes recebam a aprovação das suas equipes jurídica e de privacidade, para certificar-se de que essa decisão se alinha com suas políticas internas. Como referência, veja o <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">artigo sobre o modo de consentimento</Anchor> do Google.

**Para não compartilhar dados de consentimento com o Google:**

1. Na AppsFlyer, no menu lateral, selecione **Colaboração** > **Integrações ativas**.
2. Procure pelo parceiro e clique em **Gerenciar integração**.
3. Na aba de configuração da integração, ative **usuários fora da UE**

<Image alt="Alternância para usuários não pertencentes à UE na guia de configuração da integração" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="595px" />

</Accordion>

<div id="is-consent-needed-for-mobile-web-events" />

<Accordion title="É necessário consentimento para eventos de web mobile?">

Nesse estágio, apenas eventos de aplicativos mobile são compartilhados com o Google, portanto, não há necessidade de compartilhar com dados consentimento para eventos da web para a AppsFlyer. Se os usuários forem da web para o seu aplicativo, o consentimento deles será coletado dentro do aplicativo em um estágio posterior.

</Accordion>

<div id="which-countries-does-googles-eu-consent-policy-cover" />

<Accordion title="Para quais países o consentimento do DMA se aplica?">

O Digital Markets Act (DMA) se aplica a usuários dentro da UE e do EEE (Espaço Econômico Europeu) e, portanto, <Anchor target="_blank" href="https://www.gov.uk/eu-eea">afeta esses países</Anchor>. Embora **o Reino Unido e a Suíça** não façam parte da UE, o Google estendeu sua política de consentimento para incluir esses países também.

</Accordion>

<div id="whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way" />

<Accordion title="Qual é a forma recomendada de pedir consentimento do usuário dentro da compliance?">

A AppsFlyer recomenda consultar sua equipe jurídica para garantir o consentimento em compliance com o DMA. Embora <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14009343?hl=en&sjid=3762335249108620505-NC#app-consent">o Google forneça instruções gerais</Anchor>, ele não sugere uma linguagem específica para os prompts.

</Accordion>

<div id="how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags" />

<Accordion title="Como a AppsFlyer está traduzindo as strings TCF para as flags de consentimento do DMA do Google?">

Depois que a AppsFlyer recebe as strings TCF do seu CMP (seja através do SDK da AppsFlyer ou S2S), elas são processadas e traduzidas nos servidores da AppsFlyer. A seguinte tradução é mapeada e enviada ao Google, conforme recomendado pelo Google:

| Strings coletadas pela AppsFlyer | Flags de consentimento do Google | Descrição |
| --- | --- | --- |
| `gdpr_applies=1/0` | `eea=1/0` | Identifica se o DMA se aplica ou não ao respectivo usuário |
| `dados_do_utilizador_anúncio` | `ad_user_data=1` | Quando o consentimento é dado ao Google para o propósito 1 e o consentimento/interesse legítimo é dado ao Google para o propósito 7 |
| `dados_do_utilizador_anúncio` | `ad_user_data=0` | Quando o consentimento não é dado ao Google para o propósito 1 **e/ou** o consentimento/interesse legítimo não é dado ao Google para o propósito 7 |
| `personalização_de_anúncio` | `ad_personalization=1` `ad_personalization=0` | Quando o consentimento é dado ao Google para os propósitos 3 e 4Quando o consentimento não é dado ao Google para os propósitos 3 e 4 |

</Accordion>

<div id="if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk" />

<Accordion title="Preciso atualizar tanto os SDKs da AppsFlyer quanto do Firebase para enviar dados de consentimento?">

Sim. O Google exige que os dados de consentimento sejam incluídos em cada evento enviado da AppsFlyer, pois o Google não mescla os dados de consentimento do usuário do Firebase com os dados enviados da AppsFlyer. Portanto, os dados de consentimento devem ser enviados para a AppsFlyer, que os encaminha para o Google. Da mesma forma, compartilhar dados de consentimento apenas com a AppsFlyer é insuficiente para os requisitos do SDK do Firebase. Isso significa que você deve enviar os dados tanto para a AppsFlyer quanto para o Firebase.

</Accordion>

## Preparando-se para as mudanças que estão por vir

<div id="how-can-i-prepare-for-the-upcoming-changes" />

<Accordion title="Siga as seguintes etapas">

#### Consentimento do usuário no Espaço Econômico Europeu (EEE)

Colabore com a assessoria jurídica da sua empresa. Eles podem oferecer insights sobre as implicações das políticas de consentimento de usuários europeus para os dados que você compartilha com parceiros como o Google. Se for relevante, use notificações de privacidade como "configurações de privacidade" ou "opções de privacidade" para coletar o consentimento do usuário para fins de marketing e publicidade.

#### CPM Compliance e compatibilidade com TCF 2.2

Certifique-se de que a sua Plataforma de Gestão de Consentimento (CMP) é compatível com o TCF 2.2, que é a versão mais atualizada do Transparency and Consent Framework (TCF). Seu TCF também deve estar ciente das novas diretrizes de consentimento do Google para a UE, podendo aconselhá-lo sobre como oferecer o suporte necessário via TCF.

#### Implementar as versões mais recentes do SDK/Server-to-Server (S2S) APIs

Veja algumas das opções para enviar os novos campos de consentimento usando o SDK ou as chamadas da S2S API:

* **Usando o SDK:**
  * Implemente a versão mais recente do SDK da AppsFlyer (Android - v6.13.0+, iOS - v6.13.1+) para aplicativos iOS e Android
  * Defina como será o <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">envio dos dados de consentimento</Anchor>
* Usando chamadas de <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile?">S2S</Anchor> API :
  * Antes de enviar eventos in-app para a AppsFlyer, atualize suas chamadas de API, incluindo o objeto `consent_data` para cada evento. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">Clique aqui</Anchor> para mais informações.

#### Transição da integração legada GMP (DoubleClick)

Se você ainda estiver usando a integração GMP legada (doubleclick\_int), recomendamos que você complete a transição para a versão mais recente (dv360\_int) no primeiro trimestre de 2024. A integração legada **não é compatível com as novas diretrizes de consentimento da UE** e será desativada em breve. Mais detalhes <Anchor target="_blank" href="/marketers/pt/docs/bulletin-google-marketing-platform-gmp-integration-transition">aqui</Anchor>.

</Accordion>

## Impacto na atividade publicitária—FAQ

<div id="how-will-the-upcoming-change-impact-my-remarketing-campaigns" />

<Accordion title="Como essa mudança impacta a atribuição da minha campanha?">

Usuários da UE que não permitirem que seus dados sejam usados para fins de publicidade (`ad_user_data=0`) não serão atribuídos pelo Google Ads e DV360. Isso significa que a AppsFlyer também não poderá atribuí-los.

Existem alguns casos extremos em que o Google e a AppsFlyer ainda podem realizar a atribuição quando ad\_user\_data=0, com base na interpretação do Google sobre a regulamentação do DMA.

</Accordion>

<div id="how-will-the-upcoming-change-affect-my-audiences" />

<Accordion title="Como isso afetará o Audiences?">

Essas alterações podem afetar o número de usuários do espaço econômico europeu que fazem parte da sua audiência e que são expostos a campanhas de remarketing no Google. Usuários localizados no EEE terão que permitir o compartilhamento de dados antes que suas informações sejam compartilhadas com o Google. Aqueles que não derem seu consentimento serão excluídos das audiências do Google e não serão expostos às suas campanhas. Assim, você pode estar se perguntando sobre como obter o consentimento dos seus usuários e como isso pode afetar seus esforços de publicidade. <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy#eu-digital-markets-act">Saiba mais sobre possíveis alterações no Audiences.</Anchor>

</Accordion>

## Mais informações e detalhes de contato

Nesse caso, veja abaixo:

* Para dúvidas sobre as novas diretrizes ou sobre como essas atualizações podem afetar seus dados, consulte <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy-help/">os artigos de ajuda do Google</Anchor> ou entre em contato diretamente com seu representante do Google.
* Para dúvidas sobre a compatibilidade da AppsFlyer com os campos de consentimento de usuários da UE, entre em contato com seu CSM da AppsFlyer ou envie um e-mail para [hello@appsflyer.com](mailto:hello@appsflyer.com).
* Como referência, veja o <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">artigo sobre o modo de consentimento</Anchor> do Google.

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide">Integração adicional com SDK</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/bulletin-google-marketing-platform-gmp-integration-transition">Migrar para a nova integração do DV360</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy">Política de identificadores de utilizador para públicos-alvo</Anchor>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HP195KV35FD6X67WTMXJWWSZ=vis%C3%A3o-geral relevant-integrations-and-continued-use-of-google-features=integra%C3%A7%C3%B5es-relevantes-e-uso-ininterrupto-dos-recursos-do-google h_01HP1M37V1CYW5T5E4K1ES3NQA=integra%C3%A7%C3%B5es-relevantes-e-uso-ininterrupto-dos-recursos-do-google 01HP1KN2H7NTS2V1S2PGF0C41N=which-integrations-are-involved h_01HP2HRPJR72Z0R5VEG5N36CN2=importante h_01HP1K1088SJK60QRSTQF4WF6S=what-must-i-do-to-continue-using-googles-features updating-the-appsflyer-sdk=atualizando-o-sdk-da-appsflyer h_01HP1Z2G2M56DDQS9T47GMCFHJ=atualizando-o-sdk-da-appsflyer h_01HP1ZASRQGABCEFV67P961XAV=what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk how-consent-data-is-sent=enviando-dados-de-consentimento h_01HP1KPSMCH3EG373BWVQZM4ZT=enviando-dados-de-consentimento h_01HP1JJ2AYHYJET9GYMXA93E86=how-do-i-send-consent-data-to-appsflyer h_01HP1JJ2AYWRBREW5GD0KPDF1R=which-consent-values-does-appsflyer-send-to-google sending-consent-data%E2%80%94faq=enviando-dados-de-consentimentofaq h_01HR1X08VZ5MEAV01E9X54KAQS=enviando-dados-de-consentimentofaq h_01HP1JJ2AYZ57G0GMR8QRDTEZ7=do-i-have-control-over-consent-data-for-nonue-users h_01HP2MRPFA2ECJGAZ93NQHVD2J=importante-1 01HVE9TVZWTRW3VQ8TSXWA13QM=is-consent-needed-for-mobile-web-events h_01JVYS49FCZT3Z91KNACNR6GET=which-countries-does-googles-eu-consent-policy-cover h_01HRXZYZJBDTP8CHJDHQ187CTN=whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way 01HR6SD3PBWN5X9AHT66ZADQ3R=how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags 01J2V4XRKRSEPA6KPJFMSTHE1F=if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk what-i-can-do-on-my-side=preparando-se-para-as-mudan%C3%A7as-que-est%C3%A3o-por-vir 01HR1XYXRDVEW6H9Q3WP17E2N3=preparando-se-para-as-mudan%C3%A7as-que-est%C3%A3o-por-vir h_01HP1JJ2AYFHRRDYZS8YFYE6WP=how-can-i-prepare-for-the-upcoming-changes address-user-consent-in-the-european-economic-area-eea-and-in-the-uk=consentimento-do-usu%C3%A1rio-no-espa%C3%A7o-econ%C3%B4mico-europeu-eee h_01HPGNBQCTJFVZR99BY6E5J2JF=consentimento-do-usu%C3%A1rio-no-espa%C3%A7o-econ%C3%B4mico-europeu-eee verify-cmp-compliance-and-tcf-22-support=cpm-compliance-e-compatibilidade-com-tcf-22 h_01HPGNC0HAMA7Z0B4DNV2QSFYG=cpm-compliance-e-compatibilidade-com-tcf-22 implement-the-newest-sdkservertoserver-s2s-apis=implementar-as-vers%C3%B5es-mais-recentes-do-sdkserver-to-server-s2s-apis h_01HPGNCAG3M9XPHDTP03WHQQ9F=implementar-as-vers%C3%B5es-mais-recentes-do-sdkserver-to-server-s2s-apis transition-from-the-legacy-gmp-integration-doubleclick=transi%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o-legada-gmp-doubleclick h_01HPGNCHP6SSFCVZ3P4AG0N1FB=transi%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o-legada-gmp-doubleclick impact-on-my-advertising-activity=impacto-na-atividade-publicit%C3%A1riafaq h_01HP1PKNZN32TQYHGJNNM3JFVZ=impacto-na-atividade-publicit%C3%A1riafaq h_01HP1PKNZN0VJGYAPFHR5JVV5H=how-will-the-upcoming-change-impact-my-remarketing-campaigns h_01HP4K2ZJW11BFSKNPRH7FA092=how-will-the-upcoming-change-affect-my-audiences further-information-and-contact-details=mais-informa%C3%A7%C3%B5es-e-detalhes-de-contato h_01HQ2VJES04CYF4J8YBB4GQS73=mais-informa%C3%A7%C3%B5es-e-detalhes-de-contato h_01KZZYSDB33GZ47RSDRP9ACAH0=consulte-tamb%C3%A9m" />

---
title: Mensuração de Eventos Agregados (AEM) do Meta Ads para iOS
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
  created_at: '2023-10-09T16:40:55Z'
  edited_at: '2026-10-27T03:47:30Z'
  id: 19228737402129
  locale: pt
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/pt/articles/19228737402129
---
> **Resumo:** Saiba mais sobre a solução Aggregated Event Measurement (AEM) para otimizar conversões e eventos in-app no iOS e atribuir reengajamentos no iOS no Meta Ads.

<div id="overview" />

## Resumo

A AppsFlyer oferece suporte para a <Anchor target="_blank" href="https://www.facebook.com/business/help/721422165168355">Mensuração de Eventos Agregados (AEM) do Meta Ads</Anchor>. Com essa solução, você pode mensurar eventos da web e de aplicativos para iOS 14+ usando os seguintes métodos de atribuição:

* [AEM para reengajamento](#app-aem-para-reengajamento)
* [AEM para promoção de aplicativos](#app-aem-para-promo%C3%A7%C3%A3o-de-aplicativos)

Como parte da AEM, a Meta aceita conversões e postbacks dentro do aplicativo da AppsFlyer, desde que os eventos estejam qualificados para a mensuração. Para descobrir isso:

* [Verifique se os eventos do seu aplicativo são elegíveis para a AEM](#verificar-elegibilidade)

<div id="app-aem-for-re-engagement" />

## AEM para reengajamento

Com a AEM, o Meta Ads fornece atribuição de reengajamento por deep link para usuários de iOS quando o ID do anunciante não está disponível.

<div id="attribution-flow" />

### Fluxo de atribuição

O Meta Ads anexa dados de atribuição ao deep link junto com o identificador `campaign_ids` da AEM. A AppsFlyer recebe e processa os parâmetros da campanha mostrados na URL do deep link e, em seguida:

* Envia os dados de relatórios agregados de volta para o Meta Ads
* Executa a atribuição com base nas informações do deep link anexadas pelo Meta Ads
* Inclui dados de atribuição do deep link em dados brutos e relatórios de dados agregados

<div id="attribution-data-parameters" />

### Parâmetros de dados de atribuição

Estes parâmetros de dados de atribuição, conforme compartilhados pelo Meta Ads, estão incluídos nos relatórios:

* `id_anúncio`
* `adgroup_id`
* `id_da_campanha`
* `campaign_group_id`
* `account_id`

<div id="note" />

> 📘 **Atenção**
>
> Para aproveitar a AEM no remarketing, o SDK da AppsFlyer recupera a string `campaign_ids` na abertura do deep link. Por padrão, o SDK compartilha deep links de todos os domínios. Se você tiver personalizado sua integração, verifique se ela está configurada para compartilhar deep links de todos os domínios, incluindo o domínio da Meta, e não apenas do domínio da AppsFlyer.

<div id="faqs-on-deep-link-re-engagement-attribution" />

### Perguntas frequentes sobre a atribuição de reengajamento de deep links

<div id="what-must-the-advertiser-do-to-enable-this-attribution" />

<Accordion title="O que o anunciante deve fazer para ativar essa atribuição?">

**Nenhuma ação é necessária** para que o anunciante receba esses parâmetros para atribuição.

No entanto, para mensurar a atribuição de reengajamento de deep link, a **opção de alternância de atribuição de reengajamento** **deve estar ativada**.

**Observação:** De acordo com os termos e condições do Meta Ads sobre a AEM, ativar a mensuração da atribuição de reengajamento significa que os postbacks para o Meta Ads podem incluir endereços IP parciais como parte dos dados de atribuição.

</Accordion>

<div id="what-about-agencies-and-meta-campaign-management-partners" />

<Accordion title="E como ficam as agências e os parceiros de gerenciamento de campanhas da Meta?">

Atualmente, a atribuição para agências e parceiros de gerenciamento de campanhas da Meta não é válida. Isso significa que todo o tráfego é atribuído ao Meta Ads. Isso é temporário e mudará em breve.

</Accordion>

<div id="are-there-any-restrictions-on-data-from-this-attribution" />

<Accordion title="Há alguma restrição sobre os dados dessa atribuição?">

Os dados provenientes de atribuições de deep links não estão sujeitos a restrições de relatórios. Isso significa que todos os dados aparecem nos relatórios brutos agregados e em nível de usuário.

</Accordion>

<div id="app-aem-for-app-promotion" />

## AEM para promoção de aplicativos

<div id="aem-eligibility" />

### Elegibilidade da AEM

Quando um aplicativo é elegível para AEM no Meta Ads, a **Aggregated Event Measurement** é selecionada por padrão durante a criação do conjunto de anúncios. Isso significa que tanto a AEM quanto a SKAdNetwork (SKAN) podem ser usadas simultaneamente para a campanha. Se **Apple SKAdNetwork** for selecionada, somente a SKAN se aplicará à campanha. Isso significa que a AppsFlyer tem capacidade limitada para mensurar a atividade do aplicativo no Meta Ads.

<Image align="center" alt="aem_meta_ads_platform.png" src="https://files.readme.io/9ce9735024294967545fee9e9fc44cc49834ffcb5b3496febd50f8466c1bd397-46192072798737.png" width="563px" />

<div id="note-1" />

> 📘 **Atenção**
>
> Se você tiver problemas com a elegibilidade para AEM, consulte [Verifique se os eventos do seu aplicativo são elegíveis para AEM](#verifique-se-os-eventos-do-seu-aplicativo-são-elegíveis-para-a-aem).

<div id="aem-data-sharing" />

### Compartilhamento de dados da AEM

Com o **compartilhamento avançado de dados**, você compartilha todos os eventos de conversão com o Meta Ads e atribui todas as instalações e os eventos posteriores dentro do aplicativo, independentemente do status de consentimento da ATT.

* Quando desativado, o compartilhamento avançado de dados fica limitado a eventos de conversão de usuários com um ID do anunciante disponível. Eventos de usuários sem ID de anunciante não são compartilhados nem atribuídos.
* Quando ativado, o compartilhamento avançado de dados disponibiliza eventos de conversão para o Meta Ads para todos os usuários, incluindo aqueles sem um ID do anunciante. A AppsFlyer atribui esses eventos. Os dados disponibilizados podem incluir informações adicionais relacionadas ao dispositivo que não envolvem o ID do dispositivo. Para saber mais, veja o <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#advanced_data_sharing">compartilhamento avançado de dados</Anchor>.

<Image align="center" alt="aem" src="https://files.readme.io/77e44d893994581dbe1a058fb5bebbf9b5e8bf167abe6e9d35ea8aa809ceca4b-46192056604305.png" />

<div id="note-2" />

> 📘 **Atenção**
>
> * Todos os eventos incluem instalações, aberturas de aplicativos e eventos in-app.
> * Antes de habilitar **Advanced data sharing**, verifique se disponibilizar esses dados para os anúncios da Meta, incluindo qualquer uso dos seus dados por terceiros, está em conformidade com as políticas e/ou regulamentações da plataforma às quais você está sujeito. Os dados disponibilizados podem incluir endereços IP, anon\_ids (se disponíveis), vendor\_id e agentes de usuário.
> * Para eventos in-app enviados de servidor para servidor (S2S), a Meta exige que tanto o **endereço IP** quanto o **identificador para fornecedores (IDFV)** sejam incluídos no payload do evento. Sem esses identificadores, o evento não será elegível para a atribuição da AEM pela Meta.
> * A AEM da Meta para promoção de aplicativos também pode incluir reivindicações de view-through não determinísticas. Para oferecer suporte à atribuição de view-through não determinística via AEM da Meta, verifique se a opção no nível do aplicativo Enable view-through attribution via campaign measurement modeling está ativada. Para mais detalhes, veja a <Anchor target="_blank" href="/marketers/pt/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">atribuição de visualização via modelagem probabilística</Anchor>.

<div id="check-if-your-app-events-are-eligible-for-aem" />

## Verifique se os eventos do seu aplicativo são elegíveis para a AEM

Você pode acessar o Gerenciador de Eventos da Meta para verificar se os eventos do seu aplicativo são elegíveis para a AEM. Caso o evento do seu aplicativo seja elegível, você consegue ver os resultados das suas campanhas de AEM no Gerenciador de Anúncios. Para aprender a verificar se os eventos do seu aplicativo são elegíveis para a AEM, consulte este <Anchor target="_blank" href="https://www.facebook.com/business/help/716239976391518?id=1877298665783613">artigo da Meta</Anchor>.

<div id="enable-aem-summary" />

## Habilitar a AEM: resumo

Use a tabela abaixo como uma lista de verificação para habilitar a AEM do Meta Ads na AppsFlyer.

| **Solução** | **Ativar** | **Ativar localização** | **Impacto** |
| --- | --- | --- | --- |
| **Remarketing da AEM (reengajamentos)** | Atribuição de reengajamento | Integração de parceiros (Meta Ads) | Habilita a AEM para remarketing (atribuição de reengajamento). |
| **AEM para promoção de aplicativos (instalações)** | Compartilhamento avançado de dados | Integração de parceiros (Meta Ads) | Habilita a AEM para promoção de aplicativos, incluindo disponibilizar para mensuração via Meta os eventos de usuários quando um ID do anunciante não está disponível e aceitar reivindicações não determinísticas (quando aplicável). |
| **AEM para promoção de aplicativos (instalações)** | Atribuição de exibição via modelagem probabilística | Configurações do aplicativo | Habilita a atribuição de visualização para reivindicações não determinísticas. |

<div id="troubleshooting" />

## Resolução de problemas

<div id="troubleshooting-ineligible-events-in-meta-aem" />

<Accordion title="Solução de problemas de eventos inelegíveis na AEM da Meta">

Se o Meta Ads marcar os eventos do seu aplicativo como inelegíveis, mostrando erros como **“Missing opt-out events”** ou outras mensagens relacionadas à AEM, isso normalmente ocorre devido a dados ausentes ou configurados incorretamente. Use a lista de verificação abaixo para diagnosticar e corrigir problemas comuns.

<div id="important" />

> 🚧 **Importante!**
>
> Depois de concluir as etapas a seguir, aguarde até que as mudanças sejam implementadas. O Meta Ads pode levar até **2–3 dias** para refletir a elegibilidade para AEM.

<div id="step-1-advanced-data-sharing-is-enabled" />

<Accordion title="Etapa 1: compartilhamento avançado de dados ativado">

1. Acesse **Colaborar** > **Integrações ativas** > **Meta Ads**.
2. Verifique se o **compartilhamento avançado de dados** está ativado.

</Accordion>

<div id="step-2-ip-masking-is-disabled" />

<Accordion title="Etapa 2: Desativação do mascaramento de IP">

Eventos com IPs mascarados não são elegíveis para a AEM.

* Acesse as **Configurações do aplicativo**.
* Verifique se o **mascaramento de IP** está desativado.

</Accordion>

<div id="step-3-servertoserver-s2s-events-include-required-parameters" />

<Accordion title="Etapa 3: Eventos de servidor para servidor (S2S) com parâmetros obrigatórios">

Todo evento S2S deve incluir:

* **Endereço IP**
* **IDFV** (identificador para fornecedores)

</Accordion>

<div id="step-4-review-att-consent-rate" />

<Accordion title="Etapa 4: Revise a taxa de consentimento da App Tracking Transparency (ATT)">

A Meta aceita um volume limitado de eventos com valores ausentes ou zerados do Identifier for Advertisers (IDFA). Caso seu aplicativo exceda esse limite, talvez você veja o seguinte erro: "**O volume do parâmetro Advertiser Tracking Enabled está fora do intervalo."**

</Accordion>

<div id="step-5-postback-mapping-configuration" />

<Accordion title="Etapa 5: Configuração do mapeamento de postback">

Verifique se os postbacks de eventos estão mapeados para **Enviar tudo (incluindo os orgânicos)**.

</Accordion>

<div id="step-6-check-reengagement-settings-if-relevant" />

<Accordion title="Etapa 6: Verificação das configurações de reengajamento (se relevante)">

Para campanhas de reengajamento pagas:

* Ative a **Atribuição de reengajamento** nas **Configurações do aplicativo** e na **Página de integração ativa da Meta**.

</Accordion>

<div id="still-not-working" />

#### Ainda não funcionou?

Se eventos específicos permanecerem inelegíveis:

1. Vá para o Gerenciador de Eventos da Meta e siga as orientações na tela.
2. Selecione o evento do aplicativo afetado.
3. Defina o **tráfego do MMP** como o método de conexão padrão.

<div id="need-help" />

#### Precisa de ajuda?

Se o problema persistir:

* Envie um ticket para o suporte
* Inclua uma captura de tela do Meta Ads mostrando os eventos inelegíveis

</Accordion>

<div id="i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible" />

<Accordion title="Minhas campanhas são elegíveis para a AEM, mas não estou recebendo os dados da mensuração em dashboards e relatórios">

Resposta da Meta: "Estamos lançando esta atualização em colaboração com seu MMP ao longo dos próximos meses, e alguns anunciantes talvez não tenham acesso até que a implementação seja concluída."

</Accordion>

<div id="why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement" />

<Accordion title="Por que não posso ver instalações atribuídas à AEM em relatórios brutos, mesmo após assinar o contrato da AMM?">

Quando a AAP está ativada, as instalações atribuídas por meio da Mensuração de Eventos Agregados (AEM) da Meta são excluídas dos relatórios de dados brutos. Isso se aplica mesmo com o contrato da AMM.

</Accordion>

<div id="note-3" />

> 📘 **Importante!**
>
> Quando o **compartilhamento avançado de dados** está ativado, a Meta pode reivindicar e atribuir instalações por meio da Mensuração de Eventos Agregados (AEM), mesmo quando não há dados de opt-in disponíveis, inclusive quando nenhum IDFA é coletado. No entanto, os resultados da AEM podem melhorar à medida que mais sinais de IDFA ficarem disponíveis; por isso, recomendamos enviar o máximo possível de eventos com opt-in.

<div data-zendesk-anchors="overview=resumo h_01HCAM4CEVRCG13CA32B0GM9QS=resumo app-aem-for-reengagement=aem-para-reengajamento 01H88ZM20H99W37M0H6XXQVMQA=aem-para-reengajamento attribution-flow=fluxo-de-atribui%C3%A7%C3%A3o 01H7YJVNMV7QSZJWKZZA9042K6=fluxo-de-atribui%C3%A7%C3%A3o attribution-data-parameters=par%C3%A2metros-de-dados-de-atribui%C3%A7%C3%A3o 01H7YJVNMVPPCD08Z2R0V5GCMY=par%C3%A2metros-de-dados-de-atribui%C3%A7%C3%A3o h_attribution_deeplink_note=aten%C3%A7%C3%A3o faqs-on-deep-link-reengagement-attribution=perguntas-frequentes-sobre-a-atribui%C3%A7%C3%A3o-de-reengajamento-de-deep-links 01H7YJVNMV4ZKMWKD06RC6GKFW=perguntas-frequentes-sobre-a-atribui%C3%A7%C3%A3o-de-reengajamento-de-deep-links 01H7YJVNMVSGMNJ3K84MCENXYG=what-must-the-advertiser-do-to-enable-this-attribution 01H7YJVNMVP7ZRCKXDRRH7GZBY=what-about-agencies-and-meta-campaign-management-partners are-there-any-restrictions-on-data-from-this%20attribution=are-there-any-restrictions-on-data-from-this-attribution 01H7YJVNMVQF0B0DV2NQYQVYHK=are-there-any-restrictions-on-data-from-this-attribution app-aem-for-app-promotion=aem-para-promo%C3%A7%C3%A3o-de-aplicativos 01H88ZM20HQFMG962AZGYA98FR=aem-para-promo%C3%A7%C3%A3o-de-aplicativos aem-eligibility=elegibilidade-da-aem 01H7YJVNMVPB054VFS60KH9N7W=elegibilidade-da-aem h_01HR886Q0KPM99FCQXD6RDPSBK=aten%C3%A7%C3%A3o-1 aem-data-sharing=compartilhamento-de-dados-da-aem 01H88ZM20HK2HY32M4BKZ4N0B9=compartilhamento-de-dados-da-aem 01H7YK9CHHNARCD7M2VZRMEW6S=aten%C3%A7%C3%A3o-2 check-eligibility=verifique-se-os-eventos-do-seu-aplicativo-s%C3%A3o-eleg%C3%ADveis-para-a-aem 01JBHQSHF8NA4SGVJ3WYPRN9B3=verifique-se-os-eventos-do-seu-aplicativo-s%C3%A3o-eleg%C3%ADveis-para-a-aem enable-aem-toggles-summary=habilitar-a-aem-resumo h_01KJ28ETP9GK6TBTJK8SBZ5PFW=habilitar-a-aem-resumo faqs-and-troubleshooting=resolu%C3%A7%C3%A3o-de-problemas 01H7YK9CHHZN78CBHFTQ7E9RKQ=resolu%C3%A7%C3%A3o-de-problemas h_01K720W9MYXFTYG18368SKHGGC=troubleshooting-ineligible-events-in-meta-aem h_01K720W9MYDKK5Q2J1M8VT9JFP=importante h_01K722GQSB92J5KFFYQNP5WR29=step-1-advanced-data-sharing-is-enabled h_01K722GQSBV3GY2ZNN29ENG7Q2=step-2-ip-masking-is-disabled h_01K722GQSBVTSC09EPPCZQ6WN3=step-3-servertoserver-s2s-events-include-required-parameters h_01K722GQSBSX06A56ZX8RJ6YKT=step-4-review-att-consent-rate h_01K722GQSB26TN65JVJD6R7BAV=step-5-postback-mapping-configuration h_01K722GQSBTD4J9TZHBRGYS1XV=step-6-check-reengagement-settings-if-relevant still-not-working=ainda-n%C3%A3o-funcionou h_01K722GQSB8CXSSCVZPA3R3CJX=ainda-n%C3%A3o-funcionou need-help=precisa-de-ajuda h_01K722GQSBBB8KS8JNRBJZ4WWT=precisa-de-ajuda 01JCX7SKJ76KGW9SN7RCFA18E6=i-dont-receive-aem-data-in-dashboards-and-reports-although-my-campaigns-are-aemeligible why-can%27t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01K4ADBT26D2KD5MH568542XSV=why-can-t-i-see-aemattributed-installs-in-raw-reports-even-after-signing-the-amm-agreement h_01M5VSB77G1VDKA6SJC81XNNFX=importante-1" />

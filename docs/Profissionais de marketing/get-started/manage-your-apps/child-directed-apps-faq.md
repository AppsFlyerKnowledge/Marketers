---
title: Aplicativos para crianças—Perguntas frequentes
metadata:
  keywords:
    - Agencies
    - Ad Networks
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
  created_at: '2023-09-05T19:02:32Z'
  edited_at: '2026-08-18T00:17:53Z'
  id: 18324823209745
  locale: pt
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/pt/articles/18324823209745
---
**Visão geral:** encontre respostas para as perguntas mais frequentes sobre aplicativos para crianças.

<div id="overview" />

## Visão geral

Para proteger a privacidade de menores, existem muitas políticas, leis e regulamentos específicos para aplicativos para crianças. Os principais são o [COPPA](https://www.ftc.gov/legal-library/browse/rules/childrens-online-privacy-protection-rule-coppa) e a [GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN#d1e2029-1-1). Nos últimos anos, plataformas como o iOS e Android implementaram políticas para melhorar a privacidade dessa audiência. Na hora de criar um aplicativo, uma das primeiras coisas que você precisa fazer é indicar se seu app é direcionado para menores ou para uma audiência mista (crianças e adultos). Acesse <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">esse guia</Anchor> para saber mais sobre como implementar uma solução de atribuição compatível com as diretrizes de aplicativos direcionados a crianças.

<div id="adding-a-child-directed-app" />

## Como adicionar um aplicativo para crianças

<div id="what-steps-do-i-need-to-take-when-adding-a-childdirected-app" />

<Accordion title="Quais passos são necessários para adicionar um aplicativo para crianças?">

1. <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Siga os passos do assistente</Anchor>.
2. No segundo passo do assistente, <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#configure-a-audiência-do-aplicativo">veja as instruções para aplicativos para crianças</Anchor>.
3. Depois que o aplicativo for adicionado:
   * Implemente a <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#implementação-da-dev-key-em-seu-app">dev key</Anchor> no SDK
   * Inclua os <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">controles de privacidade</Anchor> apropriados

 Veja mais detalhes sobre a [implementação de ferramentas de compliance com ad networks](#implementando-as-ferramentas-de-compliance-da-appsflyer).

</Accordion>

<div id="when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children" />

<Accordion title="Ao adicionar um novo aplicativo, o que acontece depois que ele for identificado como um app para crianças?">

Duas semanas depois de adicionar o aplicativo, você receberá uma notificação solicitando a confirmação de implementação de controles de privacidade. Feito isso, você receberá uma mensagem de confirmação. Você sempre pode acessar a mensagem de confirmação na Central de notificações ou ver os detalhes no <Anchor target="_blank" href="/marketers/pt/docs/audit-log">log de auditoria</Anchor>.

</Accordion>

<div id="if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later" />

<Accordion title="Posso alterar a configuração de um aplicativo como um app para crianças?">

Depois de definir se um aplicativo é direcionado para crianças ou não, essa configuração não pode ser alterada. Isso só pode ser feito na hora de adicionar o aplicativo.

</Accordion>

<div id="how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps" />

<Accordion title="Como posso saber se alguém da minha equipe definiu que o meu app é para crianças?">

Após a confirmação, você pode visualizar essa informação de duas maneiras:

* **Central de notificações:** na barra do menu, clique no ícone de notificação ![notificatin center icon.png](https://files.readme.io/5d0b4f1712ba0c05786025adf183e065a2144e1917542ebec0f302688dccb5eb-18473195561489.png) e procure pela notificação de confirmação.
* **Log de auditoria**
  1. Na barra do menu, acesse o menu do usuário (lista suspensa de endereço de e-mail).
  2. Selecione **Central de segurança.**
  3. Na seção do **log de auditoria**, clique em **Ver log de auditoria.**  
     Você pode ver os detalhes de confirmação em **meus aplicativos**.

</Accordion>

<div id="implementing-appsflyer-compliance-tools" />

## Implementando as ferramentas de compliance da AppsFlyer

<div id="how-do-i-know-which-tool-to-use" />

<Accordion title="Como saber qual ferramenta devo usar?">

Quando o seu aplicativo foi feito para crianças ou possui uma audiência mista (menores e adultos), você pode usar qualquer uma das ferramentas recomendadas <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">nesse guia</Anchor>. Veja mais recursos de SDK no final dessa página. 

<div id="examples-of-compliance-tools-and-their-use" />

#### Exemplos de ferramentas de compliance e seus usos

<table><thead><tr><th>Ferramenta</th><th>/docs/ctv-pc-and-console-platform-attribution-concepts</th><th>com o Android</th><th>Disponibilidade de dados brutos</th></tr></thead><tbody><tr><td><span id="strict-sdk"></span><p><a href="./additional-sdk-integration-guide#strictmode-sdk" target="_blank">SDK restrito</a>: </p><p>Garante que o IDFA não seja enviado para a AppsFlyer. No geral, essa é a recomendação para aplicativos para crianças.</p></td><td><span><span>✓</span></span></td><td>- </td><td>Disponível somente para anunciantes</td></tr><tr><td><span id="standard-sdk-using-the-setdisableadvertisingidentifiers-api"></span><p>SDK padrão usando a <a href="./android-oaid-implementation-in-the-sdk#opting-out-of-oaid-collection" target="_blank"><kbd>setDisableAdvertisingIdentifiers</kbd> API</a>:</p><p>Garante que o AAID (Android advertising ID do Google) não seja enviado à AppsFlyer. No geral, essa é a recomendação para aplicativos para crianças.</p></td><td>- </td><td><span><span>✓</span></span></td><td>Disponível somente para anunciantes</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-specific-ad-networks"></span><p>SDK padrão com um filtro de idade usando a <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank">função <kbd>setSharingFilterForPartners</kbd></a> para ad networks <strong>específicas:</strong> </p><p>Impede que essas ad networks acessem os dados de usuários que estão abaixo do filtro de idade\*.</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Limitados para ad networks específicas</td></tr><tr><td><span id="standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks"></span><p>SDK padrão com um limite de idade usando a <a href="./additional-sdk-integration-guide#exclude-partners-from-getting-data" target="_blank">função <kbd>setSharingFilterForPartners</kbd></a> para <strong>todas</strong> as ad networks:</p><p>Impede que as ad networks acessem os dados de usuários que estão abaixo do filtro de idade\*.</p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Disponível somente para anunciantes</td></tr><tr><td><span id="skan-only"></span><p><a href="./skadnetwork-skan-solution-guide" target="_blank">Somente SKAN</a>:</p><p>Garante que o ID de publicidade não seja compartilhado com outras ad networks.</p></td><td><span><span>✓</span></span></td><td>- </td><td>Disponível somente para anunciantes</td></tr><tr><td><span id="sdkless-solutions-less-recommended"></span><p>Soluções sem SDK (menos recomendáveis):</p><p><span>Configure seus próprios servidores de forma que eles enviam os dados diretamente para a AppsFlyer como alternativa ao envio de dados por meio do </span><span>SDK.</span></p></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>Depende da sua configuração</td></tr><tr><td><span id="aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners"></span><p><a href="./apply-aggregated-advanced-privacy-framework" target="_blank">Framework de privacidade avançada agregada</a>: </p><p>Aplica os níveis de privacidade da ATT da Apple, garantindo que os dados do usuário ficarão <span>indisponíveis </span><span>para anunciantes e ad networks.</span></p></td><td><span><span>✓</span></span></td><td>- </td><td>Indisponíveis para anunciantes e ad networks</td></tr><tr><td colspan="4"><span id="-when-applying-an-age-gate-block-userlevel-data-that-doesnt-fall-under-the-age-gate-is-available-in-raw-data-reports"></span><p>\* Ao aplicar um bloqueio de filtro de idade, os dados dos usuários que não se enquadram no limite de idade ficam disponíveis nos relatórios de dados brutos.</p></td></tr></tbody></table>

</Accordion>

<div id="how-does-using-the-tools-in-the-guide-affect-attribution" />

<Accordion title="Como as ferramentas mencionadas no guia afetam a atribuição?">

<Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">O guia de soluções de compliance da AppsFlyer</Anchor> oferece diferentes ferramentas com [diversos níveis de controle](#how-do-i-know-which-tool-to-use). Seu impacto sobre a atribuição pode variar de acordo com a ferramenta que você escolhe implementar.

Ao usar uma ferramenta que limita o envio de dados do usuário, como é o caso de dados de device ID, outros métodos de atribuição são usados. Por exemplo, a <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">modelagem probabilística</Anchor> ou o <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#install-referrer-android-only">Install referrer (para Android)</Anchor>.

Ferramentas que não enviam dados do usuário são consideradas como ferramentas seguras e, portanto, permitem que você receba dados agregados de campanha.

</Accordion>

<div id="i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do" />

<Accordion title="Não sei se a ad network com a qual eu trabalho segue as diretrizes de privacidade. O que devo fazer?">

Muitas vezes, não fica claro se as ad networks estão em compliance com as leis relevantes. Você pode fazer essa pergunta diretamente para a sua ad network. Se ela não estiver em conformidade ou se, mesmo após uma resposta, você se sentir inseguro, você pode optar por não compartilhar seus dados com ela. Você pode usar a **<Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">função `setSharingFilterForPartners`</Anchor>** para especificar quais ad networks serão bloqueadas. Você também pode usar essa função para bloquear todas as ad networks. Veja mais [exemplos de ferramentas de compliance](#exemplos-de-ferramentas-de-compliance-e-seus-usos).

</Accordion>

<div id="do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant" />

<Accordion title="Se a ad network tem compliance, eu preciso implementar as ferramentas da AppsFlyer?">

As ferramentas da AppsFlyer sempre devem ser implementadas. As ferramentas certas para as suas necessidades variam de acordo com a audiência do seu aplicativo. Você pode usar a  **<Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">função `setSharingFilterForPartners`</Anchor>** (“MediaSourceName”) se a ad network se comprometeu a tratar os dados compartilhados exclusivamente como uma processadora de dados, para fins limitados permitidos pelo COPPA, GDPR, leis e regras aplicáveis ou políticas da plataforma, mediante o devido consentimento

Isso se aplica a cada uma das ad networks com as quais você trabalha.

</Accordion>

<div id="what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this" />

<Accordion title="Quais dados estou compartilhando com as ad networks? Que controle eu tenho sobre isso?">

Ad networks que não são <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">SRNs</Anchor> recebem seus dados através de postbacks Elas podem definir quais eventos serão inclusos nos postbacks. Elas podem definir quais eventos incluir nos postbacks. Postbacks de instalação são enviados por padrão para fins de atribuição, enquanto postbacks de eventos in-app são enviados somente se você <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">configurou eventos específicos</Anchor>. Desde que os postbacks não estejam bloqueados ou restringidos pelo SDK, eles podem conter dados relacionados com o engajamento do usuário no aplicativo (como instalação, eventos in-app e reengajamentos).

Com a exceção dos postbacks, ad networks e agências têm um <Anchor target="_blank" href="/marketers/pt/docs/manage-data-access-permissions">acesso limitado aos dados na plataforma</Anchor>.

**Para saber quais dados foram enviados às ad networks por meio de postbacks:**

* Baixe os <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#postbacks">relatórios de postback</Anchor> no menu **Relatórios** > **Exportação de dados brutos**

**Para controlar quais dados serão enviados:**

* Use qualquer uma das ferramentas de compliance do Sdk, como <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#exclude-partners-from-getting-data">`setSharingFilterForPartners`</Anchor> para bloquear ou restringir o envio de certos dados.
* Configure para quem você envia <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app</Anchor>. Ou seja, se eles serão enviados para a ad network à qual o evento foi atribuído ou para todos os canais de mídia, incluindo orgânicos.

**Para controlar a disponibilidade de dados de atribuição no nível do usuário para usuários do iOS:**

* Use o <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">framework de Privacidade Avançada Agregada</Anchor> para aplicar os limites de privacidade da ATT. Isso garante que os dados do usuário, mesmo quando usados para atribuição, não sejam disponibilizados na AppsFlyer para anunciantes e ad networks. Os dados agregados ficam disponíveis sem nenhuma limitação.

</Accordion>

<div id="do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked" />

<Accordion title="Eu preciso do SDK se o meu aplicativo é para crianças e todas as ad networks estão bloqueadas?">

O SDK registra os eventos no seu aplicativo, como instalações, reengajamentos e eventos in-app. Sem o SDK, não há atribuição. Você pode <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#privacidade-do-usuário">proteger a privacidade dos usuários com o SDK</Anchor> e disponibilizar somente dados agregados.

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">Visão geral da integração do SDK</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/apply-privacy-preserving-sdk-methods">SDK: métodos de proteção à privacidade</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#privacidade-do-usuário">SDK: configurações de privacidade do usuário</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/trust/privacy/">Medidas de privacidade da AppsFlyer</Anchor>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HA20EGWDBSNAFZ7WNXJFFRRV=vis%C3%A3o-geral general-questions=como-adicionar-um-aplicativo-para-crian%C3%A7as h_01H9ZK2THJVFYQ49HHRYKZZNEK=como-adicionar-um-aplicativo-para-crian%C3%A7as h_01HHCE11YQX4DKV5BEW6QHKN55=what-steps-do-i-need-to-take-when-adding-a-childdirected-app when-adding-a-new-app-what-happens-after-i%E2%80%99ve-indicated-my-app-is-directed-towards-children=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children h_01H9ZK2THJ225P38Q9CHQSTNY4=when-adding-a-new-app-what-happens-after-i-ve-indicated-my-app-is-directed-towards-children if-ive-added-an-app-and-didn%E2%80%99t-define-it-as-directed-towards-children-can-i-change-this-later=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01HGZ5VAJHNW2K62ARTK43SG19=if-ive-added-an-app-and-didn-t-define-it-as-directed-towards-children-can-i-change-this-later h_01H9ZK2THJK5Q5EE3K38GTCCT7=how-can-i-see-if-someone-in-my-team-confirmed-childdirected-apps implementing-compliance-tools=implementando-as-ferramentas-de-compliance-da-appsflyer h_01HGZ5VAJHNJVM2ENFZ3DEAK42=implementando-as-ferramentas-de-compliance-da-appsflyer h_01HGZ4VWDBZJE8RWM05EJNH0S9=how-do-i-know-which-tool-to-use examples-of-compliance-tools-and-their-use=exemplos-de-ferramentas-de-compliance-e-seus-usos h_01HHEED2AQTW7G0MJJZDZV2B09=exemplos-de-ferramentas-de-compliance-e-seus-usos standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function%C2%A0for-all-ad-networks=standard-sdk-using-an-age-gate-using-the-setsharingfilterforpartners-function-for-all-ad-networks aggregated-advanced-privacy-framework%C2%A0%0Aenforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners=aggregated-advanced-privacy-framework-enforces-apple-att-privacy-levels-making-sure-userlevel-data-is-unavailable-to-advertisers-or-partners h_01HKHX0GBS9EWMXMY387FQ95X1=how-does-using-the-tools-in-the-guide-affect-attribution h_01HH9EAB8T4Z6RMT8MVS77Q6BP=i-dont-know-if-the-ad-network-im-working-with-is-compliant-what-do-i-do h_01HKHWSQQKEDZBCDH0P8H760K6=do-i-need-to-implement-appsflyer-compliance-tools-if-the-ad-network-is-compliant h_01HHEEQ4AAEZSA0YB6V2DSRYXK=what-data-am-i-sending-to-ad-networks-what-control-do-i-have-over-this h_01HKJ843208PMQF1MCYCWMJC3H=do-i-need-the-sdk-if-my-app-is-childdirected-and-all-ad-networks-are-blocked h_01HE7TQV7VDSEX3E7RTKAHBMNN=veja-tamb%C3%A9m" />

---
title: Aplicar a estrutura de privacidade avançada agregada
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
  created_at: '2021-03-15T11:32:31Z'
  edited_at: '2026-08-18T00:34:19Z'
  id: 360018515798
  locale: pt
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/pt/articles/360018515798
---
> **Resumo:** devido à disponibilidade geral do iOS 14.5+ e da aplicação do ATT pela Apple, os anunciantes usam a estrutura de Privacidade Avançada Agregada (AAP) para controlar a disponibilidade de dados de atribuição no nível do usuário a partir da plataforma.

<div id="aggregated-advanced-privacy-aap-framework" />

## Estrutura de privacidade avançada agregada (APP)

A estrutura de privacidade avançada agregada (AAP) da AppsFlyer impede o rastreamento em aplicativos e sites pertencentes a diferentes empresas e a capacidade de identificar exclusivamente um usuário ou dispositivo. A AAP utiliza os níveis de privacidade da App Tracking Transparency da Apple como referência mínima para seus limiares de preservação da privacidade.

A estrutura fornece aos anunciantes a capacidade de controlar a disponibilidade de dados de atribuição no nível do usuário através da plataforma da AppsFlyer.

Devido à disponibilidade geral do iOS 14.5+ e da aplicação do ATT pela Apple, se a AAP estiver ativada, os dados de atribuição no nível do usuário para usuários sem consentimento que executam o iOS 14.5+ não estarão disponíveis para anunciantes ou parceiros. **Observação**: Mesmo quando o AAP está desativado, os dados em nível de usuário não podem ser usados para identificar exclusivamente um dispositivo.

A AAP não tem impacto na disponibilidade de dados de atribuição agregados e relatórios analíticos para anunciantes e parceiros.

<div id="aap-impacted-features" />

### Recursos afetados pela AAP

Se a AAP estiver ativada, os dados fornecidos pelos dados brutos serão afetados e alguns campos serão restritos ou não estarão disponíveis. Isso afeta os dados fornecidos pelas seguintes ferramentas:

* Relatório do Data Locker
* Pull API de dados brutos
* API de push
* Página de exportação do dashboard
* Postbacks para ad networks
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">API Get conversion data (GCD)</Anchor> no contexto da API de dados do lado do cliente e a nível do usuário

A disponibilidade de dados é afetada quando a AAP está ativada da seguinte forma:

* **Dados de atribuição e fraude (Protect360):** <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">Alguns campos de atribuição são restritos ou não estão disponíveis.</Anchor>
* **Dados de cliques, impressões e de cliques bloqueados (fraude):** <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#identifier-restriction">Identificadores relacionados ao usuário e ao dispositivo</Anchor> não estão disponíveis.
* **Deferred deep linking**: Se você implementar deferred deep linking em mídias pagas, use a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unifieddeeplink">API unificada de deep linking (UDL). A API legada, que usa GCD, não pode ser usada no contexto de usuários que não permitem o rastreamento. No caso de mídias próprias, o deferred deep linking é compatível via GCD e a deferred deep linking API mais recente.</Anchor>

<div id="data-availability-principles-in-aggregated-advanced-privacy" />

## Princípios de disponibilidade de dados na privacidade avançada agregada

Quando a AAP se aplica aos dados de um determinado usuário, a disponibilidade dos dados depende do status da ATT desse usuário e da fonte de mídia que traz o usuário.

**Definições:**

* **Dados de atribuição no nível do usuário:** Registros de dados contendo identificadores no nível do dispositivo vinculados à atribuição no nível do usuário
* **Dados de atribuição limitados para anunciantes:**
  * Disponível: identificadores no nível do dispositivo (o IDFA está disponível com o consentimento do usuário). (o IDFA está disponível com o consentimento do usuário).
  * Indisponível: parâmetros de atribuição recebidos via link de atribuição do publisher (por exemplo, `pid` e `c`). <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#unavailable-attribution-fields">Lista de campos restritos e indisponíveis para anunciantes</Anchor> OU fonte de mídia restrita.
* **Dados de atribuição limitados para parceiros:**
  * Disponível: detalhes agregados da campanha.
  * Indisponível: dados no nível do usuário que podem ajudar a identificar o usuário, como ID da AppsFlyer, dados personalizados, Customer User ID (CUID), ID de clique, IDFA, IDFV, IMEI, agente de usuário e endereço IP.

Os termos definidos são usados na figura e nas seções a seguir para descrever os dados disponíveis para anunciantes e parceiros.

![Estrutura de Privacidade Avançada - Anunciantes (4).png](https://files.readme.io/0291fe2eea5f6efc41f2338824a0017be3e265f502e0d3999d52ac87b1ee7719-35847850634897.png)

A Privacidade Avançada se comporta de maneira diferente quando veiculada na web e o parâmetro af\_media\_type=web ou af\_media\_type=app deve ser usado. Para obter mais informações, clique <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks#campanhas-na-web">aqui</Anchor>.

<div id="paid-and-owned-media-data-availability" />

### Disponibilidade de dados de mídia paga e própria

<div id="paid-media" />

<Accordion title="Mídia paga">

Mídia paga inclui ad networks mobile com integrações na plataforma da AppsFlyer com as quais os anunciantes executam campanhas.

<div id="paid-media-data-availability-by-att-status" />

#### Disponibilidade de dados de mídia paga por status ATT

<table><thead><tr><th rowspan="2">Tipo de mídia</th><th colspan="2">Status da ATT</th><th colspan="2">Dados disponíveis para:</th></tr><tr><th>Aplicativo do publisher</th><th>Aplicativo do anunciante</th><th>AppsFlyer</th><th>Rede de anúncios</th></tr></thead><tbody><tr><td rowspan="4">Aplicação</td><td>Autorizado</td><td>Autorizado</td><td>Dados de atribuição no nível do usuário</td><td>Dados de atribuição no nível do usuário</td></tr><tr><td>Não autorizado</td><td>Autorizado</td><td>Dados de atribuição limitados para anunciantes </td><td>Dados de atribuição limitados para parceiros</td></tr><tr><td>Autorizado</td><td>Não autorizado</td><td>Dados de atribuição limitados para anunciantes </td><td>Dados de atribuição limitados para parceiros</td></tr><tr><td>Não autorizado</td><td>Não autorizado</td><td>Dados de atribuição limitados para anunciantes </td><td>Dados de atribuição limitados para parceiros</td></tr><tr><td> </td><td colspan="4"> </td></tr><tr><td rowspan="2"><p>Web</p></td><td>N/D</td><td>Autorizado</td><td>Dados de atribuição no nível do usuário</td><td>Dados de atribuição no nível do usuário</td></tr><tr><td>N/D</td><td>Não autorizado</td><td>Dados de atribuição limitados para anunciantes </td><td>Dados de atribuição limitados para parceiros</td></tr></tbody></table>

</Accordion>

<div id="owned-media" />

<Accordion title="Mídias próprias">

A estrutura AppTrackingTransparency da Apple se aplica apenas a dados coletados de diferentes empresas. Portanto, os dados de atribuição no nível do usuário de mídia própria estão disponíveis para os anunciantes, independentemente do status de consentimento do ATT do usuário.

A mídia própria inclui campanhas de marketing digital usadas pelos anunciantes para alcançar clientes. Isso inclui campanhas de e-mail, promoções cruzadas, notificações push e outros. Na AppsFlyer, as campanhas que usam ad networks não são consideradas mídias próprias.

</Accordion>

<div id="controlling-advanced-aggregated-privacy" />

## Controlando a privacidade agregada avançada

<div id="aap-central-switch" />

<Accordion title="Privacidade avançada agregada (AAP)—toggle para aplicativo">

A AAP é um toggle no nível do aplicativo que controla as configurações de privacidade avançada para todos os parceiros do aplicativo selecionado. O botão da AAP encontra-se na página **Configurações do aplicativo**. Quando o toggle da AAP está ativado, os botões de **Privacidade avançada** para todos os parceiros do aplicativo selecionado são ativados automaticamente e não podem ser modificados. Quando está desativado, os anunciantes podem acessar cada integração de parceiro individualmente e ativar e **Privacidade avançada**.

![AAPcontrol.png](https://files.readme.io/ddc8140ada9278eab447ecdfa4d88c56e07a0ed54b10b71de1cc2352f9590d40-35847850639121.png)

<div id="aap-enabled" />

#### AAP ativada

* A atribuição agregada está disponível. Isso inclui, por exemplo, painéis de visão geral e ferramentas de relatórios, como Cohot e Master API.
* [Os parceiros de privacidade avançada](#partner-advanced-privacy-switch) estão ativos e não podem ser modificados. Atenção! Eles ficam bloqueados nesse status.
* A disponibilidade de dados no nível do usuário para anunciantes e parceiros é limitada, conforme definido na [seção anterior](/docs/apply-aggregated-advanced-privacy-framework#princípios-de-disponibilidade-de-dados-na-privacidade-avançada-agregada).

<div id="aap-disabled" />

#### AAP desativada

* Os dados de atribuição no nível do usuário estão disponíveis para anunciantes.
* A configuração de privacidade avançada por parceiro pode ser definida individualmente.

*Antes de desativar a AAP, considere se, ao fazê-lo, você disponibilizará os dados de atribuição no nível do usuário a terceiros e como eles usarão os dados. Você deve trabalhar com seus consultores jurídicos e outros profissionais em relação à forma como a Apple define o acompanhamento. Nada declarado aqui é aconselhamento jurídico. Os dados são fornecidos para sua informação e conveniência.*

Para definir a configuração de privacidade avançada agregada:

1. Na AppsFlyer, no menu lateral, selecione **configurações** > **configurações do aplicativo**.
2. Ative ou desative a opção **Privacidade avançada agregada** conforme necessário.
3. Clique em **Salvar**.

</Accordion>

<div id="partner-advanced-privacy-switch" />

<Accordion title="Privacidade avançada (AP)—toggle para parceiros">

Se a AAP estiver desativada, os anunciantes poderão definir a configuração de privacidade avançada para cada ad network individualmente.

![APControl.png](https://files.readme.io/8e5a005cbadb5665cf255d39d6fa425298510f719b166c2013a2dfe57d4e982b-35847865312657.png)

**Para desativar a Privacidade Avançada de um parceiro:**

1. Verifique se o botão central para a AAP está desativado na página **Configurações do aplicativo**.
2. No menu lateral, selecione **Colaborar** >**Integrações ativas**.
3. Selecione a ad network.
4. Na aba **Integração**, desative a opção **Privacidade avançada**.

**Alterar a configuração de AAP e o impacto na configuração de Privacidade Avançada do parceiro**

Conforme mencionado anteriormente, a configuração da AAP substitui a configuração de Privacidade Avançada (AP) no nível do parceiro. No entanto, se você desativar posteriormente a AAP (o controle central), as configurações individuais de Privacidade Avançada no nível do parceiro serão revertidas para o status anterior. Ou seja:

* No passado, você desativou a AAP e definiu algumas configurações de AP do parceiro como desativadas.
* Depois, você ativou a AAP. Lembre-se, quando a AAP está ativada, ela substitui a configuração do parceiro e todos os parceiros são considerados ativados.
* Agora você desativa o AAP novamente. Isso significa que as configurações individuais do parceiro se aplicam. Então, para alguns parceiros, a configuração já está desativada.

</Accordion>

<div id="advanced-aggregated-privacy-implications-for-your-partners" />

## Consequências da privacidade avançada agregada para seus parceiros

<div id="ad-networks" />

<Accordion title="Redes de anúncios">

<div id="postbacks-to-ad-network-partners" />

#### **Postbacks para ad networks parceiras**

A AAP afeta as ad networks em relação aos dados compartilhados com elas e está alinhado aos princípios da AAP que se aplicam aos anunciantes no contexto de uma ad network. Os dados são compartilhados com ad networks através de postbacks, que diferem entre a ad network atribuída e a ad network não atribuída.

As regras de compartilhamento de dados descritas se aplicam a uma determinada ad network se um dos seguintes botões estiver ativado:

* AAP: botão que faz alterações a nível de aplicativo
* AP: botão que faz alterações a nível de parceiro

<div id="postbacks-for-attributed-ad-networks" />

#### **Postbacks para ad networks atribuídas**

No caso da rede atribuída, o tipo de postback usado para compartilhar dados depende do status de consentimento do usuário da seguinte forma:

* **Usuários que permitem o rastreamento:** postback regular contendo dados de atribuição no nível do usuário, incluindo identificadores.
* **Usuários que não permitem o rastreamento:** postback de Privacidade Avançada (AP) contendo dados de atribuição limitados. Contém detalhes da campanha e nenhum identificador.
  * **Pré-requisito:** para uma ad network obter postbacks AP, ela deve ter integração AP com a AppsFlyer. Sem integração, nenhum postback é enviado para usuários sem consentimento.
  * **Exceção: para instalações atribuídas ao Apple Search Ads (ASA), quando uma ad network que não oferece suporte à privacidade avançada define os postbacks de instalação como** Todas as fontes de mídia, incluindo orgânica/strong>, o Apple Search Ads (ASA) ainda envia postbacks de instalação para a ad network independentemente do status de privacidade avançada do lado do anunciante.

Os vários cenários de consentimento do usuário e tipos de postback usados são ilustrados na figura a seguir.

![AAP - Attributed ad networks.png](https://files.readme.io/d776c77115beb4c6b6ada1850077f186aa2feb809a8b69af8cf0ec760cd02b39-35847865314961.png)

A Privacidade Avançada se comporta de maneira diferente quando veiculada na web e o parâmetro af\_media\_type=web ou af\_media\_type=app deve ser usado. Para obter mais informações, clique <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks#campanhas-na-web">aqui</Anchor>.

<div id="postbacks-for-unattributed-partners" />

#### **Postbacks para parceiros não atribuídos**

Postbacks não atribuídos são enviados para uma rede quando a opção de envio na aba de integração do parceiro integrado é definida como *todas as fontes de mídia, inclusive orgânicas* e esse parceiro não é atribuído ao evento, como ilustrado na figura a seguir.

![InAppEventAll.png](https://files.readme.io/e24037f75b2b82797031eb13d5e063b8c2006812491e69674ff066ac830919f7-35847850644881.png)

Os vários cenários de consentimento do usuário e tipo de postback usados são ilustrados na figura a seguir.

![AAP - Unattributed ad networks.png](https://files.readme.io/bb8a5d192e2120f8df90b9be044c0b4abf48c2250f5128fbbce76c60c89718cc-35847850645649.png)

A Privacidade Avançada se comporta de maneira diferente quando veiculada na web e o parâmetro af\_media\_type=web ou af\_media\_type=app deve ser usado. Para obter mais informações, clique <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks#campanhas-na-web">aqui</Anchor>.

</Accordion>

<div id="analytics-partners" />

<Accordion title="Parceiros de análise">

A AAP afeta os parceiros de análise em relação aos dados compartilhados com eles e está alinhado com os princípios da AAP que se aplicam aos anunciantes no contexto do parceiro de análise.  Os dados são compartilhados com o parceiro por meio de postbacks.

As regras de compartilhamento de dados descritas se aplicam a um determinado parceiro se um dos seguintes botões estiver ativado:

* AAP: botão que faz alterações a nível de aplicativo
* AP: botão que faz alterações a nível de parceiro

Postbacks contendo dados de atribuição no nível do usuário, incluindo identificadores de usuário, são enviados para usuários com consentimento. Nenhum postback é enviado no caso de usuários sem consentimento.

Os vários cenários de consentimento do usuário e tipo de postback usados são ilustrados na figura a seguir.

![AAP - Analytics partner.png](https://files.readme.io/4bb77720f9e0be093e325f989987f5b5ba2dba5aa26e2f32df5f1bd5b99161eb-35847865320593.png)

A Privacidade Avançada se comporta de maneira diferente quando veiculada na web e o parâmetro af\_media\_type=web ou af\_media\_type=app deve ser usado. Para obter mais informações, clique <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks#campanhas-na-web">aqui</Anchor>.

</Accordion>

<div id="agencies" />

<Accordion title="Agências">

**Disponibilidade de dados:** o impacto da AAP nas agências é semelhante ao impacto sentido pelos anunciantes. Se os dados brutos estiverem disponíveis para a agência para um determinado aplicativo e a AAP se aplicar aos dados de um determinado usuário, os dados estarão disponíveis de acordo com as regras de dados de [atribuição limitada para anunciantes](/docs/apply-aggregated-advanced-privacy-framework#princípios-de-disponibilidade-de-dados-na-privacidade-avançada-agregada).

**Agência altera a configuração de privacidade avançada de uma ad network:**

* Se a AAP estiver desativada, a configuração de privacidade avançada de cada parceiro integrado poderá ser definida.
* Por padrão, somente anunciantes podem alterar a configuração de privacidade avançada. No entanto, o anunciante pode conceder explicitamente à agência permissão para definir a configuração de privacidade avançada das ad networks habilitadas pela agência.

**Para conceder permissão a uma agência para definir a privacidade avançada**

![agency_advanced_privacy.png](https://files.readme.io/ac4a1aae41e9e39b9759006db84ea14df7495d0a14c02df7dbfb8dd93a2d2c23-35847865322129.png)

Para permitir que uma agência configure a privacidade avançada:

1. No menu lateral, selecione **Colaborar** >**Integrações ativas**.
2. Selecione a agência.
3. Na aba **Permissões** ative o botão **Alterar a** **configuração de privacidade avançada.**
4. Clique em **Salvar.**

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/partners/pt/docs/advanced-privacy-guide-postback-macros-for-ad-networks">Guia de privacidade avançada e macros de postback para ad networks</Anchor>

<div data-zendesk-anchors="aggregated-advanced-privacy-framework=estrutura-de-privacidade-avan%C3%A7ada-agregada-app h_01HDPDE0H3SYFWBHK59HBV2P6N=estrutura-de-privacidade-avan%C3%A7ada-agregada-app aapimpacted-features=recursos-afetados-pela-aap h_01HDPDE0H339BPACN235V70MWW=recursos-afetados-pela-aap data-availability-principles-in-aggregated-advanced-privacy=princ%C3%ADpios-de-disponibilidade-de-dados-na-privacidade-avan%C3%A7ada-agregada h_01HDPDE0H3QBE60DVBZ1MWNB9N=princ%C3%ADpios-de-disponibilidade-de-dados-na-privacidade-avan%C3%A7ada-agregada paid-and-owned-media-data-availability=disponibilidade-de-dados-de-m%C3%ADdia-paga-e-pr%C3%B3pria h_01HDPDE0H326EXNCQHPVJWXK3H=disponibilidade-de-dados-de-m%C3%ADdia-paga-e-pr%C3%B3pria h_01HDPDE0H3TBDSXCNW5Q3E1Q7P=paid-media paid-media-data-availability-by-att-status=disponibilidade-de-dados-de-m%C3%ADdia-paga-por-status-att h_01HDPDE0H3SACYAV19WQD9TCQ3=disponibilidade-de-dados-de-m%C3%ADdia-paga-por-status-att h_01HDPDE0H4M4XPE1C54K284BGW=owned-media controlling-aap=controlando-a-privacidade-agregada-avan%C3%A7ada h_01HDPDE0H4VQC2DWAV68Q9VDVQ=controlando-a-privacidade-agregada-avan%C3%A7ada h_01HDPDE0H4BHG114REGTWCDBP9=aap-central-switch aap-enabled=aap-ativada h_01HDPDE0H4SC810EBK7ZGQ02K0=aap-ativada aap-disabled=aap-desativada h_01HKHPGQ1R6HZEXSRTX7ATVWE9=aap-desativada h_01HDPDE0H4FRDXWRCYAWTPZZWE=partner-advanced-privacy-switch 01HKHPEBBFGQ5ZX4J6G50GEN64=consequ%C3%AAncias-da-privacidade-avan%C3%A7ada-agregada-para-seus-parceiros h_01HDPDE0H4PDJ4TC02TED0DB8P=ad-networks postbacks-to-ad-network-partners=postbacks-para-ad-networks-parceiras h_01HDPDE0H47ENYTWRVFPX0VTZC=postbacks-para-ad-networks-parceiras postbacks-for-attributed-ad-networks=postbacks-para-ad-networks-atribu%C3%ADdas h_01HDPDE0H4B01YG577QZCG7TA7=postbacks-para-ad-networks-atribu%C3%ADdas postbacks-for-unattributed-partners=postbacks-para-parceiros-n%C3%A3o-atribu%C3%ADdos h_01HDPDE0H63ZMV255SN7EKDRMV=postbacks-para-parceiros-n%C3%A3o-atribu%C3%ADdos h_01HDPDE0H67T1XFTEB2N0NN6YN=analytics-partners h_01HDPDE0H6AM91W49W2G2Z94DM=agencies h_01HDPDMX05ZZCAMW4TTWF4M4YN=veja-tamb%C3%A9m" />

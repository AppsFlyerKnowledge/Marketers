---
title: Implicações para a ATT (iOS 14+) e descontinuação do LAT
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-10-07T17:33:35Z'
  edited_at: '2026-08-18T00:32:03Z'
  id: 360014090597
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/360014090597
---
> **Visão geral**: A partir do iOS 14, o iOS utiliza ATT para determinar as preferências de privacidade do usuário e se a opção Limit ad tracking / Rastreamento de anúncios limitado (LAT) está obsoleta.

<div id="att-values" />

### Valores ATT

* A partir do iOS 14: O Apple <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> (ATT) fornece os valores do status para a autorização do rastreamento do app.
* A AppsFlyer obtém ATT das seguintes fontes:
  * SDK V6+ da AppsFlyer incorporado no app.
  * Por API de anunciantes. Por exemplo, a API S2S.
* ATT está disponível nos relatórios de dados brutos. É necessário solicitá-lo explicitamente da seguinte forma:
  * Pull API: Adicione ATT *ao* parâmetro additional\_ fields nas suas solicitações de Pull API.
  * Página Exportar dados Na aba dos campos de relatório, selecione explicitamente ATT.
  * Data Locker: Na página de configuração do Data Locker, adicione explicitamente ATT à lista de campos.
  * Push API: Na página Acesso à API, adicione explicitamente ATT à lista de campos.
* Em alguns casos, a ATT é preenchida por valores definidos pela AppsFlyer. São indicados pelo prefixo *af* na tabela.
* Se o IDFA não estiver disponível, ele é preenchido com zeros.

<div id="att-values-defined-by-apple" />

#### Valores ATT definidos pela Apple

| Status da ATT | Disponibilidade do IDFA | Comportamento |
| --- | --- | --- |
| not\_determined | No iOS 14-14.4: Disponível<br /><br />A partir do iOS 14.5: Não disponível | Valor padrão da ATT |
| restricted | Não disponível | Isto é determinado pela Apple com base na conta iTunes e não está relacionado com o comportamento do usuário. Por exemplo, com base na idade do usuário, dispositivos controlados por organizações. |
| denied | Não disponível | Ocorre quando:<ul><li>Esse valor foi definido antes da exibição do prompt</li><li>O usuário desativou a opção *permitir solicitações* (no nível do dispositivo)</li><li>Antes que o usuário instalasse o iOS 14 no dispositivo, a opção LAT estava ativada</li></ul> |
| authorized | Disponível | O usuário deu seu consentimento explícito |

<div id="additional-att-values-defined-by-appsflyer" />

#### Valores ATT adicionais definidos pela AppsFlyer

| Status da ATT | Observação | Disponibilidade do IDFA |
| --- | --- | --- |
| af\_unknown | O valor ATT foi reportado pelo anunciante, mas não é um valor conhecido de acordo com a especificação <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> | Dependente da versão do iOS |
| af\_authorized | O uso do IDFA é autorizada por uma das seguintes razões:<ul><li>Versão iOS do dispositivo: anterior ao iOS 14.</li><li>O evento reportado continha IDFA mas não ATT. Por exemplo, um app com o SDK V5. X num dispositivo com uma versão do iOS anterior ao iOS 14.</li></ul> | Disponível |
| af\_unavailable | <ul><li>O ATT não foi reportado no evento pelo anunciante e o IDFA não está disponível.</li><li>A versão V5. X do SDK da AppsFlyer não consegue obter o ATT e não obteve o IDFA</li></ul> | Não disponível |

<div id="is-lat-in-iosconsiderations-and-how-lat-translates-to-att-in-ios-14" />

### Is LAT está no iOS - considerações e como o LAT se traduz em ATT no iOS 14

| Versão do iOS | Uso de Is LAT |
| --- | --- |
| Até iOS 13 | <Image alt="IsLatTrue_us-en.png" src="https://files.readme.io/28440075d9c3913a148228a85ede15048d76f24913b48799ec4de3952d8f33e7-360011938457.png" width="221px" /><br /><br />Se for verdadeiro, o Limit ad tracking / Rastreamento de anúncios limitado ativado pelo usuário, o IDFA não está disponível. |
| A partir do iOS 14 | <Anchor target="_blank" href="https://developer.apple.com/documentation/adsupport/asidentifiermanager/1614148-isadvertisingtrackingenabled">A Apple descontinuou</Anchor> o <Anchor target="_blank" href="https://developer.apple.com/documentation/adsupport/asidentifiermanager/1614148-isadvertisingtrackingenabled">*Is LAT*</Anchor>. Ignore o valor *Is LAT* e use ATT no lugar dele. |

**Como o LAT se traduz em ATT no iOS 14**

<Image align="center" alt="LATtoiOS14.5.png" src="https://files.readme.io/872b3acdcd975337ff4de791a9fc98cd45eb50a487e80b3dfad6a1c7d9495739-360017977837.png" width="522px" />

<div data-zendesk-anchors="att-values=valores-att h_01HGX9468F5YF0KSHB3S49CW2Y=valores-att att-values-defined-by-apple=valores-att-definidos-pela-apple h_01HGX9468F0TFTMKP1W2J6GEBV=valores-att-definidos-pela-apple additional-att-values-defined-by-appsflyer=valores-att-adicionais-definidos-pela-appsflyer h_01HGX96RG9NX9QM2WTX8789DDR=valores-att-adicionais-definidos-pela-appsflyer is-lat-in-ios%E2%80%94considerations-and-how-lat-translates-to-att-in-ios-14=is-lat-est%C3%A1-no-ios---considera%C3%A7%C3%B5es-e-como-o-lat-se-traduz-em-att-no-ios-14 h_01HGX9468F0VTYNXBJRSTNBCMB=is-lat-est%C3%A1-no-ios---considera%C3%A7%C3%B5es-e-como-o-lat-se-traduz-em-att-no-ios-14" />

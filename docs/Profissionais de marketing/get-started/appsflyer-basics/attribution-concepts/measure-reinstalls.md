---
title: Mensuração de reinstalações
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2022-10-27T07:37:21Z'
  edited_at: '2026-08-19T00:09:20Z'
  id: 10164066030737
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/10164066030737
---
> **Resumo**: uma reinstalação ocorre quando um usuário instala o aplicativo, o desinstala e então o reinstala. As reinstalações resultam em um dos seguintes tipos de atribuição: reinstalação não orgânica, reinstalação orgânica ou nova atribuição (retargeting). As reinstalações ajudam a evitar várias cobranças para usuários que desinstalam e instalam novamente.

## O que é uma reinstalação

Uma reinstalação ocorre quando um usuário do aplicativo exclui um aplicativo e o reinstala durante a <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window#janela-de-reatribuição">janela de reatribuição.</Anchor>

A reinstalação pode vir de uma campanha de retargeting (reatribuição), um canal orgânico ou um canal não-orgânico.

As reinstalações provenientes de um canal orgânico ou não-orgânico e que ocorrem dentro da <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window#janela-de-reatribuição">janela de reatribuição</Anchor> são chamadas de reinstalações.

As reinstalações provenientes de campanhas de retargeting são chamadas de reatribuições.

Elas diferem na maneira como os eventos de reinstalação e in-app são atribuídos.

Se ocorrer uma instalação fora da <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window#janela-de-reatribuição">janela de reatribuição</Anchor>, a reinstalação será chamada de <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window#new-install">nova instalação</Anchor>. Uma nova instalação é atribuída ao canal de mídia (ou orgânico, se nenhum engajamento for registrado) e uma nova janela de reatribuição começa.

A tabela abaixo mostra o que a AppsFlyer chamaria de diferentes reinstalações

| Fonte de reinstalação | A janela de reatribuição é válida? | O usuário interagiu com uma campanha de retargeting antes de reinstalar? | O usuário interagiu com uma campanha de UA antes de reinstalar? | Como isso é chamado |
| --- | --- | --- | --- | --- |
| Campanha de retargeting | Sim | Sim | Não | Re-atribuição |
| Canal orgânico ou não-orgânico | Sim | Não | Sim ou não | Reinstalação |
| Canal orgânico ou não-orgânico | Não | Não | Sim ou não | Nova instalação |

## Por que as reinstalações são importantes

Além de ser uma boa indicação de que os usuários estão voltando para seu aplicativo e de que suas campanhas estão funcionando, a atribuição de reinstalação adequada é importante para ajudar a evitar várias cobranças para usuários que desinstalam e instalam novamente dentro da <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window#janela-de-reatribuição">janela de reatribuição</Anchor>.

Da mesma forma, eventos in-app que ocorreram a partir de reinstalações e são atribuídos à fonte de mídia original (primeira instalação) é um processo que permite que os anunciantes entendam melhor como os usuários se engajam com um app. Ele também mostra a eficácia das campanhas de UA e anúncios de retargeting. Para mais informações, veja a seção de [eventos in-app](#eventos-in-app-pós-instalação) abaixo.

## Fluxo de reinstalação e resultados

<div id="reinstall" />

<Accordion title="Reinstalação">

Após a primeira instalação do aplicativo, o usuário desinstala e reinstala durante a <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window#janela-de-reatribuição">janela de reatribuição</Anchor>. Uma reinstalação pode vir de uma campanha orgânica ou de UA (veja [exemplos](/docs/measure-reinstalls#examples)).

Em seguida:

* A instalação NÃO é atribuída - não aparece no dashboard, nem nos dados
* Parceiros podem receber postbacks de reinstalação apenas quando oferecem suporte a essa capacidade e quando recebem permissões explícitas por parte da AppsFlyer. Os anunciantes podem optar por enviar postbacks de reinstalação para um único parceiro ou para todos os canais de mídia, incluindo orgânicos, na página **Integração ativa**, na seção de postbacks de *instalação*.
* Consulte [eventos in-app](/docs/measure-reinstalls#eventos-in-app-pós-instalação) para mais informações sobre como os eventos in-app são atribuídos

</Accordion>

<div id="reattribution" />

<Accordion title="Re-atribuição">

Após a instalação do primeiro aplicativo, o usuário desinstala, inicia uma campanha de retargeting e reinstala durante a <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window#janela-de-reatribuição">janela de reatribuição</Anchor>.

Em seguida:

* A instalação é atribuída à fonte de mídia de retargeting na visualização unificada e de retargeting do painel Visão geral
  * A visualização de aquisição do usuário não contém reatribuições
* Todos os eventos in-app a seguir são atribuídos ao canal de mídia de retargeting (consulte [eventos in-app](/docs/measure-reinstalls#eventos-in-app-pós-instalação) para mais informações)
* Um postback de instalação é enviado para o canal de mídia de retargeting

Para mais informações sobre a atribuição de retargeting, clique <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">aqui</Anchor>.

</Accordion>

## Eventos in-app pós-instalação

Os eventos in-app executados por um usuário após uma reinstalação são considerados orgânicos atribuídos, não-orgânicos atribuídos ou orgânicos não atribuídos, a depender do **status da atribuição de eventos pós-instalação** (saiba mais abaixo). Um exemplo de evento in-app é um usuário que reinstala um aplicativo e faz uma compra in-app.

[![](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)

<div id="postreinstall-events-attribution-state" />

<Accordion title="Status da atribuição de eventos pós-reinstalação">

<table><thead><tr><th>Status da atribuição de eventos pós-reinstalação</th><th>Após uma reinstalação</th><th>Após uma reatribuição</th></tr></thead><tbody><tr><td><strong>Atribuído como in-apps orgânicos</strong></td><td>orgânico não atribuído</td><td>Redirecionamento</td></tr><tr><td> <strong>Atribuído à primeira instalação</strong><span>(1)</span> </td><td>canal de mídia da primeira instalação</td><td>Retargeting <span>(2)</span> </td></tr><tr><td colspan="3"><p><span>(1) Veja as limitações abaixo</span></p><p><span><span>(2) No campo de fonte primária. O primeiro canal de mídia responsável por uma instalação estará listado no campo de canal secundário (<span>você verá isso apenas nos dados brutos</span>)</span>.</span></p></td></tr></tbody></table>

</Accordion>

<div id="unattributed-organic-inapps" />

<Accordion title="Eventos in-app orgânicos e não atribuídos">

Reinstalação

* Todos os eventos in-app são considerados como orgânicos ou desconsiderados completamente, <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">dependendo do método de relatório</Anchor>.
* Eventos in-app serão relatados com o conversion\_type e campaign\_type como "unknown".
* A data usada para agregar dados depende do evento:
  * Para a maioria dos eventos in-app originados pelo SDK, a data do download do aplicativo é usada para agregar dados; não a data da reinstalação.
  * Para eventos de receita de anúncios (af\_ad\_revenue) enviados pelo conector SDK, a data da reinstalação é usada para agregar dados.

Re-atribuição

* Todos os eventos in-app são atribuídos ao canal de mídia de retargeting

</Accordion>

<div id="attributed-to-the-first-install" />

<Accordion title="Atribuição à primeira instalação (modo de primeira instalação)">

> 📘 **Nota**
>
> O modo de primeira instalação se aplica automaticamente a aplicativos adicionados à AppsFlyer em 31 de julho de 2024 ou após essa data. Para aplicativos adicionados antes dessa data, recomendamos entrar em contato com a AppsFlyer para migrar seus aplicativos existentes para o modo de primeira instalação.

O modo de primeira instalação fornece aos anunciantes uma imagem mais clara do engajamento do usuário. Mostra a eficácia das campanhas de UA e dos anúncios de retargeting atribuindo eventos in-app ao canal original, em vez de considerá-los orgânicos.

* **Reinstalação no modo de primeira instalação:** Todos os eventos in-app gerados a partir de reinstalações são atribuídos à instalação original (1). A hora da instalação para o evento in-app atribuído é a hora em que a primeira instalação ocorreu, não a hora em que a reinstalação ocorreu. Por exemplo, se houve uma instalação em 1 de março e depois uma reinstalação em 5 de março, e se a opção "Atribuição de eventos pós-instalação" estiver ativada, qualquer compra feita após a reinstalação será atribuída à hora de instalação do dia 1 de março.
* **Reatribuição no modo de primeira instalação:** Todos os eventos in-app são atribuídos ao anúncio de retargeting no canal primário e à instalação original no canal secundário. (2)

(1) Saiba mais sobre as [limitações abaixo.](/docs/measure-reinstalls#limitations)

(2) Essas informações ficam disponíveis apenas nos dados brutos.

> 📘 **Nota**
>
> Os dados de KPI orgânicos no dashboard podem mostrar um valor mais baixo com a **Atribuição de eventos pós-reinstalação** configurada como **Atribuída à primeira instalação**, pois alguns desses números podem ser atribuídos a um canal de mídia não orgânico.

#### Exemplos de atribuição no modo de primeira instalação.

**Exemplo 1**

Um usuário instala o aplicativo (dia 0), faz uma compra de R$10 e desinstala o aplicativo.

No dia seguinte (dia 1), o usuário reinstala o aplicativo e faz uma compra de R$5.

![Reinstall_1.jpg](https://files.readme.io/7e8eccb3a6873b42a1d8503c0f027386728adb2eecbe457451d2e37c0a7b6774-10225445609873.jpg)

Como o usuário já fez uma compra antes de reinstalar, não haverá uma contagem adicional de usuários únicos.

| Canal de mídia | usuários | Af\_purchase:<br /><br />Usuários únicos<br /><br />Dia 0 | Af\_purchase:<br /><br />Usuários únicos<br /><br />Dia 1 (cumulativo) | Resultados<br /><br />Dia 0 | Resultados<br /><br />Dia 1 (cumulativo) |
| --- | --- | --- | --- | --- | --- |
| Media\_source\_A | 1 | 1 | 1 | R$10 | R$15 |

Veremos um aumento das receitas com o mesmo `device_identifier`.

| Appsflyer\_id | Identificador de dispositivo | Canal de mídia | Nome do evento | Data do evento |
| --- | --- | --- | --- | --- |
| 111 | XXX | media\_source\_A | instalação | dia 0 |
| 111 | XXX | media\_source\_A | af\_compra | dia 0 |
| 222 | XXX | Orgânica | reinstall | dia 1 |
| 222 | XXX | media\_source\_A | af\_compra | dia 1 |

**Exemplo 2**

Um usuário instala o aplicativo (dia 0), faz uma compra e desinstala o aplicativo.

No dia seguinte (dia 1), ele reinstala o app a partir de uma campanha de UA e faz uma compra.

| Canal de mídia | Nome do evento | Data do evento | Atribuição de reinstalação | Atribuição de eventos in-app |
| --- | --- | --- | --- | --- |
| media\_source\_A | instalação | dia 0 | media\_source\_A |  |
| media\_source\_A | af\_compra | dia 0 |  | media\_source\_A |
| media\_source\_B | reinstall | dia 1 | media\_source\_B |  |
| media\_source\_B | af\_compra | dia 1 |  | media\_source\_A |

</Accordion>

<div id="confirm-inapps-are-attributed-to-the-original-install" />

<Accordion title="Confirmar que os eventos in-app foram atribuídos à instalação original">

No seu relatório de dados brutos, você pode verificar se os seus eventos in-app pós-instalação seguem a lógica do modo de primeira instalação seguindo os seguintes passos:

* Verifique o campo `install_time` no evento in-app. Se ele mostrar a hora da instalação original (e não da reinstalação), o evento foi atribuído à primeira instalação.
* Verifique o `device_id` (GAID ou IDFA). Ele deve ser o mesmo em todas as instalações e reinstalações, de modo que você possa usá-lo para conectar o evento à instalação original.
* O `appsflyer_id` do evento in-app é diferente do valor da instalação original. A AppsFlyer gera um novo AppsFlyer ID após cada reinstalação.

</Accordion>

<div id="limitations" />

<Accordion title="Limitações">

* Somente os usuários que consentiram em compartilhar seu identificador de dispositivo (como IDFA ou GAID) com o aplicativo para instalação e reinstalação terão seus eventos in-app atribuídos à instalação original
  * Os identificadores de dispositivo na primeira instalação e na reinstalação devem corresponder.
* A reinstalação deve ocorrer dentro da <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#reengagement-rules-and-windows">janela de reatribuição</Anchor> da última instalação registrada.
* Cada instalação e reinstalação ainda terá seu próprio `appsflyer_id` exclusivo.
* Os dashboards não diferenciam entre um evento in-app pós-instalação ou reinstalação
  * É possível ver isso através dos dados brutos
* Reinstalações não são mensuradas pelo SDK do Windows da AppsFlyer.

</Accordion>

## Como os dados aparecem nos dashboards da AppsFlyer

<table><thead><tr><th colspan="2"> </th><th>Reinstalação não orgânica</th><th>Reinstalação orgânica </th><th>Re-atribuição</th></tr></thead><tbody><tr><td colspan="2">A reinstalação em si</td><td>Não visualizada</td><td>Não visualizada</td><td>Fonte de mídia de retargeting\*</td></tr><tr><td rowspan="2">Atribuições de eventos in-app daqui para frente</td><td>Eventos pós-reinstalação definidos como <strong>Atribuídos como in-apps orgânicos</strong> </td><td>Orgânico não atribuído</td><td>Orgânico não atribuído</td><td>Canal de mídia de retargeting</td></tr><tr><td>Eventos de pós-reinstalação definidos como <strong>Atribuídos à primeira instalação</strong> </td><td>Primeiro canal de mídia</td><td>Primeiro canal de mídia</td><td>Campanhas de retargeting</td></tr><tr><td colspan="5">\*Somente no dashboard de visão geral.</td></tr></tbody></table>

## Relatórios de dados brutos de reinstalações

> 🚧 **Pré-requisitos**
>
> Requer ativação. Entre em contato com seu CSM para falar sobre isso.

* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQtlerXtCVImurv-JyuG7JMPvLN6p2w79pmbMNBx6WBnLwnYq5bUqXiUuoy2l_UTzEjIr8UkDdclRxf/pub?output=csv">Reinstale o relatório de exemplo como um arquivo CSV</Anchor>

#### Como os eventos de instalação e in-app são atribuídos

<table><thead><tr><th colspan="2"> </th><th>Reinstalação não orgânica</th><th>Reinstalação orgânica </th><th>Re-atribuição</th><th>Instalação não orgânica</th><th>Instalação orgânica</th></tr></thead><tbody><tr><td colspan="2">Atribuído a </td><td>Campanha de UA</td><td>Orgânico</td><td>Campanhas de retargeting</td><td>Campanha de UA</td><td>Orgânico</td></tr><tr><td rowspan="2">Atribuição de evento daqui para frente</td><td>Eventos pós-reinstalação definidos como <strong>Atribuídos como in-apps orgânicos</strong> </td><td>Orgânico</td><td>Orgânico</td><td>Campanhas de retargeting</td><td>Campanha de UA</td><td>Orgânico</td></tr><tr><td>Eventos de pós-reinstalação definidos como <strong>Atribuídos à primeira instalação</strong> </td><td>Primeira instalação</td><td>Primeira instalação</td><td>Campanhas de retargeting</td><td>Campanha de UA</td><td>Orgânico</td></tr></tbody></table>

### Disponibilidade de relatórios de reinstalação

* Os relatórios de dados brutos de reinstalação estão disponíveis nas ferramentas de envio detalhadas na tabela a seguir.
* Os relatórios têm a mesma estrutura e são preenchidos de maneira semelhante para relatórios de instalação em que:
  * Os campos de **canal de mídia** são preenchidos usando o canal de mídia que trouxe a reinstalação ou orgânico.
  * **Hora da instalação**: é a hora da reinstalação, ou seja, o horário da primeira abertura do aplicativo após a reinstalação
  * **Nome do evento:** *Reinstalação*

| Método de envio do relatório | Reinstalação não orgânica | Reinstalação orgânica |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Exportar dados</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/pt/docs/pull-api-aggregate-data">Extrair API</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Relatório do Data Locker</Anchor> | ✓ | ✓ |
| API de push | ✓ | ✓ |

<div data-zendesk-anchors="what-is-a-reinstall=o-que-%C3%A9-uma-reinstala%C3%A7%C3%A3o 01H7SZVZPGHBQ7VM8TMWRD3CE4=o-que-%C3%A9-uma-reinstala%C3%A7%C3%A3o why-are-reinstalls-important=por-que-as-reinstala%C3%A7%C3%B5es-s%C3%A3o-importantes 01H7SZVZPG6T2AW9B3EMT29AQQ=por-que-as-reinstala%C3%A7%C3%B5es-s%C3%A3o-importantes reinstall-flow-and-outcome=fluxo-de-reinstala%C3%A7%C3%A3o-e-resultados 01H7SZVZPGVQCNCQ7TCZMYM33T=fluxo-de-reinstala%C3%A7%C3%A3o-e-resultados 01H7SZVZPGCDP3GRK1BWZ04MR6=reinstall 01H7SZVZPG8WNTK30YXNZ44VTS=reattribution inapp-events=eventos-in-app-p%C3%B3s-instala%C3%A7%C3%A3o 01H7SZVZPGBYRWZGAZRT36EFGH=eventos-in-app-p%C3%B3s-instala%C3%A7%C3%A3o h_01K47GSZ90CKBGPCZFGQBD1PMK=postreinstall-events-attribution-state 01H7SZVZPH4AE1PZK8V5JG6C6X=unattributed-organic-inapps 01H7SZVZPH7KPM7T42GHZ7N69S=attributed-to-the-first-install h_01KHJV7J6H5KKMZVZN8XPW4CEZ=nota 01H7SZVZPH5YGSMPGW7NPKXJAF=nota-1 with-attributed-to-the-first-install-enabled=exemplos-de-atribui%C3%A7%C3%A3o-no-modo-de-primeira-instala%C3%A7%C3%A3o 01H7SZVZPHH3DS9J4VRD70VTX6=exemplos-de-atribui%C3%A7%C3%A3o-no-modo-de-primeira-instala%C3%A7%C3%A3o h_01K47KBXE2NXXQFMS4RPJ0RA4T=confirm-inapps-are-attributed-to-the-original-install 01H7SZVZPH8MSBQ92XWFK0HWGQ=limitations how-does-the-data-appear-in-the-appsflyer-dashboards=como-os-dados-aparecem-nos-dashboards-da-appsflyer 01H7SZVZPHHQS4NHEDATD7ZP9V=como-os-dados-aparecem-nos-dashboards-da-appsflyer reinstalls-raw-data-reports=relat%C3%B3rios-de-dados-brutos-de-reinstala%C3%A7%C3%B5es 01H7SZVZPHPWN8REBQ5CWVFNJT=relat%C3%B3rios-de-dados-brutos-de-reinstala%C3%A7%C3%B5es 01H7SZVZPHCVDPDDYD6HHNFMMK=pr%C3%A9-requisitos how-the-install-and-inapp-events-are-attributed=como-os-eventos-de-instala%C3%A7%C3%A3o-e-in-app-s%C3%A3o-atribu%C3%ADdos 01H7SZVZPHQT8XS3ZBA4W682GB=como-os-eventos-de-instala%C3%A7%C3%A3o-e-in-app-s%C3%A3o-atribu%C3%ADdos availability-of-reinstall-reports=disponibilidade-de-relat%C3%B3rios-de-reinstala%C3%A7%C3%A3o 01H7SZVZPH6NY7FMG9YHDBB95R=disponibilidade-de-relat%C3%B3rios-de-reinstala%C3%A7%C3%A3o" />

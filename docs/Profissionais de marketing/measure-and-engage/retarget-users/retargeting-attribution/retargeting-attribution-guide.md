---
title: Guia de atribuição de retargeting
metadata:
  keywords:
    - Attribution
    - Re-targeting
    - retargeting
    - Advertisers
    - reatribution
    - re-atribution
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-30T13:18:26Z'
  edited_at: '2026-08-18T00:37:18Z'
  id: 207033786
  locale: pt
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/pt/articles/207033786
---
> **Visão geral:** as campanhas de retargeting (remarketing) motivam os usuários a abrir e se reengajar com o aplicativo ou fazer com que os usuários que excluíram o aplicativo o reinstalem.

<div id="retargeting-fundamentals" />

## Fundamentos do retargeting

A atribuição de retargeting ocorre quando um usuário engaja com uma campanha de retargeting clicando em um [link de atribuição de retargeting](/docs/retargeting-attribution-guide#retargeting-attribution-links) ou <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">deep link</Anchor>. O resultado disso é em um dos seguintes eventos de atribuição:

* Reengajamento:/strong> se o aplicativo estiver no dispositivo, a fonte de mídia que motiva o usuário a abrir o aplicativo é creditada com um reengajamento.
* **Reatribuição (ou reinstalação de retargeting)**: se o aplicativo não estiver no dispositivo do usuário (ou seja, o usuário desinstalou o aplicativo), o engajamento com a campanha de retargeting fará com que o usuário reinstale e abra o aplicativo. Se isso acontecer durante uma <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição:</Anchor> a fonte de mídia de redirecionamento é creditada com a reatribuição. Leitura relacionada: <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#reinstalls">Reinstalações.</Anchor>

![](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

Antes de executar campanhas de retargeting, revise as regras de reengajamento e os casos de exemplo nas seções a seguir e configure o retargeting conforme descrito na seção sobre procedimentos de retargeting. Para facilitar a compreensão, você deve estar familiarizado com o <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">modelo de atribuição</Anchor> da AppsFlyer e com as janelas de atribuição associadas.

<div id="tip" />

> 👍 **Dica**
>
> Quer saber mais sobre retargeting? Confira nosso  <Anchor target="_blank" href="https://elevate.appsflyer.com/pages/142/remarketing">curso rápido e informativo no portal de aprendizado da AppsFlyer</Anchor>.

<div id="reengagement-rules-and-windows" />

<Accordion title="Regras e janelas de reengajamento">

* As regras de atribuição de retargeting determinam se um evento é um evento de retargeting e atribuído à fonte de mídia de retargeting.
* Semelhante às campanhas de atribuição de aquisição de usuários, os reengajamentos de retargeting de SRN são reportados pela API e os de não-SRN são reportados por link de atribuição.
* As regras, baseadas na jornada do usuário, consistem em:
  * [Janelas de inclusão](/docs/retargeting-attribution-guide#janelas-de-inclusão), período durante o qual pode ocorrer um reengajamento.
  * [Janelas de exclusão](/docs/retargeting-attribution-guide#janelas-de-exclusão), período durante o qual não pode ocorrer um reengajamento.
* Se um reengajamento for atribuído, os eventos no aplicativo durante a janela de reengajamento serão <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">atribuídos duas vezes</Anchor>. Isso significa que é atribuído tanto à fonte de mídia de retargeting quanto à fonte de mídia original da UA, se conhecida.

O diagrama a seguir contém o conjunto de regras de reengajamento. Use-o como um guia para determinar se uma interação com uma campanha de retargeting será atribuída como um reengajamento.

**Regras de reengajamento**

![](https://files.readme.io/e6643112f3e9969242c0dd394f6401406fbc837a9494cc4bb3825cff6365f36d-33563511578513.png) **Referência — janelas de inclusão e exclusão**

As tabelas a seguir contêm informações de referência que dizem respeito às janelas relacionadas à atribuição de retargeting.

<div id="inclusion-windows" />

#### Janelas de inclusão

| Tipo de janela | Descrição |
| --- | --- |
| Exibição (view-through) | A duração máxima a partir do momento em que o usuário visualiza um anúncio até abrir um aplicativo.<br /><br />**Configuração:** Link de atribuição<br /><br />**Duração**:<ul><li>Padrão: 1 dia</li><li>Intervalo: 1-23 horas/1-7 dias</li></ul> |
| Lookback de clique | A duração máxima desde o momento em que um usuário clica em um anúncio até abrir um aplicativo.<br /><br />**Configuração:** Link de atribuição<br /><br />**Duração**:<ul><li>Padrão: 7 dias</li><li>Intervalo: 1-23 horas/1-30 dias</li></ul>**Observações da SRN:** verifique com a SRN qual é sua política específica de janela de lookback. |
| Re-engajamento | Considere o seguinte em relação à janela de reengajamento:<ul><li>A janela começa quando o usuário abre o aplicativo pela primeira vez depois de se engajar com o canal de mídia de retargeting.</li><li>Os eventos in-app são <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">atribuídos duas vezes</Anchor> aos canais de mídia de retargeting e de aquisição de usuários ao longo da duração da janela.</li><li>A duração da janela é determinada pela configuração do aplicativo ou pela SRN.</li><li>Se o usuário engajar com outra campanha de retargeting durante a janela de reengajamento, que não é bloqueada por uma janela de exclusão, a janela de reengajamento atual termina imediatamente e uma nova janela de reengajamento será iniciada.</li><li>No contexto de uma reatribuição: A duração da **janela de atribuição**é ilimitada(semelhante às instalações). No entanto, essa janela termina no caso de uma nova instalação, reinstalação ou devido a limitações de retenção de dados.</li></ul>**Configuração:** Link de atribuição<ul><li>Padrão: 30 dias</li><li>Intervalo: 1-23 horas/1-90 dias/tempo de vida</li></ul>**Observações para SRN**: configurável para SRNs<br /><br />Se você alterar a configuração da janela, a alteração afetará os reengajamentos no futuro. Isso não tem impacto sobre os reengajamentos existentes. |

<div id="exclusion-windows" />

#### Janelas de exclusão

| Tipo de janela | Descrição |
| --- | --- |
| Intervalo mínimo entre conversões de reengajamento | Não registrar um novo reengajamento durante a janela de exclusão.<br /><br />**Intervalo mínimo entre conversões de reengajamento**<ul><li>No reengajamento, uma janela durante a qual os eventos in-app são atribuídos tanto às campanhas de retargeting (principal) quanto de UA (não primária) é aberta.</li><li>Isso permite a mensuração da performance da campanha de retargeting.</li><li>Se outra rede ou campanha trouxer um reengajamento durante esta janela:<ul><li>[Padrão] a janela de reengajamento existente é fechada, outro reengajamento é registrado e eventos subsequentes no aplicativo são atribuídos ao reengajamento mais recente.</li><li>Para evitar isso, defina o tempo mínimo entre conversões de reengajamento. Nesse caso, um novo reengajamento pode ser registrado somente após o tempo mínimo decorrido.</li></ul></li><li>Essa definição não tem impacto nos casos em que a janela de reengajamento é menor do que a duração dessa definição. Exemplo: Exemplo: se a janela de reengajamento é de 1 dia, e esta configuração é de 4 dias, então esta configuração não tem qualquer impacto.</li><li>Essas configurações não afetam a duração entre a instalação e o reengajamento.</li></ul>**Configuração:** Página de configurações do aplicativo<br /><br />**Duração**:<ul><li>Padrão: Nenhuma</li><li>Intervalo: 1-23 horas/1-30 dias</li></ul> |
| <Anchor target="_blank" href="/marketers/pt/docs/set-retargeting-inactivity-window">Período mínimo de inatividade</Anchor> | Não registe um reengajamento ou reatribuição durante o período de exclusão.<br /><br />**Configuração:** página de configurações de parceiros integrados na aba Integração.<br /><br />**Duração**:<ul><li>Padrão: Nenhuma</li><li>0-30 dias</li></ul>**Observações da SRN**: considere que as SRNs geralmente têm suas próprias regras de período de inatividade. Se a configuração for diferente da SRN, isso pode causar discrepâncias. |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">Reatribuição</Anchor> | A janela de reatribuição afeta as reatribuições, mas não os reengajamentos.<br /><br />Os usuários que reinstalam durante a janela de reatribuição depois de engajar com uma campanha de retargeting são atribuídos às fontes de mídia de retargeting. Leitura relacionada: <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#reinstalls">Reinstalações</Anchor><br /><br />**Configuração:** Configurações do aplicativo |

<div id="example-flow-implementing-the-rules" />

#### Exemplo de fluxo de implementação das regras

![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)

Checklist de regras de reengajamento para atribuição de click-through e view-through:

| Regra | Regra |
| --- | --- |
| E | O usuário se engajou com uma campanha de retargeting, o que significa que ele visualizou ou clicou em um anúncio definido como um anúncio de retargeting. |
| B | O engajamento ocorreu **durante** uma janela de lookback de cliques ou de exibição. |
| C | O usuário ficou inativo por mais tempo do que o período mínimo de inatividade. |
| J | No caso de eventos in-app, eles ocorrem durante a janela de reengajamento. |
| E | O período entre o reengajamento anterior é maior do que o tempo mínimo entre os reengajamentos. |

</Accordion>

<div id="example-retargeting-scenarios" />

<Accordion title="Exemplo de cenários de retargeting">

| **Cenário 1: compras antes, durante e depois da janela de reengajamento**<br /><br />Viagem do utilizador:<ul><li>O usuário se engaja com um anúncio da ad network Z, instala o aplicativo e faz uma compra (A).</li><li>Ele engaja com um anúncio de retargeting da rede Y, abre o aplicativo e faz uma compra (B).</li><li>Ele faz uma compra (C).</li></ul>![](https://files.readme.io/f4b53c27319370434863c156bf29051db9c2c12fda2128d0faf0f8a6ca6b7002-33563511579537.png)<br /><br />Coluna P/S: Primária ou Secundária descrita em <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">atribuição dupla de eventos de retargeting</Anchor> |
| --- |
| Cenário 2: Múltiplas conversões durante a janela de atribuição de reengajamento<br /><br />Viagem do utilizador:<ul><li>O usuário se engaja com um anúncio da ad network Z, instala o aplicativo e faz uma compra (A).</li><li>Ele engaja com um anúncio de retargeting da rede Y, abre o aplicativo e faz uma compra (B).</li><li>Ele faz uma compra (C).</li></ul>![](https://files.readme.io/bf57f8a9597bd56a89bb3f1be3700195e1b153b548cb11ee3d37c65d5382e711-33563474530321.png)<br /><br />Coluna P/S: Primária ou Secundária descrita em <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">atribuição dupla de eventos de retargeting</Anchor> |

</Accordion>

<div id="retargeting-operations" />

## Operações de retargeting

<div id="retargeting-settings" />

<Accordion title="Configurações de retargeting">

As seguintes configurações são necessárias dependendo do cenário.

| Tipo de conversão | SRN | Não-SRN |
| --- | --- | --- |
| Re-engajamento | <ol><li>Na AppsFlyer, no menu lateral, selecione **Configurações**> **Configurações do aplicativo**.</li><li>Verifique se a **atribuição de reengajamento** está ativada.</li><li>Por SRN:</li><li>No menu lateral, selecione **Colaborar** > **Integrações ativas** e escolha a SRN.</li><li>Ative a **atribuição de reengajamento**.</li></ol> | <ol><li>Na AppsFlyer, no menu lateral, selecione **Configurações**> **Configurações do aplicativo**.</li><li>Verifique se a atribuição de **reengajamento** está ativada.</li><li>Por não-SRN: Anexe o parâmetro de retargeting aos links de atribuição conforme detalhado nesta seção.</li></ol> |
| Reatribuição | <ol><li>No menu lateral, selecione **Colaborar** > **Integrações ativas** e</li><li>ative **Atribuição de reinstalação**.</li></ol> | <ol><li>Nenhuma configuração explícita é necessária.</li><li>Anexe o parâmetro de retargeting aos links de atribuição conforme detalhado nesta seção.</li></ol> |

<div id="non-srn-settings" />

#### **Configurações para não-SRNs**

**Para configurar um parceiro de retargeting de uma ad network (não-SRN)**:

1. No menu lateral, selecione **Colaborar** > **Integrações ativas**.
2. Selecione a ad network.
3. Ative **Habilitar** **configurações de retargeting**. Isto altera o link de atribuição para uma URL de retargeting, adicionando `is_retargeting=true` ao link.

   [![](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)](https://files.readme.io/68b8939885439a4f0e6d1ec6601552185905d1afc817da9fb88ccfe043a83364-33563511582609.png)
4. Escolha uma das seguintes opções:
   * **Use um link de atribuição padrão** para links de plataforma única (específicos do aplicativo).
   * **Use o OneLink**.
     * Insira uma **URL de deep link**, se necessário (consulte o guia de <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Deep Linking</Anchor>).
5. Copie a URL gerada e ofereça à ad network para usar com a sua campanha de retargeting.  
   **Atenção:** a URL não é persistente e não pode ser salva.

</Accordion>

<div id="retargeting-dashboard" />

<Accordion title="Dashboard de retargeting">

O dashboard de Visão geral contém métricas de retargeting, além de métricas de aquisição de usuários. As métricas são baseadas em LTV e estão relacionadas a usuários que engajam com uma campanha de retargeting.

**Para ver os dados de retargeting**:

1. No menu lateral, selecione **Analisar** > **Visão Geral**.
2. Clique em **Tipo de Visualização** e selecione **Retargeting**.  
   Os dados de retargeting são exibidos.  
   **Atenção:** Você também pode visualizar os dados de retargeting na visualização unificada. Consulte Tipos de visualização do dashboard.

</Accordion>

<div id="retargeting-attribution-links" />

<Accordion title="Links de atribuição de retargeting">

* Os links de retargeting são semelhantes aos links de aquisição de usuários comuns.
* Crie-os para:
  * Não-SRNs que são compatíveis com retargeting.
  * Mídia própria, usando a página de <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">gerenciamento do link</Anchor>.

Parâmetros do link de atribuição de retargeting

| Parâmetro | Descrições | Obrigatório |
| --- | --- | --- |
| `is_retargeting` | Definir como: `is_retargeting=true` | Sim |
| ID de publicidade | Sempre que possível, envie um advertising ID como IDFA, OAID, IDFV e outros. <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">Limitações da Modelagem Probabilística para aplicativos do iOS.</Anchor> | Não |
| Janela de lookback de clique de retargeting | <ul><li>A <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de cliques</Anchor> para retargeting funciona como a das campanhas de aquisição de usuários.</li><li>Ela define o período máximo que pode decorrer entre o clique de um usuário em um anúncio até a sua atribuição.</li><li>A janela de lookback é definida usando o parâmetro `&af_click_lookback`.</li><li>O padrão é 7 dias.</li></ul>**<span id="01ECF12NKTFH6Q2NH4B1WKSYF9"></span>Exemplo**<br />Para definir uma janela de lookback de click-through de 14 dias, adicione o seguinte ao link de atribuição da campanha de retargeting: `&af_click_lookback=14d` | Não |
| Timer de lookback de view-through para retargeting | <ul><li>A <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de view-through</Anchor> para retargeting funciona como a das campanhas de aquisição de usuários.</li><li>Ela define o período máximo que pode decorrer entre a exibição de um anúncio a um usuário e sua atribuição.</li><li>O parâmetro padrão é 1 dia.</li><li>A janela de lookback é configurada usando</li></ul>`af_viewthrough_lookback={time}`<br /><br /><br /><br />**<span id="01ECF12NKTE8W4K72VATN9RM2X"></span>Exemplo**<br />Para definir uma janela de lookback de view-through de 5 horas, adicione o seguinte ao link de atribuição da campanha de retargeting: `&af_viewthrough_lookback=5h` | Não |
| Janela de reengajamento | <ul><li>A **janela de reengajamento** pode ser definida na interface do usuário do link de atribuição. Isso define o parâmetro **af\_reengagement\_window** no link de atribuição. O parâmetro pode ser adicionado manualmente.</li><li>O padrão é 30 dias.</li><li>Os seguintes valores da janela de reengajamento estão disponíveis:</li><li>Horas: 1-23 horas</li><li>Dias: 1-90 dias</li><li>Vida útil: persiste até que o usuário desinstale ou execute outro novo engajamento, por exemplo, af\_reengagement\_window=lifetime</li></ul>Por exemplo, **af\_reengagement\_window=60d** significa que os eventos relatados dentro de 60 dias após o reengajamento são atribuídos à fonte de mídia de retargeting. | Não |

<div id="retargeting-view-through-lookback-period" />

#### Período de lookback de view-through de retargeting

```http
https://app.appsflyer.com/id123456789?pid=remerge_int&af_dp=mydeeplink%3A%2F%2F&
clickid={clickid}&af_siteid={publisher}&idfa={device_id_raw}&sha1_idfa={device_id}
&af_sub1={creative_name}&is_retargeting=true&af_reengagement_window=60d
```

</Accordion>

<div id="retargeting-reports-and-raw-data" />

<Accordion title="Relatórios de retargeting e dados brutos">

* Relatórios de retargeting, semelhantes aos relatórios de dados <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview">agregados</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">dados brutos</Anchor> de UA, estão disponíveis usando as ferramentas de relatório de dados brutos.
* Os eventos e as sessões de retargeting são <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">duplamente atribuídos.</Anchor>

**Relatório de conversões de retargeting**

* O relatório de Conversões de Retargeting contém dados brutos de reengajamento e reatribuição.
* Alguns campos têm um significado diferente no contexto de retargeting em relação aos usados nos relatórios de aquisição de usuários.

Interpretação de relatórios de dados brutos no contexto do retargeting

| Coluna | **Descrição** |
| --- | --- |
| Nome do evento | <ul><li>O preenchimento do campo depende do tipo de relatório.</li><li>Relatórios de eventos in-app: O nome do evento no aplicativo.</li><li>Relatórios de conversão de retargeting: reengajamento ou reatribuição. **Atenção**! No caso do Data Locker, os valores são os seguintes:<ul><li>instalação significa reatribuição</li><li>retargeting significa reengajamento</li></ul></li></ul> |
| Tipo de toque atribuído | Tipo de engajamento:<ul><li>Clique</li><li>Impressão</li></ul> |
| Hora de atribuição do toque | Tempo de engajamento de retargeting |
| Hora da instalação | A primeira inicialização do aplicativo após o reengajamento ou reatribuição. |
| Hora do evento | A hora em que o evento ocorreu |
| ID da AppsFlyer | <ul><li>Reatribuições: Um novo AppsFlyer ID</li><li>Reengajamento: Permanece inalterado</li></ul> |
| Está redirecionando | TRUE para conversões e eventos de retargeting |
| É atribuição primária | TRUE para conversões e eventos de retargeting |
| Tipo de conversão de retargeting | <ul><li>Re-engajamento</li><li>Reatribuição</li></ul> |
| Tipo de conversão | O tipo de conversão:<ul><li>não relacionada</li><li>Reinstall (1)</li><li>Re-engajamento</li><li>Unknown (2)</li></ul>(1) Se conversion\_type= reinstall e campaign\_type=retargeting é equivalente a retargeting\_conversion\_type=re-attribution<br /><br />(2) Eventos/sessões in-app não atribuídos a nenhuma fonte de mídia. |
| Tipo de campanha | A fonte que traz o usuário:<ul><li>UA</li><li>Orgânico</li><li>Redirecionamento</li><li>Desconhecido</li></ul> |
| Lookback de atribuição | Janela de lookback de click-through para retargeting |
| URL original | Contém um dos seguintes:<ul><li>Link de retargeting</li><li>Dados de deep linking</li><li>Vazio para SRNs</li></ul> |
| Campos de contribuição | Indisponível para reengajamentos |

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="app-requirements" />

<Accordion title="Requisitos do aplicativo">

Para executar campanhas de retargeting, o aplicativo deve atender aos seguintes requisitos mínimos.

* /docs/ctv-pc-and-console-platform-attribution-concepts
  * Além da integração padrão do SDK da AppsFlyer, você deve adicionar um código adicional ao representante do aplicativo. Veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#deep-linking-com-o-onelink">Integração do SDK</Anchor> (seção links de atribuição).
  * O código para Abertura de aplicativo por Universal Link no iOS 9 deve ser implementado. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Universal Links com iOS 9</Anchor>.
* Android:
  * Se o deep link abre uma atividade diferente da atividade principal, consulte o artigo <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#deep-linking">Integração do SDK</Anchor> (seção links de atribuição).

</Accordion>

<div id="retargeting-limitations" />

<Accordion title="Limitações de retargeting">

* A partir de 17 de fevereiro de 2021, o retargeting terá compatibilidade com a Modelagem Probabilística.
* Os dados de custo da campanha para retargeting estão disponíveis nos painéis e relatórios de Visão geral e de Coorte na exibição unificada.

</Accordion>

<div id="faq" />

<Accordion title="Perguntas frequentes">

| **Cliques de retargeting:**<ul><li>Os cliques de retargeting incluem usuários que passaram por retargeting e se engajam com um link de atribuição da AppsFlyer.</li><li>Cliques de SRNs ou de <Anchor target="_blank" href="/marketers/pt/docs/measuring-push-notification-re-engagement-campaigns">notificações push</Anchor> não estão incluídos na contagem.</li><li>Alguns cliques resultam em novas instalações que são atribuídas como uma aquisição de usuário. Isto ocorre quando não usuários ou usuários antigos engajam com um link de retargeting e fazem a instalação após a expiração da <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor>.</li><li>Se um clique de retargeting levar à abertura de um aplicativo por meio de Universal Links ou Android App Links, mas o reengajamento não for contabilizado devido a motivos como janelas de inatividade, o clique não será medido.</li></ul> |
| --- |
| **Quando a hora do toque atribuído é idêntico à hora da instalação?**<ul><li>Quando os usuários de universal links, ou app links do Android, passam por deep linking, eles são direcionados para o aplicativo sem passar primeiro pela AppsFlyer.</li><li>Quando o aplicativo é inicializado e o SDK informa um novo reengajamento, o AppsFlyer reproduz os dados do clique, usando o mesmo carimbo de data e hora da inicialização. Isto faz com que a data/hora de engajamento e da inicialização sejam idênticas.</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">Modelo de atribuição da AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide">Guia do Audiences</Anchor>

<div data-zendesk-anchors="retargeting-fundamentals=fundamentos-do-retargeting h_01HCFJHC85VK0A05X5F69E2WKT=fundamentos-do-retargeting h_01HCFJHC851PV0VR42H07VQAXF=dica h_01HCFJHC85EW8MBQ8MBXBVPF03=reengagement-rules-and-windows inclusion-windows=janelas-de-inclus%C3%A3o h_01HCFJHC85FRFJ531Y08DW03Y2=janelas-de-inclus%C3%A3o exclusion-windows=janelas-de-exclus%C3%A3o h_01HCFJHC85ECS3PJV80D943TVY=janelas-de-exclus%C3%A3o example-flow-implementing-the-rules=exemplo-de-fluxo-de-implementa%C3%A7%C3%A3o-das-regras h_01HCFJHC8529NW0ABMQ0RB3E8R=exemplo-de-fluxo-de-implementa%C3%A7%C3%A3o-das-regras h_01HCFJHC85E1SWGYN0BH603BV9=example-retargeting-scenarios retargeting-operations=opera%C3%A7%C3%B5es-de-retargeting h_01HCFJHC863XPHNWRHJ60JPSRF=opera%C3%A7%C3%B5es-de-retargeting h_01HCFJHC86XNCT5AQP48R9ZDC4=retargeting-settings nonsrn-settings=configura%C3%A7%C3%B5es-para-n%C3%A3o-srns h_01HCFJHC865V36R3H58D5PWXYY=configura%C3%A7%C3%B5es-para-n%C3%A3o-srns h_01HCFJHC860BS9YJM99G437G24=retargeting-dashboard h_01HCFJHC860Y5HZN66DRNN2Q89=retargeting-attribution-links retargeting-viewthrough-lookback-period=per%C3%ADodo-de-lookback-de-view-through-de-retargeting h_01HCFJHC863CSP03AYBXFSNC37=per%C3%ADodo-de-lookback-de-view-through-de-retargeting h_01HCFJHC86MNFRGYMN776FYHJV=retargeting-reports-and-raw-data additional-information=informa%C3%A7%C3%B5es-adicionais h_01HCFJHC86RKKPPMBYEZV4Q3X9=informa%C3%A7%C3%B5es-adicionais h_01HCFJHC862E6C46Q7645VJ6CZ=app-requirements h_01HCFJHC86SMKZ1HT5KHQNQS1N=retargeting-limitations h_01HCFJHC86BVSVRNAGJEKZFCJP=faq h_01HE7TPR7928SF2W8ZJS55Y5BG=veja-tamb%C3%A9m" />

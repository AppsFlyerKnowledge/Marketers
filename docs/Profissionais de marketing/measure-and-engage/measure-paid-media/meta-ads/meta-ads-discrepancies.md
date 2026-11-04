---
title: Discrepâncias dos anúncios do Meta
metadata:
  keywords:
    - Facebook
    - Advertisers
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
  created_at: '2021-11-09T10:10:54Z'
  edited_at: '2026-08-19T00:29:36Z'
  id: 4410481130641
  locale: pt
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/pt/articles/4410481130641
---
> **Visão geral:** saiba mais sobre as diferenças dos modelos de atribuição dos anúncios do Meta e da AppsFlyer.

<div id="meta-ads-discrepancies-with-appsflyer" />

## Discrepâncias entre os anúncios do Meta e a AppsFlyer

Como quaisquer dois players importantes do ecossistema de aquisição de usuários mobile, a AppsFlyer e o Meta ads diferem em seus modelos de atribuição. Isso pode causar discrepâncias entre os dashboards do Meta ads e da AppsFlyer.

Embora nós trabalhemos em conjunto com o Meta ads para minimizar essas discrepâncias, os anunciantes devem estar cientes das possíveis causas para essas discrepâncias, que descrevemos abaixo.

<div id="detect-a-discrepancy-between-appsflyer-and-meta-ads" />

### Detectar uma discrepância entre a AppsFlyer e o Meta ads

Compare eventos listados no **Gerenciador de eventos** do Meta ads com aqueles nos relatórios da AppsFlyer. Se o número de eventos variar significativamente, pode haver uma discrepância.

<div id="differences-in-attribution-models" />

## Diferenças em modelos de atribuição

<table><thead><tr><th>Causa</th><th>Meta Ads</th><th>A AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><strong>Janela de lookback de atribuição de cliques</strong></td><td>7 dias (Observe que <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">existem alguns casos específicos nos quais o padrão é diferente</a>).</td><td>1 a 30 dias. Certifique-se de definir 7 dias com o Meta ads.</td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><strong>Janela retroativa de atribuição por visualização</strong></td><td>1 dia (Observe que <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">existem alguns casos específicos nos quais o padrão é diferente</a>).</td><td>1 dia por padrão, mas pode ser configurada para 1–48 horas (manter este valor padrão)</td></tr><tr><td><span id="multichannel-sourceattribution"></span> Atribuição de fonte<br/>multi-canal </td><td>O Meta ads autoatribui instalações independentemente de outros canais de mídia.</td><td>A AppsFlyer usa a atribuição de último clique (veja mais informações sobre a atribuição da AppsFlyer <a href="./appsflyer-attribution-model" title="Modelo de atribuição da AppsFlyer" target="_blank">aqui</a>).</td></tr><tr><td><span id="crossdevice-attribution"></span><strong>Atribuição entre dispositivos</strong></td><td>O Meta ads atribui seus usuários que clicam e instalam em diferentes dispositivos, por exemplo, iOS/Android/desktop.</td><td>A AppsFlyer atribui dispositivos únicos, que executam tanto o engajamento quanto a instalação</td></tr><tr><td><span id="different-time-zones"></span><strong>Fusos horários diferentes</strong></td><td>O fuso horário padrão dos anúncios do Meta é PST. Certifique-se de <a href="https://www.facebook.com/business/help/754049591334898" target="_blank">alterá-lo no gerenciador de anúncios do Meta</a> para corresponder ao fuso horário do aplicativo definido nas configurações do aplicativo na AppsFlyer.</td><td>O fuso horário padrão do aplicativo da AppsFlyer é UTC + 0. Você pode alterar o fuso horário definido para o aplicativo na <a href="./app-settings#localization-time-zone" target="_blank">página configurações do aplicativo</a> para corresponder ao fuso horário definido no gerenciador de anúncios do Meta.</td></tr><tr><td><span id="google-install-referrer"></span><strong>Referenciador da instalação do Google</strong></td><td colspan="2">Quando uma instalação sem um ID de anunciante é atribuída aos anúncios do Meta usando o referenciador da instalação do Google Play, a AppsFlyer não a relata de volta aos anúncios do Meta. Isso causa uma discrepância, já que o dado será exibido na AppsFlyer e não nos anúncios do Meta.</td></tr></tbody></table>

<div id="click-through-and-view-through-attribution" />

## Atribuição de cliques e de exibição

A AppsFlyer é compatível com a atribuição de cliques e de exibição. Para minimizar as discrepâncias entre os anúncios do Meta e a AppsFlyer, certifique-se de que tanto as janelas de lookback de clique e de exibição sejam consistentes com as padrão definidas pelos anúncios do Meta.

A janela de lookback de clique padrão dos anúncios do Meta é definida para 7 dias. Embora [existam alguns casos específicos em que o padrão é diferente](https://www.facebook.com/business/help/395050428485124?id=428636648170202), é recomendável definir a janela de lookback de clique na AppsFlyer para 7 dias para abranger todas as opções padrão dos anúncios do Meta.

Recomendamos configurar as janelas de atribuição na AppsFlyer de acordo com os valores do Meta ads, conforme mostrado na captura de tela a seguir: <Anchor target="_blank" href="https://www.facebook.com/business/help/654970342692714">Consulte a documentação da Meta para desenvolvedores sobre como comparar configurações de atribuição.</Anchor> <Anchor target="_blank" href="https://www.facebook.com/business/help/654970342692714">Consulte a documentação da Meta para desenvolvedores sobre como comparar configurações de atribuição.</Anchor>

![image (13).png](https://files.readme.io/215d2234aae1ec6b4e1c6ac922915851bf8ab02574a874119d286fa49c64f9ba-25899749062033.png)

<div id="example" />

> 📄 **Exemplo**
>
> Vamos supor que a janela de lookback de cliques do Meta ads esteja configurada na AppsFlyer para 1 dia para o aplicativo com.greatapp, enquanto no Meta ads o valor padrão é de 7 dias. Usuários que clicam no anúncio do greatapp no Facebook, mas inicializam o aplicativo pela primeira vez após 2 a 7 dias, são atribuídos como usuários orgânicos na AppsFlyer, enquanto o Meta ads autorrelata esses usuários.

<div id="in-app-events-differences" />

## Diferenças nos eventos in-app

As diferenças entre plataformas também podem estar presentes em eventos pós-instalação (por exemplo, compras in-app), que são exibidos no Meta ads e na AppsFlyer. A tabela a seguir descreve os motivos mais comuns para essas diferenças e sugere algumas dicas para minimizá-las:

| Causa | Descrição | Dica da AppsFlyer |
| --- | --- | --- |
| <span id="different-lifetime-definition"></span>**Definição de tempo de vida diferente** | A vida útil de um usuário no Meta ads é definida em até 7 dias, o que significa que o Meta ads não mostra eventos se eles ocorreram mais de 7 dias após o clique no anúncio.  <br />Na AppsFlyer, a vida útil de um usuário do Meta ads é definida como até 180 dias. | Ao avaliar o valor dos usuários das campanhas do Meta ads que ocorreram há mais de 7 dias, use dados da AppsFlyer para ter uma visão mais ampla. |
| <span id="unmapped-events"></span>**Eventos não mapeados** | A AppsFlyer recebe os eventos originados do SDK, mas eles não são mapeados para o Meta ads e, portanto, não são enviados. | Certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-in-app-event-mapping">mapear com o Meta ads</Anchor> todos os eventos in-app que indicam a qualidade dos usuários. |
| <span id="unsent-revenue"></span>**Receita não enviada** | A AppsFlyer recebe a receita dos eventos originários do SDK, mas eles não são enviados para o Meta ads. | Certifique-se de que as caixas **Enviar Receita** dos eventos in-app estejam sempre marcadas. Por exemplo, no caso do evento de compra na captura de tela abaixo. |
| <span id="missing-event-values-on-facebook"></span>**Valores de eventos ausentes no Meta ads** | A AppsFlyer envia parâmetros e valores para o Meta ads como parte do mapeamento de eventos, se eles tiverem as estruturas corretas. | Crie seus eventos in-app do SDK de acordo com as <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure">estruturas recomendadas pela AppsFlyer</Anchor> para mapear totalmente os valores de eventos com o Meta ads. |
| <span id="different-event-count"></span>**Contagem de eventos diferente** | A contagem de um evento in-app específico (por exemplo, evento de compra) no dashboard do Facebook (FB) difere da contagem correspondente no dashboard da AppsFlyer (AF). | O dashboard do Facebook (FB) é baseado em atividade, enquanto os dashboards Visão geral e Eventos da AppsFlyer (AF) são baseados em LTV. Para comparar contagens de eventos, use um dashboard da AF baseado em atividade. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports#sobre-diferenças-e-discrepâncias-de-dados">LTV vs. Atividade</Anchor> |

<div id="installs-from-re-engagement-campaigns-in-my-ua-dashboard" />

## Instalações de campanhas de reengajamento em meu painel da UA?

Uma campanha de reengajamento pode fazer com que os usuários abram um aplicativo já instalado (**reengajamento**). Como alternativa, quando a AppsFlyer reconhece que houve uma instalação anterior do aplicativo no mesmo dispositivo, a AppsFlyer pode se referir a essa conversão como uma **reatribuição**.

Se, em uma campanha de reengajamento, o Meta ads chegar até **novos usuários** ou usuários que instalaram o aplicativo pela primeira vez **após mais** **do que a <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor>** definida após a instalação original, esses usuários são registrados como **novas instalações de aquisição na AppsFlyer**, que pertencem a campanhas de reengajamento no Meta ads.

Por outro lado, instalações que acontecem **dentro da janela de reatribuição definida** depois da instalação original são consideradas como reatribuições e aparecem na página de retargeting da AppsFlyer, enquanto podem aparecer como novas instalações pelo Meta ads.

<div id="note" />

> 📘 **Nota**
>
> Enquanto o Meta ads mostra todas as instalações de uma campanha de retargeting no mesmo lugar, no dashboard da AppsFlyer as instalações são divididas entre a página de Visão geral (novas instalações) e a página de Retargeting (reatribuição e reengajamentos).

<div id="cross-device-attribution" />

## Atribuição entre dispositivos

Relatórios do Meta ads sobre a atribuição entre dispositivos. Às vezes, isso pode causar problemas em que uma campanha para uma plataforma (iOS/Android) mostra instalações em outra plataforma.

<div id="example-1" />

> 📄 **Exemplo**
>
> Aline clica em um anúncio mobile do GreatApp no Facebook com seu celular Android. Os anúncios do Meta registram o clique que Alina realizou na campanha original direcionada ao Android chamada "Mulheres no Android". Aline decide instalar o GreatApp em seu iPad. Na primeira inicialização, a AppsFlyer pergunta ao Meta ads a origem dessa instalação do iOS, e o Meta ads responde com a campanha "Mulheres no Android".

<div id="validation-rules-and-protect360" />

## Regras de validação e Protect360

Se você usar as <Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud">Regras de validação da AppsFlyer</Anchor>, os resultados podem diferir entre a AppsFlyer e o Meta ads quando instalações originadas no Meta ads forem negadas. Nesses casos, o Meta ads autorrelata as instalações, enquanto a AppsFlyer recusa essas instalações.

Da mesma forma, se você usar a solução antifraude da AppsFlyer, o Protect360, é possível que haja instalações em que o Meta ads auto-reporta e a AppsFlyer nega.

<div id="example-2" />

> 📄 **Exemplo**
>
> Roberto, gerente de UA do GreatApp, cria uma campanha chamada SPNA, que tem como público-alvo somente falantes de espanhol na América do Norte. Como verificação, Roberto define uma regra de validação que aceita somente usuários do Canadá e dos EUA.
> Quando um usuário do Meta ads da Espanha realiza um clique e uma instalação, o Meta ads auto-reporta a instalação, enquanto a AppsFlyer nega a instalação que não passa pela regra da validação.

<div id="sdk-related-discrepancies" />

## Discrepâncias relacionadas ao SDK

Podem haver <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-faq#who-needs-facebooks-sdk">várias ocasiões nas quais os anunciantes implementam ambos os SDKs da AppsFlyer e do Facebook</Anchor>. Isso pode causar discrepâncias nos eventos in-app. Isso pode causar dicrepâncias nos dados de eventos in-app O Meta não desduplica eventos in-app, que são relatados por ambos os SDKs. Isso significa que há a probabilidade de que o Meta Ads relate receitas e outros eventos de forma errônea.

* Use um dos métodos a seguir para evitar relatórios de eventos in-app duplicados em anúncios do Meta:
  * Não configure eventos no SDK do Facebook.
  * Desative o <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-in-app-event-mapping">mapeamento de eventos in-app do Meta ads</Anchor> da AppsFlyer.

<div id="meta-probabilistic-modeling-aem-discrepancies-in-ios-apps" />

## Discrepâncias do modelo probabilístico da Meta (AEM) em aplicativos iOS

Quando a Mensuração agregada de eventos (AEM) está habilitada para aplicativos iOS, a Meta pode atribuir instalações ou eventos in-app usando seu modelo probabilístico. **A Meta pode aplicar métodos de modelagem diferentes em seus relatórios internos, em comparação com o que compartilha com a AppsFlyer.** Devido a essas diferenças nos métodos de modelo, as contagens de instalações exibidas no Meta Ads Manager e na AppsFlyer podem variar — às vezes para mais, às vezes para menos. Especificamente:

* A Meta pode registrar conversões internamente, mas optar por não enviar à AppsFlyer as reivindicações de AEM correspondentes.
* A Meta pode enviar à AppsFlyer uma reivindicação de AEM para uma conversão modelada que não aparece no Ads Manager.

<div data-zendesk-anchors="facebook-ads-discrepancies-with-appsflyer=discrep%C3%A2ncias-entre-os-an%C3%BAncios-do-meta-e-a-appsflyer 01H890CZSXPMK0BDMC4202HNYM=discrep%C3%A2ncias-entre-os-an%C3%BAncios-do-meta-e-a-appsflyer detect-a-discrepancy-between-appsflyer-and-facebook=detectar-uma-discrep%C3%A2ncia-entre-a-appsflyer-e-o-meta-ads 01H890CZSXGHVBH21SQA0671JQ=detectar-uma-discrep%C3%A2ncia-entre-a-appsflyer-e-o-meta-ads differences-in-attribution-models=diferen%C3%A7as-em-modelos-de-atribui%C3%A7%C3%A3o 01H890CZSX8M6VGGREYX4W2X37=diferen%C3%A7as-em-modelos-de-atribui%C3%A7%C3%A3o clickthrough-and-viewthrough-attribution=atribui%C3%A7%C3%A3o-de-cliques-e-de-exibi%C3%A7%C3%A3o 01H890CZSX40JDGY8P8AQ4CYGS=atribui%C3%A7%C3%A3o-de-cliques-e-de-exibi%C3%A7%C3%A3o 01H890CZSXRD7PCZBK52GW7QE9=exemplo inapp-events-differences=diferen%C3%A7as-nos-eventos-in-app 01H890CZSXKC5JKK9051MC0VY6=diferen%C3%A7as-nos-eventos-in-app installs-from-reengagement-campaigns-in-my-ua-dashboard=instala%C3%A7%C3%B5es-de-campanhas-de-reengajamento-em-meu-painel-da-ua 01H890CZSYE21K7PBQK4PNMGJR=instala%C3%A7%C3%B5es-de-campanhas-de-reengajamento-em-meu-painel-da-ua 01H890CZSY7TRCA4NVKSVPY7DB=nota crossdevice-attribution::77a37a1f=atribui%C3%A7%C3%A3o-entre-dispositivos 01H890CZSYS8QKEAF6799SBS8J=atribui%C3%A7%C3%A3o-entre-dispositivos 01H890CZSY2Z3S6E9R5MYC1CHX=exemplo-1 validation-rules-and-protect360=regras-de-valida%C3%A7%C3%A3o-e-protect360 01H890CZSYDHZE4V0ZWTT8V0EJ=regras-de-valida%C3%A7%C3%A3o-e-protect360 01H890CZSYCTQZCAYAZP9TCBBF=exemplo-2 sdk-related-discrepancies=discrep%C3%A2ncias-relacionadas-ao-sdk 01H890CZSYVFPQP0SKNPWMPB1R=discrep%C3%A2ncias-relacionadas-ao-sdk meta-probabilistic-modeling-aem-discrepancies-in-ios-apps=discrep%C3%A2ncias-do-modelo-probabil%C3%ADstico-da-meta-aem-em-aplicativos-ios h_01KA6NEZSRFSAJYZ5C4HJ4SKTQ=discrep%C3%A2ncias-do-modelo-probabil%C3%ADstico-da-meta-aem-em-aplicativos-ios" />

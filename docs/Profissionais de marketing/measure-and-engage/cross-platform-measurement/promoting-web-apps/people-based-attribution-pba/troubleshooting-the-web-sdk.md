---
title: Solução de problemas do SDK web
metadata:
  keywords:
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2019-07-22T13:55:15Z'
  edited_at: '2026-08-18T00:24:06Z'
  id: 360002075858
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360002075858
---
> **Resumo:** Guia de solução de problemas para o SDK web da AppsFlyer adicionado diretamente ao seu site ou implementado via Google Tag Manager.

## SDK adicionado diretamente

Você pode adicionar o SDK diretamente ao seu site.

### Sem dados ou com dados parciais no dashboard do PBA

| Motivo | solução |
| --- | --- |
| Os dados levam até 24 horas para aparecer nos <Anchor target="_blank" href="/marketers/pt/docs/pba-website-attribution-dashboard">dashboards do People-Based Analysis</Anchor> após você implementar o SDK. | Aguarde 24 horas. Se os dados ainda não estiverem disponíveis, consulte outras causas neste documento. |
| Chave do desenvolvedor web incorreta | <ul><li>O SDK web usa a chave do desenvolvedor web para identificar eventos web enviados e saber a qual bundle atribuir os dados.</li><li>Verifique se você está usando a <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working">chave de desenvolvedor web correta.</Anchor></li></ul><Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings#add-brand-bundle">Página do pacote da marca</Anchor> |
| Você colocou o SDK web no body da página | <ul><li>Você pode colocar o SDK web no body da página, mas isso pode afetar os dados enviados à AppsFlyer.</li><li>Recomendamos que você o coloque na seção head da página.</li></ul> |
| O SDK web não está presente em todas as páginas do seu site | Recomendamos colocar o SDK web em todas as páginas do seu site. |

### Os eventos não são enviados

| Motivo | solução |
| --- | --- |
| Os eventos estão sendo enviados antes de o SDK web ser carregado. Nesses casos, o console do desenvolvedor do navegador mostra o erro: `Uncaught ReferenceError: AF is not defined` | Verifique se o SDK web é carregado antes do código que envia eventos. |
| Chave do desenvolvedor web incorreta | <ul><li>O PBA exige uma chave do desenvolvedor web para saber a qual bundle atribuir os dados. Certifique-se de que a chave do desenvolvedor web correta esteja sendo usada.</li><li>Verifique se você está usando a <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#ensure-that-the-sdk-is-working">chave de desenvolvedor web correta.</Anchor></li></ul> |
| Eventos malformados | Certifique-se de que o evento esteja bem formado.<br /><br />Consulte os <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">parâmetros de evento disponíveis</Anchor> para saber mais sobre eventos bem formados. |
| SDK chamado duas vezes |  |

### SDKs e bibliotecas em conflito

Muitos SDKs web usam bibliotecas JavaScript populares. Esses SDKs também ocupam nomes no escopo global. Por exemplo, nosso SDK web ocupa **AF** como o objeto principal que habilita o SDK web.

* Se algum SDK fizer uso da biblioteca X versão 1.2 e o SDK da AppsFlyer fizer uso da biblioteca X 2.1, as duas bibliotecas podem entrar em conflito.
* Se outro SDK ou biblioteca usar **AF** (no escopo global) como nome de objeto, os dois SDKs entrarão em conflito, e um SDK poderá substituir o outro.

## SDK adicionado com o Google Tag Manager

* Implementar o SDK web com a ajuda do Google Tag Manager (GTM) pode economizar tempo.
* Você pode implementá-lo de forma independente e não precisa depender do seu desenvolvedor web para adicioná-lo ao seu site.

Se você encontrar problemas. Além dos problemas descritos na [implementação nativa do SDK](/docs/troubleshooting-the-web-sdk#sdk-adicionado-diretamente), há alguns possíveis problemas específicos do GTM.

### Chamar o SDK

| Causa | solução |
| --- | --- |
| <ul><li>Nosso guia do SDK web mostra como adicionar o SDK web usando uma tag.</li></ul><ul><li>Alguns usuários, ao criar tags para chamar eventos, configuram a tag para também chamar a tag do SDK novamente. Mas isso pode causar problemas.</li></ul>![mceclip0.png](https://files.readme.io/77be12759c5ec5a04a517ee1b99109e8952b97d1d4280b71c51fa36304f5adbf-360003756558.png) | A melhor abordagem é configurar uma tag para carregar o SDK e definir essa tag para disparar em todas as páginas. As tags que enviam eventos não devem chamar a tag do SDK novamente. |

### Prioridade da tag

O GTM permite que você <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">defina a prioridade da tag</Anchor>. Isso significa que você pode controlar quais tags serão disparadas primeiro.

| Causa | solução |
| --- | --- |
| Uma tag que carrega o SDK está definida com prioridade menor do que uma tag que envia um evento ao carregar a página. Como resultado, o SDK não é inicializado a tempo de enviar o evento. | Para a tag que carrega o SDK, sempre defina uma prioridade mais alta do que a das tags que enviam eventos ou identificam usuários. |

### Disparo de tags

No GTM, toda tag tem um acionador que determina quando essa tag deve ser disparada.

| Causa | solução |
| --- | --- |
| O acionador responsável por disparar a tag que carrega o SDK não está definido para todas as páginas. Como resultado, nem todas as visitas à página são registradas, e alguns eventos não são enviados. | A melhor abordagem é definir um acionador de <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en">visualizações de todas as páginas</Anchor> para a tag que carrega o SDK. |
| O acionador responsável por disparar as tags que enviam eventos não está configurado corretamente. Como resultado, alguns eventos não são enviados. | Determine as condições para o acionador. Exemplo:<ul><li>uma interação com elementos do DOM, como um clique em um botão</li><li>uma visita a uma página com um determinado caminho, como **/thank-you-page** ou **/confirmation-page**</li></ul> |

### Publicação de contêineres GTM

Toda alteração no GTM, como adicionar ou editar tags e acionadores, exige a publicação do contêiner GTM para que as mudanças entrem em vigor. Se você usa o SDK web pelo GTM, mas o SDK não carrega ou os eventos não são enviados, certifique-se de [publicar o contêiner do GTM](https://support.google.com/tagmanager/answer/6107163?hl=en).

<div data-zendesk-anchors="sdk-added-directly=sdk-adicionado-diretamente no-data-or-partial-data-in-the-pba-dashboard=sem-dados-ou-com-dados-parciais-no-dashboard-do-pba events-are-not-sent=os-eventos-n%C3%A3o-s%C3%A3o-enviados conflicting-sdks-and-libraries=sdks-e-bibliotecas-em-conflito sdk-added-using-google-tag-manager=sdk-adicionado-com-o-google-tag-manager calling-the-sdk=chamar-o-sdk tag-priority=prioridade-da-tag triggering-tags=disparo-de-tags publishing-gtm-containers=publica%C3%A7%C3%A3o-de-cont%C3%AAineres-gtm" />

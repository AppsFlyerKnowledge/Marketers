---
title: Páginas de Destino Multiplataforma com Smart Script
metadata:
  keywords:
    - CTV
    - Marketers
    - gaming
    - cross-platform
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2023-09-10T07:17:21Z'
  edited_at: '2026-08-18T00:22:19Z'
  id: 18440789126289
  locale: pt
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/pt/articles/18440789126289
---
> **Resumo:** Utilize uma página de destino multiplataforma com o AppsFlyer Smart Script para realizar a atribuição web-to-app. Isto é, converta utilizadores que visualizam um anúncio na web de qualquer origem de média em utilizadores de aplicações em plataformas como CTV, PC, consola ou móvel.

## Visão Geral

Com uma página de destino multiplataforma a executar o AppsFlyer Smart Script, pode realizar atribuições web-to-app. Isto significa que pode atribuir instalações, em qualquer plataforma, a anúncios exibidos na web.

O Smart Script numa página de destino multiplataforma utiliza o link de entrada (referente ao anúncio na web) para certificar-se de duas coisas: a fonte de média original e o anúncio web são atribuídos à instalação.

* Cria um link OneLink multiplataforma que envia uma impressão para a AppsFlyer.
* Cria links de atribuição direta para cada aplicação/plataforma.

## Configuração

#### ESCOPO DO TRABALHO

| **Quem está envolvido**<ul><li>**Anunciante**:<ul><li>Decide o que a [impressão multiplataforma](#create-crossplatform-impression-link) de saída e os [links de atribuição direta](#create-direct-attribution-links) devem conter com base nos <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#arguments">argumentos</Anchor> do Smart Script. Isto determina os dados de atribuição que são adicionados ao URL de saída, seja manipulando o URL de entrada ou forçando certos valores.</li><li>Garante que todas as campanhas que levam ao site tenham URLs de entrada com parâmetros que o script possa processar.</li><li><Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Testa o Smart Script</Anchor>.</li></ul></li><li>**Desenvolvedor Web**:<ul><li>Adiciona os argumentos ao script e implementa o Smart Script na página de destino.</li><li>Testa o Smart Script.</li></ul></li></ul> |
| --- |
| **Pré-requisitos**<ul><li>Uma conta no AppsFlyer com pelo menos uma aplicação.</li><li>Para o URL de impressão: Um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">modelo OneLink</Anchor> com atribuição multiplataforma ativada.</li></ul> |

<div id="create-crossplatform-impression-link" />

<Accordion title="Criar link de impressão multiplataforma">

**Para criar um link OneLink multiplataforma que envie uma impressão para a AppsFlyer**:

1. Mapeie os parâmetros do link de entrada para os parâmetros que o link de impressão deve conter (para a origem dos média, campanha, nome do anúncio, etc.).
   * Saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#arguments">argumentos</Anchor> no script que processam o URL de entrada.
   * O valor do argumento <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#arguments">OneLinkURL</Anchor> é o domínio+ID do modelo OneLink com atribuição multiplataforma ativada.
2. Informe o seu programador para inicializar os argumentos do Smart Script e chamar o método do Smart Script `generateOneLinkURL`. <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">Consulte a demonstração e as instruções para programadores</Anchor>.  
   **Nota:** O parâmetro `af_xplatform=true` é necessário para habilitar a atribuição entre plataformas.

</Accordion>

<div id="create-direct-attribution-links" />

<Accordion title="Crie links de atribuição direta">

1. Associe os parâmetros do link de entrada aos parâmetros que os links de atribuição direta de saída devem conter (fonte de mídia, campanha, nome do anúncio, etc.). Saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#arguments">argumentos</Anchor> no script que processa o URL recebido.
2. Peça ao seu programador para inicializar os argumentos do Smart Script e executar o método Smart Script para criar um link para cada plataforma/aplicação. Veja a <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">demonstração</Anchor> e as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/create-direct-click-url">instruções</Anchor> para o programador.  
   **Observação:** O desenvolvedor deve adicionar os seguintes parâmetros:  

| Parâmetro/Argumento | Considerações | Registre suas respostas (para que você ou o desenvolvedor as utilize) |
| --- | --- | --- |
| platforma | Uma string que descreve a plataforma e deve ser desta lista:<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>Android</li><li>ios</li><li>steam</li><li>quest</li><li>battlenet</li><li>nativepc</li></ul> |  |
| ativado | <ul><li>ID da aplicação</li><li>Exemplo: 123456</li></ul> |  |
| redirectURL | <ul><li>O URL para o qual o utilizador da plataforma/aplicação deverá ser redirecionado.</li><li>Exemplo: `https://store.steampowered.com/app/123456/Team_Fortress_2/`</li></ul> |  |

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H8V0RV7X8JEVEJ36TJB1X43D=vis%C3%A3o-geral setup=configura%C3%A7%C3%A3o 01H8V0RV7X0K157JTDQMJSQYKF=configura%C3%A7%C3%A3o scope-of-work=escopo-do-trabalho h_01H95PGMNWPBRHSZBPMKNJ2PS6=escopo-do-trabalho 01H8EQ4KS75Q62Z7WVNSTDXBZX=create-crossplatform-impression-link 01H8EQ4KS7C6HADNKQZYNTTFMF=create-direct-attribution-links" />

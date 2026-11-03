---
title: Segurança e performance do Smart Banners e do Smart Script
metadata:
  keywords:
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-01-30T14:54:37Z'
  edited_at: '2026-08-19T00:34:44Z'
  id: 22082177372561
  locale: pt
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/pt/articles/22082177372561
---
> **Em resumo:** Saiba como a AppsFlyer aborda proativamente suas preocupações de segurança em relação ao Smart Banners e ao Smart Script.

Neste Q&A, discutimos dúvidas comuns sobre a integração de Smart Banners e Smart Script, com foco no impacto na segurança e na velocidade do site.

## Segurança da API do Smart Banners

<div id="what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it" />

<Accordion title="Quais dados o smart banner captura quando alguém clica nele ou o visualiza?">

| agregados | Considerações |
| --- | --- |
| IP do cliente | O IP é usado para calcular a localização (país, região e estado) |
| Data/hora do evento |  |
| User-Agent |  |
| Página do site | A URL da qual se originou a chamada para o SDK web |
| Protocolo HTTP | HTTP/HTTPS |
| Cabeçalhos | Host, Content-type, Origin, Content-length, Encoding |
| Parâmetros do OneLink |  |
| Parâmetros do banner | Configurações do banner:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#dismissal-behaviour">Comportamento de dispensa</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#param-table">Parâmetros de entrada</Anchor></li><li>Parâmetros UTM</li><li>Parâmetros da AppsFlyer</li><li>parâmetros padrão</li><li>outros parâmetros</li></ul> |

</Accordion>

<div id="what-api-calls-are-needed-to-show-a-smart-banner" />

<Accordion title="Quais chamadas de API são necessárias para exibir um smart banner?">

* Uma API para buscar o SDK em uma CDN localizada em `https://websdk.appsflyersdk.com`.
* Uma API para gerar o link por trás do CTA localizado em `banner.appsflyer.com`. Essa API é acionada pelo método [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner) do SDK.
* Uma API para buscar o criativo do banner de uma CDN localizada em `creatives-cdn-appsflyer.com`.

</Accordion>

<div id="do-these-api-calls-include-an-identifier" />

<Accordion title="Essas chamadas de API incluem um identificador?">

sim, sim, A chave web exclusiva do cliente atua como identificador nas chamadas de API, permitindo recuperar os dados necessários para exibir o banner e gerar a URL do OneLink para a CTA do banner.

</Accordion>

<div id="is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key" />

<Accordion title="É possível que uma entidade mal-intencionada altere a URL ou modifique a chave web das APIs?">

Sem. Não é possível acessar e modificar o código que define a chave web usada na chamada de API do banner. Isso significa que agentes mal-intencionados não podem manipular o cálculo do banner nem a URL do OneLink gerada para o CTA do banner.

</Accordion>

## Segurança da hospedagem do script dos Smart Banners

<div id="can-clients-host-a-copy-of-the-smart-banner-script-on-their-server" />

<Accordion title="Os clientes podem hospedar uma cópia do script do Smart Banner em seu servidor?">

Os clientes não podem hospedar o script dos Smart Banners nos seus servidores. No entanto, eles podem usar o <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor> para gerar a URL do OneLink e implementar os próprios criativos de banner.

Usar o Smart Script com seus próprios banners permite criar criativos personalizados e mapear e personalizar ainda mais os links gerados, eliminando a necessidade de implementar o SDK do banner no seu site e de fazer chamadas de API externas.

</Accordion>

<div id="can-clients-host-their-own-code-and-still-use-banners" />

<Accordion title="Os clientes podem hospedar o próprio código e ainda usar banners?">

Os clientes podem desenvolver seus próprios banners, incluindo o design, o desenvolvimento e a integração no site, e usar o <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor> para gerar os links para o call-to-action (CTA) do banner.

</Accordion>

<div id="can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page" />

<Accordion title="Os Smart Banners podem ser usados sem incorporar o snippet de código na página?">

* Os clientes têm a opção de usar gerenciadores de tags para invocar as APIs do Smart Banner, como alternativa à integração direta do snippet de código. Para saber mais sobre gerenciadores de tags, clique <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-website-code-implementation-for-marketers#implementação-do-código-do-site">aqui.</Anchor>
* A execução do script em um iFrame não é suportada.

</Accordion>

<div id="how-does-appsflyer-protect-your-banners-from-postsave-tampering" />

<Accordion title="Como a AppsFlyer protege seus banners contra adulteração após o salvamento">

Ao editar e salvar um criativo de banner no editor de criativos da AppsFlyer, um invasor pode tentar interceptar a solicitação, assumir seu controle e injetar código JavaScript malicioso.

Implementamos várias medidas para garantir que os Smart Banners estejam seguros contra possíveis ataques e para impedir edições não autorizadas por usuários fora da própria conta.

* Nossa equipe de segurança executa testes e verificações para garantir que todos os nossos serviços (incluindo Smart Banners) estejam protegidos e livres de vulnerabilidades.
* Realizamos regularmente testes de invasão independentes e imparciais para garantir a proteção e a segurança da AppsFlyer.
* Internamente, validamos tags de HTML e script e sanitizamos quaisquer scripts maliciosos.

</Accordion>

<div id="do-smart-banners-use-cookies" />

<Accordion title="Os Smart Banners usam cookies?">

Por padrão, os Smart Banners não usam cookies. No entanto, oferecemos uma configuração opcional para usar cookies primários para clientes que preferem maior persistência (por exemplo, para lidar com a volatilidade do armazenamento no Safari no iOS 26).

O proprietário do site deve <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#set-storage-mode-optional">ativar esta opção</Anchor> explicitamente. Se essa opção estiver ativada, o proprietário do site também será responsável por atualizar o gerenciamento de consentimento de cookies e as divulgações de privacidade, conforme exigido pelas regulamentações aplicáveis.

</Accordion>

## Performance dos Smart Banners

<div id="does-the-smart-banner-web-sdk-impact-website-load-speed" />

<Accordion title="O SDK web do Smart Banner afeta o carregamento do site?">

Embora adicionar qualquer código extra a um site possa afetar potencialmente os tempos de carregamento, a maior parte do trabalho do smart banner é feita do lado do servidor, de forma assíncrona e sem bloquear o carregamento da página.

Além disso, usamos CDNs para agilizar o carregamento de páginas e banners.

</Accordion>

<div id="can-you-share-some-metrics-regarding-banner-speed-performance" />

<Accordion title="Vocês podem compartilhar algumas métricas sobre a performance da velocidade de carregamento do banner?">

A velocidade de carregamento do banner varia e depende de vários fatores, incluindo:

* Velocidade da internet
* Conectividade e tipo de conexão
* Performance do site, entre outros.

Esses fatores, somados ao tempo mínimo de resposta dos servidores da AppsFlyer aos navegadores, contribuem para o cálculo dos tempos de carregamento do banner.

Como as variáveis acima não estão relacionadas à AppsFlyer, não podemos especificar prazos exatos para o processo completo de ponta a ponta.

</Accordion>

<div id="how-can-i-actively-improve-the-banner-loading-time" />

<Accordion title="Como posso minimizar ativamente o tempo de carregamento do banner?">

O tempo de carregamento do banner é impactado pelo Largest Contentful Paint (LCP), que diz respeito principalmente à imagem do banner. Para melhorar a performance de carregamento do LCP, você pode::

* Escolha um modelo de banner menor.
* Reduza o tamanho das imagens do logotipo e de fundo
  * Considere substituir a imagem de fundo por uma cor sólida para reduzir os tempos de carregamento dos recursos.
  * Use uma CDN para hospedar as imagens do banner e ter tempos de carregamento mais rápidos.

* Escolha a mesma espessura de fonte em todo o banner.

</Accordion>

## Segurança e performance do Smart Script

<div id="does-smart-script-use-cookies" />

<Accordion title="O Smart Script usa cookies?">

Não, não usamos cookies na nossa solução Smart Script.

</Accordion>

<div id="does-smart-script-make-any-external-calls-to-generate-links" />

<Accordion title="O Smart Script faz chamadas externas para gerar links?">

Não, o script é executado localmente no site do cliente, portanto não depende de chamadas externas, o que torna seu uso muito seguro.

</Accordion>

<div id="is-there-a-download-time-associated-with-smart-script" />

<Accordion title="Há algum tempo de download associado ao Smart Script?">

Você pode incorporar o script diretamente ao seu site, garantindo que não haja tempo de download. O script carrega rapidamente porque não requer chamadas ao servidor.

</Accordion>

<div data-zendesk-anchors="smart-banners-api-security=seguran%C3%A7a-da-api-do-smart-banners h_01HNDDT0XHK5Y5NYTQMSXYSCZ4=seguran%C3%A7a-da-api-do-smart-banners h_01HNDDT0XHY7BZNXA2CRT1W46F=what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it h_01HNDDT0XJGFJE3XBAXTE0C2K5=what-api-calls-are-needed-to-show-a-smart-banner h_01HNDDT0XJVX8KXSZC10GTJMCS=do-these-api-calls-include-an-identifier h_01HNDDT0XJ7MGPFSZKJ7YRZ2HJ=is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key smart-banners-script-hosting-security=seguran%C3%A7a-da-hospedagem-do-script-dos-smart-banners h_01HNDDT0XJSS77BFVVT2QQV5HP=seguran%C3%A7a-da-hospedagem-do-script-dos-smart-banners h_01HNDDT0XJYW3Y0MQZWW1C1ETJ=can-clients-host-a-copy-of-the-smart-banner-script-on-their-server h_01HNDDT0XJG1SKBMA14KBGKZGD=can-clients-host-their-own-code-and-still-use-banners h_01HNDDT0XJDEGBK5WTBJ52ZVST=can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page h_01HNDDT0XJC7FT514HEGN68T68=how-does-appsflyer-protect-your-banners-from-postsave-tampering h_01HNDDT0XJR4BQPN20FNGJPARY=do-smart-banners-use-cookies smart-banner-performance=performance-dos-smart-banners h_01HNDDT0XJNJXY52BZJS9T1G72=performance-dos-smart-banners h_01HNDDT0XJ456B4DG38BMMP98W=does-the-smart-banner-web-sdk-impact-website-load-speed h_01HNDDT0XJSEXVNRT8H27EMCNS=can-you-share-some-metrics-regarding-banner-speed-performance h_01HNDDT0XJK99RH6MAJFGQ7FPX=how-can-i-actively-improve-the-banner-loading-time smart-script-security-and-performance=seguran%C3%A7a-e-performance-do-smart-script h_01HNDDT0XJSGVRA6SB2YYYAE0P=seguran%C3%A7a-e-performance-do-smart-script h_01HNDDT0XJW9B4GJ3J4RMJDG6V=does-smart-script-use-cookies h_01HNDDT0XJNZXGPZN2NDHQ34KF=does-smart-script-make-any-external-calls-to-generate-links h_01HNDDT0XJXV12C5P1CD32FZW3=is-there-a-download-time-associated-with-smart-script" />

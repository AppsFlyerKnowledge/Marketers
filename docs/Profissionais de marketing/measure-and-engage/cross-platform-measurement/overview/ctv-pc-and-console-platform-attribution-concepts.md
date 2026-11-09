---
title: Conceitos de atribuição de plataformas de CTV, PC e console
metadata:
  keywords:
    - Attribution
    - Advertisers
    - Developers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-15T11:30:45Z'
  edited_at: '2026-10-20T03:44:21Z'
  id: 4404083608849
  locale: pt
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/pt/articles/4404083608849
---
> **At a glance:** saiba como funciona a atribuição para plataformas CTV, PC e console e permita que a AppsFlyer receba dados de atribuição e de eventos para suas campanhas nesses dispositivos.

<Image align="center" alt="Diagrama da solução de atribuição cross-platform da AppsFlyer para CTV, PC e consola" src="https://files.readme.io/7fc57fd80ad86bb173bcf81581b9fe8b4625ed2a044d302a6d72194560019e81-4410336840977.png" width="471px" />

<div id="the-appsflyer-cross-platform-solution" />

## A solução multiplataforma da AppsFlyer

No atual panorama digital, os profissionais de growth enfrentam o desafio de chegar aos consumidores através de múltiplos dispositivos e plataformas. As abordagens tradicionais de mensuração não conseguem captar a jornada completa dos usuários. Assim, a mensuração multiplataforma é fundamental para que você entenda o impacto das suas atividades de marketing e tome decisões bem informadas.

A AppsFlyer oferece uma solução que complementa as ferramentas convencionais de atribuição mobile. Essa solução permite que os profissionais de growth mensurem e atribuam com precisão seus esforços de marketing quando os usuários interagem em mais de uma plataforma e dispositivo. O foco dessa solução são os canais de CTV, PC e console.

Os anunciantes podem promover um app na mesma plataforma em que o anúncio é exibido ou em plataformas diferentes. <span id="tv-screens"></span>Por exemplo, um anunciante pode exibir um anúncio para um app da Steam na plataforma da Steam. Ou então, ele pode exibir um anúncio para um app da Steam no desktop, através do Google Ads, por exemplo. As campanhas CTV envolvem especificamente anúncios exibidos em telas de TV e displays semelhantes a TVs.

Independentemente da sua estratégia de marketing, você pode usar a AppsFlyer para receber dados de atribuição e mensurações de performance de fontes (não orgânicas ou orgânicas) e campanhas que geram instalações e eventos pós-instalação em plataformas de CTV, PC e console. Use esses insights para calcular o lifetime value dos usuários (LTV) e mensurar e otimizar suas atividades de marketing. <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">Saiba mais sobre a atribuição da AppsFlyer</Anchor>

<div id="supported-platforms" />

### Plataformas compatíveis

<table><thead><tr><th rowspan="2">Platform</th><th colspan="2">Método de integração da AppsFlyer</th></tr><tr><th>S2S</th><th>SDK</th></tr></thead><tbody><tr><td>Android TV</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>tvOS (Apple TV)</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>MacOS</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Amazon Fire TV</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Chromecast</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Roku</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Vizio</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Samsung</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>LGUDID</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>PlayStation</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>RIDA</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Steam</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>PC nativo</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Meta Quest (Oculus)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Epic Games</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Nintendo Switch</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Xbox</td><td><span>✓</span></td><td><span>-</span></td></tr></tbody></table>

<div id="integrate-with-ad-networks-that-support-specified-ctv-pc-and-console-platforms" />

### Selecione as ad networks compatíveis com as plataformas de CTV/PC/Console especificadas

A lista de ad networks que exibem anúncios em plataformas de CTV, PC e console e são compatíveis com a atribuição entre plataformas (por exemplo, CTV para aplicativo móvel) pode ser encontrada no <Anchor target="_blank" href="https://hq1.appsflyer.com/partner-marketplace/explore?integrationLevels=CROSS_PLATFORM">marketplace de parceiros da AppsFlyer</Anchor>.

<div id="cross-platform-attribution-flows" />

## cross\_platform\_attribution\_1.jpg

Ao promover aplicativos em plataformas de CTV, PC e console, existem vários fluxos - desde a exibição de anúncios (impressão ou clique) até a atribuição da AppsFlyer - que se aplicam a todas as plataformas:

* Link de atribuição direta
* Onelink multiplataforma
* SRN (rede de auto-relato, também conhecida como SAN, ou rede de auto-atribuição)
* Landing page multiplataforma

Cada aplicativo, anunciante e plataforma pode ter um ou mais fluxos implementados ao mesmo tempo. Vamos explicar os diferentes tipos e quando cada um deles é usado.

<Accordion title="Link de atribuição direta">

Os links de atribuição direta são links da AppsFlyer compatíveis com o redirecionamento e a atribuição para um único aplicativo de destino em uma única plataforma por vez. Costumam ser usados para:

* Publicidade dentro de uma mesma plataforma. Ou seja, a plataforma que exibe o anúncio e a plataforma que hospeda o app é a mesma. Por exemplo, um anunciante pode exibir um anúncio para um app da Samsung TV em uma TV da Samsung. Os links de atribuição direta são compatíveis com os métodos de atribuição probabilística e determinística (quando <Anchor target="_blank" href="/marketers/pt/docs/about-device-identifiers#identificadores-de-dispositivos-ctv">um ID compatível</Anchor> é fornecido no link), em que uma instalação é associada a um clique ou impressão de um anúncio.
* Publicidade de qualquer plataforma para qualquer plataforma, com um destino/plataforma predeterminado. Por exemplo, uma landing page de desktop web exibe um anúncio com um ou mais botões, sendo que cada botão redireciona para uma plataforma de loja/marketplace específico. A atribuição é realizada por meio de modelagem probabilística.

 O diagrama abaixo ilustra o fluxo de atribuição.

<Image align="center" alt="Fluxo de atribuição CTV - Fluxo do link de atribuição direta" src="https://files.readme.io/2af32b096faa381843040314c9c183056256d03a7e2e6095e72a59bb7211727f-19374976446225.png" />

Como os links de atribuição direta são usados para um aplicativo em uma plataforma predeterminada, levando a um destino específico, eles sempre contêm o app ID e as informações da plataforma na URL.

Amostra de um link de atribuição direta: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/1234561?&af_media_source=game_media_source&af_campaign=campaign_yellow&af_campaign_id=1234&af_ad=game_ad_name&af_adset=game_adset_name&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F1176160%2FSpace_Wars%2F`

<Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links#link-de-atribuição">Aprenda a criar links de atribuição direta</Anchor>.

</Accordion>

<Accordion title="Onelink multiplataforma">

Os links multiplataforma do OneLink são compatíveis com o redirecionamento e a atribuição quando a plataforma de exibição do anúncio e a plataforma de destino são diferentes. O usuário vê um anúncio de um app mobile em uma plataforma e depois continua a jornada em outra.

Exemplos:

* CTV-to-mobile. O usuário vê o anúncio do app mobile em um dispositivo Roku. Em seguida, o usuário instala ou abre o aplicativo Android ou iOS.
* De web para desktop para console. O usuário vê o anúncio do jogo no desktop web. Depois, ele continua em uma plataforma de PC ou console, como PlayStation, Xbox ou Steam.

Os links multiplataforma do OneLink são compatíveis apenas com o método de atribuição de modelagem probabilística (que se baseia no endereço de IP). Por isso, diferentes instalações de vários usuários podem ser atribuídas à mesma impressão. O diagrama abaixo ilustra o fluxo de atribuição.

Todos os destinos/plataformas possíveis são configurados no template do OneLink. Os links multiplataforma do OneLink não contêm um app ID específico ou informações de plataformas específicas na URL. A URL inclui o ID do template onde estão configurados todos os destinos/plataformas possíveis.

Amostra de link multiplataforma do OneLink:

```
https://impressions.onelink.me/ch/AG7A?pid=game_media_source&c=game_landing_page&af_ad=game_ad_name&af_adset=game_adset_name&af_xplatform=true
```

<Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns">Saiba como configurar links multiplataforma do OneLink</Anchor>

</Accordion>

<Accordion title="SRN">

Com links de atribuição direta e links multiplataforma do OneLink, a AppsFlyer atribui instalações através dos dados contidos na URL. Por outro lado, as redes de autorrelato (SRNs), também conhecidas como redes de auto-atribuição (SANs), auto-atribuem usando o device ID quando recebem a notificação de uma instalação pela AppsFlyer.

A atribuição das SRNs é feita através de uma correspondência determinística. Quando um anunciante integra uma SRN, a atribuição funciona da seguinte maneira:

<Image align="center" alt="Fluxo de atribuição CTV - Fluxo de atribuição SRN" src="https://files.readme.io/ba0d84643aefd6a20e95c8aca9424affea8169c95ccc428ddf3d35bb8787a67c-19374961372945.png" />

Atualmente, a atribuição de SRNs não funciona para a publicidade multiplataforma. Ou seja, ela só funciona quando o touchpoint (clique ou impressão) ocorre na mesma plataforma que a instalação. Por exemplo, se uma instalação da Roku CTV for verificada com a Roku Endemic Media (a SRN da Roku), sendo que uma impressão ocorreu em um dispositivo da Roku. Se a impressão ocorrer em uma plataforma diferente, como o mobile, isso não será considerado para a atribuição.

No futuro, espera-se que a atribuição de SRNs seja compatível com a atribuição multiplataforma.

</Accordion>

<Accordion title="Landing page multiplataforma">

As landing pages multiplataformas são compatíveis com as jornadas e fluxos de marketing multiplataformas comuns. Elas costumam ser mais usadas para apps de jogos. As landing pages executam o Smart Script da AppsFlyer para realizar a atribuição web-to-app. Isso significa que elas atribuem instalações em qualquer plataforma (como CTV, PC, console e plataformas mobile) a anúncios exibidos na web.

O Smart Script usa o link de entrada (ou seja, o link no anúncio na web) para garantir que a fonte de mídia original e o anúncio sejam atribuídos à instalação:

* Cria um link OneLink multiplataforma que envia uma impressão para a AppsFlyer. Isso permite que a AppsFlyer registre uma impressão que pode ser usada posteriormente para atribuir instalações de usuários. As impressões são enviadas quando a landing page é aberta. Mesmo que os usuários saiam da landing page sem clicar em nenhum botão e, depois, baixem o aplicativo de forma autônoma, a impressão ainda será atribuída.
* Links de atribuição direta são criados para cada app/plataforma. Quando os usuários clicam nesses links, eles são direcionados para a plataforma/loja de aplicativos certa. E, posteriormente, quando eles baixam e instalam o app, a instalação é atribuída ao clique.

A landing page é compatível com os métodos de atribuição de modelagem probabilística e correspondência determinística (quando um ID é fornecido no link). Com a modelagem probabilística, é possível que várias instalações de vários usuários sejam atribuídas à mesma impressão. O diagrama abaixo ilustra o fluxo de atribuição.

<Image align="center" alt="Fluxo de atribuição CTV - Fluxo de atribuição da landing page" src="https://files.readme.io/28e4d14d14532332027e5d429ac3f95c8d4d451d94125e399cfb9ad04727b278-19374961376529.png" />

Exemplo:

1. Você tem um app de jogos que pode ser baixado e jogado nas plataformas de desktop, mobile, Epic e Steam.
2. Você promove esse app na web.
3. Um usuário vê um anúncio na web, seja através de resultados de pesquisa ou redes sociais.
4. Ele clica no anúncio e é redirecionado para uma landing page, que possui diferentes botões de download para cada plataforma.
5. A landing page executa o Smart Script da AppsFlyer, que:
6. Captura os pontos de dados essenciais do link de entrada (o link que trouxe o usuário da web para a ladning page), como query ou UTM params, ou valores predefinidos, que identificam o canal de mídia, campanha, anúncio e mais.
7. Usa esses pontos de dados para gerar uma impressão e enviá-la para a AppsFlyer.
8. Gera links de saída para cada um dos botões de download.
9. O usuário clica em um dos botões, é levado até a loja da plataforma, baixa e abre o aplicativo.
10. A instalação/primeira abertura do app é associada à impressão e atribuída ao canal de mídia que apresentou o anúncio original na web.

Informações adicionais:

* <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">Veja uma amostra de uma landing page multiplataforma</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/cross-platform-landing-pages-with-smart-script">Saiba como configurar landing pages multiplataforma com o Smart Script</Anchor>

</Accordion>

<div id="data-availability" />

## Disponibilidade de dados

Os dados das plataformas de CTV, PC e console incluem dados de instalação, bem como dados de eventos in-app que fornecem informações sobre o lifetime value (LTV) de usuários não orgânicos e orgânicos, com base em assinaturas, compras in-app e monetização de anúncios. As métricas de LTV são calculadas a partir da data de atribuição até o presente.

Os dados estão disponíveis da seguinte forma:

* Agregue dados via o Dashboard Overview.
* Dados brutos via:
  * <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-data-via-data-locker">Relatório do Data Locker</Anchor>
  * <Anchor target="_blank" href="/marketers/pt/docs/raw-data-export-page">Exportar</Anchor>
  * <Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data">Extrair API</Anchor>
* **Impressões de campanhas entre plataformas** (por exemplo, de CTV para mobile) não são exibidas em dashboards no nível de aplicativo. Uma única impressão de CTV pode gerar várias conversões mobile, o que torna impossível dividir as impressões com precisão entre aplicativos. Para acessar a contagem total de impressões, use o <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-data-via-data-locker">relatório de engajamentos cross-platform no Data Locker</Anchor>.

<div id="note" />

> 📘 **Importante!**
>
> Para plataformas com sistemas operacionais Android e iOS, a disponibilidade de <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview">dados agregados</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Relatórios de dados brutos</Anchor> é a mesma que para apps mobile.

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Janela de reatribuição | Para as plataformas de CTV, PC e console, a janela de reatribuição se baseia em um período de inatividade definido (default: 90 dias). |
| Eventos pós-reinstalação | Atribuído à primeira instalação. <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#attributed-to-the-first-install">Saiba mais</Anchor> |
| Redirecionamento | <ul><li>Reatribuição: Suportado para cross-platform-to-mobile.</li><li>Reengajamento: Compatível em qualquer plataforma que não seja Android, iOS, Windows Phone ou website. Na prática, isso significa aplicativos de CTV, PC e console.</li></ul> |
| Método de atribuição | <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#métodos-de-atribuição">Ver métodos de atribuição de plataformas de CTV, PC e console</Anchor> |
| Moeda | USD ou conforme definido nas configurações do app na AppsFlyer |
| Fuso horário | UTC |
| Dados de custo | Para apps nessas plataformas, importe dados de custo por meio do <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Cost Import</Anchor> usando o método de upload por e-mail.<br /><br />Você também pode extrair dados via API do Google, da Meta ou do TikTok para as seguintes plataformas:<ul><li>Steam</li><li>PC nativo</li><li>Smart Cast</li><li>Windows Phone</li><li>Tizen</li><li>Quest</li></ul> |
| Atualização de dados | Em My Dashboards, as métricas de instalações, reengajamentos e reatribuições para as plataformas de CTV, PC e console são fornecidas pelo nosso pipeline de dados pronto para IA (migrado entre 21 de julho e 10 de agosto de 2026). Isso significa que essas métricas para essas plataformas agora aparecem com atraso, em vez de continuamente. Veja <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#traits-and-limitations">características e limitações do My Dashboards</Anchor> para mais detalhes. |

</Accordion>

<div data-zendesk-anchors="about-ctv-attribution=a-solu%C3%A7%C3%A3o-multiplataforma-da-appsflyer 01H7ZRK7PCNZG54ZQ0804HMR38=a-solu%C3%A7%C3%A3o-multiplataforma-da-appsflyer list-of-supported-ctv-and-gaming-device-types=plataformas-compat%C3%ADveis 01H7ZRK7PCP1KWRX1A5K81F4KR=plataformas-compat%C3%ADveis list-of-specified-platforms=selecione-as-ad-networks-compat%C3%ADveis-com-as-plataformas-de-ctvpcconsole-especificadas h_01JMA8F9F6M2MZFNRXFQWJF8B8=selecione-as-ad-networks-compat%C3%ADveis-com-as-plataformas-de-ctvpcconsole-especificadas crossplatform-attribution=cross_platform_attribution_1jpg 01H8EHHJNBA8NKMX2C8RSV7P31=cross_platform_attribution_1jpg data-availability=disponibilidade-de-dados h_01H9G52NKMQG9QD9S3N537BM7N=disponibilidade-de-dados h_01M2MN6SN9SW7RGGK5R1MFW91B=importante" />

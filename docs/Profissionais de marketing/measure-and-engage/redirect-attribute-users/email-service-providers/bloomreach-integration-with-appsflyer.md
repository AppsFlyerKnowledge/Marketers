---
title: Integração do Bloomreach com AppsFlyer
metadata:
  keywords:
    - marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2026-03-29T13:30:32Z'
  edited_at: '2026-08-18T00:35:14Z'
  id: 45235709425553
  locale: pt
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/pt/articles/45235709425553
---
> **Visão geral:** Configure uma integração com o Bloomreach para habilitar o Deep linking contínuo a partir de campanhas de e-mail, mensurar o tráfego no Bloomreach e no AppsFlyer e criar experiências de usuário que impulsionam a conversão.

<Image align="center" alt="Bloomreach + AppsFlyer.png" src="https://files.readme.io/842523ac61d5f702a451b361d435e794f8dedad0f54eecffdf27f596c2cab262-45298084947473.png" width="645px" />

<div id="about-the-integration" />

## Aba de integração

O Bloomreach é uma plataforma de automação de marketing por e-mail e um provedor de serviços de e-mail (ESP) que ajuda marcas a criar experiências personalizadas em vários canais.

A integração entre AppsFlyer e Bloomreach permite Deep linking contínuo a partir de campanhas de e-mail, oferece suporte à mensuração precisa do tráfego no Bloomreach e no AppsFlyer e ajuda a criar experiências de usuário integradas que impulsionam a conversão.

<div id="set-up-the-integration" />

## Configurando o Amplitude

A configuração da integração exige ações no AppsFlyer e no Bloomreach. Para configurar a integração, siga esses passos:

<div id="step-1-in-appsflyer-create-and-configure-onelink" />

<Accordion title="Etapa 1: no AppsFlyer, crie e configure o OneLink">

Primeiro, configure o OneLink no AppsFlyer e confirme que as configurações necessárias de hospedagem e domínio estão definidas.

<div id="when-your-app-is-installed" />

#### Quando o aplicativo está instalado

Defina o comportamento de redirecionamento para usuários que já têm seu aplicativo instalado.

**Para definir o comportamento de redirecionamento:**

1. <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Crie um template OneLink</Anchor> e configure Universal Links/App Links. Esse template será usado para criar links do OneLink para suas campanhas de e-mail.
2. Se você já tiver um template do OneLink com Universal Links/App Links já configurados, você pode usá-lo.

<div id="hosting-and-ssl" />

#### Hospedagem e SSL

* Os links do OneLink são protegidos por SSL e hospedados pela AppsFlyer.
* O arquivo AASA e os arquivos App Link também são hospedados pela AppsFlyer.

Consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-esp-integration-with-appsflyer#configure-seu-aplicativo-para-garantir-o-suporte-para-deep-linking">informações e instruções adicionais.</Anchor>

<div id="app-domain-definition" />

#### Definição do domínio do aplicativo

Exemplo: no iOS, defina o domínio associado da seguinte forma:

```text
applinks:<your-onelink-subdomain>.onelink.me
```

Consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">informações e instruções adicionais.</Anchor>

</Accordion>

<div id="step-2-in-bloomreach-define-a-universal-link-domain" />

<Accordion title="Etapa 2: no Bloomreach, defina um domínio Universal Link">

Em seguida, defina um domínio Universal Link no Bloomreach para que os links possam oferecer suporte ao Deep linking e ainda sejam mensurados.

Os domínios definidos no Bloomreach não são encapsulados em um link de rastreamento de cliques da CDN quando são usados em uma campanha de e-mail, o que habilita o Deep linking.

Um parâmetro adicional é anexado automaticamente ao Universal Link original para habilitar a mensuração por meio dos SDKs web e mobile do Bloomreach.

Consulte <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/universal-link">informações adicionais e instruções.</Anchor>

<Image align="center" alt="2026-03-31_09-28-18.png" src="https://files.readme.io/4058ab59e2622f26327d9a4a62fa8afdc5965210acba9d9c5bb7a62d53a05503-45298084948753.png" width="73.36%" />

<div id="ios" />

<div id="example" />

> 📄 **Exemplo**
>
> Abaixo está um exemplo de um link Universal não encapsulado, com parâmetros de rastreamento da Bloomreach anexados:
>
> ```text
> https://engmntqa.onelink.me/LtRd?pid=ESP_Bloomreach&c=esp-campaign&is_retargeting=true&utm_source=bloomreach&utm_medium=email&utm_campaign=Test-severla-link-yossi-26-10&xnpe_cmp=.eJwzPNrmPEXT6ZZjVKC-flJ-SqV-SWJSTqp-CYRdpF-SQrxItHEslJuSWaafmMWTsWTZufIm9r61XAs2AABFBChI.jF6UMukHXiw5lw
> ```

</Accordion>

<div id="step-3-in-bloomreach-implement-mobile-and-web-sdks" />

<Accordion title="Etapa 3: Na Bloomreach, implemente os SDKs mobile e web">

Por fim, implemente os SDKs relevantes da Bloomreach para garantir que a mensuração de cliques funcione corretamente em aplicativos mobile e na web.

#### /docs/ctv-pc-and-console-platform-attribution-concepts

Implemente o <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">SDK mobile</Anchor> da Bloomreach para iOS e garanta que a mensuração do link Universal esteja configurada corretamente. O SDK da Bloomreach oferece suporte à mensuração de links Universal para capturar interações do usuário iniciadas por campanhas de e-mail.

Consulte informações adicionais e instruções sobre <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/ios-sdk-universal-links#track-universal-links">links Universal</Anchor> e <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">SDKs mobile.</Anchor>

<div id="android" />

#### com o Android

Implemente o <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">SDK mobile</Anchor> da Bloomreach para Android e configure os App Links de forma semelhante aos links Universal do iOS para garantir a atribuição de clique e a consistência da mensuração.

Consulte informações adicionais e instruções sobre <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/android-sdk-app-links#track-android-app-links">Android App Links</Anchor> e <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">SDKs mobile.</Anchor>

#### Web

Implemente o <Anchor target="_blank" href="https://Mobile%20SDKs">SDK web JavaScript</Anchor> da Bloomreach para garantir que os cliques em links Universal também sejam mensurados no seu site. A mensuração de cliques em links Universal no seu site funcionará sem necessidade de configuração adicional.

Consulte <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/js-sdk">informações adicionais e instruções.</Anchor>

</Accordion>

<div id="step-4-test-the-integration-by-sending-a-test-email" />

<Accordion title="Etapa 4: Teste a integração">

Depois de concluir a configuração, envie um e-mail de teste para validar a integração e confirmar que o Deep linking e a mensuração de cliques funcionam conforme o esperado.

1. **Insira o link OneLink em um e-mail de teste e envie-o para si mesmo.**

   Usando o editor de e-mail do seu ESP, adicione o link OneLink a um e-mail de teste e envie-o para si mesmo. Garanta que o domínio configurado na Etapa 2 seja usado e que o link não seja encapsulado.
2. **Valide a estrutura do link.**

   Abra o e-mail de teste e confirme que o OneLink não é encapsulado pela Bloomreach. Além disso, verifique se o parâmetro `xnpe_cmp` foi anexado ao link.
3. **Verifique a mensuração de cliques e o comportamento do OneLink.**

   No seu dispositivo mobile, abra o e-mail e clique no link. Confirme que:

   * Se o Aplicativo estiver instalado, ele é aberto e faz Deep linking para o conteúdo in-app esperado.
   * O clique aparece no dashboard de análises da Bloomreach.

Quando todas as validações forem concluídas, a configuração da integração estará concluída.

<div id="note" />

> 📘 **Atenção**
>
> Se os cliques não aparecerem na plataforma da Bloomreach, entre em contato com a equipe de suporte da Bloomreach.

</Accordion>

<div id="important-notes" />

> 📘 **Observações importantes**
>
> * A AppsFlyer hospeda e protege todos os arquivos relevantes do OneLink e de associação, incluindo os arquivos AASA e App Link.
> * Os SDKs da Bloomreach para iOS, Android e JavaScript devem ser implementados corretamente para que a mensuração de links funcione.
> * Os Universal Links e App Links devem permanecer sem encapsulamento, com os parâmetros da Bloomreach anexados automaticamente.
> * Esta integração permite a atribuição precisa de cliques de e-mail para aplicativo e de e-mail para web, bem como a mensuração do engajamento entre canais.

<div data-zendesk-anchors="about-the-integration=aba-de-integra%C3%A7%C3%A3o h_01KMWVJR5AQRY8YRAD6ZV6H1VV=aba-de-integra%C3%A7%C3%A3o set-up-the-integration=configurando-o-amplitude h_01KMWVJR5ACS7Q1GKP1GGGBRYK=configurando-o-amplitude h_01KMWVJR5ABTK766X4G0B9J92E=step-1-in-appsflyer-create-and-configure-onelink when-your-app-is-installed=quando-o-aplicativo-est%C3%A1-instalado h_01KMWVJR5AY8WRV4Y6GTWHDE5D=quando-o-aplicativo-est%C3%A1-instalado hosting-and-ssl=hospedagem-e-ssl h_01KMWVJR5A40099PC91YW2QR1D=hospedagem-e-ssl app-domain-definition=defini%C3%A7%C3%A3o-do-dom%C3%ADnio-do-aplicativo h_01KMWVJR5A7JV0FHC5W1EP9502=defini%C3%A7%C3%A3o-do-dom%C3%ADnio-do-aplicativo h_01KMWVJR5A57Y1ZPAYBC5321DX=step-2-in-bloomreach-define-a-universal-link-domain h_01KMWVJR5BER86B8YV3H60PGF6=exemplo h_01KMWVJR5B6K6EG49VJM7JSEK2=step-3-in-bloomreach-implement-mobile-and-web-sdks ios=exemplo h_01KMWVJR5B3505FSJSXRC9NQ4A=exemplo android=com-o-android h_01KMWVJR5BE703X877C40DZ5MX=com-o-android h_01KMWVJR5BVTXS8W2WGTYEGP0D=web h_01KMWVJR5BPA0N2YTK2983DHMT=step-4-test-the-integration-by-sending-a-test-email h_01KMWVJR5B6PHSEK7NA5W8ZGNF=aten%C3%A7%C3%A3o h_01KN1TCDE27DNPJJ8HRHZ4FPA0=observa%C3%A7%C3%B5es-importantes" />

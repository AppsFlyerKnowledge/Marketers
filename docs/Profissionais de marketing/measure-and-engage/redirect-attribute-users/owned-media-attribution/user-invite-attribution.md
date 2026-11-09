---
title: Atribuição de convites de usuário
metadata:
  keywords:
    - OneLink
    - Advertisers
    - User invite
    - Developers
    - Marketers
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2017-08-30T12:13:45Z'
  edited_at: '2026-08-19T00:34:28Z'
  id: 115004480866
  locale: pt
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/pt/articles/115004480866
---
> **Resumo:** atribua e registre novas instalações quando os usuários existentes convidarem outras pessoas para usar seus aplicativos.

<Image align="center" alt="Invite_Attribution_new.png" src="https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png" />

<div id="about-user-invite-attribution" />

## Sobre a atribuição de convites de usuários

Quando falamos sobre convites de usuários, nos referimos ao momento em que usuários do seu aplicativo enviam links de compartilhamento que redirecionam outras pessoas (por exemplo, amigos) para fazer o download/abrir seu app.

Assim, a atribuição de convites de usuários é a atribuição de novas instalações ou interações de aplicativos correlacionadas aos usuários que enviaram esses convites.

A atribuição de convites de usuários permite que você:

* Analise o custo e o ROI dos convites de usuários. Convites de usuários usam espaço de publicidade dentro do seu app, que poderia ser usado para gerar receita de anúncios. Avalie se os convites de usuários trazem um ROI melhor.
* Registrar informações sobre os usuários que mais convidam outras pessoas. Usuários que convidam outras pessoas para o seu aplicativo são usuários engajados de alto valor, que você pode querer redirecionar ou incentivar.

Você também pode usar os dados dos links para:

* Personalizar a nova experiência do usuário. Por exemplo, fazer com que o aplicativo abra uma página de um conteúdo específico ou, em vez de uma mensagem geral, personalizar uma mensagem de boas-vindas, como "Olá, João! Sua amiga Maria quer desafiá-lo em uma partida. Jogue agora!"
* Recompensar os usuários que enviam convites de usuários. [Saiba mais](/docs/user-invite-attribution#reward-referrers-for-user-invite-installs).

Os links de convites de usuários que os usuários compartilham com outras pessoas são, na verdade, links personalizados do OneLink (URLs curtos) gerados pelo SDK da AppsFlyer, que está integrado ao seu aplicativo Os links de convites de usuários que os usuários compartilham com outras pessoas são, na verdade, links personalizados do OneLink (URLs curtos) gerados pelo SDK da AppsFlyer, que está integrado ao seu aplicativo As configurações do seu OneLink garantem que os usuários que recebem um convite sejam redirecionados para o lugar certo — ou seja, para a loja de aplicativos correta, para o seu aplicativo ou para uma página específica do seu aplicativo por meio de um deep link/deferred deep link. Os links de convites de usuários que os usuários compartilham com outras pessoas são, na verdade, links personalizados do OneLink (URLs curtos) gerados pelo SDK da AppsFlyer, que está integrado ao seu aplicativo As configurações do seu OneLink garantem que os usuários que recebem um convite sejam redirecionados para o lugar certo — ou seja, para a loja de aplicativos correta, para o seu aplicativo ou para uma página específica do seu aplicativo por meio de um deep link/deferred deep link. <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">Saiba mais sobre o OneLink.</Anchor>

<div id="flow" />

### Fluxo

O fluxo funciona da seguinte maneira:

1. O usuário A faz uma ação de dentro do aplicativo para compartilhar o aplicativo com um amigo (O usuário A tem o aplicativo instalado e está conectado). (O usuário A tem o aplicativo instalado e está conectado).
2. A ação gera um link com um parâmetro que identifica o usuário A nele.
3. O usuário A envia o link para o usuário B por e-mail/WhatsApp/SMS etc.
4. Se o usuário B:
   * Tem o aplicativo instalado, o aplicativo é aberto. O usuário B pode ser enviado para uma página específica no aplicativo por meio de um deep link, e/ou ser recompensado.
   * Não tem aplicativo instalado, ele é enviado para a loja de aplicativos correta. O usuário B pode ser enviado por meio de um deferred deep link para uma página específica no aplicativo após a primeira abertura do aplicativo e/ou o usuário A pode ser recompensado.
   * Realiza um evento in-app, o usuário A pode ser recompensado.

<div id="viewing-data" />

## Visualização de dados

Os dados de convites do usuário estão disponíveis nos dashboards e relatórios da AppsFlyer. Nos dashboards da AppsFlyer, você pode filtrar a atribuição dos convites de usuários:

* **Fonte de mídia**: convites de aplicativo.
* **Canal**: conforme estabelecido pelo profissional de marketing.
* **Campanha**: conforme estabelecido pelo profissional de marketing.

Nos relatórios, a fonte da mídia (parâmetro `pid`) é enviada pelo SDK com o valor padrão `af_app_invites`.

<div id="procedures" />

## Procedimentos

**Para criar links de convites de usuários**:

1. Crie um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor>.
2. Decida os valores dos parâmetros do canal e da campanha. Veja os [parâmetros](/docs/user-invite-attribution#parameters).
3. Escolha quais casos de uso você deseja aplicar nesses links. Casos de uso comuns incluem:
   * Fazer o deep linking de novos usuários para uma página específica no aplicativo.
   * Registrar quais usuários fizeram a indicação.
   * Recompensar novos usuários.
4. Entre em contato com seus desenvolvedores de Android e iOS para definir quais parâmetros serão responsáveis por permitir o funcionamento do uso que você deseja para os links. Veja os [parâmetros](/docs/user-invite-attribution#parameters) disponíveis.
5. Peça ao desenvolvedor que ele <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">implemente o deep linking</Anchor> (usando o comportamento desejado dos parâmetros no código).
6. Peça ao desenvolvedor para que ele implemente convites de usuário nas seguintes plataformas:

   <Tabs>
   <Tab title="Android">

   Veja [convite de usuário no Android](https://dev.appsflyer.com/hc/docs/dl_android_user_invite) no Dev Hub.

   </Tab>

   <Tab title="iOS">

   Veja [convite de usuário no iOS](https://dev.appsflyer.com/hc/docs/dl_ios_user_invite) no Dev Hub.

   </Tab>

   <Tab title="Unity">

   Veja [convite de usuário](https://dev.appsflyer.com/hc/docs/userinvite) no Dev Hub.

   </Tab>
   </Tabs>

<div id="parameters" />

<Accordion title="Parâmetros">

<div id="parametersvalues-provided-to-the-developer-to-implement-in-the-sdk" />

#### Parâmetros/valores fornecidos ao desenvolvedor para implementar no SDK

<table><thead><tr><th>Parâmetro/valor</th><th>Observações</th><th>Registre o valor/uso que o desenvolvedor deve implementar</th></tr></thead><tbody><tr><td>ID do modelo do OneLink</td><td>O ID do template do OneLink com as configurações básicas nas quais todos os links de convite do usuário serão baseados. Por exemplo: H5hv</td><td> </td></tr><tr><td>Canal</td><td>O nome do canal. Isso ajuda você a classificar e visualizar atribuições por canal na interface do usuário da AppsFlyer.</td><td> </td></tr><tr><td>Campanha</td><td>O nome da campanha. Isso ajuda você a classificar e visualizar atribuições por campanha na interface do usuário da AppsFlyer.</td><td> </td></tr><tr><td> <span>is_retargeting=true</span><br/> </td><td>É adicionado caso a sua campanha faça o retargeting de usuários existentes.</td><td> </td></tr><tr><td>deep_link_value</td><td>Um parâmetro a ser usado no dispositivo do usuário indicado para fornecer uma experiência específica. Normalmente, ele é usado para nomear a página específica para a qual os usuários serão direcionados. Por exemplo, se seu aplicativo vende frutas, você pode direcionar os usuários para a página da maçã.</td><td> </td></tr><tr><td>deep_link_sub1</td><td rowspan="10">Um parâmetro a ser usado no dispositivo do usuário indicado para fornecer uma experiência específica. Como deep_link_value é normalmente usado para enviar usuários para uma página específica, esse parâmetro pode ser usado para qualquer outra funcionalidade desejada. Por exemplo, para adicionar uma recompensa ou desconto, ou registrar o usuário que fez a indicação. </td><td> </td></tr><tr><td>deep_link_sub2</td><td> </td></tr><tr><td>deep_link_sub3</td><td> </td></tr><tr><td>deep_link_sub4</td><td> </td></tr><tr><td>deep_link_sub5</td><td> </td></tr><tr><td>deep_link_sub6</td><td> </td></tr><tr><td>deep_link_sub7</td><td> </td></tr><tr><td>deep_link_sub8</td><td> </td></tr><tr><td>deep_link_sub9</td><td> </td></tr><tr><td>deep_link_sub10</td><td> </td></tr><tr><td>[Opcional] pid</td><td><p>Por padrão, os links gerados incluem a fonte de mídia (parâmetro<code>pid</code>) com o valor <code>af_app_invites</code>. </p><p>Para alterar o valor, seu desenvolvedor precisa adicionar um parâmetro personalizado chamado <code>pid</code> com o valor desejado. <strong>Atenção:</strong> para Android, isso só funciona para o SDK V6.4.2+.</p></td><td> </td></tr><tr><td>Nome de marca</td><td>O nome do branded domain. Isso ajuda você a classificar e visualizar atribuições por domínio de marca na IU da AppsFlyer.</td><td> </td></tr></tbody></table>

</Accordion>

<div id="example" />

<Accordion title="Exemplo">

Marcos, o profissional de marketing, tem um aplicativo que vende frutas. Ele quer criar um deep link que vincula os usuários a uma página de frutas específica, com a opção de comprar uma quantidade específica de frutas.

Ele quer que esse link possa ser enviado por meio de um convite de usuário para recompensar os usuários que enviarem esse convite sempre que o convite gerar uma nova instalação do aplicativo e compra de frutas.

Para que tudo isso funcione, Marcos envia a seu desenvolvedor a seguinte lista de parâmetros e valores a serem usados na implementação de links de convite do usuário:

| Parâmetro | Valor | Observações |
| --- | --- | --- |
| deep\_link\_value | fruit\_name | Para deep links que usam o método UDL da AppsFlyer. |
| deep\_link\_sub1 | promo\_code | Para deep links que usam o método UDL da AppsFlyer. |
| deep\_link\_sub2 | referrer\_id | Para criar links por meio do SDK. |
| param\_1 | referrer\_id | Para o evento in-app que registra cada compra. |
| Canal | mobile\_share | Para realizar a atribuição e visualizar os dados na AppsFlyer. |
| Campanha | summer\_sale | Para realizar a atribuição e visualizar os dados na AppsFlyer. |

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="record-user-invites-as-inapp-events" />

<Accordion title="Registre convites de usuários como eventos in-app">

Registrar um evento in-app depois que um usuário envia um convite de usuário ajuda a identificar quais usuários enviam convites a outras pessoas, além de indicar quais canais de mídia são responsáveis por trazer esses usuários que enviam convites.

**Para registrar um evento in-app de convite de usuário**:

* Envie um <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#invite-af_invite">evento af\_invite.</Anchor> O desenvolvedor precisa implementar seguindo as instruções do nosso dev hub.

**Atenção:** você pode adicionar mais parâmetros que deseja associar ao evento. Escolha parâmetros que forneçam contexto adicional ao evento e enriqueçam os dados. <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">Saiba mais</Anchor>.

</Accordion>

<div id="reward-referrers-for-user-invite-installs" />

<Accordion title="Reward referrers por instalações geradas por convites de usuários">

**Para recompensar os usuários por enviar um convite de usuário que resulta em uma instalação**:

1. Certifique-se de que o referrer ID (ou seja, do usuário que envia o convite) seja o valor de um dos [parâmetros deep\_link\_sub1-10](/docs/user-invite-attribution#parameters).
2. Peça ao desenvolvedor que ele <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">implemente o deep linking</Anchor> (usando o comportamento do parâmetro escolhido no código).
3. Peça aos desenvolvedores do seu backend para que eles trabalhem com os desenvolvedores para acessar os referrer IDs (que podem ser encontrados nos relatórios da AppsFlyer) e recompensar esses usuários.

Exemplo:

1. O usuário A convida o usuário B para instalar o seu aplicativo.
2. Quando o usuário B abre o app, o aplicativo obtém o referrer ID do usuário A.
3. Seu backend recupera o referrer ID a partir dos relatórios da AppsFlyer.
4. No backend, adicione o referrer ID do usuário A a uma lista de usuários a serem recompensados.
5. Quando o usuário A abrir o aplicativo, verifique se o referrer ID está na lista de usuários a serem recompensados e, se estiver, recompense-o.

</Accordion>

<div id="reward-referrers-for-referred-user-actions" />

<Accordion title="Recompense referrers pelas ações do usuário que recebeu o convite">

**Para recompensar referrers por um convite de usuário que resulta em um evento in-app específico**:

1. <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#configurando-eventos-in-app">Crie o evento in-app</Anchor> que você deseja recompensar.
2. Peça ao seu desenvolvedor que ele adicione um parâmetro (por exemplo, param\_1) ao evento com o valor do referrer ID. **Atenção:** o referrer ID é originalmente registrado na instalação do aplicativo usando o [parâmetro](/docs/user-invite-attribution#parameters) selecionado (deep\_link\_sub1-10).
3. Peça aos desenvolvedores do seu backend para que eles trabalhem com os desenvolvedores para acessar os referrer IDs (que podem ser encontrados nos relatórios da AppsFlyer) e recompensar esses usuários.

Exemplo:

1. O usuário A convida o usuário B a realizar uma ação no seu aplicativo.
2. Quando o usuário B executa a ação, um evento in-app que contém o referrer ID do usuário A é registrado.
3. Seu backend recupera o referrer ID a partir dos relatórios da AppsFlyer.
4. No backend, adicione o referrer ID do usuário A a uma lista de usuários a serem recompensados.
5. Quando o usuário A abrir o aplicativo, verifique se o referrer ID está na lista de usuários a serem recompensados e, se estiver, recompense-o.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e Limitações">

| Caraterística | Descrição |
| --- | --- |
| Versão do SDK | Deve ter versão 4.8.0+ do SDK da AppsFlyer e a versão 4.17.0+ do SDK Unity. |
| <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Landing page em rede social</Anchor> | Links gerados a partir de convites de usuários não podem implementar landing pages de redes sociais. |
| Time to live (TTL) | O tempo padrão de vida (TTL) para URLs curtas OneLink criadas para um convite de usuário via SDK é de 60 dias. Ele é estendido por mais 60 dias a cada vez que o link é clicado. |
| Limite de payload | O valor do payload dos parâmetros do link não deve exceder 3.000 caracteres. |
| Preços | Incluído nos planos de assinatura OneLink Standalone e Atribuição.<br /><br />**Observação:** Se o seu pacote terminar ou for cancelado, o SDK de convite do usuário deixará de gerar novos links de convite, e todos os fluxos de convite relacionados serão afetados. Os links de convite existentes continuarão a funcionar. |
| iOS 14+ | A atribuição de convites de usuário não usa IDFA, por isso o iOS 14 não afeta esse recurso. |
| URL ID | O ID da URL (ou shortlink ID) pode ser editado para destacar a oferta da sua campanha. Por exemplo: [https://myapp.onelink.me/abc123/ma](https://myapp.onelink.me/abc123/ma)çãs. O ID da URL não deve exceder 50 caracteres e pode ser uma combinação de letras e números. Por padrão, são 8 caracteres.<br /><br />**Atenção:** Você só pode editar o URL ID se o ID atual ainda não estiver em uso. |

</Accordion>

<div data-zendesk-anchors="about-user-invite-attribution=sobre-a-atribui%C3%A7%C3%A3o-de-convites-de-usu%C3%A1rios h_01H98E1CZ2AG8AW2H77SPPHFGR=sobre-a-atribui%C3%A7%C3%A3o-de-convites-de-usu%C3%A1rios flow=fluxo h_01H98E1CZ234MRBWDEYGZFCDRE=fluxo viewing-data=visualiza%C3%A7%C3%A3o-de-dados h_01H98E1CZ23FEAS8JJC7FFTFXD=visualiza%C3%A7%C3%A3o-de-dados procedures=procedimentos h_01H98E1CZ2VBCG0RREERW8FNJE=procedimentos h_01H98E1CZ2WE6DJW717C6AJWXD=parameters parametersvalues-provided-to-the-developer-to-implement-in-the-sdk=par%C3%A2metrosvalores-fornecidos-ao-desenvolvedor-para-implementar-no-sdk h_01H98E1CZ2CANBK1T55DD103JB=par%C3%A2metrosvalores-fornecidos-ao-desenvolvedor-para-implementar-no-sdk h_01H98E1CZ2NXCCYEV12JC6EMFG=example additional-information=informa%C3%A7%C3%B5es-adicionais h_01H98E1CZ28T2SJ3YNY8TNCAZY=informa%C3%A7%C3%B5es-adicionais h_01H98E1CZ2172W6845K099F814=record-user-invites-as-inapp-events h_01H98E1CZ316WWYK55XTN4C8JE=reward-referrers-for-user-invite-installs h_01H98E1CZ330FXG06A4MVQ56PW=reward-referrers-for-referred-user-actions h_01H98E1CZ3SPASZDF5CCY3T3B3=traits-and-limitations" />

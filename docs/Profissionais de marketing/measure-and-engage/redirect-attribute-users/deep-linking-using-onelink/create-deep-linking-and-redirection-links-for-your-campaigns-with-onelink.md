---
title: Crie um link do OneLink para as suas campanhas
metadata:
  keywords:
    - Marketers
    - onelink
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2016-05-22T10:03:37Z'
  edited_at: '2026-11-03T13:22:20Z'
  id: 208874366
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/208874366
---
> **Resumo:** **crie links do OneLink** que oferecem aos usuários exatamente a experiência que você quer que eles tenham. Os usuários que clicam no link são redirecionados para a loja de aplicativos, web URL ou para o aplicativo correto, conforme necessário.

## Links e experiências do OneLink

<Embed title="Crie um link do OneLink para as suas campanhas" typeOfEmbed="youtube" url="https://www.youtube.com/embed/KZBrxGEjVUE" providerUrl="https://www.youtube.com" />

Seus clientes interagem com a sua marca em diversos touchpoints online e offline. Independentemente de onde seus usuários venham, você pode criar um link que proporcione a experiência ideal para eles, desde o clique até a instalação do aplicativo, do deep linking ao deferred deep linking.

Os passos necessários para configurar um link estão descritos na próxima seção, mas, basicamente, eles incluem o seguinte:

* Seleção de uma experiência do usuário
* Configurações gerais
* Configurações específicas da experiência
* Configurações de deep linking e redirecionamentos
* Configurações de parâmetros adicionais

## Crie um link do OneLink

| **Quem está envolvido**<ul><li>Apenas um profissional de marketing é necessário para criar links do OneLink com uma experiência que redireciona os usuários para lojas de aplicativos, web URLs ou, após a configuração do template para a abertura do aplicativo com Android App Links e iOS Universal Links, para a página inicial do app.</li><li>Para acrescentar a funcionalidade de deep linking e deferred deep linking aos links, tanto um profissional de marketing como os desenvolvedores do Android/iOS são necessários.</li></ul> |
| --- |
| **Pré-requisitos**<ul><li>Uma conta da AppsFlyer com pelo menos um aplicativo.</li><li>Um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">template do OneLink</Anchor> como base para os seus links.</li><li>Para a atribuição: <Anchor target="_blank" href="/marketers/pt/docs/integrate-the-appsflyer-sdk">O SDK da AppsFlyer já instalado</Anchor> em cada um dos seus aplicativos mobile.<ul><li>Se o SDK ainda não estiver instalado nos seus aplicativos, ainda será possível criar um link de redirecionamento que funcione, mas não será possível mensurar instalações em seu dashboard, deep link ou deferred deep link.</li></ul></li></ul> |
| **Tempo necessário**<br /><br />30 minutos para a maioria dos links, mas aproximadamente 3 horas para links que exigem a funcionalidade de deep linking ou deferred deep linking. |
| **Resultado**<ul><li>Um link que envia os usuários para a loja de aplicativos correta, para a página web ou para o aplicativo em seu dispositivo, oferecendo precisamente a experiência que você deseja que eles tenham.</li></ul> |

> 👍 **Tip**
>
> **Crie links OneLink a partir da sua ferramenta de IA**
>
> Você também pode criar links OneLink descrevendo-os em linguagem simples em uma ferramenta de IA conectada ao <Anchor target="_blank" href="/marketers/pt/docs/beta-appsflyer-mcp">MCP da AppsFlyer</Anchor><Anchor target="_blank" href="/marketers/pt/docs/beta-appsflyer-mcp">.</Anchor> Por exemplo: "Crie um link para nossa newsletter de Black Friday por e-mail que abra a página da promoção no aplicativo." A IA mapeia sua solicitação para os parâmetros corretos, mostra os detalhes do link e cria o link somente depois da sua aprovação. Os links são criados em um modelo do OneLink existente. <Anchor target="_blank" href="/marketers/pt/docs/beta-appsflyer-mcp#onelink-management">Saiba mais</Anchor>

**Para criar um link do OneLink com uma experiência de usuário específica:**

1. **Na AppsFlyer, no menu lateral, selecione** **engajamento** > gerenciar o OneLink.
2. **Selecione o** template do OneLink para adicionar um link personalizado.
3. Clique em **Adicionar link**.
4. Selecione a [experiência](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#experiences) que você deseja criar para seus usuários:
5. Selecione um canal de mídia ou insira um canal de mídia personalizado. Esse é o canal de mídia para o qual os dados serão exibidos na AppsFlyer. O canal de mídia é incluído em seu link como o valor do parâmetro `pid`.

   > 📘 **Nota**
   >
   > A AppsFlyer bloqueia links de atribuição que usam nomes reservados às <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">SRNs</Anchor> Essa restrição não se aplica a ASRNs. Essa restrição não se aplica a ASRNs.

6. Clique em **Próximo**.
7. Complete as [Configurações gerais](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings).
8. Clique em **Próximo**.
9. [Opcional] Complete os procedimentos relevantes para a experiência do usuário que você está criando:

   

| Experiência | Opções de procedimento |
| --- | --- |
| <ul><li>Social-to-app</li><li>Text-to-app</li><li>Referral-to-app</li><li>Link personalizado</li></ul> | <ul><li>[Pré-visualização nas redes sociais](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Landing page social](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li></ul> |
| Email-to-app | Se você estiver usando um ESP, siga as <Anchor target="_blank" href="/marketers/pt/docs/email-service-provider-esp-integration-guide">instruções de integração ESP</Anchor>. |
| App-to-app | Você pode criar links dinâmicos que funcionam através de diferentes aplicativos via <Anchor target="_blank" href="/marketers/pt/docs/cross-promotion-attribution-for-marketers">promoção cruzada</Anchor>. |
| Referral-to-app | <ul><li>[Pré-visualização nas redes sociais](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[Landing page social](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li><li>Você pode criar links de referral-to-app dinâmicos através do SDK em seu aplicativo via <Anchor target="_blank" href="/marketers/pt/docs/user-invite-attribution">integração de convites do usuário</Anchor>.</li></ul> |

10. Clique em **Próximo**.
11. [Opcional] Em **Deep linking e redirecionamento**, complete a configuração de [deep linking/deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking). Pule esta seção se este link não se destina a deep linking.
12. [Opcional] Em **Deep linking e redirecionamento**, altere as [configurações de redirecionamento](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection). Pule essa seção se as configurações de redirecionamento do template do OneLink estiverem corretas.
13. Clique em **Próximo**.
14. Em **Parâmetros adicionais**, [adicione parâmetros predefinidos ou personalizados](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#additional-parameters) ao seu link para uma análise mais granular. <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre os parâmetros de atribuição</Anchor>
15. Clique em **Gerar link**.
16. Certifique-se de que a sua <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">redirect allowlist de domínio</Anchor> está atualizada com todos os domínios para os quais você deseja redirecionar os usuários.

<div id="experiences" />

<Accordion title="Experiências">

Você pode criar links para as seguintes experiências:

* Social-to-app: engaje com seus usuários nas redes sociais e envie-os das suas publicações nas redes sociais para seu aplicativo.
* App-to-app: envie usuários para seu aplicativo através de anúncios que eles veem em outros aplicativos.
* QR-to-app: use QR codes para impulsionar instalações, fazendo com que os usuários escaneiem um QR code em pontos importantes durante a experiência offline. Você também pode colocar QR codes em seu site para desktop ou em anúncios de TV e CTV para levar os usuários ao seu aplicativo.
* Email-to-app: use provedores de serviços de e-mail (ESPs) para engajar os usuários por e-mail e enviá-los da caixa de entrada para o seu aplicativo.
* Text-to-app: crie links para as suas campanhas de SMS e mensagens e engaje seus usuários por meio de mensagens de texto.
* Referral-to-app: crie links que permitam que usuários ou influenciadores convidem outras pessoas para seu aplicativo ou compartilhem um conteúdo específico no aplicativo como, por exemplo, um artigo.
* Link personalizado: para jornadas que não se encaixam em uma das experiências mencionadas acima, você pode criar um link personalizado do OneLink. Assim, independentemente de onde venham os seus usuários, seja via desktop ou celular, online ou offline, mídia própria ou paga, você pode usar o OneLink para enviá-los rapidamente para o destino certo.

</Accordion>

<div id="general-settings" />

<Accordion title="Configurações gerais">

As configurações gerais são uma parte do processo de criação de um OneLink que se aplica a todas as experiências.

**Para completar as configurações gerais**:

1. [Opcional] Mude o nome do canal de mídia.
2. [Opcional] Mude o nome da campanha.
3. [Opcional] Ative o **Retargeting** se você planeja usar esse link para segmentar usuários existentes.

   Isso permite que você veja os reengajamentos realizados pelos usuários clicando em seu link personalizado.

   Os usuários existentes que clicam em links sem redirecionamento (UA) também iniciam o aplicativo e têm a mesma experiência de usuário. No entanto, seus reengajamentos são registrados como sessões regulares, o que significa que é impossível mensurar o sucesso da campanha de mídia própria.

   > 🚧 **Importante!**
   >
   > Para que o retargeting funcione, você também precisa ativar o retargeting para o aplicativo.

4. [Opcional] Ative **Ignorar usuários ativos para retargeting** e selecione a janela de inatividade.  
   Isto adiciona o parâmetro af\_inactivity\_window=[número de dias] ao seu link, e todos os usuários ativos durante o período são ignorados para retargeting.
5. Defina a janela de reengajamento para determinar o período após o reengajamento, onde os eventos in-app do usuário são atribuídos ao canal de mídia de retargeting.
   * Pode definir o valor em dias (1-90), horas (até 23) ou mesmo vitalício.
   * A janela de reengajamento é adicionada ao link no parâmetro af\_reengagement\_window.
6. [Opcional] Na subseção **Link branding**:
   * Selecione um domínio diferente que seja a cara da sua marca. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data#revenue-ltv">Saiba mais</Anchor>
   * <span id="url-id"></span>Edite o URL ID para destacar a oferta da campanha. O URL ID deve ter no máximo 50 caracteres e pode ser uma combinação de letras e números. Por padrão, são 8 caracteres.

#### Ativar o retargeting para o aplicativo

Se o retargeting nunca tiver sido ativado para o aplicativo, você precisará fazê-lo apenas uma vez. <Anchor target="_blank" href="/marketers/pt/docs/app-settings#configurações-de-atribuição">Saiba mais</Anchor>

**Para definir o retargeting no nível do aplicativo:**

1. Na AppsFlyer, no menu lateral, selecione **Configurações**> **Configurações do aplicativo**.
2. Na seção **Atribuição** ative Atribuição de **reengajamento.**
3. Clique em **salvar configurações**.

</Accordion>

<div id="social-media-preview-og-tags" />

<Accordion title="Pré-visualização de redes sociais - OG tags">

Quando um link é compartilhado, as tags de gráfico aberto (OG) são usadas para gerar uma pré-visualização com um título, uma descrição e uma imagem.

Essas tags OG podem ser automaticamente retiradas da URL da web ou da loja de aplicativos para a qual você está redirecionando. No entanto, às vezes, esse método de pré-visualização falha. Portanto, recomendamos definir suas visualizações de mídia social no OneLink, usando a interface do usuário do OneLink ou, para links não criados na interface do usuário do OneLink, adicionando parâmetros de tag OG ao seu link.

**Para criar sua própria visualização das redes sociais na interface do usuário do OneLink:**

1. **Em seu editor de links personalizados OneLink, acesse** Compartilhar nas redes sociais.
2. Na seção **Prévia de rede social** , selecione **Prévia padrão (do site/loja)** para usar as tags OG do URL de destino ou **Prévia personalizada (imagem e tags)** para definir a sua própria.
3. Se você selecionou **Prévia personalizada (imagem e tags)**, insira:
   * Título
   * Descrição
   * URL da imagem
4. [Opcional] Revise o campo **Favicon do modelo**.
   * Isso mostra o favicon configurado nas <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#h_favicon">configurações do modelo</Anchor> do OneLink. Ele é exibido automaticamente nas prévias de links em plataformas compatíveis.
   * Para mudar o favicon, acesse as <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#h_favicon">configurações do modelo</Anchor>.
   * Se nenhum favicon for exibido, é porque ainda não há nenhum configurado no modelo. Você ainda pode usar a prévia personalizada sem favicon.

Para adicionar parâmetros da OG tag ao seu link (se ela não tiver sido criada na interface do usuário do OneLink):

* Adicione os seguintes parâmetros necessários:
  * af\_og\_title (até 40 caracteres)
  * af\_og\_description (até 300 caracteres)
  * af\_og\_image

> 📘 **Nota**
>
> * Você pode adicionar os parâmetros da OG tag ao seu link fora da IU da AppsFlyer.
> * Se você adicionar OG tags separadas para o X (antigo Twitter), elas substituirão a visualização normal da AppsFlyer.

</Accordion>

<div id="social-app-landing-page" />

<Accordion title="Landing page nas redes sociais">

> 🚧 **Importante!**
>
> Os Universal Links do iOS agora são aceitos no Meta Ads.
>
> * Como o Meta agora <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-faq#are-ios-universal-links-and-android-app-links-supported-in-meta-ads">aceita Universal Links</Anchor>, uma landing page social não é mais necessária para anúncios pagos no Meta que oferecem suporte aos Universal Links.
> * Uma landing page social é necessária para publicações próprias (anúncios não pagos).

Os aplicativos de redes sociais podem interromper a experiência dos usuários existentes usando Universal Links. Isso pode ser resolvido da seguinte maneira:

* [**Recomendado**] Criar uma landing page social.  
  Ao criar uma landing page social, recomendamos que você tenha um esquema URI configurado.**Observação:** O X (antigo Twitter) não oferece suporte a esquemas de URI para iOS. Uma landing page de aplicativo social com links universais deve ser usada para evitar problemas ao iniciar o aplicativo.
* [Alternativa] <Anchor target="_blank" href="/marketers/pt/docs/onelink-troubleshooting-and-faq#deep-linking-forçado">Forçar a abertura do aplicativo</Anchor> usando o parâmetro `af_force_deeplink=true`.  
  **Observação**: esse parâmetro é ativado automaticamente para Kakaotalk, Naver, Naver-Blog, Chrome, Weibo e X (antigo Twitter).

Ao usar uma landing page social, os usuários que clicam em anúncios em aplicativos de redes sociais são redirecionados para uma landing page gerada pela AppsFlyer. A partir daí, eles podem ser direcionados via deep linking ou seguir para a instalação do aplicativo.

A AppsFlyer oferece uma variedade de templates de landing pages de aplicativos de redes sociais. As posições dos elementos nos templates são fixas, mas os próprios elementos são personalizáveis, incluindo a imagem ou cor de fundo, títulos, textos, imagens, botões, tags e muito mais.

A landing page pode ser usada nos seguintes aplicativos de redes sociais:

* Instagram
* Facebook/Facebook Messenger (**observação:** para o Facebook e o Facebook Messenger, se o esquema URI e a landing pgae social estiverem configurados, a landing page do aplicativo social não será exibida.
* LinkedIn
* Pinterest para iOS
* Snapchat
* X (antigo Twitter)
* WeChat

**Experiência do usuário**

Quando o usuário engaja com o botão CTA na landing page:

* **Se o aplicativo estiver instalado**: o usuário que clica iniciará o aplicativo.
* **Se o aplicativo NÃO estiver instalado**: o usuário será levado para a app store correspondente. Após a instalação, é possível fazer deferred deep linking do usuário (explicado em [deep linking e deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)).

> 📘 **Observação**
>
> A landing page social é compatível apenas com URLs curtas do OneLink.

#### **Para usar a landing page social:**

1. Configure a landing page conforme descrito na seção a seguir.
2. Registre a URL**curta** gerada pelo OneLink.  
   A landing page social não funciona com URLs longas do OneLink.
3. Publique a URL curta do OneLink no aplicativo social.

A atribuição é determinada com base nas configurações de atribuição.

#### **Para configurar a landing page de aplicativos sociais:**

1. Na configuração do link personalizado, acesse a seção de **Social-to-app**.
2. Na seção da **landing page social**, clique em **Criar landing page social**.  
   Uma janela é aberta para que você escolha um template.  
   [![](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)
3. Para escolher um template de landing page, passe o mouse sobre o template selecionado e clique em **Criar**. **Dica**: passe o mouse sobre o ícone 🛈 de um template para ver em que casos ele deve ser usado. Clustered Poster e ShowAndTell são recomendados para o Instagram.
4. Personalize todos os elementos no criativo da landing page. Para fazer isso, selecione os elementos por nome ou clique em cada um na imagem de pré-visualização.    
   **Dica**: salve seus textos caso você substitua o template do criativo.
5. Substitua todas as imagens do template pelas suas próprias imagens.  
   1. Insira URLs de imagem, incluindo a extensão, por exemplo, `https://example.com/image.png`.
   2. Use um dos seguintes tipos de arquivo: jpeg, jpg, png.   
      **Observação**: o formato webp não é compatível.
   3. As recomendações para as imagens são:

| Tipo de imagem do template | Tamanho máximo do arquivo de imagem | Proporção da imagem |
| --- | --- | --- |
| Coleção | 300 KB | 16:9 (horizontal) |
| <ul><li>Trapeze</li><li>Carrossel</li><li>ShowAndTell</li></ul> | 300 KB | 1:1 |
| <ul><li>Flyer</li><li>Poster</li><li>Blurry Poster</li><li>Clustered Poster</li></ul> | 300 KB | 9:16 (vertical) |

   4. Se uma ou mais imagens não forem uma URL exata, um erro será exibido e você não poderá revisar o criativo.  
      [![](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)
6. Para revisar o criativo, clique em **Revisar**.  
   Se forem necessárias alterações, clique em **Voltar ao editor**.  
   [![](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)
7. Para salvar sua landing page, clique em **Concluído**.  
   **Importante**: Os criativos novos/atualizados da landing page só se aplicam após a criação/atualização do link personalizado.
8. [Opcional] Para editar sua landing page, clique em **Editar landing page social**.

</Accordion>

<div id="deep-linking-and-deferred-deep-linking" />

<Accordion title="Deep linking e deferred deep linking">

Deep linking é quando você redireciona os usuários existentes do seu aplicativo e os envia diretamente para uma experiência específica (por exemplo, uma página específica) dentro do seu aplicativo, sem que o usuário seja direcionado primeiro para a loja de aplicativos ou para a página inicial do aplicativo. Esses usuários são atribuídos usando a atribuição de retargeting.

Usar deferred deep linking significa que você proporciona aos novos usuários uma experiência de deep linking semelhante a dos usuários existentes. Mas seu fluxo de usuários é que primeiro, novos usuários são enviados para a loja de aplicativos e depois de baixar e lançar o aplicativo, eles são enviados para a experiência ou página específica.

> 📘 **Observação:**
>
> a configuração de deep linking e deferred deep linking requer a ação dos seus desenvolvedores Android e iOS.

**Para configurar o deep linking e deferred deep linking para direcionar os usuários a uma experiência específica no aplicativo:**

1. Entre em contato com seus desenvolvedores iOS e Android para planejar o **deep\_link\_value** para definir em seus links.
   * O **deep\_link\_value** é o nome do valor para o conteúdo específico no aplicativo para o qual os usuários serão direcionados. Os desenvolvedores implementam o comportamento desejado do deep\_link\_value no código.
   * Os desenvolvedores implementam o comportamento desejado no código. Compartilhe o guia para que eles entendam o fluxo técnico e vejam exemplos:
     * Para o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">deep linking E deferred deep linking</Anchor> de usuários novos ou existentes, com ou sem o seu app.  
       **Considerações sobre UDL:**
       * Necessita o SDK V6.1 ou versão posterior.
       * A janela de lookback de clique pode durar até 15 minutos.
     * **Observação**: clientes que já usam o OneLink para deep linking podem usar os métodos legados para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_gcd_legacy">iOS</Anchor>, ao invés de UDL.

       > 📄 **Dicas**
       >
       > O **deep\_link\_value** pode ser baseado em um SKU de produto, ID de post de mídia social, caminho de URL ou qualquer outro valor.
       >
       > Você deve trabalhar com seus desenvolvedores para criar o melhor sistema de longo prazo para o **deep\_link\_value** e quaisquer outros parâmetros ou valores. Isso reduzirá a necessidade de atualizações adicionais do aplicativo. Converse com seu desenvolvedor sobre o uso de valores dinâmicos para gerar vários deep links diferentes que direcionam para diferentes conteúdos dentro do aplicativo, **sem precisar alterar o código do aplicativo toda vez**.
       >
       > Por exemplo, o **deep\_link\_value** de um tipo de fruta foi escolhido e os desenvolvedores utilizaram valores dinâmicos. Isso significa que você pode inserir qualquer fruta sem a necessidade de mais trabalho da sua equipe de dev.
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=apples``...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=bananas``...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=peaches``...`

2. Após receber a confirmação dos desenvolvedores de que o aplicativo se comporta de acordo com os parâmetros e valores selecionados, na seção **Deep linking e redirecionamento** da página de configuração do link, insira o **valor de Deep Link** de acordo com o que você combinou com os desenvolvedores.
3. [Opcional] Se seu deep link exigir mais de uma experiência in-app (por exemplo, você quer direcionar os usuários para um produto e oferecer um desconto separadamente), você pode **adicionar um valor de deep link** (que usa o parâmetro deep\_link\_sub1) ao payload de dados do deep link. Você pode adicionar mais parâmetros de deep link (deep\_link\_sub2-10) na seção **Parâmetros adicionais.**
   1. Entre em contato com seus desenvolvedores iOS e Android para planejar os valores.
   2. Os desenvolvedores implementam o comportamento desejado no código. Compartilhe os guias do OneLink com seus desenvolvedores para entender o fluxo técnico e ver exemplos.

      <Tabs>
      <Tab title="Android">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_overview">Instruções para desenvolvedores do Android</Anchor>

      </Tab>

      <Tab title="iOS">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_overview">Instruções para desenvolvedores do iOS</Anchor>

      </Tab>
      </Tabs>

   3. Em **Parâmetros adicionais**, adicione parâmetros personalizados **deep\_link\_sub2-10** e outros valores conforme necessário, de acordo com o que você combinou com os desenvolvedores.

> 📘 **Observação:**
>
> Uma vez que parâmetros e valores dinâmicos são implementados pelos desenvolvedores, o profissional de marketing pode usar a API do OneLink para gerar automaticamente milhares de links personalizados. <Anchor target="_blank" href="/marketers/pt/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">Saiba mais</Anchor>

</Accordion>

<div id="redirection" />

<Accordion title="Redirecionamento">

Para enviar novos usuários para uma landing page, em vez de para a loja de aplicativos:

1. Na seção **Deep linking e redirecionamento** da página de configuração do link, quando o aplicativo não estiver instalado, selecione o envio dos usuários para uma URL diferente.  
   As URLs personalizadas do Android e do iOS redirecionam novos usuários para a página inicial especificada.   
   **Atenção!** Se o template do OneLink já tiver um valor definido para uma URL personalizada, essas URLs de links personalizados a substituirão.
2. Você também pode enviar novos usuários para <Anchor target="_blank" href="/marketers/pt/docs/redirect-users-to-custom-app-store-product-pages">páginas personalizadas de produtos da loja</Anchor>.

</Accordion>

<div id="additional-parameters" />

<Accordion title="Parâmetros adicionais">

É possível que você deseje incluir parâmetros adicionais em seu link, como campanha, nome do conjunto de anúncios, nome do anúncio, canal, parâmetros personalizados ou de 1 a 5 <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">parâmetros de inscrição</Anchor>. Isso permite uma análise mais granular dos seus esforços de marketing. Saiba mais sobre os <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">parâmetros adicionais de atribuição</Anchor>.

Você também pode incluir parâmetros adicionais de deep linking (deep\_link\_sub2-10).

**Para adicionar parâmetros**:

1. Na seção **Parâmetros adicionais** da configuração do link, clique em **Adicionar parâmetro**.
2. Selecione o parâmetro a ser adicionado ou digite um parâmetro personalizado.

</Accordion>

<div id="testing" />

<Accordion title="Testes">

Você pode testar se seu link funciona para redirecionar:

* Novos usuários sem seu aplicativo instalado
* Usuários existentes com seu aplicativo instalado

#### Novos usuários sem seu aplicativo instalado

**Pré-requisitos**: um <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">dispositivo de teste registrado</Anchor> sem o aplicativo.

Para testar seu link:

1. Na AppsFlyer, no menu lateral, selecione **engajamento** > **gerenciar o OneLink**.
2. Passe o mouse sobre o ícone **Ações** do link que deseja testar e clique em **Obter URL**.
3. Envie a URL curta ou longa para o seu telefone. Você tem duas opções:
   * Escaneie o QR code com a câmera do telefone ou aplicativo de QR scan.
   * Envie o link por e-mail ou WhatsApp e abra-o em seu telefone.  
     **Atenção:** não cole esse link nas notas do iOS ou diretamente em um navegador mobile. Muitas vezes, o sistema operacional mobile não abrirá o aplicativo nesse contexto.
4. Clique no link em seu dispositivo mobile.  
   Dependendo da sua plataforma, o direcionamento será para a loja de aplicativos ou para a landing page.  
   **Observação**: é necessário um clique real em um dispositivo mobile. Os redirecionamentos Javascript ou 301/302 não podem acionar Universal Links e App Links. Mesmo redirecionamentos básicos falham com esses métodos em alguns navegadores.
5. Faça o download e inicie o aplicativo.
   * O aplicativo deve abrir em sua tela inicial.
   * Se você implementou deferred deep linking, o aplicativo deve abrir o conteúdo especificado nos parâmetros do link.
6. No **dashboard de Visão geral** da AppsFlyer, procure por uma nova instalação.  
   Procure um novo clique e instalação de acordo com o canal de mídia (por exemplo, teste) e o nome da campanha que você colocou na URL.

O link não está se comportando como esperado? Confira <Anchor target="_blank" href="/marketers/pt/docs/onelink-troubleshooting-and-faq">o FAQ e o guia de solução de problemas do OneLink.</Anchor>

#### Usuários existentes com seu aplicativo instalado

**Pré-requisitos**: Um dispositivo  Android e/ou iOS com o aplicativo instalado. Certifique-se de que seja a fonte e a versão do aplicativo em que o desenvolvedor fez alterações (e implementou esquemas de links universais, links de aplicativo e/ou URI).

**Para testar seu link:**

1. Na AppsFlyer, no menu lateral, selecione **engajamento** > **gerenciar o OneLink**.
2. Clique no template **do OneLink selecionado**.
3. Na lista, selecione o Link personalizado.
4. Passe o mouse sobre o ícone **Ações** do link que deseja testar e clique em **Obter URL**.
5. Envie a URL curta ou longa para o seu telefone. Você tem duas opções:
   * Escaneie o QR code com a câmera do telefone ou aplicativo de QR scan.
   * Envie o link por e-mail ou WhatsApp e abra-o em seu telefone.  
     **Atenção:** não cole esse link nas notas do iOS ou diretamente em um navegador mobile. Muitas vezes, o sistema operacional mobile não abrirá o aplicativo nesse contexto.
6. Clique no link em seu dispositivo mobile.
   * O aplicativo deve abrir em sua tela inicial.
   * Se você implementou um deep link, o aplicativo deve abrir para o conteúdo que você especificou nos parâmetros do link.
7. Acesse o dashboard de **Visão Geral** da AppsFlyer (**Tipo de visualização: retargeting**).  
   Acesse o dashboard de **Visão Geral** da AppsFlyer (**Tipo de visualização: Retargeting**)  
   Procure por um novo clique/reengajamento (abertura do aplicativo) sob a fonte de mídia do seu link (por exemplo, teste) e o nome da campanha que você colocou no URL.

O link não está se comportando como esperado? Confira <Anchor target="_blank" href="/marketers/pt/docs/onelink-troubleshooting-and-faq">o FAQ e o guia de solução de problemas do OneLink.</Anchor>

</Accordion>

## Procedimentos adicionais

<div id="create-a-custom-impression-url" />

<Accordion title="Criar uma URL de impressão personalizada">

Links de impressão personalizados permitem que você:

* Mensure as <Anchor target="_blank" href="/marketers/pt/docs/about-conversion-rates#estágios-de-funil-de-marketing-e-taxas-de-conversão-1">taxas de conversão de impressões em cliques</Anchor> dos anúncios que você exibe.
* Receba atribuição para impressões.

**Pré-requisitos:** Uma URL longa e funcional do OneLink. URLs curtas não são compatíveis.

**Quem está envolvido:**

Profissional de marketing e desenvolvedor

**Para criar URLs de impressão para mensurar apenas impressões:**

1. Na AppsFlyer, no menu lateral, selecione **engajamento** > **gerenciar o OneLink**.
2. Passe o mouse sobre o menu de opções do link que você gostaria de testar e clique em **obter URL**.
3. Copie a URL longa do OneLink para edição.  
   Exemplo: `https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
4. Substitua o subdomínio (ou todo o Branded Domain, se você estiver usando um) por “impressions”.    
   Exemplo: se você estiver usando um OneLink com marca como `https://app.alltrails.com/Waim?` altere-o para um link de impressões `https://impressions.onelink.me/Waim?`.
5. Copie a URL de impressão e envie-a para o seu desenvolvedor.
6. Peça ao seu desenvolvedor para implementar a URL de impressão na lógica do site.

Agora você tem uma URL de impressão, que pode ser usada para contar impressões nas páginas do seu site, mas **não pode atribuir novas instalações.** Para atribuição de exibição, siga as próximas etapas.

**Para usar URLs de impressão para atribuição:**

1. Prepare a URL de impressão conforme descrito nas etapas anteriores.
2. Certifique-se de que a <Anchor target="_blank" href="/marketers/pt/docs/measure-view-through-engagements">atribuição de exibição esteja ativada</Anchor>.
3. [opcional] Se você deseja alterar o valor da <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback</Anchor> de exibição padrão de 1 dia, adicione o parâmetro `af_viewthrough_lookback` com o novo valor. Por exemplo: `af_viewthrough_lookback=1d`.
4. Copie a URL de impressão e envie-a para o seu desenvolvedor.
5. Peça ao seu desenvolvedor para implementar a URL de impressão na lógica do site.

Exemplo de URL de impressão completa:

```http
https://impressions.onelink.me/j7rN?pid=email&c=Spring&af_viewthrough_lookback=1d
```

</Accordion>

<div id="deep-linking-post-event" />

<Accordion title="Deep linking pós-evento">

Você pode querer enviar os usuários a atividades ou páginas específicas somente após um evento, por exemplo:

* Ao fazer login
* Ao visualizar uma tela inicial
* Ao concordar com os termos e condições
* E mais

**Para fazer o deep linking de usuários após um evento**:

Peça aos seus desenvolvedores que sigam as instruções para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_dl_post_event">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_dl_post_event">iOS</Anchor>.

</Accordion>

<div id="deferred-deep-linking-with-ios-private-relay" />

<Accordion title="Deferred deep linking com o iOS Private Relay">

Com o lançamento do iOS 15, a Apple oferece aos usuários do iCloud+ um recurso chamado <Anchor target="_blank" href="https://www.macworld.com/article/348965/icloud-plus-private-relay-safari-vpn-ip-address-encryption-privacy.html">Private Relay</Anchor>, que oferece a opção de criptografar o tráfego de navegação na web e ocultar sua localização exata, endereço IP e o conteúdo do tráfego de navegação. Se os usuários optarem pelo Private Relay, isso poderá interferir na atribuição e no deferred deep linking. Ou seja, quando um novo usuário sem o aplicativo acessa a App Store, instala e inicia o aplicativo, o Private Relay pode impedir que ele seja enviado para uma página específica dentro do app.

Para garantir que o Deferred deep linking (DDL) continue funcionando como esperado, você precisa implementar uma das seguintes soluções da AppsFlyer:

* **[Recomendado] Solução baseada em App Clip**: crie um App Clip que forneça dados de atribuição do usuário e direcione os usuários para uma experiência personalizada de App Clip, semelhante à que você quer que o DDL alcance. O App Clip também pode incluir um fluxo para direcionar os usuários do seu App Clip para o aplicativo completo.
* **Solução baseada na área de transferência**: crie uma landing page na web que copie os dados de deferred deep linking da URL e redirecione o usuário para o aplicativo. **Observação**: essa solução não ajuda com a atribuição.

<div id="app-clipbased-solution" />

<Accordion title="Solução baseada em App Clips">

Essa solução combina URLs curtas do OneLink com a tecnologia de App Clips disponível no iOS, permitindo que você envie usuários para fluxos específicos em seu produto sem a necessidade de instalar o aplicativo completo. A URL curta do OneLink fornece dados de atribuição do usuário e direciona os usuários para uma experiência personalizada do App Clip semelhante à que você deseja que o DDL alcance. O App Clip também pode incluir um fluxo para direcionar os usuários para o aplicativo completo. **Observação**: se os usuários reinstalarem o aplicativo a partir da solução baseada no App Clip, isso poderá ser relatado na AppsFlyer como uma instalação orgânica. 

#### **Fluxo**

O fluxo da solução DDL baseada no App Clip é o seguinte:

1. O anunciante cria um App Clip e o adiciona a um template do OneLink para usuários que ativaram o Private Relay.
2. O usuário toca na URL do OneLink.
3. O manipulador da web da AppsFlyer verifica se:
   * O dispositivo está usando iOS 15+
   * O navegador é Safari
   * O usuário ativou o Private Relay.
4. Assim que a AppsFlyer confirmar os itens acima, o usuário será solicitado a clicar em **Reproduzir App Clip** ou **Exibir no Safari**.
   * Se o usuário clicar em **Reproduzir App Clip**, um card do App Clip será exibido para o usuário.
   * Se o usuário clicar em Exibir no Safari, uma landing page será aberta, solicitando que ele abra o App Clip.
5. O usuário abre o App Clip.
6. O App Clip é aberto e fornece ao usuário a experiência criada pelo profissional de marketing mobile e desenvolvedor do aplicativo.
7. Se o App Clip incluir um fluxo para direcionar os usuários para o aplicativo completo, os usuários serão enviados para a App Store para baixar o aplicativo completo. Na inicialização do aplicativo, eles têm a experiência do usuário definida pelo desenvolvedor.

**Pré-requisitos:** AppsFlyer SDK V6.4.0+

**Para configurar a solução DDL baseada em App Clip**:

1. Peça ao desenvolvedor que siga as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#app-clip-based-solution">instruções de soluções baseadas em App Clip</Anchor> e crie um App Clip que ofereça a experiência desejada. e crie um Clipe de App que forneça a experiência de usuário desejada. Isso também pode incluir um fluxo para direcionar os usuários do seu App Clip para o aplicativo completo.
2. Crie ou edite um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">template do OneLink</Anchor> com <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">Universal Links</Anchor> e [deferred deep linking](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking).
3. No template do OneLink, ative **Exibir App Clip se o usuário ativou o Private Relay**. Não ative essa opção a menos que você tenha um App Clip.  
   **Observação**: ao fazer alterações em um template do OneLink com Universal Links, como adicionar (ou remover) o recurso de App Clip, podem ser necessárias várias horas para que o arquivo AASA seja atualizado. Assim, os links que você cria com base no template podem não ter sua funcionalidade atualizada imediatamente.
4. Crie um link personalizado com base no template do OneLink:
5. No App Store Connect, vá para a seção **Experiência do App Clip**, vá até **URLs do aplicativo** e insira a URL do template do OneLink (domínio + ID do template). Por exemplo:`yourbrand.onelink.me/GrbZ`) ou uma URL curta de link personalizado específico do OneLink.  
   **Observação**: se você inserir um link personalizado do OneLink, a solução baseada em App Clips funcionará apenas para usuários que clicarem nesse determinado link; outros links criados com base no template do OneLink não funcionarão.

</Accordion>

<div id="clipboardbased-solution" />

<Accordion title="Solução baseada em área de transferência">

#### **Fluxo**

O fluxo da solução DDL baseada na área de transferência é o seguinte:

1. O anunciante cria um deferred deep link que contém o parâmetro `af_cp_lp=true`.
2. O usuário clica no deferred deep link.
3. A AppsFlyer verifica se:
   * O dispositivo está usando iOS 15+
   * O navegador é Safari
   * O usuário ativou o Private Relay.
   * O link contém o parâmetro `af_cp_lp=true`.
4. Depois que a AppsFlyer confirmar o item acima, a landing page da web é carregada, contendo o ícone do aplicativo, a imagem e um CTA para baixar o aplicativo na App Store. O usuário também vê uma mensagem que explica o processo: a URL é copiada para garantir a melhor experiência do usuário, que o enviará para a página específica no aplicativo.  
   ![ios_15_ip_masking__1_.png](https://files.readme.io/c130314c98ebd42f50feaafd752c0cea954f42c5bfd99a6dbd94daf9e48c2ff4-30151216595345.png)
5. O usuário toca em **Baixar o aplicativo**.
6. O usuário é enviado para a App Store para instalar o aplicativo. Em seguida, na primeira inicialização, ele é enviado para a página específica do aplicativo.

#### **Requisitos**

A solução copiar/colar DDL da lading page requer:

* Que o usuário esteja navegando na web no Safari.
* O deferred deep link deve incluir o parâmetro `af_cp_lp=true`.
* SDK para iOS V6+ da AppsFlyer.
* Seu desenvolvedor de aplicativos iOS deve implementar um código que cola os dados do deferred deep link na URL da área de transferência. Isso não faz parte do SDK da AppsFlyer.
* O usuário final deve selecionar a caixa de seleção (padrão). Se essa opção não estiver ativa, a URL não será copiada e o deferred deep link não funcionará.

#### **Configuração**

**Para configurar a solução DDL baseada na área de transferência**:

1. Diga ao desenvolvedor do iOS para:
   1. Seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#clipboard-based-solution">instruções do dev hub</Anchor> e integrar o código necessário no SDK da AppsFlyer.
   2. Implementar o código que cola o deferred deep link na URL da área de transferência. Isso não faz parte do SDK da AppsFlyer.
2. Adicione o parâmetro `af_cp_lp=true` aos seus links.   
   Você pode fazer isso adicionando um parâmetro personalizado na interface de links personalizados do OneLink ou simplesmente anexar o parâmetro a qualquer um dos seus links.

</Accordion>

</Accordion>

## Informações adicionais

<div id="examples" />

<Accordion title="Exemplos">

**Exemplo básico**

Mark é o profissional de marketing de um serviço de delivery chamado "Feed Me". Mark direciona seus números de telefone da base de usuários para baixar os novos aplicativos móveis iOS e Android do Feed Me. Ele planeja uma campanhas por SMS. No entanto, Mark não sabe quais usuários têm dispositivos Android ou iOS. Ele também não sabe se eles têm ou não o aplicativo instalado.

Para resolver isso, Mark envia aos usuários um SMS contendo uma URL curta com tecnologia OneLink. Quando os usuários receberem o SMS e clicarem no link:

* Se eles ainda não têm o aplicativo, ele os direciona automaticamente para a loja de aplicativos ou para a página de destino apropriada, onde é fácil instalar o aplicativo.
* Se eles já têm o aplicativo instalado, o aplicativo é aberto.

As novas instalações e reengajamentos são atribuídas à campanha SMS, permitindo a Mark verificar o sucesso da campanha por SMS na AppsFlyer. 

**Exemplo de deep linking**

O SMS do Mark (do exemplo anterior) teve um leve sucesso em conseguir que os usuários fizessem o download e abrissem o aplicativo. No entanto, poucos usuários que clicaram no link e abriram o aplicativo converteram para fazer um pedido.

Mark decide aumentar a conversão oferecendo pêssegos, maçãs ou abacates gratuitos a cada compra. Para isso, Mark cria uma experiência rápida e fácil de deep linking para os usuários existentes. Ele envia um e-mail detalhado para sua base de usuários, enfatizando os benefícios dessas frutas. 

Para cada fruta mencionada no e-mail, Mark inclui um link com um valor de deep link baseado no OneLink, configurado (com a ajuda de seus desenvolvedores) para:

Para resolver isso, Mark envia aos usuários um SMS contendo uma URL curta com tecnologia OneLink. Quando os usuários receberem o SMS e clicarem no link:

* Se eles já tiverem o aplicativo instalado, são levados diretamente para a página de frutas relevante.
* Se eles ainda não têm o aplicativo, são direcionados para a loja de aplicativos ou página de destino apropriada, com base no dispositivo deles. Então, uma vez que eles baixam e abrem o aplicativo, são levados diretamente para a página de frutas.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| <span id="onelink-characters"></span>Caracteres do OneLink | <ul><li>O comprimento total do URL não deve exceder 2.000 caracteres</li><li>Nome do link e canal de mídia: não deve exceder 150 caracteres</li><li>A ID de URL curta não deve exceder 50 caracteres</li><li>Veja as <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#special-characters">características e limitações</Anchor> adicionais dos parâmetros de redirecionamento.</li></ul> |
| <span id="maximum-links"></span>Máximo de links | O número máximo de links do OneLink que você pode criar na AppsFlyer é de 120.000 por conta. |
| <span id="posting-onelink-urls-in-web-pages"></span>Publicando URLs do OneLink em páginas da web | Usar `target="_blank"` na tag href HTML não resulta em redirecionamento para o Google Play ou a App Store. Se a URL do OneLink for colocada dentro de uma tag html **a** com o atributo **target="\_blank"**, uma página em branco será aberta no Chrome no Android e iOS. Isso afeta a funcionalidade do OneLink. Certifique-se de que a tag **a** não inclui o atributo de direcionamento. |
| <span id="agencies"></span>Agências | As agências não podem usar templates ou links do OneLink. Eles são apenas para canais de mídia personalizados/próprios. |
| <span id="ad-networks"></span>Redes de anúncios | As agências não podem usar templates ou links do OneLink. Eles são apenas para canais de mídia personalizados/próprios. |
| <span id="social-media-preview-image"></span>Imagem de pré-visualização na rede social | <ul><li>Se o tipo de imagem não for compatível com a plataforma de rede social, ela não será exibida.</li><li>Para a WhatsApp, a imagem não pode exceder 300 KB.</li></ul> |
| <span id="desktop"></span>Desktop | Quando você configura a URL ou template do OneLink para redirecionar os usuários de desktop para uma URL diferente, a web URL é adicionada ao link no parâmetro `af_web_dp`. Se o link contiver `af_web_dp`, a AppsFlyer não registrará um clique quando ele ocorrer no desktop |
| <span id="af_enc_data"></span>af\_enc\_data | Não compatível com URLs de impressão. |
| <span id="android-social-apps-webview-deep-linking-redirection"></span>Aplicativos de redes sociais para Android WebView | Devido a mudanças recentes feitas em vários apps sociais do Android, alguns fluxos de deep linking e de redirecionamento da loja na visualização do navegador interno (WebView) quebraram.<br /><br />**App Links do Android:**<br /><br />Atualmente, os App Links não funcionam quando recebem um clique dentro do navegador in-app no Facebook. Esquemas URI seguem funcionando normalmente.<br /><br />**Redirecionamento para a loja**<br /><br />Para acomodar essas mudanças e reativar o redirecionamento para a loja, tivemos que introduzir uma interação adicional do usuário para os seguintes apps:<ul><li>Versões do Facebook de v420 em diante</li><li>Instagram</li><li>Facebook Messenger</li><li>Snapchat</li></ul>O novo fluxo do usuário exige que os usuários cliquem em um botão adicional da landing page para acionar o redirecionamento para a Google Play Store e outras lojas externas.<br /><br />Esse botão é adicionado automaticamente e, portanto, não exige nenhuma ação sua.<br /><br />**Atenção:**<ul><li>As versões à anteriores v420, incluindo a v420, continuam a funcionar como antes, sem precisar de uma interação adicional do usuário.</li><li>Os App Links do Facebook (usando o esquema URI) usados em postagens do Facebook seguem funcionando como antes, sem precisar de uma interação adicional do usuário.</li><li>Os App Links no chat do Instagram seguem funcionando como antes, sem precisar de uma interação adicional do usuário.</li><li>No fluxo de deep linking, quando o aplicativo não está instalado, um pop-up de erro é exibido. Essa mensagem não afeta o fluxo do usuário - ele ainda é redirecionado para a loja conforme o planejado.</li></ul> |
| <span id="onelink-link-previews-sometimes-fail-to-display-correctly-on-facebook-and-linkedin"></span>Pré-visualizações de links do OneLink | **Descrição**  <br />Às vezes, as pré-visualizações de links do OneLink não são exibidas corretamente no Facebook e no LinkedIn. O problema surge quando o site de destino não reconhece a user-agent string `AppsFlyerBot-Previewer/1.0` na solicitação de pré-visualização como proveniente de um robô (ou rastreador). Nesses casos, o site não responde com o conteúdo de pré-visualização apropriado com a tag OG.<br /><br />**Solução**  <br />Você pode configurar sua landing page para tratar páginas com a user-agent header string `AppsFlyerBot-Previewer/1.0` como provenientes de um robô, <Anchor target="_blank" href="https://moz.com/learn/seo/robotstxt">atualizando o arquivo robot.txt do seu site</Anchor>.<br /><br />O robô de prévia também verifica os parâmetros de redirecionamento de cada link em relação à sua lista de permissões de redirecionamento. Quando um parâmetro aponta para um domínio que não está na lista, o robô ignora a URL, então a prévia permanece em branco ou genérica. Verifique se todos os domínios de landing page que você espera pré-visualizar foram adicionados à sua lista de permissões de redirecionamento. |
| <span id="deep-linking-is-not-supported-on-android-naver-blog-app"></span>Aplicativo Android Naver Blog | O deep linking não é compatível com o aplicativo Android Naver Blog. Os usuários serão direcionados para o Google Play ou para o redirecionamento da web, conforme definido no link. |
| <span id="chrome-browser-on-ios"></span>Navegador Chrome no iOS | Devido a uma alteração no Chrome, sempre que um usuário clica em um link de esquema URI no Chrome no iOS, um pop-up é exibido, solicitando que o usuário confirme a abertura do app ou o redirecionamento para a App Store. |
| <span id="telegram-webview"></span>Telegram WebView | A atribuição de modelagem probabilística não funciona para o engajamento de usuários no Telegram WebView (navegador do Telegram). Isso acontece pois o WebView não inclui modelos de dispositivos e versões de sistemas operacionais em suas solicitações de engajamento. |
| <span id="xiaomi-browser"></span>Navegador Xiaomi | A atribuição do modelo probabilístico não funciona para o engajamento do usuário no Navegador Xiaomi. |

</Accordion>

<div data-zendesk-anchors="onelink-links-and-experiences=links-e-experi%C3%AAncias-do-onelink h_01H8Y6DDT4M8XGAEJJVTHKHPKV=links-e-experi%C3%AAncias-do-onelink create-a-onelink-link=crie-um-link-do-onelink h_01H8Y6DDT41C6JYKXET0NDRB1G=crie-um-link-do-onelink h_01JRX3VWTVE77QVNG37BKPKHWW=nota h_01H8Y6DDT4C543RS2BXAGS487M=experiences h_01H8Y6DDT4WZ5FKZYBX2H08MFD=general-settings h_01KY2AWC72SCQKY3XEQGW2J269=importante enable-retargeting-for-the-app=ativar-o-retargeting-para-o-aplicativo h_01H8Y6DDT4R7785X5DRES66BKJ=ativar-o-retargeting-para-o-aplicativo h_01H8Y6DDT4JT9H0R13ZNGHJ79S=social-media-preview-og-tags h_01KY2AWC72V1JR1BBGKHPDQ7AF=nota-1 h_01H8Y6DDT4PHY2F5E3GK582P51=social-app-landing-page h_01H8Y6DDT463F5569B28DD17SV=importante-1 h_01H8Y6DDT4MMD1AW6D1PNGNX5X=observa%C3%A7%C3%A3o to-use-the-social-app-landing-page=para-usar-a-landing-page-social h_01H8Y6DDT4JB4RT438MAGNNX2S=para-usar-a-landing-page-social to-set-up-the-social-apps-landing-page=para-configurar-a-landing-page-de-aplicativos-sociais h_01H8Y6DDT4G34S3RV3ZH64XT19=para-configurar-a-landing-page-de-aplicativos-sociais h_01H8Y6DDT5XNJVYW2Y8F6JWPK2=deep-linking-and-deferred-deep-linking h_01KY2AWC73CNKHAF4HV26F132E=observa%C3%A7%C3%A3o-1 h_01H8Y6DDT5JR3B3DMR87JCBZ69=dicas h_01H8Y6DDT5KSBE00WWDGQ5R1AQ=observa%C3%A7%C3%A3o-2 h_01H8Y6DDT58FC3HMSRZBMGZZRJ=redirection h_01H8Y6DDT5AAQ3BZD8QB9H19QB=additional-parameters h_01H8Y6DDT5B6M7CETQRD9NKX8R=testing new-users-without-your-app-installed=novos-usu%C3%A1rios-sem-seu-aplicativo-instalado h_01H8Y6DDT50DH5TGVVPJPJC4MG=novos-usu%C3%A1rios-sem-seu-aplicativo-instalado existing-users-with-your-app-installed=usu%C3%A1rios-existentes-com-seu-aplicativo-instalado h_01H8Y6DDT5KDEWS40XPYGYC8HK=usu%C3%A1rios-existentes-com-seu-aplicativo-instalado additional-procedures=procedimentos-adicionais h_01H8Y6DDT5YR8JA5YMZFPMCC2X=procedimentos-adicionais h_01H8Y6DDT58EFS8S46D1AVP3T1=create-a-custom-impression-url h_01H8Y6DDT5S4NEJMNJR4K3QMNH=deep-linking-post-event h_01H8Y6DDT58Y6CS27M2W3MHYAD=deferred-deep-linking-with-ios-private-relay h_01H8Y6DDT5A7J07KNNRWCXCBH2=app-clipbased-solution flow=fluxo h_01H8Y6DDT5VDKAR89B8N6D7YMB=fluxo h_01H8Y6DDT62H71A8DPG00A3ZTN=clipboardbased-solution flow::21baf6ac=fluxo-1 h_01H8Y6DDT638T7C9HQHZ1CJ726=fluxo-1 requirements=requisitos h_01H8Y6DDT6JGP33AWFQV6Z8FF0=requisitos setup=configura%C3%A7%C3%A3o h_01H8Y6DDT61ENGJFZ1XS28GS1T=configura%C3%A7%C3%A3o additional-information=informa%C3%A7%C3%B5es-adicionais h_01H8Y6DDT679SGBTSM669F9FHV=informa%C3%A7%C3%B5es-adicionais h_01H8Y6DDT6TX4WTP2HYRF11DZ3=examples h_01H8Y6DDT6TQYRS81BMHARB62S=traits-and-limitations" />

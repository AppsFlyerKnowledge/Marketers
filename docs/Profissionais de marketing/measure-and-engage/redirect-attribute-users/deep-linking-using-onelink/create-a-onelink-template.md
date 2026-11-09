---
title: Criar um template OneLink
metadata:
  keywords:
    - template
    - Marketers
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2014-11-03T12:35:49Z'
  edited_at: '2026-09-01T00:34:12Z'
  id: 207032246
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/207032246
---
> **Resumo:** crie um template para definir uma lógica de redirecionamento para todos os seus links do OneLink em suas campanhas de marketing. Um template é necessário para criar links e experiências para seus usuários finais.

<div id="onelink-templates" />

## Templates do OneLink

<Embed title="Criar um template OneLink" typeOfEmbed="youtube" url="https://www.youtube.com/embed/d4AtCJ9122Q" providerUrl="https://www.youtube.com" />

O template do OneLink:

* Não é um link que pode ser usado por seus usuários finais; ele é a sua base para criar muitos links personalizados. Normalmente, você só precisa de um template por app (sem contar os testes) para gerar quantos links quiser para todas as suas campanhas publicitárias.
* É onde você registra suas decisões sobre como redirecionar usuários com base em sua plataforma de dispositivos e sobre se eles têm ou não seu aplicativo instalado.
* Ele representa a lógica de roteamento central de todos os seus links do OneLink. Isso inclui as configurações de redirecionamento para:
  * **Novos usuários que não têm o seu app instalado**: para a loja de aplicativos ou web URL ideal
  * **Usuários existentes com seu aplicativo instalado**: abrindo o seu app através de App Links do Android, Universal Links do iOS ou esquemas URI. Isso requer a ação de um desenvolvedor.
  * **Observação**: as configurações de redirecionamento do site ou da loja de aplicativos podem ser substituídas no nível do link.

<div id="create-a-onelink-template" />

## Como criar templates do OneLink

| Quem está envolvido | Pré-requisitos | Tempo necessário | Caraterística |
| --- | --- | --- | --- |
| <ul><li>Apenas o profissional de marketing precisa estabelecer uma lógica de redirecionamento para novos usuários que não possuem o seu aplicativo instalado (por exemplo, para a loja de aplicativos ou página da web correta).</li><li>Para adicionar uma lógica de redirecionamento para usuários existentes, que já têm o seu app instalado (por exemplo, para abrir o app), tanto o profissional de marketing quanto desenvolvedores do Android/iOS devem participar desse processo.</li></ul> | <ul><li>Uma conta da AppsFlyer com pelo menos um aplicativo.</li><li>O profissional de marketing deve ser um usuário administrador da AppsFlyer, ou ter <Anchor target="_blank" href="/marketers/pt/docs/user-management">permissão para adicionar/editar templates do OneLink</Anchor>.</li></ul> | Aproximadamente 1 hora e meia, trabalhando em conjunto com seus desenvolvedores Android/iOS. | Um template a partir do qual você pode criar links que enviam os usuários para a loja de aplicativos, para a página web ou para o aplicativo de acordo o dispositivo usado. |

<div id="create-a-onelink-template-with-redirection-logic-for-new-app-users" />

<Accordion title="Como criar um template com lógica de redirecionamento para novos usuários">

**Para criar um template do OneLink:**

1. Na AppsFlyer, no menu lateral, selecione **Engajamento** > **gerenciar o OneLink**.  
   As ferramentas do OneLink permitem que você crie templates e links personalizados para todos os seus aplicativos.  
   [![](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)**Atenção:**](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png) se você não tiver nenhum template criado, um assistente de onboarding será aberto. Siga as instruções e desconsidere o restante desse procedimento.
2. Clique em **salvar template do OneLink** (atualize o template do OneLink para templates editados).A página de configuração abre.  
   <Image align="center" alt="OneLink_template_page_en-us.png" src="https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png" />
3. No campo **nome do template do OneLink**, insira um nome.

   <div id="note" />

   > 📘 **Observação**
   >
   > * Um bom nome de template inclui o **nome do aplicativo** (por exemplo feed\_me) ou o caso de uso ou experiência representada pelo OneLink (por exemplo, pre\_launch\_landing\_page).
   > * O nome não deve incluir o nome da campanha, do canal ou fonte de mídia (já que esse não é o link do usuário final), nem o nome da plataforma (Android, iOS, já que plataformas múltiplas costumam são o motivo para usar um template do OneLink, em primeiro lugar).
   > * Esse é usado apenas internamente. Ele não afeta seus dados de atribuição e não é visto pelos usuários.

4. No campo **subdomínio** , insira o nome do seu <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#subdomínio">subdomínio</Anchor>.
   * Escolha um subdomínio que corresponda à sua marca. Por exemplo, se seu site for www.abcd.com, escolha abcd como seu subdomínio.
   * Os usuários verão esse subdomínio como parte da URL. Por exemplo: `https://abcd.onelink.me/RPsv/37e5cd36`
   * O subdomínio não pode ser alterado depois que links personalizados forem criados com base nesse template.
   * Use apenas letras minúsculas, dígitos ou hífen (-).
   * O OneLink também é totalmente compatível com branded domains, que podem te ajudar a melhorar a performance de uma campanha e aumentar a exposição da marca. <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain">Saiba mais</Anchor>
5. Selecione seu aplicativo Android, iOS, ou ambos.
6. (Opcional) Ative shortlinks seguros se quiser impedir que seus links sejam sequestrados com parâmetros extras. **Para ativar shortlinks seguros:**

   Em **Shortlinks seguros**, ative **Não atribuir cliques com parâmetros adicionados**.

   Veja o que isso significa para você: depois de ativado, se alguém adicionar um parâmetro a um shortlink criado a partir deste modelo, esse clique não será atribuído. O usuário é redirecionado de acordo com as configurações de redirecionamento do modelo; apenas a atribuição é afetada.  

   **Exemplo:**

| Link | Resultado |
| --- | --- |
| `[subdomain].onelink.me/[template_id]/[shortlink_id]` | Atribuído como de costume. |
| `[subdomain].onelink.me/[template_id]/[shortlink_id]?param=value` | Um parâmetro foi adicionado, portanto o clique não é atribuído. |

   **Atenção:**

   * Essa configuração se aplica no nível do modelo. Não há como ativá-la ou desativá-la para links individuais.
   * Para modelos criados antes do lançamento desse recurso, a configuração fica desativada. Ative-a se quiser. Para modelos criados após o lançamento, ela vem ativada por padrão; desative-a se não quiser.
7. Defina para onde os usuários serão redirecionados **quando o aplicativo não estiver instalado**.  
   * Se você selecionou um aplicativo Android e um aplicativo iOS, o template é configurado por padrão para enviar novos usuários para a loja de aplicativos correta.
   * Se você selecionou apenas um aplicativo, Android ou iOS, o template será configurado para enviar TODOS os usuários (do iOS e do Android, novos e existentes) para o único destino definido.
   * Se você selecionar um aplicativo do Android que não está no Google Play, terá que inserir uma URL para a qual os usuários do Android serão redirecionados.
   * [Opcional] **Redirecione para lojas de aplicativos externas** se o seu app estiver disponível em outras lojas além do Google Play. Certifique-se de que o app nessas outras lojas tenha o mesmo nome de pacote que o app Android selecionado no template do OneLink.
   * [Opcional] **Mude para uma URL diferente**: em alguns casos, você pode querer oferecer uma experiência na web mobile para novos usuários, sem levá-los diretamente para a loja de aplicativos (ou caso o seu app não esteja listado em uma loja). Para implementá-la, introduza a URL no campo URL. **Atenção:** se você configurar um redirecionamento para uma loja externa e uma URL diferente, o redirecionamento padrão envia os usuários para a loja externa.
   * [Opcional] Habilite **ativar App Clip para usuários com Private Relay** (disponível no iOS 14+). <Anchor target="_blank" href="/marketers/pt/docs/apple-app-clips-integration-guide">Saiba mais sobre App Clips.</Anchor>
8. Pule a configuração para casos em que **o app está instalado**. Vamos falar sobre isso no [procedimento seguinte.](/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users)
9. **Observação**: configurações de redirecionamento para um site ou loja de aplicativos podem ser substituídas no nível do link.  
   * * Em alguns casos, o usuário pode clicar no seu link em um computador desktop, especialmente quando o link é enviado através de e-mail ou redes sociais. Se você espera receber um grande tráfego de desktop para o seu link, recomendamos que você envie esses usuários para uma landing page ou para a página inicial do seu site, ou então para uma página onde eles possam solicitar um SMS com o link.
   * Por padrão, os usuários de desktop são redirecionados para uma versão web da App Store ou da Google Play Store - dependendo dos aplicativos configurados no template.
     * * Para alterar a opção de loja padrão, selecione "URL da web para desktop" e adicione a URL da loja relevante. Certifique-se de adicionar o domínio da loja à redirect allowlist.
10. [Opcional] **Selecione aplicativos de outras plataformas**  
    Se você tiver uma versão do app dedicada para:
    * **Windows Phone**: ative a alavanca e selecione o aplicativo ou **mude para uma URL diferente**.
    * **iPad**: ative a alavanca e selecione o aplicativo iPad
    * **Amazon Kindle Fire**: ative a alavanca e adicione a URL da loja Amazon ASIN ou da página do aplicativo.
11. **Resumo:** crie um template para definir uma lógica de redirecionamento para todos os seus links do OneLink em suas campanhas de marketing. Um template é necessário para criar links e experiências para seus usuários finais.

</Accordion>

<div id="add-redirection-logic-for-existing-app-users" />

<Accordion title="Adicionar lógica de redirecionamento para usuários existentes">

Os usuários existentes normalmente esperam ser redirecionados diretamente para o aplicativo, e não para uma loja de aplicativos ou página na web. Há três tecnologias disponíveis para abrir o aplicativo logo após um clique:

* **Universal Links do iOS:** podem ser usados a partir do iOS 9, fornecendo uma experiência rápida e segura para a abertura do seu app.
* **App Links do Android:** podem ser usados a partir do Android 6, fornecendo uma experiência rápida e segura para a abertura do seu app. **App Links do Android:** podem ser usados a partir do Android 6, fornecendo uma experiência rápida e segura para a abertura do seu app.
* **Esquema URI**:  
  * Método de fallback:
    * Android: o esquema URI é um método de fallback eficaz para quando os App Links não abrem o aplicativo, seja porque eles não funcionam ou porque não foram configurados.
    * iOS: recursos de fallback limitados para casos em que os Universal Links não abrem o aplicativo, seja porque eles não funcionam ou porque não foram configurados. <Anchor target="_blank" href="/marketers/pt/docs/uri-scheme-fallback-for-ios">Saiba mais</Anchor>
  * Método principal para abrir aplicativos em dispositivos Samsung.
  * É um endereço que, quando acessado, abre seu aplicativo caso ele esteja instalado. Eles são semelhantes aos links de sites, mas para aplicativos.
  * Deve ser o mesmo para iOS e Android.

Para oferecer a melhor experiência, segurança e cobertura aos seus usuários, recomendamos que você use o maior número possível de tecnologias. Se você ativar todas as tecnologias de link, o OneLink aplicará automaticamente o melhor método para cada usuário.

**Para adicionar lógica de redirecionamento para usuários existentes ao seu template do OneLink:**

1. Na AppsFlyer, no menu lateral, selecione **Engajamento** > **gerenciar o OneLink**.
2. Selecione o template do OneLink que você quer editar.
3. Clique no ícone do menu (⋮) e depois clique em **editar template do OneLink**.
4. Role para baixo até **Quando o aplicativo está instalado**. [![](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)
5. Siga as instruções para iOS, Android e configuração de fallback:

   <Tabs>
   <Tab title="Universal Links do iOS">

   Os App Links seguem o formato padrão de web links (por exemplo, https://suamarca.onelink.me ou https://www.suamarca.com) e, por isso, exigem um subdomínio (como explicamos no [guia anterior](/docs/create-a-onelink-template#como-criar-templates-do-onelink)). O OneLink também oferece suporte a <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain">branded domains</Anchor>, mas isso não é necessário para concluir este guia.

   **Para iniciar o aplicativo usando Univeral Links**:

   1. Entre em contato com seu desenvolvedor do iOS:
      * Dê a ele o subdomínio para o template do OneLink.
      * Peça que ele siga <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">essas instruções</Anchor>.
      * O desenvolvedor retorna para você o Team ID (também chamada Apple App ID Prefix, por exemplo, PF23MIWNTW).
      * Se o aplicativo ainda não estiver publicado, o desenvolvedor também deverá fornecer o Bundle Identifier (por exemplo, com.meuapp.exemplo).  
        <Image align="center" alt="" src="https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png" />
   2. Na página de template do OneLink, clique em **Alterar para iniciar o aplicativo usando Universal Links**.
   3. Na nova janela, selecione **Inicializar o aplicativo usando Universal Links.**
   4. No campo **Team ID**, insira o Team ID fornecido pelo desenvolvedor.
   5. Se o aplicativo não estiver publicado, insira também o **Bundle Identifier**.
   6. Clique em **Salvar alterações**.

   </Tab>

   <Tab title="App Links do Android">

   Os Universal Links seguem o formato padrão de web links (por exemplo, https://suamarca.onelink.me ou https://www.suamarca.com) e, por isso, exigem um subdomínio (como explicamos no [guia anterior](/docs/create-a-onelink-template#como-criar-templates-do-onelink)). O OneLink também é compatível com <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain">domínios totalmente personalizados</Anchor>, mas isso não é necessário para concluir essas instruções.

   **Antes de começar**:

   Registre o subdomínio escolhido para o template do OneLink.

   **Para iniciar o aplicativo usando App Links**:

   1. Fale com seu desenvolvedor do Android:   
      Peça que ele gere um fingerprinting SHA256 seguindo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">essas instruções</Anchor>.  
      Fale com seu desenvolvedor do Android:   
      Peça que ele gere um fingerprinting SHA256 seguindo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">essas instruções</Anchor>.  
       Por exemplo: `DC:65:43:67:F3:BD:02:52:AC:B4:50:F1:74:54: 23:49:4D:49:6C:E6:DF:56:BD:CB:53:06:11:5B:C9:4E:5D:0C`.
   2. Na página de template do OneLink, clique em **Alterar para iniciar o aplicativo usando App Links**.
   3. Na nova janela, selecione **Inicializar o aplicativo usando App Links.**
   4. No campo de **fingerprinting SHA256**, insira o fingerprinting SHA256 fornecido pelo desenvolvedor.  
      Um código de intent-filter gerado automaticamente é exibido.
   5. Fale com seu desenvolvedor do Android:   
      Forneça o código de intent-filter.  
      Peça que ele siga <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">essas instruções</Anchor> e confirme a conclusão.

   </Tab>

   <Tab title="Esquema URI">

   O esquema URI serve principalmente como fallback para usuários iOS e Android, e por isso deve ser o mesmo em ambos.

   **Para configurar o fallback de URI para Android e iOS:**

   1. Entre em contato com seus desenvolvedores iOS e Android para configurar o esquema URI. Por exemplo: `feedmeapp://`.

      <div id="tip" />

      > 👍 **Atenção**
      >
      > * A Apple e o Google não aplicam nomenclatura exclusiva para esquemas de aplicativos. **Escolha um nome de esquema exclusivo para a sua marca** para evitar esquemas conflitantes nos diferentes aplicativos. Uma sugestão de nome seria o bundle ID do seu aplicativo, por exemplo **com.empresa.app**.
      > * Para habilitar o OneLink de forma que ele seja usado tanto para o iOS como para o Android, é importante que **o mesmo esquema seja configurado para ambas as plataformas**. Veja as instruções para <Anchor target="_blank" href="https://help.contrast.co/hc/en-us/articles/200865293-URL-Scheme-Intro-for-App-Developers">iOS</Anchor> e <Anchor target="_blank" href="https://developer.android.com/training/app-links/deep-linking.html">Android</Anchor>.
      > * O esquema URI não deve começar com http ou https.

   2. O desenvolvedor do iOS deve implementar o esquema URI em seu aplicativo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-uri-scheme">seguindo essas instruções</Anchor>.  
      **E**  
      O desenvolvedor do Android deve implementar o esquema URI em seu aplicativo <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#procedures-for-uri-scheme">seguindo essas instruções.</Anchor>
   3. Quando concluído, o desenvolvedor deve confirmar o valor do esquema URI implementado. Ele deve ter um dos seguintes formatos: `exampleapp://` ou `exampleapp://home` ou `exampleapp://main`, etc.
   4. Na página de template do OneLink, clique em **Adicionar esquema URI para iniciar o aplicativo**.
   5. Selecione **Iniciar o aplicativo usando o esquema URI**.
   6. Insira o valor do esquema URI.
   7. Clique em **Salvar alterações**.
   8. Teste o esquema URI (isso pode ser feito por você OU seus desenvolvedores):
      1. Acesse <Anchor target="_blank" href="https://halgatewood.com/deeplink/">essa ferramenta de teste gratuita</Anchor> em um dispositivo iOS e Android que tenha seu aplicativo instalado.
      2. Toque no link gerado pela ferramenta.  
         Se o esquema URI estiver correto, o aplicativo será aberto.

   </Tab>
   </Tabs>

6. Clique em **Atualizar template do OneLink**.

<div id="h_01H9Q4E7VR4CAK0PJY269GQ9XJ" />

<div id="note-1" />

> 📘 **Atenção**
>
> * Quando você salva ou atualiza seu template do OneLink, a AppsFlyer gera automaticamente o arquivo AASA e/ou Digital Asset Links JSON para verificar o domínio do seu aplicativo, hospedando-o por você. Isso é essencial para que seus Universal Links e App Links funcionem corretamente.
> * Pode levar até 1 hora para que as atualizações do template entrem em vigor.

</Accordion>

<div id="customize-qr-codes" />

<Accordion title="Personalização de QR codes">

<Image align="center" alt="OnelinkQRFinal__1_.gif" src="https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif" />

Você pode personalizar os QR codes gerados via OneLink:

* Adicione seu logotipo.
* Mude a cor do QR code.

**Atenção:** A personalização de QR codes é feita no nível do template; não no nível do link individual. Portanto, as personalizações afetam todos os QR codes feitos com base no template editado.

**Para personalizar seu QR code**:

1. Na AppsFlyer, no menu lateral, selecione **Engajamento** > **Links personalizados do OneLink**.
2. Passe o mouse sobre o ícone **ações** do template que você deseja editar e clique em **personalizar QR code**.  
   O editor de QR codes abre.
3. Insira a URL onde seu logo está hospedado. Por exemplo: https://suamarca.com/logo.png.  
   Requisitos do logotipo:

   * Formato PNG ou JPG
   * Quadrado ou circular com fundo transparente
   * Dimensões mínimas 400 x 400 px
   * Para impressão, use a resolução máxima de imagem
4. Defina a cor do QR code.
5. Clique em **Salvar**.

</Accordion>

<div id="h_favicon" />

<Accordion title="Defina um favicon para pré-visualizações de links">

Um favicon é o pequeno ícone que aparece ao lado do título do seu link quando um link é compartilhado em redes sociais ou aplicativos de mensagens. Personalize a aparência adicionando seu próprio ícone aqui. Ele se aplica a todos os links baseados neste modelo e é exibido em plataformas compatíveis quando um link é compartilhado com uma pré-visualização personalizada de rede social configurada.

<div id="note-2" />

> 📘 **Importante!**
>
> Este favicon só aparece em pré-visualizações de links em plataformas compatíveis e somente quando a opção **Pré-visualização personalizada (imagem e tags)** está configurada no nível do link. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags">Saiba mais</Anchor>

**Para definir um favicon para o seu modelo do OneLink:**

1. Na AppsFlyer, no menu lateral, selecione **Engajamento** > **gerenciar o OneLink**.
2. Selecione o template do OneLink que você quer editar.
3. Clique no ícone do menu (⋮) e depois em **Editar template do OneLink**.
4. Role para baixo até a seção **Favicon**.
5. No campo **URL da imagem do favicon**, insira a URL da imagem do favicon.
   * Formato compatível: ICO
   * Tamanho recomendado do ícone: 32×32 ou 64×64 pixels
   * O tamanho do arquivo não deve exceder 100 KB.
   * A URL deve ser acessível publicamente
6. Verifique a **Visualização** para confirmar se o ícone é exibido corretamente.
7. Clique em **Atualizar template do OneLink**.

</Accordion>

<div id="traits-and-limitations" />

## Características e Limitações

<div id="key-traits-and-limitations" />

<Accordion title="Caraterística">

| Caraterística | Observações |
| --- | --- |
| Agências | As agências não podem criar templates e links do OneLink. |
| Adicionar/editar templates do OneLink | Os usuários da conta precisam de <Anchor target="_blank" href="/marketers/pt/docs/user-management">permissão</Anchor> para adicionar e editar templates do OneLink. |
| Templates do OneLink | Até 600 templates do OneLink por conta. |
| Desktop | Quando você configura a URL ou template do OneLink para redirecionar os usuários de desktop para uma URL diferente, a web URL é adicionada ao link no parâmetro `af_web_dp`. Se o link contiver `af_web_dp`, a AppsFlyer não registrará um clique quando ele ocorrer no desktop |
| Redirecionar para lojas de aplicativos externas | Várias lojas de aplicativos só podem ser configuradas no template do OneLink se o nome do pacote do aplicativo for o mesmo para todas as lojas. Para saber mais sobre o redirecionamento do OneLink para lojas externas do Android, clique <Anchor target="_blank" href="/marketers/pt/docs/bulletin-onelink-redirection-to-third-party-android-app-stores?query=3rd%20party%20store">aqui</Anchor>.<br /><br />**Observação**:<ul><li>Às vezes, a Huawei e outras lojas externas exigem nomes de pacotes diferentes. Se esse for o caso, o mesmo template do OneLink não pode ser usado para várias lojas.</li><li>Alguns dispositivos Xiaomi têm a loja GetApps, que usa o mesmo esquema URI do Google Play. Isso significa que, se você pretende redirecionar esses usuários para o Google Play, mas seu aplicativo não existe na Xiaomi, o link será redirecionado para o GetApps.</li><li>Se o nome do pacote for o mesmo, mas o canal for diferente, o redirecionamento funcionará, mas a atribuição não.</li><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">Saiba mais</Anchor> sobre a atribuição e os dados de lojas de aplicativos externas.</li></ul> |
| Atualizar um template | <ul><li>Alterações na configuração de um template do OneLink levam até 1 hora para serem aplicadas.</li><li>Os templates do Onelink não podem ser editados se um aplicativo associado foi excluído da conta. Nesse caso, você pode:<ul><li>Criar um novo template.</li><li>Entrar em contato com o seu customer success manager da AppsFlyer ou enviar uma mensagem para hello@appsflyer.com para restaurar o aplicativo excluído.</li></ul></li></ul> |
| Caraterística | Consulte <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#chrome-browser-on-ios">aqui</Anchor>. |

</Accordion>

Você tem alguma dúvida sobre os templates do OneLink? Confira nosso <Anchor target="_blank" href="/marketers/pt/docs/onelink-troubleshooting-and-faq#perguntas-frequentes-sobre-o-template-do-onelink">FAQ</Anchor>!

<div id="next-step" />

## Próxima etapa

Siga as instruções para <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">criar links do OneLink</Anchor> com base no seu template.

<div data-zendesk-anchors="onelink-templates=templates-do-onelink h_01H9Q4E7VQ0GKZ9HFF88190TYN=templates-do-onelink procedures=como-criar-templates-do-onelink h_01H9Q4E7VQYGZ1MH5SS3ZYZF1K=como-criar-templates-do-onelink h_01H9Q4E7VQ648CQ1VJTB1TC571=create-a-onelink-template-with-redirection-logic-for-new-app-users h_01H9Q4E7VQ15AAR1VXNKWR1XGT=observa%C3%A7%C3%A3o h_01H9Q4E7VQ4NEWYAD6AMR9YKGY=add-redirection-logic-for-existing-app-users h_01H9Q4E7VR4CAK0PJY269GQ9XJ=aten%C3%A7%C3%A3o-1 h_01H9Q4E7VR8164HR6MD0EAV2SN=aten%C3%A7%C3%A3o-1 h_01H9Q4E7VR0F4B7CTF08YTG715=customize-qr-codes set-a-favicon-for-link-previews=h_favicon h_01KT6GG94CRBYFDWZ28BA8HEYY=importante traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KZX85DYWA1TJ0AS3QV27VPA4=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01H9Q4E7VR2B50EQE31DDG8GNZ=key-traits-and-limitations next-step=pr%C3%B3xima-etapa h_01H9Q4E7VRJK31P9CSGJFCKQQF=pr%C3%B3xima-etapa" />

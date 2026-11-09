---
title: Adicionar um aplicativo à AppsFlyer
metadata:
  keywords:
    - Add App
    - adding an app
    - Advertisers
    - could not add app
    - security reasons
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-01-20T08:57:00Z'
  edited_at: '2026-08-19T00:16:59Z'
  id: 207377436
  locale: pt
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/pt/articles/207377436
---
> **Resumo:** saiba como adicionar seu aplicativo à AppsFlyer para obter dados de atribuição sobre instalações e eventos in-app e analisar os dados usando as diferentes ferramentas da AppsFlyer.

<div id="overview" />

## Visão geral

Se você ainda não adicionou um aplicativo ao seu dashboard, a página Integração do aplicativo será exibida quando você fizer login na AppsFlyer. A integração do aplicativo orienta você em todas as etapas para adicionar seu aplicativo e também prepará-lo para atribuição.

<div id="entering-the-wizard-for-adding-an-app" />

### Entrar no assistente para adicionar um aplicativo

Você pode adicionar todos os seus aplicativos por meio da página de integração do aplicativo ou entrar no assistente para adicionar aplicativos na plataforma.

**Para entrar no assistente na página de integração do aplicativo:**

* Na etapa **Adicione um aplicativo**, clique em **Adicionar aplicativo** e siga as instruções para adicionar um aplicativo.

<div id="note" />

> 📘 **Nota**
>
> Se a página de integração ainda não estiver aberta, na barra de menu superior > menu suspenso de endereço de e-mail, clique em **Integração do aplicativo**.

<Image align="center" alt="onboarding page.png" src="https://files.readme.io/8903839c25f12df28e1c4b488699670e2dadca83af9ddfebfc0cf4eacd2ce744-33198275479953.png" />

**Para entrar no assistente e adicionar um aplicativo da plataforma:**

* Na barra de menu superior > **Meus aplicativos,** clique em **+ Adicionar aplicativo**
* Na página inicial da AppsFlyer, clique em **+ Adicionar aplicativo**
* Na barra de menu superior > menu suspenso de endereço de e-mail > **Integração do aplicativo**, clique em **+ Integrar outro aplicativo**

<Image align="center" alt="add an app (1).png" src="https://files.readme.io/894b7b76c1da76e2308b110266cbffeb579c551033ce302ade182c1d63fd9384-33198275483793.png" width="593px" />

<div id="adding-an-app" />

## Adicionando um aplicativo

Depois de [entrar no assistente](#entrar-no-assistente-para-adicionar-um-aplicativo), siga essas etapas:

1. [Insira as informações do aplicativo](#insira-detalhes-do-aplicativo).
2. [Insira informações adicionais](#insira-informações-adicionais-não-aplicáveis-a-aplicativos-da-web).
3. Clique em **Adicionar meu aplicativo**.
4. Copie a chave do desenvolvedor, para ser usada na <Anchor target="_blank" href="/marketers/pt/docs/getting-started-onboarding-for-marketers#passo-2-integração-sdk--api">integração do SDK</Anchor> (você pode recuperá-la posteriormente na página <Anchor target="_blank" href="/marketers/pt/docs/app-settings#configurações-gerais-do-aplicativo">Configurações do aplicativo</Anchor>).
5. Clique em **Concluído** ou **+ Adicionar outro aplicativo** para adicionar mais aplicativos. Repita o processo para adicionar mais apps.

<div id="note-1" />

> 📘 **Atenção**
>
> * Somente administradores e <Anchor target="_blank" href="/marketers/pt/docs/user-management">usuários da conta com as permissões necessárias</Anchor> podem adicionar aplicativos.
> * Conforme você segue as etapas para adicionar um aplicativo (abaixo), as opções disponíveis variam de acordo com as opções anteriores selecionadas.

Após registrar o aplicativo, ele aparecerá no dashboard. Para que instalações e eventos in-app sejam registrados e atribuídos às fontes de mídia corretas, você precisará:

* Integrar o SDK
* Conectar o aplicativo a parceiros no Partner Marketplace

Veja <Anchor target="_blank" href="/marketers/pt/docs/getting-started-onboarding-for-marketers">todas as etapas</Anchor> para concluir o processo de integração.

<div id="enter-app-details" />

### Insira detalhes do aplicativo

Selecione a plataforma do aplicativo e digite as informações necessárias, conforme listado abaixo:

<div id="android-androidtv-fire" />

<Accordion title="Android, AndroidTV, Fire">

Use essa opção para as seguintes plataformas:

* Android (mobile)
* Android TV
* Fire da Amazon
* Amazon Fire TV
* Kindle

<Table>
  <thead>
    <tr>
      <th>
        Status do Google Play
      </th>
      <th>
        Quando utilizar
      </th>
      <th>
        Informações obrigatórias
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="in-store"></span>
        In store
      </td>
      <td>
        Seu aplicativo está disponível no momento na loja do Google Play
      </td>
      <td>
        **URL do Google Play** (copiado do Google Play)

        * **Exemplo:** https://play.google.com/store/apps/details?id=com.appsflyer.adNetworkTest&hl=en&gl=GB
        * **Importante!**
          * Se o seu aplicativo **não** estiver listado na Google Play Store dos EUA:
            * A URL deve incluir o código do país de qualquer loja em que ele esteja listado, como como mostrado no exemplo acima: **&gl=`{country_code}`.** Se você não incluir o código do país, você vai receber um erro ao tentar adicionar o aplicativo.
            * O código de idioma é opcional: **&hl=`{language_code}`**
          * Se a sua loja **está** listada na Google Play store dos EUA, os códigos do país e do idioma são opcionais.
      </td>
    </tr>
    <tr>
      <td><span id="pending-approval-not-published"></span>
        Aprovação pendente ou não publicada
      </td>
      <td>
        Seu aplicativo ainda não foi publicado ou depende da aprovação do Google Play
      </td>
      <td>
        **Nome do pacote Android**

        * **Exemplo:** com.appsflyer.adNetworkTest
        * **Atenção:** O nome do pacote é sensível a maiúsculas/minúsculas
        * **Formato:**
          * Pelo menos dois segmentos (um ou mais pontos)
          * Cada segmento deve começar com uma letra
          * Todos os caracteres devem ser alfanuméricos ou sublinhado (a-z, A-Z, 0-9 ou \_)
          * Comprimento máximo de 100 caracteres

        Para mais informações, consulte a <Anchor target="_blank" href="https://developer.android.com/studio/build/application-id">Documentação para desenvolvedores do Android</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="third-party-store-out-of-store"></span>
        Loja de terceiros/fora da loja
      </td>
      <td>
        Seu aplicativo está em uma app store Android diferente do do Google Play e/ou pode ser baixado do um local que não seja uma loja de aplicativos
      </td>
      <td>
        * **Nome do pacote Android:** Para requisitos detalhados, veja a linha anterior.
        * **App URL** (copiada da app store externa ou local externo)
        * **Nome do canal:** um nome exclusivo que você define no AndroidManifest.xml do APK individual preparado para essa loja/local. O nome deve ser:
          * diferencia maiúsculas de minúsculas
          * Nome do pacote Android

        ```xml
        <application>
             ...
             <meta-data android:name="CHANNEL" android:value="Amazon"/>
             ...
        Etapa 1</application>:
        ```

        <div id="note-2" />

        > 📘 **Nota**
        >
        > Não é recomendável usar o parâmetro canal para atribuição multiloja. Para uma implementação mais simples e padronizada, use o parâmetro af\_store.

        <div id="important" />

        > 🚧 **Importante!**
        >
        > Se o seu aplicativo estiver disponível em mais de uma fonte (ou seja, qualquer combinação de Google Play, lojas de terceiros ou locais externos), é fundamental considerar opções para <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">configurar a atribuição multiplataforma do Android</Anchor>.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="ios-tvos-macos" />

<Accordion title="iOS, tvOS, MacOS">

Use essa opção para as seguintes plataformas:

* /docs/ctv-pc-and-console-platform-attribution-concepts
* tvOS
* MacOS

| Status da App Store | Quando utilizar | Informações obrigatórias |
| --- | --- | --- |
| <span id="in-store::f93cfa22"></span>In store | Seu aplicativo está atualmente disponível na App Store | **URL da App Store** (copiada da App Store)<ul><li>**Exemplo:** https://apps.apple.com/us/app/partner-integrations/id1543229303</li><li>**Atenção:**<ul><li>Certifique-se de que a URL inclui da código de país de duas letras da loja (por exemplo, **us** na URL acima)</li><li>Um aplicativo adicionado à App Store antes de 14 de junho de 2019, pode conter itunes.apple.com na sua URL (em vez de apps.apple.com).</li></ul></li></ul> |
| <span id="pending-approvalnot-published"></span>Aprovação pendente ou não publicada | Seu aplicativo ainda não foi publicado ou depende da aprovação da App Store | **País** da App Store para o qual o aplicativo foi submetido<br /><br />**App ID** atribuído da App Store, sem o prefixo id<ul><li>**Exemplo:** 1543229303</li><li>**Formato:** 9 ou 10 caracteres numéricos, 0-9</li></ul> |

</Accordion>

<div id="windows-xbox" />

<Accordion title="Windows">

Use essa opção para as seguintes plataformas:

* Windows Phone
* Windows (desktop)

| Status da Microsoft Store | Quando utilizar | Informações obrigatórias |
| --- | --- | --- |
| In store | Seu aplicativo está atualmente disponível na Microsoft Store | **URL da Microsoft Store** (copiada da Microsoft Store)<ul><li>**Exemplo:** https://www.microsoft.com/en-us/p/wordament/9wzdncrfhwfg</li><li>**Atenção:** A URL acima é um exemplo para um app do Windows Phone. URL - formato: O formato de URL varia para aplicativos de desktop do Windows.</li></ul>**App ID:** Comprimento máximo de 50 caracteres. |
| Aprovação pendente ou não publicada | Seu aplicativo ainda não foi publicado ou depende da aprovação da loja | **App ID** atribuído pela Microsoft Store<ul><li>**Comprimento máximo:** 150 caracteres</li><li>**Exemplo:** 9wzdncrfhwfg</li><li>Atenção: O App ID é sensível a maiúsculas/minúsculas</li></ul> |

</Accordion>

<div id="web-pba" />

<Accordion title="Web (PBA)">

<div id="note-3" />

> 📘 **Atenção**
>
> Um aplicativo web é onde você define um site que será incluso em um brand bundle a nossa funcionalidade People-Based Attribution (PBA).
>
> * Esta opção está disponível apenas para clientes que assinam o PBA.
> * <Anchor target="_blank" href="/marketers/pt/docs/people-based-attribution-pba-overview">Saiba mais</Anchor> sobre o PBA e a atribuição de visitas web, eventos web e instalações assistidas por site para obter uma visão unificada das jornadas dos clientes em canais, plataformas e dispositivos.

**URL completa:** A URL completa do site para o qual você deseja mensurar o tráfego. Este é o site no qual você implementou (ou irá implementar) o <Anchor target="_blank" href="/marketers/pt/docs/onboarding-guide-to-people-based-attribution#2">SDK Web do PBA</Anchor>.

<Image align="center" alt="URL_diagram" src="https://files.readme.io/45c6e433af693fd8c293380192a8e60f26c82588195bab61bafbc9839baf5c7b-33198323426961.png" width="377px" />

Incluir –

* esquema
* subdomínio [opcional]
* nome de domínio
* domínio de nível superior
* caminho [opcional] – o endereço de um diretório ou página específica no seu website

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo

* Comprimento máximo: 100 caracteres
* Tags XSS não são permitidas

<div id="important-1" />

> 🚧 **Importante!**
>
> Após criar um aplicativo web, você não poderá editar as suas propriedades (URL e nome do aplicativo) sem precisar deletá-lo e recriá-lo, **o que significa que você também deve <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle">apagar o brand bundle</Anchor> ao qual ele pertence.**

**Próximos passos:**

* Adicione seu novo aplicativo web a um <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings">Brand Bundle do PBA</Anchor> para visualizá-lo no dashboard do PBA.
  * Assegure-se de que todos os aplicativos mobile que você deseja incluir foram adicionados à sua conta no brand bundle antes de criar o bundle.
* <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide">Integre o Web SDK do PBA</Anchor> ao site especificado no aplicativo web para fazer com que os dados de mensuração sejam transmitidos.

</Accordion>

<div id="web" />

<Accordion title="Web">

Use a plataforma web para criar um novo aplicativo web e mensurar visitas ao site e conversões usando a mensuração de performance web.

<div id="before-you-begin" />

#### **Antes de começar**

* Aplicativos web legados de People-Based Attribution (PBA) aparecem em “**web (PBA)**”, marcados como Legacy.
* Se você estiver migrando de um aplicativo web PBA legado, poderá usar sua chave de desenvolvimento web do PBA existente.

<div id="to-add-a-web-app" />

#### **Atenção**

1. Para requisitos detalhados, veja a linha anterior (Pending approval/not published)
2. Atenção
3. Insira o seguinte:

**Nome do aplicativo**: O nome que você escolheu para o seu aplicativo web.

* **Tamanho:** 1-100 caracteres
* **Caracteres permitidos:** Letras (qualquer idioma), números, espaços (não no início nem no fim) e caracteres especiais: . - \_ :
* **Caracteres bloqueados:** ; \`{ }\` $ &lt; > \` \

**Exemplo:** Minha Loja Online, Site Corporativo 2024, E-Commerce\_Production

**Domínio principal (URL completa)**: O domínio principal do seu site. Isso é definido durante a criação do aplicativo web e não pode ser alterado depois.

* **Formato:** Somente nome de domínio válido (sem protocolo, caminho ou porta)
* **Tamanho:** Máximo de 500 caracteres
* **Processamento:** o AppsFlyer automaticamente
  * Remove http:// ou https://
  * Remove as barras finais
  * converte o domínio para letras minúsculas
* **Imutabilidade:** Não pode ser editado após a criação do aplicativo

**Importante:** Para alterar o domínio principal, é necessário excluir e recriar o aplicativo web, o que resulta em perda da continuidade histórica dos dados.

**Exemplos:**

* https://shop.example.com/checkout → Armazenado como shop.example.com → ID do Aplicativo: website-shop.example.com
* example.com/ → Armazenado como example.com → ID do Aplicativo: [website-example.com](http://website-example.com)

**ID do Aplicativo**: O ID exclusivo que a AppsFlyer cria para o aplicativo web, com base no domínio principal.

* Gerado automaticamente usando o formato: website-`<primary_domain>`
* Por exemplo: website-shop.example.com

**ID do SDK web**: O identificador usado pelo SDK web para atribuição (anteriormente chamado de web\_dev\_key).

Duas opções durante a criação do aplicativo:

**Opção 1: Gerar novo (padrão)**

* Cria automaticamente um novo ID do SDK web
* Formato: website-`{yourdomain.com}`
* Por exemplo: website-shop.example.com
* **Caso de uso:** Novas implementações de atribuição web

**Opção 2: Reutilizar chave de desenvolvimento PBA existente**

* Selecione na lista suspensa as chaves de desenvolvimento de aplicativos web PBA (People-Based Attribution) existentes
* Permite uma migração sem interrupções sem alterar o código do site
* **Caso de uso:** Migrar do PBA legado para a nova solução de atribuição web

**Observação:** Reutilizar a chave de desenvolvimento PBA permite migrar do PBA para o novo aplicativo web **sem fazer nenhuma alteração na implementação do seu site.** Etapa 1:

Cada chave de desenvolvimento PBA pode ser atribuída a apenas **UM** aplicativo web. Depois que uma chave de desenvolvimento PBA é usada em um aplicativo web, ela não fica mais disponível para outros aplicativos web.

* **Tamanho:** 1-550 caracteres
* **Imutabilidade:** Não pode ser alterado após a criação do aplicativo
* **Migração de PBA:** Somente as chaves de desenvolvimento dos aplicativos web PBA da sua conta aparecem na lista suspensa

**Moeda**: A moeda usada nos relatórios do aplicativo.

* Código de moeda padrão ISO 4217 (por exemplo, USD, EUR, GBP, ILS)
* Selecionado no menu suspenso
* Campo obrigatório

**Fuso horário**: o fuso horário usado para os relatórios do aplicativo.

* Formato de fuso horário IANA (por exemplo, America/New\_York, Europe/London, Asia/Tokyo)
* Selecionado no menu suspenso
* Campo obrigatório

4. Clique em **Criar aplicativo**.

**Limitações**

* O **domínio principal não pode ser alterado** depois que o aplicativo é criado.
* O domínio principal é adicionado automaticamente a **Domínios excluídos** como tipo **PRIMARY**.

Cada **chave legada do Web Dev só pode ser reutilizada para um** novo aplicativo web.

<div id="note-4" />

> 📘 **Atenção**
>
> Para informações completas sobre as configurações de atribuição web, <Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings">veja aqui</Anchor>.

</Accordion>

<div id="roku" />

<Accordion title="Roku">

**Nome do aplicativo:** Nome do canal copiado do <Anchor target="_blank" href="https://developer.roku.com/developer">Roku Developer Dashboard</Anchor>.

* **Exemplo:** Meu canal Roku
* **Formato:**
  * Comprimento máximo de 100 caracteres
  * Tags XSS não são permitidas

**Channel ID:** ID numérico atribuído ao canal pela Roku.

* **Formato:**
  * Caracteres numéricos (0-9)
  * Comprimento máximo: 50 caracteres
* **Como posso encontrá-lo?**
  * No <Anchor target="_blank" href="https://developer.roku.com/developer">Roku Developer Dashboard</Anchor>, clique no nome do canal que você quer adicionar à AppsFlyer. Isto abrirá a página do Roku Preview & Publish para o canal.
  * O número no final da URL da página é o Channel ID: ID:

    <Image align="center" alt="" src="https://files.readme.io/89f6513eee03558a9dc8e465fe67953780074477fc0fe20675b721d8116671af-33198275490577.png" />

</Accordion>

<div id="amazon-vega-os" />

<Accordion title="Amazon Vega OS">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O ID do aplicativo. Encontrado usando a notação DNS reversa:  `<tld>`.`<company_name>`.`<app_name>`  
Deve conter no mínimo 2 segmentos. Cada segmento deve começar com uma letra, seguida de caracteres entre: `A-Z` `a-z` `0-9.` `_` `-`.

Para mais informações, consulte o campo “id” na <Anchor target="_blank" href="https://developer.amazon.com/docs/vega/0.21/manifest-package.html#fields">documentação do Amazon Vega OS</Anchor>.

</Accordion>

<div id="vizio-smartcast" />

<Accordion title="Vizio SmartCast">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O App ID, reconhecido pela Vizio. Começa com as letras `vz`, seguido de 2 a 10 caracteres de: `.` `-` `0-9` `.` `-`. Se precisar confirmar o App ID, fale com o seu representante da Vizio.

</Accordion>

<div id="samsung-tizen" />

<Accordion title="Samsung Tizen">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O Bundle ID atribuído ao seu app pela Samsung. Começa com a letra `G`, seguida de 8 a 15 dígitos. Você pode encontrá-lo no final da URL da loja de aplicativos do seu app:

1. Faça login no Samsung TV Seller Office usando [este link](https://developer.samsung.com/tv-seller-office/guides/overview.html).

   1. Insira a URL de desenvolvedor
2. Seu Bundle ID é gerado e exibido automaticamente. Isso pode ser usado para acessar a URL da loja de aplicativos.
3. Em caso de problemas, abra um ticket no quadro de issues no Seller Office.

Observação: para acessar sua página web exclusiva da loja de aplicativos, adicione o Bundle ID à URL "[https://www.samsung.com/us/appstore/app/](https://www.samsung.com/us/appstore/app/)".

Por exemplo, se o seu Bundle ID for "G15147002586", a URL da sua página será "[https://www.samsung.com/us/appstore/app/G15147002586/](https://www.samsung.com/us/appstore/app/G15147002586/) ". A URL do desenvolvedor, o Bundle ID e o ID da loja de aplicativos são exibidos nos metadados dessa página.

<Image align="center" alt="" src="https://files.readme.io/ee4b192abab24e064013a4a034bda38fb3ed49497ae333e327e1b78dd05d5349-33198275491729.png" />

</Accordion>

<div id="lg-webos" />

<Accordion title="LG WebOS">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O App ID da LG WebOS.

* **Formato:**
  * Comprimento máximo de 50 caracteres
  * Caracteres de `A-Z` `a-z` `.` `_` em um formato bundle-like . Deve começar com letras.
* **Exemplo:** com.a-minha-empresa.app

Se precisar de confirmar o App ID, fale com o seu representante LG WebOS.

</Accordion>

<div id="playstation" />

<Accordion title="PlayStation">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O conceito de ID da PlayStation, um identificador único atribuído a um jogo ou a outros conceitos de conteúdo. Aparece como um número de 5 a 9 dígitos na URL da PlayStation store. Pode encontrá-lo no final da URL:

<Image align="center" alt="playstation_app_id_url.png" src="https://files.readme.io/df92705244e55e7adc44a88076556609983ec3dff89c03df77e19f0f1a061bbb-33198323434513.png" />

</Accordion>

<div id="vidaa" />

<Accordion title="RIDA">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O App ID da Vidaa. Comprimento máximo de 50 caracteres.

</Accordion>

<div id="steam" />

<Accordion title="Steam">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O App ID da Steam. Este é o número composto por 5 a 8 dígitos que aparece na URL da loja Steam:

<Image align="center" alt="steam_store_app_url.png" src="https://files.readme.io/4976c0323eab0c08b61d4a1a7a75ebf7ea9fcd819176ff574421f0de4d8c614c-33198275497617.png" />

</Accordion>

<div id="meta-quest" />

<Accordion title="Meta Quest (Oculus)">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O App ID da Epic Games, conforme aparece na loja de onde o aplicativo é baixado. Inclui entre 3 a 50 caracteres de: `A-Z` `a-z` `0-9` `.`

<Image align="center" alt="" src="https://files.readme.io/1938b3f89b866ebdd3452367d7410c423ce57372544a801ca3d1b409f3bff541-33198323442449.png" width="397px" />

</Accordion>

<div id="nintendo-switch" />

<Accordion title="Nintendo Switch">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O App ID do Nintendo Switch, conforme aparece no final do URL da loja de onde o aplicativo é baixado. Inclui 14 dígitos.

* **Exemplo:** 70010000012345

</Accordion>

<div id="xbox" />

<Accordion title="Xbox">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O App ID do Xbox, conforme aparece no final da URL da loja do Xbox de onde o aplicativo é baixado. Inclui apenas 12 letras e dígitos (`A-Z` `a-z0-9`).

<Image align="center" alt="" src="https://files.readme.io/c33ffcb35d4488b9340cfa8b475097eab7b79bfeaf94e8cf8ce6478dda07d341-33198275505041.png" />

**Atenção:** O App ID diferencia letras maiúsculas de minúsculas.

</Accordion>

<div id="epic-games" />

<Accordion title="Epic Games">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O App Ide do Native PC. Inclui entre 3 a 50 caracteres de: `A-Z` `a-z` `0-9` `.`

<Image align="center" alt="" src="https://files.readme.io/81d1f043c8a7ef5e367a62d564f8c6241c6057445363b21286e3f72ad4210cf6-33198275508497.png" />

</Accordion>

<div id="native-pc" />

<Accordion title="PC nativo">

**Nome do aplicativo:** O nome que você escolheu para o seu aplicativo.

**App ID:** O App ID do Xbox, conforme aparece no final da URL da loja do Xbox, de onde o aplicativo é baixado. Inclui apenas 12 letras e dígitos (`0-9` `0-9` `0-9`).

</Accordion>

<div id="enter-additional-information-not-applicable-to-web-apps" />

### Insira informações adicionais (não aplicáveis a aplicativos da web):

<Image align="center" alt="" src="https://files.readme.io/561aea51bbfaa733721040706cac2b9520e35cfe71027fa34d08ed7890baf00c-33198323448081.png" width="559px" />

<div id="select-currency" />

#### **Selecione a moeda**

Selecione a moeda na qual os dados deste aplicativo serão exibidos no dashboard. Os eventos de receita e gasto são convertidos para essa moeda usando a taxa de câmbio em vigor no momento do evento. <Anchor target="_blank" href="/marketers/pt/docs/app-settings#localization-currency">Saiba mais</Anchor> sobre a configuração de moeda de um aplicativo e seu impacto.

<div id="important-2" />

> 🚧 **Importante!**
>
> Tome cuidado ao selecionar a moeda que deseja usar para esse aplicativo. Você não poderá alterá-la depois que o custo e a receita tiverem sido registrados.

<div id="select-timezone" />

#### **Selecione o fuso horário**

Alinhe o fuso horário que você selecionar aqui com o fuso horário que você definir com outros parceiros de atribuição (como Meta ads e do Google). Isso garante a correspondência mais próxima entre os dados reportados no dashboard da AppsFlyer e os dados que você recebe desses parceiros.

<div id="note-5" />

> 📘 **Nota**
>
> * Depois que o fuso horário for definido, ele permanecerá bloqueado e não poderá ser alterado até o dia seguinte.
> * <Anchor target="_blank" href="/marketers/pt/docs/changing-app-time-zone-settings">Saiba mais</Anchor> sobre a configuração de fuso horário de um aplicativo e seu impacto.

<div id="define-app-audience" />

#### **Configure a audiência do aplicativo**

Selecione **Sim** ou **Não** para indicar se seu aplicativo é direcionado ou não para crianças ou para um público misto (crianças e adultos).  
Caso tenha selecionado **Sim:**

1. Abra e leia o <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">guia</Anchor> sobre como implementar a compliance em aplicativos direcionados a crianças.
2. Marque a caixa para confirmar que você leu o guia e implementará os controles especificados.

<div id="note-6" />

> 📘 **Nota**
>
> * Duas semanas após adicionar o aplicativo, você receberá uma notificação solicitando a confirmação de que implementou controles de privacidade para seus aplicativos direcionados a crianças. Após a confirmação, você receberá uma mensagem de confirmação. Você sempre pode acessar a mensagem de confirmação na Central de notificações ou ver os detalhes da confirmação no <Anchor target="_blank" href="/marketers/pt/docs/audit-log">log de auditoria</Anchor>.
> * Veja as <Anchor target="_blank" href="/marketers/pt/docs/child-directed-apps-faq">perguntas frequentes sobre aplicativos para crianças.</Anchor>

<div id="manage-your-apps-in-bulk-via-api" />

#### Gerencie seus aplicativos em massa através da API

Os administradores de conta podem <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/app-management-v2-overview">gerenciar múltiplos aplicativos em massa</Anchor> utilizando uma API dedicada que oferece suporte para as principais funcionalidades. Isso inclui adicionar e remover aplicativos, assim como atualizar suas configurações. A API também possui os mesmos mecanismos de verificação de erros.

<div id="note-7" />

> 📘 **Nota**
>
> Nessa fase, adicionar aplicativo e atualizar as configurações via API só é possível para aplicativos mobile. Você pode deletar aplicativos para todas as plataformas.

<div id="add-a-debug-or-testing-app" />

### Adicionar um aplicativo de depuração ou teste

Se o desenvolvedor criar um **aplicativo de depuração**, **sandbox** ou **aplicativo de teste**, você deverá adicionar o aplicativo ao dashboard. Depois que o desenvolvedor começar a testar o aplicativo, os dados serão exibidos no dashboard do aplicativo.

<div id="note-8" />

> 📘 **Atenção**
>
> Para aplicativos iOS que ainda não foram publicados na App Store e ainda não têm um ID válido da App Store, você ainda pode prosseguir com o teste do SDK adicionando o aplicativo com um **ID fictício da App Store para iOS**. Isso permite a integração e o teste do SDK sem precisar de uma listagem real na App Store.

Para ver instruções para desenvolvedores sobre como criar um aplicativo de depuração e adicioná-lo ao dashboard, consulte:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-android#creating-an-android-debug-app">Instruções para Android</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-ios#creating-an-ios-debug-app">Instruções iOS</Anchor>

<div id="about-pending-apps" />

## Sobre aplicativos pendentes

Trabalhar com um aplicativo em estado pendente pode ser útil quando você estiver depurando-o para testar o SDK do AppsFlyer.

O status do aplicativo como "pendente" no painel não tem efeito na coleta e medição de dados. Se um aplicativo está pendente ou online em uma loja de aplicativos, se os usuários instalam e interagem com ele, os dados de instalação e de eventos no painel de controle são gravados exatamente da mesma forma.

Quando seu aplicativo pendente for ativado, a AppsFlyer detectará e atualizará automaticamente seu status, para que você não precise adicioná-lo novamente. <Anchor target="_blank" href="/marketers/pt/docs/why-is-my-app-still-pending">Saiba mais</Anchor> sobre aplicativos pendentes e o procedimento opcional para atualização manual do status.

<div id="troubleshooting" />

## Resolução de problemas

Encontre soluções para algumas questões comuns:

<div id="app-wasnt-added" />

<Accordion title="O aplicativo não foi adicionado">

Se esse erro ocorrer, entre em contato com seu CSM ou envie um e-mail para [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="app-not-in-the-store" />

<Accordion title="Aplicativo não está disponível na loja">

Verifique se você copiou a URL da store corretamente, usando o nome/ID apropriados do aplicativo.

</Accordion>

<div id="cant-access-marketplace" />

<Accordion title="Não é possível acessar o marketplace">

Esse erro às vezes ocorre quando se adiciona um aplicativo Android de uma store que não seja dos EUA. Para resolver esse problema, siga as etapas abaixo:

1. Adicione o aplicativo com um status de **Pending approval/not published**, conforme descrito acima.
2. Acesse a página **Configurações do aplicativo** da AppsFlyer.
3. Altere o **país da app store** para o país correto (por exemplo, Japão).

</Accordion>

<div id="something-went-wrong" />

<Accordion title="Ocorreu um erro. Por favor, tente outra vez.">

Um possível motivo para esse erro é tentar adicionar um aplicativo Android sem um código de país (para aplicativos **não** listados na Google Play Store dos EUA). Veja os detalhes completos para resolver esse problema [acima](/docs/adding-an-app-to-appsflyer#in-store).

</Accordion>

<div id="my-ios-app" />

<Accordion title="Meu aplicativo iOS foi removido da App Store. Por que ainda estou vendo instalações?">

Isso acontece porque os usuários podem reinstalar um aplicativo pelo sistema operacional se ele já existia em seu dispositivo. Mesmo que o aplicativo não esteja mais disponível na App Store, os usuários ainda podem instalá-lo, e essas instalações serão contabilizadas na AppsFlyer.

</Accordion>

<div id="other-information" />

## Outras informações

<div id="product-line" />

<Accordion title="Linha de produto">

Você pode adicionar ou remover aplicativos de uma linha de produto. Para mais informações sobre linhas de produto e o que elas oferecem, clique <Anchor target="_blank" href="/marketers/pt/docs/product-line-group-apps-for-cross-platform-attribution">aqui</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H8Y09SSKZS2RHM35JT16ESKM=vis%C3%A3o-geral entering-the-wizard-for-adding-an-app=entrar-no-assistente-para-adicionar-um-aplicativo 01H8Y0K9EHWH05DB5K02ASJG11=entrar-no-assistente-para-adicionar-um-aplicativo 01H8F2TENNWXADKVZFHY9SE8JC=nota adding-an-app=adicionando-um-aplicativo 01H8ECFB7V0DCNE0ZKPZ2GCVMP=adicionando-um-aplicativo 01H81661SR41SQFZZ0AW6K2EDM=aten%C3%A7%C3%A3o enter-app-details=insira-detalhes-do-aplicativo 01H815FE64VZZS9WGJSC8VY74D=insira-detalhes-do-aplicativo 01H815FE64CXEHWTV40NVYQHGJ=android-androidtv-fire h_01KRB930DZ2NRYBZSERSG7WB3A=nota-1 01H815FE641Q6N5JY5846QE59Y=importante 01H815FE64X0SPA71TBQ9T4ZVB=ios-tvos-macos 01H815FE64ZZA2N1XQFBRXVF41=windows-xbox 01H815FE64XZKDJW1CX5R1JE1T=web-pba 01H815FE646GWA7KJ83KTGHH05=aten%C3%A7%C3%A3o-1 01H815FE65R1Z06TJR0DNC8PFY=importante-1 h_01KGEPG8V7ZZ6V2EYYPES0QM77=web before-you-begin=antes-de-come%C3%A7ar h_01KGPM33BA6AJSX32CTN808AXM=antes-de-come%C3%A7ar to-add-a-web-app=aten%C3%A7%C3%A3o-2 h_01KGPM3GTYJJ0ARD3R1XHVAQ8F=aten%C3%A7%C3%A3o-2 h_01KGPM5TTNSECSWEAQY5VH7DTY=aten%C3%A7%C3%A3o-3 01H815FE65X37H40AN99EZJ940=roku h_01KDJP1G4QZHAKH13M5D3CD793=amazon-vega-os 01H815FE654W6D4FCANR1DET8A=vizio-smartcast 01H815FE65J6T610QQXWJS0CJS=samsung-tizen 01H815FE65CRW81AD1006KHGV4=lg-webos 01H815FE65ESQZ56C8B4HG9P8M=playstation 01H815FE65483DV8MD4STH3QTR=vidaa 01H815FE655PZS1H9YW95X1R53=steam 01H815FE655XP075WYRVVFKD4F=meta-quest 01H815FE65XJEVHNT45SHGWJS4=nintendo-switch 01H815FE6598PD87PNBE7MFEQ8=xbox 01H815FE658WJCB1ZCPGAD4GGS=epic-games 01H815FE652P3HCWY2PEDJJARM=native-pc enter-additional-information-not-applicable-to-web-apps=insira-informa%C3%A7%C3%B5es-adicionais-n%C3%A3o-aplic%C3%A1veis-a-aplicativos-da-web 01H815FE65AWE8VKV9FYJ7N8MV=insira-informa%C3%A7%C3%B5es-adicionais-n%C3%A3o-aplic%C3%A1veis-a-aplicativos-da-web select-currency=selecione-a-moeda h_01HHCFD94K6PGQRED6Z6KXKRQF=selecione-a-moeda 01H815FE65X7BCFKH1EEFA91GQ=importante-2 select-timezone=selecione-o-fuso-hor%C3%A1rio h_01HHCFDE25S92GZ9TPGQW4PXHV=selecione-o-fuso-hor%C3%A1rio h_01HMNSSBP2EFXCVW290MKW1EFV=nota-2 define-app-audience=configure-a-audi%C3%AAncia-do-aplicativo h_01HHCFDRNFDERZZV3TT8BVXMB4=configure-a-audi%C3%AAncia-do-aplicativo h_01H9MYF17VNBETQ0HS745EJ85H=nota-3 manage-your-apps-in-bulk-via-api=gerencie-seus-aplicativos-em-massa-atrav%C3%A9s-da-api h_01HR3Z81NXCAZKK26HWCN5VD9D=gerencie-seus-aplicativos-em-massa-atrav%C3%A9s-da-api h_01HR3ZJW7YD4B8WV0NW9MX6EVP=nota-4 add-debug-or-testing-app=adicionar-um-aplicativo-de-depura%C3%A7%C3%A3o-ou-teste h_01K2F8JX66F614HF8D5MWQ26P7=adicionar-um-aplicativo-de-depura%C3%A7%C3%A3o-ou-teste ios-dummy-app-id-note=aten%C3%A7%C3%A3o-4 h_01K2F8JX662XEY0A47DZG6DHWQ=aten%C3%A7%C3%A3o-4 about-pending-apps=sobre-aplicativos-pendentes 01H815FE65MYPABC3DTVEMA8E9=sobre-aplicativos-pendentes troubleshooting=resolu%C3%A7%C3%A3o-de-problemas 01H815FE655HS8EA4R00D0VCYD=resolu%C3%A7%C3%A3o-de-problemas 01H815FE65V2GYP0Q612512DE0=app-wasnt-added 01H815FE65A0HPTVVCT42QQA6M=app-not-in-the-store 01H815FE65EN3PBSH5BKRGNNXD=cant-access-marketplace 01H815FE65FR4ATDA4CVX2FW9N=something-went-wrong h_01JNK9HB2ZWQ78XK9B33QWHV49=my-ios-app other-information=outras-informa%C3%A7%C3%B5es h_01K7KSRWCB1Y89T21JFJR42VAJ=outras-informa%C3%A7%C3%B5es h_01K7KSPDSSG8CRCQB5V545Y12Z=product-line" />

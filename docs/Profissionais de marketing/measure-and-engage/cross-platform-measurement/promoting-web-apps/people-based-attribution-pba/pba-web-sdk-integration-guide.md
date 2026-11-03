---
title: Guia de integração do PBA Web SDK
metadata:
  keywords:
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-05-17T09:05:30Z'
  edited_at: '2026-08-19T00:23:05Z'
  id: 360001610038
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360001610038
---
> **At a glance:** Integre a AppsFlyer a sites usando o Web SDK para registrar e medir visitas, eventos, conversões e receitas.

![5107_Infographic_Web_S2S_759x270_option1.jpg](https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg)

## Guia de usuário e integração do web SDK

* A tag JavaScript do Web SDK:
  * faz parte da solução People-Based Attribution (PBA) para analisar as jornadas dos usuários em multi plataformas.
  * comunica as visitas e ações dos usuários no seu site à plataforma da AppsFlyer.
  * é um módulo de plug-in de site que não precisa de programação. É independente do sistema operativo e do browser do visitante do site.
  * Tamanho  40-60Kb.
* Implemente o Web SDK juntamente com o SDK mobile da AppsFlyer para registrar e mapear a atividade do usuário em seu aplicativo móvel e ambientes web.
* Os eventos que ocorrem fora do site podem ser registados com a <Anchor target="_blank" href="/marketers/pt/docs/web-server-to-server-events-api-for-pba-web-s2s">Web server-to-server events API</Anchor> (Web S2S)

## Selecionar um code snippet

Escolha o snippet que corresponde ao seu tipo de integração e requisitos de segurança. Duas opções estão disponíveis:

* [Web SDK padrão](#web-sdk-padrão): integração padrão.
* [Verificação avançada de SDK](#verificação-avançada-de-sdk): uma integração aprimorada que inclui segurança da cadeia de suprimentos para o Web SDK. Use-a para adicionar uma camada extra de segurança contra comprometimento de CDN, sequestro de DNS e ataques intermediários (MiTM).

> 🚧 **Important**
>
> **Importante!**
>
> Se você estiver fazendo a transição do Web SDK padrão para a verificação avançada do SDK, substitua o snippet existente pelo novo. O novo snippet não deve ser adicionado em conjunto com o snippet existente.

### Web SDK padrão

Use esse snippet para implementar a integração do Web SDK padrão. Insira-o perto do topo da tag  em todas as páginas onde você deseja que o SDK seja carregado.

<div id="standard-without-smart-banners" />

<Accordion title="Sem Smart Banners">

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        // Using the fetch API to send the user email to the server
        // and get the unique user id in return	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Thank You for Signing Up!</h1> 
     </body> 
</html>
```

</Accordion>

<div id="standard-with-smart-banners" />

<Accordion title="Com Smart Banners">

```html
<html>
<head>
    <!-- The Web SDK script loads first -->
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        };
    // This function stores the user email sent to the server after the user reaches the thank you page
    // The response from the server is a unique CUID that should be set using the web SDK setCustomerUserId method
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>Email</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

</Accordion>

### Verificação avançada de SDK

A verificação avançada de SDK adiciona segurança da cadeia de suprimentos ao Web SDK. Ela garante que o código executado nos navegadores dos seus usuários é exatamente o mesmo que a AppsFlyer publicou. O código-fonte do SDK em si é idêntico à integração padrão; apenas os mecanismos de entrega e verificação diferem.

A verificação avançada de SDK:

* Adiciona uma camada extra de segurança contra comprometimento de CDN, sequestro de DNS e ataques intermediários (MiTM).
* Adiciona aproximadamente 250ms ao tempo de carregamento do SDK.

Esse recurso é opcional. A integração padrão permanece totalmente disponível e é o padrão de mercado para analytics pixels de terceiros. A verificação avançada do SDK fornece uma camada adicional de proteção além do padrão.

Se o seu site impõe uma Política de Segurança de Conteúdo (CSP) usando nonce, consulte [Política de Segurança de Conteúdo (CSP)](#política-de-segurança-de-conteúdo-csp) em "Gerenciar privacidade" para acessar a variante nonce-extended do snippet.

<Accordion title="Sem Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<Accordion title="Com Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

## Integrar o web SDK no site

<div id="installation-and-integration" />

<Accordion title="Instalação e integração">

#### Considerações e ações necessárias

| Checklist da integração |
| --- |
| Para garantir o registro das visitas e dos eventos, o web SDK deve ser instalado em todas as páginas do site. |
| Coloque o snippet code [que você selecionou acima](#selecionar-um-code-snippet) para que ele carregue o mais cedo possível no escopo da página. Para isso, coloque o código perto do topo da tag do cabeçalho. |
| Se você estiver integrando o SDK usando o Google Tag Manager (GTM):<ul><li>Certifique-se de que o SDK é carregado uma vez por carregamento de página.</li><li>Configure o SDK para ativar assim que a página carregar usando a <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">priorização GTM.</Anchor></li></ul> |
| Você pode implementar o Web SDK **com** ou **sem** Smart Banners. Siga as instruções relevantes nas seções a seguir. |
| Requisitos obrigatórios de integração<ul><li>Gravação de visita</li><li>Gravação de evento</li><li>Definir o [Customer User ID](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid) (CUID) : Se você não tiver um CUID, entre em contato com seu CSM para conversar sobre alternativas.</li></ul>Valide a integração usando a <Anchor target="_blank" href="/marketers/pt/docs/test-pba-web-sdk-integration">ferramenta de teste</Anchor> |

**Antes de começar**:

* Verifique com o profissional de marketing se o <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings">pacote de marca</Anchor> foi criado.
* Para obter orientações adicionais, consulte o <Anchor target="_blank" href="/marketers/pt/docs/onboarding-guide-to-people-based-attribution">guia de integração de PBA</Anchor>.
* Considere: se você já possui o Web SDK específico para Smart Banners, remova-o e substitua-o pelo Web SDK para Smart Banners e PBA. Não adicione somente o Web SDK para PBA.

**Faça o seguinte:**

* Obter a chave de desenvolvimento web do web SDK. **Atenção!** Esta não é a mesma chave usada pelos aplicativos mobile.
  * **Para obter a chave do desenvolvedor web:**
    1. Na AppsFlyer, no menu superior, selecione a aba **Meus Aplicativos** .
    2. Clique em **Visualizar pacotes de marca.**
    3. Copie a chave de desenvolvimento web necessária **. (WEB\_DEV\_KEY)**
* Se você implementar Smart Banners, obtenha a chave Smart Banner.
  * **Para obter a chave Smart Banner:**
    1. Na AppsFlyer, no menu lateral, vá para **Engajamento**> **Web-to-app** > **Smart Banners.**
    2. Copie a **chave do Smart Banner** necessária.
* Permissões para adicionar scripts a etiquetas de cabeçalho no site.
* Se você usar o Google Tag Manager, ele deve estar integrado no site.

**Proceda à integração do SDK web usando uma das seguintes opções.**

<Tabs>
<Tab title="Nativo">

#### Trecho de código JavaScript

Integrar o SDK da web usando um dos seguintes métodos.

#### **Para instalar o web SDK sem Smart Banners:**

1. Repita o procedimento a seguir em todas as páginas do seu site.
2. No trecho de código a seguir, substitua o `WEB_DEV_KEY` usando a chave especificada nos pré-requisitos.
3. Cole o code snippet [que você selecionou acima](#selecionar-um-code-snippet) na head tag do seu site. Cole-o perto do topo da etiqueta de cabeçalho.

#### **Para implementar o Web SDK com Smart Banners:**

1. Repita o procedimento abaixo em todas as páginas do seu site.
2. No code snippet [que você selecionou acima](#selecionar-um-code-snippet), substitua `WEB_DEV_KEY` e `YOUR_BANNER_KEY` usando as chaves especificadas nos pré-requisitos.
3. Cole esse code snippet na head tag do site. Cole-o perto do topo da etiqueta de cabeçalho.

</Tab>

<Tab title="Google Tag Manager">

**Para implementar o Web SDK com o Google Tag Manager (GTM):**

1. <Anchor target="_blank" href="https://developers.google.com/tag-manager/quickstart">Acesse o Google Tag Manager.</Anchor>
2. Crie uma nova tag para o Web SDK da AppsFlyer.

   ![Crie uma nova tag para o SDK Web da AppsFlyer no Google Tag Manager](https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png)
3. Selecione o tipo de tag **HTML personalizada**.
4. Dê um nome significativo à etiqueta.
5. Siga um dos procedimentos abaixo:
   * Se você integrando o Web SDK **sem** Smart Banners:
     1. Cole o code snippet [que você selecionou acima](#selecionar-um-code-snippet) na janela **Configuração da Tag**.
     2. No trecho de código, substitua `WEB_DEV_KEY` usando a chave mencionada nos pré-requisitos.
   * Se estiver integrando o Web SDK **com** Smart Banners:
     1. Cole o code snippet [que você selecionou acima](#selecionar-um-code-snippet) na janela **Configuração da Tag**.
     2. No trecho de código, substitua `WEB_DEV_KEY` e `YOUR_BANNER_KEY`usando as chaves mencionadas nos pré-requisitos.
6. Clique em **Guardar**.
7. Siga um dos procedimentos abaixo:
   * **Para adicionar o gatilho a todas as páginas:**
     1. Clique em **Adicionar gatilho**.

        ![gtm-af-tag-sdk-trigger.png](https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png)
     2. Selecione **Todas as páginas**.
     3. Clique em **Salvar.**
     4. Digite um nome para a tag e clique em **Salvar**.  
        Você concluiu o procedimento.
   * **Para adicionar o gatilho a páginas específicas:**
     1. Clique em **Salvar tag**.
     2. Na janela principal do GTM, selecione Gatilhos . Clique em **Novo**.
     3. Clique no ícone de caneta.
     4. Escolha o tipo de gatilho **Visualização de página**.  
        ![PBAselectTrigger_us-en.jpg](https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg)
     5. Selecione **Algumas visualizações de página.**
     6. Defina a página e as condições de gatilho conforme necessário.
     7. Clique em **Salvar.**
     8. Associe o gatilho à tag AppsFlyer Web SDK. Para isso:
        1. Na janela principal do GTM, selecione Gatilhos.
        2. Selecione a etiqueta que criou anteriormente.
        3. No painel de gatilho, clique na caneta.
        4. Selecione o gatilho da visualização da página que criou anteriormente.

           ![Selecione o gatilho de visualização de página criado anteriormente no Google Tag Manager](https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png)
        5. Clique em **Salvar**.

</Tab>

<Tab title="Adobe Launch Tag Manager">

1. [Crie uma propriedade na Adobe Experience Cloud](/docs/pba-web-sdk-integration-guide#create-a-property-in-adobe-experience-cloud)
2. [Adicione o Web SDK à propriedade do Adobe Launch](/docs/pba-web-sdk-integration-guide#add-the-web-sdk-to-the-adobe-launch-property)
3. [Adicione a etiqueta do Adobe Launch ao site](/docs/pba-web-sdk-integration-guide#add-the-adobe-launch-tag-to-the-website)
4. [Publique o ambiente do Adobe Launch](/docs/pba-web-sdk-integration-guide#publish-the-adobe-launch-environment)

<div id="create-a-property-in-adobe-experience-cloud" />

<Accordion title="Crie uma propriedade na Adobe Experience Cloud">

![adobe_create_property.png](https://files.readme.io/1f97d619d5fdfe47b1dd1a2e17c0169e939c32bcda62580ba259d6e86f61d6c2-20260884824209.png)

1. Acesse **Adobe Experience Cloud** > **Inicialização**.
2. Em **Adobe Experience Cloud Launch**, clique em **Ir para Inicialização**.
3. Clique em **Nova propriedade**.
4. Nomeie a propriedade.
5. Em **Plataforma**, selecione **Web**.
6. Insira o domínio do seu site.
7. Clique em **Salvar**.

</Accordion>

<div id="add-the-web-sdk-to-the-adobe-launch-property" />

<Accordion title="Adicione o Web SDK à propriedade do Adobe Launch">

<Image alt="web_property_rules.png" src="https://files.readme.io/5f592f3ce1f5b319c8f6f96a6235618d884a4faccb1387b1f22c1fd2ce662d15-360006168098.png" width="491px" />

1. Na página **Minha propriedade da web**, selecione a aba **Regras**.
2. Nomeie a regra. Recomendado para uso, **Carregar Web SDK**.
3. Na seção **IF**, em **EVENTOS**, clique em **+Adicionar**.
   * Em **Tipo de evento**, selecione **Core - DOM Ready**.
   * Clique em **Manter alterações**.
4. Na seção **THEN**, em **Ações**, clique em **+Adicionar** .
   * Em **Tipo de ação** > **Código personalizado**.
   * Selecione **JavaScript** > **Abrir Editor** e cole o trecho do código do SDK web **sem as tags de &lt;script>**.
   * Clique em **Manter alterações** para fechar o editor de código.
5. Clique em **Salvar**.

</Accordion>

<div id="add-the-adobe-launch-tag-to-the-website" />

<Accordion title="Adicione a etiqueta do Adobe Launch ao site">

![adobe_tag.png](https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png)

1. Na página de **Propriedade da minha web**, selecione a aba **Ambientes** .
2. Encontre a linha com o ambiente no qual você deseja publicar (desenvolvimento ou produção).
   * No título **INSTALAÇÃO**, clique no ícone de caixa na linha relevante; geralmente, esse é um ambiente de produção.
   * Consulte a seção sobre como publicar o ambiente do **Adobe Launch**.
3. Na caixa de diálogo **Instruções de instalação na web**:
   * Copie o trecho de código de script.
   * Feche a caixa de diálogo.
4. Cole o trecho de código na tag &lt;head> do site.

</Accordion>

<div id="publish-the-adobe-launch-environment" />

<Accordion title="Publique o ambiente do Adobe Launch">

![adobe_publishing_env.png](https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png)

1. Na página **Propriedade da minha web**, acesse a aba **Publicação** .
2. Na seção  **Desenvolvimento**, clique em **Adicionar nova biblioteca.**
   * Nomeie a biblioteca e escolha um ambiente.
   * Em **ALTERAÇÕES DE RECURSO**, clique em **Adicionar um recurso.**
   * Clique em **Regras** > **Carregar SDK web** > **Mais recentes** > **Selecionar e criar uma nova revisão**.
   * Clique em **Salvar**.
3. Na seção **Desenvolvimento**:
   * Ao lado da biblioteca recém-criada, clique no menu Ação (3 pontos) > selecione **Construir para Desenvolvimento**.
   * Clique no menu de ação novamente > selecione **Enviar para aprovação**.
4. Na seção **Submetido**:
   * Clique no menu de ação > selecione **Construir para Staging**.
   * Clique novamente no menu de ação > selecione **Aprovar para publicação**.
5. Abaixo da seção **Aprovado**:
   * Clique no menu de ação > selecione **Construir e publicar em Production.**
   * O processo está concluído.

</Accordion>

Quando o site é carregado num dispositivo móvel, o criativo ativo aparece no banner. Para exibir o banner em páginas específicas ou de acordo com as ações do usuário, consulte as <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Regras do Adobe Launch</Anchor>.

</Tab>
</Tabs>

</Accordion>

<div id="ensure-that-the-sdk-is-working" />

<Accordion title="Certifique-se de que o SDK está funcionando">

Depois de instalado, verifique se o Web SDK da AppsFlyer é chamado pelo navegador do visitante e se as mensagens estão sendo enviadas. Isto é feito examinando a conexão de rede de mensagem relatada no navegador.

**Para garantir que o SDK é carregado e está funcionando:**

1. Acesse o site.
2. Abra as ferramentas de desenvolvimento do navegador.

   ![WebSDK_us-en.jpg](https://files.readme.io/5550f0ee8c1a5852a983e6482cb0489696b669ffe5fade49d2308ee32f57201b-360009548497.jpg)
3. Vá para a aba (A) **Network**.
4. Atualize a página.
5. Filtre por (B) **wa.appflyer**.
6. Selecione a mensagem **events** (C).
7. Na aba de cabeçalhos, (D) certifique-se de:
   * O **URL de solicitação** é wa.appsflyer.com/events.
   * parâmetro de consulta site\_id= `WEB_DEV_KEY`.
   * (E) **o código de status é 200**.
8. Verifique se o valor de site\_id é igual ao valor de `WEB_DEV_KEY` nas configurações do pacote de marcas:
   1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **Pacotes de marca**.
   2. Clique na **chave Web dev,** o que permite copiar a chave.
   3. Cole a chave em qualquer local (nova aba do navegador, bloco de notas) para exibir a chave.
   4. Verifique se o site\_id e `WEB_DEV_KEY` correspondem.
9. Certifique-se de que o SDK é carregado apenas uma vez. O carregamento múltiplo de SDK pode fazer com que o SDK deixe de funcionar.

</Accordion>

<div id="sending-events-optinoptout" />

<Accordion title="Eventos de envio opt-in/opt-out">

![5578-VistiorPrivacyOptIn_us-en.png](https://files.readme.io/cd6cbcaeb7f831f4efe74a9a6c6b20d5095602e7edf4dd38becd90864e73c2fb-360010263157.png)

O Web SDK envia dados de eventos do visitante para a AppsFlyer. É possível controlar, parar ou iniciar o envio de eventos, conforme descrito nesta secção.

Considere:

* **Definição do estado inicial do SDK**: Determina se o SDK envia eventos ao carregar inicialmente a página web ou se o SDK tem de esperar até que seja dado um comando explícito para começar a enviar eventos. A definição está contida no trecho da web.
* **Controle explícito:** Use para parar ou iniciar o envio de eventos. Por exemplo, se você implementar banners de opt-in/opt-out de dados (também conhecidos como banners de consentimento de cookies), integre os comandos explícitos nos controlos do banner para iniciar e parar o envio de eventos. O controle explícito tem prioridade sobre a definição do estado inicial do SDK e usa cookies primários persistentes com as seguintes características:
  * Definido no domínio do site.
  * Expira após um período definido pelo Web SDK ou conforme determinado pelo navegador. Após a expiração do cookie, o Web SDK reverte para a configuração do estado inicial.
  * O cookie do Web SDK não causa interferência e está sempre sujeito às configurações de cookies específicas do navegador.

#### Definição do estado inicial do SDK

| Configuração | Trecho necessário |
| --- | --- |
| [Padrão] Enviar eventos | Faça a seguinte alteração no trecho do Web SDK. Se necessário, adicione o parâmetro measurementStatus:<br /><br />Defina measurementStatus=true<br /><br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:true}` |
| Não envie eventos | Faça a seguinte alteração no trecho do Web SDK. Se necessário, adicione o parâmetro measurementStatus:<br /><br />Defina measurementStatus=false  <br />  <br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:false}` |

#### Controle explícito:

| Opção | Comando |
| --- | --- |
| Começar a enviar eventos (opt-in) | `window.AF_SDK.PLUGINS.PBA.enableMeasurement()` |
| Pare de enviar eventos (opt-out) | `window.AF_SDK.PLUGINS.PBA.disableMeasurement()` |

</Accordion>

<div id="implement-a-content-security-policy-csp-policy" />

<Accordion title="Implementar uma política de Política de Segurança de Conteúdo (CSP)">

Se o seu site exige protocolos rigorosos de segurança e de privacidade de dados, use os seguintes mecanismos para configurar a maneira como o Web SDK interage com seu ambiente e seus dados.

#### Política de Segurança de Conteúdo (CSP)

Se o seu site exige que o JavaScript seja protegido por uma CSP, o Web SDK é compatível com duas abordagens diferentes, a depender da configuração da sua CSP.

* **CSP usando self**: Adicione `https://websdk.appsflyersdk.com` à sua lista de permissões `script-src`. Isso funciona tanto para o Web SDK padrão quanto para a Verificação avançada do SDK.
* **CSP usando nonce**: Se sua política usar `script-src 'nonce-...'`, você pode usar [a variante nonce-extended da Verificação avançada do SDK](#verificação-avançada-de-sdk-com-snippets-de-nonce-csp). Esse mecanismo encaminha o nonce para todas as três tags de script exigidas pelo processo de verificação. Substitua `{{CSP_NONCE}}` pelo valor nonce gerado pelo servidor.

A tabela abaixo mostra quais políticas CSP são compatíveis com a variante nonce-extended.

| Política | Funciona? | Observações |
| --- | --- | --- |
| `script-src 'self'` | Não | Origem de CDN externa não permitida; script inline também é bloqueado. |
| `script-src 'self' https://websdk.appsflyersdk.com` | Parcial | Permite carregador e SDK, mas o script de configuração inline ainda está bloqueado. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | Sim | Nonce cobre script inline e carregador; a tag SDK recebe nonce encaminhado pelo carregador. |
| `script-src 'nonce-...' 'strict-dynamic'` | Sim (recomendado) | Nonce cobre script inline e carregador; `strict-dynamic` propaga confiança para a tag SDK inserida dinamicamente. Nenhuma origem de CDN necessária na lista de permissões. |

Compatibilidade com a política CSP

#### Verificação avançada de SDK com snippets de nonce CSP

<div id="advanced-verification-without-smart-banners" />

<div id="nonce-without-smart-banners" />

<Accordion title="Sem Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="advanced-verification-with-smart-banners" />

<div id="nonce-with-smart-banners" />

<Accordion title="Com Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

</Accordion>

<div id="discard-query-params" />

<Accordion title="Descartar parâmetros de consulta">

Se seus parâmetros de consulta contiverem dados que você não deseja que a AppsFlyer registre, você poderá instruir a plataforma AppsFlyer a descartar alguns ou todos os parâmetros de consulta. Ao fazer isso, eles não ficam disponíveis em dados brutos ou relatórios.

Você pode implementar os métodos descritos em relação a URLs, referenciadores e header\_referer.

#### Consultar opções de descarte

| Método | Descrição |
| --- | --- |
| Descartar todos os parâmetros de consulta | Anexe `af_url=true` ao url |
| Descartar parâmetros de consulta especificados | Ao definir uma máscara de parâmetros de consulta, você especifica quais parâmetros serão descartados.  Defina a máscara de descarte usando `af_url_mask=param` onde param é o nome do parâmetro.<br /><br />Exemplo:<br /><br />**URL com máscara:**<br /><br />`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`<br /><br />**URL após descartar:**<br /><br />`param1=value1&af_url_mask=param2;param3` |

</Accordion>

## Princípios do registro de eventos

<div id="conversion-and-standard-events" />

<Accordion title="Eventos de conversão e padrão">

* Os eventos do usuário são registrados pelo SDK, que envia o evento para a plataforma AppsFlyer.
* Usando a lista de <Anchor target="_blank" href="/marketers/pt/docs/pba-brand-bundles-and-settings#web-event-settings">eventos de conversão</Anchor>, definida pelo profissional de marketing, a AppsFlyer faz uma divisão entre eventos padrão e de conversão.
* Os dados dos eventos de conversão estão disponíveis nos painéis de controle de PBA.
* Os dados de conversão e eventos padrão estão disponíveis nos <Anchor target="_blank" href="/marketers/pt/docs/pba-raw-data-reports">relatórios de dados brutos.</Anchor>

### Eventos de conversão

* Os eventos de conversão fornecem insights sobre os seus esforços comerciais e de marketing. Os eventos de conversão incluem compras, downloads, inscrições e assinaturas.
* O PBA atribui os eventos de conversão à fonte de media que levou o usuário a visitar o site.
* Ao identificar o canal de mídia atribuído, é possível medir e diferenciar a qualidade dos usuários trazida por diferentes canais de mídia.
* Os eventos de conversão são usado para registrar as receitas e calcular o ROI.
* Use-os para comparar o orçamento de anúncios para canais de mídia específicas com as receitas geradas pelos usuários que provêm desses canais de mídia.

### Eventos padrão

* Os eventos padrão são usados para validar a jornada do usuário e os funis que geram conversões.
* Use-os para medir a atividade do usuário e destacar os canais de mídia que atraem usuários engajados.
* Registre a atividade do usuário para marcar os usuários para campanhas de reengajamento.

### Eventos de registro

Acione o Web SDK para registrar eventos quando determinadas condições são cumpridas, por exemplo, quando uma página inicial é carregada ou quando os usuários interagem com elementos do site. Ver [exemplos de registro de eventos](#recording-events::f1e16eae).

</Accordion>

<div id="identifying-users-using-customer-user-id-cuid" />

<Accordion title="Identificação de usuários através do ID de usuário do cliente (CUID)">

* Os usuários da web são identificados na AppsFlyer usando o CUID único que você atribui a eles. Normalmente, o CUID é gerenciado pelos seus servidores backend.
* Use o mesmo valor CUID que usa no ambiente móvel. Desta forma, é possível ter uma visão holística da atividade do usuário em multi plataformas. A função no SDK mobile é setCustomerUserId (<Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid#configuração-do-cuid">iOS</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid#configuração-do-cuid">Android, Unity</Anchor>).
* Para definir o CUID no Web SDK:
  * Defina o CUID no primeiro momento em que tiver acesso a ele. Na maioria das vezes, isto significa que é necessário esperar que o usuário se identifique através do login ou da inscrição.
  * Acione a chamada JavaScript para setCustomerUserId() como mostrado no exemplo a seguir.   
    Atenção! Envie o CUID como uma string mesmo que seja um número. Não se esqueça das aspas.
* Se você implementar a Web S2S, talvez precise notificar o PBA quando <Anchor target="_blank" href="/marketers/pt/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method">associar</Anchor> um CUID a um ID de visitante da web no seu backend.
* Os CUID não devem conter <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid#cuid-e-privacidade">informações pessoais diretamente identificáveis</Anchor> , como um número de telefone ou um endereço de email.

**Exemplo: definir o CUID**

```javascript
// Associate all current user web events to distinct ID 663274 AF('pba', 'setCustomerUserId' , '663274')
```

</Accordion>

<div id="web-sdk-event-parameters" />

<Accordion title="Parâmetros de eventos do Web SDK">

| Nome do parâmetro | Obrigatório | Descrição |
| --- | --- | --- |
| eventType | Sim | Tipo de evento<br /><br />Formato: String<br /><br />Preencha sempre este parâmetro com EVENT.<br /><br />Exemplo: eventType: "EVENT" |
| eventName | Sim | Nome do evento<br /><br />Formato: String<br /><br />Exemplo: Compra, Assinatura |
| ~~eventCategory~~ | Não | Este parâmetro está descontinuado e será removido do sistema em data a ser anunciada. No lugar dele, use o parâmetro eventValue. |
| ~~eventLabel~~ | Não | Este parâmetro está descontinuado e será removido do sistema em data a ser anunciada. No lugar dele, use o parâmetro eventValue. |
| eventRevenue | Não | Receita atribuída a um evento de conversão<br /><br />Formato: Número flutuante |
| eventRevenueCurrency | Não | Moeda da receita<ul><li>Código de moeda <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> de 3 caracteres.</li><li>Predefinição: USD</li></ul>Formato: String |
| Valor do evento | Não | Mapa de parâmetros de eventos que descrevem o evento. Use este parâmetro para enviar eventos avançados in-app como SKU do produto, preço do item de linha.<br /><br />Formato: JSON<br /><br />**Exemplo:** Para enviar o SKU ABC123, de cor azul e preço unitário de $3,99<br /><br />`{"sku": "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}`<br /><br />**Limitação:** 1000 caracteres. Não exceda este valor, será truncado. |

</Accordion>

<div id="recording-event-scenarios" />

<Accordion title="Registrar cenários de eventos">

Exemplo de evento

```javascript
// purchase event of shoes with associated revenue AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

Os eventos que você envia dependem da natureza do seu aplicativo web. Por exemplo, um aplicativo de loja online requer um conjunto de eventos diferente do de um canal de notícias. Veja os cenários que a seguir para ter uma noção dos eventos que você deve enviar e quando.

#### Loja online

Suponha que está gerenciando uma loja online. Alguns eventos padrão que talvez você queira registrar são:

* Pesquisa: evento padrão
* Adicionar ao carrinho: evento padrão
* Remover do carrinho: evento padrão
* Compra: evento de conversão

Canal de notícias

Suponhamos que está gerenciando um canal de notícias. Alguns eventos que talvez você queira registrar são:

* Inscrição: evento de conversão
* Assinatura de compras: evento de conversão

</Accordion>

<div id="ensuring-that-events-are-sent" />

<Accordion title="Garantir o envio de eventos">

Esta parte destina-se a desenvolvedores web.

<Anchor target="_blank" href="/marketers/pt/docs/test-pba-web-sdk-integration">Teste a integração do Web SDK do PBA:</Anchor> visualize eventos de teste em tempo real.

**Para garantir que os eventos sejam enviados para a AppsFlyer**:

1. Abra o site.
2. Abra as ferramentas de desenvolvimento do navegador.
   * <Anchor target="_blank" href="https://developers.google.com/web/tools/chrome-devtools/open#console">Como abrir as ferramentas de desenvolvimento no Chrome</Anchor>
   * <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html">Como abrir as ferramentas de desenvolvimento no Safari</Anchor>
3. Mude para a aba Network.
4. Acione o evento.
5. Filtrar por mensagem.

   ![pba_af_event.png](https://files.readme.io/394f43890d1aaf09114054a3bca1a003178526e768a5da0b554dbc8d63ef1eb4-360003502238.png)
6. Procure uma solicitação de network que comece com o destino wa.appsflyer.com (veja a imagem abaixo).
7. Certifique-se de que:
   1. O código de status é 200.
   2. A carga útil do pedido está alinhada com os parâmetros do evento.

</Accordion>

## Exemplos

<div id="recording-events::f1e16eae" />

<Accordion title="Eventos de registro">

O código fornecido serve apenas para fins ilustrativos. Não use este código tal como está.

* Pressupostos: O Web SDK já está carregado pela página no momento em que o evento é enviado.
* Os cenários de exemplo contêm o código para registrar eventos quando:
  * uma página inicial é carregada.
  * os usuários interagem com o site.

<Tabs>
<Tab title="Gravação nativa de eventos">

**Registro de eventos quando uma página inicial é carregada**

* Você tem uma página de assinatura de newsletters e pretende registrar as assinaturas.
* Você também pode criar uma página de agradecimento e redirecionar os usuários para essa página depois que eles se inscrevem.

```html
<html>\n    <head>\n        <!-- Suponha que o servidor retorne uma resposta com detalhes sobre o usuário recém-inscrito -->\n        <!-- Como alternativa, você pode extrair dados do localStorage ou de cookies,\n            caso os dados tenham sido definidos em qualquer um deles durante o processo de inscrição\n        -->\n        <script>window.onload = function(){\n            AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion', eventValue: {'label' : 'newspaper'}, eventName: 'subscription',}); } </script> </head> <body> <h1>Obrigado por se inscrever em nossa newsletter</h1> </body> </html>
```

* O código anterior contém uma página HTML básica. A página web precisa carregar o Web SDK para que você possa enviar eventos.
* Depois que a página é carregada, após o usuário ser redirecionado para ela, o método de carregamento da janela chama o método AF() para enviar o evento de assinatura para a AppsFlyer.

**Registro de eventos quando os usuários interagem com o site**

* Você tem um site de eCommerce e deseja registrar eventos de checkout.
* Quando o usuário clica no botão de checkout, o Web SDK envia um evento para a AppsFlyer.

```html
<html>
<head>
    <!-- Suponha que os dados sobre os produtos no carrinho de compras
    estejam armazenados no localStorage -->
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Carrinho de compras</h1>
    <h2>Camisa</h2>
    <p>
        <ul>
            <li>Cor: Azul</li>
            <li>Quantidade: 2</li>
            <li>Preço: $20</li>
        </ul>
    </p>
    <h2>Calça</h2>
    <p>
        <ul>
            <li>Cor: Preto</li>
            <li>Quantidade: 3</li>
            <li>Preço: $15</li>
        </ul>
    </p>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

O código anterior mostra uma página HTML básica. A página web precisa carregar o Web SDK para que você possa enviar eventos.

* Depois que a página é carregada, ela vincula um ouvinte de clique ao botão **Checkout**.
* Quando o usuário clica no botão **Checkout**, a função de retorno de chamada:
  * busca dados de localStorage.
  * chama o método AF() e passa dados para ele.
* O método AF() envia o evento para a AppsFlyer.

</Tab>

<Tab title="Gravação de eventos do Gerenciador de tags">

**Registro de eventos quando uma página inicial é carregada**

* Você tem uma página de assinatura de newsletters e pretende registrar as assinaturas bem-sucedidas.
* Você configurou uma página de agradecimento para a qual os usuários são redirecionados depois de se inscreverem com sucesso.

1. Crie uma página de agradecimento

   ```html Markup
   <html>\n<head>\n    <script>\n         // O Google Tag Manager carrega o SDK web\n        <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':\n        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],\n        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=\n        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);\n        })(window,document,'script','dataLayer','GTM-XXXX');\n    </script>\n     <script>\n        // Suponha que o servidor retorne uma resposta com detalhes sobre o usuário recém-inscrito\n        function getResponseFromServer() {\n            return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })\n        }\n        // Como alternativa, você pode extrair dados do localStorage ou de cookies,\n        // caso os dados tenham sido definidos em qualquer um deles durante o processo de inscrição\n        localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));\n    </script>\n</head>\n<body>\n    <h1>Obrigado por se inscrever em nossa newsletter</h1>\n</body>\n</html>
   ```

   O código anterior carrega o GTM que, por sua vez, carrega o Web SDK. Depois disso, duas outras ações ocorrem no script. Uma é uma função que obtém uma resposta do servidor com detalhes do usuário. A outra define dados para armazenamento local. GTM tem acesso à função e ao localStorage. Você pode chamar a função e acessar localStorage usando GTM.
2. Adicione uma nova tag para atribuir assinaturas após o carregamento da página de agradecimento

   ![Adicione uma nova tag para atribuir assinaturas no Google Tag Manager](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
3. Dê um nome distinto à tag e selecione a opção de tipo de tag **HTML personalizado**.
4. Coloque o seguinte código no **HTML personalizado**.

   ```html
   <script> AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'}); </script>
   ```

   ![gtm_tag_after_subscribe.png](https://files.readme.io/6cf080f94a97a7f38c50899a93d154320995e91f60963c075a5dd03b3a080408-360003515298.png)
5. Expanda o controle **Configurações avançadas** e, em seguida, o controle **Sequenciamento de tags** abaixo da área de texto e certifique-se de que ele esteja configurado para disparar a conversão após a execução da tag.

   ![Configurações de sequenciamento de tags no Google Tag Manager](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. Para disparar a tag de conversão, defina um gatilho. No exemplo, o gatilho é acionado ao carregar a página de agradecimento.

   ![Acionador configurado para disparar no carregamento da página de agradecimento](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

**Registro de eventos quando os usuários interagem com o site**

* Você tem um site de eCommerce e deseja registrar eventos de checkout.
* Depois que o usuário clica no botão de checkout, o Web SDK envia um evento para a AppsFlyer.

1. Configure uma página de checkout

   ```html Markup
   <html>\n<head>\n    <script>\n        // O Google Tag Manager carrega o SDK web\n        <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':\n        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],\n        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=\n        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);\n        })(window,document,'script','dataLayer','GTM-XXXX');\n    </script>\n</head>\n<body>\n    <h1>Carrinho de compras</h1>\n    <h2>Camisa</h2>\n    <p>\n        <ul>\n            <li>Cor: Azul</li>\n            <li>Quantidade: 2</li>\n            <li>Preço: $20</li>\n        </ul>\n    </p>\n    <h2>Calça</h2>\n    <p>\n        <ul>\n            <li>Cor: Preto</li>\n            <li>Quantidade: 3</li>\n            <li>Preço: $15</li>\n        </ul>\n    </p>\n    <button id='checkout'>Checkout</button>\n</body>\n</html>
   ```

   O código anterior carrega o Web SDK usando GTM. O resto é simplesmente HTML que imita uma página de carrinho de compras. Observe o botão **Checkout** que contém o ID checkout. É necessário ao configurar o GTM para lidar com um clique nesse botão.
2. No GTM, clique em **Variáveis**, clique em **Configurar** e marque **Clicar element** na lista de **Variáveis internas.**  

   ![gtm-create-variable.png](https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png)
3. Crie uma nova variável, atribua um nome significativo e escolha o tipo Todos os elementos.  

   ![gtm-checkout-all-elements.png](https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png)
4. Na configuração de gatilho, escolha **Alguns cliques** e **Clicar elemento**, que **corresponda ao seletor CSS** de #checkout.  

   ![gtm-checkout-click-elememt.png](https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png)
5. Crie uma nova tag para a ação de checkout, escolha o tipo HTML personalizado e defina o gatilho como gatilho de checkout.

   ```html
   <script>
    AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'}); </script>
   ```

   ![gtm-checkout-tag.png](https://files.readme.io/8d3f99dcd3c3ff8df9e6fc13076b798237b86f8cbc5bbd26f349fa9948edb0d6-360003431857.png)

</Tab>
</Tabs>

* Certifique-se de que a tag das funções do Web SDK seja carregada antes de o evento ser acionado.
* Não envie caracteres especiais nos valores dos eventos, como símbolos de moeda no valor da receita.
* As strings de valor devem ter menos de 50 caracteres.

</Accordion>

<div id="setting-customer-user-id-after-signup" />

<Accordion title="Definir o ID de usuário do cliente após a inscrição">

O código fornecido nestes exemplos é apenas para referência. Não use este código tal como está. Se você não tiver certeza de como usar este código, consulte o seu desenvolvedor Web. 

Pressuposto: O Web SDK é carregado pela página antes de o evento ser enviado; não carregue o SDK novamente.

Cenário do usuário:

* Um usuário inscreve-se no seu site.
* O código do site recolhe os dados do usuário e envia-os para o seu servidor.
* O servidor gera um CUID único para o usuário.
* Na página de agradecimento após o registro, você consulta o servidor para obter o novo CUID.
* Usando a resposta do servidor, você define o CUID da AppsFlyer usando o método setCustomerUserId() do Web SDK.

<Tabs>
<Tab title="Nativo">

Crie uma página de inscrição:

```html Markup
<html>
<head>
    <!-- The Web SDK script loads first -->
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        };
    // Esta função armazena o e-mail do usuário enviado ao servidor depois que o usuário chega à página de agradecimento
    // A resposta do servidor é um CUID exclusivo que deve ser definido usando o método setCustomerUserId do SDK web
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Cadastre-se</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Nome</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>E-mail</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

O código anterior acima é um formulário de registro simples. Quando o formulário é enviado, o e-maill é armazenado em localStorage. Quando o usuário chega à página de agradecimento, o endereço de e-mail é enviado para o servidor para gerar o CUID único para o endereço de e-mail.

Configure uma página de agradecimento para os usuários que se inscrevem:

```html Markup
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        // Usando a API fetch para enviar o e-mail do usuário ao servidor
        // e receber o ID exclusivo do usuário em resposta	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Obrigado por se cadastrar!</h1> 
     </body> 
</html>
```

O código usa a API fetch. Ele envia ao servidor o endereço de e-mail inserido pelo usuário. Partindo do princípio de que o servidor cria um usuário com um CUID único aquando da inscrição, o envio do endereço de e-mail para o servidor destina-se a receber um CUID único. O servidor responde com um CUID único e este CUID único é o valor que é passado com o método setCustomerUserId.

</Tab>

<Tab title="Google Tag Manager">

1. Crie uma página de inscrição:

   ```html Markup
   <html>
   <head>
       <script>
            // O Google Tag Manager carrega o SDK web
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({
                   'gtm.start':
                       new Date().getTime(), event: 'gtm.js'
               }); var f = d.getElementsByTagName(s)[0],
                   j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true; j.src =
                       'https://www.googletagmanager.com/gtm.js?id=' + i + dl; f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');

       // Esta função armazena o e-mail do usuário para ser enviado ao servidor depois que o usuário chega à página de agradecimento
       // a resposta do servidor é um CUID exclusivo que deve ser usado no método setCustomerUserId do SDK web
           function storeUserEmail (){
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Cadastre-se</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Nome</label>
               <input type="text" name="name" id="name"></div>
           <br />
           <div> <label>E-mail</label>
               <input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```

   O código acima é um formulário de registro simples. Quando o formulário é enviado, o endereço de e-mail é armazenado em localStorage. Quando o usuário chega à página de agradecimento, o endereço de e-mail é enviado para o servidor para obter o CUID único para esse e-mail.
2. Configure uma página de agradecimento para os usuários que se inscrevem:

   ```
   (t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
   t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
   o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
   p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
       </script>
       <script>
           // usando a API fetch para enviar o e-mail do usuário ao servidor
           // e receber o ID exclusivo do usuário em resposta 
           window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
                  res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
           } </script> 
       </head>
       <body> 
               <h1>Obrigado por se cadastrar!</h1> 
        </body> 
    </html>
   ```

   O código anterior é uma página de agradecimento com um gatilho GTM que envia ao servidor o endereço de e-mail fornecido pelo usuário no formulário de inscrição.  
   Supondo que na inscrição, o servidor crie um usuário com um CUID exclusivo.  
   O envio do email para o servidor tem como objetivo receber um CUID exclusivo.  
   O servidor responde com um CUID exclusivo que é enviado usando o método setCustomerUserId().  
   Continue este procedimento para criar o gatilho e a aba.
3. Adicione uma nova tag para atribuir assinaturas após o carregamento da página de agradecimento. ![Adicione uma nova tag para atribuir assinaturas no Google Tag Manager](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. Atribua um nome distinto à tag e selecione a opção de tag do tipo “HTML personalizado” ![GoogleTag.jpg](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```html
   <script>
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
            res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
   </script>
   ```
5. Expanda o controle **Configurações avançadas** e, em seguida, o controle **Sequenciamento de tags** abaixo da área de texto e certifique-se de que ele esteja configurado para disparar a conversão após a execução da tag

   ![Configurações de sequenciamento de tags no Google Tag Manager](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. Defina um gatilho para a tag de conversão para indicar quando a tag de conversão deve ser acionada (no exemplo abaixo, é acionada no carregamento da página "Obrigado")

   ![Acionador configurado para disparar no carregamento da página de agradecimento](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Tab>
</Tabs>

A função setCustomerUserId pode ser enviada em qualquer fase do fluxo do utilizador, por exemplo, após o início de sessão e a inscrição do usuário. A AppsFlyer usa o CUID mais recente enviado para atualizar o usuário atualmente observado para pontos de contacto e eventos passados ou futuros.

Use o mesmo valor de CUID que você usa na função setCustomerUserId no app mobile (consulte setCustomerUserId mobile para: <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid#configuração-do-cuid">iOS</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid#configuração-do-cuid">Android</Anchor> e Unity)

</Accordion>

## Informações adicionais

<div id="web-sdk-cookies" />

<Accordion title="Cookies Web SDK">

Os cookies listados na tabela que a seguir são definidos ou usados pelo Web SDK no seu site.

Na tabela são utilizadas as seguintes abreviaturas:

* AMP: Páginas AMP (accelerated mobile pages)
* CDN: Rede de distribuição de conteúdo
* 3PC: Cookies de terceiros

| Nome do cookie | Domínio | Duração | Quando usado | Detalhes |
| --- | --- | --- | --- | --- |
| afUserid | Domínio do seu site | 395 dias | não AMP | Identifique um usuário no contexto de eventos de carregamento e navegação da web |
| AF\_SYNC | Domínio do seu site | 1 semana | não AMP | <ul><li>Sinalizador indicando que um identificador de usuário final está definido</li><li>Ele é usado para reduzir o tempo de carregamento do site</li></ul> |
| af\_id | appsflyer.com | 395 dias | não AMP quando 3PC permitido | Identifique um usuário no contexto de eventos de inicialização de aplicativo e navegação |
| af\_id | onelink.me | 395 dias | não AMP quando 3PC permitido | Vincule compromissos de banner, compromissos de onelink ou ambos a eventos de lançamento de aplicativos. |
| amp-afUserid | AMP CDN ou domínio do seu site | 1 ano | Para serviço de páginas por AMP |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | Domínio do seu site | 395 dias | Armazena o estado de consentimento do PBA. Previne a operação do SDK até que o consentimento do usuário seja concedido. Não definido por padrão — usado apenas quando [gating de consentimento](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) configurado. | não AMP |

</Accordion>

<div id="release-notes" />

<Accordion title="Notas de versão do Web SDK">

| Data | Versão | Observações |
| --- | --- | --- |
| 01/07/2021 | 1.0 | [Descartar parâmetros de consulta](/docs/pba-web-sdk-integration-guide#discard-query-params) |
| 01/06/2021 | 1.0 | [Implementar uma Política de Segurança de Conteúdo (CSP)](/docs/pba-web-sdk-integration-guide#implement-a-content-security-policy-csp-policy) |
| 31/08/2020 | 1.0 | [Adicionada funcionalidade de optar por participar e optar por não participar](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) |
| 16/04/2020 | 1.0 | A função customerUserId() substitui o evento IDENTIFY para enviar o CUID exclusivo |
| 30/07/2020 | 1.0 | <ul><li>Controle explícito de início/paragem para enviar eventos</li><li>Alterar o estado inicial predefinido</li></ul> |

</Accordion>

<div id="deprecations" />

<Accordion title="Descontinuações">

* Um aviso de descontinuação informa sobre a nossa intenção de parar a compatibilidade com um recurso ou método. A caraterística ou método continua a funcionar até à sua data de expiração.
* Encare os avisos de descontinuação como uma oportunidade para fazer alterações no seu código.

| Data da descontinuação | Data da descontinuação (EN: Sunset date) | Detalhes |
| --- | --- | --- |
| 16/04/2020 | A ser anunciado | **Método obsoleto:** Envio do ID de usuário do cliente (CUID) no parâmetro do evento customUserId com o eventType definido como "IDENTIFY"<br /><br />**Método atual:** Envie o CUID usando a função setCustomerUserId() . |

</Accordion>

<div data-zendesk-anchors="web-sdk-user-and-integration-guide=guia-de-usu%C3%A1rio-e-integra%C3%A7%C3%A3o-do-web-sdk h_01HFKCMH8HAW5DN4K9H1A5Q2NJ=guia-de-usu%C3%A1rio-e-integra%C3%A7%C3%A3o-do-web-sdk step-2-select-a-code-snippet=selecionar-um-code-snippet h_01KP11XJV8RDV378GMFF0DVZ8V=selecionar-um-code-snippet standard=web-sdk-padr%C3%A3o h_01KP11XJV8MN64YV17D1M0T5B9=web-sdk-padr%C3%A3o h_01KP3CJBZWK17M58W9M2EP8VC3=standard-without-smart-banners h_01KP3CJBZWKW1K9P9V1XGYM5ED=standard-with-smart-banners advanced-sdk-verification=verifica%C3%A7%C3%A3o-avan%C3%A7ada-de-sdk h_01KP11XJV8ZGF4SDXJH6FKX18E=verifica%C3%A7%C3%A3o-avan%C3%A7ada-de-sdk h_01KP3CJBZWP7HDJ0GE2DF3TTE3=advanced-verification-without-smart-banners h_01KP3CJBZWJWS9H0XVHQFF758B=advanced-verification-with-smart-banners integrating-the-web-sdk-into-the-website=integrar-o-web-sdk-no-site h_01HFKCMH8HCDNGFJEN32BNA9F2=integrar-o-web-sdk-no-site h_01HFKCMH8HVTJX37PD22ZFV0AY=installation-and-integration considerations-and-actions-required=considera%C3%A7%C3%B5es-e-a%C3%A7%C3%B5es-necess%C3%A1rias h_01HFKCMH8H0JBGD2GWY127428R=considera%C3%A7%C3%B5es-e-a%C3%A7%C3%B5es-necess%C3%A1rias javascript-code-snippet=trecho-de-c%C3%B3digo-javascript h_01HFKCMH8HC064MHGH8D66QCYK=trecho-de-c%C3%B3digo-javascript to-install-the-web-sdk-without-smart-banners=para-instalar-o-web-sdk-sem-smart-banners h_01HFKCMH8HST7G880G44WXXXB6=para-instalar-o-web-sdk-sem-smart-banners to-implement-the-web-sdk-with-smart-banners=para-implementar-o-web-sdk-com-smart-banners h_01HFKCMH8HX4SQP6YCBHJH4AX5=para-implementar-o-web-sdk-com-smart-banners h_01HFKCMH8JMMPMHFR4399QPRJV=create-a-property-in-adobe-experience-cloud h_01HFKCMH8J8WVHP7RZ2ENHGY9V=add-the-web-sdk-to-the-adobe-launch-property h_01HFKCMH8J2MAXJ3YVHJ2AJHWQ=add-the-adobe-launch-tag-to-the-website h_01HFKCMH8JWE1Q2749N54MAYRT=publish-the-adobe-launch-environment h_01HFKCMH8JFQQG0BEQ5CATGQ2P=ensure-that-the-sdk-is-working h_01HFKCMH8JCHH5WB5XRC8029DE=sending-events-optinoptout sdk-initial-state-setting=defini%C3%A7%C3%A3o-do-estado-inicial-do-sdk h_01HFKCMH8JSJR95Y9KNANABBKR=defini%C3%A7%C3%A3o-do-estado-inicial-do-sdk explicit-control=controle-expl%C3%ADcito h_01HFKCMH8JG2C43P8QZ0SKZCBB=controle-expl%C3%ADcito h_01HFKCMH8J9XDX87ES4F5WW4GJ=implement-a-content-security-policy-csp-policy content-security-policy-csp=pol%C3%ADtica-de-seguran%C3%A7a-de-conte%C3%BAdo-csp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=pol%C3%ADtica-de-seguran%C3%A7a-de-conte%C3%BAdo-csp advanced-sdk-verification-with-csp-nonce-snippets=verifica%C3%A7%C3%A3o-avan%C3%A7ada-de-sdk-com-snippets-de-nonce-csp h_01KP11XJV88YB2NSBZJTX9K7ZQ=verifica%C3%A7%C3%A3o-avan%C3%A7ada-de-sdk-com-snippets-de-nonce-csp h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners h_01HFKCMH8JG40DT9NHXG6TPMJ1=discard-query-params query-discard-options=consultar-op%C3%A7%C3%B5es-de-descarte h_01HFKCMH8JYSV81BEY5XQRZ24Y=consultar-op%C3%A7%C3%B5es-de-descarte principles-of-event-recording=princ%C3%ADpios-do-registro-de-eventos h_01HFKCMH8JZCKH1JPTGBVJ3QP4=princ%C3%ADpios-do-registro-de-eventos h_01HFKCMH8JEDEDC48AH5A2797D=conversion-and-standard-events conversion-events=eventos-de-convers%C3%A3o h_01HFKCMH8JYYB7HG2W8XQ7RFPD=eventos-de-convers%C3%A3o standard-events=eventos-padr%C3%A3o h_01HFKCMH8JQHSJF3T8SF4ZES7W=eventos-padr%C3%A3o recording-events=eventos-de-registro h_01HFKCMH8J79VD5BX96ANAYAFQ=eventos-de-registro h_01HFKCMH8JPJZQ81TYZX5PDF91=identifying-users-using-customer-user-id-cuid h_01HFKCMH8JYPNHJGYVRK1SZFYB=web-sdk-event-parameters h_01HFKCMH8J35YT2448PX8ZRM5P=recording-event-scenarios online-store=loja-online h_01HFKCMH8JQS3CTE6NTZY4G8ZR=loja-online h_01HFKCMH8J1EDH3XM5V4ECYCPS=ensuring-that-events-are-sent examples=exemplos h_01HFKCMH8J4KQSZ489TMDEN426=exemplos h_01HFKCMH8JAK25DZ1BZDFS4THD=recording-events::f1e16eae h_01HFKCMH8J4XNY5B9MKAS81T6Z=setting-customer-user-id-after-signup addtional-information=informa%C3%A7%C3%B5es-adicionais h_01HFKCMH8KJDZ0A15RMQ8BDMDH=informa%C3%A7%C3%B5es-adicionais h_01HFKCMH8KV3QD9CPBSVWM3EVE=web-sdk-cookies h_01HFKCMH8KGJTE7BMK4VSQJF33=release-notes h_01HFKCMH8KP1SHA21JZA5PTZXG=deprecations" />

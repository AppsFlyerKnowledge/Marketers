---
title: Integração da Kahuna com a AppsFlyer
metadata:
  keywords:
    - kahuna
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-09-14T11:26:59Z'
  edited_at: '2026-08-19T00:11:11Z'
  id: 212561966
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/212561966
---
> **Em resumo:** a Kahuna, um parceiro integrado da AppsFlyer, dedica-se a capacitar empresas a crescer e prosperar na era mobile. Oferecemos um novo nível de engajamento autêntico entre marcas e seus clientes, onde quer que eles estejam — na web, no e-mail, no mobile, nos canais sociais — por meio de comunicação personalizada em escala. Com tecnologia de big data e machine learning, ajudamos a criar experiências encantadoras para cada cliente com a mensagem perfeita, entregue no canal certo, no momento exato.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

Siga as instruções abaixo para configurar a integração com a Kahuna:

1. Requisitos mínimos - AppsFlyer SDK:

* Android – versão 2.3.1.18 e superior
* iOS – versão 3.3.3 e superior

2. A integração com a Kahuna exige que o <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/deviceid/">Device ID</Anchor> da Kahuna (identificador exclusivo do usuário da Kahuna) seja preenchido no SDK da AppsFlyer. Esse parâmetro é enviado com cada postback e permite a identificação de cada usuário. Para fazer isso, você deve inserir as seguintes strings no código do seu aplicativo:

<div id="important-note" />

> 📘 **Observação importante**
>
> Verifique se as linhas de código foram inseridas no local correto – depois que o SDK da Kahuna for iniciado e antes que os métodos appsflyer.sendtracking (Android) / trackAppLaunch (iOS) sejam chamados.

<Tabs>
<Tab title="Para Android">

```java
HashMap<String, Object> customData = new HashMap<String,Object>(); String deviceId = Kahuna.getInstance().getKahunaDeviceId();
customData .put("customData", deviceId); AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="Para iOS">

```objectivec
NSString *kahunaDeviceID = [Kahuna getKahunaDeviceId];
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{@"customData" : kahunaDeviceID}];
```

</Tab>
</Tabs>

<div id="setting-up-kahuna" />

## Configuração da Kahuna

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

A janela de configuração da Kahuna usa apenas a aba ***integração***.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Em sua **primeira visita**, você terá que selecionar as seguintes opções. Clique no botão ***ativar parceiro*** para permitir a configuração dos parâmetros na aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro. **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**

<div id="general-settings" />

### Configurações gerais

**Chave secreta da Kahuna, Staging e Production**

A Kahuna se conecta com a AppsFlyer por meio de uma chave secreta exclusiva. Se você ainda não tiver essa chave, deverá obtê-la com a Kahuna para continuar com a integração ou seguir as etapas abaixo. [![](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)](https://files.readme.io/941ce1b787ab4c34a502f254f7ec3ec8da356a05c99625f5e60e54b0da1f06b6-360002216249.png)

<div id="obtaining-the-kahuna-secret-key" />

### Como obter a chave secreta da Kahuna

1. Faça login na sua conta da Kahuna

2. Clique no ícone do usuário e selecione **Settings** no canto direito do menu do dashboard

<Image align="center" alt="" src="https://files.readme.io/4962454c4dd428c69e90d4ebcfa20304dc0ea57c7d58a1368c9a9369ba3e563a-207206166.png" />

3. Copie a chave secreta da Kahuna:

<Image align="center" alt="" src="https://files.readme.io/73d24826e6c55636dafbc22766910fea12fbe7a58c49079c800d5056be45352a-207229823.png" />

4. Selecione **APIs & Integrations**– nesta página, você pode encontrar os parâmetros:

* Insira a Master Key da Kahuna obtida no console da Kahuna (consulte a Seção 3)
* Se você quiser enviar os eventos para o ambiente Sandbox da Kahuna, insira a letra S no campo Staging (consulte “Teste com o Sandbox da Kahuna”)
* Para o ambiente de Production, insira a letra P no campo Production
* Se você inserir ambos, os eventos serão enviados para a produção
* Clique em **Salvar**.

<div id="default-postbacks" />

### Postbacks padrão

O AppsFlyer pode enviar postbacks automáticos para instalações de usuários do Kahuna. Use esta seção para definir o envio desses postbacks.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para enviar postbacks ao Kahuna para qualquer usuário que faça o download do aplicativo.

Clique em **Guardar.**

Depois de salvar a configuração, o AppsFlyer envia os seguintes dados ao Kahuna para cada instalação orgânica e não orgânica:

* Kahuna Dev\_ID
* Media Source
* Código do país
* Versão do sistema operativo

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Links de atribuição não estão disponíveis para Kahuna.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Permissões não estão disponíveis para Kahuna.

</Accordion>

<div id="view-user-attribution-data-in-kahuna" />

## Ver dados de atribuição de usuário no Kahuna

Os eventos de instalação podem ser visualizados como Newbies no dashboard principal do Kahuna.

<Image align="center" alt="" src="https://files.readme.io/ebbb7f265e37ead80dd77a9956b9629ce07eeb2fcc9b283ad7b6cc927fe10758-207230483.png" />

Você pode pesquisar um usuário específico ou acessar "Top People" na navegação do lado esquerdo.

<Image align="center" alt="" src="https://files.readme.io/ea6ae8494f600bb8a9b9b0af3e36a976e65d72b64052da3e7399f9a9b0c9458c-207230503.png" />

Selecionar um dos usuários abre o Mini Profile, onde você pode ver o evento de instalação "af\_install" na seção Top Events:

<Image align="center" alt="" src="https://files.readme.io/3e0a99f178cc1a9ab18886a576b4ba56878fecb6dbd0866926730fb32b65bc59-207230563.png" />

<div id="testing-with-sandbox" />

## Teste no sandbox

Se você ainda não lançou seu aplicativo na loja de aplicativos e quer testar a integração no ambiente Sandbox do Kahuna, siga estas etapas:

1. Ao configurar o Kahuna no AppsFlyer, insira "s" na caixa de texto Staging

<Image align="center" alt="" src="https://files.readme.io/b69fc390ed7f1303ee8ba6dd1345d2c76b5b4c22b4b0b6ec0957a108d709247b-360002217229.png" />

2. Verifique se você adicionou o código ao seu aplicativo para integrar os SDKs do AppsFlyer e do Kahuna, conforme descrito nas seções acima

3. Você deve obter o Advertising ID do seu dispositivo de teste (você pode encontrar o Advertising ID instalando o aplicativo no seu dispositivo e consultando os logs)

4. Peça ao AppsFlyer para incluir seu Advertising ID na allowlist

5. Desinstale o aplicativo do seu dispositivo

6. Configure esta URL com seus dados (nome do pacote do aplicativo, Advertising ID e nome da campanha... não inclua os colchetes) - [https://app.appsflyer.com/[APP PACKAGE NAME]?pid=[SOMETHING]&advertising\_id=](https://app.appsflyer.com/com.dailylabs.kahunatest?pid=Testing_Installs&advertising_id=0eea1488-3037-44b2-a944-11f8bfc3e479)[DEVICE’S ADVERTISING ID]

7. Acesse essa URL; você poderá ver isto:

<Image align="center" alt="" src="https://files.readme.io/8b16b6d84f0244db3510e4376bf5fc51b6a737e13df89da82e951e1bda90711a-207230963.png" width="486px" />

8. Instale o aplicativo no seu dispositivo

9. Acesse o dashboard do Kahuna e pesquise o usuário (você pode ativar a depuração do Kahuna e consultar os logs para obter o ID exclusivo do dispositivo do Kahuna para esse usuário.. “dev\_id”... ou, se o seu aplicativo exigir login e você passar credenciais para o Kahuna, também poderá pesquisar por essa credencial). Depois de encontrar o usuário, você deverá ver um evento “af\_install” para esse usuário.

<Image align="center" alt="" src="https://files.readme.io/b365a27e7638a6a87e6a5b46a67d329956f6a678b234bd1fd802acaeeceaaeb2-207207606.png" width="629px" />

<div data-zendesk-anchors="h_01H9FKAF22A3FTGC7CSE5K0CY4=importante h_01H9FKAF22W59PMYJRFW8HKBQ7=observa%C3%A7%C3%A3o-importante setting-up-kahuna=configura%C3%A7%C3%A3o-da-kahuna h_01H9FKAF222ES9240V0THQQ5X0=configura%C3%A7%C3%A3o-da-kahuna h_01H9FKAF227SZWFTCP9P1B7HEK=integration-tab activate-partner=ativar-parceiro h_01H9FKAF22EFF1F8D2QR1F38PV=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FKAF221EXQYBJGS8GFRF4S=configura%C3%A7%C3%B5es-gerais obtaining-the-kahuna-secret-key=como-obter-a-chave-secreta-da-kahuna h_01H9FKAF22XMJW7A89MBD0J276=como-obter-a-chave-secreta-da-kahuna default-postbacks=postbacks-padr%C3%A3o h_01H9FKAF2258JVR3XS6P7TT8H3=postbacks-padr%C3%A3o h_01H9FKAF22DMF1NNJRY3SJB5XX=attribution-link-tab h_01H9FKAF22KPY1ABFJN63XZ5CM=cost-tab h_01H9FKAF22KRDEFTVBR954JSJT=ad-revenue-tab h_01H9FKAF22HJPHZZM59TQ7RRFM=permissions-tab view-user-attribution-data-in-kahuna=ver-dados-de-atribui%C3%A7%C3%A3o-de-usu%C3%A1rio-no-kahuna h_01H9FKAF22A5910NXRFDGC1JTG=ver-dados-de-atribui%C3%A7%C3%A3o-de-usu%C3%A1rio-no-kahuna testing-with-sandbox=teste-no-sandbox h_01H9FKAF22KW2J6H2B6F9AMDP9=teste-no-sandbox" />

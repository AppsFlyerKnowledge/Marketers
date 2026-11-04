---
title: Como configurar a atribuição multi-store do Android
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2026-08-19T00:10:02Z'
  id: 207447023
  locale: pt
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/pt/articles/207447023
---
> **Resumo:** atribua seus aplicativos em várias lojas Android e visualize os dados em um único dashboard ou em um dashboard por loja.

<div id="multi-store-android-attribution" />

## Atribuição multi-store do Android

A AppsFlyer atribui aplicativos, independentemente da loja. Ou seja, Google Play Store e lojas de aplicativos Android de terceiros como Amazon, Opera, GetJar, Baidu e Huawei (também conhecidas como lojas fora do mercado principal ou lojas alternativas de aplicativos Android). (também conhecidas como lojas fora do mercado ou lojas alternativas de aplicativos Android.) (também conhecidas como lojas fora do mercado ou lojas alternativas de aplicativos Android.) Os proprietários de aplicativos, que comercializam um aplicativo por meio de várias lojas, podem escolher entre um **único** **dashboard**, com os dados de todas as lojas juntos, ou um **dashboard por loja**.

<div id="note" />

> 📘 **Observação:**
>
> * A atribuição Android da AppsFlyer é compatível com todos os tipos de identificador de dispositivo, incluindo GAID e <Anchor target="_blank" href="/marketers/pt/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>
> * Para aplicativos comercializados na China, consulte o artigo (em inglês) <Anchor target="_blank" href="/marketers/pt/docs/measure-attribution-in-the-chinese-domestic-market">Como atribuir aplicativos Android no mercado interno da China</Anchor>

![DashboardType_us-en-new.jpg](https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg)

<div id="single-dashboard-vs-dashboard-per-store" />

### Dashboard único vs. dashboard por loja

* **Dashboard único:** Combina dados de todas as lojas, incluindo a Google Play Store.
* **Dashboard por loja:** Vários dashboards, ou seja, cada loja tem seu próprio dashboard. Isso significa que você tem tantos dashboards quanto as lojas que fornecem o aplicativo.

<table><thead><tr><th> </th><th>Dashboard único<br/>[Práticas recomendadas]</th><th> Dashboard por loja</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>Nome do pacote Android</td><td colspan="2">Use o mesmo nome de pacote (idêntico) independentemente da opção selecionada. </td></tr><tr><td><span id="channel-name"></span>Nome do canal</td><td>Nada a definir</td><td><ul><li><span>Ao adicionar o aplicativo no dashboard da AppsFlyer usando a opção <strong>APK fora da loja Android</strong>, defina o canal.</span></li><li><span>O canal identifica a loja.</span></li><li>A combinação de nome do pacote Android e canal identifica exclusivamente cada dashboard da AppsFlyer.</li><li>Exemplo: O nome do pacote Android é com.abc.def e o canal é xyz_device_store. O identificador exclusivo do dashboard é com.abc.def-xyz_device_store.</li><li>Se o APK tiver uma configuração de canal, mas não houver nenhum aplicativo com essa configuração, o tráfego é atribuído ao aplicativo padrão, sendo que o aplicativo com uma configuração de canal em branco é a Google Play Store. </li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>Preenchendo o campo install_app_store</td><td><ul><li>Identifica exclusivamente a loja que fornece o aplicativo por download.</li><li>No caso da Google Play Store, o campo está em branco.</li><li>O nome da loja é definido em <a href="./set-up-multi-store-android-attribution#single-dashboard-apk-preparation">manifesto/APK</a>.</li></ul></td><td>N/D</td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#como-criar-templates-do-onelink" target="_blank">Template do OneLink</a></td><td>Ao trabalhar com o OneLink, esse método é recomendado. </td><td>N/D </td></tr><tr><td><span id="measurementattribution-links"></span>Links de mensuração/atribuição </td><td><ul><li>Os links são os mesmos independentemente da loja.</li><li>Para redirecionar para o armazenamento correto, use <a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">af_r</a> para definir o URL de redirecionamento</li></ul></td><td><ul><li>Um link exclusivo é necessário para cada loja.</li><li>Crie-os usando a página <strong>Integrações ativas</strong>.</li><li>O ID do aplicativo é o nome do canal anexado ao nome do pacote do Android. Ex: com.abc.def-def_store.<br/>Assim, os links de atribuição serão diferentes.</li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>Opções de relatórios disponíveis com o campo install_app_store</td><td>Os relatórios de dados brutos sempre incluem esse campo. No caso dos relatórios de visão geral e de cohort, entre em contato com seu CSM e peça para que ele adicione o recurso necessário. </td><td>N/D </td></tr><tr><td><span id="considerations"></span>Considerações</td><td><ul><li>Precisão da atribuição: as reinstalações de diferentes lojas não resultam em números de instalação inflados.</li><li><span>Instalações orgânicas refletirão instalações orgânicas de APKs de todas as lojas em um único dashboard.</span></li><li><span>No momento, as opções de relatório, separadas por loja, estão limitadas a visão geral, cohort e dados brutos.</span></li></ul></td><td><ul><li>Precisão da atribuição: as reinstalações são contabilizadas, o que resulta em uma atribuição menos precisa.</li><li><span>Visualize instalações orgânicas e não orgânicas e dados de eventos in-app por loja (canal) em dashboards separados na AppsFlyer.</span></li><li><span>Use o cohort para exibir relatórios combinados de todas as lojas juntos</span></li><li><p>Ative um parceiro (<a href="./partner-activation-deactivation" target="_blank">Ativar parceiro</a> está habilitado) em cada aplicativo de loja terceirizada em que o parceiro está executando uma campanha ativa. Isso ajuda a evitar discrepâncias de atribuição, especialmente ao trabalhar com Self-Reporting Networks (SRNs).<br/> </p></li></ul></td></tr></tbody></table>

<div id="set-up-tasks" />

## Tarefas de configuração

O fluxo de trabalho a seguir lista as atividades necessárias para configurar a opção desejada. As tarefas são divididas entre o profissional de marketing e o desenvolvedor.

Para a opção Dashboard-per-store, repita as tarefas para cada loja.

<div id="before-you-begin" />

### **Antes de começar**

* Decida sobre a convenção de nomenclatura para os parâmetros channel e install\_app\_store.
* Use a tabela de nomenclatura a seguir para mapear os canais e as lojas.
* A tabela é usada pelo desenvolvedor para preparar os APKs.

<table><thead><tr><th>Parâmetro</th><th>Instrução</th><th>Dashboard único<br/>[Práticas recomendadas]</th><th>Dashboard por loja</th></tr></thead><tbody><tr><td>Nome do pacote Android</td><td>Nome do pacote idêntico para todas as opções do dashboard</td><td colspan="2">Se o aplicativo já estiver na Google Play Store, use o nome do pacote existente. Exemplo: comb.abc.def</td></tr><tr><td>Nome do canal</td><td>Um valor único para cada loja.</td><td>Não definido. Deixe em branco. </td><td><p>Exclusivo para cada loja. Defina o valor no APK individual preparado para a loja e ao adicionar o aplicativo na AppsFlyer. </p><p>Não defina um canal para o APK da Google Play Store. </p></td></tr><tr><td>Instalar loja de aplicativos AF_STORE</td><td>Um valor único que identifica a loja</td><td><span>Exclusivo para cada loja. Definido no APK através do manifesto. Cada loja tem seu próprio APK. </span></td><td> Não definido</td></tr></tbody></table>

<div id="tasks" />

### Tarefas

| Etapa | Responsabilidade | Dashboard único | Dashboard por loja |
| --- | --- | --- | --- |
| 1 | Desenvolvedor | [Preparação do APK](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [Preparação do APK](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | Marketer | Nenhuma ação necessária. Presume-se que o aplicativo já está ativo na AppsFlyer. | [Adicione o aplicativo](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app) à AppsFlyer. |
| 3 | Marketer | [Preparar links de atribuição](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | Prepare links de atribuição com o ID do aplicativo combinada com o nome do canal. |
| 4 | Desenvolvedor e profissional de marketing | [Testes](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [Testes](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

<div id="procedures" />

## Procedimentos

<div id="single-dashboard-apk-preparation" />

<Accordion title="Dashboard único — preparação do APK">

O nome do pacote Android determina qual dashboard conterá os dados de atribuição. No método de dashboard único, todas as lojas têm nomes de pacotes Android idênticos. Não há nenhum conceito de parâmetro de canal aqui.

A identificação do armazenamento de download é feita por meio do parâmetro AF\_STORE definido no SDK, conforme descrito nessa seção.  O parâmetro AF\_STORE não diferencia maiúsculas e minúsculas. Por exemplo, ABC, abc, Abc.

**Para preparar o APK:**

1. Crie uma cópia da compilação do aplicativo. **Observação:** não altere o nome do pacote Android.
2. Para identificar o armazenamento individual, use um dos seguintes métodos:
   * **Método do manifesto:** adicione o seguinte na tag `<application>` do AndroidManifest.xml para identificar a loja. Defina o parâmetro AF\_STORE para o nome da loja de aplicativos.

     ```xml
     <application>
        ...
        <meta-data android:name="AF_STORE" android:value="EnterStoreNameHere"/>
        ...
     Etapa 1</application>:
     ```

     **--OU--**
   * **Método da API:** prepare um APK separado para cada loja de aplicativos alternativa. Faça a chamada para a API setOutOfStore para configurar o valor AF\_STORE. Defina um valor exclusivo para cada loja.

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("EnterStoreNameHere")
     ```

O valor definido aqui aparece no campo install\_app\_store de dados brutos da AppsFlyer. Esse campo está disponível em:

* Dashboard de visão geral
* Dashboard de cohort
* <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Relatórios de dados brutos</Anchor> (os relatórios de dados brutos são um recurso premium da AppsFlyer)

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="Dashboard único — links de atribuição">

Seja para criar links de atribuição <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">para serem usados por uma ad network</Anchor> ou pelas <Anchor target="_blank" href="/marketers/pt/docs/onelink-onboarding-guide#sobre-o-onelink">suas mídias próprias</Anchor>, siga estas etapas para garantir que o engajamento de todos os seus links de atribuição apareça em um único dashboard.

1. No link de atribuição, defina o parâmetro **URL fora da loja**. Isso preenche a macro **af\_r** no link de atribuição para redirecionar os usuários para a página de destino correta da loja de aplicativos. Por exemplo, `&af_r=https://www.destinationurl.com`

   <div id="note-1" />

   > 📘 **Nota**
   >
   > O redirecionamento padrão do **URL de aplicativos fora da loja** é definido na página <Anchor target="_blank" href="/marketers/pt/docs/app-settings">Configurações do aplicativo</Anchor>. Se já tiver sido configurado, não há necessidade de atualizar o link de atribuição porque os links de atribuição criados para o aplicativo serão preenchidos automaticamente com esse URL. <Anchor target="_blank" href="/marketers/pt/docs/app-settings#outofstore-app-url">Saiba mais</Anchor>

2. Adicione o redirecionamento de `af_r` à <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">lista de permissões de redirecionamento</Anchor>.
3. Preencha a macro `af_r` com o URL da página de destino da loja.
4. Defina <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#parâmetros-do-link-de-atribuição">parâmetros adicionais do link de atribuição</Anchor>.
5. Fontes de mídia fora da loja **usam correspondência de ID para atribuição** e a <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">modelagem probabilística</Anchor> da AppsFlyer funciona como um método de fallback.
6. Adicione um ou mais espaços reservados de ID de usuário ao URL do link:
   * `android_id`
   * `advertising_id`
   * `OAID`
7. Copie o link de atribuição e entregue-o ao parceiro da ad network.

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="Dashboard por loja — preparação do APK">

O nome do pacote Android combinado com o parâmetro de canal definido no manifesto determina qual dashboard de armazenamento conterá os dados de atribuição.

**Para preparar um APK/manifesto separado para cada armazenamento:**

* adicione o seguinte na tag `<application>` do AndroidManifest.xml para identificar a loja. Defina o parâmetro CHANNEL para o nome da loja de aplicativos.

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="EnterStoreNameHere"/>
       ...
  Etapa 1</application>:
  ```

  **Observação:** Os parâmetros diferenciam maiúsculas e minúsculas. Para o nome do canal, você deve usar apenas letras maiúsculas ou minúsculas (az ou AZ). Nenhum outro caractere, como hífen (-) ou sublinhado (\_), é permitido.

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="Dashboard por loja — adicionando o aplicativo">

Adicione um dashboard (aplicativo) identificado pela combinação do nome do pacote Android e canal definido no APK/manifesto. Exemplo: o nome do pacote Android é com.myapp e o nome do canal é abcstore, então o nome exclusivo do dashboard é com.myapp — abcstore.

Para adicionar um dashboard por loja na AppsFlyer:

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **Meus aplicativos** e clique em **Adicionar aplicativo**.
2. Selecione **Android > Loja terceirizada**.
3. Completo:
   * **Nome do pacote Android:** o nome do pacote exatamente como aparece no pacote do aplicativo.
   * Nome do canal: identificador exclusivo (nome da loja) para diferenciar entre dashboards com o mesmo nome de pacote. Verifique se você usa o mesmo valor no APK preparado para a loja.  
     **Atenção:** Para o nome do canal, você deve usar apenas letras maiúsculas ou minúsculas (az ou AZ). Nenhum outro caractere, como hífen (-) ou sublinhado (\_), é permitido.
   * **URL do aplicativo:**
     * Contém o endereço de download de URL padrão que preenche a macro af\_r nos links de atribuição. Insira o URL onde o APK está hospedado ou o URL da landing page.
     * Você pode alterar isso por link de atribuição ao criá-los.
4. Clique em **Próximo**.
5. Siga as instruções na interface para concluir a adição do aplicativo.

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="Teste — ambas as opções do dashboard">

<div id="non-organic-installs" />

#### **Instalações não orgânicas**

**Para testar instalações não orgânicas:**

1. Use um dispositivo Android que não tenha seu aplicativo instalado ou <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">registre o dispositivo</Anchor>.
2. Gere um link de atribuição de teste usando um <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink</Anchor>. Use o teste como o Nome da fonte de mídia ("&pid=test").
3. Adicione um Advertising ID que seja GAID, OAID ou ID Android ao URL de clique.

   ```http
   https://app.appsflyer.com/com.greatapp?pid=test
   &af_r=https://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   Envie o link de atribuição para você mesmo por e-mail e clique nele. **Depois de ser redirecionado, não instale a partir da loja**. Em vez disso, instale o aplicativo atualizado versão beta com o SDK de atribuição da AppsFlyer incorporado e inicialize-o.

| Dashboard único | Dashboard por loja |
| --- | --- |
| <ol><li>Verifique o relatório de dados brutos da instalação do aplicativo na página de exportação de dados.</li><li>Você deve ver uma conversão de instalação com a fonte de mídia de teste. Sob a coluna **Instalar App Store,** você deve ver o nome da loja como ele aparece no arquivo manifest.xml.</li><li>Você também deve ver o parâmetro "af\_installstore": "STORE\_NAME" nos registros de instalação.</li></ol> | <ol><li>Acesse o aplicativo necessário por dashboard da loja.</li><li>Verifique o relatório de dados brutos de instalações do aplicativo na página de exportação de dados ou consulte a página de visão geral do aplicativo.</li><li>Você deve ver uma conversão de instalação com a fonte de mídia “teste”.</li></ol> |

<div id="organic-installs" />

#### **Instalações orgânicas**

**Para testar instalações orgânicas:**

1. Use um dispositivo Android que não tenha seu aplicativo instalado ou que esteja <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">registrado</Anchor>.
2. Instale a versão beta do aplicativo atualizado com o SDK de atribuição da AppsFlyer incorporado e inicialize-o.
3. Verifique os resultados:

<div id="expected-results" />

#### Resultados esperados

| Dashboard único | Dashboard por loja |
| --- | --- |
| Verifique a página de visão geral para uma nova instalação orgânica (abaixo de fonte de mídia “orgânica”). Atualmente, com o método de aplicativo único, não há indicação quanto à origem das instalações orgânicas. | <ol><li>Acesse o dashboard e a página de visão geral do aplicativo específico para a loja testada.</li><li>Você deverá ver uma conversão de instalação na fonte de mídia "orgânica".</li></ol> |

</Accordion>

<div id="additional-features" />

## Funcionalidades adicionais

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="Direcionando usuários do Facebook para a loja de aplicativos da Amazon">

1. Configure um link de URL para o aplicativo nas configurações do aplicativo Meta, na seção **Android**.
2. Faça login na Meta como administrador do aplicativo, acesse <Anchor target="_blank" href="https://developers.facebook.com/apps/">https://developers.facebook.com/apps/</Anchor> e escolha o aplicativo.
3. Acesse as configurações e encontre suas configurações de Android. Se você ainda não configurou o Android, adicione a plataforma.
4. Preencha as informações necessárias, incluindo o URL da loja de aplicativos da Amazon específico para seu aplicativo.  

   [![outofstore_1.png](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)](https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png)
5. No dashboard da AppsFlyer, em “Integrações ativas”, selecione “Meta Ads” e insira o mesmo Facebook App ID usado para registrar anúncios de instalação de aplicativos mobile na loja da Meta com a AppsFlyer.

</Accordion>

<div id="getting-the-data-appsflyer-reports" />

<Accordion title="Obtendo os dados: relatórios adicionais da AppsFlyer">

Além do dashboard de visão geral, você pode usar os seguintes métodos de relatório na AppsFlyer.

* Coorte:
  * Combine vários dashboards (aplicativos) em um único relatório
  * Veja a performance de cada dashboard, dividindo por install\_app\_store
* Pull API (para o método de aplicativo único) A <Anchor target="_blank" href="/marketers/pt/docs/pull-api-aggregate-data">Pull API</Anchor> instala dados brutos e não contém **Instalar App Store** por padrão. Para incluir a coluna, adicione o seguinte à chamada da Pull API: `&additional_fields=install_app_store`
* Dashboard personalizado (para o método de vários aplicativos) se você usar a abordagem de vários painéis, use o <Anchor target="_blank" href="/marketers/pt/docs/custom-dashboards">dashboard personalizado</Anchor> para combinar dados de performance de vários aplicativos em um só lugar.

</Accordion>

<div id="referrer-implementation-thirdparty-android-app-stores" />

<Accordion title="Implementação de referrer — lojas de aplicativos Android de terceiros">

A atribuição de referrer de lojas terceirizadas é compatível com o SDK da seguinte forma:

* **O referrer da loja da Samsung:** Suporte nativo.
* **O referrer da loja da Huawei:** Uma dependência deve ser adicionada pelo seu desenvolvedor. Consulte o [Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer).
* **O referrer da loja da Xiaomi GetApps:** Uma dependência deve ser adicionada pelo seu desenvolvedor. Consulte o [Dev Hub](https://dev.appsflyer.com/hc/docs/install-android-sdk#xiaomi-getapps-store-referrer).

Lojas de aplicativos Android de terceiros que possuem integrações de atribuição de referrer com a AppsFlyer

| Loja de aplicativos terceirizada | A partir de | Versão do SDK |
| --- | --- | --- |
| <span id="huawei-app-store"></span>Loja da Huawei | Julho de 2020 | 6.14.0 + |
| <span id="samsung-galaxy-store"></span>Samsung Galaxy Store | Dezembro de 2020 | 6.1.1 + |
| <span id="xiaomi-getapps-store"></span>Xiaomi GetApps | Setembro de 2022 | 6.9.0 + |

</Accordion>

<div id="3rd-party-raw-data" />

<Accordion title="Referrer de lojas terceirizadas em relatórios de dados brutos">

A atribuição por um referrer de lojas terceirizadas é refletida nos relatórios de dados brutos da seguinte forma:

* Tipo de correspondência: o nome da loja atribuída. Por exemplo: `huawei_referrer`.
* Colaborador: se o usuário tiver engajado com várias lojas de aplicativos antes de instalar o aplicativo, a AppsFlyer considera esses engajamentos como colaboradores. A instalação é concedida ao engajamento do último clique. Exemplo:
  * Um usuário clica em um anúncio exibido pelo Google e é redirecionado para a Play Store. O usuário não faz o download do aplicativo.
  * O usuário clica em outro anúncio e é redirecionado para a Samsung Galaxy Store. O usuário faz o download e instala o aplicativo.
  * A atribuição é concedida à ad network, fazendo com que o usuário seja redirecionado para a Samsung Galaxy Store. O Google é reconhecido como colaborador.

</Accordion>

<div id="troubleshooting" />

## Resolução de problemas

<div id="installs-attributed-to-the-default-app" />

### Instalações atribuídas ao aplicativo padrão

Se você criar um APK de aplicativo com uma configuração de canal, mas não criar um dashboard para ele na conta da AppsFlyer: As instalações são atribuídas ao aplicativo padrão, geralmente o app da Google Play Store na sua conta. Se não houver nenhum aplicativo padrão, nenhum dado será gravado para o aplicativo.

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Redirecionamento do OneLink para múltiplas lojas de aplicativos | Múltiplas lojas de aplicativos só podem ser definidas no <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor> se o nome do pacote do aplicativo for o mesmo para todas as lojas de aplicativos e se você implementar a opção de dashboard único. |
| Loja de aplicativos na instalação | Este parâmetro não está disponível para agências ou ad networks. |
| Redirecionamento do OneLink para lojas terceirizadas | Se o seu aplicativo Android estiver disponível exclusivamente por meio de uma loja terceirizada, [você deve definir o status da Google Play Store como “Published out of store” ao adicionar o aplicativo](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app). Escolher qualquer outro status impedirá o redirecionamento para a loja terceirizada e resultará em uma mensagem de erro. |
| Receita de anúncios | Os valores de `af_ad_revenue` não podem ser agrupados por valores de `install_app_store`. |

<div data-zendesk-anchors="multistore-android-attribution=atribui%C3%A7%C3%A3o-multi-store-do-android h_01HJ369QB8PDKG7QQRV840KRAY=atribui%C3%A7%C3%A3o-multi-store-do-android h_01HJ369QB876GZKQCGJZQDXDRF=observa%C3%A7%C3%A3o single-dashboard-vs-dashboard-per-store=dashboard-%C3%BAnico-vs-dashboard-por-loja h_01HJ369QB8SRN61ABBZ51TKFX2=dashboard-%C3%BAnico-vs-dashboard-por-loja reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=tarefas-de-configura%C3%A7%C3%A3o h_01HJ369QB8NPE8FAHR42D2YN0K=tarefas-de-configura%C3%A7%C3%A3o before-you-begin=antes-de-come%C3%A7ar h_01JD2DEXW74MFE44FM3S0JCK5Q=antes-de-come%C3%A7ar tasks=tarefas h_01JD2DFF2K0APZ98JV1X09ZB33=tarefas procedures=procedimentos h_01HJ369QB990HH38TRQESQVFWN=procedimentos single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation h_01HJ369QB9V3W9R3EB6SJSNBED=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links h_01HJ369QB9H3J6E892X4V15AYJ=single-dashboard-attribution-links h_01K5EJP59771926PMZBRC0C2AB=nota dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation h_01HJ369QB9SP4DHZM5JB0RKEWG=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app h_01HJ369QB9X58DVBTWVWD0GCAV=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options h_01HJ369QB97FN9BJKD9WRW99YG=testing-both-dashboard-options nonorganic-installs=instala%C3%A7%C3%B5es-n%C3%A3o-org%C3%A2nicas h_01HJ369QB93A3ZZFAF0JAEXFRR=instala%C3%A7%C3%B5es-n%C3%A3o-org%C3%A2nicas organic-installs=instala%C3%A7%C3%B5es-org%C3%A2nicas h_01HJ369QB9SA05Y8VES8DD1FY4=instala%C3%A7%C3%B5es-org%C3%A2nicas expected-results=resultados-esperados h_01HJ369QBAJADS4SMSDPKK9RHW=resultados-esperados additional-features=funcionalidades-adicionais h_01HJ369QBAQ49ACSG3VEGSH7D4=funcionalidades-adicionais h_01HJ369QBA1XVMZD4G019T2S9W=driving-users-to-the-amazon-app-store-from-facebook h_01HJ369QBA2WDAZNNPRRWA3MRT=getting-the-data-appsflyer-reports referrer-implementation%E2%80%94thirdparty-android-app-stores=referrer-implementation-thirdparty-android-app-stores h_01HJ369QBA4D0SG9MQE6MXB0DH=referrer-implementation-thirdparty-android-app-stores 01JBKT1E0YA06EKW27VR1DH861=3rd-party-raw-data troubleshooting=resolu%C3%A7%C3%A3o-de-problemas 01JBKV47A5YJXKYHWA7H8NQAAF=resolu%C3%A7%C3%A3o-de-problemas installs-attributed-to-the-default-app=instala%C3%A7%C3%B5es-atribu%C3%ADdas-ao-aplicativo-padr%C3%A3o h_01HJ369QBANRCTCFKTGK8BTQEC=instala%C3%A7%C3%B5es-atribu%C3%ADdas-ao-aplicativo-padr%C3%A3o traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HJ369QBAJA87QJNTYNWYX82N=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />

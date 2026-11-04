---
title: Integração do Salesforce Marketing Cloud (SFMC) com a AppsFlyer
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-01T14:53:41Z'
  edited_at: '2026-10-23T01:27:36Z'
  id: 50431751712529
  locale: pt
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/pt/articles/50431751712529
---
> **At a glance:** Integre a AppsFlyer ao Salesforce Marketing Cloud (SFMC) para direcionar usuários, por Deep linking, de campanhas de e-mail para conteúdo in-app. Sincronize dados de eventos in-app com o SFMC para criar audiências e acionar jornadas com base no comportamento real no aplicativo.

<div id="about-the-integration" />

## Aba de integração

O SFMC permite reengajar usuários existentes por meio de campanhas de e-mail, direcionando-os via deep linking para conteúdos in-app específicos, como uma promoção ou uma oferta personalizada.

Há duas opções de integração:

* **Deep linking padrão de e-mail no SFMC**: crie os links OneLink da sua campanha na AppsFlyer e depois adicione-os aos seus e-mails.
* **Integração avançada do AppExchange do SFMC**: crie links OneLink de campanha diretamente no Salesforce e importe automaticamente dados de eventos in-app para que você possa criar audiências de reengajamento. Esse é um recurso premium.

<div id="comparison-standard-vs-advanced" />

## Comparação: padrão vs. avançado

| Recursos | Deep linking padrão de e-mail no SFMC | Integração avançada do AppExchange do SFMC |
| --- | --- | --- |
| Deferred deep links | Yes | Yes |
| Deep links diretos | Yes | Yes |
| Mensuração de deep link | Yes | Yes |
| Criação de link | Na AppsFlyer | No aplicativo dedicado da Salesforce |
| Postbacks do SFMC (sincronização de eventos in-app) | Sem | Yes |

<div id="prerequisites" />

## Pré-requisitos

<Tabs>
<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

* AppsFlyer iOS SDK versão 4.9.0+
* Para iOS Universal Links, faça o seguinte no seu ambiente do SFMC: compre e implemente um <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_sender_authentication_package.htm&type=5">Sender Authentication Package</Anchor> (SAP), compre um certificado SSL (configuração de SSL) e envie um formulário de solicitação de SSL. Entre em contato com o representante da sua conta na Salesforce ou envie um Caso de suporte de entregabilidade pela ajuda da Salesforce para obter ambos.

</Tab>

<Tab title="Android / iOS">

* AppsFlyer Android SDK versão 4.9.0+
* O SFMC não é compatível com Android App Links, então o deep linking com <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">URI Scheme</Anchor> é usado no lugar. Nenhuma ação especial é necessária para oferecer suporte ao deep linking em aplicativos Android do SFMC.

</Tab>
</Tabs>

<div id="set-up-standard-sfmc-email-deep-linking" />

## Configure o deep linking padrão de e-mail do SFMC

**Para ativar ou editar a integração:**

<Accordion title="Etapa 1: Defina seu domínio de gravação de cliques no SFMC">

Para definir um domínio de gravação de cliques, siga os guias oficiais do SFMC para:

* <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_implement_ios_universal_link.htm&type=5">Implementando o iOS Universal Link</Anchor>
* <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_dns_record_maintenance.htm&type=5">Manutenção de Registro DNS</Anchor>

</Accordion>

<Accordion title="Etapa 2: Carregue seu certificado SSL no SFMC">

Para que os Links Universais do iOS funcionem corretamente, o domínio de gravação de cliques deve incluir o certificado SSL do seu domínio, que deve estar instalado na sua conta SFMC. Instruções sobre como configurar seus certificados SSL podem ser encontradas no <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_ssl_certificates.htm&type=5">guia oficial do SFMC</Anchor>.

</Accordion>

<Accordion title="Etapa 3: Definir deep linking no SFMC">

Para habilitar deep linking de e-mails no SFMC:

1. Faça login na sua conta SFMC e vá para a visualização **Email Studio**
2. Clique na aba **Admin**
3. No menu lateral, clique em **deep linking**. Nesta visualização, você pode configurar uma nova integração de deep link com seu aplicativo ou modificar as existentes.

   <Image alt="[TEXTO ALT NECESSÁRIO: descreva a tela de configuração de deep linking do SFMC]" src="https://files.readme.io/4b7e68abb76163329ab5d487425c4dfe3ee903bb3360893c9b59f40f73486858-50431735587345.png" width="3348px" />
4. Para criar uma nova configuração, clique no botão **Criar** e insira seu AppID. O valor do AppID é uma combinação do ID da sua equipe de desenvolvedores da Apple e do ID do pacote. Ambos os valores podem ser recuperados da sua conta de desenvolvedor da Apple.

   <div id="example" />

   > 📄 **Exemplo**
   >
   > Dado o prefixo de ID da equipe *5UABCDFGH* e o ID do pacote *com.your.app*, o seguinte valor deve ser inserido:  
   > 5UABCDFGH.com.your.app
   >
   > <Image alt="[TEXTO ALT NECESSÁRIO: descreva a tela de configuração de deep linking do SFMC mostrada aqui]" src="https://files.readme.io/4f5500c6f538b2b8e00db0bae1bcac240fc49b30419f4f4a8b07fb0bd3cf8f4a-50431735587985.png" width="1234px" />

5. A configuração de links universais e deep linking é concluída quando o SFMC configura o arquivo Apple App Site Association (AASA). Este processo pode levar algumas horas. Você pode ver o arquivo gerado usando o seguinte URL:

   ```
   https://<click_recording_link_domain>/apple-app-site-association
   ```

</Accordion>

<Accordion title="Etapa 4: Configure seu SDK AppsFlyer">

> 📘 **Importante!**
>
> Caso ainda não tenha feito isso, certifique-se de configurar seu aplicativo para que ele seja compatível com <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">deep linking com o OneLink</Anchor>.

Depois de configurar seu domínio de gravação de cliques para ser compatível com Links Universais, conforme descrito anteriormente, você precisa configurar seu aplicativo para fazer deep link e resolver o Link Universal.

1. Associe o domínio de gravação de cliques no Xcode:

   <Image alt="[TEXTO ALT NECESSÁRIO: descreva a tela de domínios associados no Xcode]" src="https://files.readme.io/02bee3d75c32d494d80719b2718ddf4648440bcb3ebcb2132799e44e38852629-50431735589009.png" width="1135px" />
2. Forneça o domínio de gravação de cliques para a API do SDK `setResolveDeepLinkURLs`. Esta API precisa ser chamada antes da inicialização do SDK. Para mais informações, consulte a documentação do SDK sobre <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">como resolver URLs de deep link</Anchor>.

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   * **Importante!** Se você estiver usando o Movable Ink (MI) em conjunto com o Salesforce, será necessário obter o CNAME do MI e os domínios internos do seu gerente de conta do MI e adicioná-los a `setResolveDeepLinkURLs`, além do link de clique para o Salesforce. Exemplo:

     ```swift
     AppsFlyerLib.shared().resolveDeepLinkURLs = ["salesforce-click.example.com", "mi.example.com", "example.micpn.com"]
     ```
3. Quando o aplicativo é invocado devido a um clique no Universal Link, o AppsFlyer SDK resolve o deep link e extrai o OneLink subjacente. Todos os parâmetros de deep link são então propagados para a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onappopenattribution">API onAppOpenAttribution</Anchor> para execução da lógica de deep link.

</Accordion>

<div id="send-emails-with-standard-sfmc-email-deep-linking" />

## Enviar e-mails com Deep Linking de e-mail padrão do SFMC

**Para enviar e-mails com Deep Linking de e-mail padrão do SFMC:**

1. Crie um <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">link do OneLink</Anchor>, manualmente ou na página de links do OneLink no dashboard da AppsFlyer.
2. Faça a codificação de URL de todos os valores de parâmetros ao criar o OneLink. Estes parâmetros são altamente recomendados:

| Parâmetro | Descrição | Notas |
| --- | --- | --- |
| pid | compras in-app | Canal de mídia representativo |
| C | Campaign name | A campanha que será atribuída |
| af\_dp | URL de deep link | Redirecionamento de deep link para usuários |
| af\_web\_dp | Redirecionamento de desktop | Redirecionamento para usuários de desktop |
| af\_ios\_url |  | Redirecionamento para usuários de iOS que não têm o aplicativo instalado |
| af\_android\_url |  | Redirecionamento para usuários de Android que não têm o aplicativo instalado |

3. Copie o link para o e-mail que você criar no Salesforce Email Studio. O Salesforce Marketing Cloud envolve o link com seu domínio de registro de cliques, para que qualquer clique nesse domínio redirecione para seu link de atribuição do OneLink.

**Exemplo** (parâmetros de URL mostrados sem codificação, para facilitar a leitura):

```
https://example.onelink.me/ABcd?pid=Email&c=Spring_Newsletter&af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
```

<div id="set-up-the-advanced-sfmc-app-exchange-integration" />

## Configure a integração avançada do AppExchange do SFMC

**Para configurar a integração avançada do AppExchange do SFMC:**

<Accordion title="Etapa 1: Instale o aplicativo OneLink do SFMC AppExchange">

1. Peça ao seu CSM ou envie um e-mail para hello@appsflyer.com para ativar a instalação do aplicativo no SFMC AppExchange.
2. No Salesforce, acesse o link do AppExchange que seu CSM compartilhar assim que o aplicativo estiver ativado.
3. Clique em **Instalar**.
4. Conceda permissões: peça ao administrador do Salesforce Marketing Cloud para conceder acesso ao aplicativo a usuários individuais ou a Unidades de Negócios. Talvez seja necessário fazer um "hard refresh" para ver as novas permissões.
5. Dê aos usuários acesso ao aplicativo AppsFlyer OneLink: acesse **Apps > Pacotes instalados**, selecione a guia **ACCESS**, selecione os usuários que devem poder usar o OneLink e clique em **Salvar**. Novamente, talvez seja necessário fazer um "hard refresh".

</Accordion>

<Accordion title="Etapa 2: Conclua a configuração básica">

Conclua as etapas em "[Configurar o Deep Linking padrão de e-mail do SFMC](#configure-o-deep-linking-padrão-de-e-mail-do-sfmc)" acima.

</Accordion>

<Accordion title="Etapa 3: Crie links do OneLink no Salesforce usando o aplicativo AppsFlyer OneLink">

Crie um link de atribuição separado para cada campanha.

<Image alt="[TEXTO ALT NECESSÁRIO: atualmente, o nome do arquivo é SFMC-AF-app1-en_us.png; descreva a tela do aplicativo OneLink mostrada]" src="https://files.readme.io/21d7961d03e822dd2a4ccb426dc7b5c85c3700f81a9530bc8950a67e3f1d6237-50431735591185.png" width="684px" />

**Para criar um link do OneLink:**

1. No **Salesforce**, abra o aplicativo **AppsFlyer** OneLink.
2. Clique em **Adicionar OneLink**.
3. Digite um nome no campo **Nome do link**. Considere o seguinte:
   * Escolha um nome fácil de identificar.
   * O nome do link será usado ao aplicar OneLinks a campanhas de e-mail.
4. No campo **URL base**, insira a URL longa do OneLink copiada da página **Links personalizados do AppsFlyer OneLink**.
   * Use uma URL longa para garantir que o aplicativo analise e defina os parâmetros de link.
   * Saiba como <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">copiar a URL de um link existente</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">criar um novo link do OneLink</Anchor>.
5. [Opcional] Para adicionar mais parâmetros, clique em **Adicionar parâmetro**. Veja a <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#parâmetros-do-link-de-atribuição">lista de parâmetros recomendados</Anchor>.
6. [Opcional] Para definir uma macro interna do Salesforce Marketing Cloud, clique no ícone localizado à direita de um parâmetro.
   * Recomenda-se definir uma **Subscriber key** para cada parâmetro do **OneLink**.
   * Isso permite conectar as conversões de e-mail atribuídas aos seus dados do Salesforce.
7. Clique em **Gerar link**.

</Accordion>

<Accordion title="Etapa 4: Envie e-mails com links de atribuição personalizados">

1. No **Salesforce Email Studio**, crie um novo modelo ou e-mail.
2. Clique no ícone **Edit**, na guia **Content** e selecione **Blocks**.
3. Role a tela para baixo até encontrar **AppsFlyer Button CB** ou **AppsFlyer Image CB**.

   <Image alt="[ALT TEXT NEEDED: currently the filename sf_email_edit_onelink_new.PNG; describe the Content Blocks panel shown]" src="https://files.readme.io/565a80933451dbdb1606b20f8d71964019a36f14ffd0b0ba295649a96b056cf0-50431751706641.png" width="396px" />
4. Arraste a imagem/o botão para o corpo do e-mail.
5. Clique na imagem/no botão para editar.
6. No campo **Title**, dê um nome à imagem/ao botão.
7. Selecione um **link do OneLink**.

   <Image alt="[ALT TEXT NEEDED: describe the OneLink link selector shown]" src="https://files.readme.io/1d22268b5ced4d753cb6812decdccd960e92d9d8156213f76fc67db98b52c9c7-50431751707665.png" width="415px" />
8. Salve o e-mail e envie-o.

<div id="example-1" />

> 📄 **Exemplo**
>
> Para fins de legibilidade, os parâmetros de URL não são codificados em URL:
>
> ```
> https://example.onelink.me/ABcd?pid=Email&c=Spring_Newsletter&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

</Accordion>

<Accordion title="Etapa 5: Teste seus links">

**Para testar seus links de atribuição:**

1. Crie o URL OneLink apropriado.
2. Coloque-o em um e-mail.
3. Envie o e-mail para você mesmo.
4. Clique no link.

* Se você tiver o aplicativo instalado no seu dispositivo, ele deverá ser chamado.
* Se as APIs de deep linking relevantes do SDK da AppsFlyer forem implementadas, deve haver um deep link para o conteúdo relevante.
* Um clique deve aparecer tanto no painel da AppsFlyer, atribuído à fonte de mídia e campanha fornecidas.
* Um clique aparece nos dados do Salesforce.

</Accordion>

<div id="dynamic-emails" />

## E-mails dinâmicos

Se você precisar gerar links dinamicamente para representar conteúdo dinâmico por usuário, use a API do OneLink.

Para isso, use uma atividade de script do Automation Studio no Journey Builder do SFMC que chame a API do OneLink antes do envio, grave o deep link gerado em um campo da Data Extension de envio para cada contato e, em seguida, faça o e-mail buscar esse campo com uma simples consulta de AMPscript.

<div id="advanced-sfmc-in-app-events-data-sync" />

## Sincronização avançada de dados de eventos in-app do SFMC

Esse recurso permite que a AppsFlyer envie automaticamente os dados de eventos in-app do seu aplicativo para o Salesforce Marketing Cloud, onde eles são armazenados em uma Data Extension dedicada. Use esses dados para criar audiências, acionar jornadas e personalizar campanhas com base no comportamento real do aplicativo, como compras, cadastros ou conclusão de níveis.

Este é um recurso premium, disponível como parte da integração avançada do AppExchange do SFMC.

<div id="how-it-works" />

### Como funciona

Quando um usuário realiza um evento in-app (por exemplo, ao concluir uma compra), a AppsFlyer envia um postback para o conector do SFMC. O conector grava os dados do evento em uma Data Extension na sua conta do SFMC, onde cada linha representa um evento para um contato. A partir daí, use o Journey Builder do SFMC ou o Automation Studio para acionar comunicações de acompanhamento com base nesse evento.

**Para configurar a sincronização avançada de dados:**

<Accordion title="Etapa 1: Ativar o envio de postback na AppsFlyer">

1. Na AppsFlyer, acesse **Colaborar > Integrações ativas** e pesquise por Salesforce Marketing Cloud.
2. Selecione o aplicativo que você quer configurar e clique em **Configurar integração**.
3. Na guia **Integração**, verifique se a opção **Ativar parceiro** está ativada.
4. Role até **Postbacks de eventos in-app** e ative a opção.
5. Clique em **Adicionar evento** e mapeie os eventos da AppsFlyer que você quer enviar para o SFMC. Para cada evento, selecione-o na lista de eventos do seu aplicativo e defina a condição de envio: **Somente este parceiro** (envia apenas eventos atribuídos ao tráfego do SFMC) ou **Todas as fontes de mídia, inclusive orgânico** (recomendado para a criação de audiências, pois envia cada ocorrência do evento independentemente da atribuição).
6. Clique em **Guardar integração**.

<div id="note-1" />

> 📘 **Note**
>
> Somente os eventos que a AppsFlyer já recebeu do seu SDK ou da integração S2S aparecem na lista de eventos. Se um evento estiver faltando, primeiro verifique a implementação do seu SDK.

</Accordion>

<Accordion title="Etapa 2: Verificar a Data Extension no SFMC">

Depois que o primeiro postback for enviado, a AppsFlyer criará automaticamente uma Data Extension na sua conta do SFMC, chamada Installs-`{mid} ou Events-{mid}`. Para verificar:

1. No SFMC, acesse **Email Studio > Data Extensions**.
2. Pesquise a Data Extension do seu aplicativo.
3. Confirme se as linhas estão sendo preenchidas com dados de evento. Cada linha deve incluir o identificador de contato, o nome do evento, o carimbo de data/hora do evento e os parâmetros do evento.

Se a Data Extension não foi criada automaticamente, confirme se o aplicativo do conector do SFMC está instalado corretamente e se o administrador do SFMC concedeu a ele as permissões necessárias para gravar dados.

</Accordion>

<Accordion title="Etapa 3: Usar dados de evento no Journey Builder">

1. No SFMC, abra o Journey Builder e crie ou edite uma jornada.
2. Defina a fonte de entrada como **Data Extension** e selecione a Data Extension da AppsFlyer para seu aplicativo.
3. Configure os critérios de entrada, por exemplo, contatos cujo event\_name seja igual a af\_purchase.
4. Monte as etapas da jornada de que você precisa (enviar e-mail, esperar, ramificar por valor do evento e assim por diante).
5. Ative a jornada.

> 👍 **Tip**
>
> Use o parâmetro af\_sub1 nos seus OneLinks para transmitir a subscriber key do SFMC como identificador do usuário. Isso permite que os postbacks correspondam ao registro de contato correto no Salesforce, possibilitando a personalização no nível do contato, em vez de apenas a atribuição no nível da campanha.

</Accordion>

<div id="postback-data-fields" />

### Campos de dados de postback

O conector do SFMC cria duas Data Extensions na sua conta: uma para instalações e outra para eventos in-app. Todos os campos existem no esquema, mas alguns não são preenchidos no momento. Os campos marcados como "not written" fazem parte do esquema, mas sempre ficarão vazios.

<Accordion title="Campos de dados">

**Campos da Data Extension de instalação (49 campos)**

| Campo | Gravado | Notas |
| --- | --- | --- |
| Tipo de toque | Yes |  |
| Hora do toque | Yes |  |
| Nome do evento | Yes |  |
| Fonte do evento | Yes |  |
| Media Source | Yes |  |
| Disponível apenas em <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports">relatórios avançados</Anchor>. | Yes |  |
| Campaign | Yes |  |
| ID da campanha | Yes |  |
| Subparâmetros de 1 a 5 | Yes | Mapear para af\_sub1 até af\_sub5 no OneLink |
| Region | Yes |  |
| Código do país | Yes |  |
| Sequência de caracteres | Yes |  |
| ID da conta do anunciante com a ad network | Yes |  |
| Código postal | Yes |  |
| Validação de compra da AppsFlyer | Yes |  |
| IP | Yes |  |
| ID da AF | Yes | Identificador exclusivo de dispositivo da AppsFlyer |
| IDFV | Yes |  |
| Janela de lookback solicitada | Yes |  |
| Categoria do dispositivo | Yes |  |
| Platform | Yes |  |
| Versão do sistema operativo | Yes |  |
| Versão do aplicativo | Yes |  |
| Versão do SDK | Yes |  |
| Sequência de caracteres | Yes |  |
| App Name | Yes |  |
| É retargeting | Yes |  |
| Tipo de correspondência | Yes |  |
| User-Agent | Yes |  |
| Tempo de instalação | Yes |  |
| Hora do evento | Yes |  |
| Valor de deep link | Yes |  |
| deep\_link\_sub1 a sub10 | Sem | Existe no esquema, não foi registrado |
| IDFA | Sem | Existe no esquema, não foi registrado (identificador do dispositivo iOS) |
| ID do anunciante | Sem | Existe no esquema, não foi registrado (GAID do Android) |

**Campos da Extensão de Dados de eventos in-app**

Todos os campos de instalação acima, mais:

| Campo | Gravado | Notas |
| --- | --- | --- |
| É atribuição primária | Sem | Existe no esquema, não foi registrado |
| Janela de reengajamento | Sem | Existe no esquema, não foi registrado |
| Valor do evento | Sem | Existe no esquema, não foi registrado |
| Moeda da receita do evento | Sem | Existe no esquema, não foi registrado |
| Receita do evento em USD | Sem | Existe no esquema, não foi registrado |

</Accordion>

<div id="troubleshooting" />

### Resolução de problemas

* **Sem dados na Extensão de Dados**: Verifique se os botões de alternância "Ativar parceiro" e "postbacks de eventos in-app" estão ativados e se os eventos de que você precisa estão mapeados. Confirme também se o aplicativo da SFMC tem permissões de gravação de dados na sua conta da SFMC.
* **Eventos aparecem, mas não há contatos correspondentes**: Certifique-se de que você esteja passando af\_sub1=%%\_subscriberkey%% nos seus OneLinks para que os postbacks possam corresponder aos contatos do SFMC.
* **Extensão de Dados não criada**: Entre em contato com seu CSM ou com o suporte da AppsFlyer para confirmar se o conector foi provisionado corretamente para a sua conta.

<div data-zendesk-anchors="h_01M1EKQ4FWJDKEECDASNHC226Z=aba-de-integra%C3%A7%C3%A3o h_01M1EKQ4FWVTQ3R02AE6QREKKK=compara%C3%A7%C3%A3o-padr%C3%A3o-vs-avan%C3%A7ado h_01M1EKQ4FW9XVMFC7FXD8551C1=pr%C3%A9-requisitos h_01M1EKQ4FW115929RS4BR442QF=configure-o-deep-linking-padr%C3%A3o-de-e-mail-do-sfmc h_01HE7RCE5NE25563AAGBH0EPZC=exemplo h_01HE7RCE5N1WQA3XEN9W1QY29K=importante h_01M1EKQ4FW5Q23VEPA4YJK9MQF=enviar-e-mails-com-deep-linking-de-e-mail-padr%C3%A3o-do-sfmc h_01M1EKQ4FW91474YRH5GZ0K805=configure-a-integra%C3%A7%C3%A3o-avan%C3%A7ada-do-appexchange-do-sfmc h_01HA51F56HX6VQDYNAQAADKBHJ=exemplo-1 h_01M1EKQ4FW48QWSZ9W5J80AZVZ=e-mails-din%C3%A2micos h_01M1EKQ4FW4N9ZGBDGYZ6VAKWN=sincroniza%C3%A7%C3%A3o-avan%C3%A7ada-de-dados-de-eventos-in-app-do-sfmc h_01M1EKQ4FWVP1A3J89BGQBV8A8=como-funciona h_01M1EKQ4FWZZS3D4T5QW7HNQ9W=campos-de-dados-de-postback h_01M1EKQ4FW366GDCCXJS7TDEQS=resolu%C3%A7%C3%A3o-de-problemas" />

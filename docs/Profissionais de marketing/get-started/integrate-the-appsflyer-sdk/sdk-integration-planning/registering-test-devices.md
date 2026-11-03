---
title: Registrando dispositivos de teste
metadata:
  keywords:
    - whitelisting
    - Testing
    - device
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-03-10T08:19:35Z'
  edited_at: '2026-08-29T00:14:48Z'
  id: 207031996
  locale: pt
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/pt/articles/207031996
---
> **At a glance:** **Resumo:** ao realizar testes de atribuição, registre o seu dispositivo de teste para garantir que cada instalação seja registrada como uma nova instalação. Um dispositivo de teste registrado impede que as instalações sejam registradas como reinstalações.

## Por que registrar um dispositivo de teste?

Ao executar testes de atribuição, a janela de reatribuição limita as atribuições de instalação a uma por janela de 90 dias. Portanto, se você usar o mesmo dispositivo várias vezes para testar atribuições de instalação, nada será gravado. O registro de um dispositivo de teste impede que as instalações sejam registradas como reinstalações.

## Métodos para registrar um dispositivo de teste

Registrar um dispositivo de teste inclui selecionar o sistema operacional do dispositivo (Android, iOS ou Windows) e adicionar o identificador do dispositivo.

Você pode usar um dos seguintes métodos:

* [Faça o download e baixe o aplicativo My Device ID by AppsFlyer:](#register-a-device-using-the-appsflyer-device-id-app-admin-only) Depois de instalar o aplicativo no dispositivo de teste, você pode registrar automaticamente o dispositivo e compartilhar os detalhes do device ID na sua conta da AppsFlyer. O dispositivo será listado automaticamente na página **Dispositivos de teste**.

> 📘 **Note**
>
> * Em dispositivos de teste iOS 14+, você pode usar esse método somente quando a AppTransparency Tracking (ATT) foi implementada em seu aplicativo e você deseja executar testes como um usuário que permite o rastreamento. Caso contrário, use o método manual.
> * Se a autenticação de dois fatores (2FA) estiver ativada na sua conta do AppsFlyer, você não poderá registrar dispositivos de teste usando o aplicativo, porque o aplicativo não oferece suporte à autenticação por 2FA. Nesse caso, use o método manual para registrar dispositivos de teste.

* [Adicionar manualmente o dispositivo de teste:](#register-a-device-manually) qualquer usuário de conta pode registrar diretamente um dispositivo de teste, adicionando o identificador do dispositivo à página **Dispositivos de teste**.

Lembre-se:

* Dispositivos de teste registrados estão disponíveis para todos os aplicativos hospedados na conta.
* As ad networks precisam pedir a um anunciante para adicionar dispositivos. As agências podem adicionar seus próprios dispositivos.

<Accordion title="Identificadores de dispositivos compatíveis">

Os identificadores de dispositivo incluem:

* **Android:** AID (GAID ou OAID), IMEI, Android ID

> 📘 **Note**
>
> Ao registrar um dispositivo de teste, você só deve adicionar identificadores de dispositivo IMEI ou Android ID se seu app coletar e usar esses identificadores.

* **iOS:** IDFA, IDFV
* **Windows Phone:** ID de publicidade do Windows

</Accordion>

## Gerenciar o registro do dispositivo de teste

<Accordion title="Registrar um dispositivo usando o app de device ID da AppsFlyer">

**Para fazer o download do app de device ID:**

1. Faça o download e instale o aplicativo usando o QR code (Google Play store) ou um dos links fornecidos:

   <div id="android" />

   <Accordion title="com o Android">

   [<Image alt="kb_qr_code.png" src="https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png" width="50%" />](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

   Links: [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en) e [loja externa](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

   </Accordion>

   <div id="ios" />

   <Accordion title="iOS">

   [<Image alt="kb_qr_code.png" src="https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png" width="50%" />](https://files.readme.io/e9b6e2c498b76b5d673d750b4721b2b428603d9e8fdc941ebb6e106274b93bba-49173115688593.png)

   </Accordion>

   <div id="windows" />

   <Accordion title="Windows">

   [<Image alt="" src="https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png" width="50.91%" />](https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png)

   </Accordion>

2. Em um dispositivo iOS 14.5+, se você quiser permitir a coleta de IDFA, clique em **Permitir** quando o prompt da ATT for exibido. [<Image alt="" src="https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png" width="50%" />](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)
3. Na tela Android/iOS/Windows, clique em **Registrar** para registrar um dispositivo.

   <div id="android::db8cc168" />

   <Accordion title="Android">

   [<Image alt="" src="https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png" width="50%" />](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)

   </Accordion>

   <div id="ios::80f176b3" />

   <Accordion title="iOS">

   [<Image alt="" src="https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png" width="50%" />](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)

   </Accordion>

   <div id="windows::6c6af14b" />

   <Accordion title="Windows">

   [<Image alt="" src="https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg" width="50%" />](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)

   </Accordion>

4. Insira suas credenciais de login da AppsFlyer. O dispositivo agora está registrado.
5. Clique em **Compartilhar** detalhes para compartilhar as informações do device ID.

</Accordion>

<Accordion title="Registrar um dispositivo manualmente">

Os usuários da conta podem registrar manualmente um dispositivo:

1. Na AppsFlyer, no menu lateral, selecione **Configurações** -> **Dispositivos de teste**.
2. Selecione **Testar dispositivos**.
3. Clique em **+ Adicionar dispositivo**.

   [<Image alt="" src="https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png" width="50%" />](https://files.readme.io/e28ef06002e423d4cf7863d4c7fd2b269a0ede5c4b996a50cee25ffbedfcd9d1-31773630618769.png)
4. Complete o seguinte:
   * **Nome (use apenas letras do alfabeto romano):** insira um nome de identificação exclusivo para o dispositivo.
   * **Sistema operacional:** Selecione um sistema operacional.
   * **Tipo de device ID:** Selecione um identificador de dispositivo.
   * **Device ID:** Forneça o device ID de acordo com o sistema operacional:

     <Accordion title="/docs/ctv-pc-and-console-platform-attribution-concepts">

     Como obter os identificadores IDFA ou IDFV:

     * **IDFA:** Para obter o IDFA, instale a aplicação de ID de dispositivo da AppsFlyer no seu dispositivo de teste. Para aprender como, veja: [Adicione um dispositivo](#register-a-device-manually) utilizando a aplicação de ID de dispositivo da AppsFlyer (apenas para administradores) acima.
     * **IDFV:** Para obter o IDFV, solicite ao seu programador para instalar a aplicação da ferramenta de teste IDFV no seu dispositivo de teste. Uma vez instalada e iniciada, a aplicação exibirá o IDFV. **Atenção: a ferramenta de teste pode ser instalada somente depois que o desenvolvedor executou as etapas preliminares no X-Code.**

     Para saber quando usar IDFA ou IDFV consulte [Registrando um dispositivo de teste iOS.](#registrar-um-dispositivo-de-teste-ios)

     </Accordion>

     <div id="android::7db075c7" />

     <Accordion title="com o Android">

     Obtenha identificadores usando o app de device ID da AppsFlyer ou digitando os códigos no dispositivo:

     | Identificador | Método de recuperação | Google Play | Outros |
     | --- | --- | --- | --- |
     | AID (GAID ou OAID) | Use o [app ID do dispositivo da AppsFlyer](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid) | Obrigatório |  |
     | IMEI | *#06#* | Não aplicável | Garanta que o desenvolvedor usou <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">setCollectImei</Anchor> para coletar o ID. |
     | ID Android | *#*#8255#*#*  (pode não funcionar em dispositivos mais recentes) | Não aplicável | Garanta que o desenvolvedor usou <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">setCollectImei</Anchor> para coletar o ID. |

     </Accordion>

5. Clique em **Salvar**. O dispositivo é exibido na lista de dispositivos registrados. **Atenção:** Embora o dispositivo seja exibido na lista de dispositivos registrados imediatamente, podem levar alguns minutos para que ele seja registrado no sistema e funcione como pretendido.

> 📘 **Note**
>
> **Adicionar mais de um identificador**
>
> Pode haver casos em que você deseja adicionar mais de um identificador ao seu dispositivo de teste, por exemplo, caso você queira ter IDFA e IDFV no mesmo dispositivo.
>
> **Para incluir um identificador adicional:**
>
> 1. Clique em **Adicionar dispositivo**.
> 2. Use o mesmo nome para o dispositivo de teste e adicione o segundo identificador.
> 3. Clique em **Salvar**.

</Accordion>

<Accordion title="Cancelar o registro de um dispositivo">

Você pode registrar até 200 dispositivos por conta.

**Para remover um dispositivo da lista:**

1. Na AppsFlyer, no canto superior direito, clique no seu endereço de e-mail.
2. Selecione **Testar dispositivos**.
3. Clique no ícone de exclusão para remover dispositivos.

</Accordion>

## Registrar um dispositivo de teste iOS

O fluxograma abaixo ilustra os possíveis cursos de ação ao registrar seus dispositivos de teste iOS.

[![](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)](https://files.readme.io/214818cd73ebc8cd5d3479d27e3074fec55ec7f9e3d4702b17f3c8811270f54e-31773630621585.png)

Selecione entre as seguintes opções ao registrar seu dispositivo de teste iOS:

<Accordion title="Registrar seu dispositivo de teste com IDFA">

#### **Quando usar o IDFA para registrar um dispositivo de teste?**

Você pode registrar um dispositivo usando o IDFA se a AppTransparencyTracking (ATT) tiver sido implementada em seu aplicativo e se você quiser executar testes como um usuário que permite o rastreamento. Ao abrir o aplicativo pela primeira vez, clique em **Permitir** no prompt da ATT.

#### **Como registrar seu dispositivo de teste com um IDFA?**

Para isso, registre um dispositivo usando o app de device ID da AppsFlyer.

</Accordion>

<Accordion title="Registrar seu dispositivo de teste com IDFV">

#### **Quando usar o IDFV para registrar dispositivos de teste?**

Quando o IDFA não está disponível, o IDFV é sua única opção. Você deve usar o IDFV nos seguintes casos:

* **A ATT foi implementada** mas você deseja executar testes como um usuário que não dá o consentimento à ATT. Ao abrir o aplicativo pela primeira vez, clique em **Não permitir** no prompt da ATT.
* **O ATT não foi implementado** de forma alguma.

#### **Como registrar seu dispositivo com um IDFV**

1. Antes de registrar o dispositivo de teste com um IDFV, seu desenvolvedor precisa instalar o aplicativo da ferramenta de teste IDFV em seu dispositivo de teste. Para instruções de desenvolvedores, consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app">esse artigo</Anchor>.
2. Depois que seu desenvolvedor instalar o aplicativo da ferramenta de teste IDFV, inicie-o e copie o IDFV exibido.
3. [Registre o dispositivo de teste manualmente](#register-a-device-manually) usando o IDFV.

> 📘 **Note**
>
> **Quais são os motivos para instalar o aplicativo da ferramenta de teste IDFV?**
>
> * A ferramenta de teste IDFV é usada para extrair o IDFV necessário para registrar o dispositivo de teste.
> * Quando não houver outra aplicação do seu desenvolvedor instalada no dispositivo de teste. Nesse caso, o iOS atribui um novo vendor ID toda vez que você reinstala o aplicativo. Como o teste envolve, em muitos casos, a reinstalação do aplicativo, cada reinstalação aciona o iOS para redefinir o IDFV. **O aplicativo utilitário, fingindo pertencer ao fornecedor, impede que o iOS crie um novo IDFV sempre que o aplicativo for reinstalado no dispositivo de teste.**

</Accordion>

<Accordion title="Testando com um dispositivo não registrado">

Use esta opção apenas se não puder registrar um dispositivo de teste com IDFA ou IDFV. Nesse caso, a modelagem probabilística é usada para atribuição. Cada instalação é registrada como uma nova instalação no dispositivo de teste. Este método pode ajudar no registro de instalações de teste repetidas para o mesmo dispositivo se pelo menos uma dos seguintes cenários:

* O SDK da AppsFlyer para iOS é a versão 6.8.0 ou versões anteriores.
* A detecção de reinstalação está desativada para o aplicativo (não recomendado para aplicativos publicados).
* O link de atribuição de teste contém `is_retargeting="true"`. Nesse caso, as instalações são registradas como reatribuições e estão disponíveis no dashboard e nos relatórios de dados brutos de retargeting.
* Apenas para iOS: Para impedir que o Protect360 identifique cliques como fraudulentos, adicione o parâmetro de consulta `pid="ios_testing"` ao seu link de atribuição de teste.

</Accordion>

<div data-zendesk-anchors="why-register-a-testing-device=por-que-registrar-um-dispositivo-de-teste 01H7W9EA7RQDB69QS339XFHAFZ=por-que-registrar-um-dispositivo-de-teste methods-for-registering-a-testing-device=m%C3%A9todos-para-registrar-um-dispositivo-de-teste 01H7W9EA7RRRJBFSXW3KY53R9K=m%C3%A9todos-para-registrar-um-dispositivo-de-teste managing-testingdevice-registration=gerenciar-o-registro-do-dispositivo-de-teste 01H7W9EA7R7SJVVQCST3WA6YBM=gerenciar-o-registro-do-dispositivo-de-teste 01JHJKN5Z3562N4W2H543XPC7E=android 01JHJKN5Z54T180C7G462C26Z4=ios 01JHJKN5Z51FABEGCFVTK0MPYR=windows 01JHJKTNRHHSZSC44WDWA9J2PD=android::db8cc168 01JHJKTNRJJBBA6WAC44PD33V7=ios::80f176b3 01JHJKTNRK9DY99SZ759ZGRP23=windows::6c6af14b ios::41efa11e=gerenciar-o-registro-do-dispositivo-de-teste 01JHJKDZK8084GMZ9QAZPHVBHQ=gerenciar-o-registro-do-dispositivo-de-teste 01JHJKDZK9MTNXANVEHCM18EBM=android::7db075c7 registering-an-ios-testing-device=registrar-um-dispositivo-de-teste-ios h_01H6S2AKDH181MBDFGPBP1BQPV=registrar-um-dispositivo-de-teste-ios when-to-use-idfa-for-testing-device-registration=quando-usar-o-idfa-para-registrar-um-dispositivo-de-teste 01H7W9EA7SRD5V5134H2BRZ2AF=quando-usar-o-idfa-para-registrar-um-dispositivo-de-teste how-to-register-your-testing-device-with-an-idfa=como-registrar-seu-dispositivo-de-teste-com-um-idfa 01H7W9EA7SBBCAP3Y24FFCCGJW=como-registrar-seu-dispositivo-de-teste-com-um-idfa when-to-use-idfv-for-testing-device-registration=quando-usar-o-idfv-para-registrar-dispositivos-de-teste 01H7W9EA7S3103TSHSH4XHTP1R=quando-usar-o-idfv-para-registrar-dispositivos-de-teste how-to-register-your-device-with-idfv=como-registrar-seu-dispositivo-com-um-idfv 01H7W9EA7SGTDQCRVJKKRH0EVT=como-registrar-seu-dispositivo-com-um-idfv" />

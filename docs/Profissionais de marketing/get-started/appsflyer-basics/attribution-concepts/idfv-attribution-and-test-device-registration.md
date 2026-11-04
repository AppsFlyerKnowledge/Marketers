---
title: Atribuição por IDFV e registro de dispositivos de teste
metadata:
  keywords:
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
  created_at: '2023-08-15T13:44:35Z'
  edited_at: '2026-08-18T00:09:36Z'
  id: 17798709514001
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/17798709514001
---
> **At a glance:** O IDFV é um identificador exclusivo atribuído pelo iOS a aplicativos do mesmo fornecedor. Você pode usá-lo para atribuir instalações originadas em campanhas de promoção cruzada e registrar dispositivos de teste.

O IDFV (Identifier for Vendor) é um identificador exclusivo que o iOS gera ao instalar o primeiro aplicativo pertencente ao fornecedor. Quando outro aplicativo do mesmo fornecedor é instalado no mesmo dispositivo, ele recebe o mesmo IDFV. Se todos os aplicativos do fornecedor forem excluídos do dispositivo, o IDFV também será excluído, e um IDFV diferente será gerado quando os aplicativos do fornecedor forem instalados novamente.

Segundo a Apple: "O ID para fornecedores (IDFV) pode ser usado para análises em aplicativos do mesmo provedor de conteúdo. Nesse caso, o uso do [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) framework não é necessário. O IDFV não pode ser combinado com outros dados para rastrear um usuário em aplicativos e sites de propriedade de outras empresas. Você continua sendo totalmente responsável por garantir que sua coleta e seu uso do IDFV estejam em conformidade com a legislação aplicável."

O IDFV tem os seguintes usos na AppsFlyer:

* [Atribuição de promoção cruzada](/docs/idfv-attribution-and-test-device-registration#idfv-na-atribuição-de-promoção-cruzada)
* [Registro de dispositivo de teste](/docs/idfv-attribution-and-test-device-registration#idfv-para-registro-de-dispositivo-de-teste)

<div id="idfv-in-cross-promotion-attribution" />

## IDFV na atribuição de promoção cruzada

O IDFV pode ser usado para correspondência em um cenário de atribuição de promoção cruzada. Nesse cenário, o usuário recebe um anúncio dentro de um aplicativo de propriedade da sua empresa. O anúncio está promovendo outro aplicativo que também pertence à sua empresa.

<div id="how-does-crosspromotion-attribution-using-idfv-work" />

<Accordion title="Como funciona a atribuição de promoção cruzada usando IDFV?">

1. Um anúncio do aplicativo promovido é exibido em um dos aplicativos do fornecedor. O mesmo fornecedor também é proprietário do aplicativo promovido.
2. Ao clicar no anúncio ou visualizá-lo, o SDK notifica a AppsFlyer sobre o evento de clique ou de impressão correspondente. O SDK associa o **promotor** IDFV do aplicativo ao evento (o SDK coletou automaticamente o IDFV quando o aplicativo promotor foi iniciado pela primeira vez).
3. Depois que o aplicativo promovido é instalado e aberto, o SDK notifica a AppsFlyer sobre o evento de instalação. Esse evento inclui o IDFV do **promovido** aplicativo.
4. Ao receber o evento de instalação, a AppsFlyer tenta associá-lo ao clique ou engajamento por impressão correspondente. Se ambos os eventos compartilharem o mesmo IDFV, o evento de instalação será atribuído à campanha de promoção cruzada.

</Accordion>

<div id="a-few-examples-of-idfv-attribution" />

<Accordion title="Alguns exemplos de atribuição de promoção cruzada com IDFV">

A correspondência de IDFV é usada para atribuição de promoção cruzada nos seguintes cenários:

* **Campanhas de e-mail e SMS próprios:** Uma mensagem de e-mail ou SMS é enviada aos usuários de outros aplicativos pertencentes ao mesmo fornecedor do aplicativo promovido. Essa mensagem inclui um link de atribuição que carrega o IDFV coletado do evento de instalação do aplicativo original do fornecedor. Em seguida, a AppsFlyer faz a correspondência desse IDFV com o IDFV atribuído ao evento de instalação do aplicativo promovido.
* **Campanhas de notificações push:** Uma notificação push acionada pelo SDK de um aplicativo pertencente ao mesmo fornecedor do aplicativo promovido contém um link de atribuição com o IDFV incorporado. A AppsFlyer faz a correspondência do IDFV na notificação push com o IDFV associado ao evento de instalação do aplicativo promovido.

</Accordion>

<div id="idfv-for-test-device-registration" />

## IDFV para registro de dispositivo de teste

Os anunciantes realizam testes durante o processo de onboarding da AppsFlyer para verificar se o aplicativo deles consegue registrar e enviar eventos de instalação com sucesso. O IDFV funciona como um identificador exclusivo que permite à AppsFlyer reconhecer os dispositivos usados para testes.

<div id="why-identify-devices-as-test-devices" />

<Accordion title="Por que identificar dispositivos como dispositivos de teste?">

A AppsFlyer trata de forma diferente os eventos de instalação originados de dispositivos de teste para permitir várias instalações do mesmo aplicativo. Isso geralmente é necessário para fins de teste de integração. Para permitir que a AppsFlyer reconheça esses eventos como provenientes de dispositivos de teste, o IDFV do dispositivo de teste é registrado na página **Test Device** acessível através do menu **User Account** .

</Accordion>

<div id="why-use-idfv-as-an-identifier-in-test-device-registration" />

<Accordion title="Por que usar o IDFV como identificador no registro de dispositivo de teste?">

O registro de dispositivo de teste também pode ser feito com o IDFA. No entanto, um aplicativo iOS não tem acesso ao IDFA quando o aplicativo não implementa o App Tracking Transparency (ATT) ou quando o usuário não consente em compartilhar dados pessoais. Nesses casos, podemos usar o acesso ao IDFV para identificar o dispositivo de teste, porque ele não depende do ATT.

</Accordion>

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/cross-promotion-attribution-for-marketers">Atribuição promoção cruzada para profissionais de marketing</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices#como-registrar-seu-dispositivo-com-um-idfv">Como registrar seu dispositivo de teste com o IDFV</Anchor>

<div data-zendesk-anchors="idfv-in-crosspromotion-attribution=idfv-na-atribui%C3%A7%C3%A3o-de-promo%C3%A7%C3%A3o-cruzada h_01H9041HQ7H18541W83A72B85B=idfv-na-atribui%C3%A7%C3%A3o-de-promo%C3%A7%C3%A3o-cruzada h_01H9041HQ7JE11FTWTD0XYQWRS=how-does-crosspromotion-attribution-using-idfv-work a-few-examples-of-idfv-attribution%E2%80%A6=a-few-examples-of-idfv-attribution h_01H9041HQ7YDCTJQYBYDVJZPW0=a-few-examples-of-idfv-attribution idfv-for-test-device-registration=idfv-para-registro-de-dispositivo-de-teste h_01H9041HQ8ZC679PX7HWRMG1YC=idfv-para-registro-de-dispositivo-de-teste h_01H9041HQ8K76JD72VR4EXCEZB=why-identify-devices-as-test-devices h_01H9041HQ8WS1GEAY6RGV10PF5=why-use-idfv-as-an-identifier-in-test-device-registration h_01HG809S72YC5W61GGN0CE6TP1=consulte-tamb%C3%A9m" />

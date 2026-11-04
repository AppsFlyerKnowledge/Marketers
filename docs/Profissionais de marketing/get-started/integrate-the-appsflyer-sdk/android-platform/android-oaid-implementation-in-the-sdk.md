---
title: Implementação do OAID do Android no SDK
metadata:
  keywords:
    - China
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2020-02-27T20:21:05Z'
  edited_at: '2026-08-18T00:13:18Z'
  id: 360006278797
  locale: pt
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/pt/articles/360006278797
---
> Visão geral: Colete a OAID do Android para atribuir instalações de lojas de aplicativos Android de terceiros.

<div id="about-oaid" />

## Sobre o OAID

O Open Anonymous Device Identifier (OAID) é um identificador único redefinível pelo usuário para dispositivos Android. Ele foi introduzido pela Mobile Security Alliance (MSA), pelo China Information and Communication Research Institute e pelos fabricantes de dispositivos, como uma alternativa de preservação da privacidade aos identificadores de dispositivos não reinicializáveis, como o IMEI.

O OAID é normalmente utilizado para mensuração de anúncios e atribuição de instalações em dispositivos onde o Google Play Services não está disponível (ou seja, onde o Google Advertising ID não existe).

<span id="supported-devices"></span>O OAID pode ser lido em todos os dispositivos que usam um SDK fornecido pela MSA, ou em dispositivos Huawei que usam o Huawei Mobile Service (HMS) Core SDK.

<div id="integration" />

## integração

A integração do OAID consiste em 3 etapas:

1. Integração de um SDK para gerar e fornecer o OAID (o SDK MSA ou o SDK HMS da Huawei).
2. Integração do módulo do plugin OAID da AppsFlyer.
3. Integrando o SDK da AppsFlyer.

**Observação**:

* Para aplicativos que se destinam a ser usados na China, deve ser utilizado o SDK MSA.
* Para aplicativos que se destinam a ser usados globalmente em dispositivos Huawei, deve ser utilizada a biblioteca HMS da Huawei.

<div id="msa-sdk" />

<Accordion title="MSA SDK">

**Para integrar e usar o SDK MSA**:

1. Siga as instruções no [site da MSA](http://www.msa-alliance.cn/col.jsp?id=120) para registar seu aplicativo.
   * Depois de se registrar você pode fazer o download do SDK.
   * Como parte do processo de registo, você recebe um ficheiro de certificado que tem de ser adicionado ao aplicativo.
2. Peça aos seus desenvolvedores para seguirem as suas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#msa-sdk-integration">instruções de integração</Anchor>.

</Accordion>

<div id="huawei-hms-sdk" />

<Accordion title="Huawei HMS SDK">

**Para integrar e usar o Huawei HMS SDK**:

* Peça aos seus desenvolvedores para seguirem as suas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#huawei-hms-sdk-integration">instruções de integração</Anchor>.

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="opting-out-of-oaid-collection" />

<Accordion title="Desativar a coleta de OAID">

Quando a integração do OAID estiver concluída, o SDK tenta coletar o OAID automaticamente. Se você quiser impedir a coleta de OAID para determinados usuários, peça para o desenvolvedor usar o seguinte:

<Tabs>
<Tab title="Android">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid">API setCollectOAID(false)</Anchor> ou <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid">API</Anchor> <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>

<Tab title="Unity">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectoaid">API setCollectOAID(false)</Anchor> ou <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectoaid">API</Anchor> <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>
</Tabs>

<div id="setting-oaid-manually" />

<Accordion title="Definir o OAID manualmente">

Se seu aplicativo já coleta OAID, você pode ignorar a integração do plugin OAID da AppsFlyer e simplesmente definir o valor OAID no SDK da AppsFlyer manualmente, usando a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#setting-oaid-manually">API setOaidData</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="about-oaid=sobre-o-oaid h_01HG8PXBZS1SN3SY3AAH1EKMNP=sobre-o-oaid integration=integra%C3%A7%C3%A3o h_01HG8PXBZS26P9X1TQ7J4WQNF5=integra%C3%A7%C3%A3o h_01HG8PXBZSM0QYQE4C9S1FBFB1=msa-sdk h_01HG8PXBZS3HP9X1AZ7HQ8C34Y=huawei-hms-sdk additional-information=informa%C3%A7%C3%B5es-adicionais h_01HG8PXBZSW5HNTTDRQ7DFFF4D=informa%C3%A7%C3%B5es-adicionais h_01HG8PXBZS8Z3MTQWFN5R6FFA8=opting-out-of-oaid-collection h_01HG8PXBZSYNS8R1PCW4YXHFBA=setting-oaid-manually" />

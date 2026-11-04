---
title: Campo de ID do utilizador do cliente (CUID)
metadata:
  keywords:
    - ID
    - Customer User ID
    - User
    - Mixpanel
    - Swrve
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-11-18T11:55:22Z'
  edited_at: '2026-09-11T00:12:24Z'
  id: 207032016
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/207032016
---
> **At a glance:** O CUID permite agrupar eventos do mesmo utilizador, independentemente do dispositivo, fonte de media ou canal.

<div id="what-is-cuid" />

## O que é o CUID?

O ID de utilizador do cliente (CUID) é um identificador exclusivo de utilizador. O proprietário do aplicativo normalmente o gera e define no momento do registro do usuário. O CUID permite que os donos de apps acompanhem as trajetórias dos utilizadores em diferentes dispositivos.

<div id="example" />

> 📘 **Exemplo**
>
> Um usuário com dois ou mais dispositivos tem o mesmo CUID em todos os apps. Sempre que o usuário realiza um evento em um dispositivo mobile ou desktop, o SDK captura o evento junto com o CUID. Isto permite ao anunciante combinar os dados dos dispositivos numa visualização unificada do utilizador.
>
> Alguns exemplos de utilização:
>
> * Compras in-app feitas pelo mesmo usuário no mesmo aplicativo em vários dispositivos (celular, tablet, TV, desktop) podem ser combinadas em uma única visualização.
> * Você pode compartilhar dados de performance do usuário em várias plataformas (desktop, mobile, TV) para alcançar uma experiência do usuário holística.

<div id="setting-the-cuid" />

## Configuração do CUID

Recomendamos definir o CUID o mais cedo possível no fluxo de inicialização do SDK para que o maior número possível de eventos possa ser associado a um CUID.

<Tabs>
<Tab title="Iniciando o SDK no Android native">

Assim que o CUID estiver disponível, pode ser configurado chamando `setCustomerUserID`. Você só pode associar o CUID a eventos in-app que ocorram depois de defini-lo. Portanto, o evento de instalação não será associado ao CUID quando você chamar `start` antes de `setCustomerUserID`.

<div id="associate-the-cuid-with-the-install-event" />

### Associar o CUID ao evento de instalação

Se você precisar associar o evento de instalação ao CUID, recomendamos defini-lo antes de chamar `start`.

**Importante:** Tenha em mente que definir o CUID antes de `start` pode impedir que o SDK envie o evento de instalação e, consequentemente, impedir a atribuição. Isso pode ocorrer, por exemplo, quando o utilizador inicia a aplicação pela primeira vez e sai antes do SDK conseguir definir o CUID.

No Android, você pode executar o `start` método e configurar o CUID na classe global `Application` ou em uma classe `Activity` , dependendo da implementação do aplicativo. Para obter mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#selecione-em-qual-classe-iniciar-o-sdk">Selecionar em qual classe iniciar o SDK</Anchor>.

<div id="if-the-sdk-starts-in-the-application-class" />

#### Se o SDK for iniciado na classe Application

Se você quiser associar o CUID ao install evento quando iniciar a partir da classe global `Application`class, certifique-se de adiar o envio do evento de instalação usando o `waitForCustomerUserId` método. Esse método coloca o SDK em modo de espera até que o CUID seja definido.

Observação: se, por algum motivo, a definição do CUID falhar, o SDK permanecerá em modo de espera e não enviará nenhum evento.

<div id="if-the-sdk-starts-in-an-activity-class" />

#### Se o SDK for iniciado numa classe Activity

Se você quiser associar o CUID ao evento de instalação ao iniciar a partir de uma classe `Activity` , não será necessário adiar o envio do evento de instalação. Basta executar `start` antes de executar `start`.

<div id="developer-instructions" />

#### Instruções para desenvolvedores

Informe o desenvolvedor sobre o seguinte:

* Use `waitForCustomerUserId` se o SDK for iniciado na classe `Application` global
* Links para desenvolvedores:
  * Se quiser associar o CUID ao evento de instalação, veja <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#associate-the-cuid-with-the-install-event">aqui</Anchor>.

</Tab>

<Tab title="Android nativo iOS nativo Unity React nativo">

Use o método `customerUserId` para definir o CUID. A posição de `customerUserId`  em relação ao método `start` determina quais eventos você pode associar ao CUID.

* Se você chamar `customerUserId` antes de chamar `start`, o SDK associará o CUID à instalação e aos seguintes eventos in-app
* Se você chamá-lo após `start`, o SDK associará o CUID apenas aos eventos registrados depois que você o definir.

<div id="developer-instructions-1" />

#### Instruções para desenvolvedores

Indique ao seu programador a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#setting-the-customer-user-id">Definição do ID do utilizador do cliente</Anchor> no Dev Hub.

</Tab>

<Tab title="Unity">

<div id="developer-instructions-2" />

#### Instruções para desenvolvedores

Indique ao seu programador a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">Definição do ID do utilizador do cliente</Anchor> no Dev Hub.

</Tab>

<Tab title="CONTEXTO">

<div id="developer-instructions-3" />

#### Instruções para desenvolvedores

Indique ao seu programador a referência da API <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcustomeruserid">setCustomerUserId</Anchor> no Dev Hub.

</Tab>

<Tab title="Web">

Para obter o passo a passo completo da implementação, consulte <Anchor target="_blank" href="/marketers/pt/docs/integrate-appsflyer-web-sdk#6-definir-o-customer-user-id">Definir ID de usuário do cliente</Anchor> em Integrar o SDK web da AppsFlyer.

</Tab>
</Tabs>

<div id="cuid-and-privacy" />

## CUID e privacidade

A AppsFlyer valoriza e respeita a privacidade dos seus utilizadores e <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">não permite a recolha nem a transferência de dados pessoais sensíveis para a plataforma AppsFlyer.</Anchor>

Para proteger a privacidade dos seus usuários, você não deve criar o CUID de forma que ele contenha informações que identifiquem diretamente o usuário. Isto inclui números de segurança social ou de identificação nacional.

Se o CUID contiver o endereço de e-mail ou o número de telefone de um usuário, você deverá aplicar hashing antes de enviá-lo para a AppsFlyer. Nunca envie CUIDs sem hashing que contenham dados pessoais para a AppsFlyer.

<div id="see-also" />

> 📘 **Ver também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#relatórios-de-jornada-do-usuário">Relatórios de jornada do utilizador</Anchor> (para mais informações sobre o CUID em relatórios de dados brutos)
> * <Anchor target="_blank" href="https://support.google.com/analytics/answer/6366371?hl=en">Práticas recomendadas da Google para evitar enviar PII</Anchor>

<div data-zendesk-anchors="what-is-cuid=o-que-%C3%A9-o-cuid h_01HAJ00DVHRSDBS4FFKM16JFER=o-que-%C3%A9-o-cuid h_01HAJ00DVHZ8V8MRAXN2W3T8DS=exemplo setting-the-cuid=configura%C3%A7%C3%A3o-do-cuid h_01HAJ00DVHDGM133A72HD5JXER=configura%C3%A7%C3%A3o-do-cuid associate-the-cuid-with-the-install-event=associar-o-cuid-ao-evento-de-instala%C3%A7%C3%A3o h_01HAJ00DVHDE9V2MT6JQF8SAH3=associar-o-cuid-ao-evento-de-instala%C3%A7%C3%A3o if-the-sdk-starts-in-the-application-class=se-o-sdk-for-iniciado-na-classe-application h_01HAJ00DVH746B6YJVF70PMZJ8=se-o-sdk-for-iniciado-na-classe-application if-the-sdk-starts-in-an-activity-class=se-o-sdk-for-iniciado-numa-classe-activity h_01HAJ00DVHYZBER40RJH0GM8KF=se-o-sdk-for-iniciado-numa-classe-activity developer-instructions-android=instru%C3%A7%C3%B5es-para-desenvolvedores h_01HAJ00DVHZBZCRA1VGYJY44VY=instru%C3%A7%C3%B5es-para-desenvolvedores developer-instructions::31dbab4b=instru%C3%A7%C3%B5es-para-desenvolvedores h_01HAJ00DVH2RV902D6G224A4QY=instru%C3%A7%C3%B5es-para-desenvolvedores developer-instructions-unity=instru%C3%A7%C3%B5es-para-desenvolvedores h_01HCT1MKQWSJZ9MQTA9B1GJFWQ=instru%C3%A7%C3%B5es-para-desenvolvedores developer-instructions-react=instru%C3%A7%C3%B5es-para-desenvolvedores h_01M25Y3EFC7BJAYE9YEJYA4S5A=instru%C3%A7%C3%B5es-para-desenvolvedores cuid-and-privacy=cuid-e-privacidade h_01HAJ00DVH4987JGZZVDA1NB29=cuid-e-privacidade h_01HE7RXTEPQAWV03276TDEPG0V=ver-tamb%C3%A9m" />

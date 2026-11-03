---
title: Compartilhamento avançado de dados de correspondência avançada
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-06-18T14:23:54Z'
  edited_at: '2026-10-20T03:38:32Z'
  id: 47876839961489
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/47876839961489
---
> **At a glance:** **Em resumo:** o compartilhamento avançado de dados de correspondência avançada permite que identificadores de usuário com hash, como e-mail e número de telefone, sejam encaminhados da AppsFlyer para ad networks selecionadas, permitindo que os Parceiros atribuam eventos a engajamentos com anúncios sem um Device ID.

## Sobre o compartilhamento avançado de dados de correspondência avançada

À medida que os identificadores de dispositivo se tornam menos disponíveis, as ad networks dependem cada vez mais de dados primários para corresponder a engajamentos com anúncios. O compartilhamento avançado de dados de correspondência avançada resolve essa lacuna encaminhando identificadores com hash para Parceiros compatíveis, em um formato em conformidade com a privacidade.

O recurso é opcional e configurado por parceiro. Quando habilitado em uma network com suporte, a AppsFlyer encaminha identificadores com hash junto com dados de evento de instalações, reengajamentos e eventos in-app.

> 🚧 **Important**
>
> Todos os identificadores devem receber hash com SHA-256 antes de chegar à AppsFlyer, seja no dispositivo via SDK ou no servidor via API Server-to-Server (S2S). Dados em texto simples nunca são recebidos, armazenados nem encaminhados, e qualquer valor que falhe na validação é descartado na ingestão.

### Parceiros compatíveis

O compartilhamento de dados de correspondência avançada está disponível para as seguintes networks:

| URL da página da web onde ocorreu o evento (igual à URL original em visitas ao site) | Partner ID (PID) | Campos compatíveis |
| --- | --- | --- |
| Bliss Point Media | blisspointmedia\_int | Hashed email |
| Google | googleads\_int | E-mail com hash, número de telefone com hash |
| Meta | facebook\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash |
| Meta | metweb\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash, ID de login do Facebook |
| Moloco | moloco\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash |
| Anúncios do ChatGPT | openai\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash |
| Pinterest | pinterest\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash |
| Snapchat | "snapchat\_int" | E-mail com hash, número de telefone com hash |
| Snapchat | snapweb\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash |
| Tiktok | tiktokglobal\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash |
| Tiktok | tiktokweb\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash |
| Reddit | reddit\_int | E-mail com hash, número de telefone com hash |
| Rokt | roktv2\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash |
| Roku | rokuads\_int | E-mail com hash, número de telefone com hash |
| Smadex | smadex\_int | E-mail com hash, número de telefone com hash, primeiro nome com hash, sobrenome com hash |

## O fluxo de ponta a ponta

Veja o que acontece desde o momento em que um identificador é recuperado até o momento em que chega a um parceiro:

1. O aplicativo ou backend recupera um identificador (endereço de e-mail, número de telefone ou outro tipo compatível).
2. O SDK da AppsFlyer normaliza e aplica hashing automaticamente ao identificador usando SHA-256, ou o servidor faz isso antes de enviá-lo pela API S2S.
3. O SDK ou servidor envia o identificador com hash para a AppsFlyer junto com o evento (instalação, reinstalação, reengajamento ou evento in-app).
4. Se o Compartilhamento de dados de correspondência avançada estiver habilitado para o parceiro, a AppsFlyer encaminhará o hash junto com a carga útil do evento.
5. O parceiro usa o hash para associar o evento a um usuário conhecido, melhorando a precisão da atribuição e a qualidade da correspondência.

> 📘 **Note**
>
> Identificadores com hash são encaminhados apenas para parceiros em que o Compartilhamento de dados de correspondência avançada está habilitado. Quando a configuração estiver desativada para um parceiro, nenhum dado com hash será compartilhado com esse parceiro, mesmo que haja identificadores no evento.

## Como os identificadores de usuário com hash chegam à AppsFlyer

Os identificadores com hash chegam à AppsFlyer por dois métodos: o SDK ou a API S2S. Em ambos os casos, apenas valores com hash gerado corretamente são aceitos. As seções abaixo descrevem cada método.

<div id="send-hashed-identifiers-with-the-sdk" />

<Accordion title="Envie identificadores com hash pelo SDK">

O SDK V7.0.1 introduz métodos para transmitir identificadores brutos aos SDKs Android e iOS da AppsFlyer. O SDK normaliza a entrada e aplica hashing antes de enviá-la à AppsFlyer.

O SDK executa as etapas a seguir em sequência:

1. Normaliza a entrada de acordo com os requisitos de cada parceiro.
2. Aplica hash ao valor normalizado usando SHA-256.
3. Envia apenas o valor com hash para a AppsFlyer. A entrada bruta nunca sai do dispositivo.

O SDK rejeita valores inválidos com um erro e não os envia à AppsFlyer.

> 📘 **Note**
>
> O suporte para Android e iOS está disponível a partir do SDK v7.0.1.

Os seguintes métodos estão disponíveis no SDK da AppsFlyer para transmitir identificadores:

* `setUserEmail` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuseremail">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuseremail">iOS</Anchor>)
* `setUserFbLoginId` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserfbloginid">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserfbloginid">iOS</Anchor>)
* `setUserFirstName` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserfirstname">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserfirstname">iOS</Anchor>)
* `setUserLastName` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserlastname">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserlastname">iOS</Anchor>)
* `setUserPhone` (<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setuserphone">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setuserphone">iOS</Anchor>)

Para ver detalhes de implementação, consulte os <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib">métodos do SDK para Android</Anchor> e os <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib">métodos do SDK para iOS</Anchor>.

</Accordion>

<div id="send-hashed-identifiers-with-the-s2s-api" />

<Accordion title="Envie identificadores com hash pela API S2S">

Ao enviar eventos pela API S2S de eventos in-app, os identificadores devem ser normalizados e ter hash aplicado no servidor antes do envio. A API aceita os seguintes campos:

| Campo | A descrição |
| --- | --- |
| `email_hashed` | Endereço de e-mail com Hashing |
| `phone_number_hashed` | Número de telefone com Hashing, somente dígitos |
| `phone_number_e164_hashed` | Número de telefone com Hashing no formato E.164 |
| `first_name_hashed` | Primeiro nome com Hashing |
| `last_name_hashed` | Sobrenome com Hashing |
| `fb_login_id` | ID de login do Facebook (sem Hashing; transmitido como está) |

> 🚧 **Important**
>
> Todos os campos desta tabela (exceto `fb_login_id`) são validados em relação ao formato SHA-256. A AppsFlyer descarta silenciosamente os valores que não correspondem e não os encaminha a nenhum parceiro. Ela processa normalmente os outros campos do evento.

</Accordion>

### Por que há dois campos de número de telefone?

As networks fazem a correspondência de eventos comparando o hash que a AppsFlyer encaminha com o próprio hash armazenado do número de telefone do usuário. Como o mesmo número normalizado em um formato diferente gera um hash diferente, os dois lados precisam aplicar hash a partir do mesmo formato para obter uma correspondência. Como as networks normalizam números de telefone de maneiras diferentes e a AppsFlyer recebe valores já com Hashing, ambas as versões devem ser enviadas para cobrir todos os Parceiros suportados.

* `phone_number_hashed`: para Meta e Snapchat. Formato de normalização antes do hashing: `16501234567`
* `phone_number_e164_hashed`: para Google e TikTok. Formato de normalização antes do hashing: `+16501234567`

## Normalizar e aplicar hash aos identificadores

Normalize o valor bruto exatamente como descrito abaixo, depois aplique Hashing com SHA-256 e envie o digest hexadecimal em letras minúsculas.

<div id="email-emailhashed" />

<Accordion title="E-mail (email_hashed)">

Normalize e aplique hash ao endereço de e-mail da seguinte forma:

1. Remova todos os espaços em branco.
2. Converta para minúsculas.
3. Aplique hash com SHA-256.

**Exemplo:**

`User@Example.COM` → `user@example.com` → hash SHA-256

</Accordion>

<div id="phone-number-digits-only-phonenumberhashed" />

<Accordion title="Número de telefone, somente dígitos (phone_number_hashed)">

Use isto para a Meta, o Reddit, o Pinterest e o Snapchat. Normalize e aplique hash ao número de telefone da seguinte forma:

1. Adicione o código do país no início.
2. Remova todos os símbolos, letras e zeros à esquerda.
3. Aplique hashing com SHA-256.

**Nome do imposto sobre a receita líquida**

`+1 (650) 123-4567` → `16501234567` → hash SHA-256

</Accordion>

<div id="phone-number-e164-phonenumbere164hashed" />

<Accordion title="Número de telefone, E.164 (phone_number_e164_hashed)">

Use isto para o Google, o TikTok e o Roku. Normalize e aplique hash ao número de telefone da seguinte forma:

1. Adicione o código do país no início.
2. Remova todos os símbolos, letras e zeros à esquerda.
3. Adicione o sinal `+` no início.
4. Aplique hash com SHA-256.

**Exemplo:**

`+1 (650) 123-4567` → `+16501234567` → hash com SHA-256

</Accordion>

<div id="first-name-firstnamehashed-and-last-name-lastnamehashed" />

<Accordion title="Primeiro nome (first_name_hashed) e sobrenome (last_name_hashed)">

Normalize e aplique hash ao nome da seguinte forma:

1. Remova todos os espaços em branco.
2. Converta para letras minúsculas.
3. Aplique hash com SHA-256.

</Accordion>

<div id="facebook-login-id-fbloginid" />

<Accordion title="ID de login do Facebook (fb_login_id)">

Envie o ID de login do Facebook bruto, conforme fornecido pelo SDK de Login do Facebook. Este campo não recebe hashing.

</Accordion>

## Ative o Compartilhamento de dados de correspondência avançada

O Compartilhamento de dados de correspondência avançada é controlado por parceiro e por aplicativo e deve ser habilitado explicitamente para cada network.

**Para ativar o Compartilhamento de dados de correspondência avançada:**

1. Na AppsFlyer, no menu lateral, selecione **Collaborate > Active Integrations**.
2. Pesquise o parceiro e selecione-o.
3. Ative **Advanced-Matching Data Sharing**.
4. Clique em **Guardar integração**.

Quando o Compartilhamento de dados de correspondência avançada está ativado, qualquer evento que inclua um ou mais campos de identificador compatíveis terá esses campos encaminhados ao parceiro.

> 📘 **Note**
>
> Desativar o Compartilhamento de dados de correspondência avançada interrompe imediatamente o compartilhamento de dados com hashing com esse parceiro. Outras configurações de integração, incluindo postbacks e dados de evento, não são afetadas.

## Privacidade e tratamento de dados

Quando o Compartilhamento de dados de correspondência avançada é habilitado para um parceiro, a AppsFlyer começa a encaminhar identificadores de usuário com hashing para essa network junto com os dados do evento. Antes de ativá-lo, confirme o seguinte:

* Existe uma base legal (de acordo com as leis de privacidade aplicáveis, como o Regulamento Geral sobre a Proteção de Dados (GDPR) ou a California Consumer Privacy Act (CCPA)) para compartilhar esses dados com o parceiro.
* Você atualizou sua política de privacidade e, quando necessário, obteve o consentimento do usuário.
* Suas práticas de compartilhamento de dados estão alinhadas aos termos do parceiro.

> 🚧 **Important**
>
> A AppsFlyer não processa nem armazena Informações de Identificação Pessoal (PII) em texto simples. Todos os campos de identificador são validados no momento da ingestão: valores que não estejam em conformidade com o formato SHA-256 são descartados e nunca encaminhados a nenhum parceiro.

## Perguntas frequentes

<div id="is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature" />

<Accordion title="O compartilhamento de dados de Advanced Matching é o mesmo que o recurso de e-mail e telefone com hash de audiências?">

Sem. Esses são mecanismos separados. As audiências criam listas de usuários para segmentação de anúncios. O compartilhamento de dados de Advanced Matching encaminha identificadores com hash com eventos individuais para melhorar as taxas de correspondência no nível do parceiro. A AppsFlyer planeja consolidar os dois métodos, usando o novo método de recuperação de dados tanto para o compartilhamento de dados de Advanced Matching quanto para as audiências.

</Accordion>

<div id="what-happens-if-i-send-an-invalid-hash-value" />

<Accordion title="O que acontece se eu enviar um valor de hash inválido?">

A AppsFlyer descarta o campo no momento da ingestão e não o encaminha a nenhum parceiro. Ela processa normalmente os outros campos do evento.

</Accordion>

<div id="do-i-need-to-send-all-supported-fields" />

<Accordion title="Preciso enviar todos os campos compatíveis?">

Sem. Só precisam ser incluídos os identificadores disponíveis e relevantes para os Parceiros configurados. Os campos ausentes não são encaminhados.

</Accordion>

<div id="will-advancedmatching-data-sharing-improve-install-attribution" />

<Accordion title="O Compartilhamento de Dados de Advanced Matching vai melhorar a atribuição de instalação?">

A maioria dos Parceiros não usa e-mail com hash nem telefone com hash para correspondência de instalação, reengajamento ou reinstalação. O envio desses campos ajuda principalmente os Parceiros a melhorar a correspondência de eventos in-app no lado deles. Isso não afeta a atribuição da AppsFlyer.

</Accordion>

<div id="does-appsflyer-ever-receive-plaintext-user-identifiers" />

<Accordion title="A AppsFlyer alguma vez recebe identificadores de usuário em texto simples?">

Sem. Os identificadores sempre passam por hash antes de chegar à AppsFlyer, seja no dispositivo via SDK ou no servidor via API S2S. A AppsFlyer aceita apenas valores com hash.

</Accordion>

<div data-zendesk-anchors="about-advancedmatching-data-sharing=sobre-o-compartilhamento-avan%C3%A7ado-de-dados-de-correspond%C3%AAncia-avan%C3%A7ada h_01KVFJHWK1TYAPPMZDYFAP0RX0=sobre-o-compartilhamento-avan%C3%A7ado-de-dados-de-correspond%C3%AAncia-avan%C3%A7ada supported-partners=parceiros-compat%C3%ADveis h_01KVFJHWK1VTJZH53FKNE8NZ59=parceiros-compat%C3%ADveis the-endtoend-flow=o-fluxo-de-ponta-a-ponta h_01KVFJHWK1JQ7J838YNDTYDD4A=o-fluxo-de-ponta-a-ponta how-hashed-user-identifiers-reach-appsflyer=como-os-identificadores-de-usu%C3%A1rio-com-hash-chegam-%C3%A0-appsflyer h_01KVFJHWK197KW8YBQ1NBD9XT1=como-os-identificadores-de-usu%C3%A1rio-com-hash-chegam-%C3%A0-appsflyer h_01M4ZE5P7QWCWP3FMXPM572R3R=send-hashed-identifiers-with-the-sdk h_01M4ZE5P7Q6W3G4JPQKRSSWSX6=send-hashed-identifiers-with-the-s2s-api h_why-two-phone-fields=por-que-h%C3%A1-dois-campos-de-n%C3%BAmero-de-telefone why-are-there-two-phone-number-fields=por-que-h%C3%A1-dois-campos-de-n%C3%BAmero-de-telefone normalize-and-hash-identifiers=normalizar-e-aplicar-hash-aos-identificadores h_01KVFJHWK16KQ1X1WFTTTFFND3=normalizar-e-aplicar-hash-aos-identificadores h_01M4ZE5P7Q0NJXDVM5MP0S2SKC=email-emailhashed h_01M4ZE5P7QDR4PVS9XZ68J6KW5=phone-number-digits-only-phonenumberhashed h_01M4ZE5P7Q2Z4APXNAWVJ8FES9=phone-number-e164-phonenumbere164hashed h_01M4ZE5P7Q98VNS456PMVXQQXC=first-name-firstnamehashed-and-last-name-lastnamehashed h_01M4ZE5P7QEXVV2EPX3Q550586=facebook-login-id-fbloginid turn-on-advancedmatching-data-sharing=ative-o-compartilhamento-de-dados-de-correspond%C3%AAncia-avan%C3%A7ada h_01KVFJHWK27C5FA358M526EJED=ative-o-compartilhamento-de-dados-de-correspond%C3%AAncia-avan%C3%A7ada privacy-and-data-handling=privacidade-e-tratamento-de-dados h_01KVFJHWK2BN2T7BTXANAWAX4B=privacidade-e-tratamento-de-dados faq=perguntas-frequentes h_01KVFJHWK2XB5VF8V2KPG62QYV=perguntas-frequentes h_01M4ZE5P7Q0NE2H8D3N7AX5301=is-advancedmatching-data-sharing-the-same-as-the-audiences-hashed-email-and-phone-feature h_01M4ZE5P7QCKZYS7399QED62F5=what-happens-if-i-send-an-invalid-hash-value h_01M4ZE5P7QT2SG5DBKZ3GTTZ8S=do-i-need-to-send-all-supported-fields h_01M4ZE5P7QZQJA45VV4XV00VAD=will-advancedmatching-data-sharing-improve-install-attribution h_01M4ZE5P7QVF3HQ2Q8HKAB7W98=does-appsflyer-ever-receive-plaintext-user-identifiers" />
